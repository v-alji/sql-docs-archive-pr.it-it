---
title: Eliminare un membro o una raccolta (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- collections [Master Data Services], deleting
- leaf members [Master Data Services], deleting
- deleting members [Master Data Services]
- members [Master Data Services], deleting
- consolidated members [Master Data Services], deleting
ms.assetid: 519130a7-4226-4d71-9124-d2ee0ce7e5bd
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 9b248750c0e755c3fc9e32d45068c754e64957b7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712100"
---
# <a name="delete-a-member-or-collection-master-data-services"></a><span data-ttu-id="d0ef9-102">Eliminare un membro o una raccolta (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="d0ef9-102">Delete a Member or Collection (Master Data Services)</span></span>
  <span data-ttu-id="d0ef9-103">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]eliminare un membro o una raccolta quando non è più necessaria.</span><span class="sxs-lookup"><span data-stu-id="d0ef9-103">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], delete a member or collection when you no longer need it.</span></span> <span data-ttu-id="d0ef9-104">Se si desidera eliminare i membri in bulk, utilizzare invece il processo di gestione temporanea.</span><span class="sxs-lookup"><span data-stu-id="d0ef9-104">If you want to delete members in bulk, use the staging process instead.</span></span> <span data-ttu-id="d0ef9-105">Per ulteriori informazioni, vedere [disattivare o eliminare membri utilizzando il processo di gestione temporanea &#40;Master Data Services&#41;](add-update-and-delete-data-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="d0ef9-105">For more information, see [Deactivate or Delete Members by Using the Staging Process &#40;Master Data Services&#41;](add-update-and-delete-data-master-data-services.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d0ef9-106">Non è possibile eliminare un membro se viene utilizzato come valore dell'attributo basato su dominio per un altro membro.</span><span class="sxs-lookup"><span data-stu-id="d0ef9-106">You cannot delete a member if it is used as a domain-based attribute value for another member.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d0ef9-107">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="d0ef9-107">Prerequisites</span></span>  
 <span data-ttu-id="d0ef9-108">Per eseguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="d0ef9-108">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="d0ef9-109">È necessario disporre dell'autorizzazione per accedere all'area funzionale **Esplora** .</span><span class="sxs-lookup"><span data-stu-id="d0ef9-109">You must have permission to access the **Explorer** functional area.</span></span>  
  
-   <span data-ttu-id="d0ef9-110">Per i membri, è necessario disporre almeno dell'autorizzazione **aggiornamento** per l'oggetto modello foglia da cui si desidera eliminare un membro.</span><span class="sxs-lookup"><span data-stu-id="d0ef9-110">For members, you must have a minimum of **Update** permission to the leaf model object you are deleting a member from.</span></span>  
  
-   <span data-ttu-id="d0ef9-111">Per le raccolte, è necessario disporre almeno dell'autorizzazione **Aggiornamento** per l'oggetto raccolta foglia in fase di eliminazione.</span><span class="sxs-lookup"><span data-stu-id="d0ef9-111">For collections, you must have a minimum of **Update** permission to the leaf collection object you are deleting.</span></span>  
  
### <a name="to-delete-a-member-or-collection"></a><span data-ttu-id="d0ef9-112">Per eliminare un membro o una raccolta</span><span class="sxs-lookup"><span data-stu-id="d0ef9-112">To delete a member or collection</span></span>  
  
1.  <span data-ttu-id="d0ef9-113">Nella home page di [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] selezionare un modello nell'elenco **Modello** .</span><span class="sxs-lookup"><span data-stu-id="d0ef9-113">On the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] home page, from the **Model** list, select a model.</span></span>  
  
2.  <span data-ttu-id="d0ef9-114">Selezionare una versione dall'elenco **Versione** .</span><span class="sxs-lookup"><span data-stu-id="d0ef9-114">From the **Version** list, select a version.</span></span>  
  
3.  <span data-ttu-id="d0ef9-115">Fare clic su **Esplora**.</span><span class="sxs-lookup"><span data-stu-id="d0ef9-115">Click **Explorer**.</span></span>  
  
4.  <span data-ttu-id="d0ef9-116">Per eliminare:</span><span class="sxs-lookup"><span data-stu-id="d0ef9-116">To delete:</span></span>  
  
    -   <span data-ttu-id="d0ef9-117">Un membro foglia, scegliere **Entità** dalla barra dei menu, quindi fare clic sul nome dell'entità che contiene il membro.</span><span class="sxs-lookup"><span data-stu-id="d0ef9-117">A leaf member, from the menu bar, point to **Entities** and click the name of the entity that contains the member.</span></span>  
  
    -   <span data-ttu-id="d0ef9-118">Un membro consolidato, scegliere **Gerarchie** dalla barra dei menu, quindi fare clic sul nome della gerarchia che contiene il membro.</span><span class="sxs-lookup"><span data-stu-id="d0ef9-118">A consolidated member, from the menu bar, point to **Hierarchies** and click the name of the hierarchy that contains the member.</span></span> <span data-ttu-id="d0ef9-119">Quindi fare clic sul nodo nella gerarchia che contiene il membro.</span><span class="sxs-lookup"><span data-stu-id="d0ef9-119">Then click the node in the hierarchy that contains the member.</span></span>  
  
    -   <span data-ttu-id="d0ef9-120">Una raccolta, scegliere **Raccolte** dalla barra dei menu, quindi fare clic sul nome dell'entità che contiene la raccolta.</span><span class="sxs-lookup"><span data-stu-id="d0ef9-120">A collection, from the menu bar, point to **Collections** and click the name of the entity that contains the collection.</span></span>  
  
5.  <span data-ttu-id="d0ef9-121">Nella griglia fare clic sulla riga del membro o della raccolta che si desidera eliminare.</span><span class="sxs-lookup"><span data-stu-id="d0ef9-121">In the grid, click the row of the member or collection you want to delete.</span></span>  
  
6.  <span data-ttu-id="d0ef9-122">Fare clic su **Elimina membro**, **Elimina**o **Elimina raccolta**.</span><span class="sxs-lookup"><span data-stu-id="d0ef9-122">Click **Delete Member**, **Delete**, or **Delete Collection**.</span></span>  
  
7.  <span data-ttu-id="d0ef9-123">Nella finestra di dialogo di conferma fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d0ef9-123">In the confirmation dialog box, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0ef9-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d0ef9-124">See Also</span></span>  
 <span data-ttu-id="d0ef9-125">[Riattivare un membro o una raccolta &#40;Master Data Services&#41;](../../2014/master-data-services/reactivate-a-member-or-collection-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="d0ef9-125">[Reactivate a Member or Collection &#40;Master Data Services&#41;](../../2014/master-data-services/reactivate-a-member-or-collection-master-data-services.md) </span></span>  
 <span data-ttu-id="d0ef9-126">[Membri &#40;Master Data Services&#41;](../../2014/master-data-services/members-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="d0ef9-126">[Members &#40;Master Data Services&#41;](../../2014/master-data-services/members-master-data-services.md) </span></span>  
 [<span data-ttu-id="d0ef9-127">Raccolte &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="d0ef9-127">Collections &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/collections-master-data-services.md)  
  
  
