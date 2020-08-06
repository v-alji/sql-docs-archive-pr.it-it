---
title: 'Lezione 9: Ripristinare un database da archiviazione di Azure | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: ebba12c7-3d13-4c9d-8540-ad410a08356d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5e7c2350bb2a9b1f8c31da8e094459b5bc8ccd90
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637291"
---
# <a name="lesson-9-restore-a-database-from-azure-storage"></a><span data-ttu-id="0ce86-103">Lezione 9:</span><span class="sxs-lookup"><span data-stu-id="0ce86-103">Lesson 9.</span></span> <span data-ttu-id="0ce86-104">Ripristinare un database da Archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="0ce86-104">Restore a database from Azure Storage</span></span>
  <span data-ttu-id="0ce86-105">In questa lezione si apprenderà come ripristinare un file di backup del database da archiviazione di Azure in un database, che si trova in locale o in una macchina virtuale in Azure.</span><span class="sxs-lookup"><span data-stu-id="0ce86-105">In this lesson, you will learn how to restore a database backup file from Azure Storage to a database, which either resides on-premises or in a virtual machine in Azure.</span></span> <span data-ttu-id="0ce86-106">È possibile seguire questa lezione anche senza aver completato le lezioni 4, 5, 6, 7 e 8.</span><span class="sxs-lookup"><span data-stu-id="0ce86-106">To follow this lesson, you do not need to complete Lesson 4, 5, 6, 7, and 8.</span></span>  
  
 <span data-ttu-id="0ce86-107">Per questa lezione si presuppone che l'utente abbia già completato i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="0ce86-107">This lesson assumes that you already completed the following steps:</span></span>  
  
-   <span data-ttu-id="0ce86-108">È stato creato un database nel computer di origine.</span><span class="sxs-lookup"><span data-stu-id="0ce86-108">You have created a database in the source machine.</span></span>  
  
-   <span data-ttu-id="0ce86-109">È stata creata una copia di backup del database (con estensione bak) in archiviazione di Azure usando la funzionalità di [backup e ripristino SQL Server con il servizio di archiviazione BLOB di Azure](backup-restore/sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md) .</span><span class="sxs-lookup"><span data-stu-id="0ce86-109">You have created a backup of your database (.bak) in Azure Storage by using the [SQL Server Backup and Restore with Azure Blob Storage Service](backup-restore/sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md) feature.</span></span> <span data-ttu-id="0ce86-110">Si noti che è necessario creare un'altra credenziale di SQL Server durante questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="0ce86-110">Note that you will need to create another SQL Server Credential in this step.</span></span> <span data-ttu-id="0ce86-111">La credenziale usano le chiavi di account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="0ce86-111">This credential uses storage account keys.</span></span>  
  
-   <span data-ttu-id="0ce86-112">Si ha un account di archiviazione di Azure.</span><span class="sxs-lookup"><span data-stu-id="0ce86-112">You have an Azure Storage account.</span></span>  
  
-   <span data-ttu-id="0ce86-113">È stato creato un contenitore nell'account di archiviazione di Azure.</span><span class="sxs-lookup"><span data-stu-id="0ce86-113">You have created a container under your Azure Storage account.</span></span>  
  
-   <span data-ttu-id="0ce86-114">Creazione dei criteri in un contenitore con diritti di lettura, scrittura ed elenco.</span><span class="sxs-lookup"><span data-stu-id="0ce86-114">You have created a policy on a container with read, write, and list rights.</span></span> <span data-ttu-id="0ce86-115">Generazione di una chiave SAS.</span><span class="sxs-lookup"><span data-stu-id="0ce86-115">You also generated a SAS key.</span></span>  
  
-   <span data-ttu-id="0ce86-116">È stata creata una credenziale SQL Server nel computer per la funzionalità di integrazione di archiviazione di Azure.</span><span class="sxs-lookup"><span data-stu-id="0ce86-116">You have created a SQL Server credential on your machine for Azure Storage Integration feature.</span></span> <span data-ttu-id="0ce86-117">Si noti che la credenziale richiede una chiave della la firma di accesso condiviso.</span><span class="sxs-lookup"><span data-stu-id="0ce86-117">Note that this credential requires a Shared Access Signature (SAS) key.</span></span>  
  
 <span data-ttu-id="0ce86-118">Per ripristinare un database da archiviazione di Azure, è possibile seguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="0ce86-118">To restore a database from Azure Storage, you can follow these steps:</span></span>  
  
1.  <span data-ttu-id="0ce86-119">Avviare SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="0ce86-119">Start SQL Server Management Studio.</span></span> <span data-ttu-id="0ce86-120">Connettersi all'istanza predefinita.</span><span class="sxs-lookup"><span data-stu-id="0ce86-120">Connect to the default instance.</span></span>  
  
2.  <span data-ttu-id="0ce86-121">Fare clic su **nuova query** sulla barra degli strumenti standard.</span><span class="sxs-lookup"><span data-stu-id="0ce86-121">Click **New Query** on the Standard Toolbar.</span></span>  
  
3.  <span data-ttu-id="0ce86-122">Copiare e incollare il seguente script completo nella finestra Query.</span><span class="sxs-lookup"><span data-stu-id="0ce86-122">Copy and paste the following complete script to the query window.</span></span> <span data-ttu-id="0ce86-123">Modificare lo script in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="0ce86-123">Modify the script as needed.</span></span>  
  
     <span data-ttu-id="0ce86-124">**Nota:** Eseguire l' `RESTORE` istruzione per ripristinare il backup del database (con estensione bak) in archiviazione di Azure in un'istanza del database in un altro computer.</span><span class="sxs-lookup"><span data-stu-id="0ce86-124">**Note:** You run the `RESTORE` statement to restore the database backup (.bak) in Azure Storage to a database instance in another machine.</span></span>  
  
    ```sql  
  
    USE master   
    GO   
    -- Create a new database to be backed up.   
    CREATE DATABASE TestDbRestoreFrom;   
    GO   
    USE TestDbRestoreFrom;   
    GO   
    CREATE TABLE Table1 (Col1 int primary key, Col2 varchar(20));   
    GO   
    INSERT INTO Table1 (Col1, Col2) VALUES (1, 'string1'), (2, 'string2');   
    GO   
    USE TestDbRestoreFrom;   
    GO   
    SELECT * from dbo.Table1;   
    GO   
    -- Create a credential to be used by SQL Server Backup and Restore with Azure -----Blob Storage Service.   
    USE master;   
    GO   
    CREATE CREDENTIAL BackupCredential    
    WITH IDENTITY= 'teststorageaccnt',   
    SECRET = 'BO1nH/lWRdnc8TGPlQIXmGLWVCoEa48suYSGiAlC73+S0TX5VXo5/LCm8qiyGCYafDg4ZsueDIV3GQ5RXHaRGw=='    
    GO   
    -- Display the newly created credential   
    SELECT * from sys.credentials   
    -- Create a backup in Azure Storage.   
    BACKUP DATABASE TestDBRestoreFrom    
    TO URL = 'https://teststorageaccnt.blob.core.windows.net/testrestorefrom/TestDBRestoreFrom.bak'    
          WITH CREDENTIAL = 'BackupCredential'    
         ,COMPRESSION   
         ,STATS = 5;   
    GO    
    -- Create a Shared Access Signature credential   
    CREATE CREDENTIAL [https://teststorageaccnt.blob.core.windows.net/testrestorefrom]   
    WITH IDENTITY='SHARED ACCESS SIGNATURE',   
    SECRET = 'sv=2012-02-12&sr=c&si=policy_resfrom&sig=EhVpzLUXjG4ThAMLmVhrnoiCt8IfmD3BsuYiMawGzxc%3D'   
    GO   
    USE master;   
    GO   
    RESTORE DATABASE TestDBRestoreFrom    
    FROM URL = 'https://teststorageaccnt.blob.core.windows.net/testrestorefrom/TestDBRestoreFrom.bak'    
    WITH    
    CREDENTIAL = 'BackupCredential',    
    REPLACE,   
    MOVE 'TestDBRestoreFrom' TO 'C:\Backup\TestDBRestoreFrom.mdf',     
    MOVE 'TestDBRestoreFrom_log' TO 'C:\Backup\TestDBRestoreFrom_log.ldf';   
    GO  
  
    ```  
  
 <span data-ttu-id="0ce86-125">**Fine dell'esercitazione: SQL Server i file di dati nel servizio di archiviazione di Azure**</span><span class="sxs-lookup"><span data-stu-id="0ce86-125">**End of Tutorial: SQL Server Data Files in Azure Storage service**</span></span>  
  
  
