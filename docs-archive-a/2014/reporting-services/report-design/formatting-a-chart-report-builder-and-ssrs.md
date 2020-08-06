---
title: Formattazione di un grafico (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10214"
- sql12.rtp.rptdesigner.calculatedseriesproperties.fill.f1
- sql12.rtp.rptdesigner.serieslabelproperties.fill.f1
- sql12.rtp.rptdesigner.legendproperties.fill.f1
- "10149"
- sql12.rtp.rptdesigner.seriesproperties.shadow.f1
- sql12.rtp.rptdesigner.seriesproperties.markers.f1
- "10255"
- sql12.rtp.rptdesigner.charttitleproperties.fill.f1
- "10154"
- "10170"
- "10173"
- sql12.rtp.rptdesigner.seriesproperties.fill.f1
- "10169"
- "10158"
- sql12.rtp.rptdesigner.chartareaproperties.fill.f1
- sql12.rtp.rptdesigner.charttitleproperties.shadow.f1
- "10246"
- "10150"
- sql12.rtp.rptdesigner.calculatedseriesproperties.borders.f1
- sql12.rtp.rptdesigner.chartproperties.fill.f1
- "10159"
- sql12.rtp.rptdesigner.majorgridlineproperties.gridlineoptions.f1
- "10160"
- sql12.rtp.rptdesigner.serieslabelproperties.font.f1
- "10182"
- "10163"
- "10164"
- "10253"
- "10216"
- "10171"
- "10257"
- sql12.rtp.rptdesigner.chartareaproperties.border.f1
- sql12.rtp.rptdesigner.calculatedseriesproperties.shadow.f1
- sql12.rtp.rptdesigner.chartproperties.border.f1
- sql12.rtp.rptdesigner.minorgridlineproperties.gridlineoptions.f1
- sql12.rtp.rptdesigner.chartareaproperties.shadow.f1
- sql12.rtp.rptdesigner.charttitleproperties.borders.f1
- sql12.rtp.rptdesigner.charttitleproperties.font.f1
- "10247"
ms.assetid: d3984300-c766-42f8-b7c4-863123d67c99
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: af164d4db9b6439f0634d113652b95939827b0f5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627090"
---
# <a name="formatting-a-chart-report-builder-and-ssrs"></a><span data-ttu-id="d6974-102">Formattazione di un grafico (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="d6974-102">Formatting a Chart (Report Builder and SSRS)</span></span>
  <span data-ttu-id="d6974-103">Dopo aver definito i dati per il grafico e una volta ottenuta la visualizzazione desiderata, è possibile aggiungere una formattazione per migliorare l'aspetto complessivo ed evidenziare i principali punti dati.</span><span class="sxs-lookup"><span data-stu-id="d6974-103">After you have defined the data for your chart and it is appearing the way you want, you can add formatting to improve the overall appearance and highlight key data points.</span></span> <span data-ttu-id="d6974-104">Le opzioni di formattazione più comuni possono essere modificate dalla finestra di dialogo Proprietà accessibile facendo clic con il pulsante destro del mouse su un elemento del grafico per visualizzare il relativo menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="d6974-104">The most common formatting options can be modified from the Properties dialog box that are found when you right-click a chart element to display its shortcut menu.</span></span> <span data-ttu-id="d6974-105">A ogni elemento del grafico è associata una finestra di dialogo specifica.</span><span class="sxs-lookup"><span data-stu-id="d6974-105">Each chart element has its own dialog box.</span></span> <span data-ttu-id="d6974-106">Per altre informazioni sugli elementi dei grafici, vedere [Grafici &#40;Generatore report e SSRS&#41;](charts-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="d6974-106">For more information about chart elements, see [Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="d6974-107">Tutte le proprietà correlate al grafico sono disponibili nel riquadro Proprietà, ma molte di esse possono essere impostate anche da una finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="d6974-107">All properties that relate to the chart are located in the Properties pane, but many of these properties can also be set from a dialog box.</span></span> <span data-ttu-id="d6974-108">Se si formatta la serie, è possibile definire proprietà specifiche usando attributi personalizzati, disponibili solo nella categoria **CustomAttributes** delle proprietà nel riquadro Proprietà.</span><span class="sxs-lookup"><span data-stu-id="d6974-108">If you are formatting the series, you can specify series-specific properties using custom attributes, which can only be found in the **CustomAttributes** category of properties, located in the Properties pane.</span></span>  
  
 <span data-ttu-id="d6974-109">Per formattare in modo efficace il grafico con un numero minimo di passaggi, modificare lo stile predefinito del bordo, la tavolozza e lo stile di disegno.</span><span class="sxs-lookup"><span data-stu-id="d6974-109">To effectively format the chart using a minimal number of steps, change the default border style, palette and drawing style.</span></span> <span data-ttu-id="d6974-110">Queste tre caratteristiche producono le modifiche maggiormente visibili nel grafico.</span><span class="sxs-lookup"><span data-stu-id="d6974-110">These three features produce the largest visible change on the chart.</span></span> <span data-ttu-id="d6974-111">Gli stili di disegno sono applicabili solo ai grafici a torta, ad anello a barre e istogrammi.</span><span class="sxs-lookup"><span data-stu-id="d6974-111">Drawing styles are only applicable to pie, doughnut, bar and column charts.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="in-this-section"></a><span data-ttu-id="d6974-112">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="d6974-112">In This Section</span></span>  
 [<span data-ttu-id="d6974-113">Formattazione dei colori delle serie in un grafico &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="d6974-113">Formatting Series Colors on a Chart &#40;Report Builder and SSRS&#41;</span></span>](formatting-series-colors-on-a-chart-report-builder-and-ssrs.md)  
 <span data-ttu-id="d6974-114">Viene descritto come definire i colori tramite una tavolozza, come definire una tavolozza dei colori personalizzata e come definire i colori in base a un'espressione.</span><span class="sxs-lookup"><span data-stu-id="d6974-114">Discusses how colors are defined using a palette, how you can define your own color palette, and how to define colors based on an expression.</span></span>  
  
 [<span data-ttu-id="d6974-115">Formattazione delle etichette degli assi in un grafico &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="d6974-115">Formatting Axis Labels on a Chart &#40;Report Builder and SSRS&#41;</span></span>](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md)  
 <span data-ttu-id="d6974-116">Viene descritto come visualizzare al griglia, i segni di graduazione e i titoli, nonché come formattare i numeri e le date sulla scala dell'asse.</span><span class="sxs-lookup"><span data-stu-id="d6974-116">Discusses how to display gridlines, tick marks, and titles, and how to format numbers and dates on the axis scale.</span></span>  
  
 [<span data-ttu-id="d6974-117">Formattazione della legenda in un grafico &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="d6974-117">Formatting the Legend on a Chart &#40;Report Builder and SSRS&#41;</span></span>](chart-legend-formatting-report-builder.md)  
 <span data-ttu-id="d6974-118">Viene descritto come modificare l'ordine e formattare gli elementi nella legenda del grafico.</span><span class="sxs-lookup"><span data-stu-id="d6974-118">Discusses how to re-order and format items in the chart legend.</span></span>  
  
 [<span data-ttu-id="d6974-119">Formattazione dei punti dati di un grafico &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="d6974-119">Formatting Data Points on a Chart &#40;Report Builder and SSRS&#41;</span></span>](formatting-data-points-on-a-chart-report-builder-and-ssrs.md)  
 <span data-ttu-id="d6974-120">Viene descritto come posizionare le etichette dei punti dati e formattare i marcatori dei punti dati per ogni serie del grafico.</span><span class="sxs-lookup"><span data-stu-id="d6974-120">Discusses how to position data point labels and format data point markers for every series on the chart.</span></span>  
  
 [<span data-ttu-id="d6974-121">Effetti 3D, smussature e altri effetti in un grafico &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="d6974-121">3D, Bevel, and Other Effects in a Chart &#40;Report Builder and SSRS&#41;</span></span>](chart-effects-3d-bevel-and-other-report-builder.md)  
 <span data-ttu-id="d6974-122">Vengono descritti vari effetti 3D che è possibile applicare a un grafico.</span><span class="sxs-lookup"><span data-stu-id="d6974-122">Discusses various 3D effects that you can apply to a chart.</span></span>  
  
 [<span data-ttu-id="d6974-123">Aggiungere un bordo o un frame a un grafico &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="d6974-123">Add a Border Frame to a Chart &#40;Report Builder and SSRS&#41;</span></span>](add-a-border-frame-to-a-chart-report-builder-and-ssrs.md)  
 <span data-ttu-id="d6974-124">Viene illustrato come aggiungere un bordo/frame a un grafico.</span><span class="sxs-lookup"><span data-stu-id="d6974-124">Explains how to add a border frame to a chart.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6974-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d6974-125">See Also</span></span>  
 <span data-ttu-id="d6974-126">[Grafici &#40;Generatore report e SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d6974-126">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="d6974-127">[Aggiungere un bordo o un frame a un grafico &#40;Generatore report e SSRS&#41;](add-a-border-frame-to-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d6974-127">[Add a Border Frame to a Chart &#40;Report Builder and SSRS&#41;](add-a-border-frame-to-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="d6974-128">[Definire i colori in un grafico mediante la tavolozza &#40;Generatore report e SSRS&#41;](define-colors-on-a-chart-using-a-palette-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d6974-128">[Define Colors on a Chart Using a Palette &#40;Report Builder and SSRS&#41;](define-colors-on-a-chart-using-a-palette-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="d6974-129">Aggiungere stili smussato, rilievo e trama a un grafico &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="d6974-129">Add Bevel, Emboss, and Texture Styles to a Chart &#40;Report Builder and SSRS&#41;</span></span>](chart-effects-add-bevel-emboss-or-texture-report-builder.md)  
  
  
