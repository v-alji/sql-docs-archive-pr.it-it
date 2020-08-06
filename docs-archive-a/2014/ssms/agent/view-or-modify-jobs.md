---
title: Visualizzare o modificare processi | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], modifying
- jobs [SQL Server Agent], viewing
- modifying jobs
- viewing jobs
- SQL Server Agent jobs, viewing
- SQL Server Agent jobs, modifying
- displaying jobs
ms.assetid: 57f649b8-190c-4304-abd7-7ca5297deab7
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5d0d731d25c20597be3ac84adfacd8973e4a51cd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714980"
---
# <a name="view-or-modify-jobs"></a><span data-ttu-id="30a8d-102">Visualizzare o modificare processi</span><span class="sxs-lookup"><span data-stu-id="30a8d-102">View or Modify Jobs</span></span>
  <span data-ttu-id="30a8d-103">È possibile visualizzare tutti i processi creati.</span><span class="sxs-lookup"><span data-stu-id="30a8d-103">You can view any job you have created.</span></span> <span data-ttu-id="30a8d-104">Dopo l'esecuzione di un processo, è inoltre possibile visualizzarne la cronologia.</span><span class="sxs-lookup"><span data-stu-id="30a8d-104">After you have run a job, you can also view its history.</span></span> <span data-ttu-id="30a8d-105">Ciò consente di verificare quando un processo è stato eseguito, lo stato dell'intero processo e lo stato di ogni relativo passaggio.</span><span class="sxs-lookup"><span data-stu-id="30a8d-105">Viewing a job's history allows you to see when the job ran, the status of the job as a whole, and the status of each job step in the job.</span></span> <span data-ttu-id="30a8d-106">È inoltre possibile verificare se in precedenza si sono verificati errori nel processo, l'ultima volta che il processo è stato completato e l'output creato a ogni esecuzione del processo.</span><span class="sxs-lookup"><span data-stu-id="30a8d-106">You can see whether the job ever failed in the past, when the job last completed successfully, and what output the job created each time the job ran.</span></span> <span data-ttu-id="30a8d-107">I membri del ruolo predefinito del server **sysadmin** possono visualizzare o modificare qualsiasi processo, indipendentemente dal proprietario.</span><span class="sxs-lookup"><span data-stu-id="30a8d-107">Members of the **sysadmin** fixed server role can view or modify any job, regardless of the owner.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="30a8d-108">Affinché sia disponibile una cronologia processo, è necessario che il processo sia stato eseguito almeno una volta.</span><span class="sxs-lookup"><span data-stu-id="30a8d-108">A job must have been executed at least one time for there to be a job history.</span></span> <span data-ttu-id="30a8d-109">È possibile limitare le dimensioni totali del log di cronologia processo e le dimensioni di ogni processo.</span><span class="sxs-lookup"><span data-stu-id="30a8d-109">You can limit the total size of the job history log and the size per job.</span></span>  
  
 <span data-ttu-id="30a8d-110">È infine possibile modificare un processo in modo da soddisfare nuovi requisiti.</span><span class="sxs-lookup"><span data-stu-id="30a8d-110">Finally, you can modify a job to meet new requirements.</span></span> <span data-ttu-id="30a8d-111">È possibile ad esempio modificare:</span><span class="sxs-lookup"><span data-stu-id="30a8d-111">You can modify:</span></span>  
  
-   <span data-ttu-id="30a8d-112">Opzioni di risposta</span><span class="sxs-lookup"><span data-stu-id="30a8d-112">Response options</span></span>  
  
-   <span data-ttu-id="30a8d-113">Pianificazioni</span><span class="sxs-lookup"><span data-stu-id="30a8d-113">Schedules</span></span>  
  
-   <span data-ttu-id="30a8d-114">Passaggi di processo</span><span class="sxs-lookup"><span data-stu-id="30a8d-114">Job steps</span></span>  
  
-   <span data-ttu-id="30a8d-115">Proprietario</span><span class="sxs-lookup"><span data-stu-id="30a8d-115">Ownership</span></span>  
  
-   <span data-ttu-id="30a8d-116">Categoria di processo</span><span class="sxs-lookup"><span data-stu-id="30a8d-116">Job category</span></span>  
  
-   <span data-ttu-id="30a8d-117">Server di destinazione (solo processi multiserver)</span><span class="sxs-lookup"><span data-stu-id="30a8d-117">Target servers (multiserver jobs only)</span></span>  
  
 <span data-ttu-id="30a8d-118">Per verificare che le modifiche ai processi multiserver siano operative, è necessario inviare le modifiche all'elenco di download, in modo da consentire ai server di destinazione di scaricare nuovamente il processo aggiornato.</span><span class="sxs-lookup"><span data-stu-id="30a8d-118">To make sure that changes to multiserver jobs take effect, you must post the changes to the download list so that target servers can download the updated job.</span></span> <span data-ttu-id="30a8d-119">Per garantire che i server di destinazione dispongano delle definizioni di processo più aggiornate, inviare un'istruzione INSERT dopo l'aggiornamento del processo multiserver, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="30a8d-119">To ensure that target servers have the most current job definitions, post an INSERT instruction after you update the multiserver job as follows:</span></span>  
  
```  
EXECUTE sp_post_msx_operation 'INSERT', 'JOB', '<job id>'  
```  
  
 <span data-ttu-id="30a8d-120">Per ulteriori informazioni, vedere [sp_purge_jobhistory &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-purge-jobhistory-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="30a8d-120">For more information, see [sp_purge_jobhistory &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-purge-jobhistory-transact-sql).</span></span>  
  
 <span data-ttu-id="30a8d-121">I membri del ruolo predefinito del server **sysadmin** possono visualizzare la definizione o la cronologia nonché modificare qualsiasi processo.</span><span class="sxs-lookup"><span data-stu-id="30a8d-121">Members of the **sysadmin** fixed server role can view the definition or history of any job, and can modify any job.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="30a8d-122">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="30a8d-122">Related Tasks</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="30a8d-123">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="30a8d-123">**Description**</span></span>|<span data-ttu-id="30a8d-124">**Argomento**</span><span class="sxs-lookup"><span data-stu-id="30a8d-124">**Topic**</span></span>|  
|<span data-ttu-id="30a8d-125">Descrive la procedura per la visualizzazione dei processi di [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="30a8d-125">Describes how to view [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent jobs.</span></span>|[<span data-ttu-id="30a8d-126">View a Job</span><span class="sxs-lookup"><span data-stu-id="30a8d-126">View a Job</span></span>](view-a-job.md)|  
|<span data-ttu-id="30a8d-127">Illustra come visualizzare il log cronologia processi di [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="30a8d-127">Describes how to view the [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent job history log.</span></span>|[<span data-ttu-id="30a8d-128">Visualizzare la cronologia processi</span><span class="sxs-lookup"><span data-stu-id="30a8d-128">View the Job History</span></span>](view-the-job-history.md)|  
|<span data-ttu-id="30a8d-129">Descrive come eliminare i contenuti del log cronologia processi di [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="30a8d-129">Describes how to delete the contents of the [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent job history log.</span></span>|[<span data-ttu-id="30a8d-130">Cancellare il contenuto del log di cronologia processi</span><span class="sxs-lookup"><span data-stu-id="30a8d-130">Clear the Job History Log</span></span>](clear-the-job-history-log.md)|  
|<span data-ttu-id="30a8d-131">Descrive come impostare le dimensioni massime per i log cronologia processi di [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="30a8d-131">Describes how to set size limits for [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent job history logs.</span></span>|[<span data-ttu-id="30a8d-132">Modificare le dimensioni del log di cronologia processi</span><span class="sxs-lookup"><span data-stu-id="30a8d-132">Resize the Job History Log</span></span>](resize-the-job-history-log.md)|  
|<span data-ttu-id="30a8d-133">Illustra la procedura per la modifica delle proprietà dei processi di [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="30a8d-133">Describes how to change the properties of [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent jobs.</span></span>|[<span data-ttu-id="30a8d-134">Modificare un processo</span><span class="sxs-lookup"><span data-stu-id="30a8d-134">Modify a Job</span></span>](modify-a-job.md)|  
  
## <a name="see-also"></a><span data-ttu-id="30a8d-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="30a8d-135">See Also</span></span>  
 [<span data-ttu-id="30a8d-136">dbo.sysjobhistory &#40;&#41;Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="30a8d-136">dbo.sysjobhistory &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-tables/dbo-sysjobhistory-transact-sql)  
  
  
