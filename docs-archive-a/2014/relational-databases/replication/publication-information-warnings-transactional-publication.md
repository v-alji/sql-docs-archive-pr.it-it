---
title: Informazioni sulla pubblicazione, avvisi (pubblicazione transazionale, SQL Server 2005 e versioni successive) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.publicationinfo.warningsandagents.tran.f1
ms.assetid: 4d4baf1d-d0a1-4d09-bec7-137811f43f09
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: cac7ab0f712fe69d3736985921d70b0ce200d474
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717843"
---
# <a name="publication-information-warnings-transactional-publication-sql-server-2005-and-later"></a><span data-ttu-id="17505-102">Informazioni sulla pubblicazione, Avvisi (pubblicazione transazionale, SQL Server 2005 e versioni successive)</span><span class="sxs-lookup"><span data-stu-id="17505-102">Publication Information, Warnings (Transactional Publication, SQL Server 2005 and Later)</span></span>
  <span data-ttu-id="17505-103"> La scheda **Avvisi** è disponibile per i server di distribuzione che eseguono [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="17505-103">The **Warnings** tab is available for Distributors that are running [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions.</span></span> <span data-ttu-id="17505-104">La scheda **Avvisi** consente di eseguire le attività seguenti per la pubblicazione selezionata:</span><span class="sxs-lookup"><span data-stu-id="17505-104">The **Warnings** tab allows you to perform the following tasks for the selected publication:</span></span>  
  
-   <span data-ttu-id="17505-105">Consentire la visualizzazione degli avvisi in Monitoraggio replica.</span><span class="sxs-lookup"><span data-stu-id="17505-105">Enable warnings to be displayed in Replication Monitor.</span></span>  
  
-   <span data-ttu-id="17505-106">Specificare valori soglia associati agli avvisi.</span><span class="sxs-lookup"><span data-stu-id="17505-106">Specify thresholds associated with warnings.</span></span>  
  
-   <span data-ttu-id="17505-107">Definire messaggi di avviso associati ad avvisi.</span><span class="sxs-lookup"><span data-stu-id="17505-107">Define alerts associated with warnings.</span></span>  
  
## <a name="warnings-thresholds-and-alerts"></a><span data-ttu-id="17505-108">Avvisi, soglie e messaggi di avviso</span><span class="sxs-lookup"><span data-stu-id="17505-108">Warnings, Thresholds, and Alerts</span></span>  
 <span data-ttu-id="17505-109">Per impostazione predefinita, Monitoraggio replica visualizza avvisi per le sottoscrizioni non inizializzate, includendo lo stato **Sottoscrizione non inizializzata** come avviso nella colonna **Stato** delle pagine contenenti informazioni sulla sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="17505-109">By default, Replication Monitor displays warnings for uninitialized subscriptions: a status of **Uninitialized subscription** is displayed as a warning in the **Status** column of pages that include subscription information.</span></span> <span data-ttu-id="17505-110">Per le pubblicazioni transazionali è possibile specificare se le condizioni aggiuntive seguenti generano avvisi:</span><span class="sxs-lookup"><span data-stu-id="17505-110">For transactional publications, you can specify whether these additional conditions result in warnings:</span></span>  
  
-   <span data-ttu-id="17505-111">Scadenza imminente della sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="17505-111">Imminent subscription expiration.</span></span>  
  
     <span data-ttu-id="17505-112">Corrisponde all'opzione **Avvisa se una sottoscrizione scade entro il valore soglia**.</span><span class="sxs-lookup"><span data-stu-id="17505-112">This corresponds to the option **Warn if a subscription will expire within the threshold**.</span></span> <span data-ttu-id="17505-113">Se il valore soglia specificato viene raggiunto o superato, lo stato della sottoscrizione viene visualizzato come **Scadenza imminente/Scaduta** , a meno che non sia necessario visualizzare un problema con una priorità più alta.</span><span class="sxs-lookup"><span data-stu-id="17505-113">If the specified threshold is met or exceeded, the subscription status is displayed as **Expiring soon/Expired** (unless an issue with a higher priority needs to be displayed).</span></span>  
  
-   <span data-ttu-id="17505-114">Superamento della latenza specificata.</span><span class="sxs-lookup"><span data-stu-id="17505-114">Exceeding the specified latency.</span></span> <span data-ttu-id="17505-115">Indica la quantità di tempo che intercorre tra l'esecuzione del commit di una transazione nel server di pubblicazione e l'esecuzione del commit della transazione corrispondente nel Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="17505-115">This is the amount of time that elapses between a transaction being committed at the Publisher and the corresponding transaction being committed at the Subscriber.</span></span>  
  
     <span data-ttu-id="17505-116">Corrisponde all'opzione **Avvisa se la latenza supera il valore soglia**.</span><span class="sxs-lookup"><span data-stu-id="17505-116">This corresponds to the option **Warn if latency exceeds the threshold**.</span></span> <span data-ttu-id="17505-117">Se il valore soglia specificato viene raggiunto o superato, lo stato della sottoscrizione viene visualizzato come **Prestazioni critiche** , a meno che non sia necessario visualizzare un problema con una priorità più alta.</span><span class="sxs-lookup"><span data-stu-id="17505-117">If the specified threshold is met or exceeded, the subscription status is displayed as **Performance critical** (unless an issue with a higher priority needs to be displayed).</span></span> <span data-ttu-id="17505-118">Il valore soglia viene inoltre utilizzato per determinare una valutazione delle prestazioni, visualizzata nella colonna **Prestazioni** delle pagine che contengono informazioni sulle sottoscrizioni.</span><span class="sxs-lookup"><span data-stu-id="17505-118">The threshold is also used to provide a performance rating, which is displayed in the **Performance** column of pages that include subscription information.</span></span> <span data-ttu-id="17505-119">La valutazione delle prestazioni può corrispondere a uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="17505-119">The performance rating is one of the following values:</span></span>  
  
    -   <span data-ttu-id="17505-120">Eccellente</span><span class="sxs-lookup"><span data-stu-id="17505-120">Excellent</span></span>  
  
    -   <span data-ttu-id="17505-121">Buono</span><span class="sxs-lookup"><span data-stu-id="17505-121">Good</span></span>  
  
    -   <span data-ttu-id="17505-122">Sufficiente</span><span class="sxs-lookup"><span data-stu-id="17505-122">Fair</span></span>  
  
    -   <span data-ttu-id="17505-123">Scarso</span><span class="sxs-lookup"><span data-stu-id="17505-123">Poor</span></span>  
  
    -   <span data-ttu-id="17505-124">Critico</span><span class="sxs-lookup"><span data-stu-id="17505-124">Critical</span></span>  
  
 <span data-ttu-id="17505-125">Quando si abilita un avviso, è inoltre necessario impostare un valore soglia.</span><span class="sxs-lookup"><span data-stu-id="17505-125">When you enable a warning, you also set a threshold.</span></span> <span data-ttu-id="17505-126">Se, ad esempio, si attiva l'avviso **Avvisa se la latenza supera il valore soglia**, selezionare la quantità di tempo consentita tra il commit di una transazione nel server di pubblicazione e il commit della transazione nel Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="17505-126">For example, if you enable the warning **Warn if latency exceeds the threshold**, select the amount of time allowable between a transaction being committed at the Publisher and the transaction being committed at the Subscriber.</span></span>  
  
 <span data-ttu-id="17505-127">Oltre a visualizzare un avviso in Monitoraggio replica, il raggiungimento di un valore soglia può inoltre attivare un messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="17505-127">In addition to displaying a warning in Replication Monitor, reaching a threshold can also trigger an alert.</span></span> <span data-ttu-id="17505-128">Gli avvisi vengono definiti facendo clic su **Configura avvisi** e specificando le informazioni appropriate nella finestra di dialogo **Configura avvisi di replica** .</span><span class="sxs-lookup"><span data-stu-id="17505-128">Alerts are defined by clicking **Configure Alerts** and providing information in the **Configure Replication Alerts** dialog box.</span></span>  
  
## <a name="options"></a><span data-ttu-id="17505-129">Opzioni</span><span class="sxs-lookup"><span data-stu-id="17505-129">Options</span></span>  
 <span data-ttu-id="17505-130">**Enabled**</span><span class="sxs-lookup"><span data-stu-id="17505-130">**Enabled**</span></span>  
 <span data-ttu-id="17505-131">Selezionare questa opzione per abilitare un avviso e specificare un valore soglia.</span><span class="sxs-lookup"><span data-stu-id="17505-131">Select to enable a warning and specify a threshold.</span></span>  
  
 <span data-ttu-id="17505-132">**Warning**</span><span class="sxs-lookup"><span data-stu-id="17505-132">**Warning**</span></span>  
 <span data-ttu-id="17505-133">Descrizione dell'avviso associato al valore soglia.</span><span class="sxs-lookup"><span data-stu-id="17505-133">A description of the warning associated with a threshold.</span></span>  
  
 <span data-ttu-id="17505-134">**Soglia**</span><span class="sxs-lookup"><span data-stu-id="17505-134">**Threshold**</span></span>  
 <span data-ttu-id="17505-135">Consente di specificare un valore per la soglia.</span><span class="sxs-lookup"><span data-stu-id="17505-135">Specify a value for the threshold.</span></span>  
  
 <span data-ttu-id="17505-136">**Configurare gli avvisi**</span><span class="sxs-lookup"><span data-stu-id="17505-136">**Configure Alerts**</span></span>  
 <span data-ttu-id="17505-137">Selezionare una riga nella griglia **Avvisi** e fare clic su **Configura avvisi** per aprire la finestra di dialogo **Configura avvisi di replica** .</span><span class="sxs-lookup"><span data-stu-id="17505-137">Select a row in the **Warnings** grid, and click **Configure Alerts** to launch the **Configure Replication Alerts** dialog box.</span></span> <span data-ttu-id="17505-138">Tramite questa finestra di dialogo è possibile definire un avviso associato al valore soglia e all'avviso selezionati.</span><span class="sxs-lookup"><span data-stu-id="17505-138">The dialog box allows you to define an alert, which is associated with the selected threshold and warning.</span></span>  
  
 <span data-ttu-id="17505-139">**Ignora modifiche**</span><span class="sxs-lookup"><span data-stu-id="17505-139">**Discard Changes**</span></span>  
 <span data-ttu-id="17505-140">Fare clic su questo pulsante per ignorare le eventuali modifiche apportate agli avvisi e alle soglie.</span><span class="sxs-lookup"><span data-stu-id="17505-140">Click to discard any changes to warnings and thresholds.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="17505-141"> La scelta del pulsante **Ignora modifiche** non influisce sugli avvisi definiti nella finestra di dialogo **Configura avvisi di replica** .</span><span class="sxs-lookup"><span data-stu-id="17505-141">Clicking **Discard Changes** does not affect alerts defined in the **Configure Replication Alerts** dialog box.</span></span>  
  
 <span data-ttu-id="17505-142">**Salva modifiche**</span><span class="sxs-lookup"><span data-stu-id="17505-142">**Save Changes**</span></span>  
 <span data-ttu-id="17505-143">Fare clic su questo pulsante per salvare le eventuali modifiche apportate agli avvisi e alle soglie.</span><span class="sxs-lookup"><span data-stu-id="17505-143">Click to save any changes to warnings and thresholds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17505-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="17505-144">See Also</span></span>  
 <span data-ttu-id="17505-145">[Avviare Monitoraggio replica](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="17505-145">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="17505-146">[Visualizzare le informazioni ed eseguire attività usando Monitoraggio replica](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="17505-146">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 <span data-ttu-id="17505-147">[Monitorare le prestazioni con monitoraggio replica](monitor/monitor-performance-with-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="17505-147">[Monitor Performance with Replication Monitor](monitor/monitor-performance-with-replication-monitor.md) </span></span>  
 <span data-ttu-id="17505-148">[Monitoraggio della replica](monitoring-replication.md) </span><span class="sxs-lookup"><span data-stu-id="17505-148">[Monitoring Replication](monitoring-replication.md) </span></span>  
 [<span data-ttu-id="17505-149">Impostare valori di soglia e avvisi in Monitoraggio replica</span><span class="sxs-lookup"><span data-stu-id="17505-149">Set Thresholds and Warnings in Replication Monitor</span></span>](monitor/set-thresholds-and-warnings-in-replication-monitor.md)  
  
  
