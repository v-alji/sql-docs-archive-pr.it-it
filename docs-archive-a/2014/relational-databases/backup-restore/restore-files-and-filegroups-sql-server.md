---
title: Ripristinare file e filegroup (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- sql12.swb.restorefilesandfilegrps.general.f1
- sql12.swb.restorefilesandfilegrps.options.f1
- sql12.swb.bselectfilegrpsfiles.f1
helpviewer_keywords:
- SQL Server Management Studio [SQL Server], restoring files and filegroups
- restoring [SQL Server], files
ms.assetid: 72603b21-3065-4b56-8b01-11b707911b05
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d2576f1326cb50fa197b1623aaa1326d70137823
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715423"
---
# <a name="restore-files-and-filegroups-sql-server"></a><span data-ttu-id="1e8e5-102">Ripristino di file e filegroup (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="1e8e5-102">Restore Files and Filegroups (SQL Server)</span></span>
  <span data-ttu-id="1e8e5-103">In questo argomento viene descritto come ripristinare file e filegroup in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1e8e5-103">This topic describes how to restore files and filegroups in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="1e8e5-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="1e8e5-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="1e8e5-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="1e8e5-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="1e8e5-106">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="1e8e5-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
-   [<span data-ttu-id="1e8e5-107">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="1e8e5-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="1e8e5-108">**Ripristino di file e filegroup utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="1e8e5-108">**To restore files and filegroups, using:**</span></span>  
  
     [<span data-ttu-id="1e8e5-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1e8e5-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="1e8e5-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1e8e5-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="1e8e5-111">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="1e8e5-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="1e8e5-112">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="1e8e5-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="1e8e5-113">L'amministratore di sistema che esegue il ripristino di file e di filegroup deve essere l'unico utente attualmente collegato al database da ripristinare.</span><span class="sxs-lookup"><span data-stu-id="1e8e5-113">The system administrator restoring the files and filegroups must be the only person currently using the database to be restored.</span></span>  
  
-   <span data-ttu-id="1e8e5-114">Non è possibile utilizzare RESTORE in una transazione esplicita o implicita.</span><span class="sxs-lookup"><span data-stu-id="1e8e5-114">RESTORE is not allowed in an explicit or implicit transaction.</span></span>  
  
-   <span data-ttu-id="1e8e5-115">Con il modello di recupero con registrazione minima, il file deve appartenere a un filegroup di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="1e8e5-115">Under the simple recovery model, the file must belong to a read-only filegroup.</span></span>  
  
-   <span data-ttu-id="1e8e5-116">In base al modello di recupero con registrazione completa o con registrazione minima delle operazioni bulk, prima di poter ripristinare file è necessario eseguire il backup del log delle transazioni attivo, noto come parte finale del log.</span><span class="sxs-lookup"><span data-stu-id="1e8e5-116">Under the full or bulk-logged recovery model, before you can restore files, you must back up the active transaction log (known as the tail of the log).</span></span> <span data-ttu-id="1e8e5-117">Per altre informazioni, vedere [Backup di un log delle transazioni &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="1e8e5-117">For more information, see [Back Up a Transaction Log &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md).</span></span>  
  
-   <span data-ttu-id="1e8e5-118">Per ripristinare un database crittografato, è necessario poter accedere alla chiave asimmetrica o al certificato utilizzato per crittografare il database.</span><span class="sxs-lookup"><span data-stu-id="1e8e5-118">To restore a database that is encrypted, you must have access to the certificate or asymmetric key that was used to encrypt the database.</span></span> <span data-ttu-id="1e8e5-119">Non è possibile effettuare l'operazione di ripristino del database senza almeno uno di questi due elementi.</span><span class="sxs-lookup"><span data-stu-id="1e8e5-119">Without the certificate or asymmetric key, the database cannot be restored.</span></span> <span data-ttu-id="1e8e5-120">Di conseguenza, il certificato utilizzato per crittografare la chiave di crittografia del database deve essere conservato fino a quando il backup è necessario.</span><span class="sxs-lookup"><span data-stu-id="1e8e5-120">As a result, the certificate that is used to encrypt the database encryption key must be retained as long as the backup is needed.</span></span> <span data-ttu-id="1e8e5-121">Per altre informazioni, vedere [SQL Server Certificates and Asymmetric Keys](../security/sql-server-certificates-and-asymmetric-keys.md).</span><span class="sxs-lookup"><span data-stu-id="1e8e5-121">For more information, see [SQL Server Certificates and Asymmetric Keys](../security/sql-server-certificates-and-asymmetric-keys.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="1e8e5-122">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="1e8e5-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="1e8e5-123">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="1e8e5-123">Permissions</span></span>  
 <span data-ttu-id="1e8e5-124">Se il database da ripristinare non esiste, per eseguire un'operazione RESTORE l'utente deve disporre delle autorizzazioni CREATE DATABASE.</span><span class="sxs-lookup"><span data-stu-id="1e8e5-124">If the database being restored does not exist, the user must have CREATE DATABASE permissions to be able to execute RESTORE.</span></span> <span data-ttu-id="1e8e5-125">Se il database esiste, le autorizzazioni per l'istruzione RESTORE vengono assegnate per impostazione predefinita ai membri dei ruoli predefiniti del server **sysadmin** e **dbcreator** e al proprietario (**dbo**) del database. Per l'opzione FROM DATABASE_SNAPSHOT, il database esiste sempre.</span><span class="sxs-lookup"><span data-stu-id="1e8e5-125">If the database exists, RESTORE permissions default to members of the **sysadmin** and **dbcreator** fixed server roles and the owner (**dbo**) of the database (for the FROM DATABASE_SNAPSHOT option, the database always exists).</span></span>  
  
 <span data-ttu-id="1e8e5-126">Le autorizzazioni per l'istruzione RESTORE vengono assegnate ai ruoli in cui le informazioni sull'appartenenza sono sempre disponibili per il server.</span><span class="sxs-lookup"><span data-stu-id="1e8e5-126">RESTORE permissions are given to roles in which membership information is always readily available to the server.</span></span> <span data-ttu-id="1e8e5-127">Poiché è possibile controllare l'appartenenza ai ruoli predefiniti del database solo quando il database è accessibile e non è danneggiato, condizioni che non risultano sempre vere quando si esegue un'operazione RESTORE, i membri del ruolo predefinito del database **db_owner** non dispongono delle autorizzazioni per l'istruzione RESTORE.</span><span class="sxs-lookup"><span data-stu-id="1e8e5-127">Because fixed database role membership can be checked only when the database is accessible and undamaged, which is not always the case when RESTORE is executed, members of the **db_owner** fixed database role do not have RESTORE permissions.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="1e8e5-128">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1e8e5-128">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-restore-files-and-filegroups"></a><span data-ttu-id="1e8e5-129">Per ripristinare file e filegroup</span><span class="sxs-lookup"><span data-stu-id="1e8e5-129">To restore files and filegroups</span></span>  
  
1.  <span data-ttu-id="1e8e5-130">Dopo aver eseguito la connessione all'istanza appropriata del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Esplora oggetti fare clic sul nome del server per espandere l'albero del server.</span><span class="sxs-lookup"><span data-stu-id="1e8e5-130">After you connect to the appropriate instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="1e8e5-131">Espandere **Database**.</span><span class="sxs-lookup"><span data-stu-id="1e8e5-131">Expand **Databases**.</span></span> <span data-ttu-id="1e8e5-132">A seconda del database, selezionare un database utente oppure espandere **Database di sistema**e selezionare un database di sistema.</span><span class="sxs-lookup"><span data-stu-id="1e8e5-132">Depending on the database, either select a user database or expand **System Databases**, and then select a system database.</span></span>  
  
3.  <span data-ttu-id="1e8e5-133">Fare clic con il pulsante destro del mouse sul database, scegliere **Attività**e quindi fare clic su **Ripristina**.</span><span class="sxs-lookup"><span data-stu-id="1e8e5-133">Right-click the database, point to **Tasks**, and then click **Restore**.</span></span>  
  
4.  <span data-ttu-id="1e8e5-134">Fare clic su **File e filegroup**. Verrà visualizzata la finestra di dialogo **Ripristina file e filegroup** .</span><span class="sxs-lookup"><span data-stu-id="1e8e5-134">Click **Files and Filegroups**, which opens the **Restore Files and Filegroups** dialog box.</span></span>  
  
5.  <span data-ttu-id="1e8e5-135">Nella pagina **Generale** nella casella di riepilogo **Database di destinazione** , immettere il database da ripristinare.</span><span class="sxs-lookup"><span data-stu-id="1e8e5-135">On the **General** page, in the **To database** list box, enter the database to restore.</span></span> <span data-ttu-id="1e8e5-136">È possibile immettere un nuovo database oppure sceglierne uno esistente dall'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="1e8e5-136">You can enter a new database or choose an existing database from the drop-down list.</span></span> <span data-ttu-id="1e8e5-137">Nell'elenco sono inclusi tutti i database presenti nel server, ad eccezione dei database di sistema **master** e **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="1e8e5-137">The list includes all databases on the server, excluding the system databases **master** and **tempdb**.</span></span>  
  
6.  <span data-ttu-id="1e8e5-138">Per specificare l'origine e il percorso dei set di backup da ripristinare, fare clic su una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1e8e5-138">To specify the source and location of the backup sets to restore, click one of the following options:</span></span>  
  
    -   <span data-ttu-id="1e8e5-139">**Database di origine**</span><span class="sxs-lookup"><span data-stu-id="1e8e5-139">**From database**</span></span>  
  
         <span data-ttu-id="1e8e5-140">Immettere il nome di un database nella casella di riepilogo.</span><span class="sxs-lookup"><span data-stu-id="1e8e5-140">Enter a database name in the list box.</span></span> <span data-ttu-id="1e8e5-141">Nell'elenco sono inclusi solo i database di cui è stato eseguito il backup in base alla cronologia di backup di **msdb** .</span><span class="sxs-lookup"><span data-stu-id="1e8e5-141">This list contains only databases that have been backed up according to the **msdb** backup history.</span></span>  
  
    -   <span data-ttu-id="1e8e5-142">**Dispositivo di origine**</span><span class="sxs-lookup"><span data-stu-id="1e8e5-142">**From device**</span></span>  
  
         <span data-ttu-id="1e8e5-143">Fare clic sul pulsante Sfoglia</span><span class="sxs-lookup"><span data-stu-id="1e8e5-143">Click the browse button.</span></span> <span data-ttu-id="1e8e5-144">Nella finestra di dialogo **Seleziona dispositivi di backup** selezionare uno dei tipi di dispositivo elencati nella casella di riepilogo **Tipo di supporti di backup** .</span><span class="sxs-lookup"><span data-stu-id="1e8e5-144">In the **Specify backup devices** dialog box, select one of the listed device types in the **Backup media type** list box.</span></span> <span data-ttu-id="1e8e5-145">Per selezionare uno o più dispositivi per la casella di riepilogo **Supporti di backup** , fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="1e8e5-145">To select one or more devices for the **Backup media** list box, click **Add**.</span></span>  
  
         <span data-ttu-id="1e8e5-146">Dopo avere aggiunto i dispositivi desiderati nella casella di riepilogo **Dispositivi di backup** , fare clic su **OK** per tornare alla pagina **Generale** .</span><span class="sxs-lookup"><span data-stu-id="1e8e5-146">After you add the devices you want to the **Backup media** list box, click **OK** to return to the **General** page.</span></span>  
  
7.  <span data-ttu-id="1e8e5-147">Nella griglia **Selezionare i set di backup da ripristinare** selezionare i set di backup che si desidera ripristinare.</span><span class="sxs-lookup"><span data-stu-id="1e8e5-147">In the **Select the backup sets to restore** grid, select the backups to restore.</span></span> <span data-ttu-id="1e8e5-148">In questa griglia vengono visualizzati i backup disponibili per il percorso specificato.</span><span class="sxs-lookup"><span data-stu-id="1e8e5-148">This grid displays the backups available for the specified location.</span></span> <span data-ttu-id="1e8e5-149">Per impostazione predefinita, viene suggerito un piano di recupero.</span><span class="sxs-lookup"><span data-stu-id="1e8e5-149">By default, a recovery plan is suggested.</span></span> <span data-ttu-id="1e8e5-150">Per ignorare il piano di recupero suggerito, è possibile modificare le impostazioni selezionate nella griglia.</span><span class="sxs-lookup"><span data-stu-id="1e8e5-150">To override the suggested recovery plan, you can change the selections in the grid.</span></span> <span data-ttu-id="1e8e5-151">I backup che dipendono da un backup deselezionato vengono automaticamente deselezionati.</span><span class="sxs-lookup"><span data-stu-id="1e8e5-151">Any backups that depend on a deselected backup are deselected automatically.</span></span>  
  
    |<span data-ttu-id="1e8e5-152">Intestazione della colonna</span><span class="sxs-lookup"><span data-stu-id="1e8e5-152">Column head</span></span>|<span data-ttu-id="1e8e5-153">Valori</span><span class="sxs-lookup"><span data-stu-id="1e8e5-153">Values</span></span>|  
    |-----------------|------------|  
    |<span data-ttu-id="1e8e5-154">**Restore**</span><span class="sxs-lookup"><span data-stu-id="1e8e5-154">**Restore**</span></span>|<span data-ttu-id="1e8e5-155">Le caselle di controllo selezionate indicano i set di backup da ripristinare.</span><span class="sxs-lookup"><span data-stu-id="1e8e5-155">The selected check boxes indicate the backup sets to be restored.</span></span>|  
    |<span data-ttu-id="1e8e5-156">**Nome**</span><span class="sxs-lookup"><span data-stu-id="1e8e5-156">**Name**</span></span>|<span data-ttu-id="1e8e5-157">Nome del set di backup.</span><span class="sxs-lookup"><span data-stu-id="1e8e5-157">The name of the backup set.</span></span>|  
    |<span data-ttu-id="1e8e5-158">**Tipo di file**</span><span class="sxs-lookup"><span data-stu-id="1e8e5-158">**File Type**</span></span>|<span data-ttu-id="1e8e5-159">Specifica il tipo di dati nel backup: **dati**, **registro** o **dati FILESTREAM**.</span><span class="sxs-lookup"><span data-stu-id="1e8e5-159">Specifies the type of data in the backup: **Data**, **Log**, or **Filestream Data**.</span></span> <span data-ttu-id="1e8e5-160">I dati contenuti nelle tabelle sono nei file **Dati** .</span><span class="sxs-lookup"><span data-stu-id="1e8e5-160">Data that is contained in tables is in **Data** files.</span></span> <span data-ttu-id="1e8e5-161">I dati del log delle transazioni sono nei file **Log** .</span><span class="sxs-lookup"><span data-stu-id="1e8e5-161">Transaction log data is in **Log** files.</span></span> <span data-ttu-id="1e8e5-162">I dati BLOB (Binary Large Object, oggetto binario di grandi dimensioni) archiviati nel file system si trovano nei file **Dati FILESTREAM** .</span><span class="sxs-lookup"><span data-stu-id="1e8e5-162">Binary large object (BLOB) data that is stored on the file system is in **Filestream Data** files.</span></span>|  
    |<span data-ttu-id="1e8e5-163">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="1e8e5-163">**Type**</span></span>|<span data-ttu-id="1e8e5-164">Tipo di operazione di backup eseguita: **Completo**, **Differenziale** o **Log delle transazioni**.</span><span class="sxs-lookup"><span data-stu-id="1e8e5-164">The type of backup performed: **Full**, **Differential**, or **Transaction Log**.</span></span>|  
    |<span data-ttu-id="1e8e5-165">**Server**</span><span class="sxs-lookup"><span data-stu-id="1e8e5-165">**Server**</span></span>|<span data-ttu-id="1e8e5-166">Nome dell'istanza del Motore di database che ha eseguito l'operazione di backup.</span><span class="sxs-lookup"><span data-stu-id="1e8e5-166">The name of the Database-Engine instance that performed the backup operation.</span></span>|  
    |<span data-ttu-id="1e8e5-167">**Nome file logico**</span><span class="sxs-lookup"><span data-stu-id="1e8e5-167">**File Logical Name**</span></span>|<span data-ttu-id="1e8e5-168">Nome logico del file.</span><span class="sxs-lookup"><span data-stu-id="1e8e5-168">The logical name of the file.</span></span>|  
    |<span data-ttu-id="1e8e5-169">**Database**</span><span class="sxs-lookup"><span data-stu-id="1e8e5-169">**Database**</span></span>|<span data-ttu-id="1e8e5-170">Nome del database interessato dall'operazione di backup.</span><span class="sxs-lookup"><span data-stu-id="1e8e5-170">The name of the database involved in the backup operation.</span></span>|  
    |<span data-ttu-id="1e8e5-171">**Data inizio**</span><span class="sxs-lookup"><span data-stu-id="1e8e5-171">**Start Date**</span></span>|<span data-ttu-id="1e8e5-172">Data e ora di inizio dell'operazione di backup, visualizzate in base alle impostazioni internazionali del client.</span><span class="sxs-lookup"><span data-stu-id="1e8e5-172">The date and time when the backup operation began, presented in the regional setting of the client.</span></span>|  
    |<span data-ttu-id="1e8e5-173">**Data fine**</span><span class="sxs-lookup"><span data-stu-id="1e8e5-173">**Finish Date**</span></span>|<span data-ttu-id="1e8e5-174">Data e ora di fine dell'operazione di backup, visualizzate in base alle impostazioni internazionali del client.</span><span class="sxs-lookup"><span data-stu-id="1e8e5-174">The date and time when the backup operation finished, presented in the regional setting of the client.</span></span>|  
    |<span data-ttu-id="1e8e5-175">**Dimensione**</span><span class="sxs-lookup"><span data-stu-id="1e8e5-175">**Size**</span></span>|<span data-ttu-id="1e8e5-176">Dimensioni in byte del set di backup.</span><span class="sxs-lookup"><span data-stu-id="1e8e5-176">The size of the backup set in bytes.</span></span>|  
    |<span data-ttu-id="1e8e5-177">**Nome utente**</span><span class="sxs-lookup"><span data-stu-id="1e8e5-177">**User Name**</span></span>|<span data-ttu-id="1e8e5-178">Nome dell'utente che ha eseguito l'operazione di backup.</span><span class="sxs-lookup"><span data-stu-id="1e8e5-178">The name of the user who performed the backup operation.</span></span>|  
  
8.  <span data-ttu-id="1e8e5-179">Per visualizzare o selezionare le opzioni avanzate, fare clic su **Opzioni** nel riquadro **Selezione pagina**.</span><span class="sxs-lookup"><span data-stu-id="1e8e5-179">To view or select the advanced options, click **Options** in the **Select a page pane**.</span></span>  
  
9. <span data-ttu-id="1e8e5-180">Nel pannello **Opzioni di ripristino** è possibile scegliere una qualsiasi delle opzioni seguenti, in base alla specifica situazione.</span><span class="sxs-lookup"><span data-stu-id="1e8e5-180">In the **Restore options** panel, you can choose any of the following options, if appropriate for your situation.</span></span>  
  
     <span data-ttu-id="1e8e5-181">**Ripristina come filegroup**</span><span class="sxs-lookup"><span data-stu-id="1e8e5-181">**Restore as filegroup**</span></span>  
     <span data-ttu-id="1e8e5-182">Indica che un intero filegroup è in fase di ripristino.</span><span class="sxs-lookup"><span data-stu-id="1e8e5-182">Indicates that an entire filegroup is being restored.</span></span>  
  
     <span data-ttu-id="1e8e5-183">**Sovrascrivi il database esistente**</span><span class="sxs-lookup"><span data-stu-id="1e8e5-183">**Overwrite the existing database**</span></span>  
     <span data-ttu-id="1e8e5-184">Specifica che l'operazione di ripristino deve sovrascrivere eventuali database esistenti e i file correlati, anche se esiste già un database o un file con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="1e8e5-184">Specifies that the restore operation should overwrite any existing databases and their related files, even if another database or file already exists with the same name.</span></span>  
  
     <span data-ttu-id="1e8e5-185">La selezione di questa opzione equivale all'utilizzo dell'opzione REPLACE in un'istruzione RESTORE [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1e8e5-185">Selecting this option is equivalent to using the REPLACE option in a [!INCLUDE[tsql](../../includes/tsql-md.md)] RESTORE statement.</span></span>  
  
     <span data-ttu-id="1e8e5-186">**Chiedi conferma prima del ripristino di ogni backup**</span><span class="sxs-lookup"><span data-stu-id="1e8e5-186">**Prompt before restoring each backup**</span></span>  
     <span data-ttu-id="1e8e5-187">Viene richiesta la conferma dell'utente prima del ripristino di ogni set di backup.</span><span class="sxs-lookup"><span data-stu-id="1e8e5-187">Asks you for confirmation before restoring each backup set.</span></span>  
  
     <span data-ttu-id="1e8e5-188">Questa opzione risulta particolarmente utile quando è necessario scambiare i nastri di set di supporti diversi, ad esempio quando il server dispone di un solo dispositivo nastro.</span><span class="sxs-lookup"><span data-stu-id="1e8e5-188">This option is particularly useful where you must swap tapes for different media sets, such as when the server has one tape device.</span></span>  
  
     <span data-ttu-id="1e8e5-189">**Limita accesso al database ripristinato**</span><span class="sxs-lookup"><span data-stu-id="1e8e5-189">**Restrict access to the restored database**</span></span>  
     <span data-ttu-id="1e8e5-190">Consente di rendere disponibile il database ripristinato solo per i membri di **db_owner**, **dbcreator**o **sysadmin**.</span><span class="sxs-lookup"><span data-stu-id="1e8e5-190">Makes the restored database available only to the members of **db_owner**, **dbcreator**, or **sysadmin**.</span></span>  
  
     <span data-ttu-id="1e8e5-191">La selezione di questa opzione equivale all'utilizzo dell'opzione RESTRICTED_USER in un'istruzione RESTORE [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1e8e5-191">Selecting this option is synonymous to using the RESTRICTED_USER option in a [!INCLUDE[tsql](../../includes/tsql-md.md)] RESTORE statement.</span></span>  
  
10. <span data-ttu-id="1e8e5-192">È possibile ripristinare il database in un nuovo percorso specificando una nuova destinazione di ripristino per ogni file nella griglia **Ripristina file di database come** .</span><span class="sxs-lookup"><span data-stu-id="1e8e5-192">Optionally, you can restore the database to a new location by specifying a new restore destination for each file in the **Restore database files as** grid.</span></span>  
  
    |<span data-ttu-id="1e8e5-193">Intestazione della colonna</span><span class="sxs-lookup"><span data-stu-id="1e8e5-193">Column head</span></span>|<span data-ttu-id="1e8e5-194">Valori</span><span class="sxs-lookup"><span data-stu-id="1e8e5-194">Values</span></span>|  
    |-----------------|------------|  
    |<span data-ttu-id="1e8e5-195">**Nome file originale**</span><span class="sxs-lookup"><span data-stu-id="1e8e5-195">**Original File Name**</span></span>|<span data-ttu-id="1e8e5-196">Percorso completo di un file di backup di origine.</span><span class="sxs-lookup"><span data-stu-id="1e8e5-196">The full path of a source backup file.</span></span>|  
    |<span data-ttu-id="1e8e5-197">**Tipo di file**</span><span class="sxs-lookup"><span data-stu-id="1e8e5-197">**File Type**</span></span>|<span data-ttu-id="1e8e5-198">Specifica il tipo di dati nel backup: **dati**, **registro** o **dati FILESTREAM**.</span><span class="sxs-lookup"><span data-stu-id="1e8e5-198">Specifies the type of data in the backup: **Data**, **Log**, or **Filestream Data**.</span></span> <span data-ttu-id="1e8e5-199">I dati contenuti nelle tabelle sono nei file **Dati** .</span><span class="sxs-lookup"><span data-stu-id="1e8e5-199">Data that is contained in tables is in **Data** files.</span></span> <span data-ttu-id="1e8e5-200">I dati del log delle transazioni sono nei file **Log** .</span><span class="sxs-lookup"><span data-stu-id="1e8e5-200">Transaction log data is in **Log** files.</span></span> <span data-ttu-id="1e8e5-201">I dati BLOB (Binary Large Object, oggetto binario di grandi dimensioni) archiviati nel file system si trovano nei file **Dati FILESTREAM** .</span><span class="sxs-lookup"><span data-stu-id="1e8e5-201">Binary large object (BLOB) data that is stored on the file system is in **Filestream Data** files.</span></span>|  
    |<span data-ttu-id="1e8e5-202">**Ripristina come**</span><span class="sxs-lookup"><span data-stu-id="1e8e5-202">**Restore As**</span></span>|<span data-ttu-id="1e8e5-203">Percorso completo del file di database da ripristinare.</span><span class="sxs-lookup"><span data-stu-id="1e8e5-203">The full path of the database file to be restored.</span></span> <span data-ttu-id="1e8e5-204">Per specificare un nuovo file di ripristino, fare clic nella casella di testo e modificare il percorso e il nome del file suggeriti.</span><span class="sxs-lookup"><span data-stu-id="1e8e5-204">To specify a new restore file, click the text box and edit the suggested path and file name.</span></span> <span data-ttu-id="1e8e5-205">La modifica del percorso o del nome file nella colonna **Ripristina come** equivale all'utilizzo dell'opzione MOVE in un'istruzione RESTORE [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1e8e5-205">Changing the path or file name in the **Restore As** column is equivalent to using the MOVE option in a [!INCLUDE[tsql](../../includes/tsql-md.md)] RESTORE statement.</span></span>|  
  
11. <span data-ttu-id="1e8e5-206">Il pannello **Stato di recupero** determina lo stato del database dopo l'operazione di ripristino.</span><span class="sxs-lookup"><span data-stu-id="1e8e5-206">The **Recovery state** panel determines the state of the database after the restore operation.</span></span>  
  
     <span data-ttu-id="1e8e5-207">**Lascia il database pronto per l'utilizzo eseguendo il rollback delle transazioni di cui non è stato eseguito il commit. I log delle transazioni aggiuntivi non possono essere ripristinati. (RESTORE WITH RECOVERY)**</span><span class="sxs-lookup"><span data-stu-id="1e8e5-207">**Leave the database ready for use by rolling back the uncommitted transactions. Additional transaction logs cannot be restored. (RESTORE WITH RECOVERY)**</span></span>  
     <span data-ttu-id="1e8e5-208">Esegue il recupero del database.</span><span class="sxs-lookup"><span data-stu-id="1e8e5-208">Recovers the database.</span></span> <span data-ttu-id="1e8e5-209">Questo è il comportamento predefinito.</span><span class="sxs-lookup"><span data-stu-id="1e8e5-209">This is the default behavior.</span></span> <span data-ttu-id="1e8e5-210">Selezionare questa opzione solo se si stanno ripristinando tutti i backup necessari.</span><span class="sxs-lookup"><span data-stu-id="1e8e5-210">Choose this option only if you are restoring all of the necessary backups now.</span></span> <span data-ttu-id="1e8e5-211">Questa opzione equivale all'opzione WITH RECOVERY in un'istruzione RESTORE [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1e8e5-211">This option is equivalent to specifying WITH RECOVERY in a [!INCLUDE[tsql](../../includes/tsql-md.md)] RESTORE statement.</span></span>  
  
     <span data-ttu-id="1e8e5-212">**Lascia il database non operativo e non eseguire il rollback delle transazioni di cui non è stato eseguito il commit. I log delle transazioni aggiuntivi possono essere ripristinati. (RESTORE WITH NORECOVERY)**</span><span class="sxs-lookup"><span data-stu-id="1e8e5-212">**Leave the database non-operational, and don't roll back the uncommitted transactions. Additional transaction logs can be restored. (RESTORE WITH NORECOVERY)**</span></span>  
     <span data-ttu-id="1e8e5-213">Il database viene lasciato nello stato di ripristino.</span><span class="sxs-lookup"><span data-stu-id="1e8e5-213">Leaves the database in the restoring state.</span></span> <span data-ttu-id="1e8e5-214">Per recuperare il database sarà necessario eseguire un altro ripristino utilizzando l'opzione RESTORE WITH RECOVERY descritta in precedenza.</span><span class="sxs-lookup"><span data-stu-id="1e8e5-214">To recover the database, you will need to perform another restore using the preceding RESTORE WITH RECOVERY option (see above).</span></span> <span data-ttu-id="1e8e5-215">Questa opzione equivale all'opzione WITH NORECOVERY in un'istruzione RESTORE [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1e8e5-215">This option is equivalent to specifying WITH NORECOVERY in a [!INCLUDE[tsql](../../includes/tsql-md.md)] RESTORE statement.</span></span>  
  
     <span data-ttu-id="1e8e5-216">Selezionando questa opzione, l'opzione **Mantieni le impostazioni di replica** non sarà disponibile.</span><span class="sxs-lookup"><span data-stu-id="1e8e5-216">If you select this option, the **Preserve replication settings** option is unavailable.</span></span>  
  
     <span data-ttu-id="1e8e5-217">**Lascia il database in modalità sola lettura. Esegui il rollback delle transazioni di cui non è stato eseguito il commit e salva l'operazione di rollback in un file in modo che gli effetti del recupero possano essere annullati. (RESTORE WITH STANDBY)**</span><span class="sxs-lookup"><span data-stu-id="1e8e5-217">**Leave the database in read-only mode. Roll back the uncommitted transactions, but save the rollback operation in a file so the recovery effects can be undone. (RESTORE WITH STANDBY)**</span></span>  
     <span data-ttu-id="1e8e5-218">Il database viene lasciato nello stato di standby.</span><span class="sxs-lookup"><span data-stu-id="1e8e5-218">Leaves the database in a standby state.</span></span> <span data-ttu-id="1e8e5-219">Questa opzione equivale all'opzione WITH STANDBY in un'istruzione RESTORE [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1e8e5-219">This option is equivalent to specifying WITH STANDBY in a [!INCLUDE[tsql](../../includes/tsql-md.md)] RESTORE statement.</span></span>  
  
     <span data-ttu-id="1e8e5-220">Se si seleziona questa opzione è necessario specificare un file standby.</span><span class="sxs-lookup"><span data-stu-id="1e8e5-220">Choosing this option requires that you specify a standby file.</span></span>  
  
     <span data-ttu-id="1e8e5-221">**File di rollback**</span><span class="sxs-lookup"><span data-stu-id="1e8e5-221">**Rollback undo file**</span></span>  
     <span data-ttu-id="1e8e5-222">Specificare un nome per il file standby nella casella di testo **File di rollback** .</span><span class="sxs-lookup"><span data-stu-id="1e8e5-222">Specify a standby file name in the **Rollback undo file** text box.</span></span> <span data-ttu-id="1e8e5-223">Questa opzione è necessaria se il database viene lasciato in modalità sola lettura (RESTORE WITH STANDBY).</span><span class="sxs-lookup"><span data-stu-id="1e8e5-223">This option is required if you leave the database in read-only mode (RESTORE WITH STANDBY).</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="1e8e5-224">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1e8e5-224">Using Transact-SQL</span></span>  
  
#### <a name="to-restore-files-and-filegroups"></a><span data-ttu-id="1e8e5-225">Per ripristinare file e filegroup</span><span class="sxs-lookup"><span data-stu-id="1e8e5-225">To restore files and filegroups</span></span>  
  
1.  <span data-ttu-id="1e8e5-226">Eseguire l'istruzione RESTORE DATABASE per ripristinare il backup di file e filegroup, specificando:</span><span class="sxs-lookup"><span data-stu-id="1e8e5-226">Execute the RESTORE DATABASE statement to restore the file and filegroup backup, specifying:</span></span>  
  
    -   <span data-ttu-id="1e8e5-227">Nome del database da ripristinare.</span><span class="sxs-lookup"><span data-stu-id="1e8e5-227">The name of the database to restore.</span></span>  
  
    -   <span data-ttu-id="1e8e5-228">Dispositivo di backup da cui verrà ripristinato il backup completo del database.</span><span class="sxs-lookup"><span data-stu-id="1e8e5-228">The backup device from where the full database backup will be restored.</span></span>  
  
    -   <span data-ttu-id="1e8e5-229">Clausola FILE per ogni file da ripristinare.</span><span class="sxs-lookup"><span data-stu-id="1e8e5-229">The FILE clause for each file to restore.</span></span>  
  
    -   <span data-ttu-id="1e8e5-230">Clausola FILEGROUP per ogni filegroup da ripristinare.</span><span class="sxs-lookup"><span data-stu-id="1e8e5-230">The FILEGROUP clause for each filegroup to restore.</span></span>  
  
    -   <span data-ttu-id="1e8e5-231">Clausola NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="1e8e5-231">The NORECOVERY clause.</span></span> <span data-ttu-id="1e8e5-232">Se i file non sono stati modificati dopo la creazione del backup, specificare la clausola RECOVERY.</span><span class="sxs-lookup"><span data-stu-id="1e8e5-232">If the files have not been modified after the backup was created, specify the RECOVERY clause.</span></span>  
  
2.  <span data-ttu-id="1e8e5-233">Se i file sono stati modificati dopo la creazione del backup, eseguire l'istruzione RESTORE LOG per applicare il backup del log delle transazioni, specificando:</span><span class="sxs-lookup"><span data-stu-id="1e8e5-233">If the files have been modified after the file backup was created, execute the RESTORE LOG statement to apply the transaction log backup, specifying:</span></span>  
  
    -   <span data-ttu-id="1e8e5-234">Nome del database a cui verrà applicato il log delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="1e8e5-234">The name of the database to which the transaction log will be applied.</span></span>  
  
    -   <span data-ttu-id="1e8e5-235">Dispositivo di backup da cui verrà ripristinato il backup del log delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="1e8e5-235">The backup device from where the transaction log backup will be restored.</span></span>  
  
    -   <span data-ttu-id="1e8e5-236">Clausola NORECOVERY se è disponibile un altro backup del log delle transazioni successivo a quello corrente. In caso contrario, specificare la clausola RECOVERY.</span><span class="sxs-lookup"><span data-stu-id="1e8e5-236">The NORECOVERY clause if you have another transaction log backup to apply after the current one; otherwise, specify the RECOVERY clause.</span></span>  
  
         <span data-ttu-id="1e8e5-237">Nei backup del log delle transazioni, se applicati, deve essere incluso il periodo di tempo intercorso dall'ultimo backup di file e filegroup fino alla fine del log, a meno che non vengano ripristinati TUTTI i file di database.</span><span class="sxs-lookup"><span data-stu-id="1e8e5-237">The transaction log backups, if applied, must cover the time when the files and filegroups were backed up until the end of log (unless ALL database files are restored).</span></span>  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="1e8e5-238">Esempio (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="1e8e5-238">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="1e8e5-239">In questo esempio vengono ripristinati i file e i filegroup per il database `MyDatabase` .</span><span class="sxs-lookup"><span data-stu-id="1e8e5-239">This example restores the files and filegroups for the `MyDatabase` database.</span></span> <span data-ttu-id="1e8e5-240">Per ripristinare il database all'ora corrente, verranno applicati due log delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="1e8e5-240">To restore the database to the current time, two transaction logs are applied.</span></span>  
  
```sql  
USE master;  
GO  
-- Restore the files and filesgroups for MyDatabase.  
RESTORE DATABASE MyDatabase  
   FILE = 'MyDatabase_data_1',  
   FILEGROUP = 'new_customers',  
   FILE = 'MyDatabase_data_2',  
   FILEGROUP = 'first_qtr_sales'  
   FROM MyDatabase_1  
   WITH NORECOVERY;  
GO  
-- Apply the first transaction log backup.  
RESTORE LOG MyDatabase  
   FROM MyDatabase_log1  
   WITH NORECOVERY;  
GO  
-- Apply the last transaction log backup.  
RESTORE LOG MyDatabase  
   FROM MyDatabase_log2  
   WITH RECOVERY;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="1e8e5-241">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1e8e5-241">See Also</span></span>  
 <span data-ttu-id="1e8e5-242">[Ripristinare un backup del database &#40;SQL Server Management Studio&#41;](restore-a-database-backup-using-ssms.md) </span><span class="sxs-lookup"><span data-stu-id="1e8e5-242">[Restore a Database Backup &#40;SQL Server Management Studio&#41;](restore-a-database-backup-using-ssms.md) </span></span>  
 <span data-ttu-id="1e8e5-243">[Backup di file e filegroup &#40;SQL Server&#41;](back-up-files-and-filegroups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="1e8e5-243">[Back Up Files and Filegroups &#40;SQL Server&#41;](back-up-files-and-filegroups-sql-server.md) </span></span>  
 <span data-ttu-id="1e8e5-244">[Creare un backup completo del database &#40;SQL Server&#41;](create-a-full-database-backup-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="1e8e5-244">[Create a Full Database Backup &#40;SQL Server&#41;](create-a-full-database-backup-sql-server.md) </span></span>  
 <span data-ttu-id="1e8e5-245">[Backup di un log delle transazioni &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="1e8e5-245">[Back Up a Transaction Log &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md) </span></span>  
 <span data-ttu-id="1e8e5-246">[Ripristinare un backup del log delle transazioni &#40;SQL Server&#41;](restore-a-transaction-log-backup-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="1e8e5-246">[Restore a Transaction Log Backup &#40;SQL Server&#41;](restore-a-transaction-log-backup-sql-server.md) </span></span>  
 [<span data-ttu-id="1e8e5-247">RESTORE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1e8e5-247">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  
  
