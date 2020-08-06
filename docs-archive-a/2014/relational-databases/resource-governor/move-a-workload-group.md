---
title: Spostare un gruppo di carico di lavoro | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
f1_keywords:
- sql12.swb.rg.properties_moveworkloadgroup.f1
helpviewer_keywords:
- workload groups [SQL Server], move
- Resource Governor, workload group move
ms.assetid: f2068636-6e53-486a-a6fc-c12de2a38424
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 7f73b48f0ec2255760b4ee55acfaf91dc02af7cd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715148"
---
# <a name="move-a-workload-group"></a><span data-ttu-id="442c1-102">Spostare un gruppo di carico di lavoro</span><span class="sxs-lookup"><span data-stu-id="442c1-102">Move a Workload Group</span></span>
  <span data-ttu-id="442c1-103">È possibile spostare un gruppo di carico di lavoro di Resource Governor in un pool di risorse diverso tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="442c1-103">You can move a Resource Governor workload group to a different resource pool by using either [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or Transact-SQL.</span></span>  
  
-   <span data-ttu-id="442c1-104">**Prima di iniziare:**  [Limitazioni e restrizioni](#LimitationsRestrictions), [Autorizzazioni](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="442c1-104">**Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions), [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="442c1-105">**Per spostare un gruppo di carico di lavoro usando:**  [SQL Server Management Studio](#MoveWGSSMS), [Transact-SQL](#MoveWGTSQL)</span><span class="sxs-lookup"><span data-stu-id="442c1-105">**To move a workload group, using:**  [SQL Server Management Studio](#MoveWGSSMS), [Transact-SQL](#MoveWGTSQL)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="442c1-106">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="442c1-106">Before You Begin</span></span>  
 <span data-ttu-id="442c1-107">Non è possibile spostare un gruppo di carico di lavoro se un'operazione di configurazione di Resource Governor è in sospeso.</span><span class="sxs-lookup"><span data-stu-id="442c1-107">You cannot move a workload group if there is a pending Resource Governor configuration operation.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="442c1-108">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="442c1-108">Limitations and Restrictions</span></span>  
 <span data-ttu-id="442c1-109">Non è possibile spostare un gruppo di carico di lavoro se un'operazione di configurazione di Resource Governor è in sospeso.</span><span class="sxs-lookup"><span data-stu-id="442c1-109">You cannot move a workload group if there is a pending Resource Governor configuration operation.</span></span> <span data-ttu-id="442c1-110">È possibile determinare se è presente una configurazione in sospeso eseguendo una query alla vista a gestione dinamica [sys.dm_resource_governor_configuration &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-resource-governor-configuration-transact-sql) per ottenere lo stato corrente di is_configuration_pending.</span><span class="sxs-lookup"><span data-stu-id="442c1-110">You can determine whether there is a configuration pending by querying the [sys.dm_resource_governor_configuration &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-resource-governor-configuration-transact-sql) dynamic management view to get the current status of is_configuration_pending.</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="442c1-111">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="442c1-111">Permissions</span></span>  
 <span data-ttu-id="442c1-112">Per spostare un gruppo di carico di lavoro è necessaria l'autorizzazione CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="442c1-112">Moving a workload group requires CONTROL SERVER permission.</span></span>  
  
##  <a name="move-a-workload-group-using-sql-server-management-studio"></a><a name="MoveWGSSMS"></a> <span data-ttu-id="442c1-113">Spostare un gruppo di carico di lavoro utilizzando SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="442c1-113">Move a Workload Group Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="442c1-114">**Per spostare un gruppo di carico di lavoro utilizzando [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="442c1-114">**To move a workload group by using [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]**</span></span>  
  
1.  <span data-ttu-id="442c1-115">In Esplora oggetti espandere in modo ricorsivo il nodo **Gestione** fino a **Resource Governor**.</span><span class="sxs-lookup"><span data-stu-id="442c1-115">In Object Explorer, recursively expand the **Management** node down to **Resource Governor**.</span></span>  
  
2.  <span data-ttu-id="442c1-116">Fare clic con il pulsante destro del mouse su **Resource Governor** , quindi fare clic su **Proprietà**. In questo modo viene aperta la pagina **Proprietà di Resource Governor** .</span><span class="sxs-lookup"><span data-stu-id="442c1-116">Right-click **Resource Governor** and then click **Properties**, this opens the **Resource Governor Properties** page.</span></span>  
  
3.  <span data-ttu-id="442c1-117">Nella finestra **Pool di risorse** fare clic sul pool di risorse contenente il gruppo di carico di lavoro da spostare.</span><span class="sxs-lookup"><span data-stu-id="442c1-117">In the **Resource Pools** window, click the resource pool containing the workload group to be moved.</span></span> <span data-ttu-id="442c1-118">Nella finestra **Gruppi del carico di lavoro** sono ora elencati i gruppi di carico di lavoro di tale pool di risorse.</span><span class="sxs-lookup"><span data-stu-id="442c1-118">The **Workload Groups** window now lists the workload groups in that resource pool.</span></span>  
  
4.  <span data-ttu-id="442c1-119">Nella finestra **Gruppi del carico di lavoro** fare clic con il pulsante destro del mouse sulla freccia a destra, a sinistra del gruppo di carico di lavoro da spostare e fare clic su **Sposta in**.</span><span class="sxs-lookup"><span data-stu-id="442c1-119">In the **Workload Groups** window, right-click the right arrow to the left of the workload group to be moved, and click **Move to**.</span></span> <span data-ttu-id="442c1-120">In questo modo viene visualizza una finestra **Sposta gruppo del carico di lavoro** .</span><span class="sxs-lookup"><span data-stu-id="442c1-120">This displays a **Move Workload Group** window.</span></span>  
  
5.  <span data-ttu-id="442c1-121">I pool di risorse disponibili sono visualizzati nella finestra.</span><span class="sxs-lookup"><span data-stu-id="442c1-121">Available resource pools are displayed in the window.</span></span> <span data-ttu-id="442c1-122">Fare clic sul nome del pool di risorse in cui si desidera spostare il gruppo di carico di lavoro, quindi fare clic su **OK** per eseguire l'operazione.</span><span class="sxs-lookup"><span data-stu-id="442c1-122">Click the name of the resource pool that you want to move the workload group to, and then click **OK** to carry out this action.</span></span>  
  
6.  <span data-ttu-id="442c1-123">Questa operazione non viene completata fino a quando non si fa clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="442c1-123">This action is not completed until after you click **OK**.</span></span> <span data-ttu-id="442c1-124">Quando si fa clic su **OK**viene eseguita l'istruzione ALTER RESOURCE GOVERNOR RECONFIGURE.</span><span class="sxs-lookup"><span data-stu-id="442c1-124">When you click **OK**, the ALTER RESOURCE GOVERNOR RECONFIGURE statement is executed.</span></span>  
  
7.  <span data-ttu-id="442c1-125">Se l'operazione di creazione o riconfigurazione del pool di risorse o gruppo di carico di lavoro non viene completata, viene visualizzato un messaggio di riepilogo degli errori sotto il titolo della pagina delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="442c1-125">If the create or reconfigure operation fails for the resource pool or workload group, a summary error message appears below the title of the property page.</span></span> <span data-ttu-id="442c1-126">Per visualizzare un messaggio di errore dettagliato, fare clic sulla freccia GIÙ sul messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="442c1-126">To see a detailed error message, click the down arrow on the error message.</span></span>  
  
##  <a name="move-a-workload-group-using-transact-sql"></a><a name="MoveWGTSQL"></a> <span data-ttu-id="442c1-127">Spostare un gruppo di carico di lavoro utilizzando Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="442c1-127">Move a Workload Group Using Transact-SQL</span></span>  
 <span data-ttu-id="442c1-128">**Per spostare un gruppo di carico di lavoro utilizzando Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="442c1-128">**To move a workload group by using Transact-SQL**</span></span>  
  
1.  <span data-ttu-id="442c1-129">Eseguire l'istruzione `ALTER WORKLOAD GROUP` specificando il nome del gruppo di carico di lavoro da spostare e il pool di risorse in cui deve essere spostato.</span><span class="sxs-lookup"><span data-stu-id="442c1-129">Run the `ALTER WORKLOAD GROUP` statement specifying the name of the workload group to be moved and the resource pool to which it should be moved.</span></span>  
  
2.  <span data-ttu-id="442c1-130">Eseguire l'istruzione **ALTER RESOURCE GOVERNOR RECONFIGURE** .</span><span class="sxs-lookup"><span data-stu-id="442c1-130">Run the **ALTER RESOURCE GOVERNOR RECONFIGURE** statement.</span></span>  
  
### <a name="example-transact-sql"></a><span data-ttu-id="442c1-131">Esempio (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="442c1-131">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="442c1-132">Nell'esempio seguente viene spostato un gruppo di carico di lavoro denominato `groupAdhoc` nel pool di risorse predefinito.</span><span class="sxs-lookup"><span data-stu-id="442c1-132">The following example moves a workload group named `groupAdhoc` to the default resource pool.</span></span>  
  
```  
ALTER WORKLOAD GROUP groupAdhoc  
USING [default];  
GO  
ALTER RESOURCE GOVERNOR RECONFIGURE;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="442c1-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="442c1-133">See Also</span></span>  
 <span data-ttu-id="442c1-134">[Resource Governor](resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="442c1-134">[Resource Governor](resource-governor.md) </span></span>  
 <span data-ttu-id="442c1-135">[Abilitare Resource Governor](enable-resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="442c1-135">[Enable Resource Governor](enable-resource-governor.md) </span></span>  
 <span data-ttu-id="442c1-136">[Creare un pool di risorse](create-a-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="442c1-136">[Create a Resource Pool](create-a-resource-pool.md) </span></span>  
 <span data-ttu-id="442c1-137">[Creare un gruppo di carico di lavoro](create-a-workload-group.md) </span><span class="sxs-lookup"><span data-stu-id="442c1-137">[Create a Workload Group](create-a-workload-group.md) </span></span>  
 <span data-ttu-id="442c1-138">[ALTER WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-workload-group-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="442c1-138">[ALTER WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-workload-group-transact-sql) </span></span>  
 [<span data-ttu-id="442c1-139">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="442c1-139">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-resource-governor-transact-sql)  
  
  
