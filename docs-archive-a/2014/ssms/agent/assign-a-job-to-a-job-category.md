---
title: Assegnare un processo a una categoria di processi | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], assigning
- SQL Server Agent jobs, categories
- jobs [SQL Server Agent], categories
- categories [SQL Server Agent jobs]
- SQL Server Agent jobs, assigning
- assigning job to category
ms.assetid: a9ea65a2-1d73-4582-a335-63adeb450cb6
author: stevestein
ms.author: sstein
ms.openlocfilehash: 208ff6722a9c18fd4dd0d061575f0d496af27810
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637598"
---
# <a name="assign-a-job-to-a-job-category"></a><span data-ttu-id="4ed2f-102">Assegnare un processo a una categoria di processi</span><span class="sxs-lookup"><span data-stu-id="4ed2f-102">Assign a Job to a Job Category</span></span>
  <span data-ttu-id="4ed2f-103">In questo argomento viene descritto come assegnare [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] processi di Agent a categorie di processi in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] [!INCLUDE[tsql](../../includes/tsql-md.md)] o SQL Server Management Objects.</span><span class="sxs-lookup"><span data-stu-id="4ed2f-103">This topic describes how to assign [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs to job categories in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)] or SQL Server Management Objects.</span></span>  
  
 <span data-ttu-id="4ed2f-104">Le categorie consentono di organizzare i processi per semplificare le operazioni di raggruppamento e filtro.</span><span class="sxs-lookup"><span data-stu-id="4ed2f-104">Job categories help you organize your jobs for easy filtering and grouping.</span></span> <span data-ttu-id="4ed2f-105">È ad esempio possibile organizzare tutti i processi di backup dei database raggruppandoli nella categoria Manutenzione database.</span><span class="sxs-lookup"><span data-stu-id="4ed2f-105">For example, you can organize all your database backup jobs in the Database Maintenance category.</span></span> <span data-ttu-id="4ed2f-106">È possibile assegnare processi a categorie predefinite, oppure creare una categoria definita dall'utente e usarla per l'assegnazione dei processi.</span><span class="sxs-lookup"><span data-stu-id="4ed2f-106">You can assign jobs to built-in job categories, or you can create a user-defined job category and then assign jobs to that.</span></span>  
  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="4ed2f-107">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="4ed2f-107">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="4ed2f-108">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="4ed2f-108">Security</span></span>  
 <span data-ttu-id="4ed2f-109">Per informazioni dettagliate, vedere [Implementazione della sicurezza di SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="4ed2f-109">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="4ed2f-110">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4ed2f-110">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-assign-a-job-to-a-job-category"></a><span data-ttu-id="4ed2f-111">Per assegnare un processo a una categoria di processi</span><span class="sxs-lookup"><span data-stu-id="4ed2f-111">To assign a job to a job category</span></span>  
  
1.  <span data-ttu-id="4ed2f-112">In **Esplora oggetti**fare clic sul segno più per espandere il server in cui si desidera assegnare un processo a una categoria di processi.</span><span class="sxs-lookup"><span data-stu-id="4ed2f-112">In **Object Explorer**, click the plus sign to expand the server where you want to assign a job to a job category.</span></span>  
  
2.  <span data-ttu-id="4ed2f-113">Fare clic sul segno più per espandere **SQL Server Agent**.</span><span class="sxs-lookup"><span data-stu-id="4ed2f-113">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="4ed2f-114">Fare clic sul segno più per espandere la cartella **Processi** .</span><span class="sxs-lookup"><span data-stu-id="4ed2f-114">Click the plus sign to expand the **Jobs** folder.</span></span>  
  
4.  <span data-ttu-id="4ed2f-115">Fare clic con il pulsante destro del mouse sul processo da modificare e selezionare **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="4ed2f-115">Right-click the job you want to edit and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="4ed2f-116">Nell'elenco **categoria** della finestra di dialogo **proprietà processo-**_job_name_ Selezionare la categoria di processi che si desidera assegnare al processo.</span><span class="sxs-lookup"><span data-stu-id="4ed2f-116">In the **Job Properties -**_job_name_ dialog box, in the **Category** list, select the job category you want to assign to the job.</span></span>  
  
6.  <span data-ttu-id="4ed2f-117">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="4ed2f-117">Click **OK**.</span></span>  
  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="4ed2f-118">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4ed2f-118">Using Transact-SQL</span></span>  
  
#### <a name="to-assign-a-job-to-a-job-category"></a><span data-ttu-id="4ed2f-119">Per assegnare un processo a una categoria di processi</span><span class="sxs-lookup"><span data-stu-id="4ed2f-119">To assign a job to a job category</span></span>  
  
1.  <span data-ttu-id="4ed2f-120">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4ed2f-120">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="4ed2f-121">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="4ed2f-121">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="4ed2f-122">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="4ed2f-122">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- adding a new job category to the "NightlyBackups" job  
    USE msdb ;  
    GO  
    EXEC dbo.sp_update_job  
        @job_name = N'NightlyBackups',  
        @category_name = N'[Uncategorized (Local)]';  
    GO  
    ```  
  
 <span data-ttu-id="4ed2f-123">Per ulteriori informazioni, vedere [sp_update_job &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-update-job-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4ed2f-123">For more information, see [sp_update_job &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-job-transact-sql).</span></span>  
  
  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="4ed2f-124">Utilizzo di SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="4ed2f-124">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="4ed2f-125">**Per assegnare un processo a una categoria di processi**</span><span class="sxs-lookup"><span data-stu-id="4ed2f-125">**To assign a job to a job category**</span></span>  
  
 <span data-ttu-id="4ed2f-126">Usare la classe `JobCategory` tramite un linguaggio di programmazione scelto come Visual Basic, Visual C# o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4ed2f-126">Use the `JobCategory` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span>  
  
  
  
  
