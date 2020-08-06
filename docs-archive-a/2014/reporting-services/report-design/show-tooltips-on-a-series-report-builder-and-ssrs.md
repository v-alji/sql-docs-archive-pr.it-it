---
title: Visualizzare descrizioni comando in una serie (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 4c9606ff-e1c3-4cf7-a4e7-bb16f1a9e8ab
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9113ec843b3b9255f380b17ee1ab6b360fa1f60d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636556"
---
# <a name="show-tooltips-on-a-series-report-builder-and-ssrs"></a><span data-ttu-id="941e9-102">Visualizzazione di descrizioni comandi in una serie (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="941e9-102">Show ToolTips on a Series (Report Builder and SSRS)</span></span>
  <span data-ttu-id="941e9-103">È possibile aggiungere una descrizione comando a ogni punto dati nella serie di un grafico per visualizzare informazioni relative al punto dati, ad esempio il nome del gruppo, il valore del punto dati o la relativa percentuale rispetto al totale della serie, al passaggio del mouse sul punto dati in un report sottoposto a rendering.</span><span class="sxs-lookup"><span data-stu-id="941e9-103">You can add a ToolTip to each data point on the series of a chart to display information related to the data point, such as the group name, the value of the data point, or the percentage of the data point relative to the series total when users hover over the data point in a rendered report.</span></span>  
  
 <span data-ttu-id="941e9-104">Non è possibile aggiungere una descrizione comandi a una serie calcolata.</span><span class="sxs-lookup"><span data-stu-id="941e9-104">You cannot add a ToolTip to a calculated series.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-specify-a-tooltip-on-each-data-point"></a><span data-ttu-id="941e9-105">Per specificare una descrizione comandi su ogni punto dati</span><span class="sxs-lookup"><span data-stu-id="941e9-105">To specify a ToolTip on each data point</span></span>  
  
1.  <span data-ttu-id="941e9-106">Fare clic con il pulsante destro del mouse sulla serie o sul campo contenuto nell'area **Valori** , quindi scegliere **Proprietà serie**.</span><span class="sxs-lookup"><span data-stu-id="941e9-106">Right-click on the series or right-click on the field in the **Values** area, and click **Series Properties**.</span></span>  
  
2.  <span data-ttu-id="941e9-107">Fare clic su **Dati serie** e digitare una stringa o un'espressione per la proprietà **Descrizione comando** .</span><span class="sxs-lookup"><span data-stu-id="941e9-107">Click **Series Data** and, for the **ToolTip** property, type in a string or expression.</span></span> <span data-ttu-id="941e9-108">È possibile utilizzare qualsiasi parola chiave specifica del grafico per rappresentare un altro elemento sul grafico.</span><span class="sxs-lookup"><span data-stu-id="941e9-108">You can use any chart-specific keyword to represent another element on the chart.</span></span> <span data-ttu-id="941e9-109">Per altre informazioni, vedere [Formattazione dei punti dati di un grafico &#40;Generatore report e SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="941e9-109">For more information, see [Formatting Data Points on a Chart &#40;Report Builder and SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="941e9-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="941e9-110">See Also</span></span>  
 <span data-ttu-id="941e9-111">[Formattazione dei punti dati in un grafico &#40;Generatore report e SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="941e9-111">[Formatting Data Points on a Chart &#40;Report Builder and SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="941e9-112">[Modificare il testo di un elemento della legenda &#40;Generatore report e SSRS&#41;](chart-legend-change-item-text-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="941e9-112">[Change the Text of a Legend Item &#40;Report Builder and SSRS&#41;](chart-legend-change-item-text-report-builder.md) </span></span>  
 <span data-ttu-id="941e9-113">[Formattazione di colori delle serie in un grafico &#40;Generatore report e SSRS&#41;](formatting-series-colors-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="941e9-113">[Formatting Series Colors on a Chart &#40;Report Builder and SSRS&#41;](formatting-series-colors-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="941e9-114">Aggiungere un'azione drill-through a un report &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="941e9-114">Add a Drillthrough Action on a Report &#40;Report Builder and SSRS&#41;</span></span>](add-a-drillthrough-action-on-a-report-report-builder-and-ssrs.md)  
  
  
