---
title: Creare una pianificazione | Microsoft Docs
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
- schedules [SQL Server], jobs
ms.assetid: 8c7ef3b3-c06d-4a27-802d-ed329dc86ef3
author: stevestein
ms.author: sstein
ms.openlocfilehash: ac71a61163dceb06697b61ef24fce2117d57cf2f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636532"
---
# <a name="create-a-schedule"></a><span data-ttu-id="da982-102">Create a Schedule</span><span class="sxs-lookup"><span data-stu-id="da982-102">Create a Schedule</span></span>
  <span data-ttu-id="da982-103">È possibile creare una pianificazione per i processi di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)]o SQL Server Management Objects.</span><span class="sxs-lookup"><span data-stu-id="da982-103">You can create a schedule for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Management Objects.</span></span>  
  
-   <span data-ttu-id="da982-104">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="da982-104">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="da982-105">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="da982-105">Security</span></span>](#Security)  
  
-   <span data-ttu-id="da982-106">**Per creare una pianificazione utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="da982-106">**To create a schedule, using:**</span></span>  
  
     [<span data-ttu-id="da982-107">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="da982-107">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="da982-108">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="da982-108">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="da982-109">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="da982-109">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="da982-110">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="da982-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="da982-111">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="da982-111">Security</span></span>  
 <span data-ttu-id="da982-112">Per informazioni dettagliate, vedere [Implementazione della sicurezza di SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="da982-112">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="da982-113">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="da982-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-schedule"></a><span data-ttu-id="da982-114">Per creare una pianificazione</span><span class="sxs-lookup"><span data-stu-id="da982-114">To create a schedule</span></span>  
  
1.  <span data-ttu-id="da982-115">In **Esplora oggetti** connettersi a un'istanza del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , quindi espandere l'istanza.</span><span class="sxs-lookup"><span data-stu-id="da982-115">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="da982-116">Espandere **SQL Server Agent**, fare clic con il pulsante destro del mouse su **Processi**e scegliere **Gestisci pianificazioni**.</span><span class="sxs-lookup"><span data-stu-id="da982-116">Expand **SQL Server Agent**, right-click **Jobs**, and select **Manage Schedules**.</span></span>  
  
3.  <span data-ttu-id="da982-117">Nella finestra di dialogo **Gestione pianificazioni** fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="da982-117">In the **Manage Schedules** dialog box, click **New**.</span></span>  
  
4.  <span data-ttu-id="da982-118">Nella casella **Nome** digitare un nome per la nuova pianificazione.</span><span class="sxs-lookup"><span data-stu-id="da982-118">In the **Name** box, type a name for the new schedule.</span></span>  
  
5.  <span data-ttu-id="da982-119">Se non si desidera rendere effettiva la pianificazione subito dopo la creazione, deselezionare la casella di controllo **Abilitata** .</span><span class="sxs-lookup"><span data-stu-id="da982-119">If you do not want the schedule to take effect immediately after it has been created, clear the **Enabled** check box.</span></span>  
  
6.  <span data-ttu-id="da982-120">Per **Tipo pianificazione**, selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="da982-120">For **Schedule Type**, select one of the following:</span></span>  
  
    -   <span data-ttu-id="da982-121">Fare clic su **Avvia quando la CPU diventa inattiva**per avviare il processo quando la CPU raggiunge una condizione di inattività.</span><span class="sxs-lookup"><span data-stu-id="da982-121">To start the job when the CPUs reach an idle condition, click **Start whenever the CPUs become idle**.</span></span>  
  
    -   <span data-ttu-id="da982-122">Se si desidera eseguire ripetutamente una pianificazione, fare clic su **Periodica**.</span><span class="sxs-lookup"><span data-stu-id="da982-122">If you want a schedule to run repeatedly, click **Recurring**.</span></span> <span data-ttu-id="da982-123">Per impostare la pianificazione periodica, completare i gruppi **Frequenza**, **Frequenza giornaliera**e **Durata** della finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="da982-123">To set the recurring schedule, complete the **Frequency**, **Daily Frequency**, and **Duration** groups on the dialog.</span></span>  
  
    -   <span data-ttu-id="da982-124">Fare clic su **Singola occorrenza**se si desidera che la pianificazione venga eseguita una sola volta.</span><span class="sxs-lookup"><span data-stu-id="da982-124">If you want the schedule to run only one time, click **One time**.</span></span> <span data-ttu-id="da982-125">Per impostare la pianificazione di tipo **Singola occorrenza** , compilare il gruppo **Singola occorrenza** della finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="da982-125">To set the **One time** schedule, complete the **One-time occurrence** group on the dialog box.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="da982-126">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="da982-126">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-schedule"></a><span data-ttu-id="da982-127">Per creare una pianificazione</span><span class="sxs-lookup"><span data-stu-id="da982-127">To create a schedule</span></span>  
  
1.  <span data-ttu-id="da982-128">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="da982-128">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="da982-129">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="da982-129">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="da982-130">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="da982-130">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- creates a schedule named RunOnce.   
    -- The schedule runs one time, at 23:30 on the day that the schedule is created.  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_add_schedule  
        @schedule_name = N'RunOnce',  
        @freq_type = 1,  
        @active_start_time = 233000 ;  
  
    GO  
    ```  
  
 <span data-ttu-id="da982-131">Per ulteriori informazioni, vedere [sp_add_schedule &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-add-schedule-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="da982-131">For more information, see [sp_add_schedule &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-schedule-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="da982-132">Utilizzo di SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="da982-132">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="da982-133">**Per creare una pianificazione**</span><span class="sxs-lookup"><span data-stu-id="da982-133">**To create a schedule**</span></span>  
  
 <span data-ttu-id="da982-134">Usare la classe `JobSchedule` tramite un linguaggio di programmazione scelto come Visual Basic, Visual C# o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="da982-134">Use the `JobSchedule` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="da982-135">Per altre informazioni, vedere [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span><span class="sxs-lookup"><span data-stu-id="da982-135">For more information, see [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span></span>  
