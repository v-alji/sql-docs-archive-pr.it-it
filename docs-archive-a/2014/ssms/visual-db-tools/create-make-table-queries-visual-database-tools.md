---
title: Creare query di creazione tabella (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- queries [SQL Server], types
- table creation [SQL Server], Make Table query
- inserting tables
- Make Table query
- adding tables
ms.assetid: 4493cffa-7b2d-4c24-8ef0-d49329198972
author: stevestein
ms.author: sstein
ms.openlocfilehash: 91c4a3bf45935053789d6e884b1af5b338b4c7c9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714964"
---
# <a name="create-make-table-queries-visual-database-tools"></a><span data-ttu-id="fc6df-102">Creazione di query di creazione tabella (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="fc6df-102">Create Make Table Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="fc6df-103">Per copiare delle righe in una nuova tabella è possibile utilizzare una query di creazione tabella, che consente di creare subset di dati da utilizzare o di copiare il contenuto di una tabella da un database a un altro.</span><span class="sxs-lookup"><span data-stu-id="fc6df-103">You can copy rows into a new table using a Make Table query, which is useful for creating subsets of data to work with or copying the contents of a table from one database to another.</span></span> <span data-ttu-id="fc6df-104">Una query di creazione tabella è analoga a una query di accodamento, con la differenza che viene creata una nuova tabella in cui copiare le righe.</span><span class="sxs-lookup"><span data-stu-id="fc6df-104">A Make Table query is similar to an Insert Results query but creates a new table to copy rows into.</span></span>  
  
 <span data-ttu-id="fc6df-105">Durante la creazione di una query di creazione tabella è necessario specificare:</span><span class="sxs-lookup"><span data-stu-id="fc6df-105">When you create a Make Table query, you specify:</span></span>  
  
-   <span data-ttu-id="fc6df-106">Il nome della nuova tabella di database, ossia la tabella di destinazione.</span><span class="sxs-lookup"><span data-stu-id="fc6df-106">The name of the new database table (the destination table).</span></span>  
  
-   <span data-ttu-id="fc6df-107">Le tabelle da cui copiare le righe, ossia le tabelle di origine.</span><span class="sxs-lookup"><span data-stu-id="fc6df-107">The table or tables to copy rows from (the source table).</span></span> <span data-ttu-id="fc6df-108">È possibile effettuare la copia da una singola tabella o da tabelle in join.</span><span class="sxs-lookup"><span data-stu-id="fc6df-108">You can copy from a single table or from joined tables.</span></span>  
  
-   <span data-ttu-id="fc6df-109">Le colonne della tabella di origine di cui si desidera copiare il contenuto.</span><span class="sxs-lookup"><span data-stu-id="fc6df-109">The columns in the source table whose contents you want to copy.</span></span>  
  
-   <span data-ttu-id="fc6df-110">Il criterio di ordinamento, se si desidera copiare le righe in un particolare ordine.</span><span class="sxs-lookup"><span data-stu-id="fc6df-110">Sort order, if you want to copy the rows in a particular order.</span></span>  
  
-   <span data-ttu-id="fc6df-111">Le condizioni di ricerca per la definizione delle righe da copiare.</span><span class="sxs-lookup"><span data-stu-id="fc6df-111">Search conditions to define the rows you want to copy.</span></span>  
  
-   <span data-ttu-id="fc6df-112">Le opzioni di raggruppamento, se si desidera copiare solo le informazioni di riepilogo.</span><span class="sxs-lookup"><span data-stu-id="fc6df-112">Group By options, if you want to copy only summary information.</span></span>  
  
 <span data-ttu-id="fc6df-113">L'esempio di query fornito di seguito consente di creare una nuova tabella denominata `uk`_`customers` e di copiarvi le informazioni contenute nella tabella `customers` :</span><span class="sxs-lookup"><span data-stu-id="fc6df-113">For example, the following query creates a new table called `uk`_`customers` and copies information from the `customers` table to it:</span></span>  
  
```  
SELECT *   
INTO uk_customers  
FROM customers  
WHERE country = 'UK'  
```  
  
 <span data-ttu-id="fc6df-114">Per utilizzare correttamente una query di creazione tabella è necessario che:</span><span class="sxs-lookup"><span data-stu-id="fc6df-114">In order to use a Make Table query successfully:</span></span>  
  
-   <span data-ttu-id="fc6df-115">il database supporti la sintassi SELECT...INTO;</span><span class="sxs-lookup"><span data-stu-id="fc6df-115">Your database must support the SELECT...INTO syntax.</span></span>  
  
-   <span data-ttu-id="fc6df-116">l'autore disponga dei privilegi necessari per creare una tabella nel database di destinazione.</span><span class="sxs-lookup"><span data-stu-id="fc6df-116">You must have permission to create a table in the target database.</span></span>  
  
### <a name="to-create-a-make-table-query"></a><span data-ttu-id="fc6df-117">Per creare una query di creazione tabella</span><span class="sxs-lookup"><span data-stu-id="fc6df-117">To create a Make Table query</span></span>  
  
1.  <span data-ttu-id="fc6df-118">Aggiungere le tabelle di origine nel riquadro Diagramma.</span><span class="sxs-lookup"><span data-stu-id="fc6df-118">Add the source table or tables to the Diagram pane.</span></span>  
  
2.  <span data-ttu-id="fc6df-119">Scegliere **Modifica tipo** dal menu **Progettazione query**e fare clic su **Creazione tabella**.</span><span class="sxs-lookup"><span data-stu-id="fc6df-119">From the **Query Designer** menu, point to **Change Type**, and then click **Make Table**.</span></span>  
  
3.  <span data-ttu-id="fc6df-120">Digitare il nome della tabella di destinazione nella finestra di dialogo **Creazione tabella** .</span><span class="sxs-lookup"><span data-stu-id="fc6df-120">In the **Make Table** dialog box, type the name of the destination table.</span></span> <span data-ttu-id="fc6df-121">In Progettazione query e Progettazione viste non viene eseguito alcun controllo per verificare se il nome è già in uso o se si è autorizzati a creare la tabella.</span><span class="sxs-lookup"><span data-stu-id="fc6df-121">The Query and View Designer does not check whether the name is already in use or whether you have permission to create the table.</span></span>  
  
     <span data-ttu-id="fc6df-122">Per creare una tabella di destinazione in un altro database è necessario specificare il nome completo di una tabella, compreso il nome del database di destinazione, il proprietario (se necessario) e il nome della tabella.</span><span class="sxs-lookup"><span data-stu-id="fc6df-122">To create a destination table in another database, specify a fully qualified table name including the name of the target database, the owner (if required), and the name of the table.</span></span>  
  
4.  <span data-ttu-id="fc6df-123">Specificare le colonne da copiare aggiungendole alla query.</span><span class="sxs-lookup"><span data-stu-id="fc6df-123">Specify the columns to copy by adding them to the query.</span></span> <span data-ttu-id="fc6df-124">Per altre informazioni dettagliate, vedere [Aggiungere colonne a query &#40;Visual Database Tools&#41;](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="fc6df-124">For details, see [Add Columns to Queries &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span> <span data-ttu-id="fc6df-125">Verranno copiate solo le colonne aggiunte alla query.</span><span class="sxs-lookup"><span data-stu-id="fc6df-125">Columns will be copied only if you add them to the query.</span></span> <span data-ttu-id="fc6df-126">Per copiare intere righe, scegliere \*\* \* (tutte le colonne)\*\*.</span><span class="sxs-lookup"><span data-stu-id="fc6df-126">To copy entire rows, choose **\* (All Columns)**.</span></span>  
  
     <span data-ttu-id="fc6df-127">Le colonne selezionate verranno aggiunte alla colonna **Colonna** del riquadro Criteri.</span><span class="sxs-lookup"><span data-stu-id="fc6df-127">The Query and View Designer adds the columns you choose to the **Column** column of the Criteria pane.</span></span>  
  
5.  <span data-ttu-id="fc6df-128">Se si desidera copiare le righe in un particolare ordine, specificare il criterio di ordinamento.</span><span class="sxs-lookup"><span data-stu-id="fc6df-128">If you want to copy rows in a particular order, specify a sort order.</span></span> <span data-ttu-id="fc6df-129">Per informazioni dettagliate, vedere **Ordinamento e raggruppamento dei risultati delle query**.</span><span class="sxs-lookup"><span data-stu-id="fc6df-129">For details, see **Sorting and Grouping Query Results**.</span></span>  
  
6.  <span data-ttu-id="fc6df-130">Specificare le righe da copiare immettendo le condizioni di ricerca.</span><span class="sxs-lookup"><span data-stu-id="fc6df-130">Specify the rows to copy by entering search conditions.</span></span> <span data-ttu-id="fc6df-131">Per informazioni dettagliate, vedere [Specifica di criteri di ricerca &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="fc6df-131">For details, see [Specify Search Criteria &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md).</span></span>  
  
     <span data-ttu-id="fc6df-132">Se non si specifica alcuna condizione di ricerca, tutte le righe della tabella di origine verranno copiate nella tabella di destinazione.</span><span class="sxs-lookup"><span data-stu-id="fc6df-132">If you do not specify a search condition, all rows from the source table will be copied to the destination table.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="fc6df-133">Quando nel riquadro Criteri si aggiunge una colonna da includere nella ricerca, tale colonna verrà aggiunta anche all'elenco delle colonne da copiare.</span><span class="sxs-lookup"><span data-stu-id="fc6df-133">When you add a column to search to the Criteria pane, the Query and View Designer also adds it to the list of columns to copy.</span></span> <span data-ttu-id="fc6df-134">Se si desidera utilizzare una colonna per la ricerca senza copiarla, deselezionare la casella di controllo accanto al nome della colonna nel rettangolo che rappresenta la tabella o l'oggetto con struttura di tabella.</span><span class="sxs-lookup"><span data-stu-id="fc6df-134">If you want to use a column for searching but not copy it, clear the check box next to the column name in the rectangle representing the table or table-structured object.</span></span>  
  
7.  <span data-ttu-id="fc6df-135">Se si desidera copiare le informazioni di riepilogo, specificare le opzioni di raggruppamento.</span><span class="sxs-lookup"><span data-stu-id="fc6df-135">If you want to copy summary information, specify Group By options.</span></span> <span data-ttu-id="fc6df-136">Per informazioni dettagliate, vedere [Riepilogo dei risultati di query &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="fc6df-136">For details, see [Summarize Query Results &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="fc6df-137">Quando si esegue una query di creazione tabella, non viene restituito alcun risultato nel [riquadro Risultati](results-pane-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="fc6df-137">When you execute a Make Table query, no results are reported in the [Results Pane](results-pane-visual-database-tools.md).</span></span> <span data-ttu-id="fc6df-138">Viene invece visualizzato un messaggio che indica il numero di righe copiate.</span><span class="sxs-lookup"><span data-stu-id="fc6df-138">Instead, a message appears indicating how many rows were copied.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc6df-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fc6df-139">See Also</span></span>  
 <span data-ttu-id="fc6df-140">[Procedure per la progettazione di query e viste &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="fc6df-140">[Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="fc6df-141">Tipi di query &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="fc6df-141">Types of Queries &#40;Visual Database Tools&#41;</span></span>](types-of-queries-visual-database-tools.md)  
  
  
