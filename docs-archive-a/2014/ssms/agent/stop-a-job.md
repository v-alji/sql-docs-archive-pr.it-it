---
title: Arrestare un processo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], stopping
- SQL Server Agent jobs, stopping
- stopping jobs
ms.assetid: 4249328a-24d8-4284-9d1d-7d04ed90e3d7
author: stevestein
ms.author: sstein
ms.openlocfilehash: 78986e85dd8ee808f5fb621182d903a94bbc5eb7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711567"
---
# <a name="stop-a-job"></a><span data-ttu-id="09dc2-102">Stop a Job</span><span class="sxs-lookup"><span data-stu-id="09dc2-102">Stop a Job</span></span>
  <span data-ttu-id="09dc2-103">In questo argomento viene descritto come arrestare un [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] processo di Agent.</span><span class="sxs-lookup"><span data-stu-id="09dc2-103">This topic describes how to stop a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job.</span></span> <span data-ttu-id="09dc2-104">Un processo è una serie specificata di azioni eseguite da SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="09dc2-104">A job is a specified series of actions that SQL Server Agent performs.</span></span>  
  
-   <span data-ttu-id="09dc2-105">**Prima di iniziare:** ,</span><span class="sxs-lookup"><span data-stu-id="09dc2-105">**Before you begin:**  ,</span></span>  
  
     [<span data-ttu-id="09dc2-106">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="09dc2-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="09dc2-107">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="09dc2-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="09dc2-108">**Per arrestare un processo utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="09dc2-108">**To stop a job, using:**</span></span>  
  
     [<span data-ttu-id="09dc2-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="09dc2-109">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="09dc2-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="09dc2-110">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="09dc2-111">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="09dc2-111">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="09dc2-112">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="09dc2-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="09dc2-113">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="09dc2-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="09dc2-114">Se in un processo è in esecuzione un passaggio di tipo **CmdExec** o **PowerShell**, viene impostata l'interruzione anticipata del processo eseguito, ad esempio MioProgramma.exe.</span><span class="sxs-lookup"><span data-stu-id="09dc2-114">If a job is currently executing a step of type **CmdExec** or **PowerShell**, the process that is being run (for example, MyProgram.exe) is forced to end prematurely.</span></span> <span data-ttu-id="09dc2-115">Tale interruzione può causare un comportamento imprevisto, poiché ad esempio i file utilizzati dal processo potrebbero restare aperti.</span><span class="sxs-lookup"><span data-stu-id="09dc2-115">This can cause unpredictable behavior, such as files that are being used by the process being held open.</span></span>  
  
-   <span data-ttu-id="09dc2-116">Per un processo multiserver, viene inviata un'istruzione STOP a tutti i server di destinazione del processo.</span><span class="sxs-lookup"><span data-stu-id="09dc2-116">For a multiserver job, a STOP instruction for the job is posted to all target servers of the job.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="09dc2-117">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="09dc2-117">Security</span></span>  
 <span data-ttu-id="09dc2-118">Per informazioni dettagliate, vedere [Implementazione della sicurezza di SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="09dc2-118">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="09dc2-119">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="09dc2-119">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-stop-a-job"></a><span data-ttu-id="09dc2-120">Per arrestare un processo</span><span class="sxs-lookup"><span data-stu-id="09dc2-120">To stop a job</span></span>  
  
1.  <span data-ttu-id="09dc2-121">In **Esplora oggetti** connettersi a un'istanza del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , quindi espandere l'istanza.</span><span class="sxs-lookup"><span data-stu-id="09dc2-121">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="09dc2-122">Espandere **SQL Server Agent**e **Processi**, fare clic con il pulsante destro del mouse sul processo da arrestare e scegliere **Arresta processo**.</span><span class="sxs-lookup"><span data-stu-id="09dc2-122">Expand **SQL Server Agent**, expand **Jobs**, right-click the job you want to stop, and then click **Stop Job**.</span></span>  
  
3.  <span data-ttu-id="09dc2-123">Se si intende arrestare più processi, fare clic con il pulsante destro del mouse su **Monitoraggio attività processi**e scegliere **Visualizza attività processi**.</span><span class="sxs-lookup"><span data-stu-id="09dc2-123">If you want to stop multiple jobs, right-click **Job Activity Monitor**, and then click **View Job Activity**.</span></span> <span data-ttu-id="09dc2-124">In Monitoraggio attività processo selezionare i processi da arrestare, fare clic con il pulsante destro del mouse sulla selezione e scegliere **Arresta processi**.</span><span class="sxs-lookup"><span data-stu-id="09dc2-124">In the Job Activity Monitor, select the jobs you want to stop, right-click your selection, and then click **Stop Jobs**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="09dc2-125">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="09dc2-125">Using Transact-SQL</span></span>  
  
### <a name="to-stop-a-job"></a><span data-ttu-id="09dc2-126">Per arrestare un processo</span><span class="sxs-lookup"><span data-stu-id="09dc2-126">To stop a job</span></span>  
  
1.  <span data-ttu-id="09dc2-127">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="09dc2-127">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="09dc2-128">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="09dc2-128">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="09dc2-129">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="09dc2-129">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- stops a job named Weekly Sales Data Backup  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_stop_job  
        N'Weekly Sales Data Backup' ;  
    GO  
    ```  
  
 <span data-ttu-id="09dc2-130">Per ulteriori informazioni, vedere [sp_stop_job &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-stop-job-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="09dc2-130">For more information, see [sp_stop_job &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-stop-job-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="09dc2-131">Utilizzo di SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="09dc2-131">Using SQL Server Management Objects</span></span>  

### <a name="to-stop-a-job"></a><span data-ttu-id="09dc2-132">Per arrestare un processo</span><span class="sxs-lookup"><span data-stu-id="09dc2-132">To stop a job</span></span>
  
 <span data-ttu-id="09dc2-133">Chiamare il metodo `Stop` della classe `Job` usando un linguaggio di programmazione come Visual Basic, Visual C# o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="09dc2-133">Call the `Stop` method of the `Job` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="09dc2-134">Per altre informazioni, vedere [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span><span class="sxs-lookup"><span data-stu-id="09dc2-134">For more information, see [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span></span>  
