---
title: Creare un attributo numerico (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- attributes [Master Data Services], creating number attributes
- creating number attributes [Master Data Services]
ms.assetid: c0dbb6d8-ba78-485a-a40d-6d5cb7e75d0a
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: bb9302c0b585c21410a6a764dc2e6dac845c6299
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623383"
---
# <a name="create-a-numeric-attribute-master-data-services"></a><span data-ttu-id="d622b-102">Creare un attributo numerico (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="d622b-102">Create a Numeric Attribute (Master Data Services)</span></span>
  <span data-ttu-id="d622b-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]creare un attributo numerico quando si vuole che gli utenti immettano un numero come valore di attributo.</span><span class="sxs-lookup"><span data-stu-id="d622b-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], create a numeric attribute when you want users to enter a number as an attribute value.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d622b-104">Gli attributi numerici presentano limitazioni.</span><span class="sxs-lookup"><span data-stu-id="d622b-104">Numeric attributes have limitations.</span></span> <span data-ttu-id="d622b-105">Per altre informazioni, vedere [Attributi &#40;Master Data Services&#41;](attributes-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="d622b-105">For more information, see [Attributes &#40;Master Data Services&#41;](attributes-master-data-services.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d622b-106">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="d622b-106">Prerequisites</span></span>  
 <span data-ttu-id="d622b-107">Per eseguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="d622b-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="d622b-108">È necessario disporre di autorizzazione per accedere all'area funzionale **Amministrazione sistema** .</span><span class="sxs-lookup"><span data-stu-id="d622b-108">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="d622b-109">È necessario essere un amministratore del modello.</span><span class="sxs-lookup"><span data-stu-id="d622b-109">You must be a model administrator.</span></span> <span data-ttu-id="d622b-110">Per ulteriori informazioni, vedere [amministratori &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="d622b-110">For more information, see [Administrators &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="d622b-111">È necessario che sia presente un'entità perché ne venga creato l'attributo.</span><span class="sxs-lookup"><span data-stu-id="d622b-111">An entity must exist to create the attribute for.</span></span> <span data-ttu-id="d622b-112">Per altre informazioni, vedere [Creare un'entità &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="d622b-112">For more information, see [Create an Entity &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span></span>  
  
### <a name="to-create-a-numeric-attribute"></a><span data-ttu-id="d622b-113">Per creare un attributo numerico</span><span class="sxs-lookup"><span data-stu-id="d622b-113">To create a numeric attribute</span></span>  
  
1.  <span data-ttu-id="d622b-114">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], fare clic su **Amministrazione sistema**.</span><span class="sxs-lookup"><span data-stu-id="d622b-114">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="d622b-115">Nella pagina **Vista modelli** scegliere **Gestisci** dalla barra dei menu, quindi fare clic su **Entità**.</span><span class="sxs-lookup"><span data-stu-id="d622b-115">On the **Model View** page, from the menu bar, point to **Manage** and click **Entities**.</span></span>  
  
3.  <span data-ttu-id="d622b-116">Nella pagina **Gestione entità** selezionare un modello dall'elenco **Modello** .</span><span class="sxs-lookup"><span data-stu-id="d622b-116">On the **Entity Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="d622b-117">Selezionare la riga relativa all'entità per la quale si desidera creare un attributo.</span><span class="sxs-lookup"><span data-stu-id="d622b-117">Select the row for the entity that you want to create an attribute for.</span></span>  
  
5.  <span data-ttu-id="d622b-118">Fare clic su **Modifica entità selezionata**.</span><span class="sxs-lookup"><span data-stu-id="d622b-118">Click **Edit selected entity**.</span></span>  
  
6.  <span data-ttu-id="d622b-119">Nella pagina **Modifica entità** :</span><span class="sxs-lookup"><span data-stu-id="d622b-119">On the **Edit Entity** page:</span></span>  
  
    -   <span data-ttu-id="d622b-120">Se l'attributo è per membri foglia, nel riquadro **Attributi membro foglia** fare clic su **Aggiungi attributo foglia**.</span><span class="sxs-lookup"><span data-stu-id="d622b-120">If the attribute is for leaf members, in the **Leaf member attributes** pane, click **Add leaf attribute**.</span></span>  
  
    -   <span data-ttu-id="d622b-121">Se l'attributo è per membri consolidati, nel riquadro **Attributi membro consolidati** fare clic su **Aggiungi attributo consolidato**.</span><span class="sxs-lookup"><span data-stu-id="d622b-121">If the attribute is for consolidated members, in the **Consolidated member attributes** pane, click **Add consolidated attribute**.</span></span>  
  
    -   <span data-ttu-id="d622b-122">Se l'attributo è per raccolte, nel riquadro **Attributi raccolta** fare clic su **Aggiungi attributo raccolta**.</span><span class="sxs-lookup"><span data-stu-id="d622b-122">If the attribute is for collections, in the **Collection attributes** pane, click **Add collection attribute**.</span></span>  
  
7.  <span data-ttu-id="d622b-123">Nella pagina **Aggiungi attributo** selezionare l'opzione **Formato libero** .</span><span class="sxs-lookup"><span data-stu-id="d622b-123">On the **Add Attribute** page, select the **Free-form** option.</span></span>  
  
8.  <span data-ttu-id="d622b-124">Nella casella **Nome** digitare un nome per l'attributo.</span><span class="sxs-lookup"><span data-stu-id="d622b-124">In the **Name** box, type a name for the attribute.</span></span> <span data-ttu-id="d622b-125">Per un elenco di parole che non devono essere usate come nomi di attributo, vedere [parole riservate &#40;Master Data Services&#41;](../../2014/master-data-services/reserved-words-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="d622b-125">For a list of words that should not be used as attribute names, see [Reserved Words &#40;Master Data Services&#41;](../../2014/master-data-services/reserved-words-master-data-services.md).</span></span>  
  
9. <span data-ttu-id="d622b-126">Nella casella **Larghezza in pixel visualizzazione** digitare la larghezza della colonna attributo da visualizzare nella griglia **Esplora** .</span><span class="sxs-lookup"><span data-stu-id="d622b-126">In the **Display pixel width** box, type the width of the attribute column to be displayed in the **Explorer** grid.</span></span>  
  
10. <span data-ttu-id="d622b-127">Nell'elenco **Tipo di dati** selezionare **Numero**.</span><span class="sxs-lookup"><span data-stu-id="d622b-127">From the **Data type** list, select **Number**.</span></span>  
  
11. <span data-ttu-id="d622b-128">Nella casella **Decimali** digitare il numero di cifre che è possibile immettere dopo un separatore decimale.</span><span class="sxs-lookup"><span data-stu-id="d622b-128">In the **Decimals** box, type the number of numbers that can be entered after a decimal.</span></span>  
  
12. <span data-ttu-id="d622b-129">Nell'elenco **maschera di input** selezionare un formato per i numeri negativi.</span><span class="sxs-lookup"><span data-stu-id="d622b-129">From the **Input mask** list, select a format for negative numbers.</span></span>  
  
13. <span data-ttu-id="d622b-130">Facoltativamente, selezionare **Abilita rilevamento modifiche** per tenere traccia delle modifiche a gruppi di attributi.</span><span class="sxs-lookup"><span data-stu-id="d622b-130">Optionally, select **Enable change tracking** to track changes to groups of attributes.</span></span> <span data-ttu-id="d622b-131">Per altre informazioni, vedere [Aggiungere attributi ad un gruppo rilevamento modifiche &#40;Master Data Services&#41;](../../2014/master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md) .</span><span class="sxs-lookup"><span data-stu-id="d622b-131">See [Add Attributes to a Change Tracking Group &#40;Master Data Services&#41;](../../2014/master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md) for more information.</span></span>  
  
14. <span data-ttu-id="d622b-132">Fare clic su **Salva attributo**.</span><span class="sxs-lookup"><span data-stu-id="d622b-132">Click **Save attribute**.</span></span>  
  
15. <span data-ttu-id="d622b-133">Nella pagina **Gestione entità** , fare clic su **Salva entità**.</span><span class="sxs-lookup"><span data-stu-id="d622b-133">On the **Entity Maintenance** page, click **Save entity**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d622b-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d622b-134">See Also</span></span>  
 <span data-ttu-id="d622b-135">[Attributi &#40;Master Data Services&#41;](attributes-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="d622b-135">[Attributes &#40;Master Data Services&#41;](attributes-master-data-services.md) </span></span>  
 <span data-ttu-id="d622b-136">[Modificare il nome di un attributo &#40;Master Data Services&#41;](change-an-attribute-name-and-data-type-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="d622b-136">[Change an Attribute Name &#40;Master Data Services&#41;](change-an-attribute-name-and-data-type-master-data-services.md) </span></span>  
 <span data-ttu-id="d622b-137">[Creare un attributo basato su dominio &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-domain-based-attribute-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="d622b-137">[Create a Domain-Based Attribute &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-domain-based-attribute-master-data-services.md) </span></span>  
 [<span data-ttu-id="d622b-138">Creare un attributo di file &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="d622b-138">Create a File Attribute &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-file-attribute-master-data-services.md)  
  
  
