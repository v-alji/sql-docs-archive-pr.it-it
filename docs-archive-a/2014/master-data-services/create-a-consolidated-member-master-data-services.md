---
title: Creare membri consolidati (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- creating consolidated members [Master Data Services]
- members [Master Data Services], creating consolidated members
- consolidated members [Master Data Services], creating
ms.assetid: 431ab2d2-5517-4372-9980-142b05427c08
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c41673f6f3bf1f4de2a831ecd659321b273b6af9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718348"
---
# <a name="create-a-consolidated-member-master-data-services"></a><span data-ttu-id="0a8cb-102">Create a Consolidated Member (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="0a8cb-102">Create a Consolidated Member (Master Data Services)</span></span>
  <span data-ttu-id="0a8cb-103">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]creare un membro consolidato quando si desidera un nodo padre per una gerarchia esplicita.</span><span class="sxs-lookup"><span data-stu-id="0a8cb-103">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], create a consolidated member when you want a parent node for an explicit hierarchy.</span></span> <span data-ttu-id="0a8cb-104">I membri consolidati possono avere attributi specifici,</span><span class="sxs-lookup"><span data-stu-id="0a8cb-104">Consolidated members can have their own attributes.</span></span> <span data-ttu-id="0a8cb-105">che vengono usati per il raggruppamento.</span><span class="sxs-lookup"><span data-stu-id="0a8cb-105">They are used for grouping.</span></span> <span data-ttu-id="0a8cb-106">Come illustrato nell'esempio seguente, i membri consolidati possono essere usati per i gruppi di account che includono account sottostanti.</span><span class="sxs-lookup"><span data-stu-id="0a8cb-106">As shown in the following example, consolidated members can be used for account groups that have accounts under them.</span></span>

 <span data-ttu-id="0a8cb-107">![Membri consolidati MDS](../../2014/master-data-services/media/mds-consolidated-members.png "Membri consolidati MDS")</span><span class="sxs-lookup"><span data-stu-id="0a8cb-107">![MDS Consolidated Members](../../2014/master-data-services/media/mds-consolidated-members.png "MDS Consolidated Members")</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0a8cb-108">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="0a8cb-108">Prerequisites</span></span>
 <span data-ttu-id="0a8cb-109">Per eseguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="0a8cb-109">To perform this procedure:</span></span>

-   <span data-ttu-id="0a8cb-110">È necessario disporre dell'autorizzazione per accedere all'area funzionale **Esplora** .</span><span class="sxs-lookup"><span data-stu-id="0a8cb-110">You must have permission to access the **Explorer** functional area.</span></span>

-   <span data-ttu-id="0a8cb-111">È necessario disporre almeno dell'autorizzazione **Aggiornamento** per l'oggetto modello consolidato per l'entità a cui si desidera aggiungere un membro.</span><span class="sxs-lookup"><span data-stu-id="0a8cb-111">You must have a minimum of **Update** permission to the consolidated model object for the entity you are adding a member to.</span></span>

### <a name="to-create-a-consolidated-member"></a><span data-ttu-id="0a8cb-112">Per creare un membro consolidato</span><span class="sxs-lookup"><span data-stu-id="0a8cb-112">To create a consolidated member</span></span>

1.  <span data-ttu-id="0a8cb-113">Nella home page di [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] selezionare un modello nell'elenco **Modello** .</span><span class="sxs-lookup"><span data-stu-id="0a8cb-113">On the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] home page, from the **Model** list, select a model.</span></span>

2.  <span data-ttu-id="0a8cb-114">Selezionare una versione dall'elenco **Versione** .</span><span class="sxs-lookup"><span data-stu-id="0a8cb-114">From the **Version** list, select a version.</span></span>

3.  <span data-ttu-id="0a8cb-115">Fare clic su **Esplora**.</span><span class="sxs-lookup"><span data-stu-id="0a8cb-115">Click **Explorer**.</span></span>

4.  <span data-ttu-id="0a8cb-116">Dalla barra dei menu scegliere **Gerarchie** , quindi fare clic sul nome della gerarchia alla quale si desidera aggiungere un membro consolidato.</span><span class="sxs-lookup"><span data-stu-id="0a8cb-116">From the menu bar, point to **Hierarchies** and click the name of the hierarchy you want to add a consolidated member to.</span></span>

5.  <span data-ttu-id="0a8cb-117">Sopra la griglia, selezionare l'opzione **Membri consolidati** o **Tutti i membri consolidati nella gerarchia** .</span><span class="sxs-lookup"><span data-stu-id="0a8cb-117">Above the grid, select either the **Consolidated members** or the **All consolidated members in hierarchy** option.</span></span>

6.  <span data-ttu-id="0a8cb-118">Scegliere **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="0a8cb-118">Click **Add**.</span></span>

7.  <span data-ttu-id="0a8cb-119">Nel riquadro sulla destra, completare i campi.</span><span class="sxs-lookup"><span data-stu-id="0a8cb-119">In the pane on the right, complete the fields.</span></span>

8.  <span data-ttu-id="0a8cb-120">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="0a8cb-120">Optional.</span></span> <span data-ttu-id="0a8cb-121">Nella casella **Annotazioni** , digitare un commento indicando il perché è stato aggiunto il membro.</span><span class="sxs-lookup"><span data-stu-id="0a8cb-121">In the **Annotations** box, type a comment about why the member was added.</span></span> <span data-ttu-id="0a8cb-122">Tutti gli utenti che dispongono di accesso al membro possono visualizzare l'annotazione.</span><span class="sxs-lookup"><span data-stu-id="0a8cb-122">All users who have access to the member can view the annotation.</span></span>

9. <span data-ttu-id="0a8cb-123">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="0a8cb-123">Click **OK**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="0a8cb-124">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="0a8cb-124">Next Steps</span></span>

-   [<span data-ttu-id="0a8cb-125">Spostare i membri all'interno di una gerarchia &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="0a8cb-125">Move Members within a Hierarchy &#40;Master Data Services&#41;</span></span>](move-members-within-a-hierarchy-master-data-services.md)

## <a name="see-also"></a><span data-ttu-id="0a8cb-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0a8cb-126">See Also</span></span>
 <span data-ttu-id="0a8cb-127">[Creare una gerarchia esplicita &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-explicit-hierarchy-master-data-services.md) [creare un membro foglia &#40;Master Data Services](../../2014/master-data-services/create-a-leaf-member-master-data-services.md)&#41;[caricare o aggiornare membri in Master Data Services usando i membri del processo di gestione temporanea](add-update-and-delete-data-master-data-services.md) [&#40;](../../2014/master-data-services/members-master-data-services.md) Master Data Services&#41;[gerarchie esplicite](../../2014/master-data-services/explicit-hierarchies-master-data-services.md) &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="0a8cb-127">[Create an Explicit Hierarchy &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-explicit-hierarchy-master-data-services.md) [Create a Leaf Member &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-leaf-member-master-data-services.md) [Load or Update Members in Master Data Services by Using the Staging Process](add-update-and-delete-data-master-data-services.md) [Members &#40;Master Data Services&#41;](../../2014/master-data-services/members-master-data-services.md) [Explicit Hierarchies &#40;Master Data Services&#41;](../../2014/master-data-services/explicit-hierarchies-master-data-services.md)</span></span>


