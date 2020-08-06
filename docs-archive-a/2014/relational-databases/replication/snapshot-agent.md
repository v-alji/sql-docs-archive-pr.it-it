---
title: Agente snapshot | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.snapshotagent.f1
helpviewer_keywords:
- Snapshot Agent dialog box
ms.assetid: b715e621-2cd5-4a15-8f58-a341aa8ef5e4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 925f2d3841b5dded6c8504a4a05dc60e61024161
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637751"
---
# <a name="snapshot-agent"></a><span data-ttu-id="12c2b-102">agente snapshot</span><span class="sxs-lookup"><span data-stu-id="12c2b-102">Snapshot Agent</span></span>
  <span data-ttu-id="12c2b-103">Nella finestra di dialogo **Agente snapshot** vengono visualizzate informazioni dettagliate sull'agente snapshot, inclusi lo stato, la cronologia, i messaggi informativi e tutti quelli di errore.</span><span class="sxs-lookup"><span data-stu-id="12c2b-103">The **Snapshot Agent** dialog box displays detailed information on the Snapshot Agent, including status, history, informational messages, and any error messages.</span></span>  
  
## <a name="options"></a><span data-ttu-id="12c2b-104">Opzioni</span><span class="sxs-lookup"><span data-stu-id="12c2b-104">Options</span></span>  
 <span data-ttu-id="12c2b-105">Scegliere le sessioni dell'agente snapshot da visualizzare dal menu **Visualizza** e quindi selezionare una specifica sessione nella griglia con etichetta **Sessioni dell'agente snapshot**.</span><span class="sxs-lookup"><span data-stu-id="12c2b-105">Select which Snapshot Agent sessions to view from the **View** menu, and then select a specific session in the grid labeled **Sessions of the Snapshot Agent**.</span></span> <span data-ttu-id="12c2b-106">Nella griglia con etichetta **Azioni nella sessione selezionata**verranno visualizzate informazioni dettagliate sulla sessione selezionata.</span><span class="sxs-lookup"><span data-stu-id="12c2b-106">Detailed information on this session is displayed in the grid labeled **Actions in the selected session**.</span></span> <span data-ttu-id="12c2b-107">Se la sessione selezionata è terminata con un errore, verrà inoltre visualizzata l'area di testo con etichetta **Messaggio o dettagli errore della sessione selezionata** .</span><span class="sxs-lookup"><span data-stu-id="12c2b-107">If the selected session ended in an error, the text area labeled **Error details or message of the selected session** is also displayed.</span></span>  
  
 <span data-ttu-id="12c2b-108">**Visualizza**</span><span class="sxs-lookup"><span data-stu-id="12c2b-108">**View**</span></span>  
 <span data-ttu-id="12c2b-109">Consente di selezionare le sessioni dell'agente snapshot da visualizzare.</span><span class="sxs-lookup"><span data-stu-id="12c2b-109">Select which Snapshot Agent sessions to view.</span></span>  
  
 <span data-ttu-id="12c2b-110">**Status**</span><span class="sxs-lookup"><span data-stu-id="12c2b-110">**Status**</span></span>  
 <span data-ttu-id="12c2b-111">Stato dell'agente snapshot.</span><span class="sxs-lookup"><span data-stu-id="12c2b-111">The status of the Snapshot Agent.</span></span> <span data-ttu-id="12c2b-112">Nell'elenco seguente vengono indicati i valori di stato possibili:</span><span class="sxs-lookup"><span data-stu-id="12c2b-112">The following list shows the possible status values:</span></span>  
  
-   <span data-ttu-id="12c2b-113">Errore</span><span class="sxs-lookup"><span data-stu-id="12c2b-113">Error</span></span>  
  
-   <span data-ttu-id="12c2b-114">Ripetizione comando non riuscito</span><span class="sxs-lookup"><span data-stu-id="12c2b-114">Retrying failed commands</span></span>  
  
-   <span data-ttu-id="12c2b-115">Non in esecuzione</span><span class="sxs-lookup"><span data-stu-id="12c2b-115">Not running</span></span>  
  
-   <span data-ttu-id="12c2b-116">Completi</span><span class="sxs-lookup"><span data-stu-id="12c2b-116">Completed</span></span>  
  
 <span data-ttu-id="12c2b-117">**Start Time**</span><span class="sxs-lookup"><span data-stu-id="12c2b-117">**Start Time**</span></span>  
 <span data-ttu-id="12c2b-118">Ora di inizio della sessione.</span><span class="sxs-lookup"><span data-stu-id="12c2b-118">The start time of the session.</span></span>  
  
 <span data-ttu-id="12c2b-119">**Ora fine**</span><span class="sxs-lookup"><span data-stu-id="12c2b-119">**End Time**</span></span>  
 <span data-ttu-id="12c2b-120">Ora di fine della sessione.</span><span class="sxs-lookup"><span data-stu-id="12c2b-120">The end time of the session.</span></span> <span data-ttu-id="12c2b-121">Se l'agente non è arrestato, questo campo è vuoto.</span><span class="sxs-lookup"><span data-stu-id="12c2b-121">If the agent has not stopped, this field is empty.</span></span>  
  
 <span data-ttu-id="12c2b-122">**Duration**</span><span class="sxs-lookup"><span data-stu-id="12c2b-122">**Duration**</span></span>  
 <span data-ttu-id="12c2b-123">Periodo di tempo per cui l'agente snapshot è stato eseguito in questa sessione.</span><span class="sxs-lookup"><span data-stu-id="12c2b-123">The amount of time the Snapshot Agent has run in this session.</span></span> <span data-ttu-id="12c2b-124">Il valore di durata rappresenta il tempo trascorso se l'agente è ancora in esecuzione e la durata totale della sessione se la sessione dell'agente è terminata.</span><span class="sxs-lookup"><span data-stu-id="12c2b-124">The time represents elapsed time if the agent is currently running and the total time of the session if the agent session has ended.</span></span>  
  
 <span data-ttu-id="12c2b-125">**Messaggio di errore**</span><span class="sxs-lookup"><span data-stu-id="12c2b-125">**Error Message**</span></span>  
 <span data-ttu-id="12c2b-126">Se una sessione è terminata con un errore, in questo campo verrà visualizzato l'ultimo messaggio di errore registrato dall'agente snapshot.</span><span class="sxs-lookup"><span data-stu-id="12c2b-126">If a session ended in an error, this field displays the last error message logged by the Snapshot Agent.</span></span> <span data-ttu-id="12c2b-127">Se una sessione non è terminata con un errore, questo campo è vuoto.</span><span class="sxs-lookup"><span data-stu-id="12c2b-127">If a session did not end in an error, this field is blank.</span></span>  
  
 <span data-ttu-id="12c2b-128">**Messaggio azione**</span><span class="sxs-lookup"><span data-stu-id="12c2b-128">**Action Message**</span></span>  
 <span data-ttu-id="12c2b-129">Tutti i messaggi informativi e di errore registrati dall'agente snapshot durante la sezione selezionata.</span><span class="sxs-lookup"><span data-stu-id="12c2b-129">All informational messages and error messages that the Snapshot Agent has logged during the selected session.</span></span>  
  
 <span data-ttu-id="12c2b-130">**Ora azione**</span><span class="sxs-lookup"><span data-stu-id="12c2b-130">**Action Time**</span></span>  
 <span data-ttu-id="12c2b-131">Ora di esecuzione dell'azione descritta nella colonna **Messaggio azione** .</span><span class="sxs-lookup"><span data-stu-id="12c2b-131">The time at which the action described in the **Action Message** column was performed.</span></span>  
  
 <span data-ttu-id="12c2b-132">**Messaggio o dettagli errore della sessione selezionata**</span><span class="sxs-lookup"><span data-stu-id="12c2b-132">**Error details or message of the selected session**</span></span>  
 <span data-ttu-id="12c2b-133">Area visualizzata solo se per la sessione selezionata è visualizzato il valore **Errore** nella colonna **Stato** .</span><span class="sxs-lookup"><span data-stu-id="12c2b-133">Is displayed only if the selected session displays a value of **Error** in the **Status** column.</span></span> <span data-ttu-id="12c2b-134">In questa area di testo vengono visualizzate informazioni dettagliate sull'errore e viene indicato il comando di cui è stata tentata l'esecuzione quando si è verificato l'errore.</span><span class="sxs-lookup"><span data-stu-id="12c2b-134">This text area displays detailed error information and the command that was attempted at the time of the error.</span></span> <span data-ttu-id="12c2b-135">Sono inoltre disponibili collegamenti a contenuto aggiuntivo correlato all'errore.</span><span class="sxs-lookup"><span data-stu-id="12c2b-135">It also includes links to additional content related to the error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12c2b-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="12c2b-136">See Also</span></span>  
 <span data-ttu-id="12c2b-137">[Avviare Monitoraggio replica](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="12c2b-137">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="12c2b-138">[Visualizzare le informazioni ed eseguire attività usando Monitoraggio replica](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="12c2b-138">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 <span data-ttu-id="12c2b-139">[Monitoraggio della replica](monitoring-replication.md) </span><span class="sxs-lookup"><span data-stu-id="12c2b-139">[Monitoring Replication](monitoring-replication.md) </span></span>  
 [<span data-ttu-id="12c2b-140">Panoramica degli agenti di replica</span><span class="sxs-lookup"><span data-stu-id="12c2b-140">Replication Agents Overview</span></span>](agents/replication-agents-overview.md)  
  
  
