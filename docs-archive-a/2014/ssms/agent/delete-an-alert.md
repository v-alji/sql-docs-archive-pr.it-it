---
title: Eliminare un avviso | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, alerts
- alerts [SQL Server], deleting
- deleting alerts
- canceling alerts
- dropping alerts
- disabling alerts
- removing alerts
ms.assetid: c982b208-e2d1-4d34-8cee-940b9baf6586
author: stevestein
ms.author: sstein
ms.openlocfilehash: 15fdae19b150a5a06a32e91ec1947a0acfa5f900
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635319"
---
# <a name="delete-an-alert"></a><span data-ttu-id="4e4eb-102">Delete an Alert</span><span class="sxs-lookup"><span data-stu-id="4e4eb-102">Delete an Alert</span></span>
  <span data-ttu-id="4e4eb-103">In questo argomento viene descritto come eliminare gli [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] avvisi [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] di Agent in tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4e4eb-103">This topic describes how to delete [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alerts in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="4e4eb-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="4e4eb-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="4e4eb-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="4e4eb-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="4e4eb-106">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="4e4eb-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="4e4eb-107">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="4e4eb-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="4e4eb-108">**Per eliminare un avviso tramite:**</span><span class="sxs-lookup"><span data-stu-id="4e4eb-108">**To delete an alert, using:**</span></span>  
  
     [<span data-ttu-id="4e4eb-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4e4eb-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="4e4eb-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4e4eb-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="4e4eb-111">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="4e4eb-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="4e4eb-112">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="4e4eb-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="4e4eb-113">Quando si rimuove un avviso, vengono rimosse anche le notifiche associate.</span><span class="sxs-lookup"><span data-stu-id="4e4eb-113">Removing an alert also removes any notifications associated with the alert.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="4e4eb-114">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="4e4eb-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="4e4eb-115">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="4e4eb-115">Permissions</span></span>  
 <span data-ttu-id="4e4eb-116">Per impostazione predefinita, solo i membri del ruolo predefinito del server **sysadmin** possono eliminare gli avvisi.</span><span class="sxs-lookup"><span data-stu-id="4e4eb-116">By default, only members of the **sysadmin** fixed server role can delete alerts.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="4e4eb-117">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4e4eb-117">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-an-alert"></a><span data-ttu-id="4e4eb-118">Per eliminare un avviso</span><span class="sxs-lookup"><span data-stu-id="4e4eb-118">To delete an alert</span></span>  
  
1.  <span data-ttu-id="4e4eb-119">In **Esplora oggetti** fare clic sul segno più per espandere il server che contiene l'avviso di SQL Server Agent da eliminare.</span><span class="sxs-lookup"><span data-stu-id="4e4eb-119">In **Object Explorer,** click the plus sign to expand the server that contains the SQL Server Agent alert that you want to delete.</span></span>  
  
2.  <span data-ttu-id="4e4eb-120">Fare clic sul segno più per espandere **SQL Server Agent**.</span><span class="sxs-lookup"><span data-stu-id="4e4eb-120">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="4e4eb-121">Fare clic sul segno più per espandere la cartella **Avvisi** .</span><span class="sxs-lookup"><span data-stu-id="4e4eb-121">Click the plus sign to expand the **Alerts** folder.</span></span>  
  
4.  <span data-ttu-id="4e4eb-122">Fare clic con il pulsante destro del mouse sull'avviso da eliminare e scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="4e4eb-122">Right-click the alert you want to delete and select **Delete**.</span></span>  
  
5.  <span data-ttu-id="4e4eb-123">Nella finestra di dialogo **Elimina oggetto** verificare che sia selezionato l'avviso corretto, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="4e4eb-123">In the **Delete Object** dialog box, confirm that the correct alert is selected and click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="4e4eb-124">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4e4eb-124">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-an-alert"></a><span data-ttu-id="4e4eb-125">Per eliminare un avviso</span><span class="sxs-lookup"><span data-stu-id="4e4eb-125">To delete an alert</span></span>  
  
1.  <span data-ttu-id="4e4eb-126">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4e4eb-126">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="4e4eb-127">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="4e4eb-127">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="4e4eb-128">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="4e4eb-128">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- deletes the SQL Server Agent alert called 'Test Alert.'  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_delete_alert  
       @name = N'Test Alert' ;  
    GO  
    ```  
  
 <span data-ttu-id="4e4eb-129">Per ulteriori informazioni, vedere s[sp_delete_alert &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-delete-alert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4e4eb-129">For more information, see s[sp_delete_alert &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-alert-transact-sql).</span></span>  
  
  
