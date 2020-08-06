---
title: Creazione di query utilizzando elementi oltre a una tabella (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- user-defined functions [SQL Server], queries
- queries [SQL Server], creating
ms.assetid: 8e4a1f0a-8a42-4733-be8d-e21d6dbddb33
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0444c20fe10080949930f23623d5699f7fd3712c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623706"
---
# <a name="create-queries-using-something-besides-a-table-visual-database-tools"></a><span data-ttu-id="a3ca9-102">Creazione di query mediante l'utilizzo di altre origini oltre a una tabella (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="a3ca9-102">Create Queries using Something Besides a Table (Visual Database Tools)</span></span>
  <span data-ttu-id="a3ca9-103">Quando si crea una query di recupero dati, si definiscono le colonne e le righe da estrarre e la posizione dei dati originali.</span><span class="sxs-lookup"><span data-stu-id="a3ca9-103">Whenever you write a retrieval query, you articulate what columns you want, what rows you want, and where the query processor should find the original data.</span></span> <span data-ttu-id="a3ca9-104">I dati originali in genere sono costituiti da una tabella o da più tabelle unite in join,</span><span class="sxs-lookup"><span data-stu-id="a3ca9-104">Typically, this original data consists of a table or several tables joined together.</span></span> <span data-ttu-id="a3ca9-105">ma possono anche provenire da origini diverse dalle tabelle, quali</span><span class="sxs-lookup"><span data-stu-id="a3ca9-105">But the original data can come from sources other than tables.</span></span> <span data-ttu-id="a3ca9-106">viste, query, sinonimi o funzioni definite dall'utente che restituiscono una tabella.</span><span class="sxs-lookup"><span data-stu-id="a3ca9-106">In fact, it can come from views, queries, synonyms, or user-defined functions that return a table.</span></span>  
  
## <a name="using-a-view-in-place-of-a-table"></a><span data-ttu-id="a3ca9-107">Utilizzo di una vista al posto di una tabella</span><span class="sxs-lookup"><span data-stu-id="a3ca9-107">Using a View in Place of a Table</span></span>  
 <span data-ttu-id="a3ca9-108">È possibile selezionare le righe di una vista.</span><span class="sxs-lookup"><span data-stu-id="a3ca9-108">You can select rows from a view.</span></span> <span data-ttu-id="a3ca9-109">Si supponga ad esempio che il database includa una vista denominata "ExpensiveBooks", nella quale ogni riga descrive un libro il cui prezzo supera i 19,99 dollari.</span><span class="sxs-lookup"><span data-stu-id="a3ca9-109">For example, suppose the database includes a view called "ExpensiveBooks," in which each row describes a title whose price exceeds 19.99.</span></span> <span data-ttu-id="a3ca9-110">La definizione della vista potrebbe essere simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="a3ca9-110">The view definition might look like this:</span></span>  
  
```  
SELECT *  
FROM titles  
WHERE price > 19.99  
  
```  
  
 <span data-ttu-id="a3ca9-111">È possibile selezionare i libri di psicologia più costosi semplicemente selezionando i libri di psicologia nella vista ExpensiveBooks.</span><span class="sxs-lookup"><span data-stu-id="a3ca9-111">You can select the expensive psychology books merely by selecting the psychology books from the ExpensiveBooks view.</span></span> <span data-ttu-id="a3ca9-112">Il codice SQL risultante potrebbe essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="a3ca9-112">The resulting SQL might look like this:</span></span>  
  
```  
SELECT *  
FROM ExpensiveBooks  
WHERE type = 'psychology'  
  
```  
  
 <span data-ttu-id="a3ca9-113">Analogamente, una vista può essere utilizzata in un'operazione di JOIN.</span><span class="sxs-lookup"><span data-stu-id="a3ca9-113">Similarly, a view can participate in a JOIN operation.</span></span> <span data-ttu-id="a3ca9-114">È possibile, ad esempio, trovare le vendite dei libri più costosi semplicemente eseguendo il join della tabella sales con la vista ExpensiveBooks.</span><span class="sxs-lookup"><span data-stu-id="a3ca9-114">For example, you can find the sales of expensive books merely by joining the sales table to the ExpensiveBooks view.</span></span> <span data-ttu-id="a3ca9-115">Il codice SQL risultante potrebbe essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="a3ca9-115">The resulting SQL might look like this:</span></span>  
  
```  
SELECT *  
FROM sales   
         INNER JOIN   
         ExpensiveBooks   
         ON sales.title_id   
         =  ExpensiveBooks.title_id  
  
```  
  
 <span data-ttu-id="a3ca9-116">Per altre informazioni sull'aggiunta di una vista a una query, vedere [Aggiunta di tabelle a query &#40;Visual Database Tools&#41;](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a3ca9-116">For more information about adding a view to a query, see [Add Tables to Queries &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
## <a name="using-a-query-in-place-of-a-table"></a><span data-ttu-id="a3ca9-117">Utilizzo di una query al posto di una tabella</span><span class="sxs-lookup"><span data-stu-id="a3ca9-117">Using a Query in Place of a Table</span></span>  
 <span data-ttu-id="a3ca9-118">È possibile selezionare le righe di una query.</span><span class="sxs-lookup"><span data-stu-id="a3ca9-118">You can select rows from a query.</span></span> <span data-ttu-id="a3ca9-119">Si supponga, ad esempio, di avere già scritto una query che recupera i titoli e gli identificatori dei libri scritti da più autori.</span><span class="sxs-lookup"><span data-stu-id="a3ca9-119">For example, suppose you have already written a query retrieving titles and identifiers of the coauthored books - the books with more than one author.</span></span> <span data-ttu-id="a3ca9-120">Il codice SQL potrebbe essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="a3ca9-120">The SQL might look like this:</span></span>  
  
```  
SELECT   
     titles.title_id, title, type  
FROM   
     titleauthor   
         INNER JOIN  
         titles   
         ON titleauthor.title_id   
         =  titles.title_id   
GROUP BY   
     titles.title_id, title, type  
HAVING COUNT(*) > 1  
  
```  
  
 <span data-ttu-id="a3ca9-121">È quindi possibile scrivere un'altra query che sfrutta questo risultato.</span><span class="sxs-lookup"><span data-stu-id="a3ca9-121">You can then write another query that builds on this result.</span></span> <span data-ttu-id="a3ca9-122">Ad esempio, è possibile scrivere una query che recupera i libri di psicologia scritti da più autori.</span><span class="sxs-lookup"><span data-stu-id="a3ca9-122">For example, you can write a query that retrieves the coauthored psychology books.</span></span> <span data-ttu-id="a3ca9-123">Per scrivere questa nuova query, si può utilizzare la query esistente come origine dei dati della nuova query.</span><span class="sxs-lookup"><span data-stu-id="a3ca9-123">To write this new query, you can use the existing query as the source of the new query's data.</span></span> <span data-ttu-id="a3ca9-124">Il codice SQL risultante potrebbe essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="a3ca9-124">The resulting SQL might look like this:</span></span>  
  
```  
SELECT   
    title  
FROM   
    (  
    SELECT   
        titles.title_id,   
        title,   
        type  
    FROM   
        titleauthor   
            INNER JOIN  
            titles   
            ON titleauthor.title_id   
            =  titles.title_id   
    GROUP BY   
        titles.title_id,   
        title,   
        type  
    HAVING COUNT(*) > 1  
    )   
    co_authored_books  
WHERE     type = 'psychology'  
  
```  
  
 <span data-ttu-id="a3ca9-125">Il testo evidenziato indica la query esistente utilizzata come origine dei dati della nuova query.</span><span class="sxs-lookup"><span data-stu-id="a3ca9-125">The emphasized text shows the existing query used as the source of the new query's data.</span></span> <span data-ttu-id="a3ca9-126">Si noti che la nuova query utilizza un alias ("co_authored_books") per la query esistente.</span><span class="sxs-lookup"><span data-stu-id="a3ca9-126">Note that the new query uses an alias ("co_authored_books") for the existing query.</span></span> <span data-ttu-id="a3ca9-127">Per altre informazioni sugli alias, vedere [Creazione di alias di tabella &#40;Visual Database Tools&#41;](create-table-aliases-visual-database-tools.md) e [Creazione di alias di colonna &#40;Visual Database Tools&#41;](create-column-aliases-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a3ca9-127">For more information about aliases, see [Create Table Aliases &#40;Visual Database Tools&#41;](create-table-aliases-visual-database-tools.md) and [Create Column Aliases &#40;Visual Database Tools&#41;](create-column-aliases-visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="a3ca9-128">Analogamente, una query può essere utilizzata in un'operazione di JOIN.</span><span class="sxs-lookup"><span data-stu-id="a3ca9-128">Similarly, a query can participate in a JOIN operation.</span></span> <span data-ttu-id="a3ca9-129">È possibile, ad esempio, trovare le vendite dei libri più costosi scritti da più autori semplicemente eseguendo il join della vista ExpensiveBooks con la query che recupera i libri scritti da più autori.</span><span class="sxs-lookup"><span data-stu-id="a3ca9-129">For example, you can find the sales of expensive coauthored books merely by joining the ExpensiveBooks view to the query retrieving the coauthored books.</span></span> <span data-ttu-id="a3ca9-130">Il codice SQL risultante potrebbe essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="a3ca9-130">The resulting SQL might look like this:</span></span>  
  
```  
SELECT   
    ExpensiveBooks.title  
FROM   
    ExpensiveBooks   
        INNER JOIN  
        (  
        SELECT   
            titles.title_id,   
            title,   
            type  
        FROM   
            titleauthor   
                INNER JOIN  
                titles   
                ON titleauthor.title_id   
                =  titles.title_id   
        GROUP BY   
            titles.title_id,   
            title,   
            type  
        HAVING COUNT(*) > 1  
        )  
```  
  
 <span data-ttu-id="a3ca9-131">Per altre informazioni sull'aggiunta di una tabella a una query, vedere [Aggiunta di tabelle a query &#40;Visual Database Tools&#41;](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a3ca9-131">For more information about adding a query to a query, see [Add Tables to Queries &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
## <a name="using-a-user-defined-function-in-place-of-a-table"></a><span data-ttu-id="a3ca9-132">Utilizzo di una funzione definita dall'utente al posto di una tabella</span><span class="sxs-lookup"><span data-stu-id="a3ca9-132">Using a User-Defined Function in Place of a Table</span></span>  
 <span data-ttu-id="a3ca9-133">In SQL Server 2000 o versione successiva è possibile creare una funzione definita dall'utente che restituisca una tabella.</span><span class="sxs-lookup"><span data-stu-id="a3ca9-133">In SQL Server 2000 or higher, you can create a user-defined function that returns a table.</span></span> <span data-ttu-id="a3ca9-134">Tali funzioni risultano utili per l'esecuzione di logiche procedurali o complesse.</span><span class="sxs-lookup"><span data-stu-id="a3ca9-134">Such functions are useful for performing complex or procedural logic.</span></span>  
  
 <span data-ttu-id="a3ca9-135">Si supponga ad esempio che la tabella dei dipendenti contenga un'ulteriore colonna, employee.manager_emp_id, e che una chiave esterna di manager_emp_id sia presente in employee.emp_id.</span><span class="sxs-lookup"><span data-stu-id="a3ca9-135">For example, suppose the employee table contains an additional column, employee.manager_emp_id, and that a foreign key exists from manager_emp_id to employee.emp_id.</span></span> <span data-ttu-id="a3ca9-136">All'interno di ciascuna riga della tabella dei dipendenti, la colonna manager_emp_id indica il superiore di un dipendente</span><span class="sxs-lookup"><span data-stu-id="a3ca9-136">Within each row of the employee table, the manager_emp_id column indicates the employee's boss.</span></span> <span data-ttu-id="a3ca9-137">o più precisamente, indica l'emp_id del superiore del dipendente.</span><span class="sxs-lookup"><span data-stu-id="a3ca9-137">More precisely, it indicates the employee's boss's emp_id.</span></span> <span data-ttu-id="a3ca9-138">È possibile creare una funzione definita dall'utente che restituisca una tabella contenente una riga per ciascun dipendente facente parte della gerarchia organizzativa di un particolare responsabile di alto livello.</span><span class="sxs-lookup"><span data-stu-id="a3ca9-138">You can create a user-defined function that returns a table containing one row for each employee working within a particular high-level manager's organizational hierarchy.</span></span> <span data-ttu-id="a3ca9-139">La funzione potrebbe essere denominata fn_GetWholeTeam e progettata in modo da accettare una variabile di input, ovvero l'emp_id del responsabile di cui si vuole recuperare il team.</span><span class="sxs-lookup"><span data-stu-id="a3ca9-139">You might call the function fn_GetWholeTeam, and design it to take an input variable - the emp_id of the manager whose team you want to retrieve.</span></span>  
  
 <span data-ttu-id="a3ca9-140">È possibile scrivere una query che utilizzi la funzione fn_GetWholeTeam come origine dei dati.</span><span class="sxs-lookup"><span data-stu-id="a3ca9-140">You can write a query that uses the fn_GetWholeTeam function as a source of data.</span></span> <span data-ttu-id="a3ca9-141">Il codice SQL risultante potrebbe essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="a3ca9-141">The resulting SQL might look like this:</span></span>  
  
```  
SELECT *   
FROM   
     fn_GetWholeTeam ('VPA30890F')  
  
```  
  
 <span data-ttu-id="a3ca9-142">"VPA30890F" è l'emp_id del responsabile di cui si desidera recuperare l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a3ca9-142">"VPA30890F" is the emp_id of the manager whose organization you want to retrieve.</span></span> <span data-ttu-id="a3ca9-143">Per altre informazioni sull'aggiunta di una funzione definita dall'utente a una query, vedere [Aggiunta di tabelle a query &#40;Visual Database Tools&#41;](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a3ca9-143">For more information about adding a user-defined function to a query, see [Add Tables to Queries &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span> <span data-ttu-id="a3ca9-144">Per una descrizione completa delle funzioni definite dall'utente, vedere [Funzioni definite dall'utente](../../relational-databases/user-defined-functions/user-defined-functions.md).</span><span class="sxs-lookup"><span data-stu-id="a3ca9-144">For a complete description of user-defined functions, see [User-Defined Functions](../../relational-databases/user-defined-functions/user-defined-functions.md).</span></span>  
  
  
