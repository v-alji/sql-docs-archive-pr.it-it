---
title: Funzione Previous (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 403a9384-6ca4-42e8-97ca-ac3f6fe4316b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3891deec3f152cdf46da77a7f2d11d38387c5c8a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628409"
---
# <a name="previous-function-report-builder-and-ssrs"></a><span data-ttu-id="5d6c3-102">Funzione Previous (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="5d6c3-102">Previous Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="5d6c3-103">Restituisce il valore o il valore di aggregazione specificato per l'istanza precedente di un elemento all'interno dell'ambito specificato.</span><span class="sxs-lookup"><span data-stu-id="5d6c3-103">Returns the value or the specified aggregate value for the previous instance of an item within the specified scope.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="5d6c3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5d6c3-104">Syntax</span></span>  
  
```  
  
Previous(expression, scope)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5d6c3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5d6c3-105">Parameters</span></span>  
 <span data-ttu-id="5d6c3-106">*expression*</span><span class="sxs-lookup"><span data-stu-id="5d6c3-106">*expression*</span></span>  
 <span data-ttu-id="5d6c3-107">(`Variant` o `Binary`) Espressione da utilizzare per identificare i dati e per cui recuperare il valore precedente, ad esempio `Fields!Fieldname.Value` o `Sum(Fields!Fieldname.Value)`.</span><span class="sxs-lookup"><span data-stu-id="5d6c3-107">(`Variant` or `Binary`) The expression to use to identify the data and for which to retrieve the previous value, for example, `Fields!Fieldname.Value` or `Sum(Fields!Fieldname.Value)`.</span></span>  
  
 <span data-ttu-id="5d6c3-108">*ambito*</span><span class="sxs-lookup"><span data-stu-id="5d6c3-108">*scope*</span></span>  
 <span data-ttu-id="5d6c3-109">(`String`) Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="5d6c3-109">(`String`) Optional.</span></span> <span data-ttu-id="5d6c3-110">Nome di un gruppo o di un'area dati oppure null ( `Nothing` in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] ) che specifica l'ambito da cui recuperare il valore precedente specificato da *Expression*.</span><span class="sxs-lookup"><span data-stu-id="5d6c3-110">The name of a group or data region, or null (`Nothing` in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]), that specifies the scope from which to retrieve the previous value specified by *expression*.</span></span>  
  
## <a name="return-type"></a><span data-ttu-id="5d6c3-111">Tipo restituito</span><span class="sxs-lookup"><span data-stu-id="5d6c3-111">Return Type</span></span>  
 <span data-ttu-id="5d6c3-112">Restituisce un valore `Variant` o `Binary`.</span><span class="sxs-lookup"><span data-stu-id="5d6c3-112">Returns a `Variant` or `Binary`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5d6c3-113">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="5d6c3-113">Remarks</span></span>  
 <span data-ttu-id="5d6c3-114">La funzione `Previous` restituisce il valore precedente per l'espressione valutata nell'ambito specificato dopo l'applicazione di tutti i criteri di ordinamento e di filtro.</span><span class="sxs-lookup"><span data-stu-id="5d6c3-114">The `Previous` function returns the previous value for the expression evaluated in the specified scope after all sorting and filtering have been applied.</span></span>  
  
 <span data-ttu-id="5d6c3-115">Se l' *espressione* non contiene un'aggregazione, per `Previous` impostazione predefinita la funzione viene impostata sull'ambito corrente per l'elemento del report.</span><span class="sxs-lookup"><span data-stu-id="5d6c3-115">If *expression* does not contain an aggregate, the `Previous` function defaults to the current scope for the report item.</span></span>  
  
 <span data-ttu-id="5d6c3-116">In un gruppo di dettagli utilizzare `Previous` per specificare il valore di un riferimento di campo nell'istanza precedente della riga di dettaglio.</span><span class="sxs-lookup"><span data-stu-id="5d6c3-116">In a details group, use `Previous` to specify the value of a field reference in the previous instance of the detail row.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5d6c3-117">La `Previous` funzione supporta solo i riferimenti ai campi nel gruppo dettagli.</span><span class="sxs-lookup"><span data-stu-id="5d6c3-117">The `Previous` function only supports field references in the details group.</span></span> <span data-ttu-id="5d6c3-118">Ad esempio, per una casella di testo nel gruppo di dettagli, tramite `=Previous(Fields!Quantity.Value)` vengono restituiti i dati per il campo `Quantity` dalla riga precedente.</span><span class="sxs-lookup"><span data-stu-id="5d6c3-118">For example, in a text box in the details group, `=Previous(Fields!Quantity.Value)` returns the data for the field `Quantity` from the previous row.</span></span> <span data-ttu-id="5d6c3-119">Nella prima riga tramite questa espressione viene restituito un valore Null (`Nothing` in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="5d6c3-119">In the first row, this expression returns a null (`Nothing` in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]).</span></span>  
  
 <span data-ttu-id="5d6c3-120">Se *Expression* contiene una funzione di aggregazione che usa un ambito predefinito, `Previous` aggrega i dati all'interno dell'istanza precedente dell'ambito specificato nella chiamata di funzione di aggregazione.</span><span class="sxs-lookup"><span data-stu-id="5d6c3-120">If *expression* contains an aggregate function that uses a default scope, `Previous` aggregates the data within the previous instance of the scope specified in the aggregate function call.</span></span>  
  
 <span data-ttu-id="5d6c3-121">Se *Expression* contiene una funzione di aggregazione che specifica un ambito diverso da quello predefinito, il parametro *scope* per la `Previous` funzione deve essere un ambito contenitore per l'ambito specificato nella chiamata di funzione di aggregazione.</span><span class="sxs-lookup"><span data-stu-id="5d6c3-121">If *expression* contains an aggregate function that specifies a scope other than the default, the *scope* parameter for the `Previous` function must be a containing scope for the scope specified in the aggregate function call.</span></span>  
  
 <span data-ttu-id="5d6c3-122">Le funzioni `Level` , `InScope` `Aggregate` e `Previous` non possono essere usate nel parametro *Expression*.</span><span class="sxs-lookup"><span data-stu-id="5d6c3-122">The functions `Level`, `InScope`, `Aggregate` and `Previous` cannot be used in the *expression*parameter.</span></span> <span data-ttu-id="5d6c3-123">Non è possibile specificare il parametro *recursive* per una funzione di aggregazione.</span><span class="sxs-lookup"><span data-stu-id="5d6c3-123">Specifying the *recursive* parameter for any aggregate function is not supported.</span></span>  
  
 <span data-ttu-id="5d6c3-124">Per altre informazioni, vedere [Riferimento a funzioni di aggregazione &#40;Generatore report e SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) e [Ambito di espressioni per totali, aggregazioni e raccolte predefinite &#40;Generatore report e SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="5d6c3-124">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) and [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="5d6c3-125">Esempi</span><span class="sxs-lookup"><span data-stu-id="5d6c3-125">Examples</span></span>  
  
### <a name="description"></a><span data-ttu-id="5d6c3-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5d6c3-126">Description</span></span>  
 <span data-ttu-id="5d6c3-127">L'esempio di codice seguente, se inserito nella riga di dati predefinita di un'area dati, fornisce il valore per il campo `LineTotal` nella riga precedente.</span><span class="sxs-lookup"><span data-stu-id="5d6c3-127">The following code example, when placed in the default data row of a data region, provides the value for the field `LineTotal` in the previous row.</span></span>  
  
### <a name="code"></a><span data-ttu-id="5d6c3-128">Codice</span><span class="sxs-lookup"><span data-stu-id="5d6c3-128">Code</span></span>  
  
```  
=Previous(Fields!LineTotal.Value)  
```  
  
### <a name="description"></a><span data-ttu-id="5d6c3-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5d6c3-129">Description</span></span>  
 <span data-ttu-id="5d6c3-130">Nell'esempio seguente è illustrata un'espressione che calcola la somma delle vendite in un giorno del mese specifico e il valore precedente relativo allo stesso giorno del mese in un anno precedente.</span><span class="sxs-lookup"><span data-stu-id="5d6c3-130">The following example shows an expression that calculates the sum of sales on a specific day of the month and the previous value for that day of the month in a previous year.</span></span> <span data-ttu-id="5d6c3-131">L'espressione viene aggiunta a una riga di una cella che appartiene al gruppo figlio `GroupbyDay`.</span><span class="sxs-lookup"><span data-stu-id="5d6c3-131">The expression is added to a cell in a row that belongs to the child group `GroupbyDay`.</span></span> <span data-ttu-id="5d6c3-132">Il gruppo padre è `GroupbyMonth`, che dispone di un gruppo padre `GroupbyYear`.</span><span class="sxs-lookup"><span data-stu-id="5d6c3-132">Its parent group is `GroupbyMonth`, which has a parent group `GroupbyYear`.</span></span> <span data-ttu-id="5d6c3-133">L'espressione visualizza i risultati per GroupbyDay (ambito predefinito), quindi per `GroupbyYear` (elemento padre del gruppo padre `GroupbyMonth`).</span><span class="sxs-lookup"><span data-stu-id="5d6c3-133">The expression displays the results for GroupbyDay (the default scope) and then for `GroupbyYear` (the parent of the parent group `GroupbyMonth`).</span></span>  
  
 <span data-ttu-id="5d6c3-134">Ad esempio, per un'area dati con un gruppo padre denominato `Year`che ha un gruppo figlio denominato `Month`che a sua volta ha un gruppo figlio denominato `Day` (3 livelli annidati).</span><span class="sxs-lookup"><span data-stu-id="5d6c3-134">For example, for a data region with a parent group named `Year`, its child group named `Month`, and its child group named `Day` (3 nested levels).</span></span> <span data-ttu-id="5d6c3-135">L'espressione `=Previous(Sum(Fields!Sales.Value,"Day"),"Year")` in una riga associata al gruppo `Day` restituisce il valore delle vendite per lo stesso giorno e mese dell'anno precedente.</span><span class="sxs-lookup"><span data-stu-id="5d6c3-135">The expression `=Previous(Sum(Fields!Sales.Value,"Day"),"Year")` in a row associated with the group `Day` returns the sales value for the same day and month for the previous year.</span></span>  
  
### <a name="code"></a><span data-ttu-id="5d6c3-136">Codice</span><span class="sxs-lookup"><span data-stu-id="5d6c3-136">Code</span></span>  
  
```  
=Sum(Fields!Sales.Value) & " " & Previous(Sum(Fields!Sales.Value,"GroupbyDay"),"GroupbyYear")  
```  
  
## <a name="see-also"></a><span data-ttu-id="5d6c3-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5d6c3-137">See Also</span></span>  
 <span data-ttu-id="5d6c3-138">[Utilizzo delle espressioni nei report &#40;Generatore report e SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="5d6c3-138">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="5d6c3-139">[Esempi di espressioni &#40;Generatore report e SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="5d6c3-139">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="5d6c3-140">[Tipi di dati nelle espressioni &#40;Generatore report e SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="5d6c3-140">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="5d6c3-141">Ambito di espressioni per totali, aggregazioni e raccolte predefinite &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="5d6c3-141">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
