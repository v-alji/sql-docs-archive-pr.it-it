---
title: Funzione First (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: d0914520-30c5-4d63-9b59-8d9342ed63b9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2cd8578a1d9a17030d603457d4eaadf107316bdd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628423"
---
# <a name="first-function-report-builder-and-ssrs"></a><span data-ttu-id="2a01a-102">Funzione First (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="2a01a-102">First Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="2a01a-103">Restituisce il primo valore nell'ambito specificato dell'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="2a01a-103">Returns the first value in the given scope of the specified expression.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="2a01a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2a01a-104">Syntax</span></span>  
  
```  
  
First(expression, scope)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2a01a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2a01a-105">Parameters</span></span>  
 <span data-ttu-id="2a01a-106">*expression*</span><span class="sxs-lookup"><span data-stu-id="2a01a-106">*expression*</span></span>  
 <span data-ttu-id="2a01a-107">(`Variant` o `Binary`) Espressione su cui eseguire l'aggregazione, ad esempio `=Fields!FieldName.Value`.</span><span class="sxs-lookup"><span data-stu-id="2a01a-107">(`Variant` or `Binary`) The expression on which to perform the aggregation, for example, `=Fields!FieldName.Value`.</span></span>  
  
 <span data-ttu-id="2a01a-108">*ambito*</span><span class="sxs-lookup"><span data-stu-id="2a01a-108">*scope*</span></span>  
 <span data-ttu-id="2a01a-109">(`String`) Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="2a01a-109">(`String`) Optional.</span></span> <span data-ttu-id="2a01a-110">Nome di un set di dati, gruppo o area dati che contiene gli elementi del report a cui applicare la funzione di aggregazione.</span><span class="sxs-lookup"><span data-stu-id="2a01a-110">The name of a dataset, group, or data region that contains the report items to which to apply the aggregate function.</span></span> <span data-ttu-id="2a01a-111">Se si omette *scope* , viene usato l'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="2a01a-111">If *scope* is not specified, the current scope is used.</span></span>  
  
## <a name="return-type"></a><span data-ttu-id="2a01a-112">Tipo restituito</span><span class="sxs-lookup"><span data-stu-id="2a01a-112">Return Type</span></span>  
 <span data-ttu-id="2a01a-113">Determinato dal tipo di espressione.</span><span class="sxs-lookup"><span data-stu-id="2a01a-113">Determined by the type of expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2a01a-114">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="2a01a-114">Remarks</span></span>  
 <span data-ttu-id="2a01a-115">La funzione `First` restituisce il primo valore di un set di dati dopo l'applicazione di tutti i criteri di ordinamento e di filtro all'ambito specificato.</span><span class="sxs-lookup"><span data-stu-id="2a01a-115">The `First` function returns the first value in a set of data after all sorting and filtering have been applied at the specified scope.</span></span>  
  
 <span data-ttu-id="2a01a-116">La funzione `First` non può essere utilizzata nelle espressioni di filtro di gruppo con altri ambiti ad eccezione dell'ambito corrente (predefinito).</span><span class="sxs-lookup"><span data-stu-id="2a01a-116">The `First` function cannot be used in group filter expressions with anything except the current (default) scope.</span></span>  
  
 <span data-ttu-id="2a01a-117">È anche possibile utilizzare `First` in un'intestazione di pagina per restituire il primo valore della raccolta `ReportItems` per una pagina in modo da creare intestazioni in formato dizionario che visualizzano la prima e l'ultima voce in una pagina.</span><span class="sxs-lookup"><span data-stu-id="2a01a-117">You can also use `First` in a page header to return the first value from the `ReportItems` collection for a page in order to produce dictionary-style headings that display the first and last entries on a page.</span></span>  
  
 <span data-ttu-id="2a01a-118">Il valore di *scope* deve essere una costante di tipo stringa e non può essere un'espressione.</span><span class="sxs-lookup"><span data-stu-id="2a01a-118">The value of *scope* must be a string constant andcannot be an expression.</span></span> <span data-ttu-id="2a01a-119">Per aggregazioni o aggregazioni esterne che non specificano altre aggregazioni, *scope* deve fare riferimento all'ambito corrente o a un ambito contenitore.</span><span class="sxs-lookup"><span data-stu-id="2a01a-119">For outer aggregates or aggregates that do not specify other aggregates, *scope* must refer to the current scope or a containing scope.</span></span> <span data-ttu-id="2a01a-120">Per le aggregazioni di aggregazioni, le aggregazioni nidificate possono specificare un ambito figlio.</span><span class="sxs-lookup"><span data-stu-id="2a01a-120">For aggregates of aggregates, nested aggregates can specify a child scope.</span></span>  
  
 <span data-ttu-id="2a01a-121">*Expression* può contenere chiamate alle funzioni di aggregazione nidificate con le eccezioni e le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2a01a-121">*Expression* can contain calls to nested aggregate functions with the following exceptions and conditions:</span></span>  
  
-   <span data-ttu-id="2a01a-122">*Scope* per le aggregazioni nidificate deve corrispondere o essere contenuto nell'ambito dell'aggregazione esterna.</span><span class="sxs-lookup"><span data-stu-id="2a01a-122">*Scope* for nested aggregates must be the same as, or contained by, the scope of the outer aggregate.</span></span> <span data-ttu-id="2a01a-123">Per tutti gli ambiti distinti nell'espressione, un ambito deve essere in una relazione figlio con tutti gli altri ambiti.</span><span class="sxs-lookup"><span data-stu-id="2a01a-123">For all distinct scopes in the expression, one scope must be in a child relationship to all other scopes.</span></span>  
  
-   <span data-ttu-id="2a01a-124">*Scope* per le aggregazioni nidificate non può essere il nome di un set di dati.</span><span class="sxs-lookup"><span data-stu-id="2a01a-124">*Scope* for nested aggregates cannot be the name of a dataset.</span></span>  
  
-   <span data-ttu-id="2a01a-125">L' *espressione* non deve contenere `First` funzioni,, `Last` `Previous` o `RunningValue` .</span><span class="sxs-lookup"><span data-stu-id="2a01a-125">*Expression* must not contain `First`, `Last`, `Previous`, or `RunningValue` functions.</span></span>  
  
-   <span data-ttu-id="2a01a-126">*Expression* non deve contenere aggregazioni nidificate che specificano *recursive*.</span><span class="sxs-lookup"><span data-stu-id="2a01a-126">*Expression* must not contain nested aggregates that specify *recursive*.</span></span>  
  
 <span data-ttu-id="2a01a-127">Per altre informazioni, vedere [Riferimento a funzioni di aggregazione &#40;Generatore report e SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) e [Ambito di espressioni per totali, aggregazioni e raccolte predefinite &#40;Generatore report e SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="2a01a-127">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) and [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
 <span data-ttu-id="2a01a-128">Per altre informazioni sulle aggregazioni ricorsive, vedere [Creazione di gruppi di gerarchie ricorsive &#40;Generatore report e SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="2a01a-128">For more information about recursive aggregates, see [Creating Recursive Hierarchy Groups &#40;Report Builder and SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2a01a-129">Esempio</span><span class="sxs-lookup"><span data-stu-id="2a01a-129">Example</span></span>  
 <span data-ttu-id="2a01a-130">L'esempio di codice seguente restituisce il primo numero di prodotto nel gruppo o nell'area dati `Category` :</span><span class="sxs-lookup"><span data-stu-id="2a01a-130">The following code example returns the first product number in the `Category` group of a data region:</span></span>  
  
```  
=First(Fields!ProductNumber.Value, "Category")  
```  
  
## <a name="see-also"></a><span data-ttu-id="2a01a-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2a01a-131">See Also</span></span>  
 <span data-ttu-id="2a01a-132">[Utilizzo delle espressioni nei report &#40;Generatore report e SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2a01a-132">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="2a01a-133">[Esempi di espressioni &#40;Generatore report e SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2a01a-133">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="2a01a-134">[Tipi di dati nelle espressioni &#40;Generatore report e SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2a01a-134">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="2a01a-135">Ambito di espressioni per totali, aggregazioni e raccolte predefinite &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="2a01a-135">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
