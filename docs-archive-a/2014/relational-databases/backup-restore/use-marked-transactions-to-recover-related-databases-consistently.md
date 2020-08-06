---
title: Usare transazioni contrassegnate per recuperare coerentemente i database correlati (modello di recupero con distribuzione completa) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- transaction marks [SQL Server]
- marked transactions [SQL Server]
- database restores [SQL Server], inserting transaction marks for
- recovery [SQL Server], related databases
- restoring databases [SQL Server], related database recovery
- database restores [SQL Server], related databases
- marked transactions [SQL Server], creating
- BEGIN TRAN...WITH MARK statement
- two-phase commit
ms.assetid: 50a73574-1a69-448e-83dd-9abcc7cb7e1a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8dd368ad14f6e521fb8d504bdea774e3088c2522
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721511"
---
# <a name="use-marked-transactions-to-recover-related-databases-consistently-full-recovery-model"></a><span data-ttu-id="4ed58-102">Utilizzare Transazioni contrassegnate per recuperare coerentemente i database correlati (Modello di recupero con registrazione completa)</span><span class="sxs-lookup"><span data-stu-id="4ed58-102">Use Marked Transactions to Recover Related Databases Consistently (Full Recovery Model)</span></span>
  <span data-ttu-id="4ed58-103">Le informazioni contenute in questo argomento sono rilevanti solo per i database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] che utilizzano i modelli di recupero con registrazione completa o con registrazione minima delle operazioni bulk.</span><span class="sxs-lookup"><span data-stu-id="4ed58-103">This topic is relevant only for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases that are using the full or bulk-logged recovery models.</span></span>  
  
 <span data-ttu-id="4ed58-104">Quando si eseguono aggiornamenti in due o più *database correlati*, è possibile usare i contrassegni delle transazioni per recuperarli fino a un punto consistente logico.</span><span class="sxs-lookup"><span data-stu-id="4ed58-104">When you make related updates to two or more databases, *related databases*, you can use transaction marks to recover them to a logically consistent point.</span></span> <span data-ttu-id="4ed58-105">In questo recupero viene tuttavia persa qualsiasi transazione di cui sia stato eseguito il commit dopo il contrassegno utilizzato come punto di recupero.</span><span class="sxs-lookup"><span data-stu-id="4ed58-105">However, this recovery loses any transaction that is committed after the mark that was used as the recovery point.</span></span> <span data-ttu-id="4ed58-106">L'utilizzo del contrassegno delle transazioni è adeguato solo quando si esegue il test di database correlati o quando la perdita delle transazioni di cui sia stato eseguito il commit di recente non è importante.</span><span class="sxs-lookup"><span data-stu-id="4ed58-106">Marking transactions is suitable only when you are testing related databases or when you are willing to lose recently committed transactions.</span></span>  
  
 <span data-ttu-id="4ed58-107">L'applicazione ripetuta di contrassegni alle transazioni correlate in ogni database correlato determina una serie di punti di recupero comuni nei database.</span><span class="sxs-lookup"><span data-stu-id="4ed58-107">Routinely marking related transactions in every related database establishes a series of common recovery points in the databases.</span></span> <span data-ttu-id="4ed58-108">I contrassegni delle transazioni vengono registrati nel log delle transazioni e inclusi nei backup del log.</span><span class="sxs-lookup"><span data-stu-id="4ed58-108">The transaction marks are recorded in the transaction log and included in log backups.</span></span> <span data-ttu-id="4ed58-109">In caso di emergenza, è possibile ripristinare tutti i database rispetto allo stesso contrassegno della transazione per recuperarli fino a una punto consistente.</span><span class="sxs-lookup"><span data-stu-id="4ed58-109">In the event of a disaster, you can restore each of the databases to the same transaction mark to recover them to a consistent point.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4ed58-110">I backup del log nei diversi database possono essere creati in modo indipendente gli uni dagli altri e non è necessario che siano simultanei.</span><span class="sxs-lookup"><span data-stu-id="4ed58-110">Log backups on the different databases can be created independently of each other and do not have to be simultaneous.</span></span>  
  
 <span data-ttu-id="4ed58-111">Il recupero di database correlati negli scenari seguenti richiede che siano già presenti transazioni contrassegnate in ogni database correlato:</span><span class="sxs-lookup"><span data-stu-id="4ed58-111">Recovering related databases in the following scenarios requires that you have already marked transactions in every related database:</span></span>  
  
-   <span data-ttu-id="4ed58-112">Uno o più log delle transazioni sono danneggiati.</span><span class="sxs-lookup"><span data-stu-id="4ed58-112">One or more transaction logs are destroyed.</span></span> <span data-ttu-id="4ed58-113">È necessario ripristinare il set di database in uno stato consistente al momento dell'ultimo backup del log.</span><span class="sxs-lookup"><span data-stu-id="4ed58-113">You have to restore the set of databases to a consistent state at the time of your last log backup.</span></span>  
  
-   <span data-ttu-id="4ed58-114">È necessario ripristinare l'intero set di database in uno stato mutualmente consistente fino a un punto nel tempo precedente.</span><span class="sxs-lookup"><span data-stu-id="4ed58-114">You have to restore the entire set of databases to a mutually consistent state at some earlier point in time.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="4ed58-115">È possibile recuperare database correlati solo fino a una transazione contrassegnata e non a un momento specifico.</span><span class="sxs-lookup"><span data-stu-id="4ed58-115">You can recover related databases only to a marked transaction, not to a specific point in time.</span></span>  
  
 <span data-ttu-id="4ed58-116">Per informazioni su come creare transazioni contrassegnate, vedere "Creazione di transazioni contrassegnate", di seguito in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="4ed58-116">For information about how to create marking transactions, see "Creating the Marked Transactions," later in this topic.</span></span>  
  
## <a name="typical-scenario-for-using-marked-transactions"></a><span data-ttu-id="4ed58-117">Scenario tipico per l'utilizzo delle transazioni contrassegnate</span><span class="sxs-lookup"><span data-stu-id="4ed58-117">Typical Scenario for Using Marked Transactions</span></span>  
 <span data-ttu-id="4ed58-118">Uno scenario tipico per l'utilizzo delle transazioni contrassegnate include i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="4ed58-118">A typical scenario for using marked transactions includes the following steps:</span></span>  
  
1.  <span data-ttu-id="4ed58-119">Creare un backup completo o differenziale del database per ogni database correlato.</span><span class="sxs-lookup"><span data-stu-id="4ed58-119">Create a full or differential database backup of each of the related databases.</span></span>  
  
2.  <span data-ttu-id="4ed58-120">Contrassegnare un blocco di transazioni in tutti i database.</span><span class="sxs-lookup"><span data-stu-id="4ed58-120">Mark a transaction block in all the databases.</span></span>  
  
3.  <span data-ttu-id="4ed58-121">Eseguire il backup del log delle transazioni per tutti i database.</span><span class="sxs-lookup"><span data-stu-id="4ed58-121">Back up the transaction log for all the databases.</span></span>  
  
4.  <span data-ttu-id="4ed58-122">Ripristinare i backup dei database WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="4ed58-122">Restore database backups WITH NORECOVERY.</span></span>  
  
5.  <span data-ttu-id="4ed58-123">Ripristinare i log WITH STOPATMARK.</span><span class="sxs-lookup"><span data-stu-id="4ed58-123">Restore logs WITH STOPATMARK.</span></span>  
  
## <a name="considerations-for-using-marked-transactions"></a><span data-ttu-id="4ed58-124">Considerazioni sull'utilizzo delle transazioni contrassegnate</span><span class="sxs-lookup"><span data-stu-id="4ed58-124">Considerations for Using Marked Transactions</span></span>  
 <span data-ttu-id="4ed58-125">Prima di inserire contrassegni denominati nel log delle transazioni, considerare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="4ed58-125">Before inserting named marks into the transaction log, consider the following:</span></span>  
  
-   <span data-ttu-id="4ed58-126">I contrassegni di transazione occupano spazio nei log e pertanto è consigliabile utilizzarli esclusivamente per transazioni importanti ai fini della strategia di recupero dei database.</span><span class="sxs-lookup"><span data-stu-id="4ed58-126">Because transaction marks consume log space, use them only for transactions that play a significant role in the database recovery strategy.</span></span>  
  
-   <span data-ttu-id="4ed58-127">Dopo il commit di una transazione contrassegnata, viene inserita una riga nella tabella [logmarkhistory](/sql/relational-databases/system-tables/logmarkhistory-transact-sql) del database **msdb**.</span><span class="sxs-lookup"><span data-stu-id="4ed58-127">After a marked transaction commits, a row is inserted in the [logmarkhistory](/sql/relational-databases/system-tables/logmarkhistory-transact-sql) table in **msdb**.</span></span>  
  
-   <span data-ttu-id="4ed58-128">Se una transazione contrassegnata si estende su più database dello stesso server di database o di server diversi, i contrassegni devono essere registrati nei log di tutti i database interessati.</span><span class="sxs-lookup"><span data-stu-id="4ed58-128">If a marked transaction spans multiple databases on the same database server or on different servers, the marks must be recorded in the logs of all the affected databases.</span></span>  
  
## <a name="creating-the-marked-transactions"></a><span data-ttu-id="4ed58-129">Creazione delle transazioni contrassegnate</span><span class="sxs-lookup"><span data-stu-id="4ed58-129">Creating the Marked Transactions</span></span>  
 <span data-ttu-id="4ed58-130">Per creare una transazione contrassegnata, usare l'istruzione [BEGIN TRANSACTION](/sql/t-sql/language-elements/begin-transaction-transact-sql) e la clausola WITH MARK [*description*].</span><span class="sxs-lookup"><span data-stu-id="4ed58-130">To create a marked transaction, use the [BEGIN TRANSACTION](/sql/t-sql/language-elements/begin-transaction-transact-sql) statement and the WITH MARK [*description*] clause.</span></span> <span data-ttu-id="4ed58-131">L'argomento *description* è facoltativo e rappresenta una descrizione del contrassegno.</span><span class="sxs-lookup"><span data-stu-id="4ed58-131">The optional *description* is a textual description of the mark.</span></span> <span data-ttu-id="4ed58-132">Il nome del contrassegno della transazione è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="4ed58-132">A mark name for the transaction is required.</span></span> <span data-ttu-id="4ed58-133">È possibile riutilizzare il nome di un contrassegno.</span><span class="sxs-lookup"><span data-stu-id="4ed58-133">A mark name can be reused.</span></span> <span data-ttu-id="4ed58-134">Il log delle transazioni registra il nome del contrassegno, la descrizione, il database, l'utente, le informazioni di data/ora e il numero di sequenza del file di log (LSN).</span><span class="sxs-lookup"><span data-stu-id="4ed58-134">The transaction log records the mark name, description, database, user, datetime information, and the log sequence number (LSN).</span></span> <span data-ttu-id="4ed58-135">Le informazioni di data/ora sono utilizzate insieme al nome del contrassegno per identificare il contrassegno in modo univoco.</span><span class="sxs-lookup"><span data-stu-id="4ed58-135">The datetime information is used along with the mark name to uniquely identify the mark.</span></span>  
  
 <span data-ttu-id="4ed58-136">**Per creare transazioni contrassegnate in un set di database:**</span><span class="sxs-lookup"><span data-stu-id="4ed58-136">**To create marked transactions in a set of databases:**</span></span>  
  
1.  <span data-ttu-id="4ed58-137">Denominare la transazione nell'istruzione BEGIN TRAN e utilizzare la clausola WITH MARK</span><span class="sxs-lookup"><span data-stu-id="4ed58-137">Name the transaction in the BEGIN TRAN statement and use the WITH MARK clause</span></span>  
  
     <span data-ttu-id="4ed58-138">È possibile nidificare l'istruzione BEGIN TRAN *nuovo_nome_contrassegno* WITH MARK all'interno di una transazione esistente.</span><span class="sxs-lookup"><span data-stu-id="4ed58-138">You can nest the statement BEGIN TRAN *new_mark_name* WITH MARK within an existing transaction.</span></span> <span data-ttu-id="4ed58-139">Il valore di *nuovo_nome_contrassegno* è il nome di contrassegno per la transazione, anche se è dotata di un nome di transazione.</span><span class="sxs-lookup"><span data-stu-id="4ed58-139">The value of *new_mark_name* is the mark name for the transaction, even if the transaction possesses a transaction name.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4ed58-140">Se si esegue una seconda istruzione nidificata BEGIN TRAN...WITH MARK, l'istruzione verrà ignorata ma provocherà un messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="4ed58-140">If you issue a second nested BEGIN TRAN...WITH MARK, that statement is skipped but causes a warning message.</span></span>  
  
2.  <span data-ttu-id="4ed58-141">Eseguire un aggiornamento di tutti i database nel set.</span><span class="sxs-lookup"><span data-stu-id="4ed58-141">Run an update against all of the databases in the set.</span></span>  
  
     <span data-ttu-id="4ed58-142">Il contrassegno per una transazione specifica viene inserito solo nei log delle transazioni dell'istanza del server in cui viene eseguita l'istruzione BEGIN TRAN.</span><span class="sxs-lookup"><span data-stu-id="4ed58-142">The mark for a specific transaction is inserted into transaction logs only on the server instance where the BEGIN TRAN...WITH MARK statement is executed.</span></span> <span data-ttu-id="4ed58-143">Il contrassegno della transazione viene inserito nel log delle transazioni di ogni database aggiornato dalla transazione contrassegnata in tale istanza del server.</span><span class="sxs-lookup"><span data-stu-id="4ed58-143">The transaction mark is placed in the transaction log of every database updated by the marked transaction on that server instance.</span></span> <span data-ttu-id="4ed58-144">Se il database si trova in istanze del server diverse, è necessario creare contrassegni identici in ogni istanza del server.</span><span class="sxs-lookup"><span data-stu-id="4ed58-144">If the databases reside on different server instances, identical marks must be created on each of the server instances.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="4ed58-145">Esempi</span><span class="sxs-lookup"><span data-stu-id="4ed58-145">Examples</span></span>  
 <span data-ttu-id="4ed58-146">Nell'esempio seguente viene ripristinato il log delle transazioni fino al contrassegno nella transazione contrassegnata denominata `ListPriceUpdate`.</span><span class="sxs-lookup"><span data-stu-id="4ed58-146">The following example restores the transaction log to the mark in the marked transaction named `ListPriceUpdate`.</span></span>  
  
```sql  
USE AdventureWorks  
GO  
BEGIN TRANSACTION ListPriceUpdate  
   WITH MARK 'UPDATE Product list prices';  
GO  
  
UPDATE Production.Product  
   SET ListPrice = ListPrice * 1.10  
   WHERE ProductNumber LIKE 'BK-%';  
GO  
  
COMMIT TRANSACTION ListPriceUpdate;  
GO  
  
-- Time passes. Regular database   
-- and log backups are taken.  
-- An error occurs in the database.  
USE master  
GO  
  
RESTORE DATABASE AdventureWorks  
FROM AdventureWorksBackups  
WITH FILE = 3, NORECOVERY;  
GO  
  
RESTORE LOG AdventureWorks  
   FROM AdventureWorksBackups   
   WITH FILE = 4,  
   RECOVERY,   
   STOPATMARK = 'ListPriceUpdate';  
```  
  
## <a name="forcing-a-mark-to-spread-to-other-servers"></a><span data-ttu-id="4ed58-147">Distribuzione forzata di un contrassegno in altri server</span><span class="sxs-lookup"><span data-stu-id="4ed58-147">Forcing a Mark to Spread to Other Servers</span></span>  
 <span data-ttu-id="4ed58-148">Il nome di un contrassegno di transazione non viene distribuito automaticamente in altri server se la transazione viene distribuita.</span><span class="sxs-lookup"><span data-stu-id="4ed58-148">A transaction mark name is not automatically distributed to another server as the transaction spreads there.</span></span> <span data-ttu-id="4ed58-149">Per forzare la distribuzione del contrassegno in altri server, è necessario scrivere una stored procedure contenente un'istruzione BEGIN TRAN *name* WITH MARK.</span><span class="sxs-lookup"><span data-stu-id="4ed58-149">To force the mark to spread to the other servers, a stored procedure must be written that contains a BEGIN TRAN *name* WITH MARK statement.</span></span> <span data-ttu-id="4ed58-150">Tale stored procedure deve quindi essere eseguita nel server remoto nell'ambito della transazione del server di origine.</span><span class="sxs-lookup"><span data-stu-id="4ed58-150">That stored procedure must then be executed on the remote server under the scope of the transaction in the originating server.</span></span>  
  
 <span data-ttu-id="4ed58-151">Ad esempio, considerare un database partizionato esistente in più istanze di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4ed58-151">For example, consider a partitioned database that exists on multiple instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="4ed58-152">In ogni istanza è presente un database denominato `coyote`.</span><span class="sxs-lookup"><span data-stu-id="4ed58-152">On each instance is a database named `coyote`.</span></span> <span data-ttu-id="4ed58-153">Creare innanzitutto una stored procedure in ogni database, ad esempio `sp_SetMark`.</span><span class="sxs-lookup"><span data-stu-id="4ed58-153">First, in every database, create a stored procedure, for example, `sp_SetMark`.</span></span>  
  
```sql  
CREATE PROCEDURE sp_SetMark  
@name nvarchar (128)  
AS  
BEGIN TRANSACTION @name WITH MARK  
UPDATE coyote.dbo.Marks SET one = 1  
COMMIT TRANSACTION;  
GO  
```  
  
 <span data-ttu-id="4ed58-154">Creare quindi una stored procedure `sp_MarkAll` contenente una transazione che inserisce un contrassegno in ogni database.</span><span class="sxs-lookup"><span data-stu-id="4ed58-154">Next, create stored procedure `sp_MarkAll` containing a transaction that places a mark in every database.</span></span> <span data-ttu-id="4ed58-155">`sp_MarkAll` può essere eseguita da qualsiasi istanza.</span><span class="sxs-lookup"><span data-stu-id="4ed58-155">`sp_MarkAll` can be run from any of the instances.</span></span>  
  
```sql  
CREATE PROCEDURE sp_MarkAll  
@name nvarchar (128)  
AS  
BEGIN TRANSACTION  
EXEC instance0.coyote.dbo.sp_SetMark @name  
EXEC instance1.coyote.dbo.sp_SetMark @name  
EXEC instance2.coyote.dbo.sp_SetMark @name  
COMMIT TRANSACTION;  
GO  
```  
  
### <a name="two-phase-commit"></a><span data-ttu-id="4ed58-156">commit in due fasi</span><span class="sxs-lookup"><span data-stu-id="4ed58-156">Two-Phase Commit</span></span>  
 <span data-ttu-id="4ed58-157">L'esecuzione del commit di una transazione distribuita avviene in due fasi: la preparazione e il commit.</span><span class="sxs-lookup"><span data-stu-id="4ed58-157">Committing a distributed transaction occurs in two phases: prepare and commit.</span></span> <span data-ttu-id="4ed58-158">Quando si esegue il commit di una transazione contrassegnata, il record di commit del log per ogni database interessato dalla transazione contrassegnata viene inserito nel log in un punto in cui non sono presenti transazioni in sospeso in nessuno dei log.</span><span class="sxs-lookup"><span data-stu-id="4ed58-158">When a marked transaction is committed, the commit log record for each database in the marked transaction is placed in the log at a point where there are no in-doubt transactions in any of the logs.</span></span> <span data-ttu-id="4ed58-159">In questo modo, si garantisce che non vi siano transazioni di cui è stato eseguito il commit in un log ma di cui non è stato eseguito il commit in un altro log.</span><span class="sxs-lookup"><span data-stu-id="4ed58-159">At this point, it is guaranteed that there are no transactions that appear as committed in one log, but not committed in another log.</span></span>  
  
 <span data-ttu-id="4ed58-160">I passaggi seguenti garantiscono questo risultato durante il commit di una transazione contrassegnata:</span><span class="sxs-lookup"><span data-stu-id="4ed58-160">The following steps accomplish this during the commit of a marked transaction:</span></span>  
  
1.  <span data-ttu-id="4ed58-161">La fase di preparazione di una transazione contrassegnata blocca tutte le nuove operazioni di preparazione e commit.</span><span class="sxs-lookup"><span data-stu-id="4ed58-161">Prepare phase of a marking transaction stalls all new prepares and commits.</span></span>  
  
2.  <span data-ttu-id="4ed58-162">È consentito il proseguimento solo delle operazioni di commit di transazioni già preparate.</span><span class="sxs-lookup"><span data-stu-id="4ed58-162">Only commits of already prepared transactions are allowed to continue.</span></span>  
  
3.  <span data-ttu-id="4ed58-163">La transazione contrassegnata attende quindi il completamento di tutte le transazioni preparate (con timeout).</span><span class="sxs-lookup"><span data-stu-id="4ed58-163">Marking transaction then waits for all prepared transactions to drain (with time-out).</span></span>  
  
4.  <span data-ttu-id="4ed58-164">La transazione contrassegnata viene preparata e quindi ne viene eseguito il commit.</span><span class="sxs-lookup"><span data-stu-id="4ed58-164">Marked transaction is prepared and committed.</span></span>  
  
5.  <span data-ttu-id="4ed58-165">Il blocco di nuove operazioni di preparazione e commit viene annullato.</span><span class="sxs-lookup"><span data-stu-id="4ed58-165">The stall of new prepares and commits is removed.</span></span>  
  
 <span data-ttu-id="4ed58-166">I blocchi generati dalle transazioni contrassegnate che si estendono su più database possono rallentare le prestazioni di elaborazione delle transazioni nel server.</span><span class="sxs-lookup"><span data-stu-id="4ed58-166">The stalls generated by marked transactions that span multiple databases can reduce the transaction processing performance of the server.</span></span>  
  
 <span data-ttu-id="4ed58-167">È consigliabile non eseguire transazioni contrassegnate simultanee.</span><span class="sxs-lookup"><span data-stu-id="4ed58-167">We recommend that you do not run concurrent marked transactions.</span></span> <span data-ttu-id="4ed58-168">È raro ma possibile che il commit di una transazione contrassegnata distribuita generi un deadlock quando viene eseguito il commit simultaneo di altre transazioni contrassegnate distribuite.</span><span class="sxs-lookup"><span data-stu-id="4ed58-168">It is rare but possible for the commit of a distributed marked transaction to deadlock with other distributed marked transactions that are committing at the same time.</span></span> <span data-ttu-id="4ed58-169">In tal caso, la transazione contrassegnata verrà scelta come oggetto del deadlock e ne verrà eseguito il rollback.</span><span class="sxs-lookup"><span data-stu-id="4ed58-169">When this happens, the marking transaction is chosen as the deadlock victim and is rolled back.</span></span> <span data-ttu-id="4ed58-170">Se si verifica questo errore, l'applicazione può ripetere il tentativo di esecuzione della transazione contrassegnata.</span><span class="sxs-lookup"><span data-stu-id="4ed58-170">When this error occurs, the application can retry the marked transaction.</span></span> <span data-ttu-id="4ed58-171">Quando più transazioni contrassegnate tentano di eseguire il commit simultaneamente, la probabilità che venga generato un deadlock è maggiore.</span><span class="sxs-lookup"><span data-stu-id="4ed58-171">When multiple marked transactions try to commit concurrently, there is a higher probability of deadlock.</span></span>  
  
## <a name="recovering-to-a-marked-transaction"></a><span data-ttu-id="4ed58-172">Recupero fino a una transazione contrassegnata</span><span class="sxs-lookup"><span data-stu-id="4ed58-172">Recovering to a Marked Transaction</span></span>  
 <span data-ttu-id="4ed58-173">Per informazioni su come recuperare un database che contiene transazioni contrassegnate fino a un contrassegno particolare o appena prima di esso, vedere [Recupero di database correlati che contengono transazioni contrassegnate](recovery-of-related-databases-that-contain-marked-transaction.md).</span><span class="sxs-lookup"><span data-stu-id="4ed58-173">For information about how to recover a database that contains marked transactions to or just before a particular mark, see [Recovery of Related  Databases That Contain Marked Transaction](recovery-of-related-databases-that-contain-marked-transaction.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ed58-174">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4ed58-174">See Also</span></span>  
 <span data-ttu-id="4ed58-175">[BEGIN DISTRIBUTED TRANSACTION &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/begin-distributed-transaction-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4ed58-175">[BEGIN DISTRIBUTED TRANSACTION &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/begin-distributed-transaction-transact-sql) </span></span>  
 <span data-ttu-id="4ed58-176">[Backup e ripristino di database di sistema &#40;SQL Server&#41;](back-up-and-restore-of-system-databases-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="4ed58-176">[Back Up and Restore of System Databases &#40;SQL Server&#41;](back-up-and-restore-of-system-databases-sql-server.md) </span></span>  
 <span data-ttu-id="4ed58-177">[BEGIN TRANSACTION &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/begin-transaction-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4ed58-177">[BEGIN TRANSACTION &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/begin-transaction-transact-sql) </span></span>  
 <span data-ttu-id="4ed58-178">[Applicare backup del log delle transazioni &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="4ed58-178">[Apply Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span></span>  
 <span data-ttu-id="4ed58-179">[Backup completo del database &#40;SQL Server&#41;](full-database-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="4ed58-179">[Full Database Backups &#40;SQL Server&#41;](full-database-backups-sql-server.md) </span></span>  
 <span data-ttu-id="4ed58-180">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4ed58-180">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 [<span data-ttu-id="4ed58-181">Recupero di database correlati che contengono transazioni contrassegnate</span><span class="sxs-lookup"><span data-stu-id="4ed58-181">Recovery of Related  Databases That Contain Marked Transaction</span></span>](recovery-of-related-databases-that-contain-marked-transaction.md)  
  
  
