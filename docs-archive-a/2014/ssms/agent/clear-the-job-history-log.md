---
title: Cancellare il contenuto del log di cronologia processi | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], history
- clearing job history log
- logs [SQL Server], jobs
- SQL Server Agent jobs, history
- historical information [SQL Server], jobs
ms.assetid: 34b9398a-c409-4040-8ea1-0deceb18f961
author: stevestein
ms.author: sstein
ms.openlocfilehash: 813c2c7c86a769eea09a093f2de999460d78ef54
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637591"
---
# <a name="clear-the-job-history-log"></a><span data-ttu-id="8fd72-102">Cancellare il contenuto del log di cronologia processi</span><span class="sxs-lookup"><span data-stu-id="8fd72-102">Clear the Job History Log</span></span>
  <span data-ttu-id="8fd72-103">In questo argomento viene descritto come eliminare il contenuto del [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log cronologia processi di Agent in utilizzando [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , [!INCLUDE[tsql](../../includes/tsql-md.md)] o SQL Server Management Objects.</span><span class="sxs-lookup"><span data-stu-id="8fd72-103">This topic describes how to delete the contents of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job history log in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Management Objects.</span></span>  
  
 <span data-ttu-id="8fd72-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="8fd72-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="8fd72-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="8fd72-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="8fd72-106">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="8fd72-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="8fd72-107">**Per cancellare il contenuto del log di cronologia processo utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="8fd72-107">**To clear the job history log, using:**</span></span>  
  
     [<span data-ttu-id="8fd72-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8fd72-108">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="8fd72-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8fd72-109">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="8fd72-110">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="8fd72-110">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="8fd72-111">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="8fd72-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="8fd72-112">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="8fd72-112">Security</span></span>  
 <span data-ttu-id="8fd72-113">Per informazioni dettagliate, vedere [Implementazione della sicurezza di SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="8fd72-113">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="8fd72-114">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8fd72-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-clear-the-job-history-log"></a><span data-ttu-id="8fd72-115">Per cancellare il contenuto del log di cronologia processo</span><span class="sxs-lookup"><span data-stu-id="8fd72-115">To clear the job history log</span></span>  
  
1.  <span data-ttu-id="8fd72-116">In **Esplora oggetti** connettersi a un'istanza del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , quindi espandere l'istanza.</span><span class="sxs-lookup"><span data-stu-id="8fd72-116">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="8fd72-117">Espandere **SQL Server Agent**e quindi espandere **Processi**.</span><span class="sxs-lookup"><span data-stu-id="8fd72-117">Expand **SQL Server Agent**, and then expand **Jobs**.</span></span>  
  
3.  <span data-ttu-id="8fd72-118">Fare clic con il pulsante destro del mouse su un processo e scegliere **Visualizza cronologia**.</span><span class="sxs-lookup"><span data-stu-id="8fd72-118">Right-click a job and click **View history**.</span></span>  
  
4.  <span data-ttu-id="8fd72-119">Nel **Visualizzatore file di log**selezionare il processo di cui si desidera cancellare la cronologia e quindi eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8fd72-119">In the **Log File Viewer**, select the job for which you want to clear history, and then do one of the following:</span></span>  
  
    -   <span data-ttu-id="8fd72-120">Fare clic su **Elimina**e quindi su **Elimina tutta la cronologia** nella finestra di dialogo **Elimina cronologia** .</span><span class="sxs-lookup"><span data-stu-id="8fd72-120">Click **Delete**, and then click **Delete all history** in the **Delete History** dialog.</span></span> <span data-ttu-id="8fd72-121">È possibile eliminare tutta la cronologia processo oppure solo quella precedente a una data specificata.</span><span class="sxs-lookup"><span data-stu-id="8fd72-121">You can delete all job history or only history that is older than a specified date.</span></span> <span data-ttu-id="8fd72-122">Per rimuovere tutta la cronologia processo, fare clic su **Elimina tutta la cronologia**.</span><span class="sxs-lookup"><span data-stu-id="8fd72-122">If you want to remove all job history, click **Delete all history**.</span></span> <span data-ttu-id="8fd72-123">Per rimuovere solo i log cronologia processo più vecchi, fare clic su **Elimina la cronologia precedente a**e quindi specificare una data.</span><span class="sxs-lookup"><span data-stu-id="8fd72-123">If you only want to remove older job history logs, click **Delete history before**, and then specify a date.</span></span>  
  
    -   <span data-ttu-id="8fd72-124">Fare clic su **Stato processo** se si desidera cancellare il contenuto del log della cronologia di un processo multiserver.</span><span class="sxs-lookup"><span data-stu-id="8fd72-124">Click **Job status** if you want to clear the history log of a multiserver job.</span></span> <span data-ttu-id="8fd72-125">Fare clic su **Processo**, selezionare il nome di un processo e quindi fare clic su **Visualizza cronologia processi remoti**.</span><span class="sxs-lookup"><span data-stu-id="8fd72-125">Click **Job**, click a job name, and then click **View Remote Job History**.</span></span>  
  
5.  <span data-ttu-id="8fd72-126">Fare clic su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="8fd72-126">Click **Delete**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="8fd72-127">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8fd72-127">Using Transact-SQL</span></span>  
  
#### <a name="to-clear-the-job-history-log"></a><span data-ttu-id="8fd72-128">Per cancellare il contenuto del log di cronologia processo</span><span class="sxs-lookup"><span data-stu-id="8fd72-128">To clear the job history log</span></span>  
  
1.  <span data-ttu-id="8fd72-129">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8fd72-129">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="8fd72-130">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="8fd72-130">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="8fd72-131">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="8fd72-131">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- example removes the history for a job named NightlyBackups.  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_purge_jobhistory  
        @job_name = N'NightlyBackups' ;  
    GO  
    ```  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="8fd72-132">Utilizzo di SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="8fd72-132">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="8fd72-133">**Per cancellare il contenuto del log di cronologia processo**</span><span class="sxs-lookup"><span data-stu-id="8fd72-133">**To clear the job history log**</span></span>  
  
 <span data-ttu-id="8fd72-134">Utilizzare il metodo `PurgeJobHistory` della classe `JobServer` utilizzando un linguaggio di programmazione come Visual Basic, Visual C# o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8fd72-134">Use the `PurgeJobHistory` method of the `JobServer` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="8fd72-135">Per altre informazioni, vedere [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span><span class="sxs-lookup"><span data-stu-id="8fd72-135">For more information, see [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span></span>  
  
  
