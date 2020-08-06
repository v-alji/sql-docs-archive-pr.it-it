---
title: Creare e collegare pianificazioni ai processi | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server]
- scheduling jobs [SQL Server]
- jobs [SQL Server], scheduling
- CPU [SQL Server], idle conditions
- automatic job processing
- SQL Server Agent jobs, scheduling
- idle time [SQL Server]
ms.assetid: 079c2984-0052-4a37-a2b8-4ece56e6b6b5
author: stevestein
ms.author: sstein
ms.openlocfilehash: ced47013b6552725e6350b113a3722b066016a6b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715060"
---
# <a name="create-and-attach-schedules-to-jobs"></a><span data-ttu-id="30e5c-102">Creazione e collegamento di pianificazioni ai processi</span><span class="sxs-lookup"><span data-stu-id="30e5c-102">Create and Attach Schedules to Jobs</span></span>
  <span data-ttu-id="30e5c-103">La pianificazione dei processi di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent comporta la definizione della condizione o delle condizioni che provocano l'inizio dell'esecuzione del processo senza interazione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="30e5c-103">Scheduling [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs means defining the condition or conditions that cause the job to begin running without user interaction.</span></span> <span data-ttu-id="30e5c-104">È possibile pianificare l'esecuzione automatica di un processo creando una nuova pianificazione per il processo o collegando una pianificazione esistente al processo.</span><span class="sxs-lookup"><span data-stu-id="30e5c-104">You can schedule a job to run automatically by creating a new schedule for the job, or by attaching an existing schedule to the job.</span></span>  
  
 <span data-ttu-id="30e5c-105">È possibile creare una pianificazione in due modi:</span><span class="sxs-lookup"><span data-stu-id="30e5c-105">There are two ways to create a schedule:</span></span>  
  
-   <span data-ttu-id="30e5c-106">Creare la pianificazione durante la creazione di un processo.</span><span class="sxs-lookup"><span data-stu-id="30e5c-106">Create the schedule while you are creating a job.</span></span>  
  
-   <span data-ttu-id="30e5c-107">Creare la pianificazione in Esplora oggetti.</span><span class="sxs-lookup"><span data-stu-id="30e5c-107">Create the schedule in Object Explorer.</span></span>  
  
 <span data-ttu-id="30e5c-108">Dopo la creazione, la pianificazione può essere collegata a più processi anche se è stata creata per un processo specifico.</span><span class="sxs-lookup"><span data-stu-id="30e5c-108">After a schedule has been created, you can attach that schedule to multiple jobs, even if the schedule was created for a specific job.</span></span> <span data-ttu-id="30e5c-109">È anche possibile scollegare le pianificazioni dai processi.</span><span class="sxs-lookup"><span data-stu-id="30e5c-109">You can also detach schedules from jobs.</span></span>  
  
 <span data-ttu-id="30e5c-110">Una pianificazione può essere basata sul tempo o su un evento.</span><span class="sxs-lookup"><span data-stu-id="30e5c-110">A schedule can be based upon time or an event.</span></span> <span data-ttu-id="30e5c-111">Ad esempio, è possibile pianificare l'esecuzione di un processo nei momenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="30e5c-111">For example, you can schedule a job to run at the following times:</span></span>  
  
-   <span data-ttu-id="30e5c-112">All'avvio di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="30e5c-112">Whenever [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent starts.</span></span>  
  
-   <span data-ttu-id="30e5c-113">Quando l'utilizzo della CPU del computer corrisponde al livello di inattività.</span><span class="sxs-lookup"><span data-stu-id="30e5c-113">Whenever CPU utilization of the computer is at a level you have defined as idle.</span></span>  
  
-   <span data-ttu-id="30e5c-114">Una sola volta in corrispondenza di una data e un'ora specifiche.</span><span class="sxs-lookup"><span data-stu-id="30e5c-114">One time, at a specific date and time.</span></span>  
  
-   <span data-ttu-id="30e5c-115">In base a una pianificazione ricorrente.</span><span class="sxs-lookup"><span data-stu-id="30e5c-115">On a recurring schedule.</span></span>  
  
 <span data-ttu-id="30e5c-116">In alternativa alle pianificazioni di processi, è possibile creare un avviso che risponda a un evento tramite l'esecuzione di un processo.</span><span class="sxs-lookup"><span data-stu-id="30e5c-116">As an alternative to job schedules, you can also create an alert that responds to an event by running a job.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="30e5c-117">È possibile eseguire una sola istanza del processo alla volta.</span><span class="sxs-lookup"><span data-stu-id="30e5c-117">Only one instance of the job can be run at a time.</span></span> <span data-ttu-id="30e5c-118">Se si tenta di eseguire manualmente un processo mentre questo viene eseguito in base alla pianificazione, la richiesta di esecuzione verrà rifiutata da Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="30e5c-118">If you try to run a job manually while it is running as scheduled, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent refuses the request.</span></span>  
  
 <span data-ttu-id="30e5c-119">Per impedire l'esecuzione di un processo pianificato, è necessario eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="30e5c-119">To prevent a scheduled job from running, you must do one of the following:</span></span>  
  
-   <span data-ttu-id="30e5c-120">Disabilitare la pianificazione.</span><span class="sxs-lookup"><span data-stu-id="30e5c-120">Disable the schedule.</span></span>  
  
-   <span data-ttu-id="30e5c-121">Disabilitare il processo.</span><span class="sxs-lookup"><span data-stu-id="30e5c-121">Disable the job.</span></span>  
  
-   <span data-ttu-id="30e5c-122">Scollegare la pianificazione dal processo.</span><span class="sxs-lookup"><span data-stu-id="30e5c-122">Detach the schedule from the job.</span></span>  
  
-   <span data-ttu-id="30e5c-123">Arrestare il servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="30e5c-123">Stop the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service.</span></span>  
  
-   <span data-ttu-id="30e5c-124">Eliminare la pianificazione.</span><span class="sxs-lookup"><span data-stu-id="30e5c-124">Delete the schedule.</span></span>  
  
 <span data-ttu-id="30e5c-125">Se la pianificazione non è attivata, il processo potrà essere eseguito comunque in risposta a un avviso o quando viene eseguito manualmente da un utente.</span><span class="sxs-lookup"><span data-stu-id="30e5c-125">If the schedule is not enabled, the job can still run in response to an alert or when a user runs the job manually.</span></span> <span data-ttu-id="30e5c-126">Se una pianificazione di processo non è attivata, sarà disattivata per tutti i processi che la utilizzano.</span><span class="sxs-lookup"><span data-stu-id="30e5c-126">When a job schedule is not enabled, the schedule is not enabled for any job that uses the schedule.</span></span>  
  
 <span data-ttu-id="30e5c-127">È necessario riattivare esplicitamente una pianificazione disabilitata.</span><span class="sxs-lookup"><span data-stu-id="30e5c-127">You must explicitly re-enable a schedule that has been disabled.</span></span> <span data-ttu-id="30e5c-128">La modifica della pianificazione non consente di riabilitarla automaticamente.</span><span class="sxs-lookup"><span data-stu-id="30e5c-128">Editing the schedule does not automatically re-enable the schedule.</span></span>  
  
## <a name="scheduling-start-dates"></a><span data-ttu-id="30e5c-129">Date di inizio della pianificazione</span><span class="sxs-lookup"><span data-stu-id="30e5c-129">Scheduling Start Dates</span></span>  
 <span data-ttu-id="30e5c-130">La data di inizio di una pianificazione deve essere maggiore o uguale a 19900101.</span><span class="sxs-lookup"><span data-stu-id="30e5c-130">The start date of a schedule must be greater than or equal to 19900101.</span></span>  
  
 <span data-ttu-id="30e5c-131">Quando si collega una pianificazione a un processo, è necessario controllare la data di inizio utilizzata dalla pianificazione per eseguire il processo la prima volta.</span><span class="sxs-lookup"><span data-stu-id="30e5c-131">When you are attaching a schedule to a job, you should review the start date that the schedule uses to run the job for the first time.</span></span> <span data-ttu-id="30e5c-132">La data di inizio dipende dal giorno e dall'ora in cui la pianificazione viene collegata al processo.</span><span class="sxs-lookup"><span data-stu-id="30e5c-132">The start date depends upon the day and time when you attach the schedule to the job.</span></span> <span data-ttu-id="30e5c-133">Ad esempio, se si crea una pianificazione che viene eseguita ogni due lunedì alle 8.00</span><span class="sxs-lookup"><span data-stu-id="30e5c-133">For example, you create a schedule that runs every other Monday at 8:00 A.M.</span></span> <span data-ttu-id="30e5c-134">Se si crea un processo alle ore 10.00</span><span class="sxs-lookup"><span data-stu-id="30e5c-134">If you create a job at 10:00 A.M.</span></span> <span data-ttu-id="30e5c-135">di lunedì 3 marzo 2008, la data di inizio della pianificazione sarà lunedì 17 marzo 2008.</span><span class="sxs-lookup"><span data-stu-id="30e5c-135">on Monday, March 3, 2008, the schedule start date is Monday, March 17, 2008.</span></span> <span data-ttu-id="30e5c-136">Se si crea un altro processo martedì 4 marzo 2008, la data di inizio della pianificazione è lunedì 10 marzo 2008.</span><span class="sxs-lookup"><span data-stu-id="30e5c-136">If you create another job on Tuesday, March 4, 2008, the schedule start date is Monday, March 10, 2008.</span></span>  
  
 <span data-ttu-id="30e5c-137">È possibile modificare la data di inizio della pianificazione dopo avere collegato la pianificazione a un processo.</span><span class="sxs-lookup"><span data-stu-id="30e5c-137">You can change the schedule start date after you attach the schedule to a job.</span></span>  
  
## <a name="cpu-idle-schedules"></a><span data-ttu-id="30e5c-138">Pianificazioni con CPU inattiva</span><span class="sxs-lookup"><span data-stu-id="30e5c-138">CPU Idle Schedules</span></span>  
 <span data-ttu-id="30e5c-139">Per ottimizzare l'utilizzo della CPU, è possibile definire una condizione di inattività della CPU per Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="30e5c-139">To maximize CPU resources, you can define a CPU idle condition for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="30e5c-140">Tale impostazione consente all'agente di eseguire i processi nei momenti di minor carico di lavoro della CPU.</span><span class="sxs-lookup"><span data-stu-id="30e5c-140">Agent uses the CPU idle condition setting to determine the best time to run jobs.</span></span> <span data-ttu-id="30e5c-141">Ad esempio è possibile pianificare un processo di ricompilazione degli indici quando la CPU è in stato inattivo o durante i periodi di produzione ridotta.</span><span class="sxs-lookup"><span data-stu-id="30e5c-141">For example, you can schedule a job to rebuild indexes during CPU idle time and slow production periods.</span></span>  
  
 <span data-ttu-id="30e5c-142">Prima di definire i processi da eseguire durante l'inattività della CPU, è necessario determinare il carico di lavoro della CPU durante l'elaborazione normale.</span><span class="sxs-lookup"><span data-stu-id="30e5c-142">Before you define jobs to run during CPU idle time, determine the load on the CPU during normal processing.</span></span> <span data-ttu-id="30e5c-143">A tale scopo, utilizzare [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] o Performance Monitor per monitorare il traffico nel server e raccogliere statistiche.</span><span class="sxs-lookup"><span data-stu-id="30e5c-143">To do this, use [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] or Performance Monitor to monitor server traffic and collect statistics.</span></span> <span data-ttu-id="30e5c-144">Le informazioni raccolte saranno utili per la definizione di una percentuale di utilizzo corrispondente allo stato di inattività della CPU e della durata di tale stato.</span><span class="sxs-lookup"><span data-stu-id="30e5c-144">You can then use the information you gather to set the CPU idle time percentage and duration.</span></span>  
  
 <span data-ttu-id="30e5c-145">Definire la condizione di inattività come valore percentuale. L'utilizzo della CPU dovrà rimanere inferiore a tale valore per un periodo di tempo specificato.</span><span class="sxs-lookup"><span data-stu-id="30e5c-145">Define the CPU idle condition as a percentage below which CPU usage must remain for a specified time.</span></span> <span data-ttu-id="30e5c-146">Definire quindi il periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="30e5c-146">Next, set the amount of time.</span></span> <span data-ttu-id="30e5c-147">Quando l'utilizzo della CPU è inferiore alla percentuale specificata per il periodo di tempo specificato, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent avvia tutti i processi pianificati per l'esecuzione con CPU inattiva.</span><span class="sxs-lookup"><span data-stu-id="30e5c-147">When the CPU usage is below the specified percentage for the specified amount of time, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent starts all jobs that have a CPU idle time schedule.</span></span> <span data-ttu-id="30e5c-148">Per ulteriori informazioni sull'utilizzo [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] di o Performance Monitor per il monitoraggio dell'utilizzo della CPU, vedere [monitorare l'utilizzo della](../../relational-databases/performance-monitor/monitor-cpu-usage.md)CPU.</span><span class="sxs-lookup"><span data-stu-id="30e5c-148">For more information on using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] or Performance Monitor to monitor CPU usage, see [Monitor CPU Usage](../../relational-databases/performance-monitor/monitor-cpu-usage.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="30e5c-149">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="30e5c-149">Related Tasks</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="30e5c-150">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="30e5c-150">**Description**</span></span>|<span data-ttu-id="30e5c-151">**Argomento**</span><span class="sxs-lookup"><span data-stu-id="30e5c-151">**Topic**</span></span>|  
|<span data-ttu-id="30e5c-152">Viene descritto come creare una pianificazione per un processo di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="30e5c-152">Describes how to create a schedule for a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job.</span></span>|[<span data-ttu-id="30e5c-153">Creare una pianificazione</span><span class="sxs-lookup"><span data-stu-id="30e5c-153">Create a Schedule</span></span>](create-a-schedule.md)|  
|<span data-ttu-id="30e5c-154">Viene descritto come pianificare un processo di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="30e5c-154">Describes how to schedule a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job.</span></span>|[<span data-ttu-id="30e5c-155">Pianificare un processo</span><span class="sxs-lookup"><span data-stu-id="30e5c-155">Schedule a Job</span></span>](schedule-a-job.md)|  
|<span data-ttu-id="30e5c-156">Viene illustrato come definire la condizione di inattività della CPU per il server.</span><span class="sxs-lookup"><span data-stu-id="30e5c-156">Explains how to define the CPU idle condition for your server.</span></span>|[<span data-ttu-id="30e5c-157">Impostare tempo e durata di inattività della CPU &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="30e5c-157">Set CPU Idle Time and Duration &#40;SQL Server Management Studio&#41;</span></span>](set-cpu-idle-time-and-duration-sql-server-management-studio.md)|  
  
## <a name="see-also"></a><span data-ttu-id="30e5c-158">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="30e5c-158">See Also</span></span>  
 <span data-ttu-id="30e5c-159">[sp_help_jobschedule &#40;&#41;Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-help-jobschedule-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="30e5c-159">[sp_help_jobschedule &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-jobschedule-transact-sql) </span></span>  
 [<span data-ttu-id="30e5c-160">dbo.sysJobSchedules &#40;&#41;Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="30e5c-160">dbo.sysjobschedules &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-tables/dbo-sysjobschedules-transact-sql)  
  
  
