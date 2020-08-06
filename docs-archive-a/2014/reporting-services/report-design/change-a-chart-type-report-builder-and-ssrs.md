---
title: Modificare un tipo di grafico (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: fff24978-e3bd-4fac-8cd7-d6aa81f3cc25
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: fb466bed475b27206bf6837a60d0867f5fb745be
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711727"
---
# <a name="change-a-chart-type-report-builder-and-ssrs"></a><span data-ttu-id="27ba9-102">Modificare un tipo di grafico (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="27ba9-102">Change a Chart Type (Report Builder and SSRS)</span></span>
  <span data-ttu-id="27ba9-103">Quando si inserisce un grafico in un report per la prima volta, viene visualizzata la finestra di dialogo **Seleziona tipo di grafico** .</span><span class="sxs-lookup"><span data-stu-id="27ba9-103">When you first insert a chart into a report, the **Select Chart Type** dialog appears.</span></span> <span data-ttu-id="27ba9-104">Se si elimina questa finestra di dialogo, per impostazione predefinita viene aggiunto un istogramma.</span><span class="sxs-lookup"><span data-stu-id="27ba9-104">If you cancel this dialog, a Column chart type is added by default.</span></span>  
  
 <span data-ttu-id="27ba9-105">In qualsiasi fase della progettazione del report, è possibile impostare il grafico su un tipo più appropriato in relazione al report.</span><span class="sxs-lookup"><span data-stu-id="27ba9-105">At any point when designing the report, you can change the chart type to something more suitable to the report.</span></span> <span data-ttu-id="27ba9-106">È importante selezionare il tipo di grafico adeguato per i dati utilizzati in modo che possa essere interpretato correttamente.</span><span class="sxs-lookup"><span data-stu-id="27ba9-106">It is important to select the correct chart type for your data so that it can be interpreted correctly.</span></span> <span data-ttu-id="27ba9-107">È necessario comprendere le caratteristiche di ogni tipo di grafico per determinare il grafico più appropriato per i dati.</span><span class="sxs-lookup"><span data-stu-id="27ba9-107">You should understand each chart type's characteristics to determine what chart type is best suited for your data.</span></span> <span data-ttu-id="27ba9-108">Per altre informazioni, vedere [Tipi di grafico &#40;Generatore report e SSRS&#41;](chart-types-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="27ba9-108">For more information, see [Chart Types &#40;Report Builder and SSRS&#41;](chart-types-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="27ba9-109">Quando in un grafico vengono visualizzate più serie, potrebbe essere necessario modificare il tipo di grafico di una serie singola.</span><span class="sxs-lookup"><span data-stu-id="27ba9-109">When multiple series are displayed on a chart, you may want to change the chart type of an individual series.</span></span> <span data-ttu-id="27ba9-110">È possibile modificare solo il tipo di grafico di una serie singola se il grafico è ad area, a linee, a dispersione oppure se è un istogramma.</span><span class="sxs-lookup"><span data-stu-id="27ba9-110">You can only change the chart type of an individual series if the chart type is Area, Column, Line, or Scatter.</span></span> <span data-ttu-id="27ba9-111">Per tutti gli altri tipi di grafico, tutte le serie nel grafico verranno impostate sul tipo di grafico selezionato.</span><span class="sxs-lookup"><span data-stu-id="27ba9-111">For all other chart types, all series in your chart will be changed to the selected chart type.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-change-the-chart-type"></a><span data-ttu-id="27ba9-112">Per modificare il tipo di grafico</span><span class="sxs-lookup"><span data-stu-id="27ba9-112">To change the chart type</span></span>  
  
1.  <span data-ttu-id="27ba9-113">Nella visualizzazione della struttura fare clic con il pulsante destro del mouse sul grafico e quindi scegliere **Modifica tipo di grafico**.</span><span class="sxs-lookup"><span data-stu-id="27ba9-113">In Design view, right-click the chart and then click **Change Chart Type**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="27ba9-114">Se in un grafico sono presenti più serie, è necessario fare clic con il pulsante destro del mouse sulla serie da modificare e non sul grafico.</span><span class="sxs-lookup"><span data-stu-id="27ba9-114">When there are multiple series on a chart, you must right-click on the series, not the chart, which you want to change.</span></span>  
  
2.  <span data-ttu-id="27ba9-115">Nella finestra di dialogo **Seleziona tipo di grafico** selezionare un tipo di grafico nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="27ba9-115">In the **SelectChart Type** dialog box, select a chart type from the list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27ba9-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="27ba9-116">See Also</span></span>  
 <span data-ttu-id="27ba9-117">[Grafici &#40;Generatore report e SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="27ba9-117">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="27ba9-118">[Misuratori &#40;Generatore report e SSRS&#41;](gauges-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="27ba9-118">[Gauges &#40;Report Builder and SSRS&#41;](gauges-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="27ba9-119">Aggiungere un grafico a un report &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="27ba9-119">Add a Chart to a Report &#40;Report Builder and SSRS&#41;</span></span>](add-a-chart-to-a-report-report-builder-and-ssrs.md)  
  
  
