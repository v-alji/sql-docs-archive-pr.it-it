---
title: Formattazione degli intervalli su un misuratore (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: ffdec8ca-3e95-41cd-850b-9e8c83be4b49
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 29574c58eef6f18d685b48dd8d695a5fc42c3e6e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711687"
---
# <a name="formatting-ranges-on-a-gauge-report-builder-and-ssrs"></a><span data-ttu-id="3731d-102">Formattazione di intervalli su un misuratore (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="3731d-102">Formatting Ranges on a Gauge (Report Builder and SSRS)</span></span>
  <span data-ttu-id="3731d-103">Un intervallo del misuratore è un'area sulla scala del misuratore tramite cui viene indicata un'importante sottosezione dei valori sul misuratore.</span><span class="sxs-lookup"><span data-stu-id="3731d-103">A gauge range is a zone or area on the gauge scale that indicates an important subsection of values on the gauge.</span></span> <span data-ttu-id="3731d-104">L'uso di un intervallo del misuratore consente di indicare visivamente quando il valore dell'indicatore di misura rientra in un determinato intervallo di valori.</span><span class="sxs-lookup"><span data-stu-id="3731d-104">Using a gauge range, you can visually indicate when the pointer value has gone into a certain span of values.</span></span> <span data-ttu-id="3731d-105">Gli intervalli sono definiti da un valore iniziale e un valore finale.</span><span class="sxs-lookup"><span data-stu-id="3731d-105">Ranges are defined by a start value and an end value.</span></span>  
  
 <span data-ttu-id="3731d-106">È anche possibile utilizzare gli intervalli per definire le diverse sezioni di un misuratore.</span><span class="sxs-lookup"><span data-stu-id="3731d-106">You can also use ranges to define different sections of a gauge.</span></span> <span data-ttu-id="3731d-107">Su un misuratore con valori compresi tra 0 e 10 è ad esempio possibile definire un intervallo rosso contenente i valori da 0 a 3, un intervallo giallo contenente i valori da 4 a 7 e un intervallo verde contenente i valori da 8 a 10.</span><span class="sxs-lookup"><span data-stu-id="3731d-107">For example, on a gauge with values from 0 to 10, you can define a red range that has a value from 0 to 3, a yellow range that has a value from 4 to 7 and a green range that has a value from 8 to 10.</span></span> <span data-ttu-id="3731d-108">Se il valore iniziale specificato è maggiore di quello finale specificato, i valori vengono scambiati in modo che quello iniziale diventi quello finale e viceversa.</span><span class="sxs-lookup"><span data-stu-id="3731d-108">If the start value that you specified is greater than the end value that you specified, the values are swapped so that the start value is the end value and the end value is the start value.</span></span>  
  
 <span data-ttu-id="3731d-109">È possibile posizionare l'intervallo con una procedura analoga a quella che consente di posizionare gli indicatori di misura su una scala.</span><span class="sxs-lookup"><span data-stu-id="3731d-109">You can position the range in the same way that you position pointers on a scale.</span></span> <span data-ttu-id="3731d-110">La posizione dell'intervallo dipende dalle proprietà **Posizione** e **Distanza dalla scala** .</span><span class="sxs-lookup"><span data-stu-id="3731d-110">The **Position** and **Distance from scale** properties determine the position of the range.</span></span> <span data-ttu-id="3731d-111">Per altre informazioni, vedere [Misuratori &#40;Generatore report e SSRS&#41;](gauges-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="3731d-111">For more information, see [Gauges &#40;Report Builder and SSRS&#41;](gauges-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3731d-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3731d-112">See Also</span></span>  
 <span data-ttu-id="3731d-113">[Formattazione di scale su un misuratore &#40;Generatore report e SSRS&#41;](formatting-scales-on-a-gauge-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="3731d-113">[Formatting Scales on a Gauge &#40;Report Builder and SSRS&#41;](formatting-scales-on-a-gauge-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="3731d-114">[Formattazione degli indicatori di misura su un misuratore &#40;Generatore report e SSRS&#41;](formatting-pointers-on-a-gauge-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="3731d-114">[Formatting Pointers on a Gauge &#40;Report Builder and SSRS&#41;](formatting-pointers-on-a-gauge-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="3731d-115">[Impostare un valore minimo o massimo su un misuratore &#40;Generatore report e SSRS&#41;](set-a-minimum-or-maximum-on-a-gauge-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="3731d-115">[Set a Minimum or Maximum on a Gauge &#40;Report Builder and SSRS&#41;](set-a-minimum-or-maximum-on-a-gauge-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="3731d-116">[Esercitazione: Aggiunta di un indicatore di prestazioni chiave al report &#40;Generatore report&#41;](../tutorial-adding-a-kpi-to-your-report-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="3731d-116">[Tutorial: Adding a KPI to Your Report &#40;Report Builder&#41;](../tutorial-adding-a-kpi-to-your-report-report-builder.md) </span></span>  
 [<span data-ttu-id="3731d-117">Misuratori &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="3731d-117">Gauges &#40;Report Builder and SSRS&#41;</span></span>](gauges-report-builder-and-ssrs.md)  
  
  
