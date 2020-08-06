---
title: Autorizzazioni per elementi foglia (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- attribute groups [Master Data Services], permissions
- members [Master Data Services], leaf member permissions
- permissions [Master Data Services], leaf members
- leaf members [Master Data Services], attribute permissions
- attributes [Master Data Services], leaf member attribute permissions
ms.assetid: bde16e8c-bcd4-4041-8130-55c5450e5f72
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 794e1d138b91e896b8df16765ae8984c6e60aca7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722871"
---
# <a name="leaf-permissions-master-data-services"></a><span data-ttu-id="280b8-102">Autorizzazioni per elementi foglia (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="280b8-102">Leaf Permissions (Master Data Services)</span></span>
  <span data-ttu-id="280b8-103">Le autorizzazioni foglia si applicano ai valori di attributo per tutti i membri foglia di un'entità.</span><span class="sxs-lookup"><span data-stu-id="280b8-103">Leaf permissions apply to the attribute values for all leaf members of an entity.</span></span>  
  
 <span data-ttu-id="280b8-104">Per le entità senza gerarchie esplicite abilitate, l'assegnazione delle autorizzazioni all'elemento **Foglia** equivale all'assegnazione delle autorizzazioni all'entità.</span><span class="sxs-lookup"><span data-stu-id="280b8-104">For entities without explicit hierarchies enabled, assigning permission to **Leaf** is the same as assigning permission to the entity.</span></span>  
  
 <span data-ttu-id="280b8-105">**Note:**</span><span class="sxs-lookup"><span data-stu-id="280b8-105">**Notes:**</span></span>  
  
-   <span data-ttu-id="280b8-106">Le autorizzazioni foglia si applicano solo all'area funzionale **Visualizzatore** dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="280b8-106">Leaf permissions apply to the **Explorer** functional area of the user interface only.</span></span>  
  
-   <span data-ttu-id="280b8-107">Le autorizzazioni assegnate agli attributi **Name** e **Code** non sono applicate.</span><span class="sxs-lookup"><span data-stu-id="280b8-107">Permissions assigned to **Name** and **Code** attributes are not enforced.</span></span>  
  
|<span data-ttu-id="280b8-108">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="280b8-108">Permission</span></span>|<span data-ttu-id="280b8-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="280b8-109">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="280b8-110">**Sola lettura**</span><span class="sxs-lookup"><span data-stu-id="280b8-110">**Read-only**</span></span>|<span data-ttu-id="280b8-111">I membri foglia vengono visualizzati, ma l'utente non può aggiungerli, rimuoverli o modificarli.</span><span class="sxs-lookup"><span data-stu-id="280b8-111">Leaf members are displayed but the user cannot add, remove, or change them.</span></span><br /><br /> <span data-ttu-id="280b8-112">Se esistono membri consolidati, i nomi e i codici vengono visualizzati, ma l'utente non può aggiungerli, rimuoverli o modificarli.</span><span class="sxs-lookup"><span data-stu-id="280b8-112">If consolidated members exist, the names and codes are displayed but the user cannot add, remove, or change them.</span></span>|  
|<span data-ttu-id="280b8-113">**Aggiornamento**</span><span class="sxs-lookup"><span data-stu-id="280b8-113">**Update**</span></span>|<span data-ttu-id="280b8-114">I membri foglia vengono visualizzati e l'utente può aggiungerli, rimuoverli e modificarli.</span><span class="sxs-lookup"><span data-stu-id="280b8-114">Leaf members are displayed and the user can add, remove, and change them.</span></span><br /><br /> <span data-ttu-id="280b8-115">Se esistono membri consolidati, i nomi e i codici vengono visualizzati, ma l'utente non può aggiungerli, rimuoverli o modificarli.</span><span class="sxs-lookup"><span data-stu-id="280b8-115">If consolidated members exist, the names and codes are displayed but the user cannot add, remove, or change them.</span></span>|  
|<span data-ttu-id="280b8-116">**Nega**</span><span class="sxs-lookup"><span data-stu-id="280b8-116">**Deny**</span></span>|<span data-ttu-id="280b8-117">I membri foglia per l'entità non vengono visualizzati.</span><span class="sxs-lookup"><span data-stu-id="280b8-117">Leaf members for the entity are not displayed.</span></span>|  
  
## <a name="attribute-permissions"></a><span data-ttu-id="280b8-118">Autorizzazioni per attributi</span><span class="sxs-lookup"><span data-stu-id="280b8-118">Attribute Permissions</span></span>  
 <span data-ttu-id="280b8-119">Le autorizzazioni per gli attributi si applicano ai valori degli attributi per l'entità specifica.</span><span class="sxs-lookup"><span data-stu-id="280b8-119">Attribute permissions apply to the attribute's values for the specific entity.</span></span> <span data-ttu-id="280b8-120">Gli utenti che dispongono solo delle autorizzazioni per gli attributi non possono aggiungere o rimuovere membri.</span><span class="sxs-lookup"><span data-stu-id="280b8-120">Users with attribute permissions only cannot add or remove members.</span></span>  
  
|<span data-ttu-id="280b8-121">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="280b8-121">Permission</span></span>|<span data-ttu-id="280b8-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="280b8-122">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="280b8-123">**Sola lettura**</span><span class="sxs-lookup"><span data-stu-id="280b8-123">**Read-only**</span></span>|<span data-ttu-id="280b8-124">L'attributo viene visualizzato, ma l'utente non può modificare i valori di attributo.</span><span class="sxs-lookup"><span data-stu-id="280b8-124">The attribute is displayed but the user cannot change attribute values.</span></span>|  
|<span data-ttu-id="280b8-125">**Aggiornamento**</span><span class="sxs-lookup"><span data-stu-id="280b8-125">**Update**</span></span>|<span data-ttu-id="280b8-126">L'attributo viene visualizzato e l'utente può modificare i valori di attributo.</span><span class="sxs-lookup"><span data-stu-id="280b8-126">The attribute is displayed and the user can change attribute values.</span></span>|  
|<span data-ttu-id="280b8-127">**Nega**</span><span class="sxs-lookup"><span data-stu-id="280b8-127">**Deny**</span></span>|<span data-ttu-id="280b8-128">L'attributo non viene visualizzato.</span><span class="sxs-lookup"><span data-stu-id="280b8-128">The attribute is not displayed.</span></span><br /><br /> <span data-ttu-id="280b8-129">Nota: non è possibile negare in modo esplicito l'accesso agli attributi Name e Code.</span><span class="sxs-lookup"><span data-stu-id="280b8-129">Note: You cannot explicitly deny access to Name and Code attributes.</span></span>|  
  
### <a name="example"></a><span data-ttu-id="280b8-130">Esempio</span><span class="sxs-lookup"><span data-stu-id="280b8-130">Example</span></span>  
 <span data-ttu-id="280b8-131">Per l'entità Product, assegnare l'autorizzazione **Update** all'attributo Subcategory.</span><span class="sxs-lookup"><span data-stu-id="280b8-131">For the Product entity, assign **Update** permission to Subcategory attribute.</span></span> <span data-ttu-id="280b8-132">Negare l'autorizzazione per tutti gli altri attributi.</span><span class="sxs-lookup"><span data-stu-id="280b8-132">Deny permission to all other attributes.</span></span>  
  
|<span data-ttu-id="280b8-133">Nome</span><span class="sxs-lookup"><span data-stu-id="280b8-133">Name</span></span>|<span data-ttu-id="280b8-134">Codice</span><span class="sxs-lookup"><span data-stu-id="280b8-134">Code</span></span>|<span data-ttu-id="280b8-135">Subcategory (Aggiornamento)</span><span class="sxs-lookup"><span data-stu-id="280b8-135">Subcategory (Update)</span></span>|  
|----------|----------|----------------------------|  
|<span data-ttu-id="280b8-136">Mountain-100</span><span class="sxs-lookup"><span data-stu-id="280b8-136">Mountain-100</span></span>|<span data-ttu-id="280b8-137">BK-M101</span><span class="sxs-lookup"><span data-stu-id="280b8-137">BK-M101</span></span>|<span data-ttu-id="280b8-138">{5}Mountain bike</span><span class="sxs-lookup"><span data-stu-id="280b8-138">{5} Mountain Bikes</span></span>|  
|<span data-ttu-id="280b8-139">Mountain-100</span><span class="sxs-lookup"><span data-stu-id="280b8-139">Mountain-100</span></span>|<span data-ttu-id="280b8-140">BK-M201</span><span class="sxs-lookup"><span data-stu-id="280b8-140">BK-M201</span></span>|<span data-ttu-id="280b8-141">{5}Mountain bike</span><span class="sxs-lookup"><span data-stu-id="280b8-141">{5} Mountain Bikes</span></span>|  
  
 <span data-ttu-id="280b8-142">Nel **Visualizzatore**è possibile aggiornare qualsiasi valore di attributo nella colonna Subcategory.</span><span class="sxs-lookup"><span data-stu-id="280b8-142">In **Explorer**, you can update any attribute value in the Subcategory column.</span></span> <span data-ttu-id="280b8-143">Se non si dispone delle autorizzazioni per un attributo, l'attributo non viene visualizzato.</span><span class="sxs-lookup"><span data-stu-id="280b8-143">If you do not have permission to an attribute, the attribute is not displayed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="280b8-144">In questo esempio, Subcategory è un attributo basato su dominio, basato sull'entità SubcategoryList.</span><span class="sxs-lookup"><span data-stu-id="280b8-144">In this example, Subcategory is a domain-based attribute, based on the SubcategoryList entity.</span></span> <span data-ttu-id="280b8-145">È possibile selezionare una sottocategoria diversa per Mountain-100, ma non è possibile aggiungere o eliminare membri dall'entità SubcategoryList.</span><span class="sxs-lookup"><span data-stu-id="280b8-145">You can select a different subcategory for Mountain-100 but you cannot add members to or delete members from the SubcategoryList entity.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="280b8-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="280b8-146">See Also</span></span>  
 <span data-ttu-id="280b8-147">[Assegnare autorizzazioni per oggetti modello &#40;Master Data Services&#41;](assign-model-object-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="280b8-147">[Assign Model Object Permissions &#40;Master Data Services&#41;](assign-model-object-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="280b8-148">[Autorizzazioni consolidate &#40;Master Data Services&#41;](../../2014/master-data-services/consolidated-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="280b8-148">[Consolidated Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/consolidated-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="280b8-149">[Autorizzazioni per oggetti modello &#40;Master Data Services&#41;](../../2014/master-data-services/model-object-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="280b8-149">[Model Object Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/model-object-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="280b8-150">[Membri &#40;Master Data Services&#41;](../../2014/master-data-services/members-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="280b8-150">[Members &#40;Master Data Services&#41;](../../2014/master-data-services/members-master-data-services.md) </span></span>  
 [<span data-ttu-id="280b8-151">Attributi &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="280b8-151">Attributes &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/attributes-master-data-services.md)  
  
  
