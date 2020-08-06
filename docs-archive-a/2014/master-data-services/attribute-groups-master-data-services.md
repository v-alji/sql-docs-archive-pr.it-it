---
title: Gruppi di attributi (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- attribute groups [Master Data Services]
- attribute groups [Master Data Services], about attribute groups
ms.assetid: 648b3d0b-e15a-45f9-8292-3a54a072e62c
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 390b402489799639e66a44992da1e20b0d0c1bbf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629468"
---
# <a name="attribute-groups-master-data-services"></a><span data-ttu-id="4dc96-102">Gruppi di attributi (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="4dc96-102">Attribute Groups (Master Data Services)</span></span>
  <span data-ttu-id="4dc96-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]i gruppi di attributi consentono di organizzare gli attributi in un'entità.</span><span class="sxs-lookup"><span data-stu-id="4dc96-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], attribute groups help organize attributes in an entity.</span></span> <span data-ttu-id="4dc96-104">Quando un'entità dispone di molti attributi, i gruppi di attributi migliorano la modalità di visualizzazione di un'entità nell'applicazione Web [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4dc96-104">When an entity has lots of attributes, attribute groups improve the way an entity is displayed in the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] web application.</span></span>  
  
## <a name="how-attribute-groups-change-the-display"></a><span data-ttu-id="4dc96-105">Modalità di modifica della visualizzazione dei gruppi di attributi</span><span class="sxs-lookup"><span data-stu-id="4dc96-105">How Attribute Groups Change the Display</span></span>  
 <span data-ttu-id="4dc96-106">I gruppi di attributi vengono visualizzati come schede al di sopra della griglia nell'area funzionale **Visualizzatore** di [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4dc96-106">Attribute groups are displayed as tabs above the grid in the **Explorer** functional area of [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span></span>  
  
 <span data-ttu-id="4dc96-107">Quando un'entità dispone di un numero elevato di attributi e l'entità + visualizzata in una griglia nel **Visualizzatore**, è necessario scorrere verso destra per visualizzare tutti gli attributi.</span><span class="sxs-lookup"><span data-stu-id="4dc96-107">When an entity has a large number of attributes and you view that entity in a grid in **Explorer**, you must scroll to the right to view all of the attributes.</span></span> <span data-ttu-id="4dc96-108">Per evitare di dover scorrere verso destra, è possibile creare gruppi di attributi.</span><span class="sxs-lookup"><span data-stu-id="4dc96-108">To prevent this scrolling, you can create attribute groups.</span></span>  
  
-   <span data-ttu-id="4dc96-109">Gli attributi Name e Code sono sempre inclusi automaticamente nei gruppi di attributi.</span><span class="sxs-lookup"><span data-stu-id="4dc96-109">Attribute groups always include the Name and Code attributes.</span></span>  
  
-   <span data-ttu-id="4dc96-110">Ciascun attributo di un'entità può appartenere a uno o più gruppi di attributi.</span><span class="sxs-lookup"><span data-stu-id="4dc96-110">Each attribute for an entity can belong to one or more attribute groups.</span></span>  
  
-   <span data-ttu-id="4dc96-111">Tutti gli attributi sono inclusi automaticamente nella scheda **Tutti gli attributi** nel **Visualizzatore**.</span><span class="sxs-lookup"><span data-stu-id="4dc96-111">All attributes are automatically included on the **All Attributes** tab in **Explorer**.</span></span>  
  
-   <span data-ttu-id="4dc96-112">Non è possibile nascondere la scheda **Tutti gli attributi** .</span><span class="sxs-lookup"><span data-stu-id="4dc96-112">There is no way to hide the **All Attributes** tab.</span></span>  
  
 <span data-ttu-id="4dc96-113">I gruppi di attributi vengono amministrati nell'area funzionale **Amministrazione sistema** di [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4dc96-113">Attribute groups are administered in the **System Administration** functional area of [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span></span>  
  
## <a name="show-or-hide-attribute-groups"></a><span data-ttu-id="4dc96-114">Mostrare o nascondere i gruppi di attributi</span><span class="sxs-lookup"><span data-stu-id="4dc96-114">Show or Hide Attribute Groups</span></span>  
 <span data-ttu-id="4dc96-115">Quando si crea un gruppo di attributi, questo viene automaticamente nascosto a tutti gli utenti ad eccezione di quello che lo creato.</span><span class="sxs-lookup"><span data-stu-id="4dc96-115">When you create an attribute group, it is automatically hidden from all users except the one who created it.</span></span> <span data-ttu-id="4dc96-116">Per altre informazioni su come rendere visibile un gruppo, vedere [Rendere visibile un gruppo di attributi per gli utenti &#40;Master Data Services&#41;](make-an-attribute-group-visible-to-users-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="4dc96-116">For more information about making the group visible, see [Make an Attribute Group Visible to Users &#40;Master Data Services&#41;](make-an-attribute-group-visible-to-users-master-data-services.md).</span></span>  
  
 <span data-ttu-id="4dc96-117">Per nascondere un attributo specifico all'interno di un gruppo, è possibile assegnare l'autorizzazione **Nega** all'attributo.</span><span class="sxs-lookup"><span data-stu-id="4dc96-117">If you want to hide a specific attribute within a group, you can assign **Deny** permission to the attribute.</span></span> <span data-ttu-id="4dc96-118">Per altre informazioni, vedere [Autorizzazioni per elementi foglia &#40;Master Data Services&#41;](../../2014/master-data-services/leaf-permissions-master-data-services.md) o [Autorizzazioni consolidate &#40;Master Data Services&#41;](../../2014/master-data-services/consolidated-permissions-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="4dc96-118">For more information, see [Leaf Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/leaf-permissions-master-data-services.md) or [Consolidated Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/consolidated-permissions-master-data-services.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="4dc96-119">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="4dc96-119">Related Tasks</span></span>  
  
|<span data-ttu-id="4dc96-120">Descrizione dell'attività</span><span class="sxs-lookup"><span data-stu-id="4dc96-120">Task Description</span></span>|<span data-ttu-id="4dc96-121">Argomento</span><span class="sxs-lookup"><span data-stu-id="4dc96-121">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="4dc96-122">Creare un nuovo gruppo di attributi e aggiungergli attributi.</span><span class="sxs-lookup"><span data-stu-id="4dc96-122">Create a new attribute group and add attributes to it.</span></span>|[<span data-ttu-id="4dc96-123">Creare un gruppo di attributi &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="4dc96-123">Create an Attribute Group &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-an-attribute-group-master-data-services.md)|  
|<span data-ttu-id="4dc96-124">Rendere visibile un gruppo di attributi agli utenti.</span><span class="sxs-lookup"><span data-stu-id="4dc96-124">Make an attribute group visible to users.</span></span>|[<span data-ttu-id="4dc96-125">Rendere visibile un gruppo di attributi per gli utenti &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="4dc96-125">Make an Attribute Group Visible to Users &#40;Master Data Services&#41;</span></span>](make-an-attribute-group-visible-to-users-master-data-services.md)|  
|<span data-ttu-id="4dc96-126">Modificare il nome di un gruppo di attributi esistente.</span><span class="sxs-lookup"><span data-stu-id="4dc96-126">Change the name of an existing attribute group.</span></span>|[<span data-ttu-id="4dc96-127">Modificare il nome di un gruppo di attributi &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="4dc96-127">Change an Attribute Group Name &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/change-an-attribute-group-name-master-data-services.md)|  
|<span data-ttu-id="4dc96-128">Eliminare un gruppo di attributi esistente.</span><span class="sxs-lookup"><span data-stu-id="4dc96-128">Delete an existing attribute group.</span></span>|[<span data-ttu-id="4dc96-129">Eliminare un gruppo di attributi &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="4dc96-129">Delete an Attribute Group &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/delete-an-attribute-group-master-data-services.md)|  
  
## <a name="related-content"></a><span data-ttu-id="4dc96-130">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="4dc96-130">Related Content</span></span>  
  
-   [<span data-ttu-id="4dc96-131">Attributi &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="4dc96-131">Attributes &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/attributes-master-data-services.md)  
  
  
