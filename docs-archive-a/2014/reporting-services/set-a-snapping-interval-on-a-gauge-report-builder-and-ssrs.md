---
title: Impostare un intervallo di blocco su un misuratore (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 0ece7297-6e2f-47fb-835d-b9e9cce53fe2
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: bdc2a621c4406791838d97e93f47cd32fa9d5f94
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719458"
---
# <a name="set-a-snapping-interval-on-a-gauge-report-builder-and-ssrs"></a><span data-ttu-id="81f79-102">Impostazione di un intervallo di blocco su un misuratore (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="81f79-102">Set a Snapping Interval on a Gauge (Report Builder and SSRS)</span></span>
  <span data-ttu-id="81f79-103">Un intervallo di blocco definisce il multiplo in base al quale arrotondare i valori.</span><span class="sxs-lookup"><span data-stu-id="81f79-103">A snapping interval defines the multiple to which values are rounded.</span></span> <span data-ttu-id="81f79-104">Per impostazione predefinita, il misuratore punterà al valore esatto del campo specificato nel riquadro dei dati.</span><span class="sxs-lookup"><span data-stu-id="81f79-104">By default, the gauge will point to the exact value of the field you have specified in the data pane.</span></span> <span data-ttu-id="81f79-105">È tuttavia possibile arrotondare il valore esatto per eccesso o per difetto in modo da bloccare l'indicatore di misura su un intervallo predefinito.</span><span class="sxs-lookup"><span data-stu-id="81f79-105">However, you may want to round the exact value up or down so that the pointer will snap to a preset interval.</span></span> <span data-ttu-id="81f79-106">Se, ad esempio, il valore sul misuratore è 34,2 e si specifica un intervallo di blocco pari a 5, l'indicatore di misura del misuratore punterà al valore 35.</span><span class="sxs-lookup"><span data-stu-id="81f79-106">For example, if the value on your gauge is 34.2 and you specify a snapping interval of 5, the gauge pointer will point to 35.</span></span> <span data-ttu-id="81f79-107">Se invece il valore sul misuratore è 31,2 e si specifica un intervallo di blocco pari a 5, l'indicatore di misura del misuratore punterà al valore 30.</span><span class="sxs-lookup"><span data-stu-id="81f79-107">If the value on your gauge is 31.2 and you specify a snapping interval of 5, the gauge pointer will point to 30.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../includes/ssrbrddup-md.md)]  
  
### <a name="to-set-a-snapping-interval-on-a-gauge"></a><span data-ttu-id="81f79-108">Per impostare un intervallo di blocco su un misuratore</span><span class="sxs-lookup"><span data-stu-id="81f79-108">To set a snapping interval on a gauge</span></span>  
  
1.  <span data-ttu-id="81f79-109">Fare clic in un punto qualsiasi dei numeri del misuratore per evidenziare la scala.</span><span class="sxs-lookup"><span data-stu-id="81f79-109">Click anywhere on the numbers of the gauge to highlight the scale.</span></span>  
  
2.  <span data-ttu-id="81f79-110">Aprire il riquadro Proprietà.</span><span class="sxs-lookup"><span data-stu-id="81f79-110">Open the Properties pane.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="81f79-111">Se il riquadro proprietà non è visualizzato, fare clic sulla scheda **Visualizza** , quindi selezionare la casella di controllo **Proprietà** .</span><span class="sxs-lookup"><span data-stu-id="81f79-111">If you do not see the Properties pane, click the **View** tab and then select the **Properties** checkbox.</span></span>  
  
3.  <span data-ttu-id="81f79-112">Nella proprietà **puntatori** fare clic sul pulsante (...).</span><span class="sxs-lookup"><span data-stu-id="81f79-112">In the **Pointers** property, click the (...) button.</span></span> <span data-ttu-id="81f79-113">Verrà aperto l'editor di raccolta indicatori di misura.</span><span class="sxs-lookup"><span data-stu-id="81f79-113">The Pointer Collection Editor opens.</span></span>  
  
4.  <span data-ttu-id="81f79-114">Impostare la proprietà **SnappingEnabled** su `True` .</span><span class="sxs-lookup"><span data-stu-id="81f79-114">Set the **SnappingEnabled** property to `True`.</span></span>  
  
5.  <span data-ttu-id="81f79-115">Impostare **SnappingInterval** su un valore che rappresenta l'intervallo di blocco.</span><span class="sxs-lookup"><span data-stu-id="81f79-115">Set the **SnappingInterval** to a value that represents the snapping interval.</span></span> <span data-ttu-id="81f79-116">L'indicatore di misura verrà bloccato sul multiplo di arrotondamento più vicino al valore specificato.</span><span class="sxs-lookup"><span data-stu-id="81f79-116">The pointer will be snapped to the nearest round multiple of the value that you have specified.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81f79-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="81f79-117">See Also</span></span>  
 <span data-ttu-id="81f79-118">[Formattazione di scale su un misuratore &#40;Generatore report e SSRS&#41;](report-design/formatting-scales-on-a-gauge-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="81f79-118">[Formatting Scales on a Gauge &#40;Report Builder and SSRS&#41;](report-design/formatting-scales-on-a-gauge-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="81f79-119">[Formattazione di puntatori su un misuratore &#40;Generatore report e SSRS&#41;](report-design/formatting-pointers-on-a-gauge-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="81f79-119">[Formatting Pointers on a Gauge &#40;Report Builder and SSRS&#41;](report-design/formatting-pointers-on-a-gauge-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="81f79-120">Misuratori &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="81f79-120">Gauges &#40;Report Builder and SSRS&#41;</span></span>](report-design/gauges-report-builder-and-ssrs.md)  
  
  
