---
title: Creare un pool di risorse | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- resource pools [SQL Server], create
- Resource Governor, resource pool create
ms.assetid: 44dd0567-a4c8-4c72-89ff-e76f6ddef344
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5abd2e60f4f9bb5290b47f95349782f8b26ad8bb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637739"
---
# <a name="create-a-resource-pool"></a><span data-ttu-id="6c9db-102">Creare un pool di risorse</span><span class="sxs-lookup"><span data-stu-id="6c9db-102">Create a Resource Pool</span></span>
  <span data-ttu-id="6c9db-103">È possibile creare un pool di risorse utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6c9db-103">You can create a resource pool by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
-   <span data-ttu-id="6c9db-104">**Prima di iniziare:**  [Limitazioni e restrizioni](#LimitationsRestrictions), [Autorizzazioni](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="6c9db-104">**Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions), [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="6c9db-105">**Per creare un pool di risorse usando:**  [SQL Server Management Studio](#CreRPProp), [Transact-SQL](#CreRPTSQL)</span><span class="sxs-lookup"><span data-stu-id="6c9db-105">**To create a resource pool, using:**  [SQL Server Management Studio](#CreRPProp), [Transact-SQL](#CreRPTSQL)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="6c9db-106">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="6c9db-106">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="6c9db-107">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="6c9db-107">Limitations and Restrictions</span></span>  
 <span data-ttu-id="6c9db-108">La percentuale massima della CPU deve essere uguale o maggiore della percentuale minima della CPU.</span><span class="sxs-lookup"><span data-stu-id="6c9db-108">The maximum CPU percentage must be equal to or higher than the minimum CPU percentage.</span></span> <span data-ttu-id="6c9db-109">La percentuale massima della memoria deve essere uguale o maggiore della percentuale minima della memoria.</span><span class="sxs-lookup"><span data-stu-id="6c9db-109">The maximum memory percentage must be equal to or higher than the minimum memory percentage.</span></span>  
  
 <span data-ttu-id="6c9db-110">La somma delle percentuali minime della CPU e delle percentuali minime della memoria per tutti i pool di risorse non deve superare 100.</span><span class="sxs-lookup"><span data-stu-id="6c9db-110">The sums of the minimum CPU percentages and minimum memory percentages for all resource pools must not exceed 100.</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="6c9db-111">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="6c9db-111">Permissions</span></span>  
 <span data-ttu-id="6c9db-112">Per creare un pool di risorse è necessaria l'autorizzazione CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="6c9db-112">Creating a resource pool requires CONTROL SERVER permission.</span></span>  
  
##  <a name="create-a-resource-pool-using-sql-server-management-studio"></a><a name="CreRPProp"></a> <span data-ttu-id="6c9db-113">Creare un pool di risorse utilizzando SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6c9db-113">Create a Resource Pool Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="6c9db-114">**Per creare un pool di risorse utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="6c9db-114">**To create a resource pool by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]**</span></span>  
  
1.  <span data-ttu-id="6c9db-115">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]aprire Esplora oggetti ed espandere in modo ricorsivo il nodo **Gestione** fino a **Resource Governor**incluso.</span><span class="sxs-lookup"><span data-stu-id="6c9db-115">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open Object Explorer and recursively expand the **Management** node down to and including **Resource Governor**.</span></span>  
  
2.  <span data-ttu-id="6c9db-116">Fare clic con il pulsante destro del mouse su **Resource Governor**, quindi su **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="6c9db-116">Right-click **Resource Governor**, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="6c9db-117">Nella griglia **Pool di risorse** fare clic sulla prima colonna nella riga vuota.</span><span class="sxs-lookup"><span data-stu-id="6c9db-117">In the **Resource pools** grid, click the first column in the empty row.</span></span> <span data-ttu-id="6c9db-118">Questa colonna è etichettata con un asterisco (\*).</span><span class="sxs-lookup"><span data-stu-id="6c9db-118">This column is labeled with an asterisk (\*).</span></span>  
  
4.  <span data-ttu-id="6c9db-119">Fare doppio clic sulla cella vuota nella colonna **Nome** .</span><span class="sxs-lookup"><span data-stu-id="6c9db-119">Double-click the empty cell in the **Name** column.</span></span> <span data-ttu-id="6c9db-120">Digitare il nome che si desidera utilizzare per il pool di risorse.</span><span class="sxs-lookup"><span data-stu-id="6c9db-120">Type in the name that you want to use for the resource pool.</span></span>  
  
5.  <span data-ttu-id="6c9db-121">Selezionare o fare doppio clic su qualsiasi altra cella della riga che si desidera modificare e immettere i nuovi valori.</span><span class="sxs-lookup"><span data-stu-id="6c9db-121">Click or double-click any other cells in the row you want to change, and enter the new values.</span></span>  
  
6.  <span data-ttu-id="6c9db-122">Per salvare le modifiche, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="6c9db-122">To save the changes, click **OK**</span></span>  
  
##  <a name="create-a-resource-pool-using-transact-sql"></a><a name="CreRPTSQL"></a> <span data-ttu-id="6c9db-123">Creare un pool di risorse utilizzando Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6c9db-123">Create a Resource Pool Using Transact-SQL</span></span>  
 <span data-ttu-id="6c9db-124">**Per creare un pool di risorse utilizzando [!INCLUDE[tsql](../../includes/tsql-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="6c9db-124">**To create a resource pool by using [!INCLUDE[tsql](../../includes/tsql-md.md)]**</span></span>  
  
1.  <span data-ttu-id="6c9db-125">Eseguire l'istruzione `CREATE RESOURCE POOL` specificando i valori di proprietà da impostare.</span><span class="sxs-lookup"><span data-stu-id="6c9db-125">Run the `CREATE RESOURCE POOL` statement specifying the property values to be set.</span></span>  
  
2.  <span data-ttu-id="6c9db-126">Eseguire l'istruzione **ALTER RESOURCE GOVERNOR RECONFIGURE** .</span><span class="sxs-lookup"><span data-stu-id="6c9db-126">Run the **ALTER RESOURCE GOVERNOR RECONFIGURE** statement.</span></span>  
  
### <a name="example-transact-sql"></a><span data-ttu-id="6c9db-127">Esempio (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="6c9db-127">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="6c9db-128">Nell'esempio seguente viene creato un pool di risorse denominato `poolAdhoc`.</span><span class="sxs-lookup"><span data-stu-id="6c9db-128">The following example creates a resource pool named `poolAdhoc`.</span></span>  
  
```  
CREATE RESOURCE POOL poolAdhoc  
WITH (MAX_CPU_PERCENT = 20);  
GO  
ALTER RESOURCE GOVERNOR RECONFIGURE;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="6c9db-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6c9db-129">See Also</span></span>  
 <span data-ttu-id="6c9db-130">[Resource Governor](resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="6c9db-130">[Resource Governor](resource-governor.md) </span></span>  
 <span data-ttu-id="6c9db-131">[Abilitare Resource Governor](enable-resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="6c9db-131">[Enable Resource Governor](enable-resource-governor.md) </span></span>  
 <span data-ttu-id="6c9db-132">[Pool di risorse di Resource Governor](resource-governor-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="6c9db-132">[Resource Governor Resource Pool](resource-governor-resource-pool.md) </span></span>  
 <span data-ttu-id="6c9db-133">[Modificare le impostazioni del pool di risorse](change-resource-pool-settings.md) </span><span class="sxs-lookup"><span data-stu-id="6c9db-133">[Change Resource Pool Settings](change-resource-pool-settings.md) </span></span>  
 <span data-ttu-id="6c9db-134">[Eliminare un pool di risorse](delete-a-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="6c9db-134">[Delete a Resource Pool](delete-a-resource-pool.md) </span></span>  
 <span data-ttu-id="6c9db-135">[Configurare Resource Governor utilizzando un modello](configure-resource-governor-using-a-template.md) </span><span class="sxs-lookup"><span data-stu-id="6c9db-135">[Configure Resource Governor Using a Template](configure-resource-governor-using-a-template.md) </span></span>  
 <span data-ttu-id="6c9db-136">[Gruppo di carico di lavoro di Resource Governor](resource-governor-workload-group.md) </span><span class="sxs-lookup"><span data-stu-id="6c9db-136">[Resource Governor Workload Group](resource-governor-workload-group.md) </span></span>  
 <span data-ttu-id="6c9db-137">[Funzione di classificazione di Resource Governor](resource-governor-classifier-function.md) </span><span class="sxs-lookup"><span data-stu-id="6c9db-137">[Resource Governor Classifier Function](resource-governor-classifier-function.md) </span></span>  
 <span data-ttu-id="6c9db-138">[CREATE RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-resource-pool-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6c9db-138">[CREATE RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-resource-pool-transact-sql) </span></span>  
 [<span data-ttu-id="6c9db-139">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="6c9db-139">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-resource-governor-transact-sql)  
  
  
