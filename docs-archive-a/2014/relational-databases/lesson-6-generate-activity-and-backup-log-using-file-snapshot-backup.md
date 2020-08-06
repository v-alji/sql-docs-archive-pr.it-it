---
title: 'Lezione 7: spostare i file di dati in archiviazione di Azure | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 26aa534a-afe7-4a14-b99f-a9184fc699bd
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 753863d7b8b8d8fa554f1579bee6837c525efd9b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635579"
---
# <a name="lesson-7-move-your-data-files-to-azure-storage"></a><span data-ttu-id="7712a-102">Lezione 7: Spostare i file di dati in Archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="7712a-102">Lesson 7: Move your data files to Azure Storage</span></span>
  <span data-ttu-id="7712a-103">In questa lezione verrà illustrato come spostare i file di dati in archiviazione di Azure (ma non nell'istanza di SQL Server).</span><span class="sxs-lookup"><span data-stu-id="7712a-103">In this lesson, you will learn how to move your data files to Azure Storage (but not your SQL Server instance).</span></span> <span data-ttu-id="7712a-104">È possibile seguire questa lezione anche senza aver completato le lezioni 4, 5 e 6.</span><span class="sxs-lookup"><span data-stu-id="7712a-104">To follow this lesson, you do not need to complete Lesson 4, 5, and 6.</span></span>  
  
 <span data-ttu-id="7712a-105">Per spostare i file di dati in archiviazione di Azure, è possibile usare l' `ALTER DATABASE` istruzione in quanto consente di modificare il percorso dei file di dati.</span><span class="sxs-lookup"><span data-stu-id="7712a-105">To move your data files to Azure Storage, you can use the `ALTER DATABASE` statement as it helps to change the location of the data files.</span></span>  
  
 <span data-ttu-id="7712a-106">Per questa lezione si presuppone che l'utente abbia già completato i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="7712a-106">This lesson assumes that you already completed the following steps:</span></span>  
  
-   <span data-ttu-id="7712a-107">Si ha un account di archiviazione di Azure.</span><span class="sxs-lookup"><span data-stu-id="7712a-107">You have an Azure Storage account.</span></span>  
  
-   <span data-ttu-id="7712a-108">È stato creato un contenitore nell'account di archiviazione di Azure.</span><span class="sxs-lookup"><span data-stu-id="7712a-108">You have created a container under your Azure Storage account.</span></span>  
  
-   <span data-ttu-id="7712a-109">Creazione dei criteri in un contenitore con diritti di lettura, scrittura ed elenco.</span><span class="sxs-lookup"><span data-stu-id="7712a-109">You have created a policy on a container with read, write, and list rights.</span></span> <span data-ttu-id="7712a-110">Generazione di una chiave SAS.</span><span class="sxs-lookup"><span data-stu-id="7712a-110">You also generated a SAS key.</span></span>  
  
-   <span data-ttu-id="7712a-111">Creazione di una credenziale di SQL Server nel computer di origine.</span><span class="sxs-lookup"><span data-stu-id="7712a-111">You have created a SQL Server credential on the source machine.</span></span>  
  
 <span data-ttu-id="7712a-112">Usare quindi la procedura seguente per spostare i file di dati in archiviazione di Azure:</span><span class="sxs-lookup"><span data-stu-id="7712a-112">Next, use the following steps to move your data files to Azure Storage:</span></span>  
  
1.  <span data-ttu-id="7712a-113">Innanzitutto, creare un database di prova nel computer di origine e aggiungere alcuni dati.</span><span class="sxs-lookup"><span data-stu-id="7712a-113">First, create a test database in the source machine and add some data to it.</span></span>  
  
    ```sql  
  
    USE master;   
    CREATE DATABASE TestDB1Alter;   
    GO   
    USE TestDB1Alter;   
    GO   
    CREATE TABLE Table1 (Col1 int primary key, Col2 varchar(20));   
    GO   
    INSERT INTO Table1 (Col1, Col2) VALUES (1, 'string1'), (2, 'string2');   
    GO  
  
    ```  
  
2.  <span data-ttu-id="7712a-114">Eseguire il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="7712a-114">Run the following code:</span></span>  
  
    ```sql  
  
    -- In the following statement, modify the path specified in FILENAME to   
    -- the new location of the file in Azure Storage container.   
    ALTER DATABASE TestDB1Alter    
        MODIFY FILE ( NAME = TestDB1Alter,    
                    FILENAME = 'https://teststorageaccnt.blob.core.windows.net/testcontaineralter/TestDB1AlterData.mdf');   
    GO  
  
    ```  
  
3.  <span data-ttu-id="7712a-115">Quando si esegue questa operazione, viene visualizzato il messaggio seguente: "il file" TestDB1Alter "è stato modificato nel catalogo di sistema.</span><span class="sxs-lookup"><span data-stu-id="7712a-115">When you run this, you will see this message: "The file "TestDB1Alter" has been modified in the system catalog.</span></span> <span data-ttu-id="7712a-116">Il nuovo percorso verrà utilizzato al successivo avvio del database ".</span><span class="sxs-lookup"><span data-stu-id="7712a-116">The new path will be used the next time the database is started."</span></span>  
  
4.  <span data-ttu-id="7712a-117">Quindi, impostare il database come offline.</span><span class="sxs-lookup"><span data-stu-id="7712a-117">Then, set the database offline.</span></span>  
  
    ```sql  
  
    ALTER DATABASE TestDB1Alter SET OFFLINE;   
    GO  
  
    ```  
  
5.  <span data-ttu-id="7712a-118">A questo punto, è necessario copiare i file di dati in archiviazione di Azure usando uno dei metodi seguenti: [strumento AzCopy](https://docs.microsoft.com/archive/blogs/windowsazurestorage/azcopy-uploadingdownloading-files-for-windows-azure-blobs), [pagina put](https://msdn.microsoft.com/library/azure/ee691975.aspx), informazioni di [riferimento sulla libreria client di archiviazione](https://msdn.microsoft.com/library/azure/dn261237.aspx)o uno strumento di esplorazione di archiviazione di terze parti.</span><span class="sxs-lookup"><span data-stu-id="7712a-118">Now, you need to copy the data files to Azure Storage by using one of the following methods: [AzCopy Tool](https://docs.microsoft.com/archive/blogs/windowsazurestorage/azcopy-uploadingdownloading-files-for-windows-azure-blobs), [Put Page](https://msdn.microsoft.com/library/azure/ee691975.aspx), [Storage Client Library Reference](https://msdn.microsoft.com/library/azure/dn261237.aspx), or a third-party storage explorer tool.</span></span>  
  
     <span data-ttu-id="7712a-119">**Importante:** Quando si usa questa nuova funzionalità avanzata, assicurarsi sempre di creare un BLOB di pagine e non un BLOB in blocchi.</span><span class="sxs-lookup"><span data-stu-id="7712a-119">**Important:** When using this new enhancement, always make sure that you create a page blob not a block blob.</span></span>  
  
6.  <span data-ttu-id="7712a-120">Quindi, impostare il database come online.</span><span class="sxs-lookup"><span data-stu-id="7712a-120">Then, set the database online.</span></span>  
  
    ```sql  
  
    ALTER DATABASE TestDB1Alter SET ONLINE;   
    GO  
  
    ```  
  
 <span data-ttu-id="7712a-121">**Lezione successiva:**</span><span class="sxs-lookup"><span data-stu-id="7712a-121">**Next Lesson:**</span></span>  
  
 [<span data-ttu-id="7712a-122">Lezione 8. Ripristinare un database in archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="7712a-122">Lesson 8. Restore a database to Azure Storage</span></span>](lesson-7-restore-a-database-to-a-point-in-time.md)  
  
  
