---
title: Specificare le condizioni di ricerca (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- choosing search criteria
- search conditions [SQL Server], specifying
- search criteria [SQL Server], specifying conditions
ms.assetid: 18e2c759-68ec-4efe-b208-2f73418cd9bd
author: stevestein
ms.author: sstein
ms.openlocfilehash: aa5dab8326de079c385a3a508bc1b01b1ee1247d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628057"
---
# <a name="specify-search-conditions-visual-database-tools"></a><span data-ttu-id="4246b-102">Definizione di condizioni di ricerca (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="4246b-102">Specify Search Conditions (Visual Database Tools)</span></span>
  <span data-ttu-id="4246b-103">È possibile indicare le righe di dati da inserire nella query specificando delle condizioni di ricerca.</span><span class="sxs-lookup"><span data-stu-id="4246b-103">You can specify the data rows that appear in your query by specifying search conditions.</span></span> <span data-ttu-id="4246b-104">Se ad esempio si desidera eseguire una query su una tabella `employee` , è possibile limitare la ricerca ai soli dipendenti che lavorano in una particolare area.</span><span class="sxs-lookup"><span data-stu-id="4246b-104">For example, if you are querying an `employee` table, you can specify that you want to find only the employees who work in a particular region.</span></span>  
  
 <span data-ttu-id="4246b-105">Le condizioni di ricerca vanno specificate mediante un'espressione,</span><span class="sxs-lookup"><span data-stu-id="4246b-105">You specify search conditions using an expression.</span></span> <span data-ttu-id="4246b-106">che generalmente è costituita da un operatore e da un valore di ricerca.</span><span class="sxs-lookup"><span data-stu-id="4246b-106">Most commonly the expression consists of an operator and a search value.</span></span> <span data-ttu-id="4246b-107">Per trovare, ad esempio, un dipendente di una determinata area di vendita, è possibile specificare il seguente criterio di ricerca nella colonna `region` :</span><span class="sxs-lookup"><span data-stu-id="4246b-107">For example, to find employees in a particular sales region, you might specify the following search criterion for the `region` column:</span></span>  
  
```  
='UK'  
```  
  
> [!NOTE]  
>  <span data-ttu-id="4246b-108">Se si lavora su più tabelle, in Progettazione query e Progettazione viste verrà esaminata ciascuna condizione di ricerca per stabilire se il confronto avrà come risultato un join.</span><span class="sxs-lookup"><span data-stu-id="4246b-108">If you are working with multiple tables, the Query and View Designer examines each search condition to determine whether the comparison you are making results in a join.</span></span> <span data-ttu-id="4246b-109">In tal caso, la condizione di ricerca verrà convertita automaticamente in un join.</span><span class="sxs-lookup"><span data-stu-id="4246b-109">If so, the Query and View Designer automatically converts the search condition into a join.</span></span> <span data-ttu-id="4246b-110">Per altre informazioni, vedere [Unione di tabelle in modo automatico &#40;Visual Database Tools&#41;](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="4246b-110">For more information, see [Join Tables Automatically &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
### <a name="to-specify-search-conditions"></a><span data-ttu-id="4246b-111">Per specificare le condizioni di ricerca</span><span class="sxs-lookup"><span data-stu-id="4246b-111">To specify search conditions</span></span>  
  
1.  <span data-ttu-id="4246b-112">Se necessario, aggiungere nel riquadro Criteri le colonne o le espressioni da utilizzare nella condizione di ricerca.</span><span class="sxs-lookup"><span data-stu-id="4246b-112">If you have not done so already, add the columns or expressions that you want to use within your search condition to the Criteria pane.</span></span>  
  
     <span data-ttu-id="4246b-113">Se si sta creando una query di selezione e si preferisce che le colonne o le espressioni di ricerca non siano visualizzate nell'output della query, deselezionare la colonna **Output** per tutte le colonne o espressioni da rimuovere dall'output.</span><span class="sxs-lookup"><span data-stu-id="4246b-113">If you are creating a Select query and do not want the search columns or expressions to appear in the query output, clear the **Output** column for each search column or expression to remove them as output columns.</span></span>  
  
2.  <span data-ttu-id="4246b-114">Individuare la riga contenente la colonna di dati o l'espressione da includere nella ricerca e immettere una condizione di ricerca nella colonna **Filtro** .</span><span class="sxs-lookup"><span data-stu-id="4246b-114">Locate the row containing the data column or expression to search, and then in the **Filter** column, enter a search condition.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4246b-115">Se non si specifica un operatore, in Progettazione query e Progettazione viste verrà inserito automaticamente l'operatore di uguaglianza "=".</span><span class="sxs-lookup"><span data-stu-id="4246b-115">If you do not enter an operator, the Query and View Designer automatically inserts the equality operator "=".</span></span>  
  
 <span data-ttu-id="4246b-116">In Progettazione query e Progettazione viste l'istruzione SQL verrà aggiornata nel [riquadro SQL](sql-pane-visual-database-tools.md) tramite l’aggiunta o la modifica della clausola WHERE.</span><span class="sxs-lookup"><span data-stu-id="4246b-116">The Query and View Designer updates the SQL statement in the [SQL Pane](sql-pane-visual-database-tools.md) by adding or modifying the WHERE clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4246b-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4246b-117">See Also</span></span>  
 <span data-ttu-id="4246b-118">[Regole per l'immissione di valori di ricerca &#40;Visual Database Tools&#41;](rules-for-entering-search-values-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="4246b-118">[Rules for Entering Search Values &#40;Visual Database Tools&#41;](rules-for-entering-search-values-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="4246b-119">Specifica dei criteri di ricerca &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="4246b-119">Specify Search Criteria &#40;Visual Database Tools&#41;</span></span>](specify-search-criteria-visual-database-tools.md)  
  
  
