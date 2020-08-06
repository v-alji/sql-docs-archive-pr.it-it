---
title: Sottoscrizione, Cronologia server di pubblicazione - database di distribuzione (sottoscrizione transazionale) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.subscription.pubtodist.tran.f1
ms.assetid: d5a4c697-1342-49fd-8b7b-b059af32556a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3806c59e545e325fa7e60f2cd92a4b990b0505cc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726884"
---
# <a name="subscription-publisher-to-distributor-history-transactional-subscription"></a><span data-ttu-id="9ac4d-102">Sottoscrizione, Cronologia server di pubblicazione - server di distribuzione (sottoscrizione transazionale)</span><span class="sxs-lookup"><span data-stu-id="9ac4d-102">Subscription, Publisher to Distributor History (Transactional Subscription)</span></span>
  <span data-ttu-id="9ac4d-103">Nella scheda **Cronologia server di pubblicazione - server di distribuzione** vengono visualizzate informazioni dettagliate sull'agente di lettura log, quali lo stato, la cronologia, i messaggi informativi ed eventuali messaggi di errore.</span><span class="sxs-lookup"><span data-stu-id="9ac4d-103">The **Publisher to Distributor History** tab displays detailed information on the Log Reader Agent, including status, history, informational messages, and any error messages.</span></span>  
  
## <a name="options"></a><span data-ttu-id="9ac4d-104">Opzioni</span><span class="sxs-lookup"><span data-stu-id="9ac4d-104">Options</span></span>  
 <span data-ttu-id="9ac4d-105">Scegliere le sessioni dell'agente di lettura log da visualizzare dal menu **Visualizza** e quindi selezionare una sessione specifica nella griglia con etichetta **Sessioni dell'agente di lettura log**.</span><span class="sxs-lookup"><span data-stu-id="9ac4d-105">Select which Log Reader Agent sessions to view from the **View** menu, and then select a specific session in the grid labeled **Sessions of the Log Reader Agent**.</span></span> <span data-ttu-id="9ac4d-106">Nella griglia con etichetta **Azioni nella sessione selezionata**verranno visualizzate informazioni dettagliate sulla sessione selezionata.</span><span class="sxs-lookup"><span data-stu-id="9ac4d-106">Detailed information on this session is displayed in the grid labeled **Actions in the selected session**.</span></span> <span data-ttu-id="9ac4d-107">Se la sessione selezionata è terminata con un errore, verrà inoltre visualizzata l'area di testo con etichetta **Messaggio o dettagli errore della sessione selezionata** .</span><span class="sxs-lookup"><span data-stu-id="9ac4d-107">If the selected session ended in an error, the text area labeled **Error details or message of the selected session** is also displayed.</span></span>  
  
 <span data-ttu-id="9ac4d-108">**Visualizzazione**</span><span class="sxs-lookup"><span data-stu-id="9ac4d-108">**View**</span></span>  
 <span data-ttu-id="9ac4d-109">Selezionare le sessioni dell'agente di lettura log da visualizzare.</span><span class="sxs-lookup"><span data-stu-id="9ac4d-109">Select which Log Reader Agent sessions to view.</span></span> <span data-ttu-id="9ac4d-110">L'agente di lettura log in genere viene eseguito in modo continuo, pertanto potrebbe essere disponibile una sola sessione da visualizzare.</span><span class="sxs-lookup"><span data-stu-id="9ac4d-110">The Log Reader Agent typically runs continuously, therefore there might be only one session to view.</span></span>  
  
 <span data-ttu-id="9ac4d-111">**Status**</span><span class="sxs-lookup"><span data-stu-id="9ac4d-111">**Status**</span></span>  
 <span data-ttu-id="9ac4d-112">Stato dell'agente di lettura log.</span><span class="sxs-lookup"><span data-stu-id="9ac4d-112">The status of the Log Reader Agent.</span></span> <span data-ttu-id="9ac4d-113">Nell'elenco seguente vengono indicati i valori di stato possibili:</span><span class="sxs-lookup"><span data-stu-id="9ac4d-113">The following list shows the possible status values:</span></span>  
  
-   <span data-ttu-id="9ac4d-114">Errore</span><span class="sxs-lookup"><span data-stu-id="9ac4d-114">Error</span></span>  
  
-   <span data-ttu-id="9ac4d-115">Completi</span><span class="sxs-lookup"><span data-stu-id="9ac4d-115">Completed</span></span>  
  
-   <span data-ttu-id="9ac4d-116">Nuovo tentativo in corso</span><span class="sxs-lookup"><span data-stu-id="9ac4d-116">Retrying</span></span>  
  
-   <span data-ttu-id="9ac4d-117">In esecuzione</span><span class="sxs-lookup"><span data-stu-id="9ac4d-117">Running</span></span>  
  
 <span data-ttu-id="9ac4d-118">**Ora di inizio**</span><span class="sxs-lookup"><span data-stu-id="9ac4d-118">**Start Time**</span></span>  
 <span data-ttu-id="9ac4d-119">Ora di inizio della sessione.</span><span class="sxs-lookup"><span data-stu-id="9ac4d-119">The start time of the session.</span></span>  
  
 <span data-ttu-id="9ac4d-120">**Ora di fine**</span><span class="sxs-lookup"><span data-stu-id="9ac4d-120">**End Time**</span></span>  
 <span data-ttu-id="9ac4d-121">Ora di fine della sessione.</span><span class="sxs-lookup"><span data-stu-id="9ac4d-121">The end time of the session.</span></span> <span data-ttu-id="9ac4d-122">Se l'agente non è arrestato, questo campo è vuoto.</span><span class="sxs-lookup"><span data-stu-id="9ac4d-122">If the agent has not stopped, this field is empty.</span></span>  
  
 <span data-ttu-id="9ac4d-123">**Duration**</span><span class="sxs-lookup"><span data-stu-id="9ac4d-123">**Duration**</span></span>  
 <span data-ttu-id="9ac4d-124">Periodo di tempo durante il quale l'agente di lettura log è stato eseguito in questa sessione.</span><span class="sxs-lookup"><span data-stu-id="9ac4d-124">The amount of time the Log Reader Agent has run in this session.</span></span> <span data-ttu-id="9ac4d-125">Il valore di durata rappresenta il tempo trascorso se l'agente è ancora in esecuzione e la durata totale della sessione se la sessione dell'agente è terminata.</span><span class="sxs-lookup"><span data-stu-id="9ac4d-125">The time represents elapsed time if the agent is currently running and the total time of the session if the agent session has ended.</span></span>  
  
 <span data-ttu-id="9ac4d-126">**Messaggio di errore**</span><span class="sxs-lookup"><span data-stu-id="9ac4d-126">**Error Message**</span></span>  
 <span data-ttu-id="9ac4d-127">Se una sessione è terminata con un errore, in questo campo viene visualizzato l'ultimo messaggio di errore registrato dall'agente di lettura log.</span><span class="sxs-lookup"><span data-stu-id="9ac4d-127">If a session ended in an error, this field displays the last error message logged by the Log Reader Agent.</span></span> <span data-ttu-id="9ac4d-128">Se una sessione non è terminata con un errore, questo campo è vuoto.</span><span class="sxs-lookup"><span data-stu-id="9ac4d-128">If a session did not end in an error, this field is blank.</span></span>  
  
 <span data-ttu-id="9ac4d-129">**Messaggio azione**</span><span class="sxs-lookup"><span data-stu-id="9ac4d-129">**Action Message**</span></span>  
 <span data-ttu-id="9ac4d-130">Tutti i messaggi informativi e i messaggi di errore registrati dall'agente di lettura log durante la sessione selezionata.</span><span class="sxs-lookup"><span data-stu-id="9ac4d-130">All informational messages and error messages that the Log Reader Agent has logged during the selected session.</span></span>  
  
 <span data-ttu-id="9ac4d-131">**Ora azione**</span><span class="sxs-lookup"><span data-stu-id="9ac4d-131">**Action Time**</span></span>  
 <span data-ttu-id="9ac4d-132">Ora di esecuzione dell'azione descritta nella colonna **Messaggio azione** .</span><span class="sxs-lookup"><span data-stu-id="9ac4d-132">The time at which the action described in the **Action Message** column was performed.</span></span>  
  
 <span data-ttu-id="9ac4d-133">**Messaggio o dettagli errore della sessione selezionata**</span><span class="sxs-lookup"><span data-stu-id="9ac4d-133">**Error details or message of the selected session**</span></span>  
 <span data-ttu-id="9ac4d-134">Area visualizzata solo se per la sessione selezionata è visualizzato il valore **Errore** nella colonna **Stato** .</span><span class="sxs-lookup"><span data-stu-id="9ac4d-134">Displayed only if the selected session displays a value of **Error** in the **Status** column.</span></span> <span data-ttu-id="9ac4d-135">In questa area di testo vengono visualizzate informazioni dettagliate sull'errore e viene indicato il comando di cui è stata tentata l'esecuzione quando si è verificato l'errore.</span><span class="sxs-lookup"><span data-stu-id="9ac4d-135">This text area displays detailed error information and the command that was attempted at the time of the error.</span></span> <span data-ttu-id="9ac4d-136">Sono inoltre disponibili collegamenti a contenuto aggiuntivo correlato all'errore.</span><span class="sxs-lookup"><span data-stu-id="9ac4d-136">It also includes links to additional content related to the error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ac4d-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9ac4d-137">See Also</span></span>  
 <span data-ttu-id="9ac4d-138">[Avviare Monitoraggio replica](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="9ac4d-138">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="9ac4d-139">[Visualizzare le informazioni ed eseguire attività usando Monitoraggio replica](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="9ac4d-139">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 <span data-ttu-id="9ac4d-140">[Monitoraggio della replica](monitoring-replication.md) </span><span class="sxs-lookup"><span data-stu-id="9ac4d-140">[Monitoring Replication](monitoring-replication.md) </span></span>  
 [<span data-ttu-id="9ac4d-141">Panoramica degli agenti di replica</span><span class="sxs-lookup"><span data-stu-id="9ac4d-141">Replication Agents Overview</span></span>](agents/replication-agents-overview.md)  
  
  
