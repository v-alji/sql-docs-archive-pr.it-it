---
title: Autorizzazioni per i modelli (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- models [Master Data Services], permissions
- permissions [Master Data Services], models
ms.assetid: 210f440b-2cc1-4c49-94b1-3a97e2af7bc3
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 2846918b515bba16d12d48cd7058cf25863bf569
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628784"
---
# <a name="model-permissions-master-data-services"></a><span data-ttu-id="58c31-102">Autorizzazioni per i modelli (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="58c31-102">Model Permissions (Master Data Services)</span></span>
  <span data-ttu-id="58c31-103">Le autorizzazioni per i modelli si applicano a tutte le entità, alle gerarchie derivate, alle gerarchie esplicite e alle raccolte esistenti all'interno del modello.</span><span class="sxs-lookup"><span data-stu-id="58c31-103">Model permissions apply to all entities, derived hierarchies, explicit hierarchies, and collections that exist within the model.</span></span> <span data-ttu-id="58c31-104">È possibile eseguire l'override delle autorizzazioni assegnate al modello per qualsiasi singolo oggetto.</span><span class="sxs-lookup"><span data-stu-id="58c31-104">Permissions assigned to the model can be overridden for any individual object.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="58c31-105">Se un utente è un amministratore di modelli, il modello viene visualizzato in tutte le aree funzionali dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="58c31-105">If a user is a model administrator, the model is displayed in all functional areas of the user interface.</span></span> <span data-ttu-id="58c31-106">In caso contrario, il modello viene visualizzato solo nell'area funzionale **Visualizzatore** .</span><span class="sxs-lookup"><span data-stu-id="58c31-106">Otherwise, the model is displayed in the **Explorer** functional area only.</span></span> <span data-ttu-id="58c31-107">Per ulteriori informazioni, vedere [amministratori &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="58c31-107">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
|<span data-ttu-id="58c31-108">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="58c31-108">Permission</span></span>|<span data-ttu-id="58c31-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="58c31-109">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="58c31-110">**Sola lettura**</span><span class="sxs-lookup"><span data-stu-id="58c31-110">**Read-only**</span></span>|<span data-ttu-id="58c31-111">In **Esplora**viene visualizzato il modello, ma l'utente non può aggiungere o rimuovere membri né aggiornare i valori degli attributi, le appartenenze a gerarchie o le appartenenze alla raccolta.</span><span class="sxs-lookup"><span data-stu-id="58c31-111">In **Explorer**, the model is displayed but the user cannot add or remove members, and cannot update attribute values, hierarchy memberships, or collection memberships.</span></span>|  
|<span data-ttu-id="58c31-112">**Aggiornamento**</span><span class="sxs-lookup"><span data-stu-id="58c31-112">**Update**</span></span>|<span data-ttu-id="58c31-113">In **Esplora**viene visualizzato il modello e l'utente può aggiungere e rimuovere membri, può aggiornare i valori degli attributi, le appartenenze alla gerarchia e le appartenenze alla raccolta.</span><span class="sxs-lookup"><span data-stu-id="58c31-113">In **Explorer**, the model is displayed and the user can add and remove members, can update attribute values, hierarchy memberships, and collection memberships.</span></span>|  
|<span data-ttu-id="58c31-114">**Nega**</span><span class="sxs-lookup"><span data-stu-id="58c31-114">**Deny**</span></span>|<span data-ttu-id="58c31-115">Il modello non viene visualizzato.</span><span class="sxs-lookup"><span data-stu-id="58c31-115">The model is not displayed.</span></span>|  
  
 <span data-ttu-id="58c31-116">Quando si assegna un'autorizzazione a un modello, l'utente ottiene l'accesso a tutte le versioni del modello.</span><span class="sxs-lookup"><span data-stu-id="58c31-116">When you assign permission to a model, the user gets access to all versions of the model.</span></span> <span data-ttu-id="58c31-117">Non è possibile assegnare un'autorizzazione a una determinata versione.</span><span class="sxs-lookup"><span data-stu-id="58c31-117">You cannot assign permission to an individual version.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58c31-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="58c31-118">See Also</span></span>  
 <span data-ttu-id="58c31-119">[Assegnare autorizzazioni per oggetti modello &#40;Master Data Services&#41;](../../2014/master-data-services/assign-model-object-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="58c31-119">[Assign Model Object Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/assign-model-object-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="58c31-120">[Autorizzazioni per oggetti modello &#40;Master Data Services&#41;](../../2014/master-data-services/model-object-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="58c31-120">[Model Object Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/model-object-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="58c31-121">[Autorizzazioni per le entità &#40;Master Data Services&#41;](../../2014/master-data-services/entity-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="58c31-121">[Entity Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/entity-permissions-master-data-services.md) </span></span>  
 [<span data-ttu-id="58c31-122">Autorizzazioni per raccolte &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="58c31-122">Collection Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/collection-permissions-master-data-services.md)  
  
  
