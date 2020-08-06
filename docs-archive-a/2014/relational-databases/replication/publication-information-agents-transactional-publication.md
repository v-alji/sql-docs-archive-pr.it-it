---
title: Informazioni sulla pubblicazione, Agenti (pubblicazione transazionale) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.publicationinfo.downlevelagents.tran.f1
ms.assetid: 38ef2f54-53bb-4053-876d-86f8f06a4519
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1a3d50da15ea653a7911e65ad888d5997f47a3f0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624048"
---
# <a name="publication-information-agents-transactional-publication"></a><span data-ttu-id="0126e-102">Informazioni sulla pubblicazione, Agenti (pubblicazione transazionale)</span><span class="sxs-lookup"><span data-stu-id="0126e-102">Publication Information, Agents (Transactional Publication)</span></span>
  <span data-ttu-id="0126e-103">La scheda **Agenti** visualizza informazioni di riepilogo sugli agenti per la pubblicazione selezionata.</span><span class="sxs-lookup"><span data-stu-id="0126e-103">The **Agents** tab displays summary information on the agents for the selected publication.</span></span> <span data-ttu-id="0126e-104">Le informazioni sull'agente snapshot e sull'agente di lettura log vengono visualizzate per tutte le pubblicazioni transazionali.</span><span class="sxs-lookup"><span data-stu-id="0126e-104">Information on the Snapshot Agent and Log Reader Agent is displayed for all transactional publications.</span></span> <span data-ttu-id="0126e-105">Le informazioni sull'agente di lettura coda vengono visualizzate per le pubblicazioni transazionali abilitate per le sottoscrizioni ad aggiornamento in coda.</span><span class="sxs-lookup"><span data-stu-id="0126e-105">Information on the Queue Reader Agent is displayed for those transactional publications that are enabled for queued updating subscriptions.</span></span>  
  
## <a name="options"></a><span data-ttu-id="0126e-106">Opzioni</span><span class="sxs-lookup"><span data-stu-id="0126e-106">Options</span></span>  
 <span data-ttu-id="0126e-107">Per ulteriori informazioni su un agente e per le attività correlate, fare clic con il pulsante destro del mouse sulla riga dell'agente e quindi scegliere un'opzione dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="0126e-107">For more detailed information and tasks related to an agent, right-click the row for that agent, and then click an option on the shortcut menu.</span></span> <span data-ttu-id="0126e-108">Per modificare la modalità di visualizzazione dei dati nella griglia, fare clic con il pulsante destro del mouse sulla griglia, quindi scegliere una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0126e-108">To change the way that the grid displays data, right-click the grid, and then click one of the following options:</span></span>  
  
-   <span data-ttu-id="0126e-109">**Ordinamento**: consente di ordinare una o più colonne nella finestra di dialogo **Ordina colonne** .</span><span class="sxs-lookup"><span data-stu-id="0126e-109">**Sort**: Sort on one or more columns in the **Sort Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="0126e-110">**Seleziona colonne da visualizzare**: consente di selezionare le colonne da visualizzare e l'ordine di visualizzazione nella finestra di dialogo **Seleziona colonne** .</span><span class="sxs-lookup"><span data-stu-id="0126e-110">**Choose Columns to Show**: Select which columns to display and the order in which to display them in the **Choose Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="0126e-111">**Filtro**: consente di filtrare le righe nella griglia in base a valori di colonna nella finestra di dialogo **Impostazioni filtro** .</span><span class="sxs-lookup"><span data-stu-id="0126e-111">**Filter**: Filter rows in the grid based on column values in the **Filter Settings** dialog box.</span></span>  
  
-   <span data-ttu-id="0126e-112">**Cancella filtro**: consente di cancellare qualsiasi impostazione di filtro per la griglia.</span><span class="sxs-lookup"><span data-stu-id="0126e-112">**Clear Filter**: Clear any filter settings for the grid.</span></span>  
  
 <span data-ttu-id="0126e-113">Le impostazioni di filtro sono specifiche di ogni griglia.</span><span class="sxs-lookup"><span data-stu-id="0126e-113">Filter settings are specific to each grid.</span></span> <span data-ttu-id="0126e-114">La selezione e l'ordinamento delle colonne vengono applicati a tutte le griglie dello stesso tipo, ad esempio la griglia delle pubblicazioni per ogni server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="0126e-114">Column selection and sorting are applied to all grids of the same type, such as the publications grid for each Publisher.</span></span>  
  
 <span data-ttu-id="0126e-115">**Status**</span><span class="sxs-lookup"><span data-stu-id="0126e-115">**Status**</span></span>  
 <span data-ttu-id="0126e-116">Stato di ogni agente di replica associato alla pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="0126e-116">The status of each replication agent associated with the publication.</span></span> <span data-ttu-id="0126e-117">Nell'elenco seguente vengono indicati i valori di stato possibili:</span><span class="sxs-lookup"><span data-stu-id="0126e-117">The following list shows the possible status values:</span></span>  
  
-   <span data-ttu-id="0126e-118">Errore</span><span class="sxs-lookup"><span data-stu-id="0126e-118">Error</span></span>  
  
-   <span data-ttu-id="0126e-119">Ripetizione comando non riuscito</span><span class="sxs-lookup"><span data-stu-id="0126e-119">Retrying failed commands</span></span>  
  
-   <span data-ttu-id="0126e-120">Non in esecuzione</span><span class="sxs-lookup"><span data-stu-id="0126e-120">Not running</span></span>  
  
-   <span data-ttu-id="0126e-121">In esecuzione</span><span class="sxs-lookup"><span data-stu-id="0126e-121">Running</span></span>  
  
-   <span data-ttu-id="0126e-122">Completi</span><span class="sxs-lookup"><span data-stu-id="0126e-122">Completed</span></span>  
  
 <span data-ttu-id="0126e-123">**Agent**</span><span class="sxs-lookup"><span data-stu-id="0126e-123">**Agent**</span></span>  
 <span data-ttu-id="0126e-124">Nome di ogni agente di replica associato alla pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="0126e-124">The name of each replication agent associated with the publication.</span></span> <span data-ttu-id="0126e-125">L'agente di distribuzione è associato alle sottoscrizioni della pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="0126e-125">The Distribution Agent is associated with subscriptions to this publication.</span></span> <span data-ttu-id="0126e-126">Per altre informazioni, vedere [Visualizzare le informazioni ed eseguire attività usando Monitoraggio replica](monitor/view-information-and-perform-tasks-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="0126e-126">For more information, see [View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md).</span></span>  
  
 <span data-ttu-id="0126e-127">**Ultima ora di inizio**</span><span class="sxs-lookup"><span data-stu-id="0126e-127">**Last Start Time**</span></span>  
 <span data-ttu-id="0126e-128">Ultima ora di avvio dell'agente.</span><span class="sxs-lookup"><span data-stu-id="0126e-128">The last time the agent started.</span></span>  
  
 <span data-ttu-id="0126e-129">**Duration**</span><span class="sxs-lookup"><span data-stu-id="0126e-129">**Duration**</span></span>  
 <span data-ttu-id="0126e-130">Quantità di tempo di esecuzione dell'agente.</span><span class="sxs-lookup"><span data-stu-id="0126e-130">The amount of time the agent has run.</span></span> <span data-ttu-id="0126e-131">Il valore di durata rappresenta il tempo trascorso se l'agente è ancora in esecuzione e la durata totale se l'agente è stato eseguito in precedenza.</span><span class="sxs-lookup"><span data-stu-id="0126e-131">The time represents elapsed time if the agent is currently running and total time if the agent has run previously.</span></span>  
  
 <span data-ttu-id="0126e-132">**Ultima azione**</span><span class="sxs-lookup"><span data-stu-id="0126e-132">**Last Action**</span></span>  
 <span data-ttu-id="0126e-133">Ultima azione eseguita durante la più recente esecuzione dell'agente.</span><span class="sxs-lookup"><span data-stu-id="0126e-133">The last action performed during the most recent run of the agent.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0126e-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0126e-134">See Also</span></span>  
 <span data-ttu-id="0126e-135">[Avviare Monitoraggio replica](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="0126e-135">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="0126e-136">[Visualizzare le informazioni ed eseguire attività usando Monitoraggio replica](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="0126e-136">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 [<span data-ttu-id="0126e-137">Monitoraggio della replica</span><span class="sxs-lookup"><span data-stu-id="0126e-137">Monitoring Replication</span></span>](monitoring-replication.md)  
  
  
