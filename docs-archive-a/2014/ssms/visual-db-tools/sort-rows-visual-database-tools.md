---
title: Ordinare righe (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- sorting rows [SQL Server]
- sorting query results [SQL Server]
ms.assetid: 780ef467-f96e-4373-8235-6dacbedb05a2
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4939c08a4be8c6a7aa3a52d55928abe077f25d76
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722140"
---
# <a name="sort-rows-visual-database-tools"></a><span data-ttu-id="476c0-102">Ordinamento di righe (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="476c0-102">Sort Rows (Visual Database Tools)</span></span>
  <span data-ttu-id="476c0-103">È possibile ordinare le righe nel risultato di una query.</span><span class="sxs-lookup"><span data-stu-id="476c0-103">You can order the rows in a query result.</span></span> <span data-ttu-id="476c0-104">In altre parole, è possibile identificare una colonna o un set di colonne particolare i cui valori determinano l'ordine delle righe nel set di risultati.</span><span class="sxs-lookup"><span data-stu-id="476c0-104">That is, you can name a particular column or set of columns whose values determine the order of rows in the result set.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="476c0-105">Il criterio di ordinamento è determinato in parte dalla sequenza di confronto della colonna.</span><span class="sxs-lookup"><span data-stu-id="476c0-105">The sort order is determined in part by the column's collation sequence.</span></span> <span data-ttu-id="476c0-106">Per cambiare la sequenza di confronto, è possibile usare la [finestra di dialogo Regole di confronto](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="476c0-106">You can change the collation sequence in the [Collation Dialog Box](visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="476c0-107">I risultati delle query possono essere ordinati in diversi modi:</span><span class="sxs-lookup"><span data-stu-id="476c0-107">There are several ways in which you can sort query results:</span></span>  
  
-   <span data-ttu-id="476c0-108">**È possibile disporre le righe in ordine crescente o decrescente** Per impostazione predefinita, in SQL vengono usate le colonne ORDER BY per disporre le righe in ordine crescente.</span><span class="sxs-lookup"><span data-stu-id="476c0-108">**You can arrange rows in ascending or descending order** By default, SQL uses order-by columns to arrange rows in ascending order.</span></span> <span data-ttu-id="476c0-109">Per disporre, ad esempio, i titoli dei libri in ordine crescente in base al prezzo, è sufficiente ordinare le righe in base alla colonna price.</span><span class="sxs-lookup"><span data-stu-id="476c0-109">For example, to arrange the book titles by ascending price, simply sort the rows by the price column.</span></span> <span data-ttu-id="476c0-110">Il codice SQL risultante potrebbe essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="476c0-110">The resulting SQL might look like this:</span></span>  
  
    ```  
    SELECT *  
    FROM titles  
    ORDER BY price  
  
    ```  
  
     <span data-ttu-id="476c0-111">Se invece si desidera disporre i titoli indicando per primi i libri più costosi, è possibile specificare in modo esplicito un ordinamento di questo tipo,</span><span class="sxs-lookup"><span data-stu-id="476c0-111">On the other hand, if you want to arrange the titles with the more expensive books first, you can explicitly specify a highest-first ordering.</span></span> <span data-ttu-id="476c0-112">ovvero indicare che le righe dei risultati devono essere disposte in ordine decrescente in base ai valori della colonna price.</span><span class="sxs-lookup"><span data-stu-id="476c0-112">That is, you indicate that the result rows should be arranged by descending values of the price column.</span></span> <span data-ttu-id="476c0-113">Il codice SQL risultante potrebbe essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="476c0-113">The resulting SQL might look like this:</span></span>  
  
    ```  
    SELECT *  
    FROM titles  
    ORDER BY price DESC  
  
    ```  
  
-   <span data-ttu-id="476c0-114">**È possibile eseguire l'ordinamento in base a più colonne** È possibile, ad esempio, creare un set di risultati con una riga per ogni autore, eseguendo l'ordinamento prima in base alla nazione e poi in base alla città.</span><span class="sxs-lookup"><span data-stu-id="476c0-114">**You can sort by multiple columns** For example, you can create a result set with one row for each author, ordering first by state and then by city.</span></span> <span data-ttu-id="476c0-115">Il codice SQL risultante potrebbe essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="476c0-115">The resulting SQL might look like this:</span></span>  
  
    ```  
    SELECT *  
    FROM authors   
    ORDER BY state, city  
  
    ```  
  
-   <span data-ttu-id="476c0-116">**È possibile eseguire l'ordinamento in base a colonne non presenti nel set di risultati** È possibile, ad esempio, creare un set di risultati con i libri più costosi indicati per primi anche se i prezzi non sono specificati.</span><span class="sxs-lookup"><span data-stu-id="476c0-116">**You can sort by columns not appearing in the result set** For example, you can create a result set with the most expensive titles first, even though the prices do not appear.</span></span> <span data-ttu-id="476c0-117">Il codice SQL risultante potrebbe essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="476c0-117">The resulting SQL might look like this:</span></span>  
  
    ```  
    SELECT title_id, title  
    FROM titles  
    ORDER BY price DESC  
  
    ```  
  
-   <span data-ttu-id="476c0-118">**È possibile eseguire l'ordinamento in base a colonne derivate**. Ad esempio, si può creare un set di risultati in cui ogni riga contiene il titolo di un libro, riportando per primi i libri con i diritti d'autore più elevati per singola copia.</span><span class="sxs-lookup"><span data-stu-id="476c0-118">**You can sort by derived columns** For example, you can create a result set in which each row contains a book title - with the books that pay the highest royalty per copy appearing first.</span></span> <span data-ttu-id="476c0-119">Il codice SQL risultante potrebbe essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="476c0-119">The resulting SQL might look like this:</span></span>  
  
    ```  
    SELECT title, price * royalty / 100 as royalty_per_unit  
    FROM titles  
    ORDER BY royalty_per_unit DESC  
  
    ```  
  
     <span data-ttu-id="476c0-120">In questo esempio è evidenziata la formula che consente di calcolare i diritti di autore corrisposti per ciascuna copia di un libro.</span><span class="sxs-lookup"><span data-stu-id="476c0-120">(The formula for calculating the royalty that each book earns per copy is emphasized.)</span></span>  
  
     <span data-ttu-id="476c0-121">Per calcolare una colonna derivata, è possibile utilizzare la sintassi SQL, come è stato fatto nell'esempio precedente, oppure è possibile utilizzare una funzione definita dall'utente che restituisca un valore scalare.</span><span class="sxs-lookup"><span data-stu-id="476c0-121">To calculate a derived column, you can use SQL syntax, as in the preceding example, or you can use a user-defined function that returns a scalar value.</span></span> <span data-ttu-id="476c0-122">Per ulteriori informazioni sulle funzioni definite dall'utente, vedere la documentazione di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="476c0-122">For more information about user-defined functions, see the SQL Server documentation.</span></span>  
  
-   <span data-ttu-id="476c0-123">**È possibile ordinare righe raggruppate**. Ad esempio, si può creare un set di risultati in cui ogni riga descrive una città e il numero di autori in tale città, riportando per prime le città con più autori.</span><span class="sxs-lookup"><span data-stu-id="476c0-123">**You can sort grouped rows** For example; you can create a result set in which each row describes a city, plus the number of authors in that city - with the cities containing many authors appearing first.</span></span> <span data-ttu-id="476c0-124">Il codice SQL risultante potrebbe essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="476c0-124">The resulting SQL might look like this:</span></span>  
  
    ```  
    SELECT city, state, COUNT(*)  
    FROM authors  
    GROUP BY city, state  
    ORDER BY COUNT(*) DESC, state  
  
    ```  
  
     <span data-ttu-id="476c0-125">Si noti che la query utilizza `state` come colonna di ordinamento secondaria.</span><span class="sxs-lookup"><span data-stu-id="476c0-125">Notice that the query uses `state` as a secondary sort column.</span></span> <span data-ttu-id="476c0-126">Due stati che hanno lo stesso numero di autori verranno quindi disposti in ordine alfabetico.</span><span class="sxs-lookup"><span data-stu-id="476c0-126">Thus, if two states have the same number of authors, those states will appear in alphabetical order.</span></span>  
  
-   <span data-ttu-id="476c0-127">**È possibile eseguire l'ordinamento usando dati internazionali** È possibile ordinare una colonna usando convenzioni di confronto diverse dalle convenzioni predefinite per tale colonna.</span><span class="sxs-lookup"><span data-stu-id="476c0-127">**You can sort using international data** That is; you can sort a column using collating conventions that differ from the default conventions for that column.</span></span> <span data-ttu-id="476c0-128">Ad esempio, è possibile scrivere una query che recupera tutti i titoli dei libri di Jaime pati?? o.</span><span class="sxs-lookup"><span data-stu-id="476c0-128">For example, you can write a query that retrieves all the book titles by Jaime Pati??o.</span></span> <span data-ttu-id="476c0-129">Per visualizzare i titoli in ordine alfabetico, si utilizza una sequenza di confronto spagnola per la colonna title.</span><span class="sxs-lookup"><span data-stu-id="476c0-129">To display the titles in alphabetical order, you use a Spanish collating sequence for the title column.</span></span> <span data-ttu-id="476c0-130">Il codice SQL risultante potrebbe essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="476c0-130">The resulting SQL might look like this:</span></span>  
  
    ```  
    SELECT title  
    FROM   
        authors   
        INNER JOIN   
            titleauthor   
            ON authors.au_id   
            =  titleauthor.au_id   
            INNER JOIN  
                titles   
                ON titleauthor.title_id   
                =  titles.title_id   
    WHERE   
         au_fname = 'Jaime' AND   
         au_lname = 'Pati??o'  
    ORDER BY   
         title COLLATE SQL_Spanish_Pref_CP1_CI_AS  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="476c0-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="476c0-131">See Also</span></span>  
 <span data-ttu-id="476c0-132">[Ordinare e raggruppare i risultati delle query &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="476c0-132">[Sort and Group Query Results &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="476c0-133">Procedure per la progettazione di query e viste &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="476c0-133">Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;</span></span>](design-queries-and-views-how-to-topics-visual-database-tools.md)  
  
  
