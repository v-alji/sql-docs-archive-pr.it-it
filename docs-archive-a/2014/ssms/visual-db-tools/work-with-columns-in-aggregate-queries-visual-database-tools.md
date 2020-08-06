---
title: Usare colonne in query di aggregazione (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- HAVING clause, query summary results
- GROUP BY clause, query summary results
- aggregate queries [SQL Server]
- WHERE clause, query summary results
ms.assetid: 1b82681f-3d4f-4b9a-bb1d-2060e44f2577
author: stevestein
ms.author: sstein
ms.openlocfilehash: 880f7529cebd7f51951e62952e3b5f13190f99b1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711395"
---
# <a name="work-with-columns-in-aggregate-queries-visual-database-tools"></a><span data-ttu-id="9323b-102">Utilizzo di colonne in query di aggregazione (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="9323b-102">Work with Columns in Aggregate Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="9323b-103">Quando si creano query di aggregazione con [Progettazione query e Progettazione viste](visual-database-tools.md) , le operazioni vengono eseguite sulla base di alcuni presupposti che garantiscono la generazione di una query valida.</span><span class="sxs-lookup"><span data-stu-id="9323b-103">When you create aggregate queries the [Query and View Designer](visual-database-tools.md) makes certain assumptions so that it can construct a valid query.</span></span> <span data-ttu-id="9323b-104">Se, ad esempio, si crea una query di aggregazione e si contrassegna una colonna di dati per l'output, in Progettazione query e Progettazione viste la colonna viene automaticamente inserita nella clausola GROUP BY, in modo che non sia possibile visualizzare inavvertitamente il contenuto di una singola riga in un riepilogo.</span><span class="sxs-lookup"><span data-stu-id="9323b-104">For example, if you are creating an aggregate query and mark a data column for output, the Query and View Designer automatically makes the column part of the GROUP BY clause so that you do not inadvertently attempt to display the contents of an individual row in a summary.</span></span>  
  
## <a name="using-group-by"></a><span data-ttu-id="9323b-105">Utilizzo dell'opzione Group By</span><span class="sxs-lookup"><span data-stu-id="9323b-105">Using Group By</span></span>  
 <span data-ttu-id="9323b-106">In Progettazione query e Progettazione viste vengono utilizzate le seguenti regole per le operazioni con le colonne:</span><span class="sxs-lookup"><span data-stu-id="9323b-106">The Query and View Designer uses the following guidelines for working with columns:</span></span>  
  
-   <span data-ttu-id="9323b-107">Quando si sceglie l'opzione Group By o si aggiunge una funzione di aggregazione a una query, tutte le colonne contrassegnate per l'output o utilizzate per l'ordinamento vengono aggiunte automaticamente alla clausola GROUP BY.</span><span class="sxs-lookup"><span data-stu-id="9323b-107">When you choose the Group By option or add an aggregate function to a query, all columns marked for output or used for sorting are automatically added to the GROUP BY clause.</span></span> <span data-ttu-id="9323b-108">Le colonne non vengono aggiunte automaticamente alla clausola GROUP BY se fanno già parte di una funzione di aggregazione.</span><span class="sxs-lookup"><span data-stu-id="9323b-108">Columns are not automatically added to the GROUP BY clause if they are already part of an aggregate function.</span></span>  
  
     <span data-ttu-id="9323b-109">Se non si desidera inserire una determinata colonna nella clausola GROUP BY, è necessario modificarla manualmente selezionando una diversa opzione nella colonna Group By del riquadro Criteri.</span><span class="sxs-lookup"><span data-stu-id="9323b-109">If you do not want a particular column to be part of the GROUP BY clause, you must manually change it by selecting a different option in the Group By column of the Criteria pane.</span></span> <span data-ttu-id="9323b-110">È possibile, tuttavia, scegliere un'opzione che può dare come risultato una query non eseguibile.</span><span class="sxs-lookup"><span data-stu-id="9323b-110">However, the Query and View Designer will not prevent you from choosing an option that can result in a query that will not run.</span></span>  
  
-   <span data-ttu-id="9323b-111">Se si aggiunge manualmente una colonna di output della query a una funzione di aggregazione nel riquadro Criteri o SQL, in Progettazione query e Progettazione viste le altre colonne di output non verranno rimosse automaticamente dalla query.</span><span class="sxs-lookup"><span data-stu-id="9323b-111">If you manually add a query output column to an aggregate function in either the Criteria or SQL pane, the Query and View Designer does not automatically remove other output columns from the query.</span></span> <span data-ttu-id="9323b-112">Sarà quindi necessario rimuovere le restanti colonne dall'output della query o inserirle in una clausola GROUP BY o in una funzione di aggregazione manualmente.</span><span class="sxs-lookup"><span data-stu-id="9323b-112">Therefore, you must remove the remaining columns from the query output or make them part of the GROUP BY clause or of an aggregate function.</span></span>  
  
 <span data-ttu-id="9323b-113">Quando si immette una condizione di ricerca nella colonna Filtro del riquadro Criteri, in Progettazione query e Progettazione viste vengono rispettate le seguenti regole:</span><span class="sxs-lookup"><span data-stu-id="9323b-113">When you enter a search condition into the Filter column of the Criteria pane, the Query and View Designer follows these rules:</span></span>  
  
-   <span data-ttu-id="9323b-114">Se la colonna **Group By** della griglia non è visualizzata perché non è stata ancora specificata una query di aggregazione, la condizione di ricerca verrà inserita nella clausola WHERE.</span><span class="sxs-lookup"><span data-stu-id="9323b-114">If the **Group By** column of the grid is not displayed (because you have not yet specified an aggregate query), the search condition is placed into the WHERE clause.</span></span>  
  
-   <span data-ttu-id="9323b-115">Se ci si trova già in una query di aggregazione ed è stata selezionata l'opzione **Where** nella colonna **Group By** , la condizione di ricerca verrà inserita nella clausola WHERE.</span><span class="sxs-lookup"><span data-stu-id="9323b-115">If you are already in an aggregate query and have selected the option **Where** in the **Group By** column, the search condition is placed into the WHERE clause.</span></span>  
  
-   <span data-ttu-id="9323b-116">Se la colonna **Group By** contiene un valore diverso da **Where**, la condizione di ricerca verrà inserita nella clausola HAVING.</span><span class="sxs-lookup"><span data-stu-id="9323b-116">If the **Group By** column contains any value other than **Where**, the search condition is placed in the HAVING clause.</span></span>  
  
## <a name="using-the-having-and-where-clauses"></a><span data-ttu-id="9323b-117">Utilizzo delle clausole HAVING e WHERE</span><span class="sxs-lookup"><span data-stu-id="9323b-117">Using the HAVING and WHERE Clauses</span></span>  
 <span data-ttu-id="9323b-118">I seguenti principi descrivono come fare riferimento a colonne nelle condizioni di ricerca per una query di aggregazione.</span><span class="sxs-lookup"><span data-stu-id="9323b-118">The following principles describe how you can reference columns in an aggregate query in search conditions.</span></span> <span data-ttu-id="9323b-119">In generale, è possibile utilizzare una colonna in una condizione di ricerca per filtrare le righe da riepilogare (una clausola WHERE) o per determinare quali risultati raggruppati saranno presenti nell'output finale (una clausola HAVING).</span><span class="sxs-lookup"><span data-stu-id="9323b-119">In general, you can use a column in a search condition to filter the rows that should be summarized (a WHERE clause) or to determine which grouped results appear in the final output (a HAVING clause).</span></span>  
  
-   <span data-ttu-id="9323b-120">Le singole colonne di dati possono essere inserite nella clausola WHERE o HAVING, in base a come vengono utilizzate in altri punti della query.</span><span class="sxs-lookup"><span data-stu-id="9323b-120">Individual data columns can appear in either the WHERE or HAVING clause, depending on how they are used elsewhere in the query.</span></span>  
  
-   <span data-ttu-id="9323b-121">Le clausole WHERE vengono utilizzate per selezionare un subset di righe per i riepiloghi e i raggruppamenti e vengono pertanto applicate prima dell'esecuzione del raggruppamento.</span><span class="sxs-lookup"><span data-stu-id="9323b-121">WHERE clauses are used to select a subset of rows for summarizing and grouping and are thus applied before any grouping is done.</span></span> <span data-ttu-id="9323b-122">È quindi possibile utilizzare una colonna di dati in una clausola WHERE anche se non fa parte della clausola GROUP BY o non è contenuta in una funzione di aggregazione.</span><span class="sxs-lookup"><span data-stu-id="9323b-122">Therefore, you can use a data column in a WHERE clause even if it is not part of the GROUP BY clause or contained in an aggregate function.</span></span> <span data-ttu-id="9323b-123">La seguente istruzione seleziona, ad esempio, tutti i libri che costano più di 10 dollari e calcola il prezzo medio:</span><span class="sxs-lookup"><span data-stu-id="9323b-123">For example, the following statement selects all titles that cost more than $10.00 and averages the price:</span></span>  
  
    ```  
    SELECT AVG(price)  
    FROM titles  
    WHERE price > 10  
    ```  
  
-   <span data-ttu-id="9323b-124">Se si crea una condizione di ricerca che coinvolge una colonna usata anche in una clausola GROUP BY o in una funzione di aggregazione, la condizione di ricerca potrà essere indicata come una clausola WHERE o HAVING. La clausola da usare può essere scelta quando si definisce la condizione.</span><span class="sxs-lookup"><span data-stu-id="9323b-124">If you create a search condition that involves a column also used in a GROUP BY clause or aggregate function, the search condition can appear as either a WHERE clause or a HAVING clause - you can decide which when you create the condition.</span></span> <span data-ttu-id="9323b-125">La seguente istruzione consente di calcolare, ad esempio, il prezzo medio dei libri di ogni editore, quindi visualizza la media calcolata per gli editori il cui prezzo medio è maggiore di 10 dollari.</span><span class="sxs-lookup"><span data-stu-id="9323b-125">For example, the following statement creates an average price for the titles for each publisher, then displays the average for the publishers in which the average price is greater than $10.00:</span></span>  
  
    ```  
    SELECT pub_id, AVG(price)  
    FROM titles  
    GROUP BY pub_id  
    HAVING (AVG(price) > 10)  
    ```  
  
-   <span data-ttu-id="9323b-126">Se si utilizza una funzione di aggregazione in una condizione di ricerca, la condizione richiederà un riepilogo e dovrà pertanto essere inserita nella clausola HAVING.</span><span class="sxs-lookup"><span data-stu-id="9323b-126">If you use an aggregate function in a search condition, the condition involves a summary and must therefore be part of the HAVING clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9323b-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9323b-127">See Also</span></span>  
 <span data-ttu-id="9323b-128">[Riepilogare i risultati delle query &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="9323b-128">[Summarize Query Results &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="9323b-129">Ordinare e raggruppare i risultati delle query &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="9323b-129">Sort and Group Query Results &#40;Visual Database Tools&#41;</span></span>](sort-and-group-query-results-visual-database-tools.md)  
  
  
