---
title: Riproduzione di tracce | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Profiler, replaying traces
- Run to Cursor option
- Toggle Breakpoint option
- traces [SQL Server], replaying
- replaying traces
- playback engine [SQL Server Profiler]
- events [SQL Server], replaying traces
- Profiler [SQL Server Profiler], replaying traces
ms.assetid: da958d3c-7f3e-44c9-aecc-8a9493bea7c0
author: stevestein
ms.author: sstein
ms.openlocfilehash: c485317d1343958f9c430b73d858130097d44d75
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722048"
---
# <a name="replay-traces"></a><span data-ttu-id="d40e7-102">Riprodurre le tracce</span><span class="sxs-lookup"><span data-stu-id="d40e7-102">Replay Traces</span></span>
  <span data-ttu-id="d40e7-103">La riproduzione è la possibilità di riprodurre un'attività acquisita in una traccia.</span><span class="sxs-lookup"><span data-stu-id="d40e7-103">Replay is the ability to reproduce activity that has been captured in a trace.</span></span> <span data-ttu-id="d40e7-104">Quando si crea o si modifica una traccia, è possibile salvarla in un file per riprodurla successivamente.</span><span class="sxs-lookup"><span data-stu-id="d40e7-104">When you create or edit a trace, you can save the trace to a file and replay it later.</span></span> <span data-ttu-id="d40e7-105">È possibile usare [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] per riprodurre l'attività di traccia da un singolo computer.</span><span class="sxs-lookup"><span data-stu-id="d40e7-105">You can use [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] to replay trace activity from a single computer.</span></span> <span data-ttu-id="d40e7-106">In presenza di carichi di lavoro elevati, utilizzare Distributed Replay Utility per riprodurre dati di traccia da più computer.</span><span class="sxs-lookup"><span data-stu-id="d40e7-106">For large workloads, use the Distributed Replay Utility to replay trace data from multiple computers.</span></span>  
  
 <span data-ttu-id="d40e7-107">In questa sezione viene descritto come utilizzare le caratteristiche di riproduzione di [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d40e7-107">This section describes how to use the replay features of [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span> <span data-ttu-id="d40e7-108">Per altre informazioni su Distributed Replay Utility, vedere [SQL Server Distributed Replay](../distributed-replay/sql-server-distributed-replay.md).</span><span class="sxs-lookup"><span data-stu-id="d40e7-108">For more information about the Distributed Replay Utility, see [SQL Server Distributed Replay](../distributed-replay/sql-server-distributed-replay.md).</span></span>  
  
 [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="d40e7-109">include un motore di riproduzione a thread multipli in grado di simulare le connessioni utente e l'autenticazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d40e7-109">features a multithreaded playback engine that can simulate user connections and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="d40e7-110">La funzionalità di riproduzione risulta utile per la risoluzione dei problemi a livello di applicazione o di processo.</span><span class="sxs-lookup"><span data-stu-id="d40e7-110">Replay is useful to troubleshoot an application or process problem.</span></span> <span data-ttu-id="d40e7-111">Dopo aver identificato il problema e implementato le correzioni adeguate, eseguire nell'applicazione o nel processo la traccia con cui è stato rilevato il possibile problema.</span><span class="sxs-lookup"><span data-stu-id="d40e7-111">When you have identified the problem and implemented corrections, run the trace that found the potential problem against the corrected application or process.</span></span> <span data-ttu-id="d40e7-112">Riprodurre quindi la traccia originale e confrontare i risultati.</span><span class="sxs-lookup"><span data-stu-id="d40e7-112">Then, replay the original trace and compare results.</span></span>  
  
 <span data-ttu-id="d40e7-113">La riproduzione di tracce supporta il debug eseguito tramite le opzioni **Attiva/Disattiva punto di interruzione** ed **Esegui fino al cursore** del menu **Riproduci** di [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d40e7-113">Trace replay supports debugging by using the **Toggle Breakpoint** and the **Run to Cursor** options on the [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] **Replay** menu.</span></span> <span data-ttu-id="d40e7-114">Queste opzioni consentono in modo particolare un miglioramento dell'analisi di script lunghi. La riproduzione della traccia viene suddivisa infatti in segmenti brevi, che possono essere quindi analizzati in modo incrementale.</span><span class="sxs-lookup"><span data-stu-id="d40e7-114">These options especially improve the analysis of long scripts because they can break the replay of the trace into short segments so they can be analyzed incrementally.</span></span>  
  
 <span data-ttu-id="d40e7-115">Per informazioni sulle autorizzazioni richieste per riprodurre tracce, vedere [Autorizzazioni necessarie per l'esecuzione di SQL Server Profiler](permissions-required-to-run-sql-server-profiler.md).</span><span class="sxs-lookup"><span data-stu-id="d40e7-115">For information about the permissions required to replay traces, see [Permissions Required to Run SQL Server Profiler](permissions-required-to-run-sql-server-profiler.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d40e7-116">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="d40e7-116">In This Section</span></span>  
  
|<span data-ttu-id="d40e7-117">Argomento</span><span class="sxs-lookup"><span data-stu-id="d40e7-117">Topic</span></span>|<span data-ttu-id="d40e7-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d40e7-118">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="d40e7-119">Requisiti per la riproduzione</span><span class="sxs-lookup"><span data-stu-id="d40e7-119">Replay Requirements</span></span>](replay-requirements.md)|<span data-ttu-id="d40e7-120">Vengono descritti gli eventi che è necessario includere in una definizione di traccia perché questa possa essere riprodotta con [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d40e7-120">Describes the events that must be included in a trace definition so that it can be replayed with [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>|  
|[<span data-ttu-id="d40e7-121">Opzioni di riproduzione &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="d40e7-121">Replay Options &#40;SQL Server Profiler&#41;</span></span>](replay-options-sql-server-profiler.md)|<span data-ttu-id="d40e7-122">Vengono descritte le opzioni disponibili nella finestra di dialogo **Configurazione riproduzione** di [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d40e7-122">Describes the options you can set in the **Replay Configuration** dialog box of [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>|  
|[<span data-ttu-id="d40e7-123">Considerazioni relative alla riproduzione di tracce &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="d40e7-123">Considerations for Replaying Traces &#40;SQL Server Profiler&#41;</span></span>](considerations-for-replaying-traces-sql-server-profiler.md)|<span data-ttu-id="d40e7-124">Vengono descritti gli eventi di traccia non riproducibili con [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] e l'impatto della riproduzione di tracce sulle prestazioni del server.</span><span class="sxs-lookup"><span data-stu-id="d40e7-124">Describes trace events that can not be replayed with [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] and the effects on server performance of replaying traces.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d40e7-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d40e7-125">See Also</span></span>  
 [<span data-ttu-id="d40e7-126">SQL Server Distributed Replay</span><span class="sxs-lookup"><span data-stu-id="d40e7-126">SQL Server Distributed Replay</span></span>](../distributed-replay/sql-server-distributed-replay.md)  
  
  
