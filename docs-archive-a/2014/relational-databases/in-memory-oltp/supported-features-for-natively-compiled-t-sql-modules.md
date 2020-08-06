---
title: Costrutti supportati nelle stored procedure compilate in modo nativo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 05515013-28b5-4ccf-9a54-ae861448945b
author: rothja
ms.author: jroth
ms.openlocfilehash: 65e6e794c5858a68c4b2a9b298513911b487cf52
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637319"
---
# <a name="supported-constructs-in-natively-compiled-stored-procedures"></a><span data-ttu-id="df2aa-102">Costrutti supportati in stored procedure compilate in modo nativo</span><span class="sxs-lookup"><span data-stu-id="df2aa-102">Supported Constructs in Natively Compiled Stored Procedures</span></span>
  <span data-ttu-id="df2aa-103">Questo argomento contiene un elenco delle funzionalità supportate per le stored procedure compilate in modo nativo ([create procedure &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql)):</span><span class="sxs-lookup"><span data-stu-id="df2aa-103">This topic contains a list of supported features for natively compiled stored procedures ([CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql)):</span></span>  
  
-   [<span data-ttu-id="df2aa-104">Programmabilità nelle stored procedure compilate in modo nativo</span><span class="sxs-lookup"><span data-stu-id="df2aa-104">Programmability in Natively Compiled Stored Procedures</span></span>](#pncsp)  
  
-   [<span data-ttu-id="df2aa-105">Operatori supportati</span><span class="sxs-lookup"><span data-stu-id="df2aa-105">Supported Operators</span></span>](#so)  
  
-   [<span data-ttu-id="df2aa-106">Funzioni predefinite nelle stored procedure compilate in modo nativo</span><span class="sxs-lookup"><span data-stu-id="df2aa-106">Built-in Functions in Natively Compiled Stored Procedures</span></span>](#bfncsp)  
  
-   [<span data-ttu-id="df2aa-107">Superficie di attacco per le query nelle stored procedure compilate in modo nativo</span><span class="sxs-lookup"><span data-stu-id="df2aa-107">Query Surface Area in Natively Compiled Stored Procedures</span></span>](#qsancsp)  
  
-   [<span data-ttu-id="df2aa-108">Controllo</span><span class="sxs-lookup"><span data-stu-id="df2aa-108">Auditing</span></span>](#auditing)  
  
-   [<span data-ttu-id="df2aa-109">Hint per tabella, query e join</span><span class="sxs-lookup"><span data-stu-id="df2aa-109">Table, Query, and Join Hints</span></span>](#tqh)  
  
-   [<span data-ttu-id="df2aa-110">Limitazioni relative all'ordinamento</span><span class="sxs-lookup"><span data-stu-id="df2aa-110">Limitations on Sorting</span></span>](#los)  
  
 <span data-ttu-id="df2aa-111">Per informazioni sui tipi di dati supportati nelle stored procedure compilate in modo nativo, vedere [Supported Data Types](supported-data-types-for-in-memory-oltp.md).</span><span class="sxs-lookup"><span data-stu-id="df2aa-111">For information on data types supported in natively compiled stored procedures, see [Supported Data Types](supported-data-types-for-in-memory-oltp.md).</span></span>  
  
 <span data-ttu-id="df2aa-112">Per informazioni complete sui costrutti non supportati e per informazioni su come sopperire ad alcune funzionalità non supportate nelle stored procedure compilate in modo nativo, vedere [Migration Issues for Natively Compiled Stored Procedures](migration-issues-for-natively-compiled-stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="df2aa-112">For complete information about unsupported constructs, and for information about how to work around some of the unsupported features in natively compiled stored procedures, see [Migration Issues for Natively Compiled Stored Procedures](migration-issues-for-natively-compiled-stored-procedures.md).</span></span> <span data-ttu-id="df2aa-113">Per altre informazioni su funzionalità non supportate, vedere [Costrutti Transact-SQL non supportati da OLTP in memoria](transact-sql-constructs-not-supported-by-in-memory-oltp.md).</span><span class="sxs-lookup"><span data-stu-id="df2aa-113">For more information about unsupported features, see [Transact-SQL Constructs Not Supported by In-Memory OLTP](transact-sql-constructs-not-supported-by-in-memory-oltp.md).</span></span>  
  
##  <a name="programmability-in-natively-compiled-stored-procedures"></a><a name="pncsp"></a><span data-ttu-id="df2aa-114">Programmabilità nelle stored procedure compilate in modo nativo</span><span class="sxs-lookup"><span data-stu-id="df2aa-114">Programmability in Natively Compiled Stored Procedures</span></span>  
 <span data-ttu-id="df2aa-115">Sono supportati gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="df2aa-115">The following are supported:</span></span>  
  
-   <span data-ttu-id="df2aa-116">BEGIN ATOMIC (al livello esterno della stored procedure), LANGUAGE, ISOLATION LEVEL, DATEFORMAT e DATEFIRST.</span><span class="sxs-lookup"><span data-stu-id="df2aa-116">BEGIN ATOMIC (at the outer level of the stored procedure), LANGUAGE, ISOLATION LEVEL, DATEFORMAT, and DATEFIRST.</span></span>  
  
-   <span data-ttu-id="df2aa-117">Dichiarazione di variabili come NULL o NOT NULL.</span><span class="sxs-lookup"><span data-stu-id="df2aa-117">Declaring variables as NULL or NOT NULL.</span></span> <span data-ttu-id="df2aa-118">Se una variabile viene dichiarata come NOT NULL, la dichiarazione deve avere un inizializzatore.</span><span class="sxs-lookup"><span data-stu-id="df2aa-118">If a variable is declared as NOT NULL, the declaration must have an initializer.</span></span> <span data-ttu-id="df2aa-119">Se la variabile non viene dichiarata come NOT NULL, un inizializzatore è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="df2aa-119">If a variable is not declared as NOT NULL, an initializer is optional.</span></span>  
  
-   <span data-ttu-id="df2aa-120">IF e WHILE.</span><span class="sxs-lookup"><span data-stu-id="df2aa-120">IF and WHILE</span></span>  
  
-   <span data-ttu-id="df2aa-121">INSERT/UPDATE/DELETE</span><span class="sxs-lookup"><span data-stu-id="df2aa-121">INSERT/UPDATE/DELETE</span></span>  
  
     <span data-ttu-id="df2aa-122">Le sottoquery non sono supportate.</span><span class="sxs-lookup"><span data-stu-id="df2aa-122">Subqueries are not supported.</span></span> <span data-ttu-id="df2aa-123">Nella clausola WHERE o HAVING, AND e BETWEEN sono supportati; OR, NOT IN e IN non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="df2aa-123">In the WHERE or HAVING clause, AND and BETWEEN are supported; OR, NOT, and IN are not supported.</span></span>  
  
-   <span data-ttu-id="df2aa-124">Tipi di tabella con ottimizzazione per la memoria e variabili di tabella.</span><span class="sxs-lookup"><span data-stu-id="df2aa-124">Memory-optimized table types and table variables.</span></span>  
  
-   <span data-ttu-id="df2aa-125">RETURN</span><span class="sxs-lookup"><span data-stu-id="df2aa-125">RETURN</span></span>  
  
-   <span data-ttu-id="df2aa-126">SELECT</span><span class="sxs-lookup"><span data-stu-id="df2aa-126">SELECT</span></span>  
  
-   <span data-ttu-id="df2aa-127">SET</span><span class="sxs-lookup"><span data-stu-id="df2aa-127">SET</span></span>  
  
-   <span data-ttu-id="df2aa-128">TRY/CATCH/THROW</span><span class="sxs-lookup"><span data-stu-id="df2aa-128">TRY/CATCH/THROW</span></span>  
  
     <span data-ttu-id="df2aa-129">Per ottimizzare le prestazioni, utilizzare un solo blocco TRY/CATCH per un'intera stored procedure compilata in modo nativo.</span><span class="sxs-lookup"><span data-stu-id="df2aa-129">To optimize performance, use a single TRY/CATCH block for an entire natively compiled stored procedure.</span></span>  
  
##  <a name="supported-operators"></a><a name="so"></a> <span data-ttu-id="df2aa-130">Operatori supportati</span><span class="sxs-lookup"><span data-stu-id="df2aa-130">Supported Operators</span></span>  
 <span data-ttu-id="df2aa-131">Di seguito vengono elencati gli operatori supportati.</span><span class="sxs-lookup"><span data-stu-id="df2aa-131">The following operators are supported.</span></span>  
  
-   <span data-ttu-id="df2aa-132">[Gli operatori di confronto &#40;&#41;Transact-SQL](/sql/t-sql/language-elements/comparison-operators-transact-sql) (ad esempio, >, \<, > = e <=) sono supportati nelle istruzioni condizionali (if, while).</span><span class="sxs-lookup"><span data-stu-id="df2aa-132">[Comparison Operators &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/comparison-operators-transact-sql) (for example, >, \<, >=, and <=) are supported in conditionals (IF, WHILE).</span></span>  
  
-   <span data-ttu-id="df2aa-133">Operatori unari (+, -).</span><span class="sxs-lookup"><span data-stu-id="df2aa-133">Unary operators (+, -).</span></span>  
  
-   <span data-ttu-id="df2aa-134">Operatori binari (\*, /, +, -, % (modulo)).</span><span class="sxs-lookup"><span data-stu-id="df2aa-134">Binary operators (\*, /, +, -, % (modulo)).</span></span>  
  
     <span data-ttu-id="df2aa-135">L'operatore di addizione (+) è supportato sia con i numeri che con le stringhe.</span><span class="sxs-lookup"><span data-stu-id="df2aa-135">The plus operator (+) is supported on both numbers and strings.</span></span>  
  
-   <span data-ttu-id="df2aa-136">Operatori logici (AND, OR, NOT).</span><span class="sxs-lookup"><span data-stu-id="df2aa-136">Logical operators (AND, OR, NOT).</span></span> <span data-ttu-id="df2aa-137">OR e NOT sono supportati nelle istruzioni IF e WHILE ma non nelle clausole WHERE o HAVING.</span><span class="sxs-lookup"><span data-stu-id="df2aa-137">OR and NOT are supported in IF and WHILE statements but not in WHERE or HAVING clauses.</span></span>  
  
-   <span data-ttu-id="df2aa-138">Operatori bit per bit ~, &, | e ^</span><span class="sxs-lookup"><span data-stu-id="df2aa-138">Bitwise operators ~, &, |, and ^</span></span>  
  
##  <a name="built-in-functions-in-natively-compiled-stored-procedures"></a><a name="bfncsp"></a><span data-ttu-id="df2aa-139">Funzioni predefinite nelle stored procedure compilate in modo nativo</span><span class="sxs-lookup"><span data-stu-id="df2aa-139">Built-in Functions in Natively Compiled Stored Procedures</span></span>  
 <span data-ttu-id="df2aa-140">Le seguenti funzioni sono supportate nei vincoli predefiniti nelle tabelle ottimizzate per la memoria e nelle stored procedure compilate in modo nativo.</span><span class="sxs-lookup"><span data-stu-id="df2aa-140">The following functions are supported in default constraints on memory-optimized tables and in natively compiled stored procedures.</span></span>  
  
-   <span data-ttu-id="df2aa-141">Funzioni matematiche: ACOS, ASIN, ATAN, ATN2, COS, COT, DEGREES, EXP, LOG, LOG10, PI, POWER, RADIANS, RAND, SIN, SQRT, SQUARE e TAN</span><span class="sxs-lookup"><span data-stu-id="df2aa-141">Math Functions: ACOS, ASIN, ATAN, ATN2, COS, COT, DEGREES, EXP, LOG, LOG10, PI, POWER, RADIANS, RAND, SIN, SQRT, SQUARE, and TAN</span></span>  
  
-   <span data-ttu-id="df2aa-142">Funzioni di data: CURRENT_TIMESTAMP, DATEADD, DATEDIFF, DATEFROMPARTS, DATEPART, DATETIME2FROMPARTS, DATETIMEFROMPARTS, DAY, EOMONTH, GETDATE, GETUTCDATE, MONTH, SMALLDATETIMEFROMPARTS, SYSDATETIME, SYSUTCDATETIME e YEAR.</span><span class="sxs-lookup"><span data-stu-id="df2aa-142">Date Functions: CURRENT_TIMESTAMP, DATEADD, DATEDIFF, DATEFROMPARTS, DATEPART, DATETIME2FROMPARTS, DATETIMEFROMPARTS, DAY, EOMONTH, GETDATE, GETUTCDATE, MONTH, SMALLDATETIMEFROMPARTS, SYSDATETIME, SYSUTCDATETIME, and YEAR.</span></span>  
  
-   <span data-ttu-id="df2aa-143">Funzioni di tipo stringa: LEN, LTRIM, RTRIM e SUBSTRING</span><span class="sxs-lookup"><span data-stu-id="df2aa-143">String Functions: LEN, LTRIM, RTRIM, and SUBSTRING</span></span>  
  
-   <span data-ttu-id="df2aa-144">Funzione di identità: SCOPE_IDENTITY</span><span class="sxs-lookup"><span data-stu-id="df2aa-144">Identity Function: SCOPE_IDENTITY</span></span>  
  
-   <span data-ttu-id="df2aa-145">Funzioni NULL: ISNULL</span><span class="sxs-lookup"><span data-stu-id="df2aa-145">NULL functions: ISNULL</span></span>  
  
-   <span data-ttu-id="df2aa-146">Funzioni di identificazione univoca: NEWID e NEWSEQUENTIALID</span><span class="sxs-lookup"><span data-stu-id="df2aa-146">Uniqueidentifier functions: NEWID and NEWSEQUENTIALID</span></span>  
  
-   <span data-ttu-id="df2aa-147">Funzioni di errore: ERROR_LINE, ERROR_MESSAGE, ERROR_NUMBER, ERROR_PROCEDURE, ERROR_SEVERITY e ERROR_STATE</span><span class="sxs-lookup"><span data-stu-id="df2aa-147">Error Functions: ERROR_LINE, ERROR_MESSAGE, ERROR_NUMBER, ERROR_PROCEDURE, ERROR_SEVERITY, and ERROR_STATE</span></span>  
  
-   <span data-ttu-id="df2aa-148">Conversioni: CAST e CONVERT.</span><span class="sxs-lookup"><span data-stu-id="df2aa-148">Conversions: CAST and CONVERT.</span></span> <span data-ttu-id="df2aa-149">Le conversioni tra stringhe di caratteri Unicode e non Unicode (n(var)char e (var)char) non sono supportate.</span><span class="sxs-lookup"><span data-stu-id="df2aa-149">Conversions between Unicode and non-Unicode character strings (n(var)char and (var)char) are not supported.</span></span>  
  
-   <span data-ttu-id="df2aa-150">Funzioni di sistema: @@rowcount.</span><span class="sxs-lookup"><span data-stu-id="df2aa-150">System Functions: @@rowcount.</span></span> <span data-ttu-id="df2aa-151">Le istruzioni all'interno di stored procedure compilate in modo nativo aggiornano @@rowcount ed è possibile usare @@rowcount in una stored procedure compilata in modo nativo per determinare il numero di righe interessate dall'ultima istruzione eseguita all'interno della stored procedure.</span><span class="sxs-lookup"><span data-stu-id="df2aa-151">Statements inside natively compiled stored procedures update @@rowcount and you can use @@rowcount in a natively compiled stored procedure to determine the number of rows affected by the last statement executed within that natively compiled stored procedure.</span></span> <span data-ttu-id="df2aa-152">Tuttavia, @@rowcount viene reimpostato su 0 all'inizio e alla fine dell'esecuzione di una stored procedure compilata in modo nativo.</span><span class="sxs-lookup"><span data-stu-id="df2aa-152">However, @@rowcount is reset to 0 at the start and at the end of the execution of a natively compiled stored procedure.</span></span>  
  
##  <a name="query-surface-area-in-natively-compiled-stored-procedures"></a><a name="qsancsp"></a><span data-ttu-id="df2aa-153">Superficie di attacco delle query nelle stored procedure compilate in modo nativo</span><span class="sxs-lookup"><span data-stu-id="df2aa-153">Query Surface Area in Natively Compiled Stored Procedures</span></span>  
 <span data-ttu-id="df2aa-154">Sono supportati gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="df2aa-154">The following are supported:</span></span>  
  
-   <span data-ttu-id="df2aa-155">BETWEEN</span><span class="sxs-lookup"><span data-stu-id="df2aa-155">BETWEEN</span></span>  
  
-   <span data-ttu-id="df2aa-156">Alias di nomi di colonna (utilizzando la sintassi AS o =).</span><span class="sxs-lookup"><span data-stu-id="df2aa-156">Column name aliases (using either AS or = syntax).</span></span>  
  
-   <span data-ttu-id="df2aa-157">CROSS JOIN e INNER JOIN, supportati solo con query SELECT.</span><span class="sxs-lookup"><span data-stu-id="df2aa-157">CROSS JOIN and INNER JOIN, supported only with SELECT queries.</span></span>  
  
-   <span data-ttu-id="df2aa-158">Le espressioni sono supportate nell'elenco di selezione e [dove &#40;clausola Transact-SQL&#41;](/sql/t-sql/queries/where-transact-sql) se utilizzano un operatore supportato.</span><span class="sxs-lookup"><span data-stu-id="df2aa-158">Expressions are supported in SELECT list and [WHERE &#40;Transact-SQL&#41;](/sql/t-sql/queries/where-transact-sql) clause if they use a supported operator.</span></span> <span data-ttu-id="df2aa-159">Vedere [Operatori supportati](#so) per l'elenco degli operatori attualmente supportati.</span><span class="sxs-lookup"><span data-stu-id="df2aa-159">See [Supported Operators](#so) for the list of currently-supported operators.</span></span>  
  
-   <span data-ttu-id="df2aa-160">Predicato del filtro IS [NOT] NULL</span><span class="sxs-lookup"><span data-stu-id="df2aa-160">Filter predicate IS [NOT] NULL</span></span>  
  
-   <span data-ttu-id="df2aa-161">FROM \<memory optimized table></span><span class="sxs-lookup"><span data-stu-id="df2aa-161">FROM \<memory optimized table></span></span>  
  
-   <span data-ttu-id="df2aa-162">[GROUP BY &#40;&#41;Transact-SQL](/sql/t-sql/queries/select-group-by-transact-sql) è supportato, insieme alle funzioni di aggregazione AVG, COUNT, COUNT_BIG, min, Max e Sum.</span><span class="sxs-lookup"><span data-stu-id="df2aa-162">[GROUP BY &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-group-by-transact-sql) is supported, along with the aggregate functions AVG, COUNT, COUNT_BIG, MIN, MAX, and SUM.</span></span> <span data-ttu-id="df2aa-163">MIN e MAX non sono supportate per i tipi nvarchar, char, varchar, varchar, varbinary e binary.</span><span class="sxs-lookup"><span data-stu-id="df2aa-163">MIN and MAX are not supported for types nvarchar, char, varchar, varchar, varbinary, and binary.</span></span> <span data-ttu-id="df2aa-164">La [clausola order by &#40;&#41;Transact-SQL](/sql/t-sql/queries/select-order-by-clause-transact-sql) è supportata con [Group by &#40;transact-SQL&#41;](/sql/t-sql/queries/select-group-by-transact-sql) se un'espressione nell'elenco ORDER BY viene visualizzata Verbatim nell'elenco Group by.</span><span class="sxs-lookup"><span data-stu-id="df2aa-164">[ORDER BY Clause &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-order-by-clause-transact-sql) is supported with [GROUP BY &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-group-by-transact-sql) if an expression in the ORDER BY list appears verbatim in the GROUP BY list.</span></span> <span data-ttu-id="df2aa-165">Ad esempio, l'espressione GROUP BY a + b ORDER BY a + b è supportata, ma GROUP BY a, b ORDER BY a + b non lo è.</span><span class="sxs-lookup"><span data-stu-id="df2aa-165">For example, GROUP BY a + b ORDER BY a + b is supported, but GROUP BY a, b ORDER BY a + b is not.</span></span>  
  
-   <span data-ttu-id="df2aa-166">HAVING, soggetto alle stesse limitazioni delle espressioni della clausola WHERE.</span><span class="sxs-lookup"><span data-stu-id="df2aa-166">HAVING, subject to the same expression limitations as the WHERE clause.</span></span>  
  
-   <span data-ttu-id="df2aa-167">INSERT VALUES (una riga per istruzione) e INSERT SELECT</span><span class="sxs-lookup"><span data-stu-id="df2aa-167">INSERT VALUES (one row per statement) and INSERT SELECT</span></span>  
  
-   <span data-ttu-id="df2aa-168">Ordina per <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="df2aa-168">ORDER BY <sup>1</sup></span></span>  
  
-   <span data-ttu-id="df2aa-169">Predicati che non fanno riferimento a una colonna</span><span class="sxs-lookup"><span data-stu-id="df2aa-169">Predicates not referencing a column.</span></span>  
  
-   <span data-ttu-id="df2aa-170">SELECT, UPDATE e DELETE</span><span class="sxs-lookup"><span data-stu-id="df2aa-170">SELECT, UPDATE, and DELETE</span></span>  
  
-   <span data-ttu-id="df2aa-171">PRIMI <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="df2aa-171">TOP <sup>1</sup></span></span>  
  
-   <span data-ttu-id="df2aa-172">Assegnazione di variabile nell'elenco SELECT.</span><span class="sxs-lookup"><span data-stu-id="df2aa-172">Variable assignment in the SELECT list.</span></span>  
  
-   <span data-ttu-id="df2aa-173">DOVE... E</span><span class="sxs-lookup"><span data-stu-id="df2aa-173">WHERE ... AND</span></span>  
  
 <span data-ttu-id="df2aa-174"><sup>1</sup> order by e Top sono supportati nelle stored procedure compilate in modo nativo, con alcune restrizioni:</span><span class="sxs-lookup"><span data-stu-id="df2aa-174"><sup>1</sup> ORDER BY and TOP are supported in natively compiled stored procedures, with some restrictions:</span></span>  
  
-   <span data-ttu-id="df2aa-175">`DISTINCT` non è supportata nella clausola `SELECT` o `ORDER BY`.</span><span class="sxs-lookup"><span data-stu-id="df2aa-175">There is no support for `DISTINCT` in the `SELECT` or `ORDER BY` clause.</span></span>  
  
-   <span data-ttu-id="df2aa-176">`WITH TIES` o `PERCENT` non è supportata nella clausola `TOP`.</span><span class="sxs-lookup"><span data-stu-id="df2aa-176">There is no support for `WITH TIES` or `PERCENT` in the `TOP` clause.</span></span>  
  
-   <span data-ttu-id="df2aa-177">`TOP` in combinazione con `ORDER BY` non supporta un valore superiore a 8.192 quando si utilizza una costante nella clausola `TOP`.</span><span class="sxs-lookup"><span data-stu-id="df2aa-177">`TOP` combined with `ORDER BY` does not support more than 8,192 when using a constant in the `TOP` clause.</span></span> <span data-ttu-id="df2aa-178">Questo limite può risultare più basso nel caso in cui la query contenga funzioni di aggregazione o dei join.</span><span class="sxs-lookup"><span data-stu-id="df2aa-178">This limit may be lowered in case the query contains joins or aggregate functions.</span></span> <span data-ttu-id="df2aa-179">Ad esempio, con un join (due tabelle) il limite scende a 4.096 righe.</span><span class="sxs-lookup"><span data-stu-id="df2aa-179">(For example, with one join (two tables), the limit is 4,096 rows.</span></span> <span data-ttu-id="df2aa-180">Con due join (tre tabelle) il limite è 2.730 righe.</span><span class="sxs-lookup"><span data-stu-id="df2aa-180">With two joins (three tables), the limit is 2,730 rows.)</span></span>  
  
     <span data-ttu-id="df2aa-181">È possibile che si ottengano risultati maggiori di 8.192 archiviando il numero di righe in una variabile:</span><span class="sxs-lookup"><span data-stu-id="df2aa-181">You can obtain results greater than 8,192 by storing the number of rows in a variable:</span></span>  
  
    ```sql  
    DECLARE @v INT = 9000  
    SELECT TOP (@v) ... FROM ... ORDER BY ...  
    ```  
  
 <span data-ttu-id="df2aa-182">Tuttavia, una costante nella clausola `TOP` assicura prestazioni migliori rispetto a una variabile.</span><span class="sxs-lookup"><span data-stu-id="df2aa-182">However, a constant in the `TOP` clause results in better performance compared to using a variable.</span></span>  
  
 <span data-ttu-id="df2aa-183">Queste limitazioni non si applicano all'accesso [!INCLUDE[tsql](../../includes/tsql-md.md)] interpretato nelle tabelle ottimizzate per la memoria.</span><span class="sxs-lookup"><span data-stu-id="df2aa-183">These restrictions do not apply to interpreted [!INCLUDE[tsql](../../includes/tsql-md.md)] access on memory-optimized tables.</span></span>  
  
##  <a name="auditing"></a><a name="auditing"></a> <span data-ttu-id="df2aa-184">Controllo</span><span class="sxs-lookup"><span data-stu-id="df2aa-184">Auditing</span></span>  
 <span data-ttu-id="df2aa-185">Il controllo a livello di routine è supportato nelle stored procedure compilate in modo nativo.</span><span class="sxs-lookup"><span data-stu-id="df2aa-185">Procedure level auditing is supported in natively compiled stored procedures.</span></span> <span data-ttu-id="df2aa-186">Il controllo a livello di istruzione non è supportato.</span><span class="sxs-lookup"><span data-stu-id="df2aa-186">Statement level auditing is not supported.</span></span>  
  
 <span data-ttu-id="df2aa-187">Per ulteriori informazioni sul controllo, vedere [Creazione di un controllo del server e di una specifica del controllo del database](../security/auditing/create-a-server-audit-and-database-audit-specification.md).</span><span class="sxs-lookup"><span data-stu-id="df2aa-187">For more information about auditing, see [Create a Server Audit and Database Audit Specification](../security/auditing/create-a-server-audit-and-database-audit-specification.md).</span></span>  
  
##  <a name="table-query-and-join-hints"></a><a name="tqh"></a><span data-ttu-id="df2aa-188">Hint di tabella, query e join</span><span class="sxs-lookup"><span data-stu-id="df2aa-188">Table, Query, and Join Hints</span></span>  
 <span data-ttu-id="df2aa-189">Sono supportati gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="df2aa-189">The following are supported:</span></span>  
  
-   <span data-ttu-id="df2aa-190">Gli hint INDEX, FORCESCAN e FORCESEEK, nella sintassi di hint di tabella o nella [clausola OPTION &#40;Transact-SQL&#41;](/sql/t-sql/queries/option-clause-transact-sql) della query.</span><span class="sxs-lookup"><span data-stu-id="df2aa-190">INDEX, FORCESCAN, and FORCESEEK hints, either in table hints syntax or in [OPTION Clause &#40;Transact-SQL&#41;](/sql/t-sql/queries/option-clause-transact-sql) of the query.</span></span>  
  
-   <span data-ttu-id="df2aa-191">FORCE ORDER</span><span class="sxs-lookup"><span data-stu-id="df2aa-191">FORCE ORDER</span></span>  
  
-   <span data-ttu-id="df2aa-192">INNER LOOP JOIN</span><span class="sxs-lookup"><span data-stu-id="df2aa-192">INNER LOOP JOIN</span></span>  
  
-   <span data-ttu-id="df2aa-193">OPTIMIZE FOR</span><span class="sxs-lookup"><span data-stu-id="df2aa-193">OPTIMIZE FOR</span></span>  
  
 <span data-ttu-id="df2aa-194">Per ulteriori informazioni, vedere [hint &#40;&#41;Transact-SQL ](/sql/t-sql/queries/hints-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="df2aa-194">For more information, see [Hints &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql).</span></span>  
  
##  <a name="limitations-on-sorting"></a><a name="los"></a> <span data-ttu-id="df2aa-195">Limitazioni relative all'ordinamento</span><span class="sxs-lookup"><span data-stu-id="df2aa-195">Limitations on Sorting</span></span>  
 <span data-ttu-id="df2aa-196">È possibile ordinare più di 8.000 righe in una query che usa [TOP &#40;Transact-SQL&#41;](/sql/t-sql/queries/top-transact-sql) e una clausola [ORDER BY Clause &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-order-by-clause-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="df2aa-196">You can sort greater than 8,000 rows in a query that uses [TOP &#40;Transact-SQL&#41;](/sql/t-sql/queries/top-transact-sql) and an [ORDER BY Clause &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-order-by-clause-transact-sql).</span></span> <span data-ttu-id="df2aa-197">Tuttavia, senza la [ clausola ORDER BY &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-order-by-clause-transact-sql), [TOP &#40;Transact-SQL&#41;](/sql/t-sql/queries/top-transact-sql) può ordinare fino a 8.000 righe, meno se sono presenti join.</span><span class="sxs-lookup"><span data-stu-id="df2aa-197">However, without [ORDER BY Clause &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-order-by-clause-transact-sql), [TOP &#40;Transact-SQL&#41;](/sql/t-sql/queries/top-transact-sql) can sort up to 8,000 rows (fewer rows if there are joins).</span></span>  
  
 <span data-ttu-id="df2aa-198">Se la query usa sia l'operatore [TOP &#40;Transact-SQL&#41;](/sql/t-sql/queries/top-transact-sql) che una [clausola ORDER BY &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-order-by-clause-transact-sql), è possibile specificare fino a 8192 righe per l'operatore TOP.</span><span class="sxs-lookup"><span data-stu-id="df2aa-198">If your query uses both the [TOP &#40;Transact-SQL&#41;](/sql/t-sql/queries/top-transact-sql) operator and an [ORDER BY Clause &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-order-by-clause-transact-sql), you can specify up to 8192 rows for the TOP operator.</span></span> <span data-ttu-id="df2aa-199">Se si specificano più di 8192 righe viene visualizzato il messaggio di errore seguente: **Messaggio 41398, livello 16, stato 1, procedura *\<procedureName>* , riga *\<lineNumber>* L'operatore TOP può restituire un massimo di 8192 righe. Il numero richiesto è *\<number>* .**</span><span class="sxs-lookup"><span data-stu-id="df2aa-199">If you specify more than 8192 rows you get the error message: **Msg 41398, Level 16, State 1, Procedure *\<procedureName>*, Line *\<lineNumber>* The TOP operator can return a maximum of 8192 rows; *\<number>* was requested.**</span></span>  
  
 <span data-ttu-id="df2aa-200">Se non si dispone di una clausola TOP, è possibile ordinare qualsiasi numero di righe con ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="df2aa-200">If you do not have a TOP clause, you can sort any number of rows with ORDER BY.</span></span>  
  
 <span data-ttu-id="df2aa-201">Se non si utilizza una clausola ORDER BY, è possibile utilizzare qualsiasi valore intero con l'operatore TOP.</span><span class="sxs-lookup"><span data-stu-id="df2aa-201">If you do not use an ORDER BY clause, you can use any integer value with the TOP operator.</span></span>  
  
 <span data-ttu-id="df2aa-202">Esempio con TOP N = 8192: esegue la compilazione</span><span class="sxs-lookup"><span data-stu-id="df2aa-202">Example with TOP N = 8192: Compiles</span></span>  
  
```sql  
CREATE PROCEDURE testTop  
WITH EXECUTE AS OWNER, SCHEMABINDING, NATIVE_COMPILATION  
  AS  
  BEGIN ATOMIC WITH (TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE = N'us_english')  
    SELECT TOP 8192 ShoppingCartId, CreatedDate, TotalPrice FROM dbo.ShoppingCart  
    ORDER BY ShoppingCartId DESC  
  END;  
GO  
```  
  
 <span data-ttu-id="df2aa-203">Esempio con TOP N > 8192: non riesce a compilare.</span><span class="sxs-lookup"><span data-stu-id="df2aa-203">Example with TOP N > 8192: Fails to compile.</span></span>  
  
```sql  
CREATE PROCEDURE testTop  
WITH EXECUTE AS OWNER, SCHEMABINDING, NATIVE_COMPILATION  
  AS  
  BEGIN ATOMIC WITH (TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE = N'us_english')  
    SELECT TOP 8193 ShoppingCartId, CreatedDate, TotalPrice FROM dbo.ShoppingCart  
    ORDER BY ShoppingCartId DESC  
  END;  
GO  
```  
  
 <span data-ttu-id="df2aa-204">Il limite di 8192 righe si applica solo a `TOP N``N` dove  è una costante, come negli esempi precedenti.</span><span class="sxs-lookup"><span data-stu-id="df2aa-204">The 8192 row limitation only applies to `TOP N` where `N` is a constant, as in the preceding examples.</span></span>  <span data-ttu-id="df2aa-205">Se è necessario un valore `N` maggiore di 8192 è possibile assegnare il valore a una variabile e utilizzare tale variabile con `TOP`.</span><span class="sxs-lookup"><span data-stu-id="df2aa-205">If you need `N` greater than 8192 you can assign the value to a variable and use that variable with `TOP`.</span></span>  
  
 <span data-ttu-id="df2aa-206">Esempio d'uso di una variabile: esegue la compilazione</span><span class="sxs-lookup"><span data-stu-id="df2aa-206">Example using a variable: Compiles</span></span>  
  
```sql  
CREATE PROCEDURE testTop  
WITH EXECUTE AS OWNER, SCHEMABINDING, NATIVE_COMPILATION  
  AS  
  BEGIN ATOMIC WITH (TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE = N'us_english')  
    DECLARE @v int = 8193   
    SELECT TOP (@v) ShoppingCartId, CreatedDate, TotalPrice FROM dbo.ShoppingCart  
    ORDER BY ShoppingCartId DESC  
  END;  
GO  
```  
  
 <span data-ttu-id="df2aa-207">**Limitazioni per le righe restituite:** In due casi è possibile che il numero di righe restituibili dall'operatore TOP venga ridotto:</span><span class="sxs-lookup"><span data-stu-id="df2aa-207">**Limitations on rows returned:** There are two cases where that can potentially reduce the number of rows that can be returned by the TOP operator:</span></span>  
  
-   <span data-ttu-id="df2aa-208">Utilizzando JOIN nella query.</span><span class="sxs-lookup"><span data-stu-id="df2aa-208">Using JOINs in the query.</span></span>  <span data-ttu-id="df2aa-209">L'influenza di JOIN sulla limitazione dipende dal piano di query.</span><span class="sxs-lookup"><span data-stu-id="df2aa-209">The influence of JOINs on the limitation depends on the query plan.</span></span>  
  
-   <span data-ttu-id="df2aa-210">Utilizzando funzioni di aggregazione o riferimenti a funzioni di aggregazione nella clausola ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="df2aa-210">Using aggregate functions or references to aggregate functions in the ORDER BY clause.</span></span>  
  
 <span data-ttu-id="df2aa-211">La formula per calcolare un valore N massimo supportato nel caso peggiore in TOP N è: `N = floor ( 65536 / number_of_tables * 8 + total_size+of+aggs )`.</span><span class="sxs-lookup"><span data-stu-id="df2aa-211">The formula to calculate a worst case maximum supported N in TOP N is: `N = floor ( 65536 / number_of_tables * 8 + total_size+of+aggs )`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df2aa-212">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="df2aa-212">See Also</span></span>  
 <span data-ttu-id="df2aa-213">[Stored procedure compilate in modo nativo](natively-compiled-stored-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="df2aa-213">[Natively Compiled Stored Procedures](natively-compiled-stored-procedures.md) </span></span>  
 [<span data-ttu-id="df2aa-214">Problemi di migrazione relativi alle stored procedure compilate in modo nativo</span><span class="sxs-lookup"><span data-stu-id="df2aa-214">Migration Issues for Natively Compiled Stored Procedures</span></span>](migration-issues-for-natively-compiled-stored-procedures.md)  
  
  
