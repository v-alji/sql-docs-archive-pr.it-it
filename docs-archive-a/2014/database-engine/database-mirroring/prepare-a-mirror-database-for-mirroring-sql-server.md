---
title: Preparazione di un database mirror per il mirroring (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- database mirroring [SQL Server], preparing for mirroring
- logins [SQL Server], database mirroring
- mirror database [SQL Server]
ms.assetid: 8676f9d8-c451-419b-b934-786997d46c2b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: cf46b4f6fd8e7af55e1930ef6063c4754673fa79
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716784"
---
# <a name="prepare-a-mirror-database-for-mirroring-sql-server"></a><span data-ttu-id="d49b8-102">Preparazione di un database mirror per il mirroring (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="d49b8-102">Prepare a Mirror Database for Mirroring (SQL Server)</span></span>
  <span data-ttu-id="d49b8-103">Prima di avviare una sessione di mirroring del database, è necessario che il proprietario del database o l'amministratore del sistema verifichi che il database mirror sia stato creato e sia pronto per il mirroring.</span><span class="sxs-lookup"><span data-stu-id="d49b8-103">Before a database mirroring session can start, the database owner or system administrator must make sure that the mirror database has been created and is ready for mirroring.</span></span> <span data-ttu-id="d49b8-104">La creazione di un nuovo database mirror richiede l'esecuzione di un backup completo del database principale e di un backup del log successivo. Entrambi i backup devono quindi essere ripristinati sull'istanza del server mirror tramite WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="d49b8-104">Creating a new mirror database minimally requires taking a full backup of the principal database and a subsequent log backup and restoring them both onto the mirror server instance, using WITH NORECOVERY.</span></span>  
  
 <span data-ttu-id="d49b8-105">In questo argomento viene descritto come preparare un database mirror in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d49b8-105">This topic describes how to prepare a mirror database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="d49b8-106">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="d49b8-106">Before You Begin</span></span>  
  
###  <a name="requirements"></a><a name="Requirements"></a> <span data-ttu-id="d49b8-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d49b8-107">Requirements</span></span>  
  
-   <span data-ttu-id="d49b8-108">Le istanze del server principale e del server mirror devono essere eseguite nella stessa versione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d49b8-108">The principal and mirror server instances must be running on the same version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="d49b8-109">Sebbene sia possibile che la versione di SQL Server del server mirror sia successiva, questa configurazione è consigliata solo per processi di aggiornamento accuratamente pianificati.</span><span class="sxs-lookup"><span data-stu-id="d49b8-109">While it is possible for the mirror server to have a higher version of SQL Server, this configuration is only recommended during a carefully planned upgrade process.</span></span> <span data-ttu-id="d49b8-110">In questo tipo di configurazione si corre il rischio che venga effettuato un failover automatico durante il quale lo spostamento dei dati viene automaticamente sospeso in quanto non è possibile spostare i dati in una versione precedente di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d49b8-110">In such a configuration, you run the risk of an automatic failover, in which data movement is automatically suspended because data cannot move to a lower version of SQL Server.</span></span> <span data-ttu-id="d49b8-111">Per altre informazioni, vedere [Minimize Downtime for Mirrored Databases When Upgrading Server Instances](upgrading-mirrored-instances.md).</span><span class="sxs-lookup"><span data-stu-id="d49b8-111">For more information, see [Minimize Downtime for Mirrored Databases When Upgrading Server Instances](upgrading-mirrored-instances.md).</span></span>  
  
-   <span data-ttu-id="d49b8-112">Le istanze del server principale e del server mirror devono essere eseguite nella stessa edizione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d49b8-112">The principal and mirror server instances must be running on the same edition of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="d49b8-113">Per informazioni sul supporto del mirroring del database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], vedere [Funzionalità supportate dalle edizioni di SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="d49b8-113">For information about support for database mirroring in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
-   <span data-ttu-id="d49b8-114">Il database deve utilizzare il modello di recupero con registrazione completa.</span><span class="sxs-lookup"><span data-stu-id="d49b8-114">The database must use the full recovery model.</span></span>  
  
     <span data-ttu-id="d49b8-115">Per altre informazioni, vedere [Visualizzare o modificare il modello di recupero di un database &#40;SQL Server&#41;](../../relational-databases/backup-restore/view-or-change-the-recovery-model-of-a-database-sql-server.md) o [sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) e [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d49b8-115">For more information, see [View or Change the Recovery Model of a Database &#40;SQL Server&#41;](../../relational-databases/backup-restore/view-or-change-the-recovery-model-of-a-database-sql-server.md) or [sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) and [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span></span>  
  
-   <span data-ttu-id="d49b8-116">Il nome del database mirror deve essere identico a quello del database principale.</span><span class="sxs-lookup"><span data-stu-id="d49b8-116">The name of the mirror database must be the same as the name of the principal database.</span></span>  
  
-   <span data-ttu-id="d49b8-117">Per poter eseguire correttamente il mirroring, è necessario che lo stato del database mirror sia RESTORING.</span><span class="sxs-lookup"><span data-stu-id="d49b8-117">The mirror database must be in the RESTORING state for mirroring to work.</span></span> <span data-ttu-id="d49b8-118">Quando si prepara un database mirror, è necessario utilizzare l'opzione RESTORE WITH NORECOVERY per tutte le operazioni di ripristino.</span><span class="sxs-lookup"><span data-stu-id="d49b8-118">When preparing a mirror database, you must use RESTORE WITH NORECOVERY for every restore operation.</span></span> <span data-ttu-id="d49b8-119">Per ripristinare un backup completo del database principale, seguito da tutti i backup del log successivi sarà necessaria almeno l'opzione WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="d49b8-119">Minimally, you will need to restore WITH NORECOVERY a full backup of the principal database, followed by all subsequent log backups.</span></span>  
  
-   <span data-ttu-id="d49b8-120">Nel sistema in cui si desidera creare il database mirror deve essere disponibile un'unità disco con spazio sufficiente per contenere il database in questione.</span><span class="sxs-lookup"><span data-stu-id="d49b8-120">The system where you plan to create the mirror database must possesses a disk drive with sufficient space to hold the mirror database.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="d49b8-121">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="d49b8-121">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="d49b8-122">Non è possibile eseguire il mirroring del database di sistema **master**, **msdb**, **temp**o **model** .</span><span class="sxs-lookup"><span data-stu-id="d49b8-122">You cannot mirror the **master**, **msdb**, **temp**, or **model** system databases.</span></span>  
  
-   <span data-ttu-id="d49b8-123">Non è possibile eseguire il mirroring di un database appartenente a un [gruppi di disponibilità AlwaysOn (SQL Server)](../availability-groups/windows/always-on-availability-groups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="d49b8-123">You cannot mirror a database that belongs to an [AlwaysOn Availability Groups (SQL Server)](../availability-groups/windows/always-on-availability-groups-sql-server.md).</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="d49b8-124">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="d49b8-124">Recommendations</span></span>  
  
-   <span data-ttu-id="d49b8-125">Utilizzare un backup completo molto recente o uno differenziale recente del database principale.</span><span class="sxs-lookup"><span data-stu-id="d49b8-125">Use a very recent full database backup or a recent differential database backup of the principal database.</span></span>  
  
-   <span data-ttu-id="d49b8-126">Se un processo di backup del log è stato pianificato in modo da essere eseguito sul database principale con una frequenza elevata, potrebbe essere necessario disabilitare tale processo fino all'avvio del mirroring.</span><span class="sxs-lookup"><span data-stu-id="d49b8-126">If a log backup job is scheduled to run very frequently on the principal database, you might have to disable the backup job until mirroring has started.</span></span>  
  
-   <span data-ttu-id="d49b8-127">Se possibile, è consigliabile che il percorso del database mirror, inclusa la lettera di unità, sia identico a quello del database principale.</span><span class="sxs-lookup"><span data-stu-id="d49b8-127">If possible, the path (including the drive letter) of the mirror database should be identical to the path of the principal database.</span></span>  
  
     <span data-ttu-id="d49b8-128">Se i percorsi dei file sono diversi, ad esempio il database principale è disponibile nell'unità F: e tale unità non è presente nel sistema mirror, è necessario includere l'opzione MOVE nell'istruzione RESTORE.</span><span class="sxs-lookup"><span data-stu-id="d49b8-128">If the file paths must differ, for example, if the principal database is on drive 'F:' but the mirror system lacks an F: drive, you must include the MOVE option in the RESTORE STATEMENT.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="d49b8-129">Per aggiungere un file durante una sessione di mirroring senza conseguenze per la sessione, è necessario che il percorso del file esista in entrambi i server.</span><span class="sxs-lookup"><span data-stu-id="d49b8-129">Adding a file during a mirroring session without impacting the session requires that the path of the file exists on both servers.</span></span> <span data-ttu-id="d49b8-130">Pertanto, se durante la creazione del database mirror i file del database vengono spostati, potrebbe essere impossibile aggiungere successivamente file al database mirror senza sospendere il mirroring.</span><span class="sxs-lookup"><span data-stu-id="d49b8-130">Therefore, if you move the database files when creating the mirror database, a later add-file operation might fail on the mirror database and cause mirroring to be suspended.</span></span> <span data-ttu-id="d49b8-131">Per informazioni sulla gestione di un'operazione di creazione file non riuscita, vedere [Risolvere i problemi relativi alla configurazione del mirroring del database &#40;SQL Server&#41;](troubleshoot-database-mirroring-configuration-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="d49b8-131">For information about dealing with a failed create-file operation, see [Troubleshoot Database Mirroring Configuration &#40;SQL Server&#41;](troubleshoot-database-mirroring-configuration-sql-server.md).</span></span>  
  
-   <span data-ttu-id="d49b8-132">Se il database principale ha cataloghi full-text, è consigliabile vedere [Mirroring di database e cataloghi full-text &#40;SQL Server&#41;](database-mirroring-and-full-text-catalogs-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="d49b8-132">If the principal database has any full-text catalogs, we recommend that you see [Database Mirroring and Full-Text Catalogs &#40;SQL Server&#41;](database-mirroring-and-full-text-catalogs-sql-server.md).</span></span>  
  
-   <span data-ttu-id="d49b8-133">Nel caso di un database di produzione, eseguire sempre il backup in un dispositivo distinto.</span><span class="sxs-lookup"><span data-stu-id="d49b8-133">For a production database, always back up to a separate device.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="d49b8-134">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="d49b8-134">Security</span></span>  
 <span data-ttu-id="d49b8-135">La proprietà TRUSTWORTHY è impostata su OFF quando viene eseguito il backup di un database.</span><span class="sxs-lookup"><span data-stu-id="d49b8-135">TRUSTWORTHY is set to OFF when a database is backed up.</span></span> <span data-ttu-id="d49b8-136">Di conseguenza, la proprietà TRUSTWORTHY è sempre impostata su OFF in un nuovo database mirror.</span><span class="sxs-lookup"><span data-stu-id="d49b8-136">Therefore, TRUSTWORTHY is always OFF on a new mirror database.</span></span> <span data-ttu-id="d49b8-137">Se il database deve risultare attendibile dopo un failover, è necessario eseguire passaggi di configurazione aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="d49b8-137">If the database needs to be trustworthy after a failover, additional setup steps are necessary.</span></span> <span data-ttu-id="d49b8-138">Per altre informazioni, vedere [Impostare un database mirror per l'uso della proprietà Trustworthy &#40;Transact-SQL&#41;](set-up-a-mirror-database-to-use-the-trustworthy-property-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="d49b8-138">For more information, see [Set Up a Mirror Database to Use the Trustworthy Property &#40;Transact-SQL&#41;](set-up-a-mirror-database-to-use-the-trustworthy-property-transact-sql.md).</span></span>  
  
 <span data-ttu-id="d49b8-139">Per informazioni sull'abilitazione della decrittografia automatica della chiave master del database di un database mirror, vedere [Impostazione di un database mirror crittografato](set-up-an-encrypted-mirror-database.md).</span><span class="sxs-lookup"><span data-stu-id="d49b8-139">For information about enabling automatic decryption of the database master key of a mirror database, see [Set Up an Encrypted Mirror Database](set-up-an-encrypted-mirror-database.md).</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="d49b8-140">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="d49b8-140">Permissions</span></span>  
 <span data-ttu-id="d49b8-141">Proprietario del database o amministratore di sistema.</span><span class="sxs-lookup"><span data-stu-id="d49b8-141">Database owner or system administrator.</span></span>  
  
##  <a name="to-prepare-an-existing-mirror-database-to-restart-mirroring"></a><a name="PrepareToRestartMirroring"></a> <span data-ttu-id="d49b8-142">Per preparare un database mirror esistente per il riavvio del mirroring</span><span class="sxs-lookup"><span data-stu-id="d49b8-142">To Prepare an Existing Mirror Database to Restart Mirroring</span></span>  
 <span data-ttu-id="d49b8-143">Se il mirroring è stato rimosso e lo stato del database mirror è ancora RECOVERING, è possibile riavviare il mirroring.</span><span class="sxs-lookup"><span data-stu-id="d49b8-143">If mirroring has been removed and the mirror database is still in the RECOVERING state, you can restart mirroring.</span></span>  
  
1.  <span data-ttu-id="d49b8-144">Eseguire almeno un backup del log sul database principale.</span><span class="sxs-lookup"><span data-stu-id="d49b8-144">Take at least one log backup on the principal database.</span></span> <span data-ttu-id="d49b8-145">Per altre informazioni, vedere [Backup di un log delle transazioni &#40;SQL Server&#41;](../../relational-databases/backup-restore/back-up-a-transaction-log-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="d49b8-145">For more information, see [Back Up a Transaction Log &#40;SQL Server&#41;](../../relational-databases/backup-restore/back-up-a-transaction-log-sql-server.md).</span></span>  
  
2.  <span data-ttu-id="d49b8-146">Nel database mirror utilizzare RESTORE WITH NORECOVERY per il ripristino di tutti i backup del log eseguiti sul database principale dopo la rimozione del mirroring.</span><span class="sxs-lookup"><span data-stu-id="d49b8-146">On the mirror database, use RESTORE WITH NORECOVERY to restore all log backups taken on the principal database since mirroring was removed.</span></span> <span data-ttu-id="d49b8-147">Per altre informazioni, vedere [Ripristinare un backup del log delle transazioni &#40;SQL Server&#41;](../../relational-databases/backup-restore/restore-a-transaction-log-backup-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="d49b8-147">For more information, see [Restore a Transaction Log Backup &#40;SQL Server&#41;](../../relational-databases/backup-restore/restore-a-transaction-log-backup-sql-server.md).</span></span>  
  
##  <a name="to-prepare-a-new-mirror-database"></a><a name="CombinedProcedure"></a> <span data-ttu-id="d49b8-148">Per preparare un nuovo database mirror</span><span class="sxs-lookup"><span data-stu-id="d49b8-148">To Prepare a New Mirror Database</span></span>  
 <span data-ttu-id="d49b8-149">**Per preparare un database mirror**</span><span class="sxs-lookup"><span data-stu-id="d49b8-149">**To prepare a mirror database**</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d49b8-150">Per un esempio [!INCLUDE[tsql](../../includes/tsql-md.md)] di questa procedura, vedere [Esempio (Transact-SQL)](#TsqlExample)più avanti in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="d49b8-150">For a [!INCLUDE[tsql](../../includes/tsql-md.md)] example of this procedure, see [Example (Transact-SQL)](#TsqlExample), later in this section.</span></span>  
  
1.  <span data-ttu-id="d49b8-151">Connettersi all'istanza del server principale.</span><span class="sxs-lookup"><span data-stu-id="d49b8-151">Connect to principal server instance.</span></span>  
  
2.  <span data-ttu-id="d49b8-152">Creare un backup completo o differenziale del database principale.</span><span class="sxs-lookup"><span data-stu-id="d49b8-152">Create either a full database backup or a differential database backup of the principal database.</span></span>  
  
    -   [<span data-ttu-id="d49b8-153">Creazione di un backup completo del database &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="d49b8-153">Create a Full Database Backup &#40;SQL Server&#41;</span></span>](../../relational-databases/backup-restore/create-a-full-database-backup-sql-server.md)  
  
    -   <span data-ttu-id="d49b8-154">[Creare un backup differenziale del database &#40;SQL Server&#41;](../../relational-databases/backup-restore/create-a-differential-database-backup-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="d49b8-154">[Create a Differential Database Backup &#40;SQL Server&#41;](../../relational-databases/backup-restore/create-a-differential-database-backup-sql-server.md).</span></span>  
  
3.  <span data-ttu-id="d49b8-155">In genere, è necessario eseguire almeno un backup del log sul database principale.</span><span class="sxs-lookup"><span data-stu-id="d49b8-155">Typically, you need to take at least one log backup on the principal database.</span></span> <span data-ttu-id="d49b8-156">È tuttavia possibile evitare il backup del log se il database è stato appena creato e non è ancora stato eseguito alcun backup del log oppure se il modello di recupero è stato appena modificato da SIMPLE a FULL.</span><span class="sxs-lookup"><span data-stu-id="d49b8-156">However, a log backup might be unnecessary, if the database has just been created and no log backup has been taken yet, or if the recovery model has just been changed from SIMPLE to FULL.</span></span>  
  
    -   [<span data-ttu-id="d49b8-157">Eseguire il backup di un log delle transazioni &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="d49b8-157">Back Up a Transaction Log &#40;SQL Server&#41;</span></span>](../../relational-databases/backup-restore/back-up-a-transaction-log-sql-server.md)  
  
4.  <span data-ttu-id="d49b8-158">Se i backup non sono posizionati in un'unità di rete accessibile da entrambi i sistemi, copiare i backup del database e del log nel sistema in cui verrà ospitata l'istanza del server mirror.</span><span class="sxs-lookup"><span data-stu-id="d49b8-158">Unless the backups are on a network drive that is accessible from both systems, copy the database and log backups to the system that will host the mirror server instance.</span></span>  
  
5.  <span data-ttu-id="d49b8-159">Connettersi all'istanza del server mirror.</span><span class="sxs-lookup"><span data-stu-id="d49b8-159">Connect to mirror server instance.</span></span>  
  
6.  <span data-ttu-id="d49b8-160">Se si utilizza RESTORE WITH NORECOVERY, creare il database mirror ripristinando il backup di database completo e, facoltativamente, il backup di database differenziale più recente, nell'istanza del server mirror.</span><span class="sxs-lookup"><span data-stu-id="d49b8-160">Using RESTORE WITH NORECOVERY, create the mirror database by restoring the full database backup and, optionally, the most recent differential database backup, onto the mirror server instance.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d49b8-161">Se si ripristina il database un filegroup alla volta, prestare attenzione a ripristinare l'intero database.</span><span class="sxs-lookup"><span data-stu-id="d49b8-161">If you restore the database filegroup by filegroup, be sure to restore the whole database.</span></span>  
  
    -   [<span data-ttu-id="d49b8-162">Ripristinare un backup del database &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="d49b8-162">Restore a Database Backup &#40;SQL Server Management Studio&#41;</span></span>](../../relational-databases/backup-restore/restore-a-database-backup-using-ssms.md)  
  
    -   <span data-ttu-id="d49b8-163">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) e [RESTORE Arguments &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-arguments-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d49b8-163">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) and [RESTORE Arguments &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-arguments-transact-sql).</span></span>  
  
7.  <span data-ttu-id="d49b8-164">Se si utilizza RESTORE WITH NORECOVERY, applicare tutti i backup del log in sospeso al database mirror.</span><span class="sxs-lookup"><span data-stu-id="d49b8-164">Using RESTORE WITH NORECOVERY, apply any outstanding log backup or backups to the mirror database.</span></span>  
  
    -   [<span data-ttu-id="d49b8-165">Ripristinare un backup del log delle transazioni &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="d49b8-165">Restore a Transaction Log Backup &#40;SQL Server&#41;</span></span>](../../relational-databases/backup-restore/restore-a-transaction-log-backup-sql-server.md)  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="d49b8-166">Esempio (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="d49b8-166">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="d49b8-167">Prima di iniziare una sessione di mirroring del database, è necessario creare il database mirror.</span><span class="sxs-lookup"><span data-stu-id="d49b8-167">Before you can start a database mirroring session, you must create the mirror database.</span></span> <span data-ttu-id="d49b8-168">Questa operazione deve essere eseguita poco prima di iniziare la sessione di mirroring.</span><span class="sxs-lookup"><span data-stu-id="d49b8-168">You should do this just before starting the mirroring session.</span></span>  
  
 <span data-ttu-id="d49b8-169">Nell'esempio viene utilizzato il database di esempio [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] in cui, per impostazione predefinita, viene utilizzato il modello di recupero con registrazione minima.</span><span class="sxs-lookup"><span data-stu-id="d49b8-169">This example uses the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database, which uses the simple recovery model by default.</span></span>  
  
1.  <span data-ttu-id="d49b8-170">Per utilizzare il mirroring con il database [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] , è necessario modificare il database in modo da utilizzare il modello di recupero con registrazione completa:</span><span class="sxs-lookup"><span data-stu-id="d49b8-170">To use database mirroring with the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database, modify it to use the full recovery model:</span></span>  
  
    ```  
    USE master;  
    GO  
    ALTER DATABASE AdventureWorks   
    SET RECOVERY FULL;  
    GO  
    ```  
  
2.  <span data-ttu-id="d49b8-171">Dopo aver modificato il modello di recupero del database da SIMPLE a FULL, creare un backup completo da utilizzare per la creazione del database mirror.</span><span class="sxs-lookup"><span data-stu-id="d49b8-171">After modifying the recovery model of the database from SIMPLE to FULL, create a full backup, which can be used to create the mirror database.</span></span> <span data-ttu-id="d49b8-172">Dopo la modifica del modello di recupero, è consigliabile selezionare l'opzione WITH FORMAT per creare un nuovo set di supporti.</span><span class="sxs-lookup"><span data-stu-id="d49b8-172">Because the recovery model has just been changed, the WITH FORMAT option is specified to create a new media set.</span></span> <span data-ttu-id="d49b8-173">L'operazione risulta utile per separare i backup eseguiti durante l'utilizzo del modello di recupero con registrazione completa dai backup precedenti eseguiti durante l'utilizzo del modello di recupero con registrazione semplice.</span><span class="sxs-lookup"><span data-stu-id="d49b8-173">This is useful to separate the backups under the full recovery model from any previous backups made under the simple recovery model.</span></span> <span data-ttu-id="d49b8-174">Ai fini di questo esempio, il file di backup (`C:\AdventureWorks.bak`) verrà creato nella stessa unità del database.</span><span class="sxs-lookup"><span data-stu-id="d49b8-174">For the purpose of this example, the backup file (`C:\AdventureWorks.bak`) is created on the same drive as the database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d49b8-175">Nel caso di un database di produzione, è consigliabile eseguire sempre il backup in un dispositivo distinto.</span><span class="sxs-lookup"><span data-stu-id="d49b8-175">For a production database, you should always back up to a separate device.</span></span>  
  
     <span data-ttu-id="d49b8-176">Nell'istanza del server principale, ovvero in `PARTNERHOST1`, creare un backup completo del database principale nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="d49b8-176">On the principal server instance (on `PARTNERHOST1`), create a full backup of the principal database as follows:</span></span>  
  
    ```  
    BACKUP DATABASE AdventureWorks   
        TO DISK = 'C:\AdventureWorks.bak'   
        WITH FORMAT  
    GO  
    ```  
  
3.  <span data-ttu-id="d49b8-177">Copiare il backup completo nel server mirror.</span><span class="sxs-lookup"><span data-stu-id="d49b8-177">Copy the full backup to the mirror server.</span></span>  
  
4.  <span data-ttu-id="d49b8-178">Se si utilizza RESTORE WITH NORECOVERY, ripristinare il backup completo nell'istanza del server mirror.</span><span class="sxs-lookup"><span data-stu-id="d49b8-178">Using RESTORE WITH NORECOVERY, restore the full backup onto the mirror server instance.</span></span> <span data-ttu-id="d49b8-179">Il comando di ripristino dipende dal fatto che i percorsi del database mirror e di quello principale siano identici o meno.</span><span class="sxs-lookup"><span data-stu-id="d49b8-179">The restore command depends on whether the paths of principal and mirror databases are identical.</span></span>  
  
    -   <span data-ttu-id="d49b8-180">**Se i percorsi sono identici:**</span><span class="sxs-lookup"><span data-stu-id="d49b8-180">**If the paths are identical:**</span></span>  
  
         <span data-ttu-id="d49b8-181">Nell'istanza del server mirror, ovvero in `PARTNERHOST5`, ripristinare il backup completo nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="d49b8-181">On the mirror server instance (on `PARTNERHOST5`), restore the full backup as follows:</span></span>  
  
        ```  
        RESTORE DATABASE AdventureWorks   
            FROM DISK = 'C:\AdventureWorks.bak'   
            WITH NORECOVERY  
        GO  
        ```  
  
    -   <span data-ttu-id="d49b8-182">**Se i percorsi sono diversi:**</span><span class="sxs-lookup"><span data-stu-id="d49b8-182">**If the paths differ:**</span></span>  
  
         <span data-ttu-id="d49b8-183">Se il percorso del database mirror è diverso dal percorso del database principale, ad esempio perché le lettere di unità non corrispondono, per creare il database mirror è necessario che l'operazione di ripristino includa una clausola MOVE.</span><span class="sxs-lookup"><span data-stu-id="d49b8-183">If the path of the mirror database differs from the path of the principal database (for instance, their drive letters differ), creating the mirror database requires that the restore operation include a MOVE clause.</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="d49b8-184">Se il nome di percorso del database principale è diverso dal nome di percorso del database mirror, non è possibile aggiungere un file.</span><span class="sxs-lookup"><span data-stu-id="d49b8-184">If the path names of the principal and mirror databases differ, you cannot add a file.</span></span> <span data-ttu-id="d49b8-185">Alla ricezione del log relativo all'operazione di aggiunta del file, l'istanza del server mirror tenta infatti di salvare il nuovo file nella posizione utilizzata dal database principale.</span><span class="sxs-lookup"><span data-stu-id="d49b8-185">This is because on receiving the log for the add file operation, the mirror server instance attempts to place the new file in the location used by the principal database.</span></span>  
  
         <span data-ttu-id="d49b8-186">Ad esempio, il comando seguente ripristina un backup di un database principale che si trova in C:\Programmi\Microsoft SQL Server\MSSQL..*n*\MSSQL\Data\ in un percorso diverso, D:\Programmi\Microsoft SQL Server\MSSQL.*n*\MSSQL\Dat`a\`, in cui deve trovarsi il database mirror.</span><span class="sxs-lookup"><span data-stu-id="d49b8-186">For example, the following command restores a backup of a principal database residing in C:\Program Files\Microsoft SQL Server\MSSQL.*n*\MSSQL\Data\ to a different location, D:\Program Files\Microsoft SQL Server\MSSQL.*n*\MSSQL\Dat`a\`, where the mirror database is to reside.</span></span>  
  
        ```  
        RESTORE DATABASE AdventureWorks  
           FROM DISK='C:\AdventureWorks.bak'  
           WITH NORECOVERY,   
              MOVE 'AdventureWorks_Data' TO   
                 'D:\Program Files\Microsoft SQL Server\MSSQL.n\MSSQL\Data\AdventureWorks_Data.mdf',   
              MOVE 'AdventureWorks_Log' TO  
                 'D:\Program Files\Microsoft SQL Server\MSSQL.n\MSSQL\Data\AdventureWorks_Log.ldf';  
        GO  
        ```  
  
5.  <span data-ttu-id="d49b8-187">Dopo aver creato il backup completo, è necessario creare un backup del log nel database principale.</span><span class="sxs-lookup"><span data-stu-id="d49b8-187">After you create the full backup, you must create a log backup on the principal database.</span></span> <span data-ttu-id="d49b8-188">Ad esempio, l'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] seguente esegue il backup del log nello stesso file utilizzato dal precedente backup completo:</span><span class="sxs-lookup"><span data-stu-id="d49b8-188">For example, the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement backs up the log to the same file used by the preceding full backup:</span></span>  
  
    ```  
    BACKUP LOG AdventureWorks   
        TO DISK = 'C:\AdventureWorks.bak'   
    GO  
    ```  
  
6.  <span data-ttu-id="d49b8-189">Prima di avviare il mirroring, è necessario applicare il backup del log richiesto ed eventuali backup del log successivi.</span><span class="sxs-lookup"><span data-stu-id="d49b8-189">Before you can start mirroring, you must apply the required log backup (and any subsequent log backups).</span></span>  
  
     <span data-ttu-id="d49b8-190">Ad esempio, l'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] seguente ripristina il primo log da `C:\AdventureWorks.bak`:</span><span class="sxs-lookup"><span data-stu-id="d49b8-190">For example, the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement restores the first log from `C:\AdventureWorks.bak`:</span></span>  
  
    ```  
    RESTORE LOG AdventureWorks   
        FROM DISK = 'C:\AdventureWorks.bak'   
        WITH FILE=1, NORECOVERY  
    GO  
    ```  
  
7.  <span data-ttu-id="d49b8-191">Se vengono eseguiti altri backup del log prima dell'avvio del mirroring, è necessario ripristinare anche tali backup, in sequenza, nel server mirror tramite WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="d49b8-191">If any additional log backups occur before you start mirroring, you must also restore all of those log backups, in sequence, to the mirror server using WITH NORECOVERY.</span></span>  
  
     <span data-ttu-id="d49b8-192">Ad esempio, l'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] seguente ripristina due log aggiuntivi da `C:\AdventureWorks.bak`:</span><span class="sxs-lookup"><span data-stu-id="d49b8-192">For example, the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement restores two additional logs from `C:\AdventureWorks.bak`:</span></span>  
  
    ```  
    RESTORE LOG AdventureWorks   
        FROM DISK = 'C:\AdventureWorks.bak'   
        WITH FILE=2, NORECOVERY  
    GO  
    RESTORE LOG AdventureWorks   
        FROM DISK = 'C:\AdventureWorks.bak'   
        WITH FILE=3, NORECOVERY  
    GO  
    ```  
  
 <span data-ttu-id="d49b8-193">Per un esempio completo di impostazione del mirroring del database, con le impostazioni relative alla sicurezza e ai partner, nonché l'aggiunta di un server di controllo del mirroring, vedere [Impostazione del mirroring del database &#40;SQL Server&#41;](database-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="d49b8-193">For a complete example of setting up database mirroring, showing security setup, preparing the mirror database, setting up the partners, and adding a witness, see [Setting Up Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-preparing-a-mirror-database"></a><a name="FollowUp"></a> <span data-ttu-id="d49b8-194">Completamento: Dopo la preparazione di un database mirror</span><span class="sxs-lookup"><span data-stu-id="d49b8-194">Follow Up: After Preparing a Mirror Database</span></span>  
  
1.  <span data-ttu-id="d49b8-195">Se è stato eseguito un backup del log aggiuntivo dopo l'ultima operazione RESTORE LOG, è necessario applicare manualmente ogni backup del log aggiuntivo, utilizzando RESTORE WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="d49b8-195">If any additional log backups have been taken since your most recent RESTORE LOG operation, you must manually apply every additional log backup, using RESTORE WITH NORECOVERY.</span></span>  
  
2.  <span data-ttu-id="d49b8-196">Avviare la sessione di mirroring.</span><span class="sxs-lookup"><span data-stu-id="d49b8-196">Start the mirroring session.</span></span> <span data-ttu-id="d49b8-197">Per altre informazioni, vedere [Stabilire una sessione di mirroring del database tramite autenticazione di Windows &#40;SQL Server Management Studio&#41;](establish-database-mirroring-session-windows-authentication.md) o [Stabilire una sessione di mirroring del database tramite autenticazione di Windows &#40;Transact-SQL&#41;](database-mirroring-establish-session-windows-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="d49b8-197">For more information, see [Establish a Database Mirroring Session Using Windows Authentication &#40;SQL Server Management Studio&#41;](establish-database-mirroring-session-windows-authentication.md) or [Establish a Database Mirroring Session Using Windows Authentication &#40;Transact-SQL&#41;](database-mirroring-establish-session-windows-authentication.md).</span></span>  
  
3.  <span data-ttu-id="d49b8-198">Se è stato disabilitato il processo di backup sul database principale, riabilitare il processo.</span><span class="sxs-lookup"><span data-stu-id="d49b8-198">If you disabled the backup job on the principal database, reenable the job.</span></span>  
  
4.  <span data-ttu-id="d49b8-199">Se il database deve risultare attendibile dopo un failover, è necessario eseguire passaggi di configurazione aggiuntivi dopo l'avvio del mirroring.</span><span class="sxs-lookup"><span data-stu-id="d49b8-199">If the database needs to be trustworthy after a failover, extra setup steps are necessary after mirroring begins.</span></span> <span data-ttu-id="d49b8-200">Per altre informazioni, vedere [Impostare un database mirror per l'uso della proprietà Trustworthy &#40;Transact-SQL&#41;](set-up-a-mirror-database-to-use-the-trustworthy-property-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="d49b8-200">For more information, see [Set Up a Mirror Database to Use the Trustworthy Property &#40;Transact-SQL&#41;](set-up-a-mirror-database-to-use-the-trustworthy-property-transact-sql.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="d49b8-201">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="d49b8-201">Related Tasks</span></span>  
  
-   [<span data-ttu-id="d49b8-202">Creazione di un backup completo del database &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="d49b8-202">Create a Full Database Backup &#40;SQL Server&#41;</span></span>](../../relational-databases/backup-restore/create-a-full-database-backup-sql-server.md)  
  
-   [<span data-ttu-id="d49b8-203">Ripristinare un backup del log delle transazioni &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="d49b8-203">Restore a Transaction Log Backup &#40;SQL Server&#41;</span></span>](../../relational-databases/backup-restore/restore-a-transaction-log-backup-sql-server.md)  
  
-   [<span data-ttu-id="d49b8-204">Stabilire una sessione di mirroring del database tramite autenticazione di Windows &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="d49b8-204">Establish a Database Mirroring Session Using Windows Authentication &#40;SQL Server Management Studio&#41;</span></span>](establish-database-mirroring-session-windows-authentication.md)  
  
-   [<span data-ttu-id="d49b8-205">Stabilire una sessione di mirroring del database tramite autenticazione di Windows &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d49b8-205">Establish a Database Mirroring Session Using Windows Authentication &#40;Transact-SQL&#41;</span></span>](database-mirroring-establish-session-windows-authentication.md)  
  
-   [<span data-ttu-id="d49b8-206">Impostazione di un database mirror crittografato</span><span class="sxs-lookup"><span data-stu-id="d49b8-206">Set Up an Encrypted Mirror Database</span></span>](set-up-an-encrypted-mirror-database.md)  
  
-   [<span data-ttu-id="d49b8-207">Impostazione di un database mirror per l'utilizzo della proprietà Trustworthy &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d49b8-207">Set Up a Mirror Database to Use the Trustworthy Property &#40;Transact-SQL&#41;</span></span>](set-up-a-mirror-database-to-use-the-trustworthy-property-transact-sql.md)  
  
## <a name="see-also"></a><span data-ttu-id="d49b8-208">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d49b8-208">See Also</span></span>  
 <span data-ttu-id="d49b8-209">[Mirroring del database &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="d49b8-209">[Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="d49b8-210">[Sicurezza del trasporto per il mirroring del database e Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](transport-security-database-mirroring-always-on-availability.md) </span><span class="sxs-lookup"><span data-stu-id="d49b8-210">[Transport Security for Database Mirroring and AlwaysOn Availability Groups &#40;SQL Server&#41;](transport-security-database-mirroring-always-on-availability.md) </span></span>  
 <span data-ttu-id="d49b8-211">[Impostazione del mirroring del database &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="d49b8-211">[Setting Up Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="d49b8-212">[Backup e ripristino di indici e cataloghi full-text](../../relational-databases/indexes/indexes.md) </span><span class="sxs-lookup"><span data-stu-id="d49b8-212">[Back Up and Restore Full-Text Catalogs and Indexes](../../relational-databases/indexes/indexes.md) </span></span>  
 <span data-ttu-id="d49b8-213">[Mirroring di database e cataloghi full-text &#40;SQL Server&#41;](database-mirroring-and-full-text-catalogs-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="d49b8-213">[Database Mirroring and Full-Text Catalogs &#40;SQL Server&#41;](database-mirroring-and-full-text-catalogs-sql-server.md) </span></span>  
 <span data-ttu-id="d49b8-214">[Mirroring e replica del database &#40;SQL Server&#41;](database-mirroring-and-replication-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="d49b8-214">[Database Mirroring and Replication &#40;SQL Server&#41;](database-mirroring-and-replication-sql-server.md) </span></span>  
 <span data-ttu-id="d49b8-215">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d49b8-215">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="d49b8-216">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d49b8-216">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 [<span data-ttu-id="d49b8-217">Argomenti RESTORE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d49b8-217">RESTORE Arguments &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-arguments-transact-sql)  
  
  
