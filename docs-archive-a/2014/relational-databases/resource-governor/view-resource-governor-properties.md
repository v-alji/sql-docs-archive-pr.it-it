---
title: Visualizzare proprietà di Resource Governor | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
f1_keywords:
- sql12.swb.rg.properties.f1
helpviewer_keywords:
- Resource Governor, properties
ms.assetid: de3510df-f792-4a9d-80fa-f198fd36cdc8
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 3cd7af8f4f8eb3cd0531bc907011846f73f94f6f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627174"
---
# <a name="view-resource-governor-properties"></a><span data-ttu-id="94056-102">View Resource Governor Properties</span><span class="sxs-lookup"><span data-stu-id="94056-102">View Resource Governor Properties</span></span>
  <span data-ttu-id="94056-103">È possibile creare o configurare entità Resource Governor, ad esempio pool di risorse e gruppi di carico di lavoro, tramite la pagina Proprietà di Resource Governor in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="94056-103">You can create or configure Resource Governor entities, such as resource pools and workload groups, by using the Resource Governor Properties page in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
1.  <span data-ttu-id="94056-104">**Prima di iniziare:**  [Autorizzazioni](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="94056-104">**Before you begin:**  [Permissions](#Permissions)</span></span>  
  
2.  <span data-ttu-id="94056-105">**Per visualizzare le proprietà di Resource Governor usando:**  [Pagina Proprietà di Resource Governor](#ViewRGProp)</span><span class="sxs-lookup"><span data-stu-id="94056-105">**To view Resource Governor properties, using:**  [Resource Governor Properties page](#ViewRGProp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="94056-106">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="94056-106">Before You Begin</span></span>  
 <span data-ttu-id="94056-107">Oltre a visualizzare le proprietà di entità Resource Governor, è possibile eseguire diverse attività di configurazione tramite la pagina **Proprietà di Resource Governor** .</span><span class="sxs-lookup"><span data-stu-id="94056-107">In addition to viewing the properties of Resource Governor entities, you can perform several configuration tasks using the **Resource Governor Properties** page.</span></span> <span data-ttu-id="94056-108">Per altre informazioni, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="94056-108">For more information, see these topics:</span></span>  
  
-   [<span data-ttu-id="94056-109">Abilitare Resource Governor</span><span class="sxs-lookup"><span data-stu-id="94056-109">Enable Resource Governor</span></span>](enable-resource-governor.md)  
  
-   [<span data-ttu-id="94056-110">Disabilitare Resource Governor</span><span class="sxs-lookup"><span data-stu-id="94056-110">Disable Resource Governor</span></span>](disable-resource-governor.md)  
  
-   [<span data-ttu-id="94056-111">Creare un pool di risorse</span><span class="sxs-lookup"><span data-stu-id="94056-111">Create a Resource Pool</span></span>](create-a-resource-pool.md)  
  
-   [<span data-ttu-id="94056-112">Creare un gruppo di carico di lavoro</span><span class="sxs-lookup"><span data-stu-id="94056-112">Create a Workload Group</span></span>](create-a-workload-group.md)  
  
-   [<span data-ttu-id="94056-113">Modificare le impostazioni del pool di risorse</span><span class="sxs-lookup"><span data-stu-id="94056-113">Change Resource Pool Settings</span></span>](change-resource-pool-settings.md)  
  
-   [<span data-ttu-id="94056-114">Modificare le impostazioni dei gruppi di carico di lavoro</span><span class="sxs-lookup"><span data-stu-id="94056-114">Change Workload Group Settings</span></span>](change-workload-group-settings.md)  
  
-   [<span data-ttu-id="94056-115">Spostare un gruppo di carico di lavoro</span><span class="sxs-lookup"><span data-stu-id="94056-115">Move a Workload Group</span></span>](move-a-workload-group.md)  
  
 <span data-ttu-id="94056-116">Dopo aver aggiunto, eliminato o spostato un gruppo di carico di lavoro o un pool di risorse e quindi aver scelto **OK** , verrà eseguita l'istruzione ALTER RESOURCE GOVERNOR RECONFIGURE.</span><span class="sxs-lookup"><span data-stu-id="94056-116">When you click **OK** after adding, deleting, or moving a workload group or resource pool, the ALTER RESOURCE GOVERNOR RECONFIGURE statement is executed.</span></span>  
  
 <span data-ttu-id="94056-117">Se l'operazione di creazione o riconfigurazione del pool di risorse o gruppo di carico di lavoro non viene completata, viene visualizzato un messaggio di riepilogo degli errori sotto il titolo della pagina delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="94056-117">If the create or reconfigure operation for the resource pool or workload group fails, a summary error message appears below the title of the property page.</span></span> <span data-ttu-id="94056-118">Per visualizzare un messaggio di errore dettagliato, fare clic sulla freccia GIÙ sul messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="94056-118">To see a detailed error message, click the down arrow on the error message.</span></span>  
  
 <span data-ttu-id="94056-119">È possibile determinare se è presente una configurazione in sospeso eseguendo una query sulla vista a gestione dinamica [sys.dm_resource_governor_configuration](/sql/relational-databases/system-dynamic-management-views/sys-dm-resource-governor-configuration-transact-sql) per ottenere lo stato corrente di is_configuration_pending.</span><span class="sxs-lookup"><span data-stu-id="94056-119">You can determine whether there is a configuration pending by querying the [sys.dm_resource_governor_configuration](/sql/relational-databases/system-dynamic-management-views/sys-dm-resource-governor-configuration-transact-sql) dynamic management view to get the current status of is_configuration_pending.</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="94056-120">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="94056-120">Permissions</span></span>  
 <span data-ttu-id="94056-121">Per visualizzare le proprietà di Resource Governor è necessaria l'autorizzazione VIEW SERVER STATER.</span><span class="sxs-lookup"><span data-stu-id="94056-121">Viewing resource governor properties requires VIEW SERVER STATER permission.</span></span> <span data-ttu-id="94056-122">Per le attività di configurazione di Resource Governor è necessaria l'autorizzazione CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="94056-122">The resource governor configuration tasks require CONTROL SERVER permission.</span></span>  
  
##  <a name="view-the-resource-governor-properties-page"></a><a name="ViewRGProp"></a><span data-ttu-id="94056-123">Visualizzare la pagina delle proprietà Resource Governor</span><span class="sxs-lookup"><span data-stu-id="94056-123">View the Resource Governor Properties Page</span></span>  
 <span data-ttu-id="94056-124">**Per visualizzare le proprietà di Resource Governor tramite la pagina Proprietà di Resource Governor in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="94056-124">**To view resource governor properties by using the Resource Governor Properties page in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]**</span></span>  
  
1.  <span data-ttu-id="94056-125">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]aprire Esplora oggetti ed espandere in modo ricorsivo il nodo **Gestione** fino a **Resource Governor**.</span><span class="sxs-lookup"><span data-stu-id="94056-125">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open Object Explorer and recursively expand the **Management** node down to **Resource Governor**.</span></span>  
  
2.  <span data-ttu-id="94056-126">Fare clic con il pulsante destro del mouse su **Resource Governor** , quindi fare clic su **Proprietà**. In questo modo viene aperta la pagina **Proprietà di Resource Governor** .</span><span class="sxs-lookup"><span data-stu-id="94056-126">Right-click **Resource Governor** and then click **Properties**, this opens the **Resource Governor Properties** page.</span></span>  
  
3.  <span data-ttu-id="94056-127">Per le descrizioni dei campi nella pagina, vedere [Proprietà di Resource Governor](#RGProp).</span><span class="sxs-lookup"><span data-stu-id="94056-127">For descriptions of the fields in the page, see [Resource Governor Properties](#RGProp).</span></span>  
  
4.  <span data-ttu-id="94056-128">Per salvare eventuali modifiche, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="94056-128">To save any changes, click **OK**.</span></span>  
  
##  <a name="resource-governor-properties"></a><a name="RGProp"></a><span data-ttu-id="94056-129">Proprietà Resource Governor</span><span class="sxs-lookup"><span data-stu-id="94056-129">Resource Governor Properties</span></span>  
 <span data-ttu-id="94056-130">**Nome della funzione di classificazione**</span><span class="sxs-lookup"><span data-stu-id="94056-130">**Classifier function name**</span></span>  
 <span data-ttu-id="94056-131">Consente di specificare la funzione di classificazione selezionandola nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="94056-131">Specify the classifier function by selecting from the list.</span></span>  
  
 <span data-ttu-id="94056-132">**Abilitare Resource Governor**</span><span class="sxs-lookup"><span data-stu-id="94056-132">**Enable Resource Governor**</span></span>  
 <span data-ttu-id="94056-133">Consente di abilitare o disabilitare Resource Governor selezionando o deselezionando la casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="94056-133">Enable or disable Resource Governor by selecting or clearing the check box.</span></span>  
  
 <span data-ttu-id="94056-134">**Pool di risorse**</span><span class="sxs-lookup"><span data-stu-id="94056-134">**Resource pools**</span></span>  
 <span data-ttu-id="94056-135">Consente di creare o modificare la configurazione del pool di risorse utilizzando la griglia fornita.</span><span class="sxs-lookup"><span data-stu-id="94056-135">Create or change resource pool configuration by using the grid that is provided.</span></span> <span data-ttu-id="94056-136">Questa griglia viene popolata con le informazioni sui pool interni e sui pool predefiniti.</span><span class="sxs-lookup"><span data-stu-id="94056-136">This grid is populated with information for the predefined internal and default pools.</span></span> <span data-ttu-id="94056-137">Selezionare un pool da utilizzare facendo clic sulla prima colonna nella riga del pool.</span><span class="sxs-lookup"><span data-stu-id="94056-137">Select a pool to work with by clicking the first column in the row for the pool.</span></span> <span data-ttu-id="94056-138">Per creare un nuovo pool di risorse, fare clic sulla riga preceduta dall'asterisco ( **&#42;** ).</span><span class="sxs-lookup"><span data-stu-id="94056-138">To create a new resource pool, click the row that is prefixed by the asterisk (**&#42;**).</span></span>  
  
 <span data-ttu-id="94056-139">**Nome**</span><span class="sxs-lookup"><span data-stu-id="94056-139">**Name**</span></span>  
 <span data-ttu-id="94056-140">Consente di specificare il nome del pool di risorse.</span><span class="sxs-lookup"><span data-stu-id="94056-140">Specify the name of the resource pool.</span></span>  
  
 <span data-ttu-id="94056-141">**% CPU minima**</span><span class="sxs-lookup"><span data-stu-id="94056-141">**Minimum CPU %**</span></span>  
 <span data-ttu-id="94056-142">Consente di specificare la larghezza di banda media garantita della CPU concessa per tutte le richieste nel pool di risorse, in caso di conflitto di CPU.</span><span class="sxs-lookup"><span data-stu-id="94056-142">Specify the guaranteed average CPU bandwidth for all requests in the resource pool when there is CPU contention.</span></span> <span data-ttu-id="94056-143">L'intervallo è compreso tra 0 e 100.</span><span class="sxs-lookup"><span data-stu-id="94056-143">Range is 0 to 100.</span></span>  
  
 <span data-ttu-id="94056-144">**% massima CPU**</span><span class="sxs-lookup"><span data-stu-id="94056-144">**Maximum CPU %**</span></span>  
 <span data-ttu-id="94056-145">Consente di specificare la larghezza di banda media massima della CPU concessa per tutte le richieste nel pool di risorse in caso di conflitto di CPU.</span><span class="sxs-lookup"><span data-stu-id="94056-145">Specify the maximum average CPU bandwidth that all requests in this resource pool will receive when there is CPU contention.</span></span> <span data-ttu-id="94056-146">L'intervallo è compreso tra 0 e 100.</span><span class="sxs-lookup"><span data-stu-id="94056-146">Range is 0 to 100.</span></span> <span data-ttu-id="94056-147">L'impostazione predefinita è 100.</span><span class="sxs-lookup"><span data-stu-id="94056-147">The default setting is 100.</span></span>  
  
 <span data-ttu-id="94056-148">**% memoria minima**</span><span class="sxs-lookup"><span data-stu-id="94056-148">**Minimum Memory %**</span></span>  
 <span data-ttu-id="94056-149">Consente di specificare la quantità minima di memoria riservata al pool di risorse non condivisibile con altri pool di risorse.</span><span class="sxs-lookup"><span data-stu-id="94056-149">Specify the minimum amount of memory reserved for this resource pool that can not be shared with other resource pools.</span></span> <span data-ttu-id="94056-150">L'intervallo è compreso tra 0 e 100.</span><span class="sxs-lookup"><span data-stu-id="94056-150">Range is 0 to 100.</span></span>  
  
 <span data-ttu-id="94056-151">**% memoria massima**</span><span class="sxs-lookup"><span data-stu-id="94056-151">**Maximum Memory %**</span></span>  
 <span data-ttu-id="94056-152">Consente di specificare la memoria totale del server utilizzabile dalle richieste in questo pool di risorse.</span><span class="sxs-lookup"><span data-stu-id="94056-152">Specify the total server memory that can be used by requests in this resource pool.</span></span> <span data-ttu-id="94056-153">L'intervallo è compreso tra 0 e 100.</span><span class="sxs-lookup"><span data-stu-id="94056-153">Range is 0 to 100.</span></span> <span data-ttu-id="94056-154">L'impostazione predefinita è 100.</span><span class="sxs-lookup"><span data-stu-id="94056-154">The default setting is 100.</span></span>  
  
 <span data-ttu-id="94056-155">Per altre informazioni, vedere [creare un pool di risorse &#40;&#41;Transact-SQL ](/sql/t-sql/statements/create-resource-pool-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="94056-155">For more information, see [CREATE RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-resource-pool-transact-sql).</span></span>  
  
 <span data-ttu-id="94056-156">**Gruppi del carico di lavoro per pool di risorse**</span><span class="sxs-lookup"><span data-stu-id="94056-156">**Workload groups for resource pool**</span></span>  
 <span data-ttu-id="94056-157">Consente di creare o modificare la configurazione del gruppo del carico di lavoro utilizzando la griglia fornita.</span><span class="sxs-lookup"><span data-stu-id="94056-157">Create or change the workload group configuration by using the grid that is provided.</span></span> <span data-ttu-id="94056-158">Questa griglia viene popolata con le informazioni sui gruppi interni e sui gruppi predefiniti.</span><span class="sxs-lookup"><span data-stu-id="94056-158">This grid is populated with information for the predefined internal and default groups.</span></span> <span data-ttu-id="94056-159">Selezionare un gruppo da utilizzare facendo clic sulla prima colonna nella riga del pool.</span><span class="sxs-lookup"><span data-stu-id="94056-159">Select a group to work with by clicking the first column in the row for the pool.</span></span> <span data-ttu-id="94056-160">Per creare un nuovo gruppo del carico di lavoro, fare clic sulla riga preceduta dall'asterisco ( **&#42;** ).</span><span class="sxs-lookup"><span data-stu-id="94056-160">To create a new workload group, click the row that is prefixed by the asterisk (**&#42;**).</span></span>  
  
 <span data-ttu-id="94056-161">**Nome**</span><span class="sxs-lookup"><span data-stu-id="94056-161">**Name**</span></span>  
 <span data-ttu-id="94056-162">Consente di specificare il nome del gruppo del carico di lavoro.</span><span class="sxs-lookup"><span data-stu-id="94056-162">Specify the name of the workload group.</span></span>  
  
 <span data-ttu-id="94056-163">**Priorità**</span><span class="sxs-lookup"><span data-stu-id="94056-163">**Importance**</span></span>  
 <span data-ttu-id="94056-164">Consente di specificare l'importanza relativa di una richiesta nel gruppo del carico di lavoro.</span><span class="sxs-lookup"><span data-stu-id="94056-164">Specify the relative importance of a request in the workload group.</span></span> <span data-ttu-id="94056-165">Le impostazioni disponibili sono Minima, Media e Massima.</span><span class="sxs-lookup"><span data-stu-id="94056-165">Available settings are Low, Medium, and High.</span></span>  
  
 <span data-ttu-id="94056-166">**Numero massimo di richieste**</span><span class="sxs-lookup"><span data-stu-id="94056-166">**Maximum Requests**</span></span>  
 <span data-ttu-id="94056-167">Consente di specificare il numero massimo di richieste simultanee eseguibili nel gruppo del carico di lavoro.</span><span class="sxs-lookup"><span data-stu-id="94056-167">Specify the maximum number of simultaneous requests that are allowed to execute in the workload group.</span></span> <span data-ttu-id="94056-168">Deve essere 0 o un valore intero positivo.</span><span class="sxs-lookup"><span data-stu-id="94056-168">Must be 0 or a positive integer.</span></span>  
  
 <span data-ttu-id="94056-169">**Tempo CPU (sec)**</span><span class="sxs-lookup"><span data-stu-id="94056-169">**CPU Time (sec)**</span></span>  
 <span data-ttu-id="94056-170">Consente di specificare la quantità massimo di tempo della CPU utilizzabile da una richiesta.</span><span class="sxs-lookup"><span data-stu-id="94056-170">Specify the maximum amount of CPU time that a request can use.</span></span> <span data-ttu-id="94056-171">Deve essere 0 o un valore intero positivo.</span><span class="sxs-lookup"><span data-stu-id="94056-171">Must be 0 or a positive integer.</span></span> <span data-ttu-id="94056-172">Se è 0, il tempo è illimitato.</span><span class="sxs-lookup"><span data-stu-id="94056-172">If 0, the time is unlimited.</span></span>  
  
 <span data-ttu-id="94056-173">**% concessione memoria**</span><span class="sxs-lookup"><span data-stu-id="94056-173">**Memory Grant %**</span></span>  
 <span data-ttu-id="94056-174">Consente di specificare la quantità massima di memoria utilizzabile dal pool da una richiesta singola.</span><span class="sxs-lookup"><span data-stu-id="94056-174">Specify the maximum amount of memory that a single request can take from the pool.</span></span> <span data-ttu-id="94056-175">L'intervallo è compreso tra 0 e 100.</span><span class="sxs-lookup"><span data-stu-id="94056-175">Range is 0 to 100.</span></span>  
  
 <span data-ttu-id="94056-176">**Timeout concessione (sec)**</span><span class="sxs-lookup"><span data-stu-id="94056-176">**Grant Time-out (sec)**</span></span>  
 <span data-ttu-id="94056-177">Consente di specificare il tempo massimo di attesa di una query per la disponibilità di una risorsa, prima che la query generi un errore.</span><span class="sxs-lookup"><span data-stu-id="94056-177">Specify the maximum time that a query can wait for a resource to become available before the query fails.</span></span> <span data-ttu-id="94056-178">Deve essere 0 o un valore intero positivo.</span><span class="sxs-lookup"><span data-stu-id="94056-178">Must be 0 or a positive integer.</span></span>  
  
 <span data-ttu-id="94056-179">**Grado di parallelismo**</span><span class="sxs-lookup"><span data-stu-id="94056-179">**Degree of Parallelism**</span></span>  
 <span data-ttu-id="94056-180">Consente di specificare il grado massimo di parallelismo (DOP) per le richieste parallele.</span><span class="sxs-lookup"><span data-stu-id="94056-180">Specify the maximum degree of parallelism (DOP) for parallel requests.</span></span> <span data-ttu-id="94056-181">L'intervallo è da 0 a 64.</span><span class="sxs-lookup"><span data-stu-id="94056-181">Range is 0 to 64.</span></span>  
  
 <span data-ttu-id="94056-182">Per altre informazioni, vedere [CREATE WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-workload-group-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="94056-182">For more information, see [CREATE WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-workload-group-transact-sql).</span></span>  
  
## <a name="view-resource-governor-properties-by-using-transact-sql"></a><span data-ttu-id="94056-183">Visualizzare le proprietà di Resource Governor utilizzando Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="94056-183">View Resource Governor Properties by Using Transact-SQL</span></span>  
 <span data-ttu-id="94056-184">**Visualizzare le proprietà di Resource Governor utilizzando Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="94056-184">**View resource governor properties by using Transact-SQL**</span></span>  
  
1.  <span data-ttu-id="94056-185">Per visualizzare le definizioni delle entità resource governor, usare le [Viste del catalogo di Resource Governor &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/resource-governor-catalog-views-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="94056-185">To view the definitions of resource governor entities, use the [Resource Governor Catalog Views &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/resource-governor-catalog-views-transact-sql).</span></span>  
  
2.  <span data-ttu-id="94056-186">Per visualizzare le configurazioni correnti delle entità resource governor, usare le [Viste a gestione dinamica relative a Resource Governor &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/resource-governor-related-dynamic-management-views-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="94056-186">To view the current configuration of resource governor entities, use the [Resource Governor Related Dynamic Management Views &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/resource-governor-related-dynamic-management-views-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94056-187">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="94056-187">See Also</span></span>  
 <span data-ttu-id="94056-188">[Resource Governor](resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="94056-188">[Resource Governor](resource-governor.md) </span></span>  
 <span data-ttu-id="94056-189">[Abilitare Resource Governor](enable-resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="94056-189">[Enable Resource Governor](enable-resource-governor.md) </span></span>  
 <span data-ttu-id="94056-190">[Pool di risorse di Resource Governor](resource-governor-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="94056-190">[Resource Governor Resource Pool](resource-governor-resource-pool.md) </span></span>  
 <span data-ttu-id="94056-191">[Gruppo di carico di lavoro di Resource Governor](resource-governor-workload-group.md) </span><span class="sxs-lookup"><span data-stu-id="94056-191">[Resource Governor Workload Group](resource-governor-workload-group.md) </span></span>  
 [<span data-ttu-id="94056-192">Funzione di classificazione di Resource Governor</span><span class="sxs-lookup"><span data-stu-id="94056-192">Resource Governor Classifier Function</span></span>](resource-governor-classifier-function.md)  
  
  
