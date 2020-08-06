---
title: Metodi di pianificazione | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- schedules [Reporting Services], methods
- reports [Reporting Services], scheduling
- shared schedules [Reporting Services], methods
- methods [Reporting Services], scheduling
ms.assetid: 68ae13f9-d91e-4572-a82a-8fa42001569e
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 735da4f22d523fd40dd031f55e203fa9a4204f5b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625134"
---
# <a name="scheduling-methods"></a><span data-ttu-id="876e4-102">Metodi di pianificazione</span><span class="sxs-lookup"><span data-stu-id="876e4-102">Scheduling Methods</span></span>
  <span data-ttu-id="876e4-103">Questi metodi consentono di creare e gestire pianificazioni condivise per l'esecuzione e il recapito di report e piani di aggiornamento della cache utilizzati dal server di report.</span><span class="sxs-lookup"><span data-stu-id="876e4-103">You can use these methods to create and manage shared schedules for report execution and delivery, and to cache refresh plans utilized by the report server.</span></span>  
  
|<span data-ttu-id="876e4-104">Metodo</span><span class="sxs-lookup"><span data-stu-id="876e4-104">Method</span></span>|<span data-ttu-id="876e4-105">Azione</span><span class="sxs-lookup"><span data-stu-id="876e4-105">Action</span></span>|  
|------------|------------|  
|<xref:ReportService2010.ReportingService2010.CreateCacheRefreshPlan%2A>|<span data-ttu-id="876e4-106">Crea un piano di aggiornamento della cache per un elemento.</span><span class="sxs-lookup"><span data-stu-id="876e4-106">Creates a cache refresh plan for an item.</span></span>|  
|<xref:ReportService2010.ReportingService2010.CreateSchedule%2A>|<span data-ttu-id="876e4-107">Crea una nuova pianificazione condivisa.</span><span class="sxs-lookup"><span data-stu-id="876e4-107">Creates a new shared schedule.</span></span>|  
|<xref:ReportService2010.ReportingService2010.DeleteCacheRefreshPlan%2A>|<span data-ttu-id="876e4-108">Elimina un piano di aggiornamento della cache.</span><span class="sxs-lookup"><span data-stu-id="876e4-108">Deletes a cache refresh plan.</span></span>|  
|<xref:ReportService2010.ReportingService2010.DeleteSchedule%2A>|<span data-ttu-id="876e4-109">Elimina una pianificazione condivisa in base a un ID di pianificazione specifico.</span><span class="sxs-lookup"><span data-stu-id="876e4-109">Deletes a shared schedule based on a specific schedule ID.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetCacheRefreshPlanProperties%2A>|<span data-ttu-id="876e4-110">Restituisce le proprietà del piano di aggiornamento della cache specificato.</span><span class="sxs-lookup"><span data-stu-id="876e4-110">Returns the properties of the specified cache refresh plan.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetScheduleProperties%2A>|<span data-ttu-id="876e4-111">Restituisce i valori delle proprietà di una pianificazione condivisa.</span><span class="sxs-lookup"><span data-stu-id="876e4-111">Returns the values of properties of a shared schedule.</span></span>|  
|<xref:ReportService2010.ReportingService2010.ListCacheRefreshPlans%2A>|<span data-ttu-id="876e4-112">Restituisce un elenco di piani di aggiornamento della cache associati a un elemento del catalogo.</span><span class="sxs-lookup"><span data-stu-id="876e4-112">Returns a list of the cache refresh plans associated with a catalog item.</span></span>|  
|<xref:ReportService2010.ReportingService2010.ListScheduledItems%2A>|<span data-ttu-id="876e4-113">Restituisce un elenco di elementi associati a una pianificazione condivisa.</span><span class="sxs-lookup"><span data-stu-id="876e4-113">Returns a list of items that are associated with a shared schedule.</span></span>|  
|<xref:ReportService2010.ReportingService2010.ListSchedules%2A>|<span data-ttu-id="876e4-114">Restituisce un elenco di tutte le pianificazioni condivise nel server di report o nel sito di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="876e4-114">Returns a list of all shared schedules at the report server or the SharePoint site.</span></span>|  
|<xref:ReportService2010.ReportingService2010.ListScheduleStates%2A>|<span data-ttu-id="876e4-115">Restituisce un elenco di stati della pianificazione supportati.</span><span class="sxs-lookup"><span data-stu-id="876e4-115">Returns a list of supported schedule states.</span></span>|  
|<xref:ReportService2010.ReportingService2010.PauseSchedule%2A>|<span data-ttu-id="876e4-116">Sospende l'esecuzione di una pianificazione specifica.</span><span class="sxs-lookup"><span data-stu-id="876e4-116">Pauses the execution of a given schedule.</span></span>|  
|<xref:ReportService2010.ReportingService2010.ResumeSchedule%2A>|<span data-ttu-id="876e4-117">Riprende una pianificazione condivisa sospesa.</span><span class="sxs-lookup"><span data-stu-id="876e4-117">Resumes a shared schedule that has been paused.</span></span>|  
|<xref:ReportService2010.ReportingService2010.SetCacheRefreshPlanProperties%2A>|<span data-ttu-id="876e4-118">Imposta le proprietà di un piano di aggiornamento della cache.</span><span class="sxs-lookup"><span data-stu-id="876e4-118">Sets the properties of a cache refresh plan.</span></span>|  
|<xref:ReportService2010.ReportingService2010.SetScheduleProperties%2A>|<span data-ttu-id="876e4-119">Imposta il valore delle proprietà di una pianificazione condivisa.</span><span class="sxs-lookup"><span data-stu-id="876e4-119">Sets the value of properties of a shared schedule.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="876e4-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="876e4-120">See Also</span></span>  
 <span data-ttu-id="876e4-121">[Compilazione di applicazioni tramite servizio Web e .NET Framework](../net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="876e4-121">[Building Applications Using the Web Service and the .NET Framework](../net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 <span data-ttu-id="876e4-122">[Servizio Web ReportServer](../report-server-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="876e4-122">[Report Server Web Service](../report-server-web-service.md) </span></span>  
 <span data-ttu-id="876e4-123">[Metodi del servizio Web ReportServer](report-server-web-service-methods.md) </span><span class="sxs-lookup"><span data-stu-id="876e4-123">[Report Server Web Service Methods](report-server-web-service-methods.md) </span></span>  
 [<span data-ttu-id="876e4-124">Riferimento tecnico &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="876e4-124">Technical Reference &#40;SSRS&#41;</span></span>](../../technical-reference-ssrs.md)  
  
  
