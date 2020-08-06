---
title: MSSQLSERVER_207 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 207 (Database Engine error)
ms.assetid: d1ab00c7-0331-437a-84fe-bae53b82feec
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: bd6044c08ecd5a73f539bfbc1139d6257c2db9d3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714395"
---
# <a name="mssqlserver_207"></a><span data-ttu-id="6e48f-102">MSSQLSERVER_207</span><span class="sxs-lookup"><span data-stu-id="6e48f-102">MSSQLSERVER_207</span></span>
    
## <a name="details"></a><span data-ttu-id="6e48f-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="6e48f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6e48f-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="6e48f-104">Product Name</span></span>|<span data-ttu-id="6e48f-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="6e48f-105">SQL Server</span></span>|  
|<span data-ttu-id="6e48f-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="6e48f-106">Event ID</span></span>|<span data-ttu-id="6e48f-107">207</span><span class="sxs-lookup"><span data-stu-id="6e48f-107">207</span></span>|  
|<span data-ttu-id="6e48f-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="6e48f-108">Event Source</span></span>|<span data-ttu-id="6e48f-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="6e48f-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="6e48f-110">Componente</span><span class="sxs-lookup"><span data-stu-id="6e48f-110">Component</span></span>|<span data-ttu-id="6e48f-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="6e48f-111">SQLEngine</span></span>|  
|<span data-ttu-id="6e48f-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="6e48f-112">Symbolic Name</span></span>|<span data-ttu-id="6e48f-113">SQ_BADCOL</span><span class="sxs-lookup"><span data-stu-id="6e48f-113">SQ_BADCOL</span></span>|  
|<span data-ttu-id="6e48f-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="6e48f-114">Message Text</span></span>|<span data-ttu-id="6e48f-115">Il nome di colonna '%.\*ls' non è valido.</span><span class="sxs-lookup"><span data-stu-id="6e48f-115">Invalid column name '%.\*ls'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="6e48f-116">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="6e48f-116">Explanation</span></span>  
 <span data-ttu-id="6e48f-117">L'errore di query può essere causato da uno dei problemi seguenti:</span><span class="sxs-lookup"><span data-stu-id="6e48f-117">This query error can be caused by one of the following problems.</span></span>  
  
-   <span data-ttu-id="6e48f-118">Il nome di colonna è errato oppure la colonna non esiste in alcuna delle tabelle specificate.</span><span class="sxs-lookup"><span data-stu-id="6e48f-118">The column name is misspelled or the column does not exist in any of the specified tables.</span></span>  
  
-   <span data-ttu-id="6e48f-119">Le regole di confronto del database rispettano la distinzione tra maiuscole e minuscole e la combinazione di maiuscole e minuscole del nome di colonna specificato nella query non corrisponde a quella della colonna definita nella tabella.</span><span class="sxs-lookup"><span data-stu-id="6e48f-119">The collation of the database is case-sensitive and the case of the column name specified in the query does not match the case of the column defined in the table.</span></span> <span data-ttu-id="6e48f-120">Ad esempio, se una colonna viene definita in una tabella come **Cognome** e nel database vengono usate regole di confronto con distinzione tra maiuscole e minuscole, le query che fanno riferimento alla colonna con **COGNOME** o **cognome** restituiranno l'errore 207 poiché il nome di colonna non corrisponde.</span><span class="sxs-lookup"><span data-stu-id="6e48f-120">For example, when a column is defined in a table as **LastName** and the database uses a case-sensitive collation, queries that refer to the column as **Lastname** or **lastname** will cause error 207 to return because the column name does not match.</span></span>  
  
-   <span data-ttu-id="6e48f-121">A un alias di colonna, definito nella clausola SELECT, viene fatto riferimento in un'altra clausola, ad esempio una clausola WHERE o GROUP BY.</span><span class="sxs-lookup"><span data-stu-id="6e48f-121">A column alias, defined in the SELECT clause, is referenced in another clause such as a WHERE or GROUP BY clause.</span></span> <span data-ttu-id="6e48f-122">La query seguente, ad esempio, definisce l'alias di colonna `Year` nella clausola SELECT e fa riferimento all'alias nella clausola GROUP BY.</span><span class="sxs-lookup"><span data-stu-id="6e48f-122">For example, the following query defines the column alias `Year` in the SELECT clause and refers to it in the GROUP BY clause.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT DATEPART(yyyy,OrderDate) AS Year, SUM(TotalDue) AS Total  
    FROM Sales.SalesOrderHeader  
    GROUP BY Year;  
    ```  
  
     <span data-ttu-id="6e48f-123">A causa dell'ordine in cui le clausole di query vengono elaborate logicamente, l'esempio restituisce l'errore 207.</span><span class="sxs-lookup"><span data-stu-id="6e48f-123">Due to the order in which query clauses are logically processed, the example returns error 207.</span></span> <span data-ttu-id="6e48f-124">L'ordine di elaborazione è il seguente:</span><span class="sxs-lookup"><span data-stu-id="6e48f-124">The processing order is as follows:</span></span>  
  
    1.  <span data-ttu-id="6e48f-125">FROM</span><span class="sxs-lookup"><span data-stu-id="6e48f-125">FROM</span></span>  
  
    2.  <span data-ttu-id="6e48f-126">ON</span><span class="sxs-lookup"><span data-stu-id="6e48f-126">ON</span></span>  
  
    3.  <span data-ttu-id="6e48f-127">JOIN</span><span class="sxs-lookup"><span data-stu-id="6e48f-127">JOIN</span></span>  
  
    4.  <span data-ttu-id="6e48f-128">WHERE</span><span class="sxs-lookup"><span data-stu-id="6e48f-128">WHERE</span></span>  
  
    5.  <span data-ttu-id="6e48f-129">GROUP BY</span><span class="sxs-lookup"><span data-stu-id="6e48f-129">GROUP BY</span></span>  
  
    6.  <span data-ttu-id="6e48f-130">WITH CUBE o WITH ROLLUP</span><span class="sxs-lookup"><span data-stu-id="6e48f-130">WITH CUBE or WITH ROLLUP</span></span>  
  
    7.  <span data-ttu-id="6e48f-131">HAVING</span><span class="sxs-lookup"><span data-stu-id="6e48f-131">HAVING</span></span>  
  
    8.  <span data-ttu-id="6e48f-132">SELECT</span><span class="sxs-lookup"><span data-stu-id="6e48f-132">SELECT</span></span>  
  
    9. <span data-ttu-id="6e48f-133">DISTINCT</span><span class="sxs-lookup"><span data-stu-id="6e48f-133">DISTINCT</span></span>  
  
    10. <span data-ttu-id="6e48f-134">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="6e48f-134">ORDER BY</span></span>  
  
    11. <span data-ttu-id="6e48f-135">TOP</span><span class="sxs-lookup"><span data-stu-id="6e48f-135">TOP</span></span>  
  
     <span data-ttu-id="6e48f-136">Poiché un alias di colonna non viene definito fino a quando la clausola SELECT non viene elaborata, il nome di alias è sconosciuto al momento dell'elaborazione della clausola GROUP BY.</span><span class="sxs-lookup"><span data-stu-id="6e48f-136">Because a column alias is not defined until the SELECT clause is processed, the alias name is unknown when the GROUP BY clause is processed.</span></span>  
  
-   <span data-ttu-id="6e48f-137">L'istruzione MERGE genera questo errore quando la clausola *<merge_corrispondente>* fa riferimento alle colonne nella tabella di origine, ma quest'ultima non restituisce alcuna riga nella clausola WHEN NOT MATCHED BY SOURCE.</span><span class="sxs-lookup"><span data-stu-id="6e48f-137">The MERGE statement raises this error when the *<merge_matched>* clause references columns in the source table but no rows are returned by the source table in the WHEN NOT MATCHED BY SOURCE clause.</span></span> <span data-ttu-id="6e48f-138">L'errore si verifica poiché non è possibile accedere alle colonne della tabella di origine quando alla query non viene restituita alcuna riga.</span><span class="sxs-lookup"><span data-stu-id="6e48f-138">The error occurs because the columns in the source table cannot be accessed when no rows are returned to the query.</span></span> <span data-ttu-id="6e48f-139">La clausola `WHEN NOT MATCHED BY SOURCE THEN UPDATE SET TargetTable.Col1 = SourceTable.Col1` può provocare ad esempio un errore nell'istruzione se non è possibile accedere a `Col1` nella tabella di origine.</span><span class="sxs-lookup"><span data-stu-id="6e48f-139">For example, the clause `WHEN NOT MATCHED BY SOURCE THEN UPDATE SET TargetTable.Col1 = SourceTable.Col1` may cause the statement to fail if `Col1` in the source table is inaccessible.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6e48f-140">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="6e48f-140">User Action</span></span>  
 <span data-ttu-id="6e48f-141">Verificare le informazioni seguenti e correggere l'istruzione in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="6e48f-141">Verify the following information and correct the statement as appropriate.</span></span>  
  
-   <span data-ttu-id="6e48f-142">Presenza e ortografia corretta del nome di colonna nella tabella.</span><span class="sxs-lookup"><span data-stu-id="6e48f-142">The column name exists in the table and is spelled correctly.</span></span> <span data-ttu-id="6e48f-143">Nell'esempio seguente viene eseguita una query sulla vista del catalogo **sys.columns** per restituire tutti i nomi di colonna per una tabella specifica.</span><span class="sxs-lookup"><span data-stu-id="6e48f-143">The following example queries the **sys.columns** catalog view to return all column names for a given table.</span></span>  
  
    ```  
    SELECT name FROM sys.columns WHERE object_id = OBJECT_ID('schema_name.table_name');  
    ```  
  
-   <span data-ttu-id="6e48f-144">Distinzione tra maiuscole e minuscole delle regole di confronto del database.</span><span class="sxs-lookup"><span data-stu-id="6e48f-144">The case sensitivity of the database collation.</span></span> <span data-ttu-id="6e48f-145">L'istruzione seguente restituisce le regole di confronto del database specificato.</span><span class="sxs-lookup"><span data-stu-id="6e48f-145">The following statement returns the collation of the specified database.</span></span>  
  
    ```  
    SELECT collation_name FROM sys.databases WHERE name = 'database_name';  
    ```  
  
     <span data-ttu-id="6e48f-146">L'abbreviazione CS nel nome delle regole di confronto indica che le regole di confronto rispettano la distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="6e48f-146">The abbreviation CS in the collation name indicates the collation is case-sensitive.</span></span> <span data-ttu-id="6e48f-147">Latin1_General_CS_AS ad esempio è una regola di confronto con distinzione tra maiuscole e minuscole e distinzione tra caratteri accentati e non accentati.</span><span class="sxs-lookup"><span data-stu-id="6e48f-147">For example, Latin1_General_CS_AS is a case-sensitive and accent-sensitive collation.</span></span> <span data-ttu-id="6e48f-148">Modificare il nome di colonna in modo che corrisponda alla combinazione di maiuscole e minuscole del nome di colonna come definito nella tabella.</span><span class="sxs-lookup"><span data-stu-id="6e48f-148">Modify the column name to match the case of the column name as it is defined in the table.</span></span>  
  
-   <span data-ttu-id="6e48f-149">Riferimento non corretto a un alias di colonna.</span><span class="sxs-lookup"><span data-stu-id="6e48f-149">A column alias is referenced incorrectly.</span></span> <span data-ttu-id="6e48f-150">Modificare l'istruzione ripetendo l'espressione che definisce l'alias nella clausola appropriata oppure utilizzando una tabella derivata.</span><span class="sxs-lookup"><span data-stu-id="6e48f-150">Modify the statement by repeating the expression that defines the alias in the appropriate clause or by using a derived table.</span></span> <span data-ttu-id="6e48f-151">Nell'esempio seguente vengono ripetute le espressioni che definiscono l'alias `Year` nella clausola GROUP BY.</span><span class="sxs-lookup"><span data-stu-id="6e48f-151">The following example repeats the expressions that define the `Year` alias in the GROUP BY clause.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT DATEPART(yyyy,OrderDate) AS Year ,SUM(TotalDue) AS Total  
    FROM Sales.SalesOrderHeader  
    GROUP BY DATEPART(yyyy,OrderDate);  
    ```  
  
     <span data-ttu-id="6e48f-152">Nell'esempio seguente viene utilizzata una tabella derivata per rendere disponibile il nome di alias ad altre clausole nella query.</span><span class="sxs-lookup"><span data-stu-id="6e48f-152">The following example uses a derived table to make the alias name available to other clauses in the query.</span></span> <span data-ttu-id="6e48f-153">Si noti che l'alias `Year` viene definito nella clausola FROM, che viene elaborata per prima. In questo modo l'alias può essere utilizzato in altre clausole nella query.</span><span class="sxs-lookup"><span data-stu-id="6e48f-153">Notice that the alias `Year` is defined in the FROM clause, which is processed first, and so makes the alias available for use in other clauses in the query.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT d.Year, SUM(TotalDue) AS Total  
    FROM (SELECT DATEPART(yyyy,OrderDate) AS Year, TotalDue  
          FROM Sales.SalesOrderHeader)AS d  
    GROUP BY Year;  
    ```  
  
-   <span data-ttu-id="6e48f-154">La clausola WHEN NOT MATCHED BY SOURCE nell'istruzione MERGE fa riferimento a un valore cui è possibile accedere.</span><span class="sxs-lookup"><span data-stu-id="6e48f-154">The WHEN NOT MATCHED BY SOURCE clause in the MERGE statement refers to a value that can be accessed.</span></span> <span data-ttu-id="6e48f-155">Modificare l'istruzione MERGE in modo che venga restituita almeno una riga dalla tabella di origine nella clausola WHEN NOT MATCHED BY SOURCE.</span><span class="sxs-lookup"><span data-stu-id="6e48f-155">Modify the MERGE statement so that at least one row is returned by the source table in the WHEN NOT MATCHED BY SOURCE clause.</span></span> <span data-ttu-id="6e48f-156">Può ad esempio essere necessario aggiungere o modificare la condizione di ricerca specificata per la clausola.</span><span class="sxs-lookup"><span data-stu-id="6e48f-156">For example, you might need to add or revise the search condition specified for the clause.</span></span> <span data-ttu-id="6e48f-157">In alternativa, è possibile modificare la clausola per specificare un valore che non fa riferimento alla tabella di origine,</span><span class="sxs-lookup"><span data-stu-id="6e48f-157">Alternatively, you can modify the clause to specify a value that does not reference the source table.</span></span> <span data-ttu-id="6e48f-158">Ad esempio: `WHEN NOT MATCHED BY SOURCE THEN UPDATE SET TargetTable.Col1 = <expression, or other available value>`.</span><span class="sxs-lookup"><span data-stu-id="6e48f-158">For example, `WHEN NOT MATCHED BY SOURCE THEN UPDATE SET TargetTable.Col1 = <expression, or other available value>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e48f-159">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6e48f-159">See Also</span></span>  
 <span data-ttu-id="6e48f-160">[MERGE &#40;Transact-SQL&#41;](/sql/t-sql/statements/merge-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6e48f-160">[MERGE &#40;Transact-SQL&#41;](/sql/t-sql/statements/merge-transact-sql) </span></span>  
 <span data-ttu-id="6e48f-161">[FROM &#40;Transact-SQL&#41;](/sql/t-sql/queries/from-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6e48f-161">[FROM &#40;Transact-SQL&#41;](/sql/t-sql/queries/from-transact-sql) </span></span>  
 <span data-ttu-id="6e48f-162">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6e48f-162">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span></span>  
 [<span data-ttu-id="6e48f-163">UPDATE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="6e48f-163">UPDATE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/queries/update-transact-sql)  
  
  
