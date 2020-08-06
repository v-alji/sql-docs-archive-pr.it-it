---
title: Raggruppare righe nei risultati di una query (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- summarizing table subsets
- grouping rows
- grouping query results
ms.assetid: b07082d5-4d55-4903-9af9-4c470554c6d3
author: stevestein
ms.author: sstein
ms.openlocfilehash: 52de25c86425d95f5917d89c8a3f4fec8939fb16
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629687"
---
# <a name="group-rows-in-query-results-visual-database-tools"></a><span data-ttu-id="e2d9e-102">Raggruppare righe nei risultati di una query (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="e2d9e-102">Group Rows in Query Results (Visual Database Tools)</span></span>
  <span data-ttu-id="e2d9e-103">Se si desidera creare dei subtotali o visualizzare altre informazioni riepilogative per i subset di una tabella, è possibile utilizzare una query di aggregazione.</span><span class="sxs-lookup"><span data-stu-id="e2d9e-103">If you want to create subtotals or show other summary information for subsets of a table, you create groups using an aggregate query.</span></span> <span data-ttu-id="e2d9e-104">Ciascun gruppo creato riepiloga i dati per tutte le righe della tabella con lo stesso valore.</span><span class="sxs-lookup"><span data-stu-id="e2d9e-104">Each group summarizes the data for all the rows in the table that have the same value.</span></span>  
  
 <span data-ttu-id="e2d9e-105">Può essere necessario, ad esempio, visualizzare il prezzo medio di un libro nella tabella `titles` , suddividendo i risultati in base all'editore.</span><span class="sxs-lookup"><span data-stu-id="e2d9e-105">For example, you might want to see the average price of a book in the `titles` table, but break the results down by publisher.</span></span> <span data-ttu-id="e2d9e-106">Per ottenere questo risultato, è necessario raggruppare la query in base all'editore (ad esempio, `pub_id`).</span><span class="sxs-lookup"><span data-stu-id="e2d9e-106">To do so, you group the query by publisher (for example, `pub_id`).</span></span> <span data-ttu-id="e2d9e-107">L'output della query potrebbe essere analogo al seguente:</span><span class="sxs-lookup"><span data-stu-id="e2d9e-107">The resulting query output might look like this:</span></span>  
  
 <span data-ttu-id="e2d9e-108">![Risultati della query: prezzo medio raggruppato per server di pubblicazione](../../database-engine/media//dv3w9e1.gif "Risultati della query: prezzo medio raggruppato per server di pubblicazione")</span><span class="sxs-lookup"><span data-stu-id="e2d9e-108">![Query results: average price grouped by publisher](../../database-engine/media//dv3w9e1.gif "Query results: average price grouped by publisher")</span></span>  
  
 <span data-ttu-id="e2d9e-109">Quando si raggruppano i dati, è possibile visualizzare solo dati riepilogativi o raggruppati, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="e2d9e-109">When you group data, you can display only summary or grouped data, such as:</span></span>  
  
-   <span data-ttu-id="e2d9e-110">I valori delle colonne raggruppate (quelli che compaiono nella clausola GROUP BY).</span><span class="sxs-lookup"><span data-stu-id="e2d9e-110">The values of the grouped columns (those that appear in the GROUP BY clause).</span></span> <span data-ttu-id="e2d9e-111">Nell'esempio precedente, `pub_id` è la colonna raggruppata.</span><span class="sxs-lookup"><span data-stu-id="e2d9e-111">In the example above, `pub_id` is the grouped column.</span></span>  
  
-   <span data-ttu-id="e2d9e-112">I valori prodotti da funzioni di aggregazione quali SUM( ) e AVG( ).</span><span class="sxs-lookup"><span data-stu-id="e2d9e-112">Values produced by aggregate functions such as SUM( ) and AVG( ).</span></span> <span data-ttu-id="e2d9e-113">Nell'esempio precedente, la seconda colonna viene generata usando la funzione AVG( ) con la colonna `price` .</span><span class="sxs-lookup"><span data-stu-id="e2d9e-113">In the example above, the second column is produced by using the AVG( ) function with the `price` column.</span></span>  
  
 <span data-ttu-id="e2d9e-114">Non è possibile visualizzare valori di singole righe.</span><span class="sxs-lookup"><span data-stu-id="e2d9e-114">You cannot display values from individual rows.</span></span> <span data-ttu-id="e2d9e-115">Se ad esempio si effettua il raggruppamento solo in base all'editore, non sarà possibile visualizzare anche singoli titoli nella query.</span><span class="sxs-lookup"><span data-stu-id="e2d9e-115">For example, if you group only by publisher, you cannot also display individual titles in the query.</span></span> <span data-ttu-id="e2d9e-116">Quindi, se si aggiungono colonne all'output della query, in [Progettazione query e Progettazione viste](visual-database-tools.md) queste verranno aggiunte automaticamente alla clausola GROUP BY dell'istruzione nel [riquadro SQL](sql-pane-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="e2d9e-116">Therefore, if you add columns to the query output, the [Query and View Designer](visual-database-tools.md) automatically adds them to the GROUP BY clause of the statement in the [SQL pane](sql-pane-visual-database-tools.md).</span></span> <span data-ttu-id="e2d9e-117">Se invece si desidera che sia la colonna ad essere aggregata, sarà possibile specificare una funzione di aggregazione per tale colonna.</span><span class="sxs-lookup"><span data-stu-id="e2d9e-117">If you want a column to be aggregated instead, you can specify an aggregate function for that column.</span></span>  
  
 <span data-ttu-id="e2d9e-118">Se si definisce un raggruppamento in base a più colonne, in ogni gruppo della query verranno visualizzati i valori aggregati per tutte le colonne raggruppate.</span><span class="sxs-lookup"><span data-stu-id="e2d9e-118">If you group by more than one column, each group in the query shows the aggregate values for all grouping columns.</span></span>  
  
 <span data-ttu-id="e2d9e-119">Nella seguente query, ad esempio, effettuata sulla tabella `titles` il raggruppamento viene effettuato in base all'editore (`pub_id`) e al tipo di libro (`type`).</span><span class="sxs-lookup"><span data-stu-id="e2d9e-119">For example, the following query against the `titles` table groups by publisher (`pub_id`) and also by book type (`type`).</span></span> <span data-ttu-id="e2d9e-120">I risultati della query vengono ordinati in base all'editore e mostrano informazioni di riepilogo su ogni tipo di libro prodotto dall'editore:</span><span class="sxs-lookup"><span data-stu-id="e2d9e-120">The query results are ordered by publisher and show summary information for each different type of book that the publisher produces:</span></span>  
  
```  
SELECT pub_id, type, SUM(price) Total_price  
FROM titles  
GROUP BY pub_id, type  
```  
  
 <span data-ttu-id="e2d9e-121">L'output risultante può essere analogo al seguente:</span><span class="sxs-lookup"><span data-stu-id="e2d9e-121">The resulting output might look like this:</span></span>  
  
 <span data-ttu-id="e2d9e-122">![Risultati della query: prezzo raggruppato per server di pubblicazione e tipo](../../database-engine/media//dv3w9e2.gif "Risultati della query: prezzo raggruppato per server di pubblicazione e tipo")</span><span class="sxs-lookup"><span data-stu-id="e2d9e-122">![Query results: price grouped by publisher and type](../../database-engine/media//dv3w9e2.gif "Query results: price grouped by publisher and type")</span></span>  
  
### <a name="to-group-rows"></a><span data-ttu-id="e2d9e-123">Per raggruppare le righe</span><span class="sxs-lookup"><span data-stu-id="e2d9e-123">To group rows</span></span>  
  
1.  <span data-ttu-id="e2d9e-124">Iniziare la query aggiungendo le tabelle da riepilogare nel riquadro Diagramma.</span><span class="sxs-lookup"><span data-stu-id="e2d9e-124">Start the query by adding the tables you want to summarize to the Diagram pane.</span></span>  
  
2.  <span data-ttu-id="e2d9e-125">Fare clic con il pulsante destro del mouse sullo sfondo del riquadro Diagramma e scegliere **Aggiungi raggruppamento** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="e2d9e-125">Right-click the background of the Diagram pane, then choose **Add Group By** from the shortcut menu.</span></span> <span data-ttu-id="e2d9e-126">In Progettazione query e Progettazione viste verrà aggiunta una colonna **Group By** alla griglia nel riquadro Criteri.</span><span class="sxs-lookup"><span data-stu-id="e2d9e-126">The Query and View Designer adds a **Group By** column to the grid in the Criteria pane.</span></span>  
  
3.  <span data-ttu-id="e2d9e-127">Aggiungere al riquadro Criteri la colonna o la combinazione di colonne da raggruppare.</span><span class="sxs-lookup"><span data-stu-id="e2d9e-127">Add the column or columns you want to group to the Criteria pane.</span></span> <span data-ttu-id="e2d9e-128">Per visualizzare la colonna nell'output della query, assicurarsi che la colonna **Output** sia selezionata per l'output.</span><span class="sxs-lookup"><span data-stu-id="e2d9e-128">If you want the column to appear in the query output, be sure that the **Output** column is selected for output.</span></span>  
  
     <span data-ttu-id="e2d9e-129">In Progettazione query e Progettazione viste sarà aggiunta una clausola GROUP BY all'istruzione nel riquadro SQL.</span><span class="sxs-lookup"><span data-stu-id="e2d9e-129">The Query and View Designer adds a GROUP BY clause to the statement in the SQL pane.</span></span> <span data-ttu-id="e2d9e-130">L'istruzione SQL, ad esempio, può essere analoga alla seguente:</span><span class="sxs-lookup"><span data-stu-id="e2d9e-130">For example, the SQL statement might look like this:</span></span>  
  
    ```  
    SELECT pub_id  
    FROM titles  
    GROUP BY pub_id  
    ```  
  
4.  <span data-ttu-id="e2d9e-131">Aggiungere al riquadro Criteri la colonna o la combinazione di colonne da aggregare.</span><span class="sxs-lookup"><span data-stu-id="e2d9e-131">Add the column or columns you want to aggregate to the Criteria pane.</span></span> <span data-ttu-id="e2d9e-132">Assicurarsi che la colonna sia contrassegnata per l'output.</span><span class="sxs-lookup"><span data-stu-id="e2d9e-132">Be sure that the column is marked for output.</span></span>  
  
5.  <span data-ttu-id="e2d9e-133">Nella cella della griglia **Group By** per la colonna da aggregare, selezionare la funzione di aggregazione appropriata.</span><span class="sxs-lookup"><span data-stu-id="e2d9e-133">In the **Group By** grid cell for the column that is going to be aggregated, select the appropriate aggregate function.</span></span>  
  
     <span data-ttu-id="e2d9e-134">Verrà assegnato automaticamente un alias di colonna alla colonna di cui si effettua il riepilogo.</span><span class="sxs-lookup"><span data-stu-id="e2d9e-134">The Query and View Designer automatically assigns a column alias to the column you are summarizing.</span></span> <span data-ttu-id="e2d9e-135">Tale alias generato automaticamente può essere sostituito con un alias più significativo.</span><span class="sxs-lookup"><span data-stu-id="e2d9e-135">You can replace this automatically generated alias with a more meaningful one.</span></span> <span data-ttu-id="e2d9e-136">Per altre informazioni dettagliate, vedere [Creazione di alias di colonna &#40;Visual Database Tools&#41;](create-column-aliases-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="e2d9e-136">For more details, see [Create Column Aliases &#40;Visual Database Tools&#41;](create-column-aliases-visual-database-tools.md).</span></span>  
  
     <span data-ttu-id="e2d9e-137">![Aggiunta di un alias di colonna al set di risultati della query](../../database-engine/media//dv3w9e3.gif "Aggiunta di un alias di colonna al set di risultati della query")</span><span class="sxs-lookup"><span data-stu-id="e2d9e-137">![Adding a column alias to the query result set](../../database-engine/media//dv3w9e3.gif "Adding a column alias to the query result set")</span></span>  
  
     <span data-ttu-id="e2d9e-138">L'istruzione corrispondente nel riquadro **SQL** può essere analoga alla seguente:</span><span class="sxs-lookup"><span data-stu-id="e2d9e-138">The corresponding statement in the **SQL** pane might look like this:</span></span>  
  
    ```  
    SELECT   pub_id, SUM(price) AS Totalprice  
    FROM     titles  
    GROUP BY pub_id  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="e2d9e-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e2d9e-139">See Also</span></span>  
 [<span data-ttu-id="e2d9e-140">Ordinare e raggruppare i risultati delle query &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="e2d9e-140">Sort and Group Query Results &#40;Visual Database Tools&#41;</span></span>](sort-and-group-query-results-visual-database-tools.md)  
  
  
