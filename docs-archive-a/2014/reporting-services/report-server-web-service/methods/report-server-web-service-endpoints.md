---
title: Endpoint del servizio Web ReportServer | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- management endpoints [Reporting Services]
- Web service [Reporting Services], endpoints
- endpoints [Reporting Services]
- execution endpoints [Reporting Services]
- Report Server Web service, endpoints
ms.assetid: f3f5d85f-9359-4508-bc5a-7f78a3cf7421
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 70281c5171eb37d9888d663542a7850820c81bea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717358"
---
# <a name="report-server-web-service-endpoints"></a><span data-ttu-id="2a179-102">Endpoint del servizio Web ReportServer</span><span class="sxs-lookup"><span data-stu-id="2a179-102">Report Server Web Service Endpoints</span></span>
  <span data-ttu-id="2a179-103">Il servizio Web ReportServer fornisce diversi endpoint per la gestione di un server di report e per l'esecuzione e la navigazione dei report.</span><span class="sxs-lookup"><span data-stu-id="2a179-103">The Report Server Web service provides several endpoints for managing a report server as well as executing and navigating reports.</span></span>  
  
## <a name="the-management-endpoints"></a><span data-ttu-id="2a179-104">Endpoint di gestione</span><span class="sxs-lookup"><span data-stu-id="2a179-104">The Management Endpoints</span></span>  
 <span data-ttu-id="2a179-105">Per la gestione degli oggetti in un server di report sono disponibili tre endpoint, <xref:ReportService2005>, <xref:ReportService2006> e <xref:ReportService2010>.</span><span class="sxs-lookup"><span data-stu-id="2a179-105">There are three endpoints available for managing objects on a report server, <xref:ReportService2005>, <xref:ReportService2006>, and <xref:ReportService2010>.</span></span> <span data-ttu-id="2a179-106">L'endpoint <xref:ReportService2005> viene utilizzato per la gestione degli oggetti in un server di report configurato per la modalità nativa.</span><span class="sxs-lookup"><span data-stu-id="2a179-106">The <xref:ReportService2005> endpoint is used for managing objects on a report server that is configured for native mode.</span></span> <span data-ttu-id="2a179-107">L'endpoint <xref:ReportService2006> viene utilizzato per la gestione degli oggetti in un server di report configurato per la modalità integrata SharePoint.</span><span class="sxs-lookup"><span data-stu-id="2a179-107">The <xref:ReportService2006> endpoint is used for managing objects on a report server that is configured for SharePoint integrated mode.</span></span> <span data-ttu-id="2a179-108">L'endpoint <xref:ReportService2010> unisce le funzionalità di <xref:ReportService2005> e <xref:ReportService2006> e può gestire gli oggetti in un server di report configurati per la modalità nativa o per la modalità integrata SharePoint.</span><span class="sxs-lookup"><span data-stu-id="2a179-108">The <xref:ReportService2010> endpoint merges the functionalities of <xref:ReportService2005> and <xref:ReportService2006> and can manage objects on a report server that are configured for either native or SharePoint integrated mode.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="2a179-109">Quando un server di report è configurato per la modalità integrata SharePoint, le API di <xref:ReportService2005> restituiscono un errore `rsOperationNotSupportedSharePointMode`.</span><span class="sxs-lookup"><span data-stu-id="2a179-109">When a report server is configured for SharePoint integrated mode, the <xref:ReportService2005> APIs will return an `rsOperationNotSupportedSharePointMode` error.</span></span> <span data-ttu-id="2a179-110">Se il server di report è configurato per la modalità nativa, le API di <xref:ReportService2006> restituiscono un errore `rsOperationNotSupportedNativeMode`.</span><span class="sxs-lookup"><span data-stu-id="2a179-110">If the report server is configured for native mode, the <xref:ReportService2006> APIs will return an `rsOperationNotSupportedNativeMode` error.</span></span> <span data-ttu-id="2a179-111">In modo analogo, se le API specifiche della modalità in <xref:ReportService2010> vengono utilizzate in modalità non previste, restituiranno gli errori corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="2a179-111">Similarly, when mode-specific APIs in <xref:ReportService2010> are used on unintended modes, the APIs will return the respective errors.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2a179-112">Gli endpoint <xref:ReportService2005> e <xref:ReportService2006> sono deprecati in [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2a179-112">The <xref:ReportService2005> and <xref:ReportService2006> endpoints are deprecated in [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)].</span></span> <span data-ttu-id="2a179-113">L'endpoint <xref:ReportService2010> include le funzionalità di entrambi gli endpoint e contiene caratteristiche di gestione aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="2a179-113">The <xref:ReportService2010> endpoint includes the functionalities of both endpoints and contains additional management features.</span></span>  
  
 <span data-ttu-id="2a179-114">Se il server di report è configurato per la modalità nativa o la modalità integrata SharePoint, è possibile accedere al codice WSDL per l'endpoint di gestione utilizzando uno dei seguenti URL:</span><span class="sxs-lookup"><span data-stu-id="2a179-114">If the report server is configured for native mode or SharePoint integrate mode, the WSDL for the management endpoint can be accessed using one of the following URL:</span></span>  
  
```  
http://<Server Name>/ReportServer/ReportService2010.asmx?wsdl  
```  
  
 <span data-ttu-id="2a179-115">Per altre informazioni, vedere [Accesso all'API SOAP](../accessing-the-soap-api.md).</span><span class="sxs-lookup"><span data-stu-id="2a179-115">For more information, see [Accessing the SOAP API](../accessing-the-soap-api.md).</span></span>  
  
## <a name="the-execution-endpoint"></a><span data-ttu-id="2a179-116">Endpoint di esecuzione</span><span class="sxs-lookup"><span data-stu-id="2a179-116">The Execution Endpoint</span></span>  
 <span data-ttu-id="2a179-117">L'endpoint <xref:ReportExecution2005> consente agli sviluppatori di personalizzare in modo semplice le fasi di elaborazione e rendering dei report da un server di report sia in modalità nativa che in modalità integrata SharePoint.</span><span class="sxs-lookup"><span data-stu-id="2a179-117">The <xref:ReportExecution2005> endpoint makes it easy for developers to customize report processing and rendering from a report server in both native and SharePoint integrated modes.</span></span> <span data-ttu-id="2a179-118">L'endpoint include le classi e i metodi disponibili nelle versioni precedenti del servizio Web ReportServer.</span><span class="sxs-lookup"><span data-stu-id="2a179-118">The endpoint includes classes and methods that existed in earlier versions of the Report Server Web service.</span></span> <span data-ttu-id="2a179-119">Al servizio Web ReportServer sono inoltre stati aggiunti numerosi nuovi metodi e classi esposti tramite l'endpoint di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="2a179-119">In addition, many new classes and methods have been added to the Report Server Web service that are exposed through the execution endpoint.</span></span>  
  
 <span data-ttu-id="2a179-120">È possibile accedere al codice WSDL per l'endpoint di gestione utilizzando l'URL seguente:</span><span class="sxs-lookup"><span data-stu-id="2a179-120">The WSDL for the management endpoint can be accessed using the following URL:</span></span>  
  
```  
http://<Server Name>/ReportServer/ReportExecution2005.asmx?wsdl  
```  
  
 <span data-ttu-id="2a179-121">Se il server di report è configurato per la modalità integrata SharePoint, è possibile accedere al codice WSDL utilizzando l'URL seguente:</span><span class="sxs-lookup"><span data-stu-id="2a179-121">If the report server is configured for SharePoint integrate mode, the WSDL can be accessed using the following URL:</span></span>  
  
```  
http://<Server Name>/<Site Name>/_vti_bin/ReportServer/ReportExecution2005.asmx?wsdl  
```  
  
 <span data-ttu-id="2a179-122">Per altre informazioni, vedere [Accesso all'API SOAP](../accessing-the-soap-api.md).</span><span class="sxs-lookup"><span data-stu-id="2a179-122">For more information, please see [Accessing the SOAP API](../accessing-the-soap-api.md).</span></span>  
  
## <a name="sharepoint-proxy-endpoints"></a><span data-ttu-id="2a179-123">Endpoint proxy di SharePoint</span><span class="sxs-lookup"><span data-stu-id="2a179-123">SharePoint Proxy Endpoints</span></span>  
 <span data-ttu-id="2a179-124">Quando un server di report è configurato per la modalità integrata SharePoint ed è stato installato il componente aggiuntivo [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)], nel server SharePoint viene installato un set di endpoint proxy.</span><span class="sxs-lookup"><span data-stu-id="2a179-124">When a report server is configured for SharePoint integrated mode and the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] Add-in has been installed, a set of proxy endpoints are installed on the SharePoint server.</span></span> <span data-ttu-id="2a179-125">Gli endpoint proxy rappresentano l'API principale per lo sviluppo di soluzioni di report quando un server di report è configurato per la modalità integrata SharePoint.</span><span class="sxs-lookup"><span data-stu-id="2a179-125">The proxy endpoints are the primary API for developing report solutions when a report server is configured for SharePoint integrated mode.</span></span> <span data-ttu-id="2a179-126">Quando lo sviluppo viene eseguito negli endpoint proxy, il componente aggiuntivo [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] gestisce lo scambio di credenziali tra il server SharePoint e il server di report nella modalità di autenticazione Account attendibile.</span><span class="sxs-lookup"><span data-stu-id="2a179-126">When developing against the proxy endpoints, the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] Add-in manages the exchange of credentials between the SharePoint server and the report server in Trusted account authentication mode.</span></span> <span data-ttu-id="2a179-127">Quando lo sviluppo viene eseguito negli endpoint del server di report, l'applicazione chiamante deve gestire lo scambio di credenziali nella modalità di autenticazione Account attendibile.</span><span class="sxs-lookup"><span data-stu-id="2a179-127">When developing against the report server endpoints, the calling application will have to manage the credential exchange in Trusted account authentication mode.</span></span> <span data-ttu-id="2a179-128">Nella tabella seguente sono elencati gli endpoint installati con il componente aggiuntivo [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2a179-128">The following table lists the endpoints that are installed with the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] Add-in.</span></span>  
  
|<span data-ttu-id="2a179-129">Endpoint proxy</span><span class="sxs-lookup"><span data-stu-id="2a179-129">Proxy Endpoint</span></span>|<span data-ttu-id="2a179-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2a179-130">Description</span></span>|  
|--------------------|-----------------|  
|<xref:ReportService2006>|<span data-ttu-id="2a179-131">Fornisce le API per la gestione di un server di report configurato per la modalità integrata SharePoint.</span><span class="sxs-lookup"><span data-stu-id="2a179-131">Provides the APIs for managing a report server that is configured for SharePoint integrate mode.</span></span> <span data-ttu-id="2a179-132">**Nota:**  Questo endpoint è deprecato in [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2a179-132">**Note:**  This endpoint is deprecated in [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)].</span></span>|  
|<xref:ReportService2010>|<span data-ttu-id="2a179-133">Fornisce le API per la gestione di un server di report configurato per la modalità nativa o la modalità integrata SharePoint.</span><span class="sxs-lookup"><span data-stu-id="2a179-133">Provides the APIs for managing a report server that is configured for either native or SharePoint integrated mode.</span></span>|  
|<xref:ReportExecution2005>|<span data-ttu-id="2a179-134">Fornisce le API per l'esecuzione e la navigazione dei report.</span><span class="sxs-lookup"><span data-stu-id="2a179-134">Provides the APIs for running and navigating reports.</span></span>|  
|<xref:ReportServiceAuthentication>|<span data-ttu-id="2a179-135">Fornisce le API per l'autenticazione degli utenti rispetto a un server di report quando l'applicazione Web SharePoint è configurata per l'autenticazione basata su form.</span><span class="sxs-lookup"><span data-stu-id="2a179-135">Provides the APIs for authenticating users against a report server when the SharePoint Web application is configured for Forms Authentication.</span></span>|  
  
 <span data-ttu-id="2a179-136">Di seguito sono riportati alcuni URL di esempio che consentono di fare riferimento agli endpoint proxy in un sito di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="2a179-136">The following are example URLs for referencing the proxy endpoints on a SharePoint site.</span></span>  
  
```  
http://<Server Name>/<Site Name>/_vti_bin/ReportServer/ReportService2010.asmx  
```  
  
```  
http://<Server Name>/<Site Name>/_vti_bin/ReportServer/ReportExecution2005.asmx  
```  
  
```  
http://<Server Name>/<Site Name>/_vti_bin/ReportServer/ReportServiceAuthentication.asmx  
```  
  
## <a name="see-also"></a><span data-ttu-id="2a179-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2a179-137">See Also</span></span>  
 [<span data-ttu-id="2a179-138">Compilazione di applicazioni tramite servizio Web e .NET Framework</span><span class="sxs-lookup"><span data-stu-id="2a179-138">Building Applications Using the Web Service and the .NET Framework</span></span>](../net-framework/building-applications-using-the-web-service-and-the-net-framework.md)  
  
  
