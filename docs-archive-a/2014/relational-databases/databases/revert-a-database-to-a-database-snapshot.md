---
title: Ripristinare un database a uno snapshot del database | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- database snapshots [SQL Server], reverting to
- reverting databases
ms.assetid: 8f74dd31-c9ca-4537-8760-0c7648f0787d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1c78da3d7c559309c0563760e7062f01cf784648
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627798"
---
# <a name="revert-a-database-to-a-database-snapshot"></a><span data-ttu-id="02138-102">Ripristinare un database a uno snapshot del database</span><span class="sxs-lookup"><span data-stu-id="02138-102">Revert a Database to a Database Snapshot</span></span>
  <span data-ttu-id="02138-103">Se i dati in un database online sono danneggiati, in alcuni casi il ripristino del database a un snapshot del database precedente alla data del danno può essere un'alternativa appropriata per ripristinare il database da un backup.</span><span class="sxs-lookup"><span data-stu-id="02138-103">If data in an online database becomes damaged, in some cases, reverting the database to a database snapshot that predates the damage might be an appropriate alternative to restoring the database from a backup.</span></span> <span data-ttu-id="02138-104">Il ripristino di un database può, ad esempio, risultare utile per annullare un errore grave dell'utente verificatosi di recente, come l'eliminazione di una tabella.</span><span class="sxs-lookup"><span data-stu-id="02138-104">For example, reverting a database might be useful for reverse a recent serious user error, such as a dropped table.</span></span> <span data-ttu-id="02138-105">Tutte le modifiche apportate dopo la creazione dello snapshot verranno tuttavia perse.</span><span class="sxs-lookup"><span data-stu-id="02138-105">However, all changes made after the snapshot was created are lost.</span></span>  
  
-   <span data-ttu-id="02138-106">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="02138-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="02138-107">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="02138-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="02138-108">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="02138-108">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="02138-109">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="02138-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="02138-110">**Per ripristinare un database a uno snapshot del database tramite:**  [Transact-SQL](#TsqlProcedure)</span><span class="sxs-lookup"><span data-stu-id="02138-110">**To Revert a Database to a Database Snapshot, using:**  [Transact-SQL](#TsqlProcedure)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="02138-111">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="02138-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="02138-112">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="02138-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="02138-113">Il ripristino da snapshot non è supportato nei casi seguenti:</span><span class="sxs-lookup"><span data-stu-id="02138-113">Reverting is unsupported under the following conditions:</span></span>  
  
-   <span data-ttu-id="02138-114">Nel database deve essere attualmente disponibile un solo snapshot del database in base al quale si prevede di effettuare il ripristino.</span><span class="sxs-lookup"><span data-stu-id="02138-114">The database must currently have only one database snapshot, to which you plan to revert.</span></span>  
  
-   <span data-ttu-id="02138-115">Nel database sono presenti filegroup di sola lettura o compressi.</span><span class="sxs-lookup"><span data-stu-id="02138-115">Any read-only or compressed filegroups exist in the database.</span></span>  
  
-   <span data-ttu-id="02138-116">Alcuni file sono attualmente offline ma erano online al momento della creazione dello snapshot.</span><span class="sxs-lookup"><span data-stu-id="02138-116">Any files are now offline but were online when the snapshot was created.</span></span>  
  
 <span data-ttu-id="02138-117">Prima di ripristinare un database, considerare le limitazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="02138-117">Before reverting a database, consider the following limitations:</span></span>  
  
-   <span data-ttu-id="02138-118">Non è previsto il ripristino per il recupero di supporti.</span><span class="sxs-lookup"><span data-stu-id="02138-118">Reverting is not intended for media recovery.</span></span> <span data-ttu-id="02138-119">.</span><span class="sxs-lookup"><span data-stu-id="02138-119">.</span></span> <span data-ttu-id="02138-120">Un snapshot del database è una copia incompleta dei file di database, pertanto se il database o lo snapshot del database è danneggiato, è probabile che il ripristino da uno snapshot risulti impossibile.</span><span class="sxs-lookup"><span data-stu-id="02138-120">A database snapshot is an incomplete copy of the database files, so if either the database or the database snapshot is corrupted, reverting from a snapshot is likely to be impossible.</span></span> <span data-ttu-id="02138-121">Anche quando possibile, è inoltre improbabile che il ripristino in caso di danneggiamento consenta di risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="02138-121">Furthermore, even when it is possible, reverting in the event of corruption is unlikely to correct the problem.</span></span> <span data-ttu-id="02138-122">Per proteggere un database è pertanto essenziale eseguire backup regolari e testare il piano di ripristino.</span><span class="sxs-lookup"><span data-stu-id="02138-122">Therefore, taking regular backups and testing your restore plan are essential to protect a database.</span></span> <span data-ttu-id="02138-123">Per altre informazioni, vedere [Backup e ripristino di database SQL Server](../backup-restore/back-up-and-restore-of-sql-server-databases.md).</span><span class="sxs-lookup"><span data-stu-id="02138-123">For more information, see [Back Up and Restore of SQL Server Databases](../backup-restore/back-up-and-restore-of-sql-server-databases.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="02138-124">Se è necessario essere in grado di ripristinare il database di origine al punto nel tempo in cui è stato creato uno snapshot del database, utilizzare il modello di recupero completo e implementare criteri di backup che consentano di eseguire tale operazione.</span><span class="sxs-lookup"><span data-stu-id="02138-124">If you need to be able to restore the source database to the point in time at which you created a database snapshot, use the full recovery model and implement a backup policy that enables you to do that.</span></span>  
  
-   <span data-ttu-id="02138-125">Il database di origine originale viene sovrascritto dal database ripristinato, pertanto qualsiasi aggiornamento apportato al database dalla creazione dello snapshot verrà perso.</span><span class="sxs-lookup"><span data-stu-id="02138-125">The original source database is overwritten by the reverted database, so any updates to the database since the snapshot's creation are lost.</span></span>  
  
-   <span data-ttu-id="02138-126">Tramite l'operazione di ripristino viene inoltre sovrascritto il file di log precedente e viene ricompilato il log.</span><span class="sxs-lookup"><span data-stu-id="02138-126">The revert operation also overwrites the old log file and rebuilds the log.</span></span> <span data-ttu-id="02138-127">Di conseguenza, non è possibile eseguire il rollforward del database ripristinato al punto in cui si è verificato l'errore dell'utente.</span><span class="sxs-lookup"><span data-stu-id="02138-127">Consequently, you cannot roll the reverted database forward to the point of user error.</span></span> <span data-ttu-id="02138-128">Si consiglia pertanto di eseguire il backup del log prima di ripristinare un database.</span><span class="sxs-lookup"><span data-stu-id="02138-128">Therefore, we recommend that you back up the log before reverting a database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="02138-129">Sebbene non sia possibile ripristinare il log originale per eseguire il rollforward del database, le informazioni del file di log originale saranno utili per ricostruire i dati persi.</span><span class="sxs-lookup"><span data-stu-id="02138-129">Although you cannot restore the original log to roll forward the database, the information in the original log file can be useful for reconstructing lost data.</span></span>  
  
-   <span data-ttu-id="02138-130">Tramite il ripristino viene interrotta la catena di backup del log.</span><span class="sxs-lookup"><span data-stu-id="02138-130">Reverting breaks the log backup chain.</span></span> <span data-ttu-id="02138-131">Prima di eseguire backup del log del database ripristinato, è pertanto necessario eseguire un backup completo del database o il backup del file.</span><span class="sxs-lookup"><span data-stu-id="02138-131">Therefore, before you can take log backups of the reverted database, you must first take a full database backup or file backup.</span></span> <span data-ttu-id="02138-132">È consigliabile eseguire un backup completo del database.</span><span class="sxs-lookup"><span data-stu-id="02138-132">We recommend a full database backup.</span></span>  
  
-   <span data-ttu-id="02138-133">Durante un'operazione di ripristino, sia lo snapshot che il database di origine non sono disponibili.</span><span class="sxs-lookup"><span data-stu-id="02138-133">During a revert operation, both the snapshot and the source database are unavailable.</span></span> <span data-ttu-id="02138-134">Entrambi sono contrassegnati come in fase di ripristino.</span><span class="sxs-lookup"><span data-stu-id="02138-134">The source database and snapshot are both marked "In restore."</span></span> <span data-ttu-id="02138-135">Se si verifica un errore durante l'operazione di ripristino, al nuovo avvio del database verrà eseguito un tentativo di completamento dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="02138-135">If an error occurs during the revert operation, when the database starts up again, the revert operation will try to finish reverting.</span></span>  
  
-   <span data-ttu-id="02138-136">I metadati di un database ripristinato corrispondono a quelli del database al momento dello snapshot.</span><span class="sxs-lookup"><span data-stu-id="02138-136">The metadata of a reverted database is the same as the metadata at the time of the snapshot.</span></span>  
  
-   <span data-ttu-id="02138-137">Il ripristino causa l'eliminazione di tutti i cataloghi full-text.</span><span class="sxs-lookup"><span data-stu-id="02138-137">Reverting drops all the full-text catalogs.</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="02138-138">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="02138-138">Prerequisites</span></span>  
 <span data-ttu-id="02138-139">Assicurarsi che il database di origine e lo snapshot del database soddisfino i prerequisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="02138-139">Ensure that the source database and database snapshot meet the following prerequisites:</span></span>  
  
-   <span data-ttu-id="02138-140">Verificare che il database non sia stato danneggiato.</span><span class="sxs-lookup"><span data-stu-id="02138-140">Verify that the database has not become corrupted.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="02138-141">Se il database è stato danneggiato, sarà necessario ripristinarlo dai backup.</span><span class="sxs-lookup"><span data-stu-id="02138-141">If the database has been corrupted, you will need to restore it from backups.</span></span> <span data-ttu-id="02138-142">Per altre informazioni, vedere [Ripristini di database completi &#40;modello di recupero con registrazione minima&#41;](../backup-restore/complete-database-restores-simple-recovery-model.md) o [Ripristini di database completi &#40;modello di recupero con registrazione completa &#41;](../backup-restore/complete-database-restores-full-recovery-model.md).</span><span class="sxs-lookup"><span data-stu-id="02138-142">For more information, see [Complete Database Restores &#40;Simple Recovery Model&#41;](../backup-restore/complete-database-restores-simple-recovery-model.md) or [Complete Database Restores &#40;Full Recovery Model&#41;](../backup-restore/complete-database-restores-full-recovery-model.md).</span></span>  
  
-   <span data-ttu-id="02138-143">Identificare un recente snapshot creato prima dell'errore.</span><span class="sxs-lookup"><span data-stu-id="02138-143">Identify a recent snapshot that was created before the error.</span></span> <span data-ttu-id="02138-144">Per altre informazioni, vedere [Visualizzare uno snapshot del database &#40;SQL Server&#41;](view-a-database-snapshot-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="02138-144">For more information, see [View a Database Snapshot &#40;SQL Server&#41;](view-a-database-snapshot-sql-server.md).</span></span>  
  
-   <span data-ttu-id="02138-145">Eliminare qualsiasi altro snapshot del database attualmente presente nel database.</span><span class="sxs-lookup"><span data-stu-id="02138-145">Drop any other snapshots that currently exist on the database.</span></span> <span data-ttu-id="02138-146">Per altre informazioni, vedere [Eliminare uno snapshot del database &#40;Transact-SQL&#41;](drop-a-database-snapshot-transact-sql.md)o a un'istanza diversa.</span><span class="sxs-lookup"><span data-stu-id="02138-146">For more information, see [Drop a Database Snapshot &#40;Transact-SQL&#41;](drop-a-database-snapshot-transact-sql.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="02138-147">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="02138-147">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="02138-148">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="02138-148">Permissions</span></span>  
 <span data-ttu-id="02138-149">Qualsiasi utente con autorizzazioni RESTORE DATABASE sul database di origine può ripristinarne lo stato corrispondente al momento in cui è stato creato lo snapshot.</span><span class="sxs-lookup"><span data-stu-id="02138-149">Any user who has RESTORE DATABASE permissions on the source database can revert it to its state when a database snapshot was created.</span></span>  
  
##  <a name="how-to-revert-a-database-to-a-database-snapshot-using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="02138-150">Come ripristinare un database a uno snapshot del database (tramite Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="02138-150">How to Revert a Database to a Database Snapshot (Using Transact-SQL)</span></span>  
 <span data-ttu-id="02138-151">**Per ripristinare un database a uno snapshot del database**</span><span class="sxs-lookup"><span data-stu-id="02138-151">**To revert a database to a database snapshot**</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="02138-152">Per un esempio di questa procedura, vedere [Esempi (Transact-SQL)](#TsqlExample)più avanti in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="02138-152">For an example of this procedure, see [Examples (Transact-SQL)](#TsqlExample), later in this section.</span></span>  
  
1.  <span data-ttu-id="02138-153">Individuare lo snapshot del database a cui ripristinare il database.</span><span class="sxs-lookup"><span data-stu-id="02138-153">Identify the database snapshot to which you want to revert the database.</span></span> <span data-ttu-id="02138-154">È possibile visualizzare gli snapshot di un database in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] . Vedere [Visualizzare uno snapshot del database &#40;SQL Server&#41;](view-a-database-snapshot-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="02138-154">You can view the snapshots on a database in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] (see [View a Database Snapshot &#40;SQL Server&#41;](view-a-database-snapshot-sql-server.md)).</span></span> <span data-ttu-id="02138-155">È anche possibile trovare il database di origine di una vista dalla colonna **source_database_id** della vista del catalogo [sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="02138-155">Also, you can identify the source database of a view from the **source_database_id** column of the [sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) catalog view.</span></span>  
  
2.  <span data-ttu-id="02138-156">Eliminare eventuali altri snapshot del database.</span><span class="sxs-lookup"><span data-stu-id="02138-156">Drop any other database snapshots.</span></span>  
  
     <span data-ttu-id="02138-157">Per informazioni sull'eliminazione di snapshot, vedere [Eliminare uno snapshot del database &#40;Transact-SQL&#41;](drop-a-database-snapshot-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="02138-157">For information on dropping snapshots, see [Drop a Database Snapshot &#40;Transact-SQL&#41;](drop-a-database-snapshot-transact-sql.md).</span></span> <span data-ttu-id="02138-158">Se nel database viene utilizzato il modello di recupero con registrazione completa, prima del ripristino è necessario eseguire il backup del log.</span><span class="sxs-lookup"><span data-stu-id="02138-158">If the database uses the full recovery model, before reverting, you should back up the log.</span></span> <span data-ttu-id="02138-159">Per altre informazioni, vedere [Eseguire il backup di un log delle transazioni &#40;SQL Server&#41;](../backup-restore/back-up-a-transaction-log-sql-server.md) oppure [Eseguire il backup del log delle transazioni quando il database è danneggiato &#40;SQL Server&#41;](../backup-restore/back-up-the-transaction-log-when-the-database-is-damaged-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="02138-159">For more information, see [Back Up a Transaction Log &#40;SQL Server&#41;](../backup-restore/back-up-a-transaction-log-sql-server.md) or [Back Up the Transaction Log When the Database Is Damaged &#40;SQL Server&#41;](../backup-restore/back-up-the-transaction-log-when-the-database-is-damaged-sql-server.md).</span></span>  
  
3.  <span data-ttu-id="02138-160">Eseguire l'operazione di ripristino.</span><span class="sxs-lookup"><span data-stu-id="02138-160">Perform the revert operation.</span></span>  
  
     <span data-ttu-id="02138-161">Per un'operazione di ripristino è necessario disporre delle autorizzazioni RESTORE DATABASE nel database di origine.</span><span class="sxs-lookup"><span data-stu-id="02138-161">A revert operation requires RESTORE DATABASE permissions on the source database.</span></span> <span data-ttu-id="02138-162">Utilizzare quindi l'istruzione Transact-SQL per ripristinare il database:</span><span class="sxs-lookup"><span data-stu-id="02138-162">To revert the database, use the following Transact-SQL statement:</span></span>  
  
     <span data-ttu-id="02138-163">RESTORE DATABASE *nome_database* FROM DATABASE_SNAPSHOT **=** _nome_snapshot_database_</span><span class="sxs-lookup"><span data-stu-id="02138-163">RESTORE DATABASE *database_name* FROM DATABASE_SNAPSHOT **=**_database_snapshot_name_</span></span>  
  
     <span data-ttu-id="02138-164">dove *nome_database* è il database di origine e *nome_snapshot_database* è il nome dello snapshot con cui ripristinare il database.</span><span class="sxs-lookup"><span data-stu-id="02138-164">Where *database_name* is the source database and *database_snapshot_name* is the name of the snapshot to which you want to revert the database.</span></span> <span data-ttu-id="02138-165">Si noti che in questa istruzione è necessario specificare un nome di snapshot anziché un dispositivo di backup.</span><span class="sxs-lookup"><span data-stu-id="02138-165">Notice that in this statement, you must specify a snapshot name rather than a backup device.</span></span>  
  
     <span data-ttu-id="02138-166">Per altre informazioni, vedere [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="02138-166">For more information, see [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="02138-167">Durante l'operazione di ripristino sia lo snapshot che il database di origine risultano indisponibili</span><span class="sxs-lookup"><span data-stu-id="02138-167">During the revert operation, both the snapshot and the source database are unavailable.</span></span> <span data-ttu-id="02138-168">e sono contrassegnati come in fase di ripristino.</span><span class="sxs-lookup"><span data-stu-id="02138-168">The source database and snapshot are both marked as "In restore."</span></span> <span data-ttu-id="02138-169">In caso di errori durante il ripristino, al riavvio del database verrà eseguito un tentativo di completamento dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="02138-169">If an error occurs during the revert operation, it will try to finish reverting when the database starts up again.</span></span>  
  
4.  <span data-ttu-id="02138-170">Se il proprietario del database è cambiato dalla creazione dello snapshot, è opportuno aggiornare il proprietario del database ripristinato.</span><span class="sxs-lookup"><span data-stu-id="02138-170">If the database owner changed since creation of the database snapshot, you may want to update the database owner of the reverted database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="02138-171">Per il database ripristinato vengono mantenute le autorizzazioni e la configurazione dello snapshot, ad esempio il proprietario del database e il modello di recupero.</span><span class="sxs-lookup"><span data-stu-id="02138-171">The reverted database retains the permissions and configuration (such as database owner and recovery model) of the database snapshot.</span></span>  
  
5.  <span data-ttu-id="02138-172">Avviare il database.</span><span class="sxs-lookup"><span data-stu-id="02138-172">Start the database.</span></span>  
  
6.  <span data-ttu-id="02138-173">Facoltativamente, eseguire il backup del database ripristinato, in particolare se viene utilizzato il modello di recupero con registrazione completa o con registrazione minima delle operazioni bulk.</span><span class="sxs-lookup"><span data-stu-id="02138-173">Optionally, back up the reverted database, especially if it uses the full (or bulk-logged) recovery model.</span></span> <span data-ttu-id="02138-174">Per eseguire il backup di un database, vedere [Creare un backup completo del database &#40;SQL Server&#41;](../backup-restore/create-a-full-database-backup-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="02138-174">To back up a database, see [Create a Full Database Backup &#40;SQL Server&#41;](../backup-restore/create-a-full-database-backup-sql-server.md).</span></span>  
  
###  <a name="examples-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="02138-175">Esempi (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="02138-175">Examples (Transact-SQL)</span></span>  
 <span data-ttu-id="02138-176">In questa sezione sono inclusi i seguenti esempi di ripristino di un database a uno snapshot del database:</span><span class="sxs-lookup"><span data-stu-id="02138-176">This section contains the following examples of reverting a database to a database snapshot:</span></span>  
  
-   <span data-ttu-id="02138-177">R.</span><span class="sxs-lookup"><span data-stu-id="02138-177">A.</span></span> [<span data-ttu-id="02138-178">Ripristino di uno snapshot nel database AdventureWorks</span><span class="sxs-lookup"><span data-stu-id="02138-178">Reverting a snapshot on the AdventureWorks database</span></span>](#Reverting_AW)  
  
-   <span data-ttu-id="02138-179">B.</span><span class="sxs-lookup"><span data-stu-id="02138-179">B.</span></span> [<span data-ttu-id="02138-180">Ripristino di uno snapshot del database Sales</span><span class="sxs-lookup"><span data-stu-id="02138-180">Reverting a snapshot on the Sales database</span></span>](#Reverting_Sales)  
  
####  <a name="a-reverting-a-snapshot-on-the-adventureworks-database"></a><a name="Reverting_AW"></a> <span data-ttu-id="02138-181">A.</span><span class="sxs-lookup"><span data-stu-id="02138-181">A.</span></span> <span data-ttu-id="02138-182">Ripristino di uno snapshot nel database AdventureWorks</span><span class="sxs-lookup"><span data-stu-id="02138-182">Reverting a snapshot on the AdventureWorks database</span></span>  
 <span data-ttu-id="02138-183">Nell'esempio si presuppone che per il database [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] esista un solo snapshot.</span><span class="sxs-lookup"><span data-stu-id="02138-183">This example assumes that only one snapshot currently exists on the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span> <span data-ttu-id="02138-184">Per l'esempio in cui viene creato lo snapshot usato per il ripristino, vedere [Creare uno snapshot del database &#40;Transact-SQL&#41;](create-a-database-snapshot-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="02138-184">For the example that creates the snapshot to which the database is reverted here, see [Create a Database Snapshot &#40;Transact-SQL&#41;](create-a-database-snapshot-transact-sql.md).</span></span>  
  
```  
USE master;  
-- Reverting AdventureWorks to AdventureWorks_dbss1800  
RESTORE DATABASE AdventureWorks from   
DATABASE_SNAPSHOT = 'AdventureWorks_dbss1800';  
GO  
```  
  
####  <a name="b-reverting-a-snapshot-on-the-sales-database"></a><a name="Reverting_Sales"></a> <span data-ttu-id="02138-185">B.</span><span class="sxs-lookup"><span data-stu-id="02138-185">B.</span></span> <span data-ttu-id="02138-186">Ripristino di uno snapshot del database Sales</span><span class="sxs-lookup"><span data-stu-id="02138-186">Reverting a snapshot on the Sales database</span></span>  
 <span data-ttu-id="02138-187">In questo esempio si suppone che esistano attualmente due snapshot del database **Sales** : **sales_snapshot0600** e **sales_snapshot1200**.</span><span class="sxs-lookup"><span data-stu-id="02138-187">This example assumes that two snapshots currently exist on the **Sales** database: **sales_snapshot0600** and **sales_snapshot1200**.</span></span> <span data-ttu-id="02138-188">Nell'esempio viene eliminato lo snapshot meno recente e il database viene ripristinato in base allo snapshot più recente.</span><span class="sxs-lookup"><span data-stu-id="02138-188">The example deletes the older of the snapshots and reverts the database to the more recent snapshot.</span></span>  
  
 <span data-ttu-id="02138-189">Per il codice di creazione del database di esempio e degli snapshot su cui si basa questo esempio, vedere:</span><span class="sxs-lookup"><span data-stu-id="02138-189">For the code for creating the sample database and snapshots on which this example depends, see:</span></span>  
  
-   <span data-ttu-id="02138-190">Per il database **Sales** e lo snapshot **sales_snapshot0600** vedere "Creazione di un database con filegroup" e "Creazione di uno snapshot del database" in [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="02138-190">For the **Sales** database and the **sales_snapshot0600** snapshot, see "Creating a database with filegroups" and "Creating a database snapshot" in [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql).</span></span>  
  
-   <span data-ttu-id="02138-191">Per il database **sales_snapshot1200** , vedere "Creazione di uno snapshot del database Sales" in [Creare uno snapshot del database &#40;Transact-SQL&#41;](create-a-database-snapshot-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="02138-191">For the **sales_snapshot1200** snapshot, see "Creating a snapshot on the Sales database" in [Create a Database Snapshot &#40;Transact-SQL&#41;](create-a-database-snapshot-transact-sql.md).</span></span>  
  
```  
--Test to see if sales_snapshot0600 exists and if it   
-- does, delete it.  
IF EXISTS (SELECT dbid FROM sys.databases  
    WHERE NAME='sales_snapshot0600')  
    DROP DATABASE SalesSnapshot0600;  
GO  
-- Reverting Sales to sales_snapshot1200  
USE master;  
RESTORE DATABASE Sales FROM DATABASE_SNAPSHOT = 'sales_snapshot1200';  
GO  
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="02138-192">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="02138-192">Related Tasks</span></span>  
  
-   [<span data-ttu-id="02138-193">Creare uno snapshot del database &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="02138-193">Create a Database Snapshot &#40;Transact-SQL&#41;</span></span>](create-a-database-snapshot-transact-sql.md)  
  
-   [<span data-ttu-id="02138-194">Visualizzazione di uno snapshot del database &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="02138-194">View a Database Snapshot &#40;SQL Server&#41;</span></span>](view-a-database-snapshot-sql-server.md)  
  
-   [<span data-ttu-id="02138-195">Eliminare uno snapshot del database &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="02138-195">Drop a Database Snapshot &#40;Transact-SQL&#41;</span></span>](drop-a-database-snapshot-transact-sql.md)  
  
## <a name="see-also"></a><span data-ttu-id="02138-196">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="02138-196">See Also</span></span>  
 <span data-ttu-id="02138-197">[Snapshot del database &#40;SQL Server&#41;](database-snapshots-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="02138-197">[Database Snapshots &#40;SQL Server&#41;](database-snapshots-sql-server.md) </span></span>  
 <span data-ttu-id="02138-198">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="02138-198">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 <span data-ttu-id="02138-199">[sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="02138-199">[sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) </span></span>  
 [<span data-ttu-id="02138-200">Mirroring e snapshot del database &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="02138-200">Database Mirroring and Database Snapshots &#40;SQL Server&#41;</span></span>](../../database-engine/database-mirroring/database-mirroring-and-database-snapshots-sql-server.md)  
  
  
