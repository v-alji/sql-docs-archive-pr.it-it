---
title: Configurare Resource Governor usando un modello | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Resource Governor, templates
ms.assetid: f342dec2-d1d6-483e-b44e-98eb7d168b5e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 62edb23cf55a953cb0fef54f002f8eaaa16f58ec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636677"
---
# <a name="configure-resource-governor-using-a-template"></a><span data-ttu-id="e5718-102">Configurare Resource Governor utilizzando un modello</span><span class="sxs-lookup"><span data-stu-id="e5718-102">Configure Resource Governor Using a Template</span></span>
  <span data-ttu-id="e5718-103">È possibile configurare Resource Governor utilizzando un modello fornito in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e5718-103">You can configure Resource Governor by using a template that is provided in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
-   <span data-ttu-id="e5718-104">**Prima di iniziare:**  [Autorizzazioni](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="e5718-104">**Before you begin:**  [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="e5718-105">**Per creare un gruppo di carico di lavoro usando:** [un modello](#ConfRGTemplate)</span><span class="sxs-lookup"><span data-stu-id="e5718-105">**To create a workload group, using:**  [a template](#ConfRGTemplate)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="e5718-106">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="e5718-106">Before You Begin</span></span>  
 <span data-ttu-id="e5718-107">Utilizzare i seguenti passaggi per aprire e modificare un modello che consente di creare un pool di risorse e un gruppo di carico di lavoro per il pool.</span><span class="sxs-lookup"><span data-stu-id="e5718-107">Use the following steps to open and modify a template that creates a resource pool and a workload group for the pool.</span></span> <span data-ttu-id="e5718-108">Inoltre, questo modello consente di creare una funzione di classificazione definita dall'utente mediante la quale vengono indirizzate le nuove connessioni al gruppo predefinito o al gruppo di carico di lavoro creato.</span><span class="sxs-lookup"><span data-stu-id="e5718-108">In addition, this template enables you to create a classifier user-defined function that routes new connections to either the default group or the workload group that you create.</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="e5718-109">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="e5718-109">Permissions</span></span>  
 <span data-ttu-id="e5718-110">Per istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] di Resource Governor nel modello è necessaria l'autorizzazione CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="e5718-110">The resource governor [!INCLUDE[tsql](../../includes/tsql-md.md)] statements in the template require CONTROL SERVER permission.</span></span>  
  
##  <a name="configure-resource-governor-using-a-template"></a><a name="ConfRGTemplate"></a> <span data-ttu-id="e5718-111">Configurare Resource Governor utilizzando un modello</span><span class="sxs-lookup"><span data-stu-id="e5718-111">Configure Resource Governor Using a Template</span></span>  
 <span data-ttu-id="e5718-112">**Per configurare Resource Governor utilizzando un modello di [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="e5718-112">**To configure resource governor by using a template in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]**</span></span>  
  
1.  <span data-ttu-id="e5718-113">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]scegliere **Esplora modelli** dal menu **Visualizza**.</span><span class="sxs-lookup"><span data-stu-id="e5718-113">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], on the **View** menu, click **Template Explorer**.</span></span>  
  
2.  <span data-ttu-id="e5718-114">In **Esplora modelli**espandere **Resource Governor**, quindi fare doppio clic su **Configura Resource Governor**.</span><span class="sxs-lookup"><span data-stu-id="e5718-114">In **Template Explorer**, expand **Resource Governor**, and then double-click **Configure Resource Governor**.</span></span>  
  
3.  <span data-ttu-id="e5718-115">In **Connetti al Motore di database**immettere le informazioni necessarie e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="e5718-115">In **Connect to Database Engine**, enter the required information, and then click **OK**.</span></span> <span data-ttu-id="e5718-116">Il modello Configure Resource Governor.sql è disponibile nell'editor di query.</span><span class="sxs-lookup"><span data-stu-id="e5718-116">The template Configure Resource Governor.sql is provided in the Query Editor.</span></span> <span data-ttu-id="e5718-117">Utilizzare questo modello per creare e configurare un pool di risorse, un gruppo del carico di lavoro e una funzione di classificazione.</span><span class="sxs-lookup"><span data-stu-id="e5718-117">Use this template to create and configure a resource pool, a workload group, and a classifier function.</span></span>  
  
4.  <span data-ttu-id="e5718-118">Per modificare i valori del modello, premere CTRL+SHIFT+M.</span><span class="sxs-lookup"><span data-stu-id="e5718-118">To change the values in the template, press CTRL+SHIFT+M.</span></span> <span data-ttu-id="e5718-119">Nella finestra di dialogo **Imposta valori per parametri modello** immettere i valori che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="e5718-119">In the **Specify Values for Template Parameters** window, enter the values that you want to use.</span></span>  
  
5.  <span data-ttu-id="e5718-120">Per salvare le modifiche apportate al modello, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="e5718-120">To save the changes that you make to the template, click **OK**.</span></span>  
  
6.  <span data-ttu-id="e5718-121">Per eseguire la query, fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="e5718-121">To run the query, click **Execute**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5718-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e5718-122">See Also</span></span>  
 <span data-ttu-id="e5718-123">[Resource Governor](resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="e5718-123">[Resource Governor](resource-governor.md) </span></span>  
 <span data-ttu-id="e5718-124">[Abilitare Resource Governor](enable-resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="e5718-124">[Enable Resource Governor](enable-resource-governor.md) </span></span>  
 <span data-ttu-id="e5718-125">[Pool di risorse di Resource Governor](resource-governor-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="e5718-125">[Resource Governor Resource Pool](resource-governor-resource-pool.md) </span></span>  
 <span data-ttu-id="e5718-126">[Gruppo di carico di lavoro di Resource Governor](resource-governor-workload-group.md) </span><span class="sxs-lookup"><span data-stu-id="e5718-126">[Resource Governor Workload Group](resource-governor-workload-group.md) </span></span>  
 <span data-ttu-id="e5718-127">[Funzione di classificazione di Resource Governor](resource-governor-classifier-function.md) </span><span class="sxs-lookup"><span data-stu-id="e5718-127">[Resource Governor Classifier Function](resource-governor-classifier-function.md) </span></span>  
 <span data-ttu-id="e5718-128">[Visualizzare proprietà di Resource Governor](view-resource-governor-properties.md) </span><span class="sxs-lookup"><span data-stu-id="e5718-128">[View Resource Governor Properties](view-resource-governor-properties.md) </span></span>  
 <span data-ttu-id="e5718-129">[CREATE RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-resource-pool-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e5718-129">[CREATE RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-resource-pool-transact-sql) </span></span>  
 <span data-ttu-id="e5718-130">[CREATE WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-workload-group-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e5718-130">[CREATE WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-workload-group-transact-sql) </span></span>  
 <span data-ttu-id="e5718-131">[CREATE FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-function-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e5718-131">[CREATE FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-function-transact-sql) </span></span>  
 [<span data-ttu-id="e5718-132">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e5718-132">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-resource-governor-transact-sql)  
  
  
