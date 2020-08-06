---
title: Funzione CountDistinct (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 902c251e-e1e8-41d2-ac20-5bb6138ac410
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 62fab53d4f26a874ac40e0a915c4242a41c72ce0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628432"
---
# <a name="countdistinct-function-report-builder-and-ssrs"></a><span data-ttu-id="63d05-102">Funzione CountDistinct (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="63d05-102">CountDistinct Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="63d05-103">Restituisce un conteggio di tutti i distinti valori non Null specificati dall'espressione, valutato nel contesto dell'ambito specificato.</span><span class="sxs-lookup"><span data-stu-id="63d05-103">Returns a count of all distinct non-null values specified by the expression, evaluated in the context of the given scope.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="63d05-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="63d05-104">Syntax</span></span>  
  
```  
  
CountDistinct(expression, scope, recursive)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="63d05-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="63d05-105">Parameters</span></span>  
 <span data-ttu-id="63d05-106">*expression*</span><span class="sxs-lookup"><span data-stu-id="63d05-106">*expression*</span></span>  
 <span data-ttu-id="63d05-107">(`Variant`) Espressione su cui eseguire l'aggregazione.</span><span class="sxs-lookup"><span data-stu-id="63d05-107">(`Variant`) The expression on which to perform the aggregation.</span></span>  
  
 <span data-ttu-id="63d05-108">*ambito*</span><span class="sxs-lookup"><span data-stu-id="63d05-108">*scope*</span></span>  
 <span data-ttu-id="63d05-109">(`String`) Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="63d05-109">(`String`) Optional.</span></span> <span data-ttu-id="63d05-110">Nome di un set di dati, gruppo o area dati che contiene gli elementi del report a cui applicare la funzione di aggregazione.</span><span class="sxs-lookup"><span data-stu-id="63d05-110">The name of a dataset, group, or data region that contains the report items to which to apply the aggregate function.</span></span> <span data-ttu-id="63d05-111">Se si omette *scope* , viene usato l'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="63d05-111">If *scope* is not specified, the current scope is used.</span></span>  
  
 <span data-ttu-id="63d05-112">*ricorsivi*</span><span class="sxs-lookup"><span data-stu-id="63d05-112">*recursive*</span></span>  
 <span data-ttu-id="63d05-113">(**Enumerated Type**) Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="63d05-113">(**Enumerated Type**) Optional.</span></span> <span data-ttu-id="63d05-114">`Simple` (valore predefinito) o `RdlRecursive`.</span><span class="sxs-lookup"><span data-stu-id="63d05-114">`Simple` (default) or `RdlRecursive`.</span></span> <span data-ttu-id="63d05-115">Specifica se eseguire l'aggregazione in modo ricorsivo.</span><span class="sxs-lookup"><span data-stu-id="63d05-115">Specifies whether to perform the aggregation recursively.</span></span>  
  
## <a name="return-type"></a><span data-ttu-id="63d05-116">Tipo restituito</span><span class="sxs-lookup"><span data-stu-id="63d05-116">Return Type</span></span>  
 <span data-ttu-id="63d05-117">Restituisce un valore `Integer`.</span><span class="sxs-lookup"><span data-stu-id="63d05-117">Returns an `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="63d05-118">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="63d05-118">Remarks</span></span>  
 <span data-ttu-id="63d05-119">Il valore di *scope* deve essere una costante di tipo stringa e non può essere un'espressione.</span><span class="sxs-lookup"><span data-stu-id="63d05-119">The value of *scope* must be a string constant and cannot be an expression.</span></span> <span data-ttu-id="63d05-120">Per aggregazioni o aggregazioni esterne che non specificano altre aggregazioni, *scope* deve fare riferimento all'ambito corrente o a un ambito contenitore.</span><span class="sxs-lookup"><span data-stu-id="63d05-120">For outer aggregates or aggregates that do not specify other aggregates, *scope* must refer to the current scope or a containing scope.</span></span> <span data-ttu-id="63d05-121">Per le aggregazioni di aggregazioni, le aggregazioni nidificate possono specificare un ambito figlio.</span><span class="sxs-lookup"><span data-stu-id="63d05-121">For aggregates of aggregates, nested aggregates can specify a child scope.</span></span>  
  
 <span data-ttu-id="63d05-122">*Expression* può contenere chiamate alle funzioni di aggregazione nidificate con le eccezioni e le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="63d05-122">*Expression* can contain calls to nested aggregate functions with the following exceptions and conditions:</span></span>  
  
-   <span data-ttu-id="63d05-123">*Scope* per le aggregazioni nidificate deve corrispondere o essere contenuto nell'ambito dell'aggregazione esterna.</span><span class="sxs-lookup"><span data-stu-id="63d05-123">*Scope* for nested aggregates must be the same as, or contained by, the scope of the outer aggregate.</span></span> <span data-ttu-id="63d05-124">Per tutti gli ambiti distinti nell'espressione, un ambito deve essere in una relazione figlio con tutti gli altri ambiti.</span><span class="sxs-lookup"><span data-stu-id="63d05-124">For all distinct scopes in the expression, one scope must be in a child relationship to all other scopes.</span></span>  
  
-   <span data-ttu-id="63d05-125">*Scope* per le aggregazioni nidificate non può essere il nome di un set di dati.</span><span class="sxs-lookup"><span data-stu-id="63d05-125">*Scope* for nested aggregates cannot be the name of a dataset.</span></span>  
  
-   <span data-ttu-id="63d05-126">L' *espressione* non deve contenere `First` funzioni,, `Last` `Previous` o `RunningValue` .</span><span class="sxs-lookup"><span data-stu-id="63d05-126">*Expression* must not contain `First`, `Last`, `Previous`, or `RunningValue` functions.</span></span>  
  
-   <span data-ttu-id="63d05-127">*Expression* non deve contenere aggregazioni nidificate che specificano *recursive*.</span><span class="sxs-lookup"><span data-stu-id="63d05-127">*Expression* must not contain nested aggregates that specify *recursive*.</span></span>  
  
 <span data-ttu-id="63d05-128">Per altre informazioni, vedere [Riferimento a funzioni di aggregazione &#40;Generatore report e SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) e [Ambito di espressioni per totali, aggregazioni e raccolte predefinite &#40;Generatore report e SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="63d05-128">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) and [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
 <span data-ttu-id="63d05-129">Per altre informazioni sulle aggregazioni ricorsive, vedere [Creazione di gruppi di gerarchie ricorsive &#40;Generatore report e SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="63d05-129">For more information about recursive aggregates, see [Creating Recursive Hierarchy Groups &#40;Report Builder and SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="63d05-130">Esempio</span><span class="sxs-lookup"><span data-stu-id="63d05-130">Example</span></span>  
 <span data-ttu-id="63d05-131">L'esempio di codice seguente illustra un'espressione che calcola il numero di valori non Null univoci di `Size` per l'ambito predefinito e per un ambito di gruppo padre.</span><span class="sxs-lookup"><span data-stu-id="63d05-131">The following code example shows an expression that calculates the number of unique non-null values of `Size` for the default scope and for a parent group scope.</span></span> <span data-ttu-id="63d05-132">L'espressione viene aggiunta a una riga di una cella che appartiene al gruppo figlio `GroupbySubcategory`.</span><span class="sxs-lookup"><span data-stu-id="63d05-132">The expression is added to a cell in a row that belongs to the child group `GroupbySubcategory`.</span></span> <span data-ttu-id="63d05-133">Il gruppo padre è `GroupbyCategory`.</span><span class="sxs-lookup"><span data-stu-id="63d05-133">The parent group is `GroupbyCategory`.</span></span> <span data-ttu-id="63d05-134">L'espressione visualizza i risultati per `GroupbySubcategory` (ambito predefinito) e quindi per `GroupbyCategory` (ambito del gruppo padre).</span><span class="sxs-lookup"><span data-stu-id="63d05-134">The expression displays the results for `GroupbySubcategory` (the default scope) and then for `GroupbyCategory` (the parent group scope).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="63d05-135">Le espressioni non devono contenere ritorni a capo e interruzioni di riga, che sono inclusi nell'esempio di codice per supportare i renderer della documentazione.</span><span class="sxs-lookup"><span data-stu-id="63d05-135">Expressions should not contain actual carriage returns and line breaks; these are included in the example code to support documentation renderers.</span></span> <span data-ttu-id="63d05-136">Se si copia l'esempio seguente, rimuovere i ritorni a capo da ogni riga.</span><span class="sxs-lookup"><span data-stu-id="63d05-136">If you copy the following example, remove carriage returns from each line.</span></span>  
  
```  
="Distinct count (Subcategory): " & CountDistinct(Fields!Size.Value) &   
"Distinct count (Category): " & CountDistinct(Fields!Size.Value,"GroupbyCategory")  
```  
  
## <a name="see-also"></a><span data-ttu-id="63d05-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="63d05-137">See Also</span></span>  
 <span data-ttu-id="63d05-138">[Utilizzo delle espressioni nei report &#40;Generatore report e SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="63d05-138">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="63d05-139">[Esempi di espressioni &#40;Generatore report e SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="63d05-139">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="63d05-140">[Tipi di dati nelle espressioni &#40;Generatore report e SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="63d05-140">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="63d05-141">Ambito di espressioni per totali, aggregazioni e raccolte predefinite &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="63d05-141">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
