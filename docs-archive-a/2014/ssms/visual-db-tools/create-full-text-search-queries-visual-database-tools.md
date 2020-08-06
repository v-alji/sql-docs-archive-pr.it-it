---
title: Creare query di ricerca full-text (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- CONTAINS predicate (Transact-SQL)
- queries [full-text search], creating
- full-text queries [SQL Server], creating
ms.assetid: 537fa556-390e-4c88-9b8e-679848d94abc
author: stevestein
ms.author: sstein
ms.openlocfilehash: f84ab465da0a1b7ac1da1211de1d5199fd28ee95
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714968"
---
# <a name="create-full-text-search-queries-visual-database-tools"></a><span data-ttu-id="a4c72-102">Creazione di query di ricerca full-text (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="a4c72-102">Create Full-Text Search Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="a4c72-103">Nelle ricerche full-text viene utilizzato il predicato CONTAINS per individuare le righe contenenti in una colonna specifica il testo desiderato.</span><span class="sxs-lookup"><span data-stu-id="a4c72-103">Full-text searches use the CONTAINS predicate to locate rows that have specified text in a given column.</span></span> <span data-ttu-id="a4c72-104">Le ricerche full-text possono essere eseguite solo in colonne con indici full-text attivi.</span><span class="sxs-lookup"><span data-stu-id="a4c72-104">Full-Text searches are only possible on columns that have active full-text indexes.</span></span> <span data-ttu-id="a4c72-105">Se si tenta di utilizzare la clausola CONTAINS in una colonna che non contiene un indice full-text attualmente attivo, verrà visualizzato un errore.</span><span class="sxs-lookup"><span data-stu-id="a4c72-105">If you attempt to use the CONTAINS clause on a column that does not have a currently active full-text index, you will receive an error.</span></span> <span data-ttu-id="a4c72-106">Per ulteriori informazioni sugli indici full-text e sulla clausola CONTAINs, vedere [ricerca full-text](../../relational-databases/search/full-text-search.md) e [contiene &#40;&#41;Transact-SQL ](/sql/t-sql/queries/contains-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a4c72-106">For more information on full-text indexes and the CONTAINS clause, see [Full-Text Search](../../relational-databases/search/full-text-search.md) and [CONTAINS &#40;Transact-SQL&#41;](/sql/t-sql/queries/contains-transact-sql).</span></span>  
  
### <a name="to-create-a-full-text-search-query"></a><span data-ttu-id="a4c72-107">Per creare una query di ricerca full-text</span><span class="sxs-lookup"><span data-stu-id="a4c72-107">To create a full-text search query</span></span>  
  
1.  <span data-ttu-id="a4c72-108">Aprire una query in Esplora soluzioni o crearne una nuova.</span><span class="sxs-lookup"><span data-stu-id="a4c72-108">Open a query from Solution Explorer or create a new one.</span></span>  
  
2.  <span data-ttu-id="a4c72-109">Nella clausola WHERE della query utilizzare la funzione CONTAINS per eseguire una ricerca in una colonna di testo completo.</span><span class="sxs-lookup"><span data-stu-id="a4c72-109">In the WHERE clause of your query, use the CONTAINS function to search a full-text column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4c72-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a4c72-110">See Also</span></span>  
 <span data-ttu-id="a4c72-111">[Tipi di query supportati &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="a4c72-111">[Supported Query Types &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 <span data-ttu-id="a4c72-112">[Procedure per la progettazione di query e viste &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="a4c72-112">[Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="a4c72-113">Eseguire operazioni di base con le query &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="a4c72-113">Perform Basic Operations with Queries &#40;Visual Database Tools&#41;</span></span>](perform-basic-operations-with-queries-visual-database-tools.md)  
  
  
