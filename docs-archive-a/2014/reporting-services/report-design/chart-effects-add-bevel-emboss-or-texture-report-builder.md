---
title: Add Bevel, Emboss, and Texture Styles to a Chart (Aggiungere gli stili smussato, rilievo e trama a un grafico (Generatore report e SSRS)) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 737cfc80-b39e-497c-817b-b46693deb58f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 92c5d4af47b7889b9ba5ec421706848f8822075b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636581"
---
# <a name="add-bevel-emboss-and-texture-styles-to-a-chart-report-builder-and-ssrs"></a><span data-ttu-id="8ee43-102">Aggiungere stili smussato, rilievo e trama a un grafico (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="8ee43-102">Add Bevel, Emboss, and Texture Styles to a Chart (Report Builder and SSRS)</span></span>
  <span data-ttu-id="8ee43-103">Quando si utilizzano determinati tipi di grafico, è possibile specificare un effetto di disegno per aumentarne l'effetto visivo.</span><span class="sxs-lookup"><span data-stu-id="8ee43-103">When using certain chart types, you can specify a drawing effect to increase the visual impact of your chart.</span></span> <span data-ttu-id="8ee43-104">Tali effetti vengono applicati solo alle serie,</span><span class="sxs-lookup"><span data-stu-id="8ee43-104">These drawing effects are only applied to the series of your chart.</span></span> <span data-ttu-id="8ee43-105">mentre non influiscono su altri elementi del grafico.</span><span class="sxs-lookup"><span data-stu-id="8ee43-105">They have no effect on any other chart element.</span></span>  
  
 <span data-ttu-id="8ee43-106">Quando si utilizza una variante di un grafico a torta o ad anello, è possibile specificare uno stile di disegno con contorni sfumati o concavo, simile agli effetti smussato o rilievo applicabili a un'immagine.</span><span class="sxs-lookup"><span data-stu-id="8ee43-106">When you are using any variant of a pie or doughnut chart, you can specify a soft edge or concave drawing style, similar to bevel or emboss effects that can be applied to an image.</span></span>  
  
 <span data-ttu-id="8ee43-107">Quando si utilizza una variante di un grafico a barre o di un istogramma, è possibile applicare stili di trama, ad esempio cilindro, spicchio e chiaroscuro, alle singole barre o colonne.</span><span class="sxs-lookup"><span data-stu-id="8ee43-107">When you are using any variant of a bar or column chart, you can apply texture styles, such as cylinder, wedge, and light-to-dark, to the individual bars or columns.</span></span>  
  
 <span data-ttu-id="8ee43-108">Oltre a questi stili di disegno, è possibile aggiungere bordi e ombreggiature a molti elementi del grafico per conferire un effetto ottico di profondità.</span><span class="sxs-lookup"><span data-stu-id="8ee43-108">In addition to these drawing styles, you can add borders and shadows to many chart elements to give the illusion of depth.</span></span> <span data-ttu-id="8ee43-109">Per altre informazioni su altri modi per formattare il grafico, vedere [Formattazione di un grafico &#40;Generatore report e SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="8ee43-109">For more information on other ways to format the chart, see [Formatting a Chart &#40;Report Builder and SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-bevel-or-emboss-styles-to-a-pie-or-doughnut-chart"></a><span data-ttu-id="8ee43-110">Per aggiungere gli stili smussato o rilievo a un grafico a torta o ad anello</span><span class="sxs-lookup"><span data-stu-id="8ee43-110">To add bevel or emboss styles to a pie or doughnut chart</span></span>  
  
1.  <span data-ttu-id="8ee43-111">Nella scheda **Visualizza** selezionare **Proprietà** per aprire il riquadro Proprietà.</span><span class="sxs-lookup"><span data-stu-id="8ee43-111">On the **View** tab, select **Properties** to open the Properties pane.</span></span>  
  
2.  <span data-ttu-id="8ee43-112">Selezionare il grafico a torta o ad anello che si desidera ottimizzare.</span><span class="sxs-lookup"><span data-stu-id="8ee43-112">Select the pie or doughnut chart that you want to enhance.</span></span> <span data-ttu-id="8ee43-113">Selezionare un campo di dati nel grafico, non tutto il grafico.</span><span class="sxs-lookup"><span data-stu-id="8ee43-113">Select a data field in the chart, not the entire chart.</span></span>  
  
3.  <span data-ttu-id="8ee43-114">Nel riquadro Proprietà espandere il nodo **CustomAttributes** .</span><span class="sxs-lookup"><span data-stu-id="8ee43-114">In the Properties pane, expand the **CustomAttributes** node.</span></span>  
  
4.  <span data-ttu-id="8ee43-115">Per PieDrawingStyle selezionare uno stile dall'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="8ee43-115">For PieDrawingStyle, select a style from the drop-down list.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8ee43-116">Non è possibile disporre di stili 3D e smussato o rilievo nello stesso grafico.</span><span class="sxs-lookup"><span data-stu-id="8ee43-116">You can't have 3D and bevel or emboss styles on the same chart.</span></span> <span data-ttu-id="8ee43-117">Una volta abilitato lo stile 3D per il grafico, la proprietà PieDrawingStyle non verrà visualizzata.</span><span class="sxs-lookup"><span data-stu-id="8ee43-117">If you have enabled 3D for the chart, you will not see the PieDrawingStyle property.</span></span>  
  
 <span data-ttu-id="8ee43-118">![Grafico a torta con stile di disegno concavo](../media/rs-piedrawingeffects-concave.gif "Grafico a torta con stile di disegno concavo")</span><span class="sxs-lookup"><span data-stu-id="8ee43-118">![Pie chart with concave drawing style](../media/rs-piedrawingeffects-concave.gif "Pie chart with concave drawing style")</span></span>  
  
### <a name="to-add-texture-styles-to-a-bar-or-column-chart"></a><span data-ttu-id="8ee43-119">Per aggiungere gli stili di trama a un grafico a barre o a un istogramma</span><span class="sxs-lookup"><span data-stu-id="8ee43-119">To add texture styles to a bar or column chart</span></span>  
  
1.  <span data-ttu-id="8ee43-120">Selezionare il grafico a barre o l'istogramma che si desidera ottimizzare.</span><span class="sxs-lookup"><span data-stu-id="8ee43-120">Select the bar or column chart that you want to enhance.</span></span> <span data-ttu-id="8ee43-121">Selezionare un campo di dati nel grafico, non tutto il grafico.</span><span class="sxs-lookup"><span data-stu-id="8ee43-121">Select a data field in the chart, not the entire chart.</span></span>  
  
2.  <span data-ttu-id="8ee43-122">Aprire il riquadro Proprietà.</span><span class="sxs-lookup"><span data-stu-id="8ee43-122">Open the Properties pane.</span></span>  
  
3.  <span data-ttu-id="8ee43-123">Espandere il nodo **CustomAttributes** .</span><span class="sxs-lookup"><span data-stu-id="8ee43-123">Expand the **CustomAttributes** node.</span></span>  
  
4.  <span data-ttu-id="8ee43-124">Per DrawingStyle selezionare uno stile dall'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="8ee43-124">For DrawingStyle, select a style from the drop-down list.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8ee43-125">Non è possibile disporre di stili 3D e smussato o rilievo nello stesso grafico.</span><span class="sxs-lookup"><span data-stu-id="8ee43-125">You can't have 3D and bevel or emboss styles on the same chart.</span></span> <span data-ttu-id="8ee43-126">Una volta abilitato lo stile 3D per il grafico, la proprietà PieDrawingStyle non verrà visualizzata.</span><span class="sxs-lookup"><span data-stu-id="8ee43-126">If you have enabled 3D for the chart, you will not see the PieDrawingStyle property.</span></span>  
  
 <span data-ttu-id="8ee43-127">![Grafico a barre con effetto di disegno LightToDark](../media/rs-bardrawingeffects-lighttodark.gif "Grafico a barre con effetto di disegno LightToDark")</span><span class="sxs-lookup"><span data-stu-id="8ee43-127">![Bar chart with LightToDark drawing effect](../media/rs-bardrawingeffects-lighttodark.gif "Bar chart with LightToDark drawing effect")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ee43-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8ee43-128">See Also</span></span>  
 <span data-ttu-id="8ee43-129">[Grafici a barre &#40;Generatore report e SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="8ee43-129">[Bar Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="8ee43-130">[Istogrammi &#40;Generatore report e SSRS&#41;](column-charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="8ee43-130">[Column Charts &#40;Report Builder and SSRS&#41;](column-charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="8ee43-131">[Grafici a torta &#40;Generatore report e SSRS&#41;](pie-charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="8ee43-131">[Pie Charts &#40;Report Builder and SSRS&#41;](pie-charts-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="8ee43-132">Formattazione di un grafico &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="8ee43-132">Formatting a Chart &#40;Report Builder and SSRS&#41;</span></span>](formatting-a-chart-report-builder-and-ssrs.md)  
  
  
