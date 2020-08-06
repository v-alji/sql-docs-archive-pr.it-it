---
title: Ripristinare i file in una nuova posizione (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- restoring files [SQL Server], how-to topics
- restoring databases [SQL Server], moving
- restoring files [SQL Server], steps
- file restores [SQL Server], how-to topics
- filegroups [SQL Server], restoring
- restoring filegroups [SQL Server]
ms.assetid: b4f4791d-646e-4632-9980-baae9cb1aade
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2a8336e5d186fb72df4e0a17fdd9affccab4ee57
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715419"
---
# <a name="restore-files-to-a-new-location-sql-server"></a><span data-ttu-id="4e26b-102">Ripristino dei file in una nuova posizione (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="4e26b-102">Restore Files to a New Location (SQL Server)</span></span>
  <span data-ttu-id="4e26b-103">In questo argomento viene descritto come ripristinare i file in un nuovo percorso in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4e26b-103">This topic describes how to restore files to a new location in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="4e26b-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="4e26b-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="4e26b-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="4e26b-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="4e26b-106">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="4e26b-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="4e26b-107">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="4e26b-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="4e26b-108">**Per ripristinare i file in una nuova posizione utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="4e26b-108">**To restore files to a new location, using:**</span></span>  
  
     [<span data-ttu-id="4e26b-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4e26b-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="4e26b-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4e26b-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="4e26b-111">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="4e26b-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="4e26b-112">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="4e26b-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="4e26b-113">L'amministratore di sistema che esegue il ripristino dei file deve essere l'unico utente collegato al database da ripristinare.</span><span class="sxs-lookup"><span data-stu-id="4e26b-113">The system administrator restoring the files must be the only person currently using the database to be restored.</span></span>  
  
-   <span data-ttu-id="4e26b-114">Non è possibile utilizzare RESTORE in una transazione esplicita o implicita.</span><span class="sxs-lookup"><span data-stu-id="4e26b-114">RESTORE is not allowed in an explicit or implicit transaction.</span></span>  
  
-   <span data-ttu-id="4e26b-115">In base al modello di recupero con registrazione completa o con registrazione minima delle operazioni bulk, prima di poter ripristinare file è necessario eseguire il backup del log delle transazioni attivo, noto come parte finale del log.</span><span class="sxs-lookup"><span data-stu-id="4e26b-115">Under the full or bulk-logged recovery model, before you can restore files, you must back up the active transaction log (known as the tail of the log).</span></span> <span data-ttu-id="4e26b-116">Per altre informazioni, vedere [Backup di un log delle transazioni &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="4e26b-116">For more information, see [Back Up a Transaction Log &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md).</span></span>  
  
-   <span data-ttu-id="4e26b-117">Per ripristinare un database crittografato, è necessario poter accedere alla chiave asimmetrica o al certificato utilizzato per crittografare il database.</span><span class="sxs-lookup"><span data-stu-id="4e26b-117">To restore a database that is encrypted, you must have access to the certificate or asymmetric key that was used to encrypt the database.</span></span> <span data-ttu-id="4e26b-118">Non è possibile effettuare l'operazione di ripristino del database senza almeno uno di questi due elementi.</span><span class="sxs-lookup"><span data-stu-id="4e26b-118">Without the certificate or asymmetric key, the database cannot be restored.</span></span> <span data-ttu-id="4e26b-119">Di conseguenza, il certificato utilizzato per crittografare la chiave di crittografia del database deve essere conservato fino a quando il backup è necessario.</span><span class="sxs-lookup"><span data-stu-id="4e26b-119">As a result, the certificate that is used to encrypt the database encryption key must be retained as long as the backup is needed.</span></span> <span data-ttu-id="4e26b-120">Per altre informazioni, vedere [SQL Server Certificates and Asymmetric Keys](../security/sql-server-certificates-and-asymmetric-keys.md).</span><span class="sxs-lookup"><span data-stu-id="4e26b-120">For more information, see [SQL Server Certificates and Asymmetric Keys](../security/sql-server-certificates-and-asymmetric-keys.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="4e26b-121">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="4e26b-121">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="4e26b-122">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="4e26b-122">Permissions</span></span>  
 <span data-ttu-id="4e26b-123">Se il database da ripristinare non esiste, per eseguire un'operazione RESTORE l'utente deve disporre delle autorizzazioni CREATE DATABASE.</span><span class="sxs-lookup"><span data-stu-id="4e26b-123">If the database being restored does not exist, the user must have CREATE DATABASE permissions to be able to execute RESTORE.</span></span> <span data-ttu-id="4e26b-124">Se il database esiste, le autorizzazioni per l'istruzione RESTORE vengono assegnate per impostazione predefinita ai membri dei ruoli predefiniti del server **sysadmin** e **dbcreator** e al proprietario (**dbo**) del database. Per l'opzione FROM DATABASE_SNAPSHOT, il database esiste sempre.</span><span class="sxs-lookup"><span data-stu-id="4e26b-124">If the database exists, RESTORE permissions default to members of the **sysadmin** and **dbcreator** fixed server roles and the owner (**dbo**) of the database (for the FROM DATABASE_SNAPSHOT option, the database always exists).</span></span>  
  
 <span data-ttu-id="4e26b-125">Le autorizzazioni per l'istruzione RESTORE vengono assegnate ai ruoli in cui le informazioni sull'appartenenza sono sempre disponibili per il server.</span><span class="sxs-lookup"><span data-stu-id="4e26b-125">RESTORE permissions are given to roles in which membership information is always readily available to the server.</span></span> <span data-ttu-id="4e26b-126">Poiché è possibile controllare l'appartenenza ai ruoli predefiniti del database solo quando il database è accessibile e non è danneggiato, condizioni che non risultano sempre vere quando si esegue un'operazione RESTORE, i membri del ruolo predefinito del database **db_owner** non dispongono delle autorizzazioni per l'istruzione RESTORE.</span><span class="sxs-lookup"><span data-stu-id="4e26b-126">Because fixed database role membership can be checked only when the database is accessible and undamaged, which is not always the case when RESTORE is executed, members of the **db_owner** fixed database role do not have RESTORE permissions.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="4e26b-127">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4e26b-127">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-restore-files-to-a-new-location"></a><span data-ttu-id="4e26b-128">Per ripristinare i file in una nuova posizione</span><span class="sxs-lookup"><span data-stu-id="4e26b-128">To restore files to a new location</span></span>  
  
1.  <span data-ttu-id="4e26b-129">In **Esplora oggetti**connettersi a un'istanza di [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], espandere tale istanza, quindi espandere **Database**.</span><span class="sxs-lookup"><span data-stu-id="4e26b-129">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], expand that instance, and then expand **Databases**.</span></span>  
  
2.  <span data-ttu-id="4e26b-130">Fare clic con il pulsante destro del mouse sul database specifico, scegliere **Attività**e scegliere **Ripristina**e fare clic su **File e filegroup**.</span><span class="sxs-lookup"><span data-stu-id="4e26b-130">Right-click the database that you want, point to **Tasks**, point to **Restore**, and then click **Files and Filegroups**.</span></span>  
  
3.  <span data-ttu-id="4e26b-131">Nella pagina **Generale** nella casella di riepilogo **Database di destinazione** , immettere il database da ripristinare.</span><span class="sxs-lookup"><span data-stu-id="4e26b-131">On the **General** page, in the **To database** list box, enter the database to restore.</span></span> <span data-ttu-id="4e26b-132">È possibile immettere un nuovo database oppure sceglierne uno esistente dall'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="4e26b-132">You can enter a new database or choose an existing database from the drop-down list.</span></span> <span data-ttu-id="4e26b-133">Nell'elenco sono inclusi tutti i database presenti nel server, ad eccezione dei database di sistema **master** e **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="4e26b-133">The list includes all databases on the server, excluding the system databases **master** and **tempdb**.</span></span>  
  
4.  <span data-ttu-id="4e26b-134">Per specificare l'origine e il percorso dei set di backup da ripristinare, fare clic su una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4e26b-134">To specify the source and location of the backup sets to restore, click one of the following options:</span></span>  
  
    -   <span data-ttu-id="4e26b-135">**Database di origine**</span><span class="sxs-lookup"><span data-stu-id="4e26b-135">**From database**</span></span>  
  
         <span data-ttu-id="4e26b-136">Immettere il nome di un database nella casella di riepilogo.</span><span class="sxs-lookup"><span data-stu-id="4e26b-136">Enter a database name in the list box.</span></span> <span data-ttu-id="4e26b-137">Nell'elenco sono inclusi solo i database di cui è stato eseguito il backup in base alla cronologia di backup di **msdb** .</span><span class="sxs-lookup"><span data-stu-id="4e26b-137">This list contains only databases that have been backed up according to the **msdb** backup history.</span></span>  
  
    -   <span data-ttu-id="4e26b-138">**Dispositivo di origine**</span><span class="sxs-lookup"><span data-stu-id="4e26b-138">**From device**</span></span>  
  
         <span data-ttu-id="4e26b-139">Fare clic sul pulsante Sfoglia</span><span class="sxs-lookup"><span data-stu-id="4e26b-139">Click the browse button.</span></span> <span data-ttu-id="4e26b-140">Nella finestra di dialogo **Seleziona dispositivi di backup** selezionare uno dei tipi di dispositivo elencati nella casella di riepilogo **Tipo di supporti di backup** .</span><span class="sxs-lookup"><span data-stu-id="4e26b-140">In the **Specify backup devices** dialog box, select one of the listed device types in the **Backup media type** list box.</span></span> <span data-ttu-id="4e26b-141">Per selezionare uno o più dispositivi per la casella di riepilogo **Supporti di backup** , fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="4e26b-141">To select one or more devices for the **Backup media** list box, click **Add**.</span></span>  
  
         <span data-ttu-id="4e26b-142">Dopo avere aggiunto i dispositivi desiderati nella casella di riepilogo **Dispositivi di backup** , fare clic su **OK** per tornare alla pagina **Generale** .</span><span class="sxs-lookup"><span data-stu-id="4e26b-142">After you add the devices you want to the **Backup media** list box, click **OK** to return to the **General** page.</span></span>  
  
5.  <span data-ttu-id="4e26b-143">Nella griglia **Selezionare i set di backup da ripristinare** selezionare i set di backup che si desidera ripristinare.</span><span class="sxs-lookup"><span data-stu-id="4e26b-143">In the **Select the backup sets to restore** grid, select the backups to restore.</span></span> <span data-ttu-id="4e26b-144">In questa griglia vengono visualizzati i backup disponibili per il percorso specificato.</span><span class="sxs-lookup"><span data-stu-id="4e26b-144">This grid displays the backups available for the specified location.</span></span> <span data-ttu-id="4e26b-145">Per impostazione predefinita, viene suggerito un piano di recupero.</span><span class="sxs-lookup"><span data-stu-id="4e26b-145">By default, a recovery plan is suggested.</span></span> <span data-ttu-id="4e26b-146">Per ignorare il piano di recupero suggerito, è possibile modificare le impostazioni selezionate nella griglia.</span><span class="sxs-lookup"><span data-stu-id="4e26b-146">To override the suggested recovery plan, you can change the selections in the grid.</span></span> <span data-ttu-id="4e26b-147">I backup che dipendono da un backup deselezionato vengono automaticamente deselezionati.</span><span class="sxs-lookup"><span data-stu-id="4e26b-147">Any backups that depend on a deselected backup are deselected automatically.</span></span>  
  
    |<span data-ttu-id="4e26b-148">Intestazione della colonna</span><span class="sxs-lookup"><span data-stu-id="4e26b-148">Column head</span></span>|<span data-ttu-id="4e26b-149">Valori</span><span class="sxs-lookup"><span data-stu-id="4e26b-149">Values</span></span>|  
    |-----------------|------------|  
    |<span data-ttu-id="4e26b-150">**Restore**</span><span class="sxs-lookup"><span data-stu-id="4e26b-150">**Restore**</span></span>|<span data-ttu-id="4e26b-151">Le caselle di controllo selezionate indicano i set di backup da ripristinare.</span><span class="sxs-lookup"><span data-stu-id="4e26b-151">The selected check boxes indicate the backup sets to be restored.</span></span>|  
    |<span data-ttu-id="4e26b-152">**Nome**</span><span class="sxs-lookup"><span data-stu-id="4e26b-152">**Name**</span></span>|<span data-ttu-id="4e26b-153">Nome del set di backup.</span><span class="sxs-lookup"><span data-stu-id="4e26b-153">The name of the backup set.</span></span>|  
    |<span data-ttu-id="4e26b-154">**Tipo di file**</span><span class="sxs-lookup"><span data-stu-id="4e26b-154">**File Type**</span></span>|<span data-ttu-id="4e26b-155">Specifica il tipo di dati nel backup: **dati**, **registro** o **dati FILESTREAM**.</span><span class="sxs-lookup"><span data-stu-id="4e26b-155">Specifies the type of data in the backup: **Data**, **Log**, or **Filestream Data**.</span></span> <span data-ttu-id="4e26b-156">I dati contenuti nelle tabelle sono nei file **Dati** .</span><span class="sxs-lookup"><span data-stu-id="4e26b-156">Data that is contained in tables is in **Data** files.</span></span> <span data-ttu-id="4e26b-157">I dati del log delle transazioni sono nei file **Log** .</span><span class="sxs-lookup"><span data-stu-id="4e26b-157">Transaction log data is in **Log** files.</span></span> <span data-ttu-id="4e26b-158">I dati BLOB (Binary Large Object, oggetto binario di grandi dimensioni) archiviati nel file system si trovano nei file **Dati FILESTREAM** .</span><span class="sxs-lookup"><span data-stu-id="4e26b-158">Binary large object (BLOB) data that is stored on the file system is in **Filestream Data** files.</span></span>|  
    |<span data-ttu-id="4e26b-159">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="4e26b-159">**Type**</span></span>|<span data-ttu-id="4e26b-160">Tipo di operazione di backup eseguita: **Completo**, **Differenziale** o **Log delle transazioni**.</span><span class="sxs-lookup"><span data-stu-id="4e26b-160">The type of backup performed: **Full**, **Differential**, or **Transaction Log**.</span></span>|  
    |<span data-ttu-id="4e26b-161">**Server**</span><span class="sxs-lookup"><span data-stu-id="4e26b-161">**Server**</span></span>|<span data-ttu-id="4e26b-162">Nome dell'istanza del Motore di database che ha eseguito l'operazione di backup.</span><span class="sxs-lookup"><span data-stu-id="4e26b-162">The name of the Database-Engine instance that performed the backup operation.</span></span>|  
    |<span data-ttu-id="4e26b-163">**Nome file logico**</span><span class="sxs-lookup"><span data-stu-id="4e26b-163">**File Logical Name**</span></span>|<span data-ttu-id="4e26b-164">Nome logico del file.</span><span class="sxs-lookup"><span data-stu-id="4e26b-164">The logical name of the file.</span></span>|  
    |<span data-ttu-id="4e26b-165">**Database**</span><span class="sxs-lookup"><span data-stu-id="4e26b-165">**Database**</span></span>|<span data-ttu-id="4e26b-166">Nome del database interessato dall'operazione di backup.</span><span class="sxs-lookup"><span data-stu-id="4e26b-166">The name of the database involved in the backup operation.</span></span>|  
    |<span data-ttu-id="4e26b-167">**Data inizio**</span><span class="sxs-lookup"><span data-stu-id="4e26b-167">**Start Date**</span></span>|<span data-ttu-id="4e26b-168">Data e ora di inizio dell'operazione di backup, visualizzate in base alle impostazioni internazionali del client.</span><span class="sxs-lookup"><span data-stu-id="4e26b-168">The date and time when the backup operation began, presented in the regional setting of the client.</span></span>|  
    |<span data-ttu-id="4e26b-169">**Data fine**</span><span class="sxs-lookup"><span data-stu-id="4e26b-169">**Finish Date**</span></span>|<span data-ttu-id="4e26b-170">Data e ora di fine dell'operazione di backup, visualizzate in base alle impostazioni internazionali del client.</span><span class="sxs-lookup"><span data-stu-id="4e26b-170">The date and time when the backup operation finished, presented in the regional setting of the client.</span></span>|  
    |<span data-ttu-id="4e26b-171">**Dimensione**</span><span class="sxs-lookup"><span data-stu-id="4e26b-171">**Size**</span></span>|<span data-ttu-id="4e26b-172">Dimensioni in byte del set di backup.</span><span class="sxs-lookup"><span data-stu-id="4e26b-172">The size of the backup set in bytes.</span></span>|  
    |<span data-ttu-id="4e26b-173">**Nome utente**</span><span class="sxs-lookup"><span data-stu-id="4e26b-173">**User Name**</span></span>|<span data-ttu-id="4e26b-174">Nome dell'utente che ha eseguito l'operazione di backup.</span><span class="sxs-lookup"><span data-stu-id="4e26b-174">The name of the user who performed the backup operation.</span></span>|  
  
6.  <span data-ttu-id="4e26b-175">Nel riquadro **Selezione pagina** fare clic sulla pagina **Opzioni** .</span><span class="sxs-lookup"><span data-stu-id="4e26b-175">In the **Select a page** pane, click the **Options** page.</span></span>  
  
7.  <span data-ttu-id="4e26b-176">Nella griglia **Ripristina file di database come** , specificare un nuovo percorso per il file o i file da spostare.</span><span class="sxs-lookup"><span data-stu-id="4e26b-176">In the **Restore database files as** grid, specify a new location for the file or files that you want to move.</span></span>  
  
    |<span data-ttu-id="4e26b-177">Intestazione della colonna</span><span class="sxs-lookup"><span data-stu-id="4e26b-177">Column head</span></span>|<span data-ttu-id="4e26b-178">Valori</span><span class="sxs-lookup"><span data-stu-id="4e26b-178">Values</span></span>|  
    |-----------------|------------|  
    |<span data-ttu-id="4e26b-179">**Nome file originale**</span><span class="sxs-lookup"><span data-stu-id="4e26b-179">**Original File Name**</span></span>|<span data-ttu-id="4e26b-180">Percorso completo di un file di backup di origine.</span><span class="sxs-lookup"><span data-stu-id="4e26b-180">The full path of a source backup file.</span></span>|  
    |<span data-ttu-id="4e26b-181">**Tipo di file**</span><span class="sxs-lookup"><span data-stu-id="4e26b-181">**File Type**</span></span>|<span data-ttu-id="4e26b-182">Specifica il tipo di dati nel backup: **dati**, **registro** o **dati FILESTREAM**.</span><span class="sxs-lookup"><span data-stu-id="4e26b-182">Specifies the type of data in the backup: **Data**, **Log**, or **Filestream Data**.</span></span> <span data-ttu-id="4e26b-183">I dati contenuti nelle tabelle sono nei file **Dati** .</span><span class="sxs-lookup"><span data-stu-id="4e26b-183">Data that is contained in tables is in **Data** files.</span></span> <span data-ttu-id="4e26b-184">I dati del log delle transazioni sono nei file **Log** .</span><span class="sxs-lookup"><span data-stu-id="4e26b-184">Transaction log data is in **Log** files.</span></span> <span data-ttu-id="4e26b-185">I dati BLOB (Binary Large Object, oggetto binario di grandi dimensioni) archiviati nel file system si trovano nei file **Dati FILESTREAM** .</span><span class="sxs-lookup"><span data-stu-id="4e26b-185">Binary large object (BLOB) data that is stored on the file system is in **Filestream Data** files.</span></span>|  
    |<span data-ttu-id="4e26b-186">**Ripristina come**</span><span class="sxs-lookup"><span data-stu-id="4e26b-186">**Restore As**</span></span>|<span data-ttu-id="4e26b-187">Percorso completo del file di database da ripristinare.</span><span class="sxs-lookup"><span data-stu-id="4e26b-187">The full path of the database file to be restored.</span></span> <span data-ttu-id="4e26b-188">Per specificare un nuovo file di ripristino, fare clic nella casella di testo e modificare il percorso e il nome del file suggeriti.</span><span class="sxs-lookup"><span data-stu-id="4e26b-188">To specify a new restore file, click the text box and edit the suggested path and file name.</span></span> <span data-ttu-id="4e26b-189">La modifica del percorso o del nome file nella colonna **Ripristina come** equivale all'utilizzo dell'opzione MOVE in un'istruzione RESTORE [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4e26b-189">Changing the path or file name in the **Restore As** column is equivalent to using the MOVE option in a [!INCLUDE[tsql](../../includes/tsql-md.md)] RESTORE statement.</span></span>|  
  
8.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="4e26b-190">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4e26b-190">Using Transact-SQL</span></span>  
  
#### <a name="to-restore-files-to-a-new-location"></a><span data-ttu-id="4e26b-191">Per ripristinare i file in una nuova posizione</span><span class="sxs-lookup"><span data-stu-id="4e26b-191">To restore files to a new location</span></span>  
  
1.  <span data-ttu-id="4e26b-192">Eseguire facoltativamente l'istruzione RESTORE FILELISTONLY per stabilire il numero e i nomi dei file nel backup completo del database.</span><span class="sxs-lookup"><span data-stu-id="4e26b-192">Optionally, execute the RESTORE FILELISTONLY statement to determine the number and names of the files in the full database backup.</span></span>  
  
2.  <span data-ttu-id="4e26b-193">Eseguire l'istruzione RESTORE DATABASE per ripristinare il backup completo del database, specificando:</span><span class="sxs-lookup"><span data-stu-id="4e26b-193">Execute the RESTORE DATABASE statement to restore the full database backup, specifying:</span></span>  
  
    -   <span data-ttu-id="4e26b-194">Nome del database da ripristinare.</span><span class="sxs-lookup"><span data-stu-id="4e26b-194">The name of the database to restore.</span></span>  
  
    -   <span data-ttu-id="4e26b-195">Dispositivo di backup da cui verrà ripristinato il backup completo del database.</span><span class="sxs-lookup"><span data-stu-id="4e26b-195">The backup device from where the full database backup will be restored.</span></span>  
  
    -   <span data-ttu-id="4e26b-196">Clausola MOVE per ogni file da ripristinare in una nuova posizione.</span><span class="sxs-lookup"><span data-stu-id="4e26b-196">The MOVE clause for each file to restore to a new location.</span></span>  
  
    -   <span data-ttu-id="4e26b-197">Clausola NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="4e26b-197">The NORECOVERY clause.</span></span>  
  
3.  <span data-ttu-id="4e26b-198">Se i file sono stati modificati dopo la creazione del backup, eseguire l'istruzione RESTORE LOG per applicare il backup del log delle transazioni, specificando:</span><span class="sxs-lookup"><span data-stu-id="4e26b-198">If the files have been modified after the file backup was created, execute the RESTORE LOG statement to apply the transaction log backup, specifying:</span></span>  
  
    -   <span data-ttu-id="4e26b-199">Nome del database a cui verrà applicato il log delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="4e26b-199">The name of the database to which the transaction log will be applied.</span></span>  
  
    -   <span data-ttu-id="4e26b-200">Dispositivo di backup da cui verrà ripristinato il backup del log delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="4e26b-200">The backup device from where the transaction log backup will be restored.</span></span>  
  
    -   <span data-ttu-id="4e26b-201">Clausola NORECOVERY se è disponibile un altro backup del log delle transazioni successivo a quello corrente. In caso contrario, specificare la clausola RECOVERY.</span><span class="sxs-lookup"><span data-stu-id="4e26b-201">The NORECOVERY clause if you have another transaction log backup to apply after the current one; otherwise, specify the RECOVERY clause.</span></span>  
  
         <span data-ttu-id="4e26b-202">I backup dei log delle transazioni, se utilizzati, devono coprire il periodo intercorso dall'ultimo backup dei file e dei filegroup.</span><span class="sxs-lookup"><span data-stu-id="4e26b-202">The transaction log backups, if applied, must cover the time when the files and filegroups were backed up.</span></span>  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="4e26b-203">Esempio (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="4e26b-203">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="4e26b-204">Questo esempio illustra come ripristinare in nuove posizioni nell'unità D due file del database `MyNwind` originariamente memorizzati nell'unità C. Verranno anche applicati due log delle transazioni per ripristinare il database all'ora corrente.</span><span class="sxs-lookup"><span data-stu-id="4e26b-204">This example restores two of the files for the `MyNwind` database that were originally located on Drive C to new locations on Drive D. Two transaction logs will also be applied to restore the database to the current time.</span></span> <span data-ttu-id="4e26b-205">L'istruzione `RESTORE FILELISTONLY` viene utilizzata per determinare il numero e i nomi logici e fisici dei file del database da ripristinare.</span><span class="sxs-lookup"><span data-stu-id="4e26b-205">The `RESTORE FILELISTONLY` statement is used to determine the number and logical and physical names of the files in the database being restored.</span></span>  
  
```sql  
USE master;  
GO  
-- First determine the number and names of the files in the backup.  
RESTORE FILELISTONLY  
   FROM MyNwind_1;  
-- Restore the files for MyNwind.  
RESTORE DATABASE MyNwind  
   FROM MyNwind_1  
   WITH NORECOVERY,  
   MOVE 'MyNwind_data_1' TO 'D:\MyData\MyNwind_data_1.mdf',   
   MOVE 'MyNwind_data_2' TO 'D:\MyData\MyNwind_data_2.ndf';  
GO  
-- Apply the first transaction log backup.  
RESTORE LOG MyNwind  
   FROM MyNwind_log1  
   WITH NORECOVERY;  
GO  
-- Apply the last transaction log backup.  
RESTORE LOG MyNwind  
   FROM MyNwind_log2  
   WITH RECOVERY;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="4e26b-206">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4e26b-206">See Also</span></span>  
 <span data-ttu-id="4e26b-207">[Ripristinare un backup del database &#40;SQL Server Management Studio&#41;](restore-a-database-backup-using-ssms.md) </span><span class="sxs-lookup"><span data-stu-id="4e26b-207">[Restore a Database Backup &#40;SQL Server Management Studio&#41;](restore-a-database-backup-using-ssms.md) </span></span>  
 <span data-ttu-id="4e26b-208">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4e26b-208">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 <span data-ttu-id="4e26b-209">[Copiare database tramite backup e ripristino](../databases/copy-databases-with-backup-and-restore.md) </span><span class="sxs-lookup"><span data-stu-id="4e26b-209">[Copy Databases with Backup and Restore](../databases/copy-databases-with-backup-and-restore.md) </span></span>  
 [<span data-ttu-id="4e26b-210">Ripristino di file e filegroup &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4e26b-210">Restore Files and Filegroups &#40;SQL Server&#41;</span></span>](restore-files-and-filegroups-sql-server.md)  
  
  
