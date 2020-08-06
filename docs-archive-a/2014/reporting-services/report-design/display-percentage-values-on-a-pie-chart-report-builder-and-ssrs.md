---
title: Display Percentage Values on a Pie Chart (Report Builder and SSRS) (Visualizzare i valori in percentuale in un grafico a torta (Generatore report e SSRS)) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: eb905fc1-5235-4773-a27e-b07be9318be5
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2dee9017d34f2751b790b2e4928571160b597f1d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628440"
---
# <a name="display-percentage-values-on-a-pie-chart-report-builder-and-ssrs"></a><span data-ttu-id="ceec7-102">Visualizzare i valori in percentuale in un grafico a torta (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="ceec7-102">Display Percentage Values on a Pie Chart (Report Builder and SSRS)</span></span>
  <span data-ttu-id="ceec7-103">Per impostazione predefinita, nella legenda vengono visualizzate categorie per identificare ogni valore.</span><span class="sxs-lookup"><span data-stu-id="ceec7-103">By default, categories are shown in the legend to identify each value.</span></span> <span data-ttu-id="ceec7-104">Se nel grafico a torta si utilizzano etichette di categorie, è possibile scegliere di mostrare le percentuali nella legenda.</span><span class="sxs-lookup"><span data-stu-id="ceec7-104">If you have labeled the pie chart using category labels, you may want show percentages in the legend.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-display-percentage-values-as-labels-on-a-pie-chart"></a><span data-ttu-id="ceec7-105">Per visualizzare valori in percentuale come etichette in un grafico a torta</span><span class="sxs-lookup"><span data-stu-id="ceec7-105">To display percentage values as labels on a pie chart</span></span>  
  
1.  <span data-ttu-id="ceec7-106">Aggiungere un grafico a torta al report.</span><span class="sxs-lookup"><span data-stu-id="ceec7-106">Add a pie chart to your report.</span></span> <span data-ttu-id="ceec7-107">Per altre informazioni, vedere [Aggiungere un grafico a un report &#40;Generatore report e SSRS&#41;](add-a-chart-to-a-report-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="ceec7-107">For more information, see [Add a Chart to a Report &#40;Report Builder and SSRS&#41;](add-a-chart-to-a-report-report-builder-and-ssrs.md).</span></span>  
  
2.  <span data-ttu-id="ceec7-108">Nell'area di progettazione fare clic con il pulsante destro del mouse sulla torta e scegliere **Mostra etichette dati**.</span><span class="sxs-lookup"><span data-stu-id="ceec7-108">On the design surface, right-click on the pie and select **Show Data Labels**.</span></span> <span data-ttu-id="ceec7-109">Le etichette dati dovrebbero apparire in ogni sezione del grafico a torta.</span><span class="sxs-lookup"><span data-stu-id="ceec7-109">The data labels should appear within each slice on the pie chart.</span></span>  
  
3.  <span data-ttu-id="ceec7-110">Nell'area di progettazione fare clic con il pulsante destro del mouse sulle etichette e scegliere **Proprietà etichetta serie**.</span><span class="sxs-lookup"><span data-stu-id="ceec7-110">On the design surface, right-click on the labels and select **Series Label Properties**.</span></span> <span data-ttu-id="ceec7-111">Verrà visualizzata la finestra di dialogo **Proprietà etichetta serie** .</span><span class="sxs-lookup"><span data-stu-id="ceec7-111">The **Series Label Properties** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="ceec7-112">Digitare `#PERCENT` per l'opzione **dati etichetta** .</span><span class="sxs-lookup"><span data-stu-id="ceec7-112">Type `#PERCENT` for the **Label data** option.</span></span>  
  
5.  <span data-ttu-id="ceec7-113">(Facoltativo) Per specificare il numero di cifre decimali da visualizzare nell'etichetta, digitare "#PERCENT{P*n*}" dove *n* è il numero di cifre decimali da visualizzare.</span><span class="sxs-lookup"><span data-stu-id="ceec7-113">(Optional) To specify how many decimal places the label shows, type "#PERCENT{P*n*}" where *n* is the number of decimal places to display.</span></span> <span data-ttu-id="ceec7-114">Ad esempio per non visualizzare posizioni decimali, digitare "#PERCENT{P0}."</span><span class="sxs-lookup"><span data-stu-id="ceec7-114">For example, to display no decimal places, type "#PERCENT{P0}".</span></span>  
  
### <a name="to-display-percentage-values-in-the-legend-of-a-pie-chart"></a><span data-ttu-id="ceec7-115">Per visualizzare valori in percentuale nella legenda di un grafico a torta</span><span class="sxs-lookup"><span data-stu-id="ceec7-115">To display percentage values in the legend of a pie chart</span></span>  
  
1.  <span data-ttu-id="ceec7-116">Nell'area di progettazione fare clic con il pulsante destro del mouse sul grafico a torta e scegliere **Proprietà serie**.</span><span class="sxs-lookup"><span data-stu-id="ceec7-116">On the design surface, right-click on the pie chart and select **Series Properties**.</span></span> <span data-ttu-id="ceec7-117">Verrà visualizzata la finestra di dialogo **Proprietà serie** .</span><span class="sxs-lookup"><span data-stu-id="ceec7-117">The **Series Properties** dialog box displays.</span></span>  
  
2.  <span data-ttu-id="ceec7-118">In **Legenda**Digitare `#PERCENT` per la proprietà **Testo legenda personalizzato** .</span><span class="sxs-lookup"><span data-stu-id="ceec7-118">In **Legend**, type `#PERCENT` for the **Custom legend text** property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ceec7-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ceec7-119">See Also</span></span>  
 <span data-ttu-id="ceec7-120">[Grafici a torta &#40;Generatore report e SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ceec7-120">[Pie Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="ceec7-121">[Formattazione della legenda in un grafico &#40;Generatore report e SSRS&#41;](chart-legend-formatting-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="ceec7-121">[Formatting the Legend on a Chart &#40;Report Builder and SSRS&#41;](chart-legend-formatting-report-builder.md) </span></span>  
 <span data-ttu-id="ceec7-122">[Visualizzare le etichette dei punti dati all'esterno di un grafico a torta &#40;Generatore report e SSRS&#41;](display-data-point-labels-outside-a-pie-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ceec7-122">[Display Data Point Labels Outside a Pie Chart &#40;Report Builder and SSRS&#41;](display-data-point-labels-outside-a-pie-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="ceec7-123">Raccogliere piccole sezioni in un grafico a torta &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="ceec7-123">Collect Small Slices on a Pie Chart &#40;Report Builder and SSRS&#41;</span></span>](collect-small-slices-on-a-pie-chart-report-builder-and-ssrs.md)  
  
  
