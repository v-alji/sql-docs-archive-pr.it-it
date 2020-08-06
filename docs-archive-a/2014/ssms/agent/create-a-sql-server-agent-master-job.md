---
title: Creare un processo master di SQL Server Agent | Microsoft Docs
ms.custom: ''
ms.date: 04/26/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], master jobs
- jobs [SQL Server Agent], creating
- master SQL Server Agent job [SQL Server]
ms.assetid: c12ab23f-d7ee-43a5-8cd2-0a9121292bcd
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8a6503caec3f153878e360ee29ce09a5c099ade5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715931"
---
# <a name="create-a-sql-server-agent-master-job"></a><span data-ttu-id="d384b-102">Creazione di un processo master di SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="d384b-102">Create a SQL Server Agent Master Job</span></span>
  <span data-ttu-id="d384b-103">In questo argomento viene descritto come creare un [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] processo di agente Master in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d384b-103">This topic describes how to create a master [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="d384b-104">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="d384b-104">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="d384b-105">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="d384b-105">Limitations and Restrictions</span></span>  
 <span data-ttu-id="d384b-106">Le modifiche apportate ai processi master di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent devono essere propagate a tutti i server di destinazione interessati.</span><span class="sxs-lookup"><span data-stu-id="d384b-106">Changes to master [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs must be propagated to all involved target servers.</span></span> <span data-ttu-id="d384b-107">Poiché i server di destinazione non scaricano il processo finché le destinazioni non vengono specificate, [!INCLUDE[msCoName](../../includes/msconame-md.md)] consiglia di completare tutti i passaggi e le pianificazioni di un particolare processo prima di specificare i server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="d384b-107">Because target servers do not initially download a job until those targets are specified, [!INCLUDE[msCoName](../../includes/msconame-md.md)] recommends that you complete all job steps and job schedules for a particular job before you specify any target servers.</span></span> <span data-ttu-id="d384b-108">In caso contrario, è necessario richiedere manualmente che i server di destinazione scarichino nuovamente il processo modificato, eseguendo la stored procedure **sp_post_msx_operation** o modificando il processo con [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d384b-108">Otherwise, you must manual request that the target servers download the modified job again, either by executing the **sp_post_msx_operation** stored procedure or modifying the job using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="d384b-109">Per ulteriori informazioni, vedere [sp_post_msx_operation &#40;&#41;Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-post-msx-operation-transact-sql) o [modificare un processo](modify-a-job.md).</span><span class="sxs-lookup"><span data-stu-id="d384b-109">For more information, see [sp_post_msx_operation &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-post-msx-operation-transact-sql) or [Modify a Job](modify-a-job.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="d384b-110">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="d384b-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="d384b-111">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="d384b-111">Permissions</span></span>  
 <span data-ttu-id="d384b-112">I processi distribuiti con passaggi associati a un proxy vengono eseguiti nel contesto dell'account proxy nel server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="d384b-112">Distributed jobs that have steps which are associated with a proxy run under the context of the proxy account on the target server.</span></span> <span data-ttu-id="d384b-113">Verificare che siano soddisfatte le condizioni seguenti, per assicurare che i passaggi di processo associati a un proxy vengano scaricati dal server master a quello di destinazione:</span><span class="sxs-lookup"><span data-stu-id="d384b-113">Make sure that the following conditions are met or job steps that are associated with a proxy will not be downloaded from the master server to the target:</span></span>  
  
-   <span data-ttu-id="d384b-114">La sottochiave del registro di sistema **\ HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft\Microsoft SQL Server \\ < *instance_name*> \SQL Server Agent\AllowDownloadedJobsToMatchProxyName** (REG_DWORD) è impostata su 1 (true).</span><span class="sxs-lookup"><span data-stu-id="d384b-114">The registry subkey **\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<*instance_name*>\SQL Server Agent\AllowDownloadedJobsToMatchProxyName** (REG_DWORD) is set to 1 (true).</span></span> <span data-ttu-id="d384b-115">Per impostazione predefinita, questa sottochiave è impostata su 0 (False).</span><span class="sxs-lookup"><span data-stu-id="d384b-115">By default, this subkey is set to 0 (false).</span></span>  
  
-   <span data-ttu-id="d384b-116">Nel server di destinazione deve esistere un account proxy con lo stesso nome dell'account proxy del server master utilizzato per l'esecuzione del passaggio del processo.</span><span class="sxs-lookup"><span data-stu-id="d384b-116">A proxy account exists on the target server that has the same name as the master server proxy account under which the job step runs.</span></span>  
  
 <span data-ttu-id="d384b-117">Se si verificano errori nel download dei passaggi dei processi che usano account proxy dal server master a quello di destinazione, è possibile controllare se nella colonna **error_message** della tabella **sysdownloadlist** nel database **msdb** sono presenti i messaggi di errore seguenti:</span><span class="sxs-lookup"><span data-stu-id="d384b-117">If job steps that use proxy accounts fail when downloading them from the master server to the target server, you can check the **error_message** column in the **sysdownloadlist** table in the **msdb** database for the following error messages:</span></span>  
  
-   <span data-ttu-id="d384b-118">"Per questo passaggio del processo è necessario un account proxy, ma l'individuazione dei proxy è disabilitata nel server di destinazione."</span><span class="sxs-lookup"><span data-stu-id="d384b-118">"The job step requires a proxy account, however proxy matching is disabled on the target server."</span></span> <span data-ttu-id="d384b-119">Per risolvere il problema, impostare la sottochiave del Registro di sistema **AllowDownloadedJobsToMatchProxyName** su 1.</span><span class="sxs-lookup"><span data-stu-id="d384b-119">To resolve this error, set the **AllowDownloadedJobsToMatchProxyName** registry subkey to 1.</span></span>  
  
-   <span data-ttu-id="d384b-120">"Impossibile trovare il proxy."</span><span class="sxs-lookup"><span data-stu-id="d384b-120">"Proxy not found."</span></span> <span data-ttu-id="d384b-121">Per risolvere il problema, verificare che nel server di destinazione sia disponibile un account proxy con lo stesso nome dell'account proxy del server master utilizzato per l'esecuzione del passaggio di processo.</span><span class="sxs-lookup"><span data-stu-id="d384b-121">To resolve this error, make sure a proxy account exists on the target server that has the same name as the master server proxy account under which the job step runs.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="d384b-122">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d384b-122">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-master-sql-server-agent-job"></a><span data-ttu-id="d384b-123">Per creare un processo master di SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="d384b-123">To create a master SQL Server Agent job</span></span>  
  
1.  <span data-ttu-id="d384b-124">In **Esplora oggetti**fare clic sul segno più per espandere il server in cui si desidera creare un processo di SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="d384b-124">In the **Object Explorer**, click the plus sign to expand the server where you want to create a SQL Server Agent job.</span></span>  
  
2.  <span data-ttu-id="d384b-125">Fare clic sul segno più per espandere **SQL Server Agent**.</span><span class="sxs-lookup"><span data-stu-id="d384b-125">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="d384b-126">Fare clic con il pulsante destro del mouse sulla cartella **Processi** e quindi selezionare **Nuovo processo**.</span><span class="sxs-lookup"><span data-stu-id="d384b-126">Right-click the **Jobs** folder and select **New Job...**.</span></span>  
  
4.  <span data-ttu-id="d384b-127">Nella pagina **Generale** della finestra di dialogo **Nuove processo** modificare le proprietà generali del processo.</span><span class="sxs-lookup"><span data-stu-id="d384b-127">In the **New Job** dialog box, on the **General** page, modify the general properties of the job.</span></span> <span data-ttu-id="d384b-128">Per ulteriori informazioni sulle opzioni disponibili in questa pagina, vedere [Proprietà processo e nuovo processo &#40;pagina generale&#41;](../../integration-services/general-page-of-integration-services-designers-options.md)</span><span class="sxs-lookup"><span data-stu-id="d384b-128">For more information on the available options on this page, see [Job Properties and New Job &#40;General Page&#41;](../../integration-services/general-page-of-integration-services-designers-options.md)</span></span>  
  
5.  <span data-ttu-id="d384b-129">Nella pagina **Passaggi** , organizzare i passaggi del processo.</span><span class="sxs-lookup"><span data-stu-id="d384b-129">On the **Steps** page, organize the job steps.</span></span> <span data-ttu-id="d384b-130">Per ulteriori informazioni sulle opzioni disponibili in questa pagina, vedere la [pagina Proprietà processo: nuovo processo &#40;passaggi&#41;](job-properties-new-job-steps-page.md)</span><span class="sxs-lookup"><span data-stu-id="d384b-130">For more information on the available options on this page, see [Job Properties:New Job &#40;Steps Page&#41;](job-properties-new-job-steps-page.md)</span></span>  
  
6.  <span data-ttu-id="d384b-131">Nella pagina **Pianificazioni** , organizzare le pianificazioni per il processo.</span><span class="sxs-lookup"><span data-stu-id="d384b-131">On the **Schedules** page, organize schedules for the job.</span></span> <span data-ttu-id="d384b-132">Per ulteriori informazioni sulle opzioni disponibili in questa pagina, vedere [Proprietà processo: pagina Pianificazioni nuovo processo &#40;&#41;](job-properties-new-job-schedules-page.md)</span><span class="sxs-lookup"><span data-stu-id="d384b-132">For more information on the available options on this page, see [Job Properties: New Job &#40;Schedules Page&#41;](job-properties-new-job-schedules-page.md)</span></span>  
  
7.  <span data-ttu-id="d384b-133">Nella pagina **Avvisi** , organizzare gli avvisi per il processo.</span><span class="sxs-lookup"><span data-stu-id="d384b-133">On the **Alerts** page, organize the alerts for the job.</span></span> <span data-ttu-id="d384b-134">Per ulteriori informazioni sulle opzioni disponibili in questa pagina, vedere la [pagina Proprietà processo: nuovo processo &#40;avvisi&#41;](job-properties-new-job-alerts-page.md)</span><span class="sxs-lookup"><span data-stu-id="d384b-134">For more information on the available options on this page, see [Job Properties: New Job &#40;Alerts Page&#41;](job-properties-new-job-alerts-page.md)</span></span>  
  
8.  <span data-ttu-id="d384b-135">Nella pagina **Notifiche** impostare le azioni che [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent deve eseguire al completamento del processo.</span><span class="sxs-lookup"><span data-stu-id="d384b-135">On the **Notifications** page, set actions for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to perform when the job completes.</span></span> <span data-ttu-id="d384b-136">Per ulteriori informazioni sulle opzioni disponibili in questa pagina, vedere [Proprietà processo: nuova pagina notifiche &#40;processo&#41;](job-properties-new-job-notifications-page.md).</span><span class="sxs-lookup"><span data-stu-id="d384b-136">For more information on the available options on this page, see [Job Properties: New Job &#40;Notifications Page&#41;](job-properties-new-job-notifications-page.md).</span></span>  
  
9. <span data-ttu-id="d384b-137">Nella pagina **Destinazioni** , gestire i server di destinazione per il processo.</span><span class="sxs-lookup"><span data-stu-id="d384b-137">On the **Targets** page, manage the target servers for the job.</span></span> <span data-ttu-id="d384b-138">Per ulteriori informazioni sulle opzioni disponibili in questa pagina, vedere [Proprietà processo: nuova pagina &#40;di destinazione processo&#41;](job-properties-new-job-targets-page.md).</span><span class="sxs-lookup"><span data-stu-id="d384b-138">For more information on the available options on this page, see [Job Properties: New Job &#40;Targets Page&#41;](job-properties-new-job-targets-page.md).</span></span>  
  
10. <span data-ttu-id="d384b-139">Al termine, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d384b-139">When finished, click **OK**.</span></span>  
  

  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="d384b-140">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d384b-140">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-master-sql-server-agent-job"></a><span data-ttu-id="d384b-141">Per creare un processo master di SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="d384b-141">To create a master SQL Server Agent job</span></span>  
  
1.  <span data-ttu-id="d384b-142">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d384b-142">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="d384b-143">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="d384b-143">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="d384b-144">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="d384b-144">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE msdb ;  
    GO  
    -- Adds a new job executed by the SQLServerAgent service called 'Weekly Sales Data Backup'  
    EXEC dbo.sp_add_job  
        @job_name = N'Weekly Sales Data Backup' ;  
    GO  
    -- Adds a step (operation) to the 'Weekly Sales Data Backup' job.  
    EXEC sp_add_jobstep  
        @job_name = N'Weekly Sales Data Backup',  
        @step_name = N'Set database to read only',  
        @subsystem = N'TSQL',  
        @command = N'ALTER DATABASE SALES SET READ_ONLY',   
        @retry_attempts = 5,  
        @retry_interval = 5 ;  
    GO  
    -- Creates a schedule called RunOnce  
    EXEC dbo.sp_add_schedule  
        @schedule_name = N'RunOnce',  
        @freq_type = 1,  
        @active_start_time = 233000 ;  
    USE msdb ;  
    GO  
    -- Sets the 'RunOnce' schedule to the "Weekly Sales Data Backup' Job  
    EXEC sp_attach_schedule  
       @job_name = N'Weekly Sales Data Backup',  
       @schedule_name = N'RunOnce';  
    GO  
    -- assigns the multiserver job Weekly Sales Backups to the server SEATTLE2  
    -- assumes that SEATTLE2 is registered as a target server for the current instance.  
    EXEC dbo.sp_add_jobserver  
        @job_name = N'Weekly Sales Data Backups',  
        @server_name = N'SEATTLE2' ;  
    GO  
    ```  
  
 <span data-ttu-id="d384b-145">Per altre informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="d384b-145">For more information, see:</span></span>  
  
-   [<span data-ttu-id="d384b-146">sp_add_job &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d384b-146">sp_add_job &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-job-transact-sql)  
  
-   [<span data-ttu-id="d384b-147">sp_add_jobstep &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d384b-147">sp_add_jobstep &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql)  
  
-   [<span data-ttu-id="d384b-148">sp_add_schedule &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d384b-148">sp_add_schedule &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-schedule-transact-sql)  
  
-   [<span data-ttu-id="d384b-149">sp_attach_schedule &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d384b-149">sp_attach_schedule &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-attach-schedule-transact-sql)  
  
-   [<span data-ttu-id="d384b-150">sp_add_jobserver &#40;&#41;Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d384b-150">sp_add_jobserver &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-jobserver-transact-sql)  
  

  
  
