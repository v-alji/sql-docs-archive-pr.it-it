---
title: Aggiungere un'immagine esterna (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 81fd4a1f-79a9-4967-86d6-6229413c0995
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 8d0030c8f29b14b2c62048be306daa15948cd8d9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712732"
---
# <a name="add-an-external-image-report-builder-and-ssrs"></a><span data-ttu-id="64601-102">Aggiungere un'immagine esterna (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="64601-102">Add an External Image (Report Builder and SSRS)</span></span>
  <span data-ttu-id="64601-103">Le immagini esterne possono trovarsi in un server di report in modalità nativa o in modalità integrata SharePoint oppure in qualsiasi altro sito Web.</span><span class="sxs-lookup"><span data-stu-id="64601-103">External images can be on a report server in native mode or SharePoint integrated mode, or on any other Web site.</span></span> <span data-ttu-id="64601-104">Quando si includono immagini esterne nel report, è necessario verificare che l'immagine esista e che il lettore del report disponga delle autorizzazioni per accedervi.</span><span class="sxs-lookup"><span data-stu-id="64601-104">When you include external images in your report, you must verify that the image exists and that the report reader has permissions to access the image.</span></span> <span data-ttu-id="64601-105">Per altre informazioni, vedere [Immagini &#40;Generatore report e SSRS&#41;](images-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="64601-105">For more information, see [Images &#40;Report Builder and SSRS&#41;](images-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-an-external-image"></a><span data-ttu-id="64601-106">Per aggiungere un'immagine esterna</span><span class="sxs-lookup"><span data-stu-id="64601-106">To add an external image</span></span>  
  
1.  <span data-ttu-id="64601-107">Nella visualizzazione di progettazione report fare clic su **Immagine** nella scheda **Inserisci**.</span><span class="sxs-lookup"><span data-stu-id="64601-107">In report design view, on the **Insert** tab, click **Image**.</span></span>  
  
2.  <span data-ttu-id="64601-108">Nell'area di progettazione fare clic su una casella, quindi trascinarla fino a raggiungere le dimensioni desiderate per l'immagine.</span><span class="sxs-lookup"><span data-stu-id="64601-108">On the design surface, click and then drag a box to the desired size of the image.</span></span>  
  
3.  <span data-ttu-id="64601-109">Nella scheda **Generale** della finestra di dialogo **Proprietà immagine** digitare un nome nella casella di testo **Nome** o accettare quello predefinito.</span><span class="sxs-lookup"><span data-stu-id="64601-109">On the **General** tab of the **Image Properties** dialog box, type a name in the **Name** text box or accept the default.</span></span>  
  
4.  <span data-ttu-id="64601-110">(Facoltativo) Nella casella di testo **Descrizione comando** digitare il testo da visualizzare quando il puntatore del mouse viene posizionato sull'immagine in un report sottoposto a rendering per HTML.</span><span class="sxs-lookup"><span data-stu-id="64601-110">(Optional) In the **Tooltip** text box, type text to display when the user hovers over the image in a report rendered for HTML.</span></span>  
  
5.  <span data-ttu-id="64601-111">In **Selezionare l'origine dell'immagine**selezionare **Esterna**.</span><span class="sxs-lookup"><span data-stu-id="64601-111">In **Select the image source**, select **External**.</span></span>  
  
     <span data-ttu-id="64601-112">Per un'immagine in un server di report in modalità nativa, digitare il percorso relativo dell'immagine nella casella **Usare questa immagine**, ad esempio ../images/image1.jpg.</span><span class="sxs-lookup"><span data-stu-id="64601-112">For an image on a report server in native mode, type a relative path to the image in the **Use this image** box-for example, ../images/image1.jpg.</span></span>  
  
     <span data-ttu-id="64601-113">Per un'immagine in un server di report in modalità integrata SharePoint o in qualsiasi altro sito Web, digitare un URL completo dell'immagine nella casella **utilizzare questa immagine** , ad esempio http:// \<SharePointservername> / \<site> /Documents/images/image1.jpg.</span><span class="sxs-lookup"><span data-stu-id="64601-113">For an image on a report server in SharePoint integrated mode, or any other Web site, type a full URL to the image in the **Use this image** box-for example, http://\<SharePointservername>/\<site>/Documents/images/image1.jpg.</span></span>  
  
     <span data-ttu-id="64601-114">Per altre informazioni, vedere [Specifica di percorsi di elementi esterni &#40;Generatore report e SSRS&#41;](specifying-paths-to-external-items-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="64601-114">For more information, see [Specifying Paths to External Items &#40;Report Builder and SSRS&#41;](specifying-paths-to-external-items-report-builder-and-ssrs.md).</span></span>  
  
6.  <span data-ttu-id="64601-115">(Facoltativo) Fare clic su **Dimensioni**, **Visibilità**, **Azione**o **Bordo** per impostare ulteriori proprietà per l'elemento del report immagine.</span><span class="sxs-lookup"><span data-stu-id="64601-115">(Optional) Click **Size**, **Visibility**, **Action**, or **Border** to set additional properties for the image report item.</span></span>  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="64601-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="64601-116">See Also</span></span>  
 <span data-ttu-id="64601-117">[Incorporare un'immagine in un report &#40;Generatore report e SSRS&#41;](embed-an-image-in-a-report-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="64601-117">[Embed an Image in a Report &#40;Report Builder and SSRS&#41;](embed-an-image-in-a-report-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="64601-118">[Aggiungere un'immagine di sfondo &#40;Generatore report e SSRS&#41;](add-a-background-image-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="64601-118">[Add a Background Image &#40;Report Builder and SSRS&#41;](add-a-background-image-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="64601-119">Finestra di dialogo Proprietà immagine, Generale &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="64601-119">Image Properties Dialog Box, General &#40;Report Builder and SSRS&#41;</span></span>](../image-properties-dialog-box-general-report-builder-and-ssrs.md)  
  
  
