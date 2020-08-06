---
title: Visualizzare e modificare i parametri del prompt dei comandi dell'agente di replica (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- agents [SQL Server replication], command prompt parameters
ms.assetid: 45f2e781-c21d-4b44-8992-89f60fb3d022
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 752f674c21bb66c7b64e399e30e4917512431195
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624653"
---
# <a name="view-and-modify-replication-agent-command-prompt-parameters-sql-server-management-studio"></a><span data-ttu-id="79943-102">Visualizzare e modificare i parametri del prompt dei comandi dell'agente di replica (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="79943-102">View and Modify Replication Agent Command Prompt Parameters (SQL Server Management Studio)</span></span>
  <span data-ttu-id="79943-103">Gli agenti di replica sono file eseguibili che accettano parametri della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="79943-103">Replication agents are executables that accept command line parameters.</span></span> <span data-ttu-id="79943-104">Per impostazione predefinita, gli agenti vengono eseguiti in passaggi di processi di [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]Agent, quindi questi parametri possono essere visualizzati e modificati usando la finestra di dialogo **Proprietà processo - \<Job>** .</span><span class="sxs-lookup"><span data-stu-id="79943-104">By default, agents run under [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent job steps, so these parameters can be viewed and modified using the **Job Properties - \<Job>** dialog box.</span></span> <span data-ttu-id="79943-105">accessibile dalla cartella **Processi** di [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] e dalla scheda **Agenti** di Monitoraggio replica.</span><span class="sxs-lookup"><span data-stu-id="79943-105">This dialog box is available from the **Jobs** folder in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] and from the **Agents** tab in Replication Monitor.</span></span> <span data-ttu-id="79943-106">Per informazioni sull'avvio di Monitoraggio replica, vedere [Avviare Monitoraggio replica](../monitor/start-the-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="79943-106">For information about starting Replication Monitor, see [Start the Replication Monitor](../monitor/start-the-replication-monitor.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="79943-107">Le modifiche apportate al parametro dell'agente verranno applicate al successivo avvio dell'agente.</span><span class="sxs-lookup"><span data-stu-id="79943-107">Agent parameter changes take effect the next time the agent is started.</span></span> <span data-ttu-id="79943-108">Se l'agente viene eseguito in modo continuo, è necessario arrestarlo e riavviarlo.</span><span class="sxs-lookup"><span data-stu-id="79943-108">If the agent runs continuously, you must stop and restart the agent.</span></span>  
  
 <span data-ttu-id="79943-109">Sebbene i parametri possano essere modificati direttamente, in genere li si modifica tramite un profilo agente.</span><span class="sxs-lookup"><span data-stu-id="79943-109">Although parameters can be modified directly, it is more common to modify them through an agent profile.</span></span> <span data-ttu-id="79943-110">Per altre informazioni, vedere [Replication Agent Profiles](replication-agent-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="79943-110">For more information, see [Replication Agent Profiles](replication-agent-profiles.md).</span></span>  
  
 <span data-ttu-id="79943-111">Se si accede ai processi agente dalla cartella **Processi** , utilizzare la tabella seguente per determinare il nome del processo agente e i parametri disponibili per ogni agente.</span><span class="sxs-lookup"><span data-stu-id="79943-111">If you access agent jobs from the **Jobs** folder, use the following table to determine the agent job name and the parameters available for each agent.</span></span>  
  
|<span data-ttu-id="79943-112">Agente</span><span class="sxs-lookup"><span data-stu-id="79943-112">Agent</span></span>|<span data-ttu-id="79943-113">Nome processo</span><span class="sxs-lookup"><span data-stu-id="79943-113">Job name</span></span>|<span data-ttu-id="79943-114">Per un elenco dei parametri, vedere...</span><span class="sxs-lookup"><span data-stu-id="79943-114">For a list of parameters, see...</span></span>|  
|-----------|--------------|------------------------------------|  
|<span data-ttu-id="79943-115">agente snapshot</span><span class="sxs-lookup"><span data-stu-id="79943-115">Snapshot Agent</span></span>|**\<Publisher>-\<PublicationDatabase>-\<Publication>-\<integer>**|[<span data-ttu-id="79943-116">Replication Snapshot Agent</span><span class="sxs-lookup"><span data-stu-id="79943-116">Replication Snapshot Agent</span></span>](replication-snapshot-agent.md)|  
|<span data-ttu-id="79943-117">Agente snapshot per una partizione di una pubblicazione di tipo merge</span><span class="sxs-lookup"><span data-stu-id="79943-117">Snapshot Agent for a merge publication partition</span></span>|<span data-ttu-id="79943-118">**Dyn_\<Publisher>-\<PublicationDatabase>-\<Publication>-\<GUID>**</span><span class="sxs-lookup"><span data-stu-id="79943-118">**Dyn_\<Publisher>-\<PublicationDatabase>-\<Publication>-\<GUID>**</span></span>|[<span data-ttu-id="79943-119">Replication Snapshot Agent</span><span class="sxs-lookup"><span data-stu-id="79943-119">Replication Snapshot Agent</span></span>](replication-snapshot-agent.md)|  
|<span data-ttu-id="79943-120">Agente di lettura log</span><span class="sxs-lookup"><span data-stu-id="79943-120">Log Reader Agent</span></span>|**\<Publisher>-\<PublicationDatabase>-\<integer>**|[<span data-ttu-id="79943-121">Agente lettura log repliche</span><span class="sxs-lookup"><span data-stu-id="79943-121">Replication Log Reader Agent</span></span>](replication-log-reader-agent.md)|  
|<span data-ttu-id="79943-122">Agente di merge per le sottoscrizioni pull</span><span class="sxs-lookup"><span data-stu-id="79943-122">Merge Agent for pull subscriptions</span></span>|**\<Publisher>-\<PublicationDatabase>-\<Publication>-\<Subscriber>-\<SubscriptionDatabase>-\<integer>**|[<span data-ttu-id="79943-123">Replication Merge Agent</span><span class="sxs-lookup"><span data-stu-id="79943-123">Replication Merge Agent</span></span>](replication-merge-agent.md)|  
|<span data-ttu-id="79943-124">Agente di merge per le sottoscrizioni push</span><span class="sxs-lookup"><span data-stu-id="79943-124">Merge Agent for push subscriptions</span></span>|**\<Publisher>-\<PublicationDatabase>-\<Publication>-\<Subscriber>-\<integer>**|[<span data-ttu-id="79943-125">Replication Merge Agent</span><span class="sxs-lookup"><span data-stu-id="79943-125">Replication Merge Agent</span></span>](replication-merge-agent.md)|  
|<span data-ttu-id="79943-126">Agente di distribuzione per le sottoscrizioni push</span><span class="sxs-lookup"><span data-stu-id="79943-126">Distribution Agent for push subscriptions</span></span>|<span data-ttu-id="79943-127">**\<Publisher>-\<PublicationDatabase>-\<Publication>-\<Subscriber>-\<integer>** <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="79943-127">**\<Publisher>-\<PublicationDatabase>-\<Publication>-\<Subscriber>-\<integer>** <sup>1</sup></span></span>|[<span data-ttu-id="79943-128">Replication Distribution Agent</span><span class="sxs-lookup"><span data-stu-id="79943-128">Replication Distribution Agent</span></span>](replication-distribution-agent.md)|  
|<span data-ttu-id="79943-129">Agente di distribuzione per le sottoscrizioni pull</span><span class="sxs-lookup"><span data-stu-id="79943-129">Distribution Agent for pull subscriptions</span></span>|<span data-ttu-id="79943-130">**\<Publisher>-\<PublicationDatabase>-\<Publication>-\<Subscriber>-\<SubscriptionDatabase>-\<GUID>** <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="79943-130">**\<Publisher>-\<PublicationDatabase>-\<Publication>-\<Subscriber>-\<SubscriptionDatabase>-\<GUID>** <sup>2</sup></span></span>|[<span data-ttu-id="79943-131">Replication Distribution Agent</span><span class="sxs-lookup"><span data-stu-id="79943-131">Replication Distribution Agent</span></span>](replication-distribution-agent.md)|  
|<span data-ttu-id="79943-132">Agente di distribuzione per le sottoscrizioni push di Sottoscrittori non SQL Server</span><span class="sxs-lookup"><span data-stu-id="79943-132">Distribution Agent for push subscriptions to non-SQL Server Subscribers</span></span>|**\<Publisher>-\<PublicationDatabase>-\<Publication>-\<Subscriber>-\<integer>**|[<span data-ttu-id="79943-133">Replication Distribution Agent</span><span class="sxs-lookup"><span data-stu-id="79943-133">Replication Distribution Agent</span></span>](replication-distribution-agent.md)|  
|<span data-ttu-id="79943-134">Agente di lettura coda</span><span class="sxs-lookup"><span data-stu-id="79943-134">Queue Reader Agent</span></span>|<span data-ttu-id="79943-135">**[\<Distributor>].\<integer>**</span><span class="sxs-lookup"><span data-stu-id="79943-135">**[\<Distributor>].\<integer>**</span></span>|[<span data-ttu-id="79943-136">Agente di lettura coda repliche</span><span class="sxs-lookup"><span data-stu-id="79943-136">Replication Queue Reader Agent</span></span>](replication-queue-reader-agent.md)|  
  
 <span data-ttu-id="79943-137"><sup>1</sup> Per le sottoscrizioni push di pubblicazioni Oracle, è\*\*\<Publisher>-\<Publisher**> invece di **\<Publisher>-\<PublicationDatabase>**</span><span class="sxs-lookup"><span data-stu-id="79943-137"><sup>1</sup> For push subscriptions to Oracle publications, it is \*\*\<Publisher>-\<Publisher**> rather than **\<Publisher>-\<PublicationDatabase>**</span></span>  
  
 <span data-ttu-id="79943-138"><sup>2</sup> Per le sottoscrizioni pull di pubblicazioni Oracle, è \*\*\<Publisher>-\<DistributionDatabase**> invece di **\<Publisher>-\<PublicationDatabase>**</span><span class="sxs-lookup"><span data-stu-id="79943-138"><sup>2</sup> For pull subscriptions to Oracle publications, it is \*\*\<Publisher>-\<DistributionDatabase**> rather than **\<Publisher>-\<PublicationDatabase>**</span></span>  
  
### <a name="to-view-and-modify-replication-agent-command-line-parameters-from-management-studio"></a><span data-ttu-id="79943-139">Per visualizzare e modificare i parametri della riga di comando dell'agente di replica in Management Studio</span><span class="sxs-lookup"><span data-stu-id="79943-139">To view and modify replication agent command line parameters from Management Studio</span></span>  
  
1.  <span data-ttu-id="79943-140">Connettersi al computer appropriato in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)]e quindi espandere il nodo del server:</span><span class="sxs-lookup"><span data-stu-id="79943-140">Connect to the appropriate computer in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)], and then expand the server node:</span></span>  
  
    -   <span data-ttu-id="79943-141">Per l'agente di distribuzione e l'agente di merge per le sottoscrizioni pull, connettersi al Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="79943-141">For the Distribution Agent and Merge Agent for pull subscriptions, connect to the Subscriber.</span></span>  
  
    -   <span data-ttu-id="79943-142">Per tutti gli altri agenti, connettersi al server di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="79943-142">For all other agents, connect to the Distributor.</span></span>  
  
2.  <span data-ttu-id="79943-143">Espandere la cartella **SQL Server Agent** e quindi la cartella **Processi** .</span><span class="sxs-lookup"><span data-stu-id="79943-143">Expand the **SQL Server Agent** folder, and then expand the **Jobs** folder.</span></span>  
  
3.  <span data-ttu-id="79943-144">Fare clic con il pulsante destro del mouse su un processo e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="79943-144">Right-click a job, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="79943-145">Nella pagina **Passaggi** della finestra di dialogo **Proprietà processo - \<Job>** selezionare il passaggio **Esecuzione agente** e quindi fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="79943-145">On the **Steps** page of the **Job Properties - \<Job>** dialog box, select the step **Run agent**, and then click **Edit**.</span></span>  
  
5.  <span data-ttu-id="79943-146">Nella finestra di dialogo **Proprietà passaggio processo - Esecuzione agente** modificare il campo **Comando** .</span><span class="sxs-lookup"><span data-stu-id="79943-146">In the **Job Step Properties - Run agent** dialog box, edit the **Command** field.</span></span>  
  
6.  <span data-ttu-id="79943-147">Fare clic su **OK** in entrambe le finestre di dialogo.</span><span class="sxs-lookup"><span data-stu-id="79943-147">Click **OK** on both dialog boxes.</span></span>  
  
### <a name="to-view-and-modify-distribution-agent-and-merge-agent-command-line-parameters-from-replication-monitor"></a><span data-ttu-id="79943-148">Per visualizzare e modificare i parametri della riga di comando dell'agente di distribuzione e dell'agente di merge in Monitoraggio replica</span><span class="sxs-lookup"><span data-stu-id="79943-148">To view and modify Distribution Agent and Merge Agent command line parameters from Replication Monitor</span></span>  
  
1.  <span data-ttu-id="79943-149">Espandere un gruppo di server di pubblicazione nel riquadro a sinistra di Monitoraggio replica, espandere un server di pubblicazione e quindi fare clic su una pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="79943-149">Expand a Publisher group in the left pane of Replication Monitor, expand a Publisher, and then click a publication.</span></span>  
  
2.  <span data-ttu-id="79943-150">Fare clic sulla scheda **Tutte le sottoscrizioni** .</span><span class="sxs-lookup"><span data-stu-id="79943-150">Click the **All Subscriptions** tab.</span></span>  
  
3.  <span data-ttu-id="79943-151">Fare clic con il pulsante destro del mouse su una sottoscrizione e quindi scegliere **Visualizza dettagli**.</span><span class="sxs-lookup"><span data-stu-id="79943-151">Right-click a subscription, and then click **View Details**.</span></span>  
  
4.  <span data-ttu-id="79943-152">Nella finestra **sottoscrizione \< SubscriptionName> \*\* fare clic su **azione**e quindi su \*\* \<AgentName> Proprietà processo**.</span><span class="sxs-lookup"><span data-stu-id="79943-152">In the **Subscription \< SubscriptionName>** window, click **Action**, and then click **\<AgentName> Job Properties**.</span></span>  
  
5.  <span data-ttu-id="79943-153">Nella pagina **Passaggi** della finestra di dialogo **Proprietà processo - \<Job>** selezionare il passaggio **Esecuzione agente** e quindi fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="79943-153">On the **Steps** page of the **Job Properties - \<Job>** dialog box, select the step **Run agent**, and then click **Edit**.</span></span>  
  
6.  <span data-ttu-id="79943-154">Nella finestra di dialogo **Proprietà passaggio processo - Esecuzione agente** modificare il campo **Comando** .</span><span class="sxs-lookup"><span data-stu-id="79943-154">In the **Job Step Properties - Run agent** dialog box, edit the **Command** field.</span></span>  
  
7.  <span data-ttu-id="79943-155">Fare clic su **OK** in entrambe le finestre di dialogo.</span><span class="sxs-lookup"><span data-stu-id="79943-155">Click **OK** on both dialog boxes.</span></span>  
  
### <a name="to-view-and-modify-snapshot-agent-log-reader-agent-and-queue-reader-agent-command-line-parameters-from-replication-monitor"></a><span data-ttu-id="79943-156">Per visualizzare e modificare i parametri della riga di comando dell'agente snapshot, dell'agente di lettura log e dell'agente di lettura coda in Monitoraggio replica</span><span class="sxs-lookup"><span data-stu-id="79943-156">To view and modify Snapshot Agent, Log Reader Agent, and Queue Reader Agent command line parameters from Replication Monitor</span></span>  
  
1.  <span data-ttu-id="79943-157">Espandere un gruppo di server di pubblicazione nel riquadro a sinistra di Monitoraggio replica, espandere un server di pubblicazione e quindi fare clic su una pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="79943-157">Expand a Publisher group in the left pane of Replication Monitor, expand a Publisher, and then click a publication.</span></span>  
  
2.  <span data-ttu-id="79943-158">Fare clic sulla scheda **Agenti** .</span><span class="sxs-lookup"><span data-stu-id="79943-158">Click the **Agents** tab.</span></span>  
  
3.  <span data-ttu-id="79943-159">Fare clic con il pulsante destro del mouse su un punto all'interno del riquadro della griglia e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="79943-159">Right-click an agent in the grid, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="79943-160">Nella pagina **Passaggi** della finestra di dialogo **Proprietà processo - \<Job>** selezionare il passaggio **Esecuzione agente** e quindi fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="79943-160">On the **Steps** page of the **Job Properties - \<Job>** dialog box, select the step **Run agent**, and then click **Edit**.</span></span>  
  
5.  <span data-ttu-id="79943-161">Nella finestra di dialogo **Proprietà passaggio processo - Esecuzione agente** modificare il campo **Comando** .</span><span class="sxs-lookup"><span data-stu-id="79943-161">In the **Job Step Properties - Run agent** dialog box, edit the **Command** field.</span></span>  
  
6.  <span data-ttu-id="79943-162">Fare clic su **OK** in entrambe le finestre di dialogo.</span><span class="sxs-lookup"><span data-stu-id="79943-162">Click **OK** on both dialog boxes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79943-163">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="79943-163">See Also</span></span>  
 <span data-ttu-id="79943-164">[Amministrazione dell'agente di replica](replication-agent-administration.md) </span><span class="sxs-lookup"><span data-stu-id="79943-164">[Replication Agent Administration](replication-agent-administration.md) </span></span>  
 <span data-ttu-id="79943-165">[Concetti di base relativi ai file eseguibili dell'agente di replica](../concepts/replication-agent-executables-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="79943-165">[Replication Agent Executables Concepts](../concepts/replication-agent-executables-concepts.md) </span></span>  
 [<span data-ttu-id="79943-166">Panoramica degli agenti di replica</span><span class="sxs-lookup"><span data-stu-id="79943-166">Replication Agents Overview</span></span>](replication-agents-overview.md)  
  
  
