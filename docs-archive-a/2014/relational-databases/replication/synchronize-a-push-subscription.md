---
title: Sincronizzare una sottoscrizione push | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- synchronization [SQL Server replication], push subscriptions
- subscriptions [SQL Server replication], push
- push subscriptions [SQL Server replication], synchronizing
ms.assetid: 0cfa7ae5-91d3-4a4f-9edf-a852d45783b5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5fb2f7bd961748272d6cd67e3412b09d9370a6f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716239"
---
# <a name="synchronize-a-push-subscription"></a><span data-ttu-id="ef79c-102">Sincronizzazione di una sottoscrizione push</span><span class="sxs-lookup"><span data-stu-id="ef79c-102">Synchronize a Push Subscription</span></span>
  <span data-ttu-id="ef79c-103">In questo argomento viene descritto come sincronizzare una sottoscrizione push in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [agenti di replica](agents/replication-agents-overview.md)o RMO (Replication Management Objects).</span><span class="sxs-lookup"><span data-stu-id="ef79c-103">This topic describes how to synchronize a push subscription in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [replication agents](agents/replication-agents-overview.md), or Replication Management Objects (RMO).</span></span>  
  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="ef79c-104">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ef79c-104">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="ef79c-105">Le sottoscrizioni vengono sincronizzate dall'agente di distribuzione, per la replica snapshot e transazionale, o dall'agente di merge, per la replica di tipo merge.</span><span class="sxs-lookup"><span data-stu-id="ef79c-105">Subscriptions are synchronized by the Distribution Agent (for snapshot and transactional replication) or the Merge Agent (for merge replication).</span></span> <span data-ttu-id="ef79c-106">Gli agenti possono essere in esecuzione continuamente, essere in esecuzione su richiesta o essere in esecuzione su una pianificazione.</span><span class="sxs-lookup"><span data-stu-id="ef79c-106">Agents can run continuously, run on demand, or run on a schedule.</span></span> <span data-ttu-id="ef79c-107">Per altre informazioni sull'impostazione delle pianificazioni della sincronizzazione, vedere [Specificare le pianificazioni della sincronizzazione](specify-synchronization-schedules.md).</span><span class="sxs-lookup"><span data-stu-id="ef79c-107">For more information about specifying synchronization schedules, see [Specify Synchronization Schedules](specify-synchronization-schedules.md).</span></span>  
  
 <span data-ttu-id="ef79c-108">Una sottoscrizione può essere sincronizzata su richiesta dalle cartelle **Pubblicazioni locali** e **Sottoscrizioni locali** in [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] e dalla scheda **Tutte le sottoscrizioni** in Monitoraggio replica.</span><span class="sxs-lookup"><span data-stu-id="ef79c-108">Synchronize a subscription on demand from the **Local Publications** and **Local Subscriptions** folders in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and the **All Subscriptions** tab in Replication Monitor.</span></span> <span data-ttu-id="ef79c-109">Le sottoscrizioni a pubblicazioni Oracle non possono essere sincronizzate su richiesta dal Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="ef79c-109">Subscriptions to Oracle publications cannot be synchronized on demand from the Subscriber.</span></span> <span data-ttu-id="ef79c-110">Per informazioni sull'avvio di Monitoraggio replica, vedere [Avviare Monitoraggio replica](monitor/start-the-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="ef79c-110">For information about starting Replication Monitor, see [Start the Replication Monitor](monitor/start-the-replication-monitor.md).</span></span>  
  
#### <a name="to-synchronize-a-push-subscription-on-demand-in-management-studio-at-the-publisher"></a><span data-ttu-id="ef79c-111">Per sincronizzare una sottoscrizione push su richiesta in Management Studio (nel server di pubblicazione)</span><span class="sxs-lookup"><span data-stu-id="ef79c-111">To synchronize a push subscription on demand in Management Studio (at the Publisher)</span></span>  
  
1.  <span data-ttu-id="ef79c-112">Connettersi al server di pubblicazione in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]e quindi espandere il nodo del server.</span><span class="sxs-lookup"><span data-stu-id="ef79c-112">Connect to the Publisher in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="ef79c-113">Espandere la cartella **Replica** e quindi la cartella **Pubblicazioni locali** .</span><span class="sxs-lookup"><span data-stu-id="ef79c-113">Expand the **Replication** folder, and then expand the **Local Publications** folder.</span></span>  
  
3.  <span data-ttu-id="ef79c-114">Espandere la pubblicazione per cui sincronizzare le sottoscrizioni.</span><span class="sxs-lookup"><span data-stu-id="ef79c-114">Expand the publication for which you want to synchronize subscriptions.</span></span>  
  
4.  <span data-ttu-id="ef79c-115">Fare clic con il pulsante destro del mouse sulla sottoscrizione che si desidera sincronizzare e quindi scegliere **Visualizza stato sincronizzazione**.</span><span class="sxs-lookup"><span data-stu-id="ef79c-115">Right-click the subscription you want to synchronize, and then click **View Synchronization Status**.</span></span>  
  
5.  <span data-ttu-id="ef79c-116">Nella finestra di dialogo **Visualizza stato sincronizzazione - \<Subscriber>:\<SubscriptionDatabase>** fare clic su **Avvia**.</span><span class="sxs-lookup"><span data-stu-id="ef79c-116">In the **View Synchronization Status - \<Subscriber>:\<SubscriptionDatabase>** dialog box, click **Start**.</span></span> <span data-ttu-id="ef79c-117">Al termine della sincronizzazione verrà visualizzato il messaggio **Sincronizzazione completata** .</span><span class="sxs-lookup"><span data-stu-id="ef79c-117">When synchronization is complete, the message **Synchronization completed** is displayed.</span></span>  
  
6.  <span data-ttu-id="ef79c-118">Fare clic su **Close**.</span><span class="sxs-lookup"><span data-stu-id="ef79c-118">Click **Close**.</span></span>  
  
#### <a name="to-synchronize-a-push-subscription-on-demand-in-management-studio-at-the-subscriber"></a><span data-ttu-id="ef79c-119">Per sincronizzare una sottoscrizione push su richiesta in Management Studio (nel Sottoscrittore)</span><span class="sxs-lookup"><span data-stu-id="ef79c-119">To synchronize a push subscription on demand in Management Studio (at the Subscriber)</span></span>  
  
1.  <span data-ttu-id="ef79c-120">Connettersi al Sottoscrittore in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]e quindi espandere il nodo del server.</span><span class="sxs-lookup"><span data-stu-id="ef79c-120">Connect to the Subscriber in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="ef79c-121">Espandere la cartella **Replica** e quindi la cartella **Sottoscrizioni locali** .</span><span class="sxs-lookup"><span data-stu-id="ef79c-121">Expand the **Replication** folder, and then expand the **Local Subscriptions** folder.</span></span>  
  
3.  <span data-ttu-id="ef79c-122">Fare clic con il pulsante destro del mouse sulla sottoscrizione che si desidera sincronizzare e quindi scegliere **Visualizza stato sincronizzazione**.</span><span class="sxs-lookup"><span data-stu-id="ef79c-122">Right-click the subscription you want to synchronize, and then click **View Synchronization Status**.</span></span>  
  
4.  <span data-ttu-id="ef79c-123">Viene visualizzato un messaggio in cui si chiede di stabilire una connessione al server di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="ef79c-123">A message is displayed about establishing a connection to the Distributor.</span></span> <span data-ttu-id="ef79c-124">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="ef79c-124">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="ef79c-125">Nella finestra di dialogo **Visualizza stato sincronizzazione - \<Subscriber>:\<SubscriptionDatabase>** fare clic su **Avvia**.</span><span class="sxs-lookup"><span data-stu-id="ef79c-125">In the **View Synchronization Status - \<Subscriber>:\<SubscriptionDatabase>** dialog box, click **Start**.</span></span> <span data-ttu-id="ef79c-126">Al termine della sincronizzazione verrà visualizzato il messaggio **Sincronizzazione completata** .</span><span class="sxs-lookup"><span data-stu-id="ef79c-126">When synchronization is complete, the message **Synchronization completed** is displayed.</span></span>  
  
6.  <span data-ttu-id="ef79c-127">Fare clic su **Close**.</span><span class="sxs-lookup"><span data-stu-id="ef79c-127">Click **Close**.</span></span>  
  
#### <a name="to-synchronize-a-push-subscription-on-demand-in-replication-monitor"></a><span data-ttu-id="ef79c-128">Per sincronizzare una sottoscrizione push su richiesta in Monitoraggio replica</span><span class="sxs-lookup"><span data-stu-id="ef79c-128">To synchronize a push subscription on demand in Replication Monitor</span></span>  
  
1.  <span data-ttu-id="ef79c-129">In Monitoraggio replica espandere un gruppo di server di pubblicazione nel riquadro di sinistra, espandere un server di pubblicazione e quindi fare clic su una pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="ef79c-129">In Replication Monitor, expand a Publisher group in the left pane, expand a Publisher, and then click a publication.</span></span>  
  
2.  <span data-ttu-id="ef79c-130">Fare clic sulla scheda **Tutte le sottoscrizioni** .</span><span class="sxs-lookup"><span data-stu-id="ef79c-130">Click the **All Subscriptions** tab.</span></span>  
  
3.  <span data-ttu-id="ef79c-131">Fare clic con il pulsante destro del mouse sulla sottoscrizione che si desidera sincronizzare e quindi scegliere **Avvia sincronizzazione**.</span><span class="sxs-lookup"><span data-stu-id="ef79c-131">Right-click the subscription you want to synchronize, and then click **Start Synchronizing**.</span></span>  
  
4.  <span data-ttu-id="ef79c-132">Per visualizzare lo stato della sincronizzazione, fare clic con il pulsante destro del mouse sulla sottoscrizione e quindi scegliere **Visualizza dettagli**.</span><span class="sxs-lookup"><span data-stu-id="ef79c-132">To view synchronization progress, right-click the subscription, and then click **View Details**.</span></span>  
  
##  <a name="using-replication-agents"></a><a name="ReplProg"></a> <span data-ttu-id="ef79c-133">Utilizzo degli agenti di replica</span><span class="sxs-lookup"><span data-stu-id="ef79c-133">Using Replication Agents</span></span>  
 <span data-ttu-id="ef79c-134">Le sottoscrizioni push possono essere sincronizzate a livello di programmazione e su richiesta richiamando il file eseguibile dell'agente di replica appropriato dal prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="ef79c-134">Push subscriptions can be synchronized programmatically and on-demand by invoking the appropriate replication agent executable file from the command prompt.</span></span> <span data-ttu-id="ef79c-135">Il file eseguibile dell'agente di replica richiamato dipenderà dal tipo di pubblicazione a cui appartiene la sottoscrizione push.</span><span class="sxs-lookup"><span data-stu-id="ef79c-135">The replication agent executable file that is invoked will depend on the type of publication to which the push subscription belongs.</span></span>  
  
#### <a name="to-start-the-distribution-agent-to-synchronize-a-push-subscription-to-a-transactional-publication"></a><span data-ttu-id="ef79c-136">Per avviare l'agente di distribuzione per sincronizzare una sottoscrizione push di una pubblicazione transazionale</span><span class="sxs-lookup"><span data-stu-id="ef79c-136">To start the Distribution Agent to synchronize a push subscription to a transactional publication</span></span>  
  
1.  <span data-ttu-id="ef79c-137">Eseguire **distrib.exe**dal prompt dei comandi o in un file batch nel server di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="ef79c-137">From the command prompt or in a batch file at the Distributor, execute **distrib.exe**.</span></span> <span data-ttu-id="ef79c-138">Specificare gli argomenti della riga di comando seguenti:</span><span class="sxs-lookup"><span data-stu-id="ef79c-138">Specify the following command-line arguments:</span></span>  
  
    -   <span data-ttu-id="ef79c-139">**-Publisher**</span><span class="sxs-lookup"><span data-stu-id="ef79c-139">**-Publisher**</span></span>  
  
    -   <span data-ttu-id="ef79c-140">**-PublisherDB**</span><span class="sxs-lookup"><span data-stu-id="ef79c-140">**-PublisherDB**</span></span>  
  
    -   <span data-ttu-id="ef79c-141">**-Distributor**</span><span class="sxs-lookup"><span data-stu-id="ef79c-141">**-Distributor**</span></span>  
  
    -   <span data-ttu-id="ef79c-142">**-Subscriber**</span><span class="sxs-lookup"><span data-stu-id="ef79c-142">**-Subscriber**</span></span>  
  
    -   <span data-ttu-id="ef79c-143">**-SubscriberDB**</span><span class="sxs-lookup"><span data-stu-id="ef79c-143">**-SubscriberDB**</span></span>  
  
    -   <span data-ttu-id="ef79c-144">**-SubscriptionType = 0**</span><span class="sxs-lookup"><span data-stu-id="ef79c-144">**-SubscriptionType = 0**</span></span>  
  
     <span data-ttu-id="ef79c-145">Se si usano l'autenticazione di SQL Server, è inoltre necessario specificare gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="ef79c-145">If you are using SQL Server Authentication, you must also specify the following arguments:</span></span>  
  
    -   <span data-ttu-id="ef79c-146">**-DistributorLogin**</span><span class="sxs-lookup"><span data-stu-id="ef79c-146">**-DistributorLogin**</span></span>  
  
    -   <span data-ttu-id="ef79c-147">**-DistributorPassword**</span><span class="sxs-lookup"><span data-stu-id="ef79c-147">**-DistributorPassword**</span></span>  
  
    -   <span data-ttu-id="ef79c-148">**-DistributorSecurityMode = 0**</span><span class="sxs-lookup"><span data-stu-id="ef79c-148">**-DistributorSecurityMode = 0**</span></span>  
  
    -   <span data-ttu-id="ef79c-149">**-PublisherLogin**</span><span class="sxs-lookup"><span data-stu-id="ef79c-149">**-PublisherLogin**</span></span>  
  
    -   <span data-ttu-id="ef79c-150">**-PublisherPassword**</span><span class="sxs-lookup"><span data-stu-id="ef79c-150">**-PublisherPassword**</span></span>  
  
    -   <span data-ttu-id="ef79c-151">**-PublisherSecurityMode = 0**</span><span class="sxs-lookup"><span data-stu-id="ef79c-151">**-PublisherSecurityMode = 0**</span></span>  
  
    -   <span data-ttu-id="ef79c-152">**-SubscriberLogin**</span><span class="sxs-lookup"><span data-stu-id="ef79c-152">**-SubscriberLogin**</span></span>  
  
    -   <span data-ttu-id="ef79c-153">**-SubscriberPassword**</span><span class="sxs-lookup"><span data-stu-id="ef79c-153">**-SubscriberPassword**</span></span>  
  
    -   <span data-ttu-id="ef79c-154">**-SubscriberSecurityMode = 0**</span><span class="sxs-lookup"><span data-stu-id="ef79c-154">**-SubscriberSecurityMode = 0**</span></span>  
  
        > [!IMPORTANT]  
        >  [!INCLUDE[ssNoteWinAuthentication](../../includes/ssnotewinauthentication-md.md)]  
  
#### <a name="to-start-the-merge-agent-to-synchronize-a-push-subscription-to-a-merge-publication"></a><span data-ttu-id="ef79c-155">Per avviare l'agente di merge per sincronizzare una sottoscrizione push di una pubblicazione di tipo merge</span><span class="sxs-lookup"><span data-stu-id="ef79c-155">To start the Merge Agent to synchronize a push subscription to a merge publication</span></span>  
  
1.  <span data-ttu-id="ef79c-156">Eseguire **replmerg.exe**dal prompt dei comandi o in un file batch nel server di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="ef79c-156">From the command prompt or in a batch file at the Distributor, execute **replmerg.exe**.</span></span> <span data-ttu-id="ef79c-157">Specificare gli argomenti della riga di comando seguenti:</span><span class="sxs-lookup"><span data-stu-id="ef79c-157">Specify the following command-line arguments:</span></span>  
  
    -   <span data-ttu-id="ef79c-158">**-Publisher**</span><span class="sxs-lookup"><span data-stu-id="ef79c-158">**-Publisher**</span></span>  
  
    -   <span data-ttu-id="ef79c-159">**-PublisherDB**</span><span class="sxs-lookup"><span data-stu-id="ef79c-159">**-PublisherDB**</span></span>  
  
    -   <span data-ttu-id="ef79c-160">**-Publication**</span><span class="sxs-lookup"><span data-stu-id="ef79c-160">**-Publication**</span></span>  
  
    -   <span data-ttu-id="ef79c-161">**-Distributor**</span><span class="sxs-lookup"><span data-stu-id="ef79c-161">**-Distributor**</span></span>  
  
    -   <span data-ttu-id="ef79c-162">**-Subscriber**</span><span class="sxs-lookup"><span data-stu-id="ef79c-162">**-Subscriber**</span></span>  
  
    -   <span data-ttu-id="ef79c-163">**-SubscriberDB**</span><span class="sxs-lookup"><span data-stu-id="ef79c-163">**-SubscriberDB**</span></span>  
  
    -   <span data-ttu-id="ef79c-164">**-SubscriptionType = 0**</span><span class="sxs-lookup"><span data-stu-id="ef79c-164">**-SubscriptionType = 0**</span></span>  
  
     <span data-ttu-id="ef79c-165">Se si usano l'autenticazione di SQL Server, è inoltre necessario specificare gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="ef79c-165">If you are using SQL Server Authentication, you must also specify the following arguments:</span></span>  
  
    -   <span data-ttu-id="ef79c-166">**-DistributorLogin**</span><span class="sxs-lookup"><span data-stu-id="ef79c-166">**-DistributorLogin**</span></span>  
  
    -   <span data-ttu-id="ef79c-167">**-DistributorPassword**</span><span class="sxs-lookup"><span data-stu-id="ef79c-167">**-DistributorPassword**</span></span>  
  
    -   <span data-ttu-id="ef79c-168">**-DistributorSecurityMode = 0**</span><span class="sxs-lookup"><span data-stu-id="ef79c-168">**-DistributorSecurityMode = 0**</span></span>  
  
    -   <span data-ttu-id="ef79c-169">**-PublisherLogin**</span><span class="sxs-lookup"><span data-stu-id="ef79c-169">**-PublisherLogin**</span></span>  
  
    -   <span data-ttu-id="ef79c-170">**-PublisherPassword**</span><span class="sxs-lookup"><span data-stu-id="ef79c-170">**-PublisherPassword**</span></span>  
  
    -   <span data-ttu-id="ef79c-171">**-PublisherSecurityMode = 0**</span><span class="sxs-lookup"><span data-stu-id="ef79c-171">**-PublisherSecurityMode = 0**</span></span>  
  
    -   <span data-ttu-id="ef79c-172">**-SubscriberLogin**</span><span class="sxs-lookup"><span data-stu-id="ef79c-172">**-SubscriberLogin**</span></span>  
  
    -   <span data-ttu-id="ef79c-173">**-SubscriberPassword**</span><span class="sxs-lookup"><span data-stu-id="ef79c-173">**-SubscriberPassword**</span></span>  
  
    -   <span data-ttu-id="ef79c-174">**-SubscriberSecurityMode = 0**</span><span class="sxs-lookup"><span data-stu-id="ef79c-174">**-SubscriberSecurityMode = 0**</span></span>  
  
        > [!IMPORTANT]  
        >  [!INCLUDE[ssNoteWinAuthentication](../../includes/ssnotewinauthentication-md.md)]  
  
###  <a name="examples-replication-agents"></a><a name="TsqlExample"></a> <span data-ttu-id="ef79c-175">Esempi (agenti di replica)</span><span class="sxs-lookup"><span data-stu-id="ef79c-175">Examples (Replication Agents)</span></span>  
 <span data-ttu-id="ef79c-176">Nell'esempio seguente viene avviato l'agente di distribuzione per sincronizzare una sottoscrizione push.</span><span class="sxs-lookup"><span data-stu-id="ef79c-176">The following example starts the Distribution Agent to synchronize a push subscription.</span></span>  
  
 
```
REM -- Declare the variables.  
SET Publisher=%instancename%  
SET Subscriber=%instancename%  
SET PublicationDB=AdventureWorks2012  
SET SubscriptionDB=AdventureWorks2012Replica   
SET Publication=AdvWorksProductsTran  
  
REM -- Start the Distribution Agent with four subscription streams.  
REM -- The following command must be supplied without line breaks.  
"C:\Program Files\Microsoft SQL Server\120\COM\DISTRIB.EXE" -Subscriber %Subscriber%   
-SubscriberDB %SubscriptionDB% -SubscriberSecurityMode 1 -Publication %Publication%   
-Publisher %Publisher% -PublisherDB %PublicationDB% -Distributor %Publisher%   
-DistributorSecurityMode 1 -Continuous -SubscriptionType 0 -SubscriptionStreams 4
```
  
 <span data-ttu-id="ef79c-177">Nell'esempio seguente viene avviato l'agente di merge per sincronizzare una sottoscrizione push.</span><span class="sxs-lookup"><span data-stu-id="ef79c-177">The following example starts the Merge Agent to synchronize a push subscription.</span></span>  

```
REM -- Declare the variables.  
SET Publisher=%instancename%  
SET Subscriber=%instancename%  
SET PublicationDB=AdventureWorks2012  
SET SubscriptionDB=AdventureWorks2012Replica   
SET Publication=AdvWorksSalesOrdersMerge  
  
REM -- Start the Merge Agent.  
REM -- The following command must be supplied without line breaks.  
"C:\Program Files\Microsoft SQL Server\120\COM\REPLMERG.EXE"  -Publisher %Publisher%   
-Subscriber  %Subscriber%  -Distributor %Publisher% -PublisherDB  %PublicationDB%   
-SubscriberDB %SubscriptionDB% -Publication %Publication% -PublisherSecurityMode 1   
-OutputVerboseLevel 3  -Output -SubscriberSecurityMode 1  -SubscriptionType 0   
-DistributorSecurityMode 1
```
  
  
##  <a name="using-replication-management-objects-rmo"></a><a name="RMOProcedure"></a> <span data-ttu-id="ef79c-178">Utilizzo di RMO (Replication Management Objects)</span><span class="sxs-lookup"><span data-stu-id="ef79c-178">Using Replication Management Objects (RMO)</span></span>  
 <span data-ttu-id="ef79c-179">È possibile sincronizzare le sottoscrizioni push a livello di programmazione tramite gli oggetti RMO (Replication Management Objects) e l'accesso tramite codice gestito alle funzionalità dell'agente di replica.</span><span class="sxs-lookup"><span data-stu-id="ef79c-179">You can synchronize push subscriptions programmatically by using Replication Management Objects (RMO) and managed code access to replication agent functionalities.</span></span> <span data-ttu-id="ef79c-180">Le classi usate per la sincronizzazione di una sottoscrizione push dipendono dal tipo di pubblicazione a cui appartiene la sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="ef79c-180">The classes that you use to synchronize a push subscription depend on the type of publication to which the subscription belongs.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ef79c-181">Se si desidera avviare una sincronizzazione eseguita in modo autonomo senza effetti sull'applicazione, avviare l'agente in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="ef79c-181">If you want to start a synchronization that runs autonomously without affecting your application, start the agent asynchronously.</span></span> <span data-ttu-id="ef79c-182">Se invece si desidera monitorare i risultati della sincronizzazione e ricevere callback dall'agente durante il processo di sincronizzazione (ad esempio per la visualizzazione di una barra di stato) è necessario avviare l'agente in modo sincrono.</span><span class="sxs-lookup"><span data-stu-id="ef79c-182">However, if you want to monitor the outcome of the synchronization and receive callbacks from the agent during the synchronization process (for example, if you want to display a progress bar), you should start the agent synchronously.</span></span> <span data-ttu-id="ef79c-183">Per i sottoscrittori di [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssExpressEd2005](../../includes/ssexpressed2005-md.md)] , l'agente deve essere avviato in modo sincrono.</span><span class="sxs-lookup"><span data-stu-id="ef79c-183">For [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssExpressEd2005](../../includes/ssexpressed2005-md.md)] Subscribers, you must start the agent synchronously.</span></span>  
  
#### <a name="to-synchronize-a-push-subscription-to-a-snapshot-or-transactional-publication"></a><span data-ttu-id="ef79c-184">Per sincronizzare una sottoscrizione push di una pubblicazione snapshot o transazionale</span><span class="sxs-lookup"><span data-stu-id="ef79c-184">To synchronize a push subscription to a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="ef79c-185">Creare una connessione al server di distribuzione tramite la classe <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="ef79c-185">Create a connection to the Distributor by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="ef79c-186">Creare un'istanza della classe <xref:Microsoft.SqlServer.Replication.TransSubscription> e impostare le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="ef79c-186">Create an instance of the <xref:Microsoft.SqlServer.Replication.TransSubscription> class and set the following properties:</span></span>  
  
    -   <span data-ttu-id="ef79c-187">Nome del database di pubblicazione per <xref:Microsoft.SqlServer.Replication.Subscription.DatabaseName%2A>.</span><span class="sxs-lookup"><span data-stu-id="ef79c-187">The publication database name for <xref:Microsoft.SqlServer.Replication.Subscription.DatabaseName%2A>.</span></span>  
  
    -   <span data-ttu-id="ef79c-188">Nome della pubblicazione a cui appartiene la sottoscrizione per <xref:Microsoft.SqlServer.Replication.Subscription.PublicationName%2A>.</span><span class="sxs-lookup"><span data-stu-id="ef79c-188">The name of the publication to which the subscription belongs for <xref:Microsoft.SqlServer.Replication.Subscription.PublicationName%2A>.</span></span>  
  
    -   <span data-ttu-id="ef79c-189">Nome del database di sottoscrizione per <xref:Microsoft.SqlServer.Replication.Subscription.SubscriptionDBName%2A>.</span><span class="sxs-lookup"><span data-stu-id="ef79c-189">The name of the subscription database for <xref:Microsoft.SqlServer.Replication.Subscription.SubscriptionDBName%2A>.</span></span>  
  
    -   <span data-ttu-id="ef79c-190">Nome del Sottoscrittore per <xref:Microsoft.SqlServer.Replication.Subscription.SubscriberName%2A>.</span><span class="sxs-lookup"><span data-stu-id="ef79c-190">The name of the Subscriber for <xref:Microsoft.SqlServer.Replication.Subscription.SubscriberName%2A>.</span></span>  
  
    -   <span data-ttu-id="ef79c-191">La connessione creata nel passaggio 1 per <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A>.</span><span class="sxs-lookup"><span data-stu-id="ef79c-191">The connection created in step 1 for <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A>.</span></span>  
  
3.  <span data-ttu-id="ef79c-192">Chiamare il metodo <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> per recuperare le proprietà rimanenti della sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="ef79c-192">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> method to get the remaining subscription properties.</span></span> <span data-ttu-id="ef79c-193">Se il metodo restituisce `false`, verificare che la sottoscrizione esista.</span><span class="sxs-lookup"><span data-stu-id="ef79c-193">If this method returns `false`, verify that the subscription exists.</span></span>  
  
4.  <span data-ttu-id="ef79c-194">Avviare l'agente di distribuzione nel server di distribuzione in uno dei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="ef79c-194">Start the Distribution Agent at the Distributor in one of the following ways:</span></span>  
  
    -   <span data-ttu-id="ef79c-195">Chiamare il metodo <xref:Microsoft.SqlServer.Replication.TransSubscription.SynchronizeWithJob%2A> nell'istanza di <xref:Microsoft.SqlServer.Replication.TransSubscription> creata al passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="ef79c-195">Call the <xref:Microsoft.SqlServer.Replication.TransSubscription.SynchronizeWithJob%2A> method on the instance of <xref:Microsoft.SqlServer.Replication.TransSubscription> from step 2.</span></span> <span data-ttu-id="ef79c-196">Questo metodo consente di avviare l'agente di distribuzione in modo asincrono e il controllo viene restituito immediatamente all'applicazione durante l'esecuzione del processo dell'agente.</span><span class="sxs-lookup"><span data-stu-id="ef79c-196">This method starts the Distribution Agent asynchronously, and control immediately returns to your application while the agent job is running.</span></span> <span data-ttu-id="ef79c-197">Non è possibile chiamare questo metodo se la sottoscrizione è stata creata con il valore `false` per <xref:Microsoft.SqlServer.Replication.Subscription.CreateSyncAgentByDefault%2A>.</span><span class="sxs-lookup"><span data-stu-id="ef79c-197">You cannot call this method if the subscription was created with a value of `false` for <xref:Microsoft.SqlServer.Replication.Subscription.CreateSyncAgentByDefault%2A>.</span></span>  
  
    -   <span data-ttu-id="ef79c-198">Recuperare un'istanza della classe <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent> dalla proprietà <xref:Microsoft.SqlServer.Replication.TransSubscription.SynchronizationAgent%2A> e chiamare il metodo <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.Synchronize%2A> .</span><span class="sxs-lookup"><span data-stu-id="ef79c-198">Obtain an instance of the <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent> class from the <xref:Microsoft.SqlServer.Replication.TransSubscription.SynchronizationAgent%2A> property, and call the <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.Synchronize%2A> method.</span></span> <span data-ttu-id="ef79c-199">Questo metodo avvia l'agente in modo sincrono e il controllo rimane al processo dell'agente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="ef79c-199">This method starts the agent synchronously, and control remains with the running agent job.</span></span> <span data-ttu-id="ef79c-200">Nella modalità sincrona è possibile gestire l'evento <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.Status> durante l'esecuzione dell'agente.</span><span class="sxs-lookup"><span data-stu-id="ef79c-200">During synchronous execution you can handle the <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.Status> event while the agent is running.</span></span>  
  
#### <a name="to-synchronize-a-push-subscription-to-a-merge-publication"></a><span data-ttu-id="ef79c-201">Per sincronizzare una sottoscrizione push di una pubblicazione di tipo merge</span><span class="sxs-lookup"><span data-stu-id="ef79c-201">To synchronize a push subscription to a merge publication</span></span>  
  
1.  <span data-ttu-id="ef79c-202">Creare una connessione al server di distribuzione tramite la classe <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="ef79c-202">Create a connection to the Distributor by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="ef79c-203">Creare un'istanza della classe <xref:Microsoft.SqlServer.Replication.MergeSubscription> e impostare le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="ef79c-203">Create an instance of the <xref:Microsoft.SqlServer.Replication.MergeSubscription> class, and set the following properties:</span></span>  
  
    -   <span data-ttu-id="ef79c-204">Nome del database di pubblicazione per <xref:Microsoft.SqlServer.Replication.Subscription.DatabaseName%2A>.</span><span class="sxs-lookup"><span data-stu-id="ef79c-204">The publication database name for <xref:Microsoft.SqlServer.Replication.Subscription.DatabaseName%2A>.</span></span>  
  
    -   <span data-ttu-id="ef79c-205">Nome della pubblicazione a cui appartiene la sottoscrizione per <xref:Microsoft.SqlServer.Replication.Subscription.PublicationName%2A>.</span><span class="sxs-lookup"><span data-stu-id="ef79c-205">The name of the publication to which the subscription belongs for <xref:Microsoft.SqlServer.Replication.Subscription.PublicationName%2A>.</span></span>  
  
    -   <span data-ttu-id="ef79c-206">Nome del database di sottoscrizione per <xref:Microsoft.SqlServer.Replication.Subscription.SubscriptionDBName%2A>.</span><span class="sxs-lookup"><span data-stu-id="ef79c-206">The name of the subscription database for <xref:Microsoft.SqlServer.Replication.Subscription.SubscriptionDBName%2A>.</span></span>  
  
    -   <span data-ttu-id="ef79c-207">Nome del Sottoscrittore per <xref:Microsoft.SqlServer.Replication.Subscription.SubscriberName%2A>.</span><span class="sxs-lookup"><span data-stu-id="ef79c-207">The name of the Subscriber for <xref:Microsoft.SqlServer.Replication.Subscription.SubscriberName%2A>.</span></span>  
  
    -   <span data-ttu-id="ef79c-208">La connessione creata nel passaggio 1 per <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A>.</span><span class="sxs-lookup"><span data-stu-id="ef79c-208">The connection created in step 1 for <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A>.</span></span>  
  
3.  <span data-ttu-id="ef79c-209">Chiamare il metodo <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> per recuperare le proprietà rimanenti della sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="ef79c-209">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> method to get the remaining subscription properties.</span></span> <span data-ttu-id="ef79c-210">Se il metodo restituisce `false`, verificare che la sottoscrizione esista.</span><span class="sxs-lookup"><span data-stu-id="ef79c-210">If this method returns `false`, verify that the subscription exists.</span></span>  
  
4.  <span data-ttu-id="ef79c-211">Avviare l'agente di merge nel server di distribuzione in uno dei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="ef79c-211">Start the Merge Agent at the Distributor in one of the following ways:</span></span>  
  
    -   <span data-ttu-id="ef79c-212">Chiamare il metodo <xref:Microsoft.SqlServer.Replication.MergeSubscription.SynchronizeWithJob%2A> nell'istanza di <xref:Microsoft.SqlServer.Replication.MergeSubscription> creata al passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="ef79c-212">Call the <xref:Microsoft.SqlServer.Replication.MergeSubscription.SynchronizeWithJob%2A> method on the instance of <xref:Microsoft.SqlServer.Replication.MergeSubscription> from step 2.</span></span> <span data-ttu-id="ef79c-213">Questo metodo consente di avviare l'agente di merge in modo asincrono e il controllo viene restituito immediatamente all'applicazione durante l'esecuzione del processo dell'agente.</span><span class="sxs-lookup"><span data-stu-id="ef79c-213">This method starts the Merge Agent asynchronously, and control immediately returns to your application while the agent job is running.</span></span> <span data-ttu-id="ef79c-214">Non è possibile chiamare questo metodo se la sottoscrizione è stata creata con il valore `false` per <xref:Microsoft.SqlServer.Replication.Subscription.CreateSyncAgentByDefault%2A>.</span><span class="sxs-lookup"><span data-stu-id="ef79c-214">You cannot call this method if the subscription was created with a value of `false` for <xref:Microsoft.SqlServer.Replication.Subscription.CreateSyncAgentByDefault%2A>.</span></span>  
  
    -   <span data-ttu-id="ef79c-215">Recuperare un'istanza della classe <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent> dalla proprietà <xref:Microsoft.SqlServer.Replication.MergeSubscription.SynchronizationAgent%2A> e chiamare il metodo <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.Synchronize%2A> .</span><span class="sxs-lookup"><span data-stu-id="ef79c-215">Obtain an instance of the <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent> class from the <xref:Microsoft.SqlServer.Replication.MergeSubscription.SynchronizationAgent%2A> property, and call the <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.Synchronize%2A> method.</span></span> <span data-ttu-id="ef79c-216">Questo metodo avvia l'agente di merge in modo sincrono e il controllo rimane al processo dell'agente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="ef79c-216">This method starts the Merge Agent synchronously, and control remains with the running agent job.</span></span> <span data-ttu-id="ef79c-217">Nella modalità sincrona è possibile gestire l'evento <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.Status> durante l'esecuzione dell'agente.</span><span class="sxs-lookup"><span data-stu-id="ef79c-217">During synchronous execution, you can handle the <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.Status> event while the agent is running.</span></span>  
  
###  <a name="examples-rmo"></a><a name="PShellExample"></a> <span data-ttu-id="ef79c-218">Esempi (RMO)</span><span class="sxs-lookup"><span data-stu-id="ef79c-218">Examples (RMO)</span></span>  
 <span data-ttu-id="ef79c-219">In questo esempio viene illustrata la sincronizzazione di una sottoscrizione push di una pubblicazione transazionale, con avvio asincrono dell'agente usando il processo dell'agente.</span><span class="sxs-lookup"><span data-stu-id="ef79c-219">This example synchronizes a push subscription to a transactional publication, where the agent is started asynchronously using the agent job.</span></span>  
  
 [!code-csharp[HowTo#rmo_SyncTranPushSub_WithJob](../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_synctranpushsub_withjob)]  
  
 [!code-vb[HowTo#rmo_vb_SyncTranPushSub_WithJob](../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_synctranpushsub_withjob)]  
  
 <span data-ttu-id="ef79c-220">In questo esempio viene illustrata la sincronizzazione di una sottoscrizione push di una pubblicazione transazionale, con avvio sincrono dell'agente.</span><span class="sxs-lookup"><span data-stu-id="ef79c-220">This example synchronizes a push subscription to a transactional publication, where the agent is started synchronously.</span></span>  
  
 [!code-csharp[HowTo#rmo_SyncTranPushSub](../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_synctranpushsub)]  
  
 [!code-vb[HowTo#rmo_vb_SyncTranPushSub](../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_synctranpushsub)]  
  
 <span data-ttu-id="ef79c-221">In questo esempio viene illustrata la sincronizzazione di una sottoscrizione push di una pubblicazione di tipo merge, con avvio asincrono dell'agente usando il processo dell'agente.</span><span class="sxs-lookup"><span data-stu-id="ef79c-221">This example synchronizes a push subscription to a merge publication, where the agent is started asynchronously using the agent job.</span></span>  
  
 [!code-csharp[HowTo#rmo_SyncMergePushSub_WithJob](../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_syncmergepushsub_withjob)]  
  
 [!code-vb[HowTo#rmo_vb_SyncMergePushSub_WithJob](../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_syncmergepushsub_withjob)]  
  
 <span data-ttu-id="ef79c-222">In questo esempio viene illustrata la sincronizzazione di una sottoscrizione push di una pubblicazione di tipo merge, con avvio sincrono dell'agente.</span><span class="sxs-lookup"><span data-stu-id="ef79c-222">This example synchronizes a push subscription to a merge publication, where the agent is started synchronously.</span></span>  
  
 [!code-csharp[HowTo#rmo_SyncMergePushSub](../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_syncmergepushsub)]  
  
 [!code-vb[HowTo#rmo_vb_SyncMergePushSub](../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_syncmergepushsub)]  
  
## <a name="see-also"></a><span data-ttu-id="ef79c-223">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ef79c-223">See Also</span></span>  
 <span data-ttu-id="ef79c-224">[Replication Management Objects Concepts](concepts/replication-management-objects-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="ef79c-224">[Replication Management Objects Concepts](concepts/replication-management-objects-concepts.md) </span></span>  
 <span data-ttu-id="ef79c-225">[Sincronizzare i dati](synchronize-data.md) </span><span class="sxs-lookup"><span data-stu-id="ef79c-225">[Synchronize Data](synchronize-data.md) </span></span>  
 [<span data-ttu-id="ef79c-226">Procedure consigliate per la sicurezza della replica</span><span class="sxs-lookup"><span data-stu-id="ef79c-226">Replication Security Best Practices</span></span>](security/replication-security-best-practices.md)  
  
  
