---
title: Finestra di dialogo riempimento (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.reportbody.fill.f1
- "10065"
- "10501"
- sql12.rtp.rptdesigner.shared.filldv.f1
- sql12.rtp.rptdesigner.rectangleproperties.fill.f1
- "10064"
- sql12.rtp.rptdesigner.textboxproperties.fill.f1
- "10124"
ms.assetid: 93a91d02-d558-4a0e-8d17-3fdf21e208d3
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: ae7f2b05d4d108c77f1dcae9ce7fefe5073e2522
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629213"
---
# <a name="fill-dialog-box-report-builder-and-ssrs"></a><span data-ttu-id="9d5f7-102">Finestra di dialogo Riempimento (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="9d5f7-102">Fill Dialog Box (Report Builder and SSRS)</span></span>
  <span data-ttu-id="9d5f7-103">Nella scheda **Riempimento** è possibile specificare le opzioni relative al colore per lo sfondo di una o più celle in un'area dati o una casella di testo.</span><span class="sxs-lookup"><span data-stu-id="9d5f7-103">On the **Fill** tab, you can specify color options for the background of a single cell or multiple cells within a data region or a text box.</span></span>  
  
## <a name="options"></a><span data-ttu-id="9d5f7-104">Opzioni</span><span class="sxs-lookup"><span data-stu-id="9d5f7-104">Options</span></span>  
 <span data-ttu-id="9d5f7-105">**Colore riempimento**</span><span class="sxs-lookup"><span data-stu-id="9d5f7-105">**Fill Color**</span></span>  
 <span data-ttu-id="9d5f7-106">Fare clic sul pulsante del colore per selezionare un colore di riempimento per il rettangolo.</span><span class="sxs-lookup"><span data-stu-id="9d5f7-106">Click the color button to select a fill color for the rectangle.</span></span> <span data-ttu-id="9d5f7-107">Fare clic sul pulsante **Espressione**_(fx)_ per modificare l'espressione, che può essere un valore esadecimale per il colore RGB o uno dei nomi di colore predefiniti specificati nella finestra di dialogo **Espressione** .</span><span class="sxs-lookup"><span data-stu-id="9d5f7-107">Click the **Expression**_(fx)_ button to edit the expression, which can be a hexadecimal value for the RGB color or one of the predefined color names that are provided in the **Expression** dialog box.</span></span> <span data-ttu-id="9d5f7-108">Per visualizzare un elenco di colori predefiniti, selezionare **Web** nel riquadro **Elemento**.</span><span class="sxs-lookup"><span data-stu-id="9d5f7-108">To see a list of predefined colors, in the **Item** pane, select **Web**.</span></span> <span data-ttu-id="9d5f7-109">I nomi di colore elencati nel riquadro **Titolo** possono essere digitati nel riquadro di testo dell'espressione.</span><span class="sxs-lookup"><span data-stu-id="9d5f7-109">The color names listed in the **Title** pane can be typed into the expression text pane.</span></span> <span data-ttu-id="9d5f7-110">Quando si digita il nome del colore, non utilizzare un segno di uguale (=) o le virgolette ("").</span><span class="sxs-lookup"><span data-stu-id="9d5f7-110">Do not use an equal sign (=) or quotation marks ("") when typing the color name.</span></span>  
  
 <span data-ttu-id="9d5f7-111">**Selezionare l'origine dell'immagine**</span><span class="sxs-lookup"><span data-stu-id="9d5f7-111">**Select the image source**</span></span>  
 <span data-ttu-id="9d5f7-112">Indicare il percorso di archiviazione dell'immagine in modo da consentire al processore del report di visualizzarla durante il rendering del report.</span><span class="sxs-lookup"><span data-stu-id="9d5f7-112">Indicate where the image is stored so that when the report is rendered, the report processor can display it.</span></span>  
  
-   <span data-ttu-id="9d5f7-113">**Esterna** Scegliere questa opzione se si desidera che l'immagine continui ad essere disponibile come file su un server di report o un server Web.</span><span class="sxs-lookup"><span data-stu-id="9d5f7-113">**External** Choose this option when you want the image to continue to exist as a file on a report server or Web server.</span></span>  
  
-   <span data-ttu-id="9d5f7-114">**Incorporata** Scegliere questa opzione se si desidera incorporare l'immagine nel report.</span><span class="sxs-lookup"><span data-stu-id="9d5f7-114">**Embedded** Choose this option when you want to embed the image into the report.</span></span>  
  
-   <span data-ttu-id="9d5f7-115">**Database** Scegliere questa opzione se si desidera includere un nome di campo del database che rappresenti le immagini da includere nel report.</span><span class="sxs-lookup"><span data-stu-id="9d5f7-115">**Database** Choose this option when you want to include a database field name that represents the images that you want to include in your report.</span></span>  
  
 <span data-ttu-id="9d5f7-116">**Utilizzare questa immagine**</span><span class="sxs-lookup"><span data-stu-id="9d5f7-116">**Use this image**</span></span>  
 <span data-ttu-id="9d5f7-117">Questa opzione viene visualizzata quando si seleziona l'opzione **Incorporata** o **Esterna** .</span><span class="sxs-lookup"><span data-stu-id="9d5f7-117">This option appears when you select the **Embedded** or **External** option.</span></span>  
  
 <span data-ttu-id="9d5f7-118">Se si intende incorporare l'immagine, selezionare l'immagine da aggiungere al report nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="9d5f7-118">If you are embedding the image, choose the picture that you want to add to the report from the drop-down list.</span></span> <span data-ttu-id="9d5f7-119">Fare clic su **Importa** per aggiungere l'immagine all'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="9d5f7-119">Click **Import** to add the image to the drop-down list.</span></span> <span data-ttu-id="9d5f7-120">Se un'immagine è stata aggiunta al riquadro **Dati** , è possibile scegliere **Incorporata** e quindi selezionare l'immagine nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="9d5f7-120">If you added an image to the **Data** pane, you can select that image by choosing **Embedded** and then selecting the image from the drop-down list.</span></span>  
  
 <span data-ttu-id="9d5f7-121">Se si seleziona l'opzione **Esterna** , digitare l'URL dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="9d5f7-121">If you select the **External** option, type the URL of the image.</span></span> <span data-ttu-id="9d5f7-122">Per un report pubblicato in un server di report configurato per la modalità nativa, utilizzare un percorso completo o relativo (ad esempio, http:// *\<servername>* /images/image1.jpg).</span><span class="sxs-lookup"><span data-stu-id="9d5f7-122">For a report published to a report server configured for native mode, use a full or relative path (for example, http://*\<servername>*/images/image1.jpg).</span></span> <span data-ttu-id="9d5f7-123">Per un report pubblicato in un server di report configurato per la modalità integrata SharePoint, utilizzare un URL completo (ad esempio, http:// *\<SharePointservername>/\<site>* /Documents/images/image1.jpg).</span><span class="sxs-lookup"><span data-stu-id="9d5f7-123">For a report published to a report server configured in SharePoint integrated mode, use a fully qualified URL (for example, http://*\<SharePointservername>/\<site>*/Documents/images/image1.jpg).</span></span>  
  
 <span data-ttu-id="9d5f7-124">**Importa**</span><span class="sxs-lookup"><span data-stu-id="9d5f7-124">**Import**</span></span>  
 <span data-ttu-id="9d5f7-125">Questa opzione è disponibile quando si seleziona **Incorporata**.</span><span class="sxs-lookup"><span data-stu-id="9d5f7-125">Available when you select **Embedded**.</span></span> <span data-ttu-id="9d5f7-126">Fare clic su questa opzione per aggiungere un'immagine all'elenco a discesa **Use this image** (Usa questa immagine).</span><span class="sxs-lookup"><span data-stu-id="9d5f7-126">Click to add an image to the **Use this image** drop-down list.</span></span>  
  
 <span data-ttu-id="9d5f7-127">**Utilizzare questo campo**</span><span class="sxs-lookup"><span data-stu-id="9d5f7-127">**Use this field**</span></span>  
 <span data-ttu-id="9d5f7-128">Disponibile quando si seleziona **Database**.</span><span class="sxs-lookup"><span data-stu-id="9d5f7-128">Available when you select **Database**.</span></span> <span data-ttu-id="9d5f7-129">Selezionare il nome del campo.</span><span class="sxs-lookup"><span data-stu-id="9d5f7-129">Select the field name.</span></span>  
  
 <span data-ttu-id="9d5f7-130">**Utilizzare questo tipo MIME**</span><span class="sxs-lookup"><span data-stu-id="9d5f7-130">**Use this MIME type**</span></span>  
 <span data-ttu-id="9d5f7-131">Scegliere il formato appropriato delle immagini contenute nel database, ad esempio bmp, jpeg, gif, png o x-png.</span><span class="sxs-lookup"><span data-stu-id="9d5f7-131">Choose the appropriate format of the pictures contained in the database (for example, .bmp, .jpeg, .gif, .png, or .x-png).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d5f7-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9d5f7-132">See Also</span></span>  
 <span data-ttu-id="9d5f7-133">[Formattazione degli elementi del report &#40;Generatore report e SSRS&#41;](report-design/formatting-report-items-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="9d5f7-133">[Formatting Report Items &#40;Report Builder and SSRS&#41;](report-design/formatting-report-items-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="9d5f7-134">[Formattazione di testo e segnaposto &#40;Generatore report e SSRS&#41;](report-design/formatting-text-and-placeholders-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="9d5f7-134">[Formatting Text and Placeholders &#40;Report Builder and SSRS&#41;](report-design/formatting-text-and-placeholders-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="9d5f7-135">Immagini &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="9d5f7-135">Images &#40;Report Builder and SSRS&#41;</span></span>](report-design/images-report-builder-and-ssrs.md)  
  
  
