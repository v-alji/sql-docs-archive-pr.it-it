---
title: Informazioni sulla pubblicazione, avvisi (pubblicazione di tipo merge, SQL Server 2005 e versioni successive) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.publicationinfo.warningsandagents.merge.f1
ms.assetid: 9bef3565-5f13-42ac-8723-ebe55b0c11e6
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 75f58a4cd9bd84791acf7fd9d28147ef3bbd6232
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629361"
---
# <a name="publication-information-warnings-merge-publication-sql-server-2005-and-later"></a><span data-ttu-id="81424-102">Informazioni sulla pubblicazione, Avvisi (pubblicazione di tipo merge, SQL Server 2005 e versioni successive)</span><span class="sxs-lookup"><span data-stu-id="81424-102">Publication Information, Warnings (Merge Publication, SQL Server 2005 and Later)</span></span>
  <span data-ttu-id="81424-103"> La scheda **Avvisi** è disponibile per i server di distribuzione che eseguono [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="81424-103">The **Warnings** tab is available for Distributors that are running [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions.</span></span> <span data-ttu-id="81424-104">La scheda **Avvisi** consente di eseguire le attività seguenti per la pubblicazione selezionata:</span><span class="sxs-lookup"><span data-stu-id="81424-104">The **Warnings** tab allows you to perform the following tasks for the selected publication:</span></span>  
  
-   <span data-ttu-id="81424-105">Abilitazione di avvisi.</span><span class="sxs-lookup"><span data-stu-id="81424-105">Enable warnings.</span></span>  
  
-   <span data-ttu-id="81424-106">Specificare valori soglia associati agli avvisi.</span><span class="sxs-lookup"><span data-stu-id="81424-106">Specify thresholds associated with warnings.</span></span>  
  
-   <span data-ttu-id="81424-107">Definire messaggi di avviso associati ad avvisi.</span><span class="sxs-lookup"><span data-stu-id="81424-107">Define alerts associated with warnings.</span></span>  
  
## <a name="warnings-thresholds-and-alerts"></a><span data-ttu-id="81424-108">Avvisi, soglie e messaggi di avviso</span><span class="sxs-lookup"><span data-stu-id="81424-108">Warnings, Thresholds, and Alerts</span></span>  
 <span data-ttu-id="81424-109">Per impostazione predefinita, Monitoraggio replica visualizza avvisi per le sottoscrizioni non inizializzate, includendo lo stato **Sottoscrizione non inizializzata** come avviso nella colonna **Stato** delle pagine contenenti informazioni sulla sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="81424-109">By default, Replication Monitor displays warnings for uninitialized subscriptions: a status of **Uninitialized subscription** is displayed as a warning in the **Status** column of pages that include subscription information.</span></span> <span data-ttu-id="81424-110">Per le pubblicazioni di tipo merge è possibile specificare se le condizioni aggiuntive seguenti generano avvisi:</span><span class="sxs-lookup"><span data-stu-id="81424-110">For merge publications, you can specify whether these additional conditions result in warnings:</span></span>  
  
-   <span data-ttu-id="81424-111">Scadenza imminente della sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="81424-111">Imminent subscription expiration.</span></span>  
  
     <span data-ttu-id="81424-112">Corrisponde all'opzione **Avvisa se una sottoscrizione scade entro il valore soglia**.</span><span class="sxs-lookup"><span data-stu-id="81424-112">This corresponds to the option **Warn if a subscription will expire within the threshold**.</span></span> <span data-ttu-id="81424-113">Se il valore soglia specificato viene raggiunto o superato, lo stato della sottoscrizione viene visualizzato come **Scadenza imminente/Scaduta** , a meno che non sia necessario visualizzare un problema con una priorità più alta.</span><span class="sxs-lookup"><span data-stu-id="81424-113">If the specified threshold is met or exceeded, the subscription status is displayed as **Expiring soon/Expired** (unless an issue with a higher priority needs to be displayed).</span></span>  
  
-   <span data-ttu-id="81424-114">Superamento del tempo di sincronizzazione specificato.</span><span class="sxs-lookup"><span data-stu-id="81424-114">Exceeding the specified synchronization time.</span></span>  
  
     <span data-ttu-id="81424-115">Corrisponde alle opzioni **Avvisa se la durata del processo di merge per le connessioni remote supera il valore soglia** e **Avvisa se la durata del processo di merge per le connessioni LAN supera il valore soglia**.</span><span class="sxs-lookup"><span data-stu-id="81424-115">This corresponds to the options **Warn if a merge length for dialup connections exceeds the threshold** and **Warn if a merge length for LAN connections exceeds the threshold**.</span></span> <span data-ttu-id="81424-116">È possibile impostare entrambe le soglie, ma solo una delle due viene utilizzata durante una determinata sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="81424-116">Both of these thresholds can be set, but only one is used during a given synchronization.</span></span> <span data-ttu-id="81424-117">L'agente di merge applica la soglia appropriata in base al tipo di connessione.</span><span class="sxs-lookup"><span data-stu-id="81424-117">The Merge Agent applies the appropriate threshold based on the connection type.</span></span>  
  
     <span data-ttu-id="81424-118">Se il valore soglia specificato viene raggiunto o superato, lo stato della sottoscrizione viene visualizzato come **Merge con esecuzione prolungata** , a meno che non debba essere visualizzato un problema con priorità più alta.</span><span class="sxs-lookup"><span data-stu-id="81424-118">If the specified threshold is met or exceeded, the subscription status is displayed as **Long-running merge** (unless an issue with a higher priority needs to be displayed).</span></span>  
  
-   <span data-ttu-id="81424-119">Impossibilità di elaborare il numero di righe specificato in un determinato intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="81424-119">Falling short of processing the specified number of rows in a given amount of time.</span></span>  
  
     <span data-ttu-id="81424-120">Corrisponde alle opzioni **Avvisa se il numero di righe al secondo di cui è stato eseguito il merge per le connessioni remote è minore del valore soglia** e **Avvisa se la durata del processo di merge per le connessioni LAN supera il valore soglia**.</span><span class="sxs-lookup"><span data-stu-id="81424-120">This corresponds to the options **Warn if rows merged per second for dialup connections is less than the threshold** and **Warn if a merge length for LAN connections exceeds the threshold**.</span></span> <span data-ttu-id="81424-121">È possibile impostare entrambe le soglie, ma solo una delle due viene utilizzata durante una determinata sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="81424-121">Both of these thresholds can be set, but only one is used during a given synchronization.</span></span> <span data-ttu-id="81424-122">L'agente di merge applica la soglia appropriata in base al tipo di connessione.</span><span class="sxs-lookup"><span data-stu-id="81424-122">The Merge Agent applies the appropriate threshold based on the connection type.</span></span>  
  
     <span data-ttu-id="81424-123">Se il valore soglia specificato viene raggiunto o superato, lo stato della sottoscrizione viene visualizzato come **Prestazioni critiche** , a meno che non sia necessario visualizzare un problema con una priorità più alta.</span><span class="sxs-lookup"><span data-stu-id="81424-123">If the specified threshold is met or exceeded, the subscription status is displayed as **Performance critical** (unless an issue with a higher priority needs to be displayed).</span></span>  
  
 <span data-ttu-id="81424-124">Quando si abilita un avviso, è inoltre necessario impostare un valore soglia.</span><span class="sxs-lookup"><span data-stu-id="81424-124">When you enable a warning, you also set a threshold.</span></span> <span data-ttu-id="81424-125">Ad esempio, se si abilita l'avviso **Avvisa se la durata del processo di merge per le connessioni LAN supera il valore soglia**, impostare la lunghezza di tempo massima consentita per una sincronizzazione di tipo merge.</span><span class="sxs-lookup"><span data-stu-id="81424-125">For example, if you enable the warning **Warn if a merge length for LAN connections exceeds the threshold**, set the maximum allowable length of time for a merge synchronization.</span></span>  
  
 <span data-ttu-id="81424-126">Oltre a visualizzare un avviso in Monitoraggio replica, il raggiungimento di un valore soglia può inoltre attivare un messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="81424-126">In addition to displaying a warning in Replication Monitor, reaching a threshold can also trigger an alert.</span></span> <span data-ttu-id="81424-127">Gli avvisi vengono definiti facendo clic su **Configura avvisi** e specificando le informazioni appropriate nella finestra di dialogo **Configura avvisi di replica** .</span><span class="sxs-lookup"><span data-stu-id="81424-127">Alerts are defined by clicking **Configure Alerts** and providing information in the **Configure Replication Alerts** dialog box.</span></span>  
  
## <a name="options"></a><span data-ttu-id="81424-128">Opzioni</span><span class="sxs-lookup"><span data-stu-id="81424-128">Options</span></span>  
 <span data-ttu-id="81424-129">**Enabled**</span><span class="sxs-lookup"><span data-stu-id="81424-129">**Enabled**</span></span>  
 <span data-ttu-id="81424-130">Selezionare questa opzione per abilitare un avviso e specificare un valore soglia.</span><span class="sxs-lookup"><span data-stu-id="81424-130">Select to enable a warning and specify a threshold.</span></span>  
  
 <span data-ttu-id="81424-131">**Avviso**</span><span class="sxs-lookup"><span data-stu-id="81424-131">**Alert**</span></span>  
 <span data-ttu-id="81424-132">Selezionare questa opzione per abilitare l'impostazione di avvisi per un determinato avviso di replica.</span><span class="sxs-lookup"><span data-stu-id="81424-132">Select to enable the alert setting for a given replication warning.</span></span>  
  
 <span data-ttu-id="81424-133">**Warning**</span><span class="sxs-lookup"><span data-stu-id="81424-133">**Warning**</span></span>  
 <span data-ttu-id="81424-134">Descrizione dell'avviso associato al valore soglia.</span><span class="sxs-lookup"><span data-stu-id="81424-134">A description of the warning associated with a threshold.</span></span>  
  
 <span data-ttu-id="81424-135">**Soglia**</span><span class="sxs-lookup"><span data-stu-id="81424-135">**Threshold**</span></span>  
 <span data-ttu-id="81424-136">Consente di specificare un valore per la soglia.</span><span class="sxs-lookup"><span data-stu-id="81424-136">Specify a value for the threshold.</span></span>  
  
 <span data-ttu-id="81424-137">**Configurare gli avvisi**</span><span class="sxs-lookup"><span data-stu-id="81424-137">**Configure Alerts**</span></span>  
 <span data-ttu-id="81424-138">Selezionare una riga nella griglia **Avvisi** e fare clic su **Configura avvisi** per aprire la finestra di dialogo **Configura avvisi di replica** .</span><span class="sxs-lookup"><span data-stu-id="81424-138">Select a row in the **Warnings** grid, and click **Configure Alerts** to launch the **Configure Replication Alerts** dialog box.</span></span> <span data-ttu-id="81424-139">Tramite questa finestra di dialogo è possibile definire un avviso associato al valore soglia e all'avviso selezionati.</span><span class="sxs-lookup"><span data-stu-id="81424-139">The dialog box allows you to define an alert, which is associated with the selected threshold and warning.</span></span>  
  
 <span data-ttu-id="81424-140">**Ignora modifiche**</span><span class="sxs-lookup"><span data-stu-id="81424-140">**Discard Changes**</span></span>  
 <span data-ttu-id="81424-141">Fare clic su questo pulsante per ignorare le eventuali modifiche apportate agli avvisi e alle soglie.</span><span class="sxs-lookup"><span data-stu-id="81424-141">Click to discard any changes to warnings and thresholds.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="81424-142"> La scelta del pulsante **Ignora modifiche** non influisce sugli avvisi definiti nella finestra di dialogo **Configura avvisi di replica** .</span><span class="sxs-lookup"><span data-stu-id="81424-142">Clicking **Discard Changes** does not affect alerts defined in the **Configure Replication Alerts** dialog box.</span></span>  
  
 <span data-ttu-id="81424-143">**Salva modifiche**</span><span class="sxs-lookup"><span data-stu-id="81424-143">**Save Changes**</span></span>  
 <span data-ttu-id="81424-144">Fare clic su questo pulsante per salvare le eventuali modifiche apportate agli avvisi e alle soglie.</span><span class="sxs-lookup"><span data-stu-id="81424-144">Click to save any changes to warnings and thresholds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81424-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="81424-145">See Also</span></span>  
 <span data-ttu-id="81424-146">[Avviare Monitoraggio replica](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="81424-146">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="81424-147">[Visualizzare le informazioni ed eseguire attività usando Monitoraggio replica](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="81424-147">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 <span data-ttu-id="81424-148">[Monitorare le prestazioni con monitoraggio replica](monitor/monitor-performance-with-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="81424-148">[Monitor Performance with Replication Monitor](monitor/monitor-performance-with-replication-monitor.md) </span></span>  
 <span data-ttu-id="81424-149">[Monitoraggio della replica](monitoring-replication.md) </span><span class="sxs-lookup"><span data-stu-id="81424-149">[Monitoring Replication](monitoring-replication.md) </span></span>  
 [<span data-ttu-id="81424-150">Impostare valori di soglia e avvisi in Monitoraggio replica</span><span class="sxs-lookup"><span data-stu-id="81424-150">Set Thresholds and Warnings in Replication Monitor</span></span>](monitor/set-thresholds-and-warnings-in-replication-monitor.md)  
  
  
