---
title: Creare un passaggio di processo di uno script di PowerShell | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- PowerShell [SQL Server], job steps
- jobs [SQL Server Agent], PowerShell
- job steps [PowerShell]
- SQL Server Agent jobs, PowerShell steps
ms.assetid: 50afcf84-fae0-4eb5-9b0f-f2cf144c1433
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4232cdfa584fdcc2e13786ecc9bd00f0c6fe7066
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628065"
---
# <a name="create-a-powershell-script-job-step"></a><span data-ttu-id="f3bbf-102">Create a PowerShell Script Job Step</span><span class="sxs-lookup"><span data-stu-id="f3bbf-102">Create a PowerShell Script Job Step</span></span>
  <span data-ttu-id="f3bbf-103">In questo argomento vengono descritte le procedure per la creazione e la definizione di un passaggio di processo di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent mediante il quale viene eseguito uno script di PowerShell in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f3bbf-103">This topic describes how to create and define a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job step that executes a PowerShell script in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="f3bbf-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="f3bbf-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="f3bbf-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="f3bbf-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="f3bbf-106">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="f3bbf-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="f3bbf-107">**Per creare un passaggio di processo di uno script di PowerShell utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="f3bbf-107">**To create a PowerShell Script job step, using:**</span></span>  
  
     [<span data-ttu-id="f3bbf-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f3bbf-108">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="f3bbf-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f3bbf-109">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="f3bbf-110">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="f3bbf-110">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f3bbf-111">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="f3bbf-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f3bbf-112">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="f3bbf-112">Security</span></span>  
 <span data-ttu-id="f3bbf-113">Per informazioni dettagliate, vedere [Implementazione della sicurezza di SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="f3bbf-113">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="f3bbf-114">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f3bbf-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-powershell-script-job-step"></a><span data-ttu-id="f3bbf-115">Per creare un passaggio di processo di uno script di PowerShell</span><span class="sxs-lookup"><span data-stu-id="f3bbf-115">To create a PowerShell Script job step</span></span>  
  
1.  <span data-ttu-id="f3bbf-116">In **Esplora oggetti** connettersi a un'istanza del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , quindi espandere l'istanza.</span><span class="sxs-lookup"><span data-stu-id="f3bbf-116">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="f3bbf-117">Espandere **SQL Server Agent**, creare un nuovo processo oppure fare clic con il pulsante destro del mouse su un processo esistente e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="f3bbf-117">Expand **SQL Server Agent**, create a new job or right-click an existing job, and then click **Properties**.</span></span> <span data-ttu-id="f3bbf-118">Per ulteriori informazioni sulla creazione di un processo, vedere [Creazione di processi](create-jobs.md).</span><span class="sxs-lookup"><span data-stu-id="f3bbf-118">For more information on creating a job, see [Creating Jobs](create-jobs.md).</span></span>  
  
3.  <span data-ttu-id="f3bbf-119">Nella finestra di dialogo **Proprietà processo** fare clic sulla pagina **Passaggi** e quindi su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="f3bbf-119">In the **Job Properties** dialog, click the **Steps** page, and then click **New**.</span></span>  
  
4.  <span data-ttu-id="f3bbf-120">Nella finestra di dialogo **Nuovo passaggio di processo** digitare il nome del passaggio del processo nella casella **Nome passaggio**.</span><span class="sxs-lookup"><span data-stu-id="f3bbf-120">In the **New Job Step** dialog, type a job **Step name**.</span></span>  
  
5.  <span data-ttu-id="f3bbf-121">Scegliere **PowerShell** dall'elenco **Tipo**.</span><span class="sxs-lookup"><span data-stu-id="f3bbf-121">In the **Type** list, click **PowerShell**.</span></span>  
  
6.  <span data-ttu-id="f3bbf-122">Nell'elenco **Esegui come** selezionare l'account proxy con le credenziali che verranno utilizzate dal processo.</span><span class="sxs-lookup"><span data-stu-id="f3bbf-122">In the **Run as** list, select the proxy account with the credentials that the job will use.</span></span>  
  
7.  <span data-ttu-id="f3bbf-123">Nella casella **Comando** immettere la sintassi dello script di PowerShell che verrà eseguito per il passaggio di processo.</span><span class="sxs-lookup"><span data-stu-id="f3bbf-123">In the **Command** box, enter the PowerShell script syntax that will be executed for the job step.</span></span> <span data-ttu-id="f3bbf-124">In alternativa, è possibile fare clic su **Apri** e selezionare un file contenente la sintassi dello script.</span><span class="sxs-lookup"><span data-stu-id="f3bbf-124">Alternately, click **Open** and select a file containing the script syntax.</span></span> <span data-ttu-id="f3bbf-125">Per un esempio di script di PowerShell, vedere di seguito **Utilizzo di Transact-SQL** .</span><span class="sxs-lookup"><span data-stu-id="f3bbf-125">For an example of a PowerShell script, see **Using Transact-SQL** below.</span></span>  
  
8.  <span data-ttu-id="f3bbf-126">Fare clic sulla pagina **Avanzate** per impostare le opzioni seguenti relative al passaggio di processo: l'azione da eseguire in caso di esito positivo o negativo del passaggio, il numero di tentativi di esecuzione del passaggio che devono essere effettuati da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent e gli intervalli tra tentativi successivi.</span><span class="sxs-lookup"><span data-stu-id="f3bbf-126">Click the **Advanced** page to set the following job step options: what action to take if the job step succeeds or fails, how many times [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent should try to execute the job step, and how often retry attempts should be made.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="f3bbf-127">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f3bbf-127">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-powershell-script-job-step"></a><span data-ttu-id="f3bbf-128">Per creare un passaggio di processo di uno script di PowerShell</span><span class="sxs-lookup"><span data-stu-id="f3bbf-128">To create a PowerShell Script job step</span></span>  
  
1.  <span data-ttu-id="f3bbf-129">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f3bbf-129">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="f3bbf-130">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="f3bbf-130">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="f3bbf-131">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="f3bbf-131">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- creates a PowerShell job step that finds the processes that use more than 1000 MB of memory and kills them  
    USE msdb;  
    GO  
    EXEC sp_add_jobstep  
        @job_name = N'Weekly Sales Data Backup',  
        @step_name = N'Kills all processes that use more than 1000 MB of memory',  
        @subsystem = N'PowerShell',  
        @command = N'Get-Process | Where-Object { $_.WS -gt 1000MB } | Stop-Process',   
        @retry_attempts = 5,  
        @retry_interval = 5 ;  
    GO  
    ```  
  
 <span data-ttu-id="f3bbf-132">Per ulteriori informazioni, vedere [sp_add_jobstep &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f3bbf-132">For more information, see [sp_add_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="f3bbf-133">Utilizzo di SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="f3bbf-133">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="f3bbf-134">**Per creare un passaggio di processo di uno script di PowerShell**</span><span class="sxs-lookup"><span data-stu-id="f3bbf-134">**To create a PowerShell Script job step**</span></span>  
  
 <span data-ttu-id="f3bbf-135">Usare la classe `JobStep` tramite un linguaggio di programmazione scelto come Visual Basic, Visual C# o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f3bbf-135">Use the `JobStep` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span>  
