---
title: Gerarchie (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- hierarchies [Master Data Services]
- hierarchies [Master Data Services], about hierarchies
ms.assetid: 70dbb1fc-ead7-45be-9552-a45e3ccd8d21
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 126a01c03134c6859426c09fda398408694795f5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629888"
---
# <a name="hierarchies-master-data-services"></a><span data-ttu-id="90404-102">Gerarchie (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="90404-102">Hierarchies (Master Data Services)</span></span>
  <span data-ttu-id="90404-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]una gerarchia è una struttura ad albero che consente di effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="90404-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], a hierarchy is a tree structure that you can use to:</span></span>

-   <span data-ttu-id="90404-104">Raggruppare membri simili per scopi organizzativi.</span><span class="sxs-lookup"><span data-stu-id="90404-104">Group similar members for organizational purposes.</span></span>

-   <span data-ttu-id="90404-105">Consolidare e riepilogare membri per la creazione di report e l'analisi.</span><span class="sxs-lookup"><span data-stu-id="90404-105">Consolidate and summarize members for reporting and analysis.</span></span>

## <a name="what-hierarchies-contain"></a><span data-ttu-id="90404-106">Contenuto delle gerarchie</span><span class="sxs-lookup"><span data-stu-id="90404-106">What Hierarchies Contain</span></span>
 <span data-ttu-id="90404-107">In ogni gerarchia sono contenuti i membri di una o più entità.</span><span class="sxs-lookup"><span data-stu-id="90404-107">Each hierarchy contains members from one or more entities.</span></span> <span data-ttu-id="90404-108">Quando un membro viene aggiunto, modificato o eliminato, vengono aggiornate tutte le gerarchie.</span><span class="sxs-lookup"><span data-stu-id="90404-108">When a member is added, changed, or deleted, all hierarchies are updated.</span></span> <span data-ttu-id="90404-109">In questo modo viene garantita l'accuratezza dei dati in esse contenute.</span><span class="sxs-lookup"><span data-stu-id="90404-109">This ensures that the data is accurate in all hierarchies.</span></span> <span data-ttu-id="90404-110">Le gerarchie consentono inoltre di assicurare che ogni membro venga contato una sola volta.</span><span class="sxs-lookup"><span data-stu-id="90404-110">Hierarchies also help ensure that each member is counted once and only once.</span></span>

 <span data-ttu-id="90404-111">Se si desidera creare un raggruppamento di un subset di membri, si consideri l'utilizzo di una raccolta.</span><span class="sxs-lookup"><span data-stu-id="90404-111">If you want to create a grouping of a subset of members, consider using a collection.</span></span> <span data-ttu-id="90404-112">Per altre informazioni, vedere [Raccolte &#40;Master Data Services&#41;](collections-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="90404-112">For more information, see [Collections &#40;Master Data Services&#41;](collections-master-data-services.md).</span></span>

## <a name="kinds-of-hierarchies"></a><span data-ttu-id="90404-113">Tipi di gerarchie</span><span class="sxs-lookup"><span data-stu-id="90404-113">Kinds of Hierarchies</span></span>
 <span data-ttu-id="90404-114">È possibile creare più gerarchie per visualizzare e organizzare i membri in modi diversi.</span><span class="sxs-lookup"><span data-stu-id="90404-114">You can create multiple hierarchies to view and organize your members in different ways.</span></span> <span data-ttu-id="90404-115">È possibile creare:</span><span class="sxs-lookup"><span data-stu-id="90404-115">You can create:</span></span>

-   <span data-ttu-id="90404-116">Gerarchie incomplete da una sola entità, chiamate gerarchie esplicite.</span><span class="sxs-lookup"><span data-stu-id="90404-116">Ragged hierarchies from a single entity, which are called explicit hierarchies.</span></span> <span data-ttu-id="90404-117">Per altre informazioni, vedere [Gerarchie esplicite &#40;Master Data Services&#41;](../../2014/master-data-services/explicit-hierarchies-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="90404-117">For more information, see [Explicit Hierarchies &#40;Master Data Services&#41;](../../2014/master-data-services/explicit-hierarchies-master-data-services.md).</span></span>

-   <span data-ttu-id="90404-118">Gerarchie basate su livelli provenienti da più entità, in base alle relazioni esistenti tra le entità e i relativi attributi, chiamate gerarchie derivate.</span><span class="sxs-lookup"><span data-stu-id="90404-118">Level-based hierarchies from multiple entities, based on the existing relationships between entities and their attributes, which are called derived hierarchies.</span></span> <span data-ttu-id="90404-119">Per altre informazioni, vedere [Gerarchie derivate &#40;Master Data Services&#41;](../../2014/master-data-services/derived-hierarchies-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="90404-119">For more information, see [Derived Hierarchies &#40;Master Data Services&#41;](../../2014/master-data-services/derived-hierarchies-master-data-services.md).</span></span>

> [!NOTE]
>  <span data-ttu-id="90404-120">Tutti i membri di una gerarchia devono trovarsi all'interno dello stesso modello.</span><span class="sxs-lookup"><span data-stu-id="90404-120">All members in a hierarchy must be within the same model.</span></span>

## <a name="hierarchies-are-not-taxonomies"></a><span data-ttu-id="90404-121">Le gerarchie non sono tassonomie</span><span class="sxs-lookup"><span data-stu-id="90404-121">Hierarchies Are Not Taxonomies</span></span>
 <span data-ttu-id="90404-122">Una gerarchia è diversa da una tassonomia.</span><span class="sxs-lookup"><span data-stu-id="90404-122">A hierarchy is different from a taxonomy.</span></span> <span data-ttu-id="90404-123">In una tassonomia i membri vengono organizzati contemporaneamente in base a più attributi, mentre in una gerarchia i membri vengono organizzati in base a un attributo alla volta.</span><span class="sxs-lookup"><span data-stu-id="90404-123">A taxonomy organizes members by multiple attributes at the same time, while a hierarchy organizes members by one attribute at a time.</span></span> <span data-ttu-id="90404-124">In una tassonomia lo stesso membro può essere incluso più volte, mentre in una gerarchia può essere incluso una sola volta.</span><span class="sxs-lookup"><span data-stu-id="90404-124">A taxonomy can include the same member multiple times, while a hierarchy includes a member only once.</span></span>

 <span data-ttu-id="90404-125">Ad esempio, la stessa bicicletta può essere inclusa due volte in una tassonomia, una perché è rossa e un'altra perché ha una dimensione 38.</span><span class="sxs-lookup"><span data-stu-id="90404-125">For example, the same bike can be included in a taxonomy twice: once because it's red, and once because it's a size 38.</span></span> <span data-ttu-id="90404-126">In una gerarchia la bicicletta viene inclusa una sola volta ed è pertanto necessario decidere se visualizzarla in relazione al colore o alla dimensione.</span><span class="sxs-lookup"><span data-stu-id="90404-126">In a hierarchy, the bike is included only once, so you must decide whether to show it in relation to its color or its size.</span></span>

## <a name="hierarchy-example"></a><span data-ttu-id="90404-127">Esempio di gerarchia</span><span class="sxs-lookup"><span data-stu-id="90404-127">Hierarchy Example</span></span>
 <span data-ttu-id="90404-128">Nell'esempio seguente, i membri del prodotto vengono raggruppati in base ai membri della sottocategoria.</span><span class="sxs-lookup"><span data-stu-id="90404-128">In the following example, product members are grouped by subcategory members.</span></span>

 <span data-ttu-id="90404-129">![Esempio di gerarchia raggruppata per sottocategorie](../../2014/master-data-services/media/mds-conc-hierarchy.gif "Esempio di gerarchia raggruppata per sottocategorie")</span><span class="sxs-lookup"><span data-stu-id="90404-129">![Hierarchy Grouped by Subcategory Example](../../2014/master-data-services/media/mds-conc-hierarchy.gif "Hierarchy Grouped by Subcategory Example")</span></span>

## <a name="related-tasks"></a><span data-ttu-id="90404-130">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="90404-130">Related Tasks</span></span>

|<span data-ttu-id="90404-131">Descrizione dell'attività</span><span class="sxs-lookup"><span data-stu-id="90404-131">Task Description</span></span>|<span data-ttu-id="90404-132">Argomento</span><span class="sxs-lookup"><span data-stu-id="90404-132">Topic</span></span>|
|----------------------|-----------|
|<span data-ttu-id="90404-133">Abilitare un'entità per le gerarchie esplicite e le raccolte.</span><span class="sxs-lookup"><span data-stu-id="90404-133">Enable an entity for explicit hierarchies and collections.</span></span>|[<span data-ttu-id="90404-134">Abilitare un'entità per le gerarchie esplicite e le raccolte &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="90404-134">Enable an Entity for Explicit Hierarchies and Collections &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/enable-an-entity-for-explicit-hierarchies-and-collections-master-data-services.md)|
|<span data-ttu-id="90404-135">Creare una gerarchia esplicita.</span><span class="sxs-lookup"><span data-stu-id="90404-135">Create a explicit hierarchy.</span></span>|[<span data-ttu-id="90404-136">Creare una gerarchia esplicita &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="90404-136">Create an Explicit Hierarchy &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-an-explicit-hierarchy-master-data-services.md)|
|<span data-ttu-id="90404-137">Creare una gerarchia derivata.</span><span class="sxs-lookup"><span data-stu-id="90404-137">Create a derived hierarchy.</span></span>|[<span data-ttu-id="90404-138">Creare una gerarchia derivata &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="90404-138">Create a Derived Hierarchy &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-derived-hierarchy-master-data-services.md)|
|<span data-ttu-id="90404-139">Nascondere o eliminare i livelli in una gerarchia derivata esistente.</span><span class="sxs-lookup"><span data-stu-id="90404-139">Hide or delete levels in an existing derived hierarchy.</span></span>|[<span data-ttu-id="90404-140">Nascondere o eliminare livelli di una gerarchia derivata &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="90404-140">Hide or Delete Levels in a Derived Hierarchy &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/hide-or-delete-levels-in-a-derived-hierarchy-master-data-services.md)|

## <a name="related-content"></a><span data-ttu-id="90404-141">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="90404-141">Related Content</span></span>

-   [<span data-ttu-id="90404-142">Gerarchie esplicite &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="90404-142">Explicit Hierarchies &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/explicit-hierarchies-master-data-services.md)

-   [<span data-ttu-id="90404-143">Gerarchie derivate &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="90404-143">Derived Hierarchies &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/derived-hierarchies-master-data-services.md)

-   [<span data-ttu-id="90404-144">Gerarchie ricorsive &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="90404-144">Recursive Hierarchies &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/recursive-hierarchies-master-data-services.md)

-   [<span data-ttu-id="90404-145">Gerarchie derivate con estremità esplicite &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="90404-145">Derived Hierarchies with Explicit Caps &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/derived-hierarchies-with-explicit-caps-master-data-services.md)

-   [<span data-ttu-id="90404-146">Raccolte &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="90404-146">Collections &#40;Master Data Services&#41;</span></span>](collections-master-data-services.md)


