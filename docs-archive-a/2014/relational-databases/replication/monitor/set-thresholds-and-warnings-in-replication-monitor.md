---
title: Impostare valori di soglia e avvisi in Monitoraggio replica | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- alerts [SQL Server replication]
- Merge Agent, thresholds and warnings
- Distribution Agent, thresholds and warnings
- thresholds [SQL Server replication]
- Replication Monitor, thresholds and warnings
- monitoring performance [SQL Server replication], thresholds and warnings
ms.assetid: 3a409c2c-b77e-4001-b81a-1dcd918618ec
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f34878a6398df34e55e6dd3783f2da736bee0959
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725508"
---
# <a name="set-thresholds-and-warnings-in-replication-monitor"></a><span data-ttu-id="d2d49-102">Impostazione di valore soglia e avvisi in Monitoraggio replica</span><span class="sxs-lookup"><span data-stu-id="d2d49-102">Set Thresholds and Warnings in Replication Monitor</span></span>
  [!INCLUDE[msCoName](../../../includes/msconame-md.md)]<span data-ttu-id="d2d49-103">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]In Monitoraggio replica vengono visualizzate informazioni sullo stato delle pubblicazioni e delle sottoscrizioni.</span><span class="sxs-lookup"><span data-stu-id="d2d49-103">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Replication Monitor displays status information for publications and subscriptions.</span></span> <span data-ttu-id="d2d49-104">Per impostazione predefinita, in Monitoraggio replica vengono visualizzati avvisi solo per le sottoscrizioni non inizializzate, ma è possibile abilitarli anche per altre condizioni.</span><span class="sxs-lookup"><span data-stu-id="d2d49-104">By default, Replication Monitor displays warnings only for uninitialized subscriptions, but you can enable warnings for other conditions.</span></span> <span data-ttu-id="d2d49-105">È consigliabile abilitare gli avvisi per la topologia, in modo da poter essere informati tempestivamente sullo stato e sulle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="d2d49-105">It is recommended that you enable warnings for your topology, so that you are informed about status and performance in a timely manner.</span></span>  
  
 <span data-ttu-id="d2d49-106">Quando si attiva un avviso, si specifica una soglia.</span><span class="sxs-lookup"><span data-stu-id="d2d49-106">When you enable a warning, you specify a threshold.</span></span> <span data-ttu-id="d2d49-107">Quando tale soglia viene soddisfatta o superata, viene visualizzato un avviso, a meno che non sia necessario visualizzare un problema con una priorità più elevata.</span><span class="sxs-lookup"><span data-stu-id="d2d49-107">When that threshold is met or exceeded, a warning is displayed (unless an issue with a higher priority needs to be displayed).</span></span> <span data-ttu-id="d2d49-108">Oltre a visualizzare un avviso in Monitoraggio replica, il raggiungimento di un valore soglia può inoltre attivare un messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="d2d49-108">In addition to displaying a warning in Replication Monitor, reaching a threshold can also trigger an alert.</span></span> <span data-ttu-id="d2d49-109">È possibile abilitare avvisi per le seguenti condizioni:</span><span class="sxs-lookup"><span data-stu-id="d2d49-109">You can enable warnings for the following conditions:</span></span>  
  
-   <span data-ttu-id="d2d49-110">Imminente scadenza della sottoscrizione</span><span class="sxs-lookup"><span data-stu-id="d2d49-110">Imminent subscription expiration</span></span>  
  
     <span data-ttu-id="d2d49-111">Applicabile a tutti i tipi di replica.</span><span class="sxs-lookup"><span data-stu-id="d2d49-111">This applies to all types of replication.</span></span> <span data-ttu-id="d2d49-112">Se il valore soglia specificato viene raggiunto o superato, lo stato della sottoscrizione diventa **Scadenza imminente/Scaduta**.</span><span class="sxs-lookup"><span data-stu-id="d2d49-112">If the specified threshold is met or exceeded, the subscription status is displayed as **Expiring soon/Expired**.</span></span>  
  
-   <span data-ttu-id="d2d49-113">Superamento della latenza specificata (quantità di tempo trascorso tra l'esecuzione del commit di una transazione nel server di pubblicazione e l'esecuzione del commit della transazione corrispondente nel Sottoscrittore).</span><span class="sxs-lookup"><span data-stu-id="d2d49-113">Exceeding the specified latency (the amount of time that elapses between a transaction being committed at the Publisher and the corresponding transaction being committed at the Subscriber).</span></span>  
  
     <span data-ttu-id="d2d49-114">Si applica alla replica transazionale.</span><span class="sxs-lookup"><span data-stu-id="d2d49-114">This applies to transactional replication.</span></span> <span data-ttu-id="d2d49-115">Se la soglia specificata viene raggiunta o superata, lo stato della sottoscrizione diventa **Prestazioni critiche**.</span><span class="sxs-lookup"><span data-stu-id="d2d49-115">If the specified threshold is met or exceeded, the subscription status is displayed as **Performance critical**.</span></span>  
  
-   <span data-ttu-id="d2d49-116">Superamento del tempo di sincronizzazione specificato.</span><span class="sxs-lookup"><span data-stu-id="d2d49-116">Exceeding the specified synchronization time.</span></span>  
  
     <span data-ttu-id="d2d49-117">Si applica alla replica di tipo merge.</span><span class="sxs-lookup"><span data-stu-id="d2d49-117">This applies to merge replication.</span></span> <span data-ttu-id="d2d49-118">Se la soglia specificata viene raggiunta o superata, viene visualizzato lo stato **Merge con esecuzione prolungata**.</span><span class="sxs-lookup"><span data-stu-id="d2d49-118">If the specified threshold is met or exceeded, the status is displayed as **Long-running merge**.</span></span> <span data-ttu-id="d2d49-119">È possibile specificare valore soglia differenti per le connessioni remote e le connessioni LAN.</span><span class="sxs-lookup"><span data-stu-id="d2d49-119">You can specify different thresholds for dialup and Local Area Network (LAN) connections.</span></span>  
  
-   <span data-ttu-id="d2d49-120">Impossibilità di elaborare il numero di righe specificato in un determinato intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="d2d49-120">Falling short of processing the specified number of rows in a given amount of time.</span></span>  
  
     <span data-ttu-id="d2d49-121">Si applica alla replica di tipo merge.</span><span class="sxs-lookup"><span data-stu-id="d2d49-121">This applies to merge replication.</span></span> <span data-ttu-id="d2d49-122">Se la soglia specificata viene raggiunta o superata, viene visualizzato lo stato **Prestazioni critiche**.</span><span class="sxs-lookup"><span data-stu-id="d2d49-122">If the specified threshold is met or exceeded, the status is displayed as **Performance critical**.</span></span> <span data-ttu-id="d2d49-123">È possibile specificare valore soglia differenti per le connessioni remote e le connessioni LAN.</span><span class="sxs-lookup"><span data-stu-id="d2d49-123">You can specify different thresholds for dialup and LAN connections.</span></span>  
  
 <span data-ttu-id="d2d49-124">Per altre informazioni sugli avvisi **Prestazioni critiche** e **Merge con esecuzione prolungata**, vedere [Monitoraggio delle prestazioni con Monitoraggio replica](monitor-performance-with-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="d2d49-124">For more information on the warnings **Performance critical** and **Long-running merge**, see [Monitor Performance with Replication Monitor](monitor-performance-with-replication-monitor.md).</span></span>  
  
 <span data-ttu-id="d2d49-125">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="d2d49-125">**In This Topic**</span></span>  
  
-   [<span data-ttu-id="d2d49-126">Impostare soglie e avvisi per una pubblicazione transazionale</span><span class="sxs-lookup"><span data-stu-id="d2d49-126">Set thresholds and warnings for a transactional publication</span></span>](#Transactional)  
  
-   [<span data-ttu-id="d2d49-127">Impostare valore soglia e avvisi per una pubblicazione di tipo merge</span><span class="sxs-lookup"><span data-stu-id="d2d49-127">Set thresholds and warnings for a merge publication</span></span>](#Merge)  
  
-   [<span data-ttu-id="d2d49-128">Impostare soglie e avvisi per una pubblicazione snapshot</span><span class="sxs-lookup"><span data-stu-id="d2d49-128">Set thresholds and warnings for a snapshot publication</span></span>](#Snapshot)  
  
##  <a name="to-set-thresholds-and-warnings-for-a-transactional-publication"></a><a name="Transactional"></a><span data-ttu-id="d2d49-129">Per impostare soglie e avvisi per una pubblicazione transazionale</span><span class="sxs-lookup"><span data-stu-id="d2d49-129">To set thresholds and warnings for a transactional publication</span></span>  
  
1.  <span data-ttu-id="d2d49-130">Espandere un gruppo di server di pubblicazione nel riquadro sinistro, espandere un server di pubblicazione e quindi fare clic su una pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="d2d49-130">Expand a Publisher group in the left pane, expand a Publisher, and then click a publication.</span></span>  
  
2.  <span data-ttu-id="d2d49-131">Fare clic sulla scheda **avvisi** . Per visualizzare ulteriori informazioni sulle opzioni disponibili in questa scheda, **fare clic su** ? sulla barra dei menu.</span><span class="sxs-lookup"><span data-stu-id="d2d49-131">Click the **Warnings** tab. To view more information about the options on this tab click **Help** on the menu bar.</span></span>  
  
3.  <span data-ttu-id="d2d49-132">Abilitare un avviso selezionando la casella di controllo appropriata tra **Avvisa se una sottoscrizione scade entro il valore soglia** e **Avvisa se la latenza supera il valore soglia**.</span><span class="sxs-lookup"><span data-stu-id="d2d49-132">Enable a warning by selecting the appropriate check box: **Warn if a subscription will expire within the threshold** or **Warn if latency exceeds the threshold**.</span></span>  
  
4.  <span data-ttu-id="d2d49-133">Impostare una soglia per gli avvisi nella colonna **Soglia** .</span><span class="sxs-lookup"><span data-stu-id="d2d49-133">Set a threshold for the warnings in the **Threshold** column.</span></span> <span data-ttu-id="d2d49-134">Se, ad esempio, nel passaggio 3 è stata selezionata la casella di controllo **Avvisa se la latenza supera il valore soglia** , è possibile impostare una latenza di **60 secondi** nella colonna **Soglia** .</span><span class="sxs-lookup"><span data-stu-id="d2d49-134">For example, if you selected **Warn if latency exceeds the threshold** in step 3, you could select a latency of **60 seconds** in the **Threshold** column.</span></span>  
  
5.  <span data-ttu-id="d2d49-135">Fare clic su **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="d2d49-135">Click **Save Changes**.</span></span>  
  
#### <a name="to-configure-an-alert-for-a-threshold"></a><span data-ttu-id="d2d49-136">Per configurare un avviso per una soglia</span><span class="sxs-lookup"><span data-stu-id="d2d49-136">To configure an alert for a threshold</span></span>  
  
1.  <span data-ttu-id="d2d49-137">Fare clic su **Configura avvisi**.</span><span class="sxs-lookup"><span data-stu-id="d2d49-137">Click **Configure Alerts**.</span></span>  
  
2.  <span data-ttu-id="d2d49-138">Nella finestra di dialogo **Configura avvisi di replica** selezionare un avviso e quindi fare clic su **Configura**.</span><span class="sxs-lookup"><span data-stu-id="d2d49-138">In the **Configure Replication Alerts** dialog box, select an alert, and then click **Configure**.</span></span>  
  
     <span data-ttu-id="d2d49-139">In questa finestra di dialogo vengono visualizzati gli avvisi per tutti i tipi di pubblicazione, inclusi quelli che non sono relativi al monitoraggio delle soglie.</span><span class="sxs-lookup"><span data-stu-id="d2d49-139">This dialog box displays alerts for all publication types, including alerts that are not related to monitoring thresholds.</span></span> <span data-ttu-id="d2d49-140">Per altre informazioni, vedere [Usare gli avvisi per gli eventi degli agenti di replica](../agents/use-alerts-for-replication-agent-events.md).</span><span class="sxs-lookup"><span data-stu-id="d2d49-140">For more information, see [Use Alerts for Replication Agent Events](../agents/use-alerts-for-replication-agent-events.md).</span></span>  
  
3.  <span data-ttu-id="d2d49-141">Impostare le opzioni nella finestra di dialogo **Proprietà dell'avviso \<AlertName>** :</span><span class="sxs-lookup"><span data-stu-id="d2d49-141">Set options in the **\<AlertName> alert properties** dialog box:</span></span>  
  
    -   <span data-ttu-id="d2d49-142">Nella pagina **Generale** fare clic su **Abilita**e specificare il database a cui si desidera applicare l'avviso.</span><span class="sxs-lookup"><span data-stu-id="d2d49-142">On the **General** page, click **Enable**; specify which database the alert should apply to.</span></span>  
  
    -   <span data-ttu-id="d2d49-143">Nella pagina **Risposta** specificare se si desidera inviare un messaggio di posta elettronica e/o eseguire un processo.</span><span class="sxs-lookup"><span data-stu-id="d2d49-143">On the **Response** page, specify whether an e-mail should be sent and/or a job should be executed.</span></span>  
  
    -   <span data-ttu-id="d2d49-144">Nella pagina **Opzioni** personalizzare il testo della risposta.</span><span class="sxs-lookup"><span data-stu-id="d2d49-144">On the **Options** page, customize the text of the response.</span></span>  
  
4.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
5.  <span data-ttu-id="d2d49-145">Fare clic su **Close**.</span><span class="sxs-lookup"><span data-stu-id="d2d49-145">Click **Close**.</span></span>  
  
##  <a name="set-thresholds-and-warnings-for-a-merge-publication"></a><a name="Merge"></a><span data-ttu-id="d2d49-146">Impostare soglie e avvisi per una pubblicazione di tipo merge</span><span class="sxs-lookup"><span data-stu-id="d2d49-146">Set thresholds and warnings for a merge publication</span></span>  
  
1.  <span data-ttu-id="d2d49-147">Espandere un gruppo di server di pubblicazione nel riquadro sinistro, espandere un server di pubblicazione e quindi fare clic su una pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="d2d49-147">Expand a Publisher group in the left pane, expand a Publisher, and then click a publication.</span></span>  
  
2.  <span data-ttu-id="d2d49-148">Fare clic sulla scheda **avvisi** . Per visualizzare ulteriori informazioni sulle opzioni **disponibili in questa scheda, fare clic** su? sulla barra dei menu.</span><span class="sxs-lookup"><span data-stu-id="d2d49-148">Click the **Warnings** tab. To view more information about the options on this tab, click **Help** on the menu bar.</span></span>  
  
3.  <span data-ttu-id="d2d49-149">Abilitare un avviso selezionando la casella di controllo appropriata tra</span><span class="sxs-lookup"><span data-stu-id="d2d49-149">Enable a warning by selecting the appropriate check box:</span></span>  
  
    -   <span data-ttu-id="d2d49-150">**Avvisa se una sottoscrizione scade entro il valore soglia**</span><span class="sxs-lookup"><span data-stu-id="d2d49-150">**Warn if a subscription will expire within the threshold**</span></span>  
  
    -   <span data-ttu-id="d2d49-151">**Avvisa se la durata del processo di merge per le connessioni remote supera il valore soglia**</span><span class="sxs-lookup"><span data-stu-id="d2d49-151">**Warn if a merge length for dialup connections exceeds the threshold**</span></span>  
  
    -   <span data-ttu-id="d2d49-152">**Avvisa se la durata del processo di merge per le connessioni LAN supera il valore soglia**</span><span class="sxs-lookup"><span data-stu-id="d2d49-152">**Warn if a merge length for LAN connections exceeds the threshold**</span></span>  
  
    -   <span data-ttu-id="d2d49-153">**Avvisa se il numero di righe al secondo di cui è stato eseguito il merge per le connessioni LAN è minore del valore soglia**</span><span class="sxs-lookup"><span data-stu-id="d2d49-153">**Warn if rows merged per second for LAN connections is less than the threshold**</span></span>  
  
    -   <span data-ttu-id="d2d49-154">**Avvisa se il numero di righe al secondo di cui è stato eseguito il merge per le connessioni remote è minore del valore soglia**</span><span class="sxs-lookup"><span data-stu-id="d2d49-154">**Warn if rows merged per second for dialup connections is less than the threshold**</span></span>  
  
4.  <span data-ttu-id="d2d49-155">Impostare i valore soglia per gli avvisi nella colonna **Soglia** .</span><span class="sxs-lookup"><span data-stu-id="d2d49-155">Set thresholds for the warnings in the **Threshold** column.</span></span> <span data-ttu-id="d2d49-156">Ad esempio, se si seleziona **Avvisa se la durata del processo di merge per le connessioni remote supera il valore soglia** nel passaggio 3, è possibile selezionare un periodo di **10 minuti** nella colonna **Soglia** .</span><span class="sxs-lookup"><span data-stu-id="d2d49-156">For example, if you selected **Warn if a merge length for dialup connections exceeds the threshold** in step 3, you could select a time of **10 minutes** in the **Threshold** column.</span></span>  
  
5.  <span data-ttu-id="d2d49-157">Fare clic su **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="d2d49-157">Click **Save Changes**.</span></span>  
  
#### <a name="to-configure-an-alert-for-a-threshold"></a><span data-ttu-id="d2d49-158">Per configurare un avviso per una soglia</span><span class="sxs-lookup"><span data-stu-id="d2d49-158">To configure an alert for a threshold</span></span>  
  
1.  <span data-ttu-id="d2d49-159">Fare clic su **Configura avvisi**.</span><span class="sxs-lookup"><span data-stu-id="d2d49-159">Click **Configure Alerts**.</span></span>  
  
2.  <span data-ttu-id="d2d49-160">Nella finestra di dialogo **Configura avvisi di replica** selezionare un avviso e quindi fare clic su **Configura**.</span><span class="sxs-lookup"><span data-stu-id="d2d49-160">In the **Configure Replication Alerts** dialog box, select an alert, and then click **Configure**.</span></span>  
  
     <span data-ttu-id="d2d49-161">In questa finestra di dialogo vengono visualizzati gli avvisi per tutti i tipi di pubblicazione, inclusi quelli che non sono relativi al monitoraggio delle soglie.</span><span class="sxs-lookup"><span data-stu-id="d2d49-161">This dialog box displays alerts for all publication types, including alerts that are not related to monitoring thresholds.</span></span>  
  
3.  <span data-ttu-id="d2d49-162">Impostare le opzioni nella finestra di dialogo **Proprietà dell'avviso \<AlertName>** :</span><span class="sxs-lookup"><span data-stu-id="d2d49-162">Set options in the **\<AlertName> alert properties** dialog box:</span></span>  
  
    -   <span data-ttu-id="d2d49-163">Nella pagina **Generale** fare clic su **Abilita**e specificare il database a cui si desidera applicare l'avviso.</span><span class="sxs-lookup"><span data-stu-id="d2d49-163">On the **General** page, click **Enable**; specify which database the alert should apply to.</span></span>  
  
    -   <span data-ttu-id="d2d49-164">Nella pagina **Risposta** specificare se si desidera inviare un messaggio di posta elettronica e/o eseguire un processo.</span><span class="sxs-lookup"><span data-stu-id="d2d49-164">On the **Response** page, specify whether an e-mail should be sent and/or a job should be executed.</span></span>  
  
    -   <span data-ttu-id="d2d49-165">Nella pagina **Opzioni** personalizzare il testo della risposta.</span><span class="sxs-lookup"><span data-stu-id="d2d49-165">On the **Options** page, customize the text of the response.</span></span>  
  
4.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
5.  <span data-ttu-id="d2d49-166">Fare clic su **Close**.</span><span class="sxs-lookup"><span data-stu-id="d2d49-166">Click **Close**.</span></span>  
  
##  <a name="set-thresholds-and-warnings-for-a-snapshot-publication"></a><a name="Snapshot"></a> <span data-ttu-id="d2d49-167">Impostare valore soglia e avvisi per una pubblicazione di snapshot</span><span class="sxs-lookup"><span data-stu-id="d2d49-167">Set thresholds and warnings for a snapshot publication</span></span>  
  
1.  <span data-ttu-id="d2d49-168">Espandere un gruppo di server di pubblicazione nel riquadro sinistro, espandere un server di pubblicazione e quindi fare clic su una pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="d2d49-168">Expand a Publisher group in the left pane, expand a Publisher, and then click a publication.</span></span>  
  
2.  <span data-ttu-id="d2d49-169">Fare clic sulla scheda **avvisi** . Per visualizzare ulteriori informazioni sulle opzioni disponibili in questa scheda, **fare clic su** ? nel menu in alto.</span><span class="sxs-lookup"><span data-stu-id="d2d49-169">Click the **Warnings** tab. To view more information about the options on this tab click **Help** on the top menu.</span></span>  
  
3.  <span data-ttu-id="d2d49-170">Abilitare un avviso selezionando la casella di controllo **Avvisa se una sottoscrizione scade entro il valore soglia**.</span><span class="sxs-lookup"><span data-stu-id="d2d49-170">Enable a warning by selecting the check box **Warn if a subscription will expire within the threshold**.</span></span>  
  
4.  <span data-ttu-id="d2d49-171">Impostare una soglia per l'avviso nella colonna **Soglia** .</span><span class="sxs-lookup"><span data-stu-id="d2d49-171">Set a threshold for the warning in the **Threshold** column.</span></span> <span data-ttu-id="d2d49-172">È ad esempio possibile selezionare un valore di **70%** nella colonna **Soglia** .</span><span class="sxs-lookup"><span data-stu-id="d2d49-172">For example, you could select a value of **70%** in the **Threshold** column.</span></span>  
  
5.  <span data-ttu-id="d2d49-173">Fare clic su **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="d2d49-173">Click **Save Changes**.</span></span>  
  
#### <a name="to-configure-an-alert-for-a-threshold"></a><span data-ttu-id="d2d49-174">Per configurare un avviso per una soglia</span><span class="sxs-lookup"><span data-stu-id="d2d49-174">To configure an alert for a threshold</span></span>  
  
1.  <span data-ttu-id="d2d49-175">Fare clic su **Configura avvisi**.</span><span class="sxs-lookup"><span data-stu-id="d2d49-175">Click **Configure Alerts**.</span></span>  
  
2.  <span data-ttu-id="d2d49-176">Nella finestra di dialogo **Configura avvisi di replica** selezionare un avviso e quindi fare clic su **Configura**.</span><span class="sxs-lookup"><span data-stu-id="d2d49-176">In the **Configure Replication Alerts** dialog box, select an alert, and then click **Configure**.</span></span>  
  
     <span data-ttu-id="d2d49-177">In questa finestra di dialogo vengono visualizzati gli avvisi per tutti i tipi di pubblicazione, inclusi quelli che non sono relativi al monitoraggio delle soglie.</span><span class="sxs-lookup"><span data-stu-id="d2d49-177">This dialog box displays alerts for all publication types, including alerts that are not related to monitoring thresholds.</span></span> <span data-ttu-id="d2d49-178">Per altre informazioni, vedere [Usare gli avvisi per gli eventi degli agenti di replica](../agents/use-alerts-for-replication-agent-events.md).</span><span class="sxs-lookup"><span data-stu-id="d2d49-178">For more information, see [Use Alerts for Replication Agent Events](../agents/use-alerts-for-replication-agent-events.md).</span></span>  
  
3.  <span data-ttu-id="d2d49-179">Impostare le opzioni nella finestra di dialogo **Proprietà dell'avviso \<AlertName>** :</span><span class="sxs-lookup"><span data-stu-id="d2d49-179">Set options in the **\<AlertName> alert properties** dialog box:</span></span>  
  
    -   <span data-ttu-id="d2d49-180">Nella pagina **Generale** fare clic su **Abilita**e specificare il database a cui si desidera applicare l'avviso.</span><span class="sxs-lookup"><span data-stu-id="d2d49-180">On the **General** page, click **Enable**; specify which database the alert should apply to.</span></span>  
  
    -   <span data-ttu-id="d2d49-181">Nella pagina **Risposta** specificare se si desidera inviare un messaggio di posta elettronica e/o eseguire un processo.</span><span class="sxs-lookup"><span data-stu-id="d2d49-181">On the **Response** page, specify whether an e-mail should be sent and/or a job should be executed.</span></span>  
  
    -   <span data-ttu-id="d2d49-182">Nella pagina **Opzioni** personalizzare il testo della risposta.</span><span class="sxs-lookup"><span data-stu-id="d2d49-182">On the **Options** page, customize the text of the response.</span></span>  
  
4.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
5.  <span data-ttu-id="d2d49-183">Fare clic su **Close**.</span><span class="sxs-lookup"><span data-stu-id="d2d49-183">Click **Close**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2d49-184">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d2d49-184">See Also</span></span>  
 [<span data-ttu-id="d2d49-185">Monitoraggio della replica</span><span class="sxs-lookup"><span data-stu-id="d2d49-185">Monitoring Replication</span></span>](../monitoring-replication.md)  
  
  
