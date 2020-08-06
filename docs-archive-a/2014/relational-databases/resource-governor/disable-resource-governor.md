---
title: Disabilitare Resource Governor | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Resource Governor, disabling
ms.assetid: 2c2d2db0-34a5-4f50-b783-17693e3ce3f1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 172f01bdde0f792cd9ed72ad371e5811b8de8885
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715156"
---
# <a name="disable-resource-governor"></a><span data-ttu-id="721a4-102">Disabilitare Resource Governor</span><span class="sxs-lookup"><span data-stu-id="721a4-102">Disable Resource Governor</span></span>
  <span data-ttu-id="721a4-103">È possibile disabilitare Resource Governor tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="721a4-103">You can disable the Resource Governor by using either [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or Transact-SQL.</span></span>  
  
-   <span data-ttu-id="721a4-104">**Prima di iniziare:**  [Limitazioni e restrizioni](#LimitationsRestrictions), [Autorizzazioni](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="721a4-104">**Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions), [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="721a4-105">**Per disabilitare Resource Governor usando:**  [Esplora oggetti](#RGOffObjEx), [le proprietà di Resource Governor](#RGOffProp), [Transact-SQL](#RGOffTSQL)</span><span class="sxs-lookup"><span data-stu-id="721a4-105">**To disable Resource Governorn, using:**  [Object Explorer](#RGOffObjEx), [Resource Governor Properties](#RGOffProp), [Transact-SQL](#RGOffTSQL)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="721a4-106">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="721a4-106">Before You Begin</span></span>  
 <span data-ttu-id="721a4-107">La disabilitazione di Resource Governor comporta i risultati riportati di seguito:</span><span class="sxs-lookup"><span data-stu-id="721a4-107">Disabling the Resource Governor has the following results:</span></span>  
  
-   <span data-ttu-id="721a4-108">La funzione di classificazione non viene eseguita.</span><span class="sxs-lookup"><span data-stu-id="721a4-108">The classifier function is not run.</span></span>  
  
-   <span data-ttu-id="721a4-109">Tutte le nuove connessioni vengono classificate automaticamente nel gruppo di carico di lavoro predefinito.</span><span class="sxs-lookup"><span data-stu-id="721a4-109">All new connections are automatically classified into the default workload group.</span></span>  
  
-   <span data-ttu-id="721a4-110">Le richieste avviate dal sistema vengono classificate nel gruppo di carico di lavoro interno.</span><span class="sxs-lookup"><span data-stu-id="721a4-110">System-initiated requests are classified into the internal workload group.</span></span>  
  
-   <span data-ttu-id="721a4-111">Tutte le impostazioni del gruppo del carico di lavoro e del pool di risorse esistenti vengono reimpostate ai valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="721a4-111">All existing workload group and resource pool settings are reset to their default values.</span></span> <span data-ttu-id="721a4-112">In questo caso non viene generato alcun evento quando vengono raggiunti i limiti.</span><span class="sxs-lookup"><span data-stu-id="721a4-112">In this case, no events are fired when limits are reached.</span></span>  
  
-   <span data-ttu-id="721a4-113">Il normale monitoraggio del sistema non viene modificato.</span><span class="sxs-lookup"><span data-stu-id="721a4-113">Normal system monitoring is not affected.</span></span>  
  
-   <span data-ttu-id="721a4-114">Le modifiche alla configurazione non hanno effetto fino all'abilitazione di Resource Governor.</span><span class="sxs-lookup"><span data-stu-id="721a4-114">Configuration changes can be made, but the changes do not take effect until the Resource Governor is enabled.</span></span>  
  
-   <span data-ttu-id="721a4-115">Al riavvio di SQL Server, non verrà caricata la configurazione di Resource Governor, ma solo i gruppi di carico di lavoro e i pool di risorse interni e predefiniti.</span><span class="sxs-lookup"><span data-stu-id="721a4-115">Upon restarting SQL Server, the Resource Governor will not load its configuration, but instead will have only the default and internal workload groups and resource pools.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="721a4-116">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="721a4-116">Limitations and Restrictions</span></span>  
 <span data-ttu-id="721a4-117">Non è possibile utilizzare l'istruzione `ALTER RESOURCE GOVERNOR` per disabilitare Resource Governor quando in una transazione utente.</span><span class="sxs-lookup"><span data-stu-id="721a4-117">You cannot use the `ALTER RESOURCE GOVERNOR` statement to disable Resource Governor when in a user transaction.</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="721a4-118">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="721a4-118">Permissions</span></span>  
 <span data-ttu-id="721a4-119">Per disabilitare Resource Governor è necessaria l'autorizzazione CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="721a4-119">Disabling the Resource Governor requires CONTROL SERVER permission.</span></span>  
  
##  <a name="disable-resource-governor-using-object-explorer"></a><a name="RGOffObjEx"></a> <span data-ttu-id="721a4-120">Disabilitare Resource Governor utilizzando Esplora oggetti</span><span class="sxs-lookup"><span data-stu-id="721a4-120">Disable Resource Governor Using Object Explorer</span></span>  
 <span data-ttu-id="721a4-121">**Per disabilitare Resource Governor utilizzando Esplora oggetti**</span><span class="sxs-lookup"><span data-stu-id="721a4-121">**To disable the Resource Governor by using Object Explorer**</span></span>  
  
1.  <span data-ttu-id="721a4-122">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]aprire Esplora oggetti ed espandere in modo ricorsivo il nodo **Gestione** fino a **Resource Governor**.</span><span class="sxs-lookup"><span data-stu-id="721a4-122">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open Object Explorer and recursively expand the **Management** node down to **Resource Governor**.</span></span>  
  
2.  <span data-ttu-id="721a4-123">Fare clic con il pulsante destro del mouse su **Resource Governor**, quindi su **Disabilita**.</span><span class="sxs-lookup"><span data-stu-id="721a4-123">Right-click **Resource Governor**, and then click **Disable**.</span></span>  
  
##  <a name="disable-resource-governor-using-resource-governor-properties"></a><a name="RGOffProp"></a> <span data-ttu-id="721a4-124">Disabilitare Resource Governor utilizzando Proprietà di Resource Governor</span><span class="sxs-lookup"><span data-stu-id="721a4-124">Disable Resource Governor Using Resource Governor Properties</span></span>  
 <span data-ttu-id="721a4-125">**Per disabilitare Resource Governor utilizzando la pagina Proprietà di Resource Governor**</span><span class="sxs-lookup"><span data-stu-id="721a4-125">**To disable the Resource Governor by using the Resource Governor Properties page**</span></span>  
  
1.  <span data-ttu-id="721a4-126">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]aprire Esplora oggetti ed espandere in modo ricorsivo il nodo **Gestione** fino a **Resource Governor**.</span><span class="sxs-lookup"><span data-stu-id="721a4-126">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open Object Explorer and recursively expand the **Management** node down to **Resource Governor**.</span></span>  
  
2.  <span data-ttu-id="721a4-127">Fare clic con il pulsante destro del mouse su **Resource Governor** , quindi fare clic su **Proprietà**. In questo modo viene aperta la pagina **Proprietà di Resource Governor** .</span><span class="sxs-lookup"><span data-stu-id="721a4-127">Right-click **Resource Governor** and then click **Properties**, this opens the **Resource Governor Properties** page.</span></span>  
  
3.  <span data-ttu-id="721a4-128">Fare clic sulla casella di controllo **Abilita Resource Governor** , assicurarsi che la casella non sia selezionata, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="721a4-128">Click the **Enable Resource Governor** check box, ensure that the box is not selected, and then click **OK**.</span></span>  
  
##  <a name="disable-resource-governor-using-transact-sql"></a><a name="RGOffTSQL"></a> <span data-ttu-id="721a4-129">Disabilitare Resource Governor utilizzando Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="721a4-129">Disable Resource Governor Using Transact-SQL</span></span>  
 <span data-ttu-id="721a4-130">**Per disabilitare Resource Governor utilizzando Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="721a4-130">**To disable the Resource Governor by using Transact-SQL**</span></span>  
  
1.  <span data-ttu-id="721a4-131">Eseguire l'istruzione **ALTER RESOURCE GOVERNOR DISABLE** .</span><span class="sxs-lookup"><span data-stu-id="721a4-131">Run the **ALTER RESOURCE GOVERNOR DISABLE** statement.</span></span>  
  
### <a name="example-transact-sql"></a><span data-ttu-id="721a4-132">Esempio (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="721a4-132">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="721a4-133">Nell'esempio seguente viene abilitato Resource Governor.</span><span class="sxs-lookup"><span data-stu-id="721a4-133">The following example enables the Resource Governor.</span></span>  
  
```  
ALTER RESOURCE GOVERNOR DISABLE;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="721a4-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="721a4-134">See Also</span></span>  
 <span data-ttu-id="721a4-135">[Resource Governor](resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="721a4-135">[Resource Governor](resource-governor.md) </span></span>  
 <span data-ttu-id="721a4-136">[Abilitare Resource Governor](enable-resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="721a4-136">[Enable Resource Governor](enable-resource-governor.md) </span></span>  
 <span data-ttu-id="721a4-137">[Pool di risorse di Resource Governor](resource-governor-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="721a4-137">[Resource Governor Resource Pool](resource-governor-resource-pool.md) </span></span>  
 <span data-ttu-id="721a4-138">[Gruppo di carico di lavoro di Resource Governor](resource-governor-workload-group.md) </span><span class="sxs-lookup"><span data-stu-id="721a4-138">[Resource Governor Workload Group](resource-governor-workload-group.md) </span></span>  
 <span data-ttu-id="721a4-139">[Funzione di classificazione di Resource Governor](resource-governor-classifier-function.md) </span><span class="sxs-lookup"><span data-stu-id="721a4-139">[Resource Governor Classifier Function](resource-governor-classifier-function.md) </span></span>  
 [<span data-ttu-id="721a4-140">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="721a4-140">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-resource-governor-transact-sql)  
  
  
