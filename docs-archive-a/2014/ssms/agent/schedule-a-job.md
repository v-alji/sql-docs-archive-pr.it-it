---
title: Pianificare un processo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- scheduling jobs [SQL Server]
- SQL Server Agent jobs, scheduling
- jobs [SQL Server Agent], scheduling
ms.assetid: f626390a-a3df-4970-b7a7-a0529e4a109c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1077766d6853ed7c029b8eefa76515c89ad861fd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715004"
---
# <a name="schedule-a-job"></a><span data-ttu-id="e0954-102">Schedule a Job</span><span class="sxs-lookup"><span data-stu-id="e0954-102">Schedule a Job</span></span>
  <span data-ttu-id="e0954-103">In questo argomento viene descritto come pianificare un processo di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="e0954-103">This topic describes how to schedule a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job.</span></span>  
  
-   <span data-ttu-id="e0954-104">**Prima di iniziare:** ,</span><span class="sxs-lookup"><span data-stu-id="e0954-104">**Before you begin:** ,</span></span>  
  
     [<span data-ttu-id="e0954-105">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="e0954-105">Security</span></span>](#Security)  
  
-   <span data-ttu-id="e0954-106">**Per pianificare un processo utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="e0954-106">**To schedule a job, using:**</span></span>  
  
     [<span data-ttu-id="e0954-107">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e0954-107">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="e0954-108">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e0954-108">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="e0954-109">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="e0954-109">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="e0954-110">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="e0954-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="e0954-111">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="e0954-111">Security</span></span>  
 <span data-ttu-id="e0954-112">Per informazioni dettagliate, vedere [Implementazione della sicurezza di SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="e0954-112">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="e0954-113">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e0954-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-and-attach-a-schedule-to-a-job"></a><span data-ttu-id="e0954-114">Per creare e collegare una pianificazione a un processo</span><span class="sxs-lookup"><span data-stu-id="e0954-114">To create and attach a schedule to a job</span></span>  
  
1.  <span data-ttu-id="e0954-115">In **Esplora oggetti** connettersi a un'istanza del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , quindi espandere l'istanza.</span><span class="sxs-lookup"><span data-stu-id="e0954-115">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="e0954-116">Espandere **SQL Server Agent**, espandere **Processi**, fare clic con il pulsante destro del mouse sul processo che si vuole pianificare e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="e0954-116">Expand **SQL Server Agent**, expand **Jobs**, right-click the job you want to schedule, and click **Properties**.</span></span>  
  
3.  <span data-ttu-id="e0954-117">Selezionare la pagina **Pianificazioni** e quindi fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="e0954-117">Select the **Schedules** page, and then click **New**.</span></span>  
  
4.  <span data-ttu-id="e0954-118">Nella casella **Nome** digitare un nome per la nuova pianificazione.</span><span class="sxs-lookup"><span data-stu-id="e0954-118">In the **Name** box, type a name for the new schedule.</span></span>  
  
5.  <span data-ttu-id="e0954-119">Deselezionare la casella di controllo **Abilitata** se non si desidera attivare la pianificazione subito dopo la relativa creazione.</span><span class="sxs-lookup"><span data-stu-id="e0954-119">Clear the **Enabled** check box if you do not want the schedule to take effect immediately following its creation.</span></span>  
  
6.  <span data-ttu-id="e0954-120">Per **Tipo pianificazione**, selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e0954-120">For **Schedule Type**, select one of the following:</span></span>  
  
    -   <span data-ttu-id="e0954-121">Fare clic su **Avvia automaticamente all'avvio di SQL Server Agent** per avviare il processo all'avvio del servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="e0954-121">Click **Start automatically when SQL Server Agent starts** to start the job when the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service is started.</span></span>  
  
    -   <span data-ttu-id="e0954-122">Fare clic su **Avvia quando la CPU diventa inattiva** per avviare il processo quando la CPU raggiunge una condizione di inattività.</span><span class="sxs-lookup"><span data-stu-id="e0954-122">Click **Start whenever the CPUs become idle** to start the job when the CPUs reach an idle condition.</span></span>  
  
    -   <span data-ttu-id="e0954-123">Fare clic su **Periodica** se si desidera eseguire ripetutamente una pianificazione.</span><span class="sxs-lookup"><span data-stu-id="e0954-123">Click **Recurring** if you want a schedule to run repeatedly.</span></span> <span data-ttu-id="e0954-124">Per impostare la pianificazione periodica, completare i gruppi **Frequenza**, **Frequenza giornaliera**e **Durata** della finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="e0954-124">To set the recurring schedule, complete the **Frequency**, **Daily Frequency**, and **Duration** groups on the dialog.</span></span>  
  
    -   <span data-ttu-id="e0954-125">Fare clic su **Singola occorrenza** se si desidera che la pianificazione venga eseguita una sola volta.</span><span class="sxs-lookup"><span data-stu-id="e0954-125">Click **One time** if you want the schedule to run only once.</span></span> <span data-ttu-id="e0954-126">Per impostare la pianificazione di tipo **Singola occorrenza** , completare il gruppo **Singola occorrenza** nella finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="e0954-126">To set the **One time** schedule, complete the **One-time occurrence** group on the dialog.</span></span>  
  
#### <a name="to-attach-a-schedule-to-a-job"></a><span data-ttu-id="e0954-127">Per collegare una pianificazione a un processo</span><span class="sxs-lookup"><span data-stu-id="e0954-127">To attach a schedule to a job</span></span>  
  
1.  <span data-ttu-id="e0954-128">In **Esplora oggetti** connettersi a un'istanza del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , quindi espandere l'istanza.</span><span class="sxs-lookup"><span data-stu-id="e0954-128">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="e0954-129">Espandere **SQL Server Agent**, espandere **Processi**, fare clic con il pulsante destro del mouse sul processo che si vuole pianificare e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="e0954-129">Expand **SQL Server Agent**, expand **Jobs**, right-click the job that you want to schedule, and click **Properties**.</span></span>  
  
3.  <span data-ttu-id="e0954-130">Selezionare la pagina **Pianificazioni** , quindi fare clic su **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="e0954-130">Select the **Schedules** page, and then click **Pick**.</span></span>  
  
4.  <span data-ttu-id="e0954-131">Selezionare la pianificazione da collegare, quindi scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="e0954-131">Select the schedule that you want to attach, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="e0954-132">Nella finestra di dialogo **Proprietà processo** , fare doppio clic sulla pianificazione collegata.</span><span class="sxs-lookup"><span data-stu-id="e0954-132">In the **Job Properties** dialog box, double-click the attached schedule.</span></span>  
  
6.  <span data-ttu-id="e0954-133">Verificare che l'opzione **Data inizio** sia impostata correttamente.</span><span class="sxs-lookup"><span data-stu-id="e0954-133">Verify that **Start date** is set correctly.</span></span> <span data-ttu-id="e0954-134">In caso contrario, impostare la data desiderata per l'avvio della pianificazione, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="e0954-134">If it is not, set the date when you want for the schedule to start, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="e0954-135">Nella finestra di dialogo **Proprietà processo** scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="e0954-135">In the **Job Properties** dialog box, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="e0954-136">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e0954-136">Using Transact-SQL</span></span>  
  
#### <a name="to-schedule-a-job"></a><span data-ttu-id="e0954-137">Per pianificare un processo</span><span class="sxs-lookup"><span data-stu-id="e0954-137">To schedule a job</span></span>  
  
1.  <span data-ttu-id="e0954-138">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e0954-138">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="e0954-139">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="e0954-139">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="e0954-140">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="e0954-140">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    USE msdb ;  
    GO  
    -- creates a schedule named NightlyJobs.   
    -- Jobs that use this schedule execute every day when the time on the server is 01:00.   
    EXEC sp_add_schedule  
        @schedule_name = N'NightlyJobs' ,  
        @freq_type = 4,  
        @freq_interval = 1,  
        @active_start_time = 010000 ;  
    GO  
    -- attaches the schedule to the job BackupDatabase  
    EXEC sp_attach_schedule  
       @job_name = N'BackupDatabase',  
       @schedule_name = N'NightlyJobs' ;  
    GO  
    ```  
  
 <span data-ttu-id="e0954-141">Per ulteriori informazioni, vedere [sp_add_schedule &#40;&#41;Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-add-schedule-transact-sql) e [sp_attach_schedule &#40;transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-attach-schedule-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e0954-141">For more information, see [sp_add_schedule &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-schedule-transact-sql) and [sp_attach_schedule &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-attach-schedule-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="e0954-142">Utilizzo di SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="e0954-142">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="e0954-143">Usare la classe `JobSchedule` tramite un linguaggio di programmazione scelto come Visual Basic, Visual C# o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e0954-143">Use the `JobSchedule` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="e0954-144">Per altre informazioni, vedere[SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span><span class="sxs-lookup"><span data-stu-id="e0954-144">For more information, see[SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span></span>  
