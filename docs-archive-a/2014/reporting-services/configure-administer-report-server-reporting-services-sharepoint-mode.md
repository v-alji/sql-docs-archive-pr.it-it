---
title: Configurazione e amministrazione di un server di report (modalità Reporting Services SharePoint) | Microsoft Docs
ms.custom: ''
ms.date: 11/25/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 846e86d0-fbbb-426c-97f9-f179cd42b390
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: ce7c1f524eec4785ddbc25d95c641d070ecbf408
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723603"
---
# <a name="configuration-and-administration-of-a-report-server-reporting-services-sharepoint-mode"></a><span data-ttu-id="ee135-102">Configurazione e amministrazione di un server di report (modalità SharePoint di Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="ee135-102">Configuration and Administration of a Report Server (Reporting Services SharePoint Mode)</span></span>
  [!INCLUDE[msCoName](../includes/msconame-md.md)]<span data-ttu-id="ee135-103">[!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] è una piattaforma per la creazione di report basata su server che fornisce una gamma completa di strumenti e servizi pronti per l'uso che consentono di creare, distribuire e gestire report per l'organizzazione, nonché di programmare funzionalità che consentono di estendere e personalizzare la funzionalità di creazione di report.</span><span class="sxs-lookup"><span data-stu-id="ee135-103">[!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] is a server-based reporting platform that provides a full range of ready-to-use tools and services to help you create, deploy, and manage reports for your organization, as well as programming features that enable you to extend and customize your reporting functionality.</span></span> <span data-ttu-id="ee135-104">È possibile integrare l'ambiente di gestione dei report con un prodotto SharePoint per sfruttare i vantaggi dell'utilizzo dell'ambiente di collaborazione fornito dai siti di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ee135-104">You can integrate your reporting environment with a SharePoint product to experience the benefits of using the collaborative environment provided by SharePoint sites.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ee135-105">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="ee135-105">In this section</span></span>  
 <span data-ttu-id="ee135-106">Utilizzare le sezioni seguenti per meglio comprendere concetti, scenari di distribuzione, procedure e altro ancora per l'integrazione dell'ambiente [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] con un prodotto o una tecnologia SharePoint:</span><span class="sxs-lookup"><span data-stu-id="ee135-106">Use the following sections to help you understand concepts, deployment scenarios, procedures, and more for integrating your [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] environment with a SharePoint product or technology:</span></span>  
  
-   <span data-ttu-id="ee135-107">Opzioni di menu in una raccolta documenti di SharePoint</span><span class="sxs-lookup"><span data-stu-id="ee135-107">Menu options in a SharePoint document library</span></span>  
  
    -   [<span data-ttu-id="ee135-108">Gestione avvisi dati per utenti di SharePoint</span><span class="sxs-lookup"><span data-stu-id="ee135-108">Data Alert Manager for SharePoint Users</span></span>](../../2014/reporting-services/data-alert-manager-for-sharepoint-users.md)  
  
    -   [<span data-ttu-id="ee135-109">Creare e gestire sottoscrizioni per server di report in modalità SharePoint</span><span class="sxs-lookup"><span data-stu-id="ee135-109">Create and Manage Subscriptions for SharePoint Mode Report Servers</span></span>](subscriptions/create-and-manage-subscriptions-for-sharepoint-mode-report-servers.md)  
  
    -   [<span data-ttu-id="ee135-110">Aggiornare le credenziali nelle origini dati dei report da un sito di SharePoint</span><span class="sxs-lookup"><span data-stu-id="ee135-110">Update Credentials in Report Data Sources from a SharePoint Site</span></span>](report-data/update-credentials-in-report-data-sources-from-a-sharepoint-site.md)  
  
    -   [<span data-ttu-id="ee135-111">Gestire set di dati condivisi</span><span class="sxs-lookup"><span data-stu-id="ee135-111">Manage Shared Datasets</span></span>](report-data/manage-shared-datasets.md)  
  
    -   [<span data-ttu-id="ee135-112">Impostazione dei parametri per un report pubblicato &#40;Reporting Services in modalità integrata SharePoint&#41;</span><span class="sxs-lookup"><span data-stu-id="ee135-112">Set Parameters on a Published Report &#40;Reporting Services in SharePoint Integrated Mode&#41;</span></span>](report-design/set-parameters-on-a-published-report-sharepoint-integrated-mode.md)  
  
    -   [<span data-ttu-id="ee135-113">Impostare le opzioni di elaborazione &#40;Reporting Services in modalità integrata SharePoint&#41;</span><span class="sxs-lookup"><span data-stu-id="ee135-113">Set Processing Options &#40;Reporting Services in SharePoint Integrated Mode&#41;</span></span>](../../2014/reporting-services/set-processing-options-reporting-services-in-sharepoint-integrated-mode.md)  
  
    -   [<span data-ttu-id="ee135-114">Opzioni di aggiornamento cache &#40;Gestione report&#41;</span><span class="sxs-lookup"><span data-stu-id="ee135-114">Cache Refresh Options &#40;Report Manager&#41;</span></span>](../../2014/reporting-services/cache-refresh-options-report-manager.md)  
  
-   [<span data-ttu-id="ee135-115">Funzionalità della raccolta siti Reporting Services</span><span class="sxs-lookup"><span data-stu-id="ee135-115">Reporting Services Site Collection Features</span></span>](../../2014/reporting-services/reporting-services-site-collection-features.md)  
  
-   [<span data-ttu-id="ee135-116">Attivare le funzionalità di integrazione per Power View e server di report in SharePoint</span><span class="sxs-lookup"><span data-stu-id="ee135-116">Activate the Report Server and Power View Integration Features in SharePoint</span></span>](activate-the-report-server-and-power-view-integration-features-in-sharepoint.md)  
  
-   [<span data-ttu-id="ee135-117">Funzionalità e impostazioni del sito di Reporting Services &#40;modalità SharePoint&#41;</span><span class="sxs-lookup"><span data-stu-id="ee135-117">Reporting Services Site Settings and Site Features&#40;SharePoint Mode&#41;</span></span>](../../2014/reporting-services/reporting-services-site-settings-and-site-features-sharepoint-mode.md)  
  
-   [<span data-ttu-id="ee135-118">Attivare la funzionalità Sincronizzazione file server di report in Amministrazione centrale SharePoint</span><span class="sxs-lookup"><span data-stu-id="ee135-118">Activate the Report Server File Sync Feature in SharePoint Central Administration</span></span>](../../2014/reporting-services/activate-report-server-file-sync-feature-sharepoint-central-administration.md)  
  
-   [<span data-ttu-id="ee135-119">Aggiungere tipi di contenuto del server di report a una raccolta &#40;Reporting Services in modalità integrata SharePoint&#41;</span><span class="sxs-lookup"><span data-stu-id="ee135-119">Add Report Server Content Types to a Library &#40;Reporting Services in SharePoint Integrated Mode&#41;</span></span>](../../2014/reporting-services/add-reporting-services-content-types-to-a-sharepoint-library.md)  
  
-   [<span data-ttu-id="ee135-120">Report in modalità locale e Report in modalità locale nel visualizzatore di report &#40;Reporting Services in modalità SharePoint&#41;</span><span class="sxs-lookup"><span data-stu-id="ee135-120">Local Mode vs. Connected Mode Reports in the Report Viewer &#40;Reporting Services in SharePoint Mode&#41;</span></span>](../../2014/reporting-services/local-vs-connected-mode-report-viewer-reporting-services-sharepoint-mode.md)  
  
-   [<span data-ttu-id="ee135-121">Caricare documenti in una raccolta di SharePoint &#40;Reporting Services in modalità SharePoint&#41;</span><span class="sxs-lookup"><span data-stu-id="ee135-121">Upload Documents to a SharePoint Library &#40;Reporting Services in SharePoint Mode&#41;</span></span>](../../2014/reporting-services/upload-documents-to-a-sharepoint-library-reporting-services-in-sharepoint-mode.md)  
  
-   [<span data-ttu-id="ee135-122">Impostare le opzioni di elaborazione &#40;Reporting Services in modalità integrata SharePoint&#41;</span><span class="sxs-lookup"><span data-stu-id="ee135-122">Set Processing Options &#40;Reporting Services in SharePoint Integrated Mode&#41;</span></span>](../../2014/reporting-services/set-processing-options-reporting-services-in-sharepoint-integrated-mode.md)  
  
 <span data-ttu-id="ee135-123">Per altre informazioni generali su [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], vedere [Reporting Services &#40;SSRS&#41;](create-deploy-and-manage-mobile-and-paginated-reports.md) nella documentazione online di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ee135-123">For more general information about [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], see [Reporting Services &#40;SSRS&#41;](create-deploy-and-manage-mobile-and-paginated-reports.md) in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Books Online.</span></span> <span data-ttu-id="ee135-124">Per informazioni su altri componenti, strumenti e risorse di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , vedere la [Documentazione online di SQL Server](../index.yml).</span><span class="sxs-lookup"><span data-stu-id="ee135-124">For information about other [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] components, tools, and resources, see [SQL Server Books Online](../index.yml).</span></span>  
  
  
