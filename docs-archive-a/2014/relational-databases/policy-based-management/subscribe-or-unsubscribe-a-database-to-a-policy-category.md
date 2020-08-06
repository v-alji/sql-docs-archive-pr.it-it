---
title: Sottoscrivere una categoria di criteri o annullarne la sottoscrizione per un database | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.dmf.groupsubscription.f1
ms.assetid: d2c31769-7098-428e-ad9c-ef56541b7c52
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2b4ca6f804352b57b30b42012da93e0d031be8d4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715191"
---
# <a name="subscribe-or-unsubscribe-a-database--to-a-policy-category"></a><span data-ttu-id="83630-102">Sottoscrivere una categoria di criteri o annullarne la sottoscrizione per un database</span><span class="sxs-lookup"><span data-stu-id="83630-102">Subscribe or Unsubscribe a Database  to a Policy Category</span></span>
  <span data-ttu-id="83630-103">In questo argomento verrà descritto come sottoscrivere una categoria di criteri o annullarne la sottoscrizione per un database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="83630-103">This topic describes how to subscribe or unsubscribe a database to a policy category.in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="83630-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="83630-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="83630-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="83630-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="83630-106">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="83630-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="83630-107">**Per sottoscrivere una categoria di criteri o annullarne la sottoscrizione per un database utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="83630-107">**To subscribe or unsubscribe a database to a policy category., using:**</span></span>  
  
     [<span data-ttu-id="83630-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="83630-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="83630-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="83630-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="83630-110">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="83630-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="83630-111">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="83630-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="83630-112">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="83630-112">Permissions</span></span>  
 <span data-ttu-id="83630-113">Richiede l'appartenenza al ruolo predefinito del database db_owner.</span><span class="sxs-lookup"><span data-stu-id="83630-113">Requires membership in the db_owner fixed database role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="83630-114">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="83630-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-subscribe-or-unsubscribe-a-database-to-a-policy-category"></a><span data-ttu-id="83630-115">Per sottoscrivere una categoria di criteri o annullarne la sottoscrizione per un database</span><span class="sxs-lookup"><span data-stu-id="83630-115">To subscribe or unsubscribe a database to a policy category</span></span>  
  
1.  <span data-ttu-id="83630-116">In **Esplora oggetti**fare clic sul segno più per espandere il server contenente il database in cui si desidera gestire le sottoscrizioni di categorie.</span><span class="sxs-lookup"><span data-stu-id="83630-116">In **Object Explorer**, click the plus sign to expand the server that contains the database wherein you want to manage category subscriptions.</span></span>  
  
2.  <span data-ttu-id="83630-117">Fare clic sul segno più per espandere la cartella **Database** .</span><span class="sxs-lookup"><span data-stu-id="83630-117">Click the plus sign to expand the **Databases** folder.</span></span>  
  
3.  <span data-ttu-id="83630-118">Fare clic con il pulsante destro del mouse sul database dove si desidera gestire sottoscrizioni di categorie, scegliere **Criteri**e selezionare **Categorie**.</span><span class="sxs-lookup"><span data-stu-id="83630-118">Right-click the database wherein you want to manage category subscriptions, point to **Policies**, and select **Categories**</span></span>  
  
     <span data-ttu-id="83630-119">Nella finestra di dialogo **Categorie** sono disponibili le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="83630-119">The following options are available in the **Categories** dialog box:</span></span>  
  
     <span data-ttu-id="83630-120">Colonna Espandi</span><span class="sxs-lookup"><span data-stu-id="83630-120">Expand column</span></span>  
     <span data-ttu-id="83630-121">Fare clic su questa opzione per espandere una categoria di criteri.</span><span class="sxs-lookup"><span data-stu-id="83630-121">Click to expand a policy category.</span></span> <span data-ttu-id="83630-122">Verranno elencati tutti i criteri inclusi nella categoria.</span><span class="sxs-lookup"><span data-stu-id="83630-122">This lists all the policies that are included in the category.</span></span>  
  
     <span data-ttu-id="83630-123">**Nome**</span><span class="sxs-lookup"><span data-stu-id="83630-123">**Name**</span></span>  
     <span data-ttu-id="83630-124">Nome della categoria di criteri.</span><span class="sxs-lookup"><span data-stu-id="83630-124">The name of the policy category.</span></span>  
  
     <span data-ttu-id="83630-125">**Sottoscritto**</span><span class="sxs-lookup"><span data-stu-id="83630-125">**Subscribed**</span></span>  
     <span data-ttu-id="83630-126">Indica se la destinazione ha sottoscritto la categoria di criteri.</span><span class="sxs-lookup"><span data-stu-id="83630-126">Indicates whether the target has subscribed to the policy category.</span></span> <span data-ttu-id="83630-127">Se questa casella di controllo è disabilitata, la categoria di criteri è impostata su **Imponi sottoscrizioni di database**,</span><span class="sxs-lookup"><span data-stu-id="83630-127">If this check box is disabled, the policy category is set for **Mandate Database Subscriptions**.</span></span> <span data-ttu-id="83630-128">ovvero la categoria di criteri si applica a tutti i database nel server.</span><span class="sxs-lookup"><span data-stu-id="83630-128">This means that the policy category applies to all databases on the server.</span></span>  
  
     <span data-ttu-id="83630-129">**Criteri**</span><span class="sxs-lookup"><span data-stu-id="83630-129">**Policy**</span></span>  
     <span data-ttu-id="83630-130">Quando i gruppi di criteri sono espansi, vengono visualizzati i criteri inclusi nella categoria di criteri.</span><span class="sxs-lookup"><span data-stu-id="83630-130">When policy groups are expanded, displays the policies in the policy category.</span></span>  
  
     <span data-ttu-id="83630-131">**Enabled**</span><span class="sxs-lookup"><span data-stu-id="83630-131">**Enabled**</span></span>  
     <span data-ttu-id="83630-132">Indica se i criteri sono abilitati o disabilitati.</span><span class="sxs-lookup"><span data-stu-id="83630-132">Indicates whether the policies are enabled or disabled.</span></span>  
  
     <span data-ttu-id="83630-133">**Modalità di esecuzione**</span><span class="sxs-lookup"><span data-stu-id="83630-133">**Execution Mode**</span></span>  
     <span data-ttu-id="83630-134">Visualizza la modalità di esecuzione dei criteri.</span><span class="sxs-lookup"><span data-stu-id="83630-134">Displays the execution mode of the policy.</span></span>  
  
     <span data-ttu-id="83630-135">**History**</span><span class="sxs-lookup"><span data-stu-id="83630-135">**History**</span></span>  
     <span data-ttu-id="83630-136">Fare clic sul collegamento ipertestuale Visualizza cronologia per aprire il Visualizzatore file di log ed esaminare la cronologia dei criteri.</span><span class="sxs-lookup"><span data-stu-id="83630-136">Click the View History hyperlink to open the Log File Viewer to see the policy history.</span></span>  
  
4.  <span data-ttu-id="83630-137">Per sottoscrivere una categoria Gestione basata su criteri, selezionare la casella di controllo della categoria nella colonna **Sottoscritto** .</span><span class="sxs-lookup"><span data-stu-id="83630-137">To subscribe to a Policy-Based Management category, select the category's check box under the **Subscribed** column.</span></span> <span data-ttu-id="83630-138">Per annullare la sottoscrizione da una categoria, deselezionare la casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="83630-138">To unsubscribe from a category, clear the check box.</span></span>  
  
5.  <span data-ttu-id="83630-139">Al termine, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="83630-139">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="83630-140">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="83630-140">Using Transact-SQL</span></span>  
  
#### <a name="to-subscribe-a-database-to-a-policy-category"></a><span data-ttu-id="83630-141">Per sottoscrivere una categoria di criteri per un database</span><span class="sxs-lookup"><span data-stu-id="83630-141">To subscribe a database to a policy category</span></span>  
  
1.  <span data-ttu-id="83630-142">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="83630-142">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="83630-143">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="83630-143">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="83630-144">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="83630-144">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    -- Adds a subscription to the 'Finance' policy category for the AdventureWorks2012 database.  
    EXEC sys.sp_syspolicy_subscribe_to_policy_category @policy_category = N'Finance';  
    GO  
    ```  
  
 <span data-ttu-id="83630-145">Per altre informazioni, vedere [sp_syspolicy_subscribe_to_policy_category &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-syspolicy-subscribe-to-policy-category-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="83630-145">For more information, see [sp_syspolicy_subscribe_to_policy_category &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-syspolicy-subscribe-to-policy-category-transact-sql).</span></span>  
  
#### <a name="to-unsubscribe-a-database-to-a-policy-category"></a><span data-ttu-id="83630-146">Per annullare la sottoscrizione di una categoria di criteri per un database</span><span class="sxs-lookup"><span data-stu-id="83630-146">To unsubscribe a database to a policy category</span></span>  
  
1.  <span data-ttu-id="83630-147">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="83630-147">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="83630-148">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="83630-148">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="83630-149">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="83630-149">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    -- Deletes a subscription to the 'Finance' policy category for the AdventureWorks2012 database.  
    EXEC sys.sp_syspolicy_unsubscribe_from_policy_category @policy_category = N'Finance';  
    GO  
    ```  
  
 <span data-ttu-id="83630-150">Per altre informazioni, vedere [sp_syspolicy_unsubscribe_from_policy_category &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-syspolicy-unsubscribe-from-policy-category-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="83630-150">For more information, see [sp_syspolicy_unsubscribe_from_policy_category &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-syspolicy-unsubscribe-from-policy-category-transact-sql).</span></span>  
  
  
