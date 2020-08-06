---
title: Gestire i processi in un'organizzazione | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- multiserver job management [SQL Server]
- jobs [SQL Server Agent], modifying
- modifying jobs
- SQL Server Agent jobs, modifying
- target servers [SQL Server], job changes
ms.assetid: 4fe7f6c6-f89b-4430-979c-4994a5dcf7a6
author: stevestein
ms.author: sstein
ms.openlocfilehash: 385435302b2e987c86afb17eaebf90e91bc93e56
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627055"
---
# <a name="manage-jobs-across-an-enterprise"></a><span data-ttu-id="38fa8-102">Gestire i processi in un'azienda</span><span class="sxs-lookup"><span data-stu-id="38fa8-102">Manage Jobs Across an Enterprise</span></span>
  <span data-ttu-id="38fa8-103">Se si apportano modifiche alle definizioni di processi multiserver al di fuori di [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , è necessario inviare le modifiche all'elenco di download in modo che i server di destinazione possano scaricare nuovamente il processo aggiornato.</span><span class="sxs-lookup"><span data-stu-id="38fa8-103">If you make changes to multiserver job definitions outside [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], you must post the changes to the download list so that target servers can download the updated job again.</span></span> <span data-ttu-id="38fa8-104">Per garantire che i server di destinazione dispongano delle definizioni dei processi più aggiornate, inviare un'istruzione INSERT dopo l'aggiornamento del processo multiserver:</span><span class="sxs-lookup"><span data-stu-id="38fa8-104">To ensure that target servers have current job definitions, post an INSERT instruction after you update the multiserver job, as follows:</span></span>  
  
```  
EXECUTE sp_post_msx_operation 'INSERT', 'JOB', '<job id>'  
```  
  
 <span data-ttu-id="38fa8-105">Per notificare ai server di destinazione che un processo multiserver è stato modificato, è necessario richiamare il comando precedente dopo avere utilizzato una qualsiasi delle procedure seguenti:</span><span class="sxs-lookup"><span data-stu-id="38fa8-105">To notify target servers that a multiserver job has been modified, you must invoke the preceding command after using any of the following procedures:</span></span>  
  
-   [<span data-ttu-id="38fa8-106">sp_add_jobstep (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="38fa8-106">sp_add_jobstep (Transact-SQL)</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql)  
  
-   [<span data-ttu-id="38fa8-107">sp_update_jobstep (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="38fa8-107">sp_update_jobstep (Transact-SQL)</span></span>](/sql/relational-databases/system-stored-procedures/sp-update-jobstep-transact-sql)  
  
-   [<span data-ttu-id="38fa8-108">sp_delete_jobstep (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="38fa8-108">sp_delete_jobstep (Transact-SQL)</span></span>](/sql/relational-databases/system-stored-procedures/sp-delete-jobstep-transact-sql)  
  
-   [<span data-ttu-id="38fa8-109">sp_attach_schedule &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="38fa8-109">sp_attach_schedule &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-attach-schedule-transact-sql)  
  
-   [<span data-ttu-id="38fa8-110">sp_detach_schedule &#40;&#41;Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="38fa8-110">sp_detach_schedule &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-detach-schedule-transact-sql)  
  
    > [!NOTE]  
    >  <span data-ttu-id="38fa8-111">Non è necessario chiamare **sp_post_msx_operation** dopo aver chiamato **sp_update_job** o **sp_delete_job**, in quanto tali stored procedure inviano automaticamente le modifiche necessarie all'elenco di download.</span><span class="sxs-lookup"><span data-stu-id="38fa8-111">It is not necessary to call **sp_post_msx_operation** after you call **sp_update_job** or **sp_delete_job**, because these stored procedures post the required changes to the download list automatically.</span></span>  
  
 <span data-ttu-id="38fa8-112">Di seguito sono indicate le operazioni comuni per la gestione di processi in un'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="38fa8-112">The following are common tasks for managing jobs across an enterprise:</span></span>  
  
 <span data-ttu-id="38fa8-113">**Per controllare lo stato di un server di destinazione**</span><span class="sxs-lookup"><span data-stu-id="38fa8-113">**To check the status of a target server**</span></span>  
  
-   [<span data-ttu-id="38fa8-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="38fa8-114">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-help-targetserver-transact-sql)  
  
-   [<span data-ttu-id="38fa8-115">Oggetti SMO (SQL Server Management Objects)</span><span class="sxs-lookup"><span data-stu-id="38fa8-115">SQL Server Management Objects (SMO)</span></span>](../../relational-databases/server-management-objects-smo/sql-server-management-objects-smo-programming-guide.md)  
  
 <span data-ttu-id="38fa8-116">**Per modificare i server di destinazione per un processo**</span><span class="sxs-lookup"><span data-stu-id="38fa8-116">**To change the target servers for a job**</span></span>  
  
-   [<span data-ttu-id="38fa8-117">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="38fa8-117">SQL Server Management Studio</span></span>](modify-the-target-servers-for-a-job.md)  
  
-   [<span data-ttu-id="38fa8-118">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="38fa8-118">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-jobserver-transact-sql)  
  
-   [<span data-ttu-id="38fa8-119">Oggetti SMO (SQL Server Management Objects)</span><span class="sxs-lookup"><span data-stu-id="38fa8-119">SQL Server Management Objects (SMO)</span></span>](../../relational-databases/server-management-objects-smo/sql-server-management-objects-smo-programming-guide.md)  
  
 <span data-ttu-id="38fa8-120">**Per modificare la posizione di un server di destinazione**</span><span class="sxs-lookup"><span data-stu-id="38fa8-120">**To change the location of a target server**</span></span>  
  
-   [<span data-ttu-id="38fa8-121">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="38fa8-121">SQL Server Management Studio</span></span>](../sql-server-management-studio-ssms.md)  
  
-   [<span data-ttu-id="38fa8-122">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="38fa8-122">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-msx-enlist-transact-sql)  
  
-   [<span data-ttu-id="38fa8-123">Oggetti SMO (SQL Server Management Objects)</span><span class="sxs-lookup"><span data-stu-id="38fa8-123">SQL Server Management Objects (SMO)</span></span>](../../relational-databases/server-management-objects-smo/sql-server-management-objects-smo-programming-guide.md)  
  
 <span data-ttu-id="38fa8-124">**Per sincronizzare gli orologi dei server di destinazione**</span><span class="sxs-lookup"><span data-stu-id="38fa8-124">**To synchronize target server clocks**</span></span>  
  
-   [<span data-ttu-id="38fa8-125">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="38fa8-125">SQL Server Management Studio</span></span>](synchronize-target-server-clocks-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="38fa8-126">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="38fa8-126">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-resync-targetserver-transact-sql)  
  
 <span data-ttu-id="38fa8-127">**Per forzare un server di destinazione a eseguire il polling del server master**</span><span class="sxs-lookup"><span data-stu-id="38fa8-127">**To force a target server to poll the master server**</span></span>  
  
-   [<span data-ttu-id="38fa8-128">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="38fa8-128">SQL Server Management Studio</span></span>](force-a-target-server-to-poll-the-master-server.md)  
  
-   [<span data-ttu-id="38fa8-129">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="38fa8-129">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-post-msx-operation-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="38fa8-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="38fa8-130">See Also</span></span>  
 [<span data-ttu-id="38fa8-131">Gestione di eventi</span><span class="sxs-lookup"><span data-stu-id="38fa8-131">Manage Events</span></span>](manage-events.md)  
  
  
