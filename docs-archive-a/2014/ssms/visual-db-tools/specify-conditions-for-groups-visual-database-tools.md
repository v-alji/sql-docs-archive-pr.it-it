---
title: Specificare le condizioni per i gruppi (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- HAVING clause, query groups
- group query conditions [SQL Server]
ms.assetid: 269ad9c5-3261-4526-badf-7be3c869f229
author: stevestein
ms.author: sstein
ms.openlocfilehash: da9bc1b70fbfae8bf2a68a3a3ba332020020f310
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622980"
---
# <a name="specify-conditions-for-groups-visual-database-tools"></a><span data-ttu-id="c3308-102">Definizione di condizioni per i gruppi (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="c3308-102">Specify Conditions for Groups (Visual Database Tools)</span></span>
  <span data-ttu-id="c3308-103">Per limitare i gruppi inclusi in una query, è possibile specificare una condizione che si applica a tutti i gruppi, ossia una clausola HAVING.</span><span class="sxs-lookup"><span data-stu-id="c3308-103">You can limit the groups that appear in a query by specifying a condition that applies to groups as a whole - a HAVING clause.</span></span> <span data-ttu-id="c3308-104">Dopo il raggruppamento e l'aggregazione dei dati, vengono applicate le condizioni nella clausola HAVING.</span><span class="sxs-lookup"><span data-stu-id="c3308-104">After the data has been grouped and aggregated, the conditions in the HAVING clause are applied.</span></span> <span data-ttu-id="c3308-105">Nella query verranno inseriti solo i gruppi che soddisfano le condizioni.</span><span class="sxs-lookup"><span data-stu-id="c3308-105">Only the groups that meet the conditions appear in the query.</span></span>  
  
 <span data-ttu-id="c3308-106">Può ad esempio essere necessario visualizzare il prezzo medio di tutti i libri di ciascun editore nella tabella `titles` , ma solo se il prezzo medio è maggiore di 10 dollari.</span><span class="sxs-lookup"><span data-stu-id="c3308-106">For example, you might want to see the average price of all books for each publisher in a `titles` table, but only if the average price exceeds $10.00.</span></span> <span data-ttu-id="c3308-107">In questo caso, è possibile specificare una clausola HAVING con una condizione quale `AVG(price) > 10`.</span><span class="sxs-lookup"><span data-stu-id="c3308-107">In that case, you could specify a HAVING clause with a condition such as `AVG(price) > 10`.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c3308-108">In alcuni casi, può essere necessario escludere singole righe dai gruppi prima di applicare una condizione a tutti i gruppi.</span><span class="sxs-lookup"><span data-stu-id="c3308-108">In some instances, you might want to exclude individual rows from groups before applying a condition to groups as a whole.</span></span> <span data-ttu-id="c3308-109">Per informazioni dettagliate, vedere [Utilizzo delle clausole HAVING e WHERE nella stessa query &#40;Visual Database Tools&#41;](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c3308-109">For details, see [Use HAVING and WHERE Clauses in the Same Query &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="c3308-110">È possibile creare condizioni complesse per una clausola HAVING utilizzando AND e OR per collegare le condizioni.</span><span class="sxs-lookup"><span data-stu-id="c3308-110">You can create complex conditions for a HAVING clause by using AND and OR to link conditions.</span></span> <span data-ttu-id="c3308-111">Per informazioni dettagliate sull'uso di AND e OR nelle condizioni di ricerca, vedere [Definizione di più condizioni di ricerca per una sola colonna & #40;Visual Database Tools&#41;](specify-multiple-search-conditions-for-one-column-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c3308-111">For details about using AND and OR in search conditions, see [Specify Multiple Search Conditions for One Column &#40;Visual Database Tools&#41;](specify-multiple-search-conditions-for-one-column-visual-database-tools.md).</span></span>  
  
### <a name="to-specify-a-condition-for-a-group"></a><span data-ttu-id="c3308-112">Per specificare una condizione per un gruppo</span><span class="sxs-lookup"><span data-stu-id="c3308-112">To specify a condition for a group</span></span>  
  
1.  <span data-ttu-id="c3308-113">Specificare i gruppi per la query.</span><span class="sxs-lookup"><span data-stu-id="c3308-113">Specify the groups for your query.</span></span> <span data-ttu-id="c3308-114">Per informazioni dettagliate, vedere [Raggruppare righe nei risultati di una query &#40;Visual Database Tools&#41;](group-rows-in-query-results-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c3308-114">For details, see [Group Rows in Query Results &#40;Visual Database Tools&#41;](group-rows-in-query-results-visual-database-tools.md).</span></span>  
  
2.  <span data-ttu-id="c3308-115">Se necessario, aggiungere nel [riquadro Criteri](criteria-pane-visual-database-tools.md) la colonna su cui si vuole basare la condizione.</span><span class="sxs-lookup"><span data-stu-id="c3308-115">If it is not already in the [Criteria pane](criteria-pane-visual-database-tools.md), add the column on which you want to base the condition.</span></span> <span data-ttu-id="c3308-116">In genere la condizione riguarda una colonna che fa già parte di un gruppo o di un riepilogo. Non è possibile utilizzare una colonna che non fa parte di una funzione di aggregazione o della clausola GROUP BY.</span><span class="sxs-lookup"><span data-stu-id="c3308-116">(Most often the condition involves a column that is already a group or summary column.) You cannot use a column that is not part of an aggregate function or of the GROUP BY clause.</span></span>  
  
3.  <span data-ttu-id="c3308-117">Nella colonna **Filtro** specificare la condizione da applicare al gruppo.</span><span class="sxs-lookup"><span data-stu-id="c3308-117">In the **Filter** column, specify the condition to apply to the group.</span></span>  
  
     <span data-ttu-id="c3308-118">In [Progettazione query e Progettazione viste](query-and-view-designer-tools-visual-database-tools.md) verrà creata automaticamente una clausola HAVING nell'istruzione del [riquadro SQL](sql-pane-visual-database-tools.md), come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="c3308-118">The [Query and View Designer](query-and-view-designer-tools-visual-database-tools.md) automatically creates a HAVING clause in the statement in the [SQL pane](sql-pane-visual-database-tools.md), such as in the following example:</span></span>  
  
    ```  
    SELECT pub_id, AVG(price)  
    FROM titles  
    GROUP BY pub_id  
    HAVING (AVG(price) > 10)  
  
    ```  
  
4.  <span data-ttu-id="c3308-119">Ripetere i passaggi 2 e 3 per tutte le altre condizioni da specificare.</span><span class="sxs-lookup"><span data-stu-id="c3308-119">Repeat steps 2 and 3 for each additional condition you want to specify.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3308-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c3308-120">See Also</span></span>  
 [<span data-ttu-id="c3308-121">Ordinare e raggruppare i risultati delle query &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="c3308-121">Sort and Group Query Results &#40;Visual Database Tools&#41;</span></span>](sort-and-group-query-results-visual-database-tools.md)  
  
  
