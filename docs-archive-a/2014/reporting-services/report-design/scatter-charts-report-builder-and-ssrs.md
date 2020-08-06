---
title: Grafici a dispersione (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 2520ae24-0609-4890-807d-3267018aba8e
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 93f9b31089eb8399c7fdfd201d3c799608f2e91e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717466"
---
# <a name="scatter-charts-report-builder-and-ssrs"></a><span data-ttu-id="02094-102">Grafici a dispersione (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="02094-102">Scatter Charts (Report Builder and SSRS)</span></span>
  <span data-ttu-id="02094-103">In un grafico a dispersione le serie vengono visualizzate come set di punti.</span><span class="sxs-lookup"><span data-stu-id="02094-103">A scatter chart displays a series as a set of points.</span></span> <span data-ttu-id="02094-104">I valori sono rappresentati dalla posizione dei punti nel grafico.</span><span class="sxs-lookup"><span data-stu-id="02094-104">Values are represented by the position of the points on the chart.</span></span> <span data-ttu-id="02094-105">Le categorie sono rappresentate dai diversi simboli marcatori nel grafico.</span><span class="sxs-lookup"><span data-stu-id="02094-105">Categories are represented by different markers on the chart.</span></span> <span data-ttu-id="02094-106">I grafici a dispersione vengono in genere utilizzati per confrontare dati aggregati tra categorie.</span><span class="sxs-lookup"><span data-stu-id="02094-106">Scatter charts are typically used to compare aggregated data across categories.</span></span> <span data-ttu-id="02094-107">Per altre informazioni sull'aggiunta di dati a un grafico a dispersione, vedere [Grafici &#40;Generatore report e SSRS&#41;](charts-report-builder-and-ssrs.md)</span><span class="sxs-lookup"><span data-stu-id="02094-107">For more information on how to add data to a scatter chart, see [Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md)</span></span>  
  
 <span data-ttu-id="02094-108">Nella figura seguente viene illustrato un esempio di grafico a dispersione.</span><span class="sxs-lookup"><span data-stu-id="02094-108">The following illustration shows an example of a scatter chart.</span></span>  
  
 <span data-ttu-id="02094-109">![Grafico a dispersione](../media/rs-scatterchart.gif "Grafico a dispersione")</span><span class="sxs-lookup"><span data-stu-id="02094-109">![Scatter chart](../media/rs-scatterchart.gif "Scatter chart")</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="variations"></a><span data-ttu-id="02094-110">Variazioni</span><span class="sxs-lookup"><span data-stu-id="02094-110">Variations</span></span>  
  
-   <span data-ttu-id="02094-111">**A bolle.**</span><span class="sxs-lookup"><span data-stu-id="02094-111">**Bubble.**</span></span> <span data-ttu-id="02094-112">I grafici a bolle consentono di visualizzare la differenza tra due valori di un punto dati sulla base delle dimensioni della bolla.</span><span class="sxs-lookup"><span data-stu-id="02094-112">Bubble charts display the difference between two values of a data point based on the size of the bubble.</span></span> <span data-ttu-id="02094-113">Più grande è la bolla, maggiore sarà la differenza tra i due valori.</span><span class="sxs-lookup"><span data-stu-id="02094-113">The larger the bubble, the larger the difference between the two values.</span></span>  
  
-   <span data-ttu-id="02094-114">**Bolle 3D**.</span><span class="sxs-lookup"><span data-stu-id="02094-114">**3-D Bubble**.</span></span> <span data-ttu-id="02094-115">Grafico a bolle visualizzato in 3D.</span><span class="sxs-lookup"><span data-stu-id="02094-115">A bubble chart displayed in 3-D.</span></span>  
  
## <a name="data-considerations-for-a-scatter-chart"></a><span data-ttu-id="02094-116">Considerazioni sui dati per un grafico a dispersione</span><span class="sxs-lookup"><span data-stu-id="02094-116">Data Considerations for a Scatter Chart</span></span>  
  
-   <span data-ttu-id="02094-117">I grafici a dispersione vengono in genere utilizzati per visualizzare e confrontare valori numerici, ad esempio dati scientifici, statistici e ingegneristici.</span><span class="sxs-lookup"><span data-stu-id="02094-117">Scatter charts are commonly used for displaying and comparing numeric values, such as scientific, statistical, and engineering data.</span></span>  
  
-   <span data-ttu-id="02094-118">Utilizzare un grafico a dispersione quando si desidera confrontare un numero elevato di punti dati senza tener conto del tempo.</span><span class="sxs-lookup"><span data-stu-id="02094-118">Use the scatter chart when you want to compare large numbers of data points without regard to time.</span></span> <span data-ttu-id="02094-119">Maggiore è la quantità di dati inclusi in un grafico a dispersione, migliori saranno i confronti che è possibile effettuare.</span><span class="sxs-lookup"><span data-stu-id="02094-119">The more data that you include in a scatter chart, the better the comparisons that you can make.</span></span>  
  
-   <span data-ttu-id="02094-120">Per un grafico a bolle sono necessari due valori (massimo e minimo) per ogni punto dati.</span><span class="sxs-lookup"><span data-stu-id="02094-120">The bubble chart requires two values (top and bottom) per data point.</span></span>  
  
-   <span data-ttu-id="02094-121">I grafici a dispersione sono ideali per gestire la distribuzione di valori e cluster di punti dati.</span><span class="sxs-lookup"><span data-stu-id="02094-121">Scatter charts are ideal for handling the distribution of values and clusters of data points.</span></span> <span data-ttu-id="02094-122">Si tratta del tipo di grafico migliore se il set di dati contiene molti punti, ad esempio diverse migliaia.</span><span class="sxs-lookup"><span data-stu-id="02094-122">This is the best chart type if your dataset contains many points (for example, several thousand points).</span></span> <span data-ttu-id="02094-123">È opportuno evitare di visualizzare più serie in un grafico a punti poiché può causare distrazione.</span><span class="sxs-lookup"><span data-stu-id="02094-123">Displaying multiple series on a point chart is visually distracting and should be avoided.</span></span> <span data-ttu-id="02094-124">In uno scenario di questo tipo è preferibile utilizzare un grafico a linee.</span><span class="sxs-lookup"><span data-stu-id="02094-124">In this scenario, consider using a line chart.</span></span>  
  
-   <span data-ttu-id="02094-125">Per impostazione predefinita, nei grafici a dispersione i punti dati vengono visualizzati come cerchi.</span><span class="sxs-lookup"><span data-stu-id="02094-125">By default, scatter charts display data points as circles.</span></span> <span data-ttu-id="02094-126">Se in un grafico a dispersione sono presenti più serie, è preferibile modificare la forma del marcatore di ogni punto in modo che sia quadrata, triangolare, romboidale o comunque diversa.</span><span class="sxs-lookup"><span data-stu-id="02094-126">If you have multiple series on a scatter chart, consider changing the marker shape of each point to be square, triangle, diamond, or another shape.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02094-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="02094-127">See Also</span></span>  
 <span data-ttu-id="02094-128">[Grafici &#40;Generatore report e SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="02094-128">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="02094-129">[Tipi di grafico &#40;Generatore report e SSRS&#41;](chart-types-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="02094-129">[Chart Types &#40;Report Builder and SSRS&#41;](chart-types-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="02094-130">[Formattazione di un grafico &#40;Generatore report e SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="02094-130">[Formatting a Chart &#40;Report Builder and SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="02094-131">Grafici a linee &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="02094-131">Line Charts &#40;Report Builder and SSRS&#41;</span></span>](line-charts-report-builder-and-ssrs.md)  
  
  
