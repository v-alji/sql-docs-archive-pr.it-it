---
title: Creare query (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- queries [SQL Server], creating
ms.assetid: 696a080d-848f-44d3-a918-e29bafaab85a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 52392adff03b27e1c4c19f354bc62c350cccf17a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623705"
---
# <a name="create-queries-visual-database-tools"></a><span data-ttu-id="31bb4-102">Creazione di query (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="31bb4-102">Create Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="31bb4-103">Le query consentono di recuperare dati dalle tabelle e dalle viste del database.</span><span class="sxs-lookup"><span data-stu-id="31bb4-103">Queries allow you to retrieve data from the tables and views in your database.</span></span> <span data-ttu-id="31bb4-104">Le query vengono create e usate in **Progettazione query e Progettazione viste**, uno strumento che comprende quattro riquadri: il [riquadro Diagramma](visual-database-tools.md), il [riquadro SQL](sql-pane-visual-database-tools.md), il [riquadro Criteri Pane](criteria-pane-visual-database-tools.md)e il [riquadro Risultati](results-pane-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="31bb4-104">You create and work with queries in **Query and View Designer**, which is composed of four panes: the [Diagram Pane](visual-database-tools.md), the [SQL Pane](sql-pane-visual-database-tools.md), the [Criteria Pane](criteria-pane-visual-database-tools.md), and the [Results Pane](results-pane-visual-database-tools.md).</span></span>  
  
### <a name="to-create-a-new-query"></a><span data-ttu-id="31bb4-105">Per creare una nuova query</span><span class="sxs-lookup"><span data-stu-id="31bb4-105">To create a new query</span></span>  
  
1.  <span data-ttu-id="31bb4-106">In **Esplora oggetti**espandere il nodo **Tabelle** del database su cui si vuole eseguire la query.</span><span class="sxs-lookup"><span data-stu-id="31bb4-106">In **Object Explorer**, expand the **Tables** node for the database you want to query.</span></span> <span data-ttu-id="31bb4-107">Fare clic con il pulsante destro del mouse sulla tabella su cui si vuole eseguire la query e fare clic su **Apri tabella**.</span><span class="sxs-lookup"><span data-stu-id="31bb4-107">Right-click the table you want to query and click **Open Table**.</span></span>  
  
2.  <span data-ttu-id="31bb4-108">Per aggiungere altre tabelle alla query, selezionare **Aggiungi tabella**nel menu Progettazione query.</span><span class="sxs-lookup"><span data-stu-id="31bb4-108">To add more tables to the query, on the Query Designer menu, select **Add Table**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="31bb4-109">Se il riquadro **Diagramma**, **SQL**, **Criteri**o **Risultati** non è visibile, scegliere **Pannello** dal menu Progettazione query e fare clic sul riquadro da aprire.</span><span class="sxs-lookup"><span data-stu-id="31bb4-109">If you do not see the **Diagram**, **SQL**, **Criteria**, or **Results** panes, from the Query Designer menu, point to **Pane** and click the pane you want to open.</span></span>  
  
3.  <span data-ttu-id="31bb4-110">Nella finestra di dialogo **Aggiungi tabella** selezionare le tabelle su cui si vuole eseguire la query e fare clic su **Aggiungi** per ciascuna di esse.</span><span class="sxs-lookup"><span data-stu-id="31bb4-110">In the **Add Table** dialog box, select the tables you want to query and click **Add** for each one.</span></span>  
  
4.  <span data-ttu-id="31bb4-111">Dopo aver aggiunto tutte le tabelle su cui eseguire la query, fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="31bb4-111">Once you have added all the tables you want to query, click **Close**.</span></span>  
  
     <span data-ttu-id="31bb4-112">Per aggiungere altre tabelle in un secondo momento, fare clic con il pulsante destro del mouse sullo spazio vuoto nel riquadro **Diagramma** e scegliere **Aggiungi tabella**dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="31bb4-112">To add more tables later, right-click the open space in the **Diagram** pane and from the shortcut menu click **Add Table**.</span></span>  
  
5.  <span data-ttu-id="31bb4-113">Nel **riquadro Diagramma**selezionare, negli oggetti con valori di tabella, le caselle di ogni colonna su cui eseguire la query.</span><span class="sxs-lookup"><span data-stu-id="31bb4-113">In the **Diagram Pane**, check the boxes in the table-valued objects for each column you want to query.</span></span>  
  
6.  <span data-ttu-id="31bb4-114">Per eseguire la query, scegliere **Esegui SQL** dal menu Progettazione query.</span><span class="sxs-lookup"><span data-stu-id="31bb4-114">From the Query Designer menu, choose **Execute SQL** to run your query.</span></span>  
  
 <span data-ttu-id="31bb4-115">Per perfezionare la query, è possibile modificare il codice SQL nel **riquadro SQL** o specificare opzioni quali il criterio di ordinamento e gli alias delle colonne nel **riquadro Criteri**.</span><span class="sxs-lookup"><span data-stu-id="31bb4-115">To further refine your query, you can change the SQL code in the **SQL Pane** or choose options such as sort order and column aliases in the **Criteria Pane.**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31bb4-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="31bb4-116">See Also</span></span>  
 <span data-ttu-id="31bb4-117">[Salvataggio di query &#40;Visual Database Tools&#41;](save-queries-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="31bb4-117">[Save Queries &#40;Visual Database Tools&#41;](save-queries-visual-database-tools.md) </span></span>  
 <span data-ttu-id="31bb4-118">[Tipi di query &#40;Visual Database Tools&#41;](types-of-queries-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="31bb4-118">[Types of Queries &#40;Visual Database Tools&#41;](types-of-queries-visual-database-tools.md) </span></span>  
 <span data-ttu-id="31bb4-119">[Specificare i criteri di ricerca &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="31bb4-119">[Specify Search Criteria &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md) </span></span>  
 <span data-ttu-id="31bb4-120">[Riepilogare i risultati delle query &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="31bb4-120">[Summarize Query Results &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="31bb4-121">Eseguire operazioni di base con le query &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="31bb4-121">Perform Basic Operations with Queries &#40;Visual Database Tools&#41;</span></span>](perform-basic-operations-with-queries-visual-database-tools.md)  
  
  
