---
title: Creare una raccolta (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- creating collections [Master Data Services]
- collections [Master Data Services], creating
ms.assetid: 3d4f152c-863c-4385-bca9-a9fcd0402e1f
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: f76171b4fd9b07f751d4f919011a443253fbe31b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718365"
---
# <a name="create-a-collection-master-data-services"></a><span data-ttu-id="a75e0-102">Creare una raccolta (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="a75e0-102">Create a Collection (Master Data Services)</span></span>
  <span data-ttu-id="a75e0-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]creare una raccolta quando si vuole creare elenchi semplici di membri foglia e membri consolidati.</span><span class="sxs-lookup"><span data-stu-id="a75e0-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], create a collection when you want to create flat lists of leaf and consolidated members.</span></span> <span data-ttu-id="a75e0-104">Non è necessario includere nelle raccolte tutti i membri dell'entità.</span><span class="sxs-lookup"><span data-stu-id="a75e0-104">Collections do not need to include all members from the entity.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a75e0-105">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="a75e0-105">Prerequisites</span></span>  
 <span data-ttu-id="a75e0-106">Per eseguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="a75e0-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="a75e0-107">È necessario disporre dell'autorizzazione per accedere all'area funzionale **Esplora** .</span><span class="sxs-lookup"><span data-stu-id="a75e0-107">You must have permission to access the **Explorer** functional area.</span></span>  
  
-   <span data-ttu-id="a75e0-108">È necessario disporre almeno dell'autorizzazione **Update** per l'oggetto modello della raccolta per l'entità.</span><span class="sxs-lookup"><span data-stu-id="a75e0-108">You must have a minimum of **Update** permission to the collection model object for the entity.</span></span>  
  
-   <span data-ttu-id="a75e0-109">È necessario abilitare l'entità per le gerarchie esplicite e le raccolte.</span><span class="sxs-lookup"><span data-stu-id="a75e0-109">The entity must be enabled for explicit hierarchies and collections.</span></span> <span data-ttu-id="a75e0-110">Per altre informazioni, vedere [abilitare un'entità per gerarchie esplicite e raccolte &#40;Master Data Services&#41;](enable-an-entity-for-explicit-hierarchies-and-collections-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="a75e0-110">For more information, see [Enable an Entity for Explicit Hierarchies and Collections &#40;Master Data Services&#41;](enable-an-entity-for-explicit-hierarchies-and-collections-master-data-services.md).</span></span>  
  
### <a name="to-create-a-collection"></a><span data-ttu-id="a75e0-111">Per creare una raccolta</span><span class="sxs-lookup"><span data-stu-id="a75e0-111">To create a collection</span></span>  
  
1.  <span data-ttu-id="a75e0-112">Nella home page di [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] selezionare un modello nell'elenco **Modello** .</span><span class="sxs-lookup"><span data-stu-id="a75e0-112">On the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] home page, from the **Model** list, select a model.</span></span>  
  
2.  <span data-ttu-id="a75e0-113">Selezionare una versione dall'elenco **Versione** .</span><span class="sxs-lookup"><span data-stu-id="a75e0-113">From the **Version** list, select a version.</span></span>  
  
3.  <span data-ttu-id="a75e0-114">Fare clic su **Esplora**.</span><span class="sxs-lookup"><span data-stu-id="a75e0-114">Click **Explorer**.</span></span>  
  
4.  <span data-ttu-id="a75e0-115">Dalla barra dei menu scegliere **Raccolte** e fare clic su *nome_entità*.</span><span class="sxs-lookup"><span data-stu-id="a75e0-115">From the menu bar, point to **Collections** and click *entity_name*.</span></span>  
  
5.  <span data-ttu-id="a75e0-116">Fare clic su **Aggiungi raccolta**.</span><span class="sxs-lookup"><span data-stu-id="a75e0-116">Click **Add collection**.</span></span>  
  
6.  <span data-ttu-id="a75e0-117">Nella scheda **Dettagli** digitare un nome per la raccolta nella casella **Nome** .</span><span class="sxs-lookup"><span data-stu-id="a75e0-117">On the **Details** tab, in the **Name** box, type a name for the collection.</span></span>  
  
7.  <span data-ttu-id="a75e0-118">Nella casella **Codice** digitare un codice univoco per la raccolta.</span><span class="sxs-lookup"><span data-stu-id="a75e0-118">In the **Code** box, type a unique code for the collection.</span></span>  
  
8.  <span data-ttu-id="a75e0-119">Facoltativamente, digitare una descrizione per la raccolta nella casella **Descrizione** .</span><span class="sxs-lookup"><span data-stu-id="a75e0-119">Optionally, in the **Description** box, type a description for the collection.</span></span>  
  
9. <span data-ttu-id="a75e0-120">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="a75e0-120">Click **OK**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="a75e0-121">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="a75e0-121">Next Steps</span></span>  
  
-   [<span data-ttu-id="a75e0-122">Aggiungere membri a una raccolta &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="a75e0-122">Add Members to a Collection &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/add-members-to-a-collection-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="a75e0-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a75e0-123">See Also</span></span>  
 <span data-ttu-id="a75e0-124">[Raccolte &#40;Master Data Services&#41;](../../2014/master-data-services/collections-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="a75e0-124">[Collections &#40;Master Data Services&#41;](../../2014/master-data-services/collections-master-data-services.md) </span></span>  
 <span data-ttu-id="a75e0-125">[Eliminare un membro o una raccolta &#40;Master Data Services&#41;](../../2014/master-data-services/delete-a-member-or-collection-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="a75e0-125">[Delete a Member or Collection &#40;Master Data Services&#41;](../../2014/master-data-services/delete-a-member-or-collection-master-data-services.md) </span></span>  
 [<span data-ttu-id="a75e0-126">Creare una gerarchia esplicita &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="a75e0-126">Create an Explicit Hierarchy &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-an-explicit-hierarchy-master-data-services.md)  
  
  
