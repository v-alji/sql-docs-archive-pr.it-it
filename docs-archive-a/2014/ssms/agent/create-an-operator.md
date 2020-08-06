---
title: Creare un operatore | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, operators
- jobs [SQL Server Agent], notification options
- operators (users) [Database Engine], creating with Management Studio
- SQL Server Agent jobs, notification options
- jobs [SQL Server Agent], operators
- notifications [SQL Server], job status
ms.assetid: 1359d790-5905-4927-a208-e7155e7768a2
author: stevestein
ms.author: sstein
ms.openlocfilehash: dfe07042f9a4b8ac595ada8b86e7bad131032700
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715059"
---
# <a name="create-an-operator"></a><span data-ttu-id="b5b27-102">Create an Operator</span><span class="sxs-lookup"><span data-stu-id="b5b27-102">Create an Operator</span></span>
  <span data-ttu-id="b5b27-103">In questo argomento viene descritto come configurare un utente per la ricezione di notifiche relative ai [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] processi di Agent in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b5b27-103">This topic describes how to configure a user to receive notifications about [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="b5b27-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="b5b27-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="b5b27-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="b5b27-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="b5b27-106">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="b5b27-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="b5b27-107">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="b5b27-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="b5b27-108">**Per creare un operatore utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="b5b27-108">**To create an operator, using:**</span></span>  
  
     [<span data-ttu-id="b5b27-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b5b27-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="b5b27-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b5b27-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b5b27-111">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="b5b27-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="b5b27-112">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="b5b27-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="b5b27-113">Le opzioni Cercapersone e **net send** verranno rimosse da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent in una versione futura di [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b5b27-113">The Pager and **net send** options will be removed from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent in a future version of [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="b5b27-114">Evitare pertanto di utilizzarle in un nuovo progetto di sviluppo e prevedere interventi di modifica nelle applicazioni in cui sono state implementate.</span><span class="sxs-lookup"><span data-stu-id="b5b27-114">Avoid using these features in new development work, and plan to modify applications that currently use these features.</span></span>  
  
-   <span data-ttu-id="b5b27-115">Si noti che per inviare notifiche tramite posta elettronica e cercapersone agli operatori, è necessario configurare SQL Server Agent per l'utilizzo di Posta elettronica database.</span><span class="sxs-lookup"><span data-stu-id="b5b27-115">Note that SQL Server Agent must be configured to use Database Mail to send e-mail and pager notifications to operators.</span></span> <span data-ttu-id="b5b27-116">Per ulteriori informazioni, vedere [Procedura: Assegnazione di avvisi a un operatore (SQL Server Management Studio)](assign-alerts-to-an-operator.md).</span><span class="sxs-lookup"><span data-stu-id="b5b27-116">For more information, see [Assign Alerts to an Operator](assign-alerts-to-an-operator.md).</span></span>  
  
-   [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="b5b27-117">è incluso un semplice strumento grafico per la gestione dei processi, che è lo strumento consigliato per la creazione e la gestione dell'infrastruttura dei processi.</span><span class="sxs-lookup"><span data-stu-id="b5b27-117">provides an easy, graphical way to manage jobs, and is the recommended way to create and manage the job infrastructure.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="b5b27-118">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="b5b27-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b5b27-119">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="b5b27-119">Permissions</span></span>  
 <span data-ttu-id="b5b27-120">Solo i membri del ruolo predefinito del server **sysadmin** possono creare gli operatori.</span><span class="sxs-lookup"><span data-stu-id="b5b27-120">Only members of the **sysadmin** fixed server role can create operators.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="b5b27-121">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b5b27-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-an-operator"></a><span data-ttu-id="b5b27-122">Per creare un operatore</span><span class="sxs-lookup"><span data-stu-id="b5b27-122">To create an operator</span></span>  
  
1.  <span data-ttu-id="b5b27-123">In **Esplora oggetti**fare clic sul segno più per espandere il server in cui si desidera creare un operatore di SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="b5b27-123">In **Object Explorer**, click the plus sign to expand the server where you want to create a SQL Server Agent operator.</span></span>  
  
2.  <span data-ttu-id="b5b27-124">Fare clic sul segno più per espandere **SQL Server Agent**.</span><span class="sxs-lookup"><span data-stu-id="b5b27-124">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="b5b27-125">Fare clic con il pulsante destro del mouse sulla cartella **Operatori** e quindi scegliere **Nuovo operatore**.</span><span class="sxs-lookup"><span data-stu-id="b5b27-125">Right-click the **Operators** folder and select **New Operator**.</span></span>  
  
     <span data-ttu-id="b5b27-126">Nella pagina **Generale** della finestra di dialogo **Nuovo operatore** sono disponibili le opzioni indicate di seguito.</span><span class="sxs-lookup"><span data-stu-id="b5b27-126">The following options are available on the **General** page of the **New Operator** dialog box:</span></span>  
  
     <span data-ttu-id="b5b27-127">**Nome**</span><span class="sxs-lookup"><span data-stu-id="b5b27-127">**Name**</span></span>  
     <span data-ttu-id="b5b27-128">Consente di modificare il nome dell'operatore.</span><span class="sxs-lookup"><span data-stu-id="b5b27-128">Change the name of the operator.</span></span>  
  
     <span data-ttu-id="b5b27-129">**Enabled**</span><span class="sxs-lookup"><span data-stu-id="b5b27-129">**Enabled**</span></span>  
     <span data-ttu-id="b5b27-130">Consente di abilitare l'operatore.</span><span class="sxs-lookup"><span data-stu-id="b5b27-130">Enable the operator.</span></span> <span data-ttu-id="b5b27-131">Se non è abilitato, all'operatore non verranno inviate notifiche.</span><span class="sxs-lookup"><span data-stu-id="b5b27-131">When not enabled, no notifications are sent to the operator.</span></span>  
  
     <span data-ttu-id="b5b27-132">**Indirizzo posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="b5b27-132">**E-mail name**</span></span>  
     <span data-ttu-id="b5b27-133">Specifica l'indirizzo di posta elettronica dell'operatore.</span><span class="sxs-lookup"><span data-stu-id="b5b27-133">Specifies the e-mail address for the operator.</span></span>  
  
     <span data-ttu-id="b5b27-134">**Indirizzo Net Send**</span><span class="sxs-lookup"><span data-stu-id="b5b27-134">**Net send address**</span></span>  
     <span data-ttu-id="b5b27-135">Specifica l'indirizzo da usare per **Net Send**.</span><span class="sxs-lookup"><span data-stu-id="b5b27-135">Specify the address to use for **net send**.</span></span>  
  
     <span data-ttu-id="b5b27-136">**Indirizzo cercapersone**</span><span class="sxs-lookup"><span data-stu-id="b5b27-136">**Pager e-mail name**</span></span>  
     <span data-ttu-id="b5b27-137">Specifica l'indirizzo di posta elettronica da utilizzare per il cercapersone dell'operatore.</span><span class="sxs-lookup"><span data-stu-id="b5b27-137">Specifies the e-mail address to use for the operator's pager.</span></span>  
  
     <span data-ttu-id="b5b27-138">**Pianificazione cercapersone per operatore in servizio**</span><span class="sxs-lookup"><span data-stu-id="b5b27-138">**Pager on duty schedule**</span></span>  
     <span data-ttu-id="b5b27-139">Consente di impostare gli orari in cui il cercapersone è attivo.</span><span class="sxs-lookup"><span data-stu-id="b5b27-139">Sets the times at which the pager is active.</span></span>  
  
     <span data-ttu-id="b5b27-140">**Lunedì - Domenica**</span><span class="sxs-lookup"><span data-stu-id="b5b27-140">**Monday - Sunday**</span></span>  
     <span data-ttu-id="b5b27-141">Consente di selezionare i giorni in cui il cercapersone è attivo.</span><span class="sxs-lookup"><span data-stu-id="b5b27-141">Select the days that the pager is active.</span></span>  
  
     <span data-ttu-id="b5b27-142">**Inizio giornata lavorativa**</span><span class="sxs-lookup"><span data-stu-id="b5b27-142">**Workday begin**</span></span>  
     <span data-ttu-id="b5b27-143">Consente di selezionare l'ora a partire da cui [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent invierà messaggi al cercapersone.</span><span class="sxs-lookup"><span data-stu-id="b5b27-143">Select the time of day after which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent sends messages to the pager.</span></span>  
  
     <span data-ttu-id="b5b27-144">**Fine giornata lavorativa**</span><span class="sxs-lookup"><span data-stu-id="b5b27-144">**Workday end**</span></span>  
     <span data-ttu-id="b5b27-145">Consente di selezionare l'ora oltre cui [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent non invierà più messaggi al cercapersone.</span><span class="sxs-lookup"><span data-stu-id="b5b27-145">Select the time of day after which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent no longer sends messages to the pager.</span></span>  
  
     <span data-ttu-id="b5b27-146">Nella pagina **Generale** della finestra di dialogo **Notifiche** sono disponibili le opzioni indicate di seguito.</span><span class="sxs-lookup"><span data-stu-id="b5b27-146">The following options are available on the **Notifications** page of the **New Operator** dialog box:</span></span>  
  
     <span data-ttu-id="b5b27-147">**Avvisi**</span><span class="sxs-lookup"><span data-stu-id="b5b27-147">**Alerts**</span></span>  
     <span data-ttu-id="b5b27-148">Consente di visualizzare gli avvisi nell'istanza.</span><span class="sxs-lookup"><span data-stu-id="b5b27-148">View the alerts in the instance.</span></span>  
  
     <span data-ttu-id="b5b27-149">**Processi**</span><span class="sxs-lookup"><span data-stu-id="b5b27-149">**Jobs**</span></span>  
     <span data-ttu-id="b5b27-150">Consente di visualizzare i processi nell'istanza.</span><span class="sxs-lookup"><span data-stu-id="b5b27-150">View the jobs in the instance.</span></span>  
  
     <span data-ttu-id="b5b27-151">**Elenco avvisi**</span><span class="sxs-lookup"><span data-stu-id="b5b27-151">**Alert list**</span></span>  
     <span data-ttu-id="b5b27-152">Consente di visualizzare l'elenco degli avvisi nell'istanza.</span><span class="sxs-lookup"><span data-stu-id="b5b27-152">Lists the alerts in the instance.</span></span>  
  
     <span data-ttu-id="b5b27-153">**Elenco processi**</span><span class="sxs-lookup"><span data-stu-id="b5b27-153">**Job list**</span></span>  
     <span data-ttu-id="b5b27-154">Consente di visualizzare l'elenco dei processi nell'istanza.</span><span class="sxs-lookup"><span data-stu-id="b5b27-154">Lists the jobs in the instance.</span></span>  
  
     <span data-ttu-id="b5b27-155">**Posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="b5b27-155">**E-mail**</span></span>  
     <span data-ttu-id="b5b27-156">Consente di inviare una notifica all'operatore tramite posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="b5b27-156">Notify this operator using e-mail.</span></span>  
  
     <span data-ttu-id="b5b27-157">**Cercapersone**</span><span class="sxs-lookup"><span data-stu-id="b5b27-157">**Pager**</span></span>  
     <span data-ttu-id="b5b27-158">Inviare una notifica all'operatore tramite un messaggio di posta elettronica all'indirizzo del cercapersone.</span><span class="sxs-lookup"><span data-stu-id="b5b27-158">Notify this operator by sending e-mail to the pager address.</span></span>  
  
     <span data-ttu-id="b5b27-159">**NET SEND**</span><span class="sxs-lookup"><span data-stu-id="b5b27-159">**Net send**</span></span>  
     <span data-ttu-id="b5b27-160">Notificare questo operatore tramite **Net Send**.</span><span class="sxs-lookup"><span data-stu-id="b5b27-160">Notify this operator using **net send**.</span></span>  
  
4.  <span data-ttu-id="b5b27-161">Al termine della creazione del nuovo operatore, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b5b27-161">When finished creating the new operator, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="b5b27-162">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b5b27-162">Using Transact-SQL</span></span>  
  
#### <a name="to-create-an-operator"></a><span data-ttu-id="b5b27-163">Per creare un operatore</span><span class="sxs-lookup"><span data-stu-id="b5b27-163">To create an operator</span></span>  
  
1.  <span data-ttu-id="b5b27-164">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b5b27-164">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="b5b27-165">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="b5b27-165">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="b5b27-166">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="b5b27-166">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- sets up the operator information for user 'danwi.' The operator is enabled.   
    -- SQL Server Agent sends notifications by pager from Monday through Friday from 8 A.M. to 5 P.M.  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_add_operator  
        @name = N'Dan Wilson',  
        @enabled = 1,  
        @email_address = N'danwi',  
        @pager_address = N'5551290AW@pager.Adventure-Works.com',  
        @weekday_pager_start_time = 080000,  
        @weekday_pager_end_time = 170000,  
        @pager_days = 62 ;  
    GO  
    ```  
  
 <span data-ttu-id="b5b27-167">Per ulteriori informazioni, vedere [sp_add_operator &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-add-operator-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b5b27-167">For more information, see [sp_add_operator &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-operator-transact-sql).</span></span>  
  
  
