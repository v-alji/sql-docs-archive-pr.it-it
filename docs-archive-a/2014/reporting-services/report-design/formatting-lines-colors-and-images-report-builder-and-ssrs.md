---
title: Formattazione di linee, colori e immagini (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.textboxproperties.border.f1
- "10502"
- "10094"
- sql12.rtp.rptdesigner.pictureproperties.border.f1
- "10063"
- sql12.rtp.rptdesigner.rectangleproperties.border.f1
- "10055"
- sql12.rtp.rptdesigner.subreportproperties.border.f1
- "10126"
- sql12.rtp.rptdesigner.shared.borderdv.f1
- "10066"
- sql12.rtp.rptdesigner.reportbody.border.f1
ms.assetid: 0f5f0d2a-9537-4152-b441-b40d7f04cf4c
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 681ff6b46f692804aef5c7cbbc16e5abe99dbb2d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711699"
---
# <a name="formatting-lines-colors-and-images-report-builder-and-ssrs"></a><span data-ttu-id="e2f9d-102">Formattazione di linee, colori e immagini (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="e2f9d-102">Formatting Lines, Colors, and Images (Report Builder and SSRS)</span></span>
  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="e2f9d-103">è possibile formattare linee, colori, aree dati, immagini e altri elementi del report.</span><span class="sxs-lookup"><span data-stu-id="e2f9d-103">gives you the ability to format lines, colors, data regions, images, and other report items.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="borders-lines-and-gridlines"></a><span data-ttu-id="e2f9d-104">Bordi, linee e griglie</span><span class="sxs-lookup"><span data-stu-id="e2f9d-104">Borders, Lines and Gridlines</span></span>  
 <span data-ttu-id="e2f9d-105">I bordi, le linee e le griglie consentono di unire visivamente gli elementi presenti nella pagina, aumentando in questo modo la leggibilità del contenuto del report.</span><span class="sxs-lookup"><span data-stu-id="e2f9d-105">Borders, lines, and gridlines can visually tie items together on the page and help your report readers easily read the contents of the report.</span></span> <span data-ttu-id="e2f9d-106">Usando gli stili predefiniti dei bordi, è possibile aggiungere rapidamente un bordo intorno a una casella di testo, a un gruppo di caselle di testo oppure a un'immagine.</span><span class="sxs-lookup"><span data-stu-id="e2f9d-106">Using the predefined border styles, you can quickly add a border around a text box, a group of text boxes, or an image.</span></span> <span data-ttu-id="e2f9d-107">È inoltre possibile modificare lo stile, la larghezza e il colore per i bordi, le linee e le griglie.</span><span class="sxs-lookup"><span data-stu-id="e2f9d-107">In addition, you can change the style, width, and color for the borders, lines, and gridlines.</span></span> <span data-ttu-id="e2f9d-108">I bordi vengono aggiunti intorno all'intero elemento selezionato o solamente intorno a uno dei lati dell'elemento, ad esempio intorno alla parte inferiore di una casella di testo.</span><span class="sxs-lookup"><span data-stu-id="e2f9d-108">Borders are added around the entire item selected or around a border along an edge of the item, for example, a border along the bottom of a text box.</span></span>  
  
 <span data-ttu-id="e2f9d-109">Per formattare bordi e griglie in una casella di testo, nel layout del report o intorno a un'immagine, usare la scheda **Bordo** della finestra di dialogo **Proprietà** dell'elemento di report.</span><span class="sxs-lookup"><span data-stu-id="e2f9d-109">To format borders and gridlines in a text box, report layout, or around an image, use the **Border** tab of the report item's **Properties** dialog box.</span></span> <span data-ttu-id="e2f9d-110">Se ad esempio si vuole aggiungere un bordo intorno a un'immagine, fare clic con il pulsante destro del mouse sull'immagine, quindi scegliere **Bordo** nella finestra di dialogo **Proprietà immagine**.</span><span class="sxs-lookup"><span data-stu-id="e2f9d-110">For example, if you want to add a border around an image, right-click the image and then in the **Image Properties** dialog box, click **Border**.</span></span>  
  
 <span data-ttu-id="e2f9d-111">Oltre ai bordi standard, ai grafici è possibile applicare bordi aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="e2f9d-111">In addition to the standard border frames, additional border frames can be applied to charts.</span></span> <span data-ttu-id="e2f9d-112">Per altre informazioni, vedere [Aggiungere un bordo o un frame a un grafico &#40;Generatore report e SSRS&#41;](add-a-border-frame-to-a-chart-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="e2f9d-112">For more information, see [Add a Border Frame to a Chart &#40;Report Builder and SSRS&#41;](add-a-border-frame-to-a-chart-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="e2f9d-113">È anche possibile aggiungere un bordo al report stesso.</span><span class="sxs-lookup"><span data-stu-id="e2f9d-113">You can also add a border to the report itself.</span></span> <span data-ttu-id="e2f9d-114">Per altre informazioni, vedere [Aggiungere un bordo a un report &#40;Generatore report e SSRS&#41;](add-a-border-to-a-report-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="e2f9d-114">For more information, see [Add a Border to a Report &#40;Report Builder and SSRS&#41;](add-a-border-to-a-report-report-builder-and-ssrs.md).</span></span>  
  
## <a name="applying-background-colors"></a><span data-ttu-id="e2f9d-115">Applicazione di colori di sfondo</span><span class="sxs-lookup"><span data-stu-id="e2f9d-115">Applying Background Colors</span></span>  
 <span data-ttu-id="e2f9d-116">È possibile impostare un colore a tinta unita come sfondo per l'intero report, una casella di testo del report o una cella oppure un gruppo di celle in un'area dati.</span><span class="sxs-lookup"><span data-stu-id="e2f9d-116">A solid color can be added to the background of the entire report, a text box within the report, or to a cell or group of cells within a data region.</span></span> <span data-ttu-id="e2f9d-117">Per impostazione predefinita, il colore di sfondo è il bianco. È tuttavia possibile selezionare un altro colore nella scheda **Riempimento** della finestra di dialogo **Proprietà** dell'elemento di report.</span><span class="sxs-lookup"><span data-stu-id="e2f9d-117">By default, the background color is white; however, you can select a color from the **Fill** tab of the report item's **Properties** dialog box.</span></span> <span data-ttu-id="e2f9d-118">Se ad esempio si vuole modificare il colore di sfondo di una casella di testo, fare clic con il pulsante destro del mouse sulla casella di testo, quindi scegliere **Proprietà casella di testo**.</span><span class="sxs-lookup"><span data-stu-id="e2f9d-118">For example, if you want to change the background color of a text box, right-click the text box and select **Text Box Properties**.</span></span> <span data-ttu-id="e2f9d-119">Fare clic su **Riempimento** , quindi selezionare il colore desiderato.</span><span class="sxs-lookup"><span data-stu-id="e2f9d-119">Click **Fill** and then select the color you want.</span></span> <span data-ttu-id="e2f9d-120">In questa finestra di dialogo è possibile selezionare un colore di sfondo per l'elemento selezionato oppure aggiungere un'immagine da visualizzare come sfondo.</span><span class="sxs-lookup"><span data-stu-id="e2f9d-120">In this dialog box, you can select a background color for the selected item or you can add an image that appears in the background.</span></span>  
  
 <span data-ttu-id="e2f9d-121">Quando si usa il grafico, è inoltre possibile specificare sfumature e stili del motivo per i colori di sfondo.</span><span class="sxs-lookup"><span data-stu-id="e2f9d-121">When you use the chart, you can also specify gradients and pattern styles for background colors.</span></span> <span data-ttu-id="e2f9d-122">Per altre informazioni, vedere [Formattazione di un grafico &#40;Generatore report e SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="e2f9d-122">For more information, see [Formatting a Chart &#40;Report Builder and SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md).</span></span>  
  
## <a name="using-images-as-formatting"></a><span data-ttu-id="e2f9d-123">Utilizzo di immagini per la formattazione</span><span class="sxs-lookup"><span data-stu-id="e2f9d-123">Using Images as Formatting</span></span>  
 <span data-ttu-id="e2f9d-124">A un'area dati è possibile aggiungere campi in cui sono contenute immagini.</span><span class="sxs-lookup"><span data-stu-id="e2f9d-124">Fields that contain images can be added to a data region.</span></span> <span data-ttu-id="e2f9d-125">Le immagini eventualmente incluse negli appositi campi vengono visualizzate in fase di esecuzione del report.</span><span class="sxs-lookup"><span data-stu-id="e2f9d-125">If you use an image field, the images appear in the report with the report is run.</span></span>  
  
 <span data-ttu-id="e2f9d-126">È anche possibile aggiungere immagini, quali logo, allo sfondo di un report, a un rettangolo, una casella di testo, una tabella, una matrice o parti di un grafico oppure al corpo o a sezioni della pagina di un report.</span><span class="sxs-lookup"><span data-stu-id="e2f9d-126">You can also add images such as logos to the background of your report or to a rectangle, text box, table, matrix, or some parts of a chart, or to the body and page sections of a report.</span></span> <span data-ttu-id="e2f9d-127">Per altre informazioni, vedere [Immagini &#40;Generatore report e SSRS&#41;](images-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="e2f9d-127">For more information, see [Images &#40;Report Builder and SSRS&#41;](images-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2f9d-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e2f9d-128">See Also</span></span>  
 <span data-ttu-id="e2f9d-129">[Formattazione di testo e segnaposto &#40;Generatore report e SSRS&#41;](formatting-text-and-placeholders-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e2f9d-129">[Formatting Text and Placeholders &#40;Report Builder and SSRS&#41;](formatting-text-and-placeholders-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="e2f9d-130">[Formattazione di numeri e date &#40;Generatore report e SSRS&#41;](formatting-numbers-and-dates-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e2f9d-130">[Formatting Numbers and Dates &#40;Report Builder and SSRS&#41;](formatting-numbers-and-dates-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="e2f9d-131">[Formattare il testo in una casella di testo &#40;Generatore report e SSRS&#41;](format-text-in-a-text-box-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e2f9d-131">[Format Text in a Text Box &#40;Report Builder and SSRS&#41;](format-text-in-a-text-box-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="e2f9d-132">Finestra di dialogo Riempimento &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="e2f9d-132">Fill Dialog Box &#40;Report Builder and SSRS&#41;</span></span>](../fill-dialog-box-report-builder-and-ssrs.md)  
  
  
