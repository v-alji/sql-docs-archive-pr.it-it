---
title: Creare un passaggio di processo di CmdExec | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- CmdExec jobs
ms.assetid: b48da5b4-6fe7-4eb7-bade-dc7d697c6d5c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 48c557b8ea4228d27b73d361c50aac62232d1e00
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628063"
---
# <a name="create-a-cmdexec-job-step"></a><span data-ttu-id="6d4b9-102">Create a CmdExec Job Step</span><span class="sxs-lookup"><span data-stu-id="6d4b9-102">Create a CmdExec Job Step</span></span>
  <span data-ttu-id="6d4b9-103">In questo argomento viene descritto come creare e definire un [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] passaggio di processo di Agent in in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] cui viene utilizzato un programma eseguibile o un comando del sistema operativo tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , [!INCLUDE[tsql](../../includes/tsql-md.md)] o SQL Server Management Objects.</span><span class="sxs-lookup"><span data-stu-id="6d4b9-103">This topic describes how to create and define a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job step in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] that uses an executable program or operating system command by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)] or SQL Server Management Objects.</span></span>  
  
 <span data-ttu-id="6d4b9-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="6d4b9-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="6d4b9-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="6d4b9-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="6d4b9-106">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="6d4b9-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="6d4b9-107">**Per creare un passaggio di processo di CmdExec utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="6d4b9-107">**To create a CmdExec job step, using:**</span></span>  
  
     [<span data-ttu-id="6d4b9-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6d4b9-108">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="6d4b9-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6d4b9-109">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="6d4b9-110">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="6d4b9-110">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="6d4b9-111">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="6d4b9-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="6d4b9-112">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="6d4b9-112">Security</span></span>  
 <span data-ttu-id="6d4b9-113">Per impostazione predefinita, solo i membri del ruolo predefinito del server **sysadmin** possono creare passaggi di processo CmdExec.</span><span class="sxs-lookup"><span data-stu-id="6d4b9-113">By default, only members of the **sysadmin** fixed server role can create CmdExec job steps.</span></span> <span data-ttu-id="6d4b9-114">Questi passaggi di processo vengono eseguiti nel contesto dell'account di servizio SQL Server Agent a meno che l'utente **sysadmin** crei un account proxy.</span><span class="sxs-lookup"><span data-stu-id="6d4b9-114">These job steps run under the context of the SQL Server Agent service account unless the **sysadmin** user creates a proxy account.</span></span> <span data-ttu-id="6d4b9-115">Gli utenti che non sono membri del ruolo **sysadmin** possono creare passaggi di processo CmdExec se hanno accesso a un account proxy CmdExec.</span><span class="sxs-lookup"><span data-stu-id="6d4b9-115">Users who are not members of the **sysadmin** role can create CmdExec job steps if they have access to a CmdExec proxy account.</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="6d4b9-116">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="6d4b9-116">Permissions</span></span>  
 <span data-ttu-id="6d4b9-117">Per informazioni dettagliate, vedere [Implementazione della sicurezza di SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="6d4b9-117">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="6d4b9-118">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6d4b9-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-cmdexec-job-step"></a><span data-ttu-id="6d4b9-119">Per creare un passaggio del processo di CmdExec</span><span class="sxs-lookup"><span data-stu-id="6d4b9-119">To create a CmdExec job step</span></span>  
  
1.  <span data-ttu-id="6d4b9-120">In **Esplora oggetti** connettersi a un'istanza del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , quindi espandere l'istanza.</span><span class="sxs-lookup"><span data-stu-id="6d4b9-120">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="6d4b9-121">Espandere **SQL Server Agent**, creare un nuovo processo oppure fare clic con il pulsante destro del mouse su un processo esistente e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="6d4b9-121">Expand **SQL Server Agent**, create a new job or right-click an existing job, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="6d4b9-122">Nella finestra di dialogo **Proprietà processo** fare clic sulla pagina **Passaggi** e quindi su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="6d4b9-122">In the **Job Properties** dialog, click the **Steps** page, and then click **New**.</span></span>  
  
4.  <span data-ttu-id="6d4b9-123">Nella finestra di dialogo **Nuovo passaggio di processo** digitare il nome del passaggio del processo nella casella **Nome passaggio**.</span><span class="sxs-lookup"><span data-stu-id="6d4b9-123">In the **New Job Step** dialog, type a job **Step name**.</span></span>  
  
5.  <span data-ttu-id="6d4b9-124">Nell'elenco **Tipo** selezionare **Sistema operativo (CmdExec)**.</span><span class="sxs-lookup"><span data-stu-id="6d4b9-124">In the **Type** list, choose **Operating system (CmdExec)**.</span></span>  
  
6.  <span data-ttu-id="6d4b9-125">Nell'elenco **Esegui come** selezionare l'account proxy con le credenziali che verranno utilizzate dal processo.</span><span class="sxs-lookup"><span data-stu-id="6d4b9-125">In **Run as** list, select the proxy account with the credentials that the job will use.</span></span> <span data-ttu-id="6d4b9-126">Per impostazione predefinita, questi passaggi di processo vengono eseguiti nel contesto dell'account di servizio SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="6d4b9-126">By default, CmdExec job steps run under the context of the SQL Server Agent service account.</span></span>  
  
7.  <span data-ttu-id="6d4b9-127">Nella casella **Elabora codice di uscita di un comando eseguito correttamente** digitare un valore compreso tra 0 e 999999.</span><span class="sxs-lookup"><span data-stu-id="6d4b9-127">In the **Process exit code of a successful command** box, enter a value from 0 to 999999.</span></span>  
  
8.  <span data-ttu-id="6d4b9-128">Nella casella **Comando** digitare il comando di sistema operativo o programma eseguibile.</span><span class="sxs-lookup"><span data-stu-id="6d4b9-128">In the **Command** box, enter the operating system command or executable program.</span></span> <span data-ttu-id="6d4b9-129">Per un esempio vedere "Utilizzo di Transact-SQL".</span><span class="sxs-lookup"><span data-stu-id="6d4b9-129">See "Using Transact T-SQL for an example.</span></span>  
  
9. <span data-ttu-id="6d4b9-130">Fare clic sulla pagina **Avanzate** per impostare le opzioni relative ai passaggi di processo, ad esempio l'operazione da eseguire se il passaggio di processo ha esito positivo o negativo, il numero di tentativi che devono essere eseguiti da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent per l'esecuzione del passaggio di processo e il file in cui [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent può scrivere l'output del passaggio di processo.</span><span class="sxs-lookup"><span data-stu-id="6d4b9-130">Click the **Advanced** page to set job step options, such as: what action to take if the job step succeeds or fails, how many times [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent should try to execute the job step, and the file where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent can write the job step output.</span></span> <span data-ttu-id="6d4b9-131">L'output del passaggio di processo può essere scritto in un file di sistema unicamente dai membri del ruolo predefinito del server **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="6d4b9-131">Only members of the **sysadmin** fixed server role can write job step output to an operating system file.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="6d4b9-132">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6d4b9-132">Using Transact-SQL</span></span>  
  
### <a name="to-create-a-cmdexec-job-step"></a><span data-ttu-id="6d4b9-133">Per creare un passaggio del processo di CmdExec</span><span class="sxs-lookup"><span data-stu-id="6d4b9-133">To create a CmdExec job step</span></span>  
  
1.  <span data-ttu-id="6d4b9-134">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6d4b9-134">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="6d4b9-135">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="6d4b9-135">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="6d4b9-136">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="6d4b9-136">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- creates a job step that uses CmdExec  
    USE msdb;  
    GO  
    EXEC sp_add_jobstep  
        @job_name = N'Weekly Sales Data Backup',  
        @step_name = N'Set database to read only',  
        @subsystem = N'CMDEXEC',  
        @command = C:\clickme_scripts\SQL11\PostBOLReorg GetHsX.exe',   
        @retry_attempts = 5,  
        @retry_interval = 5 ;  
    GO  
    ```  
  
 <span data-ttu-id="6d4b9-137">Per ulteriori informazioni, vedere [sp_add_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="6d4b9-137">For more information, see [sp_add_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql)</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="6d4b9-138">Utilizzo di SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="6d4b9-138">Using SQL Server Management Objects</span></span>  

### <a name="to-create-a-cmdexec-job-step"></a><span data-ttu-id="6d4b9-139">Per creare un passaggio del processo di CmdExec</span><span class="sxs-lookup"><span data-stu-id="6d4b9-139">To create a CmdExec job step</span></span>
  
 <span data-ttu-id="6d4b9-140">Usare la classe `JobStep` tramite un linguaggio di programmazione scelto come Visual Basic, Visual C# o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6d4b9-140">Use the `JobStep` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span>  
