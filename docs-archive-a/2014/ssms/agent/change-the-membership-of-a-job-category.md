---
title: Modificare l'appartenenza a una categoria di processi | Microsoft Docs
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
- members [SQL Server], job categories
ms.assetid: 6a18f7f0-eb50-485f-a9c7-df31ae0f994e
author: stevestein
ms.author: sstein
ms.openlocfilehash: d9ed0db394f63594937ad923734b07fed8050955
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637595"
---
# <a name="change-the-membership-of-a-job-category"></a><span data-ttu-id="dd418-102">Modificare l'appartenenza a una categoria di processi</span><span class="sxs-lookup"><span data-stu-id="dd418-102">Change the Membership of a Job Category</span></span>
  <span data-ttu-id="dd418-103">In questo argomento viene descritto come modificare l'appartenenza della categoria di processi in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)]o SQL Server Management Objects.</span><span class="sxs-lookup"><span data-stu-id="dd418-103">This topic describes how to change the membership of the job category in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Management Objects.</span></span>  
  
 <span data-ttu-id="dd418-104">Le categorie consentono di organizzare i processi per semplificare le operazioni di raggruppamento e filtro.</span><span class="sxs-lookup"><span data-stu-id="dd418-104">Job categories help you organize your jobs for easy filtering and grouping.</span></span> <span data-ttu-id="dd418-105">È possibile creare categorie di processi personalizzate.</span><span class="sxs-lookup"><span data-stu-id="dd418-105">You can create your own job categories.</span></span> <span data-ttu-id="dd418-106">È inoltre possibile modificare l'appartenenza dei processi di Microsoft SQL Server Agent alle categorie del processo.</span><span class="sxs-lookup"><span data-stu-id="dd418-106">You can also change Microsoft SQL Server Agent jobs membership in job categories.</span></span>  
  
 <span data-ttu-id="dd418-107">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="dd418-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="dd418-108">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="dd418-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="dd418-109">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="dd418-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="dd418-110">**Per modificare l'appartenenza a una categoria di processi usando:**</span><span class="sxs-lookup"><span data-stu-id="dd418-110">**To change the membership of a job category, using:**</span></span>  
  
     [<span data-ttu-id="dd418-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="dd418-111">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="dd418-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="dd418-112">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="dd418-113">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="dd418-113">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="dd418-114">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="dd418-114">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="dd418-115">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="dd418-115">Security</span></span>  
 <span data-ttu-id="dd418-116">Per informazioni dettagliate, vedere [Implementazione della sicurezza di SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="dd418-116">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="dd418-117">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="dd418-117">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-change-the-membership-of-a-job-category"></a><span data-ttu-id="dd418-118">Per modificare l'appartenenza a una categoria di processi</span><span class="sxs-lookup"><span data-stu-id="dd418-118">To change the membership of a job category</span></span>  
  
1.  <span data-ttu-id="dd418-119">In **Esplora oggetti**fare clic sul segno più per espandere il server in cui si desidera modificare una categoria di processi.</span><span class="sxs-lookup"><span data-stu-id="dd418-119">In **Object Explorer**, click the plus sign to expand the server where you want to edit a job category.</span></span>  
  
2.  <span data-ttu-id="dd418-120">Fare clic sul segno più per espandere **SQL Server Agent**.</span><span class="sxs-lookup"><span data-stu-id="dd418-120">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="dd418-121">Fare clic con il pulsante destro del mouse sulla cartella **Processi** e selezionare **Gestione categorie processi**.</span><span class="sxs-lookup"><span data-stu-id="dd418-121">Right-click the **Jobs** folder and select **Manage Job Categories**.</span></span>  
  
4.  <span data-ttu-id="dd418-122">Nella finestra di dialogo **Gestione categorie processi**_nome_server_ selezionare la categoria di processi da modificare e fare clic su **Visualizza processi**.</span><span class="sxs-lookup"><span data-stu-id="dd418-122">In the **Manage Job Categories**_server_name_ dialog box, select the job category that you want to edit, and then click **View Jobs**.</span></span>  
  
5.  <span data-ttu-id="dd418-123">Selezionare la casella di controllo **Mostra tutti i processi** .</span><span class="sxs-lookup"><span data-stu-id="dd418-123">Select the **Show all jobs** check box.</span></span>  
  
6.  <span data-ttu-id="dd418-124">Per aggiungere un processo alla categoria, selezionare nella griglia principale la casella di controllo della colonna **Seleziona** corrispondente al processo.</span><span class="sxs-lookup"><span data-stu-id="dd418-124">To add a job to the category, in the main grid, select the check box in the **Select** column corresponding to the job.</span></span> <span data-ttu-id="dd418-125">Per rimuovere un processo dalla categoria, deselezionare la casella.</span><span class="sxs-lookup"><span data-stu-id="dd418-125">To remove a job from the category, clear the box.</span></span> <span data-ttu-id="dd418-126">Al termine, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="dd418-126">When finished, click **OK**.</span></span>  
  
7.  <span data-ttu-id="dd418-127">Chiudere la finestra di dialogo **Gestione categorie processi**_nome_server_ .</span><span class="sxs-lookup"><span data-stu-id="dd418-127">Close the **Manage Job Categories**_server_name_ dialog box.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="dd418-128">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="dd418-128">Using Transact-SQL</span></span>  
  
#### <a name="to-change-the-membership-of-a-job-category"></a><span data-ttu-id="dd418-129">Per modificare l'appartenenza a una categoria di processi</span><span class="sxs-lookup"><span data-stu-id="dd418-129">To change the membership of a job category</span></span>  
  
1.  <span data-ttu-id="dd418-130">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dd418-130">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="dd418-131">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="dd418-131">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="dd418-132">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="dd418-132">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- adding a new job category to the "NightlyBackups" job  
    USE msdb ;  
    GO  
    EXEC dbo.sp_update_job  
        @job_name = N'NightlyBackups',  
        @category_name = N'[Uncategorized (Local)]';  
    GO  
    ```  
  
 <span data-ttu-id="dd418-133">Per ulteriori informazioni, vedere [sp_update_job &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-update-job-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="dd418-133">For more information, see [sp_update_job &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-job-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="dd418-134">Utilizzo di SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="dd418-134">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="dd418-135">**Per modificare l'appartenenza a una categoria di processi**</span><span class="sxs-lookup"><span data-stu-id="dd418-135">**To change the membership of a job category**</span></span>  
  
 <span data-ttu-id="dd418-136">Usare la classe `JobCategory` tramite un linguaggio di programmazione scelto come Visual Basic, Visual C# o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dd418-136">Use the `JobCategory` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span>  
