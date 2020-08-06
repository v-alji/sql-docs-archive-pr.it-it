---
title: Assegnare ad altri la proprietà di un processo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], owners
- owners [SQL Server], jobs
- SQL Server Agent jobs, owners
ms.assetid: 2ded5e9c-4251-4fb1-a047-99f13d150b61
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2cf03fdc9031ce9761125d95619438837f2959bb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623714"
---
# <a name="give-others-ownership-of-a-job"></a><span data-ttu-id="cb541-102">Give Others Ownership of a Job</span><span class="sxs-lookup"><span data-stu-id="cb541-102">Give Others Ownership of a Job</span></span>
  <span data-ttu-id="cb541-103">In questo argomento viene descritto come riassegnare la proprietà dei [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] processi di Agent a un altro utente.</span><span class="sxs-lookup"><span data-stu-id="cb541-103">This topic describes how to reassign ownership of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs to another user.</span></span>  
  
-   <span data-ttu-id="cb541-104">**Prima di iniziare:**  [Limitazioni e restrizioni](#Restrictions), [Sicurezza](#Security)</span><span class="sxs-lookup"><span data-stu-id="cb541-104">**Before you begin:**  [Limitations and Restrictions](#Restrictions), [Security](#Security)</span></span>  
  
-   <span data-ttu-id="cb541-105">**Per assegnare ad altri utenti la proprietà di un processo usando:**</span><span class="sxs-lookup"><span data-stu-id="cb541-105">**To give others ownership of a job, using:**</span></span>  
  
     [<span data-ttu-id="cb541-106">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="cb541-106">SQL Server Management Studio</span></span>](#SSMSProc2)  
  
     [<span data-ttu-id="cb541-107">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="cb541-107">Transact-SQL</span></span>](#TsqlProc2)  
  
     [<span data-ttu-id="cb541-108">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="cb541-108">SQL Server Management Objects</span></span>](#SMOProc2)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="cb541-109">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="cb541-109">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="cb541-110">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="cb541-110">Limitations and Restrictions</span></span>  
 <span data-ttu-id="cb541-111">Per creare un processo, è necessario che l'utente sia membro di uno dei ruoli predefiniti del database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent o del ruolo predefinito del server **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="cb541-111">To create a job, a user must be a member of one of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database roles or the **sysadmin** fixed server role.</span></span> <span data-ttu-id="cb541-112">Un processo può essere modificato solo dal proprietario o dai membri del ruolo **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="cb541-112">A job can be edited only by its owner or members of the **sysadmin** role.</span></span> <span data-ttu-id="cb541-113">Per altre informazioni sui ruoli predefiniti del database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, vedere [Ruoli di database predefiniti di SQL Server Agent](sql-server-agent-fixed-database-roles.md).</span><span class="sxs-lookup"><span data-stu-id="cb541-113">For more information about the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database roles, see [SQL Server Agent Fixed Database Roles](sql-server-agent-fixed-database-roles.md).</span></span>  
  
 <span data-ttu-id="cb541-114">Solo un amministratore di sistema può cambiare il proprietario di un processo.</span><span class="sxs-lookup"><span data-stu-id="cb541-114">You must be a system administrator to change the owner of a job.</span></span>  
  
 <span data-ttu-id="cb541-115">L'assegnazione di un processo a un altro account di accesso non garantisce che il nuovo proprietario disponga di autorizzazioni sufficienti per eseguire correttamente il processo.</span><span class="sxs-lookup"><span data-stu-id="cb541-115">Assigning a job to another login does not guarantee that the new owner has sufficient permission to run the job successfully.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="cb541-116">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="cb541-116">Security</span></span>  
 <span data-ttu-id="cb541-117">Per motivi di sicurezza, solo il proprietario del processo o un membro del ruolo **sysadmin** può modificare la definizione del processo.</span><span class="sxs-lookup"><span data-stu-id="cb541-117">For security reasons, only the job owner or a member of the **sysadmin** role can change the definition of the job.</span></span> <span data-ttu-id="cb541-118">Solo i membri del ruolo predefinito del server **sysadmin** possono assegnare la proprietà di un processo ad altri utenti ed eseguire qualsiasi processo, indipendentemente dal proprietario.</span><span class="sxs-lookup"><span data-stu-id="cb541-118">Only members of the **sysadmin** fixed server role can assign job ownership to other users, and they can run any job, regardless of the job owner.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cb541-119">Se si assegna la proprietà di un processo a un utente che non è membro del ruolo predefinito del server **sysadmin** e il processo sta eseguendo operazioni per le quali sono necessari account proxy, ad esempio l'esecuzione del pacchetto [!INCLUDE[ssIS](../../includes/ssis-md.md)] , verificare che l'utente possa accedere all'account proxy. In caso contrario, verrà generato un errore.</span><span class="sxs-lookup"><span data-stu-id="cb541-119">If you change job ownership to a user who is not a member of the **sysadmin** fixed server role, and the job is executing job steps that require proxy accounts (for example, [!INCLUDE[ssIS](../../includes/ssis-md.md)] package execution), make sure that the user has access to that proxy account or else the job will fail.</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="cb541-120">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="cb541-120">Permissions</span></span>  
 <span data-ttu-id="cb541-121">Per informazioni dettagliate, vedere [Implementazione della sicurezza di SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="cb541-121">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProc2"></a> <span data-ttu-id="cb541-122">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="cb541-122">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="cb541-123">**Per assegnare ad altri utenti la proprietà di un processo**</span><span class="sxs-lookup"><span data-stu-id="cb541-123">**To give others ownership of a job**</span></span>  
  
1.  <span data-ttu-id="cb541-124">In **Esplora oggetti** connettersi a un'istanza del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , quindi espandere l'istanza.</span><span class="sxs-lookup"><span data-stu-id="cb541-124">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="cb541-125">Espandere **SQL Server Agent**e quindi **Processi**, fare clic con il pulsante destro del mouse sul processo e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="cb541-125">Expand **SQL Server Agent**, expand **Jobs**, right-click the job, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="cb541-126">Nell'elenco **Proprietario** selezionare un account di accesso.</span><span class="sxs-lookup"><span data-stu-id="cb541-126">In the **Owner** list, select a login.</span></span> <span data-ttu-id="cb541-127">Solo un amministratore di sistema può cambiare il proprietario di un processo.</span><span class="sxs-lookup"><span data-stu-id="cb541-127">You must be a system administrator to change the owner of a job.</span></span>  
  
     <span data-ttu-id="cb541-128">L'assegnazione di un processo a un altro account di accesso non garantisce che il nuovo proprietario disponga di autorizzazioni sufficienti per eseguire correttamente il processo.</span><span class="sxs-lookup"><span data-stu-id="cb541-128">Assigning a job to another login does not guarantee that the new owner has sufficient permission to run the job successfully.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProc2"></a> <span data-ttu-id="cb541-129">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="cb541-129">Using Transact-SQL</span></span>  
 <span data-ttu-id="cb541-130">**Per assegnare ad altri utenti la proprietà di un processo**</span><span class="sxs-lookup"><span data-stu-id="cb541-130">**To give others ownership of a job**</span></span>  
  
1.  <span data-ttu-id="cb541-131">In Esplora oggetti connettersi a un'istanza del motore di database ed espanderla.</span><span class="sxs-lookup"><span data-stu-id="cb541-131">In Object Explorer, connect to an instance of the Database Engine, and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="cb541-132">Sulla barra degli strumenti fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="cb541-132">On the toolbar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="cb541-133">Nella finestra query immettere le istruzioni seguenti che utilizzano il [sp_manage_jobs_by_login &#40;&#41;di sistema Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-manage-jobs-by-login-transact-sql) stored procedure.</span><span class="sxs-lookup"><span data-stu-id="cb541-133">In the query window, enter the following statements that use the [sp_manage_jobs_by_login &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-manage-jobs-by-login-transact-sql) system stored procedure.</span></span> <span data-ttu-id="cb541-134">In questo esempio tutti i processi di `danw` vengono riassegnati a `fran??oisa`.</span><span class="sxs-lookup"><span data-stu-id="cb541-134">The following example reassigns all jobs from `danw` to `fran??oisa`.</span></span>  
  
    ```sql
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_manage_jobs_by_login  
        @action = N'REASSIGN',  
        @current_owner_login_name = N'danw',  
        @new_owner_login_name = N'fran??oisa' ;  
    GO  
    ```  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMOProc2"></a><span data-ttu-id="cb541-135">Utilizzo di SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="cb541-135">Using SQL Server Management Objects</span></span>  

### <a name="to-give-others-ownership-of-a-job"></a><span data-ttu-id="cb541-136">Per assegnare ad altri utenti la proprietà di un processo</span><span class="sxs-lookup"><span data-stu-id="cb541-136">To give others ownership of a job</span></span>
  
1.  <span data-ttu-id="cb541-137">Chiamare la classe `Job` tramite un linguaggio di programmazione come Visual Basic, Visual C# o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cb541-137">Call the `Job` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="cb541-138">Per un codice di esempio, vedere [Pianificazione delle attività amministrative automatiche in SQL Server Agent](sql-server-agent.md).</span><span class="sxs-lookup"><span data-stu-id="cb541-138">For example code, see [Scheduling Automatic Administrative Tasks in SQL Server Agent](sql-server-agent.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb541-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cb541-139">See Also</span></span>  
 <span data-ttu-id="cb541-140">[Implementazione di processi](implement-jobs.md) </span><span class="sxs-lookup"><span data-stu-id="cb541-140">[Implement Jobs](implement-jobs.md) </span></span>  
 [<span data-ttu-id="cb541-141">Creazione di processi</span><span class="sxs-lookup"><span data-stu-id="cb541-141">Create Jobs</span></span>](create-jobs.md)  
