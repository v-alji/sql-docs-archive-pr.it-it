---
title: Creare un processo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], creating
- SQL Server Agent jobs, creating
ms.assetid: b35af2b6-6594-40d1-9861-4d5dd906048c
author: stevestein
ms.author: sstein
ms.openlocfilehash: de74f032924fbb0b6643bd8f3d482481ffb1f983
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623726"
---
# <a name="create-a-job"></a><span data-ttu-id="54711-102">Creare un processo</span><span class="sxs-lookup"><span data-stu-id="54711-102">Create a Job</span></span>
  <span data-ttu-id="54711-103">In questo argomento viene descritto come creare un processo di SQL Server Agent in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)] o SQL Server Management Objects (SMO).</span><span class="sxs-lookup"><span data-stu-id="54711-103">This topic describes how to create a SQL Server Agent job in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Management Objects (SMO).</span></span>  
  
 <span data-ttu-id="54711-104">Per aggiungere al processo passaggi, pianificazioni, avvisi e notifiche da inviare agli operatori, vedere i collegamenti agli argomenti nella sezione Vedere anche.</span><span class="sxs-lookup"><span data-stu-id="54711-104">To add job steps, schedules, alerts, and notifications that can be sent to operators, see the links to topics in the See Also section.</span></span>  
  
-   <span data-ttu-id="54711-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="54711-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="54711-106">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="54711-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="54711-107">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="54711-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="54711-108">**Per creare un processo tramite:**</span><span class="sxs-lookup"><span data-stu-id="54711-108">**To create a job, using:**</span></span>  
  
     <span data-ttu-id="54711-109">[SQL Server Management Studio](#SSMSProcedure),</span><span class="sxs-lookup"><span data-stu-id="54711-109">[SQL Server Management Studio](#SSMSProcedure),</span></span>  
  
     [<span data-ttu-id="54711-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="54711-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="54711-111">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="54711-111">SQL Server Management Objects</span></span>](#SMOProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="54711-112">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="54711-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="54711-113">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="54711-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="54711-114">Per creare un processo, è necessario che l'utente sia membro di uno dei ruoli predefiniti del database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent o del ruolo predefinito del server **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="54711-114">To create a job, a user must be a member of one of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database roles or the **sysadmin** fixed server role.</span></span> <span data-ttu-id="54711-115">Un processo può essere modificato solo dal proprietario o dai membri del ruolo **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="54711-115">A job can be edited only by its owner or members of the **sysadmin** role.</span></span> <span data-ttu-id="54711-116">Per altre informazioni sui ruoli predefiniti del database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, vedere [Ruoli di database predefiniti di SQL Server Agent](sql-server-agent-fixed-database-roles.md).</span><span class="sxs-lookup"><span data-stu-id="54711-116">For more information about the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database roles, see [SQL Server Agent Fixed Database Roles](sql-server-agent-fixed-database-roles.md).</span></span>  
  
-   <span data-ttu-id="54711-117">L'assegnazione di un processo a un altro account di accesso non garantisce che il nuovo proprietario disponga di autorizzazioni sufficienti per eseguire correttamente il processo.</span><span class="sxs-lookup"><span data-stu-id="54711-117">Assigning a job to another login does not guarantee that the new owner has sufficient permission to run the job successfully.</span></span>  
  
-   <span data-ttu-id="54711-118">I processi locali vengono memorizzati nella cache dall'istanza locale di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="54711-118">Local jobs are cached by the local [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span> <span data-ttu-id="54711-119">Eventuali modifiche, pertanto, forzano in modo implicito una nuova memorizzazione nella cache da parte di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="54711-119">Therefore, any modifications implicitly force [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to re-cache the job.</span></span> <span data-ttu-id="54711-120">Poiché [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent non memorizza nella cache il processo fino alla chiamata di **sp_add_jobserver** , è consigliabile chiamare la store procedure **sp_add_jobserver** per ultima.</span><span class="sxs-lookup"><span data-stu-id="54711-120">Because [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent does not cache the job until **sp_add_jobserver** is called, it is more efficient to call **sp_add_jobserver** last.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="54711-121">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="54711-121">Security</span></span>  
  
-   <span data-ttu-id="54711-122">Solo un amministratore di sistema può cambiare il proprietario di un processo.</span><span class="sxs-lookup"><span data-stu-id="54711-122">You must be a system administrator to change the owner of a job.</span></span>  
  
-   <span data-ttu-id="54711-123">Per motivi di sicurezza, solo il proprietario del processo o un membro del ruolo **sysadmin** può modificare la definizione del processo.</span><span class="sxs-lookup"><span data-stu-id="54711-123">For security reasons, only the job owner or a member of the **sysadmin** role can change the definition of the job.</span></span> <span data-ttu-id="54711-124">Solo i membri del ruolo predefinito del server **sysadmin** possono assegnare la proprietà di un processo ad altri utenti ed eseguire qualsiasi processo, indipendentemente dal proprietario.</span><span class="sxs-lookup"><span data-stu-id="54711-124">Only members of the **sysadmin** fixed server role can assign job ownership to other users, and they can run any job, regardless of the job owner.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="54711-125">Se si assegna la proprietà di un processo a un utente che non è membro del ruolo predefinito del server **sysadmin** e il processo sta eseguendo operazioni per le quali sono necessari account proxy, ad esempio l'esecuzione del pacchetto [!INCLUDE[ssIS](../../includes/ssis-md.md)] , verificare che l'utente possa accedere all'account proxy. In caso contrario, verrà generato un errore.</span><span class="sxs-lookup"><span data-stu-id="54711-125">If you change job ownership to a user who is not a member of the **sysadmin** fixed server role, and the job is executing job steps that require proxy accounts (for example, [!INCLUDE[ssIS](../../includes/ssis-md.md)] package execution), make sure that the user has access to that proxy account or else the job will fail.</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="54711-126">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="54711-126">Permissions</span></span>  
 <span data-ttu-id="54711-127">Per informazioni dettagliate, vedere [Implementazione della sicurezza di SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="54711-127">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="54711-128">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="54711-128">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-sql-server-agent-job"></a><span data-ttu-id="54711-129">Per creare un processo di SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="54711-129">To create a SQL Server Agent job</span></span>  
  
1.  <span data-ttu-id="54711-130">In **Esplora oggetti**fare clic sul segno più per espandere il server in cui si desidera creare un processo di SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="54711-130">In the **Object Explorer**, click the plus sign to expand the server where you want to create a SQL Server Agent job.</span></span>  
  
2.  <span data-ttu-id="54711-131">Fare clic sul segno più per espandere **SQL Server Agent**.</span><span class="sxs-lookup"><span data-stu-id="54711-131">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="54711-132">Fare clic con il pulsante destro del mouse sulla cartella **Processi** e quindi selezionare **Nuovo processo**.</span><span class="sxs-lookup"><span data-stu-id="54711-132">Right-click the **Jobs** folder and select **New Job...**.</span></span>  
  
4.  <span data-ttu-id="54711-133">Nella pagina **Generale** della finestra di dialogo **Nuove processo** modificare le proprietà generali del processo.</span><span class="sxs-lookup"><span data-stu-id="54711-133">In the **New Job** dialog box, on the **General** page, modify the general properties of the job.</span></span> <span data-ttu-id="54711-134">Per ulteriori informazioni sulle opzioni disponibili in questa pagina, vedere [Proprietà processo e nuovo processo &#40;pagina generale&#41;](../../integration-services/general-page-of-integration-services-designers-options.md)</span><span class="sxs-lookup"><span data-stu-id="54711-134">For more information on the available options on this page, see [Job Properties and New Job &#40;General Page&#41;](../../integration-services/general-page-of-integration-services-designers-options.md)</span></span>  
  
5.  <span data-ttu-id="54711-135">Nella pagina **Passaggi** , organizzare i passaggi del processo.</span><span class="sxs-lookup"><span data-stu-id="54711-135">On the **Steps** page, organize the job steps.</span></span> <span data-ttu-id="54711-136">Per ulteriori informazioni sulle opzioni disponibili in questa pagina, vedere la [pagina Proprietà processo: nuovo processo &#40;passaggi&#41;](job-properties-new-job-steps-page.md)</span><span class="sxs-lookup"><span data-stu-id="54711-136">For more information on the available options on this page, see [Job Properties:New Job &#40;Steps Page&#41;](job-properties-new-job-steps-page.md)</span></span>  
  
6.  <span data-ttu-id="54711-137">Nella pagina **Pianificazioni** , organizzare le pianificazioni per il processo.</span><span class="sxs-lookup"><span data-stu-id="54711-137">On the **Schedules** page, organize schedules for the job.</span></span> <span data-ttu-id="54711-138">Per ulteriori informazioni sulle opzioni disponibili in questa pagina, vedere [Proprietà processo: pagina Pianificazioni nuovo processo &#40;&#41;](job-properties-new-job-schedules-page.md)</span><span class="sxs-lookup"><span data-stu-id="54711-138">For more information on the available options on this page, see [Job Properties: New Job &#40;Schedules Page&#41;](job-properties-new-job-schedules-page.md)</span></span>  
  
7.  <span data-ttu-id="54711-139">Nella pagina **Avvisi** , organizzare gli avvisi per il processo.</span><span class="sxs-lookup"><span data-stu-id="54711-139">On the **Alerts** page, organize the alerts for the job.</span></span> <span data-ttu-id="54711-140">Per ulteriori informazioni sulle opzioni disponibili in questa pagina, vedere la [pagina Proprietà processo: nuovo processo &#40;avvisi&#41;](job-properties-new-job-alerts-page.md)</span><span class="sxs-lookup"><span data-stu-id="54711-140">For more information on the available options on this page, see [Job Properties: New Job &#40;Alerts Page&#41;](job-properties-new-job-alerts-page.md)</span></span>  
  
8.  <span data-ttu-id="54711-141">Nella pagina **Notifiche** impostare le azioni che [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent deve eseguire al completamento del processo.</span><span class="sxs-lookup"><span data-stu-id="54711-141">On the **Notifications** page, set actions for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to perform when the job completes.</span></span> <span data-ttu-id="54711-142">Per ulteriori informazioni sulle opzioni disponibili in questa pagina, vedere [Proprietà processo: nuova pagina notifiche &#40;processo&#41;](job-properties-new-job-notifications-page.md).</span><span class="sxs-lookup"><span data-stu-id="54711-142">For more information on the available options on this page, see [Job Properties: New Job &#40;Notifications Page&#41;](job-properties-new-job-notifications-page.md).</span></span>  
  
9. <span data-ttu-id="54711-143">Nella pagina **Destinazioni** , gestire i server di destinazione per il processo.</span><span class="sxs-lookup"><span data-stu-id="54711-143">On the **Targets** page, manage the target servers for the job.</span></span> <span data-ttu-id="54711-144">Per ulteriori informazioni sulle opzioni disponibili in questa pagina, vedere [Proprietà processo: nuova pagina &#40;di destinazione processo&#41;](job-properties-new-job-targets-page.md).</span><span class="sxs-lookup"><span data-stu-id="54711-144">For more information on the available options on this page, see [Job Properties: New Job &#40;Targets Page&#41;](job-properties-new-job-targets-page.md).</span></span>  
  
10. <span data-ttu-id="54711-145">Al termine, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="54711-145">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="54711-146">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="54711-146">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-sql-server-agent-job"></a><span data-ttu-id="54711-147">Per creare un processo di SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="54711-147">To create a SQL Server Agent job</span></span>  
  
1.  <span data-ttu-id="54711-148">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="54711-148">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="54711-149">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="54711-149">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="54711-150">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="54711-150">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    USE msdb ;  
    GO  
    EXEC dbo.sp_add_job  
        @job_name = N'Weekly Sales Data Backup' ;  
    GO  
    EXEC sp_add_jobstep  
        @job_name = N'Weekly Sales Data Backup',  
        @step_name = N'Set database to read only',  
        @subsystem = N'TSQL',  
        @command = N'ALTER DATABASE SALES SET READ_ONLY',   
        @retry_attempts = 5,  
        @retry_interval = 5 ;  
    GO  
    EXEC dbo.sp_add_schedule  
        @schedule_name = N'RunOnce',  
        @freq_type = 1,  
        @active_start_time = 233000 ;  
    USE msdb ;  
    GO  
    EXEC sp_attach_schedule  
       @job_name = N'Weekly Sales Data Backup',  
       @schedule_name = N'RunOnce';  
    GO  
    EXEC dbo.sp_add_jobserver  
        @job_name = N'Weekly Sales Data Backup';  
    GO  
    ```  
  
 <span data-ttu-id="54711-151">Per altre informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="54711-151">For more information, see:</span></span>  
  
-   [<span data-ttu-id="54711-152">sp_add_job &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="54711-152">sp_add_job &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-job-transact-sql)  
  
-   [<span data-ttu-id="54711-153">sp_add_jobstep &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="54711-153">sp_add_jobstep &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql)  
  
-   [<span data-ttu-id="54711-154">sp_add_schedule &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="54711-154">sp_add_schedule &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-schedule-transact-sql)  
  
-   [<span data-ttu-id="54711-155">sp_attach_schedule &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="54711-155">sp_attach_schedule &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-attach-schedule-transact-sql)  
  
-   [<span data-ttu-id="54711-156">sp_add_jobserver &#40;&#41;Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="54711-156">sp_add_jobserver &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-jobserver-transact-sql)  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMOProcedure"></a><span data-ttu-id="54711-157">Utilizzo di SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="54711-157">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="54711-158">**Per creare un processo di SQL Server Agent**</span><span class="sxs-lookup"><span data-stu-id="54711-158">**To create a SQL Server Agent job**</span></span>  
  
 <span data-ttu-id="54711-159">Chiamare il metodo `Create` della classe `Job` usando un linguaggio di programmazione come Visual Basic, Visual C# o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="54711-159">Call the `Create` method of the `Job` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="54711-160">Per un codice di esempio, vedere [Pianificazione delle attività amministrative automatiche in SQL Server Agent](sql-server-agent.md).</span><span class="sxs-lookup"><span data-stu-id="54711-160">For example code, see [Scheduling Automatic Administrative Tasks in SQL Server Agent](sql-server-agent.md).</span></span>  
  
##  <a name="SSMSProc2"></a>  
