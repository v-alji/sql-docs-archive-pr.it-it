---
title: Causa e risoluzione degli errori di Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- messages [Reporting Services]
- errors [Reporting Services]
- troubleshooting [Reporting Services], errors
ms.assetid: 3db0fef3-37f8-40d0-acc7-1928760dc0e9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: fa98b9f760485b80f4fa4ac74f3b8008dc3bbec3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715988"
---
# <a name="cause-and-resolution-of-reporting-services-errors"></a><span data-ttu-id="41698-102">Causa e risoluzione degli errori di Reporting Services</span><span class="sxs-lookup"><span data-stu-id="41698-102">Cause and Resolution of Reporting Services Errors</span></span>
  <span data-ttu-id="41698-103">In questo argomento vengono fornite informazioni sulla causa e sulla risoluzione di diversi errori correlati a [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="41698-103">This topic contains cause and resolution information for a number of errors related to [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="41698-104">Gli argomenti relativi ai messaggi di errore di questa sezione contengono una spiegazione del messaggio di errore, le possibili cause e le eventuali azioni da eseguire per risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="41698-104">The error message topics in this section provide an explanation of the error message, possible causes, and any actions you can take to correct the problem.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="41698-105">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="41698-105">In This Section</span></span>  
  
|<span data-ttu-id="41698-106">Errore</span><span class="sxs-lookup"><span data-stu-id="41698-106">Error</span></span>|<span data-ttu-id="41698-107">Message</span><span class="sxs-lookup"><span data-stu-id="41698-107">Message</span></span>|  
|-----------|-------------|  
|[<span data-ttu-id="41698-108">rsAccessedDenied - Errore di Reporting Services</span><span class="sxs-lookup"><span data-stu-id="41698-108">rsAccessedDenied - Reporting Services Error</span></span>](rsaccesseddenied-reporting-services-error.md)|<span data-ttu-id="41698-109">Le autorizzazioni concesse all'utente 'mydomain\myAccount' non sono sufficienti per eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="41698-109">The permissions granted to user 'mydomain\myAccount' are insufficient for performing this operation.</span></span> <span data-ttu-id="41698-110">(rsAccessDenied) (ReportingServicesLibrary).</span><span class="sxs-lookup"><span data-stu-id="41698-110">(rsAccessDenied) (ReportingServicesLibrary).</span></span>|  
|[<span data-ttu-id="41698-111">rsInternalError - Errore di Reporting Services</span><span class="sxs-lookup"><span data-stu-id="41698-111">rsInternalError - Reporting Services Error</span></span>](rsinternalerror-reporting-services-error.md)|<span data-ttu-id="41698-112">Errore interno nel server di report.</span><span class="sxs-lookup"><span data-stu-id="41698-112">An internal error occurred on the report server.</span></span> <span data-ttu-id="41698-113">Per altre informazioni, vedere il log degli errori.</span><span class="sxs-lookup"><span data-stu-id="41698-113">See the error log for more details.</span></span>|  
|[<span data-ttu-id="41698-114">rsModelGenerationError - Errore di Reporting Services</span><span class="sxs-lookup"><span data-stu-id="41698-114">rsModelGenerationError - Reporting Services Error</span></span>](rsmodelgenerationerror-reporting-services-error.md)|<span data-ttu-id="41698-115">Errore durante la generazione del modello.</span><span class="sxs-lookup"><span data-stu-id="41698-115">An error occurred while generating model.</span></span> <span data-ttu-id="41698-116">(rsModelGenerationError) (ReportingServicesLibrary) %1.</span><span class="sxs-lookup"><span data-stu-id="41698-116">(rsModelGenerationError) (ReportingServicesLibrary) %1.</span></span>|  
|[<span data-ttu-id="41698-117">rsProcessingError - Errore di Reporting Services</span><span class="sxs-lookup"><span data-stu-id="41698-117">rsProcessingError - Reporting Services Error</span></span>](rsprocessingerror-reporting-services-error.md)|<span data-ttu-id="41698-118">Errori durante l'elaborazione del report.</span><span class="sxs-lookup"><span data-stu-id="41698-118">Errors have occurred in report processing.</span></span>|  
|[<span data-ttu-id="41698-119">rsServerConfigurationError - Errore di Reporting Services</span><span class="sxs-lookup"><span data-stu-id="41698-119">rsServerConfigurationError - Reporting Services Error</span></span>](rsserverconfigurationerror-reporting-services-error.md)|<span data-ttu-id="41698-120">Il server di report ha rilevato un errore di configurazione.</span><span class="sxs-lookup"><span data-stu-id="41698-120">The report server has encountered a configuration error.</span></span>|  
|[<span data-ttu-id="41698-121">rrRenderingError - Errore di Reporting Services</span><span class="sxs-lookup"><span data-stu-id="41698-121">rrRenderingError - Reporting Services Error</span></span>](rrrenderingerror-reporting-services-error.md)|<span data-ttu-id="41698-122">Errore durante il rendering del report.</span><span class="sxs-lookup"><span data-stu-id="41698-122">An error occurred during rendering of the report.</span></span> <span data-ttu-id="41698-123">(rrRenderingError) %1.</span><span class="sxs-lookup"><span data-stu-id="41698-123">(rrRenderingError) %1.</span></span>|  
|[<span data-ttu-id="41698-124">Servizio Windows ReportServer &#40;MSSQLServer&#41; 107</span><span class="sxs-lookup"><span data-stu-id="41698-124">Report Server Windows Service &#40;MSSQLServer&#41; 107</span></span>](../../relational-databases/errors-events/mssqlserver-107-database-engine-error.md)|<span data-ttu-id="41698-125">Il servizio Windows ReportServer (MSSQLSERVER) non è in grado di connettersi al database del server di report.</span><span class="sxs-lookup"><span data-stu-id="41698-125">Report Server Windows service (MSSQLSERVER) cannot connect to the report server database.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="41698-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="41698-126">See Also</span></span>  
 <span data-ttu-id="41698-127">[File di log e origini di Reporting Services](../report-server/reporting-services-log-files-and-sources.md) </span><span class="sxs-lookup"><span data-stu-id="41698-127">[Reporting Services Log Files and Sources](../report-server/reporting-services-log-files-and-sources.md) </span></span>  
 [<span data-ttu-id="41698-128">Guida di riferimento a errori ed eventi &#40;Reporting Services&#41;</span><span class="sxs-lookup"><span data-stu-id="41698-128">Errors and Events Reference &#40;Reporting Services&#41;</span></span>](errors-and-events-reference-reporting-services.md)  
  
  
