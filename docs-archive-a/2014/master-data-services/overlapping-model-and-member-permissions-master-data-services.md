---
title: Autorizzazioni per modelli e membri sovrapposte (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- models [Master Data Services], effective permissions
- permissions [Master Data Services], model and member overlaps
- members [Master Data Services], effective permissions
ms.assetid: 9fd7a555-43bf-4796-a8b6-1ca63a291216
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: ec5f4019f25a777e4c70433bd9a7e72fca2277e2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624788"
---
# <a name="overlapping-model-and-member-permissions-master-data-services"></a><span data-ttu-id="5c163-102">Autorizzazioni per modelli e membri sovrapposte (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="5c163-102">Overlapping Model and Member Permissions (Master Data Services)</span></span>
  <span data-ttu-id="5c163-103">Le autorizzazioni assegnate a un membro possono sovrapporsi alle autorizzazioni assegnate a un oggetto modello.</span><span class="sxs-lookup"><span data-stu-id="5c163-103">Permission assigned to a member can overlap with permission assigned to a model object.</span></span> <span data-ttu-id="5c163-104">Quando si verificano sovrapposizioni, viene applicata l'autorizzazione più restrittiva.</span><span class="sxs-lookup"><span data-stu-id="5c163-104">When overlaps occur, the more restrictive permission takes effect.</span></span>  
  
 <span data-ttu-id="5c163-105">Se un membro dispone di autorizzazione diversa da quella del relativo oggetto modello corrispondente, si applicano le regole seguenti:</span><span class="sxs-lookup"><span data-stu-id="5c163-105">If a member has permission that is different than its corresponding model object, the following rules apply:</span></span>  
  
-   <span data-ttu-id="5c163-106">**Nega** esegue l'override di tutte le altre autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="5c163-106">**Deny** overrides all other permissions.</span></span>  
  
-   <span data-ttu-id="5c163-107">**Aggiornamento** **di sola lettura** esegue l'override di.</span><span class="sxs-lookup"><span data-stu-id="5c163-107">**Read-only** overrides **Update**.</span></span>  
  
 <span data-ttu-id="5c163-108">Nell'immagine seguente viene indicato quali autorizzazioni vengono applicate a ogni singolo valore di attributo quando le autorizzazioni per gli attributi sono diverse dalle autorizzazioni per i membri.</span><span class="sxs-lookup"><span data-stu-id="5c163-108">The following image shows which permissions take effect on an individual attribute value when attribute permissions are different than member permissions.</span></span>  
  
 <span data-ttu-id="5c163-109">![mds_conc_security_member_overlap_table](../../2014/master-data-services/media/mds-conc-security-member-overlap-table.gif "mds_conc_security_member_overlap_table")</span><span class="sxs-lookup"><span data-stu-id="5c163-109">![mds_conc_security_member_overlap_table](../../2014/master-data-services/media/mds-conc-security-member-overlap-table.gif "mds_conc_security_member_overlap_table")</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="5c163-110">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="5c163-110">Example 1</span></span>  
 <span data-ttu-id="5c163-111">![mds_conc_overlap_model_1](../../2014/master-data-services/media/mds-conc-overlap-model-1.gif "mds_conc_overlap_model_1")</span><span class="sxs-lookup"><span data-stu-id="5c163-111">![mds_conc_overlap_model_1](../../2014/master-data-services/media/mds-conc-overlap-model-1.gif "mds_conc_overlap_model_1")</span></span>  
  
 <span data-ttu-id="5c163-112">Nella scheda **Modelli** all'entità Product è stata assegnata l'autorizzazione **Aggiorna** .</span><span class="sxs-lookup"><span data-stu-id="5c163-112">On the **Models** tab, the Product entity has **Update** permission assigned.</span></span> <span data-ttu-id="5c163-113">Tutti gli attributi nell'entità ereditano questa autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="5c163-113">All attributes in the entity inherit that permission.</span></span>  
  
 <span data-ttu-id="5c163-114">Nella scheda **Membri gerarchia** il nodo della sottocategoria Mountain Bikes in una gerarchia derivata dispone dell'autorizzazione **Aggiorna** .</span><span class="sxs-lookup"><span data-stu-id="5c163-114">On the **Hierarchy Members** tab, the Mountain Bikes subcategory node in a derived hierarchy has **Update** permission assigned.</span></span>  
  
 <span data-ttu-id="5c163-115">Risultato: in **Esplora**l'utente dispone dell'autorizzazione **Aggiorna** per tutti i valori di attributo per tutti i membri nel nodo Mountain Bike.</span><span class="sxs-lookup"><span data-stu-id="5c163-115">Result: In **Explorer**, the user has **Update** permission to all attribute values for all members in the Mountain Bikes node.</span></span> <span data-ttu-id="5c163-116">Tutti gli altri membri e attributi sono nascosti.</span><span class="sxs-lookup"><span data-stu-id="5c163-116">All other members and attributes are hidden.</span></span>  
  
 <span data-ttu-id="5c163-117">![mds_conc_overlap_model_example_1](../../2014/master-data-services/media/mds-conc-overlap-model-example-1.gif "mds_conc_overlap_model_example_1")</span><span class="sxs-lookup"><span data-stu-id="5c163-117">![mds_conc_overlap_model_example_1](../../2014/master-data-services/media/mds-conc-overlap-model-example-1.gif "mds_conc_overlap_model_example_1")</span></span>  
  
## <a name="example-2"></a><span data-ttu-id="5c163-118">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="5c163-118">Example 2</span></span>  
 <span data-ttu-id="5c163-119">![mds_conc_overlap_model_2](../../2014/master-data-services/media/mds-conc-overlap-model-2.gif "mds_conc_overlap_model_2")</span><span class="sxs-lookup"><span data-stu-id="5c163-119">![mds_conc_overlap_model_2](../../2014/master-data-services/media/mds-conc-overlap-model-2.gif "mds_conc_overlap_model_2")</span></span>  
  
 <span data-ttu-id="5c163-120">Nella scheda **Modelli** all'attributo Subcategory è assegnata l'autorizzazione **Aggiorna** .</span><span class="sxs-lookup"><span data-stu-id="5c163-120">On the **Models** tab, the Subcategory attribute has **Update** permission assigned.</span></span>  
  
 <span data-ttu-id="5c163-121">Nella scheda **membri gerarchia** , al nodo della sottocategoria Mountain Bikes in una gerarchia derivata viene assegnata in modo esplicito l'autorizzazione **di sola lettura** .</span><span class="sxs-lookup"><span data-stu-id="5c163-121">On the **Hierarchy Members** tab, the Mountain Bikes subcategory node in a derived hierarchy is explicitly assigned **Read-only** permission.</span></span>  
  
 <span data-ttu-id="5c163-122">Risultato: in **Esplora**l'utente dispone dell'autorizzazione di sola **lettura** per i valori dell'attributo Subcategory per i membri del nodo Mountain Bikes.</span><span class="sxs-lookup"><span data-stu-id="5c163-122">Result: In **Explorer**, the user has **Read-only** permission to the Subcategory attribute values for the members in the Mountain Bikes node.</span></span> <span data-ttu-id="5c163-123">Tutti gli altri membri e attributi sono nascosti.</span><span class="sxs-lookup"><span data-stu-id="5c163-123">All other members and attributes are hidden.</span></span>  
  
 <span data-ttu-id="5c163-124">![mds_conc_overlap_model_example_2](../../2014/master-data-services/media/mds-conc-overlap-model-example-2.gif "mds_conc_overlap_model_example_2")</span><span class="sxs-lookup"><span data-stu-id="5c163-124">![mds_conc_overlap_model_example_2](../../2014/master-data-services/media/mds-conc-overlap-model-example-2.gif "mds_conc_overlap_model_example_2")</span></span>  
  
## <a name="example-3"></a><span data-ttu-id="5c163-125">Esempio 3</span><span class="sxs-lookup"><span data-stu-id="5c163-125">Example 3</span></span>  
 <span data-ttu-id="5c163-126">![mds_conc_overlap_model_3](../../2014/master-data-services/media/mds-conc-overlap-model-3.gif "mds_conc_overlap_model_3")</span><span class="sxs-lookup"><span data-stu-id="5c163-126">![mds_conc_overlap_model_3](../../2014/master-data-services/media/mds-conc-overlap-model-3.gif "mds_conc_overlap_model_3")</span></span>  
  
 <span data-ttu-id="5c163-127">Nella scheda **modelli** all'attributo Subcategory è stata assegnata l'autorizzazione di sola **lettura** .</span><span class="sxs-lookup"><span data-stu-id="5c163-127">On the **Models** tab, the Subcategory attribute has **Read-only** permission assigned.</span></span>  
  
 <span data-ttu-id="5c163-128">Nella scheda **Membri gerarchia** alla sottocategoria Mountain Bikes in una gerarchia derivata è stata assegnata in modo esplicito l'autorizzazione **Aggiorna** .</span><span class="sxs-lookup"><span data-stu-id="5c163-128">On the **Hierarchy Members** tab, the Mountain Bikes subcategory in a derived hierarchy is explicitly assigned **Update** permission.</span></span>  
  
 <span data-ttu-id="5c163-129">Risultato: in **Esplora**l'utente dispone dell'autorizzazione di sola **lettura** per i valori dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="5c163-129">Result: In **Explorer**, the user has **Read-only** permission to the attribute values.</span></span> <span data-ttu-id="5c163-130">Tutti gli altri membri e attributi sono nascosti.</span><span class="sxs-lookup"><span data-stu-id="5c163-130">All other members and attributes are hidden.</span></span>  
  
 <span data-ttu-id="5c163-131">![mds_conc_overlap_model_example_2](../../2014/master-data-services/media/mds-conc-overlap-model-example-2.gif "mds_conc_overlap_model_example_2")</span><span class="sxs-lookup"><span data-stu-id="5c163-131">![mds_conc_overlap_model_example_2](../../2014/master-data-services/media/mds-conc-overlap-model-example-2.gif "mds_conc_overlap_model_example_2")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c163-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5c163-132">See Also</span></span>  
 <span data-ttu-id="5c163-133">[Modalità di determinazione delle autorizzazioni &#40;Master Data Services&#41;](how-permissions-are-determined-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="5c163-133">[How Permissions Are Determined &#40;Master Data Services&#41;](how-permissions-are-determined-master-data-services.md) </span></span>  
 [<span data-ttu-id="5c163-134">Autorizzazioni utenti e gruppi sovrapposte &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="5c163-134">Overlapping User and Group Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/overlapping-user-and-group-permissions-master-data-services.md)  
  
  
