---
title: Avviare un processo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], starting
- SQL Server Agent jobs, starting
- starting jobs
ms.assetid: cec9f7f7-d0a7-4239-9dc5-a69c011ebaa0
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4d5af895df518a915dacd953331b9139471933aa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722172"
---
# <a name="start-a-job"></a><span data-ttu-id="94fc7-102">Avviare un processo</span><span class="sxs-lookup"><span data-stu-id="94fc7-102">Start a Job</span></span>
  <span data-ttu-id="94fc7-103">In questo argomento viene descritto come avviare l'esecuzione di un [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] processo di Agent in utilizzando [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] [!INCLUDE[tsql](../../includes/tsql-md.md)] o SQL Server Management Objects.</span><span class="sxs-lookup"><span data-stu-id="94fc7-103">This topic describes how to start running a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)] or SQL Server Management Objects.</span></span>  
  
 <span data-ttu-id="94fc7-104">Un processo è una serie specificata di azioni eseguite da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="94fc7-104">A job is a specified series of actions that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent performs.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="94fc7-105">Agent possono essere eseguiti in un server locale o in più server remoti.</span><span class="sxs-lookup"><span data-stu-id="94fc7-105">Agent jobs can run on one local server or on multiple remote servers.</span></span>  
  
-   <span data-ttu-id="94fc7-106">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="94fc7-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="94fc7-107">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="94fc7-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="94fc7-108">**Per avviare un processo utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="94fc7-108">**To start a job, using:**</span></span>  
  
     [<span data-ttu-id="94fc7-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="94fc7-109">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="94fc7-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="94fc7-110">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="94fc7-111">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="94fc7-111">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="94fc7-112">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="94fc7-112">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="94fc7-113">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="94fc7-113">Security</span></span>  
 <span data-ttu-id="94fc7-114">Per informazioni dettagliate, vedere [Implementazione della sicurezza di SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="94fc7-114">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="94fc7-115">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="94fc7-115">Using SQL Server Management Studio</span></span>  
  
### <a name="to-start-a-job"></a><span data-ttu-id="94fc7-116">Per avviare un processo</span><span class="sxs-lookup"><span data-stu-id="94fc7-116">To start a job</span></span>  
  
1.  <span data-ttu-id="94fc7-117">In **Esplora oggetti** connettersi a un'istanza del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , quindi espandere l'istanza.</span><span class="sxs-lookup"><span data-stu-id="94fc7-117">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="94fc7-118">Espandere **SQL Server Agent** e quindi **Processi**.</span><span class="sxs-lookup"><span data-stu-id="94fc7-118">Expand **SQL Server Agent,** and expand **Jobs**.</span></span> <span data-ttu-id="94fc7-119">In base alla modalità di avvio del processo desiderata, eseguire una delle seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="94fc7-119">Depending on how you want the job to start, do one of the following:</span></span>  
  
    -   <span data-ttu-id="94fc7-120">Se si usa un unico server oppure un server di destinazione, oppure se si esegue un processo del server locale in un server master, fare clic con il pulsante destro del mouse sul processo da avviare e scegliere **Avvia processo**.</span><span class="sxs-lookup"><span data-stu-id="94fc7-120">If you are working on a single server, or working on a target server, or running a local server job on a master server, right-click the job you want to start, and then click **Start Job**.</span></span>  
  
    -   <span data-ttu-id="94fc7-121">Se si vuole avviare più processi, fare clic con il pulsante destro del mouse su **Monitoraggio attività processi**e scegliere **Visualizza attività processi**.</span><span class="sxs-lookup"><span data-stu-id="94fc7-121">If you want to start multiple jobs, right-click **Job Activity Monitor**, and then click **View Job Activity**.</span></span> <span data-ttu-id="94fc7-122">In Monitoraggio attività processi è possibile selezionare più processi; fare clic con il pulsante destro del mouse sui processi selezionati e scegliere **Avvia processi**.</span><span class="sxs-lookup"><span data-stu-id="94fc7-122">In the Job Activity Monitor you can select multiple jobs, right-click your selection, and click **Start Jobs**.</span></span>  
  
    -   <span data-ttu-id="94fc7-123">Se si usa un server master e si vuole eseguire il processo contemporaneamente in tutti i server di destinazione, fare clic con il pulsante destro del mouse sul processo da avviare, scegliere **Avvia processo**e fare clic su **Avvia su tutti i server di destinazione**.</span><span class="sxs-lookup"><span data-stu-id="94fc7-123">If you are working on a master server and want all targeted servers to run the job simultaneously, right-click the job you want to start, click **Start Job**, and then click **Start on all targeted servers**.</span></span>  
  
    -   <span data-ttu-id="94fc7-124">Se si usa un server master e si vogliono specificare i server di destinazione in cui eseguire il processo, fare clic con il pulsante destro del mouse sul processo da avviare, scegliere **Avvia processo**e fare clic su **Avvia sui server di destinazione specificati**.</span><span class="sxs-lookup"><span data-stu-id="94fc7-124">If you are working on a master server and want to specify target servers for the job, right-click the job you want to start, click **Start Job**, and then click **Start on specific target servers**.</span></span> <span data-ttu-id="94fc7-125">Nella finestra di dialogo **Invia istruzioni di download** selezionare la casella di controllo **Solo i server di destinazione seguenti** e quindi selezionare i server di destinazione in cui si desidera eseguire il processo.</span><span class="sxs-lookup"><span data-stu-id="94fc7-125">In the **Post Download Instructions** dialog box, select the **These target servers** check box, and then select each target server on which this job should run.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="94fc7-126">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="94fc7-126">Using Transact-SQL</span></span>  
  
### <a name="to-start-a-job"></a><span data-ttu-id="94fc7-127">Per avviare un processo</span><span class="sxs-lookup"><span data-stu-id="94fc7-127">To start a job</span></span>  
  
1.  <span data-ttu-id="94fc7-128">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="94fc7-128">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="94fc7-129">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="94fc7-129">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="94fc7-130">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="94fc7-130">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- starts a job named Weekly Sales Data Backup.    
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_start_job N'Weekly Sales Data Backup' ;  
    GO  
    ```  
  
 <span data-ttu-id="94fc7-131">Per altre informazioni, vedere [sp_start_job &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-start-job-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="94fc7-131">For more information, see [sp_start_job &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-start-job-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="94fc7-132">Utilizzo di SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="94fc7-132">Using SQL Server Management Objects</span></span>  

### <a name="to-start-a-job"></a><span data-ttu-id="94fc7-133">Per avviare un processo</span><span class="sxs-lookup"><span data-stu-id="94fc7-133">To start a job</span></span>
  
 <span data-ttu-id="94fc7-134">Chiamare il metodo `Start` della classe `Job` usando un linguaggio di programmazione come Visual Basic, Visual C# o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="94fc7-134">Call the `Start` method of the `Job` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="94fc7-135">Per altre informazioni, vedere [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span><span class="sxs-lookup"><span data-stu-id="94fc7-135">For more information, see [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span></span>  
