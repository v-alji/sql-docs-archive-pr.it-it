---
title: Limitare i risultati della ricerca mediante RANK | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
helpviewer_keywords:
- row ranking [full-text search]
- relevance ranking values [full-text search]
- full-text search [SQL Server], rankings
- index rankings [full-text search]
- ranked results [full-text search]
- rankings [full-text search]
- per-row rank values [full-text search]
ms.assetid: 06a776e6-296c-4ec7-9fa5-0794709ccb17
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ab1b930b3238cb541965e1984d1561f1a1c22d87
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717700"
---
# <a name="limit-search-results-with-rank"></a><span data-ttu-id="48ec6-102">Limitazione dei risultati della ricerca mediante RANK</span><span class="sxs-lookup"><span data-stu-id="48ec6-102">Limit Search Results with RANK</span></span>
  <span data-ttu-id="48ec6-103">Le funzioni [CONTAINSTABLE](/sql/relational-databases/system-functions/containstable-transact-sql) e [FREETEXTTABLE](/sql/relational-databases/system-functions/freetexttable-transact-sql) restituiscono una colonna denominata RANK che contiene valori ordinali compresi tra 0 e 1000 (valori di classificazione).</span><span class="sxs-lookup"><span data-stu-id="48ec6-103">The [CONTAINSTABLE](/sql/relational-databases/system-functions/containstable-transact-sql) and [FREETEXTTABLE](/sql/relational-databases/system-functions/freetexttable-transact-sql) functions return a column named RANK that contains ordinal values from 0 through 1000 (rank values).</span></span> <span data-ttu-id="48ec6-104">Questi valori vengono utilizzati per classificare le righe restituite in base al grado di corrispondenza con i criteri di selezione.</span><span class="sxs-lookup"><span data-stu-id="48ec6-104">These values are used to rank the rows returned according to how well they match the selection criteria.</span></span> <span data-ttu-id="48ec6-105">I valori di pertinenza indicano solo un ordine relativo di pertinenza delle righe nel set di risultati, dove un valore inferiore indica una pertinenza inferiore.</span><span class="sxs-lookup"><span data-stu-id="48ec6-105">The rank values indicate only a relative order of relevance of the rows in the result set, with a lower value indicating lower relevance.</span></span> <span data-ttu-id="48ec6-106">I valori effettivi sono senza importanza e in genere variano ogni volta che viene eseguita la query.</span><span class="sxs-lookup"><span data-stu-id="48ec6-106">The actual values are unimportant and typically differ each time the query is run.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="48ec6-107">I predicati CONTAINS e FREETEXT non restituiscono alcun valore di pertinenza.</span><span class="sxs-lookup"><span data-stu-id="48ec6-107">The CONTAINS and FREETEXT predicates do not return any rank values.</span></span>  
  
 <span data-ttu-id="48ec6-108">Il numero di elementi corrispondenti a una condizione di ricerca è spesso molto elevato.</span><span class="sxs-lookup"><span data-stu-id="48ec6-108">The number of items matching a search condition is often very large.</span></span> <span data-ttu-id="48ec6-109">Per evitare che le query CONTAINSTABLE o FREETEXTTABLE restituiscano un numero eccessivo di risultati, usare il parametro facoltativo *top_n_by_rank* che restituisce solo un subset di righe.</span><span class="sxs-lookup"><span data-stu-id="48ec6-109">To prevent CONTAINSTABLE or FREETEXTTABLE queries from returning too many matches, use the optional *top_n_by_rank* parameter, which returns only a subset of rows.</span></span> <span data-ttu-id="48ec6-110">*top_n_by_rank* è un numero intero, *n*, che specifica che dovranno essere restituite solo le *n* corrispondenze con la pertinenza più alta, in ordine discendente.</span><span class="sxs-lookup"><span data-stu-id="48ec6-110">*top_n_by_rank* is an integer value, *n*, that specifies that only the *n* highest ranked matches are to be returned, in descending order.</span></span> <span data-ttu-id="48ec6-111">Se il parametro *top_n_by_rank* viene combinato con altri parametri, la query potrebbe restituire un numero inferiore di righe rispetto al numero di righe effettivamente corrispondenti a tutti i predicati.</span><span class="sxs-lookup"><span data-stu-id="48ec6-111">If *top_n_by_rank* is combined with other parameters, the query could return fewer rows than the number of rows that actually match all the predicates.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="48ec6-112">ordina le corrispondenze per pertinenza e restituisce solo il numero specificato di righe.</span><span class="sxs-lookup"><span data-stu-id="48ec6-112">orders the matches by rank and returns only up to the specified number of rows.</span></span> <span data-ttu-id="48ec6-113">Questa opzione può comportare un miglioramento significativo delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="48ec6-113">This choice can result in a dramatic increase in performance.</span></span> <span data-ttu-id="48ec6-114">Una query che normalmente restituisce 100.000 righe di una tabella che contiene un milione di righe, ad esempio, viene elaborata più rapidamente se vengono richieste solo le prime 100 righe.</span><span class="sxs-lookup"><span data-stu-id="48ec6-114">For example, a query that would normally return 100,000 rows from a table of one million rows are processed more quickly if only the top 100 rows are requested.</span></span>  
  
##  <a name="examples-of-using-rank-to-limit-search-results"></a><a name="examples"></a> <span data-ttu-id="48ec6-115">Esempi di utilizzo di RANK per limitare i risultati della ricerca</span><span class="sxs-lookup"><span data-stu-id="48ec6-115">Examples of Using RANK to Limit Search Results</span></span>  
  
### <a name="example-a-searching-for-only-the-top-three-matches"></a><span data-ttu-id="48ec6-116">Esempio A: Ricerca delle prime tre corrispondenze</span><span class="sxs-lookup"><span data-stu-id="48ec6-116">Example A: Searching for only the top three matches</span></span>  
 <span data-ttu-id="48ec6-117">Nell'esempio seguente viene utilizzato CONTAINSTABLE per restituire solo le prime tre corrispondenze.</span><span class="sxs-lookup"><span data-stu-id="48ec6-117">The following example uses CONTAINSTABLE to return only the top three matches.</span></span>  
  
```  
USE AdventureWorks2012  
GO  
  
SELECT K.RANK, AddressLine1, City  
FROM Person.Address AS A  
  INNER JOIN  
  CONTAINSTABLE(Person.Address, AddressLine1, 'ISABOUT ("des*",  
    Rue WEIGHT(0.5),  
    Bouchers WEIGHT(0.9))',  
    3) AS K  
  ON A.AddressID = K.[KEY]  
GO  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
```  
RANK        Address                          City  
----------- -------------------------------- ------------------------------  
172         9005, rue des Bouchers           Paris  
172         5, rue des Bouchers              Orleans  
172         5, rue des Bouchers              Metz  
  
(3 row(s) affected)  
```  
  
  
### <a name="example-b-searching-for-the-top-ten-matches"></a><span data-ttu-id="48ec6-118">Esempio B: Ricerca delle prime dieci corrispondenze</span><span class="sxs-lookup"><span data-stu-id="48ec6-118">Example B: Searching for the top ten matches</span></span>  
 <span data-ttu-id="48ec6-119">Nell'esempio seguente viene utilizzato CONTAINSTABLE per restituire la descrizione dei primi 5 prodotti la cui colonna `Description` include la parola "aluminum" accanto alla parola "light" o "lightweight".</span><span class="sxs-lookup"><span data-stu-id="48ec6-119">The following example uses CONTAINSTABLE to return the description of the top 5 products where the `Description` column contains the word "aluminum" near either the word "light" or the word "lightweight".</span></span>  
  
```  
USE AdventureWorks2012  
GO  
  
SELECT FT_TBL.ProductDescriptionID,  
   FT_TBL.Description,   
   KEY_TBL.RANK  
FROM Production.ProductDescription AS FT_TBL INNER JOIN  
   CONTAINSTABLE (Production.ProductDescription,  
      Description,   
      '(light NEAR aluminum) OR  
      (lightweight NEAR aluminum)',  
      5  
   ) AS KEY_TBL  
   ON FT_TBL.ProductDescriptionID = KEY_TBL.[KEY]  
GO  
```  
  
  
##  <a name="how-search-query-results-are-ranked"></a><a name="how"></a> <span data-ttu-id="48ec6-120">Classificazione per pertinenza dei risultati delle query di ricerca</span><span class="sxs-lookup"><span data-stu-id="48ec6-120">How Search Query Results Are Ranked</span></span>  
 <span data-ttu-id="48ec6-121">In [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] la ricerca full-text può generare un punteggio facoltativo (o valore di pertinenza) che indica la pertinenza dei dati restituiti da una query full-text.</span><span class="sxs-lookup"><span data-stu-id="48ec6-121">Full-text search in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] can generate an optional score (or rank value) that indicates the relevance of the data returned by a full-text query.</span></span> <span data-ttu-id="48ec6-122">Questo valore di pertinenza viene calcolato in ogni riga e può essere utilizzato come criteri di ordinamento del set di risultati di una query basato sulla pertinenza.</span><span class="sxs-lookup"><span data-stu-id="48ec6-122">This rank value is calculated on every row and can be used as an ordering criteria to sort the result set of a given query by relevance.</span></span> <span data-ttu-id="48ec6-123">Il valore di pertinenza indica solo un ordine di pertinenza relativo delle righe nel set di risultati.</span><span class="sxs-lookup"><span data-stu-id="48ec6-123">The rank values indicate only a relative order of relevance of the rows in the result set.</span></span> <span data-ttu-id="48ec6-124">I valori effettivi sono senza importanza e in genere variano ogni volta che viene eseguita la query.</span><span class="sxs-lookup"><span data-stu-id="48ec6-124">The actual values are unimportant and typically differ each time the query is run.</span></span> <span data-ttu-id="48ec6-125">Il valore di pertinenza non mantiene alcun significato nelle query.</span><span class="sxs-lookup"><span data-stu-id="48ec6-125">The rank value does not hold any significance across queries.</span></span>  
  
### <a name="statistics-for-ranking"></a><span data-ttu-id="48ec6-126">Statistiche per il calcolo della pertinenza</span><span class="sxs-lookup"><span data-stu-id="48ec6-126">Statistics for Ranking</span></span>  
 <span data-ttu-id="48ec6-127">Al momento della compilazione di un indice vengono raccolte statistiche per l'utilizzo nei calcolo della pertinenza.</span><span class="sxs-lookup"><span data-stu-id="48ec6-127">When an index is built, statistics are collected for use in ranking.</span></span> <span data-ttu-id="48ec6-128">Il processo di compilazione di un catalogo full-text non conduce direttamente a una singola struttura di indice.</span><span class="sxs-lookup"><span data-stu-id="48ec6-128">The process of building a full-text catalog does not directly result in a single index structure.</span></span> <span data-ttu-id="48ec6-129">Il motore di ricerca full-text per [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , al contrario, crea indici intermedi man mano che i dati vengono indicizzati</span><span class="sxs-lookup"><span data-stu-id="48ec6-129">Instead, the Full-Text Engine for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] creates intermediate indexes as data is indexed.</span></span> <span data-ttu-id="48ec6-130">e successivamente unisce tali indici in un indice di dimensioni maggiori in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="48ec6-130">The Full-Text Engine then merges these indexes into a larger index as needed.</span></span> <span data-ttu-id="48ec6-131">Il processo può essere ripetuto più volte.</span><span class="sxs-lookup"><span data-stu-id="48ec6-131">This process can be repeated many times.</span></span> <span data-ttu-id="48ec6-132">Il motore di ricerca full-text SQL esegue infine un'unione nell'indice master per associare tutti gli indici intermedi in un indice master di dimensioni elevate.</span><span class="sxs-lookup"><span data-stu-id="48ec6-132">The Full-Text Engine then conducts a "master merge" that combines all of the intermediate indexes into one large master index.</span></span>  
  
 <span data-ttu-id="48ec6-133">Le statistiche vengono raccolte a ogni livello di indice intermedio.</span><span class="sxs-lookup"><span data-stu-id="48ec6-133">Statistics are collected at each intermediate index level.</span></span> <span data-ttu-id="48ec6-134">L'unione delle statistiche avviene contemporaneamente a quella degli indici.</span><span class="sxs-lookup"><span data-stu-id="48ec6-134">The statistics are merged when the indexes are merged.</span></span> <span data-ttu-id="48ec6-135">Alcuni valori statistici possono essere generati solo durante il processo di unione nell'indice master.</span><span class="sxs-lookup"><span data-stu-id="48ec6-135">Some statistical values can only be generated during the master merging process.</span></span>  
  
 <span data-ttu-id="48ec6-136">Nella classificazione di un set di risultati della query, in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] vengono utilizzate statistiche in base all'indice intermedio di dimensioni maggiori.</span><span class="sxs-lookup"><span data-stu-id="48ec6-136">While ranking a query result set, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] uses statistics from the largest intermediate index.</span></span> <span data-ttu-id="48ec6-137">Ciò varia a seconda che gli indici intermedi siano stati uniti o meno.</span><span class="sxs-lookup"><span data-stu-id="48ec6-137">This depends on whether intermediate indexes have been merged or not.</span></span> <span data-ttu-id="48ec6-138">Se gli indici intermedi non sono stati uniti, l'accuratezza delle statistiche per il calcolo della pertinenza può variare.</span><span class="sxs-lookup"><span data-stu-id="48ec6-138">As a result, ranking statistics can vary in accuracy if the intermediate indexes have not been merged.</span></span> <span data-ttu-id="48ec6-139">Per questo motivo la stessa query può restituire nel tempo risultati di pertinenza diversi, man mano che i dati con indicizzazione full-text vengono aggiunti, modificati ed eliminati e vengono uniti gli indici più piccoli.</span><span class="sxs-lookup"><span data-stu-id="48ec6-139">This explains why the same query can return different rank results over time as full-text indexed data is added, modified, and deleted, and as the smaller indexes are merged.</span></span>  
  
 <span data-ttu-id="48ec6-140">Per ridurre al minimo le dimensioni dell'indice e la complessità del calcolo, le statistiche vengono spesso arrotondate.</span><span class="sxs-lookup"><span data-stu-id="48ec6-140">To minimize the size of the index and computational complexity, statistics are often rounded.</span></span>  
  
 <span data-ttu-id="48ec6-141">Nell'elenco seguente sono inclusi alcuni termini e valori statistici utilizzati di frequente e importanti per calcolare il valore di pertinenza:</span><span class="sxs-lookup"><span data-stu-id="48ec6-141">The list below includes some commonly used terms and statistical values that are important in calculating rank.</span></span>  
  
 <span data-ttu-id="48ec6-142">Proprietà</span><span class="sxs-lookup"><span data-stu-id="48ec6-142">Property</span></span>  
 <span data-ttu-id="48ec6-143">Una colonna con indicizzazione full-text della riga.</span><span class="sxs-lookup"><span data-stu-id="48ec6-143">A full-text indexed column of the row.</span></span>  
  
 <span data-ttu-id="48ec6-144">Document</span><span class="sxs-lookup"><span data-stu-id="48ec6-144">Document</span></span>  
 <span data-ttu-id="48ec6-145">L'entità restituita nelle query.</span><span class="sxs-lookup"><span data-stu-id="48ec6-145">The entity that is returned in queries.</span></span> <span data-ttu-id="48ec6-146">In [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] corrisponde a una riga.</span><span class="sxs-lookup"><span data-stu-id="48ec6-146">In [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] this corresponds to a row.</span></span> <span data-ttu-id="48ec6-147">Un documento può disporre di più proprietà, esattamente come una riga può includere più colonne con indicizzazione full-text.</span><span class="sxs-lookup"><span data-stu-id="48ec6-147">A document can have multiple properties, just as a row can have multiple full-text indexed columns.</span></span>  
  
 <span data-ttu-id="48ec6-148">Indice</span><span class="sxs-lookup"><span data-stu-id="48ec6-148">Index</span></span>  
 <span data-ttu-id="48ec6-149">Un singolo indice invertito di uno o più documenti.</span><span class="sxs-lookup"><span data-stu-id="48ec6-149">A single inverted index of one or more documents.</span></span> <span data-ttu-id="48ec6-150">Può essere contenuto completamente nella memoria o su disco.</span><span class="sxs-lookup"><span data-stu-id="48ec6-150">This may be entirely in memory or on disk.</span></span> <span data-ttu-id="48ec6-151">Molte statistiche di query riguardano l'indice specifico nel quale si è verificata la corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="48ec6-151">Many query statistics are relative to the individual index where the match occurred.</span></span>  
  
 <span data-ttu-id="48ec6-152">Catalogo full-text</span><span class="sxs-lookup"><span data-stu-id="48ec6-152">Full-Text Catalog</span></span>  
 <span data-ttu-id="48ec6-153">Una raccolta di indici intermedi gestita come singola entità per le query.</span><span class="sxs-lookup"><span data-stu-id="48ec6-153">A collection of intermediate indexes treated as one entity for queries.</span></span> <span data-ttu-id="48ec6-154">I cataloghi rappresentano l'unità di organizzazione visibile all'amministratore di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="48ec6-154">Catalogs are the unit of organization visible to the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] administrator.</span></span>  
  
 <span data-ttu-id="48ec6-155">Word, token o item</span><span class="sxs-lookup"><span data-stu-id="48ec6-155">Word, token or item</span></span>  
 <span data-ttu-id="48ec6-156">L'unità di corrispondenza del motore full-text.</span><span class="sxs-lookup"><span data-stu-id="48ec6-156">The unit of matching in the full-text engine.</span></span> <span data-ttu-id="48ec6-157">I flussi di testo dai documenti vengono suddivisi in parole o token da word breaker specifici della lingua.</span><span class="sxs-lookup"><span data-stu-id="48ec6-157">Streams of text from documents are tokenized into words, or tokens by language-specific word breakers.</span></span>  
  
 <span data-ttu-id="48ec6-158">Occorrenza</span><span class="sxs-lookup"><span data-stu-id="48ec6-158">Occurrence</span></span>  
 <span data-ttu-id="48ec6-159">L'offset delle parole in una proprietà del documento, determinato dal word breaker.</span><span class="sxs-lookup"><span data-stu-id="48ec6-159">The word offset in a document property as determined by the word breaker.</span></span> <span data-ttu-id="48ec6-160">La prima parola corrisponde all'occorrenza 1, quella successiva all'occorrenza 2 e così via.</span><span class="sxs-lookup"><span data-stu-id="48ec6-160">The first word is at occurrence 1, the next at 2, and so on.</span></span> <span data-ttu-id="48ec6-161">Per evitare falsi positivi nelle query su frasi e di prossimità, indicatori di fine frase e indicatori di fine paragrafo introducono gap di occorrenza più grandi.</span><span class="sxs-lookup"><span data-stu-id="48ec6-161">In order to avoid false positives in phrase and proximity queries, end-of-sentence and end-of-paragraph introduce larger occurrence gaps.</span></span>  
  
 <span data-ttu-id="48ec6-162">TermFrequency</span><span class="sxs-lookup"><span data-stu-id="48ec6-162">TermFrequency</span></span>  
 <span data-ttu-id="48ec6-163">Il numero di volte che il valore della chiave è presente in una riga.</span><span class="sxs-lookup"><span data-stu-id="48ec6-163">The number times the key value occurs in a row.</span></span>  
  
 <span data-ttu-id="48ec6-164">IndexedRowCount</span><span class="sxs-lookup"><span data-stu-id="48ec6-164">IndexedRowCount</span></span>  
 <span data-ttu-id="48ec6-165">Il numero totale di righe indicizzate.</span><span class="sxs-lookup"><span data-stu-id="48ec6-165">Total number of rows indexed.</span></span> <span data-ttu-id="48ec6-166">Viene calcolato in base ai conteggi gestiti negli indici intermedi.</span><span class="sxs-lookup"><span data-stu-id="48ec6-166">This is computed, based on counts maintained in the intermediate indexes.</span></span> <span data-ttu-id="48ec6-167">L'accuratezza di questo numero può variare.</span><span class="sxs-lookup"><span data-stu-id="48ec6-167">This number can vary in accuracy.</span></span>  
  
 <span data-ttu-id="48ec6-168">KeyRowCount</span><span class="sxs-lookup"><span data-stu-id="48ec6-168">KeyRowCount</span></span>  
 <span data-ttu-id="48ec6-169">Il numero totale di righe nel catalogo full-text contenenti una chiave specifica.</span><span class="sxs-lookup"><span data-stu-id="48ec6-169">Total number of rows in the full-text catalog that contain a given key.</span></span>  
  
 <span data-ttu-id="48ec6-170">MaxOccurrence</span><span class="sxs-lookup"><span data-stu-id="48ec6-170">MaxOccurrence</span></span>  
 <span data-ttu-id="48ec6-171">Il valore di occorrenza più grande archiviato in un catalogo full-text per una proprietà specifica di una riga.</span><span class="sxs-lookup"><span data-stu-id="48ec6-171">The largest occurrence stored in a full-text catalog for a given property in a row.</span></span>  
  
 <span data-ttu-id="48ec6-172">MaxQueryRank</span><span class="sxs-lookup"><span data-stu-id="48ec6-172">MaxQueryRank</span></span>  
 <span data-ttu-id="48ec6-173">Il valore di pertinenza massimo, 1000, restituito dal motore di ricerca full-text.</span><span class="sxs-lookup"><span data-stu-id="48ec6-173">The maximum rank, 1000, returned by the Full-Text Engine.</span></span>  
  
  
### <a name="rank-computation-issues"></a><span data-ttu-id="48ec6-174">Problemi nel calcolo della pertinenza</span><span class="sxs-lookup"><span data-stu-id="48ec6-174">Rank Computation Issues</span></span>  
 <span data-ttu-id="48ec6-175">Il processo di calcolo della pertinenza dipende da alcuni fattori.</span><span class="sxs-lookup"><span data-stu-id="48ec6-175">The process of computing rank, depends on a number of factors.</span></span>  <span data-ttu-id="48ec6-176">I word breaker delle diverse lingue suddividono il testo in token in modo diverso.</span><span class="sxs-lookup"><span data-stu-id="48ec6-176">Different language word breakers tokenize text differently.</span></span> <span data-ttu-id="48ec6-177">La stringa "pick-up", ad esempio, potrebbe essere suddivisa in "pick" "up" da un word breaker e in "pick-up" da un altro.</span><span class="sxs-lookup"><span data-stu-id="48ec6-177">For example, the string "dog-house" could be broken into "dog" "house" by one word breaker and into "dog-house" by another.</span></span> <span data-ttu-id="48ec6-178">Ciò significa che la corrispondenza e il calcolo della pertinenza variano in base alla lingua specificata, poiché non solo le parole sono diverse, ma lo è anche la lunghezza dei documenti.</span><span class="sxs-lookup"><span data-stu-id="48ec6-178">This means that matching and ranking will vary based on the language specified, because not only are the words different, but so is the document length.</span></span> <span data-ttu-id="48ec6-179">La differenza di lunghezza dei documenti può influire sul calcolo della pertinenza per tutte le query.</span><span class="sxs-lookup"><span data-stu-id="48ec6-179">The document length difference can affect ranking for all queries.</span></span>  
  
 <span data-ttu-id="48ec6-180">Statistiche quali `IndexRowCount` possono variare notevolmente.</span><span class="sxs-lookup"><span data-stu-id="48ec6-180">Statistics such as `IndexRowCount` can vary widely.</span></span> <span data-ttu-id="48ec6-181">Se, ad esempio, un catalogo presenta 2 miliardi di righe nell'indice master, un nuovo documento viene indicizzato in un indice intermedio in memoria e la pertinenza corrispondente basata sul numero di documenti dell'indice in memoria potrebbe essere asimmetrica rispetto alla pertinenza per i documenti dall'indice master.</span><span class="sxs-lookup"><span data-stu-id="48ec6-181">For example, if a catalog has 2 billion rows in the master index, then one new document is indexed into an in-memory intermediate index, and ranks for that document based on the number of documents in the in-memory index could be skewed compared with ranks for documents from the master index.</span></span> <span data-ttu-id="48ec6-182">Per questo motivo, dopo ogni popolamento che determini l'indicizzazione o la reindicizzazione di un grande numero di righe è consigliabile unire gli indici in un indice master utilizzando l'istruzione ALTER FULLTEXT CATALOG ... Istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] REORGANIZE.</span><span class="sxs-lookup"><span data-stu-id="48ec6-182">For this reason, it is recommended that after any population that results in large number of rows being indexed or re-indexed the indexes be merged into a master index using the ALTER FULLTEXT CATALOG ... REORGANIZE [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span> <span data-ttu-id="48ec6-183">Il motore di ricerca full-text, inoltre, unirà automaticamente gli indici in base a parametri quali il numero e le dimensioni di indici intermedi.</span><span class="sxs-lookup"><span data-stu-id="48ec6-183">The Full-Text Engine will also automatically merge the indexes based on parameters such as the number and size of intermediate indexes.</span></span>  
  
 <span data-ttu-id="48ec6-184">I valori `MaxOccurrence` vengono normalizzati in 1 di 32 intervalli.</span><span class="sxs-lookup"><span data-stu-id="48ec6-184">`MaxOccurrence` values are normalized into 1 of 32 ranges.</span></span> <span data-ttu-id="48ec6-185">Ciò significa, ad esempio, che un documento di 50 parole di lunghezza viene gestito come un documento di 100 parole.</span><span class="sxs-lookup"><span data-stu-id="48ec6-185">This means, for example, that a document 50 words long is treated the same as a document 100 words long.</span></span> <span data-ttu-id="48ec6-186">Di seguito viene riportata la tabella utilizzata per la normalizzazione.</span><span class="sxs-lookup"><span data-stu-id="48ec6-186">Below is the table used for normalization.</span></span> <span data-ttu-id="48ec6-187">Poiché le lunghezze dei documenti rientrano nell'intervallo tra i valori di tabella adiacenti 32 e 128, vengono trattati in modo efficace con la stessa lunghezza, 128 (32 < `docLength` <= 128).</span><span class="sxs-lookup"><span data-stu-id="48ec6-187">Because the document lengths are in the range between adjacent table values 32 and 128, they are effectively treated as having the same length, 128 (32 < `docLength` <= 128).</span></span>  
  
```  
{ 16, 32, 128, 256, 512, 725, 1024, 1450, 2048, 2896, 4096, 5792, 8192, 11585,   
16384, 23170, 28000, 32768, 39554, 46340, 55938, 65536, 92681, 131072, 185363,   
262144, 370727, 524288, 741455, 1048576, 2097152, 4194304 };  
  
```  
  
  
### <a name="ranking-of-containstable"></a><span data-ttu-id="48ec6-188">Calcolo della pertinenza di CONTAINSTABLE</span><span class="sxs-lookup"><span data-stu-id="48ec6-188">Ranking of CONTAINSTABLE</span></span>  
 <span data-ttu-id="48ec6-189">Per il calcolo della pertinenza di[CONTAINSTABLE](/sql/relational-databases/system-functions/containstable-transact-sql) viene usato l'algoritmo seguente:</span><span class="sxs-lookup"><span data-stu-id="48ec6-189">[CONTAINSTABLE](/sql/relational-databases/system-functions/containstable-transact-sql) ranking uses the following algorithm:</span></span>  
  
```  
StatisticalWeight = Log2( ( 2 + IndexedRowCount ) / KeyRowCount )  
Rank = min( MaxQueryRank, HitCount * 16 * StatisticalWeight / MaxOccurrence )  
```  
  
 <span data-ttu-id="48ec6-190">Il calcolo della pertinenza per le corrispondenze di frase è analogo a quello delle chiavi singole, tranne per il fatto che `KeyRowCount` (il numero di righe contenenti la frase) è il risultato di una stima e può essere impreciso e maggiore del numero effettivo.</span><span class="sxs-lookup"><span data-stu-id="48ec6-190">Phrase matches are ranked just like individual keys except that `KeyRowCount` (the number of rows containing the phrase) is estimated and can be inaccurate and higher than the actual number.</span></span>  
  
 <span data-ttu-id="48ec6-191">**Calcolo della pertinenza di NEAR**</span><span class="sxs-lookup"><span data-stu-id="48ec6-191">**Ranking of NEAR**</span></span>  
  
 <span data-ttu-id="48ec6-192">CONTAINSTABLE supporta l'esecuzione di query per due o più termini di ricerca prossimi l'uno all'altro tramite l'opzione NEAR.</span><span class="sxs-lookup"><span data-stu-id="48ec6-192">CONTAINSTABLE supports querying for two or more search terms in proximity to each other by using the NEAR option.</span></span> <span data-ttu-id="48ec6-193">Il valore di pertinenza di ogni riga restituita è basato su diversi parametri.</span><span class="sxs-lookup"><span data-stu-id="48ec6-193">The rank value of each returned row is based on several parameters.</span></span> <span data-ttu-id="48ec6-194">Un importante fattore di pertinenza è il numero complessivo di corrispondenze (o *riscontri*) in relazione alla lunghezza del documento.</span><span class="sxs-lookup"><span data-stu-id="48ec6-194">One major ranking factor is the total number of matches (or *hits*) relative to the length of the document.</span></span> <span data-ttu-id="48ec6-195">Pertanto se, ad esempio, un documento di 100 parole e un documento 900 parole contengono corrispondenze identiche, il documento di 100 parole avrà un valore di pertinenza più in alto.</span><span class="sxs-lookup"><span data-stu-id="48ec6-195">Thus, for example, if a 100-word document and a 900-word document contain identical matches, the 100-word document is ranked higher.</span></span>  
  
 <span data-ttu-id="48ec6-196">La lunghezza totale di ogni riscontro in una riga contribuirà inoltre al calcolo della pertinenza di tale riga in base alla distanza tra i primo e l'ultimo termine di ricerca di tale riscontro.</span><span class="sxs-lookup"><span data-stu-id="48ec6-196">The total length of each hit in a row will also contribute to the ranking of that row based on the distance between the first and last search terms of that hit.</span></span> <span data-ttu-id="48ec6-197">Minore è la distanza, maggiore sarà il contributo del riscontro al valore di pertinenza della riga.</span><span class="sxs-lookup"><span data-stu-id="48ec6-197">The smaller the distance, the more the hit contributes to the rank value of the row.</span></span> <span data-ttu-id="48ec6-198">Se in una query full-text non viene specificato un valore intero come distanza massima, un documento che contiene solo riscontri le cui distanze sono maggiori di 100 termini logici avrà un valore di pertinenza pari a 0.</span><span class="sxs-lookup"><span data-stu-id="48ec6-198">If a full-text query does not specify an integer as the maximum distance, a document that contains only hits whose distances are greater than 100 logical terms apart, will have a ranking of 0.</span></span>  
  
 <span data-ttu-id="48ec6-199">**Calcolo della pertinenza di ISABOUT**</span><span class="sxs-lookup"><span data-stu-id="48ec6-199">**Ranking of ISABOUT**</span></span>  
  
 <span data-ttu-id="48ec6-200">CONTAINSTABLE consente di eseguire query per termini ponderati tramite l'opzione ISABOUT.</span><span class="sxs-lookup"><span data-stu-id="48ec6-200">CONTAINSTABLE supports querying for weighted terms by using the ISABOUT option.</span></span> <span data-ttu-id="48ec6-201">ISABOUT è una query per lo spazio vettoriale nella terminologia tradizionale relativa al recupero delle informazioni.</span><span class="sxs-lookup"><span data-stu-id="48ec6-201">ISABOUT is a vector-space query in traditional information retrieval terminology.</span></span> <span data-ttu-id="48ec6-202">L'algoritmo predefinito per il calcolo della pertinenza è di tipo Jaccard, una formula molto nota.</span><span class="sxs-lookup"><span data-stu-id="48ec6-202">The default ranking algorithm used is Jaccard, a widely known formula.</span></span> <span data-ttu-id="48ec6-203">La pertinenza viene calcolata per ogni termine nella query, quindi combinata come descritto di seguito.</span><span class="sxs-lookup"><span data-stu-id="48ec6-203">The ranking is computed for each term in the query and then combined as described below.</span></span>  
  
```  
ContainsRank = same formula used for CONTAINSTABLE ranking of a single term (above).  
Weight = the weight specified in the query for each term. Default weight is 1.  
WeightedSum = ??[key=1 to n] ContainsRankKey * WeightKey  
Rank =  ( MaxQueryRank * WeightedSum ) / ( ( ??[key=1 to n] ContainsRankKey^2 )   
      + ( ??[key=1 to n] WeightKey^2 ) - ( WeightedSum ) )  
  
```  
  
  
### <a name="ranking-of-freetexttable"></a><span data-ttu-id="48ec6-204">Calcolo della pertinenza di FREETEXTTABLE</span><span class="sxs-lookup"><span data-stu-id="48ec6-204">Ranking of FREETEXTTABLE</span></span>  
 <span data-ttu-id="48ec6-205">Il calcolo della pertinenza di[FREETEXTTABLE](/sql/relational-databases/system-functions/freetexttable-transact-sql) si basa sulla formula OKAPI BM25.</span><span class="sxs-lookup"><span data-stu-id="48ec6-205">[FREETEXTTABLE](/sql/relational-databases/system-functions/freetexttable-transact-sql) ranking is based on the OKAPI BM25 ranking formula.</span></span> <span data-ttu-id="48ec6-206">Le query FREETEXTTABLE aggiungono parole alla query tramite generazione flessiva (forme flesse delle parole della query originale). Queste parole vengono gestite separatamente, senza nessuna relazione particolare con le parole di origine.</span><span class="sxs-lookup"><span data-stu-id="48ec6-206">FREETEXTTABLE queries will add words to the query via inflectional generation (inflected forms of the original query words); these words are treated as separate words with no special relationship to the words from which they were generated.</span></span> <span data-ttu-id="48ec6-207">I sinonimi generati dal thesaurus vengono gestiti come termini separati, con lo stesso valore ponderato.</span><span class="sxs-lookup"><span data-stu-id="48ec6-207">Synonyms generated from the Thesaurus feature are treated as separate, equally weighted terms.</span></span> <span data-ttu-id="48ec6-208">Ogni parola nella query contribuisce alla pertinenza.</span><span class="sxs-lookup"><span data-stu-id="48ec6-208">Each word in the query contributes to the rank.</span></span>  
  
```  
Rank = ??[Terms in Query] w ( ( ( k1 + 1 ) tf ) / ( K + tf ) ) * ( ( k3 + 1 ) qtf / ( k3 + qtf ) ) )  
Where:   
w is the Robertson-Sparck Jones weight.   
In simplified form, w is defined as:   
w = log10 ( ( ( r + 0.5 ) * ( N - R + r + 0.5 ) ) / ( ( R - r + 0.5 ) * ( n - r + 0.5 ) )  
N is the number of indexed rows for the property being queried.   
n is the number of rows containing the word.   
K is ( k1 * ( ( 1 - b ) + ( b * dl / avdl ) ) ).   
dl is the property length, in word occurrences.   
avdl is the average length of the property being queried, in word occurrences.   
k1, b, and k3 are the constants 1.2, 0.75, and 8.0, respectively.   
tf is the frequency of the word in the queried property in a specific row.   
qtf is the frequency of the term in the query.   
```  
  
  
## <a name="see-also"></a><span data-ttu-id="48ec6-209">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="48ec6-209">See Also</span></span>  
 [<span data-ttu-id="48ec6-210">Eseguire query con ricerca full-text</span><span class="sxs-lookup"><span data-stu-id="48ec6-210">Query with Full-Text Search</span></span>](query-with-full-text-search.md)  
  
  
