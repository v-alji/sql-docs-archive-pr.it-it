---
title: Ripristinare un database fino al punto di errore nel modello di recupero con versione completa (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- point of failure [SQL Server]
- restoring databases [SQL Server], point of failure
- database restores [SQL Server], point of failure
ms.assetid: 04106e18-bbf7-4a5e-a2e1-3d65319814d5
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 95b73660ebb44f4daffe6eaefd873699cfbbd8ca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627830"
---
# <a name="restore-a-database-to-the-point-of-failure-under-the-full-recovery-model-transact-sql"></a><span data-ttu-id="911e5-102">Ripristinare un database al punto di errore nel modello di recupero con registrazione completa (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="911e5-102">Restore a Database to the Point of Failure Under the Full Recovery Model (Transact-SQL)</span></span>
  <span data-ttu-id="911e5-103">In questo argomento vengono fornite informazioni su come eseguire il ripristino fino al punto di errore.</span><span class="sxs-lookup"><span data-stu-id="911e5-103">This topic explains how to restore to the point of failure.</span></span> <span data-ttu-id="911e5-104">L'argomento è rilevante solo per i database che utilizzano i modelli di recupero con registrazione completa o con registrazione minima delle operazioni bulk.</span><span class="sxs-lookup"><span data-stu-id="911e5-104">The topic is relevant only for databases that are using the full or bulk-logged recovery models.</span></span>  
  
### <a name="to-restore-to-the-point-of-failure"></a><span data-ttu-id="911e5-105">Per eseguire il ripristino fino al punto di errore</span><span class="sxs-lookup"><span data-stu-id="911e5-105">To restore to the point of failure</span></span>  
  
1.  <span data-ttu-id="911e5-106">Eseguire il backup della parte finale del log eseguendo l'istruzione [BACKUP](/sql/t-sql/statements/backup-transact-sql) di base seguente:</span><span class="sxs-lookup"><span data-stu-id="911e5-106">Back up the tail of the log by running the following basic [BACKUP](/sql/t-sql/statements/backup-transact-sql) statement:</span></span>  
  
    ```  
    BACKUP LOG <database_name> TO <backup_device>   
       WITH NORECOVERY, NO_TRUNCATE;  
    ```  
  
2.  <span data-ttu-id="911e5-107">Eseguire il ripristino di un backup completo del database eseguendo l'istruzione [RESTORE DATABASE](/sql/t-sql/statements/restore-statements-transact-sql) di base seguente:</span><span class="sxs-lookup"><span data-stu-id="911e5-107">Restore a full database backup by running the following basic [RESTORE DATABASE](/sql/t-sql/statements/restore-statements-transact-sql) statement:</span></span>  
  
    ```  
    RESTORE DATABASE <database_name> FROM <backup_device>   
       WITH NORECOVERY;  
    ```  
  
3.  <span data-ttu-id="911e5-108">Facoltativamente, ripristinare un backup differenziale del database eseguendo l'istruzione RESTORE DATABASE di base seguente:</span><span class="sxs-lookup"><span data-stu-id="911e5-108">Optionally, restore a differential database backup by running the following basic RESTORE DATABASE statement:</span></span>  
  
    ```  
    RESTORE DATABASE <database_name> FROM <backup_device>   
       WITH NORECOVERY;  
    ```  
  
4.  <span data-ttu-id="911e5-109">Applicare tutti i log delle transazioni, incluso il backup della parte finale del log creato nel passaggio 1, specificando WITH NORECOVERY nell'istruzione RESTORE LOG:</span><span class="sxs-lookup"><span data-stu-id="911e5-109">Apply each transaction log, including the tail-log backup you created in step 1, by specifying WITH NORECOVERY in the RESTORE LOG statement:</span></span>  
  
    ```  
    RESTORE LOG <database_name> FROM <backup_device>   
       WITH NORECOVERY;  
    ```  
  
5.  <span data-ttu-id="911e5-110">Recuperare il database eseguendo l'istruzione RESTORE DATABASE seguente:</span><span class="sxs-lookup"><span data-stu-id="911e5-110">Recover the database by running the following RESTORE DATABASE statement:</span></span>  
  
    ```  
    RESTORE DATABASE <database_name>   
       WITH RECOVERY;  
    ```  
  
## <a name="example"></a><span data-ttu-id="911e5-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="911e5-111">Example</span></span>  
 <span data-ttu-id="911e5-112">Prima che sia possibile eseguire l'esempio, è necessario completare le operazioni preliminari seguenti:</span><span class="sxs-lookup"><span data-stu-id="911e5-112">Before you can run the example, you must complete the following preparations:</span></span>  
  
1.  <span data-ttu-id="911e5-113">Il modello di recupero predefinito del database [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] è il modello di recupero con registrazione minima.</span><span class="sxs-lookup"><span data-stu-id="911e5-113">The default recovery model of the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database is the simple recovery model.</span></span> <span data-ttu-id="911e5-114">Dato che questo modello di recupero non supporta il ripristino in corrispondenza del punto in cui si è verificato un errore, impostare [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] per usare il modello di recupero con registrazione completa eseguendo l'istruzione [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql) seguente:</span><span class="sxs-lookup"><span data-stu-id="911e5-114">Because this recovery model does not support restoring to the point of a failure, set [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] to use the full recovery model by running the following [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql) statement:</span></span>  
  
    ```  
    USE master;  
    GO  
    ALTER DATABASE AdventureWorks2012 SET RECOVERY FULL;  
    ```  
  
2.  <span data-ttu-id="911e5-115">Creare un backup completo del database utilizzando l'istruzione BACKUP seguente:</span><span class="sxs-lookup"><span data-stu-id="911e5-115">Create a full database back of the database by using the following BACKUP statement:</span></span>  
  
    ```  
    BACKUP DATABASE AdventureWorks2012 TO DISK = 'C:\AdventureWorks2012_Data.bck';  
    ```  
  
3.  <span data-ttu-id="911e5-116">Creare un backup del log di routine:</span><span class="sxs-lookup"><span data-stu-id="911e5-116">Create a routine log backup:</span></span>  
  
    ```  
    BACKUP LOG AdventureWorks2012 TO DISK = 'C:\AdventureWorks2012_Log.bck';  
    ```  
  
 <span data-ttu-id="911e5-117">Nell'esempio seguente vengono ripristinati i backup creati in precedenza, dopo la creazione di un backup della parte finale del log del database [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="911e5-117">The following example restores the backups that are created previously, after creating a tail-log backup of the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span> <span data-ttu-id="911e5-118">In questo passaggio si suppone che il disco del log sia accessibile.</span><span class="sxs-lookup"><span data-stu-id="911e5-118">(This step assumes that the log disk can be accessed.)</span></span>  
  
 <span data-ttu-id="911e5-119">Innanzitutto, nell'esempio viene creato un backup della parte finale del log del database che acquisisce il log attivo e lascia il database nello stato di ripristino.</span><span class="sxs-lookup"><span data-stu-id="911e5-119">First, the example creates a tail-log backup of the database that captures the active log and leaves the database in the Restoring state.</span></span> <span data-ttu-id="911e5-120">Quindi, nell'esempio viene ripristinato il backup del database e vengono applicati il backup del log di routine creato in precedenza e il backup della parte finale del log.</span><span class="sxs-lookup"><span data-stu-id="911e5-120">Then, the example restores the database backup, applies the routine log backup created previously, and applies the tail-log backup.</span></span> <span data-ttu-id="911e5-121">Infine viene recuperato il database in un passaggio separato.</span><span class="sxs-lookup"><span data-stu-id="911e5-121">Finally, the example recovers the database in a separate step.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="911e5-122">Il comportamento predefinito consiste nel recuperare un database come parte dell'istruzione che ripristina il backup finale.</span><span class="sxs-lookup"><span data-stu-id="911e5-122">The default behavior is to recover a database as part of the statement that restores the final backup.</span></span>  
  
```  
/* Example of restoring a to the point of failure */  
-- Step 1: Create a tail-log backup by using WITH NORECOVERY.  
BACKUP LOG AdventureWorks2012  
   TO DISK = 'C:\AdventureWorks2012_Log.bck'  
   WITH NORECOVERY;  
GO  
-- Step 2: Restore the full database backup.  
RESTORE DATABASE AdventureWorks2012  
   FROM DISK = 'C:\AdventureWorks2012_Data.bck'  
   WITH NORECOVERY;  
GO  
-- Step 3: Restore the first transaction log backup.  
RESTORE LOG AdventureWorks2012  
   FROM DISK = 'C:\AdventureWorks2012_Log.bck'  
   WITH NORECOVERY;  
GO  
-- Step 4: Restore the tail-log backup.  
RESTORE LOG AdventureWorks2012  
   FROM  DISK = 'C:\AdventureWorks2012_Log.bck'  
   WITH NORECOVERY;  
GO  
-- Step 5: Recover the database.  
RESTORE DATABASE AdventureWorks2012  
   WITH RECOVERY;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="911e5-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="911e5-123">See Also</span></span>  
 <span data-ttu-id="911e5-124">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="911e5-124">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 [<span data-ttu-id="911e5-125">RESTORE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="911e5-125">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  
  
