---
title: Utilizzo delle clausole HAVING e WHERE nella stessa query (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- search criteria [SQL Server], excluding rows
- search criteria [SQL Server], WHERE clause
- search conditions [SQL Server], HAVING clause
- row excluded in search [SQL Server]
- search criteria [SQL Server], HAVING clause
- HAVING clause, search criteria
- search conditions [SQL Server], WHERE clause
- WHERE clause, search criteria
- excluding rows
ms.assetid: 1e07cf56-b4b7-4c49-8ddd-c276812a7148
author: stevestein
ms.author: sstein
ms.openlocfilehash: 20f6b471a60bf225ee61bdbbf0ecec30f21a92cf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712687"
---
# <a name="use-having-and-where-clauses-in-the-same-query-visual-database-tools"></a><span data-ttu-id="31563-102">Utilizzo delle clausole HAVING e WHERE nella stessa query (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="31563-102">Use HAVING and WHERE Clauses in the Same Query (Visual Database Tools)</span></span>
  <span data-ttu-id="31563-103">In alcuni casi può essere necessario escludere singole righe dai gruppi (utilizzando una clausola WHERE) prima di applicare una condizione ai gruppi (utilizzando una clausola HAVING).</span><span class="sxs-lookup"><span data-stu-id="31563-103">In some instances, you might want to exclude individual rows from groups (using a WHERE clause) before applying a condition to groups as a whole (using a HAVING clause).</span></span>  
  
 <span data-ttu-id="31563-104">La clausola HAVING è analoga alla clausola WHERE ma è applicabile solo ai gruppi come insieme, ossia alle righe nel set di risultati che rappresentano i gruppi, mentre la clausola WHERE è applicabile a righe singole.</span><span class="sxs-lookup"><span data-stu-id="31563-104">A HAVING clause is like a WHERE clause, but applies only to groups as a whole (that is, to the rows in the result set representing groups), whereas the WHERE clause applies to individual rows.</span></span> <span data-ttu-id="31563-105">Una query può contenere sia una clausola WHERE che una clausola HAVING.</span><span class="sxs-lookup"><span data-stu-id="31563-105">A query can contain both a WHERE clause and a HAVING clause.</span></span> <span data-ttu-id="31563-106">In questo caso:</span><span class="sxs-lookup"><span data-stu-id="31563-106">In that case:</span></span>  
  
-   <span data-ttu-id="31563-107">La clausola WHERE viene applicata prima alle singole righe nelle tabelle o negli oggetti con valori di tabella nel riquadro Diagramma.</span><span class="sxs-lookup"><span data-stu-id="31563-107">The WHERE clause is applied first to the individual rows in the tables or table-valued objects in the Diagram pane.</span></span> <span data-ttu-id="31563-108">Vengono raggruppate solo le righe che soddisfano le condizioni della clausola WHERE.</span><span class="sxs-lookup"><span data-stu-id="31563-108">Only the rows that meet the conditions in the WHERE clause are grouped.</span></span>  
  
-   <span data-ttu-id="31563-109">Successivamente viene applicata la clausola HAVING alle righe del set di risultati.</span><span class="sxs-lookup"><span data-stu-id="31563-109">The HAVING clause is then applied to the rows in the result set.</span></span> <span data-ttu-id="31563-110">Nell'output della query saranno visualizzati solo i gruppi che soddisfano le condizioni HAVING.</span><span class="sxs-lookup"><span data-stu-id="31563-110">Only the groups that meet the HAVING conditions appear in the query output.</span></span> <span data-ttu-id="31563-111">La clausola HAVING può essere applicata solo alle colonne presenti anche nella clausola GROUP BY o in una funzione di aggregazione.</span><span class="sxs-lookup"><span data-stu-id="31563-111">You can apply a HAVING clause only to columns that also appear in the GROUP BY clause or in an aggregate function.</span></span>  
  
 <span data-ttu-id="31563-112">Si supponga ad esempio di unire le tabelle `titles` e `publishers` per creare una query in cui sia visualizzato il prezzo medio dei libri per un set di editori,</span><span class="sxs-lookup"><span data-stu-id="31563-112">For example, imagine that you are joining the `titles` and `publishers` tables to create a query showing the average book price for a set of publishers.</span></span> <span data-ttu-id="31563-113">limitando la ricerca a un set specifico di editori, ad esempio quelli dello stato della California.</span><span class="sxs-lookup"><span data-stu-id="31563-113">You want to see the average price for only a specific set of publishers - perhaps only the publishers in the state of California.</span></span> <span data-ttu-id="31563-114">e a un prezzo medio maggiore di 10 dollari.</span><span class="sxs-lookup"><span data-stu-id="31563-114">And even then, you want to see the average price only if it is over $10.00.</span></span>  
  
 <span data-ttu-id="31563-115">In questo caso, prima di calcolare il prezzo medio è possibile stabilire la prima condizione con una clausola WHERE che escluda tutti gli editori che non si trovano in California.</span><span class="sxs-lookup"><span data-stu-id="31563-115">You can establish the first condition by including a WHERE clause, which discards any publishers that are not in California, before calculating average prices.</span></span> <span data-ttu-id="31563-116">La seconda condizione richiede una clausola HAVING, in quanto la condizione è basata sui risultati del raggruppamento e del riepilogo di dati.</span><span class="sxs-lookup"><span data-stu-id="31563-116">The second condition requires a HAVING clause, because the condition is based on the results of grouping and summarizing the data.</span></span> <span data-ttu-id="31563-117">L'istruzione SQL risultante sarà analoga alla seguente:</span><span class="sxs-lookup"><span data-stu-id="31563-117">The resulting SQL statement might look like this:</span></span>  
  
```  
SELECT titles.pub_id, AVG(titles.price)  
FROM titles INNER JOIN publishers  
   ON titles.pub_id = publishers.pub_id  
WHERE publishers.state = 'CA'  
GROUP BY titles.pub_id  
HAVING AVG(price) > 10  
```  
  
 <span data-ttu-id="31563-118">È possibile creare sia clausole HAVING che clausole WHERE nel riquadro Criteri.</span><span class="sxs-lookup"><span data-stu-id="31563-118">You can create both HAVING and WHERE clauses in the Criteria pane.</span></span> <span data-ttu-id="31563-119">In base all'impostazione predefinita, se si specifica una condizione di ricerca per una colonna, tale condizione entrerà a far parte della clausola HAVING,</span><span class="sxs-lookup"><span data-stu-id="31563-119">By default, if you specify a search condition for a column, the condition becomes part of the HAVING clause.</span></span> <span data-ttu-id="31563-120">ma sarà comunque possibile cambiarla in una clausola.</span><span class="sxs-lookup"><span data-stu-id="31563-120">However, you can change the condition to be a WHERE clause.</span></span>  
  
 <span data-ttu-id="31563-121">È possibile creare una clausola WHERE e una clausola HAVING relative alla stessa colonna.</span><span class="sxs-lookup"><span data-stu-id="31563-121">You can create a WHERE clause and HAVING clause involving the same column.</span></span> <span data-ttu-id="31563-122">A tale scopo, è necessario aggiungere due volte la colonna nel riquadro Criteri, quindi assegnare un'istanza alla clausola HAVING e l'altra alla clausola WHERE.</span><span class="sxs-lookup"><span data-stu-id="31563-122">To do so, you must add the column twice to the Criteria pane, then specify one instance as part of the HAVING clause and the other instance as part of the WHERE clause.</span></span>  
  
### <a name="to-specify-a-where-condition-in-an-aggregate-query"></a><span data-ttu-id="31563-123">Per specificare una condizione WHERE in una query di aggregazione</span><span class="sxs-lookup"><span data-stu-id="31563-123">To specify a WHERE condition in an aggregate query</span></span>  
  
1.  <span data-ttu-id="31563-124">Specificare i gruppi per la query.</span><span class="sxs-lookup"><span data-stu-id="31563-124">Specify the groups for your query.</span></span> <span data-ttu-id="31563-125">Per informazioni dettagliate, vedere [Raggruppare righe nei risultati di una query &#40;Visual Database Tools&#41;](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="31563-125">For details, see [Group Rows in Query Results &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
2.  <span data-ttu-id="31563-126">Se necessario, aggiungere nel riquadro Criteri la colonna su cui si desidera basare la condizione WHERE.</span><span class="sxs-lookup"><span data-stu-id="31563-126">If it is not already in the Criteria pane, add the column on which you want to base the WHERE condition.</span></span>  
  
3.  <span data-ttu-id="31563-127">Se la colonna di dati non è inclusa nella clausola GROUP BY o nella funzione di aggregazione, eliminare il contenuto della colonna **Output** .</span><span class="sxs-lookup"><span data-stu-id="31563-127">Clear the **Output** column unless the data column is part of the GROUP BY clause or included in an aggregate function.</span></span>  
  
4.  <span data-ttu-id="31563-128">Nella colonna **Filtro** specificare la condizione WHERE.</span><span class="sxs-lookup"><span data-stu-id="31563-128">In the **Filter** column, specify the WHERE condition.</span></span> <span data-ttu-id="31563-129">La condizione verrà aggiunta alla clausola HAVING dell'istruzione SQL.</span><span class="sxs-lookup"><span data-stu-id="31563-129">The Query and View Designer adds the condition to the HAVING clause of the SQL statement.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="31563-130">Nella query illustrata nell'esempio della procedura vengono unite due tabelle: `titles` e `publishers`.</span><span class="sxs-lookup"><span data-stu-id="31563-130">The query shown in the example for this procedure joins two tables, `titles` and `publishers`.</span></span>  
  
     <span data-ttu-id="31563-131">A questo punto della creazione della query, l'istruzione SQL contiene una clausola HAVING:</span><span class="sxs-lookup"><span data-stu-id="31563-131">At this point in the query, the SQL statement contains a HAVING clause:</span></span>  
  
    ```  
    SELECT titles.pub_id, AVG(titles.price)  
    FROM titles INNER JOIN publishers   
       ON titles.pub_id = publishers.pub_id  
    GROUP BY titles.pub_id  
    HAVING publishers.state = 'CA'  
    ```  
  
5.  <span data-ttu-id="31563-132">Selezionare **Where** dall'elenco di opzioni di raggruppamento e riepilogo nella colonna **Group By** .</span><span class="sxs-lookup"><span data-stu-id="31563-132">In the **Group By** column, select **Where** from the list of group and summary options.</span></span> <span data-ttu-id="31563-133">La condizione verrà rimossa dalla clausola HAVING dell'istruzione SQL e aggiunta alla clausola WHERE.</span><span class="sxs-lookup"><span data-stu-id="31563-133">The Query and View Designer removes the condition from the HAVING clause in the SQL statement and adds it to the WHERE clause.</span></span>  
  
     <span data-ttu-id="31563-134">L'istruzione SQL includerà ora una clausola WHERE:</span><span class="sxs-lookup"><span data-stu-id="31563-134">The SQL statement changes to include a WHERE clause instead:</span></span>  
  
    ```  
    SELECT titles.pub_id, AVG(titles.price)  
    FROM titles INNER JOIN publishers   
       ON titles.pub_id = publishers.pub_id  
    WHERE publishers.state = 'CA'  
    GROUP BY titles.pub_id  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="31563-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="31563-135">See Also</span></span>  
 <span data-ttu-id="31563-136">[Ordinare e raggruppare i risultati delle query &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="31563-136">[Sort and Group Query Results &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="31563-137">Creare un riepilogo dei risultati di query &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="31563-137">Summarize Query Results &#40;Visual Database Tools&#41;</span></span>](summarize-query-results-visual-database-tools.md)  
  
  
