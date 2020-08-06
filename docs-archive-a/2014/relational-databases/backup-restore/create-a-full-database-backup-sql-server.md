---
title: Creare un backup completo del database (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- backing up databases [SQL Server], full backups
- backing up databases [SQL Server], SQL Server Management Studio
- backups [SQL Server], creating
- database backups [SQL Server], SQL Server Management Studio
ms.assetid: 586561fc-dfbb-4842-84f8-204a9100a534
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f406464680a1669133dc87bdfb231c644d33fbdb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724776"
---
# <a name="create-a-full-database-backup-sql-server"></a><span data-ttu-id="9a0f9-102">Creazione di un backup completo del database (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="9a0f9-102">Create a Full Database Backup (SQL Server)</span></span>
  <span data-ttu-id="9a0f9-103">In questo argomento viene descritto come creare un backup completo del database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)]o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9a0f9-103">This topic describes how to create a full database backup in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or PowerShell.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9a0f9-104">Per informazioni sul backup di SQL Server nel servizio di archiviazione BLOB di Azure, vedere [SQL Server backup e ripristino con il servizio di archiviazione BLOB di Azure](sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md).</span><span class="sxs-lookup"><span data-stu-id="9a0f9-104">For information on SQL Server backup to the Azure Blob storage service, see, [SQL Server Backup and Restore with Azure Blob Storage Service](sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md).</span></span>  
  
 <span data-ttu-id="9a0f9-105">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="9a0f9-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="9a0f9-106">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="9a0f9-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="9a0f9-107">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="9a0f9-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="9a0f9-108">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="9a0f9-108">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="9a0f9-109">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="9a0f9-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="9a0f9-110">**Per creare un backup completo del database utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="9a0f9-110">**To create a full database backup, using:**</span></span>  
  
     [<span data-ttu-id="9a0f9-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9a0f9-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="9a0f9-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9a0f9-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="9a0f9-113">PowerShell</span><span class="sxs-lookup"><span data-stu-id="9a0f9-113">PowerShell</span></span>](#PowerShellProcedure)  
  
-   [<span data-ttu-id="9a0f9-114">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="9a0f9-114">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="9a0f9-115">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="9a0f9-115">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="9a0f9-116">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="9a0f9-116">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="9a0f9-117">Non è possibile utilizzare l'istruzione BACKUP in una transazione esplicita o implicita.</span><span class="sxs-lookup"><span data-stu-id="9a0f9-117">The BACKUP statement is not allowed in an explicit or implicit transaction.</span></span>  
  
-   <span data-ttu-id="9a0f9-118">I backup creati nella versione più recente di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] non possono essere ripristinati nelle versioni precedenti di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9a0f9-118">Backups that are created by more recent version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cannot be restored in earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="9a0f9-119">Per altre informazioni, vedere [Panoramica del backup &#40;SQL Server&#41;](backup-overview-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="9a0f9-119">For more information, see [Backup Overview &#40;SQL Server&#41;](backup-overview-sql-server.md).</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="9a0f9-120">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="9a0f9-120">Recommendations</span></span>  
  
-   <span data-ttu-id="9a0f9-121">Poiché le dimensioni del database aumentano, i backup completi del database richiedono più tempo e più spazio di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="9a0f9-121">As a database increases in size full database backups take more time to finish and require more storage space.</span></span> <span data-ttu-id="9a0f9-122">Per un database di grandi dimensioni può pertanto essere utile integrare un backup completo del database con una serie di *backup database differenziali*.</span><span class="sxs-lookup"><span data-stu-id="9a0f9-122">Therefore, for a large database, you might want to supplement a full database backup with a series of *differential database backups*.</span></span> <span data-ttu-id="9a0f9-123">Per altre informazioni, vedere [Backup differenziali &#40;SQL Server&#41;](differential-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="9a0f9-123">For more information, see [Differential Backups &#40;SQL Server&#41;](differential-backups-sql-server.md).</span></span>  
  
-   <span data-ttu-id="9a0f9-124">È possibile stimare la dimensione di un backup del database completo tramite la stored procedure di sistema [sp_spaceused](/sql/relational-databases/system-stored-procedures/sp-spaceused-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="9a0f9-124">You can estimate the size of a full database backup by using the [sp_spaceused](/sql/relational-databases/system-stored-procedures/sp-spaceused-transact-sql) system stored procedure.</span></span>  
  
-   <span data-ttu-id="9a0f9-125">Per impostazione predefinita, per ogni operazione di backup eseguita in modo corretto viene aggiunta una voce al log degli errori di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e al registro eventi di sistema.</span><span class="sxs-lookup"><span data-stu-id="9a0f9-125">By default, every successful backup operation adds an entry in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log and in the system event log.</span></span> <span data-ttu-id="9a0f9-126">Se il backup del log viene eseguito di frequente, questi messaggi possono aumentare rapidamente, provocando la creazione di log degli errori di dimensioni elevate e rendendo difficile l'individuazione di altri messaggi.</span><span class="sxs-lookup"><span data-stu-id="9a0f9-126">If back up the log very frequently, these success messages accumulate quickly, resulting in huge error logs that can make finding other messages difficult.</span></span> <span data-ttu-id="9a0f9-127">In questi casi è possibile eliminare tali voci di log utilizzando il flag di traccia 3226 se nessuno degli script dipende da esse.</span><span class="sxs-lookup"><span data-stu-id="9a0f9-127">In such cases you can suppress these log entries by using trace flag 3226 if none of your scripts depend on those entries.</span></span> <span data-ttu-id="9a0f9-128">Per altre informazioni, vedere [Flag di traccia &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-traceon-trace-flags-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9a0f9-128">For more information, see [Trace Flags &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-traceon-trace-flags-transact-sql).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="9a0f9-129">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="9a0f9-129">Security</span></span>  
 <span data-ttu-id="9a0f9-130">TRUSTWORTHY è impostato su OFF in un backup del database.</span><span class="sxs-lookup"><span data-stu-id="9a0f9-130">TRUSTWORTHY is set to OFF on a database backup.</span></span> <span data-ttu-id="9a0f9-131">Per informazioni su come impostare TRUSTWORTHY su ON, vedere [Opzioni ALTER DATABASE SET &#40; Transact-SQL &#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span><span class="sxs-lookup"><span data-stu-id="9a0f9-131">For information about how to set TRUSTWORTHY to ON, see [ALTER DATABASE SET Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span></span>  
  
 <span data-ttu-id="9a0f9-132">A partire da [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], le opzioni `PASSWORD` e `MEDIAPASSWORD` non sono più disponibili per la creazione di backup.</span><span class="sxs-lookup"><span data-stu-id="9a0f9-132">Beginning with [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] the `PASSWORD` and `MEDIAPASSWORD` options are discontinued for creating backups.</span></span> <span data-ttu-id="9a0f9-133">È possibile ripristinare backup creati con password.</span><span class="sxs-lookup"><span data-stu-id="9a0f9-133">You can still restore backups created with passwords.</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="9a0f9-134">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="9a0f9-134">Permissions</span></span>  
 <span data-ttu-id="9a0f9-135">Le autorizzazioni BACKUP DATABASE e BACKUP LOG vengono assegnate per impostazione predefinita ai membri del ruolo predefinito del server **sysadmin** e dei ruoli predefiniti del database **db_owner** e **db_backupoperator** .</span><span class="sxs-lookup"><span data-stu-id="9a0f9-135">BACKUP DATABASE and BACKUP LOG permissions default to members of the **sysadmin** fixed server role and the **db_owner** and **db_backupoperator** fixed database roles.</span></span>  
  
 <span data-ttu-id="9a0f9-136">Eventuali problemi correlati alla proprietà e alle autorizzazioni sul file fisico del dispositivo di backup possono interferire con l'operazione di backup.</span><span class="sxs-lookup"><span data-stu-id="9a0f9-136">Ownership and permission problems on the backup device's physical file can interfere with a backup operation.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="9a0f9-137">sia possibile leggere e scrivere sul dispositivo e che l'account utilizzato per eseguire il servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] disponga delle autorizzazioni di scrittura.</span><span class="sxs-lookup"><span data-stu-id="9a0f9-137">must be able to read and write to the device; the account under which the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service runs must have write permissions.</span></span> <span data-ttu-id="9a0f9-138">Le autorizzazioni di accesso ai file, tuttavia, non vengono controllate dalla stored procedure [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql)che aggiunge una voce per un dispositivo di backup nelle tabelle di sistema.</span><span class="sxs-lookup"><span data-stu-id="9a0f9-138">However, [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql), which adds an entry for a backup device in the system tables, does not check file access permissions.</span></span> <span data-ttu-id="9a0f9-139">Di conseguenza, i problemi relativi all'accesso e alla proprietà del file fisico del dispositivo di backup potrebbero emergere solo in fase di accesso alla risorsa fisica durante un tentativo di backup o ripristino.</span><span class="sxs-lookup"><span data-stu-id="9a0f9-139">Such problems on the backup device's physical file may not appear until the physical resource is accessed when the backup or restore is attempted.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="9a0f9-140">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9a0f9-140">Using SQL Server Management Studio</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9a0f9-141"> Quando si specifica un'attività di backup utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], è possibile generare lo script [!INCLUDE[tsql](../../includes/tsql-md.md)] [BACKUP](/sql/t-sql/statements/backup-transact-sql) corrispondente facendo clic sul pulsante **Script** e selezionando una destinazione per lo script.</span><span class="sxs-lookup"><span data-stu-id="9a0f9-141">When you specify a back up task by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], you can generate the corresponding [!INCLUDE[tsql](../../includes/tsql-md.md)] [BACKUP](/sql/t-sql/statements/backup-transact-sql) script by clicking the **Script** button and selecting a script destination.</span></span>  
  
#### <a name="to-back-up-a-database"></a><span data-ttu-id="9a0f9-142">Per eseguire il backup di un database</span><span class="sxs-lookup"><span data-stu-id="9a0f9-142">To back up a database</span></span>  
  
1.  <span data-ttu-id="9a0f9-143">Dopo aver stabilito la connessione all'istanza appropriata del [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Esplora oggetti fare clic sul nome del server per espanderne l'albero.</span><span class="sxs-lookup"><span data-stu-id="9a0f9-143">After connecting to the appropriate instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="9a0f9-144">Espandere **Database**e, a seconda del database, selezionare un database utente o espandere **Database di sistema** e selezionare un database di sistema.</span><span class="sxs-lookup"><span data-stu-id="9a0f9-144">Expand **Databases**, and depending on the database, either select a user database or expand **System Databases** and select a system database.</span></span>  
  
3.  <span data-ttu-id="9a0f9-145">Fare clic con il pulsante destro del mouse sul database, scegliere **Attività**e quindi fare clic su **Backup**.</span><span class="sxs-lookup"><span data-stu-id="9a0f9-145">Right-click the database, point to **Tasks**, and then click **Back Up**.</span></span> <span data-ttu-id="9a0f9-146">Verrà visualizzata la finestra di dialogo **Backup database** .</span><span class="sxs-lookup"><span data-stu-id="9a0f9-146">The **Back Up Database** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="9a0f9-147">Nella `Database` casella di Riepilogo verificare il nome del database.</span><span class="sxs-lookup"><span data-stu-id="9a0f9-147">In the `Database` list box, verify the database name.</span></span> <span data-ttu-id="9a0f9-148">È possibile selezionare facoltativamente un database diverso nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="9a0f9-148">You can optionally select a different database from the list.</span></span>  
  
5.  <span data-ttu-id="9a0f9-149">È possibile eseguire il backup di un database per qualsiasi modello di recupero (**FULL**, **BULK_LOGGED**, o **SIMPLE**).</span><span class="sxs-lookup"><span data-stu-id="9a0f9-149">You can perform a database backup for any recovery model (**FULL**, **BULK_LOGGED**, or **SIMPLE**).</span></span>  
  
6.  <span data-ttu-id="9a0f9-150">Nella casella di riepilogo **Tipo di backup** selezionare **Completo**.</span><span class="sxs-lookup"><span data-stu-id="9a0f9-150">In the **Backup type** list box, select **Full**.</span></span>  
  
     <span data-ttu-id="9a0f9-151">Si noti che dopo aver eseguito un backup completo, è possibile creare un backup differenziale del database. Per altre informazioni, vedere [Creare un backup differenziale del database &#40;SQL Server&#41;](create-a-differential-database-backup-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="9a0f9-151">Note that after creating a full database backup, you can create a differential database backup; for more information, see [Create a Differential Database Backup &#40;SQL Server&#41;](create-a-differential-database-backup-sql-server.md).</span></span>  
  
7.  <span data-ttu-id="9a0f9-152">Facoltativamente, è possibile selezionare **Backup di sola copia** per creare un backup di sola copia.</span><span class="sxs-lookup"><span data-stu-id="9a0f9-152">Optionally, you can select **Copy Only Backup** to create a copy-only backup.</span></span> <span data-ttu-id="9a0f9-153">Un *backup di sola copia* è un backup di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] indipendente dalla sequenza di backup convenzionali di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9a0f9-153">A *copy-only backup* is a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup that is independent of the sequence of conventional [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backups.</span></span> <span data-ttu-id="9a0f9-154">Per altre informazioni, vedere [Backup di sola copia &#40;SQL Server&#41;](copy-only-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="9a0f9-154">For more information, see [Copy-Only Backups &#40;SQL Server&#41;](copy-only-backups-sql-server.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9a0f9-155">Quando si seleziona l'opzione **Differenziale** , non è possibile creare un backup di sola copia.</span><span class="sxs-lookup"><span data-stu-id="9a0f9-155">When the **Differential** option is selected, you cannot create a copy-only backup.</span></span>  
  
8.  <span data-ttu-id="9a0f9-156">Per **componente di backup**, fare clic su `Database` .</span><span class="sxs-lookup"><span data-stu-id="9a0f9-156">For **Backup component**, click `Database`.</span></span>  
  
9. <span data-ttu-id="9a0f9-157">Accettare il nome predefinito del set di backup indicato nella casella di testo **Nome** oppure immettere un nome diverso per il set di backup.</span><span class="sxs-lookup"><span data-stu-id="9a0f9-157">Either accept the default backup set name suggested in the **Name** text box, or enter a different name for the backup set.</span></span>  
  
10. <span data-ttu-id="9a0f9-158">Facoltativamente, immettere una descrizione del set di backup nella casella di testo **Descrizione** .</span><span class="sxs-lookup"><span data-stu-id="9a0f9-158">Optionally, in the **Description** text box, enter a description of the backup set.</span></span>  
  
11. <span data-ttu-id="9a0f9-159">Scegliere il tipo di destinazione di backup facendo clic su **Disco**, **Nastro** o **URL**.</span><span class="sxs-lookup"><span data-stu-id="9a0f9-159">Choose the type of backup destination by clicking **Disk**, **Tape** or **URL**.</span></span> <span data-ttu-id="9a0f9-160">Per selezionare i percorsi per un massimo di 64 unità disco o nastro contenenti un singolo set di supporti, fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="9a0f9-160">To select the paths of up to 64 disk or tape drives containing a single media set, click **Add**.</span></span> <span data-ttu-id="9a0f9-161">I percorsi selezionati vengono visualizzati nella casella di riepilogo **Backup su** .</span><span class="sxs-lookup"><span data-stu-id="9a0f9-161">The selected paths are displayed in the **Backup to** list box.</span></span>  
  
     <span data-ttu-id="9a0f9-162">Per rimuovere una destinazione di backup, selezionarla e fare clic su **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="9a0f9-162">To remove a backup destination, select it and click **Remove**.</span></span> <span data-ttu-id="9a0f9-163">Per visualizzare il contenuto di una destinazione di backup, selezionarla e fare clic su **Contenuto**.</span><span class="sxs-lookup"><span data-stu-id="9a0f9-163">To view the contents of a backup destination, select it and click **Contents**.</span></span>  
  
12. <span data-ttu-id="9a0f9-164">Per visualizzare o selezionare le opzioni dei supporti, fare clic su **Opzioni supporti** nel riquadro **Selezione pagina** .</span><span class="sxs-lookup"><span data-stu-id="9a0f9-164">To view or select the media options, click **Media Options** in the **Select a page** pane.</span></span>  
  
13. <span data-ttu-id="9a0f9-165">Selezionare un'opzione **Sovrascrivi supporti** facendo clic su una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9a0f9-165">Select an **Overwrite Media** option, by clicking one of the following:</span></span>  
  
    -   <span data-ttu-id="9a0f9-166">**Esegui backup nel set di supporti esistente**</span><span class="sxs-lookup"><span data-stu-id="9a0f9-166">**Back up to the existing media set**</span></span>  
  
         <span data-ttu-id="9a0f9-167">Per questa opzione, fare clic su **Accoda al set di backup esistente** o **Sovrascrivi tutti i set di backup esistenti**.</span><span class="sxs-lookup"><span data-stu-id="9a0f9-167">For this option, click either **Append to the existing backup set** or **Overwrite all existing backup sets**.</span></span> <span data-ttu-id="9a0f9-168">Per altre informazioni, vedere [Set di supporti, gruppi di supporti e set di backup &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="9a0f9-168">For more information, see [Media Sets, Media Families, and Backup Sets &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md).</span></span>  
  
         <span data-ttu-id="9a0f9-169">Selezionare facoltativamente l'opzione **Controlla nome set di supporti e scadenza set di backup** per impostare la verifica della data e dell'ora di scadenza del set di supporti e del set di backup durante l'operazione di backup.</span><span class="sxs-lookup"><span data-stu-id="9a0f9-169">Optionally, select **Check media set name and backup set expiration** to cause the backup operation to verify the date and time at which the media set and backup set expire.</span></span>  
  
         <span data-ttu-id="9a0f9-170">Immettere facoltativamente un nome nella casella di testo **Nome set di supporti** .</span><span class="sxs-lookup"><span data-stu-id="9a0f9-170">Optionally, enter a name in the **Media set name** text box.</span></span> <span data-ttu-id="9a0f9-171">Se non si specifica un nome, verrà creato un set di supporti con nome vuoto.</span><span class="sxs-lookup"><span data-stu-id="9a0f9-171">If no name is specified, a media set with a blank name is created.</span></span> <span data-ttu-id="9a0f9-172">Se si specifica un nome per il set di supporti, il supporto (nastro o disco) verrà controllato per verificare che il nome effettivo corrisponda al nome specificato.</span><span class="sxs-lookup"><span data-stu-id="9a0f9-172">If you specify a media set name, the media (tape or disk) is checked to see whether the actual name matches the name you enter here.</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="9a0f9-173">Questa opzione è disabilitata se è stato selezionato **URL** come destinazione di backup nella pagina **Generale** .</span><span class="sxs-lookup"><span data-stu-id="9a0f9-173">This option is disabled if you selected **URL** as the backup destination in the **General** page.</span></span> <span data-ttu-id="9a0f9-174">Per altre informazioni, vedere [Backup database &#40;pagina Opzioni di backup &#41;](back-up-database-media-options-page.md)</span><span class="sxs-lookup"><span data-stu-id="9a0f9-174">For more information, see [Back Up Database &#40;Media Options Page&#41;](back-up-database-media-options-page.md)</span></span>  
        >   
        >  <span data-ttu-id="9a0f9-175">Se si intende utilizzare la crittografia, non selezionare questa opzione.</span><span class="sxs-lookup"><span data-stu-id="9a0f9-175">If you plan to use encryption, do not select this option.</span></span> <span data-ttu-id="9a0f9-176">Se si seleziona questa opzione, le opzioni di crittografia nella pagina **Opzioni di backup** saranno disabilitate.</span><span class="sxs-lookup"><span data-stu-id="9a0f9-176">If you select this option, the encryption options in the **Backup Options** page will be disabled.</span></span> <span data-ttu-id="9a0f9-177">La crittografia non è supportata quando si esegue un accodamento al set di backup esistenti.</span><span class="sxs-lookup"><span data-stu-id="9a0f9-177">Encryption is not supported when appending to the existing backup set.</span></span>  
  
    -   <span data-ttu-id="9a0f9-178">**Esegui backup in un nuovo set di supporti e cancella tutti i set di backup esistenti**</span><span class="sxs-lookup"><span data-stu-id="9a0f9-178">**Back up to a new media set, and erase all existing backup sets**</span></span>  
  
         <span data-ttu-id="9a0f9-179">Per questa opzione, immettere un nome nella casella di testo **Nome nuovo set di supporti** e, facoltativamente, aggiungere una descrizione per il set di supporti nella casella di testo **Descrizione nuovo set di supporti** .</span><span class="sxs-lookup"><span data-stu-id="9a0f9-179">For this option, enter a name in the **New media set name** text box, and, optionally, describe the media set in the **New media set description** text box.</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="9a0f9-180">Questa opzione è disabilitata se è stato selezionato **URL** nella pagina **Generale** .</span><span class="sxs-lookup"><span data-stu-id="9a0f9-180">This option is disabled if you selected **URL** in the **General** page.</span></span> <span data-ttu-id="9a0f9-181">Queste azioni non sono supportate quando si esegue il backup nell'archiviazione di Azure.</span><span class="sxs-lookup"><span data-stu-id="9a0f9-181">These actions are not supported when backing up to Azure storage.</span></span>  
  
14. <span data-ttu-id="9a0f9-182">Nella sezione **affidabilità** selezionare facoltativamente:</span><span class="sxs-lookup"><span data-stu-id="9a0f9-182">In the **Reliability** section, optionally check:</span></span>  
  
    -   <span data-ttu-id="9a0f9-183">**Verifica backup al termine**.</span><span class="sxs-lookup"><span data-stu-id="9a0f9-183">**Verify backup when finished**.</span></span>  
  
    -   <span data-ttu-id="9a0f9-184">**Esegui checksum prima della scrittura nei supporti**e, facoltativamente, **Continua in caso di errori checksum**.</span><span class="sxs-lookup"><span data-stu-id="9a0f9-184">**Perform checksum before writing to media**, and, optionally, **Continue on checksum error**.</span></span> <span data-ttu-id="9a0f9-185">Per informazioni sui checksum, vedere [Possibili errori relativi ai supporti durante il backup e il ripristino &#40;SQL Server&#41;](possible-media-errors-during-backup-and-restore-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="9a0f9-185">For information on checksums, see [Possible Media Errors During Backup and Restore &#40;SQL Server&#41;](possible-media-errors-during-backup-and-restore-sql-server.md).</span></span>  
  
15. <span data-ttu-id="9a0f9-186">Se si esegue il backup su un'unità nastro, come specificato nella sezione **Destinazione** della pagina **Generale** , l'opzione **Scarica nastro al termine del backup** sarà attiva.</span><span class="sxs-lookup"><span data-stu-id="9a0f9-186">If you are backing up to a tape drive (as specified in the **Destination** section of the **General** page), the **Unload the tape after backup** option is active.</span></span> <span data-ttu-id="9a0f9-187">Se si seleziona questa opzione, verrà inoltre attivata l'opzione **Riavvolgi il nastro prima di scaricarlo** .</span><span class="sxs-lookup"><span data-stu-id="9a0f9-187">Clicking this option activates the **Rewind the tape before unloading** option.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9a0f9-188">Le opzioni presenti nella sezione **Log delle transazioni** sono attive solo in caso di backup di un log delle transazioni, come specificato nella sezione **Tipo backup** nella pagina **Generale** .</span><span class="sxs-lookup"><span data-stu-id="9a0f9-188">The options in the **Transaction log** section are inactive unless you are backing up a transaction log (as specified in the **Backup type** section of the **General** page).</span></span>  
  
16. <span data-ttu-id="9a0f9-189">Per visualizzare o selezionare le opzioni di backup, fare clic su **Opzioni di backup** nel riquadro **Selezione pagina** .</span><span class="sxs-lookup"><span data-stu-id="9a0f9-189">To view or select the backup options, click **Backup Options** in the **Select a page** pane.</span></span>  
  
17. <span data-ttu-id="9a0f9-190">Specificare quando il set di backup scadrà e potrà essere sovrascritto senza ignorare esplicitamente la verifica dei dati relativi alla scadenza:</span><span class="sxs-lookup"><span data-stu-id="9a0f9-190">Specify when the backup set will expire and can be overwritten without explicitly skipping verification of the expiration data:</span></span>  
  
    -   <span data-ttu-id="9a0f9-191">Per impostare la scadenza del set di backup dopo un numero di giorni specifico, fare clic su **Dopo** (opzione predefinita) e immettere il numero di giorni dopo la creazione del set trascorsi i quali il set scadrà.</span><span class="sxs-lookup"><span data-stu-id="9a0f9-191">To have the backup set expire after a specific number of days, click **After** (the default option), and enter the number of days after set creation that the set will expire.</span></span> <span data-ttu-id="9a0f9-192">È possibile impostare un valore compreso nell'intervallo da 0 a 99999 giorni. L'impostazione del valore 0 giorni indica che il set di backup non ha scadenza.</span><span class="sxs-lookup"><span data-stu-id="9a0f9-192">This value can be from 0 to 99999 days; a value of 0 days means that the backup set will never expire.</span></span>  
  
         <span data-ttu-id="9a0f9-193">Il valore predefinito viene impostato nell'opzione **Periodo di memorizzazione predefinito supporti di backup (giorni)** della finestra di dialogo **Proprietà server** (pagina Impostazioni database).</span><span class="sxs-lookup"><span data-stu-id="9a0f9-193">The default value is set in the **Default backup media retention (in days)** option of the **Server Properties** dialog box (Database Settings Page).</span></span> <span data-ttu-id="9a0f9-194">Per accedere alla pagina, fare clic con il pulsante destro del mouse sul nome del server in Esplora oggetti e scegliere Proprietà, quindi selezionare la pagina **Impostazioni database** .</span><span class="sxs-lookup"><span data-stu-id="9a0f9-194">To access this, right-click the server name in Object Explorer and select properties; then select the **Database Settings** page.</span></span>  
  
    -   <span data-ttu-id="9a0f9-195">Per impostare una data di scadenza specifica per il set di backup, fare clic su **Il**e immettere la data di scadenza del set.</span><span class="sxs-lookup"><span data-stu-id="9a0f9-195">To have the backup set expire on a specific date, click **On**, and enter the date on which the set will expire.</span></span>  
  
         <span data-ttu-id="9a0f9-196">Per altre informazioni sulle date di scadenza dei backup, vedere [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9a0f9-196">For more information about backup expiration dates, see [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql).</span></span>  
  
18. [!INCLUDE[ssEnterpriseEd10](../../../includes/ssenterpriseed10-md.md)] <span data-ttu-id="9a0f9-197">e versioni successive supporta la [compressione dei backup](backup-compression-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="9a0f9-197">and later supports [backup compression](backup-compression-sql-server.md).</span></span> <span data-ttu-id="9a0f9-198">Per impostazione predefinita, la compressione di un backup dipende dal valore dell'opzione di configurazione del server **Valore predefinito di compressione backup**.</span><span class="sxs-lookup"><span data-stu-id="9a0f9-198">By default, whether a backup is compressed depends on the value of the **backup-compression default** server configuration option.</span></span> <span data-ttu-id="9a0f9-199">Tuttavia, indipendentemente dall'impostazione predefinita a livello di server corrente, è possibile comprimere un backup selezionando **Comprimi backup**ed è possibile impedire la compressione selezionando **Non comprimere il backup**.</span><span class="sxs-lookup"><span data-stu-id="9a0f9-199">However, regardless of the current server-level default, you can compress a backup by checking **Compress backup**, and you can prevent compression by checking **Do not compress backup**.</span></span>  
  
     <span data-ttu-id="9a0f9-200">**Per visualizzare o modificare l'impostazione predefinita corrente della compressione dei backup**</span><span class="sxs-lookup"><span data-stu-id="9a0f9-200">**To view or change the current backup compression default**</span></span>  
  
    -   [<span data-ttu-id="9a0f9-201">Visualizzare o configurare l'opzione di configurazione del server backup compression default</span><span class="sxs-lookup"><span data-stu-id="9a0f9-201">View or Configure the backup compression default Server Configuration Option</span></span>](../../database-engine/configure-windows/view-or-configure-the-backup-compression-default-server-configuration-option.md)  
  
19. <span data-ttu-id="9a0f9-202">Specificare se utilizzare la crittografia per il backup.</span><span class="sxs-lookup"><span data-stu-id="9a0f9-202">Specify whether to use encryption for the backup.</span></span> <span data-ttu-id="9a0f9-203">Selezionare un algoritmo di crittografia da utilizzare per il passaggio di crittografia e specificare un certificato o una chiave asimmetrica da un elenco di chiavi asimmetriche o di certificati esistenti.</span><span class="sxs-lookup"><span data-stu-id="9a0f9-203">Select an encryption algorithm to use for the encryption step, and provide a Certificate or Asymmetric key from a list of existing certificates or asymmetric keys.</span></span> <span data-ttu-id="9a0f9-204">La crittografia è supportata in SQL Server 2014 o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="9a0f9-204">Encryption is supported in SQL Server 2014 or later.</span></span> <span data-ttu-id="9a0f9-205">Per altre informazioni sulle opzioni di crittografia, vedere [Eseguire il backup di database &#40;pagina Opzioni di backup&#41;](back-up-database-backup-options-page.md).</span><span class="sxs-lookup"><span data-stu-id="9a0f9-205">For more details on the Encryption options, see [Back Up Database &#40;Backup Options Page&#41;](back-up-database-backup-options-page.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9a0f9-206">In alternativa, è possibile creare i backup di database tramite Creazione guidata piano di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="9a0f9-206">Alternatively, you can use the Maintenance Plan Wizard to create database backups.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="9a0f9-207">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9a0f9-207">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-full-database-backup"></a><span data-ttu-id="9a0f9-208">Per creare un backup completo del database</span><span class="sxs-lookup"><span data-stu-id="9a0f9-208">To create a full database backup</span></span>  
  
1.  <span data-ttu-id="9a0f9-209">Per creare backup completo del database, eseguire l'istruzione BACKUP DATABASE specificando:</span><span class="sxs-lookup"><span data-stu-id="9a0f9-209">Execute the BACKUP DATABASE statement to create the full database backup, specifying:</span></span>  
  
    -   <span data-ttu-id="9a0f9-210">Il nome del database di cui eseguire il backup.</span><span class="sxs-lookup"><span data-stu-id="9a0f9-210">The name of the database to back up.</span></span>  
  
    -   <span data-ttu-id="9a0f9-211">Il dispositivo di backup in cui archiviare il backup completo del database.</span><span class="sxs-lookup"><span data-stu-id="9a0f9-211">The backup device where the full database backup is written.</span></span>  
  
     <span data-ttu-id="9a0f9-212">La sintassi di base dell'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] per un backup completo del database è la seguente:</span><span class="sxs-lookup"><span data-stu-id="9a0f9-212">The basic [!INCLUDE[tsql](../../includes/tsql-md.md)] syntax for a full database backup is:</span></span>  
  
     <span data-ttu-id="9a0f9-213">BACKUP DATABASE *database*</span><span class="sxs-lookup"><span data-stu-id="9a0f9-213">BACKUP DATABASE *database*</span></span>  
  
     <span data-ttu-id="9a0f9-214">TO *dispositivo_backup* [ **,** ...*n* ]</span><span class="sxs-lookup"><span data-stu-id="9a0f9-214">TO *backup_device* [ **,**...*n* ]</span></span>  
  
     <span data-ttu-id="9a0f9-215">[ WITH *con_opzioni* [ **,** ...*o* ] ];</span><span class="sxs-lookup"><span data-stu-id="9a0f9-215">[ WITH *with_options* [ **,**...*o* ] ] ;</span></span>  
  
    |<span data-ttu-id="9a0f9-216">Opzione</span><span class="sxs-lookup"><span data-stu-id="9a0f9-216">Option</span></span>|<span data-ttu-id="9a0f9-217">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9a0f9-217">Description</span></span>|  
    |------------|-----------------|  
    |<span data-ttu-id="9a0f9-218">*database*</span><span class="sxs-lookup"><span data-stu-id="9a0f9-218">*database*</span></span>|<span data-ttu-id="9a0f9-219">Corrisponde al database di cui eseguire il backup.</span><span class="sxs-lookup"><span data-stu-id="9a0f9-219">Is the database that is to be backed up.</span></span>|  
    |<span data-ttu-id="9a0f9-220">*backup_device* [ **,** ...*n* ]</span><span class="sxs-lookup"><span data-stu-id="9a0f9-220">*backup_device* [ **,**...*n* ]</span></span>|<span data-ttu-id="9a0f9-221">Specifica un elenco di dispositivi di backup da 1 a 64 da utilizzare per l'operazione di backup.</span><span class="sxs-lookup"><span data-stu-id="9a0f9-221">Specifies a list of from 1 to 64 backup devices to use for the backup operation.</span></span> <span data-ttu-id="9a0f9-222">È possibile specificare un dispositivo di backup fisico oppure un dispositivo di backup logico corrispondente se è già stata definito.</span><span class="sxs-lookup"><span data-stu-id="9a0f9-222">You can specify a physical backup device, or you can specify a corresponding logical backup device, if already defined.</span></span> <span data-ttu-id="9a0f9-223">Per specificare un dispositivo di backup fisico, utilizzare l'opzione DISK o TAPE:</span><span class="sxs-lookup"><span data-stu-id="9a0f9-223">To specify a physical backup device, use the DISK or TAPE option:</span></span><br /><br /> <span data-ttu-id="9a0f9-224">{ DISK &#124; TAPE } **=** _nome_dispositivo_backup_fisico_</span><span class="sxs-lookup"><span data-stu-id="9a0f9-224">{ DISK &#124; TAPE } **=**_physical_backup_device_name_</span></span><br /><br /> <span data-ttu-id="9a0f9-225">Per altre informazioni, vedere [Dispositivi di backup &#40;SQL Server&#41;](backup-devices-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="9a0f9-225">For more information, see [Backup Devices &#40;SQL Server&#41;](backup-devices-sql-server.md).</span></span>|  
    |<span data-ttu-id="9a0f9-226">WITH *con_opzioni* [ **,** ...*o* ]</span><span class="sxs-lookup"><span data-stu-id="9a0f9-226">WITH *with_options* [ **,**...*o* ]</span></span>|<span data-ttu-id="9a0f9-227">Facoltativamente, specifica una o più opzioni aggiuntive, *o*.</span><span class="sxs-lookup"><span data-stu-id="9a0f9-227">Optionally, specifies one or more additional options, *o*.</span></span> <span data-ttu-id="9a0f9-228">Per informazioni su alcune opzioni WITH di base, vedere il passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="9a0f9-228">For information about some of the basic with options, see step 2.</span></span>|  
  
2.  <span data-ttu-id="9a0f9-229">Facoltativamente, specificare uno o più opzioni WITH.</span><span class="sxs-lookup"><span data-stu-id="9a0f9-229">Optionally, specify one or more WITH options.</span></span> <span data-ttu-id="9a0f9-230">Alcune opzioni WITH di base sono descritte di seguito.</span><span class="sxs-lookup"><span data-stu-id="9a0f9-230">A few basic WITH options are described here.</span></span> <span data-ttu-id="9a0f9-231">Per informazioni su tutte le opzioni WITH, vedere [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9a0f9-231">For information about all the WITH options, see [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql).</span></span>  
  
    -   <span data-ttu-id="9a0f9-232">Opzioni WITH del set di backup di base:</span><span class="sxs-lookup"><span data-stu-id="9a0f9-232">Basic backup set WITH options:</span></span>  
  
         <span data-ttu-id="9a0f9-233">{ COMPRESSION | NO_COMPRESSION }</span><span class="sxs-lookup"><span data-stu-id="9a0f9-233">{ COMPRESSION | NO_COMPRESSION }</span></span>  
         <span data-ttu-id="9a0f9-234">Solo in [!INCLUDE[ssEnterpriseEd10](../../../includes/ssenterpriseed10-md.md)] e versioni successive, specifica se la [compressione backup](backup-compression-sql-server.md) è eseguita su questo backup, ignorando l'impostazione predefinita a livello di server.</span><span class="sxs-lookup"><span data-stu-id="9a0f9-234">In [!INCLUDE[ssEnterpriseEd10](../../../includes/ssenterpriseed10-md.md)] and later only, specifies whether [backup compression](backup-compression-sql-server.md) is performed on this backup, overriding the server-level default.</span></span>  
  
         <span data-ttu-id="9a0f9-235">ENCRYPTION (ALGORITHM,  SERVER CERTIFICATE |ASYMMETRIC KEY)</span><span class="sxs-lookup"><span data-stu-id="9a0f9-235">ENCRYPTION (ALGORITHM,  SERVER CERTIFICATE |ASYMMETRIC KEY)</span></span>  
         <span data-ttu-id="9a0f9-236">Solo in SQL Server 2014 o versioni successive specificare l'algoritmo di crittografia da utilizzare e il certificato o la chiave asimmetrica da utilizzare per proteggere la crittografia.</span><span class="sxs-lookup"><span data-stu-id="9a0f9-236">In SQL Server 2014 or later only, specify the encryption algorithm to use, and the Certificate or Asymmetric key to use to secure the encryption.</span></span>  
  
         <span data-ttu-id="9a0f9-237">Description **=** { **' *`text`* '**  |  **@** _text_variable_ }</span><span class="sxs-lookup"><span data-stu-id="9a0f9-237">DESCRIPTION **=** { **'*`text`*'** | **@**_text_variable_ }</span></span>  
         <span data-ttu-id="9a0f9-238">Specifica il testo in formato libero che descrive il set di backup.</span><span class="sxs-lookup"><span data-stu-id="9a0f9-238">Specifies the free-form text that describes the backup set.</span></span> <span data-ttu-id="9a0f9-239">La stringa può essere composta da un massimo di 255 caratteri.</span><span class="sxs-lookup"><span data-stu-id="9a0f9-239">The string can have a maximum of 255 characters.</span></span>  
  
         <span data-ttu-id="9a0f9-240">Nome **=** { *backup_set_name*  |  **@** _backup_set_name_var_ }</span><span class="sxs-lookup"><span data-stu-id="9a0f9-240">NAME **=** { *backup_set_name* | **@**_backup_set_name_var_ }</span></span>  
         <span data-ttu-id="9a0f9-241">Specifica il nome del set di backup.</span><span class="sxs-lookup"><span data-stu-id="9a0f9-241">Specifies the name of the backup set.</span></span> <span data-ttu-id="9a0f9-242">I nomi possono essere composti da un massimo di 128 caratteri.</span><span class="sxs-lookup"><span data-stu-id="9a0f9-242">Names can have a maximum of 128 characters.</span></span> <span data-ttu-id="9a0f9-243">Se si omette NAME, al set di backup non viene assegnato alcun nome specifico.</span><span class="sxs-lookup"><span data-stu-id="9a0f9-243">If NAME is not specified, it is blank.</span></span>  
  
    -   <span data-ttu-id="9a0f9-244">Opzioni WITH del set di backup di base:</span><span class="sxs-lookup"><span data-stu-id="9a0f9-244">Basic backup set WITH options:</span></span>  
  
         <span data-ttu-id="9a0f9-245">Per impostazione predefinita, BACKUP accoda il backup a un set di supporti esistente, conservando i set di backup esistenti.</span><span class="sxs-lookup"><span data-stu-id="9a0f9-245">By default, BACKUP appends the backup to an existing media set, preserving existing backup sets.</span></span> <span data-ttu-id="9a0f9-246">E possibile specificarlo in modo esplicito utilizzando l'opzione NOINIT.</span><span class="sxs-lookup"><span data-stu-id="9a0f9-246">To explicitly specify this, use the NOINIT option.</span></span> <span data-ttu-id="9a0f9-247">Per informazioni sull'accodamento a set di backup esistenti, vedere [Set di supporti, gruppi di supporti e set di backup &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="9a0f9-247">For information about appending to existing backup sets, see [Media Sets, Media Families, and Backup Sets &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md).</span></span>  
  
         <span data-ttu-id="9a0f9-248">In alternativa, utilizzare l'opzione FORMAT per formattare i supporti di backup:</span><span class="sxs-lookup"><span data-stu-id="9a0f9-248">Alternatively, to format the backup media, use the FORMAT option:</span></span>  
  
         <span data-ttu-id="9a0f9-249">Format [ **,** MEDIANAME **=** { *media_name*  |  **@** _media_name_variable_ }] [ **,** MEDIADESCRIPTION **=** { *Text*  |  **@** _text_variable_ }]</span><span class="sxs-lookup"><span data-stu-id="9a0f9-249">FORMAT [ **,** MEDIANAME**=** { *media_name* | **@**_media_name_variable_ } ] [ **,** MEDIADESCRIPTION **=** { *text* | **@**_text_variable_ } ]</span></span>  
         <span data-ttu-id="9a0f9-250">Utilizzare la clausola FORMAT, se i supporti vengono utilizzati per la prima volta o si desiderano sovrascrivere tutti i dati esistenti.</span><span class="sxs-lookup"><span data-stu-id="9a0f9-250">Use the FORMAT clause when you are using media for the first time or you want to overwrite all existing data.</span></span> <span data-ttu-id="9a0f9-251">Facoltativamente, assegnare al nuovo supporto un nome e una descrizione.</span><span class="sxs-lookup"><span data-stu-id="9a0f9-251">Optionally, assign the new media a media name and description.</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="9a0f9-252">Utilizzare la clausola FORMAT dell'istruzione BACKUP con estrema cautela, in quanto entrambe comportano la cancellazione di eventuali backup archiviati in precedenza nei supporti di backup.</span><span class="sxs-lookup"><span data-stu-id="9a0f9-252">Use extreme caution when you are using the FORMAT clause of the BACKUP statement because this destroys any backups that were previously stored on the backup media.</span></span>  
  
###  <a name="examples-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="9a0f9-253">Esempi (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="9a0f9-253">Examples (Transact-SQL)</span></span>  
  
#### <a name="a-backing-up-to-a-disk-device"></a><span data-ttu-id="9a0f9-254">R.</span><span class="sxs-lookup"><span data-stu-id="9a0f9-254">A.</span></span> <span data-ttu-id="9a0f9-255">Esecuzione del backup su un dispositivo disco</span><span class="sxs-lookup"><span data-stu-id="9a0f9-255">Backing up to a disk device</span></span>  
 <span data-ttu-id="9a0f9-256">Nell'esempio riportato di seguito viene eseguito il backup su disco del database [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] completo, utilizzando `FORMAT` per creare un nuovo set di supporti.</span><span class="sxs-lookup"><span data-stu-id="9a0f9-256">The following example backs up the complete [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database to disk, by using `FORMAT` to create a new media set.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
BACKUP DATABASE AdventureWorks2012  
TO DISK = 'Z:\SQLServerBackups\AdventureWorks2012.Bak'  
   WITH FORMAT,  
      MEDIANAME = 'Z_SQLServerBackups',  
      NAME = 'Full Backup of AdventureWorks2012';  
GO  
```  
  
#### <a name="b-backing-up-to-a-tape-device"></a><span data-ttu-id="9a0f9-257">B.</span><span class="sxs-lookup"><span data-stu-id="9a0f9-257">B.</span></span> <span data-ttu-id="9a0f9-258">Esecuzione del backup su un dispositivo nastro</span><span class="sxs-lookup"><span data-stu-id="9a0f9-258">Backing up to a tape device</span></span>  
 <span data-ttu-id="9a0f9-259">Nell'esempio seguente viene eseguito il backup completo su nastro del database [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)], accodandolo ai backup precedenti.</span><span class="sxs-lookup"><span data-stu-id="9a0f9-259">The following example backs up the complete [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)]database to tape, appending the backup to the previous backups.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
BACKUP DATABASE AdventureWorks2012  
   TO TAPE = '\\.\Tape0'  
   WITH NOINIT,  
      NAME = 'Full Backup of AdventureWorks2012';  
GO  
```  
  
#### <a name="c-backing-up-to-a-logical-tape-device"></a><span data-ttu-id="9a0f9-260">C.</span><span class="sxs-lookup"><span data-stu-id="9a0f9-260">C.</span></span> <span data-ttu-id="9a0f9-261">Esecuzione del backup su un dispositivo nastro logico</span><span class="sxs-lookup"><span data-stu-id="9a0f9-261">Backing up to a logical tape device</span></span>  
 <span data-ttu-id="9a0f9-262">Nell'esempio seguente viene creato in un dispositivo di backup logico per un'unità nastro.</span><span class="sxs-lookup"><span data-stu-id="9a0f9-262">The following example creates a logical backup device for a tape drive.</span></span> <span data-ttu-id="9a0f9-263">Nell'esempio viene quindi eseguito il backup completo del database [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] su quel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9a0f9-263">The example then backs up the complete [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database to that device.</span></span>  
  
```sql  
-- Create a logical backup device,   
-- AdventureWorks2012_Bak_Tape, for tape device \\.\tape0.  
USE master;  
GO  
EXEC sp_addumpdevice 'tape', 'AdventureWorks2012_Bak_Tape', '\\.\tape0'; USE AdventureWorks2012;  
GO  
BACKUP DATABASE AdventureWorks2012  
   TO AdventureWorks2012_Bak_Tape  
   WITH FORMAT,  
      MEDIANAME = 'AdventureWorks2012_Bak_Tape',  
      MEDIADESCRIPTION = '\\.\tape0',   
      NAME = 'Full Backup of AdventureWorks2012';  
GO  
```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="9a0f9-264">Uso di PowerShell</span><span class="sxs-lookup"><span data-stu-id="9a0f9-264">Using PowerShell</span></span>  
  
1.  <span data-ttu-id="9a0f9-265">Utilizzare il cmdlet `Backup-SqlDatabase`.</span><span class="sxs-lookup"><span data-stu-id="9a0f9-265">Use the `Backup-SqlDatabase` cmdlet.</span></span> <span data-ttu-id="9a0f9-266">Per indicare in modo esplicito che si tratta di un backup completo del database, specificare il parametro **-parametro BackupAction** con il valore predefinito `Database` .</span><span class="sxs-lookup"><span data-stu-id="9a0f9-266">To explicitly indicate that this is a full database backup, specify the **-BackupAction**  parameter with its default value, `Database`.</span></span> <span data-ttu-id="9a0f9-267">Questo parametro è facoltativo per i backup completi di database.</span><span class="sxs-lookup"><span data-stu-id="9a0f9-267">This parameter is optional for full database backups.</span></span>  
  
     <span data-ttu-id="9a0f9-268">L'esempio seguente consente di creare un backup di database completo del database di `MyDB` nel percorso di backup predefinito dell'istanza del server `Computer\Instance`.</span><span class="sxs-lookup"><span data-stu-id="9a0f9-268">The following example creates a full database backup of the `MyDB` database to the default backup location of the server instance `Computer\Instance`.</span></span> <span data-ttu-id="9a0f9-269">Facoltativamente, in questo esempio viene specificato `-BackupAction Database`.</span><span class="sxs-lookup"><span data-stu-id="9a0f9-269">Optionally, this example specifies `-BackupAction Database`.</span></span>  
  
    ```powershell
    Backup-SqlDatabase -ServerInstance Computer\Instance -Database MyDB -BackupAction Database  
    ```  
  
 <span data-ttu-id="9a0f9-270">**Per impostare e utilizzare il provider PowerShell per SQL Server**</span><span class="sxs-lookup"><span data-stu-id="9a0f9-270">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="9a0f9-271">Provider PowerShell per SQL Server</span><span class="sxs-lookup"><span data-stu-id="9a0f9-271">SQL Server PowerShell Provider</span></span>](../../powershell/sql-server-powershell-provider.md)  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="9a0f9-272">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="9a0f9-272">Related Tasks</span></span>  
  
-   [<span data-ttu-id="9a0f9-273">Eseguire il backup di un database (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="9a0f9-273">Back Up a Database (SQL Server)</span></span>](create-a-full-database-backup-sql-server.md)  
  
-   [<span data-ttu-id="9a0f9-274">Creare un backup differenziale del database &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9a0f9-274">Create a Differential Database Backup &#40;SQL Server&#41;</span></span>](create-a-differential-database-backup-sql-server.md)  
  
-   [<span data-ttu-id="9a0f9-275">Ripristinare un backup del database &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="9a0f9-275">Restore a Database Backup &#40;SQL Server Management Studio&#41;</span></span>](restore-a-database-backup-using-ssms.md)  
  
-   [<span data-ttu-id="9a0f9-276">Ripristinare un backup del database nel modello di recupero con registrazione minima &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9a0f9-276">Restore a Database Backup Under the Simple Recovery Model &#40;Transact-SQL&#41;</span></span>](restore-a-database-backup-under-the-simple-recovery-model-transact-sql.md)  
  
-   [<span data-ttu-id="9a0f9-277">Ripristinare un database fino al punto di errore nel modello di recupero con registrazione completa &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9a0f9-277">Restore a Database to the Point of Failure Under the Full Recovery Model &#40;Transact-SQL&#41;</span></span>](restore-database-to-point-of-failure-full-recovery.md)  
  
-   [<span data-ttu-id="9a0f9-278">Ripristinare un database in una nuova posizione &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9a0f9-278">Restore a Database to a New Location &#40;SQL Server&#41;</span></span>](restore-a-database-to-a-new-location-sql-server.md)  
  
-   [<span data-ttu-id="9a0f9-279">Utilizzare la Creazione guidata piano di manutenzione</span><span class="sxs-lookup"><span data-stu-id="9a0f9-279">Use the Maintenance Plan Wizard</span></span>](../maintenance-plans/use-the-maintenance-plan-wizard.md)  
  
## <a name="see-also"></a><span data-ttu-id="9a0f9-280">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9a0f9-280">See Also</span></span>  
 <span data-ttu-id="9a0f9-281">[Panoramica del backup &#40;SQL Server&#41;](backup-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9a0f9-281">[Backup Overview &#40;SQL Server&#41;](backup-overview-sql-server.md) </span></span>  
 <span data-ttu-id="9a0f9-282">[Backup di log delle transazioni &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9a0f9-282">[Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span></span>  
 <span data-ttu-id="9a0f9-283">[Set di supporti, gruppi di supporti e set di backup &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9a0f9-283">[Media Sets, Media Families, and Backup Sets &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md) </span></span>  
 <span data-ttu-id="9a0f9-284">[sp_addumpdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9a0f9-284">[sp_addumpdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) </span></span>  
 <span data-ttu-id="9a0f9-285">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9a0f9-285">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="9a0f9-286">[Eseguire il backup di database &#40;pagina Generale&#41;](../../integration-services/general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="9a0f9-286">[Back Up Database &#40;General Page&#41;](../../integration-services/general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="9a0f9-287">[Eseguire il backup di database &#40;pagina Opzioni di backup&#41;](back-up-database-backup-options-page.md) </span><span class="sxs-lookup"><span data-stu-id="9a0f9-287">[Back Up Database &#40;Backup Options Page&#41;](back-up-database-backup-options-page.md) </span></span>  
 <span data-ttu-id="9a0f9-288">[Backup differenziali &#40;SQL Server&#41;](differential-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9a0f9-288">[Differential Backups &#40;SQL Server&#41;](differential-backups-sql-server.md) </span></span>  
 [<span data-ttu-id="9a0f9-289">Backup completo del database &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9a0f9-289">Full Database Backups &#40;SQL Server&#41;</span></span>](full-database-backups-sql-server.md)  
