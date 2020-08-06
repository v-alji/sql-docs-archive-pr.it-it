---
title: Gerarchie ricorsive (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- recursive hierarchies [Master Data Services]
- hierarchies [Master Data Services], recursive hierarchies
ms.assetid: 9408c6ea-d9c4-4a0b-8a1b-1457fb6944af
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 3c149d500ce1499ad36247d5e32bb6f2d55b4250
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636748"
---
# <a name="recursive-hierarchies-master-data-services"></a><span data-ttu-id="02c92-102">Gerarchie ricorsive (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="02c92-102">Recursive Hierarchies (Master Data Services)</span></span>
  <span data-ttu-id="02c92-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]una gerarchia ricorsiva è una gerarchia derivata in cui è inclusa una relazione ricorsiva.</span><span class="sxs-lookup"><span data-stu-id="02c92-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], a recursive hierarchy is a derived hierarchy that includes a recursive relationship.</span></span> <span data-ttu-id="02c92-104">Una relazione ricorsiva si verifica quando un'entità dispone di un attributo basato su dominio che si fonda sull'entità stessa.</span><span class="sxs-lookup"><span data-stu-id="02c92-104">A recursive relationship exists when an entity has a domain-based attribute based on the entity itself.</span></span>

## <a name="recursive-hierarchy-example"></a><span data-ttu-id="02c92-105">Esempio di gerarchia ricorsiva</span><span class="sxs-lookup"><span data-stu-id="02c92-105">Recursive Hierarchy Example</span></span>
 <span data-ttu-id="02c92-106">Un esempio tipico di gerarchia ricorsiva è una struttura organizzativa.</span><span class="sxs-lookup"><span data-stu-id="02c92-106">A typical recursive hierarchy example is an organizational structure.</span></span> <span data-ttu-id="02c92-107">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]questa operazione viene effettuata creando un'entità Employee con un attributo basato su dominio chiamato Manager.</span><span class="sxs-lookup"><span data-stu-id="02c92-107">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], you would do this by creating an Employee entity with a domain-based attribute called Manager.</span></span> <span data-ttu-id="02c92-108">L'attributo Manager viene popolato dall'elenco dei dipendenti.</span><span class="sxs-lookup"><span data-stu-id="02c92-108">The Manager attribute is populated from the list of employees.</span></span> <span data-ttu-id="02c92-109">Nell'organizzazione di esempio, tutti i dipendenti possono essere responsabili (Manager).</span><span class="sxs-lookup"><span data-stu-id="02c92-109">In this sample organization, all employees can be managers.</span></span>

 <span data-ttu-id="02c92-110">![mds_conc_recursive_table_w_data](../../2014/master-data-services/media/mds-conc-recursive-table-w-data.gif "mds_conc_recursive_table_w_data")</span><span class="sxs-lookup"><span data-stu-id="02c92-110">![mds_conc_recursive_table_w_data](../../2014/master-data-services/media/mds-conc-recursive-table-w-data.gif "mds_conc_recursive_table_w_data")</span></span>

 <span data-ttu-id="02c92-111">È possibile creare una gerarchia derivata che evidenzia la relazione tra l'entità Employee e l'attributo basato su dominio Manager.</span><span class="sxs-lookup"><span data-stu-id="02c92-111">You can create a derived hierarchy that highlights the relationship between the Employee entity and the Manager domain-based attribute.</span></span>

 <span data-ttu-id="02c92-112">![mds_conc_recursive_UI_structure](../../2014/master-data-services/media/mds-conc-recursive-ui-structure.gif "mds_conc_recursive_UI_structure")</span><span class="sxs-lookup"><span data-stu-id="02c92-112">![mds_conc_recursive_UI_structure](../../2014/master-data-services/media/mds-conc-recursive-ui-structure.gif "mds_conc_recursive_UI_structure")</span></span>

 <span data-ttu-id="02c92-113">Per includere ciascun membro solo una volta nella gerarchia, è possibile ancorare relazioni Null.</span><span class="sxs-lookup"><span data-stu-id="02c92-113">To include each member in the hierarchy only once, you can anchor null relationships.</span></span> <span data-ttu-id="02c92-114">Quando si fa ciò, i membri con valori di attributo basati su dominio vuoti vengono visualizzati al livello gerarchico principale.</span><span class="sxs-lookup"><span data-stu-id="02c92-114">When you do, members with blank domain-based attribute values are displayed at the top level of the hierarchy.</span></span>

 <span data-ttu-id="02c92-115">![mds_conc_recursive_UI_example_anchored](../../2014/master-data-services/media/mds-conc-recursive-ui-example-anchored.gif "mds_conc_recursive_UI_example_anchored")</span><span class="sxs-lookup"><span data-stu-id="02c92-115">![mds_conc_recursive_UI_example_anchored](../../2014/master-data-services/media/mds-conc-recursive-ui-example-anchored.gif "mds_conc_recursive_UI_example_anchored")</span></span>

 <span data-ttu-id="02c92-116">Se non si ancorano relazioni Null, i membri vengono inclusi più volte.</span><span class="sxs-lookup"><span data-stu-id="02c92-116">If you do not anchor null relationships, members are included multiple times.</span></span> <span data-ttu-id="02c92-117">Tutti i membri vengono visualizzati al livello principale.</span><span class="sxs-lookup"><span data-stu-id="02c92-117">All members are displayed at the top level.</span></span> <span data-ttu-id="02c92-118">Vengono anche visualizzati al di sotto dei membri dei quali sono attributi.</span><span class="sxs-lookup"><span data-stu-id="02c92-118">They are also displayed under members of which they are attributes.</span></span>

 <span data-ttu-id="02c92-119">![mds_conc_recursive_UI_example_nonanchored](../../2014/master-data-services/media/mds-conc-recursive-ui-example-nonanchored.gif "mds_conc_recursive_UI_example_nonanchored")</span><span class="sxs-lookup"><span data-stu-id="02c92-119">![mds_conc_recursive_UI_example_nonanchored](../../2014/master-data-services/media/mds-conc-recursive-ui-example-nonanchored.gif "mds_conc_recursive_UI_example_nonanchored")</span></span>

 <span data-ttu-id="02c92-120">In questo esempio, Marcia è al livello principale.</span><span class="sxs-lookup"><span data-stu-id="02c92-120">In this example, Marcia is at the top level.</span></span> <span data-ttu-id="02c92-121">Non è il responsabile (Manager) di alcun dipendente poiché non viene utilizzata come un valore di attributo basato su dominio per nessun altro membro definito come Employee.</span><span class="sxs-lookup"><span data-stu-id="02c92-121">She is not the manager of any employees because she is not used as a domain-based attribute value for any other Employee members.</span></span> <span data-ttu-id="02c92-122">Robert, invece, presenta un livello al di sotto di lui poiché Marcia ha Robert come suo valore dell'attributo Manager.</span><span class="sxs-lookup"><span data-stu-id="02c92-122">Robert, in contrast, has a level beneath him because Marcia has Robert as her Manager attribute value.</span></span>

## <a name="rules"></a><span data-ttu-id="02c92-123">Regole</span><span class="sxs-lookup"><span data-stu-id="02c92-123">Rules</span></span>

-   <span data-ttu-id="02c92-124">Una gerarchia derivata non può contenere più di una relazione ricorsiva.</span><span class="sxs-lookup"><span data-stu-id="02c92-124">A derived hierarchy cannot contain more than one recursive relationship.</span></span> <span data-ttu-id="02c92-125">Tuttavia, può disporre di altre relazioni derivate, ad esempio una gerarchia derivata che contiene una relazione ricorsiva da amministratore a dipendente può disporre anche delle relazioni da paese ad amministratore e da dipendente a archivia).</span><span class="sxs-lookup"><span data-stu-id="02c92-125">It can, however, have other derived relationships (for example, a derived hierarchy that contains a recursive Manager to Employee relationship can also have Country to Manager and Employee to Store relationships).</span></span>

-   <span data-ttu-id="02c92-126">Non è possibile assegnare autorizzazioni (nella scheda **Membri gerarchia** ) ai membri appartenenti a una gerarchia ricorsiva.</span><span class="sxs-lookup"><span data-stu-id="02c92-126">You cannot assign member permissions (on the **Hierarchy Members** tab) to members in a recursive hierarchy.</span></span>

-   <span data-ttu-id="02c92-127">Le gerarchie ricorsive non possono includere relazioni circolari.</span><span class="sxs-lookup"><span data-stu-id="02c92-127">Recursive hierarchies cannot include circular relationships.</span></span> <span data-ttu-id="02c92-128">Ad esempio, Katherine non può essere il responsabile (Manager) di Sandeep se Sandeep è il suo responsabile.</span><span class="sxs-lookup"><span data-stu-id="02c92-128">For example, Katherine cannot be Sandeep's manager if Sandeep is her manager.</span></span> <span data-ttu-id="02c92-129">Inoltre, Katherine non può essere il responsabile (Manager) di se stessa.</span><span class="sxs-lookup"><span data-stu-id="02c92-129">Also, Katherine cannot manage herself.</span></span>

## <a name="related-tasks"></a><span data-ttu-id="02c92-130">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="02c92-130">Related Tasks</span></span>

|<span data-ttu-id="02c92-131">Descrizione dell'attività</span><span class="sxs-lookup"><span data-stu-id="02c92-131">Task Description</span></span>|<span data-ttu-id="02c92-132">Argomento</span><span class="sxs-lookup"><span data-stu-id="02c92-132">Topic</span></span>|
|----------------------|-----------|
|<span data-ttu-id="02c92-133">Creare una gerarchia derivata.</span><span class="sxs-lookup"><span data-stu-id="02c92-133">Create a derived hierarchy.</span></span>|[<span data-ttu-id="02c92-134">Creare una gerarchia derivata &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="02c92-134">Create a Derived Hierarchy &#40;Master Data Services&#41;</span></span>](create-a-derived-hierarchy-master-data-services.md)|
|<span data-ttu-id="02c92-135">Modificare il nome di una gerarchia derivata esistente.</span><span class="sxs-lookup"><span data-stu-id="02c92-135">Change the name of an existing derived hierarchy.</span></span>|[<span data-ttu-id="02c92-136">Modificare il nome di una gerarchia derivata &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="02c92-136">Change a Derived Hierarchy Name &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/change-a-derived-hierarchy-name-master-data-services.md)|
|<span data-ttu-id="02c92-137">Eliminare una gerarchia derivata esistente.</span><span class="sxs-lookup"><span data-stu-id="02c92-137">Delete an existing derived hierarchy.</span></span>|[<span data-ttu-id="02c92-138">Eliminare una gerarchia derivata &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="02c92-138">Delete a Derived Hierarchy &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/delete-a-derived-hierarchy-master-data-services.md)|

## <a name="related-content"></a><span data-ttu-id="02c92-139">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="02c92-139">Related Content</span></span>

-   [<span data-ttu-id="02c92-140">Attributi basati su dominio &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="02c92-140">Domain-Based Attributes &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/domain-based-attributes-master-data-services.md)

-   [<span data-ttu-id="02c92-141">Gerarchie derivate &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="02c92-141">Derived Hierarchies &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/derived-hierarchies-master-data-services.md)


