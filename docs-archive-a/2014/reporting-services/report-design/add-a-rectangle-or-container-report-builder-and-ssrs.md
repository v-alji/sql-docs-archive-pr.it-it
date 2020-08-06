---
title: Aggiungere un rettangolo o un contenitore (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10061"
- sql12.rtp.rptdesigner.rectangleproperties.general.f1
ms.assetid: f905c35f-754d-4d02-80f3-85e29ddda826
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5fddda2f02b9f370d9742ae6add5bae444f8f55f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623797"
---
# <a name="add-a-rectangle-or-container-report-builder-and-ssrs"></a><span data-ttu-id="4289f-102">Aggiungere un rettangolo o un contenitore (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="4289f-102">Add a Rectangle or Container (Report Builder and SSRS)</span></span>
  <span data-ttu-id="4289f-103">Aggiungere un rettangolo al report quando si desidera separare le aree del report con un elemento grafico, enfatizzare aree del report o fornire uno sfondo per uno o più elementi del report.</span><span class="sxs-lookup"><span data-stu-id="4289f-103">Add a rectangle to your report when you want a graphical element to separate areas of the report, emphasize areas of a report, or provide a background for one or more report items.</span></span> <span data-ttu-id="4289f-104">I rettangoli sono utilizzati anche come contenitori per consentire di controllare il rendering di aree dati in un report.</span><span class="sxs-lookup"><span data-stu-id="4289f-104">Rectangles are also used as containers to help control the way data regions render in a report.</span></span> <span data-ttu-id="4289f-105">È possibile personalizzare l'aspetto di un rettangolo modificandone le proprietà quali lo sfondo e i colori del bordo.</span><span class="sxs-lookup"><span data-stu-id="4289f-105">You can customize the appearance of a rectangle by editing rectangle properties such as the background and border colors.</span></span> <span data-ttu-id="4289f-106">Per altre informazioni sull'uso di un rettangolo come contenitore, vedere [Rettangoli e linee &#40;Generatore report e SSRS&#41;](rectangles-and-lines-report-builder-and-ssrs.md) e [Visualizzare dati identici in una matrice e in un grafico &#40;Generatore report&#41;](display-the-same-data-on-a-matrix-and-a-chart-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="4289f-106">For more information about using a rectangle as a container, see [Rectangles and Lines &#40;Report Builder and SSRS&#41;](rectangles-and-lines-report-builder-and-ssrs.md) and [Display the Same Data on a Matrix and a Chart &#40;Report Builder&#41;](display-the-same-data-on-a-matrix-and-a-chart-report-builder.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-rectangle"></a><span data-ttu-id="4289f-107">Per aggiungere un rettangolo</span><span class="sxs-lookup"><span data-stu-id="4289f-107">To add a rectangle</span></span>  
  
1.  <span data-ttu-id="4289f-108">Nella gruppo **Elementi del report** della scheda **Inserisci** fare clic su **Rettangolo**.</span><span class="sxs-lookup"><span data-stu-id="4289f-108">On the **Insert** tab, in the **Report Items** group, click **Rectangle.**</span></span>  
  
2.  <span data-ttu-id="4289f-109">Fare clic sul punto in cui si desidera posizionare l'angolo superiore sinistro del rettangolo nell'area di progettazione, quindi trascinare fino al punto in cui si desidera posizionare l'angolo inferiore destro.</span><span class="sxs-lookup"><span data-stu-id="4289f-109">On the design surface, click the location where you want the upper left corner of the rectangle, and drag to where you want the lower-right corner.</span></span>  
  
     <span data-ttu-id="4289f-110">Si noti che quando si sposta il cursore, le "guide di allineamento" vengono visualizzate quando il cursore viene allineato agli altri oggetti sull'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="4289f-110">Note that as you move the cursor, "snap lines" appear as the cursor lines up with other objects on the design surface.</span></span> <span data-ttu-id="4289f-111">In tal modo si semplifica l'allineamento degli oggetti.</span><span class="sxs-lookup"><span data-stu-id="4289f-111">These help you if you want objects to be aligned.</span></span>  
  
### <a name="to-create-a-container"></a><span data-ttu-id="4289f-112">Per creare un contenitore</span><span class="sxs-lookup"><span data-stu-id="4289f-112">To create a container</span></span>  
  
1.  <span data-ttu-id="4289f-113">Aggiungere un elemento del report Rettangolo al report.</span><span class="sxs-lookup"><span data-stu-id="4289f-113">Add a rectangle report item to the report.</span></span>  
  
2.  <span data-ttu-id="4289f-114">Trascinare altri elementi del report nel rettangolo.</span><span class="sxs-lookup"><span data-stu-id="4289f-114">Drag other report items into the rectangle.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4289f-115">Un rettangolo è solo un contenitore di elementi che in esso vengono creati o trascinati.</span><span class="sxs-lookup"><span data-stu-id="4289f-115">A rectangle is only a container for items that you either create in the rectangle or drag into the rectangle.</span></span> <span data-ttu-id="4289f-116">Se si disegna un rettangolo intorno a un elemento esistente nell'area di progettazione, il rettangolo non agirà da contenitore.</span><span class="sxs-lookup"><span data-stu-id="4289f-116">If you draw a rectangle around an item that already exists on the design surface, the rectangle will not act as its container.</span></span>  
  
### <a name="to-change-rectangle-properties-such-as-color-style-or-weight"></a><span data-ttu-id="4289f-117">Per modificare le proprietà del rettangolo, ad esempio colore, stile o spessore</span><span class="sxs-lookup"><span data-stu-id="4289f-117">To change rectangle properties such as color, style, or weight</span></span>  
  
1.  <span data-ttu-id="4289f-118">Selezionare il rettangolo, quindi fare clic sull'opzione del colore, dello stile o dello spessore della linea nella sezione **Bordo** della scheda Home.</span><span class="sxs-lookup"><span data-stu-id="4289f-118">Select the rectangle, and then click the line color, style, or weight options in the **Border** section of the Home tab.</span></span>  
  
2.  <span data-ttu-id="4289f-119">Fare clic sulla freccia accanto al pulsante **Bordo** per determinare i lati del rettangolo da modificare.</span><span class="sxs-lookup"><span data-stu-id="4289f-119">Click the arrow next to the **Border** button to determine which sides of the rectangle to change.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4289f-120">Se si imposta lo stile di linea su **doppio** e la lunghezza riga è 1 1/2 PT o più stretta, è possibile che la linea non venga visualizzata come doppia quando si esegue il report in Generatore report, Progettazione report o Gestione report.</span><span class="sxs-lookup"><span data-stu-id="4289f-120">If you set the line style to **Double** and the line width is 1 1/2 pt or narrower, the line may not appear double when you run the report in Report Builder, Report Designer, or Report Manager.</span></span> <span data-ttu-id="4289f-121">Risulterà doppia quando si esporta il report in altri formati, ad esempio Microsoft Word e Acrobat PDF.</span><span class="sxs-lookup"><span data-stu-id="4289f-121">It will appear double when you export the report to other formats such as Microsoft Word and Acrobat PDF.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4289f-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4289f-122">See Also</span></span>  
 <span data-ttu-id="4289f-123">[Rettangoli e linee &#40;Generatore report e SSRS&#41;](rectangles-and-lines-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="4289f-123">[Rectangles and Lines &#40;Report Builder and SSRS&#41;](rectangles-and-lines-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="4289f-124">Tipi di rendering &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="4289f-124">Rendering Behaviors &#40;Report Builder  and SSRS&#41;</span></span>](rendering-behaviors-report-builder-and-ssrs.md)  
  
  
