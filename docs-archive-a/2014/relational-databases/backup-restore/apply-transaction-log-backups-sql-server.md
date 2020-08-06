---
title: Applicare backup di log delle transazioni (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- restoring [SQL Server], log backups
- transaction log backups [SQL Server], applying backups
- online restores [SQL Server], log backups
- transaction log backups [SQL Server], quantity needed for restore sequence
- backups [SQL Server], log backups
ms.assetid: 9b12be51-5469-46f9-8e86-e938e10aa3a1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 54c91106f8ca6f15539b4103220860143882c3ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627847"
---
# <a name="apply-transaction-log-backups-sql-server"></a><span data-ttu-id="326f2-102">Applicazione dei backup di log delle transazioni (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="326f2-102">Apply Transaction Log Backups (SQL Server)</span></span>
  <span data-ttu-id="326f2-103">Le informazioni contenute in questo argomento sono rilevanti solo per il modello di recupero con registrazione completa o il modello di recupero con registrazione minima delle operazioni bulk.</span><span class="sxs-lookup"><span data-stu-id="326f2-103">The topic is relevant only for the full recovery model or bulk-logged recovery model.</span></span>  
  
 <span data-ttu-id="326f2-104">In questo argomento viene descritta l'applicazione dei backup del log delle transazioni durante il ripristino di un database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="326f2-104">This topic describes applying transaction log backups as part of restoring a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span>  
  
 <span data-ttu-id="326f2-105">**Contenuto dell'argomento**</span><span class="sxs-lookup"><span data-stu-id="326f2-105">**In this Topic:**</span></span>  
  
-   [<span data-ttu-id="326f2-106">Requisiti per il ripristino dei backup del log delle transazioni</span><span class="sxs-lookup"><span data-stu-id="326f2-106">Requirements for Restoring Transaction Log Backups</span></span>](#Requirements)  
  
-   [<span data-ttu-id="326f2-107">Log delle transazioni e ripristino</span><span class="sxs-lookup"><span data-stu-id="326f2-107">Recovery and Transaction Logs</span></span>](#RecoveryAndTlogs)  
  
-   [<span data-ttu-id="326f2-108">Utilizzo dei backup del log per eseguire il ripristino fino al momento dell'errore</span><span class="sxs-lookup"><span data-stu-id="326f2-108">Using Log Backups to Restore to the Point of Failure</span></span>](#PITrestore)  
  
-   [<span data-ttu-id="326f2-109">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="326f2-109">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="requirements-for-restoring-transaction-log-backups"></a><a name="Requirements"></a><span data-ttu-id="326f2-110">Requisiti per il ripristino dei backup del log delle transazioni</span><span class="sxs-lookup"><span data-stu-id="326f2-110">Requirements for Restoring Transaction Log Backups</span></span>  
 <span data-ttu-id="326f2-111">Per applicare un backup del log delle transazioni devono essere soddisfatti i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="326f2-111">To apply a transaction log backup, the following requirements must be met:</span></span>  
  
-   <span data-ttu-id="326f2-112">**Numero sufficiente di backup del log per una sequenza di ripristino:** per completare una sequenza di ripristino, è necessario che sia disponibile il backup di un numero sufficiente di record del log.</span><span class="sxs-lookup"><span data-stu-id="326f2-112">**Enough Log Backups for a Restore Sequence :** You must have enough log records backed up to complete a restore sequence.</span></span> <span data-ttu-id="326f2-113">I backup del log necessari, incluso il [backup della parte finale del log](tail-log-backups-sql-server.md) se richiesto, devono essere disponibili prima dell'inizio della sequenza di ripristino.</span><span class="sxs-lookup"><span data-stu-id="326f2-113">The necessary log backups, including the [tail-log backup](tail-log-backups-sql-server.md) where required, must be available before the start of the restore sequence.</span></span>  
  
-   <span data-ttu-id="326f2-114">**Ordine di ripristino corretto:**  è necessario ripristinare innanzitutto il backup completo o il backup differenziale del database immediatamente precedente.</span><span class="sxs-lookup"><span data-stu-id="326f2-114">**Correct restore order:**  The immediately previous full database backup or differential database backup must be restored first.</span></span> <span data-ttu-id="326f2-115">Tutti i log delle transazioni creati dopo tale backup completo o differenziale devono essere ripristinati in ordine cronologico.</span><span class="sxs-lookup"><span data-stu-id="326f2-115">Then, all transaction logs that are created after that full or differential database backup must be restored in chronological order.</span></span> <span data-ttu-id="326f2-116">Se uno dei backup del log delle transazioni appartenente a questa catena di log non è presente o risulta danneggiato, è possibile ripristinare soltanto i log delle transazioni antecedenti al log delle transazioni non più disponibile.</span><span class="sxs-lookup"><span data-stu-id="326f2-116">If a transaction log backup in this log chain is lost or damaged, you can restore only transaction logs before the missing transaction log.</span></span>  
  
-   <span data-ttu-id="326f2-117">**Database non ancora recuperato:**  non è possibile recuperare il database finché non viene applicato il log delle transazioni finale.</span><span class="sxs-lookup"><span data-stu-id="326f2-117">**Database not yet recovered:**  The database cannot be recovered until after the final transaction log has been applied.</span></span> <span data-ttu-id="326f2-118">Se si esegue il recupero del database dopo aver ripristinato uno dei backup del log delle transazioni intermedi, ovvero antecedenti all'estremità della catena di log, non sarà possibile eseguire il ripristino del database successivamente a tale punto senza riavviare l'intera sequenza di ripristino a partire dal backup completo del database.</span><span class="sxs-lookup"><span data-stu-id="326f2-118">If you recover the database after restoring one of the intermediate transaction log backups, that before the end of the log chain, you cannot restore the database past that point without restarting the complete restore sequence, starting with the full database backup.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="326f2-119">È consigliabile ripristinare tutti i backup del log (RESTORE LOG *nome_database* WITH NORECOVERY).</span><span class="sxs-lookup"><span data-stu-id="326f2-119">A best practice is to restore all the log backups (RESTORE LOG *database_name* WITH NORECOVERY).</span></span> <span data-ttu-id="326f2-120">Dopo aver ripristinato l'ultimo backup del log, recuperare il database in un'operazione separata (RESTORE DATABASE *nome_database* WITH RECOVERY).</span><span class="sxs-lookup"><span data-stu-id="326f2-120">Then, after restoring the last log backup, recover the database in a separate operation (RESTORE DATABASE *database_name* WITH RECOVERY).</span></span>  
  
##  <a name="recovery-and-transaction-logs"></a><a name="RecoveryAndTlogs"></a><span data-ttu-id="326f2-121">Log delle transazioni e ripristino</span><span class="sxs-lookup"><span data-stu-id="326f2-121">Recovery and Transaction Logs</span></span>  
 <span data-ttu-id="326f2-122">Quando si recupera il database al termine dell'operazione di ripristino, viene eseguito il rollback di tutte le transazioni incomplete.</span><span class="sxs-lookup"><span data-stu-id="326f2-122">When you finish the restore operation and recover the database, recovery rolls back all incomplete transactions.</span></span> <span data-ttu-id="326f2-123">Questa procedura è nota come *fase di rollback*.</span><span class="sxs-lookup"><span data-stu-id="326f2-123">This is known as the *undo phase*.</span></span> <span data-ttu-id="326f2-124">L'esecuzione del rollback è necessaria per ripristinare l'integrità del database.</span><span class="sxs-lookup"><span data-stu-id="326f2-124">Rolling back is required to restore the integrity of the database.</span></span> <span data-ttu-id="326f2-125">Dopo il rollback il database passa nello stato online, dopodiché non è possibile applicare alcun altro backup del log delle transazioni al database.</span><span class="sxs-lookup"><span data-stu-id="326f2-125">After rollback, the database goes online, and no more transaction log backups can be applied to the database.</span></span>  
  
 <span data-ttu-id="326f2-126">Si supponga, ad esempio, che una serie di backup del log delle transazioni includa una transazione con esecuzione prolungata.</span><span class="sxs-lookup"><span data-stu-id="326f2-126">For example, a series of transaction log backups contain a long-running transaction.</span></span> <span data-ttu-id="326f2-127">L'inizio della transazione viene registrato nel primo backup del log delle transazioni, mentre la fine della transazione viene registrata nel secondo backup del log delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="326f2-127">The start of the transaction is recorded in the first transaction log backup, but the end of the transaction is recorded in the second transaction log backup.</span></span> <span data-ttu-id="326f2-128">Il primo backup del log delle transazioni non include un record di un'operazione di commit o rollback.</span><span class="sxs-lookup"><span data-stu-id="326f2-128">There is no record of a commit or rollback operation in the first transaction log backup.</span></span> <span data-ttu-id="326f2-129">Se viene eseguita un'operazione di recupero quando è applicato il primo backup del log delle transazioni, la transazione con esecuzione prolungata verrà considerata incompleta e verrà eseguito il rollback delle modifiche dei dati registrate nel primo backup del log delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="326f2-129">If a recovery operation runs when the first transaction log backup is applied, the long-running transaction is treated as incomplete, and data modifications recorded in the first transaction log backup for the transaction are rolled back.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="326f2-130">non è possibile applicare il secondo backup del log delle transazioni dopo questo punto.</span><span class="sxs-lookup"><span data-stu-id="326f2-130">does not allow for the second transaction log backup to be applied after this point.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="326f2-131">In alcuni casi, durante il ripristino del log è possibile aggiungere un file in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="326f2-131">In some circumstances, you can explicitly add a file during log restore.</span></span>  
  
##  <a name="using-log-backups-to-restore-to-the-point-of-failure"></a><a name="PITrestore"></a><span data-ttu-id="326f2-132">Uso dei backup del log per eseguire il ripristino fino al punto di errore</span><span class="sxs-lookup"><span data-stu-id="326f2-132">Using Log Backups to Restore to the Point of Failure</span></span>  
 <span data-ttu-id="326f2-133">Si osservi a titolo di esempio la sequenza di eventi seguente:</span><span class="sxs-lookup"><span data-stu-id="326f2-133">Assume the following sequence of events.</span></span>  
  
|<span data-ttu-id="326f2-134">Tempo</span><span class="sxs-lookup"><span data-stu-id="326f2-134">Time</span></span>|<span data-ttu-id="326f2-135">Event</span><span class="sxs-lookup"><span data-stu-id="326f2-135">Event</span></span>|  
|----------|-----------|  
|<span data-ttu-id="326f2-136">8\.00</span><span class="sxs-lookup"><span data-stu-id="326f2-136">8:00 A.M.</span></span>|<span data-ttu-id="326f2-137">Backup del database per creare un backup completo del database.</span><span class="sxs-lookup"><span data-stu-id="326f2-137">Back up database to create a full database backup.</span></span>|  
|<span data-ttu-id="326f2-138">12.00</span><span class="sxs-lookup"><span data-stu-id="326f2-138">Noon</span></span>|<span data-ttu-id="326f2-139">Backup del log delle transazioni</span><span class="sxs-lookup"><span data-stu-id="326f2-139">Back up transaction log.</span></span>|  
|<span data-ttu-id="326f2-140">16.00</span><span class="sxs-lookup"><span data-stu-id="326f2-140">4:00 P.M.</span></span>|<span data-ttu-id="326f2-141">Backup del log delle transazioni</span><span class="sxs-lookup"><span data-stu-id="326f2-141">Back up transaction log.</span></span>|  
|<span data-ttu-id="326f2-142">18.00</span><span class="sxs-lookup"><span data-stu-id="326f2-142">6:00 P.M.</span></span>|<span data-ttu-id="326f2-143">Backup del database per creare un backup completo del database.</span><span class="sxs-lookup"><span data-stu-id="326f2-143">Back up database to create a full database backup.</span></span>|  
|<span data-ttu-id="326f2-144">20.00</span><span class="sxs-lookup"><span data-stu-id="326f2-144">8:00 P.M.</span></span>|<span data-ttu-id="326f2-145">Backup del log delle transazioni</span><span class="sxs-lookup"><span data-stu-id="326f2-145">Back up transaction log.</span></span>|  
|<span data-ttu-id="326f2-146">21.45</span><span class="sxs-lookup"><span data-stu-id="326f2-146">9:45 P.M.</span></span>|<span data-ttu-id="326f2-147">Si verifica un errore.</span><span class="sxs-lookup"><span data-stu-id="326f2-147">Failure occurs.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="326f2-148">Per la spiegazione di questa sequenza esemplificativa di backup, vedere [Backup di log delle transazioni &#40;SQL Server&#41;](transaction-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="326f2-148">For an explanation of this example sequence of backups, see [Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md).</span></span>  
  
 <span data-ttu-id="326f2-149">Per ripristinare lo stato del database corrispondente alle ore 21.45</span><span class="sxs-lookup"><span data-stu-id="326f2-149">To restore the database to its state at 9:45 P.M.</span></span> <span data-ttu-id="326f2-150">(punto di errore), è possibile utilizzare una delle procedure alternative seguenti:</span><span class="sxs-lookup"><span data-stu-id="326f2-150">(the point of failure), either of the following alternative procedures can be used:</span></span>  
  
 <span data-ttu-id="326f2-151">**Alternativa 1: ripristinare il database da un backup completo più recente**</span><span class="sxs-lookup"><span data-stu-id="326f2-151">**Alternative 1: Restore the database by using the most recent full database backup**</span></span>  
  
1.  <span data-ttu-id="326f2-152">Creare un backup della parte finale del log delle transazioni attivo a partire dal momento dell'errore.</span><span class="sxs-lookup"><span data-stu-id="326f2-152">Create a tail-log backup of the currently active transaction log as of the point of failure.</span></span>  
  
2.  <span data-ttu-id="326f2-153">Non ripristinare</span><span class="sxs-lookup"><span data-stu-id="326f2-153">Do not restore the 8:00 A.M.</span></span> <span data-ttu-id="326f2-154">del backup completo del database delle 18.00.</span><span class="sxs-lookup"><span data-stu-id="326f2-154">full database backup.</span></span> <span data-ttu-id="326f2-155">Ripristinare invece il backup completo del database</span><span class="sxs-lookup"><span data-stu-id="326f2-155">Instead, restore the more recent 6:00 P.M.</span></span> <span data-ttu-id="326f2-156">più recente effettuato alle 18.00, quindi applicare il</span><span class="sxs-lookup"><span data-stu-id="326f2-156">full database backup, and then apply the 8:00 P.M.</span></span> <span data-ttu-id="326f2-157">backup del log effettuato alle 20.00 e il backup della parte finale del log.</span><span class="sxs-lookup"><span data-stu-id="326f2-157">log backup and the tail-log backup.</span></span>  
  
 <span data-ttu-id="326f2-158">**Alternativa 2: ripristinare il database da un backup completo precedente**</span><span class="sxs-lookup"><span data-stu-id="326f2-158">**Alternative 2: Restore the database by using an earlier full database backup**</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="326f2-159">Questa procedura alternativa è utile nel caso non sia possibile utilizzare il backup completo del database effettuato alle 18.00</span><span class="sxs-lookup"><span data-stu-id="326f2-159">This alternative process is useful if a problem prevents you from using the 6:00 P.M.</span></span> <span data-ttu-id="326f2-160">del backup completo del database delle 18.00.</span><span class="sxs-lookup"><span data-stu-id="326f2-160">full database backup.</span></span> <span data-ttu-id="326f2-161">Questa procedura richiede più tempo di quello necessario per il ripristino</span><span class="sxs-lookup"><span data-stu-id="326f2-161">This process takes longer than restoring from the 6:00 P.M.</span></span> <span data-ttu-id="326f2-162">del backup completo del database delle 18.00.</span><span class="sxs-lookup"><span data-stu-id="326f2-162">full database backup.</span></span>  
  
1.  <span data-ttu-id="326f2-163">Creare un backup della parte finale del log delle transazioni attivo a partire dal momento dell'errore.</span><span class="sxs-lookup"><span data-stu-id="326f2-163">Create a tail-log backup of the currently active transaction log as of the point of failure.</span></span>  
  
2.  <span data-ttu-id="326f2-164">Ripristinare il backup</span><span class="sxs-lookup"><span data-stu-id="326f2-164">Restore the 8:00 A.M.</span></span> <span data-ttu-id="326f2-165">completo del database delle 8.00, quindi ripristinare in sequenza tutti e quattro i backup del log delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="326f2-165">full database backup, and then restore all four transaction log backups in sequence.</span></span> <span data-ttu-id="326f2-166">Ciò determina il rollforward di tutte le transazioni completate fino alle 21.45.</span><span class="sxs-lookup"><span data-stu-id="326f2-166">This rolls forward all completed transactions up to 9:45 P.M.</span></span>  
  
     <span data-ttu-id="326f2-167">Questa procedura alternativa mostra quale sia il livello di sicurezza supplementare garantito dal mantenimento di una catena di backup del log delle transazioni eseguiti in una serie di backup completi del database.</span><span class="sxs-lookup"><span data-stu-id="326f2-167">This alternative points out the redundant security offered by maintaining a chain of transaction log backups across a series of full database backups.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="326f2-168">In alcuni casi è anche possibile utilizzare i log delle transazioni per ripristinare un database fino a un punto nel tempo specifico.</span><span class="sxs-lookup"><span data-stu-id="326f2-168">In some cases, you can also use transaction logs to restore a database to a specific point in time.</span></span> <span data-ttu-id="326f2-169">Per altre informazioni, vedere [Ripristinare un database di SQL Server fino a un punto specifico &#40;modello di recupero con registrazione completa&#41;](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md).</span><span class="sxs-lookup"><span data-stu-id="326f2-169">For more information, [Restore a SQL Server Database to a Point in Time &#40;Full Recovery Model&#41;](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="326f2-170">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="326f2-170">Related Tasks</span></span>  
 <span data-ttu-id="326f2-171">**Per applicare un backup del log delle transazioni**</span><span class="sxs-lookup"><span data-stu-id="326f2-171">**To apply a transaction log backup**</span></span>  
  
-   [<span data-ttu-id="326f2-172">Ripristinare un backup del log delle transazioni &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="326f2-172">Restore a Transaction Log Backup &#40;SQL Server&#41;</span></span>](restore-a-transaction-log-backup-sql-server.md)  
  
 <span data-ttu-id="326f2-173">**Per eseguire il ripristino fino al punto di recupero**</span><span class="sxs-lookup"><span data-stu-id="326f2-173">**To restore to your recovery point**</span></span>  
  
-   [<span data-ttu-id="326f2-174">Ripristinare un database fino al punto di errore nel modello di recupero con registrazione completa &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="326f2-174">Restore a Database to the Point of Failure Under the Full Recovery Model &#40;Transact-SQL&#41;</span></span>](restore-database-to-point-of-failure-full-recovery.md)  
  
-   [<span data-ttu-id="326f2-175">Ripristinare un database di SQL Server fino a un punto specifico &#40;modello di recupero con registrazione completa&#41;</span><span class="sxs-lookup"><span data-stu-id="326f2-175">Restore a SQL Server Database to a Point in Time &#40;Full Recovery Model&#41;</span></span>](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md)  
  
-   <span data-ttu-id="326f2-176"><xref:Microsoft.SqlServer.Management.Smo.Restore.SqlRestore%2A> (SMO)</span><span class="sxs-lookup"><span data-stu-id="326f2-176"><xref:Microsoft.SqlServer.Management.Smo.Restore.SqlRestore%2A> (SMO)</span></span>  
  
-   [<span data-ttu-id="326f2-177">Recupero di database correlati che contengono transazioni contrassegnate</span><span class="sxs-lookup"><span data-stu-id="326f2-177">Recovery of Related  Databases That Contain Marked Transaction</span></span>](recovery-of-related-databases-that-contain-marked-transaction.md)  
  
-   [<span data-ttu-id="326f2-178">Recupero fino a un numero di sequenza del file di log &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="326f2-178">Recover to a Log Sequence Number &#40;SQL Server&#41;</span></span>](recover-to-a-log-sequence-number-sql-server.md)  
  
 <span data-ttu-id="326f2-179">**Per recuperare un database dopo il ripristino dei backup utilizzando WITH NORECOVERY**</span><span class="sxs-lookup"><span data-stu-id="326f2-179">**To recover a database after restoring backups using WITH NORECOVERY**</span></span>  
  
-   [<span data-ttu-id="326f2-180">Recuperare un database senza ripristino dei dati &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="326f2-180">Recover a Database Without Restoring Data &#40;Transact-SQL&#41;</span></span>](recover-a-database-without-restoring-data-transact-sql.md)  
  
## <a name="see-also"></a><span data-ttu-id="326f2-181">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="326f2-181">See Also</span></span>  
 [<span data-ttu-id="326f2-182">Log delle transazioni &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="326f2-182">The Transaction Log &#40;SQL Server&#41;</span></span>](../logs/the-transaction-log-sql-server.md)  
  
  
