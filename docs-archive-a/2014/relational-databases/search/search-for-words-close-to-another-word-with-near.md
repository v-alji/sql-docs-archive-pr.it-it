---
title: Cercare parole vicine a un'altra parola con NEAR | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- word searches [full-text search]
- NEAR option [full-text search]
- phrase searches [full-text search]
- proximity searches [full-text search]
- full-text search [SQL Server], proximity searches
- full-text queries [SQL Server], proximity
- queries [full-text search], proximity
ms.assetid: 87520646-4865-49ae-8790-f766b80a41f3
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8c2d187ea3ed951ac6f17eb4babc5f4f77451d4e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719818"
---
# <a name="search-for-words-close-to-another-word-with-near"></a><span data-ttu-id="bf1ff-102">Ricerca di parole vicine a un'altra parola con NEAR</span><span class="sxs-lookup"><span data-stu-id="bf1ff-102">Search for Words Close to Another Word with NEAR</span></span>
  <span data-ttu-id="bf1ff-103">Per cercare parole o frasi vicine, è possibile usare un termine di prossimità (NEAR) in un predicato [CONTAINS](/sql/t-sql/queries/contains-transact-sql) o in una funzione [CONTAINSTABLE](/sql/relational-databases/system-functions/containstable-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="bf1ff-103">You can use a proximity term (NEAR) in a [CONTAINS](/sql/t-sql/queries/contains-transact-sql) predicate or [CONTAINSTABLE](/sql/relational-databases/system-functions/containstable-transact-sql) function to search for words or phrases near one another.</span></span> <span data-ttu-id="bf1ff-104">È inoltre possibile specificare il numero massimo di termini non di ricerca che separano il primo e l'ultimo termine di ricerca.</span><span class="sxs-lookup"><span data-stu-id="bf1ff-104">You can also specify the maximum number of non-search terms that separate the first and last search terms.</span></span> <span data-ttu-id="bf1ff-105">È inoltre possibile cercare parole o frasi in qualsiasi ordine o parole e frasi nell'ordine in cui sono state specificate.</span><span class="sxs-lookup"><span data-stu-id="bf1ff-105">In addition, you can search for words or phrases in any order, or you can search for words and phrases in the order in which you specify them.</span></span> [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]<span data-ttu-id="bf1ff-106">supporta sia il [termine di prossimità generico](#Generic_NEAR)precedente, che è ora deprecato, che il [termine di prossimità personalizzato](#Custom_NEAR), che è nuovo in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bf1ff-106">supports both the earlier [generic proximity term](#Generic_NEAR), which is now deprecated, and the [custom proximity term](#Custom_NEAR), which is new in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)].</span></span>  
  
##  <a name="the-custom-proximity-term"></a><a name="Custom_NEAR"></a><span data-ttu-id="bf1ff-107">Termine di prossimità personalizzato</span><span class="sxs-lookup"><span data-stu-id="bf1ff-107">The Custom Proximity Term</span></span>  
 <span data-ttu-id="bf1ff-108">Con il termine di prossimità personalizzato vengono introdotte le seguenti nuove funzionalità:</span><span class="sxs-lookup"><span data-stu-id="bf1ff-108">The custom proximity term introduces the following new capabilities:</span></span>  
  
-   <span data-ttu-id="bf1ff-109">È possibile specificare il numero massimo di termini non di ricerca, oppure la *distanza massima*che separa il primo e l'ultimo termine di ricerca per formare una corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="bf1ff-109">You can specify the maximum number of non-search terms, or *maximum distance*, that separates the first and last search terms in order to constitute a match.</span></span>  
  
-   <span data-ttu-id="bf1ff-110">Se si specifica il numero massimo di termini, è inoltre possibile specificare che nelle corrispondenze devono essere inclusi i termini di ricerca nell'ordine specificato.</span><span class="sxs-lookup"><span data-stu-id="bf1ff-110">If you specify the maximum number of terms, you can also specify that matches must contain the search terms in the specified order.</span></span>  
  
 <span data-ttu-id="bf1ff-111">Per essere considerata una corrispondenza, una stringa di testo deve soddisfare i seguenti requisiti:</span><span class="sxs-lookup"><span data-stu-id="bf1ff-111">To qualify as a match, a string of text must:</span></span>  
  
-   <span data-ttu-id="bf1ff-112">Iniziare con uno dei termini di ricerca specificati e terminare con uno degli altri termini di ricerca specificati.</span><span class="sxs-lookup"><span data-stu-id="bf1ff-112">Start with one of the specified search terms and end with the one of the other specified search terms.</span></span>  
  
-   <span data-ttu-id="bf1ff-113">Contenere tutti i termini di ricerca specificati.</span><span class="sxs-lookup"><span data-stu-id="bf1ff-113">Contain all of the specified search terms.</span></span>  
  
-   <span data-ttu-id="bf1ff-114">Il numero di termini non di ricerca, incluse le parole non significative, presenti tra i primo e l'ultimo termine di ricerca deve essere minore o uguale alla distanza massima, se specificato.</span><span class="sxs-lookup"><span data-stu-id="bf1ff-114">The number of non-search terms, including stopwords, that occur between the first and last search terms must be less than or equal to the maximum distance, if specified.</span></span>  
  
 <span data-ttu-id="bf1ff-115">La sintassi di base è la seguente:</span><span class="sxs-lookup"><span data-stu-id="bf1ff-115">The basic syntax is:</span></span>  
  
 <span data-ttu-id="bf1ff-116">NEAR (</span><span class="sxs-lookup"><span data-stu-id="bf1ff-116">NEAR (</span></span>  
  
 <span data-ttu-id="bf1ff-117">{</span><span class="sxs-lookup"><span data-stu-id="bf1ff-117">{</span></span>  
  
 <span data-ttu-id="bf1ff-118">*search_term* [,... *n* ]</span><span class="sxs-lookup"><span data-stu-id="bf1ff-118">*search_term* [ ,...*n* ]</span></span>  
  
 |  
  
 <span data-ttu-id="bf1ff-119">(*search_term* [,... *n* ]) [, <maximum_distance> [, <match_order>]]</span><span class="sxs-lookup"><span data-stu-id="bf1ff-119">(*search_term* [ ,...*n* ] ) [, <maximum_distance> [, <match_order> ] ]</span></span>  
  
 <span data-ttu-id="bf1ff-120">}</span><span class="sxs-lookup"><span data-stu-id="bf1ff-120">}</span></span>  
  
 <span data-ttu-id="bf1ff-121">)</span><span class="sxs-lookup"><span data-stu-id="bf1ff-121">)</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bf1ff-122">Per altre informazioni sulla sintassi di <custom_proximity_term>, vedere [CONTAINS &#40;Transact-SQL&#41;](/sql/t-sql/queries/contains-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="bf1ff-122">For more information about the <custom_proximity_term> syntax, see [CONTAINS &#40;Transact-SQL&#41;](/sql/t-sql/queries/contains-transact-sql).</span></span>  
  
 <span data-ttu-id="bf1ff-123">È possibile, ad esempio, cercare 'John' entro due termini 'Smith', come segue:</span><span class="sxs-lookup"><span data-stu-id="bf1ff-123">For example, you could search for 'John' within two terms of 'Smith', as follows:</span></span>  
  
```  
CONTAINS(column_name, 'NEAR((John, Smith), 2)')  
```  
  
 <span data-ttu-id="bf1ff-124">Esempi di stringhe corrispondenti sono "`John Jacob Smith`" e "`Smith, John`".</span><span class="sxs-lookup"><span data-stu-id="bf1ff-124">Some examples of strings that match are "`John Jacob Smith`" and "`Smith, John`".</span></span> <span data-ttu-id="bf1ff-125">La stringa "`John Jones knows Fred Smith`" include tre termini non di ricerca intermedi, pertanto non è una corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="bf1ff-125">The string "`John Jones knows Fred Smith`" contains three intervening non-search terms, so it is not a match.</span></span>  
  
 <span data-ttu-id="bf1ff-126">Per ottenere che i termini vengano trovati nell'ordine specificato, modificare il termine di prossimità di esempio in `NEAR((John, Smith),2, TRUE).` In questo modo viene effettuata la ricerca di "`John`" entro due termini "`Smith`", ma solo quando "`John`" precede "`Smith`".</span><span class="sxs-lookup"><span data-stu-id="bf1ff-126">To require that the terms be found in the specified order, you would change the example proximity term to `NEAR((John, Smith),2, TRUE).` This searches for "`John`" within two terms of "`Smith`" but only when "`John`" precedes "`Smith`".</span></span> <span data-ttu-id="bf1ff-127">In una lingua con direzione di lettura da sinistra a destra, ad esempio la lingua inglese, un esempio di stringa corrispondente è il seguente: "`John Jacob Smith`".</span><span class="sxs-lookup"><span data-stu-id="bf1ff-127">In a language that reads from left to right, such as English, an example of a string that matches is "`John Jacob Smith`".</span></span>  
  
 <span data-ttu-id="bf1ff-128">Si noti che per le lingue con lettura da destra a sinistra, come l'arabo o l'ebraico, i termini specificati vengono applicati in ordine inverso dal motore di ricerca full-text.</span><span class="sxs-lookup"><span data-stu-id="bf1ff-128">Note that for a language that reads from right to left, such as Arabic or Hebrew, the Full-Text Engine applies the specified terms in reverse order.</span></span> <span data-ttu-id="bf1ff-129">L'ordine di visualizzazione di parole specificate nelle lingue con scrittura da destra a sinistra viene inoltre invertito automaticamente da Esplora oggetti in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bf1ff-129">Also, Object Explorer in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] automatically reverses the display order of words specified in right-to-left languages.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bf1ff-130">Per altre informazioni, vedere "[Considerazioni aggiuntive per le ricerche per prossimità](#Additional_Considerations)" più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="bf1ff-130">For more information, see "[Additional Considerations about Proximity Searches](#Additional_Considerations)," later in this topic.</span></span>  
  
### <a name="how-maximum-distance-is-measured"></a><span data-ttu-id="bf1ff-131">Modalità di misurazione della distanza massima</span><span class="sxs-lookup"><span data-stu-id="bf1ff-131">How Maximum Distance Is Measured</span></span>  
 <span data-ttu-id="bf1ff-132">Una distanza massima specifica, ad esempio 10 o 25, determina il numero di termini non di ricerca, incluse le parole non significative, che possono essere presenti tra il primo e l'ultimo termine di ricerca in una determinata stringa.</span><span class="sxs-lookup"><span data-stu-id="bf1ff-132">A specific maximum distance, such as 10 or 25, determines how many non-search terms, including stopwords, can occur between the first and last search terms in a given string.</span></span> <span data-ttu-id="bf1ff-133">Ad esempio, `NEAR((dogs, cats, "hunting mice"), 3)` restituirà la riga seguente nella quale sono complessivamente presenti tre termini non di ricerca ("`enjoy`", "`but`" e "`avoid`"):</span><span class="sxs-lookup"><span data-stu-id="bf1ff-133">For example, `NEAR((dogs, cats, "hunting mice"), 3)` would return the following row, in which the total number of non-search terms is three ("`enjoy`", "`but`", and "`avoid`"):</span></span>  
  
 <span data-ttu-id="bf1ff-134">"`Cats` `enjoy` `hunting mice``, but avoid` `dogs``.`"</span><span class="sxs-lookup"><span data-stu-id="bf1ff-134">"`Cats` `enjoy` `hunting mice``, but avoid` `dogs``.`"</span></span>  
  
 <span data-ttu-id="bf1ff-135">Lo stesso termine di prossimità non restituirà la riga seguente, perché la distanza massima viene superata dai quattro termini non di ricerca ("`enjoy`", "`but`", "`usually`" e "`avoid`"):</span><span class="sxs-lookup"><span data-stu-id="bf1ff-135">The same proximity term would not return the following row, because the maximum distance is exceeded by the four non-search terms ("`enjoy`", "`but`", "`usually`", and "`avoid`"):</span></span>  
  
 <span data-ttu-id="bf1ff-136">"`Cats` `enjoy` `hunting mice``, but usually avoid` `dogs``.`"</span><span class="sxs-lookup"><span data-stu-id="bf1ff-136">"`Cats` `enjoy` `hunting mice``, but usually avoid` `dogs``.`"</span></span>  
  
### <a name="combining-a-custom-proximity-term-with-other-terms"></a><span data-ttu-id="bf1ff-137">Combinazione di un termine di prossimità personalizzato con altri termini</span><span class="sxs-lookup"><span data-stu-id="bf1ff-137">Combining a Custom Proximity Term with Other Terms</span></span>  
 <span data-ttu-id="bf1ff-138">È possibile combinare un termine di prossimità personalizzato con alcuni altri termini.</span><span class="sxs-lookup"><span data-stu-id="bf1ff-138">You can combine a custom proximity term with some other terms.</span></span> <span data-ttu-id="bf1ff-139">È possibile usare AND (&), OR (|) oppure AND NOT (&!) per combinare un termine di prossimità personalizzato con un altro termine di prossimità personalizzato, un termine semplice o un termine prefisso.</span><span class="sxs-lookup"><span data-stu-id="bf1ff-139">You can use AND (&), OR (|), or AND NOT (&!) to combine a custom proximity term with another custom proximity term, a simple term, or a prefix term.</span></span> <span data-ttu-id="bf1ff-140">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="bf1ff-140">For example:</span></span>  
  
-   <span data-ttu-id="bf1ff-141">CONTAINS('NEAR((*term1*,*term2*),5) AND *term3*')</span><span class="sxs-lookup"><span data-stu-id="bf1ff-141">CONTAINS('NEAR((*term1*,*term2*),5) AND *term3*')</span></span>  
  
-   <span data-ttu-id="bf1ff-142">CONTAINS('NEAR((*term1*,*term2*),5) OR *term3*')</span><span class="sxs-lookup"><span data-stu-id="bf1ff-142">CONTAINS('NEAR((*term1*,*term2*),5) OR *term3*')</span></span>  
  
-   <span data-ttu-id="bf1ff-143">CONTAINS('NEAR((*term1*,*term2*),5) AND NOT *term3*')</span><span class="sxs-lookup"><span data-stu-id="bf1ff-143">CONTAINS('NEAR((*term1*,*term2*),5) AND NOT *term3*')</span></span>  
  
-   <span data-ttu-id="bf1ff-144">CONTAINS('NEAR((*term1*,*term2*),5) AND NEAR((*term3*,*term4*),2)')</span><span class="sxs-lookup"><span data-stu-id="bf1ff-144">CONTAINS('NEAR((*term1*,*term2*),5) AND NEAR((*term3*,*term4*),2)')</span></span>  
  
-   <span data-ttu-id="bf1ff-145">CONTAINS('NEAR((*term1*,*term2*),5) OR NEAR((*term3*,*term4*),2, TRUE)')</span><span class="sxs-lookup"><span data-stu-id="bf1ff-145">CONTAINS('NEAR((*term1*,*term2*),5) OR NEAR((*term3*,*term4*),2, TRUE)')</span></span>  
  
 <span data-ttu-id="bf1ff-146">ad esempio:</span><span class="sxs-lookup"><span data-stu-id="bf1ff-146">For example,</span></span>  
  
```  
CONTAINS(column_name, 'NEAR((term1, term2), 5, TRUE) AND term3')  
```  
  
 <span data-ttu-id="bf1ff-147">Non è possibile combinare un termine di prossimità personalizzato con un termine di prossimità generico (*Term1* near *Term2*), un termine di generazione (noabout...) o un termine ponderato (FORMSOF...).</span><span class="sxs-lookup"><span data-stu-id="bf1ff-147">You cannot combine a custom proximity term with a generic proximity term (*term1* NEAR *term2*), a generation term (ISABOUT ...), or a weighted term (FORMSOF ...).</span></span>  
  
### <a name="example-using-the-custom-proximity-term"></a><span data-ttu-id="bf1ff-148">Esempio: Utilizzo del termine di prossimità personalizzato</span><span class="sxs-lookup"><span data-stu-id="bf1ff-148">Example: Using the Custom Proximity Term</span></span>  
 <span data-ttu-id="bf1ff-149">Nell'esempio seguente viene effettuata la ricerca nella tabella `Production.Document` del database di esempio `AdventureWorks2012` di tutti i riepiloghi di documenti che contengono sia la parola "riflettore" che la parola "supporto".</span><span class="sxs-lookup"><span data-stu-id="bf1ff-149">The following example searches the `Production.Document` table of the `AdventureWorks2012` sample database for all document summaries that contain the word "reflector" in the same document as the word "bracket".</span></span>  
  
```  
SELECT DocumentNode, Title, DocumentSummary  
FROM Production.Document AS DocTable   
INNER JOIN CONTAINSTABLE(Production.Document, Document,  
  'NEAR(bracket, reflector)' ) AS KEY_TBL  
  ON DocTable.DocumentNode = KEY_TBL.[KEY]  
WHERE KEY_TBL.RANK > 50  
ORDER BY KEY_TBL.RANK DESC;  
GO  
```  
  

  
##  <a name="additional-considerations-for-proximity-searches"></a><a name="Additional_Considerations"></a><span data-ttu-id="bf1ff-150">Considerazioni aggiuntive per le ricerche per prossimità</span><span class="sxs-lookup"><span data-stu-id="bf1ff-150">Additional Considerations for Proximity Searches</span></span>  
 <span data-ttu-id="bf1ff-151">In questa sezione vengono illustrate alcune considerazioni riguardanti le ricerche per prossimità sia generiche che personalizzate:</span><span class="sxs-lookup"><span data-stu-id="bf1ff-151">This section discusses consideration that affect both generic and custom proximity searches:</span></span>  
  
-   <span data-ttu-id="bf1ff-152">Occorrenze di termini di ricerca sovrapposte</span><span class="sxs-lookup"><span data-stu-id="bf1ff-152">Overlapping occurrences of search terms</span></span>  
  
     <span data-ttu-id="bf1ff-153">In tutte le ricerche per prossimità viene sempre effettuata la ricerca solo di occorrenze non sovrapposte.</span><span class="sxs-lookup"><span data-stu-id="bf1ff-153">All proximity searches always look for only non-overlapping occurrences.</span></span> <span data-ttu-id="bf1ff-154">Le occorrenze di termini di ricerca sovrapposte non vengono mai considerate come corrispondenze.</span><span class="sxs-lookup"><span data-stu-id="bf1ff-154">Overlapping occurrences of search terms never qualify as matches.</span></span> <span data-ttu-id="bf1ff-155">Si consideri, ad esempio, il termine di prossimità seguente che effettua la ricerca di "`A`" e "`AA`" in questo ordine con una distanza massima di due termini:</span><span class="sxs-lookup"><span data-stu-id="bf1ff-155">For example, consider the following proximity term, which searches "`A`" and "`AA`" in this order with a maximum distance of two terms:</span></span>  
  
    ```  
    CONTAINS(column_name, 'NEAR((A,AA),2, TRUE')  
    ```  
  
     <span data-ttu-id="bf1ff-156">Le corrispondenze possibili sono "`AAA`", "`A.AA`" e "`A..AA`".</span><span class="sxs-lookup"><span data-stu-id="bf1ff-156">The possible matches are as "`AAA`", "`A.AA`", and "`A..AA`".</span></span> <span data-ttu-id="bf1ff-157">Le righe che contengono solo "`AA`" non restituirebbero alcuna corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="bf1ff-157">Rows containing just "`AA`" would not match.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bf1ff-158">È possibile specificare termini che si sovrappongono, ad esempio, `NEAR("mountain bike", "bike trails")` o `(NEAR(comfort*, comfortable), 5)`.</span><span class="sxs-lookup"><span data-stu-id="bf1ff-158">You can specify terms that overlap, for example, `NEAR("mountain bike", "bike trails")` or `(NEAR(comfort*, comfortable), 5)`.</span></span> <span data-ttu-id="bf1ff-159">In tal caso, tuttavia, aumenterebbe la complessità della query, aumentando di conseguenza le possibili permutazioni delle corrispondenze.</span><span class="sxs-lookup"><span data-stu-id="bf1ff-159">Specifying a overlapping terms increases the complexity of the query by increasing the possible match permutations.</span></span> <span data-ttu-id="bf1ff-160">Se si specifica un numero elevato di tali termini sovrapposti, è possibile che le risorse della query si esauriscano e che l'operazione abbia esito negativo.</span><span class="sxs-lookup"><span data-stu-id="bf1ff-160">If you specify a large number of such overlapping terms, the query can run out of resources and fail.</span></span> <span data-ttu-id="bf1ff-161">In tal caso, semplificare la query e riprovare.</span><span class="sxs-lookup"><span data-stu-id="bf1ff-161">If this occurs, simplify the query and try again.</span></span>  
  
-   <span data-ttu-id="bf1ff-162">Sia il termine generico NEAR che il termine personalizzato NEAR (indipendentemente dal fatto venga specificata o meno una distanza massima) indicano la distanza logica anziché la distanza assoluta tra i termini.</span><span class="sxs-lookup"><span data-stu-id="bf1ff-162">Both generic NEAR and custom NEAR (regardless of whether a maximum distance is specified) indicate the logical distance between terms, rather than the absolute distance between them.</span></span> <span data-ttu-id="bf1ff-163">Ad esempio, i termini all'interno di espressioni o frasi diverse di un paragrafo vengono trattati come più lontani dei termini nella stessa espressione o frase, indipendentemente dalla loro prossimità effettiva, presupponendo che siano meno correlati.</span><span class="sxs-lookup"><span data-stu-id="bf1ff-163">For example, terms within different phrases or sentences within a paragraph are treated as farther apart than terms in the same phrase or sentence, regardless of their actual proximity, on the assumption that they are less related.</span></span> <span data-ttu-id="bf1ff-164">In modo analogo, i termini presenti in paragrafi diversi vengono trattati come ancora più lontani.</span><span class="sxs-lookup"><span data-stu-id="bf1ff-164">Likewise, terms in different paragraphs are treated as being even farther apart.</span></span> <span data-ttu-id="bf1ff-165">Se una corrispondenza si estende fino alla fine di una frase, un paragrafo o un capitolo, il gap utilizzato per la classificazione per rango di un documento viene aumentato rispettivamente di 8, 128 o 1024.</span><span class="sxs-lookup"><span data-stu-id="bf1ff-165">If a match spans the end of a sentence, paragraph, or chapter, the gap used for ranking a document is increased by 8, 128, or 1024, respectively.</span></span>  
  
-   <span data-ttu-id="bf1ff-166">Impatto dei termini di prossimità sulla classificazione per rango tramite la funzione CONTAINSTABLE</span><span class="sxs-lookup"><span data-stu-id="bf1ff-166">Impact of proximity terms on ranking by the CONTAINSTABLE function</span></span>  
  
     <span data-ttu-id="bf1ff-167">Quando NEAR viene utilizzato nella funzione CONTAINSTABLE, il numero di riscontri presenti in un documento in rapporto alla relativa lunghezza, nonché alla distanza tra i primo e l'ultimo termine di ricerca in ognuno dei riscontri, influisce sulla classificazione per rango di ogni documento.</span><span class="sxs-lookup"><span data-stu-id="bf1ff-167">When NEAR is used in the CONTAINSTABLE function, the number of hits in a document relative to its length as well as the distance between the first and last search terms in each of the hits affects the ranking of each document.</span></span> <span data-ttu-id="bf1ff-168">Per un termine di prossimità generico, se i termini di ricerca corrispondenti sono separati da >50 termini logici, il rango restituito per un documento sarà pari a 0.</span><span class="sxs-lookup"><span data-stu-id="bf1ff-168">For a generic proximity term, if the matched search terms are >50 logical terms apart, the rank returned on a document is 0.</span></span> <span data-ttu-id="bf1ff-169">Per un termine di prossimità personalizzato in cui non è specificato un intero come distanza massima, il rango restituito per un documento che contiene solo riscontri il cui gap è >100 termini logici sarà pari a 0.</span><span class="sxs-lookup"><span data-stu-id="bf1ff-169">For a custom proximity term that does not specify an integer as the maximum distance, a document that contains only hits whose gap is >100 logical terms will receive a ranking of 0.</span></span> <span data-ttu-id="bf1ff-170">Per altre informazioni sulla classificazione per rango di ricerche per prossimità personalizzate, vedere [Limitare i risultati della ricerca con RANK](limit-search-results-with-rank.md).</span><span class="sxs-lookup"><span data-stu-id="bf1ff-170">For more information about ranking of custom proximity searches, see [Limit Search Results with RANK](limit-search-results-with-rank.md).</span></span>  
  
-   <span data-ttu-id="bf1ff-171">Opzione server **Transform Noise Words**</span><span class="sxs-lookup"><span data-stu-id="bf1ff-171">The **transform noise words** server option</span></span>  
  
     <span data-ttu-id="bf1ff-172">Il valore di **Transform Noise Words** influisce sul modo in cui [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] gestisce le parole non significative, se vengono specificate nelle ricerche per prossimità.</span><span class="sxs-lookup"><span data-stu-id="bf1ff-172">The value of **transform noise words** impacts how [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] treats stopwords if they are specified in proximity searches.</span></span> <span data-ttu-id="bf1ff-173">Per altre informazioni, vedere [transform noise words Server Configuration Option](../../database-engine/configure-windows/transform-noise-words-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="bf1ff-173">For more information, see [transform noise words Server Configuration Option](../../database-engine/configure-windows/transform-noise-words-server-configuration-option.md).</span></span>  
  

  
##  <a name="the-deprecated-generic-proximity-term"></a><a name="Generic_NEAR"></a><span data-ttu-id="bf1ff-174">Termine di prossimità generico deprecato</span><span class="sxs-lookup"><span data-stu-id="bf1ff-174">The Deprecated Generic Proximity Term</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)]<span data-ttu-id="bf1ff-175">Si consiglia di usare il [termine di prossimità personalizzato](#Custom_NEAR).</span><span class="sxs-lookup"><span data-stu-id="bf1ff-175">We recommend that you use the [custom proximity term](#Custom_NEAR).</span></span>  
  
 <span data-ttu-id="bf1ff-176">Un termine di prossimità generico indica che i termini di ricerca specificati devono essere tutti presenti in un documento perché venga restituita una corrispondenza, indipendentemente dal numero di termini non di ricerca, ovvero la *distanza*, tra i termini di ricerca.</span><span class="sxs-lookup"><span data-stu-id="bf1ff-176">A generic proximity term indicates that the specified search terms must all occur in a document for a match to be returned, regardless of the number of non-search terms (the *distance*) between the search terms.</span></span> <span data-ttu-id="bf1ff-177">La sintassi di base è la seguente:</span><span class="sxs-lookup"><span data-stu-id="bf1ff-177">The basic syntax is:</span></span>  
  
 <span data-ttu-id="bf1ff-178">{ *search_term* {near | ~} *search_term* } [ ,... *n* ]</span><span class="sxs-lookup"><span data-stu-id="bf1ff-178">{ *search_term* { NEAR | ~ } *search_term* } [ ,...*n* ]</span></span>  
  
 <span data-ttu-id="bf1ff-179">Negli esempi seguenti le parole 'fox' e 'chicken', ad esempio, devono essere entrambe presenti, indipendentemente dall'ordine, per produrre una corrispondenza:</span><span class="sxs-lookup"><span data-stu-id="bf1ff-179">For example, in the following examples, the words 'fox' and 'chicken' must both appear, in either order, to produce a match:</span></span>  
  
-   `CONTAINS(column_name, 'fox NEAR chicken')`  
  
-   `CONTAINSTABLE(table_name, column_name, 'fox ~ chicken')`  
  
> [!NOTE]  
>  <span data-ttu-id="bf1ff-180">Per informazioni sulla sintassi di <generic_proximity_term>, vedere [CONTAINS &#40;Transact-SQL&#41;](/sql/t-sql/queries/contains-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="bf1ff-180">For information about the <generic_proximity_term> syntax, see [CONTAINS &#40;Transact-SQL&#41;](/sql/t-sql/queries/contains-transact-sql).</span></span>  
  
 <span data-ttu-id="bf1ff-181">Per altre informazioni, vedere "[Considerazioni aggiuntive per le ricerche per prossimità](#Additional_Considerations)" più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="bf1ff-181">For more information, see "[Additional Considerations about Proximity Searches](#Additional_Considerations)," later in this topic.</span></span>  
  
### <a name="combining-a-generic-proximity-term-with-other-terms"></a><span data-ttu-id="bf1ff-182">Combinazione di un termine di prossimità generico con altri termini</span><span class="sxs-lookup"><span data-stu-id="bf1ff-182">Combining a Generic Proximity Term with Other Terms</span></span>  
 <span data-ttu-id="bf1ff-183">È possibile usare AND (&), OR (|) oppure AND NOT (&!) per combinare un termine di prossimità generico con un altro termine di prossimità generico, un termine semplice o un termine prefisso.</span><span class="sxs-lookup"><span data-stu-id="bf1ff-183">You can use AND (&), OR (|), or AND NOT (&!) to combine a generic proximity term with another generic proximity term, a simple term, or a prefix term.</span></span> <span data-ttu-id="bf1ff-184">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="bf1ff-184">For example:</span></span>  
  
```  
CONTAINSTABLE (Production.ProductDescription,  
   Description,   
   '(light NEAR aluminum) OR  
   (lightweight NEAR aluminum)'  
)  
```  
  
 <span data-ttu-id="bf1ff-185">Non è possibile combinare un termine di prossimità generico con un termine di prossimità personalizzato, ad esempio `NEAR((term1,term2),5)` , un termine ponderato (noabout...) o un termine generazionale (FORMSOF...).</span><span class="sxs-lookup"><span data-stu-id="bf1ff-185">You cannot combine a generic proximity term with a custom proximity term, such as `NEAR((term1,term2),5)`, a weighted term (ISABOUT ...), or a generational term (FORMSOF ...).</span></span>  
  
### <a name="example-using-the-generic-proximity-term"></a><span data-ttu-id="bf1ff-186">Esempio: Utilizzo del termine di prossimità generico</span><span class="sxs-lookup"><span data-stu-id="bf1ff-186">Example: Using the Generic Proximity Term</span></span>  
 <span data-ttu-id="bf1ff-187">Nell'esempio seguente viene utilizzato il termine di prossimità generico per cercare la parola "reflector" nello stesso documento che contiene la parola "bracket".</span><span class="sxs-lookup"><span data-stu-id="bf1ff-187">The following example uses the generic proximity term to search for the word "reflector" in the same document as the word "bracket".</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
  
SELECT DocumentNode, Title, DocumentSummary  
FROM Production.Document AS DocTable INNER JOIN  
  CONTAINSTABLE(Production.Document, Document,  
  '(reflector NEAR bracket)' ) AS KEY_TBL  
  ON DocTable.DocumentNode = KEY_TBL.[KEY]  
ORDER BY KEY_TBL.RANK DESC;  
GO  
```  
  
 <span data-ttu-id="bf1ff-188">Si noti che invertendo i termini in CONTAINSTABLE si ottiene lo stesso risultato:</span><span class="sxs-lookup"><span data-stu-id="bf1ff-188">Notice that you can also reverse the terms in CONTAINSTABLE to get the same result:</span></span>  
  
```  
CONTAINSTABLE(Production.Document, Document, '(bracket NEAR reflector)' ) AS KEY_TBL  
```  
  
 <span data-ttu-id="bf1ff-189">È possibile ottenere lo stesso risultato sostituendo la parola chiave NEAR con una tilde (~):</span><span class="sxs-lookup"><span data-stu-id="bf1ff-189">You can use the tilde character (~) in place of the NEAR keyword in the earlier query, and get the same results:</span></span>  
  
```  
CONTAINSTABLE(Production.Document, Document, '(reflector ~ bracket)' ) AS KEY_TBL  
```  
  
 <span data-ttu-id="bf1ff-190">Nelle condizioni di ricerca è possibile includere più di due parole o frasi,</span><span class="sxs-lookup"><span data-stu-id="bf1ff-190">More than two words or phrases can be specified in the search conditions.</span></span> <span data-ttu-id="bf1ff-191">ad esempio:</span><span class="sxs-lookup"><span data-stu-id="bf1ff-191">For example, it is possible to write:</span></span>  
  
```  
CONTAINSTABLE(Production.Document, Document, '(reflector ~ bracket ~ installation)' ) AS KEY_TBL  
```  
  
 <span data-ttu-id="bf1ff-192">Ciò significa che la parola "riflettore" deve trovarsi nello stesso documento della parola "supporto" e "supporto" deve trovarsi nello stesso documento della parola "installazione".</span><span class="sxs-lookup"><span data-stu-id="bf1ff-192">This means that "reflector" must be in the same document as "bracket", and "bracket" must be in the same document as "installation".</span></span>  
  

  
## <a name="see-also"></a><span data-ttu-id="bf1ff-193">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bf1ff-193">See Also</span></span>  
 <span data-ttu-id="bf1ff-194">[CONTAINSTABLE &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/containstable-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="bf1ff-194">[CONTAINSTABLE &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/containstable-transact-sql) </span></span>  
 <span data-ttu-id="bf1ff-195">[Eseguire query con ricerca full-text](query-with-full-text-search.md) </span><span class="sxs-lookup"><span data-stu-id="bf1ff-195">[Query with Full-Text Search](query-with-full-text-search.md) </span></span>  
 [<span data-ttu-id="bf1ff-196">CONTAINS &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="bf1ff-196">CONTAINS &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/queries/contains-transact-sql)  
  
  
