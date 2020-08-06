---
title: Ripristinare un backup differenziale di database (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- full differential backups [SQL Server]
- restoring databases [SQL Server], full differential backups
- database backups [SQL Server], full differential backups
- database restores [SQL Server], full differential backups
- backing up databases [SQL Server], full differential backups
ms.assetid: 0dd971a4-ee38-4dd3-9f30-ef77fc58dd11
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: a8eab18d84efc1a990715e0d5488085252f93a7e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635675"
---
# <a name="restore-a-differential-database-backup-sql-server"></a><span data-ttu-id="7d522-102">Ripristino di un backup differenziale di database (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="7d522-102">Restore a Differential Database Backup (SQL Server)</span></span>
  <span data-ttu-id="7d522-103">In questo argomento viene descritto il ripristino di un backup differenziale del database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7d522-103">This topic describes how to restore a differential database backup in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="7d522-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="7d522-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="7d522-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="7d522-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="7d522-106">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="7d522-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="7d522-107">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="7d522-107">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="7d522-108">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="7d522-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="7d522-109">**Per ripristinare un backup differenziale di database utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="7d522-109">**To restore a differential database backup, using:**</span></span>  
  
     [<span data-ttu-id="7d522-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7d522-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="7d522-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7d522-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   [<span data-ttu-id="7d522-112">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="7d522-112">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="7d522-113">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="7d522-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="7d522-114">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="7d522-114">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="7d522-115">Non è possibile utilizzare RESTORE in una transazione esplicita o implicita.</span><span class="sxs-lookup"><span data-stu-id="7d522-115">RESTORE is not allowed in an explicit or implicit transaction.</span></span>  
  
-   <span data-ttu-id="7d522-116">I backup creati nella versione più recente di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] non possono essere ripristinati nelle versioni precedenti di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7d522-116">Backups that are created by more recent version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cannot be restored in earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="7d522-117">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]è possibile ripristinare un database utente dal backup di un database creato tramite [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] o una versione successiva.</span><span class="sxs-lookup"><span data-stu-id="7d522-117">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], you can restore a user database from a database backup that was created by using [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] or a later version.</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="7d522-118">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="7d522-118">Prerequisites</span></span>  
  
-   <span data-ttu-id="7d522-119">Nel modello di recupero con registrazione completa o con registrazione minima delle operazioni bulk, prima di poter ripristinare un database, è necessario effettuare il backup del log delle transazioni attivo, noto come parte finale del log.</span><span class="sxs-lookup"><span data-stu-id="7d522-119">Under the full or bulk-logged recovery model, before you can restore a database, you must back up the active transaction log (known as the tail of the log).</span></span> <span data-ttu-id="7d522-120">Per altre informazioni, vedere [Backup di un log delle transazioni &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="7d522-120">For more information, see [Back Up a Transaction Log &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="7d522-121">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="7d522-121">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="7d522-122">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="7d522-122">Permissions</span></span>  
 <span data-ttu-id="7d522-123">Se il database da ripristinare non esiste, per eseguire un'operazione RESTORE l'utente deve disporre delle autorizzazioni CREATE DATABASE.</span><span class="sxs-lookup"><span data-stu-id="7d522-123">If the database being restored does not exist, the user must have CREATE DATABASE permissions to be able to execute RESTORE.</span></span> <span data-ttu-id="7d522-124">Se il database esiste, le autorizzazioni per l'istruzione RESTORE vengono assegnate per impostazione predefinita ai membri dei ruoli predefiniti del server **sysadmin** e **dbcreator** e al proprietario (**dbo**) del database. Per l'opzione FROM DATABASE_SNAPSHOT, il database esiste sempre.</span><span class="sxs-lookup"><span data-stu-id="7d522-124">If the database exists, RESTORE permissions default to members of the **sysadmin** and **dbcreator** fixed server roles and the owner (**dbo**) of the database (for the FROM DATABASE_SNAPSHOT option, the database always exists).</span></span>  
  
 <span data-ttu-id="7d522-125">Le autorizzazioni per l'istruzione RESTORE vengono assegnate ai ruoli in cui le informazioni sull'appartenenza sono sempre disponibili per il server.</span><span class="sxs-lookup"><span data-stu-id="7d522-125">RESTORE permissions are given to roles in which membership information is always readily available to the server.</span></span> <span data-ttu-id="7d522-126">Poiché è possibile controllare l'appartenenza ai ruoli predefiniti del database solo quando il database è accessibile e non è danneggiato, condizioni che non risultano sempre vere quando si esegue un'operazione RESTORE, i membri del ruolo predefinito del database **db_owner** non dispongono delle autorizzazioni per l'istruzione RESTORE.</span><span class="sxs-lookup"><span data-stu-id="7d522-126">Because fixed database role membership can be checked only when the database is accessible and undamaged, which is not always the case when RESTORE is executed, members of the **db_owner** fixed database role do not have RESTORE permissions.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="7d522-127">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7d522-127">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-restore-a-differential-database-backup"></a><span data-ttu-id="7d522-128">Per ripristinare un backup differenziale del database</span><span class="sxs-lookup"><span data-stu-id="7d522-128">To restore a differential database backup</span></span>  
  
1.  <span data-ttu-id="7d522-129">Dopo aver stabilito la connessione all'istanza appropriata di [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Esplora oggetti fare clic sul nome del server per espanderne l'albero.</span><span class="sxs-lookup"><span data-stu-id="7d522-129">After you connect to the appropriate instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="7d522-130">Espandere **Database**.</span><span class="sxs-lookup"><span data-stu-id="7d522-130">Expand **Databases**.</span></span> <span data-ttu-id="7d522-131">A seconda del database, selezionare un database utente oppure espandere **Database di sistema**e selezionare un database di sistema.</span><span class="sxs-lookup"><span data-stu-id="7d522-131">Depending on the database, either select a user database or expand **System Databases**, and then select a system database.</span></span>  
  
3.  <span data-ttu-id="7d522-132">Fare clic con il pulsante destro del mouse sul database, scegliere **Attività**, selezionare **Ripristina**, quindi fare clic su **Database**.</span><span class="sxs-lookup"><span data-stu-id="7d522-132">Right-click the database, point to **Tasks**, point to **Restore**, and then click **Database**.</span></span>  
  
4.  <span data-ttu-id="7d522-133">Per specificare l'origine e il percorso dei set di backup da ripristinare, nella pagina **Generale** , utilizzare la sezione **Origine** .</span><span class="sxs-lookup"><span data-stu-id="7d522-133">On the **General** page, use the **Source** section to specify the source and location of the backup sets to restore.</span></span> <span data-ttu-id="7d522-134">Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7d522-134">Select one of the following options:</span></span>  
  
    -   <span data-ttu-id="7d522-135">**Database**</span><span class="sxs-lookup"><span data-stu-id="7d522-135">**Database**</span></span>  
  
         <span data-ttu-id="7d522-136">Selezionare il database da ripristinare dall'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="7d522-136">Select the database to restore from the drop-down list.</span></span> <span data-ttu-id="7d522-137">Nell'elenco sono inclusi solo i database di cui è stato eseguito il backup in base alla cronologia dei backup di **msdb** .</span><span class="sxs-lookup"><span data-stu-id="7d522-137">The list contains only databases that have been backed up according to the **msdb** backup history.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7d522-138">Se il backup viene eseguito da un server diverso, il server di destinazione non disporrà delle informazioni della cronologia di backup per il database specificato.</span><span class="sxs-lookup"><span data-stu-id="7d522-138">If the backup is taken from a different server, the destination server will not have the backup history information for the specified database.</span></span> <span data-ttu-id="7d522-139">In questo caso, selezionare **Dispositivo** per specificare manualmente il file o il dispositivo da ripristinare.</span><span class="sxs-lookup"><span data-stu-id="7d522-139">In this case, select **Device** to manually specify the file or device to restore.</span></span>  
  
    -   <span data-ttu-id="7d522-140">**Dispositivo**</span><span class="sxs-lookup"><span data-stu-id="7d522-140">**Device**</span></span>  
  
         <span data-ttu-id="7d522-141">Fare clic sul pulsante Sfoglia ( **...** ) per aprire la finestra di dialogo **Seleziona dispositivi di backup** .</span><span class="sxs-lookup"><span data-stu-id="7d522-141">Click the browse (**...**) button to open the **Select backup devices** dialog box.</span></span> <span data-ttu-id="7d522-142">Nella casella **Tipi di supporti di backup** selezionare uno dei tipi di dispositivi elencati.</span><span class="sxs-lookup"><span data-stu-id="7d522-142">In the **Backup media type** box, select one of the listed device types.</span></span> <span data-ttu-id="7d522-143">Per selezionare uno o più dispositivi per la casella **Supporti di backup** , fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="7d522-143">To select one or more devices for the **Backup media** box, click **Add**.</span></span>  
  
         <span data-ttu-id="7d522-144">Dopo avere aggiunto i dispositivi desiderati nella casella di riepilogo **Dispositivi di backup** , fare clic su **OK** per tornare alla pagina **Generale** .</span><span class="sxs-lookup"><span data-stu-id="7d522-144">After you add the devices you want to the **Backup media** list box, click **OK** to return to the **General** page.</span></span>  
  
         <span data-ttu-id="7d522-145">Nella casella di riepilogo **Origine: Dispositivo: Database** selezionare il nome del database da ripristinare.</span><span class="sxs-lookup"><span data-stu-id="7d522-145">In the **Source: Device: Database** list box, select the name of the database which should be restored.</span></span>  
  
         <span data-ttu-id="7d522-146">**Nota** Questo elenco è disponibile solo se si seleziona **Dispositivo** .</span><span class="sxs-lookup"><span data-stu-id="7d522-146">**Note** This list is only available when **Device** is selected.</span></span> <span data-ttu-id="7d522-147">Saranno disponibili solo i database che dispongono di backup sul dispositivo selezionato.</span><span class="sxs-lookup"><span data-stu-id="7d522-147">Only databases that have backups on the selected device will be available.</span></span>  
  
5.  <span data-ttu-id="7d522-148">Nella sezione **Destinazione** , la casella **Database** viene popolata automaticamente con il nome del database da ripristinare.</span><span class="sxs-lookup"><span data-stu-id="7d522-148">In the **Destination** section, the **Database** box is automatically populated with the name of the database to be restored.</span></span> <span data-ttu-id="7d522-149">Per modificare il nome del database, immettere il nome nuovo nella casella **Database** .</span><span class="sxs-lookup"><span data-stu-id="7d522-149">To change the name of the database, enter the new name in the **Database** box.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7d522-150">Per arrestare il ripristino in una data e un'ora diverse, fare clic su **Sequenza temporale** per accedere alla finestra di dialogo **Cronologia di backup** .</span><span class="sxs-lookup"><span data-stu-id="7d522-150">To stop the restore at a specific point in time, click **Timeline** to access the **Backup Timeline** dialog box.</span></span> <span data-ttu-id="7d522-151">Per informazioni sull'arresto del ripristino di un database in un momento specifico, vedere [Ripristino di un database di SQL Server fino a un punto specifico all'interno di un backup &#40;modello di recupero con registrazione completa&#41;](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md).</span><span class="sxs-lookup"><span data-stu-id="7d522-151">For help with stopping a database restore at a specific point in time, see [Restore a SQL Server Database to a Point in Time &#40;Full Recovery Model&#41;](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md).</span></span>  
  
6.  <span data-ttu-id="7d522-152">Nella griglia **Selezionare i set di backup da ripristinare** selezionare i backup che si desidera ripristinare dal backup differenziale.</span><span class="sxs-lookup"><span data-stu-id="7d522-152">In the **Backup sets to restore** grid, select the backups through the differential backup that you wish to restore.</span></span>  
  
     <span data-ttu-id="7d522-153">Per informazioni sulle colonne nella griglia **Selezionare i set di backup da ripristinare** , vedere [Ripristina database &#40;pagina Generale&#41;](../../integration-services/general-page-of-integration-services-designers-options.md).</span><span class="sxs-lookup"><span data-stu-id="7d522-153">For information about the columns in the **Backup sets to restore** grid, see [Restore Database &#40;General Page&#41;](../../integration-services/general-page-of-integration-services-designers-options.md).</span></span>  
  
7.  <span data-ttu-id="7d522-154">Nella pagina **Opzioni** del pannello **Opzioni di ripristino** è possibile selezionare una qualsiasi delle opzioni seguenti, in base alla situazione:</span><span class="sxs-lookup"><span data-stu-id="7d522-154">On the **Options** page, in the **Restore options** panel, you can select any of the following options, if appropriate for your situation:</span></span>  
  
    -   <span data-ttu-id="7d522-155">**Sovrascrivi il database esistente (WITH REPLACE)**</span><span class="sxs-lookup"><span data-stu-id="7d522-155">**Overwrite the existing database (WITH REPLACE)**</span></span>  
  
    -   <span data-ttu-id="7d522-156">**Mantieni le impostazioni di replica (WITH KEEP_REPLICATION)**</span><span class="sxs-lookup"><span data-stu-id="7d522-156">**Preserve the replication settings (WITH KEEP_REPLICATION)**</span></span>  
  
    -   <span data-ttu-id="7d522-157">**Chiedi conferma prima del ripristino di ogni backup**</span><span class="sxs-lookup"><span data-stu-id="7d522-157">**Prompt before restoring each backup**</span></span>  
  
    -   <span data-ttu-id="7d522-158">**Limita accesso al database ripristinato (WITH RESTRICTED_USER)**</span><span class="sxs-lookup"><span data-stu-id="7d522-158">**Restrict access to the restored database (WITH RESTRICTED_USER)**</span></span>  
  
     <span data-ttu-id="7d522-159">Per altre informazioni su queste opzioni, vedere [Ripristina database &#40;(pagina Opzioni)&#41;](restore-database-options-page.md).</span><span class="sxs-lookup"><span data-stu-id="7d522-159">For more information about these options, see [Restore Database &#40;Options Page&#41;](restore-database-options-page.md).</span></span>  
  
8.  <span data-ttu-id="7d522-160">Selezionare un'opzione per la casella **Stato di recupero** .</span><span class="sxs-lookup"><span data-stu-id="7d522-160">Select an option for the **Recovery state** box.</span></span> <span data-ttu-id="7d522-161">Questa casella determina lo stato del database al termine dell'operazione di ripristino.</span><span class="sxs-lookup"><span data-stu-id="7d522-161">This box determines the state of the database after the restore operation.</span></span>  
  
    -   <span data-ttu-id="7d522-162">**RESTORE WITH RECOVERY** è il comportamento predefinito che lascia il database pronto per l'utilizzo mediante il rollback delle transazioni di cui non è stato eseguito il commit.</span><span class="sxs-lookup"><span data-stu-id="7d522-162">**RESTORE WITH RECOVERY** is the default behavior which leaves the database ready for use by rolling back the uncommitted transactions.</span></span> <span data-ttu-id="7d522-163">I log delle transazioni aggiuntivi non possono essere ripristinati.</span><span class="sxs-lookup"><span data-stu-id="7d522-163">Additional transaction logs cannot be restored.</span></span> <span data-ttu-id="7d522-164">Selezionare questa opzione se si desidera ripristinare subito tutti i backup necessari.</span><span class="sxs-lookup"><span data-stu-id="7d522-164">Select this option if you are restoring all of the necessary backups now.</span></span>  
  
    -   <span data-ttu-id="7d522-165">**RESTORE WITH NORECOVERY** lascia il database non operativo e non esegue il rollback delle transazioni di cui non è stato eseguito il commit.</span><span class="sxs-lookup"><span data-stu-id="7d522-165">**RESTORE WITH NORECOVERY** which leaves the database non-operational, and does not roll back the uncommitted transactions.</span></span> <span data-ttu-id="7d522-166">I log delle transazioni aggiuntivi possono essere ripristinati.</span><span class="sxs-lookup"><span data-stu-id="7d522-166">Additional transaction logs can be restored.</span></span> <span data-ttu-id="7d522-167">Non è possibile utilizzare il database fino al completamento del recupero.</span><span class="sxs-lookup"><span data-stu-id="7d522-167">The database cannot be used until it is recovered.</span></span>  
  
    -   <span data-ttu-id="7d522-168">**RESTORE WITH STANDBY** lascia il database in modalità di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="7d522-168">**RESTORE WITH STANDBY** which leaves the database in read-only mode.</span></span> <span data-ttu-id="7d522-169">Annulla le transazioni di cui non è stato eseguito il commit, ma salva le azioni di rollback in un file standby in modo che gli effetti del recupero possano essere annullati.</span><span class="sxs-lookup"><span data-stu-id="7d522-169">It undoes uncommitted transactions, but saves the undo actions in a standby file so that recovery effects can be reverted.</span></span>  
  
     <span data-ttu-id="7d522-170">Per una descrizione delle opzioni, vedere [Ripristina database &#40;pagina Opzioni&#41;](restore-database-options-page.md).</span><span class="sxs-lookup"><span data-stu-id="7d522-170">For descriptions of the options, see [Restore Database &#40;Options Page&#41;](restore-database-options-page.md).</span></span>  
  
9. <span data-ttu-id="7d522-171">Le operazioni di ripristino non riescono in presenza di connessioni attive al database.</span><span class="sxs-lookup"><span data-stu-id="7d522-171">Restore operations will fail if there are active connections to the database.</span></span> <span data-ttu-id="7d522-172">Selezionare l'opzione **Chiudi connessioni esistenti** per garantire che tutte le connessioni attive tra [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] e il database vengano chiuse.</span><span class="sxs-lookup"><span data-stu-id="7d522-172">Check the **Close existing connections option** to ensure that all active connections between [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] and the database are closed.</span></span>  
  
10. <span data-ttu-id="7d522-173">Selezionare **Chiedi conferma prima del ripristino di ogni backup** se si desidera ricevere una richiesta di conferma prima di ciascuna operazione di ripristino.</span><span class="sxs-lookup"><span data-stu-id="7d522-173">Select **Prompt before restoring each backup** if you wish to be prompted between each restore operation.</span></span> <span data-ttu-id="7d522-174">L'operazione non è normalmente necessaria, a meno che le dimensioni del database siano elevate e si desideri monitorare lo stato dell'operazione di ripristino.</span><span class="sxs-lookup"><span data-stu-id="7d522-174">This is not usually necessary unless the database is large and you wish to monitor the status of the restore operation.</span></span>  
  
11. <span data-ttu-id="7d522-175">Facoltativamente, utilizzare la pagina **File** per ripristinare il database in un nuovo percorso.</span><span class="sxs-lookup"><span data-stu-id="7d522-175">Optionally, use the **Files** page to restore the database to a new location.</span></span> <span data-ttu-id="7d522-176">Per informazioni su come spostare un database, vedere [Ripristino di un database in una nuova posizione &#40;SQL Server&#41;](restore-a-database-to-a-new-location-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="7d522-176">For help with moving a database, see [Restore a Database to a New Location &#40;SQL Server&#41;](restore-a-database-to-a-new-location-sql-server.md).</span></span>  
  
12. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="7d522-177">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7d522-177">Using Transact-SQL</span></span>  
  
#### <a name="to-restore-a-differential-database-backup"></a><span data-ttu-id="7d522-178">Per ripristinare un backup differenziale del database</span><span class="sxs-lookup"><span data-stu-id="7d522-178">To restore a differential database backup</span></span>  
  
1.  <span data-ttu-id="7d522-179">Eseguire l'istruzione RESTORE DATABASE, specificando la clausola NORECOVERY, per ripristinare il backup completo del database precedente al backup differenziale del database.</span><span class="sxs-lookup"><span data-stu-id="7d522-179">Execute the RESTORE DATABASE statement, specifying the NORECOVERY clause, to restore the full database backup that comes before the differential database backup.</span></span> <span data-ttu-id="7d522-180">Per altre informazioni, vedere [Procedura: Ripristinare un backup completo](restore-a-database-backup-under-the-simple-recovery-model-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="7d522-180">For more information, see [How to: Restore a Full Backup](restore-a-database-backup-under-the-simple-recovery-model-transact-sql.md).</span></span>  
  
2.  <span data-ttu-id="7d522-181">Eseguire l'istruzione RESTORE DATABASE per ripristinare il backup differenziale del database, specificando:</span><span class="sxs-lookup"><span data-stu-id="7d522-181">Execute the RESTORE DATABASE statement to restore the differential database backup, specifying:</span></span>  
  
    -   <span data-ttu-id="7d522-182">Il nome del database a cui si riferisce il backup differenziale del database.</span><span class="sxs-lookup"><span data-stu-id="7d522-182">The name of the database to which the differential database backup is applied.</span></span>  
  
    -   <span data-ttu-id="7d522-183">Il dispositivo di backup da cui viene ripristinato il backup differenziale del database.</span><span class="sxs-lookup"><span data-stu-id="7d522-183">The backup device where the differential database backup is restored from.</span></span>  
  
    -   <span data-ttu-id="7d522-184">La clausola NORECOVERY, se sono presenti backup del log delle transazioni da applicare dopo il ripristino del backup differenziale del database.</span><span class="sxs-lookup"><span data-stu-id="7d522-184">The NORECOVERY clause if you have transaction log backups to apply after the differential database backup is restored.</span></span> <span data-ttu-id="7d522-185">In caso contrario, specificare la clausola RECOVERY.</span><span class="sxs-lookup"><span data-stu-id="7d522-185">Otherwise, specify the RECOVERY clause.</span></span>  
  
3.  <span data-ttu-id="7d522-186">Con il modello di recupero con registrazione completa o con registrazione minima delle operazioni bulk, tramite il ripristino di un backup differenziale del database viene ripristinato il database fino al punto in cui è stato completato il backup differenziale del database.</span><span class="sxs-lookup"><span data-stu-id="7d522-186">With the full or bulk-logged recovery model, restoring a differential database backup restores the database to the point at which the differential database backup was completed.</span></span> <span data-ttu-id="7d522-187">Per eseguire il recupero fino al momento dell'errore, applicare tutti i backup del log delle transazioni creati dopo la creazione dell'ultimo backup differenziale del database.</span><span class="sxs-lookup"><span data-stu-id="7d522-187">To recover to the point of failure, you must apply all transaction log backups created after the last differential database backup was created.</span></span> <span data-ttu-id="7d522-188">Per altre informazioni, vedere [Applicazione dei backup di log delle transazioni &#40;SQL Server&#41;](transaction-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="7d522-188">For more information, see [Apply Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md).</span></span>  
  
###  <a name="examples-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="7d522-189">Esempi (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="7d522-189">Examples (Transact-SQL)</span></span>  
  
#### <a name="a-restoring-a-differential-database-backup"></a><span data-ttu-id="7d522-190">R.</span><span class="sxs-lookup"><span data-stu-id="7d522-190">A.</span></span> <span data-ttu-id="7d522-191">Ripristino di un backup differenziale del database</span><span class="sxs-lookup"><span data-stu-id="7d522-191">Restoring a differential database backup</span></span>  
 <span data-ttu-id="7d522-192">Nell'esempio seguente vengono ripristinati un backup del database e un backup differenziale del database `MyAdvWorks` .</span><span class="sxs-lookup"><span data-stu-id="7d522-192">This example restores a database and differential database backup of the `MyAdvWorks` database.</span></span>  
  
```sql  
-- Assume the database is lost, and restore full database,   
-- specifying the original full database backup and NORECOVERY,   
-- which allows subsequent restore operations to proceed.  
RESTORE DATABASE MyAdvWorks  
   FROM MyAdvWorks_1  
   WITH NORECOVERY;  
GO  
-- Now restore the differential database backup, the second backup on   
-- the MyAdvWorks_1 backup device.  
RESTORE DATABASE MyAdvWorks  
   FROM MyAdvWorks_1  
   WITH FILE = 2,  
   RECOVERY;  
GO  
```  
  
#### <a name="b-restoring-a-database-differential-database-and-transaction-log-backup"></a><span data-ttu-id="7d522-193">B.</span><span class="sxs-lookup"><span data-stu-id="7d522-193">B.</span></span> <span data-ttu-id="7d522-194">Ripristino di un backup del database, di un backup differenziale del database e di un backup del log delle transazioni</span><span class="sxs-lookup"><span data-stu-id="7d522-194">Restoring a database, differential database, and transaction log backup</span></span>  
 <span data-ttu-id="7d522-195">In questo esempio vengono ripristinati un backup, un backup differenziale e un backup del log delle transazioni del database `MyAdvWorks` .</span><span class="sxs-lookup"><span data-stu-id="7d522-195">This example restores a database, differential database, and transaction log backup of the `MyAdvWorks` database.</span></span>  
  
```sql  
-- Assume the database is lost at this point. Now restore the full   
-- database. Specify the original full database backup and NORECOVERY.  
-- NORECOVERY allows subsequent restore operations to proceed.  
RESTORE DATABASE MyAdvWorks  
   FROM MyAdvWorks_1  
   WITH NORECOVERY;  
GO  
-- Now restore the differential database backup, the second backup on   
-- the MyAdvWorks_1 backup device.  
RESTORE DATABASE MyAdvWorks  
   FROM MyAdvWorks_1  
   WITH FILE = 2,  
   NORECOVERY;  
GO  
-- Now restore each transaction log backup created after  
-- the differential database backup.  
RESTORE LOG MyAdvWorks  
   FROM MyAdvWorks_log1  
   WITH NORECOVERY;  
GO  
RESTORE LOG MyAdvWorks  
   FROM MyAdvWorks_log2  
   WITH RECOVERY;  
GO  
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="7d522-196">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="7d522-196">Related Tasks</span></span>  
  
-   [<span data-ttu-id="7d522-197">Creare un backup differenziale del database &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="7d522-197">Create a Differential Database Backup &#40;SQL Server&#41;</span></span>](create-a-differential-database-backup-sql-server.md)  
  
-   [<span data-ttu-id="7d522-198">Ripristinare un backup del log delle transazioni &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="7d522-198">Restore a Transaction Log Backup &#40;SQL Server&#41;</span></span>](restore-a-transaction-log-backup-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="7d522-199">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7d522-199">See Also</span></span>  
 <span data-ttu-id="7d522-200">[Backup differenziali &#40;SQL Server&#41;](differential-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="7d522-200">[Differential Backups &#40;SQL Server&#41;](differential-backups-sql-server.md) </span></span>  
 [<span data-ttu-id="7d522-201">RESTORE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7d522-201">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  
  
