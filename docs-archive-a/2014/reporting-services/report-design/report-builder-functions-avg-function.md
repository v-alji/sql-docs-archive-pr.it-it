---
title: Funzione Avg (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: f1276c4c-bb44-44c0-a1bf-386a0c340003
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: cfa9d3517e3b3b0c2e4e01853ffa30295ec343df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721125"
---
# <a name="avg-function-report-builder-and-ssrs"></a><span data-ttu-id="4cf03-102">Funzione Avg (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="4cf03-102">Avg Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="4cf03-103">Restituisce la media di tutti i valori numerici non Null specificati dall'espressione, valutata nell'ambito specificato.</span><span class="sxs-lookup"><span data-stu-id="4cf03-103">Returns the average of all non-null numeric values specified by the expression, evaluated in the given scope.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="4cf03-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4cf03-104">Syntax</span></span>  
  
```  
  
Avg(expression, scope, recursive)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4cf03-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4cf03-105">Parameters</span></span>  
 <span data-ttu-id="4cf03-106">*expression*</span><span class="sxs-lookup"><span data-stu-id="4cf03-106">*expression*</span></span>  
 <span data-ttu-id="4cf03-107">(`Float`) Espressione su cui eseguire l'aggregazione.</span><span class="sxs-lookup"><span data-stu-id="4cf03-107">(`Float`) The expression on which to perform the aggregation.</span></span>  
  
 <span data-ttu-id="4cf03-108">*ambito*</span><span class="sxs-lookup"><span data-stu-id="4cf03-108">*scope*</span></span>  
 <span data-ttu-id="4cf03-109">(`String`) Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="4cf03-109">(`String`) Optional.</span></span> <span data-ttu-id="4cf03-110">Nome di un set di dati, gruppo o area dati che contiene gli elementi del report a cui applicare la funzione di aggregazione.</span><span class="sxs-lookup"><span data-stu-id="4cf03-110">The name of a dataset, group, or data region that contains the report items to which to apply the aggregate function.</span></span> <span data-ttu-id="4cf03-111">Se si omette *scope* , viene usato l'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="4cf03-111">If *scope* is not specified, the current scope is used.</span></span>  
  
 <span data-ttu-id="4cf03-112">*ricorsivi*</span><span class="sxs-lookup"><span data-stu-id="4cf03-112">*recursive*</span></span>  
 <span data-ttu-id="4cf03-113">(**Enumerated Type**) Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="4cf03-113">(**Enumerated Type**) Optional.</span></span> <span data-ttu-id="4cf03-114">`Simple` (valore predefinito) o `RdlRecursive`.</span><span class="sxs-lookup"><span data-stu-id="4cf03-114">`Simple` (default) or `RdlRecursive`.</span></span> <span data-ttu-id="4cf03-115">Specifica se eseguire l'aggregazione in modo ricorsivo.</span><span class="sxs-lookup"><span data-stu-id="4cf03-115">Specifies whether to perform the aggregation recursively.</span></span>  
  
## <a name="return-type"></a><span data-ttu-id="4cf03-116">Tipo restituito</span><span class="sxs-lookup"><span data-stu-id="4cf03-116">Return Type</span></span>  
 <span data-ttu-id="4cf03-117">Restituisce un valore `Decimal` per le espressioni decimali e un valore `Double` per tutte le altre espressioni.</span><span class="sxs-lookup"><span data-stu-id="4cf03-117">Returns a `Decimal` for decimal expressions and a `Double` for all other expressions.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4cf03-118">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="4cf03-118">Remarks</span></span>  
 <span data-ttu-id="4cf03-119">Il set di dati specificato nell'espressione deve essere dello stesso tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="4cf03-119">The set of data specified in the expression must have the same data type.</span></span> <span data-ttu-id="4cf03-120">Per convertire dati con più tipi di dati numerici nello stesso tipo di dati, usare funzioni di conversione come `CInt`, `CDbl` o `CDec`.</span><span class="sxs-lookup"><span data-stu-id="4cf03-120">To convert data that has multiple numeric data types to the same data type, use conversion functions like `CInt`, `CDbl` or `CDec`.</span></span> <span data-ttu-id="4cf03-121">Per altre informazioni, vedere [Funzioni di conversione del tipo](https://go.microsoft.com/fwlink/?LinkId=96142).</span><span class="sxs-lookup"><span data-stu-id="4cf03-121">For more information, see [Type Conversion Functions](https://go.microsoft.com/fwlink/?LinkId=96142).</span></span>  
  
 <span data-ttu-id="4cf03-122">Il valore di *scope* deve essere una costante di tipo stringa e non può essere un'espressione.</span><span class="sxs-lookup"><span data-stu-id="4cf03-122">The value of *scope* must be a string constant and cannot be an expression.</span></span> <span data-ttu-id="4cf03-123">Per aggregazioni o aggregazioni esterne che non specificano altre aggregazioni, *scope* deve fare riferimento all'ambito corrente o a un ambito contenitore.</span><span class="sxs-lookup"><span data-stu-id="4cf03-123">For outer aggregates or aggregates that do not specify other aggregates, *scope* must refer to the current scope or a containing scope.</span></span> <span data-ttu-id="4cf03-124">Per le aggregazioni di aggregazioni, le aggregazioni nidificate possono specificare un ambito figlio.</span><span class="sxs-lookup"><span data-stu-id="4cf03-124">For aggregates of aggregates, nested aggregates can specify a child scope.</span></span>  
  
 <span data-ttu-id="4cf03-125">*Expression* può contenere chiamate alle funzioni di aggregazione nidificate con le eccezioni e le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4cf03-125">*Expression* can contain calls to nested aggregate functions with the following exceptions and conditions:</span></span>  
  
-   <span data-ttu-id="4cf03-126">*Scope* per le aggregazioni nidificate deve corrispondere o essere contenuto nell'ambito dell'aggregazione esterna.</span><span class="sxs-lookup"><span data-stu-id="4cf03-126">*Scope* for nested aggregates must be the same as, or contained by, the scope of the outer aggregate.</span></span> <span data-ttu-id="4cf03-127">Per tutti gli ambiti distinti nell'espressione, un ambito deve essere in una relazione figlio con tutti gli altri ambiti.</span><span class="sxs-lookup"><span data-stu-id="4cf03-127">For all distinct scopes in the expression, one scope must be in a child relationship to all other scopes.</span></span>  
  
-   <span data-ttu-id="4cf03-128">*Scope* per le aggregazioni nidificate non può essere il nome di un set di dati.</span><span class="sxs-lookup"><span data-stu-id="4cf03-128">*Scope* for nested aggregates cannot be the name of a dataset.</span></span>  
  
-   <span data-ttu-id="4cf03-129">L' *espressione* non deve contenere `First` funzioni,, `Last` `Previous` o `RunningValue` .</span><span class="sxs-lookup"><span data-stu-id="4cf03-129">*Expression* must not contain `First`, `Last`, `Previous`, or `RunningValue` functions.</span></span>  
  
-   <span data-ttu-id="4cf03-130">*Expression* non deve contenere aggregazioni nidificate che specificano *recursive*.</span><span class="sxs-lookup"><span data-stu-id="4cf03-130">*Expression* must not contain nested aggregates that specify *recursive*.</span></span>  
  
 <span data-ttu-id="4cf03-131">Per altre informazioni, vedere [Riferimento a funzioni di aggregazione &#40;Generatore report e SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) e [Ambito di espressioni per totali, aggregazioni e raccolte predefinite &#40;Generatore report e SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="4cf03-131">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) and [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
 <span data-ttu-id="4cf03-132">Per altre informazioni sulle aggregazioni ricorsive, vedere [Creazione di gruppi di gerarchie ricorsive &#40;Generatore report e SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="4cf03-132">For more information about recursive aggregates, see [Creating Recursive Hierarchy Groups &#40;Report Builder and SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4cf03-133">Esempio</span><span class="sxs-lookup"><span data-stu-id="4cf03-133">Example</span></span>  
 <span data-ttu-id="4cf03-134">I due esempi di codice seguenti consentono di ottenere una media di tutti i valori del campo `Cost` contenuto in un set di dati denominato `Inventory`.</span><span class="sxs-lookup"><span data-stu-id="4cf03-134">The following two code examples provide an average of all values in the `Cost` field contained in a dataset named `Inventory`.</span></span>  
  
```  
=Avg(Fields!Cost.Value, "Inventory")   
  OR    
=Avg (CDbl(Fields!Cost.Value), "Inventory")  
```  
  
## <a name="see-also"></a><span data-ttu-id="4cf03-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4cf03-135">See Also</span></span>  
 <span data-ttu-id="4cf03-136">[Utilizzo delle espressioni nei report &#40;Generatore report e SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="4cf03-136">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="4cf03-137">[Esempi di espressioni &#40;Generatore report e SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="4cf03-137">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="4cf03-138">[Tipi di dati nelle espressioni &#40;Generatore report e SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="4cf03-138">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="4cf03-139">Ambito di espressioni per totali, aggregazioni e raccolte predefinite &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="4cf03-139">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
