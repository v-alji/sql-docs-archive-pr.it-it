---
title: Attributi basati su dominio (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- domain-based attributes [Master Data Services], about domain-based attributes
- domain-based attributes [Master Data Services]
- attributes [Master Data Services], domain-based attributes
ms.assetid: df6f33ff-97f6-466c-af74-9780b2247473
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 9182974923848d49ed3e9ecfb58a14949784a2c1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638426"
---
# <a name="domain-based-attributes-master-data-services"></a><span data-ttu-id="7fe82-102">Attributi basati su dominio [Master Data Services]</span><span class="sxs-lookup"><span data-stu-id="7fe82-102">Domain-Based Attributes (Master Data Services)</span></span>
  <span data-ttu-id="7fe82-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]un attributo basato su dominio è un attributo i cui valori sono popolati da membri di un'entità.</span><span class="sxs-lookup"><span data-stu-id="7fe82-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], a domain-based attribute is an attribute with values that are populated by members from another entity.</span></span> <span data-ttu-id="7fe82-104">È possibile pensare a un attributo basato su dominio come a un elenco vincolato, gli attributi basati su dominio non consentono l'immissione dei valori di attributo non validi da parte degli utenti.</span><span class="sxs-lookup"><span data-stu-id="7fe82-104">You can think of a domain-based attribute as a constrained list; domain-based attributes prevent users from entering attribute values that are not valid.</span></span> <span data-ttu-id="7fe82-105">Per selezionare un valore di attributo, l'utente deve scegliere da un elenco.</span><span class="sxs-lookup"><span data-stu-id="7fe82-105">To select an attribute value, the user must pick from a list.</span></span>

## <a name="domain-based-attribute-example"></a><span data-ttu-id="7fe82-106">Esempio di attributo basato su dominio</span><span class="sxs-lookup"><span data-stu-id="7fe82-106">Domain-Based Attribute Example</span></span>
 <span data-ttu-id="7fe82-107">Nella immagine seguente, l'entità Product dispone di un attributo basato su dominio chiamato Subcategory.</span><span class="sxs-lookup"><span data-stu-id="7fe82-107">In the following image, the Product entity has a domain-based attribute called Subcategory.</span></span> <span data-ttu-id="7fe82-108">L'attributo Subcategory viene popolato dai valori dell'entità Subcategory.</span><span class="sxs-lookup"><span data-stu-id="7fe82-108">The Subcategory attribute is populated by values from the Subcategory entity.</span></span>

 <span data-ttu-id="7fe82-109">L'entità Subcategory dispone di un attributo basato su dominio chiamato Category.</span><span class="sxs-lookup"><span data-stu-id="7fe82-109">The Subcategory entity has a domain-based attribute called Category.</span></span> <span data-ttu-id="7fe82-110">L'attributo Category viene popolato dai valori dell'entità Category.</span><span class="sxs-lookup"><span data-stu-id="7fe82-110">The Category attribute is populated by values from the Category entity.</span></span>

 <span data-ttu-id="7fe82-111">![Attributi basati su dominio in un'entità](../../2014/master-data-services/media/mds-conc-domain-based-attribute-conceptual.gif "Attributi basati su dominio in un'entità")</span><span class="sxs-lookup"><span data-stu-id="7fe82-111">![Domain-Based Attributes in an Entity](../../2014/master-data-services/media/mds-conc-domain-based-attribute-conceptual.gif "Domain-Based Attributes in an Entity")</span></span>

## <a name="use-same-entity-for-multiple-domain-based-attributes"></a><span data-ttu-id="7fe82-112">Utilizzare la stessa entità per più attributi basati su dominio</span><span class="sxs-lookup"><span data-stu-id="7fe82-112">Use Same Entity for Multiple Domain-Based Attributes</span></span>
 <span data-ttu-id="7fe82-113">È possibile utilizzare la stessa entità come un attributo basato su dominio di più entità.</span><span class="sxs-lookup"><span data-stu-id="7fe82-113">You can use the same entity as a domain-based attribute of multiple entities.</span></span> <span data-ttu-id="7fe82-114">Ad esempio, è possibile creare un'entità denominata YesNoIndicator con i membri Yes, No e Maybe.</span><span class="sxs-lookup"><span data-stu-id="7fe82-114">For example, you can create an entity called YesNoIndicator with the members: Yes, No, and Maybe.</span></span> <span data-ttu-id="7fe82-115">È possibile creare un attributo basato su dominio denominato InStock e utilizzare l'entità YesNoIndicator come origine.</span><span class="sxs-lookup"><span data-stu-id="7fe82-115">You can create a domain-based attribute named InStock and use the YesNoIndicator entity as the source.</span></span> <span data-ttu-id="7fe82-116">Inoltre è possibile creare un altro attributo basato su dominio denominato Approved e utilizzare l'entità YesNoIndicator come origine.</span><span class="sxs-lookup"><span data-stu-id="7fe82-116">You can also create another domain-based attribute named Approved and use the YesNoIndicator entity as a source.</span></span> <span data-ttu-id="7fe82-117">Ogni volta che si desidera che gli utenti scelgano da un elenco di membri dell'entità YesNoIndicator, è possibile utilizzare l'entità come attributo basato su dominio.</span><span class="sxs-lookup"><span data-stu-id="7fe82-117">Any time you want users to choose from a list of the YesNoIndicator entity's members, you can use the entity as a domain-based attribute.</span></span>

## <a name="domain-based-attributes-form-derived-hierarchies"></a><span data-ttu-id="7fe82-118">Gerarchie derivate del form degli attributi basati su dominio dedotto gerarchie</span><span class="sxs-lookup"><span data-stu-id="7fe82-118">Domain-Based Attributes Form Derived Hierarchies</span></span>
 <span data-ttu-id="7fe82-119">Le relazioni tra attributi basati su dominio costituiscono la base delle gerarchie derivate.</span><span class="sxs-lookup"><span data-stu-id="7fe82-119">Domain-based attribute relationships are the basis for derived hierarchies.</span></span> <span data-ttu-id="7fe82-120">Per altre informazioni, vedere [Gerarchie derivate &#40;Master Data Services&#41;](derived-hierarchies-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="7fe82-120">For more information, see [Derived Hierarchies &#40;Master Data Services&#41;](derived-hierarchies-master-data-services.md).</span></span>

## <a name="related-tasks"></a><span data-ttu-id="7fe82-121">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="7fe82-121">Related Tasks</span></span>

|<span data-ttu-id="7fe82-122">Descrizione dell'attività</span><span class="sxs-lookup"><span data-stu-id="7fe82-122">Task Description</span></span>|<span data-ttu-id="7fe82-123">Argomento</span><span class="sxs-lookup"><span data-stu-id="7fe82-123">Topic</span></span>|
|----------------------|-----------|
|<span data-ttu-id="7fe82-124">Creare un nuovo attributo basato su dominio originato da un'entità esistente.</span><span class="sxs-lookup"><span data-stu-id="7fe82-124">Create a new domain-based attribute that is sourced from an existing entity.</span></span>|[<span data-ttu-id="7fe82-125">Creare un attributo basato su dominio &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="7fe82-125">Create a Domain-Based Attribute &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-domain-based-attribute-master-data-services.md)|
|<span data-ttu-id="7fe82-126">Creare una nuova entità.</span><span class="sxs-lookup"><span data-stu-id="7fe82-126">Create a new entity.</span></span>|[<span data-ttu-id="7fe82-127">Creare un'entità &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="7fe82-127">Create an Entity &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-an-entity-master-data-services.md)|

## <a name="related-content"></a><span data-ttu-id="7fe82-128">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="7fe82-128">Related Content</span></span>

-   [<span data-ttu-id="7fe82-129">Gerarchie derivate &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="7fe82-129">Derived Hierarchies &#40;Master Data Services&#41;</span></span>](derived-hierarchies-master-data-services.md)

-   [<span data-ttu-id="7fe82-130">Attributi &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="7fe82-130">Attributes &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/attributes-master-data-services.md)

-   [<span data-ttu-id="7fe82-131">Entità &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="7fe82-131">Entities &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/entities-master-data-services.md)


