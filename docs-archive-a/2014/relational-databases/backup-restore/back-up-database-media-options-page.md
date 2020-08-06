---
title: Backup database (pagina Opzioni supporti) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- swb.backupdatabase.mediaoptions.f1
- sql12.swb.backupdatabase.mediaoptions.f1
ms.assetid: eff36228-710c-4ed5-9af5-95859575dc0f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: cd09eb091a7f488f891bc2e69d19ad039b65e065
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720106"
---
# <a name="back-up-database-media-options-page"></a><span data-ttu-id="f99e9-102">Backup database (pagina Opzioni multimediali)</span><span class="sxs-lookup"><span data-stu-id="f99e9-102">Back Up Database (Media Options Page)</span></span>
  <span data-ttu-id="f99e9-103">Usare la pagina  **Opzioni multimediali** della finestra di dialogo **Backup database** per visualizzare o modificare le opzioni multimediali del database.</span><span class="sxs-lookup"><span data-stu-id="f99e9-103">Use the  **Media Options** page of the **Back Up Database** dialog box to view or modify database media options.</span></span>  
  
 <span data-ttu-id="f99e9-104">**Per creare un backup utilizzando SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="f99e9-104">**To create a backup by using SQL Server Management Studio**</span></span>  
  
-   [<span data-ttu-id="f99e9-105">Creazione di un backup completo del database &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f99e9-105">Create a Full Database Backup &#40;SQL Server&#41;</span></span>](create-a-full-database-backup-sql-server.md)  
  
-   [<span data-ttu-id="f99e9-106">Creare un backup differenziale del database &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f99e9-106">Create a Differential Database Backup &#40;SQL Server&#41;</span></span>](create-a-differential-database-backup-sql-server.md)  
  
> [!IMPORTANT]  
>  <span data-ttu-id="f99e9-107">È possibile definire un piano di manutenzione database per creare backup di database.</span><span class="sxs-lookup"><span data-stu-id="f99e9-107">You can define a database maintenance plan to create database backups.</span></span> <span data-ttu-id="f99e9-108">Per altre informazioni, vedere [Piani di manutenzione](../maintenance-plans/maintenance-plans.md) e [Usare la Creazione guidata piano di manutenzione](../maintenance-plans/use-the-maintenance-plan-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="f99e9-108">For more information, see [Maintenance Plans](../maintenance-plans/maintenance-plans.md) and [Use the Maintenance Plan Wizard](../maintenance-plans/use-the-maintenance-plan-wizard.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f99e9-109">Quando si specifica un'attività di backup usando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], è possibile generare lo script [!INCLUDE[tsql](../../includes/tsql-md.md)][BACKUP](/sql/t-sql/statements/backup-transact-sql) corrispondente facendo clic sul pulsante **Script** e selezionando una destinazione per lo script.</span><span class="sxs-lookup"><span data-stu-id="f99e9-109">When you specify a backup task by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], you can generate the corresponding [!INCLUDE[tsql](../../includes/tsql-md.md)][BACKUP](/sql/t-sql/statements/backup-transact-sql) script by clicking the **Script** button and then selecting a destination for the script.</span></span>  
  
## <a name="options"></a><span data-ttu-id="f99e9-110">Opzioni</span><span class="sxs-lookup"><span data-stu-id="f99e9-110">Options</span></span>  
  
### <a name="overwrite-media"></a><span data-ttu-id="f99e9-111">Sovrascrivi supporti</span><span class="sxs-lookup"><span data-stu-id="f99e9-111">Overwrite media</span></span>  
 <span data-ttu-id="f99e9-112">Le opzioni del pannello **Sovrascrivi supporti** controllano la modalità di scrittura del backup nei supporti.</span><span class="sxs-lookup"><span data-stu-id="f99e9-112">The options of the **Overwrite media** panel control how the backup is written to the media.</span></span> <span data-ttu-id="f99e9-113">Se è stato selezionato un URL (Archiviazione di Azure) come destinazione di backup nella pagina Generale della finestra di dialogo Backup database, le opzioni nella sezione Sovrascrivi supporti sono disabilitate.</span><span class="sxs-lookup"><span data-stu-id="f99e9-113">IF you selected URL (Azure Storage) as the backup destination on the General page of the Back Up Database dialog box, the options under the Overwrite media section are disabled.</span></span> <span data-ttu-id="f99e9-114">È possibile sovrascrivere un backup utilizzando l'istruzione Transact-SQL `BACKUP TO URL.. WITH FORMAT`.</span><span class="sxs-lookup"><span data-stu-id="f99e9-114">You can overwrite a backup using the `BACKUP TO URL.. WITH FORMAT` Transact-SQL statement.</span></span> <span data-ttu-id="f99e9-115">Per altre informazioni, vedere [SQL Server Backup to URL](sql-server-backup-to-url.md).</span><span class="sxs-lookup"><span data-stu-id="f99e9-115">For more information, see [SQL Server Backup to URL](sql-server-backup-to-url.md).</span></span>  
  
 <span data-ttu-id="f99e9-116">Solo l'opzione **Esegui backup in un nuovo set di supporti e cancella tutti i set di backup esistenti** è supportata con le opzioni di crittografia.</span><span class="sxs-lookup"><span data-stu-id="f99e9-116">Only the option, **Backup to a new media, and erase all existing backup sets** is supported with encryption options.</span></span> <span data-ttu-id="f99e9-117">Se si selezionano le opzioni nella sezione **Esegui backup nel set di supporti esistente**, le opzioni di crittografia nella pagina **Opzioni di backup** saranno disabilitate.</span><span class="sxs-lookup"><span data-stu-id="f99e9-117">If you select the options under the **Back up to existing media** section, the encryptions options on the **Backup Options** page will be disabled.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f99e9-118">Per informazioni sui set di supporti, vedere [Set di supporti, gruppi di supporti e set di backup &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="f99e9-118">For information about media sets, see [Media Sets, Media Families, and Backup Sets &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md).</span></span>  
  
 <span data-ttu-id="f99e9-119">**Esegui backup nel set di supporti esistente**</span><span class="sxs-lookup"><span data-stu-id="f99e9-119">**Back up to the existing media set**</span></span>  
 <span data-ttu-id="f99e9-120">Consente di eseguire il backup del database in un set di supporti esistente.</span><span class="sxs-lookup"><span data-stu-id="f99e9-120">Back up a database to an existing media set.</span></span> <span data-ttu-id="f99e9-121">Selezionando questa opzione, vengono attivate tre opzioni.</span><span class="sxs-lookup"><span data-stu-id="f99e9-121">Selecting this option button activates three options.</span></span>  
  
 <span data-ttu-id="f99e9-122">Scegliere una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f99e9-122">Choose one of the following options:</span></span>  
  
 <span data-ttu-id="f99e9-123">**Accoda al set di backup esistente**</span><span class="sxs-lookup"><span data-stu-id="f99e9-123">**Append to the existing backup set**</span></span>  
 <span data-ttu-id="f99e9-124">Consente di accodare il set di backup a quello dei supporti esistente e di mantenere tutti i backup precedenti.</span><span class="sxs-lookup"><span data-stu-id="f99e9-124">Append the backup set to the existing media set, preserving any prior backups.</span></span>  
  
 <span data-ttu-id="f99e9-125">**Sovrascrivi tutti i set di backup esistenti**</span><span class="sxs-lookup"><span data-stu-id="f99e9-125">**Overwrite all existing backup sets**</span></span>  
 <span data-ttu-id="f99e9-126">Consente di sostituire un eventuale backup precedente nei set di supporti esistenti con quello corrente.</span><span class="sxs-lookup"><span data-stu-id="f99e9-126">Replace any prior backups on the existing media set with the current backup.</span></span>  
  
 <span data-ttu-id="f99e9-127">**Controlla nome set di supporti e scadenza set di backup**</span><span class="sxs-lookup"><span data-stu-id="f99e9-127">**Check media set name and backup set expiration**</span></span>  
 <span data-ttu-id="f99e9-128">Facoltativa. Se si esegue il backup in un set di supporti esistente, consente di richiedere che durante l'operazione di backup vengano verificati il nome e la data di scadenza dei set di backup.</span><span class="sxs-lookup"><span data-stu-id="f99e9-128">Optionally, if backing up to an existing media set, require the backup operation to verify the name and the expiration date of the backup sets.</span></span>  
  
 <span data-ttu-id="f99e9-129">**Nome set di supporti**</span><span class="sxs-lookup"><span data-stu-id="f99e9-129">**Media set name**</span></span>  
 <span data-ttu-id="f99e9-130">Facoltativa. Se l'opzione **Controlla nome set di supporti e scadenza set di backup** è selezionata, consente di specificare il nome del set di supporti da usare per l'operazione di backup.</span><span class="sxs-lookup"><span data-stu-id="f99e9-130">If **Check media set name and backup set expiration** is selected, optionally, specify the name of the media set to be used for this backup operation.</span></span>  
  
 <span data-ttu-id="f99e9-131">**Esegui backup in un nuovo set di supporti e cancella tutti i set di backup esistenti**</span><span class="sxs-lookup"><span data-stu-id="f99e9-131">**Back up to a new media set, and erase all existing backup sets**</span></span>  
 <span data-ttu-id="f99e9-132">Consente di utilizzare un nuovo set di supporti, cancellando i set di backup precedenti.</span><span class="sxs-lookup"><span data-stu-id="f99e9-132">Use a new media set, erasing the previous backup sets.</span></span>  
  
 <span data-ttu-id="f99e9-133">Se si seleziona questa opzione, verranno attivate le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f99e9-133">Clicking this option activates the following options:</span></span>  
  
 <span data-ttu-id="f99e9-134">**Nome nuovo set di supporti**</span><span class="sxs-lookup"><span data-stu-id="f99e9-134">**New media set name**</span></span>  
 <span data-ttu-id="f99e9-135">Facoltativa. Consente di immettere un nuovo nome per il set di supporti.</span><span class="sxs-lookup"><span data-stu-id="f99e9-135">Optionally, enter a new name for the media set.</span></span>  
  
 <span data-ttu-id="f99e9-136">**Descrizione nuovo set di supporti**</span><span class="sxs-lookup"><span data-stu-id="f99e9-136">**New media set description**</span></span>  
 <span data-ttu-id="f99e9-137">Facoltativa. Consente di immettere una descrizione significativa del nuovo set di supporti.</span><span class="sxs-lookup"><span data-stu-id="f99e9-137">Optionally, enter a meaningful description of the new media set.</span></span> <span data-ttu-id="f99e9-138">La descrizione deve essere sufficientemente specifica da indicare il contenuto in modo accurato.</span><span class="sxs-lookup"><span data-stu-id="f99e9-138">This description should be specific enough to communicate the contents accurately.</span></span>  
  
### <a name="reliability"></a><span data-ttu-id="f99e9-139">Affidabilità</span><span class="sxs-lookup"><span data-stu-id="f99e9-139">Reliability</span></span>  
 <span data-ttu-id="f99e9-140">Le opzioni del pannello **Log delle transazioni** controllano la gestione degli errori da parte dell'operazione di backup.</span><span class="sxs-lookup"><span data-stu-id="f99e9-140">The options of the **Transaction log** panel control error management by the backup operation.</span></span>  
  
 <span data-ttu-id="f99e9-141">**Verifica backup al termine**</span><span class="sxs-lookup"><span data-stu-id="f99e9-141">**Verify backup when finished**</span></span>  
 <span data-ttu-id="f99e9-142">Consente di verificare che il set di backup sia completo e che tutti i volumi siano leggibili.</span><span class="sxs-lookup"><span data-stu-id="f99e9-142">Verify that the backup set is complete and that all volumes are readable.</span></span>  
  
 <span data-ttu-id="f99e9-143">**Esegui checksum prima della scrittura nei supporti**</span><span class="sxs-lookup"><span data-stu-id="f99e9-143">**Perform checksum before writing to media**</span></span>  
 <span data-ttu-id="f99e9-144">Consente di verificare i checksum prima di scrivere nei supporti di backup.</span><span class="sxs-lookup"><span data-stu-id="f99e9-144">Verify the checksums before writing to the backup media.</span></span> <span data-ttu-id="f99e9-145">La selezione di questa opzione equivale a specificare l'opzione CHECKSUM nell'istruzione BACKUP di [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f99e9-145">Selecting this option is equivalent to specifying the CHECKSUM option in the BACKUP statement of [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="f99e9-146">L'opzione può determinare un aumento del carico di lavoro e una riduzione della velocità effettiva dell'operazione di backup.</span><span class="sxs-lookup"><span data-stu-id="f99e9-146">Selecting this option may increase the workload, and decrease the backup throughput of the backup operation.</span></span> <span data-ttu-id="f99e9-147">Per informazioni sui checksum di backup, vedere [Possibili errori relativi ai supporti durante il backup e il ripristino &#40;SQL Server&#41;](possible-media-errors-during-backup-and-restore-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="f99e9-147">For information about backup checksums, see [Possible Media Errors During Backup and Restore &#40;SQL Server&#41;](possible-media-errors-during-backup-and-restore-sql-server.md).</span></span>  
  
 <span data-ttu-id="f99e9-148">**Continua in stato di errore**</span><span class="sxs-lookup"><span data-stu-id="f99e9-148">**Continue on error**</span></span>  
 <span data-ttu-id="f99e9-149">L'operazione di backup deve continuare anche se si verificano errori.</span><span class="sxs-lookup"><span data-stu-id="f99e9-149">The backup operation is to continue even after encountering one or more errors.</span></span>  
  
### <a name="transaction-log"></a><span data-ttu-id="f99e9-150">Log delle transazioni</span><span class="sxs-lookup"><span data-stu-id="f99e9-150">Transaction log</span></span>  
 <span data-ttu-id="f99e9-151">Le opzioni del pannello **Log delle transazioni** controllano il comportamento del backup del log delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="f99e9-151">The options of the **Transaction log** panel control the behavior of a transaction log backup.</span></span> <span data-ttu-id="f99e9-152">Tali opzioni sono rilevanti solo nel modello di recupero con registrazione completa o nel modello di recupero con registrazione minima delle operazioni bulk.</span><span class="sxs-lookup"><span data-stu-id="f99e9-152">These options are relevant only under the full recovery model or bulk-logged recovery model.</span></span> <span data-ttu-id="f99e9-153">Sono attivate solo se l'opzione **Log delle transazioni** è stata selezionata nel campo **Tipo backup** disponibile nella pagina [Generale](../../integration-services/general-page-of-integration-services-designers-options.md) della finestra di dialogo **Backup database**.</span><span class="sxs-lookup"><span data-stu-id="f99e9-153">They are activated only if **Transaction log** has been selected in the **Backup type** field on the [General](../../integration-services/general-page-of-integration-services-designers-options.md) page of the **Back Up Database** dialog box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f99e9-154">Per informazioni sui backup del log delle transazioni, vedere [Backup di log delle transazioni &#40; SQL Server&#41;](transaction-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="f99e9-154">For information about transaction log backups, see [Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md).</span></span>  
  
 <span data-ttu-id="f99e9-155">**Tronca il log delle transazioni**</span><span class="sxs-lookup"><span data-stu-id="f99e9-155">**Truncate the transaction log**</span></span>  
 <span data-ttu-id="f99e9-156">Consente di eseguire il backup del log delle transazioni e di troncarlo per liberare spazio per i log.</span><span class="sxs-lookup"><span data-stu-id="f99e9-156">Back up the transaction log and truncate it to free log space.</span></span> <span data-ttu-id="f99e9-157">Il database rimane online.</span><span class="sxs-lookup"><span data-stu-id="f99e9-157">The database remains online.</span></span> <span data-ttu-id="f99e9-158">Questa è l'opzione predefinita.</span><span class="sxs-lookup"><span data-stu-id="f99e9-158">This is the default option.</span></span>  
  
 <span data-ttu-id="f99e9-159">**Esegui backup della parte finale del log e lascia il database in stato di ripristino**</span><span class="sxs-lookup"><span data-stu-id="f99e9-159">**Back up the tail of the log, and leave the database in the restoring state**</span></span>  
 <span data-ttu-id="f99e9-160">Consente di eseguire il backup della parte finale del log lasciando il database in stato di ripristino.</span><span class="sxs-lookup"><span data-stu-id="f99e9-160">Back up the tail of the log and leave the database in a restoring state.</span></span> <span data-ttu-id="f99e9-161">Questa opzione crea un *backup della parte finale del log*, che consente di eseguire il backup dei log non ancora sottoposti a questa procedura (il log attivo), in genere per la preparazione del ripristino di un database.</span><span class="sxs-lookup"><span data-stu-id="f99e9-161">This option creates a *tail-log backup*, which backs up logs that have not yet been backed up (the active log), typically, in preparation for restoring a database.</span></span> <span data-ttu-id="f99e9-162">Il database non sarà disponibile per gli utenti finché non viene ripristinato completamente.</span><span class="sxs-lookup"><span data-stu-id="f99e9-162">The database will be unavailable to users until it is completely restored.</span></span>  
  
 <span data-ttu-id="f99e9-163">La selezione di questa opzione equivale a specificare l'opzione WITH NO_TRUNCATE, NORECOVERY in un'istruzione [BACKUP](/sql/t-sql/statements/backup-transact-sql) ([!INCLUDE[tsql](../../includes/tsql-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="f99e9-163">Selecting this option is equivalent to specifying WITH NO_TRUNCATE, NORECOVERY in a [BACKUP](/sql/t-sql/statements/backup-transact-sql) statement ([!INCLUDE[tsql](../../includes/tsql-md.md)]).</span></span> <span data-ttu-id="f99e9-164">Per altre informazioni, vedere [Backup della parte finale del log &#40;SQL Server&#41;](tail-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="f99e9-164">For more information, see [Tail-Log Backups &#40;SQL Server&#41;](tail-log-backups-sql-server.md).</span></span>  
  
### <a name="tape-drive"></a><span data-ttu-id="f99e9-165">Unità nastro</span><span class="sxs-lookup"><span data-stu-id="f99e9-165">Tape drive</span></span>  
 <span data-ttu-id="f99e9-166">Le opzioni del pannello **Unità nastro** controllano la gestione dei nastri durante l'operazione di backup.</span><span class="sxs-lookup"><span data-stu-id="f99e9-166">The options of the **Tape drive** panel control tape management during the backup operation.</span></span> <span data-ttu-id="f99e9-167">Queste opzioni sono attivate solo se l'opzione **Nastro** è stata selezionata nel campo **Destinazione** disponibile nella pagina [Generale](../../integration-services/general-page-of-integration-services-designers-options.md) della finestra di dialogo **Backup database**.</span><span class="sxs-lookup"><span data-stu-id="f99e9-167">These options are activated only if **Tape** has been selected in the **Destination** panel on the [General](../../integration-services/general-page-of-integration-services-designers-options.md) page of the **Back Up Database** dialog box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f99e9-168">Per informazioni sull'uso dei dispositivi nastro, vedere [Dispositivi di backup &#40;SQL Server&#41;](backup-devices-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="f99e9-168">For information about how to use tape devices, see [Backup Devices &#40;SQL Server&#41;](backup-devices-sql-server.md).</span></span>  
  
 <span data-ttu-id="f99e9-169">**Scarica nastro al termine del backup**</span><span class="sxs-lookup"><span data-stu-id="f99e9-169">**Unload the tape after backup**</span></span>  
 <span data-ttu-id="f99e9-170">Consente di scaricare il nastro al termine del backup.</span><span class="sxs-lookup"><span data-stu-id="f99e9-170">After the backup is complete, unload the tape.</span></span>  
  
 <span data-ttu-id="f99e9-171">**Riavvolgi il nastro prima di scaricarlo**</span><span class="sxs-lookup"><span data-stu-id="f99e9-171">**Rewind the tape before unloading**</span></span>  
 <span data-ttu-id="f99e9-172">Consente di rilasciare e riavvolgere il nastro prima di scaricarlo.</span><span class="sxs-lookup"><span data-stu-id="f99e9-172">Before unloading the tape, release and rewind it.</span></span> <span data-ttu-id="f99e9-173">Questa opzione è abilitata solo se è selezionata l'opzione **Scarica nastro al termine del backup** .</span><span class="sxs-lookup"><span data-stu-id="f99e9-173">This is enabled only if **Unload the tape after backup** is selected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f99e9-174">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f99e9-174">See Also</span></span>  
 <span data-ttu-id="f99e9-175">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f99e9-175">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="f99e9-176">[Backup di un log delle transazioni &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="f99e9-176">[Back Up a Transaction Log &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md) </span></span>  
 <span data-ttu-id="f99e9-177">[Backup di file e filegroup &#40;SQL Server&#41;](back-up-files-and-filegroups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="f99e9-177">[Back Up Files and Filegroups &#40;SQL Server&#41;](back-up-files-and-filegroups-sql-server.md) </span></span>  
 [<span data-ttu-id="f99e9-178">Esecuzione del backup del log delle transazioni quando il database è danneggiato &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f99e9-178">Back Up the Transaction Log When the Database Is Damaged &#40;SQL Server&#41;</span></span>](back-up-the-transaction-log-when-the-database-is-damaged-sql-server.md)  
  
  
