---
title: Creare un avviso per evento WMI | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- WMI event alerts [SQL Server Management Studio]
ms.assetid: b8c46db6-408b-484e-98f0-a8af3e7ec763
author: stevestein
ms.author: sstein
ms.openlocfilehash: 737e7ccac9c92e663040e71339aa120f8db8b80b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630247"
---
# <a name="create-a-wmi-event-alert"></a><span data-ttu-id="2cbe4-102">Creare un avviso per evento WMI</span><span class="sxs-lookup"><span data-stu-id="2cbe4-102">Create a WMI Event Alert</span></span>
  <span data-ttu-id="2cbe4-103">In questo argomento viene descritto come creare un avviso di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent che viene generato quando si verifica un evento specifico di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] monitorato dal provider WMI per eventi del server in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2cbe4-103">This topic describes how to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alert that is raised when a specific [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] event occurs that is monitored by the WMI Provider for Server Events in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="2cbe4-104">Per informazioni sull'utilizzo del provider WMI per il monitoraggio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] degli eventi, vedere [concetti relativi al provider WMI per eventi del server](../../relational-databases/wmi-provider-server-events/wmi-provider-for-server-events-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="2cbe4-104">For information about the using the WMI Provider to monitor [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] events, see [WMI Provider for Server Events Concepts](../../relational-databases/wmi-provider-server-events/wmi-provider-for-server-events-concepts.md).</span></span> <span data-ttu-id="2cbe4-105">Per informazioni sulle autorizzazioni necessarie per ricevere notifiche di avviso per eventi WMI, vedere [Selezionare un account per il servizio SQL Server Agent](select-an-account-for-the-sql-server-agent-service.md).</span><span class="sxs-lookup"><span data-stu-id="2cbe4-105">For information about the permissions necessary to receive WMI event alert notifications, see [Select an Account for the SQL Server Agent Service](select-an-account-for-the-sql-server-agent-service.md).</span></span> <span data-ttu-id="2cbe4-106">Per altre informazioni su WQL, vedere [Utilizzo di WQL con il provider WMI per eventi del server](../../relational-databases/wmi-provider-server-events/using-wql-with-the-wmi-provider-for-server-events.md).</span><span class="sxs-lookup"><span data-stu-id="2cbe4-106">For more information about WQL, see [Using WQL with the WMI Provider for Server Events](../../relational-databases/wmi-provider-server-events/using-wql-with-the-wmi-provider-for-server-events.md).</span></span>  
  
 <span data-ttu-id="2cbe4-107">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="2cbe4-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="2cbe4-108">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="2cbe4-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="2cbe4-109">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="2cbe4-109">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="2cbe4-110">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="2cbe4-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="2cbe4-111">**Per creare un avviso per evento WMI utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="2cbe4-111">**To create a WMI event alert, using:**</span></span>  
  
     [<span data-ttu-id="2cbe4-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2cbe4-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="2cbe4-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2cbe4-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="2cbe4-114">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="2cbe4-114">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="2cbe4-115">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="2cbe4-115">Limitations and Restrictions</span></span>  
  
-   [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="2cbe4-116">include un semplice strumento grafico per la gestione del sistema di avvisi ed è lo strumento consigliato per la configurazione di un'infrastruttura di avvisi.</span><span class="sxs-lookup"><span data-stu-id="2cbe4-116">provides an easy, graphical way to manage the entire alerting system and is the recommended way to configure an alert infrastructure.</span></span>  
  
-   <span data-ttu-id="2cbe4-117">Gli eventi generati con la stored procedure **xp_logevent** si verificano nel database master.</span><span class="sxs-lookup"><span data-stu-id="2cbe4-117">Events generated with **xp_logevent** occur in the master database.</span></span> <span data-ttu-id="2cbe4-118">Pertanto, **xp_logevent** genera un avviso solo se **@database_name** per l'avviso è **'master'** o NULL.</span><span class="sxs-lookup"><span data-stu-id="2cbe4-118">Therefore, **xp_logevent** does not trigger an alert unless the **@database_name** for the alert is **'master'** or NULL.</span></span>  
  
-   <span data-ttu-id="2cbe4-119">Sono supportati solo gli spazi dei nomi WMI sul computer in cui è in esecuzione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="2cbe4-119">Only WMI namespaces on the computer that runs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent are supported.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="2cbe4-120">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="2cbe4-120">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="2cbe4-121">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="2cbe4-121">Permissions</span></span>  
 <span data-ttu-id="2cbe4-122">Per impostazione predefinita, solo i membri del ruolo predefinito del server **sysadmin** possono eseguire **sp_add_alert**.</span><span class="sxs-lookup"><span data-stu-id="2cbe4-122">By default, only members of the **sysadmin** fixed server role can execute **sp_add_alert**.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="2cbe4-123">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2cbe4-123">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-wmi-event-alert"></a><span data-ttu-id="2cbe4-124">Per creare un avviso per evento WMI</span><span class="sxs-lookup"><span data-stu-id="2cbe4-124">To create a WMI event alert</span></span>  
  
1.  <span data-ttu-id="2cbe4-125">In **Esplora oggetti** fare clic sul segno più per espandere il server in cui si desidera creare un avviso di evento WMI.</span><span class="sxs-lookup"><span data-stu-id="2cbe4-125">In **Object Explorer,** click the plus sign to expand the server where you want to create a WMI event alert.</span></span>  
  
2.  <span data-ttu-id="2cbe4-126">Fare clic sul segno più per espandere **SQL Server Agent**.</span><span class="sxs-lookup"><span data-stu-id="2cbe4-126">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="2cbe4-127">Fare clic con il pulsante destro del mouse su **Avvisi** e selezionare **Nuovo avviso**.</span><span class="sxs-lookup"><span data-stu-id="2cbe4-127">Right-click **Alerts** and select **New Alert**.</span></span>  
  
4.  <span data-ttu-id="2cbe4-128">Nella casella **Nome** della finestra di dialogo **Nuovo avviso** immettere un nome per l'avviso.</span><span class="sxs-lookup"><span data-stu-id="2cbe4-128">In the **New Alert** dialog box, in the **Name** box, enter a name for this alert.</span></span>  
  
5.  <span data-ttu-id="2cbe4-129">Selezionare la casella di controllo **Abilita** per abilitare l'esecuzione dell'avviso.</span><span class="sxs-lookup"><span data-stu-id="2cbe4-129">Check the **Enable** check box to enable the alert to run.</span></span> <span data-ttu-id="2cbe4-130">Per impostazione predefinita, l'opzione **Abilita** è selezionata.</span><span class="sxs-lookup"><span data-stu-id="2cbe4-130">By default, **Enable** is checked.</span></span>  
  
6.  <span data-ttu-id="2cbe4-131">Nell'elenco **Tipo** selezionare **Avviso per evento WMI**.</span><span class="sxs-lookup"><span data-stu-id="2cbe4-131">In the **Type** list, select **WMI event alert**.</span></span>  
  
7.  <span data-ttu-id="2cbe4-132">Nella casella **Spazio dei nomi**in **Definizione di avviso di evento WMI** specificare lo spazio dei nomi WMI da usare per l'istruzione WQL (WMI Query Language) che identifica l'evento WMI che attiva l'avviso.</span><span class="sxs-lookup"><span data-stu-id="2cbe4-132">Under **WMI event alert definition**, in the **Namespace** box, specify the WMI namespace for the WMI Query Language (WQL) statement that identifies which WMI event will trigger this alert.</span></span>  
  
8.  <span data-ttu-id="2cbe4-133">Nella casella **Query** specificare l'istruzione WQL che identifica l'evento al quale risponde l'avviso.</span><span class="sxs-lookup"><span data-stu-id="2cbe4-133">In the **Query** box, specify the WQL statement that identifies the event that this alert responds to.</span></span>  
  
9. <span data-ttu-id="2cbe4-134">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="2cbe4-134">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="2cbe4-135">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2cbe4-135">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-wmi-event-alert"></a><span data-ttu-id="2cbe4-136">Per creare un avviso per evento WMI</span><span class="sxs-lookup"><span data-stu-id="2cbe4-136">To create a WMI event alert</span></span>  
  
1.  <span data-ttu-id="2cbe4-137">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2cbe4-137">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="2cbe4-138">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="2cbe4-138">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="2cbe4-139">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="2cbe4-139">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- creates a WMI event alert that retrieves all event properties for any ALTER_TABLE event that occurs on table AdventureWorks2012.Sales.SalesOrderDetail  
    -- This example assumes that the message 54001 already exists.  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_add_alert  
        @name = N'Test Alert 2',  
        @message_id = 54001  
        @notification_message = N'Error 54001 has occurred on the Sales.SalesOrderDetail table on the AdventureWorks2012 database. Please see the following information...',  
        @wmi_namespace = '\\.\root\Microsoft\SqlServer\ServerEvents\,  
        @wmi_query = N'SELECT * FROM ALTER_TABLE   
    WHERE DatabaseName = 'AdventureWorks2012' AND SchemaName = 'Sales'   
        AND ObjectType='Table' AND ObjectName = 'SalesOrderDetail'';  
    GO  
    ```  
  
 <span data-ttu-id="2cbe4-140">Per ulteriori informazioni, vedere [sp_add_alert &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-add-alert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2cbe4-140">For more information, see [sp_add_alert &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-alert-transact-sql).</span></span>  
  
  
