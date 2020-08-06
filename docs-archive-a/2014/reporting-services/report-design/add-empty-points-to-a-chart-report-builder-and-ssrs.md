---
title: Aggiungere punti vuoti al grafico (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 2b056119-439f-494f-83cf-ee0c05dc6487
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 53d891c58210bcd51cd4e49f2f9a691a7729c884
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722536"
---
# <a name="add-empty-points-to-the-chart-report-builder-and-ssrs"></a><span data-ttu-id="7c8b5-102">Aggiunta di punti vuoti al grafico (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="7c8b5-102">Add Empty Points to the Chart (Report Builder and SSRS)</span></span>
  <span data-ttu-id="7c8b5-103">Nel grafico i valori Null vengono visualizzati come spazi o intervalli vuoti tra punti dati in una serie.</span><span class="sxs-lookup"><span data-stu-id="7c8b5-103">Null values are shown on the chart as empty spaces or gaps between data points in a series.</span></span> <span data-ttu-id="7c8b5-104">I punti vuoti sono punti dati che possono essere inseriti nello spazio vuoto creato dai valori Null.</span><span class="sxs-lookup"><span data-stu-id="7c8b5-104">Empty points are data points that can be inserted in the empty space created by null values.</span></span>  
  
 <span data-ttu-id="7c8b5-105">Per impostazione predefinita i punti vuoti vengono calcolati considerando la media tra il punto dati precedente e quello successivo che contiene un valore.</span><span class="sxs-lookup"><span data-stu-id="7c8b5-105">By default, empty points are calculated by taking the average of the previous and next data points that contain a value.</span></span> <span data-ttu-id="7c8b5-106">È possibile modificare questa situazione in modo che tutti i punti vuoti vengano inseriti nella posizione zero.</span><span class="sxs-lookup"><span data-stu-id="7c8b5-106">You can change this so that all empty points are inserted at zero.</span></span>  
  
 <span data-ttu-id="7c8b5-107">Per altre informazioni, vedere [Punti dati vuoti e Null nei grafici &#40;Generatore report e SSRS&#41;](charts-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="7c8b5-107">For more information, see [Empty and Null Data Points in Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-specify-empty-points-on-a-chart"></a><span data-ttu-id="7c8b5-108">Per specificare punti vuoti in un grafico</span><span class="sxs-lookup"><span data-stu-id="7c8b5-108">To specify empty points on a chart</span></span>  
  
1.  <span data-ttu-id="7c8b5-109">Aprire il riquadro Proprietà.</span><span class="sxs-lookup"><span data-stu-id="7c8b5-109">Open the Properties pane.</span></span>  
  
2.  <span data-ttu-id="7c8b5-110">Nell'area di progettazione fare clic con il pulsante destro del mouse sulla serie che contiene valori Null.</span><span class="sxs-lookup"><span data-stu-id="7c8b5-110">On the design surface, right-click the series that contains null values.</span></span> <span data-ttu-id="7c8b5-111">Le proprietà della serie verranno visualizzate nel riquadro Proprietà.</span><span class="sxs-lookup"><span data-stu-id="7c8b5-111">The properties for the series are displayed in the Properties pane.</span></span>  
  
3.  <span data-ttu-id="7c8b5-112">Espandere il nodo **EmptyPoint** .</span><span class="sxs-lookup"><span data-stu-id="7c8b5-112">Expand the **EmptyPoint** node.</span></span>  
  
4.  <span data-ttu-id="7c8b5-113">Selezionare un valore del colore per la proprietà Color.</span><span class="sxs-lookup"><span data-stu-id="7c8b5-113">Select a color value for the Color property.</span></span>  
  
5.  <span data-ttu-id="7c8b5-114">Nel nodo **EmptyPoint** espandere il nodo Marker.</span><span class="sxs-lookup"><span data-stu-id="7c8b5-114">In the **EmptyPoint** node, expand the Marker node.</span></span>  
  
6.  <span data-ttu-id="7c8b5-115">Selezionare un tipo di marcatore per la proprietà MarkerType.</span><span class="sxs-lookup"><span data-stu-id="7c8b5-115">Select a marker type for the MarkerType property.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7c8b5-116">È necessario selezionare un tipo di marcatore per aggiungere punti vuoti a una barra, a una colonna oppure a un grafico a dispersione.</span><span class="sxs-lookup"><span data-stu-id="7c8b5-116">You must select a marker type to add empty points to a bar, column or scatter chart.</span></span> <span data-ttu-id="7c8b5-117">Per i grafici ad area, a linee e radar, tuttavia, la selezione di un tipo di marcatore è facoltativa poiché nel grafico lo spazio vuoto o l'intervallo viene riempito senza che sia necessario specificare un marcatore.</span><span class="sxs-lookup"><span data-stu-id="7c8b5-117">However, for area, line and radar charts, selecting a marker type is optional because the chart fills in the empty space or gap without requiring a marker to be specified.</span></span>  
  
7.  <span data-ttu-id="7c8b5-118">Impostare il valore del punto vuoto.</span><span class="sxs-lookup"><span data-stu-id="7c8b5-118">Set the value of the empty point.</span></span>  
  
    1.  <span data-ttu-id="7c8b5-119">Nel riquadro Proprietà espandere il nodo **CustomAttributes** .</span><span class="sxs-lookup"><span data-stu-id="7c8b5-119">In the Properties pane, expand the **CustomAttributes** node.</span></span>  
  
    2.  <span data-ttu-id="7c8b5-120">Impostare la proprietà EmptyPointValue.</span><span class="sxs-lookup"><span data-stu-id="7c8b5-120">Set the EmptyPointValue property.</span></span> <span data-ttu-id="7c8b5-121">Per inserire punti vuoti in una posizione relativa alla media dei punti dati precedente e successivo, selezionare **Media**.</span><span class="sxs-lookup"><span data-stu-id="7c8b5-121">To insert empty points at an average of the previous and next data points, select **Average**.</span></span> <span data-ttu-id="7c8b5-122">Per inserire punti vuoti nella posizione zero, selezionare **Zero**.</span><span class="sxs-lookup"><span data-stu-id="7c8b5-122">To insert empty points at zero, select **Zero**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c8b5-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7c8b5-123">See Also</span></span>  
 <span data-ttu-id="7c8b5-124">[Aggiungere filtri per set di dati, aree dati e gruppi &#40;Generatore report e SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span><span class="sxs-lookup"><span data-stu-id="7c8b5-124">[Add Dataset Filters, Data Region Filters, and Group Filters &#40;Report Builder and SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span></span>  
 <span data-ttu-id="7c8b5-125">[Tipi di grafico &#40;Generatore report e SSRS&#41;](chart-types-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="7c8b5-125">[Chart Types &#40;Report Builder and SSRS&#41;](chart-types-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="7c8b5-126">[Aggiungere cambi di scala a un grafico &#40;Generatore report e SSRS&#41;](add-scale-breaks-to-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="7c8b5-126">[Add Scale Breaks to a Chart &#40;Report Builder and SSRS&#41;](add-scale-breaks-to-a-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="7c8b5-127">Grafici &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="7c8b5-127">Charts &#40;Report Builder and SSRS&#41;</span></span>](charts-report-builder-and-ssrs.md)  
  
  
