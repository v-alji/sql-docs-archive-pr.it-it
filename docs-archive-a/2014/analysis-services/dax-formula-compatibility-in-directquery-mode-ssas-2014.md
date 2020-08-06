---
title: Compatibilità delle formule DAX in modalità DirectQuery (SSAS 2014) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: de83cfa9-9ffe-4e24-9c74-96a3876cb4bd
author: minewiskan
ms.author: owend
ms.openlocfilehash: acaac82d6930787a45281c0e942def8df764f4f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627524"
---
# <a name="dax-formula-compatibility-in-directquery-mode-ssas-2014"></a><span data-ttu-id="60eaf-102">Compatibilità delle formule DAX in modalità DirectQuery (SSAS 2014)</span><span class="sxs-lookup"><span data-stu-id="60eaf-102">DAX Formula Compatibility in DirectQuery Mode (SSAS 2014)</span></span>
<span data-ttu-id="60eaf-103">Data Analysis Expression Language (DAX) può essere utilizzato per creare misure e altre formule personalizzate da utilizzare in Analysis Services modelli tabulari, [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] modelli di dati in cartelle di lavoro di Excel e modelli di dati Power bi desktop.</span><span class="sxs-lookup"><span data-stu-id="60eaf-103">The Data Analysis Expression language (DAX) can be used to create measures and other custom formulas for use in Analysis Services Tabular models, [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] data models in Excel workbooks, and Power BI Desktop data models.</span></span> <span data-ttu-id="60eaf-104">Nella maggior parte dei casi, i modelli creati in questi ambienti sono identici ed è possibile usare le stesse misure, le stesse relazioni e gli indicatori KPI e così via. Tuttavia, se si crea un modello tabulare Analysis Services e lo si distribuisce in modalità DirectQuery, esistono alcune restrizioni per le formule che è possibile utilizzare.</span><span class="sxs-lookup"><span data-stu-id="60eaf-104">In most respects, the models you create in these environments are identical, and you can use the same measures, relationships, and KPIs, etc. However, if you author an Analysis Services Tabular model and deploy it in DirectQuery mode, there are some restrictions on the formulas that you can use.</span></span> <span data-ttu-id="60eaf-105">Questo argomento fornisce una panoramica di tali differenze, elenca le funzioni che non sono supportate nel modello tabulare di SQL Server 2014 Analysis Services a livello di compatibilità 1100 o 1103 e in modalità DirectQuery ed elenca le funzioni supportate, ma che potrebbero restituire risultati diversi.</span><span class="sxs-lookup"><span data-stu-id="60eaf-105">This topic provides an overview of those differences, lists the functions that are not supported in SQL Server 2014 Analysis Services tabulars model at compatibility level 1100 or 1103 and in DirectQuery mode, and lists the functions that are supported but might return different results.</span></span>  
  
<span data-ttu-id="60eaf-106">In questo argomento viene usato il termine *modello in memoria* per fare riferimento a modelli tabulari, che sono dati memorizzati nella cache in memoria completamente ospitati in un server Analysis Services in esecuzione in modalità tabulare.</span><span class="sxs-lookup"><span data-stu-id="60eaf-106">Within this topic, we use the term *in-memory model* to refer to  Tabular models, which are fully hosted in-memory cached data on an Analysis Services server running in Tabular mode.</span></span> <span data-ttu-id="60eaf-107">I *modelli DirectQuery* vengono usati per fare riferimento a modelli tabulari che sono stati creati e/o distribuiti in modalità DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="60eaf-107">We use *DirectQuery models* to refer to Tabular models that have been authored and/or deployed in DirectQuery mode.</span></span> <span data-ttu-id="60eaf-108">Per informazioni sulla modalità DirectQuery, vedere [modalità DirectQuery (SSAS tabulare)](https://msdn.microsoft.com/45ad2965-05ec-4fb1-a164-d8060b562ea5).</span><span class="sxs-lookup"><span data-stu-id="60eaf-108">For information about DirectQuery mode, see [DirectQuery Mode (SSAS Tabular)](https://msdn.microsoft.com/45ad2965-05ec-4fb1-a164-d8060b562ea5).</span></span>  
  
  
## <a name="differences-between-in-memory-and-directquery-mode"></a><a name="bkmk_SemanticDifferences"></a><span data-ttu-id="60eaf-109">Differenze tra la modalità in memoria e la modalità DirectQuery</span><span class="sxs-lookup"><span data-stu-id="60eaf-109">Differences between in-memory and DirectQuery mode</span></span>  
<span data-ttu-id="60eaf-110">Le query eseguite su un modello distribuito nella modalità DirectQuery possono restituire risultati differenti se eseguite sullo stesso modello distribuito nella modalità in memoria.</span><span class="sxs-lookup"><span data-stu-id="60eaf-110">Queries on a model deployed in DirectQuery mode can return different results than the same model deployed in in-memory mode.</span></span> <span data-ttu-id="60eaf-111">Questo perché con DirectQuery viene eseguita una query sui dati direttamente da un archivio dati relazionale e le aggregazioni richieste dalle formule vengono eseguite utilizzando il motore relazionale pertinente, anziché utilizzare il motore di analisi in memoria xVelocity (VertiPaq) per l'archiviazione e il calcolo.</span><span class="sxs-lookup"><span data-stu-id="60eaf-111">This is because with DirectQuery, data is queried directly from a relational data store and aggregations required by formulas are performed using the relevant relational engine, rather than using the xVelocity in-memory analytics engine (VertiPaq) for storage and calculation.</span></span>  
  
<span data-ttu-id="60eaf-112">Ad esempio, esistono differenze nel modo in cui alcuni archivi dati relazionali gestiscono i valori numerici, le date, i valori Null e così via.</span><span class="sxs-lookup"><span data-stu-id="60eaf-112">For example, there are differences in the way that certain relational data stores handle numeric values, dates, nulls, and so forth.</span></span>  
  
<span data-ttu-id="60eaf-113">Al contrario, il linguaggio DAX deve emulare il più possibile il comportamento delle funzioni di Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="60eaf-113">In contrast, the DAX language is intended to emulate as closely as possible the behavior of functions in Microsoft Excel.</span></span> <span data-ttu-id="60eaf-114">Ad esempio, per gestire valori Null, stringhe vuote e valori zero, Excel tenta di fornire la risposta migliore, a prescindere dal tipo di dati preciso, di conseguenza anche il motore xVelocity terrà lo stesso comportamento.</span><span class="sxs-lookup"><span data-stu-id="60eaf-114">For example, when handling nulls, empty strings and zero values, Excel attempts to provide the best answer regardless of the precise data type, and therefore the xVelocity engine does the same.</span></span> <span data-ttu-id="60eaf-115">Tuttavia, quando un modello tabulare viene distribuito nella modalità DirectQuery e le formule vengono passate a un'origine dati relazionale per la valutazione, i dati devono essere gestiti in base alla semantica dell'origine dati relazionale che in genere prevede una gestione separata delle stringhe vuote rispetto a quelle null.</span><span class="sxs-lookup"><span data-stu-id="60eaf-115">However, when a tabular model is deployed in DirectQuery mode and passes formulas to a relational data source for evaluation, the data must be handled according to the semantics of the relational data source, which typically require distinct handling of empty strings vs. nulls.</span></span> <span data-ttu-id="60eaf-116">Per questo motivo, la stessa formula potrebbe restituire un risultato diverso se valutata rispetto ai dati memorizzati nella cache e rispetto ai dati restituiti solo dall'archivio relazionale.</span><span class="sxs-lookup"><span data-stu-id="60eaf-116">For this reason, the same formula might return a different result when evaluated against cached data and against data returned solely from the relational store.</span></span>  
  
<span data-ttu-id="60eaf-117">Inoltre, alcune funzioni non possono essere utilizzate nella modalità DirectQuery perché il calcolo richiederebbe l'invio dei dati nel contesto corrente all'origine dati relazionale come parametro.</span><span class="sxs-lookup"><span data-stu-id="60eaf-117">Additionally, some functions cannot be used at all in DirectQuery mode because the calculation would require the data in the current context be sent to the relational data source as a parameter.</span></span> <span data-ttu-id="60eaf-118">Le misure di una cartella di lavoro, ad esempio, [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] utilizzano spesso funzioni di business intelligence che fanno riferimento a intervalli di date disponibili all'interno della cartella di lavoro.</span><span class="sxs-lookup"><span data-stu-id="60eaf-118">For example, measures in a [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] workbook often use time-intelligence functions that reference date ranges available within the workbook.</span></span> <span data-ttu-id="60eaf-119">Tali formule non possono in genere essere utilizzate nella modalità DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="60eaf-119">Such formulas generally cannot be used in DirectQuery mode.</span></span>  
  
## <a name="semantic-differences"></a><span data-ttu-id="60eaf-120">Differenze semantiche</span><span class="sxs-lookup"><span data-stu-id="60eaf-120">Semantic differences</span></span>  
<span data-ttu-id="60eaf-121">In questa sezione sono elencati i tipi di differenze semantiche che potrebbero verificarsi e vengono descritte le limitazioni che potrebbero applicarsi all'utilizzo di funzioni o ai risultati delle query.</span><span class="sxs-lookup"><span data-stu-id="60eaf-121">This section lists the types of semantic differences that you can expect, and describes any limitations that might apply to the usage of functions or to query results.</span></span>  
  
### <a name="comparisons"></a><a name="bkmk_Comparisons"></a><span data-ttu-id="60eaf-122">Confronti</span><span class="sxs-lookup"><span data-stu-id="60eaf-122">Comparisons</span></span>  
<span data-ttu-id="60eaf-123">Il linguaggio DAX nei modelli in memoria supporta i confronti di due espressioni risolvibili in valori scalari di tipi di dati diversi.</span><span class="sxs-lookup"><span data-stu-id="60eaf-123">DAX in in-memory models support comparisons of two expressions that resolve to scalar values of different data types.</span></span> <span data-ttu-id="60eaf-124">Tuttavia, i modelli distribuiti nella modalità DirectQuery utilizzano i tipi di dati e gli operatori di confronto del motore relazionale, pertanto potrebbero restituire risultati diversi.</span><span class="sxs-lookup"><span data-stu-id="60eaf-124">However, models that are deployed in DirectQuery mode use the data types and comparison operators of the relational engine, and therefore might return different results.</span></span>  
  
<span data-ttu-id="60eaf-125">I confronti seguenti restituiscono sempre un errore quando vengono usati in un calcolo su un'origine dati DirectQuery:</span><span class="sxs-lookup"><span data-stu-id="60eaf-125">The following comparisons will always return an error when used in a calculation on a DirectQuery data source:</span></span>  
  
-   <span data-ttu-id="60eaf-126">Tipo di dati numerico confrontato a un qualsiasi tipo di dati stringa</span><span class="sxs-lookup"><span data-stu-id="60eaf-126">Numeric data type compared to any string data type</span></span>  
  
-   <span data-ttu-id="60eaf-127">Tipo di dati numerico confrontato a un valore booleano</span><span class="sxs-lookup"><span data-stu-id="60eaf-127">Numeric data type compared to a Boolean value</span></span>  
  
-   <span data-ttu-id="60eaf-128">Qualsiasi tipo di dati stringa confrontato a un valore booleano</span><span class="sxs-lookup"><span data-stu-id="60eaf-128">Any string data type compared to a Boolean value</span></span>  
  
<span data-ttu-id="60eaf-129">In generale, il linguaggio DAX tollera meglio le mancate corrispondenze tra tipi di dati nei modelli in memoria e tenta fino a due volte un cast implicito dei valori, come descritto in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="60eaf-129">In general, DAX is more forgiving of data type mismatches in in-memory models and will attempt an implicit cast of values up to two times, as described in this section.</span></span> <span data-ttu-id="60eaf-130">Tuttavia, le formule inviate a un archivio dati relazionale in modalità DirectQuery vengono valutate in modo più rigoroso, in base alle regole del motore relazionale ed è più probabile che abbiano esito negativo.</span><span class="sxs-lookup"><span data-stu-id="60eaf-130">However, formulas sent to a relational data store in DirectQuery mode are evaluated more strictly, following the rules of the relational engine, and are more likely to fail.</span></span>  
  
<span data-ttu-id="60eaf-131">**Confronti tra stringhe e numeri**</span><span class="sxs-lookup"><span data-stu-id="60eaf-131">**Comparisons of strings and numbers**</span></span>  
<span data-ttu-id="60eaf-132">ESEMPIO: `"2" < 3`</span><span class="sxs-lookup"><span data-stu-id="60eaf-132">EXAMPLE: `"2" < 3`</span></span>  
  
<span data-ttu-id="60eaf-133">La formula confronta una stringa di testo a un numero.</span><span class="sxs-lookup"><span data-stu-id="60eaf-133">The formula compares a text string to a number.</span></span> <span data-ttu-id="60eaf-134">L'espressione è **true** sia in modalità DirectQuery sia nei modelli in memoria.</span><span class="sxs-lookup"><span data-stu-id="60eaf-134">The expression is **true** in both DirectQuery mode and in-memory models.</span></span>  
  
<span data-ttu-id="60eaf-135">In un modello in memoria, il risultato è **true** perché viene eseguito il cast implicito dei numeri come stringhe a un tipo di dati numerico per confronti con altri numeri.</span><span class="sxs-lookup"><span data-stu-id="60eaf-135">In an in-memory model, the result is **true** because numbers as strings are implicitly cast to a numerical data type for comparisons with other numbers.</span></span> <span data-ttu-id="60eaf-136">SQL prevede inoltre il cast implicito di numeri di testo come numeri per il confronto con tipi di dati numerici.</span><span class="sxs-lookup"><span data-stu-id="60eaf-136">SQL also implicitly casts text numbers as numbers for comparison to numerical data types.</span></span>  
  
<span data-ttu-id="60eaf-137">Si noti che questo rappresenta una modifica del comportamento dalla prima versione di [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] , che restituisce **false**, perché il testo "2" verrebbe sempre considerato maggiore di qualsiasi numero.</span><span class="sxs-lookup"><span data-stu-id="60eaf-137">Note that this represents a change in behavior from the first version of [!INCLUDE[ssGemini](../includes/ssgemini-md.md)], which would return **false**, because the text "2" would always be considered larger than any number.</span></span>  
  
<span data-ttu-id="60eaf-138">**Confronto tra valori di testo e valori booleani**</span><span class="sxs-lookup"><span data-stu-id="60eaf-138">**Comparison of text with Boolean**</span></span>  
<span data-ttu-id="60eaf-139">ESEMPIO: `"VERDADERO" = TRUE`</span><span class="sxs-lookup"><span data-stu-id="60eaf-139">EXAMPLE: `"VERDADERO" = TRUE`</span></span>  
  
<span data-ttu-id="60eaf-140">Questa espressione confronta una stringa di testo a un valore booleano.</span><span class="sxs-lookup"><span data-stu-id="60eaf-140">This expression compares a text string with a Boolean value.</span></span> <span data-ttu-id="60eaf-141">In generale, per i modelli DirectQuery o in memoria, il confronto tra un valore stringa e un valore booleano genera un errore.</span><span class="sxs-lookup"><span data-stu-id="60eaf-141">In general, for DirectQuery or In-Memory models, comparing a string value to a Boolean value results in an error.</span></span> <span data-ttu-id="60eaf-142">Le uniche eccezioni alla regola si hanno quando la stringa contiene la parola **true** o **false**; se la stringa contiene valori true o false, viene convertita in valore booleano e il confronto restituisce il risultato logico.</span><span class="sxs-lookup"><span data-stu-id="60eaf-142">The only exceptions to the rule are when the string contains the word **true** or the word **false**; if the string contains any of true or false values, a conversion to Boolean is made and the comparison takes place giving the logical result.</span></span>  
  
<span data-ttu-id="60eaf-143">**Confronto tra valori Null**</span><span class="sxs-lookup"><span data-stu-id="60eaf-143">**Comparison of nulls**</span></span>  
<span data-ttu-id="60eaf-144">ESEMPIO: `EVALUATE ROW("X", BLANK() = BLANK())`</span><span class="sxs-lookup"><span data-stu-id="60eaf-144">EXAMPLE: `EVALUATE ROW("X", BLANK() = BLANK())`</span></span>  
  
<span data-ttu-id="60eaf-145">Questa formula confronta l'equivalente SQL di un valore Null a un valore Null.</span><span class="sxs-lookup"><span data-stu-id="60eaf-145">This formula compares the SQL equivalent of a null to a null.</span></span> <span data-ttu-id="60eaf-146">Restituisce **true** nei modelli in memoria e DirectQuery; nel modello DirectQuery un provisioning garantisce un comportamento simile al modello in memoria.</span><span class="sxs-lookup"><span data-stu-id="60eaf-146">It returns **true** in in-memory and DirectQuery models; a provision is made in DirectQuery model to guarantee similar behavior to in-memory model.</span></span>  
  
<span data-ttu-id="60eaf-147">Si noti che in Transact-SQL un valore Null non è mai uguale a un valore Null.</span><span class="sxs-lookup"><span data-stu-id="60eaf-147">Note that in Transact-SQL, a null is never equal to a null.</span></span> <span data-ttu-id="60eaf-148">Tuttavia, nel linguaggio DAX uno spazio vuoto è uguale a un altro spazio vuoto.</span><span class="sxs-lookup"><span data-stu-id="60eaf-148">However, in DAX, a blank is equal to another blank.</span></span> <span data-ttu-id="60eaf-149">Questo comportamento rimane invariato per tutti i modelli in memoria.</span><span class="sxs-lookup"><span data-stu-id="60eaf-149">This behavior is the same for all in-memory models.</span></span> <span data-ttu-id="60eaf-150">È importante notare che la modalità DirectQuery utilizza la maggior parte della semantica di SQL Server, anche se in questo caso si distingue fornendo un nuovo comportamento per i confronti NULL.</span><span class="sxs-lookup"><span data-stu-id="60eaf-150">It is important to note that DirectQuery mode uses, most of, the semantics of SQL Server; but, in this case it separates from it giving a new behavior to NULL comparisons.</span></span>  
  
### <a name="casts"></a><a name="bkmk_Casts"></a><span data-ttu-id="60eaf-151">Cast</span><span class="sxs-lookup"><span data-stu-id="60eaf-151">Casts</span></span>  
  
<span data-ttu-id="60eaf-152">Il linguaggio DAX non prevede alcuna funzione cast di questo tipo, tuttavia i cast impliciti vengono eseguiti in molte operazioni aritmetiche e di confronto.</span><span class="sxs-lookup"><span data-stu-id="60eaf-152">There is no cast function as such in DAX, but implicit casts are performed in many comparison and arithmetic operations.</span></span> <span data-ttu-id="60eaf-153">È l'operazione aritmetica o di confronto a determinare il tipo di dati del risultato.</span><span class="sxs-lookup"><span data-stu-id="60eaf-153">It is the comparison or arithmetic operation that determines the data type of the result.</span></span> <span data-ttu-id="60eaf-154">ad esempio:</span><span class="sxs-lookup"><span data-stu-id="60eaf-154">For example,</span></span>  
  
-   <span data-ttu-id="60eaf-155">I valori booleani vengono trattati come valori numerici nelle operazioni aritmetiche, ad esempio TRUE + 1 o la funzione MIN applicata a una colonna di valori booleani.</span><span class="sxs-lookup"><span data-stu-id="60eaf-155">Boolean values are treated as numeric in arithmetic operations, such as TRUE + 1, or the function MIN applied to a column of Boolean values.</span></span> <span data-ttu-id="60eaf-156">Anche un'operazione NOT restituisce un valore numerico.</span><span class="sxs-lookup"><span data-stu-id="60eaf-156">A NOT operation also returns a numeric value.</span></span>  
  
-   <span data-ttu-id="60eaf-157">I valori booleani vengono sempre trattati come valori logici nei confronti e quando vengono usati con EXACT, AND, OR, &amp;&amp;o ||.</span><span class="sxs-lookup"><span data-stu-id="60eaf-157">Boolean values are always treated as logical values in comparisons and when used with EXACT, AND, OR, &amp;&amp;, or ||.</span></span>  
  
<span data-ttu-id="60eaf-158">**Cast di una stringa a un valore booleano**</span><span class="sxs-lookup"><span data-stu-id="60eaf-158">**Cast from string to Boolean**</span></span>  
<span data-ttu-id="60eaf-159">Nei modelli in memoria e DirectQuery i cast sono consentiti solo a valori booleani da queste stringhe: **""** (stringa vuota), **"true"**, **"false"**; dove viene eseguito il cast di una stringa vuota a un valore false.</span><span class="sxs-lookup"><span data-stu-id="60eaf-159">In in-memory and DirectQuery models, casts are permitted to Boolean values from these strings only: **""** (empty string), **"true"**, **"false"**; where an empty string casts to false value.</span></span>  
  
<span data-ttu-id="60eaf-160">Il cast a un tipo di dati booleano di qualsiasi altra stringa genera un errore.</span><span class="sxs-lookup"><span data-stu-id="60eaf-160">Casts to the Boolean data type of any other string results in an error.</span></span>  
  
<span data-ttu-id="60eaf-161">**Cast da stringa a data/ora**</span><span class="sxs-lookup"><span data-stu-id="60eaf-161">**Cast from string to date/time**</span></span>  
<span data-ttu-id="60eaf-162">Nella modalità DirectQuery i cast da rappresentazioni stringa di date e ore a valori **datetime** effettivi si comportano come in SQL Server.</span><span class="sxs-lookup"><span data-stu-id="60eaf-162">In DirectQuery mode, casts from string representations of dates and times to actual **datetime** values behave the same way as they do in SQL Server.</span></span>  
  
<span data-ttu-id="60eaf-163">Per informazioni sulle regole che regolano i cast dai tipi di dati stringa a **DateTime** nei [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] modelli, vedere la Guida di [riferimento alla sintassi DAX](/dax/dax-syntax-reference).</span><span class="sxs-lookup"><span data-stu-id="60eaf-163">For information about the rules governing casts from string to **datetime** data types in [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] models, see the [DAX Syntax Reference](/dax/dax-syntax-reference).</span></span>
  
<span data-ttu-id="60eaf-164">I modelli che utilizzano l'archivio dati in memoria supportano una gamma più limitata di formati di testo per le date rispetto ai formati stringa per date supportati in SQL Server.</span><span class="sxs-lookup"><span data-stu-id="60eaf-164">Models that use the in-memory data store support a more limited range of text formats for dates than the string formats for dates that are supported by SQL Server.</span></span> <span data-ttu-id="60eaf-165">Tuttavia, il linguaggio DAX supporta formati data e ora personalizzati.</span><span class="sxs-lookup"><span data-stu-id="60eaf-165">However, DAX supports custom date and time formats.</span></span>  
  
<span data-ttu-id="60eaf-166">**Cast da stringa ad altri valori non booleani**</span><span class="sxs-lookup"><span data-stu-id="60eaf-166">**Cast from string to other non Boolean values**</span></span>  
<span data-ttu-id="60eaf-167">In caso di cast da stringhe a valori non booleani, la modalità DirectQuery si comporta come SQL Server.</span><span class="sxs-lookup"><span data-stu-id="60eaf-167">When casting from strings to non-Boolean values, DirectQuery mode behaves the same as SQL Server.</span></span> <span data-ttu-id="60eaf-168">Per altre informazioni, vedere [CAST e CONVERT (Transact-SQL)](https://msdn.microsoft.com/a87d0850-c670-4720-9ad5-6f5a22343ea8).</span><span class="sxs-lookup"><span data-stu-id="60eaf-168">For more information, see [CAST and CONVERT (Transact-SQL)](https://msdn.microsoft.com/a87d0850-c670-4720-9ad5-6f5a22343ea8).</span></span>  
  
<span data-ttu-id="60eaf-169">**Cast da numeri a stringa non consentito**</span><span class="sxs-lookup"><span data-stu-id="60eaf-169">**Cast from numbers to string not allowed**</span></span>  
<span data-ttu-id="60eaf-170">ESEMPIO: `CONCATENATE(102,",345")`</span><span class="sxs-lookup"><span data-stu-id="60eaf-170">EXAMPLE: `CONCATENATE(102,",345")`</span></span>  
  
<span data-ttu-id="60eaf-171">Il cast da numeri a stringhe non è consentito in SQL Server.</span><span class="sxs-lookup"><span data-stu-id="60eaf-171">Casting from numbers to strings is not allowed in SQL Server.</span></span>  
  
<span data-ttu-id="60eaf-172">Questa formula restituisce un errore nei modelli tabulari e nella modalità DirectQuery, ma produce un risultato in [!INCLUDE[ssGemini](../includes/ssgemini-md.md)].</span><span class="sxs-lookup"><span data-stu-id="60eaf-172">This formula returns an error in tabular models and in DirectQuery mode; however, the formula produces a result in [!INCLUDE[ssGemini](../includes/ssgemini-md.md)].</span></span>  
  
<span data-ttu-id="60eaf-173">**Cast a due tentativi non supportato in DirectQuery**</span><span class="sxs-lookup"><span data-stu-id="60eaf-173">**No support for two-try casts in DirectQuery**</span></span>  
<span data-ttu-id="60eaf-174">I modelli in memoria spesso tentano un secondo cast se il primo ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="60eaf-174">In-memory models often attempt a second cast when the first one fails.</span></span> <span data-ttu-id="60eaf-175">Questo non si verifica mai nella modalità DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="60eaf-175">This never happens in DirectQuery mode.</span></span>  
  
<span data-ttu-id="60eaf-176">ESEMPIO: `TODAY() + "13:14:15"`</span><span class="sxs-lookup"><span data-stu-id="60eaf-176">EXAMPLE: `TODAY() + "13:14:15"`</span></span>  
  
<span data-ttu-id="60eaf-177">In questa espressione il primo parametro presenta il tipo **datetime** e il secondo il tipo **string**.</span><span class="sxs-lookup"><span data-stu-id="60eaf-177">In this expression, the first parameter has type **datetime** and second parameter has type **string**.</span></span> <span data-ttu-id="60eaf-178">Tuttavia, quando gli operandi vengono combinati i cast vengono gestiti in modo diverso.</span><span class="sxs-lookup"><span data-stu-id="60eaf-178">However, the casts when combining the operands are handled differently.</span></span> <span data-ttu-id="60eaf-179">Il linguaggio DAX esegue un cast implicito da **string** a **double**.</span><span class="sxs-lookup"><span data-stu-id="60eaf-179">DAX will perform an implicit cast from **string** to **double**.</span></span> <span data-ttu-id="60eaf-180">Nei modelli in memoria il motore delle formule tenta di eseguire il cast direttamente a **double**e, se ha esito negativo, tenta di eseguire il cast della stringa a **datetime**.</span><span class="sxs-lookup"><span data-stu-id="60eaf-180">In in-memory models, the formula engine attempts to cast directly to **double**, and if that fails, it will try to cast the string to **datetime**.</span></span>  
  
<span data-ttu-id="60eaf-181">Nella modalità DirectQuery verrà applicato solo il cast diretto da **string** a **double** .</span><span class="sxs-lookup"><span data-stu-id="60eaf-181">In DirectQuery mode, only the direct cast from **string** to **double** will be applied.</span></span> <span data-ttu-id="60eaf-182">Se questo cast ha esito negativo, la formula restituisce un errore.</span><span class="sxs-lookup"><span data-stu-id="60eaf-182">If this cast fails, the formula will return an error.</span></span>  
  
### <a name="math-functions-and-arithmetic-operations"></a><a name="bkmk_Math"></a><span data-ttu-id="60eaf-183">Funzioni matematiche e operazioni aritmetiche</span><span class="sxs-lookup"><span data-stu-id="60eaf-183">Math functions and arithmetic operations</span></span>  
<span data-ttu-id="60eaf-184">Alcune funzioni matematiche restituiscono risultati diversi nella modalità DirectQuery a causa delle differenze nel tipo di dati sottostante o nei cast che possono essere applicati nelle operazioni.</span><span class="sxs-lookup"><span data-stu-id="60eaf-184">Some mathematical functions will return different results in DirectQuery mode because of differences in the underlying data type or the casts that can be applied in operations.</span></span> <span data-ttu-id="60eaf-185">Inoltre, le limitazioni descritte in precedenza sull'intervallo di valori consentito potrebbero influire sul risultato delle operazioni aritmetiche.</span><span class="sxs-lookup"><span data-stu-id="60eaf-185">Also, the restrictions described above on the allowed range of values might affect the outcome of arithmetic operations.</span></span>  
  
<span data-ttu-id="60eaf-186">**Ordine di addizione**</span><span class="sxs-lookup"><span data-stu-id="60eaf-186">**Order of addition**</span></span>  
<span data-ttu-id="60eaf-187">Quando si crea una formula per aggiungere una serie di numeri, un modello in memoria potrebbe elaborare i numeri in un ordine diverso rispetto a un modello DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="60eaf-187">When you create a formula that adds a series of numbers, an in-memory model might process the numbers in a different order than a DirectQuery model.</span></span>  <span data-ttu-id="60eaf-188">Di conseguenza, quando si dispone di molti numeri positivi elevati e di numeri negativi molto elevati, è possibile che un'operazione restituisca un errore e un'altra dei risultati.</span><span class="sxs-lookup"><span data-stu-id="60eaf-188">Therefore, when you have many very large positive numbers and very large negative numbers, you may get an error in one operation and results in another operation.</span></span>  
  
<span data-ttu-id="60eaf-189">**Utilizzo della funzione POWER**</span><span class="sxs-lookup"><span data-stu-id="60eaf-189">**Use of the POWER function**</span></span>  
<span data-ttu-id="60eaf-190">ESEMPIO: `POWER(-64, 1/3)`</span><span class="sxs-lookup"><span data-stu-id="60eaf-190">EXAMPLE: `POWER(-64, 1/3)`</span></span>  
  
<span data-ttu-id="60eaf-191">Nella modalità DirectQuery la funzione POWER non può utilizzare valori negativi come base se viene elevata a un esponente frazionario.</span><span class="sxs-lookup"><span data-stu-id="60eaf-191">In DirectQuery mode, the POWER function cannot use negative values as the base when raised to a fractional exponent.</span></span> <span data-ttu-id="60eaf-192">Si tratta del comportamento previsto in SQL Server.</span><span class="sxs-lookup"><span data-stu-id="60eaf-192">This is the expected behavior in SQL Server.</span></span>  
  
<span data-ttu-id="60eaf-193">In un modello in memoria la formula restituisce -4.</span><span class="sxs-lookup"><span data-stu-id="60eaf-193">In an in-memory model, the formula returns -4.</span></span>  
  
<span data-ttu-id="60eaf-194">**Operazioni di overflow numerico**</span><span class="sxs-lookup"><span data-stu-id="60eaf-194">**Numerical overflow operations**</span></span>  
<span data-ttu-id="60eaf-195">In Transact-SQL le operazioni che generano un overflow numerico restituiscono un errore di overflow. Di conseguenza, le formule che generano un overflow restituiscono un errore nella modalità DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="60eaf-195">In Transact-SQL, operations that result in a numerical overflow return an overflow error; therefore, formulas that result in an overflow also raise an error in DirectQuery mode.</span></span>  
  
<span data-ttu-id="60eaf-196">Tuttavia, la stessa formula, se utilizzata in un modello in memoria, restituisce un numero intero a otto byte</span><span class="sxs-lookup"><span data-stu-id="60eaf-196">However, the same formula when used in an in-memory model returns an eight-byte integer.</span></span> <span data-ttu-id="60eaf-197">perché il motore delle formule non esegue i controlli per gli overflow numerici.</span><span class="sxs-lookup"><span data-stu-id="60eaf-197">That is because the formula engine does not perform checks for numerical overflows.</span></span>  
  
<span data-ttu-id="60eaf-198">**Le funzioni LOG con spazi vuoti restituiscono risultati diversi**</span><span class="sxs-lookup"><span data-stu-id="60eaf-198">**LOG functions with blanks return different results**</span></span>  
<span data-ttu-id="60eaf-199">SQL Server gestisce i valori Null e gli spazi vuoti in modo diverso rispetto al motore xVelocity.</span><span class="sxs-lookup"><span data-stu-id="60eaf-199">SQL Server handles nulls and blanks differently than the xVelocity engine.</span></span> <span data-ttu-id="60eaf-200">Di conseguenza, la formula seguente restituisce un errore nella modalità DirectQuery, ma restituisce Infinity (-inf) in modalità in memoria.</span><span class="sxs-lookup"><span data-stu-id="60eaf-200">As a result, the following formula returns an error in DirectQuery mode, but return infinity (-inf) in in-memory mode.</span></span>  
  
`EXAMPLE: LOG(blank())`  
  
<span data-ttu-id="60eaf-201">Le stesse limitazioni si applicano alle altre funzioni logaritmiche: LOG10 e LN.</span><span class="sxs-lookup"><span data-stu-id="60eaf-201">The same limitations apply to the other logarithmic functions: LOG10 and LN.</span></span>  
  
<span data-ttu-id="60eaf-202">Per altre informazioni sul tipo di dati **blank** in DAX, vedere [Specifica della sintassi DAX per PowerPivot](/dax/dax-syntax-reference).</span><span class="sxs-lookup"><span data-stu-id="60eaf-202">For more information about the **blank** data type in DAX, see [DAX Syntax Reference](/dax/dax-syntax-reference).</span></span>
  
<span data-ttu-id="60eaf-203">**Divisione per 0 e divisione per spazio vuoto**</span><span class="sxs-lookup"><span data-stu-id="60eaf-203">**Division by 0 and division by Blank**</span></span>  
<span data-ttu-id="60eaf-204">Nella modalità DirectQuery la divisione per zero (0) o per BLANK genera sempre un errore.</span><span class="sxs-lookup"><span data-stu-id="60eaf-204">In DirectQuery mode, division by zero (0) or division by BLANK will always result in an error.</span></span> <span data-ttu-id="60eaf-205">SQL Server non supporta la nozione di infinito e poiché il risultato naturale di qualsiasi divisione per 0 è un infinito, il risultato è un errore.</span><span class="sxs-lookup"><span data-stu-id="60eaf-205">SQL Server does not support the notion of infinity, and because the natural result of any division by 0 is infinity, the result is an error.</span></span> <span data-ttu-id="60eaf-206">Tuttavia, SQL Server supporta la divisione per valori Null e il risultato deve sempre essere uguale a Null.</span><span class="sxs-lookup"><span data-stu-id="60eaf-206">However, SQL Server supports division by nulls, and the result must always equal null.</span></span>  
  
<span data-ttu-id="60eaf-207">Anziché restituire risultati diversi per queste operazioni, nella modalità DirectQuery entrambi i tipi di operazioni (divisione per zero e divisione per valore Null) restituiscono un errore.</span><span class="sxs-lookup"><span data-stu-id="60eaf-207">Rather than return different results for these operations, in DirectQuery mode, both types of operations (division by zero and division by null) return an error.</span></span>  
  
<span data-ttu-id="60eaf-208">Si noti che anche nei modelli di Excel e [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] la divisione per zero restituisce un errore.</span><span class="sxs-lookup"><span data-stu-id="60eaf-208">Note that, in Excel and in [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] models, division by zero also returns an error.</span></span> <span data-ttu-id="60eaf-209">La divisione per spazio vuoto restituisce uno spazio vuoto.</span><span class="sxs-lookup"><span data-stu-id="60eaf-209">Division by a blank returns a blank.</span></span>  
  
<span data-ttu-id="60eaf-210">Le espressioni seguenti sono tutte valide nei modelli in memoria, ma generano un errore nella modalità DirectQuery:</span><span class="sxs-lookup"><span data-stu-id="60eaf-210">The following expressions are all valid in in-memory models, but will fail in DirectQuery mode:</span></span>  
  
`1/BLANK`  
  
`1/0`  
  
`0.0/BLANK`  
  
`0/0`  
  
<span data-ttu-id="60eaf-211">L'espressione `BLANK/BLANK` è un caso speciale che restituisce `BLANK` sia per i modelli in memoria sia per quelli in modalità DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="60eaf-211">The expression `BLANK/BLANK` is a special case that returns `BLANK` in both for in-memory models, and in DirectQuery mode.</span></span>  
  
### <a name="supported-numeric-and-date-time-ranges"></a><a name="bkmk_Ranges"></a><span data-ttu-id="60eaf-212">Intervalli numerici e data e ora supportati</span><span class="sxs-lookup"><span data-stu-id="60eaf-212">Supported numeric and date-time ranges</span></span>  
<span data-ttu-id="60eaf-213">Le formule nei [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] modelli tabulari e in memoria sono soggette alle stesse limitazioni di Excel rispetto ai valori massimi consentiti per i numeri reali e le date.</span><span class="sxs-lookup"><span data-stu-id="60eaf-213">Formulas in [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] and tabular models in-memory are subject to the same limitations as Excel with regard to maximum allowed values for real numbers and dates.</span></span> <span data-ttu-id="60eaf-214">Possono tuttavia sorgere delle differenze quando il valore massimo viene restituito da un calcolo o da una query o quando si esegue la conversione, il cast, l'arrotondamento o il troncamento di valori.</span><span class="sxs-lookup"><span data-stu-id="60eaf-214">However, differences can arise when the maximum value is returned from a calculation or query, or when values are converted, cast, rounded, or truncated.</span></span>  
  
-   <span data-ttu-id="60eaf-215">Se valori dei tipi **Currency** e **Real** vengono moltiplicati e il risultato è maggiore del valore massimo possibile, nella modalità DirectQuery non viene generato alcun errore e viene restituito un valore Null.</span><span class="sxs-lookup"><span data-stu-id="60eaf-215">If values of types **Currency** and **Real** are multiplied, and the result is larger than the maximum possible value, in DirectQuery mode, no error is raised, and a null is returned.</span></span>  
  
-   <span data-ttu-id="60eaf-216">Nei modelli in memoria non viene generato alcun errore, ma viene restituito il valore massimo.</span><span class="sxs-lookup"><span data-stu-id="60eaf-216">In in-memory models, no error is raised, but the maximum value is returned.</span></span>  
  
<span data-ttu-id="60eaf-217">In generale, poiché gli intervalli di date accettati sono diversi per Excel e SQL Server, i risultati corrisponderanno solo quando le date rientrano nell'intervallo di date comune che include le date seguenti:</span><span class="sxs-lookup"><span data-stu-id="60eaf-217">In general, because the accepted date ranges are different for Excel and SQL Server, results can be guaranteed to match only when dates are within the common date range, which is inclusive of the following dates:</span></span>  
  
-   <span data-ttu-id="60eaf-218">Data meno recente: 1 marzo 1990</span><span class="sxs-lookup"><span data-stu-id="60eaf-218">Earliest date: March 1, 1990</span></span>  
  
-   <span data-ttu-id="60eaf-219">Data più recente: 31 dicembre 9999</span><span class="sxs-lookup"><span data-stu-id="60eaf-219">Latest date: December 31, 9999</span></span>  
  
<span data-ttu-id="60eaf-220">Se alcune date utilizzate nelle formule non rientrano in questo intervallo, la formula genererà un errore oppure i risultati non corrisponderanno.</span><span class="sxs-lookup"><span data-stu-id="60eaf-220">If any dates used in formulas fall outside this range, either the formula will result in an error, or the results will not match.</span></span>  
  
<span data-ttu-id="60eaf-221">**Valori a virgola mobile supportati da CEILING**</span><span class="sxs-lookup"><span data-stu-id="60eaf-221">**Floating point values supported by CEILING**</span></span>  
<span data-ttu-id="60eaf-222">ESEMPIO: `EVALUATE ROW("x", CEILING(-4.398488E+30, 1))`</span><span class="sxs-lookup"><span data-stu-id="60eaf-222">EXAMPLE: `EVALUATE ROW("x", CEILING(-4.398488E+30, 1))`</span></span>  
  
<span data-ttu-id="60eaf-223">L'equivalente Transact-SQL della funzione DAX CEILING supporta unicamente i valori con grandezza pari a 10^19 o inferiore.</span><span class="sxs-lookup"><span data-stu-id="60eaf-223">The Transact-SQL equivalent of the DAX CEILING function only supports values with magnitude of 10^19 or less.</span></span> <span data-ttu-id="60eaf-224">La regola pratica è che i valori a virgola mobile devono rientrare in **bigint**.</span><span class="sxs-lookup"><span data-stu-id="60eaf-224">A rule of thumb is that floating point values should be able to fit into **bigint**.</span></span>  
  
<span data-ttu-id="60eaf-225">**Funzioni Datepart con date esterne all'intervallo**</span><span class="sxs-lookup"><span data-stu-id="60eaf-225">**Datepart functions with dates that are out of range**</span></span>  
<span data-ttu-id="60eaf-226">Nella modalità DirectQuery i risultati corrisponderanno a quelli nei modelli in memoria solo quando la data utilizzata come argomento rientra nell'intervallo di date valido.</span><span class="sxs-lookup"><span data-stu-id="60eaf-226">Results in DirectQuery mode are guaranteed to match those in in-memory models only when the date used as the argument is in the valid date range.</span></span> <span data-ttu-id="60eaf-227">Se queste condizioni non vengono soddisfatte, viene generato un errore oppure la formula restituisce risultati diversi in DirectQuery rispetto alla modalità in memoria.</span><span class="sxs-lookup"><span data-stu-id="60eaf-227">If these conditions are not satisfied, either an error will be raised, or the formula will return different results in DirectQuery than in in-memory mode.</span></span>  
  
<span data-ttu-id="60eaf-228">ESEMPIO: `MONTH(0)` o `YEAR(0)`</span><span class="sxs-lookup"><span data-stu-id="60eaf-228">EXAMPLE: `MONTH(0)` or `YEAR(0)`</span></span>  
  
<span data-ttu-id="60eaf-229">Nella modalità DirectQuery le espressioni restituiscono rispettivamente 12 e 1899.</span><span class="sxs-lookup"><span data-stu-id="60eaf-229">In DirectQuery mode, the expressions return 12 and 1899, respectively.</span></span>  
  
<span data-ttu-id="60eaf-230">Nei modelli in memoria le espressioni restituiscono rispettivamente 1 e 1900.</span><span class="sxs-lookup"><span data-stu-id="60eaf-230">In in-memory models, the expressions return 1 and 1900, respectively.</span></span>  
  
<span data-ttu-id="60eaf-231">ESEMPIO:  `EOMONTH(0.0001, 1)`</span><span class="sxs-lookup"><span data-stu-id="60eaf-231">EXAMPLE:  `EOMONTH(0.0001, 1)`</span></span>  
  
<span data-ttu-id="60eaf-232">I risultati di questa espressione corrisponderanno solo quando i dati forniti come parametri rientrano nell'intervallo di date valido.</span><span class="sxs-lookup"><span data-stu-id="60eaf-232">The results of this expression will match only when the data supplied as a parameter is within the valid date range.</span></span>  
  
<span data-ttu-id="60eaf-233">ESEMPIO: `EOMONTH(blank(), blank())` o `EDATE(blank(), blank())`</span><span class="sxs-lookup"><span data-stu-id="60eaf-233">EXAMPLE: `EOMONTH(blank(), blank())` or `EDATE(blank(), blank())`</span></span>  
  
<span data-ttu-id="60eaf-234">I risultati di questa espressione devono essere gli stessi sia nella modalità DirectQuery sia nella modalità in memoria.</span><span class="sxs-lookup"><span data-stu-id="60eaf-234">The results of this expression should be the same in DirectQuery mode and in-memory mode.</span></span>  
  
<span data-ttu-id="60eaf-235">**Troncamento di valori ora**</span><span class="sxs-lookup"><span data-stu-id="60eaf-235">**Truncation of time values**</span></span>  
<span data-ttu-id="60eaf-236">ESEMPIO: `SECOND(1231.04097222222)`</span><span class="sxs-lookup"><span data-stu-id="60eaf-236">EXAMPLE: `SECOND(1231.04097222222)`</span></span>  
  
<span data-ttu-id="60eaf-237">Nella modalità DirectQuery il risultato viene troncato in base alle regole di SQL Server e l'espressione restituisce 59.</span><span class="sxs-lookup"><span data-stu-id="60eaf-237">In DirectQuery mode, the result is truncated, following the rules of SQL Server, and the expression evaluates to 59.</span></span>  
  
<span data-ttu-id="60eaf-238">Nei modelli in memoria i risultati di ogni operazione provvisoria vengono arrotondati. Di conseguenza, l'espressione restituisce 0.</span><span class="sxs-lookup"><span data-stu-id="60eaf-238">In in-memory models, the results of each interim operation are rounded; therefore, the expression evaluates to 0.</span></span>  
  
<span data-ttu-id="60eaf-239">Nell'esempio seguente viene illustrata la modalità di calcolo di questo valore:</span><span class="sxs-lookup"><span data-stu-id="60eaf-239">The following example demonstrates how this value is calculated:</span></span>  
  
1.  <span data-ttu-id="60eaf-240">La frazione dell'input (0,04097222222) viene moltiplicata per 24.</span><span class="sxs-lookup"><span data-stu-id="60eaf-240">The fraction of the input (0.04097222222) is multiplied by 24.</span></span>  
  
2.  <span data-ttu-id="60eaf-241">Il valore ora risultante (0,98333333328) viene moltiplicato per 60.</span><span class="sxs-lookup"><span data-stu-id="60eaf-241">The resulting hour value (0.98333333328) is multiplied by 60.</span></span>  
  
3.  <span data-ttu-id="60eaf-242">Il valore minuti risultante è 58,9999999968.</span><span class="sxs-lookup"><span data-stu-id="60eaf-242">The resulting minute value is 58.9999999968.</span></span>  
  
4.  <span data-ttu-id="60eaf-243">La frazione del valore minuti (0,9999999968) viene moltiplicata per 60.</span><span class="sxs-lookup"><span data-stu-id="60eaf-243">The fraction of the minute value (0.9999999968) is multiplied by 60.</span></span>  
  
5.  <span data-ttu-id="60eaf-244">Il secondo valore risultante (59,999999808) viene arrotondato a 60.</span><span class="sxs-lookup"><span data-stu-id="60eaf-244">The resulting second value (59.999999808) rounds up to 60.</span></span>  
  
6.  <span data-ttu-id="60eaf-245">60 equivale a 0.</span><span class="sxs-lookup"><span data-stu-id="60eaf-245">60 is equivalent to 0.</span></span>  
  
<span data-ttu-id="60eaf-246">**Tipo di dati Time di SQL non supportato**</span><span class="sxs-lookup"><span data-stu-id="60eaf-246">**SQL Time data type not supported**</span></span>  
<span data-ttu-id="60eaf-247">I modelli in memoria non supportano l'uso del nuovo tipo di dati **Time** di SQL.</span><span class="sxs-lookup"><span data-stu-id="60eaf-247">In-memory models do not support use of the new SQL **Time** data type.</span></span> <span data-ttu-id="60eaf-248">Nella modalità DirectQuery le formule che fanno riferimento a colonne con questo tipo di dati restituiscono un errore.</span><span class="sxs-lookup"><span data-stu-id="60eaf-248">In DirectQuery mode, formulas that reference columns with this data type will return an error.</span></span> <span data-ttu-id="60eaf-249">Le colonne di dati di tipo Time non possono essere importate in un modello in memoria.</span><span class="sxs-lookup"><span data-stu-id="60eaf-249">Time data columns cannot be imported into an in-memory model.</span></span>  
  
<span data-ttu-id="60eaf-250">Tuttavia, in [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] e nei modelli memorizzati nella cache, talvolta il motore esegue il cast del valore di ora a un tipo di dati accettabile e la formula restituisce un risultato.</span><span class="sxs-lookup"><span data-stu-id="60eaf-250">However, in [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] and in cached models, sometimes the engine casts the time value to an acceptable data type, and the formula returns a result.</span></span>  
  
<span data-ttu-id="60eaf-251">Questo comportamento influisce su tutte le funzioni che utilizzano una colonna di tipo date come parametro.</span><span class="sxs-lookup"><span data-stu-id="60eaf-251">This behavior affects all functions that use a date column as a parameter.</span></span>  
  
### <a name="currency"></a><a name="bkmk_Currency"></a><span data-ttu-id="60eaf-252">Valuta</span><span class="sxs-lookup"><span data-stu-id="60eaf-252">Currency</span></span>  
<span data-ttu-id="60eaf-253">Nella modalità DirectQuery, se il risultato di un'operazione aritmetica presenta il tipo **Currency**, il valore deve rientrare nell'intervallo seguente:</span><span class="sxs-lookup"><span data-stu-id="60eaf-253">In DirectQuery mode, if the result of an arithmetic operation has the type **Currency**, the value must be within the following range:</span></span>  
  
-   <span data-ttu-id="60eaf-254">Valore minimo: -922337203685477.5808</span><span class="sxs-lookup"><span data-stu-id="60eaf-254">Minimum: -922337203685477.5808</span></span>  
  
-   <span data-ttu-id="60eaf-255">Valore massimo: 922337203685477.5807</span><span class="sxs-lookup"><span data-stu-id="60eaf-255">Maximum: 922337203685477.5807</span></span>  
  
<span data-ttu-id="60eaf-256">**Combinazione di tipi di dati REAL e currency**</span><span class="sxs-lookup"><span data-stu-id="60eaf-256">**Combining currency and REAL data types**</span></span>  
<span data-ttu-id="60eaf-257">ESEMPIO: `Currency sample 1`</span><span class="sxs-lookup"><span data-stu-id="60eaf-257">EXAMPLE: `Currency sample 1`</span></span>  
  
<span data-ttu-id="60eaf-258">Se i tipi **Currency** e **Real** vengono moltiplicati e il risultato è maggiore di 9223372036854774784 (0x7ffffffffffffc00), la modalità DirectQuery non genera alcun errore.</span><span class="sxs-lookup"><span data-stu-id="60eaf-258">If **Currency** and **Real** types are multiplied, and the result is larger than 9223372036854774784 (0x7ffffffffffffc00), DirectQuery mode will not raise an error.</span></span>  
  
<span data-ttu-id="60eaf-259">In un modello in memoria viene generato un errore se il valore assoluto del risultato è maggiore di 922337203685477.4784.</span><span class="sxs-lookup"><span data-stu-id="60eaf-259">In an in-memory model, an error is raised if the absolute value of the result is larger than 922337203685477.4784.</span></span>  
  
<span data-ttu-id="60eaf-260">**L'operazione restituisce un valore non compreso nell'intervallo**</span><span class="sxs-lookup"><span data-stu-id="60eaf-260">**Operation results in an out-of-range value**</span></span>  
<span data-ttu-id="60eaf-261">ESEMPIO: `Currency sample 2`</span><span class="sxs-lookup"><span data-stu-id="60eaf-261">EXAMPLE: `Currency sample 2`</span></span>  
  
<span data-ttu-id="60eaf-262">Se le operazioni eseguite su due valori valuta qualsiasi restituiscono un valore non compreso nell'intervallo specificato, viene generato un errore nei modelli in memoria, ma non nei modelli DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="60eaf-262">If operations on any two currency values result in a value that is outside the specified range, an error is raised in in-memory models, but not in DirectQuery models.</span></span>  
  
<span data-ttu-id="60eaf-263">**Combinazione del tipo di dati currency con altri tipi**</span><span class="sxs-lookup"><span data-stu-id="60eaf-263">**Combining currency with other data types**</span></span>  
<span data-ttu-id="60eaf-264">La divisione di valori valuta per valori di altri tipi numerici può generare risultati diversi.</span><span class="sxs-lookup"><span data-stu-id="60eaf-264">Division of currency values by values of other numeric types can result in different results.</span></span>  
  
### <a name="aggregation-functions"></a><a name="bkmk_Aggregations"></a><span data-ttu-id="60eaf-265">Funzioni di aggregazione</span><span class="sxs-lookup"><span data-stu-id="60eaf-265">Aggregation functions</span></span>  
<span data-ttu-id="60eaf-266">Le funzioni statistiche eseguite su una tabella con una riga restituiscono risultati diversi.</span><span class="sxs-lookup"><span data-stu-id="60eaf-266">Statistical functions on a table with one row return different results.</span></span> <span data-ttu-id="60eaf-267">Le funzioni di aggregazione eseguite su tabelle vuote si comportano anch'esse in modo diverso nei modelli in memoria e nei modelli DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="60eaf-267">Aggregation functions over empty tables also behave differently in in-memory models than they do in DirectQuery mode.</span></span>  
  
<span data-ttu-id="60eaf-268">**Funzioni statistiche eseguite su una tabella con una sola riga**</span><span class="sxs-lookup"><span data-stu-id="60eaf-268">**Statistical functions over a table with a single row**</span></span>  
<span data-ttu-id="60eaf-269">Se la tabella utilizzata come argomento contiene una sola riga, nella modalità DirectQuery funzioni statistiche quali STDEV e VAR restituiscono valori Null.</span><span class="sxs-lookup"><span data-stu-id="60eaf-269">If the table that is used as argument contains a single row, in DirectQuery mode, statistical functions such as STDEV and VAR return null.</span></span>  
  
<span data-ttu-id="60eaf-270">In un modello in memoria una formula che utilizza STDEV o VAR su una tabella con una sola riga restituisce un errore di divisione per zero.</span><span class="sxs-lookup"><span data-stu-id="60eaf-270">In an in-memory model, a formula that uses STDEV or VAR over a table with a single row returns a division by zero error.</span></span>  
  
### <a name="text-functions"></a><a name="bkmk_Text"></a><span data-ttu-id="60eaf-271">Funzioni di testo</span><span class="sxs-lookup"><span data-stu-id="60eaf-271">Text functions</span></span>  
<span data-ttu-id="60eaf-272">Poiché gli archivi dati relazionali forniscono tipi di dati di testo diversi rispetto a Excel, è possibile ottenere risultati diversi quando si eseguono ricerche nelle stringhe o si utilizzano sottostringhe.</span><span class="sxs-lookup"><span data-stu-id="60eaf-272">Because relational data stores provide different text data types than does Excel, you may see different results when searching strings or working with substrings.</span></span> <span data-ttu-id="60eaf-273">Anche la lunghezza delle stringhe può essere diversa.</span><span class="sxs-lookup"><span data-stu-id="60eaf-273">The length of strings also can be different.</span></span>  
  
<span data-ttu-id="60eaf-274">In generale, qualsiasi funzione di modifica delle stringhe che utilizza come argomenti colonne a dimensione fissa può restituire risultati diversi.</span><span class="sxs-lookup"><span data-stu-id="60eaf-274">In general, any string manipulation functions that use fixed-size columns as arguments can have different results.</span></span>  
  
<span data-ttu-id="60eaf-275">Inoltre, in SQL Server alcune funzioni di testo supportano argomenti aggiuntivi non disponibili in Excel.</span><span class="sxs-lookup"><span data-stu-id="60eaf-275">Additionally, in SQL Server, some text functions support additional arguments that are not provided in Excel.</span></span> <span data-ttu-id="60eaf-276">Se la formula richiede l'argomento mancante, è possibile ottenere risultati o errori diversi nel modello in memoria.</span><span class="sxs-lookup"><span data-stu-id="60eaf-276">If the formula requires the missing argument you can get different results or errors in the in-memory model.</span></span>  
  
<span data-ttu-id="60eaf-277">**È possibile che le operazioni che restituiscono un carattere utilizzando LEFT, RIGHT e così via restituiscano il carattere corretto, anche se con maiuscole/minuscole diverse, oppure nessun risultato.**</span><span class="sxs-lookup"><span data-stu-id="60eaf-277">**Operations that return a character using LEFT, RIGHT, etc. may return the correct character but in a different case, or no results**</span></span>  
<span data-ttu-id="60eaf-278">ESEMPIO: `LEFT(["text"], 2)`</span><span class="sxs-lookup"><span data-stu-id="60eaf-278">EXAMPLE: `LEFT(["text"], 2)`</span></span>  
  
<span data-ttu-id="60eaf-279">Nella modalità DirectQuery le maiuscole/minuscole del carattere restituito corrispondono sempre esattamente a quelle della lettera archiviata nel database.</span><span class="sxs-lookup"><span data-stu-id="60eaf-279">In DirectQuery mode, the case of the character that is returned is always exactly the same as the letter that is stored in the database.</span></span> <span data-ttu-id="60eaf-280">Tuttavia, il motore xVelocity utilizza un algoritmo diverso per la compressione e l'indicizzazione di valori per migliorare le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="60eaf-280">However, the xVelocity engine uses a different algorithm for compression and indexing of values, to improve performance.</span></span>  
  
<span data-ttu-id="60eaf-281">Per impostazione predefinita, vengono utilizzate le regole di confronto Latin1_General che non fanno distinzione tra maiuscole e minuscole, ma distinzione tra caratteri accentati e non.</span><span class="sxs-lookup"><span data-stu-id="60eaf-281">By default, the Latin1_General collation is used, which is case-insensitive but accent-sensitive.</span></span> <span data-ttu-id="60eaf-282">Di conseguenza, se sono presenti più istanze di una stringa di testo in caratteri minuscoli, maiuscoli o entrambi, tutte le istanze saranno considerate la stessa stringa e solo la prima istanza della stringa verrà archiviata nell'indice.</span><span class="sxs-lookup"><span data-stu-id="60eaf-282">Therefore, if there are multiple instances of a text string in lower case, upper case, or mixed case, all instances are considered the same string, and only the first instance of the string is stored in the index.</span></span> <span data-ttu-id="60eaf-283">Tutte le funzioni di testo eseguite su stringhe archiviate consentono di recuperare la porzione specificata della forma indicizzata.</span><span class="sxs-lookup"><span data-stu-id="60eaf-283">All text functions that operate on stored strings will retrieve the specified portion of the indexed form.</span></span> <span data-ttu-id="60eaf-284">Di conseguenza, la formula di esempio restituisce lo stesso valore per l'intera colonna, utilizzando la prima istanza come input.</span><span class="sxs-lookup"><span data-stu-id="60eaf-284">Therefore, the example formula would return the same value for the entire column, using the first instance as the input.</span></span>  
  
[<span data-ttu-id="60eaf-285">Archivio di stringhe e regole di confronto nei modelli tabulari</span><span class="sxs-lookup"><span data-stu-id="60eaf-285">String Storage and Collation in Tabular Models</span></span>](https://msdn.microsoft.com/8516f0ad-32ee-4688-a304-e705143642ca)  
  
<span data-ttu-id="60eaf-286">Questo comportamento si applica anche ad altre funzioni di testo, incluse RIGHT, MID e così via.</span><span class="sxs-lookup"><span data-stu-id="60eaf-286">This behavior also applies to other text functions, including RIGHT, MID, and so forth.</span></span>  
  
<span data-ttu-id="60eaf-287">**La lunghezza della stringa influisce sui risultati**</span><span class="sxs-lookup"><span data-stu-id="60eaf-287">**String length affects results**</span></span>  
<span data-ttu-id="60eaf-288">ESEMPIO: `SEARCH("within string", "sample target  text", 1, 1)`</span><span class="sxs-lookup"><span data-stu-id="60eaf-288">EXAMPLE: `SEARCH("within string", "sample target  text", 1, 1)`</span></span>  
  
<span data-ttu-id="60eaf-289">Se si cerca una stringa utilizzando la funzione SEARCH e la stringa di destinazione è più lunga della stringa che la contiene, viene generato un errore.</span><span class="sxs-lookup"><span data-stu-id="60eaf-289">If you search for a string using the SEARCH function, and the target string is longer than the within string, DirectQuery mode raises an error.</span></span>  
  
<span data-ttu-id="60eaf-290">In un modello in memoria viene restituita la stringa cercata, ma la sua lunghezza viene troncata alla lunghezza del &lt;testo che la contiene&gt;.</span><span class="sxs-lookup"><span data-stu-id="60eaf-290">In an in-memory model, the searched string is returned, but with its length truncated to the length of &lt;within text&gt;.</span></span>  
  
<span data-ttu-id="60eaf-291">ESEMPIO: `EVALUATE ROW("X", REPLACE("CA", 3, 2, "California") )`</span><span class="sxs-lookup"><span data-stu-id="60eaf-291">EXAMPLE: `EVALUATE ROW("X", REPLACE("CA", 3, 2, "California") )`</span></span>  
  
<span data-ttu-id="60eaf-292">Se la lunghezza della stringa di sostituzione è maggiore della lunghezza della stringa originale, nella modalità DirectQuery la formula restituisce Null.</span><span class="sxs-lookup"><span data-stu-id="60eaf-292">If the length of the replacement string is greater than the length of the original string, in DirectQuery mode, the formula returns null.</span></span>  
  
<span data-ttu-id="60eaf-293">Nei modelli in memoria la formula segue il comportamento di Excel che prevede il concatenamento della stringa di origine e della stringa di sostituzione, con restituzione del risultato CACalifornia.</span><span class="sxs-lookup"><span data-stu-id="60eaf-293">In in-memory models, the formula follows the behavior of Excel, which concatenates the source string and the replacement string, which returns CACalifornia.</span></span>  
  
<span data-ttu-id="60eaf-294">**Funzione TRIM implicita al centro delle stringhe**</span><span class="sxs-lookup"><span data-stu-id="60eaf-294">**Implicit TRIM in the middle of strings**</span></span>  
<span data-ttu-id="60eaf-295">ESEMPIO: `TRIM(" A sample sentence with leading white space")`</span><span class="sxs-lookup"><span data-stu-id="60eaf-295">EXAMPLE: `TRIM(" A sample sentence with leading white space")`</span></span>  
  
<span data-ttu-id="60eaf-296">La modalità DirectQuery prevede la conversione della funzione DAX TRIM nell'istruzione SQL `LTRIM(RTRIM(<column>))`.</span><span class="sxs-lookup"><span data-stu-id="60eaf-296">DirectQuery mode translates the DAX TRIM function to the SQL statement `LTRIM(RTRIM(<column>))`.</span></span> <span data-ttu-id="60eaf-297">Di conseguenza, vengono rimossi gli spazi vuoti iniziale e finale.</span><span class="sxs-lookup"><span data-stu-id="60eaf-297">As a result, only leading and trailing white space is removed.</span></span>  
  
<span data-ttu-id="60eaf-298">Al contrario, in un modello in memoria la stessa formula prevede la rimozione degli spazi all'interno della stringa, in base al comportamento di Excel.</span><span class="sxs-lookup"><span data-stu-id="60eaf-298">In contrast, the same formula in an in-memory model removes spaces within the string, following the behavior of Excel.</span></span>  
  
<span data-ttu-id="60eaf-299">**Funzione RTRIM implicita con utilizzo della funzione LEN**</span><span class="sxs-lookup"><span data-stu-id="60eaf-299">**Implicit RTRIM with use of LEN function**</span></span>  
<span data-ttu-id="60eaf-300">ESEMPIO: `LEN('string_column')`</span><span class="sxs-lookup"><span data-stu-id="60eaf-300">EXAMPLE: `LEN('string_column')`</span></span>  
  
<span data-ttu-id="60eaf-301">Analogamente a SQL Server, la modalità DirectQuery rimuove automaticamente lo spazio vuoto dalla fine delle colonne stringa, ovvero esegue una funzione RTRIM implicita.</span><span class="sxs-lookup"><span data-stu-id="60eaf-301">Like SQL Server, DirectQuery mode automatically removes white space from the end of string columns: that is, it performs an implicit RTRIM.</span></span> <span data-ttu-id="60eaf-302">Di conseguenza, le formule che utilizzano la funzione LEN possono restituire valori diversi se la stringa contiene spazi finali.</span><span class="sxs-lookup"><span data-stu-id="60eaf-302">Therefore, formulas that use the LEN function can return different values if the string has trailing spaces.</span></span>  
  
<span data-ttu-id="60eaf-303">**In memoria supporta parametri aggiuntivi per SUBSTITUTE**</span><span class="sxs-lookup"><span data-stu-id="60eaf-303">**In-memory supports additional parameters for SUBSTITUTE**</span></span>  
<span data-ttu-id="60eaf-304">ESEMPIO: `SUBSTITUTE([Title],"Doctor","Dr.")`</span><span class="sxs-lookup"><span data-stu-id="60eaf-304">EXAMPLE: `SUBSTITUTE([Title],"Doctor","Dr.")`</span></span>  
  
<span data-ttu-id="60eaf-305">ESEMPIO: `SUBSTITUTE([Title],"Doctor","Dr.", 2)`</span><span class="sxs-lookup"><span data-stu-id="60eaf-305">EXAMPLE: `SUBSTITUTE([Title],"Doctor","Dr.", 2)`</span></span>  
  
<span data-ttu-id="60eaf-306">Nella modalità DirectQuery è possibile utilizzare solo la versione di questa funzione che dispone di tre (3) parametri: un riferimento a una colonna, il testo precedente e quello nuovo.</span><span class="sxs-lookup"><span data-stu-id="60eaf-306">In DirectQuery mode, you can use only the version of this function that has three (3) parameters: a reference to a column, the old text, and the new text.</span></span> <span data-ttu-id="60eaf-307">Se si utilizza la seconda formula, viene generato un errore.</span><span class="sxs-lookup"><span data-stu-id="60eaf-307">If you use the second formula, an error is raised.</span></span>  
  
<span data-ttu-id="60eaf-308">Nei modelli in memoria è possibile utilizzare un quarto parametro facoltativo per specificare il numero di istanza della stringa da sostituire.</span><span class="sxs-lookup"><span data-stu-id="60eaf-308">In in-memory models, you can use an optional fourth parameter to specify the instance number of the string to replace.</span></span> <span data-ttu-id="60eaf-309">Ad esempio, è possibile sostituire solo la seconda istanza e così via.</span><span class="sxs-lookup"><span data-stu-id="60eaf-309">For example, you can replace only the second instance, etc.</span></span>  
  
<span data-ttu-id="60eaf-310">**Limitazioni sulle lunghezze di stringa per le operazioni REPT**</span><span class="sxs-lookup"><span data-stu-id="60eaf-310">**Restrictions on string lengths for REPT operations**</span></span>  
<span data-ttu-id="60eaf-311">Nei modelli in memoria la lunghezza di una stringa risultante da un'operazione che utilizza REPT deve essere minore di 32.767 caratteri.</span><span class="sxs-lookup"><span data-stu-id="60eaf-311">In in-memory models, the length of a string resulting from an operation using REPT must be less than 32,767 characters.</span></span>  
  
<span data-ttu-id="60eaf-312">Questa limitazione non è applicabile alla modalità DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="60eaf-312">This limitation does not apply in DirectQuery mode.</span></span>  
  
<span data-ttu-id="60eaf-313">**Le operazioni di sottostringa restituiscono risultati diversi a seconda del tipo di carattere**</span><span class="sxs-lookup"><span data-stu-id="60eaf-313">**Substring operations return different results depending on character type**</span></span>  
<span data-ttu-id="60eaf-314">ESEMPIO: `MID([col], 2, 5)`</span><span class="sxs-lookup"><span data-stu-id="60eaf-314">EXAMPLE: `MID([col], 2, 5)`</span></span>  
  
<span data-ttu-id="60eaf-315">Se il testo di input è **varchar** o **nvarchar**, il risultato della formula è sempre lo stesso.</span><span class="sxs-lookup"><span data-stu-id="60eaf-315">If the input text is **varchar** or **nvarchar**, the result of the formula is always the same.</span></span>  
  
<span data-ttu-id="60eaf-316">Tuttavia, se il testo è un carattere a lunghezza fissa e il valore per \* &lt; num_chars &gt; \* è maggiore della lunghezza della stringa di destinazione, nella modalità DirectQuery viene aggiunto uno spazio vuoto alla fine della stringa di risultato.</span><span class="sxs-lookup"><span data-stu-id="60eaf-316">However, if the text is a fixed-length character and the value for *&lt;num_chars&gt;* is greater than the length of the target string, in DirectQuery mode, a blank is added at the end of the result string.</span></span>  
  
<span data-ttu-id="60eaf-317">In un modello in memoria il risultato termina in corrispondenza dell'ultimo carattere della stringa, senza riempimento.</span><span class="sxs-lookup"><span data-stu-id="60eaf-317">In an in-memory model, the result terminates at the last string character, with no padding.</span></span>  
  
## <a name="functions-supported-in-directquery-mode"></a><a name="bkmk_SupportedFunc"></a><span data-ttu-id="60eaf-318">Funzioni supportate in modalità DirectQuery</span><span class="sxs-lookup"><span data-stu-id="60eaf-318">Functions supported in DirectQuery mode</span></span>  
<span data-ttu-id="60eaf-319">Le funzioni DAX seguenti possono essere utilizzate nella modalità DirectQuery, ma con le caratteristiche descritte nella sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="60eaf-319">The following DAX functions can be used in DirectQuery mode, but with the qualifications as described in the preceding section.</span></span>  
  
<span data-ttu-id="60eaf-320">**Funzioni di testo**</span><span class="sxs-lookup"><span data-stu-id="60eaf-320">**Text functions**</span></span>  
  
<span data-ttu-id="60eaf-321">CONCATENATE</span><span class="sxs-lookup"><span data-stu-id="60eaf-321">CONCATENATE</span></span>  
  
<span data-ttu-id="60eaf-322">FIND</span><span class="sxs-lookup"><span data-stu-id="60eaf-322">FIND</span></span>  
  
<span data-ttu-id="60eaf-323">LEFT</span><span class="sxs-lookup"><span data-stu-id="60eaf-323">LEFT</span></span>  
  
<span data-ttu-id="60eaf-324">LEN</span><span class="sxs-lookup"><span data-stu-id="60eaf-324">LEN</span></span>  
  
<span data-ttu-id="60eaf-325">MID</span><span class="sxs-lookup"><span data-stu-id="60eaf-325">MID</span></span>  
  
<span data-ttu-id="60eaf-326">REPLACE</span><span class="sxs-lookup"><span data-stu-id="60eaf-326">REPLACE</span></span>  
  
<span data-ttu-id="60eaf-327">REPT</span><span class="sxs-lookup"><span data-stu-id="60eaf-327">REPT</span></span>  
  
<span data-ttu-id="60eaf-328">RIGHT</span><span class="sxs-lookup"><span data-stu-id="60eaf-328">RIGHT</span></span>  
  
<span data-ttu-id="60eaf-329">SUBSTITUTE</span><span class="sxs-lookup"><span data-stu-id="60eaf-329">SUBSTITUTE</span></span>  
  
<span data-ttu-id="60eaf-330">TRIM</span><span class="sxs-lookup"><span data-stu-id="60eaf-330">TRIM</span></span>  
  
<span data-ttu-id="60eaf-331">**Funzioni statistiche**</span><span class="sxs-lookup"><span data-stu-id="60eaf-331">**Statistical functions**</span></span>  
  
<span data-ttu-id="60eaf-332">COUNT</span><span class="sxs-lookup"><span data-stu-id="60eaf-332">COUNT</span></span>  
  
<span data-ttu-id="60eaf-333">STDEV.P</span><span class="sxs-lookup"><span data-stu-id="60eaf-333">STDEV.P</span></span>  
  
<span data-ttu-id="60eaf-334">STDEV.S</span><span class="sxs-lookup"><span data-stu-id="60eaf-334">STDEV.S</span></span>  
  
<span data-ttu-id="60eaf-335">STDEVX.P</span><span class="sxs-lookup"><span data-stu-id="60eaf-335">STDEVX.P</span></span>  
  
<span data-ttu-id="60eaf-336">STDEVX.S</span><span class="sxs-lookup"><span data-stu-id="60eaf-336">STDEVX.S</span></span>  
  
<span data-ttu-id="60eaf-337">VAR.P</span><span class="sxs-lookup"><span data-stu-id="60eaf-337">VAR.P</span></span>  
  
<span data-ttu-id="60eaf-338">VAR.S</span><span class="sxs-lookup"><span data-stu-id="60eaf-338">VAR.S</span></span>  
  
<span data-ttu-id="60eaf-339">VARX.P</span><span class="sxs-lookup"><span data-stu-id="60eaf-339">VARX.P</span></span>  
  
<span data-ttu-id="60eaf-340">VARX.S</span><span class="sxs-lookup"><span data-stu-id="60eaf-340">VARX.S</span></span>  
  
<span data-ttu-id="60eaf-341">**Funzioni di data/ora**</span><span class="sxs-lookup"><span data-stu-id="60eaf-341">**Date/time functions**</span></span>  
  
<span data-ttu-id="60eaf-342">DATE</span><span class="sxs-lookup"><span data-stu-id="60eaf-342">DATE</span></span>  
  
<span data-ttu-id="60eaf-343">EDATE</span><span class="sxs-lookup"><span data-stu-id="60eaf-343">EDATE</span></span>  
  
<span data-ttu-id="60eaf-344">EOMONTH</span><span class="sxs-lookup"><span data-stu-id="60eaf-344">EOMONTH</span></span>  
  
<span data-ttu-id="60eaf-345">DATE</span><span class="sxs-lookup"><span data-stu-id="60eaf-345">DATE</span></span>  
  
<span data-ttu-id="60eaf-346">TIME</span><span class="sxs-lookup"><span data-stu-id="60eaf-346">TIME</span></span>  
  
<span data-ttu-id="60eaf-347">SECOND</span><span class="sxs-lookup"><span data-stu-id="60eaf-347">SECOND</span></span>  
  
<span data-ttu-id="60eaf-348">**Funzioni numeriche e matematiche**</span><span class="sxs-lookup"><span data-stu-id="60eaf-348">**Math and number functions**</span></span>  
  
<span data-ttu-id="60eaf-349">CEILING</span><span class="sxs-lookup"><span data-stu-id="60eaf-349">CEILING</span></span>  
  
<span data-ttu-id="60eaf-350">LN</span><span class="sxs-lookup"><span data-stu-id="60eaf-350">LN</span></span>  
  
<span data-ttu-id="60eaf-351">LOG</span><span class="sxs-lookup"><span data-stu-id="60eaf-351">LOG</span></span>  
  
<span data-ttu-id="60eaf-352">LOG10</span><span class="sxs-lookup"><span data-stu-id="60eaf-352">LOG10</span></span>  
  
<span data-ttu-id="60eaf-353">POWER</span><span class="sxs-lookup"><span data-stu-id="60eaf-353">POWER</span></span>  
  
<span data-ttu-id="60eaf-354">**Query di tabella DAX**</span><span class="sxs-lookup"><span data-stu-id="60eaf-354">**DAX Table queries**</span></span>  
  
<span data-ttu-id="60eaf-355">Esistono alcune limitazioni sulla valutazione delle formule su un modello DirectQuery tramite le query di tabella DAX.</span><span class="sxs-lookup"><span data-stu-id="60eaf-355">There are some limitations when you evaluate formulas against a DirectQuery model by using DAX Table queries.</span></span> <span data-ttu-id="60eaf-356">DirectQuery non supporta il doppio riferimento alla stessa colonna in una clausola ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="60eaf-356">DirectQuery does not support referring to the same column twice in an ORDER BY clause.</span></span> <span data-ttu-id="60eaf-357">L'istruzione Transact-SQL equivalente non può essere creata e la query ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="60eaf-357">The equivalent Transact-SQL statement cannot be created and the query fails.</span></span>  
  
<span data-ttu-id="60eaf-358">In un modello in memoria la ripetizione della clausola ORDER BY non influisce sui risultati.</span><span class="sxs-lookup"><span data-stu-id="60eaf-358">In an in-memory model, repeating the ORDER by clause has no effect on the results.</span></span>  
  
## <a name="functions-not-supported-in-directquery-mode"></a><a name="bkmk_NotSupportedFunc"></a><span data-ttu-id="60eaf-359">Funzioni non supportate nella modalità DirectQuery</span><span class="sxs-lookup"><span data-stu-id="60eaf-359">Functions not supported in DirectQuery Mode</span></span>  
<span data-ttu-id="60eaf-360">Le funzioni DAX non sono supportate nei modelli distribuiti nella modalità DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="60eaf-360">Some DAX functions are not supported in models that are deployed in DirectQuery mode.</span></span> <span data-ttu-id="60eaf-361">I motivi per cui una particolare funzione non è supportata possono includere uno o una combinazione dei motivi seguenti:</span><span class="sxs-lookup"><span data-stu-id="60eaf-361">The reasons that a particular function is not supported can include any or a combination of these reasons:</span></span>  
  
-   <span data-ttu-id="60eaf-362">Il motore relazionale sottostante non è in grado di eseguire calcoli equivalenti a quelli eseguiti dal motore xVelocity.</span><span class="sxs-lookup"><span data-stu-id="60eaf-362">The underlying relational engine cannot perform calculations equivalent to those performed by the xVelocity engine.</span></span>  
  
-   <span data-ttu-id="60eaf-363">La formula non può essere convertita in un'espressione SQL equivalente.</span><span class="sxs-lookup"><span data-stu-id="60eaf-363">The formula cannot be converted to en equivalent SQL expression.</span></span>  
  
-   <span data-ttu-id="60eaf-364">Le prestazioni dell'espressione convertita e i calcoli risultanti sarebbero inaccettabili.</span><span class="sxs-lookup"><span data-stu-id="60eaf-364">The performance of the converted expression and the resulting calculations would be unacceptable.</span></span>  
  
<span data-ttu-id="60eaf-365">Le funzioni DAX seguenti non possono essere utilizzate nei modelli DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="60eaf-365">The following DAX functions cannot be used in DirectQuery models.</span></span>  
  
<span data-ttu-id="60eaf-366">**Funzioni percorso**</span><span class="sxs-lookup"><span data-stu-id="60eaf-366">**Path functions**</span></span>  
  
<span data-ttu-id="60eaf-367">PATH</span><span class="sxs-lookup"><span data-stu-id="60eaf-367">PATH</span></span>  
  
<span data-ttu-id="60eaf-368">PATHCONTAINS</span><span class="sxs-lookup"><span data-stu-id="60eaf-368">PATHCONTAINS</span></span>  
  
<span data-ttu-id="60eaf-369">PATHITEM</span><span class="sxs-lookup"><span data-stu-id="60eaf-369">PATHITEM</span></span>  
  
<span data-ttu-id="60eaf-370">PATHITEMREVERSE</span><span class="sxs-lookup"><span data-stu-id="60eaf-370">PATHITEMREVERSE</span></span>  
  
<span data-ttu-id="60eaf-371">PATHLENGTH</span><span class="sxs-lookup"><span data-stu-id="60eaf-371">PATHLENGTH</span></span>  
  
<span data-ttu-id="60eaf-372">**Funzioni varie**</span><span class="sxs-lookup"><span data-stu-id="60eaf-372">**Misc functions**</span></span>  
  
<span data-ttu-id="60eaf-373">COUNTBLANK</span><span class="sxs-lookup"><span data-stu-id="60eaf-373">COUNTBLANK</span></span>  
  
<span data-ttu-id="60eaf-374">FIXED</span><span class="sxs-lookup"><span data-stu-id="60eaf-374">FIXED</span></span>  
  
<span data-ttu-id="60eaf-375">FORMAT</span><span class="sxs-lookup"><span data-stu-id="60eaf-375">FORMAT</span></span>  
  
<span data-ttu-id="60eaf-376">RAND</span><span class="sxs-lookup"><span data-stu-id="60eaf-376">RAND</span></span>  
  
<span data-ttu-id="60eaf-377">RANDBETWEEN</span><span class="sxs-lookup"><span data-stu-id="60eaf-377">RANDBETWEEN</span></span>  
  
<span data-ttu-id="60eaf-378">**Funzioni di Business Intelligence per le gerarchie temporali: date di inizio e fine**</span><span class="sxs-lookup"><span data-stu-id="60eaf-378">**Time intelligence functions: Start and end dates**</span></span>  
  
<span data-ttu-id="60eaf-379">DATESQTD</span><span class="sxs-lookup"><span data-stu-id="60eaf-379">DATESQTD</span></span>  
  
<span data-ttu-id="60eaf-380">DATESYTD</span><span class="sxs-lookup"><span data-stu-id="60eaf-380">DATESYTD</span></span>  
  
<span data-ttu-id="60eaf-381">DATESMTD</span><span class="sxs-lookup"><span data-stu-id="60eaf-381">DATESMTD</span></span>  
  
<span data-ttu-id="60eaf-382">DATESQTD</span><span class="sxs-lookup"><span data-stu-id="60eaf-382">DATESQTD</span></span>  
  
<span data-ttu-id="60eaf-383">DATESINPERIOD</span><span class="sxs-lookup"><span data-stu-id="60eaf-383">DATESINPERIOD</span></span>  
  
<span data-ttu-id="60eaf-384">TOTALMTD</span><span class="sxs-lookup"><span data-stu-id="60eaf-384">TOTALMTD</span></span>  
  
<span data-ttu-id="60eaf-385">TOTALQTD</span><span class="sxs-lookup"><span data-stu-id="60eaf-385">TOTALQTD</span></span>  
  
<span data-ttu-id="60eaf-386">TOTALYTD</span><span class="sxs-lookup"><span data-stu-id="60eaf-386">TOTALYTD</span></span>  
  
<span data-ttu-id="60eaf-387">DATESINPERIOD</span><span class="sxs-lookup"><span data-stu-id="60eaf-387">DATESINPERIOD</span></span>  
  
<span data-ttu-id="60eaf-388">SAMEPERIODLASTYEAR</span><span class="sxs-lookup"><span data-stu-id="60eaf-388">SAMEPERIODLASTYEAR</span></span>  
  
<span data-ttu-id="60eaf-389">PARALLELPERIOD</span><span class="sxs-lookup"><span data-stu-id="60eaf-389">PARALLELPERIOD</span></span>  
  
<span data-ttu-id="60eaf-390">**Funzioni di Business Intelligence per il tempo: Saldi**</span><span class="sxs-lookup"><span data-stu-id="60eaf-390">**Time-intelligence functions: Balances**</span></span>  
  
<span data-ttu-id="60eaf-391">OPENINGBALANCEMONTH</span><span class="sxs-lookup"><span data-stu-id="60eaf-391">OPENINGBALANCEMONTH</span></span>  
  
<span data-ttu-id="60eaf-392">OPENINGBALANCEQUARTER</span><span class="sxs-lookup"><span data-stu-id="60eaf-392">OPENINGBALANCEQUARTER</span></span>  
  
<span data-ttu-id="60eaf-393">OPENINGBALANCEYEAR</span><span class="sxs-lookup"><span data-stu-id="60eaf-393">OPENINGBALANCEYEAR</span></span>  
  
<span data-ttu-id="60eaf-394">CLOSINGBALANCEMONTH</span><span class="sxs-lookup"><span data-stu-id="60eaf-394">CLOSINGBALANCEMONTH</span></span>  
  
<span data-ttu-id="60eaf-395">CLOSINGBALANCEQUARTER</span><span class="sxs-lookup"><span data-stu-id="60eaf-395">CLOSINGBALANCEQUARTER</span></span>  
  
<span data-ttu-id="60eaf-396">CLOSINGBALANCEYEAR</span><span class="sxs-lookup"><span data-stu-id="60eaf-396">CLOSINGBALANCEYEAR</span></span>  
  
<span data-ttu-id="60eaf-397">**Funzioni di Business Intelligence per le gerarchie temporali: periodi precedenti e successivi**</span><span class="sxs-lookup"><span data-stu-id="60eaf-397">**Time intelligence functions: Previous and next periods**</span></span>  
  
<span data-ttu-id="60eaf-398">PREVIOUSDAY</span><span class="sxs-lookup"><span data-stu-id="60eaf-398">PREVIOUSDAY</span></span>  
  
<span data-ttu-id="60eaf-399">PREVIOUSMONTH</span><span class="sxs-lookup"><span data-stu-id="60eaf-399">PREVIOUSMONTH</span></span>  
  
<span data-ttu-id="60eaf-400">PREVIOUSQUARTER</span><span class="sxs-lookup"><span data-stu-id="60eaf-400">PREVIOUSQUARTER</span></span>  
  
<span data-ttu-id="60eaf-401">PREVIOUSYEAR</span><span class="sxs-lookup"><span data-stu-id="60eaf-401">PREVIOUSYEAR</span></span>  
  
<span data-ttu-id="60eaf-402">NEXTDAY</span><span class="sxs-lookup"><span data-stu-id="60eaf-402">NEXTDAY</span></span>  
  
<span data-ttu-id="60eaf-403">NEXTMONTH</span><span class="sxs-lookup"><span data-stu-id="60eaf-403">NEXTMONTH</span></span>  
  
<span data-ttu-id="60eaf-404">NEXTQUARTER</span><span class="sxs-lookup"><span data-stu-id="60eaf-404">NEXTQUARTER</span></span>  
  
<span data-ttu-id="60eaf-405">NEXTYEAR</span><span class="sxs-lookup"><span data-stu-id="60eaf-405">NEXTYEAR</span></span>  
  
<span data-ttu-id="60eaf-406">**Funzioni di Business Intelligence per le gerarchie temporali: periodi e calcoli su periodi**</span><span class="sxs-lookup"><span data-stu-id="60eaf-406">**Time intelligence functions: Periods and calculations over periods**</span></span>  
  
<span data-ttu-id="60eaf-407">STARTOFMONTH</span><span class="sxs-lookup"><span data-stu-id="60eaf-407">STARTOFMONTH</span></span>  
  
<span data-ttu-id="60eaf-408">STARTOFQUARTER</span><span class="sxs-lookup"><span data-stu-id="60eaf-408">STARTOFQUARTER</span></span>  
  
<span data-ttu-id="60eaf-409">STARTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="60eaf-409">STARTOFYEAR</span></span>  
  
<span data-ttu-id="60eaf-410">ENDOFMONTH</span><span class="sxs-lookup"><span data-stu-id="60eaf-410">ENDOFMONTH</span></span>  
  
<span data-ttu-id="60eaf-411">ENDOFQUARTER</span><span class="sxs-lookup"><span data-stu-id="60eaf-411">ENDOFQUARTER</span></span>  
  
<span data-ttu-id="60eaf-412">ENDOFYEAR</span><span class="sxs-lookup"><span data-stu-id="60eaf-412">ENDOFYEAR</span></span>  
  
<span data-ttu-id="60eaf-413">FIRSTDATE</span><span class="sxs-lookup"><span data-stu-id="60eaf-413">FIRSTDATE</span></span>  
  
<span data-ttu-id="60eaf-414">LASTDATE</span><span class="sxs-lookup"><span data-stu-id="60eaf-414">LASTDATE</span></span>  
  
<span data-ttu-id="60eaf-415">DATEADD</span><span class="sxs-lookup"><span data-stu-id="60eaf-415">DATEADD</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60eaf-416">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="60eaf-416">See also</span></span>  
[<span data-ttu-id="60eaf-417">Modalità DirectQuery (SSAS tabulare)</span><span class="sxs-lookup"><span data-stu-id="60eaf-417">DirectQuery Mode (SSAS Tabular)</span></span>](https://msdn.microsoft.com/45ad2965-05ec-4fb1-a164-d8060b562ea5)  
  

