---
title: Individuare i colli di bottiglia | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- resource bottlenecks [SQL Server]
- database monitoring [SQL Server], bottlenecks
- performance [SQL Server], bottlenecks
- tuning databases [SQL Server], bottlenecks
- monitoring server performance [SQL Server], bottlenecks
- monitoring performance [SQL Server], bottlenecks
- database performance [SQL Server], bottlenecks
- server performance [SQL Server], bottlenecks
- bottlenecks [SQL Server]
- identifying bottlenecks [SQL Server]
ms.assetid: db079e65-ee80-4105-aec9-f8230d0d6635
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: e941b3f4a1185177cef007eb6a02a71ae1adece7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713063"
---
# <a name="identify-bottlenecks"></a><span data-ttu-id="98dac-102">Individuare i colli di bottiglia</span><span class="sxs-lookup"><span data-stu-id="98dac-102">Identify Bottlenecks</span></span>
  <span data-ttu-id="98dac-103">In seguito all'accesso simultaneo alle risorse condivise si possono verificare colli di bottiglia.</span><span class="sxs-lookup"><span data-stu-id="98dac-103">Simultaneous access to shared resources causes bottlenecks.</span></span> <span data-ttu-id="98dac-104">I colli di bottiglia in genere sono inevitabili e presenti in qualsiasi sistema software.</span><span class="sxs-lookup"><span data-stu-id="98dac-104">In general, bottlenecks are present in every software system and are inevitable.</span></span> <span data-ttu-id="98dac-105">È tuttavia necessario identificare e ottimizzare le situazioni di eccesso di domanda, in quanto una domanda eccessiva delle risorse condivise comporta un rallentamento dei tempi di risposta.</span><span class="sxs-lookup"><span data-stu-id="98dac-105">However, excessive demands on shared resources cause poor response time and must be identified and tuned.</span></span>  
  
 <span data-ttu-id="98dac-106">Le possibili cause dei colli di bottiglia sono:</span><span class="sxs-lookup"><span data-stu-id="98dac-106">Causes of bottlenecks include:</span></span>  
  
-   <span data-ttu-id="98dac-107">Risorse insufficienti che rendono necessari l'aggiunta di componenti o l'aggiornamento dei componenti disponibili.</span><span class="sxs-lookup"><span data-stu-id="98dac-107">Insufficient resources, requiring additional or upgraded components.</span></span>  
  
-   <span data-ttu-id="98dac-108">Carichi di lavoro non distribuiti equamente tra risorse dello stesso tipo, ad esempio monopolizzazione di un disco.</span><span class="sxs-lookup"><span data-stu-id="98dac-108">Resources of the same type among which workloads are not distributed evenly; for example, one disk is being monopolized.</span></span>  
  
-   <span data-ttu-id="98dac-109">Funzionamento non corretto delle risorse.</span><span class="sxs-lookup"><span data-stu-id="98dac-109">Malfunctioning resources.</span></span>  
  
-   <span data-ttu-id="98dac-110">Configurazione non corretta delle risorse.</span><span class="sxs-lookup"><span data-stu-id="98dac-110">Incorrectly configured resources.</span></span>  
  
## <a name="analyzing-bottlenecks"></a><span data-ttu-id="98dac-111">Analisi dei colli di bottiglia</span><span class="sxs-lookup"><span data-stu-id="98dac-111">Analyzing Bottlenecks</span></span>  
 <span data-ttu-id="98dac-112">La durata eccessiva di alcuni eventi segnala la presenza di colli di bottiglia che è possibile ottimizzare.</span><span class="sxs-lookup"><span data-stu-id="98dac-112">Excessive durations for various events are indicators of bottlenecks that can be tuned.</span></span>  
  
 <span data-ttu-id="98dac-113">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="98dac-113">For example:</span></span>  
  
-   <span data-ttu-id="98dac-114">È possibile che un altro componente impedisca che il processo di caricamento raggiunga il componente in uso, con un conseguente incremento dei tempi necessari per completare il caricamento.</span><span class="sxs-lookup"><span data-stu-id="98dac-114">Some other component may prevent the load from reaching this component thereby increasing the time to complete the load.</span></span>  
  
-   <span data-ttu-id="98dac-115">Le richieste client potrebbero richiedere tempi più lunghi a causa di traffico di rete intenso.</span><span class="sxs-lookup"><span data-stu-id="98dac-115">Client requests may take longer due to network congestion.</span></span>  
  
 <span data-ttu-id="98dac-116">Per la valutazione delle prestazioni del server allo scopo di individuare eventuali colli di bottiglia, è necessario eseguire il monitoraggio delle cinque aree fondamentali descritte nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="98dac-116">Following are five key areas to monitor when tracking server performance to identify bottlenecks.</span></span>  
  
|<span data-ttu-id="98dac-117">Possibile area in cui è presente un collo di bottiglia</span><span class="sxs-lookup"><span data-stu-id="98dac-117">Possible bottleneck area</span></span>|<span data-ttu-id="98dac-118">Effetti sul server</span><span class="sxs-lookup"><span data-stu-id="98dac-118">Effects on the server</span></span>|  
|------------------------------|---------------------------|  
|<span data-ttu-id="98dac-119">Utilizzo della memoria</span><span class="sxs-lookup"><span data-stu-id="98dac-119">Memory usage</span></span>|<span data-ttu-id="98dac-120">Se la memoria allocata per Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o disponibile per il sistema non è sufficiente, le prestazioni risultano inferiori.</span><span class="sxs-lookup"><span data-stu-id="98dac-120">Insufficient memory allocated or available to Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] degrades performance.</span></span> <span data-ttu-id="98dac-121">I dati infatti devono essere letti nel disco anziché direttamente nella cache dei dati.</span><span class="sxs-lookup"><span data-stu-id="98dac-121">Data must be read from the disk rather than directly from the data cache.</span></span> <span data-ttu-id="98dac-122">Microsoft Windows NT esegue un paging eccessivo con uno swapping dei dati da e nel disco in base alle pagine richieste.</span><span class="sxs-lookup"><span data-stu-id="98dac-122">Microsoft Windows operating systems perform excessive paging by swapping data to and from the disk as the pages are needed.</span></span>|  
|<span data-ttu-id="98dac-123">Uso della CPU</span><span class="sxs-lookup"><span data-stu-id="98dac-123">CPU utilization</span></span>|<span data-ttu-id="98dac-124">Se la frequenza di utilizzo della CPU risulta costantemente elevata, potrebbe essere necessario ottimizzare le query [!INCLUDE[tsql](../../includes/tsql-md.md)] o aggiornare la CPU.</span><span class="sxs-lookup"><span data-stu-id="98dac-124">A chronically high CPU utilization rate may indicate that [!INCLUDE[tsql](../../includes/tsql-md.md)] queries need to be tuned or that a CPU upgrade is needed.</span></span>|  
|<span data-ttu-id="98dac-125">Input/output (I/O) del disco</span><span class="sxs-lookup"><span data-stu-id="98dac-125">Disk input/output (I/O)</span></span>|[!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="98dac-126">le query possono essere ottimizzate per ridurre le operazioni di I/O del disco non necessarie, ad esempio tramite l'uso di indici.</span><span class="sxs-lookup"><span data-stu-id="98dac-126">queries can be tuned to reduce unnecessary I/O; for example, by employing indexes.</span></span>|  
|<span data-ttu-id="98dac-127">Connessioni utente</span><span class="sxs-lookup"><span data-stu-id="98dac-127">User connections</span></span>|<span data-ttu-id="98dac-128">Se il numero di utenti che accede al server simultaneamente è molto elevato, le prestazioni potrebbe risultare inferiori.</span><span class="sxs-lookup"><span data-stu-id="98dac-128">Too many users may be accessing the server simultaneously causing performance degradation.</span></span>|  
|<span data-ttu-id="98dac-129">Blocchi di blocco</span><span class="sxs-lookup"><span data-stu-id="98dac-129">Blocking locks</span></span>|<span data-ttu-id="98dac-130">L'utilizzo di applicazioni progettate in modo non corretto può causare blocchi e ostacolare la concorrenza, con un conseguente rallentamento dei tempi di risposta e una diminuzione della velocità effettiva.</span><span class="sxs-lookup"><span data-stu-id="98dac-130">Incorrectly designed applications can cause locks and hamper concurrency, thus causing longer response times and lower transaction throughput rates.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="98dac-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="98dac-131">See Also</span></span>  
 <span data-ttu-id="98dac-132">[Monitorare l'utilizzo della CPU](../performance-monitor/monitor-cpu-usage.md) </span><span class="sxs-lookup"><span data-stu-id="98dac-132">[Monitor CPU Usage](../performance-monitor/monitor-cpu-usage.md) </span></span>  
 <span data-ttu-id="98dac-133">[Monitoraggio dell'utilizzo del disco](../performance-monitor/monitor-disk-usage.md) </span><span class="sxs-lookup"><span data-stu-id="98dac-133">[Monitor Disk Usage](../performance-monitor/monitor-disk-usage.md) </span></span>  
 <span data-ttu-id="98dac-134">[Monitoraggio dell'utilizzo della memoria](../performance-monitor/monitor-memory-usage.md) </span><span class="sxs-lookup"><span data-stu-id="98dac-134">[Monitor Memory Usage](../performance-monitor/monitor-memory-usage.md) </span></span>  
 <span data-ttu-id="98dac-135">[Oggetto Statistiche generali di SQL Server](../performance-monitor/sql-server-general-statistics-object.md) </span><span class="sxs-lookup"><span data-stu-id="98dac-135">[SQL Server, General Statistics Object](../performance-monitor/sql-server-general-statistics-object.md) </span></span>  
 [<span data-ttu-id="98dac-136">Oggetto Locks di SQL Server</span><span class="sxs-lookup"><span data-stu-id="98dac-136">SQL Server, Locks Object</span></span>](../performance-monitor/sql-server-locks-object.md)  
  
  
