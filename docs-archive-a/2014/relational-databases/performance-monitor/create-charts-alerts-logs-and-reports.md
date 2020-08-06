---
title: Creare grafici, avvisi, log e report | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- System Monitor [SQL Server], charts and reports
- charts [SQL Server]
- reports [SQL Server]
- reports [SQL Server], creating
- Windows System Monitor [SQL Server], charts and reports
- logs [SQL Server], System Monitor
- System Monitor [SQL Server], logs
- Windows System Monitor [SQL Server], logs
ms.assetid: c9162b37-e5dc-43d1-a3aa-1e9ebc69fecc
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 3a0c95c3f483a8af3e3e68d9c5c7d3caf44350d0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723731"
---
# <a name="create-charts-alerts-logs-and-reports"></a><span data-ttu-id="2f70b-102">Creare grafici, avvisi, log e report</span><span class="sxs-lookup"><span data-stu-id="2f70b-102">Create Charts, Alerts, Logs, and Reports</span></span>
  <span data-ttu-id="2f70b-103">Monitoraggio di sistema consente di creare grafici, avvisi, log e report per monitorare un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2f70b-103">System Monitor lets you create charts, alerts, logs, and reports to monitor an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="charts"></a><span data-ttu-id="2f70b-104">Grafici</span><span class="sxs-lookup"><span data-stu-id="2f70b-104">Charts</span></span>  
 <span data-ttu-id="2f70b-105">I grafici consentono di monitorare le prestazioni correnti di oggetti e contatori selezionati, ad esempio l'utilizzo della CPU o l'I/O su disco.</span><span class="sxs-lookup"><span data-stu-id="2f70b-105">Charts can monitor the current performance of selected objects and counters; for example, the CPU usage or disk I/O.</span></span> <span data-ttu-id="2f70b-106">È possibile inserire in un grafico diverse combinazioni di oggetti e contatori di Monitoraggio di sistema,</span><span class="sxs-lookup"><span data-stu-id="2f70b-106">You can add to a chart various combinations of System Monitor objects and counters.</span></span> <span data-ttu-id="2f70b-107">nonché di oggetti e contatori di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="2f70b-107">You also can add [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows objects and counters to a chart.</span></span>  
  
 <span data-ttu-id="2f70b-108">Ogni grafico rappresenta un subset di informazioni da monitorare.</span><span class="sxs-lookup"><span data-stu-id="2f70b-108">Each chart represents a subset of information you want to monitor.</span></span> <span data-ttu-id="2f70b-109">Ad esempio, è possibile utilizzare un grafico per registrare le statistiche di utilizzo della memoria e un secondo grafico per le statistiche dell'I/O su disco.</span><span class="sxs-lookup"><span data-stu-id="2f70b-109">For example, one chart can track memory usage statistics and a second chart can track disk I/O statistics.</span></span>  
  
 <span data-ttu-id="2f70b-110">È possibile utilizzare i grafici per:</span><span class="sxs-lookup"><span data-stu-id="2f70b-110">Using a chart can be useful for the following tasks:</span></span>  
  
-   <span data-ttu-id="2f70b-111">Individuare la ragione delle scarse prestazioni di un computer o un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2f70b-111">Investigating why a computer or application is slow or inefficient.</span></span>  
  
-   <span data-ttu-id="2f70b-112">Eseguire un monitoraggio continuo dei sistemi per individuare problemi di prestazioni intermittenti.</span><span class="sxs-lookup"><span data-stu-id="2f70b-112">Continually monitoring systems to find intermittent performance problems.</span></span>  
  
-   <span data-ttu-id="2f70b-113">Individuare la ragione per la quale è necessario un potenziamento del sistema.</span><span class="sxs-lookup"><span data-stu-id="2f70b-113">Discovering why you need to increase capacity.</span></span>  
  
-   <span data-ttu-id="2f70b-114">Visualizzare una tendenza sotto forma di grafico a linee.</span><span class="sxs-lookup"><span data-stu-id="2f70b-114">Displaying a trend as a line chart.</span></span>  
  
-   <span data-ttu-id="2f70b-115">Visualizzare un confronto sotto forma di istogramma.</span><span class="sxs-lookup"><span data-stu-id="2f70b-115">Displaying a comparison as a histogram chart.</span></span>  
  
 <span data-ttu-id="2f70b-116">I grafici risultano particolarmente utili per i monitoraggi a breve termine e in tempo reale di computer locali o remoti, ad esempio per monitorare un evento in corso.</span><span class="sxs-lookup"><span data-stu-id="2f70b-116">Charts are useful for short-term, real-time monitoring of a local or remote computer (for example, when you want to monitor an event as it occurs).</span></span>  
  
## <a name="alerts"></a><span data-ttu-id="2f70b-117">Avvisi</span><span class="sxs-lookup"><span data-stu-id="2f70b-117">Alerts</span></span>  
 <span data-ttu-id="2f70b-118">Gli avvisi di Monitoraggio di sistema consentono di tenere traccia di determinati eventi e di riceverne notifica.</span><span class="sxs-lookup"><span data-stu-id="2f70b-118">Using alerts, System Monitor tracks specific events and notifies you of these events as requested.</span></span> <span data-ttu-id="2f70b-119">È possibile utilizzare un log degli avvisi per monitorare le prestazioni correnti di contatori e istanze per gli oggetti di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2f70b-119">An alert log can monitor the current performance of selected counters and instances for objects in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="2f70b-120">Se un contatore supera il valore specificato, la data e l'ora dell'evento vengono registrate nel log.</span><span class="sxs-lookup"><span data-stu-id="2f70b-120">When a counter exceeds a given value, the log records the date and time of the event.</span></span> <span data-ttu-id="2f70b-121">Un evento può inoltre generare un avviso di rete</span><span class="sxs-lookup"><span data-stu-id="2f70b-121">An event can also generate a network alert.</span></span> <span data-ttu-id="2f70b-122">ed è possibile fare in modo che venga avviato un determinato programma la prima volta o tutte le volte che si verifica un evento.</span><span class="sxs-lookup"><span data-stu-id="2f70b-122">You can have a specified program run the first time or every time an event occurs.</span></span> <span data-ttu-id="2f70b-123">Ad esempio, è possibile impostare un avviso che invia un messaggio di rete a tutti gli amministratori di sistema per comunicare che per un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] lo spazio su disco è insufficiente.</span><span class="sxs-lookup"><span data-stu-id="2f70b-123">For example, an alert can send a network message to all system administrators that the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is getting low on disk space.</span></span>  
  
## <a name="logs"></a><span data-ttu-id="2f70b-124">Log</span><span class="sxs-lookup"><span data-stu-id="2f70b-124">Logs</span></span>  
 <span data-ttu-id="2f70b-125">È possibile utilizzare i log per registrare le informazioni relative all'attività corrente di oggetti e computer in modo da poterle visualizzare ed esaminare in un momento successivo.</span><span class="sxs-lookup"><span data-stu-id="2f70b-125">Logs allow you to record information on the current activity of selected objects and computers for later viewing and analysis.</span></span> <span data-ttu-id="2f70b-126">È possibile raccogliere i dati relativi a più sistemi in un unico file di log.</span><span class="sxs-lookup"><span data-stu-id="2f70b-126">You can collect data from multiple systems into a single log file.</span></span> <span data-ttu-id="2f70b-127">Ad esempio, è possibile creare diversi log per raccogliere informazioni sulle prestazioni di determinati oggetti in diversi computer in modo da poterle analizzare in seguito.</span><span class="sxs-lookup"><span data-stu-id="2f70b-127">For example, you can create different logs to accumulate information about the performance of selected objects on various computers for future analysis.</span></span> <span data-ttu-id="2f70b-128">La selezione di oggetti potrà essere salvata in un file in modo da poterla riutilizzare per creare un altro log contenente informazioni analoghe a scopo di confronto.</span><span class="sxs-lookup"><span data-stu-id="2f70b-128">You can save these selections under a file name and reuse them when you want to create another log of similar information for comparison.</span></span>  
  
 <span data-ttu-id="2f70b-129">I file di log forniscono informazioni utili per la risoluzione dei problemi e la pianificazione.</span><span class="sxs-lookup"><span data-stu-id="2f70b-129">Log files provide a wealth of information for troubleshooting or planning.</span></span> <span data-ttu-id="2f70b-130">A differenza dei grafici, degli avvisi e dei report, che forniscono informazioni immediate sull'attività corrente, i file di log consentono di registrare i valori dei contatori su lunghi periodi di tempo</span><span class="sxs-lookup"><span data-stu-id="2f70b-130">Whereas charts, alerts, and reports on current activity provide instant feedback, log files enable you to track counters over a long period of time.</span></span> <span data-ttu-id="2f70b-131">fornendo un'analisi e una documentazione più dettagliata delle prestazioni del sistema.</span><span class="sxs-lookup"><span data-stu-id="2f70b-131">Thus, you can examine information more thoroughly and document system performance.</span></span>  
  
## <a name="reports"></a><span data-ttu-id="2f70b-132">Report</span><span class="sxs-lookup"><span data-stu-id="2f70b-132">Reports</span></span>  
 <span data-ttu-id="2f70b-133">È possibile utilizzare i report per visualizzare i diversi valori dei contatori e delle istanze di determinati oggetti nella loro continua evoluzione.</span><span class="sxs-lookup"><span data-stu-id="2f70b-133">Reports allow you to display constantly changing counter and instance values for selected objects.</span></span> <span data-ttu-id="2f70b-134">I valori di ogni istanza vengono visualizzati in colonne.</span><span class="sxs-lookup"><span data-stu-id="2f70b-134">Values appear in columns for each instance.</span></span> <span data-ttu-id="2f70b-135">È possibile modificare gli intervalli dei report, stampare snapshot ed esportare dati.</span><span class="sxs-lookup"><span data-stu-id="2f70b-135">You can adjust report intervals, print snapshots, and export data.</span></span> <span data-ttu-id="2f70b-136">Utilizzare i report per visualizzare i valori non elaborati.</span><span class="sxs-lookup"><span data-stu-id="2f70b-136">Use reports when you need to display the raw numbers.</span></span>  
  
 <span data-ttu-id="2f70b-137">Per ulteriori informazioni sulla creazione di grafici, avvisi, log e report o sugli oggetti e i contatori di Windows, vedere la documentazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="2f70b-137">For more information about creating charts, alerts, logs, and reports, or about Windows objects and counters, see the Windows documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f70b-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2f70b-138">See Also</span></span>  
 [<span data-ttu-id="2f70b-139">Monitorare l'utilizzo delle risorse &#40;Monitor di sistema&#41;</span><span class="sxs-lookup"><span data-stu-id="2f70b-139">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](monitor-resource-usage-system-monitor.md)  
  
  
