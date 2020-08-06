---
title: MSSQL_ENG014150 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014150 error
ms.assetid: c3dd3109-abf3-4b38-a4e9-ef48d0235656
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4c926d05be9613ff559f119484fa5e238d71d861
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624068"
---
# <a name="mssql_eng014150"></a><span data-ttu-id="d4ee7-102">MSSQL_ENG014150</span><span class="sxs-lookup"><span data-stu-id="d4ee7-102">MSSQL_ENG014150</span></span>
    
## <a name="message-details"></a><span data-ttu-id="d4ee7-103">Dettagli messaggio</span><span class="sxs-lookup"><span data-stu-id="d4ee7-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d4ee7-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="d4ee7-104">Product Name</span></span>|<span data-ttu-id="d4ee7-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="d4ee7-105">SQL Server</span></span>|  
|<span data-ttu-id="d4ee7-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="d4ee7-106">Event ID</span></span>|<span data-ttu-id="d4ee7-107">14150</span><span class="sxs-lookup"><span data-stu-id="d4ee7-107">14150</span></span>|  
|<span data-ttu-id="d4ee7-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="d4ee7-108">Event Source</span></span>|<span data-ttu-id="d4ee7-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="d4ee7-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="d4ee7-110">Componente</span><span class="sxs-lookup"><span data-stu-id="d4ee7-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="d4ee7-111">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="d4ee7-111">Symbolic Name</span></span>||  
|<span data-ttu-id="d4ee7-112">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="d4ee7-112">Message Text</span></span>|<span data-ttu-id="d4ee7-113">Replica-%s: l'esecuzione dell'agente %s è riuscita.</span><span class="sxs-lookup"><span data-stu-id="d4ee7-113">Replication-%s: agent %s succeeded.</span></span> <span data-ttu-id="d4ee7-114">%s</span><span class="sxs-lookup"><span data-stu-id="d4ee7-114">%s</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d4ee7-115">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="d4ee7-115">Explanation</span></span>  
 <span data-ttu-id="d4ee7-116">Il messaggio indica che l'esecuzione di un agente di replica è stata completata correttamente.</span><span class="sxs-lookup"><span data-stu-id="d4ee7-116">This message indicates that a replication agent has successfully finished running.</span></span> <span data-ttu-id="d4ee7-117">Nella replica vengono utilizzati gli agenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="d4ee7-117">Replication uses the following agents:</span></span>  
  
-   <span data-ttu-id="d4ee7-118">Agente snapshot.</span><span class="sxs-lookup"><span data-stu-id="d4ee7-118">The Snapshot Agent.</span></span> <span data-ttu-id="d4ee7-119">Questo agente viene utilizzato da tutte le pubblicazioni.</span><span class="sxs-lookup"><span data-stu-id="d4ee7-119">This agent is used by all publications.</span></span>  
  
-   <span data-ttu-id="d4ee7-120">Agente di lettura log.</span><span class="sxs-lookup"><span data-stu-id="d4ee7-120">The Log Reader Agent.</span></span> <span data-ttu-id="d4ee7-121">Questo agente viene utilizzato da tutte le pubblicazioni transazionali.</span><span class="sxs-lookup"><span data-stu-id="d4ee7-121">This agent is used by all transactional publications.</span></span>  
  
-   <span data-ttu-id="d4ee7-122">Agente di lettura coda.</span><span class="sxs-lookup"><span data-stu-id="d4ee7-122">The Queue Reader Agent.</span></span> <span data-ttu-id="d4ee7-123">Questo agente viene utilizzato dalle pubblicazioni transazionali abilitate per le sottoscrizioni ad aggiornamento in coda.</span><span class="sxs-lookup"><span data-stu-id="d4ee7-123">This agent is used by transactional publications enabled for queued updating subscriptions.</span></span>  
  
-   <span data-ttu-id="d4ee7-124">Agente di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="d4ee7-124">The Distribution Agent.</span></span> <span data-ttu-id="d4ee7-125">Questo agente consente di sincronizzare le sottoscrizioni con le pubblicazioni transazionali e snapshot.</span><span class="sxs-lookup"><span data-stu-id="d4ee7-125">This agent synchronizes subscriptions to transactional and snapshot publications.</span></span>  
  
-   <span data-ttu-id="d4ee7-126">Agente di merge.</span><span class="sxs-lookup"><span data-stu-id="d4ee7-126">The Merge Agent.</span></span> <span data-ttu-id="d4ee7-127">Questo agente consente di sincronizzare le sottoscrizioni con le pubblicazioni di tipo merge.</span><span class="sxs-lookup"><span data-stu-id="d4ee7-127">This agent synchronizes subscriptions to merge publications.</span></span>  
  
-   <span data-ttu-id="d4ee7-128">Processi di manutenzione della replica.</span><span class="sxs-lookup"><span data-stu-id="d4ee7-128">Replication maintenance jobs.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d4ee7-129">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="d4ee7-129">User Action</span></span>  
 <span data-ttu-id="d4ee7-130">L'agente di lettura log, l'agente di lettura coda e l'agente di distribuzione vengono in genere eseguiti in modo continuo, mentre altri agenti vengono eseguiti su richiesta o in base a una pianificazione.</span><span class="sxs-lookup"><span data-stu-id="d4ee7-130">The Log Reader Agent, Queue Reader Agent, and Distribution Agent typically run continuously, whereas the other agents typically run on demand or on a schedule.</span></span> <span data-ttu-id="d4ee7-131">Se il completamento dell'esecuzione di un agente non è previsto, verificare lo stato dell'agente.</span><span class="sxs-lookup"><span data-stu-id="d4ee7-131">If you do not expect an agent to have completed a run, check the status of the agent.</span></span> <span data-ttu-id="d4ee7-132">Per altre informazioni, vedere [Monitor Replication Agents](agents/replication-agents-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d4ee7-132">For more information, see [Monitor Replication Agents](agents/replication-agents-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4ee7-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d4ee7-133">See Also</span></span>  
 <span data-ttu-id="d4ee7-134">[Amministrazione dell'agente di replica](agents/replication-agent-administration.md) </span><span class="sxs-lookup"><span data-stu-id="d4ee7-134">[Replication Agent Administration](agents/replication-agent-administration.md) </span></span>  
 <span data-ttu-id="d4ee7-135">[Guida di riferimento a errori ed eventi &#40;replica&#41;](errors-and-events-reference-replication.md) </span><span class="sxs-lookup"><span data-stu-id="d4ee7-135">[Errors and Events Reference &#40;Replication&#41;](errors-and-events-reference-replication.md) </span></span>  
 <span data-ttu-id="d4ee7-136">[Replication Distribution Agent](agents/replication-distribution-agent.md) </span><span class="sxs-lookup"><span data-stu-id="d4ee7-136">[Replication Distribution Agent](agents/replication-distribution-agent.md) </span></span>  
 <span data-ttu-id="d4ee7-137">[Replication Log Reader Agent](agents/replication-log-reader-agent.md) </span><span class="sxs-lookup"><span data-stu-id="d4ee7-137">[Replication Log Reader Agent](agents/replication-log-reader-agent.md) </span></span>  
 <span data-ttu-id="d4ee7-138">[Replication Merge Agent](agents/replication-merge-agent.md) </span><span class="sxs-lookup"><span data-stu-id="d4ee7-138">[Replication Merge Agent](agents/replication-merge-agent.md) </span></span>  
 <span data-ttu-id="d4ee7-139">[Agente di lettura coda repliche](agents/replication-queue-reader-agent.md) </span><span class="sxs-lookup"><span data-stu-id="d4ee7-139">[Replication Queue Reader Agent](agents/replication-queue-reader-agent.md) </span></span>  
 [<span data-ttu-id="d4ee7-140">Replication Snapshot Agent</span><span class="sxs-lookup"><span data-stu-id="d4ee7-140">Replication Snapshot Agent</span></span>](agents/replication-snapshot-agent.md)  
  
  
