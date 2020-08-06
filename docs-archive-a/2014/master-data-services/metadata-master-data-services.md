---
title: Metadati (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- user-defined metadata [Master Data Services], about user-defined metadata
- metadata [Master Data Services], about metadata
- metadata [Master Data Services]
- user-defined metadata [Master Data Services]
ms.assetid: ac1aabe3-d8d4-4d7a-8954-50ee3c185d81
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 39ab95b7925306febb551962495da7ec9751589b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714491"
---
# <a name="metadata-master-data-services"></a><span data-ttu-id="d7e05-102">Metadati (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="d7e05-102">Metadata (Master Data Services)</span></span>
  <span data-ttu-id="d7e05-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] i metadati definiti dall'utente sono informazioni utilizzate per descrivere gli oggetti modello.</span><span class="sxs-lookup"><span data-stu-id="d7e05-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], user-defined metadata is information that you use to describe model objects.</span></span> <span data-ttu-id="d7e05-104">È ad esempio possibile tenere traccia dei proprietari di un particolare modello o entità oppure dei sistemi di origine tramite cui vengono forniti dati a un'entità.</span><span class="sxs-lookup"><span data-stu-id="d7e05-104">For example, you may want to track the owners of a particular model or entity, or track the source systems that supply data to an entity.</span></span>  
  
 <span data-ttu-id="d7e05-105">I metadati definiti dall'utente sono gestiti da un modello denominato **metadati**.</span><span class="sxs-lookup"><span data-stu-id="d7e05-105">User-defined metadata is managed by a model called **Metadata**.</span></span> <span data-ttu-id="d7e05-106">Questo modello viene incluso automaticamente durante l' [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] installazione di ed è simile a tutti gli altri modelli MDS, ad eccezione del fatto che non è possibile crearne versioni.</span><span class="sxs-lookup"><span data-stu-id="d7e05-106">This model is automatically included when [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] is installed, and it is similar to all other MDS models, except that you cannot create versions of it.</span></span>  
  
 <span data-ttu-id="d7e05-107">Dopo aver popolato il modello Metadati con metadati definiti dall'utente, è possibile includerlo nelle viste sottoscrizioni, in modo che possa essere utilizzato dai sistemi di sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="d7e05-107">After you populate the Metadata model with user-defined metadata, you can include it in subscription views, so it can be consumed by subscribing systems.</span></span>  
  
## <a name="metadata-entities"></a><span data-ttu-id="d7e05-108">Entità dei metadati</span><span class="sxs-lookup"><span data-stu-id="d7e05-108">Metadata Entities</span></span>  
 <span data-ttu-id="d7e05-109">Nel modello Metadati sono incluse cinque entità, ognuna delle quali rappresenta un tipo di oggetto modello di dati master che supporta i metadati definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="d7e05-109">The Metadata model includes five entities, each of which represents a type of master data model object that supports user-defined metadata.</span></span> <span data-ttu-id="d7e05-110">L'entità di **definizione dei metadati del modello** , ad esempio, contiene membri che rappresentano modelli e l'entità di **definizione dei metadati dell'attributo** dispone di membri che rappresentano tutti gli attributi in tutti i modelli.</span><span class="sxs-lookup"><span data-stu-id="d7e05-110">For example, the **Model Metadata Definition** entity contains members that represent models, and the **Attribute Metadata Definition** entity has members that represent all attributes in all models.</span></span>  
  
 <span data-ttu-id="d7e05-111">Per definire i metadati per un oggetto modello, è necessario popolare uno di questi attributi del membro.</span><span class="sxs-lookup"><span data-stu-id="d7e05-111">To define metadata for a model object, you populate one of these member's attributes.</span></span> <span data-ttu-id="d7e05-112">Nell'entità **definizione dei metadati dell'entità** , ad esempio, è possibile popolare l'attributo Description del membro Price con il testo: **il prezzo del prodotto quando è venduto a un cliente**.</span><span class="sxs-lookup"><span data-stu-id="d7e05-112">For example, in the **Entity Metadata Definition** entity, you can populate the Price member's Description attribute with the text: **The product price when sold to a customer**.</span></span>  
  
 <span data-ttu-id="d7e05-113">I membri nel modello Metadati vengono aggiornati automaticamente ogni volta che gli oggetti modello che supportano i metadati definiti dall'utente vengono aggiunti o eliminati.</span><span class="sxs-lookup"><span data-stu-id="d7e05-113">The members in the Metadata model are automatically updated whenever model objects that support user-defined metadata are added or deleted.</span></span>  
  
 <span data-ttu-id="d7e05-114">Non è possibile controllare la versione, aggiungere o modificare i flag di versione oppure salvare il modello Metadati come pacchetto di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="d7e05-114">The Metadata model cannot be versioned, have version flags added or changed, or be saved as a model deployment package.</span></span> <span data-ttu-id="d7e05-115">Tuttavia, sono disponibili le stesse funzionalità degli altri modelli di dati master.</span><span class="sxs-lookup"><span data-stu-id="d7e05-115">However, it has all the same other functionality available to other master data models.</span></span> <span data-ttu-id="d7e05-116">È ad esempio possibile implementare un set di regole business sul modello di metadati per applicare i criteri dati.</span><span class="sxs-lookup"><span data-stu-id="d7e05-116">For example, you might implement a set of business rules on the Metadata model to enforce data policies.</span></span>  
  
## <a name="customizing-your-metadata-model"></a><span data-ttu-id="d7e05-117">Personalizzazione del modello dei metadati</span><span class="sxs-lookup"><span data-stu-id="d7e05-117">Customizing Your Metadata Model</span></span>  
 <span data-ttu-id="d7e05-118">Ciascuna entità di definizione dei metadati include gli attributi Name, Code e Description.</span><span class="sxs-lookup"><span data-stu-id="d7e05-118">Each metadata definition entity includes Name, Code, and Description attributes.</span></span> <span data-ttu-id="d7e05-119">È necessario creare attributi aggiuntivi per descrivere ulteriormente gli oggetti modello.</span><span class="sxs-lookup"><span data-stu-id="d7e05-119">You may want to create additional attributes to further describe your model objects.</span></span>  
  
 <span data-ttu-id="d7e05-120">Può, ad esempio, essere necessario creare:</span><span class="sxs-lookup"><span data-stu-id="d7e05-120">For example, you might create:</span></span>  
  
-   <span data-ttu-id="d7e05-121">Un attributo basato su dominio chiamato Owner da utilizzare per tenere traccia del proprietario di ciascun oggetto modello.</span><span class="sxs-lookup"><span data-stu-id="d7e05-121">A domain-based attribute named Owner, which you use to track the owner of each model object.</span></span>  
  
-   <span data-ttu-id="d7e05-122">Un attributo in formato libero chiamato Last Review Date da utilizzare per tenere traccia dell'ultima data in cui un oggetto è stato rivisto dal proprietario.</span><span class="sxs-lookup"><span data-stu-id="d7e05-122">A free-form attribute named Last Review Date, which you use to track the date that an object was last reviewed by the owner.</span></span>  
  
-   <span data-ttu-id="d7e05-123">Un attributo basato su dominio denominato Sources, che consente di tenere traccia e gestire i sistemi di origine che interagiscono con l' [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] istanza di.</span><span class="sxs-lookup"><span data-stu-id="d7e05-123">A domain-based attribute named Sources, which you use to track and manage the source systems that interact with the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] instance.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="d7e05-124">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="d7e05-124">Related Tasks</span></span>  
  
|<span data-ttu-id="d7e05-125">Descrizione dell'attività</span><span class="sxs-lookup"><span data-stu-id="d7e05-125">Task Description</span></span>|<span data-ttu-id="d7e05-126">Argomento</span><span class="sxs-lookup"><span data-stu-id="d7e05-126">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="d7e05-127">Aggiungere metadati a un oggetto modello.</span><span class="sxs-lookup"><span data-stu-id="d7e05-127">Add metadata to a model object.</span></span>|[<span data-ttu-id="d7e05-128">Aggiungere metadati &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="d7e05-128">Add Metadata &#40;Master Data Services&#41;</span></span>](add-metadata-master-data-services.md)
|&nbsp;|&nbsp;|
  
## <a name="related-content"></a><span data-ttu-id="d7e05-129">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="d7e05-129">Related Content</span></span>  
  
-   [<span data-ttu-id="d7e05-130">Esportazione dei dati &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="d7e05-130">Exporting Data &#40;Master Data Services&#41;</span></span>](overview-exporting-data-master-data-services.md)  
  
  
