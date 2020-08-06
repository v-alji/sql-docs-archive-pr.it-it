---
title: Informazioni sulla pubblicazione, Agenti (pubblicazione di tipo merge) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.publicationinfo.downlevelagents.merge.f1
ms.assetid: 73ff590a-20da-4f10-b592-c60b7226d22b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8562a24066efd7cdad01f5559e97d8493a0f73a5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624053"
---
# <a name="publication-information-agents-merge-publication"></a><span data-ttu-id="52207-102">Informazioni sulla pubblicazione, Agenti (pubblicazione di tipo merge)</span><span class="sxs-lookup"><span data-stu-id="52207-102">Publication Information, Agents (Merge Publication)</span></span>
  <span data-ttu-id="52207-103">La scheda **Agenti** visualizza informazioni di riepilogo sull'agente snapshot per la pubblicazione selezionata.</span><span class="sxs-lookup"><span data-stu-id="52207-103">The **Agents** tab displays summary information on the Snapshot Agent for the selected publication.</span></span>  
  
## <a name="options"></a><span data-ttu-id="52207-104">Opzioni</span><span class="sxs-lookup"><span data-stu-id="52207-104">Options</span></span>  
 <span data-ttu-id="52207-105">Per ulteriori informazioni sull'agente snapshot e sulle attività correlate, fare clic con il pulsante destro del mouse sulla riga dell'agente e quindi scegliere un'opzione dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="52207-105">For more detailed information and tasks related to the Snapshot Agent, right-click the row for the agent, and then click an option on the shortcut menu.</span></span> <span data-ttu-id="52207-106">Per modificare la modalità di visualizzazione dei dati nella griglia, fare clic con il pulsante destro del mouse sulla griglia, quindi scegliere una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="52207-106">To change the way that the grid displays data, right-click the grid, and then click one of the following options:</span></span>  
  
-   <span data-ttu-id="52207-107">**Ordinamento**: consente di ordinare una o più colonne nella finestra di dialogo **Ordina colonne** .</span><span class="sxs-lookup"><span data-stu-id="52207-107">**Sort**: Sort on one or more columns in the **Sort Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="52207-108">**Seleziona colonne da visualizzare**: consente di selezionare le colonne da visualizzare e l'ordine di visualizzazione nella finestra di dialogo **Seleziona colonne** .</span><span class="sxs-lookup"><span data-stu-id="52207-108">**Choose Columns to Show**: Select which columns to display and the order in which to display them in the **Choose Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="52207-109">**Filtro**: consente di filtrare le righe nella griglia in base a valori di colonna nella finestra di dialogo **Impostazioni filtro** .</span><span class="sxs-lookup"><span data-stu-id="52207-109">**Filter**: Filter rows in the grid based on column values in the **Filter Settings** dialog box.</span></span>  
  
-   <span data-ttu-id="52207-110">**Cancella filtro**: consente di cancellare qualsiasi impostazione di filtro per la griglia.</span><span class="sxs-lookup"><span data-stu-id="52207-110">**Clear Filter**: Clear any filter settings for the grid.</span></span>  
  
 <span data-ttu-id="52207-111">Le impostazioni di filtro sono specifiche di ogni griglia.</span><span class="sxs-lookup"><span data-stu-id="52207-111">Filter settings are specific to each grid.</span></span> <span data-ttu-id="52207-112">La selezione e l'ordinamento delle colonne vengono applicati a tutte le griglie dello stesso tipo, ad esempio la griglia delle pubblicazioni per ogni server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="52207-112">Column selection and sorting are applied to all grids of the same type, such as the publications grid for each Publisher.</span></span>  
  
 <span data-ttu-id="52207-113">**Status**</span><span class="sxs-lookup"><span data-stu-id="52207-113">**Status**</span></span>  
 <span data-ttu-id="52207-114">Stato dell'agente snapshot.</span><span class="sxs-lookup"><span data-stu-id="52207-114">The status of the Snapshot Agent.</span></span> <span data-ttu-id="52207-115">Nell'elenco seguente vengono indicati i valori di stato possibili:</span><span class="sxs-lookup"><span data-stu-id="52207-115">The following list shows the possible status values:</span></span>  
  
-   <span data-ttu-id="52207-116">Errore</span><span class="sxs-lookup"><span data-stu-id="52207-116">Error</span></span>  
  
-   <span data-ttu-id="52207-117">Ripetizione comando non riuscito</span><span class="sxs-lookup"><span data-stu-id="52207-117">Retrying failed commands</span></span>  
  
-   <span data-ttu-id="52207-118">Non in esecuzione</span><span class="sxs-lookup"><span data-stu-id="52207-118">Not running</span></span>  
  
-   <span data-ttu-id="52207-119">Completi</span><span class="sxs-lookup"><span data-stu-id="52207-119">Completed</span></span>  
  
 <span data-ttu-id="52207-120">**Agent**</span><span class="sxs-lookup"><span data-stu-id="52207-120">**Agent**</span></span>  
 <span data-ttu-id="52207-121">Agente snapshot.</span><span class="sxs-lookup"><span data-stu-id="52207-121">The Snapshot Agent.</span></span> <span data-ttu-id="52207-122">Si tratta dell'unico agente associato a una pubblicazione di tipo merge.</span><span class="sxs-lookup"><span data-stu-id="52207-122">This is the only agent associated with a merge publication.</span></span> <span data-ttu-id="52207-123">L'agente di merge è associato alle sottoscrizioni della pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="52207-123">The Merge Agent is associated with subscriptions to this publication.</span></span> <span data-ttu-id="52207-124">Per altre informazioni, vedere [Visualizzare le informazioni ed eseguire attività usando Monitoraggio replica](monitor/view-information-and-perform-tasks-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="52207-124">For more information, see [View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md).</span></span>  
  
 <span data-ttu-id="52207-125">**Ultima ora inizio**</span><span class="sxs-lookup"><span data-stu-id="52207-125">**Last Start Time**</span></span>  
 <span data-ttu-id="52207-126">Ultima ora di avvio dell'agente.</span><span class="sxs-lookup"><span data-stu-id="52207-126">The last time the agent started.</span></span>  
  
 <span data-ttu-id="52207-127">**Duration**</span><span class="sxs-lookup"><span data-stu-id="52207-127">**Duration**</span></span>  
 <span data-ttu-id="52207-128">Quantità di tempo di esecuzione dell'agente.</span><span class="sxs-lookup"><span data-stu-id="52207-128">The amount of time the agent has run.</span></span> <span data-ttu-id="52207-129">Il valore di durata rappresenta il tempo trascorso se l'agente è ancora in esecuzione e la durata totale se l'agente è stato eseguito in precedenza.</span><span class="sxs-lookup"><span data-stu-id="52207-129">The time represents elapsed time if the agent is currently running and total time if the agent has run previously.</span></span>  
  
 <span data-ttu-id="52207-130">**Ultima azione**</span><span class="sxs-lookup"><span data-stu-id="52207-130">**Last Action**</span></span>  
 <span data-ttu-id="52207-131">Ultima azione eseguita durante la più recente esecuzione dell'agente.</span><span class="sxs-lookup"><span data-stu-id="52207-131">The last action performed during the most recent run of the agent.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52207-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="52207-132">See Also</span></span>  
 <span data-ttu-id="52207-133">[Avviare Monitoraggio replica](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="52207-133">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="52207-134">[Visualizzare le informazioni ed eseguire attività usando Monitoraggio replica](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="52207-134">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 [<span data-ttu-id="52207-135">Monitoraggio della replica</span><span class="sxs-lookup"><span data-stu-id="52207-135">Monitoring Replication</span></span>](monitoring-replication.md)  
  
  
