---
title: Integrazione di Reporting Services nelle applicazioni | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- integrating reports [Reporting Services]
- custom applications [SSRS]
- Reporting Services, application integration
- application integration [Reporting Services]
- reports [Reporting Services], integrating
ms.assetid: 49eb539c-d89b-4291-839a-0ec1a65cd270
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3ab92008c5beb4d931e8e781857d766bb56a1efd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623921"
---
# <a name="integrating-reporting-services-into-applications"></a><span data-ttu-id="bb9d0-102">Integrazione di Reporting Services nelle applicazioni</span><span class="sxs-lookup"><span data-stu-id="bb9d0-102">Integrating Reporting Services into Applications</span></span>
  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="bb9d0-103">è una piattaforma di creazione di report aperta ed estendibile progettata per fornire agli sviluppatori un set completo di API per lo sviluppo di soluzioni.</span><span class="sxs-lookup"><span data-stu-id="bb9d0-103">is an open and extensible reporting platform designed to provide developers with a comprehensive set of APIs for developing solutions.</span></span>  
  
 <span data-ttu-id="bb9d0-104">Sono disponibili tre opzioni per l'integrazione di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] nelle applicazioni personalizzate: il servizio Web ReportServer, noto anche come [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] API SOAP, i controlli ReportViewer per [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsOrcas](../../includes/vsorcas-md.md)] e l'accesso con URL.</span><span class="sxs-lookup"><span data-stu-id="bb9d0-104">There are three options for integrating [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] into custom applications: the Report Server Web service, also known as the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SOAP API, the ReportViewer controls for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsOrcas](../../includes/vsorcas-md.md)], and URL access.</span></span> <span data-ttu-id="bb9d0-105">Ogni opzione fornisce un approccio diverso per l'integrazione di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] nelle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="bb9d0-105">Each option provides a different approach for integrating [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] into your applications.</span></span>  
  
## <a name="report-server-web-service"></a><span data-ttu-id="bb9d0-106">servizio Web ReportServer</span><span class="sxs-lookup"><span data-stu-id="bb9d0-106">Report Server Web Service</span></span>  
 <span data-ttu-id="bb9d0-107">Il servizio Web ReportServer è l'interfaccia principale per lo sviluppo in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bb9d0-107">The Report Server Web service is the primary interface for developing against [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="bb9d0-108">Sia che si sviluppi codice per gestire il catalogo di report o che si sviluppi codice per il rendering dei report in un formato supportato, il servizio Web espone tutti i metodi necessari per integrare [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] nelle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="bb9d0-108">Whether you are developing code to manage your report catalog or developing code to render reports to a supported format, the Web service exposes all the necessary methods to integrate [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] into your applications.</span></span> <span data-ttu-id="bb9d0-109">Un esempio di tale applicazione è costituito da Gestione report, incluso in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], che usa il servizio Web per la gestione del database del server di report.</span><span class="sxs-lookup"><span data-stu-id="bb9d0-109">An example of one such application is Report Manager, which is included with [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]; it uses the Web service to manage the report server database.</span></span>  
  
## <a name="reportviewer-controls-for-visual-studio"></a><span data-ttu-id="bb9d0-110">Controlli ReportViewer per Visual Studio</span><span class="sxs-lookup"><span data-stu-id="bb9d0-110">ReportViewer Controls for Visual Studio</span></span>  
 <span data-ttu-id="bb9d0-111">I controlli ReportViewer inclusi in [!INCLUDE[vsOrcas](../../includes/vsorcas-md.md)] vengono utilizzati per l'integrazione delle funzionalità di visualizzazione dei report nelle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="bb9d0-111">The ReportViewer controls included with [!INCLUDE[vsOrcas](../../includes/vsorcas-md.md)] are used for integrating report viewing into your applications.</span></span> <span data-ttu-id="bb9d0-112">Sono disponibili due controlli, uno per le applicazioni basate su Windows Form e uno per le applicazioni Web Form.</span><span class="sxs-lookup"><span data-stu-id="bb9d0-112">There are two controls: one for Windows Forms-based applications and one for Web Forms applications.</span></span> <span data-ttu-id="bb9d0-113">Ogni controllo fornisce funzionalità per la visualizzazione dei report distribuiti in un server di report e consente di eseguire il rendering dei report presenti in un ambiente in cui non è stato installato un server di report.</span><span class="sxs-lookup"><span data-stu-id="bb9d0-113">Each control provides the capability for viewing reports that have been deployed to a report server as well as the ability to render reports that exist in an environment where a report server has not been installed.</span></span>  
  
## <a name="url-access"></a><span data-ttu-id="bb9d0-114">Accesso con URL</span><span class="sxs-lookup"><span data-stu-id="bb9d0-114">URL Access</span></span>  
 <span data-ttu-id="bb9d0-115">L'accesso con URL rappresenta un'altra opzione per l'integrazione delle funzionalità di visualizzazione dei report nelle applicazioni se non sono disponibili i controlli ReportViewer.</span><span class="sxs-lookup"><span data-stu-id="bb9d0-115">URL access is another option for integrating report viewing into your applications if the ReportViewer controls are not an option.</span></span> <span data-ttu-id="bb9d0-116">L'accesso con URL è inoltre utile per inviare agli utenti collegamenti ai report tramite posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="bb9d0-116">In addition, URL access is useful for sending links to reports to users via e-mail.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bb9d0-117">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="bb9d0-117">In This Section</span></span>  
 [<span data-ttu-id="bb9d0-118">Integrazione di Reporting Services tramite SOAP</span><span class="sxs-lookup"><span data-stu-id="bb9d0-118">Integrating Reporting Services Using SOAP</span></span>](../application-integration/integrating-reporting-services-using-soap.md)  
 <span data-ttu-id="bb9d0-119">Viene descritto come integrare le funzionalità di navigazione e gestione dei report di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] nelle applicazioni aziendali esistenti utilizzando il servizio Web ReportServer.</span><span class="sxs-lookup"><span data-stu-id="bb9d0-119">Describes how to integrate [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] report navigation and management into your existing business applications using the Report Server Web service.</span></span>  
  
 [<span data-ttu-id="bb9d0-120">Integrazione di Reporting Services tramite i controlli ReportViewer</span><span class="sxs-lookup"><span data-stu-id="bb9d0-120">Integrating Reporting Services Using the ReportViewer Controls</span></span>](../application-integration/integrating-reporting-services-using-reportviewer-controls.md)  
 <span data-ttu-id="bb9d0-121">Viene descritto come integrare le funzionalità di visualizzazione dei report nelle applicazioni esistenti utilizzando i controlli ReportViewer.</span><span class="sxs-lookup"><span data-stu-id="bb9d0-121">Describes how to integrate report viewing into your existing applications using the ReportViewer controls.</span></span>  
  
 [<span data-ttu-id="bb9d0-122">Integrazione di Reporting Services tramite l'accesso con URL</span><span class="sxs-lookup"><span data-stu-id="bb9d0-122">Integrating Reporting Services Using URL Access</span></span>](../application-integration/integrating-reporting-services-using-url-access.md)  
 <span data-ttu-id="bb9d0-123">Viene descritto come integrare le funzionalità di navigazione dei report di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] nelle applicazioni esistenti utilizzando l'accesso con URL.</span><span class="sxs-lookup"><span data-stu-id="bb9d0-123">Describes how to integrate [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] report navigation into your existing business applications using URL access.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb9d0-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bb9d0-124">See Also</span></span>  
 <span data-ttu-id="bb9d0-125">[Gestione report &#40;modalità nativa SSRS&#41;](../../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="bb9d0-125">[Report Manager  &#40;SSRS Native Mode&#41;](../../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span></span>  
 <span data-ttu-id="bb9d0-126">[Scelta tra accesso con URL e SOAP](../../../2014/reporting-services/application-integration/choosing-between-url-access-and-soap.md) </span><span class="sxs-lookup"><span data-stu-id="bb9d0-126">[Choosing Between URL Access and SOAP](../../../2014/reporting-services/application-integration/choosing-between-url-access-and-soap.md) </span></span>  
 <span data-ttu-id="bb9d0-127">[Riferimento tecnico &#40;SSRS&#41;](../../../2014/reporting-services/technical-reference-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="bb9d0-127">[Technical Reference &#40;SSRS&#41;](../../../2014/reporting-services/technical-reference-ssrs.md) </span></span>  
 [<span data-ttu-id="bb9d0-128">Servizio Web ReportServer</span><span class="sxs-lookup"><span data-stu-id="bb9d0-128">Report Server Web Service</span></span>](../report-server-web-service/report-server-web-service.md)  
  
  
