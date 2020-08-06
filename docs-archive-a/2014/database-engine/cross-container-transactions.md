---
title: Transazioni tra contenitori | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 5d84b51a-ec17-4c5c-b80e-9e994fc8ae80
author: stevestein
ms.author: sstein
ms.openlocfilehash: 28437f0903459616a574e713c0f138e8bb459870
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628956"
---
# <a name="cross-container-transactions"></a><span data-ttu-id="a5161-102">Transazioni tra contenitori</span><span class="sxs-lookup"><span data-stu-id="a5161-102">Cross-Container Transactions</span></span>
  <span data-ttu-id="a5161-103">Le transazioni tra contenitori sono transazioni utente implicite o esplicite che includono chiamate a stored procedure compilate in modo nativo o operazioni in tabelle ottimizzate per la memoria.</span><span class="sxs-lookup"><span data-stu-id="a5161-103">Cross-container transactions are either implicit or explicit user transactions that include calls to natively-compiled stored procedures or operations on memory-optimized tables.</span></span>  
  
 <span data-ttu-id="a5161-104">In [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] le chiamate a stored procedure non avviano una transazione.</span><span class="sxs-lookup"><span data-stu-id="a5161-104">In [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], calls to stored procedures do not initiate a transaction.</span></span> <span data-ttu-id="a5161-105">Le esecuzioni di stored procedure compilate in modo nativo in modalità autocommit, non nel contesto di una transazione utente, non vengono considerate transazioni tra contenitori.</span><span class="sxs-lookup"><span data-stu-id="a5161-105">Executions of natively compiled procedures in autocommit mode (not in the context of a user transaction) are not considered cross-container transactions.</span></span>  
  
 <span data-ttu-id="a5161-106">Qualsiasi query interpretata che faccia riferimento a tabelle ottimizzate per la memoria viene considerata parte di una transazione tra contenitori, sia che venga eseguita da una transazione esplicita o implicita sia in modalità autocommit.</span><span class="sxs-lookup"><span data-stu-id="a5161-106">Any interpreted query that references memory-optimized tables is considered a part of a cross-container transaction, whether executed from an explicit or implicit transaction or in auto-commit mode.</span></span>  
  
##  <a name="isolation-of-individual-operations"></a><a name="isolation"></a><span data-ttu-id="a5161-107">Isolamento di singole operazioni</span><span class="sxs-lookup"><span data-stu-id="a5161-107">Isolation of Individual Operations</span></span>  
 <span data-ttu-id="a5161-108">A ogni transazione di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] è associato un livello di isolamento.</span><span class="sxs-lookup"><span data-stu-id="a5161-108">Each [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] transaction has an isolation level.</span></span> <span data-ttu-id="a5161-109">Il livello di isolamento predefinito è READ COMMITTED.</span><span class="sxs-lookup"><span data-stu-id="a5161-109">The default isolation level is Read Committed.</span></span> <span data-ttu-id="a5161-110">Per usare un livello di isolamento diverso, è possibile impostare il livello di isolamento usando [set Transaction isolation level &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-transaction-isolation-level-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a5161-110">To use a different isolation level, you can set the isolation level using [SET TRANSACTION ISOLATION LEVEL &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-transaction-isolation-level-transact-sql).</span></span>  
  
 <span data-ttu-id="a5161-111">È spesso necessario effettuare operazioni in tabelle ottimizzate per la memoria in un livello di isolamento diverso dalle operazioni in tabelle basate su disco.</span><span class="sxs-lookup"><span data-stu-id="a5161-111">It is often necessary to perform operations on memory-optimized tables at a different isolation level than operations on disk-based tables.</span></span> <span data-ttu-id="a5161-112">In una transazione è possibile impostare un livello di isolamento diverso per una raccolta di istruzioni o per una singola operazione di lettura.</span><span class="sxs-lookup"><span data-stu-id="a5161-112">In a transaction, it is possible to set a different isolation level for a collection of statements or for an individual read operation.</span></span>  
  
### <a name="specifying-the-isolation-level-of-individual-operations"></a><span data-ttu-id="a5161-113">Specifica del livello di isolamento di singole operazioni</span><span class="sxs-lookup"><span data-stu-id="a5161-113">Specifying the Isolation Level of Individual Operations</span></span>  
 <span data-ttu-id="a5161-114">Per impostare un livello di isolamento diverso per un set di istruzioni in una transazione, è possibile utilizzare `SET TRANSACTION ISOLATION LEVEL`.</span><span class="sxs-lookup"><span data-stu-id="a5161-114">To set a different isolation level for a set of statements in a transaction, you can use `SET TRANSACTION ISOLATION LEVEL`.</span></span> <span data-ttu-id="a5161-115">Nell'esempio di una transazione riportato di seguito viene utilizzato il livello di isolamento SERIALIZABLE per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="a5161-115">The following example of a transaction uses the serializable isolation level as default.</span></span> <span data-ttu-id="a5161-116">Le operazioni INSERT e SELECT in t3, t2 e t1 vengono eseguite con livello di isolamento REPEATABLE READ.</span><span class="sxs-lookup"><span data-stu-id="a5161-116">The insert and select operations on t3, t2, and t1 are executed under repeatable read isolation.</span></span>  
  
```sql  
set transaction isolation level serializable  
go  
  
begin transaction  
 ......  
  set transaction isolation level repeatable read  
  
  insert t3 select * from t1 join t2 on t1.id=t2.id  
  
  set transaction isolation level serializable  
 ......  
commit  
```  
  
 <span data-ttu-id="a5161-117">Per impostare un livello di isolamento per singole operazioni di lettura diverso da quello predefinito della transazione, è possibile utilizzare un hint di tabella (ad esempio, serializable).</span><span class="sxs-lookup"><span data-stu-id="a5161-117">To set an isolation level for individual read operations that is different from the transaction default, you can use a table hint (for example, serializable).</span></span> <span data-ttu-id="a5161-118">Ogni operazione SELECT corrisponde a un'operazione READ e ogni UPDATE e DELETE corrisponde a un'operazione READ, poiché la riga deve sempre essere letta prima che sia possibile aggiornarla o eliminarla.</span><span class="sxs-lookup"><span data-stu-id="a5161-118">Every select corresponds to a read operation and every update and every delete corresponds to a read, because the row always needs to be read before it can be updated or deleted.</span></span> <span data-ttu-id="a5161-119">Per le operazioni INSERT non è disponibile un livello di isolamento, perché le scritture vengono sempre isolate in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a5161-119">Insert operations do not have an isolation level, because writes are always isolated in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="a5161-120">Nell'esempio seguente il livello di isolamento predefinito per la transazione è READ COMMITTED, ma l'accesso viene effettuato alla tabella t1 con isolamento SERIALIZABLE e alla tabella t2 con isolamento SNAPSHOT.</span><span class="sxs-lookup"><span data-stu-id="a5161-120">In the following example, the default isolation level for the transaction is read committed, but table t1 is accessed under serializable and t2 under snapshot isolation.</span></span>  
  
```sql  
set transaction isolation level read committed  
go  
  
begin transaction  
 ......  
  
  insert t3 select * from t1 (serializable) join t2 (snapshot) on t1.id=t2.id  
  
  ......  
commit  
```  
  
### <a name="isolation-semantics-for-individual-operations"></a><span data-ttu-id="a5161-121">Semantica di isolamento per singole operazioni</span><span class="sxs-lookup"><span data-stu-id="a5161-121">Isolation Semantics for Individual Operations</span></span>  
 <span data-ttu-id="a5161-122">Una transazione T serializzabile viene eseguita in isolamento completo.</span><span class="sxs-lookup"><span data-stu-id="a5161-122">A serializable transaction T is executed in complete isolation.</span></span> <span data-ttu-id="a5161-123">È come se per tutte le altre transazioni fosse stato eseguito il commit prima dell'avvio di T o l'avvio dopo il commit di T.</span><span class="sxs-lookup"><span data-stu-id="a5161-123">It is as if every other transaction has either committed before T started, or is started after T committed.</span></span> <span data-ttu-id="a5161-124">Il comportamento diventa più complesso quando operazioni diverse in una transazione presentano livelli di isolamento diversi.</span><span class="sxs-lookup"><span data-stu-id="a5161-124">It becomes more complex when different operations in a transaction have different isolation levels.</span></span>  
  
 <span data-ttu-id="a5161-125">La semantica generale dei livelli di isolamento delle transazioni in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , insieme alle implicazioni sul blocco, viene illustrata in [set Transaction isolation level &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-transaction-isolation-level-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a5161-125">The general semantics of the transaction isolation levels in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], along with the implications on locking, is explained in [SET TRANSACTION ISOLATION LEVEL &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-transaction-isolation-level-transact-sql).</span></span>  
  
 <span data-ttu-id="a5161-126">Per le transazioni tra contenitori in cui operazioni diverse possono avere livelli di isolamento diversi, è necessario comprendere la semantica di isolamento delle singole operazioni di lettura.</span><span class="sxs-lookup"><span data-stu-id="a5161-126">For cross-container transactions where different operations may have different isolation levels, you need to understand the semantics of isolation of individual read operations.</span></span> <span data-ttu-id="a5161-127">Le operazioni di scrittura sono sempre isolate.</span><span class="sxs-lookup"><span data-stu-id="a5161-127">Write operations are always isolated.</span></span> <span data-ttu-id="a5161-128">Le scritture in transazioni diverse non possono avere un'influenza reciproca.</span><span class="sxs-lookup"><span data-stu-id="a5161-128">Writes in different transactions cannot impact each other.</span></span>  
  
 <span data-ttu-id="a5161-129">Un'operazione di lettura dei dati restituisce un numero di righe che soddisfa una condizione di filtro.</span><span class="sxs-lookup"><span data-stu-id="a5161-129">A data read operation returns a number of rows that satisfy a filter condition.</span></span>  
  
 <span data-ttu-id="a5161-130">Le letture vengono eseguite come parte di una transazione T. i livelli di isolamento per le operazioni di lettura possono essere interpretati in termini di,</span><span class="sxs-lookup"><span data-stu-id="a5161-130">Reads are performed as part of a transaction T. Isolation levels for read operations can be understood in terms of,</span></span>  
  
 <span data-ttu-id="a5161-131">Stato di commit</span><span class="sxs-lookup"><span data-stu-id="a5161-131">Commit Status</span></span>  
 <span data-ttu-id="a5161-132">Lo stato di commit indica se il commit dei dati letti è garantito.</span><span class="sxs-lookup"><span data-stu-id="a5161-132">Commit status refers to whether the data read is guaranteed to be committed.</span></span>  
  
 <span data-ttu-id="a5161-133">Coerenza (transazionale)</span><span class="sxs-lookup"><span data-stu-id="a5161-133">(Transactional) Consistency</span></span>  
 <span data-ttu-id="a5161-134">La coerenza transazionale per un set di letture indica se per tutte le versioni delle righe lette è garantita l'inclusione di aggiornamenti esattamente dallo stesso set di transazioni.</span><span class="sxs-lookup"><span data-stu-id="a5161-134">Transactional consistency for a set of reads refers to whether the row versions read are all guaranteed to include updates from precisely the same set of transactions.</span></span>  
  
 <span data-ttu-id="a5161-135">Garanzie di stabilità per i dati letti fornite automaticamente alla transazione T.</span><span class="sxs-lookup"><span data-stu-id="a5161-135">Stability guarantees the system gives to transaction T about the data read.</span></span>  
 <span data-ttu-id="a5161-136">Stabilità indica se le letture della transazione sono ripetibili.</span><span class="sxs-lookup"><span data-stu-id="a5161-136">Stability refers to whether the transaction's reads are repeatable.</span></span> <span data-ttu-id="a5161-137">ovvero se in caso di ripetizione di tali operazioni verrebbero restituite le stesse righe e le stesse versioni di riga.</span><span class="sxs-lookup"><span data-stu-id="a5161-137">That is, if the reads were repeated would they return the same rows and row versions?</span></span>  
  
 <span data-ttu-id="a5161-138">Alcune garanzie fanno riferimento all'ora di fine logica della transazione.</span><span class="sxs-lookup"><span data-stu-id="a5161-138">Certain guarantees refer to the logical end time of the transaction.</span></span> <span data-ttu-id="a5161-139">L'ora di fine logica è in genere l'ora in cui viene eseguito il commit della transazione nel database.</span><span class="sxs-lookup"><span data-stu-id="a5161-139">In general, the logical end time is the time the transaction is committed to the database.</span></span> <span data-ttu-id="a5161-140">Se la transazione accede a tabelle ottimizzate per la memoria, l'ora di fine logica è tecnicamente l'inizio della fase di convalida.</span><span class="sxs-lookup"><span data-stu-id="a5161-140">If memory-optimized tables are accessed by the transaction, the logical end time is technically the beginning of the validation phase.</span></span> <span data-ttu-id="a5161-141">Per ulteriori informazioni, vedere la discussione relativa alla durata delle transazioni nelle [transazioni nelle tabelle ottimizzate per la memoria](../relational-databases/in-memory-oltp/memory-optimized-tables.md).</span><span class="sxs-lookup"><span data-stu-id="a5161-141">(For more information, see the transaction lifetime discussion in [Transactions in Memory-Optimized Tables](../relational-databases/in-memory-oltp/memory-optimized-tables.md).</span></span>  
  
 <span data-ttu-id="a5161-142">Indipendentemente dal livello di isolamento, in una transazione (T) vengono sempre rilevati i relativi aggiornamenti:</span><span class="sxs-lookup"><span data-stu-id="a5161-142">Regardless of isolation level, a transaction (T) always sees its own updates:</span></span>  
  
 <span data-ttu-id="a5161-143">READ UNCOMMITTED</span><span class="sxs-lookup"><span data-stu-id="a5161-143">READ UNCOMMITTED</span></span>  
 <span data-ttu-id="a5161-144">I dati letti non possono essere sottoposti a commit, né possono essere coerenti o stabili.</span><span class="sxs-lookup"><span data-stu-id="a5161-144">The data read may neither be committed, consistent, or stable.</span></span> <span data-ttu-id="a5161-145">Saranno tuttavia incluse le operazioni di scrittura precedenti eseguite da T.</span><span class="sxs-lookup"><span data-stu-id="a5161-145">However, it will include earlier write operations done by T.</span></span>  
  
 <span data-ttu-id="a5161-146">READ COMMITTED</span><span class="sxs-lookup"><span data-stu-id="a5161-146">READ COMMITTED</span></span>  
 <span data-ttu-id="a5161-147">Per i dati letti verrà eseguito il commit.</span><span class="sxs-lookup"><span data-stu-id="a5161-147">The data read will be committed.</span></span>  
  
 <span data-ttu-id="a5161-148">SNAPSHOT</span><span class="sxs-lookup"><span data-stu-id="a5161-148">SNAPSHOT</span></span>  
 <span data-ttu-id="a5161-149">Tutte le operazioni di lettura eseguite da T nel livello di isolamento SNAPSHOT hanno la stessa ora di lettura logica, che corrisponde all'inizio della transazione.</span><span class="sxs-lookup"><span data-stu-id="a5161-149">All read operations performed by T under snapshot isolation have the same logical read time, which is the beginning of the transaction.</span></span> <span data-ttu-id="a5161-150">Vengono garantiti il commit e la coerenza dei dati letti dall'ora di lettura logica.</span><span class="sxs-lookup"><span data-stu-id="a5161-150">The data read is guaranteed to be committed and consistent as of the logical read time.</span></span> <span data-ttu-id="a5161-151">È garantita la restituzione dello stesso risultato dalla ripetizione di una lettura dall'ora di lettura originale.</span><span class="sxs-lookup"><span data-stu-id="a5161-151">Repeating a read as of the original read time is guaranteed to return the same result.</span></span>  
  
 <span data-ttu-id="a5161-152">REPEATABLE READ</span><span class="sxs-lookup"><span data-stu-id="a5161-152">REPEATABLE READ</span></span>  
 <span data-ttu-id="a5161-153">Vengono garantiti il commit e la stabilità dei dati letti fino all'ora di fine logica della transazione.</span><span class="sxs-lookup"><span data-stu-id="a5161-153">The data read is guaranteed to be committed and stable up to the logical end time of the transaction.</span></span>  
  
 <span data-ttu-id="a5161-154">SERIALIZABLE</span><span class="sxs-lookup"><span data-stu-id="a5161-154">SERIALIZABLE</span></span>  
 <span data-ttu-id="a5161-155">Tutte le garanzie di REPEATable READ e la coerenza delle transazioni e della coerenza transazionale rispetto a tutte le operazioni di lettura serializzabili eseguite da T. Phantom avoid significa che l'operazione di analisi può restituire solo righe aggiuntive scritte da T, ma nessuna riga scritta da altre transazioni.</span><span class="sxs-lookup"><span data-stu-id="a5161-155">All guarantees of REPEATABLE READ plus phantom avoidance and transactional consistency with respect to all serializable read operations performed by T. Phantom avoidance means that the scan operation can only return additional rows that were written by T, but no rows that were written by other transactions.</span></span>  
  
 <span data-ttu-id="a5161-156">Si consideri la transazione seguente:</span><span class="sxs-lookup"><span data-stu-id="a5161-156">Consider the following transaction,</span></span>  
  
```sql  
set transaction isolation level read committed  
go  
  
begin transaction  
  -- remove all rows from t3; the related read operation is performed under read committed   
  -- isolation, as this is the default for the transaction  
  delete from t3  
  
  -- copy the contents from t1 to t3; the read on t1 is performed under the serializable   
  -- isolation level  
  insert t3 select * from t1 (serializable)  
  
  -- compare t3 and t1; note: the result set may not be empty, as rows may have been added   
  -- by other transaction before this select, due to the read committed isolation level  
  select * from t3 except t1  
  
  -- compare t1 and t3; note: the result set is empty, as no rows have been added to t1   
  -- since its contents were copied to t1, due to the serializable isolation level  
  select * from t1 except t3  
commit  
```  
  
 <span data-ttu-id="a5161-157">In questa transazione vengono eliminate tutte le righe da t3 nel livello di isolamento READ COMMITTED, vengono copiate tutte le righe da t1 a t3 nel livello di isolamento SERIALIZABLE, quindi vengono confrontate t1 e t3.</span><span class="sxs-lookup"><span data-stu-id="a5161-157">This transaction deletes all rows from t3 under read committed isolation, copies all rows from t1 to t3 under serializable isolation, and then compares t1 and t3.</span></span> <span data-ttu-id="a5161-158">È possibile che alcune righe [non in t1] siano state aggiunte a t3 poiché la tabella è stata svuotata.</span><span class="sxs-lookup"><span data-stu-id="a5161-158">Some rows [not in t1] may have been added to t3 since the table was emptied.</span></span> <span data-ttu-id="a5161-159">Nessuna riga è stata aggiunta a t1 in quanto la copia era SERIALIZABLE.</span><span class="sxs-lookup"><span data-stu-id="a5161-159">No rows were added to t1 as the copy was serializable.</span></span>  
  
 <span data-ttu-id="a5161-160">Sebbene lettura da t1 alla fine della transazione sia sintatticamente READ COMMITTED, è in effetti SERIALIZABLE, perché la stessa lettura è stata eseguita in precedenza nella transazione nel livello di isolamento SERIALIZABLE: la serializzabilità garantisce che se la lettura viene eseguita in qualsiasi momento successivo della transazione, verranno restituite le stesse righe.</span><span class="sxs-lookup"><span data-stu-id="a5161-160">Although the read from t1 at the end of the transaction is syntactically read committed, it is effectively serializable, because the same read was performed earlier in the transaction under serializable isolation: serializability guarantees that if the read is performed at any later point in the transaction, the same rows are returned.</span></span>  
  
## <a name="cross-container-transactions-and-isolation-levels"></a><span data-ttu-id="a5161-161">Transazioni tra contenitori e livelli di isolamento</span><span class="sxs-lookup"><span data-stu-id="a5161-161">Cross-Container Transactions and Isolation Levels</span></span>  
 <span data-ttu-id="a5161-162">È possibile considerare una transazione tra contenitori come se fosse costituita da due lati: uno basato su disco (per le operazioni nelle tabelle basate su disco) e uno ottimizzato per la memoria (per le operazioni nelle tabelle ottimizzate per la memoria).</span><span class="sxs-lookup"><span data-stu-id="a5161-162">A cross-container transaction can be seen as having two sides: a disk-based side (for operations on disk-based tables) and a memory-optimized side (for operations on memory-optimized tables).</span></span> <span data-ttu-id="a5161-163">Questi due lati possono avere livelli di isolamento diversi.</span><span class="sxs-lookup"><span data-stu-id="a5161-163">These two sides may have different isolation levels.</span></span> <span data-ttu-id="a5161-164">Infatti, alle singole operazioni di lettura in ogni lato possono essere assegnati livelli di isolamento diversi.</span><span class="sxs-lookup"><span data-stu-id="a5161-164">In fact, individual read operations on each side may have different isolation levels.</span></span>  
  
 <span data-ttu-id="a5161-165">Il lato basato su disco di una transazione T specificata raggiunge un determinato livello di isolamento X se viene soddisfatta una delle condizioni indicate di seguito:</span><span class="sxs-lookup"><span data-stu-id="a5161-165">The disk-based side of a given transaction T reaches a certain isolation level X if one of the following conditions is met:</span></span>  
  
-   <span data-ttu-id="a5161-166">Inizia in X. Ovvero, il valore predefinito della sessione è X, perché è stato eseguito `SET TRANSACTION ISOLATION LEVEL` o è l' [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="a5161-166">It starts in X. That is, the session default was X, either because you executed `SET TRANSACTION ISOLATION LEVEL`, or it is the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] default.</span></span>  
  
-   <span data-ttu-id="a5161-167">Durante la transazione il livello di isolamento predefinito viene modificato in X utilizzando `SET TRANSACTION ISOLATION LEVEL`.</span><span class="sxs-lookup"><span data-stu-id="a5161-167">During the transaction, the default isolation level is changed to X using `SET TRANSACTION ISOLATION LEVEL`.</span></span>  
  
-   <span data-ttu-id="a5161-168">Un'operazione di lettura in una tabella basata su disco viene eseguita nel livello di isolamento X, utilizzando la sintassi `WITH (X)`.</span><span class="sxs-lookup"><span data-stu-id="a5161-168">A read operation on a disk-based table is executed under isolation level X, using the syntax `WITH (X)`.</span></span>  
  
 <span data-ttu-id="a5161-169">Il lato ottimizzato per la memoria di T raggiunge un livello di isolamento Y se durante l'esecuzione di T una qualsiasi operazione di lettura in una tabella ottimizzata per la memoria o una stored procedure compilata in modo nativo viene eseguita nel livello di isolamento Y.</span><span class="sxs-lookup"><span data-stu-id="a5161-169">The memory-optimized side of T reaches an isolation level Y if during execution of T, any read operation on a memory-optimized table or any natively compiled stored procedure is executed under isolation level Y.</span></span>  
  
 <span data-ttu-id="a5161-170">Si consideri la transazione di esempio riportata di seguito.</span><span class="sxs-lookup"><span data-stu-id="a5161-170">Consider the following transaction as an example.</span></span> <span data-ttu-id="a5161-171">In questo caso, t1 e t2 sono tabelle basate su disco e t3 e t4 sono tabelle ottimizzate per la memoria.</span><span class="sxs-lookup"><span data-stu-id="a5161-171">Here, t1 and t2 are disk-based tables and t3 and t4 are memory-optimized tables.</span></span>  
  
 <span data-ttu-id="a5161-172">Il lato basato su disco della transazione raggiunge il livello di isolamento READ COMMITTED, perché inizia in tale livello.</span><span class="sxs-lookup"><span data-stu-id="a5161-172">The disk-based side of the transaction reaches the isolation level read committed, because it starts in that level.</span></span> <span data-ttu-id="a5161-173">Il lato basato su disco raggiunge inoltre il livello REPEATABLE READ, in quanto la prima operazione di lettura viene eseguita in tale livello di isolamento.</span><span class="sxs-lookup"><span data-stu-id="a5161-173">The disk-based side also reaches repeatable read, because the first read operation is executed under that isolation level.</span></span> <span data-ttu-id="a5161-174">L'eliminazione alla fine della transazione viene eseguita nel livello di isolamento READ COMMITTED e pertanto non introduce un nuovo livello di isolamento.</span><span class="sxs-lookup"><span data-stu-id="a5161-174">The delete at the end of the transaction is executed under read committed isolation level, and so does not introduce a new isolation level.</span></span>  
  
 <span data-ttu-id="a5161-175">Il lato ottimizzato per la memoria della transazione può raggiungere uno dei due livelli: se condition1 è true, raggiunge il livello SERIALIZABLE, mentre se è false, raggiunge solo l'isolamento SNAPSHOT.</span><span class="sxs-lookup"><span data-stu-id="a5161-175">The memory-optimized side of the transaction can reach one of two levels: if condition1 is true, it reaches serializable, while if it is false, the memory-optimized side reaches only snapshot isolation.</span></span>  
  
```sql  
set transaction isolation level read committed  
go  
  
begin transaction  
  select * from t1 (repeatableread)  
  
  if condition1 begin  
    insert t3 select * from t4 (serializable)  
  end  
  else begin  
    insert t3 select * from t4 (snapshot)  
  end  
  
  delete from t1  
commit  
```  
  
### <a name="supported-isolation-levels-for-cross-container-transactions"></a><span data-ttu-id="a5161-176">Livelli di isolamento supportati per le transazioni tra contenitori</span><span class="sxs-lookup"><span data-stu-id="a5161-176">Supported Isolation Levels for Cross-Container Transactions</span></span>  
 <span data-ttu-id="a5161-177">Sono presenti limitazioni per i livelli di isolamento utilizzati con operazioni in tabelle ottimizzate per la memoria nelle transazioni tra contenitori.</span><span class="sxs-lookup"><span data-stu-id="a5161-177">There are limitations on the isolation levels used with operations on memory-optimized tables in cross-container transactions.</span></span>  
  
 <span data-ttu-id="a5161-178">Le tabelle con ottimizzazione per la memoria supportano i livelli di isolamento SNAPSHOT, REPEATABLE READ e SERIALIZABLE.</span><span class="sxs-lookup"><span data-stu-id="a5161-178">Memory-optimized tables support the isolation levels SNAPSHOT, REPEATABLE READ, and SERIALIZABLE.</span></span> <span data-ttu-id="a5161-179">Per le transazioni in modalità autocommit, nelle tabelle ottimizzate per la memoria è supportato il livello di isolamento READ COMMITTED.</span><span class="sxs-lookup"><span data-stu-id="a5161-179">For autocommit transactions, memory-optimized tables support the isolation level READ COMMITTED.</span></span>  
  
 <span data-ttu-id="a5161-180">Sono supportati gli scenari indicati di seguito:</span><span class="sxs-lookup"><span data-stu-id="a5161-180">The following scenarios are supported:</span></span>  
  
-   <span data-ttu-id="a5161-181">Le transazioni tra contenitori READ UNCOMMITTED, READ COMMITTED e READ_COMMITTED_SNAPSHOT possono accedere alle tabelle ottimizzate per la memoria con livello di isolamento SNAPSHOT, REPEATABLE READ e SERIALIZABLE.</span><span class="sxs-lookup"><span data-stu-id="a5161-181">READ UNCOMMITTED, READ COMMITTED, and READ_COMMITTED_SNAPSHOT cross-container transactions can access memory-optimized tables under SNAPSHOT, REPEATABLE READ, and SERIALIZABLE isolation.</span></span> <span data-ttu-id="a5161-182">Viene rispettata la garanzia READ COMMITTED per la transazione; per tutte le righe lette dalla transazione è stato eseguito il commit nel database.</span><span class="sxs-lookup"><span data-stu-id="a5161-182">The READ COMMITTED guarantee holds for the transaction; all rows read by the transaction have been committed to the database.</span></span>  
  
-   <span data-ttu-id="a5161-183">Le transazioni tra contenitori REPEATABLE READ e SERIALIZABLE possono accedere a tabelle ottimizzate per la memoria con isolamento SNAPSHOT.</span><span class="sxs-lookup"><span data-stu-id="a5161-183">REPEATABLE READ and SERIALIZABLE transactions can access memory-optimized tables under SNAPSHOT isolation.</span></span>  
  
## <a name="read-only-cross-container-transactions"></a><span data-ttu-id="a5161-184">Transazioni tra contenitori di sola lettura</span><span class="sxs-lookup"><span data-stu-id="a5161-184">Read-only Cross-Container Transactions</span></span>  
 <span data-ttu-id="a5161-185">Per la maggior parte delle transazioni di sola lettura in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] viene eseguito il rollback in fase di commit.</span><span class="sxs-lookup"><span data-stu-id="a5161-185">Most read-only transactions in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] are rolled back at commit time.</span></span> <span data-ttu-id="a5161-186">Poiché non sono presenti modifiche di cui eseguire il commit nel database, le risorse utilizzate dalla transazione vengono semplicemente liberate automaticamente.</span><span class="sxs-lookup"><span data-stu-id="a5161-186">Because there are no changes to commit to the database, the system simply frees the resources used by the transaction.</span></span> <span data-ttu-id="a5161-187">Per le transazioni di sola lettura basate su disco, gli eventuali blocchi eseguiti dalla transazione vengono rilasciati in questa fase.</span><span class="sxs-lookup"><span data-stu-id="a5161-187">For read-only disk-based transactions, all locks taken by the transaction are released at this time.</span></span> <span data-ttu-id="a5161-188">Per le transazioni ottimizzate per la memoria di sola lettura che interessano l'esecuzione di una singola stored procedure compilata in modo nativo non viene eseguita alcuna convalida.</span><span class="sxs-lookup"><span data-stu-id="a5161-188">For read-only memory-optimized transactions that span a single natively compiled procedure execution, no validation is performed.</span></span>  
  
 <span data-ttu-id="a5161-189">Per le transazioni tra contenitori di sola lettura nella modalità autocommit viene eseguito semplicemente il rollback alla fine della transazione.</span><span class="sxs-lookup"><span data-stu-id="a5161-189">Cross-container, read-only transactions in autocommit mode are simply rolled back at the end of the transaction.</span></span> <span data-ttu-id="a5161-190">Non viene eseguita alcuna convalida.</span><span class="sxs-lookup"><span data-stu-id="a5161-190">No validation is performed.</span></span>  
  
 <span data-ttu-id="a5161-191">Le transazioni tra contenitori di sola lettura implicite o esplicite eseguono la convalida in fase di commit se la transazione accede alle tabelle ottimizzate per la memoria nell'isolamento REPEATABLE READ o SERIALIZABLE.</span><span class="sxs-lookup"><span data-stu-id="a5161-191">Explicit or implicit cross-container, read-only transactions perform validation at commit time if the transaction accesses memory-optimized tables under REPEATABLE READ or SERIALIZABLE isolation.</span></span> <span data-ttu-id="a5161-192">Per informazioni dettagliate sulla convalida, vedere la sezione relativa ai controlli di rilevamento dei conflitti, convalida e dipendenza di commit nelle [transazioni nelle tabelle ottimizzate](../relational-databases/in-memory-oltp/memory-optimized-tables.md)per la memoria.</span><span class="sxs-lookup"><span data-stu-id="a5161-192">For details about validation see the section on Conflict Detection, Validation, and Commit Dependency Checks in [Transactions in Memory-Optimized Tables](../relational-databases/in-memory-oltp/memory-optimized-tables.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5161-193">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a5161-193">See Also</span></span>  
 <span data-ttu-id="a5161-194">[Informazioni sulle transazioni nelle tabelle ottimizzate per la memoria](../../2014/database-engine/understanding-transactions-on-memory-optimized-tables.md) </span><span class="sxs-lookup"><span data-stu-id="a5161-194">[Understanding Transactions on Memory-Optimized Tables](../../2014/database-engine/understanding-transactions-on-memory-optimized-tables.md) </span></span>  
 <span data-ttu-id="a5161-195">[Linee guida per i livelli di isolamento delle transazioni con tabelle con ottimizzazione per la memoria](../../2014/database-engine/guidelines-for-transaction-isolation-levels-with-memory-optimized-tables.md) </span><span class="sxs-lookup"><span data-stu-id="a5161-195">[Guidelines for Transaction Isolation Levels with Memory-Optimized Tables](../../2014/database-engine/guidelines-for-transaction-isolation-levels-with-memory-optimized-tables.md) </span></span>  
 [<span data-ttu-id="a5161-196">Linee guida per la logica di riesecuzione per le transazioni in tabelle con ottimizzazione per la memoria</span><span class="sxs-lookup"><span data-stu-id="a5161-196">Guidelines for Retry Logic for Transactions on Memory-Optimized Tables</span></span>](../../2014/database-engine/guidelines-for-retry-logic-for-transactions-on-memory-optimized-tables.md)  
  
  
