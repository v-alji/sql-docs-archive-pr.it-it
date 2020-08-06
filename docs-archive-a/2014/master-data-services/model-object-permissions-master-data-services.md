---
title: Autorizzazioni per oggetti modello (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- permissions [Master Data Services], model objects
- models [Master Data Services], object permissions
ms.assetid: fab6335b-4cae-47de-ae7c-6c4743e0680f
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 4cc64d753b680cfabc3707a29c6d9de631708c20
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636754"
---
# <a name="model-object-permissions-master-data-services"></a><span data-ttu-id="5d4e6-102">Autorizzazioni per oggetti modello (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="5d4e6-102">Model Object Permissions (Master Data Services)</span></span>
  <span data-ttu-id="5d4e6-103">Le autorizzazioni per oggetti modello sono obbligatorie.</span><span class="sxs-lookup"><span data-stu-id="5d4e6-103">Model object permissions are mandatory.</span></span> <span data-ttu-id="5d4e6-104">Esse determinano a quali attributi può accedere un utente nell'area funzionale **Visualizzatore** dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="5d4e6-104">They determine the attributes a user can access in the **Explorer** functional area of the UI.</span></span>  
  
 <span data-ttu-id="5d4e6-105">Ad esempio, se si assegna all'utente un'autorizzazione **Update** per l'entità Product, l'utente può aggiornare tutti gli attributi dell'entità Product.</span><span class="sxs-lookup"><span data-stu-id="5d4e6-105">For example, if you assign a user **Update** permission to the Product entity, the user can update all of the attributes of the Product entity.</span></span> <span data-ttu-id="5d4e6-106">Se si assegna l'autorizzazione **Update** per un singolo attributo, l'utente potrà aggiornare solo quell'attributo.</span><span class="sxs-lookup"><span data-stu-id="5d4e6-106">If you assign **Update** permission to a single attribute, the user can update that attribute only.</span></span>  
  
 <span data-ttu-id="5d4e6-107">Per determinare la sicurezza assegnata su ogni singolo valore di attributo, le autorizzazioni degli oggetti modello vengono combinate alle autorizzazioni dei membri della gerarchia che determinano i membri ai quali un utente può accedere.</span><span class="sxs-lookup"><span data-stu-id="5d4e6-107">To determine security assigned on each individual attribute value, model object permissions are combined with hierarchy member permissions, which determine the members a user can access.</span></span>  
  
 <span data-ttu-id="5d4e6-108">Per concedere a un utente l'accesso a un'area funzionale diversa da **Esplora**, l'utente deve essere un amministratore del modello, che implica anche l'assegnazione delle autorizzazioni per gli oggetti modello.</span><span class="sxs-lookup"><span data-stu-id="5d4e6-108">To give a user access to a functional area other than **Explorer**, the user must be a model administrator, which also involves assigning model object permissions.</span></span> <span data-ttu-id="5d4e6-109">Per ulteriori informazioni, vedere [amministratori &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="5d4e6-109">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
 <span data-ttu-id="5d4e6-110">Le autorizzazioni per gli oggetti modello vengono assegnate nell' [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] area funzionale **autorizzazioni utenti e gruppi** della scheda **modelli** nell'interfaccia utente (UI). In questa scheda il modello viene rappresentato come struttura ad albero.</span><span class="sxs-lookup"><span data-stu-id="5d4e6-110">Model object permissions are assigned in the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] user interface (UI), in the **User and Group Permissions** functional area on the **Models** tab. On this tab, the model is represented as a tree structure.</span></span> <span data-ttu-id="5d4e6-111">Quando si assegna un'autorizzazione a un oggetto dell'albero, tutti gli oggetti sottostanti ereditano tale autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="5d4e6-111">When you assign permission to an object in the tree, all objects below inherit that permission.</span></span> <span data-ttu-id="5d4e6-112">Per eseguire l'override dell'ereditarietà, è possibile assegnare autorizzazioni ai singoli oggetti.</span><span class="sxs-lookup"><span data-stu-id="5d4e6-112">You can override that inheritance by assigning permission to individual objects.</span></span>  
  
 <span data-ttu-id="5d4e6-113">È possibile assegnare l'autorizzazione di sola **lettura**, **aggiornamento**o **negazione** agli oggetti modello.</span><span class="sxs-lookup"><span data-stu-id="5d4e6-113">You can assign **Read-only**, **Update**, or **Deny** permission to model objects.</span></span> <span data-ttu-id="5d4e6-114">La mancata assegnazione di autorizzazioni nella scheda **Modelli** determina l'impossibilità da parte dell'utente di visualizzare modelli o dati in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5d4e6-114">If you do not assign any permissions on the **Models** tab, the user cannot view any models or data in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span></span>  
  
## <a name="best-practice"></a><span data-ttu-id="5d4e6-115">Procedura consigliata</span><span class="sxs-lookup"><span data-stu-id="5d4e6-115">Best Practice</span></span>  
 <span data-ttu-id="5d4e6-116">In generale, è consigliabile assegnare l'autorizzazione **aggiornamento** all'oggetto modello e quindi assegnare in modo esplicito l'autorizzazione agli oggetti sottostanti.</span><span class="sxs-lookup"><span data-stu-id="5d4e6-116">In general, you should assign **Update** permission to the model object, and then explicitly assign permission to objects underneath.</span></span> <span data-ttu-id="5d4e6-117">Se non si assegna l'autorizzazione agli oggetti sottostanti, le autorizzazioni vengono ereditate e l'utente è un amministratore.</span><span class="sxs-lookup"><span data-stu-id="5d4e6-117">If you do not assign permission to objects underneath, the permissions are inherited and the user is an administrator.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d4e6-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5d4e6-118">See Also</span></span>  
 <span data-ttu-id="5d4e6-119">[Assegnare autorizzazioni per oggetti modello &#40;Master Data Services&#41;](../../2014/master-data-services/assign-model-object-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="5d4e6-119">[Assign Model Object Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/assign-model-object-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="5d4e6-120">[Autorizzazioni del modello &#40;Master Data Services&#41;](../../2014/master-data-services/model-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="5d4e6-120">[Model Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/model-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="5d4e6-121">[Autorizzazioni per aree funzionali &#40;Master Data Services&#41;](../../2014/master-data-services/functional-area-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="5d4e6-121">[Functional Area Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/functional-area-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="5d4e6-122">[Autorizzazioni membri gerarchia &#40;Master Data Services&#41;](../../2014/master-data-services/hierarchy-member-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="5d4e6-122">[Hierarchy Member Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/hierarchy-member-permissions-master-data-services.md) </span></span>  
 [<span data-ttu-id="5d4e6-123">Modalità di determinazione delle autorizzazioni &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="5d4e6-123">How Permissions Are Determined &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/how-permissions-are-determined-master-data-services.md)  
  
  
