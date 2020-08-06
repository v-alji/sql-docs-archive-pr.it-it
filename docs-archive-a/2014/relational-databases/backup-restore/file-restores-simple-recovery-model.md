---
title: Ripristini di file (modello di recupero con registrazione minima) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- file restores [SQL Server]
- simple recovery model [SQL Server]
- restoring files [SQL Server], Transact-SQL restore sequence
- restoring files [SQL Server]
- Transact-SQL restore sequence
- restoring files [SQL Server], simple recovery model
- file restores [SQL Server], simple recovery model
- file restores [SQL Server], Transact-SQL restore sequence
ms.assetid: b6d07386-7c6f-4cc6-be32-93289adbd3d6
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2ed48f48f531e727de5d6e1403ef47f5399f874d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715440"
---
# <a name="file-restores-simple-recovery-model"></a><span data-ttu-id="e49c0-102">Ripristini di file (modello di recupero con registrazione minima)</span><span class="sxs-lookup"><span data-stu-id="e49c0-102">File Restores (Simple Recovery Model)</span></span>
  <span data-ttu-id="e49c0-103">Le informazioni contenute in questo argomento sono rilevanti solo per i database che utilizzano il modello di recupero con registrazione minima e includono almeno un filegroup secondario di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="e49c0-103">This topic is relevant only for simple-model databases that contain at least one read-only secondary filegroup.</span></span>  
  
 <span data-ttu-id="e49c0-104">L'obiettivo di un ripristino di file consiste nel ripristinare uno o più file danneggiati senza ripristinare l'intero database.</span><span class="sxs-lookup"><span data-stu-id="e49c0-104">In a file restore, the goal is to restore one or more damaged files without restoring the whole database.</span></span> <span data-ttu-id="e49c0-105">In base al modello di recupero con registrazione minima, i backup di file sono supportati solo per i file di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="e49c0-105">Under the simple recovery model, file backups are supported only for read-only files.</span></span> <span data-ttu-id="e49c0-106">Il filegroup primario e i filegroup secondari di lettura/scrittura vengono sempre ripristinati insieme attraverso il ripristino di un backup del database o di un backup parziale.</span><span class="sxs-lookup"><span data-stu-id="e49c0-106">The primary filegroup and read/write secondary filegroups are always restored together, by restoring a database or partial backup.</span></span>  
  
 <span data-ttu-id="e49c0-107">Gli scenari di ripristino dei file sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="e49c0-107">The file-restore scenarios are as follows:</span></span>  
  
-   <span data-ttu-id="e49c0-108">Ripristino di file offline</span><span class="sxs-lookup"><span data-stu-id="e49c0-108">Offline file restore</span></span>  
  
     <span data-ttu-id="e49c0-109">In un *ripristino di file offline*, i file o i filegroup danneggiati vengono ripristinati mentre il database è offline.</span><span class="sxs-lookup"><span data-stu-id="e49c0-109">In an *offline file restore*, the database is offline while damaged files or filegroups are restored.</span></span> <span data-ttu-id="e49c0-110">Al termine della sequenza di ripristino, il database torna online.</span><span class="sxs-lookup"><span data-stu-id="e49c0-110">At the end of the restore sequence, the database comes online.</span></span>  
  
     <span data-ttu-id="e49c0-111">Tutte le edizioni di [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] supportano il ripristino di file offline.</span><span class="sxs-lookup"><span data-stu-id="e49c0-111">All editions of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] support offline file restore.</span></span>  
  
-   <span data-ttu-id="e49c0-112">Ripristino di file online</span><span class="sxs-lookup"><span data-stu-id="e49c0-112">Online file restore</span></span>  
  
     <span data-ttu-id="e49c0-113">In un *ripristino di file offline*, se il database è online al momento del ripristino, rimarrà online durante il ripristino del file.</span><span class="sxs-lookup"><span data-stu-id="e49c0-113">In an *online file restore*, if database is online at restore time, it remains online during the file restore.</span></span> <span data-ttu-id="e49c0-114">Tuttavia, durante l'operazione di ripristino, ogni filegroup nel quale viene ripristinato un file rimane offline.</span><span class="sxs-lookup"><span data-stu-id="e49c0-114">However, each filegroup in which a file is being restored is offline during the restore operation.</span></span> <span data-ttu-id="e49c0-115">Al termine del recupero di tutti i file del filegroup offline, viene attivata automaticamente la modalità online per il filegroup.</span><span class="sxs-lookup"><span data-stu-id="e49c0-115">After all the files in an offline filegroup are recovered, the filegroup is automatically brought online.</span></span>  
  
     <span data-ttu-id="e49c0-116">Per informazioni sul supporto per il ripristino di pagine e file online, vedere [Funzionalità supportate dalle edizioni di SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="e49c0-116">For information about support for online page and file restore, see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span> <span data-ttu-id="e49c0-117">Per altre informazioni sui ripristini online, vedere [Ripristino in linea &#40;SQL Server&#41;](online-restore-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="e49c0-117">For more information about online restores, see [Online Restore &#40;SQL Server&#41;](online-restore-sql-server.md).</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="e49c0-118">Se si desidera attivare la modalità offline per il database per eseguire un ripristino di file, eseguire l'istruzione [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-options) seguente prima di avviare la sequenza di ripristino: ALTER DATABASE *database_name* SET OFFLINE.</span><span class="sxs-lookup"><span data-stu-id="e49c0-118">If you want the database to be offline for a file restore, take the database offline before you start the restore sequence by executing the following [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-options) statement: ALTER DATABASE *database_name* SET OFFLINE.</span></span>  
  

  
##  <a name="overview-of-file-and-filegroup-restore-under-the-simple-recovery-model"></a><a name="Overview"></a> <span data-ttu-id="e49c0-119">Panoramica del ripristino di file e filegroup nel modello di recupero con registrazione minima</span><span class="sxs-lookup"><span data-stu-id="e49c0-119">Overview of File and Filegroup Restore Under the Simple Recovery Model</span></span>  
 <span data-ttu-id="e49c0-120">Uno scenario di ripristino di file consiste in un'unica sequenza di ripristino che consente di eseguire la copia, il rollforward e il recupero dei dati appropriati come descritto di seguito:</span><span class="sxs-lookup"><span data-stu-id="e49c0-120">A file restore scenario consists of a single restore sequence that copies, rolls forward, and recovers the appropriate data as follows:</span></span>  
  
1.  <span data-ttu-id="e49c0-121">Ripristinare ogni file danneggiato dal backup di file più recente.</span><span class="sxs-lookup"><span data-stu-id="e49c0-121">Restore each damaged file from its most recent file backup.</span></span>  
  
2.  <span data-ttu-id="e49c0-122">Ripristinare il backup differenziale di file più recente per ogni file ripristinato e recuperare il database.</span><span class="sxs-lookup"><span data-stu-id="e49c0-122">Restore the most recent differential file backup for each restored file and recover the database.</span></span>  
  
### <a name="transact-sql-steps-for-file-restore-sequence-simple-recovery-model"></a><span data-ttu-id="e49c0-123">Passaggi di Transact-SQL per la sequenza di ripristino di file (modello di recupero con registrazione minima)</span><span class="sxs-lookup"><span data-stu-id="e49c0-123">Transact-SQL Steps for File Restore Sequence (Simple Recovery Model)</span></span>  
 <span data-ttu-id="e49c0-124">Questa sezione descrive le opzioni [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) essenziali di [!INCLUDE[tsql](../../../includes/tsql-md.md)] per una semplice sequenza di ripristino di file.</span><span class="sxs-lookup"><span data-stu-id="e49c0-124">This section shows the essential [!INCLUDE[tsql](../../../includes/tsql-md.md)][RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) options for a simple file-restore sequence.</span></span> <span data-ttu-id="e49c0-125">La sintassi e i dettagli non rilevanti sono stati omessi.</span><span class="sxs-lookup"><span data-stu-id="e49c0-125">Syntax and details that are not relevant to this purpose are omitted.</span></span>  
  
 <span data-ttu-id="e49c0-126">La sequenza di ripristino contiene solo due istruzioni [!INCLUDE[tsql](../../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e49c0-126">The restore sequence contains only two [!INCLUDE[tsql](../../../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="e49c0-127">La prima istruzione esegue il ripristino di un file secondario, il file `A`, che viene ripristinato utilizzando WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="e49c0-127">The first statement restores a secondary file, file `A`, which is restored using WITH NORECOVERY.</span></span> <span data-ttu-id="e49c0-128">La seconda operazione ripristina altri due file, i file `B` e `C` , che vengono ripristinati utilizzando WITH RECOVERY da un diverso dispositivo di backup:</span><span class="sxs-lookup"><span data-stu-id="e49c0-128">The second operation restores two other files, `B` and `C` which are restored using WITH RECOVERY from a different backup device:</span></span>  
  
1.  <span data-ttu-id="e49c0-129">RESTORE DATABASE *database* FILE **=** _nome_file_A_</span><span class="sxs-lookup"><span data-stu-id="e49c0-129">RESTORE DATABASE *database* FILE **=**_name_of_file_A_</span></span>  
  
     <span data-ttu-id="e49c0-130">FROM *backup_file_A*</span><span class="sxs-lookup"><span data-stu-id="e49c0-130">FROM *file_backup_of_file_A*</span></span>  
  
     <span data-ttu-id="e49c0-131">WITH NORECOVERY **;**</span><span class="sxs-lookup"><span data-stu-id="e49c0-131">WITH NORECOVERY **;**</span></span>  
  
2.  <span data-ttu-id="e49c0-132">RESTORE DATABASE *database* FILE **=** _nome_file_B_ **,** _nome_file_C_</span><span class="sxs-lookup"><span data-stu-id="e49c0-132">RESTORE DATABASE *database* FILE **=**_name_of_file_B_**,**_name_of_file_C_</span></span>  
  
     <span data-ttu-id="e49c0-133">FROM *backup_dei_file_B_e_C*</span><span class="sxs-lookup"><span data-stu-id="e49c0-133">FROM *file_backup_of_files_B_and_C*</span></span>  
  
     <span data-ttu-id="e49c0-134">WITH RECOVERY **;**</span><span class="sxs-lookup"><span data-stu-id="e49c0-134">WITH RECOVERY **;**</span></span>  
  
### <a name="examples"></a><span data-ttu-id="e49c0-135">Esempi</span><span class="sxs-lookup"><span data-stu-id="e49c0-135">Examples</span></span>  
  
-   [<span data-ttu-id="e49c0-136">Esempio: Ripristino online di un file di sola lettura &#40;Modello di recupero con registrazione minima&#41;</span><span class="sxs-lookup"><span data-stu-id="e49c0-136">Example: Online Restore of a Read-Only File &#40;Simple Recovery Model&#41;</span></span>](example-online-restore-of-a-read-only-file-simple-recovery-model.md)  
  
-   [<span data-ttu-id="e49c0-137">Esempio: Ripristino offline del filegroup primario e di un altro filegroup &#40;Modello di recupero con registrazione completa&#41;</span><span class="sxs-lookup"><span data-stu-id="e49c0-137">Example: Offline Restore of Primary and One Other Filegroup &#40;Full Recovery Model&#41;</span></span>](example-offline-restore-of-primary-and-one-other-filegroup-full-recovery-model.md)  
  
 
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="e49c0-138">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="e49c0-138">Related Tasks</span></span>  
 <span data-ttu-id="e49c0-139">**Per ripristinare file e filegroup**</span><span class="sxs-lookup"><span data-stu-id="e49c0-139">**To restore files and filegroups**</span></span>  
  
-   [<span data-ttu-id="e49c0-140">Ripristinare file e filegroup sovrascrivendo file esistenti &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e49c0-140">Restore Files and Filegroups over Existing Files &#40;SQL Server&#41;</span></span>](restore-files-and-filegroups-over-existing-files-sql-server.md)  
  
-   [<span data-ttu-id="e49c0-141">Ripristino di file e filegroup &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e49c0-141">Restore Files and Filegroups &#40;SQL Server&#41;</span></span>](restore-files-and-filegroups-sql-server.md)  
  
-   [<span data-ttu-id="e49c0-142">Ripristino di file e filegroup &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e49c0-142">Restore Files and Filegroups &#40;SQL Server&#41;</span></span>](restore-files-and-filegroups-sql-server.md)  
  
-   <span data-ttu-id="e49c0-143"><xref:Microsoft.SqlServer.Management.Smo.Restore.SqlRestore%2A> (SMO)</span><span class="sxs-lookup"><span data-stu-id="e49c0-143"><xref:Microsoft.SqlServer.Management.Smo.Restore.SqlRestore%2A> (SMO)</span></span>  
  
  
  
## <a name="see-also"></a><span data-ttu-id="e49c0-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e49c0-144">See Also</span></span>  
 <span data-ttu-id="e49c0-145">[Backup e ripristino: interoperabilità e coesistenza &#40;SQL Server&#41;](backup-and-restore-interoperability-and-coexistence-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="e49c0-145">[Backup and Restore: Interoperability and Coexistence &#40;SQL Server&#41;](backup-and-restore-interoperability-and-coexistence-sql-server.md) </span></span>  
 <span data-ttu-id="e49c0-146">[Backup differenziali &#40;SQL Server&#41;](differential-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="e49c0-146">[Differential Backups &#40;SQL Server&#41;](differential-backups-sql-server.md) </span></span>  
 <span data-ttu-id="e49c0-147">[Backup completi del file &#40;SQL Server&#41;](full-file-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="e49c0-147">[Full File Backups &#40;SQL Server&#41;](full-file-backups-sql-server.md) </span></span>  
 <span data-ttu-id="e49c0-148">[Panoramica del backup &#40;SQL Server&#41;](backup-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="e49c0-148">[Backup Overview &#40;SQL Server&#41;](backup-overview-sql-server.md) </span></span>  
 <span data-ttu-id="e49c0-149">[Panoramica del ripristino e del recupero &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="e49c0-149">[Restore and Recovery Overview &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md) </span></span>  
 <span data-ttu-id="e49c0-150">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e49c0-150">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 <span data-ttu-id="e49c0-151">[Ripristini di database completi &#40;modello di recupero con registrazione minima&#41;](complete-database-restores-simple-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="e49c0-151">[Complete Database Restores &#40;Simple Recovery Model&#41;](complete-database-restores-simple-recovery-model.md) </span></span>  
 [<span data-ttu-id="e49c0-152">Ripristini a fasi &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e49c0-152">Piecemeal Restores &#40;SQL Server&#41;</span></span>](piecemeal-restores-sql-server.md)  
  
  
