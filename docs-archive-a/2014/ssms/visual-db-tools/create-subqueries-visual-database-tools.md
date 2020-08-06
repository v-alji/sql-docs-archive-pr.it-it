---
title: Creare sottoquery (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- search criteria [SQL Server], subqueries
- nested queries
- subqueries [SQL Server], SQL pane
ms.assetid: 34f6b9b4-ca3a-4a4f-9594-36e513f1c547
author: stevestein
ms.author: sstein
ms.openlocfilehash: 540228839b9734992be008b5d4fb7d717176832e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629698"
---
# <a name="create-subqueries-visual-database-tools"></a><span data-ttu-id="1008e-102">Creazione di sottoquery (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="1008e-102">Create Subqueries (Visual Database Tools)</span></span>
  <span data-ttu-id="1008e-103">È possibile utilizzare i risultati di una query come input per un'altra.</span><span class="sxs-lookup"><span data-stu-id="1008e-103">You can use the results of one query as the input for another.</span></span> <span data-ttu-id="1008e-104">I risultati di una sottoquery possono essere usati come istruzione che usa la funzione IN( ), l'operatore EXISTS o la clausola FROM.</span><span class="sxs-lookup"><span data-stu-id="1008e-104">You can use the results of a subquery as a statement that uses the IN( ) function, the EXISTS operator, or the FROM clause.</span></span>  
  
 <span data-ttu-id="1008e-105">Per creare una sottoquery, immetterla direttamente nel riquadro SQL oppure copiare una query e incollarla in un'altra query.</span><span class="sxs-lookup"><span data-stu-id="1008e-105">You can create a subquery by entering it directly into the SQL pane or by copying a query and pasting it into another.</span></span>  
  
### <a name="to-define-a-subquery-in-the-sql-pane"></a><span data-ttu-id="1008e-106">Per definire una sottoquery nel riquadro SQL</span><span class="sxs-lookup"><span data-stu-id="1008e-106">To define a subquery in the SQL pane</span></span>  
  
1.  <span data-ttu-id="1008e-107">Creare la query primaria.</span><span class="sxs-lookup"><span data-stu-id="1008e-107">Create the primary query.</span></span>  
  
2.  <span data-ttu-id="1008e-108">Selezionare l'istruzione SQL nel riquadro SQL e usare il comando **Copia** per copiare la query negli Appunti.</span><span class="sxs-lookup"><span data-stu-id="1008e-108">In the SQL pane, select the SQL statement, and then use **Copy** to move the query to the Clipboard.</span></span>  
  
3.  <span data-ttu-id="1008e-109">Iniziare la nuova query e usare il comando **Incolla** per spostare la prima query nella clausola WHERE o FROM della nuova query.</span><span class="sxs-lookup"><span data-stu-id="1008e-109">Start the new query, and then use **Paste** to move the first query into the new query's WHERE or FROM clause.</span></span>  
  
     <span data-ttu-id="1008e-110">Si supponga ad esempio di disporre di due tabelle, `products` e `suppliers`, e di creare una query che mostri tutti i prodotti dei fornitori in Svezia.</span><span class="sxs-lookup"><span data-stu-id="1008e-110">For example, imagine you have two tables, `products` and `suppliers`, and you want to create a query showing all products for suppliers in Sweden.</span></span> <span data-ttu-id="1008e-111">Creare la prima query sulla tabella `suppliers` per individuare tutti i fornitori svedesi:</span><span class="sxs-lookup"><span data-stu-id="1008e-111">Create the first query on the `suppliers` table to find all Swedish suppliers:</span></span>  
  
    ```  
    SELECT supplier_id  
    FROM supplier  
    WHERE (country = 'Sweden')  
    ```  
  
     <span data-ttu-id="1008e-112">Utilizzare il comando Copia per copiare la query negli Appunti.</span><span class="sxs-lookup"><span data-stu-id="1008e-112">Use the Copy command to move this query to the Clipboard.</span></span> <span data-ttu-id="1008e-113">Creare la seconda query utilizzando la tabella `products` , in cui sono elencate tutte le informazioni necessarie sui prodotti:</span><span class="sxs-lookup"><span data-stu-id="1008e-113">Create the second query using the `products` table, listing the information you need about products:</span></span>  
  
    ```  
    SELECT product_id, supplier_id, product_name  
    FROM products  
    ```  
  
     <span data-ttu-id="1008e-114">Nel riquadro SQL aggiungere una clausola WHERE alla seconda query, quindi incollare la prima query dagli Appunti.</span><span class="sxs-lookup"><span data-stu-id="1008e-114">In the SQL pane, add a WHERE clause to the second query, then paste the first query from the Clipboard.</span></span> <span data-ttu-id="1008e-115">Racchiudere fra parentesi la prima query, in modo da ottenere un risultato analogo al seguente:</span><span class="sxs-lookup"><span data-stu-id="1008e-115">Place parentheses around the first query, so that the end result looks like this:</span></span>  
  
    ```  
    SELECT product_id, supplier_id, product_name  
    FROM products  
    WHERE supplier_id IN  
       (SELECT supplier_id  
      FROM supplier  
      WHERE (country = 'Sweden'))  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="1008e-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1008e-116">See Also</span></span>  
 <span data-ttu-id="1008e-117">[Tipi di query supportati &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="1008e-117">[Supported Query Types &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 [<span data-ttu-id="1008e-118">Specifica dei criteri di ricerca &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="1008e-118">Specify Search Criteria &#40;Visual Database Tools&#41;</span></span>](specify-search-criteria-visual-database-tools.md)  
  
  
