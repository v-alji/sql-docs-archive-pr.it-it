---
title: Eliminare il log di un passaggio di processo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- job steps [SQL Server Agent]
- deleting job step logs
- logs [SQL Server], jobs
- removing job step logs
ms.assetid: ee20c6cd-0258-4550-bdb0-71e86a0fb330
author: stevestein
ms.author: sstein
ms.openlocfilehash: de7c64c4d7cf461eef563ae6989e043d125c6f5b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629702"
---
# <a name="delete-a-job-step-log"></a><span data-ttu-id="3ab0e-102">Delete a Job Step Log</span><span class="sxs-lookup"><span data-stu-id="3ab0e-102">Delete a Job Step Log</span></span>
  <span data-ttu-id="3ab0e-103">In questo argomento viene illustrato come eliminare un log dei passaggi di processo di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3ab0e-103">This topic describes how to delete a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job step log.</span></span>  
  
-   <span data-ttu-id="3ab0e-104">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="3ab0e-104">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="3ab0e-105">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="3ab0e-105">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="3ab0e-106">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="3ab0e-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="3ab0e-107">**Per eliminare un log dei passaggi di processo di SQL Server Agent mediante:**</span><span class="sxs-lookup"><span data-stu-id="3ab0e-107">**To delete a SQL Server Agent job step log, using:**</span></span>  
  
     [<span data-ttu-id="3ab0e-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3ab0e-108">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="3ab0e-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3ab0e-109">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="3ab0e-110">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="3ab0e-110">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="3ab0e-111">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="3ab0e-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="3ab0e-112">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="3ab0e-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="3ab0e-113">Il log di output dei passaggi di processo eliminati viene eliminato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="3ab0e-113">When job steps are deleted their output log is automatically deleted.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="3ab0e-114">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="3ab0e-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="3ab0e-115">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="3ab0e-115">Permissions</span></span>  
 <span data-ttu-id="3ab0e-116">È possibile modificare solo i processi di cui si è proprietari, a meno che non si appartenga al ruolo predefinito del server **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="3ab0e-116">Unless you are a member of the **sysadmin** fixed server role, you can only modify jobs that you own.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="3ab0e-117">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3ab0e-117">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-sql-server-agent-job-step-log"></a><span data-ttu-id="3ab0e-118">Per eliminare un log dei passaggi di processo di SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="3ab0e-118">To delete a SQL Server Agent job step log</span></span>  
  
1.  <span data-ttu-id="3ab0e-119">In **Esplora oggetti** connettersi a un'istanza del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , quindi espandere l'istanza.</span><span class="sxs-lookup"><span data-stu-id="3ab0e-119">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="3ab0e-120">Espandere il nodo **SQL Server Agent**e il nodo **Processi**; fare clic con il pulsante destro del mouse sul processo che si vuole modificare e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="3ab0e-120">Expand **SQL Server Agent**, expand **Jobs**, right-click the job you want to modify, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="3ab0e-121">Nella finestra di dialogo **Proprietà processo** eliminare il passaggio di processo selezionato.</span><span class="sxs-lookup"><span data-stu-id="3ab0e-121">In the **Job Properties** dialog box, delete the selected job step.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="3ab0e-122">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3ab0e-122">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-sql-server-agent-job-step-log"></a><span data-ttu-id="3ab0e-123">Per eliminare un log dei passaggi di processo di SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="3ab0e-123">To delete a SQL Server Agent job step log</span></span>  
  
1.  <span data-ttu-id="3ab0e-124">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3ab0e-124">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="3ab0e-125">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="3ab0e-125">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="3ab0e-126">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="3ab0e-126">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- removes the job step log for step 2 in the job Weekly Sales Data Backup  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_delete_jobsteplog  
        @job_name = N'Weekly Sales Data Backup',  
        @step_id = 2;  
    GO  
    ```  
  
 <span data-ttu-id="3ab0e-127">Per ulteriori informazioni, vedere [sp_delete_jobsteplog &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-delete-jobsteplog-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="3ab0e-127">For more information, see [sp_delete_jobsteplog &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-jobsteplog-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="3ab0e-128">Utilizzo di SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="3ab0e-128">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="3ab0e-129">Utilizzare i metodi `DeleteJobStepLogs` della classe `Job` utilizzando un linguaggio di programmazione come Visual Basic, Visual C# o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3ab0e-129">Use the `DeleteJobStepLogs` methods of the `Job` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="3ab0e-130">Per altre informazioni, vedere[SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span><span class="sxs-lookup"><span data-stu-id="3ab0e-130">For more information, see[SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span></span>  
  
```powershell
# Delete all job step log files that have ID values larger than 5.  
$srv = New-Object Microsoft.SqlServer.Management.Smo.Server("(local)")  
$jb = $srv.JobServer.Jobs["Test Job"]  
$jb.DeleteJobStepLogs(5)  
```
