---
title: Usare la ricerca full-text con colonne XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- xml columns [full-text search]
- indexes [full-text search]
ms.assetid: 8096cfc6-1836-4ed5-a769-a5d63b137171
author: rothja
ms.author: jroth
ms.openlocfilehash: 2b6b23933fde6a09d043c7055b0daa7c07035cdb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713907"
---
# <a name="use-full-text-search-with-xml-columns"></a><span data-ttu-id="27aa2-102">Utilizzo della ricerca full-text con colonne XML</span><span class="sxs-lookup"><span data-stu-id="27aa2-102">Use Full-Text Search with XML Columns</span></span>
  <span data-ttu-id="27aa2-103">Sulle colonne XML è possibile creare un indice full-text che indicizza il contenuto dei valori XML, ma ignora i markup XML.</span><span class="sxs-lookup"><span data-stu-id="27aa2-103">You can create a full-text index on XML columns that indexes the content of the XML values, but ignores the XML markup.</span></span> <span data-ttu-id="27aa2-104">I tag degli elementi vengono utilizzati come limiti dei token.</span><span class="sxs-lookup"><span data-stu-id="27aa2-104">Element tags are used as token boundaries.</span></span> <span data-ttu-id="27aa2-105">Gli elementi riportati di seguito sono indicizzati:</span><span class="sxs-lookup"><span data-stu-id="27aa2-105">The following items are indexed:</span></span>  
  
-   <span data-ttu-id="27aa2-106">Contenuto degli elementi XML.</span><span class="sxs-lookup"><span data-stu-id="27aa2-106">The content of XML elements.</span></span>  
  
-   <span data-ttu-id="27aa2-107">Solo il contenuto degli attributi XML dell'elemento di livello principale, a meno che non si tratti di valori numerici.</span><span class="sxs-lookup"><span data-stu-id="27aa2-107">The content of XML attributes of the top-level element only, unless those values are numeric values.</span></span>  
  
 <span data-ttu-id="27aa2-108">In alcuni casi è possibile combinare la ricerca full-text con l'indicizzazione XML, procedendo nel modo descritto di seguito.</span><span class="sxs-lookup"><span data-stu-id="27aa2-108">When possible, you can combine full-text search with XML index in the following way:</span></span>  
  
1.  <span data-ttu-id="27aa2-109">Filtrare innanzitutto i valori XML desiderati utilizzando la ricerca full-text SQL.</span><span class="sxs-lookup"><span data-stu-id="27aa2-109">First, filter the XML values of interest by using SQL full-text search.</span></span>  
  
2.  <span data-ttu-id="27aa2-110">Eseguire quindi una query sui valori XML che utilizzano l'indice XML sulla colonna XML.</span><span class="sxs-lookup"><span data-stu-id="27aa2-110">Next, query those XML values that use XML index on the XML column.</span></span>  
  
## <a name="example-combining-full-text-search-with-xml-querying"></a><span data-ttu-id="27aa2-111">Esempio: Combinazione di ricerca full-text e query XML</span><span class="sxs-lookup"><span data-stu-id="27aa2-111">Example: Combining Full-text Search with XML Querying</span></span>  
 <span data-ttu-id="27aa2-112">Dopo la creazione dell'indice full-text sulla colonna XML è possibile utilizzare la query seguente per verificare se un valore XML contiene la parola "custom" nel titolo di un libro:</span><span class="sxs-lookup"><span data-stu-id="27aa2-112">After the full-text index has been created on the XML column, the following query checks that an XML value contains the word "custom" in the title of a book:</span></span>  
  
```  
SELECT *   
FROM   T   
WHERE  CONTAINS(xCol,'custom')   
AND    xCol.exist('/book/title/text()[contains(.,"custom")]') =1  
```  
  
 <span data-ttu-id="27aa2-113">Il metodo **contains()** usa l'indice full-text per creare un subset dei valori XML contenenti la parola "custom", in qualunque punto del documento.</span><span class="sxs-lookup"><span data-stu-id="27aa2-113">The **contains()** method uses the full-text index to subset the XML values that contain the word "custom" anywhere in the document.</span></span> <span data-ttu-id="27aa2-114">La clausola **exist()** garantisce che la parola "custom" compaia nel titolo di un libro.</span><span class="sxs-lookup"><span data-stu-id="27aa2-114">The **exist()** clause ensures that the word "custom" occurs in the title of a book.</span></span>  
  
 <span data-ttu-id="27aa2-115">Una ricerca full-text che usa **contains()** a la query XQuery **contains()** hanno semantiche diverse.</span><span class="sxs-lookup"><span data-stu-id="27aa2-115">A full-text search that uses **contains()** and XQuery **contains()** has different semantics.</span></span> <span data-ttu-id="27aa2-116">Nel secondo caso si tratta di una corrispondenza tra sottostringhe, mentre nel primo si tratta di una corrispondenza tra token basata sullo stemming.</span><span class="sxs-lookup"><span data-stu-id="27aa2-116">The latter is a substring match and the former is a token match that uses stemming.</span></span> <span data-ttu-id="27aa2-117">Quindi, se si esegua la ricerca della stringa che include la parola "run" nel titolo, le corrispondenze includeranno le parole "run", "runs" e "running", perché sono soddisfatti sia i criteri della ricerca full-text **contains()** che quelli della query XQuery **contains()** .</span><span class="sxs-lookup"><span data-stu-id="27aa2-117">Therefore, if the search is for the string that has "run" in the title, the matches will include "run", "runs", and "running", because both the full-text **contains()** and the Xquery **contains()** are satisfied.</span></span> <span data-ttu-id="27aa2-118">La query, tuttavia, non individua la parola "customizable" nel titolo, perché la ricerca full-text **contains()** non riesce, ma la query XQuery **contains()** è soddisfatta.</span><span class="sxs-lookup"><span data-stu-id="27aa2-118">However, the query does not match the word "customizable" in the title in that the full-text **contains()** fails, but the Xquery **contains()** is satisfied.</span></span> <span data-ttu-id="27aa2-119">In genere, per le semplici corrispondenze di sottostringhe è consigliabile rimuovere la clausola **contains()** della ricerca full-text.</span><span class="sxs-lookup"><span data-stu-id="27aa2-119">Generally, for pure substring match, the full-text **contains()** clause should be removed.</span></span>  
  
 <span data-ttu-id="27aa2-120">Inoltre, la ricerca full-text usa lo stemming delle parole, mentre la query XQuery **contains()** richiede una corrispondenza letterale.</span><span class="sxs-lookup"><span data-stu-id="27aa2-120">Additionally, full-text search uses word stemming, but XQuery **contains()** is a literal match.</span></span> <span data-ttu-id="27aa2-121">Tale differenza è illustrata nell'esempio successivo.</span><span class="sxs-lookup"><span data-stu-id="27aa2-121">This difference is illustrated in the next example.</span></span>  
  
## <a name="example-full-text-search-on-xml-values-using-stemming"></a><span data-ttu-id="27aa2-122">Esempio: Ricerca full-text su valori XML tramite stemming</span><span class="sxs-lookup"><span data-stu-id="27aa2-122">Example: Full-text Search on XML Values Using Stemming</span></span>  
 <span data-ttu-id="27aa2-123">Il controllo eseguito dalla query XQuery **contains()** nell'esempio precedente non può essere in genere eliminato.</span><span class="sxs-lookup"><span data-stu-id="27aa2-123">The XQuery **contains()** check that was performed in the previous example generally cannot be eliminated.</span></span> <span data-ttu-id="27aa2-124">Considerare la query seguente:</span><span class="sxs-lookup"><span data-stu-id="27aa2-124">Consider this query:</span></span>  
  
```  
SELECT *   
FROM   T   
WHERE  CONTAINS(xCol,'run')   
```  
  
 <span data-ttu-id="27aa2-125">La parola "ran" nel documento soddisfa la condizione di ricerca a causa dello stemming.</span><span class="sxs-lookup"><span data-stu-id="27aa2-125">The word "ran" in the document matches the search condition because of stemming.</span></span> <span data-ttu-id="27aa2-126">Se si utilizza una query XQuery, inoltre, il contesto della ricerca non viene verificato.</span><span class="sxs-lookup"><span data-stu-id="27aa2-126">Additionally, the search context is not checked by using XQuery.</span></span>  
  
 <span data-ttu-id="27aa2-127">Quando i valori XML vengono scomposti tramite AXSD in colonne relazionali con indicizzazione full-text, le query XPath sulla visualizzazione XML non eseguono una ricerca full-text sulle tabelle sottostanti.</span><span class="sxs-lookup"><span data-stu-id="27aa2-127">When XML is decomposed into relational columns by using AXSD that are full-text indexed, XPath queries that occur over the XML view do not perform full-text search on the underlying tables.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27aa2-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="27aa2-128">See Also</span></span>  
 [<span data-ttu-id="27aa2-129">Indici XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="27aa2-129">XML Indexes &#40;SQL Server&#41;</span></span>](xml-indexes-sql-server.md)  
  
  
