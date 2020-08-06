---
title: Blocchi atomici | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 40e0e749-260c-4cfc-a848-444d30c09d85
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: ca8f5b4d767ef0fe836cd260f8d12dd5b40c75d0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624711"
---
# <a name="atomic-blocks"></a><span data-ttu-id="b54e6-102">Blocchi atomici</span><span class="sxs-lookup"><span data-stu-id="b54e6-102">Atomic Blocks</span></span>
  <span data-ttu-id="b54e6-103">`BEGIN ATOMIC` fa parte dello standard SQL ANSI.</span><span class="sxs-lookup"><span data-stu-id="b54e6-103">`BEGIN ATOMIC` is part of the ANSI SQL standard.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="b54e6-104">supporta i blocchi atomici solo al livello superiore delle stored procedure compilate in modo nativo.</span><span class="sxs-lookup"><span data-stu-id="b54e6-104">supports atomic blocks only at the top-level of natively compiled stored procedures.</span></span>  
  
-   <span data-ttu-id="b54e6-105">Ogni stored procedure compilata in modo nativo contiene un blocco di istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b54e6-105">Every natively compiled stored procedure contains exactly one block of [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="b54e6-106">Si tratta di un blocco ATOMIC.</span><span class="sxs-lookup"><span data-stu-id="b54e6-106">This is an ATOMIC block.</span></span>  
  
-   <span data-ttu-id="b54e6-107">Le stored procedure [!INCLUDE[tsql](../../includes/tsql-md.md)] interpretate e non native e i batch ad hoc non supportano i blocchi atomici.</span><span class="sxs-lookup"><span data-stu-id="b54e6-107">Non-native, interpreted [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedures and ad hoc batches do not support atomic blocks.</span></span>  
  
 <span data-ttu-id="b54e6-108">I blocchi atomici vengono eseguiti (in modo atomico) nella transazione.</span><span class="sxs-lookup"><span data-stu-id="b54e6-108">Atomic blocks are executed (atomically) within the transaction.</span></span> <span data-ttu-id="b54e6-109">Tutte le istruzioni nel blocco devono avere esito positivo, altrimenti verrà eseguito il rollback dell'intero blocco al punto di salvataggio creato all'inizio del blocco.</span><span class="sxs-lookup"><span data-stu-id="b54e6-109">Either all statements in the block succeed or the entire block will be rolled back to the savepoint that was created at the start of the block.</span></span> <span data-ttu-id="b54e6-110">Inoltre, per il blocco atomico tutte le impostazioni di sessione sono fisse.</span><span class="sxs-lookup"><span data-stu-id="b54e6-110">In addition, the session settings are fixed for the atomic block.</span></span> <span data-ttu-id="b54e6-111">L'esecuzione dello stesso blocco atomico in sessioni con impostazioni diverse genera lo stesso comportamento, indipendentemente dalle impostazioni della sessione corrente.</span><span class="sxs-lookup"><span data-stu-id="b54e6-111">Executing the same atomic block in sessions with different settings will result in the same behavior, independent of the settings of the current session.</span></span>  
  
## <a name="transactions-and-error-handling"></a><span data-ttu-id="b54e6-112">Transazioni e gestione degli errori</span><span class="sxs-lookup"><span data-stu-id="b54e6-112">Transactions and Error Handling</span></span>  
 <span data-ttu-id="b54e6-113">Se in una sessione esiste già una transazione (perché un batch ha eseguito un'istruzione `BEGIN TRANSACTION` e la transazione rimane attiva), l'avvio di un blocco atomico creerà un punto di salvataggio nella transazione.</span><span class="sxs-lookup"><span data-stu-id="b54e6-113">If a transaction already exists on a session (because a batch executed a `BEGIN TRANSACTION` statement and the transaction remains active), then starting an atomic block will create a savepoint in the transaction.</span></span> <span data-ttu-id="b54e6-114">Se il blocco viene chiuso senza un'eccezione, viene eseguito il commit del punto di salvataggio creato per il blocco, ma non verrà eseguito il commit della transazione finché non viene eseguito il commit a livello di sessione.</span><span class="sxs-lookup"><span data-stu-id="b54e6-114">If the block exits without an exception, the savepoint that was created for the block commits, but the transaction will not commit until the transaction at the session level commits.</span></span> <span data-ttu-id="b54e6-115">Se il blocco genera un'eccezione, viene eseguito il rollback degli effetti del blocco, ma la transazione procede a livello di sessione, a meno che l'eccezione non la termini.</span><span class="sxs-lookup"><span data-stu-id="b54e6-115">If the block throws an exception, the effects of the block are rolled back but the transaction at the session level will proceed, unless the exception is transaction-dooming.</span></span> <span data-ttu-id="b54e6-116">Ad esempio, un conflitto di scrittura comporta la fine della transazione, ma non un errore di cast del tipo.</span><span class="sxs-lookup"><span data-stu-id="b54e6-116">For example a write conflict is transaction-dooming, but not a type casting error.</span></span>  
  
 <span data-ttu-id="b54e6-117">Se non è presente alcuna transazione attiva in una sessione, `BEGIN ATOMIC` avvia una nuova transazione.</span><span class="sxs-lookup"><span data-stu-id="b54e6-117">If there is no active transaction on a session, `BEGIN ATOMIC` will start a new transaction.</span></span> <span data-ttu-id="b54e6-118">Se non viene generata alcuna eccezione all'esterno dell'ambito del blocco, verrà eseguito il commit della transazione alla fine del blocco.</span><span class="sxs-lookup"><span data-stu-id="b54e6-118">If no exception is thrown outside the scope of the block, the transaction will be committed at the end of the block.</span></span> <span data-ttu-id="b54e6-119">Se il blocco genera un'eccezione (l'eccezione non viene rilevata e gestita nel blocco), verrà eseguito il rollback della transazione.</span><span class="sxs-lookup"><span data-stu-id="b54e6-119">If the block throws an exception (that is, the exception is not caught and handled within the block), the transaction will be rolled back.</span></span> <span data-ttu-id="b54e6-120">Per le transazioni che interessano un singolo blocco atomico (una singola stored procedure compilata in modo nativo), non è necessario scrivere istruzioni `BEGIN TRANSACTION` e `COMMIT` o `ROLLBACK` esplicite.</span><span class="sxs-lookup"><span data-stu-id="b54e6-120">For transactions that span a single atomic block (a single natively compiled stored procedure), you do not need to write explicit `BEGIN TRANSACTION` and `COMMIT` or `ROLLBACK` statements.</span></span>  
  
 <span data-ttu-id="b54e6-121">Le stored procedure compilate in modo nativo supportano i costrutti `TRY`, `CATCH` e `THROW` per la gestione degli errori.</span><span class="sxs-lookup"><span data-stu-id="b54e6-121">Natively compiled stored procedures support the `TRY`, `CATCH`, and `THROW` constructs for error handling.</span></span> <span data-ttu-id="b54e6-122">`RAISERROR` non è supportato.</span><span class="sxs-lookup"><span data-stu-id="b54e6-122">`RAISERROR` is not supported.</span></span>  
  
 <span data-ttu-id="b54e6-123">Nell'esempio seguente viene illustrato il comportamento della gestione degli errori con blocchi atomici e stored procedure compilate in modo nativo:</span><span class="sxs-lookup"><span data-stu-id="b54e6-123">The following example illustrates the error handling behavior with atomic blocks and natively compiled stored procedures:</span></span>  
  
```sql  
-- sample table  
CREATE TABLE dbo.t1 (  
  c1 int not null primary key nonclustered  
)  
WITH (MEMORY_OPTIMIZED=ON)  
GO  
  
-- sample proc that inserts 2 rows  
CREATE PROCEDURE dbo.usp_t1 @v1 bigint not null, @v2 bigint not null  
WITH NATIVE_COMPILATION, SCHEMABINDING, EXECUTE AS OWNER  
AS  
BEGIN ATOMIC  
WITH (TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE = N'us_english', DELAYED_DURABILITY = ON)  
  
  INSERT dbo.t1 VALUES (@v1)  
  INSERT dbo.t1 VALUES (@v2)  
  
END  
GO  
  
-- insert two rows  
EXEC dbo.usp_t1 1, 2  
GO  
  
-- verify we have no active transaction  
SELECT @@TRANCOUNT  
GO  
  
-- verify the rows 1 and 2 were committed  
SELECT c1 FROM dbo.t1  
GO  
  
-- execute proc with arithmetic overflow  
EXEC dbo.usp_t1 3, 4444444444444  
GO  
-- expected error message:  
-- Msg 8115, Level 16, State 0, Procedure usp_t1  
-- Arithmetic overflow error converting bigint to data type int.  
  
-- verify we have no active transaction  
SELECT @@TRANCOUNT  
GO  
  
-- verify rows 3 was not committed; usp_t1 has been rolled back  
SELECT c1 FROM dbo.t1  
GO  
  
-- start a new transaction  
BEGIN TRANSACTION  
  -- insert rows 3 and 4  
  EXEC dbo.usp_t1 3, 4  
  
  -- verify there is still an active transaction  
  SELECT @@TRANCOUNT  
  
  -- verify the rows 3 and 4 were inserted  
  SELECT c1 FROM dbo.t1 WITH (SNAPSHOT)   
  ORDER BY c1  
  
  -- catch the arithmetic overflow error  
  BEGIN TRY  
    EXEC dbo.usp_t1 5, 4444444444444  
  END TRY  
  BEGIN CATCH  
    PRINT N'Error occurred: ' + error_message()  
  END CATCH  
  
  -- verify there is still an active transaction  
  SELECT @@TRANCOUNT  
  
  -- verify rows 3 and 4 are still in the table, and row 5 has not been inserted  
  SELECT c1 FROM dbo.t1 WITH (SNAPSHOT)   
  ORDER BY c1  
  
COMMIT  
GO  
  
-- verify we have no active transaction  
SELECT @@TRANCOUNT  
GO  
  
-- verify rows 3 and 4 has been committed  
SELECT c1 FROM dbo.t1  
ORDER BY c1  
GO  
```  
  
 <span data-ttu-id="b54e6-124">I messaggi di errore seguenti specifici delle tabelle ottimizzate per la memoria comportano la fine della transazione.</span><span class="sxs-lookup"><span data-stu-id="b54e6-124">The following error messages specific to memory-optimized tables are transaction dooming.</span></span> <span data-ttu-id="b54e6-125">Se si verificano nell'ambito di un blocco atomico, causano l'interruzione della transazione: 10772, 41301, 41302, 41305, 41325, 41332 e 41333.</span><span class="sxs-lookup"><span data-stu-id="b54e6-125">If they occur in the scope of an atomic block, they will cause the transaction to abort: 10772, 41301, 41302, 41305, 41325, 41332, and 41333.</span></span>  
  
## <a name="session-settings"></a><span data-ttu-id="b54e6-126">Impostazioni sessione</span><span class="sxs-lookup"><span data-stu-id="b54e6-126">Session Settings</span></span>  
 <span data-ttu-id="b54e6-127">Le impostazioni di sessione nei blocchi atomici sono fisse quando la stored procedure è compilata.</span><span class="sxs-lookup"><span data-stu-id="b54e6-127">The session settings in atomic blocks are fixed when the stored procedure is compiled.</span></span> <span data-ttu-id="b54e6-128">Alcune impostazioni possono essere specificate con `BEGIN ATOMIC`, mentre altre sono sempre fisse sullo stesso valore.</span><span class="sxs-lookup"><span data-stu-id="b54e6-128">Some settings can be specified with `BEGIN ATOMIC` while other settings are always fixed to the same value.</span></span>  
  
 <span data-ttu-id="b54e6-129">Le opzioni seguenti sono necessarie con `BEGIN ATOMIC`:</span><span class="sxs-lookup"><span data-stu-id="b54e6-129">The following options are required with `BEGIN ATOMIC`:</span></span>  
  
|<span data-ttu-id="b54e6-130">Impostazione necessaria</span><span class="sxs-lookup"><span data-stu-id="b54e6-130">Required Setting</span></span>|<span data-ttu-id="b54e6-131">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b54e6-131">Description</span></span>|  
|----------------------|-----------------|  
|`TRANSACTION ISOLATION LEVEL`|<span data-ttu-id="b54e6-132">I valori supportati sono `SNAPSHOT`, `REPEATABLEREAD` e `SERIALIZABLE`.</span><span class="sxs-lookup"><span data-stu-id="b54e6-132">Supported values are `SNAPSHOT`, `REPEATABLEREAD`, and `SERIALIZABLE`.</span></span>|  
|`LANGUAGE`|<span data-ttu-id="b54e6-133">Determina i formati data e ora e i messaggi di sistema.</span><span class="sxs-lookup"><span data-stu-id="b54e6-133">Determines date and time formats and system messages.</span></span> <span data-ttu-id="b54e6-134">Tutti i linguaggi e gli alias in [sys.syslanguages &#40;Transact-SQL&#41;](/sql/relational-databases/system-compatibility-views/sys-syslanguages-transact-sql) sono supportati.</span><span class="sxs-lookup"><span data-stu-id="b54e6-134">All languages and aliases in [sys.syslanguages &#40;Transact-SQL&#41;](/sql/relational-databases/system-compatibility-views/sys-syslanguages-transact-sql) are supported.</span></span>|  
  
 <span data-ttu-id="b54e6-135">Le impostazioni seguenti sono facoltative:</span><span class="sxs-lookup"><span data-stu-id="b54e6-135">The following settings are optional:</span></span>  
  
|<span data-ttu-id="b54e6-136">Impostazione facoltativa</span><span class="sxs-lookup"><span data-stu-id="b54e6-136">Optional Setting</span></span>|<span data-ttu-id="b54e6-137">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b54e6-137">Description</span></span>|  
|----------------------|-----------------|  
|`DATEFORMAT`|<span data-ttu-id="b54e6-138">Tutti i formati data di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sono supportati.</span><span class="sxs-lookup"><span data-stu-id="b54e6-138">All [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] date formats are supported.</span></span> <span data-ttu-id="b54e6-139">Quando viene specificata, `DATEFORMAT` esegue l'override del formato data predefinito associato a `LANGUAGE`.</span><span class="sxs-lookup"><span data-stu-id="b54e6-139">When specified, `DATEFORMAT` overrides the default date format associated with `LANGUAGE`.</span></span>|  
|`DATEFIRST`|<span data-ttu-id="b54e6-140">Quando viene specificata, `DATEFIRST` esegue l'override dell'impostazione predefinita associata a `LANGUAGE`.</span><span class="sxs-lookup"><span data-stu-id="b54e6-140">When specified, `DATEFIRST` overrides the default associated with `LANGUAGE`.</span></span>|  
|`DELAYED_DURABILITY`|<span data-ttu-id="b54e6-141">I valori supportati sono `OFF` e `ON`.</span><span class="sxs-lookup"><span data-stu-id="b54e6-141">Supported values are `OFF` and `ON`.</span></span><br /><br /> <span data-ttu-id="b54e6-142">Il commit delle transazioni [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] può essere completamente durevole, che è l'impostazione predefinita, oppure con durabilità ritardata. Per altre informazioni, vedere [Controllo della durabilità delle transazioni](../logs/control-transaction-durability.md).</span><span class="sxs-lookup"><span data-stu-id="b54e6-142">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] transaction commits can be either fully durable, the default, or delayed durable.For more information, see [Control Transaction Durability](../logs/control-transaction-durability.md).</span></span>|  
  
 <span data-ttu-id="b54e6-143">Le opzioni SET seguenti presentano lo stesso valore predefinito di sistema per tutti i blocchi atomici in tutte le stored procedure compilate in modo nativo:</span><span class="sxs-lookup"><span data-stu-id="b54e6-143">The following SET options have the same system default value for all atomic blocks in all natively compiled stored procedures:</span></span>  
  
|<span data-ttu-id="b54e6-144">Opzione SET</span><span class="sxs-lookup"><span data-stu-id="b54e6-144">Set Option</span></span>|<span data-ttu-id="b54e6-145">Impostazione predefinita di sistema per i blocchi atomici</span><span class="sxs-lookup"><span data-stu-id="b54e6-145">System Default for Atomic Blocks</span></span>|  
|----------------|--------------------------------------|  
|<span data-ttu-id="b54e6-146">ANSI_NULLS</span><span class="sxs-lookup"><span data-stu-id="b54e6-146">ANSI_NULLS</span></span>|<span data-ttu-id="b54e6-147">ON</span><span class="sxs-lookup"><span data-stu-id="b54e6-147">ON</span></span>|  
|<span data-ttu-id="b54e6-148">ANSI_PADDING</span><span class="sxs-lookup"><span data-stu-id="b54e6-148">ANSI_PADDING</span></span>|<span data-ttu-id="b54e6-149">ON</span><span class="sxs-lookup"><span data-stu-id="b54e6-149">ON</span></span>|  
|<span data-ttu-id="b54e6-150">ANSI_WARNING</span><span class="sxs-lookup"><span data-stu-id="b54e6-150">ANSI_WARNING</span></span>|<span data-ttu-id="b54e6-151">ON</span><span class="sxs-lookup"><span data-stu-id="b54e6-151">ON</span></span>|  
|<span data-ttu-id="b54e6-152">ARITHABORT</span><span class="sxs-lookup"><span data-stu-id="b54e6-152">ARITHABORT</span></span>|<span data-ttu-id="b54e6-153">ON</span><span class="sxs-lookup"><span data-stu-id="b54e6-153">ON</span></span>|  
|<span data-ttu-id="b54e6-154">ARITHIGNORE</span><span class="sxs-lookup"><span data-stu-id="b54e6-154">ARITHIGNORE</span></span>|<span data-ttu-id="b54e6-155">OFF</span><span class="sxs-lookup"><span data-stu-id="b54e6-155">OFF</span></span>|  
|<span data-ttu-id="b54e6-156">CONCAT_NULL_YIELDS_NULL</span><span class="sxs-lookup"><span data-stu-id="b54e6-156">CONCAT_NULL_YIELDS_NULL</span></span>|<span data-ttu-id="b54e6-157">ON</span><span class="sxs-lookup"><span data-stu-id="b54e6-157">ON</span></span>|  
|<span data-ttu-id="b54e6-158">IDENTITY_INSERT</span><span class="sxs-lookup"><span data-stu-id="b54e6-158">IDENTITY_INSERT</span></span>|<span data-ttu-id="b54e6-159">OFF</span><span class="sxs-lookup"><span data-stu-id="b54e6-159">OFF</span></span>|  
|<span data-ttu-id="b54e6-160">NOCOUNT</span><span class="sxs-lookup"><span data-stu-id="b54e6-160">NOCOUNT</span></span>|<span data-ttu-id="b54e6-161">ON</span><span class="sxs-lookup"><span data-stu-id="b54e6-161">ON</span></span>|  
|<span data-ttu-id="b54e6-162">NUMERIC_ROUNDABORT</span><span class="sxs-lookup"><span data-stu-id="b54e6-162">NUMERIC_ROUNDABORT</span></span>|<span data-ttu-id="b54e6-163">OFF</span><span class="sxs-lookup"><span data-stu-id="b54e6-163">OFF</span></span>|  
|<span data-ttu-id="b54e6-164">QUOTED_IDENTIFIER</span><span class="sxs-lookup"><span data-stu-id="b54e6-164">QUOTED_IDENTIFIER</span></span>|<span data-ttu-id="b54e6-165">ON</span><span class="sxs-lookup"><span data-stu-id="b54e6-165">ON</span></span>|  
|<span data-ttu-id="b54e6-166">ROWCOUNT</span><span class="sxs-lookup"><span data-stu-id="b54e6-166">ROWCOUNT</span></span>|<span data-ttu-id="b54e6-167">0</span><span class="sxs-lookup"><span data-stu-id="b54e6-167">0</span></span>|  
|<span data-ttu-id="b54e6-168">TEXTSIZE</span><span class="sxs-lookup"><span data-stu-id="b54e6-168">TEXTSIZE</span></span>|<span data-ttu-id="b54e6-169">0</span><span class="sxs-lookup"><span data-stu-id="b54e6-169">0</span></span>|  
|<span data-ttu-id="b54e6-170">XACT_ABORT</span><span class="sxs-lookup"><span data-stu-id="b54e6-170">XACT_ABORT</span></span>|<span data-ttu-id="b54e6-171">OFF</span><span class="sxs-lookup"><span data-stu-id="b54e6-171">OFF</span></span><br /><br /> <span data-ttu-id="b54e6-172">Le eccezioni non rilevate causano il rollback dei blocchi atomici, ma non l'interruzione della transazione, a meno che l'errore non comporti la fine della transazione.</span><span class="sxs-lookup"><span data-stu-id="b54e6-172">Uncaught exceptions cause the atomic block to roll back, but not cause the transaction to abort unless the error is transaction dooming.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b54e6-173">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b54e6-173">See Also</span></span>  
 [<span data-ttu-id="b54e6-174">Stored procedure compilate in modo nativo</span><span class="sxs-lookup"><span data-stu-id="b54e6-174">Natively Compiled Stored Procedures</span></span>](natively-compiled-stored-procedures.md)  
  
  
