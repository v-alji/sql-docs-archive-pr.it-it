---
title: Riquadro SQL (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- Query Designer [SQL Server], SQL pane
- View Designer, SQL pane
- SQL pane [Visual Database Tools]
ms.assetid: dbabab18-0614-415b-a2ef-9bcd0d320d5c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3a87ec1d5517852fefb152e0ec7b3165fa32988b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711399"
---
# <a name="sql-pane-visual-database-tools"></a><span data-ttu-id="eb0e7-102">Riquadro SQL (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="eb0e7-102">SQL Pane (Visual Database Tools)</span></span>
  <span data-ttu-id="eb0e7-103">Utilizzando il riquadro SQL è possibile creare un'istruzione SQL personalizzata. Per creare un'istruzione, è anche possibile utilizzare i riquadri Criteri e Diagramma, ma in questo caso le istruzioni SQL verranno comunque create nel riquadro SQL.</span><span class="sxs-lookup"><span data-stu-id="eb0e7-103">You can use the SQL pane to create your own SQL statement, or you can use the Criteria pane and Diagram pane to create the statement, in which case the SQL statements will be created in the SQL pane.</span></span> <span data-ttu-id="eb0e7-104">Mentre si compila la query, il riquadro SQL viene aggiornato e riformattato automaticamente in modo da semplificarne la lettura.</span><span class="sxs-lookup"><span data-stu-id="eb0e7-104">As you build your query, the SQL pane automatically updates and reformats for easy readability.</span></span>  
  
 <span data-ttu-id="eb0e7-105">Per aprire il riquadro SQL, aprire innanzitutto Progettazione query e Progettazione viste (con un oggetto di database selezionato in Esplora server, scegliere **Nuova query** dal menu **Database**).</span><span class="sxs-lookup"><span data-stu-id="eb0e7-105">To open the SQL pane, first open Query and View Designer (with a database object selected in Server Explorer, from the **Database** menu, click **New Query**).</span></span> <span data-ttu-id="eb0e7-106">A questo punto, scegliere **Riquadro** dal menu **Progettazione query** e fare clic su **SQL**.</span><span class="sxs-lookup"><span data-stu-id="eb0e7-106">Then from the **Query Designer** menu point to **Pane** and click **SQL**.</span></span>  
  
 <span data-ttu-id="eb0e7-107">Nel riquadro SQL è possibile:</span><span class="sxs-lookup"><span data-stu-id="eb0e7-107">In the SQL pane you can:</span></span>  
  
-   <span data-ttu-id="eb0e7-108">Creare nuove query immettendo istruzioni SQL.</span><span class="sxs-lookup"><span data-stu-id="eb0e7-108">Create new queries by entering SQL statements.</span></span>  
  
-   <span data-ttu-id="eb0e7-109">Modificare l'istruzione SQL creata da Progettazione query e Progettazione viste in base alle impostazioni definite nei riquadri Diagramma e Criteri.</span><span class="sxs-lookup"><span data-stu-id="eb0e7-109">Modify the SQL statement created by the Query and View Designer based on settings you make in the Diagram and Criteria panes.</span></span>  
  
-   <span data-ttu-id="eb0e7-110">Immettere istruzioni che sfruttano caratteristiche specifiche del database utilizzato.</span><span class="sxs-lookup"><span data-stu-id="eb0e7-110">Enter statements that take advantage of features specific to the database you are using.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="eb0e7-111">È importante conoscere le regole che consentono di identificare gli oggetti di database nel database utilizzato.</span><span class="sxs-lookup"><span data-stu-id="eb0e7-111">Be sure you know the rules for identifying database objects in the database you are using.</span></span> <span data-ttu-id="eb0e7-112">Per informazioni dettagliate, vedere la documentazione relativa al sistema di gestione di database in uso.</span><span class="sxs-lookup"><span data-stu-id="eb0e7-112">For details, see the documentation for your database management system.</span></span>  
  
## <a name="statements-in-the-sql-pane"></a><span data-ttu-id="eb0e7-113">Istruzioni nel riquadro SQL</span><span class="sxs-lookup"><span data-stu-id="eb0e7-113">Statements in the SQL Pane</span></span>  
 <span data-ttu-id="eb0e7-114">È possibile modificare la query corrente direttamente nel riquadro SQL.</span><span class="sxs-lookup"><span data-stu-id="eb0e7-114">You can edit the current query directly in the SQL pane.</span></span> <span data-ttu-id="eb0e7-115">Quando ci si sposta in un altro riquadro, l'istruzione viene formattata automaticamente in Progettazione query e Progettazione viste, quindi i riquadri Diagramma e Criteri vengono modificati in base all'istruzione.</span><span class="sxs-lookup"><span data-stu-id="eb0e7-115">When you move to another pane, the Query and View Designer automatically formats your statement, and then changes the Diagram and Criteria panes to match your statement.</span></span>  
  
 <span data-ttu-id="eb0e7-116">Se l'istruzione non può essere rappresentata nei riquadri Diagramma e Criteri e se tali riquadri sono visibili, in Progettazione query e Progettazione viste verrà generato un errore e sarà possibile scegliere di procedere in due modi:</span><span class="sxs-lookup"><span data-stu-id="eb0e7-116">If your statement cannot be represented in the Diagram and Criteria panes, and if those panes are visible, Query and View Designer displays an error and then offers you two choices:</span></span>  
  
-   <span data-ttu-id="eb0e7-117">Ignorare il fatto che l'istruzione non può essere rappresentata nei riquadri Diagramma e Criteri.</span><span class="sxs-lookup"><span data-stu-id="eb0e7-117">Ignore that the statement can not be represented in the Diagram and Criteria panes.</span></span>  
  
-   <span data-ttu-id="eb0e7-118">Annullare la modifica che non può essere rappresentata e ripristinare la versione più recente dell'istruzione SQL.</span><span class="sxs-lookup"><span data-stu-id="eb0e7-118">Undo the change that can not be represented and revert to the most recent version of the SQL statement.</span></span>  
  
 <span data-ttu-id="eb0e7-119">Se si sceglie di ignorare il fatto che l'istruzione non può essere rappresentata nei riquadri Diagramma e Criteri, in Progettazione query e Progettazione viste gli altri riquadri saranno visualizzati con colori più sfumati in modo da indicare che non riflettono più il contenuto del riquadro SQL.</span><span class="sxs-lookup"><span data-stu-id="eb0e7-119">If you choose to ignore that the statement can not be represented in the Diagram and Criteria panes, the Query and View Designer dims the other panes to indicate that they no longer reflect the contents of the SQL pane.</span></span>  
  
 <span data-ttu-id="eb0e7-120">È possibile continuare a modificare l'istruzione ed eseguirla come qualsiasi istruzione SQL.</span><span class="sxs-lookup"><span data-stu-id="eb0e7-120">You can continue to edit the statement and execute it as you would any SQL statement.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="eb0e7-121">Se si immette un'istruzione SQL ma successivamente si apportano ulteriori modifiche alla query, cambiando i riquadri Diagramma e Criteri, l'istruzione SQL verrà ricompilata e visualizzata nuovamente in Progettazione query e Progettazione viste.</span><span class="sxs-lookup"><span data-stu-id="eb0e7-121">If you enter an SQL statement, but then make further changes to the query by changing the Diagram and Criteria panes, the Query and View Designer rebuilds and redisplays the SQL statement.</span></span> <span data-ttu-id="eb0e7-122">In alcuni casi, questa operazione ha come risultato un'istruzione SQL con una struttura diversa rispetto all'istruzione SQL immessa in origine (anche se i risultati generati sono gli stessi).</span><span class="sxs-lookup"><span data-stu-id="eb0e7-122">In some cases, this action results in an SQL statement that is constructed differently from the one you originally entered (though it will always yield the same results).</span></span> <span data-ttu-id="eb0e7-123">Questa differenza è particolarmente frequente quando si utilizzano condizioni di ricerca che richiedono numerose clausole collegate con operatori AND e OR.</span><span class="sxs-lookup"><span data-stu-id="eb0e7-123">This difference is particularly likely when you are working with search conditions that involve several clauses linked with AND and OR.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb0e7-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eb0e7-124">See Also</span></span>  
 <span data-ttu-id="eb0e7-125">[Creazione di query &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="eb0e7-125">[Create Queries &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 <span data-ttu-id="eb0e7-126">[Eseguire query &#40;Visual Database Tools&#41;](run-queries-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="eb0e7-126">[Run Queries &#40;Visual Database Tools&#41;](run-queries-visual-database-tools.md) </span></span>  
 <span data-ttu-id="eb0e7-127">[Procedure per la progettazione di query e viste &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="eb0e7-127">[Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span></span>  
 <span data-ttu-id="eb0e7-128">[Riquadro diagramma &#40;Visual Database Tools&#41;](diagram-pane-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="eb0e7-128">[Diagram Pane &#40;Visual Database Tools&#41;](diagram-pane-visual-database-tools.md) </span></span>  
 <span data-ttu-id="eb0e7-129">[Riquadro Criteri &#40;Visual Database Tools&#41;](criteria-pane-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="eb0e7-129">[Criteria Pane &#40;Visual Database Tools&#41;](criteria-pane-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="eb0e7-130">Riquadro Risultati &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="eb0e7-130">Results Pane &#40;Visual Database Tools&#41;</span></span>](results-pane-visual-database-tools.md)  
  
  
