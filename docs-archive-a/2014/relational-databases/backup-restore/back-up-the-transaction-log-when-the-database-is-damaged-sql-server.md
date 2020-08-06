---
title: Eseguire il backup del log delle transazioni quando il database è danneggiato (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- databases [SQL Server], damaged
- backing up [SQL Server]. damaged database
- transaction log backups [SQL Server], damaged databases
ms.assetid: 9b8873cc-df54-4336-ab9b-8f525132c2b0
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ea712e6bc4e73119a4f07a7775f9f25e212f8534
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623358"
---
# <a name="back-up-the-transaction-log-when-the-database-is-damaged-sql-server"></a><span data-ttu-id="13233-102">Esecuzione del backup del log delle transazioni quando il database è danneggiato (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="13233-102">Back Up the Transaction Log When the Database Is Damaged (SQL Server)</span></span>
  <span data-ttu-id="13233-103">In questo argomento viene spiegato come eseguire il backup di un log delle transazioni quando il database è danneggiato in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="13233-103">This topic describes how to back up a transaction log when the database is damaged in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="13233-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="13233-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="13233-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="13233-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="13233-106">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="13233-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="13233-107">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="13233-107">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="13233-108">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="13233-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="13233-109">**Per eseguire il backup del log delle transazioni quando il database è danneggiato utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="13233-109">**To back up the transaction log when the database is damaged, using:**</span></span>  
  
     [<span data-ttu-id="13233-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="13233-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="13233-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="13233-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="13233-112">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="13233-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="13233-113">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="13233-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="13233-114">Non è possibile utilizzare l'istruzione BACKUP in una transazione esplicita o implicita.</span><span class="sxs-lookup"><span data-stu-id="13233-114">The BACKUP statement is not allowed in an explicit or implicit transaction.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="13233-115">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="13233-115">Recommendations</span></span>  
  
-   <span data-ttu-id="13233-116">Per un database che utilizza il modello di recupero con registrazione completa o il modello di recupero con registrazione minima delle operazioni bulk, è in genere necessario eseguire il backup della parte finale del log prima di avviare il ripristino del database.</span><span class="sxs-lookup"><span data-stu-id="13233-116">For a database that uses either the full or bulk-logged recovery model, you generally need to back up the tail of the log before beginning to restore the database.</span></span> <span data-ttu-id="13233-117">È inoltre consigliabile eseguire il backup della parte finale del log del database primario prima del failover di una configurazione di log shipping.</span><span class="sxs-lookup"><span data-stu-id="13233-117">You also should back up the tail of the log of the primary database before failing over a log shipping configuration.</span></span> <span data-ttu-id="13233-118">Il ripristino del backup della parte finale del log come backup del log finale prima del recupero del database consente di evitare la perdita di dati in seguito a un errore.</span><span class="sxs-lookup"><span data-stu-id="13233-118">Restoring the tail-log backup as the final log backup before recovering the database avoids work loss after a failure.</span></span> <span data-ttu-id="13233-119">Per altre informazioni sui backup della parte finale del log, vedere [Backup della parte finale del log &#40;SQL Server&#41;](tail-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="13233-119">For more information about tail-log backups, see [Tail-Log Backups &#40;SQL Server&#41;](tail-log-backups-sql-server.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="13233-120">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="13233-120">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="13233-121">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="13233-121">Permissions</span></span>  
 <span data-ttu-id="13233-122">Le autorizzazioni BACKUP DATABASE e BACKUP LOG vengono assegnate per impostazione predefinita ai membri del ruolo predefinito del server **sysadmin** e dei ruoli predefiniti del database **db_owner** e **db_backupoperator** .</span><span class="sxs-lookup"><span data-stu-id="13233-122">BACKUP DATABASE and BACKUP LOG permissions default to members of the **sysadmin** fixed server role and the **db_owner** and **db_backupoperator** fixed database roles.</span></span>  
  
 <span data-ttu-id="13233-123">Eventuali problemi correlati alla proprietà e alle autorizzazioni sul file fisico del dispositivo di backup possono interferire con l'operazione di backup.</span><span class="sxs-lookup"><span data-stu-id="13233-123">Ownership and permission problems on the backup device's physical file can interfere with a backup operation.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="13233-124">sia possibile leggere e scrivere sul dispositivo e che l'account utilizzato per eseguire il servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] disponga delle autorizzazioni di scrittura.</span><span class="sxs-lookup"><span data-stu-id="13233-124">must be able to read and write to the device; the account under which the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service runs must have write permissions.</span></span> <span data-ttu-id="13233-125">Le autorizzazioni di accesso ai file, tuttavia, non vengono controllate dalla stored procedure [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql)che aggiunge una voce per un dispositivo di backup nelle tabelle di sistema.</span><span class="sxs-lookup"><span data-stu-id="13233-125">However, [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql), which adds an entry for a backup device in the system tables, does not check file access permissions.</span></span> <span data-ttu-id="13233-126">Di conseguenza, i problemi relativi all'accesso e alla proprietà del file fisico del dispositivo di backup potrebbero emergere solo in fase di accesso alla risorsa fisica durante un tentativo di backup o ripristino.</span><span class="sxs-lookup"><span data-stu-id="13233-126">Such problems on the backup device's physical file may not appear until the physical resource is accessed when the backup or restore is attempted.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="13233-127">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="13233-127">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-back-up-the-tail-of-the-transaction-log"></a><span data-ttu-id="13233-128">Per eseguire il backup della parte finale del log delle transazioni</span><span class="sxs-lookup"><span data-stu-id="13233-128">To back up the tail of the transaction log</span></span>  
  
1.  <span data-ttu-id="13233-129">Dopo aver stabilito la connessione all'istanza appropriata del [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Esplora oggetti fare clic sul nome del server per espanderne l'albero.</span><span class="sxs-lookup"><span data-stu-id="13233-129">After connecting to the appropriate instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="13233-130">Espandere **Database**e, a seconda del database, selezionare un database utente o espandere **Database di sistema** e selezionare un database di sistema.</span><span class="sxs-lookup"><span data-stu-id="13233-130">Expand **Databases**, and, depending on the database, either select a user database or expand **System Databases** and select a system database.</span></span>  
  
3.  <span data-ttu-id="13233-131">Fare clic con il pulsante destro del mouse sul database, scegliere **Attività**e quindi fare clic su **Backup**.</span><span class="sxs-lookup"><span data-stu-id="13233-131">Right-click the database, point to **Tasks**, and then click **Back Up**.</span></span> <span data-ttu-id="13233-132">Verrà visualizzata la finestra di dialogo **Backup database** .</span><span class="sxs-lookup"><span data-stu-id="13233-132">The **Back Up Database** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="13233-133">Verificare il nome del database nella casella di riepilogo **Database** .</span><span class="sxs-lookup"><span data-stu-id="13233-133">In the **Database** list box, verify the database name.</span></span> <span data-ttu-id="13233-134">È possibile selezionare facoltativamente un database diverso nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="13233-134">You can optionally select a different database from the list.</span></span>  
  
5.  <span data-ttu-id="13233-135">Verificare che il modello di recupero sia impostato su **FULL** o **BULK_LOGGED**.</span><span class="sxs-lookup"><span data-stu-id="13233-135">Verify that the recovery model is either **FULL** or **BULK_LOGGED**.</span></span>  
  
6.  <span data-ttu-id="13233-136">Nella casella di riepilogo **Tipo backup** selezionare **Log delle transazioni**.</span><span class="sxs-lookup"><span data-stu-id="13233-136">In the **Backup type** list box, select **Transaction Log**.</span></span>  
  
7.  <span data-ttu-id="13233-137">Lasciare deselezionata l'opzione **Copia solo backup** .</span><span class="sxs-lookup"><span data-stu-id="13233-137">Leave **Copy Only Backup** deselected.</span></span>  
  
8.  <span data-ttu-id="13233-138">Nell'area **Set di backup** , accettare il nome predefinito del set di backup indicato nella casella di testo **Nome** oppure immettere un nome diverso per il set di backup.</span><span class="sxs-lookup"><span data-stu-id="13233-138">In the **Backup set** area, either accept the default backup set name suggested in the **Name** text box, or enter a different name for the backup set.</span></span>  
  
9. <span data-ttu-id="13233-139">Nella casella di testo **Descrizione** immettere una descrizione per il backup della parte finale del log.</span><span class="sxs-lookup"><span data-stu-id="13233-139">In the **Description** text box, enter a description for the tail-log backup.</span></span>  
  
10. <span data-ttu-id="13233-140">Specificare la scadenza del set di backup:</span><span class="sxs-lookup"><span data-stu-id="13233-140">Specify when the backup set will expire:</span></span>  
  
    -   <span data-ttu-id="13233-141">Per impostare la scadenza del set di backup dopo un numero di giorni specifico, fare clic su **Dopo** (opzione predefinita) e immettere il numero di giorni dopo la creazione del set trascorsi i quali il set scadrà.</span><span class="sxs-lookup"><span data-stu-id="13233-141">To have the backup set expire after a specific number of days, click **After** (the default option), and enter the number of days after set creation that the set will expire.</span></span> <span data-ttu-id="13233-142">È possibile impostare un valore compreso nell'intervallo da 0 a 99999 giorni. L'impostazione del valore 0 giorni indica che il set di backup non ha scadenza.</span><span class="sxs-lookup"><span data-stu-id="13233-142">This value can be from 0 to 99999 days; a value of 0 days means that the backup set will never expire.</span></span>  
  
         <span data-ttu-id="13233-143">Il valore predefinito viene impostato nell'opzione **Periodo di memorizzazione predefinito supporti di backup (giorni)** della finestra di dialogo **Proprietà server** (pagina**Impostazioni database** ).</span><span class="sxs-lookup"><span data-stu-id="13233-143">The default value is set in the **Default backup media retention (in days)** option of the **Server Properties** dialog box (**Database Settings** page).</span></span> <span data-ttu-id="13233-144">Per accedere a questa finestra di dialogo, fare clic con il pulsante destro del mouse sul nome del server in Esplora oggetti, scegliere Proprietà e quindi selezionare la pagina **Impostazioni database** .</span><span class="sxs-lookup"><span data-stu-id="13233-144">To access this dialog box, right-click the server name in Object Explorer and select properties; then select the **Database Settings** page.</span></span>  
  
    -   <span data-ttu-id="13233-145">Per impostare una data di scadenza specifica per il set di backup, fare clic su **Il**e immettere la data di scadenza del set.</span><span class="sxs-lookup"><span data-stu-id="13233-145">To have the backup set expire on a specific date, click **On**, and enter the date on which the set will expire.</span></span>  
  
11. <span data-ttu-id="13233-146">Fare clic su **Disco** o su **Nastro**per selezionare il tipo di destinazione del backup.</span><span class="sxs-lookup"><span data-stu-id="13233-146">Choose the type of backup destination by clicking **Disk** or **Tape**.</span></span> <span data-ttu-id="13233-147">Per selezionare i percorsi per un massimo di 64 unità disco o nastro contenenti un singolo set di supporti, fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="13233-147">To select the paths of up to 64 disk or tape drives containing a single media set, click **Add**.</span></span> <span data-ttu-id="13233-148">I percorsi selezionati vengono visualizzati nella casella di riepilogo **Backup su** .</span><span class="sxs-lookup"><span data-stu-id="13233-148">The selected paths are displayed in the **Backup to** list box.</span></span>  
  
     <span data-ttu-id="13233-149">Per rimuovere una destinazione di backup, selezionarla e fare clic su **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="13233-149">To remove a backup destination, select it and click **Remove**.</span></span> <span data-ttu-id="13233-150">Per visualizzare il contenuto di una destinazione di backup, selezionarla e fare clic su **Contenuto**.</span><span class="sxs-lookup"><span data-stu-id="13233-150">To view the contents of a backup destination, select it and click **Contents**.</span></span>  
  
12. <span data-ttu-id="13233-151">Nella pagina **Opzioni** , selezionare un'opzione **Sovrascrivi supporti** facendo clic su una delle impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="13233-151">On the **Options** page, select an **Overwrite Media** option, by clicking one of the following:</span></span>  
  
    -   <span data-ttu-id="13233-152">**Esegui backup nel set di supporti esistente**</span><span class="sxs-lookup"><span data-stu-id="13233-152">**Back up to the existing media set**</span></span>  
  
         <span data-ttu-id="13233-153">Per questa opzione, fare clic su **Accoda al set di backup esistente** o **Sovrascrivi tutti i set di backup esistenti**.</span><span class="sxs-lookup"><span data-stu-id="13233-153">For this option, click either **Append to the existing backup set** or **Overwrite all existing backup sets**.</span></span>  
  
         <span data-ttu-id="13233-154">Selezionare facoltativamente l'opzione **Controlla nome set di supporti e scadenza set di backup** per impostare la verifica della data e dell'ora di scadenza del set di supporti e del set di backup durante l'operazione di backup.</span><span class="sxs-lookup"><span data-stu-id="13233-154">Optionally, select **Check media set name and backup set expiration** to cause the backup operation to verify the date and time at which the media set and backup set expire.</span></span>  
  
         <span data-ttu-id="13233-155">Immettere facoltativamente un nome nella casella di testo **Nome set di supporti** .</span><span class="sxs-lookup"><span data-stu-id="13233-155">Optionally, enter a name in the **Media set name** text box.</span></span> <span data-ttu-id="13233-156">Se non si specifica un nome, verrà creato un set di supporti con nome vuoto.</span><span class="sxs-lookup"><span data-stu-id="13233-156">If no name is specified, a media set with a blank name is created.</span></span> <span data-ttu-id="13233-157">Se si specifica un nome per il set di supporti, il supporto (nastro o disco) verrà controllato per verificare che il nome effettivo corrisponda al nome specificato.</span><span class="sxs-lookup"><span data-stu-id="13233-157">If you specify a media set name, the media (tape or disk) is checked to see whether the actual name matches the name you enter here.</span></span>  
  
         <span data-ttu-id="13233-158">Se non si specifica il nome del set di supporti e si seleziona la casella di controllo per il controllo del nome, in caso di esito positivo anche il nome dei supporti nei supporti risulterà vuoto.</span><span class="sxs-lookup"><span data-stu-id="13233-158">If you leave the media name blank and check the box to check it against the media, success will equal the media name on the media also being blank.</span></span>  
  
    -   <span data-ttu-id="13233-159">**Esegui backup in un nuovo set di supporti e cancella tutti i set di backup esistenti**</span><span class="sxs-lookup"><span data-stu-id="13233-159">**Back up to a new media set, and erase all existing backup sets**</span></span>  
  
         <span data-ttu-id="13233-160">Per questa opzione, immettere un nome nella casella di testo **Nome nuovo set di supporti** e, facoltativamente, aggiungere una descrizione per il set di supporti nella casella di testo **Descrizione nuovo set di supporti** .</span><span class="sxs-lookup"><span data-stu-id="13233-160">For this option, enter a name in the **New media set name** text box, and, optionally, describe the media set in the **New media set description** text box.</span></span>  
  
     <span data-ttu-id="13233-161">Per altre informazioni sulle opzioni dei set di supporti, vedere [Set di supporti, gruppi di supporti e set di backup &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="13233-161">For more information about media set options, see [Media Sets, Media Families, and Backup Sets &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md).</span></span>  
  
13. <span data-ttu-id="13233-162">Nella sezione **Affidabilità** selezionare facoltativamente una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="13233-162">In the **Reliability** section, optionally, check:</span></span>  
  
    -   <span data-ttu-id="13233-163">**Verifica backup al termine**.</span><span class="sxs-lookup"><span data-stu-id="13233-163">**Verify backup when finished**.</span></span>  
  
    -   <span data-ttu-id="13233-164">**Esegui checksum prima della scrittura nei supporti**.</span><span class="sxs-lookup"><span data-stu-id="13233-164">**Perform checksum before writing to media**.</span></span>  
  
    -   <span data-ttu-id="13233-165">**Continuare su errore di checksum**</span><span class="sxs-lookup"><span data-stu-id="13233-165">**Continue on checksum error**</span></span>  
  
     <span data-ttu-id="13233-166">Per informazioni sui checksum, vedere [Possibili errori relativi ai supporti durante il backup e il ripristino &#40;SQL Server&#41;](possible-media-errors-during-backup-and-restore-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="13233-166">For information on checksums, see [Possible Media Errors During Backup and Restore &#40;SQL Server&#41;](possible-media-errors-during-backup-and-restore-sql-server.md).</span></span>  
  
14. <span data-ttu-id="13233-167">Nella sezione **Log delle transazioni** selezionare **Esegui backup della parte finale del log e lascia il database in stato di ripristino**.</span><span class="sxs-lookup"><span data-stu-id="13233-167">In the **Transaction log** section, check **Back up the tail of the log, and leave database in the restoring state**.</span></span>  
  
     <span data-ttu-id="13233-168">Questa opzione equivale a specificare l'istruzione [BACKUP](/sql/t-sql/statements/backup-transact-sql) seguente:</span><span class="sxs-lookup"><span data-stu-id="13233-168">This is equivalent to specifying the following [BACKUP](/sql/t-sql/statements/backup-transact-sql) statement:</span></span>  
  
     `BACKUP LOG <database_name> TO <backup_device> WITH NORECOVERY`  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="13233-169">In fase di ripristino nella finestra di dialogo Ripristina database il tipo di backup della parte finale del log verrà visualizzato come **Log delle transazioni (solo copia)** .</span><span class="sxs-lookup"><span data-stu-id="13233-169">At restore time, the Restore Database dialog box displays the type of a tail-log backup as **Transaction Log (Copy Only)**.</span></span>  
  
15. <span data-ttu-id="13233-170">Se si esegue il backup su un'unità nastro, come specificato nella sezione **Destinazione** della pagina **Generale** , l'opzione **Scarica nastro al termine del backup** sarà attiva.</span><span class="sxs-lookup"><span data-stu-id="13233-170">If you are backing up to a tape drive (as specified in the **Destination** section of the **General** page), the **Unload the tape after backup** option is active.</span></span> <span data-ttu-id="13233-171">Se si seleziona questa opzione, verrà inoltre attivata l'opzione **Riavvolgi il nastro prima di scaricarlo** .</span><span class="sxs-lookup"><span data-stu-id="13233-171">Clicking this option activates the **Rewind the tape before unloading** option.</span></span>  
  
16. [!INCLUDE[ssEnterpriseEd10](../../includes/ssenterpriseed10-md.md)] <span data-ttu-id="13233-172">e versioni successive supporta la [compressione dei backup](backup-compression-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="13233-172">and later supports [backup compression](backup-compression-sql-server.md).</span></span> <span data-ttu-id="13233-173">Per impostazione predefinita, la compressione di un backup dipende dal valore dell'opzione di configurazione del server **Valore predefinito di compressione backup**.</span><span class="sxs-lookup"><span data-stu-id="13233-173">By default, whether a backup is compressed depends on the value of the **backup-compression default** server configuration option.</span></span> <span data-ttu-id="13233-174">Tuttavia, indipendentemente dall'impostazione predefinita a livello di server corrente, è possibile comprimere un backup selezionando **Comprimi backup**ed è possibile impedire la compressione selezionando **Non comprimere il backup**.</span><span class="sxs-lookup"><span data-stu-id="13233-174">However, regardless of the current server-level default, you can compress a backup by checking **Compress backup**, and you can prevent compression by checking **Do not compress backup**.</span></span>  
  
     <span data-ttu-id="13233-175">**Per visualizzare l'impostazione predefinita corrente della compressione dei backup**</span><span class="sxs-lookup"><span data-stu-id="13233-175">**To view the current backup compression default**</span></span>  
  
    -   [<span data-ttu-id="13233-176">Visualizzare o configurare l'opzione di configurazione del server backup compression default</span><span class="sxs-lookup"><span data-stu-id="13233-176">View or Configure the backup compression default Server Configuration Option</span></span>](../../database-engine/configure-windows/view-or-configure-the-backup-compression-default-server-configuration-option.md)  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="13233-177">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="13233-177">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-backup-of-the-currently-active-transaction-log"></a><span data-ttu-id="13233-178">Per creare una copia di backup del log delle transazioni attivo</span><span class="sxs-lookup"><span data-stu-id="13233-178">To create a backup of the currently active transaction log</span></span>  
  
1.  <span data-ttu-id="13233-179">Eseguire l'istruzione BACKUP LOG per eseguire il backup del log delle transazioni attivo, specificando:</span><span class="sxs-lookup"><span data-stu-id="13233-179">Execute the BACKUP LOG statement to back up the currently active transaction log, specifying:</span></span>  
  
    -   <span data-ttu-id="13233-180">Il nome del database a cui appartiene il log delle transazioni di cui si desidera eseguire il backup.</span><span class="sxs-lookup"><span data-stu-id="13233-180">The name of the database to which the transaction log to back up belongs.</span></span>  
  
    -   <span data-ttu-id="13233-181">Il dispositivo di backup in cui verrà memorizzato il backup del log delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="13233-181">The backup device where the transaction log backup will be written.</span></span>  
  
    -   <span data-ttu-id="13233-182">Clausola NO_TRUNCATE.</span><span class="sxs-lookup"><span data-stu-id="13233-182">The NO_TRUNCATE clause.</span></span>  
  
         <span data-ttu-id="13233-183">Questa clausola consente di eseguire il backup della parte attiva del log delle transazioni anche se non è possibile accedere al database, purché il file del log delle transazioni sia accessibile e non danneggiato.</span><span class="sxs-lookup"><span data-stu-id="13233-183">This clause allows the active part of the transaction log to be backed up even if the database is inaccessible, provided that the transaction log file is accessible and undamaged.</span></span>  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="13233-184">Esempio (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="13233-184">Example (Transact-SQL)</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="13233-185">In questo esempio viene utilizzato [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)]che utilizza il modello di recupero con registrazione minima.</span><span class="sxs-lookup"><span data-stu-id="13233-185">This example uses the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)], which uses the simple recovery model.</span></span> <span data-ttu-id="13233-186">Per consentire i backup del log, prima di eseguire un backup completo del database, il database viene impostato in modo da utilizzare il modello di recupero con registrazione completa.</span><span class="sxs-lookup"><span data-stu-id="13233-186">To permit log backups, before taking a full database backup, the database was set to use the full recovery model.</span></span> <span data-ttu-id="13233-187">Per altre informazioni, vedere [Visualizzazione o modifica del modello di recupero di un database &#40;SQL Server&#41;](view-or-change-the-recovery-model-of-a-database-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="13233-187">For more information, see [View or Change the Recovery Model of a Database &#40;SQL Server&#41;](view-or-change-the-recovery-model-of-a-database-sql-server.md).</span></span>  
  
 <span data-ttu-id="13233-188">In questo esempio viene eseguito il backup del log della transazione attualmente attivo quando un database è danneggiato e inaccessibile, se il log delle transazioni non è danneggiato ed è accessibile.</span><span class="sxs-lookup"><span data-stu-id="13233-188">This example backs up the currently active transaction log when a database is damaged and inaccessible, if the transaction log is undamaged and accessible.</span></span>  
  
```scr  
BACKUP LOG AdventureWorks2012  
   TO MyAdvWorks_FullRM_log1  
   WITH NO_TRUNCATE;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="13233-189">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="13233-189">See Also</span></span>  
 <span data-ttu-id="13233-190">[Ripristinare un backup del log delle transazioni &#40;SQL Server&#41;](restore-a-transaction-log-backup-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="13233-190">[Restore a Transaction Log Backup &#40;SQL Server&#41;](restore-a-transaction-log-backup-sql-server.md) </span></span>  
 <span data-ttu-id="13233-191">[Ripristinare un database di SQL Server fino a un punto specifico &#40;Modello di recupero con registrazione completa&#41;](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="13233-191">[Restore a SQL Server Database to a Point in Time &#40;Full Recovery Model&#41;](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md) </span></span>  
 <span data-ttu-id="13233-192">[Eseguire il backup di database &#40;pagina Opzioni di backup&#41;](back-up-database-backup-options-page.md) </span><span class="sxs-lookup"><span data-stu-id="13233-192">[Back Up Database &#40;Backup Options Page&#41;](back-up-database-backup-options-page.md) </span></span>  
 <span data-ttu-id="13233-193">[Eseguire il backup di database &#40;pagina Generale&#41;](../../integration-services/general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="13233-193">[Back Up Database &#40;General Page&#41;](../../integration-services/general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="13233-194">[Applicare backup del log delle transazioni &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="13233-194">[Apply Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span></span>  
 <span data-ttu-id="13233-195">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="13233-195">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="13233-196">[Ripristini di file &#40;modello di recupero con registrazione minima&#41;](file-restores-simple-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="13233-196">[File Restores &#40;Simple Recovery Model&#41;](file-restores-simple-recovery-model.md) </span></span>  
 [<span data-ttu-id="13233-197">Ripristini di file &#40;modello di recupero con registrazione completa&#41;</span><span class="sxs-lookup"><span data-stu-id="13233-197">File Restores &#40;Full Recovery Model&#41;</span></span>](file-restores-full-recovery-model.md)  
  
  
