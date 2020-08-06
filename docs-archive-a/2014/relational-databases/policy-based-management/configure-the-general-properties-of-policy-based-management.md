---
title: Configurare le proprietà generali della gestione basata su criteri | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.dmf.PolicyManagement.f1
helpviewer_keywords:
- Policy-Based Management, configure properties
ms.assetid: 6d1e0e37-29ea-408a-a055-384984d884be
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: a2efb37fafa29bcb043dedbcfa8719d0092b1c77
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715203"
---
# <a name="configure-the-general-properties-of-policy-based-management"></a><span data-ttu-id="63ba8-102">Configurare le proprietà generali della gestione basata su criteri</span><span class="sxs-lookup"><span data-stu-id="63ba8-102">Configure the General Properties of Policy-Based Management</span></span>
  <span data-ttu-id="63ba8-103">In questo argomento verrà descritto come configurare le proprietà per la gestione basata su criteri in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="63ba8-103">This topic describes how to configure the properties for Policy-Based Management in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="63ba8-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="63ba8-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="63ba8-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="63ba8-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="63ba8-106">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="63ba8-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="63ba8-107">**Per configurare la gestione basata su criteri utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="63ba8-107">**To configure Policy-Based Management, using:**</span></span>  
  
     [<span data-ttu-id="63ba8-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="63ba8-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="63ba8-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="63ba8-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="63ba8-110">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="63ba8-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="63ba8-111">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="63ba8-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="63ba8-112">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="63ba8-112">Permissions</span></span>  
 <span data-ttu-id="63ba8-113">È necessaria l'appartenenza al ruolo predefinito del database PolicyAdministratorRole.</span><span class="sxs-lookup"><span data-stu-id="63ba8-113">Requires membership in the PolicyAdministratorRole fixed database role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="63ba8-114">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="63ba8-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-policy-based-management"></a><span data-ttu-id="63ba8-115">Per configurare la gestione basata su criteri</span><span class="sxs-lookup"><span data-stu-id="63ba8-115">To configure Policy-Based Management</span></span>  
  
1.  <span data-ttu-id="63ba8-116">In **Esplora oggetti**fare clic sul segno più per espandere il server in cui configurare le proprietà della gestione basata su criteri.</span><span class="sxs-lookup"><span data-stu-id="63ba8-116">In **Object Explorer**, click the plus sign to expand the server where you want to configure Policy-Based Management properties.</span></span>  
  
2.  <span data-ttu-id="63ba8-117">Fare clic sul segno più per espandere la cartella **Gestione** .</span><span class="sxs-lookup"><span data-stu-id="63ba8-117">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="63ba8-118">Fare clic con il pulsante destro del mouse su **Gestione criteri** , quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="63ba8-118">Right-click **Policy Management** and select **Properties**.</span></span>  
  
     <span data-ttu-id="63ba8-119">Nella finestra di dialogo **Proprietà Gestione criteri** sono disponibili le opzioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="63ba8-119">The following options are available in **Policy Management Properties** dialog box.</span></span>  
  
     <span data-ttu-id="63ba8-120">**Enabled**</span><span class="sxs-lookup"><span data-stu-id="63ba8-120">**Enabled**</span></span>  
     <span data-ttu-id="63ba8-121">Consente di specificare se la gestione basata su criteri è abilitata.</span><span class="sxs-lookup"><span data-stu-id="63ba8-121">Specifies whether Policy-Based Management is enabled.</span></span>  
  
     <span data-ttu-id="63ba8-122">**HistoryRetentionInDays**</span><span class="sxs-lookup"><span data-stu-id="63ba8-122">**HistoryRetentionInDays**</span></span>  
     <span data-ttu-id="63ba8-123">Consente di specificare il numero di giorni di conservazione della cronologia di valutazione dei criteri.</span><span class="sxs-lookup"><span data-stu-id="63ba8-123">Specifies the number of days that policy evaluation history should be retained.</span></span> <span data-ttu-id="63ba8-124">Se questo valore è pari a 0, ovvero il valore predefinito, la cronologia non verrà rimossa automaticamente.</span><span class="sxs-lookup"><span data-stu-id="63ba8-124">If this value is 0 (the default), the history will not be automatically removed.</span></span>  
  
     <span data-ttu-id="63ba8-125">**LogOnSuccess**</span><span class="sxs-lookup"><span data-stu-id="63ba8-125">**LogOnSuccess**</span></span>  
     <span data-ttu-id="63ba8-126">Consente di specificare se vengono registrate le valutazioni di criteri riuscite nella gestione basata su criteri.</span><span class="sxs-lookup"><span data-stu-id="63ba8-126">Specifies whether Policy-Based Management logs successful policy evaluations.</span></span>  
  
    -   <span data-ttu-id="63ba8-127">Se questo valore corrisponde a false, ovvero il valore predefinito, vengono registrate solo le valutazioni di criteri non riuscite.</span><span class="sxs-lookup"><span data-stu-id="63ba8-127">When this value is false (the default), only failed policy evaluations are logged.</span></span>  
  
    -   <span data-ttu-id="63ba8-128">Se questo valore corrisponde a true, vengono registrate sia le valutazioni di criteri riuscite che quelle non riuscite.</span><span class="sxs-lookup"><span data-stu-id="63ba8-128">When this value is true, both successful and failed policy evaluations are logged.</span></span>  
  
4.  <span data-ttu-id="63ba8-129">Al termine, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="63ba8-129">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="63ba8-130">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="63ba8-130">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-policy-based-management"></a><span data-ttu-id="63ba8-131">Per configurare la gestione basata su criteri</span><span class="sxs-lookup"><span data-stu-id="63ba8-131">To configure Policy-Based Management</span></span>  
  
1.  <span data-ttu-id="63ba8-132">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="63ba8-132">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="63ba8-133">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="63ba8-133">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="63ba8-134">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="63ba8-134">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- enables Policy-Based Management   
    USE msdb;  
    GO  
    EXEC dbo.sp_syspolicy_configure   
         @name = N'Enabled',   
         @value = 1;  
    GO  
    ```  
  
 <span data-ttu-id="63ba8-135">Per altre informazioni, vedere [sp_syspolicy_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-syspolicy-configure-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="63ba8-135">For more information, see [sp_syspolicy_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-syspolicy-configure-transact-sql).</span></span>  
  
  
