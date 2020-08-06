---
title: Eliminare una categoria di processi | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, categories
- deleting job category
- jobs [SQL Server Agent], categories
- categories [SQL Server Agent jobs]
- removing job category
ms.assetid: 47a7640b-20b3-4639-ab37-b6fc73575e6c
author: stevestein
ms.author: sstein
ms.openlocfilehash: e96dd0461f3dace138b7822cdbaaa2fa242e2cb1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712688"
---
# <a name="delete-a-job-category"></a><span data-ttu-id="893ef-102">Eliminare una categoria di processi</span><span class="sxs-lookup"><span data-stu-id="893ef-102">Delete a Job Category</span></span>
  <span data-ttu-id="893ef-103">In questo argomento viene descritto come eliminare una [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] categoria di processi di Agent in utilizzando [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] [!INCLUDE[tsql](../../includes/tsql-md.md)] o SQL Server Management Objects.</span><span class="sxs-lookup"><span data-stu-id="893ef-103">This topic describes how to delete a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job category in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)] or SQL Server Management Objects.</span></span>  
  
 <span data-ttu-id="893ef-104">Le categorie consentono di organizzare i processi per semplificare le operazioni di raggruppamento e filtro.</span><span class="sxs-lookup"><span data-stu-id="893ef-104">Job categories help you organize your jobs for easy filtering and grouping.</span></span> <span data-ttu-id="893ef-105">È ad esempio possibile organizzare tutti i processi di backup dei database raggruppandoli nella categoria Manutenzione database.</span><span class="sxs-lookup"><span data-stu-id="893ef-105">For example, you can organize all your database backup jobs in the Database Maintenance category.</span></span>  

##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="893ef-106">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="893ef-106">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="893ef-107">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="893ef-107">Limitations and Restrictions</span></span>  
 <span data-ttu-id="893ef-108">Quando si elimina una categoria di processi definita dall'utente, tramite [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent viene richiesto di riassegnare i processi appartenenti alla categoria a un'altra categoria.</span><span class="sxs-lookup"><span data-stu-id="893ef-108">When you delete a user-defined job category, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent prompts you to reassign the jobs that are assigned to it to another job category.</span></span> <span data-ttu-id="893ef-109">È possibile eliminare solo categorie di processi definite dall'utente.</span><span class="sxs-lookup"><span data-stu-id="893ef-109">You can only delete user-defined job categories.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="893ef-110">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="893ef-110">Security</span></span>  
 <span data-ttu-id="893ef-111">Per informazioni dettagliate, vedere [Implementazione della sicurezza di SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="893ef-111">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  

##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="893ef-112">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="893ef-112">Using SQL Server Management Studio</span></span>  
  
### <a name="to-delete-a-job-category"></a><span data-ttu-id="893ef-113">Per eliminare una categoria di processi</span><span class="sxs-lookup"><span data-stu-id="893ef-113">To delete a job category</span></span>  
  
1.  <span data-ttu-id="893ef-114">In **Esplora oggetti**fare clic sul segno più per espandere il server in cui si desidera eliminare una categoria di processi.</span><span class="sxs-lookup"><span data-stu-id="893ef-114">In **Object Explorer**, click the plus sign to expand the server where you want to delete a job category.</span></span>  
  
2.  <span data-ttu-id="893ef-115">Fare clic sul segno più per espandere **SQL Server Agent**.</span><span class="sxs-lookup"><span data-stu-id="893ef-115">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="893ef-116">Fare clic con il pulsante destro del mouse sulla cartella **Processi** e selezionare **Gestione categorie processi**.</span><span class="sxs-lookup"><span data-stu-id="893ef-116">Right-click the **Jobs** folder and select **Manage Job Categories**.</span></span>  
  
4.  <span data-ttu-id="893ef-117">Nella finestra di dialogo **Gestisci categorie di processi**_nome_server_ selezionare la categoria di processi da eliminare.</span><span class="sxs-lookup"><span data-stu-id="893ef-117">In the **Manage Job Categories**_server_name_ dialog box, select the job category to delete.</span></span>  
  
5.  <span data-ttu-id="893ef-118">Fare clic su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="893ef-118">Click **Delete**.</span></span>  
  
6.  <span data-ttu-id="893ef-119">Nella finestra di dialogo **Categorie di processi** fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="893ef-119">In the **Job Categories** dialog box, click **Yes**.</span></span>  
  
7.  <span data-ttu-id="893ef-120">Chiudere la finestra di dialogo **Gestione categorie processi**_nome_server_ .</span><span class="sxs-lookup"><span data-stu-id="893ef-120">Close the **Manage Job Categories**_server_name_ dialog box.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="893ef-121">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="893ef-121">Using Transact-SQL</span></span>  
  
### <a name="to-delete-a-job-category"></a><span data-ttu-id="893ef-122">Per eliminare una categoria di processi</span><span class="sxs-lookup"><span data-stu-id="893ef-122">To delete a job category</span></span>  
  
1.  <span data-ttu-id="893ef-123">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="893ef-123">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="893ef-124">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="893ef-124">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="893ef-125">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="893ef-125">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- deletes the job category named AdminJobs.  
    USE msdb ;  
    GO   
    EXEC dbo.sp_delete_category  
        @name = N'AdminJobs',  
        @class = N'JOB' ;  
    GO  
    ```  
  
 <span data-ttu-id="893ef-126">Per ulteriori informazioni, vedere [sp_delete_category &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-delete-category-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="893ef-126">For more information, see [sp_delete_category &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-category-transact-sql).</span></span>  

  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="893ef-127">Utilizzo di SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="893ef-127">Using SQL Server Management Objects</span></span>  

### <a name="to-delete-a-job-category"></a><span data-ttu-id="893ef-128">Per eliminare una categoria di processi</span><span class="sxs-lookup"><span data-stu-id="893ef-128">To delete a job category</span></span>
  
 <span data-ttu-id="893ef-129">Chiamare la classe `JobCategory` tramite un linguaggio di programmazione come Visual Basic, Visual C# o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="893ef-129">Call the `JobCategory` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span>  
