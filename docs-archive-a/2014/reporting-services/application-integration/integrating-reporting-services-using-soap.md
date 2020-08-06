---
title: Integrazione di Reporting Services tramite SOAP | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- Report Server Web service, application integration
- SOAP [Reporting Services]
- SOAP [Reporting Services], about report integration
- integrating reports [Reporting Services]
- Web service [Reporting Services], application integration
ms.assetid: 6bc17af5-883c-4bfa-87d9-48cd7056d145
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7b6fffd65b22900d7c505c4b50ec290b95fe9ab4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623915"
---
# <a name="integrating-reporting-services-using-soap"></a><span data-ttu-id="bf3c4-102">Integrazione di Reporting Services tramite SOAP</span><span class="sxs-lookup"><span data-stu-id="bf3c4-102">Integrating Reporting Services Using SOAP</span></span>
  <span data-ttu-id="bf3c4-103">L' [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] API SOAP fornisce diversi endpoint del servizio Web per lo sviluppo di soluzioni di creazione di report personalizzate.</span><span class="sxs-lookup"><span data-stu-id="bf3c4-103">The [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SOAP API provides several Web service endpoints for developing custom reporting solutions.</span></span> <span data-ttu-id="bf3c4-104">Gli endpoint rientrano attualmente in due categorie, ovvero gestione ed esecuzione.</span><span class="sxs-lookup"><span data-stu-id="bf3c4-104">The endpoints currently fall into two categories: management and execution.</span></span> <span data-ttu-id="bf3c4-105">La funzionalità di gestione viene esposta tramite gli endpoint <xref:ReportService2005>, <xref:ReportService2006> e <xref:ReportService2010>.</span><span class="sxs-lookup"><span data-stu-id="bf3c4-105">The management functionality is exposed through the <xref:ReportService2005>, <xref:ReportService2006>, and <xref:ReportService2010> endpoints.</span></span> <span data-ttu-id="bf3c4-106">L'endpoint <xref:ReportService2005> viene utilizzato per la gestione di un server di report configurato in modalità nativa, mentre l'endpoint <xref:ReportService2006> viene utilizzato per la gestione di un server di report configurato per la modalità integrata SharePoint.</span><span class="sxs-lookup"><span data-stu-id="bf3c4-106">The <xref:ReportService2005> endpoint is used for managing a report server that is configured in native mode and the <xref:ReportService2006> endpoint is used for managing a report server that is configured for SharePoint integrated mode.</span></span> <span data-ttu-id="bf3c4-107">L'endpoint <xref:ReportService2010> unisce le funzionalità di <xref:ReportService2005> e <xref:ReportService2006> e può gestire gli oggetti in un server di report configurati per la modalità nativa o per la modalità integrata SharePoint.</span><span class="sxs-lookup"><span data-stu-id="bf3c4-107">The <xref:ReportService2010> merges the functionalities of <xref:ReportService2005> and <xref:ReportService2006> and can manage a report server that is configured for either native or SharePoint integrated mode.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bf3c4-108">Gli endpoint <xref:ReportService2005> e <xref:ReportService2006> sono deprecati in [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bf3c4-108">The <xref:ReportService2005> and <xref:ReportService2006> endpoints are deprecated in [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)].</span></span> <span data-ttu-id="bf3c4-109">L'endpoint <xref:ReportService2010> include le funzionalità di entrambi gli endpoint e contiene caratteristiche di gestione aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="bf3c4-109">The <xref:ReportService2010> endpoint includes the functionalities of both endpoints and contains additional management features.</span></span>  
  
 <span data-ttu-id="bf3c4-110">La funzionalità di esecuzione viene esposta tramite l'endpoint <xref:ReportExecution2005> e viene utilizzata quando il server di report è configurato in modalità nativa o in modalità integrata SharePoint.</span><span class="sxs-lookup"><span data-stu-id="bf3c4-110">The execution functionality is exposed through the <xref:ReportExecution2005> endpoint and it is used when the report server is configured in native or SharePoint integrated mode.</span></span> <span data-ttu-id="bf3c4-111">Negli argomenti seguenti viene illustrato come utilizzare questi endpoint per lo sviluppo di soluzioni di creazione di report in [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, in SharePoint e nelle applicazioni Web.</span><span class="sxs-lookup"><span data-stu-id="bf3c4-111">The following topics show how these endpoints can be used for developing reporting solutions in [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, SharePoint, and Web applications.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bf3c4-112">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="bf3c4-112">In This Section</span></span>  
 [<span data-ttu-id="bf3c4-113">Uso dell'API SOAP in un'applicazione Windows</span><span class="sxs-lookup"><span data-stu-id="bf3c4-113">Using the SOAP API in a Windows Application</span></span>](integrating-reporting-services-using-soap-windows-application.md)  
 <span data-ttu-id="bf3c4-114">Viene descritto come utilizzare l'API SOAP per integrare [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] in un ambiente Windows.</span><span class="sxs-lookup"><span data-stu-id="bf3c4-114">Describes how to use the SOAP API to integrate [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] into a Windows environment.</span></span>  
  
 [<span data-ttu-id="bf3c4-115">Uso dell'API SOAP in un'applicazione Web</span><span class="sxs-lookup"><span data-stu-id="bf3c4-115">Using the SOAP API in a Web Application</span></span>](integrating-reporting-services-using-soap-web-application.md)  
 <span data-ttu-id="bf3c4-116">Viene descritto come utilizzare l'API SOAP per integrare [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] in un ambiente Web.</span><span class="sxs-lookup"><span data-stu-id="bf3c4-116">Describes how to use the SOAP API to integrate [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] into a Web environment.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf3c4-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bf3c4-117">See Also</span></span>  
 <span data-ttu-id="bf3c4-118">[Integrazione di Reporting Services in applicazioni](../application-integration/integrating-reporting-services-into-applications.md) </span><span class="sxs-lookup"><span data-stu-id="bf3c4-118">[Integrating Reporting Services into Applications](../application-integration/integrating-reporting-services-into-applications.md) </span></span>  
 <span data-ttu-id="bf3c4-119">[Servizio Web ReportServer](../report-server-web-service/report-server-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="bf3c4-119">[Report Server Web Service](../report-server-web-service/report-server-web-service.md) </span></span>  
 [<span data-ttu-id="bf3c4-120">Compilazione di applicazioni tramite servizio Web e .NET Framework</span><span class="sxs-lookup"><span data-stu-id="bf3c4-120">Building Applications Using the Web Service and the .NET Framework</span></span>](../report-server-web-service/net-framework/building-applications-using-the-web-service-and-the-net-framework.md)  
  
  
