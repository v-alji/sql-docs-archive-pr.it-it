---
title: Avviare e arrestare un agente di replica (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- agents [SQL Server replication], stopping
- agents [SQL Server replication], starting
ms.assetid: 97977c4a-8c7c-4a22-9480-69aa812bd1e5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b40e329e0f04e8a54a2d5a40c30aff418da2cd65
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624654"
---
# <a name="start-and-stop-a-replication-agent-sql-server-management-studio"></a><span data-ttu-id="154c9-102">Avviare e arrestare un agente di replica (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="154c9-102">Start and Stop a Replication Agent (SQL Server Management Studio)</span></span>
  <span data-ttu-id="154c9-103">Avviare e arrestare gli agenti dalla cartella **Processi** e dalla cartella **Replica** in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] e da Monitoraggio replica.</span><span class="sxs-lookup"><span data-stu-id="154c9-103">Start and stop agents from the **Jobs** folder and the **Replication** folder in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] and from Replication Monitor.</span></span> <span data-ttu-id="154c9-104">Avviare e arrestare gli agenti e i processi seguenti:</span><span class="sxs-lookup"><span data-stu-id="154c9-104">Start and stop the following agents and jobs:</span></span>  
  
-   <span data-ttu-id="154c9-105">Agente snapshot, utilizzato da tutte le pubblicazioni.</span><span class="sxs-lookup"><span data-stu-id="154c9-105">The Snapshot Agent, which is used by all publications.</span></span>  
  
-   <span data-ttu-id="154c9-106">Agente di lettura log, utilizzato da tutte le pubblicazioni transazionali.</span><span class="sxs-lookup"><span data-stu-id="154c9-106">The Log Reader Agent, which is used by all transactional publications.</span></span>  
  
-   <span data-ttu-id="154c9-107">Agente di lettura coda, utilizzato dalle pubblicazioni transazionali abilitate per le sottoscrizioni ad aggiornamento in coda.</span><span class="sxs-lookup"><span data-stu-id="154c9-107">The Queue Reader Agent, which is used by transactional publications enabled for queued updating subscriptions.</span></span>  
  
-   <span data-ttu-id="154c9-108">Agente di distribuzione, che consente di sincronizzare le sottoscrizioni con le pubblicazioni transazionali e snapshot.</span><span class="sxs-lookup"><span data-stu-id="154c9-108">The Distribution Agent, which synchronizes subscriptions to transactional and snapshot publications.</span></span>  
  
-   <span data-ttu-id="154c9-109">Agente di merge, che consente di sincronizzare le sottoscrizioni con le pubblicazioni di tipo merge.</span><span class="sxs-lookup"><span data-stu-id="154c9-109">The Merge Agent, which synchronizes subscriptions to merge publications.</span></span>  
  
-   <span data-ttu-id="154c9-110">Processi di manutenzione della replica.</span><span class="sxs-lookup"><span data-stu-id="154c9-110">Replication maintenance jobs.</span></span>  
  
 <span data-ttu-id="154c9-111">Per altre informazioni sull'avvio dell'agente di merge e dell'agente di distribuzione, vedere [Sincronizzare una sottoscrizione push](../synchronize-a-push-subscription.md) e [Sincronizzare una sottoscrizione pull](../synchronize-a-pull-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="154c9-111">For more information about starting the Merge Agent and the Distribution Agent, see [Synchronize a Push Subscription](../synchronize-a-push-subscription.md) and [Synchronize a Pull Subscription](../synchronize-a-pull-subscription.md).</span></span> <span data-ttu-id="154c9-112">Per altre informazioni sui processi di manutenzione, vedere [Eseguire processi di manutenzione della replica &#40;SQL Server Management Studio&#41;](../../../ssms/sql-server-management-studio-ssms.md).</span><span class="sxs-lookup"><span data-stu-id="154c9-112">For more information about maintenance jobs, see [Run Replication Maintenance Jobs &#40;SQL Server Management Studio&#41;](../../../ssms/sql-server-management-studio-ssms.md).</span></span>  
  
 <span data-ttu-id="154c9-113">Per informazioni sull'avvio di Monitoraggio replica, vedere [Avviare Monitoraggio replica](../monitor/start-the-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="154c9-113">For information about starting Replication Monitor, see [Start the Replication Monitor](../monitor/start-the-replication-monitor.md).</span></span>  
  
### <a name="to-start-and-stop-a-snapshot-agent-or-log-reader-agent-from-management-studio"></a><span data-ttu-id="154c9-114">Per avviare e arrestare un agente snapshot o un agente di lettura log da Management Studio</span><span class="sxs-lookup"><span data-stu-id="154c9-114">To start and stop a Snapshot Agent or Log Reader Agent from Management Studio</span></span>  
  
1.  <span data-ttu-id="154c9-115">Connettersi al server di pubblicazione in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)]e quindi espandere il nodo del server e la cartella **Replica** .</span><span class="sxs-lookup"><span data-stu-id="154c9-115">Connect to the Publisher in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)], and then expand the server node and the **Replication** folder.</span></span>  
  
2.  <span data-ttu-id="154c9-116">Espandere la cartella **Pubblicazioni locali** e quindi fare clic con il pulsante destro del mouse su una pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="154c9-116">Expand the **Local Publications** folder, and then right-click a publication.</span></span>  
  
3.  <span data-ttu-id="154c9-117">Scegliere **Visualizza stato agente snapshot** o **Visualizza stato agente di lettura log**.</span><span class="sxs-lookup"><span data-stu-id="154c9-117">Click **View Snapshot Agent Status** or **View Log Reader Agent Status**.</span></span>  
  
4.  <span data-ttu-id="154c9-118">Fare clic su **Avvia** o su **Arresta**.</span><span class="sxs-lookup"><span data-stu-id="154c9-118">Click **Start** or **Stop**.</span></span>  
  
### <a name="to-start-and-stop-a-queue-reader-agent-from-management-studio"></a><span data-ttu-id="154c9-119">Per avviare e arrestare un agente di lettura coda da Management Studio</span><span class="sxs-lookup"><span data-stu-id="154c9-119">To start and stop a Queue Reader Agent from Management Studio</span></span>  
  
1.  <span data-ttu-id="154c9-120">Connettersi al database di distribuzione in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)], quindi espandere il nodo del server.</span><span class="sxs-lookup"><span data-stu-id="154c9-120">Connect to the Distributor in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="154c9-121">Espandere la cartella **SQL Server Agent** e quindi la cartella **Processi** .</span><span class="sxs-lookup"><span data-stu-id="154c9-121">Expand the **SQL Server Agent** folder, and then expand the **Jobs** folder.</span></span>  
  
3.  <span data-ttu-id="154c9-122">Fare clic con il pulsante destro del mouse sul processo dell'agente e quindi scegliere **Avvia processo** o **Arresta processo**.</span><span class="sxs-lookup"><span data-stu-id="154c9-122">Right-click the job for the agent, and then click **Start Job** or **Stop Job**.</span></span> <span data-ttu-id="154c9-123">Il nome del processo dell'agente di lettura coda è in formato **[\<Distributor>].\<integer>** .</span><span class="sxs-lookup"><span data-stu-id="154c9-123">The name of the job for the Queue Reader Agent is in the form **[\<Distributor>].\<integer>**.</span></span>  
  
### <a name="to-start-and-stop-a-snapshot-agent-log-reader-agent-or-queue-reader-agent-from-replication-monitor"></a><span data-ttu-id="154c9-124">Per avviare e arrestare un agente snapshot, un agente di lettura log o un agente di lettura coda da Monitoraggio replica</span><span class="sxs-lookup"><span data-stu-id="154c9-124">To start and stop a Snapshot Agent, Log Reader Agent, or Queue Reader Agent from Replication Monitor</span></span>  
  
1.  <span data-ttu-id="154c9-125">Espandere un gruppo di server di pubblicazione nel riquadro sinistro, espandere un server di pubblicazione e quindi fare clic su una pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="154c9-125">Expand a Publisher group in the left pane, expand a Publisher, and then click a publication.</span></span>  
  
2.  <span data-ttu-id="154c9-126">Fare clic sulla scheda **Agenti** .</span><span class="sxs-lookup"><span data-stu-id="154c9-126">Click the **Agents** tab.</span></span>  
  
3.  <span data-ttu-id="154c9-127">Fare clic con il pulsante destro del mouse su un agente e quindi scegliere **Avvia agente** o **Arresta agente**.</span><span class="sxs-lookup"><span data-stu-id="154c9-127">Right-click an agent, and then click **Start Agent** or **Stop Agent**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="154c9-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="154c9-128">See Also</span></span>  
 <span data-ttu-id="154c9-129">[Monitoraggio della replica](../monitoring-replication.md) </span><span class="sxs-lookup"><span data-stu-id="154c9-129">[Monitoring Replication](../monitoring-replication.md) </span></span>  
 <span data-ttu-id="154c9-130">[Concetti di base relativi ai file eseguibili dell'agente di replica](../concepts/replication-agent-executables-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="154c9-130">[Replication Agent Executables Concepts](../concepts/replication-agent-executables-concepts.md) </span></span>  
 [<span data-ttu-id="154c9-131">Panoramica degli agenti di replica</span><span class="sxs-lookup"><span data-stu-id="154c9-131">Replication Agents Overview</span></span>](replication-agents-overview.md)  
  
  
