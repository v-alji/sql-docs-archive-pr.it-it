---
title: Gestire categorie di criteri | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.dmf.policycategories.f1
ms.assetid: d188a819-731f-4029-98aa-780d3299a0ce
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 168d05dd88286263da1dca5456a2c6072e946786
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626709"
---
# <a name="manage-policy-categories"></a><span data-ttu-id="a8a3f-102">Gestione categorie di criteri</span><span class="sxs-lookup"><span data-stu-id="a8a3f-102">Manage Policy Categories</span></span>
  <span data-ttu-id="a8a3f-103">In questo argomento viene descritto come applicare uno o tutti i criteri disponibili in una categoria all'istanza intera di [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a8a3f-103">This topic describes how to apply any or all available policies in a category to the whole instance of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="a8a3f-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="a8a3f-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="a8a3f-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="a8a3f-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="a8a3f-106">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="a8a3f-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="a8a3f-107">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="a8a3f-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="a8a3f-108">**Per applicare i criteri di categoria a un'istanza di SQL Server utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="a8a3f-108">**To apply category policies to a SQL Server instance, using:**</span></span>  
  
     [<span data-ttu-id="a8a3f-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a8a3f-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="a8a3f-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a8a3f-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="a8a3f-111">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="a8a3f-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="a8a3f-112">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="a8a3f-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="a8a3f-113">Quando si utilizza [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], se la casella di controllo **Imponi sottoscrizioni di database** non è selezionata, la categoria di criteri deve essere applicata singolarmente a ogni parte appropriata del server, ad esempio uno o più database o tabelle.</span><span class="sxs-lookup"><span data-stu-id="a8a3f-113">When using [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], if the **Mandate Database Subscriptions** check box is not selected, the policy category must be individually applied to each relevant portion of the server, such as one or more databases or tables.</span></span>  
  
-   <span data-ttu-id="a8a3f-114">Se si specifica una categoria di criteri non esistente, verrà creata una nuova categoria di criteri e la sottoscrizione sarà obbligatoria per tutti i database all'esecuzione della stored procedure.</span><span class="sxs-lookup"><span data-stu-id="a8a3f-114">If you specify a policy category that does not exist, a new policy category is created and the subscription is mandated for all databases when you execute the stored procedure.</span></span> <span data-ttu-id="a8a3f-115">Se la sottoscrizione obbligatoria per la nuova categoria viene successivamente cancellata, la sottoscrizione sarà valida solo per il database specificato come *target_object*.</span><span class="sxs-lookup"><span data-stu-id="a8a3f-115">If you then clear the mandated subscription for the new category, the subscription will only apply for the database that you specified as the *target_object*.</span></span> <span data-ttu-id="a8a3f-116">Per altre informazioni sulla modifica dell'impostazione di una sottoscrizione obbligatoria, vedere [sp_syspolicy_update_policy_category &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-syspolicy-update-policy-category-subscription-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a8a3f-116">For more information about how to change a mandated subscription setting, see [sp_syspolicy_update_policy_category &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-syspolicy-update-policy-category-subscription-transact-sql).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="a8a3f-117">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="a8a3f-117">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="a8a3f-118">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="a8a3f-118">Permissions</span></span>  
 <span data-ttu-id="a8a3f-119">Questa stored procedure viene eseguita nel contesto del proprietario corrente della stessa.</span><span class="sxs-lookup"><span data-stu-id="a8a3f-119">This stored procedure runs in the context of the current owner of the stored procedure.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="a8a3f-120">Con SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a8a3f-120">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-apply-category-policies-to-a-sql-server-instance"></a><span data-ttu-id="a8a3f-121">Per applicare i criteri di categoria a un'istanza di SQL Server</span><span class="sxs-lookup"><span data-stu-id="a8a3f-121">To apply category policies to a SQL Server instance</span></span>  
  
1.  <span data-ttu-id="a8a3f-122">In **Esplora oggetti**fare clic sul segno più per espandere il server in cui si desidera applicare i criteri di categoria.</span><span class="sxs-lookup"><span data-stu-id="a8a3f-122">In **Object Explorer**, click the plus sign to expand the server where you will apply category policies.</span></span>  
  
2.  <span data-ttu-id="a8a3f-123">Fare clic sul segno più per espandere la cartella **Gestione** .</span><span class="sxs-lookup"><span data-stu-id="a8a3f-123">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="a8a3f-124">Fare clic con il pulsante destro del mouse su **Gestione criteri** e selezionare **Gestione categorie**.</span><span class="sxs-lookup"><span data-stu-id="a8a3f-124">Right-click **Policy Management** and select **Manage Categories**.</span></span>  
  
     <span data-ttu-id="a8a3f-125">Le informazioni seguenti sono disponibili nella finestra di dialogo **Gestione categorie di criteri** :</span><span class="sxs-lookup"><span data-stu-id="a8a3f-125">The following information is available in the **Manage Policy Categories** dialog box:</span></span>  
  
     <span data-ttu-id="a8a3f-126">**Nome**</span><span class="sxs-lookup"><span data-stu-id="a8a3f-126">**Name**</span></span>  
     <span data-ttu-id="a8a3f-127">Nome della categoria di criteri.</span><span class="sxs-lookup"><span data-stu-id="a8a3f-127">The name of the policy category.</span></span>  
  
     <span data-ttu-id="a8a3f-128">**Imponi sottoscrizioni di database**</span><span class="sxs-lookup"><span data-stu-id="a8a3f-128">**Mandate Database Subscriptions**</span></span>  
     <span data-ttu-id="a8a3f-129">Impone a tutti i database presenti nell'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] di applicare i criteri contenuti nella categoria.</span><span class="sxs-lookup"><span data-stu-id="a8a3f-129">Forces all databases on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to enforce policies in the policy category.</span></span>  
  
4.  <span data-ttu-id="a8a3f-130">Selezionare o deselezionare una o tutte le caselle di controllo in **Imponi sottoscrizioni di database** per applicare la categoria di criteri all'istanza di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a8a3f-130">Select or clear any or all check boxes under **Mandate Database Subscriptions** to apply that policy category to the SQL Server instance.</span></span>  
  
5.  <span data-ttu-id="a8a3f-131">Al termine, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="a8a3f-131">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="a8a3f-132">Con Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a8a3f-132">Using Transact-SQL</span></span>  
  
#### <a name="to-apply-category-policies-to-a-sql-server-instance"></a><span data-ttu-id="a8a3f-133">Per applicare i criteri di categoria a un'istanza di SQL Server</span><span class="sxs-lookup"><span data-stu-id="a8a3f-133">To apply category policies to a SQL Server instance</span></span>  
  
1.  <span data-ttu-id="a8a3f-134">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a8a3f-134">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="a8a3f-135">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="a8a3f-135">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="a8a3f-136">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="a8a3f-136">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE msdb;  
    GO  
    -- configures the specified database to subscribe to a policy category that is named 'Table Naming Policies'.  
    EXEC dbo.sp_syspolicy_add_policy_category_subscription @target_type = N'DATABASE'  
    , @target_object = N'AdventureWorks2012'  
    , @policy_category = N'Table Naming Policies';  
    GO  
    ```  
  
 <span data-ttu-id="a8a3f-137">Per altre informazioni, vedere [sp_syspolicy_add_policy_category_subscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-syspolicy-add-policy-category-subscription-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a8a3f-137">For more information, see [sp_syspolicy_add_policy_category_subscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-syspolicy-add-policy-category-subscription-transact-sql).</span></span>  
  
  
