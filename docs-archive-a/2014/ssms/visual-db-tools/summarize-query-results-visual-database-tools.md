---
title: Riepilogare i risultati di query (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- summarizing query results
- queries [SQL Server], results
- aggregate queries [SQL Server]
ms.assetid: c9e15350-ed57-4d95-814d-815fbebfd86b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 08713be2d4439e520df07ec5efd6cb761a78a994
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720718"
---
# <a name="summarize-query-results-visual-database-tools"></a><span data-ttu-id="e3072-102">Riepilogo dei risultati di query (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="e3072-102">Summarize Query Results (Visual Database Tools)</span></span>
  <span data-ttu-id="e3072-103">Quando si creano query di aggregazione, è necessario rispettare alcuni principi logici.</span><span class="sxs-lookup"><span data-stu-id="e3072-103">When you create aggregate queries, certain logical principles apply.</span></span> <span data-ttu-id="e3072-104">Non è, ad esempio, possibile visualizzare il contenuto di singole righe in una query di riepilogo.</span><span class="sxs-lookup"><span data-stu-id="e3072-104">For example, you cannot display the contents of individual rows in a summary query.</span></span> <span data-ttu-id="e3072-105">Progettazione query e Progettazione viste agevola il rispetto di tali principi mediante le particolari modalità di funzionamento del [riquadro Diagramma](visual-database-tools.md) e del [riquadro Criteri](criteria-pane-visual-database-tools.md) .</span><span class="sxs-lookup"><span data-stu-id="e3072-105">The Query and View Designer helps you comply with these principles in the way the [Diagram pane](visual-database-tools.md) and [Criteria pane](criteria-pane-visual-database-tools.md) behave.</span></span>  
  
 <span data-ttu-id="e3072-106">La conoscenza dei principi alla base delle query di aggregazione e del funzionamento di Progettazione query e Progettazione viste consente di creare query di aggregazione corrette da un punto di vista logico.</span><span class="sxs-lookup"><span data-stu-id="e3072-106">By understanding the principles of aggregate queries and the Query and View Designer's behavior, you can create logically correct aggregate queries.</span></span> <span data-ttu-id="e3072-107">Il principio fondamentale è che le query di aggregazione possono dare come risultato soltanto informazioni di riepilogo.</span><span class="sxs-lookup"><span data-stu-id="e3072-107">The overriding principle is that aggregate queries can result only in summary information.</span></span> <span data-ttu-id="e3072-108">Di conseguenza, la maggior parte dei principi che seguono descrive le modalità in base a cui è possibile fare riferimento a singole colonne di dati all'interno di una query di aggregazione.</span><span class="sxs-lookup"><span data-stu-id="e3072-108">Thus, most of the principles that follow describe the ways that you can reference individual data columns within an aggregate query.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e3072-109">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="e3072-109">In This Section</span></span>  
 [<span data-ttu-id="e3072-110">Utilizzo di colonne in query di aggregazione &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="e3072-110">Work with Columns in Aggregate Queries &#40;Visual Database Tools&#41;</span></span>](work-with-columns-in-aggregate-queries-visual-database-tools.md)  
 <span data-ttu-id="e3072-111">Vengono descritte le nozioni di base per il raggruppamento e il riepilogo delle colonne con le clausole GROUP BY, WHERE e HAVING.</span><span class="sxs-lookup"><span data-stu-id="e3072-111">Describes concepts about grouping and summarizing columns with the GROUP BY, WHERE, and HAVING clauses.</span></span>  
  
 [<span data-ttu-id="e3072-112">Conteggio delle righe di una tabella &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="e3072-112">Count Rows in a Table &#40;Visual Database Tools&#41;</span></span>](count-rows-in-a-table-visual-database-tools.md)  
 <span data-ttu-id="e3072-113">Viene descritta la procedura per contare il numero di righe di una tabella o il numero di righe di una tabella corrispondenti a un set di criteri.</span><span class="sxs-lookup"><span data-stu-id="e3072-113">Provides steps for counting the number of rows in a table or the number of rows in a table that meet a set of criteria.</span></span>  
  
 [<span data-ttu-id="e3072-114">Riepilogo o aggregazione di valori per tutte le righe di una tabella &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="e3072-114">Summarize or Aggregate Values for All Rows in a Table &#40;Visual Database Tools&#41;</span></span>](summarize-or-aggregate-values-for-all-rows-in-a-table-visual-database-tools.md)  
 <span data-ttu-id="e3072-115">Viene descritta la procedura per riepilogare tutte le righe anziché un set di righe raggruppate.</span><span class="sxs-lookup"><span data-stu-id="e3072-115">Provides steps for summarizing all rows rather than for a set of grouped rows.</span></span>  
  
 [<span data-ttu-id="e3072-116">Riepilogo o aggregazione di valori mediante l'utilizzo di espressioni personalizzate &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="e3072-116">Summarize or Aggregate Values Using Custom Expressions &#40;Visual Database Tools&#41;</span></span>](summarize-or-aggregate-values-using-custom-expressions-visual-database-tools.md)  
 <span data-ttu-id="e3072-117">Viene descritta la procedura per utilizzare le espressioni per il riepilogo o l'aggregazione anziché le clausole prestabilite.</span><span class="sxs-lookup"><span data-stu-id="e3072-117">Provides steps for using expressions to summarize or aggregate rather than using the predefined clauses.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="e3072-118">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="e3072-118">Related Sections</span></span>  
 [<span data-ttu-id="e3072-119">Procedure per la progettazione di query e viste &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="e3072-119">Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;</span></span>](design-queries-and-views-how-to-topics-visual-database-tools.md)  
 <span data-ttu-id="e3072-120">Vengono forniti collegamenti ad argomenti in cui viene descritto come utilizzare Progettazione query e Progettazione viste.</span><span class="sxs-lookup"><span data-stu-id="e3072-120">Provides links to topics covering how to use the Query and View Designer.</span></span>  
  
  
