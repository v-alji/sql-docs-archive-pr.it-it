---
title: Abilitare Resource Governor | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Resource Governor, enabling
ms.assetid: 4d17af53-cf11-4ce4-aab4-deda94a49836
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 7b1b0f780457aa5a4d26cbb463c9f31a94185f0d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715152"
---
# <a name="enable-resource-governor"></a><span data-ttu-id="4218a-102">Abilitare Resource Governor</span><span class="sxs-lookup"><span data-stu-id="4218a-102">Enable Resource Governor</span></span>
  <span data-ttu-id="4218a-103">Resource Governor è disabilitato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="4218a-103">The Resource Governor is turned off by default.</span></span> <span data-ttu-id="4218a-104">È possibile abilitare Resource Governor tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="4218a-104">You can enable the Resource Governor by using either [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or Transact-SQL.</span></span>  
  
-   <span data-ttu-id="4218a-105">**Prima di iniziare:**  [Limitazioni e restrizioni](#LimitationsRestrictions), [Autorizzazioni](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="4218a-105">**Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions), [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="4218a-106">**Per attivare Resource Governor usando:**  [Esplora oggetti](#RGOnObjEx), [le proprietà di Resource Governor](#RGOnProp), [Transact-SQL](#RGOnTSQL)</span><span class="sxs-lookup"><span data-stu-id="4218a-106">**To enable Resource Governorn, using:**  [Object Explorer](#RGOnObjEx), [Resource Governor Properties](#RGOnProp), [Transact-SQL](#RGOnTSQL)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="4218a-107">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="4218a-107">Before You Begin</span></span>  
 <span data-ttu-id="4218a-108">L'abilitazione di Resource Governor determina i risultati riportati di seguito:</span><span class="sxs-lookup"><span data-stu-id="4218a-108">Enabling the resource governor has the following results:</span></span>  
  
-   <span data-ttu-id="4218a-109">Viene eseguita la funzione di classificazione per le nuove connessioni, in modo che i relativi carichi di lavoro possano essere assegnati ai gruppi del carico di lavoro.</span><span class="sxs-lookup"><span data-stu-id="4218a-109">The classifier function is run for new connections so that their workloads can be assigned to workload groups.</span></span>  
  
-   <span data-ttu-id="4218a-110">Vengono imposti e applicati i limiti delle risorse specificati nella configurazione di Resource Governor.</span><span class="sxs-lookup"><span data-stu-id="4218a-110">The resource limits that are specified in the Resource Governor configuration are honored and enforced.</span></span>  
  
-   <span data-ttu-id="4218a-111">Le richieste esistenti prima dell'abilitazione di Resource Governor sono interessate dalle modifiche alla configurazione effettuate quando Resource Governor è stato disabilitato.</span><span class="sxs-lookup"><span data-stu-id="4218a-111">Requests that existed before enabling Resource Governor are affected by any configuration changes that were made when the Resource Governor was disabled.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="4218a-112">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="4218a-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="4218a-113">Non è possibile utilizzare l'istruzione `ALTER RESOURCE GOVERNOR` per abilitare Resource Governor quando in una transazione utente.</span><span class="sxs-lookup"><span data-stu-id="4218a-113">You cannot use the `ALTER RESOURCE GOVERNOR` statement to enable Resource Governor when in a user transaction.</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="4218a-114">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="4218a-114">Permissions</span></span>  
 <span data-ttu-id="4218a-115">Per abilitare Resource Governor è necessaria l'autorizzazione CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="4218a-115">Enabling the Resource Governor requires CONTROL SERVER permission.</span></span>  
  
##  <a name="enable-resource-governor-using-object-explorer"></a><a name="RGOnObjEx"></a> <span data-ttu-id="4218a-116">Abilitare Resource Governor utilizzando Esplora oggetti</span><span class="sxs-lookup"><span data-stu-id="4218a-116">Enable Resource Governor Using Object Explorer</span></span>  
 <span data-ttu-id="4218a-117">**Per abilitare Resource Governor utilizzando Esplora oggetti**</span><span class="sxs-lookup"><span data-stu-id="4218a-117">**To enable the Resource Governor by using Object Explorer**</span></span>  
  
1.  <span data-ttu-id="4218a-118">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]aprire Esplora oggetti ed espandere in modo ricorsivo il nodo **Gestione** fino a **Resource Governor**.</span><span class="sxs-lookup"><span data-stu-id="4218a-118">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open Object Explorer and recursively expand the **Management** node down to **Resource Governor**.</span></span>  
  
2.  <span data-ttu-id="4218a-119">Fare clic con il pulsante destro del mouse su **Resource Governor**, quindi su **Abilita**.</span><span class="sxs-lookup"><span data-stu-id="4218a-119">Right-click **Resource Governor**, and then click **Enable**.</span></span>  
  
##  <a name="enable-resource-governor-using-resource-governor-properties"></a><a name="RGOnProp"></a> <span data-ttu-id="4218a-120">Abilitare Resource Governor utilizzando Proprietà di Resource Governor</span><span class="sxs-lookup"><span data-stu-id="4218a-120">Enable Resource Governor Using Resource Governor Properties</span></span>  
 <span data-ttu-id="4218a-121">**Per abilitare Resource Governor utilizzando la pagina Proprietà di Resource Governor**</span><span class="sxs-lookup"><span data-stu-id="4218a-121">**To enable the Resource Governor by using the Resource Governor Properties page**</span></span>  
  
1.  <span data-ttu-id="4218a-122">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]aprire Esplora oggetti ed espandere in modo ricorsivo il nodo **Gestione** fino a **Resource Governor**.</span><span class="sxs-lookup"><span data-stu-id="4218a-122">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open Object Explorer and recursively expand the **Management** node down to **Resource Governor**.</span></span>  
  
2.  <span data-ttu-id="4218a-123">Fare clic con il pulsante destro del mouse su **Resource Governor** , quindi fare clic su **Proprietà**. In questo modo viene aperta la pagina **Proprietà di Resource Governor** .</span><span class="sxs-lookup"><span data-stu-id="4218a-123">Right-click **Resource Governor** and then click **Properties**, this opens the **Resource Governor Properties** page.</span></span>  
  
3.  <span data-ttu-id="4218a-124">Fare clic sulla casella di controllo **Abilita Resource Governor** , quindi scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="4218a-124">Click the **Enable Resource Governor** check box, and then click **OK**.</span></span>  
  
##  <a name="enable-resource-governor-using-transact-sql"></a><a name="RGOnTSQL"></a> <span data-ttu-id="4218a-125">Abilitare Resource Governor utilizzando Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4218a-125">Enable Resource Governor Using Transact-SQL</span></span>  
 <span data-ttu-id="4218a-126">**Per abilitare Resource Governor utilizzando Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="4218a-126">**To enable the Resource Governor by using Transact-SQL**</span></span>  
  
1.  <span data-ttu-id="4218a-127">Eseguire l'istruzione **ALTER RESOURCE GOVERNOR RECONFIGURE** .</span><span class="sxs-lookup"><span data-stu-id="4218a-127">Run the **ALTER RESOURCE GOVERNOR RECONFIGURE** statement.</span></span>  
  
### <a name="example-transact-sql"></a><span data-ttu-id="4218a-128">Esempio (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="4218a-128">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="4218a-129">Nell'esempio seguente viene abilitato Resource Governor.</span><span class="sxs-lookup"><span data-stu-id="4218a-129">The following example enables the Resource Governor.</span></span>  
  
```  
ALTER RESOURCE GOVERNOR RECONFIGURE;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="4218a-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4218a-130">See Also</span></span>  
 <span data-ttu-id="4218a-131">[Resource Governor](resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="4218a-131">[Resource Governor](resource-governor.md) </span></span>  
 <span data-ttu-id="4218a-132">[Disabilitare Resource Governor](disable-resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="4218a-132">[Disable Resource Governor](disable-resource-governor.md) </span></span>  
 <span data-ttu-id="4218a-133">[Pool di risorse di Resource Governor](resource-governor-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="4218a-133">[Resource Governor Resource Pool](resource-governor-resource-pool.md) </span></span>  
 <span data-ttu-id="4218a-134">[Gruppo di carico di lavoro di Resource Governor](resource-governor-workload-group.md) </span><span class="sxs-lookup"><span data-stu-id="4218a-134">[Resource Governor Workload Group](resource-governor-workload-group.md) </span></span>  
 <span data-ttu-id="4218a-135">[Funzione di classificazione di Resource Governor](resource-governor-classifier-function.md) </span><span class="sxs-lookup"><span data-stu-id="4218a-135">[Resource Governor Classifier Function](resource-governor-classifier-function.md) </span></span>  
 [<span data-ttu-id="4218a-136">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4218a-136">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-resource-governor-transact-sql)  
  
  
