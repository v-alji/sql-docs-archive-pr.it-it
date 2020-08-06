---
title: Configurazione della riproduzione SQL Server Profiler (opzioni avanzate di riproduzione) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.pro.replay.generaloptions.advanced.f1
helpviewer_keywords:
- Replay Configuration dialog box
ms.assetid: b4eb34f7-3af6-4a44-ba7e-2b8430ec3cd7
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 95070d8defb5b7778859ce470aaa8cfc85955ba6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721691"
---
# <a name="sql-server-profiler---replay-configuration-advanced-replay-options"></a><span data-ttu-id="36a37-102">SQL Server Profiler - Configurazione riproduzione (Opzioni avanzate di riproduzione)</span><span class="sxs-lookup"><span data-stu-id="36a37-102">SQL Server Profiler - Replay Configuration (Advanced Replay Options)</span></span>
  <span data-ttu-id="36a37-103">La scheda **Opzioni avanzate di riproduzione** della finestra di dialogo **Configurazione riproduzione** consente di specificare la modalità di riproduzione di un file di traccia.</span><span class="sxs-lookup"><span data-stu-id="36a37-103">In the **Replay Configuration** dialog box, use the **Advanced Replay Options** tab to specify how to replay a trace file.</span></span>  
  
 <span data-ttu-id="36a37-104">Per visualizzare questa finestra utilizzare [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] per aprire un file o una tabella di traccia che contiene gli eventi appropriati per la riproduzione.</span><span class="sxs-lookup"><span data-stu-id="36a37-104">To view this window, use [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] to open a trace file or table that contains the appropriate events for replay.</span></span> <span data-ttu-id="36a37-105">Per altre informazioni, vedere [Requisiti per la riproduzione](../tools/sql-server-profiler/replay-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="36a37-105">For more information, see [Replay Requirements](../tools/sql-server-profiler/replay-requirements.md).</span></span> <span data-ttu-id="36a37-106">Con la tabella o il file di traccia aperto, scegliere **Avvia** dal menu **Riproduci**, connettersi all'istanza di SQL Server in cui si vuole riprodurre la traccia e quindi fare clic sulla scheda **Opzioni avanzate di riproduzione** .</span><span class="sxs-lookup"><span data-stu-id="36a37-106">While the trace file or table is open, on the **Replay** menu, click **Start**, connect to the instance of SQL Server where you want to replay the trace, and then click the **Advanced Replay Options** tab.</span></span>  
  
## <a name="options"></a><span data-ttu-id="36a37-107">Opzioni</span><span class="sxs-lookup"><span data-stu-id="36a37-107">Options</span></span>  
 <span data-ttu-id="36a37-108">**Riproduci SPID di sistema**</span><span class="sxs-lookup"><span data-stu-id="36a37-108">**Replay system SPIDs**</span></span>  
 <span data-ttu-id="36a37-109">Consente di specificare se [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] esegue la riproduzione degli SPID (System Process Identifier).</span><span class="sxs-lookup"><span data-stu-id="36a37-109">Specifies whether [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] replays system process identifiers (SPIDs).</span></span>  
  
 <span data-ttu-id="36a37-110">**Riproduci un solo SPID**</span><span class="sxs-lookup"><span data-stu-id="36a37-110">**Replay one SPID only**</span></span>  
 <span data-ttu-id="36a37-111">Consente di riprodurre solo l'attività del file di traccia di origine correlata allo SPID selezionato.</span><span class="sxs-lookup"><span data-stu-id="36a37-111">Replays only the activity in the source trace file that is related to the selected SPID.</span></span>  
  
 <span data-ttu-id="36a37-112">**SPID da riprodurre**</span><span class="sxs-lookup"><span data-stu-id="36a37-112">**SPID to replay**</span></span>  
 <span data-ttu-id="36a37-113">Consente di specificare lo SPID da riprodurre.</span><span class="sxs-lookup"><span data-stu-id="36a37-113">Specify which SPID to replay.</span></span>  
  
 <span data-ttu-id="36a37-114">**Limite di tempo per la riproduzione**</span><span class="sxs-lookup"><span data-stu-id="36a37-114">**Limit replay by date and time**</span></span>  
 <span data-ttu-id="36a37-115">Consente di riprodurre solo una parte del file di traccia di origine.</span><span class="sxs-lookup"><span data-stu-id="36a37-115">Check to replay only a portion of the source trace file.</span></span>  
  
 <span data-ttu-id="36a37-116">**Ora di inizio**</span><span class="sxs-lookup"><span data-stu-id="36a37-116">**Start time**</span></span>  
 <span data-ttu-id="36a37-117">Data e ora nel file di traccia di origine in corrispondenza delle quali deve iniziare la riproduzione.</span><span class="sxs-lookup"><span data-stu-id="36a37-117">Date and time in the source trace file where the replay should start.</span></span>  
  
 <span data-ttu-id="36a37-118">**Ora di fine**</span><span class="sxs-lookup"><span data-stu-id="36a37-118">**End time**</span></span>  
 <span data-ttu-id="36a37-119">Data e ora nel file di traccia di origine in corrispondenza delle quali deve essere arrestata la riproduzione.</span><span class="sxs-lookup"><span data-stu-id="36a37-119">Date and time in the source trace file where the replay should stop.</span></span>  
  
 <span data-ttu-id="36a37-120">**Intervallo di attesa Health Monitor (sec)**</span><span class="sxs-lookup"><span data-stu-id="36a37-120">**Health monitor wait interval (sec)**</span></span>  
 <span data-ttu-id="36a37-121">Consente di specificare l'intervallo di attesa in secondi per la riproduzione.</span><span class="sxs-lookup"><span data-stu-id="36a37-121">Specify the wait interval to replay in seconds.</span></span> <span data-ttu-id="36a37-122">Il valore predefinito è 3600 secondi (1 ora).</span><span class="sxs-lookup"><span data-stu-id="36a37-122">Default is 3600 seconds (1 hour).</span></span> <span data-ttu-id="36a37-123">Questa impostazione influisce sulla quantità di tempo durante la quale è consentita l'esecuzione di un processo prima che venga terminato da Health Monitor.</span><span class="sxs-lookup"><span data-stu-id="36a37-123">This setting affects the amount of time a process is allowed to run before being terminated by the health monitor.</span></span>  
  
 <span data-ttu-id="36a37-124">**Intervallo di polling Health Monitor (sec)**</span><span class="sxs-lookup"><span data-stu-id="36a37-124">**Health monitor poll interval (sec)**</span></span>  
 <span data-ttu-id="36a37-125">Consente di specificare l'intervallo di polling in secondi di Health Monitor durante la riproduzione.</span><span class="sxs-lookup"><span data-stu-id="36a37-125">Specify the health monitor poll interval during replay in seconds.</span></span> <span data-ttu-id="36a37-126">Il valore predefinito è 60 secondi.</span><span class="sxs-lookup"><span data-stu-id="36a37-126">Default is 60 seconds.</span></span> <span data-ttu-id="36a37-127">Questo valore consente di configurare la frequenza con cui Health Monitor esegue il polling di candidati per la terminazione.</span><span class="sxs-lookup"><span data-stu-id="36a37-127">This value allows the user to configure how often the health monitor polls for candidates for termination.</span></span>  
  
 <span data-ttu-id="36a37-128">**Abilita monitoraggio processi bloccati di SQL Server**</span><span class="sxs-lookup"><span data-stu-id="36a37-128">**Enable SQL Server blocked processes monitor**</span></span>  
 <span data-ttu-id="36a37-129">Consente di abilitare un processo che esegue la ricerca di processi bloccati e di blocco.</span><span class="sxs-lookup"><span data-stu-id="36a37-129">Enables a process that searches for blocked or blocking processes.</span></span>  
  
 <span data-ttu-id="36a37-130">**Intervallo di attesa monitoraggio processi bloccati (sec)**</span><span class="sxs-lookup"><span data-stu-id="36a37-130">**Blocked processes monitor wait interval (sec)**</span></span>  
 <span data-ttu-id="36a37-131">Consente di configurare la frequenza con cui i processi bloccati o di blocco vengono cercati tramite il monitoraggio dei processi bloccati.</span><span class="sxs-lookup"><span data-stu-id="36a37-131">Configures how often the blocked processes monitor searches for blocked or blocking processes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36a37-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="36a37-132">See Also</span></span>  
 <span data-ttu-id="36a37-133">[Riprodurre una tabella di traccia &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/replay-a-trace-table-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="36a37-133">[Replay a Trace Table &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/replay-a-trace-table-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="36a37-134">[Riprodurre un file di traccia &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/replay-a-trace-file-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="36a37-134">[Replay a Trace File &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/replay-a-trace-file-sql-server-profiler.md) </span></span>  
 [<span data-ttu-id="36a37-135">Riprodurre le tracce</span><span class="sxs-lookup"><span data-stu-id="36a37-135">Replay Traces</span></span>](../tools/sql-server-profiler/replay-traces.md)  
  
  
