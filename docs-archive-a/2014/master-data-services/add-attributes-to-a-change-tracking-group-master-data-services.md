---
title: Aggiungere attributi a un gruppo di rilevamento modifiche (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- change tracking groups [Master Data Services]
- attributes [Master Data Services], change tracking groups
- change tracking groups [Master Data Services], adding attributes
ms.assetid: e153eb5f-70ca-4c6f-89d8-1f937ed3917d
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c8a13dad3ca886668c96c1886f8cd238d9adad9f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637407"
---
# <a name="add-attributes-to-a-change-tracking-group-master-data-services"></a><span data-ttu-id="27a4c-102">Aggiungere attributi ad un gruppo rilevamento modifiche (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="27a4c-102">Add Attributes to a Change Tracking Group (Master Data Services)</span></span>
  <span data-ttu-id="27a4c-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]aggiungere attributi a un gruppo rilevamento modifiche quando si vuole tenere traccia delle modifiche apportate ai valori dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="27a4c-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], add attributes to a change tracking group when you want to track changes to the attribute's values.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="27a4c-104">In seguito all'aggiunta di un attributo a un gruppo rilevamento modifiche, quando si modificano i valori relativi a tale attributo, l'attributo viene contrassegnato nel database [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="27a4c-104">After you add an attribute to a change tracking group, when values for the attribute change, the attribute is flagged as changed in the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span> <span data-ttu-id="27a4c-105">Creare una regola business per eseguire le azioni appropriate in base alla modifica.</span><span class="sxs-lookup"><span data-stu-id="27a4c-105">Create a business rule to take action based on the change.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="27a4c-106">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="27a4c-106">Prerequisites</span></span>  
 <span data-ttu-id="27a4c-107">Per eseguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="27a4c-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="27a4c-108">È necessario disporre di autorizzazione per accedere all'area funzionale **Amministrazione sistema** .</span><span class="sxs-lookup"><span data-stu-id="27a4c-108">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="27a4c-109">È necessario essere un amministratore del modello.</span><span class="sxs-lookup"><span data-stu-id="27a4c-109">You must be a model administrator.</span></span> <span data-ttu-id="27a4c-110">Per ulteriori informazioni, vedere [amministratori &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="27a4c-110">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="27a4c-111">È necessario che esistano degli attributi da aggiungere al gruppo rilevamento modifiche.</span><span class="sxs-lookup"><span data-stu-id="27a4c-111">Attributes must exist to add to the change tracking group.</span></span> <span data-ttu-id="27a4c-112">Per altre informazioni, vedere [Creare un attributo di testo &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-text-attribute-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="27a4c-112">For more information, see [Create a Text Attribute &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-text-attribute-master-data-services.md).</span></span>  
  
### <a name="to-add-attributes-to-a-change-tracking-group"></a><span data-ttu-id="27a4c-113">Per aggiungere attributi ad un gruppo rilevamento modifiche</span><span class="sxs-lookup"><span data-stu-id="27a4c-113">To add attributes to a change tracking group</span></span>  
  
1.  <span data-ttu-id="27a4c-114">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], fare clic su **Amministrazione sistema**.</span><span class="sxs-lookup"><span data-stu-id="27a4c-114">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="27a4c-115">Nella pagina **Esplora modelli** scegliere **Gestisci** dalla barra dei menu, quindi fare clic su **entità**.</span><span class="sxs-lookup"><span data-stu-id="27a4c-115">On the **Model Explorer** page, from the menu bar, point to **Manage** and click **Entities**.</span></span>  
  
3.  <span data-ttu-id="27a4c-116">Nella pagina **Gestione entità** selezionare un modello dall'elenco **Modello** .</span><span class="sxs-lookup"><span data-stu-id="27a4c-116">On the **Entity Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="27a4c-117">Selezionare la riga relativa all'entità per la quale si desidera tenere traccia dei valori di attributo.</span><span class="sxs-lookup"><span data-stu-id="27a4c-117">Select the row for the entity that you want to track attribute values for.</span></span>  
  
5.  <span data-ttu-id="27a4c-118">Fare clic su **Modifica entità selezionata**.</span><span class="sxs-lookup"><span data-stu-id="27a4c-118">Click **Edit selected entity**.</span></span>  
  
6.  <span data-ttu-id="27a4c-119">Nella pagina **Modifica entità** :</span><span class="sxs-lookup"><span data-stu-id="27a4c-119">On the **Edit Entity** page:</span></span>  
  
    -   <span data-ttu-id="27a4c-120">Se l'attributo è per i membri foglia, nel riquadro **attributi foglia** selezionare l'attributo e fare clic su **modifica attributo foglia**.</span><span class="sxs-lookup"><span data-stu-id="27a4c-120">If the attribute is for leaf members, in the **Leaf attributes** pane, select the attribute and click **Edit leaf attribute**.</span></span>  
  
    -   <span data-ttu-id="27a4c-121">Se l'attributo è per i membri consolidati, nel riquadro **attributi** consolidati selezionare l'attributo e fare clic su **modifica attributo consolidato**.</span><span class="sxs-lookup"><span data-stu-id="27a4c-121">If the attribute is for consolidated members, in the **Consolidated attributes** pane, select the attribute and click **Edit consolidated attribute**.</span></span>  
  
    -   <span data-ttu-id="27a4c-122">Se l'attributo è per le raccolte, nel riquadro **attributi raccolta** selezionare l'attributo e fare clic su **modifica attributo raccolta**.</span><span class="sxs-lookup"><span data-stu-id="27a4c-122">If the attribute is for collections, in the **Collection attributes** pane, select the attribute and click **Edit collection attribute**.</span></span>  
  
7.  <span data-ttu-id="27a4c-123">Selezionare la casella di controllo **Abilita rilevamento modifiche** .</span><span class="sxs-lookup"><span data-stu-id="27a4c-123">Select the **Enable change tracking** check box.</span></span>  
  
8.  <span data-ttu-id="27a4c-124">Nella casella **Gruppo rilevamento modifiche** digitare un numero per il gruppo.</span><span class="sxs-lookup"><span data-stu-id="27a4c-124">In the **Change tracking group** box, type a number for the group.</span></span>  
  
9. <span data-ttu-id="27a4c-125">Fare clic su **Salva attributo**.</span><span class="sxs-lookup"><span data-stu-id="27a4c-125">Click **Save attribute**.</span></span>  
  
10. <span data-ttu-id="27a4c-126">Nella pagina **Gestione entità** , fare clic su **Salva entità**.</span><span class="sxs-lookup"><span data-stu-id="27a4c-126">On the **Entity Maintenance** page, click **Save entity**.</span></span>  
  
11. <span data-ttu-id="27a4c-127">Ripetere questa procedura per tutti gli attributi che si desidera includere nel gruppo.</span><span class="sxs-lookup"><span data-stu-id="27a4c-127">Repeat this procedure for all attributes you want to include in the group.</span></span> <span data-ttu-id="27a4c-128">Utilizzare lo stesso numero del gruppo rilevamento modifiche per ciascun attributo del gruppo.</span><span class="sxs-lookup"><span data-stu-id="27a4c-128">Use the same change tracking group number for each attribute in the group.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="27a4c-129">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="27a4c-129">Next Steps</span></span>  
  
-   [<span data-ttu-id="27a4c-130">Inizializzare azioni basate su modifiche dei valori di attributo &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="27a4c-130">Initiate Actions Based on Attribute Value Changes &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/initiate-actions-based-on-attribute-value-changes-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="27a4c-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="27a4c-131">See Also</span></span>  
 <span data-ttu-id="27a4c-132">[Creare un attributo di testo &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-text-attribute-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="27a4c-132">[Create a Text Attribute &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-text-attribute-master-data-services.md) </span></span>  
 [<span data-ttu-id="27a4c-133">Creare un attributo basato su dominio &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="27a4c-133">Create a Domain-Based Attribute &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-domain-based-attribute-master-data-services.md)  
  
  
