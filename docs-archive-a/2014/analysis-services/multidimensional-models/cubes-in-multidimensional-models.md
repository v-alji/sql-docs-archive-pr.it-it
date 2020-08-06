---
title: Cubi nei modelli multidimensionali | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- OLAP objects [Analysis Services], cubes
- cubes [Analysis Services], about cubes
- cubes [Analysis Services]
- OLAP [Analysis Services], cubes
ms.assetid: e0f7acf3-4b07-41fc-a5fc-ac30b4a56c54
author: minewiskan
ms.author: owend
ms.openlocfilehash: 372bb8075b232ff8fbf8a54facf9bc065e6763a3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725099"
---
# <a name="cubes-in-multidimensional-models"></a><span data-ttu-id="a3a6a-102">Cubi nei modelli multidimensionali</span><span class="sxs-lookup"><span data-stu-id="a3a6a-102">Cubes in Multidimensional Models</span></span>
  <span data-ttu-id="a3a6a-103">Un cubo è una struttura multidimensionale che contiene informazioni per scopi analitici. Un cubo è principalmente costituito da dimensioni e misure.</span><span class="sxs-lookup"><span data-stu-id="a3a6a-103">A cube is a multidimensional structure that contains information for analytical purposes; the main constituents of a cube are dimensions and measures.</span></span> <span data-ttu-id="a3a6a-104">Le dimensioni definiscono la struttura del cubo utilizzata per effettuare delle sezioni, mentre le misure forniscono valori numerici aggregati di interesse per l'utente finale.</span><span class="sxs-lookup"><span data-stu-id="a3a6a-104">Dimensions define the structure of the cube that you use to slice and dice over, and measures provide aggregated numerical values of interest to the end user.</span></span> <span data-ttu-id="a3a6a-105">Come struttura logica, un cubo consente a un'applicazione client di recuperare i valori delle misure, come se si trovassero nelle celle del cubo. Le celle vengono definite per ogni possibile valore riepilogato.</span><span class="sxs-lookup"><span data-stu-id="a3a6a-105">As a logical structure, a cube allows a client application to retrieve values, of measures, as if they were contained in cells in the cube; cells are defined for every possible summarized value.</span></span> <span data-ttu-id="a3a6a-106">Una cella del cubo è definita dall'intersezione dei membri della dimensione e contiene i valori aggregati delle misure a quell'intersezione specifica.</span><span class="sxs-lookup"><span data-stu-id="a3a6a-106">A cell, in the cube, is defined by the intersection of dimension members and contains the aggregated values of the measures at that specific intersection.</span></span>  
  
## <a name="benefits-of-using-cubes"></a><span data-ttu-id="a3a6a-107">Vantaggi derivanti dall'utilizzo dei cubi</span><span class="sxs-lookup"><span data-stu-id="a3a6a-107">Benefits of Using Cubes</span></span>  
 <span data-ttu-id="a3a6a-108">Un cubo rappresenta un contenitore in cui vengono archiviati tutti i dati correlati a scopo di analisi.</span><span class="sxs-lookup"><span data-stu-id="a3a6a-108">A cube provides a single place where all related data, for analysis, is stored.</span></span>  
  
## <a name="components-of-cubes"></a><span data-ttu-id="a3a6a-109">Componenti dei cubi</span><span class="sxs-lookup"><span data-stu-id="a3a6a-109">Components of Cubes</span></span>  
 <span data-ttu-id="a3a6a-110">Un cubo è composto dagli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="a3a6a-110">A cube is composed of:</span></span>  
  
|<span data-ttu-id="a3a6a-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="a3a6a-111">Element</span></span>|<span data-ttu-id="a3a6a-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a3a6a-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a3a6a-113">Dimensioni</span><span class="sxs-lookup"><span data-stu-id="a3a6a-113">Dimensions</span></span>|[<span data-ttu-id="a3a6a-114">Dimensioni nei modelli multidimensionali</span><span class="sxs-lookup"><span data-stu-id="a3a6a-114">Dimensions in Multidimensional Models</span></span>](dimensions-in-multidimensional-models.md)|  
|<span data-ttu-id="a3a6a-115">Misure e gruppi di misure</span><span class="sxs-lookup"><span data-stu-id="a3a6a-115">Measures and Measure Groups</span></span>|[<span data-ttu-id="a3a6a-116">Creare misure e gruppi di misure nei modelli multidimensionali</span><span class="sxs-lookup"><span data-stu-id="a3a6a-116">Create Measures and Measure Groups in Multidimensional Models</span></span>](create-measures-and-measure-groups-in-multidimensional-models.md)|  
|<span data-ttu-id="a3a6a-117">Partizioni</span><span class="sxs-lookup"><span data-stu-id="a3a6a-117">Partitions</span></span>|[<span data-ttu-id="a3a6a-118">Partizioni nei modelli multidimensionali</span><span class="sxs-lookup"><span data-stu-id="a3a6a-118">Partitions in Multidimensional Models</span></span>](partitions-in-multidimensional-models.md)|  
|<span data-ttu-id="a3a6a-119">Prospettive</span><span class="sxs-lookup"><span data-stu-id="a3a6a-119">Perspectives</span></span>|[<span data-ttu-id="a3a6a-120">Prospettive nei modelli multidimensionali</span><span class="sxs-lookup"><span data-stu-id="a3a6a-120">Perspectives in Multidimensional Models</span></span>](perspectives-in-multidimensional-models.md)|  
|<span data-ttu-id="a3a6a-121">Gerarchie</span><span class="sxs-lookup"><span data-stu-id="a3a6a-121">Hierarchies</span></span>|[<span data-ttu-id="a3a6a-122">Creare gerarchie definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="a3a6a-122">Create User-Defined Hierarchies</span></span>](user-defined-hierarchies-create.md)|  
|<span data-ttu-id="a3a6a-123">Azioni</span><span class="sxs-lookup"><span data-stu-id="a3a6a-123">Actions</span></span>|[<span data-ttu-id="a3a6a-124">Azioni nei modelli multidimensionali</span><span class="sxs-lookup"><span data-stu-id="a3a6a-124">Actions in Multidimensional Models</span></span>](actions-in-multidimensional-models.md)|  
|<span data-ttu-id="a3a6a-125">Indicatori KPI</span><span class="sxs-lookup"><span data-stu-id="a3a6a-125">Key Performance Indicators (KPI)</span></span>|[<span data-ttu-id="a3a6a-126">Indicatori KPI nei modelli multidimensionali</span><span class="sxs-lookup"><span data-stu-id="a3a6a-126">Key Performance Indicators &#40;KPIs&#41; in Multidimensional Models</span></span>](key-performance-indicators-kpis-in-multidimensional-models.md)|  
|<span data-ttu-id="a3a6a-127">Calcoli</span><span class="sxs-lookup"><span data-stu-id="a3a6a-127">Calculations</span></span>|[<span data-ttu-id="a3a6a-128">Calcoli nei modelli multidimensionali</span><span class="sxs-lookup"><span data-stu-id="a3a6a-128">Calculations in Multidimensional Models</span></span>](calculations-in-multidimensional-models.md)|  
|<span data-ttu-id="a3a6a-129">Traduzioni</span><span class="sxs-lookup"><span data-stu-id="a3a6a-129">Translations</span></span>|[<span data-ttu-id="a3a6a-130">Traduzioni nei modelli multidimensionali</span><span class="sxs-lookup"><span data-stu-id="a3a6a-130">Translations in Multidimensional Models</span></span>](translations-in-multidimensional-models-analysis-services.md)|  
  
## <a name="related-tasks"></a><span data-ttu-id="a3a6a-131">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="a3a6a-131">Related Tasks</span></span>  
  
|<span data-ttu-id="a3a6a-132">Argomento</span><span class="sxs-lookup"><span data-stu-id="a3a6a-132">Topic</span></span>|<span data-ttu-id="a3a6a-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a3a6a-133">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="a3a6a-134">Creare un cubo mediante la Creazione guidata cubo</span><span class="sxs-lookup"><span data-stu-id="a3a6a-134">Create a Cube Using the Cube Wizard</span></span>](create-a-cube-using-the-cube-wizard.md)|<span data-ttu-id="a3a6a-135">Viene illustrato come utilizzare la Creazione guidata cubo per definire un cubo, le dimensioni, gli attributi delle dimensioni e le gerarchie definite dall'utente.</span><span class="sxs-lookup"><span data-stu-id="a3a6a-135">Describes how to use the Cube Wizard to define a cube, dimensions, dimension attributes, and user-defined hierarchies.</span></span>|  
|[<span data-ttu-id="a3a6a-136">Creare misure e gruppi di misure nei modelli multidimensionali</span><span class="sxs-lookup"><span data-stu-id="a3a6a-136">Create Measures and Measure Groups in Multidimensional Models</span></span>](create-measures-and-measure-groups-in-multidimensional-models.md)|<span data-ttu-id="a3a6a-137">Descrive come definire i gruppi di misure.</span><span class="sxs-lookup"><span data-stu-id="a3a6a-137">Describes how to define measure groups.</span></span>|  
|[<span data-ttu-id="a3a6a-138">Calcoli nei modelli multidimensionali</span><span class="sxs-lookup"><span data-stu-id="a3a6a-138">Calculations in Multidimensional Models</span></span>](calculations-in-multidimensional-models.md)|<span data-ttu-id="a3a6a-139">Descrive come definire e configurare un calcolo in uno script MDX.</span><span class="sxs-lookup"><span data-stu-id="a3a6a-139">Describes how to define and configure a calculation in an MDX script.</span></span>|  
|[<span data-ttu-id="a3a6a-140">Azioni nei modelli multidimensionali</span><span class="sxs-lookup"><span data-stu-id="a3a6a-140">Actions in Multidimensional Models</span></span>](actions-in-multidimensional-models.md)|<span data-ttu-id="a3a6a-141">Descrive come definire e configurare un'azione.</span><span class="sxs-lookup"><span data-stu-id="a3a6a-141">Describes how to define and configure an action.</span></span>|  
|[<span data-ttu-id="a3a6a-142">Prospettive nei modelli multidimensionali</span><span class="sxs-lookup"><span data-stu-id="a3a6a-142">Perspectives in Multidimensional Models</span></span>](perspectives-in-multidimensional-models.md)|<span data-ttu-id="a3a6a-143">Descrive come definire e configurare una prospettiva.</span><span class="sxs-lookup"><span data-stu-id="a3a6a-143">Describes how to define and configure a perspective.</span></span>|  
|[<span data-ttu-id="a3a6a-144">Definizione di stored procedure</span><span class="sxs-lookup"><span data-stu-id="a3a6a-144">Defining Stored Procedures</span></span>](../multidimensional-models-extending-olap-stored-procedures/defining-stored-procedures.md)|<span data-ttu-id="a3a6a-145">Descrive come utilizzare le stored procedure.</span><span class="sxs-lookup"><span data-stu-id="a3a6a-145">Describes how to work with stored procedures.</span></span>|  
  
  
