---
title: Aggiungere colonne a query (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- inserting columns
- columns [SQL Server], adding
- queries [SQL Server], columns
- adding columns
ms.assetid: 82f3ba72-3d72-4fb1-8179-2a953a782787
author: stevestein
ms.author: sstein
ms.openlocfilehash: 49c6e575eea2d4437be1f16b400ca22120471fcf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626472"
---
# <a name="add-columns-to-queries-visual-database-tools"></a><span data-ttu-id="c3d76-102">Aggiunta di colonne a query (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="c3d76-102">Add Columns to Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="c3d76-103">Per utilizzare una colonna in una query, è necessario aggiungerla alla query.</span><span class="sxs-lookup"><span data-stu-id="c3d76-103">To use a column in a query, you must add it to the query.</span></span> <span data-ttu-id="c3d76-104">È possibile aggiungere una colonna per visualizzarla nell'output della query, per utilizzarla per l'ordinamento oppure per ricercarne o riepilogarne il contenuto.</span><span class="sxs-lookup"><span data-stu-id="c3d76-104">You might add a column to display it in query output, to use it for sorting, to search the contents of the column, or to summarize its contents.</span></span> <span data-ttu-id="c3d76-105">È possibile decidere quali colonne utilizzate nella query devono essere incluse nel riquadro Risultati quando viene eseguita la query.</span><span class="sxs-lookup"><span data-stu-id="c3d76-105">You can decide which of the columns you use in the query are included in the results pane when the query is run.</span></span> <span data-ttu-id="c3d76-106">Per altre informazioni, vedere [Rimuovere colonne dai risultati della query &#40;Visual Database Tools&#41;](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c3d76-106">For more information see [Remove Columns from Query Results &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c3d76-107">Per visualizzare il tipo di dati di una colonna in Progettazione query e Progettazione viste, selezionare la tabella o l'oggetto con valori di tabella nel **riquadro Diagramma** e nella finestra delle proprietà fare clic su Elenco colonne.</span><span class="sxs-lookup"><span data-stu-id="c3d76-107">To view the data type of a column in Query and View Designer; select the table or table-valued object in the **Diagram Pane** and in the properties window click Column List.</span></span> <span data-ttu-id="c3d76-108">Fare clic sui **puntini di sospensione (...)** per aprire la finestra di dialogo **Elenco colonne**.</span><span class="sxs-lookup"><span data-stu-id="c3d76-108">Then click the **ellipses (...)** to open the **Column List** dialog box.</span></span>  
  
 <span data-ttu-id="c3d76-109">Ovunque si utilizzi una colonna in una query, è anche possibile utilizzare un'espressione costituita da una qualunque combinazione di colonne, valori letterali, operatori e funzioni.</span><span class="sxs-lookup"><span data-stu-id="c3d76-109">Wherever you use a column in a query, you can also use an expression that can consist of any combination of columns, literals, operators, and functions.</span></span>  
  
### <a name="to-add-an-individual-column"></a><span data-ttu-id="c3d76-110">Per aggiungere una singola colonna</span><span class="sxs-lookup"><span data-stu-id="c3d76-110">To add an individual column</span></span>  
  
-   <span data-ttu-id="c3d76-111">Nel **riquadro Diagramma**selezionare la casella di controllo accanto alla colonna da includere.</span><span class="sxs-lookup"><span data-stu-id="c3d76-111">In the **Diagram Pane**, select the check box next to the column that you want to include.</span></span>  
  
     <span data-ttu-id="c3d76-112">-oppure-</span><span class="sxs-lookup"><span data-stu-id="c3d76-112">-or-</span></span>  
  
-   <span data-ttu-id="c3d76-113">Nel **riquadro Criteri**spostarsi sulla prima riga vuota della griglia, fare clic sul campo nella colonna **Colonna** e selezionare un nome di colonna dall'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="c3d76-113">In the **Criteria Pane**, move to the first blank grid row, click the field in the **Column** column, and select a column name from the drop-down list.</span></span>  
  
### <a name="to-add-all-columns-for-one-table-or-table-valued-object"></a><span data-ttu-id="c3d76-114">Per aggiungere tutte le colonne di una tabella o di un oggetto con valori di tabella</span><span class="sxs-lookup"><span data-stu-id="c3d76-114">To add all columns for one table or table-valued object</span></span>  
  
-   <span data-ttu-id="c3d76-115">Nel **riquadro diagramma**selezionare la casella di controllo accanto a \*\* \* (tutte le colonne)\*\*.</span><span class="sxs-lookup"><span data-stu-id="c3d76-115">In the **Diagram Pane**, select the check box next to **\*(All Columns)**.</span></span>  
  
### <a name="to-add-all-columns-for-all-tables-and-table-structured-objects"></a><span data-ttu-id="c3d76-116">Per aggiungere tutte le colonne per tutte le tabelle e gli oggetti con struttura di tabella</span><span class="sxs-lookup"><span data-stu-id="c3d76-116">To add all columns for all tables and table-structured objects</span></span>  
  
1.  <span data-ttu-id="c3d76-117">Assicurarsi che non sia selezionata alcuna linea di join nel **Riquadro operazioni tabella** .</span><span class="sxs-lookup"><span data-stu-id="c3d76-117">Make sure no join lines in the **Table Operations Pane** are selected.</span></span>  
  
2.  <span data-ttu-id="c3d76-118">Fare clic con il pulsante destro del mouse nello spazio vuoto della finestra Progettazione e scegliere **Proprietà** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="c3d76-118">Right-click in the empty space of the Design window and choose **Properties** from the shortcut menu.</span></span>  
  
3.  <span data-ttu-id="c3d76-119">Nella finestra Proprietà fare clic su **Tutte le colonne** e scegliere **Sì** o **No** dall'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="c3d76-119">In the Properties window click **Output all columns** and choose **Yes** or **No** from the dropdown list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3d76-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c3d76-120">See Also</span></span>  
 <span data-ttu-id="c3d76-121">[Rimuovere colonne dai risultati della query &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="c3d76-121">[Remove Columns from Query Results &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 <span data-ttu-id="c3d76-122">[Rimuovere colonne da query &#40;Visual Database Tools&#41;](remove-columns-from-queries-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="c3d76-122">[Remove Columns from Queries &#40;Visual Database Tools&#41;](remove-columns-from-queries-visual-database-tools.md) </span></span>  
 <span data-ttu-id="c3d76-123">[Specificare i criteri di ricerca &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="c3d76-123">[Specify Search Criteria &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md) </span></span>  
 <span data-ttu-id="c3d76-124">[Riepilogare i risultati delle query &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="c3d76-124">[Summarize Query Results &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="c3d76-125">Eseguire operazioni di base con le query &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="c3d76-125">Perform Basic Operations with Queries &#40;Visual Database Tools&#41;</span></span>](perform-basic-operations-with-queries-visual-database-tools.md)  
  
  
