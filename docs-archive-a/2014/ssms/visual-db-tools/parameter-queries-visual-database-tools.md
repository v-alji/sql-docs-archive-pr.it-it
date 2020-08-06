---
title: Query con parametri (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- parameter queries [SQL Server]
ms.assetid: 4897c41a-324a-47b8-a30b-cbc9e9e19a8b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7f6fd94ef180a34ae91d52c213092898612dc77d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630200"
---
# <a name="parameter-queries-visual-database-tools"></a><span data-ttu-id="bed7a-102">Query con parametri (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="bed7a-102">Parameter Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="bed7a-103">In alcuni casi potrebbe essere necessario creare una query da utilizzare più volte, specificando però ogni volta un valore diverso.</span><span class="sxs-lookup"><span data-stu-id="bed7a-103">In some cases you want to create a query that you can use many times, but with a different value each time.</span></span> <span data-ttu-id="bed7a-104">Se, ad esempio, si eseguono di frequente delle query per individuare tutti i `title_ids` di un determinato autore,</span><span class="sxs-lookup"><span data-stu-id="bed7a-104">For example, you might frequently run a query to find all the `title_ids` written by one author.</span></span> <span data-ttu-id="bed7a-105">è possibile utilizzare la stessa query per tutte le richieste specificando però ogni volta un ID o un nome di autore diverso.</span><span class="sxs-lookup"><span data-stu-id="bed7a-105">You could run the same query for each request, except that the author's ID or name would be different each time.</span></span>  
  
 <span data-ttu-id="bed7a-106">Per creare una query che può accettare valori diversi in momenti diversi, è necessario utilizzare i parametri.</span><span class="sxs-lookup"><span data-stu-id="bed7a-106">To create a query that can have different values at different times, you use parameters in the query.</span></span> <span data-ttu-id="bed7a-107">Un parametro è un segnaposto per un valore che verrà fornito durante l'esecuzione della query.</span><span class="sxs-lookup"><span data-stu-id="bed7a-107">A parameter is a placeholder for a value that is supplied when the query runs.</span></span> <span data-ttu-id="bed7a-108">Un'istruzione SQL con un parametro potrebbe essere simile alla seguente, dove "?" rappresenta il parametro relativo all'ID dell'autore:</span><span class="sxs-lookup"><span data-stu-id="bed7a-108">An SQL statement with a parameter might look like the following, where "?" represents the parameter for the author's ID:</span></span>  
  
```  
SELECT title_id  
FROM titleauthor  
WHERE (au_id = ?)  
```  
  
## <a name="where-you-can-use-parameters"></a><span data-ttu-id="bed7a-109">Possibili utilizzi dei parametri</span><span class="sxs-lookup"><span data-stu-id="bed7a-109">Where You Can Use Parameters</span></span>  
 <span data-ttu-id="bed7a-110">È possibile usare i parametri come segnaposto per valori letterali (per valori di testo o numerici).</span><span class="sxs-lookup"><span data-stu-id="bed7a-110">You can use parameters as placeholders for literal values - for either text or numeric values.</span></span> <span data-ttu-id="bed7a-111">Nella maggior parte dei casi i parametri vengono utilizzati come segnaposto all'interno di condizioni di ricerca per singole righe o per gruppi, ovvero nelle clausole WHERE o HAVING di un'istruzione SQL.</span><span class="sxs-lookup"><span data-stu-id="bed7a-111">Most commonly, parameters are used as placeholders in search conditions for individual rows or for groups (that is, in the WHERE or HAVING clauses of an SQL statement).</span></span>  
  
 <span data-ttu-id="bed7a-112">I parametri possono essere utilizzati nelle espressioni come segnaposto.</span><span class="sxs-lookup"><span data-stu-id="bed7a-112">You can use parameters as placeholders in expressions.</span></span> <span data-ttu-id="bed7a-113">Si supponga ad esempio di voler calcolare prezzi scontati specificando un valore di sconto diverso a ogni esecuzione della query.</span><span class="sxs-lookup"><span data-stu-id="bed7a-113">For example, you might want to calculate discounted prices by supplying a different discount value each time you run a query.</span></span> <span data-ttu-id="bed7a-114">A tale scopo, è possibile utilizzare la seguente espressione:</span><span class="sxs-lookup"><span data-stu-id="bed7a-114">To do so, you could specify the following expression:</span></span>  
  
```  
(price * ?)  
```  
  
## <a name="specifying-unnamed-and-named-parameters"></a><span data-ttu-id="bed7a-115">Specifica di parametri denominati e non denominati</span><span class="sxs-lookup"><span data-stu-id="bed7a-115">Specifying Unnamed and Named Parameters</span></span>  
 <span data-ttu-id="bed7a-116">È possibile specificare due tipi di parametri: denominati e non denominati.</span><span class="sxs-lookup"><span data-stu-id="bed7a-116">You can specify two types of parameters: unnamed and named.</span></span> <span data-ttu-id="bed7a-117">Un parametro non denominato è un punto di domanda (?) che è possibile inserire in una posizione qualsiasi della query per richiedere o per sostituire un valore letterale.</span><span class="sxs-lookup"><span data-stu-id="bed7a-117">An unnamed parameter is a question mark (?) that you put anywhere in the query that you want to prompt for or substitute a literal value.</span></span> <span data-ttu-id="bed7a-118">Se, ad esempio, si usa un parametro non denominato per cercare l'ID di un autore nella tabella `titleauthor` , l'istruzione risultante nel [riquadro SQL](visual-database-tools.md) potrebbe essere simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="bed7a-118">For example, if you use an unnamed parameter to search for an author's id in the `titleauthor` table, the resulting statement in the [SQL Pane](visual-database-tools.md) might look like this:</span></span>  
  
```  
SELECT title_id  
FROM titleauthor  
WHERE (au_id = ?)  
```  
  
 <span data-ttu-id="bed7a-119">Al momento dell'esecuzione della query in [Progettazione query e Progettazione viste](query-and-view-designer-tools-visual-database-tools.md), nella [finestra di dialogo Parametri query](query-parameters-dialog-box-visual-database-tools.md) viene visualizzato un punto interrogativo ("?") come nome del parametro.</span><span class="sxs-lookup"><span data-stu-id="bed7a-119">When you run the query in the [Query and View Designer](query-and-view-designer-tools-visual-database-tools.md), the [Query Parameters Dialog Box](query-parameters-dialog-box-visual-database-tools.md) appears with "?" as the name of the parameter.</span></span>  
  
 <span data-ttu-id="bed7a-120">In alternativa, è possibile assegnare un nome a un parametro.</span><span class="sxs-lookup"><span data-stu-id="bed7a-120">Alternatively, you can assign a name to a parameter.</span></span> <span data-ttu-id="bed7a-121">I parametri denominati risultano particolarmente utili quando in una query sono presenti più parametri.</span><span class="sxs-lookup"><span data-stu-id="bed7a-121">Named parameters are particularly useful if you have multiple parameters in a query.</span></span> <span data-ttu-id="bed7a-122">Se, ad esempio, si utilizzano parametri denominati per cercare il nome e il cognome di un autore in una tabella `authors` , l'istruzione risultante nel riquadro SQL potrebbe essere simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="bed7a-122">For example, if you use named parameters to search for an author's first and last names in the `authors` table, the resulting statement in the SQL pane might look like this:</span></span>  
  
```  
SELECT au_id  
FROM authors  
WHERE au_fname = %first name% AND  
      au_lname = %last name%  
```  
  
> [!TIP]  
>  <span data-ttu-id="bed7a-123">Prima di creare una query con parametri denominati, è necessario definire i caratteri del prefisso e del suffisso.</span><span class="sxs-lookup"><span data-stu-id="bed7a-123">You must define prefix and suffix characters before creating a named parameter query.</span></span>  
  
 <span data-ttu-id="bed7a-124">Al momento dell'esecuzione della query in Progettazione query e Progettazione viste, nella [finestra di dialogo Parametri query](query-parameters-dialog-box-visual-database-tools.md) viene visualizzato un elenco di parametri denominati.</span><span class="sxs-lookup"><span data-stu-id="bed7a-124">When you run the query in the Query and View Designer, the [Query Parameters Dialog Box](query-parameters-dialog-box-visual-database-tools.md) appears with a list of named parameters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bed7a-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bed7a-125">See Also</span></span>  
 <span data-ttu-id="bed7a-126">[Esecuzione di query con parametri &#40;Visual Database Tools&#41;](query-with-parameters-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="bed7a-126">[Query with Parameters &#40;Visual Database Tools&#41;](query-with-parameters-visual-database-tools.md) </span></span>  
 <span data-ttu-id="bed7a-127">[Tipi di query supportati &#40;Visual Database Tools&#41;](supported-query-types-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="bed7a-127">[Supported Query Types &#40;Visual Database Tools&#41;](supported-query-types-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="bed7a-128">Procedure per la progettazione di query e viste &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="bed7a-128">Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;</span></span>](design-queries-and-views-how-to-topics-visual-database-tools.md)  
  
  
