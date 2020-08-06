---
title: Eliminare un gruppo di carico di lavoro | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- workload groups [SQL Server], delete
- Resource Governor, workload group delete
ms.assetid: d5902c46-5c28-4ac1-8b56-cb4ca2b072d0
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 801a731db6c5b31bc479d1a3f6079c45ad9a7c04
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715167"
---
# <a name="delete-a-workload-group"></a><span data-ttu-id="7b3d4-102">Eliminare un gruppo di carico di lavoro</span><span class="sxs-lookup"><span data-stu-id="7b3d4-102">Delete a Workload Group</span></span>
  <span data-ttu-id="7b3d4-103">È possibile eliminare un gruppo di carico di lavoro o un pool di risorse utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="7b3d4-103">You can delete a workload group or resource pool by using either [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or Transact-SQL.</span></span>  
  
-   <span data-ttu-id="7b3d4-104">**Prima di iniziare:**  [Limitazioni e restrizioni](#LimitationsRestrictions), [Autorizzazioni](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="7b3d4-104">**Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions), [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="7b3d4-105">**Per eliminare un gruppo del carico di lavoro usando:**  [Esplora oggetti](#DelWGObjEx), [le proprietà di Resource Governor](#DelWGRGProp), [Transact-SQL](#DelWGTSQL)</span><span class="sxs-lookup"><span data-stu-id="7b3d4-105">**To delete a workload group, using:**  [Object Explorer](#DelWGObjEx), [Resource Governor Properties](#DelWGRGProp), [Transact-SQL](#DelWGTSQL)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="7b3d4-106">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="7b3d4-106">Before You Begin</span></span>  
 <span data-ttu-id="7b3d4-107">Non è possibile eliminare un gruppo di carico di lavoro contenente sessioni attive.</span><span class="sxs-lookup"><span data-stu-id="7b3d4-107">You cannot delete a workload group if it contains active sessions.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="7b3d4-108">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="7b3d4-108">Limitations and Restrictions</span></span>  
 <span data-ttu-id="7b3d4-109">Se in un gruppo di carico di lavoro sono contenute sessioni attive, non sarà possibile eliminare o spostare tale gruppo in un pool di risorse diverso quando viene chiamata l'istruzione ALTER RESOURCE GOVERNOR RECONFIGURE per l'applicazione della modifica.</span><span class="sxs-lookup"><span data-stu-id="7b3d4-109">If a workload group contains active sessions, deleting or moving the workload group to a different resource pool will fail when the ALTER RESOURCE GOVERNOR RECONFIGURE statement is called to apply the change.</span></span> <span data-ttu-id="7b3d4-110">Per evitare il problema, eseguire una delle azioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7b3d4-110">To avoid this problem, you can take one of the following actions:</span></span>  
  
-   <span data-ttu-id="7b3d4-111">Attendere la disconnessione di tutte le sessioni relative al gruppo interessato, quindi eseguire nuovamente l'istruzione ALTER RESOURCE GOVERNOR RECONFIGURE.</span><span class="sxs-lookup"><span data-stu-id="7b3d4-111">Wait until all the sessions from the affected group have disconnected, and then rerun the ALTER RESOURCE GOVERNOR RECONFIGURE statement.</span></span>  
  
-   <span data-ttu-id="7b3d4-112">Arrestare in modo esplicito le sessioni del gruppo interessato utilizzando il comando KILL, quindi eseguire nuovamente l'istruzione ALTER RESOURCE GOVERNOR RECONFIGURE.</span><span class="sxs-lookup"><span data-stu-id="7b3d4-112">Explicitly stop sessions in the affected group by using the KILL command, and then rerun the ALTER RESOURCE GOVERNOR RECONFIGURE statement.</span></span> <span data-ttu-id="7b3d4-113">Se si decide di non arrestare in modo esplicito le sessioni dopo aver utilizzato **Elimina** ma prima di arrestare le sessioni attive, ricreare il gruppo utilizzando il nome originale e spostare il gruppo nel pool di risorse originale.</span><span class="sxs-lookup"><span data-stu-id="7b3d4-113">If you decide that you do not want to explicitly stop sessions after you use **Delete** but before you stop active sessions, re-create the group by using the original name and move the group to the original resource pool.</span></span>  
  
-   <span data-ttu-id="7b3d4-114">Riavviare il server.</span><span class="sxs-lookup"><span data-stu-id="7b3d4-114">Restart the server.</span></span> <span data-ttu-id="7b3d4-115">Una volta completato il processo di riavvio, il gruppo eliminato non verrà creato e in un gruppo spostato verrà utilizzata la nuova assegnazione del pool di risorse.</span><span class="sxs-lookup"><span data-stu-id="7b3d4-115">After the restart process is completed, the deleted group will not be created, and a moved group will use the new resource pool assignment.</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="7b3d4-116">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="7b3d4-116">Permissions</span></span>  
 <span data-ttu-id="7b3d4-117">Per eliminare un gruppo di carico di lavoro è necessaria l'autorizzazione CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="7b3d4-117">Deleting a workload group requires CONTROL SERVER permission.</span></span>  
  
##  <a name="delete-a-workload-group-using-object-explorer"></a><a name="DelWGObjEx"></a> <span data-ttu-id="7b3d4-118">Eliminare un gruppo di carico di lavoro utilizzando Esplora oggetti</span><span class="sxs-lookup"><span data-stu-id="7b3d4-118">Delete a Workload Group Using Object Explorer</span></span>  
 <span data-ttu-id="7b3d4-119">**Per eliminare un gruppo di carico di lavoro utilizzando Esplora oggetti**</span><span class="sxs-lookup"><span data-stu-id="7b3d4-119">**To delete a workload group by using Object Explorer**</span></span>  
  
1.  <span data-ttu-id="7b3d4-120">In[!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]aprire Esplora oggetti ed espandere in modo ricorsivo il nodo **Gestione** fino a **Pool di risorse**incluso.</span><span class="sxs-lookup"><span data-stu-id="7b3d4-120">In[!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open Object Explorer and recursively expand the **Management** node down to and including **Resource Pools**.</span></span>  
  
2.  <span data-ttu-id="7b3d4-121">Espandere in modo ricorsivo **Pool di risorse** fino al nodo **Gruppi del carico di lavoro** incluso nel pool di risorse in cui è contenuto il gruppo di carico di lavoro da eliminare.</span><span class="sxs-lookup"><span data-stu-id="7b3d4-121">Recursively expand **Resource Pools** down to and including the **Workload Groups** node in the resource pool that contains the workload group to be deleted.</span></span>  
  
3.  <span data-ttu-id="7b3d4-122">Fare clic con il pulsante destro del mouse sul gruppo di carico di lavoro e scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="7b3d4-122">Right-click the workload group, and then click **Delete**.</span></span>  
  
4.  <span data-ttu-id="7b3d4-123">Nella finestra **Elimina oggetto** il gruppo di carico di lavoro viene indicato nell'elenco **Oggetto da eliminare** .</span><span class="sxs-lookup"><span data-stu-id="7b3d4-123">In the **Delete Object** window, the workload group is listed in the **Object to be deleted** list.</span></span> <span data-ttu-id="7b3d4-124">Per eliminare il gruppo di carico di lavoro, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="7b3d4-124">To delete the workload group, click **OK**.</span></span>  
  
##  <a name="delete-a-workload-group-using-resource-governor-properties"></a><a name="DelWGRGProp"></a> <span data-ttu-id="7b3d4-125">Eliminare un gruppo di carico di lavoro utilizzando Proprietà di Resource Governor</span><span class="sxs-lookup"><span data-stu-id="7b3d4-125">Delete a Workload Group Using Resource Governor Properties</span></span>  
 <span data-ttu-id="7b3d4-126">**Per eliminare un gruppo di carico di lavoro utilizzando la pagina Proprietà di Resource Governor**</span><span class="sxs-lookup"><span data-stu-id="7b3d4-126">**To delete a workload group by using the Resource Governor Properties page**</span></span>  
  
1.  <span data-ttu-id="7b3d4-127">In Esplora oggetti espandere in modo ricorsivo il nodo **Gestione** fino a **Pool di risorse**compreso.</span><span class="sxs-lookup"><span data-stu-id="7b3d4-127">In Object Explorer, recursively expand the **Management** node down to and including **Resource Pools**.</span></span>  
  
2.  <span data-ttu-id="7b3d4-128">Fare clic con il pulsante destro del mouse sul pool di risorse in cui è contenuto il gruppo di carico di lavoro da eliminare, quindi fare clic su **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="7b3d4-128">Right-click the resource pool that contains the workload group to be deleted, and then click **Properties**.</span></span> <span data-ttu-id="7b3d4-129">Viene aperta la pagina **Proprietà di Resource Governor** .</span><span class="sxs-lookup"><span data-stu-id="7b3d4-129">This opens the **Resource Governor Properties** page.</span></span>  
  
3.  <span data-ttu-id="7b3d4-130">Nella finestra **Gruppi del carico di lavoro per il pool di risorse** fare clic sulla riga del gruppo di carico di lavoro da eliminare, fare clic con il pulsante destro del mouse sulla freccia a destra sul lato sinistro della riga, quindi scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="7b3d4-130">In the **Workload groups for resource pool** window, click the line for the workload group to be deleted, then right-click the right arrow on the left side of the line, and then click **Delete**.</span></span>  
  
4.  <span data-ttu-id="7b3d4-131">Per eliminare il gruppo di carico di lavoro, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="7b3d4-131">To delete the workload group, click **OK**.</span></span>  
  
##  <a name="delete-a-workload-group-using-transact-sql"></a><a name="DelWGTSQL"></a> <span data-ttu-id="7b3d4-132">Eliminare un gruppo di carico di lavoro utilizzando Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7b3d4-132">Delete a Workload Group Using Transact-SQL</span></span>  
 <span data-ttu-id="7b3d4-133">**Per eliminare un gruppo di carico di lavoro utilizzando Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="7b3d4-133">**To delete a workload group by using Transact-SQL**</span></span>  
  
1.  <span data-ttu-id="7b3d4-134">Eseguire l'istruzione `DROP WORKLOAD GROUP` specificando il nome del gruppo di carico di lavoro da eliminare.</span><span class="sxs-lookup"><span data-stu-id="7b3d4-134">Run the `DROP WORKLOAD GROUP` statement specifying the name of the workload group to delete.</span></span>  
  
2.  <span data-ttu-id="7b3d4-135">Prima di eseguire l'istruzione `ALTER RESOURCE GOVERNOR RECONFIGURE`, verificare che non siano presenti richieste attive nel gruppo di carico di lavoro che viene eliminato.</span><span class="sxs-lookup"><span data-stu-id="7b3d4-135">Before you issue the `ALTER RESOURCE GOVERNOR RECONFIGURE` statement, verify that there are no active requests in the workload group being deleted.</span></span> <span data-ttu-id="7b3d4-136">Se sono presenti richieste attive, l'esecuzione dell'istruzione `ALTER RESOURCE GOVERNOR` non viene completata.</span><span class="sxs-lookup"><span data-stu-id="7b3d4-136">If there are active requests, `ALTER RESOURCE GOVERNOR` will fail.</span></span> <span data-ttu-id="7b3d4-137">Per evitare il problema, effettuare una delle azioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7b3d4-137">To avoid this issue, you can take one of the following actions:</span></span>  
  
    -   <span data-ttu-id="7b3d4-138">Attendere la disconnessione di tutte le sessioni dal gruppo del carico di lavoro.</span><span class="sxs-lookup"><span data-stu-id="7b3d4-138">Wait until all the sessions from the workload group have disconnected.</span></span>  
  
    -   <span data-ttu-id="7b3d4-139">Arrestare in modo esplicito le sessioni nel gruppo di carico di lavoro utilizzando il comando `KILL`.</span><span class="sxs-lookup"><span data-stu-id="7b3d4-139">Explicitly stop sessions in the workload group by using the `KILL` command.</span></span>  
  
    -   <span data-ttu-id="7b3d4-140">Riavviare il server.</span><span class="sxs-lookup"><span data-stu-id="7b3d4-140">Restart the server.</span></span> <span data-ttu-id="7b3d4-141">Il gruppo di carico di lavoro non verrà ricreato.</span><span class="sxs-lookup"><span data-stu-id="7b3d4-141">The workload group will not be re-created.</span></span>  
  
    -   <span data-ttu-id="7b3d4-142">In uno scenario in cui viene eseguita l'istruzione `DROP WORKLOAD GROUP` ma si decide di non arrestare in modo esplicito le sessioni per applicare la modifica, è possibile ricreare il gruppo utilizzando lo stesso nome presente prima dell'esecuzione dell'istruzione DROP, quindi spostare il gruppo nel pool di risorse originale.</span><span class="sxs-lookup"><span data-stu-id="7b3d4-142">In a scenario in which you have issued the `DROP WORKLOAD GROUP` statement but decide that you do not want to explicitly stop sessions to apply the change, you can re-create the group by using the same name that it had before you issued the DROP statement, and then move the group to the original resource pool.</span></span>  
  
3.  <span data-ttu-id="7b3d4-143">Eseguire l' `ALTER RESOURCE GOVERNOR RECONFIGURE` istruzione.</span><span class="sxs-lookup"><span data-stu-id="7b3d4-143">Run the `ALTER RESOURCE GOVERNOR RECONFIGURE` statement.</span></span>  
  
### <a name="example-transact-sql"></a><span data-ttu-id="7b3d4-144">Esempio (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="7b3d4-144">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="7b3d4-145">Nell'esempio seguente viene eliminato un gruppo di carico di lavoro denominato `groupAdhoc`.</span><span class="sxs-lookup"><span data-stu-id="7b3d4-145">The following example drops a workload group named `groupAdhoc`.</span></span>  
  
```  
DROP WORKLOAD GROUP groupAdhoc;  
GO  
ALTER RESOURCE GOVERNOR RECONFIGURE;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="7b3d4-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7b3d4-146">See Also</span></span>  
 <span data-ttu-id="7b3d4-147">[Resource Governor](resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="7b3d4-147">[Resource Governor](resource-governor.md) </span></span>  
 <span data-ttu-id="7b3d4-148">[Creare un pool di risorse](create-a-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="7b3d4-148">[Create a Resource Pool](create-a-resource-pool.md) </span></span>  
 <span data-ttu-id="7b3d4-149">[Creare un gruppo di carico di lavoro](create-a-workload-group.md) </span><span class="sxs-lookup"><span data-stu-id="7b3d4-149">[Create a Workload Group](create-a-workload-group.md) </span></span>  
 <span data-ttu-id="7b3d4-150">[Eliminare un pool di risorse](delete-a-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="7b3d4-150">[Delete a Resource Pool](delete-a-resource-pool.md) </span></span>  
 <span data-ttu-id="7b3d4-151">[DROP WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-workload-group-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7b3d4-151">[DROP WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-workload-group-transact-sql) </span></span>  
 <span data-ttu-id="7b3d4-152">[DROP RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-resource-pool-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7b3d4-152">[DROP RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-resource-pool-transact-sql) </span></span>  
 [<span data-ttu-id="7b3d4-153">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7b3d4-153">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-resource-governor-transact-sql)  
  
  
