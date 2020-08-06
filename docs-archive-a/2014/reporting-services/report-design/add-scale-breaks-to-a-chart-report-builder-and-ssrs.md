---
title: Aggiungere cambi di scala a un grafico (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 84d66436-ed62-4967-bbbd-b457593ee787
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 1c081debd1e0a84158615edebdb6b84705c10e5b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719572"
---
# <a name="add-scale-breaks-to-a-chart-report-builder-and-ssrs"></a><span data-ttu-id="6db91-102">Aggiungere cambi di scala a un grafico (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="6db91-102">Add Scale Breaks to a Chart (Report Builder and SSRS)</span></span>
  <span data-ttu-id="6db91-103">Un cambio di scala è una striscia disegnata attraverso l'area del tracciato del grafico per indicare un'interruzione nella continuità tra i valori massimo e minimo sull'asse dei valori, in genere l'asse verticale o y.</span><span class="sxs-lookup"><span data-stu-id="6db91-103">A scale break is a stripe drawn across the plotting area of a chart to denote a break in continuity between the high and low values on a value axis (usually the vertical, or y-axis).</span></span> <span data-ttu-id="6db91-104">Utilizzare un cambio di scala per visualizzare due intervalli distinti nella stessa area del grafico.</span><span class="sxs-lookup"><span data-stu-id="6db91-104">Use a scale break to display two distinct ranges in the same chart area.</span></span>  
  
 <span data-ttu-id="6db91-105">![Grafico con cambio di scala](../media/rs-multipledatarangeschart-scalebreak.gif "Grafico con cambio di scala")</span><span class="sxs-lookup"><span data-stu-id="6db91-105">![Chart with scale break](../media/rs-multipledatarangeschart-scalebreak.gif "Chart with scale break")</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6db91-106">Non è possibile specificare il punto in cui posizionare un cambio di scala sul grafico.</span><span class="sxs-lookup"><span data-stu-id="6db91-106">You cannot specify where to place a scale break on your chart.</span></span> <span data-ttu-id="6db91-107">Vengono utilizzati calcoli specifici in base ai valori del set di dati per determinare se la separazione tra gli intervalli di dati è sufficiente per disegnare un cambio di scala sull'asse dei valori (asse Y) in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="6db91-107">The chart uses its own calculations based on the values in your dataset to determine whether there is sufficient separation between data ranges to draw a scale break on the value axis (y-axis) at run time.</span></span>  
  
 <span data-ttu-id="6db91-108">Un esempio di un grafico con cambi di scala è disponibile come report di esempio.</span><span class="sxs-lookup"><span data-stu-id="6db91-108">An example of a chart with scale breaks is available as a sample report.</span></span> <span data-ttu-id="6db91-109">Per altre informazioni sul download di questo e di altri report di esempio, vedere la pagina relativa ai [report di esempio per Generatore report e Progettazione report](https://go.microsoft.com/fwlink/?LinkId=198283) di [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6db91-109">For more information about downloading this sample report and others, see [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)][Report Builder and Report Designer sample reports](https://go.microsoft.com/fwlink/?LinkId=198283).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-enable-scale-breaks-on-the-chart"></a><span data-ttu-id="6db91-110">Per abilitare i cambi di scala sul grafico</span><span class="sxs-lookup"><span data-stu-id="6db91-110">To enable scale breaks on the chart</span></span>  
  
1.  <span data-ttu-id="6db91-111">Fare clic con il pulsante destro del mouse sull'asse verticale, quindi scegliere **Proprietà asse**.</span><span class="sxs-lookup"><span data-stu-id="6db91-111">Right-click the vertical axis and then click **Axis Properties**.</span></span> <span data-ttu-id="6db91-112">Viene visualizzata la finestra di dialogo **Proprietà asse verticale** .</span><span class="sxs-lookup"><span data-stu-id="6db91-112">The **VerticalAxis Properties** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="6db91-113">Selezionare la casella di controllo **Abilita cambi di scala** .</span><span class="sxs-lookup"><span data-stu-id="6db91-113">Select the **Enable scale breaks** check box.</span></span>  
  
### <a name="to-change-the-style-of-the-scale-break"></a><span data-ttu-id="6db91-114">Per modificare lo stile del cambio di scala</span><span class="sxs-lookup"><span data-stu-id="6db91-114">To change the style of the scale break</span></span>  
  
1.  <span data-ttu-id="6db91-115">Aprire il riquadro Proprietà.</span><span class="sxs-lookup"><span data-stu-id="6db91-115">Open the Properties pane.</span></span>  
  
2.  <span data-ttu-id="6db91-116">Nell'area di progettazione fare clic con il pulsante destro del mouse sull'asse Y del grafico.</span><span class="sxs-lookup"><span data-stu-id="6db91-116">On the design surface, right-click on the y-axis of the chart.</span></span> <span data-ttu-id="6db91-117">Nel riquadro Proprietà verranno visualizzate le proprietà dell'oggetto asse Y (denominato asse del grafico per impostazione predefinita).</span><span class="sxs-lookup"><span data-stu-id="6db91-117">The properties for the y-axis object (named Chart Axis by default) are displayed in the Properties pane.</span></span>  
  
3.  <span data-ttu-id="6db91-118">Nel sezione **Scala** quindi espandere la proprietà ScaleBreakStyle.</span><span class="sxs-lookup"><span data-stu-id="6db91-118">In the **Scale** section, expand the ScaleBreakStyle property.</span></span>  
  
4.  <span data-ttu-id="6db91-119">Modificare i valori delle proprietà ScaleBreakStyle, ad esempio BreakLineType e Spacing.</span><span class="sxs-lookup"><span data-stu-id="6db91-119">Change the values for ScaleBreakStyle properties, such as BreakLineType and Spacing.</span></span> <span data-ttu-id="6db91-120">Per altre informazioni sulle proprietà del cambio di scala, vedere [Visualizzazione di una serie con più intervalli di dati in un grafico &#40;Generatore report e SSRS&#41;](displaying-a-series-with-multiple-data-ranges-on-a-chart.md).</span><span class="sxs-lookup"><span data-stu-id="6db91-120">For more information about scale break properties, see [Displaying a Series with Multiple Data Ranges on a Chart &#40;Report Builder and SSRS&#41;](displaying-a-series-with-multiple-data-ranges-on-a-chart.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6db91-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6db91-121">See Also</span></span>  
 <span data-ttu-id="6db91-122">[Grafici &#40;Generatore report e SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="6db91-122">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="6db91-123">[Formattazione di un grafico &#40;Generatore report e SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="6db91-123">[Formatting a Chart &#40;Report Builder and SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="6db91-124">Finestra di dialogo Proprietà asse, Opzioni asse &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="6db91-124">Axis Properties Dialog Box, Axis Options &#40;Report Builder and SSRS&#41;</span></span>](../axis-properties-dialog-box-axis-options-report-builder-and-ssrs.md)  
  
  
