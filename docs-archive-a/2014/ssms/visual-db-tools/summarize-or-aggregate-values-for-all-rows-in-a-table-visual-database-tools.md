---
title: Riepilogare o aggregare valori per tutte le righe di una tabella (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- summarizing query results
- aggregate functions [SQL Server], summarizing query results
ms.assetid: f5af876e-f937-4110-ba09-07999c35a699
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5c4d80c8ab2b811b8e796f0a37b2180a2866c332
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720729"
---
# <a name="summarize-or-aggregate-values-for-all-rows-in-a-table-visual-database-tools"></a><span data-ttu-id="55a03-102">Riepilogo o aggregazione di valori per tutte le righe di una tabella (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="55a03-102">Summarize or Aggregate Values for All Rows in a Table (Visual Database Tools)</span></span>
  <span data-ttu-id="55a03-103">Con una funzione di aggregazione è possibile creare un riepilogo di tutti i valori di una tabella.</span><span class="sxs-lookup"><span data-stu-id="55a03-103">Using an aggregate function, you can create a summary for all the values in a table.</span></span> <span data-ttu-id="55a03-104">Per visualizzare, ad esempio, il prezzo totale di tutti i libri nella tabella `titles` , è possibile creare una query analoga alla seguente:</span><span class="sxs-lookup"><span data-stu-id="55a03-104">For example, you can create a query such as the following to display the total price for all books in the `titles` table:</span></span>  
  
```  
SELECT SUM(price)  
FROM titles  
```  
  
 <span data-ttu-id="55a03-105">Se si utilizza la funzione di aggregazione con più colonne, sarà possibile creare più aggregazioni nella stessa query.</span><span class="sxs-lookup"><span data-stu-id="55a03-105">You can create multiple aggregations in the same query by using aggregate functions with more than one column.</span></span> <span data-ttu-id="55a03-106">È ad esempio possibile creare una query per il calcolo del totale della colonna `price` e la media della colonna `discount` .</span><span class="sxs-lookup"><span data-stu-id="55a03-106">For example, you can create a query that calculates the total of the `price` column and the average of the `discount` column.</span></span>  
  
 <span data-ttu-id="55a03-107">Inoltre, è possibile aggregare la stessa colonna in modi diversi, calcolando ad esempio totale, conteggio e media nella stessa query.</span><span class="sxs-lookup"><span data-stu-id="55a03-107">You can also aggregate the same column in different ways (such as totaling, counting, and averaging) in the same query.</span></span> <span data-ttu-id="55a03-108">L'esempio seguente riguarda una query in cui viene calcolata la media ed eseguito il riepilogo della colonna `price` della tabella `titles` :</span><span class="sxs-lookup"><span data-stu-id="55a03-108">For example, the following query averages and summarizes the `price` column from the `titles` table:</span></span>  
  
```  
SELECT AVG(price), SUM(price)  
FROM titles  
```  
  
 <span data-ttu-id="55a03-109">Se si aggiunge un criterio di ricerca sarà possibile aggregare il subset delle righe che soddisfano tale criterio.</span><span class="sxs-lookup"><span data-stu-id="55a03-109">If you add a search condition, you can aggregate the subset of rows that meet that condition.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="55a03-110">È inoltre possibile contare tutte le righe della tabella o le righe che soddisfano una specifica condizione.</span><span class="sxs-lookup"><span data-stu-id="55a03-110">You can also count all the rows in the table or the ones that meet a specific condition.</span></span> <span data-ttu-id="55a03-111">Per informazioni dettagliate, vedere [Conteggio delle righe di una tabella &#40;Visual Database Tools&#41;](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="55a03-111">For details, see [Count Rows in a Table &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="55a03-112">Quando si crea un singolo valore di aggregazione per tutte le righe di una tabella, vengono visualizzati solo i valori aggregati.</span><span class="sxs-lookup"><span data-stu-id="55a03-112">When you create a single aggregation value for all rows in a table, you display only the aggregate values themselves.</span></span> <span data-ttu-id="55a03-113">Se ad esempio si calcola il valore totale della colonna `price` della tabella `titles` , non vengono visualizzati i singoli titoli, i nomi dei server di pubblicazione e così via.</span><span class="sxs-lookup"><span data-stu-id="55a03-113">For example, if you are totaling the value of the `price` column of the `titles` table, you would not also display individual titles, publisher names, and so on.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="55a03-114">Quando si crea un subtotale e dunque si creano gruppi, è possibile visualizzare i valori delle colonne per ogni gruppo.</span><span class="sxs-lookup"><span data-stu-id="55a03-114">If you are subtotaling - that is, creating groups - you can display column values for each group.</span></span> <span data-ttu-id="55a03-115">Per informazioni dettagliate, vedere [Raggruppare righe nei risultati di una query &#40;Visual Database Tools&#41;](group-rows-in-query-results-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="55a03-115">For details, see [Group Rows in Query Results &#40;Visual Database Tools&#41;](group-rows-in-query-results-visual-database-tools.md).</span></span>  
  
### <a name="to-aggregate-values-for-all-rows"></a><span data-ttu-id="55a03-116">Per aggregare i valori di tutte le righe</span><span class="sxs-lookup"><span data-stu-id="55a03-116">To aggregate values for all rows</span></span>  
  
1.  <span data-ttu-id="55a03-117">Assicurarsi che la tabella che si desidera aggregare sia già presente nel riquadro Diagramma.</span><span class="sxs-lookup"><span data-stu-id="55a03-117">Be sure the table you want to aggregate is already present in the Diagram pane.</span></span>  
  
2.  <span data-ttu-id="55a03-118">Fare clic con il pulsante destro del mouse sullo sfondo del riquadro Diagramma e scegliere **Raggruppa** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="55a03-118">Right-click the background of the Diagram pane, then choose **Group By** from the shortcut menu.</span></span> <span data-ttu-id="55a03-119">In [Progettazione query e Progettazione viste](query-and-view-designer-tools-visual-database-tools.md) verrà aggiunta una colonna **Group by** alla griglia nel riquadro criteri.</span><span class="sxs-lookup"><span data-stu-id="55a03-119">The [Query and View Designer](query-and-view-designer-tools-visual-database-tools.md) adds a **Group By** column to the grid in the Criteria pane.</span></span>  
  
3.  <span data-ttu-id="55a03-120">Aggiungere al riquadro Criteri la colonna da aggregare.</span><span class="sxs-lookup"><span data-stu-id="55a03-120">Add the column you want to aggregate to the Criteria pane.</span></span> <span data-ttu-id="55a03-121">Assicurarsi che la colonna sia contrassegnata per l'output.</span><span class="sxs-lookup"><span data-stu-id="55a03-121">Be sure that the column is marked for output.</span></span>  
  
     <span data-ttu-id="55a03-122">Verrà assegnato automaticamente un alias di colonna alla colonna di cui si effettua il riepilogo.</span><span class="sxs-lookup"><span data-stu-id="55a03-122">The Query and View Designer automatically assigns a column alias to the column you are summarizing.</span></span> <span data-ttu-id="55a03-123">Tale alias può essere sostituito con un alias più significativo.</span><span class="sxs-lookup"><span data-stu-id="55a03-123">You can replace this alias with a more meaningful one.</span></span> <span data-ttu-id="55a03-124">Per altre informazioni dettagliate, vedere [Creazione di alias di colonna &#40;Visual Database Tools&#41;](create-column-aliases-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="55a03-124">For details, see [Create Column Aliases &#40;Visual Database Tools&#41;](create-column-aliases-visual-database-tools.md).</span></span>  
  
4.  <span data-ttu-id="55a03-125">Nella colonna della griglia **Group By** selezionare la funzione di aggregazione appropriata, ad esempio **Sum**, **Avg**, **Min**, **Max**, **Count**.</span><span class="sxs-lookup"><span data-stu-id="55a03-125">In the **Group By** grid column, select the appropriate aggregate function, such as: **Sum**, **Avg**, **Min**, **Max**, **Count**.</span></span> <span data-ttu-id="55a03-126">Per aggregare solo le righe univoche nel set di risultati, scegliere una funzione di aggregazione con l'opzione DISTINCT, ad esempio **Min Distinct**.</span><span class="sxs-lookup"><span data-stu-id="55a03-126">If you want to aggregate only unique rows in the result set, choose an aggregate function with the DISTINCT options, such as **Min Distinct**.</span></span> <span data-ttu-id="55a03-127">Non scegliere **Group By**, **Expression**o **Where**, in quanto tali opzioni non sono applicabili per l'aggregazione di tutte le righe.</span><span class="sxs-lookup"><span data-stu-id="55a03-127">Do not choose **Group By**, **Expression**, or **Where**, because those options do not apply when you are aggregating all rows.</span></span>  
  
     <span data-ttu-id="55a03-128">Il nome della colonna nell'istruzione del [riquadro SQL](sql-pane-visual-database-tools.md) verrà sostituito con la funzione di aggregazione specificata in Progettazione query e Progettazione viste.</span><span class="sxs-lookup"><span data-stu-id="55a03-128">The Query and View Designer replaces the column name in the statement in the [SQL pane](sql-pane-visual-database-tools.md) with the aggregate function that you specify.</span></span> <span data-ttu-id="55a03-129">L'istruzione SQL, ad esempio, può essere analoga alla seguente:</span><span class="sxs-lookup"><span data-stu-id="55a03-129">For example, the SQL statement might look like this:</span></span>  
  
    ```  
    SELECT SUM(price)  
    FROM titles  
    ```  
  
5.  <span data-ttu-id="55a03-130">Per creare più aggregazioni in una query, ripetere i passaggi 3 e 4.</span><span class="sxs-lookup"><span data-stu-id="55a03-130">If you want to create more than one aggregation in the query, repeat steps 3 and 4.</span></span>  
  
     <span data-ttu-id="55a03-131">Quando si aggiunge un'altra colonna all'elenco di output della query o all'elenco di ordinamento, il termine **Group By** verrà inserito automaticamente nella colonna **Group By** della griglia.</span><span class="sxs-lookup"><span data-stu-id="55a03-131">When you add another column to the query output list or order by list, the Query and View Designer automatically fills the term **Group By** into the **Group By** column of the grid.</span></span> <span data-ttu-id="55a03-132">Selezionare la funzione di aggregazione desiderata.</span><span class="sxs-lookup"><span data-stu-id="55a03-132">Select the appropriate aggregate function.</span></span>  
  
6.  <span data-ttu-id="55a03-133">Aggiungere le condizioni di ricerca eventualmente necessarie per specificare il subset di righe da riepilogare.</span><span class="sxs-lookup"><span data-stu-id="55a03-133">Add search conditions, if any, to specify the subset of rows you want to summarize.</span></span>  
  
 <span data-ttu-id="55a03-134">Quando si esegue la query, nel riquadro Risultati verranno visualizzate le aggregazioni specificate.</span><span class="sxs-lookup"><span data-stu-id="55a03-134">When you execute the query, the Results pane displays the aggregations that you specified.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="55a03-135">In Progettazione query e Progettazione viste le funzioni di aggregazione vengono mantenute nell'istruzione SQL nel riquadro SQL fino a quando non viene disabilitata esplicitamente la modalità di raggruppamento.</span><span class="sxs-lookup"><span data-stu-id="55a03-135">The Query and View Designer maintains aggregate functions as part of the SQL statement in the SQL pane until you explicitly turn off Group By mode.</span></span> <span data-ttu-id="55a03-136">Se pertanto si modifica la query cambiandone il tipo o cambiando le tabelle o gli oggetti con valori di tabella presenti nel riquadro Diagramma, la query risultante potrebbe includere funzioni di aggregazione non valide.</span><span class="sxs-lookup"><span data-stu-id="55a03-136">Therefore, if you modify your query by changing its type or by changing which tables or table-valued objects are present in the Diagram pane, the resulting query might include invalid aggregate functions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55a03-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="55a03-137">See Also</span></span>  
 <span data-ttu-id="55a03-138">[Ordinare e raggruppare i risultati delle query &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="55a03-138">[Sort and Group Query Results &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="55a03-139">Creare un riepilogo dei risultati di query &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="55a03-139">Summarize Query Results &#40;Visual Database Tools&#41;</span></span>](summarize-query-results-visual-database-tools.md)  
  
  
