---
title: Gerarchie esplicite (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- explicit hierarchies, about explicit hierarchies
- hierarchies [Master Data Services], explicit hierarchies
- explicit hierarchies
ms.assetid: e6f44e37-e1f0-4c38-a816-1935a856d5a4
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: f37f341dc2c003683e696f2767a6b644047d5a0a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715515"
---
# <a name="explicit-hierarchies-master-data-services"></a><span data-ttu-id="b07d3-102">Gerarchie esplicite (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="b07d3-102">Explicit Hierarchies (Master Data Services)</span></span>
  <span data-ttu-id="b07d3-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]una gerarchia esplicita consente di organizzare i membri di una sola entità secondo qualsiasi modalità specificata.</span><span class="sxs-lookup"><span data-stu-id="b07d3-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], an explicit hierarchy organizes members from a single entity in any way you specify.</span></span> <span data-ttu-id="b07d3-104">La struttura può essere incompleta e, a differenza delle gerarchie derivate, le gerarchie esplicite non sono basate su relazioni tra attributi basati su dominio.</span><span class="sxs-lookup"><span data-stu-id="b07d3-104">The structure can be ragged and unlike derived hierarchies, explicit hierarchies are not based on domain-based attribute relationships.</span></span>

## <a name="consolidated-members-group-other-members"></a><span data-ttu-id="b07d3-105">Membri consolidati che raggruppano altri membri</span><span class="sxs-lookup"><span data-stu-id="b07d3-105">Consolidated Members Group Other Members</span></span>
 <span data-ttu-id="b07d3-106">In una gerarchia esplicita vengono utilizzati membri consolidati creati allo scopo di raggruppare altri membri.</span><span class="sxs-lookup"><span data-stu-id="b07d3-106">An explicit hierarchy uses consolidated members that you create for the purpose of grouping other members.</span></span> <span data-ttu-id="b07d3-107">Questi membri consolidati possono appartenere a un'unica gerarchia esplicita per volta.</span><span class="sxs-lookup"><span data-stu-id="b07d3-107">These consolidated members can belong to only one explicit hierarchy at a time.</span></span> <span data-ttu-id="b07d3-108">Inoltre, in una gerarchia esplicita sono inclusi tutti i membri foglia dell'entità associata.</span><span class="sxs-lookup"><span data-stu-id="b07d3-108">An explicit hierarchy also includes all of the leaf members from the associated entity.</span></span>

 <span data-ttu-id="b07d3-109">Una gerarchia esplicita può essere incompleta, il che vuol dire che la gerarchia può terminare su livelli diversi simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="b07d3-109">An explicit hierarchy can be ragged, which means that the hierarchy can end at different levels simultaneously.</span></span> <span data-ttu-id="b07d3-110">Ogni membro consolidato può disporre di un numero illimitato di membri consolidati e foglia sottostanti oppure di nessuno membro.</span><span class="sxs-lookup"><span data-stu-id="b07d3-110">Each consolidated member can have an unlimited number of consolidated and leaf members underneath, or can have none.</span></span> <span data-ttu-id="b07d3-111">I membri foglia possono trovarsi al di sotto di un singolo membro consolidato o al di sotto di più livelli di membri consolidati.</span><span class="sxs-lookup"><span data-stu-id="b07d3-111">The leaf members can be under a single consolidated member or under multiple levels of consolidated members.</span></span>

> [!NOTE]
>  <span data-ttu-id="b07d3-112">Prima di creare una gerarchia esplicita, è necessario abilitare l'entità per le gerarchie esplicite.</span><span class="sxs-lookup"><span data-stu-id="b07d3-112">Before you can create an explicit hierarchy, the entity must be enabled for explicit hierarchies.</span></span> <span data-ttu-id="b07d3-113">Per altre informazioni, vedere [abilitare un'entità per gerarchie esplicite e raccolte &#40;Master Data Services&#41;](enable-an-entity-for-explicit-hierarchies-and-collections-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="b07d3-113">For more information, see [Enable an Entity for Explicit Hierarchies and Collections &#40;Master Data Services&#41;](enable-an-entity-for-explicit-hierarchies-and-collections-master-data-services.md).</span></span>

## <a name="types-of-explicit-hierarchies"></a><span data-ttu-id="b07d3-114">Tipi di gerarchie esplicite</span><span class="sxs-lookup"><span data-stu-id="b07d3-114">Types of Explicit Hierarchies</span></span>
 <span data-ttu-id="b07d3-115">Esistono due tipi di gerarchie esplicite, ovvero obbligatoria e non obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="b07d3-115">There are two types of explicit hierarchies: mandatory and non-mandatory.</span></span>

### <a name="mandatory-explicit-hierarchy"></a><span data-ttu-id="b07d3-116">Gerarchia esplicita obbligatoria</span><span class="sxs-lookup"><span data-stu-id="b07d3-116">Mandatory Explicit Hierarchy</span></span>
 <span data-ttu-id="b07d3-117">Una gerarchia esplicita obbligatoria è una gerarchia nella quale tutti i membri foglia devono essere inclusi nell'albero gerarchico.</span><span class="sxs-lookup"><span data-stu-id="b07d3-117">A mandatory explicit hierarchy is a hierarchy in which all leaf members must be included in the hierarchy tree.</span></span> <span data-ttu-id="b07d3-118">Per impostazione predefinita, tutti i membri vengono inclusi al livello radice dell'albero.</span><span class="sxs-lookup"><span data-stu-id="b07d3-118">By default, all members are included at the root of the tree.</span></span> <span data-ttu-id="b07d3-119">È possibile ridisporre i membri in base alle necessità.</span><span class="sxs-lookup"><span data-stu-id="b07d3-119">You can rearrange the members as needed.</span></span>

### <a name="non-mandatory-explicit-hierarchy"></a><span data-ttu-id="b07d3-120">Gerarchia esplicita non obbligatoria</span><span class="sxs-lookup"><span data-stu-id="b07d3-120">Non-Mandatory Explicit Hierarchy</span></span>
 <span data-ttu-id="b07d3-121">Una gerarchia esplicita non obbligatoria è una gerarchia nella quale tutti i membri foglia si trovano in un nodo **Inutilizzato** creato dal sistema.</span><span class="sxs-lookup"><span data-stu-id="b07d3-121">A non-mandatory explicit hierarchy is a hierarchy in which all leaf members are in a system-created **Unused** node.</span></span> <span data-ttu-id="b07d3-122">I membri necessari possono essere spostati fuori da questo nodo.</span><span class="sxs-lookup"><span data-stu-id="b07d3-122">You can move members out of this node as you need them.</span></span> <span data-ttu-id="b07d3-123">Il resto dei membri può rimanere nel nodo **Inutilizzato** .</span><span class="sxs-lookup"><span data-stu-id="b07d3-123">The rest of the members can remain in the **Unused** node.</span></span>

 <span data-ttu-id="b07d3-124">Quando si utilizzano gerarchie esplicite non obbligatorie, le attività di report o le analisi eseguite sulla gerarchia potrebbero non corrispondere alle attività di report o analisi eseguite su gerarchie obbligatorie.</span><span class="sxs-lookup"><span data-stu-id="b07d3-124">When you use non-mandatory explicit hierarchies, any reporting or analysis done on the hierarchy may not match reporting or analysis done on mandatory hierarchies.</span></span>

## <a name="rules"></a><span data-ttu-id="b07d3-125">Regole</span><span class="sxs-lookup"><span data-stu-id="b07d3-125">Rules</span></span>
 <span data-ttu-id="b07d3-126">Le regole seguenti si applicano alle gerarchie esplicite (obbligatorie e non obbligatorie).</span><span class="sxs-lookup"><span data-stu-id="b07d3-126">The following rules apply to explicit hierarchies (both mandatory and non-mandatory).</span></span>

-   <span data-ttu-id="b07d3-127">Ogni membro foglia può essere incluso nella gerarchia una sola volta.</span><span class="sxs-lookup"><span data-stu-id="b07d3-127">Each leaf member can be included in the hierarchy only once.</span></span>

-   <span data-ttu-id="b07d3-128">Tutti i membri consolidati devono essere inclusi in una gerarchia.</span><span class="sxs-lookup"><span data-stu-id="b07d3-128">All consolidated members must be included in a hierarchy.</span></span>

-   <span data-ttu-id="b07d3-129">I membri consolidati non possono trovarsi in più di una gerarchia esplicita.</span><span class="sxs-lookup"><span data-stu-id="b07d3-129">Consolidated members cannot be in more than one explicit hierarchy.</span></span>

-   <span data-ttu-id="b07d3-130">I membri consolidati nell'albero gerarchico non devono contenere membri foglia sottostanti.</span><span class="sxs-lookup"><span data-stu-id="b07d3-130">Consolidated members in the hierarchy tree do not have to contain leaf members underneath them.</span></span>

-   <span data-ttu-id="b07d3-131">Se si elimina una gerarchia esplicita, vengono eliminati tutti i membri consolidati utilizzati nella gerarchia.</span><span class="sxs-lookup"><span data-stu-id="b07d3-131">If you delete an explicit hierarchy, all consolidated members that were used in the hierarchy are deleted.</span></span>

-   <span data-ttu-id="b07d3-132">Se si elimina un membro consolidato incluso in una gerarchia esplicita, tutti i membri foglia raggruppati in base a tale membro consolidato vengono spostati al livello radice.</span><span class="sxs-lookup"><span data-stu-id="b07d3-132">If you delete a consolidated member that was in an explicit hierarchy, all leaf members that were grouped by that consolidated member are moved to the root.</span></span>

## <a name="explicit-hierarchies-versus-derived-hierarchies"></a><span data-ttu-id="b07d3-133">Gerarchie esplicite e gerarchie derivate</span><span class="sxs-lookup"><span data-stu-id="b07d3-133">Explicit Hierarchies versus Derived Hierarchies</span></span>
 <span data-ttu-id="b07d3-134">Nella tabella seguente vengono illustrate alcune differenze tra le gerarchie esplicite e derivate.</span><span class="sxs-lookup"><span data-stu-id="b07d3-134">The following table shows some of the differences between explicit and derived hierarchies.</span></span>

|<span data-ttu-id="b07d3-135">Gerarchie esplicite</span><span class="sxs-lookup"><span data-stu-id="b07d3-135">Explicit Hierarchies</span></span>|<span data-ttu-id="b07d3-136">Gerarchie derivate</span><span class="sxs-lookup"><span data-stu-id="b07d3-136">Derived Hierarchies</span></span>|
|--------------------------|-------------------------|
|<span data-ttu-id="b07d3-137">La struttura viene definita dall'utente</span><span class="sxs-lookup"><span data-stu-id="b07d3-137">Structure is defined by the user</span></span>|<span data-ttu-id="b07d3-138">La struttura è derivata dalle relazioni tra attributi basati su dominio</span><span class="sxs-lookup"><span data-stu-id="b07d3-138">Structure is derived from the relationships between domain-based attributes</span></span>|
|<span data-ttu-id="b07d3-139">Contengono membri di una sola entità</span><span class="sxs-lookup"><span data-stu-id="b07d3-139">Contains members from a single entity</span></span>|<span data-ttu-id="b07d3-140">Contengono membri di più entità</span><span class="sxs-lookup"><span data-stu-id="b07d3-140">Contains members from multiple entities</span></span>|
|<span data-ttu-id="b07d3-141">Utilizzano i membri consolidati per raggruppare altri membri</span><span class="sxs-lookup"><span data-stu-id="b07d3-141">Uses consolidated members to group other members</span></span>|<span data-ttu-id="b07d3-142">Utilizzano i membri foglia di un'entità per raggruppare i membri foglia di un'altra entità</span><span class="sxs-lookup"><span data-stu-id="b07d3-142">Uses leaf members from one entity to group leaf members from another entity</span></span>|
|<span data-ttu-id="b07d3-143">Possono essere incomplete</span><span class="sxs-lookup"><span data-stu-id="b07d3-143">Can be ragged</span></span>|<span data-ttu-id="b07d3-144">Contengono sempre un numero coerente di livelli</span><span class="sxs-lookup"><span data-stu-id="b07d3-144">Always contains a consistent number of levels</span></span>|

## <a name="explicit-hierarchy-example"></a><span data-ttu-id="b07d3-145">Esempio di gerarchia esplicita</span><span class="sxs-lookup"><span data-stu-id="b07d3-145">Explicit Hierarchy Example</span></span>
 <span data-ttu-id="b07d3-146">Nell'esempio seguente, l'entità Product contiene i seguenti membri foglia: BK-M101 {Mountain-100}, BK-M201 {Mountain-200}, BK-M301 {Mountain-300}, BK-R150 {Road-150}, BK-R450 {Road-450} e BK-R650 {Road-650}.</span><span class="sxs-lookup"><span data-stu-id="b07d3-146">In the following example, the Product entity contains these leaf members: BK-M101 {Mountain-100}, BK-M201 {Mountain-200}, BK-M301 {Mountain-300}, BK-R150 {Road-150}, BK-R450 {Road-450}, and BK-R650 {Road-650}.</span></span>

 <span data-ttu-id="b07d3-147">Per riepilogare i membri foglia in corrispondenza di punti di consolidamento specifici, è possibile creare membri consolidati nell'entità Product.</span><span class="sxs-lookup"><span data-stu-id="b07d3-147">To summarize these leaf members at specific consolidation points, you can create consolidated members in the Product entity.</span></span> <span data-ttu-id="b07d3-148">Inserire i membri consolidati nei livelli dell'albero gerarchico nel punto in cui si desidera riepilogare i membri foglia.</span><span class="sxs-lookup"><span data-stu-id="b07d3-148">Insert the consolidated members at levels in the hierarchy tree where you want to summarize the leaf members.</span></span> <span data-ttu-id="b07d3-149">Non sussistono limitazioni rispetto al punto di inserimento dei membri consolidati. Ogni membro (foglia o consolidato) può tuttavia essere utilizzato una sola volta.</span><span class="sxs-lookup"><span data-stu-id="b07d3-149">There is no limitation on where you insert your consolidated members; however, each member (leaf or consolidated) can be used only once.</span></span>

 <span data-ttu-id="b07d3-150">![Esempio di gerarchia esplicita di mountain bike](../../2014/master-data-services/media/mds-conc-explicit-hierarchy.gif "Esempio di gerarchia esplicita di mountain bike")</span><span class="sxs-lookup"><span data-stu-id="b07d3-150">![Mountain Bike Explicit Hierarchy Example](../../2014/master-data-services/media/mds-conc-explicit-hierarchy.gif "Mountain Bike Explicit Hierarchy Example")</span></span>

 <span data-ttu-id="b07d3-151">I membri consolidati possono essere utilizzati per raggruppare membri a qualsiasi livello e i membri consolidati vengono ordinati nell'ordine determinato dall'utente.</span><span class="sxs-lookup"><span data-stu-id="b07d3-151">Consolidated members can be used to group members at any level, and leaf and consolidated members are sorted in the order you determine.</span></span>

## <a name="related-tasks"></a><span data-ttu-id="b07d3-152">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="b07d3-152">Related Tasks</span></span>

|<span data-ttu-id="b07d3-153">Descrizione dell'attività</span><span class="sxs-lookup"><span data-stu-id="b07d3-153">Task Description</span></span>|<span data-ttu-id="b07d3-154">Argomento</span><span class="sxs-lookup"><span data-stu-id="b07d3-154">Topic</span></span>|
|----------------------|-----------|
|<span data-ttu-id="b07d3-155">Abilitare un'entità per le gerarchie esplicite e le raccolte.</span><span class="sxs-lookup"><span data-stu-id="b07d3-155">Enable an entity for explicit hierarchies and collections.</span></span>|[<span data-ttu-id="b07d3-156">Abilitare un'entità per le gerarchie esplicite e le raccolte &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="b07d3-156">Enable an Entity for Explicit Hierarchies and Collections &#40;Master Data Services&#41;</span></span>](enable-an-entity-for-explicit-hierarchies-and-collections-master-data-services.md)|
|<span data-ttu-id="b07d3-157">Creare una nuova gerarchia esplicita.</span><span class="sxs-lookup"><span data-stu-id="b07d3-157">Create a new explicit hierarchy.</span></span>|[<span data-ttu-id="b07d3-158">Creare una gerarchia esplicita &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="b07d3-158">Create an Explicit Hierarchy &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-an-explicit-hierarchy-master-data-services.md)|
|<span data-ttu-id="b07d3-159">Modificare il nome di una gerarchia esplicita esistente.</span><span class="sxs-lookup"><span data-stu-id="b07d3-159">Change the name of an existing explicity hierarchy.</span></span>|[<span data-ttu-id="b07d3-160">Modificare il nome di una gerarchia esplicita &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="b07d3-160">Change an Explicit Hierarchy Name &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/change-an-explicit-hierarchy-name-master-data-services.md)|
|<span data-ttu-id="b07d3-161">Eliminare una gerarchia esplicita esistente.</span><span class="sxs-lookup"><span data-stu-id="b07d3-161">Delete an existing explicit hierarchy.</span></span>|[<span data-ttu-id="b07d3-162">Eliminare una gerarchia esplicita &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="b07d3-162">Delete an Explicit Hierarchy &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/delete-an-explicit-hierarchy-master-data-services.md)|
|||

## <a name="related-content"></a><span data-ttu-id="b07d3-163">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="b07d3-163">Related Content</span></span>

-   [<span data-ttu-id="b07d3-164">Gerarchie derivate &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="b07d3-164">Derived Hierarchies &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/derived-hierarchies-master-data-services.md)

-   [<span data-ttu-id="b07d3-165">Raccolte &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="b07d3-165">Collections &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/collections-master-data-services.md)


