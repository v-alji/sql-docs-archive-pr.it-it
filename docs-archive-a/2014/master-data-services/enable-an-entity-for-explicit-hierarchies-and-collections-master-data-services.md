---
title: Abilitare un'entità per le gerarchie esplicite e le raccolte (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- entities [Master Data Services], enabling for collections
- entities [Master Data Services], enabling for explicit hierarchies
ms.assetid: 380e77e5-ad60-43d4-9605-34a84525f5dd
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: a8129b3f67f050603f85ffb782a9dd209cb303fc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712076"
---
# <a name="enable-an-entity-for-explicit-hierarchies-and-collections-master-data-services"></a><span data-ttu-id="c55ef-102">Abilitare un'entità per gerarchie esplicite e raccolte (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="c55ef-102">Enable an Entity for Explicit Hierarchies and Collections (Master Data Services)</span></span>
  <span data-ttu-id="c55ef-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] abilitare un'entità per le gerarchie esplicite e le raccolte in modo che sia possibile creare gerarchie e raccolte per la stessa entità.</span><span class="sxs-lookup"><span data-stu-id="c55ef-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], enable an entity for explicit hierarchies and collections so that you can create explicit hierarchies and collections for the entity.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c55ef-104">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="c55ef-104">Prerequisites</span></span>  
 <span data-ttu-id="c55ef-105">Per eseguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="c55ef-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="c55ef-106">È necessario disporre di autorizzazione per accedere all'area funzionale **Amministrazione sistema** .</span><span class="sxs-lookup"><span data-stu-id="c55ef-106">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="c55ef-107">È necessario essere un amministratore del modello.</span><span class="sxs-lookup"><span data-stu-id="c55ef-107">You must be a model administrator.</span></span> <span data-ttu-id="c55ef-108">Per ulteriori informazioni, vedere [amministratori &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="c55ef-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="c55ef-109">Deve essere presente un'entità.</span><span class="sxs-lookup"><span data-stu-id="c55ef-109">An entity must exist.</span></span> <span data-ttu-id="c55ef-110">Per altre informazioni, vedere [Creare un'entità &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="c55ef-110">For more information, see [Create an Entity &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span></span>  
  
### <a name="to-enable-an-entity-for-explicit-hierarchies-and-collections"></a><span data-ttu-id="c55ef-111">Per abilitare un'entità per le gerarchie esplicite e le raccolte</span><span class="sxs-lookup"><span data-stu-id="c55ef-111">To enable an entity for explicit hierarchies and collections</span></span>  
  
1.  <span data-ttu-id="c55ef-112">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], fare clic su **Amministrazione sistema**.</span><span class="sxs-lookup"><span data-stu-id="c55ef-112">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="c55ef-113">Nella pagina **Vista modelli** scegliere **Gestisci** dalla barra dei menu, quindi fare clic su **Entità**.</span><span class="sxs-lookup"><span data-stu-id="c55ef-113">On the **Model View** page, from the menu bar, point to **Manage** and click **Entities**.</span></span>  
  
3.  <span data-ttu-id="c55ef-114">Nella pagina **Gestione entità** selezionare un modello dall'elenco **Modello** .</span><span class="sxs-lookup"><span data-stu-id="c55ef-114">On the **Entity Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="c55ef-115">Selezionare la riga relativa all'entità che si desidera aggiornare.</span><span class="sxs-lookup"><span data-stu-id="c55ef-115">Select the row for the entity that you want to update.</span></span>  
  
5.  <span data-ttu-id="c55ef-116">Fare clic su **Modifica entità selezionata**.</span><span class="sxs-lookup"><span data-stu-id="c55ef-116">Click **Edit selected entity**.</span></span>  
  
6.  <span data-ttu-id="c55ef-117">Dall'elenco **Abilita gerarchie esplicite e raccolte** selezionare **Sì**.</span><span class="sxs-lookup"><span data-stu-id="c55ef-117">From the **Enable explicit hierarchies and collections** list, select **Yes**.</span></span>  
  
7.  <span data-ttu-id="c55ef-118">Nella casella **nome gerarchia esplicita** Digitare un nome per una gerarchia esplicita.</span><span class="sxs-lookup"><span data-stu-id="c55ef-118">In the **Explicit hierarchy name** box, type a name for an explicit hierarchy.</span></span>  
  
8.  <span data-ttu-id="c55ef-119">Facoltativamente, deselezionare la casella di controllo **Gerarchia obbligatoria** per creare una gerarchia come non obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="c55ef-119">Optionally, clear the **Mandatory hierarchy** check box to create the hierarchy as a non-mandatory hierarchy.</span></span>  
  
9. <span data-ttu-id="c55ef-120">Fare clic su **Salva entità**.</span><span class="sxs-lookup"><span data-stu-id="c55ef-120">Click **Save entity**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="c55ef-121">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="c55ef-121">Next Steps</span></span>  
  
-   [<span data-ttu-id="c55ef-122">Creare una gerarchia esplicita &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="c55ef-122">Create an Explicit Hierarchy &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-an-explicit-hierarchy-master-data-services.md)  
  
-   [<span data-ttu-id="c55ef-123">Creare una raccolta &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="c55ef-123">Create a Collection &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-collection-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="c55ef-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c55ef-124">See Also</span></span>  
 <span data-ttu-id="c55ef-125">[Entità &#40;Master Data Services&#41;](../../2014/master-data-services/entities-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="c55ef-125">[Entities &#40;Master Data Services&#41;](../../2014/master-data-services/entities-master-data-services.md) </span></span>  
 <span data-ttu-id="c55ef-126">[Gerarchie esplicite &#40;Master Data Services&#41;](../../2014/master-data-services/explicit-hierarchies-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="c55ef-126">[Explicit Hierarchies &#40;Master Data Services&#41;](../../2014/master-data-services/explicit-hierarchies-master-data-services.md) </span></span>  
 [<span data-ttu-id="c55ef-127">Raccolte &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="c55ef-127">Collections &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/collections-master-data-services.md)  
  
  
