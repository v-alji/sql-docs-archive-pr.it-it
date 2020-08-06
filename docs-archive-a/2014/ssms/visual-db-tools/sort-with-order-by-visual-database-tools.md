---
title: Ordinare con ORDER BY (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- ORDER BY clause [Visual Database Tools]
ms.assetid: 459f5640-8058-4c24-97e7-7bbd6168bc39
author: stevestein
ms.author: sstein
ms.openlocfilehash: 93bdb9ed01c7935c5b9dae543804fca758a9262d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722136"
---
# <a name="sort-with-order-by-visual-database-tools"></a><span data-ttu-id="6f5f5-102">Ordinamento tramite la clausola ORDER BY (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="6f5f5-102">Sort with ORDER BY (Visual Database Tools)</span></span>
  <span data-ttu-id="6f5f5-103">Utilizzando la clausola ORDER BY è possibile ordinare i risultati delle query in base a una o più colonne delle righe restituite.</span><span class="sxs-lookup"><span data-stu-id="6f5f5-103">You can sort query results by one or more of the columns in the returned rows by using an ORDER BY clause.</span></span> <span data-ttu-id="6f5f5-104">Per definire una clausola ORDER BY, scegliere le opzioni desiderate nel riquadro Criteri.</span><span class="sxs-lookup"><span data-stu-id="6f5f5-104">You can define an ORDER BY clause by choosing options in the Criteria Details pane.</span></span>  
  
### <a name="to-sort-a-query-using-an-order-by-clause"></a><span data-ttu-id="6f5f5-105">Per ordinare una query utilizzando una clausola ORDER BY</span><span class="sxs-lookup"><span data-stu-id="6f5f5-105">To sort a query using an ORDER BY clause</span></span>  
  
1.  <span data-ttu-id="6f5f5-106">Aprire una query esistente o crearne una nuova.</span><span class="sxs-lookup"><span data-stu-id="6f5f5-106">Open a query or create a new one.</span></span>  
  
2.  <span data-ttu-id="6f5f5-107">Nel [riquadro Criteri](visual-database-tools.md)fare clic sulla colonna **Tipo di ordinamento** della riga corrispondente alla colonna da usare per ordinare i risultati della query.</span><span class="sxs-lookup"><span data-stu-id="6f5f5-107">In the [Criteria Pane](visual-database-tools.md), click the **Sort Type** column for the row corresponding to the column that you want to use to sort your query results.</span></span>  
  
3.  <span data-ttu-id="6f5f5-108">Scegliere *Crescente* o *Decrescente* dall'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="6f5f5-108">Choose *Ascending* or *Descending* from the drop-down list.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6f5f5-109">Se si deseleziona la voce **Tipo di ordinamento** per una colonna, la colonna verrà rimossa dalla clausola ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="6f5f5-109">Clearing the **Sort Type** entry for a column removes that column from the ORDER BY clause.</span></span>  
  
 <span data-ttu-id="6f5f5-110">Quando si utilizza il riquadro Criteri, la clausola UNION della query cambia in base alle azioni più recenti.</span><span class="sxs-lookup"><span data-stu-id="6f5f5-110">Notice that as you work in the Criteria pane, your query's UNION clause changes to match your most recent actions.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6f5f5-111">Per ordinare i risultati in base a più colonne, usare la colonna **Ordinamento** per specificare l'ordine in cui deve essere effettuata la ricerca nelle diverse colonne.</span><span class="sxs-lookup"><span data-stu-id="6f5f5-111">When sorting results by more than one column, specify the order in which columns are searched relative to each other by using the **Sort Order** column.</span></span> <span data-ttu-id="6f5f5-112">Per altre informazioni, vedere **Procedura: Ordinare più colonne nelle query**.</span><span class="sxs-lookup"><span data-stu-id="6f5f5-112">For more information, see **How to: Sort Multiple Columns in Queries**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f5f5-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6f5f5-113">See Also</span></span>  
 <span data-ttu-id="6f5f5-114">[Ordinare e raggruppare i risultati delle query &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="6f5f5-114">[Sort and Group Query Results &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span></span>  
 <span data-ttu-id="6f5f5-115">[Riepilogare i risultati delle query &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="6f5f5-115">[Summarize Query Results &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="6f5f5-116">Procedure per la progettazione di query e viste &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="6f5f5-116">Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;</span></span>](design-queries-and-views-how-to-topics-visual-database-tools.md)  
  
  
