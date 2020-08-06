---
title: Modelli (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- models [Master Data Services], about models
- models [Master Data Services]
ms.assetid: 9f862a3d-25ab-41e9-b833-1db99959e825
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 1d5a4a431d3ca7b6fa499de68a2bc4c5033cd086
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637385"
---
# <a name="models-master-data-services"></a><span data-ttu-id="07af8-102">Modelli (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="07af8-102">Models (Master Data Services)</span></span>
  <span data-ttu-id="07af8-103">I modelli rappresentano il livello più elevato di organizzazione dei dati in [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="07af8-103">Models are the highest level of data organization in [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)].</span></span> <span data-ttu-id="07af8-104">Un modello definisce la struttura di dati nella soluzione di gestione dati master.</span><span class="sxs-lookup"><span data-stu-id="07af8-104">A model defines the structure of data in your master data management solution.</span></span> <span data-ttu-id="07af8-105">Un modello contiene gli oggetti seguenti:</span><span class="sxs-lookup"><span data-stu-id="07af8-105">A model contains the following objects:</span></span>  
  
-   <span data-ttu-id="07af8-106">Entità</span><span class="sxs-lookup"><span data-stu-id="07af8-106">Entities</span></span>  
  
-   <span data-ttu-id="07af8-107">Attributi e gruppi di attributi</span><span class="sxs-lookup"><span data-stu-id="07af8-107">Attributes and attribute groups</span></span>  
  
-   <span data-ttu-id="07af8-108">Gerarchie derivate ed esplicite</span><span class="sxs-lookup"><span data-stu-id="07af8-108">Explicit and derived hierarchies</span></span>  
  
-   <span data-ttu-id="07af8-109">Raccolte</span><span class="sxs-lookup"><span data-stu-id="07af8-109">Collections</span></span>  
  
 <span data-ttu-id="07af8-110">I modelli organizzano la struttura dei dati master.</span><span class="sxs-lookup"><span data-stu-id="07af8-110">Models organize the structure of your master data.</span></span> <span data-ttu-id="07af8-111">L'implementazione di [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] può avere uno o più modelli che raggruppano tipi di dati simili.</span><span class="sxs-lookup"><span data-stu-id="07af8-111">Your [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] implementation can have one or many models that each group similar kinds of data.</span></span> <span data-ttu-id="07af8-112">I dati master rientrano in genere in una delle quattro categorie seguenti: persone, luoghi, cose o concetti.</span><span class="sxs-lookup"><span data-stu-id="07af8-112">In general, master data can be categorized in one of four ways: people, places, things, or concepts.</span></span> <span data-ttu-id="07af8-113">È ad esempio possibile creare un modello Product per contenere dati relativi al prodotto oppure un modello Customer per contenere dati relativi al cliente.</span><span class="sxs-lookup"><span data-stu-id="07af8-113">For example, you can create a Product model to contain product-related data or a Customer model to contain customer-related data.</span></span>  
  
 <span data-ttu-id="07af8-114">È possibile assegnare le autorizzazioni di utenti e gruppi per visualizzare e aggiornare oggetti all'interno del modello.</span><span class="sxs-lookup"><span data-stu-id="07af8-114">You can assign users and groups permission to view and update objects within the model.</span></span> <span data-ttu-id="07af8-115">Se non si assegnano autorizzazioni al modello, questo non verrà visualizzato.</span><span class="sxs-lookup"><span data-stu-id="07af8-115">If you do not give permission to the model, it is not displayed.</span></span>  
  
 <span data-ttu-id="07af8-116">In qualsiasi momento è possibile creare copie dei dati master all'interno di un modello.</span><span class="sxs-lookup"><span data-stu-id="07af8-116">At any given time, you can create copies of the master data within a model.</span></span> <span data-ttu-id="07af8-117">Queste copie sono denominate versioni.</span><span class="sxs-lookup"><span data-stu-id="07af8-117">These copies are called versions.</span></span>  
  
 <span data-ttu-id="07af8-118">Dopo aver definito un modello in un ambiente di prova, è possibile distribuirlo, con o senza i dati corrispondenti, dall'ambiente di prova in un ambiente di produzione.</span><span class="sxs-lookup"><span data-stu-id="07af8-118">When you have defined a model in a test environment, you can deploy it, with or without the corresponding data, from the test environment to a production environment.</span></span> <span data-ttu-id="07af8-119">In questo modo viene eliminata la necessità di ricreare i modelli nell'ambiente di produzione.</span><span class="sxs-lookup"><span data-stu-id="07af8-119">This eliminates the need to recreate your models in your production environment.</span></span>  
  
## <a name="how-models-relate-to-other-objects"></a><span data-ttu-id="07af8-120">Correlazione tra modelli e altri oggetti</span><span class="sxs-lookup"><span data-stu-id="07af8-120">How Models Relate to Other Objects</span></span>  
 <span data-ttu-id="07af8-121">Un modello contiene entità.</span><span class="sxs-lookup"><span data-stu-id="07af8-121">A model contains entities.</span></span> <span data-ttu-id="07af8-122">Le entità contengono attributi, gerarchie esplicite e raccolte.</span><span class="sxs-lookup"><span data-stu-id="07af8-122">Entities contain attributes, explicit hierarchies, and collections.</span></span> <span data-ttu-id="07af8-123">È possibile contenere gli attributi in gruppi di attributi.</span><span class="sxs-lookup"><span data-stu-id="07af8-123">Attributes can be contained in attribute groups.</span></span> <span data-ttu-id="07af8-124">Gli attributi si dicono basati su dominio quando un'entità viene utilizzata come un attributo per un'altra entità.</span><span class="sxs-lookup"><span data-stu-id="07af8-124">Domain-based attributes exist when an entity is used as an attribute for another entity.</span></span>  
  
 <span data-ttu-id="07af8-125">La seguente immagine illustra la relazione tra gli oggetti di un modello.</span><span class="sxs-lookup"><span data-stu-id="07af8-125">This image shows the relationships among the objects in a model.</span></span>  
  
 <span data-ttu-id="07af8-126">![Oggetti in un modello Master Data Services](../../2014/master-data-services/media/mds-conc-model-circles.gif "Oggetti in un modello Master Data Services")</span><span class="sxs-lookup"><span data-stu-id="07af8-126">![Objects in a Master Data Services Model](../../2014/master-data-services/media/mds-conc-model-circles.gif "Objects in a Master Data Services Model")</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="07af8-127">Anche le gerarchie derivate sono oggetti modello, ma non sono presenti nell'immagine.</span><span class="sxs-lookup"><span data-stu-id="07af8-127">Derived hierarchies are also model objects, but they are not shown in the image.</span></span> <span data-ttu-id="07af8-128">Le gerarchie derivate sono basate sulle relazioni tra gli attributi basati su dominio che esistono in un modello.</span><span class="sxs-lookup"><span data-stu-id="07af8-128">Derived hierarchies are derived from the domain-based attribute relationships that exist between entities.</span></span> <span data-ttu-id="07af8-129">Vedere [Gerarchie derivate &#40;Master Data Services&#41;](derived-hierarchies-master-data-services.md) per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="07af8-129">See [Derived Hierarchies &#40;Master Data Services&#41;](derived-hierarchies-master-data-services.md) for more information.</span></span>  
  
 <span data-ttu-id="07af8-130">I dati master sono i dati contenuti negli oggetti modello.</span><span class="sxs-lookup"><span data-stu-id="07af8-130">Master data is the data that is contained in the model objects.</span></span> <span data-ttu-id="07af8-131">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], i dati master vengono archiviati come membri all'interno di un'entità.</span><span class="sxs-lookup"><span data-stu-id="07af8-131">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], master data is stored as members in an entity.</span></span>  
  
 <span data-ttu-id="07af8-132">Gli oggetti modello vengono gestiti nell'area funzionale **Amministrazione sistema** dell'interfaccia utente di [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="07af8-132">Model objects are maintained in the **System Administration** functional area of the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] user interface.</span></span>  
  
## <a name="model-example"></a><span data-ttu-id="07af8-133">Esempio di modello</span><span class="sxs-lookup"><span data-stu-id="07af8-133">Model Example</span></span>  
 <span data-ttu-id="07af8-134">Nell'esempio seguente, gli oggetti del modello Product raggruppano in modo logico i dati relativi al prodotto.</span><span class="sxs-lookup"><span data-stu-id="07af8-134">In the following example, the objects in the Product model logically group product-related data.</span></span>  
  
 <span data-ttu-id="07af8-135">![Esempio di dati master del modello del prodotto](../../2014/master-data-services/media/mds-conc-model.gif "Esempio di dati master del modello del prodotto")</span><span class="sxs-lookup"><span data-stu-id="07af8-135">![Product Model Master Data Example](../../2014/master-data-services/media/mds-conc-model.gif "Product Model Master Data Example")</span></span>  
  
 <span data-ttu-id="07af8-136">Altri modelli comuni sono:</span><span class="sxs-lookup"><span data-stu-id="07af8-136">Other common models are:</span></span>  
  
-   <span data-ttu-id="07af8-137">Conti, che potrebbe includere entità quali conti patrimoniali, conti economici, statistiche e tipo di conto.</span><span class="sxs-lookup"><span data-stu-id="07af8-137">Accounts, which could include entities such as balance sheet accounts, income statement accounts, statistics, and account type.</span></span>  
  
-   <span data-ttu-id="07af8-138">Cliente, che potrebbe includere entità quale genere, livello di istruzione, occupazione e stato civile.</span><span class="sxs-lookup"><span data-stu-id="07af8-138">Customer, which could include entities such as gender, education, occupation, and marital status.</span></span>  
  
-   <span data-ttu-id="07af8-139">Geografia, che potrebbe includere entità quali codici postali, paesi, città, province, regioni, stati e continenti.</span><span class="sxs-lookup"><span data-stu-id="07af8-139">Geography, which could include entities such as postal codes, cities, counties, states, provinces, regions, territories, countries, and continents.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="07af8-140">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="07af8-140">Related Tasks</span></span>  
  
|<span data-ttu-id="07af8-141">Descrizione dell'attività</span><span class="sxs-lookup"><span data-stu-id="07af8-141">Task Description</span></span>|<span data-ttu-id="07af8-142">Argomento</span><span class="sxs-lookup"><span data-stu-id="07af8-142">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="07af8-143">Creare un modello per organizzare i dati master.</span><span class="sxs-lookup"><span data-stu-id="07af8-143">Create a model to organize your master data.</span></span>|[<span data-ttu-id="07af8-144">Creare un modello &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="07af8-144">Create a Model &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-model-master-data-services.md)|  
|<span data-ttu-id="07af8-145">Modificare il nome di un modello esistente.</span><span class="sxs-lookup"><span data-stu-id="07af8-145">Change the name of an existing model.</span></span>|[<span data-ttu-id="07af8-146">Modificare il nome di un modello &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="07af8-146">Change a Model Name &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/change-a-model-name-master-data-services.md)|  
|<span data-ttu-id="07af8-147">Eliminare un modello esistente.</span><span class="sxs-lookup"><span data-stu-id="07af8-147">Delete an existing model.</span></span>|[<span data-ttu-id="07af8-148">Eliminare un modello &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="07af8-148">Delete a Model &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/delete-a-model-master-data-services.md)|  
  
## <a name="related-content"></a><span data-ttu-id="07af8-149">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="07af8-149">Related Content</span></span>  
  
-   [<span data-ttu-id="07af8-150">Panoramica di Master Data Services</span><span class="sxs-lookup"><span data-stu-id="07af8-150">Master Data Services Overview</span></span>](master-data-services-overview-mds.md)  
  
-   [<span data-ttu-id="07af8-151">Entità &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="07af8-151">Entities &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/entities-master-data-services.md)  
  
-   [<span data-ttu-id="07af8-152">Attributi &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="07af8-152">Attributes &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/attributes-master-data-services.md)  
  
-   [<span data-ttu-id="07af8-153">Distribuzione di modelli &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="07af8-153">Deploying Models &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/deploying-models-master-data-services.md)  
  
-   [<span data-ttu-id="07af8-154">Autorizzazioni per oggetti modello &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="07af8-154">Model Object Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/model-object-permissions-master-data-services.md)  
  
  
