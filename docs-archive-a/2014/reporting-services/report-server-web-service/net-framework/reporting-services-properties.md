---
title: Proprietà di Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- report servers [Reporting Services], properties
- properties [Reporting Services], about properties
- reports [Reporting Services], properties
- Report Server Web service, properties
- report properties [Reporting Services]
- XML Web service [Reporting Services], properties
- Web service [Reporting Services], properties
- properties [Reporting Services]
ms.assetid: 8c855194-4c20-4ecc-a328-5137d54b560c
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 61f1f50ea7a49acc616a36a4eaf1d3d5fcdf269a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713784"
---
# <a name="reporting-services-properties"></a><span data-ttu-id="8f488-102">Proprietà di Reporting Services</span><span class="sxs-lookup"><span data-stu-id="8f488-102">Reporting Services Properties</span></span>
  <span data-ttu-id="8f488-103">Il server di report definisce un set di proprietà di sistema globali del server di report e un set di proprietà degli elementi associate a un singolo elemento archiviato nel database del server di report.</span><span class="sxs-lookup"><span data-stu-id="8f488-103">The report server defines a set of system properties that are global to the report server and a set of item properties that are associated with an individual item stored in the report server database.</span></span> <span data-ttu-id="8f488-104">Le proprietà definite dal server di report non possono essere eliminate e in alcuni casi sono di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="8f488-104">Properties defined by the report server cannot be deleted, and in some cases they are read-only.</span></span> <span data-ttu-id="8f488-105">Un'applicazione consente di estendere le proprietà di sistema e degli elementi aggiungendo a queste proprietà ulteriori proprietà definite dall'utente.</span><span class="sxs-lookup"><span data-stu-id="8f488-105">An application can extend system properties and item properties by adding additional user-defined properties to the system and item properties.</span></span>  
  
 <span data-ttu-id="8f488-106">I metodi del servizio Web seguenti recuperano e impostano le [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] Proprietà.</span><span class="sxs-lookup"><span data-stu-id="8f488-106">The following Web service methods retrieve and set [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] properties.</span></span>  
  
|<span data-ttu-id="8f488-107">Metodo</span><span class="sxs-lookup"><span data-stu-id="8f488-107">Method</span></span>|<span data-ttu-id="8f488-108">Azione</span><span class="sxs-lookup"><span data-stu-id="8f488-108">Action</span></span>|  
|------------|------------|  
|<xref:ReportService2010.ReportingService2010.GetProperties%2A>|<span data-ttu-id="8f488-109">Restituisce i valori di una o più proprietà di un elemento nel database del server di report.</span><span class="sxs-lookup"><span data-stu-id="8f488-109">Returns the values of one or more properties on an item in the report server database.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetSystemProperties%2A>|<span data-ttu-id="8f488-110">Restituisce una o più proprietà di sistema.</span><span class="sxs-lookup"><span data-stu-id="8f488-110">Returns one or more system properties.</span></span>|  
|<xref:ReportService2010.ReportingService2010.SetProperties%2A>|<span data-ttu-id="8f488-111">Imposta una o più proprietà di un elemento nel database del server di report.</span><span class="sxs-lookup"><span data-stu-id="8f488-111">Sets one or more properties of an item in the report server database.</span></span>|  
|<xref:ReportService2010.ReportingService2010.SetSystemProperties%2A>|<span data-ttu-id="8f488-112">Imposta una o più proprietà di sistema.</span><span class="sxs-lookup"><span data-stu-id="8f488-112">Sets one or more system properties.</span></span>|  
  
## <a name="in-this-section"></a><span data-ttu-id="8f488-113">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="8f488-113">In This Section</span></span>  
  
|<span data-ttu-id="8f488-114">Argomento</span><span class="sxs-lookup"><span data-stu-id="8f488-114">Topic</span></span>|<span data-ttu-id="8f488-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8f488-115">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="8f488-116">Proprietà degli elementi del server di report</span><span class="sxs-lookup"><span data-stu-id="8f488-116">Report Server Item Properties</span></span>](reporting-services-properties-report-server-item-properties.md)|<span data-ttu-id="8f488-117">Vengono descritte le proprietà specifiche degli elementi in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8f488-117">Describes the item-specific properties in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="8f488-118">Proprietà di sistema del server di report</span><span class="sxs-lookup"><span data-stu-id="8f488-118">Report Server System Properties</span></span>](reporting-services-properties-report-server-system-properties.md)|<span data-ttu-id="8f488-119">Vengono descritte le proprietà di sistema in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8f488-119">Describes the system-specific properties in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8f488-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8f488-120">See Also</span></span>  
 <span data-ttu-id="8f488-121">[Compilazione di applicazioni tramite servizio Web e .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="8f488-121">[Building Applications Using the Web Service and the .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 <span data-ttu-id="8f488-122">[Servizio Web ReportServer](../report-server-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="8f488-122">[Report Server Web Service](../report-server-web-service.md) </span></span>  
 [<span data-ttu-id="8f488-123">Riferimento tecnico &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="8f488-123">Technical Reference &#40;SSRS&#41;</span></span>](../../technical-reference-ssrs.md)  
  
  
