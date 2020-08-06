---
title: Oggetti ASSL e caratteristiche degli oggetti | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- reference exceptions [Analysis Services Scripting Language]
- ASSL, objects
- inheritance [Analysis Services Scripting Language]
- localized names [Analysis Services Scripting Language]
- objects [Analysis Services Scripting Language]
- names [Analysis Services Scripting Language]
- Analysis Services Scripting Language, objects
- expansion [Analysis Services Scripting Language]
ms.assetid: 6e5c28b5-c0bc-4ccd-82e5-e174bbb71386
author: minewiskan
ms.author: owend
ms.openlocfilehash: 76d57bb421a7f486983476a6549a5121ce88ee9b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635234"
---
# <a name="assl-objects-and-object-characteristics"></a><span data-ttu-id="186d0-102">Oggetti ASSL e relative caratteristiche</span><span class="sxs-lookup"><span data-stu-id="186d0-102">ASSL Objects and Object Characteristics</span></span>
  <span data-ttu-id="186d0-103">In ASSL (Analysis Services Scripting Language) gli oggetti seguono linee guida specifiche in relazione ai gruppi di oggetti, all'ereditarietà, alla denominazione, all'espansione e all'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="186d0-103">Objects in Analysis Services Scripting Language (ASSL) follow specific guidelines in regards to object groups, inheritance, naming, expansion, and processing.</span></span>  
  
## <a name="object-groups"></a><span data-ttu-id="186d0-104">Gruppi di oggetti</span><span class="sxs-lookup"><span data-stu-id="186d0-104">Object Groups</span></span>  
 <span data-ttu-id="186d0-105">Tutti [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] gli oggetti hanno una rappresentazione XML.</span><span class="sxs-lookup"><span data-stu-id="186d0-105">All [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] objects have an XML representation.</span></span> <span data-ttu-id="186d0-106">Gli oggetti sono suddivisi in due gruppi:</span><span class="sxs-lookup"><span data-stu-id="186d0-106">The objects are divided into two groups:</span></span>  
  
 <span data-ttu-id="186d0-107">**Oggetti principali**</span><span class="sxs-lookup"><span data-stu-id="186d0-107">**Major objects**</span></span>  
 <span data-ttu-id="186d0-108">Gli oggetti principali possono essere creati, modificati ed eliminati in modo indipendente.</span><span class="sxs-lookup"><span data-stu-id="186d0-108">Major objects can be independently created, altered, and deleted.</span></span> <span data-ttu-id="186d0-109">Di seguito vengono riportati gli oggetti principali:</span><span class="sxs-lookup"><span data-stu-id="186d0-109">Major objects include:</span></span>  
  
-   <span data-ttu-id="186d0-110">Server</span><span class="sxs-lookup"><span data-stu-id="186d0-110">Servers</span></span>  
  
-   <span data-ttu-id="186d0-111">Database</span><span class="sxs-lookup"><span data-stu-id="186d0-111">Databases</span></span>  
  
-   <span data-ttu-id="186d0-112">Dimensioni</span><span class="sxs-lookup"><span data-stu-id="186d0-112">Dimensions</span></span>  
  
-   <span data-ttu-id="186d0-113">Cubi</span><span class="sxs-lookup"><span data-stu-id="186d0-113">Cubes</span></span>  
  
-   <span data-ttu-id="186d0-114">Gruppi di misure</span><span class="sxs-lookup"><span data-stu-id="186d0-114">Measure groups</span></span>  
  
-   <span data-ttu-id="186d0-115">Partizioni</span><span class="sxs-lookup"><span data-stu-id="186d0-115">Partitions</span></span>  
  
-   <span data-ttu-id="186d0-116">Prospettive</span><span class="sxs-lookup"><span data-stu-id="186d0-116">Perspectives</span></span>  
  
-   <span data-ttu-id="186d0-117">Modelli di data mining</span><span class="sxs-lookup"><span data-stu-id="186d0-117">Mining models</span></span>  
  
-   <span data-ttu-id="186d0-118">Ruoli</span><span class="sxs-lookup"><span data-stu-id="186d0-118">Roles</span></span>  
  
-   <span data-ttu-id="186d0-119">Comandi associati a un server o a un database</span><span class="sxs-lookup"><span data-stu-id="186d0-119">Commands associated with a server or database</span></span>  
  
-   <span data-ttu-id="186d0-120">Origini dati</span><span class="sxs-lookup"><span data-stu-id="186d0-120">Data sources</span></span>  
  
 <span data-ttu-id="186d0-121">Per tenere traccia della propri cronologia e del proprio stato, gli oggetti principali dispongono delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="186d0-121">Major objects have the following properties to track their history and status.</span></span>  
  
-   `CreatedTimestamp`  
  
-   `LastSchemaUpdate`  
  
-   <span data-ttu-id="186d0-122">`LastProcessed` (dove appropriato)</span><span class="sxs-lookup"><span data-stu-id="186d0-122">`LastProcessed` (where appropriate)</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="186d0-123">La classificazione di un oggetto come oggetto principale influisce sul modo in cui un'istanza di [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] considera l'oggetto e sul modo in cui l'oggetto viene gestito nel linguaggio di definizione dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="186d0-123">The classification of an object as a major object affects how an instance of [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] treats that object and how that object is handled in the object definition language.</span></span> <span data-ttu-id="186d0-124">Tale classificazione non garantisce tuttavia che gli strumenti di gestione e di sviluppo di [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] consentiranno la creazione, modifica o l'eliminazione indipendente di questi oggetti.</span><span class="sxs-lookup"><span data-stu-id="186d0-124">However, this classification does not guarantee that [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] management and development tools will allow the independent creation, modification, or deletion of these objects.</span></span>  
  
 <span data-ttu-id="186d0-125">**Oggetti secondari**</span><span class="sxs-lookup"><span data-stu-id="186d0-125">**Minor objects**</span></span>  
 <span data-ttu-id="186d0-126">Gli oggetti secondari possono essere creati, modificati o eliminati solo nell'ambito della creazione, la modifica o l'eliminazione dell'oggetto padre principale.</span><span class="sxs-lookup"><span data-stu-id="186d0-126">Minor objects can only be created, altered, or deleted as part of creating, altering, or deleting the parent major object.</span></span> <span data-ttu-id="186d0-127">Di seguito vengono riportati gli oggetti secondari:</span><span class="sxs-lookup"><span data-stu-id="186d0-127">Minor objects include:</span></span>  
  
-   <span data-ttu-id="186d0-128">Gerarchie e livelli</span><span class="sxs-lookup"><span data-stu-id="186d0-128">Hierarchies and levels</span></span>  
  
-   <span data-ttu-id="186d0-129">Attributi</span><span class="sxs-lookup"><span data-stu-id="186d0-129">Attributes</span></span>  
  
-   <span data-ttu-id="186d0-130">Misure</span><span class="sxs-lookup"><span data-stu-id="186d0-130">Measures</span></span>  
  
-   <span data-ttu-id="186d0-131">Colonne del modello di data mining</span><span class="sxs-lookup"><span data-stu-id="186d0-131">Mining model columns</span></span>  
  
-   <span data-ttu-id="186d0-132">Comandi associati a un cubo</span><span class="sxs-lookup"><span data-stu-id="186d0-132">Commands associated with a cube</span></span>  
  
-   <span data-ttu-id="186d0-133">Aggregazioni</span><span class="sxs-lookup"><span data-stu-id="186d0-133">Aggregations</span></span>  
  
## <a name="object-expansion"></a><span data-ttu-id="186d0-134">Espansione di oggetti</span><span class="sxs-lookup"><span data-stu-id="186d0-134">Object Expansion</span></span>  
 <span data-ttu-id="186d0-135">La restrizione `ObjectExpansion` può essere utilizzata per controllare il grado di espansione dell'oggetto XML ASSL restituito dal server.</span><span class="sxs-lookup"><span data-stu-id="186d0-135">The `ObjectExpansion` restriction can be used to control the degree of expansion of ASSL XML returned by the server.</span></span> <span data-ttu-id="186d0-136">Per questa restrizione sono disponibili le opzioni elencate nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="186d0-136">This restriction has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="186d0-137">Valore di enumerazione</span><span class="sxs-lookup"><span data-stu-id="186d0-137">Enumeration value</span></span>|<span data-ttu-id="186d0-138">Consentito per\<Alter></span><span class="sxs-lookup"><span data-stu-id="186d0-138">Allowed for \<Alter></span></span>|<span data-ttu-id="186d0-139">Descrizione</span><span class="sxs-lookup"><span data-stu-id="186d0-139">Description</span></span>|  
|-----------------------|---------------------------|-----------------|  
|<span data-ttu-id="186d0-140">*ReferenceOnly*</span><span class="sxs-lookup"><span data-stu-id="186d0-140">*ReferenceOnly*</span></span>|<span data-ttu-id="186d0-141">No</span><span class="sxs-lookup"><span data-stu-id="186d0-141">no</span></span>|<span data-ttu-id="186d0-142">Restituisce solo il nome, l'ID e il timestamp per l'oggetto richiesto e per tutti gli oggetti principali contenuti in modo ricorsivo.</span><span class="sxs-lookup"><span data-stu-id="186d0-142">Returns only the name, ID, and timestamp for the requested object and for all contained major objects recursively.</span></span>|  
|<span data-ttu-id="186d0-143">*ObjectProperties*</span><span class="sxs-lookup"><span data-stu-id="186d0-143">*ObjectProperties*</span></span>|<span data-ttu-id="186d0-144">sì</span><span class="sxs-lookup"><span data-stu-id="186d0-144">yes</span></span>|<span data-ttu-id="186d0-145">Espande l'oggetto richiesto e gli oggetti secondari contenuti, ma non restituisce alcun oggetto principale contenuto.</span><span class="sxs-lookup"><span data-stu-id="186d0-145">Expands the requested object and minor contained objects, but does not return major contained objects.</span></span>|  
|<span data-ttu-id="186d0-146">*ExpandObject*</span><span class="sxs-lookup"><span data-stu-id="186d0-146">*ExpandObject*</span></span>|<span data-ttu-id="186d0-147">No</span><span class="sxs-lookup"><span data-stu-id="186d0-147">no</span></span>|<span data-ttu-id="186d0-148">Come per *ObjectProperties*, ma restituisce inoltre il nome, l'ID e il timestamp per gli oggetti principali contenuti.</span><span class="sxs-lookup"><span data-stu-id="186d0-148">Same as *ObjectProperties*, but also returns the name, ID, and timestamp for contained major objects.</span></span>|  
|<span data-ttu-id="186d0-149">*ExpandFull*</span><span class="sxs-lookup"><span data-stu-id="186d0-149">*ExpandFull*</span></span>|<span data-ttu-id="186d0-150">sì</span><span class="sxs-lookup"><span data-stu-id="186d0-150">yes</span></span>|<span data-ttu-id="186d0-151">Espande completamente l'oggetto richiesto e tutti gli oggetti contenuti in modo ricorsivo.</span><span class="sxs-lookup"><span data-stu-id="186d0-151">Fully expands the requested object and all contained objects recursively.</span></span>|  
  
 <span data-ttu-id="186d0-152">Questa sezione di riferimento ASSL descrive la rappresentazione *ExpandFull* .</span><span class="sxs-lookup"><span data-stu-id="186d0-152">This ASSL reference section describes the *ExpandFull* representation.</span></span> <span data-ttu-id="186d0-153">Tutti gli altri livelli di `ObjectExpansion` derivano da tale livello.</span><span class="sxs-lookup"><span data-stu-id="186d0-153">All other `ObjectExpansion` levels are derived from this level.</span></span>  
  
## <a name="object-processing"></a><span data-ttu-id="186d0-154">Elaborazione di oggetti</span><span class="sxs-lookup"><span data-stu-id="186d0-154">Object Processing</span></span>  
 <span data-ttu-id="186d0-155">In ASSL sono disponibili elementi o proprietà di sola lettura (ad esempio `LastProcessed`) che possono essere letti dall'istanza di [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)], ma che vengono omessi quando gli script del comando vengono inviati all'istanza.</span><span class="sxs-lookup"><span data-stu-id="186d0-155">ASSL includes read-only elements or properties (for example, `LastProcessed`) that can be read from the [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] instance, but which are omitted when command scripts are submitted to the instance.</span></span> [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] <span data-ttu-id="186d0-156">ignora senza preavviso valori modificati per gli elementi di sola lettura o errore.</span><span class="sxs-lookup"><span data-stu-id="186d0-156">ignores modified values for read-only elements without warning or error.</span></span>  
  
 [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] <span data-ttu-id="186d0-157">ignora inoltre le proprietà non appropriate o non rilevanti senza generare errori di convalida.</span><span class="sxs-lookup"><span data-stu-id="186d0-157">also ignores inappropriate or irrelevant properties without raising validation errors.</span></span> <span data-ttu-id="186d0-158">L'elemento X deve essere presente ad esempio solo quando all'elemento Y è associato valore specifico.</span><span class="sxs-lookup"><span data-stu-id="186d0-158">For example, the X element should only be present when the Y element has a particular value.</span></span> <span data-ttu-id="186d0-159">L'istanza di [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] ignora l'elemento X anziché convalidarlo rispetto al valore dell'elemento Y.</span><span class="sxs-lookup"><span data-stu-id="186d0-159">The [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] instance ignores the X element instead of validating that element against the value of the Y element.</span></span>  
  
  
