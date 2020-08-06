---
title: Agente di lettura coda | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.queuereaderagent.f1
helpviewer_keywords:
- Queue Reader Agent dialog box
ms.assetid: f02d24b6-dcb5-4126-b56e-fab41cfe4337
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 9649223b35562da97744d79f9506615b97274870
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636686"
---
# <a name="queue-reader-agent"></a><span data-ttu-id="32c35-102">Agente di lettura coda</span><span class="sxs-lookup"><span data-stu-id="32c35-102">Queue Reader Agent</span></span>
  <span data-ttu-id="32c35-103">Nella finestra di dialogo **Agente di lettura coda** vengono visualizzate informazioni dettagliate sull'agente di lettura coda, tra cui lo stato, la cronologia, i messaggi informativi ed eventuali messaggi di errore.</span><span class="sxs-lookup"><span data-stu-id="32c35-103">The **Queue Reader Agent** dialog box displays detailed information on the Queue Reader Agent, including status, history, informational messages, and any error messages.</span></span>  
  
## <a name="options"></a><span data-ttu-id="32c35-104">Opzioni</span><span class="sxs-lookup"><span data-stu-id="32c35-104">Options</span></span>  
 <span data-ttu-id="32c35-105">Scegliere le sessioni dell'agente di lettura coda da visualizzare nel menu **Visualizza** e quindi selezionare una sessione specifica nella griglia con etichetta **Sessioni dell'agente di lettura coda**.</span><span class="sxs-lookup"><span data-stu-id="32c35-105">Select which Queue Reader Agent sessions to view from the **View** menu, and then select a specific session in the grid labeled **Sessions of the Queue Reader Agent**.</span></span> <span data-ttu-id="32c35-106">Nella griglia con etichetta **Azioni nella sessione selezionata**verranno visualizzate informazioni dettagliate sulla sessione selezionata.</span><span class="sxs-lookup"><span data-stu-id="32c35-106">Detailed information on this session is displayed in the grid labeled **Actions in the selected session**.</span></span> <span data-ttu-id="32c35-107">Se la sessione selezionata è terminata con un errore, verrà inoltre visualizzata l'area di testo con etichetta **Messaggio o dettagli errore della sessione selezionata** .</span><span class="sxs-lookup"><span data-stu-id="32c35-107">If the selected session ended in an error, the text area labeled **Error details or message of the selected session** is also displayed.</span></span>  
  
 <span data-ttu-id="32c35-108">**Visualizza**</span><span class="sxs-lookup"><span data-stu-id="32c35-108">**View**</span></span>  
 <span data-ttu-id="32c35-109">Consente di selezionare le sessioni dell'agente di lettura coda da visualizzare.</span><span class="sxs-lookup"><span data-stu-id="32c35-109">Select which Queue Reader Agent sessions to view.</span></span> <span data-ttu-id="32c35-110">L'agente di lettura coda in genere viene eseguito in modo continuo, pertanto potrebbe essere disponibile una sola sessione da visualizzare.</span><span class="sxs-lookup"><span data-stu-id="32c35-110">The Queue Reader Agent typically runs continuously, therefore there might be only one session to view.</span></span>  
  
 <span data-ttu-id="32c35-111">**Status**</span><span class="sxs-lookup"><span data-stu-id="32c35-111">**Status**</span></span>  
 <span data-ttu-id="32c35-112">Stato dell'agente di lettura coda.</span><span class="sxs-lookup"><span data-stu-id="32c35-112">The status of the Queue Reader Agent.</span></span> <span data-ttu-id="32c35-113">Nell'elenco seguente vengono indicati i valori di stato possibili:</span><span class="sxs-lookup"><span data-stu-id="32c35-113">The following list shows the possible status values:</span></span>  
  
-   <span data-ttu-id="32c35-114">Errore</span><span class="sxs-lookup"><span data-stu-id="32c35-114">Error</span></span>  
  
-   <span data-ttu-id="32c35-115">Ripetizione comando non riuscito</span><span class="sxs-lookup"><span data-stu-id="32c35-115">Retrying failed commands</span></span>  
  
-   <span data-ttu-id="32c35-116">Non in esecuzione</span><span class="sxs-lookup"><span data-stu-id="32c35-116">Not running</span></span>  
  
-   <span data-ttu-id="32c35-117">In esecuzione</span><span class="sxs-lookup"><span data-stu-id="32c35-117">Running</span></span>  
  
 <span data-ttu-id="32c35-118">**Start Time**</span><span class="sxs-lookup"><span data-stu-id="32c35-118">**Start Time**</span></span>  
 <span data-ttu-id="32c35-119">Ora di inizio della sessione.</span><span class="sxs-lookup"><span data-stu-id="32c35-119">The start time of the session.</span></span>  
  
 <span data-ttu-id="32c35-120">**Ora fine**</span><span class="sxs-lookup"><span data-stu-id="32c35-120">**End Time**</span></span>  
 <span data-ttu-id="32c35-121">Ora di fine della sessione.</span><span class="sxs-lookup"><span data-stu-id="32c35-121">The end time of the session.</span></span> <span data-ttu-id="32c35-122">Se l'agente non è arrestato, questo campo è vuoto.</span><span class="sxs-lookup"><span data-stu-id="32c35-122">If the agent has not stopped, this field is empty.</span></span>  
  
 <span data-ttu-id="32c35-123">**Duration**</span><span class="sxs-lookup"><span data-stu-id="32c35-123">**Duration**</span></span>  
 <span data-ttu-id="32c35-124">Periodo di tempo durante il quale l'agente di lettura coda è stato eseguito in questa sessione.</span><span class="sxs-lookup"><span data-stu-id="32c35-124">The amount of time the Queue Reader Agent has run in this session.</span></span> <span data-ttu-id="32c35-125">Il valore di durata rappresenta il tempo trascorso se l'agente è ancora in esecuzione e la durata totale della sessione se la sessione dell'agente è terminata.</span><span class="sxs-lookup"><span data-stu-id="32c35-125">The time represents elapsed time if the agent is currently running and the total time of the session if the agent session has ended.</span></span>  
  
 <span data-ttu-id="32c35-126">**Messaggio di errore**</span><span class="sxs-lookup"><span data-stu-id="32c35-126">**Error Message**</span></span>  
 <span data-ttu-id="32c35-127">Se una sessione è terminata con un errore, in questo campo viene visualizzato l'ultimo messaggio di errore registrato dall'agente di lettura coda.</span><span class="sxs-lookup"><span data-stu-id="32c35-127">If a session ended in an error, this field displays the last error message logged by the Queue Reader Agent.</span></span> <span data-ttu-id="32c35-128">Se una sessione non è terminata con un errore, questo campo è vuoto.</span><span class="sxs-lookup"><span data-stu-id="32c35-128">If a session did not end in an error, this field is blank.</span></span>  
  
 <span data-ttu-id="32c35-129">**Messaggio azione**</span><span class="sxs-lookup"><span data-stu-id="32c35-129">**Action Message**</span></span>  
 <span data-ttu-id="32c35-130">Tutti i messaggi informativi e i messaggi di errore registrati dall'agente di lettura coda durante la sessione selezionata.</span><span class="sxs-lookup"><span data-stu-id="32c35-130">All informational messages and error messages that the Queue Reader Agent has logged during the selected session.</span></span>  
  
 <span data-ttu-id="32c35-131">**Ora azione**</span><span class="sxs-lookup"><span data-stu-id="32c35-131">**Action Time**</span></span>  
 <span data-ttu-id="32c35-132">Ora di esecuzione dell'azione descritta nella colonna **Messaggio azione** .</span><span class="sxs-lookup"><span data-stu-id="32c35-132">The time at which the action described in the **Action Message** column was performed.</span></span>  
  
 <span data-ttu-id="32c35-133">**Messaggio o dettagli errore della sessione selezionata**</span><span class="sxs-lookup"><span data-stu-id="32c35-133">**Error details or message of the selected session**</span></span>  
 <span data-ttu-id="32c35-134">Area visualizzata solo se per la sessione selezionata è visualizzato il valore **Errore** nella colonna **Stato** .</span><span class="sxs-lookup"><span data-stu-id="32c35-134">Displayed only if the selected session displays a value of **Error** in the **Status** column.</span></span> <span data-ttu-id="32c35-135">In questa area di testo vengono visualizzate informazioni dettagliate sull'errore e viene indicato il comando di cui è stata tentata l'esecuzione quando si è verificato l'errore.</span><span class="sxs-lookup"><span data-stu-id="32c35-135">This text area displays detailed error information and the command that was attempted at the time of the error.</span></span> <span data-ttu-id="32c35-136">Sono inoltre disponibili collegamenti a contenuto aggiuntivo correlato all'errore.</span><span class="sxs-lookup"><span data-stu-id="32c35-136">It also includes links to additional content related to the error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32c35-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="32c35-137">See Also</span></span>  
 <span data-ttu-id="32c35-138">[Avviare Monitoraggio replica](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="32c35-138">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="32c35-139">[Visualizzare le informazioni ed eseguire attività usando Monitoraggio replica](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="32c35-139">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 <span data-ttu-id="32c35-140">[Monitoraggio della replica](monitoring-replication.md) </span><span class="sxs-lookup"><span data-stu-id="32c35-140">[Monitoring Replication](monitoring-replication.md) </span></span>  
 [<span data-ttu-id="32c35-141">Panoramica degli agenti di replica</span><span class="sxs-lookup"><span data-stu-id="32c35-141">Replication Agents Overview</span></span>](agents/replication-agents-overview.md)  
  
  
