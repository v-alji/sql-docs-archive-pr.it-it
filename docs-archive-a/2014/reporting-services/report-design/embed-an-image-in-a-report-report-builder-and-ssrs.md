---
title: Incorporare un'immagine in un report (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.embeddedimages.f1
- "10060"
ms.assetid: aed77345-5eeb-41f0-96c9-db6b4a11ec6f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 6599092e0ef37dd9bbc15f4815c0315c77e7943b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711724"
---
# <a name="embed-an-image-in-a-report-report-builder-and-ssrs"></a><span data-ttu-id="54987-102">Incorporare un'immagine in un report (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="54987-102">Embed an Image in a Report (Report Builder and SSRS)</span></span>
  <span data-ttu-id="54987-103">Un report può includere un'immagine incorporata.</span><span class="sxs-lookup"><span data-stu-id="54987-103">A report can include an embedded image.</span></span> <span data-ttu-id="54987-104">L'incorporamento di un'immagine assicura che l'immagine sia sempre disponibile per il report, ma può influire sulle dimensioni della definizione del report, ovvero il file che definisce il report.</span><span class="sxs-lookup"><span data-stu-id="54987-104">Embedding an image ensures that the image is always available to a report, but can affect the size of the report definition, the file that defines the report.</span></span> <span data-ttu-id="54987-105">Le immagini incorporate in un report sono elencate nel riquadro dei dati del report.</span><span class="sxs-lookup"><span data-stu-id="54987-105">The images embedded in a report are listed in the Report Data pane.</span></span>  
  
 <span data-ttu-id="54987-106">È necessario incorporare un'immagine nella definizione del report prima di aggiungerla all'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="54987-106">You might want to embed an image in the report definition before adding the image to the design surface.</span></span> <span data-ttu-id="54987-107">Per altre informazioni, vedere [Aggiungere un'immagine di sfondo &#40;Generatore report e SSRS&#41;](add-a-background-image-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="54987-107">For more information, see [Add a Background Image &#40;Report Builder and SSRS&#41;](add-a-background-image-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-embed-an-image-in-a-report"></a><span data-ttu-id="54987-108">Per incorporare un'immagine in un report</span><span class="sxs-lookup"><span data-stu-id="54987-108">To embed an image in a report</span></span>  
  
1.  <span data-ttu-id="54987-109">Nella visualizzazione di progettazione report fare clic su **Immagine** nella scheda **Inserisci**.</span><span class="sxs-lookup"><span data-stu-id="54987-109">In report design view, on the **Insert** tab, click **Image**.</span></span>  
  
2.  <span data-ttu-id="54987-110">Nell'area di progettazione fare clic su una casella, quindi trascinarla fino a raggiungere le dimensioni desiderate per l'immagine.</span><span class="sxs-lookup"><span data-stu-id="54987-110">On the design surface, click and then drag a box to the desired size of the image.</span></span>  
  
3.  <span data-ttu-id="54987-111">Nella pagina **Generale** della finestra di dialogo **Proprietà immagine** digitare un nome nella casella di testo **Nome** o accettare il nome predefinito.</span><span class="sxs-lookup"><span data-stu-id="54987-111">In the **General** page of the **Image Properties** dialog box, type a name in the **Name** text box or accept the default.</span></span>  
  
4.  <span data-ttu-id="54987-112">(Facoltativo) Nella casella di testo **Descrizione comando** digitare il testo da visualizzare quando il puntatore del mouse viene posizionato sull'immagine nel report visualizzabile.</span><span class="sxs-lookup"><span data-stu-id="54987-112">(Optional) In the **ToolTip** text box, type the text that you want to appear when the user hovers over the image in the rendered report.</span></span>  
  
5.  <span data-ttu-id="54987-113">In **Selezionare l'origine dell'immagine**selezionare **Incorporata**.</span><span class="sxs-lookup"><span data-stu-id="54987-113">In **Select the image source**, select **Embedded**.</span></span>  
  
6.  <span data-ttu-id="54987-114">Fare clic sul pulsante **Importa** accanto alla casella di testo **Utilizzare questa immagine** .</span><span class="sxs-lookup"><span data-stu-id="54987-114">Click the **Import** button next to the **Use this image** text box</span></span>  
  
7.  <span data-ttu-id="54987-115">In **Tipo file**selezionare il tipo di file di immagine, passare al file e quindi fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="54987-115">In **Files of type**, select the image file type, navigate to the file, and then click **Open**.</span></span>  
  
8.  <span data-ttu-id="54987-116">Nella finestra di dialogo **Proprietà immagine** scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="54987-116">In the **Image Properties** dialog box, click **OK**.</span></span>  
  
     <span data-ttu-id="54987-117">L'immagine viene visualizzata nella casella disegnata nell'area di progettazione mentre il file viene visualizzato sotto la cartella Immagini nel riquadro dei dati del report.</span><span class="sxs-lookup"><span data-stu-id="54987-117">The image is displayed in the box you drew on the design surface, and the file is displayed under the Images folder in the Report Data pane.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="54987-118">Il tipo MIME, ad esempio bmp, viene derivato automaticamente al momento dell'importazione dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="54987-118">The MIME type (for example, bmp) is derived automatically when the image is imported.</span></span> <span data-ttu-id="54987-119">Per modificare il tipo MIME, vedere la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="54987-119">To change the MIME type, see the next procedure.</span></span>  
  
### <a name="optional-to-change-the-mime-type-of-an-imported-image"></a><span data-ttu-id="54987-120">(Facoltativo) Per modificare il tipo MIME di un'immagine importata</span><span class="sxs-lookup"><span data-stu-id="54987-120">(optional) To change the MIME type of an imported image</span></span>  
  
1.  <span data-ttu-id="54987-121">Aprire il report in visualizzazione Progettazione.</span><span class="sxs-lookup"><span data-stu-id="54987-121">Open the report in Design view.</span></span>  
  
2.  <span data-ttu-id="54987-122">Selezionare l'immagine nell'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="54987-122">Select the image on the design surface.</span></span> <span data-ttu-id="54987-123">Nel riquadro **Proprietà** verranno visualizzate le proprietà dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="54987-123">The **Properties** pane displays the image properties.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="54987-124">Se il riquadro Proprietà non è visualizzato, fare clic su **Proprietà** nella scheda **Visualizza**.</span><span class="sxs-lookup"><span data-stu-id="54987-124">If the Properties pane is not visible, on the **View** tab, click **Properties**.</span></span>  
  
3.  <span data-ttu-id="54987-125">Fare clic nella casella di testo accanto alla proprietà **MIMEType** e selezionare un nuovo tipo MIME nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="54987-125">Click in the text box next to the **MIMEType** property and select a new MIME type from the drop-down list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54987-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="54987-126">See Also</span></span>  
 <span data-ttu-id="54987-127">[Immagini &#40;Generatore report e SSRS&#41;](images-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="54987-127">[Images &#40;Report Builder and SSRS&#41;](images-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="54987-128">[Aggiungere un'immagine con associazione a dati &#40;Generatore report e SSRS&#41;](add-a-data-bound-image-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="54987-128">[Add a Data-Bound Image &#40;Report Builder and SSRS&#41;](add-a-data-bound-image-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="54987-129">Finestra di dialogo Proprietà immagine, Generale &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="54987-129">Image Properties Dialog Box, General &#40;Report Builder and SSRS&#41;</span></span>](../image-properties-dialog-box-general-report-builder-and-ssrs.md)  
  
  
