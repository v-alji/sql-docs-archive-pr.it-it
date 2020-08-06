---
title: Funzionalità deprecate in SQL Server Reporting Services SQL Server 2014 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- Reporting Services, backward compatibility
- deprecated features [Reporting Services]
- HTML OWC rendering extension [Reporting Services]
- Report Server Web service, endpoints
ms.assetid: 3876c01e-f81d-4cce-9104-5106a8c369e6
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: af858ae94bf5ea3d9f0cfe0b99759442dabd6629
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629244"
---
# <a name="deprecated-features-in-sql-server-reporting-services-in-sql-server-2014"></a><span data-ttu-id="7d862-102">Funzionalità deprecate di SQL Server Reporting Services in SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="7d862-102">Deprecated Features in SQL Server Reporting Services in SQL Server 2014</span></span>
  <span data-ttu-id="7d862-103">In questo argomento si descrivono le funzionalità di [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] deprecate.</span><span class="sxs-lookup"><span data-stu-id="7d862-103">This topic describes the deprecated [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features.</span></span> <span data-ttu-id="7d862-104">Le funzionalità sono ancora disponibili nella versione in cui sono deprecate, tuttavia sono pianificate per essere rimosse in una versione successiva di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7d862-104">The features are still available in the release in which they are deprecated; however the features are scheduled to be removed in a future release of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="7d862-105">È consigliabile non usare le funzionalità deprecate nelle nuove applicazioni.</span><span class="sxs-lookup"><span data-stu-id="7d862-105">Deprecated features should not be used in new applications.</span></span>  
  
 <span data-ttu-id="7d862-106">In questo argomento</span><span class="sxs-lookup"><span data-stu-id="7d862-106">In this topic:</span></span>  
  
-   [<span data-ttu-id="7d862-107">Funzionalità deprecate in SQL Server 2014 Reporting Services</span><span class="sxs-lookup"><span data-stu-id="7d862-107">SQL Server 2014 Reporting Services Deprecated Features</span></span>](#bkmk_2014)  
  
-   [<span data-ttu-id="7d862-108">Funzionalità deprecate di SQL Server 2012 SP1 Reporting Services</span><span class="sxs-lookup"><span data-stu-id="7d862-108">SQL Server 2012 SP1 Reporting Services Deprecated Features</span></span>](#bkmk_2012sp1)  
  
-   [<span data-ttu-id="7d862-109">Funzionalità deprecate in SQL Server 2012 Reporting Services</span><span class="sxs-lookup"><span data-stu-id="7d862-109">SQL Server 2012 Reporting Services Deprecated Features</span></span>](#bkmk_2012)  
  
-   [<span data-ttu-id="7d862-110">Funzionalità deprecate di SQL Server 2008 R2 Reporting Services</span><span class="sxs-lookup"><span data-stu-id="7d862-110">SQL Server 2008 R2 Reporting Services Deprecated Features</span></span>](#bkmk_kj)  
  
##  <a name="sql-server-2014-reporting-services-deprecated-features"></a><a name="bkmk_2014"></a><span data-ttu-id="7d862-111">SQL Server 2014 Reporting Services funzionalità deprecate</span><span class="sxs-lookup"><span data-stu-id="7d862-111">SQL Server 2014 Reporting Services Deprecated Features</span></span>  
  
### <a name="features-not-supported-in-the-next-version-of-sql-server"></a><span data-ttu-id="7d862-112">Funzionalità non supportate nella prossima versione di SQL Server</span><span class="sxs-lookup"><span data-stu-id="7d862-112">Features Not Supported in the Next Version of SQL Server</span></span>  
 <span data-ttu-id="7d862-113">Le [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] funzionalità seguenti non saranno supportate nella **prossima** versione di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7d862-113">The following [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features will not be supported in the **next** version of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="7d862-114">Non usare queste funzionalità in un nuovo progetto di sviluppo e modificare non appena possibile le applicazioni in cui sono attualmente implementate.</span><span class="sxs-lookup"><span data-stu-id="7d862-114">Do not use these features in new development work, and modify applications that currently use these features as soon as possible.</span></span>  
  
#### <a name="html-rendering-extension-device-information-settings"></a><span data-ttu-id="7d862-115">Impostazioni relative alle informazioni sul dispositivo per l'estensione per il rendering HTML</span><span class="sxs-lookup"><span data-stu-id="7d862-115">HTML Rendering Extension Device Information Settings</span></span>  
 <span data-ttu-id="7d862-116">Le seguenti impostazioni relative alle informazioni sul dispositivo per l'estensione per il rendering HTML sono deprecate.</span><span class="sxs-lookup"><span data-stu-id="7d862-116">The following device information settings for the HTML rendering extension are deprecated.</span></span>  
  
-   <span data-ttu-id="7d862-117">ActionScript</span><span class="sxs-lookup"><span data-stu-id="7d862-117">ActionScript</span></span>  
  
-   <span data-ttu-id="7d862-118">ActiveXControls</span><span class="sxs-lookup"><span data-stu-id="7d862-118">ActiveXControls</span></span>  
  
-   <span data-ttu-id="7d862-119">GetImage</span><span class="sxs-lookup"><span data-stu-id="7d862-119">GetImage</span></span>  
  
-   <span data-ttu-id="7d862-120">OnlyVisibleStyles</span><span class="sxs-lookup"><span data-stu-id="7d862-120">OnlyVisibleStyles</span></span>  
  
-   <span data-ttu-id="7d862-121">ReplacementRoot</span><span class="sxs-lookup"><span data-stu-id="7d862-121">ReplacementRoot</span></span>  
  
-   <span data-ttu-id="7d862-122">ResourceStreamRoot</span><span class="sxs-lookup"><span data-stu-id="7d862-122">ResourceStreamRoot</span></span>  
  
-   <span data-ttu-id="7d862-123">StreamRoot</span><span class="sxs-lookup"><span data-stu-id="7d862-123">StreamRoot</span></span>  
  
-   <span data-ttu-id="7d862-124">UsePx</span><span class="sxs-lookup"><span data-stu-id="7d862-124">UsePx</span></span>  
  
-   <span data-ttu-id="7d862-125">Zoom</span><span class="sxs-lookup"><span data-stu-id="7d862-125">Zoom</span></span>  
  
 <span data-ttu-id="7d862-126">Per ulteriori informazioni sull'estensione per il rendering HTML, vedere [HTML Device Information Settings](html-device-information-settings.md)</span><span class="sxs-lookup"><span data-stu-id="7d862-126">For more information on the HTML rendering extension, see [HTML Device Information Settings](html-device-information-settings.md)</span></span>  
  
#### <a name="microsoft-word-and-microsoft-excel-1997-2003-rendering"></a><span data-ttu-id="7d862-127">Rendering di Microsoft Word e Microsoft Excel 1997-2003</span><span class="sxs-lookup"><span data-stu-id="7d862-127">Microsoft Word and Microsoft Excel 1997-2003 Rendering</span></span>  
 <span data-ttu-id="7d862-128">Con le estensioni per il rendering BIFF8 di[!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] , [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] esegue i report nel formato BIFF (Binary Interchange File Format) di [!INCLUDE[msCoName](../includes/msconame-md.md)] Word e [!INCLUDE[msCoName](../includes/msconame-md.md)] Excel 1997-2003.</span><span class="sxs-lookup"><span data-stu-id="7d862-128">The[!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] BIFF8 rendering extensions [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] reports to the [!INCLUDE[msCoName](../includes/msconame-md.md)] Word and [!INCLUDE[msCoName](../includes/msconame-md.md)] Excel 1997-2003 binary interchange file format.</span></span> [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)]<span data-ttu-id="7d862-129">include le estensioni che eseguono il rendering nel [!INCLUDE[msCoName](../includes/msconame-md.md)] formato Office 2007-2010 Open XML.</span><span class="sxs-lookup"><span data-stu-id="7d862-129">includes extensions that render in the [!INCLUDE[msCoName](../includes/msconame-md.md)] Office 2007-2010 Open XML format.</span></span>  
  
#### <a name="report-definition-language-rdl-2005-and-earlier"></a><span data-ttu-id="7d862-130">Linguaggio RDL (Report Definition Language) 2005 e versioni precedenti</span><span class="sxs-lookup"><span data-stu-id="7d862-130">Report Definition Language (RDL) 2005 and Earlier</span></span>  
 <span data-ttu-id="7d862-131">Il linguaggio RDL (Report Definition Language) 2005 e le versioni precedenti sono deprecati.</span><span class="sxs-lookup"><span data-stu-id="7d862-131">Report Definition Language (RDL) 2005 and earlier is deprecated.</span></span> <span data-ttu-id="7d862-132">Per ulteriori informazioni su RDL, vedere [Report Definition Language &#40;SSRS&#41;](reports/report-definition-language-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="7d862-132">For more information about RDL, see [Report Definition Language &#40;SSRS&#41;](reports/report-definition-language-ssrs.md).</span></span>  
  
 <span data-ttu-id="7d862-133">Per ulteriori informazioni sull'aggiornamento dei report, vedere [Upgrade Reports](install-windows/upgrade-reports.md).</span><span class="sxs-lookup"><span data-stu-id="7d862-133">For more information on upgrading reports, see [Upgrade Reports](install-windows/upgrade-reports.md).</span></span>  
  
#### <a name="sql-server-2005-and-earlier-custom-report-items"></a><span data-ttu-id="7d862-134">Elementi di report personalizzati di SQL Server 2005 e versioni precedenti</span><span class="sxs-lookup"><span data-stu-id="7d862-134">SQL Server 2005 and earlier Custom Report Items</span></span>  
 <span data-ttu-id="7d862-135">Gli elementi del report personalizzati compilati per [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] 2005 e versioni precedenti sono deprecati.</span><span class="sxs-lookup"><span data-stu-id="7d862-135">Custom Report Items (CRI) compiled for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] 2005 and earlier are deprecated.</span></span>  
  
#### <a name="reporting-services-snapshots-2005-and-earlier"></a><span data-ttu-id="7d862-136">Snapshot di Reporting Services 2005 e versioni precedenti</span><span class="sxs-lookup"><span data-stu-id="7d862-136">Reporting Services Snapshots 2005 and earlier</span></span>  
 [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]<span data-ttu-id="7d862-137">gli snapshot di cui è stato eseguito il rendering con [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] 2005 e versioni precedenti sono deprecati.</span><span class="sxs-lookup"><span data-stu-id="7d862-137">snapshots rendered with [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] 2005 and earlier are deprecated.</span></span>  
  
#### <a name="report-models"></a><span data-ttu-id="7d862-138">Modelli di report</span><span class="sxs-lookup"><span data-stu-id="7d862-138">Report Models</span></span>  
 <span data-ttu-id="7d862-139">I modelli di report del linguaggio SMDL (Semantic Modeling Language) sono deprecati.</span><span class="sxs-lookup"><span data-stu-id="7d862-139">Semantic modeling language (SMDL) report models are deprecated.</span></span> <span data-ttu-id="7d862-140">Sebbene sia possibile continuare a utilizzare i modelli di report esistenti come origini dati nei [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] report, è consigliabile aggiornare i report per rimuovere la dipendenza dai modelli di report.</span><span class="sxs-lookup"><span data-stu-id="7d862-140">Although you can you continue to use existing report models as data sources in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)][!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] reports you should consider updating your reports to remove their dependency on report models.</span></span>  
  
 [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)]<span data-ttu-id="7d862-141">non [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] include strumenti per la creazione o l'aggiornamento di modelli di report.</span><span class="sxs-lookup"><span data-stu-id="7d862-141">[!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] does not include tools for creating or updating report models.</span></span> <span data-ttu-id="7d862-142">Per ulteriori informazioni, vedere [modifiche di rilievo nelle SQL Server Reporting Services SQL Server 2014](breaking-changes-in-sql-server-reporting-services-in-sql-server-2016.md).</span><span class="sxs-lookup"><span data-stu-id="7d862-142">For more information, see [Breaking Changes in SQL Server Reporting Services in SQL Server 2014](breaking-changes-in-sql-server-reporting-services-in-sql-server-2016.md).</span></span>  
  
#### <a name="deprecated-methods-in-the-web-service-endpoint"></a><span data-ttu-id="7d862-143">Metodi deprecati nell'endpoint servizio Web</span><span class="sxs-lookup"><span data-stu-id="7d862-143">Deprecated Methods in the Web Service Endpoint</span></span>  
 <span data-ttu-id="7d862-144">Le operazioni seguenti sono deprecate nell'endpoint servizio Web di <xref:ReportService2010.ReportingService2010>:</span><span class="sxs-lookup"><span data-stu-id="7d862-144">The following operations are deprecated in the <xref:ReportService2010.ReportingService2010> Web service endpoint:</span></span>  
  
-   <xref:ReportService2010.ReportingService2010.GetProperties%2A>  
  
-   <xref:ReportService2010.ReportingService2010.IsSSLRequired%2A>  
  
#### <a name="sharepoint-web-parts"></a><span data-ttu-id="7d862-145">Web part di SharePoint</span><span class="sxs-lookup"><span data-stu-id="7d862-145">SharePoint Web Parts</span></span>  
 <span data-ttu-id="7d862-146">Il file CAB di installazione **RSWebParts.cab** e le web part di SharePoint che possono essere estratte dal file CAB, sono deprecati.</span><span class="sxs-lookup"><span data-stu-id="7d862-146">The installation cabinet file **RSWebParts.cab** and the SharePoint web parts that can be extracted from the cab file, are deprecated.</span></span> <span data-ttu-id="7d862-147">Le web part deprecate sono Esplora report (**SPExplorer.dwp**) e Visualizzatore report (**SPViewer.dwp**).</span><span class="sxs-lookup"><span data-stu-id="7d862-147">The deprecated web parts are Report Explorer (**SPExplorer.dwp**) and Report Viewer (**SPViewer.dwp**).</span></span>  
  
 <span data-ttu-id="7d862-148">Per ulteriori informazioni sulle web part deprecate, vedere [Visualizzare ed esplorare i report in modalità nativa utilizzando le web part di SharePoint (SSRS)](https://msdn.microsoft.com/library/ms159772.aspx)</span><span class="sxs-lookup"><span data-stu-id="7d862-148">For more information on the deprecated web parts, see [View and Explore Native Mode Reports Using SharePoint Web Parts (SSRS)](https://msdn.microsoft.com/library/ms159772.aspx)</span></span>  
  
### <a name="features-not-supported-in-a-future-version-of-sql-server"></a><span data-ttu-id="7d862-149">Funzionalità non supportate in una futura versione di SQL Server</span><span class="sxs-lookup"><span data-stu-id="7d862-149">Features Not Supported in a Future Version of SQL Server</span></span>  
 <span data-ttu-id="7d862-150">Le funzionalità seguenti del [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] sono supportate nella versione successiva di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], ma in seguito verranno rimosse.</span><span class="sxs-lookup"><span data-stu-id="7d862-150">The following [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features are supported in the next version of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], but will be removed in a later version.</span></span> <span data-ttu-id="7d862-151">La versione specifica di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] non è stata determinata.</span><span class="sxs-lookup"><span data-stu-id="7d862-151">The specific version of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] has not been determined.</span></span>  
  
 <span data-ttu-id="7d862-152">In [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] non sono state deprecate funzionalità di [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7d862-152">No [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features were deprecated in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span></span>  
  
##  <a name="sql-server-2012-sp1-reporting-services-deprecated-features"></a><a name="bkmk_2012sp1"></a><span data-ttu-id="7d862-153">SQL Server 2012 SP1 Reporting Services funzionalità deprecate</span><span class="sxs-lookup"><span data-stu-id="7d862-153">SQL Server 2012 SP1 Reporting Services Deprecated Features</span></span>  
 <span data-ttu-id="7d862-154">In questa sezione si descrivono le funzionalità di [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] deprecate in [!INCLUDE[ssSQL11SP1](../includes/sssql11sp1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7d862-154">This section describes [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features deprecated in [!INCLUDE[ssSQL11SP1](../includes/sssql11sp1-md.md)].</span></span> <span data-ttu-id="7d862-155">Le funzionalità seguenti del [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] sono supportate nella versione successiva di [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], ma in seguito verranno rimosse.</span><span class="sxs-lookup"><span data-stu-id="7d862-155">The following [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features are supported in the next version of [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], but will be removed in a later version.</span></span> <span data-ttu-id="7d862-156">La versione specifica di [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] non è stata determinata.</span><span class="sxs-lookup"><span data-stu-id="7d862-156">The specific version of [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] has not been determined.</span></span>  
  
### <a name="sharepoint-web-parts"></a><span data-ttu-id="7d862-157">Web part di SharePoint</span><span class="sxs-lookup"><span data-stu-id="7d862-157">SharePoint Web Parts</span></span>  
 <span data-ttu-id="7d862-158">Il file CAB di installazione **RSWebParts.cab** e le web part di SharePoint che possono essere estratte dal file CAB, sono deprecati.</span><span class="sxs-lookup"><span data-stu-id="7d862-158">The installation cabinet file **RSWebParts.cab** and the SharePoint web parts that can be extracted from the cab file, are deprecated.</span></span> <span data-ttu-id="7d862-159">Le web part deprecate sono Esplora report (**SPExplorer.dwp**) e Visualizzatore report (**SPViewer.dwp**).</span><span class="sxs-lookup"><span data-stu-id="7d862-159">The deprecated web parts are Report Explorer (**SPExplorer.dwp**) and Report Viewer (**SPViewer.dwp**).</span></span>  
  
 <span data-ttu-id="7d862-160">Per ulteriori informazioni sulle web part deprecate, vedere [Visualizzare ed esplorare i report in modalità nativa utilizzando le web part di SharePoint (SSRS)](https://msdn.microsoft.com/library/ms159772.aspx)</span><span class="sxs-lookup"><span data-stu-id="7d862-160">For more information on the deprecated web parts, see [View and Explore Native Mode Reports Using SharePoint Web Parts (SSRS)](https://msdn.microsoft.com/library/ms159772.aspx)</span></span>  
  
##  <a name="sql-server-2012-reporting-services-deprecated-features"></a><a name="bkmk_2012"></a><span data-ttu-id="7d862-161">SQL Server 2012 Reporting Services funzionalità deprecate</span><span class="sxs-lookup"><span data-stu-id="7d862-161">SQL Server 2012 Reporting Services Deprecated Features</span></span>  
 <span data-ttu-id="7d862-162">In questa sezione si descrivono le funzionalità di [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] deprecate in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7d862-162">This section describes [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features deprecated in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)].</span></span>  
  
### <a name="html-rendering-extension-device-information-settings"></a><span data-ttu-id="7d862-163">Impostazioni relative alle informazioni sul dispositivo per l'estensione per il rendering HTML</span><span class="sxs-lookup"><span data-stu-id="7d862-163">HTML Rendering Extension Device Information Settings</span></span>  
 <span data-ttu-id="7d862-164">Le seguenti impostazioni relative alle informazioni sul dispositivo per l'estensione per il rendering HTML sono deprecate.</span><span class="sxs-lookup"><span data-stu-id="7d862-164">The following device information settings for the HTML rendering extension are deprecated.</span></span>  
  
-   <span data-ttu-id="7d862-165">ActionScript</span><span class="sxs-lookup"><span data-stu-id="7d862-165">ActionScript</span></span>  
  
-   <span data-ttu-id="7d862-166">ActiveXControls</span><span class="sxs-lookup"><span data-stu-id="7d862-166">ActiveXControls</span></span>  
  
-   <span data-ttu-id="7d862-167">GetImage</span><span class="sxs-lookup"><span data-stu-id="7d862-167">GetImage</span></span>  
  
-   <span data-ttu-id="7d862-168">OnlyVisibleStyles</span><span class="sxs-lookup"><span data-stu-id="7d862-168">OnlyVisibleStyles</span></span>  
  
-   <span data-ttu-id="7d862-169">ReplacementRoot</span><span class="sxs-lookup"><span data-stu-id="7d862-169">ReplacementRoot</span></span>  
  
-   <span data-ttu-id="7d862-170">ResourceStreamRoot</span><span class="sxs-lookup"><span data-stu-id="7d862-170">ResourceStreamRoot</span></span>  
  
-   <span data-ttu-id="7d862-171">StreamRoot</span><span class="sxs-lookup"><span data-stu-id="7d862-171">StreamRoot</span></span>  
  
-   <span data-ttu-id="7d862-172">UsePx</span><span class="sxs-lookup"><span data-stu-id="7d862-172">UsePx</span></span>  
  
-   <span data-ttu-id="7d862-173">Zoom</span><span class="sxs-lookup"><span data-stu-id="7d862-173">Zoom</span></span>  
  
 <span data-ttu-id="7d862-174">Per ulteriori informazioni sull'estensione per il rendering HTML, vedere [HTML Device Information Settings](html-device-information-settings.md)</span><span class="sxs-lookup"><span data-stu-id="7d862-174">For more information on the HTML rendering extension, see [HTML Device Information Settings](html-device-information-settings.md)</span></span>  
  
### <a name="microsoft-word-and-microsoft-excel-1997-2003-rendering"></a><span data-ttu-id="7d862-175">Rendering di Microsoft Word e Microsoft Excel 1997-2003</span><span class="sxs-lookup"><span data-stu-id="7d862-175">Microsoft Word and Microsoft Excel 1997-2003 Rendering</span></span>  
 <span data-ttu-id="7d862-176">Con le estensioni per il rendering BIFF8 di[!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] , [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] esegue i report nel formato BIFF (Binary Interchange File Format) di [!INCLUDE[msCoName](../includes/msconame-md.md)] Word e [!INCLUDE[msCoName](../includes/msconame-md.md)] Excel 1997-2003.</span><span class="sxs-lookup"><span data-stu-id="7d862-176">The[!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] BIFF8 rendering extensions [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] reports to the [!INCLUDE[msCoName](../includes/msconame-md.md)] Word and [!INCLUDE[msCoName](../includes/msconame-md.md)] Excel 1997-2003 binary interchange file format.</span></span> [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)]<span data-ttu-id="7d862-177">include le estensioni che eseguono il rendering nel [!INCLUDE[msCoName](../includes/msconame-md.md)] formato Office 2007-2010 Open XML.</span><span class="sxs-lookup"><span data-stu-id="7d862-177">includes extensions that render in the [!INCLUDE[msCoName](../includes/msconame-md.md)] Office 2007-2010 Open XML format.</span></span>  
  
### <a name="report-definition-language-rdl-2005-and-earlier"></a><span data-ttu-id="7d862-178">Linguaggio RDL (Report Definition Language) 2005 e versioni precedenti</span><span class="sxs-lookup"><span data-stu-id="7d862-178">Report Definition Language (RDL) 2005 and Earlier</span></span>  
 <span data-ttu-id="7d862-179">Il linguaggio RDL (Report Definition Language) 2005 e le versioni precedenti sono deprecati.</span><span class="sxs-lookup"><span data-stu-id="7d862-179">Report Definition Language (RDL) 2005 and earlier is deprecated.</span></span> <span data-ttu-id="7d862-180">Per ulteriori informazioni su RDL, vedere [Report Definition Language &#40;SSRS&#41;](reports/report-definition-language-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="7d862-180">For more information about RDL, see [Report Definition Language &#40;SSRS&#41;](reports/report-definition-language-ssrs.md).</span></span>  
  
 <span data-ttu-id="7d862-181">Per ulteriori informazioni sull'aggiornamento dei report, vedere [Upgrade Reports](install-windows/upgrade-reports.md).</span><span class="sxs-lookup"><span data-stu-id="7d862-181">For more information on upgrading reports, see [Upgrade Reports](install-windows/upgrade-reports.md).</span></span>  
  
### <a name="sql-server-2005-and-earlier-custom-report-items"></a><span data-ttu-id="7d862-182">Elementi di report personalizzati di SQL Server 2005 e versioni precedenti</span><span class="sxs-lookup"><span data-stu-id="7d862-182">SQL Server 2005 and earlier Custom Report Items</span></span>  
 <span data-ttu-id="7d862-183">Gli elementi del report personalizzati compilati per [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] 2005 e versioni precedenti sono deprecati.</span><span class="sxs-lookup"><span data-stu-id="7d862-183">Custom Report Items (CRI) compiled for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] 2005 and earlier are deprecated.</span></span>  
  
### <a name="reporting-services-snapshots-2005-and-earlier"></a><span data-ttu-id="7d862-184">Snapshot di Reporting Services 2005 e versioni precedenti</span><span class="sxs-lookup"><span data-stu-id="7d862-184">Reporting Services Snapshots 2005 and earlier</span></span>  
 [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]<span data-ttu-id="7d862-185">gli snapshot di cui è stato eseguito il rendering con [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] 2005 e versioni precedenti sono deprecati.</span><span class="sxs-lookup"><span data-stu-id="7d862-185">snapshots rendered with [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] 2005 and earlier are deprecated.</span></span>  
  
### <a name="report-models"></a><span data-ttu-id="7d862-186">Modelli di report</span><span class="sxs-lookup"><span data-stu-id="7d862-186">Report Models</span></span>  
 <span data-ttu-id="7d862-187">I modelli di report del linguaggio SMDL (Semantic Modeling Language) sono deprecati.</span><span class="sxs-lookup"><span data-stu-id="7d862-187">Semantic modeling language (SMDL) report models are deprecated.</span></span> <span data-ttu-id="7d862-188">Sebbene sia possibile continuare a utilizzare i modelli di report esistenti come origini dati nei [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] report, è consigliabile aggiornare i report per rimuovere la dipendenza dai modelli di report.</span><span class="sxs-lookup"><span data-stu-id="7d862-188">Although you can you continue to use existing report models as data sources in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)][!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] reports you should consider updating your reports to remove their dependency on report models.</span></span>  
  
 [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)]<span data-ttu-id="7d862-189">non [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] include strumenti per la creazione o l'aggiornamento di modelli di report.</span><span class="sxs-lookup"><span data-stu-id="7d862-189">[!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] does not include tools for creating or updating report models.</span></span> <span data-ttu-id="7d862-190">Per ulteriori informazioni, vedere [modifiche di rilievo nelle SQL Server Reporting Services SQL Server 2014](breaking-changes-in-sql-server-reporting-services-in-sql-server-2016.md).</span><span class="sxs-lookup"><span data-stu-id="7d862-190">For more information, see [Breaking Changes in SQL Server Reporting Services in SQL Server 2014](breaking-changes-in-sql-server-reporting-services-in-sql-server-2016.md).</span></span>  
  
### <a name="deprecated-methods-in-the-web-service-endpoint"></a><span data-ttu-id="7d862-191">Metodi deprecati nell'endpoint servizio Web</span><span class="sxs-lookup"><span data-stu-id="7d862-191">Deprecated Methods in the Web Service Endpoint</span></span>  
 <span data-ttu-id="7d862-192">Le operazioni seguenti sono deprecate nell'endpoint servizio Web di <xref:ReportService2010.ReportingService2010>:</span><span class="sxs-lookup"><span data-stu-id="7d862-192">The following operations are deprecated in the <xref:ReportService2010.ReportingService2010> Web service endpoint:</span></span>  
  
-   <xref:ReportService2010.ReportingService2010.GetProperties%2A>  
  
-   <xref:ReportService2010.ReportingService2010.IsSSLRequired%2A>  
  
##  <a name="sql-server-2008-r2-reporting-services-deprecated-features"></a><a name="bkmk_kj"></a><span data-ttu-id="7d862-193">SQL Server 2008 R2 Reporting Services funzionalità deprecate</span><span class="sxs-lookup"><span data-stu-id="7d862-193">SQL Server 2008 R2 Reporting Services Deprecated Features</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7d862-194">Poiché SQL Server 2008 R2 è un aggiornamento secondario della versione di SQL Server 2008, è consigliabile rivedere anche il contenuto nella sezione relativa a SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="7d862-194">Because SQL Server 2008 R2 is a minor version upgrade of SQL Server 2008, we recommend that you also review the content in the SQL Server 2008 section.</span></span>  
  
### <a name="report-server-web-service-endpoints"></a><span data-ttu-id="7d862-195">Endpoint del servizio Web ReportServer</span><span class="sxs-lookup"><span data-stu-id="7d862-195">Report Server Web Service Endpoints</span></span>  
 <span data-ttu-id="7d862-196">I servizi Web <xref:ReportService2005.ReportingService2005> e <xref:ReportService2006.ReportingService2006> sono deprecati in questa versione.</span><span class="sxs-lookup"><span data-stu-id="7d862-196">The Web services <xref:ReportService2005.ReportingService2005> and <xref:ReportService2006.ReportingService2006> have been deprecated in this release.</span></span> <span data-ttu-id="7d862-197">Questi endpoint sono stati sostituiti da un nuovo endpoint: <xref:ReportService2010.ReportingService2010>.</span><span class="sxs-lookup"><span data-stu-id="7d862-197">These endpoints have been replaced by a new endpoint: <xref:ReportService2010.ReportingService2010>.</span></span>  
  
 <span data-ttu-id="7d862-198">Nel nuovo endpoint sono incluse tutte le funzionalità disponibili negli endpoint deprecati e le nuove funzionalità introdotte in SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="7d862-198">The new endpoint includes all the functionality available in the deprecated endpoints and the new features introduced in SQL Server 2008 R2.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d862-199">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7d862-199">See Also</span></span>  
 <span data-ttu-id="7d862-200">[Novità &#40;Reporting Services&#41;](what-s-new-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="7d862-200">[What's New &#40;Reporting Services&#41;](what-s-new-reporting-services.md) </span></span>  
 <span data-ttu-id="7d862-201">[Compatibilità con le versioni precedenti](../getting-started/backward-compatibility.md) </span><span class="sxs-lookup"><span data-stu-id="7d862-201">[Backward Compatibility](../getting-started/backward-compatibility.md) </span></span>  
 <span data-ttu-id="7d862-202">[Modifiche del comportamento a SQL Server Reporting Services in SQL Server 2014](behavior-changes-to-sql-server-reporting-services-in-sql-server-2016.md) </span><span class="sxs-lookup"><span data-stu-id="7d862-202">[Behavior Changes to SQL Server Reporting Services  in SQL Server 2014](behavior-changes-to-sql-server-reporting-services-in-sql-server-2016.md) </span></span>  
 [<span data-ttu-id="7d862-203">Funzionalità non più disponibili di SQL Server Reporting Services in SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="7d862-203">Discontinued Functionality to SQL Server Reporting Services in SQL Server 2014</span></span>](discontinued-functionality-to-sql-server-reporting-services-in-sql-server.md)  
  
  
