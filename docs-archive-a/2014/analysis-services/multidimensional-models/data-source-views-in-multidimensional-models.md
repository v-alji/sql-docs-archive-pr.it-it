---
title: Viste origine dati in modelli multidimensionali | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data source views [Analysis Services]
- data source views [Analysis Services], about data source views
- SQL Server Analysis Services, data source views
- data source views [Analysis Services], multiple
- Analysis Services, data source views
- multiple data source views
- SSAS, data source views
ms.assetid: 4c12376f-4fc2-492b-9a00-93eec34571ed
author: minewiskan
ms.author: owend
ms.openlocfilehash: 1aef6b6d716ec71ac082ca8b7c042492c1712b1a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725091"
---
# <a name="data-source-views-in-multidimensional-models"></a><span data-ttu-id="7c60f-102">Viste origine dati in modelli multidimensionali</span><span class="sxs-lookup"><span data-stu-id="7c60f-102">Data Source Views in Multidimensional Models</span></span>
  <span data-ttu-id="7c60f-103">Una vista origine dati è un'astrazione di un'origine dati relazionale che diventa la base dei cubi e delle dimensioni creati in un progetto multidimensionale.</span><span class="sxs-lookup"><span data-stu-id="7c60f-103">A data source view (DSV) is an abstraction of a relational data source that becomes the basis of the cubes and dimensions you create in a multidimensional project.</span></span> <span data-ttu-id="7c60f-104">Lo scopo di una vista origine dati è fornire il controllo sulle strutture di dati utilizzate nel progetto e funzionare indipendentemente dalle origini dati sottostanti (ad esempio, con la possibilità di rinominare o concatenare colonne senza modificare direttamente l'origine dati originale).</span><span class="sxs-lookup"><span data-stu-id="7c60f-104">The purpose of a DSV is to give you control over the data structures used in your project, and to work independently of the underlying data sources (for example, the ability to rename or concatenate columns without directly modifying the original data source).</span></span>  
  
 <span data-ttu-id="7c60f-105">In un progetto o un database di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] è possibile compilare più viste origine dati per una o più origini dati e costruire ognuna in modo da soddisfare i requisiti per una diversa soluzione.</span><span class="sxs-lookup"><span data-stu-id="7c60f-105">You can build multiple data source views in an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project or database on one or more data sources, and construct each one to satisfy the requirements for a different solution.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="7c60f-106">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="7c60f-106">Related Tasks</span></span>  
 [<span data-ttu-id="7c60f-107">Definizione di una vista origine dati &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="7c60f-107">Defining a Data Source View &#40;Analysis Services&#41;</span></span>](defining-a-data-source-view-analysis-services.md)  
  
 [<span data-ttu-id="7c60f-108">Aggiunta o rimozione di tabelle o viste in una vista origine dati &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="7c60f-108">Adding or Removing Tables or Views in a Data Source View &#40;Analysis Services&#41;</span></span>](adding-or-removing-tables-or-views-in-a-data-source-view-analysis-services.md)  
  
 [<span data-ttu-id="7c60f-109">Modificare le proprietà in una vista origine dati &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="7c60f-109">Change Properties in a Data Source View &#40;Analysis Services&#41;</span></span>](change-properties-in-a-data-source-view-analysis-services.md)  
  
 [<span data-ttu-id="7c60f-110">Definire relazioni logiche in una vista origine dati &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="7c60f-110">Define Logical Relationships in a Data Source View &#40;Analysis Services&#41;</span></span>](define-logical-relationships-in-a-data-source-view-analysis-services.md)  
  
 [<span data-ttu-id="7c60f-111">Definire chiavi primarie logiche in una vista origine dati &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="7c60f-111">Define Logical Primary Keys in a Data Source View &#40;Analysis Services&#41;</span></span>](define-logical-primary-keys-in-a-data-source-view-analysis-services.md)  
  
 [<span data-ttu-id="7c60f-112">Definire calcoli denominati in una vista origine dati &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="7c60f-112">Define Named Calculations in a Data Source View &#40;Analysis Services&#41;</span></span>](define-named-calculations-in-a-data-source-view-analysis-services.md)  
  
 [<span data-ttu-id="7c60f-113">Definire query denominate in una vista origine dati &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="7c60f-113">Define Named Queries in a Data Source View &#40;Analysis Services&#41;</span></span>](define-named-queries-in-a-data-source-view-analysis-services.md)  
  
 [<span data-ttu-id="7c60f-114">Sostituire una tabella o una query denominata in una vista origine dati &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="7c60f-114">Replace a Table or a Named Query in a Data Source View &#40;Analysis Services&#41;</span></span>](replace-a-table-or-a-named-query-in-a-data-source-view-analysis-services.md)  
  
 [<span data-ttu-id="7c60f-115">Utilizzare diagrammi in Progettazione vista origine dati &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="7c60f-115">Work with Diagrams in Data Source View Designer &#40;Analysis Services&#41;</span></span>](work-with-diagrams-in-data-source-view-designer-analysis-services.md)  
  
 [<span data-ttu-id="7c60f-116">Esplorare dati in una vista origine dati &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="7c60f-116">Explore Data in a Data Source View &#40;Analysis Services&#41;</span></span>](explore-data-in-a-data-source-view-analysis-services.md)  
  
 [<span data-ttu-id="7c60f-117">Eliminare una vista origine dati &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="7c60f-117">Delete a Data Source View &#40;Analysis Services&#41;</span></span>](delete-a-data-source-view-analysis-services.md)  
  
 [<span data-ttu-id="7c60f-118">Aggiornare lo schema in una vista origine dati &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="7c60f-118">Refresh the Schema in a Data Source View &#40;Analysis Services&#41;</span></span>](refresh-the-schema-in-a-data-source-view-analysis-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="7c60f-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7c60f-119">See Also</span></span>  
 <span data-ttu-id="7c60f-120">[Generazione guidata schema &#40;Analysis Services&#41;](schema-generation-wizard-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="7c60f-120">[Schema Generation Wizard &#40;Analysis Services&#41;](schema-generation-wizard-analysis-services.md) </span></span>  
 [<span data-ttu-id="7c60f-121">Origini dati supportate &#40;SSAS multidimensionale&#41;</span><span class="sxs-lookup"><span data-stu-id="7c60f-121">Data Sources Supported &#40;SSAS Multidimensional&#41;</span></span>](supported-data-sources-ssas-multidimensional.md)  
  
  
