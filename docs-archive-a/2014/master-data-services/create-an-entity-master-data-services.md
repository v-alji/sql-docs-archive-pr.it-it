---
title: Creare un'entità (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- entities [Master Data Services], creating
- creating entities [Master Data Services]
ms.assetid: d9a6a51e-7b53-4785-a118-3baeb7ca2d48
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 7cefdedd07ee248f12b3b17337878934a2b1aa84
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637399"
---
# <a name="create-an-entity-master-data-services"></a><span data-ttu-id="d94dd-102">Creare un'entità (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="d94dd-102">Create an Entity (Master Data Services)</span></span>
  <span data-ttu-id="d94dd-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]creare un'entità in cui siano contenuti i membri e i relativi attributi.</span><span class="sxs-lookup"><span data-stu-id="d94dd-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], create an entity to contain members and their attributes.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d94dd-104">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="d94dd-104">Prerequisites</span></span>  
 <span data-ttu-id="d94dd-105">Per eseguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="d94dd-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="d94dd-106">È necessario disporre di autorizzazione per accedere all'area funzionale **Amministrazione sistema** .</span><span class="sxs-lookup"><span data-stu-id="d94dd-106">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="d94dd-107">È necessario essere un amministratore del modello.</span><span class="sxs-lookup"><span data-stu-id="d94dd-107">You must be a model administrator.</span></span> <span data-ttu-id="d94dd-108">Per ulteriori informazioni, vedere [amministratori &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="d94dd-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="d94dd-109">È necessario che sia presente un modello.</span><span class="sxs-lookup"><span data-stu-id="d94dd-109">A model must exist.</span></span> <span data-ttu-id="d94dd-110">Per altre informazioni, vedere [Creare un modello &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-model-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="d94dd-110">For more information, see [Create a Model &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-model-master-data-services.md).</span></span>  
  
### <a name="to-create-an-entity"></a><span data-ttu-id="d94dd-111">Per creare un'entità</span><span class="sxs-lookup"><span data-stu-id="d94dd-111">To create an entity</span></span>  
  
1.  <span data-ttu-id="d94dd-112">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], fare clic su **Amministrazione sistema**.</span><span class="sxs-lookup"><span data-stu-id="d94dd-112">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="d94dd-113">Nella pagina **Vista modelli** scegliere **Gestisci** dalla barra dei menu, quindi fare clic su **Entità**.</span><span class="sxs-lookup"><span data-stu-id="d94dd-113">On the **Model View** page, from the menu bar, point to **Manage** and click **Entities**.</span></span>  
  
3.  <span data-ttu-id="d94dd-114">Nella pagina **Gestione entità** selezionare un modello dall'elenco **Modello** .</span><span class="sxs-lookup"><span data-stu-id="d94dd-114">On the **Entity Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="d94dd-115">Fare clic su **Aggiungi entità**.</span><span class="sxs-lookup"><span data-stu-id="d94dd-115">Click **Add entity**.</span></span>  
  
5.  <span data-ttu-id="d94dd-116">Nella casella **nome entità** Digitare il nome dell'entità.</span><span class="sxs-lookup"><span data-stu-id="d94dd-116">In the **Entity name** box, type the name of the entity.</span></span>  
  
6.  <span data-ttu-id="d94dd-117">Nella casella **nome per le tabelle di staging** Digitare un nome per la tabella di staging.</span><span class="sxs-lookup"><span data-stu-id="d94dd-117">In the **Name for staging tables** box, type a name for the staging table.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="d94dd-118">Usare il nome del modello come parte del nome della tabella di staging, ad esempio *Nomemodello_Nomeentità*.</span><span class="sxs-lookup"><span data-stu-id="d94dd-118">Use the model name as part of the staging table name, for example *Modelname_Entityname*.</span></span> <span data-ttu-id="d94dd-119">In questo modo risulta più agevole trovare le tabelle nel database.</span><span class="sxs-lookup"><span data-stu-id="d94dd-119">This makes the tables easier to find in the database.</span></span> <span data-ttu-id="d94dd-120">Per ulteriori informazioni sulle tabelle di staging, vedere [Data Import &#40;Master Data Services&#41;](overview-importing-data-from-tables-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="d94dd-120">For more information about the staging tables, see [Data Import &#40;Master Data Services&#41;](overview-importing-data-from-tables-master-data-services.md).</span></span>  
  
7.  <span data-ttu-id="d94dd-121">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="d94dd-121">Optional.</span></span> <span data-ttu-id="d94dd-122">Selezionare la casella di controllo **Crea valori Code automaticamente** .</span><span class="sxs-lookup"><span data-stu-id="d94dd-122">Select the **Create Code values automatically** check box.</span></span> <span data-ttu-id="d94dd-123">Per ulteriori informazioni, vedere [creazione automatica di codice &#40;Master Data Services&#41;](../../2014/master-data-services/automatic-code-creation-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="d94dd-123">For more information, see [Automatic Code Creation &#40;Master Data Services&#41;](../../2014/master-data-services/automatic-code-creation-master-data-services.md).</span></span>  
  
8.  <span data-ttu-id="d94dd-124">Dall'elenco **Abilita gerarchie esplicite e raccolte** , selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d94dd-124">From the **Enable explicit hierarchies and collections** list, select one of the following options:</span></span>  
  
    -   <span data-ttu-id="d94dd-125">**No**.</span><span class="sxs-lookup"><span data-stu-id="d94dd-125">**No**.</span></span> <span data-ttu-id="d94dd-126">Selezionare questa opzione se non è necessario abilitare l'entità per gerarchie esplicite e raccolte.</span><span class="sxs-lookup"><span data-stu-id="d94dd-126">Select this option if you do not need to enable the entity for explicit hierarchies and collections.</span></span> <span data-ttu-id="d94dd-127">È possibile modificare tale opzione in seguito, se necessario.</span><span class="sxs-lookup"><span data-stu-id="d94dd-127">You can change this later if needed.</span></span>  
  
    -   <span data-ttu-id="d94dd-128">**Sì**.</span><span class="sxs-lookup"><span data-stu-id="d94dd-128">**Yes**.</span></span> <span data-ttu-id="d94dd-129">Selezionare questa opzione quando si desidera abilitare l'entità per gerarchie esplicite e raccolte.</span><span class="sxs-lookup"><span data-stu-id="d94dd-129">Select this option when you want to enable the entity for explicit hierarchies and collections.</span></span> <span data-ttu-id="d94dd-130">Digitare un nome nella casella **nome gerarchia esplicita** .</span><span class="sxs-lookup"><span data-stu-id="d94dd-130">In the **Explicit hierarchy name** box, type a name.</span></span> <span data-ttu-id="d94dd-131">Facoltativamente, selezionare **gerarchia obbligatoria (tutti i membri foglia sono inclusi** per rendere la gerarchia esplicita una gerarchia obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="d94dd-131">Optionally, select **Mandatory hierarchy (all leaf members are included** to make the explicit hierarchy a mandatory hierarchy.</span></span>  
  
9. <span data-ttu-id="d94dd-132">Fare clic su **Salva entità**.</span><span class="sxs-lookup"><span data-stu-id="d94dd-132">Click **Save entity**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="d94dd-133">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="d94dd-133">Next Steps</span></span>  
  
-   [<span data-ttu-id="d94dd-134">Creare un attributo di testo &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="d94dd-134">Create a Text Attribute &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-text-attribute-master-data-services.md)  
  
-   [<span data-ttu-id="d94dd-135">Creare un attributo basato su dominio &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="d94dd-135">Create a Domain-Based Attribute &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-domain-based-attribute-master-data-services.md)  
  
-   [<span data-ttu-id="d94dd-136">Creare un attributo di file &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="d94dd-136">Create a File Attribute &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-file-attribute-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="d94dd-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d94dd-137">See Also</span></span>  
 <span data-ttu-id="d94dd-138">[Entità &#40;Master Data Services&#41;](../../2014/master-data-services/entities-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="d94dd-138">[Entities &#40;Master Data Services&#41;](../../2014/master-data-services/entities-master-data-services.md) </span></span>  
 <span data-ttu-id="d94dd-139">[Gerarchie esplicite &#40;Master Data Services&#41;](../../2014/master-data-services/explicit-hierarchies-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="d94dd-139">[Explicit Hierarchies &#40;Master Data Services&#41;](../../2014/master-data-services/explicit-hierarchies-master-data-services.md) </span></span>  
 <span data-ttu-id="d94dd-140">[Modificare il nome di un'entità &#40;Master Data Services&#41;](edit-an-entity-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="d94dd-140">[Change an Entity Name &#40;Master Data Services&#41;](edit-an-entity-master-data-services.md) </span></span>  
 [<span data-ttu-id="d94dd-141">Eliminare un'entità &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="d94dd-141">Delete an Entity &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/delete-an-entity-master-data-services.md)  
  
  
