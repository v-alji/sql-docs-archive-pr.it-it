---
title: Specificare una scala logaritmica (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: f3092c1c-b128-433d-9a95-983508b2a8d4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2cc422a6f95a420445dc604d08a23e8f8e65c95d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623775"
---
# <a name="specify-a-logarithmic-scale-report-builder-and-ssrs"></a><span data-ttu-id="7891c-102">Specificare una scala logaritmica (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="7891c-102">Specify a Logarithmic Scale (Report Builder and SSRS)</span></span>
  <span data-ttu-id="7891c-103">Se i dati sono proporzionali in modo logaritmico, è opportuno utilizzare nel grafico una scala logaritmica</span><span class="sxs-lookup"><span data-stu-id="7891c-103">If you have data that is logarithmically proportional, you may want to consider using a logarithmic scale on the chart.</span></span> <span data-ttu-id="7891c-104">per migliorare l'aspetto del grafico e agevolare la gestione dei dati.</span><span class="sxs-lookup"><span data-stu-id="7891c-104">This helps improve the appearance of the chart by making your data more manageable.</span></span> <span data-ttu-id="7891c-105">Con la maggior parte delle scale logaritmiche viene utilizzata la base 10.</span><span class="sxs-lookup"><span data-stu-id="7891c-105">Most logarithmic scales use a base of 10.</span></span>  
  
 <span data-ttu-id="7891c-106">Questa caratteristica è disponibile solo sull'asse dei valori.</span><span class="sxs-lookup"><span data-stu-id="7891c-106">This feature is only available on the value axis.</span></span> <span data-ttu-id="7891c-107">L'asse dei valori è in genere l'asse verticale, ovvero l'asse Y.</span><span class="sxs-lookup"><span data-stu-id="7891c-107">The value axis is usually the vertical, or y-axis.</span></span> <span data-ttu-id="7891c-108">Sui grafici a barre, tuttavia, è l'asse orizzontale, ovvero l'asse x.</span><span class="sxs-lookup"><span data-stu-id="7891c-108">On bar charts, however, it is the horizontal, or x-axis.</span></span>  
  
 <span data-ttu-id="7891c-109">Se l'asse è logaritmico, tutte le altre proprietà correlate all'asse verranno scalate in modo logaritmico.</span><span class="sxs-lookup"><span data-stu-id="7891c-109">If your axis is logarithmic, all other properties relating to the axis will be scaled logarithmically.</span></span> <span data-ttu-id="7891c-110">Se ad esempio si specifica una scala logaritmica in base 10 sull'asse e si imposta per l'asse un intervallo di 2, verranno generati intervalli con ordine di grandezza pari a 10 alla potenza di 2 o 100.</span><span class="sxs-lookup"><span data-stu-id="7891c-110">For example, if you specify a base-10 logarithmic scale on your axis, setting an axis interval of 2 will generate intervals in magnitudes of 10 to the power of 2, or 100.</span></span> <span data-ttu-id="7891c-111">Ciò significa che i valori dell'asse indicheranno 1, 100, 10000, anziché il risultato predefinito 1, 10, 100, 1000, 10000.</span><span class="sxs-lookup"><span data-stu-id="7891c-111">This means your axis values will read 1, 100, 10000, instead of the default result of 1, 10, 100, 1000, 10000.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-specify-a-logarithmic-scale"></a><span data-ttu-id="7891c-112">Per specificare una scala logaritmica</span><span class="sxs-lookup"><span data-stu-id="7891c-112">To specify a logarithmic scale</span></span>  
  
1.  <span data-ttu-id="7891c-113">Fare clic con il pulsante destro del mouse sull'asse Y del grafico e scegliere **Proprietà asse verticale**.</span><span class="sxs-lookup"><span data-stu-id="7891c-113">Right-click the y-axis of your chart, and click **VerticalAxis Properties**.</span></span> <span data-ttu-id="7891c-114">Viene visualizzata la finestra di dialogo **Proprietà asse verticale** .</span><span class="sxs-lookup"><span data-stu-id="7891c-114">The **VerticalAxis Properties** dialog box appears.</span></span>  
  
2.  <span data-ttu-id="7891c-115">In **Opzioni asse**selezionare **Usa scala logaritmica**.</span><span class="sxs-lookup"><span data-stu-id="7891c-115">In **Axis Options**, select **Uselogarithmic scale**.</span></span>  
  
3.  <span data-ttu-id="7891c-116">Nella casella di testo **Base logaritmo** digitare un valore positivo per la base logaritmica.</span><span class="sxs-lookup"><span data-stu-id="7891c-116">In the **Logbase** text box, type a positive value for the logarithmic base.</span></span> <span data-ttu-id="7891c-117">Se non si specifica alcun valore, il valore predefinito della base logaritmica sarà 10.</span><span class="sxs-lookup"><span data-stu-id="7891c-117">If no value is specified, the logarithmic base defaults to 10.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7891c-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7891c-118">See Also</span></span>  
 <span data-ttu-id="7891c-119">[Formattazione delle etichette degli assi in un grafico &#40;Generatore report e SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="7891c-119">[Formatting Axis Labels on a Chart &#40;Report Builder and SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="7891c-120">[Formattazione di un grafico &#40;Generatore report e SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="7891c-120">[Formatting a Chart &#40;Report Builder and SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="7891c-121">[Formattazione delle etichette degli assi come date o valute &#40;Generatore report e SSRSSSRS&#41;](format-axis-labels-as-dates-or-currencies-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="7891c-121">[Format Axis Labels as Dates or Currencies &#40;Report Builder and SSRS&#41;](format-axis-labels-as-dates-or-currencies-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="7891c-122">Grafici &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="7891c-122">Charts &#40;Report Builder and SSRS&#41;</span></span>](charts-report-builder-and-ssrs.md)  
  
  
