---
title: Membri (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- leaf members [Master Data Services]
- consolidated members [Master Data Services]
- consolidated members [Master Data Services], about consolidated members
- members [Master Data Services], about members
- leaf members [Master Data Services], about leaf members
- members [Master Data Services]
ms.assetid: 0fda32b9-677d-4ba2-bb28-f76f2383a30f
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 89d2edb21b58575dffc21d9a6470171251889cc0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714496"
---
# <a name="members-master-data-services"></a><span data-ttu-id="3ece3-102">Membri (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="3ece3-102">Members (Master Data Services)</span></span>
  <span data-ttu-id="3ece3-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]i membri sono i dati master fisici.</span><span class="sxs-lookup"><span data-stu-id="3ece3-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], members are the physical master data.</span></span> <span data-ttu-id="3ece3-104">Ad esempio, un membro può essere una bicicletta Road-150 in un'entità Product o un cliente specifico in un'entità Customer.</span><span class="sxs-lookup"><span data-stu-id="3ece3-104">For example, a member can be a Road-150 bike in a Product entity or a specific customer in a Customer entity.</span></span>

## <a name="how-members-relate-to-other-model-objects"></a><span data-ttu-id="3ece3-105">Correlazione tra membri e altri oggetti modello</span><span class="sxs-lookup"><span data-stu-id="3ece3-105">How Members Relate to Other Model Objects</span></span>
 <span data-ttu-id="3ece3-106">I membri possono essere considerati come righe in una tabella.</span><span class="sxs-lookup"><span data-stu-id="3ece3-106">You can think of members as rows in a table.</span></span> <span data-ttu-id="3ece3-107">I membri correlati sono contenuti in un'entità e ogni membro è definito da valori di attributo.</span><span class="sxs-lookup"><span data-stu-id="3ece3-107">Related members are contained in an entity, and each member is defined by attribute values.</span></span>

 <span data-ttu-id="3ece3-108">In questo esempio, la tabella rappresenta un'entità, le righe della tabella rappresentano i membri e le colonne della tabella rappresentano gli attributi.</span><span class="sxs-lookup"><span data-stu-id="3ece3-108">In this example, the table represents an entity, the rows in the table represent members, and the columns in the table represent attributes.</span></span> <span data-ttu-id="3ece3-109">Ogni cella rappresenta un valore di attributo per un membro specifico.</span><span class="sxs-lookup"><span data-stu-id="3ece3-109">Each cell represents an attribute value for a specific member.</span></span>

 <span data-ttu-id="3ece3-110">![Entità Master Data Services rappresentata come tabella](../../2014/master-data-services/media/mds-conc-entity-table.gif "Entità Master Data Services rappresentata come tabella")</span><span class="sxs-lookup"><span data-stu-id="3ece3-110">![Master Data Services Entity Represented as Table](../../2014/master-data-services/media/mds-conc-entity-table.gif "Master Data Services Entity Represented as Table")</span></span>

## <a name="member-types"></a><span data-ttu-id="3ece3-111">Tipi di membri</span><span class="sxs-lookup"><span data-stu-id="3ece3-111">Member Types</span></span>
 <span data-ttu-id="3ece3-112">Sono disponibili tre tipi di membri: membri foglia, membri consolidati e membri raccolta.</span><span class="sxs-lookup"><span data-stu-id="3ece3-112">There are three types of members: leaf members, consolidated members, and collection members.</span></span>

 <span data-ttu-id="3ece3-113">I membri foglia rappresentano i membri predefiniti in un'entità.</span><span class="sxs-lookup"><span data-stu-id="3ece3-113">Leaf members are the default members in an entity.</span></span>

-   <span data-ttu-id="3ece3-114">Nelle gerarchie derivate i membri foglia sono l'unico tipo di membro.</span><span class="sxs-lookup"><span data-stu-id="3ece3-114">In derived hierarchies, leaf members are the only type of member.</span></span> <span data-ttu-id="3ece3-115">I membri foglia di un'entità vengono utilizzati come elementi padre di membri foglia di un'altra entità.</span><span class="sxs-lookup"><span data-stu-id="3ece3-115">Leaf members from one entity are used as parents of leaf members from another entity.</span></span>

-   <span data-ttu-id="3ece3-116">Nelle gerarchie esplicite i membri foglia sono il livello più basso e non possono disporre di elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="3ece3-116">In explicit hierarchies, leaf members are the lowest level and cannot have children.</span></span>

 <span data-ttu-id="3ece3-117">I membri consolidati esistono solo quando le gerarchie esplicite e le raccolte sono abilitate per l'entità.</span><span class="sxs-lookup"><span data-stu-id="3ece3-117">Consolidated members exist only when explicit hierarchies and collections are enabled for the entity.</span></span>

-   <span data-ttu-id="3ece3-118">Le gerarchie derivate non contengono membri consolidati.</span><span class="sxs-lookup"><span data-stu-id="3ece3-118">Derived hierarchies do not contain consolidated members.</span></span>

-   <span data-ttu-id="3ece3-119">Nelle gerarchie esplicite i membri consolidati possono essere elementi padre di altri membri all'interno della gerarchia o possono essere elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="3ece3-119">In explicit hierarchies, consolidated members can be parents of other members within the hierarchy, or they can be children.</span></span>

## <a name="use-hierarchies-and-collections-to-organize-members"></a><span data-ttu-id="3ece3-120">Utilizzare gerarchie e raccolte per organizzare i membri</span><span class="sxs-lookup"><span data-stu-id="3ece3-120">Use Hierarchies and Collections to Organize Members</span></span>
 <span data-ttu-id="3ece3-121">Le gerarchie e le raccolte possono essere utilizzate per raggruppare i membri per l'esecuzione di report o analisi.</span><span class="sxs-lookup"><span data-stu-id="3ece3-121">Hierarchies and collections can be used to group members for reporting or analysis.</span></span> <span data-ttu-id="3ece3-122">Per altre informazioni, vedere [Gerarchie &#40;Master Data Services&#41;](hierarchies-master-data-services.md) e [Raccolte &#40;Master Data Services&#41;](../../2014/master-data-services/collections-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="3ece3-122">For more information, see [Hierarchies &#40;Master Data Services&#41;](hierarchies-master-data-services.md) and [Collections &#40;Master Data Services&#41;](../../2014/master-data-services/collections-master-data-services.md).</span></span>

## <a name="member-example"></a><span data-ttu-id="3ece3-123">Esempio di membro</span><span class="sxs-lookup"><span data-stu-id="3ece3-123">Member Example</span></span>
 <span data-ttu-id="3ece3-124">Nell'esempio seguente ogni membro è costituito da un valore di attributo Name, Code, Subcategory StandardCost, ListPrice e FilePhoto.</span><span class="sxs-lookup"><span data-stu-id="3ece3-124">In the following example, each member is made up of a Name, Code, Subcategory, StandardCost, ListPrice, and FilePhoto attribute value.</span></span>

 <span data-ttu-id="3ece3-125">![Tabella dell'entità relativa al prodotto biciclette](../../2014/master-data-services/media/mds-conc-entity-table-w-data.gif "Tabella dell'entità relativa al prodotto biciclette")</span><span class="sxs-lookup"><span data-stu-id="3ece3-125">![Bike Product Entity Table](../../2014/master-data-services/media/mds-conc-entity-table-w-data.gif "Bike Product Entity Table")</span></span>

## <a name="related-tasks"></a><span data-ttu-id="3ece3-126">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="3ece3-126">Related Tasks</span></span>

|<span data-ttu-id="3ece3-127">Descrizione dell'attività</span><span class="sxs-lookup"><span data-stu-id="3ece3-127">Task Description</span></span>|<span data-ttu-id="3ece3-128">Argomento</span><span class="sxs-lookup"><span data-stu-id="3ece3-128">Topic</span></span>|
|----------------------|-----------|
|<span data-ttu-id="3ece3-129">Creare un nuovo membro foglia.</span><span class="sxs-lookup"><span data-stu-id="3ece3-129">Create a new leaf member.</span></span>|[<span data-ttu-id="3ece3-130">Creare un membro foglia &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="3ece3-130">Create a Leaf Member &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-leaf-member-master-data-services.md)|
|<span data-ttu-id="3ece3-131">Creare un nuovo membro consolidato.</span><span class="sxs-lookup"><span data-stu-id="3ece3-131">Create a new consolidated member.</span></span>|[<span data-ttu-id="3ece3-132">Creare membri consolidati &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="3ece3-132">Create a Consolidated Member &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-consolidated-member-master-data-services.md)|
|<span data-ttu-id="3ece3-133">Eliminare un membro o una raccolta esistente.</span><span class="sxs-lookup"><span data-stu-id="3ece3-133">Delete an existing member or collection.</span></span>|[<span data-ttu-id="3ece3-134">Eliminare un membro o una raccolta &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="3ece3-134">Delete a Member or Collection &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/delete-a-member-or-collection-master-data-services.md)|
|<span data-ttu-id="3ece3-135">Riattivare una raccolta o un membro eliminato.</span><span class="sxs-lookup"><span data-stu-id="3ece3-135">Reactivate a deleted member or collection.</span></span>|[<span data-ttu-id="3ece3-136">Riattivare un membro o una raccolta &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="3ece3-136">Reactivate a Member or Collection &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/reactivate-a-member-or-collection-master-data-services.md)|
|<span data-ttu-id="3ece3-137">Aggiornare i valori dell'attributo di un membro.</span><span class="sxs-lookup"><span data-stu-id="3ece3-137">Update the attribute values of a member.</span></span>|[<span data-ttu-id="3ece3-138">Modificare il tipo di attributo &#40;componente aggiuntivo MDS per Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="3ece3-138">Change the Attribute Type &#40;MDS Add-in for Excel&#41;</span></span>](microsoft-excel-add-in/change-the-attribute-type-mds-add-in-for-excel.md)|
|<span data-ttu-id="3ece3-139">Spostare i membri in una gerarchia.</span><span class="sxs-lookup"><span data-stu-id="3ece3-139">Move members within a hierarchy.</span></span>|[<span data-ttu-id="3ece3-140">Spostare i membri all'interno di una gerarchia &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="3ece3-140">Move Members within a Hierarchy &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/move-members-within-a-hierarchy-master-data-services.md)|

## <a name="related-content"></a><span data-ttu-id="3ece3-141">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="3ece3-141">Related Content</span></span>

-   [<span data-ttu-id="3ece3-142">Panoramica di Master Data Services</span><span class="sxs-lookup"><span data-stu-id="3ece3-142">Master Data Services Overview</span></span>](master-data-services-overview-mds.md)

-   [<span data-ttu-id="3ece3-143">Entità &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="3ece3-143">Entities &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/entities-master-data-services.md)

-   [<span data-ttu-id="3ece3-144">Attributi &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="3ece3-144">Attributes &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/attributes-master-data-services.md)

-   [<span data-ttu-id="3ece3-145">Gerarchie &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="3ece3-145">Hierarchies &#40;Master Data Services&#41;</span></span>](hierarchies-master-data-services.md)

-   [<span data-ttu-id="3ece3-146">Raccolte &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="3ece3-146">Collections &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/collections-master-data-services.md)

-   [<span data-ttu-id="3ece3-147">Autorizzazioni per elementi foglia &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="3ece3-147">Leaf Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/leaf-permissions-master-data-services.md)

-   [<span data-ttu-id="3ece3-148">Autorizzazioni consolidate &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="3ece3-148">Consolidated Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/consolidated-permissions-master-data-services.md)

-   [<span data-ttu-id="3ece3-149">Operatori di filtro &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="3ece3-149">Filter Operators &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/filter-operators-master-data-services.md)


