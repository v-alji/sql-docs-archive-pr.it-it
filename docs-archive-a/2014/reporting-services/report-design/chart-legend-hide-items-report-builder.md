---
title: Nascondere elementi legenda nel grafico (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 92256240-0cd5-4be4-8904-d1e3b93cb6b3
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 20444432f580ffaf1c5f4de1320b06319f973a01
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636569"
---
# <a name="hide-legend-items-on-the-chart-report-builder-and-ssrs"></a><span data-ttu-id="94126-102">Nascondere elementi legenda nel grafico (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="94126-102">Hide Legend Items on the Chart (Report Builder and SSRS)</span></span>
  <span data-ttu-id="94126-103">Per impostazione predefinita, qualsiasi serie aggiunta a un grafico senza forme verrà aggiunta come elemento nella legenda.</span><span class="sxs-lookup"><span data-stu-id="94126-103">By default, any series added to a non-Shape chart will be added as an item in the legend.</span></span> <span data-ttu-id="94126-104">Per grafici a torta, ad anello, a imbuto e a piramide, qualsiasi serie aggiunta al grafico determina l'aggiunta di punti dati singoli nella legenda.</span><span class="sxs-lookup"><span data-stu-id="94126-104">For pie, doughnut, funnel, and pyramid charts, any series added to the chart will add individual data points in the legend.</span></span>  
  
 <span data-ttu-id="94126-105">È possibile nascondere qualsiasi elemento della legenda.</span><span class="sxs-lookup"><span data-stu-id="94126-105">You can hide any item on the legend.</span></span> <span data-ttu-id="94126-106">Quando si nasconde un elemento della legenda, questo rimane comunque visualizzato nel grafico.</span><span class="sxs-lookup"><span data-stu-id="94126-106">When you hide a legend item, it will still appear in the chart.</span></span> <span data-ttu-id="94126-107">Ciò si rivela utile nelle situazioni in cui non si desidera mostrare ulteriori informazioni per una serie aggiunta al grafico.</span><span class="sxs-lookup"><span data-stu-id="94126-107">This is useful in situations where you do not want to show more information for a series that is added to the chart.</span></span> <span data-ttu-id="94126-108">Se ad esempio è stata aggiunta una serie calcolata come una media mobile al grafico, potrebbe essere necessario nascondere questa voce nella legenda in modo che vengano mostrate informazioni aggiuntive solo per la serie originale.</span><span class="sxs-lookup"><span data-stu-id="94126-108">For example, if you have added a calculated series like a moving average to the chart, you may want to hide this entry in the legend so that more information is only shown for the original series.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-hide-an-item-from-display-in-the-legend"></a><span data-ttu-id="94126-109">Per nascondere un elemento visualizzato nella legenda</span><span class="sxs-lookup"><span data-stu-id="94126-109">To hide an item from display in the legend</span></span>  
  
1.  <span data-ttu-id="94126-110">Fare clic con il pulsante destro del mouse sulla serie da nascondere e scegliere **Proprietà serie**.</span><span class="sxs-lookup"><span data-stu-id="94126-110">Right-click on the series you want to hide and select **Series Properties**.</span></span>  
  
2.  <span data-ttu-id="94126-111">Fare clic su **Legenda**.</span><span class="sxs-lookup"><span data-stu-id="94126-111">Click **Legend**.</span></span> <span data-ttu-id="94126-112">Selezionare l'opzione **Non mostrare questa serie in una legenda** .</span><span class="sxs-lookup"><span data-stu-id="94126-112">Select the **Do not show this series in a legend** option.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="94126-113">Non è possibile nascondere una serie per un solo gruppo.</span><span class="sxs-lookup"><span data-stu-id="94126-113">You cannot hide a series for one group and not for the others.</span></span> <span data-ttu-id="94126-114">Se è stato aggiunto un campo all'area **Gruppi di serie** , verranno nascoste tutte le serie che appartengono a questo gruppo.</span><span class="sxs-lookup"><span data-stu-id="94126-114">If you have added a field to the **Series Groups** area, all series belonging to this group will be hidden.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94126-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="94126-115">See Also</span></span>  
 <span data-ttu-id="94126-116">[Formattazione della legenda in un grafico &#40;Generatore report e SSRS&#41;](chart-legend-formatting-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="94126-116">[Formatting the Legend on a Chart &#40;Report Builder and SSRS&#41;](chart-legend-formatting-report-builder.md) </span></span>  
 <span data-ttu-id="94126-117">[Formattazione dei punti dati di un grafico &#40;Generatore report e SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="94126-117">[Formatting Data Points on a Chart &#40;Report Builder and SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="94126-118">[Modificare il testo di un elemento legenda &#40;Generatore report e SSRS&#41;](chart-legend-change-item-text-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="94126-118">[Change the Text of a Legend Item &#40;Report Builder and SSRS&#41;](chart-legend-change-item-text-report-builder.md) </span></span>  
 <span data-ttu-id="94126-119">[Aggiungere una media mobile a un grafico &#40;Generatore report e SSRS&#41;](add-a-moving-average-to-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="94126-119">[Add a Moving Average to a Chart &#40;Report Builder and SSRS&#41;](add-a-moving-average-to-a-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="94126-120">Finestra di dialogo Proprietà legenda, Generale &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="94126-120">Legend Properties Dialog Box, General &#40;Report Builder and SSRS&#41;</span></span>](../legend-properties-dialog-box-general-report-builder-and-ssrs.md)  
  
  
