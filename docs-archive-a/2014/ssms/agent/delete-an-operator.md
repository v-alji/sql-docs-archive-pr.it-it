---
title: Eliminare un operatore | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, operators
- canceling operators
- removing operators
- deleting operators
- dropping operators
- jobs [SQL Server Agent], operators
- operators (users) [Database Engine], deleting with Management Studio
ms.assetid: 2b7b8627-082d-4189-8584-abd3a9b604cf
author: stevestein
ms.author: sstein
ms.openlocfilehash: 75bea1c5c5fabff7ce55fe07a5181baa8f99e0fe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624519"
---
# <a name="delete-an-operator"></a><span data-ttu-id="3aa14-102">Delete an Operator</span><span class="sxs-lookup"><span data-stu-id="3aa14-102">Delete an Operator</span></span>
  <span data-ttu-id="3aa14-103">In questo argomento viene descritto come rimuovere un operatore in modo che non riceva più [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] notifiche di avviso di Agent in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3aa14-103">This topic describes how to remove an operator so they no longer receive [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alert notifications in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="3aa14-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="3aa14-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="3aa14-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="3aa14-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="3aa14-106">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="3aa14-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="3aa14-107">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="3aa14-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="3aa14-108">**Per eliminare un operatore tramite:**</span><span class="sxs-lookup"><span data-stu-id="3aa14-108">**To delete an operator, using:**</span></span>  
  
     [<span data-ttu-id="3aa14-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3aa14-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="3aa14-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3aa14-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="3aa14-111">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="3aa14-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="3aa14-112">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="3aa14-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="3aa14-113">Quando si rimuove un operatore, vengono rimosse tutte le notifiche associate.</span><span class="sxs-lookup"><span data-stu-id="3aa14-113">When an operator is removed, all the notifications associated with the operator are also removed.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="3aa14-114">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="3aa14-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="3aa14-115">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="3aa14-115">Permissions</span></span>  
 <span data-ttu-id="3aa14-116">I membri del ruolo predefinito del server **sysadmin** possono eliminare gli operatori.</span><span class="sxs-lookup"><span data-stu-id="3aa14-116">Members of the **sysadmin** fixed server role can delete operators.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="3aa14-117">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3aa14-117">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-an-operator"></a><span data-ttu-id="3aa14-118">Per eliminare un operatore</span><span class="sxs-lookup"><span data-stu-id="3aa14-118">To delete an operator</span></span>  
  
1.  <span data-ttu-id="3aa14-119">In **Esplora oggetti**fare clic sul segno più per espandere il server che contiene l'operatore da eliminare.</span><span class="sxs-lookup"><span data-stu-id="3aa14-119">In **Object Explorer**, click the plus sign to expand the server that contains the operator you want to delete.</span></span>  
  
2.  <span data-ttu-id="3aa14-120">Fare clic sul segno più per espandere **SQL Server Agent**.</span><span class="sxs-lookup"><span data-stu-id="3aa14-120">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="3aa14-121">Fare clic sul segno più per espandere la cartella **Operatori** .</span><span class="sxs-lookup"><span data-stu-id="3aa14-121">Click the plus sign to expand the **Operators** folder.</span></span>  
  
4.  <span data-ttu-id="3aa14-122">Fare clic con il pulsante destro del mouse sull'operatore da eliminare e scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="3aa14-122">Right-click the operator that you want to delete and select **Delete**.</span></span>  
  
5.  <span data-ttu-id="3aa14-123">Nella finestra di dialogo **Elimina oggetto** verificare che venga selezionato l'operatore corretto, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="3aa14-123">In the **Delete Object** dialog box, make sure that the correct operator is selected, and then click **OK**.</span></span> <span data-ttu-id="3aa14-124">Per fare in modo che gli avvisi e i processi inviati all'operatore eliminato vengano ricevuti da un altro operatore, selezionare l'opzione **Riassegna a** e scegliere un operatore nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="3aa14-124">If you want another operator to receive the alerts and jobs sent to the deleted operator, check **Reassign to** and select an operator in the list.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="3aa14-125">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3aa14-125">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-an-operator"></a><span data-ttu-id="3aa14-126">Per eliminare un operatore</span><span class="sxs-lookup"><span data-stu-id="3aa14-126">To delete an operator</span></span>  
  
1.  <span data-ttu-id="3aa14-127">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3aa14-127">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="3aa14-128">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="3aa14-128">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="3aa14-129">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="3aa14-129">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- deletes operator 'Test Operator' and reassigns all alerts and jobs sent to that operator to 'Fran??ois Ajenstat'  
    USE msdb ;  
    GO  
  
    EXEC sp_delete_operator @name = 'Test Operator',  
        @reassign_to_operator = 'Fran??ois Ajenstat';  
    GO  
    ```  
  
 <span data-ttu-id="3aa14-130">Per ulteriori informazioni, vedere [sp_delete_operator &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-delete-operator-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="3aa14-130">For more information, see [sp_delete_operator &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-operator-transact-sql).</span></span>  
  
  
