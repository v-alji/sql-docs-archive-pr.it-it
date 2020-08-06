---
title: Creare query di accodamento (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- queries [SQL Server], types
- result sets [SQL Server], queries
- results [SQL Server], query
- Insert Results query
- queries [SQL Server], results
ms.assetid: 8770d630-09cc-47ec-a0e9-e9de2d7bbc89
author: stevestein
ms.author: sstein
ms.openlocfilehash: 02643c2cf3295debe740a696941f8730d4417254
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714967"
---
# <a name="create-insert-results-queries-visual-database-tools"></a><span data-ttu-id="2ec0c-102">Creazione di query di accodamento (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="2ec0c-102">Create Insert Results Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="2ec0c-103">Le query di accodamento consentono di copiare righe da una tabella a un'altra oppure all'interno di una stessa tabella.</span><span class="sxs-lookup"><span data-stu-id="2ec0c-103">You can copy rows from one table to another or within a table using an Insert Results query.</span></span> <span data-ttu-id="2ec0c-104">Ad esempio, in una tabella `titles` è possibile utilizzare una query di accodamento per copiare le informazioni riguardanti tutti i titoli di un editore in una seconda tabella da presentare all'editore stesso.</span><span class="sxs-lookup"><span data-stu-id="2ec0c-104">For example, in a `titles` table, you can use an Insert Results query to copy information about all the titles for one publisher to a second table that you can make available to that publisher.</span></span> <span data-ttu-id="2ec0c-105">La query di accodamento è analoga alla query di creazione tabella, con la differenza che le righe vengono copiate in una tabella esistente.</span><span class="sxs-lookup"><span data-stu-id="2ec0c-105">An Insert Results query is similar to Make Table Queries, but copies rows into an existing table.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="2ec0c-106">Per copiare righe da una tabella a un'altra, è anche possibile utilizzare i comandi Copia e Incolla.</span><span class="sxs-lookup"><span data-stu-id="2ec0c-106">You can also copy rows from one table to another using cut and paste.</span></span> <span data-ttu-id="2ec0c-107">Creare una query per ogni tabella ed eseguire le query,</span><span class="sxs-lookup"><span data-stu-id="2ec0c-107">Create a query for each table and run the queries.</span></span> <span data-ttu-id="2ec0c-108">quindi copiare le righe desiderate da una griglia di risultati all'altra.</span><span class="sxs-lookup"><span data-stu-id="2ec0c-108">Copy the rows you want from one results grid to the other.</span></span>  
  
 <span data-ttu-id="2ec0c-109">Durante la creazione di una query di accodamento è necessario specificare:</span><span class="sxs-lookup"><span data-stu-id="2ec0c-109">When you create an Insert Results query, you specify:</span></span>  
  
-   <span data-ttu-id="2ec0c-110">La tabella di database in cui copiare le righe, ossia la tabella di destinazione.</span><span class="sxs-lookup"><span data-stu-id="2ec0c-110">The database table to copy rows to (the destination table).</span></span>  
  
-   <span data-ttu-id="2ec0c-111">Le tabelle da cui copiare le righe, ossia le tabelle di origine.</span><span class="sxs-lookup"><span data-stu-id="2ec0c-111">The table or tables to copy rows from (the source table).</span></span> <span data-ttu-id="2ec0c-112">Le tabelle di origine entrano a far parte di una sottoquery.</span><span class="sxs-lookup"><span data-stu-id="2ec0c-112">The source table or tables become part of a subquery.</span></span> <span data-ttu-id="2ec0c-113">Se la copia viene effettuata all'interno della stessa tabella, la tabella di origine e quella di destinazione coincideranno.</span><span class="sxs-lookup"><span data-stu-id="2ec0c-113">If you are copying within a table, the source table is the same as the destination table.</span></span>  
  
-   <span data-ttu-id="2ec0c-114">Le colonne della tabella di origine di cui si desidera copiare il contenuto.</span><span class="sxs-lookup"><span data-stu-id="2ec0c-114">The columns in the source table whose contents you want to copy.</span></span>  
  
-   <span data-ttu-id="2ec0c-115">Le colonne della tabella di destinazione in cui si desidera copiare i dati.</span><span class="sxs-lookup"><span data-stu-id="2ec0c-115">The target columns in the destination table to copy the data to.</span></span>  
  
-   <span data-ttu-id="2ec0c-116">Le condizioni di ricerca per la definizione delle righe da copiare.</span><span class="sxs-lookup"><span data-stu-id="2ec0c-116">Search conditions to define the rows you want to copy.</span></span>  
  
-   <span data-ttu-id="2ec0c-117">Il criterio di ordinamento, se si desidera copiare le righe in un particolare ordine.</span><span class="sxs-lookup"><span data-stu-id="2ec0c-117">Sort order, if you want to copy the rows in a particular order.</span></span>  
  
-   <span data-ttu-id="2ec0c-118">Le opzioni di raggruppamento, se si desidera copiare solo le informazioni di riepilogo.</span><span class="sxs-lookup"><span data-stu-id="2ec0c-118">Group By options, if you want to copy only summary information.</span></span>  
  
 <span data-ttu-id="2ec0c-119">L'esempio di query fornito di seguito consente di copiare le informazioni sui titoli dalla tabella `titles` a una tabella di archivio denominata `archivetitles`:</span><span class="sxs-lookup"><span data-stu-id="2ec0c-119">For example, the following query copies title information from the `titles` table to an archive table called `archivetitles`.</span></span> <span data-ttu-id="2ec0c-120">La query copia il contenuto di quattro colonne per tutti i titoli appartenenti all'editore specificato:</span><span class="sxs-lookup"><span data-stu-id="2ec0c-120">The query copies the contents of four columns for all titles belonging to a particular publisher:</span></span>  
  
```  
INSERT INTO archivetitles   
   (title_id, title, type, pub_id)  
SELECT title_id, title, type, pub_id  
FROM titles  
WHERE (pub_id = '0766')  
```  
  
> [!NOTE]  
>  <span data-ttu-id="2ec0c-121">Per inserire i valori in una nuova riga, utilizzare una query di accodamento valori.</span><span class="sxs-lookup"><span data-stu-id="2ec0c-121">To insert values into a new row, use an Insert Values query.</span></span>  
  
 <span data-ttu-id="2ec0c-122">È possibile copiare il contenuto delle colonne selezionate o di tutte le colonne in una riga.</span><span class="sxs-lookup"><span data-stu-id="2ec0c-122">You can copy the contents of selected columns or of all columns in a row.</span></span> <span data-ttu-id="2ec0c-123">In entrambi i casi, è necessario che i dati copiati siano compatibili con le colonne delle righe di destinazione.</span><span class="sxs-lookup"><span data-stu-id="2ec0c-123">In either case, the data you are copying must be compatible with the columns in the rows you are copying to.</span></span> <span data-ttu-id="2ec0c-124">Ad esempio, per copiare il contenuto di una colonna quale `price`, è necessario che la colonna di destinazione consenta l'inserimento di dati numerici con decimali.</span><span class="sxs-lookup"><span data-stu-id="2ec0c-124">For example, if you copy the contents of a column such as `price`, the column in the row you are copying to must accept numeric data with decimal places.</span></span> <span data-ttu-id="2ec0c-125">Se si copia una riga intera, è necessario che la tabella di destinazione disponga di colonne compatibili nella stessa posizione fisica rispetto alla colonna di origine.</span><span class="sxs-lookup"><span data-stu-id="2ec0c-125">If you are copying an entire row, the destination table must have compatible columns in the same physical position as the source table.</span></span>  
  
 <span data-ttu-id="2ec0c-126">Quando si crea una query di accodamento, nel riquadro Criteri vengono visualizzate le opzioni disponibili per la copia di dati.</span><span class="sxs-lookup"><span data-stu-id="2ec0c-126">When you create an Insert Results query, the Criteria pane changes to reflect options available for copying data.</span></span> <span data-ttu-id="2ec0c-127">Verrà inoltre aggiunta una colonna Accodamento dove specificare le colonne in cui copiare i dati.</span><span class="sxs-lookup"><span data-stu-id="2ec0c-127">An Append column is added to allow you to specify the columns into which data should be copied.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="2ec0c-128">Una volta eseguita, la query di accodamento non potrà essere annullata.</span><span class="sxs-lookup"><span data-stu-id="2ec0c-128">You cannot undo the action of executing an Insert Results query.</span></span> <span data-ttu-id="2ec0c-129">È dunque opportuno eseguire una copia di backup dei dati prima di eseguire la query.</span><span class="sxs-lookup"><span data-stu-id="2ec0c-129">As a precaution, back up your data before executing the query.</span></span>  
  
### <a name="to-create-an-insert-results-query"></a><span data-ttu-id="2ec0c-130">Per creare una query di accodamento</span><span class="sxs-lookup"><span data-stu-id="2ec0c-130">To create an Insert Results query</span></span>  
  
1.  <span data-ttu-id="2ec0c-131">Creare una nuova query e aggiungere la tabella da cui si desidera copiare le righe, ovvero la tabella di origine.</span><span class="sxs-lookup"><span data-stu-id="2ec0c-131">Create a new query and add the table from which you want to copy rows (the source table).</span></span> <span data-ttu-id="2ec0c-132">Se si sta effettuando la copia di righe all'interno di una stessa tabella, sarà possibile aggiungere la tabella di origine come tabella di destinazione.</span><span class="sxs-lookup"><span data-stu-id="2ec0c-132">If you are copying rows within a table, you can add the source table as a destination table.</span></span>  
  
2.  <span data-ttu-id="2ec0c-133">Scegliere **Modifica tipo** dal menu **Progettazione query**, quindi **Accodamento**.</span><span class="sxs-lookup"><span data-stu-id="2ec0c-133">From the **Query Designer** menu, point to **Change Type**, and then click **Insert Results**.</span></span>  
  
3.  <span data-ttu-id="2ec0c-134">Nella [finestra di dialogo Scegliere la tabella di destinazione per Accodamento](visual-database-tools.md)selezionare la tabella in cui copiare le righe (la tabella di destinazione).</span><span class="sxs-lookup"><span data-stu-id="2ec0c-134">In the [Choose Target Table for Insert Results Dialog Box](visual-database-tools.md), select the table to copy rows to (the destination table).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2ec0c-135">In Progettazione query e Progettazione viste non è possibile stabilire in anticipo le tabelle e le viste da aggiornare.</span><span class="sxs-lookup"><span data-stu-id="2ec0c-135">The Query and View Designer cannot determine in advance which tables and views you can update.</span></span> <span data-ttu-id="2ec0c-136">Pertanto nell'elenco **Nome tabella** della finestra di dialogo **Choose Table for Insert From Query** (Scegli tabella per query di inserimento) sono visualizzate tutte le tabelle e le viste disponibili nella connessione dati su cui si esegue la query, anche quelle che non sono valide come tabelle o viste di destinazione.</span><span class="sxs-lookup"><span data-stu-id="2ec0c-136">Therefore, the **Table Name** list in the **Choose Table for Insert From Query** dialog box shows all available tables and views in the data connection you are querying, even those that you might not be able to copy rows to.</span></span>  
  
4.  <span data-ttu-id="2ec0c-137">Nel rettangolo che rappresenta la tabella o l'oggetto con valori di tabella scegliere i nomi delle colonne di cui si desidera copiare il contenuto.</span><span class="sxs-lookup"><span data-stu-id="2ec0c-137">In the rectangle representing the table or table-valued object, choose the names of the columns whose contents you want to copy.</span></span> <span data-ttu-id="2ec0c-138">Per copiare intere righe, scegliere \*\* \* (tutte le colonne)\*\*.</span><span class="sxs-lookup"><span data-stu-id="2ec0c-138">To copy entire rows, choose **\* (All Columns)**.</span></span>  
  
     <span data-ttu-id="2ec0c-139">Le colonne selezionate verranno aggiunte alla colonna **Colonna** del riquadro Criteri.</span><span class="sxs-lookup"><span data-stu-id="2ec0c-139">The Query and View Designer adds the columns you choose to the **Column** column of the Criteriapane.</span></span>  
  
5.  <span data-ttu-id="2ec0c-140">Nella colonna **Aggiungi** del riquadro Criteri selezionare una colonna di destinazione nella tabella di destinazione per ogni colonna da copiare.</span><span class="sxs-lookup"><span data-stu-id="2ec0c-140">In the **Append** column of the Criteria pane, select a target column in the destination table for each column you are copying.</span></span> <span data-ttu-id="2ec0c-141">Scegliere \*TableName. \* \* se si stanno copiando intere righe.</span><span class="sxs-lookup"><span data-stu-id="2ec0c-141">Choose *tablename.\** if you are copying entire rows.</span></span> <span data-ttu-id="2ec0c-142">I tipi di dati nelle colonne della tabella di destinazione devono essere uguali o compatibili con quelli delle colonne nella tabella di origine.</span><span class="sxs-lookup"><span data-stu-id="2ec0c-142">The columns in the destination table must have the same (or compatible) data types as the columns in the source table.</span></span>  
  
6.  <span data-ttu-id="2ec0c-143">Se si desidera copiare le righe in un particolare ordine, specificare il criterio di ordinamento.</span><span class="sxs-lookup"><span data-stu-id="2ec0c-143">If you want to copy rows in a particular order, specify a sort order.</span></span> <span data-ttu-id="2ec0c-144">Per informazioni dettagliate, vedere [Ordinare e raggruppare i risultati delle query &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="2ec0c-144">For details, see [Sort and Group Query Results &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md).</span></span>  
  
7.  <span data-ttu-id="2ec0c-145">Specificare le righe da copiare immettendo le condizioni di ricerca nella colonna **Filtro** .</span><span class="sxs-lookup"><span data-stu-id="2ec0c-145">Specify the rows to copy by entering search conditions in the **Filter** column.</span></span> <span data-ttu-id="2ec0c-146">Per informazioni dettagliate, vedere [Specifica di criteri di ricerca &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="2ec0c-146">For details, see [Specify Search Criteria &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md).</span></span>  
  
     <span data-ttu-id="2ec0c-147">Se non si specifica alcuna condizione di ricerca, tutte le righe della tabella di origine verranno copiate nella tabella di destinazione.</span><span class="sxs-lookup"><span data-stu-id="2ec0c-147">If you do not specify a search condition, all rows from the source table will be copied to the destination table.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2ec0c-148">Quando nel riquadro Criteri si aggiunge una colonna da includere nella ricerca, tale colonna verrà aggiunta anche all'elenco delle colonne da copiare.</span><span class="sxs-lookup"><span data-stu-id="2ec0c-148">When you add a column to search to the Criteria pane, the Query and View Designer also adds it to the list of columns to copy.</span></span> <span data-ttu-id="2ec0c-149">Se si desidera utilizzare una colonna per la ricerca senza copiarla, deselezionare la casella di controllo accanto al nome della colonna nel rettangolo che rappresenta la tabella o l'oggetto con valori di tabella.</span><span class="sxs-lookup"><span data-stu-id="2ec0c-149">If you want to use a column for searching but not copy it, clear the check box next to the column name in the rectangle representing the table or table-valued object.</span></span>  
  
8.  <span data-ttu-id="2ec0c-150">Se si desidera copiare le informazioni di riepilogo, specificare le opzioni di raggruppamento.</span><span class="sxs-lookup"><span data-stu-id="2ec0c-150">If you want to copy summary information, specify Group By options.</span></span> <span data-ttu-id="2ec0c-151">Per informazioni dettagliate, vedere [Riepilogo dei risultati di query &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="2ec0c-151">For details, see [Summarize Query Results &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="2ec0c-152">Quando si esegue una query di accodamento, non viene restituito alcun risultato nel [riquadro Risultati](results-pane-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="2ec0c-152">When you execute an Insert Results query, no results are reported in the [Results Pane](results-pane-visual-database-tools.md).</span></span> <span data-ttu-id="2ec0c-153">Viene invece visualizzato un messaggio che indica il numero di righe copiate.</span><span class="sxs-lookup"><span data-stu-id="2ec0c-153">Instead, a message appears indicating how many rows were copied.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ec0c-154">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2ec0c-154">See Also</span></span>  
 <span data-ttu-id="2ec0c-155">[Tipi di query &#40;Visual Database Tools&#41;](types-of-queries-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="2ec0c-155">[Types of Queries &#40;Visual Database Tools&#41;](types-of-queries-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="2ec0c-156">Procedure per la progettazione di query e viste &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="2ec0c-156">Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;</span></span>](design-queries-and-views-how-to-topics-visual-database-tools.md)  
  
  
