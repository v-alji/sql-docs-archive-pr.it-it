---
title: Modalità di determinazione delle autorizzazioni (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- permissions [Master Data Services], determining permissions
ms.assetid: 1dc0b43a-d023-4e7d-b027-8b1459fd058c
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 3ea3306b772224bc8602659c7e17e8dc1634f0d5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629884"
---
# <a name="how-permissions-are-determined-master-data-services"></a><span data-ttu-id="22251-102">Modalità di determinazione delle autorizzazioni (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="22251-102">How Permissions Are Determined (Master Data Services)</span></span>
  <span data-ttu-id="22251-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]il modo più semplice per configurare la sicurezza consiste nell'assegnare autorizzazioni per oggetti modello a un gruppo di cui l'utente è membro.</span><span class="sxs-lookup"><span data-stu-id="22251-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], the simplest way to configure security is to assign model object permissions to a group that the user is a member of.</span></span>

 <span data-ttu-id="22251-104">La sicurezza diventa più complessa quando:</span><span class="sxs-lookup"><span data-stu-id="22251-104">Security becomes more complex when:</span></span>

-   <span data-ttu-id="22251-105">Vengono assegnate entrambe le autorizzazioni per oggetti modello e membri gerarchia.</span><span class="sxs-lookup"><span data-stu-id="22251-105">Both model object and hierarchy member permissions are assigned.</span></span>

-   <span data-ttu-id="22251-106">L'utente appartiene a gruppi e le autorizzazioni vengono assegnate sia all'utente sia ai gruppi.</span><span class="sxs-lookup"><span data-stu-id="22251-106">The user belongs to groups and permission is assigned to both the user and groups.</span></span>

-   <span data-ttu-id="22251-107">L'utente appartiene a gruppi e le autorizzazioni vengono assegnate a più gruppi.</span><span class="sxs-lookup"><span data-stu-id="22251-107">The user belongs to groups and permission is assigned to multiple groups.</span></span>

## <a name="permissions-assigned-to-a-single-group-or-user"></a><span data-ttu-id="22251-108">Autorizzazioni assegnate a un singolo gruppo o utente</span><span class="sxs-lookup"><span data-stu-id="22251-108">Permissions assigned to a single group or user</span></span>
 <span data-ttu-id="22251-109">Se vengono assegnate a un singolo gruppo o utente, le autorizzazioni vengono determinate in base al flusso di lavoro seguente.</span><span class="sxs-lookup"><span data-stu-id="22251-109">If you assign permissions to a single group or user, permissions are determined based on the following workflow.</span></span>

 <span data-ttu-id="22251-110">![mds_conc_security_no_overlap](../../2014/master-data-services/media/mds-conc-security-no-overlap.gif "mds_conc_security_no_overlap")</span><span class="sxs-lookup"><span data-stu-id="22251-110">![mds_conc_security_no_overlap](../../2014/master-data-services/media/mds-conc-security-no-overlap.gif "mds_conc_security_no_overlap")</span></span>

### <a name="step-1-effective-attribute-permissions-are-determined"></a><span data-ttu-id="22251-111">Passaggio 1: vengono determinate le autorizzazioni per attributi valide.</span><span class="sxs-lookup"><span data-stu-id="22251-111">Step 1: Effective attribute permissions are determined.</span></span>
 <span data-ttu-id="22251-112">Nell'elenco seguente viene descritto il modo in cui vengono determinate le autorizzazioni per attributi valide:</span><span class="sxs-lookup"><span data-stu-id="22251-112">The following list describes how effective attribute permissions are determined:</span></span>

-   <span data-ttu-id="22251-113">Le autorizzazioni assegnate agli oggetti modello determinano gli attributi a cui un utente può accedere.</span><span class="sxs-lookup"><span data-stu-id="22251-113">Permissions assigned to model objects determine which attributes a user can access.</span></span>

-   <span data-ttu-id="22251-114">Tutti gli oggetti modello ereditano automaticamente le autorizzazioni dall'oggetto più vicino a un livello superiore della struttura del modello.</span><span class="sxs-lookup"><span data-stu-id="22251-114">All model objects automatically inherit permission from the closest object at a higher level in the model structure.</span></span>

-   <span data-ttu-id="22251-115">Tutti gli oggetti che si trovano allo stesso livello dell'entità vengono negati in modo implicito.</span><span class="sxs-lookup"><span data-stu-id="22251-115">Any objects at the same level as the entity are implicitly denied.</span></span>

-   <span data-ttu-id="22251-116">A tutti gli oggetti che si trovano a un livello superiore viene fornito l'accesso per la navigazione.</span><span class="sxs-lookup"><span data-stu-id="22251-116">Any objects at a higher level are given navigational access.</span></span> <span data-ttu-id="22251-117">Per ulteriori informazioni sull'accesso per la navigazione, vedere [accesso &#40;Master Data Services&#41;](navigational-access-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="22251-117">For more information about navigational access, see [Navigational Access &#40;Master Data Services&#41;](navigational-access-master-data-services.md).</span></span>

 <span data-ttu-id="22251-118">In questo esempio, l'autorizzazione di sola **lettura** viene assegnata a un'entità e tale autorizzazione viene ereditata dal relativo attributo, che è a un livello inferiore della struttura del modello.</span><span class="sxs-lookup"><span data-stu-id="22251-118">In this example, **Read-only** permission is assigned to an entity and that permission is inherited by its attribute, which is at a lower level in the model structure.</span></span> <span data-ttu-id="22251-119">Il modello fornisce l'accesso per la navigazione a questa entità e al relativo attributo.</span><span class="sxs-lookup"><span data-stu-id="22251-119">The model provides navigational access to this entity and its attribute.</span></span> <span data-ttu-id="22251-120">All'altra entità del modello non viene assegnata alcuna autorizzazione esplicita e non eredita alcuna autorizzazione, pertanto viene negata in modo implicito.</span><span class="sxs-lookup"><span data-stu-id="22251-120">The other entity in the model has no explicit permission assigned and does not inherit any permissions, so it is implicitly denied.</span></span>

 <span data-ttu-id="22251-121">![mds_conc_inheritance_model](../../2014/master-data-services/media/mds-conc-inheritance-model.gif "mds_conc_inheritance_model")</span><span class="sxs-lookup"><span data-stu-id="22251-121">![mds_conc_inheritance_model](../../2014/master-data-services/media/mds-conc-inheritance-model.gif "mds_conc_inheritance_model")</span></span>

### <a name="step-2-if-hierarchy-member-permissions-are-assigned-effective-member-permissions-are-determined"></a><span data-ttu-id="22251-122">Passaggio 2: Se vengono assegnate le autorizzazioni per i membri gerarchia, vengono determinate le autorizzazioni per i membri valide.</span><span class="sxs-lookup"><span data-stu-id="22251-122">Step 2: If hierarchy member permissions are assigned, effective member permissions are determined.</span></span>
 <span data-ttu-id="22251-123">Nell'elenco seguente viene descritto il modo in cui vengono determinate le autorizzazioni per i membri gerarchia valide:</span><span class="sxs-lookup"><span data-stu-id="22251-123">The following list describes how effective hierarchy member permissions are determined:</span></span>

-   <span data-ttu-id="22251-124">Le autorizzazioni assegnate ai nodi gerarchia determinano i membri a cui un utente può accedere.</span><span class="sxs-lookup"><span data-stu-id="22251-124">Permissions assigned to hierarchy nodes determine which members a user can access.</span></span>

-   <span data-ttu-id="22251-125">Tutti i nodi di una gerarchia ereditano automaticamente le autorizzazioni dall'oggetto più vicino a un livello superiore della struttura della gerarchia.</span><span class="sxs-lookup"><span data-stu-id="22251-125">All nodes in a hierarchy automatically inherit permission from the closest object at a higher level in the hierarchy structure.</span></span>

-   <span data-ttu-id="22251-126">Tutti i nodi che si trovano allo stesso livello vengono negati in modo implicito.</span><span class="sxs-lookup"><span data-stu-id="22251-126">Any nodes at the same level are implicitly denied.</span></span>

-   <span data-ttu-id="22251-127">Tutti i nodi che si trovano a livelli superiori a cui non sono assegnate autorizzazioni vengono negati in modo implicito.</span><span class="sxs-lookup"><span data-stu-id="22251-127">Any nodes at higher levels that do not have permissions assigned are implicitly denied.</span></span>

 <span data-ttu-id="22251-128">In questo esempio, l'autorizzazione di sola **lettura** viene assegnata a un nodo della gerarchia e tale autorizzazione viene ereditata da un nodo a un livello inferiore della struttura della gerarchia.</span><span class="sxs-lookup"><span data-stu-id="22251-128">In this example, **Read-only** permission is assigned to one node of the hierarchy and that permission is inherited by a node at a lower level in the hierarchy structure.</span></span> <span data-ttu-id="22251-129">Alla radice non viene assegnata alcuna autorizzazione, pertanto viene negata in modo implicito.</span><span class="sxs-lookup"><span data-stu-id="22251-129">The root has no permission assigned, so it is implicitly denied.</span></span> <span data-ttu-id="22251-130">All'altro nodo della struttura della gerarchia non viene assegnata alcuna autorizzazione esplicita e non eredita alcuna autorizzazione, pertanto viene negato in modo implicito.</span><span class="sxs-lookup"><span data-stu-id="22251-130">The other node in the hierarchy structure has no explicit permission assigned and does not inherit any permissions, so it is implicitly denied.</span></span>

 <span data-ttu-id="22251-131">![mds_conc_inheritance_hierarchy](../../2014/master-data-services/media/mds-conc-inheritance-hierarchy.gif "mds_conc_inheritance_hierarchy")</span><span class="sxs-lookup"><span data-stu-id="22251-131">![mds_conc_inheritance_hierarchy](../../2014/master-data-services/media/mds-conc-inheritance-hierarchy.gif "mds_conc_inheritance_hierarchy")</span></span>

### <a name="step-3-the-intersection-of-attribute-and-member-permissions-is-determined"></a><span data-ttu-id="22251-132">Passaggio 3: viene determinata l'intersezione delle autorizzazioni per membri e attributi.</span><span class="sxs-lookup"><span data-stu-id="22251-132">Step 3: The intersection of attribute and member permissions is determined.</span></span>
 <span data-ttu-id="22251-133">Se le autorizzazioni per attributi valide sono diverse dalle autorizzazioni per membri valide, le autorizzazioni devono essere determinate per ogni singolo valore di attributo.</span><span class="sxs-lookup"><span data-stu-id="22251-133">If the effective attribute permissions are different than the effective member permissions, permissions must be determined for each individual attribute value.</span></span> <span data-ttu-id="22251-134">Per altre informazioni, vedere [Autorizzazioni per modelli e membri sovrapposte &#40;Master Data Services&#41;](../../2014/master-data-services/overlapping-model-and-member-permissions-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="22251-134">For more information, see [Overlapping Model and Member Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/overlapping-model-and-member-permissions-master-data-services.md).</span></span>

## <a name="permissions-assigned-to-multiple-groups"></a><span data-ttu-id="22251-135">Autorizzazioni assegnate a più gruppi</span><span class="sxs-lookup"><span data-stu-id="22251-135">Permissions assigned to multiple groups</span></span>
 <span data-ttu-id="22251-136">Se un utente appartiene uno o più gruppi e le autorizzazioni vengono assegnate sia all'utente sia ai gruppi, il flusso di lavoro diventa più complesso.</span><span class="sxs-lookup"><span data-stu-id="22251-136">If a user belongs to one or more groups and permissions are assigned to both the user and the groups, the workflow becomes more complex.</span></span>

 <span data-ttu-id="22251-137">![mds_conc_security_group_overlap](../../2014/master-data-services/media/mds-conc-security-group-overlap.gif "mds_conc_security_group_overlap")</span><span class="sxs-lookup"><span data-stu-id="22251-137">![mds_conc_security_group_overlap](../../2014/master-data-services/media/mds-conc-security-group-overlap.gif "mds_conc_security_group_overlap")</span></span>

 <span data-ttu-id="22251-138">In questo caso, la sovrapposizione delle autorizzazioni utente e gruppo deve essere risolta prima del confronto tra autorizzazioni per membri gerarchia e oggetti modello.</span><span class="sxs-lookup"><span data-stu-id="22251-138">In this case, overlapping user and group permissions must be resolved before model object and hierarchy member permissions can be compared.</span></span> <span data-ttu-id="22251-139">Per altre informazioni, vedere [Autorizzazioni utenti e gruppi sovrapposte &#40;Master Data Services&#41;](../../2014/master-data-services/overlapping-user-and-group-permissions-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="22251-139">For more information, see [Overlapping User and Group Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/overlapping-user-and-group-permissions-master-data-services.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="22251-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="22251-140">See Also</span></span>
 <span data-ttu-id="22251-141">[Autorizzazioni per utenti e gruppi sovrapposte &#40;Master Data Services&#41;](../../2014/master-data-services/overlapping-user-and-group-permissions-master-data-services.md) [autorizzazioni per modelli e membri sovrapposte &#40;Master Data Services&#41;](../../2014/master-data-services/overlapping-model-and-member-permissions-master-data-services.md)</span><span class="sxs-lookup"><span data-stu-id="22251-141">[Overlapping User and Group Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/overlapping-user-and-group-permissions-master-data-services.md) [Overlapping Model and Member Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/overlapping-model-and-member-permissions-master-data-services.md)</span></span>


