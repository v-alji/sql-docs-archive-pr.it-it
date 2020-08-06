---
title: Monitorare le attività del processo | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, monitoring
- jobs [SQL Server Agent], monitoring
- monitoring [SQL Server], jobs
- activity monitoring [SQL Server Agent]
- monitoring [SQL Server], SQL Server Agent
- monitoring [SQL Server Agent]
- SQL Server Agent Job Activity Monitor
- SQL Server Agent jobs, monitoring
- performance [SQL Server], jobs
- current activity
ms.assetid: 71cb432b-631d-4b8b-9965-e731b3d8266d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5088e029e90b4556c1559f8c948e8a8734762749
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627040"
---
# <a name="monitor-job-activity"></a><span data-ttu-id="17768-102">Monitoraggio delle attività del processo</span><span class="sxs-lookup"><span data-stu-id="17768-102">Monitor Job Activity</span></span>
  <span data-ttu-id="17768-103">Per eseguire il monitoraggio dell'attività corrente di tutti i processi definiti in un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], è possibile utilizzare Monitoraggio attività processi di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="17768-103">You can monitor the current activity of all defined jobs on an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent Job Activity Monitor.</span></span>  
  
## <a name="sql-server-agent-sessions"></a><span data-ttu-id="17768-104">Sessioni di SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="17768-104">SQL Server Agent Sessions</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="17768-105">Agent crea una nuova sessione ogni volta che viene avviato.</span><span class="sxs-lookup"><span data-stu-id="17768-105">Agent creates a new session each time the service starts.</span></span> <span data-ttu-id="17768-106">Quando viene creata una nuova sessione, la tabella **sysjobactivity** del database **msdb** viene popolata con tutti i processi esistenti definiti.</span><span class="sxs-lookup"><span data-stu-id="17768-106">When a new session is created, the **sysjobactivity** table in the **msdb** database is populated with all the existing defined jobs.</span></span> <span data-ttu-id="17768-107">Al riavvio di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, nella tabella viene mantenuta l'ultima attività relativa ai processi.</span><span class="sxs-lookup"><span data-stu-id="17768-107">This table preserves the last activity for jobs when [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent is restarted.</span></span> <span data-ttu-id="17768-108">Ogni sessione registra l'attività dei processi normale di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, dall'inizio al termine del processo.</span><span class="sxs-lookup"><span data-stu-id="17768-108">Each session records [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent normal job activity from the start of the job to its finish.</span></span> <span data-ttu-id="17768-109">Le informazioni relative alle sessioni sono archiviate nella tabella **syssessions** del database **msdb** .</span><span class="sxs-lookup"><span data-stu-id="17768-109">Information about these sessions is stored in the **syssessions** table of the **msdb** database.</span></span>  
  
## <a name="job-activity-monitor"></a><span data-ttu-id="17768-110">Monitoraggio attività processi</span><span class="sxs-lookup"><span data-stu-id="17768-110">Job Activity Monitor</span></span>  
 <span data-ttu-id="17768-111">Monitoraggio attività processi consente di visualizzare la tabella **sysjobactivity** tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="17768-111">The Job Activity Monitor allows you to view the **sysjobactivity** table by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="17768-112">È possibile visualizzare tutti i processi del server oppure definire filtri che consentono di limitare il numero dei processi visualizzati.</span><span class="sxs-lookup"><span data-stu-id="17768-112">You can view all jobs on the server, or you can define filters to limit the number of jobs displayed.</span></span> <span data-ttu-id="17768-113">È inoltre possibile ordinare le informazioni relative ai processi facendo clic su un'intestazione di colonna nella griglia di **Attività processi agente** .</span><span class="sxs-lookup"><span data-stu-id="17768-113">You can also sort the job information by clicking on a column heading in the **Agent Job Activity** grid.</span></span> <span data-ttu-id="17768-114">Ad esempio, se si seleziona l'intestazione di colonna **Ultima esecuzione** , i processi verranno visualizzati nell'ordine in cui sono stati eseguiti l'ultima volta.</span><span class="sxs-lookup"><span data-stu-id="17768-114">For example, when you select the **Last Run** column heading, you can view the jobs in the order that they were last run.</span></span> <span data-ttu-id="17768-115">Se si fa di nuovo clic sull'intestazione di colonna, i processi verranno ordinati in ordine crescente o decrescente in base alla data dell'ultima esecuzione.</span><span class="sxs-lookup"><span data-stu-id="17768-115">Clicking the column heading again toggles the jobs in ascending and descending order based on their last run date.</span></span>  
  
 <span data-ttu-id="17768-116">Tramite Monitoraggio attività processi è possibile eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="17768-116">Using the Job Activity Monitor you can perform the following tasks:</span></span>  
  
-   <span data-ttu-id="17768-117">Avviare e arrestare i processi.</span><span class="sxs-lookup"><span data-stu-id="17768-117">Start and stop jobs.</span></span>  
  
-   <span data-ttu-id="17768-118">Visualizzare le proprietà dei processi.</span><span class="sxs-lookup"><span data-stu-id="17768-118">View job properties.</span></span>  
  
-   <span data-ttu-id="17768-119">Visualizzare la cronologia di un processo specifico.</span><span class="sxs-lookup"><span data-stu-id="17768-119">View the history for a specific job.</span></span>  
  
-   <span data-ttu-id="17768-120">Aggiornare manualmente le informazioni contenute nella griglia di **Attività processi agente** oppure impostare un intervallo di aggiornamento automatico facendo clic su **Visualizza impostazioni di aggiornamento**.</span><span class="sxs-lookup"><span data-stu-id="17768-120">Refresh the information in the **Agent Job Activity** grid manually or set an automatic refresh interval by clicking **View refresh settings**.</span></span>  
  
 <span data-ttu-id="17768-121">Monitoraggio attività processi consente di verificare quali processi sono stati pianificati per l'esecuzione, gli ultimi risultati dei processi eseguiti durante la sessione corrente e quali processi sono in esecuzione o sono inattivi.</span><span class="sxs-lookup"><span data-stu-id="17768-121">Use the Job Activity Monitor when you want to find out what jobs are scheduled to run, the last outcome of jobs that have run during the current session, and to find out which jobs are currently running or idle.</span></span> <span data-ttu-id="17768-122">Se il servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent viene interrotto in modo imprevisto, è possibile individuare i processi che erano in esecuzione controllando la sessione precedente di Monitoraggio attività processi.</span><span class="sxs-lookup"><span data-stu-id="17768-122">If the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service fails unexpectedly, you can determine which jobs were in the middle of being executed by looking at the previous session in the Job Activity Monitor.</span></span>  
  
 <span data-ttu-id="17768-123">Per aprire Monitoraggio attività processi, espandere **SQL Server Agent** in Esplora oggetti di [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] , fare clic con il pulsante destro del mouse su **Monitoraggio attività processi**e scegliere **Visualizza attività processi**.</span><span class="sxs-lookup"><span data-stu-id="17768-123">To open the Job Activity Monitor, expand **SQL Server Agent** in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] Object Explorer, right-click **Job Activity Monitor**, and click **View Job Activity**.</span></span>  
  
 <span data-ttu-id="17768-124">Per visualizzare l'attività dei processi della sessione corrente è inoltre possibile usare la stored procedure **sp_help_jobactivity**.</span><span class="sxs-lookup"><span data-stu-id="17768-124">You can also view job activity for the current session by using the stored procedure **sp_help_jobactivity**.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="17768-125">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="17768-125">Related Tasks</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="17768-126">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="17768-126">**Description**</span></span>|<span data-ttu-id="17768-127">**Argomento**</span><span class="sxs-lookup"><span data-stu-id="17768-127">**Topic**</span></span>|  
|<span data-ttu-id="17768-128">Viene illustrato come visualizzare lo stato di runtime dei processi di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="17768-128">Describes how to view the runtime state of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs.</span></span>|[<span data-ttu-id="17768-129">Visualizza attività processi</span><span class="sxs-lookup"><span data-stu-id="17768-129">View Job Activity</span></span>](view-job-activity.md)|  
  
## <a name="see-also"></a><span data-ttu-id="17768-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="17768-130">See Also</span></span>  
 <span data-ttu-id="17768-131">[Visualizza attività processi](view-job-activity.md) </span><span class="sxs-lookup"><span data-stu-id="17768-131">[View Job Activity](view-job-activity.md) </span></span>  
 <span data-ttu-id="17768-132">[dbo.sysjobactivity &#40;&#41;Transact-SQL](/sql/relational-databases/system-tables/dbo-sysjobactivity-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="17768-132">[dbo.sysjobactivity &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/dbo-sysjobactivity-transact-sql) </span></span>  
 <span data-ttu-id="17768-133">[Sessioni didbo.sys&#40;&#41;Transact-SQL](/sql/relational-databases/system-tables/dbo-syssessions-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="17768-133">[dbo.syssessions &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/dbo-syssessions-transact-sql) </span></span>  
 [<span data-ttu-id="17768-134">sp_help_jobactivity &#40;&#41;Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="17768-134">sp_help_jobactivity &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-help-jobactivity-transact-sql)  
  
  
