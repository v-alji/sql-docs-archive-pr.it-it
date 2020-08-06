---
title: Panoramica del backup (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- tables [SQL Server], backing up data
- backups [SQL Server]
- database backups [SQL Server]
- backup types [SQL Server]
- data backups [SQL Server]
- backing up tables [SQL Server]
- database restores [SQL Server], backups
- backing up [SQL Server], about backing up
- restoring [SQL Server], backup types
- backups [SQL Server], about
- backups [SQL Server], table-level backups unsupported
ms.assetid: 09a6e0c2-d8fd-453f-9aac-4ff24a97dc1f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 60fbd0341c4e29c6f98cc4d5fe5a2cfabc9b703f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637939"
---
# <a name="backup-overview-sql-server"></a><span data-ttu-id="99f13-102">Backup Overview (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="99f13-102">Backup Overview (SQL Server)</span></span>
  <span data-ttu-id="99f13-103">In questo argomento viene presentato il componente di backup di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="99f13-103">This topic introduces the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup component.</span></span> <span data-ttu-id="99f13-104">L'esecuzione dei backup del database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] è essenziale per la protezione dei dati.</span><span class="sxs-lookup"><span data-stu-id="99f13-104">Backing up your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database is essential for protecting your data.</span></span> <span data-ttu-id="99f13-105">In questa discussione vengono analizzati i tipi di backup e le relative restrizioni.</span><span class="sxs-lookup"><span data-stu-id="99f13-105">This discussion covers backup types, and backup restrictions.</span></span> <span data-ttu-id="99f13-106">In questo argomento vengono inoltre presentati i dispositivi e i supporti di backup di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="99f13-106">The topic also introduces [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup devices and backup media.</span></span>  
  
 <span data-ttu-id="99f13-107">**Contenuto dell'argomento**</span><span class="sxs-lookup"><span data-stu-id="99f13-107">**In this Topic:**</span></span>  
  
-   [<span data-ttu-id="99f13-108">Componenti e concetti</span><span class="sxs-lookup"><span data-stu-id="99f13-108">Components and Concepts</span></span>](#TermsAndDefinitions)  
  
-   [<span data-ttu-id="99f13-109">Compressione dei backup</span><span class="sxs-lookup"><span data-stu-id="99f13-109">Backup Compression</span></span>](#BackupCompression)  
  
-   [<span data-ttu-id="99f13-110">Restrizioni relative alle operazioni di backup in SQL Server</span><span class="sxs-lookup"><span data-stu-id="99f13-110">Restrictions on Backup Operations in SQL Server</span></span>](#Restrictions)  
  
-   [<span data-ttu-id="99f13-111">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="99f13-111">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="components-and-concepts"></a><a name="TermsAndDefinitions"></a> <span data-ttu-id="99f13-112">Componenti e concetti</span><span class="sxs-lookup"><span data-stu-id="99f13-112">Components and Concepts</span></span>  
 <span data-ttu-id="99f13-113">eseguire il backup</span><span class="sxs-lookup"><span data-stu-id="99f13-113">back up [verb]</span></span>  
 <span data-ttu-id="99f13-114">Operazione di copia di dati o record di log da un database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o dal relativo log delle transazioni in un dispositivo di backup, ad esempio un disco, per creare un backup dei dati o del log.</span><span class="sxs-lookup"><span data-stu-id="99f13-114">Copies the data or log records from a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database or its transaction log to a backup device, such as a disk, to create a data backup or log backup.</span></span>  
  
 <span data-ttu-id="99f13-115">backup</span><span class="sxs-lookup"><span data-stu-id="99f13-115">backup [noun]</span></span>  
 <span data-ttu-id="99f13-116">Copia dei dati di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilizzabile per il recupero e il ripristino dei dati in seguito a errori.</span><span class="sxs-lookup"><span data-stu-id="99f13-116">A copy of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data that can be used to restore and recover the data after a failure.</span></span> <span data-ttu-id="99f13-117">Un backup dei dati di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] viene creato al livello di un database o di uno o più dei relativi file o filegroup.</span><span class="sxs-lookup"><span data-stu-id="99f13-117">A backup of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data is created at the level of a database or one or more of its files or filegroups.</span></span> <span data-ttu-id="99f13-118">Non è possibile creare backup a livello di tabella.</span><span class="sxs-lookup"><span data-stu-id="99f13-118">Table-level backups cannot be created.</span></span> <span data-ttu-id="99f13-119">Per utilizzare il modello di recupero con registrazione completa, oltre al backup dei dati è necessario creare backup del log delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="99f13-119">In addition to data backups, the full recovery model requires creating backups of the transaction log.</span></span>  
  
 [<span data-ttu-id="99f13-120">modello di recupero</span><span class="sxs-lookup"><span data-stu-id="99f13-120">recovery model</span></span>](recovery-models-sql-server.md)  
 <span data-ttu-id="99f13-121">Proprietà del database che controlla la manutenzione del log delle transazioni su un database.</span><span class="sxs-lookup"><span data-stu-id="99f13-121">A database property that controls transaction log maintenance on a database.</span></span> <span data-ttu-id="99f13-122">Sono tre i modelli di recupero disponibili: con registrazione minima, con registrazione completa e con registrazione minima delle operazioni bulk.</span><span class="sxs-lookup"><span data-stu-id="99f13-122">Three recovery models exist: simple, full, and bulk-logged.</span></span> <span data-ttu-id="99f13-123">Il modello di recupero del database ne determina i requisiti di backup e di ripristino.</span><span class="sxs-lookup"><span data-stu-id="99f13-123">The recovery model of database determines its backup and restore requirements.</span></span>  
  
 [<span data-ttu-id="99f13-124">restore</span><span class="sxs-lookup"><span data-stu-id="99f13-124">restore</span></span>](restore-and-recovery-overview-sql-server.md)  
 <span data-ttu-id="99f13-125">Processo multifase che copia tutti i dati e le pagine di log da un backup di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a un database specificato ed esegue il rollforward di tutte le transazioni registrate nel backup applicando le modifiche registrate in modo da aggiornare i dati.</span><span class="sxs-lookup"><span data-stu-id="99f13-125">A multi-phase process that copies all the data and log pages from a specified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup to a specified database, and then rolls forward all the transactions that are logged in the backup by applying logged changes to bring the data forward in time.</span></span>  
  
 <span data-ttu-id="99f13-126">**Tipi di backup**</span><span class="sxs-lookup"><span data-stu-id="99f13-126">**Types of Backups**</span></span>  
  
 [<span data-ttu-id="99f13-127">backup di sola copia</span><span class="sxs-lookup"><span data-stu-id="99f13-127">copy-only backup</span></span>](copy-only-backups-sql-server.md)  
 <span data-ttu-id="99f13-128">Backup per utilizzo speciale indipendente dalla sequenza di backup convenzionali di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="99f13-128">A special-use backup that is independent of the regular sequence of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backups.</span></span>  
  
 <span data-ttu-id="99f13-129">backup dei dati</span><span class="sxs-lookup"><span data-stu-id="99f13-129">data backup</span></span>  
 <span data-ttu-id="99f13-130">Backup dei dati in un database completo (backup del database), database parziale (backup parziale) o set di file di dati o di filegroup (backup di file).</span><span class="sxs-lookup"><span data-stu-id="99f13-130">A backup of data in a complete database (a database backup), a partial database (a partial backup), or a set of data files or filegroups (a file backup).</span></span>  
  
 [<span data-ttu-id="99f13-131">backup del database</span><span class="sxs-lookup"><span data-stu-id="99f13-131">database backup</span></span>](full-database-backups-sql-server.md)  
 <span data-ttu-id="99f13-132">Backup di un database.</span><span class="sxs-lookup"><span data-stu-id="99f13-132">A backup of a database.</span></span> <span data-ttu-id="99f13-133">I backup completi del database rappresentano l'intero database al momento del completamento del backup.</span><span class="sxs-lookup"><span data-stu-id="99f13-133">Full database backups represent the whole database at the time the backup finished.</span></span> <span data-ttu-id="99f13-134">I backup differenziali del database contengono solo le modifiche apportate al database a partire dal backup del database più recente.</span><span class="sxs-lookup"><span data-stu-id="99f13-134">Differential database backups contain only changes made to the database since its most recent full database backup.</span></span>  
  
 [<span data-ttu-id="99f13-135">backup differenziale</span><span class="sxs-lookup"><span data-stu-id="99f13-135">differential backup</span></span>](full-database-backups-sql-server.md)  
 <span data-ttu-id="99f13-136">Backup dei dati basato sull'ultimo backup completo di un database completo o parziale o di un set di file di dati o filegroup ( *base differenziale*) che contiene solo gli extent di dati modificati rispetto alla base differenziale.</span><span class="sxs-lookup"><span data-stu-id="99f13-136">A data backup that is based on the latest full backup of a complete or partial database or a set of data files or filegroups (the *differential base*) and that contains only the data extents that have changed since the differential base.</span></span>  
  
 <span data-ttu-id="99f13-137">Un backup parziale differenziale registra solo gli extent di dati che sono stati modificati nei filegroup dopo il backup parziale precedente, denominato base del backup differenziale.</span><span class="sxs-lookup"><span data-stu-id="99f13-137">A differential partial backup records only the data extents that have changed in the filegroups since the previous partial backup, known as the base for the differential.</span></span>  
  
 <span data-ttu-id="99f13-138">backup completo</span><span class="sxs-lookup"><span data-stu-id="99f13-138">full backup</span></span>  
 <span data-ttu-id="99f13-139">Backup dei dati che include tutti i dati in un database specifico o in un set di filegroup o file, oltre a una parte di log sufficiente al recupero di tali dati.</span><span class="sxs-lookup"><span data-stu-id="99f13-139">A data backup that contains all the data in a specific database or set of filegroups or files, and also enough log to allow for recovering that data.</span></span>  
  
 [<span data-ttu-id="99f13-140">backup di log</span><span class="sxs-lookup"><span data-stu-id="99f13-140">log backup</span></span>](transaction-log-backups-sql-server.md)  
 <span data-ttu-id="99f13-141">Backup dei log delle transazioni che include tutti i record di log di cui non è stato eseguito il backup in un backup di log precedente.</span><span class="sxs-lookup"><span data-stu-id="99f13-141">A backup of transaction logs that includes all log records that were not backed up in a previous log backup.</span></span> <span data-ttu-id="99f13-142">(modello di recupero con registrazione completa)</span><span class="sxs-lookup"><span data-stu-id="99f13-142">(full recovery model)</span></span>  
  
 [<span data-ttu-id="99f13-143">backup di file</span><span class="sxs-lookup"><span data-stu-id="99f13-143">file backup</span></span>](full-file-backups-sql-server.md)  
 <span data-ttu-id="99f13-144">Backup di uno o più file o filegroup di database.</span><span class="sxs-lookup"><span data-stu-id="99f13-144">A backup of one or more database files or filegroups.</span></span>  
  
 [<span data-ttu-id="99f13-145">backup parziale</span><span class="sxs-lookup"><span data-stu-id="99f13-145">partial backup</span></span>](partial-backups-sql-server.md)  
 <span data-ttu-id="99f13-146">Contiene dati provenienti solo da una parte dei filegroup in un database, compresi i dati del filegroup primario, di ogni filegroup con accesso di lettura/scrittura e di eventuali file di sola lettura specificati opzionalmente.</span><span class="sxs-lookup"><span data-stu-id="99f13-146">Contains data from only some of the filegroups in a database, including the data in the primary filegroup, every read/write filegroup, and any optionally-specified read-only files.</span></span>  
  
 <span data-ttu-id="99f13-147">**Termini e definizioni dei supporti di backup**</span><span class="sxs-lookup"><span data-stu-id="99f13-147">**Backup Media Terms and Definitions**</span></span>  
  
 [<span data-ttu-id="99f13-148">dispositivo di backup</span><span class="sxs-lookup"><span data-stu-id="99f13-148">backup device</span></span>](backup-devices-sql-server.md)  
 <span data-ttu-id="99f13-149">Dispositivo nastro o disco in cui vengono scritti i backup di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e da cui è possibile eseguirne il ripristino.</span><span class="sxs-lookup"><span data-stu-id="99f13-149">A disk or tape device to which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backups are written and from which they can be restored.</span></span> <span data-ttu-id="99f13-150">I backup di SQL Server possono anche essere scritti in un servizio Archiviazione BLOB di Azure e viene usato il formato **URL** per specificare la destinazione e il nome del file di backup.</span><span class="sxs-lookup"><span data-stu-id="99f13-150">SQL Server backups can also be written to an Azure Blob storage service, and **URL** format is used to specify the destination and the name of the backup file..</span></span> <span data-ttu-id="99f13-151">Per altre informazioni, vedere [Backup e ripristino di SQL Server con il servizio di archiviazione BLOB di Azure](sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md).</span><span class="sxs-lookup"><span data-stu-id="99f13-151">For more information, see [SQL Server Backup and Restore with Azure Blob Storage Service](sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md).</span></span>  
  
 [<span data-ttu-id="99f13-152">supporti di backup</span><span class="sxs-lookup"><span data-stu-id="99f13-152">backup media</span></span>](media-sets-media-families-and-backup-sets-sql-server.md)  
 <span data-ttu-id="99f13-153">Uno o più nastri o file del disco in cui sono stati scritti uno o più backup.</span><span class="sxs-lookup"><span data-stu-id="99f13-153">One or more tapes or disk files to which one or more backup have been written.</span></span>  
  
 [<span data-ttu-id="99f13-154">set di backup</span><span class="sxs-lookup"><span data-stu-id="99f13-154">backup set</span></span>](media-sets-media-families-and-backup-sets-sql-server.md)  
 <span data-ttu-id="99f13-155">Contenuto di backup aggiunto a un set di supporti da un'operazione di backup completata.</span><span class="sxs-lookup"><span data-stu-id="99f13-155">The backup content that is added to a media set by a successful backup operation.</span></span>  
  
 [<span data-ttu-id="99f13-156">gruppo di supporti</span><span class="sxs-lookup"><span data-stu-id="99f13-156">media family</span></span>](media-sets-media-families-and-backup-sets-sql-server.md)  
 <span data-ttu-id="99f13-157">Backup creati su un singolo dispositivo senza mirroring o su un set di dispositivi con mirroring in un set di supporti</span><span class="sxs-lookup"><span data-stu-id="99f13-157">Backups created on a single nonmirrored device or a set of mirrored devices in a media set</span></span>  
  
 [<span data-ttu-id="99f13-158">set di supporti</span><span class="sxs-lookup"><span data-stu-id="99f13-158">media set</span></span>](media-sets-media-families-and-backup-sets-sql-server.md)  
 <span data-ttu-id="99f13-159">Raccolta ordinata di supporti di backup, nastri o file su disco, su cui una o più operazioni di backup hanno eseguito la scrittura usando un tipo e un numero fisso di dispositivi di backup.</span><span class="sxs-lookup"><span data-stu-id="99f13-159">An ordered collection of backup media, tapes or disk files, to which one or more backup operations have written using a fixed type and number of backup devices.</span></span>  
  
 [<span data-ttu-id="99f13-160">set di supporti con mirroring</span><span class="sxs-lookup"><span data-stu-id="99f13-160">mirrored media set</span></span>](mirrored-backup-media-sets-sql-server.md)  
 <span data-ttu-id="99f13-161">Più copie (copie mirror) di un set di supporti.</span><span class="sxs-lookup"><span data-stu-id="99f13-161">Multiple copies (mirrors) of a media set.</span></span>  
  
##  <a name="backup-compression"></a><a name="BackupCompression"></a><span data-ttu-id="99f13-162">Compressione dei backup</span><span class="sxs-lookup"><span data-stu-id="99f13-162">Backup Compression</span></span>  
 [!INCLUDE[ssEnterpriseEd10](../../includes/ssenterpriseed10-md.md)] <span data-ttu-id="99f13-163">e versioni successive. I backup compressi possono essere ripristinati in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="99f13-163">and later versions support compressing backups, and [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] and later versions can restore a compressed backup.</span></span> <span data-ttu-id="99f13-164">Per altre informazioni, vedere [Compressione backup &#40;SQL Server&#41;](backup-compression-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="99f13-164">For more information, see [Backup Compression &#40;SQL Server&#41;](backup-compression-sql-server.md).</span></span>  
  
##  <a name="restrictions-on-backup-operations-in-sql-server"></a><a name="Restrictions"></a><span data-ttu-id="99f13-165">Limitazioni relative alle operazioni di backup in SQL Server</span><span class="sxs-lookup"><span data-stu-id="99f13-165">Restrictions on Backup Operations in SQL Server</span></span>  
 <span data-ttu-id="99f13-166">Il backup può verificarsi mentre il database è online e in uso.</span><span class="sxs-lookup"><span data-stu-id="99f13-166">Backup can occur while the database is online and being used.</span></span> <span data-ttu-id="99f13-167">Si applicano tuttavia le restrizioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="99f13-167">However, the following restrictions exist.</span></span>  
  
### <a name="offline-data-cannot-be-backed-up"></a><span data-ttu-id="99f13-168">Non è possibile eseguire il backup dei dati offline</span><span class="sxs-lookup"><span data-stu-id="99f13-168">Offline Data Cannot Be Backed Up</span></span>  
 <span data-ttu-id="99f13-169">Se si fa riferimento in modo implicito o esplicito a dati offline, l'operazione di backup ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="99f13-169">Any backup operation that implicitly or explicitly references data that is offline fails.</span></span> <span data-ttu-id="99f13-170">Alcuni esempi comuni sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="99f13-170">Some typical examples include the following:</span></span>  
  
-   <span data-ttu-id="99f13-171">Si richiede un backup completo del database, ma un filegroup del database è offline.</span><span class="sxs-lookup"><span data-stu-id="99f13-171">You request a full database backup, but one filegroup of the database is offline.</span></span> <span data-ttu-id="99f13-172">Poiché tutti i filegroup vengono inclusi implicitamente in un backup completo del database, questa operazione ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="99f13-172">Because all filegroups are implicitly included in a full database backup, this operation fails.</span></span>  
  
     <span data-ttu-id="99f13-173">Per eseguire un backup del database, è possibile utilizzare un backup del file e specificare solo i filegroup online.</span><span class="sxs-lookup"><span data-stu-id="99f13-173">To back up this database, you can use a file backup and specify only the filegroups that are online.</span></span>  
  
-   <span data-ttu-id="99f13-174">Viene richiesto un backup parziale, ma un filegroup di lettura/scrittura è offline.</span><span class="sxs-lookup"><span data-stu-id="99f13-174">You request a partial backup, but a read/write filegroup is offline.</span></span> <span data-ttu-id="99f13-175">Dato che tutti i filegroup di lettura/scrittura sono necessari per un backup parziale, l'operazione non riesce.</span><span class="sxs-lookup"><span data-stu-id="99f13-175">Because all read/write filegroups are required for a partial backup, the operation fails.</span></span>  
  
-   <span data-ttu-id="99f13-176">Si richiede un backup di file specifici, ma uno di tali file non è online.</span><span class="sxs-lookup"><span data-stu-id="99f13-176">You request a file backup of specific files, but one of the files is not online.</span></span> <span data-ttu-id="99f13-177">L'operazione ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="99f13-177">The operation fails.</span></span> <span data-ttu-id="99f13-178">Per eseguire il backup dei file online, è possibile escludere il file offline dall'elenco dei file e ripetere l'operazione.</span><span class="sxs-lookup"><span data-stu-id="99f13-178">To back up the online files, you can omit the offline file from the file list and repeat the operation.</span></span>  
  
 <span data-ttu-id="99f13-179">In genere, un backup del log riesce anche se uno o più file di dati non sono disponibili.</span><span class="sxs-lookup"><span data-stu-id="99f13-179">Typically, a log backup succeeds even if one or more data files are unavailable.</span></span> <span data-ttu-id="99f13-180">Tuttavia, se uno o più file contengono modifiche con registrazione minima delle operazioni bulk apportate nel modello di recupero con registrazione minima delle operazioni bulk, è necessario che tutti i file siano online perché il backup riesca.</span><span class="sxs-lookup"><span data-stu-id="99f13-180">However, if any file contains bulk-logged changes made under the bulk-logged recovery model, all the files must be online for the backup to succeed.</span></span>  
  
### <a name="concurrency-restrictions-during-backup"></a><span data-ttu-id="99f13-181">Restrizioni di concorrenza durante il backup</span><span class="sxs-lookup"><span data-stu-id="99f13-181">Concurrency Restrictions During Backup</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="99f13-182">utilizza un processo di backup online per consentire un backup del database mentre questo è in uso.</span><span class="sxs-lookup"><span data-stu-id="99f13-182">uses an online backup process to allow for a database backup while the database is still being used.</span></span> <span data-ttu-id="99f13-183">Durante un backup, è possibile eseguire la maggior parte delle operazioni, ad esempio istruzioni INSERT, UPDATE o DELETE.</span><span class="sxs-lookup"><span data-stu-id="99f13-183">During a backup, most operations are possible; for example, INSERT, UPDATE, or DELETE statements are allowed during a backup operation.</span></span> <span data-ttu-id="99f13-184">Tuttavia, se si tenta di avviare un'operazione di backup durante la creazione o l'eliminazione di un file di database, l'operazione verrà rimandata fino al completamento dell'operazione di creazione o di eliminazione, oppure verrà annullata a causa di un timeout.</span><span class="sxs-lookup"><span data-stu-id="99f13-184">However, if you try to start a backup operation while a database file is being created or deleted, the backup operation waits until the create or delete operation is finished or the backup times out.</span></span>  
  
 <span data-ttu-id="99f13-185">Le operazioni che non possono essere eseguite durante un backup del database o del log delle transazioni sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="99f13-185">Operations that cannot run during a database backup or transaction log backup include the following:</span></span>  
  
-   <span data-ttu-id="99f13-186">Operazioni di gestione dei file, ad esempio l'istruzione ALTER DATABASE con l'opzione ADD FILE o REMOVE FILE.</span><span class="sxs-lookup"><span data-stu-id="99f13-186">File-management operations such as the ALTER DATABASE statement with either the ADD FILE or REMOVE FILE options.</span></span>  
  
-   <span data-ttu-id="99f13-187">Compattazione di database o file,</span><span class="sxs-lookup"><span data-stu-id="99f13-187">Shrink database or shrink file operations.</span></span> <span data-ttu-id="99f13-188">incluse operazioni di compattazione automatica.</span><span class="sxs-lookup"><span data-stu-id="99f13-188">This includes auto-shrink operations.</span></span>  
  
-   <span data-ttu-id="99f13-189">Se durante l'esecuzione di un'operazione di backup si tenta di creare o eliminare un file di database, l'operazione di creazione o eliminazione non riuscirà.</span><span class="sxs-lookup"><span data-stu-id="99f13-189">If you try to create or delete a database file while a backup operation is in progress, the create or delete operation fails.</span></span>  
  
 <span data-ttu-id="99f13-190">Se un'operazione di backup si sovrappone a un'operazione di gestione di file o di compattazione, si verifica un conflitto.</span><span class="sxs-lookup"><span data-stu-id="99f13-190">If a backup operation overlaps with a file-management operation or shrink operation, a conflict occurs.</span></span> <span data-ttu-id="99f13-191">Indipendentemente dall'operazione in conflitto avviata per prima, la seconda operazione viene rimandata fino al timeout del blocco richiesto dalla prima operazione. Il periodo di timeout è controllato da un'impostazione relativa al timeout di sessione. Se il blocco viene rilasciato entro il periodo di timeout, la seconda operazione continua.</span><span class="sxs-lookup"><span data-stu-id="99f13-191">Regardless of which of the conflicting operation began first, the second operation waits for the lock set by the first operation to time out. (The time-out period is controlled by a session time-out setting.) If the lock is released during the time-out period, the second operation continues.</span></span> <span data-ttu-id="99f13-192">Se il periodo di timeout scade, la seconda operazione non viene eseguita.</span><span class="sxs-lookup"><span data-stu-id="99f13-192">If the lock times out, the second operation fails.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="99f13-193">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="99f13-193">Related Tasks</span></span>  
 <span data-ttu-id="99f13-194">**Per utilizzare i dispositivi di backup e i supporti di backup**</span><span class="sxs-lookup"><span data-stu-id="99f13-194">**To work with backup devices and backup media**</span></span>  
  
-   [<span data-ttu-id="99f13-195">Definire un dispositivo di backup logico per un file su disco &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="99f13-195">Define a Logical Backup Device for a Disk File &#40;SQL Server&#41;</span></span>](define-a-logical-backup-device-for-a-disk-file-sql-server.md)  
  
-   [<span data-ttu-id="99f13-196">Definizione di un dispositivo di backup logico per un'unità nastro &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="99f13-196">Define a Logical Backup Device for a Tape Drive &#40;SQL Server&#41;</span></span>](define-a-logical-backup-device-for-a-tape-drive-sql-server.md)  
  
-   [<span data-ttu-id="99f13-197">Specificare un disco o un nastro come destinazione di backup &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="99f13-197">Specify a Disk or Tape As a Backup Destination &#40;SQL Server&#41;</span></span>](specify-a-disk-or-tape-as-a-backup-destination-sql-server.md)  
  
-   [<span data-ttu-id="99f13-198">Eliminare un dispositivo di backup &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="99f13-198">Delete a Backup Device &#40;SQL Server&#41;</span></span>](delete-a-backup-device-sql-server.md)  
  
-   [<span data-ttu-id="99f13-199">Impostazione della data di scadenza di un backup &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="99f13-199">Set the Expiration Date on a Backup &#40;SQL Server&#41;</span></span>](set-the-expiration-date-on-a-backup-sql-server.md)  
  
-   [<span data-ttu-id="99f13-200">Visualizzare il contenuto di un nastro o di un file di backup &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="99f13-200">View the Contents of a Backup Tape or File &#40;SQL Server&#41;</span></span>](view-the-contents-of-a-backup-tape-or-file-sql-server.md)  
  
-   [<span data-ttu-id="99f13-201">Visualizzare i file di dati e i file di log in un set di backup &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="99f13-201">View the Data and Log Files in a Backup Set &#40;SQL Server&#41;</span></span>](view-the-data-and-log-files-in-a-backup-set-sql-server.md)  
  
-   [<span data-ttu-id="99f13-202">Visualizzare le proprietà e il contenuto di un dispositivo di backup logico &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="99f13-202">View the Properties and Contents of a Logical Backup Device &#40;SQL Server&#41;</span></span>](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md)  
  
-   [<span data-ttu-id="99f13-203">Ripristinare un backup da un dispositivo &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="99f13-203">Restore a Backup from a Device &#40;SQL Server&#41;</span></span>](restore-a-backup-from-a-device-sql-server.md)  
  
-   [<span data-ttu-id="99f13-204">Esercitazione: Backup e ripristino di SQL Server nel servizio di archiviazione BLOB di Azure</span><span class="sxs-lookup"><span data-stu-id="99f13-204">Tutorial: SQL Server Backup and Restore to Azure Blob Storage Service</span></span>](../tutorial-sql-server-backup-and-restore-to-azure-blob-storage-service.md)  
  
 <span data-ttu-id="99f13-205">**Per creare un backup**</span><span class="sxs-lookup"><span data-stu-id="99f13-205">**To create a backup**</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="99f13-206">Per eseguire backup parziali o di sola copia è necessario usare l'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)][BACKUP](/sql/t-sql/statements/backup-transact-sql) rispettivamente con l'opzione PARTIAL o COPY_ONLY.</span><span class="sxs-lookup"><span data-stu-id="99f13-206">For partial or copy-only backups, you must use the [!INCLUDE[tsql](../../includes/tsql-md.md)][BACKUP](/sql/t-sql/statements/backup-transact-sql) statement with the PARTIAL or COPY_ONLY option, respectively.</span></span>  
  
-   [<span data-ttu-id="99f13-207">Creazione di un backup completo del database &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="99f13-207">Create a Full Database Backup &#40;SQL Server&#41;</span></span>](create-a-full-database-backup-sql-server.md)  
  
-   [<span data-ttu-id="99f13-208">Eseguire il backup di un log delle transazioni &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="99f13-208">Back Up a Transaction Log &#40;SQL Server&#41;</span></span>](back-up-a-transaction-log-sql-server.md)  
  
-   [<span data-ttu-id="99f13-209">Backup di file e filegroup &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="99f13-209">Back Up Files and Filegroups &#40;SQL Server&#41;</span></span>](back-up-files-and-filegroups-sql-server.md)  
  
-   [<span data-ttu-id="99f13-210">Creare un backup differenziale del database &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="99f13-210">Create a Differential Database Backup &#40;SQL Server&#41;</span></span>](create-a-differential-database-backup-sql-server.md)  
  
-   [<span data-ttu-id="99f13-211">Esecuzione del backup del log delle transazioni quando il database è danneggiato &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="99f13-211">Back Up the Transaction Log When the Database Is Damaged &#40;SQL Server&#41;</span></span>](back-up-the-transaction-log-when-the-database-is-damaged-sql-server.md)  
  
-   [<span data-ttu-id="99f13-212">Abilitare o disabilitare il checksum di backup durante il backup o il ripristino &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="99f13-212">Enable or Disable Backup Checksums During Backup or Restore &#40;SQL Server&#41;</span></span>](enable-or-disable-backup-checksums-during-backup-or-restore-sql-server.md)  
  
-   [<span data-ttu-id="99f13-213">Specifica se un'operazione di backup o ripristino viene arrestata o prosegue in seguito a un errore &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="99f13-213">Specify Whether a Backup or Restore Operation Continues or Stops After Encountering an Error &#40;SQL Server&#41;</span></span>](specify-if-backup-or-restore-continues-or-stops-after-error.md)  
  
-   [<span data-ttu-id="99f13-214">Utilizzo di Resource Governor per limitare l'utilizzo della CPU da parte della compressione dei backup &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="99f13-214">Use Resource Governor to Limit CPU Usage by Backup Compression &#40;Transact-SQL&#41;</span></span>](use-resource-governor-to-limit-cpu-usage-by-backup-compression-transact-sql.md)  
  
-   [<span data-ttu-id="99f13-215">Esercitazione: Backup e ripristino di SQL Server nel servizio di archiviazione BLOB di Azure</span><span class="sxs-lookup"><span data-stu-id="99f13-215">Tutorial: SQL Server Backup and Restore to Azure Blob Storage Service</span></span>](../tutorial-sql-server-backup-and-restore-to-azure-blob-storage-service.md)  
  
## <a name="see-also"></a><span data-ttu-id="99f13-216">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="99f13-216">See Also</span></span>  
 <span data-ttu-id="99f13-217">[Backup e ripristino di database SQL Server](back-up-and-restore-of-sql-server-databases.md) </span><span class="sxs-lookup"><span data-stu-id="99f13-217">[Back Up and Restore of SQL Server Databases](back-up-and-restore-of-sql-server-databases.md) </span></span>  
 <span data-ttu-id="99f13-218">[Panoramica del ripristino e del recupero &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="99f13-218">[Restore and Recovery Overview &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md) </span></span>  
 <span data-ttu-id="99f13-219">[Piani di manutenzione](../maintenance-plans/maintenance-plans.md) </span><span class="sxs-lookup"><span data-stu-id="99f13-219">[Maintenance Plans](../maintenance-plans/maintenance-plans.md) </span></span>  
 <span data-ttu-id="99f13-220">[Log delle transazioni &#40;SQL Server&#41;](../logs/the-transaction-log-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="99f13-220">[The Transaction Log &#40;SQL Server&#41;](../logs/the-transaction-log-sql-server.md) </span></span>  
 [<span data-ttu-id="99f13-221">Modelli di recupero &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="99f13-221">Recovery Models &#40;SQL Server&#41;</span></span>](recovery-models-sql-server.md)  
  
  
