---
title: Modificare un avviso | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, alerts
- alerts [SQL Server], modifying
- modifying alerts
ms.assetid: f518e528-cc8f-446a-b37d-98505b86e430
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1eae606b3c2ca4c18d088e650e774986d4e31387
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629701"
---
# <a name="edit-an-alert"></a><span data-ttu-id="83364-102">Edit an Alert</span><span class="sxs-lookup"><span data-stu-id="83364-102">Edit an Alert</span></span>
  <span data-ttu-id="83364-103">In questo argomento viene descritto come modificare un [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] avviso di Agent in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="83364-103">This topic describes how to edit a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alert in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="83364-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="83364-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="83364-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="83364-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="83364-106">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="83364-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="83364-107">**Per modificare un avviso utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="83364-107">**To edit an alert, using:**</span></span>  
  
     [<span data-ttu-id="83364-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="83364-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="83364-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="83364-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="83364-110">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="83364-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="83364-111">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="83364-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="83364-112">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="83364-112">Permissions</span></span>  
 <span data-ttu-id="83364-113">Per impostazione predefinita, i membri del ruolo predefinito del server **sysadmin** possono modificare le informazioni nell'avviso.</span><span class="sxs-lookup"><span data-stu-id="83364-113">By default, members of the **sysadmin** fixed server role can edit information in an alert.</span></span> <span data-ttu-id="83364-114">Gli altri utenti devono appartenere al ruolo predefinito del database **SQLAgentOperatorRole** nel database **msdb** .</span><span class="sxs-lookup"><span data-stu-id="83364-114">Other users must be granted the **SQLAgentOperatorRole** fixed database role in the **msdb** database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="83364-115">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="83364-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-edit-an-alert"></a><span data-ttu-id="83364-116">Per modificare un avviso</span><span class="sxs-lookup"><span data-stu-id="83364-116">To edit an alert</span></span>  
  
1.  <span data-ttu-id="83364-117">In **Esplora oggetti** fare clic sul segno più per espandere il server che contiene l'avviso da modificare.</span><span class="sxs-lookup"><span data-stu-id="83364-117">In **Object Explorer,** click the plus sign to expand the server containing the alert you want to edit.</span></span>  
  
2.  <span data-ttu-id="83364-118">Fare clic sul segno più per espandere **SQL Server Agent**.</span><span class="sxs-lookup"><span data-stu-id="83364-118">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="83364-119">Fare clic sul segno più per espandere la cartella **Avvisi** .</span><span class="sxs-lookup"><span data-stu-id="83364-119">Click the plus sign to expand the **Alerts** folder.</span></span>  
  
4.  <span data-ttu-id="83364-120">Fare clic con il pulsante destro del mouse sull'avviso da modificare e selezionare **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="83364-120">Right-click the alert you want to edit and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="83364-121">Aggiornare le proprietà dell'avviso nelle pagine **Generale**, **Risposta**e **Opzioni** .</span><span class="sxs-lookup"><span data-stu-id="83364-121">Update the alert properties on the **General**, **Response**, and **Options** pages.</span></span>  
  
6.  <span data-ttu-id="83364-122">Al termine, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="83364-122">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="83364-123">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="83364-123">Using Transact-SQL</span></span>  
  
#### <a name="to-edit-an-alert"></a><span data-ttu-id="83364-124">Per modificare un avviso</span><span class="sxs-lookup"><span data-stu-id="83364-124">To edit an alert</span></span>  
  
1.  <span data-ttu-id="83364-125">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="83364-125">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="83364-126">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="83364-126">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="83364-127">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="83364-127">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- changes the enabled setting of Test Alert to 0  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_update_alert  
        @name = N'Test Alert',  
        @enabled = 0 ;  
    GO  
    ```  
  
 <span data-ttu-id="83364-128">Per ulteriori informazioni, vedere [sp_update_alert &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-update-alert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="83364-128">For more information, see [sp_update_alert &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-alert-transact-sql).</span></span>  
  
  
