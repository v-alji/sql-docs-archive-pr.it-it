---
title: Includere o escludere righe (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- search criteria [SQL Server], excluding rows
- search criteria [SQL Server], WHERE clause
- included rows
- search conditions [SQL Server], HAVING clause
- search criteria [SQL Server], including rows
- row excluded in search [SQL Server]
- search criteria [SQL Server], HAVING clause
- search conditions [SQL Server], WHERE clause
- row included in search [SQL Server]
- excluding rows
ms.assetid: ba4e1202-31a2-444d-8365-c68a530ef223
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7b2d31c51296fa73a503e59a14adb60d79a61178
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629671"
---
# <a name="include-or-exclude-rows-visual-database-tools"></a><span data-ttu-id="88a90-102">Includere o escludere righe (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="88a90-102">Include or Exclude Rows (Visual Database Tools)</span></span>
  <span data-ttu-id="88a90-103">Per limitare il numero di righe restituite da una query di selezione, è necessario creare condizioni di ricerca o criteri di filtro.</span><span class="sxs-lookup"><span data-stu-id="88a90-103">To restrict the number of rows a SELECT query should return, you create search conditions or filter criteria.</span></span> <span data-ttu-id="88a90-104">In SQL le condizioni di ricerca vengono indicate nella clausola WHERE dell'istruzione o, se si sta creando una query di aggregazione, nella clausola HAVING.</span><span class="sxs-lookup"><span data-stu-id="88a90-104">In SQL, search conditions appear in the WHERE clause of the statement, or if you are creating an aggregate query, in the HAVING clause.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="88a90-105">È inoltre possibile utilizzare condizioni di ricerca per indicare le righe su cui ha effetto una query di aggiornamento, di accodamento, di accodamento valori, di eliminazione o di creazione tabella.</span><span class="sxs-lookup"><span data-stu-id="88a90-105">You can also use search conditions to indicate which rows are affected by an Update, Insert Results, Insert Values, Delete, or Make Table query.</span></span>  
  
 <span data-ttu-id="88a90-106">Al momento dell'esecuzione della query, il [!INCLUDE[ssDE](../../includes/ssde-md.md)] esamina e applica la condizione di ricerca a ciascuna riga delle tabelle in cui si esegue la ricerca.</span><span class="sxs-lookup"><span data-stu-id="88a90-106">When the query runs, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] examines and applies the search condition to each row in the tables you are searching.</span></span> <span data-ttu-id="88a90-107">Se la riga soddisfa la condizione, verrà inclusa nella query.</span><span class="sxs-lookup"><span data-stu-id="88a90-107">If the row meets the condition, it is included in the query.</span></span> <span data-ttu-id="88a90-108">Ad esempio, una condizione per la ricerca di tutti i dipendenti di una determinata regione potrebbe essere:</span><span class="sxs-lookup"><span data-stu-id="88a90-108">For example, a search condition that would find all the employees in a particular region might be:</span></span>  
  
```  
region = 'UK'  
```  
  
 <span data-ttu-id="88a90-109">Per definire i criteri per l'inserimento di una riga in un risultato, è possibile utilizzare più condizioni di ricerca.</span><span class="sxs-lookup"><span data-stu-id="88a90-109">To establish the criteria for including a row in a result, you can use multiple search conditions.</span></span> <span data-ttu-id="88a90-110">Ad esempio, la seguente condizione di ricerca è costituita da due condizioni di ricerca.</span><span class="sxs-lookup"><span data-stu-id="88a90-110">For example, the following search criterion consists of two search conditions.</span></span> <span data-ttu-id="88a90-111">La query include una riga nel set di risultati soltanto se tale riga soddisfa entrambe le condizioni.</span><span class="sxs-lookup"><span data-stu-id="88a90-111">The query includes a row in the result set only if that row satisfies both of the conditions.</span></span>  
  
```  
region = 'UK' AND product_line = 'Housewares'  
```  
  
 <span data-ttu-id="88a90-112">È possibile combinare queste condizioni con l'operatore AND o OR.</span><span class="sxs-lookup"><span data-stu-id="88a90-112">You can combine these conditions with AND or OR.</span></span> <span data-ttu-id="88a90-113">Nell'esempio precedente è stato utilizzato AND,</span><span class="sxs-lookup"><span data-stu-id="88a90-113">The previous example uses AND.</span></span> <span data-ttu-id="88a90-114">mentre nel criterio riportato di seguito viene utilizzato OR.</span><span class="sxs-lookup"><span data-stu-id="88a90-114">In contrast, the following criterion uses OR.</span></span> <span data-ttu-id="88a90-115">In questo secondo caso il set di risultati includerà tutte le righe che soddisfano una o entrambe le condizioni di ricerca:</span><span class="sxs-lookup"><span data-stu-id="88a90-115">The result set will include any row that satisfies either or both of the search conditions:</span></span>  
  
```  
region = 'UK' OR product_line = 'Housewares'  
```  
  
 <span data-ttu-id="88a90-116">È inoltre possibile combinare condizioni di ricerca per una singola colonna.</span><span class="sxs-lookup"><span data-stu-id="88a90-116">You can even combine search conditions on a single column.</span></span> <span data-ttu-id="88a90-117">Ad esempio, il seguente criterio combina due condizioni per la colonna region:</span><span class="sxs-lookup"><span data-stu-id="88a90-117">For example, the following criterion combines two conditions on the region column:</span></span>  
  
```  
region = 'UK' OR region = 'US'  
```  
  
 <span data-ttu-id="88a90-118">Per informazioni dettagliate sulla combinazione di condizioni di ricerca, vedere i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="88a90-118">For details about combining search conditions, see the following topics:</span></span>  
  
-   [<span data-ttu-id="88a90-119">Convenzioni per la combinazione delle condizioni di ricerca nel riquadro Criteri &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="88a90-119">Conventions for Combining Search Conditions in the Criteria Pane &#40;Visual Database Tools&#41;</span></span>](conventions-combine-search-conditions-in-criteria-pane-visual-db-tools.md)  
  
-   [<span data-ttu-id="88a90-120">Definizione di più condizioni di ricerca per una sola colonna &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="88a90-120">Specify Multiple Search Conditions for One Column &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
  
-   [<span data-ttu-id="88a90-121">Definizione di più condizioni di ricerca per più colonne &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="88a90-121">Specify Multiple Search Conditions for Multiple Columns &#40;Visual Database Tools&#41;</span></span>](specify-multiple-search-conditions-for-multiple-columns-visual-database-tools.md)  
  
-   [<span data-ttu-id="88a90-122">Combinazione di condizioni quando AND ha la precedenza &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="88a90-122">Combine Conditions When AND Has Precedence &#40;Visual Database Tools&#41;</span></span>](combine-conditions-when-and-has-precedence-visual-database-tools.md)  
  
-   [<span data-ttu-id="88a90-123">Combinazione di condizioni quando OR ha la precedenza &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="88a90-123">Combine Conditions When OR Has Precedence &#40;Visual Database Tools&#41;</span></span>](combine-conditions-when-or-has-precedence-visual-database-tools.md)  
  
## <a name="examples"></a><span data-ttu-id="88a90-124">Esempi</span><span class="sxs-lookup"><span data-stu-id="88a90-124">Examples</span></span>  
 <span data-ttu-id="88a90-125">Di seguito vengono forniti alcuni esempi di query che utilizzano vari operatori e criteri per le righe:</span><span class="sxs-lookup"><span data-stu-id="88a90-125">Here are some examples of queries using various operators and row criteria:</span></span>  
  
-   <span data-ttu-id="88a90-126">**Valore letterale** Un singolo valore di testo, numerico, di data o logico.</span><span class="sxs-lookup"><span data-stu-id="88a90-126">**Literal** A single text, numeric, date, or logical value.</span></span> <span data-ttu-id="88a90-127">In questo esempio viene utilizzato un valore letterale per trovare tutte le righe relative ai dipendenti che vivono nel Regno Unito:</span><span class="sxs-lookup"><span data-stu-id="88a90-127">The following example uses a literal to find all rows for employees in the United Kingdom:</span></span>  
  
    ```  
    WHERE region = 'UK'  
    ```  
  
-   <span data-ttu-id="88a90-128">**Riferimento a una colonna** Confronta i valori di due colonne.</span><span class="sxs-lookup"><span data-stu-id="88a90-128">**Column reference** Compares the values in one column with the values in another.</span></span> <span data-ttu-id="88a90-129">In questo esempio vengono cercate all'interno di una tabella `products` tutte le righe nelle quali il valore del costo di produzione è inferiore al costo di spedizione:</span><span class="sxs-lookup"><span data-stu-id="88a90-129">The following example searches a `products` table for all rows in which the value of the production cost is lower than the shipping cost:</span></span>  
  
    ```  
    WHERE prod_cost < ship_cost  
    ```  
  
-   <span data-ttu-id="88a90-130">**Funzione** Riferimento a una funzione che può essere risolto dal back-end del database per calcolare un valore per la ricerca.</span><span class="sxs-lookup"><span data-stu-id="88a90-130">**Function** A reference to a function that the database back-end can resolve to calculate a value for the search.</span></span> <span data-ttu-id="88a90-131">La funzione può essere una funzione definita dal server di database o una funzione definita dall'utente che restituisce un valore scalare.</span><span class="sxs-lookup"><span data-stu-id="88a90-131">The function can be a function defined by the database server or a user-defined function that returns a scalar value.</span></span> <span data-ttu-id="88a90-132">In questo esempio vengono cercati gli ordini inviati nel giorno corrente (la funzione GETDATE( ) restituisce la data corrente):</span><span class="sxs-lookup"><span data-stu-id="88a90-132">The following example searches for orders placed today (the GETDATE( ) function returns the current date):</span></span>  
  
    ```  
    WHERE order_date = GETDATE()  
    ```  
  
-   <span data-ttu-id="88a90-133">**NULL** In questo esempio vengono cercati all'interno di una tabella `authors` tutti gli autori per cui è stato registrato il nome:</span><span class="sxs-lookup"><span data-stu-id="88a90-133">**NULL** The following example searches an `authors` table for all authors who have a first name on file:</span></span>  
  
    ```  
    WHERE au_fname IS NOT NULL  
    ```  
  
-   <span data-ttu-id="88a90-134">**Calcolo** Il risultato di un calcolo può includere valori letterali, riferimenti a colonne o altre espressioni.</span><span class="sxs-lookup"><span data-stu-id="88a90-134">**Calculation** The result of a calculation that can involve literals, column references, or other expressions.</span></span> <span data-ttu-id="88a90-135">In questo esempio viene eseguita una ricerca all'interno di una tabella `products` per trovare tutte le righe in cui il prezzo di vendita al dettaglio è più del doppio del costo di produzione:</span><span class="sxs-lookup"><span data-stu-id="88a90-135">The following example searches a `products` table to find all rows in which the retail sales price is more than twice the production cost:</span></span>  
  
    ```  
    WHERE sales_price > (prod_cost * 2)  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="88a90-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="88a90-136">See Also</span></span>  
 <span data-ttu-id="88a90-137">[Procedure per la progettazione di query e viste &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="88a90-137">[Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span></span>  
 <span data-ttu-id="88a90-138">[Specificare i criteri di ricerca &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="88a90-138">[Specify Search Criteria &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="88a90-139">Esecuzione di query con parametri &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="88a90-139">Query with Parameters &#40;Visual Database Tools&#41;</span></span>](query-with-parameters-visual-database-tools.md)  
  
  
