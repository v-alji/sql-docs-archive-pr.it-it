---
title: MSSQL_ENG014163 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014163 error
ms.assetid: b53dd463-ba36-421e-9745-67c7387e68dd
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b407d64b56d8d829d691b54917baae5bf3adbccd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627199"
---
# <a name="mssql_eng014163"></a><span data-ttu-id="a7c13-102">MSSQL_ENG014163</span><span class="sxs-lookup"><span data-stu-id="a7c13-102">MSSQL_ENG014163</span></span>
    
## <a name="message-details"></a><span data-ttu-id="a7c13-103">Dettagli messaggio</span><span class="sxs-lookup"><span data-stu-id="a7c13-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a7c13-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="a7c13-104">Product Name</span></span>|<span data-ttu-id="a7c13-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="a7c13-105">SQL Server</span></span>|  
|<span data-ttu-id="a7c13-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="a7c13-106">Event ID</span></span>|<span data-ttu-id="a7c13-107">14163</span><span class="sxs-lookup"><span data-stu-id="a7c13-107">14163</span></span>|  
|<span data-ttu-id="a7c13-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="a7c13-108">Event Source</span></span>|<span data-ttu-id="a7c13-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="a7c13-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="a7c13-110">Componente</span><span class="sxs-lookup"><span data-stu-id="a7c13-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="a7c13-111">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="a7c13-111">Symbolic Name</span></span>||  
|<span data-ttu-id="a7c13-112">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="a7c13-112">Message Text</span></span>|<span data-ttu-id="a7c13-113">È stata impostata la soglia [%s:%s] per la pubblicazione [%s].</span><span class="sxs-lookup"><span data-stu-id="a7c13-113">The threshold [%s:%s] for the publication [%s] has been set.</span></span> <span data-ttu-id="a7c13-114">Verificare che l'agente di merge sia in esecuzione e sia in grado di rispettare i requisiti previsti.</span><span class="sxs-lookup"><span data-stu-id="a7c13-114">Please make sure that the merge agent is running and can match the expected requirement.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a7c13-115">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="a7c13-115">Explanation</span></span>  
 <span data-ttu-id="a7c13-116">La replica consente di attivare avvisi per numerose condizioni,</span><span class="sxs-lookup"><span data-stu-id="a7c13-116">Replication lets you enable warnings for several conditions.</span></span> <span data-ttu-id="a7c13-117">tra cui il superamento della durata specificata per la sincronizzazione delle modifiche tra un server di pubblicazione e un Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="a7c13-117">This includes exceeding a specified length of time for synchronizing changes between a merge Publisher and Subscriber.</span></span> <span data-ttu-id="a7c13-118">È possibile specificare momenti diversi per connessioni LAN e remote.</span><span class="sxs-lookup"><span data-stu-id="a7c13-118">Different times can be specified for LAN connections and dial-up connections.</span></span>  
  
 <span data-ttu-id="a7c13-119">Quando si attiva un avviso utilizzando Monitoraggio replica o [sp_replmonitorchangepublicationthreshold](/sql/relational-databases/system-stored-procedures/sp-replmonitorchangepublicationthreshold-transact-sql), viene specificata una soglia che determina quando è generato l'avviso.</span><span class="sxs-lookup"><span data-stu-id="a7c13-119">When you enable a warning by using Replication Monitor or [sp_replmonitorchangepublicationthreshold](/sql/relational-databases/system-stored-procedures/sp-replmonitorchangepublicationthreshold-transact-sql), you specify a threshold that determines when a warning is triggered.</span></span> <span data-ttu-id="a7c13-120">Quando tale soglia viene raggiunta o superata, viene visualizzato un avviso in Monitoraggio replica e viene registrato un evento nel registro eventi di Windows.</span><span class="sxs-lookup"><span data-stu-id="a7c13-120">When that threshold is met or exceeded, a warning is displayed in Replication Monitor, and an event is written to the Windows event log.</span></span> <span data-ttu-id="a7c13-121">Il raggiungimento di una soglia può inoltre generare un avviso SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="a7c13-121">Reaching a threshold can also trigger a SQL Server Agent alert.</span></span> <span data-ttu-id="a7c13-122">Per altre informazioni, vedere [Impostare valori di soglia e avvisi in Monitoraggio replica](monitor/set-thresholds-and-warnings-in-replication-monitor.md) e [Monitorare la replica a livello di programmazione](monitoring-replication.md).</span><span class="sxs-lookup"><span data-stu-id="a7c13-122">For more information, see [Set Thresholds and Warnings in Replication Monitor](monitor/set-thresholds-and-warnings-in-replication-monitor.md) and [Programmatically Monitor Replication](monitoring-replication.md).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a7c13-123">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="a7c13-123">User Action</span></span>  
 <span data-ttu-id="a7c13-124">Se una sottoscrizione supera una soglia di durata, è necessario stabilire se il fenomeno dipende da un problema di prestazioni del sistema o se la soglia deve essere regolata.</span><span class="sxs-lookup"><span data-stu-id="a7c13-124">If a subscription exceeds a duration threshold, you must determine whether there is a performance issue with the system or whether the threshold should be adjusted.</span></span> <span data-ttu-id="a7c13-125">Dopo avere configurato la replica, sviluppare dati di riferimento per le prestazioni in modo da poter stabilire il comportamento della replica in presenza del carico di lavoro tipico delle applicazioni e della topologia in uso.</span><span class="sxs-lookup"><span data-stu-id="a7c13-125">After you configure replication, develop a performance baseline that will let you determine how replication behaves with a workload that is typical for your applications and topology.</span></span> <span data-ttu-id="a7c13-126">Includere nei dati di riferimento anche la durata della sincronizzazione al fine di poter impostare un valore appropriato per la soglia.</span><span class="sxs-lookup"><span data-stu-id="a7c13-126">Include duration of synchronization in this baseline so that you can set an appropriate value for the threshold.</span></span>  
  
 <span data-ttu-id="a7c13-127">Se il valore soglia è appropriato ma viene superato, è necessario individuare l'area del sistema a cui è dovuto il collo di bottiglia a livello di prestazioni.</span><span class="sxs-lookup"><span data-stu-id="a7c13-127">If the threshold value is appropriate, but it is being exceeded, you must determine where the performance bottleneck is in the system.</span></span> <span data-ttu-id="a7c13-128">Per altre informazioni su come monitorare e risolvere problemi inerenti alle prestazioni di replica, vedere [Monitorare le prestazioni con Monitoraggio replica](monitor/monitor-performance-with-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="a7c13-128">For more information about how to monitor and troubleshoot replication performance, see [Monitor Performance with Replication Monitor](monitor/monitor-performance-with-replication-monitor.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7c13-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a7c13-129">See Also</span></span>  
 [<span data-ttu-id="a7c13-130">Guida di riferimento a errori ed eventi &#40;replica&#41;</span><span class="sxs-lookup"><span data-stu-id="a7c13-130">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
