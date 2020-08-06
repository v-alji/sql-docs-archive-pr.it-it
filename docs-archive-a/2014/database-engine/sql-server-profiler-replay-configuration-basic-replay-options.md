---
title: Configurazione della riproduzione SQL Server Profiler (opzioni di base di riproduzione) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.pro.replay.generaloptions.f1
helpviewer_keywords:
- Replay Configuration dialog box
ms.assetid: 85a1dec6-9bbc-477a-86c5-b463db9ebb31
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: cbf433c3108294909d91f7860136c0755b39b46f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721687"
---
# <a name="sql-server-profiler---replay-configuration-basic-replay-options"></a><span data-ttu-id="235b7-102">SQL Server Profiler - Configurazione riproduzione (Opzioni di base di riproduzione)</span><span class="sxs-lookup"><span data-stu-id="235b7-102">SQL Server Profiler - Replay Configuration (Basic Replay Options)</span></span>
  <span data-ttu-id="235b7-103">Nella finestra di dialogo **Configurazione riproduzione** usare la pagina **Opzioni di base di riproduzione** per specificare la modalità di riproduzione di un file o una tabella di traccia.</span><span class="sxs-lookup"><span data-stu-id="235b7-103">In the **Replay Configuration** dialog box, use the **Basic Replay Options** page to specify how to replay a trace file or table.</span></span>  
  
 <span data-ttu-id="235b7-104">Per visualizzare questa finestra utilizzare [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] per aprire un file o una tabella di traccia che contiene gli eventi appropriati per la riproduzione.</span><span class="sxs-lookup"><span data-stu-id="235b7-104">To view this window, use [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] to open a trace file or table that contains the appropriate events for replay.</span></span> <span data-ttu-id="235b7-105">Per altre informazioni, vedere [Requisiti per la riproduzione](../tools/sql-server-profiler/replay-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="235b7-105">For more information, see [Replay Requirements](../tools/sql-server-profiler/replay-requirements.md).</span></span> <span data-ttu-id="235b7-106">Con la tabella o il file di traccia aperto, scegliere **Avvia** dal menu **Riproduci**e quindi connettersi all'istanza di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] in cui riprodurre la traccia.</span><span class="sxs-lookup"><span data-stu-id="235b7-106">While the trace file or table is open, on the **Replay** menu, click **Start**, and then connect to the instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] where you want to replay the trace.</span></span>  
  
## <a name="options"></a><span data-ttu-id="235b7-107">Opzioni</span><span class="sxs-lookup"><span data-stu-id="235b7-107">Options</span></span>  
 <span data-ttu-id="235b7-108">**Server di riproduzione**</span><span class="sxs-lookup"><span data-stu-id="235b7-108">**Replay server**</span></span>  
 <span data-ttu-id="235b7-109">Consente di visualizzare l'istanza di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] a cui connettersi per la riproduzione.</span><span class="sxs-lookup"><span data-stu-id="235b7-109">Displays the instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to connect to for the replay.</span></span>  
  
 <span data-ttu-id="235b7-110">**Cambia...**</span><span class="sxs-lookup"><span data-stu-id="235b7-110">**Change...**</span></span>  
 <span data-ttu-id="235b7-111">Consente di aprire la finestra di dialogo **Connetti al server** per stabilire una connessione a un altro server.</span><span class="sxs-lookup"><span data-stu-id="235b7-111">Launches the **Connect to Server** dialog box to connect to another server.</span></span>  
  
 <span data-ttu-id="235b7-112">**Salva nel file**</span><span class="sxs-lookup"><span data-stu-id="235b7-112">**Save to file**</span></span>  
 <span data-ttu-id="235b7-113">Consente di salvare i risultati di riproduzione in un file.</span><span class="sxs-lookup"><span data-stu-id="235b7-113">Save the replay results to a file.</span></span> [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] <span data-ttu-id="235b7-114">visualizza la finestra di dialogo dei file standard in cui è possibile specificare la posizione in cui salvare il file.</span><span class="sxs-lookup"><span data-stu-id="235b7-114">displays the standard file dialog, where you can specify the location to save the file.</span></span>  
  
 <span data-ttu-id="235b7-115">**Salva nella tabella**</span><span class="sxs-lookup"><span data-stu-id="235b7-115">**Save to table**</span></span>  
 <span data-ttu-id="235b7-116">Consente di salvare i risultati di riproduzione in una tabella.</span><span class="sxs-lookup"><span data-stu-id="235b7-116">Save the replay results to a table.</span></span> [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] <span data-ttu-id="235b7-117">visualizza la finestra di dialogo di selezione della tabella in cui è possibile specificare la posizione in cui salvare la tabella.</span><span class="sxs-lookup"><span data-stu-id="235b7-117">displays the table selection dialog, where you can specify the location to save the table.</span></span>  
  
 <span data-ttu-id="235b7-118">**Numero di thread di riproduzione**</span><span class="sxs-lookup"><span data-stu-id="235b7-118">**Number of replay threads**</span></span>  
 <span data-ttu-id="235b7-119">Consente di specificare il numero di thread di riproduzione da utilizzare simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="235b7-119">Specify the number of replay threads to use concurrently.</span></span> <span data-ttu-id="235b7-120">Un numero elevato determina un maggior consumo di risorse durante la riproduzione, ma la riproduzione viene eseguita in modo più veloce e simultaneo.</span><span class="sxs-lookup"><span data-stu-id="235b7-120">A higher number consumes more resources during replay, but replay is faster and more concurrent.</span></span>  
  
 <span data-ttu-id="235b7-121">**Riproduci gli eventi nell'ordine in cui sono stati inseriti nella traccia**</span><span class="sxs-lookup"><span data-stu-id="235b7-121">**Replay events in the order they were traced**</span></span>  
 <span data-ttu-id="235b7-122">Gli eventi vengono riprodotti in modo sequenziale.</span><span class="sxs-lookup"><span data-stu-id="235b7-122">Replay events sequentially.</span></span> <span data-ttu-id="235b7-123">Utilizzare questa opzione per riprodurre una traccia a scopi di debug.</span><span class="sxs-lookup"><span data-stu-id="235b7-123">Use this option if you are replaying a trace for debugging.</span></span>  
  
 <span data-ttu-id="235b7-124">**Riproduci gli eventi usando più thread**</span><span class="sxs-lookup"><span data-stu-id="235b7-124">**Replay events using multiple threads**</span></span>  
 <span data-ttu-id="235b7-125">Gli eventi vengono riprodotti simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="235b7-125">Replay events concurrently.</span></span> <span data-ttu-id="235b7-126">Questa opzione offre una riproduzione più veloce rispetto alla riproduzione degli eventi sequenziale, ma non permette l'utilizzo a scopi di debug.</span><span class="sxs-lookup"><span data-stu-id="235b7-126">This option is faster than replaying events sequentially, but disables debugging.</span></span> <span data-ttu-id="235b7-127">Gli eventi vengono ordinati in base ai relativi identificatori di processo di sistema (SPID).</span><span class="sxs-lookup"><span data-stu-id="235b7-127">The events are ordered within their system process identifiers (SPID).</span></span>  
  
 <span data-ttu-id="235b7-128">**Visualizza risultati di riproduzione**</span><span class="sxs-lookup"><span data-stu-id="235b7-128">**Display replay results**</span></span>  
 <span data-ttu-id="235b7-129">Consente di visualizzare i risultati di riproduzione in [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="235b7-129">Display replay results in [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="235b7-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="235b7-130">See Also</span></span>  
 <span data-ttu-id="235b7-131">[Riprodurre una tabella di traccia &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/replay-a-trace-table-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="235b7-131">[Replay a Trace Table &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/replay-a-trace-table-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="235b7-132">[Riprodurre un file di traccia &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/replay-a-trace-file-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="235b7-132">[Replay a Trace File &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/replay-a-trace-file-sql-server-profiler.md) </span></span>  
 [<span data-ttu-id="235b7-133">Riprodurre le tracce</span><span class="sxs-lookup"><span data-stu-id="235b7-133">Replay Traces</span></span>](../tools/sql-server-profiler/replay-traces.md)  
  
  
