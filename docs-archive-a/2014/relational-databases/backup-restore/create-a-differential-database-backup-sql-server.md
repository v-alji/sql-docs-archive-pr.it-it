---
title: Creare un backup differenziale di database (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- full differential backups [SQL Server]
- database backups [SQL Server], full differential backups
- backing up databases [SQL Server], full differential backups
- backups [SQL Server], creating
ms.assetid: 70f49794-b217-4519-9f2a-76ed61fa9f99
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2c3fb53d90ce633498bc518282d1ff03ce0b926e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637921"
---
# <a name="create-a-differential-database-backup-sql-server"></a><span data-ttu-id="ee6ea-102">Creazione di un backup differenziale del database (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="ee6ea-102">Create a Differential Database Backup (SQL Server)</span></span>
  <span data-ttu-id="ee6ea-103">In questo argomento viene descritto come creare un backup differenziale del database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ee6ea-103">This topic describes how to create a differential database backup in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="ee6ea-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="ee6ea-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="ee6ea-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="ee6ea-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="ee6ea-106">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="ee6ea-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="ee6ea-107">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="ee6ea-107">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="ee6ea-108">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="ee6ea-108">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="ee6ea-109">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="ee6ea-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="ee6ea-110">**Per creare un backup differenziale del database utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="ee6ea-110">**To create a differential database backup, using:**</span></span>  
  
     [<span data-ttu-id="ee6ea-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ee6ea-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="ee6ea-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ee6ea-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="ee6ea-113">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="ee6ea-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="ee6ea-114">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="ee6ea-114">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="ee6ea-115">Non è possibile utilizzare l'istruzione BACKUP in una transazione esplicita o implicita.</span><span class="sxs-lookup"><span data-stu-id="ee6ea-115">The BACKUP statement is not allowed in an explicit or implicit transaction.</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="ee6ea-116">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="ee6ea-116">Prerequisites</span></span>  
  
-   <span data-ttu-id="ee6ea-117">Per creare un backup differenziale del database, è necessario che sia disponibile un backup completo precedente del database.</span><span class="sxs-lookup"><span data-stu-id="ee6ea-117">Creating a differential database backup requires that a previous full database backup exist.</span></span> <span data-ttu-id="ee6ea-118">Se non è mai stato creato un backup del database selezionato, eseguire un backup completo prima di creare backup differenziali.</span><span class="sxs-lookup"><span data-stu-id="ee6ea-118">If the selected database has never been backed up, run a full database backup before creating any differential backups.</span></span> <span data-ttu-id="ee6ea-119">Per altre informazioni, vedere [Creare un backup completo del database &#40;SQL Server&#41;](create-a-full-database-backup-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="ee6ea-119">For more information, see [Create a Full Database Backup &#40;SQL Server&#41;](create-a-full-database-backup-sql-server.md).</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="ee6ea-120">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="ee6ea-120">Recommendations</span></span>  
  
-   <span data-ttu-id="ee6ea-121">A causa dell'aumento delle dimensioni dei backup differenziali, il ripristino di un backup di questo tipo può comportare un notevole aumento del tempo necessario per il ripristino di un database.</span><span class="sxs-lookup"><span data-stu-id="ee6ea-121">As the differential backups increase in size, restoring a differential backup can significantly increase the time that is required to restore a database.</span></span> <span data-ttu-id="ee6ea-122">È consigliabile pertanto eseguire un nuovo backup completo a intervalli prestabiliti per creare una nuova base differenziale per i dati.</span><span class="sxs-lookup"><span data-stu-id="ee6ea-122">Therefore, we recommend that you take a new full backup at set intervals to establish a new differential base for the data.</span></span> <span data-ttu-id="ee6ea-123">È ad esempio possibile eseguire un backup completo settimanale dell'intero database, ovvero un backup completo del database, seguito da una serie regolare di backup differenziali del database nell'arco della settimana.</span><span class="sxs-lookup"><span data-stu-id="ee6ea-123">For example, you might take a weekly full backup of the whole database (that is, a full database backup) followed by a regular series of differential database backups during the week.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="ee6ea-124">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="ee6ea-124">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="ee6ea-125">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="ee6ea-125">Permissions</span></span>  
 <span data-ttu-id="ee6ea-126">Le autorizzazioni BACKUP DATABASE e BACKUP LOG vengono assegnate per impostazione predefinita ai membri del ruolo predefinito del server **sysadmin** e dei ruoli predefiniti del database **db_owner** e **db_backupoperator** .</span><span class="sxs-lookup"><span data-stu-id="ee6ea-126">BACKUP DATABASE and BACKUP LOG permissions default to members of the **sysadmin** fixed server role and the **db_owner** and **db_backupoperator** fixed database roles.</span></span>  
  
 <span data-ttu-id="ee6ea-127">Eventuali problemi correlati alla proprietà e alle autorizzazioni sul file fisico del dispositivo di backup possono interferire con l'operazione di backup.</span><span class="sxs-lookup"><span data-stu-id="ee6ea-127">Ownership and permission problems on the backup device's physical file can interfere with a backup operation.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="ee6ea-128">sia possibile leggere e scrivere sul dispositivo e che l'account utilizzato per eseguire il servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] disponga delle autorizzazioni di scrittura.</span><span class="sxs-lookup"><span data-stu-id="ee6ea-128">must be able to read and write to the device; the account under which the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service runs must have write permissions.</span></span> <span data-ttu-id="ee6ea-129">Le autorizzazioni di accesso ai file, tuttavia, non vengono controllate dalla stored procedure [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql)che aggiunge una voce per un dispositivo di backup nelle tabelle di sistema.</span><span class="sxs-lookup"><span data-stu-id="ee6ea-129">However, [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql), which adds an entry for a backup device in the system tables, does not check file access permissions.</span></span> <span data-ttu-id="ee6ea-130">Di conseguenza, i problemi relativi all'accesso e alla proprietà del file fisico del dispositivo di backup potrebbero emergere solo in fase di accesso alla risorsa fisica durante un tentativo di backup o ripristino.</span><span class="sxs-lookup"><span data-stu-id="ee6ea-130">Such problems on the backup device's physical file may not appear until the physical resource is accessed when the backup or restore is attempted.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="ee6ea-131">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ee6ea-131">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-differential-database-backup"></a><span data-ttu-id="ee6ea-132">Per creare un backup differenziale del database</span><span class="sxs-lookup"><span data-stu-id="ee6ea-132">To create a differential database backup</span></span>  
  
1.  <span data-ttu-id="ee6ea-133">Dopo aver stabilito la connessione all'istanza appropriata del [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Esplora oggetti fare clic sul nome del server per espanderne l'albero.</span><span class="sxs-lookup"><span data-stu-id="ee6ea-133">After connecting to the appropriate instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="ee6ea-134">Espandere **Database**e, a seconda del database, selezionare un database utente o espandere **Database di sistema** e selezionare un database di sistema.</span><span class="sxs-lookup"><span data-stu-id="ee6ea-134">Expand **Databases**, and depending on the database, either select a user database or expand **System Databases** and select a system database.</span></span>  
  
3.  <span data-ttu-id="ee6ea-135">Fare clic con il pulsante destro del mouse sul database, scegliere **Attività**e quindi fare clic su **Backup**.</span><span class="sxs-lookup"><span data-stu-id="ee6ea-135">Right-click the database, point to **Tasks**, and then click **Back Up**.</span></span> <span data-ttu-id="ee6ea-136">Verrà visualizzata la finestra di dialogo **Backup database** .</span><span class="sxs-lookup"><span data-stu-id="ee6ea-136">The **Back Up Database** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="ee6ea-137">Verificare il nome del database nella casella di riepilogo **Database** .</span><span class="sxs-lookup"><span data-stu-id="ee6ea-137">In the **Database** list box, verify the database name.</span></span> <span data-ttu-id="ee6ea-138">È possibile selezionare facoltativamente un database diverso nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="ee6ea-138">You can optionally select a different database from the list.</span></span>  
  
     <span data-ttu-id="ee6ea-139">È possibile eseguire un backup differenziale per qualsiasi modello di recupero (con registrazione completa, con registrazione minima delle operazioni bulk o con registrazione minima).</span><span class="sxs-lookup"><span data-stu-id="ee6ea-139">You can perform a differential backup for any recovery model (full, bulk-logged, or simple).</span></span>  
  
5.  <span data-ttu-id="ee6ea-140">Nella casella di riepilogo **Tipo di backup** selezionare **Differenziale**.</span><span class="sxs-lookup"><span data-stu-id="ee6ea-140">In the **Backup type** list box, select **Differential**.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="ee6ea-141"> Se l'opzione **Differenziale** è selezionata, verificare che la casella di controllo **Copia solo backup** sia deselezionata.</span><span class="sxs-lookup"><span data-stu-id="ee6ea-141">When **Differential** is selected, verify that the **Copy Only Backup** check box is cleared.</span></span>  
  
6.  <span data-ttu-id="ee6ea-142">In **Componente di cui eseguire il backup**fare clic su **Database**.</span><span class="sxs-lookup"><span data-stu-id="ee6ea-142">For **Backup component**, click **Database**.</span></span>  
  
7.  <span data-ttu-id="ee6ea-143">Accettare il nome predefinito del set di backup indicato nella casella di testo **Nome** oppure immettere un nome diverso per il set di backup.</span><span class="sxs-lookup"><span data-stu-id="ee6ea-143">Either accept the default backup set name suggested in the **Name** text box, or enter a different name for the backup set.</span></span>  
  
8.  <span data-ttu-id="ee6ea-144">Facoltativamente, immettere una descrizione del set di backup nella casella di testo **Descrizione** .</span><span class="sxs-lookup"><span data-stu-id="ee6ea-144">Optionally, in the **Description** text box, enter a description of the backup set.</span></span>  
  
9. <span data-ttu-id="ee6ea-145">Specificare la scadenza del set di backup:</span><span class="sxs-lookup"><span data-stu-id="ee6ea-145">Specify when the backup set will expire:</span></span>  
  
    -   <span data-ttu-id="ee6ea-146">Per impostare la scadenza del set di backup dopo un numero di giorni specifico, fare clic su **Dopo** (opzione predefinita) e immettere il numero di giorni dopo la creazione del set trascorsi i quali il set scadrà.</span><span class="sxs-lookup"><span data-stu-id="ee6ea-146">To have the backup set expire after a specific number of days, click **After** (the default option), and enter the number of days after set creation that the set will expire.</span></span> <span data-ttu-id="ee6ea-147">È possibile impostare un valore compreso nell'intervallo da 0 a 99999 giorni. L'impostazione del valore 0 giorni indica che il set di backup non ha scadenza.</span><span class="sxs-lookup"><span data-stu-id="ee6ea-147">This value can be from 0 to 99999 days; a value of 0 days means that the backup set will never expire.</span></span>  
  
         <span data-ttu-id="ee6ea-148">Il valore predefinito viene impostato nell'opzione **Periodo di memorizzazione predefinito supporti di backup (giorni)** della finestra di dialogo **Proprietà server** (pagina**Impostazioni database** ).</span><span class="sxs-lookup"><span data-stu-id="ee6ea-148">The default value is set in the **Default backup media retention (in days)** option of the **Server Properties** dialog box (**Database Settings** page).</span></span> <span data-ttu-id="ee6ea-149">Per accedere alla pagina, fare clic con il pulsante destro del mouse sul nome del server in Esplora oggetti e scegliere Proprietà, quindi selezionare la pagina **Impostazioni database** .</span><span class="sxs-lookup"><span data-stu-id="ee6ea-149">To access this, right-click the server name in Object Explorer and select properties; then select the **Database Settings** page.</span></span>  
  
    -   <span data-ttu-id="ee6ea-150">Per impostare una data di scadenza specifica per il set di backup, fare clic su **Il**e immettere la data di scadenza del set.</span><span class="sxs-lookup"><span data-stu-id="ee6ea-150">To have the backup set expire on a specific date, click **On**, and enter the date on which the set will expire.</span></span>  
  
10. <span data-ttu-id="ee6ea-151">Fare clic su **Disco** o su **Nastro**per selezionare il tipo di destinazione del backup.</span><span class="sxs-lookup"><span data-stu-id="ee6ea-151">Choose the type of backup destination by clicking **Disk** or **Tape**.</span></span> <span data-ttu-id="ee6ea-152">Per selezionare il percorso per un massimo di 64 unità disco o nastro contenenti un singolo set di supporti, fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="ee6ea-152">To select the path of up to 64 disk or tape drives containing a single media set, click **Add**.</span></span> <span data-ttu-id="ee6ea-153">I percorsi selezionati vengono visualizzati nella casella di riepilogo **Backup su** .</span><span class="sxs-lookup"><span data-stu-id="ee6ea-153">The selected paths are displayed in the **Backup to** list box.</span></span>  
  
     <span data-ttu-id="ee6ea-154">Per rimuovere una destinazione di backup, selezionarla e fare clic su **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="ee6ea-154">To remove a backup destination, select it and click **Remove**.</span></span> <span data-ttu-id="ee6ea-155">Per visualizzare il contenuto di una destinazione di backup, selezionarla e fare clic su **Contenuto**.</span><span class="sxs-lookup"><span data-stu-id="ee6ea-155">To view the contents of a backup destination, select it and click **Contents**.</span></span>  
  
11. <span data-ttu-id="ee6ea-156">Per visualizzare o selezionare le opzioni avanzate, fare clic su **Opzioni** nel riquadro **Selezione pagina** .</span><span class="sxs-lookup"><span data-stu-id="ee6ea-156">To view or select the advanced options, click **Options** in the **Select a page** pane.</span></span>  
  
12. <span data-ttu-id="ee6ea-157">Selezionare un'opzione **Sovrascrivi supporti** facendo clic su una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ee6ea-157">Select an **Overwrite Media** option, by clicking one of the following:</span></span>  
  
    -   <span data-ttu-id="ee6ea-158">**Esegui backup nel set di supporti esistente**</span><span class="sxs-lookup"><span data-stu-id="ee6ea-158">**Back up to the existing media set**</span></span>  
  
         <span data-ttu-id="ee6ea-159">Per questa opzione, fare clic su **Accoda al set di backup esistente** o **Sovrascrivi tutti i set di backup esistenti**.</span><span class="sxs-lookup"><span data-stu-id="ee6ea-159">For this option, click either **Append to the existing backup set** or **Overwrite all existing backup sets**.</span></span> <span data-ttu-id="ee6ea-160">Facoltativamente, selezionare la casella di controllo **Controlla nome set di supporti e scadenza set di backup** e, sempre facoltativamente, immettere un nome nella casella di testo **Nome set di supporti** .</span><span class="sxs-lookup"><span data-stu-id="ee6ea-160">Optionally, check the **Check media set name and backup set expiration** check box and, optionally, enter a name in the **Media set name** text box.</span></span> <span data-ttu-id="ee6ea-161">Se non si specifica un nome, verrà creato un set di supporti con nome vuoto.</span><span class="sxs-lookup"><span data-stu-id="ee6ea-161">If no name is specified, a media set with a blank name is created.</span></span> <span data-ttu-id="ee6ea-162">Se si specifica un nome, il supporto (nastro o disco) verrà controllato per verificare che il nome effettivo corrisponda al nome specificato.</span><span class="sxs-lookup"><span data-stu-id="ee6ea-162">If you specify a media set name, the media (tape or disk) is checked to see if the actual name matches the name you enter here.</span></span>  
  
         <span data-ttu-id="ee6ea-163">Se non si specifica il nome del set di supporti e si seleziona la casella di controllo per il controllo del nome, in caso di esito positivo anche il nome dei supporti nei supporti risulterà vuoto.</span><span class="sxs-lookup"><span data-stu-id="ee6ea-163">If you leave the media name blank and check the box to check it against the media, success will equal the media name on the media also being blank.</span></span>  
  
    -   <span data-ttu-id="ee6ea-164">**Esegui backup in un nuovo set di supporti e cancella tutti i set di backup esistenti**</span><span class="sxs-lookup"><span data-stu-id="ee6ea-164">**Back up to a new media set, and erase all existing backup sets**</span></span>  
  
         <span data-ttu-id="ee6ea-165">Per questa opzione, immettere un nome nella casella di testo **Nome nuovo set di supporti** e, facoltativamente, aggiungere una descrizione per il set di supporti nella casella di testo **Descrizione nuovo set di supporti** .</span><span class="sxs-lookup"><span data-stu-id="ee6ea-165">For this option, enter a name in the **New media set name** text box, and, optionally, describe the media set in the **New media set description** text box.</span></span>  
  
13. <span data-ttu-id="ee6ea-166">Nella sezione **Affidabilità** selezionare facoltativamente una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ee6ea-166">In the **Reliability** section, optionally, check:</span></span>  
  
    -   <span data-ttu-id="ee6ea-167">**Verifica backup al termine**.</span><span class="sxs-lookup"><span data-stu-id="ee6ea-167">**Verify backup when finished**.</span></span>  
  
    -   <span data-ttu-id="ee6ea-168">**Esegui checksum prima della scrittura nei supporti**e, facoltativamente, **Continua in caso di errori checksum**.</span><span class="sxs-lookup"><span data-stu-id="ee6ea-168">**Perform checksum before writing to media**, and, optionally, **Continue on checksum error**.</span></span> <span data-ttu-id="ee6ea-169">Per informazioni sui checksum, vedere [Possibili errori relativi ai supporti durante il backup e il ripristino &#40;SQL Server&#41;](possible-media-errors-during-backup-and-restore-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="ee6ea-169">For information about checksums, see [Possible Media Errors During Backup and Restore &#40;SQL Server&#41;](possible-media-errors-during-backup-and-restore-sql-server.md).</span></span>  
  
14. <span data-ttu-id="ee6ea-170">Se si esegue il backup su un'unità nastro, come specificato nella sezione **Destinazione** della pagina **Generale** , l'opzione **Scarica nastro al termine del backup** sarà attiva.</span><span class="sxs-lookup"><span data-stu-id="ee6ea-170">If you are backing up to a tape drive (as specified in the **Destination** section of the **General** page), the **Unload the tape after backup** option is active.</span></span> <span data-ttu-id="ee6ea-171">Se si seleziona questa opzione, verrà inoltre attivata l'opzione **Riavvolgi il nastro prima di scaricarlo** .</span><span class="sxs-lookup"><span data-stu-id="ee6ea-171">Clicking this option activates the **Rewind the tape before unloading** option.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ee6ea-172">Le opzioni presenti nella sezione **Log delle transazioni** sono attive solo in caso di backup di un log delle transazioni, come specificato nella sezione **Tipo backup** nella pagina **Generale** .</span><span class="sxs-lookup"><span data-stu-id="ee6ea-172">The options in the **Transaction log** section are inactive unless you are backing up a transaction log (as specified in the **Backup type** section of the **General** page).</span></span>  
  
15. [!INCLUDE[ssEnterpriseEd10](../../includes/ssenterpriseed10-md.md)] <span data-ttu-id="ee6ea-173">e versioni successive supporta la [compressione dei backup](backup-compression-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="ee6ea-173">and later supports [backup compression](backup-compression-sql-server.md).</span></span> <span data-ttu-id="ee6ea-174">Per impostazione predefinita, la compressione di un backup dipende dal valore dell'opzione di configurazione del server **Valore predefinito di compressione backup**.</span><span class="sxs-lookup"><span data-stu-id="ee6ea-174">By default, whether a backup is compressed depends on the value of the **backup-compression default** server configuration option.</span></span> <span data-ttu-id="ee6ea-175">Tuttavia, indipendentemente dall'impostazione predefinita a livello di server corrente, è possibile comprimere un backup selezionando **Comprimi backup**ed è possibile impedire la compressione selezionando **Non comprimere il backup**.</span><span class="sxs-lookup"><span data-stu-id="ee6ea-175">However, regardless of the current server-level default, you can compress a backup by checking **Compress backup**, and you can prevent compression by checking **Do not compress backup**.</span></span>  
  
     <span data-ttu-id="ee6ea-176">**Per visualizzare l'impostazione predefinita corrente della compressione dei backup**</span><span class="sxs-lookup"><span data-stu-id="ee6ea-176">**To view the current backup compression default**</span></span>  
  
    -   [<span data-ttu-id="ee6ea-177">Visualizzare o configurare l'opzione di configurazione del server backup compression default</span><span class="sxs-lookup"><span data-stu-id="ee6ea-177">View or Configure the backup compression default Server Configuration Option</span></span>](../../database-engine/configure-windows/view-or-configure-the-backup-compression-default-server-configuration-option.md)  
  
    > [!NOTE]  
    >  <span data-ttu-id="ee6ea-178">In alternativa, è possibile creare backup differenziali del database tramite Creazione guidata piano di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="ee6ea-178">Alternatively, you can use the Maintenance Plan Wizard to create differential database backups.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="ee6ea-179">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ee6ea-179">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-differential-database-backup"></a><span data-ttu-id="ee6ea-180">Per creare un backup differenziale del database</span><span class="sxs-lookup"><span data-stu-id="ee6ea-180">To create a differential database backup</span></span>  
  
1.  <span data-ttu-id="ee6ea-181">Per creare il backup differenziale del database, eseguire l'istruzione BACKUP DATABASE specificando:</span><span class="sxs-lookup"><span data-stu-id="ee6ea-181">Execute the BACKUP DATABASE statement to create the differential database backup, specifying:</span></span>  
  
    -   <span data-ttu-id="ee6ea-182">Il nome del database di cui eseguire il backup.</span><span class="sxs-lookup"><span data-stu-id="ee6ea-182">The name of the database to back up.</span></span>  
  
    -   <span data-ttu-id="ee6ea-183">Il dispositivo di backup in cui archiviare il backup completo del database.</span><span class="sxs-lookup"><span data-stu-id="ee6ea-183">The backup device where the full database backup is written.</span></span>  
  
    -   <span data-ttu-id="ee6ea-184">Clausola DIFFERENTIAL per specificare che viene effettuato il backup solo delle parti del database modificate dopo l'ultimo backup completo del database stesso.</span><span class="sxs-lookup"><span data-stu-id="ee6ea-184">The DIFFERENTIAL clause, to specify that only the parts of the database that have changed after the last full database backup was created are backed up.</span></span>  
  
     <span data-ttu-id="ee6ea-185">La sintassi richiesta è la seguente:</span><span class="sxs-lookup"><span data-stu-id="ee6ea-185">The required syntax is:</span></span>  
  
     <span data-ttu-id="ee6ea-186">BACKUP DATABASE *database_name* TO <backup_device> WITH DIFFERENTIAL</span><span class="sxs-lookup"><span data-stu-id="ee6ea-186">BACKUP DATABASE *database_name* TO <backup_device> WITH DIFFERENTIAL</span></span>  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="ee6ea-187">Esempio (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="ee6ea-187">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="ee6ea-188">In questo esempio vengono creati un backup completo e un backup differenziale del database `MyAdvWorks` .</span><span class="sxs-lookup"><span data-stu-id="ee6ea-188">This example creates a full and a differential database backup for the `MyAdvWorks` database.</span></span>  
  
```sql  
-- Create a full database backup first.  
BACKUP DATABASE MyAdvWorks   
   TO MyAdvWorks_1   
   WITH INIT;  
GO  
-- Time elapses.  
-- Create a differential database backup, appending the backup  
-- to the backup device containing the full database backup.  
BACKUP DATABASE MyAdvWorks  
   TO MyAdvWorks_1  
   WITH DIFFERENTIAL;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="ee6ea-189">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ee6ea-189">See Also</span></span>  
 <span data-ttu-id="ee6ea-190">[Backup differenziali &#40;SQL Server&#41;](differential-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="ee6ea-190">[Differential Backups &#40;SQL Server&#41;](differential-backups-sql-server.md) </span></span>  
 <span data-ttu-id="ee6ea-191">[Creare un backup completo del database &#40;SQL Server&#41;](create-a-full-database-backup-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="ee6ea-191">[Create a Full Database Backup &#40;SQL Server&#41;](create-a-full-database-backup-sql-server.md) </span></span>  
 <span data-ttu-id="ee6ea-192">[Backup di file e filegroup &#40;SQL Server&#41;](back-up-files-and-filegroups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="ee6ea-192">[Back Up Files and Filegroups &#40;SQL Server&#41;](back-up-files-and-filegroups-sql-server.md) </span></span>  
 <span data-ttu-id="ee6ea-193">[Ripristinare un backup differenziale del database &#40;SQL Server&#41;](restore-a-differential-database-backup-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="ee6ea-193">[Restore a Differential Database Backup &#40;SQL Server&#41;](restore-a-differential-database-backup-sql-server.md) </span></span>  
 <span data-ttu-id="ee6ea-194">[Ripristinare un backup del log delle transazioni &#40;SQL Server&#41;](restore-a-transaction-log-backup-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="ee6ea-194">[Restore a Transaction Log Backup &#40;SQL Server&#41;](restore-a-transaction-log-backup-sql-server.md) </span></span>  
 <span data-ttu-id="ee6ea-195">[Piani di manutenzione](../maintenance-plans/maintenance-plans.md) </span><span class="sxs-lookup"><span data-stu-id="ee6ea-195">[Maintenance Plans](../maintenance-plans/maintenance-plans.md) </span></span>  
 [<span data-ttu-id="ee6ea-196">Backup completi del file &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ee6ea-196">Full File Backups &#40;SQL Server&#41;</span></span>](full-file-backups-sql-server.md)  
  
  
