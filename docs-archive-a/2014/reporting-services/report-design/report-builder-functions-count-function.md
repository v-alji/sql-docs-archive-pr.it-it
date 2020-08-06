---
title: Funzione Count (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 7b50b101-daf8-4fb0-ae04-57384755779f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3617e64d804b6b0f3d9522b5a089f418a942568a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636559"
---
# <a name="count-function-report-builder-and-ssrs"></a><span data-ttu-id="947a5-102">Funzione Count (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="947a5-102">Count Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="947a5-103">Restituisce il conteggio dei valori non Null specificati dall'espressione, valutato nel contesto dell'ambito specificato.</span><span class="sxs-lookup"><span data-stu-id="947a5-103">Returns a count of non-null values specified by the expression, evaluated in the context of the given scope.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="947a5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="947a5-104">Syntax</span></span>  
  
```  
  
Count(expression, scope, recursive)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="947a5-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="947a5-105">Parameters</span></span>  
 <span data-ttu-id="947a5-106">*expression*</span><span class="sxs-lookup"><span data-stu-id="947a5-106">*expression*</span></span>  
 <span data-ttu-id="947a5-107">(`Variant` o `Binary`) Espressione su cui eseguire l'aggregazione, ad esempio `=Fields!FieldName.Value`.</span><span class="sxs-lookup"><span data-stu-id="947a5-107">(`Variant` or `Binary`) The expression on which to perform the aggregation, for example, `=Fields!FieldName.Value`.</span></span>  
  
 <span data-ttu-id="947a5-108">*ambito*</span><span class="sxs-lookup"><span data-stu-id="947a5-108">*scope*</span></span>  
 <span data-ttu-id="947a5-109">(`String`) Nome di un set di dati, gruppo o area dati contenente gli elementi del report a cui applicare la funzione di aggregazione.</span><span class="sxs-lookup"><span data-stu-id="947a5-109">(`String`) The name of a dataset, group, or data region that contains the report items to which to apply the aggregate function.</span></span> <span data-ttu-id="947a5-110">Se si omette *scope* , viene usato l'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="947a5-110">If *scope* is not specified, the current scope is used.</span></span>  
  
 <span data-ttu-id="947a5-111">*ricorsivi*</span><span class="sxs-lookup"><span data-stu-id="947a5-111">*recursive*</span></span>  
 <span data-ttu-id="947a5-112">(**Enumerated Type**) Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="947a5-112">(**Enumerated Type**) Optional.</span></span> <span data-ttu-id="947a5-113">`Simple` (valore predefinito) o `RdlRecursive`.</span><span class="sxs-lookup"><span data-stu-id="947a5-113">`Simple` (default) or `RdlRecursive`.</span></span> <span data-ttu-id="947a5-114">Specifica se eseguire l'aggregazione in modo ricorsivo.</span><span class="sxs-lookup"><span data-stu-id="947a5-114">Specifies whether to perform the aggregation recursively.</span></span>  
  
## <a name="return-type"></a><span data-ttu-id="947a5-115">Tipo restituito</span><span class="sxs-lookup"><span data-stu-id="947a5-115">Return Type</span></span>  
 <span data-ttu-id="947a5-116">Restituisce un valore `Integer`.</span><span class="sxs-lookup"><span data-stu-id="947a5-116">Returns an `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="947a5-117">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="947a5-117">Remarks</span></span>  
 <span data-ttu-id="947a5-118">Il valore di *scope* deve essere una costante di tipo stringa e non può essere un'espressione.</span><span class="sxs-lookup"><span data-stu-id="947a5-118">The value of *scope* must be a string constant and cannot be an expression.</span></span> <span data-ttu-id="947a5-119">Per aggregazioni o aggregazioni esterne che non specificano altre aggregazioni, *scope* deve fare riferimento all'ambito corrente o a un ambito contenitore.</span><span class="sxs-lookup"><span data-stu-id="947a5-119">For outer aggregates or aggregates that do not specify other aggregates, *scope* must refer to the current scope or a containing scope.</span></span> <span data-ttu-id="947a5-120">Per le aggregazioni di aggregazioni, le aggregazioni nidificate possono specificare un ambito figlio.</span><span class="sxs-lookup"><span data-stu-id="947a5-120">For aggregates of aggregates, nested aggregates can specify a child scope.</span></span>  
  
 <span data-ttu-id="947a5-121">*Expression* può contenere chiamate alle funzioni di aggregazione nidificate con le eccezioni e le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="947a5-121">*Expression* can contain calls to nested aggregate functions with the following exceptions and conditions:</span></span>  
  
-   <span data-ttu-id="947a5-122">*Scope* per le aggregazioni nidificate deve corrispondere o essere contenuto nell'ambito dell'aggregazione esterna.</span><span class="sxs-lookup"><span data-stu-id="947a5-122">*Scope* for nested aggregates must be the same as, or contained by, the scope of the outer aggregate.</span></span> <span data-ttu-id="947a5-123">Per tutti gli ambiti distinti nell'espressione, un ambito deve essere in una relazione figlio con tutti gli altri ambiti.</span><span class="sxs-lookup"><span data-stu-id="947a5-123">For all distinct scopes in the expression, one scope must be in a child relationship to all other scopes.</span></span>  
  
-   <span data-ttu-id="947a5-124">*Scope* per le aggregazioni nidificate non può essere il nome di un set di dati.</span><span class="sxs-lookup"><span data-stu-id="947a5-124">*Scope* for nested aggregates cannot be the name of a dataset.</span></span>  
  
-   <span data-ttu-id="947a5-125">L' *espressione* non deve contenere `First` funzioni,, `Last` `Previous` o `RunningValue` .</span><span class="sxs-lookup"><span data-stu-id="947a5-125">*Expression* must not contain `First`, `Last`, `Previous`, or `RunningValue` functions.</span></span>  
  
-   <span data-ttu-id="947a5-126">*Expression* non deve contenere aggregazioni nidificate che specificano *recursive*.</span><span class="sxs-lookup"><span data-stu-id="947a5-126">*Expression* must not contain nested aggregates that specify *recursive*.</span></span>  
  
 <span data-ttu-id="947a5-127">Per altre informazioni, vedere [Riferimento a funzioni di aggregazione &#40;Generatore report e SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) e [Ambito di espressioni per totali, aggregazioni e raccolte predefinite &#40;Generatore report e SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="947a5-127">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) and [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
 <span data-ttu-id="947a5-128">Per altre informazioni sulle aggregazioni ricorsive, vedere [Creazione di gruppi di gerarchie ricorsive &#40;Generatore report e SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="947a5-128">For more information about recursive aggregates, see [Creating Recursive Hierarchy Groups &#40;Report Builder and SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="947a5-129">Esempio</span><span class="sxs-lookup"><span data-stu-id="947a5-129">Example</span></span>  
  
## <a name="description"></a><span data-ttu-id="947a5-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="947a5-130">Description</span></span>  
 <span data-ttu-id="947a5-131">Nell'esempio di codice seguente è illustrata un'espressione che calcola il numero di valori non Null di `Size` per l'ambito predefinito e per un ambito di gruppo padre.</span><span class="sxs-lookup"><span data-stu-id="947a5-131">The following code example shows an expression that calculates the number of non-null values of `Size` for the default scope and for a parent group scope.</span></span> <span data-ttu-id="947a5-132">L'espressione viene aggiunta a una riga di una cella che appartiene al gruppo figlio `GroupbySubcategory`.</span><span class="sxs-lookup"><span data-stu-id="947a5-132">The expression is added to a cell in a row that belongs to the child group `GroupbySubcategory`.</span></span> <span data-ttu-id="947a5-133">Il gruppo padre è `GroupbyCategory`.</span><span class="sxs-lookup"><span data-stu-id="947a5-133">The parent group is `GroupbyCategory`.</span></span> <span data-ttu-id="947a5-134">L'espressione visualizza i risultati per `GroupbySubcategory` (ambito predefinito) e quindi per `GroupbyCategory` (ambito del gruppo padre).</span><span class="sxs-lookup"><span data-stu-id="947a5-134">The expression displays the results for `GroupbySubcategory` (the default scope) and then for `GroupbyCategory` (the parent group scope).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="947a5-135">Le espressioni non devono contenere ritorni a capo e interruzioni di riga, che sono inclusi nell'esempio per supportare i renderer della documentazione.</span><span class="sxs-lookup"><span data-stu-id="947a5-135">Expressions should not contain actual carriage returns and line breaks; these are included in the example to support documentation renderers.</span></span> <span data-ttu-id="947a5-136">Se si copia l'esempio seguente, rimuovere i ritorni a capo da ogni riga.</span><span class="sxs-lookup"><span data-stu-id="947a5-136">If you copy the following example, remove carriage returns from each line.</span></span>  
  
## <a name="code"></a><span data-ttu-id="947a5-137">Codice</span><span class="sxs-lookup"><span data-stu-id="947a5-137">Code</span></span>  
  
```  
="Count (Subcategory): " & Count(Fields!Size.Value) &   
"Count (Category): " & Count(Fields!Size.Value,"GroupbyCategory")  
```  
  
## <a name="see-also"></a><span data-ttu-id="947a5-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="947a5-138">See Also</span></span>  
 <span data-ttu-id="947a5-139">[Utilizzo delle espressioni nei report &#40;Generatore report e SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="947a5-139">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="947a5-140">[Esempi di espressioni &#40;Generatore report e SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="947a5-140">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="947a5-141">[Tipi di dati nelle espressioni &#40;Generatore report e SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="947a5-141">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="947a5-142">Ambito di espressioni per totali, aggregazioni e raccolte predefinite &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="947a5-142">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
