---
title: Reporting Services (SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 11/25/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- reports [Reporting Services]
- SSRS
- reports [Reporting Services], about reports
- Reporting Services
- SQL Server Reporting Services
ms.assetid: b8d18d3d-9db0-43e7-8286-7b46cc3a37ed
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 0418acaab54032148f4bc6d42d06c97070b89e1e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711764"
---
# <a name="reporting-services-ssrs"></a><span data-ttu-id="7ea5c-102">Reporting Services (SSRS)</span><span class="sxs-lookup"><span data-stu-id="7ea5c-102">Reporting Services (SSRS)</span></span>
  [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]<span data-ttu-id="7ea5c-103">[!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]offre una gamma completa di strumenti e servizi pronti per l'uso che consentono di creare, distribuire e gestire report per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7ea5c-103">[!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] provides a full range of ready-to-use tools and services to help you create, deploy, and manage reports for your organization.</span></span> <span data-ttu-id="7ea5c-104">In [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] sono incluse funzionalità di programmazione che consentono di estendere e personalizzare la funzionalità di reporting.</span><span class="sxs-lookup"><span data-stu-id="7ea5c-104">[!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] includes programming features that enable you to extend and customize your reporting functionality.</span></span>

 [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]<span data-ttu-id="7ea5c-105">è una piattaforma per la creazione di report basata su server che fornisce funzionalità complete per la creazione di report per un'ampia gamma di origini dati.</span><span class="sxs-lookup"><span data-stu-id="7ea5c-105">is a server-based reporting platform that provides comprehensive reporting functionality for a variety of data sources.</span></span> [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]<span data-ttu-id="7ea5c-106">include un set completo di strumenti per creare, gestire e recapitare report, nonché API che consentono agli sviluppatori di integrare o estendere l'elaborazione di dati e report in applicazioni personalizzate.</span><span class="sxs-lookup"><span data-stu-id="7ea5c-106">includes a complete set of tools for you to create, manage, and deliver reports, and APIs that enable developers to integrate or extend data and report processing in custom applications.</span></span> [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]<span data-ttu-id="7ea5c-107">gli strumenti di funzionano all'interno dell' [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] ambiente e sono completamente integrati con [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] gli strumenti e i componenti di.</span><span class="sxs-lookup"><span data-stu-id="7ea5c-107">tools work within the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] environment and are fully integrated with [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] tools and components.</span></span>

 <span data-ttu-id="7ea5c-108">[!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] consente di creare report interattivi, tabulari, grafici o in formato libero da origini dati relazionali, multidimensionali o basate su XML.</span><span class="sxs-lookup"><span data-stu-id="7ea5c-108">With [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], you can create interactive, tabular, graphical, or free-form reports from relational, multidimensional, or XML-based data sources.</span></span> <span data-ttu-id="7ea5c-109">I report possono includere una visualizzazione dei dati dettagliata, con grafici, mappe e grafici sparkline.</span><span class="sxs-lookup"><span data-stu-id="7ea5c-109">Reports can include rich data visualization, including charts, maps, and sparklines.</span></span> <span data-ttu-id="7ea5c-110">È possibile pubblicare report, pianificare l'elaborazione dei report o accedere ai report su richiesta.</span><span class="sxs-lookup"><span data-stu-id="7ea5c-110">You can publish reports, schedule report processing, or access reports on-demand.</span></span> <span data-ttu-id="7ea5c-111">È possibile scegliere tra un'ampia gamma di formati di visualizzazione, esportare i report in altre applicazioni, ad esempio [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)], e sottoscrivere report pubblicati.</span><span class="sxs-lookup"><span data-stu-id="7ea5c-111">You can select from a variety of viewing formats, export reports to other applications such as [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)], and subscribe to published reports.</span></span> <span data-ttu-id="7ea5c-112">I report creati possono essere visualizzati tramite una connessione basata su Web o come parte di un'applicazione [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows o di un sito di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="7ea5c-112">The reports that you create can be viewed over a Web-based connection or as part of a [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows application or SharePoint site.</span></span> <span data-ttu-id="7ea5c-113">È inoltre possibile creare avvisi dati nei report pubblicati in un sito di SharePoint e ricevere messaggi di posta elettronica quando i dati del report cambiano.</span><span class="sxs-lookup"><span data-stu-id="7ea5c-113">You can also create data alerts on reports published to a SharePoint site and receive email messages when report data changes.</span></span>

 <span data-ttu-id="7ea5c-114">Per ulteriori informazioni sulle nuove funzionalità di [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] , vedere novità [&#40;Reporting Services&#41;](../../2014/reporting-services/what-s-new-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="7ea5c-114">For more information about features new in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], see [What's New &#40;Reporting Services&#41;](../../2014/reporting-services/what-s-new-reporting-services.md).</span></span>

 <span data-ttu-id="7ea5c-115">Per informazioni su altri componenti, strumenti e risorse di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , vedere la [Documentazione online di SQL Server](../index.yml).</span><span class="sxs-lookup"><span data-stu-id="7ea5c-115">For information about other [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] components, tools, and resources, see [SQL Server Books Online](../index.yml).</span></span>

 <span data-ttu-id="7ea5c-116">Icona **Sfoglia contenuto per** ![cartella](media/hlp-16folder.gif "Icona Cartella") area [Reporting Services server di report](../../2014/reporting-services/reporting-services-report-server.md)</span><span class="sxs-lookup"><span data-stu-id="7ea5c-116">**Browse Content by Area** ![Folder icon](media/hlp-16folder.gif "Folder icon") [Reporting Services Report Server](../../2014/reporting-services/reporting-services-report-server.md)</span></span>

 <span data-ttu-id="7ea5c-117">![Icona della cartella](media/hlp-16folder.gif "Icona Cartella") [Reporting Services report &#40;SSRS&#41;](reports/reporting-services-reports-ssrs.md)</span><span class="sxs-lookup"><span data-stu-id="7ea5c-117">![Folder icon](media/hlp-16folder.gif "Folder icon") [Reporting Services Reports &#40;SSRS&#41;](reports/reporting-services-reports-ssrs.md)</span></span>

 <span data-ttu-id="7ea5c-118">![Icona della cartella](media/hlp-16folder.gif "Icona Cartella") [dati del report &#40;&#41;SSRS](report-data/report-data-ssrs.md)</span><span class="sxs-lookup"><span data-stu-id="7ea5c-118">![Folder icon](media/hlp-16folder.gif "Folder icon") [Report Data &#40;SSRS&#41;](report-data/report-data-ssrs.md)</span></span>

 <span data-ttu-id="7ea5c-119">![Icona della cartella](media/hlp-16folder.gif "Icona Cartella") [parametri del report &#40;Generatore report e progettazione report&#41;](report-design/report-parameters-report-builder-and-report-designer.md)</span><span class="sxs-lookup"><span data-stu-id="7ea5c-119">![Folder icon](media/hlp-16folder.gif "Folder icon") [Report Parameters &#40;Report Builder and Report Designer&#41;](report-design/report-parameters-report-builder-and-report-designer.md)</span></span>

 <span data-ttu-id="7ea5c-120">![Icona della cartella](media/hlp-16folder.gif "Icona Cartella") [parti del Report in Progettazione report &#40;SSRS&#41;](report-design/report-parts-in-report-designer-ssrs.md)</span><span class="sxs-lookup"><span data-stu-id="7ea5c-120">![Folder icon](media/hlp-16folder.gif "Folder icon") [Report Parts in Report Designer &#40;SSRS&#41;](report-design/report-parts-in-report-designer-ssrs.md)</span></span>

 <span data-ttu-id="7ea5c-121">[Pianificazioni](subscriptions/schedules.md) ![icone cartella](media/hlp-16folder.gif "Icona Cartella")</span><span class="sxs-lookup"><span data-stu-id="7ea5c-121">![Folder icon](media/hlp-16folder.gif "Folder icon") [Schedules](subscriptions/schedules.md)</span></span>

 <span data-ttu-id="7ea5c-122">Sottoscrizioni dell' ![icona della cartella](media/hlp-16folder.gif "Icona Cartella") [e recapito &#40;Reporting Services&#41;](subscriptions/subscriptions-and-delivery-reporting-services.md)</span><span class="sxs-lookup"><span data-stu-id="7ea5c-122">![Folder icon](media/hlp-16folder.gif "Folder icon") [Subscriptions and Delivery &#40;Reporting Services&#41;](subscriptions/subscriptions-and-delivery-reporting-services.md)</span></span>

 <span data-ttu-id="7ea5c-123">![Icona della cartella](media/hlp-16folder.gif "Icona Cartella") [Reporting Services avvisi dati](../ssms/agent/alerts.md)</span><span class="sxs-lookup"><span data-stu-id="7ea5c-123">![Folder icon](media/hlp-16folder.gif "Folder icon") [Reporting Services Data Alerts](../ssms/agent/alerts.md)</span></span>

 <span data-ttu-id="7ea5c-124">![Icona della cartella](media/hlp-16folder.gif "Icona Cartella") [Power View](https://office.microsoft.com/excel-help/power-view-explore-visualize-and-present-your-data-HA102835634.aspx)</span><span class="sxs-lookup"><span data-stu-id="7ea5c-124">![Folder icon](media/hlp-16folder.gif "Folder icon") [Power View](https://office.microsoft.com/excel-help/power-view-explore-visualize-and-present-your-data-HA102835634.aspx)</span></span>

 <span data-ttu-id="7ea5c-125">![Icona della cartella](media/hlp-16folder.gif "Icona Cartella") [Reporting Services sicurezza e protezione](security/reporting-services-security-and-protection.md)</span><span class="sxs-lookup"><span data-stu-id="7ea5c-125">![Folder icon](media/hlp-16folder.gif "Folder icon") [Reporting Services Security and Protection](security/reporting-services-security-and-protection.md)</span></span>

 <span data-ttu-id="7ea5c-126">![Icona della cartella](media/hlp-16folder.gif "Icona Cartella") [accesso con URL &#40;SSRS&#41;](url-access-ssrs.md)</span><span class="sxs-lookup"><span data-stu-id="7ea5c-126">![Folder icon](media/hlp-16folder.gif "Folder icon") [URL Access &#40;SSRS&#41;](url-access-ssrs.md)</span></span>

 <span data-ttu-id="7ea5c-127">Estensioni ![icona cartella](media/hlp-16folder.gif "Icona Cartella") [&#40;SSRS&#41;](extensions-ssrs.md)</span><span class="sxs-lookup"><span data-stu-id="7ea5c-127">![Folder icon](media/hlp-16folder.gif "Folder icon") [Extensions &#40;SSRS&#41;](extensions-ssrs.md)</span></span>

 <span data-ttu-id="7ea5c-128">![Icona della cartella](media/hlp-16folder.gif "Icona Cartella") [Reporting Services strumenti](tools/reporting-services-tools.md)</span><span class="sxs-lookup"><span data-stu-id="7ea5c-128">![Folder icon](media/hlp-16folder.gif "Folder icon") [Reporting Services Tools](tools/reporting-services-tools.md)</span></span>

 <span data-ttu-id="7ea5c-129">![Icona della cartella](media/hlp-16folder.gif "Icona Cartella") [riferimento a errori ed eventi &#40;Reporting Services&#41;](troubleshooting/errors-and-events-reference-reporting-services.md)</span><span class="sxs-lookup"><span data-stu-id="7ea5c-129">![Folder icon](media/hlp-16folder.gif "Folder icon") [Errors and Events Reference &#40;Reporting Services&#41;](troubleshooting/errors-and-events-reference-reporting-services.md)</span></span>

 <span data-ttu-id="7ea5c-130">![Icona della cartella](media/hlp-16folder.gif "Icona Cartella") [riferimento alla funzionalità &#40;Reporting Services&#41;](feature-reference-reporting-services.md)</span><span class="sxs-lookup"><span data-stu-id="7ea5c-130">![Folder icon](media/hlp-16folder.gif "Folder icon") [Feature Reference &#40;Reporting Services&#41;](feature-reference-reporting-services.md)</span></span>

## <a name="see-also"></a><span data-ttu-id="7ea5c-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7ea5c-131">See Also</span></span>
 [<span data-ttu-id="7ea5c-132">Centro risorse di SQL Server</span><span class="sxs-lookup"><span data-stu-id="7ea5c-132">SQL Server Resource Center</span></span>](https://go.microsoft.com/fwlink/?linkID=219676)


