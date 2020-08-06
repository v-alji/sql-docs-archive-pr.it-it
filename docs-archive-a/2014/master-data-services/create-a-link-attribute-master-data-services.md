---
title: Creare un attributo di collegamento (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- attributes [Master Data Services], creating link attributes
- creating link attributes [Master Data Services]
ms.assetid: e6658e9c-5b08-4b8d-b556-17ec2dd041d2
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 4770d7904371c10dc6720e8d3d7f28ca797d9b80
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637967"
---
# <a name="create-a-link-attribute-master-data-services"></a><span data-ttu-id="3a6f7-102">Creare un attributo di collegamento (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="3a6f7-102">Create a Link Attribute (Master Data Services)</span></span>
  <span data-ttu-id="3a6f7-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] creare un attributo per il collegamento quando si deve immettere un collegamento ipertestuale come valore di attributo, ad esempio `http://www.contoso.com`.</span><span class="sxs-lookup"><span data-stu-id="3a6f7-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], create a link attribute when you want users to enter a hyperlink as an attribute value, such as `http://www.contoso.com`.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3a6f7-104">Quando gli utenti immettono un valore per un attributo di collegamento, la stringa deve iniziare con **http://** altrimenti viene visualizzato un errore.</span><span class="sxs-lookup"><span data-stu-id="3a6f7-104">When users enter a value for a link attribute, the string must begin with **http://** or an error will be displayed.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="3a6f7-105">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="3a6f7-105">Prerequisites</span></span>  
 <span data-ttu-id="3a6f7-106">Per eseguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="3a6f7-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="3a6f7-107">È necessario disporre di autorizzazione per accedere all'area funzionale **Amministrazione sistema** .</span><span class="sxs-lookup"><span data-stu-id="3a6f7-107">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="3a6f7-108">È necessario essere un amministratore del modello.</span><span class="sxs-lookup"><span data-stu-id="3a6f7-108">You must be a model administrator.</span></span> <span data-ttu-id="3a6f7-109">Per ulteriori informazioni, vedere [amministratori &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="3a6f7-109">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="3a6f7-110">È necessario che sia presente un'entità perché ne venga creato l'attributo.</span><span class="sxs-lookup"><span data-stu-id="3a6f7-110">An entity must exist to create the attribute for.</span></span> <span data-ttu-id="3a6f7-111">Per altre informazioni, vedere [Creare un'entità &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="3a6f7-111">For more information, see [Create an Entity &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span></span>  
  
### <a name="to-create-a-link-attribute"></a><span data-ttu-id="3a6f7-112">Per creare un attributo di collegamento</span><span class="sxs-lookup"><span data-stu-id="3a6f7-112">To create a link attribute</span></span>  
  
1.  <span data-ttu-id="3a6f7-113">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], fare clic su **Amministrazione sistema**.</span><span class="sxs-lookup"><span data-stu-id="3a6f7-113">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="3a6f7-114">Nella pagina **Vista modelli** scegliere **Gestisci** dalla barra dei menu, quindi fare clic su **Entità**.</span><span class="sxs-lookup"><span data-stu-id="3a6f7-114">On the **Model View** page, from the menu bar, point to **Manage** and click **Entities**.</span></span>  
  
3.  <span data-ttu-id="3a6f7-115">Nella pagina **Gestione entità** selezionare un modello dall'elenco **Modello** .</span><span class="sxs-lookup"><span data-stu-id="3a6f7-115">On the **Entity Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="3a6f7-116">Selezionare la riga relativa all'entità per la quale si desidera creare un attributo.</span><span class="sxs-lookup"><span data-stu-id="3a6f7-116">Select the row for the entity that you want to create an attribute for.</span></span>  
  
5.  <span data-ttu-id="3a6f7-117">Fare clic su **Modifica entità selezionata**.</span><span class="sxs-lookup"><span data-stu-id="3a6f7-117">Click **Edit selected entity**.</span></span>  
  
6.  <span data-ttu-id="3a6f7-118">Nella pagina **Modifica entità** :</span><span class="sxs-lookup"><span data-stu-id="3a6f7-118">On the **Edit Entity** page:</span></span>  
  
    -   <span data-ttu-id="3a6f7-119">Se l'attributo è per membri foglia, nel riquadro **Attributi membro foglia** fare clic su **Aggiungi attributo foglia**.</span><span class="sxs-lookup"><span data-stu-id="3a6f7-119">If the attribute is for leaf members, in the **Leaf member attributes** pane, click **Add leaf attribute**.</span></span>  
  
    -   <span data-ttu-id="3a6f7-120">Se l'attributo è per membri consolidati, nel riquadro **Attributi membro consolidati** fare clic su **Aggiungi attributo consolidato**.</span><span class="sxs-lookup"><span data-stu-id="3a6f7-120">If the attribute is for consolidated members, in the **Consolidated member attributes** pane, click **Add consolidated attribute**.</span></span>  
  
    -   <span data-ttu-id="3a6f7-121">Se l'attributo è per raccolte, nel riquadro **Attributi raccolta** fare clic su **Aggiungi attributo raccolta**.</span><span class="sxs-lookup"><span data-stu-id="3a6f7-121">If the attribute is for collections, in the **Collection attributes** pane, click **Add collection attribute**.</span></span>  
  
7.  <span data-ttu-id="3a6f7-122">Nella pagina **Aggiungi attributo** selezionare l'opzione **Formato libero** .</span><span class="sxs-lookup"><span data-stu-id="3a6f7-122">On the **Add Attribute** page, select the **Free-form** option.</span></span>  
  
8.  <span data-ttu-id="3a6f7-123">Nella casella **Nome** digitare un nome per l'attributo.</span><span class="sxs-lookup"><span data-stu-id="3a6f7-123">In the **Name** box, type a name for the attribute.</span></span> <span data-ttu-id="3a6f7-124">Per un elenco di parole che non devono essere usate come nomi di attributo, vedere [parole riservate &#40;Master Data Services&#41;](../../2014/master-data-services/reserved-words-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="3a6f7-124">For a list of words that should not be used as attribute names, see [Reserved Words &#40;Master Data Services&#41;](../../2014/master-data-services/reserved-words-master-data-services.md).</span></span>  
  
9. <span data-ttu-id="3a6f7-125">Nella casella **Larghezza in pixel visualizzazione** digitare la larghezza della colonna attributo da visualizzare nella griglia **Esplora** .</span><span class="sxs-lookup"><span data-stu-id="3a6f7-125">In the **Display pixel width** box, type the width of the attribute column to be displayed in the **Explorer** grid.</span></span>  
  
10. <span data-ttu-id="3a6f7-126">Nell'elenco **Tipo di dati** selezionare **Collegamento**.</span><span class="sxs-lookup"><span data-stu-id="3a6f7-126">From the **Data type** list, select **Link**.</span></span>  
  
11. <span data-ttu-id="3a6f7-127">Nella casella **Lunghezza** digitare il numero massimo di caratteri consentiti.</span><span class="sxs-lookup"><span data-stu-id="3a6f7-127">In the **Length** box, type the maximum number of characters allowed.</span></span>  
  
12. <span data-ttu-id="3a6f7-128">Facoltativamente, selezionare **Abilita rilevamento modifiche** per tenere traccia delle modifiche a gruppi di attributi.</span><span class="sxs-lookup"><span data-stu-id="3a6f7-128">Optionally, select **Enable change tracking** to track changes to groups of attributes.</span></span> <span data-ttu-id="3a6f7-129">Per altre informazioni, vedere [Aggiungere attributi ad un gruppo rilevamento modifiche &#40;Master Data Services&#41;](../../2014/master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="3a6f7-129">For more information, see [Add Attributes to a Change Tracking Group &#40;Master Data Services&#41;](../../2014/master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md).</span></span>  
  
13. <span data-ttu-id="3a6f7-130">Fare clic su **Salva attributo**.</span><span class="sxs-lookup"><span data-stu-id="3a6f7-130">Click **Save attribute**.</span></span>  
  
14. <span data-ttu-id="3a6f7-131">Nella pagina **Gestione entità** , fare clic su **Salva entità**.</span><span class="sxs-lookup"><span data-stu-id="3a6f7-131">On the **Entity Maintenance** page, click **Save entity**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a6f7-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3a6f7-132">See Also</span></span>  
 <span data-ttu-id="3a6f7-133">[Attributi &#40;Master Data Services&#41;](../../2014/master-data-services/attributes-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="3a6f7-133">[Attributes &#40;Master Data Services&#41;](../../2014/master-data-services/attributes-master-data-services.md) </span></span>  
 <span data-ttu-id="3a6f7-134">[Modificare il nome di un attributo &#40;Master Data Services&#41;](change-an-attribute-name-and-data-type-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="3a6f7-134">[Change an Attribute Name &#40;Master Data Services&#41;](change-an-attribute-name-and-data-type-master-data-services.md) </span></span>  
 <span data-ttu-id="3a6f7-135">[Creare un attributo basato su dominio &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-domain-based-attribute-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="3a6f7-135">[Create a Domain-Based Attribute &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-domain-based-attribute-master-data-services.md) </span></span>  
 [<span data-ttu-id="3a6f7-136">Creare un attributo di file &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="3a6f7-136">Create a File Attribute &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-file-attribute-master-data-services.md)  
  
  
