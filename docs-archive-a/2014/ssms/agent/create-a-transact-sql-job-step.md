---
title: Creare un passaggio di processo Transact-SQL | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- Transact-SQL job step
- job steps [Transact-SQL]
- SQL Server Agent jobs, Transact-SQL step
ms.assetid: 69c571a7-debe-4063-9d38-e4b6a1e8e84c
author: stevestein
ms.author: sstein
ms.openlocfilehash: b83ee944d2ca5c10ff1b77f3e6e6da6054b5c99a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722211"
---
# <a name="create-a-transact-sql-job-step"></a><span data-ttu-id="65914-102">Create a Transact-SQL Job Step</span><span class="sxs-lookup"><span data-stu-id="65914-102">Create a Transact-SQL Job Step</span></span>
  <span data-ttu-id="65914-103">In questo argomento viene descritto come creare un [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] passaggio di processo di Agent per l'esecuzione [!INCLUDE[tsql](../../includes/tsql-md.md)] di script in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , [!INCLUDE[tsql](../../includes/tsql-md.md)] o SQL Server Management Objects.</span><span class="sxs-lookup"><span data-stu-id="65914-103">This topic describes how to create a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job step that executes [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Management Objects.</span></span>  
  
 <span data-ttu-id="65914-104">Gli script per passaggi di processo possono chiamare stored procedure e stored procedure estese.</span><span class="sxs-lookup"><span data-stu-id="65914-104">These job step scripts may call stored procedures and extended stored procedures.</span></span> <span data-ttu-id="65914-105">Un singolo passaggio di processo [!INCLUDE[tsql](../../includes/tsql-md.md)] può contenere più batch e comandi GO incorporati.</span><span class="sxs-lookup"><span data-stu-id="65914-105">A single [!INCLUDE[tsql](../../includes/tsql-md.md)] job step can contain multiple batches and embedded GO commands.</span></span> <span data-ttu-id="65914-106">Per ulteriori informazioni sulla creazione di un processo, vedere [Creazione di processi](create-jobs.md).</span><span class="sxs-lookup"><span data-stu-id="65914-106">For more information on creating a job, see [Creating Jobs](create-jobs.md).</span></span>  
  
 <span data-ttu-id="65914-107">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="65914-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="65914-108">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="65914-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="65914-109">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="65914-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="65914-110">**Per creare un passaggio di processo Transact-SQL utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="65914-110">**To create a Transact-SQL job step, using:**</span></span>  
  
     [<span data-ttu-id="65914-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="65914-111">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="65914-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="65914-112">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="65914-113">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="65914-113">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="65914-114">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="65914-114">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="65914-115">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="65914-115">Security</span></span>  
 <span data-ttu-id="65914-116">Per informazioni dettagliate, vedere [Implementazione della sicurezza di SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="65914-116">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="65914-117">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="65914-117">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-transact-sql-job-step"></a><span data-ttu-id="65914-118">Per creare un passaggio di processo Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="65914-118">To create a Transact-SQL job step</span></span>  
  
1.  <span data-ttu-id="65914-119">In **Esplora oggetti** connettersi a un'istanza del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , quindi espandere l'istanza.</span><span class="sxs-lookup"><span data-stu-id="65914-119">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="65914-120">Espandere **SQL Server Agent**, creare un nuovo processo oppure fare clic con il pulsante destro del mouse su un processo esistente e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="65914-120">Expand **SQL Server Agent**, create a new job or right-click an existing job, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="65914-121">Nella finestra di dialogo **Proprietà processo** fare clic sulla pagina **Passaggi** e quindi su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="65914-121">In the **Job Properties** dialog, click the **Steps** page, and then click **New**.</span></span>  
  
4.  <span data-ttu-id="65914-122">Nella finestra di dialogo **Nuovo passaggio di processo** digitare il nome del passaggio del processo nella casella **Nome passaggio**.</span><span class="sxs-lookup"><span data-stu-id="65914-122">In the **New Job Step** dialog, type a job **Step name**.</span></span>  
  
5.  <span data-ttu-id="65914-123">Nell'elenco **Tipo** fare clic su **Transact-SQL Script (TSQL)**.</span><span class="sxs-lookup"><span data-stu-id="65914-123">In the **Type** list, click **Transact-SQL Script (TSQL)**.</span></span>  
  
6.  <span data-ttu-id="65914-124">Nella casella **Comando** digitare i batch di comandi [!INCLUDE[tsql](../../includes/tsql-md.md)] oppure fare clic su **Apri** per selezionare un file [!INCLUDE[tsql](../../includes/tsql-md.md)] da utilizzare come comando.</span><span class="sxs-lookup"><span data-stu-id="65914-124">In the **Command** box, type the [!INCLUDE[tsql](../../includes/tsql-md.md)] command batches, or click **Open** to select a [!INCLUDE[tsql](../../includes/tsql-md.md)] file to use as the command.</span></span>  
  
7.  <span data-ttu-id="65914-125">Fare clic su **Analizza** per controllare la sintassi.</span><span class="sxs-lookup"><span data-stu-id="65914-125">Click **Parse** to check your syntax.</span></span>  
  
8.  <span data-ttu-id="65914-126">Se la sintassi è corretta, viene visualizzato un messaggio che informa che l'analisi è stata completata.</span><span class="sxs-lookup"><span data-stu-id="65914-126">The message "Parse succeeded" is displayed when your syntax is correct.</span></span> <span data-ttu-id="65914-127">Se viene rilevato un errore, correggere la sintassi prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="65914-127">If an error is found, correct the syntax before continuing.</span></span>  
  
9. <span data-ttu-id="65914-128">Fare clic sulla pagina **Avanzate** per impostare le opzioni del passaggio di processo, ad esempio l'azione che verrà eseguita se il passaggio di processo ha esito positivo o negativo, il numero di tentativi di esecuzione del passaggio che verranno eseguiti da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent e il file o la tabella in cui [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent scriverà l'output del passaggio di processo.</span><span class="sxs-lookup"><span data-stu-id="65914-128">Click the **Advanced** page to set job step options, such as: what action to take if the job step succeeds or fails, how many times [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent should try to execute the job step, and the file or table where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent can write the job step output.</span></span> <span data-ttu-id="65914-129">L'output del passaggio di processo può essere scritto in un file di sistema unicamente dai membri del ruolo predefinito del server **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="65914-129">Only members of the **sysadmin** fixed server role can write job step output to an operating system file.</span></span> <span data-ttu-id="65914-130">Gli utenti di SQL Server Agent possono registrare l'output in una tabella.</span><span class="sxs-lookup"><span data-stu-id="65914-130">All SQL Server Agent users can log output to a table.</span></span>  
  
10. <span data-ttu-id="65914-131">Se l'utente è membro del ruolo predefinito del server **sysadmin** e intende eseguire questo passaggio di processo con un diverso account di accesso SQL, selezionare l'account di accesso SQL dall'elenco **Esegui come utente** .</span><span class="sxs-lookup"><span data-stu-id="65914-131">If you are a member of the **sysadmin** fixed server role and you want to run this job step as a different SQL login, select the SQL login from the **Run as user** list.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="65914-132">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="65914-132">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-transact-sql-job-step"></a><span data-ttu-id="65914-133">Per creare un passaggio di processo Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="65914-133">To create a Transact-SQL job step</span></span>  
  
1.  <span data-ttu-id="65914-134">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="65914-134">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="65914-135">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="65914-135">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="65914-136">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="65914-136">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- creates a job step that uses Transact-SQL  
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
  
 <span data-ttu-id="65914-137">Per ulteriori informazioni, vedere [sp_add_jobstep &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="65914-137">For more information, see [sp_add_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="65914-138">Utilizzo di SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="65914-138">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="65914-139">**Per creare un passaggio di processo Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="65914-139">**To create a Transact-SQL job step**</span></span>  
  
 <span data-ttu-id="65914-140">Usare la classe `JobStep` tramite un linguaggio di programmazione scelto come Visual Basic, Visual C# o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="65914-140">Use the `JobStep` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span>  
