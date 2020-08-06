---
title: Modificare i server di destinazione associati a un processo master di SQL Server Agent | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
ms.assetid: 176e73b6-08aa-48ec-b349-e84b431e65cc
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6b7b5ab114366cdafe40b7a70f523fef43eb11d8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637580"
---
# <a name="modify-the-target-servers-associated-with-a-sql-server-agent-master-job"></a><span data-ttu-id="95b3e-102">Modificare i server di destinazione associati a un processo master di SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="95b3e-102">Modify the Target Server(s) Associated with a SQL Server Agent Master Job</span></span>
  <span data-ttu-id="95b3e-103">In questo argomento verrà descritto come modificare i server di destinazione associati a un processo master di SQL Server Agent in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="95b3e-103">This topic describes how to modify the target server(s) associated with a SQL Server Agent master job in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="95b3e-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="95b3e-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="95b3e-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="95b3e-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="95b3e-106">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="95b3e-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="95b3e-107">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="95b3e-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="95b3e-108">**Per modificare i server di destinazione associati a un processo master di SQL Server Agent tramite:**</span><span class="sxs-lookup"><span data-stu-id="95b3e-108">**To modify the target server(s) associated with a SQL Server Agent master job, using:**</span></span>  
  
     [<span data-ttu-id="95b3e-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="95b3e-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="95b3e-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="95b3e-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="95b3e-111">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="95b3e-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="95b3e-112">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="95b3e-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="95b3e-113">Un processo master di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent non può essere destinato sia a server locali sia a server remoti.</span><span class="sxs-lookup"><span data-stu-id="95b3e-113">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent master job cannot be targeted at both local and remote servers.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="95b3e-114">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="95b3e-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="95b3e-115">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="95b3e-115">Permissions</span></span>  
 <span data-ttu-id="95b3e-116">È possibile modificare solo i processi di cui si è proprietari, a meno che non si appartenga al ruolo predefinito del server **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="95b3e-116">Unless you are a member of the **sysadmin** fixed server role, you can only modify jobs that you own.</span></span> <span data-ttu-id="95b3e-117">Per informazioni dettagliate, vedere [Implementazione della sicurezza di SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="95b3e-117">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="95b3e-118">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="95b3e-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-the-target-servers-associated-with-a-sql-server-agent-master-job"></a><span data-ttu-id="95b3e-119">Per modificare i server di destinazione associati a un processo master di SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="95b3e-119">To modify the target server(s) associated with a SQL Server Agent master job</span></span>  
  
1.  <span data-ttu-id="95b3e-120">In **Esplora oggetti** fare clic sul segno più per espandere il server contenente il processo in cui si desidera modificare il server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="95b3e-120">In **Object Explorer,** click the plus sign to expand the server that contains the job where you want to modify the target server.</span></span>  
  
2.  <span data-ttu-id="95b3e-121">Fare clic sul segno più per espandere **SQL Server Agent**.</span><span class="sxs-lookup"><span data-stu-id="95b3e-121">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="95b3e-122">Fare clic sul segno più per espandere la cartella **Processi** .</span><span class="sxs-lookup"><span data-stu-id="95b3e-122">Click the plus sign to expand the **Jobs** folder.</span></span>  
  
4.  <span data-ttu-id="95b3e-123">Fare clic con il pulsante destro del mouse sul processo in cui si vuole modificare il server di destinazione e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="95b3e-123">Right-click the job where you want to modify the target server and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="95b3e-124">Nella finestra di dialogo **Proprietà processo-**_job_name_ selezionare **destinazioni**in **Selezione pagina**.</span><span class="sxs-lookup"><span data-stu-id="95b3e-124">In the **Job Properties -**_job_name_ dialog box, under **Select a page**, select **Targets**.</span></span> <span data-ttu-id="95b3e-125">Per ulteriori informazioni sulle opzioni disponibili in questa pagina, vedere [Proprietà processo: nuova pagina &#40;di destinazione processo&#41;](job-properties-new-job-targets-page.md).</span><span class="sxs-lookup"><span data-stu-id="95b3e-125">For more information on the available options on this page, see [Job Properties: New Job &#40;Targets Page&#41;](job-properties-new-job-targets-page.md).</span></span>  
  
6.  <span data-ttu-id="95b3e-126">Al termine, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="95b3e-126">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="95b3e-127">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="95b3e-127">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-target-server-currently-associated-with-a-sql-server-agent-master-job"></a><span data-ttu-id="95b3e-128">Per eliminare un server di destinazione attualmente associato a un processo master di SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="95b3e-128">To delete a target server currently associated with a SQL Server Agent master job</span></span>  
  
1.  <span data-ttu-id="95b3e-129">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="95b3e-129">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="95b3e-130">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="95b3e-130">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="95b3e-131">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="95b3e-131">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- removes the server SEATTLE2 from processing the Weekly Sales Backupsjob   
    -- assumes that the Weekly Sales Backups job exists  
    USE msdb ;  
    GO  
  
    EXEC sp_delete_jobserver  
        @job_name = N'Weekly Sales Backups',  
        @server_name = N'SEATTLE2' ;  
    GO  
    ```  
  
 <span data-ttu-id="95b3e-132">Per ulteriori informazioni, vedere [sp_delete_jobserver &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-delete-jobserver-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="95b3e-132">For more information, see [sp_delete_jobserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-jobserver-transact-sql).</span></span>  
  
#### <a name="to-associate-a-target-server-with-the-current-sql-server-agent-master-job"></a><span data-ttu-id="95b3e-133">Per associare un server di destinazione al processo master corrente di SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="95b3e-133">To associate a target server with the current SQL Server Agent master job</span></span>  
  
1.  <span data-ttu-id="95b3e-134">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="95b3e-134">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="95b3e-135">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="95b3e-135">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="95b3e-136">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="95b3e-136">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- assigns the multiserver job Weekly Sales Backups to the server SEATTLE2   
    -- assumes that the Weekly Sales Backups job already exists and that   
    -- SEATTLE2 is registered as a target server for the current instance  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_add_jobserver  
        @job_name = N'Weekly Sales Backups',  
        @server_name = N'SEATTLE2' ;  
    GO  
    ```  
  
 <span data-ttu-id="95b3e-137">Per ulteriori informazioni, vedere [sp_add_jobserver &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-add-jobserver-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="95b3e-137">For more information, see [sp_add_jobserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobserver-transact-sql).</span></span>  
  
  
