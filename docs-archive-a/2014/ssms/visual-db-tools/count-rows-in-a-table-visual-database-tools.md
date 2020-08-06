---
title: Contare le righe di una tabella (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- totals [SQL Server], row counts
- row counts [SQL Server]
- column values [SQL Server]
- number of rows
- number of values
- counting rows
ms.assetid: dda4296a-1d16-4e77-8d6f-e295f6dd4e87
author: stevestein
ms.author: sstein
ms.openlocfilehash: f6dca92fb955b776f56d9b51f28b1a486b89f18f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715896"
---
# <a name="count-rows-in-a-table-visual-database-tools"></a><span data-ttu-id="22e6d-102">Conteggio delle righe di una tabella (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="22e6d-102">Count Rows in a Table (Visual Database Tools)</span></span>
  <span data-ttu-id="22e6d-103">Il conteggio delle righe di una tabella consente di determinare:</span><span class="sxs-lookup"><span data-stu-id="22e6d-103">You can count rows in a table to determine:</span></span>  
  
-   <span data-ttu-id="22e6d-104">Il numero totale delle righe di una tabella, ad esempio il numero di tutti i libri nella tabella `titles` .</span><span class="sxs-lookup"><span data-stu-id="22e6d-104">The total number of rows in a table, for example, a count of all the books in a `titles` table.</span></span>  
  
-   <span data-ttu-id="22e6d-105">Il numero totale delle righe di una tabella che soddisfano una determinata condizione, ad esempio il numero di libri di uno specifico editore nella tabella `titles` .</span><span class="sxs-lookup"><span data-stu-id="22e6d-105">The number of rows in a table that meet a specific condition, for example, the number of books by one publisher in a `titles` table.</span></span>  
  
-   <span data-ttu-id="22e6d-106">Il numero di valori di una determinata colonna.</span><span class="sxs-lookup"><span data-stu-id="22e6d-106">The number of values in a particular column.</span></span>  
  
 <span data-ttu-id="22e6d-107">Dal conteggio dei valori in una colonna sono esclusi i valori Null.</span><span class="sxs-lookup"><span data-stu-id="22e6d-107">When you count values in a column, nulls are not included in the count.</span></span> <span data-ttu-id="22e6d-108">È ad esempio possibile contare il numero di libri nella tabella `titles` che contengono valori nella colonna `advance` .</span><span class="sxs-lookup"><span data-stu-id="22e6d-108">For example, you might count the number of books in a `titles` table that have values in the `advance` column.</span></span> <span data-ttu-id="22e6d-109">In base all'impostazione predefinita, nel conteggio vengono inclusi tutti i valori, non solo i valori univoci.</span><span class="sxs-lookup"><span data-stu-id="22e6d-109">By default, the count includes all values, not just unique values.</span></span>  
  
 <span data-ttu-id="22e6d-110">Per tutti i tre tipi di conteggio è utilizzata una procedura analoga.</span><span class="sxs-lookup"><span data-stu-id="22e6d-110">The procedures for all three types of counts are similar.</span></span>  
  
### <a name="to-count-all-the-rows-in-a-table"></a><span data-ttu-id="22e6d-111">Per contare tutte le righe di una tabella</span><span class="sxs-lookup"><span data-stu-id="22e6d-111">To count all the rows in a table</span></span>  
  
1.  <span data-ttu-id="22e6d-112">Assicurarsi che la tabella che si desidera riepilogare sia già presente nel riquadro Diagramma.</span><span class="sxs-lookup"><span data-stu-id="22e6d-112">Be sure the table you want to summarize is already present in the Diagram pane.</span></span>  
  
2.  <span data-ttu-id="22e6d-113">Fare clic con il pulsante destro del mouse sullo sfondo del riquadro Diagramma e scegliere **Aggiungi raggruppamento** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="22e6d-113">Right-click the background of the Diagram pane, then choose **Add Group By** from the shortcut menu.</span></span> <span data-ttu-id="22e6d-114">In [Progettazione query e Progettazione viste](visual-database-tools.md) verrà aggiunta una colonna **Group By** alla griglia nel riquadro Criteri.</span><span class="sxs-lookup"><span data-stu-id="22e6d-114">The [Query and View Designer](visual-database-tools.md) adds a **Group By** column to the grid in the Criteria pane.</span></span>  
  
3.  <span data-ttu-id="22e6d-115">Selezionare \*\* \* (tutte le colonne)\*\* nel rettangolo che rappresenta la tabella o l'oggetto con valori di tabella.</span><span class="sxs-lookup"><span data-stu-id="22e6d-115">Select **\* (All Columns)** in the rectangle representing the table or table-valued object.</span></span>  
  
     <span data-ttu-id="22e6d-116">In Progettazione query e Progettazione viste verrà inserito automaticamente il termine **Count** nella colonna **Group By** nel riquadro Criteri e verrà assegnato un alias alla colonna di cui si sta eseguendo il riepilogo.</span><span class="sxs-lookup"><span data-stu-id="22e6d-116">The Query and View Designer automatically fills the term **Count** into the **Group By** column in the Criteria pane and assigns a column alias to the column you are summarizing.</span></span> <span data-ttu-id="22e6d-117">Tale alias generato automaticamente può essere sostituito con un alias più significativo.</span><span class="sxs-lookup"><span data-stu-id="22e6d-117">You can replace this automatically generated alias with a more meaningful one.</span></span> <span data-ttu-id="22e6d-118">Per altre informazioni dettagliate, vedere [Creazione di alias di colonna &#40;Visual Database Tools&#41;](create-column-aliases-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="22e6d-118">For more details, see [Create Column Aliases &#40;Visual Database Tools&#41;](create-column-aliases-visual-database-tools.md).</span></span>  
  
4.  <span data-ttu-id="22e6d-119">Consente di eseguire la query.</span><span class="sxs-lookup"><span data-stu-id="22e6d-119">Run the query.</span></span>  
  
### <a name="to-count-all-the-rows-that-meet-a-condition"></a><span data-ttu-id="22e6d-120">Per contare tutte le righe che soddisfano una condizione</span><span class="sxs-lookup"><span data-stu-id="22e6d-120">To count all the rows that meet a condition</span></span>  
  
1.  <span data-ttu-id="22e6d-121">Assicurarsi che la tabella che si desidera riepilogare sia già presente nel riquadro Diagramma.</span><span class="sxs-lookup"><span data-stu-id="22e6d-121">Be sure the table you want to summarize is already present in the Diagram pane.</span></span>  
  
2.  <span data-ttu-id="22e6d-122">Fare clic con il pulsante destro del mouse sullo sfondo del riquadro Diagramma e scegliere **Aggiungi raggruppamento** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="22e6d-122">Right-click the background of the Diagram pane, then choose **Add Group By** from the shortcut menu.</span></span> <span data-ttu-id="22e6d-123">In Progettazione query e Progettazione viste verrà aggiunta una colonna **Group By** alla griglia nel riquadro Criteri.</span><span class="sxs-lookup"><span data-stu-id="22e6d-123">The Query and View Designer adds a **Group By** column to the grid in the Criteria pane.</span></span>  
  
3.  <span data-ttu-id="22e6d-124">Selezionare \*\* \* (tutte le colonne)\*\* nel rettangolo che rappresenta la tabella o l'oggetto con struttura di tabella.</span><span class="sxs-lookup"><span data-stu-id="22e6d-124">Select **\*(All Columns)** in the rectangle representing the table or table-structured object.</span></span>  
  
     <span data-ttu-id="22e6d-125">In Progettazione query e Progettazione viste verrà inserito automaticamente il termine **Count** nella colonna **Group By** nel riquadro Criteri e verrà assegnato un alias alla colonna di cui si sta eseguendo il riepilogo.</span><span class="sxs-lookup"><span data-stu-id="22e6d-125">The Query and View Designer automatically fills the term **Count** into the **Group By** column in the Criteria pane and assigns a column alias to the column you are summarizing.</span></span> <span data-ttu-id="22e6d-126">Per creare un'intestazione di colonna più utile nell'output della query, vedere [Creazione di alias di colonna &#40;Visual Database Tools&#41;](create-column-aliases-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="22e6d-126">To create a more useful column heading in query output, see [Create Column Aliases &#40;Visual Database Tools&#41;](create-column-aliases-visual-database-tools.md).</span></span>  
  
4.  <span data-ttu-id="22e6d-127">Aggiungere la colonna di dati da includere nella ricerca e deselezionare la casella di controllo nella colonna **Output**.</span><span class="sxs-lookup"><span data-stu-id="22e6d-127">Add the data column that you want to search, and then clear the check box in the **Output** column.</span></span>  
  
     <span data-ttu-id="22e6d-128">In Progettazione query e Progettazione viste il termine **Group By** verrà inserito automaticamente nella colonna **Group By** della griglia.</span><span class="sxs-lookup"><span data-stu-id="22e6d-128">The Query and View Designer automatically fills the term **Group By** into the **Group By** column of the grid.</span></span>  
  
5.  <span data-ttu-id="22e6d-129">Sostituire **Group By** nella colonna **Group By** con **Where**.</span><span class="sxs-lookup"><span data-stu-id="22e6d-129">Change **Group By** in the **Group By** column to **Where**.</span></span>  
  
6.  <span data-ttu-id="22e6d-130">Nella colonna **Filtro** per la colonna di dati da includere nella ricerca, specificare la condizione di ricerca.</span><span class="sxs-lookup"><span data-stu-id="22e6d-130">In the **Filter** column for the data column to search, enter the search condition.</span></span>  
  
7.  <span data-ttu-id="22e6d-131">Consente di eseguire la query.</span><span class="sxs-lookup"><span data-stu-id="22e6d-131">Run the query.</span></span>  
  
### <a name="to-count-the-values-in-a-column"></a><span data-ttu-id="22e6d-132">Per contare i valori di una colonna</span><span class="sxs-lookup"><span data-stu-id="22e6d-132">To count the values in a column</span></span>  
  
1.  <span data-ttu-id="22e6d-133">Assicurarsi che la tabella che si desidera riepilogare sia già presente nel riquadro Diagramma.</span><span class="sxs-lookup"><span data-stu-id="22e6d-133">Be sure the table you want to summarize is already present in the Diagram pane.</span></span>  
  
2.  <span data-ttu-id="22e6d-134">Fare clic con il pulsante destro del mouse sullo sfondo del riquadro Diagramma e scegliere **Aggiungi raggruppamento** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="22e6d-134">Right-click the background of the Diagram pane, then choose **Add Group By** from the shortcut menu.</span></span> <span data-ttu-id="22e6d-135">In Progettazione query e Progettazione viste verrà aggiunta una colonna **Group By** alla griglia nel riquadro Criteri.</span><span class="sxs-lookup"><span data-stu-id="22e6d-135">The Query and View Designer adds a **Group By** column to the grid in the Criteria pane.</span></span>  
  
3.  <span data-ttu-id="22e6d-136">Aggiungere al riquadro Criteri la colonna su cui si desidera eseguire il conteggio.</span><span class="sxs-lookup"><span data-stu-id="22e6d-136">Add the column that you want to count to the Criteria pane.</span></span>  
  
     <span data-ttu-id="22e6d-137">In Progettazione query e Progettazione viste il termine **Group By** verrà inserito automaticamente nella colonna **Group By** della griglia.</span><span class="sxs-lookup"><span data-stu-id="22e6d-137">The Query and View Designer automatically fills the term **Group By** into the **Group By** column of the grid.</span></span>  
  
4.  <span data-ttu-id="22e6d-138">Sostituire **Group By** nella colonna **Group By** con **Count**.</span><span class="sxs-lookup"><span data-stu-id="22e6d-138">Change **Group By** in the **Group By** column to **Count**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="22e6d-139">Per contare solo i valori univoci, scegliere **Count Distinct**.</span><span class="sxs-lookup"><span data-stu-id="22e6d-139">To count only unique values, choose **Count Distinct**.</span></span>  
  
5.  <span data-ttu-id="22e6d-140">Consente di eseguire la query.</span><span class="sxs-lookup"><span data-stu-id="22e6d-140">Run the query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22e6d-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="22e6d-141">See Also</span></span>  
 <span data-ttu-id="22e6d-142">[Ordinare e raggruppare i risultati delle query &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="22e6d-142">[Sort and Group Query Results &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="22e6d-143">Creare un riepilogo dei risultati di query &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="22e6d-143">Summarize Query Results &#40;Visual Database Tools&#41;</span></span>](summarize-query-results-visual-database-tools.md)  
  
  
