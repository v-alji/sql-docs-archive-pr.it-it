---
title: Monitorare gli agenti di replica | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- monitoring performance [SQL Server replication], agents
- Log Reader Agent, monitoring
- Replication Monitor, agents
- Merge Agent, monitoring
- Queue Reader Agent, monitoring
- Snapshot Agent, monitoring
- agents [SQL Server replication], monitoring
- Distribution Agent, monitoring
ms.assetid: d06ed24f-82d7-4b9e-9e40-cc9780476a71
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: baa22ef9e9f7c4621f76838e82c309d17f1e12a6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626643"
---
# <a name="monitor-replication-agents"></a><span data-ttu-id="455fc-102">Monitoraggio degli agenti di replica</span><span class="sxs-lookup"><span data-stu-id="455fc-102">Monitor Replication Agents</span></span>
  <span data-ttu-id="455fc-103">Monitoraggio replica di [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] offre una visualizzazione a livello di sistema dell'attività di replica e semplifica l'individuazione di informazioni su un agente specifico.</span><span class="sxs-lookup"><span data-stu-id="455fc-103">[!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Replication Monitor provides a systemic view of replication activity, but also makes it straightforward to find information on a specific agent.</span></span> <span data-ttu-id="455fc-104">Nell'elenco seguente vengono inclusi tutti gli agenti, le relative schede di Monitoraggio replica e un collegamento all'argomento in cui si spiega come accedere a queste schede:</span><span class="sxs-lookup"><span data-stu-id="455fc-104">The following list includes each agent, the tabs in the Replication Monitor on which it can be found, and a link to a topic that explains how to access these tabs:</span></span>  
  
-   <span data-ttu-id="455fc-105">Gli agenti seguenti sono associati alle pubblicazioni in Monitoraggio replica:</span><span class="sxs-lookup"><span data-stu-id="455fc-105">The following agents are associated with publications in Replication Monitor:</span></span>  
  
    -   <span data-ttu-id="455fc-106">agente snapshot</span><span class="sxs-lookup"><span data-stu-id="455fc-106">Snapshot Agent</span></span>  
  
    -   <span data-ttu-id="455fc-107">Agente di lettura log</span><span class="sxs-lookup"><span data-stu-id="455fc-107">Log Reader Agent</span></span>  
  
    -   <span data-ttu-id="455fc-108">Agente di lettura coda</span><span class="sxs-lookup"><span data-stu-id="455fc-108">Queue Reader Agent</span></span>  
  
     <span data-ttu-id="455fc-109">Accedere a informazioni e attività associate a questi agenti tramite le schede seguenti: **Agenti** (disponibile per ogni server di pubblicazione e pubblicazione) e **Avvisi** (disponibile per ogni pubblicazione).</span><span class="sxs-lookup"><span data-stu-id="455fc-109">Access information and tasks associated with these agents through the following tabs: **Agents** (available for each Publisher and publication) and **Warnings** (available for each publication).</span></span> <span data-ttu-id="455fc-110">Per altre informazioni, vedere [Visualizzare le informazioni ed eseguire attività usando Monitoraggio replica](view-information-and-perform-tasks-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="455fc-110">For more information, see [View Information and Perform Tasks using Replication Monitor](view-information-and-perform-tasks-replication-monitor.md).</span></span>  
  
-   <span data-ttu-id="455fc-111">Gli agenti seguenti sono associati alle sottoscrizioni in Monitoraggio replica:</span><span class="sxs-lookup"><span data-stu-id="455fc-111">The following agents are associated with subscriptions in Replication Monitor:</span></span>  
  
    -   <span data-ttu-id="455fc-112">Agente di distribuzione</span><span class="sxs-lookup"><span data-stu-id="455fc-112">Distribution Agent</span></span>  
  
    -   <span data-ttu-id="455fc-113">Agente di merge</span><span class="sxs-lookup"><span data-stu-id="455fc-113">Merge Agent</span></span>  
  
     <span data-ttu-id="455fc-114">Accedere a informazioni e attività associate a questi agenti tramite le schede seguenti: **Elenco verifica sottoscrizioni** (disponibile per ogni server di pubblicazione) o **Tutte le sottoscrizioni** (disponibile per ogni pubblicazione).</span><span class="sxs-lookup"><span data-stu-id="455fc-114">Access information and tasks associated with these agents through the following tabs: **Subscription Watch List** (available for each Publisher) or the **All Subscriptions** tab (available for each publication).</span></span> <span data-ttu-id="455fc-115">Per altre informazioni, vedere [Visualizzare le informazioni ed eseguire attività usando Monitoraggio replica](view-information-and-perform-tasks-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="455fc-115">For more information, see [View Information and Perform Tasks using Replication Monitor](view-information-and-perform-tasks-replication-monitor.md).</span></span>  
  
## <a name="using-sql-server-management-studio-to-monitor-replication-agents"></a><span data-ttu-id="455fc-116">Utilizzo di SQL Server Management Studio per il monitoraggio degli agenti di replica</span><span class="sxs-lookup"><span data-stu-id="455fc-116">Using SQL Server Management Studio to Monitor Replication Agents</span></span>  
 <span data-ttu-id="455fc-117">In [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] sono disponibili le finestre di dialogo seguenti per il monitoraggio degli agenti di replica:</span><span class="sxs-lookup"><span data-stu-id="455fc-117">[!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] provides the following dialog boxes for monitoring replication agents:</span></span>  
  
-   <span data-ttu-id="455fc-118">**Visualizza stato agente snapshot** (per tutte le pubblicazioni)</span><span class="sxs-lookup"><span data-stu-id="455fc-118">**View Snapshot Agent Status** (for all publications)</span></span>  
  
-   <span data-ttu-id="455fc-119">**Visualizza stato agente di lettura log** (per tutte le pubblicazioni transazionali)</span><span class="sxs-lookup"><span data-stu-id="455fc-119">**View Log Reader Agent Status** (for all transactional publications)</span></span>  
  
-   <span data-ttu-id="455fc-120">**Visualizza stato sincronizzazione** (per tutte le sottoscrizioni: questa finestra di dialogo consente l'accesso all'agente di distribuzione e all'agente di merge)</span><span class="sxs-lookup"><span data-stu-id="455fc-120">**View Synchronization Status** (for all subscriptions; this dialog box allows access to the Distribution Agent and the Merge Agent)</span></span>  
  
 <span data-ttu-id="455fc-121">Monitoraggio replica offre informazioni aggiuntive su ogni agente e consente di monitorare l'agente di lettura coda, se utilizzato.</span><span class="sxs-lookup"><span data-stu-id="455fc-121">Replication Monitor provides additional information about each agent and provides monitoring for the Queue Reader Agent, if it is used.</span></span> <span data-ttu-id="455fc-122">Per altre informazioni, vedere [Visualizzare le informazioni ed eseguire attività usando Monitoraggio replica](view-information-and-perform-tasks-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="455fc-122">For more information, see [View Information and Perform Tasks using Replication Monitor](view-information-and-perform-tasks-replication-monitor.md).</span></span>  
  
#### <a name="to-monitor-the-snapshot-agent-and-log-reader-agent"></a><span data-ttu-id="455fc-123">Per monitorare l'agente snapshot e l'agente di lettura log</span><span class="sxs-lookup"><span data-stu-id="455fc-123">To monitor the Snapshot Agent and Log Reader Agent</span></span>  
  
1.  <span data-ttu-id="455fc-124">Connettersi al server di pubblicazione in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)]e quindi espandere il nodo del server.</span><span class="sxs-lookup"><span data-stu-id="455fc-124">Connect to the Publisher in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="455fc-125">Espandere la cartella **Replica** e quindi la cartella **Pubblicazioni locali** .</span><span class="sxs-lookup"><span data-stu-id="455fc-125">Expand the **Replication** folder, and then expand the **Local Publications** folder.</span></span>  
  
3.  <span data-ttu-id="455fc-126">Fare clic con il pulsante destro del mouse su una pubblicazione e quindi scegliere **Visualizza stato agente di lettura log** o **Visualizza stato agente snapshot**.</span><span class="sxs-lookup"><span data-stu-id="455fc-126">Right-click a publication, and then click **View Log Reader Agent Status** or **View Snapshot Agent Status**.</span></span>  
  
4.  <span data-ttu-id="455fc-127">Nella finestra di dialogo **Visualizza stato agente di lettura log** o **Visualizza stato agente snapshot** :</span><span class="sxs-lookup"><span data-stu-id="455fc-127">In the **View Log Reader Agent Status** or **View Snapshot Agent Status** dialog box:</span></span>  
  
    -   <span data-ttu-id="455fc-128">Visualizzare lo stato dell'agente.</span><span class="sxs-lookup"><span data-stu-id="455fc-128">View agent status.</span></span>  
  
    -   <span data-ttu-id="455fc-129">Avviare o arrestare l'agente se necessario.</span><span class="sxs-lookup"><span data-stu-id="455fc-129">Start or stop the agent if necessary.</span></span>  
  
    -   <span data-ttu-id="455fc-130">Fare clic su **Esegui monitoraggio** per avviare **Monitoraggio replica**.</span><span class="sxs-lookup"><span data-stu-id="455fc-130">Click **Monitor** to launch **Replication Monitor**.</span></span>  
  
5.  <span data-ttu-id="455fc-131">Fare clic su **Close**.</span><span class="sxs-lookup"><span data-stu-id="455fc-131">Click **Close**.</span></span>  
  
#### <a name="to-monitor-the-distribution-agent-and-merge-agent-from-the-publisher"></a><span data-ttu-id="455fc-132">Per monitorare l'agente di distribuzione e l'agente di merge (dal server di pubblicazione)</span><span class="sxs-lookup"><span data-stu-id="455fc-132">To monitor the Distribution Agent and Merge Agent (from the Publisher)</span></span>  
  
1.  <span data-ttu-id="455fc-133">Connettersi al server di pubblicazione in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)]e quindi espandere il nodo del server.</span><span class="sxs-lookup"><span data-stu-id="455fc-133">Connect to the Publisher in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="455fc-134">Espandere la cartella **Replica** e quindi la cartella **Pubblicazioni locali** .</span><span class="sxs-lookup"><span data-stu-id="455fc-134">Expand the **Replication** folder, and then expand the **Local Publications** folder.</span></span>  
  
3.  <span data-ttu-id="455fc-135">Espandere la pubblicazione della sottoscrizione da monitorare.</span><span class="sxs-lookup"><span data-stu-id="455fc-135">Expand the publication for the subscription you want to monitor.</span></span>  
  
4.  <span data-ttu-id="455fc-136">Fare clic con il pulsante destro del mouse sulla sottoscrizione e quindi scegliere **Visualizza stato sincronizzazione**.</span><span class="sxs-lookup"><span data-stu-id="455fc-136">Right-click the subscription, and then click **View Synchronization Status**.</span></span>  
  
5.  <span data-ttu-id="455fc-137">Nella finestra di dialogo **Visualizza stato sincronizzazione** :</span><span class="sxs-lookup"><span data-stu-id="455fc-137">In the **View Synchronization Status** dialog box:</span></span>  
  
    -   <span data-ttu-id="455fc-138">Visualizzare lo stato dell'agente.</span><span class="sxs-lookup"><span data-stu-id="455fc-138">View agent status.</span></span>  
  
    -   <span data-ttu-id="455fc-139">Avviare o arrestare l'agente se necessario.</span><span class="sxs-lookup"><span data-stu-id="455fc-139">Start or stop the agent if necessary.</span></span>  
  
    -   <span data-ttu-id="455fc-140">Per le sottoscrizioni push fare clic su **Esegui monitoraggio** per avviare **Monitoraggio replica**.</span><span class="sxs-lookup"><span data-stu-id="455fc-140">For push subscriptions, click **Monitor** to launch **Replication Monitor**.</span></span>  
  
    -   <span data-ttu-id="455fc-141">Per le sottoscrizioni pull fare clic su **Visualizza cronologia processi** per avviare **Visualizzatore file log**e visualizzare l'output del log dell'agente.</span><span class="sxs-lookup"><span data-stu-id="455fc-141">For pull subscriptions, click **View Job History** to launch the **Log File Viewer**, which displays output from the agent log.</span></span>  
  
6.  <span data-ttu-id="455fc-142">Fare clic su **Close**.</span><span class="sxs-lookup"><span data-stu-id="455fc-142">Click **Close**.</span></span>  
  
#### <a name="to-monitor-the-distribution-agent-and-merge-agent-from-the-subscriber"></a><span data-ttu-id="455fc-143">Per monitorare l'agente di distribuzione e l'agente di merge (dal Sottoscrittore)</span><span class="sxs-lookup"><span data-stu-id="455fc-143">To monitor the Distribution Agent and Merge Agent (from the Subscriber)</span></span>  
  
1.  <span data-ttu-id="455fc-144">Connettersi al Sottoscrittore in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)]e quindi espandere il nodo del server.</span><span class="sxs-lookup"><span data-stu-id="455fc-144">Connect to the Subscriber in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="455fc-145">Espandere la cartella **Replica** e quindi la cartella **Sottoscrizioni locali** .</span><span class="sxs-lookup"><span data-stu-id="455fc-145">Expand the **Replication** folder, and then expand the **Local Subscriptions** folder.</span></span>  
  
3.  <span data-ttu-id="455fc-146">Fare clic con il pulsante destro del mouse sulla sottoscrizione che si desidera monitorare e quindi scegliere **Visualizza stato sincronizzazione**.</span><span class="sxs-lookup"><span data-stu-id="455fc-146">Right-click the subscription you want to monitor, and then click **View Synchronization Status**.</span></span>  
  
4.  <span data-ttu-id="455fc-147">Nella finestra di dialogo **Visualizza stato sincronizzazione** :</span><span class="sxs-lookup"><span data-stu-id="455fc-147">In the **View Synchronization Status** dialog box:</span></span>  
  
    -   <span data-ttu-id="455fc-148">Visualizzare lo stato dell'agente.</span><span class="sxs-lookup"><span data-stu-id="455fc-148">View agent status.</span></span>  
  
    -   <span data-ttu-id="455fc-149">Avviare o arrestare l'agente se necessario.</span><span class="sxs-lookup"><span data-stu-id="455fc-149">Start or stop the agent if necessary.</span></span>  
  
    -   <span data-ttu-id="455fc-150">Fare clic su **Visualizza cronologia processi** per avviare **Visualizzatore file log**e visualizzare l'output del log dell'agente.</span><span class="sxs-lookup"><span data-stu-id="455fc-150">Click **View Job History** to launch the **Log File Viewer**, which displays output from the agent log.</span></span>  
  
5.  <span data-ttu-id="455fc-151">Fare clic su **Close**.</span><span class="sxs-lookup"><span data-stu-id="455fc-151">Click **Close**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="455fc-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="455fc-152">See Also</span></span>  
 <span data-ttu-id="455fc-153">[Monitoraggio della replica](../monitoring-replication.md) </span><span class="sxs-lookup"><span data-stu-id="455fc-153">[Monitoring Replication](../monitoring-replication.md) </span></span>  
 [<span data-ttu-id="455fc-154">Panoramica degli agenti di replica</span><span class="sxs-lookup"><span data-stu-id="455fc-154">Replication Agents Overview</span></span>](../agents/replication-agents-overview.md)  
  
  
