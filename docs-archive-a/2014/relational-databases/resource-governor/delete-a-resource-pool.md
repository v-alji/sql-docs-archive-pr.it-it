---
title: Eliminare un pool di risorse | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Resource Governor, resource pool delete
- resource pools [SQL Server], delete
ms.assetid: 3bdd348b-6582-4ffa-80ef-d49e50596ce5
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: a67b0e2262fa3007597091b6087cc937bb0f3276
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715159"
---
# <a name="delete-a-resource-pool"></a><span data-ttu-id="3335b-102">Eliminare un pool di risorse</span><span class="sxs-lookup"><span data-stu-id="3335b-102">Delete a Resource Pool</span></span>
  <span data-ttu-id="3335b-103">È possibile eliminare un pool di risorse utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="3335b-103">You can delete a resource pool by using either [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or Transact-SQL.</span></span>  
  
-   <span data-ttu-id="3335b-104">**Prima di iniziare:**  [Limitazioni e restrizioni](#LimitationsRestrictions), [Autorizzazioni](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="3335b-104">**Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions), [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="3335b-105">**Per eliminare un pool di risorse usando:** [SQL Server Management Studio](#DelRPSSMS), [Transact-SQL](#DelRPTSQL)</span><span class="sxs-lookup"><span data-stu-id="3335b-105">**To delete a resource pool, using:** [SQL Server Management Studio](#DelRPSSMS), [Transact-SQL](#DelRPTSQL)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="3335b-106">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="3335b-106">Before You Begin</span></span>  
 <span data-ttu-id="3335b-107">Non è possibile eliminare un pool di risorse contenente gruppi di carico di lavoro.</span><span class="sxs-lookup"><span data-stu-id="3335b-107">You cannot delete a resource pool if it contains workload groups.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="3335b-108">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="3335b-108">Limitations and Restrictions</span></span>  
 <span data-ttu-id="3335b-109">Non è possibile eliminare pool di risorse predefiniti o interni di Resource Governor.</span><span class="sxs-lookup"><span data-stu-id="3335b-109">You cannot delete the Resource Governor default or internal resource pools.</span></span> <span data-ttu-id="3335b-110">Non è possibile eliminare un pool di risorse contenente gruppi di carico di lavoro.</span><span class="sxs-lookup"><span data-stu-id="3335b-110">You cannot delete a resource pool if it contains workload groups.</span></span> <span data-ttu-id="3335b-111">Per altre informazioni, vedere [Delete a Workload Group](delete-a-workload-group.md).</span><span class="sxs-lookup"><span data-stu-id="3335b-111">For more information, see [Delete a Workload Group](delete-a-workload-group.md).</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="3335b-112">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="3335b-112">Permissions</span></span>  
 <span data-ttu-id="3335b-113">Per eliminare un pool di risorse è necessaria l'autorizzazione CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="3335b-113">Deleting a resource pool requires CONTROL SERVER permission.</span></span>  
  
##  <a name="delete-a-resource-pool-using-object-explorer"></a><a name="DelRPSSMS"></a> <span data-ttu-id="3335b-114">Eliminare un pool di risorse utilizzando Esplora oggetti</span><span class="sxs-lookup"><span data-stu-id="3335b-114">Delete a Resource Pool Using Object Explorer</span></span>  
 <span data-ttu-id="3335b-115">**Per eliminare un pool di risorse utilizzando SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="3335b-115">**To delete a resource pool by using SQL Server Management Studio**</span></span>  
  
1.  <span data-ttu-id="3335b-116">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]aprire Esplora oggetti ed espandere in modo ricorsivo il nodo **Gestione** fino a **Resource Governor**incluso.</span><span class="sxs-lookup"><span data-stu-id="3335b-116">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open Object Explorer and recursively expand the **Management** node down to and including **Resource Governor**.</span></span>  
  
2.  <span data-ttu-id="3335b-117">Fare clic con il pulsante destro del mouse sul pool di risorse da eliminare, quindi scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="3335b-117">Right-click the resource pool to be deleted, and then click **Delete**.</span></span>  
  
3.  <span data-ttu-id="3335b-118">Nella finestra **Elimina oggetto** , il pool di risorse è indicato nell'elenco **Oggetto da eliminare** .</span><span class="sxs-lookup"><span data-stu-id="3335b-118">In the **Delete Object** window, the resource pool is listed in the **Object to be deleted** list.</span></span> <span data-ttu-id="3335b-119">Per eliminare il pool di risorse, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="3335b-119">To delete the resource pool, click **OK**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="3335b-120">Se si tenta di eliminare un pool di risorse in cui è contenuto un gruppo di carico di lavoro, si verificherà un errore.</span><span class="sxs-lookup"><span data-stu-id="3335b-120">If the resource pool that you are trying to delete contains a workload group, this action will fail.</span></span>  
  
##  <a name="delete-a-resource-pool-using-transact-sql"></a><a name="DelRPTSQL"></a> <span data-ttu-id="3335b-121">Eliminare un pool di risorse utilizzando Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3335b-121">Delete a Resource Pool Using Transact-SQL</span></span>  
 <span data-ttu-id="3335b-122">**Per eliminare un pool di risorse utilizzando Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="3335b-122">**To delete a resource pool by using Transact-SQL**</span></span>  
  
1.  <span data-ttu-id="3335b-123">Eseguire l'istruzione `DROP RESOURCE POOL` specificando il nome del pool di risorse da eliminare.</span><span class="sxs-lookup"><span data-stu-id="3335b-123">Run the `DROP RESOURCE POOL` statement specifying the name of the resource pool to delete.</span></span>  
  
2.  <span data-ttu-id="3335b-124">Eseguire l'istruzione **ALTER RESOURCE GOVERNOR RECONFIGURE** .</span><span class="sxs-lookup"><span data-stu-id="3335b-124">Run the **ALTER RESOURCE GOVERNOR RECONFIGURE** statement.</span></span>  
  
### <a name="example-transact-sql"></a><span data-ttu-id="3335b-125">Esempio (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="3335b-125">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="3335b-126">Nell'esempio seguente viene eliminato un gruppo di carico di lavoro denominato `poolAdhoc`.</span><span class="sxs-lookup"><span data-stu-id="3335b-126">The following example drops a workload group named `poolAdhoc`.</span></span>  
  
```  
DROP RESOURCE POOL poolAdhoc;  
GO  
ALTER RESOURCE GOVERNOR RECONFIGURE;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="3335b-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3335b-127">See Also</span></span>  
 <span data-ttu-id="3335b-128">[Resource Governor](resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="3335b-128">[Resource Governor](resource-governor.md) </span></span>  
 <span data-ttu-id="3335b-129">[Pool di risorse di Resource Governor](resource-governor-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="3335b-129">[Resource Governor Resource Pool](resource-governor-resource-pool.md) </span></span>  
 <span data-ttu-id="3335b-130">[Creare un pool di risorse](create-a-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="3335b-130">[Create a Resource Pool](create-a-resource-pool.md) </span></span>  
 <span data-ttu-id="3335b-131">[Modificare le impostazioni del pool di risorse](change-resource-pool-settings.md) </span><span class="sxs-lookup"><span data-stu-id="3335b-131">[Change Resource Pool Settings](change-resource-pool-settings.md) </span></span>  
 <span data-ttu-id="3335b-132">[Gruppo di carico di lavoro di Resource Governor](resource-governor-workload-group.md) </span><span class="sxs-lookup"><span data-stu-id="3335b-132">[Resource Governor Workload Group](resource-governor-workload-group.md) </span></span>  
 <span data-ttu-id="3335b-133">[Funzione di classificazione di Resource Governor](resource-governor-classifier-function.md) </span><span class="sxs-lookup"><span data-stu-id="3335b-133">[Resource Governor Classifier Function](resource-governor-classifier-function.md) </span></span>  
 <span data-ttu-id="3335b-134">[DROP WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-workload-group-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3335b-134">[DROP WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-workload-group-transact-sql) </span></span>  
 <span data-ttu-id="3335b-135">[DROP RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-resource-pool-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3335b-135">[DROP RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-resource-pool-transact-sql) </span></span>  
 [<span data-ttu-id="3335b-136">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3335b-136">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-resource-governor-transact-sql)  
  
  
