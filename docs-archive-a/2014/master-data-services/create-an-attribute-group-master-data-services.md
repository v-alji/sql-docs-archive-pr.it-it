---
title: Creare un gruppo di attributi (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- attribute groups [Master Data Services], creating
- creating attribute groups [Master Data Services]
ms.assetid: 798c325e-e8d8-412a-b02e-118f2741d1c7
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: fbd95869082ea0a73f3abea092163c4705e4da5c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721543"
---
# <a name="create-an-attribute-group-master-data-services"></a><span data-ttu-id="2e00e-102">Creare un gruppo di attributi (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="2e00e-102">Create an Attribute Group (Master Data Services)</span></span>
  <span data-ttu-id="2e00e-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]creare gruppi di attributi quando si desidera che gli attributi vengano visualizzati in schede singole nella griglia **Esplora** .</span><span class="sxs-lookup"><span data-stu-id="2e00e-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], create attribute groups when you want to display attributes on individual tabs in the **Explorer** grid.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2e00e-104">Quando si crea un gruppo di attributi, questo viene automaticamente nascosto a tutti gli utenti ad eccezione di quello che lo creato.</span><span class="sxs-lookup"><span data-stu-id="2e00e-104">When you create an attribute group, it is automatically hidden from all users except the one who created it.</span></span> <span data-ttu-id="2e00e-105">Per altre informazioni su come rendere visibile un gruppo, vedere [Rendere visibile un gruppo di attributi per gli utenti &#40;Master Data Services&#41;](make-an-attribute-group-visible-to-users-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="2e00e-105">For more information about making the group visible, see [Make an Attribute Group Visible to Users &#40;Master Data Services&#41;](make-an-attribute-group-visible-to-users-master-data-services.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="2e00e-106">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="2e00e-106">Prerequisites</span></span>  
 <span data-ttu-id="2e00e-107">Per eseguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="2e00e-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="2e00e-108">È necessario disporre di autorizzazione per accedere all'area funzionale **Amministrazione sistema** .</span><span class="sxs-lookup"><span data-stu-id="2e00e-108">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="2e00e-109">È necessario essere un amministratore del modello.</span><span class="sxs-lookup"><span data-stu-id="2e00e-109">You must be a model administrator.</span></span> <span data-ttu-id="2e00e-110">Per ulteriori informazioni, vedere [amministratori &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="2e00e-110">For more information, see [Administrators &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="2e00e-111">È necessario che esista almeno un attributo.</span><span class="sxs-lookup"><span data-stu-id="2e00e-111">At least one attribute must exist.</span></span> <span data-ttu-id="2e00e-112">Per altre informazioni, vedere [Creare un attributo di testo &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-text-attribute-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="2e00e-112">For more information, see [Create a Text Attribute &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-text-attribute-master-data-services.md).</span></span>  
  
### <a name="to-create-an-attribute-group"></a><span data-ttu-id="2e00e-113">Per creare un gruppo di attributi</span><span class="sxs-lookup"><span data-stu-id="2e00e-113">To create an attribute group</span></span>  
  
1.  <span data-ttu-id="2e00e-114">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], fare clic su **Amministrazione sistema**.</span><span class="sxs-lookup"><span data-stu-id="2e00e-114">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="2e00e-115">Nella pagina **vista modelli** scegliere **Gestisci** dalla barra dei menu, quindi fare clic su **gruppi di attributi**.</span><span class="sxs-lookup"><span data-stu-id="2e00e-115">On the **Model View** page, from the menu bar, point to **Manage** and click **Attribute Groups**.</span></span>  
  
3.  <span data-ttu-id="2e00e-116">Selezionare un modello dall'elenco **Modello** .</span><span class="sxs-lookup"><span data-stu-id="2e00e-116">From the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="2e00e-117">Dall'elenco **Entità** selezionare un'entità.</span><span class="sxs-lookup"><span data-stu-id="2e00e-117">From the **Entity** list, select an entity.</span></span>  
  
5.  <span data-ttu-id="2e00e-118">Fare clic su **Gruppi di foglie**, **Gruppi consolidati**o **Gruppi di raccolte** per creare rispettivamente un gruppo di attributi per membri foglia, membri consolidati o raccolte.</span><span class="sxs-lookup"><span data-stu-id="2e00e-118">Click **Leaf Groups**, **Consolidated Groups**, or **Collection Groups** to create an attribute group of leaf members, consolidated members, or collections respectively.</span></span>  
  
6.  <span data-ttu-id="2e00e-119">Fare clic su **Aggiungi gruppo di attributi**.</span><span class="sxs-lookup"><span data-stu-id="2e00e-119">Click **Add attribute group**.</span></span>  
  
7.  <span data-ttu-id="2e00e-120">Nella casella **nome gruppo foglia** Digitare un nome per il gruppo.</span><span class="sxs-lookup"><span data-stu-id="2e00e-120">In the **Leaf group name** box, type a name for the group.</span></span> <span data-ttu-id="2e00e-121">Si tratta del nome visualizzato nella scheda in **Esplora**.</span><span class="sxs-lookup"><span data-stu-id="2e00e-121">This is the name displayed on the tab in **Explorer**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2e00e-122">Se nel passaggio 5 sono stati selezionati **gruppi consolidati** o **gruppi di raccolte** , questa casella corrisponde rispettivamente al nome del **gruppo consolidato** o al **nome del gruppo di raccolte**.</span><span class="sxs-lookup"><span data-stu-id="2e00e-122">If you selected **Consolidated Groups** or **Collection Groups** in step 5, this box is **Consolidated group name** or **Collection group name**, respectively.</span></span>  
  
8.  <span data-ttu-id="2e00e-123">Fare clic su **Salva gruppo**.</span><span class="sxs-lookup"><span data-stu-id="2e00e-123">Click **Save group**.</span></span>  
  
9. <span data-ttu-id="2e00e-124">Espandere la cartella relativa al gruppo.</span><span class="sxs-lookup"><span data-stu-id="2e00e-124">Expand the folder for the group.</span></span>  
  
10. <span data-ttu-id="2e00e-125">Fare clic su **Attributi**.</span><span class="sxs-lookup"><span data-stu-id="2e00e-125">Click **Attributes**.</span></span>  
  
11. <span data-ttu-id="2e00e-126">Fare clic su **modifica elemento selezionato**.</span><span class="sxs-lookup"><span data-stu-id="2e00e-126">Click **Edit selected item**.</span></span>  
  
12. <span data-ttu-id="2e00e-127">Fare clic su attributi nella casella **disponibile** e fare clic sulla freccia **Aggiungi** .</span><span class="sxs-lookup"><span data-stu-id="2e00e-127">Click attributes in the **Available** box and click the **Add** arrow.</span></span> <span data-ttu-id="2e00e-128">Per aggiungere tutto, fare clic sulla freccia **Aggiungi tutto** .</span><span class="sxs-lookup"><span data-stu-id="2e00e-128">To add all, click the **Add All** arrow.</span></span>  
  
13. <span data-ttu-id="2e00e-129">Facoltativamente, fare clic sulle frecce **su** e **giù** per modificare l'ordine degli attributi da sinistra a destra.</span><span class="sxs-lookup"><span data-stu-id="2e00e-129">Optionally, click the **Up** and **Down** arrows to change the left-to-right order of the attributes.</span></span>  
  
14. <span data-ttu-id="2e00e-130">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="2e00e-130">Click **Save**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="2e00e-131">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="2e00e-131">Next Steps</span></span>  
  
-   [<span data-ttu-id="2e00e-132">Rendere visibile un gruppo di attributi per gli utenti &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="2e00e-132">Make an Attribute Group Visible to Users &#40;Master Data Services&#41;</span></span>](make-an-attribute-group-visible-to-users-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="2e00e-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2e00e-133">See Also</span></span>  
 <span data-ttu-id="2e00e-134">[Gruppi di attributi &#40;Master Data Services&#41;](../../2014/master-data-services/attribute-groups-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="2e00e-134">[Attribute Groups &#40;Master Data Services&#41;](../../2014/master-data-services/attribute-groups-master-data-services.md) </span></span>  
 <span data-ttu-id="2e00e-135">[Attributi &#40;Master Data Services&#41;](../../2014/master-data-services/attributes-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="2e00e-135">[Attributes &#40;Master Data Services&#41;](../../2014/master-data-services/attributes-master-data-services.md) </span></span>  
 <span data-ttu-id="2e00e-136">[Modificare il nome di un gruppo di attributi &#40;Master Data Services&#41;](../../2014/master-data-services/change-an-attribute-group-name-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="2e00e-136">[Change an Attribute Group Name &#40;Master Data Services&#41;](../../2014/master-data-services/change-an-attribute-group-name-master-data-services.md) </span></span>  
 <span data-ttu-id="2e00e-137">[Eliminare un gruppo di attributi &#40;Master Data Services&#41;](../../2014/master-data-services/delete-an-attribute-group-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="2e00e-137">[Delete an Attribute Group &#40;Master Data Services&#41;](../../2014/master-data-services/delete-an-attribute-group-master-data-services.md) </span></span>  
 <span data-ttu-id="2e00e-138">[Autorizzazioni foglia &#40;Master Data Services&#41;](../../2014/master-data-services/leaf-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="2e00e-138">[Leaf Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/leaf-permissions-master-data-services.md) </span></span>  
 [<span data-ttu-id="2e00e-139">Autorizzazioni consolidate &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="2e00e-139">Consolidated Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/consolidated-permissions-master-data-services.md)  
  
  
