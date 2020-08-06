---
title: Aggiungere passaggi a un processo master di SQL Server Agent | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
ms.assetid: 9cc1e8ab-7ddc-427b-859e-203aa7e24642
author: stevestein
ms.author: sstein
ms.openlocfilehash: ccff8d6f4faa7bef549b5a179a957ce798250dbe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623029"
---
# <a name="add-steps-to-a-sql-server-agent-master-job"></a><span data-ttu-id="97304-102">Add Steps to a SQL Server Agent Master Job</span><span class="sxs-lookup"><span data-stu-id="97304-102">Add Steps to a SQL Server Agent Master Job</span></span>
  <span data-ttu-id="97304-103">In questo argomento verrà descritto come aggiungere passaggi a un processo master di SQL Server Agent in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="97304-103">This topic describes how to add steps to a SQL Server Agent master job in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="97304-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="97304-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="97304-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="97304-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="97304-106">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="97304-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="97304-107">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="97304-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="97304-108">**Per aggiungere passaggi a un processo master di SQL Server Agent tramite:**</span><span class="sxs-lookup"><span data-stu-id="97304-108">**To add steps to a SQL Server Agent master job, using:**</span></span>  
  
     [<span data-ttu-id="97304-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="97304-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="97304-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="97304-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="97304-111">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="97304-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="97304-112">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="97304-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="97304-113">Un processo master di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent non può essere destinato sia a server locali sia a server remoti.</span><span class="sxs-lookup"><span data-stu-id="97304-113">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent master job cannot be targeted at both local and remote servers.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="97304-114">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="97304-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="97304-115">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="97304-115">Permissions</span></span>  
 <span data-ttu-id="97304-116">È possibile modificare solo i processi di cui si è proprietari, a meno che non si appartenga al ruolo predefinito del server **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="97304-116">Unless you are a member of the **sysadmin** fixed server role, you can only modify jobs that you own.</span></span> <span data-ttu-id="97304-117">Per informazioni dettagliate, vedere [Implementazione della sicurezza di SQL Server Agent](../agent/implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="97304-117">For detailed information, see [Implement SQL Server Agent Security](../agent/implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="97304-118">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="97304-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-add-steps-to-a-sql-server-agent-master-job"></a><span data-ttu-id="97304-119">Per aggiungere passaggi a un processo master di SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="97304-119">To add steps to a SQL Server Agent master job</span></span>  
  
1.  <span data-ttu-id="97304-120">In **Esplora oggetti** fare clic sul segno più per espandere il server contenente il processo a cui si desidera aggiungere passaggi.</span><span class="sxs-lookup"><span data-stu-id="97304-120">In **Object Explorer,** click the plus sign to expand the server that contains the job to which you want to add steps.</span></span>  
  
2.  <span data-ttu-id="97304-121">Fare clic sul segno più per espandere **SQL Server Agent**.</span><span class="sxs-lookup"><span data-stu-id="97304-121">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="97304-122">Fare clic sul segno più per espandere la cartella **Processi** .</span><span class="sxs-lookup"><span data-stu-id="97304-122">Click the plus sign to expand the **Jobs** folder.</span></span>  
  
4.  <span data-ttu-id="97304-123">Fare clic con il pulsante destro del mouse sul processo a cui si intende aggiungere passaggi e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="97304-123">Right-click the job to which you want to add steps and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="97304-124">Nella finestra di dialogo **Proprietà processo -** _nome_processo_ selezionare **Passaggi** in **Selezione pagina**.</span><span class="sxs-lookup"><span data-stu-id="97304-124">In the **Job Properties -**_job_name_ dialog box, under **Select a page**, select **Steps**.</span></span> <span data-ttu-id="97304-125">Per ulteriori informazioni sulle opzioni disponibili in questa pagina, vedere la [pagina Proprietà processo: nuovo processo &#40;passaggi&#41;](../agent/job-properties-new-job-steps-page.md).</span><span class="sxs-lookup"><span data-stu-id="97304-125">For more information on the available options on this page, see [Job Properties:New Job &#40;Steps Page&#41;](../agent/job-properties-new-job-steps-page.md).</span></span>  

6.  <span data-ttu-id="97304-126">Al termine, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="97304-126">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="97304-127">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="97304-127">Using Transact-SQL</span></span>  
  
#### <a name="to-add-steps-to-a-sql-server-agent-master-job"></a><span data-ttu-id="97304-128">Per aggiungere passaggi a un processo master di SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="97304-128">To add steps to a SQL Server Agent master job</span></span>  
  
1.  <span data-ttu-id="97304-129">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="97304-129">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="97304-130">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="97304-130">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="97304-131">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="97304-131">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- creates a job step that changes database access to read-only for the Sales database.   
    -- specifies 5 retry attempts, with each retry to occur after a 5 minute wait.   
    -- assumes that the Weekly Sales Data Backup job already exists  
    USE msdb;  
    GO  
    EXEC sp_add_jobstep  
        @job_name = N'Weekly Sales Data Backup',  
        @step_name = N'Set database to read only',  
        @subsystem = N'TSQL',  
        @command = N'ALTER DATABASE SALES SET READ_ONLY',   
        @retry_attempts = 5,  
        @retry_interval = 5 ;  
    GO  
    ```  
  
 <span data-ttu-id="97304-132">Per ulteriori informazioni, vedere [sp_add_jobstep &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="97304-132">For more information, see [sp_add_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql).</span></span>  
  
  
