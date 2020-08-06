---
title: Aggiungere un'immagine di sfondo (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: c777fefb-8695-44a7-b5cd-a18c587583f2
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d7bc15e1b063a73c463cdb1e7e99075af2a3dce9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723488"
---
# <a name="add-a-background-image-report-builder-and-ssrs"></a><span data-ttu-id="fe62c-102">Aggiungere un'immagine di sfondo (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="fe62c-102">Add a Background Image (Report Builder and SSRS)</span></span>
  <span data-ttu-id="fe62c-103">È possibile aggiungere un'immagine di sfondo a un elemento del report, ad esempio un rettangolo, una casella di testo, un elenco, una matrice, una tabella e ad alcune parti di un grafico, o a una sezione del report, ad esempio un'intestazione di pagina, un piè di pagina o il corpo del report.</span><span class="sxs-lookup"><span data-stu-id="fe62c-103">You can add a background image to a report item such as a rectangle, text box, list, matrix, table, and some parts of a chart, or a report section such as the page header, page footer, or report body.</span></span> <span data-ttu-id="fe62c-104">È possibile definire un'immagine di sfondo per qualsiasi elemento selezionato nell'area di progettazione per il quale la proprietà **BackgroundImage** sia visualizzata nel riquadro Proprietà.</span><span class="sxs-lookup"><span data-stu-id="fe62c-104">You can define a background image for any selected item on the report design surface that displays **BackgroundImage** in the Properties pane.</span></span> <span data-ttu-id="fe62c-105">Analogamente ad altre immagini, quella di sfondo può essere l'URL di un'immagine nel server di report, un'immagine da un campo del set di dati o un'immagine incorporata nella definizione del report.</span><span class="sxs-lookup"><span data-stu-id="fe62c-105">Like other images, the background image can be a URL to an image on the report server, an image from a dataset field, or an image embedded in the report definition.</span></span> <span data-ttu-id="fe62c-106">Per utilizzare un'immagine incorporata nel report, è necessario innanzitutto aggiungere l'immagine alla definizione del report prima di poterla aggiungere all'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="fe62c-106">To use an image embedded in the report, you must first add the image to the report definition before you can add the image to the design surface.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-embed-an-image-in-the-report-definition"></a><span data-ttu-id="fe62c-107">Per incorporare un'immagine nella definizione del report</span><span class="sxs-lookup"><span data-stu-id="fe62c-107">To embed an image in the report definition</span></span>  
  
1.  <span data-ttu-id="fe62c-108">Nel riquadro dei dati del report fare clic con il pulsante destro del mouse sul nodo **Immagini** , quindi scegliere **Aggiungi immagine**.</span><span class="sxs-lookup"><span data-stu-id="fe62c-108">In the Report Data pane, right-click the **Images** node, and then click **Add Image**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="fe62c-109">Se il riquadro dei dati del report non è visualizzato, scegliere **Dati report** dal menu **Visualizza**.</span><span class="sxs-lookup"><span data-stu-id="fe62c-109">If the Report Data pane is not visible, on the **View** tab, click **Report Data**.</span></span>  
  
2.  <span data-ttu-id="fe62c-110">Passare all'immagine da incorporare nella definizione del report, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="fe62c-110">Navigate to the image you want to embed in your report definition, and then click **OK**.</span></span>  
  
### <a name="to-add-a-background-image"></a><span data-ttu-id="fe62c-111">Per aggiungere un'immagine di sfondo</span><span class="sxs-lookup"><span data-stu-id="fe62c-111">To add a background image</span></span>  
  
1.  <span data-ttu-id="fe62c-112">Nella visualizzazione di progettazione report selezionare l'elemento del report a cui si desidera aggiungere un'immagine di sfondo.</span><span class="sxs-lookup"><span data-stu-id="fe62c-112">In report design view, select the report item to which you want to add a background image.</span></span>  
  
2.  <span data-ttu-id="fe62c-113">Se il riquadro Proprietà non è visualizzato, selezionare **Proprietà** nella scheda **Visualizza**.</span><span class="sxs-lookup"><span data-stu-id="fe62c-113">If the Properties pane is not visible, on the **View** tab, select **Properties**.</span></span>  
  
3.  <span data-ttu-id="fe62c-114">Nel riquadro Proprietà espandere la proprietà **BackgroundImage**, quindi eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="fe62c-114">In the Properties pane, expand **BackgroundImage**, and then do the following:</span></span>  
  
    -   <span data-ttu-id="fe62c-115">Per un'immagine incorporata:</span><span class="sxs-lookup"><span data-stu-id="fe62c-115">For an embedded image:</span></span>  
  
         <span data-ttu-id="fe62c-116">Impostare **Source** su **Embedded**.</span><span class="sxs-lookup"><span data-stu-id="fe62c-116">Set **Source** to **Embedded**.</span></span>  
  
         <span data-ttu-id="fe62c-117">Impostare **Value** sul nome di un'immagine incorporata nel report.</span><span class="sxs-lookup"><span data-stu-id="fe62c-117">Set **Value** to the name of an image that is embedded in the report.</span></span>  
  
    -   <span data-ttu-id="fe62c-118">Per un'immagine esterna:</span><span class="sxs-lookup"><span data-stu-id="fe62c-118">For an external image:</span></span>  
  
         <span data-ttu-id="fe62c-119">Impostare **Source** su **External**.</span><span class="sxs-lookup"><span data-stu-id="fe62c-119">Set **Source** to **External**.</span></span>  
  
         <span data-ttu-id="fe62c-120">Impostare **Value** su un percorso valido a un'immagine.</span><span class="sxs-lookup"><span data-stu-id="fe62c-120">Set **Value** to a valid path to an image.</span></span> <span data-ttu-id="fe62c-121">Tale percorso può essere su un server di report in modalità nativa o in modalità integrata SharePoint o può essere su qualsiasi altro sito Web.</span><span class="sxs-lookup"><span data-stu-id="fe62c-121">This can be on a report server in native mode or SharePoint integrated mode, or it can be on any other Web site.</span></span> <span data-ttu-id="fe62c-122">Per altre informazioni, vedere [Aggiungere un'immagine esterna &#40;Generatore report e SSRS&#41;](add-an-external-image-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="fe62c-122">For more information, see [Add an External Image &#40;Report Builder and SSRS&#41;](add-an-external-image-report-builder-and-ssrs.md).</span></span>  
  
    -   <span data-ttu-id="fe62c-123">Per un'immagine contenuta in un campo del database al quale è connesso l'elemento del report:</span><span class="sxs-lookup"><span data-stu-id="fe62c-123">For an image is that is contained in a field in the database to which the report item is connected:</span></span>  
  
         <span data-ttu-id="fe62c-124">Impostare **Source** su **Database**.</span><span class="sxs-lookup"><span data-stu-id="fe62c-124">Set **Source** to **Database**.</span></span>  
  
         <span data-ttu-id="fe62c-125">Impostare **Value** sul nome di un campo nel set di dati del report.</span><span class="sxs-lookup"><span data-stu-id="fe62c-125">Set **Value** to the name of a field in the report dataset.</span></span> <span data-ttu-id="fe62c-126">Per altre informazioni, vedere [Aggiungere un'immagine con associazione a dati &#40;Generatore report e SSRS&#41;](add-a-data-bound-image-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="fe62c-126">For more information, see [Add a Data-Bound Image &#40;Report Builder and SSRS&#41;](add-a-data-bound-image-report-builder-and-ssrs.md).</span></span>  
  
         <span data-ttu-id="fe62c-127">Per **MIMEType**o un formato di file, selezionare il tipo MIME appropriato per l'immagine, ad esempio bmp.</span><span class="sxs-lookup"><span data-stu-id="fe62c-127">For **MIMEType**, or file format, select the appropriate MIME type for the image-for example, .bmp.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="fe62c-128">Il valore MIMEType viene applicato solo se la proprietà **Source** è impostata su **Database**.</span><span class="sxs-lookup"><span data-stu-id="fe62c-128">MIMEType applies only if the **Source** property is set to **Database**.</span></span> <span data-ttu-id="fe62c-129">Se la proprietà **Source** è impostata su **External** o **Embedded**, il valore di **MIMEType** verrà ignorato.</span><span class="sxs-lookup"><span data-stu-id="fe62c-129">If the **Source** property is set to **External** or **Embedded**, the value of **MIMEType** is ignored.</span></span>  
  
    -   <span data-ttu-id="fe62c-130">Per **BackgroundRepeat**, selezionare un'espressione, **Default**, **Repeat**, **RepeatX**, **RepeatY**o **Clip**.</span><span class="sxs-lookup"><span data-stu-id="fe62c-130">For **BackgroundRepeat**, select an expression, **Default**, **Repeat**, **RepeatX**, or **RepeatY**, or **Clip**.</span></span>  
  
         <span data-ttu-id="fe62c-131">Per immagini di sfondo in un grafico **BackgroundRepeat** può essere impostato su **Default**, **Repeat**, **Fit**e **Clip**, ma non su **RepeatX** o **RepeatY**.</span><span class="sxs-lookup"><span data-stu-id="fe62c-131">For background images in a chart, **BackgroundRepeat** can be set to **Default**, **Repeat**, **Fit**, and **Clip**, but not **RepeatX** or **RepeatY**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe62c-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fe62c-132">See Also</span></span>  
 <span data-ttu-id="fe62c-133">[Immagini &#40;Generatore report e SSRS&#41;](images-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="fe62c-133">[Images &#40;Report Builder and SSRS&#41;](images-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="fe62c-134">Finestra di dialogo Proprietà immagine, Generale &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="fe62c-134">Image Properties Dialog Box, General &#40;Report Builder and SSRS&#41;</span></span>](../image-properties-dialog-box-general-report-builder-and-ssrs.md)  
  
  
