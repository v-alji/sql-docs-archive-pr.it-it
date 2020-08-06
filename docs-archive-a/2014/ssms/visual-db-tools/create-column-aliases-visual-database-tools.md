---
title: Creare alias di colonna (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- columns [SQL Server], aliases
- aliases [SQL Server], columns
ms.assetid: e2e1c166-8ea7-47a2-b6a7-e419bf0fa3bb
author: stevestein
ms.author: sstein
ms.openlocfilehash: febe7ed27ed10a283cab549bc65299577d69761c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626456"
---
# <a name="create-column-aliases-visual-database-tools"></a><span data-ttu-id="3a81a-102">Creazione di alias di colonna (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="3a81a-102">Create Column Aliases (Visual Database Tools)</span></span>
  <span data-ttu-id="3a81a-103">Gli alias dei nomi di colonna consentono di semplificare l'utilizzo dei nomi di colonna, dei calcoli e dei valori di riepilogo.</span><span class="sxs-lookup"><span data-stu-id="3a81a-103">You can create aliases for column names to make it easier to work with column names, calculations, and summary values.</span></span> <span data-ttu-id="3a81a-104">È possibile ad esempio creare un alias di colonna per:</span><span class="sxs-lookup"><span data-stu-id="3a81a-104">For example, you can create a column alias to:</span></span>  
  
-   <span data-ttu-id="3a81a-105">Creare un nome di colonna quale "Importo totale" per un'espressione come `(quantity * unit_price)` o per una funzione di aggregazione.</span><span class="sxs-lookup"><span data-stu-id="3a81a-105">Create a column name, such as "Total Amount," for an expression such as `(quantity * unit_price)` or for an aggregate function.</span></span>  
  
-   <span data-ttu-id="3a81a-106">Creare una versione abbreviata di un nome di colonna, ad esempio `"d_id"` per `"discounts.stor_id."`</span><span class="sxs-lookup"><span data-stu-id="3a81a-106">Create a shortened form of a column name, such as `"d_id"` for `"discounts.stor_id."`</span></span>  
  
 <span data-ttu-id="3a81a-107">Dopo avere definito un alias di colonna, è possibile utilizzarlo in una query di selezione per specificare l'output della query.</span><span class="sxs-lookup"><span data-stu-id="3a81a-107">After you have defined a column alias, you can use the alias in a Select query to specify query output.</span></span>  
  
### <a name="to-create-a-column-alias"></a><span data-ttu-id="3a81a-108">Per creare un alias di colonna</span><span class="sxs-lookup"><span data-stu-id="3a81a-108">To create a column alias</span></span>  
  
1.  <span data-ttu-id="3a81a-109">Nel **riquadro Criteri**individuare la riga contenente la colonna di dati per la quale si vuole creare un alias e, se necessario, contrassegnarla per l'output.</span><span class="sxs-lookup"><span data-stu-id="3a81a-109">In the **Criteria Pane**, locate the row containing the data column for which you want to create an alias, and if necessary, mark it for output.</span></span> <span data-ttu-id="3a81a-110">Se la colonna di dati non è già presente nella griglia, aggiungerla.</span><span class="sxs-lookup"><span data-stu-id="3a81a-110">If the data column is not already in the grid, add it.</span></span>  
  
2.  <span data-ttu-id="3a81a-111">Nella colonna **Alias** per tale riga specificare l'alias.</span><span class="sxs-lookup"><span data-stu-id="3a81a-111">In the **Alias** column for that row, enter the alias.</span></span> <span data-ttu-id="3a81a-112">seguendo le convenzioni di denominazione del linguaggio SQL.</span><span class="sxs-lookup"><span data-stu-id="3a81a-112">The alias must follow all naming conventions for SQL.</span></span> <span data-ttu-id="3a81a-113">Se si specifica un nome di alias contenente spazi, verranno inseriti automaticamente delimitatori all'inizio e alla fine di esso.</span><span class="sxs-lookup"><span data-stu-id="3a81a-113">If the alias name you enter contains spaces, the Query and View Designer automatically puts delimiters around it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a81a-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3a81a-114">See Also</span></span>  
 <span data-ttu-id="3a81a-115">[Aggiunta di colonne a query &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="3a81a-115">[Add Columns to Queries &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 <span data-ttu-id="3a81a-116">[Ordinare e raggruppare i risultati delle query &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="3a81a-116">[Sort and Group Query Results &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span></span>  
 <span data-ttu-id="3a81a-117">[Riepilogare i risultati delle query &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="3a81a-117">[Summarize Query Results &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="3a81a-118">Eseguire operazioni di base con le query &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="3a81a-118">Perform Basic Operations with Queries &#40;Visual Database Tools&#41;</span></span>](perform-basic-operations-with-queries-visual-database-tools.md)  
  
  
