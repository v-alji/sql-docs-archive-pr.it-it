---
title: Funzione RunningValue (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 6bee2f15-0e69-49c8-9689-b04544063b1d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 168073a0409455041f4ebe3aa4c5dcfc8fa129a0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628401"
---
# <a name="runningvalue-function-report-builder-and-ssrs"></a><span data-ttu-id="fc7b9-102">Funzione RunningValue (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="fc7b9-102">RunningValue Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="fc7b9-103">Restituisce un'aggregazione parziale di tutti i valori numerici non Null specificati dall'espressione, valutata per l'ambito specificato.</span><span class="sxs-lookup"><span data-stu-id="fc7b9-103">Returns a running aggregate of all non-null numeric values specified by the expression, evaluated for the given scope.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="fc7b9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fc7b9-104">Syntax</span></span>  
  
```  
  
RunningValue(expression, function, scope)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fc7b9-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="fc7b9-105">Parameters</span></span>  
 <span data-ttu-id="fc7b9-106">*expression*</span><span class="sxs-lookup"><span data-stu-id="fc7b9-106">*expression*</span></span>  
 <span data-ttu-id="fc7b9-107">Espressione su cui eseguire l'aggregazione, ad esempio `[Quantity]`.</span><span class="sxs-lookup"><span data-stu-id="fc7b9-107">The expression on which to perform the aggregation, for example, `[Quantity]`.</span></span>  
  
 <span data-ttu-id="fc7b9-108">*function*</span><span class="sxs-lookup"><span data-stu-id="fc7b9-108">*function*</span></span>  
 <span data-ttu-id="fc7b9-109">(`Enum`) Nome della funzione di aggregazione da applicare all'espressione, ad esempio `Sum`.</span><span class="sxs-lookup"><span data-stu-id="fc7b9-109">(`Enum`) The name of the aggregate function to apply to the expression, for example, `Sum`.</span></span> <span data-ttu-id="fc7b9-110">Tale funzione non può essere `RunningValue`, `RowNumber` o `Aggregate`.</span><span class="sxs-lookup"><span data-stu-id="fc7b9-110">This function cannot be `RunningValue`, `RowNumber`, or `Aggregate`.</span></span>  
  
 <span data-ttu-id="fc7b9-111">*ambito*</span><span class="sxs-lookup"><span data-stu-id="fc7b9-111">*scope*</span></span>  
 <span data-ttu-id="fc7b9-112">(`String`) Costante di tipo stringa ovvero il nome di un set di dati, area dati o gruppo oppure valore Null (`Nothing` in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]) tramite cui viene specificato il contesto in cui valutare l'aggregazione.</span><span class="sxs-lookup"><span data-stu-id="fc7b9-112">(`String`) A string constant that is the name of a dataset, data region, or group, or null (`Nothing` in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]), that specifies the context in which to evaluate the aggregation.</span></span> <span data-ttu-id="fc7b9-113">Tramite `Nothing` viene specificato il contesto più esterno, generalmente il set di dati del report.</span><span class="sxs-lookup"><span data-stu-id="fc7b9-113">`Nothing` specifies the outermost context, usually the report dataset.</span></span>  
  
## <a name="return-type"></a><span data-ttu-id="fc7b9-114">Tipo restituito</span><span class="sxs-lookup"><span data-stu-id="fc7b9-114">Return Type</span></span>  
 <span data-ttu-id="fc7b9-115">Dipende dalla funzione di aggregazione specificata nel parametro *function* .</span><span class="sxs-lookup"><span data-stu-id="fc7b9-115">Determined by the aggregate function that is specified in the *function* parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fc7b9-116">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="fc7b9-116">Remarks</span></span>  
 <span data-ttu-id="fc7b9-117">Il valore per `RunningValue` viene reimpostato su 0 per ogni nuova istanza dell'ambito.</span><span class="sxs-lookup"><span data-stu-id="fc7b9-117">The value for `RunningValue` resets to 0 for each new instance of the scope.</span></span> <span data-ttu-id="fc7b9-118">Se viene specificato un gruppo, il valore corrente viene reimpostato quando viene modificata l'espressione di raggruppamento.</span><span class="sxs-lookup"><span data-stu-id="fc7b9-118">If a group is specified, the running value is reset when the group expression changes.</span></span> <span data-ttu-id="fc7b9-119">Se viene specificata un'area dati, il valore corrente viene reimpostato per ogni nuova istanza dell'area dati.</span><span class="sxs-lookup"><span data-stu-id="fc7b9-119">If a data region is specified, the running value is reset for each new instance of the data region.</span></span> <span data-ttu-id="fc7b9-120">Se viene specificato un set di dati, il valore corrente non viene reimpostato nell'intero set di dati.</span><span class="sxs-lookup"><span data-stu-id="fc7b9-120">If a dataset is specified, the running value is not reset throughout the entire dataset.</span></span>  
  
 <span data-ttu-id="fc7b9-121">`RunningValue` non può essere utilizzato in un filtro o un'espressione di ordinamento.</span><span class="sxs-lookup"><span data-stu-id="fc7b9-121">`RunningValue` cannot be used in a filter or sort expression.</span></span>  
  
 <span data-ttu-id="fc7b9-122">Il set di dati per il quale il valore corrente è calcolato deve avere lo stesso tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="fc7b9-122">The set of data for which the running value is calculated must have the same data type.</span></span> <span data-ttu-id="fc7b9-123">Per convertire dati con più tipi di dati numerici nello stesso tipo di dati, usare funzioni di conversione come `CInt`, `CDbl` o `CDec`.</span><span class="sxs-lookup"><span data-stu-id="fc7b9-123">To convert data that has multiple numeric data types to the same data type, use conversion functions like `CInt`, `CDbl` or `CDec`.</span></span> <span data-ttu-id="fc7b9-124">Per altre informazioni, vedere [Funzioni di conversione del tipo](https://go.microsoft.com/fwlink/?LinkId=96142).</span><span class="sxs-lookup"><span data-stu-id="fc7b9-124">For more information, see [Type Conversion Functions](https://go.microsoft.com/fwlink/?LinkId=96142).</span></span>  
  
 <span data-ttu-id="fc7b9-125">*Scope* non può essere un'espressione.</span><span class="sxs-lookup"><span data-stu-id="fc7b9-125">*Scope* cannot be an expression.</span></span>  
  
 <span data-ttu-id="fc7b9-126">*Expression* può contenere chiamate alle funzioni di aggregazione nidificate con le eccezioni e le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="fc7b9-126">*Expression* can contain calls to nested aggregate functions with the following exceptions and conditions:</span></span>  
  
-   <span data-ttu-id="fc7b9-127">Scope per le aggregazioni nidificate deve corrispondere o essere contenuto nell'ambito dell'aggregazione esterna.</span><span class="sxs-lookup"><span data-stu-id="fc7b9-127">Scope for nested aggregates must be the same as, or contained by, the scope of the outer aggregate.</span></span> <span data-ttu-id="fc7b9-128">Per tutti gli ambiti distinti nell'espressione, un ambito deve essere in una relazione figlio con tutti gli altri ambiti.</span><span class="sxs-lookup"><span data-stu-id="fc7b9-128">For all distinct scopes in the expression, one scope must be in a child relationship to all other scopes.</span></span>  
  
-   <span data-ttu-id="fc7b9-129">Scope per le aggregazioni nidificate non può essere il nome di un set di dati.</span><span class="sxs-lookup"><span data-stu-id="fc7b9-129">Scope for nested aggregates cannot be the name of a dataset.</span></span>  
  
-   <span data-ttu-id="fc7b9-130">L' *espressione* non deve contenere `First` funzioni,, `Last` `Previous` o `RunningValue` .</span><span class="sxs-lookup"><span data-stu-id="fc7b9-130">*Expression* must not contain `First`, `Last`, `Previous`, or `RunningValue` functions.</span></span>  
  
-   <span data-ttu-id="fc7b9-131">*Expression* non deve contenere aggregazioni nidificate che specificano *recursive*.</span><span class="sxs-lookup"><span data-stu-id="fc7b9-131">*Expression* must not contain nested aggregates that specify *recursive*.</span></span>  
  
 <span data-ttu-id="fc7b9-132">Per calcolare il valore corrente del numero di righe, utilizzare `RowNumber`.</span><span class="sxs-lookup"><span data-stu-id="fc7b9-132">To calculate the running value of the number of rows, use `RowNumber`.</span></span> <span data-ttu-id="fc7b9-133">Per altre informazioni, vedere [Funzione RowNumber &#40;Generatore report e SSRS&#41;](report-builder-functions-rownumber-function.md).</span><span class="sxs-lookup"><span data-stu-id="fc7b9-133">For more information, see [RowNumber Function &#40;Report Builder and SSRS&#41;](report-builder-functions-rownumber-function.md).</span></span>  
  
 <span data-ttu-id="fc7b9-134">Per altre informazioni, vedere [Riferimento a funzioni di aggregazione &#40;Generatore report e SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) e [Ambito di espressioni per totali, aggregazioni e raccolte predefinite &#40;Generatore report e SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="fc7b9-134">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) and [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
 <span data-ttu-id="fc7b9-135">Per altre informazioni sulle aggregazioni ricorsive, vedere [Creazione di gruppi di gerarchie ricorsive &#40;Generatore report e SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="fc7b9-135">For more information about recursive aggregates, see [Creating Recursive Hierarchy Groups &#40;Report Builder and SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="fc7b9-136">Esempi</span><span class="sxs-lookup"><span data-stu-id="fc7b9-136">Examples</span></span>  
 <span data-ttu-id="fc7b9-137">L'esempio di codice seguente consente di ottenere una somma parziale del campo denominato `Cost` nell'ambito più esterno, che corrisponde al set di dati.</span><span class="sxs-lookup"><span data-stu-id="fc7b9-137">The following code example provides a running sum of the field named `Cost` in the outermost scope, which is the dataset.</span></span>  
  
```  
=RunningValue(Fields!Cost.Value, Sum, Nothing)  
```  
  
 <span data-ttu-id="fc7b9-138">L'esempio di codice seguente consente di ottenere una somma parziale del campo denominato `Score` nel set di dati denominato `DataSet1`.</span><span class="sxs-lookup"><span data-stu-id="fc7b9-138">The following code example provides a running sum of the field named `Score` in the dataset named `DataSet1`.</span></span>  
  
```  
=RunningValue(Fields!Score.Value,sum,"DataSet1")  
```  
  
 <span data-ttu-id="fc7b9-139">L'esempio di codice seguente consente di ottenere una somma parziale del campo denominato `Traffic Charges` nell'ambito più esterno.</span><span class="sxs-lookup"><span data-stu-id="fc7b9-139">The following code example provides a running sum of the field named `Traffic Charges` in the outermost scope.</span></span>  
  
```  
=RunningValue(Fields!Traffic Charges.Value, Sum, Nothing)  
```  
  
## <a name="see-also"></a><span data-ttu-id="fc7b9-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fc7b9-140">See Also</span></span>  
 <span data-ttu-id="fc7b9-141">[Utilizzo delle espressioni nei report &#40;Generatore report e SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="fc7b9-141">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="fc7b9-142">[Esempi di espressioni &#40;Generatore report e SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="fc7b9-142">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="fc7b9-143">[Tipi di dati nelle espressioni &#40;Generatore report e SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="fc7b9-143">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="fc7b9-144">Ambito di espressioni per totali, aggregazioni e raccolte predefinite &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="fc7b9-144">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
