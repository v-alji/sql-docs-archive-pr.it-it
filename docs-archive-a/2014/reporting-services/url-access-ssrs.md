---
title: Accesso con URL (SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- URL access [Reporting Services]
- links [Reporting Services], URL access
- URL access [Reporting Services], about URL access
- parameters [Reporting Services], URL access
- report servers [Reporting Services], URL access
- hyperlinks [Reporting Services]
ms.assetid: 52c3f2a3-3d6d-4fee-9c46-83f366919398
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: bf44ea3c15c12f37eebf6e89faf4ff3affd64433
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627061"
---
# <a name="url-access-ssrs"></a><span data-ttu-id="a533a-102">Accesso con URL (SSRS)</span><span class="sxs-lookup"><span data-stu-id="a533a-102">URL Access (SSRS)</span></span>
  <span data-ttu-id="a533a-103">L'accesso tramite URL al server di report in SQL Server Reporting Services (SSRS) consente di inviare comandi a un server di report tramite una richiesta URL.</span><span class="sxs-lookup"><span data-stu-id="a533a-103">URL access of the report server in SQL Server Reporting Services (SSRS) enables you to send commands to a report server through a URL request.</span></span> <span data-ttu-id="a533a-104">Ad esempio, è possibile personalizzare il rendering di un report in un server di report in modalità nativa o in una raccolta di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a533a-104">For example, you can customize the rendering of a report on a native mode report server or in a SharePoint library.</span></span> <span data-ttu-id="a533a-105">È possibile che il report sia stato visualizzato utilizzando un set specifico di valori dei parametri del report o che sia stata visualizzata una particolare pagina di interesse nel report.</span><span class="sxs-lookup"><span data-stu-id="a533a-105">You may have viewed the report using a specific set of report parameter values, or you may have been viewing a particular page of interest in the report.</span></span> <span data-ttu-id="a533a-106">È possibile incapsulare queste informazioni nell'URL utilizzando i parametri di accesso tramite URL predefiniti.</span><span class="sxs-lookup"><span data-stu-id="a533a-106">You can encapsulate this information in the URL using predefined URL access parameters.</span></span> <span data-ttu-id="a533a-107">È possibile personalizzare ulteriormente il modo in cui il server di report elabora il report incorporando parametri relativi ai formati di rendering o all'aspetto del visualizzatore di report.</span><span class="sxs-lookup"><span data-stu-id="a533a-107">You can further customize how the report server processes the report by embedding parameters for rendering formats or for the look and feel of the report viewer.</span></span> <span data-ttu-id="a533a-108">Si può, quindi, incollare direttamente questo URL in un messaggio di posta elettronica o in una pagina Web per permettere ad altri di accedere al report con le stesse modalità tramite il browser.</span><span class="sxs-lookup"><span data-stu-id="a533a-108">You can then paste this URL directly into an email or Web page to let others to access your report in the same manner in the browser.</span></span>  
  
 <span data-ttu-id="a533a-109">Le altre azioni che si possono eseguire attraverso l'accesso tramite URL sono:</span><span class="sxs-lookup"><span data-stu-id="a533a-109">Other actions you can perform through URL access are:</span></span>  
  
-   <span data-ttu-id="a533a-110">Inviare comandi al visualizzatore HTML, ad esempio per l'impostazione dell'aspetto</span><span class="sxs-lookup"><span data-stu-id="a533a-110">Send commands to the HTML viewer, such as adjusting its look and feel</span></span>  
  
-   <span data-ttu-id="a533a-111">Elencare gli elementi figlio di una cartella del catalogo</span><span class="sxs-lookup"><span data-stu-id="a533a-111">List the children of a catalog folder</span></span>  
  
-   <span data-ttu-id="a533a-112">Recuperare la definizione XML di un elemento del catalogo</span><span class="sxs-lookup"><span data-stu-id="a533a-112">Retrieve the XML definition of a catalog item</span></span>  
  
-   <span data-ttu-id="a533a-113">Eseguire il rendering di uno snapshot della cronologia di un report specifico</span><span class="sxs-lookup"><span data-stu-id="a533a-113">Render a specific report history snapshot</span></span>  
  
-   <span data-ttu-id="a533a-114">Gestire le sessioni di report</span><span class="sxs-lookup"><span data-stu-id="a533a-114">Manage report sessions</span></span>  
  
 <span data-ttu-id="a533a-115">Per l'elenco completo dei comandi e delle impostazioni disponibili attraverso l'accesso tramite URL, vedere [Riferimento ai parametri di accesso con URL](url-access-parameter-reference.md).</span><span class="sxs-lookup"><span data-stu-id="a533a-115">For the complete list of commands and settings available through URL access, see [URL Access Parameter Reference](url-access-parameter-reference.md).</span></span>  
  
## <a name="url-access-concepts"></a><span data-ttu-id="a533a-116">Concetti di base relativi all'accesso tramite URL</span><span class="sxs-lookup"><span data-stu-id="a533a-116">URL Access Concepts</span></span>  
 <span data-ttu-id="a533a-117">Le richieste URL al server di report contengono parametri elaborati dal server di report.</span><span class="sxs-lookup"><span data-stu-id="a533a-117">URL requests to the report server contain parameters that are processed by the report server.</span></span> <span data-ttu-id="a533a-118">Il modo in cui le richieste URL vengono gestite dal server di report dipende dai parametri, dai prefissi di parametro e dai tipi di elementi inclusi nell'URL.</span><span class="sxs-lookup"><span data-stu-id="a533a-118">The way in which the report server handles URL requests depends on the parameters, parameter prefixes, and types of items that are included in the URL.</span></span> <span data-ttu-id="a533a-119">Gli URL del server di report sono conformi alle linee guida per la formattazione degli URL proposte dalla bozza di standard congiunta del World Wide Web Consortium W3C/IETF.</span><span class="sxs-lookup"><span data-stu-id="a533a-119">Report server URLs adhere to the URL formatting guidelines as proposed by the joint World Wide Web Consortium W3C/IETF draft standard.</span></span> [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] <span data-ttu-id="a533a-120">La funzionalità URL è compatibile con la maggior parte dei browser Internet o delle applicazioni che supportano il reindirizzamento URL standard.</span><span class="sxs-lookup"><span data-stu-id="a533a-120">URL functionality is compatible with most Internet browsers or applications that support standard URL addressing.</span></span>  
  
### <a name="url-access-syntax"></a><span data-ttu-id="a533a-121">Sintassi per l'accesso con URL</span><span class="sxs-lookup"><span data-stu-id="a533a-121">URL Access Syntax</span></span>  
 <span data-ttu-id="a533a-122">Le richieste URL possono contenere più parametri elencati in qualsiasi ordine.</span><span class="sxs-lookup"><span data-stu-id="a533a-122">URL requests can contain multiple parameters that are listed in any order.</span></span> <span data-ttu-id="a533a-123">I parametri sono separati da una e commerciale (&), mentre le coppie nome/valore sono separate da un segno di uguale (=).</span><span class="sxs-lookup"><span data-stu-id="a533a-123">Parameters are separated by an ampersand (&) and name/value pairs are separated by an equal sign (=).</span></span>  
  
```  
  
rswebserviceurl  
?  
reportpath  
      [&prefix:param=value]...n]  
  
```  
  
### <a name="syntax-description"></a><span data-ttu-id="a533a-124">Descrizione della sintassi</span><span class="sxs-lookup"><span data-stu-id="a533a-124">Syntax Description</span></span>  
 <span data-ttu-id="a533a-125">*rswebserviceurl*</span><span class="sxs-lookup"><span data-stu-id="a533a-125">*rswebserviceurl*</span></span>  
 <span data-ttu-id="a533a-126">URL del servizio Web del server di report.</span><span class="sxs-lookup"><span data-stu-id="a533a-126">The Web service URL of the report server.</span></span> <span data-ttu-id="a533a-127">Per la modalità nativa, è l'URL del servizio Web dell'istanza del server di report configurata in Gestione configurazione Reporting Services (vedere [Configurare gli URL del server di report &#40;Gestione configurazione SSRS&#41;](install-windows/configure-report-server-urls-ssrs-configuration-manager.md)).</span><span class="sxs-lookup"><span data-stu-id="a533a-127">For native mode, it is the Web service URL of the report server instance configured in Reporting Services Configuration Manager (see [Configure Report Server URLs  &#40;SSRS Configuration Manager&#41;](install-windows/configure-report-server-urls-ssrs-configuration-manager.md)).</span></span> <span data-ttu-id="a533a-128">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="a533a-128">For example:</span></span>  
  
```  
http://myrshost/reportserver  
https://machine.adventure-works.com/reportserver_MYNAMEDINSTANCE  
```  
  
 <span data-ttu-id="a533a-129">Per la modalità integrata SharePoint, è l'URL del proxy [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] a un sito di SharePoint integrato con [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a533a-129">For SharePoint integrated mode, it is the URL of the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] proxy at a SharePoint site integrated with [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="a533a-130">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="a533a-130">For example:</span></span>  
  
```  
http://myspsite/subsite/_vti_bin/reportserver  
```  
  
> [!TIP]  
>  <span data-ttu-id="a533a-131">È importante che nell'URL sia inclusa la sintassi proxy `_vti_bin` per indirizzare la richiesta tramite SharePoint e il proxy HTTP di [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a533a-131">It is important the URL include the `_vti_bin` proxy syntax to route the request through SharePoint and the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] HTTP proxy.</span></span> <span data-ttu-id="a533a-132">Tramite il proxy viene aggiunto del contesto alla richiesta HTTP. Questo contesto è necessario per garantire l'esecuzione corretta del report per i server di report in modalità SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a533a-132">The proxy adds some context to the HTTP request, context that is required to ensure proper execution of the report for SharePoint mode report servers.</span></span>  
  
 <span data-ttu-id="a533a-133">*pathinfo*</span><span class="sxs-lookup"><span data-stu-id="a533a-133">*pathinfo*</span></span>  
 <span data-ttu-id="a533a-134">Il nome di percorso relativo dell'elemento nel database del server di report in modalità nativa o l'URL completo dell'elemento in un catalogo di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a533a-134">The relative path name of the item in the native mode report server database, or the fully qualified URL of the item in a SharePoint catalog.</span></span>  
  
 <span data-ttu-id="a533a-135">Il percorso dell'elemento del catalogo.</span><span class="sxs-lookup"><span data-stu-id="a533a-135">The path of the catalog item.</span></span> <span data-ttu-id="a533a-136">Per la modalità nativa, si tratta del percorso relativo dell'elemento nel database del server di report, che inizia con una barra (`/`).</span><span class="sxs-lookup"><span data-stu-id="a533a-136">For native mode, it is the relative path of the item in the report server database, beginning with a slash (`/`).</span></span> <span data-ttu-id="a533a-137">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="a533a-137">For example:</span></span>  
  
```  
/AdventureWorks 2008R2/Employee_Sales_Summary_2008R2  
```  
  
 <span data-ttu-id="a533a-138">Per la modalità integrata SharePoint, si tratta dell'URL completo dell'elemento nella raccolta di SharePoint, inclusa l'estensione dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="a533a-138">For SharePoint integrated mode, it is the fully qualified URL of the item in the SharePoint library, including the item extension.</span></span> <span data-ttu-id="a533a-139">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="a533a-139">For example:</span></span>  
  
```  
http://myspsite/subsite/AdventureWorks 2008R2/Employee_Sales_Summary_2008R2.rdl  
```  
  
 `&`  
 <span data-ttu-id="a533a-140">Carattere utilizzato per separare le coppie di nome e valore dei parametri di accesso tramite URL.</span><span class="sxs-lookup"><span data-stu-id="a533a-140">Used to separate name and value pairs of URL access parameters.</span></span>  
  
 <span data-ttu-id="a533a-141">**prefix**</span><span class="sxs-lookup"><span data-stu-id="a533a-141">**prefix**</span></span>  
 <span data-ttu-id="a533a-142">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="a533a-142">Optional.</span></span> <span data-ttu-id="a533a-143">Un prefisso per il parametro di accesso tramite URL (ad esempio, `rs:` o `rc:`) per l'accesso a un processo specifico in esecuzione nel server di report.</span><span class="sxs-lookup"><span data-stu-id="a533a-143">A prefix for the URL access parameter (for example, `rs:` or `rc:`) that accesses a specific process running within the report server.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a533a-144">Se per un parametro di accesso tramite URL non viene incluso un prefisso, il parametro viene elaborato dal server di report come parametro del report.</span><span class="sxs-lookup"><span data-stu-id="a533a-144">If a prefix for a URL access parameter is not included, the parameter is processed by the report server as a report parameter.</span></span> <span data-ttu-id="a533a-145">Nei parametri del report non si utilizzano prefissi dei parametri e non esistono distinzioni tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="a533a-145">Report parameters do not use a parameter prefix and are case-sensitive.</span></span>  
  
 <span data-ttu-id="a533a-146">**param**</span><span class="sxs-lookup"><span data-stu-id="a533a-146">**param**</span></span>  
 <span data-ttu-id="a533a-147">Nome del parametro.</span><span class="sxs-lookup"><span data-stu-id="a533a-147">The parameter name.</span></span>  
  
 <span data-ttu-id="a533a-148">*value*</span><span class="sxs-lookup"><span data-stu-id="a533a-148">*value*</span></span>  
 <span data-ttu-id="a533a-149">Testo dell'URL che corrisponde al valore del parametro utilizzato.</span><span class="sxs-lookup"><span data-stu-id="a533a-149">URL text corresponding to the value of the parameter being used.</span></span>  
  
 <span data-ttu-id="a533a-150">**Nota:** per un elenco dei parametri di accesso tramite URL disponibili, vedere [Riferimento ai parametri di accesso con URL](url-access-parameter-reference.md).</span><span class="sxs-lookup"><span data-stu-id="a533a-150">**Note:** For a list of the available URL access parameters, see [URL Access Parameter Reference](url-access-parameter-reference.md).</span></span> <span data-ttu-id="a533a-151">Per esempi di passaggi di parametri di report nell'URL, vedere [Passare un parametro del report in un URL](pass-a-report-parameter-within-a-url.md).</span><span class="sxs-lookup"><span data-stu-id="a533a-151">For examples passing report parameters on the URL, see [Pass a Report Parameter Within a URL](pass-a-report-parameter-within-a-url.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="a533a-152">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="a533a-152">Related Tasks</span></span>  
  
|<span data-ttu-id="a533a-153">Descrizioni delle attività</span><span class="sxs-lookup"><span data-stu-id="a533a-153">Task Descriptions</span></span>|<span data-ttu-id="a533a-154">Collegamenti</span><span class="sxs-lookup"><span data-stu-id="a533a-154">Links</span></span>|  
|-----------------------|-----------|  
|<span data-ttu-id="a533a-155">Accedere a elementi del server di report, quali report, origini dati condivise e risorse.</span><span class="sxs-lookup"><span data-stu-id="a533a-155">Access report server items, such as reports, shared data sources, and resources.</span></span>|[<span data-ttu-id="a533a-156">Accesso agli elementi del server di report usando l'accesso tramite URL</span><span class="sxs-lookup"><span data-stu-id="a533a-156">Access Report Server Items Using URL Access</span></span>](access-report-server-items-using-url-access.md)|  
|<span data-ttu-id="a533a-157">Passare i parametri di report a un report.</span><span class="sxs-lookup"><span data-stu-id="a533a-157">Pass report parameters to a report.</span></span>|[<span data-ttu-id="a533a-158">Passare un parametro del report in un URL</span><span class="sxs-lookup"><span data-stu-id="a533a-158">Pass a Report Parameter Within a URL</span></span>](pass-a-report-parameter-within-a-url.md)|  
|<span data-ttu-id="a533a-159">Impostare le impostazioni locali dei parametri del report nella stringa dell'accesso tramite URL che definisce le interpretazioni delle impostazioni locali di date, valute e così via.</span><span class="sxs-lookup"><span data-stu-id="a533a-159">Set the locale of the report parameters in the URL access string, which defines the locale-specific interpretations of dates, currencies, and so on.</span></span>|[<span data-ttu-id="a533a-160">Impostare la lingua per i parametri del report in un URL</span><span class="sxs-lookup"><span data-stu-id="a533a-160">Set the Language for Report Parameters in a URL</span></span>](set-the-language-for-report-parameters-in-a-url.md)|  
|<span data-ttu-id="a533a-161">Inviare le impostazioni specifiche dell'estensione di rendering che personalizzano l'esecuzione del rendering del report.</span><span class="sxs-lookup"><span data-stu-id="a533a-161">Send rendering extension specific settings that customize how the report is rendered.</span></span>|[<span data-ttu-id="a533a-162">Specificare le impostazioni relative alle informazioni sul dispositivo in un URL</span><span class="sxs-lookup"><span data-stu-id="a533a-162">Specify Device Information Settings in a URL</span></span>](specify-device-information-settings-in-a-url.md)|  
|<span data-ttu-id="a533a-163">Esportare un report direttamente in un formato di file senza visualizzarlo nel browser.</span><span class="sxs-lookup"><span data-stu-id="a533a-163">Export a report directly to a file format without viewing it in the browser.</span></span>|[<span data-ttu-id="a533a-164">Esportare un report tramite l'accesso con URL</span><span class="sxs-lookup"><span data-stu-id="a533a-164">Export a Report Using URL Access</span></span>](export-a-report-using-url-access.md)|  
|<span data-ttu-id="a533a-165">Aprire un report e passare rapidamente alla posizione di una stringa.</span><span class="sxs-lookup"><span data-stu-id="a533a-165">Open a report and navigate directly to the location of a string.</span></span>|[<span data-ttu-id="a533a-166">Cercare un report tramite l'accesso con URL</span><span class="sxs-lookup"><span data-stu-id="a533a-166">Search a Report Using URL Access</span></span>](search-a-report-using-url-access.md)|  
|<span data-ttu-id="a533a-167">Eseguire il rendering di uno snapshot della cronologia di un report specifico.</span><span class="sxs-lookup"><span data-stu-id="a533a-167">Render a specific report history snapshot.</span></span>|[<span data-ttu-id="a533a-168">Eseguire il rendering degli snapshot della cronologia dei report tramite l'accesso con URL</span><span class="sxs-lookup"><span data-stu-id="a533a-168">Render a Report History Snapshot Using URL Access</span></span>](render-a-report-history-snapshot-using-url-access.md)|  
  
## <a name="see-also"></a><span data-ttu-id="a533a-169">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a533a-169">See Also</span></span>  
 <span data-ttu-id="a533a-170">[Passare un parametro del report in un URL](pass-a-report-parameter-within-a-url.md) </span><span class="sxs-lookup"><span data-stu-id="a533a-170">[Pass a Report Parameter Within a URL](pass-a-report-parameter-within-a-url.md) </span></span>  
 <span data-ttu-id="a533a-171">[Riferimento ai parametri di accesso con URL](url-access-parameter-reference.md) </span><span class="sxs-lookup"><span data-stu-id="a533a-171">[URL Access Parameter Reference](url-access-parameter-reference.md) </span></span>  
 <span data-ttu-id="a533a-172">[Integrazione di Reporting Services tramite l'accesso con URL](application-integration/integrating-reporting-services-using-url-access.md) </span><span class="sxs-lookup"><span data-stu-id="a533a-172">[Integrating Reporting Services Using URL Access](application-integration/integrating-reporting-services-using-url-access.md) </span></span>  
 [<span data-ttu-id="a533a-173">Ricerca, visualizzazione e gestione dei report &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="a533a-173">Finding, Viewing, and Managing Reports &#40;Report Builder and SSRS &#41;</span></span>](report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md)  
  
  
