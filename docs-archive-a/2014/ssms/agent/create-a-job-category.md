---
title: Creare una categoria di processi | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, categories
- jobs [SQL Server Agent], categories
- categories [SQL Server Agent jobs]
ms.assetid: e24a6d38-d231-4f64-ab89-2d1ef6f5792c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1f6daeeca6253861e8a9dcbb72faa2bd55eb2761
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720802"
---
# <a name="create-a-job-category"></a><span data-ttu-id="fb837-102">Creare una categoria di processi</span><span class="sxs-lookup"><span data-stu-id="fb837-102">Create a Job Category</span></span>
  <span data-ttu-id="fb837-103">In questo argomento si descrive come creare una categoria di processi in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)] o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Objects.</span><span class="sxs-lookup"><span data-stu-id="fb837-103">This topic describes how to create a job category in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)] or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Objects.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="fb837-104">Agent offre categorie di processi predefinite a cui possono essere assegnati processi. In alternativa, è possibile creare una nuova categoria e assegnarvi i processi.</span><span class="sxs-lookup"><span data-stu-id="fb837-104">Agent provides built-in job categories that you can assign jobs to, or you can create a job category and assign jobs to it.</span></span> <span data-ttu-id="fb837-105">Le categorie consentono di organizzare i processi per semplificare le operazioni di raggruppamento e filtro.</span><span class="sxs-lookup"><span data-stu-id="fb837-105">Job categories help you organize your jobs for easy filtering and grouping.</span></span> <span data-ttu-id="fb837-106">È ad esempio possibile organizzare tutti i processi di backup dei database raggruppandoli nella categoria Manutenzione database.</span><span class="sxs-lookup"><span data-stu-id="fb837-106">For example, you can organize all your database backup jobs in the Database Maintenance category.</span></span> <span data-ttu-id="fb837-107">È inoltre possibile creare categorie di processi personalizzate.</span><span class="sxs-lookup"><span data-stu-id="fb837-107">You can also create your own job categories.</span></span>  
  
 
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="fb837-108">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="fb837-108">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="fb837-109">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="fb837-109">Limitations and Restrictions</span></span>  
 <span data-ttu-id="fb837-110">Le categorie multiserver sono disponibili solo in un server master.</span><span class="sxs-lookup"><span data-stu-id="fb837-110">Multiserver categories exist only on a master server.</span></span> <span data-ttu-id="fb837-111">In un server master è disponibile una sola categoria di processi predefinita: [**Senza categoria (multiserver)**].</span><span class="sxs-lookup"><span data-stu-id="fb837-111">There is only one default job category available on a master server: [**Uncategorized (Multi-Server)**].</span></span> <span data-ttu-id="fb837-112">Quando viene scaricato un processo multiserver, la categoria viene modificata in **Processi dal server MSX** nel server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="fb837-112">When a multiserver job is downloaded, its category is changed to **Jobs From MSX** at the target server.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="fb837-113">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="fb837-113">Security</span></span>  
 <span data-ttu-id="fb837-114">Per informazioni dettagliate, vedere [Implementazione della sicurezza di SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="fb837-114">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="fb837-115">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="fb837-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-job-category"></a><span data-ttu-id="fb837-116">Per creare una categoria di processi</span><span class="sxs-lookup"><span data-stu-id="fb837-116">To create a job category</span></span>  
  
1.  <span data-ttu-id="fb837-117">In **Esplora oggetti**fare clic sul segno più per espandere il server in cui si desidera creare una categoria di processi.</span><span class="sxs-lookup"><span data-stu-id="fb837-117">In **Object Explorer**, click the plus sign to expand the server where you want to create a job category.</span></span>  
  
2.  <span data-ttu-id="fb837-118">Fare clic sul segno più per espandere **SQL Server Agent**.</span><span class="sxs-lookup"><span data-stu-id="fb837-118">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="fb837-119">Fare clic con il pulsante destro del mouse sulla cartella **Processi** e selezionare **Gestione categorie processi**.</span><span class="sxs-lookup"><span data-stu-id="fb837-119">Right-click the **Jobs** folder and select **Manage Job Categories**.</span></span>  
  
4.  <span data-ttu-id="fb837-120">Nella finestra di dialogo **Gestione categorie processi**_nome_server_ fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="fb837-120">In the **Manage Job Categories**_server_name_ dialog box, click **Add**.</span></span>  
  
5.  <span data-ttu-id="fb837-121">Nella casella **Nome** della nuova finestra di dialogo immettere un nome per la nuova categoria di processi.</span><span class="sxs-lookup"><span data-stu-id="fb837-121">In the new dialog box, in the **Name** box, enter a name for the new job category.</span></span>  
  
6.  <span data-ttu-id="fb837-122">Selezionare la casella di controllo **Mostra tutti i processi** .</span><span class="sxs-lookup"><span data-stu-id="fb837-122">Select the **Show all jobs** check box.</span></span> <span data-ttu-id="fb837-123">Selezionare uno o più processi per la nuova categoria selezionando le caselle corrispondenti ai processi.</span><span class="sxs-lookup"><span data-stu-id="fb837-123">Select one or more jobs for the new category by checking the boxes corresponding to the jobs.</span></span>  
  
7.  <span data-ttu-id="fb837-124">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="fb837-124">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="fb837-125">Nella finestra di dialogo **Gestisci categorie processi**_nome_server_ fare clic su **Aggiorna** per assicurarsi che la nuova categoria di processi sia attiva.</span><span class="sxs-lookup"><span data-stu-id="fb837-125">In the **Manage Job Categories**_server_name_ dialog box, click **Refresh** to ensure that the new job category is active.</span></span> <span data-ttu-id="fb837-126">Se l'aspetto è quello previsto, chiudere questa finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="fb837-126">If everything looks as expected, close this dialog box.</span></span>  
  
 <span data-ttu-id="fb837-127">Per altre informazioni su queste finestre di dialogo, vedere categorie di processi [: gestire le categorie di processi](job-categories-manage-job-categories.md) e le [proprietà delle categorie di processi e la nuova categoria di processi](job-categories-properties-new-job-category.md).</span><span class="sxs-lookup"><span data-stu-id="fb837-127">For more information on these dialog boxes, see [Job Categories: Manage Job Categories](job-categories-manage-job-categories.md) and [Job Categories Properties and New Job Category](job-categories-properties-new-job-category.md).</span></span>  

##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="fb837-128">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="fb837-128">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-job-category"></a><span data-ttu-id="fb837-129">Per creare una categoria di processi</span><span class="sxs-lookup"><span data-stu-id="fb837-129">To create a job category</span></span>  
  
1.  <span data-ttu-id="fb837-130">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fb837-130">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="fb837-131">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="fb837-131">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="fb837-132">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="fb837-132">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- creates a local job category named AdminJobs   
    USE msdb ;  
    GO  
    EXEC dbo.sp_add_category  
        @class=N'JOB',  
        @type=N'LOCAL',  
        @name=N'AdminJobs' ;  
    GO  
    ```  
  
 <span data-ttu-id="fb837-133">Per ulteriori informazioni, vedere [sp_add_category &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-add-category-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="fb837-133">For more information, see [sp_add_category &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-category-transact-sql).</span></span>  

##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="fb837-134">Utilizzo di SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="fb837-134">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="fb837-135">**Per creare una categoria di processi**</span><span class="sxs-lookup"><span data-stu-id="fb837-135">**To create a job category**</span></span>  
  
 <span data-ttu-id="fb837-136">Chiamare la classe `JobCategory` tramite un linguaggio di programmazione come Visual Basic, Visual C# o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fb837-136">Call the `JobCategory` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="fb837-137">Per un codice di esempio, vedere [Pianificazione delle attività amministrative automatiche in SQL Server Agent](sql-server-agent.md).</span><span class="sxs-lookup"><span data-stu-id="fb837-137">For example code, see [Scheduling Automatic Administrative Tasks in SQL Server Agent](sql-server-agent.md).</span></span>  
