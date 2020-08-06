---
title: Eliminare uno o più processi | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, deleting
- dropping jobs
- jobs [SQL Server Agent], deleting
- deleting jobs
- removing jobs
ms.assetid: 67dcdad0-57b2-431c-b77f-4ffc926af93d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 436625f9ad629a6b0e574aa046059f4e7e9c2bf2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624518"
---
# <a name="delete-one-or-more-jobs"></a><span data-ttu-id="aa020-102">Eliminare uno o più processi</span><span class="sxs-lookup"><span data-stu-id="aa020-102">Delete One or More Jobs</span></span>
  <span data-ttu-id="aa020-103">In questo argomento viene descritto come eliminare i [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] processi [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] di Agent in tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , [!INCLUDE[tsql](../../includes/tsql-md.md)] o SQL Server Management Objects.</span><span class="sxs-lookup"><span data-stu-id="aa020-103">This topic describes how to delete [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Management Objects.</span></span>  
  
 
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="aa020-104">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="aa020-104">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="aa020-105">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="aa020-105">Security</span></span>  
 <span data-ttu-id="aa020-106">È possibile modificare solo i processi di cui si è proprietari, a meno che non si appartenga al ruolo predefinito del server **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="aa020-106">Unless you are a member of the **sysadmin** fixed server role, you can only delete jobs that you own.</span></span>  
  
 
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="aa020-107">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="aa020-107">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-job"></a><span data-ttu-id="aa020-108">Per eliminare un processo</span><span class="sxs-lookup"><span data-stu-id="aa020-108">To delete a job</span></span>  
  
1.  <span data-ttu-id="aa020-109">In **Esplora oggetti** connettersi a un'istanza del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , quindi espandere l'istanza.</span><span class="sxs-lookup"><span data-stu-id="aa020-109">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="aa020-110">Espandere **SQL Server Agent**e **Processi**, fare clic con il pulsante destro del mouse sul processo che si vuole eliminare e scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="aa020-110">Expand **SQL Server Agent**, expand **Jobs**, right-click the job you want to delete, and then click **Delete**.</span></span>  
  
3.  <span data-ttu-id="aa020-111">Nella finestra di dialogo **Elimina oggetto** verificare che sia selezionato l'oggetto da eliminare.</span><span class="sxs-lookup"><span data-stu-id="aa020-111">In the **Delete Object** dialog box, confirm that the job you intend to delete is selected.</span></span>  
  
4.  <span data-ttu-id="aa020-112">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="aa020-112">Click **OK**.</span></span>  
  
#### <a name="to-delete-multiple-jobs"></a><span data-ttu-id="aa020-113">Per eliminare più processi</span><span class="sxs-lookup"><span data-stu-id="aa020-113">To delete multiple jobs</span></span>  
  
1.  <span data-ttu-id="aa020-114">In **Esplora oggetti** connettersi a un'istanza del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , quindi espandere l'istanza.</span><span class="sxs-lookup"><span data-stu-id="aa020-114">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="aa020-115">Espandere **SQL Server Agent**.</span><span class="sxs-lookup"><span data-stu-id="aa020-115">Expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="aa020-116">Fare clic con il pulsante destro del mouse su **Monitoraggio attività processi**e scegliere **Visualizza attività processi**.</span><span class="sxs-lookup"><span data-stu-id="aa020-116">Right-click **Job Activity Monitor**, and click **View Job Activity**.</span></span>  
  
4.  <span data-ttu-id="aa020-117">In Monitoraggio attività processi, selezionare i processi che si vuole eliminare, fare clic con il pulsante destro del mouse sui processi selezionati e scegliere **Elimina processi**.</span><span class="sxs-lookup"><span data-stu-id="aa020-117">In the Job Activity Monitor, select the jobs you want to delete, right-click your selection, and choose **Delete jobs**.</span></span>  
  

  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="aa020-118">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="aa020-118">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-job"></a><span data-ttu-id="aa020-119">Per eliminare un processo</span><span class="sxs-lookup"><span data-stu-id="aa020-119">To delete a job</span></span>  
  
1.  <span data-ttu-id="aa020-120">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aa020-120">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="aa020-121">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="aa020-121">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="aa020-122">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="aa020-122">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    USE msdb ;  
    GO  
  
    EXEC sp_delete_job  
        @job_name = N'NightlyBackups' ;  
    GO  
    ```  
  
 <span data-ttu-id="aa020-123">Per ulteriori informazioni, vedere [sp_delete_job &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-delete-job-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="aa020-123">For more information, see [sp_delete_job &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-job-transact-sql).</span></span>  

##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="aa020-124">Utilizzo di SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="aa020-124">Using SQL Server Management Objects</span></span>  

### <a name="to-delete-multiple-jobs"></a><span data-ttu-id="aa020-125">Per eliminare più processi</span><span class="sxs-lookup"><span data-stu-id="aa020-125">To delete multiple jobs</span></span>
  
 <span data-ttu-id="aa020-126">Usare la classe `JobCollection` tramite un linguaggio di programmazione scelto come Visual Basic, Visual C# o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="aa020-126">Use the `JobCollection` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="aa020-127">Per altre informazioni, vedere [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span><span class="sxs-lookup"><span data-stu-id="aa020-127">For more information, see [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span></span>  
