---
title: MSSQL_ENG014161 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014161 error
ms.assetid: 4b983e76-bb77-43c5-b44b-19919d3da619
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e8cf85181e444385e1a3908761ba71414b68cf3e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623171"
---
# <a name="mssql_eng014161"></a><span data-ttu-id="24a51-102">MSSQL_ENG014161</span><span class="sxs-lookup"><span data-stu-id="24a51-102">MSSQL_ENG014161</span></span>
    
## <a name="message-details"></a><span data-ttu-id="24a51-103">Dettagli messaggio</span><span class="sxs-lookup"><span data-stu-id="24a51-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="24a51-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="24a51-104">Product Name</span></span>|<span data-ttu-id="24a51-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="24a51-105">SQL Server</span></span>|  
|<span data-ttu-id="24a51-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="24a51-106">Event ID</span></span>|<span data-ttu-id="24a51-107">14161</span><span class="sxs-lookup"><span data-stu-id="24a51-107">14161</span></span>|  
|<span data-ttu-id="24a51-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="24a51-108">Event Source</span></span>|<span data-ttu-id="24a51-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="24a51-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="24a51-110">Componente</span><span class="sxs-lookup"><span data-stu-id="24a51-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="24a51-111">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="24a51-111">Symbolic Name</span></span>||  
|<span data-ttu-id="24a51-112">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="24a51-112">Message Text</span></span>|<span data-ttu-id="24a51-113">È stata impostata la soglia [%s:%s] per la pubblicazione [%s].</span><span class="sxs-lookup"><span data-stu-id="24a51-113">The threshold [%s:%s] for the publication [%s] has been set.</span></span> <span data-ttu-id="24a51-114">Verificare che l'agente di lettura log e l'agente di distribuzione siano in esecuzione e siano in grado di rispettare i requisiti relativi alla latenza.</span><span class="sxs-lookup"><span data-stu-id="24a51-114">Make sure that the logreader and distribution agents are running and can match the latency requirement.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="24a51-115">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="24a51-115">Explanation</span></span>  
 <span data-ttu-id="24a51-116">La replica consente di attivare avvisi per numerose condizioni,</span><span class="sxs-lookup"><span data-stu-id="24a51-116">Replication lets you enable warnings for several conditions.</span></span> <span data-ttu-id="24a51-117">tra cui il superamento di una latenza specificata per sottoscrizioni transazionali.</span><span class="sxs-lookup"><span data-stu-id="24a51-117">This includes exceeding a specified latency for transactional subscriptions.</span></span> <span data-ttu-id="24a51-118">Per latenza si intende l'intervallo di tempo che intercorre tra il commit di una modifica dei dati nel server di pubblicazione e il commit della modifica corrispondente nel Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="24a51-118">Latency is the period of time that elapses between a data change being committed at the Publisher and the corresponding change being committed at the Subscriber.</span></span>  
  
 <span data-ttu-id="24a51-119">Quando si attiva un avviso utilizzando Monitoraggio replica o [sp_replmonitorchangepublicationthreshold](/sql/relational-databases/system-stored-procedures/sp-replmonitorchangepublicationthreshold-transact-sql), viene specificata una soglia che determina quando è generato l'avviso.</span><span class="sxs-lookup"><span data-stu-id="24a51-119">When you enable a warning by using Replication Monitor or [sp_replmonitorchangepublicationthreshold](/sql/relational-databases/system-stored-procedures/sp-replmonitorchangepublicationthreshold-transact-sql), you specify a threshold that determines when a warning is triggered.</span></span> <span data-ttu-id="24a51-120">Quando tale soglia viene raggiunta o superata, viene visualizzato un avviso in Monitoraggio replica e viene registrato un evento nel registro eventi di Windows.</span><span class="sxs-lookup"><span data-stu-id="24a51-120">When that threshold is met or exceeded, a warning is displayed in Replication Monitor, and an event is written to the Windows event log.</span></span> <span data-ttu-id="24a51-121">Il raggiungimento di una soglia può inoltre generare un avviso SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="24a51-121">Reaching a threshold can also trigger a SQL Server Agent alert.</span></span> <span data-ttu-id="24a51-122">Per altre informazioni, vedere [Impostare valori di soglia e avvisi in Monitoraggio replica](monitor/set-thresholds-and-warnings-in-replication-monitor.md) e [Monitorare la replica a livello di programmazione](monitoring-replication.md).</span><span class="sxs-lookup"><span data-stu-id="24a51-122">For more information, see [Set Thresholds and Warnings in Replication Monitor](monitor/set-thresholds-and-warnings-in-replication-monitor.md) and [Programmatically Monitor Replication](monitoring-replication.md).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="24a51-123">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="24a51-123">User Action</span></span>  
 <span data-ttu-id="24a51-124">Se una sottoscrizione supera una soglia di latenza, è necessario stabilire se il fenomeno dipende da un problema di prestazioni del sistema o se la soglia deve essere regolata.</span><span class="sxs-lookup"><span data-stu-id="24a51-124">If a subscription exceeds a latency threshold, you must determine whether there is a performance issue with the system or whether the threshold should be adjusted.</span></span> <span data-ttu-id="24a51-125">Dopo avere configurato la replica, sviluppare dati di riferimento per le prestazioni in modo da poter stabilire il comportamento della replica in presenza del carico di lavoro tipico delle applicazioni e della topologia in uso.</span><span class="sxs-lookup"><span data-stu-id="24a51-125">After you configure replication, develop a performance baseline that will let you determine how replication behaves with a workload that is typical for your applications and topology.</span></span> <span data-ttu-id="24a51-126">Includere nei dati di riferimento anche la latenza al fine di poter impostare un valore appropriato per la soglia.</span><span class="sxs-lookup"><span data-stu-id="24a51-126">Include latency in this baseline so that you can set an appropriate value for the threshold.</span></span>  
  
 <span data-ttu-id="24a51-127">Se il valore soglia è appropriato ma viene superato, è necessario individuare l'area del sistema a cui è dovuto il collo di bottiglia a livello di prestazioni.</span><span class="sxs-lookup"><span data-stu-id="24a51-127">If the threshold value is appropriate, but it is being exceeded, you must determine where the performance bottleneck is in the system.</span></span> <span data-ttu-id="24a51-128">Per ulteriori informazioni sul monitoraggio e la risoluzione dei problemi delle prestazioni di replica, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="24a51-128">For more information about how to monitor and troubleshoot replication performance, see the following topics:</span></span>  
  
-   [<span data-ttu-id="24a51-129">Misurare la latenza e convalidare le connessioni per la replica transazionale</span><span class="sxs-lookup"><span data-stu-id="24a51-129">Measure Latency and Validate Connections for Transactional Replication</span></span>](monitor/measure-latency-and-validate-connections-for-transactional-replication.md)  
  
-   [<span data-ttu-id="24a51-130">Monitorare le prestazioni con Monitoraggio replica</span><span class="sxs-lookup"><span data-stu-id="24a51-130">Monitor Performance with Replication Monitor</span></span>](monitor/monitor-performance-with-replication-monitor.md)  
  
## <a name="see-also"></a><span data-ttu-id="24a51-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="24a51-131">See Also</span></span>  
 [<span data-ttu-id="24a51-132">Guida di riferimento a errori ed eventi &#40;replica&#41;</span><span class="sxs-lookup"><span data-stu-id="24a51-132">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
