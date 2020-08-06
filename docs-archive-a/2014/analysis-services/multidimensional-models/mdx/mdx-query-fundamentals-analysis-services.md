---
title: Nozioni fondamentali sulle query MDX (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- statements [MDX]
- Multidimensional Expressions [Analysis Services], statements
- Multidimensional Expressions [Analysis Services], queries
- MDX [Analysis Services], statements
- MDX queries [Analysis Services]
- MDX [Analysis Services], queries
- queries [MDX]
ms.assetid: a560383b-bb58-472e-95f5-65d03d8ea08b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 1a2a9a4f564bc33cc7a1b41a1a4c766c7a76a2cf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635825"
---
# <a name="mdx-query-fundamentals-analysis-services"></a><span data-ttu-id="f33d4-102">Nozioni fondamentali sulle query MDX (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="f33d4-102">MDX Query Fundamentals (Analysis Services)</span></span>
  <span data-ttu-id="f33d4-103">Nel linguaggio MDX (Multidimensional Expressions) è possibile eseguire query su oggetti multidimensionali, ad esempio un cubo, e restituire set di celle multidimensionali contenenti i dati del cubo.</span><span class="sxs-lookup"><span data-stu-id="f33d4-103">Multidimensional Expressions (MDX) lets you query multidimensional objects, such as cubes, and return multidimensional cellsets that contain the cube's data.</span></span> <span data-ttu-id="f33d4-104">In questo argomento e negli argomenti correlati viene fornita una panoramica delle query MDX.</span><span class="sxs-lookup"><span data-stu-id="f33d4-104">This topic and its subtopics provide an overview of MDX queries.</span></span>  
  
 <span data-ttu-id="f33d4-105">Negli argomenti seguenti vengono descritti le query MDX e i set di celle generati e sono disponibili informazioni più dettagliate sulla sintassi MDX di base.</span><span class="sxs-lookup"><span data-stu-id="f33d4-105">The following topics describe MDX queries and the cellsets they produce, and provide more detailed information about basic MDX syntax.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f33d4-106">Per ulteriori informazioni sui problemi di prestazioni relativi a query e calcoli MDX, vedere la sezione relativa alla scrittura di espressioni MDX efficienti nella [Guida alle prestazioni SQL Server 2005 Analysis Services](https://docsbay.net/Microsoft-SQL-Server-2005-Analysis-Services-Performance-Guide).</span><span class="sxs-lookup"><span data-stu-id="f33d4-106">For more information about performance issues related to MDX queries and calculations, see the section "Writing Efficient MDX" in the [SQL Server 2005 Analysis Services Performance Guide](https://docsbay.net/Microsoft-SQL-Server-2005-Analysis-Services-Performance-Guide).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f33d4-107">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="f33d4-107">In This Section</span></span>  
  
|<span data-ttu-id="f33d4-108">Argomento</span><span class="sxs-lookup"><span data-stu-id="f33d4-108">Topic</span></span>|<span data-ttu-id="f33d4-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f33d4-109">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="f33d4-110">Query MDX di base &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="f33d4-110">The Basic MDX Query &#40;MDX&#41;</span></span>](mdx-query-the-basic-query.md)|<span data-ttu-id="f33d4-111">Fornisce informazioni sulla sintassi di base dell'istruzione MDX SELECT.</span><span class="sxs-lookup"><span data-stu-id="f33d4-111">Provides basic syntax information for the MDX SELECT statement.</span></span>|  
|[<span data-ttu-id="f33d4-112">Restrizione della query con gli assi della query e di sezionamento &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="f33d4-112">Restricting the Query with Query and Slicer Axes &#40;MDX&#41;</span></span>](mdx-query-and-slicer-axes-restricting-the-query.md)|<span data-ttu-id="f33d4-113">Spiega cosa sono gli assi di query e filtro dei dati e come specificarli.</span><span class="sxs-lookup"><span data-stu-id="f33d4-113">Describes what query and slicer axes are and how to specify them.</span></span>|  
|[<span data-ttu-id="f33d4-114">Definizione del contesto di cubo in una query &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="f33d4-114">Establishing Cube Context in a Query &#40;MDX&#41;</span></span>](establishing-cube-context-in-a-query-mdx.md)|<span data-ttu-id="f33d4-115">Descrive lo scopo della clausola FROM nelle istruzioni MDX SELECT.</span><span class="sxs-lookup"><span data-stu-id="f33d4-115">Provides a description of the purpose of the FROM clause in an MDX SELECT statement.</span></span>|  
|[<span data-ttu-id="f33d4-116">Compilazione di set denominati in MDX &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="f33d4-116">Building Named Sets in MDX &#40;MDX&#41;</span></span>](mdx-named-sets-building-named-sets.md)|<span data-ttu-id="f33d4-117">Descrive lo scopo dei set denominati in MDX e le tecniche necessarie per crearli e utilizzarli nelle query MDX.</span><span class="sxs-lookup"><span data-stu-id="f33d4-117">Describes the purpose of named sets in MDX, and the techniques needed to create and use them in MDX queries.</span></span>|  
|[<span data-ttu-id="f33d4-118">Compilazione di membri calcolati in MDX &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="f33d4-118">Building Calculated Members in MDX &#40;MDX&#41;</span></span>](mdx-calculated-members-building-calculated-members.md)|<span data-ttu-id="f33d4-119">Fornisce informazioni sui membri calcolati in MDX, incluse le tecniche necessarie per crearli e utilizzarli nelle espressioni MDX.</span><span class="sxs-lookup"><span data-stu-id="f33d4-119">Provides information about calculated members in MDX, including the techniques needed to create and use them in MDX expressions.</span></span>|  
|[<span data-ttu-id="f33d4-120">Compilazione di formule per il calcolo di celle in MDX &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="f33d4-120">Building Cell Calculations in MDX &#40;MDX&#41;</span></span>](../../multidimensional-models-olap-logical-cube-objects/calculations.md)|<span data-ttu-id="f33d4-121">Descrive in dettaglio il processo di creazione e utilizzo delle celle calcolate.</span><span class="sxs-lookup"><span data-stu-id="f33d4-121">Details the process of creating and using calculated cells.</span></span>|  
|[<span data-ttu-id="f33d4-122">Creazione e utilizzo di valori di proprietà &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="f33d4-122">Creating and Using Property Values &#40;MDX&#41;</span></span>](../../creating-and-using-property-values-mdx.md)|<span data-ttu-id="f33d4-123">Descrive in dettaglio il processo di creazione e utilizzo delle proprietà di dimensioni, livelli, membri e celle.</span><span class="sxs-lookup"><span data-stu-id="f33d4-123">Details the process of creating and using dimension, level, member, and cell properties.</span></span>|  
|[<span data-ttu-id="f33d4-124">Manipolazione dei dati &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="f33d4-124">Manipulating Data &#40;MDX&#41;</span></span>](mdx-data-manipulation-manipulating-data.md)|<span data-ttu-id="f33d4-125">Illustra le nozioni fondamentali sulla manipolazione dei dati tramite drill-through e rollup, nonché l'ordine di calcolo e soluzione in MDX.</span><span class="sxs-lookup"><span data-stu-id="f33d4-125">Describes the basics behind manipulating data using drillthrough and rollup, and also describes pass order and solve order in MDX.</span></span>|  
|[<span data-ttu-id="f33d4-126">Modifica dei dati &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="f33d4-126">Modifying Data &#40;MDX&#41;</span></span>](mdx-data-modification-modifying-data.md)|<span data-ttu-id="f33d4-127">Descrive la procedura per l'utilizzo della funzionalità di writeback per modificare in modo temporaneo o permanente dati multidimensionali.</span><span class="sxs-lookup"><span data-stu-id="f33d4-127">Describes how to use writebacks to temporarily or permanently change multidimensional data.</span></span>|  
|[<span data-ttu-id="f33d4-128">Utilizzo di variabili e parametri &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="f33d4-128">Using Variables and Parameters &#40;MDX&#41;</span></span>](using-variables-and-parameters-mdx.md)|<span data-ttu-id="f33d4-129">Descrive come utilizzare le variabili e i parametri nelle query MDX.</span><span class="sxs-lookup"><span data-stu-id="f33d4-129">Describes how to use variables and parameters within MDX queries.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f33d4-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f33d4-130">See Also</span></span>  
 [<span data-ttu-id="f33d4-131">Guida di riferimento a MDX &#40;Multidimensional Expressions&#41;</span><span class="sxs-lookup"><span data-stu-id="f33d4-131">Multidimensional Expressions &#40;MDX&#41; Reference</span></span>](/sql/mdx/multidimensional-expressions-mdx-reference)  
  
  
