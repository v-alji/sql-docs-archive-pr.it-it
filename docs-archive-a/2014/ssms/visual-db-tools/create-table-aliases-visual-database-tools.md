---
title: Creare alias di tabella (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- table aliases [SQL Server]
- aliases [SQL Server], tables
ms.assetid: 49e61e85-8abf-4ca7-8c70-7e9f8f1078bd
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8f9e6269fe6e24e8d98922094e799fbf4b5af584
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629697"
---
# <a name="create-table-aliases-visual-database-tools"></a><span data-ttu-id="93c24-102">Creazione di alias di tabella (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="93c24-102">Create Table Aliases (Visual Database Tools)</span></span>
  <span data-ttu-id="93c24-103">Gli alias possono semplificare l'utilizzo dei nomi di tabella.</span><span class="sxs-lookup"><span data-stu-id="93c24-103">Aliases can make it easier to work with table names.</span></span> <span data-ttu-id="93c24-104">L'utilizzo degli alias è utile se:</span><span class="sxs-lookup"><span data-stu-id="93c24-104">Using aliases is helpful when:</span></span>  
  
-   <span data-ttu-id="93c24-105">Si intende abbreviare e rendere più facilmente leggibile l'istruzione nel [riquadro SQL](visual-database-tools.md) .</span><span class="sxs-lookup"><span data-stu-id="93c24-105">You want to make the statement in the [SQL Pane](visual-database-tools.md) shorter and easier to read.</span></span>  
  
-   <span data-ttu-id="93c24-106">Nella query si fa spesso riferimento al nome della tabella, ad esempio nei nomi che qualificano una colonna, e ci si vuole assicurare che venga rispettato un limite specifico per la lunghezza dei caratteri nella query.</span><span class="sxs-lookup"><span data-stu-id="93c24-106">You refer to the table name often in your query - such as in qualifying column names - and want to be sure you stay within a specific character-length limit for your query.</span></span> <span data-ttu-id="93c24-107">Alcuni database, infatti, impongono una lunghezza massima per le query.</span><span class="sxs-lookup"><span data-stu-id="93c24-107">(Some databases impose a maximum length for queries.)</span></span>  
  
-   <span data-ttu-id="93c24-108">Si utilizzano più istanze della stessa tabella (come in un self-join) ed è necessario fare riferimento a un'istanza o un'altra.</span><span class="sxs-lookup"><span data-stu-id="93c24-108">You are working with multiple instances of the same table (such as in a self-join) and need a way to refer to one instance or the other.</span></span>  
  
 <span data-ttu-id="93c24-109">È ad esempio possibile creare un alias `"e"` per un nome di tabella `employee`_`information`, quindi fare riferimento alla tabella con `"e"` in tutto il resto della query.</span><span class="sxs-lookup"><span data-stu-id="93c24-109">For example, you can create an alias `"e"` for a table name `employee`_`information`, and then refer to the table as `"e"` throughout the rest of the query.</span></span>  
  
### <a name="to-create-an-alias-for-a-table-or-table-valued-object"></a><span data-ttu-id="93c24-110">Per creare un alias per una tabella o un oggetto con valori di tabella</span><span class="sxs-lookup"><span data-stu-id="93c24-110">To create an alias for a table or table-valued object</span></span>  
  
1.  <span data-ttu-id="93c24-111">Aggiungere alla query la tabella o l'oggetto con valori di tabella.</span><span class="sxs-lookup"><span data-stu-id="93c24-111">Add the table or table-valued object to your query.</span></span>  
  
2.  <span data-ttu-id="93c24-112">Nel **riquadro diagramma**fare clic con il pulsante destro del mouse sull'oggetto per cui si vuole creare un alias e scegliere **Proprietà** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="93c24-112">In the **Diagram Pane**, right-click the object for which you want to create an alias, then select **Properties** from the shortcut menu.</span></span>  
  
3.  <span data-ttu-id="93c24-113">Nella finestra **Proprietà** immettere l'alias nel campo **Alias** .</span><span class="sxs-lookup"><span data-stu-id="93c24-113">In the **Properties** window, enter the alias in the **Alias** field.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93c24-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="93c24-114">See Also</span></span>  
 <span data-ttu-id="93c24-115">[Aggiunta di tabelle a query &#40;Visual Database Tools&#41;](add-tables-to-queries-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="93c24-115">[Add Tables to Queries &#40;Visual Database Tools&#41;](add-tables-to-queries-visual-database-tools.md) </span></span>  
 <span data-ttu-id="93c24-116">[Ordinare e raggruppare i risultati delle query &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="93c24-116">[Sort and Group Query Results &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span></span>  
 <span data-ttu-id="93c24-117">[Riepilogare i risultati delle query &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="93c24-117">[Summarize Query Results &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="93c24-118">Eseguire operazioni di base con le query &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="93c24-118">Perform Basic Operations with Queries &#40;Visual Database Tools&#41;</span></span>](perform-basic-operations-with-queries-visual-database-tools.md)  
  
  
