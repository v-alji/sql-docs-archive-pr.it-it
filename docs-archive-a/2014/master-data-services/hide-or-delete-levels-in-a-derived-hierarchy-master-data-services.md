---
title: Nascondere o eliminare i livelli di una gerarchia derivata (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- derived hierarchies, hiding levels
- derived hierarchies, deleting levels
ms.assetid: e00582b9-9415-4b66-b4a7-9f590d83875f
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 039b05633bcd1fdc69d226e565b3dc5211e9734f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629889"
---
# <a name="hide-or-delete-levels-in-a-derived-hierarchy-master-data-services"></a><span data-ttu-id="3981b-102">Nascondere o eliminare livelli di una gerarchia derivata (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="3981b-102">Hide or Delete Levels in a Derived Hierarchy (Master Data Services)</span></span>
  <span data-ttu-id="3981b-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]è possibile nascondere un livello di una gerarchia derivata quando è necessario per il raggruppamento ma non si vuole visualizzarlo.</span><span class="sxs-lookup"><span data-stu-id="3981b-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], hide a level in a derived hierarchy when you require the level for grouping but you do not need to show the level.</span></span> <span data-ttu-id="3981b-104">Eliminare un livello quando non si desidera utilizzarlo per il raggruppamento.</span><span class="sxs-lookup"><span data-stu-id="3981b-104">Delete a level when you do not want to use it for grouping.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="3981b-105">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="3981b-105">Prerequisites</span></span>  
 <span data-ttu-id="3981b-106">Per eseguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="3981b-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="3981b-107">È necessario disporre di autorizzazione per accedere all'area funzionale **Amministrazione sistema** .</span><span class="sxs-lookup"><span data-stu-id="3981b-107">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="3981b-108">È necessario essere un amministratore del modello.</span><span class="sxs-lookup"><span data-stu-id="3981b-108">You must be a model administrator.</span></span> <span data-ttu-id="3981b-109">Per ulteriori informazioni, vedere [amministratori &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="3981b-109">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-hide-or-delete-levels-in-a-derived-hierarchy"></a><span data-ttu-id="3981b-110">Per nascondere o eliminare i livelli di una gerarchia derivata</span><span class="sxs-lookup"><span data-stu-id="3981b-110">To hide or delete levels in a derived hierarchy</span></span>  
  
1.  <span data-ttu-id="3981b-111">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], fare clic su **Amministrazione sistema**.</span><span class="sxs-lookup"><span data-stu-id="3981b-111">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="3981b-112">Nella pagina **vista modelli** scegliere **Gestisci** dalla barra dei menu, quindi fare clic su **gerarchie derivate**.</span><span class="sxs-lookup"><span data-stu-id="3981b-112">On the **Model View** page, from the menu bar, point to **Manage** and click **Derived Hierarchies**.</span></span>  
  
3.  <span data-ttu-id="3981b-113">Nella pagina **Gestione gerarchia derivata** selezionare un modello dall'elenco **Modello** .</span><span class="sxs-lookup"><span data-stu-id="3981b-113">On the **Derived Hierarchy Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="3981b-114">Selezionare la riga relativa alla gerarchia derivata da modificare.</span><span class="sxs-lookup"><span data-stu-id="3981b-114">Select the row for the derived hierarchy you want to edit.</span></span>  
  
5.  <span data-ttu-id="3981b-115">Fare clic su **Modifica gerarchia derivata selezionata**.</span><span class="sxs-lookup"><span data-stu-id="3981b-115">Click **Edit selected derived hierarchy**.</span></span>  
  
6.  <span data-ttu-id="3981b-116">Nel riquadro **Livelli correnti** :</span><span class="sxs-lookup"><span data-stu-id="3981b-116">In the **Current Levels** pane:</span></span>  
  
    -   <span data-ttu-id="3981b-117">Per nascondere un livello, fare clic su un livello diverso quello superiore o inferiore.</span><span class="sxs-lookup"><span data-stu-id="3981b-117">To hide a level, click a level other than the top or bottom.</span></span> <span data-ttu-id="3981b-118">Nell'elenco **Visibile** selezionare **No**.</span><span class="sxs-lookup"><span data-stu-id="3981b-118">From the **Visible** list, select **No**.</span></span> <span data-ttu-id="3981b-119">Quindi fare clic su **Salva elemento gerarchia selezionato**.</span><span class="sxs-lookup"><span data-stu-id="3981b-119">Then click **Save selected hierarchy item**.</span></span>  
  
    -   <span data-ttu-id="3981b-120">Per eliminare il livello superiore, fare clic su **Elimina elemento gerarchia selezionato**.</span><span class="sxs-lookup"><span data-stu-id="3981b-120">To delete the top level, click **Delete selected hierarchy item**.</span></span> <span data-ttu-id="3981b-121">Nella finestra di dialogo di conferma fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="3981b-121">In the confirmation dialog box, click **OK**.</span></span> <span data-ttu-id="3981b-122">È possibile eliminare solo il livello superiore.</span><span class="sxs-lookup"><span data-stu-id="3981b-122">You can delete the top level only.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3981b-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3981b-123">See Also</span></span>  
 <span data-ttu-id="3981b-124">[Spostare i membri all'interno di una gerarchia &#40;Master Data Services&#41;](../../2014/master-data-services/move-members-within-a-hierarchy-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="3981b-124">[Move Members within a Hierarchy &#40;Master Data Services&#41;](../../2014/master-data-services/move-members-within-a-hierarchy-master-data-services.md) </span></span>  
 [<span data-ttu-id="3981b-125">Gerarchie derivate &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="3981b-125">Derived Hierarchies &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/derived-hierarchies-master-data-services.md)  
  
  
