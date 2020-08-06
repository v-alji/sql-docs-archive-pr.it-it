---
title: Replica di SQL Server finestra di dialogo "informazioni sul server di distribuzione" | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.Distributor.Publications.f1
- sql12.rep.monitor.Distributor.commonjobs..f1
- sql12.rep.monitor.Distributor.SubscriptionSummary.merge.f1
- sql12.rep.monitor.Distributor.SubscriptionSummary.snapshot.f1
- sql12.rep.monitor.Distributor.SubscriptionSummary.tran.f1
ms.assetid: 1f499277-7f12-42ba-8cf4-52b683434944
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8ca0717a63c9660c225ec238e1e4d2423f7d01ba
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624627"
---
# <a name="distributor-information-dialog-box"></a><span data-ttu-id="41e99-102">Finestra di dialogo informazioni server di distribuzione</span><span class="sxs-lookup"><span data-stu-id="41e99-102">Distributor Information Dialog Box</span></span> 
<span data-ttu-id="41e99-103">In questo argomento vengono fornite informazioni sulla finestra di dialogo **server di distribuzione**</span><span class="sxs-lookup"><span data-stu-id="41e99-103">This topic provides information on the **Distributor** dialog box</span></span> 

## <a name="publications"></a><span data-ttu-id="41e99-104">Pubblicazioni</span><span class="sxs-lookup"><span data-stu-id="41e99-104">Publications</span></span>

  <span data-ttu-id="41e99-105">Nella scheda **Pubblicazioni** vengono fornite informazioni di riepilogo relative a tutte le pubblicazioni nel server di distribuzione selezionato nel riquadro sinistro.</span><span class="sxs-lookup"><span data-stu-id="41e99-105">The **Publications** tab provides summary information for all publications at the Distributor that is selected in the left pane.</span></span>  
  
### <a name="options"></a><span data-ttu-id="41e99-106">Opzioni</span><span class="sxs-lookup"><span data-stu-id="41e99-106">Options</span></span>  
 <span data-ttu-id="41e99-107">Nelle informazioni visualizzate relative alle pubblicazioni supportate dal server di distribuzione è inclusa una colonna in cui è contenuta l'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] del server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="41e99-107">The information that is displayed about the publications supported by the Distributor includes a column that contains the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance of the Publisher.</span></span> <span data-ttu-id="41e99-108">In caso contrario, le informazioni sulla pubblicazione corrispondono alle informazioni sulla pubblicazione fornite quando si visualizzano pubblicazioni nella vista Server di pubblicazione di Monitoraggio replica.</span><span class="sxs-lookup"><span data-stu-id="41e99-108">Otherwise, the publication information is the same as the publication information that is provided when you view publications in the Publisher view of Replication Monitor.</span></span> <span data-ttu-id="41e99-109">Per ulteriori informazioni sulle colonne nella scheda **Pubblicazioni** , vedere [Publisher Information, Publications](publisher-information-publications.md).</span><span class="sxs-lookup"><span data-stu-id="41e99-109">For more information about the columns in the **Publications** tab, see [Publisher Information, Publications](publisher-information-publications.md).</span></span>  

## <a name="subscription-watch-list"></a><span data-ttu-id="41e99-110">Elenco verifica sottoscrizioni</span><span class="sxs-lookup"><span data-stu-id="41e99-110">Subscription watch list</span></span>

### <a name="transactional-replication"></a><span data-ttu-id="41e99-111">Replica transazionale</span><span class="sxs-lookup"><span data-stu-id="41e99-111">Transactional replication</span></span> 
  <span data-ttu-id="41e99-112">Nelle informazioni per le sottoscrizioni transazionali è incluso il nome del server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="41e99-112">Information for transactional subscriptions includes the name of the Publisher.</span></span> <span data-ttu-id="41e99-113">In caso contrario, la funzionalità e le informazioni fornite in questa finestra di dialogo sono le stesse della vista Server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="41e99-113">Otherwise, the functionality and the information that is provided in this dialog box is the same as in the Publisher view.</span></span> <span data-ttu-id="41e99-114">Per altre informazioni su come usare questa finestra di dialogo, vedere [Informazioni sul server di pubblicazione, Elenco verifica sottoscrizioni &#40;pubblicazione transazionale, SQL Server 2005 e versioni successive&#41;](publisher-information-subscription-watch-list-transactional.md).</span><span class="sxs-lookup"><span data-stu-id="41e99-114">For more information about how to use this dialog box, see [Publisher Information, Subscription Watch List &#40;Transactional Publication, SQL Server 2005 and Later&#41;](publisher-information-subscription-watch-list-transactional.md).</span></span>  

### <a name="merge-replication"></a><span data-ttu-id="41e99-115">Replica di tipo merge</span><span class="sxs-lookup"><span data-stu-id="41e99-115">Merge replication</span></span>
  <span data-ttu-id="41e99-116">Nelle informazioni per le sottoscrizioni delle pubblicazioni di tipo merge è incluso il nome del server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="41e99-116">Information for merge publication subscriptions includes the name of the Publisher.</span></span> <span data-ttu-id="41e99-117">In caso contrario, la funzionalità e le informazioni fornite in questa finestra di dialogo sono le stesse della vista Server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="41e99-117">Otherwise, the functionality and the information that is provided in this dialog box is the same as in the Publisher view.</span></span> <span data-ttu-id="41e99-118">Per altre informazioni su come usare questa finestra di dialogo, vedere [Informazioni sul server di pubblicazione, Elenco verifica sottoscrizioni &#40;pubblicazione di tipo merge, SQL Server 2005 e versioni successive&#41;](publisher-information-subscription-watch-list-merge-publication.md).</span><span class="sxs-lookup"><span data-stu-id="41e99-118">For more information about how to use this dialog box, see [Publisher Information, Subscription Watch List &#40;Merge Publication, SQL Server 2005 and Later&#41;](publisher-information-subscription-watch-list-merge-publication.md).</span></span> 

### <a name="snapshot-replication"></a><span data-ttu-id="41e99-119">Replica snapshot</span><span class="sxs-lookup"><span data-stu-id="41e99-119">Snapshot replication</span></span>
  <span data-ttu-id="41e99-120">Nelle informazioni per le sottoscrizioni delle pubblicazioni snapshot è incluso il nome del server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="41e99-120">Information for snapshot publication subscriptions includes the name of the Publisher.</span></span> <span data-ttu-id="41e99-121">In caso contrario, la funzionalità e le informazioni fornite in questa finestra di dialogo sono le stesse della vista Server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="41e99-121">Otherwise, the functionality and the information that is provided in this dialog box is the same as in the Publisher view.</span></span> <span data-ttu-id="41e99-122">Per altre informazioni su come usare questa finestra di dialogo, vedere [Informazioni sul server di pubblicazione, Elenco verifica sottoscrizioni &#40;pubblicazione snapshot, SQL Server 2005 e versioni successive&#41;](publisher-information-subscription-watch-list-snapshot.md).</span><span class="sxs-lookup"><span data-stu-id="41e99-122">For more information about how to use this dialog box, see [Publisher Information, Subscription Watch List &#40;Snapshot Publication, SQL Server 2005 and Later&#41;](publisher-information-subscription-watch-list-snapshot.md).</span></span>  

## <a name="agents"></a><span data-ttu-id="41e99-123">Agenti</span><span class="sxs-lookup"><span data-stu-id="41e99-123">Agents</span></span>
  <span data-ttu-id="41e99-124"> Nella scheda **Agenti** sono visualizzate le informazioni sugli agenti e sui processi di manutenzione associati al server di pubblicazione e al Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="41e99-124">The **Agents** tab displays information about the agents and maintenance jobs that are associated with the Publisher and Subscriber.</span></span>  
  
 <span data-ttu-id="41e99-125">Tra gli agenti disponibili nella scheda **Agenti** per un server di distribuzione nella vista Server di distribuzione sono inclusi tutti gli agenti disponibili nella scheda **Agenti** per un server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="41e99-125">The agents that are available in the **Agents** tab for a Distributor in Distributor view include all the agents that are available in the **Agents** tab for a Publisher.</span></span> <span data-ttu-id="41e99-126">Tuttavia, in **tale scheda** sono inclusi anche un agente del server di distribuzione e un agente di merge.</span><span class="sxs-lookup"><span data-stu-id="41e99-126">However, the **Agents** tab for a Distributor in Distributor view also includes a Distributor Agent and a Merge Agent.</span></span>  
  
 <span data-ttu-id="41e99-127">Per ulteriori informazioni sugli agenti snapshot, di lettura log, di lettura coda nonché sui processi di manutenzione, vedere [Publisher Information, Agents](publisher-information-agents.md).</span><span class="sxs-lookup"><span data-stu-id="41e99-127">For more information about the Snapshot, Log Reader, and Queue Reader agents, and maintenance jobs, see [Publisher Information, Agents](publisher-information-agents.md).</span></span> <span data-ttu-id="41e99-128">Si noti che quando si visualizzano le informazioni sugli agenti nella scheda **Agenti** per un server di distribuzione, le informazioni sul server di pubblicazione sono disponibili per gli agenti snapshot e di lettura log.</span><span class="sxs-lookup"><span data-stu-id="41e99-128">Notice that when you are viewing agent information on the **Agents** tab for a Distributor, Publisher information is present for the Snapshot and Log Reader agents.</span></span> <span data-ttu-id="41e99-129">Tuttavia, nella scheda **Agenti** per un server di distribuzione nella vista Server di distribuzione è possibile selezionare anche **Agente del server di distribuzione** e **Agente di merge**.</span><span class="sxs-lookup"><span data-stu-id="41e99-129">However, in the **Agents** tab for a Distributor in Distributor view, you can also select **Distributor Agent** and **Merge Agent**.</span></span>  
  
### <a name="options"></a><span data-ttu-id="41e99-130">Opzioni</span><span class="sxs-lookup"><span data-stu-id="41e99-130">Options</span></span>  
 <span data-ttu-id="41e99-131">Nelle sezioni seguenti sono descritti i dati visualizzati in questa scheda per l'agente del server di distribuzione e per quello di merge.</span><span class="sxs-lookup"><span data-stu-id="41e99-131">The following sections describe the data that is displayed on this tab for the Distributor Agent and Merge Agent.</span></span>  
  
### <a name="distributor-agent"></a><span data-ttu-id="41e99-132">Agente del server di distribuzione</span><span class="sxs-lookup"><span data-stu-id="41e99-132">Distributor Agent</span></span>  
 <span data-ttu-id="41e99-133">**Status**</span><span class="sxs-lookup"><span data-stu-id="41e99-133">**Status**</span></span>  
 <span data-ttu-id="41e99-134">Stato dell'agente.</span><span class="sxs-lookup"><span data-stu-id="41e99-134">The status of the agent.</span></span> <span data-ttu-id="41e99-135">Nell'elenco seguente vengono indicati i valori di stato possibili:</span><span class="sxs-lookup"><span data-stu-id="41e99-135">The following list shows the possible status values:</span></span>  
  
-   <span data-ttu-id="41e99-136">Errore</span><span class="sxs-lookup"><span data-stu-id="41e99-136">Error</span></span>    
-   <span data-ttu-id="41e99-137">Riprova</span><span class="sxs-lookup"><span data-stu-id="41e99-137">Retry</span></span>    
-   <span data-ttu-id="41e99-138">In esecuzione</span><span class="sxs-lookup"><span data-stu-id="41e99-138">Running</span></span>    
-   <span data-ttu-id="41e99-139">Non in esecuzione</span><span class="sxs-lookup"><span data-stu-id="41e99-139">Not Running</span></span>    
-   <span data-ttu-id="41e99-140">Mai avviato</span><span class="sxs-lookup"><span data-stu-id="41e99-140">Never started</span></span>  
  
 <span data-ttu-id="41e99-141">**Autore**</span><span class="sxs-lookup"><span data-stu-id="41e99-141">**Publisher**</span></span>  
 <span data-ttu-id="41e99-142">Istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] del server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="41e99-142">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance of the Publisher.</span></span>  
  
 <span data-ttu-id="41e99-143">**Publication**</span><span class="sxs-lookup"><span data-stu-id="41e99-143">**Publication**</span></span>  
 <span data-ttu-id="41e99-144">Nome della pubblicazione a cui è associato l'agente.</span><span class="sxs-lookup"><span data-stu-id="41e99-144">The name of the publication with which the agent is associated.</span></span>  
  
 <span data-ttu-id="41e99-145">**Sottoscrizione**</span><span class="sxs-lookup"><span data-stu-id="41e99-145">**Subscription**</span></span>  
 <span data-ttu-id="41e99-146">Nome della sottoscrizione nel formato [*SubscriberName*].[*Database*].</span><span class="sxs-lookup"><span data-stu-id="41e99-146">The name of the subscription, in the form: [*SubscriberName*].[*Database*].</span></span>  
  
 <span data-ttu-id="41e99-147">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="41e99-147">**Type**</span></span>  
 <span data-ttu-id="41e99-148">Tipo di replica: push, pull o anonima.</span><span class="sxs-lookup"><span data-stu-id="41e99-148">Type of replication: push, pull, or Anonymous.</span></span>  
  
 <span data-ttu-id="41e99-149">**Ultima ora di inizio**</span><span class="sxs-lookup"><span data-stu-id="41e99-149">**Last Start Time**</span></span>  
 <span data-ttu-id="41e99-150">Ultima ora di avvio dell'agente.</span><span class="sxs-lookup"><span data-stu-id="41e99-150">The last time at which the agent started.</span></span>  
  
 <span data-ttu-id="41e99-151">**Duration**</span><span class="sxs-lookup"><span data-stu-id="41e99-151">**Duration**</span></span>  
 <span data-ttu-id="41e99-152">Durata dell'esecuzione dell'agente.</span><span class="sxs-lookup"><span data-stu-id="41e99-152">The length of time that the agent has run.</span></span> <span data-ttu-id="41e99-153">Il valore di durata rappresenta il tempo trascorso se l'agente è ancora in esecuzione e il tempo totale se l'agente è stato eseguito in precedenza.</span><span class="sxs-lookup"><span data-stu-id="41e99-153">The time represents elapsed time if the agent is currently running, and total time if the agent has run previously.</span></span>  
  
 <span data-ttu-id="41e99-154">**Ultima azione**</span><span class="sxs-lookup"><span data-stu-id="41e99-154">**Last Action**</span></span>  
 <span data-ttu-id="41e99-155">Ultima azione eseguita durante la più recente esecuzione dell'agente.</span><span class="sxs-lookup"><span data-stu-id="41e99-155">The last action that was performed during the most recent run of the agent.</span></span>  
  
 <span data-ttu-id="41e99-156">**Frequenza recapito**</span><span class="sxs-lookup"><span data-stu-id="41e99-156">**Delivery Rate**</span></span>  
 <span data-ttu-id="41e99-157">Frequenza, in comandi al secondo, con cui viene eseguito il commit dei comandi di inizializzazione nel database di distribuzione durante la più recente esecuzione dell'agente.</span><span class="sxs-lookup"><span data-stu-id="41e99-157">The rate, in commands per second, at which initialization commands are committed in the distribution database during the most recent run of the agent.</span></span>  
  
 <span data-ttu-id="41e99-158">**Latency**</span><span class="sxs-lookup"><span data-stu-id="41e99-158">**Latency**</span></span>  
 <span data-ttu-id="41e99-159">Tempo, espresso in secondi, trascorso tra il commit della modifica più recente nel database di pubblicazione e il commit del comando corrispondente nel database di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="41e99-159">The time, in seconds, that has elapsed between the most recent change being committed in the publication database, and the corresponding command being committed in the distribution database.</span></span>  
  
 <span data-ttu-id="41e99-160">**N. transazioni**</span><span class="sxs-lookup"><span data-stu-id="41e99-160">**#Trans**</span></span>  
 <span data-ttu-id="41e99-161">Numero di transazioni di cui è stato eseguito il commit nel database di distribuzione durante la più recente esecuzione dell'agente.</span><span class="sxs-lookup"><span data-stu-id="41e99-161">The number of transactions committed in the distribution database during the most recent run of the agent.</span></span>  
  
 <span data-ttu-id="41e99-162">**N. comandi**</span><span class="sxs-lookup"><span data-stu-id="41e99-162">**#Cmds**</span></span>  
 <span data-ttu-id="41e99-163">Numero di comandi di cui è stato eseguito il commit nel database di distribuzione durante la più recente esecuzione dell'agente.</span><span class="sxs-lookup"><span data-stu-id="41e99-163">The number of commands committed in the distribution database during the most recent run of the agent.</span></span> <span data-ttu-id="41e99-164">Un comando è equivalente a una modifica dei dati, ad esempio un aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="41e99-164">A command is the same as a data change, such as an update.</span></span>  
  
 <span data-ttu-id="41e99-165">**Media n. comandi**</span><span class="sxs-lookup"><span data-stu-id="41e99-165">**Avg. #Cmds**</span></span>  
 <span data-ttu-id="41e99-166">Numero medio di comandi per transazione durante la più recente esecuzione dell'agente.</span><span class="sxs-lookup"><span data-stu-id="41e99-166">The average number of commands per transaction during the most recent run of the agent.</span></span>  
  
### <a name="merge-agent"></a><span data-ttu-id="41e99-167">Agente di merge</span><span class="sxs-lookup"><span data-stu-id="41e99-167">Merge Agent</span></span>  
 <span data-ttu-id="41e99-168">**Status**</span><span class="sxs-lookup"><span data-stu-id="41e99-168">**Status**</span></span>  
 <span data-ttu-id="41e99-169">Stato dell'agente.</span><span class="sxs-lookup"><span data-stu-id="41e99-169">The status of the agent.</span></span> <span data-ttu-id="41e99-170">Nell'elenco seguente vengono indicati i valori di stato possibili:</span><span class="sxs-lookup"><span data-stu-id="41e99-170">The following list shows the possible status values:</span></span>  
  
-   <span data-ttu-id="41e99-171">Errore</span><span class="sxs-lookup"><span data-stu-id="41e99-171">Error</span></span>    
-   <span data-ttu-id="41e99-172">Riprova</span><span class="sxs-lookup"><span data-stu-id="41e99-172">Retry</span></span>    
-   <span data-ttu-id="41e99-173">In esecuzione</span><span class="sxs-lookup"><span data-stu-id="41e99-173">Running</span></span>    
-   <span data-ttu-id="41e99-174">Non in esecuzione</span><span class="sxs-lookup"><span data-stu-id="41e99-174">Not Running</span></span>    
-   <span data-ttu-id="41e99-175">Mai avviato</span><span class="sxs-lookup"><span data-stu-id="41e99-175">Never started</span></span>  
  
 <span data-ttu-id="41e99-176">**Autore**</span><span class="sxs-lookup"><span data-stu-id="41e99-176">**Publisher**</span></span>  
 <span data-ttu-id="41e99-177">Istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] del server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="41e99-177">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance of the Publisher.</span></span>  
  
 <span data-ttu-id="41e99-178">**Publication**</span><span class="sxs-lookup"><span data-stu-id="41e99-178">**Publication**</span></span>  
 <span data-ttu-id="41e99-179">Nome della pubblicazione a cui è associato l'agente.</span><span class="sxs-lookup"><span data-stu-id="41e99-179">The name of the publication with which the agent is associated.</span></span>  
  
 <span data-ttu-id="41e99-180">**Sottoscrizione**</span><span class="sxs-lookup"><span data-stu-id="41e99-180">**Subscription**</span></span>  
 <span data-ttu-id="41e99-181">Nome della sottoscrizione nel formato [*SubscriberName*].[*Database*].</span><span class="sxs-lookup"><span data-stu-id="41e99-181">The name of the subscription, in the form: [*SubscriberName*].[*Database*].</span></span>  
  
 <span data-ttu-id="41e99-182">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="41e99-182">**Type**</span></span>  
 <span data-ttu-id="41e99-183">Tipo di replica: push, pull o anonima.</span><span class="sxs-lookup"><span data-stu-id="41e99-183">Type of replication: push, pull, or Anonymous.</span></span>  
  
 <span data-ttu-id="41e99-184">**Ultima ora di inizio**</span><span class="sxs-lookup"><span data-stu-id="41e99-184">**Last Start Time**</span></span>  
 <span data-ttu-id="41e99-185">Ultima ora di avvio dell'agente.</span><span class="sxs-lookup"><span data-stu-id="41e99-185">The last time at which the agent started.</span></span>  
  
 <span data-ttu-id="41e99-186">**Duration**</span><span class="sxs-lookup"><span data-stu-id="41e99-186">**Duration**</span></span>  
 <span data-ttu-id="41e99-187">Durata dell'esecuzione dell'agente.</span><span class="sxs-lookup"><span data-stu-id="41e99-187">The length of time that the agent has run.</span></span> <span data-ttu-id="41e99-188">Il valore di durata rappresenta il tempo trascorso se l'agente è ancora in esecuzione e il tempo totale se l'agente è stato eseguito in precedenza.</span><span class="sxs-lookup"><span data-stu-id="41e99-188">The time represents elapsed time if the agent is currently running, and total time if the agent has run previously.</span></span>  
  
 <span data-ttu-id="41e99-189">**Ultima azione**</span><span class="sxs-lookup"><span data-stu-id="41e99-189">**Last Action**</span></span>  
 <span data-ttu-id="41e99-190">Ultima azione eseguita durante la più recente esecuzione dell'agente.</span><span class="sxs-lookup"><span data-stu-id="41e99-190">The last action that was performed during the most recent run of the agent.</span></span>  
  
 <span data-ttu-id="41e99-191">**Frequenza recapito**</span><span class="sxs-lookup"><span data-stu-id="41e99-191">**Delivery Rate**</span></span>  
 <span data-ttu-id="41e99-192">Frequenza, in comandi al secondo, con cui viene eseguito il commit delle modifiche nel database di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="41e99-192">The rate, in commands per second, at which changes are committed in the distribution database.</span></span>  
  
 <span data-ttu-id="41e99-193">**Inserimenti del server di pubblicazione**</span><span class="sxs-lookup"><span data-stu-id="41e99-193">**Publisher Inserts**</span></span>  
 <span data-ttu-id="41e99-194">Numero di comandi INSERT applicati nel server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="41e99-194">Number of INSERT commands applied at the Publisher.</span></span>  
  
 <span data-ttu-id="41e99-195">**Aggiornamenti del server di pubblicazione**</span><span class="sxs-lookup"><span data-stu-id="41e99-195">**Publisher Updates**</span></span>  
 <span data-ttu-id="41e99-196">Numero di comandi UPDATE applicati nel server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="41e99-196">Number of UPDATE commands applied at the Publisher.</span></span>  
  
 <span data-ttu-id="41e99-197">**Eliminazioni del server di pubblicazione**</span><span class="sxs-lookup"><span data-stu-id="41e99-197">**Publisher Deletes**</span></span>  
 <span data-ttu-id="41e99-198">Numero di comandi DELETE applicati nel server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="41e99-198">Number of DELETE commands applied at the Publisher.</span></span>  
  
 <span data-ttu-id="41e99-199">**Conflitti del server di pubblicazione**</span><span class="sxs-lookup"><span data-stu-id="41e99-199">**Publisher Conflicts**</span></span>  
 <span data-ttu-id="41e99-200">Numero di conflitti che si verificano nel server di pubblicazione durante il processo di merge.</span><span class="sxs-lookup"><span data-stu-id="41e99-200">The number of conflicts occurring at the Publisher during the merge process.</span></span>  
  
 <span data-ttu-id="41e99-201">**Inserimenti del Sottoscrittore**</span><span class="sxs-lookup"><span data-stu-id="41e99-201">**Subscriber Inserts**</span></span>  
 <span data-ttu-id="41e99-202">Numero di comandi INSERT applicati nel Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="41e99-202">Number of INSERT commands applied at the Subscriber.</span></span>  
  
 <span data-ttu-id="41e99-203">**Aggiornamenti del Sottoscrittore**</span><span class="sxs-lookup"><span data-stu-id="41e99-203">**Subscriber Updates**</span></span>  
 <span data-ttu-id="41e99-204">Numero di comandi UPDATE applicati nel Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="41e99-204">Number of UPDATE commands applied at the Subscriber.</span></span>  
  
 <span data-ttu-id="41e99-205">**Eliminazioni del Sottoscrittore**</span><span class="sxs-lookup"><span data-stu-id="41e99-205">**Subscriber Deletes**</span></span>  
 <span data-ttu-id="41e99-206">Numero di comandi DELETE applicati nel Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="41e99-206">Number of DELETE commands applied at the Subscriber.</span></span>  
  
 <span data-ttu-id="41e99-207">**Conflitti del Sottoscrittore**</span><span class="sxs-lookup"><span data-stu-id="41e99-207">**Subscriber Conflicts**</span></span>  
 <span data-ttu-id="41e99-208">Numero di conflitti che si verificano nel Sottoscrittore durante il processo di merge.</span><span class="sxs-lookup"><span data-stu-id="41e99-208">The number of conflicts occurring at the Subscriber during the merge process.</span></span>  
  
 
## <a name="see-also"></a><span data-ttu-id="41e99-209">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="41e99-209">See Also</span></span>  
 <span data-ttu-id="41e99-210">[Avviare Monitoraggio replica](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="41e99-210">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 [<span data-ttu-id="41e99-211">Monitoraggio della replica</span><span class="sxs-lookup"><span data-stu-id="41e99-211">Monitoring Replication</span></span>](monitoring-replication.md)  
  
  
