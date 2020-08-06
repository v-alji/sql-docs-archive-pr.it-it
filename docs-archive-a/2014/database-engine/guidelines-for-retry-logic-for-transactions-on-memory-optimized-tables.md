---
title: Linee guida per la logica di ripetizione tentativi per le transazioni nelle tabelle ottimizzate per la memoria | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: f2a35c37-4449-49ee-8bba-928028f1de66
author: stevestein
ms.author: sstein
ms.openlocfilehash: c9ffaccefb8d4e0a3044c4858a06029fd4350354
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716608"
---
# <a name="guidelines-for-retry-logic-for-transactions-on-memory-optimized-tables"></a><span data-ttu-id="f4f26-102">Linee guida per la logica di riesecuzione per le transazioni in tabelle con ottimizzazione per la memoria</span><span class="sxs-lookup"><span data-stu-id="f4f26-102">Guidelines for Retry Logic for Transactions on Memory-Optimized Tables</span></span>
  <span data-ttu-id="f4f26-103">Esistono condizioni di errore che si verificano con le transazioni che accedono a tabelle ottimizzate per la memoria.</span><span class="sxs-lookup"><span data-stu-id="f4f26-103">There are error conditions that occur with transactions that access memory-optimized tables.</span></span>  
  
-   41302. <span data-ttu-id="f4f26-104">Tentativo da parte della transazione corrente di aggiornare un record che è già stato aggiornato dopo l'avvio della transazione.</span><span class="sxs-lookup"><span data-stu-id="f4f26-104">The current transaction attempted to update a record that has been updated since the transaction started.</span></span>  
  
-   41305. <span data-ttu-id="f4f26-105">Impossibile eseguire il commit della transazione corrente a causa di un errore di convalida di lettura ripetibile.</span><span class="sxs-lookup"><span data-stu-id="f4f26-105">The current transaction failed to commit due to a repeatable read validation failure.</span></span>  
  
-   41325. <span data-ttu-id="f4f26-106">Impossibile eseguire il commit della transazione corrente a causa di un errore di convalida serializzabile.</span><span class="sxs-lookup"><span data-stu-id="f4f26-106">The current transaction failed to commit due to a serializable validation failure.</span></span>  
  
-   41301. <span data-ttu-id="f4f26-107">Una transazione precedente da cui dipende la transazione corrente è stata interrotta. Impossibile eseguire il commit della transazione corrente.</span><span class="sxs-lookup"><span data-stu-id="f4f26-107">A previous transaction that the current transaction took a dependency on has aborted, and the current transaction can no longer commit.</span></span>  
  
 <span data-ttu-id="f4f26-108">Una causa comune di questi errori è con una transazione eseguita simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="f4f26-108">A common cause of these errors is interference between concurrently executing transaction.</span></span> <span data-ttu-id="f4f26-109">L'azione correttiva normale consiste nel ripetere la transazione.</span><span class="sxs-lookup"><span data-stu-id="f4f26-109">The common corrective action is to retry the transaction.</span></span>  
  
 <span data-ttu-id="f4f26-110">Per ulteriori informazioni su queste condizioni di errore, vedere la sezione relativa ai controlli di rilevamento dei conflitti, convalida e dipendenza di commit nelle [transazioni nelle tabelle ottimizzate](../relational-databases/in-memory-oltp/memory-optimized-tables.md)per la memoria.</span><span class="sxs-lookup"><span data-stu-id="f4f26-110">For more information about these error conditions, see the section on Conflict Detection, Validation, and Commit Dependency Checks in [Transactions in Memory-Optimized Tables](../relational-databases/in-memory-oltp/memory-optimized-tables.md).</span></span>  
  
 <span data-ttu-id="f4f26-111">I deadlock (codice di errore 1205) non possono verificarsi per le tabelle ottimizzate per la memoria.</span><span class="sxs-lookup"><span data-stu-id="f4f26-111">Deadlocks (error code 1205) cannot occur for memory-optimized tables.</span></span> <span data-ttu-id="f4f26-112">I blocchi non vengono utilizzati per le tabelle ottimizzate per la memoria.</span><span class="sxs-lookup"><span data-stu-id="f4f26-112">Locks are not used for memory-optimized tables.</span></span> <span data-ttu-id="f4f26-113">Se tuttavia nell'applicazione è già presente la logica di riesecuzione per i deadlock, la logica esistente può essere estesa in modo da includere i nuovi codici di errore.</span><span class="sxs-lookup"><span data-stu-id="f4f26-113">However, if the application already contains retry logic for deadlocks, the existing logic could be extended to include the new error codes.</span></span>  
  
## <a name="considerations-for-retrying"></a><span data-ttu-id="f4f26-114">Considerazioni sulla riesecuzione</span><span class="sxs-lookup"><span data-stu-id="f4f26-114">Considerations for Retrying</span></span>  
 <span data-ttu-id="f4f26-115">Nelle applicazioni si verificano in genere conflitti tra le transazioni ed è necessario implementare la logica di riesecuzione per risolverli.</span><span class="sxs-lookup"><span data-stu-id="f4f26-115">Applications will typically encounter conflicts between transactions and need to implement retry logic to resolve those conflicts.</span></span> <span data-ttu-id="f4f26-116">Il numero di conflitti rilevati dipende da una serie di fattori:</span><span class="sxs-lookup"><span data-stu-id="f4f26-116">The number of conflicts encountered depends on a number of factors:</span></span>  
  
-   <span data-ttu-id="f4f26-117">Contesa per singole righe.</span><span class="sxs-lookup"><span data-stu-id="f4f26-117">Contention for individual rows.</span></span> <span data-ttu-id="f4f26-118">Il rischio di conflitti aumenta man mano che aumenta il numero di transazioni che tenta di aggiornare la stessa riga.</span><span class="sxs-lookup"><span data-stu-id="f4f26-118">The potential for conflicts increases as the number of transactions attempting to update the same row increases.</span></span>  
  
-   <span data-ttu-id="f4f26-119">Numero di righe lette dalle transazioni REPEATABLE READ.</span><span class="sxs-lookup"><span data-stu-id="f4f26-119">Number of rows read by REPEATABLE READ transactions.</span></span> <span data-ttu-id="f4f26-120">Più righe vengono lette, maggiore è la probabilità che alcune di queste righe vengano aggiornate da transazioni simultanee.</span><span class="sxs-lookup"><span data-stu-id="f4f26-120">The more rows read, the greater the chance that some of these rows are updated by concurrent transactions.</span></span> <span data-ttu-id="f4f26-121">Questa condizione causa errori di convalida di lettura ripetibili.</span><span class="sxs-lookup"><span data-stu-id="f4f26-121">This causes repeatable read validation failures.</span></span>  
  
-   <span data-ttu-id="f4f26-122">Dimensioni degli intervalli di analisi utilizzati dalle transazioni SERIALIZABLE.</span><span class="sxs-lookup"><span data-stu-id="f4f26-122">Size of the scan ranges used by SERIALIZABLE transactions.</span></span> <span data-ttu-id="f4f26-123">Maggiori sono le dimensioni degli intervalli di analisi, maggiore è la probabilità che le transazioni simultanee introducano righe fantasma, causando errori di convalida serializzabili.</span><span class="sxs-lookup"><span data-stu-id="f4f26-123">The larger the scan ranges, the higher the chance that concurrent transactions will introduce phantom rows, causing serializable validation failures.</span></span>  
  
     <span data-ttu-id="f4f26-124">È difficile evitare questi conflitti in un'applicazione, pertanto è necessaria la logica di riesecuzione.</span><span class="sxs-lookup"><span data-stu-id="f4f26-124">It is difficult for an application to avoid these conflicts, requiring retry logic.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="f4f26-125">Le transazioni di lettura e scrittura che accedono a tabelle ottimizzate per la memoria richiedono la logica di riesecuzione.</span><span class="sxs-lookup"><span data-stu-id="f4f26-125">Read-write transactions that access memory-optimized tables require retry logic.</span></span>  
  
### <a name="considerations-for-read-only-transactions-and-natively-compiled-stored-procedures"></a><span data-ttu-id="f4f26-126">Considerazioni sulle transazioni di sola lettura e sulle stored procedure compilate in modo nativo</span><span class="sxs-lookup"><span data-stu-id="f4f26-126">Considerations for Read-Only Transactions and Natively Compiled Stored Procedures</span></span>  
 <span data-ttu-id="f4f26-127">Le transazioni di sola lettura che interessano una singola esecuzione di una stored procedure compilata in modo nativo non richiedono la convalida per le transazioni REPEATABLE READ e SERIALIZABLE.</span><span class="sxs-lookup"><span data-stu-id="f4f26-127">Read-only transactions that span a single execution of a natively compiled stored procedure do not require validation for REPEATABLE READ and SERIALIZABLE transactions.</span></span> <span data-ttu-id="f4f26-128">I conflitti di scrittura non possono verificarsi a causa di una transazione di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="f4f26-128">Write conflicts cannot occur due to a transaction being read-only.</span></span>  
  
 <span data-ttu-id="f4f26-129">Gli errori di dipendenza possono tuttavia continuare a verificarsi.</span><span class="sxs-lookup"><span data-stu-id="f4f26-129">However, dependency failures can still occur.</span></span> <span data-ttu-id="f4f26-130">Gli errori di dipendenza sono meno comuni degli errori risultanti da conflitti.</span><span class="sxs-lookup"><span data-stu-id="f4f26-130">Dependency failures are rarer than errors resulting from conflicts.</span></span> <span data-ttu-id="f4f26-131">In molti casi non è quindi richiesta logica di riesecuzione specifica per le transazioni di sola lettura che interessano singole esecuzioni di stored procedure compilate in modo nativo.</span><span class="sxs-lookup"><span data-stu-id="f4f26-131">Therefore, in many cases, specific retry logic is not required for read-only transactions that span single executions of natively compiled stored procedures.</span></span>  
  
### <a name="considerations-for-read-only-transactions-and-cross-container-transactions"></a><span data-ttu-id="f4f26-132">Considerazioni sulle transazioni di sola lettura e sulle transazioni tra contenitori</span><span class="sxs-lookup"><span data-stu-id="f4f26-132">Considerations for Read-Only Transactions and Cross-Container Transactions</span></span>  
 <span data-ttu-id="f4f26-133">Per le transazioni di sola lettura tra contenitori, ovvero transazioni che vengono avviate al di fuori del contesto di una stored procedure compilata in modo nativo, non viene eseguita la convalida se l'accesso alle tabelle ottimizzate per la memoria avviene nel livello di isolamento SNAPSHOT.</span><span class="sxs-lookup"><span data-stu-id="f4f26-133">Read-only cross-container transactions, which are transactions that are started outside the context of a natively compiled stored procedure, do not perform validation if the memory-optimized tables are all accessed under SNAPSHOT isolation.</span></span> <span data-ttu-id="f4f26-134">Quando tuttavia si accede alle tabelle ottimizzate per la memoria nell'isolamento REPEATABLE READ o SERIALIZABLE, la convalida viene eseguita in fase di commit.</span><span class="sxs-lookup"><span data-stu-id="f4f26-134">However, when memory-optimized tables are accessed under REPEATABLE READ or SERIALIZABLE isolation, validation is performed at commit time.</span></span> <span data-ttu-id="f4f26-135">In questo caso, potrebbe essere richiesta la logica di riesecuzione.</span><span class="sxs-lookup"><span data-stu-id="f4f26-135">In this case, retry logic may be required.</span></span>  
  
 <span data-ttu-id="f4f26-136">Per ulteriori informazioni, vedere la sezione relativa alle transazioni tra contenitori nei [livelli di isolamento delle transazioni](../../2014/database-engine/transaction-isolation-levels.md).</span><span class="sxs-lookup"><span data-stu-id="f4f26-136">For more information, see the section on Cross-Container Transactions in [Transaction Isolation Levels](../../2014/database-engine/transaction-isolation-levels.md).</span></span>  
  
## <a name="implementing-retry-logic"></a><span data-ttu-id="f4f26-137">Implementare della logica di riesecuzione</span><span class="sxs-lookup"><span data-stu-id="f4f26-137">Implementing Retry Logic</span></span>  
 <span data-ttu-id="f4f26-138">Come per tutte le transazioni che accedono a tabelle ottimizzate per la memoria, è necessario considerare la logica di riesecuzione per gestire possibili errori, ad esempio conflitti di scrittura (codice di errore 41302) o errori di dipendenza (codice di errore 41301).</span><span class="sxs-lookup"><span data-stu-id="f4f26-138">As with all transactions that access memory-optimized tables, you need to consider retry logic to handle potential failures, such as write conflicts (error code 41302) or dependency failures (error code 41301).</span></span> <span data-ttu-id="f4f26-139">Nella maggior parte delle applicazioni il tasso di errori sarà basso, ma è comunque necessario gestire gli errori rieseguendo la transazione.</span><span class="sxs-lookup"><span data-stu-id="f4f26-139">In most applications the failure rate will be low, but it is still necessary to handle failures by retrying the transaction.</span></span> <span data-ttu-id="f4f26-140">È consigliabile implementare la logica di riesecuzione nei due modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="f4f26-140">Two suggested ways of implementing retry logic are:</span></span>  
  
-   <span data-ttu-id="f4f26-141">Tentativi sul lato client.</span><span class="sxs-lookup"><span data-stu-id="f4f26-141">Client-side retries.</span></span> <span data-ttu-id="f4f26-142">I tentativi sul lato client costituiscono il modo consigliato per implementare la logica di riesecuzione nel caso generale.</span><span class="sxs-lookup"><span data-stu-id="f4f26-142">Client-side retries is the preferred way to implement retry logic in the general case.</span></span> <span data-ttu-id="f4f26-143">L'applicazione client rileva l'errore generato dalla transazione e riesegue la transazione.</span><span class="sxs-lookup"><span data-stu-id="f4f26-143">The client application catches the error thrown by the transaction, and retries the transaction.</span></span> <span data-ttu-id="f4f26-144">Se un'applicazione client esistente dispone di una logica di riesecuzione per la gestione di deadlock, è possibile estendere l'applicazione per gestire i nuovi codici di errore.</span><span class="sxs-lookup"><span data-stu-id="f4f26-144">If an existing client application has retry logic to handle deadlocks, you can extend the application to handle the new error codes.</span></span>  
  
-   <span data-ttu-id="f4f26-145">Utilizzo di una stored procedure del wrapper.</span><span class="sxs-lookup"><span data-stu-id="f4f26-145">Using a wrapper stored procedure.</span></span> <span data-ttu-id="f4f26-146">Il client chiama una stored procedure [!INCLUDE[tsql](../includes/tsql-md.md)] interpretata che chiama la stored procedure compilata in modo nativo oppure esegue la transazione.</span><span class="sxs-lookup"><span data-stu-id="f4f26-146">The client calls an interpreted [!INCLUDE[tsql](../includes/tsql-md.md)] stored procedure that calls the natively compiled stored procedure or executes the transaction.</span></span> <span data-ttu-id="f4f26-147">La procedura del wrapper utilizza la logica try/catch per rilevare l'errore e per ripetere la chiamata di procedura, se necessario.</span><span class="sxs-lookup"><span data-stu-id="f4f26-147">The wrapper procedure then uses try/catch logic to catch the error and retry the procedure call if needed.</span></span> <span data-ttu-id="f4f26-148">È possibile che i risultati vengano restituiti al client prima dell'errore e che il client non sia in grado di rimuoverli.</span><span class="sxs-lookup"><span data-stu-id="f4f26-148">It is possible that results are returned to the client before the failure, and the client would not know to discard them.</span></span> <span data-ttu-id="f4f26-149">Per essere sicuri, è pertanto preferibile utilizzare questo metodo solo con le stored procedure compilate in modo nativo che non restituiscono alcun set di risultati al client.</span><span class="sxs-lookup"><span data-stu-id="f4f26-149">Therefore, to be safe, it is best to use this method only with natively compiled stored procedures that do not return any result sets to the client.</span></span>  
  
 <span data-ttu-id="f4f26-150">La logica di riesecuzione può essere implementata in [!INCLUDE[tsql](../includes/tsql-md.md)] o nel livello intermedio del codice di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f4f26-150">The retry logic can be implemented either in [!INCLUDE[tsql](../includes/tsql-md.md)] or in the application code in the mid-tier.</span></span>  
  
 <span data-ttu-id="f4f26-151">Di seguito sono indicate due possibili motivi per considerare la logica di riesecuzione:</span><span class="sxs-lookup"><span data-stu-id="f4f26-151">Two possible reasons to consider the retry logic are:</span></span>  
  
-   <span data-ttu-id="f4f26-152">L'applicazione client dispone di logica di riesecuzione per altri codici di errore, ad esempio 1205, che è possibile estendere.</span><span class="sxs-lookup"><span data-stu-id="f4f26-152">The client application has retry logic for other error codes, such as 1205, which you can extend.</span></span>  
  
-   <span data-ttu-id="f4f26-153">I conflitti sono rari ed è importante ridurre la latenza end-to-end mediante un'esecuzione preparata.</span><span class="sxs-lookup"><span data-stu-id="f4f26-153">Conflicts are rare, and it is important to reduce end-to-end latency by using prepared execution.</span></span> <span data-ttu-id="f4f26-154">Per ulteriori informazioni sull'esecuzione diretta di stored procedure compilate in modo nativo, vedere [stored procedure compilate](../relational-databases/in-memory-oltp/natively-compiled-stored-procedures.md)in modo nativo.</span><span class="sxs-lookup"><span data-stu-id="f4f26-154">For more information about executing natively compiled stored procedures directly, see [Natively Compiled Stored Procedures](../relational-databases/in-memory-oltp/natively-compiled-stored-procedures.md).</span></span>  
  
 <span data-ttu-id="f4f26-155">Nell'esempio seguente viene illustrata la logica di riesecuzione in una stored procedure [!INCLUDE[tsql](../includes/tsql-md.md)] interpretata che contiene una chiamata a una stored procedure compilata in modo nativo o a una transazione tra contenitori.</span><span class="sxs-lookup"><span data-stu-id="f4f26-155">The following sample shows retry logic in an interpreted [!INCLUDE[tsql](../includes/tsql-md.md)] stored procedure that contains a call either to a natively compiled stored procedure or to a cross-container transaction.</span></span>  
  
```sql  
CREATE PROCEDURE usp_my_procedure @param1 type1, @param2 type2, ...  
AS  
BEGIN  
  -- number of retries - tune based on the workload  
  DECLARE @retry INT = 10  
  
  WHILE (@retry > 0)  
  BEGIN  
    BEGIN TRY  
  
      -- exec usp_my_native_proc @param1, @param2, ...  
  
      --       or  
  
      -- BEGIN TRANSACTION  
      --   ...  
      -- COMMIT TRANSACTION  
  
      SET @retry = 0  
    END TRY  
    BEGIN CATCH  
      SET @retry -= 1  
  
      -- the error number for deadlocks (1205) does not need to be included for   
      -- transactions that do not access disk-based tables  
      IF (@retry > 0 AND error_number() in (41302, 41305, 41325, 41301, 1205))  
      BEGIN  
        -- these error conditions are transaction dooming - rollback the transaction  
        -- this is not needed if the transaction spans a single native proc execution  
        --   as the native proc will simply rollback when an error is thrown   
        IF XACT_STATE() = -1  
          ROLLBACK TRANSACTION  
  
        -- use a delay if there is a high rate of write conflicts (41302)  
        --   length of delay should depend on the typical duration of conflicting transactions  
        -- WAITFOR DELAY '00:00:00.001'  
      END  
      ELSE  
      BEGIN  
        -- insert custom error handling for other error conditions here  
  
        -- throw if this is not a qualifying error condition  
        ;THROW  
      END  
    END CATCH  
  END  
END  
```  
  
## <a name="see-also"></a><span data-ttu-id="f4f26-156">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f4f26-156">See Also</span></span>  
 <span data-ttu-id="f4f26-157">[Informazioni sulle transazioni nelle tabelle ottimizzate per la memoria](../../2014/database-engine/understanding-transactions-on-memory-optimized-tables.md) </span><span class="sxs-lookup"><span data-stu-id="f4f26-157">[Understanding Transactions on Memory-Optimized Tables](../../2014/database-engine/understanding-transactions-on-memory-optimized-tables.md) </span></span>  
 <span data-ttu-id="f4f26-158">[Transazioni nelle tabelle con ottimizzazione per la memoria](../relational-databases/in-memory-oltp/memory-optimized-tables.md) </span><span class="sxs-lookup"><span data-stu-id="f4f26-158">[Transactions in Memory-Optimized Tables](../relational-databases/in-memory-oltp/memory-optimized-tables.md) </span></span>  
 [<span data-ttu-id="f4f26-159">Linee guida per i livelli di isolamento delle transazioni con tabelle con ottimizzazione per la memoria</span><span class="sxs-lookup"><span data-stu-id="f4f26-159">Guidelines for Transaction Isolation Levels with Memory-Optimized Tables</span></span>](../../2014/database-engine/guidelines-for-transaction-isolation-levels-with-memory-optimized-tables.md)  
  
  
