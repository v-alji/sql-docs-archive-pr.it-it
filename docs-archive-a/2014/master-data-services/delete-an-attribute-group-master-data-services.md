---
title: Eliminare un gruppo di attributi (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- deleting attribute groups [Master Data Services]
- attribute groups [Master Data Services], deleting
ms.assetid: f915e89b-629d-4725-aea6-a7f051978244
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 833c5cf327034b25d68af123a1fc134372bd6f10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637396"
---
# <a name="delete-an-attribute-group-master-data-services"></a><span data-ttu-id="dd149-102">Eliminare un gruppo di attributi (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="dd149-102">Delete an Attribute Group (Master Data Services)</span></span>
  <span data-ttu-id="dd149-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]è possibile eliminare un gruppo di attributi quando non è più necessario visualizzare la scheda nell'area funzionale **Visualizzatore** di [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dd149-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], delete an attribute group when you no longer need the tab to display in the **Explorer** functional area of [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span></span>  
  
-   <span data-ttu-id="dd149-104">**Nota** Se sono presenti gruppi di attributi, gli attributi che non appartengono a un gruppo non saranno visualizzati nel **Visualizzatore**.</span><span class="sxs-lookup"><span data-stu-id="dd149-104">**Note** When attribute groups exist, attributes that do not belong to an attribute group are not displayed in **Explorer**.</span></span> <span data-ttu-id="dd149-105">Quando non sono presenti gruppi di attributi, vengono visualizzati tutti gli attributi.</span><span class="sxs-lookup"><span data-stu-id="dd149-105">When no attribute groups exist, all attributes are displayed.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="dd149-106">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="dd149-106">Prerequisites</span></span>  
 <span data-ttu-id="dd149-107">Per eseguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="dd149-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="dd149-108">È necessario disporre di autorizzazione per accedere all'area funzionale **Amministrazione sistema** .</span><span class="sxs-lookup"><span data-stu-id="dd149-108">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="dd149-109">È necessario essere un amministratore del modello.</span><span class="sxs-lookup"><span data-stu-id="dd149-109">You must be a model administrator.</span></span> <span data-ttu-id="dd149-110">Per ulteriori informazioni, vedere [amministratori &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="dd149-110">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-delete-an-attribute-group"></a><span data-ttu-id="dd149-111">Per eliminare un gruppo di attributi</span><span class="sxs-lookup"><span data-stu-id="dd149-111">To delete an attribute group</span></span>  
  
1.  <span data-ttu-id="dd149-112">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], fare clic su **Amministrazione sistema**.</span><span class="sxs-lookup"><span data-stu-id="dd149-112">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="dd149-113">Nella pagina **vista modelli** scegliere **Gestisci** dalla barra dei menu, quindi fare clic su **gruppi di attributi**.</span><span class="sxs-lookup"><span data-stu-id="dd149-113">On the **Model View** page, from the menu bar, point to **Manage** and click **Attribute Groups**.</span></span>  
  
3.  <span data-ttu-id="dd149-114">Selezionare un modello dall'elenco **Modello** .</span><span class="sxs-lookup"><span data-stu-id="dd149-114">From the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="dd149-115">Dall'elenco **Entità** selezionare un'entità.</span><span class="sxs-lookup"><span data-stu-id="dd149-115">From the **Entity** list, select an entity.</span></span>  
  
5.  <span data-ttu-id="dd149-116">Fare clic sul segno più per espandere **gruppi foglia**, **gruppi consolidati**o **gruppi di raccolte**, a seconda del tipo di gruppo che si desidera eliminare.</span><span class="sxs-lookup"><span data-stu-id="dd149-116">Click the plus sign to expand **Leaf Groups**, **Consolidated Groups**, or **Collection Groups**, depending on the type of group you want to delete.</span></span>  
  
6.  <span data-ttu-id="dd149-117">Fare clic sul gruppo di attributi che si desidera eliminare.</span><span class="sxs-lookup"><span data-stu-id="dd149-117">Click the attribute group you want to delete.</span></span>  
  
7.  <span data-ttu-id="dd149-118">Fare clic su **Elimina gruppo selezionato**.</span><span class="sxs-lookup"><span data-stu-id="dd149-118">Click **Delete selected group**.</span></span>  
  
8.  <span data-ttu-id="dd149-119">Nella finestra di dialogo di conferma fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="dd149-119">In the confirmation dialog box, click **OK**.</span></span>  
  
9. <span data-ttu-id="dd149-120">Nell'ulteriore finestra di dialogo di conferma fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="dd149-120">In the additional confirmation dialog box, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd149-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dd149-121">See Also</span></span>  
 <span data-ttu-id="dd149-122">[Gruppi di attributi &#40;Master Data Services&#41;](../../2014/master-data-services/attribute-groups-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="dd149-122">[Attribute Groups &#40;Master Data Services&#41;](../../2014/master-data-services/attribute-groups-master-data-services.md) </span></span>  
 [<span data-ttu-id="dd149-123">Creare un gruppo di attributi &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="dd149-123">Create an Attribute Group &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-an-attribute-group-master-data-services.md)  
  
  
