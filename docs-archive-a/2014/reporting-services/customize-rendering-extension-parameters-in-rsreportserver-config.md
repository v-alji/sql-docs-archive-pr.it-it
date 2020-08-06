---
title: Personalizzare i parametri di estensione per il rendering in RSReportServer.config. | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- configuration options [Reporting Services]
- DeviceInfo settings
- rendering extensions [Reporting Services], overriding behaviors
- parameters [Reporting Services], report rendering
- overriding report rendering behavior
- extensions [Reporting Services], rendering
ms.assetid: 3bf7ab2b-70bb-41c8-acda-227994d15aed
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 35a01e12fa4016d03717b008e4241c3be5e55236
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725316"
---
# <a name="customize-rendering-extension-parameters-in-rsreportserverconfig"></a><span data-ttu-id="f5907-102">Personalizzare i parametri di estensione per il rendering in RSReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="f5907-102">Customize Rendering Extension Parameters in RSReportServer.Config</span></span>
  <span data-ttu-id="f5907-103">È possibile specificare i parametri di estensione per il rendering nel file di configurazione RSReportServer per sostituire il comportamento di rendering predefinito per i report in esecuzione in un server di report di [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f5907-103">You can specify rendering extension parameters in the RSReportServer configuration file to override default report rendering behavior for reports that run on a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] report server.</span></span> <span data-ttu-id="f5907-104">È possibile modificare i parametri di estensione per il rendering per ottenere gli obiettivi seguenti:</span><span class="sxs-lookup"><span data-stu-id="f5907-104">You can modify rendering extension parameters to achieve the following objectives:</span></span>  
  
-   <span data-ttu-id="f5907-105">Modificare il nome dell'estensione per il rendering nell'elenco Esporta sulla barra degli strumenti del report, cambiando, ad esempio, "Archivio Web" in "MHTML" oppure localizzare il nome in una lingua diversa.</span><span class="sxs-lookup"><span data-stu-id="f5907-105">Change how the rendering extension name appears in the Export list of the report toolbar (for example, to change "Web archive" to "MHTML"), or localize the name to a different language.</span></span>  
  
-   <span data-ttu-id="f5907-106">Creare più istanze della stessa estensione per il rendering, per supportare diverse opzioni di presentazione del report, ad esempio versioni con orientamento orizzontale e verticale dell'estensione per il rendering delle immagini.</span><span class="sxs-lookup"><span data-stu-id="f5907-106">Create multiple instances of the same rendering extension to support different report presentation options (for example, a portrait and landscape mode version of the Image rendering extension).</span></span>  
  
-   <span data-ttu-id="f5907-107">Modificare i parametri di estensione per il rendering predefiniti per utilizzare valori diversi. Il formato di output predefinito dell'estensione per il rendering delle immagini è, ad esempio, TIFF, ma è possibile modificare i parametri di estensione affinché venga utilizzato il formato EMF.</span><span class="sxs-lookup"><span data-stu-id="f5907-107">Change the default rendering extension parameters to use different values (for example, the Image rendering extension uses TIFF as the default output format; you can modify the extension parameters to use EMF instead).</span></span>  
  
 <span data-ttu-id="f5907-108">La modifica dei parametri di estensione per il rendering influisce solo sulle operazioni di rendering nel server di report.</span><span class="sxs-lookup"><span data-stu-id="f5907-108">Changing the rendering extension parameters only affects rendering operations on the report server.</span></span> <span data-ttu-id="f5907-109">Non è possibile sostituire le impostazioni dell'estensione per il rendering in un'anteprima del report in Progettazione report.</span><span class="sxs-lookup"><span data-stu-id="f5907-109">You cannot override rendering extension settings in report preview in Report Designer.</span></span>  
  
 <span data-ttu-id="f5907-110">La definizione dei parametri di estensione per il rendering nei file di configurazione influisce globalmente sulle estensioni per il rendering.</span><span class="sxs-lookup"><span data-stu-id="f5907-110">Specifying rendering extension parameters in the configuration files affects rendering extensions globally.</span></span> <span data-ttu-id="f5907-111">Le impostazioni nei file di configurazione sono utilizzate al posto dei valori predefiniti ogni volta che viene utilizzata un'estensione per il rendering specifica.</span><span class="sxs-lookup"><span data-stu-id="f5907-111">The settings in the configuration files are used in place of default values whenever a particular rendering extension is used.</span></span> <span data-ttu-id="f5907-112">Se si vuole impostare i parametri di estensione per il rendering per un'operazione di rendering o per un report specifico, è necessario specificare le informazioni sul dispositivo a livello di programmazione tramite il metodo <xref:ReportExecution2005.ReportExecutionService.Render%2A> o nell'URL di un report.</span><span class="sxs-lookup"><span data-stu-id="f5907-112">If you want to set rendering extension parameters for a specific report or render operation, you must specify device information programmatically using the <xref:ReportExecution2005.ReportExecutionService.Render%2A> method or by specifying device information settings on a report URL.</span></span> <span data-ttu-id="f5907-113">Per altre informazioni sulla definizione delle impostazioni relative alle informazioni sul dispositivo per un'operazione di rendering e per visualizzare l'elenco completo di tali impostazioni, vedere [Passaggio delle impostazioni relative alle informazioni sul dispositivo alle estensioni per il rendering](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md).</span><span class="sxs-lookup"><span data-stu-id="f5907-113">For more information about specifying device information settings for a render operation, and to view the complete list of device information settings, see [Passing Device Information Settings to Rendering Extensions](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md).</span></span>  
  
## <a name="finding-and-modifying-rsreportserverconfig"></a><span data-ttu-id="f5907-114">Individuazione e modifica del file RSReportServer.config</span><span class="sxs-lookup"><span data-stu-id="f5907-114">Finding and Modifying RSReportServer.config</span></span>  
 <span data-ttu-id="f5907-115">Le impostazioni di configurazione per i formati di output del report vengono specificate come parametri di estensione per il rendering nel file RSReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="f5907-115">Configuration settings for report output formats are specified as rendering extension parameters in the RSReportServer.config file.</span></span> <span data-ttu-id="f5907-116">Per specificare i parametri di estensione per il rendering nei file di configurazione, è necessario saper definire le strutture XML per l'impostazione dei parametri di rendering.</span><span class="sxs-lookup"><span data-stu-id="f5907-116">To specify rendering extension parameters in the configuration files, you must know how to define the XML structures that set rendering parameters.</span></span> <span data-ttu-id="f5907-117">È possibile modificare due strutture XML:</span><span class="sxs-lookup"><span data-stu-id="f5907-117">There are two XML structures that you can modify:</span></span>  
  
-   <span data-ttu-id="f5907-118">L'elemento `OverrideNames` definisce il nome visualizzato e la lingua dell'estensione per il rendering.</span><span class="sxs-lookup"><span data-stu-id="f5907-118">The `OverrideNames` element defines the display name and language of the rendering extension.</span></span>  
  
-   <span data-ttu-id="f5907-119">La struttura XML `DeviceInfo` definisce le impostazioni relative alle informazioni sul dispositivo utilizzate da un'estensione per il rendering.</span><span class="sxs-lookup"><span data-stu-id="f5907-119">The `DeviceInfo` XML structure defines the device information settings that are used by a rendering extension.</span></span> <span data-ttu-id="f5907-120">La maggior parte dei parametri di estensione per il rendering viene specificata come impostazioni relative alle informazioni sul dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f5907-120">Most rendering extension parameters are specified as device information settings.</span></span>  
  
 <span data-ttu-id="f5907-121">Per modificare il file, è possibile utilizzare un editor di testo.</span><span class="sxs-lookup"><span data-stu-id="f5907-121">You can use a text editor to modify the file.</span></span> <span data-ttu-id="f5907-122">Il file RSReportServer.config si trova nella cartella \Reporting Services\Report Server\Bin.</span><span class="sxs-lookup"><span data-stu-id="f5907-122">The RSReportServer.config file can be found in the \Reporting Services\Report Server\Bin folder.</span></span> <span data-ttu-id="f5907-123">Per altre informazioni su come modificare il file di configurazione, vedere [Modificare un file di configurazione di Reporting Services &#40;RSreportserver.config&#41;](report-server/modify-a-reporting-services-configuration-file-rsreportserver-config.md).</span><span class="sxs-lookup"><span data-stu-id="f5907-123">For more information about modifying configuration files, see [Modify a Reporting Services Configuration File &#40;RSreportserver.config&#41;](report-server/modify-a-reporting-services-configuration-file-rsreportserver-config.md).</span></span>  
  
## <a name="changing-the-display-name"></a><span data-ttu-id="f5907-124">Modifica del nome visualizzato</span><span class="sxs-lookup"><span data-stu-id="f5907-124">Changing the Display Name</span></span>  
 <span data-ttu-id="f5907-125">Il nome di un'estensione per il rendering viene visualizzato nell'elenco Esporta sulla barra degli strumenti del report.</span><span class="sxs-lookup"><span data-stu-id="f5907-125">The display name for a rendering extension appears in the Export list of the report toolbar.</span></span> <span data-ttu-id="f5907-126">Tra i nomi visualizzati predefiniti vi sono Archivio Web, File TIFF e File Acrobat (PDF).</span><span class="sxs-lookup"><span data-stu-id="f5907-126">Examples of default display names include Web archive, TIFF file, and Acrobat (PDF) file.</span></span> <span data-ttu-id="f5907-127">È possibile sostituire il nome visualizzato predefinito con un valore personalizzato specificando l'elemento `OverrideNames` nei file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="f5907-127">You can replace the default display name with a custom value by specifying the `OverrideNames` element in the configuration files.</span></span> <span data-ttu-id="f5907-128">Se si stanno definendo due istanze di un'unica estensione per il rendering, è inoltre possibile utilizzare l'elemento `OverrideNames` per distinguere ogni istanza nell'elenco Esporta.</span><span class="sxs-lookup"><span data-stu-id="f5907-128">In addition, if you are defining two instances of a single rendering extension, you can use the `OverrideNames` element to distinguish each instance in the Export list.</span></span>  
  
 <span data-ttu-id="f5907-129">Poiché i nomi visualizzati sono localizzati, se si sta sostituendo il nome visualizzato predefinito con un valore personalizzato, è necessario impostare l'attributo `Language`.</span><span class="sxs-lookup"><span data-stu-id="f5907-129">Because display names are localized, you must set the `Language` attribute if you are replacing the default display name with a custom value.</span></span> <span data-ttu-id="f5907-130">In caso contrario, eventuali nomi specificati verranno ignorati.</span><span class="sxs-lookup"><span data-stu-id="f5907-130">Otherwise, any name that you specify will be ignored.</span></span> <span data-ttu-id="f5907-131">La lingua impostata deve essere valida per il computer del server di report.</span><span class="sxs-lookup"><span data-stu-id="f5907-131">The language value that you set must be valid for the report server computer.</span></span> <span data-ttu-id="f5907-132">Se, ad esempio, il server di report è in esecuzione in un sistema operativo francese, è necessario specificare "fr-FR" come valore dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="f5907-132">For example, if the report server is running on a French operating system, you should specify "fr-FR" as the attribute value.</span></span>  
  
 <span data-ttu-id="f5907-133">Nell'esempio seguente viene illustrato come definire un nome personalizzato in un server di report inglese:</span><span class="sxs-lookup"><span data-stu-id="f5907-133">The following example illustrates how to provide a custom name on an English report server:</span></span>  
  
```  
<Extension Name="XML" Type="Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataReport,Microsoft.ReportingServices.DataRendering">  
   <OverrideNames>  
     <Name Language="en-US">My Custom Display Name for XML Rendering</Name>  
   </OverrideNames>  
</Extension>  
```  
  
## <a name="changing-device-information-settings"></a><span data-ttu-id="f5907-134">Modifica delle impostazioni relative alle informazioni sul dispositivo</span><span class="sxs-lookup"><span data-stu-id="f5907-134">Changing Device Information Settings</span></span>  
 <span data-ttu-id="f5907-135">Per modificare le impostazioni predefinite relative alle informazioni sul dispositivo utilizzate da un'estensione per il rendering già distribuita nel server di report, digitare la struttura XML `DeviceInfo` nei file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="f5907-135">To modify default device information settings that are used by a rendering extension that is already deployed on your report server, you must type the `DeviceInfo` XML structure into the configuration files.</span></span> <span data-ttu-id="f5907-136">Ogni estensione per il rendering supporta impostazioni relative alle informazioni sui dispositivi specifici per quella estensione.</span><span class="sxs-lookup"><span data-stu-id="f5907-136">Every rendering extension supports device information settings that are unique to that extension.</span></span> <span data-ttu-id="f5907-137">Per l'elenco completo delle impostazioni relative alle informazioni sul dispositivo, vedere [Passaggio delle impostazioni relative alle informazioni sul dispositivo alle estensioni per il rendering](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md).</span><span class="sxs-lookup"><span data-stu-id="f5907-137">To view the complete list of device information settings, see [Passing Device Information Settings to Rendering Extensions](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md).</span></span>  
  
 <span data-ttu-id="f5907-138">Nell'esempio seguente vengono illustrate la struttura XML e la sintassi per la modifica delle impostazioni predefinite dell'estensione per il rendering delle immagini:</span><span class="sxs-lookup"><span data-stu-id="f5907-138">The following example provides an illustration of the XML structure and syntax that modifies the default settings of the Image rendering extension:</span></span>  
  
```  
<Render>  
    <Extension Name="IMAGE (EMF)" Type="Microsoft.ReportingServices.Rendering.ImageRenderer.ImageRenderer,Microsoft.ReportingServices.ImageRendering">  
        <OverrideNames>  
            <Name Language="en-US">Image (EMF)</Name>  
        </OverrideNames>  
        <Configuration>  
            <DeviceInfo>  
                <ColorDepth>32</ColorDepth>  
                <DpiX>300</DpiX>  
                <DpiY>300</DpiY>  
                <OutputFormat>EMF</OutputFormat>  
            </DeviceInfo>  
        </Configuration>  
    </Extension>  
</Render>  
```  
  
## <a name="configuring-multiple-entries-for-a-rendering-extension"></a><span data-ttu-id="f5907-139">Configurazione di più voci per un'estensione per il rendering</span><span class="sxs-lookup"><span data-stu-id="f5907-139">Configuring Multiple Entries for a Rendering Extension</span></span>  
 <span data-ttu-id="f5907-140">È possibile creare più istanze della stessa estensione per il rendering, per supportare diverse opzioni di presentazione del report.</span><span class="sxs-lookup"><span data-stu-id="f5907-140">You can create multiple instances of the same rendering extension to support different report presentation options.</span></span> <span data-ttu-id="f5907-141">Per ogni istanza definita è possibile specificare una diversa combinazione di valori dei parametri.</span><span class="sxs-lookup"><span data-stu-id="f5907-141">Each instance that you define can have a different combination of parameter values.</span></span> <span data-ttu-id="f5907-142">Quando si definiscono nuove istanze di un'estensione per il rendering esistente, accertarsi di eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f5907-142">When defining new instances of an existing rendering extension, be sure to do the following:</span></span>  
  
-   <span data-ttu-id="f5907-143">Specificare un nome univoco per l'estensione.</span><span class="sxs-lookup"><span data-stu-id="f5907-143">Specify a unique name for the extension.</span></span>  
  
     <span data-ttu-id="f5907-144">L'attributo `Name` di ogni istanza deve avere un valore univoco.</span><span class="sxs-lookup"><span data-stu-id="f5907-144">Each instance must have a unique value for the `Name` attribute.</span></span> <span data-ttu-id="f5907-145">Nell'esempio seguente vengono utilizzati i nomi "IMAGE (EMF Landscape)" e "IMAGE (EMF Portrait)" per distinguere tra le due istanze.</span><span class="sxs-lookup"><span data-stu-id="f5907-145">The following example uses the names "IMAGE (EMF Landscape)" and "IMAGE (EMF Portrait)" to distinguish between the two instances.</span></span>  
  
     <span data-ttu-id="f5907-146">Fare attenzione quando si modifica il nome di un'estensione per il rendering già distribuita.</span><span class="sxs-lookup"><span data-stu-id="f5907-146">Use caution when changing the name of a rendering extension that is already deployed.</span></span> <span data-ttu-id="f5907-147">Gli sviluppatori che specificano estensioni per il rendering a livello di programmazione utilizzano i nomi delle estensioni per identificare l'istanza da utilizzare per un'operazione di rendering specifica.</span><span class="sxs-lookup"><span data-stu-id="f5907-147">Developers who specify rendering extensions programmatically use the extension name to identify which instance to use for a particular render operation.</span></span> <span data-ttu-id="f5907-148">Se nel server di report sono in esecuzione applicazioni di [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] personalizzate, verificare che lo sviluppatore sia informato se si modifica il nome di un'estensione esistente o se ne aggiunge uno nuovo.</span><span class="sxs-lookup"><span data-stu-id="f5907-148">If you are running custom [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] applications on your report server, make sure that the developer knows if you modify an existing extension name or add a new one.</span></span>  
  
-   <span data-ttu-id="f5907-149">Specificare un nome visualizzato univoco per consentire agli utenti di comprendere le differenze per ogni formato di output.</span><span class="sxs-lookup"><span data-stu-id="f5907-149">Specify a unique display name so that users can understand the differences for each output format.</span></span>  
  
     <span data-ttu-id="f5907-150">Se si configurano più versioni della stessa estensione, è possibile assegnare a ogni versione un nome univoco specificando un valore per `OverrideNames`.</span><span class="sxs-lookup"><span data-stu-id="f5907-150">If you are configuring multiple versions of the same extension, you can give each version a unique name by providing a value for `OverrideNames`.</span></span> <span data-ttu-id="f5907-151">In caso contrario, nell'elenco relativo alle opzioni di esportazione sulla barra degli strumenti del report tutte le versioni dell'estensione avranno lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="f5907-151">Otherwise, all versions of the extension will appear to have the same name in the Export options list on the report toolbar.</span></span>  
  
 <span data-ttu-id="f5907-152">Nell'esempio seguente viene illustrato come utilizzare l'estensione per il rendering delle immagini predefinita, che prevede la creazione di output in formato TIFF, per generare un output in formato EMF con orientamento verticale insieme a una seconda istanza per l'output di report in formato EMF con orientamento orizzontale.</span><span class="sxs-lookup"><span data-stu-id="f5907-152">The following example illustrates how to use the default Image rendering extension (which produces TIFF output) to output EMF in Portrait mode alongside a second instance that outputs reports in EMF in Landscape mode.</span></span> <span data-ttu-id="f5907-153">Si noti che ogni estensione ha un nome univoco.</span><span class="sxs-lookup"><span data-stu-id="f5907-153">Notice that each extension name is unique.</span></span> <span data-ttu-id="f5907-154">Quando si testa questo esempio, ricordarsi di scegliere report che non contengano funzionalità interattive, ad esempio opzioni per mostrare o nascondere gli elementi, matrici o collegamenti drill-through, in quanto le funzionalità di questo tipo non funzionano con l'estensione per il rendering delle immagini.</span><span class="sxs-lookup"><span data-stu-id="f5907-154">When testing this example, remember to choose reports that do not contain interactive features such as show/hide options, matrices, or drillthrough links (interactive features do not work in the Image rendering extension):</span></span>  
  
```  
<Render>  
    <Extension Name="IMAGE (EMF Landscape)" Type="Microsoft.ReportingServices.Rendering.ImageRenderer.ImageRenderer,Microsoft.ReportingServices.ImageRendering">  
        <OverrideNames>  
            <Name Language="en-US">EMF in Landscape Mode</Name>  
        </OverrideNames>  
        <Configuration>  
            <DeviceInfo>  
                <OutputFormat>EMF</OutputFormat>  
                <PageHeight>8.5in</PageHeight>  
                <PageWidth>11in</PageWidth>  
            </DeviceInfo>  
        </Configuration>  
    </Extension>  
    <Extension Name="IMAGE (EMF Portrait)" Type="Microsoft.ReportingServices.Rendering.ImageRenderer.ImageRenderer,Microsoft.ReportingServices.ImageRendering">  
        <OverrideNames>  
            <Name Language="en-US">EMF in Portait Mode</Name>  
        </OverrideNames>  
        <Configuration>  
            <DeviceInfo>  
                <OutputFormat>EMF</OutputFormat>  
                <PageHeight>11in</PageHeight>  
                <PageWidth>8.5in</PageWidth>  
            </DeviceInfo>  
        </Configuration>  
    </Extension>  
</Render>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f5907-155">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f5907-155">See Also</span></span>  
 <span data-ttu-id="f5907-156">[File di configurazione RSReportServer](report-server/rsreportserver-config-configuration-file.md) </span><span class="sxs-lookup"><span data-stu-id="f5907-156">[RSReportServer Configuration File](report-server/rsreportserver-config-configuration-file.md) </span></span>  
 <span data-ttu-id="f5907-157">[RSReportDesigner - file di configurazione](report-server/rsreportdesigner-configuration-file.md) </span><span class="sxs-lookup"><span data-stu-id="f5907-157">[RSReportDesigner Configuration File](report-server/rsreportdesigner-configuration-file.md) </span></span>  
 <span data-ttu-id="f5907-158">[Impostazioni relative alle informazioni sul dispositivo CSV](csv-device-information-settings.md) </span><span class="sxs-lookup"><span data-stu-id="f5907-158">[CSV Device Information Settings](csv-device-information-settings.md) </span></span>  
 <span data-ttu-id="f5907-159">[Impostazioni relative alle informazioni sul dispositivo Excel](excel-device-information-settings.md) </span><span class="sxs-lookup"><span data-stu-id="f5907-159">[Excel Device Information Settings](excel-device-information-settings.md) </span></span>  
 <span data-ttu-id="f5907-160">[Impostazioni relative alle informazioni sul dispositivo HTML](html-device-information-settings.md) </span><span class="sxs-lookup"><span data-stu-id="f5907-160">[HTML Device Information Settings](html-device-information-settings.md) </span></span>  
 <span data-ttu-id="f5907-161">[Impostazioni relative alle informazioni sul dispositivo immagine](image-device-information-settings.md) </span><span class="sxs-lookup"><span data-stu-id="f5907-161">[Image Device Information Settings](image-device-information-settings.md) </span></span>  
 <span data-ttu-id="f5907-162">[Impostazioni relative alle informazioni sul dispositivo MHTML](mhtml-device-information-settings.md) </span><span class="sxs-lookup"><span data-stu-id="f5907-162">[MHTML Device Information Settings](mhtml-device-information-settings.md) </span></span>  
 <span data-ttu-id="f5907-163">[Impostazioni relative alle informazioni sul dispositivo PDF](pdf-device-information-settings.md) </span><span class="sxs-lookup"><span data-stu-id="f5907-163">[PDF Device Information Settings](pdf-device-information-settings.md) </span></span>  
 [<span data-ttu-id="f5907-164">Impostazioni relative alle informazioni sul dispositivo XML</span><span class="sxs-lookup"><span data-stu-id="f5907-164">XML Device Information Settings</span></span>](xml-device-information-settings.md)  
  
  
