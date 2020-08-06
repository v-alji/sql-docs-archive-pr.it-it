---
title: Sottoscrizione, Cronologia sincronizzazione (sottoscrizione di tipo merge, SQL Server 2005 e versioni successive) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.subscription.synchhistory.f1
- sql12.rep.monitor.subscription.downlevelsynchhistory.f1
ms.assetid: 85f666f6-14ee-4f19-b385-e5cc508aabe4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 49fe19f22976116813ac2454b2d08fc1fe47d8de
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636024"
---
# <a name="subscription-synchronization-history-merge-subscription-sql-server-2005-and-later"></a><span data-ttu-id="8d472-102">Sottoscrizione, Cronologia sincronizzazione (Sottoscrizione di tipo merge, SQL Server 2005 e versioni successive)</span><span class="sxs-lookup"><span data-stu-id="8d472-102">Subscription, Synchronization History (Merge Subscription, SQL Server 2005 and Later)</span></span>
  <span data-ttu-id="8d472-103">La scheda **Cronologia sincronizzazione** visualizza informazioni dettagliate sull'agente di merge, tra cui lo stato, le statistiche degli articoli, la cronologia, i messaggi informativi e gli eventuali messaggi di errore.</span><span class="sxs-lookup"><span data-stu-id="8d472-103">The **Synchronization History** tab displays detailed information on the Merge Agent, including status, article statistics, history, informational messages, and any error messages.</span></span>  
  
## <a name="options"></a><span data-ttu-id="8d472-104">Opzioni</span><span class="sxs-lookup"><span data-stu-id="8d472-104">Options</span></span>  
 <span data-ttu-id="8d472-105">Scegliere le sessioni dell'agente di merge da visualizzare dal menu **Visualizza** e quindi selezionare una sessione specifica nella griglia con l'etichetta **Sessioni dell'agente di merge**.</span><span class="sxs-lookup"><span data-stu-id="8d472-105">Select which Merge Agent sessions to view from the **View** menu, and then select a specific session in the grid labeled **Sessions of the Merge Agent**.</span></span> <span data-ttu-id="8d472-106">Nella griglia con l'etichetta **Articoli elaborati nella sessione selezionata**vengono visualizzate informazioni dettagliate sulla sessione.</span><span class="sxs-lookup"><span data-stu-id="8d472-106">Detailed information on this session is displayed in the grid labeled **Articles processed in the selected session**.</span></span>  
  
 <span data-ttu-id="8d472-107">**Visualizza**</span><span class="sxs-lookup"><span data-stu-id="8d472-107">**View**</span></span>  
 <span data-ttu-id="8d472-108">Consente di selezionare l'agente di merge da visualizzare.</span><span class="sxs-lookup"><span data-stu-id="8d472-108">Select which Merge Agent sessions to view.</span></span>  
  
 <span data-ttu-id="8d472-109">**Status**</span><span class="sxs-lookup"><span data-stu-id="8d472-109">**Status**</span></span>  
 <span data-ttu-id="8d472-110">Stato dell'agente di merge al termine della sessione.</span><span class="sxs-lookup"><span data-stu-id="8d472-110">The status of the Merge Agent at the end of the session.</span></span> <span data-ttu-id="8d472-111">Nell'elenco seguente vengono indicati i valori di stato possibili:</span><span class="sxs-lookup"><span data-stu-id="8d472-111">The following list shows the possible status values:</span></span>  
  
-   <span data-ttu-id="8d472-112">Errore</span><span class="sxs-lookup"><span data-stu-id="8d472-112">Error</span></span>  
  
-   <span data-ttu-id="8d472-113">Completi</span><span class="sxs-lookup"><span data-stu-id="8d472-113">Completed</span></span>  
  
-   <span data-ttu-id="8d472-114">Nuovo tentativo in corso</span><span class="sxs-lookup"><span data-stu-id="8d472-114">Retrying</span></span>  
  
-   <span data-ttu-id="8d472-115">In esecuzione</span><span class="sxs-lookup"><span data-stu-id="8d472-115">Running</span></span>  
  
 <span data-ttu-id="8d472-116">**Start Time**</span><span class="sxs-lookup"><span data-stu-id="8d472-116">**Start Time**</span></span>  
 <span data-ttu-id="8d472-117">Ora di inizio della sessione.</span><span class="sxs-lookup"><span data-stu-id="8d472-117">The start time of the session.</span></span>  
  
 <span data-ttu-id="8d472-118">**Ora fine**</span><span class="sxs-lookup"><span data-stu-id="8d472-118">**End Time**</span></span>  
 <span data-ttu-id="8d472-119">Ora di fine della sessione.</span><span class="sxs-lookup"><span data-stu-id="8d472-119">The end time of the session.</span></span> <span data-ttu-id="8d472-120">Se l'agente non è arrestato, questo campo è vuoto.</span><span class="sxs-lookup"><span data-stu-id="8d472-120">If the agent has not stopped, this field is empty.</span></span>  
  
 <span data-ttu-id="8d472-121">**Duration**</span><span class="sxs-lookup"><span data-stu-id="8d472-121">**Duration**</span></span>  
 <span data-ttu-id="8d472-122">Quantità di tempo di esecuzione dell'agente di merge in una sessione.</span><span class="sxs-lookup"><span data-stu-id="8d472-122">The amount of time the Merge Agent has run in a session.</span></span> <span data-ttu-id="8d472-123">Il valore di durata rappresenta il tempo trascorso se l'agente è ancora in esecuzione e la durata totale se l'agente è stato eseguito in precedenza.</span><span class="sxs-lookup"><span data-stu-id="8d472-123">The time represents elapsed time if the agent is currently running and total time if the agent has run previously.</span></span>  
  
 <span data-ttu-id="8d472-124">**Comandi caricati**</span><span class="sxs-lookup"><span data-stu-id="8d472-124">**Uploaded Commands**</span></span>  
 <span data-ttu-id="8d472-125">Numero di righe caricate durante la sessione dell'agente di merge.</span><span class="sxs-lookup"><span data-stu-id="8d472-125">The number of rows uploaded during the Merge Agent session.</span></span>  
  
 <span data-ttu-id="8d472-126">**Comandi scaricati**</span><span class="sxs-lookup"><span data-stu-id="8d472-126">**Downloaded Commands**</span></span>  
 <span data-ttu-id="8d472-127">Numero di righe scaricate durante la sessione dell'agente di merge.</span><span class="sxs-lookup"><span data-stu-id="8d472-127">The number of rows downloaded during the Merge Agent session.</span></span>  
  
 <span data-ttu-id="8d472-128">**Messaggio di errore**</span><span class="sxs-lookup"><span data-stu-id="8d472-128">**Error Message**</span></span>  
 <span data-ttu-id="8d472-129">Se una sessione è terminata con un errore, in questo campo viene visualizzato l'ultimo messaggio di errore registrato dall'agente di merge.</span><span class="sxs-lookup"><span data-stu-id="8d472-129">If a session ended in an error, this field displays the last error message logged by the Merge Agent.</span></span> <span data-ttu-id="8d472-130">Se una sessione non è terminata con un errore, questo campo è vuoto.</span><span class="sxs-lookup"><span data-stu-id="8d472-130">If a session did not end in an error, this field is blank.</span></span>  
  
 <span data-ttu-id="8d472-131">**Articolo**</span><span class="sxs-lookup"><span data-stu-id="8d472-131">**Article**</span></span>  
 <span data-ttu-id="8d472-132">Il nome di ogni articolo della pubblicazione e le fasi di elaborazione seguenti per l'intera pubblicazione:</span><span class="sxs-lookup"><span data-stu-id="8d472-132">The name of each article in the publication, and the following processing phases for the entire publication:</span></span>  
  
-   <span data-ttu-id="8d472-133">**Inizializzazione**.</span><span class="sxs-lookup"><span data-stu-id="8d472-133">**Initialization**.</span></span> <span data-ttu-id="8d472-134">Si riferisce all'avvio dell'agente di merge e non all'inizializzazione di una sottoscrizione, che invece implica l'applicazione di uno snapshot.</span><span class="sxs-lookup"><span data-stu-id="8d472-134">This refers to starting the Merge Agent; this is not synonymous with initializing a subscription, which involves applying a snapshot.</span></span>  
  
-   <span data-ttu-id="8d472-135">**Modifiche dello schema e inserimenti bulk**.</span><span class="sxs-lookup"><span data-stu-id="8d472-135">**Schema changes and bulk inserts**.</span></span>  
  
-   <span data-ttu-id="8d472-136">**Carica modifiche nel server di pubblicazione**.</span><span class="sxs-lookup"><span data-stu-id="8d472-136">**Upload changes to Publisher**.</span></span>  
  
-   <span data-ttu-id="8d472-137">**Download modifiche nel Sottoscrittore**.</span><span class="sxs-lookup"><span data-stu-id="8d472-137">**Download changes to Subscriber**.</span></span>  
  
 <span data-ttu-id="8d472-138">Le fasi sono incluse in modo che nella griglia sia possibile visualizzare la quantità di tempo e la percentuale della durata totale riferite a ogni fase della sessione selezionata.</span><span class="sxs-lookup"><span data-stu-id="8d472-138">The phases are included so that the grid can display the amount of time and percentage of total time that each phase accounts for in the selected session.</span></span>  
  
 <span data-ttu-id="8d472-139">**% del totale**</span><span class="sxs-lookup"><span data-stu-id="8d472-139">**% of total**</span></span>  
 <span data-ttu-id="8d472-140">Percentuale del tempo di elaborazione totale riferita a ogni fase della sessione selezionata.</span><span class="sxs-lookup"><span data-stu-id="8d472-140">The percentage of total processing time that each phase accounts for in the selected session.</span></span>  
  
 <span data-ttu-id="8d472-141">**Duration**</span><span class="sxs-lookup"><span data-stu-id="8d472-141">**Duration**</span></span>  
 <span data-ttu-id="8d472-142">Quantità di tempo utilizzata per ogni fase di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="8d472-142">The amount of time spent in each processing phase.</span></span> <span data-ttu-id="8d472-143">Il valore di durata rappresenta il tempo trascorso se l'agente di merge è attualmente in esecuzione per la sessione e la durata totale se l'agente di merge è stato eseguito in precedenza.</span><span class="sxs-lookup"><span data-stu-id="8d472-143">The time represents elapsed time if the Merge Agent is currently running for the session and total time if the Merge Agent has run previously.</span></span>  
  
 <span data-ttu-id="8d472-144">**Inserts**</span><span class="sxs-lookup"><span data-stu-id="8d472-144">**Inserts**</span></span>  
 <span data-ttu-id="8d472-145">Numero di righe inserite nella fase specifica della sessione selezionata.</span><span class="sxs-lookup"><span data-stu-id="8d472-145">The number of rows inserted in this phase of the selected session.</span></span>  
  
 <span data-ttu-id="8d472-146">**Aggiornamenti**</span><span class="sxs-lookup"><span data-stu-id="8d472-146">**Updates**</span></span>  
 <span data-ttu-id="8d472-147">Numero di righe aggiornate nella fase specifica della sessione selezionata.</span><span class="sxs-lookup"><span data-stu-id="8d472-147">The number of rows updated in this phase of the selected session.</span></span>  
  
 <span data-ttu-id="8d472-148">**Eliminazioni**</span><span class="sxs-lookup"><span data-stu-id="8d472-148">**Deletes**</span></span>  
 <span data-ttu-id="8d472-149">Numero di righe eliminate nella fase specifica della sessione selezionata.</span><span class="sxs-lookup"><span data-stu-id="8d472-149">The number of rows deleted in this phase of the selected session.</span></span>  
  
 <span data-ttu-id="8d472-150">**Conflitti**</span><span class="sxs-lookup"><span data-stu-id="8d472-150">**Conflicts**</span></span>  
 <span data-ttu-id="8d472-151">Numero di conflitti nella sessione selezionata.</span><span class="sxs-lookup"><span data-stu-id="8d472-151">The number of conflicts in the selected session.</span></span>  
  
 <span data-ttu-id="8d472-152">**Modifiche dello schema**</span><span class="sxs-lookup"><span data-stu-id="8d472-152">**Schema Changes**</span></span>  
 <span data-ttu-id="8d472-153">Numero di modifiche dello schema nella sessione selezionata.</span><span class="sxs-lookup"><span data-stu-id="8d472-153">The number of schema changes in the selected session.</span></span> <span data-ttu-id="8d472-154">Le modifiche dello schema possono dipendere da modifiche dello schema apportate al database della pubblicazione, dall'aggiunta o eliminazione di articoli e da modifiche delle proprietà dell'articolo o della pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="8d472-154">Schema changes can result from: schema changes being replicated from the publication database; adding or dropping articles; and changes to article or publication properties.</span></span>  
  
 <span data-ttu-id="8d472-155">**Ultimo messaggio della sessione selezionata**</span><span class="sxs-lookup"><span data-stu-id="8d472-155">**Last message of the selected session**</span></span>  
 <span data-ttu-id="8d472-156">In quest'area di testo viene visualizzato l'ultimo messaggio della sessione selezionata.</span><span class="sxs-lookup"><span data-stu-id="8d472-156">This text area displays the last message in the selected session.</span></span> <span data-ttu-id="8d472-157">Se si è verificato un errore, vengono visualizzate informazioni dettagliate sull'errore e il comando di cui si è tentata l'esecuzione al momento dell'errore.</span><span class="sxs-lookup"><span data-stu-id="8d472-157">If an error has occurred, it displays detailed error information and the command that was attempted at the time of the error.</span></span> <span data-ttu-id="8d472-158">Sono inoltre disponibili collegamenti a contenuto aggiuntivo correlato all'errore.</span><span class="sxs-lookup"><span data-stu-id="8d472-158">It also includes links to additional content related to the error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d472-159">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8d472-159">See Also</span></span>  
 <span data-ttu-id="8d472-160">[Avviare Monitoraggio replica](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="8d472-160">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="8d472-161">[Visualizzare le informazioni ed eseguire attività usando Monitoraggio replica](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="8d472-161">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 <span data-ttu-id="8d472-162">[Monitoraggio della replica](monitoring-replication.md) </span><span class="sxs-lookup"><span data-stu-id="8d472-162">[Monitoring Replication](monitoring-replication.md) </span></span>  
 [<span data-ttu-id="8d472-163">Panoramica degli agenti di replica</span><span class="sxs-lookup"><span data-stu-id="8d472-163">Replication Agents Overview</span></span>](agents/replication-agents-overview.md)  
  
  
