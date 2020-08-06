---
title: Replica di SQL Server finestra di dialogo ' informazioni editore ' | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.publisherinfo.publications.f1
ms.assetid: 0b2e3d4e-03b7-4c31-8f96-48648d750010
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d3797ae4f9fe8f42b4abec715c63bc627c2a62cf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714147"
---
# <a name="sql-server-replication-publisher-information-dialog-box"></a><span data-ttu-id="cf446-102">Replica di SQL Server finestra di dialogo ' informazioni editore '</span><span class="sxs-lookup"><span data-stu-id="cf446-102">SQL Server Replication 'Publisher Information' dialog box</span></span>
  <span data-ttu-id="cf446-103">Nella scheda **Pubblicazioni** vengono fornite informazioni di riepilogo relative a tutte le pubblicazioni nel server di pubblicazione selezionato nel riquadro sinistro.</span><span class="sxs-lookup"><span data-stu-id="cf446-103">The **Publications** tab provides summary information for all publications at the Publisher selected in the left pane.</span></span>  
  
## <a name="options"></a><span data-ttu-id="cf446-104">Opzioni</span><span class="sxs-lookup"><span data-stu-id="cf446-104">Options</span></span>  
 <span data-ttu-id="cf446-105">Per modificare la modalità di visualizzazione dei dati nella griglia, fare clic con il pulsante destro del mouse sulla griglia, quindi scegliere una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cf446-105">To change the way that the grid displays data, right-click the grid, and then click one of the following options:</span></span>  
  
-   <span data-ttu-id="cf446-106">**Ordinamento**: consente di ordinare una o più colonne nella finestra di dialogo **Ordina colonne** .</span><span class="sxs-lookup"><span data-stu-id="cf446-106">**Sort**: Sort on one or more columns in the **Sort Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="cf446-107">**Seleziona colonne da visualizzare**: consente di selezionare le colonne da visualizzare e l'ordine di visualizzazione nella finestra di dialogo **Seleziona colonne** .</span><span class="sxs-lookup"><span data-stu-id="cf446-107">**Choose Columns to Show**: Select which columns to display and the order in which to display them in the **Choose Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="cf446-108">**Filtro**: consente di filtrare le righe nella griglia in base a valori di colonna nella finestra di dialogo **Impostazioni filtro** .</span><span class="sxs-lookup"><span data-stu-id="cf446-108">**Filter**: Filter rows in the grid based on column values in the **Filter Settings** dialog box.</span></span>  
  
-   <span data-ttu-id="cf446-109">**Cancella filtro**: consente di cancellare qualsiasi impostazione di filtro per la griglia.</span><span class="sxs-lookup"><span data-stu-id="cf446-109">**Clear Filter**: Clear any filter settings for the grid.</span></span>  
  
 <span data-ttu-id="cf446-110">Le impostazioni di filtro sono specifiche di ogni griglia.</span><span class="sxs-lookup"><span data-stu-id="cf446-110">Filter settings are specific to each grid.</span></span> <span data-ttu-id="cf446-111">La selezione e l'ordinamento delle colonne vengono applicati a tutte le griglie dello stesso tipo, ad esempio la griglia delle pubblicazioni per ogni server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="cf446-111">Column selection and sorting are applied to all grids of the same type, such as the publications grid for each Publisher.</span></span>  
  
 <span data-ttu-id="cf446-112">**Status**</span><span class="sxs-lookup"><span data-stu-id="cf446-112">**Status**</span></span>  
 <span data-ttu-id="cf446-113">Stato di ogni pubblicazione determinato in base allo stato di priorità più elevata delle rispettive sottoscrizioni.</span><span class="sxs-lookup"><span data-stu-id="cf446-113">The status of each publication, which is determined by the highest priority status of its subscriptions.</span></span> <span data-ttu-id="cf446-114">Per impostazione predefinita, la griglia contenente le informazioni relative alle pubblicazioni viene ordinata in base alla colonna **Stato** .</span><span class="sxs-lookup"><span data-stu-id="cf446-114">By default, the grid containing publication information is sorted by the **Status** column.</span></span> <span data-ttu-id="cf446-115">Nell'elenco seguente vengono indicati i valori di stato possibili e l'ordinamento di tali valori, ad esempio gli errori vengono sempre visualizzati nella parte superiore della griglia.</span><span class="sxs-lookup"><span data-stu-id="cf446-115">The following list shows the possible status values and the sort order for the values (for example, errors are always shown at the top of the grid):</span></span>  
  
-   <span data-ttu-id="cf446-116">Errore</span><span class="sxs-lookup"><span data-stu-id="cf446-116">Error</span></span>  
  
-   <span data-ttu-id="cf446-117">Prestazioni critiche</span><span class="sxs-lookup"><span data-stu-id="cf446-117">Performance critical</span></span>  
  
-   <span data-ttu-id="cf446-118">Ripetizione comando non riuscito</span><span class="sxs-lookup"><span data-stu-id="cf446-118">Retrying failed command</span></span>  
  
-   <span data-ttu-id="cf446-119">OK</span><span class="sxs-lookup"><span data-stu-id="cf446-119">OK</span></span>  
  
 <span data-ttu-id="cf446-120">Il valore di stato **Prestazioni critiche** fa riferimento alle sottoscrizioni di tipo merge e a quelle transazionali. Per queste ultime, il valore può essere visualizzato solo se è impostata una soglia.</span><span class="sxs-lookup"><span data-stu-id="cf446-120">The status value **Performance critical** is relevant for transactional subscriptions and merge subscriptions; for transactional subscriptions, it can be displayed only if a threshold is set.</span></span> <span data-ttu-id="cf446-121">Per informazioni sulle misurazioni delle prestazioni e sull'impostazione dei valori soglia, vedere [Monitorare le prestazioni con Monitoraggio replica](monitor/monitor-performance-with-replication-monitor.md) e [Impostare valori di soglia e avvisi in Monitoraggio replica](monitor/set-thresholds-and-warnings-in-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="cf446-121">For information on performance measurements and setting thresholds, see [Monitor Performance with Replication Monitor](monitor/monitor-performance-with-replication-monitor.md) and [Set Thresholds and Warnings in Replication Monitor](monitor/set-thresholds-and-warnings-in-replication-monitor.md).</span></span>  
  
 <span data-ttu-id="cf446-122">**Pubblicazione**</span><span class="sxs-lookup"><span data-stu-id="cf446-122">**Publication**</span></span>  
 <span data-ttu-id="cf446-123">Nome di ogni pubblicazione nel formato: *PublicationDatabaseName: PublicationName*.</span><span class="sxs-lookup"><span data-stu-id="cf446-123">The name of each publication, in the form *PublicationDatabaseName: PublicationName*.</span></span>  
  
 <span data-ttu-id="cf446-124">**Sottoscrizioni**</span><span class="sxs-lookup"><span data-stu-id="cf446-124">**Subscriptions**</span></span>  
 <span data-ttu-id="cf446-125">Numero di sottoscrizioni per ogni pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="cf446-125">The number of subscriptions for each publication.</span></span>  
  
 <span data-ttu-id="cf446-126">**Sincronizzazione in corso**</span><span class="sxs-lookup"><span data-stu-id="cf446-126">**Synchronizing**</span></span>  
 <span data-ttu-id="cf446-127">Numero di sottoscrizioni per ogni pubblicazione delle quali è in corso la sincronizzazione:</span><span class="sxs-lookup"><span data-stu-id="cf446-127">The number of subscriptions for each publication that are currently synchronizing:</span></span>  
  
-   <span data-ttu-id="cf446-128">Per la replica transazionale, lo stato di sincronizzazione in corso indica che l'agente di distribuzione è in esecuzione ma non necessariamente che i dati vengono replicati.</span><span class="sxs-lookup"><span data-stu-id="cf446-128">For transactional replication, "synchronizing" means that the Distribution Agent is running, but data is not necessarily being replicated.</span></span>  
  
-   <span data-ttu-id="cf446-129">Per la replica di tipo merge, lo stato di sincronizzazione in corso indica che l'agente di merge è in esecuzione e che i dati vengono replicati.</span><span class="sxs-lookup"><span data-stu-id="cf446-129">For merge replication, "synchronizing" means that the Merge Agent is running and that data is currently being replicated.</span></span>  
  
-   <span data-ttu-id="cf446-130">Per la replica snapshot, lo stato di sincronizzazione in corso indica che l'agente di distribuzione è in esecuzione e che i dati vengono replicati.</span><span class="sxs-lookup"><span data-stu-id="cf446-130">For snapshot replication, "synchronizing" means that the Distribution Agent is running and that data is currently being replicated.</span></span>  
  
 <span data-ttu-id="cf446-131">**Prestazioni medie correnti** e **Prestazioni peggiori correnti**</span><span class="sxs-lookup"><span data-stu-id="cf446-131">**Current Average Performance** and **Current Worst Performance**</span></span>  
 <span data-ttu-id="cf446-132">Solo [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="cf446-132">[!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions only.</span></span> <span data-ttu-id="cf446-133">Valutazione delle prestazioni medie e di quelle peggiori rispettivamente indicate per tutte le sottoscrizioni di una pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="cf446-133">The average performance rating and the worst performance rating, respectively, for all subscriptions to a publication.</span></span> <span data-ttu-id="cf446-134">Le valutazioni si basano sulle misurazioni più recenti eseguite dallo strumento Monitoraggio replica e non riflettono il livello di prestazioni di una sottoscrizione nel tempo.</span><span class="sxs-lookup"><span data-stu-id="cf446-134">Ratings are based on the most recent measurements taken by Replication Monitor and do not reflect the performance of a subscription over time.</span></span>  
  
 <span data-ttu-id="cf446-135">Per la replica transazionale, in Monitoraggio replica viene visualizzato un valore solo per le pubblicazioni per le quali sono definite soglie di prestazioni.</span><span class="sxs-lookup"><span data-stu-id="cf446-135">For transactional replication, Replication Monitor displays a value only for publications that have performance thresholds defined.</span></span> <span data-ttu-id="cf446-136">Se non sono impostati valori per le soglie delle prestazioni, in questa colonna viene visualizzato il valore **Non attivato**.</span><span class="sxs-lookup"><span data-stu-id="cf446-136">If performance thresholds are not defined for a publication, this column displays **Not enabled**.</span></span> <span data-ttu-id="cf446-137">Per la replica di tipo merge, in Monitoraggio replica viene visualizzato un valore dopo cinque sincronizzazioni con 50 o più modifiche eseguite con lo stesso tipo di connessione (remota o LAN).</span><span class="sxs-lookup"><span data-stu-id="cf446-137">For merge replication, Replication Monitor displays a value after five synchronizations have occurred with 50 or more changes each over the same type of connection (dial-up or LAN).</span></span> <span data-ttu-id="cf446-138">Se sono state eseguite meno di 5 sincronizzazioni con almeno 50 modifiche oppure durante la sincronizzazione più recente sono state apportate meno di 50 modifiche, la colonna è vuota.</span><span class="sxs-lookup"><span data-stu-id="cf446-138">If there have been less than five synchronizations with 50 or more changes or the most recent synchronization has less than 50 changes, this column is blank.</span></span>  
  
 <span data-ttu-id="cf446-139">La valutazione delle prestazioni può corrispondere a uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="cf446-139">The performance rating is one of the following values:</span></span>  
  
-   <span data-ttu-id="cf446-140">Eccellenti</span><span class="sxs-lookup"><span data-stu-id="cf446-140">Excellent</span></span>  
  
-   <span data-ttu-id="cf446-141">Buone</span><span class="sxs-lookup"><span data-stu-id="cf446-141">Good</span></span>  
  
-   <span data-ttu-id="cf446-142">Discrete</span><span class="sxs-lookup"><span data-stu-id="cf446-142">Fair</span></span>  
  
-   <span data-ttu-id="cf446-143">Scarse</span><span class="sxs-lookup"><span data-stu-id="cf446-143">Poor</span></span>  
  
-   <span data-ttu-id="cf446-144">Critico</span><span class="sxs-lookup"><span data-stu-id="cf446-144">Critical</span></span>  
  
 <span data-ttu-id="cf446-145">Per altre informazioni sulla modalità con cui vengono definite le valutazioni delle prestazioni e impostati i valori soglia per le prestazione, vedere [Monitorare le prestazioni con Monitoraggio replica](monitor/monitor-performance-with-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="cf446-145">For more information about how performance ratings are defined and how performance thresholds are set, see [Monitor Performance with Replication Monitor](monitor/monitor-performance-with-replication-monitor.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf446-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cf446-146">See Also</span></span>  
 <span data-ttu-id="cf446-147">[Avviare Monitoraggio replica](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="cf446-147">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="cf446-148">[Visualizzare le informazioni ed eseguire attività usando Monitoraggio replica](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="cf446-148">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 [<span data-ttu-id="cf446-149">Monitoraggio della replica</span><span class="sxs-lookup"><span data-stu-id="cf446-149">Monitoring Replication</span></span>](monitoring-replication.md)  
  
  
