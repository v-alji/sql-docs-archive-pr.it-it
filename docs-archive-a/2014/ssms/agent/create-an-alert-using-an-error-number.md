---
title: Creare un avviso usando un numero di errore | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- alerts [SQL Server], creating
- SQL Server Agent, alerts
- alerts [SQL Server], error numbers
ms.assetid: 03dd7fac-5073-4f86-babd-37e45a86023c
author: stevestein
ms.author: sstein
ms.openlocfilehash: a98f64bc5b9dffc3e2494a0c36c8fc04cdfb6fa2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629710"
---
# <a name="create-an-alert-using-an-error-number"></a><span data-ttu-id="95def-102">Creazione di un avviso utilizzando un numero di errore</span><span class="sxs-lookup"><span data-stu-id="95def-102">Create an Alert Using an Error Number</span></span>
  <span data-ttu-id="95def-103">In questo argomento viene descritto come creare un [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] avviso di Agent in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] che verrà generato quando si verifica un errore di un numero specifico tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="95def-103">This topic describes how to create a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alert occurs in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] that will be raised when an error of a specific number occurs by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="95def-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="95def-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="95def-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="95def-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="95def-106">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="95def-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="95def-107">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="95def-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="95def-108">**Per creare un avviso utilizzando un numero di errore utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="95def-108">**To create an alert using an error number, using:**</span></span>  
  
     [<span data-ttu-id="95def-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="95def-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="95def-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="95def-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="95def-111">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="95def-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="95def-112">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="95def-112">Limitations and Restrictions</span></span>  
  
-   [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="95def-113">include un semplice strumento grafico per la gestione del sistema di avvisi ed è lo strumento consigliato per la configurazione di un'infrastruttura di avvisi.</span><span class="sxs-lookup"><span data-stu-id="95def-113">provides an easy, graphical way to manage the entire alerting system and is the recommended way to configure an alert infrastructure.</span></span>  
  
-   <span data-ttu-id="95def-114">Gli eventi generati con la stored procedure **xp_logevent** si verificano nel database master.</span><span class="sxs-lookup"><span data-stu-id="95def-114">Events generated with **xp_logevent** occur in the master database.</span></span> <span data-ttu-id="95def-115">Pertanto, **xp_logevent** genera un avviso solo se **@database_name** per l'avviso è **'master'** o NULL.</span><span class="sxs-lookup"><span data-stu-id="95def-115">Therefore, **xp_logevent** does not trigger an alert unless the **@database_name** for the alert is **'master'** or NULL.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="95def-116">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="95def-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="95def-117">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="95def-117">Permissions</span></span>  
 <span data-ttu-id="95def-118">Per impostazione predefinita, solo i membri del ruolo predefinito del server **sysadmin** possono eseguire **sp_add_alert**.</span><span class="sxs-lookup"><span data-stu-id="95def-118">By default, only members of the **sysadmin** fixed server role can execute **sp_add_alert**.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="95def-119">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="95def-119">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-an-alert-using-an-error-number"></a><span data-ttu-id="95def-120">Per creare un avviso utilizzando un numero di errore</span><span class="sxs-lookup"><span data-stu-id="95def-120">To create an alert using an error number</span></span>  
  
1.  <span data-ttu-id="95def-121">In **Esplora oggetti** fare clic sul segno più per espandere il server in cui si desidera creare un avviso tramite un numero di errore.</span><span class="sxs-lookup"><span data-stu-id="95def-121">In **Object Explorer,** click the plus sign to expand the server where you want to create an alert using an error number.</span></span>  
  
2.  <span data-ttu-id="95def-122">Fare clic sul segno più per espandere **SQL Server Agent**.</span><span class="sxs-lookup"><span data-stu-id="95def-122">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="95def-123">Fare clic con il pulsante destro del mouse su **Avvisi** e selezionare **Nuovo avviso**.</span><span class="sxs-lookup"><span data-stu-id="95def-123">Right-click **Alerts** and select **New Alert**.</span></span>  
  
4.  <span data-ttu-id="95def-124">Nella casella **Nome** della finestra di dialogo **Nuovo avviso** immettere un nome per l'avviso.</span><span class="sxs-lookup"><span data-stu-id="95def-124">In the **New Alert** dialog box, in the **Name** box, enter a name for this alert.</span></span>  
  
5.  <span data-ttu-id="95def-125">Selezionare la casella di controllo **Abilita** per abilitare l'esecuzione dell'avviso.</span><span class="sxs-lookup"><span data-stu-id="95def-125">Check the **Enable** check box to enable the alert to run.</span></span> <span data-ttu-id="95def-126">Per impostazione predefinita, l'opzione **Abilita** è selezionata.</span><span class="sxs-lookup"><span data-stu-id="95def-126">By default, **Enable** is checked.</span></span>  
  
6.  <span data-ttu-id="95def-127">Nell'elenco **Tipo** selezionare **Avviso per evento di SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="95def-127">In the **Type** list, select **SQL Server event alert**.</span></span>  
  
7.  <span data-ttu-id="95def-128">Nell'elenco **Nome database**sotto **Definizione di avviso di evento** selezionare un database per limitare l'avviso a un database specifico.</span><span class="sxs-lookup"><span data-stu-id="95def-128">Under **Event alert definition**, in the **Database name** list, select a database to restrict the alert to a specific database.</span></span>  
  
8.  <span data-ttu-id="95def-129">In **Genera avvisi in base a**fare clic su **Numero errore**, quindi digitare un numero errore valido per l'avviso.</span><span class="sxs-lookup"><span data-stu-id="95def-129">Under **Alerts will be raised based on**, click **Error number**, and then type a valid error number for the alert.</span></span> <span data-ttu-id="95def-130">Alternativamente, fare clic su **Gravità** , quindi selezionare la gravità specifica che genererà l'avviso.</span><span class="sxs-lookup"><span data-stu-id="95def-130">Alternately, click **Severity** and then select the specific severity that will raise the alert.</span></span>  
  
9. <span data-ttu-id="95def-131">Per limitare l'avviso a una particolare sequenza di caratteri, selezionare la casella di controllo corrispondente a **Genera avviso quando il messaggio contiene** e immettere una parola chiave o una stringa di caratteri nella casella **Testo del messaggio**.</span><span class="sxs-lookup"><span data-stu-id="95def-131">Check the box corresponding to **Raise alert when message contains** check box to restrict the alert to a particular character sequence, and then enter a keyword or character string for the **Message text**.</span></span> <span data-ttu-id="95def-132">Il numero massimo di caratteri consentito è 100.</span><span class="sxs-lookup"><span data-stu-id="95def-132">The maximum number of characters is 100.</span></span>  
  
10. <span data-ttu-id="95def-133">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="95def-133">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="95def-134">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="95def-134">Using Transact-SQL</span></span>  
  
#### <a name="to-create-an-alert-using-an-error-number"></a><span data-ttu-id="95def-135">Per creare un avviso utilizzando un numero di errore</span><span class="sxs-lookup"><span data-stu-id="95def-135">To create an alert using an error number</span></span>  
  
1.  <span data-ttu-id="95def-136">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="95def-136">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="95def-137">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="95def-137">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="95def-138">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="95def-138">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- adds an alert (Test Alert) that runs the Back up the AdventureWorks2012 Database job when fired   
    -- assumes that the message 55001 and the Back up the AdventureWorks2012 Database job already exist.  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_add_alert  
        @name = N'Test Alert',  
        @message_id = 55001,   
       @severity = 0,   
       @notification_message = N'Error 55001 has occurred. The database will be backed up...',   
       @job_name = N'Back up the AdventureWorks2012 Database' ;  
    GO  
    ```  
  
 <span data-ttu-id="95def-139">Per ulteriori informazioni, vedere [sp_add_alert &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-add-alert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="95def-139">For more information, see [sp_add_alert &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-alert-transact-sql).</span></span>  
  
  
