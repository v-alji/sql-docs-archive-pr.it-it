---
title: Prospettive nei modelli multidimensionali | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- default members
- hiding objects from perspective
- renaming perspectives
- attributes [Analysis Services], default members
- removing perspectives
- perspectives [Analysis Services]
- names [Analysis Services], perspectives
- cubes [Analysis Services], perspectives
- deleting perspectives
ms.assetid: 5a3d6577-6833-4c24-820c-b65bb856157b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2d4be87ddbd691710b361d8b07d225bce37659fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626356"
---
# <a name="perspectives-in-multidimensional-models"></a><span data-ttu-id="062fd-102">Prospettive nei modelli multidimensionali</span><span class="sxs-lookup"><span data-stu-id="062fd-102">Perspectives in Multidimensional Models</span></span>
  <span data-ttu-id="062fd-103">Una prospettiva è un subset di un cubo creato per una determinata applicazione o un determinato gruppo di utenti.</span><span class="sxs-lookup"><span data-stu-id="062fd-103">A perspective is a subset of a cube created for a particular application or group of users.</span></span> <span data-ttu-id="062fd-104">La prospettiva predefinita è costituita dal cubo.</span><span class="sxs-lookup"><span data-stu-id="062fd-104">The cube itself is the default perspective.</span></span> <span data-ttu-id="062fd-105">Una prospettiva viene esposta a un client come un cubo.</span><span class="sxs-lookup"><span data-stu-id="062fd-105">A perspective is exposed to a client as a cube.</span></span> <span data-ttu-id="062fd-106">Quando viene visualizzata da un utente, una prospettiva si presenta come un altro cubo.</span><span class="sxs-lookup"><span data-stu-id="062fd-106">When a user views a perspective, it appears like another cube.</span></span> <span data-ttu-id="062fd-107">Qualsiasi modifica apportata ai dati del cubo tramite writeback nella prospettiva viene apportata al cubo originale.</span><span class="sxs-lookup"><span data-stu-id="062fd-107">Any changes made to cube data through writeback in the perspective are to the original cube.</span></span> <span data-ttu-id="062fd-108">Per altre informazioni sulle viste in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [Prospettive](../multidimensional-models-olap-logical-cube-objects/perspectives.md).</span><span class="sxs-lookup"><span data-stu-id="062fd-108">For more information about the views in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], see [Perspectives](../multidimensional-models-olap-logical-cube-objects/perspectives.md).</span></span>  
  
 <span data-ttu-id="062fd-109">Usare la scheda **Prospettive** di Progettazione cubi per creare o modificare prospettive in un cubo.</span><span class="sxs-lookup"><span data-stu-id="062fd-109">Use the **Perspectives** tab in Cube Designer to create or modify perspectives in a cube.</span></span> <span data-ttu-id="062fd-110">Nella prima colonna **Oggetti cubo** della scheda **Prospettive** sono elencati tutti gli oggetti del cubo.</span><span class="sxs-lookup"><span data-stu-id="062fd-110">The first column of the **Perspectives** tab is the **Cube Objects** column, which lists all the objects in the cube.</span></span> <span data-ttu-id="062fd-111">Corrisponde alla prospettiva predefinita per il cubo, costituita dal cubo stesso.</span><span class="sxs-lookup"><span data-stu-id="062fd-111">This corresponds to the default perspective for the cube, which is the cube itself.</span></span>  
  
## <a name="creating-or-deleting-perspectives"></a><span data-ttu-id="062fd-112">Creazione o eliminazione di prospettive</span><span class="sxs-lookup"><span data-stu-id="062fd-112">Creating or Deleting Perspectives</span></span>  
 <span data-ttu-id="062fd-113">È possibile aggiungere una prospettiva alla scheda **Prospettive** scegliendo **Nuova prospettiva** dal menu **Cubo** .</span><span class="sxs-lookup"><span data-stu-id="062fd-113">You can add a perspective to the **Perspectives** tab by clicking **New Perspective** on the **Cube** menu.</span></span> <span data-ttu-id="062fd-114">È anche possibile fare clic sul pulsante **Nuova prospettiva** sulla barra degli strumenti oppure fare clic con il pulsante destro del mouse in un punto qualsiasi del riquadro e quindi scegliere **Nuova prospettiva** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="062fd-114">You can also click the **New Perspective** button on the toolbar, or right-click anywhere in the pane and click **New Perspective** on the shortcut menu.</span></span> <span data-ttu-id="062fd-115">A un cubo può essere aggiunto qualsiasi numero di prospettive.</span><span class="sxs-lookup"><span data-stu-id="062fd-115">You can add any number of perspectives to a cube.</span></span>  
  
 <span data-ttu-id="062fd-116">Per rimuovere una prospettiva, fare innanzitutto clic su qualsiasi cella della colonna per la prospettiva che si desidera eliminare.</span><span class="sxs-lookup"><span data-stu-id="062fd-116">To remove a perspective, first click any cell in the column for the perspective that you want to delete.</span></span> <span data-ttu-id="062fd-117">Scegliere quindi **Elimina prospettiva** dal menu **Cubo**.</span><span class="sxs-lookup"><span data-stu-id="062fd-117">Then, on the **Cube** menu, click **Delete Perspective**.</span></span> <span data-ttu-id="062fd-118">È anche possibile fare clic sul pulsante **Elimina prospettiva** sulla barra degli strumenti oppure fare clic con il pulsante destro del mouse su qualsiasi cella della prospettiva che si desidera eliminare e quindi scegliere **Elimina prospettiva** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="062fd-118">You can also click the **Delete Perspective** button on the toolbar, or right-click any cell in the perspective you want to delete, and then click **Delete Perspective** on the shortcut menu.</span></span>  
  
## <a name="renaming-perspectives"></a><span data-ttu-id="062fd-119">ridenominazione di prospettive</span><span class="sxs-lookup"><span data-stu-id="062fd-119">Renaming Perspectives</span></span>  
 <span data-ttu-id="062fd-120">Nella prima riga di ogni prospettiva ne viene visualizzato il nome.</span><span class="sxs-lookup"><span data-stu-id="062fd-120">The first row of each perspective shows its name.</span></span> <span data-ttu-id="062fd-121">Quando si crea una prospettiva, il nome corrisponde inizialmente a "Prospettiva", seguito da un numero ordinale a partire da 1 se è già presente una prospettiva denominata "Prospettiva".</span><span class="sxs-lookup"><span data-stu-id="062fd-121">When you create a perspective, the name is initially Perspective (followed by an ordinal number, starting with 1, if there is already a perspective called Perspective).</span></span> <span data-ttu-id="062fd-122">È possibile fare clic sul nome per modificarlo.</span><span class="sxs-lookup"><span data-stu-id="062fd-122">You can click the name to edit it.</span></span>  
  
## <a name="hiding-objects-from-a-perspective"></a><span data-ttu-id="062fd-123">Come nascondere oggetti in una prospettiva</span><span class="sxs-lookup"><span data-stu-id="062fd-123">Hiding Objects from a Perspective</span></span>  
 <span data-ttu-id="062fd-124">Per nascondere un oggetto in una prospettiva, deselezionare la casella di controllo nella riga corrispondente all'oggetto della colonna per la prospettiva.</span><span class="sxs-lookup"><span data-stu-id="062fd-124">To hide an object from a perspective, clear the check box in the row that corresponds to the object in the column for the perspective.</span></span> <span data-ttu-id="062fd-125">In una prospettiva possono essere nascosti gli oggetti del cubo seguenti:</span><span class="sxs-lookup"><span data-stu-id="062fd-125">The cube objects that can be hidden from a perspective are:</span></span>  
  
-   <span data-ttu-id="062fd-126">Gruppi di misure</span><span class="sxs-lookup"><span data-stu-id="062fd-126">Measure groups</span></span>  
  
-   <span data-ttu-id="062fd-127">Misure</span><span class="sxs-lookup"><span data-stu-id="062fd-127">Measures</span></span>  
  
-   <span data-ttu-id="062fd-128">Dimensioni</span><span class="sxs-lookup"><span data-stu-id="062fd-128">Dimensions</span></span>  
  
-   <span data-ttu-id="062fd-129">Gerarchie</span><span class="sxs-lookup"><span data-stu-id="062fd-129">Hierarchies</span></span>  
  
-   <span data-ttu-id="062fd-130">Set denominati</span><span class="sxs-lookup"><span data-stu-id="062fd-130">Named sets</span></span>  
  
-   <span data-ttu-id="062fd-131">KPI</span><span class="sxs-lookup"><span data-stu-id="062fd-131">KPIs</span></span>  
  
-   <span data-ttu-id="062fd-132">Azioni</span><span class="sxs-lookup"><span data-stu-id="062fd-132">Actions</span></span>  
  
-   <span data-ttu-id="062fd-133">Membri calcolati</span><span class="sxs-lookup"><span data-stu-id="062fd-133">Calculated members</span></span>  
  
 <span data-ttu-id="062fd-134">Per visualizzare qualsiasi oggetto, espandere la categoria (**Gruppi di misure**, **Dimensioni**, **KPI**, **Calcoli**o **Azioni**) per qualsiasi tipo di oggetto in **Oggetti cubo**.</span><span class="sxs-lookup"><span data-stu-id="062fd-134">To view any object, expand the category (**Measure Groups**, **Dimensions**, **KPIs**, **Calculations**, or **Actions**) for any object type under **Cube Objects**.</span></span> <span data-ttu-id="062fd-135">Per visualizzare le gerarchie o gli attributi di una dimensione, espandere innanzitutto una dimensione e quindi la riga **Gerarchie** o **Attributi** .</span><span class="sxs-lookup"><span data-stu-id="062fd-135">To view hierarchies or attributes in a dimension, first expand a dimension, and then expand the **Hierarchies** or **Attributes** row.</span></span> <span data-ttu-id="062fd-136">Per visualizzare le misure in un gruppo di misure, espandere il gruppo di misure.</span><span class="sxs-lookup"><span data-stu-id="062fd-136">To view measures in a measure group, expand the measure group.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="062fd-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="062fd-137">See Also</span></span>  
 [<span data-ttu-id="062fd-138">Cubi nei modelli multidimensionali</span><span class="sxs-lookup"><span data-stu-id="062fd-138">Cubes in Multidimensional Models</span></span>](cubes-in-multidimensional-models.md)  
  
  
