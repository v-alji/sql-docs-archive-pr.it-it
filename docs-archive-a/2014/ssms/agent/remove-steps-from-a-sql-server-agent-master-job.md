---
title: Rimuovere passaggi da un processo master di SQL Server Agent | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
ms.assetid: 871e6162-1221-464d-8f7f-7e454dcd9edb
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5996971225ee0b300b307c5af24dec464dbfd43c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637564"
---
# <a name="remove-steps-from-a-sql-server-agent-master-job"></a><span data-ttu-id="43285-102">Remove Steps from a SQL Server Agent Master Job</span><span class="sxs-lookup"><span data-stu-id="43285-102">Remove Steps from a SQL Server Agent Master Job</span></span>
  <span data-ttu-id="43285-103">In questo argomento verrà descritto come rimuovere passaggi da un processo master di SQL Server Agent in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="43285-103">This topic describes how to remove steps from a SQL Server Agent master job in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="43285-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="43285-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="43285-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="43285-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="43285-106">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="43285-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="43285-107">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="43285-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="43285-108">**Per rimuovere passaggi da un processo master di SQL Server Agent tramite:**</span><span class="sxs-lookup"><span data-stu-id="43285-108">**To remove steps from a SQL Server Agent master job, using:**</span></span>  
  
     [<span data-ttu-id="43285-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="43285-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="43285-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="43285-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="43285-111">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="43285-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="43285-112">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="43285-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="43285-113">Un processo master di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent non può essere destinato sia a server locali sia a server remoti.</span><span class="sxs-lookup"><span data-stu-id="43285-113">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent master job cannot be targeted at both local and remote servers.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="43285-114">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="43285-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="43285-115">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="43285-115">Permissions</span></span>  
 <span data-ttu-id="43285-116">È possibile modificare solo i processi di cui si è proprietari, a meno che non si appartenga al ruolo predefinito del server **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="43285-116">Unless you are a member of the **sysadmin** fixed server role, you can only modify jobs that you own.</span></span> <span data-ttu-id="43285-117">Per informazioni dettagliate, vedere [Implementazione della sicurezza di SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="43285-117">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="43285-118">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="43285-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-remove-steps-from-a-sql-server-agent-master-job"></a><span data-ttu-id="43285-119">Per rimuovere passaggi da un processo master di SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="43285-119">To remove steps from a SQL Server Agent master job</span></span>  
  
1.  <span data-ttu-id="43285-120">In **Esplora oggetti** fare clic sul segno più per espandere il server contenente il processo in cui si desidera eliminare passaggi.</span><span class="sxs-lookup"><span data-stu-id="43285-120">In **Object Explorer,** click the plus sign to expand the server that contains the job where you want to delete steps.</span></span>  
  
2.  <span data-ttu-id="43285-121">Fare clic sul segno più per espandere **SQL Server Agent**.</span><span class="sxs-lookup"><span data-stu-id="43285-121">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="43285-122">Fare clic sul segno più per espandere la cartella **Processi** .</span><span class="sxs-lookup"><span data-stu-id="43285-122">Click the plus sign to expand the **Jobs** folder.</span></span>  
  
4.  <span data-ttu-id="43285-123">Fare clic con il pulsante destro del mouse sul processo in cui si intende eliminare passaggi e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="43285-123">Right-click the job where you want to delete steps and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="43285-124">Nella finestra di dialogo **Proprietà processo-**_Job_name_ , in **Selezione pagina**selezionare **passaggi**.</span><span class="sxs-lookup"><span data-stu-id="43285-124">In the **Job Properties -**_job_name_ dialog box, under **Select a page**, select **Steps**.</span></span>  
  
6.  <span data-ttu-id="43285-125">In **Elenco dei passaggi del processo**selezionare il passaggio del processo che si desidera eliminare, quindi fare clic su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="43285-125">Under **Job step list**, select the job step you want to delete and click **Delete**.</span></span>  
  
7.  <span data-ttu-id="43285-126">Al termine, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="43285-126">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="43285-127">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="43285-127">Using Transact-SQL</span></span>  
  
#### <a name="to-remove-steps-from-a-sql-server-agent-master-job"></a><span data-ttu-id="43285-128">Per rimuovere passaggi da un processo master di SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="43285-128">To remove steps from a SQL Server Agent master job</span></span>  
  
1.  <span data-ttu-id="43285-129">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="43285-129">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="43285-130">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="43285-130">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="43285-131">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="43285-131">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- removes job step 1 from the job Weekly Sales Data Backup   
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_delete_jobstep  
        @job_name = N'Weekly Sales Data Backup',  
        @step_id = 1 ;  
    GO  
    ```  
  
 <span data-ttu-id="43285-132">Per ulteriori informazioni, vedere [sp_delete_jobstep &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-delete-jobstep-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="43285-132">For more information, see [sp_delete_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-jobstep-transact-sql).</span></span>  
  
  
