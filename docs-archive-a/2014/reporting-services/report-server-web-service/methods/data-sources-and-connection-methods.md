---
title: Origini dati e metodi di connessione | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- connections [Reporting Services], data sources
- reports [Reporting Services], data
- data sources [Reporting Services], methods
ms.assetid: 50999b52-fc7c-4333-9fb0-d04c37a4c90f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 29dd8dd1c002ab3b7d4594a4e25ec44bdb2cc8ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721096"
---
# <a name="data-sources-and-connection-methods"></a><span data-ttu-id="86b0a-102">Origini dati e metodi di connessione</span><span class="sxs-lookup"><span data-stu-id="86b0a-102">Data Sources and Connection Methods</span></span>
  <span data-ttu-id="86b0a-103">È possibile utilizzare questi metodi per impostare e gestire le connessioni all'origine dati e le credenziali.</span><span class="sxs-lookup"><span data-stu-id="86b0a-103">You can use these methods to set and manage data source connections and credentials.</span></span>  
  
|<span data-ttu-id="86b0a-104">Metodo</span><span class="sxs-lookup"><span data-stu-id="86b0a-104">Method</span></span>|<span data-ttu-id="86b0a-105">Azione</span><span class="sxs-lookup"><span data-stu-id="86b0a-105">Action</span></span>|  
|------------|------------|  
|<xref:ReportService2010.ReportingService2010.CreateDataSource%2A>|<span data-ttu-id="86b0a-106">Crea una nuova origine dati nel database del server di report o in una raccolta di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="86b0a-106">Creates a new data source in the report server database or SharePoint library.</span></span>|  
|<xref:ReportService2010.ReportingService2010.DisableDataSource%2A>|<span data-ttu-id="86b0a-107">Disabilita un'origine dati abilitata.</span><span class="sxs-lookup"><span data-stu-id="86b0a-107">Disables a data source that is enabled.</span></span>|  
|<xref:ReportService2010.ReportingService2010.EnableDataSource%2A>|<span data-ttu-id="86b0a-108">Abilita un'origine dati disabilitata.</span><span class="sxs-lookup"><span data-stu-id="86b0a-108">Enables a data source that is disabled.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetDataSourceContents%2A>|<span data-ttu-id="86b0a-109">Restituisce i contenuti di un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="86b0a-109">Returns the contents of a data source.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetItemDataSourcePrompts%2A>|<span data-ttu-id="86b0a-110">Ottiene i prompt dell'origine dati per un elemento specificato.</span><span class="sxs-lookup"><span data-stu-id="86b0a-110">Gets the data source prompts for a specified item.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetItemDataSources%2A>|<span data-ttu-id="86b0a-111">Restituisce le origini dati per un elemento del catalogo.</span><span class="sxs-lookup"><span data-stu-id="86b0a-111">Returns the data sources for an item in the catalog.</span></span>|  
|<xref:ReportService2010.ReportingService2010.ListDependentItems%2A>|<span data-ttu-id="86b0a-112">Restituisce un elenco di elementi del catalogo che fanno riferimento a un elemento del catalogo specificato.</span><span class="sxs-lookup"><span data-stu-id="86b0a-112">Returns a list of catalog items that reference a specified catalog item.</span></span>|  
|<xref:ReportService2010.ReportingService2010.ListSubscriptionsUsingDataSource%2A>|<span data-ttu-id="86b0a-113">Restituisce un elenco di sottoscrizioni associate a un'origine dati specifica.</span><span class="sxs-lookup"><span data-stu-id="86b0a-113">Returns a list of subscriptions that are associated with a given data source.</span></span>|  
|<xref:ReportService2010.ReportingService2010.SetDataSourceContents%2A>|<span data-ttu-id="86b0a-114">Imposta le proprietà di connessione associate al un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="86b0a-114">Sets the connection properties that are associated with a data source.</span></span>|  
|<xref:ReportService2010.ReportingService2010.SetItemDataSources%2A>|<span data-ttu-id="86b0a-115">Imposta le origini dati per un elemento in un database del server di report o in una raccolta di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="86b0a-115">Sets the data sources for an item in a report server database or SharePoint library.</span></span>|  
|<xref:ReportService2010.ReportingService2010.TestConnectForDataSourceDefinition%2A>|<span data-ttu-id="86b0a-116">Esegue il test di una connessione per un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="86b0a-116">Tests the connection for a data source.</span></span> <span data-ttu-id="86b0a-117">Questo metodo supporta il test diretto dell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="86b0a-117">This method supports the direct testing of the data source.</span></span>|  
|<xref:ReportService2010.ReportingService2010.TestConnectForItemDataSource%2A>|<span data-ttu-id="86b0a-118">Esegue il test di una connessione per un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="86b0a-118">Tests the connection for a data source.</span></span> <span data-ttu-id="86b0a-119">Questo metodo supporta il test di origini dati pubblicate utilizzate da report o modelli e origini dati condivise.</span><span class="sxs-lookup"><span data-stu-id="86b0a-119">This method supports the testing of published data sources that are used by reports or models and shared data sources.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="86b0a-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="86b0a-120">See Also</span></span>  
 <span data-ttu-id="86b0a-121">[Compilazione di applicazioni tramite servizio Web e .NET Framework](../net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="86b0a-121">[Building Applications Using the Web Service and the .NET Framework](../net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 <span data-ttu-id="86b0a-122">[Servizio Web ReportServer](../report-server-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="86b0a-122">[Report Server Web Service](../report-server-web-service.md) </span></span>  
 <span data-ttu-id="86b0a-123">[Metodi del servizio Web ReportServer](report-server-web-service-methods.md) </span><span class="sxs-lookup"><span data-stu-id="86b0a-123">[Report Server Web Service Methods](report-server-web-service-methods.md) </span></span>  
 [<span data-ttu-id="86b0a-124">Riferimento tecnico &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="86b0a-124">Technical Reference &#40;SSRS&#41;</span></span>](../../technical-reference-ssrs.md)  
  
  
