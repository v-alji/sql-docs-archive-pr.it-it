---
title: Funzione Multilookup (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 1fec079e-33b3-4e4d-92b3-6b4d06a49a77
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2f2aff7a2a39e1a072cf4b05f0a04e12ced529af
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628413"
---
# <a name="multilookup-function-report-builder-and-ssrs"></a><span data-ttu-id="9b54b-102">Funzione Multilookup (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="9b54b-102">Multilookup Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="9b54b-103">Viene restituito il set di valori di prima corrispondenza per il set di nomi specificato da un set di dati che contiene coppie nome/valore.</span><span class="sxs-lookup"><span data-stu-id="9b54b-103">Returns the set of first-match values for the specified set of names from a dataset that contains name/value pairs.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="9b54b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9b54b-104">Syntax</span></span>  
  
```  
  
Multilookup(source_expression, destination_expression, result_expression, dataset)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9b54b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9b54b-105">Parameters</span></span>  
 <span data-ttu-id="9b54b-106">*source_expression*</span><span class="sxs-lookup"><span data-stu-id="9b54b-106">*source_expression*</span></span>  
 <span data-ttu-id="9b54b-107">(`VariantArray`) Espressione valutata nell'ambito corrente che specifica il set di nomi o chiavi da ricercare.</span><span class="sxs-lookup"><span data-stu-id="9b54b-107">(`VariantArray`) An expression that is evaluated in the current scope and that specifies the set of names or keys to look up.</span></span> <span data-ttu-id="9b54b-108">Ad esempio per un parametro multivalore, `=Parameters!IDs.value`.</span><span class="sxs-lookup"><span data-stu-id="9b54b-108">For example, for a multivalue parameter, `=Parameters!IDs.value`.</span></span>  
  
 <span data-ttu-id="9b54b-109">*destination_expression*</span><span class="sxs-lookup"><span data-stu-id="9b54b-109">*destination_expression*</span></span>  
 <span data-ttu-id="9b54b-110">(`Variant`) Espressione valutata per ogni riga in un set di dati che specifica il nome o la chiave con cui eseguire la corrispondenza,</span><span class="sxs-lookup"><span data-stu-id="9b54b-110">(`Variant`) An expression that is evaluated for each row in a dataset and that specifies the name or key to match on.</span></span> <span data-ttu-id="9b54b-111">Ad esempio: `=Fields!ID.Value`.</span><span class="sxs-lookup"><span data-stu-id="9b54b-111">For example, `=Fields!ID.Value`.</span></span>  
  
 <span data-ttu-id="9b54b-112">*result_expression*</span><span class="sxs-lookup"><span data-stu-id="9b54b-112">*result_expression*</span></span>  
 <span data-ttu-id="9b54b-113">( `Variant` ) Espressione valutata per la riga nel set di dati in cui *source_expression*  =  *destination_expression*e che specifica il valore da recuperare.</span><span class="sxs-lookup"><span data-stu-id="9b54b-113">(`Variant`) An expression that is evaluated for the row in the dataset where *source_expression* = *destination_expression*, and that specifies the value to retrieve.</span></span> <span data-ttu-id="9b54b-114">Ad esempio: `=Fields!Name.Value`.</span><span class="sxs-lookup"><span data-stu-id="9b54b-114">For example, `=Fields!Name.Value`.</span></span>  
  
 <span data-ttu-id="9b54b-115">*set di dati*</span><span class="sxs-lookup"><span data-stu-id="9b54b-115">*dataset*</span></span>  
 <span data-ttu-id="9b54b-116">Costante che specifica il nome di un set di dati nel report,</span><span class="sxs-lookup"><span data-stu-id="9b54b-116">A constant that specifies the name of a dataset in the report.</span></span> <span data-ttu-id="9b54b-117">ad esempio "Colori".</span><span class="sxs-lookup"><span data-stu-id="9b54b-117">For example, "Colors".</span></span>  
  
## <a name="return"></a><span data-ttu-id="9b54b-118">Return</span><span class="sxs-lookup"><span data-stu-id="9b54b-118">Return</span></span>  
 <span data-ttu-id="9b54b-119">Restituisce `VariantArray` o `Nothing` se non viene rilevata alcuna corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="9b54b-119">Returns a `VariantArray`, or `Nothing` if there is no match.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9b54b-120">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="9b54b-120">Remarks</span></span>  
 <span data-ttu-id="9b54b-121">Utilizzare `Multilookup` per recuperare un set di valori da un set di dati per coppie nome/valore in cui in ogni coppia è presente una relazione uno-a-molti.</span><span class="sxs-lookup"><span data-stu-id="9b54b-121">Use `Multilookup` to retrieve a set of values from a dataset for name-value pairs where each pair has a 1-to-1 relationship.</span></span> <span data-ttu-id="9b54b-122">`MultiLookup` è l'equivalente alla chiamata di `Lookup` per un set di nomi o chiavi.</span><span class="sxs-lookup"><span data-stu-id="9b54b-122">`MultiLookup` is the equivalent of calling `Lookup` for a set of names or keys.</span></span> <span data-ttu-id="9b54b-123">Per un parametro multivalore basato su identificatori di chiave primaria, ad esempio, è possibile utilizzare la funzione `Multilookup` in un'espressione in una casella di testo di una tabella per recuperare i valori associati da un set di dati non associato al parametro o alla tabella.</span><span class="sxs-lookup"><span data-stu-id="9b54b-123">For example, for a multivalue parameter that is based on primary key identifiers, you can use `Multilookup` in an expression in a text box in a table to retrieve associated values from a dataset that is not bound to the parameter or to the table.</span></span>  
  
 <span data-ttu-id="9b54b-124">Tramite la funzione `Multilookup` vengono effettuate le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9b54b-124">`Multilookup` does the following:</span></span>  
  
-   <span data-ttu-id="9b54b-125">Valuta l'espressione di origine nell'ambito corrente e genera una matrice di oggetti variant.</span><span class="sxs-lookup"><span data-stu-id="9b54b-125">Evaluates the source expression in the current scope and generates an array of variant objects.</span></span>  
  
-   <span data-ttu-id="9b54b-126">Per ogni oggetto nella matrice, chiama la [Funzione Lookup &#40;Generatore report e SSRS&#41;](report-builder-functions-lookup-function.md) e aggiunge il risultato alla matrice restituita.</span><span class="sxs-lookup"><span data-stu-id="9b54b-126">For each object in the array, calls [Lookup Function &#40;Report Builder and SSRS&#41;](report-builder-functions-lookup-function.md) and adds the result to the return array.</span></span>  
  
-   <span data-ttu-id="9b54b-127">Restituisce il set di risultati.</span><span class="sxs-lookup"><span data-stu-id="9b54b-127">Returns the set of results.</span></span>  
  
 <span data-ttu-id="9b54b-128">Per recuperare un singolo valore da un set di dati con coppie nome/valore per un nome specificato in cui è presente una relazione uno-a-uno, usare la [Funzione Lookup &#40;Generatore report e SSRS&#41;](report-builder-functions-lookup-function.md).</span><span class="sxs-lookup"><span data-stu-id="9b54b-128">To retrieve a single value from a dataset with name-value pairs for a specified name where there is a 1-to-1 relationship, use [Lookup Function &#40;Report Builder and SSRS&#41;](report-builder-functions-lookup-function.md).</span></span> <span data-ttu-id="9b54b-129">Per recuperare più valori da un set di dati con coppie nome/valore per un nome in cui è presente una relazione uno-a-molti, usare la [Funzione LookupSet &#40;Generatore report e SSRS&#41;](report-builder-functions-lookupset-function.md).</span><span class="sxs-lookup"><span data-stu-id="9b54b-129">To retrieve multiple values from a dataset with name-value pairs for a name where there is a 1-to-many relationship, use [LookupSet Function &#40;Report Builder and SSRS&#41;](report-builder-functions-lookupset-function.md).</span></span>  
  
 <span data-ttu-id="9b54b-130">Si applicano le restrizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9b54b-130">The following restrictions apply:</span></span>  
  
-   <span data-ttu-id="9b54b-131">La funzione `Multilookup` viene valutata dopo l'applicazione di tutte le espressioni di filtro</span><span class="sxs-lookup"><span data-stu-id="9b54b-131">`Multilookup` is evaluated after all filter expressions are applied</span></span>  
  
-   <span data-ttu-id="9b54b-132">È supportato solo un livello di ricerca.</span><span class="sxs-lookup"><span data-stu-id="9b54b-132">Only one level of look-up is supported.</span></span> <span data-ttu-id="9b54b-133">Un'espressione di origine, destinazione o risultato non può includere un riferimento a una funzione di ricerca.</span><span class="sxs-lookup"><span data-stu-id="9b54b-133">A source, destination, or result expression cannot include a reference to a lookup function.</span></span>  
  
-   <span data-ttu-id="9b54b-134">Le espressioni di origine e di destinazione devono restituire lo stesso tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="9b54b-134">Source and destination expressions must evaluate to the same data type.</span></span>  
  
-   <span data-ttu-id="9b54b-135">Le espressioni di origine, di destinazione e di risultato non possono includere riferimenti a variabili di report o di gruppo.</span><span class="sxs-lookup"><span data-stu-id="9b54b-135">Source, destination, and result expressions cannot include references to report or group variables.</span></span>  
  
-   <span data-ttu-id="9b54b-136">La funzione `Multilookup` non può essere utilizzata come espressione per gli elementi del report seguenti:</span><span class="sxs-lookup"><span data-stu-id="9b54b-136">`Multilookup` cannot be used as an expression for the following report items:</span></span>  
  
    -   <span data-ttu-id="9b54b-137">Stringhe di connessione dinamiche per un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="9b54b-137">Dynamic connection strings for a data source.</span></span>  
  
    -   <span data-ttu-id="9b54b-138">Campi calcolati in un set di dati.</span><span class="sxs-lookup"><span data-stu-id="9b54b-138">Calculated fields in a dataset.</span></span>  
  
    -   <span data-ttu-id="9b54b-139">Parametri di query in un set di dati.</span><span class="sxs-lookup"><span data-stu-id="9b54b-139">Query parameters in a dataset.</span></span>  
  
    -   <span data-ttu-id="9b54b-140">Filtri in un set di dati.</span><span class="sxs-lookup"><span data-stu-id="9b54b-140">Filters in a dataset.</span></span>  
  
    -   <span data-ttu-id="9b54b-141">Parametri di report.</span><span class="sxs-lookup"><span data-stu-id="9b54b-141">Report parameters.</span></span>  
  
    -   <span data-ttu-id="9b54b-142">Proprietà Report.Language.</span><span class="sxs-lookup"><span data-stu-id="9b54b-142">The Report.Language property.</span></span>  
  
 <span data-ttu-id="9b54b-143">Per altre informazioni, vedere [Riferimento a funzioni di aggregazione &#40;Generatore report e SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) e [Ambito di espressioni per totali, aggregazioni e raccolte predefinite &#40;Generatore report e SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="9b54b-143">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) and [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9b54b-144">Esempio</span><span class="sxs-lookup"><span data-stu-id="9b54b-144">Example</span></span>  
 <span data-ttu-id="9b54b-145">Si supponga che un set di dati denominato "Category" contenga il campo CategoryList che è un campo con un elenco di identificatori di categoria separato da virgole, ad esempio, "2, 4, 2, 1".</span><span class="sxs-lookup"><span data-stu-id="9b54b-145">Assume a dataset called "Category" contains the field CategoryList, which is a field that contains a comma-separated list of category identifers, for example, "2, 4, 2, 1".</span></span>  
  
 <span data-ttu-id="9b54b-146">Nel set di dati CategoryNames sono contenuti l'identificatore e il nome della categoria, come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="9b54b-146">The dataset CategoryNames contains the category identifier and category name, as shown in the following table.</span></span>  
  
|<span data-ttu-id="9b54b-147">ID</span><span class="sxs-lookup"><span data-stu-id="9b54b-147">ID</span></span>|<span data-ttu-id="9b54b-148">Nome</span><span class="sxs-lookup"><span data-stu-id="9b54b-148">Name</span></span>|  
|--------|----------|  
|<span data-ttu-id="9b54b-149">1</span><span class="sxs-lookup"><span data-stu-id="9b54b-149">1</span></span>|<span data-ttu-id="9b54b-150">Accessories</span><span class="sxs-lookup"><span data-stu-id="9b54b-150">Accessories</span></span>|  
|<span data-ttu-id="9b54b-151">2</span><span class="sxs-lookup"><span data-stu-id="9b54b-151">2</span></span>|<span data-ttu-id="9b54b-152">Bikes</span><span class="sxs-lookup"><span data-stu-id="9b54b-152">Bikes</span></span>|  
|<span data-ttu-id="9b54b-153">3</span><span class="sxs-lookup"><span data-stu-id="9b54b-153">3</span></span>|<span data-ttu-id="9b54b-154">Clothing</span><span class="sxs-lookup"><span data-stu-id="9b54b-154">Clothing</span></span>|  
|<span data-ttu-id="9b54b-155">4</span><span class="sxs-lookup"><span data-stu-id="9b54b-155">4</span></span>|<span data-ttu-id="9b54b-156">Componenti</span><span class="sxs-lookup"><span data-stu-id="9b54b-156">Components</span></span>|  
  
 <span data-ttu-id="9b54b-157">Per cercare i nomi che corrispondono all'elenco di identificatori, utilizzare `Multilookup`.</span><span class="sxs-lookup"><span data-stu-id="9b54b-157">To look up the names that correspond to the list of  identifiers, use `Multilookup`.</span></span> <span data-ttu-id="9b54b-158">È necessario innanzitutto suddividere l'elenco in una matrice di stringhe, chiamare la funzione `Multilookup` per recuperare i nomi di categoria e concatenare i risultati in una stringa.</span><span class="sxs-lookup"><span data-stu-id="9b54b-158">You must first split the list into a string array, call `Multilookup` to retrieve the category names, and concatenate the results into a string.</span></span>  
  
 <span data-ttu-id="9b54b-159">L'espressione seguente, se inserita in una casella di testo in un'area dati associata al set di dati Category, visualizza "Bikes, Components, Bikes, Accessories":</span><span class="sxs-lookup"><span data-stu-id="9b54b-159">The following expression, when placed in a text box in a data region bound to the Category dataset, displays "Bikes, Components, Bikes, Accessories":</span></span>  
  
```  
=Join(MultiLookup(Split(Fields!CategoryList.Value,","),  
   Fields!CategoryID.Value,Fields!CategoryName.Value,"Category")),  
   ", ")  
```  
  
## <a name="example"></a><span data-ttu-id="9b54b-160">Esempio</span><span class="sxs-lookup"><span data-stu-id="9b54b-160">Example</span></span>  
 <span data-ttu-id="9b54b-161">Si supponga che un set di dati ProductColors contenga un campo dell'identificatore del colore ColorID e un campo del valore del colore Color, come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="9b54b-161">Assume a dataset ProductColors contains a color identifier field ColorID and a color value field Color, as shown in the following table.</span></span>  
  
|<span data-ttu-id="9b54b-162">ColorID</span><span class="sxs-lookup"><span data-stu-id="9b54b-162">ColorID</span></span>|<span data-ttu-id="9b54b-163">Colore</span><span class="sxs-lookup"><span data-stu-id="9b54b-163">Color</span></span>|  
|-------------|-----------|  
|<span data-ttu-id="9b54b-164">1</span><span class="sxs-lookup"><span data-stu-id="9b54b-164">1</span></span>|<span data-ttu-id="9b54b-165">Rosso</span><span class="sxs-lookup"><span data-stu-id="9b54b-165">Red</span></span>|  
|<span data-ttu-id="9b54b-166">2</span><span class="sxs-lookup"><span data-stu-id="9b54b-166">2</span></span>|<span data-ttu-id="9b54b-167">Blu</span><span class="sxs-lookup"><span data-stu-id="9b54b-167">Blue</span></span>|  
|<span data-ttu-id="9b54b-168">3</span><span class="sxs-lookup"><span data-stu-id="9b54b-168">3</span></span>|<span data-ttu-id="9b54b-169">Green</span><span class="sxs-lookup"><span data-stu-id="9b54b-169">Green</span></span>|  
  
 <span data-ttu-id="9b54b-170">Si supponga che il parametro multivalore *MyColors* non sia associato a un set di dati per i valori disponibili.</span><span class="sxs-lookup"><span data-stu-id="9b54b-170">Assume the multivalue parameter *MyColors* is not bound to a dataset for its available values.</span></span> <span data-ttu-id="9b54b-171">I valori predefiniti per il parametro sono impostati su 2 e 3.</span><span class="sxs-lookup"><span data-stu-id="9b54b-171">The default values for the parameter are set to 2 and 3.</span></span> <span data-ttu-id="9b54b-172">L'espressione seguente, se inserita in una casella di testo all'interno di una tabella, consente di concatenare i valori selezionati per il parametro in un elenco delimitato da virgole e visualizza "Blue, Green".</span><span class="sxs-lookup"><span data-stu-id="9b54b-172">The following expression, when placed in a text box in a table, concatenates the multiple selected values for the parameter into a comma-separated list and displays "Blue, Green".</span></span>  
  
```  
=Join(MultiLookup(Parameters!MyColors.Value,Fields!ColorID.Value,Fields!Color.Value,"ProductColors"),", ")  
```  
  
## <a name="see-also"></a><span data-ttu-id="9b54b-173">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9b54b-173">See Also</span></span>  
 <span data-ttu-id="9b54b-174">[Utilizzo delle espressioni nei report &#40;Generatore report e SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="9b54b-174">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="9b54b-175">[Esempi di espressioni &#40;Generatore report e SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="9b54b-175">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="9b54b-176">[Tipi di dati nelle espressioni &#40;Generatore report e SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="9b54b-176">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="9b54b-177">Ambito di espressioni per totali, aggregazioni e raccolte predefinite &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="9b54b-177">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
