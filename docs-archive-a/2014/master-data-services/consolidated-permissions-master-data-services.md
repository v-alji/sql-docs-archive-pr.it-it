---
title: Autorizzazioni consolidate (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- attributes [Master Data Services], consolidated member attribute permissions
- consolidated members [Master Data Services], attribute permissions
- permissions [Master Data Services], consolidated members
- members [Master Data Services], consolidated member permissions
ms.assetid: 084055a3-5fd3-43f3-b620-ac6afab42a3d
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c4c93e74acc84d6e742139263bedc011c4028efb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638449"
---
# <a name="consolidated-permissions-master-data-services"></a><span data-ttu-id="44b08-102">Autorizzazioni consolidate (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="44b08-102">Consolidated Permissions (Master Data Services)</span></span>
  <span data-ttu-id="44b08-103">Le autorizzazioni consolidate si applicano ai valori di attributo per tutti i membri consolidati di un'entità.</span><span class="sxs-lookup"><span data-stu-id="44b08-103">Consolidated permissions apply to the attribute values for all consolidated members of an entity.</span></span>  
  
 <span data-ttu-id="44b08-104">Le autorizzazioni consolidate si applicano solo alle entità abilitate per gerarchie esplicite e raccolte.</span><span class="sxs-lookup"><span data-stu-id="44b08-104">Consolidated permissions apply only to entities that are enabled for explicit hierarchies and collections.</span></span>  
  
 <span data-ttu-id="44b08-105">**Note:**</span><span class="sxs-lookup"><span data-stu-id="44b08-105">**Notes:**</span></span>  
  
-   <span data-ttu-id="44b08-106">Le autorizzazioni foglia si applicano solo all'area funzionale **Visualizzatore** dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="44b08-106">Leaf permissions apply to the **Explorer** functional area of the user interface only.</span></span>  
  
-   <span data-ttu-id="44b08-107">Le autorizzazioni assegnate agli attributi **Name** e **Code** non sono applicate.</span><span class="sxs-lookup"><span data-stu-id="44b08-107">Permissions assigned to **Name** and **Code** attributes are not enforced.</span></span>  
  
|<span data-ttu-id="44b08-108">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="44b08-108">Permission</span></span>|<span data-ttu-id="44b08-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="44b08-109">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="44b08-110">**Sola lettura**</span><span class="sxs-lookup"><span data-stu-id="44b08-110">**Read-only**</span></span>|<span data-ttu-id="44b08-111">I membri consolidati vengono visualizzati, ma l'utente non può aggiungerli, rimuoverli o modificarli.</span><span class="sxs-lookup"><span data-stu-id="44b08-111">Consolidated members are displayed but the user cannot add, remove, or change them.</span></span>|  
|<span data-ttu-id="44b08-112">**Aggiornamento**</span><span class="sxs-lookup"><span data-stu-id="44b08-112">**Update**</span></span>|<span data-ttu-id="44b08-113">I membri consolidati vengono visualizzati e l'utente può aggiungerli, rimuoverli e modificarli.</span><span class="sxs-lookup"><span data-stu-id="44b08-113">Consolidated members are displayed and the user can add, remove, and change them.</span></span>|  
|<span data-ttu-id="44b08-114">**Nega**</span><span class="sxs-lookup"><span data-stu-id="44b08-114">**Deny**</span></span>|<span data-ttu-id="44b08-115">I membri consolidati per l'entità non vengono visualizzati.</span><span class="sxs-lookup"><span data-stu-id="44b08-115">Consolidated members for the entity are not displayed.</span></span>|  
  
## <a name="attribute-permissions"></a><span data-ttu-id="44b08-116">Autorizzazioni per attributi</span><span class="sxs-lookup"><span data-stu-id="44b08-116">Attribute Permissions</span></span>  
 <span data-ttu-id="44b08-117">Le autorizzazioni per gli attributi si applicano ai valori degli attributi per l'entità specifica.</span><span class="sxs-lookup"><span data-stu-id="44b08-117">Attribute permissions apply to the attribute's values for the specific entity.</span></span> <span data-ttu-id="44b08-118">Gli utenti che dispongono solo delle autorizzazioni per gli attributi non possono aggiungere o rimuovere membri.</span><span class="sxs-lookup"><span data-stu-id="44b08-118">Users with only attribute permissions cannot add or remove members.</span></span>  
  
|<span data-ttu-id="44b08-119">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="44b08-119">Permission</span></span>|<span data-ttu-id="44b08-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="44b08-120">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="44b08-121">**Sola lettura**</span><span class="sxs-lookup"><span data-stu-id="44b08-121">**Read-only**</span></span>|<span data-ttu-id="44b08-122">L'attributo viene visualizzato, ma l'utente non può modificare i valori di attributo.</span><span class="sxs-lookup"><span data-stu-id="44b08-122">The attribute is displayed but the user cannot change attribute values.</span></span>|  
|<span data-ttu-id="44b08-123">**Aggiornamento**</span><span class="sxs-lookup"><span data-stu-id="44b08-123">**Update**</span></span>|<span data-ttu-id="44b08-124">L'attributo viene visualizzato e l'utente può modificare i valori di attributo.</span><span class="sxs-lookup"><span data-stu-id="44b08-124">The attribute is displayed and the user can change attribute values.</span></span>|  
|<span data-ttu-id="44b08-125">**Nega**</span><span class="sxs-lookup"><span data-stu-id="44b08-125">**Deny**</span></span>|<span data-ttu-id="44b08-126">L'attributo non viene visualizzato.</span><span class="sxs-lookup"><span data-stu-id="44b08-126">The attribute is not displayed.</span></span><br /><br /> <span data-ttu-id="44b08-127">Nota: non è possibile negare in modo esplicito l'accesso agli attributi Name e Code.</span><span class="sxs-lookup"><span data-stu-id="44b08-127">Note: You cannot explicitly deny access to Name and Code attributes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="44b08-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="44b08-128">See Also</span></span>  
 <span data-ttu-id="44b08-129">[Assegnare autorizzazioni per oggetti modello &#40;Master Data Services&#41;](assign-model-object-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="44b08-129">[Assign Model Object Permissions &#40;Master Data Services&#41;](assign-model-object-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="44b08-130">[Autorizzazioni foglia &#40;Master Data Services&#41;](../../2014/master-data-services/leaf-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="44b08-130">[Leaf Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/leaf-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="44b08-131">[Autorizzazioni per oggetti modello &#40;Master Data Services&#41;](../../2014/master-data-services/model-object-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="44b08-131">[Model Object Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/model-object-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="44b08-132">[Membri &#40;Master Data Services&#41;](../../2014/master-data-services/members-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="44b08-132">[Members &#40;Master Data Services&#41;](../../2014/master-data-services/members-master-data-services.md) </span></span>  
 [<span data-ttu-id="44b08-133">Attributi &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="44b08-133">Attributes &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/attributes-master-data-services.md)  
  
  
