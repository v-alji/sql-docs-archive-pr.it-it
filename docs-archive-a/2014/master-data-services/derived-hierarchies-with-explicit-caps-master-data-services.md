---
title: Gerarchie derivate con estremità esplicite (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- hierarchies [Master Data Services], derived hierarchies with explicit caps
- explicit hierarchies, derived hierarchies with explicit caps
- derived hierarchies, derived hierarchies with explicit caps
ms.assetid: 6a82ff66-c137-4757-99bb-787d189b4295
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: d2460ddf098f0547c2876dd9689f5d2bf9b461a3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625429"
---
# <a name="derived-hierarchies-with-explicit-caps-master-data-services"></a><span data-ttu-id="1b9f4-102">Gerarchie derivate con estremità esplicite (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="1b9f4-102">Derived Hierarchies with Explicit Caps (Master Data Services)</span></span>
  <span data-ttu-id="1b9f4-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], quando i livelli di una gerarchia esplicita vengono usati come livelli principali di una gerarchia derivata, questa viene chiamata gerarchia derivata con estremità esplicita.</span><span class="sxs-lookup"><span data-stu-id="1b9f4-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], when the levels from an explicit hierarchy are used as the top levels of a derived hierarchy, this is called a derived hierarchy with an explicit cap.</span></span>

 <span data-ttu-id="1b9f4-104">La gerarchia esplicita deve essere basata sulla stessa entità dell'entità al livello principale della gerarchia derivata.</span><span class="sxs-lookup"><span data-stu-id="1b9f4-104">The explicit hierarchy must be based on the same entity as the entity at the top of the derived hierarchy.</span></span>

 <span data-ttu-id="1b9f4-105">Nell'interfaccia utente di [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] , si crea questo tipo di gerarchia trascinando una gerarchia esplicita al di sopra di una gerarchia derivata.</span><span class="sxs-lookup"><span data-stu-id="1b9f4-105">In the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] user interface (UI), you create this type of hierarchy by dragging an explicit hierarchy to the top of a derived hierarchy.</span></span>

 <span data-ttu-id="1b9f4-106">![mds_conc_explicit_cap_UI_structure](../../2014/master-data-services/media/mds-conc-explicit-cap-ui-structure.gif "mds_conc_explicit_cap_UI_structure")</span><span class="sxs-lookup"><span data-stu-id="1b9f4-106">![mds_conc_explicit_cap_UI_structure](../../2014/master-data-services/media/mds-conc-explicit-cap-ui-structure.gif "mds_conc_explicit_cap_UI_structure")</span></span>

## <a name="derived-hierarchy-with-explicit-cap-example"></a><span data-ttu-id="1b9f4-107">Esempio di gerarchia derivata con estremità esplicita</span><span class="sxs-lookup"><span data-stu-id="1b9f4-107">Derived Hierarchy with Explicit Cap Example</span></span>
 <span data-ttu-id="1b9f4-108">In questo esempio, i membri nella gerarchia esplicita provengono dall'entità Subcategory.</span><span class="sxs-lookup"><span data-stu-id="1b9f4-108">In this example, the members in the explicit hierarchy are from the Subcategory entity.</span></span> <span data-ttu-id="1b9f4-109">Nella gerarchia derivata, anche i membri del livello principale provengono dall'entità Subcategory.</span><span class="sxs-lookup"><span data-stu-id="1b9f4-109">In the derived hierarchy, the top-level members are also from the Subcategory entity.</span></span>

 <span data-ttu-id="1b9f4-110">![mds_conc_explicit_cap_UI_example](../../2014/master-data-services/media/mds-conc-explicit-cap-ui-example.gif "mds_conc_explicit_cap_UI_example")</span><span class="sxs-lookup"><span data-stu-id="1b9f4-110">![mds_conc_explicit_cap_UI_example](../../2014/master-data-services/media/mds-conc-explicit-cap-ui-example.gif "mds_conc_explicit_cap_UI_example")</span></span>

 <span data-ttu-id="1b9f4-111">Posizionando la gerarchia esplicita al di sopra di una gerarchia derivata, la gerarchia derivata diventa incompleta.</span><span class="sxs-lookup"><span data-stu-id="1b9f4-111">By using the explicit hierarchy at the top of a derived hierarchy, the derived hierarchy becomes ragged.</span></span>

## <a name="rules"></a><span data-ttu-id="1b9f4-112">Regole</span><span class="sxs-lookup"><span data-stu-id="1b9f4-112">Rules</span></span>

-   <span data-ttu-id="1b9f4-113">Non è possibile avere più di una gerarchia esplicita in una gerarchia derivata con estremità esplicita.</span><span class="sxs-lookup"><span data-stu-id="1b9f4-113">You cannot have more than one explicit hierarchy in a derived hierarchy with explicit cap.</span></span>

-   <span data-ttu-id="1b9f4-114">È possibile utilizzare come estremità la stessa gerarchia esplicita per più gerarchie derivate.</span><span class="sxs-lookup"><span data-stu-id="1b9f4-114">You can use the same explicit hierarchy as a cap for multiple derived hierarchies.</span></span>

-   <span data-ttu-id="1b9f4-115">Non è possibile assegnare autorizzazioni membri gerarchia alle gerarchie derivate con estremità esplicite.</span><span class="sxs-lookup"><span data-stu-id="1b9f4-115">You cannot assign hierarchy member permissions to derived hierarchies with explicit caps.</span></span> <span data-ttu-id="1b9f4-116">Se si assegnano autorizzazioni individualmente alla gerarchia esplicita o alla gerarchia derivata, le autorizzazioni hanno effetto su entrambe le gerarchie.</span><span class="sxs-lookup"><span data-stu-id="1b9f4-116">If you assign permissions to either the explicit hierarchy or the derived hierarchy individually, the permissions affect both hierarchies.</span></span>

## <a name="related-tasks"></a><span data-ttu-id="1b9f4-117">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="1b9f4-117">Related Tasks</span></span>

|<span data-ttu-id="1b9f4-118">Descrizione dell'attività</span><span class="sxs-lookup"><span data-stu-id="1b9f4-118">Task Description</span></span>|<span data-ttu-id="1b9f4-119">Argomento</span><span class="sxs-lookup"><span data-stu-id="1b9f4-119">Topic</span></span>|
|----------------------|-----------|
|<span data-ttu-id="1b9f4-120">Creare una gerarchia derivata.</span><span class="sxs-lookup"><span data-stu-id="1b9f4-120">Create a derived hierarchy.</span></span>|[<span data-ttu-id="1b9f4-121">Creare una gerarchia derivata &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="1b9f4-121">Create a Derived Hierarchy &#40;Master Data Services&#41;</span></span>](create-a-derived-hierarchy-master-data-services.md)|
|<span data-ttu-id="1b9f4-122">Creare una gerarchia esplicita.</span><span class="sxs-lookup"><span data-stu-id="1b9f4-122">Create an explicit hierarchy.</span></span>|[<span data-ttu-id="1b9f4-123">Creare una gerarchia esplicita &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="1b9f4-123">Create an Explicit Hierarchy &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-an-explicit-hierarchy-master-data-services.md)|
|<span data-ttu-id="1b9f4-124">Eliminare una gerarchia derivata esistente.</span><span class="sxs-lookup"><span data-stu-id="1b9f4-124">Delete an existing derived hierarchy.</span></span>|[<span data-ttu-id="1b9f4-125">Eliminare una gerarchia derivata &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="1b9f4-125">Delete a Derived Hierarchy &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/delete-a-derived-hierarchy-master-data-services.md)|
|||

## <a name="related-content"></a><span data-ttu-id="1b9f4-126">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="1b9f4-126">Related Content</span></span>

-   [<span data-ttu-id="1b9f4-127">Gerarchie derivate &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="1b9f4-127">Derived Hierarchies &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/derived-hierarchies-master-data-services.md)

-   [<span data-ttu-id="1b9f4-128">Gerarchie esplicite &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="1b9f4-128">Explicit Hierarchies &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/explicit-hierarchies-master-data-services.md)


