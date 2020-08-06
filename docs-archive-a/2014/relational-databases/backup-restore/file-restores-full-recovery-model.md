---
title: Ripristini di file (modello di recupero con registrazione completa) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- file restores [SQL Server]
- full recovery model [SQL Server], performing restores
- restoring files [SQL Server], Transact-SQL restore sequence
- restoring files [SQL Server]
- file restores [SQL Server], full recovery model
- restoring files [SQL Server], full recovery model
- Transact-SQL restore sequence
- file restores [SQL Server], Transact-SQL restore sequence
ms.assetid: d2236a2a-4cf1-4c3f-b542-f73f6096e15c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 488515ec900867f13d33580402e36a3f98747bb2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715443"
---
# <a name="file-restores-full-recovery-model"></a><span data-ttu-id="90ab3-102">Ripristini di file (modello di recupero con registrazione completa)</span><span class="sxs-lookup"><span data-stu-id="90ab3-102">File Restores (Full Recovery Model)</span></span>
  <span data-ttu-id="90ab3-103">Le informazioni in questo argomento sono rilevanti solo per i database che contengono più file o filegroup e che utilizzano il modello di recupero con registrazione completa o con registrazione minima delle operazioni bulk.</span><span class="sxs-lookup"><span data-stu-id="90ab3-103">This topic is relevant only for databases that contain multiple files or filegroups under the full or bulk-load recovery model.</span></span>  
  
 <span data-ttu-id="90ab3-104">L'obiettivo di un ripristino di file consiste nel ripristinare uno o più file danneggiati senza ripristinare l'intero database.</span><span class="sxs-lookup"><span data-stu-id="90ab3-104">In a file restore, the goal is to restore one or more damaged files without restoring the whole database.</span></span> <span data-ttu-id="90ab3-105">Uno scenario di ripristino di file consiste in un'unica sequenza di ripristino in cui vengono eseguiti la copia, il rollforward e il recupero dei dati appropriati.</span><span class="sxs-lookup"><span data-stu-id="90ab3-105">A file restore scenario consists of a single restore sequence that copies, rolls forward, and recovers the appropriate data</span></span>  
  
 <span data-ttu-id="90ab3-106">Se il filegroup in fase di ripristino è di lettura/scrittura, è necessario applicare una catena non interrotta di backup del log dopo il ripristino degli ultimi dati o del backup differenziale</span><span class="sxs-lookup"><span data-stu-id="90ab3-106">If the filegroup that is being restored is read/write, an unbroken chain of log backups must be applied after the last data or differential backup is restored.</span></span> <span data-ttu-id="90ab3-107">per portare il filegroup fino ai record di log inclusi nei record di log attivi correnti del file di log.</span><span class="sxs-lookup"><span data-stu-id="90ab3-107">This brings the filegroup forward to the log records in the current active log records in the log file.</span></span> <span data-ttu-id="90ab3-108">Il punto di recupero si trova in genere, ma non necessariamente, verso la fine del log.</span><span class="sxs-lookup"><span data-stu-id="90ab3-108">The recovery point is typically near the end of log, but not necessarily.</span></span>  
  
 <span data-ttu-id="90ab3-109">Se il filegroup in fase di ripristino è di sola lettura, l'applicazione di backup del log in genere non è necessaria e viene ignorata.</span><span class="sxs-lookup"><span data-stu-id="90ab3-109">If the filegroup that is being restored is read-only, usually applying log backups is unnecessary and is skipped.</span></span> <span data-ttu-id="90ab3-110">Se il backup è stato creato dopo l'impostazione del file in modalità di sola lettura, esso verrà ripristinato per ultimo.</span><span class="sxs-lookup"><span data-stu-id="90ab3-110">If the backup was taken after the file became read-only, that is the last backup to restore.</span></span> <span data-ttu-id="90ab3-111">Il rollforward viene arrestato in corrispondenza del punto di destinazione.</span><span class="sxs-lookup"><span data-stu-id="90ab3-111">Roll forward stops at the target point.</span></span>  
  
 <span data-ttu-id="90ab3-112">Gli scenari di ripristino dei file sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="90ab3-112">The file-restore scenarios are as follows:</span></span>  
  
-   <span data-ttu-id="90ab3-113">Ripristino di file offline</span><span class="sxs-lookup"><span data-stu-id="90ab3-113">Offline file restore</span></span>  
  
     <span data-ttu-id="90ab3-114">In un *ripristino di file offline*, i file o i filegroup danneggiati vengono ripristinati mentre il database è offline.</span><span class="sxs-lookup"><span data-stu-id="90ab3-114">In an *offline file restore*, the database is offline while damaged files or filegroups are restored.</span></span> <span data-ttu-id="90ab3-115">Al termine della sequenza di ripristino, il database torna online.</span><span class="sxs-lookup"><span data-stu-id="90ab3-115">At the end of the restore sequence, the database comes online.</span></span>  
  
     <span data-ttu-id="90ab3-116">Tutte le edizioni di [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] supportano il ripristino di file offline.</span><span class="sxs-lookup"><span data-stu-id="90ab3-116">All editions of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] support offline file restore.</span></span>  
  
-   <span data-ttu-id="90ab3-117">Ripristino di file online</span><span class="sxs-lookup"><span data-stu-id="90ab3-117">Online file restore</span></span>  
  
     <span data-ttu-id="90ab3-118">In un *ripristino di file offline*, se il database è online al momento del ripristino, rimarrà online durante il ripristino del file.</span><span class="sxs-lookup"><span data-stu-id="90ab3-118">In an *online file restore*, if database is online at restore time, it remains online during the file restore.</span></span> <span data-ttu-id="90ab3-119">Tuttavia, durante l'operazione di ripristino, ogni filegroup nel quale viene ripristinato un file rimane offline.</span><span class="sxs-lookup"><span data-stu-id="90ab3-119">However, each filegroup in which a file is being restored is offline during the restore operation.</span></span> <span data-ttu-id="90ab3-120">Al termine del recupero di tutti i file del filegroup offline, viene attivata automaticamente la modalità online per il filegroup.</span><span class="sxs-lookup"><span data-stu-id="90ab3-120">After all the files in an offline filegroup are recovered, the filegroup is automatically brought online.</span></span>  
  
     <span data-ttu-id="90ab3-121">Per informazioni sul supporto per il ripristino di pagine e file online, vedere [Funzionalità supportate dalle edizioni di SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="90ab3-121">For information about support for online page and file restore, see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span> <span data-ttu-id="90ab3-122">Per altre informazioni sui ripristini online, vedere [Ripristino in linea &#40;SQL Server&#41;](online-restore-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="90ab3-122">For more information about online restores, see [Online Restore &#40;SQL Server&#41;](online-restore-sql-server.md).</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="90ab3-123">Se si desidera attivare la modalità offline per il database per eseguire un ripristino di file, eseguire l'istruzione [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-options) seguente prima di avviare la sequenza di ripristino: ALTER DATABASE *database_name* SET OFFLINE.</span><span class="sxs-lookup"><span data-stu-id="90ab3-123">If you want the database to be offline for a file restore, take the database offline before you start the restore sequence by executing the following [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-options) statement: ALTER DATABASE *database_name* SET OFFLINE.</span></span>  
  
  
  
##  <a name="restoring-damaged-files-from-file-backups"></a><a name="Overview"></a> <span data-ttu-id="90ab3-124">Ripristino di file danneggiati da backup di file</span><span class="sxs-lookup"><span data-stu-id="90ab3-124">Restoring Damaged Files from File Backups</span></span>  
  
1.  <span data-ttu-id="90ab3-125">Prima di ripristinare uno o più file danneggiati, tentare di creare un [backup della parte finale del log](tail-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="90ab3-125">Before restoring one or more damaged files, attempt to create a [tail-log backup](tail-log-backups-sql-server.md).</span></span>  
  
     <span data-ttu-id="90ab3-126">Se il log è stato danneggiato e non è possibile creare un backup della parte finale del log, è necessario ripristinare l'intero database.</span><span class="sxs-lookup"><span data-stu-id="90ab3-126">If the log has been damaged, a tail-log backup cannot be created, and you must restore the whole database.</span></span>  
  
     <span data-ttu-id="90ab3-127">Per informazioni sul backup di un log delle transazioni, vedere [Backup di log delle transazioni &#40;SQL Server&#41;](transaction-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="90ab3-127">For information about how to back up a transaction log, see [Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md).</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="90ab3-128">Per un ripristino di file offline, è sempre necessario creare un backup della parte finale del log prima del ripristino del file.</span><span class="sxs-lookup"><span data-stu-id="90ab3-128">For an offline file restore, you must always take a tail-log backup before the file restore.</span></span> <span data-ttu-id="90ab3-129">Per un ripristino di file online, è sempre necessario creare il backup del log dopo il ripristino del file</span><span class="sxs-lookup"><span data-stu-id="90ab3-129">For an online file restore, you must always take the log backup after the file restore.</span></span> <span data-ttu-id="90ab3-130">per fare in modo che il file recuperato si trovi in uno stato consistente con il resto del database.</span><span class="sxs-lookup"><span data-stu-id="90ab3-130">This log backup is necessary to allow for the file to be recovered to a state consistent with the rest of the database.</span></span>  
  
2.  <span data-ttu-id="90ab3-131">Ripristinare ogni file danneggiato dal backup del file più recente.</span><span class="sxs-lookup"><span data-stu-id="90ab3-131">Restore each damaged file from the most recent file backup of that file.</span></span>  
  
3.  <span data-ttu-id="90ab3-132">Ripristinare l'eventuale backup differenziale del file più recente per ogni file ripristinato.</span><span class="sxs-lookup"><span data-stu-id="90ab3-132">Restore the most recent differential file backup, if any, for each restored file.</span></span>  
  
4.  <span data-ttu-id="90ab3-133">Ripristinare i backup del log delle transazioni in sequenza, iniziando con il backup associato al file ripristinato meno recente e terminando con il backup della parte finale del log creato nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="90ab3-133">Restore transaction log backups in sequence, starting with the backup that covers the oldest of the restored files and ending with the tail-log backup created in step 1.</span></span>  
  
     <span data-ttu-id="90ab3-134">È necessario ripristinare tutti i backup del log delle transazioni creati successivamente ai backup di file per assicurare la consistenza del database.</span><span class="sxs-lookup"><span data-stu-id="90ab3-134">You must restore the transaction log backups that were created after the file backups to bring the database to a consistent state.</span></span> <span data-ttu-id="90ab3-135">Il rollforward dei backup del log delle transazioni è un'operazione rapida, in quanto vengono applicate soltanto le modifiche valide per i file ripristinati.</span><span class="sxs-lookup"><span data-stu-id="90ab3-135">The transaction log backups can be rolled forward quickly, because only the changes that apply to the restored files are applied.</span></span> <span data-ttu-id="90ab3-136">Il ripristino di singoli file può offrire risultati migliori rispetto al ripristino dell'intero database poiché i file non danneggiati non vengono copiati e non ne viene eseguito il rollforward.</span><span class="sxs-lookup"><span data-stu-id="90ab3-136">Restoring individual files can be better than restoring the whole database, because undamaged files are not copied and then rolled forward.</span></span> <span data-ttu-id="90ab3-137">Deve comunque essere letta l'intera catena dei backup di log.</span><span class="sxs-lookup"><span data-stu-id="90ab3-137">However, the whole chain of log backups still has to be read.</span></span>  
  
5.  <span data-ttu-id="90ab3-138">Recuperare il database.</span><span class="sxs-lookup"><span data-stu-id="90ab3-138">Recover the database.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="90ab3-139">I backup dei file possono essere utilizzati per ripristinare il database a una temporizzazione precedente.</span><span class="sxs-lookup"><span data-stu-id="90ab3-139">File backups can be used to restore the database to an earlier point in time.</span></span> <span data-ttu-id="90ab3-140">A tale scopo, è necessario ripristinare un set completo di backup dei file e quindi ripristinare i backup del log delle transazioni in sequenza, fino a raggiungere un punto nel tempo successivo al backup di file più recente ripristinato.</span><span class="sxs-lookup"><span data-stu-id="90ab3-140">To do this, you must restore a complete set of file backups, and then restore transaction log backups in sequence to reach a target point that is after the end of the most recent restored file backup.</span></span> <span data-ttu-id="90ab3-141">Per altre informazioni sul recupero temporizzato, vedere [Ripristino di un database di SQL Server fino a un punto specifico all'interno di un backup &#40;modello di recupero con registrazione completa&#41;](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md).</span><span class="sxs-lookup"><span data-stu-id="90ab3-141">For more information about point-in-time recovery, see [Restore a SQL Server Database to a Point in Time &#40;Full Recovery Model&#41;](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md).</span></span>  
  
## <a name="transact-sql-restore-sequence-for-an-offline-file-restore-full-recovery-model"></a><span data-ttu-id="90ab3-142">Sequenza di ripristino Transact-SQL per il ripristino di file offline (modello di recupero con registrazione completa)</span><span class="sxs-lookup"><span data-stu-id="90ab3-142">Transact-SQL Restore Sequence for an Offline File Restore (Full Recovery Model)</span></span>  
 <span data-ttu-id="90ab3-143">Uno scenario di ripristino di file consiste in un'unica sequenza di ripristino in cui vengono eseguiti la copia, il rollforward e il recupero dei dati appropriati.</span><span class="sxs-lookup"><span data-stu-id="90ab3-143">A file restore scenario consists of a single restore sequence that copies, rolls forward, and recovers the appropriate data.</span></span>  
  
 <span data-ttu-id="90ab3-144">In questa sezione vengono illustrate le opzioni [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) essenziali per una sequenza di ripristino di file.</span><span class="sxs-lookup"><span data-stu-id="90ab3-144">This section shows the essential [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) options for a file-restore sequence.</span></span> <span data-ttu-id="90ab3-145">La sintassi e i dettagli non rilevanti sono stati omessi.</span><span class="sxs-lookup"><span data-stu-id="90ab3-145">Syntax and details that are not relevant to this purpose are omitted.</span></span>  
  
 <span data-ttu-id="90ab3-146">Nella sequenza di ripristino dell'esempio seguente viene illustrato un ripristino offline di due file secondari, `A` e `B`mediante WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="90ab3-146">The following sample restore sequence shows an offline restore of two secondary files, `A` and `B`, using WITH NORECOVERY.</span></span> <span data-ttu-id="90ab3-147">Successivamente vengono applicati due backup del log con NORECOVERY, seguiti dal backup della parte finale del log, che viene ripristinato con WITH RECOVERY.</span><span class="sxs-lookup"><span data-stu-id="90ab3-147">Next, two log backups are applied with NORECOVERY, followed with the tail-log backup, and this is restored using WITH RECOVERY.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="90ab3-148">La sequenza di ripristino dell'esempio seguente inizia portando il file offline e quindi creando un backup della parte finale del log.</span><span class="sxs-lookup"><span data-stu-id="90ab3-148">The following sample restore sequence starts by taking the file offline and then creates a tail-log backup.</span></span>  
  
```  
--Take the file offline.  
ALTER DATABASE database_name MODIFY FILE SET OFFLINE;  
-- Back up the currently active transaction log.  
BACKUP LOG database_name  
   TO <tail_log_backup>  
   WITH NORECOVERY;  
GO   
-- Restore the files.  
RESTORE DATABASE database_name FILE=name   
   FROM <file_backup_of_file_A>   
   WITH NORECOVERY;  
RESTORE DATABASE database_name FILE=<name> ......  
   FROM <file_backup_of_file_B>   
   WITH NORECOVERY;  
-- Restore the log backups.  
RESTORE LOG database_name FROM <log_backup>   
   WITH NORECOVERY;  
RESTORE LOG database_name FROM <log_backup>   
   WITH NORECOVERY;  
RESTORE LOG database_name FROM <tail_log_backup>   
   WITH RECOVERY;  
```  
  
## <a name="examples"></a><span data-ttu-id="90ab3-149">Esempi</span><span class="sxs-lookup"><span data-stu-id="90ab3-149">Examples</span></span>  
  
-   [<span data-ttu-id="90ab3-150">Esempio: Ripristino online di un file di lettura/scrittura &#40;modello di recupero con registrazione completa&#41;</span><span class="sxs-lookup"><span data-stu-id="90ab3-150">Example: Online Restore of a Read-Write File &#40;Full Recovery Model&#41;</span></span>](example-online-restore-of-a-read-write-file-full-recovery-model.md)  
  
-   [<span data-ttu-id="90ab3-151">Esempio: Ripristino online di un file di sola lettura &#40;Modello di recupero con registrazione completa&#41;</span><span class="sxs-lookup"><span data-stu-id="90ab3-151">Example: Online Restore of a Read-Only File &#40;Full Recovery Model&#41;</span></span>](example-online-restore-of-a-read-only-file-full-recovery-model.md)  
  
-   [<span data-ttu-id="90ab3-152">Esempio: Ripristino offline del filegroup primario e di un altro filegroup &#40;Modello di recupero con registrazione completa&#41;</span><span class="sxs-lookup"><span data-stu-id="90ab3-152">Example: Offline Restore of Primary and One Other Filegroup &#40;Full Recovery Model&#41;</span></span>](example-offline-restore-of-primary-and-one-other-filegroup-full-recovery-model.md)  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="90ab3-153">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="90ab3-153">Related Tasks</span></span>  
 <span data-ttu-id="90ab3-154">**Per ripristinare file e filegroup**</span><span class="sxs-lookup"><span data-stu-id="90ab3-154">**To restore files and filegroups**</span></span>  
  
-   [<span data-ttu-id="90ab3-155">Ripristino dei file in una nuova posizione &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="90ab3-155">Restore Files to a New Location &#40;SQL Server&#41;</span></span>](restore-files-to-a-new-location-sql-server.md)  
  
-   [<span data-ttu-id="90ab3-156">Ripristino di file e filegroup &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="90ab3-156">Restore Files and Filegroups &#40;SQL Server&#41;</span></span>](restore-files-and-filegroups-sql-server.md)  
  
-   <span data-ttu-id="90ab3-157"><xref:Microsoft.SqlServer.Management.Smo.Restore.SqlRestore%2A> (SMO)</span><span class="sxs-lookup"><span data-stu-id="90ab3-157"><xref:Microsoft.SqlServer.Management.Smo.Restore.SqlRestore%2A> (SMO)</span></span>  
  

  
## <a name="see-also"></a><span data-ttu-id="90ab3-158">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="90ab3-158">See Also</span></span>  
 <span data-ttu-id="90ab3-159">[Backup e ripristino: interoperabilità e coesistenza &#40;SQL Server&#41;](backup-and-restore-interoperability-and-coexistence-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="90ab3-159">[Backup and Restore: Interoperability and Coexistence &#40;SQL Server&#41;](backup-and-restore-interoperability-and-coexistence-sql-server.md) </span></span>  
 <span data-ttu-id="90ab3-160">[Backup differenziali &#40;SQL Server&#41;](differential-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="90ab3-160">[Differential Backups &#40;SQL Server&#41;](differential-backups-sql-server.md) </span></span>  
 <span data-ttu-id="90ab3-161">[Backup completi del file &#40;SQL Server&#41;](full-file-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="90ab3-161">[Full File Backups &#40;SQL Server&#41;](full-file-backups-sql-server.md) </span></span>  
 <span data-ttu-id="90ab3-162">[Panoramica del backup &#40;SQL Server&#41;](backup-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="90ab3-162">[Backup Overview &#40;SQL Server&#41;](backup-overview-sql-server.md) </span></span>  
 <span data-ttu-id="90ab3-163">[Panoramica del ripristino e del recupero &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="90ab3-163">[Restore and Recovery Overview &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md) </span></span>  
 <span data-ttu-id="90ab3-164">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="90ab3-164">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 <span data-ttu-id="90ab3-165">[Ripristini di database completi &#40;modello di recupero con registrazione minima&#41;](complete-database-restores-simple-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="90ab3-165">[Complete Database Restores &#40;Simple Recovery Model&#41;](complete-database-restores-simple-recovery-model.md) </span></span>  
 [<span data-ttu-id="90ab3-166">Ripristini a fasi &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="90ab3-166">Piecemeal Restores &#40;SQL Server&#41;</span></span>](piecemeal-restores-sql-server.md)  
  
  
