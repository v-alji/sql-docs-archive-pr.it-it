---
title: Opzioni di riproduzione (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- traces [SQL Server], replaying
- replaying traces
- health monitor [SQL Server]
- Replay Configuration dialog box
ms.assetid: 58761a25-a84f-4a90-9c61-97700bc5ad9c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 695a1431145813f0a7829626a380e510d0e602e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722056"
---
# <a name="replay-options-sql-server-profiler"></a><span data-ttu-id="b5e76-102">Opzioni di riproduzione (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="b5e76-102">Replay Options (SQL Server Profiler)</span></span>
  <span data-ttu-id="b5e76-103">Prima di riprodurre una traccia acquisita con [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], è necessario specificare le opzioni di riproduzione nella finestra di dialogo **Configurazione riproduzione** .</span><span class="sxs-lookup"><span data-stu-id="b5e76-103">Before replaying a captured trace with [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], specify replay options in the **Replay Configuration** dialog box.</span></span> <span data-ttu-id="b5e76-104">Per visualizzare questa finestra di dialogo, aprire il file o la tabella di traccia per la riproduzione in [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]e scegliere **Avvia** dal menu **Riproduci**.</span><span class="sxs-lookup"><span data-stu-id="b5e76-104">To launch this dialog box, open the replay trace file or table in [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], and on the **Replay** menu, click **Start**.</span></span> <span data-ttu-id="b5e76-105">Per informazioni sulle autorizzazioni necessarie per riprodurre una traccia, vedere [Autorizzazioni necessarie per l'esecuzione di SQL Server Profiler](sql-server-profiler.md).</span><span class="sxs-lookup"><span data-stu-id="b5e76-105">For information about what permissions are required to replay a trace, see [Permissions Required to Run SQL Server Profiler](sql-server-profiler.md).</span></span>  
  
 <span data-ttu-id="b5e76-106">In questo argomento vengono descritte le opzioni specificate con la finestra di dialogo **Configurazione riproduzione** .</span><span class="sxs-lookup"><span data-stu-id="b5e76-106">This topic describes the options specified with the **Replay Configuration** dialog box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b5e76-107">È consigliabile utilizzare Distributed Replay Utility per riprodurre un'applicazione OLTP intensiva (con molte connessioni simultanee attive o una velocità effettiva elevata).</span><span class="sxs-lookup"><span data-stu-id="b5e76-107">We recommend using the Distributed Replay Utility for replaying an intensive OLTP application (with many active concurrent connections or high throughput).</span></span> <span data-ttu-id="b5e76-108">Distributed Replay Utility può riprodurre dati di traccia da più computer, per simulare in modo migliore un carico di lavoro di importanza critica.</span><span class="sxs-lookup"><span data-stu-id="b5e76-108">The Distributed Replay Utility can replay trace data from multiple computers, better simulating a mission-critical workload.</span></span> <span data-ttu-id="b5e76-109">Per altre informazioni, vedere [SQL Server Distributed Replay](../distributed-replay/sql-server-distributed-replay.md).</span><span class="sxs-lookup"><span data-stu-id="b5e76-109">For more information, see [SQL Server Distributed Replay](../distributed-replay/sql-server-distributed-replay.md).</span></span>  
  
## <a name="basic-replay-options"></a><span data-ttu-id="b5e76-110">Opzioni di riproduzione di base</span><span class="sxs-lookup"><span data-stu-id="b5e76-110">Basic Replay Options</span></span>  
 <span data-ttu-id="b5e76-111">**Server di riproduzione**</span><span class="sxs-lookup"><span data-stu-id="b5e76-111">**Replay server**</span></span>  
 <span data-ttu-id="b5e76-112">Nome dell'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in cui si desidera riprodurre la traccia.</span><span class="sxs-lookup"><span data-stu-id="b5e76-112">The server is the name of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] against which you want to replay the trace.</span></span> <span data-ttu-id="b5e76-113">Il server deve soddisfare i requisiti per la riproduzione descritti in [Requisiti per la riproduzione](replay-requirements.md)."</span><span class="sxs-lookup"><span data-stu-id="b5e76-113">The server must adhere to the replay requirements described in [Replay Requirements](replay-requirements.md)."</span></span>  
  
 <span data-ttu-id="b5e76-114">**Salva nel file**</span><span class="sxs-lookup"><span data-stu-id="b5e76-114">**Save to file**</span></span>  
 <span data-ttu-id="b5e76-115">File di output nel quale vengono memorizzati i risultati della riproduzione della traccia per analisi successive.</span><span class="sxs-lookup"><span data-stu-id="b5e76-115">The output file where the result of replaying the trace is written for later viewing.</span></span> <span data-ttu-id="b5e76-116">Per impostazione predefinita, [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] visualizza sullo schermo solo i risultati della riproduzione della traccia.</span><span class="sxs-lookup"><span data-stu-id="b5e76-116">By default, [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] displays only the results of replaying the trace on the screen.</span></span>  
  
 <span data-ttu-id="b5e76-117">**Salva nella tabella**</span><span class="sxs-lookup"><span data-stu-id="b5e76-117">**Save to table**</span></span>  
 <span data-ttu-id="b5e76-118">Tabella del database nella quale vengono memorizzati i risultati della riproduzione della traccia per analisi successive.</span><span class="sxs-lookup"><span data-stu-id="b5e76-118">The database table where the result of replaying the trace is written for later viewing.</span></span>  
  
 <span data-ttu-id="b5e76-119">**Numero di thread di riproduzione**</span><span class="sxs-lookup"><span data-stu-id="b5e76-119">**Number of replay threads**</span></span>  
 <span data-ttu-id="b5e76-120">Consente di specificare il numero di thread di riproduzione da utilizzare simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="b5e76-120">Specify the number of replay threads to use concurrently.</span></span> <span data-ttu-id="b5e76-121">Un numero più alto richiede un numero di risorse maggiore durante la riproduzione, ma il processo è più rapido.</span><span class="sxs-lookup"><span data-stu-id="b5e76-121">A higher number consumes more resources during replay, but replay is faster.</span></span> <span data-ttu-id="b5e76-122">Se si utilizzano più thread, l'ordine degli eventi non viene mantenuto completamente.</span><span class="sxs-lookup"><span data-stu-id="b5e76-122">Event ordering is not fully maintained when multiple threads are used.</span></span>  
  
 <span data-ttu-id="b5e76-123">**Riproduci gli eventi nell'ordine in cui sono stati inseriti nella traccia**</span><span class="sxs-lookup"><span data-stu-id="b5e76-123">**Replay events in the order they were traced**</span></span>  
 <span data-ttu-id="b5e76-124">Consente di utilizzare metodi di debug quali l'esecuzione istruzione per istruzione di una traccia.</span><span class="sxs-lookup"><span data-stu-id="b5e76-124">Allows you to use debugging methods such as stepping through each trace.</span></span> <span data-ttu-id="b5e76-125">Se l'opzione non è selezionata, non è garantito che l'ordine nel quale vengono riprodotti gli eventi sia consistente con l'ordine in cui sono stati acquisiti in origine.</span><span class="sxs-lookup"><span data-stu-id="b5e76-125">If this option is not selected, replay does not guarantee that events are replayed in an order that is consistent with the order in which events were originally captured.</span></span>  
  
 <span data-ttu-id="b5e76-126">**Riproduci gli eventi usando più thread**</span><span class="sxs-lookup"><span data-stu-id="b5e76-126">**Replay events using multiple threads**</span></span>  
 <span data-ttu-id="b5e76-127">Ottimizza le prestazioni e disabilita il debug.</span><span class="sxs-lookup"><span data-stu-id="b5e76-127">Optimizes performance and disables debugging.</span></span> <span data-ttu-id="b5e76-128">Gli eventi vengono riprodotti nell'ordine in cui sono stati registrati per un ID di processo server (SPID), ma non viene garantito l'ordinamento degli SPID.</span><span class="sxs-lookup"><span data-stu-id="b5e76-128">Events are replayed in the order they were recorded for a particular server process ID (SPID), but ordering of SPIDs is not guaranteed.</span></span>  
  
 <span data-ttu-id="b5e76-129">**Visualizza risultati di riproduzione**</span><span class="sxs-lookup"><span data-stu-id="b5e76-129">**Display replay results**</span></span>  
 <span data-ttu-id="b5e76-130">Visualizza i risultati della riproduzione.</span><span class="sxs-lookup"><span data-stu-id="b5e76-130">Display the results of the replay.</span></span> <span data-ttu-id="b5e76-131">Questa è l'opzione predefinita.</span><span class="sxs-lookup"><span data-stu-id="b5e76-131">This is the default option.</span></span> <span data-ttu-id="b5e76-132">Se la traccia che si desidera riprodurre è molto estesa, è possibile disabilitare questa opzione per risparmiare spazio su disco.</span><span class="sxs-lookup"><span data-stu-id="b5e76-132">If the trace you are replaying is very large, you may want to disable this to save disk space.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b5e76-133">Per ottenere le migliori prestazioni di riproduzione, è consigliabile selezionare l'opzione per la riproduzione con più thread e deselezionare l'opzione per la visualizzazione dei risultati.</span><span class="sxs-lookup"><span data-stu-id="b5e76-133">For best replay performance, we recommend that you select to replay events using multiple threads, and do not select to display the replay results.</span></span>  
  
## <a name="advanced-replay-options"></a><span data-ttu-id="b5e76-134">Opzioni avanzate di riproduzione</span><span class="sxs-lookup"><span data-stu-id="b5e76-134">Advanced Replay Options</span></span>  
 <span data-ttu-id="b5e76-135">**Riproduci SPID di sistema**</span><span class="sxs-lookup"><span data-stu-id="b5e76-135">**Replay system SPIDs**</span></span>  
 <span data-ttu-id="b5e76-136">Riproduce tutti gli SPID.</span><span class="sxs-lookup"><span data-stu-id="b5e76-136">Replay all SPIDs.</span></span> <span data-ttu-id="b5e76-137">Questa è l'opzione predefinita.</span><span class="sxs-lookup"><span data-stu-id="b5e76-137">This is the default option.</span></span>  
  
 <span data-ttu-id="b5e76-138">**Riproduci un solo SPID**</span><span class="sxs-lookup"><span data-stu-id="b5e76-138">**Replay one SPID only**</span></span>  
 <span data-ttu-id="b5e76-139">Riproduce il numero di SPID selezionato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="b5e76-139">Replays the SPID number you choose from the list.</span></span>  
  
 <span data-ttu-id="b5e76-140">**Limite di tempo per la riproduzione**</span><span class="sxs-lookup"><span data-stu-id="b5e76-140">**Limit replay by date and time**</span></span>  
 <span data-ttu-id="b5e76-141">Riproduce la traccia in base ai valori **Ora di inizio** e **Ora di fine**specificati.</span><span class="sxs-lookup"><span data-stu-id="b5e76-141">Replays the trace for the specified **Start time** and **End time**.</span></span>  
  
 <span data-ttu-id="b5e76-142">**Intervallo di attesa Health Monitor**</span><span class="sxs-lookup"><span data-stu-id="b5e76-142">**Health monitor wait interval**</span></span>  
 <span data-ttu-id="b5e76-143">Imposta il periodo di tempo per il quale è consentita l'esecuzione di un processo prima che venga terminato da Health Monitor.</span><span class="sxs-lookup"><span data-stu-id="b5e76-143">Sets the amount of time a process is allowed to run before the health monitor terminates it.</span></span>  
  
 <span data-ttu-id="b5e76-144">**Intervallo di polling Health Monitor**</span><span class="sxs-lookup"><span data-stu-id="b5e76-144">**Health monitor poll interval**</span></span>  
 <span data-ttu-id="b5e76-145">Imposta la frequenza con la quale Health Monitor esegue il polling sui candidati per la chiusura.</span><span class="sxs-lookup"><span data-stu-id="b5e76-145">Sets how often the health monitor polls candidates for termination.</span></span>  
  
 <span data-ttu-id="b5e76-146">**Abilita monitoraggio processi bloccati di SQL Server**</span><span class="sxs-lookup"><span data-stu-id="b5e76-146">**Enable SQL Server blocked processes monitor**</span></span>  
 <span data-ttu-id="b5e76-147">Imposta la frequenza con la quale il monitoraggio dei processi bloccati esegue la ricerca dei processi bloccati o in fase di blocco.</span><span class="sxs-lookup"><span data-stu-id="b5e76-147">Sets how often the blocked processes monitor searches for blocked or blocking processes.</span></span>  
  
## <a name="about-the-health-monitor"></a><span data-ttu-id="b5e76-148">Informazioni su Health Monitor</span><span class="sxs-lookup"><span data-stu-id="b5e76-148">About the Health Monitor</span></span>  
 <span data-ttu-id="b5e76-149">Health Monitor è un thread dell'applicazione che esegue il monitoraggio dei processi simulati coinvolti nella riproduzione di una traccia e che termina i processi bloccati nella fase di riproduzione.</span><span class="sxs-lookup"><span data-stu-id="b5e76-149">The health monitor is an application thread that monitors the simulated processes involved in replaying a trace, and ends those processes that are blocked within the replay.</span></span> <span data-ttu-id="b5e76-150">Nella scheda **Opzioni avanzate di riproduzione** della finestra di dialogo **Configurazione riproduzione** è possibile specificare l'intervallo espresso in secondi per il quale Health Monitor dovrà attendere prima di terminare un processo bloccato (**Intervallo di attesa Health Monitor**).</span><span class="sxs-lookup"><span data-stu-id="b5e76-150">In the **Advanced Replay Options** tab of the **Replay Configuration** dialog box, you can specify how long the health monitor should wait in seconds before ending a blocked process (**Health monitor wait interval**).</span></span> <span data-ttu-id="b5e76-151">Se si imposta l'intervallo su 0, Health Monitor non terminerà mai i processi bloccati nella traccia di riproduzione.</span><span class="sxs-lookup"><span data-stu-id="b5e76-151">If you set this interval to 0, the health monitor never ends simulated blocking processes in the replaying trace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5e76-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b5e76-152">See Also</span></span>  
 <span data-ttu-id="b5e76-153">[Riprodurre le tracce](replay-traces.md) </span><span class="sxs-lookup"><span data-stu-id="b5e76-153">[Replay Traces](replay-traces.md) </span></span>  
 <span data-ttu-id="b5e76-154">[Requisiti per la riproduzione](replay-requirements.md) </span><span class="sxs-lookup"><span data-stu-id="b5e76-154">[Replay Requirements](replay-requirements.md) </span></span>  
 [<span data-ttu-id="b5e76-155">Considerazioni relative alla riproduzione di tracce &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="b5e76-155">Considerations for Replaying Traces &#40;SQL Server Profiler&#41;</span></span>](considerations-for-replaying-traces-sql-server-profiler.md)  
  
  
