---
title: Backup completo del database (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- full backups [SQL Server]
- backups [SQL Server], database
- backing up databases [SQL Server], full backups
- estimating database backup size
- backing up [SQL Server], size of backup
- database backups [SQL Server], full backups
- size [SQL Server], backups
- database backups [SQL Server], about backing up databases
ms.assetid: 4d933d19-8d21-4aa1-8153-d230cb3a3f99
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ee871b6cabbe6c2b2cb4f444fd1e2d42d711dfbc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715439"
---
# <a name="full-database-backups-sql-server"></a><span data-ttu-id="1c967-102">Backup completo del database (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="1c967-102">Full Database Backups (SQL Server)</span></span>
  <span data-ttu-id="1c967-103">Un backup completo del database consente di eseguire il backup dell'intero database.</span><span class="sxs-lookup"><span data-stu-id="1c967-103">A full database backup backs up the whole database.</span></span> <span data-ttu-id="1c967-104">Tale backup include la parte del log delle transazioni sufficiente per consentire il recupero del database completo dopo il ripristino del backup completo del database.</span><span class="sxs-lookup"><span data-stu-id="1c967-104">This includes part of the transaction log so that the full database can be recovered after a full database backup is restored.</span></span> <span data-ttu-id="1c967-105">I backup completi del database rappresentano il database al momento del completamento del backup.</span><span class="sxs-lookup"><span data-stu-id="1c967-105">Full database backups represent the database at the time the backup finished.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="1c967-106">Poiché le dimensioni del database aumentano, i backup completi del database richiedono più tempo e più spazio di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="1c967-106">As a database increases in size full database backups take more time to finish and require more storage space.</span></span> <span data-ttu-id="1c967-107">Per un database di grandi dimensioni può pertanto essere utile integrare un backup completo del database con una serie di *backup database differenziali*.</span><span class="sxs-lookup"><span data-stu-id="1c967-107">Therefore, for a large database, you might want to supplement a full database backup with a series of *differential database backups*.</span></span> <span data-ttu-id="1c967-108">Per altre informazioni, vedere [Backup differenziali &#40;SQL Server&#41;](differential-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="1c967-108">For more information, see [Differential Backups &#40;SQL Server&#41;](differential-backups-sql-server.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="1c967-109">TRUSTWORTHY è impostato su OFF in un backup del database.</span><span class="sxs-lookup"><span data-stu-id="1c967-109">TRUSTWORTHY is set to OFF on a database backup.</span></span> <span data-ttu-id="1c967-110">Per informazioni su come impostare TRUSTWORTHY su ON, vedere [Opzioni ALTER DATABASE SET &#40; Transact-SQL &#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span><span class="sxs-lookup"><span data-stu-id="1c967-110">For information about how to set TRUSTWORTHY to ON, see [ALTER DATABASE SET Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span></span>  
  
 <span data-ttu-id="1c967-111">**Contenuto dell'argomento:**</span><span class="sxs-lookup"><span data-stu-id="1c967-111">**In This Topic:**</span></span>  
  
-   [<span data-ttu-id="1c967-112">Backup del database nel modello di recupero con registrazione minima</span><span class="sxs-lookup"><span data-stu-id="1c967-112">Database Backups Under the Simple Recovery Model</span></span>](#DbBuRMs)  
  
-   [<span data-ttu-id="1c967-113">Backup del database nel modello di recupero con registrazione completa</span><span class="sxs-lookup"><span data-stu-id="1c967-113">Database Backups Under the Full Recovery Model</span></span>](#DbBuRMf)  
  
-   [<span data-ttu-id="1c967-114">Utilizzare un backup completo del database per ripristinare il database</span><span class="sxs-lookup"><span data-stu-id="1c967-114">Use a Full Database Backup to Restore the Database</span></span>](#RestoreDbBu)  
  
-   [<span data-ttu-id="1c967-115">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="1c967-115">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="database-backups-under-the-simple-recovery-model"></a><a name="DbBuRMs"></a> <span data-ttu-id="1c967-116">Backup del database nel modello di recupero con registrazione minima</span><span class="sxs-lookup"><span data-stu-id="1c967-116">Database Backups Under the Simple Recovery Model</span></span>  
 <span data-ttu-id="1c967-117">Se si utilizza il modello di recupero con registrazione minima, dopo ogni backup, il database è esposto al rischio di perdita di dati nel caso si verifichi un'emergenza.</span><span class="sxs-lookup"><span data-stu-id="1c967-117">Under the simple recovery model, after each backup, the database is exposed to potential work loss if a disaster were to occur.</span></span> <span data-ttu-id="1c967-118">Questo rischio aumenta a ogni aggiornamento fino al backup successivo, quando il rischio torna a essere zero e inizia un nuovo ciclo.</span><span class="sxs-lookup"><span data-stu-id="1c967-118">The work-loss exposure increases with each update until the next backup, when the work-loss exposure returns to zero and a new cycle of work-loss exposure starts.</span></span> <span data-ttu-id="1c967-119">Il rischio di perdita dei dati cresce nel tempo che intercorre tra un backup e l'altro.</span><span class="sxs-lookup"><span data-stu-id="1c967-119">Work-loss exposure increases over time between backups.</span></span> <span data-ttu-id="1c967-120">Nella figura seguente viene illustrato il rischio di perdita di dati per una strategia di backup che utilizza solo backup completi di database.</span><span class="sxs-lookup"><span data-stu-id="1c967-120">The following illustration shows the work-loss exposure for a backup strategy that uses only full database backups.</span></span>  
  
 <span data-ttu-id="1c967-121">![Rischio di perdita di lavoro tra due backup del database](../../database-engine/media/bnr-rmsimple-1-fulldb-backups.gif "Rischio di perdita di lavoro tra due backup del database")</span><span class="sxs-lookup"><span data-stu-id="1c967-121">![Shows work-loss exposure between database backups](../../database-engine/media/bnr-rmsimple-1-fulldb-backups.gif "Shows work-loss exposure between database backups")</span></span>  
  
### <a name="example--tsql"></a><span data-ttu-id="1c967-122">Esempio ([!INCLUDE[tsql](../../../includes/tsql-md.md)])</span><span class="sxs-lookup"><span data-stu-id="1c967-122">Example ( [!INCLUDE[tsql](../../../includes/tsql-md.md)])</span></span>  
 <span data-ttu-id="1c967-123">Nell'esempio seguente viene illustrato come creare un backup completo del database utilizzando WITH FORMAT per sovrascrivere eventuali backup esistenti e creare un nuovo set di supporti.</span><span class="sxs-lookup"><span data-stu-id="1c967-123">The following example shows how to create a full database backup by using WITH FORMAT to overwrite any existing backups and create a new media set.</span></span>  
  
```  
-- Back up the AdventureWorks2012 database to new media set.  
BACKUP DATABASE AdventureWorks2012  
    TO DISK = 'Z:\SQLServerBackups\AdventureWorksSimpleRM.bak'   
    WITH FORMAT;  
GO  
```  
  
##  <a name="database-backups-under-the-full-recovery-model"></a><a name="DbBuRMf"></a> <span data-ttu-id="1c967-124">Backup del database nel modello di recupero con registrazione completa</span><span class="sxs-lookup"><span data-stu-id="1c967-124">Database Backups Under the Full Recovery Model</span></span>  
 <span data-ttu-id="1c967-125">Per i database che utilizzano il modello di recupero con registrazione completa e il modello di recupero con registrazione minima delle operazioni bulk, i backup del database sono necessari, ma non sufficienti.</span><span class="sxs-lookup"><span data-stu-id="1c967-125">For databases that use full and bulk-logged recovery, database backups are necessary but not sufficient.</span></span> <span data-ttu-id="1c967-126">Sono inoltre necessari i backup del log delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="1c967-126">Transaction log backups are also required.</span></span> <span data-ttu-id="1c967-127">Nella figura seguente viene illustrata la strategia di backup più semplice possibile quando si utilizza il modello di recupero con registrazione completa.</span><span class="sxs-lookup"><span data-stu-id="1c967-127">The following illustration shows the least complex backup strategy that is possible under the full recovery model.</span></span>  
  
 <span data-ttu-id="1c967-128">![Serie di backup completi del database e backup del log](../../database-engine/media/bnr-rmfull-1-fulldb-log-backups.gif "Serie di backup completi del database e backup del log")</span><span class="sxs-lookup"><span data-stu-id="1c967-128">![Series of full database backups and log backups](../../database-engine/media/bnr-rmfull-1-fulldb-log-backups.gif "Series of full database backups and log backups")</span></span>  
  
 <span data-ttu-id="1c967-129">Per informazioni sulle modalità di creazione dei backup di log, vedere [Backup di log delle transazioni &#40; SQL Server&#41;](transaction-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="1c967-129">For information about how to create log backups, see [Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md).</span></span>  
  
### <a name="example--tsql"></a><span data-ttu-id="1c967-130">Esempio ([!INCLUDE[tsql](../../../includes/tsql-md.md)])</span><span class="sxs-lookup"><span data-stu-id="1c967-130">Example ( [!INCLUDE[tsql](../../../includes/tsql-md.md)])</span></span>  
 <span data-ttu-id="1c967-131">Nell'esempio seguente viene illustrato come creare un backup completo del database utilizzando WITH FORMAT per sovrascrivere eventuali backup esistenti e creare un nuovo set di supporti.</span><span class="sxs-lookup"><span data-stu-id="1c967-131">The following example shows how to create a full database backup by using WITH FORMAT to overwrite any existing backups and create a new media set.</span></span> <span data-ttu-id="1c967-132">Viene quindi eseguito il backup del log delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="1c967-132">Then, the example backs up the transaction log.</span></span> <span data-ttu-id="1c967-133">In una situazione reale sarebbe necessario eseguire una serie di backup del log regolari.</span><span class="sxs-lookup"><span data-stu-id="1c967-133">In a real-life situation, you would have to perform a series of regular log backups.</span></span> <span data-ttu-id="1c967-134">In questo caso il database di esempio [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] viene impostato per l'utilizzo del modello di recupero con registrazione completa.</span><span class="sxs-lookup"><span data-stu-id="1c967-134">For this example, the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database is set to use the full recovery model.</span></span>  
  
```  
USE master;  
ALTER DATABASE AdventureWorks2012 SET RECOVERY FULL;  
GO  
-- Back up the AdventureWorks2012 database to new media set (backup set 1).  
BACKUP DATABASE AdventureWorks2012  
  TO DISK = 'Z:\SQLServerBackups\AdventureWorks2012FullRM.bak'   
  WITH FORMAT;  
GO  
--Create a routine log backup (backup set 2).  
BACKUP LOG AdventureWorks2012 TO DISK = 'Z:\SQLServerBackups\AdventureWorks2012FullRM.bak';  
GO  
```  
  
##  <a name="use-a-full-database-backup-to-restore-the-database"></a><a name="RestoreDbBu"></a> <span data-ttu-id="1c967-135">Utilizzare un backup completo del database per ripristinare il database</span><span class="sxs-lookup"><span data-stu-id="1c967-135">Use a Full Database Backup to Restore the Database</span></span>  
 <span data-ttu-id="1c967-136">È possibile ricreare un intero database in un solo passaggio ripristinando il database da un backup completo del database in qualsiasi posizione.</span><span class="sxs-lookup"><span data-stu-id="1c967-136">You can re-create a whole database in one step by restoring the database from a full database backup to any location.</span></span> <span data-ttu-id="1c967-137">Nel backup è inclusa una parte del log delle transazioni sufficiente per consentire il recupero del database fino al momento in cui è terminato il backup.</span><span class="sxs-lookup"><span data-stu-id="1c967-137">Enough of the transaction log is included in the backup to let you recover the database to the time when the backup finished.</span></span> <span data-ttu-id="1c967-138">Lo stato del database ripristinato corrisponde allo stato del database originale al termine del backup del database, escluse eventuali transazioni di cui non è stato eseguito il commit.</span><span class="sxs-lookup"><span data-stu-id="1c967-138">The restored database matches the state of the original database when the database backup finished, minus any uncommitted transactions.</span></span> <span data-ttu-id="1c967-139">Nel modello di recupero completo, ripristinare tutti i successivi backup del log delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="1c967-139">Under the full recovery model, you should then restore all subsequent transaction log backups.</span></span> <span data-ttu-id="1c967-140">Quando il database viene recuperato, viene effettuato il rollback delle transazioni di cui non è stato eseguito il commit.</span><span class="sxs-lookup"><span data-stu-id="1c967-140">When the database is recovered, uncommitted transactions are rolled back.</span></span>  
  
 <span data-ttu-id="1c967-141">Per altre informazioni, vedere [Ripristini di database completi &#40;modello di recupero con registrazione minima&#41;](complete-database-restores-simple-recovery-model.md) o [Ripristini di database completi &#40;modello di recupero con registrazione completa &#41;](complete-database-restores-full-recovery-model.md).</span><span class="sxs-lookup"><span data-stu-id="1c967-141">For more information, see [Complete Database Restores &#40;Simple Recovery Model&#41;](complete-database-restores-simple-recovery-model.md) or [Complete Database Restores &#40;Full Recovery Model&#41;](complete-database-restores-full-recovery-model.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="1c967-142">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="1c967-142">Related Tasks</span></span>  
 <span data-ttu-id="1c967-143">**Per creare un backup completo del database**</span><span class="sxs-lookup"><span data-stu-id="1c967-143">**To create a full database backup**</span></span>  
  
-   [<span data-ttu-id="1c967-144">Creazione di un backup completo del database &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="1c967-144">Create a Full Database Backup &#40;SQL Server&#41;</span></span>](create-a-full-database-backup-sql-server.md)  
  
-   <span data-ttu-id="1c967-145"><xref:Microsoft.SqlServer.Management.Smo.Backup.SqlBackup%2A> (SMO)</span><span class="sxs-lookup"><span data-stu-id="1c967-145"><xref:Microsoft.SqlServer.Management.Smo.Backup.SqlBackup%2A> (SMO)</span></span>  
  
 <span data-ttu-id="1c967-146">**Per pianificare i processi di backup**</span><span class="sxs-lookup"><span data-stu-id="1c967-146">**To schedule backup jobs**</span></span>  
  
 [<span data-ttu-id="1c967-147">Utilizzare la Creazione guidata piano di manutenzione</span><span class="sxs-lookup"><span data-stu-id="1c967-147">Use the Maintenance Plan Wizard</span></span>](../maintenance-plans/use-the-maintenance-plan-wizard.md)  
  
## <a name="see-also"></a><span data-ttu-id="1c967-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1c967-148">See Also</span></span>  
 <span data-ttu-id="1c967-149">[Backup e ripristino di database SQL Server](back-up-and-restore-of-sql-server-databases.md) </span><span class="sxs-lookup"><span data-stu-id="1c967-149">[Back Up and Restore of SQL Server Databases](back-up-and-restore-of-sql-server-databases.md) </span></span>  
 <span data-ttu-id="1c967-150">[Panoramica del backup &#40;SQL Server&#41;](backup-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="1c967-150">[Backup Overview &#40;SQL Server&#41;](backup-overview-sql-server.md) </span></span>  
 [<span data-ttu-id="1c967-151">Backup e ripristino di database di Analysis Services</span><span class="sxs-lookup"><span data-stu-id="1c967-151">Backup and Restore of Analysis Services Databases</span></span>](https://docs.microsoft.com/analysis-services/multidimensional-models/backup-and-restore-of-analysis-services-databases)  
  
  
