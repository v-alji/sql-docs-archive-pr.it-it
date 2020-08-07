---
title: Visualizzare la cronologia processi | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], history
- viewing job history
- SQL Server Agent jobs, history
- historical information [SQL Server], jobs
- displaying job history
ms.assetid: 3bbd1556-abdb-48a3-b249-546eace76343
author: stevestein
ms.author: sstein
ms.openlocfilehash: e84fafdaeddb5748a8129cd5d71d667db7e5fa37
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719374"
---
# <a name="view-the-job-history"></a><span data-ttu-id="9ef91-102">Visualizzare la cronologia processi</span><span class="sxs-lookup"><span data-stu-id="9ef91-102">View the Job History</span></span>
  <span data-ttu-id="9ef91-103">In questo argomento viene descritto come visualizzare il [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log cronologia processi di Agent in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , [!INCLUDE[tsql](../../includes/tsql-md.md)] o SQL Server Management Objects.</span><span class="sxs-lookup"><span data-stu-id="9ef91-103">This topic describes how to view the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job history log in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Management Objects.</span></span>  
  
-   <span data-ttu-id="9ef91-104">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="9ef91-104">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="9ef91-105">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="9ef91-105">Security</span></span>](#Security)  
  
-   <span data-ttu-id="9ef91-106">**Per visualizzare il log cronologia processi utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="9ef91-106">**To view the job history log, using:**</span></span>  
  
     [<span data-ttu-id="9ef91-107">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9ef91-107">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="9ef91-108">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9ef91-108">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="9ef91-109">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="9ef91-109">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="9ef91-110">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="9ef91-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="9ef91-111">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="9ef91-111">Security</span></span>  
 <span data-ttu-id="9ef91-112">Per informazioni dettagliate, vedere [Implementazione della sicurezza di SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="9ef91-112">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="9ef91-113">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9ef91-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-the-job-history-log"></a><span data-ttu-id="9ef91-114">Per visualizzare il log cronologia processi</span><span class="sxs-lookup"><span data-stu-id="9ef91-114">To view the job history log</span></span>  
  
1.  <span data-ttu-id="9ef91-115">In **Esplora oggetti** connettersi a un'istanza del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , quindi espandere l'istanza.</span><span class="sxs-lookup"><span data-stu-id="9ef91-115">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="9ef91-116">Espandere **SQL Server Agent**e quindi espandere **Processi**.</span><span class="sxs-lookup"><span data-stu-id="9ef91-116">Expand **SQL Server Agent**, and then expand **Jobs**.</span></span>  
  
3.  <span data-ttu-id="9ef91-117">Fare clic con il pulsante destro del mouse su un processo e scegliere **Visualizza cronologia**.</span><span class="sxs-lookup"><span data-stu-id="9ef91-117">Right-click a job, and then click **View History**.</span></span>  
  
4.  <span data-ttu-id="9ef91-118">Nel Visualizzatore file di log visualizzare la cronologia processo.</span><span class="sxs-lookup"><span data-stu-id="9ef91-118">In the Log File Viewer, view the job history.</span></span>  
  
5.  <span data-ttu-id="9ef91-119">Per aggiornare la cronologia processo, fare clic su **Aggiorna**.</span><span class="sxs-lookup"><span data-stu-id="9ef91-119">To update the job history, click **Refresh**.</span></span> <span data-ttu-id="9ef91-120">Per visualizzare un numero inferiore di righe, fare clic sul pulsante **Filtro** e immettere i parametri di filtro.</span><span class="sxs-lookup"><span data-stu-id="9ef91-120">To view fewer rows, click the **Filter** button and enter filter parameters.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="9ef91-121">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9ef91-121">Using Transact-SQL</span></span>  
  
#### <a name="to-view-the-job-history-log"></a><span data-ttu-id="9ef91-122">Per visualizzare il log cronologia processi</span><span class="sxs-lookup"><span data-stu-id="9ef91-122">To view the job history log</span></span>  
  
1.  <span data-ttu-id="9ef91-123">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9ef91-123">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="9ef91-124">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="9ef91-124">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="9ef91-125">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="9ef91-125">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- lists all job information for the NightlyBackups job.  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_help_jobhistory   
        @job_name = N'NightlyBackups' ;  
    GO  
    ```  
  
 <span data-ttu-id="9ef91-126">Per ulteriori informazioni, vedere [sp_help_jobhistory &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-help-jobhistory-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9ef91-126">For more information, see [sp_help_jobhistory &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-jobhistory-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="9ef91-127">Utilizzo di SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="9ef91-127">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="9ef91-128">**Per visualizzare il log cronologia processi**</span><span class="sxs-lookup"><span data-stu-id="9ef91-128">**To view the job history log**</span></span>  
  
 <span data-ttu-id="9ef91-129">Chiamare il metodo `EnumHistory` della classe `Job` usando un linguaggio di programmazione come Visual Basic, Visual C# o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9ef91-129">Call the `EnumHistory` method of the `Job` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="9ef91-130">Per altre informazioni, vedere [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span><span class="sxs-lookup"><span data-stu-id="9ef91-130">For more information, see [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span></span>  
