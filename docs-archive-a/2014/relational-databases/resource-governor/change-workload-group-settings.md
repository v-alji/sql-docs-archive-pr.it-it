---
title: Modificare le impostazioni dei gruppi di carico di lavoro | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- workload groups [SQL Server], alter
- Resource Governor, workload group alter
ms.assetid: 73b6109c-2ad0-4915-b11b-d40d5a0fdc25
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 579aad71d32a629d75f1eecd76e7dacfe32d94f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623133"
---
# <a name="change-workload-group-settings"></a><span data-ttu-id="06f9d-102">Modificare le impostazioni dei gruppi di carico di lavoro</span><span class="sxs-lookup"><span data-stu-id="06f9d-102">Change Workload Group Settings</span></span>
  <span data-ttu-id="06f9d-103">È possibile modificare le impostazioni di un gruppo di carico di lavoro utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="06f9d-103">You can change workload group settings by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
-   <span data-ttu-id="06f9d-104">**Prima di iniziare:**  [Limitazioni e restrizioni](#LimitationsRestrictions), [Autorizzazioni](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="06f9d-104">**Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions), [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="06f9d-105">**Per modificare le impostazioni per un gruppo di carico di lavoro, usando:**  [SQL Server Management Studio](#ChgWGProp), [Transact-SQL](#ChgWGTSQL)</span><span class="sxs-lookup"><span data-stu-id="06f9d-105">**To change the settings for a workload group, using:**  [SQL Server Management Studio](#ChgWGProp), [Transact-SQL](#ChgWGTSQL)</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="06f9d-106">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="06f9d-106">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="06f9d-107">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="06f9d-107">Limitations and Restrictions</span></span>  
 <span data-ttu-id="06f9d-108">È possibile modificare le impostazioni del gruppo di carico di lavoro predefinito e dei gruppi di carico di lavoro definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="06f9d-108">You can change the settings of the default workload group and user-defined workload groups.</span></span>  
  
 <span data-ttu-id="06f9d-109">**REQUEST_MAX_MEMORY_GRANT_PERCENT**</span><span class="sxs-lookup"><span data-stu-id="06f9d-109">**REQUEST_MAX_MEMORY_GRANT_PERCENT**</span></span>  
  
 <span data-ttu-id="06f9d-110">La quantità di memoria utilizzata per la creazione dell'indice in una tabella partizionata non allineata è proporzionale al numero di partizioni interessate.</span><span class="sxs-lookup"><span data-stu-id="06f9d-110">The memory consumed by index creation on a non-aligned partitioned table is proportional to the number of partitions involved.</span></span> <span data-ttu-id="06f9d-111">Se la memoria totale necessaria supera il limite per query (REQUEST_MAX_MEMORY_GRANT_PERCENT) imposto dall'impostazione del gruppo di carico di lavoro, la creazione dell'indice potrebbe non essere completata.</span><span class="sxs-lookup"><span data-stu-id="06f9d-111">If the total required memory exceeds the per-query limit, (REQUEST_MAX_MEMORY_GRANT_PERCENT) imposed by the workload group setting, this index creation may fail.</span></span> <span data-ttu-id="06f9d-112">Poiché il gruppo di carico di lavoro predefinito consente a una query di superare il limite per query con la memoria minima necessaria per la compatibilità con SQL Server 2005, l'utente potrebbe essere in grado di eseguire la stessa creazione dell'indice nel gruppo di carico di lavoro predefinito, se nel pool di risorse predefinito è configurata una quantità di memoria totale sufficiente per eseguire una query.</span><span class="sxs-lookup"><span data-stu-id="06f9d-112">Because the default workload group allows a query to exceed the per-query limit with the minimum required memory to start for SQL Server 2005 compatibility, the user may be able to run the same index creation in the default workload group, if the default resource pool has enough total memory configured to run such a query.</span></span>  
  
 <span data-ttu-id="06f9d-113">Per la creazione dell'indice è possibile utilizzare un'area di lavoro per la memoria maggiore rispetto a quanto inizialmente garantito per le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="06f9d-113">Index creation is allowed to use more memory workspace than initially granted for performance.</span></span> <span data-ttu-id="06f9d-114">Questa speciale gestione è supportata da Resource Governor, tuttavia, la concessione iniziale ed eventuali concessioni di memoria aggiuntiva sono limitate dalle impostazioni di gruppo del carico di lavoro e dal pool di risorse.</span><span class="sxs-lookup"><span data-stu-id="06f9d-114">This special handling is supported by Resource Governor, however, the initial grant and any additional memory grant are limited by the workload group and resource pool settings.</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="06f9d-115">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="06f9d-115">Permissions</span></span>  
 <span data-ttu-id="06f9d-116">Per modificare le impostazioni di un gruppo di carico di lavoro è necessaria l'autorizzazione CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="06f9d-116">Changing workload group settings requires CONTROL SERVER permission.</span></span>  
  
##  <a name="change-workload-group-settings-using-sql-server-management-studio"></a><a name="ChgWGProp"></a> <span data-ttu-id="06f9d-117">Modificare le impostazioni di un gruppo di carico di lavoro utilizzando SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="06f9d-117">Change Workload Group Settings Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="06f9d-118">**Per modificare le impostazioni di un gruppo di carico di lavoro utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="06f9d-118">**To change workload group settings by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]**</span></span>  
  
1.  <span data-ttu-id="06f9d-119">In Esplora oggetti espandere in modo ricorsivo il nodo **Gestione** fino alla cartella **Gruppi del carico di lavoro** inclusa in cui è contenuto il gruppo di carico di lavoro da modificare.</span><span class="sxs-lookup"><span data-stu-id="06f9d-119">In Object Explorer, recursively expand the **Management** node down to and including the **Workload Groups** folder that contains the workload group to be modified.</span></span>  
  
2.  <span data-ttu-id="06f9d-120">Fare clic con il pulsante destro del mouse sul gruppo di carico di lavoro da modificare e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="06f9d-120">Right-click the workload group to be modified, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="06f9d-121">Nella pagina **Proprietà di Resource Governor** selezionare la riga per il gruppo di carico di lavoro nella griglia **Gruppi del carico di lavoro per il pool di risorse** se non è selezionata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="06f9d-121">In the **Resource Governor Properties** page, select the row for the workload group in the **Workload groups for resource pool** grid if it is not automatically selected.</span></span>  
  
4.  <span data-ttu-id="06f9d-122">Selezionare o fare doppio clic sulle celle della riga da modificare e immettere i nuovi valori.</span><span class="sxs-lookup"><span data-stu-id="06f9d-122">Click or double-click the cells in the row to be changed, and enter the new values.</span></span>  
  
5.  <span data-ttu-id="06f9d-123">Per salvare le modifiche, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="06f9d-123">To save the changes, click **OK**</span></span>  
  
##  <a name="change-workload-group-settings-using-transact-sql"></a><a name="ChgWGTSQL"></a> <span data-ttu-id="06f9d-124">Modificare le impostazioni di un gruppo di carico di lavoro utilizzando Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="06f9d-124">Change Workload Group Settings Using Transact-SQL</span></span>  
 <span data-ttu-id="06f9d-125">**Per modificare le impostazioni di un gruppo di carico di lavoro utilizzando Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="06f9d-125">**To change workload group settings by using Transact-SQL**</span></span>  
  
1.  <span data-ttu-id="06f9d-126">Eseguire l'istruzione ALTER WORKLOAD GROUPP specificando i valori delle proprietà da modificare.</span><span class="sxs-lookup"><span data-stu-id="06f9d-126">Run the ALTER WORKLOAD GROUP statement specifying the property values to be changed.</span></span>  
  
2.  <span data-ttu-id="06f9d-127">Eseguire l'istruzione ALTER RESOURCE GOVERNOR RECONFIGURE.</span><span class="sxs-lookup"><span data-stu-id="06f9d-127">Run the ALTER RESOURCE GOVERNOR RECONFIGURE statement.</span></span>  
  
### <a name="example-transact-sql"></a><span data-ttu-id="06f9d-128">Esempio (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="06f9d-128">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="06f9d-129">Nell'esempio seguente viene modificata l'impostazione di percentuale di concessione di memoria massima per il gruppo di carico di lavoro denominato `groupAdhoc`.</span><span class="sxs-lookup"><span data-stu-id="06f9d-129">The following example changes the max memory grant percent setting for the workload group named `groupAdhoc`.</span></span>  
  
```  
ALTER WORKLOAD GROUP groupAdhoc  
WITH (REQUEST_MAX_MEMORY_GRANT_PERCENT = 30);  
GO  
ALTER RESOURCE GOVERNOR RECONFIGURE;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="06f9d-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="06f9d-130">See Also</span></span>  
 <span data-ttu-id="06f9d-131">[Resource Governor](resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="06f9d-131">[Resource Governor](resource-governor.md) </span></span>  
 <span data-ttu-id="06f9d-132">[Creare un gruppo di carico di lavoro](create-a-workload-group.md) </span><span class="sxs-lookup"><span data-stu-id="06f9d-132">[Create a Workload Group](create-a-workload-group.md) </span></span>  
 <span data-ttu-id="06f9d-133">[Creare un pool di risorse](create-a-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="06f9d-133">[Create a Resource Pool](create-a-resource-pool.md) </span></span>  
 <span data-ttu-id="06f9d-134">[Modificare le impostazioni del pool di risorse](change-resource-pool-settings.md) </span><span class="sxs-lookup"><span data-stu-id="06f9d-134">[Change Resource Pool Settings](change-resource-pool-settings.md) </span></span>  
 <span data-ttu-id="06f9d-135">[ALTER WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-workload-group-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="06f9d-135">[ALTER WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-workload-group-transact-sql) </span></span>  
 <span data-ttu-id="06f9d-136">[ALTER RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-resource-pool-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="06f9d-136">[ALTER RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-resource-pool-transact-sql) </span></span>  
 [<span data-ttu-id="06f9d-137">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="06f9d-137">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-resource-governor-transact-sql)  
  
  
