---
title: Aggiungere o rimuovere i margini da un grafico (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 91c43f58-5771-4d33-a54d-0e802d2f5cba
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9d8bad99591964540bcd14fc5609560a3d324515
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719595"
---
# <a name="add-or-remove-margins-from-a-chart-report-builder-and-ssrs"></a><span data-ttu-id="2fe56-102">Aggiungere o rimuovere i margini da un grafico (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="2fe56-102">Add or Remove Margins from a Chart (Report Builder and SSRS)</span></span>
  <span data-ttu-id="2fe56-103">Nei tipi di grafico istogramma e a dispersione vengono automaticamente aggiunti margini laterali alle estremità dell'asse X.</span><span class="sxs-lookup"><span data-stu-id="2fe56-103">In Column and Scatter chart types, the chart automatically adds side margins on the ends of the x-axis.</span></span> <span data-ttu-id="2fe56-104">Nei tipi di grafico a barre vengono automaticamente aggiunti margini laterali alle estremità dell'asse Y.</span><span class="sxs-lookup"><span data-stu-id="2fe56-104">In Bar chart types, the chart automatically adds side margins on the ends of the y-axis.</span></span> <span data-ttu-id="2fe56-105">In tutti gli altri tipi di grafico non vengono aggiunti margini laterali.</span><span class="sxs-lookup"><span data-stu-id="2fe56-105">In all other chart types, the chart does not add side margins.</span></span> <span data-ttu-id="2fe56-106">Non è possibile modificare le dimensioni del margine.</span><span class="sxs-lookup"><span data-stu-id="2fe56-106">You cannot change the size of the margin.</span></span>  
  
 <span data-ttu-id="2fe56-107">Questo argomento non è applicabile per grafici a torta, ad anello, a imbuto o a piramide.</span><span class="sxs-lookup"><span data-stu-id="2fe56-107">This topic does not apply to pie, doughnut, funnel, or pyramid chart types.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-enable-or-disable-side-margins"></a><span data-ttu-id="2fe56-108">Per abilitare o disabilitare i margini laterali</span><span class="sxs-lookup"><span data-stu-id="2fe56-108">To enable or disable side margins</span></span>  
  
1.  <span data-ttu-id="2fe56-109">Fare clic con il pulsante destro del mouse sull'asse e selezionare **Proprietà asse**.</span><span class="sxs-lookup"><span data-stu-id="2fe56-109">Right-click the axis and select **Axis Properties**.</span></span> <span data-ttu-id="2fe56-110">Verrà visualizzata la finestra di dialogo **Proprietà asse verticale** o **orizzontale** .</span><span class="sxs-lookup"><span data-stu-id="2fe56-110">The **Vertical** or **HorizontalAxis Properties** dialog box appears.</span></span>  
  
2.  <span data-ttu-id="2fe56-111">Nella pagina **Opzioni asse** impostare la proprietà **Margini laterali** :</span><span class="sxs-lookup"><span data-stu-id="2fe56-111">On the **Axis Options** page, set the **Side margins** property:</span></span>  
  
    -   <span data-ttu-id="2fe56-112">**Automatico** Il grafico determinerà se aggiungere o meno un margine laterale in base al tipo di grafico.</span><span class="sxs-lookup"><span data-stu-id="2fe56-112">**Auto** The chart will determine whether to add a side margin based on the chart type.</span></span>  
  
    -   <span data-ttu-id="2fe56-113">**Disabilitato** I grafici a barre, a dispersione e gli istogrammi non disporranno di margini laterali.</span><span class="sxs-lookup"><span data-stu-id="2fe56-113">**Disabled** Bar, column, and scatter charts will have no side margins.</span></span>  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2fe56-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2fe56-114">See Also</span></span>  
 <span data-ttu-id="2fe56-115">[Formattazione delle etichette degli assi in un grafico &#40;Generatore report e SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2fe56-115">[Formatting Axis Labels on a Chart &#40;Report Builder and SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="2fe56-116">[Finestra di dialogo Proprietà asse, Opzioni asse &#40;Generatore report e SSRS&#41;](../axis-properties-dialog-box-axis-options-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2fe56-116">[Axis Properties Dialog Box, Axis Options &#40;Report Builder and SSRS&#41;](../axis-properties-dialog-box-axis-options-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="2fe56-117">[Specificare un intervallo dell'asse &#40;Generatore report e SSRS&#41;](specify-an-axis-interval-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2fe56-117">[Specify an Axis Interval &#40;Report Builder and SSRS&#41;](specify-an-axis-interval-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="2fe56-118">[Formattazione delle etichette degli assi come date o valute &#40;Generatore report e SSRSSSRS&#41;](format-axis-labels-as-dates-or-currencies-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2fe56-118">[Format Axis Labels as Dates or Currencies &#40;Report Builder and SSRS&#41;](format-axis-labels-as-dates-or-currencies-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="2fe56-119">Grafici &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="2fe56-119">Charts &#40;Report Builder and SSRS&#41;</span></span>](charts-report-builder-and-ssrs.md)  
  
  
