---
title: Rimuovere join (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- removing joins
- joins [SQL Server], removing
- deleting joins
ms.assetid: ccc212a1-fd13-48d6-85e5-5ff310c34bbd
author: stevestein
ms.author: sstein
ms.openlocfilehash: b037e317b629671f6ec5ea1fa90edfca6fafa627
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622981"
---
# <a name="remove-joins-visual-database-tools"></a><span data-ttu-id="49a5f-102">Rimozione di join (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="49a5f-102">Remove Joins (Visual Database Tools)</span></span>
  <span data-ttu-id="49a5f-103">Se non si desidera che le tabelle siano unite in join mediante un inner join o un outer join, sarà possibile rimuovere il join che le unisce.</span><span class="sxs-lookup"><span data-stu-id="49a5f-103">If you do not want tables to be joined via an inner join or an outer join, you can remove the join between them.</span></span> <span data-ttu-id="49a5f-104">È ad esempio possibile rimuovere un join tra due tabelle creato automaticamente da [Progettazione query e Progettazione viste](visual-database-tools.md) .</span><span class="sxs-lookup"><span data-stu-id="49a5f-104">For example, you might remove a join that the [Query and View Designer](visual-database-tools.md) has been created automatically between two tables.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="49a5f-105">La rimozione di un join da una query non modifica la relazione sottostante nel database.</span><span class="sxs-lookup"><span data-stu-id="49a5f-105">Removing a join from a query does not alter the underlying relationship in the database.</span></span>  
  
 <span data-ttu-id="49a5f-106">Se le due tabelle in join fanno parte di una query e si rimuovono tutte le condizioni di join tra di esse, la query risultante diventerà il prodotto di entrambe le tabelle. In altre parole, si trasformerà in un CROSS JOIN.</span><span class="sxs-lookup"><span data-stu-id="49a5f-106">If two joined tables are part of your query and you remove all join conditions between them, the resulting query becomes the product of both tables - that is, it becomes a CROSS JOIN.</span></span>  
  
### <a name="to-remove-a-join"></a><span data-ttu-id="49a5f-107">Per rimuovere un join</span><span class="sxs-lookup"><span data-stu-id="49a5f-107">To remove a join</span></span>  
  
-   <span data-ttu-id="49a5f-108">Nel [riquadro Diagramma](diagram-pane-visual-database-tools.md)selezionare la linea relativa al join da rimuovere, quindi premere CANC.</span><span class="sxs-lookup"><span data-stu-id="49a5f-108">In the [Diagram pane](diagram-pane-visual-database-tools.md), select the join line for the join to remove, and then press the DELETE key.</span></span> <span data-ttu-id="49a5f-109">È possibile selezionare e rimuovere più linee di join contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="49a5f-109">You can select and delete multiple join lines at one time.</span></span>  
  
 <span data-ttu-id="49a5f-110">In Progettazione query e Progettazione viste verrà rimossa la linea di join e modificata l'istruzione nel [riquadro SQL](sql-pane-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="49a5f-110">The Query and View Designer removes the join line and alters the statement in the [SQL pane](sql-pane-visual-database-tools.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49a5f-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="49a5f-111">See Also</span></span>  
 <span data-ttu-id="49a5f-112">[Unire tabelle in modo automatico &#40;Visual Database Tools&#41;](join-tables-automatically-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="49a5f-112">[Join Tables Automatically &#40;Visual Database Tools&#41;](join-tables-automatically-visual-database-tools.md) </span></span>  
 <span data-ttu-id="49a5f-113">[Unione di tabelle manualmente &#40;Visual Database Tools&#41;](join-tables-manually-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="49a5f-113">[Join Tables Manually &#40;Visual Database Tools&#41;](join-tables-manually-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="49a5f-114">Eseguire query con join &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="49a5f-114">Query with Joins &#40;Visual Database Tools&#41;</span></span>](query-with-joins-visual-database-tools.md)  
  
  
