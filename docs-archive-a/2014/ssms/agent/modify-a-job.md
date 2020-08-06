---
title: Modificare un processo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], modifying
- modifying jobs
- SQL Server Agent jobs, modifying
ms.assetid: dd5e5f20-20c4-4ab9-a19a-db87577dcd43
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0d25830ad119a1f5f344a4dcf318c35bee5f86ca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627052"
---
# <a name="modify-a-job"></a><span data-ttu-id="e422f-102">Modificare un processo</span><span class="sxs-lookup"><span data-stu-id="e422f-102">Modify a Job</span></span>
  <span data-ttu-id="e422f-103">In questo argomento viene descritto come modificare le proprietà dei [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] processi di Agent in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , [!INCLUDE[tsql](../../includes/tsql-md.md)] o SQL Server Management Objects.</span><span class="sxs-lookup"><span data-stu-id="e422f-103">This topic describes how to change the properties of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Management Objects.</span></span>  
  
 <span data-ttu-id="e422f-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="e422f-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="e422f-105">**Prima di iniziare:** ,</span><span class="sxs-lookup"><span data-stu-id="e422f-105">**Before you begin:** ,</span></span>  
  
     [<span data-ttu-id="e422f-106">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="e422f-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="e422f-107">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="e422f-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="e422f-108">**Per modificare un processo tramite:**</span><span class="sxs-lookup"><span data-stu-id="e422f-108">**To modify a job, using:**</span></span>  
  
     [<span data-ttu-id="e422f-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e422f-109">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="e422f-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e422f-110">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="e422f-111">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="e422f-111">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="e422f-112">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="e422f-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="e422f-113">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="e422f-113">Limitations and Restrictions</span></span>  
 <span data-ttu-id="e422f-114">Un processo master di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent non può essere destinato sia a server locali sia a server remoti.</span><span class="sxs-lookup"><span data-stu-id="e422f-114">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent master job cannot be targeted at both local and remote servers.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="e422f-115">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="e422f-115">Security</span></span>  
 <span data-ttu-id="e422f-116">È possibile modificare solo i processi di cui si è proprietari, a meno che non si appartenga al ruolo predefinito del server **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="e422f-116">Unless you are a member of the **sysadmin** fixed server role, you can only modify jobs that you own.</span></span> <span data-ttu-id="e422f-117">Per informazioni dettagliate, vedere [Implementazione della sicurezza di SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="e422f-117">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="e422f-118">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e422f-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-a-job"></a><span data-ttu-id="e422f-119">Per modificare un processo</span><span class="sxs-lookup"><span data-stu-id="e422f-119">To modify a job</span></span>  
  
1.  <span data-ttu-id="e422f-120">In **Esplora oggetti** connettersi a un'istanza del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , quindi espandere l'istanza.</span><span class="sxs-lookup"><span data-stu-id="e422f-120">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="e422f-121">Espandere il nodo **SQL Server Agent**e il nodo **Processi**; fare clic con il pulsante destro del mouse sul processo che si vuole modificare e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="e422f-121">Expand **SQL Server Agent**, expand **Jobs**, right-click the job you want to modify, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="e422f-122">Nella finestra di dialogo **Proprietà processo** aggiornare le proprietà, i passaggi, la pianificazione e le notifiche del processo nelle schede corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="e422f-122">In the **Job Properties** dialog box, update the job's properties, steps, schedule, alerts, and notifications using the corresponding pages.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="e422f-123">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e422f-123">Using Transact-SQL</span></span>  
  
#### <a name="to-modify-a-job"></a><span data-ttu-id="e422f-124">Per modificare un processo</span><span class="sxs-lookup"><span data-stu-id="e422f-124">To modify a job</span></span>  
  
1.  <span data-ttu-id="e422f-125">In Esplora oggetti connettersi a un'istanza del motore di database ed espanderla.</span><span class="sxs-lookup"><span data-stu-id="e422f-125">In Object Explorer, connect to an instance of the Database Engine, and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="e422f-126">Sulla barra degli strumenti fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="e422f-126">On the toolbar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="e422f-127">Nella finestra Query utilizzare le stored procedure di sistema seguenti per modificare un processo.</span><span class="sxs-lookup"><span data-stu-id="e422f-127">In the query window, use the following system stored procedures to modify a job.</span></span>  
  
    -   <span data-ttu-id="e422f-128">Eseguire [sp_update_job &#40;&#41;Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-update-job-transact-sql) per modificare gli attributi di un processo.</span><span class="sxs-lookup"><span data-stu-id="e422f-128">Execute [sp_update_job &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-job-transact-sql) to change the attributes of a job.</span></span>  
  
    -   <span data-ttu-id="e422f-129">Eseguire [sp_update_schedule &#40;&#41;Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-update-schedule-transact-sql) per modificare i dettagli della pianificazione per la definizione di un processo.</span><span class="sxs-lookup"><span data-stu-id="e422f-129">Execute [sp_update_schedule &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-schedule-transact-sql) to change the scheduling details for a job definition.</span></span>  
  
    -   <span data-ttu-id="e422f-130">Eseguire [sp_add_jobstep &#40;&#41;Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql) per aggiungere nuovi passaggi di processo.</span><span class="sxs-lookup"><span data-stu-id="e422f-130">Execute [sp_add_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql) to add new job steps.</span></span>  
  
    -   <span data-ttu-id="e422f-131">Eseguire [sp_update_jobstep &#40;&#41;Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-update-jobstep-transact-sql) per modificare i passaggi di processo pre-esistenti.</span><span class="sxs-lookup"><span data-stu-id="e422f-131">Execute [sp_update_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-jobstep-transact-sql) to change pre-existing job steps.</span></span>  
  
    -   <span data-ttu-id="e422f-132">Eseguire [sp_delete_jobstep &#40;&#41;Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-delete-jobstep-transact-sql) per rimuovere un passaggio di processo da un processo.</span><span class="sxs-lookup"><span data-stu-id="e422f-132">Execute [sp_delete_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-jobstep-transact-sql) to remove a job step from a job.</span></span>  
  
    -   <span data-ttu-id="e422f-133">Stored procedure aggiuntive per modificare qualsiasi processo master di SQL Server Agent:</span><span class="sxs-lookup"><span data-stu-id="e422f-133">Additional stored procedures to modify any SQL Server Agent master job:</span></span>  
  
        -   <span data-ttu-id="e422f-134">Eseguire [sp_delete_jobserver &#40;&#41;Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-delete-jobserver-transact-sql) per eliminare un server attualmente associato a un processo.</span><span class="sxs-lookup"><span data-stu-id="e422f-134">Execute [sp_delete_jobserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-jobserver-transact-sql) to delete a server currently associated with a job.</span></span>  
  
        -   <span data-ttu-id="e422f-135">Eseguire [sp_add_jobserver &#40;&#41;Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-add-jobserver-transact-sql) per associare un server al processo corrente.</span><span class="sxs-lookup"><span data-stu-id="e422f-135">Execute [sp_add_jobserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobserver-transact-sql) to associate a server with the current job.</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="e422f-136">Utilizzo di SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="e422f-136">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="e422f-137">**Per modificare un processo**</span><span class="sxs-lookup"><span data-stu-id="e422f-137">**To modify a job**</span></span>  
  
 <span data-ttu-id="e422f-138">Usare la classe `Job` tramite un linguaggio di programmazione scelto come Visual Basic, Visual C# o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e422f-138">Use the `Job` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="e422f-139">Per altre informazioni, vedere [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span><span class="sxs-lookup"><span data-stu-id="e422f-139">For more information, see [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span></span>  
  
  
