---
title: Creare query di eliminazione (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- row removal [SQL Server], Delete query
- Delete query
- queries [SQL Server], types
- removing rows
- removing data
- data deletions [SQL Server]
- deleting rows
- deleting data
ms.assetid: 0db3af43-1ec4-48c8-b769-2bb9c76d3434
author: stevestein
ms.author: sstein
ms.openlocfilehash: a76c3aaef623365e419f40f3058308f6217d75d4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637538"
---
# <a name="create-delete-queries-visual-database-tools"></a><span data-ttu-id="72b47-102">Creazione di query (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="72b47-102">Create Delete Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="72b47-103">Per eliminare tutte le righe di una tabella, è possibile utilizzare una query di eliminazione.</span><span class="sxs-lookup"><span data-stu-id="72b47-103">You can delete all rows in a table by using a Delete query.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="72b47-104">Se si eliminano tutte le righe di una tabella, non verrà eliminata la tabella, ma solo i dati in essa contenuti.</span><span class="sxs-lookup"><span data-stu-id="72b47-104">Deleting all rows from a table clears the data in the table but does not delete the table itself.</span></span> <span data-ttu-id="72b47-105">Per eliminare una tabella da un database, fare clic su di essa con il pulsante destro del mouse in Esplora oggetti, quindi scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="72b47-105">To delete a table from a database, right-click the table in Object Explorer and click **Delete**.</span></span>  
  
 <span data-ttu-id="72b47-106">Quando si crea una query di eliminazione, nel riquadro Criteri vengono visualizzate le opzioni disponibili per l'eliminazione delle righe.</span><span class="sxs-lookup"><span data-stu-id="72b47-106">When you create a Delete query, the Criteria pane changes to reflect the options available for deleting rows.</span></span> <span data-ttu-id="72b47-107">Poiché la query di eliminazione non consente la visualizzazione di dati, vengono eliminate le colonne Output, Ordina per e Ordinamento.</span><span class="sxs-lookup"><span data-stu-id="72b47-107">Because you do not display data in a Delete query, the Output, Sort By, and Sort Order columns are removed.</span></span> <span data-ttu-id="72b47-108">Vengono inoltre rimosse le caselle di controllo accanto ai nomi di colonna nel rettangolo che rappresenta la tabella o l'oggetto con valori di tabella, in quanto non è possibile specificare singole colonne da eliminare.</span><span class="sxs-lookup"><span data-stu-id="72b47-108">In addition, the check boxes next to the column names in the rectangle representing the table or table-valued object are removed because you cannot specify individual columns to delete.</span></span>  
  
 <span data-ttu-id="72b47-109">Se in Progettazione query e Progettazione viste non è possibile eliminare una o più righe, non ne verrà eliminata alcuna e un messaggio indicherà in quali righe sono contenute informazioni che non possono essere eliminate dal database.</span><span class="sxs-lookup"><span data-stu-id="72b47-109">If the Query and View Designer can't delete one or more of the rows none of them will be deleted and you will receive a message telling you which row(s) contain information that can't be deleted from the database.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="72b47-110">Una volta eseguita, la query di eliminazione non potrà essere annullata.</span><span class="sxs-lookup"><span data-stu-id="72b47-110">You cannot undo the action of executing a Delete query.</span></span> <span data-ttu-id="72b47-111">È dunque opportuno eseguire una copia di backup dei dati prima di eseguire la query di eliminazione.</span><span class="sxs-lookup"><span data-stu-id="72b47-111">As a precaution, back up your data before executing a Delete query.</span></span>  
  
### <a name="to-create-a-delete-query"></a><span data-ttu-id="72b47-112">Per creare una query di eliminazione</span><span class="sxs-lookup"><span data-stu-id="72b47-112">To create a Delete query</span></span>  
  
1.  <span data-ttu-id="72b47-113">Aggiungere al riquadro Diagramma la tabella da cui eliminare le righe.</span><span class="sxs-lookup"><span data-stu-id="72b47-113">Add the table to delete rows from to the Diagram pane.</span></span>  
  
2.  <span data-ttu-id="72b47-114">Scegliere **Modifica tipo** dal menu **Progettazione query**, quindi **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="72b47-114">From the **Query Designer** menu, point to **Change Type**, and then click **Delete**.</span></span> <span data-ttu-id="72b47-115">**Nota** Se nel riquadro Diagramma sono visualizzate più tabelle quando si inizia a creare la query di eliminazione, in Progettazione query e Progettazione viste verrà visualizzata la finestra di dialogo [Elimina tabella](visual-database-tools.md) , in cui è necessario specificare il nome della tabella contenente le righe da eliminare.</span><span class="sxs-lookup"><span data-stu-id="72b47-115">**Note** If more than one table is displayed in the Diagram pane when you start the Delete query, the Query and View Designer displays the [Delete Table Dialog Box](visual-database-tools.md) to prompt you for the name of the table to delete rows from.</span></span>  
  
 <span data-ttu-id="72b47-116">Quando si esegue una query di eliminazione, non viene restituito alcun risultato nel [riquadro Risultati](results-pane-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="72b47-116">When you execute the Delete query, no results are reported in the [Results Pane](results-pane-visual-database-tools.md).</span></span> <span data-ttu-id="72b47-117">Viene invece visualizzato un messaggio che indica il numero di righe eliminate.</span><span class="sxs-lookup"><span data-stu-id="72b47-117">Instead, a message appears indicating how many rows were deleted.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72b47-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="72b47-118">See Also</span></span>  
 <span data-ttu-id="72b47-119">[Tipi di query supportati &#40;Visual Database Tools&#41;](supported-query-types-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="72b47-119">[Supported Query Types &#40;Visual Database Tools&#41;](supported-query-types-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="72b47-120">Procedure per la progettazione di query e viste &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="72b47-120">Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;</span></span>](design-queries-and-views-how-to-topics-visual-database-tools.md)  
  
  
