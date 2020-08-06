---
title: Metodi di rendering e di esecuzione | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- rendered reports [Reporting Services]
- reports [Reporting Services], execution options
- methods [Reporting Services], execution options
- methods [Reporting Services], rendering
ms.assetid: 12626aad-f0be-4653-87d0-60eb3a3fff78
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d0bc793e9a18e993989563fd3526ff12272f775c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721077"
---
# <a name="rendering-and-execution-methods"></a><span data-ttu-id="63799-102">Metodi di rendering e di esecuzione</span><span class="sxs-lookup"><span data-stu-id="63799-102">Rendering and Execution Methods</span></span>
  <span data-ttu-id="63799-103">Per gestire l'esecuzione, il rendering e la memorizzazione nella cache degli elementi, è possibile utilizzare i metodi seguenti.</span><span class="sxs-lookup"><span data-stu-id="63799-103">You can use these methods to manage item execution and caching, and report rendering.</span></span>  
  
|<span data-ttu-id="63799-104">Metodo</span><span class="sxs-lookup"><span data-stu-id="63799-104">Method</span></span>|<span data-ttu-id="63799-105">Azione</span><span class="sxs-lookup"><span data-stu-id="63799-105">Action</span></span>|  
|------------|------------|  
|<xref:ReportService2010.ReportingService2010.FlushCache%2A>|<span data-ttu-id="63799-106">Invalida la cache per un elemento.</span><span class="sxs-lookup"><span data-stu-id="63799-106">Invalidates the cache for an item.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetCacheOptions%2A>|<span data-ttu-id="63799-107">Restituisce la configurazione della cache per un elemento e le impostazioni che indicano la scadenza della copia dell'elemento memorizzata nella cache.</span><span class="sxs-lookup"><span data-stu-id="63799-107">Returns the cache configuration for an item and the settings that describe when the cached copy of the item expires.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetExecutionOptions%2A>|<span data-ttu-id="63799-108">Restituisce l'opzione di esecuzione e le impostazioni associate per un singolo elemento.</span><span class="sxs-lookup"><span data-stu-id="63799-108">Returns the execution option and associated settings for an individual item.</span></span>|  
|<xref:ReportService2010.ReportingService2010.ListExecutionSettings%2A>|<span data-ttu-id="63799-109">Restituisce un elenco di impostazioni di esecuzione supportate.</span><span class="sxs-lookup"><span data-stu-id="63799-109">Returns a list of supported execution settings.</span></span>|  
|<xref:ReportExecution2005.ReportExecutionService.Render%2A>|<span data-ttu-id="63799-110">Elabora il report specificato e ne esegue il rendering in un formato specificato.</span><span class="sxs-lookup"><span data-stu-id="63799-110">Processes the specified report and renders it in a specified format.</span></span>|  
|<xref:ReportService2010.ReportingService2010.SetCacheOptions%2A>|<span data-ttu-id="63799-111">Configura un elemento per la memorizzazione nella cache e fornisce le impostazioni che specificano il momento in cui scade la copia memorizzata nella cache dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="63799-111">Configures an item to be cached and provides settings that specify when the cached copy of the item expires.</span></span>|  
|<xref:ReportService2010.ReportingService2010.SetExecutionOptions%2A>|<span data-ttu-id="63799-112">Imposta le opzioni di esecuzione e le proprietà di esecuzione associate per un singolo elemento.</span><span class="sxs-lookup"><span data-stu-id="63799-112">Sets execution options and associated execution properties for a specified item.</span></span>|  
|<xref:ReportService2010.ReportingService2010.UpdateItemExecutionSnapshot%2A>|<span data-ttu-id="63799-113">Genera uno snapshot di esecuzione per un elemento specificato.</span><span class="sxs-lookup"><span data-stu-id="63799-113">Generates an item execution snapshot for a specified item.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="63799-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="63799-114">See Also</span></span>  
 <span data-ttu-id="63799-115">[Compilazione di applicazioni tramite servizio Web e .NET Framework](../net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="63799-115">[Building Applications Using the Web Service and the .NET Framework](../net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 <span data-ttu-id="63799-116">[Servizio Web ReportServer](../report-server-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="63799-116">[Report Server Web Service](../report-server-web-service.md) </span></span>  
 <span data-ttu-id="63799-117">[Metodi del servizio Web ReportServer](report-server-web-service-methods.md) </span><span class="sxs-lookup"><span data-stu-id="63799-117">[Report Server Web Service Methods](report-server-web-service-methods.md) </span></span>  
 [<span data-ttu-id="63799-118">Riferimento tecnico &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="63799-118">Technical Reference &#40;SSRS&#41;</span></span>](../../technical-reference-ssrs.md)  
  
  
