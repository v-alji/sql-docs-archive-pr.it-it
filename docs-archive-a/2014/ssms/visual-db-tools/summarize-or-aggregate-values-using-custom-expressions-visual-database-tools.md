---
title: Riepilogare o aggregare valori mediante espressioni personalizzate (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- summarizing query results
- custom expressions to aggregate values [SQL Server]
ms.assetid: 34130ac1-0106-4766-b324-acb0b7bb6f6e
author: stevestein
ms.author: sstein
ms.openlocfilehash: b9f03f82842178a68c8a3d04ebc1bd738c0ab0b5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720723"
---
# <a name="summarize-or-aggregate-values-using-custom-expressions-visual-database-tools"></a><span data-ttu-id="b97e2-102">Riepilogo o aggregazione di valori mediante l'utilizzo di espressioni personalizzate (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="b97e2-102">Summarize or Aggregate Values Using Custom Expressions (Visual Database Tools)</span></span>
  <span data-ttu-id="b97e2-103">Oltre a utilizzare le funzioni di aggregazione per raggruppare i dati, è possibile creare espressioni personalizzate che producono valori aggregati.</span><span class="sxs-lookup"><span data-stu-id="b97e2-103">In addition to using aggregate functions to aggregate data, you can create custom expressions to produce aggregate values.</span></span> <span data-ttu-id="b97e2-104">È possibile utilizzare espressioni personalizzate al posto di funzioni di aggregazione in qualsiasi punto di una query di aggregazione.</span><span class="sxs-lookup"><span data-stu-id="b97e2-104">You can use custom expressions in place of aggregate functions anywhere in an aggregate query.</span></span>  
  
 <span data-ttu-id="b97e2-105">Si supponga ad esempio che nella tabella `titles` si desideri creare una query in cui sia riportato non solo il prezzo medio ma anche il prezzo medio dopo l'applicazione di uno sconto.</span><span class="sxs-lookup"><span data-stu-id="b97e2-105">For example, in the `titles` table you might want to create a query that shows not just the average price, but what the average price would be if it were discounted.</span></span>  
  
 <span data-ttu-id="b97e2-106">In questo caso non sarà possibile includere un'espressione basata su calcoli che coinvolgono solo singole righe della tabella; l'espressione dovrà essere basata su un valore aggregato in quanto al momento del calcolo dell'espressione sono disponibili solo i valori aggregati.</span><span class="sxs-lookup"><span data-stu-id="b97e2-106">You cannot include an expression that is based on calculations involving only individual rows in the table; the expression must be based on an aggregate value, because only the aggregate values are available at the time the expression is calculated.</span></span>  
  
### <a name="to-specify-a-custom-expression-for-a-summary-value"></a><span data-ttu-id="b97e2-107">Per specificare un'espressione personalizzata per un valore di riepilogo</span><span class="sxs-lookup"><span data-stu-id="b97e2-107">To specify a custom expression for a summary value</span></span>  
  
1.  <span data-ttu-id="b97e2-108">Specificare i gruppi per la query.</span><span class="sxs-lookup"><span data-stu-id="b97e2-108">Specify the groups for your query.</span></span> <span data-ttu-id="b97e2-109">Per informazioni dettagliate, vedere [Raggruppare righe nei risultati di una query &#40;Visual Database Tools&#41;](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="b97e2-109">For details, see [Group Rows in Query Results &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
2.  <span data-ttu-id="b97e2-110">Spostarsi su una riga vuota del riquadro Criteri e digitare l'espressione nella colonna **Columns**.</span><span class="sxs-lookup"><span data-stu-id="b97e2-110">Move to a blank row of the Criteria pane, and then type the expression in the **Columns** column.</span></span>  
  
     <span data-ttu-id="b97e2-111">In [Progettazione query e Progettazione viste](query-and-view-designer-tools-visual-database-tools.md) verrà assegnato automaticamente all'espressione un alias di colonna in modo da creare un'intestazione di colonna utile nell'output della query.</span><span class="sxs-lookup"><span data-stu-id="b97e2-111">The [Query and View Designer](query-and-view-designer-tools-visual-database-tools.md) automatically assigns a column alias to the expression to create a useful column heading in query output.</span></span> <span data-ttu-id="b97e2-112">Per altre informazioni dettagliate, vedere [Creazione di alias di colonna &#40;Visual Database Tools&#41;](create-column-aliases-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="b97e2-112">For more details, see [Create Column Aliases &#40;Visual Database Tools&#41;](create-column-aliases-visual-database-tools.md).</span></span>  
  
3.  <span data-ttu-id="b97e2-113">Nella colonna **Group By** per l'espressione selezionare **Espressione**.</span><span class="sxs-lookup"><span data-stu-id="b97e2-113">In the **Group By** column for the expression, select **Expression**.</span></span>  
  
4.  <span data-ttu-id="b97e2-114">Consente di eseguire la query.</span><span class="sxs-lookup"><span data-stu-id="b97e2-114">Run the query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b97e2-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b97e2-115">See Also</span></span>  
 <span data-ttu-id="b97e2-116">[Ordinare e raggruppare i risultati delle query &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="b97e2-116">[Sort and Group Query Results &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="b97e2-117">Creare un riepilogo dei risultati di query &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="b97e2-117">Summarize Query Results &#40;Visual Database Tools&#41;</span></span>](summarize-query-results-visual-database-tools.md)  
  
  
