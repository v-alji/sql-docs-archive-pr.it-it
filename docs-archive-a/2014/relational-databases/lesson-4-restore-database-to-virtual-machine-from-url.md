---
title: Lezione 5. Opzionale Crittografare il database tramite Transparent Data Encryption | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: ba793c8f-665a-4c46-b68d-f558a37906b2
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 613b66c04a69364f3c9be1059f95021dd3eff595
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629822"
---
# <a name="lesson-5-optional-encrypt-your-database-using-tde"></a><span data-ttu-id="1f1d9-103">Lezione 5.</span><span class="sxs-lookup"><span data-stu-id="1f1d9-103">Lesson 5.</span></span> <span data-ttu-id="1f1d9-104">(facoltativo) crittografare il database tramite TDE</span><span class="sxs-lookup"><span data-stu-id="1f1d9-104">(Optional) Encrypt your database using TDE</span></span>
  <span data-ttu-id="1f1d9-105">Come passaggio facoltativo, è possibile crittografare il database appena creato.</span><span class="sxs-lookup"><span data-stu-id="1f1d9-105">As an optional step, you can encrypt the newly created database.</span></span> <span data-ttu-id="1f1d9-106">Transparent Data Encryption (TDE) esegue la crittografia e la decrittografia I/O in tempo reale dei file di dati e di log.</span><span class="sxs-lookup"><span data-stu-id="1f1d9-106">Transparent data encryption (TDE) performs real-time I/O encryption and decryption of the data and log files.</span></span> <span data-ttu-id="1f1d9-107">Per questo tipo di crittografia viene utilizzata una chiave di crittografia del database (DEK), archiviata nel record di avvio del database affinché sia disponibile durante le operazioni di recupero.</span><span class="sxs-lookup"><span data-stu-id="1f1d9-107">This kind of encryption uses a database encryption key (DEK), which is stored in the database boot record for availability during recovery.</span></span> <span data-ttu-id="1f1d9-108">Per ulteriori informazioni, vedere [Transparent Data Encryption &#40;&#41;](security/encryption/transparent-data-encryption.md) Transparent Data Encryption e [spostare un database protetto con crittografia transparent in un altro SQL Server](security/encryption/move-a-tde-protected-database-to-another-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="1f1d9-108">For more information, see [Transparent Data Encryption &#40;TDE&#41;](security/encryption/transparent-data-encryption.md) and [Move a TDE Protected Database to Another SQL Server](security/encryption/move-a-tde-protected-database-to-another-sql-server.md).</span></span>  
  
 <span data-ttu-id="1f1d9-109">Per questa lezione si presuppone che l'utente abbia già completato i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="1f1d9-109">This lesson assumes you already completed the following steps:</span></span>  
  
-   <span data-ttu-id="1f1d9-110">Si ha un account di archiviazione di Azure.</span><span class="sxs-lookup"><span data-stu-id="1f1d9-110">You have an Azure Storage account.</span></span>  
  
-   <span data-ttu-id="1f1d9-111">È stato creato un contenitore nell'account di archiviazione di Azure.</span><span class="sxs-lookup"><span data-stu-id="1f1d9-111">You have created a container under your Azure Storage account.</span></span>  
  
-   <span data-ttu-id="1f1d9-112">Creazione dei criteri in un contenitore con diritti di lettura, scrittura ed elenco.</span><span class="sxs-lookup"><span data-stu-id="1f1d9-112">You have created a policy on a container with read, write, and list rights.</span></span> <span data-ttu-id="1f1d9-113">Generazione di una chiave SAS.</span><span class="sxs-lookup"><span data-stu-id="1f1d9-113">You also generated a SAS key.</span></span>  
  
-   <span data-ttu-id="1f1d9-114">Creazione di una credenziale di SQL Server nel computer di origine.</span><span class="sxs-lookup"><span data-stu-id="1f1d9-114">You have created a SQL Server credential on the source machine.</span></span>  
  
-   <span data-ttu-id="1f1d9-115">È stato creato un database seguendo i passaggi descritti nella lezione 4.</span><span class="sxs-lookup"><span data-stu-id="1f1d9-115">You have created a database by following the steps that are described in Lesson 4.</span></span>  
  
 <span data-ttu-id="1f1d9-116">Se si desidera crittografare un database, effettuare i passaggi riportati di seguito:</span><span class="sxs-lookup"><span data-stu-id="1f1d9-116">If you want to encrypt a database, follow these steps:</span></span>  
  
1.  <span data-ttu-id="1f1d9-117">Nel computer di origine modificare ed eseguire le istruzioni seguenti in una finestra di query:</span><span class="sxs-lookup"><span data-stu-id="1f1d9-117">In the source machine, modify and run the following statements in a query window:</span></span>  
  
    ```  
  
    -- Create a master key and a server certificate   
    USE master   
    GO   
    CREATE MASTER KEY ENCRYPTION BY PASSWORD = 'MySQLKey01';   
    GO   
    CREATE CERTIFICATE MySQLCert WITH SUBJECT = 'SQL - Azure Storage Certification'   
    GO   
    -- Create a backup of the server certificate in the master database.   
    -- Store TDS certificates in the source machine locally.   
    BACKUP CERTIFICATE MySQLCert   
    TO FILE = 'C:\certs\MySQLCert.CER'   
    WITH PRIVATE KEY   
    (   
    FILE = 'C:\certs\MySQLPrivateKeyFile.PVK',   
    ENCRYPTION BY PASSWORD = 'MySQLKey01'   
    );  
  
    ```  
  
2.  <span data-ttu-id="1f1d9-118">Quindi, crittografare il nuovo database nel computer di origine eseguendo la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="1f1d9-118">Then, encrypt your new database in the source machine by following these steps:</span></span>  
  
    ```  
  
    -- Switch to the new database.   
    -- Create a database encryption key, that is protected by the server certificate in the master database.    
    -- Alter the new database to encrypt the database using TDE.   
    USE TestDB1;   
    GO   
    -- Encrypt your database   
    CREATE DATABASE ENCRYPTION KEY   
    WITH ALGORITHM = AES_256   
    ENCRYPTION BY SERVER CERTIFICATE MySQLCert   
    GO   
  
    ALTER DATABASE TestDB1   
    SET ENCRYPTION ON   
    GO  
  
    ```  
  
 <span data-ttu-id="1f1d9-119">Se si desiderano informazioni sullo stato della crittografia di un database e le relative chiavi di crittografia del database associate, eseguire l'istruzione seguente:</span><span class="sxs-lookup"><span data-stu-id="1f1d9-119">If you want to learn the encryption state of a database and its associated database encryption keys, run the following statement:</span></span>  
  
```  
  
SELECT * FROM sys.dm_database_encryption_keys;   
GO  
  
```  
  
 <span data-ttu-id="1f1d9-120">Per informazioni dettagliate sulle istruzioni Transact-SQL utilizzate in questa lezione, vedere [create database &#40;SQL Server Transact-sql&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql), [ALTER database &#40;transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql), [CREATE MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-master-key-transact-sql), [Create Certificate &#40;transact-SQL ](/sql/t-sql/statements/create-certificate-transact-sql)&#41;e [sys. dm_database_encryption_keys &#40;Transact-SQL ](/sql/relational-databases/system-dynamic-management-views/sys-dm-database-encryption-keys-transact-sql)&#41;.</span><span class="sxs-lookup"><span data-stu-id="1f1d9-120">For detailed information the Transact-SQL statements that have been used in this lesson, see [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql), [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql), [CREATE MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-master-key-transact-sql), [CREATE CERTIFICATE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-certificate-transact-sql), and [sys.dm_database_encryption_keys &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-database-encryption-keys-transact-sql).</span></span>  
  
 <span data-ttu-id="1f1d9-121">**Lezione successiva:**</span><span class="sxs-lookup"><span data-stu-id="1f1d9-121">**Next Lesson:**</span></span>  
  
 [<span data-ttu-id="1f1d9-122">Lezione 6: Eseguire la migrazione di un database da un computer di origine locale a un computer di destinazione in Azure</span><span class="sxs-lookup"><span data-stu-id="1f1d9-122">Lesson 6: Migrate a database from a source machine on-premises to a destination machine in Azure</span></span>](lesson-5-backup-database-using-file-snapshot-backup.md)  
  
  
