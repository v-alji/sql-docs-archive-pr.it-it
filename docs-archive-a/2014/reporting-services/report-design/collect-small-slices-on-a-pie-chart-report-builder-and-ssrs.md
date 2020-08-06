---
title: Raccogliere piccole sezioni in un grafico a torta (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 21c2b8cb-b9ca-4bc0-bf49-50ba432562f6
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2302217843864115847aeb544d1c64727b8ad3a1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629206"
---
# <a name="collect-small-slices-on-a-pie-chart-report-builder-and-ssrs"></a><span data-ttu-id="8f4c0-102">Raccogliere piccole sezioni in un grafico a torta (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="8f4c0-102">Collect Small Slices on a Pie Chart (Report Builder and SSRS)</span></span>
  <span data-ttu-id="8f4c0-103">Quando in un grafico a torta viene visualizzato un numero eccessivo di punti dati, l'aspetto finale risulta poco chiaro.</span><span class="sxs-lookup"><span data-stu-id="8f4c0-103">When pie charts display too many points of data, they begin to look cluttered.</span></span> <span data-ttu-id="8f4c0-104">Per risolvere questo problema, è possibile visualizzare tutti i dati al di sotto di un determinato valore come un'unica sezione del grafico a torta.</span><span class="sxs-lookup"><span data-stu-id="8f4c0-104">To resolve this issue, you can show all data that falls beneath a certain value as one slice on the pie chart.</span></span>  
  
 <span data-ttu-id="8f4c0-105">Per raccogliere le piccole sezioni in un'unica sezione, determinare innanzitutto se la soglia deve essere misurata come percentuale del grafico a torta o come valore fisso.</span><span class="sxs-lookup"><span data-stu-id="8f4c0-105">To collect small slices into one slice, first decide whether your threshold for collecting small slices is measured as a percentage of the pie chart or as a fixed value.</span></span> <span data-ttu-id="8f4c0-106">Impostare le proprietà CollectedThreshold e CollectedThresholdUsePercent. Impostare la proprietà CollectedThreshold su una percentuale del grafico che il valore di raccolta non deve superare o il valore dei dati soglia effettivo per la raccolta.</span><span class="sxs-lookup"><span data-stu-id="8f4c0-106">Then set the CollectedThreshold and CollectedThresholdUsePercent properties.Set the CollectedThreshold property to either the percentage of the chart that a value must fall below to be collected, or the actual threshold data value for collection.</span></span> <span data-ttu-id="8f4c0-107">Impostare la proprietà CollectedThresholdUsePercent su `True` per usare una percentuale o `False` per usare un valore effettivo.</span><span class="sxs-lookup"><span data-stu-id="8f4c0-107">Set the CollectedThresholdUsePercent property to `True` to use a percentage or `False` to use an actual value.</span></span>  
  
 <span data-ttu-id="8f4c0-108">È anche possibile raccogliere le piccole sezioni in un secondo grafico a torta derivato da una sezione del primo grafico ottenuta tramite raccolta.</span><span class="sxs-lookup"><span data-stu-id="8f4c0-108">You can also collect small slices into a second pie chart that is called out from a collected slice of the first pie chart.</span></span> <span data-ttu-id="8f4c0-109">Il secondo grafico a torta verrà disegnato a destra di quello originale.</span><span class="sxs-lookup"><span data-stu-id="8f4c0-109">The second pie chart is drawn to the right of the original pie chart.</span></span>  
  
 <span data-ttu-id="8f4c0-110">Non è possibile combinare in un'unica sezione le sezioni di grafici a imbuto o a piramide.</span><span class="sxs-lookup"><span data-stu-id="8f4c0-110">You cannot combine slices of funnel or pyramid charts into one slice.</span></span>  
  
 <span data-ttu-id="8f4c0-111">Un esempio di questo grafico è disponibile come report di esempio.</span><span class="sxs-lookup"><span data-stu-id="8f4c0-111">An example of this chart is available as a sample report.</span></span> <span data-ttu-id="8f4c0-112">Per altre informazioni sul download di questo e di altri report di esempio, vedere la pagina relativa ai [report di esempio per Generatore report e Progettazione report](https://go.microsoft.com/fwlink/?LinkId=198283) di [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8f4c0-112">For more information about downloading this sample report and others, see [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)][Report Builder and Report Designer sample reports](https://go.microsoft.com/fwlink/?LinkId=198283).</span></span>  
  
### <a name="to-collect-small-slices-into-a-single-slice-on-a-pie-chart"></a><span data-ttu-id="8f4c0-113">Per raccogliere le piccole sezioni in una singola sezione di un grafico a torta</span><span class="sxs-lookup"><span data-stu-id="8f4c0-113">To collect small slices into a single slice on a pie chart</span></span>  
  
1.  <span data-ttu-id="8f4c0-114">Aprire il riquadro Proprietà.</span><span class="sxs-lookup"><span data-stu-id="8f4c0-114">Open the Properties pane.</span></span>  
  
2.  <span data-ttu-id="8f4c0-115">Nell'area di progettazione fare clic su una sezione del grafico a torta.</span><span class="sxs-lookup"><span data-stu-id="8f4c0-115">On the design surface, click on any slice of the pie chart.</span></span> <span data-ttu-id="8f4c0-116">Le proprietà della serie verranno visualizzate nel riquadro Proprietà.</span><span class="sxs-lookup"><span data-stu-id="8f4c0-116">The properties for the series are displayed in the Properties pane.</span></span>  
  
3.  <span data-ttu-id="8f4c0-117">Nella sezione **Generale** espandere il nodo **CustomAttributes** .</span><span class="sxs-lookup"><span data-stu-id="8f4c0-117">In the **General** section, expand the **CustomAttributes** node.</span></span>  
  
4.  <span data-ttu-id="8f4c0-118">Impostare la proprietà CollectedStyle su **SingleSlice**.</span><span class="sxs-lookup"><span data-stu-id="8f4c0-118">Set the CollectedStyle property to **SingleSlice**.</span></span>  
  
5.  <span data-ttu-id="8f4c0-119">Impostare il valore soglia e il tipo di soglia per la raccolta.</span><span class="sxs-lookup"><span data-stu-id="8f4c0-119">Set the collected threshold value and type of threshold.</span></span> <span data-ttu-id="8f4c0-120">Di seguito sono riportati alcuni esempi comuni di impostazione di queste soglie.</span><span class="sxs-lookup"><span data-stu-id="8f4c0-120">The following examples are common ways of setting collected thresholds.</span></span>  
  
    -   <span data-ttu-id="8f4c0-121">**Per percentuale.**</span><span class="sxs-lookup"><span data-stu-id="8f4c0-121">**By percentage.**</span></span> <span data-ttu-id="8f4c0-122">Ad esempio, per raccogliere in un'unica sezione tutte le sezioni del grafico a torta minori del 10%:</span><span class="sxs-lookup"><span data-stu-id="8f4c0-122">For example, to collect any slice on your pie chart that is less than 10% into a single slice:</span></span>  
  
         <span data-ttu-id="8f4c0-123">Impostare la proprietà CollectedThresholdUsePercent su `True` .</span><span class="sxs-lookup"><span data-stu-id="8f4c0-123">Set the CollectedThresholdUsePercent property to `True`.</span></span>  
  
         <span data-ttu-id="8f4c0-124">Impostare la proprietà CollectedThreshold su **10**.</span><span class="sxs-lookup"><span data-stu-id="8f4c0-124">Set the CollectedThreshold property to **10**.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="8f4c0-125">Se si imposta CollectedStyle su **SingleSlice**, CollectedThreshold su un valore maggiore di **100**e CollectedThresholdUsePercent è `True` , il grafico genererà un'eccezione perché non è in grado di calcolare una percentuale.</span><span class="sxs-lookup"><span data-stu-id="8f4c0-125">If you set CollectedStyle to **SingleSlice**, CollectedThreshold to a value greater than **100**, and CollectedThresholdUsePercent is `True`, the chart will throw an exception because it cannot calculate a percentage.</span></span> <span data-ttu-id="8f4c0-126">Per risolvere questo problema, impostare CollectedThreshold su un valore inferiore a **100**.</span><span class="sxs-lookup"><span data-stu-id="8f4c0-126">To resolve this issue, set the CollectedThreshold to a value less than **100**.</span></span>  
  
    -   <span data-ttu-id="8f4c0-127">**Per valore di dati.**</span><span class="sxs-lookup"><span data-stu-id="8f4c0-127">**By data value.**</span></span> <span data-ttu-id="8f4c0-128">Ad esempio, per raccogliere in un'unica sezione tutte le sezioni del grafico a torta inferiori a 5000:</span><span class="sxs-lookup"><span data-stu-id="8f4c0-128">For example, to collect any slice on your pie chart that is less than 5000 into a single slice:</span></span>  
  
         <span data-ttu-id="8f4c0-129">Impostare la proprietà CollectedThresholdUsePercent su `False` .</span><span class="sxs-lookup"><span data-stu-id="8f4c0-129">Set the CollectedThresholdUsePercent property to `False`.</span></span>  
  
         <span data-ttu-id="8f4c0-130">Impostare la proprietà CollectedThreshold su **5000**.</span><span class="sxs-lookup"><span data-stu-id="8f4c0-130">Set the CollectedThreshold property to **5000**.</span></span>  
  
6.  <span data-ttu-id="8f4c0-131">Impostare la proprietà CollectedLabel su una stringa che rappresenta l'etichetta di testo che verrà visualizzata nella sezione raccolta.</span><span class="sxs-lookup"><span data-stu-id="8f4c0-131">Set the CollectedLabel property to a string that represents the text label that will be shown on the collected slice.</span></span>  
  
7.  <span data-ttu-id="8f4c0-132">(Facoltativo) Impostare le proprietà CollectedSliceExploded, CollectedColor, CollectedLegendText e CollectedToolTip.</span><span class="sxs-lookup"><span data-stu-id="8f4c0-132">(Optional) Set the CollectedSliceExploded, CollectedColor, CollectedLegendText and CollectedToolTip properties.</span></span> <span data-ttu-id="8f4c0-133">Queste proprietà consentono di modificare l'aspetto, il colore, il testo di etichette e legende e l'aspetto delle descrizioni comando della singola sezione.</span><span class="sxs-lookup"><span data-stu-id="8f4c0-133">These properties change the appearance, color, label text, legend text and tooltip aspects of the single slice.</span></span>  
  
### <a name="to-collect-small-slices-into-a-secondary-callout-pie-chart"></a><span data-ttu-id="8f4c0-134">Per raccogliere le piccole sezioni in un grafico a torta secondario</span><span class="sxs-lookup"><span data-stu-id="8f4c0-134">To collect small slices into a secondary, callout pie chart</span></span>  
  
1.  <span data-ttu-id="8f4c0-135">Completare i passaggi da 1 a 3 descritti sopra.</span><span class="sxs-lookup"><span data-stu-id="8f4c0-135">Follow Steps 1-3 from above.</span></span>  
  
2.  <span data-ttu-id="8f4c0-136">Impostare la proprietà CollectedStyle su **CollectedPie**.</span><span class="sxs-lookup"><span data-stu-id="8f4c0-136">Set the CollectedStyle property to **CollectedPie**.</span></span>  
  
3.  <span data-ttu-id="8f4c0-137">Impostare la proprietà CollectedThresholdproperty su un valore che rappresenta la soglia in corrispondenza della quale le sezioni piccole verranno raccolte in un'unica sezione.</span><span class="sxs-lookup"><span data-stu-id="8f4c0-137">Set the CollectedThresholdproperty to a value that represents the threshold at which small slices will be collected into one slice.</span></span> <span data-ttu-id="8f4c0-138">Quando la proprietà CollectedStyle è impostata su **su CollectedPie**, CollectedThresholdUsePercentproperty è sempre impostato su `True` e la soglia raccolta viene sempre misurata in percentuale.</span><span class="sxs-lookup"><span data-stu-id="8f4c0-138">When the CollectedStyle property is set to **CollectedPie**, the CollectedThresholdUsePercentproperty is always set to `True`, and the collected threshold is always measured in percent.</span></span>  
  
4.  <span data-ttu-id="8f4c0-139">(Facoltativo) Impostare le proprietà CollectedColor, CollectedLabel, CollectedLegendText e CollectedToolTip.</span><span class="sxs-lookup"><span data-stu-id="8f4c0-139">(Optional) Set the CollectedColor, CollectedLabel, CollectedLegendText and CollectedToolTip properties.</span></span> <span data-ttu-id="8f4c0-140">Tutte le altre proprietà denominate "Collected" non si applicano alla torta raccolta.</span><span class="sxs-lookup"><span data-stu-id="8f4c0-140">All other properties named "Collected" do not apply to the collected pie.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8f4c0-141">Il grafico a torta secondario viene calcolato in base alle piccole sezioni di dati, in modo che verrà visualizzato solo in anteprima,</span><span class="sxs-lookup"><span data-stu-id="8f4c0-141">The secondary pie chart is calculated based on the small slices in your data so it will only appear in Preview.</span></span> <span data-ttu-id="8f4c0-142">non nell'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="8f4c0-142">It does not appear on the design surface.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8f4c0-143">Non è possibile formattare il grafico a torta secondario.</span><span class="sxs-lookup"><span data-stu-id="8f4c0-143">You cannot format the secondary pie chart.</span></span> <span data-ttu-id="8f4c0-144">Per questo motivo, si consiglia di utilizzare il primo approccio per la raccolta delle sezioni della torta.</span><span class="sxs-lookup"><span data-stu-id="8f4c0-144">For this reason, it is strongly recommended to use the first approach when collecting pie slices.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f4c0-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8f4c0-145">See Also</span></span>  
 <span data-ttu-id="8f4c0-146">[Grafici a torta &#40;Generatore report e SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="8f4c0-146">[Pie Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="8f4c0-147">[Formattazione dei punti dati in un grafico &#40;Generatore report e SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="8f4c0-147">[Formatting Data Points on a Chart &#40;Report Builder and SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="8f4c0-148">[Visualizzare le etichette dei punti dati all'esterno di un grafico a torta &#40;Generatore report e SSRS&#41;](display-data-point-labels-outside-a-pie-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="8f4c0-148">[Display Data Point Labels Outside a Pie Chart &#40;Report Builder and SSRS&#41;](display-data-point-labels-outside-a-pie-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="8f4c0-149">[Visualizzare i valori in percentuale in un grafico a torta &#40;Generatore report e SSRS&#41;](display-percentage-values-on-a-pie-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="8f4c0-149">[Display Percentage Values on a Pie Chart &#40;Report Builder and SSRS&#41;](display-percentage-values-on-a-pie-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="8f4c0-150">Aggiungere effetti 3D a un grafico &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="8f4c0-150">Add 3D Effects to a Chart &#40;Report Builder and SSRS&#41;</span></span>](chart-effects-add-3d-effects-report-builder.md)  
  
  
