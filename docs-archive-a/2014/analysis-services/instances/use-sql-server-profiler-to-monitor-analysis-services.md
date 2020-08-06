---
title: Usare SQL Server Profiler per monitorare Analysis Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Profiler, Analysis Services
- monitoring Analysis Services [SQL Server]
- performance [Analysis Services], SQL Server Profiler
- Profiler [SQL Server Profiler], Analysis Services
ms.assetid: 8b77dafc-4584-4e93-8ad7-299304391bfd
author: minewiskan
ms.author: owend
ms.openlocfilehash: e144c1d858670f8a46b164ffc9885e6e082c4b0a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625667"
---
# <a name="use-sql-server-profiler-to-monitor-analysis-services"></a><span data-ttu-id="54d4d-102">Usare SQL Server Profiler per il monitoraggio di Analysis Services</span><span class="sxs-lookup"><span data-stu-id="54d4d-102">Use SQL Server Profiler to Monitor Analysis Services</span></span>
  [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="54d4d-103">consente di tenere traccia degli eventi di elaborazione del motore, ad esempio l'avvio di un batch o di una transazione, e di acquisire i dati relativi a tali eventi consentendo in questo modo di monitorare l'attività del server e del database, ad esempio query utente o attività di accesso.</span><span class="sxs-lookup"><span data-stu-id="54d4d-103">tracks engine process events, such as the start of a batch or a transaction, and it captures data about those events, thus enabling you to monitor server and database activity (for example, user queries or login activity).</span></span> <span data-ttu-id="54d4d-104">È possibile acquisire i dati di [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] in un file o in una tabella [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per poterli analizzare in seguito, nonché riprodurre gli eventi acquisiti nella stessa istanza di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] o in un'istanza diversa per analizzare in modo approfondito cosa sia avvenuto.</span><span class="sxs-lookup"><span data-stu-id="54d4d-104">You can capture [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] data to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table or a file for later analysis, and you can also replay the events captured on the same or another [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance to see exactly what happened.</span></span> <span data-ttu-id="54d4d-105">È possibile riprodurre gli eventi in tempo reale oppure in fasi successive.</span><span class="sxs-lookup"><span data-stu-id="54d4d-105">You can replay events in real time or on a step-by-step basis.</span></span> <span data-ttu-id="54d4d-106">Risulta inoltre particolarmente utile far eseguire gli eventi di traccia assieme ai contatori delle prestazioni nello stesso computer.</span><span class="sxs-lookup"><span data-stu-id="54d4d-106">It is also very useful to run the trace events along with the Performance counters on the same machine.</span></span> <span data-ttu-id="54d4d-107">SQL Profiler è in grado di correlare gli eventi di traccia e i contatori delle prestazioni in base all'orario e visualizzarli insieme in un'unica cronologia.</span><span class="sxs-lookup"><span data-stu-id="54d4d-107">The profiler can correlate these two based on time and display them together along a single timeline.</span></span> <span data-ttu-id="54d4d-108">Gli eventi di traccia restituiscono un maggior numero di dettagli mentre i contatori delle prestazioni offrono una vista aggregata.</span><span class="sxs-lookup"><span data-stu-id="54d4d-108">Trace events will give you more details while Performance counters give you an aggregate view.</span></span> <span data-ttu-id="54d4d-109">Per informazioni su come creare ed eseguire tracce, vedere [Creare tracce del profiler per la riproduzione &#40;Analysis Services&#41;](create-profiler-traces-for-replay-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="54d4d-109">For information about how to create and run traces, see [Create Profiler Traces for Replay &#40;Analysis Services&#41;](create-profiler-traces-for-replay-analysis-services.md).</span></span>  
  
 <span data-ttu-id="54d4d-110">Gli argomenti disponibili in questa sezione sono descritti nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="54d4d-110">The following table describes the topics in this section.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="54d4d-111">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="54d4d-111">In This Section</span></span>  
  
|<span data-ttu-id="54d4d-112">Argomento</span><span class="sxs-lookup"><span data-stu-id="54d4d-112">Topic</span></span>|<span data-ttu-id="54d4d-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="54d4d-113">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="54d4d-114">Introduzione al monitoraggio di Analysis Services tramite SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="54d4d-114">Introduction to Monitoring Analysis Services with SQL Server Profiler</span></span>](introduction-to-monitoring-analysis-services-with-sql-server-profiler.md)|<span data-ttu-id="54d4d-115">Descrive l'utilizzo di [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] per il monitoraggio di un'istanza di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="54d4d-115">Describes how to use [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] to monitor an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance.</span></span>|  
|[<span data-ttu-id="54d4d-116">Creare tracce del profiler per la riproduzione &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="54d4d-116">Create Profiler Traces for Replay &#40;Analysis Services&#41;</span></span>](create-profiler-traces-for-replay-analysis-services.md)|<span data-ttu-id="54d4d-117">Descrive i requisiti per la creazione di una traccia per la riproduzione tramite [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="54d4d-117">Describes the requirements for creating a trace for replay by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>|  
|[<span data-ttu-id="54d4d-118">Eventi di traccia di Analysis Services</span><span class="sxs-lookup"><span data-stu-id="54d4d-118">Analysis Services Trace Events</span></span>](https://docs.microsoft.com/bi-reference/trace-events/analysis-services-trace-events)|<span data-ttu-id="54d4d-119">Descrive le classi di evento di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="54d4d-119">Describes [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] event classes.</span></span> <span data-ttu-id="54d4d-120">Queste classi di evento eseguono il mapping ad azioni generate da [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] e vengono utilizzate per le riproduzioni delle tracce.</span><span class="sxs-lookup"><span data-stu-id="54d4d-120">These event classes map to actions generated by [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] and are used for trace replays.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="54d4d-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="54d4d-121">See Also</span></span>  
 [<span data-ttu-id="54d4d-122">Monitorare un'istanza di Analysis Services</span><span class="sxs-lookup"><span data-stu-id="54d4d-122">Monitor an Analysis Services Instance</span></span>](monitor-an-analysis-services-instance.md)  
  
  
