---
title: Riquadro Risultati (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- View Designer, Results pane
- result sets [SQL Server], queries
- synchronization [SQL Server], query results with definition
- displaying query results in grid
- grid showing query results [SQL Server]
- showing query results in grid
- Query Designer [SQL Server], Results pane
- results [SQL Server], query
- viewing query results
- queries [SQL Server], results
- Results pane
ms.assetid: 6309a1bc-a628-4141-8bb5-b35924bd19f9
author: stevestein
ms.author: sstein
ms.openlocfilehash: f0db32336931f74777be56befcde9501dc484b69
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623698"
---
# <a name="results-pane-visual-database-tools"></a><span data-ttu-id="fc7e0-102">Results Pane (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="fc7e0-102">Results Pane (Visual Database Tools)</span></span>
  <span data-ttu-id="fc7e0-103">Nel riquadro Risultati vengono visualizzati i risultati dell'ultima query di selezione (SELECT) eseguita.</span><span class="sxs-lookup"><span data-stu-id="fc7e0-103">The Results pane shows the results of the most recently executed SELECT query.</span></span> <span data-ttu-id="fc7e0-104">I risultati di altri tipi di query vengono visualizzati in finestre di messaggio. Il riquadro Risultati viene visualizzato automaticamente quando si apre o si crea una query o una vista oppure quando vengono restituiti i dati di una tabella.</span><span class="sxs-lookup"><span data-stu-id="fc7e0-104">(The results of other query types are displayed in message boxes.) To open the results pane, open or create a query or view or return a table's data.</span></span> <span data-ttu-id="fc7e0-105">Se il riquadro Risultati non viene visualizzato per impostazione predefinita, scegliere **Pannello** dal menu **Progettazione query**, quindi **Risultati**.</span><span class="sxs-lookup"><span data-stu-id="fc7e0-105">If the results pane doesn't show by default, from the **Query Designer** menu, point to **Pane**, and then click **Results**.</span></span>  
  
## <a name="what-you-can-do-in-the-results-pane"></a><span data-ttu-id="fc7e0-106">Operazioni che è possibile eseguire nel riquadro Risultati</span><span class="sxs-lookup"><span data-stu-id="fc7e0-106">What You Can Do in the Results Pane</span></span>  
  
-   <span data-ttu-id="fc7e0-107">Visualizzare in una griglia simile a un foglio di calcolo il set di risultati dell'ultima query SELECT eseguita.</span><span class="sxs-lookup"><span data-stu-id="fc7e0-107">View the result set for the most recently executed SELECT query in a spreadsheet-like grid.</span></span>  
  
-   <span data-ttu-id="fc7e0-108">Nel caso di query o viste che visualizzano i dati di una sola tabella o vista, modificare i valori nelle singole colonne del set di risultati, aggiungere nuove righe ed eliminare righe esistenti.</span><span class="sxs-lookup"><span data-stu-id="fc7e0-108">For queries or views that show data from a single table or view, you can edit the values in individual columns in the result set, add new rows, and delete existing rows.</span></span>  
  
## <a name="limitations-in-the-results-pane"></a><span data-ttu-id="fc7e0-109">Limitazioni relative al riquadro Risultati</span><span class="sxs-lookup"><span data-stu-id="fc7e0-109">Limitations in the Results Pane</span></span>  
  
-   <span data-ttu-id="fc7e0-110">I risultati restituiti da funzioni con valori di tabella possono essere aggiornati solo in alcuni casi.</span><span class="sxs-lookup"><span data-stu-id="fc7e0-110">Results returned by table-valued functions can only be updated in some cases.</span></span>  
  
-   <span data-ttu-id="fc7e0-111">Le query o le viste in cui sono incluse colonne provenienti da più tabelle o viste non possono essere aggiornate.</span><span class="sxs-lookup"><span data-stu-id="fc7e0-111">Queries or views that include columns from more than one table or view cannot be updated.</span></span>  
  
-   <span data-ttu-id="fc7e0-112">I risultati restituiti da una stored procedure non possono essere aggiornati.</span><span class="sxs-lookup"><span data-stu-id="fc7e0-112">Results returned by a stored procedure cannot be updated.</span></span>  
  
-   <span data-ttu-id="fc7e0-113">Le query o le viste in cui viene utilizzata la clausola GROUP BY o DISTINCT non possono essere aggiornate.</span><span class="sxs-lookup"><span data-stu-id="fc7e0-113">Queries or views using the GROUP BY or DISTINCT clauses are not updatable.</span></span>  
  
## <a name="navigating-in-the-results-pane"></a><span data-ttu-id="fc7e0-114">Navigazione all'interno del riquadro Risultati</span><span class="sxs-lookup"><span data-stu-id="fc7e0-114">Navigating in the Results Pane</span></span>  
 <span data-ttu-id="fc7e0-115">Nella parte inferiore del riquadro Risultati è presente una barra di navigazione che consente di passare velocemente da un record all'altro.</span><span class="sxs-lookup"><span data-stu-id="fc7e0-115">You can quickly navigate through the records using the navigation bar at the bottom of the Results pane.</span></span>  
  
 <span data-ttu-id="fc7e0-116">Sono disponibili pulsanti per spostarsi sul primo e sull'ultimo record, sul record successivo e su quello precedente oppure direttamente su un record specifico.</span><span class="sxs-lookup"><span data-stu-id="fc7e0-116">There are buttons for going to the first and last records, the next and previous records, and for going to a particular record.</span></span>  
  
 <span data-ttu-id="fc7e0-117">Per spostarsi su un record specifico, digitare il numero delle riga nella casella di testo all'interno della barra di navigazione, quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="fc7e0-117">To go to a particular record, type the number of the row in the text box in the navigation bar and then press ENTER.</span></span>  
  
 <span data-ttu-id="fc7e0-118">Per informazioni sull'uso di tasti di scelta rapida in Progettazione query e Progettazione viste, vedere [Navigazione all'interno di Progettazione viste e Progettazione query &#40;Visual Database Tools&#41;](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="fc7e0-118">For information about using keyboard shortcuts in the Query and View Designer see [Navigate in the Query and View Designer &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
## <a name="keeping-the-results-set-synchronized-with-the-query-definition"></a><span data-ttu-id="fc7e0-119">Mantenimento della sincronizzazione tra il set di risultati e la definizione della query</span><span class="sxs-lookup"><span data-stu-id="fc7e0-119">Keeping the Results Set Synchronized with the Query Definition</span></span>  
 <span data-ttu-id="fc7e0-120">Mentre si lavora sui risultati di una query o di una vista, è possibile che i record nel riquadro Risultati perdano la sincronizzazione con la definizione della query.</span><span class="sxs-lookup"><span data-stu-id="fc7e0-120">While you are working on the results of a query or view it is possible for the records in the results pane to get out of synchronization with the query's definition.</span></span> <span data-ttu-id="fc7e0-121">Se ad esempio è stata eseguita una query per quattro delle cinque colonne di una tabella e quindi è stato utilizzato il riquadro Diagramma per aggiungere la quinta colonna alla definizione della query, i dati di tale colonna non verranno aggiunti automaticamente al riquadro Risultati.</span><span class="sxs-lookup"><span data-stu-id="fc7e0-121">For example, if you run a query for four out of five columns in a table, and then use the Diagram pane to add the fifth column to the definition of the query, that fifth column's data will not automatically be added to the Results pane.</span></span> <span data-ttu-id="fc7e0-122">Perché il riquadro Risultati rifletta la nuova definizione della query, sarà necessario eseguire ancora una volta la query.</span><span class="sxs-lookup"><span data-stu-id="fc7e0-122">To make the results pane reflect the new query definition, run the query again.</span></span>  
  
 <span data-ttu-id="fc7e0-123">Se una query è stata modificata, nell'angolo inferiore destro del riquadro Risultati verranno visualizzati un'icona di avviso e un messaggio indicante che la query è cambiata.</span><span class="sxs-lookup"><span data-stu-id="fc7e0-123">If a query changes, an alert icon and the text "Query Changed" appears in the lower-right corner of the results pane.</span></span> <span data-ttu-id="fc7e0-124">L'icona verrà visualizzata anche nell'angolo superiore sinistro del riquadro.</span><span class="sxs-lookup"><span data-stu-id="fc7e0-124">The icon is repeated in the upper-left corner of the pane.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc7e0-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fc7e0-125">See Also</span></span>  
 <span data-ttu-id="fc7e0-126">[Creazione di query &#40;Visual Database Tools&#41;](create-queries-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="fc7e0-126">[Create Queries &#40;Visual Database Tools&#41;](create-queries-visual-database-tools.md) </span></span>  
 <span data-ttu-id="fc7e0-127">[Eseguire query &#40;Visual Database Tools&#41;](run-queries-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="fc7e0-127">[Run Queries &#40;Visual Database Tools&#41;](run-queries-visual-database-tools.md) </span></span>  
 <span data-ttu-id="fc7e0-128">[Procedure per la progettazione di query e viste &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="fc7e0-128">[Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span></span>  
 <span data-ttu-id="fc7e0-129">[Riquadro diagramma &#40;Visual Database Tools&#41;](diagram-pane-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="fc7e0-129">[Diagram Pane &#40;Visual Database Tools&#41;](diagram-pane-visual-database-tools.md) </span></span>  
 <span data-ttu-id="fc7e0-130">[Riquadro Criteri &#40;Visual Database Tools&#41;](criteria-pane-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="fc7e0-130">[Criteria Pane &#40;Visual Database Tools&#41;](criteria-pane-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="fc7e0-131">Usare i dati nel riquadro Risultati &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="fc7e0-131">Work with Data in the Results Pane &#40;Visual Database Tools&#41;</span></span>](results-pane-visual-database-tools.md)  
  
  
