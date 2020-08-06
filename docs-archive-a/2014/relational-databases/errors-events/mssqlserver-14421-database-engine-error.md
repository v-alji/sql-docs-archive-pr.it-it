---
title: MSSQLSERVER_14421 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 14421 (Database Engine error)
ms.assetid: 03e76d4a-d463-4673-8843-08e4ecaefe27
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d6bc793911797c334d87238ec46531f7afbf63ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636166"
---
# <a name="mssqlserver_14421"></a><span data-ttu-id="99c1b-102">MSSQLSERVER_14421</span><span class="sxs-lookup"><span data-stu-id="99c1b-102">MSSQLSERVER_14421</span></span>
    
## <a name="details"></a><span data-ttu-id="99c1b-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="99c1b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="99c1b-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="99c1b-104">Product Name</span></span>|<span data-ttu-id="99c1b-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="99c1b-105">SQL Server</span></span>|  
|<span data-ttu-id="99c1b-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="99c1b-106">Event ID</span></span>|<span data-ttu-id="99c1b-107">14421</span><span class="sxs-lookup"><span data-stu-id="99c1b-107">14421</span></span>|  
|<span data-ttu-id="99c1b-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="99c1b-108">Event Source</span></span>|<span data-ttu-id="99c1b-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="99c1b-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="99c1b-110">Componente</span><span class="sxs-lookup"><span data-stu-id="99c1b-110">Component</span></span>|<span data-ttu-id="99c1b-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="99c1b-111">SQLEngine</span></span>|  
|<span data-ttu-id="99c1b-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="99c1b-112">Symbolic Name</span></span>|<span data-ttu-id="99c1b-113">SQLErrorNum14421</span><span class="sxs-lookup"><span data-stu-id="99c1b-113">SQLErrorNum14421</span></span>|  
|<span data-ttu-id="99c1b-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="99c1b-114">Message Text</span></span>|<span data-ttu-id="99c1b-115">Per il database secondario per il log shipping %s.%s è impostato un valore soglia per il ripristino di %d minuti e tale database non è sincronizzato. Non è stata eseguita alcuna operazione di ripristino per %d minuti.</span><span class="sxs-lookup"><span data-stu-id="99c1b-115">The log shipping secondary database %s.%s has restore threshold of %d minutes and is out of sync. No restore was performed for %d minutes.</span></span> <span data-ttu-id="99c1b-116">La latenza ripristinata è di %d minuti.</span><span class="sxs-lookup"><span data-stu-id="99c1b-116">Restored latency is %d minutes.</span></span> <span data-ttu-id="99c1b-117">Controllare le informazioni nel log dell'agente e del server di monitoraggio distribuzione log.</span><span class="sxs-lookup"><span data-stu-id="99c1b-117">Check agent log and logshipping monitor information.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="99c1b-118">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="99c1b-118">Explanation</span></span>  
 <span data-ttu-id="99c1b-119">Questo messaggio indica che il log shipping non è stato sincronizzato entro la soglia per il ripristino.</span><span class="sxs-lookup"><span data-stu-id="99c1b-119">This message indicates that log shipping is out of synchronization beyond the restore threshold.</span></span> <span data-ttu-id="99c1b-120">Per soglia si intende il numero di minuti che possono trascorrere tra operazioni di ripristino prima che venga generato un messaggio.</span><span class="sxs-lookup"><span data-stu-id="99c1b-120">The restore threshold is the number of minutes that can elapse between restore operations before a message is generated.</span></span>  
  
### <a name="possible-causes"></a><span data-ttu-id="99c1b-121">Possibili cause</span><span class="sxs-lookup"><span data-stu-id="99c1b-121">Possible Causes</span></span>  
 <span data-ttu-id="99c1b-122">Questo messaggio non indica necessariamente un problema relativo al log shipping,</span><span class="sxs-lookup"><span data-stu-id="99c1b-122">This message does not necessarily indicate a problem with log shipping.</span></span> <span data-ttu-id="99c1b-123">ma potrebbe indicare uno dei problemi seguenti:</span><span class="sxs-lookup"><span data-stu-id="99c1b-123">Instead, this message might indicate one of the following problems:</span></span>  
  
-   <span data-ttu-id="99c1b-124">Il processo di ripristino non è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="99c1b-124">The restore job is not running.</span></span>  
  
     <span data-ttu-id="99c1b-125">La mancata esecuzione del processo può dipendere da diverse cause. È ad esempio possibile che il servizio SQL Server Agent nell'istanza del server secondario non sia in esecuzione, che il processo sia disabilitato oppure che la pianificazione del processo sia stata modificata.</span><span class="sxs-lookup"><span data-stu-id="99c1b-125">Possible causes of the job not running include the following: the SQL Server Agent service on the secondary server instance is not running, the job is disabled, or the schedule of the job has been changed.</span></span>  
  
-   <span data-ttu-id="99c1b-126">Si è verificato un errore relativo al processo di ripristino.</span><span class="sxs-lookup"><span data-stu-id="99c1b-126">The restore job is failing.</span></span>  
  
     <span data-ttu-id="99c1b-127">L'errore relativo al processo può dipendere da diverse cause. È ad esempio possibile che il percorso della cartella di ripristino non sia valido, che il disco sia pieno o che vi siano altri motivi che causano errori nell'istruzione RESTORE.</span><span class="sxs-lookup"><span data-stu-id="99c1b-127">Possible causes of the job failing include the following: the restore folder path is not valid, the disk is full, or any other reason that the RESTORE statement could fail.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="99c1b-128">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="99c1b-128">User Action</span></span>  
 <span data-ttu-id="99c1b-129">Per risolvere il problema che ha causato la visualizzazione di questo messaggio:</span><span class="sxs-lookup"><span data-stu-id="99c1b-129">To troubleshoot this message:</span></span>  
  
-   <span data-ttu-id="99c1b-130">Verificare che il servizio SQL Server Agent sia in esecuzione per l'istanza del server secondario e che il processo di ripristino del database secondario sia abilitato e pianificato per l'esecuzione a intervalli appropriati.</span><span class="sxs-lookup"><span data-stu-id="99c1b-130">Make sure that the SQL Server Agent service is running for the secondary server instance and that the restore job for this secondary database is enabled and is scheduled to run at the appropriate frequency.</span></span>  
  
-   <span data-ttu-id="99c1b-131">È possibile che si sia verificato un errore relativo al processo di ripristino nel server secondario.</span><span class="sxs-lookup"><span data-stu-id="99c1b-131">The restore job on the secondary server might be failing.</span></span> <span data-ttu-id="99c1b-132">In questo caso, verificare la cronologia processo del processo di ripristino per individuarne la causa.</span><span class="sxs-lookup"><span data-stu-id="99c1b-132">In this case, check the job history for the restore job to look for the cause.</span></span>  
  
-   <span data-ttu-id="99c1b-133">È possibile che il processo di ripristino del log shipping, che viene eseguito nell'istanza del server secondario, non sia in grado di connettersi all'istanza del server di monitoraggio per aggiornare la tabella **log_shipping_monitor_secondary**.</span><span class="sxs-lookup"><span data-stu-id="99c1b-133">The log shipping restore job, which runs on the secondary server instance, might not be able to connect to the monitor server instance to update the **log_shipping_monitor_secondary** table.</span></span> <span data-ttu-id="99c1b-134">L'errore potrebbe essere causato da un problema di autenticazione tra l'istanza del server di monitoraggio e l'istanza del server secondario.</span><span class="sxs-lookup"><span data-stu-id="99c1b-134">This might be caused by an authentication problem between the monitor server instance and the secondary server instance.</span></span>  
  
-   <span data-ttu-id="99c1b-135">È possibile che la soglia di avviso per il backup non sia corretta.</span><span class="sxs-lookup"><span data-stu-id="99c1b-135">The backup alert threshold might have an incorrect value.</span></span> <span data-ttu-id="99c1b-136">In una situazione ideale, la soglia è impostata su un valore pari ad almeno tre volte la frequenza del processo di ripristino.</span><span class="sxs-lookup"><span data-stu-id="99c1b-136">Ideally, this value is set to at least three times the frequency of the restore job.</span></span> <span data-ttu-id="99c1b-137">Se si cambia la frequenza del processo di ripristino dopo aver configurato e reso operativo il log shipping, sarà necessario aggiornare di conseguenza la soglia di avviso per il backup.</span><span class="sxs-lookup"><span data-stu-id="99c1b-137">If you change the frequency of the restore job after log shipping is configured and functional, you must update the value of the backup alert threshold accordingly.</span></span>  
  
-   <span data-ttu-id="99c1b-138">Quando l'istanza del server di monitoraggio passa alla modalità offline e quindi torna alla modalità online, la tabella **log_shipping_monitor_secondary** non viene aggiornata con i valori correnti prima dell'esecuzione del processo del messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="99c1b-138">When the monitor server instance goes offline and then comes back online, the **log_shipping_monitor_secondary** table is not updated with the current values before the alert message job runs.</span></span> <span data-ttu-id="99c1b-139">È quindi possibile che durante un processo di ripristino venga generato l'errore 14421 "Impossibile trovare un file di backup del log applicabile al database secondario".</span><span class="sxs-lookup"><span data-stu-id="99c1b-139">Error 14421 can be raised when a restore job succeeds with, "Could not find a log backup file that could be applied to secondary database."</span></span> <span data-ttu-id="99c1b-140">In tale circostanza l'ora di ripristino non viene aggiornata.</span><span class="sxs-lookup"><span data-stu-id="99c1b-140">When this occurs, the restore time is not updated.</span></span> <span data-ttu-id="99c1b-141">In questo caso l'errore può dipendere da un problema relativo al processo di copia.</span><span class="sxs-lookup"><span data-stu-id="99c1b-141">The cause of the error in this case might be an issue with the copy job.</span></span>  
  
     <span data-ttu-id="99c1b-142">Per aggiornare le tabelle di monitoraggio con i dati più recenti del database secondario, eseguire **sp_refresh_log_shipping_monitor** nell'istanza del server secondario.</span><span class="sxs-lookup"><span data-stu-id="99c1b-142">To update the monitor tables with the latest data for the secondary database, run **sp_refresh_log_shipping_monitor** on the secondary server instance.</span></span>  
  
-   <span data-ttu-id="99c1b-143">Nell'istanza del server secondario o di monitoraggio la data o l'ora non è corretta.</span><span class="sxs-lookup"><span data-stu-id="99c1b-143">On the secondary or monitor server instance, the date or time is incorrect.</span></span> <span data-ttu-id="99c1b-144">Questo problema può causare la generazione di messaggi di avviso.</span><span class="sxs-lookup"><span data-stu-id="99c1b-144">This may also generate alert messages.</span></span> <span data-ttu-id="99c1b-145">È possibile che in uno dei due server sia stata modificata la data o l'ora di sistema.</span><span class="sxs-lookup"><span data-stu-id="99c1b-145">Possibly the system date or time was modified on the one of them.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="99c1b-146">Fusi orari diversi per le due istanze del server non dovrebbero invece costituire un problema.</span><span class="sxs-lookup"><span data-stu-id="99c1b-146">Different time zones for the two server instances should not cause a problem.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99c1b-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="99c1b-147">See Also</span></span>  
 <span data-ttu-id="99c1b-148">[log_shipping_monitor_secondary &#40;&#41;Transact-SQL](/sql/relational-databases/system-tables/log-shipping-monitor-secondary-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="99c1b-148">[log_shipping_monitor_secondary &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/log-shipping-monitor-secondary-transact-sql) </span></span>  
 <span data-ttu-id="99c1b-149">[Informazioni sul log shipping &#40;SQL Server&#41;](../../database-engine/log-shipping/about-log-shipping-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="99c1b-149">[About Log Shipping &#40;SQL Server&#41;](../../database-engine/log-shipping/about-log-shipping-sql-server.md) </span></span>  
 <span data-ttu-id="99c1b-150">[sp_help_log_shipping_monitor_secondary &#40;&#41;Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-help-log-shipping-monitor-secondary-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="99c1b-150">[sp_help_log_shipping_monitor_secondary &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-log-shipping-monitor-secondary-transact-sql) </span></span>  
 <span data-ttu-id="99c1b-151">[sp_refresh_log_shipping_monitor &#40;&#41;Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-refresh-log-shipping-monitor-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="99c1b-151">[sp_refresh_log_shipping_monitor &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-refresh-log-shipping-monitor-transact-sql) </span></span>  
 [<span data-ttu-id="99c1b-152">Informazioni sul log shipping &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="99c1b-152">About Log Shipping &#40;SQL Server&#41;</span></span>](../../database-engine/log-shipping/about-log-shipping-sql-server.md)  
  
  
