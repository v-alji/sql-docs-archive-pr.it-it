---
title: Modificare un operatore | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, operators
- modifying operators
- jobs [SQL Server Agent], operators
- operators (users) [Database Engine], modifying with Management Studio
ms.assetid: b2ba2168-ca0b-4b59-9007-4e1e4c30679e
author: stevestein
ms.author: sstein
ms.openlocfilehash: 45ffb520e240dfd97002060370ff6dcf7c60d083
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623725"
---
# <a name="edit-an-operator"></a><span data-ttu-id="6c744-102">Modifica di un operatore</span><span class="sxs-lookup"><span data-stu-id="6c744-102">Edit an Operator</span></span>
  <span data-ttu-id="6c744-103">In questo argomento viene descritto come modificare la disponibilità degli operatori per la ricezione di notifiche e dei relativi indirizzi di posta elettronica, cercapersone e Net Send in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6c744-103">This topic describes how to edit an operators' availability for receiving notifications and their e-mail, pager, and net send addresses in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="6c744-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="6c744-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="6c744-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="6c744-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="6c744-106">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="6c744-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="6c744-107">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="6c744-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="6c744-108">**Per modificare un operatore utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="6c744-108">**To edit an operator, using:**</span></span>  
  
     [<span data-ttu-id="6c744-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6c744-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="6c744-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6c744-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="6c744-111">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="6c744-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="6c744-112">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="6c744-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="6c744-113">Le opzioni Cercapersone e **net send** verranno rimosse da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent in una versione futura di [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6c744-113">The Pager and **net send** options will be removed from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent in a future version of [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="6c744-114">Evitare pertanto di utilizzarle in un nuovo progetto di sviluppo e prevedere interventi di modifica nelle applicazioni in cui sono state implementate.</span><span class="sxs-lookup"><span data-stu-id="6c744-114">Avoid using these features in new development work, and plan to modify applications that currently use these features.</span></span>  
  
-   <span data-ttu-id="6c744-115">Si noti che per inviare notifiche tramite posta elettronica e cercapersone agli operatori, è necessario configurare SQL Server Agent per l'utilizzo di Posta elettronica database.</span><span class="sxs-lookup"><span data-stu-id="6c744-115">Note that SQL Server Agent must be configured to use Database Mail to send e-mail and pager notifications to operators.</span></span> <span data-ttu-id="6c744-116">Per ulteriori informazioni, vedere [Procedura: Assegnazione di avvisi a un operatore (SQL Server Management Studio)](assign-alerts-to-an-operator.md).</span><span class="sxs-lookup"><span data-stu-id="6c744-116">For more information, see [Assign Alerts to an Operator](assign-alerts-to-an-operator.md).</span></span>  
  
-   [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="6c744-117">è incluso un semplice strumento grafico per la gestione dei processi, che è lo strumento consigliato per la creazione e la gestione dell'infrastruttura dei processi.</span><span class="sxs-lookup"><span data-stu-id="6c744-117">provides an easy, graphical way to manage jobs, and is the recommended way to create and manage the job infrastructure.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="6c744-118">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="6c744-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="6c744-119">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="6c744-119">Permissions</span></span>  
 <span data-ttu-id="6c744-120">Solo i membri del ruolo predefinito del server **sysadmin** possono modificare gli operatori.</span><span class="sxs-lookup"><span data-stu-id="6c744-120">Only members of the **sysadmin** fixed server role can edit operators.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="6c744-121">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6c744-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-edit-an-operator"></a><span data-ttu-id="6c744-122">Per modificare un operatore</span><span class="sxs-lookup"><span data-stu-id="6c744-122">To edit an operator</span></span>  
  
1.  <span data-ttu-id="6c744-123">In **Esplora oggetti**fare clic sul segno più per espandere il server che contiene l'operatore da modificare.</span><span class="sxs-lookup"><span data-stu-id="6c744-123">In **Object Explorer**, click the plus sign to expand the server that contains the operator you want to edit.</span></span>  
  
2.  <span data-ttu-id="6c744-124">Fare clic sul segno più per espandere **SQL Server Agent**.</span><span class="sxs-lookup"><span data-stu-id="6c744-124">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="6c744-125">Fare clic sul segno più per espandere la cartella **Operatori** .</span><span class="sxs-lookup"><span data-stu-id="6c744-125">Click the plus sign to expand the **Operators** folder.</span></span>  
  
4.  <span data-ttu-id="6c744-126">Fare clic con il pulsante destro del mouse sull'operatore da modificare e selezionare **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="6c744-126">Right-click the operator that you want to edit and select **Properties**.</span></span>  
  
     <span data-ttu-id="6c744-127">Per altre informazioni sulle opzioni disponibili contenute nella finestra di dialogo _Proprietà_**nome_operatore** , vedere:</span><span class="sxs-lookup"><span data-stu-id="6c744-127">For more information on the available options contained in the _operator_name_**Properties** dialog box, see:</span></span>  
  
    -   [<span data-ttu-id="6c744-128">Proprietà operatore e nuovo operatore &#40;pagina generale&#41;</span><span class="sxs-lookup"><span data-stu-id="6c744-128">Operator Properties and New Operator &#40;General Page&#41;</span></span>](../../integration-services/general-page-of-integration-services-designers-options.md)  
  
    -   [<span data-ttu-id="6c744-129">Proprietà operatore: pagina nuove notifiche operatore &#40;&#41;</span><span class="sxs-lookup"><span data-stu-id="6c744-129">Operator Properties: New Operator &#40;Notifications Page&#41;</span></span>](operator-properties-new-operator-notifications-page.md)  
  
    -   [<span data-ttu-id="6c744-130">Proprietà operatore &#40;pagina Cronologia&#41;</span><span class="sxs-lookup"><span data-stu-id="6c744-130">Operator Properties &#40;History Page&#41;</span></span>](operator-properties-history-page.md)  
  
5.  <span data-ttu-id="6c744-131">Al termine, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="6c744-131">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="6c744-132">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6c744-132">Using Transact-SQL</span></span>  
  
#### <a name="to-edit-an-operator"></a><span data-ttu-id="6c744-133">Per modificare un operatore</span><span class="sxs-lookup"><span data-stu-id="6c744-133">To edit an operator</span></span>  
  
1.  <span data-ttu-id="6c744-134">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6c744-134">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="6c744-135">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="6c744-135">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="6c744-136">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="6c744-136">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- updates the operator status to enabled, and sets the days   
    -- (from Monday through Friday, from 8 A.M. through 5 P.M.) when the operator can be paged.   
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_update_operator   
        @name = N'Fran??ois Ajenstat',  
        @enabled = 1,  
        @email_address = N'fran??oisa',  
        @pager_address = N'5551290AW@pager.Adventure-Works.com',  
        @weekday_pager_start_time = 080000,  
        @weekday_pager_end_time = 170000,  
        @pager_days = 64 ;  
    GO  
    ```  
  
 <span data-ttu-id="6c744-137">Per ulteriori informazioni, vedere [sp_update_operator &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-update-operator-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="6c744-137">For more information, see [sp_update_operator &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-operator-transact-sql).</span></span>  
  
  
