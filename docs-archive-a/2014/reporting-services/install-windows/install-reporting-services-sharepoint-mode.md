---
title: Installazione in modalità SharePoint di Reporting Services (SharePoint 2010 e SharePoint 2013) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- default configuration [Reporting Services]
- installing Reporting Services, SharePoint integrated mode
- installation options [Reporting Services]
ms.assetid: ac6cba68-2665-4a39-8fa3-cb7d7e6723c0
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c27b6f9fbeebcc896b1a6097cb51e8d2e15924bf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624541"
---
# <a name="reporting-services-sharepoint-mode-installation-sharepoint-2010-and-sharepoint-2013"></a><span data-ttu-id="aac15-102">Installazione della modalità SharePoint di Reporting Services (SharePoint 2010 e SharePoint 2013)</span><span class="sxs-lookup"><span data-stu-id="aac15-102">Reporting Services SharePoint Mode Installation (SharePoint 2010 and SharePoint 2013)</span></span>
  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]<span data-ttu-id="aac15-103">in modalità SharePoint è una raccolta di componenti server che forniscono la generazione e il recapito di report, basati su [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e [!INCLUDE[msCoName](../../includes/msconame-md.md)] prodotti SharePoint.</span><span class="sxs-lookup"><span data-stu-id="aac15-103">in SharePoint mode is a collection of server components that provide report generation and delivery, based on [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and [!INCLUDE[msCoName](../../includes/msconame-md.md)] SharePoint products.</span></span>  
  
 <span data-ttu-id="aac15-104">L'esecuzione di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] in modalità SharePoint fornisce [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] e funzionalità di avvisi dati.</span><span class="sxs-lookup"><span data-stu-id="aac15-104">Running [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] in SharePoint mode provides the [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] and data alerting features.</span></span> <span data-ttu-id="aac15-105">Per ulteriori informazioni sulle funzionalità in modalità SharePoint, vedere la sezione "supporto della funzionalità e differenze di comportamento in base alla modalità server" in [Reporting Services server di report](../reporting-services-report-server.md)</span><span class="sxs-lookup"><span data-stu-id="aac15-105">For more information regarding features in SharePoint mode, see the section "Feature Support and Behavior Differences by Server Mode" in [Reporting Services Report Server](../reporting-services-report-server.md)</span></span>  
  
 <span data-ttu-id="aac15-106">Esistono due installazioni fondamentali necessarie per [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] in modalità SharePoint:</span><span class="sxs-lookup"><span data-stu-id="aac15-106">There are two fundamental installations needed for [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] in SharePoint mode:</span></span>  
  
|<span data-ttu-id="aac15-107">Installazione</span><span class="sxs-lookup"><span data-stu-id="aac15-107">Installation</span></span>|<span data-ttu-id="aac15-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="aac15-108">Description</span></span>|  
|------------------|-----------------|  
|<span data-ttu-id="aac15-109">[!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Componente aggiuntivo per prodotti SharePoint.</span><span class="sxs-lookup"><span data-stu-id="aac15-109">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] add-in for SharePoint products.</span></span>|<span data-ttu-id="aac15-110">Il componente aggiuntivo installa le pagine dell'interfaccia utente (Interfaccia utente) [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] e funzionalità in un server Web front-end di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="aac15-110">The add-in installs the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] user interface (UI) pages and features on a SharePoint web front-end server.</span></span> <span data-ttu-id="aac15-111">Le funzionalità dell'interfaccia utente includono [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)], pagine dell'amministrazione in Amministrazione centrale SharePoint, pagine delle funzionalità utilizzate nelle raccolte documenti di SharePoint e pagine di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] avvisi dati.</span><span class="sxs-lookup"><span data-stu-id="aac15-111">The UI features include [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)], administration pages in SharePoint Central Administration, feature pages used within SharePoint document libraries, and [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Data Alerting pages.</span></span>|  
|<span data-ttu-id="aac15-112">[!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Server di report installato in modalità SharePoint</span><span class="sxs-lookup"><span data-stu-id="aac15-112">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] report server installed in SharePoint Mode</span></span>|<span data-ttu-id="aac15-113">Il server di report gestisce l'elaborazione di dati e report e del rendering, oltre all'elaborazione delle sottoscrizioni e degli avvisi dati.</span><span class="sxs-lookup"><span data-stu-id="aac15-113">The report server handles the data and report processing and rendering as well subscription and Data Alert processing.</span></span> <span data-ttu-id="aac15-114">Il server di report della modalità SharePoint è configurato e installato come un servizio Shared SharePoint.</span><span class="sxs-lookup"><span data-stu-id="aac15-114">The SharePoint mode report server is architected and installed as a SharePoint Shared Service.</span></span>|  
  
 <span data-ttu-id="aac15-115">Per installare [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], utilizzare i supporti di installazione di [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aac15-115">To install [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], use the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] installation media.</span></span>  
  
 <span data-ttu-id="aac15-116">Per istruzioni sugli scenari di distribuzione avanzati, vedere elenco di controllo per la [distribuzione: Reporting Services, Power View e PowerPivot per SharePoint](../../sql-server/install/deployment-checklist-reporting-services-power-view-power-pivot-for-sharepoint.md) e [l'elenco di controllo per la distribuzione: installare Reporting Services in una farm di SharePoint esistente](../../sql-server/install/deployment-checklist-install-reporting-services-existing-sharepoint-farm.md).</span><span class="sxs-lookup"><span data-stu-id="aac15-116">For instructions on advanced deployment scenarios, see [Deployment Checklist: Reporting Services, Power View, and PowerPivot for SharePoint](../../sql-server/install/deployment-checklist-reporting-services-power-view-power-pivot-for-sharepoint.md) and [Deployment Checklist: Install Reporting Services into an Existing SharePoint Farm](../../sql-server/install/deployment-checklist-install-reporting-services-existing-sharepoint-farm.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="aac15-117">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="aac15-117">In This Section</span></span>  
 [<span data-ttu-id="aac15-118">Combinazioni supportate di SharePoint e Reporting Services server e componenti aggiuntivi &#40;SQL Server 2014&#41;</span><span class="sxs-lookup"><span data-stu-id="aac15-118">Supported Combinations of SharePoint and Reporting Services Server and Add-in &#40;SQL Server 2014&#41;</span></span>](supported-combinations-of-sharepoint-and-reporting-services-server.md)  
  
 [<span data-ttu-id="aac15-119">Installare la modalità SharePoint di Reporting Services per SharePoint 2013</span><span class="sxs-lookup"><span data-stu-id="aac15-119">Install Reporting Services SharePoint Mode for SharePoint 2013</span></span>](../../sql-server/install/install-reporting-services-sharepoint-mode-for-sharepoint-2013.md)  
  
 [<span data-ttu-id="aac15-120">Installare la modalità SharePoint di Reporting Services per SharePoint 2010</span><span class="sxs-lookup"><span data-stu-id="aac15-120">Install Reporting Services SharePoint Mode for SharePoint 2010</span></span>](../../sql-server/install/install-reporting-services-sharepoint-mode-for-sharepoint-2010.md)  
  
 [<span data-ttu-id="aac15-121">Installare o disinstallare il componente aggiuntivo Reporting Services per SharePoint &#40;SharePoint 2010 e SharePoint 2013&#41;</span><span class="sxs-lookup"><span data-stu-id="aac15-121">Install or Uninstall the Reporting Services Add-in for SharePoint &#40;SharePoint 2010 and SharePoint 2013&#41;</span></span>](install-or-uninstall-the-reporting-services-add-in-for-sharepoint.md)  
  
 [<span data-ttu-id="aac15-122">Posizione in cui trovare il componente aggiuntivo Reporting Services per prodotti SharePoint</span><span class="sxs-lookup"><span data-stu-id="aac15-122">Where to find the Reporting Services add-in for SharePoint Products</span></span>](where-to-find-the-reporting-services-add-in-for-sharepoint-products.md)  
  
 [<span data-ttu-id="aac15-123">Aggiungere un ulteriore server di report a una farm &#40;con scalabilità orizzontale SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="aac15-123">Add an Additional Report Server to a Farm &#40;SSRS Scale-out&#41;</span></span>](add-an-additional-report-server-to-a-farm-ssrs-scale-out.md)  
  
 [<span data-ttu-id="aac15-124">Aggiungere un ulteriore front-end Web di Reporting Services a una farm</span><span class="sxs-lookup"><span data-stu-id="aac15-124">Add an Additional Reporting Services Web Front-end to a Farm</span></span>](add-an-additional-reporting-services-web-front-end-to-a-farm.md)  
  
 [<span data-ttu-id="aac15-125">Configurare le impostazioni di posta elettronica per l'applicazione di servizio Reporting Services &#40;SharePoint 2010 e SharePoint 2013&#41;</span><span class="sxs-lookup"><span data-stu-id="aac15-125">Configure E-mail for a Reporting Services Service Application &#40;SharePoint 2010 and SharePoint 2013&#41;</span></span>](configure-e-mail-for-a-reporting-services-service-application.md)  
  
 [<span data-ttu-id="aac15-126">Provisioning di sottoscrizioni e avvisi per le applicazioni di servizio SSRS</span><span class="sxs-lookup"><span data-stu-id="aac15-126">Provision Subscriptions and Alerts for SSRS Service Applications</span></span>](provision-subscriptions-and-alerts-for-ssrs-service-applications.md)  
  
 [<span data-ttu-id="aac15-127">Attestazioni per il servizio token Windows &#40;C2WTS&#41; e Reporting Services</span><span class="sxs-lookup"><span data-stu-id="aac15-127">Claims to Windows Token Service &#40;C2WTS&#41; and Reporting Services</span></span>](../../sql-server/install/claims-to-windows-token-service-c2wts-and-reporting-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="aac15-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aac15-128">See Also</span></span>  
 <span data-ttu-id="aac15-129">[Architettura e flusso di lavoro degli avvisi dati](../reporting-services-data-alerts.md#AlertingWF) </span><span class="sxs-lookup"><span data-stu-id="aac15-129">[Data Alerts Architecture and Workflow](../reporting-services-data-alerts.md#AlertingWF) </span></span>  
 [<span data-ttu-id="aac15-130">Gestione avvisi dati per gli amministratori di avvisi</span><span class="sxs-lookup"><span data-stu-id="aac15-130">Data Alert Manager for Alerting Administrators</span></span>](../data-alert-manager-for-alerting-administrators.md)  
  
  
