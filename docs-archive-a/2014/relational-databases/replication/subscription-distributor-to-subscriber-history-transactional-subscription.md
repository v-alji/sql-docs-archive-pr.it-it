---
title: Sottoscrizione, Cronologia server di distribuzione - Sottoscrittore (sottoscrizione transazionale) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.subscription.disttosub.f1
ms.assetid: 1aad5b82-592e-4907-92f7-b90794175be5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5cb9d708b75a9414725907530c7454cdba26d135
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724479"
---
# <a name="subscription-distributor-to-subscriber-history-transactional-subscription"></a><span data-ttu-id="52e3b-102">Sottoscrizione, Cronologia server di distribuzione - Sottoscrittore (Sottoscrizione transazionale)</span><span class="sxs-lookup"><span data-stu-id="52e3b-102">Subscription, Distributor to Subscriber History (Transactional Subscription)</span></span>
  <span data-ttu-id="52e3b-103">Nella scheda **Cronologia server di distribuzione - Sottoscrittore** vengono visualizzate informazioni dettagliate sull'agente di distribuzione, quali lo stato, la cronologia, i messaggi informativi ed eventuali messaggi di errore.</span><span class="sxs-lookup"><span data-stu-id="52e3b-103">The **Distributor to Subscriber History** tab displays detailed information on the Distribution Agent, including status, history, informational messages, and any error messages.</span></span>  
  
## <a name="options"></a><span data-ttu-id="52e3b-104">Opzioni</span><span class="sxs-lookup"><span data-stu-id="52e3b-104">Options</span></span>  
 <span data-ttu-id="52e3b-105">Scegliere le sessioni dell'agente di distribuzione da visualizzare dal menu **Visualizza** e quindi selezionare una sessione specifica nella griglia con etichetta **Sessioni dell'agente di distribuzione**.</span><span class="sxs-lookup"><span data-stu-id="52e3b-105">Select which Distribution Agent sessions to view from the **View** menu, and then select a specific session in the grid labeled **Sessions of the Distribution Agent**.</span></span> <span data-ttu-id="52e3b-106">Nella griglia con etichetta **Azioni nella sessione selezionata**verranno visualizzate informazioni dettagliate sulla sessione selezionata.</span><span class="sxs-lookup"><span data-stu-id="52e3b-106">Detailed information on this session is displayed in the grid labeled **Actions in the selected session**.</span></span> <span data-ttu-id="52e3b-107">Se la sessione selezionata è terminata con un errore, verrà inoltre visualizzata l'area di testo con etichetta **Messaggio o dettagli errore della sessione selezionata** .</span><span class="sxs-lookup"><span data-stu-id="52e3b-107">If the selected session ended in an error, the text area labeled **Error details or message of the selected session** is also displayed.</span></span>  
  
 <span data-ttu-id="52e3b-108">**Visualizzazione**</span><span class="sxs-lookup"><span data-stu-id="52e3b-108">**View**</span></span>  
 <span data-ttu-id="52e3b-109">Consente di selezionare le sessioni dell'agente di distribuzione da visualizzare.</span><span class="sxs-lookup"><span data-stu-id="52e3b-109">Select which Distribution Agent sessions to view.</span></span> <span data-ttu-id="52e3b-110">L'esecuzione dell'agente di distribuzione è in genere continua. Potrebbe pertanto essere presente una sola sessione.</span><span class="sxs-lookup"><span data-stu-id="52e3b-110">The Distribution Agent typically runs continuously, therefore there might be only one session to view.</span></span>  
  
 <span data-ttu-id="52e3b-111">**Status**</span><span class="sxs-lookup"><span data-stu-id="52e3b-111">**Status**</span></span>  
 <span data-ttu-id="52e3b-112">Stato dell'agente di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="52e3b-112">The status of the Distribution Agent.</span></span> <span data-ttu-id="52e3b-113">Nell'elenco seguente vengono indicati i valori di stato possibili:</span><span class="sxs-lookup"><span data-stu-id="52e3b-113">The following list shows the possible status values:</span></span>  
  
-   <span data-ttu-id="52e3b-114">Errore</span><span class="sxs-lookup"><span data-stu-id="52e3b-114">Error</span></span>  
  
-   <span data-ttu-id="52e3b-115">Completi</span><span class="sxs-lookup"><span data-stu-id="52e3b-115">Completed</span></span>  
  
-   <span data-ttu-id="52e3b-116">Nuovo tentativo in corso</span><span class="sxs-lookup"><span data-stu-id="52e3b-116">Retrying</span></span>  
  
-   <span data-ttu-id="52e3b-117">In esecuzione</span><span class="sxs-lookup"><span data-stu-id="52e3b-117">Running</span></span>  
  
 <span data-ttu-id="52e3b-118">**Ora di inizio**</span><span class="sxs-lookup"><span data-stu-id="52e3b-118">**Start Time**</span></span>  
 <span data-ttu-id="52e3b-119">Ora di inizio della sessione.</span><span class="sxs-lookup"><span data-stu-id="52e3b-119">The start time of the session.</span></span>  
  
 <span data-ttu-id="52e3b-120">**Ora di fine**</span><span class="sxs-lookup"><span data-stu-id="52e3b-120">**End Time**</span></span>  
 <span data-ttu-id="52e3b-121">Ora di fine della sessione.</span><span class="sxs-lookup"><span data-stu-id="52e3b-121">The end time of the session.</span></span> <span data-ttu-id="52e3b-122">Se l'agente non è arrestato, questo campo è vuoto.</span><span class="sxs-lookup"><span data-stu-id="52e3b-122">If the agent has not stopped, this field is empty.</span></span>  
  
 <span data-ttu-id="52e3b-123">**Duration**</span><span class="sxs-lookup"><span data-stu-id="52e3b-123">**Duration**</span></span>  
 <span data-ttu-id="52e3b-124">Periodo di tempo durante il quale l'agente di distribuzione è stato eseguito in questa sessione.</span><span class="sxs-lookup"><span data-stu-id="52e3b-124">The amount of time the Distribution Agent has run in this session.</span></span> <span data-ttu-id="52e3b-125">Il valore di durata rappresenta il tempo trascorso se l'agente è ancora in esecuzione e la durata totale della sessione se la sessione dell'agente è terminata.</span><span class="sxs-lookup"><span data-stu-id="52e3b-125">The time represents elapsed time if the agent is currently running and the total time of the session if the agent session has ended.</span></span>  
  
 <span data-ttu-id="52e3b-126">**Messaggio di errore**</span><span class="sxs-lookup"><span data-stu-id="52e3b-126">**Error Message**</span></span>  
 <span data-ttu-id="52e3b-127">Se una sessione è terminata con un errore, in questo campo viene visualizzato l'ultimo messaggio di errore registrato dall'agente di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="52e3b-127">If a session ended in an error, this field displays the last error message logged by the Distribution Agent.</span></span> <span data-ttu-id="52e3b-128">Se una sessione non è terminata con un errore, questo campo è vuoto.</span><span class="sxs-lookup"><span data-stu-id="52e3b-128">If a session did not end in an error, this field is blank.</span></span>  
  
 <span data-ttu-id="52e3b-129">**Messaggio azione**</span><span class="sxs-lookup"><span data-stu-id="52e3b-129">**Action Message**</span></span>  
 <span data-ttu-id="52e3b-130">Tutti i messaggi informativi e i messaggi di errore registrati dall'agente di distribuzione durante la sessione selezionata.</span><span class="sxs-lookup"><span data-stu-id="52e3b-130">All informational messages and error messages that the Distribution Agent has logged during the selected session.</span></span>  
  
 <span data-ttu-id="52e3b-131">**Ora azione**</span><span class="sxs-lookup"><span data-stu-id="52e3b-131">**Action Time**</span></span>  
 <span data-ttu-id="52e3b-132">Ora di esecuzione dell'azione descritta nella colonna **Messaggio azione** .</span><span class="sxs-lookup"><span data-stu-id="52e3b-132">The time at which the action described in the **Action Message** column was performed.</span></span>  
  
 <span data-ttu-id="52e3b-133">**Messaggio o dettagli errore della sessione selezionata**</span><span class="sxs-lookup"><span data-stu-id="52e3b-133">**Error details or message of the selected session**</span></span>  
 <span data-ttu-id="52e3b-134">Area visualizzata solo se per la sessione selezionata è visualizzato il valore **Errore** nella colonna **Stato** .</span><span class="sxs-lookup"><span data-stu-id="52e3b-134">Displayed only if the selected session displays a value of **Error** in the **Status** column.</span></span> <span data-ttu-id="52e3b-135">In questa area di testo vengono visualizzate informazioni dettagliate sull'errore e viene indicato il comando di cui è stata tentata l'esecuzione quando si è verificato l'errore.</span><span class="sxs-lookup"><span data-stu-id="52e3b-135">This text area displays detailed error information and the command that was attempted at the time of the error.</span></span> <span data-ttu-id="52e3b-136">Sono inoltre disponibili collegamenti a contenuto aggiuntivo correlato all'errore.</span><span class="sxs-lookup"><span data-stu-id="52e3b-136">It also includes links to additional content related to the error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52e3b-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="52e3b-137">See Also</span></span>  
 <span data-ttu-id="52e3b-138">[Avviare Monitoraggio replica](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="52e3b-138">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="52e3b-139">[Visualizzare le informazioni ed eseguire attività usando Monitoraggio replica](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="52e3b-139">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 <span data-ttu-id="52e3b-140">[Monitoraggio della replica](monitoring-replication.md) </span><span class="sxs-lookup"><span data-stu-id="52e3b-140">[Monitoring Replication](monitoring-replication.md) </span></span>  
 [<span data-ttu-id="52e3b-141">Panoramica degli agenti di replica</span><span class="sxs-lookup"><span data-stu-id="52e3b-141">Replication Agents Overview</span></span>](agents/replication-agents-overview.md)  
  
  
