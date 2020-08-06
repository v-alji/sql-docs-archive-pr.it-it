---
title: Posizionamento di etichette in un grafico (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 5db74e0b-8be8-4b47-b386-faab56dffa9b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: e90cbf04e0282454658e6324f0ba6600a99cb718
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711608"
---
# <a name="position-labels-in-a-chart-report-builder-and-ssrs"></a><span data-ttu-id="de6a2-102">Posizionamento di etichette in un grafico (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="de6a2-102">Position Labels in a Chart (Report Builder and SSRS)</span></span>
  <span data-ttu-id="de6a2-103">Poiché ogni tipo di grafico è caratterizzato da una forma diversa, le etichette dei punti dati vengono collocate in una posizione ottimale in modo da non interferire con il grafico.</span><span class="sxs-lookup"><span data-stu-id="de6a2-103">Because each chart type has a different shape, data point labels are placed in an optimal location so as not to interfere on the chart.</span></span> <span data-ttu-id="de6a2-104">La posizione predefinita delle etichette varia a seconda del tipo di grafico:</span><span class="sxs-lookup"><span data-stu-id="de6a2-104">The default position of the labels depends varies with the chart type:</span></span>  
  
-   <span data-ttu-id="de6a2-105">Sui grafici in pila le etichette possono essere posizionate solo all'interno della serie.</span><span class="sxs-lookup"><span data-stu-id="de6a2-105">On stacked charts, labels can only be positioned inside the series.</span></span>  
  
-   <span data-ttu-id="de6a2-106">Sui grafici a imbuto o a piramide le etichette vengono posizionate all'esterno di una colonna.</span><span class="sxs-lookup"><span data-stu-id="de6a2-106">On funnel or pyramid charts, labels are placed on the outside in a column.</span></span>  
  
-   <span data-ttu-id="de6a2-107">Sui grafici a torta le etichette vengono posizionate all'interno delle singole sezioni.</span><span class="sxs-lookup"><span data-stu-id="de6a2-107">On pie charts, labels are placed inside the individual slices on a pie chart.</span></span>  
  
-   <span data-ttu-id="de6a2-108">Sui grafici a barre le etichette vengono posizionate all'esterno delle barre che rappresentano i punti dati.</span><span class="sxs-lookup"><span data-stu-id="de6a2-108">On bar charts, labels are placed outside of the bars that represent data points.</span></span>  
  
-   <span data-ttu-id="de6a2-109">Sui grafici polari le etichette vengono posizionate all'esterno dell'area circolare che rappresenta i punti dati.</span><span class="sxs-lookup"><span data-stu-id="de6a2-109">On polar charts, labels are placed outside of the circular area that represents data points.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-change-the-position-of-point-labels-in-a-pie-chart"></a><span data-ttu-id="de6a2-110">Per modificare la posizione delle etichette dei punti dati in un grafico a torta</span><span class="sxs-lookup"><span data-stu-id="de6a2-110">To change the position of point labels in a Pie chart</span></span>  
  
1.  <span data-ttu-id="de6a2-111">Creare un grafico a torta.</span><span class="sxs-lookup"><span data-stu-id="de6a2-111">Create a pie chart.</span></span>  
  
2.  <span data-ttu-id="de6a2-112">Nell'area di progettazione fare clic con il pulsante destro del mouse sul grafico, quindi scegliere **Mostra etichette dati**.</span><span class="sxs-lookup"><span data-stu-id="de6a2-112">On the design surface, right-click the chart and select **Show Data Labels**.</span></span>  
  
3.  <span data-ttu-id="de6a2-113">Aprire il riquadro Proprietà.</span><span class="sxs-lookup"><span data-stu-id="de6a2-113">Open the Properties pane.</span></span> <span data-ttu-id="de6a2-114">Nella scheda **Visualizza** fare clic su **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="de6a2-114">On the **View** tab, click **Properties**.</span></span>  
  
4.  <span data-ttu-id="de6a2-115">Nell'area di progettazione fare clic sul grafico.</span><span class="sxs-lookup"><span data-stu-id="de6a2-115">On the design surface, click the chart.</span></span> <span data-ttu-id="de6a2-116">Le proprietà del grafico verranno visualizzate nel riquadro Proprietà.</span><span class="sxs-lookup"><span data-stu-id="de6a2-116">The properties for the chart are displayed in the Properties pane.</span></span>  
  
5.  <span data-ttu-id="de6a2-117">Nella sezione **Generale** espandere il nodo **CustomAttributes** .</span><span class="sxs-lookup"><span data-stu-id="de6a2-117">In the **General** section, expand the **CustomAttributes** node.</span></span> <span data-ttu-id="de6a2-118">Verrà visualizzato un elenco di attributi per il grafico a torta.</span><span class="sxs-lookup"><span data-stu-id="de6a2-118">A list of attributes for the pie chart is displayed.</span></span>  
  
6.  <span data-ttu-id="de6a2-119">Selezionare un valore per la proprietà PieLabelStyle.</span><span class="sxs-lookup"><span data-stu-id="de6a2-119">Select a value for the PieLabelStyle property.</span></span>  
  
### <a name="to-change-the-position-of-point-labels-in-a-funnel-or-pyramid-chart"></a><span data-ttu-id="de6a2-120">Per modificare la posizione delle etichette dei punti in un grafico a imbuto o a piramide</span><span class="sxs-lookup"><span data-stu-id="de6a2-120">To change the position of point labels in a Funnel or Pyramid chart</span></span>  
  
1.  <span data-ttu-id="de6a2-121">Creare un grafico a imbuto o a piramide.</span><span class="sxs-lookup"><span data-stu-id="de6a2-121">Create a funnel or pyramid chart.</span></span>  
  
2.  <span data-ttu-id="de6a2-122">Nell'area di progettazione fare clic con il pulsante destro del mouse sul grafico, quindi scegliere **Mostra etichette dati**.</span><span class="sxs-lookup"><span data-stu-id="de6a2-122">On the design surface, right-click the chart and select **Show Data Labels**.</span></span>  
  
3.  <span data-ttu-id="de6a2-123">Aprire il riquadro Proprietà.</span><span class="sxs-lookup"><span data-stu-id="de6a2-123">Open the Properties pane.</span></span> <span data-ttu-id="de6a2-124">Nella scheda **Visualizza** fare clic su **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="de6a2-124">On the **View** tab, click **Properties**</span></span>  
  
4.  <span data-ttu-id="de6a2-125">Nell'area di progettazione fare clic sul grafico.</span><span class="sxs-lookup"><span data-stu-id="de6a2-125">On the design surface, click the chart.</span></span> <span data-ttu-id="de6a2-126">Le proprietà del grafico verranno visualizzate nel riquadro Proprietà.</span><span class="sxs-lookup"><span data-stu-id="de6a2-126">The properties for the chart are displayed in the Properties pane.</span></span>  
  
5.  <span data-ttu-id="de6a2-127">Nella sezione **Generale** espandere il nodo **CustomAttributes** .</span><span class="sxs-lookup"><span data-stu-id="de6a2-127">In the **General** section, expand the **CustomAttributes** node.</span></span> <span data-ttu-id="de6a2-128">Verrà visualizzato un elenco di attributi per il grafico a imbuto.</span><span class="sxs-lookup"><span data-stu-id="de6a2-128">A list of attributes for the funnel chart is displayed.</span></span>  
  
6.  <span data-ttu-id="de6a2-129">Per un grafico a imbuto, selezionare un valore per la proprietà FunnelLabelStyle.</span><span class="sxs-lookup"><span data-stu-id="de6a2-129">For a funnel chart, select a value for the FunnelLabelStyle property.</span></span> <span data-ttu-id="de6a2-130">Per un grafico a piramide, selezionare un valore per la proprietà PyramidLabelStyle.</span><span class="sxs-lookup"><span data-stu-id="de6a2-130">For a pyramid chart, select a value for the PyramidLabelStyle property.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="de6a2-131">Quando questa proprietà è impostata su un valore `OutsideInColumn`, le etichette vengono disegnate in una colonna verticale.</span><span class="sxs-lookup"><span data-stu-id="de6a2-131">When this property is set to a value `OutsideInColumn`, the labels are drawn in a vertical column.</span></span> <span data-ttu-id="de6a2-132">La posizione della colonna non può essere modificata in alcun modo.</span><span class="sxs-lookup"><span data-stu-id="de6a2-132">There is no way to change the position of the column.</span></span>  
  
### <a name="to-change-the-position-of-point-labels-in-a-bar-chart"></a><span data-ttu-id="de6a2-133">Per modificare la posizione delle etichette dei punti dati in un grafico a barre</span><span class="sxs-lookup"><span data-stu-id="de6a2-133">To change the position of point labels in a Bar chart</span></span>  
  
1.  <span data-ttu-id="de6a2-134">Creare un grafico a barre.</span><span class="sxs-lookup"><span data-stu-id="de6a2-134">Create a bar chart.</span></span>  
  
2.  <span data-ttu-id="de6a2-135">Nell'area di progettazione fare clic con il pulsante destro del mouse sul grafico, quindi scegliere **Mostra etichette dati**.</span><span class="sxs-lookup"><span data-stu-id="de6a2-135">On the design surface, right-click the chart and select **Show Data Labels**.</span></span>  
  
3.  <span data-ttu-id="de6a2-136">Aprire il riquadro Proprietà.</span><span class="sxs-lookup"><span data-stu-id="de6a2-136">Open the Properties pane.</span></span> <span data-ttu-id="de6a2-137">Nella scheda **Visualizza** fare clic su **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="de6a2-137">On the **View** tab, click **Properties**</span></span>  
  
4.  <span data-ttu-id="de6a2-138">Nell'area di progettazione fare clic sul grafico.</span><span class="sxs-lookup"><span data-stu-id="de6a2-138">On the design surface, click the chart.</span></span> <span data-ttu-id="de6a2-139">Le proprietà del grafico verranno visualizzate nel riquadro Proprietà.</span><span class="sxs-lookup"><span data-stu-id="de6a2-139">The properties for the chart are displayed in the Properties pane.</span></span>  
  
5.  <span data-ttu-id="de6a2-140">Nella sezione **Generale** espandere il nodo **CustomAttributes** .</span><span class="sxs-lookup"><span data-stu-id="de6a2-140">In the **General** section, expand the **CustomAttributes** node.</span></span> <span data-ttu-id="de6a2-141">Verrà visualizzato un elenco di attributi per il grafico a barre.</span><span class="sxs-lookup"><span data-stu-id="de6a2-141">A list of attributes for the bar chart is displayed.</span></span>  
  
6.  <span data-ttu-id="de6a2-142">Selezionare un valore per la proprietà BarLabelStyle.</span><span class="sxs-lookup"><span data-stu-id="de6a2-142">Select a value for the BarLabelStyle property.</span></span>  
  
 <span data-ttu-id="de6a2-143">Quando lo stile delle etichette del grafico a barre è impostato su `Outside`, le etichette vengono posizionate all'esterno della barra, a condizione che la posizione rientri nell'area del grafico.</span><span class="sxs-lookup"><span data-stu-id="de6a2-143">When the bar label style is set to `Outside`, the labels will be placed outside of the bar, as long as it fits in the chart area.</span></span> <span data-ttu-id="de6a2-144">Se l'etichetta non può essere posizionata all'esterno della barra ma all'interno dell'area del grafico, verrà inserita nella posizione più vicina all'estremità della barra.</span><span class="sxs-lookup"><span data-stu-id="de6a2-144">If the label cannot be placed outside of the bar but inside of the chart area, the label is placed inside the bar at the position closest to the end of the bar.</span></span>  
  
### <a name="to-change-the-position-of-point-labels-in-an-area-column-line-or-scatter-chart"></a><span data-ttu-id="de6a2-145">Per modificare la posizione delle etichette dei punti dati in un grafico ad area, a linee, a dispersione o in un istogramma</span><span class="sxs-lookup"><span data-stu-id="de6a2-145">To change the position of point labels in an Area, Column, Line or Scatter chart</span></span>  
  
1.  <span data-ttu-id="de6a2-146">Creare un grafico ad area, a linee, a dispersione o un istogramma.</span><span class="sxs-lookup"><span data-stu-id="de6a2-146">Create an Area, Column, Line or Scatter chart.</span></span>  
  
2.  <span data-ttu-id="de6a2-147">Nell'area di progettazione fare clic con il pulsante destro del mouse sul grafico, quindi scegliere **Mostra etichette dati**.</span><span class="sxs-lookup"><span data-stu-id="de6a2-147">On the design surface, right-click the chart and select **Show Data Labels**.</span></span>  
  
3.  <span data-ttu-id="de6a2-148">Aprire il riquadro Proprietà.</span><span class="sxs-lookup"><span data-stu-id="de6a2-148">Open the Properties pane.</span></span> <span data-ttu-id="de6a2-149">Nella scheda **Visualizza** fare clic su **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="de6a2-149">On the **View** tab, click **Properties**</span></span>  
  
4.  <span data-ttu-id="de6a2-150">Nell'area di progettazione fare clic sulla serie.</span><span class="sxs-lookup"><span data-stu-id="de6a2-150">On the design surface, click the series.</span></span> <span data-ttu-id="de6a2-151">Le proprietà della serie verranno visualizzate nel riquadro Proprietà.</span><span class="sxs-lookup"><span data-stu-id="de6a2-151">The properties for the series are displayed in the Properties pane.</span></span>  
  
5.  <span data-ttu-id="de6a2-152">Nella sezione **Dati** espandere il nodo **DataPoint** e quindi il nodo **Label**.</span><span class="sxs-lookup"><span data-stu-id="de6a2-152">In the **Data** section, expand the **DataPoint** node, then expand the **Label**node.</span></span>  
  
6.  <span data-ttu-id="de6a2-153">Selezionare un valore per la proprietà Position.</span><span class="sxs-lookup"><span data-stu-id="de6a2-153">Select a value for the Position property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de6a2-154">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="de6a2-154">See Also</span></span>  
 <span data-ttu-id="de6a2-155">[Grafici a torta &#40;Generatore report e SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="de6a2-155">[Pie Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="de6a2-156">[Grafici a barre &#40;Generatore report e SSRS&#41;](bar-charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="de6a2-156">[Bar Charts &#40;Report Builder and SSRS&#41;](bar-charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="de6a2-157">[Formattazione delle etichette degli assi in un grafico &#40;Generatore report e SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="de6a2-157">[Formatting Axis Labels on a Chart &#40;Report Builder and SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="de6a2-158">[Formattazione delle etichette degli assi come date o valute &#40;Generatore report e SSRSSSRS&#41;](format-axis-labels-as-dates-or-currencies-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="de6a2-158">[Format Axis Labels as Dates or Currencies &#40;Report Builder and SSRS&#41;](format-axis-labels-as-dates-or-currencies-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="de6a2-159">[Visualizzare le etichette dei punti dati al di fuori di un grafico a torta &#40;Generatore report e SSRS&#41;](display-data-point-labels-outside-a-pie-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="de6a2-159">[Display Data Point Labels Outside a Pie Chart &#40;Report Builder and SSRS&#41;](display-data-point-labels-outside-a-pie-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="de6a2-160">Formattazione dei punti dati di un grafico &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="de6a2-160">Formatting Data Points on a Chart &#40;Report Builder and SSRS&#41;</span></span>](formatting-data-points-on-a-chart-report-builder-and-ssrs.md)  
  
  
