---
title: Ripristinare un backup del log delle transazioni (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- sql12.swb.restoretlog.options.f1
- sql12.swb.restoretlog.general.f1
helpviewer_keywords:
- restore log
- backing up transaction logs [SQL Server], restoring
- transaction log backups [SQL Server], restoring
- restoring transaction logs [SQL Server], restoring backups
- transaction log restores [SQL Server], SQL Server Management Studio
ms.assetid: 1de2b888-78a6-4fb2-a647-ba4bf097caf3
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 68fe4bbc199d6555bd490d25f92491100b8bbfcf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635672"
---
# <a name="restore-a-transaction-log-backup-sql-server"></a><span data-ttu-id="d0ccf-102">Ripristinare un backup del log delle transazioni (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="d0ccf-102">Restore a Transaction Log Backup (SQL Server)</span></span>
  <span data-ttu-id="d0ccf-103">In questo argomento viene descritto il ripristino di un backup del log delle transazioni in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d0ccf-103">This topic describes how to restore a transaction log backup in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="d0ccf-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="d0ccf-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="d0ccf-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="d0ccf-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="d0ccf-106">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="d0ccf-106">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="d0ccf-107">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="d0ccf-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="d0ccf-108">**Per ripristinare un backup del log delle transazioni utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="d0ccf-108">**To restore a transaction log backup, using:**</span></span>  
  
     [<span data-ttu-id="d0ccf-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d0ccf-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="d0ccf-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d0ccf-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   [<span data-ttu-id="d0ccf-111">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="d0ccf-111">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="d0ccf-112">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="d0ccf-112">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="d0ccf-113">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="d0ccf-113">Prerequisites</span></span>  
  
-   <span data-ttu-id="d0ccf-114">È necessario ripristinare i backup in base all'ordine in cui sono stati creati.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-114">Backups must be restored in the order in which they were created.</span></span> <span data-ttu-id="d0ccf-115">Prima di ripristinare un determinato backup del log delle transazioni, è necessario ripristinare i backup precedenti riportati di seguito senza eseguire il rollback delle transazioni di cui non è stato eseguito il commit, ovvero utilizzando WITH NORECOVERY:</span><span class="sxs-lookup"><span data-stu-id="d0ccf-115">Before you can restore a particular transaction log backup, you must first restore the following previous backups without rolling back uncommitted transactions, that is WITH NORECOVERY:</span></span>  
  
    -   <span data-ttu-id="d0ccf-116">Il backup completo del database e l'eventuale ultimo backup differenziale che precedono il backup del log delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-116">The full database backup and the last differential backup, if any, taken before the particular transaction log backup.</span></span> <span data-ttu-id="d0ccf-117">Prima della creazione del backup completo o differenziale del database più recente, è necessario che il database utilizzi il modello di recupero con registrazione completa o il modello di recupero con registrazione minima delle operazioni bulk.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-117">Before the most recent full or differential database backup was created, the database must have been using the full recovery model or bulk-logged recovery model.</span></span>  
  
    -   <span data-ttu-id="d0ccf-118">Tutti i backup del log delle transazioni eseguiti dopo il backup completo del database o il backup differenziale (in caso di ripristino di un backup) e prima del backup del log delle transazioni specifico.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-118">All transaction log backups taken after the full database backup or the differential backup (if you restore one) and before the particular transaction log backup.</span></span> <span data-ttu-id="d0ccf-119">I backup del log devono essere applicati nella sequenza in cui sono stati creati, senza gap nella catena di log.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-119">Log backups must be applied in the sequence in which they were created, without any gaps in the log chain.</span></span>  
  
         <span data-ttu-id="d0ccf-120">Per altre informazioni sui backup di log delle transazioni, vedere [Backup di log delle transazioni &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) e [Applicare backup di log delle transazioni &#40;SQL Server&#41;](apply-transaction-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="d0ccf-120">For more information about transaction log backups, see [Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) and [Apply Transaction Log Backups &#40;SQL Server&#41;](apply-transaction-log-backups-sql-server.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="d0ccf-121">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="d0ccf-121">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="d0ccf-122">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="d0ccf-122">Permissions</span></span>  
 <span data-ttu-id="d0ccf-123">Le autorizzazioni per l'istruzione RESTORE vengono assegnate ai ruoli in cui le informazioni sull'appartenenza sono sempre disponibili per il server.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-123">RESTORE permissions are given to roles in which membership information is always readily available to the server.</span></span> <span data-ttu-id="d0ccf-124">Poiché è possibile controllare l'appartenenza ai ruoli predefiniti del database solo quando il database è accessibile e non è danneggiato, condizioni che non risultano sempre vere quando si esegue un'operazione RESTORE, i membri del ruolo predefinito del database **db_owner** non dispongono delle autorizzazioni per l'istruzione RESTORE.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-124">Because fixed database role membership can be checked only when the database is accessible and undamaged, which is not always the case when RESTORE is executed, members of the **db_owner** fixed database role do not have RESTORE permissions.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="d0ccf-125">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d0ccf-125">Using SQL Server Management Studio</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="d0ccf-126">Il normale processo di ripristino prevede la selezione dei backup di log nella finestra di dialogo **Ripristina database** insieme ai backup differenziali e dei dati.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-126">The normal process of a restore is to select the log backups in the **Restore Database** dialog box along with the data and differential backups.</span></span>  
  
#### <a name="to-restore-a-transaction-log-backup"></a><span data-ttu-id="d0ccf-127">Per ripristinare un backup del log delle transazioni</span><span class="sxs-lookup"><span data-stu-id="d0ccf-127">To restore a transaction log backup</span></span>  
  
1.  <span data-ttu-id="d0ccf-128">Dopo aver stabilito la connessione all'istanza appropriata del [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Esplora oggetti fare clic sul nome del server per espanderne l'albero.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-128">After connecting to the appropriate instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="d0ccf-129">Espandere **Database**e, a seconda del database, selezionare un database utente o espandere **Database di sistema** e selezionare un database di sistema.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-129">Expand **Databases**, and, depending on the database, either select a user database or expand **System Databases** and select a system database.</span></span>  
  
3.  <span data-ttu-id="d0ccf-130">Fare clic con il pulsante destro del mouse sul database, scegliere **Attività**, **Ripristina**, quindi fare clic su **Log delle transazioni**per aprire la finestra di dialogo **Ripristina log delle transazioni** .</span><span class="sxs-lookup"><span data-stu-id="d0ccf-130">Right-click the database, point to **Tasks**, point to **Restore**, and then click **Transaction Log**, which opens the **Restore Transaction Log** dialog box.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d0ccf-131">Se **Log delle transazioni** non è disponibile, potrebbe essere necessario ripristinare un backup completo o differenziale.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-131">If **Transaction Log** is grayed out, you may need to restore a full or differential backup first.</span></span> <span data-ttu-id="d0ccf-132">Utilizzare la finestra di dialogo di backup **Database** .</span><span class="sxs-lookup"><span data-stu-id="d0ccf-132">Use the **Database** backup dialog box.</span></span>  
  
4.  <span data-ttu-id="d0ccf-133">Nella casella di riepilogo a discesa **Database** della pagina **Generale** selezionare il nome di un database.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-133">On the **General** page, in the **Database** list box, select the name of a database.</span></span> <span data-ttu-id="d0ccf-134">Tale elenco include solo database nello stato di ripristino in corso.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-134">Only databases in the restoring state are listed.</span></span>  
  
5.  <span data-ttu-id="d0ccf-135">Per specificare l'origine e il percorso dei set di backup da ripristinare, fare clic su una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d0ccf-135">To specify the source and location of the backup sets to restore, click one of the following options:</span></span>  
  
    -   <span data-ttu-id="d0ccf-136">**Da backup precedenti del database**</span><span class="sxs-lookup"><span data-stu-id="d0ccf-136">**From previous backups of database**</span></span>  
  
         <span data-ttu-id="d0ccf-137">Selezionare il database da ripristinare dall'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-137">Select the database to restore from the drop-down list.</span></span> <span data-ttu-id="d0ccf-138">Nell'elenco sono inclusi solo i database di cui è stato eseguito il backup in base alla cronologia dei backup di **msdb** .</span><span class="sxs-lookup"><span data-stu-id="d0ccf-138">The list contains only databases that have been backed up according to the **msdb** backup history.</span></span>  
  
    -   <span data-ttu-id="d0ccf-139">**Da file o nastro**</span><span class="sxs-lookup"><span data-stu-id="d0ccf-139">**From file or tape**</span></span>  
  
         <span data-ttu-id="d0ccf-140">Fare clic sul pulsante Sfoglia ( **...** ) per aprire la finestra di dialogo **Seleziona dispositivi di backup** .</span><span class="sxs-lookup"><span data-stu-id="d0ccf-140">Click the browse (**...**) button to open the **Select backup devices** dialog box.</span></span> <span data-ttu-id="d0ccf-141">Nella casella **Tipi di supporti di backup** selezionare uno dei tipi di dispositivi elencati.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-141">In the **Backup media type** box, select one of the listed device types.</span></span> <span data-ttu-id="d0ccf-142">Per selezionare uno o più dispositivi per la casella **Supporti di backup** , fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-142">To select one or more devices for the **Backup media** box, click **Add**.</span></span>  
  
         <span data-ttu-id="d0ccf-143">Dopo avere aggiunto i dispositivi desiderati nella casella di riepilogo **Dispositivi di backup** , fare clic su **OK** per tornare alla pagina **Generale** .</span><span class="sxs-lookup"><span data-stu-id="d0ccf-143">After you add the devices you want to the **Backup media** list box, click **OK** to return to the **General** page.</span></span>  
  
6.  <span data-ttu-id="d0ccf-144">Nella griglia **Selezionare i backup del log delle transazioni da ripristinare** selezionare i backup che si desidera ripristinare.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-144">In the **Select the transaction log backups to restore** grid, select the backups to restore.</span></span> <span data-ttu-id="d0ccf-145">Nella griglia sono elencati i backup del log delle transazioni disponibili per il database selezionato.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-145">This grid lists the transaction log backups available for the selected database.</span></span> <span data-ttu-id="d0ccf-146">Un backup di log è disponibile solo se il relativo valore **Primo LSN** è maggiore del valore **Ultimo LSN** del database.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-146">A log backup is available only if its **First LSN** greater than the **Last LSN** of the database.</span></span> <span data-ttu-id="d0ccf-147">I backup di log vengono elencati in base all'ordine dei numeri di sequenza del file di log (LSN) in essi contenuti e devono essere ripristinati in base a tale ordine.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-147">Log backups are listed in the order of the log sequence numbers (LSN) they contain, and they must be restored in this order.</span></span>  
  
     <span data-ttu-id="d0ccf-148">Nella tabella seguente vengono elencate le intestazioni delle colonne della griglia con una descrizione dei rispettivi valori.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-148">The following table lists the column headers of the grid and describes their values.</span></span>  
  
    |<span data-ttu-id="d0ccf-149">Intestazione</span><span class="sxs-lookup"><span data-stu-id="d0ccf-149">Header</span></span>|<span data-ttu-id="d0ccf-150">valore</span><span class="sxs-lookup"><span data-stu-id="d0ccf-150">Value</span></span>|  
    |------------|-----------|  
    |<span data-ttu-id="d0ccf-151">**Restore**</span><span class="sxs-lookup"><span data-stu-id="d0ccf-151">**Restore**</span></span>|<span data-ttu-id="d0ccf-152">Le caselle di controllo selezionate indicano i set di backup da ripristinare.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-152">Selected check boxes indicate the backup sets to be restored.</span></span>|  
    |<span data-ttu-id="d0ccf-153">**Nome**</span><span class="sxs-lookup"><span data-stu-id="d0ccf-153">**Name**</span></span>|<span data-ttu-id="d0ccf-154">Nome del set di backup.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-154">Name of the backup set.</span></span>|  
    |<span data-ttu-id="d0ccf-155">**Componente**</span><span class="sxs-lookup"><span data-stu-id="d0ccf-155">**Component**</span></span>|<span data-ttu-id="d0ccf-156">Componente di cui è stato eseguito il backup: **database**, **file** o \<blank>, nel caso dei log delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-156">Backed-up component: **Database**, **File**, or \<blank> (for transaction logs).</span></span>|  
    |<span data-ttu-id="d0ccf-157">**Database**</span><span class="sxs-lookup"><span data-stu-id="d0ccf-157">**Database**</span></span>|<span data-ttu-id="d0ccf-158">Nome del database su cui viene eseguita l'operazione di backup.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-158">Name of the database involved in the backup operation.</span></span>|  
    |<span data-ttu-id="d0ccf-159">**Data inizio**</span><span class="sxs-lookup"><span data-stu-id="d0ccf-159">**Start Date**</span></span>|<span data-ttu-id="d0ccf-160">Data e ora di inizio dell'operazione di backup, visualizzate in base alle impostazioni internazionali del client.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-160">Date and time when the backup operation began, presented in the regional setting of the client.</span></span>|  
    |<span data-ttu-id="d0ccf-161">**Data fine**</span><span class="sxs-lookup"><span data-stu-id="d0ccf-161">**Finish Date**</span></span>|<span data-ttu-id="d0ccf-162">Data e ora di fine dell'operazione di backup, visualizzate in base alle impostazioni internazionali del client.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-162">Date and time when the backup operation finished, presented in the regional setting of the client.</span></span>|  
    |<span data-ttu-id="d0ccf-163">**Primo LSN**</span><span class="sxs-lookup"><span data-stu-id="d0ccf-163">**First LSN**</span></span>|<span data-ttu-id="d0ccf-164">Numero di sequenza del file di log della prima transazione nel set di backup.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-164">Log sequence number of the first transaction in the backup set.</span></span> <span data-ttu-id="d0ccf-165">Vuoto per i backup dei file.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-165">Blank for file backups.</span></span>|  
    |<span data-ttu-id="d0ccf-166">**Ultimo LSN**</span><span class="sxs-lookup"><span data-stu-id="d0ccf-166">**Last LSN**</span></span>|<span data-ttu-id="d0ccf-167">Numero di sequenza del file di log dell'ultima transazione nel set di backup.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-167">Log sequence number of the last transaction in the backup set.</span></span> <span data-ttu-id="d0ccf-168">Vuoto per i backup dei file.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-168">Blank for file backups.</span></span>|  
    |<span data-ttu-id="d0ccf-169">**LSN checkpoint**</span><span class="sxs-lookup"><span data-stu-id="d0ccf-169">**Checkpoint LSN**</span></span>|<span data-ttu-id="d0ccf-170">Numero di sequenza del file di log del checkpoint più recente al momento della creazione del backup.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-170">Log sequence number of the most recent checkpoint at the time the backup was created.</span></span>|  
    |<span data-ttu-id="d0ccf-171">**LSN completo**</span><span class="sxs-lookup"><span data-stu-id="d0ccf-171">**Full LSN**</span></span>|<span data-ttu-id="d0ccf-172">Numero di sequenza del file di log dell'operazione più recente di backup completo del database.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-172">Log sequence number of the most recent full database backup.</span></span>|  
    |<span data-ttu-id="d0ccf-173">**Server**</span><span class="sxs-lookup"><span data-stu-id="d0ccf-173">**Server**</span></span>|<span data-ttu-id="d0ccf-174">Nome dell'istanza del motore di database in cui è stata eseguita l'operazione di backup.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-174">Name of the Database Engine instance that performed the backup operation.</span></span>|  
    |<span data-ttu-id="d0ccf-175">**Nome utente**</span><span class="sxs-lookup"><span data-stu-id="d0ccf-175">**User Name**</span></span>|<span data-ttu-id="d0ccf-176">Nome dell'utente che ha eseguito l'operazione di backup.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-176">Name of the user who performed the backup operation.</span></span>|  
    |<span data-ttu-id="d0ccf-177">**Dimensione**</span><span class="sxs-lookup"><span data-stu-id="d0ccf-177">**Size**</span></span>|<span data-ttu-id="d0ccf-178">Dimensioni in byte del set di backup.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-178">Size of the backup set in bytes.</span></span>|  
    |<span data-ttu-id="d0ccf-179">**Posizione**</span><span class="sxs-lookup"><span data-stu-id="d0ccf-179">**Position**</span></span>|<span data-ttu-id="d0ccf-180">Posizione del set di backup nel volume.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-180">Position of the backup set in the volume.</span></span>|  
    |<span data-ttu-id="d0ccf-181">**Scadenza**</span><span class="sxs-lookup"><span data-stu-id="d0ccf-181">**Expiration**</span></span>|<span data-ttu-id="d0ccf-182">Data e ora di scadenza del set di backup.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-182">Date and time the backup set expires.</span></span>|  
  
7.  <span data-ttu-id="d0ccf-183">Selezionare uno degli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="d0ccf-183">Select one of the following:</span></span>  
  
    -   <span data-ttu-id="d0ccf-184">**Temporizzazione**</span><span class="sxs-lookup"><span data-stu-id="d0ccf-184">**Point in time**</span></span>  
  
         <span data-ttu-id="d0ccf-185">Mantenere l'impostazione predefinita (**Più recente**) oppure selezionare una data e un'ora specifiche, facendo clic sul pulsante Sfoglia per visualizzare la finestra di dialogo **Ripristino temporizzato** .</span><span class="sxs-lookup"><span data-stu-id="d0ccf-185">Either retain the default (**Most recent possible**) or select a specific date and time by clicking the browse button, which opens the **Point in Time Restore** dialog box.</span></span>  
  
    -   <span data-ttu-id="d0ccf-186">**Transazione contrassegnata**</span><span class="sxs-lookup"><span data-stu-id="d0ccf-186">**Marked transaction**</span></span>  
  
         <span data-ttu-id="d0ccf-187">Consente di ripristinare il database fino a una transazione contrassegnata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-187">Restore the database to a previously marked transaction.</span></span> <span data-ttu-id="d0ccf-188">Se si seleziona questa opzione, verrà visualizzata la finestra di dialogo **Seleziona transazione contrassegnata** , che include una griglia in cui sono elencate le transazioni contrassegnate disponibili nei backup del log delle transazioni selezionati.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-188">Selecting this option launches the **Select Marked Transaction** dialog box, which displays a grid listing the marked transactions available in the selected transaction log backups.</span></span>  
  
         <span data-ttu-id="d0ccf-189">Per impostazione predefinita, il ripristino viene eseguito fino alla transazione contrassegnata esclusa.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-189">By default, the restore is up to, but excluding, the marked transaction.</span></span> <span data-ttu-id="d0ccf-190">Per ripristinare anche la transazione contrassegnata, selezionare l'opzione **Includi transazione contrassegnata**.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-190">To restore the marked transaction also, select **Include marked transaction**.</span></span>  
  
         <span data-ttu-id="d0ccf-191">Nella tabella seguente vengono elencate le intestazioni delle colonne della griglia con una descrizione dei rispettivi valori.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-191">The following table lists the column headers of the grid and describes their values.</span></span>  
  
        |<span data-ttu-id="d0ccf-192">Intestazione</span><span class="sxs-lookup"><span data-stu-id="d0ccf-192">Header</span></span>|<span data-ttu-id="d0ccf-193">valore</span><span class="sxs-lookup"><span data-stu-id="d0ccf-193">Value</span></span>|  
        |------------|-----------|  
        |\<blank>|<span data-ttu-id="d0ccf-194">Consente di visualizzare una casella di controllo per selezionare il contrassegno.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-194">Displays a checkbox for selecting the mark.</span></span>|  
        |<span data-ttu-id="d0ccf-195">**Contrassegno transazione**</span><span class="sxs-lookup"><span data-stu-id="d0ccf-195">**Transaction Mark**</span></span>|<span data-ttu-id="d0ccf-196">Nome della transazione contrassegnata specificato dall'utente durante l'esecuzione del commit della transazione.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-196">Name of the marked transaction specified by the user when the transaction was committed.</span></span>|  
        |<span data-ttu-id="d0ccf-197">**Data**</span><span class="sxs-lookup"><span data-stu-id="d0ccf-197">**Date**</span></span>|<span data-ttu-id="d0ccf-198">Data e ora assegnate alla transazione quando ne è stato eseguito il commit.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-198">Date and time of the transaction when it was committed.</span></span> <span data-ttu-id="d0ccf-199">Vengono visualizzate la data e l'ora della transazione registrate nella tabella **msdbgmarkhistory** , non nella data e ora del computer client.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-199">Transaction date and time are displayed as recorded in the **msdbgmarkhistory** table, not in the client computer's date and time.</span></span>|  
        |<span data-ttu-id="d0ccf-200">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="d0ccf-200">**Description**</span></span>|<span data-ttu-id="d0ccf-201">Eventuale descrizione della transazione contrassegnata specificata dall'utente quando è stato eseguito il commit della transazione.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-201">Description of marked transaction specified by the user when the transaction was committed (if any).</span></span>|  
        |<span data-ttu-id="d0ccf-202">**LSN**</span><span class="sxs-lookup"><span data-stu-id="d0ccf-202">**LSN**</span></span>|<span data-ttu-id="d0ccf-203">Numero di sequenza del file di log (LSN) della transazione contrassegnata.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-203">Log sequence number of the marked transaction.</span></span>|  
        |<span data-ttu-id="d0ccf-204">**Database**</span><span class="sxs-lookup"><span data-stu-id="d0ccf-204">**Database**</span></span>|<span data-ttu-id="d0ccf-205">Nome del database in cui è stato eseguito il commit della transazione contrassegnata.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-205">Name of the database where the marked transaction was committed.</span></span>|  
        |<span data-ttu-id="d0ccf-206">**Nome utente**</span><span class="sxs-lookup"><span data-stu-id="d0ccf-206">**User Name**</span></span>|<span data-ttu-id="d0ccf-207">Nome dell'utente del database che ha eseguito il commit della transazione contrassegnata.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-207">Name of the database user who committed the marked transaction.</span></span>|  
  
8.  <span data-ttu-id="d0ccf-208">Per visualizzare o selezionare le opzioni avanzate, fare clic su **Opzioni** nel riquadro **Selezione pagina** .</span><span class="sxs-lookup"><span data-stu-id="d0ccf-208">To view or select the advanced options, click **Options** in the **Select a page** pane.</span></span>  
  
9. <span data-ttu-id="d0ccf-209">Nella sezione **Opzioni di ripristino** le scelte disponibili sono:</span><span class="sxs-lookup"><span data-stu-id="d0ccf-209">In the **Restore options** section, the choices are:</span></span>  
  
    -   <span data-ttu-id="d0ccf-210">**Mantieni le impostazioni di replica (WITH KEEP_REPLICATION)**</span><span class="sxs-lookup"><span data-stu-id="d0ccf-210">**Preserve the replication settings (WITH KEEP_REPLICATION)**</span></span>  
  
         <span data-ttu-id="d0ccf-211">Consente di mantenere le impostazioni di replica durante il ripristino di un database pubblicato in un server diverso da quello in cui è stato creato il database.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-211">Preserves the replication settings when restoring a published database to a server other than the server where the database was created.</span></span>  
  
         <span data-ttu-id="d0ccf-212">Questa opzione è disponibile solo con l'opzione **lascia il database pronto per l'utilizzo eseguendo il rollback delle transazioni di cui non è stato eseguito il commit...** (descritta più avanti), equivalente al ripristino di un backup con l' `RECOVERY` opzione.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-212">This option is available only with the **Leave the database ready for use by rolling back the uncommitted transactions...** option (described later), which is equivalent to restoring a backup with the `RECOVERY` option.</span></span>  
  
         <span data-ttu-id="d0ccf-213">La selezione di questa opzione equivale all'utilizzo dell' `KEEP_REPLICATION` opzione in un' [!INCLUDE[tsql](../../includes/tsql-md.md)] `RESTORE` istruzione.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-213">Checking this option is equivalent to using the `KEEP_REPLICATION` option in a [!INCLUDE[tsql](../../includes/tsql-md.md)]`RESTORE` statement.</span></span>  
  
    -   <span data-ttu-id="d0ccf-214">**Chiedi conferma prima del ripristino di ogni backup**</span><span class="sxs-lookup"><span data-stu-id="d0ccf-214">**Prompt before restoring each backup**</span></span>  
  
         <span data-ttu-id="d0ccf-215">Prima di ripristinare ogni set di backup successivo al primo, questa opzione visualizza la finestra di dialogo **Continua con il ripristino** , in cui viene richiesta conferma della continuazione della sequenza di ripristino.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-215">Before restoring each backup set (after the first), this option brings up the **Continue with Restore** dialog box, which asks you to indicate whether you want to continue the restore sequence.</span></span> <span data-ttu-id="d0ccf-216">In questa finestra di dialogo vengono visualizzati il nome del set di supporti successivo, se disponibile, il nome del set di backup e la descrizione del set di backup.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-216">This dialog displays the name of the next media set (if available), the backup set name, and backup set description.</span></span>  
  
         <span data-ttu-id="d0ccf-217">Questa opzione risulta particolarmente utile quando è necessario cambiare nastri per diversi set di supporti.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-217">This option is particularly useful when you must swap tapes for different media sets.</span></span> <span data-ttu-id="d0ccf-218">Ad esempio, è possibile utilizzarla quando nel server è disponibile un solo dispositivo nastro.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-218">For example, you can use it when the server has only one tape device.</span></span> <span data-ttu-id="d0ccf-219">Attendere di essere pronti per procedere prima di fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-219">Wait until you are ready to proceed before clicking **OK**.</span></span>  
  
         <span data-ttu-id="d0ccf-220">Se si fa clic su **No** , il database verrà mantenuto nello stato di ripristino in corso.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-220">Clicking **No** leaves the database in the restoring state.</span></span> <span data-ttu-id="d0ccf-221">Se lo si desidera, è possibile continuare la sequenza di ripristino dopo il completamento dell'ultimo ripristino.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-221">At your convenience, you can continue the restore sequence after the last restore that completed.</span></span> <span data-ttu-id="d0ccf-222">Se il backup successivo è un backup di dati o differenziale, utilizzare nuovamente l'attività **Ripristina database** .</span><span class="sxs-lookup"><span data-stu-id="d0ccf-222">If the next backup is a data or differential backup, use the **Restore Database** task again.</span></span> <span data-ttu-id="d0ccf-223">Se il backup successivo è un backup del log, utilizzare l'attività **Ripristina log delle transazioni** .</span><span class="sxs-lookup"><span data-stu-id="d0ccf-223">If the next backup is a log backup, use the **Restore Transaction Log** task.</span></span>  
  
    -   <span data-ttu-id="d0ccf-224">**Limita accesso al database ripristinato (WITH RESTRICTED_USER)**</span><span class="sxs-lookup"><span data-stu-id="d0ccf-224">**Restrict access to the restored database (WITH RESTRICTED_USER)**</span></span>  
  
         <span data-ttu-id="d0ccf-225">Consente di rendere disponibile il database ripristinato solo per i membri di **db_owner**, **dbcreator**o **sysadmin**.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-225">Makes the restored database available only to the members of **db_owner**, **dbcreator**, or **sysadmin**.</span></span>  
  
         <span data-ttu-id="d0ccf-226">La selezione di questa opzione è sinonimo dell'utilizzo dell' `RESTRICTED_USER` opzione in un' [!INCLUDE[tsql](../../includes/tsql-md.md)] `RESTORE` istruzione.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-226">Checking this option is synonymous to using the `RESTRICTED_USER` option in a [!INCLUDE[tsql](../../includes/tsql-md.md)]`RESTORE` statement.</span></span>  
  
10. <span data-ttu-id="d0ccf-227">Nel gruppo di opzioni **Stato di recupero** specificare lo stato desiderato per il database dopo l'operazione di ripristino.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-227">For the **Recovery state** options, specify the state of the database after the restore operation.</span></span>  
  
    -   <span data-ttu-id="d0ccf-228">**Lascia il database pronto per l'uso eseguendo il rollback delle transazioni di cui non è stato eseguito il commit. I log delle transazioni aggiuntivi non possono essere ripristinati. (RESTORE WITH RECOVERY)**</span><span class="sxs-lookup"><span data-stu-id="d0ccf-228">**Leave the database ready for use by rolling back uncommitted transactions. Additional transaction logs cannot be restored. (RESTORE WITH RECOVERY)**</span></span>  
  
         <span data-ttu-id="d0ccf-229">Esegue il recupero del database.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-229">Recovers the database.</span></span> <span data-ttu-id="d0ccf-230">Questa opzione equivale all' `RECOVERY` opzione in un' [!INCLUDE[tsql](../../includes/tsql-md.md)] `RESTORE` istruzione.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-230">This option is equivalent to the `RECOVERY` option in a [!INCLUDE[tsql](../../includes/tsql-md.md)]`RESTORE` statement.</span></span>  
  
         <span data-ttu-id="d0ccf-231">Selezionare questa opzione solo se non sono disponibili file di log da ripristinare.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-231">Choose this option only if you have no log files you want to restore.</span></span>  
  
    -   <span data-ttu-id="d0ccf-232">**Lascia il database non operativo e non eseguire il rollback delle transazioni di cui non è stato eseguito il commit. I log delle transazioni aggiuntivi possono essere ripristinati. (RESTORE WITH NORECOVERY)**</span><span class="sxs-lookup"><span data-stu-id="d0ccf-232">**Leave the database non-operational, and do not roll back uncommitted transactions. Additional transaction logs can be restored. (RESTORE WITH NORECOVERY)**</span></span>  
  
         <span data-ttu-id="d0ccf-233">Il database viene lasciato nello stato `RESTORING`.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-233">Leaves the database unrecovered, in the `RESTORING` state.</span></span> <span data-ttu-id="d0ccf-234">Questa opzione equivale all'utilizzo dell' `NORECOVERY` opzione in un' [!INCLUDE[tsql](../../includes/tsql-md.md)] `RESTORE` istruzione.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-234">This option is equivalent to using the `NORECOVERY` option in a [!INCLUDE[tsql](../../includes/tsql-md.md)]`RESTORE` statement.</span></span>  
  
         <span data-ttu-id="d0ccf-235">Quando si seleziona questa opzione, l'opzione **Mantieni le impostazioni di replica** non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-235">When you choose this option, the **Preserve replication settings** option is unavailable.</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="d0ccf-236">Nel caso di un database mirror o secondario, selezionare sempre questa opzione.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-236">For a mirror or secondary database, always select this option.</span></span>  
  
    -   <span data-ttu-id="d0ccf-237">**Lascia il database in modalità sola lettura. Annulla le transazioni di cui non è stato eseguito il commit e salva le azioni di rollback in un file standby in modo che gli effetti del recupero possano essere annullati. (RESTORE WITH STANDBY)**</span><span class="sxs-lookup"><span data-stu-id="d0ccf-237">**Leave the database in read-only mode. Undo uncommitted transactions, but save the undo actions in a file so that recovery effects can be reversed. (RESTORE WITH STANDBY)**</span></span>  
  
         <span data-ttu-id="d0ccf-238">Il database viene lasciato nello stato di standby.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-238">Leaves the database in a standby state.</span></span> <span data-ttu-id="d0ccf-239">Questa opzione equivale all'utilizzo dell' `STANDBY` opzione in un' [!INCLUDE[tsql](../../includes/tsql-md.md)] `RESTORE` istruzione.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-239">This option is equivalent to using the `STANDBY` option in a [!INCLUDE[tsql](../../includes/tsql-md.md)]`RESTORE` statement.</span></span>  
  
         <span data-ttu-id="d0ccf-240">Se si seleziona questa opzione è necessario specificare un file standby.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-240">Choosing this option requires that you specify a standby file.</span></span>  
  
11. <span data-ttu-id="d0ccf-241">Facoltativamente, specificare un nome per il file standby nella casella di testo **File standby** .</span><span class="sxs-lookup"><span data-stu-id="d0ccf-241">Optionally, specify a standby file name in the **Standby file** text box.</span></span> <span data-ttu-id="d0ccf-242">Questa opzione è necessaria se il database viene lasciato in modalità sola lettura.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-242">This option is required if you leave the database in read-only mode.</span></span> <span data-ttu-id="d0ccf-243">È possibile cercare il file standby per selezionarlo oppure digitarne direttamente il percorso nella casella di testo.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-243">You can browse for the standby file or type its pathname in the text box.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="d0ccf-244">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d0ccf-244">Using Transact-SQL</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d0ccf-245">È consigliabile specificare sempre in modo esplicito WITH NORECOVERY oppure WITH RECOVERY in ogni istruzione RESTORE per evitare ambiguità.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-245">We recommend that you always explicitly specify either WITH NORECOVERY or WITH RECOVERY in every RESTORE statement to eliminate ambiguity.</span></span> <span data-ttu-id="d0ccf-246">Questa precauzione è particolarmente importante durante la scrittura di script.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-246">This is particularly important when writing scripts.</span></span>  
  
#### <a name="to-restore-a-transaction-log-backup"></a><span data-ttu-id="d0ccf-247">Per ripristinare un backup del log delle transazioni</span><span class="sxs-lookup"><span data-stu-id="d0ccf-247">To restore a transaction log backup</span></span>  
  
1.  <span data-ttu-id="d0ccf-248">Eseguire l'istruzione RESTORE LOG per applicare il backup del log delle transazioni specificando:</span><span class="sxs-lookup"><span data-stu-id="d0ccf-248">Execute the RESTORE LOG statement to apply the transaction log backup, specifying:</span></span>  
  
    -   <span data-ttu-id="d0ccf-249">Nome del database a cui verrà applicato il log delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-249">The name of the database to which the transaction log will be applied.</span></span>  
  
    -   <span data-ttu-id="d0ccf-250">Il dispositivo di backup da cui verrà ripristinato il backup del log delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-250">The backup device where the transaction log backup will be restored from.</span></span>  
  
    -   <span data-ttu-id="d0ccf-251">Clausola NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-251">The NORECOVERY clause.</span></span>  
  
     <span data-ttu-id="d0ccf-252">La sintassi di base per questa istruzione è la seguente:</span><span class="sxs-lookup"><span data-stu-id="d0ccf-252">The basic syntax for this statement is as follows:</span></span>  
  
     <span data-ttu-id="d0ccf-253">RESTORE LOG *nome_database* FROM <dispositivo_backup> WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-253">RESTORE LOG *database_name* FROM <backup_device> WITH NORECOVERY.</span></span>  
  
     <span data-ttu-id="d0ccf-254">Dove *nome_database* è il nome del database e <dispositivo_backup> è il nome del dispositivo che contiene il backup del log in fase di ripristino.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-254">Where *database_name* is the name of database and <backup_device>is the name of the device that contains the log backup being restored.</span></span>  
  
2.  <span data-ttu-id="d0ccf-255">Ripetere il passaggio 1 per ogni backup del log delle transazioni che si desidera applicare.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-255">Repeat step 1 for each transaction log backup you have to apply.</span></span>  
  
3.  <span data-ttu-id="d0ccf-256">Dopo aver ripristinato l'ultimo backup della sequenza di ripristino, per recuperare il database utilizzare una delle istruzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d0ccf-256">After restoring the last backup in your restore sequence, to recover the database use one of the following statements:</span></span>  
  
    -   <span data-ttu-id="d0ccf-257">Recuperare il database nell'ambito dell'ultima istruzione RESTORE LOG:</span><span class="sxs-lookup"><span data-stu-id="d0ccf-257">Recover the database as part of the last RESTORE LOG statement:</span></span>  
  
        ```  
        RESTORE LOG <database_name> FROM <backup_device> WITH RECOVERY;  
        GO  
        ```  
  
    -   <span data-ttu-id="d0ccf-258">Posticipare il recupero del database utilizzando un'istruzione RESTORE DATABASE separata:</span><span class="sxs-lookup"><span data-stu-id="d0ccf-258">Wait to recover the database by using a separate RESTORE DATABASE statement:</span></span>  
  
        ```  
        RESTORE LOG <database_name> FROM <backup_device> WITH NORECOVERY;   
        RESTORE DATABASE <database_name> WITH RECOVERY;  
        GO  
        ```  
  
         <span data-ttu-id="d0ccf-259">Il posticipo del recupero del database consente di verificare di avere ripristinato tutti i backup del log necessari.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-259">Waiting to recover the database gives you the opportunity to verify that you have restored all of the necessary log backups.</span></span> <span data-ttu-id="d0ccf-260">Questo approccio è spesso consigliato quando si esegue un ripristino temporizzato.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-260">This approach is often advisable when you are performing a point-in-time restore.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="d0ccf-261">Se si sta creando un database mirror, omettere il passaggio di recupero.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-261">If you are creating a mirror database, omit the recovery step.</span></span> <span data-ttu-id="d0ccf-262">Un database mirror deve rimanere nello stato RESTORING.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-262">A mirror database must remain in the RESTORING state.</span></span>  
  
###  <a name="examples-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="d0ccf-263">Esempi (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="d0ccf-263">Examples (Transact-SQL)</span></span>  
 <span data-ttu-id="d0ccf-264">Per impostazione predefinita, il database [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] utilizza il modello di recupero con registrazione minima.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-264">By default, the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database uses the simple recovery model.</span></span> <span data-ttu-id="d0ccf-265">Per gli esempi seguenti è necessario modificare questo database in modo da utilizzare il modello di recupero con registrazione completa, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="d0ccf-265">The following examples require modifying the database to use the full recovery model, as follows:</span></span>  
  
```sql  
ALTER DATABASE AdventureWorks2012 SET RECOVERY FULL;  
```  
  
#### <a name="a-applying-a-single-transaction-log-backup"></a><span data-ttu-id="d0ccf-266">R.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-266">A.</span></span> <span data-ttu-id="d0ccf-267">Applicazione di un singolo backup del log delle transazioni</span><span class="sxs-lookup"><span data-stu-id="d0ccf-267">Applying a single transaction log backup</span></span>  
 <span data-ttu-id="d0ccf-268">Nell'esempio seguente viene innanzitutto ripristinato il database [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] da un backup completo del database che risiede in un dispositivo di backup denominato `AdventureWorks2012_1`.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-268">The following example starts by restoring the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database by using a full database backup that resides on a backup device named `AdventureWorks2012_1`.</span></span> <span data-ttu-id="d0ccf-269">Viene quindi applicato il primo backup del log delle transazioni che risiede nel dispositivo di backup denominato `AdventureWorks2012_log`e</span><span class="sxs-lookup"><span data-stu-id="d0ccf-269">The example then applies the first transaction log backup that resides on a backup device named `AdventureWorks2012_log`.</span></span> <span data-ttu-id="d0ccf-270">infine viene recuperato il database.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-270">Finally, the example recovers the database.</span></span>  
  
```sql  
RESTORE DATABASE AdventureWorks2012  
   FROM AdventureWorks2012_1  
   WITH NORECOVERY;  
GO  
RESTORE LOG AdventureWorks2012  
   FROM AdventureWorks2012_log  
   WITH FILE = 1,  
   WITH NORECOVERY;  
GO  
RESTORE DATABASE AdventureWorks2012  
   WITH RECOVERY;  
GO  
```  
  
#### <a name="b-applying-multiple-transaction-log-backups"></a><span data-ttu-id="d0ccf-271">B.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-271">B.</span></span> <span data-ttu-id="d0ccf-272">Applicazione di più backup del log delle transazioni</span><span class="sxs-lookup"><span data-stu-id="d0ccf-272">Applying multiple transaction log backups</span></span>  
 <span data-ttu-id="d0ccf-273">Nell'esempio seguente viene innanzitutto ripristinato il database [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] da un backup completo del database che risiede in un dispositivo di backup denominato `AdventureWorks2012_1`.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-273">The following example starts by restoring the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database by using a full database backup that resides on a backup device named `AdventureWorks2012_1`.</span></span> <span data-ttu-id="d0ccf-274">Vengono quindi applicati in successione i primi tre backup del log delle transazioni che risiedono in uno dispositivo di backup denominato `AdventureWorks2012_log`e</span><span class="sxs-lookup"><span data-stu-id="d0ccf-274">The example then applies, one by one, the first three transaction log backups that reside on a backup device named `AdventureWorks2012_log`.</span></span> <span data-ttu-id="d0ccf-275">infine viene recuperato il database.</span><span class="sxs-lookup"><span data-stu-id="d0ccf-275">Finally, the example recovers the database.</span></span>  
  
```sql  
RESTORE DATABASE AdventureWorks2012  
   FROM AdventureWorks2012_1  
   WITH NORECOVERY;  
GO  
RESTORE LOG AdventureWorks2012  
   FROM AdventureWorks2012_log  
   WITH FILE = 1,  
   NORECOVERY;  
GO  
RESTORE LOG AdventureWorks2012  
   FROM AdventureWorks2012_log  
   WITH FILE = 2,  
   WITH NORECOVERY;  
GO  
RESTORE LOG AdventureWorks2012  
   FROM AdventureWorks2012_log  
   WITH FILE = 3,  
   WITH NORECOVERY;  
GO  
RESTORE DATABASE AdventureWorks2012  
   WITH RECOVERY;  
GO  
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="d0ccf-276">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="d0ccf-276">Related Tasks</span></span>  
  
-   [<span data-ttu-id="d0ccf-277">Eseguire il backup di un log delle transazioni &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="d0ccf-277">Back Up a Transaction Log &#40;SQL Server&#41;</span></span>](back-up-a-transaction-log-sql-server.md)  
  
-   [<span data-ttu-id="d0ccf-278">Ripristinare un backup del database &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="d0ccf-278">Restore a Database Backup &#40;SQL Server Management Studio&#41;</span></span>](restore-a-database-backup-using-ssms.md)  
  
-   [<span data-ttu-id="d0ccf-279">Ripristinare un database fino al punto di errore nel modello di recupero con registrazione completa &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d0ccf-279">Restore a Database to the Point of Failure Under the Full Recovery Model &#40;Transact-SQL&#41;</span></span>](restore-database-to-point-of-failure-full-recovery.md)  
  
-   [<span data-ttu-id="d0ccf-280">Ripristinare un database di SQL Server fino a un punto specifico &#40;modello di recupero con registrazione completa&#41;</span><span class="sxs-lookup"><span data-stu-id="d0ccf-280">Restore a SQL Server Database to a Point in Time &#40;Full Recovery Model&#41;</span></span>](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md)  
  
-   [<span data-ttu-id="d0ccf-281">Ripristinare un database fino a una transazione contrassegnata &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="d0ccf-281">Restore a Database to a Marked Transaction &#40;SQL Server Management Studio&#41;</span></span>](restore-a-database-to-a-marked-transaction-sql-server-management-studio.md)  
  
## <a name="see-also"></a><span data-ttu-id="d0ccf-282">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d0ccf-282">See Also</span></span>  
 <span data-ttu-id="d0ccf-283">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d0ccf-283">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 [<span data-ttu-id="d0ccf-284">Applicare backup di log delle transazioni &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="d0ccf-284">Apply Transaction Log Backups &#40;SQL Server&#41;</span></span>](apply-transaction-log-backups-sql-server.md)  
  
  
