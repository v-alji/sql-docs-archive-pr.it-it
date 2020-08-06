---
title: Rettangoli e linee (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: d6226b0c-0398-4185-8565-96099876fc21
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 96b795c3edeabb938e836be3486e28e08737a8e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636561"
---
# <a name="rectangles-and-lines-report-builder-and-ssrs"></a><span data-ttu-id="82e43-102">Rettangoli e linee (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="82e43-102">Rectangles and Lines (Report Builder and SSRS)</span></span>
  <span data-ttu-id="82e43-103">È possibile utilizzare rettangoli e linee per creare effetti visivi all'interno di un report.</span><span class="sxs-lookup"><span data-stu-id="82e43-103">Rectangles and lines can create visual effects within a report.</span></span> <span data-ttu-id="82e43-104">Le proprietà di visualizzazione per questi elementi del report si impostano dalla sezione Bordo della scheda Home mentre per le altre proprietà si utilizza il riquadro Proprietà.</span><span class="sxs-lookup"><span data-stu-id="82e43-104">You can set display properties on these report items from the Border section of the Home tab, and set other properties by using the Properties pane.</span></span> <span data-ttu-id="82e43-105">A un rettangolo è possibile aggiungere caratteristiche come un colore di sfondo o un'immagine, una descrizione comando o un segnalibro.</span><span class="sxs-lookup"><span data-stu-id="82e43-105">You can add features like a background color or image, a tooltip, or a bookmark to a rectangle.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
##  <a name="rectangles-and-lines-as-report-parts"></a><a name="RectanglesLinesReportParts"></a> <span data-ttu-id="82e43-106">Rettangoli e linee come parti del report</span><span class="sxs-lookup"><span data-stu-id="82e43-106">Rectangles and Lines as Report Parts</span></span>  
 <span data-ttu-id="82e43-107">È possibile pubblicare rettangoli con gli elementi in essi contenuti separatamente dal report come parti del report.</span><span class="sxs-lookup"><span data-stu-id="82e43-107">You can publish rectangles with the items that they contain separately from the report as report parts.</span></span> [!INCLUDE[ssRBrptparts](../../includes/ssrbrptparts-md.md)]  
  
 <span data-ttu-id="82e43-108">Non è possibile pubblicare come parti del report gli elementi del report all'interno del rettangolo.</span><span class="sxs-lookup"><span data-stu-id="82e43-108">You cannot publish the report items within the rectangle as report parts.</span></span> <span data-ttu-id="82e43-109">Quando gli utenti aggiungono il rettangolo a un report, ottengono il rettangolo e gli elementi in esso contenuti.</span><span class="sxs-lookup"><span data-stu-id="82e43-109">When people add the rectangle to a report, they get the rectangle and the items it contains.</span></span>  
  

  
##  <a name="using-a-rectangle-as-a-container"></a><a name="RectangleAsContainer"></a><span data-ttu-id="82e43-110">Uso di un rettangolo come contenitore</span><span class="sxs-lookup"><span data-stu-id="82e43-110">Using a Rectangle as a Container</span></span>  
 <span data-ttu-id="82e43-111">È possibile utilizzare un rettangolo come contenitore per altri elementi.</span><span class="sxs-lookup"><span data-stu-id="82e43-111">You can use a rectangle as a container for other items.</span></span> <span data-ttu-id="82e43-112">Quando si sposta il rettangolo, vengono spostati anche gli elementi contenuti all'interno del rettangolo.</span><span class="sxs-lookup"><span data-stu-id="82e43-112">When you move the rectangle, the items that are contained within the rectangle move along with it.</span></span> <span data-ttu-id="82e43-113">Un elemento all'interno del rettangolo consente di visualizzare il nome del rettangolo nella proprietà **Parent** .</span><span class="sxs-lookup"><span data-stu-id="82e43-113">An item within the rectangle shows the name of the rectangle in its **Parent** property.</span></span> <span data-ttu-id="82e43-114">Per altre informazioni sull'uso di un rettangolo come contenitore, vedere [Aggiungere un rettangolo o un contenitore &#40;Generatore report e SSRS&#41;](add-a-rectangle-or-container-report-builder-and-ssrs.md) e [Visualizzare dati identici in una matrice e in un grafico &#40;Generatore report&#41;](display-the-same-data-on-a-matrix-and-a-chart-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="82e43-114">For more information about using a rectangle as a container, see [Add a Rectangle or Container &#40;Report Builder and SSRS&#41;](add-a-rectangle-or-container-report-builder-and-ssrs.md) and [Display the Same Data on a Matrix and a Chart &#40;Report Builder&#41;](display-the-same-data-on-a-matrix-and-a-chart-report-builder.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="82e43-115">Un rettangolo è solo un contenitore di elementi che in esso vengono creati o trascinati.</span><span class="sxs-lookup"><span data-stu-id="82e43-115">A rectangle is only a container for items that you either create in the rectangle or drag into the rectangle.</span></span> <span data-ttu-id="82e43-116">Se si disegna un rettangolo intorno a un elemento esistente nell'area di progettazione, il rettangolo non agirà da contenitore.</span><span class="sxs-lookup"><span data-stu-id="82e43-116">If you draw a rectangle around an item that already exists on the design surface, the rectangle will not act as its container.</span></span> <span data-ttu-id="82e43-117">non sarà elencato nella proprietà Parent dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="82e43-117">The rectangle will not be listed in the item's Parent property.</span></span>  
  
 <span data-ttu-id="82e43-118">Quando si utilizzano rettangoli per contenere elementi del report, occorre tenere in considerazione il modo in cui gli elementi verranno modificati nel loro insieme durante il rendering del report.</span><span class="sxs-lookup"><span data-stu-id="82e43-118">When using rectangles to contain report items, consider how the items will be affected as a whole during report rendering.</span></span> <span data-ttu-id="82e43-119">Gli elementi del report che contengono righe ripetute di dati, ad esempio le tabelle, possono espandersi per adattarsi ai dati restituiti da una query modificando di conseguenza il posizionamento degli altri elementi all'interno del rettangolo.</span><span class="sxs-lookup"><span data-stu-id="82e43-119">Report items that contain repeated rows of data (for example, tables) will expand to accommodate the data that is returned by a query, and this affects the positioning of other items in the rectangle.</span></span> <span data-ttu-id="82e43-120">Una tabella sposterà gli elementi verso il basso se sono posizionati al di sotto dell'area dati.</span><span class="sxs-lookup"><span data-stu-id="82e43-120">A table will push items down if they are positioned below the data region.</span></span> <span data-ttu-id="82e43-121">Per ancorare un elemento, è possibile posizionarlo all'interno di un rettangolo il cui bordo superiore si trovi più in alto rispetto al bordo inferiore della tabella.</span><span class="sxs-lookup"><span data-stu-id="82e43-121">To anchor an item in place, you can place the report item inside of a rectangle that has an upper edge above the lower edge of the table.</span></span> <span data-ttu-id="82e43-122">Per altre informazioni, vedere [Tipi di rendering  &#40;Generatore report e SSRS &#41;](rendering-behaviors-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="82e43-122">For more information, see [Rendering Behaviors &#40;Report Builder  and SSRS&#41;](rendering-behaviors-report-builder-and-ssrs.md).</span></span>  
  

  
##  <a name="adding-a-report-border"></a><a name="ReportBorder"></a> <span data-ttu-id="82e43-123">Aggiunta di un bordo al report</span><span class="sxs-lookup"><span data-stu-id="82e43-123">Adding a Report Border</span></span>  
 <span data-ttu-id="82e43-124">È possibile aggiungere un bordo a un report aggiungendo bordi alle intestazioni, ai piè di pagina e al corpo del report, senza inserire righe o rettangoli.</span><span class="sxs-lookup"><span data-stu-id="82e43-124">You can add a border to a report by adding borders to the headers, footers, and report body themselves, without adding lines or rectangles.</span></span> <span data-ttu-id="82e43-125">Per altre informazioni, vedere [Aggiungere un bordo a un report &#40;Generatore report e SSRS&#41;](add-a-border-to-a-report-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="82e43-125">For more information, see [Add a Border to a Report &#40;Report Builder and SSRS&#41;](add-a-border-to-a-report-report-builder-and-ssrs.md).</span></span>  
  

  
##  <a name="how-to-topics"></a><a name="HowTo"></a><span data-ttu-id="82e43-126">Procedure</span><span class="sxs-lookup"><span data-stu-id="82e43-126">How-To Topics</span></span>  
 [<span data-ttu-id="82e43-127">Aggiungere un bordo a un report &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="82e43-127">Add a Border to a Report &#40;Report Builder and SSRS&#41;</span></span>](add-a-border-to-a-report-report-builder-and-ssrs.md)  
  
 [<span data-ttu-id="82e43-128">Aggiungere un rettangolo o un contenitore &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="82e43-128">Add a Rectangle or Container &#40;Report Builder and SSRS&#41;</span></span>](add-a-rectangle-or-container-report-builder-and-ssrs.md)  
  
 [<span data-ttu-id="82e43-129">Aggiungere e modificare una linea &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="82e43-129">Add and Modify a Line &#40;Report Builder and SSRS&#41;</span></span>](add-and-modify-a-line-report-builder-and-ssrs.md)  
  
## <a name="see-also"></a><span data-ttu-id="82e43-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="82e43-130">See Also</span></span>  
 [<span data-ttu-id="82e43-131">Aggiungere un rettangolo o un contenitore &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="82e43-131">Add a Rectangle or Container &#40;Report Builder and SSRS&#41;</span></span>](add-a-rectangle-or-container-report-builder-and-ssrs.md)  
  
  
