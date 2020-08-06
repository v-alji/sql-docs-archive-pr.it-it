---
title: Specificare un'area del grafico per una serie (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10157"
- sql12.rtp.rptdesigner.chartareaproperties.alignment.f1
ms.assetid: dc3c365b-c263-402a-bf6f-c2a7081db073
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 483bc6d2fa4aa079c95e9dbd03e18c71d7b13abf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623777"
---
# <a name="specify-a-chart-area-for-a-series-report-builder-and-ssrs"></a><span data-ttu-id="c061a-102">Specificare un'area del grafico per una serie (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="c061a-102">Specify a Chart Area for a Series (Report Builder and SSRS)</span></span>
  <span data-ttu-id="c061a-103">Il grafico è il contenitore di livello superiore che include il bordo esterno, il titolo del grafico e la legenda.</span><span class="sxs-lookup"><span data-stu-id="c061a-103">The chart is the top-level container that includes the outer border, the chart title, and the legend.</span></span> <span data-ttu-id="c061a-104">Per impostazione predefinita, il grafico contiene una sola area predefinita.</span><span class="sxs-lookup"><span data-stu-id="c061a-104">By default, the chart contains one default chart area.</span></span> <span data-ttu-id="c061a-105">L'area del grafico non è visibile sulla superficie del grafico, ma è possibile considerarla come un contenitore che include solo le etichette e il titolo degli assi, nonché l'area tracciato di una o più serie.</span><span class="sxs-lookup"><span data-stu-id="c061a-105">The chart area is not visible on the chart surface, but you can think of the chart area as a container that encompasses only the axis labels, the axis title and the plotting area of one or more series.</span></span> <span data-ttu-id="c061a-106">Nell'illustrazione seguente viene mostrato il concetto di aree del grafico all'interno di un singolo grafico.</span><span class="sxs-lookup"><span data-stu-id="c061a-106">The following illustration shows the concept of chart areas within a single chart.</span></span>  
  
 <span data-ttu-id="c061a-107">![Diagramma di un'area del grafico](../media/chartareasdiagram.gif "Diagramma di un'area del grafico")</span><span class="sxs-lookup"><span data-stu-id="c061a-107">![Shows a diagram of a chart area](../media/chartareasdiagram.gif "Shows a diagram of a chart area")</span></span>  
  
 <span data-ttu-id="c061a-108">Per impostazione predefinita, tutte le serie vengono aggiunte all'area del grafico predefinita.</span><span class="sxs-lookup"><span data-stu-id="c061a-108">By default, all series are added to the default chart area.</span></span> <span data-ttu-id="c061a-109">Quando si utilizzano grafici ad area, a dispersione, a linee e istogrammi, qualsiasi combinazione di queste serie può essere visualizzata nella stessa area del grafico.</span><span class="sxs-lookup"><span data-stu-id="c061a-109">When using area, column, line, and scatter charts, any combination of these series can be displayed on the same chart area.</span></span> <span data-ttu-id="c061a-110">Se nella stessa area del grafico sono contenute diverse serie, la leggibilità del grafico risulterà ridotta.</span><span class="sxs-lookup"><span data-stu-id="c061a-110">If you have several series in the same chart area, the readability of the chart is reduced.</span></span> <span data-ttu-id="c061a-111">Potrebbe essere necessario separare i tipi di grafico in più aree del grafico</span><span class="sxs-lookup"><span data-stu-id="c061a-111">You may want to separate the chart types into multiple chart areas.</span></span> <span data-ttu-id="c061a-112">allo scopo di migliorare la leggibilità e semplificare il confronto.</span><span class="sxs-lookup"><span data-stu-id="c061a-112">Using multiple chart areas will increase readability for easier comparisons.</span></span> <span data-ttu-id="c061a-113">I grafici azionari relativi a prezzi e volumi, ad esempio, includono spesso intervalli di valori differenti. È tuttavia possibile confrontare dati che si riferiscono allo stesso periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="c061a-113">For example, price-volume stock charts often have different ranges of values, but comparisons can be made between the price and volume data over the same period of time.</span></span>  
  
 <span data-ttu-id="c061a-114">Le serie a barra, polare o con forme possono essere combinate solo con serie degli stessi tipi di grafico nella stessa area del grafico.</span><span class="sxs-lookup"><span data-stu-id="c061a-114">The bar, polar, or shape series can only be combined with series of the same chart types in the same chart area.</span></span> <span data-ttu-id="c061a-115">Se si utilizza un grafico polare o con forme, è consigliabile utilizzare un'area dati del grafico separata per ogni campo da visualizzare.</span><span class="sxs-lookup"><span data-stu-id="c061a-115">If you are using a Polar or Shape chart, consider using a separate chart data region for each field that you wish to show.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-associate-a-series-with-a-new-chart-area"></a><span data-ttu-id="c061a-116">Per associare una serie a una nuova area del grafico</span><span class="sxs-lookup"><span data-stu-id="c061a-116">To associate a series with a new chart area</span></span>  
  
1.  <span data-ttu-id="c061a-117">Fare clic con il pulsante destro del mouse in un punto qualsiasi del grafico e scegliere **Aggiungi nuova area grafico**.</span><span class="sxs-lookup"><span data-stu-id="c061a-117">Right-click anywhere on the chart and select **Add New Chart Area**.</span></span> <span data-ttu-id="c061a-118">Sul grafico verrà visualizzata una nuova area vuota.</span><span class="sxs-lookup"><span data-stu-id="c061a-118">A new, blank chart area appears on the chart.</span></span>  
  
2.  <span data-ttu-id="c061a-119">Fare clic con il pulsante destro del mouse sulla serie nel grafico o su un campo serie o dati nell'area appropriata del riquadro Dati grafico, quindi fare clic su **Proprietà serie**.</span><span class="sxs-lookup"><span data-stu-id="c061a-119">Right-click the series on the chart or right-click a series or data field in the appropriate area in the Chart Data pane, and then click **Series Properties**.</span></span>  
  
3.  <span data-ttu-id="c061a-120">In **Assi e area grafico**selezionare l'area del grafico in cui si desidera visualizzare la serie.</span><span class="sxs-lookup"><span data-stu-id="c061a-120">In **Axes and Chart Areas**, select the chart area that you want the series to be shown in.</span></span>  
  
4.  <span data-ttu-id="c061a-121">(Facoltativo) Allineare le aree del grafico in senso verticale.</span><span class="sxs-lookup"><span data-stu-id="c061a-121">(Optional) Align the chart areas vertically.</span></span> <span data-ttu-id="c061a-122">A questo scopo, fare clic con il pulsante destro del mouse sul grafico e scegliere **Proprietà area grafico**.</span><span class="sxs-lookup"><span data-stu-id="c061a-122">To do this, right-click the chart and select **Chart Area Properties**.</span></span> <span data-ttu-id="c061a-123">In **Allineamento**selezionare un'altra area del grafico con la quale si desidera allineare l'area del grafico selezionata.</span><span class="sxs-lookup"><span data-stu-id="c061a-123">In **Alignment**, select another chart area that you want to align the selected chart area with.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c061a-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c061a-124">See Also</span></span>  
 <span data-ttu-id="c061a-125">[Più serie in un grafico &#40;Generatore report e SSRS&#41;](multiple-series-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c061a-125">[Multiple Series on a Chart &#40;Report Builder and SSRS&#41;](multiple-series-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="c061a-126">[Formattazione dei punti dati di un grafico &#40;Generatore report e SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c061a-126">[Formatting Data Points on a Chart &#40;Report Builder and SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="c061a-127">[Definire i colori in un grafico mediante la tavolozza &#40;Generatore report e SSRS&#41;](define-colors-on-a-chart-using-a-palette-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c061a-127">[Define Colors on a Chart Using a Palette &#40;Report Builder and SSRS&#41;](define-colors-on-a-chart-using-a-palette-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="c061a-128">[Grafici polari &#40;Generatore report e SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c061a-128">[Polar Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="c061a-129">[Grafici con forme &#40;Generatore report e SSRS&#41;](shape-charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c061a-129">[Shape Charts &#40;Report Builder and SSRS&#41;](shape-charts-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="c061a-130">Grafici a torta &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="c061a-130">Pie Charts &#40;Report Builder and SSRS&#41;</span></span>](pie-charts-report-builder-and-ssrs.md)  
  
  
