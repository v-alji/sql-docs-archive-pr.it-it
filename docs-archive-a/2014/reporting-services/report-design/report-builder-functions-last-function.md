---
title: Funzione Last (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 123b78a0-d6c9-4f78-b0e7-73b21854a250
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c343e72e476d4a717ca551eedeb0f02650479ca4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628420"
---
# <a name="last-function-report-builder-and-ssrs"></a><span data-ttu-id="bf426-102">Funzione Last (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="bf426-102">Last Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="bf426-103">Restituisce l'ultimo valore nell'ambito specificato dell'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="bf426-103">Returns the last value in the given scope of the specified expression.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="bf426-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bf426-104">Syntax</span></span>  
  
```  
  
Last(expression, scope)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bf426-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="bf426-105">Parameters</span></span>  
 <span data-ttu-id="bf426-106">*expression*</span><span class="sxs-lookup"><span data-stu-id="bf426-106">*expression*</span></span>  
 <span data-ttu-id="bf426-107">(`Variant` o `Binary`) Espressione su cui eseguire l'aggregazione, ad esempio `=Fields!Fieldname.Value`.</span><span class="sxs-lookup"><span data-stu-id="bf426-107">(`Variant` or `Binary`) The expression on which to perform the aggregation, for example, `=Fields!Fieldname.Value`.</span></span>  
  
 <span data-ttu-id="bf426-108">*ambito*</span><span class="sxs-lookup"><span data-stu-id="bf426-108">*scope*</span></span>  
 <span data-ttu-id="bf426-109">(`String`) (Facoltativo) Nome di un set di dati, area dati o gruppo che contiene gli elementi del report a cui applicare la funzione di aggregazione.</span><span class="sxs-lookup"><span data-stu-id="bf426-109">(`String`) (Optional) The name of a dataset, data region, or group that contains the report items to which to apply the function.</span></span> <span data-ttu-id="bf426-110">Se si omette *scope* , viene usato l'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="bf426-110">If *scope* is not specified, the current scope is used.</span></span>  
  
## <a name="return-type"></a><span data-ttu-id="bf426-111">Tipo restituito</span><span class="sxs-lookup"><span data-stu-id="bf426-111">Return Type</span></span>  
 <span data-ttu-id="bf426-112">Determinato dal tipo di espressione.</span><span class="sxs-lookup"><span data-stu-id="bf426-112">Determined by the type of expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bf426-113">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="bf426-113">Remarks</span></span>  
 <span data-ttu-id="bf426-114">La funzione `Last` restituisce il valore finale di un set di dati dopo l'applicazione di tutti i criteri di ordinamento e di filtro all'ambito specificato.</span><span class="sxs-lookup"><span data-stu-id="bf426-114">The `Last` function returns the final value in a set of data after all sorting and filtering have been applied at the specified scope.</span></span>  
  
 <span data-ttu-id="bf426-115">La funzione `Last` non può essere utilizzata nelle espressioni di filtro di gruppo con altri ambiti ad eccezione dell'ambito corrente (predefinito).</span><span class="sxs-lookup"><span data-stu-id="bf426-115">The `Last` function cannot be used in group filter expressions with anything except the current (default) scope.</span></span>  
  
 <span data-ttu-id="bf426-116">È anche possibile utilizzare `Last` in un'intestazione di pagina per restituire l'ultimo valore della raccolta `ReportItems` per una pagina in modo da creare intestazioni in formato dizionario che visualizzano la prima e l'ultima voce in una pagina.</span><span class="sxs-lookup"><span data-stu-id="bf426-116">You can also use `Last` in a page header to return the last value from the `ReportItems` collection for a page in order to produce dictionary-style headings that display the first and last entries on a page.</span></span>  
  
 <span data-ttu-id="bf426-117">Il valore di *scope* deve essere una costante di tipo stringa e non può essere un'espressione.</span><span class="sxs-lookup"><span data-stu-id="bf426-117">The value of *scope* must be a string constant andcannot be an expression.</span></span> <span data-ttu-id="bf426-118">Per aggregazioni o aggregazioni esterne che non specificano altre aggregazioni, *scope* deve fare riferimento all'ambito corrente o a un ambito contenitore.</span><span class="sxs-lookup"><span data-stu-id="bf426-118">For outer aggregates or aggregates that do not specify other aggregates, *scope* must refer to the current scope or a containing scope.</span></span> <span data-ttu-id="bf426-119">Per le aggregazioni di aggregazioni, le aggregazioni nidificate possono specificare un ambito figlio.</span><span class="sxs-lookup"><span data-stu-id="bf426-119">For aggregates of aggregates, nested aggregates can specify a child scope.</span></span>  
  
 <span data-ttu-id="bf426-120">*Expression* può contenere chiamate alle funzioni di aggregazione nidificate con le eccezioni e le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="bf426-120">*Expression* can contain calls to nested aggregate functions with the following exceptions and conditions:</span></span>  
  
-   <span data-ttu-id="bf426-121">*Scope* per le aggregazioni nidificate deve corrispondere o essere contenuto nell'ambito dell'aggregazione esterna.</span><span class="sxs-lookup"><span data-stu-id="bf426-121">*Scope* for nested aggregates must be the same as, or contained by, the scope of the outer aggregate.</span></span> <span data-ttu-id="bf426-122">Per tutti gli ambiti distinti nell'espressione, un ambito deve essere in una relazione figlio con tutti gli altri ambiti.</span><span class="sxs-lookup"><span data-stu-id="bf426-122">For all distinct scopes in the expression, one scope must be in a child relationship to all other scopes.</span></span>  
  
-   <span data-ttu-id="bf426-123">*Scope* per le aggregazioni nidificate non può essere il nome di un set di dati.</span><span class="sxs-lookup"><span data-stu-id="bf426-123">*Scope* for nested aggregates cannot be the name of a dataset.</span></span>  
  
-   <span data-ttu-id="bf426-124">L' *espressione* non deve contenere `First` funzioni,, `Last` `Previous` o `RunningValue` .</span><span class="sxs-lookup"><span data-stu-id="bf426-124">*Expression* must not contain `First`, `Last`, `Previous`, or `RunningValue` functions.</span></span>  
  
-   <span data-ttu-id="bf426-125">*Expression* non deve contenere aggregazioni nidificate che specificano *recursive*.</span><span class="sxs-lookup"><span data-stu-id="bf426-125">*Expression* must not contain nested aggregates that specify *recursive*.</span></span>  
  
 <span data-ttu-id="bf426-126">Per altre informazioni, vedere [Riferimento a funzioni di aggregazione &#40;Generatore report e SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) e [Ambito di espressioni per totali, aggregazioni e raccolte predefinite &#40;Generatore report e SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="bf426-126">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) and [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
 <span data-ttu-id="bf426-127">Per altre informazioni sulle aggregazioni ricorsive, vedere [Creazione di gruppi di gerarchie ricorsive &#40;Generatore report e SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="bf426-127">For more information about recursive aggregates, see [Creating Recursive Hierarchy Groups &#40;Report Builder and SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="bf426-128">Esempio</span><span class="sxs-lookup"><span data-stu-id="bf426-128">Example</span></span>  
 <span data-ttu-id="bf426-129">L'esempio di codice seguente restituisce l'ultimo numero di prodotto nel gruppo o nell'area dati `Category` .</span><span class="sxs-lookup"><span data-stu-id="bf426-129">The following code example returns the last product number in the `Category` group of a data region.</span></span>  
  
```  
=Last(Fields!ProductNumber.Value, "Category")  
```  
  
## <a name="see-also"></a><span data-ttu-id="bf426-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bf426-130">See Also</span></span>  
 <span data-ttu-id="bf426-131">[Utilizzo delle espressioni nei report &#40;Generatore report e SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="bf426-131">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="bf426-132">[Esempi di espressioni &#40;Generatore report e SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="bf426-132">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="bf426-133">[Tipi di dati nelle espressioni &#40;Generatore report e SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="bf426-133">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="bf426-134">Ambito di espressioni per totali, aggregazioni e raccolte predefinite &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="bf426-134">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
