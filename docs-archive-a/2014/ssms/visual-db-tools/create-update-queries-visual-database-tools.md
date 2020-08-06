---
title: Creare query di aggiornamento (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- tables [SQL Server], updating
- queries [SQL Server], types
- Update query
- updating tables
ms.assetid: 178b7b75-8078-4e61-b2a8-4719b9d8033d
author: stevestein
ms.author: sstein
ms.openlocfilehash: bbea575d544875dba73de923474cc11bbcb46a9b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629695"
---
# <a name="create-update-queries-visual-database-tools"></a><span data-ttu-id="7010f-102">Creazione di query di aggiornamento (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="7010f-102">Create Update Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="7010f-103">Per modificare il contenuto di più righe contemporaneamente, è possibile utilizzare una query di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="7010f-103">You can change the contents of multiple rows in one operation by using an Update query.</span></span> <span data-ttu-id="7010f-104">Ad esempio, in una tabella `titles` è possibile utilizzare una query di aggiornamento per aumentare del 10% il prezzo di tutti i libri di un determinato editore.</span><span class="sxs-lookup"><span data-stu-id="7010f-104">For example, in a `titles` table you can use an Update query to add 10% to the price of all books for a particular publisher.</span></span>  
  
 <span data-ttu-id="7010f-105">Durante la creazione di una query di aggiornamento è necessario specificare:</span><span class="sxs-lookup"><span data-stu-id="7010f-105">When you create an Update query, you specify:</span></span>  
  
-   <span data-ttu-id="7010f-106">la tabella da aggiornare;</span><span class="sxs-lookup"><span data-stu-id="7010f-106">The table to update.</span></span>  
  
-   <span data-ttu-id="7010f-107">le colonne di cui si desidera aggiornare il contenuto;</span><span class="sxs-lookup"><span data-stu-id="7010f-107">The columns whose contents you want to update.</span></span>  
  
-   <span data-ttu-id="7010f-108">il valore o l'espressione da utilizzare per aggiornare le singole colonne;</span><span class="sxs-lookup"><span data-stu-id="7010f-108">The value or expression to use to update the individual columns.</span></span>  
  
-   <span data-ttu-id="7010f-109">le condizioni di ricerca per la definizione delle righe da aggiornare.</span><span class="sxs-lookup"><span data-stu-id="7010f-109">Search conditions to define the rows you want to update.</span></span>  
  
 <span data-ttu-id="7010f-110">Ad esempio, nella seguente query la tabella `titles` viene aggiornata aggiungendo il 10% al prezzo di tutti i titoli di un editore:</span><span class="sxs-lookup"><span data-stu-id="7010f-110">For example, the following query updates the `titles` table by adding 10% to the price of all titles for one publisher:</span></span>  
  
```  
UPDATE titles  
SET price = price * 1.1  
WHERE (pub_id = '0766')  
```  
  
> [!CAUTION]  
>  <span data-ttu-id="7010f-111">Una volta eseguita, la query di aggiornamento non potrà essere annullata.</span><span class="sxs-lookup"><span data-stu-id="7010f-111">You cannot undo the action of executing an Update query.</span></span> <span data-ttu-id="7010f-112">È dunque opportuno eseguire una copia di backup dei dati prima di eseguire la query.</span><span class="sxs-lookup"><span data-stu-id="7010f-112">As a precaution, back up your data before executing the query.</span></span>  
  
### <a name="to-create-an-update-query"></a><span data-ttu-id="7010f-113">Per creare una query di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="7010f-113">To create an Update query</span></span>  
  
1.  <span data-ttu-id="7010f-114">Aggiungere al riquadro Diagramma la tabella da aggiornare.</span><span class="sxs-lookup"><span data-stu-id="7010f-114">Add the table you want to update to the Diagram pane.</span></span>  
  
2.  <span data-ttu-id="7010f-115">Scegliere **Modifica tipo** dal menu **Progettazione query**e quindi **Aggiorna**.</span><span class="sxs-lookup"><span data-stu-id="7010f-115">From the **Query Designer** menu point to **Change Type**, and then click **Update**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7010f-116">Se nel riquadro Diagramma è visualizzata più di una tabella quando si avvia la query di aggiornamento, in Progettazione query e Progettazione viste verrà visualizzata la [finestra di dialogo Scegliere la tabella di destinazione per Accodamento valori](visual-database-tools.md) , in cui sarà possibile specificare il nome della tabella da aggiornare.</span><span class="sxs-lookup"><span data-stu-id="7010f-116">If more than one table is displayed in the Diagram pane when you start the Update query, the Query and View Designer displays the [Choose Target Table for Insert Values Dialog Box](visual-database-tools.md) to prompt you for the name of the table to update.</span></span>  
  
3.  <span data-ttu-id="7010f-117">Nel riquadro Diagramma selezionare le caselle di controllo relative alle colonne per cui si desidera specificare nuovi valori.</span><span class="sxs-lookup"><span data-stu-id="7010f-117">In the Diagram pane, click the check box for each column for which you want to supply new values.</span></span> <span data-ttu-id="7010f-118">Queste colonne verranno visualizzate nel riquadro Criteri.</span><span class="sxs-lookup"><span data-stu-id="7010f-118">Those columns will show in the Criteria pane.</span></span> <span data-ttu-id="7010f-119">Verranno aggiornate solo le colonne aggiunte alla query.</span><span class="sxs-lookup"><span data-stu-id="7010f-119">Columns will be updated only if you add them to the query.</span></span>  
  
4.  <span data-ttu-id="7010f-120">Nella colonna **Nuovo valore** del riquadro Criteri immettere il valore aggiornato per la colonna.</span><span class="sxs-lookup"><span data-stu-id="7010f-120">In the **New Value** column of the Criteria pane, enter the update value for the column.</span></span> <span data-ttu-id="7010f-121">È possibile immettere valori letterali, nomi di colonna o espressioni.</span><span class="sxs-lookup"><span data-stu-id="7010f-121">You can enter literal values, column names, or expressions.</span></span> <span data-ttu-id="7010f-122">Il valore deve corrispondere o essere compatibile con il tipo di dati della colonna da aggiornare.</span><span class="sxs-lookup"><span data-stu-id="7010f-122">The value must match (or be compatible with) the data type of the column you are updating.</span></span>  
  
    > [!CAUTION]  
    >  <span data-ttu-id="7010f-123">In Progettazione query e Progettazione viste non è possibile verificare la compatibilità di un valore rispetto alla lunghezza della colonna da aggiornare.</span><span class="sxs-lookup"><span data-stu-id="7010f-123">The Query and View Designer cannot check that a value fits within the length of the column you are updating.</span></span> <span data-ttu-id="7010f-124">Se il valore inserito è troppo lungo, è possibile che venga troncato senza preavviso.</span><span class="sxs-lookup"><span data-stu-id="7010f-124">If you provide a value that is too long, it might be truncated without warning.</span></span> <span data-ttu-id="7010f-125">Ad esempio, se una colonna `name` è lunga 20 caratteri ma si specifica un valore di aggiornamento di 25 caratteri, è possibile che gli ultimi 5 caratteri vengano troncati.</span><span class="sxs-lookup"><span data-stu-id="7010f-125">For example, if a `name` column is 20 characters long but you specify an update value of 25 characters, the last 5 characters might be truncated.</span></span>  
  
5.  <span data-ttu-id="7010f-126">Definire le righe da aggiornare immettendo le condizioni di ricerca nella colonna **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="7010f-126">Define the rows to update by entering search conditions in the **Filter** column.</span></span> <span data-ttu-id="7010f-127">Per informazioni dettagliate, vedere [Specifica di criteri di ricerca &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="7010f-127">For details, see [Specify Search Criteria &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md).</span></span>  
  
     <span data-ttu-id="7010f-128">Se non si specifica alcuna condizione di ricerca, verranno aggiornate tutte le righe della tabella specificata.</span><span class="sxs-lookup"><span data-stu-id="7010f-128">If you do not specify a search condition, all rows in the specified table will be updated.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7010f-129">Quando si aggiunge al riquadro Criteri una colonna da utilizzare in una condizione di ricerca, in Progettazione query e Progettazione viste la colonna verrà aggiunta anche all'elenco delle colonne da aggiornare.</span><span class="sxs-lookup"><span data-stu-id="7010f-129">When you add a column to the Criteria pane for use in a search condition, the Query and View Designer also adds it to the list of columns to be updated.</span></span> <span data-ttu-id="7010f-130">Se si desidera utilizzare una colonna per una condizione di ricerca senza aggiornarla, deselezionare la casella di controllo accanto al nome della colonna nel rettangolo che rappresenta la tabella o l'oggetto con valori di tabella.</span><span class="sxs-lookup"><span data-stu-id="7010f-130">If you want to use a column for a search condition but not update it, clear the check box next to the column name in the rectangle representing the table or table-valued object.</span></span>  
  
 <span data-ttu-id="7010f-131">Quando si esegue una query di aggiornamento, non viene restituito alcun risultato nel [riquadro Risultati](results-pane-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="7010f-131">When you execute an Update query, no results are reported in the [Results Pane](results-pane-visual-database-tools.md).</span></span> <span data-ttu-id="7010f-132">Viene invece visualizzato un messaggio che indica il numero di righe modificate.</span><span class="sxs-lookup"><span data-stu-id="7010f-132">Instead, a message appears indicating how many rows were changed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7010f-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7010f-133">See Also</span></span>  
 <span data-ttu-id="7010f-134">[Tipi di query supportati &#40;Visual Database Tools&#41;](supported-query-types-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="7010f-134">[Supported Query Types &#40;Visual Database Tools&#41;](supported-query-types-visual-database-tools.md) </span></span>  
 <span data-ttu-id="7010f-135">[Procedure per la progettazione di query e viste &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="7010f-135">[Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="7010f-136">Eseguire operazioni di base con le query &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="7010f-136">Perform Basic Operations with Queries &#40;Visual Database Tools&#41;</span></span>](perform-basic-operations-with-queries-visual-database-tools.md)  
  
  
