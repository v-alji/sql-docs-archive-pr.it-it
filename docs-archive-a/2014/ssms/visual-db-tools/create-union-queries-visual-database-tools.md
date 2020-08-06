---
title: Creare query UNION (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- queries [SQL Server], types
- UNION queries
- Select query
- combining query results
- merged SELECT query [SQL Server]
ms.assetid: b5aafb1d-e4ed-4922-b790-56abc5ec551a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3c10f39c3e44844c4ec8a6a2328c41ea2de350d2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629696"
---
# <a name="create-union-queries-visual-database-tools"></a><span data-ttu-id="711b8-102">Creare query UNION (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="711b8-102">Create UNION Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="711b8-103">La parola chiave UNION consente di includere i risultati di due istruzioni SELECT in una tabella risultante.</span><span class="sxs-lookup"><span data-stu-id="711b8-103">The UNION keyword enables you to include the results of two SELECT statements in one resulting table.</span></span> <span data-ttu-id="711b8-104">Tutte le righe restituite dalle due istruzioni SELECT vengono combinate nel risultato dell'espressione UNION.</span><span class="sxs-lookup"><span data-stu-id="711b8-104">All rows returned from either SELECT statement are combined into the result of the UNION expression.</span></span> <span data-ttu-id="711b8-105">Per esempi, vedere gli [esempi di selezione &#40;&#41;Transact-SQL ](/sql/t-sql/queries/select-examples-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="711b8-105">For examples, see [SELECT Examples &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-examples-transact-sql).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="711b8-106">Poiché nel riquadro Diagramma è possibile visualizzare solo una clausola SELECT,</span><span class="sxs-lookup"><span data-stu-id="711b8-106">The Diagram pane can only display one SELECT clause.</span></span> <span data-ttu-id="711b8-107">quando si lavora a una query di unione (query UNION), il Riquadro operazioni tabella verrà nascosto in Progettazione query.</span><span class="sxs-lookup"><span data-stu-id="711b8-107">Therefore, when you are working with a UNION query, Query Designer hides the Table Operations pane.</span></span>  
  
### <a name="to-create-a-merged-select-query"></a><span data-ttu-id="711b8-108">Per creare una query SELECT unita</span><span class="sxs-lookup"><span data-stu-id="711b8-108">To create a Merged SELECT query</span></span>  
  
1.  <span data-ttu-id="711b8-109">Aprire una query esistente o crearne una nuova.</span><span class="sxs-lookup"><span data-stu-id="711b8-109">Open a query or create a new one.</span></span>  
  
2.  <span data-ttu-id="711b8-110">Nel riquadro SQL digitare un'espressione UNION valida.</span><span class="sxs-lookup"><span data-stu-id="711b8-110">In the SQL pane, type a valid UNION expression.</span></span>  
  
     <span data-ttu-id="711b8-111">Nell'esempio seguente viene illustrata un'espressione UNION valida.</span><span class="sxs-lookup"><span data-stu-id="711b8-111">The following example is a valid UNION expression.</span></span>  
  
    ```  
    SELECT ProductModelID, Name  
    FROM Production.ProductModel  
    UNION  
    SELECT ProductModelID, Name   
    FROM dbo.Gloves;  
    ```  
  
3.  <span data-ttu-id="711b8-112">Per eseguire la query, scegliere **Esegui SQL** dal menu **Progettazione query** .</span><span class="sxs-lookup"><span data-stu-id="711b8-112">On the **Query Designer** menu, click **Execute SQL** to run the query.</span></span>  
  
     <span data-ttu-id="711b8-113">La query di unione verrà così formattata da Progettazione query.</span><span class="sxs-lookup"><span data-stu-id="711b8-113">Your UNION query is now formatted by Query Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="711b8-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="711b8-114">See Also</span></span>  
 <span data-ttu-id="711b8-115">[Tipi di query supportati &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="711b8-115">[Supported Query Types &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 <span data-ttu-id="711b8-116">[Procedure per la progettazione di query e viste &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="711b8-116">[Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span></span>  
 <span data-ttu-id="711b8-117">[Esecuzione di operazioni di base con le query &#40;Visual Database Tools&#41;](perform-basic-operations-with-queries-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="711b8-117">[Perform Basic Operations with Queries &#40;Visual Database Tools&#41;](perform-basic-operations-with-queries-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="711b8-118">UNION &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="711b8-118">UNION &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/set-operators-union-transact-sql)  
  
  
