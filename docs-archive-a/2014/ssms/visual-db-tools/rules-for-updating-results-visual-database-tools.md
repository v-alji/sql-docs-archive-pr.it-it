---
title: Regole per l'aggiornamento dei risultati (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- View Designer, Results pane
- updating query results
- Query Designer [SQL Server], Results pane
- Results pane
ms.assetid: de131ef0-ccbd-446f-9400-b93c7b8fa537
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5cc6befc6571f29be95b176f8de6d7dcfaed9108
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719338"
---
# <a name="rules-for-updating-results-visual-database-tools"></a><span data-ttu-id="cceea-102">Regole per l'aggiornamento dei risultati (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="cceea-102">Rules for Updating Results (Visual Database Tools)</span></span>
  <span data-ttu-id="cceea-103">Normalmente è possibile aggiornare il set di risultati visualizzato nel [riquadro Risultati](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="cceea-103">In many cases, you can update the result set displayed in the [Results Pane](visual-database-tools.md).</span></span> <span data-ttu-id="cceea-104">Talvolta non è tuttavia possibile.</span><span class="sxs-lookup"><span data-stu-id="cceea-104">However, in some cases you cannot.</span></span>  
  
 <span data-ttu-id="cceea-105">Normalmente, per aggiornare i risultati, è necessario che in [Progettazione query e Progettazione viste](query-and-view-designer-tools-visual-database-tools.md) siano disponibili informazioni sufficienti per identificare in modo univoco la riga specifica all'interno della tabella.</span><span class="sxs-lookup"><span data-stu-id="cceea-105">In general, in order to update results, the [Query and View Designer](query-and-view-designer-tools-visual-database-tools.md) must have sufficient information to uniquely identify the row in the table.</span></span> <span data-ttu-id="cceea-106">Questo è ad esempio possibile quando la query include una chiave primaria nell'elenco di output.</span><span class="sxs-lookup"><span data-stu-id="cceea-106">An example is if the query includes a primary key in the output list.</span></span> <span data-ttu-id="cceea-107">Occorre inoltre disporre delle autorizzazioni necessarie per l'aggiornamento del database.</span><span class="sxs-lookup"><span data-stu-id="cceea-107">In addition, you must have sufficient permission to update the database.</span></span>  
  
 <span data-ttu-id="cceea-108">Se la query si basa su una vista, dovrebbe essere possibile aggiornarla.</span><span class="sxs-lookup"><span data-stu-id="cceea-108">If your query is based on a view, you might be able to update it.</span></span> <span data-ttu-id="cceea-109">Restano valide le stesse indicazioni, con l'eccezione che si applicano non solo alla vista in sé, ma anche alle tabelle sottostanti.</span><span class="sxs-lookup"><span data-stu-id="cceea-109">The same guidelines apply, except that they apply to the underlying tables in the view, not just to the view itself.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cceea-110">Progettazione query e Progettazione viste non è in grado di determinare in anticipo se sia possibile aggiornare un set di risultati sulla base di una vista.</span><span class="sxs-lookup"><span data-stu-id="cceea-110">The Query and View Designer cannot determine in advance whether you can update a result set based on a view.</span></span> <span data-ttu-id="cceea-111">Vengono pertanto visualizzate tutte le viste, anche se alcune potrebbero non essere aggiornabili.</span><span class="sxs-lookup"><span data-stu-id="cceea-111">Therefore, it displays all views, even though you might not be able to update them.</span></span>  
  
 <span data-ttu-id="cceea-112">La tabella che segue contiene un riepilogo di istanze specifiche in cui è o non è possibile aggiornare i risultati delle query nel riquadro Risultati.</span><span class="sxs-lookup"><span data-stu-id="cceea-112">The following table summarizes specific instances in which you might and might not be able to update query results in the Results pane.</span></span> <span data-ttu-id="cceea-113">In numerosi casi la possibilità di aggiornare o meno i risultati delle query dipende dal database utilizzato.</span><span class="sxs-lookup"><span data-stu-id="cceea-113">In many cases, the database you are using dictates whether you can update query results.</span></span>  
  
|<span data-ttu-id="cceea-114">Query</span><span class="sxs-lookup"><span data-stu-id="cceea-114">Query</span></span>|<span data-ttu-id="cceea-115">Possibilità di aggiornare i risultati</span><span class="sxs-lookup"><span data-stu-id="cceea-115">Can results be updated?</span></span>|  
|-----------|-----------------------------|  
|<span data-ttu-id="cceea-116">Query basata su una tabella con chiave primaria nell'elenco di output</span><span class="sxs-lookup"><span data-stu-id="cceea-116">Query based on one table with primary key in the output list</span></span>|<span data-ttu-id="cceea-117">Sì, ad eccezione di quanto elencato di seguito.</span><span class="sxs-lookup"><span data-stu-id="cceea-117">Yes (except as listed below).</span></span>|  
|<span data-ttu-id="cceea-118">Query basata su una tabella senza indice univoco e senza chiave primaria</span><span class="sxs-lookup"><span data-stu-id="cceea-118">Query based on a table with no unique index and without a primary key</span></span>|<span data-ttu-id="cceea-119">Dipende dalla query e dal database.</span><span class="sxs-lookup"><span data-stu-id="cceea-119">Depends on query and database.</span></span> <span data-ttu-id="cceea-120">Alcuni database consentono l'aggiornamento se sono disponibili informazioni sufficienti per l'identificazione univoca dei record.</span><span class="sxs-lookup"><span data-stu-id="cceea-120">Some databases allow updates if sufficient information is available to uniquely identify records.</span></span>|  
|<span data-ttu-id="cceea-121">Query basata su più tabelle non unite</span><span class="sxs-lookup"><span data-stu-id="cceea-121">Query based on multiple tables which are not joined</span></span>|<span data-ttu-id="cceea-122">No.</span><span class="sxs-lookup"><span data-stu-id="cceea-122">No.</span></span>|  
|<span data-ttu-id="cceea-123">Query basata su dati contrassegnati in sola lettura nel database</span><span class="sxs-lookup"><span data-stu-id="cceea-123">Query based on data marked as read-only in the database</span></span>|<span data-ttu-id="cceea-124">No.</span><span class="sxs-lookup"><span data-stu-id="cceea-124">No.</span></span>|  
|<span data-ttu-id="cceea-125">Query basata su una vista relativa a una tabella senza vincoli</span><span class="sxs-lookup"><span data-stu-id="cceea-125">Query based on a view that involves one table with no constraints</span></span>|<span data-ttu-id="cceea-126">Sì, ad eccezione di quanto elencato di seguito.</span><span class="sxs-lookup"><span data-stu-id="cceea-126">Yes (except as listed below).</span></span>|  
|<span data-ttu-id="cceea-127">Query basata su tabelle unite da una relazione uno-a-uno</span><span class="sxs-lookup"><span data-stu-id="cceea-127">Query based on tables joined with a one-to-one relationship</span></span>|<span data-ttu-id="cceea-128">Sì, ad eccezione di quanto elencato di seguito.</span><span class="sxs-lookup"><span data-stu-id="cceea-128">Yes (except as listed below).</span></span>|  
|<span data-ttu-id="cceea-129">Query basata su tabelle unite da una relazione uno-a-molti</span><span class="sxs-lookup"><span data-stu-id="cceea-129">Query based on tables joined with a one-to-many relationship</span></span>|<span data-ttu-id="cceea-130">In genere sì.</span><span class="sxs-lookup"><span data-stu-id="cceea-130">Usually.</span></span>|  
|<span data-ttu-id="cceea-131">Query basata su tre o più tabelle unite da una relazione molti-a-molti</span><span class="sxs-lookup"><span data-stu-id="cceea-131">Query based on three or more tables in which there is a many-to-many relationship</span></span>|<span data-ttu-id="cceea-132">No.</span><span class="sxs-lookup"><span data-stu-id="cceea-132">No.</span></span>|  
|<span data-ttu-id="cceea-133">Query basata su una tabella per la quale non è stata concessa l'autorizzazione di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="cceea-133">Query based on a table for which update permission is not granted</span></span>|<span data-ttu-id="cceea-134">Possibile l'eliminazione ma non l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="cceea-134">Can delete but not update.</span></span>|  
|<span data-ttu-id="cceea-135">Query basata su una tabella per la quale non è stata concessa l'autorizzazione di eliminazione</span><span class="sxs-lookup"><span data-stu-id="cceea-135">Query based on a table for which delete permission is not granted</span></span>|<span data-ttu-id="cceea-136">Possibile l'aggiornamento ma non l'eliminazione.</span><span class="sxs-lookup"><span data-stu-id="cceea-136">Can update but not delete.</span></span>|  
|<span data-ttu-id="cceea-137">Query di aggregazione</span><span class="sxs-lookup"><span data-stu-id="cceea-137">Aggregate query</span></span>|<span data-ttu-id="cceea-138">No.</span><span class="sxs-lookup"><span data-stu-id="cceea-138">No.</span></span>|  
|<span data-ttu-id="cceea-139">Query basata su una sottoquery contenente totali o funzioni di aggregazione</span><span class="sxs-lookup"><span data-stu-id="cceea-139">Query based on a subquery that contains totals or aggregate functions</span></span>|<span data-ttu-id="cceea-140">No.</span><span class="sxs-lookup"><span data-stu-id="cceea-140">No.</span></span>|  
|<span data-ttu-id="cceea-141">Query che include la parola chiave DISTINCT per l'esclusione di righe duplicate</span><span class="sxs-lookup"><span data-stu-id="cceea-141">Query that includes the DISTINCT keyword to exclude duplicate rows</span></span>|<span data-ttu-id="cceea-142">No.</span><span class="sxs-lookup"><span data-stu-id="cceea-142">No.</span></span>|  
|<span data-ttu-id="cceea-143">Query la cui clausola FROM include una funzione definita dall'utente che contiene più istruzioni Select e che restituisce una tabella</span><span class="sxs-lookup"><span data-stu-id="cceea-143">Query whose FROM clause includes a user-defined function that returns a table and the user-defined function contains multiple select statements</span></span>|<span data-ttu-id="cceea-144">No.</span><span class="sxs-lookup"><span data-stu-id="cceea-144">No.</span></span>|  
|<span data-ttu-id="cceea-145">Query la cui clausola FROM include una funzione inline definita dall'utente</span><span class="sxs-lookup"><span data-stu-id="cceea-145">Query whose FROM clause includes an inline user-defined function</span></span>|<span data-ttu-id="cceea-146">Sì.</span><span class="sxs-lookup"><span data-stu-id="cceea-146">Yes.</span></span>|  
  
 <span data-ttu-id="cceea-147">Può inoltre non essere possibile aggiornare colonne specifiche dei risultati delle query.</span><span class="sxs-lookup"><span data-stu-id="cceea-147">In addition, you might not be able to update specific columns in the query results.</span></span> <span data-ttu-id="cceea-148">L'elenco che segue contiene un riepilogo delle colonne che non è possibile aggiornare nel riquadro Risultati.</span><span class="sxs-lookup"><span data-stu-id="cceea-148">The following list summarizes specific types of columns that you cannot update in the Results pane.</span></span>  
  
-   <span data-ttu-id="cceea-149">Colonne basate su espressioni</span><span class="sxs-lookup"><span data-stu-id="cceea-149">Columns based on expressions</span></span>  
  
-   <span data-ttu-id="cceea-150">Colonne basate su funzioni scalari definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="cceea-150">Columns based on scalar user-defined functions</span></span>  
  
-   <span data-ttu-id="cceea-151">Righe o colonne eliminate da un altro utente</span><span class="sxs-lookup"><span data-stu-id="cceea-151">Rows or columns deleted by another user</span></span>  
  
-   <span data-ttu-id="cceea-152">Righe o colonne bloccate da un altro utente. Le righe bloccate possono in genere essere aggiornate appena vengono sbloccate.</span><span class="sxs-lookup"><span data-stu-id="cceea-152">Rows or columns locked by another user (locked rows can usually be updated as soon as they are unlocked)</span></span>  
  
-   <span data-ttu-id="cceea-153">Colonne timestamp o BLOB</span><span class="sxs-lookup"><span data-stu-id="cceea-153">Timestamp or BLOB columns</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cceea-154">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cceea-154">See Also</span></span>  
 [<span data-ttu-id="cceea-155">Procedure per la progettazione di query e viste &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="cceea-155">Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;</span></span>](design-queries-and-views-how-to-topics-visual-database-tools.md)  
  
  
