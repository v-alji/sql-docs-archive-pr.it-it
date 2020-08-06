---
title: Definire la risposta a un avviso (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, alerts
- alerts [SQL Server], responding to
- responding to alerts
ms.assetid: c86ca6eb-c59f-46e9-bc32-d474e7c3b170
author: stevestein
ms.author: sstein
ms.openlocfilehash: c14e5adf43602b57697483b9ce4c2cdf20ff8e10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715032"
---
# <a name="define-the-response-to-an-alert-sql-server-management-studio"></a><span data-ttu-id="303b7-102">Define the Response to an Alert (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="303b7-102">Define the Response to an Alert (SQL Server Management Studio)</span></span>
  <span data-ttu-id="303b7-103">In questo argomento viene descritto come definire il modo in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cui risponde agli [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] avvisi di Agent in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="303b7-103">This topic describes how to define how [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] responds to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alerts in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="303b7-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="303b7-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="303b7-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="303b7-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="303b7-106">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="303b7-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="303b7-107">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="303b7-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="303b7-108">**Per definire la risposta a un avviso tramite:**</span><span class="sxs-lookup"><span data-stu-id="303b7-108">**To define the response to an alert, using:**</span></span>  
  
     [<span data-ttu-id="303b7-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="303b7-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="303b7-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="303b7-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="303b7-111">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="303b7-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="303b7-112">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="303b7-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="303b7-113">Le opzioni Cercapersone e **net send** verranno rimosse da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent in una versione futura di [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="303b7-113">The Pager and **net send** options will be removed from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent in a future version of [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="303b7-114">Evitare pertanto di utilizzarle in un nuovo progetto di sviluppo e prevedere interventi di modifica nelle applicazioni in cui sono state implementate.</span><span class="sxs-lookup"><span data-stu-id="303b7-114">Avoid using these features in new development work, and plan to modify applications that currently use these features.</span></span>  
  
-   <span data-ttu-id="303b7-115">Si noti che per inviare notifiche tramite posta elettronica e cercapersone agli operatori, è necessario configurare SQL Server Agent per l'utilizzo di Posta elettronica database.</span><span class="sxs-lookup"><span data-stu-id="303b7-115">Note that SQL Server Agent must be configured to use Database Mail to send e-mail and pager notifications to operators.</span></span> <span data-ttu-id="303b7-116">Per ulteriori informazioni, vedere [Procedura: Assegnazione di avvisi a un operatore (SQL Server Management Studio)](assign-alerts-to-an-operator.md).</span><span class="sxs-lookup"><span data-stu-id="303b7-116">For more information, see [Assign Alerts to an Operator](assign-alerts-to-an-operator.md).</span></span>  
  
-   [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="303b7-117">è incluso un semplice strumento grafico per la gestione dei processi, che è lo strumento consigliato per la creazione e la gestione dell'infrastruttura dei processi.</span><span class="sxs-lookup"><span data-stu-id="303b7-117">provides an easy, graphical way to manage jobs, and is the recommended way to create and manage the job infrastructure.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="303b7-118">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="303b7-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="303b7-119">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="303b7-119">Permissions</span></span>  
 <span data-ttu-id="303b7-120">Solo i membri del ruolo predefinito del server **sysadmin** possono definire la risposta a un avviso.</span><span class="sxs-lookup"><span data-stu-id="303b7-120">Only members of the **sysadmin** fixed server role can define the response to an alert.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="303b7-121">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="303b7-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-define-the-response-to-an-alert"></a><span data-ttu-id="303b7-122">Per definire la risposta a un avviso</span><span class="sxs-lookup"><span data-stu-id="303b7-122">To define the response to an alert</span></span>  
  
1.  <span data-ttu-id="303b7-123">In **Esplora oggetti**fare clic sul segno più per espandere il server contenente l'avviso per cui si desidera definire una risposta.</span><span class="sxs-lookup"><span data-stu-id="303b7-123">In **Object Explorer**, click the plus sign to expand the server that contains the alert on which you want to define a response.</span></span>  
  
2.  <span data-ttu-id="303b7-124">Fare clic sul segno più per espandere **SQL Server Agent**.</span><span class="sxs-lookup"><span data-stu-id="303b7-124">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="303b7-125">Fare clic sul segno più per espandere la cartella **Avvisi** .</span><span class="sxs-lookup"><span data-stu-id="303b7-125">Click the plus sign to expand the **Alerts** folder.</span></span>  
  
4.  <span data-ttu-id="303b7-126">Fare clic con il pulsante destro del mouse sull'avviso per cui si desidera definire una risposta e selezionare **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="303b7-126">Right-click the alert on which you want to define a response and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="303b7-127">Nella finestra di dialogo**Proprietà avviso** _alert_name_selezionare **risposta**in **Selezione pagina**.</span><span class="sxs-lookup"><span data-stu-id="303b7-127">In the _alert_name_**alert properties** dialog box, under **Select a page**, select **Response**.</span></span>  
  
6.  <span data-ttu-id="303b7-128">Selezionare la casella di controllo **Esegui processo** e, dall'elenco sottostante la casella di controllo **Esegui processo**, selezionare il processo da eseguire quando viene generato l'avviso.</span><span class="sxs-lookup"><span data-stu-id="303b7-128">Select the **Execute job** check box and, from the list below the **Execute job** check box, select a job to execute when the alert occurs.</span></span> <span data-ttu-id="303b7-129">È possibile creare un nuovo processo facendo clic su **Nuovo processo**.</span><span class="sxs-lookup"><span data-stu-id="303b7-129">You can create a new job by clicking **New Job**.</span></span> <span data-ttu-id="303b7-130">Per visualizzare ulteriori informazioni sul processo, fare clic su **Visualizza processo**.</span><span class="sxs-lookup"><span data-stu-id="303b7-130">You can view more information about the job by clicking **View Job**.</span></span> <span data-ttu-id="303b7-131">Per ulteriori informazioni sulle opzioni disponibili nelle finestre di dialogo **nuovo processo** e **Proprietà processo**_Job_name_ , vedere [creare un processo](create-a-job.md) e [visualizzare un processo](view-a-job.md).</span><span class="sxs-lookup"><span data-stu-id="303b7-131">For more information about the available options in the **New Job** and **Job Properties**_job_name_ dialog boxes, see [Create a Job](create-a-job.md) and [View a Job](view-a-job.md).</span></span>  
  
7.  <span data-ttu-id="303b7-132">Selezionare la casella di controllo **Invia notifica a operatori** se si desidera notificare agli operatori quando viene attivato l'avviso.</span><span class="sxs-lookup"><span data-stu-id="303b7-132">Select the **Notify Operators** check box if you want to notify operators when the alert is activated.</span></span> <span data-ttu-id="303b7-133">In **Elenco operatori**selezionare uno o più dei metodi seguenti per inviare la notifica all'operatore o agli operatori: **Posta elettronica**, **Cercapersone**o **Net Send**.</span><span class="sxs-lookup"><span data-stu-id="303b7-133">In the **Operator list**, select one or more of the following methods for notifying the operator or operators: **E-mail**, **Pager**, or **Net Send**.</span></span> <span data-ttu-id="303b7-134">È possibile creare un nuovo operatore facendo clic su **Nuovo operatore**.</span><span class="sxs-lookup"><span data-stu-id="303b7-134">You can create a new operator by clicking **New Operator**.</span></span> <span data-ttu-id="303b7-135">Per visualizzare ulteriori informazioni su un operatore, fare clic su **Visualizza operatore**.</span><span class="sxs-lookup"><span data-stu-id="303b7-135">You can view more information about an operator by clicking **View Operator**.</span></span> <span data-ttu-id="303b7-136">Per ulteriori informazioni sulle opzioni disponibili nelle finestre di dialogo delle proprietà **Nuovo operatore** e **Visualizza operatore** , vedere [Create an Operator](create-an-operator.md) e [View Information About an Operator](view-information-about-an-operator.md).</span><span class="sxs-lookup"><span data-stu-id="303b7-136">For more information about the available options in the **New Operator** and **View Operator Properties** dialog boxes, see [Create an Operator](create-an-operator.md) and [View Information About an Operator](view-information-about-an-operator.md).</span></span>  
  
8.  <span data-ttu-id="303b7-137">Al termine, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="303b7-137">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="303b7-138">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="303b7-138">Using Transact-SQL</span></span>  
  
#### <a name="to-define-the-response-to-an-alert"></a><span data-ttu-id="303b7-139">Per definire la risposta a un avviso</span><span class="sxs-lookup"><span data-stu-id="303b7-139">To define the response to an alert</span></span>  
  
1.  <span data-ttu-id="303b7-140">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="303b7-140">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="303b7-141">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="303b7-141">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="303b7-142">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="303b7-142">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- adds an e-mail notification for Test Alert.  
    -- assumes that Test Alert already exists and that Fran??ois Ajenstat is a valid operator name   
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_add_notification  
     @alert_name = N'Test Alert',  
     @operator_name = N'Fran??ois Ajenstat',  
     @notification_method = 1 ;  
    GO  
    ```  
  
 <span data-ttu-id="303b7-143">Per ulteriori informazioni, vedere [sp_add_notification &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-add-notification-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="303b7-143">For more information, see [sp_add_notification &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-notification-transact-sql).</span></span>  
  
  
