---
title: Grafici ad area (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 245b236d-1d55-4744-b752-80bd133502aa
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f401efa0abd5eac8ab39e511bc6b16a4f381ebdf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717501"
---
# <a name="area-charts-report-builder-and-ssrs"></a><span data-ttu-id="f8158-102">Grafici ad area (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="f8158-102">Area Charts (Report Builder and SSRS)</span></span>
  <span data-ttu-id="f8158-103">In un grafico ad area le serie vengono visualizzate come un set di punti collegati da una linea, con tutta l'area riempita sotto la linea.</span><span class="sxs-lookup"><span data-stu-id="f8158-103">An area chart displays a series as a set of points connected by a line, with all the area filled in below the line.</span></span> <span data-ttu-id="f8158-104">Per altre informazioni sull'aggiunta di dati a un grafico ad aree, vedere [Grafici &#40;Generatore report e SSRS&#41;](charts-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="f8158-104">For more information on how to add data to an area chart, see [Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="f8158-105">Nella figura seguente è illustrato un esempio di grafico ad area in pila.</span><span class="sxs-lookup"><span data-stu-id="f8158-105">The following illustration shows an example of a stacked area chart.</span></span> <span data-ttu-id="f8158-106">I dati sono particolarmente adatti per un grafico ad area in pila, in quanto è possibile visualizzare i totali per tutte le serie oltre alla percentuale di ogni serie rispetto al totale.</span><span class="sxs-lookup"><span data-stu-id="f8158-106">The data is well suited for display on a stacked area chart because the chart can display totals for all series as well as the proportion that each series contributes to the total.</span></span>  
  
 <span data-ttu-id="f8158-107">![Grafico ad area](../media/areachart.gif "Grafico ad area")</span><span class="sxs-lookup"><span data-stu-id="f8158-107">![Area chart](../media/areachart.gif "Area chart")</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="variations"></a><span data-ttu-id="f8158-108">Variazioni</span><span class="sxs-lookup"><span data-stu-id="f8158-108">Variations</span></span>  
  
-   <span data-ttu-id="f8158-109">**Area in pila**.</span><span class="sxs-lookup"><span data-stu-id="f8158-109">**Stacked area**.</span></span> <span data-ttu-id="f8158-110">Grafico ad area con più serie impilate in verticale.</span><span class="sxs-lookup"><span data-stu-id="f8158-110">An area chart where multiple series are stacked vertically.</span></span> <span data-ttu-id="f8158-111">Se il grafico contiene una sola serie, il grafico ad area in pila verrà visualizzato come grafico ad area.</span><span class="sxs-lookup"><span data-stu-id="f8158-111">If there is only one series in your chart, the stacked area chart will display the same as an area chart.</span></span>  
  
-   <span data-ttu-id="f8158-112">**Area in pila 100%** .</span><span class="sxs-lookup"><span data-stu-id="f8158-112">**Percent stacked area**.</span></span> <span data-ttu-id="f8158-113">Grafico ad area con più serie impilate in verticale per occupare l'intera area del grafico.</span><span class="sxs-lookup"><span data-stu-id="f8158-113">An area chart where multiple series are stacked vertically to fit the entire chart area.</span></span> <span data-ttu-id="f8158-114">Se il grafico contiene una sola serie, il grafico ad area in pila verrà visualizzato come grafico ad area.</span><span class="sxs-lookup"><span data-stu-id="f8158-114">If there is only one series in your chart, the stacked area chart will display the same as an area chart.</span></span>  
  
-   <span data-ttu-id="f8158-115">**Area smussata**.</span><span class="sxs-lookup"><span data-stu-id="f8158-115">**Smooth area**.</span></span> <span data-ttu-id="f8158-116">Grafico ad area in cui i punti dati sono collegati da una linea smussata anziché regolare.</span><span class="sxs-lookup"><span data-stu-id="f8158-116">An area chart where the data points are connected by a smooth line instead of a regular line.</span></span> <span data-ttu-id="f8158-117">Utilizzare un grafico ad area smussata anziché un grafico ad area se si preferisce che vengano visualizzate le tendenze piuttosto che i valori dei singoli punti dati.</span><span class="sxs-lookup"><span data-stu-id="f8158-117">Use a smooth area chart instead of an area chart when you are more concerned with displaying trends than with displaying the values of individual data points.</span></span>  
  
## <a name="data-considerations-for-area-charts"></a><span data-ttu-id="f8158-118">Considerazioni sui dati per i grafici ad area</span><span class="sxs-lookup"><span data-stu-id="f8158-118">Data Considerations for Area Charts</span></span>  
  
-   <span data-ttu-id="f8158-119">Insieme al grafico a linee, il grafico ad area è l'unico tipo di grafico in cui è possibile visualizzare dati contigui.</span><span class="sxs-lookup"><span data-stu-id="f8158-119">Along with the line chart, the area chart is the only chart type that displays data contiguously.</span></span> <span data-ttu-id="f8158-120">Per questo motivo, il grafico ad area viene utilizzato principalmente per rappresentare dati che si verificano nell'arco di un periodo continuo di tempo.</span><span class="sxs-lookup"><span data-stu-id="f8158-120">For this reason, an area chart is commonly used to represent data that occurs over a continuous period of time.</span></span>  
  
-   <span data-ttu-id="f8158-121">Un grafico ad area in pila 100% risulta utile per indicare dati percentuali che si verificano nel corso del tempo.</span><span class="sxs-lookup"><span data-stu-id="f8158-121">A percent stacked area chart is useful for showing proportional data that occurs over time.</span></span>  
  
-   <span data-ttu-id="f8158-122">Se il grafico contiene una sola serie, il grafico ad area in pila verrà disegnato come grafico ad area.</span><span class="sxs-lookup"><span data-stu-id="f8158-122">If there is only one series, a stacked area chart will be drawn as an area chart.</span></span>  
  
-   <span data-ttu-id="f8158-123">Se in un grafico ad area semplice i valori di più serie sono simili, è possibile che le aree si sovrappongano, nascondendo importanti valori di punti dati.</span><span class="sxs-lookup"><span data-stu-id="f8158-123">In a plain area chart, if the values in multiple series are similar, the areas may overlap, obscuring important data point values.</span></span> <span data-ttu-id="f8158-124">Per risolvere questo problema, utilizzare un grafico ad area in pila, progettato per mostrare più serie in un grafico ad area.</span><span class="sxs-lookup"><span data-stu-id="f8158-124">You can resolve this issue by changing the chart type to a stacked area chart, which is designed to show multiple series on an area chart.</span></span>  
  
-   <span data-ttu-id="f8158-125">Se il grafico ad area in pila contiene gap, è possibile che il set di dati includa valori vuoti, che verranno visualizzati come sezione vuota nel grafico.</span><span class="sxs-lookup"><span data-stu-id="f8158-125">If your stacked area chart contains gaps, it is possible that your dataset includes empty values, which will be shown as a vacant section on a stacked area chart.</span></span> <span data-ttu-id="f8158-126">Se il set di dati contiene valori vuoti, è consigliabile inserire punti vuoti nel grafico.</span><span class="sxs-lookup"><span data-stu-id="f8158-126">If your dataset includes empty values, consider inserting empty points on the chart.</span></span> <span data-ttu-id="f8158-127">In questo modo, le aree vuote del grafico verranno riempite con un colore diverso per indicare valori Null o zero.</span><span class="sxs-lookup"><span data-stu-id="f8158-127">Adding empty points will fill in the empty areas on the chart with a different color to indicate null or zero values.</span></span> <span data-ttu-id="f8158-128">Per ulteriori informazioni, vedere [aggiungere punti vuoti al grafico &#40;Generatore report e SSRS&#41;](add-empty-points-to-a-chart-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="f8158-128">For more information, see [Add Empty Points to the Chart &#40;Report Builder and SSRS&#41;](add-empty-points-to-a-chart-report-builder-and-ssrs.md).</span></span>  
  
-   <span data-ttu-id="f8158-129">Il comportamento dei tipi di grafico ad area è molto simile a quello degli istogrammi e dei grafici a linee.</span><span class="sxs-lookup"><span data-stu-id="f8158-129">Area chart types are very similar to column and line charts in behavior.</span></span> <span data-ttu-id="f8158-130">Se si esegue un confronto tra più serie, è consigliabile utilizzare un istogramma.</span><span class="sxs-lookup"><span data-stu-id="f8158-130">If you are making a comparison between multiple series, consider using a column chart instead.</span></span> <span data-ttu-id="f8158-131">Se si analizzano tendenze in un periodo di tempo, è consigliabile utilizzare un grafico a linee.</span><span class="sxs-lookup"><span data-stu-id="f8158-131">If you are analyzing trends over a period of time, consider using a line chart.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8158-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f8158-132">See Also</span></span>  
 <span data-ttu-id="f8158-133">[Grafici &#40;Generatore report e SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f8158-133">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="f8158-134">[Tipi di grafico &#40;Generatore report e SSRS&#41;](chart-types-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f8158-134">[Chart Types &#40;Report Builder and SSRS&#41;](chart-types-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="f8158-135">[Grafici a linee &#40;Generatore report e SSRS&#41;](line-charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f8158-135">[Line Charts &#40;Report Builder and SSRS&#41;](line-charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="f8158-136">[Modificare un tipo di grafico &#40;Generatore report e SSRS&#41;](change-a-chart-type-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f8158-136">[Change a Chart Type &#40;Report Builder and SSRS&#41;](change-a-chart-type-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="f8158-137">Punti dati vuoti e Null nei grafici &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="f8158-137">Empty and Null Data Points in Charts &#40;Report Builder and SSRS&#41;</span></span>](empty-and-null-data-points-in-charts-report-builder-and-ssrs.md)  
  
  
