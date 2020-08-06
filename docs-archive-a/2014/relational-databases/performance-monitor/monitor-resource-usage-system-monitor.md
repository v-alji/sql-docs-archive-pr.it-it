---
title: Monitorare l'utilizzo delle risorse (Monitor di sistema) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- monitoring performance [SQL Server], resource usage
- System Monitor [SQL Server], about Windows System Monitor
- resource usage monitoring [SQL Server]
- System Monitor [SQL Server]
- counters [SQL Server], resource usage subjects
- performance counters [SQL Server], resource usage subjects
- Windows System Monitor [SQL Server], about Windows System Monitor
- monitoring [SQL Server], server resource usage
- monitoring resource usage [SQL Server]
- Windows System Monitor [SQL Server]
- database monitoring [SQL Server], resource usage
- database performance [SQL Server], resource usage
- tuning databases [SQL Server], resource usage
- server performance [SQL Server], resource usage
ms.assetid: f2993a28-0b81-46f2-aec0-6877fe990387
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d691091a41e3161c733902824bf439b6788cc4f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637254"
---
# <a name="monitor-resource-usage-system-monitor"></a><span data-ttu-id="08925-102">Monitoraggio dell'utilizzo delle risorse (Monitor di sistema)</span><span class="sxs-lookup"><span data-stu-id="08925-102">Monitor Resource Usage (System Monitor)</span></span>
  <span data-ttu-id="08925-103">Se si utilizza un sistema operativo server Microsoft Windows, è possibile misurare le prestazioni di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]mediante lo strumento grafico Monitoraggio di sistema.</span><span class="sxs-lookup"><span data-stu-id="08925-103">If you are running Microsoft Windows server operating system, use the System Monitor graphical tool to measure the performance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="08925-104">È possibile visualizzare oggetti e contatori delle prestazioni di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , nonché funzioni di altri oggetti ad esempio processori, memoria, cache, thread e processi.</span><span class="sxs-lookup"><span data-stu-id="08925-104">You can view [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] objects, performance counters, and the behavior of other objects, such as processors, memory, cache, threads, and processes.</span></span> <span data-ttu-id="08925-105">A ognuno di questi oggetti è associato un set di contatori che misurano l'utilizzo dei dispositivi, le lunghezze delle code, i ritardi e altri indicatori di velocità effettiva e congestione interna.</span><span class="sxs-lookup"><span data-stu-id="08925-105">Each of these objects has an associated set of counters that measure device usage, queue lengths, delays, and other indicators of throughput and internal congestion.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="08925-106">Monitoraggio di sistema sostituisce Performance Monitor nelle versioni successive a Windows NT 4.0.</span><span class="sxs-lookup"><span data-stu-id="08925-106">System Monitor replaced Performance Monitor after Windows NT 4.0.</span></span>  
  
## <a name="benefits-of-system-monitor"></a><span data-ttu-id="08925-107">Vantaggi di Monitoraggio di sistema</span><span class="sxs-lookup"><span data-stu-id="08925-107">Benefits of System Monitor</span></span>  
 <span data-ttu-id="08925-108">Monitoraggio di sistema consente di monitorare contemporaneamente i contatori del sistema operativo Windows e di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] allo scopo di determinare correlazioni tra le prestazioni di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e Windows.</span><span class="sxs-lookup"><span data-stu-id="08925-108">System Monitor can be useful to monitor Windows operating system and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] counters at the same time to determine any correlation between the performance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and Windows.</span></span> <span data-ttu-id="08925-109">Ad esempio, il monitoraggio parallelo dei contatori di I/O del disco di Windows e dei contatori Gestione buffer di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] consente di ottenere una panoramica del funzionamento globale del sistema.</span><span class="sxs-lookup"><span data-stu-id="08925-109">For example, monitoring the Windows disk input/output (I/O) counters and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Buffer Manager counters at the same time can reveal the behavior of the entire system.</span></span>  
  
 <span data-ttu-id="08925-110">Monitoraggio di sistema consente di ottenere statistiche sulle attività e le prestazioni correnti di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="08925-110">System Monitor allows you to obtain statistics on current [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] activity and performance.</span></span> <span data-ttu-id="08925-111">Tramite Monitoraggio di sistema è possibile:</span><span class="sxs-lookup"><span data-stu-id="08925-111">Using System Monitor, you can:</span></span>  
  
-   <span data-ttu-id="08925-112">Visualizzare i dati simultaneamente da più computer.</span><span class="sxs-lookup"><span data-stu-id="08925-112">View data simultaneously from any number of computers.</span></span>  
  
-   <span data-ttu-id="08925-113">Visualizzare e modificare i grafici in modo da riflettere l'attività corrente e mostrare i valori dei contatori aggiornati in base alla frequenza specificata dall'utente.</span><span class="sxs-lookup"><span data-stu-id="08925-113">View and change charts to reflect current activity, and show counter values that are updated at a frequency that the user defines.</span></span>  
  
-   <span data-ttu-id="08925-114">Esportare i dati di grafici, log, log degli avvisi e report in applicazioni di foglio di calcolo o di database per modificarli e stamparli.</span><span class="sxs-lookup"><span data-stu-id="08925-114">Export data from charts, logs, alert logs, and reports to spreadsheet or database applications for further manipulation and printing.</span></span>  
  
-   <span data-ttu-id="08925-115">Aggiungere avvisi di sistema che visualizzano un evento del log degli avvisi e avvertono l'amministratore inviando un avviso di rete.</span><span class="sxs-lookup"><span data-stu-id="08925-115">Add system alerts that list an event in the alert log and can notify you by issuing a network alert.</span></span>  
  
-   <span data-ttu-id="08925-116">Eseguire un'applicazione specifica la prima volta o ogni volta che il valore di un contatore è superiore o inferiore a un valore definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="08925-116">Run a predefined application the first time or every time a counter value goes over or under a user-defined value.</span></span>  
  
-   <span data-ttu-id="08925-117">Creare file di log contenenti dati relativi a vari oggetti di diversi computer.</span><span class="sxs-lookup"><span data-stu-id="08925-117">Create log files that contain data about various objects from different computers.</span></span>  
  
-   <span data-ttu-id="08925-118">Aggiungere a un file le sezioni selezionate in altri file di log per creare un archivio a lungo termine.</span><span class="sxs-lookup"><span data-stu-id="08925-118">Append to one file selected sections from other existing log files to form a long-term archive.</span></span>  
  
-   <span data-ttu-id="08925-119">Visualizzare i report relativi all'attività corrente o creare report dai file di log esistenti.</span><span class="sxs-lookup"><span data-stu-id="08925-119">View current-activity reports, or create reports from existing log files.</span></span>  
  
-   <span data-ttu-id="08925-120">Salvare le impostazioni di un grafico, avviso, log o report o dell'intera area di lavoro per poterle riutilizzare in seguito.</span><span class="sxs-lookup"><span data-stu-id="08925-120">Save individual chart, alert, log, or report settings, or the entire workspace setup for reuse.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="08925-121">Monitoraggio di sistema ha sostituito Performance Monitor dopo Windows NT 4.0.</span><span class="sxs-lookup"><span data-stu-id="08925-121">System Monitor replaced the Performance Monitor after Windows NT 4.0.</span></span> <span data-ttu-id="08925-122">Per tali attività è possibile utilizzare sia Monitoraggio di sistema che Performance Monitor.</span><span class="sxs-lookup"><span data-stu-id="08925-122">You can use either the System Monitor or Performance Monitor to do these tasks.</span></span>  
  
## <a name="system-monitor-performance"></a><span data-ttu-id="08925-123">Prestazioni di Monitoraggio di sistema</span><span class="sxs-lookup"><span data-stu-id="08925-123">System Monitor Performance</span></span>  
 <span data-ttu-id="08925-124">Il monitoraggio di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e del sistema operativo Microsoft Windows per la verifica delle prestazioni viene eseguito per esaminare innanzitutto tre aspetti fondamentali:</span><span class="sxs-lookup"><span data-stu-id="08925-124">When you monitor [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and the Microsoft Windows operating system to investigate performance-related issues, concentrate your initial efforts in three main areas:</span></span>  
  
-   <span data-ttu-id="08925-125">Attività del disco</span><span class="sxs-lookup"><span data-stu-id="08925-125">Disk activity</span></span>  
  
-   <span data-ttu-id="08925-126">Utilizzo del processore</span><span class="sxs-lookup"><span data-stu-id="08925-126">Processor utilization</span></span>  
  
-   <span data-ttu-id="08925-127">Utilizzo della memoria</span><span class="sxs-lookup"><span data-stu-id="08925-127">Memory usage</span></span>  
  
 <span data-ttu-id="08925-128">Il monitoraggio di un computer in cui è in esecuzione Monitoraggio di sistema può determinare un lieve peggioramento delle prestazioni del computer monitorato.</span><span class="sxs-lookup"><span data-stu-id="08925-128">Monitoring a computer on which System Monitor is running can affect computer performance slightly.</span></span> <span data-ttu-id="08925-129">Per questo motivo, è consigliabile registrare i dati generati da Monitoraggio di sistema in un altro disco o computer in modo da limitare il carico di lavoro sul computer monitorato oppure eseguire Monitoraggio di sistema da un computer remoto.</span><span class="sxs-lookup"><span data-stu-id="08925-129">Therefore, either log the System Monitor data to another disk (or computer) so that it reduces the effect on the computer being monitored, or run System Monitor from a remote computer.</span></span> <span data-ttu-id="08925-130">È inoltre consigliabile monitorare solo i contatori a cui si è interessati.</span><span class="sxs-lookup"><span data-stu-id="08925-130">Monitor only the counters in which you are interested.</span></span> <span data-ttu-id="08925-131">Se il numero dei contatori monitorati è eccessivamente elevato, al processo di monitoraggio verrà aggiunto l'overhead dell'utilizzo delle risorse, che può influire sulle prestazioni del computer monitorato.</span><span class="sxs-lookup"><span data-stu-id="08925-131">If you monitor too many counters, resource usage overhead is added to the monitoring process and affects the performance of the computer that is being monitored.</span></span>  
  
## <a name="system-monitor-tasks"></a><span data-ttu-id="08925-132">Attività di Monitoraggio di sistema</span><span class="sxs-lookup"><span data-stu-id="08925-132">System Monitor Tasks</span></span>  
  
|<span data-ttu-id="08925-133">Descrizione dell'attività</span><span class="sxs-lookup"><span data-stu-id="08925-133">Task Description</span></span>|<span data-ttu-id="08925-134">Argomento</span><span class="sxs-lookup"><span data-stu-id="08925-134">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="08925-135">Viene descritto quando utilizzare Monitoraggio di sistema e ne viene illustrato l'impatto sulle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="08925-135">Describes when to use System Monitor and discusses performance overhead when you use System Monitor.</span></span>|[<span data-ttu-id="08925-136">Eseguire Monitoraggio di sistema</span><span class="sxs-lookup"><span data-stu-id="08925-136">Run System Monitor</span></span>](run-system-monitor.md)|  
|<span data-ttu-id="08925-137">Viene descritto come monitorare i contatori dei dischi per determinare l'attività dei dischi e la quantità di operazioni di I/O generate dai componenti di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="08925-137">Describes how to monitor disk counters to determine disk activity and the amount of I/O generated by their SQL Server components.</span></span>|[<span data-ttu-id="08925-138">Monitorare l'uso del disco</span><span class="sxs-lookup"><span data-stu-id="08925-138">Monitor Disk Usage</span></span>](monitor-disk-usage.md)|  
|<span data-ttu-id="08925-139">Viene descritto come monitorare un'istanza di Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per verificare che i valori di utilizzo della CPU rientrino in intervalli normali.</span><span class="sxs-lookup"><span data-stu-id="08925-139">Describes how to monitor an instance of Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to determine whether CPU usage rates are within normal ranges.</span></span>|[<span data-ttu-id="08925-140">Monitorare l'uso della CPU</span><span class="sxs-lookup"><span data-stu-id="08925-140">Monitor CPU Usage</span></span>](monitor-cpu-usage.md)|  
|<span data-ttu-id="08925-141">Viene descritto come monitorare un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per verificare che l'utilizzo della memoria rientri negli intervalli standard.</span><span class="sxs-lookup"><span data-stu-id="08925-141">Describes how to monitor an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to confirm that memory usage is within typical ranges.</span></span>|[<span data-ttu-id="08925-142">Monitorare l'uso della memoria</span><span class="sxs-lookup"><span data-stu-id="08925-142">Monitor Memory Usage</span></span>](monitor-memory-usage.md)|  
|<span data-ttu-id="08925-143">Viene descritto come creare un avviso generato nel momento in cui viene raggiunto un valore soglia di un contatore di Monitoraggio di sistema.</span><span class="sxs-lookup"><span data-stu-id="08925-143">Describes how to create an alert that is raised when a threshold value for a System Monitor counter has been reached.</span></span>|[<span data-ttu-id="08925-144">Creare un avviso del database di SQL Server</span><span class="sxs-lookup"><span data-stu-id="08925-144">Create a SQL Server Database Alert</span></span>](create-a-sql-server-database-alert.md)|  
|<span data-ttu-id="08925-145">Viene descritto come creare grafici, avvisi, log e report per monitorare un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="08925-145">Describes how to you create charts, alerts, logs, and reports to monitor an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>|[<span data-ttu-id="08925-146">Creare grafici, avvisi, log e report</span><span class="sxs-lookup"><span data-stu-id="08925-146">Create Charts, Alerts, Logs, and Reports</span></span>](create-charts-alerts-logs-and-reports.md)|  
|<span data-ttu-id="08925-147">Vengono elencati oggetti e contatori utilizzati da Monitoraggio di sistema per monitorare le attività nei computer che eseguono un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="08925-147">Lists objects and counters that System Monitor uses to monitor activity in computers running an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>|[<span data-ttu-id="08925-148">Usare oggetti di SQL Server</span><span class="sxs-lookup"><span data-stu-id="08925-148">Use SQL Server Objects</span></span>](use-sql-server-objects.md)|  
|<span data-ttu-id="08925-149">Vengono elencati oggetti e contatori utilizzati da Monitoraggio di sistema per monitorare le attività OLTP in memoria.</span><span class="sxs-lookup"><span data-stu-id="08925-149">Lists objects and counters that System Monitor uses to monitor In-Memory OLTP activity.</span></span>|[<span data-ttu-id="08925-150">XTP &#40;i contatori delle prestazioni di OLTP in memoria&#41;</span><span class="sxs-lookup"><span data-stu-id="08925-150">XTP &#40;In-Memory OLTP&#41; Performance Counters</span></span>](../../integration-services/performance/performance-counters.md)|  
  
  
