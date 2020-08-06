---
title: Ripristini di database completi (modello di recupero con registrazione completa) | Microsoft Docs
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
- restoring [SQL Server], database
- full recovery model [SQL Server], performing restores
- log backups [SQL Server[
ms.assetid: 5b4c471c-b972-498e-aba9-92cf7a0ea881
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ea6ec9f196acd0a64a0b785024bd6426cd6a5381
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637935"
---
# <a name="complete-database-restores-full-recovery-model"></a><span data-ttu-id="1e8cf-102">Ripristini di database completi (modello di recupero con registrazione completa)</span><span class="sxs-lookup"><span data-stu-id="1e8cf-102">Complete Database Restores (Full Recovery Model)</span></span>
  <span data-ttu-id="1e8cf-103">L'obiettivo di un ripristino completo del database è il ripristino dell'intero database.</span><span class="sxs-lookup"><span data-stu-id="1e8cf-103">In a complete database restore, the goal is to restore the whole database.</span></span> <span data-ttu-id="1e8cf-104">L'intero database è offline per la tutta la durata del ripristino.</span><span class="sxs-lookup"><span data-stu-id="1e8cf-104">The whole database is offline for the duration of the restore.</span></span> <span data-ttu-id="1e8cf-105">Prima che sia possibile portare online una o più parti del database, tutti i dati vengono recuperati fino a un punto coerente in cui tutte le parti del database sono aggiornate allo stesso punto nel tempo e non sono presenti transazioni di cui non è stato eseguito il commit.</span><span class="sxs-lookup"><span data-stu-id="1e8cf-105">Before any part of the database can come online, all data is recovered to a consistent point in which all parts of the database are at the same point in time and no uncommitted transactions exist.</span></span>  
  
 <span data-ttu-id="1e8cf-106">Dopo aver ripristinato uno o più backup dei dati, è necessario ripristinare tutti i backup del log delle transazioni successivi nel modello di recupero con registrazione completa, quindi recuperare il database.</span><span class="sxs-lookup"><span data-stu-id="1e8cf-106">Under the full recovery model, after you restore your data backup or backups, you must restore all subsequent transaction log backups and then recover the database.</span></span> <span data-ttu-id="1e8cf-107">È possibile ripristinare un database in un *punto di recupero* specifico all'interno di uno di questi backup del log.</span><span class="sxs-lookup"><span data-stu-id="1e8cf-107">You can restore a database to a specific *recovery point* within one of these log backups.</span></span> <span data-ttu-id="1e8cf-108">Tale punto di recupero può corrispondere a una data e un'ora specifiche, a una transazione contrassegnata o a un numero di sequenza del file di log (LSN).</span><span class="sxs-lookup"><span data-stu-id="1e8cf-108">The recovery point can be a specific date and time, a marked transaction, or a log sequence number (LSN).</span></span>  
  
 <span data-ttu-id="1e8cf-109">Durante il ripristino di un database, in particolare nel modello di recupero con registrazione completa o in quello con registrazione minima delle operazioni bulk, si consiglia di utilizzare una sola sequenza di ripristino.</span><span class="sxs-lookup"><span data-stu-id="1e8cf-109">When restoring a database, particularly under the full recovery model or bulk-logged recovery model, you should use a single restore sequence.</span></span> <span data-ttu-id="1e8cf-110">Una *sequenza di ripristino* è costituita da una o più operazioni di ripristino che gestiscono lo spostamento dei dati attraverso una o più fasi del ripristino.</span><span class="sxs-lookup"><span data-stu-id="1e8cf-110">A *restore sequence* consists of one or more restore operations that move data through one or more of the phases of restore.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="1e8cf-111">È consigliabile evitare di collegare o ripristinare database provenienti da origini sconosciute o non attendibili.</span><span class="sxs-lookup"><span data-stu-id="1e8cf-111">We recommend that you do not attach or restore databases from unknown or untrusted sources.</span></span> <span data-ttu-id="1e8cf-112">Questi database potrebbero contenere malware che può eseguire codice [!INCLUDE[tsql](../../includes/tsql-md.md)] indesiderato o causare errori modificando lo schema o la struttura fisica di database.</span><span class="sxs-lookup"><span data-stu-id="1e8cf-112">These databases could contain malicious code that might execute unintended [!INCLUDE[tsql](../../includes/tsql-md.md)] code or cause errors by modifying the schema or the physical database structure.</span></span> <span data-ttu-id="1e8cf-113">Prima di utilizzare un database da un'origine sconosciuta o non attendibile, eseguire [DBCC CHECKDB](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) sul database in un server non di produzione ed esaminare il codice contenuto nel database, ad esempio le stored procedure o altro codice definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="1e8cf-113">Before you use a database from an unknown or untrusted source, run [DBCC CHECKDB](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) on the database on a nonproduction server and also examine the code, such as stored procedures or other user-defined code, in the database.</span></span>  
  
 <span data-ttu-id="1e8cf-114">**Contenuto dell'argomento**</span><span class="sxs-lookup"><span data-stu-id="1e8cf-114">**In this Topic:**</span></span>  
  
-   [<span data-ttu-id="1e8cf-115">Ripristino di un database fino al momento in cui si è verificato l'errore</span><span class="sxs-lookup"><span data-stu-id="1e8cf-115">Restoring a Database to the Point of Failure</span></span>](#PointOfFailure)  
  
-   [<span data-ttu-id="1e8cf-116">Ripristino di un database fino a un punto all'interno di un backup del log</span><span class="sxs-lookup"><span data-stu-id="1e8cf-116">Restoring a Database to a Point Within a Log Backup</span></span>](#PointWithinBackup)  
  
-   [<span data-ttu-id="1e8cf-117">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="1e8cf-117">Related Tasks</span></span>](#RelatedTasks)  
  
> [!NOTE]  
>  <span data-ttu-id="1e8cf-118">Per informazioni sul supporto dei backup di versioni precedenti di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], vedere la sezione "Supporto della compatibilità" di [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1e8cf-118">For information about support for backups from earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see the "Compatibility Support" section of [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql).</span></span>  
  
##  <a name="restoring-a-database-to-the-point-of-failure"></a><a name="PointOfFailure"></a> <span data-ttu-id="1e8cf-119">Ripristino di un database fino al momento dell'errore</span><span class="sxs-lookup"><span data-stu-id="1e8cf-119">Restoring a Database to the Point of Failure</span></span>  
 <span data-ttu-id="1e8cf-120">Il recupero dello stato di un database fino al momento dell'errore in genere include i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="1e8cf-120">Typically, recovering a database to the point of failure involves the following basic steps:</span></span>  
  
1.  <span data-ttu-id="1e8cf-121">Eseguire il backup del log delle transazioni attive (noto anche come parte finale del log).</span><span class="sxs-lookup"><span data-stu-id="1e8cf-121">Back up the active transaction log (known as the tail of the log).</span></span> <span data-ttu-id="1e8cf-122">In questo modo viene creato un backup della parte finale del log.</span><span class="sxs-lookup"><span data-stu-id="1e8cf-122">This creates a tail-log backup.</span></span> <span data-ttu-id="1e8cf-123">Se il log delle transazioni attivo non è disponibile, tutte le transazioni in quella parte del log vengono perdute.</span><span class="sxs-lookup"><span data-stu-id="1e8cf-123">If the active transaction log is unavailable, all transactions in that part of the log are lost.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="1e8cf-124">Nel modello di recupero con registrazione minima delle operazioni bulk, per eseguire il backup di un log che contiene operazioni bulk registrate è necessario disporre dell'accesso a tutti i file di dati del database.</span><span class="sxs-lookup"><span data-stu-id="1e8cf-124">Under the bulk-logged recovery model, backing up any log that contains bulk-logged operations requires access to all data files in the database.</span></span> <span data-ttu-id="1e8cf-125">Se i file di dati non sono accessibili, non è possibile eseguire il backup del log delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="1e8cf-125">If the data files cannot be accessed, the transaction log cannot be backed up.</span></span> <span data-ttu-id="1e8cf-126">In questo caso, è necessario ripetere manualmente tutte le modifiche apportate a partire dall'ultimo backup del log.</span><span class="sxs-lookup"><span data-stu-id="1e8cf-126">In that case, you have to manually redo all changes that were made since the most recent log backup.</span></span>  
  
     <span data-ttu-id="1e8cf-127">Per altre informazioni, vedere [Backup della parte finale del log &#40;SQL Server&#41;](tail-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="1e8cf-127">For more information, see [Tail-Log Backups &#40;SQL Server&#41;](tail-log-backups-sql-server.md).</span></span>  
  
2.  <span data-ttu-id="1e8cf-128">Ripristinare il backup completo del database più recente senza recuperare il database (RESTORE DATABASE *_database* FROM *_backup* WITH NORECOVERY).</span><span class="sxs-lookup"><span data-stu-id="1e8cf-128">Restore the most recent full database backup without recovering the database (RESTORE DATABASE *database_name* FROM *backup_device* WITH NORECOVERY).</span></span>  
  
3.  <span data-ttu-id="1e8cf-129">Se sono presenti backup differenziali, ripristinare il più recente senza recuperare il database (RESTORE DATABASE *nome_database* FROM *dispositivo_backup_differenziale* WITH NORECOVERY).</span><span class="sxs-lookup"><span data-stu-id="1e8cf-129">If differential backups exist, restore the most recent one without recovering the database (RESTORE DATABASE *database_name* FROM *differential_backup_device* WITH NORECOVERY).</span></span>  
  
     <span data-ttu-id="1e8cf-130">In questo modo viene ridotto il numero di backup del log da ripristinare.</span><span class="sxs-lookup"><span data-stu-id="1e8cf-130">Restoring the most recent differential backup reduces the number of log backups that must be restored.</span></span>  
  
4.  <span data-ttu-id="1e8cf-131">Ripristinare i log in sequenza con NORECOVERY a partire dal primo backup del log delle transazioni creato dopo il backup appena ripristinato.</span><span class="sxs-lookup"><span data-stu-id="1e8cf-131">Starting with the first transaction log backup that was created after the backup you just restored, restore the logs in sequence with NORECOVERY.</span></span>  
  
5.  <span data-ttu-id="1e8cf-132">Recuperare il database (RESTORE DATABASE *nome_database* WITH RECOVERY).</span><span class="sxs-lookup"><span data-stu-id="1e8cf-132">Recover the database (RESTORE DATABASE *database_name* WITH RECOVERY).</span></span> <span data-ttu-id="1e8cf-133">In alternativa, è possibile eseguire questo passaggio insieme al ripristino dell'ultimo backup del log.</span><span class="sxs-lookup"><span data-stu-id="1e8cf-133">Alternatively, this step can be combined with restoring the last log backup.</span></span>  
  
 <span data-ttu-id="1e8cf-134">Nella figura seguente è illustrata tale sequenza di ripristino.</span><span class="sxs-lookup"><span data-stu-id="1e8cf-134">The following illustration shows this restore sequence.</span></span> <span data-ttu-id="1e8cf-135">Dopo il verificarsi di un errore (1) viene creato un backup della parte finale del log (2).</span><span class="sxs-lookup"><span data-stu-id="1e8cf-135">After a failure occurs (1), a tail-log backup is created (2).</span></span> <span data-ttu-id="1e8cf-136">Successivamente, il database viene ripristinato fino al momento dell'errore.</span><span class="sxs-lookup"><span data-stu-id="1e8cf-136">Next, the database is restored to the point of the failure.</span></span> <span data-ttu-id="1e8cf-137">L'operazione comporta il ripristino di un backup del database, di un successivo backup differenziale e di tutti i backup del log eseguiti dopo il backup differenziale, incluso il backup della parte finale del log.</span><span class="sxs-lookup"><span data-stu-id="1e8cf-137">This involves restoring a database backup, a subsequent differential backup, and every log backup taken after the differential backup, including the tail-log backup.</span></span>  
  
 <span data-ttu-id="1e8cf-138">![Ripristino di database completo fino al momento in cui si è verificato un errore](../../database-engine/media/bnrr-rmfull1-db-failure-pt.gif "Ripristino di database completo fino al momento in cui si è verificato un errore")</span><span class="sxs-lookup"><span data-stu-id="1e8cf-138">![Complete database restore to the time of a failure](../../database-engine/media/bnrr-rmfull1-db-failure-pt.gif "Complete database restore to the time of a failure")</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1e8cf-139">Se si ripristina un backup del database in un'istanza del server diversa, vedere [Copiare database tramite backup e ripristino](../databases/copy-databases-with-backup-and-restore.md).</span><span class="sxs-lookup"><span data-stu-id="1e8cf-139">When you restore a database backup onto a different server instance, see [Copy Databases with Backup and Restore](../databases/copy-databases-with-backup-and-restore.md).</span></span>  
  
###  <a name="basic-transact-sql-restore-syntax"></a><a name="TsqlSyntax"></a> <span data-ttu-id="1e8cf-140">Sintassi Transact-SQL di base per RESTORE</span><span class="sxs-lookup"><span data-stu-id="1e8cf-140">Basic Transact-SQL RESTORE Syntax</span></span>  
 <span data-ttu-id="1e8cf-141">La sintassi di base [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql)[!INCLUDE[tsql](../../includes/tsql-md.md)] per la sequenza di ripristino nell'illustrazione precedente è la seguente:</span><span class="sxs-lookup"><span data-stu-id="1e8cf-141">The basic [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql)[!INCLUDE[tsql](../../includes/tsql-md.md)] syntax for the restore sequence in the preceding illustration is as follows:</span></span>  
  
1.  <span data-ttu-id="1e8cf-142">RESTORE DATABASE *database* FROM *full database backup* WITH NORECOVERY;</span><span class="sxs-lookup"><span data-stu-id="1e8cf-142">RESTORE DATABASE *database* FROM *full database backup* WITH NORECOVERY;</span></span>  
  
2.  <span data-ttu-id="1e8cf-143">RESTORE DATABASE *database* FROM *backup_differenziale_completo* WITH NORECOVERY;</span><span class="sxs-lookup"><span data-stu-id="1e8cf-143">RESTORE DATABASE *database* FROM *full_differential_backup* WITH NORECOVERY;</span></span>  
  
3.  <span data-ttu-id="1e8cf-144">RESTORE LOG *database* FROM *backup_log* WITH NORECOVERY;</span><span class="sxs-lookup"><span data-stu-id="1e8cf-144">RESTORE LOG *database* FROM *log_backup* WITH NORECOVERY;</span></span>  
  
     <span data-ttu-id="1e8cf-145">Ripetere questo passaggio di ripristino del log per ogni ulteriore backup del log.</span><span class="sxs-lookup"><span data-stu-id="1e8cf-145">Repeat this restore-log step for each additional log backup.</span></span>  
  
4.  <span data-ttu-id="1e8cf-146">RESTORE DATABASE *database* WITH RECOVERY;</span><span class="sxs-lookup"><span data-stu-id="1e8cf-146">RESTORE DATABASE *database* WITH RECOVERY;</span></span>  
  
###  <a name="example-recovering-to-the-point-of-failure-transact-sql"></a><a name="ExampleToPoFTsql"></a> <span data-ttu-id="1e8cf-147">Esempio: ripristino fino al momento dell'errore (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="1e8cf-147">Example: Recovering to the Point of Failure (Transact-SQL)</span></span>  
 <span data-ttu-id="1e8cf-148">Nell'esempio [!INCLUDE[tsql](../../includes/tsql-md.md)] seguente vengono illustrate le opzioni fondamentali di una sequenza di ripristino del database fino al momento dell'errore.</span><span class="sxs-lookup"><span data-stu-id="1e8cf-148">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] example shows the essential options in a restore sequence that restores the database to the point of failure.</span></span> <span data-ttu-id="1e8cf-149">Nell'esempio viene creato un backup della parte finale del log del database.</span><span class="sxs-lookup"><span data-stu-id="1e8cf-149">The example creates a tail-log backup of the database.</span></span> <span data-ttu-id="1e8cf-150">Vengono quindi ripristinati un backup completo del database e un backup del log, quindi il backup della parte finale del log.</span><span class="sxs-lookup"><span data-stu-id="1e8cf-150">Next, the example restores a full database backup and log backup and then restores the tail-log backup.</span></span> <span data-ttu-id="1e8cf-151">Il database viene infine recuperato in un passaggio finale separato.</span><span class="sxs-lookup"><span data-stu-id="1e8cf-151">The example recovers the database in a separate, final step.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1e8cf-152">Questo esempio u un backup del database e un backup del log creati nella sezione "Backup del database nel modello di recupero con registrazione completa" di [Backup completo del database &#40;SQL Server&#41;](full-database-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="1e8cf-152">This example uses a database backup and log backup that is created in the "Using Database Backups Under the Full Recovery Model" section in [Full Database Backups &#40;SQL Server&#41;](full-database-backups-sql-server.md).</span></span> <span data-ttu-id="1e8cf-153">Il database di esempio [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] è stato impostato per l'utilizzo del modello di recupero con registrazione completa prima del backup del database.</span><span class="sxs-lookup"><span data-stu-id="1e8cf-153">Before the database backup, the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database was set to use the full recovery model.</span></span>  
  
```  
USE master;  
--Create tail-log backup.  
BACKUP LOG AdventureWorks2012   
TO DISK = 'Z:\SQLServerBackups\AdventureWorksFullRM.bak'    
   WITH NORECOVERY;   
GO  
--Restore the full database backup (from backup set 1).  
RESTORE DATABASE AdventureWorks2012   
  FROM DISK = 'Z:\SQLServerBackups\AdventureWorksFullRM.bak'   
  WITH FILE=1,   
    NORECOVERY;  
  
--Restore the regular log backup (from backup set 2).  
RESTORE LOG AdventureWorks2012   
  FROM DISK = 'Z:\SQLServerBackups\AdventureWorksFullRM.bak'   
  WITH FILE=2,   
    NORECOVERY;  
  
--Restore the tail-log backup (from backup set 3).  
RESTORE LOG AdventureWorks2012   
  FROM DISK = 'Z:\SQLServerBackups\AdventureWorksFullRM.bak'  
  WITH FILE=3,   
    NORECOVERY;  
GO  
--recover the database:  
RESTORE DATABASE AdventureWorks2012 WITH RECOVERY;  
GO  
```  
  
##  <a name="restoring-a-database-to-a-point-within-a-log-backup"></a><a name="PointWithinBackup"></a> <span data-ttu-id="1e8cf-154">Ripristino di un database fino a un punto all'interno di un backup del log</span><span class="sxs-lookup"><span data-stu-id="1e8cf-154">Restoring a Database to a Point Within a Log Backup</span></span>  
 <span data-ttu-id="1e8cf-155">Nel modello di recupero con registrazione completa, un ripristino del database completo può essere generalmente recuperato in un punto nel tempo, in una transazione contrassegnata o in un LSN all'interno di un backup del log.</span><span class="sxs-lookup"><span data-stu-id="1e8cf-155">Under the full recovery model, a complete database restore can usually be recovered to a point of time, a marked transaction, or an LSN within a log backup.</span></span> <span data-ttu-id="1e8cf-156">Quando si utilizza il modello di recupero con registrazione minima delle operazioni bulk, se il backup del log contiene modifiche con registrazione minima delle operazioni bulk, il recupero temporizzato non è tuttavia possibile.</span><span class="sxs-lookup"><span data-stu-id="1e8cf-156">However, under the bulk-logged recovery model, if the log backup contains bulk-logged changes, point-in-time recovery is not possible.</span></span>  
  
### <a name="sample-point-in-time-restore-scenarios"></a><span data-ttu-id="1e8cf-157">Scenari di ripristino temporizzato di esempio</span><span class="sxs-lookup"><span data-stu-id="1e8cf-157">Sample Point-in-Time Restore Scenarios</span></span>  
 <span data-ttu-id="1e8cf-158">Nell'esempio seguente viene illustrato un sistema di database di importanza critica per le strategie aziendali per il quale è necessaria la creazione di un backup completo del database ogni notte a mezzanotte, di un backup differenziale del database ogni ora da lunedì a sabato e di backup del log delle transazioni ogni 10 minuti per tutto il giorno.</span><span class="sxs-lookup"><span data-stu-id="1e8cf-158">The following example assumes a mission-critical database system for which a full database backup is created daily at midnight, a differential database backup is created on the hour, Monday through Saturday, and transaction log backups are created every 10 minutes throughout the day.</span></span> <span data-ttu-id="1e8cf-159">Per ripristinare lo stato in cui si trovava il database alle 05.19</span><span class="sxs-lookup"><span data-stu-id="1e8cf-159">To restore the database to the state is was in at 5:19 A.M.</span></span> <span data-ttu-id="1e8cf-160">di mercoledì, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1e8cf-160">Wednesday, do the following:</span></span>  
  
1.  <span data-ttu-id="1e8cf-161">Ripristinare il backup completo del database creato martedì a mezzanotte.</span><span class="sxs-lookup"><span data-stu-id="1e8cf-161">Restore the full database backup that was created Tuesday at midnight.</span></span>  
  
2.  <span data-ttu-id="1e8cf-162">Ripristinare il backup differenziale del database creato alle 5:00</span><span class="sxs-lookup"><span data-stu-id="1e8cf-162">Restore the differential database backup that was created at 5:00 A.M.</span></span> <span data-ttu-id="1e8cf-163">di mercoledì.</span><span class="sxs-lookup"><span data-stu-id="1e8cf-163">on Wednesday.</span></span>  
  
3.  <span data-ttu-id="1e8cf-164">Applicare il backup del log delle transazioni creato alle 5:10</span><span class="sxs-lookup"><span data-stu-id="1e8cf-164">Apply the transaction log backup that was created at 5:10 A.M.</span></span> <span data-ttu-id="1e8cf-165">di mercoledì.</span><span class="sxs-lookup"><span data-stu-id="1e8cf-165">on Wednesday.</span></span>  
  
4.  <span data-ttu-id="1e8cf-166">Applicare il backup del log delle transazioni creato alle 05.20</span><span class="sxs-lookup"><span data-stu-id="1e8cf-166">Apply the transaction log backup that was created 5:20 A.M.</span></span> <span data-ttu-id="1e8cf-167">di mercoledì, specificando che il processo di recupero si applica solo alle transazioni avvenute prima delle 05.19.</span><span class="sxs-lookup"><span data-stu-id="1e8cf-167">on Wednesday, specifying that the recovery process applies only to transactions that occurred before 5:19 A.M.</span></span>  
  
 <span data-ttu-id="1e8cf-168">In alternativa, se è necessario ripristinare lo stato del database alle 03.04</span><span class="sxs-lookup"><span data-stu-id="1e8cf-168">Alternatively, if the database needs to be restored to its state at 3:04 A.M.</span></span> <span data-ttu-id="1e8cf-169">di giovedì, ma il backup differenziale del database creato alle 03.00</span><span class="sxs-lookup"><span data-stu-id="1e8cf-169">Thursday, but the differential database backup that was created at 3:00 A.M.</span></span> <span data-ttu-id="1e8cf-170">di giovedì non è disponibile, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1e8cf-170">Thursday is unavailable, do the following:</span></span>  
  
1.  <span data-ttu-id="1e8cf-171">Ripristinare il backup del database creato mercoledì a mezzanotte.</span><span class="sxs-lookup"><span data-stu-id="1e8cf-171">Restore the database backup that was created Wednesday at midnight.</span></span>  
  
2.  <span data-ttu-id="1e8cf-172">Ripristinare il backup differenziale del database creato alle 02.00</span><span class="sxs-lookup"><span data-stu-id="1e8cf-172">Restore the differential database backup that was created at 2:00 A.M.</span></span> <span data-ttu-id="1e8cf-173">di giovedì.</span><span class="sxs-lookup"><span data-stu-id="1e8cf-173">on Thursday.</span></span>  
  
3.  <span data-ttu-id="1e8cf-174">Applicare tutti i backup del log delle transazioni creati dalle 02.10</span><span class="sxs-lookup"><span data-stu-id="1e8cf-174">Apply all the transaction log backups created from 2:10 A.M.</span></span> <span data-ttu-id="1e8cf-175">alle 3:00</span><span class="sxs-lookup"><span data-stu-id="1e8cf-175">to 3:00 A.M.</span></span> <span data-ttu-id="1e8cf-176">di giovedì.</span><span class="sxs-lookup"><span data-stu-id="1e8cf-176">on Thursday.</span></span>  
  
4.  <span data-ttu-id="1e8cf-177">Applicare il backup del log delle transazioni creato alle 03.10</span><span class="sxs-lookup"><span data-stu-id="1e8cf-177">Apply the transaction log backup that was created at 3:10 A.M.</span></span> <span data-ttu-id="1e8cf-178">di giovedì, arrestando il processo di recupero alle 3:04.</span><span class="sxs-lookup"><span data-stu-id="1e8cf-178">on Thursday, stopping the recovery process at 3:04 A.M.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1e8cf-179">Per un esempio di ripristino temporizzato, vedere [Ripristinare un database di SQL Server fino a un punto specifico &#40;modello di recupero con registrazione completa&#41;](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md).</span><span class="sxs-lookup"><span data-stu-id="1e8cf-179">For an example of a point-in-time restore, see [Restore a SQL Server Database to a Point in Time &#40;Full Recovery Model&#41;](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="1e8cf-180">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="1e8cf-180">Related Tasks</span></span>  
 <span data-ttu-id="1e8cf-181">**Per ripristinare un backup completo del database**</span><span class="sxs-lookup"><span data-stu-id="1e8cf-181">**To restore a full database backup**</span></span>  
  
-   [<span data-ttu-id="1e8cf-182">Ripristinare un backup del database &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="1e8cf-182">Restore a Database Backup &#40;SQL Server Management Studio&#41;</span></span>](restore-a-database-backup-using-ssms.md)  
  
-   [<span data-ttu-id="1e8cf-183">Ripristinare un database in una nuova posizione &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="1e8cf-183">Restore a Database to a New Location &#40;SQL Server&#41;</span></span>](restore-a-database-to-a-new-location-sql-server.md)  
  
 <span data-ttu-id="1e8cf-184">**Per ripristinare un backup differenziale del database**</span><span class="sxs-lookup"><span data-stu-id="1e8cf-184">**To restore a differential database backup**</span></span>  
  
-   [<span data-ttu-id="1e8cf-185">Ripristinare un backup differenziale del database &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="1e8cf-185">Restore a Differential Database Backup &#40;SQL Server&#41;</span></span>](restore-a-differential-database-backup-sql-server.md)  
  
 <span data-ttu-id="1e8cf-186">**Per ripristinare un backup del log delle transazioni**</span><span class="sxs-lookup"><span data-stu-id="1e8cf-186">**To restore a transaction log backup**</span></span>  
  
-   [<span data-ttu-id="1e8cf-187">Ripristinare un backup del log delle transazioni &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="1e8cf-187">Restore a Transaction Log Backup &#40;SQL Server&#41;</span></span>](restore-a-transaction-log-backup-sql-server.md)  
  
 <span data-ttu-id="1e8cf-188">**Per ripristinare un backup utilizzando SMO (SQL Server Management Objects)**</span><span class="sxs-lookup"><span data-stu-id="1e8cf-188">**To restore a backup by using SQL Server Management Objects (SMO)**</span></span>  
  
-   <xref:Microsoft.SqlServer.Management.Smo.Restore.SqlRestore%2A>  
  
 <span data-ttu-id="1e8cf-189">**Per ripristinare un database fino a un punto all'interno di un backup del log**</span><span class="sxs-lookup"><span data-stu-id="1e8cf-189">**To restore a database to a point within a log backup**</span></span>  
  
-   [<span data-ttu-id="1e8cf-190">Ripristinare un database di SQL Server fino a un punto specifico &#40;modello di recupero con registrazione completa&#41;</span><span class="sxs-lookup"><span data-stu-id="1e8cf-190">Restore a SQL Server Database to a Point in Time &#40;Full Recovery Model&#41;</span></span>](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md)  
  
-   [<span data-ttu-id="1e8cf-191">Recupero di database correlati che contengono transazioni contrassegnate</span><span class="sxs-lookup"><span data-stu-id="1e8cf-191">Recovery of Related  Databases That Contain Marked Transaction</span></span>](recovery-of-related-databases-that-contain-marked-transaction.md)  
  
-   [<span data-ttu-id="1e8cf-192">Recupero fino a un numero di sequenza del file di log &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="1e8cf-192">Recover to a Log Sequence Number &#40;SQL Server&#41;</span></span>](recover-to-a-log-sequence-number-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="1e8cf-193">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1e8cf-193">See Also</span></span>  
 <span data-ttu-id="1e8cf-194">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1e8cf-194">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 <span data-ttu-id="1e8cf-195">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1e8cf-195">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="1e8cf-196">[Applicare backup del log delle transazioni &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="1e8cf-196">[Apply Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span></span>  
 <span data-ttu-id="1e8cf-197">[sp_addumpdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1e8cf-197">[sp_addumpdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) </span></span>  
 <span data-ttu-id="1e8cf-198">[Backup completo del database &#40;SQL Server&#41;](full-database-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="1e8cf-198">[Full Database Backups &#40;SQL Server&#41;](full-database-backups-sql-server.md) </span></span>  
 <span data-ttu-id="1e8cf-199">[Backup differenziali &#40;SQL Server&#41;](differential-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="1e8cf-199">[Differential Backups &#40;SQL Server&#41;](differential-backups-sql-server.md) </span></span>  
 <span data-ttu-id="1e8cf-200">[Panoramica del backup &#40;SQL Server&#41;](backup-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="1e8cf-200">[Backup Overview &#40;SQL Server&#41;](backup-overview-sql-server.md) </span></span>  
 [<span data-ttu-id="1e8cf-201">Panoramica del ripristino e del recupero &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="1e8cf-201">Restore and Recovery Overview &#40;SQL Server&#41;</span></span>](restore-and-recovery-overview-sql-server.md)  
  
  
