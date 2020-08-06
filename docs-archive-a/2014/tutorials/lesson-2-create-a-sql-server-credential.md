---
title: 'Lezione 2: creare una credenziale di SQL Server | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
ms.assetid: 64f8805c-1ddc-4c96-a47c-22917d12e1ab
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: e8b13c8d4d9e5937064cef5503ec64bfd6e4a2d4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726384"
---
# <a name="lesson-2-create-a-sql-server-credential"></a><span data-ttu-id="20c37-102">Lezione 2: Creare le credenziali di SQL Server</span><span class="sxs-lookup"><span data-stu-id="20c37-102">Lesson 2: Create a SQL Server Credential</span></span>
  <span data-ttu-id="20c37-103">**Credenziale:** una credenziale di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] è un oggetto usato per archiviare le informazioni di autenticazione necessarie per la connessione a una risorsa all'esterno di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="20c37-103">**Credential:** A [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] credential is an object that is used to store authentication information required to connect to a resource outside of SQL Server.</span></span>  <span data-ttu-id="20c37-104">Qui, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] i processi di backup e ripristino usano le credenziali per eseguire l'autenticazione nel servizio di archiviazione BLOB di Azure.</span><span class="sxs-lookup"><span data-stu-id="20c37-104">Here, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] backup and restore processes use credential to authenticate to the Azure Blob storage service.</span></span> <span data-ttu-id="20c37-105">Nelle credenziali vengono archiviati il nome dell'account di archiviazione e i relativi valori della **chiave di accesso** .</span><span class="sxs-lookup"><span data-stu-id="20c37-105">The Credential stores the name of the storage account and the storage account **access key** values.</span></span> <span data-ttu-id="20c37-106">Una volta create, le credenziali devono essere specificate nell'opzione WITH CREDENTIAL durante l'esecuzione delle istruzioni BACKUP/RESTORE.</span><span class="sxs-lookup"><span data-stu-id="20c37-106">Once the credential is created, it must be specified in the WITH CREDENTIAL option when issuing the BACKUP/RESTORE statements.</span></span> <span data-ttu-id="20c37-107">Per altre informazioni su come visualizzare, copiare o rigenerare le **access keys**dell'account di archiviazione, vedere la pagina relativa alle [chiavi di accesso dell'account di archiviazione](https://msdn.microsoft.com/library/windowsazure/hh531566.aspx).</span><span class="sxs-lookup"><span data-stu-id="20c37-107">For more information about how to view, copy or regenerate storage account **access keys**, see [Storage Account Access Keys](https://msdn.microsoft.com/library/windowsazure/hh531566.aspx).</span></span>  
  
 <span data-ttu-id="20c37-108">Per informazioni generali sulle credenziali, vedere [credenziali](../relational-databases/security/authentication-access/credentials-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="20c37-108">For general information about credentials, see [Credentials](../relational-databases/security/authentication-access/credentials-database-engine.md).</span></span>  
  
 <span data-ttu-id="20c37-109">Per informazioni su altri esempi in cui vengono usate le credenziali, vedere [creare un Proxy SQL Server Agent](../ssms/agent/create-a-sql-server-agent-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="20c37-109">For information, on other examples where credentials are used, see [Create a SQL Server Agent Proxy](../ssms/agent/create-a-sql-server-agent-proxy.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="20c37-110">I requisiti per la creazione di una credenziale SQL Server descritta di seguito sono specifici per i processi di backup SQL Server ([SQL Server backup su URL](../relational-databases/backup-restore/sql-server-backup-to-url.md)e [SQL Server backup gestito in Azure](../relational-databases/backup-restore/sql-server-managed-backup-to-microsoft-azure.md)).</span><span class="sxs-lookup"><span data-stu-id="20c37-110">The requirements for creating a SQL Server credential described below are specific to SQL Server backup processes ([SQL Server Backup to URL](../relational-databases/backup-restore/sql-server-backup-to-url.md), and [SQL Server Managed  Backup to Azure](../relational-databases/backup-restore/sql-server-managed-backup-to-microsoft-azure.md)).</span></span> <span data-ttu-id="20c37-111">Per accedere alla risorsa di archiviazione di Azure, SQL Server usa le informazioni sul nome dell'account di archiviazione e sulla chiave di accesso.</span><span class="sxs-lookup"><span data-stu-id="20c37-111">SQL Server, when accessing Azure storage to write or read backups uses the storage account name and access key information.</span></span>  <span data-ttu-id="20c37-112">Per altre informazioni sulla creazione delle credenziali per l'archiviazione dei file di database nella risorsa di archiviazione di Azure, vedere [Lesson 3: Create a SQL Server Credential](../relational-databases/lesson-2-create-a-sql-server-credential-using-a-shared-access-signature.md)</span><span class="sxs-lookup"><span data-stu-id="20c37-112">For more information on creating credentials for storing database files in Azure storage, see [Lesson 3: Create a SQL Server Credential](../relational-databases/lesson-2-create-a-sql-server-credential-using-a-shared-access-signature.md)</span></span>  
  
## <a name="create-a-sql-server-credential"></a><span data-ttu-id="20c37-113">Creare le credenziali di SQL Server</span><span class="sxs-lookup"><span data-stu-id="20c37-113">Create a SQL Server Credential</span></span>  
 <span data-ttu-id="20c37-114">Per creare le credenziali di SQL Server, attenersi ai passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="20c37-114">To create a SQL Server Credential, use the following steps:</span></span>  
  
1.  <span data-ttu-id="20c37-115">Connettersi a SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="20c37-115">Connect to SQL Server Management Studio.</span></span>  
  
2.  <span data-ttu-id="20c37-116">In Esplora oggetti connettersi all'istanza del motore di database con il database AdventureWorks2012 installato; in alternativa, utilizzare il proprio database da utilizzare per questa esercitazione.</span><span class="sxs-lookup"><span data-stu-id="20c37-116">In Object Explorer, connect to the instance of Database Engine that has AdventureWorks2012 database installed, or use your own database you plan to use for this tutorial.</span></span>  
  
3.  <span data-ttu-id="20c37-117">Sulla barra degli strumenti **Standard** fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="20c37-117">On the **Standard** tool bar, click **New Query**.</span></span>  
  
4.  <span data-ttu-id="20c37-118">Copiare e incollare l'esempio seguente nella finestra Query e modificare se necessario.</span><span class="sxs-lookup"><span data-stu-id="20c37-118">Copy and paste the following example into the query window, modify as needed.</span></span>  
  
    ```  
    CREATE CREDENTIAL mycredential   
    WITH IDENTITY= 'mystorageaccount' - this is the name of the storage account you specified when creating a storage account (See Lesson 1)   
    , SECRET = '<storage account access key>' - this should be either the Primary or Secondary Access Key for the storage account (See Lesson 1)  
  
    ```  
  
     <span data-ttu-id="20c37-119">![Mapping dell'account di archiviazione alle credenziali SQL](../../2014/tutorials/media/backuptocloud-storage-credential-mapping.gif "Mapping dell'account di archiviazione alle credenziali SQL")</span><span class="sxs-lookup"><span data-stu-id="20c37-119">![mapping storage account to sql credentials](../../2014/tutorials/media/backuptocloud-storage-credential-mapping.gif "mapping storage account to sql credentials")</span></span>  
  
5.  <span data-ttu-id="20c37-120">Verificare l'istruzione T-SQL e fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="20c37-120">Verify the T-SQL statement and click **Execute**.</span></span>  
  
 <span data-ttu-id="20c37-121">Per altre informazioni sul servizio di archiviazione BLOB di Azure per i concetti e i requisiti di backup, vedere [SQL Server backup e ripristino con il servizio di archiviazione BLOB di Azure](../relational-databases/backup-restore/sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md).</span><span class="sxs-lookup"><span data-stu-id="20c37-121">For more information about the Azure Blob storage service for backup concepts and requirements, see [SQL Server Backup and Restore with Azure Blob Storage Service](../relational-databases/backup-restore/sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md).</span></span>  
  
### <a name="next-lesson"></a><span data-ttu-id="20c37-122">Lezione successiva</span><span class="sxs-lookup"><span data-stu-id="20c37-122">Next Lesson</span></span>  
 <span data-ttu-id="20c37-123">[Lezione 3: scrivere un backup completo del database nel servizio di archiviazione BLOB di Azure](../../2014/tutorials/lesson-3-write-a-full-database-backup-to-the-windows-azure-blob-storage-service.md).</span><span class="sxs-lookup"><span data-stu-id="20c37-123">[Lesson 3: Write a Full Database Backup to the Azure Blob Storage Service](../../2014/tutorials/lesson-3-write-a-full-database-backup-to-the-windows-azure-blob-storage-service.md).</span></span>  
  
  
