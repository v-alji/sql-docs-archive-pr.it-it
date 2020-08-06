---
title: Raccolte (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- collections [Master Data Services]
- collections [Master Data Services], about collections
ms.assetid: 5aa1d1e0-b4e5-4897-8e74-01dcf418df73
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: ce49c57aad5da52dabba32a0f3fb9b6f4f45b209
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715552"
---
# <a name="collections-master-data-services"></a><span data-ttu-id="78a26-102">Raccolte (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="78a26-102">Collections (Master Data Services)</span></span>
  <span data-ttu-id="78a26-103">Una raccolta è un gruppo di membri foglia e membri consolidati da una singola entità.</span><span class="sxs-lookup"><span data-stu-id="78a26-103">A collection is a group of leaf and consolidated members from a single entity.</span></span> <span data-ttu-id="78a26-104">Utilizzare le raccolte quando non è necessaria una gerarchia completa e si desidera visualizzare raggruppamenti diversi dei membri per la creazione di report o l'analisi o quando è necessario creare una tassonomia.</span><span class="sxs-lookup"><span data-stu-id="78a26-104">Use collections when you do not need a complete hierarchy and you want to view different groupings of members for reporting or analysis, or when you need to create a taxonomy.</span></span>  
  
## <a name="what-collections-contain"></a><span data-ttu-id="78a26-105">Contenuto delle raccolte</span><span class="sxs-lookup"><span data-stu-id="78a26-105">What Collections Contain</span></span>  
 <span data-ttu-id="78a26-106">Le raccolte non impongono un limite sul numero o il tipo di membri che è possibile includere, purché questi si trovino all'interno della stessa entità.</span><span class="sxs-lookup"><span data-stu-id="78a26-106">Collections do not limit the number or type of members you can include, as long as the members are within the same entity.</span></span> <span data-ttu-id="78a26-107">Una raccolta può contenere membri foglia e consolidati di più gerarchie esplicite obbligatorie e non obbligatorie.</span><span class="sxs-lookup"><span data-stu-id="78a26-107">A collection can contain leaf and consolidated members from multiple mandatory and non-mandatory explicit hierarchies.</span></span>  
  
 <span data-ttu-id="78a26-108">Quando si crea una raccolta, non si crea una struttura gerarchica, ma un elenco semplice di membri.</span><span class="sxs-lookup"><span data-stu-id="78a26-108">When you create a collection, you are not creating a hierarchical structure; you are creating a flat list of members.</span></span> <span data-ttu-id="78a26-109">Quando si seleziona un nodo da una gerarchia e lo si aggiunge alla raccolta, il membro consolidato selezionato è l'unico membro aggiunto alla raccolta.</span><span class="sxs-lookup"><span data-stu-id="78a26-109">When you select a node from a hierarchy and add it to the collection, the consolidated member you selected is the only member added to the collection.</span></span>  
  
 <span data-ttu-id="78a26-110">Una raccolta può inoltre contenere altre raccolte.</span><span class="sxs-lookup"><span data-stu-id="78a26-110">A collection can also contain other collections.</span></span> <span data-ttu-id="78a26-111">È possibile utilizzare raccolte di raccolte per creare tassonomie.</span><span class="sxs-lookup"><span data-stu-id="78a26-111">You can use collections of collections to create taxonomies.</span></span>  
  
 <span data-ttu-id="78a26-112">L'utente che crea una raccolta viene elencato automaticamente come proprietario.</span><span class="sxs-lookup"><span data-stu-id="78a26-112">When you create a collection you are automatically listed as the owner.</span></span> <span data-ttu-id="78a26-113">Gli amministratori possono creare altri attributi per la raccolta in base alle necessità.</span><span class="sxs-lookup"><span data-stu-id="78a26-113">If you are an administrator, you can create other attributes for your collection as needed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="78a26-114">Prima di creare una raccolta, è necessario abilitare l'entità per le gerarchie esplicite.</span><span class="sxs-lookup"><span data-stu-id="78a26-114">Before you can create a collection, the entity must be enabled for explicit hierarchies.</span></span> <span data-ttu-id="78a26-115">Per altre informazioni, vedere [abilitare un'entità per gerarchie esplicite e raccolte &#40;Master Data Services&#41;](enable-an-entity-for-explicit-hierarchies-and-collections-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="78a26-115">For more information, see [Enable an Entity for Explicit Hierarchies and Collections &#40;Master Data Services&#41;](enable-an-entity-for-explicit-hierarchies-and-collections-master-data-services.md).</span></span>  
  
## <a name="subscription-views-for-collections"></a><span data-ttu-id="78a26-116">Viste sottoscrizioni per le raccolte</span><span class="sxs-lookup"><span data-stu-id="78a26-116">Subscription Views for Collections</span></span>  
 <span data-ttu-id="78a26-117">Sono disponibili due tipi di viste sottoscrizioni che mostrano le raccolte.</span><span class="sxs-lookup"><span data-stu-id="78a26-117">There are two types of subscription views that show collections.</span></span> <span data-ttu-id="78a26-118">Il formato **Attributi raccolta** mostra un elenco di raccolte e degli attributi correlati alle raccolte (come descrizione o proprietario).</span><span class="sxs-lookup"><span data-stu-id="78a26-118">The **Collection attributes** format shows a list of collections and any attributes related to the collections (like description or owner).</span></span> <span data-ttu-id="78a26-119">Il formato **Raccolte** mostra tutti i membri di tutte le raccolte,, nonché il peso e l'ordinamento dei membri.</span><span class="sxs-lookup"><span data-stu-id="78a26-119">The **Collections** format shows all members in all collections, as well as each members weight and sort order.</span></span> <span data-ttu-id="78a26-120">Per ulteriori informazioni, vedere [esportazione di dati &#40;Master Data Services&#41;](overview-exporting-data-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="78a26-120">For more information, see [Exporting Data &#40;Master Data Services&#41;](overview-exporting-data-master-data-services.md).</span></span>  
  
 <span data-ttu-id="78a26-121">Se si impostano valori di peso per membri specifici di una raccolta, questi valori sono disponibili nelle viste sottoscrizioni correlate.</span><span class="sxs-lookup"><span data-stu-id="78a26-121">If you set weight values for specific members in a collection, these values are available in related subscription views.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="78a26-122">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="78a26-122">Related Tasks</span></span>  
  
|<span data-ttu-id="78a26-123">Descrizione dell'attività</span><span class="sxs-lookup"><span data-stu-id="78a26-123">Task Description</span></span>|<span data-ttu-id="78a26-124">Argomento</span><span class="sxs-lookup"><span data-stu-id="78a26-124">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="78a26-125">Abilitare un'entità per le gerarchie esplicite e le raccolte.</span><span class="sxs-lookup"><span data-stu-id="78a26-125">Enable an entity for explicit hierarchies and collections.</span></span>|[<span data-ttu-id="78a26-126">Abilitare un'entità per le gerarchie esplicite e le raccolte &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="78a26-126">Enable an Entity for Explicit Hierarchies and Collections &#40;Master Data Services&#41;</span></span>](enable-an-entity-for-explicit-hierarchies-and-collections-master-data-services.md)|  
|<span data-ttu-id="78a26-127">Creare una nuova raccolta.</span><span class="sxs-lookup"><span data-stu-id="78a26-127">Create a new collection.</span></span>|[<span data-ttu-id="78a26-128">Creare una raccolta &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="78a26-128">Create a Collection &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-collection-master-data-services.md)|  
|<span data-ttu-id="78a26-129">Aggiungere membri a una raccolta esistente.</span><span class="sxs-lookup"><span data-stu-id="78a26-129">Add members to an existing collection.</span></span>|[<span data-ttu-id="78a26-130">Aggiungere membri a una raccolta &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="78a26-130">Add Members to a Collection &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/add-members-to-a-collection-master-data-services.md)|  
  
## <a name="related-content"></a><span data-ttu-id="78a26-131">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="78a26-131">Related Content</span></span>  
  
-   [<span data-ttu-id="78a26-132">Gerarchie esplicite &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="78a26-132">Explicit Hierarchies &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/explicit-hierarchies-master-data-services.md)  
  
-   [<span data-ttu-id="78a26-133">Esportazione dei dati &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="78a26-133">Exporting Data &#40;Master Data Services&#41;</span></span>](overview-exporting-data-master-data-services.md)  
  
  
