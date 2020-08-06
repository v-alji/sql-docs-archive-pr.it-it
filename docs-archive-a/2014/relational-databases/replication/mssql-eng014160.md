---
title: MSSQL_ENG014160 | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014160 error
ms.assetid: d0f3855e-d095-4a81-a5bd-9d7ad51f2c77
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3351567a31a0a0384ab8957073ab0457ef0ea7c5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624061"
---
# <a name="mssql_eng014160"></a><span data-ttu-id="f0c48-102">MSSQL_ENG014160</span><span class="sxs-lookup"><span data-stu-id="f0c48-102">MSSQL_ENG014160</span></span>
    
## <a name="message-details"></a><span data-ttu-id="f0c48-103">Dettagli messaggio</span><span class="sxs-lookup"><span data-stu-id="f0c48-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f0c48-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="f0c48-104">Product Name</span></span>|<span data-ttu-id="f0c48-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="f0c48-105">SQL Server</span></span>|  
|<span data-ttu-id="f0c48-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="f0c48-106">Event ID</span></span>|<span data-ttu-id="f0c48-107">14160</span><span class="sxs-lookup"><span data-stu-id="f0c48-107">14160</span></span>|  
|<span data-ttu-id="f0c48-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="f0c48-108">Event Source</span></span>|<span data-ttu-id="f0c48-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="f0c48-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="f0c48-110">Componente</span><span class="sxs-lookup"><span data-stu-id="f0c48-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="f0c48-111">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="f0c48-111">Symbolic Name</span></span>||  
|<span data-ttu-id="f0c48-112">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="f0c48-112">Message Text</span></span>|<span data-ttu-id="f0c48-113">È stata impostata la soglia [%s:%s] per la pubblicazione [%s].</span><span class="sxs-lookup"><span data-stu-id="f0c48-113">The threshold [%s:%s] for the publication [%s] has been set.</span></span> <span data-ttu-id="f0c48-114">Una o più sottoscrizioni della pubblicazione sono scadute.</span><span class="sxs-lookup"><span data-stu-id="f0c48-114">One or more subscriptions to this publication have expired.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f0c48-115">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="f0c48-115">Explanation</span></span>  
 <span data-ttu-id="f0c48-116">La replica consente di attivare avvisi per numerose condizioni,</span><span class="sxs-lookup"><span data-stu-id="f0c48-116">Replication lets you enable warnings for several conditions.</span></span> <span data-ttu-id="f0c48-117">tra cui la scadenza imminente della sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="f0c48-117">This includes imminent subscription expiration.</span></span> <span data-ttu-id="f0c48-118">Le sottoscrizioni possono scadere se non vengono sincronizzate entro il *periodo di memorizzazione*specificato.</span><span class="sxs-lookup"><span data-stu-id="f0c48-118">Subscriptions can expire if they are not synchronized within a specified *retention period*.</span></span> <span data-ttu-id="f0c48-119">Per altre informazioni, vedere [Subscription Expiration and Deactivation](subscription-expiration-and-deactivation.md).</span><span class="sxs-lookup"><span data-stu-id="f0c48-119">For more information, see [Subscription Expiration and Deactivation](subscription-expiration-and-deactivation.md).</span></span>  
  
 <span data-ttu-id="f0c48-120">Quando si attiva un avviso utilizzando Monitoraggio replica o [sp_replmonitorchangepublicationthreshold](/sql/relational-databases/system-stored-procedures/sp-replmonitorchangepublicationthreshold-transact-sql), viene specificata una soglia che determina quando è generato l'avviso.</span><span class="sxs-lookup"><span data-stu-id="f0c48-120">When you enable a warning by using Replication Monitor or [sp_replmonitorchangepublicationthreshold](/sql/relational-databases/system-stored-procedures/sp-replmonitorchangepublicationthreshold-transact-sql), you specify a threshold that determines when a warning is triggered.</span></span> <span data-ttu-id="f0c48-121">Quando tale soglia viene raggiunta o superata, viene visualizzato un avviso in Monitoraggio replica e viene registrato un evento nel registro eventi di Windows.</span><span class="sxs-lookup"><span data-stu-id="f0c48-121">When that threshold is met or exceeded, a warning is displayed in Replication Monitor, and an event is written to the Windows event log.</span></span> <span data-ttu-id="f0c48-122">Il raggiungimento di una soglia può inoltre generare un avviso SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="f0c48-122">Reaching a threshold can also trigger a SQL Server Agent alert.</span></span> <span data-ttu-id="f0c48-123">Per altre informazioni, vedere [Impostare valori di soglia e avvisi in Monitoraggio replica](monitor/set-thresholds-and-warnings-in-replication-monitor.md) e [Monitorare la replica a livello di programmazione](monitoring-replication.md).</span><span class="sxs-lookup"><span data-stu-id="f0c48-123">For more information, see [Set Thresholds and Warnings in Replication Monitor](monitor/set-thresholds-and-warnings-in-replication-monitor.md) and [Programmatically Monitor Replication](monitoring-replication.md).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f0c48-124">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="f0c48-124">User Action</span></span>  
 <span data-ttu-id="f0c48-125">La risoluzione del problema dipende dal motivo per il quale è stato generato l'avviso:</span><span class="sxs-lookup"><span data-stu-id="f0c48-125">The resolution for this issue depends on the reason the warning was raised:</span></span>  
  
-   <span data-ttu-id="f0c48-126">Se la soglia è stata superata ma la sottoscrizione non è ancora scaduta, sincronizzare la sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="f0c48-126">If the threshold has been exceeded, but the subscription has not yet expired, synchronize the subscription.</span></span> <span data-ttu-id="f0c48-127">Per altre informazioni, vedere [Sincronizzare i dati](synchronize-data.md).</span><span class="sxs-lookup"><span data-stu-id="f0c48-127">For more information, see [Synchronize Data](synchronize-data.md).</span></span>  
  
-   <span data-ttu-id="f0c48-128">È possibile che la sottoscrizione scada se l'agente è stato eseguito ma la replica delle modifiche non è stata completata correttamente.</span><span class="sxs-lookup"><span data-stu-id="f0c48-128">If the agent has been running, but has not been replicating changes properly, this can cause the subscription to expire.</span></span> <span data-ttu-id="f0c48-129">Per la replica transazionale verificare che l'agente di distribuzione e l'agente di lettura log siano in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="f0c48-129">For transactional replication, make sure that the Distribution Agent and Log Reader Agent are running.</span></span> <span data-ttu-id="f0c48-130">Per la replica di tipo merge verificare che l'agente di merge sia in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="f0c48-130">For merge replication, make sure the Merge Agent is running.</span></span> <span data-ttu-id="f0c48-131">Per altre informazioni su come avviare questi agenti, vedere [Avviare e arrestare un agente di replica &#40;SQL Server Management Studio&#41;](agents/start-and-stop-a-replication-agent-sql-server-management-studio.md) e [Concetti di base relativi ai file eseguibili dell'agente di replica](concepts/replication-agent-executables-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="f0c48-131">For information about how to start these agents, see [Start and Stop a Replication Agent &#40;SQL Server Management Studio&#41;](agents/start-and-stop-a-replication-agent-sql-server-management-studio.md) and [Replication Agent Executables Concepts](concepts/replication-agent-executables-concepts.md).</span></span>  
  
-   <span data-ttu-id="f0c48-132">Se la sottoscrizione è scaduta, sarà necessario reinizializzarla oppure eliminarla e ricrearla, a seconda del tipo di sottoscrizione e da quanto tempo è scaduta.</span><span class="sxs-lookup"><span data-stu-id="f0c48-132">If the subscription has expired, it must either be reinitialized or dropped and re-created, depending on the type of subscription and how long it has been expired.</span></span> <span data-ttu-id="f0c48-133">Per altre informazioni, vedere [Subscription Expiration and Deactivation](subscription-expiration-and-deactivation.md).</span><span class="sxs-lookup"><span data-stu-id="f0c48-133">For more information, see [Subscription Expiration and Deactivation](subscription-expiration-and-deactivation.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0c48-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f0c48-134">See Also</span></span>  
 [<span data-ttu-id="f0c48-135">Guida di riferimento a errori ed eventi &#40;replica&#41;</span><span class="sxs-lookup"><span data-stu-id="f0c48-135">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
