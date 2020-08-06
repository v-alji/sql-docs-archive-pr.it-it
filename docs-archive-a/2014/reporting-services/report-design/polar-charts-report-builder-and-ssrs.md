---
title: Grafici polari (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: c9402d8f-202a-4cdf-949e-50f5b1d2b885
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b8c4dd9394fab3e076c4a714375954a616e081f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711615"
---
# <a name="polar-charts-report-builder-and-ssrs"></a><span data-ttu-id="ff857-102">Grafici polari (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="ff857-102">Polar Charts (Report Builder and SSRS)</span></span>
  <span data-ttu-id="ff857-103">In un grafico polare le serie vengono visualizzate come set di punti raggruppati per categoria in un cerchio di 360 gradi.</span><span class="sxs-lookup"><span data-stu-id="ff857-103">A polar chart displays a series as a set of points that are grouped by category on a 360-degree circle.</span></span> <span data-ttu-id="ff857-104">I valori sono rappresentati dalla lunghezza del punto, in base alla misurazione dal centro del cerchio.</span><span class="sxs-lookup"><span data-stu-id="ff857-104">Values are represented by the length of the point as measured from the center of the circle.</span></span> <span data-ttu-id="ff857-105">A una distanza maggiore del punto dal centro corrisponde un valore maggiore.</span><span class="sxs-lookup"><span data-stu-id="ff857-105">The farther the point is from the center, the greater its value.</span></span> <span data-ttu-id="ff857-106">Le etichette delle categorie vengono visualizzate sul perimetro del grafico.</span><span class="sxs-lookup"><span data-stu-id="ff857-106">Category labels are displayed on the perimeter of the chart.</span></span> <span data-ttu-id="ff857-107">Per altre informazioni sull'aggiunta di dati a un grafico polare, vedere [Grafici &#40;Generatore report e SSRS&#41;](charts-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="ff857-107">For more information on how to add data to a polar chart, see [Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="variations"></a><span data-ttu-id="ff857-108">Variazioni</span><span class="sxs-lookup"><span data-stu-id="ff857-108">Variations</span></span>  
  
-   <span data-ttu-id="ff857-109">**Grafico radar**.</span><span class="sxs-lookup"><span data-stu-id="ff857-109">**Radar chart**.</span></span> <span data-ttu-id="ff857-110">In un grafico radar le serie vengono visualizzate come linee o aree circolari.</span><span class="sxs-lookup"><span data-stu-id="ff857-110">A radar chart displays a series as a circular line or area.</span></span> <span data-ttu-id="ff857-111">A differenza del grafico polare, nel grafico radar i dati non vengono visualizzati in termini di coordinate polari.</span><span class="sxs-lookup"><span data-stu-id="ff857-111">Unlike the polar chart, the radar chart does not display data in terms of polar coordinates.</span></span>  
  
## <a name="data-considerations-for-polar-charts"></a><span data-ttu-id="ff857-112">Considerazioni sui dati per i grafici polari</span><span class="sxs-lookup"><span data-stu-id="ff857-112">Data Considerations for Polar Charts</span></span>  
  
-   <span data-ttu-id="ff857-113">Il grafico radar risulta utile per i confronti tra più serie di dati di categoria.</span><span class="sxs-lookup"><span data-stu-id="ff857-113">The radar chart is useful for comparisons between multiple series of category data.</span></span>  
  
-   <span data-ttu-id="ff857-114">I grafici polari vengono utilizzati principalmente per tracciare dati polari, in cui ogni punto dati è determinato da un angolo e da una distanza.</span><span class="sxs-lookup"><span data-stu-id="ff857-114">Polar charts are most commonly used to graph polar data, where each data point is determined by an angle and a distance.</span></span>  
  
-   <span data-ttu-id="ff857-115">I grafici polari non possono essere combinati con altri tipi di grafico nella stessa area del grafico.</span><span class="sxs-lookup"><span data-stu-id="ff857-115">Polar charts cannot be combined with any other chart type in the same chart area.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ff857-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="ff857-116">Example</span></span>  
 <span data-ttu-id="ff857-117">Nell'esempio seguente è illustrato il possibile utilizzo di un grafico radar.</span><span class="sxs-lookup"><span data-stu-id="ff857-117">The following example shows how a radar chart can be used.</span></span> <span data-ttu-id="ff857-118">Nella tabella sono forniti i dati di esempio per il grafico.</span><span class="sxs-lookup"><span data-stu-id="ff857-118">The table below provides sample data for the chart.</span></span>  
  
|<span data-ttu-id="ff857-119">Nome</span><span class="sxs-lookup"><span data-stu-id="ff857-119">Name</span></span>|<span data-ttu-id="ff857-120">Sales</span><span class="sxs-lookup"><span data-stu-id="ff857-120">Sales</span></span>|  
|----------|-----------|  
|<span data-ttu-id="ff857-121">Shrubs</span><span class="sxs-lookup"><span data-stu-id="ff857-121">Shrubs</span></span>|<span data-ttu-id="ff857-122">61</span><span class="sxs-lookup"><span data-stu-id="ff857-122">61</span></span>|  
|<span data-ttu-id="ff857-123">Seeds</span><span class="sxs-lookup"><span data-stu-id="ff857-123">Seeds</span></span>|<span data-ttu-id="ff857-124">78</span><span class="sxs-lookup"><span data-stu-id="ff857-124">78</span></span>|  
|<span data-ttu-id="ff857-125">Bulbs</span><span class="sxs-lookup"><span data-stu-id="ff857-125">Bulbs</span></span>|<span data-ttu-id="ff857-126">60</span><span class="sxs-lookup"><span data-stu-id="ff857-126">60</span></span>|  
|<span data-ttu-id="ff857-127">Trees</span><span class="sxs-lookup"><span data-stu-id="ff857-127">Trees</span></span>|<span data-ttu-id="ff857-128">38</span><span class="sxs-lookup"><span data-stu-id="ff857-128">38</span></span>|  
|<span data-ttu-id="ff857-129">Flowers</span><span class="sxs-lookup"><span data-stu-id="ff857-129">Flowers</span></span>|<span data-ttu-id="ff857-130">81</span><span class="sxs-lookup"><span data-stu-id="ff857-130">81</span></span>|  
  
 <span data-ttu-id="ff857-131">In questo esempio il campo Name è posizionato nell'area Gruppi di categorie.</span><span class="sxs-lookup"><span data-stu-id="ff857-131">In this example, the Name field is placed in the Category Groups area.</span></span> <span data-ttu-id="ff857-132">Il campo Sales è posizionato nell'area Valori.</span><span class="sxs-lookup"><span data-stu-id="ff857-132">The Sales field is placed in the Values area.</span></span> <span data-ttu-id="ff857-133">Il campo Sales viene automaticamente aggregato per il grafico quando viene rilasciato.</span><span class="sxs-lookup"><span data-stu-id="ff857-133">The Sales field is automatically aggregated for the chart when you drop it.</span></span> <span data-ttu-id="ff857-134">Il grafico radar calcola dove posizionare le etichette in base al numero di valori presenti nel campo Sales, che contiene cinque valori, e posiziona le etichette in un cerchio in corrispondenza di cinque punti equidistanti.</span><span class="sxs-lookup"><span data-stu-id="ff857-134">The radar chart calculates where to place the labels based on the number of values in the Sales field, which contains five values and places labels at five equidistant points on a circle.</span></span> <span data-ttu-id="ff857-135">Se il campo Sales contenesse tre valori, le etichette verrebbero posizionate in un cerchio in corrispondenza di tre punti equidistanti.</span><span class="sxs-lookup"><span data-stu-id="ff857-135">If the Sales field contained three values, the labels would be placed at three equidistant points on a circle.</span></span>  
  
 <span data-ttu-id="ff857-136">Nella figura seguente è illustrato un esempio di un grafico radar basato sui dati presentati.</span><span class="sxs-lookup"><span data-stu-id="ff857-136">The following illustration shows an example of a radar chart based on the data presented.</span></span>  
  
 <span data-ttu-id="ff857-137">![Grafico radar](../media/rs-radarchart.gif "Grafico radar")</span><span class="sxs-lookup"><span data-stu-id="ff857-137">![Radar chart](../media/rs-radarchart.gif "Radar chart")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff857-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ff857-138">See Also</span></span>  
 <span data-ttu-id="ff857-139">[Grafici &#40;Generatore report e SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ff857-139">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="ff857-140">[Formattazione di un grafico &#40;Generatore report e SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ff857-140">[Formatting a Chart &#40;Report Builder and SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="ff857-141">[Tipi di grafico &#40;Generatore report e SSRS&#41;](chart-types-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ff857-141">[Chart Types &#40;Report Builder and SSRS&#41;](chart-types-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="ff857-142">[Grafici a linee &#40;Generatore report e SSRS&#41;](line-charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ff857-142">[Line Charts &#40;Report Builder and SSRS&#41;](line-charts-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="ff857-143">Punti dati vuoti e Null nei grafici &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="ff857-143">Empty and Null Data Points in Charts &#40;Report Builder and SSRS&#41;</span></span>](empty-and-null-data-points-in-charts-report-builder-and-ssrs.md)  
  
  
