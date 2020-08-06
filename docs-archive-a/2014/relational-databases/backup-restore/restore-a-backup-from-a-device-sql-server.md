---
title: Ripristinare un backup da un dispositivo (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- restoring databases [SQL Server], device restores
- backup devices [SQL Server], restoring from
- database restores [SQL Server], device restores
- devices [SQL Server]
ms.assetid: 6e139de7-7de2-4d18-9df0-beac31ba7ff1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 50d7f7b8e255aea470a1065df669c0cc3169a8dd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714439"
---
# <a name="restore-a-backup-from-a-device-sql-server"></a><span data-ttu-id="2eca9-102">Ripristino di un backup da un dispositivo (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="2eca9-102">Restore a Backup from a Device (SQL Server)</span></span>
  <span data-ttu-id="2eca9-103">In questo argomento viene descritto il ripristino di un backup da un dispositivo in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2eca9-103">This topic describes how to restore a backup from a device in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2eca9-104">Per informazioni sul backup di SQL Server nel servizio di archiviazione BLOB di Azure, vedere [SQL Server backup e ripristino con il servizio di archiviazione BLOB di Azure](sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md).</span><span class="sxs-lookup"><span data-stu-id="2eca9-104">For information on SQL Server backup to the Azure Blob storage service, see, [SQL Server Backup and Restore with Azure Blob Storage Service](sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md).</span></span>  
  
 <span data-ttu-id="2eca9-105">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="2eca9-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="2eca9-106">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="2eca9-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="2eca9-107">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="2eca9-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="2eca9-108">**Per ripristinare un backup da un dispositivo utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="2eca9-108">**To restore a backup from a device, using:**</span></span>  
  
     [<span data-ttu-id="2eca9-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2eca9-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="2eca9-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2eca9-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="2eca9-111">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="2eca9-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="2eca9-112">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="2eca9-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="2eca9-113">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="2eca9-113">Permissions</span></span>  
 <span data-ttu-id="2eca9-114">Se il database da ripristinare non esiste, per eseguire un'operazione RESTORE l'utente deve disporre delle autorizzazioni CREATE DATABASE.</span><span class="sxs-lookup"><span data-stu-id="2eca9-114">If the database being restored does not exist, the user must have CREATE DATABASE permissions to be able to execute RESTORE.</span></span> <span data-ttu-id="2eca9-115">Se il database esiste, le autorizzazioni per l'istruzione RESTORE vengono assegnate per impostazione predefinita ai membri dei ruoli predefiniti del server **sysadmin** e **dbcreator** e al proprietario (**dbo**) del database. Per l'opzione FROM DATABASE_SNAPSHOT, il database esiste sempre.</span><span class="sxs-lookup"><span data-stu-id="2eca9-115">If the database exists, RESTORE permissions default to members of the **sysadmin** and **dbcreator** fixed server roles and the owner (**dbo**) of the database (for the FROM DATABASE_SNAPSHOT option, the database always exists).</span></span>  
  
 <span data-ttu-id="2eca9-116">Le autorizzazioni per l'istruzione RESTORE vengono assegnate ai ruoli in cui le informazioni sull'appartenenza sono sempre disponibili per il server.</span><span class="sxs-lookup"><span data-stu-id="2eca9-116">RESTORE permissions are given to roles in which membership information is always readily available to the server.</span></span> <span data-ttu-id="2eca9-117">Poiché è possibile controllare l'appartenenza ai ruoli predefiniti del database solo quando il database è accessibile e non è danneggiato, condizioni che non risultano sempre vere quando si esegue un'operazione RESTORE, i membri del ruolo predefinito del database **db_owner** non dispongono delle autorizzazioni per l'istruzione RESTORE.</span><span class="sxs-lookup"><span data-stu-id="2eca9-117">Because fixed database role membership can be checked only when the database is accessible and undamaged, which is not always the case when RESTORE is executed, members of the **db_owner** fixed database role do not have RESTORE permissions.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="2eca9-118">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2eca9-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-restore-a-backup-from-a-device"></a><span data-ttu-id="2eca9-119">Per ripristinare un backup da un dispositivo</span><span class="sxs-lookup"><span data-stu-id="2eca9-119">To restore a backup from a device</span></span>  
  
1.  <span data-ttu-id="2eca9-120">Dopo aver stabilito la connessione all'istanza appropriata del [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Esplora oggetti fare clic sul nome del server per espanderne l'albero.</span><span class="sxs-lookup"><span data-stu-id="2eca9-120">After connecting to the appropriate instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="2eca9-121">Espandere **Database**e, a seconda del database, selezionare un database utente o espandere **Database di sistema** e selezionare un database di sistema.</span><span class="sxs-lookup"><span data-stu-id="2eca9-121">Expand **Databases**, and, depending on the database, either select a user database or expand **System Databases** and select a system database.</span></span>  
  
3.  <span data-ttu-id="2eca9-122">Fare clic con il pulsante destro del mouse sul database, scegliere **Attività**e quindi fare clic su **Ripristina**.</span><span class="sxs-lookup"><span data-stu-id="2eca9-122">Right-click the database, point to **Tasks**, and then click **Restore**.</span></span>  
  
4.  <span data-ttu-id="2eca9-123">Fare clic sul tipo di operazione di ripristino desiderata,**Database**, **File e filegroup**o **Log delle transazioni**.</span><span class="sxs-lookup"><span data-stu-id="2eca9-123">Click the type of restore operation you want (**Database**, **Files and Filegroups**, or **Transaction Log**).</span></span> <span data-ttu-id="2eca9-124">Verrà aperta la finestra di dialogo appropriata.</span><span class="sxs-lookup"><span data-stu-id="2eca9-124">This opens the corresponding restore dialog box.</span></span>  
  
5.  <span data-ttu-id="2eca9-125">Nella pagina **Generale** fare clic su **Dispositivo di origine** nella sezione **Origine ripristino**.</span><span class="sxs-lookup"><span data-stu-id="2eca9-125">On the **General** page, in the **Restore source** section, click **From device**.</span></span>  
  
6.  <span data-ttu-id="2eca9-126">Fare clic su Sfoglia per la casella di testo **Dispositivo di origine** e verrà aperta la finestra di dialogo **Seleziona backup** .</span><span class="sxs-lookup"><span data-stu-id="2eca9-126">Click the browse button for the **From device** text box, which opens the **Specify Backup** dialog box.</span></span>  
  
7.  <span data-ttu-id="2eca9-127">Nella casella di testo **Supporti di backup** selezionare **Dispositivo di backup**e quindi fare clic sul pulsante **Aggiungi** per aprire la finestra di dialogo **Seleziona dispositivo di backup** .</span><span class="sxs-lookup"><span data-stu-id="2eca9-127">In the **Backup media** text box, select **Backup Device**, and click the **Add** button to open the **Select Backup Device** dialog box.</span></span>  
  
8.  <span data-ttu-id="2eca9-128">Nella casella di testo **Dispositivo di backup** selezionare il dispositivo che si desidera utilizzare per l'operazione di ripristino.</span><span class="sxs-lookup"><span data-stu-id="2eca9-128">In the **Backup device** text box, select the device you want to use for the restore operation.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="2eca9-129">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2eca9-129">Using Transact-SQL</span></span>  
  
#### <a name="to-restore-a-backup-from-a-device"></a><span data-ttu-id="2eca9-130">Per ripristinare un backup da un dispositivo</span><span class="sxs-lookup"><span data-stu-id="2eca9-130">To restore a backup from a device</span></span>  
  
1.  <span data-ttu-id="2eca9-131">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2eca9-131">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="2eca9-132">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="2eca9-132">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="2eca9-133">Nell'istruzione [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) , specificare un dispositivo di backup logico o fisico da utilizzare per l'operazione di backup.</span><span class="sxs-lookup"><span data-stu-id="2eca9-133">In the [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) statement, specify a logical or physical backup device to use for the backup operation.</span></span> <span data-ttu-id="2eca9-134">Questo esempio mostra come eseguire il ripristino da un file su disco con il nome fisico `Z:\SQLServerBackups\AdventureWorks2012.bak`.</span><span class="sxs-lookup"><span data-stu-id="2eca9-134">This example restores from a disk file that has the physical name `Z:\SQLServerBackups\AdventureWorks2012.bak`.</span></span>  
  
```sql  
RESTORE DATABASE AdventureWorks2012  
   FROM DISK = 'Z:\SQLServerBackups\AdventureWorks2012.bak' ;  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="2eca9-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2eca9-135">See Also</span></span>  
 <span data-ttu-id="2eca9-136">[RESTORE FILELISTONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-filelistonly-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2eca9-136">[RESTORE FILELISTONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-filelistonly-transact-sql) </span></span>  
 <span data-ttu-id="2eca9-137">[RESTORE HEADERONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-headeronly-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2eca9-137">[RESTORE HEADERONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-headeronly-transact-sql) </span></span>  
 <span data-ttu-id="2eca9-138">[RESTORE LABELONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-labelonly-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2eca9-138">[RESTORE LABELONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-labelonly-transact-sql) </span></span>  
 <span data-ttu-id="2eca9-139">[RESTORE VERIFYONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-verifyonly-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2eca9-139">[RESTORE VERIFYONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-verifyonly-transact-sql) </span></span>  
 <span data-ttu-id="2eca9-140">[Ripristinare un backup del database nel modello di recupero con registrazione minima &#40;Transact-SQL&#41;](restore-a-database-backup-under-the-simple-recovery-model-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="2eca9-140">[Restore a Database Backup Under the Simple Recovery Model &#40;Transact-SQL&#41;](restore-a-database-backup-under-the-simple-recovery-model-transact-sql.md) </span></span>  
 <span data-ttu-id="2eca9-141">[Ripristinare un backup del database &#40;SQL Server Management Studio&#41;](restore-a-database-backup-using-ssms.md) </span><span class="sxs-lookup"><span data-stu-id="2eca9-141">[Restore a Database Backup &#40;SQL Server Management Studio&#41;](restore-a-database-backup-using-ssms.md) </span></span>  
 <span data-ttu-id="2eca9-142">[Ripristinare un backup differenziale del database &#40;SQL Server&#41;](restore-a-differential-database-backup-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="2eca9-142">[Restore a Differential Database Backup &#40;SQL Server&#41;](restore-a-differential-database-backup-sql-server.md) </span></span>  
 <span data-ttu-id="2eca9-143">[Ripristinare un database in una nuova posizione &#40;SQL Server&#41;](restore-a-database-to-a-new-location-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="2eca9-143">[Restore a Database to a New Location &#40;SQL Server&#41;](restore-a-database-to-a-new-location-sql-server.md) </span></span>  
 <span data-ttu-id="2eca9-144">[Backup di file e filegroup &#40;SQL Server&#41;](back-up-files-and-filegroups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="2eca9-144">[Back Up Files and Filegroups &#40;SQL Server&#41;](back-up-files-and-filegroups-sql-server.md) </span></span>  
 <span data-ttu-id="2eca9-145">[Backup di un log delle transazioni &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="2eca9-145">[Back Up a Transaction Log &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md) </span></span>  
 [<span data-ttu-id="2eca9-146">Creare un backup differenziale del database &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="2eca9-146">Create a Differential Database Backup &#40;SQL Server&#41;</span></span>](create-a-differential-database-backup-sql-server.md)  
  
  
