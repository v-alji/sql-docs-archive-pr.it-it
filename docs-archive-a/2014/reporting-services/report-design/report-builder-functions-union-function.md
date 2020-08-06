---
title: Funzione Union (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: c87e16fe-c12a-4c9d-a9df-7a94e229fd04
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c80926be53254ec512b2189c4b67e8cd5885733f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628396"
---
# <a name="union-function-report-builder-and-ssrs"></a><span data-ttu-id="91da9-102">Funzione Union (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="91da9-102">Union Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="91da9-103">Viene restituita l'unione di tutti i valori numerici non Null specificati dall'espressione, valutata nell'ambito specificato.</span><span class="sxs-lookup"><span data-stu-id="91da9-103">Returns the union of all the non-null numeric values specified by the expression, evaluated in the given scope.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="91da9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="91da9-104">Syntax</span></span>  
  
```  
  
Union(expression, scope, recursive)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="91da9-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="91da9-105">Parameters</span></span>  
 <span data-ttu-id="91da9-106">*expression*</span><span class="sxs-lookup"><span data-stu-id="91da9-106">*expression*</span></span>  
 <span data-ttu-id="91da9-107">(`SqlGeometry` o `SqlGeography`) Espressione su cui eseguire l'aggregazione.</span><span class="sxs-lookup"><span data-stu-id="91da9-107">(`SqlGeometry` or `SqlGeography`) The expression on which to perform the aggregation.</span></span>  
  
 <span data-ttu-id="91da9-108">*ambito*</span><span class="sxs-lookup"><span data-stu-id="91da9-108">*scope*</span></span>  
 <span data-ttu-id="91da9-109">(`String`) Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="91da9-109">(`String`) Optional.</span></span> <span data-ttu-id="91da9-110">Nome di un set di dati, gruppo o area dati che contiene gli elementi del report a cui applicare la funzione di aggregazione.</span><span class="sxs-lookup"><span data-stu-id="91da9-110">The name of a dataset, group, or data region that contains the report items to which to apply the aggregate function.</span></span> <span data-ttu-id="91da9-111">Se si omette *scope* , viene usato l'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="91da9-111">If *scope* is not specified, the current scope is used.</span></span>  
  
 <span data-ttu-id="91da9-112">*ricorsivi*</span><span class="sxs-lookup"><span data-stu-id="91da9-112">*recursive*</span></span>  
 <span data-ttu-id="91da9-113">(**Enumerated Type**) Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="91da9-113">(**Enumerated Type**) Optional.</span></span> <span data-ttu-id="91da9-114">`Simple` (valore predefinito) o `RdlRecursive`.</span><span class="sxs-lookup"><span data-stu-id="91da9-114">`Simple` (default) or `RdlRecursive`.</span></span> <span data-ttu-id="91da9-115">Specifica se eseguire l'aggregazione in modo ricorsivo.</span><span class="sxs-lookup"><span data-stu-id="91da9-115">Specifies whether to perform the aggregation recursively.</span></span>  
  
## <a name="return"></a><span data-ttu-id="91da9-116">Return</span><span class="sxs-lookup"><span data-stu-id="91da9-116">Return</span></span>  
 <span data-ttu-id="91da9-117">Restituisce un oggetto spaziale, `SqlGeometry` o `SqlGeography`, in base al tipo di espressione.</span><span class="sxs-lookup"><span data-stu-id="91da9-117">Returns a spatial object, either `SqlGeometry` or `SqlGeography`, based on the expression type.</span></span> <span data-ttu-id="91da9-118">Per ulteriori informazioni sui `SqlGeometry` `SqlGeography` tipi di dati spaziali e, vedere [Cenni preliminari sui tipi di dati spaziali](../../relational-databases/spatial/spatial-data-types-overview.md).</span><span class="sxs-lookup"><span data-stu-id="91da9-118">For more information about `SqlGeometry` and `SqlGeography` spatial data types, see [Spatial Data Types Overview](../../relational-databases/spatial/spatial-data-types-overview.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="91da9-119">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="91da9-119">Remarks</span></span>  
 <span data-ttu-id="91da9-120">Il set di dati specificato nell'espressione deve essere dello stesso tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="91da9-120">The set of data specified in the expression must have the same data type.</span></span>  
  
 <span data-ttu-id="91da9-121">Il valore di *scope* deve essere una costante di tipo stringa e non può essere un'espressione.</span><span class="sxs-lookup"><span data-stu-id="91da9-121">The value of *scope* must be a string constant and cannot be an expression.</span></span> <span data-ttu-id="91da9-122">Per aggregazioni o aggregazioni esterne che non specificano altre aggregazioni, *scope* deve fare riferimento all'ambito corrente o a un ambito contenitore.</span><span class="sxs-lookup"><span data-stu-id="91da9-122">For outer aggregates or aggregates that do not specify other aggregates, *scope* must refer to the current scope or a containing scope.</span></span> <span data-ttu-id="91da9-123">Gli ambiti del set di dati non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="91da9-123">Dataset scopes are not supported.</span></span> <span data-ttu-id="91da9-124">Per le aggregazioni di aggregazioni, le aggregazioni nidificate possono specificare un ambito figlio.</span><span class="sxs-lookup"><span data-stu-id="91da9-124">For aggregates of aggregates, nested aggregates can specify a child scope.</span></span>  
  
 <span data-ttu-id="91da9-125">*Expression* può contenere chiamate alle funzioni di aggregazione nidificate con le eccezioni e le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="91da9-125">*Expression* can contain calls to nested aggregate functions with the following exceptions and conditions:</span></span>  
  
-   <span data-ttu-id="91da9-126">*Scope* per le aggregazioni nidificate deve corrispondere o essere contenuto nell'ambito dell'aggregazione esterna.</span><span class="sxs-lookup"><span data-stu-id="91da9-126">*Scope* for nested aggregates must be the same as, or contained by, the scope of the outer aggregate.</span></span> <span data-ttu-id="91da9-127">Per tutti gli ambiti distinti nell'espressione, un ambito deve essere in una relazione figlio con tutti gli altri ambiti.</span><span class="sxs-lookup"><span data-stu-id="91da9-127">For all distinct scopes in the expression, one scope must be in a child relationship to all other scopes.</span></span>  
  
-   <span data-ttu-id="91da9-128">*Scope* per le aggregazioni nidificate non può essere il nome di un set di dati.</span><span class="sxs-lookup"><span data-stu-id="91da9-128">*Scope* for nested aggregates cannot be the name of a dataset.</span></span>  
  
-   <span data-ttu-id="91da9-129">L' *espressione* non deve contenere `First` funzioni,, `Last` `Previous` o `RunningValue` .</span><span class="sxs-lookup"><span data-stu-id="91da9-129">*Expression* must not contain `First`, `Last`, `Previous`, or `RunningValue` functions.</span></span>  
  
-   <span data-ttu-id="91da9-130">*Expression* non deve contenere aggregazioni nidificate che specificano *recursive*.</span><span class="sxs-lookup"><span data-stu-id="91da9-130">*Expression* must not contain nested aggregates that specify *recursive*.</span></span>  
  
 <span data-ttu-id="91da9-131">Per altre informazioni, vedere [Riferimento a funzioni di aggregazione &#40;Generatore report e SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) e [Ambito di espressioni per totali, aggregazioni e raccolte predefinite &#40;Generatore report e SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="91da9-131">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) and [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
 <span data-ttu-id="91da9-132">Per altre informazioni sulle aggregazioni ricorsive, vedere [Creazione di gruppi di gerarchie ricorsive &#40;Generatore report e SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="91da9-132">For more information about recursive aggregates, see [Creating Recursive Hierarchy Groups &#40;Report Builder and SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="91da9-133">Esempio</span><span class="sxs-lookup"><span data-stu-id="91da9-133">Example</span></span>  
 <span data-ttu-id="91da9-134">Nella tabella seguente vengono illustrati esempi di espressioni `SqlGeometry` ed espressione di risultato `Union`, visualizzati in formato WKT (Well Known Text) per i dati spaziali.</span><span class="sxs-lookup"><span data-stu-id="91da9-134">The following table shows examples of `SqlGeometry` expressions and `Union` result expression, shown in WKT (Well Known Text) format for spatial data.</span></span>  
  
|<span data-ttu-id="91da9-135">Campo con dati spaziali</span><span class="sxs-lookup"><span data-stu-id="91da9-135">Field with spatial data</span></span>|<span data-ttu-id="91da9-136">Esempio</span><span class="sxs-lookup"><span data-stu-id="91da9-136">Example</span></span>|<span data-ttu-id="91da9-137">Risultato Union</span><span class="sxs-lookup"><span data-stu-id="91da9-137">Union result</span></span>|  
|-----------------------------|-------------|------------------|  
|<span data-ttu-id="91da9-138">[PointLocation]</span><span class="sxs-lookup"><span data-stu-id="91da9-138">[PointLocation]</span></span>|<span data-ttu-id="91da9-139">POINT(1 2)</span><span class="sxs-lookup"><span data-stu-id="91da9-139">POINT(1 2)</span></span><br /><br /> <span data-ttu-id="91da9-140">POINT(3 4)</span><span class="sxs-lookup"><span data-stu-id="91da9-140">POINT(3 4)</span></span>|<span data-ttu-id="91da9-141">MULTIPOINT((1 2), (3 4))</span><span class="sxs-lookup"><span data-stu-id="91da9-141">MULTIPOINT((1 2), (3 4))</span></span>|  
|<span data-ttu-id="91da9-142">[PathDefinition]</span><span class="sxs-lookup"><span data-stu-id="91da9-142">[PathDefinition]</span></span>|<span data-ttu-id="91da9-143">LINESTRING(1 2, 3 4)</span><span class="sxs-lookup"><span data-stu-id="91da9-143">LINESTRING(1 2, 3 4)</span></span><br /><br /> <span data-ttu-id="91da9-144">LINESTRING(5 6, 7 8)</span><span class="sxs-lookup"><span data-stu-id="91da9-144">LINESTRING(5 6, 7 8)</span></span>|<span data-ttu-id="91da9-145">MULTILINESTRING((7 8, 5 6), (3 4, 1 2))</span><span class="sxs-lookup"><span data-stu-id="91da9-145">MULTILINESTRING((7 8, 5 6), (3 4, 1 2))</span></span>|  
|<span data-ttu-id="91da9-146">[PolygonDefinition]</span><span class="sxs-lookup"><span data-stu-id="91da9-146">[PolygonDefinition]</span></span>|<span data-ttu-id="91da9-147">POLYGON((1 2, 3 4, 5 2, 1 2))</span><span class="sxs-lookup"><span data-stu-id="91da9-147">POLYGON((1 2, 3 4, 5 2, 1 2))</span></span><br /><br /> <span data-ttu-id="91da9-148">POLYGON((-1 2, -3 4, -5 2, -1 2))</span><span class="sxs-lookup"><span data-stu-id="91da9-148">POLYGON((-1 2, -3 4, -5 2, -1 2))</span></span>|<span data-ttu-id="91da9-149">MULTIPOLYGON(((1 2, 5 2, 3 4, 1 2)), ((-5 2, -1 2, -3 4, -5 2)))</span><span class="sxs-lookup"><span data-stu-id="91da9-149">MULTIPOLYGON(((1 2, 5 2, 3 4, 1 2)), ((-5 2, -1 2, -3 4, -5 2)))</span></span>|  
  
```  
=Union(Fields!PointLocation.Value)  
=Union(Fields!PathDefinition.Value)  
=Union(Fields!PolygonDefinition.Value, "Group1")  
```  
  
## <a name="see-also"></a><span data-ttu-id="91da9-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="91da9-150">See Also</span></span>  
 <span data-ttu-id="91da9-151">[Utilizzo delle espressioni nei report &#40;Generatore report e SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="91da9-151">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="91da9-152">[Esempi di espressioni &#40;Generatore report e SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="91da9-152">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="91da9-153">[Tipi di dati nelle espressioni &#40;Generatore report e SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="91da9-153">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="91da9-154">Ambito di espressioni per totali, aggregazioni e raccolte predefinite &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="91da9-154">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
