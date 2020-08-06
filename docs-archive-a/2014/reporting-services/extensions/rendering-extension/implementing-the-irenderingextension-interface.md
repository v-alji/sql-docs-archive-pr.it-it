---
title: Implementazione dell'interfaccia IRenderingExtension | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- IRenderingExtension interface
- rendering extensions [Reporting Services], IRenderingExtension interface
ms.assetid: 74b2f2b7-6796-42da-ab7d-b05891ad4001
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f57c4aa41ccfed165b69581cbf3917e4dfbb4960
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629236"
---
# <a name="implementing-the-irenderingextension-interface"></a><span data-ttu-id="85259-102">Implementazione dell'interfaccia IRenderingExtension</span><span class="sxs-lookup"><span data-stu-id="85259-102">Implementing the IRenderingExtension Interface</span></span>
  <span data-ttu-id="85259-103">L'estensione per il rendering prende i risultati da una definizione del report combinata con i dati effettivi ed eseguire il rendering dei dati risultanti in un formato che sia possibile utilizzare.</span><span class="sxs-lookup"><span data-stu-id="85259-103">The rendering extension takes the results from a report definition that is combined with the actual data and renders the resulting data to a format that is useable.</span></span> <span data-ttu-id="85259-104">La trasformazione dei dati combinati e della formattazione viene eseguita tramite una classe CLR (Common Language Runtime) che implementa <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension>.</span><span class="sxs-lookup"><span data-stu-id="85259-104">The transformation of the combined data and formatting is done by using a common language runtime (CLR) class that implements <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension>.</span></span> <span data-ttu-id="85259-105">Ciò consente di trasformare il modello a oggetti in un formato di output che può essere utilizzato da un visualizzatore, una stampante o un'altra destinazione di output.</span><span class="sxs-lookup"><span data-stu-id="85259-105">This transforms the object model into an output format that is consumable by a viewer, printer, or other output target.</span></span>  
  
 <span data-ttu-id="85259-106"><xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension> dispone di tre metodi che devono essere codificati:</span><span class="sxs-lookup"><span data-stu-id="85259-106">The <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension> has three methods that must be coded:</span></span>  
  
-   <span data-ttu-id="85259-107"><xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.Render%2A>: consente di eseguire il rendering del report.</span><span class="sxs-lookup"><span data-stu-id="85259-107"><xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.Render%2A> - renders the report.</span></span>  
  
-   <span data-ttu-id="85259-108"><xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.RenderStream%2A>: consente di eseguire il rendering di un flusso specifico dal report.</span><span class="sxs-lookup"><span data-stu-id="85259-108"><xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.RenderStream%2A> - renders a specific stream from the report.</span></span>  
  
-   <span data-ttu-id="85259-109"><xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.GetRenderingResource%2A>: consente di ottenere informazioni aggiuntive, come icone, necessarie per il report.</span><span class="sxs-lookup"><span data-stu-id="85259-109"><xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.GetRenderingResource%2A> - gets additional information, such as icons, that are required for the report.</span></span>  
  
 <span data-ttu-id="85259-110">Nelle sezioni seguenti questi metodi vengono descritti in modo più dettagliato.</span><span class="sxs-lookup"><span data-stu-id="85259-110">The following sections discuss these methods in more detail.</span></span>  
  
## <a name="render-method"></a><span data-ttu-id="85259-111">Metodo Render</span><span class="sxs-lookup"><span data-stu-id="85259-111">Render Method</span></span>  
 <span data-ttu-id="85259-112">Il metodo <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.Render%2A> contiene argomenti che rappresentano gli oggetti seguenti:</span><span class="sxs-lookup"><span data-stu-id="85259-112">The <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.Render%2A> method contains arguments that represent the following objects:</span></span>  
  
-   <span data-ttu-id="85259-113">Il *report* di cui si desidera eseguire il rendering.</span><span class="sxs-lookup"><span data-stu-id="85259-113">The *report* that you want to render.</span></span> <span data-ttu-id="85259-114">Questo oggetto contiene proprietà, dati e informazioni sul layout per il report.</span><span class="sxs-lookup"><span data-stu-id="85259-114">This object contains properties, data, and layout information for the report.</span></span> <span data-ttu-id="85259-115">Il report costituisce la radice dell'albero del modello a oggetti del report.</span><span class="sxs-lookup"><span data-stu-id="85259-115">The report is the root of the report object model tree.</span></span>  
  
-   <span data-ttu-id="85259-116">L'oggetto *ServerParameters* contenente l'oggetto dizionario di stringhe con i parametri per il server di report, se disponibili.</span><span class="sxs-lookup"><span data-stu-id="85259-116">The *ServerParameters* that contain the string dictionary object, with the parameters for the report server, if any.</span></span>  
  
-   <span data-ttu-id="85259-117">Il parametro *deviceInfo* contenente le impostazioni dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="85259-117">The *deviceInfo* parameter that contain the device settings.</span></span> <span data-ttu-id="85259-118">Per altre informazioni, vedere [Passaggio delle impostazioni relative alle informazioni sul dispositivo alle estensioni per il rendering](../../report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md).</span><span class="sxs-lookup"><span data-stu-id="85259-118">For more information, see [Passing Device Information Settings to Rendering Extensions](../../report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md).</span></span>  
  
-   <span data-ttu-id="85259-119">Il parametro *clientCapabilities* contenente un oggetto dizionario <xref:System.Collections.Specialized.NameValueCollection> con informazioni sul client in cui viene eseguito il rendering.</span><span class="sxs-lookup"><span data-stu-id="85259-119">The *clientCapabilities* parameter that contains a <xref:System.Collections.Specialized.NameValueCollection> dictionary object that has information about the client to which you are rendering.</span></span>  
  
-   <span data-ttu-id="85259-120">L'oggetto *RenderProperties* contenente le informazioni sul risultato del rendering.</span><span class="sxs-lookup"><span data-stu-id="85259-120">The *RenderProperties* that contains information about the rendering result.</span></span>  
  
-   <span data-ttu-id="85259-121">*createAndRegisterStream* è una funzione di delegato che deve essere chiamata per ottenere un flusso in cui eseguire il rendering.</span><span class="sxs-lookup"><span data-stu-id="85259-121">The *createAndRegisterStream* is a delegate function to be called to get a stream to render into.</span></span>  
  
### <a name="deviceinfo-parameter"></a><span data-ttu-id="85259-122">Parametro deviceInfo</span><span class="sxs-lookup"><span data-stu-id="85259-122">deviceInfo Parameter</span></span>  
 <span data-ttu-id="85259-123">Il parametro *deviceInfo* contiene i parametri di rendering, non i parametri del report.</span><span class="sxs-lookup"><span data-stu-id="85259-123">The *deviceInfo* parameter contains rendering parameters, not report parameters.</span></span> <span data-ttu-id="85259-124">Questi parametri vengono passati all'estensione per il rendering.</span><span class="sxs-lookup"><span data-stu-id="85259-124">These rendering parameters are passed to the rendering extension.</span></span> <span data-ttu-id="85259-125">I valori di *deviceInfo* vengono convertiti in un oggetto <xref:System.Collections.Specialized.NameValueCollection> dal server di report.</span><span class="sxs-lookup"><span data-stu-id="85259-125">The *deviceInfo* values are converted into a <xref:System.Collections.Specialized.NameValueCollection> object by the report server.</span></span> <span data-ttu-id="85259-126">Gli elementi inclusi nel parametro *deviceInfo* vengono trattati come valori senza distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="85259-126">Items in the *deviceInfo* parameter are treated as case-insensitive values.</span></span> <span data-ttu-id="85259-127">Se la richiesta di rendering deriva da un accesso con URL, i parametri URL nel formato `rc:key=value` vengono convertiti in coppie chiave/valore nell'oggetto dizionario *deviceInfo*.</span><span class="sxs-lookup"><span data-stu-id="85259-127">If the render request came as a result of URL access, the URL parameters in the form `rc:key=value` are converted to key/value pairs in the *deviceInfo* dictionary object.</span></span> <span data-ttu-id="85259-128">Il codice di rilevamento del browser include anche gli elementi seguenti nel dizionario *clientCapabilities*: EcmaScriptVersion, JavaScript, MajorVersion, MinorVersion, Win32, Type e AcceptLanguage.</span><span class="sxs-lookup"><span data-stu-id="85259-128">The browser detection code also provides the following items in the *clientCapabilities* dictionary: EcmaScriptVersion, JavaScript, MajorVersion, MinorVersion, Win32, Type, and AcceptLanguage.</span></span> <span data-ttu-id="85259-129">Le coppie nome/valore incluse nel parametro *deviceInfo* che non vengono comprese dall'estensione per il rendering verranno ignorate.</span><span class="sxs-lookup"><span data-stu-id="85259-129">Any name/value pair in the *deviceInfo* parameter that is not understood by the rendering extension is ignored.</span></span> <span data-ttu-id="85259-130">Nell'esempio di codice seguente viene illustrato un metodo <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.GetRenderingResource%2A> di esempio per il recupero delle icone:</span><span class="sxs-lookup"><span data-stu-id="85259-130">The following code sample shows a sample <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.GetRenderingResource%2A> method that retrieves icons:</span></span>  
  
```csharp  
public void GetRenderingResource (CreateStream createStreamCallback, NameValueCollection deviceInfo)  
{  
    string[] iconTagValues = deviceInfo.GetValues("Icon");  
    if ((iconTagValues != null) && (iconTagValues.Length > 0) )  
    {  
        // Create a stream to output to.  
        Stream outputStream = createStreamCallback(m_iconResourceName, "gif", null, "image/gif", false);  
        // Get the GIF image for one of the buttons on the toolbar  
        Image requiredImage = (Image) m_resourcemanager.GetObject(m_iconResourceName  
        // Write the image to the output stream  
        requiredImage.Save(outputStream, requiredImage.RawFormat);  
    }  
    return;  
}  
```  
  
## <a name="renderstream-method"></a><span data-ttu-id="85259-131">Metodo RenderStream</span><span class="sxs-lookup"><span data-stu-id="85259-131">RenderStream Method</span></span>  
 <span data-ttu-id="85259-132">Il metodo <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.RenderStream%2A> consente di eseguire il rendering di un flusso specifico dal report.</span><span class="sxs-lookup"><span data-stu-id="85259-132">The <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.RenderStream%2A> method renders a particular stream from the report.</span></span> <span data-ttu-id="85259-133">Tutti i flussi vengono creati durante la chiamata a <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.Render%2A> iniziale, ma i flussi non vengono inizialmente restituiti al client.</span><span class="sxs-lookup"><span data-stu-id="85259-133">All streams are created during the initial <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.Render%2A> call, but the streams are not returned to the client initially.</span></span> <span data-ttu-id="85259-134">Questo metodo viene utilizzato per flussi secondari, ad esempio immagini nel rendering HTML o pagine aggiuntive di un'estensione per il rendering di più pagine, come Image/EMF.</span><span class="sxs-lookup"><span data-stu-id="85259-134">This method is used for secondary streams, such as images in HTML rendering, or additional pages of a multi-page rendering extension, such as Image/EMF.</span></span>  
  
## <a name="getrenderingresource-method"></a><span data-ttu-id="85259-135">Metodo GetRenderingResource</span><span class="sxs-lookup"><span data-stu-id="85259-135">GetRenderingResource Method</span></span>  
 <span data-ttu-id="85259-136">Il metodo <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.GetRenderingResource%2A> consente di recuperare le informazioni senza eseguire l'intero rendering del report.</span><span class="sxs-lookup"><span data-stu-id="85259-136">The <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.GetRenderingResource%2A> method retrieves the information without executing an entire rendering of the report.</span></span> <span data-ttu-id="85259-137">In alcuni casi, il report necessita di informazioni che non richiedono il rendering del report stesso.</span><span class="sxs-lookup"><span data-stu-id="85259-137">There are times when the report requires information that does not require the report itself to be rendered.</span></span> <span data-ttu-id="85259-138">Se, ad esempio, è necessaria l'icona associata all'estensione per il rendering, usare il parametro *deviceInfo* contenente il tag singolo **\<Icon>** .</span><span class="sxs-lookup"><span data-stu-id="85259-138">For example, if you need the icon associated with the rendering extension, use the *deviceInfo* parameter containing the single tag **\<Icon>**.</span></span> <span data-ttu-id="85259-139">In questi casi, è possibile utilizzare il metodo <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.GetRenderingResource%2A>.</span><span class="sxs-lookup"><span data-stu-id="85259-139">In these cases, you can use the <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.GetRenderingResource%2A> method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85259-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="85259-140">See Also</span></span>  
 <span data-ttu-id="85259-141">[Implementazione di un'estensione per il rendering](implementing-a-rendering-extension.md) </span><span class="sxs-lookup"><span data-stu-id="85259-141">[Implementing a Rendering Extension](implementing-a-rendering-extension.md) </span></span>  
 [<span data-ttu-id="85259-142">Panoramica delle estensioni per il rendering</span><span class="sxs-lookup"><span data-stu-id="85259-142">Rendering Extensions Overview</span></span>](rendering-extensions-overview.md)  
  
  
