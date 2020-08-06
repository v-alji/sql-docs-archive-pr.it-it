---
title: Panoramica dell'interfaccia di Monitoraggio replica | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- Replication Monitor
- Replication Monitor, about Replication Monitor
ms.assetid: 078f0e34-7153-45c4-8725-778b5bef88da
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4d9b7edbd76153f23168ec9bcf4a286d5f7cbe9b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626638"
---
# <a name="overview-of-the-replication-monitor-interface"></a><span data-ttu-id="ca7a1-102">Panoramica dell'interfaccia di Monitoraggio replica</span><span class="sxs-lookup"><span data-stu-id="ca7a1-102">Overview of the Replication Monitor Interface</span></span>
  <span data-ttu-id="ca7a1-103">Monitoraggio replica per [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] offre una visualizzazione incentrata sul server di pubblicazione o sul server di distribuzione di tutte le attività di replica, suddivise in due riquadri.</span><span class="sxs-lookup"><span data-stu-id="ca7a1-103">[!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Replication Monitor presents a Publisher-focused view or Distributor-focused view of all replication activity in a two pane format.</span></span> <span data-ttu-id="ca7a1-104">Se si aggiunge un server di pubblicazione nel riquadro sinistro di Monitoraggio replica, verranno visualizzate nel riquadro sinistro informazioni sul server di pubblicazione, sulle relative pubblicazioni, sulle sottoscrizioni a tali pubblicazioni e sui diversi agenti di replica.</span><span class="sxs-lookup"><span data-stu-id="ca7a1-104">You add a Publisher to the monitor in the left pane, and in the right pane the monitor displays information on the Publisher, its publications, the subscriptions to those publications, and the various replication agents.</span></span> <span data-ttu-id="ca7a1-105">Oltre a visualizzare informazioni per la topologia di replica, Monitoraggio replica consente di eseguire numerose attività, quali l'avvio e l'arresto degli agenti e la convalida dei dati.</span><span class="sxs-lookup"><span data-stu-id="ca7a1-105">In addition to presenting information for the replication topology, Replication Monitor allows you to perform a number of tasks, such as starting and stopping agents, and validating data.</span></span>  
  
## <a name="viewing-information-for-the-entire-topology"></a><span data-ttu-id="ca7a1-106">Visualizzazione di informazioni per l'intera topologia</span><span class="sxs-lookup"><span data-stu-id="ca7a1-106">Viewing Information for the Entire Topology</span></span>  
 <span data-ttu-id="ca7a1-107">Nel riquadro sinistro di Monitoraggio replica vengono visualizzati</span><span class="sxs-lookup"><span data-stu-id="ca7a1-107">The left pane of Replication Monitor displays</span></span>  
  
-   <span data-ttu-id="ca7a1-108">Gruppi di server di pubblicazione, server di pubblicazione e pubblicazioni.</span><span class="sxs-lookup"><span data-stu-id="ca7a1-108">Publisher groups, Publishers, and publications.</span></span>  
  
-   <span data-ttu-id="ca7a1-109">Database di distribuzione, Server di pubblicazione e pubblicazioni.</span><span class="sxs-lookup"><span data-stu-id="ca7a1-109">Distributors, Publishers, and publications.</span></span>  
  
 <span data-ttu-id="ca7a1-110">Per visualizzare informazioni in Monitoraggio replica, è innanzitutto necessario aggiungere un server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="ca7a1-110">To view any information in Replication Monitor, you must first add a Publisher.</span></span> <span data-ttu-id="ca7a1-111">Per altre informazioni, vedere [Aggiungere e rimuovere server di pubblicazione da Monitoraggio replica](add-and-remove-publishers-from-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="ca7a1-111">For more information, see [Add and Remove Publishers from Replication Monitor](add-and-remove-publishers-from-replication-monitor.md).</span></span>  
  
 <span data-ttu-id="ca7a1-112">Il riquadro sinistro consente di individuare i seguenti aspetti:</span><span class="sxs-lookup"><span data-stu-id="ca7a1-112">The left pane helps answer the following questions:</span></span>  
  
-   <span data-ttu-id="ca7a1-113">Il sistema di replica funziona correttamente?</span><span class="sxs-lookup"><span data-stu-id="ca7a1-113">Is my replication system healthy?</span></span>  
  
     <span data-ttu-id="ca7a1-114">Lo stato del sistema di replica è valido se non sono presenti icone di errore sui nodi nel riquadro sinistro.</span><span class="sxs-lookup"><span data-stu-id="ca7a1-114">The replication system is relatively healthy if there are no error icons on nodes in the left pane.</span></span> <span data-ttu-id="ca7a1-115">Per ottenere una visione più completa dello stato del sistema, è inoltre consigliabile controllare la scheda **Elenco verifica sottoscrizioni** in cui sono visualizzate informazioni sulle sottoscrizioni che richiedono un'attenzione particolare.</span><span class="sxs-lookup"><span data-stu-id="ca7a1-115">To get a more complete view of system health, you should also check the **Subscription Watch List** tab, which displays information on subscriptions that might require attention.</span></span>  
  
-   <span data-ttu-id="ca7a1-116">Perché l'agente non è in esecuzione?</span><span class="sxs-lookup"><span data-stu-id="ca7a1-116">Why is an agent not running?</span></span>  
  
     <span data-ttu-id="ca7a1-117">Un agente può non essere in esecuzione in un determinato momento perché la sua esecuzione non è pianificata o perché si è verificato un errore.</span><span class="sxs-lookup"><span data-stu-id="ca7a1-117">An agent is not running at a particular time either because it is not scheduled to run or because an error has occurred.</span></span> <span data-ttu-id="ca7a1-118">In quest'ultimo caso viene visualizzata un'icona di errore sui nodi appropriati nel riquadro sinistro.</span><span class="sxs-lookup"><span data-stu-id="ca7a1-118">If an error has occurred, an error icon is displayed on the appropriate nodes in the left pane.</span></span> <span data-ttu-id="ca7a1-119">Ad esempio, se l'agente snapshot per una pubblicazione è stato arrestato a causa di un errore, viene visualizzata un'icona di errore sul gruppo server di pubblicazione, sul server di pubblicazione e sui nodi di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="ca7a1-119">For example, if the Snapshot Agent for a publication stopped because of an error, an error icon is displayed on the Publisher group, Publisher, and publication nodes.</span></span> <span data-ttu-id="ca7a1-120">Le informazioni di riepilogo per l'agente snapshot vengono visualizzate nella scheda **Agenti** per la pubblicazione. Fare doppio clic sull'agente snapshot in questa scheda per visualizzare informazioni dettagliate sull'errore.</span><span class="sxs-lookup"><span data-stu-id="ca7a1-120">Summary information for the Snapshot Agent is displayed on the **Agents** tab for the publication; double click the Snapshot Agent on this tab for detailed error information.</span></span>  
  
## <a name="viewing-information-and-performing-tasks-related-to-distributors"></a><span data-ttu-id="ca7a1-121">Visualizzazione delle informazioni ed esecuzione di attività relative ai server di distribuzione</span><span class="sxs-lookup"><span data-stu-id="ca7a1-121">Viewing Information and Performing Tasks Related to Distributors</span></span>  
 <span data-ttu-id="ca7a1-122">Monitoraggio replica consente di visualizzare informazioni sui server di distribuzione in tre schede:</span><span class="sxs-lookup"><span data-stu-id="ca7a1-122">Replication Monitor displays information about Distributors on three tabs:</span></span>  
  
-   <span data-ttu-id="ca7a1-123">Scheda**Pubblicazioni**</span><span class="sxs-lookup"><span data-stu-id="ca7a1-123">**Publications** tab</span></span>  
  
     <span data-ttu-id="ca7a1-124">In questa scheda sono incluse informazioni di riepilogo per tutte le pubblicazioni di un server di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="ca7a1-124">This tab provides summary information for all publications of a Distributor.</span></span>  
  
-   <span data-ttu-id="ca7a1-125">Scheda**Elenco verifica sottoscrizioni**</span><span class="sxs-lookup"><span data-stu-id="ca7a1-125">**Subscription Watch List** tab</span></span>  
  
     <span data-ttu-id="ca7a1-126">In questa scheda sono incluse informazioni sulle sottoscrizioni per il server di distribuzione selezionato.</span><span class="sxs-lookup"><span data-stu-id="ca7a1-126">This tab provides information about subscriptions for the selected Distributor.</span></span> <span data-ttu-id="ca7a1-127">È possibile filtrare l'elenco delle sottoscrizioni per visualizzare errori, avvisi ed eventuali sottoscrizioni con prestazioni scarse.</span><span class="sxs-lookup"><span data-stu-id="ca7a1-127">You can filter the list of subscriptions to see errors, warnings, and any poorly performing subscriptions.</span></span> <span data-ttu-id="ca7a1-128">In questa scheda è inoltre possibile effettuare le attività seguenti: accedere alle proprietà di sottoscrizione, accedere a informazioni dettagliate sull'agente o gli agenti associati a una sottoscrizione, reinizializzare le sottoscrizioni e convalidare le sottoscrizioni.</span><span class="sxs-lookup"><span data-stu-id="ca7a1-128">The tab also lets you to perform the following tasks: access subscription properties, access detailed information about the agent or agents associated with a subscription, reinitialize subscriptions, and validate subscriptions.</span></span>  
  
     <span data-ttu-id="ca7a1-129">La scheda **Elenco verifica sottoscrizioni** consente di individuare i seguenti aspetti:</span><span class="sxs-lookup"><span data-stu-id="ca7a1-129">The **Subscription Watch List** tab helps answer the following questions:</span></span>  
  
    -   <span data-ttu-id="ca7a1-130">Quali sottoscrizioni sono lente?</span><span class="sxs-lookup"><span data-stu-id="ca7a1-130">Which subscriptions are slow?</span></span>  
  
         <span data-ttu-id="ca7a1-131">Impostare le opzioni presenti in questa scheda in modo che nella griglia le sottoscrizioni siano disposte in base alle prestazioni offerte.</span><span class="sxs-lookup"><span data-stu-id="ca7a1-131">Set options on this tab so that the grid displays subscriptions in order by their relative performance.</span></span>  
  
    -   <span data-ttu-id="ca7a1-132">Il sistema di replica funziona correttamente?</span><span class="sxs-lookup"><span data-stu-id="ca7a1-132">Is my replication system healthy?</span></span>  
  
         <span data-ttu-id="ca7a1-133">Nella griglia presente in questa scheda vengono visualizzate icone di errore e di avviso per qualsiasi sottoscrizione che richieda un'attenzione particolare.</span><span class="sxs-lookup"><span data-stu-id="ca7a1-133">The grid on this tab displays error and warning icons for any subscriptions that require your attention.</span></span>  
  
     <span data-ttu-id="ca7a1-134">Questa scheda non è disponibile per i server di distribuzione che eseguono versioni di [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] o successive.</span><span class="sxs-lookup"><span data-stu-id="ca7a1-134">This tab is not available for Distributors that are running versions of [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] or earlier.</span></span>  
  
-   <span data-ttu-id="ca7a1-135">Scheda**Agenti**</span><span class="sxs-lookup"><span data-stu-id="ca7a1-135">**Agents** tab</span></span>  
  
     <span data-ttu-id="ca7a1-136">In questa scheda vengono visualizzate informazioni dettagliate su agenti e processi utilizzati da tutti i tipi di replica.</span><span class="sxs-lookup"><span data-stu-id="ca7a1-136">This tab displays detailed information about the agents and jobs that are used by all types of replication.</span></span> <span data-ttu-id="ca7a1-137">La scheda consente anche di avviare e arrestare ciascun agente e processo.</span><span class="sxs-lookup"><span data-stu-id="ca7a1-137">The tab also let you start and stop each agent and job.</span></span>  
  
 <span data-ttu-id="ca7a1-138">In Monitoraggio replica è incluso inoltre un menu di scelta rapida per il nodo del server di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="ca7a1-138">Replication Monitor also provides a context menu for the Distributor node.</span></span> <span data-ttu-id="ca7a1-139">Fare clic con il pulsante destro del mouse su un server di distribuzione nel riquadro sinistro per effettuare le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="ca7a1-139">Right-click a Distributor in the left pane to perform the following tasks:</span></span>  
  
-   <span data-ttu-id="ca7a1-140">Aggiungere un server di pubblicazione a Monitoraggio replica.</span><span class="sxs-lookup"><span data-stu-id="ca7a1-140">Add a Publisher to Replication Monitor.</span></span>  
  
-   <span data-ttu-id="ca7a1-141">Modificare le impostazioni di Monitoraggio replica per il server di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="ca7a1-141">Edit Replication Monitor settings for the Distributor.</span></span>  
  
-   <span data-ttu-id="ca7a1-142">Passare alla vista Gruppo server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="ca7a1-142">Switch to the Publisher Group view.</span></span>  
  
## <a name="viewing-information-and-performing-tasks-related-to-publishers"></a><span data-ttu-id="ca7a1-143">Visualizzazione delle informazioni ed esecuzione di attività relative ai server di pubblicazione</span><span class="sxs-lookup"><span data-stu-id="ca7a1-143">Viewing Information and Performing Tasks Related to Publishers</span></span>  
 <span data-ttu-id="ca7a1-144">Monitoraggio replica consente di visualizzare informazioni sui server di pubblicazione in tre schede:</span><span class="sxs-lookup"><span data-stu-id="ca7a1-144">Replication Monitor displays information about Publishers on three tabs:</span></span>  
  
-   <span data-ttu-id="ca7a1-145">Scheda**Pubblicazioni**</span><span class="sxs-lookup"><span data-stu-id="ca7a1-145">**Publications** tab</span></span>  
  
     <span data-ttu-id="ca7a1-146">In questa scheda sono incluse informazioni di riepilogo per tutte le pubblicazioni di un server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="ca7a1-146">This tab provides summary information for all publications at a Publisher.</span></span>  
  
-   <span data-ttu-id="ca7a1-147">Scheda**Elenco verifica sottoscrizioni**</span><span class="sxs-lookup"><span data-stu-id="ca7a1-147">**Subscription Watch List** tab</span></span>  
  
     <span data-ttu-id="ca7a1-148">Questa scheda è destinata alla visualizzazione delle informazioni sulle sottoscrizioni da tutte le pubblicazioni disponibili nel server di pubblicazione selezionato.</span><span class="sxs-lookup"><span data-stu-id="ca7a1-148">This tab is intended to display information on subscriptions from all publications available at the selected Publisher.</span></span> <span data-ttu-id="ca7a1-149">È possibile filtrare l'elenco delle sottoscrizioni per visualizzare errori, avvisi ed eventuali sottoscrizioni con prestazioni scarse.</span><span class="sxs-lookup"><span data-stu-id="ca7a1-149">You can filter the list of subscriptions to see errors, warnings, and any poorly performing subscriptions.</span></span> <span data-ttu-id="ca7a1-150">In questa scheda è inoltre possibile accedere alle proprietà di sottoscrizione, accedere a informazioni dettagliate sull'agente o gli agenti associati a una sottoscrizione, reinizializzare le sottoscrizioni e convalidare le sottoscrizioni.</span><span class="sxs-lookup"><span data-stu-id="ca7a1-150">The tab also allows you to: access subscription properties; access detailed information about the agent or agents associated with a subscription; reinitialize subscriptions; and validate subscriptions.</span></span>  
  
     <span data-ttu-id="ca7a1-151">La scheda **Elenco verifica sottoscrizioni** consente di individuare i seguenti aspetti:</span><span class="sxs-lookup"><span data-stu-id="ca7a1-151">The **Subscription Watch List** tab helps answer the following questions:</span></span>  
  
    -   <span data-ttu-id="ca7a1-152">Quali sottoscrizioni sono lente?</span><span class="sxs-lookup"><span data-stu-id="ca7a1-152">Which subscriptions are slow?</span></span>  
  
         <span data-ttu-id="ca7a1-153">Impostare le opzioni presenti in questa scheda in modo che nella griglia le sottoscrizioni siano disposte in base alle prestazioni offerte.</span><span class="sxs-lookup"><span data-stu-id="ca7a1-153">Set options on this tab so that the grid displays subscriptions in order by their relative performance.</span></span>  
  
    -   <span data-ttu-id="ca7a1-154">Il sistema di replica funziona correttamente?</span><span class="sxs-lookup"><span data-stu-id="ca7a1-154">Is my replication system healthy?</span></span>  
  
         <span data-ttu-id="ca7a1-155">Nella griglia presente in questa scheda vengono visualizzate icone di errore e di avviso per qualsiasi sottoscrizione che richieda un'attenzione particolare.</span><span class="sxs-lookup"><span data-stu-id="ca7a1-155">The grid on this tab displays error and warning icons for any subscriptions that require your attention.</span></span>  
  
     <span data-ttu-id="ca7a1-156">Questa scheda non viene visualizzata per i server di distribuzione che eseguono versioni precedenti a [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ca7a1-156">This tab is not displayed for Distributors running versions prior to [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)].</span></span>  
  
-   <span data-ttu-id="ca7a1-157">Scheda**Agenti**</span><span class="sxs-lookup"><span data-stu-id="ca7a1-157">**Agents** tab</span></span>  
  
     <span data-ttu-id="ca7a1-158">In questa scheda vengono visualizzate informazioni dettagliate su agenti e processi utilizzati da tutti i tipi di replica.</span><span class="sxs-lookup"><span data-stu-id="ca7a1-158">This tab displays detailed information about the agents and jobs used by all types of replication.</span></span> <span data-ttu-id="ca7a1-159">La scheda consente anche di avviare e arrestare ciascun agente e processo.</span><span class="sxs-lookup"><span data-stu-id="ca7a1-159">The tab also allows you to start and stop each agent and job.</span></span>  
  
 <span data-ttu-id="ca7a1-160">Per altre informazioni, vedere [Visualizzare le informazioni ed eseguire attività usando Monitoraggio replica](view-information-and-perform-tasks-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="ca7a1-160">For more information, see [View Information and Perform Tasks using Replication Monitor](view-information-and-perform-tasks-replication-monitor.md).</span></span>  
  
 <span data-ttu-id="ca7a1-161">In Monitoraggio replica è incluso inoltre un menu di scelta rapida per il nodo del server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="ca7a1-161">Replication Monitor also provides a context menu for the Publisher node.</span></span> <span data-ttu-id="ca7a1-162">Fare clic con il pulsante destro del mouse su un server di pubblicazione nel riquadro sinistro per:</span><span class="sxs-lookup"><span data-stu-id="ca7a1-162">Right-click a Publisher in the left pane to:</span></span>  
  
-   <span data-ttu-id="ca7a1-163">Modificare le impostazioni di Monitoraggio replica per il server di pubblicazione</span><span class="sxs-lookup"><span data-stu-id="ca7a1-163">Edit Replication Monitor settings for the Publisher</span></span>  
  
-   <span data-ttu-id="ca7a1-164">Rimuovere il server di pubblicazione da Monitoraggio replica</span><span class="sxs-lookup"><span data-stu-id="ca7a1-164">Remove the Publisher from Replication Monitor</span></span>  
  
-   <span data-ttu-id="ca7a1-165">Visualizzare e modificare i profili dell'agente</span><span class="sxs-lookup"><span data-stu-id="ca7a1-165">View and edit agent profiles</span></span>  
  
-   <span data-ttu-id="ca7a1-166">Connettersi o disconnettersi dal server di distribuzione in cui sono archiviate informazioni sul server di pubblicazione</span><span class="sxs-lookup"><span data-stu-id="ca7a1-166">Connect to or disconnect from the Distributor that stores information about the Publisher</span></span>  
  
## <a name="viewing-information-and-performing-tasks-related-to-publications"></a><span data-ttu-id="ca7a1-167">Visualizzazione delle informazioni ed esecuzione di attività relative alle pubblicazioni</span><span class="sxs-lookup"><span data-stu-id="ca7a1-167">Viewing Information and Performing Tasks Related to Publications</span></span>  
 <span data-ttu-id="ca7a1-168">In Monitoraggio replica vengono visualizzate informazioni sulle pubblicazioni in tre schede e in alcune finestre dei dettagli:</span><span class="sxs-lookup"><span data-stu-id="ca7a1-168">Replication Monitor displays information about publications on three tabs and a number of detail windows:</span></span>  
  
-   <span data-ttu-id="ca7a1-169">Scheda**Tutte le sottoscrizioni**</span><span class="sxs-lookup"><span data-stu-id="ca7a1-169">**All Subscriptions** tab</span></span>  
  
     <span data-ttu-id="ca7a1-170">In questa scheda vengono visualizzate informazioni su tutte le sottoscrizioni della pubblicazione selezionata.</span><span class="sxs-lookup"><span data-stu-id="ca7a1-170">This tab displays information about all subscriptions to the selected publication.</span></span> <span data-ttu-id="ca7a1-171">Per impostazione predefinita, le informazioni disponibili in questa scheda vengono visualizzate in ordine di priorità: errori, avvisi e sottoscrizioni ordinate in base alle prestazioni, dalle più scarse alle migliori.</span><span class="sxs-lookup"><span data-stu-id="ca7a1-171">By default, this tab is sorted in priority order: errors, then warnings, then in increasing order of performance, with any poorly performing subscriptions at the top.</span></span>  
  
     <span data-ttu-id="ca7a1-172">La scheda **Tutte le sottoscrizioni** consente di individuare i seguenti aspetti:</span><span class="sxs-lookup"><span data-stu-id="ca7a1-172">The **All Subscriptions** tab helps answer the following questions:</span></span>  
  
    -   <span data-ttu-id="ca7a1-173">Quali sottoscrizioni sono lente?</span><span class="sxs-lookup"><span data-stu-id="ca7a1-173">Which subscriptions are slow?</span></span>  
  
         <span data-ttu-id="ca7a1-174">Impostare le opzioni presenti in questa scheda in modo che nella griglia le sottoscrizioni siano disposte in base alle prestazioni offerte.</span><span class="sxs-lookup"><span data-stu-id="ca7a1-174">Set options on this tab so that the grid displays subscriptions in order by their relative performance.</span></span>  
  
    -   <span data-ttu-id="ca7a1-175">Il sistema di replica funziona correttamente?</span><span class="sxs-lookup"><span data-stu-id="ca7a1-175">Is my replication system healthy?</span></span>  
  
         <span data-ttu-id="ca7a1-176">Nella griglia presente in questa scheda vengono visualizzate icone di errore e di avviso per qualsiasi sottoscrizione che richieda un'attenzione particolare.</span><span class="sxs-lookup"><span data-stu-id="ca7a1-176">The grid on this tab displays error and warning icons for any subscriptions that require your attention.</span></span>  
  
-   <span data-ttu-id="ca7a1-177">Scheda**Agenti**</span><span class="sxs-lookup"><span data-stu-id="ca7a1-177">**Agents** tab</span></span>  
  
     <span data-ttu-id="ca7a1-178">In questa scheda vengono visualizzate informazioni sugli agenti utilizzati dalla replica.</span><span class="sxs-lookup"><span data-stu-id="ca7a1-178">This tab displays information about the agents that are used by replication.</span></span> <span data-ttu-id="ca7a1-179">In questa scheda vengono visualizzate informazioni relative agli agenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="ca7a1-179">This tab displays information about the following agents:</span></span>  
  
    -   <span data-ttu-id="ca7a1-180">Agente snapshot, utilizzato da tutte le pubblicazioni.</span><span class="sxs-lookup"><span data-stu-id="ca7a1-180">The Snapshot Agent, which is used by all publications.</span></span>  
  
    -   <span data-ttu-id="ca7a1-181">Agente di lettura log, utilizzato da tutte le pubblicazioni transazionali.</span><span class="sxs-lookup"><span data-stu-id="ca7a1-181">The Log Reader Agent, which is used by all transactional publications.</span></span>  
  
    -   <span data-ttu-id="ca7a1-182">Agente di lettura coda, utilizzato dalle pubblicazioni transazionali abilitate per le sottoscrizioni ad aggiornamento in coda.</span><span class="sxs-lookup"><span data-stu-id="ca7a1-182">The Queue Reader Agent, which is used by transactional publications enabled for queued updating subscriptions.</span></span>  
  
     <span data-ttu-id="ca7a1-183">Questa scheda consente inoltre di accedere a informazioni dettagliate su ciascun agente, nonché di avviare e arrestare ciascun agente.</span><span class="sxs-lookup"><span data-stu-id="ca7a1-183">The tab also allows for you to perform the following tasks: access detailed information about each agent, and start and stop each agent.</span></span> <span data-ttu-id="ca7a1-184">Per informazioni sugli agenti associati alle sottoscrizioni (agente di distribuzione e agente di merge), vedere la sezione "Visualizzazione delle informazioni ed esecuzione di attività relative alle sottoscrizioni" in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="ca7a1-184">For information about agents that are associated with subscriptions (the Distribution Agent and Merge Agent), see the section "Viewing Information and Performing Tasks Related to Subscriptions" in this topic.</span></span>  
  
-   <span data-ttu-id="ca7a1-185">Scheda**Avvisi**</span><span class="sxs-lookup"><span data-stu-id="ca7a1-185">**Warnings** tab</span></span>  
  
     <span data-ttu-id="ca7a1-186">Questa scheda consente di specificare avvisi per gli agenti.</span><span class="sxs-lookup"><span data-stu-id="ca7a1-186">This tab enables you to specify warnings and alerts for agents.</span></span> <span data-ttu-id="ca7a1-187">Per altre informazioni, vedere [Set Thresholds and Warnings in Replication Monitor](set-thresholds-and-warnings-in-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="ca7a1-187">For more information, see [Set Thresholds and Warnings in Replication Monitor](set-thresholds-and-warnings-in-replication-monitor.md).</span></span>  
  
-   <span data-ttu-id="ca7a1-188">Scheda**Token di traccia** (solo nella replica transazionale)</span><span class="sxs-lookup"><span data-stu-id="ca7a1-188">**Tracer Tokens** tab (transactional replication only)</span></span>  
  
     <span data-ttu-id="ca7a1-189">Questa scheda consente di misurare la latenza, ovvero l'intervallo di tempo che intercorre tra il commit di una transazione nel server di pubblicazione e il commit della transazione corrispondente nel Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="ca7a1-189">This tab allows you to measure latency, the amount of time that elapses between a transaction being committed at the Publisher and the corresponding transaction being committed at the Subscriber.</span></span>  
  
     <span data-ttu-id="ca7a1-190">Questa scheda consente di individuare i seguenti aspetti:</span><span class="sxs-lookup"><span data-stu-id="ca7a1-190">This tab helps answers the following question:</span></span>  
  
    -   <span data-ttu-id="ca7a1-191">In quanto tempo una transazione di cui è stato appena eseguito il commit raggiungerà un Sottoscrittore nella replica transazionale?</span><span class="sxs-lookup"><span data-stu-id="ca7a1-191">How long will it take a transaction committed now to reach a Subscriber in transactional replication?</span></span>  
  
         <span data-ttu-id="ca7a1-192">È possibile visualizzare l'intervallo di tempo impiegato da una transazione per attraversare il sistema e paragonare questo valore con gli intervalli precedenti.</span><span class="sxs-lookup"><span data-stu-id="ca7a1-192">View the total time for a transaction to travel through the system and also compare it to previous times.</span></span>  
  
     <span data-ttu-id="ca7a1-193">Questa scheda non viene visualizzata per i server di distribuzione che eseguono [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] o versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="ca7a1-193">This tab is not displayed for Distributors running [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] or earlier.</span></span> <span data-ttu-id="ca7a1-194">Per altre informazioni sui token di traccia, vedere [Misurare la latenza e convalidare le connessioni per la replica transazionale](measure-latency-and-validate-connections-for-transactional-replication.md).</span><span class="sxs-lookup"><span data-stu-id="ca7a1-194">For more information on tracer tokens, see [Measure Latency and Validate Connections for Transactional Replication](measure-latency-and-validate-connections-for-transactional-replication.md).</span></span>  
  
-   <span data-ttu-id="ca7a1-195">Finestre dei dettagli per gli agenti associati a una pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="ca7a1-195">Detail windows for the agents associated with a publication.</span></span> <span data-ttu-id="ca7a1-196">Alle pubblicazioni sono associati i seguenti agenti:</span><span class="sxs-lookup"><span data-stu-id="ca7a1-196">The following agents are associated with publications:</span></span>  
  
    -   <span data-ttu-id="ca7a1-197">Agente snapshot, utilizzato da tutte le pubblicazioni.</span><span class="sxs-lookup"><span data-stu-id="ca7a1-197">The Snapshot Agent, which is used by all publications.</span></span>  
  
    -   <span data-ttu-id="ca7a1-198">Agente di lettura log, utilizzato da tutte le pubblicazioni transazionali.</span><span class="sxs-lookup"><span data-stu-id="ca7a1-198">The Log Reader Agent, which is used by all transactional publications.</span></span>  
  
    -   <span data-ttu-id="ca7a1-199">Agente di lettura coda, utilizzato dalle pubblicazioni transazionali abilitate per le sottoscrizioni ad aggiornamento in coda.</span><span class="sxs-lookup"><span data-stu-id="ca7a1-199">The Queue Reader Agent, which is used by transactional publications enabled for queued updating subscriptions.</span></span>  
  
     <span data-ttu-id="ca7a1-200">Fare doppio clic su un agente in Monitoraggio replica per accedere alle informazioni in una finestra dei dettagli.</span><span class="sxs-lookup"><span data-stu-id="ca7a1-200">Double-click an agent in Replication Monitor to access information in a detail window.</span></span> <span data-ttu-id="ca7a1-201">Oltre agli agenti elencati sopra, sono disponibili agenti associati alle sottoscrizioni: l'agente di distribuzione per sottoscrizioni a pubblicazioni snapshot e transazionali e l'agente di merge per sottoscrizioni a pubblicazioni di tipo merge.</span><span class="sxs-lookup"><span data-stu-id="ca7a1-201">In addition to the agents listed above, there are agents associated with subscriptions: the Distribution Agent for subscriptions to snapshot and transactional publications; and the Merge Agent for subscriptions to merge publications.</span></span> <span data-ttu-id="ca7a1-202">Per ulteriori informazioni, vedere la sezione "Visualizzazione delle informazioni ed esecuzione di attività relative alle sottoscrizioni" in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="ca7a1-202">For more information, see the section "Viewing Information and Performing Tasks Related to Subscriptions" in this topic.</span></span>  
  
     <span data-ttu-id="ca7a1-203">Le finestre dei dettagli sugli agenti includono informazioni sulle sessioni dell'agente, specificando l'ora di inizio, l'ora di fine, la durata e le azioni eseguite in una sessione.</span><span class="sxs-lookup"><span data-stu-id="ca7a1-203">The agent detail windows provide information about agent sessions, including start time, end time, duration, and the actions performed in a session.</span></span> <span data-ttu-id="ca7a1-204">Queste finestre consentono di individuare i seguenti aspetti:</span><span class="sxs-lookup"><span data-stu-id="ca7a1-204">They help to answer the following question:</span></span>  
  
    -   <span data-ttu-id="ca7a1-205">Perché l'agente non è in esecuzione?</span><span class="sxs-lookup"><span data-stu-id="ca7a1-205">Why is an agent not running?</span></span>  
  
         <span data-ttu-id="ca7a1-206">I messaggi di errore disponibili offrono informazioni dettagliate sul motivo per cui un agente non è in esecuzione e rappresentano un punto di partenza per la risoluzione di problemi relativi agli agenti associati a una pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="ca7a1-206">The error messages available provide detailed information on why an agent is not running and provide a starting point for troubleshooting issues with the agents associated with a publication.</span></span>  
  
 <span data-ttu-id="ca7a1-207">Per altre informazioni, vedere [Visualizzare le informazioni ed eseguire attività usando Monitoraggio replica](view-information-and-perform-tasks-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="ca7a1-207">For more information, see [View Information and Perform Tasks using Replication Monitor](view-information-and-perform-tasks-replication-monitor.md).</span></span>  
  
 <span data-ttu-id="ca7a1-208">Monitoraggio replica include inoltre un menu di scelta rapida per il nodo delle pubblicazioni.</span><span class="sxs-lookup"><span data-stu-id="ca7a1-208">Replication Monitor also provides a context menu for the publications node.</span></span> <span data-ttu-id="ca7a1-209">Fare clic con il pulsante destro del mouse su una pubblicazione nel riquadro sinistro per:</span><span class="sxs-lookup"><span data-stu-id="ca7a1-209">Right-click a publication in the left pane to:</span></span>  
  
-   <span data-ttu-id="ca7a1-210">Reinizializzare tutte le sottoscrizioni di una pubblicazione</span><span class="sxs-lookup"><span data-stu-id="ca7a1-210">Reinitialize all subscriptions to a publication</span></span>  
  
-   <span data-ttu-id="ca7a1-211">Convalidare tutte le sottoscrizioni di una pubblicazione</span><span class="sxs-lookup"><span data-stu-id="ca7a1-211">Validate all subscriptions to a publication</span></span>  
  
-   <span data-ttu-id="ca7a1-212">Generare uno snapshot per una pubblicazione</span><span class="sxs-lookup"><span data-stu-id="ca7a1-212">Generate a snapshot for a publication</span></span>  
  
-   <span data-ttu-id="ca7a1-213">Visualizzare e modificare le proprietà della pubblicazione</span><span class="sxs-lookup"><span data-stu-id="ca7a1-213">View and edit publication properties</span></span>  
  
## <a name="viewing-information-and-performing-tasks-related-to-subscriptions"></a><span data-ttu-id="ca7a1-214">Visualizzazione delle informazioni ed esecuzione di attività relative alle sottoscrizioni</span><span class="sxs-lookup"><span data-stu-id="ca7a1-214">Viewing Information and Performing Tasks Related to Subscriptions</span></span>  
 <span data-ttu-id="ca7a1-215">In Monitoraggio replica vengono visualizzate informazioni sulle sottoscrizioni all'interno di numerose schede.</span><span class="sxs-lookup"><span data-stu-id="ca7a1-215">Replication Monitor displays information about subscriptions on a number of different tabs.</span></span> <span data-ttu-id="ca7a1-216">Fare doppio clic su una sottoscrizione in Monitoraggio replica per accedere a tali schede in una finestra dei dettagli.</span><span class="sxs-lookup"><span data-stu-id="ca7a1-216">Double-click a subscription in Replication Monitor to access these tabs in a detail window.</span></span> <span data-ttu-id="ca7a1-217">Tutte le schede consentono di individuare i motivi per cui un agente non è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="ca7a1-217">All of the tabs are useful in answering the question "Why is an agent not running?"</span></span> <span data-ttu-id="ca7a1-218">I messaggi di errore disponibili offrono informazioni dettagliate sul motivo per cui un agente non è in esecuzione e rappresentano un punto di partenza per la risoluzione di problemi relativi agli agenti associati a una sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="ca7a1-218">The error messages available provide detailed information on why an agent is not running and provide a starting point for troubleshooting issues with the agents associated with a subscription.</span></span>  
  
-   <span data-ttu-id="ca7a1-219">Schede**Tutte le sottoscrizioni** e **Elenco verifica sottoscrizioni**.</span><span class="sxs-lookup"><span data-stu-id="ca7a1-219">**All Subscriptions tab** and **Subscription Watch List tab.**</span></span>  
  
     <span data-ttu-id="ca7a1-220">Queste schede sono descritte più indietro in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="ca7a1-220">These tabs are described earlier in this topic.</span></span>  
  
-   <span data-ttu-id="ca7a1-221">Scheda**Cronologia server di pubblicazione - server di distribuzione** (solo nella replica transazionale)</span><span class="sxs-lookup"><span data-stu-id="ca7a1-221">**Publisher to Distributor History** tab (transactional replication only)</span></span>  
  
     <span data-ttu-id="ca7a1-222">In questa scheda vengono visualizzate informazioni sull'agente di lettura log per una pubblicazione (la scheda è identica alla finestra dei dettagli Agente di lettura log).</span><span class="sxs-lookup"><span data-stu-id="ca7a1-222">This tab displays information on the Log Reader Agent for a publication (the tab is identical to the Log Reader Agent details window).</span></span>  
  
-   <span data-ttu-id="ca7a1-223">Scheda**Cronologia server di distribuzione - Sottoscrittore** (nella replica snapshot e nella replica transazionale)</span><span class="sxs-lookup"><span data-stu-id="ca7a1-223">**Distributor to Subscriber History** tab (snapshot replication and transactional replication)</span></span>  
  
     <span data-ttu-id="ca7a1-224">In questa scheda vengono visualizzate informazioni sull'agente di distribuzione per una sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="ca7a1-224">This tab displays information on the Distribution Agent for a subscription.</span></span>  
  
-   <span data-ttu-id="ca7a1-225">Scheda**Comandi non distribuiti** (solo nella replica transazionale)</span><span class="sxs-lookup"><span data-stu-id="ca7a1-225">**Undistributed Commands** tab (transactional replication only)</span></span>  
  
     <span data-ttu-id="ca7a1-226">In questa scheda vengono visualizzate informazioni sul numero di comandi nel database di distribuzione che non sono stati recapitati al Sottoscrittore selezionato e sul tempo stimato per recapitare tali comandi.</span><span class="sxs-lookup"><span data-stu-id="ca7a1-226">This tab displays information about the number of commands in the distribution database that have not been delivered to the selected Subscriber, and the estimated time to deliver those commands.</span></span> <span data-ttu-id="ca7a1-227">Questa scheda consente di individuare lo stato della sottoscrizione</span><span class="sxs-lookup"><span data-stu-id="ca7a1-227">The tab helps answer the question, "How far behind is my subscription?"</span></span> <span data-ttu-id="ca7a1-228">è non è disponibile per i server di distribuzione che eseguono versioni precedenti a SQL Server 2005.</span><span class="sxs-lookup"><span data-stu-id="ca7a1-228">This tab is not displayed for Distributors running versions prior to SQL Server 2005.</span></span>  
  
-   <span data-ttu-id="ca7a1-229">Scheda**Cronologia sincronizzazione** (solo nella replica di tipo merge)</span><span class="sxs-lookup"><span data-stu-id="ca7a1-229">**Synchronization History** tab (merge replication only)</span></span>  
  
     <span data-ttu-id="ca7a1-230">In questa scheda vengono visualizzate informazioni sull'agente di merge per una sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="ca7a1-230">This tab displays information on the Merge Agent for a subscription.</span></span> <span data-ttu-id="ca7a1-231">Questa scheda consente di individuare i seguenti aspetti:</span><span class="sxs-lookup"><span data-stu-id="ca7a1-231">This tab helps answer the following question:</span></span>  
  
    -   <span data-ttu-id="ca7a1-232">Per quale motivo la sottoscrizione di tipo merge è lenta?</span><span class="sxs-lookup"><span data-stu-id="ca7a1-232">Why is my merge subscription slow?</span></span>  
  
         <span data-ttu-id="ca7a1-233">In questa scheda vengono incluse statistiche dettagliate per ogni articolo elaborato durante la sincronizzazione, incluso l'intervallo di tempo impiegato in ogni fase di elaborazione (caricamento delle modifiche, download delle modifiche e così via).</span><span class="sxs-lookup"><span data-stu-id="ca7a1-233">This tab provides detailed statistics for each article processed during synchronization, including the amount of time spent in each processing phase (uploading changes, downloading changes, and so on).</span></span> <span data-ttu-id="ca7a1-234">Questa scheda può agevolare l'identificazione di tabelle specifiche che causano rallentamenti ed è il luogo ideale per risolvere problemi relativi alle prestazioni delle sottoscrizioni di tipo merge.</span><span class="sxs-lookup"><span data-stu-id="ca7a1-234">It can help pinpoint specific tables that are causing slowdowns and is the best place to troubleshoot performance issues with merge subscriptions.</span></span>  
  
 <span data-ttu-id="ca7a1-235">Per altre informazioni, vedere [Visualizzare le informazioni ed eseguire attività usando Monitoraggio replica](view-information-and-perform-tasks-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="ca7a1-235">For more information, see [View Information and Perform Tasks using Replication Monitor](view-information-and-perform-tasks-replication-monitor.md).</span></span>
  
## <a name="viewing-information-and-performing-tasks-related-to-agent-profiles"></a><span data-ttu-id="ca7a1-236">Visualizzazione delle informazioni ed esecuzione di attività relative ai profili degli agenti</span><span class="sxs-lookup"><span data-stu-id="ca7a1-236">Viewing Information and Performing Tasks Related to Agent Profiles</span></span>  
 <span data-ttu-id="ca7a1-237">Monitoraggio replica include un certo numero di finestre di dialogo per la gestione dei profili degli agenti.</span><span class="sxs-lookup"><span data-stu-id="ca7a1-237">Replication Monitor includes a number of dialog boxes for managing agent profiles.</span></span> <span data-ttu-id="ca7a1-238">I profili degli agenti sono set di parametri relativi a un agente che ne determinano il comportamento.</span><span class="sxs-lookup"><span data-stu-id="ca7a1-238">Agent profiles are sets of parameters for an agent that determine agent behavior.</span></span> <span data-ttu-id="ca7a1-239">Per altre informazioni, vedere [Replication Agent Profiles](../agents/replication-agent-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="ca7a1-239">For more information, see [Replication Agent Profiles](../agents/replication-agent-profiles.md).</span></span> <span data-ttu-id="ca7a1-240">Di seguito vengono descritte le finestre di dialogo associate ai profili:</span><span class="sxs-lookup"><span data-stu-id="ca7a1-240">The dialog boxes are:</span></span>  
  
-   <span data-ttu-id="ca7a1-241">**Profili agenti**</span><span class="sxs-lookup"><span data-stu-id="ca7a1-241">**Agent Profiles**</span></span>  
  
     <span data-ttu-id="ca7a1-242">In questa finestra di dialogo è possibile modificare le proprietà dei profili, creare ed eliminare i profili, specificare un profilo predefinito e specificare che tutti gli agenti di un tipo specifico, ad esempio gli agenti snapshot, debbano utilizzare un determinato profilo.</span><span class="sxs-lookup"><span data-stu-id="ca7a1-242">This dialog box allows you to: change the properties of profiles; create and delete profiles; specify a default profile; and specify that all agents of a specific type (such as Snapshot Agents) should use a given profile.</span></span>  
  
-   <span data-ttu-id="ca7a1-243">**\<AgentProfileName> Proprietà**</span><span class="sxs-lookup"><span data-stu-id="ca7a1-243">**\<AgentProfileName> Properties**</span></span>  
  
     <span data-ttu-id="ca7a1-244">Questa finestra di dialogo consente di visualizzare e modificare le impostazioni dei parametri in un profilo.</span><span class="sxs-lookup"><span data-stu-id="ca7a1-244">This dialog box allows you to view and edit the parameter settings in a profile.</span></span>  
  
-   <span data-ttu-id="ca7a1-245">**Nuovo profilo agente**</span><span class="sxs-lookup"><span data-stu-id="ca7a1-245">**New Agent Profile**</span></span>  
  
     <span data-ttu-id="ca7a1-246">Questa finestra di dialogo consente di creare un nuovo profilo, che può facoltativamente includere i valori di un profilo esistente.</span><span class="sxs-lookup"><span data-stu-id="ca7a1-246">This dialog box allows you to create a new profile, optionally including the values from an existing profile.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca7a1-247">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ca7a1-247">See Also</span></span>  
 [<span data-ttu-id="ca7a1-248">Monitoraggio della replica</span><span class="sxs-lookup"><span data-stu-id="ca7a1-248">Monitoring Replication</span></span>](../monitoring-replication.md)  
  
  
