---
title: Informazioni sul server di pubblicazione, Agenti | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.publisherinfo.commonjobs.f1
ms.assetid: 2346c00d-c269-45a1-af14-68e7fd7ebd7e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: bdd2055ed022257524bc4d2784bdc333537be855
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624038"
---
# <a name="publisher-information-agents"></a><span data-ttu-id="0ff84-102">Informazioni sul server di pubblicazione, Agenti</span><span class="sxs-lookup"><span data-stu-id="0ff84-102">Publisher Information, Agents</span></span>
  <span data-ttu-id="0ff84-103">Nella scheda **Agenti** vengono visualizzate le informazioni sugli agenti e sui processi di manutenzione associati al server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="0ff84-103">The **Agents** tab displays information about the agents and maintenance jobs that are associated with the Publisher:</span></span>  
  
-   <span data-ttu-id="0ff84-104">Agente snapshot, visualizzato per tutte le pubblicazioni.</span><span class="sxs-lookup"><span data-stu-id="0ff84-104">Snapshot Agent, which is displayed for all publications.</span></span>  
  
-   <span data-ttu-id="0ff84-105">Agente di lettura log, visualizzato per tutte le pubblicazioni transazionali.</span><span class="sxs-lookup"><span data-stu-id="0ff84-105">Log Reader Agent, which is displayed for all transactional publications.</span></span>  
  
-   <span data-ttu-id="0ff84-106">Agente di lettura coda, visualizzato per le pubblicazioni transazionali abilitate per le sottoscrizioni ad aggiornamento in coda.</span><span class="sxs-lookup"><span data-stu-id="0ff84-106">Queue Reader Agent, which is displayed for those transactional publications that are enabled for queued updating subscriptions.</span></span>  
  
-   <span data-ttu-id="0ff84-107">Processi di manutenzione, visualizzati per tutte le pubblicazioni:</span><span class="sxs-lookup"><span data-stu-id="0ff84-107">Maintenance jobs, displayed for all publications:</span></span>  
  
    -   <span data-ttu-id="0ff84-108">Reinizializzazione delle sottoscrizioni con errori di convalida dei dati</span><span class="sxs-lookup"><span data-stu-id="0ff84-108">Reinitialize subscriptions that have data validation failures</span></span>  
  
    -   <span data-ttu-id="0ff84-109">Pulizia del contenuto della cronologia dell'agente: distribuzione</span><span class="sxs-lookup"><span data-stu-id="0ff84-109">Agent history cleanup: distribution</span></span>  
  
    -   <span data-ttu-id="0ff84-110">Aggiornamento del monitoraggio della replica per la distribuzione</span><span class="sxs-lookup"><span data-stu-id="0ff84-110">Replication monitoring refresher for distribution</span></span>  
  
    -   <span data-ttu-id="0ff84-111">Controllo degli agenti di replica</span><span class="sxs-lookup"><span data-stu-id="0ff84-111">Replication agents checkup</span></span>  
  
    -   <span data-ttu-id="0ff84-112">Pulizia riferimenti distribuzione: distribuzione</span><span class="sxs-lookup"><span data-stu-id="0ff84-112">Distribution cleanup: distribution</span></span>  
  
    -   <span data-ttu-id="0ff84-113">Pulizia dei riferimenti alle sottoscrizioni scaduti</span><span class="sxs-lookup"><span data-stu-id="0ff84-113">Expired subscription cleanup</span></span>  
  
 <span data-ttu-id="0ff84-114">Per altre informazioni su questi processi, vedere [Amministrazione dell'agente di replica](agents/replication-agent-administration.md).</span><span class="sxs-lookup"><span data-stu-id="0ff84-114">For more information about these jobs, see [Replication Agent Administration](agents/replication-agent-administration.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="0ff84-115">Opzioni</span><span class="sxs-lookup"><span data-stu-id="0ff84-115">Options</span></span>  
 <span data-ttu-id="0ff84-116">Per visualizzare le informazioni su un agente o su un processo, scegliere l'elemento desiderato dal menu a discesa relativo ai **tipi di agente e processo**.</span><span class="sxs-lookup"><span data-stu-id="0ff84-116">To display information about an agent or job, select from the **Agent and Job Types** drop-down menu.</span></span> <span data-ttu-id="0ff84-117">Per ulteriori informazioni e per conoscere le attività correlate a un agente o a un processo, fare clic con il pulsante destro del mouse sulla riga dell'agente o del processo, quindi scegliere un'opzione dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="0ff84-117">For more detailed information and tasks that are related to an agent or job, right-click the row for that agent or job, and then click an option on the shortcut menu.</span></span> <span data-ttu-id="0ff84-118">Per modificare la modalità di visualizzazione dei dati nella griglia, fare clic con il pulsante destro del mouse sulla griglia, quindi scegliere una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0ff84-118">To change the way that the grid displays data, right-click the grid, and then click one of the following options:</span></span>  
  
-   <span data-ttu-id="0ff84-119">**Ordinamento**: consente di ordinare una o più colonne nella finestra di dialogo **Ordina colonne** .</span><span class="sxs-lookup"><span data-stu-id="0ff84-119">**Sort**: Sort on one or more columns in the **Sort Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="0ff84-120">**Seleziona colonne da visualizzare**: consente di selezionare le colonne da visualizzare e l'ordine di visualizzazione nella finestra di dialogo **Seleziona colonne** .</span><span class="sxs-lookup"><span data-stu-id="0ff84-120">**Choose Columns to Show**: Select which columns to display and the order in which to display them in the **Choose Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="0ff84-121">**Filtro**: consente di filtrare le righe nella griglia in base a valori di colonna nella finestra di dialogo **Impostazioni filtro** .</span><span class="sxs-lookup"><span data-stu-id="0ff84-121">**Filter**: Filter rows in the grid based on column values in the **Filter Settings** dialog box.</span></span>  
  
-   <span data-ttu-id="0ff84-122">**Cancella filtro**: consente di cancellare qualsiasi impostazione di filtro per la griglia.</span><span class="sxs-lookup"><span data-stu-id="0ff84-122">**Clear Filter**: Clear any filter settings for the grid.</span></span>  
  
 <span data-ttu-id="0ff84-123">Le impostazioni di filtro sono specifiche di ogni griglia.</span><span class="sxs-lookup"><span data-stu-id="0ff84-123">Filter settings are specific to each grid.</span></span> <span data-ttu-id="0ff84-124">La selezione e l'ordinamento delle colonne vengono applicati a tutte le griglie dello stesso tipo, ad esempio la griglia delle pubblicazioni per ogni server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="0ff84-124">Column selection and sorting are applied to all grids of the same type, such as the publications grid for each Publisher.</span></span>  
  
 <span data-ttu-id="0ff84-125">Nelle sezioni seguenti sono descritti i dati visualizzati in questa scheda per ogni agente o processo.</span><span class="sxs-lookup"><span data-stu-id="0ff84-125">The following sections describe the data that is displayed on this tab for each agent or job.</span></span>  
  
### <a name="snapshot-agent"></a><span data-ttu-id="0ff84-126">agente snapshot</span><span class="sxs-lookup"><span data-stu-id="0ff84-126">Snapshot Agent</span></span>  
 <span data-ttu-id="0ff84-127">**Status**</span><span class="sxs-lookup"><span data-stu-id="0ff84-127">**Status**</span></span>  
 <span data-ttu-id="0ff84-128">Stato dell'agente.</span><span class="sxs-lookup"><span data-stu-id="0ff84-128">The status of the agent.</span></span> <span data-ttu-id="0ff84-129">Nell'elenco seguente vengono indicati i valori di stato possibili:</span><span class="sxs-lookup"><span data-stu-id="0ff84-129">The following list shows the possible status values:</span></span>  
  
-   <span data-ttu-id="0ff84-130">Errore</span><span class="sxs-lookup"><span data-stu-id="0ff84-130">Error</span></span>  
  
-   <span data-ttu-id="0ff84-131">Riprova</span><span class="sxs-lookup"><span data-stu-id="0ff84-131">Retry</span></span>  
  
-   <span data-ttu-id="0ff84-132">In esecuzione</span><span class="sxs-lookup"><span data-stu-id="0ff84-132">Running</span></span>  
  
-   <span data-ttu-id="0ff84-133">Completi</span><span class="sxs-lookup"><span data-stu-id="0ff84-133">Completed</span></span>  
  
 <span data-ttu-id="0ff84-134">**Pubblicazione**</span><span class="sxs-lookup"><span data-stu-id="0ff84-134">**Publication**</span></span>  
 <span data-ttu-id="0ff84-135">Nome della pubblicazione a cui è associato l'agente.</span><span class="sxs-lookup"><span data-stu-id="0ff84-135">The name of the publication with which the agent is associated.</span></span>  
  
 <span data-ttu-id="0ff84-136">**Ultima ora inizio**</span><span class="sxs-lookup"><span data-stu-id="0ff84-136">**Last Start Time**</span></span>  
 <span data-ttu-id="0ff84-137">Ultima ora di avvio dell'agente.</span><span class="sxs-lookup"><span data-stu-id="0ff84-137">The last time at which the agent started.</span></span>  
  
 <span data-ttu-id="0ff84-138">**Duration**</span><span class="sxs-lookup"><span data-stu-id="0ff84-138">**Duration**</span></span>  
 <span data-ttu-id="0ff84-139">Quantità di tempo di esecuzione dell'agente.</span><span class="sxs-lookup"><span data-stu-id="0ff84-139">The length of time the agent has run.</span></span> <span data-ttu-id="0ff84-140">Il valore di durata rappresenta il tempo trascorso se l'agente è ancora in esecuzione e il tempo totale se l'agente è stato eseguito in precedenza.</span><span class="sxs-lookup"><span data-stu-id="0ff84-140">The time represents elapsed time if the agent is currently running, and total time if the agent has run previously.</span></span>  
  
 <span data-ttu-id="0ff84-141">**Ultima azione**</span><span class="sxs-lookup"><span data-stu-id="0ff84-141">**Last Action**</span></span>  
 <span data-ttu-id="0ff84-142">Ultima azione eseguita durante la più recente esecuzione dell'agente.</span><span class="sxs-lookup"><span data-stu-id="0ff84-142">The last action performed during the most recent run of the agent.</span></span>  
  
 <span data-ttu-id="0ff84-143">**Frequenza recapito**</span><span class="sxs-lookup"><span data-stu-id="0ff84-143">**Delivery Rate**</span></span>  
 <span data-ttu-id="0ff84-144">Frequenza, in comandi al secondo, con cui viene eseguito il commit dei comandi di inizializzazione nel database di distribuzione durante la più recente esecuzione dell'agente.</span><span class="sxs-lookup"><span data-stu-id="0ff84-144">The rate, in commands per second, at which initialization commands are committed in the distribution database during the most recent run of the agent.</span></span>  
  
 <span data-ttu-id="0ff84-145">**N. transazioni**</span><span class="sxs-lookup"><span data-stu-id="0ff84-145">**#Trans**</span></span>  
 <span data-ttu-id="0ff84-146">Numero di transazioni di cui è stato eseguito il commit nel database di distribuzione durante la più recente esecuzione dell'agente.</span><span class="sxs-lookup"><span data-stu-id="0ff84-146">The number of transactions committed in the distribution database during the most recent run of the agent.</span></span>  
  
 <span data-ttu-id="0ff84-147">**N. comandi**</span><span class="sxs-lookup"><span data-stu-id="0ff84-147">**#Cmds**</span></span>  
 <span data-ttu-id="0ff84-148">Numero di comandi di cui è stato eseguito il commit nel database di distribuzione durante la più recente esecuzione dell'agente.</span><span class="sxs-lookup"><span data-stu-id="0ff84-148">The number of commands committed in the distribution database during the most recent run of the agent.</span></span> <span data-ttu-id="0ff84-149">Un comando è equivalente a una modifica dei dati, ad esempio un aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="0ff84-149">A command is equivalent to a data change, such as an update.</span></span>  
  
### <a name="log-reader-agent"></a><span data-ttu-id="0ff84-150">Agente di lettura log</span><span class="sxs-lookup"><span data-stu-id="0ff84-150">Log Reader Agent</span></span>  
 <span data-ttu-id="0ff84-151">**Status**</span><span class="sxs-lookup"><span data-stu-id="0ff84-151">**Status**</span></span>  
 <span data-ttu-id="0ff84-152">Stato dell'agente.</span><span class="sxs-lookup"><span data-stu-id="0ff84-152">The status of the agent.</span></span> <span data-ttu-id="0ff84-153">Nell'elenco seguente vengono indicati i valori di stato possibili:</span><span class="sxs-lookup"><span data-stu-id="0ff84-153">The following list shows the possible status values:</span></span>  
  
-   <span data-ttu-id="0ff84-154">Errore</span><span class="sxs-lookup"><span data-stu-id="0ff84-154">Error</span></span>  
  
-   <span data-ttu-id="0ff84-155">Riprova</span><span class="sxs-lookup"><span data-stu-id="0ff84-155">Retry</span></span>  
  
-   <span data-ttu-id="0ff84-156">In esecuzione</span><span class="sxs-lookup"><span data-stu-id="0ff84-156">Running</span></span>  
  
-   <span data-ttu-id="0ff84-157">Non in esecuzione</span><span class="sxs-lookup"><span data-stu-id="0ff84-157">Not running</span></span>  
  
 <span data-ttu-id="0ff84-158">**Database di pubblicazione**</span><span class="sxs-lookup"><span data-stu-id="0ff84-158">**Publication Database**</span></span>  
 <span data-ttu-id="0ff84-159">Nome della pubblicazione a cui è associato l'agente.</span><span class="sxs-lookup"><span data-stu-id="0ff84-159">The name of the publication with which the agent is associated.</span></span>  
  
 <span data-ttu-id="0ff84-160">**Ultima ora inizio**</span><span class="sxs-lookup"><span data-stu-id="0ff84-160">**Last Start Time**</span></span>  
 <span data-ttu-id="0ff84-161">Ultima ora di avvio dell'agente.</span><span class="sxs-lookup"><span data-stu-id="0ff84-161">The last time at which the agent started.</span></span>  
  
 <span data-ttu-id="0ff84-162">**Duration**</span><span class="sxs-lookup"><span data-stu-id="0ff84-162">**Duration**</span></span>  
 <span data-ttu-id="0ff84-163">Quantità di tempo di esecuzione dell'agente.</span><span class="sxs-lookup"><span data-stu-id="0ff84-163">The length of time the agent has run.</span></span> <span data-ttu-id="0ff84-164">Il valore di durata rappresenta il tempo trascorso se l'agente è ancora in esecuzione e il tempo totale se l'agente è stato eseguito in precedenza.</span><span class="sxs-lookup"><span data-stu-id="0ff84-164">The time represents elapsed time if the agent is currently running, and total time if the agent has run previously.</span></span>  
  
 <span data-ttu-id="0ff84-165">**Ultima azione**</span><span class="sxs-lookup"><span data-stu-id="0ff84-165">**Last Action**</span></span>  
 <span data-ttu-id="0ff84-166">Ultima azione eseguita durante la più recente esecuzione dell'agente.</span><span class="sxs-lookup"><span data-stu-id="0ff84-166">The last action performed during the most recent run of the agent.</span></span>  
  
 <span data-ttu-id="0ff84-167">**Frequenza recapito**</span><span class="sxs-lookup"><span data-stu-id="0ff84-167">**Delivery Rate**</span></span>  
 <span data-ttu-id="0ff84-168">Frequenza, in comandi al secondo, con cui viene eseguito il commit delle modifiche nel database di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="0ff84-168">The rate, in commands per second, at which changes are committed in the distribution database.</span></span>  
  
 <span data-ttu-id="0ff84-169">**Latency**</span><span class="sxs-lookup"><span data-stu-id="0ff84-169">**Latency**</span></span>  
 <span data-ttu-id="0ff84-170">Quantità di tempo, in secondi, trascorsa tra il commit della modifica più recente nel database di pubblicazione e il commit del comando corrispondente nel database di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="0ff84-170">The amount of time, in seconds, that has elapsed between the most recent change being committed in the publication database, and the corresponding command being committed in the distribution database.</span></span>  
  
 <span data-ttu-id="0ff84-171">**N. transazioni**</span><span class="sxs-lookup"><span data-stu-id="0ff84-171">**#Trans**</span></span>  
 <span data-ttu-id="0ff84-172">Numero di transazioni di cui è stato eseguito il commit nel database di distribuzione durante la più recente esecuzione dell'agente.</span><span class="sxs-lookup"><span data-stu-id="0ff84-172">The number of transactions committed in the distribution database during the most recent run of the agent.</span></span>  
  
 <span data-ttu-id="0ff84-173">**N. comandi**</span><span class="sxs-lookup"><span data-stu-id="0ff84-173">**#Cmds**</span></span>  
 <span data-ttu-id="0ff84-174">Numero di comandi di cui è stato eseguito il commit nel database di distribuzione durante la più recente esecuzione dell'agente.</span><span class="sxs-lookup"><span data-stu-id="0ff84-174">The number of commands committed in the distribution database during the most recent run of the agent.</span></span> <span data-ttu-id="0ff84-175">Un comando è equivalente a una modifica dei dati, ad esempio un aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="0ff84-175">A command is equivalent to a data change, such as an update.</span></span>  
  
 <span data-ttu-id="0ff84-176">**Media n. comandi**</span><span class="sxs-lookup"><span data-stu-id="0ff84-176">**Avg. #Cmds**</span></span>  
 <span data-ttu-id="0ff84-177">Numero medio di comandi per transazione durante la più recente esecuzione dell'agente.</span><span class="sxs-lookup"><span data-stu-id="0ff84-177">The average number of commands per transaction during the most recent run of the agent.</span></span>  
  
### <a name="queue-reader-agent"></a><span data-ttu-id="0ff84-178">Agente di lettura coda</span><span class="sxs-lookup"><span data-stu-id="0ff84-178">Queue Reader Agent</span></span>  
 <span data-ttu-id="0ff84-179">**Status**</span><span class="sxs-lookup"><span data-stu-id="0ff84-179">**Status**</span></span>  
 <span data-ttu-id="0ff84-180">Stato dell'agente.</span><span class="sxs-lookup"><span data-stu-id="0ff84-180">The status of the agent.</span></span> <span data-ttu-id="0ff84-181">Nell'elenco seguente vengono indicati i valori di stato possibili:</span><span class="sxs-lookup"><span data-stu-id="0ff84-181">The following list shows the possible status values:</span></span>  
  
-   <span data-ttu-id="0ff84-182">Errore</span><span class="sxs-lookup"><span data-stu-id="0ff84-182">Error</span></span>  
  
-   <span data-ttu-id="0ff84-183">Riprova</span><span class="sxs-lookup"><span data-stu-id="0ff84-183">Retry</span></span>  
  
-   <span data-ttu-id="0ff84-184">In esecuzione</span><span class="sxs-lookup"><span data-stu-id="0ff84-184">Running</span></span>  
  
-   <span data-ttu-id="0ff84-185">Non in esecuzione</span><span class="sxs-lookup"><span data-stu-id="0ff84-185">Not running</span></span>  
  
 <span data-ttu-id="0ff84-186">**Database di distribuzione**</span><span class="sxs-lookup"><span data-stu-id="0ff84-186">**Distribution Database**</span></span>  
 <span data-ttu-id="0ff84-187">Nome del database di distribuzione a cui è associato l'agente.</span><span class="sxs-lookup"><span data-stu-id="0ff84-187">The name of the distribution database with which the agent is associated.</span></span>  
  
 <span data-ttu-id="0ff84-188">**Ultima ora inizio**</span><span class="sxs-lookup"><span data-stu-id="0ff84-188">**Last Start Time**</span></span>  
 <span data-ttu-id="0ff84-189">Ultima ora di avvio dell'agente.</span><span class="sxs-lookup"><span data-stu-id="0ff84-189">The last time at which the agent started.</span></span>  
  
 <span data-ttu-id="0ff84-190">**Duration**</span><span class="sxs-lookup"><span data-stu-id="0ff84-190">**Duration**</span></span>  
 <span data-ttu-id="0ff84-191">Quantità di tempo di esecuzione dell'agente.</span><span class="sxs-lookup"><span data-stu-id="0ff84-191">The length of time the agent has run.</span></span> <span data-ttu-id="0ff84-192">Il valore di durata rappresenta il tempo trascorso se l'agente è ancora in esecuzione e la durata totale se l'agente è stato eseguito in precedenza.</span><span class="sxs-lookup"><span data-stu-id="0ff84-192">The time represents elapsed time if the agent is currently running and total time if the agent has run previously.</span></span>  
  
 <span data-ttu-id="0ff84-193">**Ultima azione**</span><span class="sxs-lookup"><span data-stu-id="0ff84-193">**Last Action**</span></span>  
 <span data-ttu-id="0ff84-194">Ultima azione eseguita durante la più recente esecuzione dell'agente.</span><span class="sxs-lookup"><span data-stu-id="0ff84-194">The last action performed during the most recent run of the agent.</span></span>  
  
 <span data-ttu-id="0ff84-195">**Frequenza recapito**</span><span class="sxs-lookup"><span data-stu-id="0ff84-195">**Delivery Rate**</span></span>  
 <span data-ttu-id="0ff84-196">Frequenza, in comandi al secondo, con cui viene eseguito il commit delle modifiche nel database di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="0ff84-196">The rate, in commands per second, at which changes are committed in the distribution database.</span></span>  
  
 <span data-ttu-id="0ff84-197">**Latency**</span><span class="sxs-lookup"><span data-stu-id="0ff84-197">**Latency**</span></span>  
 <span data-ttu-id="0ff84-198">Quantità di tempo, in secondi, trascorsa tra il commit della modifica più recente in un database di sottoscrizione e il commit del comando corrispondente nel database di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="0ff84-198">The amount of time, in seconds, that has elapsed between the most recent change being committed in a subscription database, and the corresponding command being committed in the publication database.</span></span>  
  
 <span data-ttu-id="0ff84-199">**N. transazioni**</span><span class="sxs-lookup"><span data-stu-id="0ff84-199">**#Trans**</span></span>  
 <span data-ttu-id="0ff84-200">Numero di transazioni di cui è stato eseguito il commit nel database di pubblicazione durante la più recente esecuzione dell'agente.</span><span class="sxs-lookup"><span data-stu-id="0ff84-200">The number of transactions committed in the publication database during the most recent run of the agent.</span></span>  
  
 <span data-ttu-id="0ff84-201">**N. comandi**</span><span class="sxs-lookup"><span data-stu-id="0ff84-201">**#Cmds**</span></span>  
 <span data-ttu-id="0ff84-202">Numero di comandi di cui è stato eseguito il commit nel database di pubblicazione durante la più recente esecuzione dell'agente.</span><span class="sxs-lookup"><span data-stu-id="0ff84-202">The number of commands committed in the publication database during the most recent run of the agent.</span></span> <span data-ttu-id="0ff84-203">Un comando è equivalente a una modifica dei dati, ad esempio un aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="0ff84-203">A command is equivalent to a data change, such as an update.</span></span>  
  
 <span data-ttu-id="0ff84-204">**Media n. comandi**</span><span class="sxs-lookup"><span data-stu-id="0ff84-204">**Avg. #Cmds**</span></span>  
 <span data-ttu-id="0ff84-205">Numero medio di comandi per transazione durante la più recente esecuzione dell'agente.</span><span class="sxs-lookup"><span data-stu-id="0ff84-205">The average number of commands per transaction during the most recent run of the agent.</span></span>  
  
### <a name="maintenance-jobs"></a><span data-ttu-id="0ff84-206">Processi di manutenzione</span><span class="sxs-lookup"><span data-stu-id="0ff84-206">Maintenance Jobs</span></span>  
 <span data-ttu-id="0ff84-207">**Status**</span><span class="sxs-lookup"><span data-stu-id="0ff84-207">**Status**</span></span>  
 <span data-ttu-id="0ff84-208">Stato di ogni processo.</span><span class="sxs-lookup"><span data-stu-id="0ff84-208">The status of each job.</span></span> <span data-ttu-id="0ff84-209">Nell'elenco seguente vengono indicati i valori di stato possibili:</span><span class="sxs-lookup"><span data-stu-id="0ff84-209">The following list shows the possible status values:</span></span>  
  
-   <span data-ttu-id="0ff84-210">Errore</span><span class="sxs-lookup"><span data-stu-id="0ff84-210">Error</span></span>  
  
-   <span data-ttu-id="0ff84-211">Riprova</span><span class="sxs-lookup"><span data-stu-id="0ff84-211">Retry</span></span>  
  
-   <span data-ttu-id="0ff84-212">In esecuzione</span><span class="sxs-lookup"><span data-stu-id="0ff84-212">Running</span></span>  
  
-   <span data-ttu-id="0ff84-213">Non in esecuzione</span><span class="sxs-lookup"><span data-stu-id="0ff84-213">Not running</span></span>  
  
 <span data-ttu-id="0ff84-214">**Processo**</span><span class="sxs-lookup"><span data-stu-id="0ff84-214">**Job**</span></span>  
 <span data-ttu-id="0ff84-215">Nome del processo.</span><span class="sxs-lookup"><span data-stu-id="0ff84-215">The name of the job.</span></span>  
  
 <span data-ttu-id="0ff84-216">**Ultima ora inizio**</span><span class="sxs-lookup"><span data-stu-id="0ff84-216">**Last Start Time**</span></span>  
 <span data-ttu-id="0ff84-217">Ultima ora di inizio del processo.</span><span class="sxs-lookup"><span data-stu-id="0ff84-217">The last time at which the job started.</span></span>  
  
 <span data-ttu-id="0ff84-218">**Duration**</span><span class="sxs-lookup"><span data-stu-id="0ff84-218">**Duration**</span></span>  
 <span data-ttu-id="0ff84-219">Tempo di esecuzione del processo.</span><span class="sxs-lookup"><span data-stu-id="0ff84-219">The length of time the job has run.</span></span> <span data-ttu-id="0ff84-220">Il valore di durata rappresenta il tempo trascorso se il processo è ancora in esecuzione e la durata totale se il processo è stato eseguito in precedenza.</span><span class="sxs-lookup"><span data-stu-id="0ff84-220">The time represents elapsed time if the job is currently running, and total time if the job has run previously.</span></span>  
  
 <span data-ttu-id="0ff84-221">**Ultima azione**</span><span class="sxs-lookup"><span data-stu-id="0ff84-221">**Last Action**</span></span>  
 <span data-ttu-id="0ff84-222">Ultima azione eseguita durante la più recente esecuzione del processo.</span><span class="sxs-lookup"><span data-stu-id="0ff84-222">The last action performed during the most recent run of the job.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ff84-223">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0ff84-223">See Also</span></span>  
 <span data-ttu-id="0ff84-224">[Avviare Monitoraggio replica](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="0ff84-224">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="0ff84-225">[Visualizzare le informazioni ed eseguire attività usando Monitoraggio replica](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="0ff84-225">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 [<span data-ttu-id="0ff84-226">Monitoraggio della replica</span><span class="sxs-lookup"><span data-stu-id="0ff84-226">Monitoring Replication</span></span>](monitoring-replication.md)  
  
  
