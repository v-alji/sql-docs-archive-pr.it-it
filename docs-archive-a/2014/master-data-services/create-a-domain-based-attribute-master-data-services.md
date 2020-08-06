---
title: Creare un attributo basato su dominio (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- domain-based attributes [Master Data Services], creating
- creating domain-based attributes [Master Data Services]
- attributes [Master Data Services], creating domain-based attributes
ms.assetid: 11c31c9f-e6cc-47b7-b76a-d691f84c93c6
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 51c0f44bb76ae2ad4c25987ed5e5ee144a18c739
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625439"
---
# <a name="create-a-domain-based-attribute-master-data-services"></a><span data-ttu-id="5bafc-102">Creare un attributo basato su dominio (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="5bafc-102">Create a Domain-Based Attribute (Master Data Services)</span></span>
  <span data-ttu-id="5bafc-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]creare un attributo basato su dominio per popolare i valori di un attributo con i membri di un'entità.</span><span class="sxs-lookup"><span data-stu-id="5bafc-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], create a domain-based attribute to populate an attribute's values with members from an entity.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="5bafc-104">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="5bafc-104">Prerequisites</span></span>  
 <span data-ttu-id="5bafc-105">Per eseguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="5bafc-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="5bafc-106">È necessario disporre di autorizzazione per accedere all'area funzionale **Amministrazione sistema** .</span><span class="sxs-lookup"><span data-stu-id="5bafc-106">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="5bafc-107">È necessario essere un amministratore del modello.</span><span class="sxs-lookup"><span data-stu-id="5bafc-107">You must be a model administrator.</span></span> <span data-ttu-id="5bafc-108">Per ulteriori informazioni, vedere [amministratori &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="5bafc-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="5bafc-109">È necessario che un'entità esista perché venga utilizzata come origine dei valori di attributo.</span><span class="sxs-lookup"><span data-stu-id="5bafc-109">An entity must exist to use as the source of the attribute values.</span></span> <span data-ttu-id="5bafc-110">Ad esempio per creare un attributo basato su dominio che si basa sull'entità Color, è necessario prima creare l'entità Color.</span><span class="sxs-lookup"><span data-stu-id="5bafc-110">For example, to create a domain-based attribute based on the Color entity, you must first create the Color entity.</span></span> <span data-ttu-id="5bafc-111">Per altre informazioni, vedere [Creare un'entità &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="5bafc-111">For more information, see [Create an Entity &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="5bafc-112">È necessario che sia presente un'entità perché ne venga creato l'attributo.</span><span class="sxs-lookup"><span data-stu-id="5bafc-112">An entity must exist to create the attribute for.</span></span> <span data-ttu-id="5bafc-113">Per altre informazioni, vedere [Creare un'entità &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="5bafc-113">For more information, see [Create an Entity &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span></span>  
  
### <a name="to-create-a-domain-based-attribute"></a><span data-ttu-id="5bafc-114">Per creare un attributo basato su dominio</span><span class="sxs-lookup"><span data-stu-id="5bafc-114">To create a domain-based attribute</span></span>  
  
1.  <span data-ttu-id="5bafc-115">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], fare clic su **Amministrazione sistema**.</span><span class="sxs-lookup"><span data-stu-id="5bafc-115">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="5bafc-116">Nella pagina **Vista modelli** scegliere **Gestisci** dalla barra dei menu, quindi fare clic su **Entità**.</span><span class="sxs-lookup"><span data-stu-id="5bafc-116">On the **Model View** page, from the menu bar, point to **Manage** and click **Entities**.</span></span>  
  
3.  <span data-ttu-id="5bafc-117">Nella pagina **Gestione entità** selezionare un modello dall'elenco **Modello** .</span><span class="sxs-lookup"><span data-stu-id="5bafc-117">On the **Entity Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="5bafc-118">Selezionare la riga relativa all'entità per la quale si desidera creare un attributo.</span><span class="sxs-lookup"><span data-stu-id="5bafc-118">Select the row for the entity that you want to create an attribute for.</span></span>  
  
5.  <span data-ttu-id="5bafc-119">Fare clic su **Modifica entità selezionata**.</span><span class="sxs-lookup"><span data-stu-id="5bafc-119">Click **Edit selected entity**.</span></span>  
  
6.  <span data-ttu-id="5bafc-120">Nella pagina **Modifica entità** :</span><span class="sxs-lookup"><span data-stu-id="5bafc-120">On the **Edit Entity** page:</span></span>  
  
    -   <span data-ttu-id="5bafc-121">Se l'attributo è per membri foglia, nel riquadro **Attributi membro foglia** fare clic su **Aggiungi attributo foglia**.</span><span class="sxs-lookup"><span data-stu-id="5bafc-121">If the attribute is for leaf members, in the **Leaf member attributes** pane, click **Add leaf attribute**.</span></span>  
  
    -   <span data-ttu-id="5bafc-122">Se l'attributo è per membri consolidati, nel riquadro **Attributi membro consolidati** fare clic su **Aggiungi attributo consolidato**.</span><span class="sxs-lookup"><span data-stu-id="5bafc-122">If the attribute is for consolidated members, in the **Consolidated member attributes** pane, click **Add consolidated attribute**.</span></span>  
  
    -   <span data-ttu-id="5bafc-123">Se l'attributo è per raccolte, nel riquadro **Attributi raccolta** fare clic su **Aggiungi attributo raccolta**.</span><span class="sxs-lookup"><span data-stu-id="5bafc-123">If the attribute is for collections, in the **Collection attributes** pane, click **Add collection attribute**.</span></span>  
  
7.  <span data-ttu-id="5bafc-124">Nella pagina **Aggiungi attributo** selezionare l'opzione **basata su dominio** .</span><span class="sxs-lookup"><span data-stu-id="5bafc-124">On the **Add Attribute** page, select the **Domain-based** option.</span></span>  
  
8.  <span data-ttu-id="5bafc-125">Nella casella **Nome** digitare un nome per l'attributo.</span><span class="sxs-lookup"><span data-stu-id="5bafc-125">In the **Name** box, type a name for the attribute.</span></span> <span data-ttu-id="5bafc-126">Non deve essere lo stesso nome dell'entità che si utilizza per l'origine dei valori di attributo.</span><span class="sxs-lookup"><span data-stu-id="5bafc-126">It does not have to be the same name as the entity that you use for the source of the attribute values.</span></span>  
  
9. <span data-ttu-id="5bafc-127">Nella casella **Larghezza in pixel visualizzazione** digitare la larghezza della colonna attributo da visualizzare nella griglia **Esplora** .</span><span class="sxs-lookup"><span data-stu-id="5bafc-127">In the **Display pixel width** box, type the width of the attribute column to be displayed in the **Explorer** grid.</span></span>  
  
10. <span data-ttu-id="5bafc-128">Dall'elenco **entità** scegliere l'entità da usare per popolare i valori dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="5bafc-128">From the **Entity** list, choose the entity to be used to populate the attribute values.</span></span>  
  
11. <span data-ttu-id="5bafc-129">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="5bafc-129">Optional.</span></span> <span data-ttu-id="5bafc-130">Selezionare **Enable change tracking** per tenere traccia delle modifiche a gruppi di attributi.</span><span class="sxs-lookup"><span data-stu-id="5bafc-130">Select **Enable change tracking** to track changes to groups of attributes.</span></span> <span data-ttu-id="5bafc-131">Per altre informazioni, vedere [Aggiungere attributi ad un gruppo rilevamento modifiche &#40;Master Data Services&#41;](../../2014/master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="5bafc-131">For more information, see [Add Attributes to a Change Tracking Group &#40;Master Data Services&#41;](../../2014/master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md).</span></span>  
  
12. <span data-ttu-id="5bafc-132">Fare clic su **Salva attributo**.</span><span class="sxs-lookup"><span data-stu-id="5bafc-132">Click **Save attribute**.</span></span>  
  
13. <span data-ttu-id="5bafc-133">Nella pagina **Gestione entità** , fare clic su **Salva entità**.</span><span class="sxs-lookup"><span data-stu-id="5bafc-133">On the **Entity Maintenance** page, click **Save entity**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bafc-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5bafc-134">See Also</span></span>  
 <span data-ttu-id="5bafc-135">[Attributi basati su dominio &#40;Master Data Services&#41;](../../2014/master-data-services/domain-based-attributes-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="5bafc-135">[Domain-Based Attributes &#40;Master Data Services&#41;](../../2014/master-data-services/domain-based-attributes-master-data-services.md) </span></span>  
 <span data-ttu-id="5bafc-136">[Creare una gerarchia derivata &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-derived-hierarchy-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="5bafc-136">[Create a Derived Hierarchy &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-derived-hierarchy-master-data-services.md) </span></span>  
 <span data-ttu-id="5bafc-137">[Modificare il nome di un attributo &#40;Master Data Services&#41;](change-an-attribute-name-and-data-type-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="5bafc-137">[Change an Attribute Name &#40;Master Data Services&#41;](change-an-attribute-name-and-data-type-master-data-services.md) </span></span>  
 [<span data-ttu-id="5bafc-138">Eliminare un attributo &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="5bafc-138">Delete an Attribute &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/delete-an-attribute-master-data-services.md)  
  
  
