---
title: Sincronizzare una sottoscrizione pull | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- pull subscriptions [SQL Server replication], synchronizing
- synchronization [SQL Server replication], pull subscriptions
- subscriptions [SQL Server replication], pull
ms.assetid: 3ca24b23-fdc3-408e-8208-a2ace48fc8e3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 826622cd17862c0535e60c01baab756af2b2996b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629352"
---
# <a name="synchronize-a-pull-subscription"></a><span data-ttu-id="2fddf-102">Sincronizzazione di una sottoscrizione pull</span><span class="sxs-lookup"><span data-stu-id="2fddf-102">Synchronize a Pull Subscription</span></span>
  <span data-ttu-id="2fddf-103">In questo argomento viene descritto come sincronizzare una sottoscrizione pull in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [agenti di replica](agents/replication-agents-overview.md)o RMO (Replication Management Objects).</span><span class="sxs-lookup"><span data-stu-id="2fddf-103">This topic describes how to synchronize a pull subscription in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [replication agents](agents/replication-agents-overview.md), or Replication Management Objects (RMO).</span></span>  
  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="2fddf-104">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2fddf-104">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="2fddf-105">Le sottoscrizioni vengono sincronizzate dall'agente di distribuzione, per la replica snapshot e transazionale, o dall'agente di merge, per la replica di tipo merge.</span><span class="sxs-lookup"><span data-stu-id="2fddf-105">Subscriptions are synchronized by the Distribution Agent (for snapshot and transactional replication) or the Merge Agent (for merge replication).</span></span> <span data-ttu-id="2fddf-106">Gli agenti possono essere in esecuzione continuamente, essere in esecuzione su richiesta o essere in esecuzione su una pianificazione.</span><span class="sxs-lookup"><span data-stu-id="2fddf-106">Agents can run continuously, run on demand, or run on a schedule.</span></span> <span data-ttu-id="2fddf-107">Per altre informazioni sull'impostazione delle pianificazioni della sincronizzazione, vedere [Specificare le pianificazioni della sincronizzazione](specify-synchronization-schedules.md).</span><span class="sxs-lookup"><span data-stu-id="2fddf-107">For more information about specifying synchronization schedules, see [Specify Synchronization Schedules](specify-synchronization-schedules.md).</span></span>  
  
 <span data-ttu-id="2fddf-108">Sincronizzare una sottoscrizione su richiesta dalla cartella **Sottoscrizioni locali** in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2fddf-108">Synchronize a subscription on demand from the **Local Subscriptions** folder in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
#### <a name="to-synchronize-a-pull-subscription-on-demand-in-management-studio"></a><span data-ttu-id="2fddf-109">Per sincronizzare una sottoscrizione pull su richiesta in Management Studio</span><span class="sxs-lookup"><span data-stu-id="2fddf-109">To synchronize a pull subscription on demand in Management Studio</span></span>  
  
1.  <span data-ttu-id="2fddf-110">Connettersi al Sottoscrittore in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]e quindi espandere il nodo del server.</span><span class="sxs-lookup"><span data-stu-id="2fddf-110">Connect to the Subscriber in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="2fddf-111">Espandere la cartella **Replica** e quindi la cartella **Sottoscrizioni locali** .</span><span class="sxs-lookup"><span data-stu-id="2fddf-111">Expand the **Replication** folder, and then expand the **Local Subscriptions** folder.</span></span>  
  
3.  <span data-ttu-id="2fddf-112">Fare clic con il pulsante destro del mouse sulla sottoscrizione che si desidera sincronizzare e quindi scegliere **Visualizza stato sincronizzazione**.</span><span class="sxs-lookup"><span data-stu-id="2fddf-112">Right-click the subscription you want to synchronize, and then click **View Synchronization Status**.</span></span>  
  
4.  <span data-ttu-id="2fddf-113">Nella finestra di dialogo **Visualizza stato sincronizzazione - \<Subscriber>:\<SubscriptionDatabase>** fare clic su **Avvia**.</span><span class="sxs-lookup"><span data-stu-id="2fddf-113">In the **View Synchronization Status - \<Subscriber>:\<SubscriptionDatabase>** dialog box, click **Start**.</span></span> <span data-ttu-id="2fddf-114">Al termine della sincronizzazione verrà visualizzato il messaggio **Sincronizzazione completata** .</span><span class="sxs-lookup"><span data-stu-id="2fddf-114">When synchronization is complete, the message **Synchronization completed** is displayed.</span></span>  
  
5.  <span data-ttu-id="2fddf-115">Fare clic su **Close**.</span><span class="sxs-lookup"><span data-stu-id="2fddf-115">Click **Close**.</span></span>  
  
##  <a name="replication-agents"></a><a name="ReplProg"></a> <span data-ttu-id="2fddf-116">Replication Agents</span><span class="sxs-lookup"><span data-stu-id="2fddf-116">Replication Agents</span></span>  
 <span data-ttu-id="2fddf-117">Le sottoscrizioni pull possono essere sincronizzate a livello di programmazione e su richiesta richiamando il file eseguibile dell'agente di replica appropriato dal prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="2fddf-117">Pull subscriptions can be synchronized programmatically and on-demand by invoking the appropriate replication agent executable file from the command prompt.</span></span> <span data-ttu-id="2fddf-118">Il file eseguibile dell'agente di replica richiamato dipenderà dal tipo di pubblicazione a cui appartiene la sottoscrizione pull.</span><span class="sxs-lookup"><span data-stu-id="2fddf-118">The replication agent executable file that is invoked will depend on the type of publication to which the pull subscription belongs.</span></span> <span data-ttu-id="2fddf-119">Per altre informazioni, vedere [Replication Agents](agents/replication-agents-overview.md).</span><span class="sxs-lookup"><span data-stu-id="2fddf-119">For more information, see [Replication Agents](agents/replication-agents-overview.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2fddf-120">Gli agenti di replica si connettono al server locale con le credenziali dell'autenticazione di Windows dell'utente che avvia l'agente dal prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="2fddf-120">Replication agents connect to the local server using the Windows Authentication credentials of the user who started the agent from the command prompt.</span></span> <span data-ttu-id="2fddf-121">Tali credenziali di Windows vengono inoltre utilizzate per la connessione ai server remoti tramite l'autenticazione integrata di Windows.</span><span class="sxs-lookup"><span data-stu-id="2fddf-121">These Windows credentials are also used when connecting to remote servers using Windows Integrated Authentication.</span></span>  
  
#### <a name="to-start-the-distribution-agent-from-the-command-prompt-or-from-a-batch-file"></a><span data-ttu-id="2fddf-122">Per avviare l'agente di distribuzione dal prompt dei comandi o da un file batch</span><span class="sxs-lookup"><span data-stu-id="2fddf-122">To start the distribution agent from the command prompt or from a batch file</span></span>  
  
1.  <span data-ttu-id="2fddf-123">Dal prompt dei comandi o in un file batch, avviare l' [Agente distribuzione repliche](agents/replication-distribution-agent.md) eseguendo **distrib.exe**con gli argomenti della riga di comando seguenti:</span><span class="sxs-lookup"><span data-stu-id="2fddf-123">From the command prompt or in a batch file, start the [Replication Distribution Agent](agents/replication-distribution-agent.md) by running **distrib.exe**, specifying the following command-line arguments:</span></span>  
  
    -   <span data-ttu-id="2fddf-124">**-Publisher**</span><span class="sxs-lookup"><span data-stu-id="2fddf-124">**-Publisher**</span></span>  
  
    -   <span data-ttu-id="2fddf-125">**-PublisherDB**</span><span class="sxs-lookup"><span data-stu-id="2fddf-125">**-PublisherDB**</span></span>  
  
    -   <span data-ttu-id="2fddf-126">**-Distributor**</span><span class="sxs-lookup"><span data-stu-id="2fddf-126">**-Distributor**</span></span>  
  
    -   <span data-ttu-id="2fddf-127">**-DistributorSecurityMode** = **1**</span><span class="sxs-lookup"><span data-stu-id="2fddf-127">**-DistributorSecurityMode** = **1**</span></span>  
  
    -   <span data-ttu-id="2fddf-128">**-Subscriber**</span><span class="sxs-lookup"><span data-stu-id="2fddf-128">**-Subscriber**</span></span>  
  
    -   <span data-ttu-id="2fddf-129">**-SubscriberDB**</span><span class="sxs-lookup"><span data-stu-id="2fddf-129">**-SubscriberDB**</span></span>  
  
    -   <span data-ttu-id="2fddf-130">**-SubscriberSecurityMode** = **1**</span><span class="sxs-lookup"><span data-stu-id="2fddf-130">**-SubscriberSecurityMode** = **1**</span></span>  
  
    -   <span data-ttu-id="2fddf-131">**-SubscriptionType** = **1**</span><span class="sxs-lookup"><span data-stu-id="2fddf-131">**-SubscriptionType** = **1**</span></span>  
  
     <span data-ttu-id="2fddf-132">Se si utilizza l'autenticazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , è inoltre necessario specificare gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="2fddf-132">If you are using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication, you must also specify the following arguments:</span></span>  
  
    -   <span data-ttu-id="2fddf-133">**-DistributorLogin**</span><span class="sxs-lookup"><span data-stu-id="2fddf-133">**-DistributorLogin**</span></span>  
  
    -   <span data-ttu-id="2fddf-134">**-DistributorPassword**</span><span class="sxs-lookup"><span data-stu-id="2fddf-134">**-DistributorPassword**</span></span>  
  
    -   <span data-ttu-id="2fddf-135">**-DistributorSecurityMode** = **0**</span><span class="sxs-lookup"><span data-stu-id="2fddf-135">**-DistributorSecurityMode** = **0**</span></span>  
  
    -   <span data-ttu-id="2fddf-136">**-PublisherLogin**</span><span class="sxs-lookup"><span data-stu-id="2fddf-136">**-PublisherLogin**</span></span>  
  
    -   <span data-ttu-id="2fddf-137">**-PublisherPassword**</span><span class="sxs-lookup"><span data-stu-id="2fddf-137">**-PublisherPassword**</span></span>  
  
    -   <span data-ttu-id="2fddf-138">**-PublisherSecurityMode** = **0**</span><span class="sxs-lookup"><span data-stu-id="2fddf-138">**-PublisherSecurityMode** = **0**</span></span>  
  
    -   <span data-ttu-id="2fddf-139">**-SubscriberLogin**</span><span class="sxs-lookup"><span data-stu-id="2fddf-139">**-SubscriberLogin**</span></span>  
  
    -   <span data-ttu-id="2fddf-140">**-SubscriberPassword**</span><span class="sxs-lookup"><span data-stu-id="2fddf-140">**-SubscriberPassword**</span></span>  
  
    -   <span data-ttu-id="2fddf-141">**-SubscriberSecurityMode** = **0**</span><span class="sxs-lookup"><span data-stu-id="2fddf-141">**-SubscriberSecurityMode** = **0**</span></span>  
  
#### <a name="to-start-the-merge-agent-from-the-command-prompt-or-from-a-batch-file"></a><span data-ttu-id="2fddf-142">Per avviare l'agente di merge dal prompt dei comandi o da un file batch</span><span class="sxs-lookup"><span data-stu-id="2fddf-142">To start the merge agent from the command prompt or from a batch file</span></span>  
  
1.  <span data-ttu-id="2fddf-143">Dal prompt dei comandi o in un file batch, avviare l' [Agente merge repliche](agents/replication-merge-agent.md) eseguendo **replmerg.exe**con gli argomenti della riga di comando seguenti:</span><span class="sxs-lookup"><span data-stu-id="2fddf-143">From the command prompt or in a batch file, start the [Replication Merge Agent](agents/replication-merge-agent.md) by running **replmerg.exe**, specifying the following command-line arguments:</span></span>  
  
    -   <span data-ttu-id="2fddf-144">**-Publisher**</span><span class="sxs-lookup"><span data-stu-id="2fddf-144">**-Publisher**</span></span>  
  
    -   <span data-ttu-id="2fddf-145">**-PublisherDB**</span><span class="sxs-lookup"><span data-stu-id="2fddf-145">**-PublisherDB**</span></span>  
  
    -   <span data-ttu-id="2fddf-146">**-PublisherSecurityMode** = **1**</span><span class="sxs-lookup"><span data-stu-id="2fddf-146">**-PublisherSecurityMode** = **1**</span></span>  
  
    -   <span data-ttu-id="2fddf-147">**-Publication**</span><span class="sxs-lookup"><span data-stu-id="2fddf-147">**-Publication**</span></span>  
  
    -   <span data-ttu-id="2fddf-148">**-Distributor**</span><span class="sxs-lookup"><span data-stu-id="2fddf-148">**-Distributor**</span></span>  
  
    -   <span data-ttu-id="2fddf-149">**-DistributorSecurityMode** = **1**</span><span class="sxs-lookup"><span data-stu-id="2fddf-149">**-DistributorSecurityMode** = **1**</span></span>  
  
    -   <span data-ttu-id="2fddf-150">**-Subscriber**</span><span class="sxs-lookup"><span data-stu-id="2fddf-150">**-Subscriber**</span></span>  
  
    -   <span data-ttu-id="2fddf-151">**-SubscriberSecurityMode** = **1**</span><span class="sxs-lookup"><span data-stu-id="2fddf-151">**-SubscriberSecurityMode** = **1**</span></span>  
  
    -   <span data-ttu-id="2fddf-152">**-SubscriberDB**</span><span class="sxs-lookup"><span data-stu-id="2fddf-152">**-SubscriberDB**</span></span>  
  
    -   <span data-ttu-id="2fddf-153">**-SubscriptionType** = **1**</span><span class="sxs-lookup"><span data-stu-id="2fddf-153">**-SubscriptionType** = **1**</span></span>  
  
     <span data-ttu-id="2fddf-154">Se si utilizza l'autenticazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , è inoltre necessario specificare gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="2fddf-154">If you are using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication, you must also specify the following arguments:</span></span>  
  
    -   <span data-ttu-id="2fddf-155">**-DistributorLogin**</span><span class="sxs-lookup"><span data-stu-id="2fddf-155">**-DistributorLogin**</span></span>  
  
    -   <span data-ttu-id="2fddf-156">**-DistributorPassword**</span><span class="sxs-lookup"><span data-stu-id="2fddf-156">**-DistributorPassword**</span></span>  
  
    -   <span data-ttu-id="2fddf-157">**-DistributorSecurityMode** = **0**</span><span class="sxs-lookup"><span data-stu-id="2fddf-157">**-DistributorSecurityMode** = **0**</span></span>  
  
    -   <span data-ttu-id="2fddf-158">**-PublisherLogin**</span><span class="sxs-lookup"><span data-stu-id="2fddf-158">**-PublisherLogin**</span></span>  
  
    -   <span data-ttu-id="2fddf-159">**-PublisherPassword**</span><span class="sxs-lookup"><span data-stu-id="2fddf-159">**-PublisherPassword**</span></span>  
  
    -   <span data-ttu-id="2fddf-160">**-PublisherSecurityMode** = **0**</span><span class="sxs-lookup"><span data-stu-id="2fddf-160">**-PublisherSecurityMode** = **0**</span></span>  
  
    -   <span data-ttu-id="2fddf-161">**-SubscriberLogin**</span><span class="sxs-lookup"><span data-stu-id="2fddf-161">**-SubscriberLogin**</span></span>  
  
    -   <span data-ttu-id="2fddf-162">**-SubscriberPassword**</span><span class="sxs-lookup"><span data-stu-id="2fddf-162">**-SubscriberPassword**</span></span>  
  
    -   <span data-ttu-id="2fddf-163">**-SubscriberSecurityMode** = **0**</span><span class="sxs-lookup"><span data-stu-id="2fddf-163">**-SubscriberSecurityMode** = **0**</span></span>  
  
###  <a name="examples-replication-agents"></a><a name="TsqlExample"></a> <span data-ttu-id="2fddf-164">Esempi (agenti di replica)</span><span class="sxs-lookup"><span data-stu-id="2fddf-164">Examples (Replication Agents)</span></span>  
 <span data-ttu-id="2fddf-165">Nell'esempio seguente viene avviato l'agente di distribuzione per sincronizzare una sottoscrizione pull.</span><span class="sxs-lookup"><span data-stu-id="2fddf-165">The following example starts the Distribution Agent to synchronize a pull subscription.</span></span> <span data-ttu-id="2fddf-166">Tutte le connessioni vengono eseguite con l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="2fddf-166">All connections are made using Windows Authentication.</span></span>  
  
 [!code-sql[HowTo#bat_synctranpullsub_10](../../snippets/tsql/SQL15/replication/howto/tsql/synctranpullsub_10.bat)]  
  
 <span data-ttu-id="2fddf-167">Nell'esempio seguente viene avviato l'agente di merge per sincronizzare una sottoscrizione pull.</span><span class="sxs-lookup"><span data-stu-id="2fddf-167">The following example starts the Merge Agent to synchronize a pull subscription.</span></span> <span data-ttu-id="2fddf-168">Tutte le connessioni vengono eseguite con l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="2fddf-168">All connections are made using Windows Authentication.</span></span>  
  
 [!code-sql[HowTo#bat_syncmergepullsub_10](../../snippets/tsql/SQL15/replication/howto/tsql/syncmergepullsub_10.bat)]  
  
##  <a name="using-replication-management-objects-rmo"></a><a name="RMOProcedure"></a> <span data-ttu-id="2fddf-169">Utilizzo di RMO (Replication Management Objects)</span><span class="sxs-lookup"><span data-stu-id="2fddf-169">Using Replication Management Objects (RMO)</span></span>  
 <span data-ttu-id="2fddf-170">È possibile sincronizzare le sottoscrizioni pull a livello di programmazione tramite gli oggetti RMO (Replication Management Objects) e l'accesso tramite codice gestito alle funzionalità dell'agente di replica.</span><span class="sxs-lookup"><span data-stu-id="2fddf-170">You can synchronize pull subscriptions programmatically by using Replication Management Objects (RMO) and managed code access to replication agent functionalities.</span></span> <span data-ttu-id="2fddf-171">Le classi utilizzate per la sincronizzazione di una sottoscrizione pull dipendono dal tipo di pubblicazione a cui appartiene la sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="2fddf-171">The classes you use to synchronize a pull subscription depend on the type of publication to which the subscription belongs.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2fddf-172">Se si desidera avviare una sincronizzazione eseguita in modo autonomo senza effetti sull'applicazione, avviare l'agente in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="2fddf-172">If you want to start a synchronization that runs autonomously without affecting your application, start the agent asynchronously.</span></span> <span data-ttu-id="2fddf-173">Se invece si desidera monitorare i risultati della sincronizzazione e ricevere callback dall'agente durante il processo di sincronizzazione (ad esempio per la visualizzazione di una barra di stato) è necessario avviare l'agente in modo sincrono.</span><span class="sxs-lookup"><span data-stu-id="2fddf-173">However, if you want to monitor the outcome of the synchronization and receive callbacks from the agent during the synchronization process (for example, to display a progress bar), you should start the agent synchronously.</span></span> <span data-ttu-id="2fddf-174">Per i sottoscrittori di [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssExpressEd2005](../../includes/ssexpressed2005-md.md)] , l'agente deve essere avviato in modo sincrono.</span><span class="sxs-lookup"><span data-stu-id="2fddf-174">For [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssExpressEd2005](../../includes/ssexpressed2005-md.md)] Subscribers, you must start the agent synchronously.</span></span>  
  
#### <a name="to-synchronize-a-pull-subscription-to-a-snapshot-or-transactional-publication"></a><span data-ttu-id="2fddf-175">Per sincronizzare una sottoscrizione pull di una pubblicazione snapshot o transazionale</span><span class="sxs-lookup"><span data-stu-id="2fddf-175">To synchronize a pull subscription to a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="2fddf-176">Creare una connessione al Sottoscrittore tramite la classe <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="2fddf-176">Create a connection to the Subscriber by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="2fddf-177">Creare un'istanza della classe <xref:Microsoft.SqlServer.Replication.TransPullSubscription> e impostare le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="2fddf-177">Create an instance of the <xref:Microsoft.SqlServer.Replication.TransPullSubscription> class, and set the following properties:</span></span>  
  
    -   <span data-ttu-id="2fddf-178">Nome del database di sottoscrizione per <xref:Microsoft.SqlServer.Replication.PullSubscription.DatabaseName%2A>.</span><span class="sxs-lookup"><span data-stu-id="2fddf-178">The subscription database name for <xref:Microsoft.SqlServer.Replication.PullSubscription.DatabaseName%2A>.</span></span>  
  
    -   <span data-ttu-id="2fddf-179">Nome della pubblicazione a cui appartiene la sottoscrizione per <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationName%2A>.</span><span class="sxs-lookup"><span data-stu-id="2fddf-179">The name of the publication to which the subscription belongs for <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationName%2A>.</span></span>  
  
    -   <span data-ttu-id="2fddf-180">Nome del database di pubblicazione per <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationDBName%2A>.</span><span class="sxs-lookup"><span data-stu-id="2fddf-180">The name of the publication database for <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationDBName%2A>.</span></span>  
  
    -   <span data-ttu-id="2fddf-181">Nome del server di pubblicazione per <xref:Microsoft.SqlServer.Replication.PullSubscription.PublisherName%2A>.</span><span class="sxs-lookup"><span data-stu-id="2fddf-181">The name of the Publisher for <xref:Microsoft.SqlServer.Replication.PullSubscription.PublisherName%2A>.</span></span>  
  
    -   <span data-ttu-id="2fddf-182">La connessione creata nel passaggio 1 per <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A>.</span><span class="sxs-lookup"><span data-stu-id="2fddf-182">The connection created in step 1 for <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A>.</span></span>  
  
3.  <span data-ttu-id="2fddf-183">Chiamare il metodo <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> per recuperare le proprietà rimanenti della sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="2fddf-183">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> method to get the remaining subscription properties.</span></span> <span data-ttu-id="2fddf-184">Se il metodo restituisce `false`, verificare che la sottoscrizione esista.</span><span class="sxs-lookup"><span data-stu-id="2fddf-184">If this method returns `false`, verify that the subscription exists.</span></span>  
  
4.  <span data-ttu-id="2fddf-185">Avviare l'agente di distribuzione nel Sottoscrittore in uno dei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="2fddf-185">Start the Distribution Agent at the Subscriber in one of the following ways:</span></span>  
  
    -   <span data-ttu-id="2fddf-186">Chiamare il metodo <xref:Microsoft.SqlServer.Replication.TransPullSubscription.SynchronizeWithJob%2A> nell'istanza di <xref:Microsoft.SqlServer.Replication.TransPullSubscription> creata al passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="2fddf-186">Call the <xref:Microsoft.SqlServer.Replication.TransPullSubscription.SynchronizeWithJob%2A> method on the instance of <xref:Microsoft.SqlServer.Replication.TransPullSubscription> from step 2.</span></span> <span data-ttu-id="2fddf-187">Questo metodo consente di avviare l'agente di distribuzione in modo asincrono e il controllo viene restituito immediatamente all'applicazione durante l'esecuzione del processo dell'agente.</span><span class="sxs-lookup"><span data-stu-id="2fddf-187">This method starts the Distribution Agent asynchronously, and control immediately returns to your application while the agent job is running.</span></span> <span data-ttu-id="2fddf-188">Non è possibile chiamare questo metodo per i Sottoscrittori [!INCLUDE[ssExpressEd2005](../../includes/ssexpressed2005-md.md)] se la sottoscrizione è stata creata con il valore `false` per <xref:Microsoft.SqlServer.Replication.PullSubscription.CreateSyncAgentByDefault%2A> (impostazione predefinita).</span><span class="sxs-lookup"><span data-stu-id="2fddf-188">You cannot call this method for [!INCLUDE[ssExpressEd2005](../../includes/ssexpressed2005-md.md)] Subscribers or if the subscription was created with a value of `false` for <xref:Microsoft.SqlServer.Replication.PullSubscription.CreateSyncAgentByDefault%2A> (the default).</span></span>  
  
    -   <span data-ttu-id="2fddf-189">Recuperare un'istanza della classe <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent> dalla proprietà <xref:Microsoft.SqlServer.Replication.TransPullSubscription.SynchronizationAgent%2A> e chiamare il metodo <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.Synchronize%2A> .</span><span class="sxs-lookup"><span data-stu-id="2fddf-189">Get an instance of the <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent> class from the <xref:Microsoft.SqlServer.Replication.TransPullSubscription.SynchronizationAgent%2A> property, and call the <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.Synchronize%2A> method.</span></span> <span data-ttu-id="2fddf-190">Questo metodo avvia l'agente in modo sincrono e il controllo rimane al processo dell'agente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="2fddf-190">This method starts the agent synchronously, and control remains with the running agent job.</span></span> <span data-ttu-id="2fddf-191">Nella modalità sincrona è possibile gestire l'evento <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.Status> durante l'esecuzione dell'agente.</span><span class="sxs-lookup"><span data-stu-id="2fddf-191">During synchronous execution, you can handle the <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.Status> event while the agent is running.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="2fddf-192">Se al `false` <xref:Microsoft.SqlServer.Replication.PullSubscription.CreateSyncAgentByDefault%2A> momento della creazione della sottoscrizione pull è stato specificato il valore per (impostazione predefinita), è inoltre necessario specificare <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.Distributor%2A> , <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.DistributorSecurityMode%2A> e facoltativamente <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.DistributorLogin%2A> e <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.DistributorPassword%2A> perché i metadati correlati al processo dell'agente per la sottoscrizione non sono disponibili in [MSsubscription_properties](/sql/relational-databases/system-tables/mssubscription-properties-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2fddf-192">If you specified a value of `false` for <xref:Microsoft.SqlServer.Replication.PullSubscription.CreateSyncAgentByDefault%2A> (the default) when you created the pull subscription, you also need to specify <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.Distributor%2A>, <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.DistributorSecurityMode%2A>, and optionally <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.DistributorLogin%2A> and <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.DistributorPassword%2A> because the agent job related metadata for the subscription is not available in [MSsubscription_properties](/sql/relational-databases/system-tables/mssubscription-properties-transact-sql).</span></span>  
  
#### <a name="to-synchronize-a-pull-subscription-to-a-merge-publication"></a><span data-ttu-id="2fddf-193">Per sincronizzare una sottoscrizione pull di una pubblicazione di tipo merge</span><span class="sxs-lookup"><span data-stu-id="2fddf-193">To synchronize a pull subscription to a merge publication</span></span>  
  
1.  <span data-ttu-id="2fddf-194">Creare una connessione al Sottoscrittore tramite la classe <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="2fddf-194">Create a connection to the Subscriber by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="2fddf-195">Creare un'istanza della classe <xref:Microsoft.SqlServer.Replication.MergePullSubscription> e impostare le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="2fddf-195">Create an instance of the <xref:Microsoft.SqlServer.Replication.MergePullSubscription> class, and set the following properties:</span></span>  
  
    -   <span data-ttu-id="2fddf-196">Nome del database di sottoscrizione per <xref:Microsoft.SqlServer.Replication.PullSubscription.DatabaseName%2A>.</span><span class="sxs-lookup"><span data-stu-id="2fddf-196">The subscription database name for <xref:Microsoft.SqlServer.Replication.PullSubscription.DatabaseName%2A>.</span></span>  
  
    -   <span data-ttu-id="2fddf-197">Nome della pubblicazione a cui appartiene la sottoscrizione per <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationName%2A>.</span><span class="sxs-lookup"><span data-stu-id="2fddf-197">The name of the publication to which the subscription belongs for <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationName%2A>.</span></span>  
  
    -   <span data-ttu-id="2fddf-198">Nome del database pubblicato per <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationDBName%2A>.</span><span class="sxs-lookup"><span data-stu-id="2fddf-198">The name of the published database for <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationDBName%2A>.</span></span>  
  
    -   <span data-ttu-id="2fddf-199">Nome del server di pubblicazione per <xref:Microsoft.SqlServer.Replication.PullSubscription.PublisherName%2A>.</span><span class="sxs-lookup"><span data-stu-id="2fddf-199">The name of the Publisher for <xref:Microsoft.SqlServer.Replication.PullSubscription.PublisherName%2A>.</span></span>  
  
    -   <span data-ttu-id="2fddf-200">La connessione creata nel passaggio 1 per <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A>.</span><span class="sxs-lookup"><span data-stu-id="2fddf-200">The connection created in step 1 for <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A>.</span></span>  
  
3.  <span data-ttu-id="2fddf-201">Chiamare il metodo <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> per recuperare le proprietà rimanenti della sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="2fddf-201">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> method to get the remaining subscription properties.</span></span> <span data-ttu-id="2fddf-202">Se il metodo restituisce `false`, verificare che la sottoscrizione esista.</span><span class="sxs-lookup"><span data-stu-id="2fddf-202">If this method returns `false`, verify that the subscription exists.</span></span>  
  
4.  <span data-ttu-id="2fddf-203">Avviare l'agente di merge nel Sottoscrittore in uno dei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="2fddf-203">Start the Merge Agent at the Subscriber in one of the following ways:</span></span>  
  
    -   <span data-ttu-id="2fddf-204">Chiamare il metodo <xref:Microsoft.SqlServer.Replication.MergePullSubscription.SynchronizeWithJob%2A> nell'istanza di <xref:Microsoft.SqlServer.Replication.MergePullSubscription> creata al passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="2fddf-204">Call the <xref:Microsoft.SqlServer.Replication.MergePullSubscription.SynchronizeWithJob%2A> method on the instance of <xref:Microsoft.SqlServer.Replication.MergePullSubscription> from step 2.</span></span> <span data-ttu-id="2fddf-205">Questo metodo consente di avviare l'agente di merge in modo asincrono e il controllo viene restituito immediatamente all'applicazione durante l'esecuzione del processo dell'agente.</span><span class="sxs-lookup"><span data-stu-id="2fddf-205">This method starts the Merge Agent asynchronously, and control immediately returns to your application while the agent job is running.</span></span> <span data-ttu-id="2fddf-206">Non è possibile chiamare questo metodo per i Sottoscrittori [!INCLUDE[ssExpressEd2005](../../includes/ssexpressed2005-md.md)] se la sottoscrizione è stata creata con il valore `false` per <xref:Microsoft.SqlServer.Replication.PullSubscription.CreateSyncAgentByDefault%2A> (impostazione predefinita).</span><span class="sxs-lookup"><span data-stu-id="2fddf-206">You cannot call this method for [!INCLUDE[ssExpressEd2005](../../includes/ssexpressed2005-md.md)] Subscribers or if the subscription was created with a value of `false` for <xref:Microsoft.SqlServer.Replication.PullSubscription.CreateSyncAgentByDefault%2A> (the default).</span></span>  
  
    -   <span data-ttu-id="2fddf-207">Recuperare un'istanza della classe <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent> dalla proprietà <xref:Microsoft.SqlServer.Replication.MergePullSubscription.SynchronizationAgent%2A> e chiamare il metodo <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.Synchronize%2A> .</span><span class="sxs-lookup"><span data-stu-id="2fddf-207">Obtain an instance of the <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent> class from the <xref:Microsoft.SqlServer.Replication.MergePullSubscription.SynchronizationAgent%2A> property, and call the <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.Synchronize%2A> method.</span></span> <span data-ttu-id="2fddf-208">Questo metodo avvia l'agente di merge in modo sincrono e il controllo rimane al processo dell'agente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="2fddf-208">This method starts the Merge Agent synchronously, and control remains with the running agent job.</span></span> <span data-ttu-id="2fddf-209">Nella modalità sincrona è possibile gestire l'evento <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.Status> durante l'esecuzione dell'agente.</span><span class="sxs-lookup"><span data-stu-id="2fddf-209">During synchronous execution, you can handle the <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.Status> event while the agent is running.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="2fddf-210">Se al `false` <xref:Microsoft.SqlServer.Replication.PullSubscription.CreateSyncAgentByDefault%2A> momento della creazione della sottoscrizione pull è stato specificato il valore per (impostazione predefinita), è necessario specificare anche <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.Distributor%2A> , <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.DistributorSecurityMode%2A> , <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.PublisherSecurityMode%2A> , <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.HostName%2A> , <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.SubscriptionType%2A> , <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.ExchangeType%2A> e facoltativamente <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.DistributorLogin%2A> ,, <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.DistributorPassword%2A> <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.PublisherLogin%2A> e <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.PublisherPassword%2A> perché i metadati correlati al processo dell'agente per la sottoscrizione non sono disponibili in [MSsubscription_properties](/sql/relational-databases/system-tables/mssubscription-properties-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2fddf-210">If you specified a value of `false` for <xref:Microsoft.SqlServer.Replication.PullSubscription.CreateSyncAgentByDefault%2A> (the default) when you created the pull subscription, you also need to specify <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.Distributor%2A>, <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.DistributorSecurityMode%2A>, <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.PublisherSecurityMode%2A>, <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.HostName%2A>, <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.SubscriptionType%2A>, <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.ExchangeType%2A>, and optionally <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.DistributorLogin%2A>, <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.DistributorPassword%2A>, <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.PublisherLogin%2A>, and <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.PublisherPassword%2A> because the agent job related metadata for the subscription is not available in [MSsubscription_properties](/sql/relational-databases/system-tables/mssubscription-properties-transact-sql).</span></span>  
  
###  <a name="examples-rmo"></a><a name="PShellExample"></a> <span data-ttu-id="2fddf-211">Esempi (RMO)</span><span class="sxs-lookup"><span data-stu-id="2fddf-211">Examples (RMO)</span></span>  
 <span data-ttu-id="2fddf-212">In questo esempio viene illustrata la sincronizzazione di una sottoscrizione pull di una pubblicazione transazionale, con avvio asincrono dell'agente utilizzando il processo dell'agente.</span><span class="sxs-lookup"><span data-stu-id="2fddf-212">This example synchronizes a pull subscription to a transactional publication, where the agent is started asynchronously using the agent job.</span></span>  
  
 [!code-csharp[HowTo#rmo_SyncTranPullSub_WithJob](../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_synctranpullsub_withjob)]  
  
 [!code-vb[HowTo#rmo_vb_SyncTranPullSub_WithJob](../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_synctranpullsub_withjob)]  
  
 <span data-ttu-id="2fddf-213">In questo esempio viene illustrata la sincronizzazione di una sottoscrizione pull di una pubblicazione transazionale, con avvio sincrono dell'agente.</span><span class="sxs-lookup"><span data-stu-id="2fddf-213">This example synchronizes a pull subscription to a transactional publication, where the agent is started synchronously.</span></span>  
  
 [!code-csharp[HowTo#rmo_SyncTranPullSub](../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_synctranpullsub)]  
  
 [!code-vb[HowTo#rmo_vb_SyncTranPullSub](../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_synctranpullsub)]  
  
 <span data-ttu-id="2fddf-214">In questo esempio viene illustrata la sincronizzazione di una sottoscrizione pull di una pubblicazione di tipo merge, con avvio asincrono dell'agente utilizzando il processo dell'agente.</span><span class="sxs-lookup"><span data-stu-id="2fddf-214">This example synchronizes a pull subscription to a merge publication, where the agent is started asynchronously using the agent job.</span></span>  
  
 [!code-csharp[HowTo#rmo_SyncMergePullSub_WithJob](../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_syncmergepullsub_withjob)]  
  
 [!code-vb[HowTo#rmo_vb_SyncMergePullSub_WithJob](../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_syncmergepullsub_withjob)]  
  
 <span data-ttu-id="2fddf-215">In questo esempio viene illustrata la sincronizzazione di una sottoscrizione pull di una pubblicazione di tipo merge, con avvio sincrono dell'agente.</span><span class="sxs-lookup"><span data-stu-id="2fddf-215">This example synchronizes a pull subscription to a merge publication, where the agent is started synchronously.</span></span>  
  
 [!code-csharp[HowTo#rmo_SyncMergePullSub](../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_syncmergepullsub)]  
  
 [!code-vb[HowTo#rmo_vb_SyncMergePullSub](../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_syncmergepullsub)]  
  
 <span data-ttu-id="2fddf-216">In questo esempio viene illustrata la sincronizzazione di una sottoscrizione pull di una pubblicazione di tipo merge con la sincronizzazione tramite il Web.</span><span class="sxs-lookup"><span data-stu-id="2fddf-216">This example synchronizes a pull subscription to a merge publication using Web synchronization.</span></span> <span data-ttu-id="2fddf-217">La sottoscrizione è stata creata senza il processo dell'agente e i metadati correlati, pertanto l'agente deve essere avviato in modo sincrono e vengono fornite informazioni aggiuntive sulla sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="2fddf-217">The subscription was created without the agent job and related subscription metadata, so the agent must be started synchronously and additional subscription information is supplied.</span></span>  
  
 [!code-csharp[HowTo#rmo_SyncMergePullSub_NoJobWebSync](../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_syncmergepullsub_nojobwebsync)]  
  
 [!code-vb[HowTo#rmo_vb_SyncMergePullSub_NoJobWebSync](../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_syncmergepullsub_nojobwebsync)]  
  
## <a name="see-also"></a><span data-ttu-id="2fddf-218">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2fddf-218">See Also</span></span>  
 <span data-ttu-id="2fddf-219">[Sincronizzare i dati](synchronize-data.md) </span><span class="sxs-lookup"><span data-stu-id="2fddf-219">[Synchronize Data](synchronize-data.md) </span></span>  
 <span data-ttu-id="2fddf-220">[Create a Pull Subscription](create-a-pull-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="2fddf-220">[Create a Pull Subscription](create-a-pull-subscription.md) </span></span>  
 [<span data-ttu-id="2fddf-221">Procedure consigliate per la sicurezza della replica</span><span class="sxs-lookup"><span data-stu-id="2fddf-221">Replication Security Best Practices</span></span>](security/replication-security-best-practices.md)  
  
  
