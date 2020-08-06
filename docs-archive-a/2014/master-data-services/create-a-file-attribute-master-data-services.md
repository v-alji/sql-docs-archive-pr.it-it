---
title: Creare un attributo di file (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- creating file attributes [Master Data Services]
- attributes [Master Data Services], creating file attributes
ms.assetid: d224886b-2ef1-4658-8b01-2213cc4b8df6
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: f4f6e2f10a830d089d1d217f7cf54d0b8557add9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625438"
---
# <a name="create-a-file-attribute-master-data-services"></a><span data-ttu-id="bab9e-102">Creare un attributo di file (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="bab9e-102">Create a File Attribute (Master Data Services)</span></span>
  <span data-ttu-id="bab9e-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]creare un attributo di file per popolare i valori di attributo con i file.</span><span class="sxs-lookup"><span data-stu-id="bab9e-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], create a file attribute to populate attribute values with files.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="bab9e-104">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="bab9e-104">Prerequisites</span></span>  
 <span data-ttu-id="bab9e-105">Per eseguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="bab9e-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="bab9e-106">È necessario disporre di autorizzazione per accedere all'area funzionale **Amministrazione sistema** .</span><span class="sxs-lookup"><span data-stu-id="bab9e-106">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="bab9e-107">È necessario essere un amministratore del modello.</span><span class="sxs-lookup"><span data-stu-id="bab9e-107">You must be a model administrator.</span></span> <span data-ttu-id="bab9e-108">Per ulteriori informazioni, vedere [amministratori &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="bab9e-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="bab9e-109">È necessario che sia presente un'entità perché ne venga creato l'attributo.</span><span class="sxs-lookup"><span data-stu-id="bab9e-109">An entity must exist to create the attribute for.</span></span> <span data-ttu-id="bab9e-110">Per altre informazioni, vedere [Creare un'entità &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="bab9e-110">For more information, see [Create an Entity &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span></span>  
  
### <a name="to-create-a-file-attribute"></a><span data-ttu-id="bab9e-111">Per creare un attributo di file</span><span class="sxs-lookup"><span data-stu-id="bab9e-111">To create a file attribute</span></span>  
  
1.  <span data-ttu-id="bab9e-112">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], fare clic su **Amministrazione sistema**.</span><span class="sxs-lookup"><span data-stu-id="bab9e-112">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="bab9e-113">Nella pagina **Vista modelli** scegliere **Gestisci** dalla barra dei menu, quindi fare clic su **Entità**.</span><span class="sxs-lookup"><span data-stu-id="bab9e-113">On the **Model View** page, from the menu bar, point to **Manage** and click **Entities**.</span></span>  
  
3.  <span data-ttu-id="bab9e-114">Nella pagina **Gestione entità** selezionare un modello dall'elenco **Modello** .</span><span class="sxs-lookup"><span data-stu-id="bab9e-114">On the **Entity Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="bab9e-115">Selezionare la riga relativa all'entità per la quale si desidera creare un attributo.</span><span class="sxs-lookup"><span data-stu-id="bab9e-115">Select the row for the entity that you want to create an attribute for.</span></span>  
  
5.  <span data-ttu-id="bab9e-116">Fare clic su **Modifica entità selezionata**.</span><span class="sxs-lookup"><span data-stu-id="bab9e-116">Click **Edit selected entity**.</span></span>  
  
6.  <span data-ttu-id="bab9e-117">Nella pagina **Modifica entità** :</span><span class="sxs-lookup"><span data-stu-id="bab9e-117">On the **Edit Entity** page:</span></span>  
  
    -   <span data-ttu-id="bab9e-118">Se l'attributo è per membri foglia, nel riquadro **Attributi membro foglia** fare clic su **Aggiungi attributo foglia**.</span><span class="sxs-lookup"><span data-stu-id="bab9e-118">If the attribute is for leaf members, in the **Leaf member attributes** pane, click **Add leaf attribute**.</span></span>  
  
    -   <span data-ttu-id="bab9e-119">Se l'attributo è per membri consolidati, nel riquadro **Attributi membro consolidati** fare clic su **Aggiungi attributo consolidato**.</span><span class="sxs-lookup"><span data-stu-id="bab9e-119">If the attribute is for consolidated members, in the **Consolidated member attributes** pane, click **Add consolidated attribute**.</span></span>  
  
    -   <span data-ttu-id="bab9e-120">Se l'attributo è per raccolte, nel riquadro **Attributi raccolta** fare clic su **Aggiungi attributo raccolta**.</span><span class="sxs-lookup"><span data-stu-id="bab9e-120">If the attribute is for collections, in the **Collection attributes** pane, click **Add collection attribute**.</span></span>  
  
7.  <span data-ttu-id="bab9e-121">Nella pagina **Aggiungi attributo** selezionare l'opzione **file** .</span><span class="sxs-lookup"><span data-stu-id="bab9e-121">On the **Add Attribute** page, select the **File** option.</span></span>  
  
8.  <span data-ttu-id="bab9e-122">Nella casella **Nome** digitare un nome per l'attributo.</span><span class="sxs-lookup"><span data-stu-id="bab9e-122">In the **Name** box, type a name for the attribute.</span></span> <span data-ttu-id="bab9e-123">Per un elenco di parole che non devono essere usate come nomi di attributo, vedere [parole riservate &#40;Master Data Services&#41;](../../2014/master-data-services/reserved-words-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="bab9e-123">For a list of words that should not be used as attribute names, see [Reserved Words &#40;Master Data Services&#41;](../../2014/master-data-services/reserved-words-master-data-services.md).</span></span>  
  
9. <span data-ttu-id="bab9e-124">Nella casella **Larghezza in pixel visualizzazione** digitare la larghezza della colonna attributo da visualizzare nella griglia **Esplora** .</span><span class="sxs-lookup"><span data-stu-id="bab9e-124">In the **Display pixel width** box, type the width of the attribute column to be displayed in the **Explorer** grid.</span></span>  
  
10. <span data-ttu-id="bab9e-125">Dall'elenco **estensione file** selezionare uno o più tipi di file che un utente può caricare o lasciare il valore predefinito (\*. \* ) per consentire tutti i tipi di file.</span><span class="sxs-lookup"><span data-stu-id="bab9e-125">From the **File extension** list, select one or more file types that a user can upload, or leave the default (\*.\*) to allow all file types.</span></span>  
  
11. <span data-ttu-id="bab9e-126">Facoltativamente, selezionare **Abilita rilevamento modifiche** per tenere traccia delle modifiche a gruppi di attributi.</span><span class="sxs-lookup"><span data-stu-id="bab9e-126">Optionally, select **Enable change tracking** to track changes to groups of attributes.</span></span> <span data-ttu-id="bab9e-127">Per altre informazioni, vedere [Aggiungere attributi ad un gruppo rilevamento modifiche &#40;Master Data Services&#41;](../../2014/master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="bab9e-127">For more information, see [Add Attributes to a Change Tracking Group &#40;Master Data Services&#41;](../../2014/master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md).</span></span>  
  
12. <span data-ttu-id="bab9e-128">Fare clic su **Salva attributo**.</span><span class="sxs-lookup"><span data-stu-id="bab9e-128">Click **Save attribute**.</span></span>  
  
13. <span data-ttu-id="bab9e-129">Nella pagina **Gestione entità** , fare clic su **Salva entità**.</span><span class="sxs-lookup"><span data-stu-id="bab9e-129">On the **Entity Maintenance** page, click **Save entity**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bab9e-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bab9e-130">See Also</span></span>  
 <span data-ttu-id="bab9e-131">[Attributi &#40;Master Data Services&#41;](../../2014/master-data-services/attributes-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="bab9e-131">[Attributes &#40;Master Data Services&#41;](../../2014/master-data-services/attributes-master-data-services.md) </span></span>  
 <span data-ttu-id="bab9e-132">[Modificare il nome di un attributo &#40;Master Data Services&#41;](change-an-attribute-name-and-data-type-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="bab9e-132">[Change an Attribute Name &#40;Master Data Services&#41;](change-an-attribute-name-and-data-type-master-data-services.md) </span></span>  
 <span data-ttu-id="bab9e-133">[Creare un attributo basato su dominio &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-domain-based-attribute-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="bab9e-133">[Create a Domain-Based Attribute &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-domain-based-attribute-master-data-services.md) </span></span>  
 [<span data-ttu-id="bab9e-134">Creare un attributo di testo &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="bab9e-134">Create a Text Attribute &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-text-attribute-master-data-services.md)  
  
  
