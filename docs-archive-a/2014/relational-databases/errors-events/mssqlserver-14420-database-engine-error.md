---
title: MSSQLSERVER_14420 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 14420 (Database Engine error)
ms.assetid: 4a1d72b1-ab1b-4119-a11b-a8a05c6fdb45
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 7a17ab1e2281530b06c9ad27ac2a31672de0681e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626802"
---
# <a name="mssqlserver_14420"></a><span data-ttu-id="1c27d-102">MSSQLSERVER_14420</span><span class="sxs-lookup"><span data-stu-id="1c27d-102">MSSQLSERVER_14420</span></span>
    
## <a name="details"></a><span data-ttu-id="1c27d-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="1c27d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1c27d-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="1c27d-104">Product Name</span></span>|<span data-ttu-id="1c27d-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="1c27d-105">SQL Server</span></span>|  
|<span data-ttu-id="1c27d-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="1c27d-106">Event ID</span></span>|<span data-ttu-id="1c27d-107">14420</span><span class="sxs-lookup"><span data-stu-id="1c27d-107">14420</span></span>|  
|<span data-ttu-id="1c27d-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="1c27d-108">Event Source</span></span>|<span data-ttu-id="1c27d-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="1c27d-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="1c27d-110">Componente</span><span class="sxs-lookup"><span data-stu-id="1c27d-110">Component</span></span>|<span data-ttu-id="1c27d-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="1c27d-111">SQLEngine</span></span>|  
|<span data-ttu-id="1c27d-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="1c27d-112">Symbolic Name</span></span>|<span data-ttu-id="1c27d-113">SQLErrorNum14420</span><span class="sxs-lookup"><span data-stu-id="1c27d-113">SQLErrorNum14420</span></span>|  
|<span data-ttu-id="1c27d-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="1c27d-114">Message Text</span></span>|<span data-ttu-id="1c27d-115">Per il database primario per il log shipping %s.%s è impostato un valore soglia per il backup di %d minuti e tale database non ha eseguito un'operazione di backup del log da %d minuti.</span><span class="sxs-lookup"><span data-stu-id="1c27d-115">The log shipping primary database %s.%s has backup threshold of %d minutes and has not performed a backup log operation for %d minutes.</span></span> <span data-ttu-id="1c27d-116">Controllare le informazioni nel log dell'agente e del server di monitoraggio distribuzione log.</span><span class="sxs-lookup"><span data-stu-id="1c27d-116">Check agent log and logshipping monitor information.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="1c27d-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="1c27d-117">Explanation</span></span>  
 <span data-ttu-id="1c27d-118">Il log shipping non è stato sincronizzato entro la soglia per il backup.</span><span class="sxs-lookup"><span data-stu-id="1c27d-118">Log shipping is out of synchronization beyond the backup threshold.</span></span> <span data-ttu-id="1c27d-119">La soglia per il backup corrisponde al numero di minuti consentiti tra processi di backup della distribuzione dei log prima che venga generato un avviso.</span><span class="sxs-lookup"><span data-stu-id="1c27d-119">The backup threshold is the number of minutes that are allowed to elapse between log-shipping backup jobs before an alert is generated.</span></span> <span data-ttu-id="1c27d-120">Questo messaggio non indica necessariamente un problema relativo al log shipping,</span><span class="sxs-lookup"><span data-stu-id="1c27d-120">This message does not necessarily indicate a problem with log shipping.</span></span> <span data-ttu-id="1c27d-121">ma potrebbe indicare uno dei problemi seguenti:</span><span class="sxs-lookup"><span data-stu-id="1c27d-121">Instead, this message might indicate one of the following problems:</span></span>  
  
-   <span data-ttu-id="1c27d-122">Il processo di backup non è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="1c27d-122">The backup job is not running.</span></span> <span data-ttu-id="1c27d-123">La mancata esecuzione del processo può dipendere da diverse cause. È ad esempio possibile che il servizio SQL Server Agent nell'istanza del server primario non sia in esecuzione, che il processo sia disabilitato oppure che la pianificazione del processo sia stata modificata.</span><span class="sxs-lookup"><span data-stu-id="1c27d-123">Possible causes for this include the following: the SQL Server Agent service on the primary server instance is not running, the job is disabled, or the job's schedule has been changed.</span></span>  
  
-   <span data-ttu-id="1c27d-124">Si è verificato un errore relativo al processo di backup.</span><span class="sxs-lookup"><span data-stu-id="1c27d-124">The backup job is failing.</span></span> <span data-ttu-id="1c27d-125">L'errore relativo al processo può dipendere da diverse cause. È ad esempio possibile che il percorso della cartella di backup non sia valido, che il disco sia pieno o che vi siano altri motivi che causano errori nell'istruzione BACKUP.</span><span class="sxs-lookup"><span data-stu-id="1c27d-125">Possible causes for this include the following: the backup folder path is not valid, the disk is full, or any other reason that the BACKUP statement could fail.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1c27d-126">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="1c27d-126">User Action</span></span>  
 <span data-ttu-id="1c27d-127">Per risolvere il problema che ha causato la visualizzazione di questo messaggio:</span><span class="sxs-lookup"><span data-stu-id="1c27d-127">To troubleshoot this message:</span></span>  
  
-   <span data-ttu-id="1c27d-128">Verificare che il servizio SQL Server Agent sia in esecuzione per l'istanza del server primario e che il processo di backup del database primario sia abilitato e pianificato per l'esecuzione a intervalli appropriati.</span><span class="sxs-lookup"><span data-stu-id="1c27d-128">Make sure that the SQL Server Agent service is running for the primary server instance and that the backup job for this primary database is enabled and is scheduled to run at the appropriate frequency.</span></span>  
  
-   <span data-ttu-id="1c27d-129">È possibile che si sia verificato un errore relativo al processo di backup nel server primario.</span><span class="sxs-lookup"><span data-stu-id="1c27d-129">The backup job on the primary server might be failing.</span></span> <span data-ttu-id="1c27d-130">In questo caso, esaminare la cronologia processo del processo di backup per individuarne la causa.</span><span class="sxs-lookup"><span data-stu-id="1c27d-130">In this case, examine the job history for the backup job to look for the cause.</span></span>  
  
-   <span data-ttu-id="1c27d-131">È possibile che il processo di backup del log shipping, che viene eseguito nell'istanza del server primario, non sia in grado di connettersi all'istanza del server di monitoraggio per aggiornare la tabella **log_shipping_monitor_primary**.</span><span class="sxs-lookup"><span data-stu-id="1c27d-131">The log shipping backup job, which runs on the primary server instance, might not be able to connect to the monitor server instance to update the **log_shipping_monitor_primary** table.</span></span> <span data-ttu-id="1c27d-132">L'errore potrebbe essere causato da un problema di autenticazione tra l'istanza del server di monitoraggio e l'istanza del server primario.</span><span class="sxs-lookup"><span data-stu-id="1c27d-132">This could be caused by an authentication problem between the monitor server instance and the primary server instance.</span></span>  
  
-   <span data-ttu-id="1c27d-133">È possibile che la soglia di avviso per il backup non sia corretta.</span><span class="sxs-lookup"><span data-stu-id="1c27d-133">The backup alert threshold might have an incorrect value.</span></span> <span data-ttu-id="1c27d-134">In una situazione ideale, la soglia è impostata su un valore pari ad almeno tre volte la frequenza del processo di backup.</span><span class="sxs-lookup"><span data-stu-id="1c27d-134">Ideally, this value is set to at least three times the frequency of the backup job.</span></span> <span data-ttu-id="1c27d-135">Se si cambia la frequenza del processo di backup dopo aver configurato e reso operativo il log shipping, sarà necessario aggiornare di conseguenza la soglia di avviso per il backup.</span><span class="sxs-lookup"><span data-stu-id="1c27d-135">If you change the frequency of the backup job after log shipping is configured and functional, you must update the value of the backup alert threshold accordingly.</span></span>  
  
-   <span data-ttu-id="1c27d-136">Quando l'istanza del server di monitoraggio passa alla modalità offline e quindi torna alla modalità online, la tabella **log_shipping_monitor_primary** non viene aggiornata con i valori correnti prima dell'esecuzione del processo del messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="1c27d-136">When the monitor server instance goes offline and then comes back online, the **log_shipping_monitor_primary** table is not updated with the current values before the alert message job runs.</span></span> <span data-ttu-id="1c27d-137">Per aggiornare le tabelle di monitoraggio con i dati più recenti del database primario, eseguire **sp_refresh_log_shipping_monitor** nell'istanza del server primario.</span><span class="sxs-lookup"><span data-stu-id="1c27d-137">To update the monitor tables with the latest data for the primary database, run **sp_refresh_log_shipping_monitor** on the primary server instance.</span></span>  
  
-   <span data-ttu-id="1c27d-138">Nell'istanza del server primario o di monitoraggio la data o l'ora non è corretta.</span><span class="sxs-lookup"><span data-stu-id="1c27d-138">On the primary or monitor server instance, the date or time is incorrect.</span></span> <span data-ttu-id="1c27d-139">Questo problema può causare la generazione di messaggi di avviso.</span><span class="sxs-lookup"><span data-stu-id="1c27d-139">This may also generate alert messages.</span></span> <span data-ttu-id="1c27d-140">È possibile che in uno dei due server sia stata modificata la data o l'ora di sistema.</span><span class="sxs-lookup"><span data-stu-id="1c27d-140">Possibly the system date or time was modified on the one of them.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1c27d-141">Fusi orari diversi per le due istanze del server non dovrebbero invece costituire un problema.</span><span class="sxs-lookup"><span data-stu-id="1c27d-141">Different time zones for the two server instances should not cause a problem.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c27d-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1c27d-142">See Also</span></span>  
 <span data-ttu-id="1c27d-143">[log_shipping_monitor_primary &#40;&#41;Transact-SQL](/sql/relational-databases/system-tables/log-shipping-monitor-primary-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1c27d-143">[log_shipping_monitor_primary &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/log-shipping-monitor-primary-transact-sql) </span></span>  
 <span data-ttu-id="1c27d-144">[Informazioni sul log shipping &#40;SQL Server&#41;](../../database-engine/log-shipping/about-log-shipping-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="1c27d-144">[About Log Shipping &#40;SQL Server&#41;](../../database-engine/log-shipping/about-log-shipping-sql-server.md) </span></span>  
 <span data-ttu-id="1c27d-145">[sp_help_log_shipping_monitor_primary &#40;&#41;Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-help-log-shipping-monitor-primary-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1c27d-145">[sp_help_log_shipping_monitor_primary &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-log-shipping-monitor-primary-transact-sql) </span></span>  
 <span data-ttu-id="1c27d-146">[sp_refresh_log_shipping_monitor &#40;&#41;Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-refresh-log-shipping-monitor-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1c27d-146">[sp_refresh_log_shipping_monitor &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-refresh-log-shipping-monitor-transact-sql) </span></span>  
 [<span data-ttu-id="1c27d-147">Informazioni sul log shipping &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="1c27d-147">About Log Shipping &#40;SQL Server&#41;</span></span>](../../database-engine/log-shipping/about-log-shipping-sql-server.md)  
  
  
