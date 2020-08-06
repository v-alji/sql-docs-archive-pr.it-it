---
title: Disabilitare o abilitare un processo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- stopping jobs
- disabling jobs
- SQL Server Agent jobs, disabling
- jobs [SQL Server Agent], disabling
ms.assetid: 5041261f-0c32-4d4a-8bee-59a6c16200dd
author: stevestein
ms.author: sstein
ms.openlocfilehash: 42fe7cbeed1e2ff3f93b1afef52b165a7d660ddd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623727"
---
# <a name="disable-or-enable-a-job"></a><span data-ttu-id="4974e-102">Abilitare o disabilitare un processo</span><span class="sxs-lookup"><span data-stu-id="4974e-102">Disable or Enable a Job</span></span>
  <span data-ttu-id="4974e-103">In questo argomento viene descritto come disabilitare un processo di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4974e-103">This topic describes how to disable a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="4974e-104">Quando si disabilita un processo, questo non viene eliminato e, se necessario, può essere abilitato nuovamente.</span><span class="sxs-lookup"><span data-stu-id="4974e-104">When you disable a job, it is not deleted and can be enabled again when necessary.</span></span>  
  
 <span data-ttu-id="4974e-105">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="4974e-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="4974e-106">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="4974e-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="4974e-107">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="4974e-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="4974e-108">**Per disabilitare o abilitare un processo utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="4974e-108">**To disable or enable a job, using:**</span></span>  
  
     [<span data-ttu-id="4974e-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4974e-109">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="4974e-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4974e-110">Transact-SQL</span></span>](#TSQL)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="4974e-111">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="4974e-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="4974e-112">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="4974e-112">Security</span></span>  
 <span data-ttu-id="4974e-113">Per informazioni dettagliate, vedere [Implementazione della sicurezza di SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="4974e-113">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="4974e-114">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4974e-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-disable-or-enable-a-job"></a><span data-ttu-id="4974e-115">Per disabilitare o abilitare un processo</span><span class="sxs-lookup"><span data-stu-id="4974e-115">To disable or enable a job</span></span>  
  
1.  <span data-ttu-id="4974e-116">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], quindi espandere questa istanza.</span><span class="sxs-lookup"><span data-stu-id="4974e-116">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="4974e-117">Espandere **SQL Server Agent**.</span><span class="sxs-lookup"><span data-stu-id="4974e-117">Expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="4974e-118">Espandere **Processi**e fare clic con il pulsante destro del mouse sul processo da disabilitare o abilitare.</span><span class="sxs-lookup"><span data-stu-id="4974e-118">Expand **Jobs**, and then right-click the job that you want to disable or enable.</span></span>  
  
4.  <span data-ttu-id="4974e-119">Per disabilitare un processo fare clic su **Disabilita**.</span><span class="sxs-lookup"><span data-stu-id="4974e-119">To disable a job, click **Disable**.</span></span> <span data-ttu-id="4974e-120">Per abilitare un processo fare clic su **Abilita**.</span><span class="sxs-lookup"><span data-stu-id="4974e-120">To enable a job, click **Enable**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="4974e-121">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4974e-121">Using Transact-SQL</span></span>  
  
#### <a name="to-disable-or-enable-a-job"></a><span data-ttu-id="4974e-122">Per disabilitare o abilitare un processo</span><span class="sxs-lookup"><span data-stu-id="4974e-122">To disable or enable a job</span></span>  
  
1.  <span data-ttu-id="4974e-123">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4974e-123">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="4974e-124">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="4974e-124">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="4974e-125">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="4974e-125">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- changes the name, description, and enables status of the job NightlyBackups.  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_update_job  
        @job_name = N'NightlyBackups',  
        @new_name = N'NightlyBackups -- Disabled',  
        @description = N'Nightly backups disabled during server migration.',  
        @enabled = 1 ;  
    GO  
    ```  
  
 <span data-ttu-id="4974e-126">Per ulteriori informazioni, vedere [sp_update_job &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-update-job-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4974e-126">For more information, see [sp_update_job &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-job-transact-sql).</span></span>  
  
  
