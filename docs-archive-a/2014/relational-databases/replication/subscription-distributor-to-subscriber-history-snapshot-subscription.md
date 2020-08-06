---
title: Sottoscrizione, Cronologia database di distribuzione - Sottoscrittore (sottoscrizione snapshot) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.subscription.pubtodist.snapshot.f1
ms.assetid: d3575964-f287-4bcf-8d2e-f81a33141b25
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: fe894e23e7ad7fef9c328334740eff73164130a6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724476"
---
# <a name="subscription-distributor-to-subscriber-history-snapshot-subscription"></a><span data-ttu-id="30f49-102">Sottoscrizione, Cronologia server di distribuzione - Sottoscrittore (sottoscrizione snapshot)</span><span class="sxs-lookup"><span data-stu-id="30f49-102">Subscription, Distributor to Subscriber History (Snapshot Subscription)</span></span>
  <span data-ttu-id="30f49-103">Nella scheda **Cronologia server di distribuzione - Sottoscrittore** vengono visualizzate informazioni dettagliate sull'agente di distribuzione, quali lo stato, la cronologia, i messaggi informativi ed eventuali messaggi di errore.</span><span class="sxs-lookup"><span data-stu-id="30f49-103">The **Distributor to Subscriber History** tab displays detailed information on the Distribution Agent, including status, history, informational messages, and any error messages.</span></span>  
  
## <a name="options"></a><span data-ttu-id="30f49-104">Opzioni</span><span class="sxs-lookup"><span data-stu-id="30f49-104">Options</span></span>  
 <span data-ttu-id="30f49-105">Scegliere le sessioni dell'agente di distribuzione da visualizzare dal menu **Visualizza** e quindi selezionare una sessione specifica nella griglia con etichetta **Sessioni dell'agente di distribuzione**.</span><span class="sxs-lookup"><span data-stu-id="30f49-105">Select which Distribution Agent sessions to view from the **View** menu, and then select a specific session in the grid labeled **Sessions of the Distribution Agent**.</span></span> <span data-ttu-id="30f49-106">Nella griglia con etichetta **Azioni nella sessione selezionata**verranno visualizzate informazioni dettagliate sulla sessione selezionata.</span><span class="sxs-lookup"><span data-stu-id="30f49-106">Detailed information on this session is displayed in the grid labeled **Actions in the selected session**.</span></span> <span data-ttu-id="30f49-107">Se la sessione selezionata è terminata con un errore, verrà inoltre visualizzata l'area di testo con etichetta **Messaggio o dettagli errore della sessione selezionata** .</span><span class="sxs-lookup"><span data-stu-id="30f49-107">If the selected session ended in an error, the text area labeled **Error details or message of the selected session** is also displayed.</span></span>  
  
 <span data-ttu-id="30f49-108">**Visualizzazione**</span><span class="sxs-lookup"><span data-stu-id="30f49-108">**View**</span></span>  
 <span data-ttu-id="30f49-109">Consente di selezionare le sessioni dell'agente di distribuzione da visualizzare.</span><span class="sxs-lookup"><span data-stu-id="30f49-109">Select which Distribution Agent sessions to view.</span></span>  
  
 <span data-ttu-id="30f49-110">**Status**</span><span class="sxs-lookup"><span data-stu-id="30f49-110">**Status**</span></span>  
 <span data-ttu-id="30f49-111">Stato dell'agente di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="30f49-111">The status of the Distribution Agent.</span></span> <span data-ttu-id="30f49-112">Nell'elenco seguente vengono indicati i valori di stato possibili:</span><span class="sxs-lookup"><span data-stu-id="30f49-112">The following list shows the possible status values:</span></span>  
  
-   <span data-ttu-id="30f49-113">Errore</span><span class="sxs-lookup"><span data-stu-id="30f49-113">Error</span></span>  
  
-   <span data-ttu-id="30f49-114">Completi</span><span class="sxs-lookup"><span data-stu-id="30f49-114">Completed</span></span>  
  
-   <span data-ttu-id="30f49-115">Nuovo tentativo in corso</span><span class="sxs-lookup"><span data-stu-id="30f49-115">Retrying</span></span>  
  
-   <span data-ttu-id="30f49-116">In esecuzione</span><span class="sxs-lookup"><span data-stu-id="30f49-116">Running</span></span>  
  
 <span data-ttu-id="30f49-117">**Ora di inizio**</span><span class="sxs-lookup"><span data-stu-id="30f49-117">**Start Time**</span></span>  
 <span data-ttu-id="30f49-118">Ora di inizio della sessione.</span><span class="sxs-lookup"><span data-stu-id="30f49-118">The start time of the session.</span></span>  
  
 <span data-ttu-id="30f49-119">**Ora di fine**</span><span class="sxs-lookup"><span data-stu-id="30f49-119">**End Time**</span></span>  
 <span data-ttu-id="30f49-120">Ora di fine della sessione.</span><span class="sxs-lookup"><span data-stu-id="30f49-120">The end time of the session.</span></span> <span data-ttu-id="30f49-121">Se l'agente non è arrestato, questo campo è vuoto.</span><span class="sxs-lookup"><span data-stu-id="30f49-121">If the agent has not stopped, this field is empty.</span></span>  
  
 <span data-ttu-id="30f49-122">**Duration**</span><span class="sxs-lookup"><span data-stu-id="30f49-122">**Duration**</span></span>  
 <span data-ttu-id="30f49-123">Periodo di tempo durante il quale l'agente di distribuzione è stato eseguito in questa sessione.</span><span class="sxs-lookup"><span data-stu-id="30f49-123">The amount of time the Distribution Agent has run in this session.</span></span> <span data-ttu-id="30f49-124">Il valore di durata rappresenta il tempo trascorso se l'agente è ancora in esecuzione e la durata totale della sessione se la sessione dell'agente è terminata.</span><span class="sxs-lookup"><span data-stu-id="30f49-124">The time represents elapsed time if the agent is currently running and the total time of the session if the agent session had ended.</span></span>  
  
 <span data-ttu-id="30f49-125">**Messaggio di errore**</span><span class="sxs-lookup"><span data-stu-id="30f49-125">**Error Message**</span></span>  
 <span data-ttu-id="30f49-126">Se una sessione è terminata con un errore, in questo campo viene visualizzato l'ultimo messaggio di errore registrato dall'agente di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="30f49-126">If a session ended in an error, this field displays the last error message logged by the Distribution Agent.</span></span> <span data-ttu-id="30f49-127">Se una sessione non è terminata con un errore, questo campo è vuoto.</span><span class="sxs-lookup"><span data-stu-id="30f49-127">If a session did not end in an error, this field is blank.</span></span>  
  
 <span data-ttu-id="30f49-128">**Messaggio azione**</span><span class="sxs-lookup"><span data-stu-id="30f49-128">**Action Message**</span></span>  
 <span data-ttu-id="30f49-129">Tutti i messaggi informativi e i messaggi di errore registrati dall'agente di distribuzione durante la sessione selezionata.</span><span class="sxs-lookup"><span data-stu-id="30f49-129">All informational messages and error messages that the Distribution Agent has logged during the selected session.</span></span>  
  
 <span data-ttu-id="30f49-130">**Ora azione**</span><span class="sxs-lookup"><span data-stu-id="30f49-130">**Action Time**</span></span>  
 <span data-ttu-id="30f49-131">Ora di esecuzione dell'azione descritta nella colonna **Messaggio azione** .</span><span class="sxs-lookup"><span data-stu-id="30f49-131">The time at which the action described in the **Action Message** column was performed.</span></span>  
  
 <span data-ttu-id="30f49-132">**Messaggio o dettagli errore della sessione selezionata**</span><span class="sxs-lookup"><span data-stu-id="30f49-132">**Error details or message of the selected session**</span></span>  
 <span data-ttu-id="30f49-133">Area visualizzata solo se per la sessione selezionata è visualizzato il valore **Errore** nella colonna **Stato** .</span><span class="sxs-lookup"><span data-stu-id="30f49-133">Displayed only if the selected session displays a value of **Error** in the **Status** column.</span></span> <span data-ttu-id="30f49-134">In questa area di testo vengono visualizzate informazioni dettagliate sull'errore e viene indicato il comando di cui è stata tentata l'esecuzione quando si è verificato l'errore.</span><span class="sxs-lookup"><span data-stu-id="30f49-134">This text area displays detailed error information and the command that was attempted at the time of the error.</span></span> <span data-ttu-id="30f49-135">Sono inoltre disponibili collegamenti a contenuto aggiuntivo correlato all'errore.</span><span class="sxs-lookup"><span data-stu-id="30f49-135">It also includes links to additional content related to the error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30f49-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="30f49-136">See Also</span></span>  
 <span data-ttu-id="30f49-137">[Avviare Monitoraggio replica](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="30f49-137">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="30f49-138">[Visualizzare le informazioni ed eseguire attività usando Monitoraggio replica](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="30f49-138">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 <span data-ttu-id="30f49-139">[Monitoraggio della replica](monitoring-replication.md) </span><span class="sxs-lookup"><span data-stu-id="30f49-139">[Monitoring Replication](monitoring-replication.md) </span></span>  
 [<span data-ttu-id="30f49-140">Panoramica degli agenti di replica</span><span class="sxs-lookup"><span data-stu-id="30f49-140">Replication Agents Overview</span></span>](agents/replication-agents-overview.md)  
  
  
