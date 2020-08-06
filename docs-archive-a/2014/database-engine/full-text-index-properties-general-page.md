---
title: Proprietà indice full-text (pagina generale) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
f1_keywords:
- sql12.swb.fulltextsearch.fulltextindexproperties.general.f1
ms.assetid: f4dff61c-8c2f-4ff9-abe4-70a34421448f
author: rothja
ms.author: jroth
ms.openlocfilehash: 61b9f2948df138c39230cf6f5787c395a364c695
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638051"
---
# <a name="full-text-index-properties-general-page"></a><span data-ttu-id="fe8c5-102">Proprietà indice full-text (pagina Generale)</span><span class="sxs-lookup"><span data-stu-id="fe8c5-102">Full-Text Index Properties (General Page)</span></span>
  <span data-ttu-id="fe8c5-103">**Per visualizzare o modificare le proprietà modificabili di un indice full-text**</span><span class="sxs-lookup"><span data-stu-id="fe8c5-103">**To view or change the modifiable properties of a full-text index**</span></span>  
  
-   [<span data-ttu-id="fe8c5-104">Gestione di indici full-text.</span><span class="sxs-lookup"><span data-stu-id="fe8c5-104">Manage Full-Text Indexes</span></span>](../relational-databases/indexes/indexes.md)  
  
## <a name="ui-element-list"></a><span data-ttu-id="fe8c5-105">Elenco di elementi dell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="fe8c5-105">UI element list</span></span>  
 <span data-ttu-id="fe8c5-106">**Catalogo full-text**</span><span class="sxs-lookup"><span data-stu-id="fe8c5-106">**Full-Text Catalog**</span></span>  
 <span data-ttu-id="fe8c5-107">Visualizza il nome del catalogo full-text a cui è associato l'indice full-text.</span><span class="sxs-lookup"><span data-stu-id="fe8c5-107">Displays the name of the full-text catalog with which the full-text index is associated.</span></span>  
  
 <span data-ttu-id="fe8c5-108">**Database**</span><span class="sxs-lookup"><span data-stu-id="fe8c5-108">**Database**</span></span>  
 <span data-ttu-id="fe8c5-109">Visualizza il nome del database in cui risiede l'indice full-text.</span><span class="sxs-lookup"><span data-stu-id="fe8c5-109">Displays the name of the database in which the full-text index resides.</span></span>  
  
 <span data-ttu-id="fe8c5-110">**Tabella**</span><span class="sxs-lookup"><span data-stu-id="fe8c5-110">**Table**</span></span>  
 <span data-ttu-id="fe8c5-111">Visualizza il nome della tabella utilizzata per la definizione dell'indice full-text.</span><span class="sxs-lookup"><span data-stu-id="fe8c5-111">Displays the name of the table on which the full-text index is defined.</span></span>  
  
 <span data-ttu-id="fe8c5-112">**Chiave indice full-text**</span><span class="sxs-lookup"><span data-stu-id="fe8c5-112">**Full-Text Index Key**</span></span>  
 <span data-ttu-id="fe8c5-113">Visualizza il nome della chiave per l'indice full-text, ovvero un indice univoco presente in una singola colonna della tabella.</span><span class="sxs-lookup"><span data-stu-id="fe8c5-113">Displays the name of the full-text index key, which is a unique index on a single column of the table.</span></span>  
  
 <span data-ttu-id="fe8c5-114">**Stato popolamento full-text tabella**</span><span class="sxs-lookup"><span data-stu-id="fe8c5-114">**Table Full-Text Populate Status**</span></span>  
 <span data-ttu-id="fe8c5-115">Visualizza lo stato di popolamento della tabella con indicizzazione full-text.</span><span class="sxs-lookup"><span data-stu-id="fe8c5-115">Displays the population status of the full-text indexed table.</span></span>  
  
 <span data-ttu-id="fe8c5-116">I valori possibili sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="fe8c5-116">The possible values are as follows:</span></span>  
  
 <span data-ttu-id="fe8c5-117">0 = Inattivo</span><span class="sxs-lookup"><span data-stu-id="fe8c5-117">0 = Idle.</span></span>  
  
 <span data-ttu-id="fe8c5-118">1 = Popolamento completo in corso.</span><span class="sxs-lookup"><span data-stu-id="fe8c5-118">1 = Full population is in progress.</span></span>  
  
 <span data-ttu-id="fe8c5-119">2 = Popolamento incrementale in corso.</span><span class="sxs-lookup"><span data-stu-id="fe8c5-119">2 = Incremental population is in progress.</span></span>  
  
 <span data-ttu-id="fe8c5-120">3 = Propagazione delle modifiche rilevate in corso.</span><span class="sxs-lookup"><span data-stu-id="fe8c5-120">3 = Propagation of tracked changes is in progress.</span></span>  
  
 <span data-ttu-id="fe8c5-121">4 = Operazione in corso per l'indice ad aggiornamento in background, ad esempio il rilevamento automatico delle modifiche.</span><span class="sxs-lookup"><span data-stu-id="fe8c5-121">4 = Background update index is in progress, such as automatic change tracking.</span></span>  
  
 <span data-ttu-id="fe8c5-122">5 = Indicizzazione full-text rallentata o sospesa.</span><span class="sxs-lookup"><span data-stu-id="fe8c5-122">5 = Full-text indexing is throttled or paused.</span></span>  
  
 <span data-ttu-id="fe8c5-123">**Indice full-text attivo**</span><span class="sxs-lookup"><span data-stu-id="fe8c5-123">**Active Full-Text Index**</span></span>  
 <span data-ttu-id="fe8c5-124">Indica se la tabella include un indice full-text attivo.</span><span class="sxs-lookup"><span data-stu-id="fe8c5-124">Indicates whether the table has an active full-text index.</span></span>  
  
 <span data-ttu-id="fe8c5-125">1 = True</span><span class="sxs-lookup"><span data-stu-id="fe8c5-125">1 = True</span></span>  
  
 <span data-ttu-id="fe8c5-126">0 = False</span><span class="sxs-lookup"><span data-stu-id="fe8c5-126">0 = False</span></span>  
  
 <span data-ttu-id="fe8c5-127">**Filegroup indice full-text**</span><span class="sxs-lookup"><span data-stu-id="fe8c5-127">**Full-Text Index Filegroup**</span></span>  
 <span data-ttu-id="fe8c5-128">Filegroup cui appartiene l'indice full-text.</span><span class="sxs-lookup"><span data-stu-id="fe8c5-128">The filegroup to which the full-text index belongs.</span></span>  
  
 <span data-ttu-id="fe8c5-129">**Elenco di parole non significative indice full-text**</span><span class="sxs-lookup"><span data-stu-id="fe8c5-129">**Full-Text Index Stoplist**</span></span>  
 <span data-ttu-id="fe8c5-130">Elenco di parole non significative associate all'indice full-text.</span><span class="sxs-lookup"><span data-stu-id="fe8c5-130">The stoplist that is currently associated with the full-text index.</span></span> <span data-ttu-id="fe8c5-131">Un elenco di [parole non significative](../relational-databases/search/full-text-search.md)</span><span class="sxs-lookup"><span data-stu-id="fe8c5-131">A stoplist is a list of [stopwords](../relational-databases/search/full-text-search.md).</span></span> <span data-ttu-id="fe8c5-132">eventualmente associato a un indice full-text viene applicato alle query full-text su tale indice.</span><span class="sxs-lookup"><span data-stu-id="fe8c5-132">The stoplist associated with a full-text index, if any, is applied to full-text queries on that index.</span></span> <span data-ttu-id="fe8c5-133">È possibile rimuovere l'elenco di parole non significative dall'indice selezionando **\<OFF>** dall'elenco oppure è possibile selezionare un elenco di parole non significative diverso; indica l'elenco di parole non significative di **\<SYSTEM>** sistema.</span><span class="sxs-lookup"><span data-stu-id="fe8c5-133">You can remove the stoplist from the index by selecting **\<OFF>** from the list, or you can select a different stoplist; **\<SYSTEM>** indicates the system stoplist.</span></span>  
  
 <span data-ttu-id="fe8c5-134">**Per creare un elenco di parole non significative**</span><span class="sxs-lookup"><span data-stu-id="fe8c5-134">**To create a stoplist**</span></span>  
  
-   [<span data-ttu-id="fe8c5-135">Configurare e gestire parole non significative ed elenchi di parole non significative per la ricerca full-text</span><span class="sxs-lookup"><span data-stu-id="fe8c5-135">Configure and Manage Stopwords and Stoplists for Full-Text Search</span></span>](../relational-databases/search/full-text-search.md)  
  
 <span data-ttu-id="fe8c5-136">**Elenco delle proprietà di ricerca**</span><span class="sxs-lookup"><span data-stu-id="fe8c5-136">**Search Property List**</span></span>  
 <span data-ttu-id="fe8c5-137">Elenco delle proprietà di ricerca, se presente, attualmente associato all'indice full-text.</span><span class="sxs-lookup"><span data-stu-id="fe8c5-137">The search property list that is currently associated with the full-text index, if any.</span></span> <span data-ttu-id="fe8c5-138">Un elenco delle proprietà di ricerca specifica un set di proprietà del documento incluse nell'indice full-text associato al momento del popolamento.</span><span class="sxs-lookup"><span data-stu-id="fe8c5-138">A search property list specifies a set of document properties that are included in the associated full-text index when it is populated.</span></span> <span data-ttu-id="fe8c5-139">Per altre informazioni, vedere [Eseguire ricerche nelle proprietà dei documenti con elenchi delle proprietà di ricerca](../relational-databases/search/search-document-properties-with-search-property-lists.md).</span><span class="sxs-lookup"><span data-stu-id="fe8c5-139">For more information, see [Search Document Properties with Search Property Lists](../relational-databases/search/search-document-properties-with-search-property-lists.md).</span></span>  
  
 <span data-ttu-id="fe8c5-140">**\<Off>** indica che all'indice non è attualmente associato alcun elenco di proprietà di ricerca.</span><span class="sxs-lookup"><span data-stu-id="fe8c5-140">**\<Off>** indicates that there is currently no search property list associated with the index.</span></span> <span data-ttu-id="fe8c5-141">È possibile rimuovere l'elenco delle proprietà di ricerca corrente dall'indice selezionando **\<Off>** nell'elenco oppure è possibile selezionare un elenco di proprietà di ricerca diverso nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="fe8c5-141">You can remove the current search property list from the index by selecting **\<Off>** from the list, or you can select a different search property list from the list.</span></span> <span data-ttu-id="fe8c5-142">Questo elenco contiene solo gli elenchi delle proprietà di ricerca inclusi nel database corrente.</span><span class="sxs-lookup"><span data-stu-id="fe8c5-142">Only search property lists in the current database are listed here.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fe8c5-143">È possibile associare un elenco delle proprietà di ricerca specificato a più indici full-text nello stesso database.</span><span class="sxs-lookup"><span data-stu-id="fe8c5-143">You can associate a given search property list with more than one full-text index in the same database.</span></span>  
  
 <span data-ttu-id="fe8c5-144">**Per creare un elenco delle proprietà di ricerca**</span><span class="sxs-lookup"><span data-stu-id="fe8c5-144">**To create a search property list**</span></span>  
  
-   [<span data-ttu-id="fe8c5-145">Eseguire ricerche nelle proprietà dei documenti con elenchi delle proprietà di ricerca</span><span class="sxs-lookup"><span data-stu-id="fe8c5-145">Search Document Properties with Search Property Lists</span></span>](../relational-databases/search/search-document-properties-with-search-property-lists.md)  
  
 <span data-ttu-id="fe8c5-146">**Conteggio elementi full-text tabella**</span><span class="sxs-lookup"><span data-stu-id="fe8c5-146">**Table Full-Text Item Count**</span></span>  
 <span data-ttu-id="fe8c5-147">Indica il numero di righe sottoposte correttamente a indicizzazione full-text.</span><span class="sxs-lookup"><span data-stu-id="fe8c5-147">Indicates the number of rows that were full-text indexed successfully.</span></span>  
  
 <span data-ttu-id="fe8c5-148">Questa proprietà corrisponde alla proprietà `TableFulltextItemCount` restituita dalla funzione [!INCLUDE[tsql](../includes/tsql-md.md)] OBJECTPROPERTYEX.</span><span class="sxs-lookup"><span data-stu-id="fe8c5-148">This property corresponds to the `TableFulltextItemCount` property returned by the OBJECTPROPERTYEX [!INCLUDE[tsql](../includes/tsql-md.md)] function.</span></span>  
  
 <span data-ttu-id="fe8c5-149">**Documenti full-text della tabella elaborati**</span><span class="sxs-lookup"><span data-stu-id="fe8c5-149">**Table Full-Text Docs Processed**</span></span>  
 <span data-ttu-id="fe8c5-150">Visualizza il numero di righe che sono state elaborate dopo l'avvio dell'indicizzazione full-text.</span><span class="sxs-lookup"><span data-stu-id="fe8c5-150">Displays the number of rows that have been processed since the start of full-text indexing.</span></span> <span data-ttu-id="fe8c5-151">In una tabella sottoposta a indicizzazione ai fini della ricerca full-text tutte le colonne di una riga vengono considerate come appartenenti a un unico documento da indicizzare.</span><span class="sxs-lookup"><span data-stu-id="fe8c5-151">In a table that is being indexed for full-text search, all the columns of one row are considered as part of one document to be indexed.</span></span> <span data-ttu-id="fe8c5-152">Le righe eliminate non vengono conteggiate.</span><span class="sxs-lookup"><span data-stu-id="fe8c5-152">Deleted rows are not counted.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fe8c5-153">0</span><span class="sxs-lookup"><span data-stu-id="fe8c5-153">0</span></span>|<span data-ttu-id="fe8c5-154">Indica che l'indicizzazione full-text è stata completata e non è presente alcun popolamento attivo.</span><span class="sxs-lookup"><span data-stu-id="fe8c5-154">Indicates that full-text indexing is completed and there is no active population.</span></span>|  
|<span data-ttu-id="fe8c5-155">> 0</span><span class="sxs-lookup"><span data-stu-id="fe8c5-155">> 0</span></span>|<span data-ttu-id="fe8c5-156">Per un popolamento attivo, indica il numero di documenti elaborati da operazioni di inserimento o aggiornamento dopo una delle operazioni seguenti: popolamento, abilitazione del rilevamento delle modifiche con popolamento dell'indice ad aggiornamento in background (ad esempio il rilevamento automatico delle modifiche), modifica dello schema dell'indice full-text, ricompilazione del catalogo full-text, riavvio dell'istanza di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]e così via.</span><span class="sxs-lookup"><span data-stu-id="fe8c5-156">For an active population, indicates the number of documents processed by insert or update operations since any of the following: a population, enabling of change tracking with background update index population (such as auto change tracking), changing the full-text index schema, rebuilding the full-text catalog, restarting the instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], and so forth.</span></span>|  
  
 <span data-ttu-id="fe8c5-157">**Modifiche in sospeso full-text tabella**</span><span class="sxs-lookup"><span data-stu-id="fe8c5-157">**Table Full-Text Pending Changes**</span></span>  
 <span data-ttu-id="fe8c5-158">Numero di voci in sospeso del rilevamento delle modifiche da elaborare.</span><span class="sxs-lookup"><span data-stu-id="fe8c5-158">Number of pending change tracking entries to process.</span></span>  
  
 <span data-ttu-id="fe8c5-159">0 = Il rilevamento delle modifiche non è abilitato.</span><span class="sxs-lookup"><span data-stu-id="fe8c5-159">0 = change tracking is not enabled.</span></span>  
  
 <span data-ttu-id="fe8c5-160">NULL = La tabella non include un indice full-text.</span><span class="sxs-lookup"><span data-stu-id="fe8c5-160">NULL = Table does not have a full-text index.</span></span>  
  
 <span data-ttu-id="fe8c5-161">**Conteggio errori full-text tabella**</span><span class="sxs-lookup"><span data-stu-id="fe8c5-161">**Table Full-Text Fail Count**</span></span>  
 <span data-ttu-id="fe8c5-162">Numero di righe non indicizzate dalla ricerca full-text.</span><span class="sxs-lookup"><span data-stu-id="fe8c5-162">The number of rows that full-text search did not index.</span></span>  
  
 <span data-ttu-id="fe8c5-163">0 = Popolamento completato.</span><span class="sxs-lookup"><span data-stu-id="fe8c5-163">0 = The population has completed.</span></span>  
  
 <span data-ttu-id="fe8c5-164">\>0 = uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="fe8c5-164">\>0 = One of the following:</span></span>  
  
-   <span data-ttu-id="fe8c5-165">Numero di documenti non indicizzati dopo l'avvio del popolamento con rilevamento delle modifiche ad aggiornamento completo, incrementale e manuale.</span><span class="sxs-lookup"><span data-stu-id="fe8c5-165">The number of documents that were not indexed since the start of full, incremental, or manual change tracking population.</span></span>  
  
-   <span data-ttu-id="fe8c5-166">Per il rilevamento delle modifiche con un indice ad aggiornamento in background, numero di righe non indicizzate dopo l'avvio o il riavvio del popolamento.</span><span class="sxs-lookup"><span data-stu-id="fe8c5-166">For change tracking with background update index, the number of rows that were not indexed since the start of the population, or the restart of the population.</span></span> <span data-ttu-id="fe8c5-167">La mancata indicizzazione potrebbe essere dovuta a una modifica dello schema, alla ricompilazione del catalogo, al riavvio del server e così via.</span><span class="sxs-lookup"><span data-stu-id="fe8c5-167">This could be caused by a schema change, rebuild of the catalog, server restart, and so on</span></span>  
  
 <span data-ttu-id="fe8c5-168">**Indicizzazione full-text abilitata**</span><span class="sxs-lookup"><span data-stu-id="fe8c5-168">**Full-Text Indexing Enabled**</span></span>  
 <span data-ttu-id="fe8c5-169">Specifica se l'indicizzazione full-text è abilitata.</span><span class="sxs-lookup"><span data-stu-id="fe8c5-169">Specifies whether full-text indexing is enabled.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fe8c5-170">**True**</span><span class="sxs-lookup"><span data-stu-id="fe8c5-170">**True**</span></span>|<span data-ttu-id="fe8c5-171">Attivato</span><span class="sxs-lookup"><span data-stu-id="fe8c5-171">Enabled</span></span>|  
|<span data-ttu-id="fe8c5-172">**False**</span><span class="sxs-lookup"><span data-stu-id="fe8c5-172">**False**</span></span>|<span data-ttu-id="fe8c5-173">Disabled</span><span class="sxs-lookup"><span data-stu-id="fe8c5-173">Disabled</span></span>|  
  
 <span data-ttu-id="fe8c5-174">**Rilevamento delle modifiche**</span><span class="sxs-lookup"><span data-stu-id="fe8c5-174">**Change Tracking**</span></span>  
 <span data-ttu-id="fe8c5-175">Specifica se per la tabella è abilitato il rilevamento delle modifiche full-text e, in caso affermativo, di quale tipo.</span><span class="sxs-lookup"><span data-stu-id="fe8c5-175">Specifies whether the table has full-text change-tracking enabled, and if so, what kind.</span></span> <span data-ttu-id="fe8c5-176">Con il rilevamento delle modifiche full-text viene mantenuto un record delle righe modificate in una tabella o in una vista indicizzata configurata per l'indicizzazione full-text.</span><span class="sxs-lookup"><span data-stu-id="fe8c5-176">Full-text change tracking maintains a record of the rows that have been modified in a table or indexed view that has been set up for full-text indexing.</span></span> <span data-ttu-id="fe8c5-177">Tali modifiche possono essere propagate nell'indice full-text.</span><span class="sxs-lookup"><span data-stu-id="fe8c5-177">These changes can be propagated to the full-text index.</span></span>  
  
 <span data-ttu-id="fe8c5-178">I valori di **Rilevamento modifiche** sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="fe8c5-178">The **Change Tracking** values are as follows:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fe8c5-179">**Disattivato**</span><span class="sxs-lookup"><span data-stu-id="fe8c5-179">**Off**</span></span>|<span data-ttu-id="fe8c5-180">L'indice full-text non viene aggiornato con le modifiche apportate ai dati sottostanti.</span><span class="sxs-lookup"><span data-stu-id="fe8c5-180">The full-text index is not updated with changes to the underlying data.</span></span>|  
|<span data-ttu-id="fe8c5-181">**Manuale**</span><span class="sxs-lookup"><span data-stu-id="fe8c5-181">**Manual**</span></span>|<span data-ttu-id="fe8c5-182">L'indice full-text non viene aggiornato automaticamente con le modifiche apportate ai dati sottostanti.</span><span class="sxs-lookup"><span data-stu-id="fe8c5-182">The full-text index is not updated automatically as changes occur to the underlying data.</span></span> <span data-ttu-id="fe8c5-183">Tuttavia, le modifiche apportate ai dati sottostanti vengono mantenute ed è possibile propagarle all'indice</span><span class="sxs-lookup"><span data-stu-id="fe8c5-183">However, changes to the underlying data are maintained, and you can propagate them to the .</span></span> <span data-ttu-id="fe8c5-184">full-text in base a una pianificazione utilizzando SQL Server Agent o manualmente.</span><span class="sxs-lookup"><span data-stu-id="fe8c5-184">full-text index either on a schedule using SQL Server Agent or manually.</span></span>|  
|<span data-ttu-id="fe8c5-185">**Automatic** (Automatica)</span><span class="sxs-lookup"><span data-stu-id="fe8c5-185">**Automatic**</span></span>|<span data-ttu-id="fe8c5-186">L'indice full-text viene aggiornato automaticamente con le modifiche apportate ai dati sottostanti nella tabella di base.</span><span class="sxs-lookup"><span data-stu-id="fe8c5-186">The full-text index is updated automatically as changes occur to the underlying data in the base table.</span></span>|  
  
 <span data-ttu-id="fe8c5-187">**Ripopolamento indice**</span><span class="sxs-lookup"><span data-stu-id="fe8c5-187">**Repopulate index**</span></span>  
 <span data-ttu-id="fe8c5-188">Fare clic per avviare un popolamento sull'indice full-text alla chiusura della finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="fe8c5-188">Click to start a population on the full-text index on exiting the dialog box.</span></span> <span data-ttu-id="fe8c5-189">Selezionare uno dei tipi di popolamento seguenti:</span><span class="sxs-lookup"><span data-stu-id="fe8c5-189">Select one of the following types of population:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fe8c5-190">**Completo**</span><span class="sxs-lookup"><span data-stu-id="fe8c5-190">**Full**</span></span>|<span data-ttu-id="fe8c5-191">Durante il popolamento di una tabella, vengono create voci di indice per tutte le righe.</span><span class="sxs-lookup"><span data-stu-id="fe8c5-191">During a full population of a table, index entries are built for all the rows.</span></span>|  
|<span data-ttu-id="fe8c5-192">**Incrementale**</span><span class="sxs-lookup"><span data-stu-id="fe8c5-192">**Incremental**</span></span>|<span data-ttu-id="fe8c5-193">Il popolamento incrementale aggiorna l'indice full-text relativamente alle righe aggiunte, eliminate o modificate dopo l'ultimo popolamento o durante la sua esecuzione.</span><span class="sxs-lookup"><span data-stu-id="fe8c5-193">Incremental population updates the full-text index for rows added, deleted, or modified after the last population, or while the last population was in progress.</span></span> <span data-ttu-id="fe8c5-194">Per eseguire un popolamento incrementale, è necessario che la tabella di base contenga una colonna del tipo di dati `timestamp`.</span><span class="sxs-lookup"><span data-stu-id="fe8c5-194">Performing an incremental population requires that the base table contain a column of the `timestamp` data type.</span></span>|  
|<span data-ttu-id="fe8c5-195">**Aggiornamento**</span><span class="sxs-lookup"><span data-stu-id="fe8c5-195">**Update**</span></span>|<span data-ttu-id="fe8c5-196">L'indice full-text viene aggiornato ogni qual volta i dati della tabella di base vengono modificati.</span><span class="sxs-lookup"><span data-stu-id="fe8c5-196">The full-text index is updated whenever the data in the base table is modified.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fe8c5-197">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fe8c5-197">See Also</span></span>  
 [<span data-ttu-id="fe8c5-198">Introduzione alla ricerca full-text</span><span class="sxs-lookup"><span data-stu-id="fe8c5-198">Get Started with Full-Text Search</span></span>](../relational-databases/search/get-started-with-full-text-search.md)  
  
  
