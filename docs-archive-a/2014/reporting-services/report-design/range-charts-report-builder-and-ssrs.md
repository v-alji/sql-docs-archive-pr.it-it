---
title: Grafici a intervalli (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 48e351d3-ac5b-4eda-a4bd-32a0de206a30
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 76a9723bc55030da59d22c945a40ce4418b84ab3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717465"
---
# <a name="range-charts-report-builder-and-ssrs"></a><span data-ttu-id="1767c-102">Grafici a intervalli (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="1767c-102">Range Charts (Report Builder and SSRS)</span></span>
  <span data-ttu-id="1767c-103">Il tipo di grafico a intervalli consente di visualizzare un set di punti dati, ognuno dei quali è definito da più valori per la stessa categoria.</span><span class="sxs-lookup"><span data-stu-id="1767c-103">A range chart type displays a set of data points that are each defined by multiple values for the same category.</span></span> <span data-ttu-id="1767c-104">I valori sono rappresentati dall'altezza del marcatore misurata sull'asse del valore.</span><span class="sxs-lookup"><span data-stu-id="1767c-104">Values are represented by the height of the marker as measured by the value axis.</span></span> <span data-ttu-id="1767c-105">Le etichette delle categorie vengono visualizzate sull'asse delle categorie.</span><span class="sxs-lookup"><span data-stu-id="1767c-105">Category labels are displayed on the category axis.</span></span> <span data-ttu-id="1767c-106">Nel grafico con intervalli semplice viene riempita l'area compresa tra il valore iniziale e finale per ogni punto dati.</span><span class="sxs-lookup"><span data-stu-id="1767c-106">The plain range chart fills in the area between the top and bottom value for each data point.</span></span>  
  
 <span data-ttu-id="1767c-107">Nell'illustrazione seguente viene illustrato un grafico con intervalli semplice con tre serie.</span><span class="sxs-lookup"><span data-stu-id="1767c-107">The following illustration shows a plain range chart with three series.</span></span>  
  
 <span data-ttu-id="1767c-108">![Grafico a intervalli](../media/rs-rangechart.gif "Grafico a intervalli")</span><span class="sxs-lookup"><span data-stu-id="1767c-108">![Range chart](../media/rs-rangechart.gif "Range chart")</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="variations"></a><span data-ttu-id="1767c-109">Variazioni</span><span class="sxs-lookup"><span data-stu-id="1767c-109">Variations</span></span>  
  
-   <span data-ttu-id="1767c-110">**Intervallo smussato**.</span><span class="sxs-lookup"><span data-stu-id="1767c-110">**Smooth range**.</span></span> <span data-ttu-id="1767c-111">In un grafico con intervalli smussati le linee vengono visualizzate curve anziché dritte.</span><span class="sxs-lookup"><span data-stu-id="1767c-111">A smooth range chart displays curved lines rather than straight.</span></span>  
  
-   <span data-ttu-id="1767c-112">**Intervallo a colonne**.</span><span class="sxs-lookup"><span data-stu-id="1767c-112">**Column range**.</span></span> <span data-ttu-id="1767c-113">In un grafico con intervalli a colonne vengono utilizzate colonne anziché aree per visualizzare gli intervalli.</span><span class="sxs-lookup"><span data-stu-id="1767c-113">A column range chart uses columns instead of areas to display the ranges.</span></span>  
  
-   <span data-ttu-id="1767c-114">**Intervallo a barre**.</span><span class="sxs-lookup"><span data-stu-id="1767c-114">**Bar range**.</span></span> <span data-ttu-id="1767c-115">In un grafico con intervalli a barre vengono utilizzate barre anziché aree per visualizzare gli intervalli.</span><span class="sxs-lookup"><span data-stu-id="1767c-115">A bar range chart uses bars instead of areas to display the ranges.</span></span>  
  
## <a name="data-considerations-for-range-charts"></a><span data-ttu-id="1767c-116">Considerazioni sui dati per i grafici con intervalli</span><span class="sxs-lookup"><span data-stu-id="1767c-116">Data Considerations for Range Charts</span></span>  
  
-   <span data-ttu-id="1767c-117">Con i tipi di grafici con intervalli sono richiesti due valori per ogni punto dati.</span><span class="sxs-lookup"><span data-stu-id="1767c-117">Range chart types require two values per data point.</span></span> <span data-ttu-id="1767c-118">Questi valori corrispondono ai valori minimi e massimi che definiscono l'intervallo per ogni punto dati.</span><span class="sxs-lookup"><span data-stu-id="1767c-118">These values correspond with a high value and a low value that defines the range for each data point.</span></span>  
  
-   <span data-ttu-id="1767c-119">I grafici con intervalli sono utili per l'analisi solo se i valori massimi sono sempre maggiori dei valori minimi.</span><span class="sxs-lookup"><span data-stu-id="1767c-119">Range charts are useful for analysis only if the top values are always higher than the bottom values.</span></span> <span data-ttu-id="1767c-120">In caso contrario, utilizzare un grafico a linee.</span><span class="sxs-lookup"><span data-stu-id="1767c-120">If this is not the case, consider using a line chart.</span></span> <span data-ttu-id="1767c-121">Se il valore massimo è minore del valore minimo, nel grafico con intervalli verrà visualizzato il valore assoluto della differenza tra questi valori.</span><span class="sxs-lookup"><span data-stu-id="1767c-121">If the high value is lower the low value, the range chart will display the absolute value of the difference between these values.</span></span>  
  
-   <span data-ttu-id="1767c-122">Se viene specificato un solo valore, il grafico con intervalli verrà visualizzato come un normale grafico ad area, con un solo valore per punto dati.</span><span class="sxs-lookup"><span data-stu-id="1767c-122">If only one value is specified, the range chart will display as if it were a regular area chart, with one value per data point.</span></span>  
  
-   <span data-ttu-id="1767c-123">I grafici con intervalli vengono spesso utilizzati per creare grafici dei dati che contengono i valori minimi e massimi per ogni gruppo di categorie del set di dati.</span><span class="sxs-lookup"><span data-stu-id="1767c-123">Range charts are often used to graph data that contains minimum and maximum values for each category group in the dataset.</span></span>  
  
-   <span data-ttu-id="1767c-124">La visualizzazione di marcatori su ogni punto dati non è supportata nel grafico con intervalli.</span><span class="sxs-lookup"><span data-stu-id="1767c-124">Displaying markers on each data point is not supported on the range chart.</span></span>  
  
-   <span data-ttu-id="1767c-125">Analogamente al grafico ad aree, in un grafico a intervalli semplice se i valori di più serie sono simili, le serie si sovrapporranno.</span><span class="sxs-lookup"><span data-stu-id="1767c-125">Like the area chart, in a plain range chart, if the values in multiple series are similar, the series will overlap.</span></span> <span data-ttu-id="1767c-126">In questo scenario è opportuno utilizzare un grafico con intervalli a colonne o a barre anziché un grafico semplice.</span><span class="sxs-lookup"><span data-stu-id="1767c-126">In this scenario, you may want to use a column range or bar range chart instead of a plain range chart.</span></span>  
  
-   <span data-ttu-id="1767c-127">Per creare diagrammi di Gantt, è possibile utilizzare un grafico a barre con intervalli.</span><span class="sxs-lookup"><span data-stu-id="1767c-127">Gantt charts can be created using a range bar chart.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1767c-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1767c-128">See Also</span></span>  
 <span data-ttu-id="1767c-129">[Grafici &#40;Generatore report e SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="1767c-129">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="1767c-130">[Tipi di grafico &#40;Generatore report e SSRS&#41;](chart-types-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="1767c-130">[Chart Types &#40;Report Builder and SSRS&#41;](chart-types-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="1767c-131">Formattazione di un grafico &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="1767c-131">Formatting a Chart &#40;Report Builder and SSRS&#41;</span></span>](formatting-a-chart-report-builder-and-ssrs.md)  
  
  
