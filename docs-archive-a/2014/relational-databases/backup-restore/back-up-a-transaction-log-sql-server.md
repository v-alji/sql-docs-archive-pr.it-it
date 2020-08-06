---
title: Backup di un log delle transazioni (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- transaction log backups [SQL Server], SQL Server Management Studio
- backups [SQL Server], creating
- backing up transaction logs [SQL Server], SQL Server Management Studio
ms.assetid: 3426b5eb-6327-4c7f-88aa-37030be69fbf
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b57ca40b08718cda5095249991e0d424e6593a24
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627849"
---
# <a name="back-up-a-transaction-log-sql-server"></a><span data-ttu-id="454be-102">Backup di un log delle transazioni (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="454be-102">Back Up a Transaction Log (SQL Server)</span></span>
  <span data-ttu-id="454be-103">In questo argomento viene descritto come eseguire il backup di un log delle transazioni in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)]o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="454be-103">This topic describes how to back up a transaction log in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or PowerShell.</span></span>  
  
 <span data-ttu-id="454be-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="454be-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="454be-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="454be-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="454be-106">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="454be-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="454be-107">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="454be-107">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="454be-108">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="454be-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="454be-109">**Per eseguire il backup di un log delle transazioni utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="454be-109">**To back up a transaction log, using:**</span></span>  
  
     [<span data-ttu-id="454be-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="454be-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="454be-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="454be-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="454be-112">PowerShell</span><span class="sxs-lookup"><span data-stu-id="454be-112">PowerShell</span></span>](#PowerShellProcedure)  
  
    > [!NOTE]  
    >  <span data-ttu-id="454be-113"> In alternativa, è possibile creare i backup tramite la[Creazione guidata piano di manutenzione](../maintenance-plans/use-the-maintenance-plan-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="454be-113">Alternatively, you can use the[Maintenance Plan Wizard](../maintenance-plans/use-the-maintenance-plan-wizard.md)to create backups.</span></span>  
  
-   [<span data-ttu-id="454be-114">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="454be-114">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="454be-115">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="454be-115">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="454be-116">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="454be-116">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="454be-117">Non è possibile utilizzare l'istruzione BACKUP in una transazione esplicita o implicita.</span><span class="sxs-lookup"><span data-stu-id="454be-117">The BACKUP statement is not allowed in an explicit or implicit transaction.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="454be-118">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="454be-118">Recommendations</span></span>  
  
-   <span data-ttu-id="454be-119">Se un database utilizza il modello di recupero con registrazione completa o il modello di recupero con registrazione minima delle operazioni bulk, è necessario eseguire il backup del log delle transazioni con una frequenza sufficiente per garantire la protezione dei dati e per evitare il riempimento del log delle transazioni stesso.</span><span class="sxs-lookup"><span data-stu-id="454be-119">If a database uses either the full or bulk-logged recovery model, you must back up the transaction log regularly enough to protect your data and to keep the transaction log from filling.</span></span> <span data-ttu-id="454be-120">Tronca il log e supporta il ripristino del database in corrispondenza di uno specifico punto nel tempo.</span><span class="sxs-lookup"><span data-stu-id="454be-120">This truncates the log and supports restoring the database to a specific point in time.</span></span>  
  
-   <span data-ttu-id="454be-121">Per impostazione predefinita, per ogni operazione di backup eseguita in modo corretto viene aggiunta una voce al log degli errori di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e al registro eventi di sistema.</span><span class="sxs-lookup"><span data-stu-id="454be-121">By default, every successful backup operation adds an entry in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log and in the system event log.</span></span> <span data-ttu-id="454be-122">Se il backup del log viene eseguito di frequente, questi messaggi possono aumentare rapidamente, provocando la creazione di log degli errori di dimensioni elevate e rendendo difficile l'individuazione di altri messaggi.</span><span class="sxs-lookup"><span data-stu-id="454be-122">If back up the log very frequently, these success messages accumulate quickly, resulting in huge error logs that can make finding other messages difficult.</span></span> <span data-ttu-id="454be-123">In questi casi è possibile eliminare tali voci di log utilizzando il flag di traccia 3226 se nessuno degli script dipende da esse.</span><span class="sxs-lookup"><span data-stu-id="454be-123">In such cases you can suppress these log entries by using trace flag 3226 if none of your scripts depend on those entries.</span></span> <span data-ttu-id="454be-124">Per altre informazioni, vedere [Flag di traccia &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-traceon-trace-flags-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="454be-124">For more information, see [Trace Flags &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-traceon-trace-flags-transact-sql).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="454be-125">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="454be-125">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="454be-126">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="454be-126">Permissions</span></span>  
 <span data-ttu-id="454be-127">Le autorizzazioni BACKUP DATABASE e BACKUP LOG vengono assegnate per impostazione predefinita ai membri del ruolo predefinito del server **sysadmin** e dei ruoli predefiniti del database **db_owner** e **db_backupoperator** .</span><span class="sxs-lookup"><span data-stu-id="454be-127">BACKUP DATABASE and BACKUP LOG permissions default to members of the **sysadmin** fixed server role and the **db_owner** and **db_backupoperator** fixed database roles.</span></span>  
  
 <span data-ttu-id="454be-128">Eventuali problemi correlati alla proprietà e alle autorizzazioni sul file fisico del dispositivo di backup possono interferire con l'operazione di backup.</span><span class="sxs-lookup"><span data-stu-id="454be-128">Ownership and permission problems on the backup device's physical file can interfere with a backup operation.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="454be-129">sia possibile leggere e scrivere sul dispositivo e che l'account utilizzato per eseguire il servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] disponga delle autorizzazioni di scrittura.</span><span class="sxs-lookup"><span data-stu-id="454be-129">must be able to read and write to the device; the account under which the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service runs must have write permissions.</span></span> <span data-ttu-id="454be-130">Le autorizzazioni di accesso ai file, tuttavia, non vengono controllate dalla stored procedure [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql)che aggiunge una voce per un dispositivo di backup nelle tabelle di sistema.</span><span class="sxs-lookup"><span data-stu-id="454be-130">However, [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql), which adds an entry for a backup device in the system tables, does not check file access permissions.</span></span> <span data-ttu-id="454be-131">Di conseguenza, i problemi relativi all'accesso e alla proprietà del file fisico del dispositivo di backup potrebbero emergere solo in fase di accesso alla risorsa fisica durante un tentativo di backup o ripristino.</span><span class="sxs-lookup"><span data-stu-id="454be-131">Such problems on the backup device's physical file may not appear until the physical resource is accessed when the backup or restore is attempted.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="454be-132">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="454be-132">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-back-up-a-transaction-log"></a><span data-ttu-id="454be-133">Per eseguire il backup di un log delle transazioni</span><span class="sxs-lookup"><span data-stu-id="454be-133">To back up a transaction log</span></span>  
  
1.  <span data-ttu-id="454be-134">Dopo aver effettuato la connessione all'istanza appropriata del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Esplora oggetti fare clic sul nome del server per espanderne l'albero.</span><span class="sxs-lookup"><span data-stu-id="454be-134">After connecting to the appropriate instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="454be-135">Espandere **Database**e, a seconda del database, selezionare un database utente o espandere **Database di sistema** e selezionare un database di sistema.</span><span class="sxs-lookup"><span data-stu-id="454be-135">Expand **Databases**, and, depending on the database, either select a user database or expand **System Databases** and select a system database.</span></span>  
  
3.  <span data-ttu-id="454be-136">Fare clic con il pulsante destro del mouse sul database, scegliere **Attività**e quindi fare clic su **Backup**.</span><span class="sxs-lookup"><span data-stu-id="454be-136">Right-click the database, point to **Tasks**, and then click **Back Up**.</span></span> <span data-ttu-id="454be-137">Verrà visualizzata la finestra di dialogo **Backup database** .</span><span class="sxs-lookup"><span data-stu-id="454be-137">The **Back Up Database** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="454be-138">Verificare il nome del database nella casella di riepilogo **Database** .</span><span class="sxs-lookup"><span data-stu-id="454be-138">In the **Database** list box, verify the database name.</span></span> <span data-ttu-id="454be-139">È possibile selezionare facoltativamente un database diverso nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="454be-139">You can optionally select a different database from the list.</span></span>  
  
5.  <span data-ttu-id="454be-140">Verificare che il modello di recupero sia impostato su **FULL** o **BULK_LOGGED**.</span><span class="sxs-lookup"><span data-stu-id="454be-140">Verify that the recovery model is either **FULL** or **BULK_LOGGED**.</span></span>  
  
6.  <span data-ttu-id="454be-141">Nella casella di riepilogo **Tipo backup** selezionare **Log delle transazioni**.</span><span class="sxs-lookup"><span data-stu-id="454be-141">In the **Backup type** list box, select **Transaction Log**.</span></span>  
  
7.  <span data-ttu-id="454be-142">Facoltativamente, è possibile selezionare **Backup di sola copia** per creare un backup di sola copia.</span><span class="sxs-lookup"><span data-stu-id="454be-142">Optionally, you can select **Copy Only Backup** to create a copy-only backup.</span></span> <span data-ttu-id="454be-143">Un *backup di sola copia* è un backup di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] indipendente dalla sequenza di backup convenzionali di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="454be-143">A *copy-only backup* is a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup that is independent of the sequence of conventional [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backups.</span></span> <span data-ttu-id="454be-144">Per altre informazioni, vedere [Backup di sola copia &#40;SQL Server&#41;](copy-only-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="454be-144">For more information, see [Copy-Only Backups &#40;SQL Server&#41;](copy-only-backups-sql-server.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="454be-145">Quando si seleziona l'opzione **Differenziale** , non è possibile creare un backup di sola copia.</span><span class="sxs-lookup"><span data-stu-id="454be-145">When the **Differential** option is selected, you cannot create a copy-only backup.</span></span>  
  
8.  <span data-ttu-id="454be-146">Accettare il nome predefinito del set di backup indicato nella casella di testo **Nome** oppure immettere un nome diverso per il set di backup.</span><span class="sxs-lookup"><span data-stu-id="454be-146">Either accept the default backup set name suggested in the **Name** text box, or enter a different name for the backup set.</span></span>  
  
9. <span data-ttu-id="454be-147">Facoltativamente, immettere una descrizione del set di backup nella casella di testo **Descrizione** .</span><span class="sxs-lookup"><span data-stu-id="454be-147">Optionally, in the **Description** text box, enter a description of the backup set.</span></span>  
  
10. <span data-ttu-id="454be-148">Specificare la scadenza del set di backup:</span><span class="sxs-lookup"><span data-stu-id="454be-148">Specify when the backup set will expire:</span></span>  
  
    -   <span data-ttu-id="454be-149">Per impostare la scadenza del set di backup dopo un numero di giorni specifico, fare clic su **Dopo** (opzione predefinita) e immettere il numero di giorni dopo la creazione del set trascorsi i quali il set scadrà.</span><span class="sxs-lookup"><span data-stu-id="454be-149">To have the backup set expire after a specific number of days, click **After** (the default option), and enter the number of days after set creation that the set will expire.</span></span> <span data-ttu-id="454be-150">È possibile impostare un valore compreso nell'intervallo da 0 a 99999 giorni. L'impostazione del valore 0 giorni indica che il set di backup non ha scadenza.</span><span class="sxs-lookup"><span data-stu-id="454be-150">This value can be from 0 to 99999 days; a value of 0 days means that the backup set will never expire.</span></span>  
  
         <span data-ttu-id="454be-151">Il valore predefinito viene impostato nell'opzione **Periodo di memorizzazione predefinito supporti di backup (giorni)** della finestra di dialogo **Proprietà server** (pagina**Impostazioni database** ).</span><span class="sxs-lookup"><span data-stu-id="454be-151">The default value is set in the **Default backup media retention (in days)** option of the **Server Properties** dialog box (**Database Settings** page).</span></span> <span data-ttu-id="454be-152">Per accedere a questa finestra di dialogo, fare clic con il pulsante destro del mouse sul nome del server in Esplora oggetti, scegliere Proprietà e quindi selezionare la pagina **Impostazioni database** .</span><span class="sxs-lookup"><span data-stu-id="454be-152">To access this dialog box, right-click the server name in Object Explorer and select properties; then select the **Database Settings** page.</span></span>  
  
    -   <span data-ttu-id="454be-153">Per impostare una data di scadenza specifica per il set di backup, fare clic su **Il**e immettere la data di scadenza del set.</span><span class="sxs-lookup"><span data-stu-id="454be-153">To have the backup set expire on a specific date, click **On**, and enter the date on which the set will expire.</span></span>  
  
11. <span data-ttu-id="454be-154">Per selezionare il tipo di destinazione del backup fare clic su **Disco**, **URL** o **Nastro**.</span><span class="sxs-lookup"><span data-stu-id="454be-154">Choose the type of backup destination by clicking **Disk**, **URL** or **Tape**.</span></span> <span data-ttu-id="454be-155">Per selezionare i percorsi per un massimo di 64 unità disco o nastro contenenti un singolo set di supporti, fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="454be-155">To select the paths of up to 64 disk or tape drives containing a single media set, click **Add**.</span></span> <span data-ttu-id="454be-156">I percorsi selezionati vengono visualizzati nella casella di riepilogo **Backup su** .</span><span class="sxs-lookup"><span data-stu-id="454be-156">The selected paths are displayed in the **Backup to** list box.</span></span>  
  
     <span data-ttu-id="454be-157">Per rimuovere una destinazione di backup, selezionarla e fare clic su **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="454be-157">To remove a backup destination, select it and click **Remove**.</span></span> <span data-ttu-id="454be-158">Per visualizzare il contenuto di una destinazione di backup, selezionarla e fare clic su **Contenuto**.</span><span class="sxs-lookup"><span data-stu-id="454be-158">To view the contents of a backup destination, select it and click **Contents**.</span></span>  
  
12. <span data-ttu-id="454be-159">Per visualizzare o selezionare le opzioni avanzate, fare clic su **Opzioni** nel riquadro **Selezione pagina** .</span><span class="sxs-lookup"><span data-stu-id="454be-159">To view or select the advanced options, click **Options** in the **Select a page** pane.</span></span>  
  
13. <span data-ttu-id="454be-160">Selezionare un'opzione **Sovrascrivi supporti** facendo clic su una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="454be-160">Select an **Overwrite Media** option, by clicking one of the following:</span></span>  
  
    -   <span data-ttu-id="454be-161">**Esegui backup nel set di supporti esistente**</span><span class="sxs-lookup"><span data-stu-id="454be-161">**Back up to the existing media set**</span></span>  
  
         <span data-ttu-id="454be-162">Per questa opzione, fare clic su **Accoda al set di backup esistente** o **Sovrascrivi tutti i set di backup esistenti**.</span><span class="sxs-lookup"><span data-stu-id="454be-162">For this option, click either **Append to the existing backup set** or **Overwrite all existing backup sets**.</span></span> <span data-ttu-id="454be-163">Per altre informazioni, vedere [Set di supporti, gruppi di supporti e set di backup &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="454be-163">For more information, see [Media Sets, Media Families, and Backup Sets &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md).</span></span>  
  
         <span data-ttu-id="454be-164">Selezionare facoltativamente l'opzione **Controlla nome set di supporti e scadenza set di backup** per impostare la verifica della data e dell'ora di scadenza del set di supporti e del set di backup durante l'operazione di backup.</span><span class="sxs-lookup"><span data-stu-id="454be-164">Optionally, select **Check media set name and backup set expiration** to cause the backup operation to verify the date and time at which the media set and backup set expire.</span></span>  
  
         <span data-ttu-id="454be-165">Immettere facoltativamente un nome nella casella di testo **Nome set di supporti** .</span><span class="sxs-lookup"><span data-stu-id="454be-165">Optionally, enter a name in the **Media set name** text box.</span></span> <span data-ttu-id="454be-166">Se non si specifica un nome, verrà creato un set di supporti con nome vuoto.</span><span class="sxs-lookup"><span data-stu-id="454be-166">If no name is specified, a media set with a blank name is created.</span></span> <span data-ttu-id="454be-167">Se si specifica un nome per il set di supporti, il supporto (nastro o disco) verrà controllato per verificare che il nome effettivo corrisponda al nome specificato.</span><span class="sxs-lookup"><span data-stu-id="454be-167">If you specify a media set name, the media (tape or disk) is checked to see whether the actual name matches the name you enter here.</span></span>  
  
         <span data-ttu-id="454be-168">Se non si specifica il nome del set di supporti e si seleziona la casella di controllo per il controllo del nome, in caso di esito positivo anche il nome dei supporti nei supporti risulterà vuoto.</span><span class="sxs-lookup"><span data-stu-id="454be-168">If you leave the media name blank and check the box to check it against the media, success will equal the media name on the media also being blank.</span></span>  
  
    -   <span data-ttu-id="454be-169">**Esegui backup in un nuovo set di supporti e cancella tutti i set di backup esistenti**</span><span class="sxs-lookup"><span data-stu-id="454be-169">**Back up to a new media set, and erase all existing backup sets**</span></span>  
  
         <span data-ttu-id="454be-170">Per questa opzione, immettere un nome nella casella di testo **Nome nuovo set di supporti** e, facoltativamente, aggiungere una descrizione per il set di supporti nella casella di testo **Descrizione nuovo set di supporti** .</span><span class="sxs-lookup"><span data-stu-id="454be-170">For this option, enter a name in the **New media set name** text box, and, optionally, describe the media set in the **New media set description** text box.</span></span> <span data-ttu-id="454be-171">Per altre informazioni, vedere [Set di supporti, gruppi di supporti e set di backup &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="454be-171">For more information, see [Media Sets, Media Families, and Backup Sets &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md).</span></span>  
  
14. <span data-ttu-id="454be-172">Nella sezione **Affidabilità** selezionare facoltativamente una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="454be-172">In the **Reliability** section, optionally, check:</span></span>  
  
    -   <span data-ttu-id="454be-173">**Verifica backup al termine**.</span><span class="sxs-lookup"><span data-stu-id="454be-173">**Verify backup when finished**.</span></span>  
  
    -   <span data-ttu-id="454be-174">**Esegui checksum prima della scrittura nei supporti**e, facoltativamente, **Continua in caso di errori checksum**.</span><span class="sxs-lookup"><span data-stu-id="454be-174">**Perform checksum before writing to media**, and, optionally, **Continue on checksum error**.</span></span> <span data-ttu-id="454be-175">Per informazioni sui checksum, vedere [Possibili errori relativi ai supporti durante il backup e il ripristino &#40;SQL Server&#41;](possible-media-errors-during-backup-and-restore-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="454be-175">For information on checksums, see [Possible Media Errors During Backup and Restore &#40;SQL Server&#41;](possible-media-errors-during-backup-and-restore-sql-server.md).</span></span>  
  
15. <span data-ttu-id="454be-176">Nella sezione **Log delle transazioni** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="454be-176">In the **Transaction log** section:</span></span>  
  
    -   <span data-ttu-id="454be-177">Per i backup dei log di routine, mantenere l'impostazione predefinita **Tronca il log delle transazioni rimuovendo le voci inattive**.</span><span class="sxs-lookup"><span data-stu-id="454be-177">For routine log backups, keep the default selection, **Truncate the transaction log by removing inactive entries**.</span></span>  
  
    -   <span data-ttu-id="454be-178">Per eseguire il backup della parte finale del log, ovvero il log attivo, selezionare **Esegui backup della parte finale del log e lascia il database in stato di ripristino**.</span><span class="sxs-lookup"><span data-stu-id="454be-178">To back up the tail of the log (that is, the active log), check **Back up the tail of the log, and leave database in the restoring state**.</span></span>  
  
         <span data-ttu-id="454be-179">Un backup della parte finale del log viene eseguito dopo un errore per evitare la perdita di dati salvando la parte finale del log.</span><span class="sxs-lookup"><span data-stu-id="454be-179">A tail-log backup is taken after a failure to back up the tail of the log in order to prevent work loss.</span></span> <span data-ttu-id="454be-180">Eseguire il backup del log attivo, ovvero il backup della parte finale del log, sia dopo un errore, prima di iniziare a ripristinare il database, sia quando si esegue il failover a un database secondario.</span><span class="sxs-lookup"><span data-stu-id="454be-180">Back up the active log (a tail-log backup) both after a failure, before beginning to restore the database, or when failing over to a secondary database.</span></span> <span data-ttu-id="454be-181">Selezionare questa opzione corrisponde a specificare l'opzione NORECOVERY nell'istruzione BACKUP LOG di Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="454be-181">Selecting this option is equivalent to specifying the NORECOVERY option in the BACKUP LOG statement of Transact-SQL.</span></span> <span data-ttu-id="454be-182">Per altre informazioni sui backup della parte finale del log, vedere [Backup della parte finale del log &#40;SQL Server&#41;](tail-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="454be-182">For more information about tail-log backups, see [Tail-Log Backups &#40;SQL Server&#41;](tail-log-backups-sql-server.md).</span></span>  
  
16. <span data-ttu-id="454be-183">Se si esegue il backup su un'unità nastro, come specificato nella sezione **Destinazione** della pagina **Generale** , l'opzione **Scarica nastro al termine del backup** sarà attiva.</span><span class="sxs-lookup"><span data-stu-id="454be-183">If you are backing up to a tape drive (as specified in the **Destination** section of the **General** page), the **Unload the tape after backup** option is active.</span></span> <span data-ttu-id="454be-184">Se si seleziona questa opzione, verrà inoltre attivata l'opzione **Riavvolgi il nastro prima di scaricarlo** .</span><span class="sxs-lookup"><span data-stu-id="454be-184">Clicking this option activates the **Rewind the tape before unloading** option.</span></span>  
  
17. [!INCLUDE[ssEnterpriseEd10](../../includes/ssenterpriseed10-md.md)] <span data-ttu-id="454be-185">e versioni successive supporta la [compressione dei backup](backup-compression-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="454be-185">and later supports [backup compression](backup-compression-sql-server.md).</span></span> <span data-ttu-id="454be-186">Per impostazione predefinita, la compressione di un backup dipende dal valore dell'opzione di configurazione del server **Valore predefinito di compressione backup**.</span><span class="sxs-lookup"><span data-stu-id="454be-186">By default, whether a backup is compressed depends on the value of the **backup-compression default** server configuration option.</span></span> <span data-ttu-id="454be-187">Tuttavia, indipendentemente dall'impostazione predefinita a livello di server corrente, è possibile comprimere un backup selezionando **Comprimi backup**ed è possibile impedire la compressione selezionando **Non comprimere il backup**.</span><span class="sxs-lookup"><span data-stu-id="454be-187">However, regardless of the current server-level default, you can compress a backup by checking **Compress backup**, and you can prevent compression by checking **Do not compress backup**.</span></span>  
  
     <span data-ttu-id="454be-188">**Per visualizzare l'impostazione predefinita corrente della compressione dei backup**</span><span class="sxs-lookup"><span data-stu-id="454be-188">**To view the current backup compression default**</span></span>  
  
    -   [<span data-ttu-id="454be-189">Visualizzare o configurare l'opzione di configurazione del server backup compression default</span><span class="sxs-lookup"><span data-stu-id="454be-189">View or Configure the backup compression default Server Configuration Option</span></span>](../../database-engine/configure-windows/view-or-configure-the-backup-compression-default-server-configuration-option.md)  
  
 <span data-ttu-id="454be-190">**Crittografia**</span><span class="sxs-lookup"><span data-stu-id="454be-190">**Encryption**</span></span>  
  
 <span data-ttu-id="454be-191">Per crittografare il file di backup, selezionare la casella di controllo **Crittografa backup** .</span><span class="sxs-lookup"><span data-stu-id="454be-191">To encrypt the backup file check the **Encrypt backup** check box.</span></span> <span data-ttu-id="454be-192">Selezionare un algoritmo di crittografia da utilizzare per la crittografia del file di backup e fornire un certificato o una chiave asimmetrica.</span><span class="sxs-lookup"><span data-stu-id="454be-192">Select an encryption algorithm to use for encrypting the backup file and provide a Certificate or Asymmetric key.</span></span> <span data-ttu-id="454be-193">Gli algoritmi di crittografia disponibili sono:</span><span class="sxs-lookup"><span data-stu-id="454be-193">The available algorithms for encryption are:</span></span>  
  
-   <span data-ttu-id="454be-194">AES 128</span><span class="sxs-lookup"><span data-stu-id="454be-194">AES 128</span></span>  
  
-   <span data-ttu-id="454be-195">AES 192</span><span class="sxs-lookup"><span data-stu-id="454be-195">AES 192</span></span>  
  
-   <span data-ttu-id="454be-196">AES 256</span><span class="sxs-lookup"><span data-stu-id="454be-196">AES 256</span></span>  
  
-   <span data-ttu-id="454be-197">Triple DES</span><span class="sxs-lookup"><span data-stu-id="454be-197">Triple DES</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="454be-198">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="454be-198">Using Transact-SQL</span></span>  
  
#### <a name="to-back-up-a-transaction-log"></a><span data-ttu-id="454be-199">Per eseguire il backup di un log delle transazioni</span><span class="sxs-lookup"><span data-stu-id="454be-199">To back up a transaction log</span></span>  
  
1.  <span data-ttu-id="454be-200">Per eseguire il backup del log delle transazioni, eseguire l'istruzione BACKUP LOG specificando gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="454be-200">Execute the BACKUP LOG statement to back up the transaction log, specifying the following:</span></span>  
  
    -   <span data-ttu-id="454be-201">Il nome del database a cui appartiene il log delle transazioni di cui si desidera eseguire il backup.</span><span class="sxs-lookup"><span data-stu-id="454be-201">The name of the database to which the transaction log that you want to back up belongs.</span></span>  
  
    -   <span data-ttu-id="454be-202">Il dispositivo di backup in cui viene scritto il backup del log della transazione.</span><span class="sxs-lookup"><span data-stu-id="454be-202">The backup device where the transaction log backup is written.</span></span>  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="454be-203">Esempio (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="454be-203">Example (Transact-SQL)</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="454be-204">In questo esempio viene utilizzato il database [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] in cui viene utilizzato il modello di recupero con registrazione minima.</span><span class="sxs-lookup"><span data-stu-id="454be-204">This example uses the [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] database, which uses the simple recovery model.</span></span> <span data-ttu-id="454be-205">Per consentire i backup del log, prima di eseguire un backup completo del database, il database viene impostato in modo da utilizzare il modello di recupero con registrazione completa.</span><span class="sxs-lookup"><span data-stu-id="454be-205">To permit log backups, before taking a full database backup, the database was set to use the full recovery model.</span></span> <span data-ttu-id="454be-206">Per altre informazioni, vedere [Visualizzazione o modifica del modello di recupero di un database &#40;SQL Server&#41;](view-or-change-the-recovery-model-of-a-database-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="454be-206">For more information, see [View or Change the Recovery Model of a Database &#40;SQL Server&#41;](view-or-change-the-recovery-model-of-a-database-sql-server.md).</span></span>  
  
 <span data-ttu-id="454be-207">In questo esempio viene creato un backup del log delle transazioni per il database [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] nel dispositivo di backup denominato creato in precedenza, `MyAdvWorks_FullRM_log1`.</span><span class="sxs-lookup"><span data-stu-id="454be-207">This example creates a transaction log backup for the [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] database to the previously created named backup device, `MyAdvWorks_FullRM_log1`.</span></span>  
  
```sql  
BACKUP LOG AdventureWorks2012  
   TO MyAdvWorks_FullRM_log1;  
GO  
```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="454be-208">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="454be-208">Using PowerShell</span></span>  
  
<span data-ttu-id="454be-209">Utilizzare il cmdlet `Backup-SqlDatabase` e specificare `Log` per il valore del parametro `-BackupAction`.</span><span class="sxs-lookup"><span data-stu-id="454be-209">Use the `Backup-SqlDatabase` cmdlet and specify `Log` for the value of the `-BackupAction` parameter.</span></span>  
  
<span data-ttu-id="454be-210">L'esempio seguente consente di creare un backup del log del database di `MyDB` nel percorso di backup predefinito dell'istanza del server `Computer\Instance`.</span><span class="sxs-lookup"><span data-stu-id="454be-210">The following example creates a log backup of the `MyDB` database to the default backup location of the server instance `Computer\Instance`.</span></span>  
  
    ```powershell
    Backup-SqlDatabase -ServerInstance Computer\Instance -Database MyDB -BackupAction Log  
    ```  
  
<span data-ttu-id="454be-211">Per configurare e usare il provider di SQL Server PowerShell, vedere [provider di SQL Server PowerShell](../../powershell/sql-server-powershell-provider.md).</span><span class="sxs-lookup"><span data-stu-id="454be-211">To set up and use the SQL Server PowerShell provider, see [SQL Server PowerShell Provider](../../powershell/sql-server-powershell-provider.md).</span></span>
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="454be-212">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="454be-212">Related Tasks</span></span>  
  
-   [<span data-ttu-id="454be-213">Ripristinare un backup del log delle transazioni &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="454be-213">Restore a Transaction Log Backup &#40;SQL Server&#41;</span></span>](restore-a-transaction-log-backup-sql-server.md)  
  
-   [<span data-ttu-id="454be-214">Ripristinare un database di SQL Server fino a un punto specifico &#40;modello di recupero con registrazione completa&#41;</span><span class="sxs-lookup"><span data-stu-id="454be-214">Restore a SQL Server Database to a Point in Time &#40;Full Recovery Model&#41;</span></span>](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md)  
  
-   [<span data-ttu-id="454be-215">Risolvere i problemi relativi a un log delle transazioni completo &#40;Errore di SQL Server 9002&#41;</span><span class="sxs-lookup"><span data-stu-id="454be-215">Troubleshoot a Full Transaction Log &#40;SQL Server Error 9002&#41;</span></span>](../logs/troubleshoot-a-full-transaction-log-sql-server-error-9002.md)  
  
## <a name="see-also"></a><span data-ttu-id="454be-216">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="454be-216">See Also</span></span>  
 <span data-ttu-id="454be-217">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="454be-217">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="454be-218">[Applicare backup del log delle transazioni &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="454be-218">[Apply Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span></span>  
 <span data-ttu-id="454be-219">[Piani di manutenzione](../maintenance-plans/maintenance-plans.md) </span><span class="sxs-lookup"><span data-stu-id="454be-219">[Maintenance Plans](../maintenance-plans/maintenance-plans.md) </span></span>  
 [<span data-ttu-id="454be-220">Backup completi del file &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="454be-220">Full File Backups &#40;SQL Server&#41;</span></span>](full-file-backups-sql-server.md)  
