---
title: Notificare lo stato di un processo a un operatore | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- status information [SQL Server], jobs
- jobs [SQL Server Agent], notification options
- SQL Server Agent jobs, status
- jobs [SQL Server Agent], status
- SQL Server Agent jobs, notification options
- notifications [SQL Server], job status
ms.assetid: e7399505-27ac-48d9-a637-73bf92b9df49
author: stevestein
ms.author: sstein
ms.openlocfilehash: a202327ad63cf7ef8f51d3572b257816ee6d9419
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627037"
---
# <a name="notify-an-operator-of-job-status"></a><span data-ttu-id="fe290-102">Notify an Operator of Job Status</span><span class="sxs-lookup"><span data-stu-id="fe290-102">Notify an Operator of Job Status</span></span>
  <span data-ttu-id="fe290-103">In questo argomento viene descritto come impostare le opzioni di notifica in utilizzando [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , [!INCLUDE[tsql](../../includes/tsql-md.md)] o SQL Server Management Objects, in modo che tramite [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent sia possibile inviare notifiche agli operatori relativi ai processi.</span><span class="sxs-lookup"><span data-stu-id="fe290-103">This topic describes how to set notification options in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Management Objects, so [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent can send notifications to operators about jobs.</span></span>  
  
 <span data-ttu-id="fe290-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="fe290-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="fe290-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="fe290-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="fe290-106">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="fe290-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="fe290-107">**Per notificare lo stato di un processo a un operatore mediante:**</span><span class="sxs-lookup"><span data-stu-id="fe290-107">**To notify an operator of job status, using:**</span></span>  
  
     [<span data-ttu-id="fe290-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="fe290-108">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="fe290-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="fe290-109">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="fe290-110">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="fe290-110">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="fe290-111">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="fe290-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="fe290-112">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="fe290-112">Security</span></span>  
 <span data-ttu-id="fe290-113">Per informazioni dettagliate, vedere [Implementazione della sicurezza di SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="fe290-113">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="fe290-114">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="fe290-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-notify-an-operator-of-job-status"></a><span data-ttu-id="fe290-115">Per notificare lo stato di un processo a un operatore</span><span class="sxs-lookup"><span data-stu-id="fe290-115">To notify an operator of job status</span></span>  
  
1.  <span data-ttu-id="fe290-116">In **Esplora oggetti** connettersi a un'istanza del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , quindi espandere l'istanza.</span><span class="sxs-lookup"><span data-stu-id="fe290-116">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="fe290-117">Espandere **SQL Server Agent**e **Processi**, fare clic con il pulsante destro del mouse sul processo che si vuole modificare e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="fe290-117">Expand **SQL Server Agent**, expand **Jobs**, right-click the job you want to edit, and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="fe290-118">Nella finestra di dialogo **Proprietà processo** selezionare la pagina **Notifiche** .</span><span class="sxs-lookup"><span data-stu-id="fe290-118">In the **Job Properties** dialog box, select the **Notifications** page.</span></span>  
  
4.  <span data-ttu-id="fe290-119">Se si vuole inviare una notifica a un operatore tramite posta elettronica, selezionare la casella **Posta elettronica**, selezionare un operatore nell'elenco e scegliere una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="fe290-119">If you want to notify an operator by e-mail, check **E-mail**, select an operator from the list, and then select one of the following:</span></span>  
  
    -   <span data-ttu-id="fe290-120">**In caso di esito positivo processo** per inviare la notifica all'operatore se il processo è stato completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="fe290-120">**When the job succeeds** to notify the operator when the job completes successfully.</span></span>  
  
    -   <span data-ttu-id="fe290-121">**In caso di esito negativo processo** per inviare all'operatore una notifica del completamento non riuscito del processo.</span><span class="sxs-lookup"><span data-stu-id="fe290-121">**When the job fails** to notify the operator when the job completes unsuccessfully.</span></span>  
  
    -   <span data-ttu-id="fe290-122">**Al termine del processo** per inviare la notifica all'operatore indipendentemente dallo stato di completamento.</span><span class="sxs-lookup"><span data-stu-id="fe290-122">**When the job completes** to notify the operator regardless of completion status.</span></span>  
  
5.  <span data-ttu-id="fe290-123">Se si desidera inviare una notifica a un operatore tramite cercapersone, selezionare la casella **Cercapersone**, selezionare un operatore nell'elenco e quindi scegliere una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="fe290-123">If you want to notify an operator by pager, check **Page**, select an operator from the list, and then select one of the following:</span></span>  
  
    -   <span data-ttu-id="fe290-124">**In caso di esito positivo processo** per inviare la notifica all'operatore se il processo è stato completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="fe290-124">**When the job succeeds** to notify the operator when the job completes successfully.</span></span>  
  
    -   <span data-ttu-id="fe290-125">**In caso di esito negativo processo** per inviare all'operatore una notifica del completamento non riuscito del processo.</span><span class="sxs-lookup"><span data-stu-id="fe290-125">**When the job fails** to notify the operator when the job completes unsuccessfully.</span></span>  
  
    -   <span data-ttu-id="fe290-126">**Al termine del processo** per inviare la notifica all'operatore indipendentemente dallo stato di completamento.</span><span class="sxs-lookup"><span data-stu-id="fe290-126">**When the job completes** to notify the operator regardless of completion status.</span></span>  
  
6.  <span data-ttu-id="fe290-127">Se si desidera inviare una notifica a un operatore tramite Net Send, selezionare la casella **Net Send**, selezionare un operatore nell'elenco e quindi scegliere una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="fe290-127">If you want to notify an operator by net send, check **Net send**, select an operator from the list, and then select one of the following:</span></span>  
  
    -   <span data-ttu-id="fe290-128">**In caso di esito positivo processo** per inviare la notifica all'operatore se il processo è stato completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="fe290-128">**When the job succeeds** to notify the operator when the job completes successfully.</span></span>  
  
    -   <span data-ttu-id="fe290-129">**In caso di esito negativo processo** per inviare all'operatore una notifica del completamento non riuscito del processo.</span><span class="sxs-lookup"><span data-stu-id="fe290-129">**When the job fails** to notify the operator when the job completes unsuccessfully.</span></span>  
  
    -   <span data-ttu-id="fe290-130">**Al termine del processo** per inviare la notifica all'operatore indipendentemente dallo stato di completamento.</span><span class="sxs-lookup"><span data-stu-id="fe290-130">**When the job completes** to notify the operator regardless of completion status.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="fe290-131">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="fe290-131">Using Transact-SQL</span></span>  
  
#### <a name="to-notify-an-operator-of-job-status"></a><span data-ttu-id="fe290-132">Per notificare lo stato di un processo a un operatore</span><span class="sxs-lookup"><span data-stu-id="fe290-132">To notify an operator of job status</span></span>  
  
1.  <span data-ttu-id="fe290-133">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fe290-133">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="fe290-134">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="fe290-134">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="fe290-135">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="fe290-135">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- adds an e-mail notification for the specified alert (Test Alert).  
    -- This example assumes that Test Alert already exists and that Fran??ois Ajenstat is a valid operator name.  
    USE msdb ;  
    GO  
    EXEC dbo.sp_add_notification   
    @alert_name = N'Test Alert',   
    @operator_name = N'Fran??ois Ajenstat',   
    @notification_method = 1 ;  
    GO  
    ```  
  
 <span data-ttu-id="fe290-136">Per ulteriori informazioni, vedere [sp_add_notification &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-add-notification-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="fe290-136">For more information, see [sp_add_notification &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-notification-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="fe290-137">Utilizzo di SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="fe290-137">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="fe290-138">**Per notificare lo stato di un processo a un operatore**</span><span class="sxs-lookup"><span data-stu-id="fe290-138">**To notify an operator of job status**</span></span>  
  
 <span data-ttu-id="fe290-139">Usare la classe `Job` tramite un linguaggio di programmazione scelto come Visual Basic, Visual C# o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fe290-139">Use the `Job` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="fe290-140">Per altre informazioni, vedere [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span><span class="sxs-lookup"><span data-stu-id="fe290-140">For more information, see [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span></span>  
