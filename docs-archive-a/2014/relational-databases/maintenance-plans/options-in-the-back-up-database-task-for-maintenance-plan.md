---
title: Attività Backup database (piano di manutenzione) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.maint.backup.f1
- sql12.swb.maint.maintplanproperties.logbackup.f1
helpviewer_keywords:
- Back Up Database Task dialog box
ms.assetid: ed1ef012-fa14-4ba5-bafe-d1527ba065b3
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 952730f09deeede360dff5e2bd83f8cdc8a20a67
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627228"
---
# <a name="back-up-database-task-maintenance-plan"></a><span data-ttu-id="1b86a-102">Attività Backup database (Piano di manutenzione)</span><span class="sxs-lookup"><span data-stu-id="1b86a-102">Back Up Database Task (Maintenance Plan)</span></span>
  <span data-ttu-id="1b86a-103">Usare la finestra di dialogo **Attività Backup database** per aggiungere un'attività di backup al piano di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="1b86a-103">Use the **Back Up Database Task** dialog to add a backup task to the maintenance plan.</span></span> <span data-ttu-id="1b86a-104">L'esecuzione di backup del database è importante in caso di guasti al sistema o all'hardware, nonché di errori degli utenti, che possono danneggiare il database e rendere pertanto necessaria la disponibilità di una copia di backup per il ripristino.</span><span class="sxs-lookup"><span data-stu-id="1b86a-104">Backing up the database is important in case of system or hardware failure (or user errors) that cause the database to be damaged in some way, thus requiring a backed-up copy to be restored.</span></span> <span data-ttu-id="1b86a-105">Questa attività consente di eseguire backup completi e differenziali, di file e filegroup, nonché del log delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="1b86a-105">This task allows you to perform full, differential, files and filegroups, and transaction log backups.</span></span>  
  
 <span data-ttu-id="1b86a-106">**Per creare un'attività Backup database**</span><span class="sxs-lookup"><span data-stu-id="1b86a-106">**To create a backup database task**</span></span>  
  
-   [<span data-ttu-id="1b86a-107">Creare un piano di manutenzione</span><span class="sxs-lookup"><span data-stu-id="1b86a-107">Create a Maintenance Plan</span></span>](create-a-maintenance-plan.md)  
  
## <a name="options"></a><span data-ttu-id="1b86a-108">Opzioni</span><span class="sxs-lookup"><span data-stu-id="1b86a-108">Options</span></span>  
 <span data-ttu-id="1b86a-109">**Connection**</span><span class="sxs-lookup"><span data-stu-id="1b86a-109">**Connection**</span></span>  
 <span data-ttu-id="1b86a-110">Consente di selezionare la connessione server da utilizzare per l'esecuzione dell'attività.</span><span class="sxs-lookup"><span data-stu-id="1b86a-110">Select the server connection to use when performing this task.</span></span>  
  
 <span data-ttu-id="1b86a-111">**Nuovo**</span><span class="sxs-lookup"><span data-stu-id="1b86a-111">**New**</span></span>  
 <span data-ttu-id="1b86a-112">Consente di creare una nuova connessione server da utilizzare per l'esecuzione dell'attività.</span><span class="sxs-lookup"><span data-stu-id="1b86a-112">Create a new server connection to use when performing this task.</span></span> <span data-ttu-id="1b86a-113">La finestra di dialogo **Nuova connessione** è descritta di seguito.</span><span class="sxs-lookup"><span data-stu-id="1b86a-113">The **New Connection** dialog box is described below.</span></span>  
  
 <span data-ttu-id="1b86a-114">**Database**</span><span class="sxs-lookup"><span data-stu-id="1b86a-114">**Databases**</span></span>  
 <span data-ttu-id="1b86a-115">Consente di specificare i database su cui verrà eseguita l'attività.</span><span class="sxs-lookup"><span data-stu-id="1b86a-115">Specify the databases affected by this task.</span></span> <span data-ttu-id="1b86a-116">Quando questa opzione è selezionata, nell'elenco a discesa sono disponibili le opzioni seguenti: **Tutti i database**, **Tutti i database di sistema**, **Tutti i database utente**, **Database specifici**.</span><span class="sxs-lookup"><span data-stu-id="1b86a-116">When selected, the drop down list provides the following options: **All databases**, **All system databases**, **All user databases**, **These specific databases**.</span></span>  
  
 <span data-ttu-id="1b86a-117">**Tutti i database**</span><span class="sxs-lookup"><span data-stu-id="1b86a-117">**All databases**</span></span>  
 <span data-ttu-id="1b86a-118">Consente di generare un piano per l'esecuzione di attività di manutenzione su tutti i database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1b86a-118">Generate a maintenance plan that runs maintenance tasks against all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases.</span></span>  
  
 <span data-ttu-id="1b86a-119">**Tutti i database di sistema (master, model e msdb)**</span><span class="sxs-lookup"><span data-stu-id="1b86a-119">**All system databases (master, msdb, model)**</span></span>  
 <span data-ttu-id="1b86a-120">Consente di generare un piano per l'esecuzione di attività di manutenzione su tutti i database di sistema di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1b86a-120">Generate a maintenance plan that runs maintenance tasks against each of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system databases.</span></span> <span data-ttu-id="1b86a-121">Non vengono eseguite attività di manutenzione sui database creati dall'utente.</span><span class="sxs-lookup"><span data-stu-id="1b86a-121">No maintenance tasks are run against user-created databases.</span></span>  
  
 <span data-ttu-id="1b86a-122">**Tutti i database utente (diversi da master, model, msdb e tempdb)**</span><span class="sxs-lookup"><span data-stu-id="1b86a-122">**All user databases (excluding master, model, msdb, tempdb)**</span></span>  
 <span data-ttu-id="1b86a-123">Consente di generare un piano per l'esecuzione di attività di manutenzione su tutti i database creati dall'utente.</span><span class="sxs-lookup"><span data-stu-id="1b86a-123">Generate a maintenance plan that runs maintenance tasks against all user-created databases.</span></span> <span data-ttu-id="1b86a-124">Nessuna attività di manutenzione viene eseguita sui database di sistema di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1b86a-124">No maintenance tasks are run against the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system databases.</span></span>  
  
 <span data-ttu-id="1b86a-125">**I database seguenti**</span><span class="sxs-lookup"><span data-stu-id="1b86a-125">**These databases**</span></span>  
 <span data-ttu-id="1b86a-126">Consente di generare un piano per l'esecuzione di attività di manutenzione solo sui database selezionati.</span><span class="sxs-lookup"><span data-stu-id="1b86a-126">Generate a maintenance plan that runs maintenance tasks against only those databases that are selected.</span></span> <span data-ttu-id="1b86a-127">Se si sceglie questa opzione, è necessario selezionare almeno un database nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="1b86a-127">At least one database in the list must be selected if this option is chosen.</span></span>  
  
 <span data-ttu-id="1b86a-128">**Tipo di backup**</span><span class="sxs-lookup"><span data-stu-id="1b86a-128">**Backup type**</span></span>  
 <span data-ttu-id="1b86a-129">Consente di visualizzare il tipo di backup da eseguire.</span><span class="sxs-lookup"><span data-stu-id="1b86a-129">Shows the type of backup to be performed.</span></span>  
  
 <span data-ttu-id="1b86a-130">**Componente di cui eseguire il backup**</span><span class="sxs-lookup"><span data-stu-id="1b86a-130">**Backup component**</span></span>  
 <span data-ttu-id="1b86a-131">Selezionare **Database** per eseguire il backup dell'intero database.</span><span class="sxs-lookup"><span data-stu-id="1b86a-131">Select **Database** to back up the entire database.</span></span> <span data-ttu-id="1b86a-132">Selezionare **File e filegroup** per eseguire il backup solo di una parte del database.</span><span class="sxs-lookup"><span data-stu-id="1b86a-132">Select **File and filegroups** to back up only a portion of the database.</span></span> <span data-ttu-id="1b86a-133">Quando si seleziona questa opzione, è necessario specificare il nome del file o del filegroup.</span><span class="sxs-lookup"><span data-stu-id="1b86a-133">If selected, provide the file or filegroup name.</span></span> <span data-ttu-id="1b86a-134">Se nella casella **Database** sono selezionati più database, è necessario specificare **Database** solo per **Componente di cui eseguire il backup**.</span><span class="sxs-lookup"><span data-stu-id="1b86a-134">When multiple databases are selected in the **Databases** box, only specify **Databases** for the **Backup components**.</span></span> <span data-ttu-id="1b86a-135">Per eseguire i backup di file o filegroup, creare un'attività per ogni database.</span><span class="sxs-lookup"><span data-stu-id="1b86a-135">To perform file or filegroup backups, create a task for each database.</span></span>  
  
 <span data-ttu-id="1b86a-136">**Scadenza set di backup**</span><span class="sxs-lookup"><span data-stu-id="1b86a-136">**Backup set will expire**</span></span>  
 <span data-ttu-id="1b86a-137">Consente di specificare la data a partire dalla quale il set di backup può essere sovrascritto da un altro set di backup.</span><span class="sxs-lookup"><span data-stu-id="1b86a-137">Specify when the backup set can be overwritten by another backup set.</span></span>  
  
 <span data-ttu-id="1b86a-138">**Backup su**</span><span class="sxs-lookup"><span data-stu-id="1b86a-138">**Back up to**</span></span>  
 <span data-ttu-id="1b86a-139">Consente di scegliere se eseguire il backup del database su file o su nastro.</span><span class="sxs-lookup"><span data-stu-id="1b86a-139">Back up the database to a file or to tape.</span></span> <span data-ttu-id="1b86a-140">Sono disponibili solo i dispositivi nastro collegati al computer in cui è archiviato il database.</span><span class="sxs-lookup"><span data-stu-id="1b86a-140">Only tape devices attached to the computer containing the database are available.</span></span>  
  
 <span data-ttu-id="1b86a-141">**Backup database in uno o più file**</span><span class="sxs-lookup"><span data-stu-id="1b86a-141">**Back up databases across one or more files**</span></span>  
 <span data-ttu-id="1b86a-142">Fare clic su **Aggiungi** per aprire la finestra di dialogo **Selezione destinazione di backup** e specificare una o più posizioni su disco o dispositivi nastro.</span><span class="sxs-lookup"><span data-stu-id="1b86a-142">Click **Add** to open the **Select Backup Destination** dialog box, and provide one or more a disk location, or tape device.</span></span>  
  
 <span data-ttu-id="1b86a-143">**Azione per file di backup esistenti**</span><span class="sxs-lookup"><span data-stu-id="1b86a-143">**If backup files exist**</span></span>  
 <span data-ttu-id="1b86a-144">Selezionare **Accoda** per aggiungere questo backup alla fine del file.</span><span class="sxs-lookup"><span data-stu-id="1b86a-144">Select **Append** to add this backup to the end of the file.</span></span> <span data-ttu-id="1b86a-145">Selezionare **Sovrascrivi**per rimuovere i backup esistenti dal file e sostituirli con il nuovo.</span><span class="sxs-lookup"><span data-stu-id="1b86a-145">Select **Overwrite**, to remove any old backup in the file and replace them with this new backup.</span></span>  
  
 <span data-ttu-id="1b86a-146">**Crea un file di backup per ogni database**</span><span class="sxs-lookup"><span data-stu-id="1b86a-146">**Create a backup file for every database**</span></span>  
 <span data-ttu-id="1b86a-147">Creare un file di backup nel percorso specificato nella casella della cartella.</span><span class="sxs-lookup"><span data-stu-id="1b86a-147">Create a backup file in the location specified in the folder box.</span></span> <span data-ttu-id="1b86a-148">Viene creato un file per ogni database selezionato.</span><span class="sxs-lookup"><span data-stu-id="1b86a-148">One file will be created for each database selected.</span></span>  
  
 <span data-ttu-id="1b86a-149">**Crea una sottodirectory per ogni database**</span><span class="sxs-lookup"><span data-stu-id="1b86a-149">**Create a sub-directory for each database**</span></span>  
 <span data-ttu-id="1b86a-150">Selezionare questa opzione per inserire ogni file di backup di database in una sottocartella.</span><span class="sxs-lookup"><span data-stu-id="1b86a-150">Select to place each database in a subfolder.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="1b86a-151">Sebbene i piani di manutenzione possano creare sottodirectory, le attività di manutenzione non possono eliminare le sottodirectory.</span><span class="sxs-lookup"><span data-stu-id="1b86a-151">Although maintenance plans can create subdirectories, maintenance tasks cannot delete subdirectories.</span></span> <span data-ttu-id="1b86a-152">Questa caratteristica riduce la possibilità di un attacco dannoso che utilizzi l'attività Pulizia file manutenzione per eliminare i file.</span><span class="sxs-lookup"><span data-stu-id="1b86a-152">This feature reduces the possibility of a malicious attack that uses the Maintenance Cleanup task to delete files.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="1b86a-153">La sottodirectory eredita le autorizzazioni dalla directory padre.</span><span class="sxs-lookup"><span data-stu-id="1b86a-153">The subdirectory inherits permissions from the parent directory.</span></span> <span data-ttu-id="1b86a-154">Limitare le autorizzazioni per impedire l'accesso non autorizzato.</span><span class="sxs-lookup"><span data-stu-id="1b86a-154">Restrict permissions to avoid unauthorized access.</span></span>  
  
 <span data-ttu-id="1b86a-155">**Cartella**</span><span class="sxs-lookup"><span data-stu-id="1b86a-155">**Folder**</span></span>  
 <span data-ttu-id="1b86a-156">Specificare la cartella in cui inserire i file di database creati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="1b86a-156">Specify the folder to contain the automatically created database files.</span></span>  
  
 <span data-ttu-id="1b86a-157">**Estensione file di backup**</span><span class="sxs-lookup"><span data-stu-id="1b86a-157">**Backup file extension**</span></span>  
 <span data-ttu-id="1b86a-158">Specificare l'estensione da utilizzare per i file di backup.</span><span class="sxs-lookup"><span data-stu-id="1b86a-158">Specify the extension to use for the backup files.</span></span> <span data-ttu-id="1b86a-159">L'estensione predefinita è **bak**.</span><span class="sxs-lookup"><span data-stu-id="1b86a-159">The default is **.bak**.</span></span>  
  
 <span data-ttu-id="1b86a-160">**Verifica integrità backup**</span><span class="sxs-lookup"><span data-stu-id="1b86a-160">**Verify backup integrity**</span></span>  
 <span data-ttu-id="1b86a-161">Consente di verificare che il set di backup sia completo e che tutti i volumi siano leggibili.</span><span class="sxs-lookup"><span data-stu-id="1b86a-161">Verify that the backup set is complete and that all volumes are readable.</span></span>  
  
 <span data-ttu-id="1b86a-162">**Esegui backup della parte finale del log e lascia il database in stato di ripristino**</span><span class="sxs-lookup"><span data-stu-id="1b86a-162">**Back up the tail of the log, and leave the database in the restoring state**</span></span>  
 <span data-ttu-id="1b86a-163">Consente di eseguire un backup del log come ultimo passaggio prima di ripristinare un database.</span><span class="sxs-lookup"><span data-stu-id="1b86a-163">Perform a log backup as the last step before restoring a database.</span></span> <span data-ttu-id="1b86a-164">Per altre informazioni, vedere [Backup della parte finale del log &#40;SQL Server&#41;](../backup-restore/tail-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="1b86a-164">For more information, see [Tail-Log Backups &#40;SQL Server&#41;](../backup-restore/tail-log-backups-sql-server.md).</span></span>  
  
 <span data-ttu-id="1b86a-165">**Imposta compressione backup**</span><span class="sxs-lookup"><span data-stu-id="1b86a-165">**Set backup compression**</span></span>  
 <span data-ttu-id="1b86a-166">In [!INCLUDE[ssEnterpriseEd10](../../includes/ssenterpriseed10-md.md)] o versioni successive, selezionare uno dei seguenti valori della [compressione dei backup](../backup-restore/backup-compression-sql-server.md) :</span><span class="sxs-lookup"><span data-stu-id="1b86a-166">In [!INCLUDE[ssEnterpriseEd10](../../includes/ssenterpriseed10-md.md)] (or a later version), select one the following [backup compression](../backup-restore/backup-compression-sql-server.md) values:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1b86a-167">**Utilizza l'impostazione predefinita del server**</span><span class="sxs-lookup"><span data-stu-id="1b86a-167">**Use the default server setting**</span></span>|<span data-ttu-id="1b86a-168">Fare clic su questa opzione per utilizzare l'impostazione predefinita a livello di server.</span><span class="sxs-lookup"><span data-stu-id="1b86a-168">Click to use the server-level default.</span></span><br /><br /> <span data-ttu-id="1b86a-169">Questa impostazione predefinita è specificata dall'opzione di configurazione del server **Valore predefinito di compressione backup** .</span><span class="sxs-lookup"><span data-stu-id="1b86a-169">This default is set by the **backup compression default** server-configuration option.</span></span> <span data-ttu-id="1b86a-170">Per informazioni su come visualizzare l'impostazione corrente di questa opzione, vedere [Visualizzare o configurare l'opzione di configurazione del server backup compression default](../../database-engine/configure-windows/view-or-configure-the-backup-compression-default-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="1b86a-170">For information about how to view the current setting of this option,  see [View or Configure the backup compression default Server Configuration Option](../../database-engine/configure-windows/view-or-configure-the-backup-compression-default-server-configuration-option.md).</span></span>|  
|<span data-ttu-id="1b86a-171">**Comprimi backup**</span><span class="sxs-lookup"><span data-stu-id="1b86a-171">**Compress backup**</span></span>|<span data-ttu-id="1b86a-172">Fare clic su questa opzione per comprimere il backup, indipendentemente dall'impostazione predefinita a livello di server.</span><span class="sxs-lookup"><span data-stu-id="1b86a-172">Click to compress the backup, regardless of the server-level default.</span></span><br /><br /> <span data-ttu-id="1b86a-173">**\*\* Importante \*\*** Per impostazione predefinita, la compressione aumenta significativamente l'uso della CPU e la CPU aggiuntiva usata dal processo di compressione può avere un impatto negativo sulle operazioni simultanee.</span><span class="sxs-lookup"><span data-stu-id="1b86a-173">**\*\* Important \*\*** By default, compression significantly increases CPU usage, and the additional CPU consumed by the compression process might adversely affect concurrent operations.</span></span> <span data-ttu-id="1b86a-174">Potrebbe pertanto essere necessario creare backup compressi con priorità bassa in una sessione in cui l'utilizzo della CPU è limitato da [Resource Governor](../resource-governor/resource-governor.md).</span><span class="sxs-lookup"><span data-stu-id="1b86a-174">Therefore, you might want to create low-priority compressed backups in a session whose CPU usage is limited by [Resource Governor](../resource-governor/resource-governor.md).</span></span> <span data-ttu-id="1b86a-175">Per ulteriori informazioni, vedere [Utilizzo di Resource Governor per limitare l'utilizzo della CPU da parte della compressione dei backup &#40;Transact-SQL&#41;](../backup-restore/use-resource-governor-to-limit-cpu-usage-by-backup-compression-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="1b86a-175">For more information, see [Use Resource Governor to Limit CPU Usage by Backup Compression &#40;Transact-SQL&#41;](../backup-restore/use-resource-governor-to-limit-cpu-usage-by-backup-compression-transact-sql.md).</span></span>|  
|<span data-ttu-id="1b86a-176">**Non comprimere il backup**</span><span class="sxs-lookup"><span data-stu-id="1b86a-176">**Do not compress backup**</span></span>|<span data-ttu-id="1b86a-177">Fare clic su questa opzione per creare un backup non compresso, indipendentemente dall'impostazione predefinita a livello di server.</span><span class="sxs-lookup"><span data-stu-id="1b86a-177">Click to create an uncompressed backup, regardless of the server-level default.</span></span>|  
  
 <span data-ttu-id="1b86a-178">**Visualizza codice T-SQL**</span><span class="sxs-lookup"><span data-stu-id="1b86a-178">**View T-SQL**</span></span>  
 <span data-ttu-id="1b86a-179">Consente di visualizzare le istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] eseguite sul server per questa attività, in base alle opzioni selezionate.</span><span class="sxs-lookup"><span data-stu-id="1b86a-179">View the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements performed against the server for this task, based on the selected options.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1b86a-180">Se il numero di oggetti interessato dall'attività è elevato, la visualizzazione del codice potrebbe richiedere una considerevole quantità di tempo.</span><span class="sxs-lookup"><span data-stu-id="1b86a-180">When the number of objects affected is large, this display can take a considerable amount of time.</span></span>  
  
## <a name="new-connection-dialog-box"></a><span data-ttu-id="1b86a-181">Finestra di dialogo Nuova connessione</span><span class="sxs-lookup"><span data-stu-id="1b86a-181">New Connection Dialog Box</span></span>  
 <span data-ttu-id="1b86a-182">**Nome connessione**</span><span class="sxs-lookup"><span data-stu-id="1b86a-182">**Connection name**</span></span>  
 <span data-ttu-id="1b86a-183">Consente di immettere un nome per la nuova connessione.</span><span class="sxs-lookup"><span data-stu-id="1b86a-183">Enter a name for the new connection.</span></span>  
  
 <span data-ttu-id="1b86a-184">**Selezionare o immettere il nome di un server**</span><span class="sxs-lookup"><span data-stu-id="1b86a-184">**Select or enter a server name**</span></span>  
 <span data-ttu-id="1b86a-185">Consente di selezionare il server a cui connettersi per l'esecuzione dell'attività.</span><span class="sxs-lookup"><span data-stu-id="1b86a-185">Select a server to connect to when performing this task.</span></span>  
  
 <span data-ttu-id="1b86a-186">**Aggiorna**</span><span class="sxs-lookup"><span data-stu-id="1b86a-186">**Refresh**</span></span>  
 <span data-ttu-id="1b86a-187">Consente di aggiornare l'elenco dei server disponibili.</span><span class="sxs-lookup"><span data-stu-id="1b86a-187">Refresh the list of available servers.</span></span>  
  
 <span data-ttu-id="1b86a-188">**Immettere le informazioni per l'accesso al server**</span><span class="sxs-lookup"><span data-stu-id="1b86a-188">**Enter information to log on to the server**</span></span>  
 <span data-ttu-id="1b86a-189">Consente di specificare le opzioni di autenticazione per l'accesso al server.</span><span class="sxs-lookup"><span data-stu-id="1b86a-189">Specify how to authenticate against the server.</span></span>  
  
 <span data-ttu-id="1b86a-190">**Usa la sicurezza integrata di Windows NT**</span><span class="sxs-lookup"><span data-stu-id="1b86a-190">**Use Windows integrated security**</span></span>  
 <span data-ttu-id="1b86a-191">Consente di connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)] di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="1b86a-191">Connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] with Windows Authentication.</span></span>  
  
 <span data-ttu-id="1b86a-192">**Usa nome utente e password specifici**</span><span class="sxs-lookup"><span data-stu-id="1b86a-192">**Use a specific user name and password**</span></span>  
 <span data-ttu-id="1b86a-193">Consente di connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)] di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando l'autenticazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1b86a-193">Connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="1b86a-194">Questa opzione non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="1b86a-194">This option is not available.</span></span>  
  
 <span data-ttu-id="1b86a-195">**Nome utente**</span><span class="sxs-lookup"><span data-stu-id="1b86a-195">**User name**</span></span>  
 <span data-ttu-id="1b86a-196">Consente di specificare un account di accesso di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] da utilizzare per l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="1b86a-196">Provide a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login to use when authenticating.</span></span> <span data-ttu-id="1b86a-197">Questa opzione non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="1b86a-197">This option is not available.</span></span>  
  
 <span data-ttu-id="1b86a-198">**Password**</span><span class="sxs-lookup"><span data-stu-id="1b86a-198">**Password**</span></span>  
 <span data-ttu-id="1b86a-199">Consente di specificare una password da utilizzare per l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="1b86a-199">Provide a password to use when authenticating.</span></span> <span data-ttu-id="1b86a-200">Questa opzione non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="1b86a-200">This option is not available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b86a-201">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1b86a-201">See Also</span></span>  
 [<span data-ttu-id="1b86a-202">BACKUP &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1b86a-202">BACKUP &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/backup-transact-sql)  
  
  
