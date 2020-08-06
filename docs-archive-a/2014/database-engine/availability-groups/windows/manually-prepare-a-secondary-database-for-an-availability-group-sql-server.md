---
title: Preparare manualmente un database secondario per un gruppo di disponibilità (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygroup.configsecondarydbs.f1
- sql12.swb.availabilitygroup.preparedbs.f1
helpviewer_keywords:
- secondary databases [SQL Server], in availability group
- secondary databases [SQL Server]
- Availability Groups [SQL Server], configuring
- Availability Groups [SQL Server], databases
ms.assetid: 9f2feb3c-ea9b-4992-8202-2aeed4f9a6dd
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3da3f7332bdabce65785b2844157dd4639389254
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626894"
---
# <a name="manually-prepare-a-secondary-database-for-an-availability-group-sql-server"></a><span data-ttu-id="22f6e-102">Preparare manualmente un database secondario per un gruppo di disponibilità (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="22f6e-102">Manually Prepare a Secondary Database for an Availability Group (SQL Server)</span></span>
  <span data-ttu-id="22f6e-103">In questo argomento viene illustrato come preparare un database secondario per un gruppo di disponibilità AlwaysOn in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)]o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="22f6e-103">This topic describes how to prepare a secondary database for an AlwaysOn availability group in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell.</span></span> <span data-ttu-id="22f6e-104">La preparazione di un database secondario richiede due passaggi: (1) ripristinare un backup del database recenti del database primario e dei backup del log successivo in ogni istanza del server che ospita la replica secondaria, utilizzando RESTORE WITH NORECOVERY e (2) creare un join del database ripristinato al gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="22f6e-104">Preparing a secondary database requires two steps: (1) restoring a recent database backup of the primary database and subsequent log backups onto each server instance that hosts the secondary replica, using RESTORE WITH NORECOVERY, and (2) joining the restored database to the availability group.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="22f6e-105">Se si dispone di una configurazione per il log shipping esistente, è possibile convertire il database primario per il log shipping insieme a uno o più dei relativi database secondari in un database primario AlwaysOn e uno o più dei relativi database secondari AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="22f6e-105">If you have an existing log shipping configuration, you might be able to convert the log shipping primary database along with one or more of its secondary databases to an AlwaysOn primary database and one or more AlwaysOn secondary databases.</span></span> <span data-ttu-id="22f6e-106">Per ulteriori informazioni, vedere [prerequisiti per la migrazione dal log shipping a Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](prereqs-migrating-log-shipping-to-always-on-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="22f6e-106">For more information, see [Prerequisites for Migrating from Log Shipping to AlwaysOn Availability Groups &#40;SQL Server&#41;](prereqs-migrating-log-shipping-to-always-on-availability-groups.md).</span></span>  
  
-   <span data-ttu-id="22f6e-107">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="22f6e-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="22f6e-108">Prerequisiti e restrizioni</span><span class="sxs-lookup"><span data-stu-id="22f6e-108">Prerequisites and Restrictions</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="22f6e-109">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="22f6e-109">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="22f6e-110">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="22f6e-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="22f6e-111">**Per preparare un database secondario tramite:**</span><span class="sxs-lookup"><span data-stu-id="22f6e-111">**To prepare a secondary database, using:**</span></span>  
  
     [<span data-ttu-id="22f6e-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="22f6e-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="22f6e-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="22f6e-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="22f6e-114">PowerShell</span><span class="sxs-lookup"><span data-stu-id="22f6e-114">PowerShell</span></span>](#PowerShellProcedure)  
  
-   [<span data-ttu-id="22f6e-115">Attività correlate a backup e ripristino</span><span class="sxs-lookup"><span data-stu-id="22f6e-115">Related Backup and Restore Tasks</span></span>](#RelatedTasks)  
  
-   <span data-ttu-id="22f6e-116">**Completamento:** [Dopo la preparazione di un database secondario](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="22f6e-116">**Follow Up:** [After Preparing a Secondary Database](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="22f6e-117">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="22f6e-117">Before You Begin</span></span>  
  
###  <a name="prerequisites-and-restrictions"></a><a name="Prerequisites"></a> <span data-ttu-id="22f6e-118">Prerequisiti e restrizioni</span><span class="sxs-lookup"><span data-stu-id="22f6e-118">Prerequisites and Restrictions</span></span>  
  
-   <span data-ttu-id="22f6e-119">Verificare che nel sistema in cui si desidera collocare il database sia presente un'unità disco con spazio sufficiente per i database secondari.</span><span class="sxs-lookup"><span data-stu-id="22f6e-119">Make sure that the system where you plan to place database possesses a disk drive with sufficient space for the secondary databases.</span></span>  
  
-   <span data-ttu-id="22f6e-120">Il nome del database secondario deve essere lo stesso del database primario.</span><span class="sxs-lookup"><span data-stu-id="22f6e-120">The name of the secondary database must be the same as the name of the primary database.</span></span>  
  
-   <span data-ttu-id="22f6e-121">Utilizzare RESTORE WITH NORECOVERY per ogni operazione di ripristino.</span><span class="sxs-lookup"><span data-stu-id="22f6e-121">Use RESTORE WITH NORECOVERY for every restore operation.</span></span>  
  
-   <span data-ttu-id="22f6e-122">Se il database secondario deve risiedere in un percorso di file diverso (inclusa la lettera dell'unità) dal database primario, è inoltre necessario utilizzare l'opzione WITH MOVE nel comando Restore per ognuno dei file di database per specificare il percorso del database secondario.</span><span class="sxs-lookup"><span data-stu-id="22f6e-122">If the secondary database needs to reside on a different file path (including the drive letter) than the primary database, the restore command must also use the WITH MOVE option for each of the database files to specify them to the path of the secondary database.</span></span>  
  
-   <span data-ttu-id="22f6e-123">Se si ripristina il database un filegroup alla volta, prestare attenzione a ripristinare l'intero database.</span><span class="sxs-lookup"><span data-stu-id="22f6e-123">If you restore the database filegroup by filegroup, be sure to restore the whole database.</span></span>  
  
-   <span data-ttu-id="22f6e-124">Dopo il ripristino del database, è necessario ripristinare (WITH NORECOVERY) ogni backup del log creato dall'ultimo backup dei dati ripristinato.</span><span class="sxs-lookup"><span data-stu-id="22f6e-124">After restoring the database, you must restore (WITH NORECOVERY) every log backup created since the last restored data backup.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="22f6e-125">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="22f6e-125">Recommendations</span></span>  
  
-   <span data-ttu-id="22f6e-126">Nelle istanze autonome di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]è consigliabile che il percorso del file di un determinato database secondario, inclusa la lettera di unità, sia se possibile identico a quello del database primario corrispondente.</span><span class="sxs-lookup"><span data-stu-id="22f6e-126">On stand-alone instances of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], we recommend that, if possible, the file path (including the drive letter) of a given secondary database be identical to the path of the corresponding primary database.</span></span> <span data-ttu-id="22f6e-127">Se durante la creazione di un database secondario i file del database vengono spostati, infatti, potrebbe essere impossibile aggiungere successivamente file al database secondario senza sospendere il database secondario.</span><span class="sxs-lookup"><span data-stu-id="22f6e-127">This is because if you move the database files when creating a secondary database, a later add-file operation might fail on the secondary database and cause the secondary database to be suspended.</span></span>  
  
-   <span data-ttu-id="22f6e-128">Prima di preparare i database secondari, si consiglia di sospendere i backup del log pianificati sui database nel gruppo di disponibilità finché non viene completata l'inizializzazione delle repliche secondarie.</span><span class="sxs-lookup"><span data-stu-id="22f6e-128">Before preparing your secondary databases, we strongly recommend that you suspend scheduled log backups on the databases in the availability group until the initialization of secondary replicas has completed.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="22f6e-129">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="22f6e-129">Security</span></span>  
 <span data-ttu-id="22f6e-130">Quando viene eseguito il backup di un database, la [Proprietà Trustworthy del database](../../../relational-databases/security/trustworthy-database-property.md) viene impostata su off.</span><span class="sxs-lookup"><span data-stu-id="22f6e-130">When a database is backed up, the [TRUSTWORTHY database property](../../../relational-databases/security/trustworthy-database-property.md) is set to OFF.</span></span> <span data-ttu-id="22f6e-131">Di conseguenza, la proprietà TRUSTWORTHY è sempre impostata su OFF in un database appena ripristinato.</span><span class="sxs-lookup"><span data-stu-id="22f6e-131">Therefore, TRUSTWORTHY is always OFF on a newly restored database.</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="22f6e-132">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="22f6e-132">Permissions</span></span>  
 <span data-ttu-id="22f6e-133">Le autorizzazioni BACKUP DATABASE e BACKUP LOG vengono assegnate per impostazione predefinita ai membri del ruolo predefinito del server **sysadmin** e dei ruoli predefiniti del database **db_owner** e **db_backupoperator** .</span><span class="sxs-lookup"><span data-stu-id="22f6e-133">BACKUP DATABASE and BACKUP LOG permissions default to members of the **sysadmin** fixed server role and the **db_owner** and **db_backupoperator** fixed database roles.</span></span> <span data-ttu-id="22f6e-134">Per altre informazioni, vedere [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="22f6e-134">For more information, see [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql).</span></span>  
  
 <span data-ttu-id="22f6e-135">Se il database da ripristinare non esiste nell'istanza del server, l'istruzione RESTORE richiede autorizzazioni CREATE DATABASE.</span><span class="sxs-lookup"><span data-stu-id="22f6e-135">When the database being restored does not exist on the server instance, the RESTORE statement requires CREATE DATABASE permissions.</span></span> <span data-ttu-id="22f6e-136">Per altre informazioni, vedere [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="22f6e-136">For more information, see [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="22f6e-137">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="22f6e-137">Using SQL Server Management Studio</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="22f6e-138"> Se i percorsi dei file di backup e ripristino sono identici nell'istanza del server che ospita una replica primaria e in ogni istanza che ospita una replica secondaria, è possibile creare database secondari utilizzando la [Creazione guidata Gruppo di disponibilità](use-the-availability-group-wizard-sql-server-management-studio.md), la procedura guidata [Aggiungi database a gruppo di disponibilità](use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md)o la procedura guidata [Aggiungi database a gruppo di disponibilità](availability-group-add-database-to-group-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="22f6e-138">If the backup and restore file paths are identical between the server instance that hosts the primary replica and every instance that hosts a secondary replica, you should be able create secondary databases by using [New Availability Group Wizard](use-the-availability-group-wizard-sql-server-management-studio.md), [Add Replica to Availability Group Wizard](use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md), or [Add Database to Availability Group Wizard](availability-group-add-database-to-group-wizard.md).</span></span>  
  
 <span data-ttu-id="22f6e-139">**Per preparare un database secondario**</span><span class="sxs-lookup"><span data-stu-id="22f6e-139">**To prepare a secondary database**</span></span>  
  
1.  <span data-ttu-id="22f6e-140">A meno che non si disponga già di un backup recente del database primario, creare un nuovo backup del database completo o differenziale.</span><span class="sxs-lookup"><span data-stu-id="22f6e-140">Unless you already have a recent database backup of the primary database, create a new full or differential database backup.</span></span> <span data-ttu-id="22f6e-141">Secondo la procedura consigliata, collocare il backup ed eventuali backup del log successivi nella condivisione di rete consigliata.</span><span class="sxs-lookup"><span data-stu-id="22f6e-141">As a best practice, place this backup and any subsequent log backups onto the recommended network share.</span></span>  
  
2.  <span data-ttu-id="22f6e-142">Creare almeno un nuovo backup del log del database primario.</span><span class="sxs-lookup"><span data-stu-id="22f6e-142">Create at least one new log backup of the primary database.</span></span>  
  
3.  <span data-ttu-id="22f6e-143">Nell'istanza del server che ospita la replica secondaria, ripristinare il backup completo del database primario (e facoltativamente un backup differenziale) seguito da eventuali backup del log successivi.</span><span class="sxs-lookup"><span data-stu-id="22f6e-143">On the server instance that hosts the secondary replica, restore the full database backup of the primary database (and optionally a differential backup) followed by any subsequent log backups.</span></span>  
  
     <span data-ttu-id="22f6e-144">Nella pagina **Opzioni di RESTORE DATABASE** selezionare **Lascia il database non operativo e non eseguire il rollback delle transazioni di cui non è stato eseguito il commit. I log delle transazioni aggiuntivi possono essere ripristinati. (RESTORE WITH NORECOVERY)**.</span><span class="sxs-lookup"><span data-stu-id="22f6e-144">On the **RESTORE DATABASEOptions** page, select **Leave the database non-operational, and do not roll back the uncommitted transactions. Additional transaction logs can be restored. (RESTORE WITH NORECOVERY)**.</span></span>  
  
     <span data-ttu-id="22f6e-145">Se i percorsi dei file del database primario e del database secondario sono diversi, ad esempio se il database primario si trova nell'unità "F:" ma nell'istanza del server che ospita la replica secondaria non è disponibile un'unità "F:", includere l'opzione MOVE nella clausola WITH.</span><span class="sxs-lookup"><span data-stu-id="22f6e-145">If the file paths of the primary database and the secondary database differ, for example, if the primary database is on drive 'F:' but the server instance that hosts the secondary replica lacks an F: drive, include the MOVE option in your WITH clause.</span></span>  
  
4.  <span data-ttu-id="22f6e-146">Per completare la configurazione del database secondario, è necessario creare un join del database secondario al gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="22f6e-146">To complete configuration of the secondary database, you need to join the secondary database to the availability group.</span></span> <span data-ttu-id="22f6e-147">Per altre informazioni, vedere [Creare un join di un database secondario a un gruppo di disponibilità &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="22f6e-147">For more information, [Join a Secondary Database to an Availability Group &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="22f6e-148"> Per informazioni sull'esecuzione di queste operazioni di backup e ripristino, vedere [Attività correlate a backup e ripristino](#RelatedTasks), più avanti in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="22f6e-148">For information about how to perform these backup and restore operations, see [Related Backup and Restore Tasks](#RelatedTasks), later in this section.</span></span>  
  
###  <a name="related-backup-and-restore-tasks"></a><a name="RelatedTasks"></a><span data-ttu-id="22f6e-149">Attività correlate a backup e ripristino</span><span class="sxs-lookup"><span data-stu-id="22f6e-149">Related Backup and Restore Tasks</span></span>  
 <span data-ttu-id="22f6e-150">**Per creare un backup del database**</span><span class="sxs-lookup"><span data-stu-id="22f6e-150">**To create a database backup**</span></span>  
  
-   [<span data-ttu-id="22f6e-151">Creazione di un backup completo del database &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="22f6e-151">Create a Full Database Backup &#40;SQL Server&#41;</span></span>](../../../relational-databases/backup-restore/create-a-full-database-backup-sql-server.md)  
  
-   [<span data-ttu-id="22f6e-152">Creare un backup differenziale del database &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="22f6e-152">Create a Differential Database Backup &#40;SQL Server&#41;</span></span>](../../../relational-databases/backup-restore/create-a-differential-database-backup-sql-server.md)  
  
 <span data-ttu-id="22f6e-153">**Per creare un backup del log**</span><span class="sxs-lookup"><span data-stu-id="22f6e-153">**To create a log backup**</span></span>  
  
-   [<span data-ttu-id="22f6e-154">Eseguire il backup di un log delle transazioni &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="22f6e-154">Back Up a Transaction Log &#40;SQL Server&#41;</span></span>](../../../relational-databases/backup-restore/back-up-a-transaction-log-sql-server.md)  
  
 <span data-ttu-id="22f6e-155">**Per ripristinare i backup**</span><span class="sxs-lookup"><span data-stu-id="22f6e-155">**To restore backups**</span></span>  
  
-   [<span data-ttu-id="22f6e-156">Ripristinare un backup del database &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="22f6e-156">Restore a Database Backup &#40;SQL Server Management Studio&#41;</span></span>](../../../relational-databases/backup-restore/restore-a-database-backup-using-ssms.md)  
  
-   [<span data-ttu-id="22f6e-157">Ripristinare un backup differenziale del database &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="22f6e-157">Restore a Differential Database Backup &#40;SQL Server&#41;</span></span>](../../../relational-databases/backup-restore/restore-a-differential-database-backup-sql-server.md)  
  
-   [<span data-ttu-id="22f6e-158">Ripristinare un backup del log delle transazioni &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="22f6e-158">Restore a Transaction Log Backup &#40;SQL Server&#41;</span></span>](../../../relational-databases/backup-restore/restore-a-transaction-log-backup-sql-server.md)  
  
-   [<span data-ttu-id="22f6e-159">Ripristinare un database in una nuova posizione &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="22f6e-159">Restore a Database to a New Location &#40;SQL Server&#41;</span></span>](../../../relational-databases/backup-restore/restore-a-database-to-a-new-location-sql-server.md)  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="22f6e-160">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="22f6e-160">Using Transact-SQL</span></span>  
 <span data-ttu-id="22f6e-161">**Per preparare un database secondario**</span><span class="sxs-lookup"><span data-stu-id="22f6e-161">**To prepare a secondary database**</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="22f6e-162">Per un esempio di questa procedura, vedere [Esempio (Transact-SQL)](#ExampleTsql), più indietro in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="22f6e-162">For an example of this procedure, see [Example (Transact-SQL)](#ExampleTsql), earlier in this topic.</span></span>  
  
1.  <span data-ttu-id="22f6e-163">A meno che si disponga di un backup completo recente del database primario, connettersi all'istanza del server che ospita la replica primaria e creare un backup completo del database.</span><span class="sxs-lookup"><span data-stu-id="22f6e-163">Unless you have a recent full backup of the primary database, connect to the server instance that hosts the primary replica and create a full database backup.</span></span> <span data-ttu-id="22f6e-164">Secondo la procedura consigliata, collocare il backup ed eventuali backup del log successivi nella condivisione di rete consigliata.</span><span class="sxs-lookup"><span data-stu-id="22f6e-164">As a best practice, place this backup and any subsequent log backups onto the recommended network share.</span></span>  
  
2.  <span data-ttu-id="22f6e-165">Nell'istanza del server che ospita la replica secondaria, ripristinare il backup completo del database primario (e facoltativamente un backup differenziale) seguito da tutti i backup del log successivi.</span><span class="sxs-lookup"><span data-stu-id="22f6e-165">On the server instance that hosts the secondary replica, restore the full database backup of the primary database (and optionally a differential backup) followed by all subsequent log backups.</span></span> <span data-ttu-id="22f6e-166">Utilizzare WITH NORECOVERY per ogni operazione di ripristino.</span><span class="sxs-lookup"><span data-stu-id="22f6e-166">Use WITH NORECOVERY for every restore operation.</span></span>  
  
     <span data-ttu-id="22f6e-167">Se i percorsi dei file del database primario e del database secondario sono diversi, ad esempio se il database primario si trova nell'unità "F:" ma nell'istanza del server che ospita la replica secondaria non è disponibile un'unità "F:", includere l'opzione MOVE nella clausola WITH.</span><span class="sxs-lookup"><span data-stu-id="22f6e-167">If the file paths of the primary database and the secondary database differ, for example, if the primary database is on drive 'F:' but the server instance that hosts the secondary replica lacks an F: drive, include the MOVE option in your WITH clause.</span></span>  
  
3.  <span data-ttu-id="22f6e-168">Se sono stati eseguiti altri backup del log sul database primario dopo il backup del log richiesto, è inoltre necessario copiarli nell'istanza del server che ospita la replica secondaria e applicare ognuno di questi backup del log al database secondario, a partire dal meno recente e utilizzando sempre RESTORE WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="22f6e-168">If any log backups have been taken on the primary database since the required log backup, you must also copy these to the server instance that hosts the secondary replica and apply each of those log backups to the secondary database, starting with the earliest and always using RESTORE WITH NORECOVERY.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="22f6e-169">Il backup del log non esiste se il database primario è stato appena creato e non è ancora stato eseguito alcun backup del log oppure se il modello di recupero è stato appena modificato da SIMPLE a FULL.</span><span class="sxs-lookup"><span data-stu-id="22f6e-169">A log backup would not exist if the primary database has just been created and no log backup has been taken yet or if the recovery model has just been changed from simple to full.</span></span>  
  
4.  <span data-ttu-id="22f6e-170">Per completare la configurazione del database secondario, è necessario creare un join del database secondario al gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="22f6e-170">To complete configuration of the secondary database, you need to join the secondary database to the availability group.</span></span> <span data-ttu-id="22f6e-171">Per altre informazioni, vedere [Creare un join di un database secondario a un gruppo di disponibilità &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="22f6e-171">For more information, [Join a Secondary Database to an Availability Group &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="22f6e-172"> Per informazioni sull'esecuzione di queste operazioni di backup e ripristino, vedere [Attività correlate a backup e ripristino](#RelatedTasks), più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="22f6e-172">For information about how to perform these backup and restore operations, see [Related Backup and Restore Tasks](#RelatedTasks), later in this topic.</span></span>  
  
###  <a name="transact-sql-example"></a><a name="ExampleTsql"></a><span data-ttu-id="22f6e-173">Esempio Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="22f6e-173">Transact-SQL Example</span></span>  
 <span data-ttu-id="22f6e-174">Nell'esempio seguente viene preparato un database secondario.</span><span class="sxs-lookup"><span data-stu-id="22f6e-174">The following example prepares a secondary database.</span></span> <span data-ttu-id="22f6e-175">Nell'esempio viene utilizzato il database di esempio [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] in cui, per impostazione predefinita, viene utilizzato il modello di recupero con registrazione minima.</span><span class="sxs-lookup"><span data-stu-id="22f6e-175">This example uses the [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] sample database, which uses the simple recovery model by default.</span></span>  
  
1.  <span data-ttu-id="22f6e-176">Per utilizzare il database [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] , modificarlo in modo da utilizzare il modello di recupero con registrazione completa:</span><span class="sxs-lookup"><span data-stu-id="22f6e-176">To use the [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] database, modify it to use the full recovery model:</span></span>  
  
    ```sql
    USE master;  
    GO  
    ALTER DATABASE MyDB1   
    SET RECOVERY FULL;  
    GO  
    ```  
  
2.  <span data-ttu-id="22f6e-177">Dopo aver modificato il modello di recupero del database da SIMPLE a FULL, creare un backup completo da utilizzare per la creazione del database secondario.</span><span class="sxs-lookup"><span data-stu-id="22f6e-177">After modifying the recovery model of the database from SIMPLE to FULL, create a full backup, which can be used to create the secondary database.</span></span> <span data-ttu-id="22f6e-178">Dopo la modifica del modello di recupero, è consigliabile selezionare l'opzione WITH FORMAT per creare un nuovo set di supporti.</span><span class="sxs-lookup"><span data-stu-id="22f6e-178">Because the recovery model has just been changed, the WITH FORMAT option is specified to create a new media set.</span></span> <span data-ttu-id="22f6e-179">L'operazione risulta utile per separare i backup eseguiti durante l'utilizzo del modello di recupero con registrazione completa dai backup precedenti eseguiti durante l'utilizzo del modello di recupero con registrazione semplice.</span><span class="sxs-lookup"><span data-stu-id="22f6e-179">This is useful to separate the backups under the full recovery model from any previous backups made under the simple recovery model.</span></span> <span data-ttu-id="22f6e-180">Ai fini di questo esempio, il file di backup (C:\\[!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)].bak) verrà creato nella stessa unità del database.</span><span class="sxs-lookup"><span data-stu-id="22f6e-180">For the purpose of this example, the backup file (C:\\[!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)].bak) is created on the same drive as the database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="22f6e-181">Nel caso di un database di produzione, è consigliabile eseguire sempre il backup in un dispositivo distinto.</span><span class="sxs-lookup"><span data-stu-id="22f6e-181">For a production database, you should always back up to a separate device.</span></span>  
  
     <span data-ttu-id="22f6e-182">Nell'istanza del server che ospita la replica primaria (`INSTANCE01`), creare un backup completo del database primario, nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="22f6e-182">On the server instance that hosts the primary replica (`INSTANCE01`), create a full backup of the primary database as follows:</span></span>  
  
    ```sql
    BACKUP DATABASE MyDB1   
        TO DISK = 'C:\MyDB1.bak'   
        WITH FORMAT  
    GO  
    ```  
  
3.  <span data-ttu-id="22f6e-183">Copiare il backup completo nell'istanza del server in cui è ospitata la replica secondaria.</span><span class="sxs-lookup"><span data-stu-id="22f6e-183">Copy the full backup to the server instance that hosts the secondary replica.</span></span>  
  
4.  <span data-ttu-id="22f6e-184">Ripristinare il backup completo nell'istanza del server che ospita la replica secondaria, utilizzando RESTORE WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="22f6e-184">Restore the full backup, using RESTORE WITH NORECOVERY, onto the server instance that hosts the secondary replica.</span></span> <span data-ttu-id="22f6e-185">Il comando di ripristino dipende dal fatto che i percorsi del database primario e di quelli secondari siano identici.</span><span class="sxs-lookup"><span data-stu-id="22f6e-185">The restore command depends on whether the paths of primary and secondary databases are identical.</span></span>  
  
    -   <span data-ttu-id="22f6e-186">**Se i percorsi sono identici:**</span><span class="sxs-lookup"><span data-stu-id="22f6e-186">**If the paths are identical:**</span></span>  
  
         <span data-ttu-id="22f6e-187">Nel computer che ospita la replica secondaria, ripristinare il backup completo nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="22f6e-187">On the computer that hosts the secondary replica, restore the full backup as follows:</span></span>  
  
        ```sql
        RESTORE DATABASE MyDB1   
            FROM DISK = 'C:\MyDB1.bak'   
            WITH NORECOVERY  
        GO  
        ```  
  
    -   <span data-ttu-id="22f6e-188">**Se i percorsi sono diversi:**</span><span class="sxs-lookup"><span data-stu-id="22f6e-188">**If the paths differ:**</span></span>  
  
         <span data-ttu-id="22f6e-189">Se il percorso del database secondario è diverso dal percorso del database primario, ad esempio perché le lettere di unità non corrispondono, per creare il database secondario è necessario che l'operazione di ripristino includa una clausola MOVE.</span><span class="sxs-lookup"><span data-stu-id="22f6e-189">If the path of the secondary database differs from the path of the primary database (for instance, their drive letters differ), creating the secondary database requires that the restore operation include a MOVE clause.</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="22f6e-190">Se il nome di percorso del database primario è diverso dal nome di percorso dei database secondari, non è possibile aggiungere un file.</span><span class="sxs-lookup"><span data-stu-id="22f6e-190">If the path names of the primary and secondary databases differ, you cannot add a file.</span></span> <span data-ttu-id="22f6e-191">Alla ricezione del log relativo all'operazione di aggiunta del file, l'istanza del server della replica secondaria tenta infatti di salvare il nuovo file nello stesso percorso utilizzato dal database primario.</span><span class="sxs-lookup"><span data-stu-id="22f6e-191">This is because on receiving the log for the add file operation, the server instance of the secondary replica attempts to place the new file in the same path as used by the primary database.</span></span>  
  
         <span data-ttu-id="22f6e-192">Ad esempio, tramite il comando seguente viene ripristinato un backup di un database primario che risiede nella directory di dati dell'istanza predefinita di [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], C:\Programmi\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA.</span><span class="sxs-lookup"><span data-stu-id="22f6e-192">For example, the following command restores a backup of a primary database that resides in the data directory of the default instance of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA.</span></span> <span data-ttu-id="22f6e-193">L'operazione Restore database deve spostare il database nella directory dei dati di un'istanza remota di [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] denominata (*AlwaysOn1*) che ospita la replica secondaria in un altro nodo del cluster.</span><span class="sxs-lookup"><span data-stu-id="22f6e-193">The restore database operation must move the database to the data directory of a remote instance of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] named  (*AlwaysOn1*), which hosts the secondary replica on another cluster node.</span></span> <span data-ttu-id="22f6e-194">In tale posizione, i file di dati e di log vengono ripristinati nel percorso *C:\Programmi\Microsoft SQL Server\MSSQL12. Directory ALWAYSON1\MSSQL\DATA* .</span><span class="sxs-lookup"><span data-stu-id="22f6e-194">There, the data and log files are restored to the *C:\Program Files\Microsoft SQL Server\MSSQL12.ALWAYSON1\MSSQL\DATA* directory .</span></span> <span data-ttu-id="22f6e-195">Per l'operazione di ripristino viene utilizzata l'opzione WITH NORECOVERY per lasciare il database secondario nel database di ripristino.</span><span class="sxs-lookup"><span data-stu-id="22f6e-195">The restore operation uses WITH NORECOVERY, to leave the secondary database in the restoring database.</span></span>  
  
        ```sql
        RESTORE DATABASE MyDB1  
          FROM DISK='C:\MyDB1.bak'  
         WITH NORECOVERY,   
            MOVE 'MyDB1_Data' TO   
             'C:\Program Files\Microsoft SQL Server\MSSQL12.ALWAYSON1\MSSQL\DATA\MyDB1_Data.mdf',   
            MOVE 'MyDB1_Log' TO  
             'C:\Program Files\Microsoft SQL Server\MSSQL12.ALWAYSON1\MSSQL\DATA\MyDB1_Data.ldf';  
        GO  
        ```  
  
5.  <span data-ttu-id="22f6e-196">Dopo il ripristino del backup completo, è necessario creare un backup del log nel database primario.</span><span class="sxs-lookup"><span data-stu-id="22f6e-196">After you restore the full backup, you must create a log backup on the primary database.</span></span> <span data-ttu-id="22f6e-197">Ad esempio, l'istruzione [!INCLUDE[tsql](../../../includes/tsql-md.md)] seguente esegue il backup del log in un file di backup denominato *E:\MyDB1_log.bak*:</span><span class="sxs-lookup"><span data-stu-id="22f6e-197">For example, the following [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement backs up the log to the a backup file named *E:\MyDB1_log.bak*:</span></span>  
  
    ```sql
    BACKUP LOG MyDB1   
      TO DISK = 'E:\MyDB1_log.bak'   
    GO  
    ```  
  
6.  <span data-ttu-id="22f6e-198">Prima di creare il join del database alla replica secondaria, è necessario applicare il backup del log richiesto ed eventuali backup del log successivi.</span><span class="sxs-lookup"><span data-stu-id="22f6e-198">Before you can join the database to the secondary replica, you must apply the required log backup (and any subsequent log backups).</span></span>  
  
     <span data-ttu-id="22f6e-199">Ad esempio, l'istruzione [!INCLUDE[tsql](../../../includes/tsql-md.md)] seguente ripristina il primo log da *C:\MyDB1.bak*:</span><span class="sxs-lookup"><span data-stu-id="22f6e-199">For example, the following [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement restores the first log from *C:\MyDB1.bak*:</span></span>  
  
    ```sql
    RESTORE LOG MyDB1   
      FROM DISK = 'E:\MyDB1_log.bak'   
        WITH FILE=1, NORECOVERY  
    GO  
    ```  
  
7.  <span data-ttu-id="22f6e-200">Se vengono eseguiti altri backup del log prima del join del database alla replica secondaria, è inoltre necessario ripristinare tutti questi backup, in sequenza, nell'istanza del server che ospita la replica secondaria utilizzando RESTORE WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="22f6e-200">If any additional log backups occur before the database joins the secondary replica, you must also restore all of those log backups, in sequence, to the server instance that hosts the secondary replica using RESTORE WITH NORECOVERY.</span></span>  
  
     <span data-ttu-id="22f6e-201">Ad esempio, l'istruzione [!INCLUDE[tsql](../../../includes/tsql-md.md)] seguente ripristina altri due log da *E:\MyDB1_log.bak*:</span><span class="sxs-lookup"><span data-stu-id="22f6e-201">For example, the following [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement restores two additional logs from *E:\MyDB1_log.bak*:</span></span>  
  
    ```sql
    RESTORE LOG MyDB1   
      FROM DISK = 'E:\MyDB1_log.bak'   
        WITH FILE=2, NORECOVERY  
    GO  
    RESTORE LOG MyDB1   
      FROM DISK = 'E:\MyDB1_log.bak'   
        WITH FILE=3, NORECOVERY  
    GO  
    ```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="22f6e-202">Uso di PowerShell</span><span class="sxs-lookup"><span data-stu-id="22f6e-202">Using PowerShell</span></span>  
 <span data-ttu-id="22f6e-203">**Per preparare un database secondario**</span><span class="sxs-lookup"><span data-stu-id="22f6e-203">**To prepare a secondary database**</span></span>  
  
1.  <span data-ttu-id="22f6e-204">Se è necessario creare un backup recente del database primario, spostarsi sulla directory (`cd`) dell'istanza del server che ospita la replica primaria.</span><span class="sxs-lookup"><span data-stu-id="22f6e-204">If you need to create a recent backup of the primary database, change directory (`cd`) to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="22f6e-205">Utilizzare il cmdlet `Backup-SqlDatabase` per creare ciascun backup.</span><span class="sxs-lookup"><span data-stu-id="22f6e-205">Use the `Backup-SqlDatabase` cmdlet to create each of the backups.</span></span>  
  
3.  <span data-ttu-id="22f6e-206">Impostare la directory (`cd`) sull'istanza del server in cui viene ospitata la replica secondaria.</span><span class="sxs-lookup"><span data-stu-id="22f6e-206">Change directory (`cd`) to the server instance that hosts the secondary replica.</span></span>  
  
4.  <span data-ttu-id="22f6e-207">Per ripristinare il database e i backup del log di ogni database primario, utilizzare il cmdlet `restore-SqlDatabase`, specificando il parametro di ripristino `NoRecovery`.</span><span class="sxs-lookup"><span data-stu-id="22f6e-207">To restore the database and log backups of each primary database, use the `restore-SqlDatabase` cmdlet, specifying the `NoRecovery` restore parameter.</span></span> <span data-ttu-id="22f6e-208">Se i percorsi di file differiscono tra i computer in cui sono ospitate la replica primaria e la replica secondaria di destinazione, usare anche il parametro di ripristino `RelocateFile`.</span><span class="sxs-lookup"><span data-stu-id="22f6e-208">If the file paths differ between the computers that host the primary replica and the target secondary replica, also use the `RelocateFile` restore parameter.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="22f6e-209">Per visualizzare la sintassi di un cmdlet, utilizzare il cmdlet `Get-Help` nell'ambiente [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="22f6e-209">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="22f6e-210">Per altre informazioni, vedere [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="22f6e-210">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
5.  <span data-ttu-id="22f6e-211">Per completare la configurazione del database secondario, è necessario creare un join dello stesso al gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="22f6e-211">To complete configuration of the secondary database, you need to join it to the availability group.</span></span> <span data-ttu-id="22f6e-212">Per altre informazioni, vedere [Creare un join di un database secondario a un gruppo di disponibilità &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="22f6e-212">For more information, [Join a Secondary Database to an Availability Group &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md).</span></span>  
  
 <span data-ttu-id="22f6e-213">**Per impostare e utilizzare il provider PowerShell per SQL Server**</span><span class="sxs-lookup"><span data-stu-id="22f6e-213">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="22f6e-214">Provider PowerShell per SQL Server</span><span class="sxs-lookup"><span data-stu-id="22f6e-214">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
###  <a name="sample-backup-and-restore-script-and-command"></a><a name="ExamplePSscript"></a><span data-ttu-id="22f6e-215">Script e comando di backup e ripristino di esempio</span><span class="sxs-lookup"><span data-stu-id="22f6e-215">Sample Backup and Restore Script and Command</span></span>  
 <span data-ttu-id="22f6e-216">Tramite i comandi di PowerShell riportati di seguito viene eseguito il backup completo di un database e del log delle transazioni in una condivisione di rete e vengono ripristinati i backup dalla condivisione.</span><span class="sxs-lookup"><span data-stu-id="22f6e-216">The following PowerShell commands back up a full database backup and transaction log to a network share and restore those backups from that share.</span></span> <span data-ttu-id="22f6e-217">In questo esempio si presuppone che il percorso del file in cui viene ripristinato il database corrisponda al percorso del file nel quale è stato eseguito il backup del database.</span><span class="sxs-lookup"><span data-stu-id="22f6e-217">This example assumes that the file path to which the database is restored is the same as the file path on which the database was backed up.</span></span>  
  
```powershell
# Create database backup  
Backup-SqlDatabase -Database "MyDB1" -BackupFile "\\share\backups\MyDB1.bak" -ServerInstance "SourceMachine\Instance"  
# Create log backup  
Backup-SqlDatabase -Database "MyDB1" -BackupAction "Log" -BackupFile "\\share\backups\MyDB1.trn" -ServerInstance "SourceMachine\Instance"  
# Restore database backup
Restore-SqlDatabase -Database "MyDB1" -BackupFile "\\share\backups\MyDB1.bak" -NoRecovery -ServerInstance "DestinationMachine\Instance"  
# Restore log backup
Restore-SqlDatabase -Database "MyDB1" -BackupFile "\\share\backups\MyDB1.trn" -RestoreAction "Log" -NoRecovery -ServerInstance "DestinationMachine\Instance"
```  
  
##  <a name="follow-up-after-preparing-a-secondary-database"></a><a name="FollowUp"></a> <span data-ttu-id="22f6e-218">Completamento: Dopo la preparazione di un database secondario</span><span class="sxs-lookup"><span data-stu-id="22f6e-218">Follow Up: After Preparing a Secondary Database</span></span>  
 <span data-ttu-id="22f6e-219">Per completare la configurazione del database secondario, creare un join del database appena ripristinato al gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="22f6e-219">To complete configuration of the secondary database, join the newly restored database to the availability group.</span></span> <span data-ttu-id="22f6e-220">Per altre informazioni, vedere [Creare un join di un database secondario a un gruppo di disponibilità &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="22f6e-220">For more information, see [Join a Secondary Database to an Availability Group &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22f6e-221">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="22f6e-221">See Also</span></span>  
 <span data-ttu-id="22f6e-222">[Panoramica di Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="22f6e-222">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="22f6e-223">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="22f6e-223">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="22f6e-224">[Argomenti dell'istruzione RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-arguments-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="22f6e-224">[RESTORE Arguments &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-arguments-transact-sql) </span></span>  
 <span data-ttu-id="22f6e-225">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="22f6e-225">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 [<span data-ttu-id="22f6e-226">Risolvere i problemi relativi a un'operazione di aggiunta file non riuscita &#40;Gruppi di disponibilità AlwaysOn&#41;</span><span class="sxs-lookup"><span data-stu-id="22f6e-226">Troubleshoot a Failed Add-File Operation &#40;AlwaysOn Availability Groups&#41;</span></span>](troubleshoot-a-failed-add-file-operation-always-on-availability-groups.md)  
