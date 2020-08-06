---
title: Funzione Lookup (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: e60e5bab-b286-4897-9685-9ff12703517d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 053fefff51e4b4e338e262664bd7570280c92540
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628415"
---
# <a name="lookup-function-report-builder-and-ssrs"></a><span data-ttu-id="f074e-102">Funzione Lookup (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="f074e-102">Lookup Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="f074e-103">Viene restituito il primo valore corrispondente per il nome specificato da un set di dati contenente coppie nome/valore.</span><span class="sxs-lookup"><span data-stu-id="f074e-103">Returns the first matching value for the specified name from a dataset that contains name/value pairs.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="f074e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f074e-104">Syntax</span></span>  
  
```  
  
Lookup(source_expression, destination_expression, result_expression, dataset)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f074e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f074e-105">Parameters</span></span>  
 <span data-ttu-id="f074e-106">*source_expression*</span><span class="sxs-lookup"><span data-stu-id="f074e-106">*source_expression*</span></span>  
 <span data-ttu-id="f074e-107">(`Variant`) Espressione valutata nell'ambito corrente che specifica il nome o la chiave da ricercare,</span><span class="sxs-lookup"><span data-stu-id="f074e-107">(`Variant`) An expression that is evaluated in the current scope and that specifies the name or key to look up.</span></span> <span data-ttu-id="f074e-108">Ad esempio: `=Fields!ProdID.Value`.</span><span class="sxs-lookup"><span data-stu-id="f074e-108">For example, `=Fields!ProdID.Value`.</span></span>  
  
 <span data-ttu-id="f074e-109">*destination_expression*</span><span class="sxs-lookup"><span data-stu-id="f074e-109">*destination_expression*</span></span>  
 <span data-ttu-id="f074e-110">(`Variant`) Espressione valutata per ogni riga in un set di dati che specifica il nome o la chiave con cui eseguire la corrispondenza,</span><span class="sxs-lookup"><span data-stu-id="f074e-110">(`Variant`) An expression that is evaluated for each row in a dataset and that specifies the name or key to match on.</span></span> <span data-ttu-id="f074e-111">Ad esempio: `=Fields!ProductID.Value`.</span><span class="sxs-lookup"><span data-stu-id="f074e-111">For example, `=Fields!ProductID.Value`.</span></span>  
  
 <span data-ttu-id="f074e-112">*result_expression*</span><span class="sxs-lookup"><span data-stu-id="f074e-112">*result_expression*</span></span>  
 <span data-ttu-id="f074e-113">( `Variant` ) Espressione valutata per la riga nel set di dati in cui *source_expression*  =  *destination_expression*e che specifica il valore da recuperare.</span><span class="sxs-lookup"><span data-stu-id="f074e-113">(`Variant`) An expression that is evaluated for the row in the dataset where *source_expression* = *destination_expression*, and that specifies the value to retrieve.</span></span> <span data-ttu-id="f074e-114">Ad esempio: `=Fields!ProductName.Value`.</span><span class="sxs-lookup"><span data-stu-id="f074e-114">For example, `=Fields!ProductName.Value`.</span></span>  
  
 <span data-ttu-id="f074e-115">*set di dati*</span><span class="sxs-lookup"><span data-stu-id="f074e-115">*dataset*</span></span>  
 <span data-ttu-id="f074e-116">Costante che specifica il nome di un set di dati nel report,</span><span class="sxs-lookup"><span data-stu-id="f074e-116">A constant that specifies the name of a dataset in the report.</span></span> <span data-ttu-id="f074e-117">ad esempio, "Prodotti".</span><span class="sxs-lookup"><span data-stu-id="f074e-117">For example, "Products".</span></span>  
  
## <a name="return"></a><span data-ttu-id="f074e-118">Return</span><span class="sxs-lookup"><span data-stu-id="f074e-118">Return</span></span>  
 <span data-ttu-id="f074e-119">Restituisce `Variant` o `Nothing` se non viene rilevata alcuna corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="f074e-119">Returns a `Variant`, or `Nothing` if there is no match.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f074e-120">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="f074e-120">Remarks</span></span>  
 <span data-ttu-id="f074e-121">Utilizzare la funzione `Lookup` per recuperare il valore dal set di dati specificato per una coppia nome/valore in cui esiste una relazione uno-a-uno.</span><span class="sxs-lookup"><span data-stu-id="f074e-121">Use `Lookup` to retrieve the value from the specified dataset for a name/value pair where there is a 1-to-1 relationship.</span></span> <span data-ttu-id="f074e-122">Ad esempio per un campo ID in una tabella, è possibile utilizzare `Lookup` per recuperare il campo Nome corrispondente da un set di dati non associato all'area dati.</span><span class="sxs-lookup"><span data-stu-id="f074e-122">For example, for an ID field in a table, you can use `Lookup` to retrieve the corresponding Name field from a dataset that is not bound to the data region.</span></span>  
  
 <span data-ttu-id="f074e-123">Tramite la funzione `Lookup` vengono effettuate le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f074e-123">`Lookup` does the following:</span></span>  
  
-   <span data-ttu-id="f074e-124">Valuta l'espressione di origine nell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="f074e-124">Evaluates the source expression in the current scope.</span></span>  
  
-   <span data-ttu-id="f074e-125">Valuta l'espressione di destinazione per ogni riga del set di dati specificato dopo che sono stati applicati i filtri, in base alle regole di confronto del set di dati specificato.</span><span class="sxs-lookup"><span data-stu-id="f074e-125">Evaluates the destination expression for each row of the specified dataset after filters have been applied, based on the collation of the specified dataset.</span></span>  
  
-   <span data-ttu-id="f074e-126">Nella prima corrispondenza di espressione di origine ed espressione di destinazione, valuta l'espressione di risultato per quella riga nel set di dati.</span><span class="sxs-lookup"><span data-stu-id="f074e-126">On the first match of source expression and destination expression, evaluates the result expression for that row in the dataset.</span></span>  
  
-   <span data-ttu-id="f074e-127">Restituisce il valore dell'espressione di risultato.</span><span class="sxs-lookup"><span data-stu-id="f074e-127">Returns the result expression value.</span></span>  
  
 <span data-ttu-id="f074e-128">Per recuperare più valori per un solo nome o un campo chiave in cui esiste una relazione uno-a-molti, usare [Funzione LookupSet &#40;Generatore report e SSRS&#41;](report-builder-functions-lookupset-function.md).</span><span class="sxs-lookup"><span data-stu-id="f074e-128">To retrieve multiple values for a single name or key field where there is a 1-to-many relationship, use [LookupSet Function &#40;Report Builder and SSRS&#41;](report-builder-functions-lookupset-function.md).</span></span> <span data-ttu-id="f074e-129">Per chiamare `Lookup` un set di valori, usare la [funzione multilookup &#40;Generatore report e SSRS&#41;](report-builder-functions-lookup-function.md).</span><span class="sxs-lookup"><span data-stu-id="f074e-129">To call `Lookup` for a set of values, use [Multilookup Function &#40;Report Builder and SSRS&#41;](report-builder-functions-lookup-function.md).</span></span>  
  
 <span data-ttu-id="f074e-130">Si applicano le restrizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f074e-130">The following restrictions apply:</span></span>  
  
-   <span data-ttu-id="f074e-131">La funzione `Lookup` viene valutata dopo l'applicazione di tutte le espressioni di filtro.</span><span class="sxs-lookup"><span data-stu-id="f074e-131">`Lookup` is evaluated after all filter expressions are applied.</span></span>  
  
-   <span data-ttu-id="f074e-132">È supportato solo un livello di ricerca.</span><span class="sxs-lookup"><span data-stu-id="f074e-132">Only one level of lookup is supported.</span></span> <span data-ttu-id="f074e-133">Un'espressione di origine, destinazione o risultato non può includere un riferimento a una funzione di ricerca.</span><span class="sxs-lookup"><span data-stu-id="f074e-133">A source, destination, or result expression cannot include a reference to a lookup function.</span></span>  
  
-   <span data-ttu-id="f074e-134">Le espressioni di origine e di destinazione devono restituire lo stesso tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="f074e-134">Source and destination expressions must evaluate to the same data type.</span></span> <span data-ttu-id="f074e-135">Il tipo restituito è lo stesso del tipo di dati dell'espressione di risultato valutata.</span><span class="sxs-lookup"><span data-stu-id="f074e-135">The return type is the same as the data type of the evaluated result expression.</span></span>  
  
-   <span data-ttu-id="f074e-136">Le espressioni di origine, di destinazione e di risultato non possono includere riferimenti a variabili di report o di gruppo.</span><span class="sxs-lookup"><span data-stu-id="f074e-136">Source, destination, and result expressions cannot include references to report or group variables.</span></span>  
  
-   <span data-ttu-id="f074e-137">La funzione `Lookup` non può essere utilizzata come espressione per gli elementi del report seguenti:</span><span class="sxs-lookup"><span data-stu-id="f074e-137">`Lookup` cannot be used as an expression for the following report items:</span></span>  
  
    -   <span data-ttu-id="f074e-138">Stringhe di connessione dinamiche per un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="f074e-138">Dynamic connection strings for a data source.</span></span>  
  
    -   <span data-ttu-id="f074e-139">Campi calcolati in un set di dati.</span><span class="sxs-lookup"><span data-stu-id="f074e-139">Calculated fields in a dataset.</span></span>  
  
    -   <span data-ttu-id="f074e-140">Parametri di query in un set di dati.</span><span class="sxs-lookup"><span data-stu-id="f074e-140">Query parameters in a dataset.</span></span>  
  
    -   <span data-ttu-id="f074e-141">Filtri in un set di dati.</span><span class="sxs-lookup"><span data-stu-id="f074e-141">Filters in a dataset.</span></span>  
  
    -   <span data-ttu-id="f074e-142">Parametri di report.</span><span class="sxs-lookup"><span data-stu-id="f074e-142">Report parameters.</span></span>  
  
    -   <span data-ttu-id="f074e-143">Proprietà Report.Language.</span><span class="sxs-lookup"><span data-stu-id="f074e-143">The Report.Language property.</span></span>  
  
 <span data-ttu-id="f074e-144">Per altre informazioni, vedere [Riferimento a funzioni di aggregazione &#40;Generatore report e SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) e [Ambito di espressioni per totali, aggregazioni e raccolte predefinite &#40;Generatore report e SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="f074e-144">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) and [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f074e-145">Esempio</span><span class="sxs-lookup"><span data-stu-id="f074e-145">Example</span></span>  
 <span data-ttu-id="f074e-146">Nell'esempio seguente, si supponga che una tabella sia associata a un set di dati che include un campo per l'identificatore del prodotto ProductID.</span><span class="sxs-lookup"><span data-stu-id="f074e-146">In the following example, assume that a table is bound to a dataset that includes a field for the product identifier ProductID.</span></span> <span data-ttu-id="f074e-147">Un set di dati separato denominato "Prodotto" contiene l'ID dell'identificatore del prodotto e il Nome del nome del prodotto corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="f074e-147">A separate dataset called "Product" contains the corresponding product identifier ID and the product name Name.</span></span>  
  
 <span data-ttu-id="f074e-148">Nell'espressione seguente, la funzione `Lookup` confronta il valore di ProductID con l'ID in ogni riga del set di dati denominata "Prodotto" e, quando viene rilevata una corrispondenza, restituisce il valore del campo Name per quella riga.</span><span class="sxs-lookup"><span data-stu-id="f074e-148">In the following expression, `Lookup` compares the value of ProductID to ID in each row of the dataset called "Product" and, when a match is found, returns the value of the Name field for that row.</span></span>  
  
```  
=Lookup(Fields!ProductID.Value, Fields!ID.Value, Fields!Name.Value, "Product")  
```  
  
## <a name="see-also"></a><span data-ttu-id="f074e-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f074e-149">See Also</span></span>  
 <span data-ttu-id="f074e-150">[Utilizzo delle espressioni nei report &#40;Generatore report e SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f074e-150">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="f074e-151">[Esempi di espressioni &#40;Generatore report e SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f074e-151">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="f074e-152">[Tipi di dati nelle espressioni &#40;Generatore report e SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f074e-152">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="f074e-153">Ambito di espressioni per totali, aggregazioni e raccolte predefinite &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="f074e-153">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
