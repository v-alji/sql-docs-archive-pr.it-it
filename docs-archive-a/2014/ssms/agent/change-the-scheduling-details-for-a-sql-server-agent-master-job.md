---
title: Modificare i dettagli della pianificazione per un processo master di SQL Server Agent | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
ms.assetid: f5414451-4d8e-464b-bd9e-f2b70c6899b3
author: stevestein
ms.author: sstein
ms.openlocfilehash: 85546bc93e6626bfcc85a28f06a4c2fe24fe9fd1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637594"
---
# <a name="change-the-scheduling-details-for-a-sql-server-agent-master-job"></a><span data-ttu-id="e4fc3-102">Change the Scheduling Details for a SQL Server Agent Master Job</span><span class="sxs-lookup"><span data-stu-id="e4fc3-102">Change the Scheduling Details for a SQL Server Agent Master Job</span></span>
  <span data-ttu-id="e4fc3-103">In questo argomento verrà descritto come modificare i dettagli della pianificazione per la definizione di un processo in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e4fc3-103">This topic describes how to change the scheduling details for a job definition in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="e4fc3-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="e4fc3-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="e4fc3-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="e4fc3-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="e4fc3-106">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="e4fc3-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="e4fc3-107">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="e4fc3-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="e4fc3-108">**Per modificare i dettagli della pianificazione per la definizione di un processo tramite:**</span><span class="sxs-lookup"><span data-stu-id="e4fc3-108">**To change the scheduling details for a job definition, using:**</span></span>  
  
     [<span data-ttu-id="e4fc3-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e4fc3-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="e4fc3-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e4fc3-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="e4fc3-111">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="e4fc3-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="e4fc3-112">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="e4fc3-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="e4fc3-113">Un processo master di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent non può essere destinato sia a server locali sia a server remoti.</span><span class="sxs-lookup"><span data-stu-id="e4fc3-113">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent master job cannot be targeted at both local and remote servers.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="e4fc3-114">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="e4fc3-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="e4fc3-115">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="e4fc3-115">Permissions</span></span>  
 <span data-ttu-id="e4fc3-116">È possibile modificare solo i processi di cui si è proprietari, a meno che non si appartenga al ruolo predefinito del server **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="e4fc3-116">Unless you are a member of the **sysadmin** fixed server role, you can only modify jobs that you own.</span></span> <span data-ttu-id="e4fc3-117">Per informazioni dettagliate, vedere [Implementazione della sicurezza di SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="e4fc3-117">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="e4fc3-118">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e4fc3-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-change-the-scheduling-details-for-a-job-definition"></a><span data-ttu-id="e4fc3-119">Per modificare i dettagli della pianificazione per la definizione di un processo</span><span class="sxs-lookup"><span data-stu-id="e4fc3-119">To change the scheduling details for a job definition</span></span>  
  
1.  <span data-ttu-id="e4fc3-120">In **Esplora oggetti** fare clic sul segno più per espandere il server contenente il processo di cui si desidera modificare la pianificazione.</span><span class="sxs-lookup"><span data-stu-id="e4fc3-120">In **Object Explorer,** click the plus sign to expand the server that contains the job whose schedule you want to edit.</span></span>  
  
2.  <span data-ttu-id="e4fc3-121">Fare clic sul segno più per espandere **SQL Server Agent**.</span><span class="sxs-lookup"><span data-stu-id="e4fc3-121">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="e4fc3-122">Fare clic sul segno più per espandere la cartella **Processi** .</span><span class="sxs-lookup"><span data-stu-id="e4fc3-122">Click the plus sign to expand the **Jobs** folder.</span></span>  
  
4.  <span data-ttu-id="e4fc3-123">Fare clic con il pulsante destro del mouse sul processo di cui si vuole modificare la pianificazione e selezionare **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="e4fc3-123">Right-click the job whose schedule you want to edit and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="e4fc3-124">Nella finestra di dialogo **Proprietà processo-**_Job_name_ , in **Selezione pagina**selezionare **pianificazioni**.</span><span class="sxs-lookup"><span data-stu-id="e4fc3-124">In the **Job Properties -**_job_name_ dialog box, under **Select a page**, select **Schedules**.</span></span> <span data-ttu-id="e4fc3-125">Per ulteriori informazioni sulle opzioni disponibili in questa pagina, vedere la [pagina Proprietà processo: nuovo processo &#40;pianificazioni&#41;](job-properties-new-job-schedules-page.md).</span><span class="sxs-lookup"><span data-stu-id="e4fc3-125">For more information on the available options on this page, see [Job Properties: New Job &#40;Schedules Page&#41;](job-properties-new-job-schedules-page.md).</span></span>  
  
6.  <span data-ttu-id="e4fc3-126">Al termine, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="e4fc3-126">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="e4fc3-127">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e4fc3-127">Using Transact-SQL</span></span>  
  
#### <a name="to-change-the-scheduling-details-for-a-job-definition"></a><span data-ttu-id="e4fc3-128">Per modificare i dettagli della pianificazione per la definizione di un processo</span><span class="sxs-lookup"><span data-stu-id="e4fc3-128">To change the scheduling details for a job definition</span></span>  
  
1.  <span data-ttu-id="e4fc3-129">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e4fc3-129">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="e4fc3-130">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="e4fc3-130">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="e4fc3-131">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="e4fc3-131">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- changes the enabled status of the NightlyJobs schedule to 0   
    -- and sets the owner to terrid.   
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_update_schedule  
        @name = 'NightlyJobs',  
        @enabled = 0,  
        @owner_login_name = 'terrid' ;  
    GO  
    ```  
  
 <span data-ttu-id="e4fc3-132">Per ulteriori informazioni, vedere [sp_update_schedule &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-update-schedule-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e4fc3-132">For more information, see [sp_update_schedule &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-schedule-transact-sql).</span></span>  
  
  
