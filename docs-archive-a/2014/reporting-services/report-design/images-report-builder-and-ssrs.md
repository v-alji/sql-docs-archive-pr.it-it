---
title: Immagini (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: fcc2db5c-5c26-4607-ae2b-f65c80360536
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 4f0840a10cc1082ba8dc7912862f7cf34c64972d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713864"
---
# <a name="images-report-builder-and-ssrs"></a><span data-ttu-id="9f350-102">Immagini (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="9f350-102">Images (Report Builder and SSRS)</span></span>
  <span data-ttu-id="9f350-103">Un'immagine è un elemento del report in cui è incluso un riferimento a un'immagine incorporata nel report o archiviata in un database, nel server di report o in un'altra posizione nel Web.</span><span class="sxs-lookup"><span data-stu-id="9f350-103">An image is a report item that contains a reference to an image that is embedded in the report, stored in a database, stored on the report server, or stored elsewhere on the Web.</span></span> <span data-ttu-id="9f350-104">Un'immagine può essere rappresentata da un'immagine ripetuta con le righe di dati.</span><span class="sxs-lookup"><span data-stu-id="9f350-104">An image can be a picture that is repeated with rows of data.</span></span> <span data-ttu-id="9f350-105">Inoltre è possibile utilizzare un'immagine come sfondo per determinati elementi del report.</span><span class="sxs-lookup"><span data-stu-id="9f350-105">You can also use an image as a background for certain report items.</span></span>  
  
 <span data-ttu-id="9f350-106">È opportuno archiviare i loghi in un server dal momento che è possibile utilizzare lo stesso logo in più report.</span><span class="sxs-lookup"><span data-stu-id="9f350-106">Storing logos on a server is a good idea because you can use the same logo in many reports.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
##  <a name="comparing-external-embedded-and-data-bound-images"></a><a name="ComparingImages"></a> <span data-ttu-id="9f350-107">Confronto fra immagini esterne, incorporate e associate a dati</span><span class="sxs-lookup"><span data-stu-id="9f350-107">Comparing External, Embedded, and Data-Bound Images</span></span>  
 <span data-ttu-id="9f350-108">Quando in un report si utilizza un'immagine basata su server o un'altra immagine esterna, l'elemento immagine include un percorso che punta a un'immagine nel server di report o nel Web.</span><span class="sxs-lookup"><span data-stu-id="9f350-108">When you use a server-based or other external image in a report, the image item contains a path that points to an image on the report server or wherever it exists on the Web.</span></span> <span data-ttu-id="9f350-109">Quando si utilizza un'immagine incorporata, tuttavia, i dati dell'immagine vengono archiviati all'interno della definizione del report e non esistono come file separato.</span><span class="sxs-lookup"><span data-stu-id="9f350-109">When you use an embedded image, however, the image data is stored within the report definition and does not exist as a separate file.</span></span>  
  
 <span data-ttu-id="9f350-110">Le immagini basate su server sono particolarmente adatte per immagini statiche e logo condivisi tra più report o pagine Web.</span><span class="sxs-lookup"><span data-stu-id="9f350-110">Server-based images work well for logos and static pictures that are shared among several reports or Web pages.</span></span> <span data-ttu-id="9f350-111">Le immagini incorporate assicurano che le immagini siano sempre disponibili per il report, ma non è possibile condividerle.</span><span class="sxs-lookup"><span data-stu-id="9f350-111">Embedded images ensure that the images are always available to the report, but they cannot be shared.</span></span> <span data-ttu-id="9f350-112">Le dimensioni delle definizioni di report con immagini esterne sono inferiori a quelle delle definizioni con immagini incorporate.</span><span class="sxs-lookup"><span data-stu-id="9f350-112">Report definitions with external images are smaller than definitions with embedded images.</span></span>  
  
 <span data-ttu-id="9f350-113">È inoltre possibile visualizzare le immagini associate a dati da dati binari archiviati in un database.</span><span class="sxs-lookup"><span data-stu-id="9f350-113">Data-bound images can also be displayed from binary data stored in a database.</span></span> <span data-ttu-id="9f350-114">Le immagini visualizzate insieme ai nomi di prodotti in un catalogo, ad esempio, sono immagini di database.</span><span class="sxs-lookup"><span data-stu-id="9f350-114">For example, the pictures that appear alongside product names in a product list are database images.</span></span> <span data-ttu-id="9f350-115">Nell'immagine seguente, le immagini di biciclette vengono archiviate in un database e recuperate nel report per illustrare ogni prodotto.</span><span class="sxs-lookup"><span data-stu-id="9f350-115">In the following picture, the images of bicycles are stored in a database and retrieved in the report to illustrate each product.</span></span>  
  
 <span data-ttu-id="9f350-116">![rs_DataboundBikes](../media/rs-databoundbikes.gif "rs_DataboundBikes")</span><span class="sxs-lookup"><span data-stu-id="9f350-116">![rs_DataboundBikes](../media/rs-databoundbikes.gif "rs_DataboundBikes")</span></span>  
  

  
##  <a name="images-as-report-parts"></a><a name="ImagesReportParts"></a> <span data-ttu-id="9f350-117">Immagini come parti del report</span><span class="sxs-lookup"><span data-stu-id="9f350-117">Images as Report Parts</span></span>  
 <span data-ttu-id="9f350-118">È possibile salvare immagini separatamente da un report come parti del report.</span><span class="sxs-lookup"><span data-stu-id="9f350-118">You can save images separately from a report as report parts.</span></span> [!INCLUDE[ssRBrptparts](../../includes/ssrbrptparts-md.md)]  
  
 
  
##  <a name="embedding-images"></a><a name="EmbedImages"></a> <span data-ttu-id="9f350-119">Incorporamento di immagini</span><span class="sxs-lookup"><span data-stu-id="9f350-119">Embedding Images</span></span>  
 <span data-ttu-id="9f350-120">È possibile incorporare immagini in un report in modo che tutti i dati delle immagini vengano archiviati all'interno della definizione del report.</span><span class="sxs-lookup"><span data-stu-id="9f350-120">You can embed images in a report so that all image data is stored within the report definition.</span></span> <span data-ttu-id="9f350-121">Quando si incorpora un'immagine, all'immagine viene applicata la codifica MIME e viene archiviata come testo nella definizione del report.</span><span class="sxs-lookup"><span data-stu-id="9f350-121">When you embed an image, the image is MIME-encoded and stored as text in the report definition.</span></span> <span data-ttu-id="9f350-122">L'utilizzo di un'immagine incorporata assicura che l'immagine sia sempre disponibile per il report, ma comporta anche un aumento delle dimensioni della definizione del report.</span><span class="sxs-lookup"><span data-stu-id="9f350-122">Using an embedded image ensures that the image is always available to the report, but it also increases the size of the report definition.</span></span>  
  
 <span data-ttu-id="9f350-123">Per altre informazioni sull'incorporamento di un'immagine, vedere [Incorporare un'immagine in un report &#40;Generatore report e SSRS&#41;](embed-an-image-in-a-report-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="9f350-123">For more information about embedding an image, see [Embed an Image in a Report &#40;Report Builder and SSRS&#41;](embed-an-image-in-a-report-report-builder-and-ssrs.md).</span></span>  
  

  
##  <a name="external-images"></a><a name="ExternalImages"></a> <span data-ttu-id="9f350-124">Immagini esterne</span><span class="sxs-lookup"><span data-stu-id="9f350-124">External Images</span></span>  
 <span data-ttu-id="9f350-125">È possibile includere in un report immagini archiviate specificando l'URL dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="9f350-125">You can include stored images in a report by specifying a URL to the image.</span></span> <span data-ttu-id="9f350-126">Quando si utilizza un'immagine esterna, l'origine dell'immagine viene impostata su `External` e il valore per l'immagine corrisponde all'indirizzo URL o al percorso all'immagine.</span><span class="sxs-lookup"><span data-stu-id="9f350-126">When you use an external image in a report, the image source is set to `External` and the value for the image is the URL address or path to the image.</span></span>  
  
 <span data-ttu-id="9f350-127">Per altre informazioni, vedere [Specifica di percorsi di elementi esterni &#40;Generatore report e SSRS&#41;](specifying-paths-to-external-items-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="9f350-127">For more information, see [Specifying Paths to External Items &#40;Report Builder and SSRS&#41;](specifying-paths-to-external-items-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="9f350-128">Quando il report viene eseguito in Generatore report o Progettazione report, vengono utilizzate le credenziali dell'utente per visualizzare l'immagine.</span><span class="sxs-lookup"><span data-stu-id="9f350-128">When the report is run in Report Builder or Report Designer, preview uses the credentials of the user to display the image.</span></span> <span data-ttu-id="9f350-129">Quando il report viene eseguito sul server di report, è possibile che l'immagine nel report non venga visualizzata se le credenziali del server non sono sufficienti per accedere all'immagine.</span><span class="sxs-lookup"><span data-stu-id="9f350-129">When the report is run on the report server, the image in the report may not be displayed if the server credentials are not sufficient to access the image.</span></span> <span data-ttu-id="9f350-130">In tal caso, rivolgersi all'amministratore di sistema.</span><span class="sxs-lookup"><span data-stu-id="9f350-130">In that case, contact your system administrator.</span></span>  
  
 <span data-ttu-id="9f350-131">Per altre informazioni sull'aggiunta di un'immagine esterna a un report, vedere [Aggiungere un'immagine esterna &#40;Generatore report e SSRS&#41;](add-an-external-image-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="9f350-131">For more information about adding an external image to a report, see [Add an External Image &#40;Report Builder and SSRS&#41;](add-an-external-image-report-builder-and-ssrs.md).</span></span>  
  
 
  
##  <a name="background-images"></a><a name="BackgroundImages"></a> <span data-ttu-id="9f350-132">Immagini di sfondo</span><span class="sxs-lookup"><span data-stu-id="9f350-132">Background Images</span></span>  
 <span data-ttu-id="9f350-133">È possibile utilizzare un'immagine come sfondo nel corpo del report o in un rettangolo, casella di testo, elenco, matrice o tabella.</span><span class="sxs-lookup"><span data-stu-id="9f350-133">You can use an image as a background image in the body of the report or in a rectangle, text box, list, matrix, or table.</span></span> <span data-ttu-id="9f350-134">Le proprietà per un'immagine di sfondo sono simili a quelle di un'immagine.</span><span class="sxs-lookup"><span data-stu-id="9f350-134">A background image and an image have similar properties.</span></span> <span data-ttu-id="9f350-135">È inoltre possibile specificare come deve essere ripetuta l'immagine per riempire lo sfondo dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="9f350-135">You can also specify how the image is repeated to fill the background of the item.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9f350-136">Alcune estensioni per il rendering, ad esempio l'estensione per il rendering HTML, visualizzano l'immagine di sfondo del corpo del report nel corpo, nell'intestazione di pagina e nel piè di pagina.</span><span class="sxs-lookup"><span data-stu-id="9f350-136">Some rendering extensions, like the HTML rendering extension, render the background image for the report body in the body, the page header, and the page footer.</span></span> <span data-ttu-id="9f350-137">È possibile definire un'immagine di sfondo diversa per l'intestazione e il piè di pagina, ma se non si definisce alcuna immagine viene utilizzata l'immagine di sfondo del corpo.</span><span class="sxs-lookup"><span data-stu-id="9f350-137">You can define a separate background image for the page header and footer, but if no image is defined, the report uses the background image of the body.</span></span> <span data-ttu-id="9f350-138">Altre estensioni per il rendering, ad esempio l'estensione per il rendering delle immagini, non visualizzano l'immagine di sfondo del corpo nell'intestazione e nel piè di pagina.</span><span class="sxs-lookup"><span data-stu-id="9f350-138">Other rendering extensions, like the Image rendering extension, do not render the body background image in the page header and footer.</span></span>  
  
 <span data-ttu-id="9f350-139">Per altre informazioni sull'aggiunta di un'immagine di sfondo, vedere [Aggiungere un'immagine di sfondo &#40;Generatore report e SSRS&#41;](add-a-background-image-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="9f350-139">For more information about adding a background image, see [Add a Background Image &#40;Report Builder and SSRS&#41;](add-a-background-image-report-builder-and-ssrs.md).</span></span>  
  
 
  
##  <a name="data-bound-images"></a><a name="DataboundImages"></a> <span data-ttu-id="9f350-140">Immagini associate a dati</span><span class="sxs-lookup"><span data-stu-id="9f350-140">Data-bound Images</span></span>  
 <span data-ttu-id="9f350-141">È possibile aggiungere a un report immagini archiviate in un database.</span><span class="sxs-lookup"><span data-stu-id="9f350-141">You can add images that are stored in a database to your report.</span></span> <span data-ttu-id="9f350-142">L'elemento immagine del report utilizzato è identico a quello utilizzato per le immagini statiche, ma dispone di un set di proprietà che indica che l'immagine è archiviata in un database.</span><span class="sxs-lookup"><span data-stu-id="9f350-142">You use the same image report item as the one used for static images, but with a set of properties that indicate that the image is stored in a database.</span></span> <span data-ttu-id="9f350-143">Per visualizzare istruzioni sull'utilizzo di immagini con associazione a dati, vedere [Aggiungere un'immagine di sfondo &#40;Generatore report e SSRS&#41;](add-a-data-bound-image-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="9f350-143">To view instructions about working with data-bound images, see [Add a Data-Bound Image &#40;Report Builder and SSRS&#41;](add-a-data-bound-image-report-builder-and-ssrs.md).</span></span>  
  

  
##  <a name="how-to-topics"></a><a name="HowTo"></a> <span data-ttu-id="9f350-144">Procedure</span><span class="sxs-lookup"><span data-stu-id="9f350-144">How-to Topics</span></span>  
 [<span data-ttu-id="9f350-145">Aggiungere un'immagine esterna &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="9f350-145">Add an External Image &#40;Report Builder and SSRS&#41;</span></span>](add-an-external-image-report-builder-and-ssrs.md)  
  
 [<span data-ttu-id="9f350-146">Incorporare un'immagine in un report &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="9f350-146">Embed an Image in a Report &#40;Report Builder and SSRS&#41;</span></span>](embed-an-image-in-a-report-report-builder-and-ssrs.md)  
  
 [<span data-ttu-id="9f350-147">Aggiungere un'immagine di sfondo &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="9f350-147">Add a Background Image &#40;Report Builder and SSRS&#41;</span></span>](add-a-background-image-report-builder-and-ssrs.md)  
  
 [<span data-ttu-id="9f350-148">Aggiungere un'immagine di sfondo &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="9f350-148">Add a Data-Bound Image &#40;Report Builder and SSRS&#41;</span></span>](add-a-data-bound-image-report-builder-and-ssrs.md)  
  
  
  
## <a name="see-also"></a><span data-ttu-id="9f350-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9f350-149">See Also</span></span>  
 <span data-ttu-id="9f350-150">[Esportazione in un file di immagine &#40;Generatore report e SSRS&#41;](../report-builder/exporting-to-an-image-file-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="9f350-150">[Exporting to an Image File &#40;Report Builder and SSRS&#41;](../report-builder/exporting-to-an-image-file-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="9f350-151">Tipi di rendering &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="9f350-151">Rendering Behaviors &#40;Report Builder  and SSRS&#41;</span></span>](rendering-behaviors-report-builder-and-ssrs.md)  
  
  
