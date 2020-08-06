---
title: Monitorare SQL Server backup gestito in Azure | Microsoft Docs
description: Questo articolo descrive gli strumenti che è possibile usare per determinare l'integrità complessiva dei backup usando SQL Server backup gestito in Azure e identificare gli errori.
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
ms.assetid: cfb9e431-7d4c-457c-b090-6f2528b2f315
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: baec99e63c70befde0cfce76e42dd6202ebc0bad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636880"
---
# <a name="monitor-sql-server-managed-backup-to-azure"></a><span data-ttu-id="2bd6e-103">Monitorare il backup gestito di SQL Server in Azure</span><span class="sxs-lookup"><span data-stu-id="2bd6e-103">Monitor SQL Server Managed Backup to Azure</span></span>
  [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] <span data-ttu-id="2bd6e-104">dispone di misure predefinite per identificare problemi ed errori durante i processi di backup e risolverli con un'azione correttiva, se possibile.</span><span class="sxs-lookup"><span data-stu-id="2bd6e-104">has built-in measures to identify problems and errors during backup processes and remedy with corrective action when possible.</span></span>  <span data-ttu-id="2bd6e-105">Tuttavia, vi sono alcune situazioni in cui è richiesto l'intervento dell'utente.</span><span class="sxs-lookup"><span data-stu-id="2bd6e-105">However there are certain situations where user intervention is required.</span></span> <span data-ttu-id="2bd6e-106">In questo argomento vengono descritti gli strumenti che è possibile utilizzare per determinare lo stato di integrità complessivo dei backup e vengono identificati tutti gli errori che devono essere risolti.</span><span class="sxs-lookup"><span data-stu-id="2bd6e-106">This topic describes the tools that you can use to determine the overall health status of backups, and identify any errors that need to be addressed.</span></span>  
  
## <a name="overview-of-ss_smartbackup-built-in-debugging"></a><span data-ttu-id="2bd6e-107">Panoramica del debug predefinito di [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2bd6e-107">Overview of [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] Built-in Debugging</span></span>  
 <span data-ttu-id="2bd6e-108">Tramite [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] vengono esaminati periodicamente i backup pianificati e viene tentata una ripianificazione di tutti i backup non completati.</span><span class="sxs-lookup"><span data-stu-id="2bd6e-108">The [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] periodically reviews scheduled backups and attempts to reschedule any failed backups.</span></span> <span data-ttu-id="2bd6e-109">Viene eseguito periodicamente il polling dell'account di archiviazione per identificare eventuali interruzioni nelle catene di log che interessano la recuperabilità del database e, di conseguenza, vengono pianificati nuovi backup.</span><span class="sxs-lookup"><span data-stu-id="2bd6e-109">It polls the storage account periodically to identify breaks in log chains affecting recoverability of the database, and schedules new backups accordingly.</span></span> <span data-ttu-id="2bd6e-110">Vengono inoltre prese in considerazione i criteri di limitazione di Azure e sono presenti meccanismi per la gestione di più backup di database.</span><span class="sxs-lookup"><span data-stu-id="2bd6e-110">It also takes into account Azure throttling policies, and has mechanisms in place to manage multiple database backups.</span></span> [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] <span data-ttu-id="2bd6e-111">utilizza gli eventi estesi per tenere traccia di tutte le attività.</span><span class="sxs-lookup"><span data-stu-id="2bd6e-111">uses extended events to track all activity.</span></span> <span data-ttu-id="2bd6e-112">Tra i canali di eventi estesi utilizzati da [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] Agent sono inclusi quello amministrativo, operativo, analitico e di debug.</span><span class="sxs-lookup"><span data-stu-id="2bd6e-112">The Extended Event channels used by [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] agent include, Admin, Operational, Analytical, and Debug.</span></span> <span data-ttu-id="2bd6e-113">Gli eventi che rientrano nella categoria amministrativa sono in genere correlati a errori, richiedono l'intervento dell'utente e sono abilitati per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="2bd6e-113">Events that fall under the Admin category usually are related to errors and require user intervention and are enabled by default.</span></span> <span data-ttu-id="2bd6e-114">Anche gli eventi analitici sono abilitati per impostazione predefinita, ma in genere non sono correlati a errori per cui è richiesto l'intervento dell'utente.</span><span class="sxs-lookup"><span data-stu-id="2bd6e-114">Analytical events are also turned on by default, but usually are not related to errors that require user intervention.</span></span> <span data-ttu-id="2bd6e-115">Gli eventi operativi sono in genere informativi.</span><span class="sxs-lookup"><span data-stu-id="2bd6e-115">Operation events are typically informational.</span></span> <span data-ttu-id="2bd6e-116">Ad esempio, gli eventi operativi includono la pianificazione di un backup, il corretto completamento del backup e così via. Il debug è il più dettagliato e viene usato internamente da [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] per determinare i problemi e correggerli, se necessario.</span><span class="sxs-lookup"><span data-stu-id="2bd6e-116">For example, operational events include scheduling a backup, a successful completion of backup, etc. The Debug is the most verbose and is used internally by [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] to determine issues and correct them if required.</span></span>  
  
### <a name="configure-monitoring-parameters-for-ss_smartbackup"></a><span data-ttu-id="2bd6e-117">Configurare parametri di monitoraggio per [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2bd6e-117">Configure Monitoring Parameters for [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)]</span></span>  
 <span data-ttu-id="2bd6e-118">Il stored procedure di sistema **smart_admin. sp_set_parameter** consente di specificare le impostazioni di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="2bd6e-118">The **smart_admin.sp_set_parameter** system stored procedure allows you to specify monitoring settings.</span></span> <span data-ttu-id="2bd6e-119">Nelle sezioni seguenti vengono descritti il processo di abilitazione degli eventi estesi e l'abilitazione della notifica tramite posta elettronica per errori e avvisi.</span><span class="sxs-lookup"><span data-stu-id="2bd6e-119">The following sections walks through the process of enabling Extended Events,  and enabling email notification for errors and warnings.</span></span>  
  
 <span data-ttu-id="2bd6e-120">La funzione **smart_admin. fn_get_parameter** può essere utilizzata per ottenere l'impostazione corrente per un parametro specifico o per tutti i parametri configurati.</span><span class="sxs-lookup"><span data-stu-id="2bd6e-120">The **smart_admin.fn_get_parameter** function can be used to get the current setting for a specific parameter or all configured parameters.</span></span> <span data-ttu-id="2bd6e-121">Se i parametri non sono mai stati configurati, non viene restituito alcun valore.</span><span class="sxs-lookup"><span data-stu-id="2bd6e-121">If the parameters have never been configured, the function does not return any values.</span></span>  
  
1.  <span data-ttu-id="2bd6e-122">Connettersi al [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2bd6e-122">Connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="2bd6e-123">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="2bd6e-123">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="2bd6e-124">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="2bd6e-124">Copy and paste the following example into the query window and then click **Execute**.</span></span> <span data-ttu-id="2bd6e-125">Verranno restituite la configurazione corrente degli eventi estesi e le notifiche di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="2bd6e-125">This will return the current configuration for Extended Events, and e-mail notifications.</span></span>  
  
```sql
Use msdb  
Go  
SELECT * FROM smart_admin.fn_get_parameter (NULL)  
GO  
```  
  
 <span data-ttu-id="2bd6e-126">Per ulteriori informazioni, vedere [smart_admin. fn_get_parameter &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/managed-backup-fn-get-parameter-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="2bd6e-126">For more information, see [smart_admin.fn_get_parameter &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/managed-backup-fn-get-parameter-transact-sql)</span></span>  
  
### <a name="extended-events-for-monitoring"></a><span data-ttu-id="2bd6e-127">Eventi estesi per il monitoraggio</span><span class="sxs-lookup"><span data-stu-id="2bd6e-127">Extended Events for Monitoring</span></span>  
 <span data-ttu-id="2bd6e-128">Per impostazione predefinita, gli eventi amministrativi, operativi e analitici sono abilitati.</span><span class="sxs-lookup"><span data-stu-id="2bd6e-128">By default, Admin, Operational and Analytical events are turned on.</span></span> <span data-ttu-id="2bd6e-129">Gli eventi amministrativi sono più importanti e utili quando si identificano errori per i quali è richiesto l'intervento manuale per la risoluzione.</span><span class="sxs-lookup"><span data-stu-id="2bd6e-129">Admin events are most critical, useful when identifying errors that require manual intervention to solve the problem.</span></span> <span data-ttu-id="2bd6e-130">È possibile che sia necessario abilitare gli eventi operativi e di debug, tuttavia si consideri che questi eventi sono dettagliati e possono richiedere l'applicazione di un filtro.</span><span class="sxs-lookup"><span data-stu-id="2bd6e-130">You may want to turn on the operational and debug events but consider that these events are verbose and may require some filtering.</span></span> <span data-ttu-id="2bd6e-131">Nelle procedure seguenti viene descritto come monitorare gli eventi registrati tramite gli eventi estesi.</span><span class="sxs-lookup"><span data-stu-id="2bd6e-131">The following procedures describe how to monitor events logged through Extended Events.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="2bd6e-132">A differenza degli eventi estesi per il motore SQL, [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] non supporta concetti relativi alla sessione eventi estesi.</span><span class="sxs-lookup"><span data-stu-id="2bd6e-132">Unlike Extended Events for SQL Engine, [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] does not support Extended Event session concepts.</span></span> <span data-ttu-id="2bd6e-133">Per interagire con gli eventi estesi vengono utilizzate le funzioni e le stored procedure di sistema.</span><span class="sxs-lookup"><span data-stu-id="2bd6e-133">System stored procedures and functions are the tools used to interact with extended events.</span></span> <span data-ttu-id="2bd6e-134">Inoltre, è possibile visualizzare il registro eventi estesi dalla directory log.</span><span class="sxs-lookup"><span data-stu-id="2bd6e-134">You can also view the extended event log from the log directory.</span></span>  
  
##### <a name="to-configure-and-view-extended-events"></a><span data-ttu-id="2bd6e-135">Per configurare e visualizzare gli eventi estesi</span><span class="sxs-lookup"><span data-stu-id="2bd6e-135">To Configure and View Extended Events</span></span>  
  
1.  <span data-ttu-id="2bd6e-136">Per visualizzare i canali di eventi estesi disponibili e il relativo stato corrente, eseguire la query riportata di seguito:</span><span class="sxs-lookup"><span data-stu-id="2bd6e-136">To view available Extended Event channels and their current status by running the following query:</span></span>  
  
    ```sql
    SELECT * FROM smart_admin.fn_get_current_xevent_settings()  
    ```  
  
     <span data-ttu-id="2bd6e-137">Nell'output della query vengono visualizzati l'oggetto event_name, l'eventuale configurabilità e se attualmente abilitato.</span><span class="sxs-lookup"><span data-stu-id="2bd6e-137">The output from this query will display the event_name, whether it is configurable or not, and whether it is currently enabled.</span></span>  <span data-ttu-id="2bd6e-138">Per ulteriori informazioni, vedere [smart_admin. fn_get_current_xevent_settings &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/managed-backup-fn-get-current-xevent-settings-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2bd6e-138">For more information, see [smart_admin.fn_get_current_xevent_settings &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/managed-backup-fn-get-current-xevent-settings-transact-sql).</span></span>  
  
2.  <span data-ttu-id="2bd6e-139">Per abilitare gli eventi di debug, eseguire la query seguente:</span><span class="sxs-lookup"><span data-stu-id="2bd6e-139">To enable debug events, run the following query:</span></span>  
  
    ```sql
    --  to enable debug events  
    Use msdb;  
    GO 
    EXEC smart_admin.sp_set_parameter 'FileRetentionDebugXevent', 'True'  
    ```  
  
     <span data-ttu-id="2bd6e-140">Per ulteriori informazioni sulla stored procedure, vedere [smart_admin. sp_set_parameter &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/managed-backup-sp-set-parameter-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2bd6e-140">For more information about the stored procedure, see [smart_admin.sp_set_parameter &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/managed-backup-sp-set-parameter-transact-sql).</span></span>  
  
3.  <span data-ttu-id="2bd6e-141">Per visualizzare gli eventi registrati, eseguire la query riportata di seguito:</span><span class="sxs-lookup"><span data-stu-id="2bd6e-141">To view the logged events run the following query:</span></span>  
  
    ```sql
    --  View all events in the current week  
    Use msdb;  
    Go  
    DECLARE @startofweek datetime  
    DECLARE @endofweek datetime  
    SET @startofweek = DATEADD(Day, 1-DATEPART(WEEKDAY, CURRENT_TIMESTAMP), CURRENT_TIMESTAMP)
    SET @endofweek = DATEADD(Day, 7-DATEPART(WEEKDAY, CURRENT_TIMESTAMP), CURRENT_TIMESTAMP)  
  
    EXEC smart_admin.sp_get_backup_diagnostics @begin_time = @startofweek, @end_time = @endofweek;
    ```  
  
    ```sql
    --  view all admin events  
    Use msdb;  
    Go  
    DECLARE @startofweek datetime  
    DECLARE @endofweek datetime  
    SET @startofweek = DATEADD(Day, 1-DATEPART(WEEKDAY, CURRENT_TIMESTAMP), CURRENT_TIMESTAMP)   
    SET @endofweek = DATEADD(Day, 7-DATEPART(WEEKDAY, CURRENT_TIMESTAMP), CURRENT_TIMESTAMP)  
  
    DECLARE @eventresult TABLE  
    (event_type nvarchar(512),  
    event nvarchar (512),  
    timestamp datetime  
    )  
  
    INSERT INTO @eventresult  
  
    EXEC smart_admin.sp_get_backup_diagnostics @begin_time = @startofweek, @end_time = @endofweek  
  
    SELECT * from @eventresult  
    WHERE event_type LIKE '%admin%'
    ```  
  
### <a name="aggregated-error-countshealth-status"></a><span data-ttu-id="2bd6e-142">Conteggi errori aggregati/stato di integrità</span><span class="sxs-lookup"><span data-stu-id="2bd6e-142">Aggregated Error Counts/Health Status</span></span>  
 <span data-ttu-id="2bd6e-143">La funzione **smart_admin. fn_get_health_status** restituisce una tabella di conteggi di errori aggregati per ogni categoria che può essere utilizzata per monitorare lo stato di integrità di [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2bd6e-143">The **smart_admin.fn_get_health_status** function returns a table of aggregated error counts for each category that can be used to monitor the health status of [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)].</span></span> <span data-ttu-id="2bd6e-144">Questa stessa funzione viene utilizzata anche dal meccanismo di notifica tramite posta elettronica configurato dal sistema descritto più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="2bd6e-144">This same function is also used by the system configured e-mail notification mechanism described later in this topic.</span></span>   
<span data-ttu-id="2bd6e-145">Questi conteggi aggregati possono essere utilizzati per monitorare l'integrità del sistema.</span><span class="sxs-lookup"><span data-stu-id="2bd6e-145">These aggregated counts can be used to monitor system health.</span></span> <span data-ttu-id="2bd6e-146">Ad esempio, se la colonna number_ of_retention_loops è 0 in 30 minuti, è possibile che la gestione della memorizzazione richieda del tempo o che addirittura non funzioni correttamente.</span><span class="sxs-lookup"><span data-stu-id="2bd6e-146">For example, if the number_ of_retention_loops column is 0 in 30 minutes, it is possible that retention management is taking long time or even not working correctly.</span></span> <span data-ttu-id="2bd6e-147">Le colonne di errori diverse da zero possono indicare problemi e, per individuarli, è necessario verificare i registri eventi estesi.</span><span class="sxs-lookup"><span data-stu-id="2bd6e-147">Non-zero error columns may indicate problems and Extended Events logs should be checked to discover the problem.</span></span> <span data-ttu-id="2bd6e-148">In alternativa, chiamare **smart_admin. sp_get_backup_diagnostics** stored procedure per trovare i dettagli dell'errore.</span><span class="sxs-lookup"><span data-stu-id="2bd6e-148">Alternatively, call **smart_admin.sp_get_backup_diagnostics** stored procedure to find the details of the error.</span></span>  
  
### <a name="using-agent-notification-for-assessing-backup-status-and-health"></a><span data-ttu-id="2bd6e-149">Utilizzo della notifica dell'agente per valutare l'integrità e lo stato di backup</span><span class="sxs-lookup"><span data-stu-id="2bd6e-149">Using Agent Notification for Assessing Backup Status and Health</span></span>  
 <span data-ttu-id="2bd6e-150">In [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] è incluso un meccanismo di notifica basato sui criteri di gestione basata su criteri di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2bd6e-150">[!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] includes a notification mechanism that is based on SQL Server policy based management policies.</span></span>  
  
 <span data-ttu-id="2bd6e-151">**Prerequisiti:**</span><span class="sxs-lookup"><span data-stu-id="2bd6e-151">**Prerequisites:**</span></span>  
  
-   <span data-ttu-id="2bd6e-152">Per utilizzare questa funzionalità, è necessario Posta elettronica database.</span><span class="sxs-lookup"><span data-stu-id="2bd6e-152">Database Mail is required to use this functionality.</span></span> <span data-ttu-id="2bd6e-153">Per ulteriori informazioni su come abilitare posta elettronica database per l'istanza di SQL Server, vedere [Configure posta elettronica database](../relational-databases/database-mail/configure-database-mail.md).</span><span class="sxs-lookup"><span data-stu-id="2bd6e-153">For more information, about how to enable DB Mail for the instance of SQL Server, see [Configure Database Mail](../relational-databases/database-mail/configure-database-mail.md).</span></span>  
  
-   <span data-ttu-id="2bd6e-154">Per utilizzare Posta elettronica database devono essere impostate le proprietà di Sistema avvisi di SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="2bd6e-154">SQL Server Agent Alert System properties should be set to use Database Mail.</span></span>  
  
 <span data-ttu-id="2bd6e-155">**Architettura della notifica:**</span><span class="sxs-lookup"><span data-stu-id="2bd6e-155">**Notification Architecture:**</span></span>  
  
-   <span data-ttu-id="2bd6e-156">**Gestione basata su criteri:** Sono impostati due criteri per monitorare l'integrità del backup: **criteri di integrità del sistema di amministrazione intelligente**e i **criteri di integrità dell'azione utente per Smart admin**.</span><span class="sxs-lookup"><span data-stu-id="2bd6e-156">**Policy Based Management:** Two policies are set to monitor backup health: **Smart Admin System Health Policy**, and the **Smart Admin User Action Health Policy**.</span></span> <span data-ttu-id="2bd6e-157">Tramite i criteri di integrità del sistema di amministrazione intelligente vengono valutati errori critici come la mancanza di credenziali SQL o credenziali SQL non valide, errori di connettività e viene segnalata l'integrità del sistema.</span><span class="sxs-lookup"><span data-stu-id="2bd6e-157">The Smart Admin System Health Policy evaluates critical errors like lack of or invalid SQL Credentials, connectivity errors and reports the health of the system.</span></span> <span data-ttu-id="2bd6e-158">Per questi errori è in genere richiesta un'azione manuale per correggere il problema sottostante.</span><span class="sxs-lookup"><span data-stu-id="2bd6e-158">These typically require a manual action to correct the underlying issue.</span></span> <span data-ttu-id="2bd6e-159">Tramite i criteri di integrità dell'azione utente di amministrazione intelligente vengono valutati gli avvisi, ad esempio backup danneggiati e simili.</span><span class="sxs-lookup"><span data-stu-id="2bd6e-159">The Smart Admin User Action Health Policy evaluates warnings such as corrupted backups, and such.</span></span>  <span data-ttu-id="2bd6e-160">Per questi non sono richieste azioni, si tratta solo dell'avviso di un evento.</span><span class="sxs-lookup"><span data-stu-id="2bd6e-160">These may not require any action but just a warning of an event.</span></span> <span data-ttu-id="2bd6e-161">È previsto che problemi di questo tipo vengano risolti automaticamente da [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="2bd6e-161">It is expected that such issues will be automatically taken care of by [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] agent.</span></span>  
  
-   <span data-ttu-id="2bd6e-162">**SQL Server Agent** Processo: la notifica viene eseguita usando un processo di SQL Server Agent con tre passaggi di processo.</span><span class="sxs-lookup"><span data-stu-id="2bd6e-162">**SQL Server Agent** Job: The notification is performed using a SQL Server Agent job that has three job steps.</span></span> <span data-ttu-id="2bd6e-163">Nel primo passaggio di processo viene verificato se [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] è configurato per un database o un'istanza.</span><span class="sxs-lookup"><span data-stu-id="2bd6e-163">In the first job step it detects to see whether [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] is configured for a database or instance.</span></span> <span data-ttu-id="2bd6e-164">Se viene rilevato [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] abilitato e configurato, viene eseguito il secondo passaggio: viene eseguito un cmdlet di PowerShell tramite cui viene valutato lo stato di integrità in base ai criteri di gestione basata su criteri di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2bd6e-164">If it finds [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] enabled and configured, it executes the second step: executes a PowerShell cmdlet that assess the health status by evaluating the SQL Server policy based management policies.</span></span> <span data-ttu-id="2bd6e-165">Se viene rilevato un errore o avviso, l'operazione non viene completata attivando il terzo passo, che prevede l'invio di una notifica tramite posta elettronica con il report dell'errore o dell'avviso.</span><span class="sxs-lookup"><span data-stu-id="2bd6e-165">If it finds either an error or warning, it fails which then triggers the third step: The third step sends out an e-mail notification with the error/warning report.</span></span>  <span data-ttu-id="2bd6e-166">Tuttavia il processo di SQL Server Agent non è abilitato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="2bd6e-166">However this SQL Server Agent job is not enabled by default.</span></span> <span data-ttu-id="2bd6e-167">Per abilitare il processo di notifica tramite posta elettronica, utilizzare il stored procedure di sistema **smart_admin. sp_set_backup_parameter** .</span><span class="sxs-lookup"><span data-stu-id="2bd6e-167">To enable the e-mail notification job, use the **smart_admin.sp_set_backup_parameter** system stored procedure.</span></span>  <span data-ttu-id="2bd6e-168">Nella procedura seguente vengono descritti i passaggi in modo più dettagliato:</span><span class="sxs-lookup"><span data-stu-id="2bd6e-168">The following procedure describes the steps in more detail:</span></span>  
  
##### <a name="enabling-email-notification"></a><span data-ttu-id="2bd6e-169">Abilitazione della notifica tramite posta elettronica</span><span class="sxs-lookup"><span data-stu-id="2bd6e-169">Enabling Email Notification</span></span>  
  
1.  <span data-ttu-id="2bd6e-170">Se Posta elettronica database non è già configurato, attenersi alla procedura descritta in [configurare posta elettronica database](../relational-databases/database-mail/configure-database-mail.md).</span><span class="sxs-lookup"><span data-stu-id="2bd6e-170">If Database Mail is not already configured, use the steps described in [Configure Database Mail](../relational-databases/database-mail/configure-database-mail.md).</span></span>  
  
2.  <span data-ttu-id="2bd6e-171">Impostare il database come sistema di posta elettronica per SQL Server sistema di avvisi: fare clic con il pulsante destro del mouse su **SQL Server Agent**, selezionare **sistema avvisi**, selezionare la casella di controllo **Abilita profilo di posta** , selezionare **posta elettronica database** come **sistema di posta**e selezionare un profilo di posta creato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="2bd6e-171">Set database as the Mail System for SQL Server Alert System: Right Click on **SQL Server Agent**, select **Alert System**, check the **Enable mail profile** box, Select **Database Mail** as the **Mail System**, and select a previously created Mail profile.</span></span>  
  
3.  <span data-ttu-id="2bd6e-172">Eseguire la query riportata di seguito in una finestra Query e immettere l'indirizzo di posta elettronica a cui si desidera inviare la notifica:</span><span class="sxs-lookup"><span data-stu-id="2bd6e-172">Run the following query in a query window and provide the e-mail address where you want the notification to be sent to:</span></span>  
  
    ```sql
    Use msdb  
    Go  
    EXEC smart_admin.sp_set_parameter @parameter_name = 'SSMBackup2WANotificationEmailIds', @parameter_value = '<email address>'
    ```  
  
     <span data-ttu-id="2bd6e-173">Verrà creato un processo di SQL Server Agent utilizzato per raccogliere lo stato di integrità e inviare notifiche quando si verifica un errore o un problema relativo ai backup.</span><span class="sxs-lookup"><span data-stu-id="2bd6e-173">This creates a SQL Server Agent job that is used to gather health status and send notifications when there is an error or an issue with backups.</span></span>  
  
 <span data-ttu-id="2bd6e-174">Di seguito è riportato uno script di esempio per abilitare Posta elettronica database e configurare la notifica di posta elettronica tramite un processo di SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="2bd6e-174">Following is a sample script  to enable DB Mail and set up the e-mail notification through SQL Server Agent Job</span></span>  
  
```sql
-- Prereq: Make sure that SQL Server service runs in a service account that has  
--  access to SMTP Server   
-- set SQL Server service account as domain account   
  
EXEC sp_configure 'show advanced', 1  
RECONFIGURE  
GO  
  
-- Enable DBMail  
EXEC sp_configure 'Database Mail XPs',1  
GO  
RECONFIGURE  
GO  
  
-- Configure DBMail  
DECLARE @emailid NVARCHAR(255)  
-- Note: change this email to your own email id  
SET @emailid = N'emailalias@mycompany.com'  
  
DECLARE @smtpserver NVARCHAR(255)  
SET @smtpserver = N'smtphost.domainname.com'  
  
DECLARE @mailprofile NVARCHAR(255)  
SET @mailprofile = N'my_profile'  
  
EXEC msdb.dbo.sysmail_add_account_sp @account_name=N'myaccount',  
                @email_address = @emailid,  
                @replyto_address = @emailid,  
                @mailserver_name = @smtpserver,  
                @use_default_credentials = 1  
  
EXEC msdb.dbo.sysmail_add_profile_sp @profile_name=@mailprofile  
EXEC msdb.dbo.sysmail_add_profileaccount_sp @profile_name=@mailprofile, @account_name=N'myaccount', @sequence_number=1  
  
-- Set SQL Agent to use DBMail profile  
EXEC msdb.dbo.sp_set_sqlagent_properties @databasemail_profile = @mailprofile  
  
-- Configure Notifications   
EXEC msdb.smart_admin.sp_set_parameter  
@parameter_name = 'SSMBackup2WANotificationEmailIds',  
@parameter_value = @emailid  
  
-- To test is you are receiving notifications  
-- delete few backup files from your storage container, Wait for 15 minutes & see if you get any email notification
```  
  
### <a name="using-powershell-to-setup-custom-health-monitoring"></a><span data-ttu-id="2bd6e-175">Utilizzo di PowerShell per configurare il monitoraggio dello stato di integrità personalizzato</span><span class="sxs-lookup"><span data-stu-id="2bd6e-175">Using PowerShell to Setup Custom Health Monitoring</span></span>  
 <span data-ttu-id="2bd6e-176">Il cmdlet **test-SqlSmartAdmin** può essere usato per creare un monitoraggio dello stato personalizzato.</span><span class="sxs-lookup"><span data-stu-id="2bd6e-176">The **Test-SqlSmartAdmin** cmdlet can be used to create custom health monitoring.</span></span> <span data-ttu-id="2bd6e-177">Ad esempio, l'opzione di notifica descritta nella sezione precedente può essere configurata a livello di istanza.</span><span class="sxs-lookup"><span data-stu-id="2bd6e-177">For example, the notification option described in the previous section can be configured at the instance level.</span></span>  <span data-ttu-id="2bd6e-178">Se si dispone di più istanze di SQL Server configurate per l'utilizzo di [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)], il cmdlet di PowerShell può essere utilizzato per creare script per raccogliere lo stato e l'integrità dei backup per tutte le istanze.</span><span class="sxs-lookup"><span data-stu-id="2bd6e-178">If you have several instances of SQL Server configured to use [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)], the PowerShell cmdlet can be used to create scripts in gather the status and health of backups for all the instances.</span></span>  
  
 <span data-ttu-id="2bd6e-179">Il cmdlet **test-SqlSmartAdmin** valuta gli errori e gli avvisi restituiti dal SQL Server criteri di gestione basata su criteri e segnala uno stato di rollup.</span><span class="sxs-lookup"><span data-stu-id="2bd6e-179">The **Test-SqlSmartAdmin** cmdlet assesses the errors and warnings returned by the SQL Server Policy Based Management policies and reports out a rolled up status.</span></span>  <span data-ttu-id="2bd6e-180">Per impostazione predefinita, tramite questo cmdlet vengono utilizzati i criteri di sistema.</span><span class="sxs-lookup"><span data-stu-id="2bd6e-180">By default this cmdlet uses the system policies.</span></span> <span data-ttu-id="2bd6e-181">Per includere tutti i criteri personalizzati, utilizzare il parametro `-AllowUserPolicies`.</span><span class="sxs-lookup"><span data-stu-id="2bd6e-181">To include any custom policy use the `-AllowUserPolicies` parameter.</span></span>  
  
 <span data-ttu-id="2bd6e-182">Di seguito è riportato un esempio di script di PowerShell tramite cui viene restituito un report di errori e avvisi basato sui criteri di sistema e su tutti i criteri utente creati:</span><span class="sxs-lookup"><span data-stu-id="2bd6e-182">Following is a sample PowerShell script that returns a report of errors and warnings based on the system policies and any user policies created:</span></span>  
  
```powershell
$policyResults = Get-SqlSmartAdmin | Test-SqlSmartAdmin -AllowUserPolicies  
$policyResults.PolicyEvaluationDetails | Select Name, Category, Expression, Result, Exception | fl
```  
  
 <span data-ttu-id="2bd6e-183">Lo script seguente restituisce un report dettagliato degli errori e degli avvisi per l'istanza predefinita ( `\SQL\COMPUTER\DEFAULT` ):</span><span class="sxs-lookup"><span data-stu-id="2bd6e-183">The following script returns a detailed report of the errors and warnings for the default instance (`\SQL\COMPUTER\DEFAULT`):</span></span>  
  
```powershell
(Get-SqlSmartAdmin ).EnumHealthStatus()  
```  
  
### <a name="objects-in-msdb-database"></a><span data-ttu-id="2bd6e-184">Oggetti in un database MSDB</span><span class="sxs-lookup"><span data-stu-id="2bd6e-184">Objects in MSDB database</span></span>  
 <span data-ttu-id="2bd6e-185">Sono disponibili degli oggetti che vengono installati per implementare le funzionalità.</span><span class="sxs-lookup"><span data-stu-id="2bd6e-185">There are objects that are installed to implement the functionality.</span></span> <span data-ttu-id="2bd6e-186">Questi oggetti sono riservati per l'utilizzo interno.</span><span class="sxs-lookup"><span data-stu-id="2bd6e-186">These objects are reserved for internal use.</span></span> <span data-ttu-id="2bd6e-187">Tuttavia, è disponibile una tabella di sistema che può essere utile per monitorare lo stato di backup: smart_backup_files.</span><span class="sxs-lookup"><span data-stu-id="2bd6e-187">However, there is one system table that can be useful in monitoring the backup status: smart_backup_files.</span></span> <span data-ttu-id="2bd6e-188">La maggior parte delle informazioni archiviate in questa tabella pertinente per il monitoraggio, ad esempio il tipo di backup, il nome del database, il primo e l'ultimo LSN, le date di scadenza del backup vengono esposte tramite la funzione di sistema [smart_admin. fn_available_backups &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/managed-backup-fn-available-backups-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2bd6e-188">Most of the Information   stored in this table relevant to monitoring like the type of backup, database name, first and last lsn, backup expiry dates are exposed through the system function [smart_admin.fn_available_backups &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/managed-backup-fn-available-backups-transact-sql).</span></span> <span data-ttu-id="2bd6e-189">Tuttavia la colonna stato nella tabella smart_backup_files in cui viene indicato lo stato del file di backup non è disponibile tramite la funzione.</span><span class="sxs-lookup"><span data-stu-id="2bd6e-189">However the status column in the smart_backup_files table which indicates the status of the backup file is not available using the function.</span></span> <span data-ttu-id="2bd6e-190">Di seguito è riportata una query di esempio utilizzabile per recuperare alcune informazioni, tra cui lo stato della tabella di sistema:</span><span class="sxs-lookup"><span data-stu-id="2bd6e-190">Following is a sample query you can use to retrieve the some information including the status from the system table:</span></span>  
  
```sql
USE msdb  
GO  
SELECT  
 database_name AS [Database Name] ,backup_path AS [Backup Destination and File]  
,[Backup Type] =  
CASE backup_type  
WHEN 1 THEN 'FULL'  
WHEN 2 THEN 'LOG'  
END  
,[Backup Status] =  
CASE [status]  
WHEN 'A' THEN 'Available'  
WHEN 'B' THEN 'Copy In Progress'  
WHEN 'C' THEN 'Corrupted'  
WHEN 'D' THEN 'Deleted'  
WHEN 'F' THEN 'Copy Failed'  
WHEN 'U' THEN 'Unknown'  
END  
,first_lsn AS [First LSN]  
,last_lsn AS [Last LSN]  
,backup_start_date AS [Backup Start Time]  
,backup_finish_date AS [Backup Completion Time]  
,expiration_date AS [Backup Expiry Date/Time]  
FROM  
smart_backup_files;
```  
  
 <span data-ttu-id="2bd6e-191">Di seguito è riportata una spiegazione dettagliata del diverso stato restituito:</span><span class="sxs-lookup"><span data-stu-id="2bd6e-191">Following is a detailed explanation of the different status returned:</span></span>  
  
-   <span data-ttu-id="2bd6e-192">**Disponibile-A:** Si tratta di un normale file di backup.</span><span class="sxs-lookup"><span data-stu-id="2bd6e-192">**Available - A:** This is a normal backup file.</span></span> <span data-ttu-id="2bd6e-193">Il backup è stato completato e anche verificato che sia disponibile nell'archiviazione di Azure.</span><span class="sxs-lookup"><span data-stu-id="2bd6e-193">The backup has been completed, and also verified that it is available in the Azure storage.</span></span>  
  
-   <span data-ttu-id="2bd6e-194">**Copia in corso-B:** Questo stato è specifico per i database del gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="2bd6e-194">**Copy in Progress -B:** This status is specifically for Availability Group databases.</span></span> <span data-ttu-id="2bd6e-195">Se tramite [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] viene rilevata un'interruzione nella catena dei log di backup, tentare innanzitutto di identificare il backup da cui potrebbe essere stata causata l'interruzione della catena di backup.</span><span class="sxs-lookup"><span data-stu-id="2bd6e-195">If [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] detects a break in the backup log chain, it will first attempt identify the  backup that might have caused the break in backup chain.</span></span> <span data-ttu-id="2bd6e-196">Quando si trova il file di backup, tenta di copiare il file in archiviazione di Azure.</span><span class="sxs-lookup"><span data-stu-id="2bd6e-196">On finding the backup file it attempts to copy the file to Azure storage.</span></span> <span data-ttu-id="2bd6e-197">Quando il processo di copia è in corso verrà visualizzato questo stato.</span><span class="sxs-lookup"><span data-stu-id="2bd6e-197">When the copying process is in progress it will display this status.</span></span>  
  
-   <span data-ttu-id="2bd6e-198">**Copia non riuscita-F:** Analogamente alla copia in corso, si tratta di database del gruppo di disponibilità t specifici.</span><span class="sxs-lookup"><span data-stu-id="2bd6e-198">**Copy Failed - F:** Similar to Copy In Progress, this is specific t Availability Group databases.</span></span> <span data-ttu-id="2bd6e-199">Se il processo di copia non viene completato, lo stato è contrassegnato come F.</span><span class="sxs-lookup"><span data-stu-id="2bd6e-199">If the copy process fails, the status is marked as F.</span></span>  
  
-   <span data-ttu-id="2bd6e-200">**Danneggiato-C:** Se [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] non è in grado di verificare il file di backup nell'archiviazione eseguendo un comando restore HEADER_ONLY anche dopo più tentativi, questo file viene contrassegnato come danneggiato.</span><span class="sxs-lookup"><span data-stu-id="2bd6e-200">**Corrupted - C:** If [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] is unable to verify the backup file in the storage by performing a RESTORE HEADER_ONLY command even after multiple attempts, it marks this file as corrupted.</span></span> <span data-ttu-id="2bd6e-201">Tramite [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] verrà pianificato un backup per garantire che dal file danneggiato non venga generata un'interruzione della catena di backup.</span><span class="sxs-lookup"><span data-stu-id="2bd6e-201">[!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] will schedule a backup to ensure that the corrupted file does not result in a break of the backup chain.</span></span>  
  
-   <span data-ttu-id="2bd6e-202">**Eliminato-D:** Il file corrispondente non è stato trovato nell'archiviazione di Azure.</span><span class="sxs-lookup"><span data-stu-id="2bd6e-202">**Deleted - D:** The corresponding file cannot be found in the Azure storage.</span></span> <span data-ttu-id="2bd6e-203">Tramite [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] verrà pianificato un backup se viene generata un'interruzione della catena di backup da parte del file eliminato.</span><span class="sxs-lookup"><span data-stu-id="2bd6e-203">[!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] will schedule a backup if the deleted file results in a break in the backup chain.</span></span>  
  
-   <span data-ttu-id="2bd6e-204">**Sconosciuto-U:** Questo stato indica che [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] non è ancora stato possibile verificare l'esistenza del file e le relative proprietà nell'archiviazione di Azure.</span><span class="sxs-lookup"><span data-stu-id="2bd6e-204">**Unknown - U:** This status indicated that [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] has not yet been able to verify file existence and its properties in the Azure storage.</span></span> <span data-ttu-id="2bd6e-205">Alla successiva esecuzione del processo, vale a dire circa ogni 15 minuti, questo stato verrà aggiornato.</span><span class="sxs-lookup"><span data-stu-id="2bd6e-205">The next time the process runs, which is approximately every 15 minutes, this status will be updated.</span></span>  
