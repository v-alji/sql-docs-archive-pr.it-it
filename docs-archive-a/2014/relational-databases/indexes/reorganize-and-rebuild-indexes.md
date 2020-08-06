---
title: Riorganizzare e ricompilare gli indici | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
f1_keywords:
- sql12.swb.indexproperties.fragmentation.f1
- sql12.swb.index.reorg.f1
- sql12.swb.index.rebuild.f1
helpviewer_keywords:
- large object defragmenting
- indexes [SQL Server], reorganizing
- index reorganization [SQL Server]
- reorganizing indexes
- defragmenting large object data types
- index fragmentation [SQL Server]
- index rebuilding [SQL Server]
- rebuilding indexes
- indexes [SQL Server], rebuilding
- defragmenting indexes
- nonclustered indexes [SQL Server], defragmenting
- fragmentation [SQL Server]
- index defragmenting [SQL Server]
- LOB data [SQL Server], defragmenting
- clustered indexes, defragmenting
ms.assetid: a28c684a-c4e9-4b24-a7ae-e248808b31e9
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 7c00f2128bb4c54064511ffff9e8929c9faf4d59
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723872"
---
# <a name="reorganize-and-rebuild-indexes"></a><span data-ttu-id="e72a5-102">Riorganizzare e ricompilare gli indici</span><span class="sxs-lookup"><span data-stu-id="e72a5-102">Reorganize and Rebuild Indexes</span></span>
  <span data-ttu-id="e72a5-103">In questo argomento viene descritto come riorganizzare o ricompilare un indice frammentato in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e72a5-103">This topic describes how to reorganize or rebuild a fragmented index in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="e72a5-104">Tramite il [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] la manutenzione degli indici viene automaticamente eseguita dopo ogni operazione di modifica, inserimento o eliminazione dei dati sottostanti.</span><span class="sxs-lookup"><span data-stu-id="e72a5-104">The [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] automatically maintains indexes whenever insert, update, or delete operations are made to the underlying data.</span></span> <span data-ttu-id="e72a5-105">Nel tempo, queste modifiche possono provocare la frammentazione dell'indice nel database.</span><span class="sxs-lookup"><span data-stu-id="e72a5-105">Over time these modifications can cause the information in the index to become scattered in the database (fragmented).</span></span> <span data-ttu-id="e72a5-106">La frammentazione si verifica quando negli indici sono presenti pagine in cui l'ordinamento logico, basato sul valore chiave, non corrisponde all'ordinamento fisico all'interno del file di dati.</span><span class="sxs-lookup"><span data-stu-id="e72a5-106">Fragmentation exists when indexes have pages in which the logical ordering, based on the key value, does not match the physical ordering inside the data file.</span></span> <span data-ttu-id="e72a5-107">Gli indici con un alto grado di frammentazione possono essere causa del calo delle prestazioni delle query e rallentare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e72a5-107">Heavily fragmented indexes can degrade query performance and cause your application to respond slowly.</span></span>  
  
 <span data-ttu-id="e72a5-108">È possibile porre rimedio alla frammentazione eseguendo la riorganizzazione o la ricompilazione dell'indice.</span><span class="sxs-lookup"><span data-stu-id="e72a5-108">You can remedy index fragmentation by reorganizing or rebuilding an index.</span></span> <span data-ttu-id="e72a5-109">Per gli indici partizionati compilati in base a uno schema di partizione è possibile procedere in uno dei metodi seguenti sull'intero indice o su una singola partizione.</span><span class="sxs-lookup"><span data-stu-id="e72a5-109">For partitioned indexes built on a partition scheme, you can use either of these methods on a complete index or a single partition of an index.</span></span> <span data-ttu-id="e72a5-110">La ricompilazione di un indice consiste nell'eliminazione e nella ricreazione dell'indice.</span><span class="sxs-lookup"><span data-stu-id="e72a5-110">Rebuilding an index drops and re-creates the index.</span></span> <span data-ttu-id="e72a5-111">Questa operazione consente di rimuovere la frammentazione, rendere disponibile spazio su disco grazie alla compattazione delle pagine in base all'impostazione del fattore di riempimento esistente o specificata e riordinare le righe dell'indice in pagine contigue.</span><span class="sxs-lookup"><span data-stu-id="e72a5-111">This removes fragmentation, reclaims disk space by compacting the pages based on the specified or existing fill factor setting, and reorders the index rows in contiguous pages.</span></span> <span data-ttu-id="e72a5-112">Quando viene specificata la parola chiave ALL, tutti gli indici della tabella vengono eliminati e ricompilati in una singola transazione.</span><span class="sxs-lookup"><span data-stu-id="e72a5-112">When ALL is specified, all indexes on the table are dropped and rebuilt in a single transaction.</span></span> <span data-ttu-id="e72a5-113">La riorganizzazione di un indice richiede una quantità minima di risorse di sistema.</span><span class="sxs-lookup"><span data-stu-id="e72a5-113">Reorganizing an index uses minimal system resources.</span></span> <span data-ttu-id="e72a5-114">Questa operazione deframmenta il livello foglia di indici cluster e non cluster di tabelle e viste tramite il riordinamento fisico delle pagine al livello foglia in base all'ordine logico, da sinistra verso destra, dei nodi foglia.</span><span class="sxs-lookup"><span data-stu-id="e72a5-114">It defragments the leaf level of clustered and nonclustered indexes on tables and views by physically reordering the leaf-level pages to match the logical, left to right, order of the leaf nodes.</span></span> <span data-ttu-id="e72a5-115">La riorganizzazione consente inoltre di compattare le pagine di indice</span><span class="sxs-lookup"><span data-stu-id="e72a5-115">Reorganizing also compacts the index pages.</span></span> <span data-ttu-id="e72a5-116">in base al valore del fattore di riempimento esistente.</span><span class="sxs-lookup"><span data-stu-id="e72a5-116">Compaction is based on the existing fill factor value.</span></span>  
  
 <span data-ttu-id="e72a5-117">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="e72a5-117">**In This Topic**</span></span>  
  
-   <span data-ttu-id="e72a5-118">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="e72a5-118">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="e72a5-119">Rilevamento della frammentazione</span><span class="sxs-lookup"><span data-stu-id="e72a5-119">Detecting Fragmentation</span></span>](#Fragmentation)  
  
     [<span data-ttu-id="e72a5-120">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="e72a5-120">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="e72a5-121">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="e72a5-121">Security</span></span>](#Security)  
  
-   <span data-ttu-id="e72a5-122">**Per controllare la frammentazione di un indice usando:**</span><span class="sxs-lookup"><span data-stu-id="e72a5-122">**To check the fragmentation of an index, using:**</span></span>  
  
     [<span data-ttu-id="e72a5-123">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e72a5-123">SQL Server Management Studio</span></span>](#SSMSProcedureFrag)  
  
     [<span data-ttu-id="e72a5-124">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e72a5-124">Transact-SQL</span></span>](#TsqlProcedureFrag)  
  
-   <span data-ttu-id="e72a5-125">**Per riorganizzare o ricompilare un indice usando:**</span><span class="sxs-lookup"><span data-stu-id="e72a5-125">**To reorganize or rebuild an index, using:**</span></span>  
  
     [<span data-ttu-id="e72a5-126">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e72a5-126">SQL Server Management Studio</span></span>](#SSMSProcedureReorg)  
  
     [<span data-ttu-id="e72a5-127">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e72a5-127">Transact-SQL</span></span>](#TsqlProcedureReorg)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="e72a5-128">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="e72a5-128">Before You Begin</span></span>  
  
###  <a name="detecting-fragmentation"></a><a name="Fragmentation"></a><span data-ttu-id="e72a5-129">Rilevamento della frammentazione</span><span class="sxs-lookup"><span data-stu-id="e72a5-129">Detecting Fragmentation</span></span>  
 <span data-ttu-id="e72a5-130">Il primo passaggio per decidere il metodo di deframmentazione da usare consiste nell'eseguire un'analisi dell'indice per determinare il grado di frammentazione.</span><span class="sxs-lookup"><span data-stu-id="e72a5-130">The first step in deciding which defragmentation method to use is to analyze the index to determine the degree of fragmentation.</span></span> <span data-ttu-id="e72a5-131">La funzione di sistema [sys.dm_db_index_physical_stats](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-index-physical-stats-transact-sql)consente di rilevare la frammentazione in un indice specifico, in tutti gli indici di una tabella o vista indicizzata, in tutti gli indici di un database o in tutti gli indici di tutti i database.</span><span class="sxs-lookup"><span data-stu-id="e72a5-131">By using the system function [sys.dm_db_index_physical_stats](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-index-physical-stats-transact-sql), you can detect fragmentation in a specific index, all indexes on a table or indexed view, all indexes in a database, or all indexes in all databases.</span></span> <span data-ttu-id="e72a5-132">Per gli indici partizionati, **sys.dm_db_index_physical_stats** fornisce anche informazioni sulla frammentazione per ogni partizione.</span><span class="sxs-lookup"><span data-stu-id="e72a5-132">For partitioned indexes, **sys.dm_db_index_physical_stats** also provides fragmentation information for each partition.</span></span>  
  
 <span data-ttu-id="e72a5-133">Il set di risultati restituito dalla funzione **sys.dm_db_index_physical_stats** include le colonne seguenti.</span><span class="sxs-lookup"><span data-stu-id="e72a5-133">The result set returned by the **sys.dm_db_index_physical_stats** function includes the following columns.</span></span>  
  
|<span data-ttu-id="e72a5-134">Colonna</span><span class="sxs-lookup"><span data-stu-id="e72a5-134">Column</span></span>|<span data-ttu-id="e72a5-135">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e72a5-135">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="e72a5-136">**avg_fragmentation_in_percent**</span><span class="sxs-lookup"><span data-stu-id="e72a5-136">**avg_fragmentation_in_percent**</span></span>|<span data-ttu-id="e72a5-137">Percentuale di frammentazione logica (pagine non ordinate nell'indice).</span><span class="sxs-lookup"><span data-stu-id="e72a5-137">The percent of logical fragmentation (out-of-order pages in the index).</span></span>|  
|<span data-ttu-id="e72a5-138">**fragment_count**</span><span class="sxs-lookup"><span data-stu-id="e72a5-138">**fragment_count**</span></span>|<span data-ttu-id="e72a5-139">Numero di frammenti (pagine foglia fisicamente consecutive) nell'indice.</span><span class="sxs-lookup"><span data-stu-id="e72a5-139">The number of fragments (physically consecutive leaf pages) in the index.</span></span>|  
|<span data-ttu-id="e72a5-140">**avg_fragment_size_in_pages**</span><span class="sxs-lookup"><span data-stu-id="e72a5-140">**avg_fragment_size_in_pages**</span></span>|<span data-ttu-id="e72a5-141">Numero medio di pagine in un frammento di un indice.</span><span class="sxs-lookup"><span data-stu-id="e72a5-141">Average number of pages in one fragment in an index.</span></span>|  
  
 <span data-ttu-id="e72a5-142">Una volta noto il grado di frammentazione, usare la tabella seguente per determinare il metodo migliore per la correzione della frammentazione.</span><span class="sxs-lookup"><span data-stu-id="e72a5-142">After the degree of fragmentation is known, use the following table to determine the best method to correct the fragmentation.</span></span>  
  
|<span data-ttu-id="e72a5-143">Valore di**avg_fragmentation_in_percent**</span><span class="sxs-lookup"><span data-stu-id="e72a5-143">**avg_fragmentation_in_percent** value</span></span>|<span data-ttu-id="e72a5-144">Istruzione correttiva</span><span class="sxs-lookup"><span data-stu-id="e72a5-144">Corrective statement</span></span>|  
|-----------------------------------------------|--------------------------|  
|<span data-ttu-id="e72a5-145">> 5% e \< = 30%</span><span class="sxs-lookup"><span data-stu-id="e72a5-145">> 5% and \< = 30%</span></span>|<span data-ttu-id="e72a5-146">ALTER INDEX REORGANIZE</span><span class="sxs-lookup"><span data-stu-id="e72a5-146">ALTER INDEX REORGANIZE</span></span>|  
|<span data-ttu-id="e72a5-147">> 30%</span><span class="sxs-lookup"><span data-stu-id="e72a5-147">> 30%</span></span>|<span data-ttu-id="e72a5-148">ALTER INDEX REBUILD WITH (ONLINE = ON) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="e72a5-148">ALTER INDEX REBUILD WITH (ONLINE = ON) <sup>1</sup></span></span>|

<span data-ttu-id="e72a5-149"><sup>1</sup> È possibile eseguire la ricompilazione di un indice online oppure offline.</span><span class="sxs-lookup"><span data-stu-id="e72a5-149"><sup>1</sup> Rebuilding an index can be executed online or offline.</span></span> <span data-ttu-id="e72a5-150">La riorganizzazione di un indice viene sempre eseguita online.</span><span class="sxs-lookup"><span data-stu-id="e72a5-150">Reorganizing an index is always executed online.</span></span> <span data-ttu-id="e72a5-151">Per ottenere una disponibilità simile a quella offerta dall'opzione di riorganizzazione è necessario ricompilare gli indici in modalità online.</span><span class="sxs-lookup"><span data-stu-id="e72a5-151">To achieve availability similar to the reorganize option, you should rebuild indexes online.</span></span>  
  
> [!TIP]
> <span data-ttu-id="e72a5-152">Questi valori costituiscono un'indicazione approssimativa per determinare il punto in cui passare da `ALTER INDEX REORGANIZE` a `ALTER INDEX REBUILD`.</span><span class="sxs-lookup"><span data-stu-id="e72a5-152">These values provide a rough guideline for determining the point at which you should switch between `ALTER INDEX REORGANIZE` and `ALTER INDEX REBUILD`.</span></span> <span data-ttu-id="e72a5-153">I valori effettivi, in realtà, variano da caso a caso.</span><span class="sxs-lookup"><span data-stu-id="e72a5-153">However, the actual values may vary from case to case.</span></span> <span data-ttu-id="e72a5-154">È importante riuscire a determinare la soglia migliore per l'ambiente in uso.</span><span class="sxs-lookup"><span data-stu-id="e72a5-154">It is important that you experiment to determine the best threshold for your environment.</span></span> <span data-ttu-id="e72a5-155">Se ad esempio un determinato indice viene usato principalmente per le operazioni di analisi, la rimozione della frammentazione può migliorare le prestazioni di tali operazioni.</span><span class="sxs-lookup"><span data-stu-id="e72a5-155">For example, if a given index is used mainly for scan operations, removing fragmentation can improve performance of these operations.</span></span> <span data-ttu-id="e72a5-156">Il vantaggio in termini di prestazioni è meno evidente per gli indici usati principalmente per le operazioni di ricerca.</span><span class="sxs-lookup"><span data-stu-id="e72a5-156">The performance benefit is less noticeable for indexes that are used primarily for seek operations.</span></span> <span data-ttu-id="e72a5-157">Analogamente, la rimozione della frammentazione in un heap (una tabella senza indici cluster) è particolarmente utile per le operazioni di analisi degli indici non cluster, ma ha un effetto ridotto nelle operazioni di ricerca.</span><span class="sxs-lookup"><span data-stu-id="e72a5-157">Similarly, removing fragmentation in a heap (a table with no clustered index) is especially useful for nonclustered index scan operations, but has little effect in lookup operations.</span></span>

<span data-ttu-id="e72a5-158">Non è in genere consigliabile usare questi comandi per livelli di frammentazione ridotti (inferiori al 5%), poiché i vantaggi offerti dalla rimozione di una frammentazione così limitata sono praticamente annullati dal costo della riorganizzazione o della ricompilazione dell'indice.</span><span class="sxs-lookup"><span data-stu-id="e72a5-158">Very low levels of fragmentation (less than 5 percent) should typically not be addressed by either of these commands, because the benefit from removing such a small amount of fragmentation is almost always vastly outweighed by the cost of reorganizing or rebuilding the index.</span></span> 

> [!NOTE]
> <span data-ttu-id="e72a5-159">La ricompilazione o la riorganizzazione degli indici di dimensioni ridotte spesso non riduce la frammentazione.</span><span class="sxs-lookup"><span data-stu-id="e72a5-159">Rebuilding or reorganizing small indexes often does not reduce fragmentation.</span></span> <span data-ttu-id="e72a5-160">Le pagine di indici di dimensioni ridotte vengono talvolta archiviate in extent misti.</span><span class="sxs-lookup"><span data-stu-id="e72a5-160">The pages of small indexes are sometimes stored on mixed extents.</span></span> <span data-ttu-id="e72a5-161">Poiché gli extent misti possono essere condivisi al massimo da otto oggetti, la frammentazione in un indice di dimensioni ridotte potrebbe non ridursi dopo la riorganizzazione o la ricompilazione dell'indice.</span><span class="sxs-lookup"><span data-stu-id="e72a5-161">Mixed extents are shared by up to eight objects, so the fragmentation in a small index might not be reduced after reorganizing or rebuilding it.</span></span>

### <a name="index-defragmentation-considerations"></a><span data-ttu-id="e72a5-162">Considerazioni sulla deframmentazione dell'indice</span><span class="sxs-lookup"><span data-stu-id="e72a5-162">Index defragmentation considerations</span></span>
<span data-ttu-id="e72a5-163">In determinate condizioni, la ricompilazione di un indice cluster ricreerà automaticamente tutti gli indici non cluster che fanno riferimento alla chiave di clustering, se è necessario modificare gli identificatori fisici o logici contenuti nei record degli indici non cluster.</span><span class="sxs-lookup"><span data-stu-id="e72a5-163">Under certain conditions, rebuilding a clustered index will automatically rebuild any nonclustered index that reference the clustering key, if the physical or logical identifiers contained in the nonclustered index records needs to change.</span></span>

<span data-ttu-id="e72a5-164">Scenari che forzano la ricompilazione automatica di tutti gli indici non cluster in una tabella:</span><span class="sxs-lookup"><span data-stu-id="e72a5-164">Scenarios that force all nonclustered indexes to be automatically rebuilt on a table:</span></span>

-  <span data-ttu-id="e72a5-165">Creazione di un indice cluster in una tabella</span><span class="sxs-lookup"><span data-stu-id="e72a5-165">Creating a clustered index on a table</span></span>
-  <span data-ttu-id="e72a5-166">Rimozione di un indice cluster, che causa l'archiviazione della tabella come heap</span><span class="sxs-lookup"><span data-stu-id="e72a5-166">Removing a clustered index, causing the table to be stored as a heap</span></span>
-  <span data-ttu-id="e72a5-167">Modifica della chiave di clustering per includere o escludere colonne</span><span class="sxs-lookup"><span data-stu-id="e72a5-167">Changing the clustering key to include or exclude columns</span></span>

<span data-ttu-id="e72a5-168">Scenari che non richiedono la ricompilazione automatica di tutti gli indici non cluster in una tabella:</span><span class="sxs-lookup"><span data-stu-id="e72a5-168">Scenarios that do not require all nonclustered indexes to be automatically rebuilt on a table:</span></span>

-  <span data-ttu-id="e72a5-169">Ricompilazione di un indice cluster univoco</span><span class="sxs-lookup"><span data-stu-id="e72a5-169">Rebuilding a unique clustered index</span></span>
-  <span data-ttu-id="e72a5-170">Ricompilazione di un indice cluster non univoco</span><span class="sxs-lookup"><span data-stu-id="e72a5-170">Rebuilding a non-unique clustered index</span></span>
-  <span data-ttu-id="e72a5-171">Modifica dello schema dell'indice, ad esempio tramite l'applicazione di uno schema di partizionamento a un indice cluster o lo spostamento dell'indice cluster in un filegroup diverso</span><span class="sxs-lookup"><span data-stu-id="e72a5-171">Changing the index schema, such as applying a partitioning scheme to a clustered index or moving the clustered index to a different filegroup</span></span>
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="e72a5-172">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="e72a5-172">Limitations and Restrictions</span></span>  
  
<span data-ttu-id="e72a5-173">Gli indici con più di 128 extent vengono ricompilati in due fasi separate, logica e fisica.</span><span class="sxs-lookup"><span data-stu-id="e72a5-173">Indexes with more than 128 extents are rebuilt in two separate phases: logical and physical.</span></span> <span data-ttu-id="e72a5-174">Nella fase logica, le unità di allocazione esistenti usate dall'indice vengono contrassegnate per la deallocazione, le righe di dati vengono copiate e ordinate, quindi spostate nelle nuove unità di allocazione create per archiviare l'indice ricompilato.</span><span class="sxs-lookup"><span data-stu-id="e72a5-174">In the logical phase, the existing allocation units used by the index are marked for deallocation, the data rows are copied and sorted, then moved to new allocation units created to store the rebuilt index.</span></span> <span data-ttu-id="e72a5-175">Nella fase fisica, le unità di allocazione precedentemente contrassegnate per la deallocazione vengono fisicamente eliminate nelle transazioni brevi eseguite in background e non richiedono molti blocchi.</span><span class="sxs-lookup"><span data-stu-id="e72a5-175">In the physical phase, the allocation units previously marked for deallocation are physically dropped in short transactions that happen in the background, and do not require many locks.</span></span> <span data-ttu-id="e72a5-176">Per altre informazioni sugli extent, vedere la [Guida all'architettura di pagine ed extent](https://docs.microsoft.com/sql/relational-databases/pages-and-extents-architecture-guide).</span><span class="sxs-lookup"><span data-stu-id="e72a5-176">For more information about extents, refer to the [Pages and Extents Architecture Guide](https://docs.microsoft.com/sql/relational-databases/pages-and-extents-architecture-guide).</span></span>

<span data-ttu-id="e72a5-177">L'istruzione `ALTER INDEX REORGANIZE` richiede che nel file di dati che include l'indice sia disponibile spazio, perché l'operazione può allocare solo pagine di lavoro temporanee nello stesso file, non in un altro file nel filegroup.</span><span class="sxs-lookup"><span data-stu-id="e72a5-177">The `ALTER INDEX REORGANIZE` statement requires the data file containing the index to have space available, because the operation can only allocate temporary work pages on the same file, not another file within the filegroup.</span></span> <span data-ttu-id="e72a5-178">Anche se nel filegroup possono essere disponibili pagine libere, è tuttavia possibile che l'utente incontri l'errore 1105: `Could not allocate space for object '###' in database '###' because the '###' filegroup is full. Create disk space by deleting unneeded files, dropping objects in the filegroup, adding additional files to the filegroup, or setting autogrowth on for existing files in the filegroup.`</span><span class="sxs-lookup"><span data-stu-id="e72a5-178">So although the filegroup might have free pages available, the user can still encounter error 1105: `Could not allocate space for object '###' in database '###' because the '###' filegroup is full. Create disk space by deleting unneeded files, dropping objects in the filegroup, adding additional files to the filegroup, or setting autogrowth on for existing files in the filegroup.`</span></span>

<span data-ttu-id="e72a5-179">La creazione e la ricompilazione di indici non allineati per una tabella con oltre 1000 partizioni sono possibili, ma non consigliate.</span><span class="sxs-lookup"><span data-stu-id="e72a5-179">Creating and rebuilding non-aligned indexes on a table with more than 1,000 partitions is possible, but is not recommended.</span></span> <span data-ttu-id="e72a5-180">Questo tipo di operazioni può causare riduzioni delle prestazioni e un eccessivo consumo della memoria.</span><span class="sxs-lookup"><span data-stu-id="e72a5-180">Doing so may cause degraded performance or excessive memory consumption during these operations.</span></span>

<span data-ttu-id="e72a5-181">Non è possibile riorganizzare o ricompilare indici contenuti in un filegroup offline o di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="e72a5-181">An index cannot be reorganized or rebuilt if the filegroup in which it is located is offline or set to read-only.</span></span> <span data-ttu-id="e72a5-182">Quando viene specificata la parola chiave `ALL` e uno o più indici si trovano in un filegroup offline o di sola lettura, l'istruzione ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="e72a5-182">When the keyword `ALL` is specified and one or more indexes are in an offline or read-only filegroup, the statement fails.</span></span>
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="e72a5-183">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="e72a5-183">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="e72a5-184">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="e72a5-184">Permissions</span></span>  
 <span data-ttu-id="e72a5-185">È richiesta l'autorizzazione `ALTER` per la tabella o la vista.</span><span class="sxs-lookup"><span data-stu-id="e72a5-185">Requires `ALTER` permission on the table or view.</span></span> <span data-ttu-id="e72a5-186">L'utente deve essere un membro del ruolo predefinito del server **sysadmin** o dei ruoli predefiniti del database **db_ddladmin** e **db_owner** .</span><span class="sxs-lookup"><span data-stu-id="e72a5-186">User must be a member of the **sysadmin** fixed server role or the **db_ddladmin** and **db_owner** fixed database roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedureFrag"></a> <span data-ttu-id="e72a5-187">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e72a5-187">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-check-the-fragmentation-of-an-index"></a><span data-ttu-id="e72a5-188">Per controllare la frammentazione di un indice</span><span class="sxs-lookup"><span data-stu-id="e72a5-188">To check the fragmentation of an index</span></span>  
  
1.  <span data-ttu-id="e72a5-189">In Esplora oggetti espandere il database contenente la tabella in cui si desidera controllare la frammentazione di un indice.</span><span class="sxs-lookup"><span data-stu-id="e72a5-189">In Object Explorer, Expand the database that contains the table on which you want to check an index's fragmentation.</span></span>  
  
2.  <span data-ttu-id="e72a5-190">Espandere la cartella **Tabelle** .</span><span class="sxs-lookup"><span data-stu-id="e72a5-190">Expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="e72a5-191">Espandere la tabella in cui si desidera controllare la frammentazione di un indice.</span><span class="sxs-lookup"><span data-stu-id="e72a5-191">Expand the table on which you want to check an index's fragmentation.</span></span>  
  
4.  <span data-ttu-id="e72a5-192">Espandere la cartella **Indici** .</span><span class="sxs-lookup"><span data-stu-id="e72a5-192">Expand the **Indexes** folder.</span></span>  
  
5.  <span data-ttu-id="e72a5-193">Fare clic con il pulsante destro del mouse sull'indice di cui si vuole controllare la frammentazione e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="e72a5-193">Right-click the index of which you want to check the fragmentation and select **Properties**.</span></span>  
  
6.  <span data-ttu-id="e72a5-194">In **Selezione pagina**selezionare **Frammentazione**.</span><span class="sxs-lookup"><span data-stu-id="e72a5-194">Under **Select a page**, select **Fragmentation**.</span></span>  
  
     <span data-ttu-id="e72a5-195">Le informazioni seguenti sono disponibili nella pagina **Frammentazione** :</span><span class="sxs-lookup"><span data-stu-id="e72a5-195">The following information is available on the **Fragmentation** page:</span></span>  
  
     <span data-ttu-id="e72a5-196">**Livello di riempimento pagina**</span><span class="sxs-lookup"><span data-stu-id="e72a5-196">**Page fullness**</span></span>  
     <span data-ttu-id="e72a5-197">Indica il livello medio di riempimento delle pagine di indice, espresso come percentuale.</span><span class="sxs-lookup"><span data-stu-id="e72a5-197">Indicates average fullness of the index pages, as a percentage.</span></span> <span data-ttu-id="e72a5-198">Il valore 100% indica che le pagine di indice sono completamente piene.</span><span class="sxs-lookup"><span data-stu-id="e72a5-198">100% means the index pages are completely full.</span></span> <span data-ttu-id="e72a5-199">Il valore 50% indica che ogni pagina di indice è piena all'incirca per metà.</span><span class="sxs-lookup"><span data-stu-id="e72a5-199">50% means that, on average, each index page is half full.</span></span>  
  
     <span data-ttu-id="e72a5-200">**Frammentazione totale**</span><span class="sxs-lookup"><span data-stu-id="e72a5-200">**Total fragmentation**</span></span>  
     <span data-ttu-id="e72a5-201">Percentuale di frammentazione logica.</span><span class="sxs-lookup"><span data-stu-id="e72a5-201">The logical fragmentation percentage.</span></span> <span data-ttu-id="e72a5-202">Indica il numero di pagine di un indice che non sono archiviate in ordine.</span><span class="sxs-lookup"><span data-stu-id="e72a5-202">This indicates the number of pages in an index that are not stored in order.</span></span>  
  
     <span data-ttu-id="e72a5-203">**Dimensioni medie delle righe**</span><span class="sxs-lookup"><span data-stu-id="e72a5-203">**Average row size**</span></span>  
     <span data-ttu-id="e72a5-204">Dimensioni medie di una riga al livello foglia.</span><span class="sxs-lookup"><span data-stu-id="e72a5-204">The average size of a leaf level row.</span></span>  
  
     <span data-ttu-id="e72a5-205">**Depth**</span><span class="sxs-lookup"><span data-stu-id="e72a5-205">**Depth**</span></span>  
     <span data-ttu-id="e72a5-206">Numero di livelli dell'indice, compreso il livello foglia.</span><span class="sxs-lookup"><span data-stu-id="e72a5-206">The number of levels in the index, including the leaf level.</span></span>  
  
     <span data-ttu-id="e72a5-207">**Record inoltrati**</span><span class="sxs-lookup"><span data-stu-id="e72a5-207">**Forwarded records**</span></span>  
     <span data-ttu-id="e72a5-208">Numero di record in un heap che hanno inoltrato puntatori a un altro percorso dei dati.</span><span class="sxs-lookup"><span data-stu-id="e72a5-208">The number of records in a heap that have forward pointers to another data location.</span></span> <span data-ttu-id="e72a5-209">Questo stato si verifica durante un aggiornamento, nel caso in cui non vi sia spazio sufficiente per archiviare la riga nel percorso originale.</span><span class="sxs-lookup"><span data-stu-id="e72a5-209">(This state occurs during an update, when there is not enough room to store the new row in the original location.)</span></span>  
  
     <span data-ttu-id="e72a5-210">**Righe fantasma**</span><span class="sxs-lookup"><span data-stu-id="e72a5-210">**Ghost rows**</span></span>  
     <span data-ttu-id="e72a5-211">Numero di righe contrassegnate come eliminate ma non ancora rimosse.</span><span class="sxs-lookup"><span data-stu-id="e72a5-211">The number of rows that are marked as deleted but not yet removed.</span></span> <span data-ttu-id="e72a5-212">Queste righe verranno rimosse da un thread di pulitura nel momento in cui il server non è occupato.</span><span class="sxs-lookup"><span data-stu-id="e72a5-212">These rows will be removed by a clean-up thread, when the server is not busy.</span></span> <span data-ttu-id="e72a5-213">Questo valore non comprende le righe mantenute a causa di una transazione di isolamento dello snapshot in attesa.</span><span class="sxs-lookup"><span data-stu-id="e72a5-213">This value does not include rows that are being retained due to an outstanding snapshot isolation transaction.</span></span>  
  
     <span data-ttu-id="e72a5-214">**Tipo di indice**</span><span class="sxs-lookup"><span data-stu-id="e72a5-214">**Index type**</span></span>  
     <span data-ttu-id="e72a5-215">Tipo di indice.</span><span class="sxs-lookup"><span data-stu-id="e72a5-215">The type of index.</span></span> <span data-ttu-id="e72a5-216">I valori possibili sono **Indice cluster**, **Indice non cluster**e **XML primario**.</span><span class="sxs-lookup"><span data-stu-id="e72a5-216">Possible values are **Clustered index**, **Nonclustered index**, and **Primary XML**.</span></span> <span data-ttu-id="e72a5-217">È inoltre possibile archiviare le tabelle come heap (senza indici), ma in questo caso non sarà possibile aprire la pagina Proprietà indice.</span><span class="sxs-lookup"><span data-stu-id="e72a5-217">Tables can also be stored as a heap (without indexes), but then this Index Properties page cannot be opened.</span></span>  
  
     <span data-ttu-id="e72a5-218">**Righe al livello foglia**</span><span class="sxs-lookup"><span data-stu-id="e72a5-218">**Leaf-level rows**</span></span>  
     <span data-ttu-id="e72a5-219">Numero di righe al livello foglia.</span><span class="sxs-lookup"><span data-stu-id="e72a5-219">The number of leaf level rows.</span></span>  
  
     <span data-ttu-id="e72a5-220">**Dimensioni massime righe**</span><span class="sxs-lookup"><span data-stu-id="e72a5-220">**Maximum row size**</span></span>  
     <span data-ttu-id="e72a5-221">Dimensioni massime delle righe al livello foglia.</span><span class="sxs-lookup"><span data-stu-id="e72a5-221">The maximum leaf-level row size.</span></span>  
  
     <span data-ttu-id="e72a5-222">**Dimensioni minime righe**</span><span class="sxs-lookup"><span data-stu-id="e72a5-222">**Minimum row size**</span></span>  
     <span data-ttu-id="e72a5-223">Dimensioni minime delle righe al livello foglia.</span><span class="sxs-lookup"><span data-stu-id="e72a5-223">The minimum leaf-level row size.</span></span>  
  
     <span data-ttu-id="e72a5-224">**Pagine**</span><span class="sxs-lookup"><span data-stu-id="e72a5-224">**Pages**</span></span>  
     <span data-ttu-id="e72a5-225">Numero totale di pagine di dati.</span><span class="sxs-lookup"><span data-stu-id="e72a5-225">The total number of data pages.</span></span>  
  
     <span data-ttu-id="e72a5-226">**ID partizione**</span><span class="sxs-lookup"><span data-stu-id="e72a5-226">**Partition ID**</span></span>  
     <span data-ttu-id="e72a5-227">ID partizione dell'albero B contenente l'indice.</span><span class="sxs-lookup"><span data-stu-id="e72a5-227">The partition ID of the b-tree containing the index.</span></span>  
  
     <span data-ttu-id="e72a5-228">**Righe fantasma versione**</span><span class="sxs-lookup"><span data-stu-id="e72a5-228">**Version ghost rows**</span></span>  
     <span data-ttu-id="e72a5-229">Numero di record fantasma mantenuti a causa di una transazione di isolamento dello snapshot in attesa.</span><span class="sxs-lookup"><span data-stu-id="e72a5-229">The number of ghost records that are being retained due to an outstanding snapshot isolation transaction.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedureFrag"></a> <span data-ttu-id="e72a5-230">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e72a5-230">Using Transact-SQL</span></span>  
  
#### <a name="to-check-the-fragmentation-of-an-index"></a><span data-ttu-id="e72a5-231">Per controllare la frammentazione di un indice</span><span class="sxs-lookup"><span data-stu-id="e72a5-231">To check the fragmentation of an index</span></span>  
  
1.  <span data-ttu-id="e72a5-232">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e72a5-232">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="e72a5-233">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="e72a5-233">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="e72a5-234">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="e72a5-234">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Find the average fragmentation percentage of all indexes  
    -- in the HumanResources.Employee table.   
    SELECT a.index_id, name, avg_fragmentation_in_percent  
    FROM sys.dm_db_index_physical_stats (DB_ID(N'AdventureWorks2012'), OBJECT_ID(N'HumanResources.Employee'), NULL, NULL, NULL) AS a  
        JOIN sys.indexes AS b ON a.object_id = b.object_id AND a.index_id = b.index_id;   
    GO  
    ```  
  
     <span data-ttu-id="e72a5-235">L'istruzione potrebbe restituire un set di risultati simile al seguente.</span><span class="sxs-lookup"><span data-stu-id="e72a5-235">The statement above might return a result set similar to the following.</span></span>  
  
    ```  
    index_id    name                                                  avg_fragmentation_in_percent  
    ----------- ----------------------------------------------------- ----------------------------  
    1           PK_Employee_BusinessEntityID                          0  
    2           IX_Employee_OrganizationalNode                        0  
    3           IX_Employee_OrganizationalLevel_OrganizationalNode    0  
    5           AK_Employee_LoginID                                   66.6666666666667  
    6           AK_Employee_NationalIDNumber                          50  
    7           AK_Employee_rowguid                                   0  
  
    (6 row(s) affected)  
    ```  
  
 <span data-ttu-id="e72a5-236">Per ulteriori informazioni, vedere [sys. dm_db_index_physical_stats &#40;&#41;Transact-SQL ](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-index-physical-stats-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e72a5-236">For more information, see  [sys.dm_db_index_physical_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-index-physical-stats-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedureReorg"></a> <span data-ttu-id="e72a5-237">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e72a5-237">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-reorganize-or-rebuild-an-index"></a><span data-ttu-id="e72a5-238">Per riorganizzare o ricompilare un indice</span><span class="sxs-lookup"><span data-stu-id="e72a5-238">To reorganize or rebuild an index</span></span>  
  
1.  <span data-ttu-id="e72a5-239">In Esplora oggetti espandere il database che contiene la tabella in cui si desidera riorganizzare un indice.</span><span class="sxs-lookup"><span data-stu-id="e72a5-239">In Object Explorer, Expand the database that contains the table on which you want to reorganize an index.</span></span>  
  
2.  <span data-ttu-id="e72a5-240">Espandere la cartella **Tabelle** .</span><span class="sxs-lookup"><span data-stu-id="e72a5-240">Expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="e72a5-241">Espandere la tabella in cui si desidera riorganizzare un indice.</span><span class="sxs-lookup"><span data-stu-id="e72a5-241">Expand the table on which you want to reorganize an index.</span></span>  
  
4.  <span data-ttu-id="e72a5-242">Espandere la cartella **Indici** .</span><span class="sxs-lookup"><span data-stu-id="e72a5-242">Expand the **Indexes** folder.</span></span>  
  
5.  <span data-ttu-id="e72a5-243">Fare clic con il pulsante destro del mouse sull'indice che si vuole riorganizzare e scegliere **Riorganizza**.</span><span class="sxs-lookup"><span data-stu-id="e72a5-243">Right-click the index you want to reorganize and select **Reorganize**.</span></span>  
  
6.  <span data-ttu-id="e72a5-244">Nella finestra di dialogo **Riorganizza indici** verificare che nella griglia **Indici da riorganizzare** sia presente l'indice corretto, quindi scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="e72a5-244">In the **Reorganize Indexes** dialog box, verify that the correct index is in the **Indexes to be reorganized** grid and click **OK**.</span></span>  
  
7.  <span data-ttu-id="e72a5-245">Selezionare la casella di controllo **Compatta dati di colonne LOB** per specificare che tutte le pagine che contengono dati LOB vengano compattate.</span><span class="sxs-lookup"><span data-stu-id="e72a5-245">Select the **Compact large object column data** check box to specify that all pages that contain large object (LOB) data are also compacted.</span></span>  
  
8.  <span data-ttu-id="e72a5-246">Scegliere **OK.**</span><span class="sxs-lookup"><span data-stu-id="e72a5-246">Click **OK.**</span></span>  
  
#### <a name="to-reorganize-all-indexes-in-a-table"></a><span data-ttu-id="e72a5-247">Per riorganizzare tutti gli indici in una tabella</span><span class="sxs-lookup"><span data-stu-id="e72a5-247">To reorganize all indexes in a table</span></span>  
  
1.  <span data-ttu-id="e72a5-248">In Esplora oggetti espandere il database che contiene la tabella in cui si desidera riorganizzare gli indici.</span><span class="sxs-lookup"><span data-stu-id="e72a5-248">In Object Explorer, Expand the database that contains the table on which you want to reorganize the indexes.</span></span>  
  
2.  <span data-ttu-id="e72a5-249">Espandere la cartella **Tabelle** .</span><span class="sxs-lookup"><span data-stu-id="e72a5-249">Expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="e72a5-250">Espandere la tabella in cui si desidera riorganizzare gli indici.</span><span class="sxs-lookup"><span data-stu-id="e72a5-250">Expand the table on which you want to reorganize the indexes.</span></span>  
  
4.  <span data-ttu-id="e72a5-251">Fare clic con il pulsante destro del mouse sulla cartella **Indici** e scegliere **Riorganizza tutto**.</span><span class="sxs-lookup"><span data-stu-id="e72a5-251">Right-click the **Indexes** folder and select **Reorganize All**.</span></span>  
  
5.  <span data-ttu-id="e72a5-252">Nella finestra di dialogo **Riorganizza indici** verificare che nella griglia **Indici da riorganizzare**siano presenti gli indici corretti.</span><span class="sxs-lookup"><span data-stu-id="e72a5-252">In the **Reorganize Indexes** dialog box, verify that the correct indexes are in the **Indexes to be reorganized**.</span></span> <span data-ttu-id="e72a5-253">Per rimuovere un indice dalla griglia **Indici da riorganizzare** , selezionare l'indice desiderato e premere CANC.</span><span class="sxs-lookup"><span data-stu-id="e72a5-253">To remove an index from the **Indexes to be reorganized** grid, select the index and then press the Delete key.</span></span>  
  
6.  <span data-ttu-id="e72a5-254">Selezionare la casella di controllo **Compatta dati di colonne LOB** per specificare che tutte le pagine che contengono dati LOB vengano compattate.</span><span class="sxs-lookup"><span data-stu-id="e72a5-254">Select the **Compact large object column data** check box to specify that all pages that contain large object (LOB) data are also compacted.</span></span>  
  
7.  <span data-ttu-id="e72a5-255">Scegliere **OK.**</span><span class="sxs-lookup"><span data-stu-id="e72a5-255">Click **OK.**</span></span>  
  
#### <a name="to-rebuild-an-index"></a><span data-ttu-id="e72a5-256">Per ricompilare un indice</span><span class="sxs-lookup"><span data-stu-id="e72a5-256">To rebuild an index</span></span>  
  
1.  <span data-ttu-id="e72a5-257">In Esplora oggetti espandere il database che contiene la tabella in cui si desidera riorganizzare un indice.</span><span class="sxs-lookup"><span data-stu-id="e72a5-257">In Object Explorer, Expand the database that contains the table on which you want to reorganize an index.</span></span>  
  
2.  <span data-ttu-id="e72a5-258">Espandere la cartella **Tabelle** .</span><span class="sxs-lookup"><span data-stu-id="e72a5-258">Expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="e72a5-259">Espandere la tabella in cui si desidera riorganizzare un indice.</span><span class="sxs-lookup"><span data-stu-id="e72a5-259">Expand the table on which you want to reorganize an index.</span></span>  
  
4.  <span data-ttu-id="e72a5-260">Espandere la cartella **Indici** .</span><span class="sxs-lookup"><span data-stu-id="e72a5-260">Expand the **Indexes** folder.</span></span>  
  
5.  <span data-ttu-id="e72a5-261">Fare clic con il pulsante destro del mouse sull'indice che si vuole riorganizzare e scegliere **Riorganizza**.</span><span class="sxs-lookup"><span data-stu-id="e72a5-261">Right-click the index you want to reorganize and select **Reorganize**.</span></span>  
  
6.  <span data-ttu-id="e72a5-262">Nella finestra di dialogo **Ricompila indici** verificare che nella griglia **Indici da ricompilare** sia presente l'indice corretto, quindi scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="e72a5-262">In the **Rebuild Indexes** dialog box, verify that the correct index is in the **Indexes to be rebuilt** grid and click **OK**.</span></span>  
  
7.  <span data-ttu-id="e72a5-263">Selezionare la casella di controllo **Compatta dati di colonne LOB** per specificare che tutte le pagine che contengono dati LOB vengano compattate.</span><span class="sxs-lookup"><span data-stu-id="e72a5-263">Select the **Compact large object column data** check box to specify that all pages that contain large object (LOB) data are also compacted.</span></span>  
  
8.  <span data-ttu-id="e72a5-264">Scegliere **OK.**</span><span class="sxs-lookup"><span data-stu-id="e72a5-264">Click **OK.**</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedureReorg"></a> <span data-ttu-id="e72a5-265">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e72a5-265">Using Transact-SQL</span></span>  
  
#### <a name="to-reorganize-a-defragmented-index"></a><span data-ttu-id="e72a5-266">Per riorganizzare un indice deframmentato</span><span class="sxs-lookup"><span data-stu-id="e72a5-266">To reorganize a defragmented index</span></span>  
  
1.  <span data-ttu-id="e72a5-267">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e72a5-267">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="e72a5-268">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="e72a5-268">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="e72a5-269">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="e72a5-269">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;   
    GO  
    -- Reorganize the IX_Employee_OrganizationalLevel_OrganizationalNode index on the HumanResources.Employee table.   
  
    ALTER INDEX IX_Employee_OrganizationalLevel_OrganizationalNode ON HumanResources.Employee  
    REORGANIZE ;   
    GO  
    ```  
  
#### <a name="to-reorganize-all-indexes-in-a-table"></a><span data-ttu-id="e72a5-270">Per riorganizzare tutti gli indici in una tabella</span><span class="sxs-lookup"><span data-stu-id="e72a5-270">To reorganize all indexes in a table</span></span>  
  
1.  <span data-ttu-id="e72a5-271">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e72a5-271">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="e72a5-272">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="e72a5-272">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="e72a5-273">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="e72a5-273">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;   
    GO  
    -- Reorganize all indexes on the HumanResources.Employee table.  
    ALTER INDEX ALL ON HumanResources.Employee  
    REORGANIZE ;   
    GO  
    ```  
  
#### <a name="to-rebuild-a-defragmented-index"></a><span data-ttu-id="e72a5-274">Per ricompilare un indice deframmentato</span><span class="sxs-lookup"><span data-stu-id="e72a5-274">To rebuild a defragmented index</span></span>  
  
1.  <span data-ttu-id="e72a5-275">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e72a5-275">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="e72a5-276">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="e72a5-276">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="e72a5-277">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="e72a5-277">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="e72a5-278">Nell'esempio viene ricompilato un solo indice nella tabella `Employee` .</span><span class="sxs-lookup"><span data-stu-id="e72a5-278">The example rebuilds a single index on the `Employee` table.</span></span>  
  
     [!code-sql[IndexDDL#AlterIndex1](../../snippets/tsql/SQL14/tsql/indexddl/transact-sql/alterindex.sql#alterindex1)]  
  
#### <a name="to-rebuild-all-indexes-in-a-table"></a><span data-ttu-id="e72a5-279">Per ricompilare tutti gli indici in una tabella</span><span class="sxs-lookup"><span data-stu-id="e72a5-279">To rebuild all indexes in a table</span></span>  
  
1.  <span data-ttu-id="e72a5-280">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e72a5-280">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="e72a5-281">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="e72a5-281">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="e72a5-282">Copiare e incollare l'esempio seguente nella finestra Query. Nell'esempio viene specificata la parola chiave `ALL`.</span><span class="sxs-lookup"><span data-stu-id="e72a5-282">Copy and paste the following example into the query The example specifies the keyword `ALL`.</span></span> <span data-ttu-id="e72a5-283">In questo modo vengono ricompilati tutti gli indici associati alla tabella.</span><span class="sxs-lookup"><span data-stu-id="e72a5-283">This rebuilds all indexes associated with the table.</span></span> <span data-ttu-id="e72a5-284">Vengono inoltre specificate tre opzioni.</span><span class="sxs-lookup"><span data-stu-id="e72a5-284">Three options are specified.</span></span>  
  
     [!code-sql[IndexDDL#AlterIndex2](../../snippets/tsql/SQL14/tsql/indexddl/transact-sql/alterindex.sql#alterindex2)]  
  
 <span data-ttu-id="e72a5-285">Per altre informazioni, vedere [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e72a5-285">For more information, see [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e72a5-286">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e72a5-286">See Also</span></span>  
 [<span data-ttu-id="e72a5-287">Procedure consigliate relative alla deframmentazione degli indici in Microsoft SQL Server 2000</span><span class="sxs-lookup"><span data-stu-id="e72a5-287">Microsoft SQL Server 2000 Index Defragmentation Best Practices</span></span>](https://technet.microsoft.com/library/cc966523.aspx)  
  
  
