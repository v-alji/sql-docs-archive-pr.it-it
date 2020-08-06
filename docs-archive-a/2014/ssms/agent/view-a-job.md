---
title: Visualizzare un processo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], viewing
- viewing jobs
- SQL Server Agent jobs, viewing
- displaying jobs
ms.assetid: d2241a3f-dbcf-433c-b7bc-f96bdf0eac8c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 26406aaf2ba0ac4809eb7ac2c84799469d0468d4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638230"
---
# <a name="view-a-job"></a><span data-ttu-id="0ab42-102">View a Job</span><span class="sxs-lookup"><span data-stu-id="0ab42-102">View a Job</span></span>
  <span data-ttu-id="0ab42-103">In questo argomento viene descritto come visualizzare i [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] processi di Agent in utilizzando [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0ab42-103">This topic describes how to view [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="0ab42-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="0ab42-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="0ab42-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="0ab42-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="0ab42-106">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="0ab42-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="0ab42-107">**Per visualizzare un processo utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="0ab42-107">**To view a job, using:**</span></span>  
  
     [<span data-ttu-id="0ab42-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0ab42-108">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="0ab42-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0ab42-109">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="0ab42-110">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="0ab42-110">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="0ab42-111">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="0ab42-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="0ab42-112">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="0ab42-112">Security</span></span>  
 <span data-ttu-id="0ab42-113">È possibile visualizzare solo i processi di cui si è proprietari, a meno che non si appartenga al ruolo predefinito del server **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="0ab42-113">You can only view jobs that you own, unless you are a member of the **sysadmin** fixed server role.</span></span> <span data-ttu-id="0ab42-114">Ai membri di questo ruolo è consentita la visualizzazione di tutti i processi.</span><span class="sxs-lookup"><span data-stu-id="0ab42-114">Members of this role can view all jobs.</span></span> <span data-ttu-id="0ab42-115">Per informazioni dettagliate, vedere [Implementazione della sicurezza di SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="0ab42-115">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="0ab42-116">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0ab42-116">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-a-job"></a><span data-ttu-id="0ab42-117">Per visualizzare un processo</span><span class="sxs-lookup"><span data-stu-id="0ab42-117">To view a job</span></span>  
  
1.  <span data-ttu-id="0ab42-118">In **Esplora oggetti** connettersi a un'istanza del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , quindi espandere l'istanza.</span><span class="sxs-lookup"><span data-stu-id="0ab42-118">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="0ab42-119">Espandere **SQL Server Agent**e quindi espandere **Processi**.</span><span class="sxs-lookup"><span data-stu-id="0ab42-119">Expand **SQL Server Agent**, and then expand **Jobs**.</span></span>  
  
3.  <span data-ttu-id="0ab42-120">Fare clic con il pulsante destro del mouse su un processo e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="0ab42-120">Right-click a job, and then click **Properties**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="0ab42-121">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0ab42-121">Using Transact-SQL</span></span>  
  
#### <a name="to-view-a-job"></a><span data-ttu-id="0ab42-122">Per visualizzare un processo</span><span class="sxs-lookup"><span data-stu-id="0ab42-122">To view a job</span></span>  
  
1.  <span data-ttu-id="0ab42-123">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0ab42-123">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="0ab42-124">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="0ab42-124">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="0ab42-125">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="0ab42-125">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- lists all aspects of the information for the job NightlyBackups.  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_help_job  
        @job_name = N'NightlyBackups',  
        @job_aspect = N'ALL' ;  
    GO  
    ```  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="0ab42-126">Utilizzo di SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="0ab42-126">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="0ab42-127">**Per visualizzare un processo**</span><span class="sxs-lookup"><span data-stu-id="0ab42-127">**To view a job**</span></span>  
  
 <span data-ttu-id="0ab42-128">Usare la classe `Job` tramite un linguaggio di programmazione scelto come Visual Basic, Visual C# o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0ab42-128">Use the `Job` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="0ab42-129">Per altre informazioni, vedere [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span><span class="sxs-lookup"><span data-stu-id="0ab42-129">For more information, see [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span></span>  
