---
title: Eliminare una gerarchia esplicita (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- explicit hierarchies, deleting
- deleting explicit hierarchies [Master Data Services]
ms.assetid: 4ce177b0-9884-47a2-9cea-212e845dd762
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 744f96a2705a3abbc2318ecd3c9b0c7fffb7605e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638444"
---
# <a name="delete-an-explicit-hierarchy-master-data-services"></a><span data-ttu-id="18fad-102">Eliminare una gerarchia esplicita (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="18fad-102">Delete an Explicit Hierarchy (Master Data Services)</span></span>
  <span data-ttu-id="18fad-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]eliminare una gerarchia esplicita quando non è più necessaria.</span><span class="sxs-lookup"><span data-stu-id="18fad-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], delete an explicit hierarchy when you no longer need it.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="18fad-104">Quando si elimina una gerarchia esplicita, vengono eliminati anche tutti i membri consolidati in essa contenuti.</span><span class="sxs-lookup"><span data-stu-id="18fad-104">When you delete an explicit hierarchy, all consolidated members in the hierarchy are deleted also.</span></span> <span data-ttu-id="18fad-105">Se si eliminano tutte le gerarchie esplicite per un'entità, vengono eliminate anche tutte le raccolte dell'entità e quest'ultima non è più abilitata per le raccolte e le gerarchie esplicite.</span><span class="sxs-lookup"><span data-stu-id="18fad-105">If you delete all explicit hierarchies for an entity, all collections for the entity are also deleted and the entity is no longer enabled for explicit hierarchies and collections.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="18fad-106">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="18fad-106">Prerequisites</span></span>  
 <span data-ttu-id="18fad-107">Per eseguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="18fad-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="18fad-108">È necessario disporre di autorizzazione per accedere all'area funzionale **Amministrazione sistema** .</span><span class="sxs-lookup"><span data-stu-id="18fad-108">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="18fad-109">È necessario essere un amministratore del modello.</span><span class="sxs-lookup"><span data-stu-id="18fad-109">You must be a model administrator.</span></span> <span data-ttu-id="18fad-110">Per ulteriori informazioni, vedere [amministratori &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="18fad-110">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-delete-an-explicit-hierarchy"></a><span data-ttu-id="18fad-111">Per eliminare una gerarchia esplicita</span><span class="sxs-lookup"><span data-stu-id="18fad-111">To delete an explicit hierarchy</span></span>  
  
1.  <span data-ttu-id="18fad-112">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], fare clic su **Amministrazione sistema**.</span><span class="sxs-lookup"><span data-stu-id="18fad-112">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="18fad-113">Nella pagina **Vista modelli** scegliere **Gestisci** dalla barra dei menu, quindi fare clic su **Entità**.</span><span class="sxs-lookup"><span data-stu-id="18fad-113">On the **Model View** page, from the menu bar, point to **Manage** and click **Entities**.</span></span>  
  
3.  <span data-ttu-id="18fad-114">Nella pagina **Gestione entità** selezionare un modello dall'elenco **Modello** .</span><span class="sxs-lookup"><span data-stu-id="18fad-114">On the **Entity Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="18fad-115">Selezionare la riga relativa all'entità contenente la gerarchia esplicita da eliminare.</span><span class="sxs-lookup"><span data-stu-id="18fad-115">Select the row for the entity that contains the explicit hierarchy you want to delete.</span></span>  
  
5.  <span data-ttu-id="18fad-116">Fare clic su **Modifica entità selezionata**.</span><span class="sxs-lookup"><span data-stu-id="18fad-116">Click **Edit selected entity**.</span></span>  
  
6.  <span data-ttu-id="18fad-117">Nel riquadro **gerarchie esplicite** della pagina **Modifica entità** fare clic sulla gerarchia esplicita che si desidera eliminare.</span><span class="sxs-lookup"><span data-stu-id="18fad-117">On the **Edit Entity** page, in the **Explicit Hierarchies** pane, click the explicit hierarchy you want to delete.</span></span>  
  
7.  <span data-ttu-id="18fad-118">Fare clic su **Elimina gerarchia selezionata**.</span><span class="sxs-lookup"><span data-stu-id="18fad-118">Click **Delete selected hierarchy**.</span></span>  
  
8.  <span data-ttu-id="18fad-119">Nella finestra di dialogo di conferma fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="18fad-119">In the confirmation dialog box, click **OK**.</span></span>  
  
9. <span data-ttu-id="18fad-120">Nell'ulteriore finestra di dialogo di conferma fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="18fad-120">In the additional confirmation dialog box, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18fad-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="18fad-121">See Also</span></span>  
 <span data-ttu-id="18fad-122">[Creare una gerarchia esplicita &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-explicit-hierarchy-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="18fad-122">[Create an Explicit Hierarchy &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-explicit-hierarchy-master-data-services.md) </span></span>  
 [<span data-ttu-id="18fad-123">Gerarchie esplicite &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="18fad-123">Explicit Hierarchies &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/explicit-hierarchies-master-data-services.md)  
  
  
