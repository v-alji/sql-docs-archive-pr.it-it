---
title: Esportazione in un file di immagine (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 020d8ea2-de07-4212-a2bb-2ed0df2c8db8
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: dc1c8539b39a99c252ebfcb0275b674f657de6c9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628494"
---
# <a name="exporting-to-an-image-file-report-builder-and-ssrs"></a><span data-ttu-id="e01a6-102">Esportazione in un file di immagine (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="e01a6-102">Exporting to an Image File (Report Builder and SSRS)</span></span>
  <span data-ttu-id="e01a6-103">L'estensione per il rendering delle immagini genera bitmap o metafile dei report.</span><span class="sxs-lookup"><span data-stu-id="e01a6-103">The Image rendering extension renders a report to a bitmap or metafile.</span></span> <span data-ttu-id="e01a6-104">Per impostazione predefinita, l'estensione per il rendering delle immagini crea un file TIFF del report, che può essere visualizzato in più pagine.</span><span class="sxs-lookup"><span data-stu-id="e01a6-104">By default, the Image rendering extension produces a TIFF file of the report, which can be viewed in multiple pages.</span></span> <span data-ttu-id="e01a6-105">Nel client l'immagine può essere visualizzata in un visualizzatore di immagini e stampata.</span><span class="sxs-lookup"><span data-stu-id="e01a6-105">When the client receives the image, it can be displayed in an image viewer and printed.</span></span> <span data-ttu-id="e01a6-106">In questo argomento vengono fornite informazioni specifiche sul renderer di immagini e vengono descritte le eccezioni alle regole di rendering.</span><span class="sxs-lookup"><span data-stu-id="e01a6-106">This topic provides Image renderer-specific information and describes exceptions to the rendering rules.</span></span>  
  
 <span data-ttu-id="e01a6-107">L'estensione per il rendering delle immagini consente di generare file in tutti i formati supportati da [!INCLUDE[ndptecgdiplus](../../includes/ndptecgdiplus-md.md)]: BMP, EMF, EMFPlus, GIF, JPEG, PNG e TIFF.</span><span class="sxs-lookup"><span data-stu-id="e01a6-107">The Image rendering extension can generate files in any of the formats supported by [!INCLUDE[ndptecgdiplus](../../includes/ndptecgdiplus-md.md)]: BMP, EMF, EMFPlus, GIF, JPEG, PNG, and TIFF.</span></span> <span data-ttu-id="e01a6-108">Per il formato TIFF, il nome file del flusso primario è *NomeReport*.tif.</span><span class="sxs-lookup"><span data-stu-id="e01a6-108">For TIFF format, the file name of the primary stream is *ReportName*.tif.</span></span> <span data-ttu-id="e01a6-109">Per tutti gli altri formati, di cui viene eseguito il rendering come singola pagina per file, il nome file è *ReportName_Page.ext* , dove</span><span class="sxs-lookup"><span data-stu-id="e01a6-109">For all other formats, which render as a single page per file, the file name is *ReportName_Page.ext* where.</span></span> <span data-ttu-id="e01a6-110">*ext* è l'estensione di file per il formato scelto.</span><span class="sxs-lookup"><span data-stu-id="e01a6-110">*ext* is the file extension for the chosen format.</span></span> <span data-ttu-id="e01a6-111">Per produrre un file in un altro formato di immagine supportato, specificare una delle stringhe elencate in precedenza nell'impostazione **OutputFormatDeviceInfo** .</span><span class="sxs-lookup"><span data-stu-id="e01a6-111">To produce a file in another Image-supported format, specify any of the above listed strings in the **OutputFormatDeviceInfo** setting.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
##  <a name="supported-image-formats"></a><a name="SupportedImageFormats"></a> <span data-ttu-id="e01a6-112">Formati di immagine supportati</span><span class="sxs-lookup"><span data-stu-id="e01a6-112">Supported Image Formats</span></span>  
 <span data-ttu-id="e01a6-113">Nella tabella seguente sono illustrati l'estensione di file e il tipo MIME per ogni formato del renderer di immagini.</span><span class="sxs-lookup"><span data-stu-id="e01a6-113">The following table shows the file extension and MimeType for each Image renderer format.</span></span>  
  
|<span data-ttu-id="e01a6-114">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="e01a6-114">**Type**</span></span>|<span data-ttu-id="e01a6-115">**Estensione**</span><span class="sxs-lookup"><span data-stu-id="e01a6-115">**Extension**</span></span>|<span data-ttu-id="e01a6-116">**MIMEType**</span><span class="sxs-lookup"><span data-stu-id="e01a6-116">**MIMEType**</span></span>|  
|--------------|-------------------|------------------|  
|<span data-ttu-id="e01a6-117">BMP</span><span class="sxs-lookup"><span data-stu-id="e01a6-117">BMP</span></span>|<span data-ttu-id="e01a6-118">bmp</span><span class="sxs-lookup"><span data-stu-id="e01a6-118">bmp</span></span>|<span data-ttu-id="e01a6-119">image/bmp</span><span class="sxs-lookup"><span data-stu-id="e01a6-119">image/bmp</span></span>|  
|<span data-ttu-id="e01a6-120">GIF</span><span class="sxs-lookup"><span data-stu-id="e01a6-120">GIF</span></span>|<span data-ttu-id="e01a6-121">GIF</span><span class="sxs-lookup"><span data-stu-id="e01a6-121">gif</span></span>|<span data-ttu-id="e01a6-122">image/gif</span><span class="sxs-lookup"><span data-stu-id="e01a6-122">image/gif</span></span>|  
|<span data-ttu-id="e01a6-123">JPEG</span><span class="sxs-lookup"><span data-stu-id="e01a6-123">JPEG</span></span>|<span data-ttu-id="e01a6-124">jpeg</span><span class="sxs-lookup"><span data-stu-id="e01a6-124">jpeg</span></span>|<span data-ttu-id="e01a6-125">image/jpeg</span><span class="sxs-lookup"><span data-stu-id="e01a6-125">image/jpeg</span></span>|  
|<span data-ttu-id="e01a6-126">PNG</span><span class="sxs-lookup"><span data-stu-id="e01a6-126">PNG</span></span>|<span data-ttu-id="e01a6-127">png</span><span class="sxs-lookup"><span data-stu-id="e01a6-127">png</span></span>|<span data-ttu-id="e01a6-128">image/png</span><span class="sxs-lookup"><span data-stu-id="e01a6-128">image/png</span></span>|  
|<span data-ttu-id="e01a6-129">TIFF</span><span class="sxs-lookup"><span data-stu-id="e01a6-129">TIFF</span></span>|<span data-ttu-id="e01a6-130">tif</span><span class="sxs-lookup"><span data-stu-id="e01a6-130">tif</span></span>|<span data-ttu-id="e01a6-131">image/tiff</span><span class="sxs-lookup"><span data-stu-id="e01a6-131">image/tiff</span></span>|  
|<span data-ttu-id="e01a6-132">EMF</span><span class="sxs-lookup"><span data-stu-id="e01a6-132">EMF</span></span>|<span data-ttu-id="e01a6-133">EMF</span><span class="sxs-lookup"><span data-stu-id="e01a6-133">emf</span></span>|<span data-ttu-id="e01a6-134">image/emf</span><span class="sxs-lookup"><span data-stu-id="e01a6-134">image/emf</span></span>|  
|<span data-ttu-id="e01a6-135">EMFPlus</span><span class="sxs-lookup"><span data-stu-id="e01a6-135">EMFPlus</span></span>|<span data-ttu-id="e01a6-136">EMF</span><span class="sxs-lookup"><span data-stu-id="e01a6-136">emf</span></span>|<span data-ttu-id="e01a6-137">image/emf</span><span class="sxs-lookup"><span data-stu-id="e01a6-137">image/emf</span></span>|  
  
  
##  <a name="rendering-multiple-pages"></a><a name="RenderingMultiplePages"></a> <span data-ttu-id="e01a6-138">Rendering di più pagine</span><span class="sxs-lookup"><span data-stu-id="e01a6-138">Rendering Multiple Pages</span></span>  
 <span data-ttu-id="e01a6-139">L'unico formato che supporta documenti a più pagine in un unico file è TIFF.</span><span class="sxs-lookup"><span data-stu-id="e01a6-139">TIFF is the only format that supports multiple page documents in a single file.</span></span> <span data-ttu-id="e01a6-140">Altri formati, ad esempio JPG o PNG, generano una pagina alla volta e richiedono una chiamata distinta all'estensione per il rendering per ogni pagina.</span><span class="sxs-lookup"><span data-stu-id="e01a6-140">Other formats, such as JPG or PNG, output one page at a time and require a separate call to the rendering extension for each page.</span></span>  
  
  
##  <a name="interactivity"></a><a name="Interactivity"></a><span data-ttu-id="e01a6-141">Interattività</span><span class="sxs-lookup"><span data-stu-id="e01a6-141">Interactivity</span></span>  
 <span data-ttu-id="e01a6-142">L'interattività non è supportata in alcun formato di immagine generato da questo renderer.</span><span class="sxs-lookup"><span data-stu-id="e01a6-142">Interactivity is not supported in any Image formats generated by this renderer.</span></span> <span data-ttu-id="e01a6-143">Non viene eseguito il rendering dei seguenti elementi interattivi:</span><span class="sxs-lookup"><span data-stu-id="e01a6-143">The following interactive elements are not rendered:</span></span>  
  
-   <span data-ttu-id="e01a6-144">Collegamenti ipertestuali</span><span class="sxs-lookup"><span data-stu-id="e01a6-144">Hyperlinks</span></span>  
  
-   <span data-ttu-id="e01a6-145">Elementi visualizzati o nascosti</span><span class="sxs-lookup"><span data-stu-id="e01a6-145">Show or Hide</span></span>  
  
-   <span data-ttu-id="e01a6-146">Mappa documento</span><span class="sxs-lookup"><span data-stu-id="e01a6-146">Document Map</span></span>  
  
-   <span data-ttu-id="e01a6-147">Collegamenti drill-through o click-through</span><span class="sxs-lookup"><span data-stu-id="e01a6-147">Drillthrough or clickthrough links</span></span>  
  
-   <span data-ttu-id="e01a6-148">Ordinamento dell'utente finale</span><span class="sxs-lookup"><span data-stu-id="e01a6-148">End user sort</span></span>  
  
-   <span data-ttu-id="e01a6-149">Intestazioni fisse</span><span class="sxs-lookup"><span data-stu-id="e01a6-149">Fixed headers</span></span>  
  
-   <span data-ttu-id="e01a6-150">Segnalibri</span><span class="sxs-lookup"><span data-stu-id="e01a6-150">Bookmarks</span></span>  
  
  
##  <a name="device-information-settings"></a><a name="DeviceInfo"></a><span data-ttu-id="e01a6-151">Impostazioni relative alle informazioni sul dispositivo</span><span class="sxs-lookup"><span data-stu-id="e01a6-151">Device Information Settings</span></span>  
 <span data-ttu-id="e01a6-152">È possibile modificare alcune impostazioni predefinite per questo renderer modificando le impostazioni relative alle informazioni sul dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e01a6-152">You can change some default settings for this renderer by changing the device information settings.</span></span> <span data-ttu-id="e01a6-153">Per ulteriori informazioni, vedere [Image Device Information Settings](../image-device-information-settings.md).</span><span class="sxs-lookup"><span data-stu-id="e01a6-153">For more information, see [Image Device Information Settings](../image-device-information-settings.md).</span></span>  
  
  
## <a name="see-also"></a><span data-ttu-id="e01a6-154">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e01a6-154">See Also</span></span>  
 <span data-ttu-id="e01a6-155">[Paginazione in Reporting Services &#40;Generatore report e SSRS&#41;](../report-design/pagination-in-reporting-services-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e01a6-155">[Pagination in Reporting Services &#40;Report Builder  and SSRS&#41;](../report-design/pagination-in-reporting-services-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="e01a6-156">[Comportamenti di rendering &#40;Generatore report e SSRS&#41;](../report-design/rendering-behaviors-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e01a6-156">[Rendering Behaviors &#40;Report Builder  and SSRS&#41;](../report-design/rendering-behaviors-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="e01a6-157">[Funzionalità interattiva per estensioni per il rendering di report diverse &#40;Generatore report e SSRS&#41;](interactive-functionality-different-report-rendering-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="e01a6-157">[Interactive Functionality for Different Report Rendering Extensions &#40;Report Builder and SSRS&#41;](interactive-functionality-different-report-rendering-extensions.md) </span></span>  
 <span data-ttu-id="e01a6-158">[Rendering degli elementi del report &#40;Generatore report e SSRS&#41;](../report-design/rendering-report-items-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e01a6-158">[Rendering Report Items &#40;Report Builder and SSRS&#41;](../report-design/rendering-report-items-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="e01a6-159">Tabelle, matrici ed elenchi &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="e01a6-159">Tables, Matrices, and Lists &#40;Report Builder and SSRS&#41;</span></span>](../report-design/create-invoices-and-forms-with-lists-report-builder-and-ssrs.md)  
  
  
