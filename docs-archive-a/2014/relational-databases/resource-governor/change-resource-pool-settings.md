---
title: Modificare le impostazioni del pool di risorse | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Resource Governor, resource pool alter
- resource pools [SQL Server], alter
ms.assetid: 49438285-a011-4dac-bd4f-f35cd90fda61
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2183cceaaf8a3e183d96c154075f9a922942c2c6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714140"
---
# <a name="change-resource-pool-settings"></a><span data-ttu-id="b7957-102">Modificare le impostazioni del pool di risorse</span><span class="sxs-lookup"><span data-stu-id="b7957-102">Change Resource Pool Settings</span></span>
  <span data-ttu-id="b7957-103">È possibile modificare le impostazioni di un pool di risorse utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b7957-103">You can change resource pool settings by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
-   <span data-ttu-id="b7957-104">**Prima di iniziare:**  [Limitazioni e restrizioni](#LimitationsRestrictions), [Autorizzazioni](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="b7957-104">**Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions), [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="b7957-105">**Per modificare le impostazioni per un pool di risorse usando:**  [SQL Server Management Studio](#ChgRPProp), [Transact-SQL](#ChgRPTSQL)</span><span class="sxs-lookup"><span data-stu-id="b7957-105">**To change the settings for a resource pool, using:**  [SQL Server Management Studio](#ChgRPProp), [Transact-SQL](#ChgRPTSQL)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b7957-106">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="b7957-106">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="b7957-107">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="b7957-107">Limitations and Restrictions</span></span>  
 <span data-ttu-id="b7957-108">La percentuale massima della CPU deve essere uguale o maggiore della percentuale minima della CPU.</span><span class="sxs-lookup"><span data-stu-id="b7957-108">The maximum CPU percentage must be equal to or higher than the minimum CPU percentage.</span></span> <span data-ttu-id="b7957-109">La percentuale massima della memoria deve essere uguale o maggiore della percentuale minima della memoria.</span><span class="sxs-lookup"><span data-stu-id="b7957-109">The maximum memory percentage must be equal to or higher than the minimum memory percentage.</span></span>  
  
 <span data-ttu-id="b7957-110">La somma delle percentuali minime della CPU e delle percentuali minime della memoria per tutti i pool di risorse non deve superare 100.</span><span class="sxs-lookup"><span data-stu-id="b7957-110">The sums of the minimum CPU percentages and minimum memory percentages for all resource pools must not exceed 100.</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b7957-111">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="b7957-111">Permissions</span></span>  
 <span data-ttu-id="b7957-112">Per modificare le impostazioni di un pool di risorse è necessaria l'autorizzazione CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="b7957-112">Changing resource pool settings requires CONTROL SERVER permission.</span></span>  
  
##  <a name="change-resource-pool-settings-using-sql-server-management-studio"></a><a name="ChgRPProp"></a> <span data-ttu-id="b7957-113">Modificare le impostazioni di un pool di risorse utilizzando SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b7957-113">Change Resource Pool Settings Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="b7957-114">**Per modificare le impostazioni di un pool di risorse utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="b7957-114">**To change resource pool settings by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]**</span></span>  
  
1.  <span data-ttu-id="b7957-115">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]aprire Esplora oggetti ed espandere in modo ricorsivo il nodo **Gestione** fino a **Pool di risorse**incluso.</span><span class="sxs-lookup"><span data-stu-id="b7957-115">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open Object Explorer and recursively expand the **Management** node down to and including **Resource Pools**.</span></span>  
  
2.  <span data-ttu-id="b7957-116">Fare clic con il pulsante destro del mouse sul pool di risorse da modificare, quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="b7957-116">Right-click the resource pool to be modified, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="b7957-117">Nella pagina **Proprietà di Resource Governor** selezionare la riga per il pool di risorse nella griglia **Pool di risorse** se non è selezionata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="b7957-117">In the **Resource Governor Properties** page, select the row for the resource pool in the **Resource pools** grid if it is not automatically selected.</span></span>  
  
4.  <span data-ttu-id="b7957-118">Selezionare o fare doppio clic sulle celle della riga da modificare e immettere i nuovi valori.</span><span class="sxs-lookup"><span data-stu-id="b7957-118">Click or double-click the cells in the row to be changed, and enter the new values.</span></span>  
  
5.  <span data-ttu-id="b7957-119">Per salvare le modifiche, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b7957-119">To save the changes, click **OK**</span></span>  
  
##  <a name="change-resource-pool-settings-using-transact-sql"></a><a name="ChgRPTSQL"></a> <span data-ttu-id="b7957-120">Modificare le impostazioni di un pool di risorse utilizzando Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b7957-120">Change Resource Pool Settings Using Transact-SQL</span></span>  
 <span data-ttu-id="b7957-121">**Per modificare le impostazioni di un pool di risorse utilizzando [!INCLUDE[tsql](../../includes/tsql-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="b7957-121">**To change resource pool settings by using [!INCLUDE[tsql](../../includes/tsql-md.md)]**</span></span>  
  
1.  <span data-ttu-id="b7957-122">Eseguire l'istruzione `ALTER RESOURCE POOL` specificando i valori di proprietà da modificare.</span><span class="sxs-lookup"><span data-stu-id="b7957-122">Run the `ALTER RESOURCE POOL` statement specifying the property values to be changed.</span></span>  
  
2.  <span data-ttu-id="b7957-123">Eseguire l'istruzione **ALTER RESOURCE GOVERNOR RECONFIGURE** .</span><span class="sxs-lookup"><span data-stu-id="b7957-123">Run the **ALTER RESOURCE GOVERNOR RECONFIGURE** statement.</span></span>  
  
### <a name="example-transact-sql"></a><span data-ttu-id="b7957-124">Esempio (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="b7957-124">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="b7957-125">Nell'esempio seguente viene modificata l'impostazione relativa alla percentuale massima della CPU per il pool di risorse denominato `poolAdhoc`.</span><span class="sxs-lookup"><span data-stu-id="b7957-125">The following example changes the max CPU percentage setting for the resource pool named `poolAdhoc`.</span></span>  
  
```  
ALTER RESOURCE POOL poolAdhoc  
WITH (MAX_CPU_PERCENT = 25);  
GO  
ALTER RESOURCE GOVERNOR RECONFIGURE;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="b7957-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b7957-126">See Also</span></span>  
 <span data-ttu-id="b7957-127">[Resource Governor](resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="b7957-127">[Resource Governor](resource-governor.md) </span></span>  
 <span data-ttu-id="b7957-128">[Abilitare Resource Governor](enable-resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="b7957-128">[Enable Resource Governor](enable-resource-governor.md) </span></span>  
 <span data-ttu-id="b7957-129">[Creare un pool di risorse](create-a-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="b7957-129">[Create a Resource Pool](create-a-resource-pool.md) </span></span>  
 <span data-ttu-id="b7957-130">[Eliminare un pool di risorse](delete-a-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="b7957-130">[Delete a Resource Pool](delete-a-resource-pool.md) </span></span>  
 <span data-ttu-id="b7957-131">[Gruppo di carico di lavoro di Resource Governor](resource-governor-workload-group.md) </span><span class="sxs-lookup"><span data-stu-id="b7957-131">[Resource Governor Workload Group](resource-governor-workload-group.md) </span></span>  
 <span data-ttu-id="b7957-132">[Funzione di classificazione di Resource Governor](resource-governor-classifier-function.md) </span><span class="sxs-lookup"><span data-stu-id="b7957-132">[Resource Governor Classifier Function](resource-governor-classifier-function.md) </span></span>  
 <span data-ttu-id="b7957-133">[ALTER RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-resource-pool-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b7957-133">[ALTER RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-resource-pool-transact-sql) </span></span>  
 [<span data-ttu-id="b7957-134">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b7957-134">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-resource-governor-transact-sql)  
  
  
