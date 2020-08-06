---
title: Informazioni sulla pubblicazione, Tutte le sottoscrizioni (Pubblicazione transazionale) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.publicationinfo.allsubscriptions.tran.f1
ms.assetid: 7073350c-f667-4f70-88e9-152c9a1b08dd
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ccc34bbe0933f4558478bd1d8276898219016e24
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625332"
---
# <a name="publication-information-all-subscriptions-transactional-publication"></a><span data-ttu-id="0d987-102">Informazioni sulla pubblicazione, Tutte le sottoscrizioni (Pubblicazione transazionale)</span><span class="sxs-lookup"><span data-stu-id="0d987-102">Publication Information, All Subscriptions (Transactional Publication)</span></span>
  <span data-ttu-id="0d987-103"> La scheda **Tutte le sottoscrizioni** visualizza informazioni su tutte le sottoscrizioni della pubblicazione transazionale selezionata.</span><span class="sxs-lookup"><span data-stu-id="0d987-103">The **All Subscriptions** tab displays information on all subscriptions to the selected transactional publication.</span></span>  
  
## <a name="options"></a><span data-ttu-id="0d987-104">Opzioni</span><span class="sxs-lookup"><span data-stu-id="0d987-104">Options</span></span>  
 <span data-ttu-id="0d987-105">Per ulteriori informazioni su una sottoscrizione e sulle attività correlate, fare clic con il pulsante destro del mouse sulla riga della sottoscrizione e quindi scegliere un'opzione dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="0d987-105">For more detailed information and tasks related to a subscription, right-click the row for that subscription, and then click an option on the shortcut menu.</span></span> <span data-ttu-id="0d987-106">Per modificare la modalità di visualizzazione dei dati nella griglia, fare clic con il pulsante destro del mouse sulla griglia, quindi scegliere una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0d987-106">To change the way that the grid displays data, right-click the grid, and then click one of the following options:</span></span>  
  
-   <span data-ttu-id="0d987-107">**Ordinamento**: consente di ordinare una o più colonne nella finestra di dialogo **Ordina colonne** .</span><span class="sxs-lookup"><span data-stu-id="0d987-107">**Sort**: Sort on one or more columns in the **Sort Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="0d987-108">**Seleziona colonne da visualizzare**: consente di selezionare le colonne da visualizzare e l'ordine di visualizzazione nella finestra di dialogo **Seleziona colonne** .</span><span class="sxs-lookup"><span data-stu-id="0d987-108">**Choose Columns to Show**: Select which columns to display and the order in which to display them in the **Choose Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="0d987-109">**Filtro**: consente di filtrare le righe nella griglia in base a valori di colonna nella finestra di dialogo **Impostazioni filtro** .</span><span class="sxs-lookup"><span data-stu-id="0d987-109">**Filter**: Filter rows in the grid based on column values in the **Filter Settings** dialog box.</span></span>  
  
-   <span data-ttu-id="0d987-110">**Cancella filtro**: consente di cancellare qualsiasi impostazione di filtro per la griglia.</span><span class="sxs-lookup"><span data-stu-id="0d987-110">**Clear Filter**: Clear any filter settings for the grid.</span></span>  
  
 <span data-ttu-id="0d987-111">Le impostazioni di filtro sono specifiche di ogni griglia.</span><span class="sxs-lookup"><span data-stu-id="0d987-111">Filter settings are specific to each grid.</span></span> <span data-ttu-id="0d987-112">La selezione e l'ordinamento delle colonne vengono applicati a tutte le griglie dello stesso tipo, ad esempio la griglia delle pubblicazioni per ogni server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="0d987-112">Column selection and sorting are applied to all grids of the same type, such as the publications grid for each Publisher.</span></span>  
  
 <span data-ttu-id="0d987-113">**Mostra**</span><span class="sxs-lookup"><span data-stu-id="0d987-113">**Show**</span></span>  
 <span data-ttu-id="0d987-114">Solo [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="0d987-114">[!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions only.</span></span> <span data-ttu-id="0d987-115">Consente di selezionare gli stati della sottoscrizione da visualizzare per il tipo di sottoscrizione selezionato.</span><span class="sxs-lookup"><span data-stu-id="0d987-115">Select the subscription states to display for the selected subscription type.</span></span> <span data-ttu-id="0d987-116">Ad esempio, è possibile scegliere di visualizzare solo le sottoscrizioni con errori.</span><span class="sxs-lookup"><span data-stu-id="0d987-116">For example, you can select to display only those subscriptions that have an error.</span></span>  
  
 <span data-ttu-id="0d987-117">**Status**</span><span class="sxs-lookup"><span data-stu-id="0d987-117">**Status**</span></span>  
 <span data-ttu-id="0d987-118">Stato di ogni sottoscrizione determinato dallo stato dell'agente di distribuzione o dell'agente di lettura log. Viene visualizzato lo stato con priorità più alta. Lo stato può inoltre essere determinato dall'agente di lettura coda nel caso in cui vengano utilizzate sottoscrizioni ad aggiornamento in coda.</span><span class="sxs-lookup"><span data-stu-id="0d987-118">The status of each subscription, which is determined by the status of the Distribution Agent or the Log Reader Agent (the higher priority status is displayed; the status can also be determined by the Queue Reader Agent if queued updating subscriptions are used).</span></span>  
  
 <span data-ttu-id="0d987-119">Per impostazione predefinita, la griglia contenente le informazioni sulla sottoscrizione viene ordinata in base alla colonna **Stato** e quindi ordinata in base alla colonna **Prestazioni** per le sottoscrizioni che hanno lo stesso stato.</span><span class="sxs-lookup"><span data-stu-id="0d987-119">By default, the grid containing subscription information is sorted by the **Status** column (and then sorted by the **Performance** column for those subscriptions with the same status).</span></span> <span data-ttu-id="0d987-120">Nell'elenco seguente vengono indicati i valori di stato possibili e l'ordinamento di tali valori, ad esempio gli errori vengono sempre visualizzati nella parte superiore della griglia.</span><span class="sxs-lookup"><span data-stu-id="0d987-120">The following list shows the possible status values and the sort order for the values (for example, errors are always shown at the top of the grid).</span></span>  
  
-   <span data-ttu-id="0d987-121">Errore</span><span class="sxs-lookup"><span data-stu-id="0d987-121">Error</span></span>  
  
-   <span data-ttu-id="0d987-122">Prestazioni critiche (solo[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] e versioni successive).</span><span class="sxs-lookup"><span data-stu-id="0d987-122">Performance critical ([!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions only)</span></span>  
  
-   <span data-ttu-id="0d987-123">Scadenza imminente/Scaduta (solo[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] e versioni successive)</span><span class="sxs-lookup"><span data-stu-id="0d987-123">Expiring soon/Expired ([!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions only)</span></span>  
  
-   <span data-ttu-id="0d987-124">Sottoscrizione non inizializzata (solo[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] e versioni successive)</span><span class="sxs-lookup"><span data-stu-id="0d987-124">Uninitialized subscription ([!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions only)</span></span>  
  
-   <span data-ttu-id="0d987-125">Ripetizione comando non riuscito</span><span class="sxs-lookup"><span data-stu-id="0d987-125">Retrying failed command</span></span>  
  
-   <span data-ttu-id="0d987-126">Non in esecuzione</span><span class="sxs-lookup"><span data-stu-id="0d987-126">Not Running</span></span>  
  
-   <span data-ttu-id="0d987-127">In esecuzione</span><span class="sxs-lookup"><span data-stu-id="0d987-127">Running</span></span>  
  
 <span data-ttu-id="0d987-128">L'ordinamento determina inoltre il valore da visualizzare quando per una particolare sottoscrizione sono disponibili più stati.</span><span class="sxs-lookup"><span data-stu-id="0d987-128">The sort order also determines which value is displayed if a given subscription is in more than one state.</span></span> <span data-ttu-id="0d987-129">Se, ad esempio, per una sottoscrizione sono presenti errori e la scadenza della sottoscrizione è imminente, nella colonna **Stato** sarà visualizzato il valore **Errore**.</span><span class="sxs-lookup"><span data-stu-id="0d987-129">For example, if a subscription has an error and is expiring soon, the **Status** column displays **Error**.</span></span>  
  
 <span data-ttu-id="0d987-130">I valori di stato **Prestazioni critiche**, **Scadenza imminente/Scaduta**e **Sottoscrizione non inizializzata** sono avvisi.</span><span class="sxs-lookup"><span data-stu-id="0d987-130">The status values **Performance critical**, **Expiring soon/Expired**, and **Uninitialized subscription** are warnings.</span></span> <span data-ttu-id="0d987-131">Quando viene visualizzato un avviso, nella colonna **Stato** viene inoltre visualizzato se è in esecuzione un agente.</span><span class="sxs-lookup"><span data-stu-id="0d987-131">When a warning is displayed, the **Status** column also displays if an agent is running.</span></span> <span data-ttu-id="0d987-132">Ad esempio, lo stato potrebbe essere **In esecuzione, Prestazioni critiche**.</span><span class="sxs-lookup"><span data-stu-id="0d987-132">For example, the status could be **Running, Performance critical**.</span></span>  
  
 <span data-ttu-id="0d987-133">I valori di stato **Prestazioni critiche** e **Scadenza imminente/Scaduta** vengono visualizzati sono se sono stati impostati valori soglia.</span><span class="sxs-lookup"><span data-stu-id="0d987-133">The status values **Performance critical** and **Expiring soon/Expired** are displayed only if thresholds are set.</span></span> <span data-ttu-id="0d987-134">Per informazioni sulle misurazioni delle prestazioni e sull'impostazione dei valori soglia, vedere [Monitorare le prestazioni con Monitoraggio replica](monitor/monitor-performance-with-replication-monitor.md) e [Impostare valori di soglia e avvisi in Monitoraggio replica](monitor/set-thresholds-and-warnings-in-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="0d987-134">For information on performance measurements and setting thresholds, see [Monitor Performance with Replication Monitor](monitor/monitor-performance-with-replication-monitor.md) and [Set Thresholds and Warnings in Replication Monitor](monitor/set-thresholds-and-warnings-in-replication-monitor.md).</span></span>  
  
 <span data-ttu-id="0d987-135">**Sottoscrizione**</span><span class="sxs-lookup"><span data-stu-id="0d987-135">**Subscription**</span></span>  
 <span data-ttu-id="0d987-136">Nome di ogni sottoscrizione nel formato: *SubscriberName: SubscriptionDatabaseName*.</span><span class="sxs-lookup"><span data-stu-id="0d987-136">The name of each subscription, in the form: *SubscriberName: SubscriptionDatabaseName*.</span></span>  
  
 <span data-ttu-id="0d987-137">**Prestazioni**</span><span class="sxs-lookup"><span data-stu-id="0d987-137">**Performance**</span></span>  
 <span data-ttu-id="0d987-138">Solo[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="0d987-138">[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions only.</span></span> <span data-ttu-id="0d987-139">La valutazione delle prestazioni per ogni sottoscrizione è basata sulle misure più recenti rilevate da Monitoraggio replica e non riflette le prestazioni cronologiche.</span><span class="sxs-lookup"><span data-stu-id="0d987-139">The performance rating for each subscription is based on the most recent measurements taken by Replication Monitor and does not reflect historical performance.</span></span> <span data-ttu-id="0d987-140">Le prestazioni vengono misurate per le sottoscrizioni delle pubblicazioni per le quali sono state definite soglie di prestazione. Se le soglie di prestazione non sono state definite per una pubblicazione, in questa colonna viene visualizzato **Non attivato**.</span><span class="sxs-lookup"><span data-stu-id="0d987-140">Performance is measured for subscriptions to publications that have performance thresholds defined; if performance thresholds are not defined for a publication, this column displays **Not enabled**.</span></span> <span data-ttu-id="0d987-141">La valutazione delle prestazioni può corrispondere a uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="0d987-141">The performance rating is one of the following values:</span></span>  
  
-   <span data-ttu-id="0d987-142">Eccellente</span><span class="sxs-lookup"><span data-stu-id="0d987-142">Excellent</span></span>  
  
-   <span data-ttu-id="0d987-143">Buono</span><span class="sxs-lookup"><span data-stu-id="0d987-143">Good</span></span>  
  
-   <span data-ttu-id="0d987-144">Sufficiente</span><span class="sxs-lookup"><span data-stu-id="0d987-144">Fair</span></span>  
  
-   <span data-ttu-id="0d987-145">Scarso</span><span class="sxs-lookup"><span data-stu-id="0d987-145">Poor</span></span>  
  
-   <span data-ttu-id="0d987-146">Critico</span><span class="sxs-lookup"><span data-stu-id="0d987-146">Critical</span></span>  
  
 <span data-ttu-id="0d987-147">Se le prestazioni sono critiche, nella colonna **Stato** viene visualizzato **Prestazioni critiche** .</span><span class="sxs-lookup"><span data-stu-id="0d987-147">If performance is critical, **Performance Critical** is displayed in the **Status** column.</span></span> <span data-ttu-id="0d987-148">Per altre informazioni sulla modalità con cui vengono definite le valutazioni delle prestazioni e impostate le soglie di prestazione, vedere [Monitorare le prestazioni con Monitoraggio replica](monitor/monitor-performance-with-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="0d987-148">For more information on how performance ratings are defined and how performance thresholds are set, see [Monitor Performance with Replication Monitor](monitor/monitor-performance-with-replication-monitor.md).</span></span>  
  
 <span data-ttu-id="0d987-149">**Latency**</span><span class="sxs-lookup"><span data-stu-id="0d987-149">**Latency**</span></span>  
 <span data-ttu-id="0d987-150">Solo[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="0d987-150">[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions only.</span></span> <span data-ttu-id="0d987-151">Tempo medio che intercorre tra l'esecuzione del commit di una transazione nel server di pubblicazione e l'esecuzione del commit della transazione corrispondente nel Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="0d987-151">The average amount of time that elapses between a transaction being committed at the Publisher and the corresponding transaction being committed at the Subscriber.</span></span> <span data-ttu-id="0d987-152">La latenza visualizzata è basata sulle misure più recenti rilevate da Monitoraggio replica.</span><span class="sxs-lookup"><span data-stu-id="0d987-152">The latency displayed is based on the most recent measurements taken by Replication Monitor.</span></span> <span data-ttu-id="0d987-153">Per altre informazioni sulla misurazione della latenza, vedere [Misurare la latenza e convalidare le connessioni per la replica transazionale](monitor/measure-latency-and-validate-connections-for-transactional-replication.md).</span><span class="sxs-lookup"><span data-stu-id="0d987-153">For more information about measuring latency, see [Measure Latency and Validate Connections for Transactional Replication](monitor/measure-latency-and-validate-connections-for-transactional-replication.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d987-154">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0d987-154">See Also</span></span>  
 <span data-ttu-id="0d987-155">[Avviare Monitoraggio replica](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="0d987-155">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="0d987-156">[Visualizzare le informazioni ed eseguire attività usando Monitoraggio replica](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="0d987-156">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 [<span data-ttu-id="0d987-157">Monitoraggio della replica</span><span class="sxs-lookup"><span data-stu-id="0d987-157">Monitoring Replication</span></span>](monitoring-replication.md)  
  
  
