---
title: Ripristini di database completi (modello di recupero con registrazione minima) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- complete database restores
- database restores [SQL Server], complete database
- restoring databases [SQL Server], complete database
- simple recovery model [SQL Server]
- restoring [SQL Server], database
ms.assetid: 49828927-1727-4d1d-9ef5-3de43f68c026
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 67eee8d7d6f44c9ff83795bf2a8bd612309bf0a5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637932"
---
# <a name="complete-database-restores-simple-recovery-model"></a><span data-ttu-id="4eece-102">Ripristini di database completi (modello di recupero con registrazione minima)</span><span class="sxs-lookup"><span data-stu-id="4eece-102">Complete Database Restores (Simple Recovery Model)</span></span>
  <span data-ttu-id="4eece-103">L'obiettivo di un ripristino completo del database è il ripristino dell'intero database.</span><span class="sxs-lookup"><span data-stu-id="4eece-103">In a complete database restore, the goal is to restore the whole database.</span></span> <span data-ttu-id="4eece-104">L'intero database è offline per la tutta la durata del ripristino.</span><span class="sxs-lookup"><span data-stu-id="4eece-104">The whole database is offline for the duration of the restore.</span></span> <span data-ttu-id="4eece-105">Prima che sia possibile portare online una o più parti del database, tutti i dati vengono recuperati fino a un punto coerente in cui tutte le parti del database sono aggiornate allo stesso punto nel tempo e non sono presenti transazioni di cui non è stato eseguito il commit.</span><span class="sxs-lookup"><span data-stu-id="4eece-105">Before any part of the database can come online, all data is recovered to a consistent point in which all parts of the database are at the same point in time and no uncommitted transactions exist.</span></span>  
  
 <span data-ttu-id="4eece-106">Il modello di recupero con registrazione minima non consente di ripristinare il database fino a uno specifico punto nel tempo all'interno di un determinato backup.</span><span class="sxs-lookup"><span data-stu-id="4eece-106">Under the simple recovery model, the database cannot be restored to a specific point in time within a specific backup.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="4eece-107">È consigliabile evitare di collegare o ripristinare database provenienti da origini sconosciute o non attendibili.</span><span class="sxs-lookup"><span data-stu-id="4eece-107">We recommend that you do not attach or restore databases from unknown or untrusted sources.</span></span> <span data-ttu-id="4eece-108">Questi database potrebbero contenere malware che può eseguire codice [!INCLUDE[tsql](../../../includes/tsql-md.md)] indesiderato o causare errori modificando lo schema o la struttura fisica di database.</span><span class="sxs-lookup"><span data-stu-id="4eece-108">These databases could contain malicious code that might execute unintended [!INCLUDE[tsql](../../../includes/tsql-md.md)] code or cause errors by modifying the schema or the physical database structure.</span></span> <span data-ttu-id="4eece-109">Prima di utilizzare un database da un'origine sconosciuta o non attendibile, eseguire [DBCC CHECKDB](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) sul database in un server non di produzione ed esaminare il codice contenuto nel database, ad esempio le stored procedure o altro codice definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="4eece-109">Before you use a database from an unknown or untrusted source, run [DBCC CHECKDB](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) on the database on a nonproduction server and also examine the code, such as stored procedures or other user-defined code, in the database.</span></span>  
  

  
> [!NOTE]  
>  <span data-ttu-id="4eece-110">Per informazioni sul supporto dei backup di versioni precedenti di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], vedere la sezione "Supporto della compatibilità" di [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4eece-110">For information about support for backups from earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see the "Compatibility Support" section of [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql).</span></span>  
  
##  <a name="overview-of-database-restore-under-the-simple-recovery-model"></a><a name="Overview"></a> <span data-ttu-id="4eece-111">Panoramica del ripristino del database nel modello di recupero con registrazione minima</span><span class="sxs-lookup"><span data-stu-id="4eece-111">Overview of Database Restore Under the Simple Recovery Model</span></span>  
 <span data-ttu-id="4eece-112">Se si utilizza il modello di recupero con registrazione minima, il ripristino completo del database richiede solo una o due istruzioni [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) , a seconda che si desideri o meno ripristinare un backup differenziale del database.</span><span class="sxs-lookup"><span data-stu-id="4eece-112">A full database restore under the simple recovery model involves one or two [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) statements, depending on whether you want to restore a differential database backup.</span></span> <span data-ttu-id="4eece-113">Se si utilizza solo un backup di database completo, ripristinare unicamente il backup più recente come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="4eece-113">If you are using only a full database backup, just restore the most recent backup, as shown in the following illustration.</span></span>  
  
 <span data-ttu-id="4eece-114">![Ripristino solo di un backup completo del database](../../database-engine/media/bnrr-rmsimple1-fulldbbu.gif "Ripristino solo di un backup completo del database")</span><span class="sxs-lookup"><span data-stu-id="4eece-114">![Restoring only a full database backup](../../database-engine/media/bnrr-rmsimple1-fulldbbu.gif "Restoring only a full database backup")</span></span>  
  
 <span data-ttu-id="4eece-115">Se si utilizza anche un backup differenziale del database, ripristinare il backup completo del database più recente senza recuperare il database e quindi ripristinare il backup differenziale del database più recente e recuperare il database.</span><span class="sxs-lookup"><span data-stu-id="4eece-115">If you are also using a differential database backup, restore the most recent full database backup without recovering the database, and then restore the most recent differential database backup and recover the database.</span></span> <span data-ttu-id="4eece-116">Questo processo viene illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="4eece-116">The following illustration shows this process.</span></span>  
  
 <span data-ttu-id="4eece-117">![Ripristino di backup completi e differenziali del database](../../database-engine/media/bnrr-rmsimple2-diffdbbu.gif "Ripristino di backup completi e differenziali del database")</span><span class="sxs-lookup"><span data-stu-id="4eece-117">![Restoring full and differential database backups](../../database-engine/media/bnrr-rmsimple2-diffdbbu.gif "Restoring full and differential database backups")</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4eece-118">Se si prevede di ripristinare un backup del database in un'istanza del server diversa, vedere [Copiare database tramite backup e ripristino](../databases/copy-databases-with-backup-and-restore.md).</span><span class="sxs-lookup"><span data-stu-id="4eece-118">If you plan to restore a database backup onto a different server instance, see [Copy Databases with Backup and Restore](../databases/copy-databases-with-backup-and-restore.md).</span></span>  
  
###  <a name="basic-transact-sql-restore-syntax"></a><a name="TsqlSyntax"></a> <span data-ttu-id="4eece-119">Sintassi Transact-SQL di base per RESTORE</span><span class="sxs-lookup"><span data-stu-id="4eece-119">Basic Transact-SQL RESTORE Syntax</span></span>  
 <span data-ttu-id="4eece-120">La sintassi di base di [!INCLUDE[tsql](../../../includes/tsql-md.md)][RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) per il ripristino di un backup di database completo è la seguente:</span><span class="sxs-lookup"><span data-stu-id="4eece-120">The basic [!INCLUDE[tsql](../../../includes/tsql-md.md)][RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) syntax for restoring a full database backup is:</span></span>  
  
 <span data-ttu-id="4eece-121">RESTORE DATABASE *nome_database* FROM *dispositivo_backup* [ WITH NORECOVERY ]</span><span class="sxs-lookup"><span data-stu-id="4eece-121">RESTORE DATABASE *database_name* FROM *backup_device* [ WITH NORECOVERY ]</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4eece-122">Utilizzare WITH NORECOVERY se si desidera ripristinare anche un backup differenziale del database.</span><span class="sxs-lookup"><span data-stu-id="4eece-122">Use WITH NORECOVERY if you plan to also restore a differential database backup.</span></span>  
  
 <span data-ttu-id="4eece-123">La sintassi di base di [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) per il ripristino di un backup del database è la seguente:</span><span class="sxs-lookup"><span data-stu-id="4eece-123">The basic [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) syntax for restoring a database backup is:</span></span>  
  
 <span data-ttu-id="4eece-124">RESTORE DATABASE *nome_database* FROM *dispositivo_backup* WITH RECOVERY</span><span class="sxs-lookup"><span data-stu-id="4eece-124">RESTORE DATABASE *database_name* FROM *backup_device* WITH RECOVERY</span></span>  
  
###  <a name="example-transact-sql"></a><a name="Example"></a> <span data-ttu-id="4eece-125">Esempio (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="4eece-125">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="4eece-126">Nell'esempio seguente viene innanzitutto illustrato come utilizzare l'istruzione [BACKUP](/sql/t-sql/statements/backup-transact-sql) per creare un backup completo del database e un backup differenziale del database [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4eece-126">The following example first shows how to use the [BACKUP](/sql/t-sql/statements/backup-transact-sql) statement to create a full database backup and a differential database backup of the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span> <span data-ttu-id="4eece-127">Questi backup vengono quindi ripristinati in sequenza.</span><span class="sxs-lookup"><span data-stu-id="4eece-127">The example then restores these backups in sequence.</span></span> <span data-ttu-id="4eece-128">Il database è ripristinato con lo stesso stato del momento in cui è stato completato il backup differenziale del database.</span><span class="sxs-lookup"><span data-stu-id="4eece-128">The database is restored to its state as of the time that the differential database backup finished.</span></span>  
  
 <span data-ttu-id="4eece-129">Nell'esempio seguente vengono illustrate le opzioni fondamentali di una sequenza di ripristino per lo scenario di ripristino completo del database.</span><span class="sxs-lookup"><span data-stu-id="4eece-129">The example shows the critical options in a restore sequence for the complete database restore scenario.</span></span> <span data-ttu-id="4eece-130">Una *sequenza di ripristino* è costituita da una o più operazioni di ripristino che gestiscono lo spostamento dei dati attraverso una o più fasi del ripristino.</span><span class="sxs-lookup"><span data-stu-id="4eece-130">A *restore sequence* consists of one or more restore operations that move data through one or more of the phases of restore.</span></span> <span data-ttu-id="4eece-131">La sintassi e i dettagli non rilevanti sono stati omessi.</span><span class="sxs-lookup"><span data-stu-id="4eece-131">Syntax and details that are not relevant to this purpose are omitted.</span></span> <span data-ttu-id="4eece-132">Quando si recupera un database, è consigliabile specificare in modo esplicito l'opzione RECOVERY per maggiore chiarezza, anche se si tratta dell'opzione predefinita.</span><span class="sxs-lookup"><span data-stu-id="4eece-132">When you recover a database, we recommend explicitly specifying the RECOVERY option for clarity, even though it is the default.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4eece-133">L'esempio inizia con un'istruzione [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql) che imposta il modello di recupero su `SIMPLE`.</span><span class="sxs-lookup"><span data-stu-id="4eece-133">The example starts with an [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql) statement that sets the recovery model to `SIMPLE`.</span></span>  
  
```  
USE master;  
--Make sure the database is using the simple recovery model.  
ALTER DATABASE AdventureWorks2012 SET RECOVERY SIMPLE;  
GO  
-- Back up the full AdventureWorks2012 database.  
BACKUP DATABASE AdventureWorks2012   
TO DISK = 'Z:\SQLServerBackups\AdventureWorks2012.bak'   
  WITH FORMAT;  
GO  
--Create a differential database backup.  
BACKUP DATABASE AdventureWorks2012   
TO DISK = 'Z:\SQLServerBackups\AdventureWorks2012.bak'  
   WITH DIFFERENTIAL;  
GO  
--Restore the full database backup (from backup set 1).  
RESTORE DATABASE AdventureWorks2012   
FROM DISK = 'Z:\SQLServerBackups\AdventureWorks2012.bak'   
   WITH FILE=1, NORECOVERY;  
--Restore the differential backup (from backup set 2).  
RESTORE DATABASE AdventureWorks2012   
FROM DISK = 'Z:\SQLServerBackups\AdventureWorks2012.bak'   
   WITH FILE=2, RECOVERY;  
GO  
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="4eece-134">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="4eece-134">Related Tasks</span></span>  
 <span data-ttu-id="4eece-135">**Per ripristinare un backup completo del database**</span><span class="sxs-lookup"><span data-stu-id="4eece-135">**To restore a full database backup**</span></span>  
  
-   [<span data-ttu-id="4eece-136">Ripristinare un backup del database nel modello di recupero con registrazione minima &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4eece-136">Restore a Database Backup Under the Simple Recovery Model &#40;Transact-SQL&#41;</span></span>](restore-a-database-backup-under-the-simple-recovery-model-transact-sql.md)  
  
-   [<span data-ttu-id="4eece-137">Ripristinare un backup del database &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="4eece-137">Restore a Database Backup &#40;SQL Server Management Studio&#41;</span></span>](restore-a-database-backup-using-ssms.md)  
  
-   [<span data-ttu-id="4eece-138">Ripristinare un database in una nuova posizione &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4eece-138">Restore a Database to a New Location &#40;SQL Server&#41;</span></span>](restore-a-database-to-a-new-location-sql-server.md)  
  
 <span data-ttu-id="4eece-139">**Per ripristinare un backup differenziale del database**</span><span class="sxs-lookup"><span data-stu-id="4eece-139">**To restore a differential database backup**</span></span>  
  
-   [<span data-ttu-id="4eece-140">Ripristinare un backup differenziale del database &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4eece-140">Restore a Differential Database Backup &#40;SQL Server&#41;</span></span>](restore-a-differential-database-backup-sql-server.md)  
  
 <span data-ttu-id="4eece-141">**Per ripristinare un backup utilizzando SMO (SQL Server Management Objects)**</span><span class="sxs-lookup"><span data-stu-id="4eece-141">**To restore a backup by using SQL Server Management Objects (SMO)**</span></span>  
  
-   <xref:Microsoft.SqlServer.Management.Smo.Restore.SqlRestore%2A>  
  

  
## <a name="see-also"></a><span data-ttu-id="4eece-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4eece-142">See Also</span></span>  
 <span data-ttu-id="4eece-143">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4eece-143">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 <span data-ttu-id="4eece-144">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4eece-144">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="4eece-145">[sp_addumpdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4eece-145">[sp_addumpdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) </span></span>  
 <span data-ttu-id="4eece-146">[Backup completo del database &#40;SQL Server&#41;](full-database-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="4eece-146">[Full Database Backups &#40;SQL Server&#41;](full-database-backups-sql-server.md) </span></span>  
 <span data-ttu-id="4eece-147">[Backup differenziali &#40;SQL Server&#41;](differential-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="4eece-147">[Differential Backups &#40;SQL Server&#41;](differential-backups-sql-server.md) </span></span>  
 <span data-ttu-id="4eece-148">[Panoramica del backup &#40;SQL Server&#41;](backup-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="4eece-148">[Backup Overview &#40;SQL Server&#41;](backup-overview-sql-server.md) </span></span>  
 [<span data-ttu-id="4eece-149">Panoramica del ripristino e del recupero &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4eece-149">Restore and Recovery Overview &#40;SQL Server&#41;</span></span>](restore-and-recovery-overview-sql-server.md)  
  
  
