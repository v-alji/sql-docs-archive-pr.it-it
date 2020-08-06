---
title: Creare un passaggio di processo con script ActiveX | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- ActiveX scripting jobs [SQL Server]
- job steps [Analysis Services]
ms.assetid: e6c46c6b-2d61-4571-bc8e-a831cd6e6302
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6604ba75af7acdd5bd2521433e8310c74150ce8f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711583"
---
# <a name="create-an-activex-script-job-step"></a><span data-ttu-id="0ecc7-102">Create an ActiveX Script Job Step</span><span class="sxs-lookup"><span data-stu-id="0ecc7-102">Create an ActiveX Script Job Step</span></span>
  <span data-ttu-id="0ecc7-103">In questo argomento viene descritto come creare e definire un [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] passaggio di processo di Agent in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] che esegue uno script ActiveX utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , [!INCLUDE[tsql](../../includes/tsql-md.md)] o SQL Server Management Objects.</span><span class="sxs-lookup"><span data-stu-id="0ecc7-103">This topic describes how to create and define a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job step in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] that executes an ActiveX script by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Management Objects.</span></span>  
  
-   <span data-ttu-id="0ecc7-104">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="0ecc7-104">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="0ecc7-105">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="0ecc7-105">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="0ecc7-106">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="0ecc7-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="0ecc7-107">**Per creare un passaggio di processo Transact-SQL utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="0ecc7-107">**To create a Transact-SQL job step, using:**</span></span>  
  
     [<span data-ttu-id="0ecc7-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0ecc7-108">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="0ecc7-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0ecc7-109">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="0ecc7-110">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="0ecc7-110">SQL Server Management Objects</span></span>](#SMO)  
  
## <a name="before-you-begin"></a><span data-ttu-id="0ecc7-111">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="0ecc7-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="0ecc7-112">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="0ecc7-112">Limitations and Restrictions</span></span>  
 [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)]  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="0ecc7-113">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="0ecc7-113">Security</span></span>  
 <span data-ttu-id="0ecc7-114">Per informazioni dettagliate, vedere [Implementazione della sicurezza di SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="0ecc7-114">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="0ecc7-115">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0ecc7-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-an-activex-script-job-step"></a><span data-ttu-id="0ecc7-116">Per creare un passaggio di processo Script ActiveX</span><span class="sxs-lookup"><span data-stu-id="0ecc7-116">To create an ActiveX Script job step</span></span>  
  
1.  <span data-ttu-id="0ecc7-117">In **Esplora oggetti** connettersi a un'istanza del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , quindi espandere l'istanza.</span><span class="sxs-lookup"><span data-stu-id="0ecc7-117">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="0ecc7-118">Espandere **SQL Server Agent**, creare un nuovo processo oppure fare clic con il pulsante destro del mouse su un processo esistente e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="0ecc7-118">Expand **SQL Server Agent**, create a new job or right-click an existing job, and then click **Properties**.</span></span> <span data-ttu-id="0ecc7-119">Per ulteriori informazioni sulla creazione di un processo, vedere [Creazione di processi](create-jobs.md).</span><span class="sxs-lookup"><span data-stu-id="0ecc7-119">For more information on creating a job, see [Creating Jobs](create-jobs.md).</span></span>  
  
3.  <span data-ttu-id="0ecc7-120">Nella finestra di dialogo **Proprietà processo** fare clic sulla pagina **Passaggi** e quindi su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="0ecc7-120">In the **Job Properties** dialog, click the **Steps** page, and then click **New**.</span></span>  
  
4.  <span data-ttu-id="0ecc7-121">Nella finestra di dialogo **Nuovo passaggio di processo** digitare il nome del passaggio del processo nella casella **Nome passaggio**.</span><span class="sxs-lookup"><span data-stu-id="0ecc7-121">In the **New Job Step** dialog, type a job **Step name**.</span></span>  
  
5.  <span data-ttu-id="0ecc7-122">Nell'elenco **Tipo** fare clic su **Script ActiveX**.</span><span class="sxs-lookup"><span data-stu-id="0ecc7-122">In the **Type** list, click **ActiveX Script**.</span></span>  
  
6.  <span data-ttu-id="0ecc7-123">Nell'elenco **Esegui come** selezionare l'account proxy con le credenziali che verranno utilizzate dal processo.</span><span class="sxs-lookup"><span data-stu-id="0ecc7-123">In the **Run as** list, select the proxy account with the credentials that the job will use.</span></span>  
  
7.  <span data-ttu-id="0ecc7-124">Nella casella **Linguaggio** selezionare il linguaggio in cui è stato scritto lo script.</span><span class="sxs-lookup"><span data-stu-id="0ecc7-124">Select the **Language** in which the script was written.</span></span> <span data-ttu-id="0ecc7-125">In alternativa, è possibile fare clic su **Altro** e quindi immettere il nome del linguaggio di scripting [!INCLUDE[msCoName](../../includes/msconame-md.md)] ActiveX in cui verrà scritto lo script.</span><span class="sxs-lookup"><span data-stu-id="0ecc7-125">Alternatively, click **Other** and then enter the name of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] ActiveX scripting language in which the script will be written.</span></span>  
  
8.  <span data-ttu-id="0ecc7-126">Nella casella **Comando** immettere la sintassi dello script che verrà eseguito per il passaggio di processo.</span><span class="sxs-lookup"><span data-stu-id="0ecc7-126">In the **Command** box, enter the script syntax that will be executed for the job step.</span></span> <span data-ttu-id="0ecc7-127">In alternativa, è possibile fare clic su **Apri** e selezionare un file contenente la sintassi dello script.</span><span class="sxs-lookup"><span data-stu-id="0ecc7-127">Alternately, click **Open** and select a file containing the script syntax.</span></span>  
  
9. <span data-ttu-id="0ecc7-128">Fare clic sulla pagina **Avanzate** per impostare le opzioni seguenti relative al passaggio di processo: l'azione da eseguire in caso di esito positivo o negativo del passaggio, il numero di tentativi di esecuzione del passaggio che devono essere effettuati da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent e gli intervalli tra tentativi successivi.</span><span class="sxs-lookup"><span data-stu-id="0ecc7-128">Click the **Advanced** page to set the following job step options: what action to take if the job step succeeds or fails, how many times [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent should try to execute the job step, and how often retry attempts should be made.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="0ecc7-129">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0ecc7-129">Using Transact-SQL</span></span>  
  
#### <a name="to-create-an-activex-script-job-step"></a><span data-ttu-id="0ecc7-130">Per creare un passaggio di processo Script ActiveX</span><span class="sxs-lookup"><span data-stu-id="0ecc7-130">To create an ActiveX Script job step</span></span>  
  
1.  <span data-ttu-id="0ecc7-131">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0ecc7-131">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="0ecc7-132">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="0ecc7-132">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="0ecc7-133">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="0ecc7-133">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- create an ActiveX Script job step written in VBScript that creates a restore point  
    USE msdb;  
    GO  
    EXEC sp_add_jobstep  
        @job_name = N'Weekly Sales Data Backup',  
        @step_name = N'Create a restore point',  
        @subsystem = N'ACTIVESCRIPTING',  
        @command = N'Const RESTORE_POINT = 20  
  
    strComputer = "."  
    Set objWMIService = GetObject("winmgmts:" _  
        & "{impersonationLevel=impersonate}!\\" & strComputer & "\root\default")  
  
    Set objItem = objWMIService.Get("SystemRestore")  
    errResults = objItem.Restore(RESTORE_POINT)',   
        @retry_attempts = 5,  
        @retry_interval = 5 ;  
    GO  
    ```  
  
 <span data-ttu-id="0ecc7-134">Per ulteriori informazioni, vedere [sp_add_jobstep &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0ecc7-134">For more information, see [sp_add_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="0ecc7-135">Utilizzo di SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="0ecc7-135">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="0ecc7-136">**Per creare un passaggio di processo Script ActiveX**</span><span class="sxs-lookup"><span data-stu-id="0ecc7-136">**To create an ActiveX Script job step**</span></span>  
  
 <span data-ttu-id="0ecc7-137">Usare la classe `JobStep` tramite un linguaggio di programmazione scelto come Visual Basic, Visual C# o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0ecc7-137">Use the `JobStep` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span>  
