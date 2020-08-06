---
title: Ordinare in modo crescente o decrescente (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- descending sorts
- ascending sorts
ms.assetid: d61cc55b-9ee8-4ecf-a32f-6459ae43910b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 67b5e6b00f62cfc297cc5930bc8cf3a41314a2f8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636992"
---
# <a name="sort-in-ascending-or-descending-order-visual-database-tools"></a><span data-ttu-id="1dfb7-102">Ordinamento in modo crescente o decrescente (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="1dfb7-102">Sort in Ascending or Descending Order (Visual Database Tools)</span></span>
  <span data-ttu-id="1dfb7-103">È possibile ordinare i risultati di una query in modo crescente o decrescente in base a una o più colonne del set di risultati utilizzando la parola chiave `ASC` o `DESC` con la clausola `ORDER BY`.</span><span class="sxs-lookup"><span data-stu-id="1dfb7-103">You can sort query results in ascending or descending order on one or more of the columns in the result set by using the `ASC` or `DESC` keywords with the `ORDER BY` clause.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1dfb7-104">Il criterio di ordinamento è determinato in parte dalla sequenza di confronto della colonna.</span><span class="sxs-lookup"><span data-stu-id="1dfb7-104">The sort order is determined in part by the column's collation sequence.</span></span> <span data-ttu-id="1dfb7-105">Per cambiare la sequenza di confronto, è possibile usare la [finestra di dialogo Regole di confronto](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="1dfb7-105">You can change the collation sequence in the [Collation Dialog Box](visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="1dfb7-106">Nella procedura riportata di seguito si presuppone che in Progettazione query e Progettazione viste sia aperta una query in cui viene utilizzata la clausola ORDER BY per ordinare una o più colonne.</span><span class="sxs-lookup"><span data-stu-id="1dfb7-106">The following procedure assumes that you have a query open in Query and View Designer that uses the ORDER BY clause to sort one or more columns.</span></span>  
  
### <a name="to-specify-or-change-the-order-in-which-results-are-sorted"></a><span data-ttu-id="1dfb7-107">Per impostare o cambiare il criterio di ordinamento dei risultati</span><span class="sxs-lookup"><span data-stu-id="1dfb7-107">To specify or change the order in which results are sorted</span></span>  
  
1.  <span data-ttu-id="1dfb7-108">Nel [riquadro Criteri](criteria-pane-visual-database-tools.md)fare clic sul campo **Tipo ordinamento** relativo alla colonna che si vuole riordinare.</span><span class="sxs-lookup"><span data-stu-id="1dfb7-108">In the [Criteria pane](criteria-pane-visual-database-tools.md), click the **Sort Type** field for the column that you want to reorder.</span></span>  
  
2.  <span data-ttu-id="1dfb7-109">Selezionare **Crescente** o **Decrescente** per specificare il criterio di ordinamento per la colonna.</span><span class="sxs-lookup"><span data-stu-id="1dfb7-109">Choose **Ascending** or **Descending** to specify the sort order for the column.</span></span>  
  
 <span data-ttu-id="1dfb7-110">Quando si utilizza il riquadro Criteri, la clausola UNION della query cambia in base alle azioni più recenti.</span><span class="sxs-lookup"><span data-stu-id="1dfb7-110">Notice that as you work in the Criteria pane, your query's UNION clause changes to match your most recent actions.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1dfb7-111">Per ordinare i risultati in base a più colonne, utilizzare la colonna Ordinamento per specificare l'ordine in cui deve essere effettuata la ricerca nelle diverse colonne.</span><span class="sxs-lookup"><span data-stu-id="1dfb7-111">When sorting results by more than one column, specify the order in which columns are searched relative to each other by using the Sort Order column.</span></span> <span data-ttu-id="1dfb7-112">Per altre informazioni, vedere [Ordinare più colonne nelle query &#40;Visual Database Tools&#41;](sort-multiple-columns-in-queries-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="1dfb7-112">For more information, see [Sort Multiple Columns in Queries &#40;Visual Database Tools&#41;](sort-multiple-columns-in-queries-visual-database-tools.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1dfb7-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1dfb7-113">See Also</span></span>  
 <span data-ttu-id="1dfb7-114">[Ordinare e raggruppare i risultati delle query &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="1dfb7-114">[Sort and Group Query Results &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span></span>  
 <span data-ttu-id="1dfb7-115">[Riepilogare i risultati delle query &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="1dfb7-115">[Summarize Query Results &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="1dfb7-116">Procedure per la progettazione di query e viste &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="1dfb7-116">Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;</span></span>](design-queries-and-views-how-to-topics-visual-database-tools.md)  
  
  
