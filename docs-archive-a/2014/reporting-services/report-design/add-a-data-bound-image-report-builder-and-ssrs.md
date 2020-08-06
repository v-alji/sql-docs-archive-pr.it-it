---
title: Aggiungere un'immagine con associazione a dati (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: df4c38d4-bfcc-41c4-aa6d-952ca6fd7a2e
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: ea85bdcd6eab04ff51c879a9e790b6e12f73a771
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623808"
---
# <a name="add-a-data-bound-image-report-builder-and-ssrs"></a><span data-ttu-id="781ef-102">Aggiungere un'immagine con associazione a dati (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="781ef-102">Add a Data-Bound Image (Report Builder and SSRS)</span></span>
  <span data-ttu-id="781ef-103">Un report può includere un riferimento a un'immagine archiviata in un database.</span><span class="sxs-lookup"><span data-stu-id="781ef-103">A report can include a reference to an image that is stored in a database.</span></span> <span data-ttu-id="781ef-104">Tale immagine è nota come *immagine con associazione a dati*.</span><span class="sxs-lookup"><span data-stu-id="781ef-104">Such an image is known as a *data-bound image*.</span></span> <span data-ttu-id="781ef-105">Le immagini visualizzate insieme ai nomi di prodotti in un catalogo sono esempi di immagini con associazione a dati.</span><span class="sxs-lookup"><span data-stu-id="781ef-105">The pictures that appear alongside product names in a product list are examples of data-bound images.</span></span>  
  
 <span data-ttu-id="781ef-106">Per aggiungere un'immagine con associazione a dati a un'intestazione di pagina o un piè di pagina, è necessario eseguire ulteriori operazioni.</span><span class="sxs-lookup"><span data-stu-id="781ef-106">Adding a data-bound image to a page header or page footer requires additional steps.</span></span> <span data-ttu-id="781ef-107">Per altre informazioni, vedere [Intestazioni di pagina e piè di pagina &#40;Generatore report e SSRS&#41;](page-headers-and-footers-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="781ef-107">For more information, see [Page Headers and Footers &#40;Report Builder and SSRS&#41;](page-headers-and-footers-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-data-bound-image"></a><span data-ttu-id="781ef-108">Per aggiungere un'immagine con associazione a dati</span><span class="sxs-lookup"><span data-stu-id="781ef-108">To add a data-bound image</span></span>  
  
1.  <span data-ttu-id="781ef-109">Nella visualizzazione di progettazione report creare una tabella con una connessione all'origine dati e un set di dati con un campo contenente dati immagine binari.</span><span class="sxs-lookup"><span data-stu-id="781ef-109">In report design view, create a table with a data source connection and a dataset with a field that contains binary image data.</span></span> <span data-ttu-id="781ef-110">Per altre informazioni, vedere [Tabelle &#40;Generatore report e SSRS&#41;](tables-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="781ef-110">For more information, see [Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md).</span></span>  
  
2.  <span data-ttu-id="781ef-111">Inserire una colonna nella tabella.</span><span class="sxs-lookup"><span data-stu-id="781ef-111">Insert a column in your table.</span></span> <span data-ttu-id="781ef-112">Per altre informazioni, vedere [Inserire o eliminare una colonna &#40;Generatore report e SSRS&#41;](insert-or-delete-a-column-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="781ef-112">For more information, see [Insert or Delete a Column &#40;Report Builder and SSRS&#41;](insert-or-delete-a-column-report-builder-and-ssrs.md).</span></span>  
  
3.  <span data-ttu-id="781ef-113">Scegliere **Immagine** dal menu **Inserisci**, quindi fare clic nella riga di dati della nuova colonna.</span><span class="sxs-lookup"><span data-stu-id="781ef-113">On the **Insert** menu, click **Image**, and then click in the data row of the new column.</span></span>  
  
4.  <span data-ttu-id="781ef-114">Nella pagina Generale della finestra di dialogo **Proprietà immagine** digitare un nome nella casella di testo **Nome** o accettare il nome predefinito.</span><span class="sxs-lookup"><span data-stu-id="781ef-114">On the General page of the **Image Properties** dialog box, type a name in the **Name** text box or accept the default.</span></span>  
  
5.  <span data-ttu-id="781ef-115">(Facoltativo) Nella casella di testo **Descrizione comando** digitare il testo da visualizzare quando il puntatore del mouse viene posizionato nel report sottoposto a rendering per HTML.</span><span class="sxs-lookup"><span data-stu-id="781ef-115">(Optional) In the **Tooltip** text box, type text to display when the user hovers over the image in the report rendered for HTML.</span></span>  
  
6.  <span data-ttu-id="781ef-116">In **Selezionare l'origine dell'immagine**selezionare **Database**.</span><span class="sxs-lookup"><span data-stu-id="781ef-116">In **Select the image source**, select **Database**.</span></span>  
  
7.  <span data-ttu-id="781ef-117">In **Utilizzare questo campo**selezionare il campo che contiene le immagini nel report.</span><span class="sxs-lookup"><span data-stu-id="781ef-117">In **Use this Field**, select the field that contains images in your report.</span></span>  
  
8.  <span data-ttu-id="781ef-118">In **Utilizzare questo tipo MIME** selezionare il tipo MIME, o il formato di file, dell'immagine, ad esempio bmp.</span><span class="sxs-lookup"><span data-stu-id="781ef-118">In **Use this MIME type**, select the MIME type, or file format, of the image-for example, bmp.</span></span>  
  
9. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="781ef-119">Nell'area di progettazione del report verrà visualizzato un segnaposto dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="781ef-119">An image placeholder appears on the report design surface.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="781ef-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="781ef-120">See Also</span></span>  
 <span data-ttu-id="781ef-121">[Immagini &#40;Generatore report e SSRS&#41;](images-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="781ef-121">[Images &#40;Report Builder and SSRS&#41;](images-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="781ef-122">[Incorporare un'immagine in un report &#40;Generatore report e SSRS&#41;](embed-an-image-in-a-report-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="781ef-122">[Embed an Image in a Report &#40;Report Builder and SSRS&#41;](embed-an-image-in-a-report-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="781ef-123">[Aggiungere un'immagine esterna &#40;Generatore report e SSRS&#41;](add-an-external-image-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="781ef-123">[Add an External Image &#40;Report Builder and SSRS&#41;](add-an-external-image-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="781ef-124">Finestra di dialogo Proprietà immagine, Generale &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="781ef-124">Image Properties Dialog Box, General &#40;Report Builder and SSRS&#41;</span></span>](../image-properties-dialog-box-general-report-builder-and-ssrs.md)  
  
  
