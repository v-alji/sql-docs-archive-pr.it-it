---
title: 'Lezione 3: creare una credenziale di SQL Server | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 29e57ebd-828f-4dff-b473-c10ab0b1c597
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 808438e544e3beb18b2e2afa9c399b5666277483
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723843"
---
# <a name="lesson-3-create-a-sql-server-credential"></a><span data-ttu-id="8f8bd-102">Lezione 3: Creare le credenziali di SQL Server</span><span class="sxs-lookup"><span data-stu-id="8f8bd-102">Lesson 3: Create a SQL Server Credential</span></span>
  <span data-ttu-id="8f8bd-103">In questa lezione verrà creata una credenziale per archiviare le informazioni di sicurezza usate per accedere all'account di archiviazione di Azure.</span><span class="sxs-lookup"><span data-stu-id="8f8bd-103">In this lesson, you will create a credential to store security information used to access the Azure storage account.</span></span>  
  
 <span data-ttu-id="8f8bd-104">Una credenziale di SQL Server è un oggetto utilizzato per archiviare le informazioni di autenticazione necessarie per connettersi a una risorsa all'esterno di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8f8bd-104">A SQL Server credential is an object that is used to store authentication information required to connect to a resource outside of SQL Server.</span></span> <span data-ttu-id="8f8bd-105">Nelle credenziali vengono archiviati il percorso URI del contenitore di archiviazione e i valori della chiave della firma di accesso condivisa.</span><span class="sxs-lookup"><span data-stu-id="8f8bd-105">The credential stores the URI path of the storage container and the shared access signature key values.</span></span> <span data-ttu-id="8f8bd-106">Per ogni contenitore di archiviazione utilizzato da un file di dati o di log, è necessario creare una credenziale di SQL Server il cui nome corrisponda al percorso del contenitore.</span><span class="sxs-lookup"><span data-stu-id="8f8bd-106">For each storage container used by a data or log file, you must create a SQL Server Credential whose name matches the container path.</span></span>  
  
 <span data-ttu-id="8f8bd-107">Per informazioni generali sulle credenziali, vedere [credenziali &#40;motore di database&#41;](security/authentication-access/credentials-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="8f8bd-107">For general information about credentials, see [Credentials &#40;Database Engine&#41;](security/authentication-access/credentials-database-engine.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="8f8bd-108">I requisiti per la creazione di una credenziale SQL Server descritta di seguito sono specifici della funzionalità relativa ai [file di dati SQL Server in Azure](databases/sql-server-data-files-in-microsoft-azure.md) .</span><span class="sxs-lookup"><span data-stu-id="8f8bd-108">The requirements for creating a SQL Server credential described below are specific to the [SQL Server Data Files in Azure](databases/sql-server-data-files-in-microsoft-azure.md) feature.</span></span> <span data-ttu-id="8f8bd-109">Per informazioni sulla creazione di credenziali per i processi di backup in archiviazione di Azure, vedere [lezione 2: creare una SQL Server Credential](../tutorials/lesson-2-create-a-sql-server-credential.md).</span><span class="sxs-lookup"><span data-stu-id="8f8bd-109">For information on creating credentials for backup processes in Azure storage, see [Lesson 2: Create a SQL Server Credential](../tutorials/lesson-2-create-a-sql-server-credential.md).</span></span>  
  
 <span data-ttu-id="8f8bd-110">Per creare le credenziali di SQL Server, effettuare i passaggi riportati di seguito:</span><span class="sxs-lookup"><span data-stu-id="8f8bd-110">To create a SQL Server Credential, follow these steps:</span></span>  
  
1.  <span data-ttu-id="8f8bd-111">Connettersi a SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="8f8bd-111">Connect to SQL Server Management Studio.</span></span>  
  
2.  <span data-ttu-id="8f8bd-112">In Esplora oggetti connettersi all'istanza del motore di database installato.</span><span class="sxs-lookup"><span data-stu-id="8f8bd-112">In Object Explorer, connect to the instance of Database Engine installed.</span></span>  
  
3.  <span data-ttu-id="8f8bd-113">Sulla barra degli strumenti Standard fare clic su Nuova query.</span><span class="sxs-lookup"><span data-stu-id="8f8bd-113">On the Standard tool bar, click New Query.</span></span>  
  
4.  <span data-ttu-id="8f8bd-114">Copiare e incollare l'esempio seguente nella finestra Query e modificare se necessario.</span><span class="sxs-lookup"><span data-stu-id="8f8bd-114">Copy and paste the following example into the query window, modify as needed.</span></span> <span data-ttu-id="8f8bd-115">L'istruzione seguente consente di creare un SQL Server credenziali per archiviare il certificato di accesso condiviso del contenitore di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="8f8bd-115">The following statement will create a SQL Server Credential to store your storage container's Shared Access Certificate.</span></span>  
  
    ```sql  
  
    USE master  
    CREATE CREDENTIAL credentialname - this name should match the container path and it must start with https.   
       WITH IDENTITY='SHARED ACCESS SIGNATURE', -- this is a mandatory string and do not change it.   
       SECRET = 'sharedaccesssignature' -- this is the shared access signature key that you obtained in Lesson 2.   
    GO  
  
    ```  
  
     <span data-ttu-id="8f8bd-116">Per informazioni dettagliate, vedere [CREATE CREDENTIAL &#40;&#41;Transact-SQL](/sql/t-sql/statements/create-credential-transact-sql) in documentazione online di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8f8bd-116">For detailed information, see [CREATE CREDENTIAL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-credential-transact-sql) in SQL Server Books Online.</span></span>  
  
5.  <span data-ttu-id="8f8bd-117">Per visualizzare tutte le credenziali disponibili, è possibile eseguire l'istruzione seguente nella finestra della query:</span><span class="sxs-lookup"><span data-stu-id="8f8bd-117">To see all available credentials, you can run the following statement in the query window:</span></span>  
  
    ```sql  
    SELECT * from sys.credentials  
    ```  
  
     <span data-ttu-id="8f8bd-118">Per ulteriori informazioni su sys. Credentials, vedere [sys. credentials &#40;&#41;Transact-SQL](/sql/relational-databases/system-catalog-views/sys-credentials-transact-sql) in documentazione online di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8f8bd-118">For more information on sys.credentials, see [sys.credentials &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-credentials-transact-sql) in SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="8f8bd-119">**Lezione successiva:**</span><span class="sxs-lookup"><span data-stu-id="8f8bd-119">**Next Lesson:**</span></span>  
  
 [<span data-ttu-id="8f8bd-120">Lezione 4: Creare un database in Archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="8f8bd-120">Lesson 4: Create a database in Azure Storage</span></span>](lesson-3-database-backup-to-url.md)  
  
  
