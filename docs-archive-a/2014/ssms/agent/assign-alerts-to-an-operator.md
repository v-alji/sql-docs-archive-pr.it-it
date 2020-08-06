---
title: Assegnare avvisi a un operatore | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, operators
- assigning alerts to operator
- SQL Server Agent, alerts
- alerts [SQL Server], assigning to operator
- jobs [SQL Server Agent], operators
- notifications [SQL Server], job status
ms.assetid: aa818155-6fa2-4565-a09f-5c7e31c89754
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3cc238b952c03595035856f377b6fdbb9eaf5e2c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628075"
---
# <a name="assign-alerts-to-an-operator"></a><span data-ttu-id="0f9ff-102">Assegnazione di avvisi a un operatore</span><span class="sxs-lookup"><span data-stu-id="0f9ff-102">Assign Alerts to an Operator</span></span>
  <span data-ttu-id="0f9ff-103">In questo argomento viene descritto come assegnare [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] avvisi di Agent agli operatori in modo che possano ricevere notifiche relative ai processi in utilizzando [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0f9ff-103">This topic describes how to assign [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alerts to operators so they can receive notifications about jobs in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="0f9ff-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="0f9ff-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="0f9ff-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="0f9ff-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="0f9ff-106">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="0f9ff-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="0f9ff-107">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="0f9ff-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="0f9ff-108">**Per assegnare avvisi a un operatore utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="0f9ff-108">**To assign alerts to an operator, using:**</span></span>  
  
     [<span data-ttu-id="0f9ff-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0f9ff-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="0f9ff-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0f9ff-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="0f9ff-111">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="0f9ff-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="0f9ff-112">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="0f9ff-112">Limitations and Restrictions</span></span>  
  
-   [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="0f9ff-113">include un semplice strumento grafico per la gestione del sistema di avvisi.</span><span class="sxs-lookup"><span data-stu-id="0f9ff-113">provides an easy, graphical way to manage the entire alerting system.</span></span> <span data-ttu-id="0f9ff-114">[!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] è lo strumento consigliato per la configurazione di un'infrastruttura di avvisi.</span><span class="sxs-lookup"><span data-stu-id="0f9ff-114">Using [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] is the recommended way to configure your alert infrastructure.</span></span>  
  
-   <span data-ttu-id="0f9ff-115">Per inviare una notifica in risposta a un avviso, è innanzitutto necessario configurare [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent per l'invio di messaggi.</span><span class="sxs-lookup"><span data-stu-id="0f9ff-115">To send a notification in response to an alert, you must first configure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to send mail.</span></span> <span data-ttu-id="0f9ff-116">Per altre informazioni, vedere [Configure SQL Server Agent Mail to Use Database Mail](../../relational-databases/database-mail/configure-sql-server-agent-mail-to-use-database-mail.md).</span><span class="sxs-lookup"><span data-stu-id="0f9ff-116">For more information, see [Configure SQL Server Agent Mail to Use Database Mail](../../relational-databases/database-mail/configure-sql-server-agent-mail-to-use-database-mail.md).</span></span>  
  
-   <span data-ttu-id="0f9ff-117">Gli eventuali errori che si verificano durante l'invio di un messaggio di posta elettronica o di una notifica su cercapersone vengono registrati nel log degli errori di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="0f9ff-117">If a failure occurs when sending an e-mail message or pager notification, the failure is reported in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service error log.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="0f9ff-118">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="0f9ff-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="0f9ff-119">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="0f9ff-119">Permissions</span></span>  
 <span data-ttu-id="0f9ff-120">Solo i membri del ruolo predefinito del server **sysadmin** possono assegnare avvisi agli operatori.</span><span class="sxs-lookup"><span data-stu-id="0f9ff-120">Only members of the **sysadmin** fixed server role can assign alerts to operators.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="0f9ff-121">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0f9ff-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-assign-alerts-to-an-operator"></a><span data-ttu-id="0f9ff-122">Per assegnare avvisi a un operatore</span><span class="sxs-lookup"><span data-stu-id="0f9ff-122">To assign alerts to an operator</span></span>  
  
1.  <span data-ttu-id="0f9ff-123">In **Esplora oggetti**fare clic sul segno più per espandere il server contenente l'operatore a cui si desidera assegnare un avviso.</span><span class="sxs-lookup"><span data-stu-id="0f9ff-123">In **Object Explorer**, click the plus sign to expand the server that contains the operator to which you want to assign an alert.</span></span>  
  
2.  <span data-ttu-id="0f9ff-124">Fare clic sul segno più per espandere **SQL Server Agent**.</span><span class="sxs-lookup"><span data-stu-id="0f9ff-124">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="0f9ff-125">Fare clic sul segno più per espandere la cartella **Operatori** .</span><span class="sxs-lookup"><span data-stu-id="0f9ff-125">Click the plus sign to expand the **Operators** folder.</span></span>  
  
4.  <span data-ttu-id="0f9ff-126">Fare clic con il pulsante destro del mouse sull'operatore a cui assegnare un avviso, scegliere **Proprietà**e selezionare la pagina **Notifiche** .</span><span class="sxs-lookup"><span data-stu-id="0f9ff-126">Right-click the operator to which you want to assign an alert and select **Properties**, and select the **Notifications** page.</span></span>  
  
5.  <span data-ttu-id="0f9ff-127">In _Seleziona una pagina_**nella finestra di dialogo** Proprietà **nome_operatore**selezionare **Notifiche**.</span><span class="sxs-lookup"><span data-stu-id="0f9ff-127">In the _operator_name_**Properties** dialog box, under **Select a page**, select **Notifications**.</span></span>  
  
6.  <span data-ttu-id="0f9ff-128">Nell'area **Visualizza le notifiche inviate all'utente per**selezionare **Avvisi** per visualizzare un elenco di avvisi inviati all'operatore oppure selezionare **Processi** per visualizzare un elenco dei processi che inviano notifiche all'operatore.</span><span class="sxs-lookup"><span data-stu-id="0f9ff-128">Under **View notifications sent to this user by**, select **Alerts** to view a list of alerts sent to this operator or select **Jobs** to view a list of jobs that send notifications to this operator.</span></span> <span data-ttu-id="0f9ff-129">Selezionare una o più tra le caselle di controllo seguenti per definire il metodo di notifica secondo le necessità: **Posta elettronica**, **CERCAPERSONE**oppure **Net Send**.</span><span class="sxs-lookup"><span data-stu-id="0f9ff-129">Select one or more of the following checkboxes to define the notification method for each notification as necessary: **E-mail**, **Pager**, or **Net send**.</span></span>  
  
7.  <span data-ttu-id="0f9ff-130">Al termine, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="0f9ff-130">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="0f9ff-131">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0f9ff-131">Using Transact-SQL</span></span>  
  
#### <a name="to-assign-alerts-to-an-operator"></a><span data-ttu-id="0f9ff-132">Per assegnare avvisi a un operatore</span><span class="sxs-lookup"><span data-stu-id="0f9ff-132">To assign alerts to an operator</span></span>  
  
1.  <span data-ttu-id="0f9ff-133">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0f9ff-133">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="0f9ff-134">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="0f9ff-134">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="0f9ff-135">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="0f9ff-135">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- adds an e-mail notification for the specified alert (Test Alert)  
    -- This example assumes that Test Alert already exists and that Fran??ois Ajenstat is a valid operator name.  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_add_notification  
     @alert_name = N'Test Alert',  
     @operator_name = N'Fran??ois Ajenstat',  
     @notification_method = 1 ;  
    GO  
    ```  
  
 <span data-ttu-id="0f9ff-136">Per ulteriori informazioni, vedere [sp_add_notification &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-add-notification-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0f9ff-136">For more information, see [sp_add_notification &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-notification-transact-sql).</span></span>  
  
  
