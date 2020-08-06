---
title: Specificare più condizioni di ricerca per una sola colonna (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- search criteria [SQL Server], multiple conditions
- multiple search conditions
- search conditions [SQL Server], multiple
- OR operator
- AND, Criteria pane
ms.assetid: 2c006e36-56b1-4992-89b4-c6c0b19808f3
author: stevestein
ms.author: sstein
ms.openlocfilehash: a07322120bd3b3f543e6f54fa50cdf75aa32be59
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628059"
---
# <a name="specify-multiple-search-conditions-for-one-column-visual-database-tools"></a><span data-ttu-id="09828-102">Definizione di più condizioni di ricerca per una sola colonna (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="09828-102">Specify Multiple Search Conditions for One Column (Visual Database Tools)</span></span>
  <span data-ttu-id="09828-103">In alcuni casi può essere necessario applicare diverse condizioni di ricerca a una stessa colonna di dati.</span><span class="sxs-lookup"><span data-stu-id="09828-103">In some instances, you might want to apply a number of search conditions to the same data column.</span></span> <span data-ttu-id="09828-104">Può, ad esempio, essere necessario:</span><span class="sxs-lookup"><span data-stu-id="09828-104">For example, you might want to:</span></span>  
  
-   <span data-ttu-id="09828-105">Cercare diversi nomi o dipendenti con diverse fasce di stipendio in una tabella `employee` .</span><span class="sxs-lookup"><span data-stu-id="09828-105">Search for several different names in an `employee` table or for employees who are in different salary ranges.</span></span> <span data-ttu-id="09828-106">Questo tipo di ricerca richiede una condizione OR.</span><span class="sxs-lookup"><span data-stu-id="09828-106">This type of search requires an OR condition.</span></span>  
  
-   <span data-ttu-id="09828-107">Cercare il titolo di un libro che inizi con la parola "Il" e contenga la parola "cuoco".</span><span class="sxs-lookup"><span data-stu-id="09828-107">Search for a book title that both starts with the word "The" and contains the word "Cook."</span></span> <span data-ttu-id="09828-108">Questo tipo di ricerca richiede una condizione AND.</span><span class="sxs-lookup"><span data-stu-id="09828-108">This type of search requires an AND condition.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="09828-109">Le informazioni contenute in questo argomento sono valide per le condizioni di ricerca nelle clausole WHERE e HAVING di una query.</span><span class="sxs-lookup"><span data-stu-id="09828-109">The information in this topic applies to search conditions in both the WHERE and HAVING clauses of a query.</span></span> <span data-ttu-id="09828-110">Gli esempi sono incentrati sulla creazione di clausole WHERE, ma i principi sono validi per entrambi i tipi di condizione di ricerca.</span><span class="sxs-lookup"><span data-stu-id="09828-110">The examples focus on creating WHERE clauses, but the principles apply to both types of search conditions.</span></span>  
  
 <span data-ttu-id="09828-111">Per cercare valori alternativi nella stessa colonna di dati, specificare una condizione OR.</span><span class="sxs-lookup"><span data-stu-id="09828-111">To search for alternative values in the same data column, you specify an OR condition.</span></span> <span data-ttu-id="09828-112">Per cercare valori che soddisfino più condizioni, specificare una condizione AND.</span><span class="sxs-lookup"><span data-stu-id="09828-112">To search for values that meet several conditions, you specify an AND condition.</span></span>  
  
## <a name="specifying-an-or-condition"></a><span data-ttu-id="09828-113">Specifica di una condizione OR</span><span class="sxs-lookup"><span data-stu-id="09828-113">Specifying an OR Condition</span></span>  
 <span data-ttu-id="09828-114">La condizione OR consente di specificare diversi valori alternativi da cercare in una colonna.</span><span class="sxs-lookup"><span data-stu-id="09828-114">Using an OR condition enables you to specify several alternative values to search for in a column.</span></span> <span data-ttu-id="09828-115">Questa opzione amplia l'ambito della ricerca e può restituire più righe rispetto alla ricerca di un valore singolo.</span><span class="sxs-lookup"><span data-stu-id="09828-115">This option expands the scope of the search and can return more rows than searching for a single value.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="09828-116">In alternativa, è spesso possibile utilizzare l'operatore IN per cercare più valori in una stessa colonna di dati.</span><span class="sxs-lookup"><span data-stu-id="09828-116">You can often use the IN operator instead to search for multiple values in the same data column.</span></span>  
  
#### <a name="to-specify-an-or-condition"></a><span data-ttu-id="09828-117">Per specificare una condizione OR</span><span class="sxs-lookup"><span data-stu-id="09828-117">To specify an OR condition</span></span>  
  
1.  <span data-ttu-id="09828-118">Nel [riquadro Criteri](visual-database-tools.md)aggiungere la colonna da includere nella ricerca.</span><span class="sxs-lookup"><span data-stu-id="09828-118">In the [Criteria Pane](visual-database-tools.md), add the column to search.</span></span>  
  
2.  <span data-ttu-id="09828-119">Nella colonna **Filtro** per la colonna di dati appena aggiunta specificare la prima condizione.</span><span class="sxs-lookup"><span data-stu-id="09828-119">In the **Filter** column for the data column you just added, specify the first condition.</span></span>  
  
3.  <span data-ttu-id="09828-120">Nella colonna **Or...** per la stessa colonna di dati specificare la seconda condizione.</span><span class="sxs-lookup"><span data-stu-id="09828-120">In the **Or...** column for the same data column, specify the second condition.</span></span>  
  
 <span data-ttu-id="09828-121">In Progettazione query e Progettazione viste viene creata una clausola WHERE contenente una condizione OR analoga alla seguente:</span><span class="sxs-lookup"><span data-stu-id="09828-121">The Query and View Designer creates a WHERE clause that contains an OR condition such as the following:</span></span>  
  
```  
SELECT fname, lname  
FROM employees  
WHERE (salary < 30000) OR (salary > 100000)  
```  
  
## <a name="specifying-an-and-condition"></a><span data-ttu-id="09828-122">Specifica di una condizione AND</span><span class="sxs-lookup"><span data-stu-id="09828-122">Specifying an AND Condition</span></span>  
 <span data-ttu-id="09828-123">La condizione AND consente di specificare che i valori in una colonna devono soddisfare due o più condizioni affinché la riga venga inclusa nel set di risultati.</span><span class="sxs-lookup"><span data-stu-id="09828-123">Using an AND condition enables you to specify that values in a column must meet two (or more) conditions for the row to be included in the result set.</span></span> <span data-ttu-id="09828-124">Questa opzione restringe l'ambito della ricerca e in genere restituisce meno righe rispetto alla ricerca di un valore singolo.</span><span class="sxs-lookup"><span data-stu-id="09828-124">This option narrows the scope of the search and usually returns fewer rows than searching for a single value.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="09828-125">Se si cerca un intervallo di valori, sarà possibile utilizzare l'operatore BETWEEN anziché collegare due condizioni con AND.</span><span class="sxs-lookup"><span data-stu-id="09828-125">If you are searching for a range of values, you can use the BETWEEN operator instead of linking two conditions with AND.</span></span>  
  
#### <a name="to-specify-an-and-condition"></a><span data-ttu-id="09828-126">Per specificare una condizione AND</span><span class="sxs-lookup"><span data-stu-id="09828-126">To specify an AND condition</span></span>  
  
1.  <span data-ttu-id="09828-127">Nel riquadro Criteri aggiungere la colonna da includere nella ricerca.</span><span class="sxs-lookup"><span data-stu-id="09828-127">In the Criteria pane, add the column to search.</span></span>  
  
2.  <span data-ttu-id="09828-128">Nella colonna **Filtro** per la colonna di dati appena aggiunta specificare la prima condizione.</span><span class="sxs-lookup"><span data-stu-id="09828-128">In the **Filter** column for the data column you just added, specify the first condition.</span></span>  
  
3.  <span data-ttu-id="09828-129">Aggiungere nuovamente la stessa colonna di dati al riquadro Criteri, collocandola in una riga vuota della griglia.</span><span class="sxs-lookup"><span data-stu-id="09828-129">Add the same data column to the Criteria pane again, placing it in an empty row of the grid.</span></span>  
  
4.  <span data-ttu-id="09828-130">Nella colonna **Filtro** per la seconda istanza della colonna di dati specificare la seconda condizione.</span><span class="sxs-lookup"><span data-stu-id="09828-130">In the **Filter** column for the second instance of the data column, specify the second condition.</span></span>  
  
 <span data-ttu-id="09828-131">In Progettazione query viene creata una clausola WHERE contenente una condizione AND analoga alla seguente:</span><span class="sxs-lookup"><span data-stu-id="09828-131">The Query Designer creates a WHERE clause that contains an AND condition such as the following:</span></span>  
  
```  
SELECT title_id, title  
FROM titles  
WHERE (title LIKE '%Cook%') AND   
  (title LIKE '%Recipe%')  
```  
  
## <a name="see-also"></a><span data-ttu-id="09828-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="09828-132">See Also</span></span>  
 <span data-ttu-id="09828-133">[Convenzioni per la combinazione di condizioni di ricerca nel riquadro Criteri &#40;Visual Database Tools&#41;](conventions-combine-search-conditions-in-criteria-pane-visual-db-tools.md) </span><span class="sxs-lookup"><span data-stu-id="09828-133">[Conventions for Combining Search Conditions in the Criteria Pane &#40;Visual Database Tools&#41;](conventions-combine-search-conditions-in-criteria-pane-visual-db-tools.md) </span></span>  
 [<span data-ttu-id="09828-134">Specifica dei criteri di ricerca &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="09828-134">Specify Search Criteria &#40;Visual Database Tools&#41;</span></span>](specify-search-criteria-visual-database-tools.md)  
  
  
