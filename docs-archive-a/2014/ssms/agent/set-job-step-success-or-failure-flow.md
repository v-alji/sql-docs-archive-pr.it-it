---
title: Impostare il flusso di interventi in caso di esito positivo o negativo del passaggio di processo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, action flow logic
- successful jobs [SQL Server]
- failed jobs [SQL Server]
- jobs [SQL Server Agent], action flow logic
ms.assetid: 23041ccf-8a07-41d3-85b9-c449a54b7e1e
author: stevestein
ms.author: sstein
ms.openlocfilehash: fddc5820676cb231b6f0cd5f7151e24d8eceaefa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726415"
---
# <a name="set-job-step-success-or-failure-flow"></a><span data-ttu-id="80546-102">Impostare il flusso di interventi in caso di esito positivo o negativo del passaggio di processo</span><span class="sxs-lookup"><span data-stu-id="80546-102">Set Job Step Success or Failure Flow</span></span>
  <span data-ttu-id="80546-103">Quando si creano [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] processi di Agent, è possibile specificare l'azione da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] eseguire se si verifica un errore durante l'esecuzione del processo.</span><span class="sxs-lookup"><span data-stu-id="80546-103">When creating [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs, you can specify what action [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] should take if a failure occurs during job execution.</span></span> <span data-ttu-id="80546-104">Determinare l'azione che [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] dovrà eseguire in caso di esito positivo o negativo di ogni passaggio di processo.</span><span class="sxs-lookup"><span data-stu-id="80546-104">Determine the action that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] should take upon the success or failure of each job step.</span></span> <span data-ttu-id="80546-105">Attenersi quindi alla procedura riportata di seguito per configurare la logica del flusso di azioni del passaggio di processo utilizzando [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="80546-105">Then use the following procedure to configure the job step action flow logic by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span>  
  
-   <span data-ttu-id="80546-106">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="80546-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="80546-107">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="80546-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="80546-108">**Per impostare il flusso di interventi in caso di esito positivo o negativo del passaggio di processo utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="80546-108">**To set job step success or failure flow, using:**</span></span>  
  
     [<span data-ttu-id="80546-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="80546-109">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="80546-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="80546-110">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="80546-111">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="80546-111">SQL Server Management Objects</span></span>](#SMO)  
  
## <a name="before-you-begin"></a><span data-ttu-id="80546-112">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="80546-112">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="80546-113">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="80546-113">Security</span></span>  
 <span data-ttu-id="80546-114">Per informazioni dettagliate, vedere [Implementazione della sicurezza di SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="80546-114">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="80546-115">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="80546-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-set-job-step-success-or-failure-flow"></a><span data-ttu-id="80546-116">Per impostare il flusso di interventi in caso di esito positivo o negativo del passaggio di processo</span><span class="sxs-lookup"><span data-stu-id="80546-116">To set job step success or failure flow</span></span>  
  
1.  <span data-ttu-id="80546-117">In **Esplora oggetti**espandere **SQL Server Agent**e quindi **Processi**.</span><span class="sxs-lookup"><span data-stu-id="80546-117">In **Object Explorer**, expand **SQL Server Agent**, and then expand **Jobs**.</span></span>  
  
2.  <span data-ttu-id="80546-118">Fare clic con il pulsante destro del mouse sul processo da modificare e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="80546-118">Right-click the job you want to edit, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="80546-119">Selezionare la pagina **Passaggi** , fare clic su un passaggio e quindi su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="80546-119">Select the **Steps** page, click a step, and then click **Edit**.</span></span>  
  
4.  <span data-ttu-id="80546-120">Nella finestra di dialogo **Proprietà passaggio processo** selezionare la pagina **Avanzate** .</span><span class="sxs-lookup"><span data-stu-id="80546-120">In the **Job Step Properties** dialog box, select the **Advanced** page.</span></span>  
  
5.  <span data-ttu-id="80546-121">Nella finestra di dialogo **Azione in caso di esito positivo**fare clic sull'azione da eseguire se il passaggio del processo viene eseguito correttamente.</span><span class="sxs-lookup"><span data-stu-id="80546-121">In the **On success action**list, click the action to perform if the job step completes successfully.</span></span>  
  
6.  <span data-ttu-id="80546-122">Nella casella **Numero tentativi** immettere un valore compreso tra 0 e 9999 per indicare il numero di ripetizioni desiderate del passaggio prima di stabilirne l'esito negativo.</span><span class="sxs-lookup"><span data-stu-id="80546-122">In the **Retry attempts** box, enter the number of times from 0 through 9999 that the job step should be repeated before it is considered to have failed.</span></span> <span data-ttu-id="80546-123">Se è stato immesso un valore maggiore di 0 nella casella **Numero tentativi** , immettere nella casella **Intervallo tra i tentativi (minuti)** un numero compreso tra 1 e 9999 per indicare i minuti che devono intercorrere tra due tentativi di esecuzione del passaggio del processo.</span><span class="sxs-lookup"><span data-stu-id="80546-123">If you entered a value greater than 0 in the **Retry attempts** box, enter in the **Retry interval (minutes)** box the number of minutes from 1 through 9999 that must pass before the job step is retried.</span></span>  
  
7.  <span data-ttu-id="80546-124">Nell'elenco **In caso di esito negativo** selezionare l'azione da eseguire in caso di esito negativo del passaggio.</span><span class="sxs-lookup"><span data-stu-id="80546-124">In the **On failure action** list, click the action to perform if the job step fails.</span></span>  
  
8.  <span data-ttu-id="80546-125">Se il processo è uno script [!INCLUDE[tsql](../../includes/tsql-md.md)] , è possibile scegliere una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="80546-125">If the job is a [!INCLUDE[tsql](../../includes/tsql-md.md)] script, you can choose from the following options:</span></span>  
  
    -   <span data-ttu-id="80546-126">Nella casella **File di output** immettere il nome di un file di output in cui scrivere l'output dello script.</span><span class="sxs-lookup"><span data-stu-id="80546-126">In the **Output file** box, enter the name of an output file to which the script output will be written.</span></span> <span data-ttu-id="80546-127">Per impostazione predefinita il file viene sovrascritto a ogni esecuzione del passaggio processo.</span><span class="sxs-lookup"><span data-stu-id="80546-127">By default the file is overwritten each time the job step executes.</span></span> <span data-ttu-id="80546-128">Per evitarlo, selezionare **Accoda output a file esistente**.</span><span class="sxs-lookup"><span data-stu-id="80546-128">If you do not want the output file overwritten, check **Append output to existing file**.</span></span>  
  
    -   <span data-ttu-id="80546-129">Selezionare **Registra nella tabella** per registrare il passaggio processo in una tabella di database.</span><span class="sxs-lookup"><span data-stu-id="80546-129">Check **Log to table** if you want to log the job step to a database table.</span></span> <span data-ttu-id="80546-130">Per impostazione predefinita il contenuto della tabella viene sovrascritto a ogni esecuzione del passaggio processo.</span><span class="sxs-lookup"><span data-stu-id="80546-130">By default the table contents are overwritten each time the job step executes.</span></span> <span data-ttu-id="80546-131">Per evitarlo, selezionare **Accoda output a voce esistente nella tabella**.</span><span class="sxs-lookup"><span data-stu-id="80546-131">If you do not want the table contents overwritten, check **Append output to existing entry in table**.</span></span> <span data-ttu-id="80546-132">Dopo l'esecuzione del passaggio processo, è possibile visualizzare il contenuto della tabella facendo clic su **Visualizza**.</span><span class="sxs-lookup"><span data-stu-id="80546-132">After the job step executes, you can view the contents of this table by clicking **View**.</span></span>  
  
    -   <span data-ttu-id="80546-133">Selezionare **Includi output passaggio nella cronologia** se si desidera includere l'output nella cronologia dei passaggi.</span><span class="sxs-lookup"><span data-stu-id="80546-133">Check **Include step output in history** if you want the output included in the step's history.</span></span> <span data-ttu-id="80546-134">L'output verrà visualizzato solo se non si sono verificati errori.</span><span class="sxs-lookup"><span data-stu-id="80546-134">Output will only be shown if there were no errors.</span></span> <span data-ttu-id="80546-135">È inoltre possibile che l'output sia troncato.</span><span class="sxs-lookup"><span data-stu-id="80546-135">Also, output may be truncated.</span></span>  
  
9. <span data-ttu-id="80546-136">Se l'elenco **Esegui come utente** è disponibile selezionare l'account proxy account con le credenziali che verranno utilizzate dal processo.</span><span class="sxs-lookup"><span data-stu-id="80546-136">If the **Run as user** list is available, select the proxy account with the credentials that the job will use.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="80546-137">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="80546-137">Using Transact-SQL</span></span>  
  
#### <a name="to-set-job-step-success-or-failure-flow"></a><span data-ttu-id="80546-138">Per impostare il flusso di interventi in caso di esito positivo o negativo del passaggio di processo</span><span class="sxs-lookup"><span data-stu-id="80546-138">To set job step success or failure flow</span></span>  
  
1.  <span data-ttu-id="80546-139">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="80546-139">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="80546-140">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="80546-140">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="80546-141">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="80546-141">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    USE msdb;  
    GO  
    EXEC sp_add_jobstep  
        @job_name = N'Weekly Sales Data Backup',  
        @step_name = N'Set database to read only',  
        @subsystem = N'TSQL',  
        @command = N'ALTER DATABASE SALES SET READ_ONLY',   
        @on_success_action = 1;  
    GO  
    ```  
  
 <span data-ttu-id="80546-142">Per ulteriori informazioni, vedere [sp_add_jobstep &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="80546-142">For more information, see [sp_add_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="80546-143">Utilizzo di SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="80546-143">Using SQL Server Management Objects</span></span>  

### <a name="to-set-job-step-success-or-failure-flow"></a><span data-ttu-id="80546-144">Per impostare il flusso di interventi in caso di esito positivo o negativo del passaggio di processo</span><span class="sxs-lookup"><span data-stu-id="80546-144">To set job step success or failure flow</span></span>
  
 <span data-ttu-id="80546-145">Usare la classe `JobStep` tramite un linguaggio di programmazione scelto come Visual Basic, Visual C# o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="80546-145">Use the `JobStep` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="80546-146">Per altre informazioni, vedere [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span><span class="sxs-lookup"><span data-stu-id="80546-146">For more information, see [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span></span>  
