---
title: Aggiungere tabelle a query (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- inserting tables
- adding tables
- queries [SQL Server], tables
ms.assetid: 6551aa7e-31a1-4636-852a-819bc53d658b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 572002bc913cc9916a75ce2b16c12064452d250f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629139"
---
# <a name="add-tables-to-queries-visual-database-tools"></a><span data-ttu-id="032e8-102">Aggiunta di tabelle a query (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="032e8-102">Add Tables to Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="032e8-103">Quando si crea una query, si recuperano dati da una tabella o da altri oggetti strutturati come tabelle, come viste e alcune funzioni definite dall'utente.</span><span class="sxs-lookup"><span data-stu-id="032e8-103">When you create a query, you are retrieving data from a table or other objects structured like tables - views and certain user-defined functions.</span></span> <span data-ttu-id="032e8-104">Per usare uno qualsiasi di questi oggetti nelle query, è necessario aggiungerlo nel **riquadro Diagramma**.</span><span class="sxs-lookup"><span data-stu-id="032e8-104">To work with any of these objects in your query, you add them to the **Diagram Pane**.</span></span>  
  
### <a name="to-add-a-table-or-table-valued-object-to-a-query"></a><span data-ttu-id="032e8-105">Per aggiungere una tabella o un oggetto con valori di tabella a una query</span><span class="sxs-lookup"><span data-stu-id="032e8-105">To add a table or table-valued object to a query</span></span>  
  
1.  <span data-ttu-id="032e8-106">Nel **riquadro Diagramma** di Progettazione query e Progettazione viste fare clic col pulsante destro sullo sfondo e scegliere **Aggiungi tabella** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="032e8-106">In the **Diagram pane** of the Query and View Designer, right-click the background and choose **Add Table** from the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="032e8-107">Nella finestra di dialogo **Aggiungi tabella** selezionare la scheda relativa al tipo di oggetto da aggiungere alla query.</span><span class="sxs-lookup"><span data-stu-id="032e8-107">In the **Add Table** dialog box, select the tab for the type of object you want to add to the query.</span></span>  
  
3.  <span data-ttu-id="032e8-108">Fare doppio clic sulle voci dell'elenco che si desidera aggiungere.</span><span class="sxs-lookup"><span data-stu-id="032e8-108">In the list of items, double-click each item you want to add.</span></span>  
  
4.  <span data-ttu-id="032e8-109">Dopo aver aggiunto tutte le voci appropriate, fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="032e8-109">When you finish adding items, click **Close**.</span></span>  
  
     <span data-ttu-id="032e8-110">Progettazione query e Progettazione viste aggiornano di conseguenza il **riquadro Diagramma**, il **riquadro Criteri**e il **riquadro SQL** .</span><span class="sxs-lookup"><span data-stu-id="032e8-110">The Query and View Designer updates the **Diagram Pane**, **Criteria Pane**, and **SQL Pane** accordingly.</span></span>  
  
 <span data-ttu-id="032e8-111">Le tabelle e le viste vengono aggiunte automaticamente alla query quando si fa riferimento ad esse nell'istruzione nel riquadro SQL.</span><span class="sxs-lookup"><span data-stu-id="032e8-111">Tables and views are automatically added to the query when you reference them in the statement in the SQL pane.</span></span>  
  
 <span data-ttu-id="032e8-112">Se non si dispone di diritti di accesso sufficienti o se il provider non è in grado di restituire le informazioni necessarie, in Progettazione query e Progettazione viste non verrà visualizzata alcuna colonna di dati per una tabella o un oggetto con valori di tabella.</span><span class="sxs-lookup"><span data-stu-id="032e8-112">The Query and View Designer will not display data columns for a table or table-structured object if you do not have sufficient access rights to it or if the provider cannot return information about it.</span></span> <span data-ttu-id="032e8-113">In questi casi, verranno visualizzati solo una barra del titolo e la casella di controllo \* (tutte le colonne) per la tabella o l'oggetto con valori di tabella.</span><span class="sxs-lookup"><span data-stu-id="032e8-113">In such cases, only a title bar and the \* (All Columns) check box are displayed for the table or table-valued object.</span></span>  
  
### <a name="to-add-an-existing-query-to-a-new-query"></a><span data-ttu-id="032e8-114">Per aggiungere una query esistente a una nuova query</span><span class="sxs-lookup"><span data-stu-id="032e8-114">To add an existing query to a new query</span></span>  
  
1.  <span data-ttu-id="032e8-115">Assicurarsi che nella nuova query che si sta creando sia visibile il **riquadro SQL** .</span><span class="sxs-lookup"><span data-stu-id="032e8-115">Make sure the **SQL Pane** is displayed in the new query you are creating.</span></span>  
  
2.  <span data-ttu-id="032e8-116">Nel **riquadro SQL**digitare una parentesi sinistra e una destra () dopo la parola FROM.</span><span class="sxs-lookup"><span data-stu-id="032e8-116">In the **SQL Pane**, type a right and left parentheses () after the word FROM.</span></span>  
  
3.  <span data-ttu-id="032e8-117">Aprire Progettazione query dalla query esistente.</span><span class="sxs-lookup"><span data-stu-id="032e8-117">Open the Query Designer for the existing query.</span></span> <span data-ttu-id="032e8-118">A questo punto saranno aperte due istanze di Progettazione query.</span><span class="sxs-lookup"><span data-stu-id="032e8-118">(You now have two Query Designers open.)</span></span>  
  
4.  <span data-ttu-id="032e8-119">Visualizzare il **riquadro SQL** per la query interna, ossia la query esistente da includere nella nuova query esterna.</span><span class="sxs-lookup"><span data-stu-id="032e8-119">Display the **SQL Pane** for the inner query - the existing query you are including in the new, outer query.</span></span>  
  
5.  <span data-ttu-id="032e8-120">Selezionare tutto il testo presente nel **riquadro SQL**e copiarlo negli Appunti.</span><span class="sxs-lookup"><span data-stu-id="032e8-120">Select all the text in the **SQL Pane**, and copy it to the Clipboard.</span></span>  
  
6.  <span data-ttu-id="032e8-121">Fare clic nel **riquadro SQL** della nuova query, posizionare il cursore tra le parentesi aggiunte e incollare il contenuto degli Appunti.</span><span class="sxs-lookup"><span data-stu-id="032e8-121">Click in the **SQL Pane** of the new query, situate the cursor between the parentheses you added, and paste the contents of the Clipboard.</span></span>  
  
7.  <span data-ttu-id="032e8-122">Sempre nel **riquadro SQL**aggiungere un alias dopo la parentesi destra.</span><span class="sxs-lookup"><span data-stu-id="032e8-122">Still in the **SQL Pane**, add an alias after the right parenthesis.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="032e8-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="032e8-123">See Also</span></span>  
 <span data-ttu-id="032e8-124">[Creazione di alias di tabella &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="032e8-124">[Create Table Aliases &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 <span data-ttu-id="032e8-125">[Rimuovere tabelle da query &#40;Visual Database Tools&#41;](remove-tables-from-queries-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="032e8-125">[Remove Tables from Queries &#40;Visual Database Tools&#41;](remove-tables-from-queries-visual-database-tools.md) </span></span>  
 <span data-ttu-id="032e8-126">[Specificare i criteri di ricerca &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="032e8-126">[Specify Search Criteria &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md) </span></span>  
 <span data-ttu-id="032e8-127">[Riepilogare i risultati delle query &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="032e8-127">[Summarize Query Results &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="032e8-128">Eseguire operazioni di base con le query &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="032e8-128">Perform Basic Operations with Queries &#40;Visual Database Tools&#41;</span></span>](perform-basic-operations-with-queries-visual-database-tools.md)  
  
  
