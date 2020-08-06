---
title: Prestazioni, snapshot, memorizzazione nella cache (Reporting Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- performance [Reporting Services]
- Reporting Services, performance
ms.assetid: 85afd00f-e8d7-4ef7-9174-2ff84d82f960
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f171586e136b36bd694fa40b15272f62e1cb1378
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716091"
---
# <a name="performance-snapshots-caching-reporting-services"></a><span data-ttu-id="7809a-102">Prestazioni, snapshot, memorizzazione nella cache (Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="7809a-102">Performance, Snapshots, Caching (Reporting Services)</span></span>
  <span data-ttu-id="7809a-103">Le prestazioni del server di report sono influenzate da una combinazione di fattori che includono hardware, numero di utenti simultanei che accedono ai report, quantità di dati in un report e formato di output.</span><span class="sxs-lookup"><span data-stu-id="7809a-103">Report server performance is affected by a combination of factors that include hardware, number of concurrent users accessing reports, the amount of data in a report, and output format.</span></span> <span data-ttu-id="7809a-104">Per comprendere i fattori relativi alle prestazioni specifici dell'installazione e quali rimedi produrranno i risultati desiderati, sarà necessario ottenere dati di base ed eseguire test.</span><span class="sxs-lookup"><span data-stu-id="7809a-104">To understand the performance factors that are specific to your installation and which remedies will produce the results you want, you will need to get baseline data and run tests.</span></span> <span data-ttu-id="7809a-105">Per ulteriori informazioni su strumenti e linee guida, vedere le pubblicazioni seguenti su MSDN relative all' [ottimizzazione delle prestazioni di Reporting Services](https://blogs.msdn.com/b/sqlcat/archive/2013/10/30/reporting-services-performance-and-optimization.aspx) e all' [utilizzo di Visual Studio 2005 per eseguire test di carico in un server di report di SQL Server 2005 Reporting Services](https://go.microsoft.com/fwlink/?LinkID=77519).</span><span class="sxs-lookup"><span data-stu-id="7809a-105">For more information about tools and guidelines, see the following publications on MSDN: [Reporting Services Performance Optimization](https://blogs.msdn.com/b/sqlcat/archive/2013/10/30/reporting-services-performance-and-optimization.aspx) and [Using Visual Studio 2005 to Perform Load Testing on a SQL Server 2005 Reporting Services Report Server](https://go.microsoft.com/fwlink/?LinkID=77519).</span></span>  
  
 <span data-ttu-id="7809a-106">I principi generali da considerare includono gli aspetti seguenti:</span><span class="sxs-lookup"><span data-stu-id="7809a-106">General principles to consider include the following:</span></span>  
  
-   <span data-ttu-id="7809a-107">L'elaborazione e il rendering del report sono operazioni che utilizzano una quantità elevata di memoria.</span><span class="sxs-lookup"><span data-stu-id="7809a-107">Report processing and rendering are memory intensive operations.</span></span> <span data-ttu-id="7809a-108">Quando possibile, scegliere un computer che dispone di molta memoria.</span><span class="sxs-lookup"><span data-stu-id="7809a-108">When possible, choose a computer that has a lot of memory.</span></span>  
  
-   <span data-ttu-id="7809a-109">Se il server di report e il relativo database vengono ospitati in computer separati, le prestazioni ottenute sono migliori rispetto alla situazioni in cui entrambi sono ospitati in un solo computer di fascia alta.</span><span class="sxs-lookup"><span data-stu-id="7809a-109">Hosting the report server and the report server database on separate computers tends to provide better performance than hosting both on a single high-end computer.</span></span>  
  
-   <span data-ttu-id="7809a-110">Se tutti i report vengono elaborati lentamente, considerare una distribuzione con scalabilità orizzontale in cui più istanze del server di report supportano un solo database del server di report.</span><span class="sxs-lookup"><span data-stu-id="7809a-110">If all reports are processing slowly, consider a scale-out deployment where multiple report server instances support a single report server database.</span></span> <span data-ttu-id="7809a-111">Per ottenere risultati migliori, utilizzare software di bilanciamento carico per distribuire uniformemente le richieste nella distribuzione.</span><span class="sxs-lookup"><span data-stu-id="7809a-111">For best results, use load balancing software to distribute requests evenly across the deployment.</span></span>  
  
-   <span data-ttu-id="7809a-112">Se l'elaborazione di un singolo report è lenta, ottimizzare le query del set di dati del report se il report viene eseguito su richiesta.</span><span class="sxs-lookup"><span data-stu-id="7809a-112">If a single report is processing slowly, tune report dataset queries if the report must run on demand.</span></span> <span data-ttu-id="7809a-113">Si consideri inoltre la possibilità di utilizzare set di dati condivisi che è possibile memorizzare nella cache, di memorizzare il report nella cache o di eseguire il report come snapshot.</span><span class="sxs-lookup"><span data-stu-id="7809a-113">You might also consider using shared datasets that you can cache, caching the report, or running the report as a snapshot.</span></span>  
  
-   <span data-ttu-id="7809a-114">Se tutti i report vengono elaborati lentamente per ottenere un formato specifico (ad esempio durante il rendering in formato PDF), prendere in considerazione l'utilizzo del recapito tramite la condivisione file, l'aggiunta di ulteriore memoria o la scelta di un formato diverso.</span><span class="sxs-lookup"><span data-stu-id="7809a-114">If all reports process slowly in a specific format (for example, while rendering to PDF), consider file share delivery, adding more memory, or choosing a different format.</span></span>  
  
-   <span data-ttu-id="7809a-115">Per individuare la quantità di tempo necessario per elaborare un report e altre misure relative all'utilizzo, esaminare il log di esecuzione del server di report.</span><span class="sxs-lookup"><span data-stu-id="7809a-115">To find out how long it takes to process a report and other usage metrics, review the report server execution log.</span></span> <span data-ttu-id="7809a-116">Per ulteriori informazioni, vedere [il log di esecuzione del server di report e la vista ExecutionLog3](report-server-executionlog-and-the-executionlog3-view.md).</span><span class="sxs-lookup"><span data-stu-id="7809a-116">For more information, see [Report Server Execution Log and the ExecutionLog3 View](report-server-executionlog-and-the-executionlog3-view.md).</span></span>  
  
-   <span data-ttu-id="7809a-117">Per altre informazioni su come limitare i problemi di prestazioni ottimizzando le impostazioni di configurazione di Gestione memoria, vedere [Configurare la memoria disponibile per applicazioni del server di report](../report-server/configure-available-memory-for-report-server-applications.md).</span><span class="sxs-lookup"><span data-stu-id="7809a-117">For more information about how to mitigate performance issues by tuning memory management configuration settings, see [Configure Available Memory for Report Server Applications](../report-server/configure-available-memory-for-report-server-applications.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7809a-118">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="7809a-118">In This Section</span></span>  
 [<span data-ttu-id="7809a-119">Monitoraggio delle prestazioni del server di report</span><span class="sxs-lookup"><span data-stu-id="7809a-119">Monitoring Report Server Performance</span></span>](monitoring-report-server-performance.md)  
 <span data-ttu-id="7809a-120">Descrive gli oggetti relativi alle prestazioni che è possibile utilizzare per tenere traccia del carico di elaborazione nel server.</span><span class="sxs-lookup"><span data-stu-id="7809a-120">Describes the performance objects you can use to track the processing load on your server.</span></span>  
  
 [<span data-ttu-id="7809a-121">Impostare le proprietà di elaborazione dei report</span><span class="sxs-lookup"><span data-stu-id="7809a-121">Set Report Processing Properties</span></span>](set-report-processing-properties.md)  
 <span data-ttu-id="7809a-122">Descrive come configurare un report per l'esecuzione su richiesta, dalla cache o in base a una pianificazione come snapshot del report.</span><span class="sxs-lookup"><span data-stu-id="7809a-122">Describes ways of configuring a report to run on demand, from cache, or on a schedule as a report snapshot.</span></span>  
  
 [<span data-ttu-id="7809a-123">Configurare la memoria disponibile per applicazioni del server di report</span><span class="sxs-lookup"><span data-stu-id="7809a-123">Configure Available Memory for Report Server Applications</span></span>](../report-server/configure-available-memory-for-report-server-applications.md)  
 <span data-ttu-id="7809a-124">Viene descritto come è possibile ignorare il comportamento predefinito per la gestione della memoria.</span><span class="sxs-lookup"><span data-stu-id="7809a-124">Describes how you can override default memory management behavior.</span></span>  
  
 [<span data-ttu-id="7809a-125">Memorizzazione dei report nella cache &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="7809a-125">Caching Reports &#40;SSRS&#41;</span></span>](caching-reports-ssrs.md)  
 <span data-ttu-id="7809a-126">Descrive il comportamento di memorizzazione del report nella cache in un server di report.</span><span class="sxs-lookup"><span data-stu-id="7809a-126">Describes report caching behavior on a report server.</span></span>  
  
 [<span data-ttu-id="7809a-127">Memorizzare nella cache set di dati condivisi &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="7809a-127">Cache Shared Datasets &#40;SSRS&#41;</span></span>](cache-shared-datasets-ssrs.md)  
 <span data-ttu-id="7809a-128">Descrive il comportamento di memorizzazione del set di dati condiviso nella cache in un server di report.</span><span class="sxs-lookup"><span data-stu-id="7809a-128">Describes shared dataset caching behavior on a report server.</span></span>  
  
 [<span data-ttu-id="7809a-129">Elaborare report di grandi dimensioni</span><span class="sxs-lookup"><span data-stu-id="7809a-129">Process Large Reports</span></span>](process-large-reports.md)  
 <span data-ttu-id="7809a-130">Offre indicazioni su come configurare e distribuire un report di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="7809a-130">Provides recommendations on how to configure and distribute a large report.</span></span>  
  
 [<span data-ttu-id="7809a-131">Impostazione dei valori di timeout per l'elaborazione di report e di set di dati condivisi &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="7809a-131">Setting Time-out Values for Report and Shared Dataset Processing &#40;SSRS&#41;</span></span>](setting-time-out-values-for-report-and-shared-dataset-processing-ssrs.md)  
 <span data-ttu-id="7809a-132">Illustra come impostare i timeout relativi all'esecuzione del report e di query.</span><span class="sxs-lookup"><span data-stu-id="7809a-132">Explains how to set time outs on query and report processing.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7809a-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7809a-133">See Also</span></span>  
 <span data-ttu-id="7809a-134">[Manage a Running Process](../subscriptions/manage-a-running-process.md) </span><span class="sxs-lookup"><span data-stu-id="7809a-134">[Manage a Running Process](../subscriptions/manage-a-running-process.md) </span></span>  
 [<span data-ttu-id="7809a-135">Verifica dell'esecuzione di un report</span><span class="sxs-lookup"><span data-stu-id="7809a-135">Verifying a Report Run</span></span>](verifying-a-report-run.md)  
  
  
