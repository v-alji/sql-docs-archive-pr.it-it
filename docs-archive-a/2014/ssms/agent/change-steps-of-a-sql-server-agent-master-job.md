---
title: Modificare i passaggi di un processo master di SQL Server Agent | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
ms.assetid: 8f1a0ee6-49ff-4080-94ca-d661daeff2a6
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7a9defc17b5b39ab8a322b6da29960eb9968c2e0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637596"
---
# <a name="change-steps-of-a-sql-server-agent-master-job"></a><span data-ttu-id="e4f41-102">Change Steps of a SQL Server Agent Master Job</span><span class="sxs-lookup"><span data-stu-id="e4f41-102">Change Steps of a SQL Server Agent Master Job</span></span>
  <span data-ttu-id="e4f41-103">In questo argomento verrà descritto come apportare modifiche ai passaggi di un processo master di SQL Server Agent in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e4f41-103">This topic describes how to make changes to the steps of a SQL Server Agent master job in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="e4f41-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="e4f41-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="e4f41-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="e4f41-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="e4f41-106">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="e4f41-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="e4f41-107">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="e4f41-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="e4f41-108">**Per apportare modifiche ai passaggi di un processo master di SQL Server Agent tramite:**</span><span class="sxs-lookup"><span data-stu-id="e4f41-108">**To make changes to the steps of a SQL Server Agent master job, using:**</span></span>  
  
     [<span data-ttu-id="e4f41-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e4f41-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="e4f41-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e4f41-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="e4f41-111">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="e4f41-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="e4f41-112">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="e4f41-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="e4f41-113">Un processo master di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent non può essere destinato sia a server locali sia a server remoti.</span><span class="sxs-lookup"><span data-stu-id="e4f41-113">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent master job cannot be targeted at both local and remote servers.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="e4f41-114">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="e4f41-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="e4f41-115">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="e4f41-115">Permissions</span></span>  
 <span data-ttu-id="e4f41-116">È possibile modificare solo i processi di cui si è proprietari, a meno che non si appartenga al ruolo predefinito del server **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="e4f41-116">Unless you are a member of the **sysadmin** fixed server role, you can only modify jobs that you own.</span></span> <span data-ttu-id="e4f41-117">Per informazioni dettagliate, vedere [Implementazione della sicurezza di SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="e4f41-117">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="e4f41-118">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e4f41-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-make-changes-to-the-steps-of-a-sql-server-agent-master-job"></a><span data-ttu-id="e4f41-119">Per apportare modifiche ai passaggi di un processo master di SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="e4f41-119">To make changes to the steps of a SQL Server Agent master job</span></span>  
  
1.  <span data-ttu-id="e4f41-120">In **Esplora oggetti** fare clic sul segno più per espandere il server contenente il processo in cui si desidera modificare passaggi.</span><span class="sxs-lookup"><span data-stu-id="e4f41-120">In **Object Explorer,** click the plus sign to expand the server that contains the job where you want to modify steps.</span></span>  
  
2.  <span data-ttu-id="e4f41-121">Fare clic sul segno più per espandere **SQL Server Agent**.</span><span class="sxs-lookup"><span data-stu-id="e4f41-121">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="e4f41-122">Fare clic sul segno più per espandere la cartella **Processi** .</span><span class="sxs-lookup"><span data-stu-id="e4f41-122">Click the plus sign to expand the **Jobs** folder.</span></span>  
  
4.  <span data-ttu-id="e4f41-123">Fare clic con il pulsante destro del mouse sul processo in cui si intende modificare passaggi e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="e4f41-123">Right-click the job where you want to modify steps and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="e4f41-124">Nella finestra di dialogo **Proprietà processo-**_Job_name_ , in **Selezione pagina**selezionare **passaggi**.</span><span class="sxs-lookup"><span data-stu-id="e4f41-124">In the **Job Properties -**_job_name_ dialog box, under **Select a page**, select **Steps**.</span></span>  
  
6.  <span data-ttu-id="e4f41-125">Fare clic su **modifica** per aprire la finestra di dialogo **Proprietà passaggio processo-**_job_step_name_ .</span><span class="sxs-lookup"><span data-stu-id="e4f41-125">Click **Edit** to open the **Job Step Properties -**_job_step_name_ dialog box.</span></span> <span data-ttu-id="e4f41-126">Per ulteriori informazioni sulle opzioni disponibili in questa finestra di dialogo, vedere [Proprietà passaggio processo: nuovo passaggio di processo &#40;pagina generale&#41;](../../integration-services/general-page-of-integration-services-designers-options.md) e [Proprietà passaggio processo: nuovo passaggio di processo &#40;pagina avanzata&#41;](job-step-properties-new-job-step-advanced-page.md).</span><span class="sxs-lookup"><span data-stu-id="e4f41-126">For more information on the available options in this dialog box, see [Job Step Properties: New Job Step &#40;General Page&#41;](../../integration-services/general-page-of-integration-services-designers-options.md) and [Job Step Properties: New Job Step &#40;Advanced Page&#41;](job-step-properties-new-job-step-advanced-page.md).</span></span>  
  
7.  <span data-ttu-id="e4f41-127">Al termine, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="e4f41-127">When finished, click **OK**.</span></span>  
  
8.  <span data-ttu-id="e4f41-128">Nella finestra di dialogo **Proprietà processo-**_job_name_ fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="e4f41-128">In the **Job Properties -**_job_name_ dialog box, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="e4f41-129">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e4f41-129">Using Transact-SQL</span></span>  
  
#### <a name="to-make-changes-to-the-steps-of-a-sql-server-agent-master-job"></a><span data-ttu-id="e4f41-130">Per apportare modifiche ai passaggi di un processo master di SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="e4f41-130">To make changes to the steps of a SQL Server Agent master job</span></span>  
  
1.  <span data-ttu-id="e4f41-131">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e4f41-131">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="e4f41-132">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="e4f41-132">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="e4f41-133">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="e4f41-133">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- changes the number of retry attempts for the first step of the Weekly Sales Data Backup job.   
    -- After running this example, the number of retry attempts is 10   
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_update_jobstep  
        @job_name = N'Weekly Sales Data Backup',  
        @step_id = 1,  
        @retry_attempts = 10 ;  
    GO  
    ```  
  
 <span data-ttu-id="e4f41-134">Per ulteriori informazioni, vedere [sp_update_jobstep &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-update-jobstep-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e4f41-134">For more information, see [sp_update_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-jobstep-transact-sql).</span></span>  
  
  
