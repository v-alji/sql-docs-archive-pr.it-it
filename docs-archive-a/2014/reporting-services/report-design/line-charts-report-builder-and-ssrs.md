---
title: Grafici a linee (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 194e6679-890d-4a3e-a756-130d32ef7e29
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 44e7a011186e66e6b8bdc8b5dd31939c883e320b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723408"
---
# <a name="line-charts-report-builder-and-ssrs"></a><span data-ttu-id="c4a3b-102">Grafici a linee (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="c4a3b-102">Line Charts (Report Builder and SSRS)</span></span>
  <span data-ttu-id="c4a3b-103">In un grafico a linee le serie vengono visualizzate come set di punti collegati da una singola linea.</span><span class="sxs-lookup"><span data-stu-id="c4a3b-103">A line chart displays a series as a set of points connected by a single line.</span></span> <span data-ttu-id="c4a3b-104">I grafici a linee vengono utilizzati per rappresentare grandi quantità di dati che si verificano nell'arco di un periodo di tempo continuo.</span><span class="sxs-lookup"><span data-stu-id="c4a3b-104">Line charts are used to representing large amounts of data that occur over a continuous period of time.</span></span> <span data-ttu-id="c4a3b-105">Per altre informazioni sull'aggiunta di dati a un grafico a linee, vedere [Grafici &#40;Generatore report e SSRS&#41;](charts-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="c4a3b-105">For more information about how to add data to a line chart, see [Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="c4a3b-106">Nella figura seguente è illustrato un grafico a linee contenente tre serie.</span><span class="sxs-lookup"><span data-stu-id="c4a3b-106">The following illustration shows a line chart that contains three series.</span></span>  
  
 <span data-ttu-id="c4a3b-107">![Grafico a linee](../media/rs-linechart.gif "Grafico a linee")</span><span class="sxs-lookup"><span data-stu-id="c4a3b-107">![Line chart](../media/rs-linechart.gif "Line chart")</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="variations"></a><span data-ttu-id="c4a3b-108">Variazioni</span><span class="sxs-lookup"><span data-stu-id="c4a3b-108">Variations</span></span>  
  
-   <span data-ttu-id="c4a3b-109">**Linee smussate**.</span><span class="sxs-lookup"><span data-stu-id="c4a3b-109">**Smooth line**.</span></span> <span data-ttu-id="c4a3b-110">Grafico a linee in cui viene utilizzata una linea curva anziché regolare.</span><span class="sxs-lookup"><span data-stu-id="c4a3b-110">A line chart that uses a curved line instead of a regular line.</span></span>  
  
-   <span data-ttu-id="c4a3b-111">**Linee con rientri**.</span><span class="sxs-lookup"><span data-stu-id="c4a3b-111">**Stepped line**.</span></span> <span data-ttu-id="c4a3b-112">Grafico a linee in cui viene utilizzata una linea con rientri anziché regolare.</span><span class="sxs-lookup"><span data-stu-id="c4a3b-112">A line chart that uses a stepped line instead of a regular line.</span></span> <span data-ttu-id="c4a3b-113">I punti vengono collegati tramite una linea in modo simile ai gradini di una scala.</span><span class="sxs-lookup"><span data-stu-id="c4a3b-113">The stepped line connects points by using a line that makes it look like steps on a ladder or staircase.</span></span>  
  
-   <span data-ttu-id="c4a3b-114">**Grafici sparkline**.</span><span class="sxs-lookup"><span data-stu-id="c4a3b-114">**Sparkline charts**.</span></span> <span data-ttu-id="c4a3b-115">Le variazioni del grafico a linee in cui viene visualizzata solo la serie di linee nella cella di una tabella o matrice.</span><span class="sxs-lookup"><span data-stu-id="c4a3b-115">Variations of the line chart that show only the line series in the cell of a table or matrix.</span></span> <span data-ttu-id="c4a3b-116">Per altre informazioni, vedere [Grafici sparkline e barre dei dati &#40;Generatore report e SSRS&#41;](sparklines-and-data-bars-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="c4a3b-116">For more information, see [Sparklines and Data Bars &#40;Report Builder and SSRS&#41;](sparklines-and-data-bars-report-builder-and-ssrs.md).</span></span>  
  
## <a name="data-considerations-for-line-charts"></a><span data-ttu-id="c4a3b-117">Considerazioni sui dati per i grafici a linee</span><span class="sxs-lookup"><span data-stu-id="c4a3b-117">Data Considerations for Line Charts</span></span>  
  
-   <span data-ttu-id="c4a3b-118">Per migliorare l'impatto visivo del grafico a linee predefinito, impostare lo spessore del bordo della serie su 3 e aggiungere un offset dell'ombreggiatura pari a 1.</span><span class="sxs-lookup"><span data-stu-id="c4a3b-118">To improve the visual impact of the default line chart, consider changing the width of the series border to 3, and adding a shadow offset of 1.</span></span> <span data-ttu-id="c4a3b-119">In questo modo verrà creato un grafico a linee più spesse.</span><span class="sxs-lookup"><span data-stu-id="c4a3b-119">This will create a much bolder line chart.</span></span> <span data-ttu-id="c4a3b-120">Se si sceglie un altro tipo di grafico, sarà necessario ripristinare i valori originali di queste proprietà.</span><span class="sxs-lookup"><span data-stu-id="c4a3b-120">You will need to revert these properties to their original values if you change the chart type from Line to another type.</span></span>  
  
-   <span data-ttu-id="c4a3b-121">Se il set di dati include valori vuoti, nel grafico a linee verranno aggiunti punti vuoti sotto forma di linee segnalibro per mantenere la continuità nel grafico.</span><span class="sxs-lookup"><span data-stu-id="c4a3b-121">If your dataset includes empty values, the line chart will add empty points, in the form of placeholder lines, in order to maintain continuity on the chart.</span></span> <span data-ttu-id="c4a3b-122">Se non si desidera visualizzare tali linee, utilizzare un tipo di grafico non contiguo per rappresentare il set di dati, ad esempio un grafico a barre o un istogramma.</span><span class="sxs-lookup"><span data-stu-id="c4a3b-122">If you would rather not see these lines, consider displaying your dataset using a non-contiguous chart type such as a bar or column chart.</span></span>  
  
-   <span data-ttu-id="c4a3b-123">Un grafico a linee richiede almeno due punti per disegnare una linea.</span><span class="sxs-lookup"><span data-stu-id="c4a3b-123">A line chart requires at least two points to draw a line.</span></span>  <span data-ttu-id="c4a3b-124">Se il set di dati contiene un unico punto dati, il grafico a linee verrà visualizzato come marcatore di un singolo punto dati.</span><span class="sxs-lookup"><span data-stu-id="c4a3b-124">If your dataset has only one data point, the line chart will display as a single data point marker.</span></span>  
  
-   <span data-ttu-id="c4a3b-125">Una serie disegnata come linea non occupa molto spazio all'interno di un'area del grafico.</span><span class="sxs-lookup"><span data-stu-id="c4a3b-125">A series that is drawn as a line will not take up much space within a chart area.</span></span>  <span data-ttu-id="c4a3b-126">Per questo motivo, i grafici a linee vengono spesso combinati con altri tipi di grafico, ad esempio istogrammi.</span><span class="sxs-lookup"><span data-stu-id="c4a3b-126">For this reason, line charts are frequently combined with other chart types such as column charts.</span></span> <span data-ttu-id="c4a3b-127">Tuttavia, non è possibile combinare un grafico a linee con i tipo di grafico a barre, polare, a torta o con forme.</span><span class="sxs-lookup"><span data-stu-id="c4a3b-127">However, you cannot combine a line chart with bar, polar, pie or shape chart types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4a3b-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c4a3b-128">See Also</span></span>  
 <span data-ttu-id="c4a3b-129">[Grafici a barre &#40;Generatore report e SSRS&#41;](bar-charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c4a3b-129">[Bar Charts &#40;Report Builder and SSRS&#41;](bar-charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="c4a3b-130">[Istogrammi &#40;Generatore report e SSRS&#41;](column-charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c4a3b-130">[Column Charts &#40;Report Builder and SSRS&#41;](column-charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="c4a3b-131">[Grafici &#40;Generatore report e SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c4a3b-131">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="c4a3b-132">[Tipi di grafico &#40;Generatore report e SSRS&#41;](chart-types-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c4a3b-132">[Chart Types &#40;Report Builder and SSRS&#41;](chart-types-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="c4a3b-133">[Grafici ad aree &#40;Generatore report e SSRS&#41;](area-charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c4a3b-133">[Area Charts &#40;Report Builder and SSRS&#41;](area-charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="c4a3b-134">[Punti dati vuoti e Null nei grafici &#40;Generatore report e SSRS&#41;](empty-and-null-data-points-in-charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c4a3b-134">[Empty and Null Data Points in Charts &#40;Report Builder and SSRS&#41;](empty-and-null-data-points-in-charts-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="c4a3b-135">Grafici &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="c4a3b-135">Charts &#40;Report Builder and SSRS&#41;</span></span>](charts-report-builder-and-ssrs.md)  
  
  
