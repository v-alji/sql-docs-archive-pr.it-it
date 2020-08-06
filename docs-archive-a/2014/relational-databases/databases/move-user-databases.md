---
title: Spostare database utente | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- disaster recovery [SQL Server], moving database files
- database files [SQL Server], moving
- data files [SQL Server], moving
- editions [SQL Server], moving databases between
- moving full-text catalogs
- scheduled disk maintenace [SQL Server]
- moving databases
- full-text catalogs [SQL Server], moving
- moving database files
- moving user databases
- relocating database files
- planned database relocations [SQL Server]
- databases [SQL Server], moving
ms.assetid: ad9a4e92-13fb-457d-996a-66ffc2d55b79
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6c2b82c3bec13c82aa30aebd175ef78f8136ee04
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627805"
---
# <a name="move-user-databases"></a><span data-ttu-id="e11c7-102">Spostare database utente</span><span class="sxs-lookup"><span data-stu-id="e11c7-102">Move User Databases</span></span>
  <span data-ttu-id="e11c7-103">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]è possibile spostare i file di dati, di log e del catalogo full-text di un database utente specificando il nuovo percorso file nella clausola FILENAME dell'istruzione [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="e11c7-103">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you can move the data, log, and full-text catalog files of a user database to a new location by specifying the new file location in the FILENAME clause of the [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql) statement.</span></span> <span data-ttu-id="e11c7-104">Questo metodo è valido per lo spostamento dei file del database all'interno della stessa istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e11c7-104">This method applies to moving database files within the same instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="e11c7-105">Per spostare un database in un'altra istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o in un altro server, usare le operazioni di [backup e ripristino](../backup-restore/back-up-and-restore-of-sql-server-databases.md) o di [collegamento e scollegamento](move-a-database-using-detach-and-attach-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="e11c7-105">To move a database to another instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or to another server, use [backup and restore](../backup-restore/back-up-and-restore-of-sql-server-databases.md) or [detach and attach operations](move-a-database-using-detach-and-attach-transact-sql.md).</span></span>  
  
## <a name="considerations"></a><span data-ttu-id="e11c7-106">Considerazioni</span><span class="sxs-lookup"><span data-stu-id="e11c7-106">Considerations</span></span>  
 <span data-ttu-id="e11c7-107">Quando si sposta un database in un'altra istanza del server, per garantire un sistema consistente a utenti e applicazioni, potrebbe essere necessario ricreare tutti i metadati del database o parte di essi.</span><span class="sxs-lookup"><span data-stu-id="e11c7-107">When you move a database onto another server instance, to provide a consistent experience to users and applications, you might have to re-create some or all the metadata for the database.</span></span> <span data-ttu-id="e11c7-108">Per altre informazioni, vedere [Gestione dei metadati quando si rende disponibile un database in un'altra istanza del server &#40;SQL Server&#41;](manage-metadata-when-making-a-database-available-on-another-server.md).</span><span class="sxs-lookup"><span data-stu-id="e11c7-108">For more information, see [Manage Metadata When Making a Database Available on Another Server Instance &#40;SQL Server&#41;](manage-metadata-when-making-a-database-available-on-another-server.md).</span></span>  
  
 <span data-ttu-id="e11c7-109">Alcune funzionalità del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] comportano una modifica della modalità di archiviazione delle informazioni nei file di database da parte del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e11c7-109">Some features of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] change the way that the [!INCLUDE[ssDE](../../includes/ssde-md.md)] stores information in the database files.</span></span> <span data-ttu-id="e11c7-110">Queste funzionalità sono disponibili solo in edizioni specifiche di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e11c7-110">These features are restricted to specific editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="e11c7-111">Un database che contiene queste funzionalità non può essere spostato a un'edizione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] che non le supporta.</span><span class="sxs-lookup"><span data-stu-id="e11c7-111">A database that contains these features cannot be moved to an edition of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that does not support them.</span></span> <span data-ttu-id="e11c7-112">Utilizzare la vista a gestione dinamica sys.dm_db_persisted_sku_features per ottenere un elenco di tutte le caratteristiche specifiche dell'edizione abilitate nel database corrente.</span><span class="sxs-lookup"><span data-stu-id="e11c7-112">Use the sys.dm_db_persisted_sku_features dynamic management view to list all edition-specific features that are enabled in the current database.</span></span>  
  
 <span data-ttu-id="e11c7-113">Le procedure descritte in questo argomento richiedono il nome logico dei file di database.</span><span class="sxs-lookup"><span data-stu-id="e11c7-113">The procedures in this topic require the logical name of the database files.</span></span> <span data-ttu-id="e11c7-114">Per ottenere il nome, eseguire una query sulla colonna name della vista del catalogo [sys.master_files](/sql/relational-databases/system-catalog-views/sys-master-files-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="e11c7-114">To obtain the name, query the name column in the [sys.master_files](/sql/relational-databases/system-catalog-views/sys-master-files-transact-sql) catalog view.</span></span>  
  
 <span data-ttu-id="e11c7-115">A partire da [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], i cataloghi full-text sono integrati nel database anziché essere archiviati nel file system.</span><span class="sxs-lookup"><span data-stu-id="e11c7-115">Starting with [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], full-text catalogs are integrated into the database rather than being stored in the file system.</span></span> <span data-ttu-id="e11c7-116">I cataloghi full-text vengono ora spostati automaticamente quando si sposta un database.</span><span class="sxs-lookup"><span data-stu-id="e11c7-116">The full-text catalogs now move automatically when you move a database.</span></span>  
  
## <a name="planned-relocation-procedure"></a><span data-ttu-id="e11c7-117">Procedura di rilocazione pianificata</span><span class="sxs-lookup"><span data-stu-id="e11c7-117">Planned Relocation Procedure</span></span>  
 <span data-ttu-id="e11c7-118">Per spostare un file di dati o di log nell'ambito di una rilocazione pianificata, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="e11c7-118">To move a data or log file as part of a planned relocation, follow these steps:</span></span>  
  
1.  <span data-ttu-id="e11c7-119">Eseguire l'istruzione seguente.</span><span class="sxs-lookup"><span data-stu-id="e11c7-119">Run the following statement.</span></span>  
  
    ```  
    ALTER DATABASE database_name SET OFFLINE;  
    ```  
  
2.  <span data-ttu-id="e11c7-120">Spostare il file o i file nella nuova posizione.</span><span class="sxs-lookup"><span data-stu-id="e11c7-120">Move the file or files to the new location.</span></span>  
  
3.  <span data-ttu-id="e11c7-121">Per ogni file che si desidera spostare, eseguire l'istruzione seguente.</span><span class="sxs-lookup"><span data-stu-id="e11c7-121">For each file moved, run the following statement.</span></span>  
  
    ```  
    ALTER DATABASE database_name MODIFY FILE ( NAME = logical_name, FILENAME = 'new_path\os_file_name' );  
    ```  
  
4.  <span data-ttu-id="e11c7-122">Eseguire l'istruzione seguente.</span><span class="sxs-lookup"><span data-stu-id="e11c7-122">Run the following statement.</span></span>  
  
    ```  
    ALTER DATABASE database_name SET ONLINE;  
    ```  
  
5.  <span data-ttu-id="e11c7-123">Verificare la modifica ai file eseguendo la query riportata di seguito.</span><span class="sxs-lookup"><span data-stu-id="e11c7-123">Verify the file change by running the following query.</span></span>  
  
    ```  
    SELECT name, physical_name AS CurrentLocation, state_desc  
    FROM sys.master_files  
    WHERE database_id = DB_ID(N'<database_name>');  
    ```  
  
## <a name="relocation-for-scheduled-disk-maintenance"></a><span data-ttu-id="e11c7-124">Rilocazione per una manutenzione pianificata del disco</span><span class="sxs-lookup"><span data-stu-id="e11c7-124">Relocation for Scheduled Disk Maintenance</span></span>  
 <span data-ttu-id="e11c7-125">Per rilocare un file nell'ambito di un processo di manutenzione pianificata del disco, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="e11c7-125">To relocate a file as part of a scheduled disk maintenance process, follow these steps:</span></span>  
  
1.  <span data-ttu-id="e11c7-126">Per ogni file che si desidera spostare, eseguire l'istruzione seguente.</span><span class="sxs-lookup"><span data-stu-id="e11c7-126">For each file to be moved, run the following statement.</span></span>  
  
    ```  
    ALTER DATABASE database_name MODIFY FILE ( NAME = logical_name , FILENAME = 'new_path\os_file_name' );  
    ```  
  
2.  <span data-ttu-id="e11c7-127">Arrestare l'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o arrestare il sistema per eseguire la manutenzione.</span><span class="sxs-lookup"><span data-stu-id="e11c7-127">Stop the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or shut down the system to perform maintenance.</span></span> <span data-ttu-id="e11c7-128">Per altre informazioni, vedere [Avviare, arrestare, sospendere, riprendere, riavviare i servizi SQL Server](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md).</span><span class="sxs-lookup"><span data-stu-id="e11c7-128">For more information, see [Start, Stop, Pause, Resume, Restart the Database Engine, SQL Server Agent, or SQL Server Browser Service](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md).</span></span>  
  
3.  <span data-ttu-id="e11c7-129">Spostare il file o i file nella nuova posizione.</span><span class="sxs-lookup"><span data-stu-id="e11c7-129">Move the file or files to the new location.</span></span>  
  
4.  <span data-ttu-id="e11c7-130">Riavviare l'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o il server.</span><span class="sxs-lookup"><span data-stu-id="e11c7-130">Restart the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or the server.</span></span> <span data-ttu-id="e11c7-131">Per altre informazioni, vedere [Avviare, arrestare, sospendere, riprendere, riavviare il motore di database, SQL Server Agent o SQL Server Browser](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md).</span><span class="sxs-lookup"><span data-stu-id="e11c7-131">For more information, see [Start, Stop, Pause, Resume, Restart the Database Engine, SQL Server Agent, or SQL Server Browser Service](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md)</span></span>  
  
5.  <span data-ttu-id="e11c7-132">Verificare la modifica ai file eseguendo la query riportata di seguito.</span><span class="sxs-lookup"><span data-stu-id="e11c7-132">Verify the file change by running the following query.</span></span>  
  
    ```  
    SELECT name, physical_name AS CurrentLocation, state_desc  
    FROM sys.master_files  
    WHERE database_id = DB_ID(N'<database_name>');  
    ```  
  
## <a name="failure-recovery-procedure"></a><span data-ttu-id="e11c7-133">Procedura di recupero da errore</span><span class="sxs-lookup"><span data-stu-id="e11c7-133">Failure Recovery Procedure</span></span>  
 <span data-ttu-id="e11c7-134">Se è necessario spostare un file a causa di un errore hardware, eseguire la procedura seguente per rilocare il file in una nuova posizione.</span><span class="sxs-lookup"><span data-stu-id="e11c7-134">If a file must be moved because of a hardware failure, use the following steps to relocate the file to a new location.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="e11c7-135">Se non è possibile avviare il database, ovvero se il database è in modalità sospetta o in stato non recuperato, il file può essere spostato solo dai membri del ruolo predefinito sysadmin.</span><span class="sxs-lookup"><span data-stu-id="e11c7-135">If the database cannot be started, that is it is in suspect mode or in an unrecovered state, only members of the sysadmin fixed role can move the file.</span></span>  
  
1.  <span data-ttu-id="e11c7-136">Arrestare l'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , se avviata.</span><span class="sxs-lookup"><span data-stu-id="e11c7-136">Stop the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] if it is started.</span></span>  
  
2.  <span data-ttu-id="e11c7-137">Avviare l'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in modalità di recupero del solo database master digitando uno dei comandi seguenti al prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="e11c7-137">Start the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in master-only recovery mode by entering one of the following commands at the command prompt.</span></span>  
  
    -   <span data-ttu-id="e11c7-138">Per l'istanza predefinita (MSSQLSERVER), eseguire il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="e11c7-138">For the default (MSSQLSERVER) instance, run the following command.</span></span>  
  
        ```  
        NET START MSSQLSERVER /f /T3608  
        ```  
  
    -   <span data-ttu-id="e11c7-139">Per un'istanza denominata, eseguire il comando riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="e11c7-139">For a named instance, run the following command.</span></span>  
  
        ```  
        NET START MSSQL$instancename /f /T3608  
        ```  
  
     <span data-ttu-id="e11c7-140">Per altre informazioni, vedere [Avviare, arrestare, sospendere, riprendere, riavviare i servizi SQL Server](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md).</span><span class="sxs-lookup"><span data-stu-id="e11c7-140">For more information, see [Start, Stop, Pause, Resume, Restart the Database Engine, SQL Server Agent, or SQL Server Browser Service](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md).</span></span>  
  
3.  <span data-ttu-id="e11c7-141">Per ogni file da spostare, usare i comandi **sqlcmd** oppure [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] per eseguire l'istruzione seguente.</span><span class="sxs-lookup"><span data-stu-id="e11c7-141">For each file to be moved, use **sqlcmd** commands or [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] to run the following statement.</span></span>  
  
    ```  
    ALTER DATABASE database_name MODIFY FILE( NAME = logical_name , FILENAME = 'new_path\os_file_name' );  
    ```  
  
     <span data-ttu-id="e11c7-142">Per altre informazioni su come usare l'utilità **sqlcmd** , vedere [Usare l'utilità sqlcmd](../scripting/sqlcmd-use-the-utility.md).</span><span class="sxs-lookup"><span data-stu-id="e11c7-142">For more information about how to use the **sqlcmd** utility, see [Use the sqlcmd Utility](../scripting/sqlcmd-use-the-utility.md).</span></span>  
  
4.  <span data-ttu-id="e11c7-143">Uscire dall'utilità **sqlcmd** o [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e11c7-143">Exit the **sqlcmd** utility or [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span></span>  
  
5.  <span data-ttu-id="e11c7-144">Arrestare l'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e11c7-144">Stop the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
6.  <span data-ttu-id="e11c7-145">Spostare il file o i file nella nuova posizione.</span><span class="sxs-lookup"><span data-stu-id="e11c7-145">Move the file or files to the new location.</span></span>  
  
7.  <span data-ttu-id="e11c7-146">Avviare l'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e11c7-146">Start the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="e11c7-147">Ad esempio, eseguire `NET START MSSQLSERVER`.</span><span class="sxs-lookup"><span data-stu-id="e11c7-147">For example, run: `NET START MSSQLSERVER`.</span></span>  
  
8.  <span data-ttu-id="e11c7-148">Verificare la modifica ai file eseguendo la query riportata di seguito.</span><span class="sxs-lookup"><span data-stu-id="e11c7-148">Verify the file change by running the following query.</span></span>  
  
    ```  
    SELECT name, physical_name AS CurrentLocation, state_desc  
    FROM sys.master_files  
    WHERE database_id = DB_ID(N'<database_name>');  
    ```  
  
## <a name="examples"></a><span data-ttu-id="e11c7-149">Esempi</span><span class="sxs-lookup"><span data-stu-id="e11c7-149">Examples</span></span>  
 <span data-ttu-id="e11c7-150">Nell'esempio seguente il file di log del database [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] viene spostato in una nuova posizione nell'ambito di una rilocazione pianificata.</span><span class="sxs-lookup"><span data-stu-id="e11c7-150">The following example moves the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] log file to a new location as part of a planned relocation.</span></span>  
  
```  
USE master;  
GO  
-- Return the logical file name.  
SELECT name, physical_name AS CurrentLocation, state_desc  
FROM sys.master_files  
WHERE database_id = DB_ID(N'AdventureWorks2012')  
    AND type_desc = N'LOG';  
GO  
ALTER DATABASE AdventureWorks2012 SET OFFLINE;  
GO  
-- Physically move the file to a new location.  
-- In the following statement, modify the path specified in FILENAME to  
-- the new location of the file on your server.  
ALTER DATABASE AdventureWorks2012   
    MODIFY FILE ( NAME = AdventureWorks2012_Log,   
                  FILENAME = 'C:\NewLoc\AdventureWorks2012_Log.ldf');  
GO  
ALTER DATABASE AdventureWorks2012 SET ONLINE;  
GO  
--Verify the new location.  
SELECT name, physical_name AS CurrentLocation, state_desc  
FROM sys.master_files  
WHERE database_id = DB_ID(N'AdventureWorks2012')  
    AND type_desc = N'LOG';  
```  
  
## <a name="see-also"></a><span data-ttu-id="e11c7-151">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e11c7-151">See Also</span></span>  
 <span data-ttu-id="e11c7-152">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e11c7-152">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 <span data-ttu-id="e11c7-153">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e11c7-153">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span></span>  
 <span data-ttu-id="e11c7-154">[Collegamento e scollegamento di un database &#40;SQL Server&#41;](database-detach-and-attach-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="e11c7-154">[Database Detach and Attach &#40;SQL Server&#41;](database-detach-and-attach-sql-server.md) </span></span>  
 <span data-ttu-id="e11c7-155">[Spostare i database di sistema](system-databases.md) </span><span class="sxs-lookup"><span data-stu-id="e11c7-155">[Move System Databases](system-databases.md) </span></span>  
 <span data-ttu-id="e11c7-156">[Spostare file del database](move-database-files.md) </span><span class="sxs-lookup"><span data-stu-id="e11c7-156">[Move Database Files](move-database-files.md) </span></span>  
 <span data-ttu-id="e11c7-157">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e11c7-157">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="e11c7-158">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e11c7-158">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 [<span data-ttu-id="e11c7-159">Avviare, arrestare, sospendere, riprendere, riavviare il motore di database, SQL Server Agent o SQL Server Browser</span><span class="sxs-lookup"><span data-stu-id="e11c7-159">Start, Stop, Pause, Resume, Restart the Database Engine, SQL Server Agent, or SQL Server Browser Service</span></span>](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md)  
  
  
