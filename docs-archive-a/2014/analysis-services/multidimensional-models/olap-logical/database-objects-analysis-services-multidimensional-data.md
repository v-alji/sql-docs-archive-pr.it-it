---
title: Oggetti di database (Analysis Services-Dati multidimensionali) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- objects [Analysis Services], about objects
- SQL Server Analysis Services, objects
- Analysis Services objects, about Analysis Services objects
- SSAS, objects
- Analysis Services objects
- objects [Analysis Services]
ms.assetid: f76d869b-fc1d-4807-9f28-da09c7be382d
author: minewiskan
ms.author: owend
ms.openlocfilehash: d61e3213356146e1cf9e452e0b62e02c96bd4902
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727247"
---
# <a name="database-objects-analysis-services---multidimensional-data"></a><span data-ttu-id="ac439-102">Oggetti di database (Analysis Services - Dati multidimensionali)</span><span class="sxs-lookup"><span data-stu-id="ac439-102">Database Objects (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="ac439-103">Un' [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] istanza di contiene gli assembly e gli oggetti di database da utilizzare con Online Analytical Processing (OLAP) e data mining.</span><span class="sxs-lookup"><span data-stu-id="ac439-103">A [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] instance contains database objects and assemblies for use with online analytical processing (OLAP) and data mining.</span></span>  
  
-   <span data-ttu-id="ac439-104">I database contengono oggetti OLAP e di data mining, ad esempio origini dei dati, viste origine dati, cubi, misure, gruppi di misure, dimensioni, attributi, gerarchie, strutture di data mining, modelli di data mining e ruoli.</span><span class="sxs-lookup"><span data-stu-id="ac439-104">Databases contain OLAP and data mining objects, such as data sources, data source views, cubes, measures, measure groups, dimensions, attributes, hierarchies, mining structures, mining models and roles.</span></span>  
  
-   <span data-ttu-id="ac439-105">Gli assembly contengono le funzioni definite dall'utente che estendono la funzionalità delle funzioni intrinseche disponibili nei linguaggi MDX (Multidimensional Expressions) e DMX (Data Mining Extensions).</span><span class="sxs-lookup"><span data-stu-id="ac439-105">Assemblies contain user-defined functions that extend the functionality of the intrinsic functions provided with the Multidimensional Expressions (MDX) and Data Mining Extensions (DMX) languages.</span></span>  
  
 <span data-ttu-id="ac439-106">L'oggetto <xref:Microsoft.AnalysisServices.Database> è il contenitore per tutti gli oggetti dati necessari per un progetto Business Intelligence, ad esempio cubi, dimensioni e strutture di data mining OLAP, e per gli oggetti di supporto, ad esempio <xref:Microsoft.AnalysisServices.DataSource>, <xref:Microsoft.AnalysisServices.Account> e <xref:Microsoft.AnalysisServices.Role>.</span><span class="sxs-lookup"><span data-stu-id="ac439-106">The <xref:Microsoft.AnalysisServices.Database> object is the container for all data objects that are needed for a business intelligence project (such as OLAP cubes, dimensions, and data mining structures), and their supporting objects (such as <xref:Microsoft.AnalysisServices.DataSource>, <xref:Microsoft.AnalysisServices.Account>, and <xref:Microsoft.AnalysisServices.Role>).</span></span>  
  
 <span data-ttu-id="ac439-107">Un oggetto <xref:Microsoft.AnalysisServices.Database> fornisce l'accesso agli oggetti e agli attributi che includono quanto segue:</span><span class="sxs-lookup"><span data-stu-id="ac439-107">A <xref:Microsoft.AnalysisServices.Database> object provides access to objects and attributes that include the following:</span></span>  
  
-   <span data-ttu-id="ac439-108">Tutti i cubi a cui è possibile accedere, sotto forma di raccolta.</span><span class="sxs-lookup"><span data-stu-id="ac439-108">All cubes that you can access, as a collection.</span></span>  
  
-   <span data-ttu-id="ac439-109">Tutte le dimensioni a cui è possibile accedere, sotto forma di raccolta.</span><span class="sxs-lookup"><span data-stu-id="ac439-109">All dimensions that you can access, as a collection.</span></span>  
  
-   <span data-ttu-id="ac439-110">Tutte le strutture di data mining a cui è possibile accedere, sotto forma di raccolta.</span><span class="sxs-lookup"><span data-stu-id="ac439-110">All mining structures that you can access, as a collection.</span></span>  
  
-   <span data-ttu-id="ac439-111">Tutte le origini dati e le viste origine dati, sotto forma di due raccolte.</span><span class="sxs-lookup"><span data-stu-id="ac439-111">All data sources and data source views, as two collections.</span></span>  
  
-   <span data-ttu-id="ac439-112">Tutti i ruoli e le autorizzazioni per il database, sotto forma di due raccolte.</span><span class="sxs-lookup"><span data-stu-id="ac439-112">All roles and database permissions, as two collections.</span></span>  
  
-   <span data-ttu-id="ac439-113">I valori delle regole di confronto per il database.</span><span class="sxs-lookup"><span data-stu-id="ac439-113">The collation value for the database.</span></span>  
  
-   <span data-ttu-id="ac439-114">Le dimensioni stimate del database.</span><span class="sxs-lookup"><span data-stu-id="ac439-114">The estimated size of the database.</span></span>  
  
-   <span data-ttu-id="ac439-115">Il valore della lingua del database.</span><span class="sxs-lookup"><span data-stu-id="ac439-115">The language value of the database.</span></span>  
  
-   <span data-ttu-id="ac439-116">L'impostazione di visibilità per il database.</span><span class="sxs-lookup"><span data-stu-id="ac439-116">The visible setting for the database.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ac439-117">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="ac439-117">In This Section</span></span>  
 <span data-ttu-id="ac439-118">Negli argomenti seguenti vengono descritti gli oggetti condivisi sia dalle caratteristiche OLAP che da quelle di data mining in [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ac439-118">The following topics describe objects shared by both OLAP and data mining features in [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span></span>  
  
|<span data-ttu-id="ac439-119">Argomento</span><span class="sxs-lookup"><span data-stu-id="ac439-119">Topic</span></span>|<span data-ttu-id="ac439-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ac439-120">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="ac439-121">Origini dati nei modelli multidimensionali</span><span class="sxs-lookup"><span data-stu-id="ac439-121">Data Sources in Multidimensional Models</span></span>](../data-sources-in-multidimensional-models.md)|<span data-ttu-id="ac439-122">Descrive un'origine dei dati in [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ac439-122">Describes a data source in [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="ac439-123">Viste origine dati in modelli multidimensionali</span><span class="sxs-lookup"><span data-stu-id="ac439-123">Data Source Views in Multidimensional Models</span></span>](../data-source-views-in-multidimensional-models.md)|<span data-ttu-id="ac439-124">Descrive un modello di dati logico basato su una o più origini dei dati in [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ac439-124">Describes a logical data model based on one or more data sources, in [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="ac439-125">Cubi nei modelli multidimensionali</span><span class="sxs-lookup"><span data-stu-id="ac439-125">Cubes in Multidimensional Models</span></span>](../cubes-in-multidimensional-models.md)|<span data-ttu-id="ac439-126">Descrive i cubi e gli oggetti dei cubi, inclusi gruppi di misure, misure, relazioni tra l'utilizzo delle dimensioni, calcoli, indicatori di prestazioni chiavi, azioni, traduzioni, partizioni e prospettive.</span><span class="sxs-lookup"><span data-stu-id="ac439-126">Describes cubes and cube objects, including measures, measure groups, dimension usage relationships, calculations, key performance indicators, actions, translations, partitions, and perspectives.</span></span>|  
|[<span data-ttu-id="ac439-127">Dimensioni &#40;Analysis Services - Dati multidimensionali&#41;</span><span class="sxs-lookup"><span data-stu-id="ac439-127">Dimensions &#40;Analysis Services - Multidimensional Data&#41;</span></span>](../../multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md)|<span data-ttu-id="ac439-128">Descrive le dimensioni e gli oggetti delle dimensioni, inclusi attributi, relazioni tra attributi, gerarchie, livelli e membri.</span><span class="sxs-lookup"><span data-stu-id="ac439-128">Describes dimensions and dimension objects, including attributes, attribute relationships, hierarchies, levels, and members.</span></span>|  
|[<span data-ttu-id="ac439-129">Strutture di data mining &#40;Analysis Services - Data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="ac439-129">Mining Structures &#40;Analysis Services - Data Mining&#41;</span></span>](../../data-mining/mining-structures-analysis-services-data-mining.md)|<span data-ttu-id="ac439-130">Descrive le strutture e gli oggetti di data mining, inclusi i modelli di data mining.</span><span class="sxs-lookup"><span data-stu-id="ac439-130">Describes mining structures and mining objects, including mining models.</span></span>|  
|[<span data-ttu-id="ac439-131">Ruoli di sicurezza &#40;Analysis Services - Dati multidimensionali&#41;</span><span class="sxs-lookup"><span data-stu-id="ac439-131">Security Roles  &#40;Analysis Services - Multidimensional Data&#41;</span></span>](security-roles-analysis-services-multidimensional-data.md)|<span data-ttu-id="ac439-132">Descrive un ruolo, ovvero il meccanismo di sicurezza utilizzato per controllare l'accesso agli oggetti in [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ac439-132">Describes a role, the security mechanism used to control access to objects in [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="ac439-133">Gestione di assembly di modelli multidimensionali</span><span class="sxs-lookup"><span data-stu-id="ac439-133">Multidimensional Model Assemblies Management</span></span>](../multidimensional-model-assemblies-management.md)|<span data-ttu-id="ac439-134">Descrive un assembly, ovvero una raccolta di funzioni definite dall'utente utilizzate per estendere i linguaggi MDX e DMX in [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ac439-134">Describes an assembly, a collection of user-defined functions used to extend the MDX and DMX languages, in [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ac439-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ac439-135">See Also</span></span>  
 <span data-ttu-id="ac439-136">[Origini dati supportate &#40;SSAS multidimensionale&#41;](../supported-data-sources-ssas-multidimensional.md) </span><span class="sxs-lookup"><span data-stu-id="ac439-136">[Data Sources Supported &#40;SSAS Multidimensional&#41;](../supported-data-sources-ssas-multidimensional.md) </span></span>  
 <span data-ttu-id="ac439-137">[Soluzioni di modelli multidimensionali &#40;SSAS&#41;](../multidimensional-model-solutions-ssas.md) </span><span class="sxs-lookup"><span data-stu-id="ac439-137">[Multidimensional Model Solutions &#40;SSAS&#41;](../multidimensional-model-solutions-ssas.md) </span></span>  
 [<span data-ttu-id="ac439-138">Soluzioni di data mining</span><span class="sxs-lookup"><span data-stu-id="ac439-138">Data Mining Solutions</span></span>](../../data-mining/data-mining-solutions.md)  
  
  
