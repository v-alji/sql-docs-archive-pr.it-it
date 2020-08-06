---
title: Strumenti di progettazione di query e viste (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.querydesigner
- vdt.pane.diagram
- vdt.pane.grid
- vdt.dlgbox.querybuilder
- vdt.pane.sql
- vdt.pane.results
helpviewer_keywords:
- Query Designer [SQL Server], panes
- View Designer, panes
- Query Designer [SQL Server], components
- View Designer, components
ms.assetid: 12e4b5a5-b793-4b6c-a0e5-c450c49bf26f
author: stevestein
ms.author: sstein
ms.openlocfilehash: 29bd3fa9e171551197927aae0d1bc00446df6e7f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720783"
---
# <a name="query-and-view-designer-tools-visual-database-tools"></a><span data-ttu-id="09291-102">Strumenti di progettazione di query e viste (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="09291-102">Query and View Designer Tools (Visual Database Tools)</span></span>
  <span data-ttu-id="09291-103">Quando si progetta una query, una vista, una funzione inline o una stored procedure a istruzione singola, la finestra di progettazione utilizzata è costituita da quattro riquadri: Diagramma, Criteri, SQL e Risultati.</span><span class="sxs-lookup"><span data-stu-id="09291-103">When you design a query, view, in-line function, or single-statement stored procedure, the designer you use consists of four panes: the Diagram pane, the Criteria pane, the SQL pane, and the Results pane.</span></span>  
  
 <span data-ttu-id="09291-104">![Progettazione query](../../database-engine/media//vs-queryviewdsgpanes.gif "Progettazione query")</span><span class="sxs-lookup"><span data-stu-id="09291-104">![Query Designer](../../database-engine/media//vs-queryviewdsgpanes.gif "Query Designer")</span></span>  
  
-   <span data-ttu-id="09291-105">Il riquadro Diagramma visualizza le tabelle e gli altri oggetti con valori di tabella su cui si esegue la query.</span><span class="sxs-lookup"><span data-stu-id="09291-105">The Diagram pane displays the tables and other table-valued objects that you are querying.</span></span> <span data-ttu-id="09291-106">Ogni rettangolo rappresenta una tabella o un oggetto con valori di tabella e visualizza le colonne di dati disponibili.</span><span class="sxs-lookup"><span data-stu-id="09291-106">Each rectangle represents a table or table-valued object and shows the available data columns.</span></span> <span data-ttu-id="09291-107">I join sono indicati da linee fra i rettangoli.</span><span class="sxs-lookup"><span data-stu-id="09291-107">Joins are indicated by lines between the rectangles.</span></span> <span data-ttu-id="09291-108">Per altre informazioni, vedere [Riquadro Diagramma &#40;Visual Database Tools&#41;](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="09291-108">For more information, see [Diagram Pane &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
-   <span data-ttu-id="09291-109">Il riquadro Criteri contiene una griglia simile a un foglio di calcolo in cui è possibile specificare varie opzioni, ad esempio le colonne di dati da visualizzare, le righe da selezionare, come raggruppare le righe e così via.</span><span class="sxs-lookup"><span data-stu-id="09291-109">The Criteria pane contains a spreadsheet-like grid in which you specify options, such as which data columns to display, what rows to select, how to group rows, and so on.</span></span> <span data-ttu-id="09291-110">Per altre informazioni, vedere [Riquadro Criteri &#40;Visual Database Tools&#41;](criteria-pane-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="09291-110">For more information, see [Criteria Pane &#40;Visual Database Tools&#41;](criteria-pane-visual-database-tools.md).</span></span>  
  
-   <span data-ttu-id="09291-111">Il riquadro SQL riporta l'istruzione SQL della query o della vista.</span><span class="sxs-lookup"><span data-stu-id="09291-111">The SQL pane displays the SQL statement for the query or view.</span></span> <span data-ttu-id="09291-112">È possibile modificare l'istruzione SQL creata da Progettazione query oppure immettere un'istruzione SQL personalizzata.</span><span class="sxs-lookup"><span data-stu-id="09291-112">You can edit the SQL statement created by the Designer or you can enter your own SQL statement.</span></span> <span data-ttu-id="09291-113">Questo riquadro risulta particolarmente utile per l'immissione di istruzioni SQL che non è possibile creare con i riquadri Diagramma e Criteri, come nel caso delle query di unione.</span><span class="sxs-lookup"><span data-stu-id="09291-113">It is particularly useful for entering SQL statements that cannot be created using the Diagram and Criteria panes, such as union queries.</span></span> <span data-ttu-id="09291-114">Per altre informazioni, vedere [Riquadro SQL &#40;Visual Database Tools&#41;](sql-pane-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="09291-114">For more information, see [SQL Pane &#40;Visual Database Tools&#41;](sql-pane-visual-database-tools.md).</span></span>  
  
-   <span data-ttu-id="09291-115">Il riquadro Risultati visualizza una griglia contenente i dati recuperati dalla query o dalla vista.</span><span class="sxs-lookup"><span data-stu-id="09291-115">The Results pane shows a grid with data retrieved by the query or view.</span></span> <span data-ttu-id="09291-116">In Progettazione query e Progettazione viste questo riquadro visualizza i risultati dell'ultima query SELECT eseguita.</span><span class="sxs-lookup"><span data-stu-id="09291-116">In the Query and View Designer, the pane shows the results of the most recently executed SELECT query.</span></span> <span data-ttu-id="09291-117">È possibile modificare il database cambiando i valori nelle celle della griglia e aggiungere o eliminare righe.</span><span class="sxs-lookup"><span data-stu-id="09291-117">You can modify the database by editing values in the cells of the grid, and you can add or delete rows.</span></span> <span data-ttu-id="09291-118">Per altre informazioni, vedere [Riquadro Risultati &#40;Visual Database Tools&#41;](results-pane-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="09291-118">For more information, see [Results Pane &#40;Visual Database Tools&#41;](results-pane-visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="09291-119">Le query o le viste possono essere create in qualsiasi riquadro: è possibile specificare una colonna da visualizzare scegliendola nel riquadro Diagramma, immettendola nel riquadro Criteri o inserendola nell'istruzione SQL del riquadro SQL.</span><span class="sxs-lookup"><span data-stu-id="09291-119">You can create a query or view by working in any of the panes: you can specify a column to display by choosing it in the Diagram pane, entering it into the Criteria pane, or making it part of the SQL statement in the SQL pane.</span></span>  
  
## <a name="displaying-and-hiding-panes"></a><span data-ttu-id="09291-120">Visualizzare e nascondere riquadri</span><span class="sxs-lookup"><span data-stu-id="09291-120">Displaying and Hiding Panes</span></span>  
 <span data-ttu-id="09291-121">Per nascondere un riquadro o visualizzarne uno non visibile, fare clic con il pulsante destro del mouse nell'area di progettazione, scegliere **Riquadro**e fare clic sul nome del riquadro.</span><span class="sxs-lookup"><span data-stu-id="09291-121">To hide a pane or display a pane that is not visible, right-click the design surface, point to **Pane**, and then click the name of the pane.</span></span> <span data-ttu-id="09291-122">Se Progettazione query e Progettazione viste è aperto in modalità Progettazione query, il riquadro **Risultati** non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="09291-122">If the Query and View Designer is opened in Query Designer mode, the **Results** pane is not available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09291-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="09291-123">See Also</span></span>  
 <span data-ttu-id="09291-124">[Procedure per la progettazione di query e viste &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="09291-124">[Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span></span>  
 <span data-ttu-id="09291-125">[Aprire Progettazione query e Progettazione viste &#40;Visual Database Tools&#41;](open-the-query-and-view-designer-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="09291-125">[Open the Query and View Designer &#40;Visual Database Tools&#41;](open-the-query-and-view-designer-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="09291-126">Editor SQL &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="09291-126">SQL Editor &#40;Visual Database Tools&#41;</span></span>](sql-editor-visual-database-tools.md)  
  
  
