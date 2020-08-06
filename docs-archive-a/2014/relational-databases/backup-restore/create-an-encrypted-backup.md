---
title: Creare un backup crittografato | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
ms.assetid: e29061d3-c2ab-4d98-b9be-8e90a11d17fe
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d46cc686684d87fe393a5db7cfe01194ae917836
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723955"
---
# <a name="create-an-encrypted-backup"></a><span data-ttu-id="62e86-102">Creare un backup crittografato</span><span class="sxs-lookup"><span data-stu-id="62e86-102">Create an Encrypted Backup</span></span>
  <span data-ttu-id="62e86-103">In questo argomento vengono descritti i passaggi necessari per creare un backup crittografato tramite Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="62e86-103">This topic describes the steps necessary to create an encrypted backup using Transact-SQL.</span></span>  
  
## <a name="backup-to-disk-with-encryption"></a><span data-ttu-id="62e86-104">Backup su disco con crittografia</span><span class="sxs-lookup"><span data-stu-id="62e86-104">Backup to Disk with Encryption</span></span>  
 <span data-ttu-id="62e86-105">**Prerequisiti:**</span><span class="sxs-lookup"><span data-stu-id="62e86-105">**Prerequisites:**</span></span>  
  
-   <span data-ttu-id="62e86-106">Accesso a un disco locale o a uno spazio di archiviazione con una quantità di spazio adeguata per creare un backup del database.</span><span class="sxs-lookup"><span data-stu-id="62e86-106">Access to a local disk or to storage with adequate space to create a backup of the database.</span></span>  
  
-   <span data-ttu-id="62e86-107">Chiave master di un database master e certificato o chiave asimmetrica disponibile nell'istanza di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="62e86-107">A Database Master Key for the master database, and a certificate or asymmetric key available on the instance of SQL Server.</span></span> <span data-ttu-id="62e86-108">Per le autorizzazioni e i requisiti di crittografia, vedere [Crittografia dei backup](backup-encryption.md).</span><span class="sxs-lookup"><span data-stu-id="62e86-108">For encryption requirements and permissions, see [Backup Encryption](backup-encryption.md).</span></span>  
  
 <span data-ttu-id="62e86-109">Utilizzare i passaggi seguenti per creare un backup crittografato di un database in un disco locale.</span><span class="sxs-lookup"><span data-stu-id="62e86-109">Use the following steps to create an encrypted backup of a database to a local disk.</span></span> <span data-ttu-id="62e86-110">In questo esempio viene utilizzato un database utente denominato MyTestDB.</span><span class="sxs-lookup"><span data-stu-id="62e86-110">This example uses a user database called MyTestDB.</span></span>  
  
1.  <span data-ttu-id="62e86-111">**Creare una chiave master del database del database master:** Scegliere una password per la crittografia della copia della chiave master che verrà archiviata nel database.</span><span class="sxs-lookup"><span data-stu-id="62e86-111">**Create a Database Master Key of the master database:** Choose a password for encrypting the copy of the master key that will be stored in the database.</span></span> <span data-ttu-id="62e86-112">Connettersi al motore di database, avviare una nuova finestra Query e copiare e incollare l'esempio seguente, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="62e86-112">Connect to the database engine, start a new query windows and copy and paste the following example and click **Execute**.</span></span>  
  
    ```  
    -- Creates a database master key.   
    -- The key is encrypted using the password "<master key password>"  
    USE master;  
    GO  
    CREATE MASTER KEY ENCRYPTION BY PASSWORD = '<master key password>';  
    GO  
  
    ```  
  
2.  <span data-ttu-id="62e86-113">**Creare un certificato di backup:** creare un certificato di backup nel database master.</span><span class="sxs-lookup"><span data-stu-id="62e86-113">**Create a Backup Certificate:** Create a backup certificate in the master database.</span></span> <span data-ttu-id="62e86-114">Copiare e incollare l'esempio seguente nella finestra Query e quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="62e86-114">Copy and paste the following example into the query window and click **Execute**</span></span>  
  
    ```  
    Use Master  
    GO  
    CREATE CERTIFICATE MyTestDBBackupEncryptCert  
       WITH SUBJECT = 'MyTestDB Backup Encryption Certificate';  
    GO  
  
    ```  
  
3.  <span data-ttu-id="62e86-115">**Eseguire il backup del database:** specificare l'algoritmo di crittografia e il certificato da usare.</span><span class="sxs-lookup"><span data-stu-id="62e86-115">**Backup the database:** Specify the encryption algorithm and certificate to use.</span></span> <span data-ttu-id="62e86-116">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="62e86-116">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    BACKUP DATABASE [MyTestDB]  
    TO DISK = N'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Backup\MyTestDB.bak'  
    WITH  
      COMPRESSION,  
      ENCRYPTION   
       (  
       ALGORITHM = AES_256,  
       SERVER CERTIFICATE = MyTestDBBackupEncryptCert  
       ),  
      STATS = 10  
    GO  
  
    ```  
  
 <span data-ttu-id="62e86-117">Per un esempio di crittografia di un backup protetto da Extensible Key Management, vedere [Extensible Key Management tramite l'insieme di credenziali delle chiavi di Azure &#40;SQL Server&#41;](../security/encryption/extensible-key-management-using-azure-key-vault-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="62e86-117">For an example of encrypting a backup protected by an EKM, see [Extensible Key Management Using Azure Key Vault &#40;SQL Server&#41;](../security/encryption/extensible-key-management-using-azure-key-vault-sql-server.md).</span></span>  
  
### <a name="backup-to-azure-storage-with-encryption"></a><span data-ttu-id="62e86-118">Backup nel servizio Archiviazione di Azure con crittografia</span><span class="sxs-lookup"><span data-stu-id="62e86-118">Backup to Azure Storage with Encryption</span></span>  
 <span data-ttu-id="62e86-119">Se si crea un backup nell'archiviazione di Azure usando l'opzione **SQL Server Backup to URL** ( Backup di SQL Server nell'URL), i passaggi di crittografia sono gli stessi, ma è necessario usare un URL come destinazione e le credenziali di SQL per autenticare l'archiviazione di Azure.</span><span class="sxs-lookup"><span data-stu-id="62e86-119">If you are creating a backup to Azure storage using the **SQL Server Backup to URL** option, the encryption steps are the same, but you must use URL as the destination and a SQL Credential to authenticate to the Azure storage.</span></span> <span data-ttu-id="62e86-120">Se si vuole configurare [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] con le opzioni di crittografia, vedere [configurazione di SQL Server backup gestito in Azure](enable-sql-server-managed-backup-to-microsoft-azure.md) e [configurazione SQL Server backup gestito in Azure per i gruppi di disponibilità](../../database-engine/setting-up-sql-server-managed-backup-to-windows-azure-for-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="62e86-120">If you want to configure [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] with encryption options, see [Setting up SQL Server Managed Backup to Azure](enable-sql-server-managed-backup-to-microsoft-azure.md) and [Setting up SQL Server Managed Backup to Azure for Availability Groups](../../database-engine/setting-up-sql-server-managed-backup-to-windows-azure-for-availability-groups.md).</span></span>  
  
 <span data-ttu-id="62e86-121">**Prerequisiti:**</span><span class="sxs-lookup"><span data-stu-id="62e86-121">**Prerequisites:**</span></span>  
  
-   <span data-ttu-id="62e86-122">Account di archiviazione di Windows con contenitore.</span><span class="sxs-lookup"><span data-stu-id="62e86-122">A windows storage account and a container.</span></span> <span data-ttu-id="62e86-123">Per altre informazioni, vedere</span><span class="sxs-lookup"><span data-stu-id="62e86-123">For more information, see.</span></span> <span data-ttu-id="62e86-124">[Lezione 1: Creare oggetti di Archiviazione di Azure](../../tutorials/lesson-1-create-windows-azure-storage-objects.md).</span><span class="sxs-lookup"><span data-stu-id="62e86-124">[Lesson 1: Create Azure Storage Objects](../../tutorials/lesson-1-create-windows-azure-storage-objects.md).</span></span>  
  
-   <span data-ttu-id="62e86-125">Chiave master di un database master e certificato o chiave asimmetrica nell'istanza di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="62e86-125">A Database Master Key for the master database, and a certificate or asymmetric key  on the instance of SQL Server.</span></span> <span data-ttu-id="62e86-126">Per le autorizzazioni e i requisiti di crittografia, vedere [Crittografia dei backup](backup-encryption.md).</span><span class="sxs-lookup"><span data-stu-id="62e86-126">For encryption requirements and permissions, see [Backup Encryption](backup-encryption.md).</span></span>  
  
1.  <span data-ttu-id="62e86-127">**Creare credenziali di SQL Server:** per creare le credenziali di SQL Server, connettersi al motore di database, aprire una nuova finestra Query, copiare e incollare l'esempio seguente e quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="62e86-127">**Create SQL Server Credential:** To create a SQL Server credential, connect to the Database Engine, open a new query window, and copy and paste the following example and click **Execute**.</span></span>  
  
    ```  
    CREATE CREDENTIAL mycredential   
    WITH IDENTITY= 'mystorageaccount' - this is the name of the storage account you specified when creating a storage account    
    , SECRET = '<storage account access key>' - this should be either the Primary or Secondary Access Key for the storage account  
    ```  
  
2.  <span data-ttu-id="62e86-128">**Creare una chiave master del database:** Scegliere una password per la crittografia della copia della chiave master che verrà archiviata nel database.</span><span class="sxs-lookup"><span data-stu-id="62e86-128">**Create a Database Master Key:** Choose a password for encrypting the copy of the master key that will be stored in the database.</span></span> <span data-ttu-id="62e86-129">Connettersi al motore di database, avviare una nuova finestra Query e copiare e incollare l'esempio seguente, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="62e86-129">Connect to the database engine, start a new query windows and copy and paste the following example and click **Execute**.</span></span>  
  
    ```  
    -- Creates a database master key.  
    -- The key is encrypted using the password "<master key password>"  
    USE Master;  
    GO  
    CREATE MASTER KEY ENCRYPTION BY PASSWORD = '<master key password>';  
    GO  
  
    ```  
  
3.  <span data-ttu-id="62e86-130">**Creare un certificato di backup:** creare un certificato di backup nel database master.</span><span class="sxs-lookup"><span data-stu-id="62e86-130">**Create a Backup Certificate:** Create a Backup Certificate in the master database.</span></span> <span data-ttu-id="62e86-131">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**</span><span class="sxs-lookup"><span data-stu-id="62e86-131">Copy and paste the following example in the query window and click **Execute**</span></span>  
  
    ```  
    USE Master;  
    GO  
    CREATE CERTIFICATE MyTestDBBackupEncryptCert  
       WITH SUBJECT = 'MyTestDBBackupEncryptCert ';  
    GO  
  
    ```  
  
4.  <span data-ttu-id="62e86-132">**Eseguire il backup del database:** specificare l'algoritmo di crittografia e il certificato da usare.</span><span class="sxs-lookup"><span data-stu-id="62e86-132">**Backup the database:** Specify the encryption algorithm and the certificate to use.</span></span> <span data-ttu-id="62e86-133">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="62e86-133">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    BACKUP DATABASE [MyTestDB]  
    TO URL = N'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Backup\MyTestDB.bak'  
    WITH  
      CREDENTIAL 'mycredential' - this is the name of the credential created in the first step.  
      ,COMPRESSION  
      ,ENCRYPTION   
       (  
       ALGORITHM = AES_256,  
       SERVER CERTIFICATE = MyTestDBBackupEncryptCert  
       ),  
      STATS = 10  
    GO  
  
    ```  
  
  
