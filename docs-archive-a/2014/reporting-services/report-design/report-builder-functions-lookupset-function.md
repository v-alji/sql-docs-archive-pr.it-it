---
title: Funzione LookupSet (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 7685acfd-1c8d-420c-993c-903236fbe1ff
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 4edc7a17f2aa3813e8aa73e538594b5df3aeabc1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628418"
---
# <a name="lookupset-function-report-builder-and-ssrs"></a><span data-ttu-id="2c0f6-102">Funzione LookupSet (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="2c0f6-102">LookupSet Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="2c0f6-103">Viene restituito il set di valori corrispondenti per il nome specificato da un set di dati contenente coppie nome/valore.</span><span class="sxs-lookup"><span data-stu-id="2c0f6-103">Returns the set of matching values for the specified name from a dataset that contains name/value pairs.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="2c0f6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2c0f6-104">Syntax</span></span>  
  
```  
  
LookupSet(source_expression, destination_expression, result_expression, dataset)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2c0f6-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2c0f6-105">Parameters</span></span>  
 <span data-ttu-id="2c0f6-106">*source_expression*</span><span class="sxs-lookup"><span data-stu-id="2c0f6-106">*source_expression*</span></span>  
 <span data-ttu-id="2c0f6-107">(`Variant`) Espressione valutata nell'ambito corrente che specifica il nome o la chiave da ricercare,</span><span class="sxs-lookup"><span data-stu-id="2c0f6-107">(`Variant`) An expression that is evaluated in the current scope and that specifies the name or key to look up.</span></span> <span data-ttu-id="2c0f6-108">Ad esempio: `=Fields!ID.Value`.</span><span class="sxs-lookup"><span data-stu-id="2c0f6-108">For example, `=Fields!ID.Value`.</span></span>  
  
 <span data-ttu-id="2c0f6-109">*destination_expression*</span><span class="sxs-lookup"><span data-stu-id="2c0f6-109">*destination_expression*</span></span>  
 <span data-ttu-id="2c0f6-110">(`Variant`) Espressione valutata per ogni riga in un set di dati che specifica il nome o la chiave con cui eseguire la corrispondenza,</span><span class="sxs-lookup"><span data-stu-id="2c0f6-110">(`Variant`) An expression that is evaluated for each row in a dataset and that specifies the name or key to match on.</span></span> <span data-ttu-id="2c0f6-111">Ad esempio: `=Fields!CustomerID.Value`.</span><span class="sxs-lookup"><span data-stu-id="2c0f6-111">For example, `=Fields!CustomerID.Value`.</span></span>  
  
 <span data-ttu-id="2c0f6-112">*result_expression*</span><span class="sxs-lookup"><span data-stu-id="2c0f6-112">*result_expression*</span></span>  
 <span data-ttu-id="2c0f6-113">( `Variant` ) Espressione valutata per la riga nel set di dati in cui *source_expression*  =  *destination_expression*e che specifica il valore da recuperare.</span><span class="sxs-lookup"><span data-stu-id="2c0f6-113">(`Variant`) An expression that is evaluated for the row in the dataset where *source_expression* = *destination_expression*, and that specifies the value to retrieve.</span></span> <span data-ttu-id="2c0f6-114">Ad esempio: `=Fields!PhoneNumber.Value`.</span><span class="sxs-lookup"><span data-stu-id="2c0f6-114">For example, `=Fields!PhoneNumber.Value`.</span></span>  
  
 <span data-ttu-id="2c0f6-115">*set di dati*</span><span class="sxs-lookup"><span data-stu-id="2c0f6-115">*dataset*</span></span>  
 <span data-ttu-id="2c0f6-116">Costante che specifica il nome di un set di dati nel report,</span><span class="sxs-lookup"><span data-stu-id="2c0f6-116">A constant that specifies the name of a dataset in the report.</span></span> <span data-ttu-id="2c0f6-117">ad esempio "InformazioniDiContatto".</span><span class="sxs-lookup"><span data-stu-id="2c0f6-117">For example, "ContactInformation".</span></span>  
  
## <a name="return"></a><span data-ttu-id="2c0f6-118">Return</span><span class="sxs-lookup"><span data-stu-id="2c0f6-118">Return</span></span>  
 <span data-ttu-id="2c0f6-119">Restituisce `VariantArray` o `Nothing` se non viene rilevata alcuna corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="2c0f6-119">Returns a `VariantArray`, or `Nothing` if there is no match.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2c0f6-120">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="2c0f6-120">Remarks</span></span>  
 <span data-ttu-id="2c0f6-121">Usare la funzione `LookupSet` per recuperare un set di valori dal set di dati specificato per una coppia nome/valore in cui è presente una relazione uno-a-molti.</span><span class="sxs-lookup"><span data-stu-id="2c0f6-121">Use `LookupSet` to retrieve a set of values from the specified dataset for a name/value pair where there is a 1-to-many relationship.</span></span> <span data-ttu-id="2c0f6-122">Per un identificatore di cliente in una tabella, ad esempio, è possibile usare la funzione `LookupSet` per recuperare tutti i numeri di telefono relativi al cliente da un set di dati non associato all'area dati.</span><span class="sxs-lookup"><span data-stu-id="2c0f6-122">For example, for a customer identifier in a table, you can use `LookupSet` to retrieve all the associated phone numbers for that customer from a dataset that is not bound to the data region.</span></span>  
  
 <span data-ttu-id="2c0f6-123">Tramite la funzione `LookupSet` vengono effettuate le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2c0f6-123">`LookupSet` does the following:</span></span>  
  
-   <span data-ttu-id="2c0f6-124">Valuta l'espressione di origine nell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="2c0f6-124">Evaluates the source expression in the current scope.</span></span>  
  
-   <span data-ttu-id="2c0f6-125">Valuta l'espressione di destinazione per ogni riga del set di dati specificato dopo che sono stati applicati i filtri, in base alle regole di confronto del set di dati specificato.</span><span class="sxs-lookup"><span data-stu-id="2c0f6-125">Evaluates the destination expression for each row of the specified dataset after filters have been applied, based on the collation of the specified dataset.</span></span>  
  
-   <span data-ttu-id="2c0f6-126">Per ogni corrispondenza dell'espressione di origine e di destinazione, valuta l'espressione di risultato per quella riga nel set di dati.</span><span class="sxs-lookup"><span data-stu-id="2c0f6-126">For each match of source expression and destination expression, evaluates the result expression for that row in the dataset.</span></span>  
  
-   <span data-ttu-id="2c0f6-127">Restituisce il set di valori dell'espressione di risultato.</span><span class="sxs-lookup"><span data-stu-id="2c0f6-127">Returns the set of result expression values.</span></span>  
  
 <span data-ttu-id="2c0f6-128">Per recuperare un singolo valore da un set di dati con coppie nome/valore per un nome specificato in cui è presente una relazione uno-a-uno, usare la [Funzione Lookup &#40;Generatore report e SSRS&#41;](report-builder-functions-lookup-function.md).</span><span class="sxs-lookup"><span data-stu-id="2c0f6-128">To retrieve a single value from a dataset with name/value pairs for a specified name where there is a 1-to-1 relationship, use [Lookup Function &#40;Report Builder and SSRS&#41;](report-builder-functions-lookup-function.md).</span></span> <span data-ttu-id="2c0f6-129">Per chiamare `Lookup` un set di valori, usare la [funzione multilookup &#40;Generatore report e SSRS&#41;](report-builder-functions-multilookup-function.md).</span><span class="sxs-lookup"><span data-stu-id="2c0f6-129">To call `Lookup` for a set of values, use [Multilookup Function &#40;Report Builder and SSRS&#41;](report-builder-functions-multilookup-function.md).</span></span>  
  
 <span data-ttu-id="2c0f6-130">Si applicano le restrizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2c0f6-130">The following restrictions apply:</span></span>  
  
-   <span data-ttu-id="2c0f6-131">La funzione `LookupSet` viene valutata dopo l'applicazione di tutte le espressioni di filtro.</span><span class="sxs-lookup"><span data-stu-id="2c0f6-131">`LookupSet` is evaluated after all filter expressions are applied.</span></span>  
  
-   <span data-ttu-id="2c0f6-132">È supportato solo un livello di ricerca.</span><span class="sxs-lookup"><span data-stu-id="2c0f6-132">Only one level of lookup is supported.</span></span> <span data-ttu-id="2c0f6-133">Un'espressione di origine, destinazione o risultato non può includere un riferimento a una funzione di ricerca.</span><span class="sxs-lookup"><span data-stu-id="2c0f6-133">A source, destination, or result expression cannot include a reference to a lookup function.</span></span>  
  
-   <span data-ttu-id="2c0f6-134">Le espressioni di origine e di destinazione devono restituire lo stesso tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="2c0f6-134">Source and destination expressions must evaluate to the same data type.</span></span>  
  
-   <span data-ttu-id="2c0f6-135">Le espressioni di origine, di destinazione e di risultato non possono includere riferimenti a variabili di report o di gruppo.</span><span class="sxs-lookup"><span data-stu-id="2c0f6-135">Source, destination, and result expressions cannot include references to report or group variables.</span></span>  
  
-   <span data-ttu-id="2c0f6-136">La funzione `LookupSet` non può essere utilizzata come espressione per gli elementi del report seguenti:</span><span class="sxs-lookup"><span data-stu-id="2c0f6-136">`LookupSet` cannot be used as an expression for the following report items:</span></span>  
  
    -   <span data-ttu-id="2c0f6-137">Stringhe di connessione dinamiche per un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="2c0f6-137">Dynamic connection strings for a data source.</span></span>  
  
    -   <span data-ttu-id="2c0f6-138">Campi calcolati in un set di dati.</span><span class="sxs-lookup"><span data-stu-id="2c0f6-138">Calculated fields in a dataset.</span></span>  
  
    -   <span data-ttu-id="2c0f6-139">Parametri di query in un set di dati.</span><span class="sxs-lookup"><span data-stu-id="2c0f6-139">Query parameters in a dataset.</span></span>  
  
    -   <span data-ttu-id="2c0f6-140">Filtri in un set di dati.</span><span class="sxs-lookup"><span data-stu-id="2c0f6-140">Filters in a dataset.</span></span>  
  
    -   <span data-ttu-id="2c0f6-141">Parametri di report.</span><span class="sxs-lookup"><span data-stu-id="2c0f6-141">Report parameters.</span></span>  
  
    -   <span data-ttu-id="2c0f6-142">Proprietà Report.Language.</span><span class="sxs-lookup"><span data-stu-id="2c0f6-142">The Report.Language property.</span></span>  
  
 <span data-ttu-id="2c0f6-143">Per altre informazioni, vedere [Riferimento a funzioni di aggregazione &#40;Generatore report e SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) e [Ambito di espressioni per totali, aggregazioni e raccolte predefinite &#40;Generatore report e SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="2c0f6-143">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) and [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2c0f6-144">Esempio</span><span class="sxs-lookup"><span data-stu-id="2c0f6-144">Example</span></span>  
 <span data-ttu-id="2c0f6-145">Nell'esempio seguente, si supponga che la tabella sia associata a un set di dati che include un identificatore del territorio di vendita TerritoryGroupID.</span><span class="sxs-lookup"><span data-stu-id="2c0f6-145">In the following example, assume the table is bound to a dataset that includes a sales territory identifier TerritoryGroupID.</span></span> <span data-ttu-id="2c0f6-146">Un set di dati separato denominato "Stores" contiene l'elenco di tutti i negozi di un territorio e include l'ID dell'identificatore del territorio e il nome del negozio StoreName.</span><span class="sxs-lookup"><span data-stu-id="2c0f6-146">A separate dataset called "Stores" contains the list of all stores in a territory and includes the territory identifier ID and the name of the store StoreName.</span></span>  
  
 <span data-ttu-id="2c0f6-147">Nell'espressione seguente, `LookupSet` confronta il valore TerritoryGroupID con ID per ogni riga nel set di dati denominato "Stores".</span><span class="sxs-lookup"><span data-stu-id="2c0f6-147">In the following expression, `LookupSet` compares the value TerritoryGroupID to ID for each row in the dataset called "Stores".</span></span> <span data-ttu-id="2c0f6-148">Per ogni corrispondenza, il valore del campo StoreName per quella riga viene aggiunto al set di risultati.</span><span class="sxs-lookup"><span data-stu-id="2c0f6-148">For each match, the value of the StoreName field for that row is added to the result set.</span></span>  
  
```  
=LookupSet(Fields!TerritoryGroupID.Value, Fields!ID.Value, Fields!StoreName.Value, "Stores")  
```  
  
## <a name="example"></a><span data-ttu-id="2c0f6-149">Esempio</span><span class="sxs-lookup"><span data-stu-id="2c0f6-149">Example</span></span>  
 <span data-ttu-id="2c0f6-150">Poiché tramite `LookupSet` viene restituita una raccolta di oggetti, non è possibile visualizzare direttamente l'espressione di risultato in una casella di testo.</span><span class="sxs-lookup"><span data-stu-id="2c0f6-150">Because `LookupSet` returns a collection of objects, you cannot display the result expression directly in a text box.</span></span> <span data-ttu-id="2c0f6-151">È possibile concatenare il valore di ogni oggetto nella raccolta come stringa.</span><span class="sxs-lookup"><span data-stu-id="2c0f6-151">You can concatenate the value of each object in the collection as a string.</span></span>  
  
 <span data-ttu-id="2c0f6-152">Usare la funzione `Join` di [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] per creare una stringa delimitata da un set di oggetti.</span><span class="sxs-lookup"><span data-stu-id="2c0f6-152">Use the [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] function `Join` create a delimited string from a set of objects.</span></span> <span data-ttu-id="2c0f6-153">Usare una virgola come separatore per combinare gli oggetti in un'unica riga.</span><span class="sxs-lookup"><span data-stu-id="2c0f6-153">Use a comma as a separator to combine the objects in a single line.</span></span> <span data-ttu-id="2c0f6-154">In alcuni renderer, è possibile usare un avanzamento riga di [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] (`vbCrLF`) come separatore per elencare ogni valore su una nuova riga.</span><span class="sxs-lookup"><span data-stu-id="2c0f6-154">In some renderers, you might use a [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] line feed (`vbCrLF`) as a separator to list each value on a new line.</span></span>  
  
 <span data-ttu-id="2c0f6-155">L'espressione seguente, quando viene usata come proprietà Value per una casella di testo, USA `Join` per creare un elenco.</span><span class="sxs-lookup"><span data-stu-id="2c0f6-155">The following expression, when it is used as the Value property for a text box, uses `Join` to create a list.</span></span>  
  
```  
=Join(LookupSet(Fields!TerritoryGroupID.Value, Fields!ID.Value, Fields!StoreName.Value, "Stores"),",")  
```  
  
## <a name="example"></a><span data-ttu-id="2c0f6-156">Esempio</span><span class="sxs-lookup"><span data-stu-id="2c0f6-156">Example</span></span>  
 <span data-ttu-id="2c0f6-157">Per caselle di testo che eseguono il rendering solo poche volte, è possibile scegliere di aggiungere un codice personalizzato per generare HTML per visualizzare i valori in una casella di testo.</span><span class="sxs-lookup"><span data-stu-id="2c0f6-157">For text boxes that only render a few times, you might choose to add custom code to generate HTML to display values in a text box.</span></span> <span data-ttu-id="2c0f6-158">HTML in una casella di testo richiede altri processi di elaborazione, pertanto non è consigliabile per una casella di testo che viene sottoposta a rendering molte volte.</span><span class="sxs-lookup"><span data-stu-id="2c0f6-158">HTML in a text box requires extra processing, so this would not be a good choice for a text box that is rendered thousands of times.</span></span>  
  
 <span data-ttu-id="2c0f6-159">Copiare le seguenti funzioni di [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] in un blocco di codice di una definizione del report.</span><span class="sxs-lookup"><span data-stu-id="2c0f6-159">Copy the following [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] functions to a Code block in a report definition.</span></span> <span data-ttu-id="2c0f6-160">**MakeList** accetta la matrice di oggetti restituita in *result_expression* e compila un elenco non ordinato usando tag HTML.</span><span class="sxs-lookup"><span data-stu-id="2c0f6-160">**MakeList** takes the object array that is returned in *result_expression* and builds an unordered list by using HTML tags.</span></span> <span data-ttu-id="2c0f6-161">**Length** restituisce il numero di elementi della matrice di oggetti.</span><span class="sxs-lookup"><span data-stu-id="2c0f6-161">**Length** returns the number of items in the object array.</span></span>  
  
```  
Function MakeList(ByVal items As Object()) As String  
   If items Is Nothing Then  
      Return Nothing  
   End If  
  
   Dim builder As System.Text.StringBuilder =   
      New System.Text.StringBuilder()  
   builder.Append("<ul>")  
  
   For Each item As Object In items  
      builder.Append("<li>")  
      builder.Append(item)  
   Next  
   builder.Append("</ul>")  
  
   Return builder.ToString()  
End Function  
  
Function Length(ByVal items as Object()) as Integer  
   If items is Nothing Then  
      Return 0  
   End If  
   Return items.Length  
End Function  
```  
  
## <a name="example"></a><span data-ttu-id="2c0f6-162">Esempio</span><span class="sxs-lookup"><span data-stu-id="2c0f6-162">Example</span></span>  
 <span data-ttu-id="2c0f6-163">Per generare HTML, è necessario chiamare la funzione.</span><span class="sxs-lookup"><span data-stu-id="2c0f6-163">To generate the HTML, you must call the function.</span></span> <span data-ttu-id="2c0f6-164">Incollare l'espressione seguente nella proprietà Value per la casella di testo e impostare il tipo di markup per il testo su HTML.</span><span class="sxs-lookup"><span data-stu-id="2c0f6-164">Paste the following expression in the Value property for the text box and set the markup type for text to HTML.</span></span> <span data-ttu-id="2c0f6-165">Per altre informazioni, vedere [Aggiungere codice HTML a un report &#40;Generatore report e SSRS&#41;](add-html-into-a-report-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="2c0f6-165">For more information, see [Add HTML into a Report &#40;Report Builder and SSRS&#41;](add-html-into-a-report-report-builder-and-ssrs.md).</span></span>  
  
```  
=Code.MakeList(LookupSet(Fields!TerritoryGroupID.Value, Fields!ID.Value, Fields!StoreName.Value, "Stores"))  
```  
  
## <a name="see-also"></a><span data-ttu-id="2c0f6-166">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2c0f6-166">See Also</span></span>  
 <span data-ttu-id="2c0f6-167">[Utilizzo delle espressioni nei report &#40;Generatore report e SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2c0f6-167">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="2c0f6-168">[Esempi di espressioni &#40;Generatore report e SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2c0f6-168">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="2c0f6-169">[Tipi di dati nelle espressioni &#40;Generatore report e SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2c0f6-169">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="2c0f6-170">Ambito di espressioni per totali, aggregazioni e raccolte predefinite &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="2c0f6-170">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
