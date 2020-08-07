---
title: Disabilitare o riattivare un avviso | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, alerts
- alerts [SQL Server], reactivating
- deleting alerts
- canceling alerts
- dropping alerts
- disabling alerts
- alerts [SQL Server], disabling
- reactivating alerts
- removing alerts
ms.assetid: 4cb37dc6-1134-405d-8590-58b44dcf63b2
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3eec4ea7288f4847c0e9b861d80f23eb9c9ddba8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719421"
---
# <a name="disable-or-reactivate-an-alert"></a><span data-ttu-id="29171-102">Disabilitazione o riattivazione di un avviso</span><span class="sxs-lookup"><span data-stu-id="29171-102">Disable or Reactivate an Alert</span></span>
  <span data-ttu-id="29171-103">In questo argomento viene descritto come disabilitare o riattivare un [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] avviso [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] di Agent in tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="29171-103">This topic describes how to disable or reactivate a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alert in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="29171-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="29171-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="29171-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="29171-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="29171-106">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="29171-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="29171-107">**Per disabilitare o riattivare un avviso utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="29171-107">**To disable or reactivate an alert, using:**</span></span>  
  
     [<span data-ttu-id="29171-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="29171-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="29171-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="29171-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="29171-110">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="29171-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="29171-111">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="29171-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="29171-112">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="29171-112">Permissions</span></span>  
 <span data-ttu-id="29171-113">Per impostazione predefinita, i membri del ruolo predefinito del server **sysadmin** possono modificare le informazioni nell'avviso.</span><span class="sxs-lookup"><span data-stu-id="29171-113">By default, members of the **sysadmin** fixed server role can edit information in an alert.</span></span> <span data-ttu-id="29171-114">Gli altri utenti devono appartenere al ruolo predefinito del database **SQLAgentOperatorRole** nel database **msdb** .</span><span class="sxs-lookup"><span data-stu-id="29171-114">Other users must be granted the **SQLAgentOperatorRole** fixed database role in the **msdb** database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="29171-115">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="29171-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-disable-or-reactivate-an-alert"></a><span data-ttu-id="29171-116">Per disabilitare o riattivare un avviso</span><span class="sxs-lookup"><span data-stu-id="29171-116">To disable or reactivate an alert</span></span>  
  
1.  <span data-ttu-id="29171-117">In **Esplora oggetti**fare clic sul segno più per espandere il server che contiene l'avviso da disabilitare o riattivare.</span><span class="sxs-lookup"><span data-stu-id="29171-117">In **Object Explorer**, click the plus sign to expand server that contains the alert you wish to disable or reactivate.</span></span>  
  
2.  <span data-ttu-id="29171-118">Fare clic sul segno più per espandere **SQL Server Agent**.</span><span class="sxs-lookup"><span data-stu-id="29171-118">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="29171-119">Fare clic sul segno più per espandere la cartella **Avvisi** .</span><span class="sxs-lookup"><span data-stu-id="29171-119">Click the plus sign to expand the **Alerts** folder.</span></span>  
  
4.  <span data-ttu-id="29171-120">Fare clic con il pulsante destro del mouse sull'avviso da abilitare e selezionare **Abilita** . Per disabilitare un avviso, fare clic con il pulsante destro del mouse sull'avviso da disabilitare e selezionare **Disabilita**.</span><span class="sxs-lookup"><span data-stu-id="29171-120">Right-click the alert you wish to enable and select **Enable** To disable an alert, right-click the alert you want to disable and select **Disable**.</span></span>  
  
5.  <span data-ttu-id="29171-121">Verrà visualizzata la finestra di dialogo **Disabilita avviso** o **Abilita avviso** indicante lo stato del processo.</span><span class="sxs-lookup"><span data-stu-id="29171-121">The **Disable Alert** or **Enable Alert** dialog box displays showing the status of the process.</span></span> <span data-ttu-id="29171-122">Al termine, fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="29171-122">When finished, click **Close**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="29171-123">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="29171-123">Using Transact-SQL</span></span>  
  
#### <a name="to-disable-or-reactivate-an-alert"></a><span data-ttu-id="29171-124">Per disabilitare o riattivare un avviso</span><span class="sxs-lookup"><span data-stu-id="29171-124">To disable or reactivate an alert</span></span>  
  
1.  <span data-ttu-id="29171-125">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="29171-125">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="29171-126">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="29171-126">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="29171-127">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="29171-127">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- changes the enabled setting of Test Alert to 0  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_update_alert  
        @name = N'Test Alert',  
        @enabled = 0 ;  
    GO  
    ```  
  
 <span data-ttu-id="29171-128">Per ulteriori informazioni, vedere [sp_update_alert &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-update-alert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="29171-128">For more information, see [sp_update_alert &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-alert-transact-sql).</span></span>  
  
  
