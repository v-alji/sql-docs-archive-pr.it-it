---
title: Oggetti Cube (Analysis Services-Dati multidimensionali) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- cubes [Analysis Services], objects
ms.assetid: 5cee362e-3f95-4467-bc6c-29b1518ecbf3
author: minewiskan
ms.author: owend
ms.openlocfilehash: 0e6dfb75be696ab26893e668b99dc36c7340f86c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629647"
---
# <a name="cube-objects-analysis-services---multidimensional-data"></a><span data-ttu-id="9b85d-102">Oggetti cubo (Analysis Services - Dati multidimensionali)</span><span class="sxs-lookup"><span data-stu-id="9b85d-102">Cube Objects (Analysis Services - Multidimensional Data)</span></span>
    
## <a name="introducing-cube-objects"></a><span data-ttu-id="9b85d-103">Introduzione agli oggetti cubo</span><span class="sxs-lookup"><span data-stu-id="9b85d-103">Introducing Cube Objects</span></span>  
 <span data-ttu-id="9b85d-104">Un oggetto <xref:Microsoft.AnalysisServices.Cube> semplice è composto da informazioni di base, dimensioni e gruppi di misure.</span><span class="sxs-lookup"><span data-stu-id="9b85d-104">A simple <xref:Microsoft.AnalysisServices.Cube> object is composed of: basic information, dimensions, and measure groups.</span></span> <span data-ttu-id="9b85d-105">Le informazioni di base includono il nome e la misura predefinita del cubo, l'origine dati, la modalità di archiviazione e altro.</span><span class="sxs-lookup"><span data-stu-id="9b85d-105">Basic information includes the name of the cube, the default measure of the cube, the data source, the storage mode, and others.</span></span>  
  
 <span data-ttu-id="9b85d-106">La raccolta Dimensions contiene il set effettivo di dimensioni utilizzate nel cubo dalla raccolta di dimensioni del database.</span><span class="sxs-lookup"><span data-stu-id="9b85d-106">The Dimensions collection contains the actual set of dimensions used in the cube from the database dimensions colection.</span></span> <span data-ttu-id="9b85d-107">È necessario definire tutte le dimensioni nella raccolta di dimensioni del database prima di potervi fare riferimento nel cubo.</span><span class="sxs-lookup"><span data-stu-id="9b85d-107">All dimensions have to be defined in the dimensions collection of the database before being referenced in the cube.</span></span> <span data-ttu-id="9b85d-108">Le dimensioni private non sono disponibili in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9b85d-108">Private dimensions are not available in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="9b85d-109">I gruppi di misure sono set di misure nel cubo.</span><span class="sxs-lookup"><span data-stu-id="9b85d-109">Measure groups are sets of measures in the cube.</span></span> <span data-ttu-id="9b85d-110">Un gruppo di misure è una raccolta di misure con una vista origine dati comune e un set di dimensioni comune.</span><span class="sxs-lookup"><span data-stu-id="9b85d-110">A measure group is a collection of measures that have a common data source view and a common set of dimensions.</span></span> <span data-ttu-id="9b85d-111">Un gruppo di misure è l'unità di elaborazione delle misure. I gruppi di misure possono essere elaborati singolarmente, per poi essere visualizzati.</span><span class="sxs-lookup"><span data-stu-id="9b85d-111">A measure group is the unit of process for measures; measure groups can be processed individually and then browsed.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9b85d-112">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="9b85d-112">In this section</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9b85d-113">Argomento</span><span class="sxs-lookup"><span data-stu-id="9b85d-113">Topic</span></span>||  
|[<span data-ttu-id="9b85d-114">Azioni &#40;Analysis Services - Dati multidimensionali&#41;</span><span class="sxs-lookup"><span data-stu-id="9b85d-114">Actions &#40;Analysis Services - Multidimensional Data&#41;</span></span>](../multidimensional-models/actions-analysis-services-multidimensional-data.md)||  
|[<span data-ttu-id="9b85d-115">Aggregations and Aggregation Designs</span><span class="sxs-lookup"><span data-stu-id="9b85d-115">Aggregations and Aggregation Designs</span></span>](aggregations-and-aggregation-designs.md)||  
|[<span data-ttu-id="9b85d-116">Calcoli</span><span class="sxs-lookup"><span data-stu-id="9b85d-116">Calculations</span></span>](calculations.md)||  
|[<span data-ttu-id="9b85d-117">Celle del cubo &#40;Analysis Services Dati multidimensionali&#41;</span><span class="sxs-lookup"><span data-stu-id="9b85d-117">Cube Cells &#40;Analysis Services - Multidimensional Data&#41;</span></span>](cube-cells-analysis-services-multidimensional-data.md)||  
|[<span data-ttu-id="9b85d-118">Proprietà dei cubi</span><span class="sxs-lookup"><span data-stu-id="9b85d-118">Cube Properties</span></span>](cube-properties-multidimensional-model-programming.md)||  
|[<span data-ttu-id="9b85d-119">Archiviazione di cubi &#40;Analysis Services-Dati multidimensionali&#41;</span><span class="sxs-lookup"><span data-stu-id="9b85d-119">Cube Storage &#40;Analysis Services - Multidimensional Data&#41;</span></span>](cube-storage-analysis-services-multidimensional-data.md)||  
|[<span data-ttu-id="9b85d-120">Traduzioni di cubi</span><span class="sxs-lookup"><span data-stu-id="9b85d-120">Cube Translations</span></span>](cube-translations.md)||  
|[<span data-ttu-id="9b85d-121">Relazioni tra dimensioni</span><span class="sxs-lookup"><span data-stu-id="9b85d-121">Dimension Relationships</span></span>](dimension-relationships.md)||  
|[<span data-ttu-id="9b85d-122">Indicatori KPI nei modelli multidimensionali</span><span class="sxs-lookup"><span data-stu-id="9b85d-122">Key Performance Indicators &#40;KPIs&#41; in Multidimensional Models</span></span>](../multidimensional-models/key-performance-indicators-kpis-in-multidimensional-models.md)||  
|[<span data-ttu-id="9b85d-123">Misure e gruppi di misure</span><span class="sxs-lookup"><span data-stu-id="9b85d-123">Measures and Measure Groups</span></span>](../multidimensional-models/measures-and-measure-groups.md)||  
|[<span data-ttu-id="9b85d-124">Partizioni &#40;Analysis Services - Dati multidimensionali&#41;</span><span class="sxs-lookup"><span data-stu-id="9b85d-124">Partitions &#40;Analysis Services - Multidimensional Data&#41;</span></span>](partitions-analysis-services-multidimensional-data.md)||  
|[<span data-ttu-id="9b85d-125">Prospettive</span><span class="sxs-lookup"><span data-stu-id="9b85d-125">Perspectives</span></span>](perspectives.md)||  
  
  
