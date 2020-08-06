---
title: Creare un attributo di testo (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- attributes [Master Data Services], creating text attributes
- creating text attributes [Master Data Services]
ms.assetid: cd8b57de-364d-42a3-9273-c1c6b992bb40
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c0f44e0e6c6e3df49b6a3746648ee46a23a7a3ce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638448"
---
# <a name="create-a-text-attribute-master-data-services"></a><span data-ttu-id="82538-102">Creare un attributo di testo (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="82538-102">Create a Text Attribute (Master Data Services)</span></span>
  <span data-ttu-id="82538-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]creare un attributo di testo quando si desidera che gli utenti immettano una stringa di testo come valore di attributo.</span><span class="sxs-lookup"><span data-stu-id="82538-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], create a text attribute when you want users to enter a text string as an attribute value.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="82538-104">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="82538-104">Prerequisites</span></span>  
 <span data-ttu-id="82538-105">Per eseguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="82538-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="82538-106">È necessario disporre di autorizzazione per accedere all'area funzionale **Amministrazione sistema** .</span><span class="sxs-lookup"><span data-stu-id="82538-106">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="82538-107">È necessario essere un amministratore del modello.</span><span class="sxs-lookup"><span data-stu-id="82538-107">You must be a model administrator.</span></span> <span data-ttu-id="82538-108">Per ulteriori informazioni, vedere [amministratori &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="82538-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="82538-109">È necessario che sia presente un'entità perché ne venga creato l'attributo.</span><span class="sxs-lookup"><span data-stu-id="82538-109">An entity must exist to create the attribute for.</span></span> <span data-ttu-id="82538-110">Per altre informazioni, vedere [Creare un'entità &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="82538-110">For more information, see [Create an Entity &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span></span>  
  
### <a name="to-create-a-text-attribute"></a><span data-ttu-id="82538-111">Per creare un attributo di testo</span><span class="sxs-lookup"><span data-stu-id="82538-111">To create a text attribute</span></span>  
  
1.  <span data-ttu-id="82538-112">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], fare clic su **Amministrazione sistema**.</span><span class="sxs-lookup"><span data-stu-id="82538-112">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="82538-113">Nella pagina **Vista modelli** scegliere **Gestisci** dalla barra dei menu, quindi fare clic su **Entità**.</span><span class="sxs-lookup"><span data-stu-id="82538-113">On the **Model View** page, from the menu bar, point to **Manage** and click **Entities**.</span></span>  
  
3.  <span data-ttu-id="82538-114">Nella pagina **Gestione entità** selezionare un modello dall'elenco **Modello** .</span><span class="sxs-lookup"><span data-stu-id="82538-114">On the **Entity Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="82538-115">Selezionare la riga relativa all'entità per la quale si desidera creare un attributo.</span><span class="sxs-lookup"><span data-stu-id="82538-115">Select the row for the entity that you want to create an attribute for.</span></span>  
  
5.  <span data-ttu-id="82538-116">Fare clic su **Modifica entità selezionata**.</span><span class="sxs-lookup"><span data-stu-id="82538-116">Click **Edit selected entity**.</span></span>  
  
6.  <span data-ttu-id="82538-117">Nella pagina **Modifica entità** :</span><span class="sxs-lookup"><span data-stu-id="82538-117">On the **Edit Entity** page:</span></span>  
  
    -   <span data-ttu-id="82538-118">Se l'attributo è per membri foglia, nel riquadro **Attributi membro foglia** fare clic su **Aggiungi attributo foglia**.</span><span class="sxs-lookup"><span data-stu-id="82538-118">If the attribute is for leaf members, in the **Leaf member attributes** pane, click **Add leaf attribute**.</span></span>  
  
    -   <span data-ttu-id="82538-119">Se l'attributo è per membri consolidati, nel riquadro **Attributi membro consolidati** fare clic su **Aggiungi attributo consolidato**.</span><span class="sxs-lookup"><span data-stu-id="82538-119">If the attribute is for consolidated members, in the **Consolidated member attributes** pane, click **Add consolidated attribute**.</span></span>  
  
    -   <span data-ttu-id="82538-120">Se l'attributo è per raccolte, nel riquadro **Attributi raccolta** fare clic su **Aggiungi attributo raccolta**.</span><span class="sxs-lookup"><span data-stu-id="82538-120">If the attribute is for collections, in the **Collection attributes** pane, click **Add collection attribute**.</span></span>  
  
7.  <span data-ttu-id="82538-121">Nella pagina **Aggiungi attributo** selezionare l'opzione **Formato libero** .</span><span class="sxs-lookup"><span data-stu-id="82538-121">On the **Add Attribute** page, select the **Free-form** option.</span></span>  
  
8.  <span data-ttu-id="82538-122">Nella casella **Nome** digitare un nome per l'attributo.</span><span class="sxs-lookup"><span data-stu-id="82538-122">In the **Name** box, type a name for the attribute.</span></span> <span data-ttu-id="82538-123">Per un elenco di parole che non devono essere usate come nomi di attributo, vedere [parole riservate &#40;Master Data Services&#41;](../../2014/master-data-services/reserved-words-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="82538-123">For a list of words that should not be used as attribute names, see [Reserved Words &#40;Master Data Services&#41;](../../2014/master-data-services/reserved-words-master-data-services.md).</span></span>  
  
9. <span data-ttu-id="82538-124">Nella casella **Larghezza in pixel visualizzazione** digitare la larghezza della colonna attributo da visualizzare nella griglia **Esplora** .</span><span class="sxs-lookup"><span data-stu-id="82538-124">In the **Display pixel width** box, type the width of the attribute column to be displayed in the **Explorer** grid.</span></span>  
  
10. <span data-ttu-id="82538-125">Nell'elenco **Tipo di dati** selezionare **Testo**.</span><span class="sxs-lookup"><span data-stu-id="82538-125">From the **Data type** list, select **Text**.</span></span>  
  
11. <span data-ttu-id="82538-126">Nella casella **Lunghezza** digitare il numero massimo di caratteri consentiti.</span><span class="sxs-lookup"><span data-stu-id="82538-126">In the **Length** box, type the maximum number of characters allowed.</span></span>  
  
12. <span data-ttu-id="82538-127">Facoltativamente, selezionare **Abilita rilevamento modifiche** per tenere traccia delle modifiche a gruppi di attributi.</span><span class="sxs-lookup"><span data-stu-id="82538-127">Optionally, select **Enable change tracking** to track changes to groups of attributes.</span></span> <span data-ttu-id="82538-128">Per altre informazioni, vedere [Aggiungere attributi ad un gruppo rilevamento modifiche &#40;Master Data Services&#41;](../../2014/master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="82538-128">For more information, see [Add Attributes to a Change Tracking Group &#40;Master Data Services&#41;](../../2014/master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md).</span></span>  
  
13. <span data-ttu-id="82538-129">Fare clic su **Salva attributo**.</span><span class="sxs-lookup"><span data-stu-id="82538-129">Click **Save attribute**.</span></span>  
  
14. <span data-ttu-id="82538-130">Nella pagina **Gestione entità** , fare clic su **Salva entità**.</span><span class="sxs-lookup"><span data-stu-id="82538-130">On the **Entity Maintenance** page, click **Save entity**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82538-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="82538-131">See Also</span></span>  
 <span data-ttu-id="82538-132">[Attributi &#40;Master Data Services&#41;](../../2014/master-data-services/attributes-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="82538-132">[Attributes &#40;Master Data Services&#41;](../../2014/master-data-services/attributes-master-data-services.md) </span></span>  
 <span data-ttu-id="82538-133">[Modificare il nome di un attributo &#40;Master Data Services&#41;](change-an-attribute-name-and-data-type-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="82538-133">[Change an Attribute Name &#40;Master Data Services&#41;](change-an-attribute-name-and-data-type-master-data-services.md) </span></span>  
 <span data-ttu-id="82538-134">[Creare un attributo basato su dominio &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-domain-based-attribute-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="82538-134">[Create a Domain-Based Attribute &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-domain-based-attribute-master-data-services.md) </span></span>  
 [<span data-ttu-id="82538-135">Creare un attributo di file &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="82538-135">Create a File Attribute &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-file-attribute-master-data-services.md)  
  
  
