---
title: Linee guida per l'uso di indici nelle tabelle ottimizzate per la memoria | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
helpviewer_keywords:
- hash indexes
ms.assetid: 16ef63a4-367a-46ac-917d-9eebc81ab29b
author: stevestein
ms.author: sstein
ms.openlocfilehash: f00d643088634c918eb626917eae64a001ce3678
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716596"
---
# <a name="guidelines-for-using-indexes-on-memory-optimized-tables"></a><span data-ttu-id="b2191-102">Linee guida per l'utilizzo di indici nelle tabelle con ottimizzazione per la memoria</span><span class="sxs-lookup"><span data-stu-id="b2191-102">Guidelines for Using Indexes on Memory-Optimized Tables</span></span>
  <span data-ttu-id="b2191-103">Gli indici vengono utilizzati per accedere in modo efficiente ai dati nelle tabelle di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b2191-103">Indexes are used for efficiently accessing data in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] tables.</span></span> <span data-ttu-id="b2191-104">La definizione degli indici corretti può migliorare notevolmente le prestazioni delle query.</span><span class="sxs-lookup"><span data-stu-id="b2191-104">Specifying the right indexes can dramatically improve query performance.</span></span> <span data-ttu-id="b2191-105">Si consideri, ad esempio, la query riportata di seguito:</span><span class="sxs-lookup"><span data-stu-id="b2191-105">Consider, for example, the query:</span></span>  
  
```sql  
SELECT c1, c2 FROM t WHERE c1 = 1;  
```  
  
 <span data-ttu-id="b2191-106">Se non è presente alcun indice sulla colonna c1, in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] dovrà essere analizzata l'intera tabella t, quindi dovranno essere filtrate le righe che soddisfano la condizione c1=1.</span><span class="sxs-lookup"><span data-stu-id="b2191-106">If there is no index on column c1, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] will need to scan the entire table t, and then filter on the rows that satisfy the condition c1=1.</span></span> <span data-ttu-id="b2191-107">Se tuttavia t include un indice sulla colonna c1, in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] può essere eseguita direttamente la ricerca del valore 1 e possono essere recuperate le righe.</span><span class="sxs-lookup"><span data-stu-id="b2191-107">However, if t has an index on column c1, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] can seek directly on the value 1 and retrieve the rows.</span></span>  
  
 <span data-ttu-id="b2191-108">Quando si effettua la ricerca di record con un valore specifico, o un intervallo di valori, per una o più colonne della tabella, in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] è possibile utilizzare un indice per tali colonne in modo da individuare rapidamente i record corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="b2191-108">When searching for records that have a specific value, or range of values, for one or more columns in the table, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] can use an index on those columns to quickly locate the corresponding records.</span></span> <span data-ttu-id="b2191-109">Gli indici costituiscono un vantaggio sia per le tabelle basate su disco che per quelle ottimizzate per la memoria.</span><span class="sxs-lookup"><span data-stu-id="b2191-109">Both disk-based and memory-optimized tables benefit from indexes.</span></span> <span data-ttu-id="b2191-110">Esistono tuttavia alcune differenze tra le strutture di indice, che è opportuno considerare quando si utilizzano tabelle ottimizzate per la memoria.</span><span class="sxs-lookup"><span data-stu-id="b2191-110">There are, however, certain differences between index structures that need to be considered when using memory-optimized tables.</span></span> <span data-ttu-id="b2191-111">Gli indici nelle tabelle ottimizzate per la memoria sono definiti indici ottimizzati per la memoria. Di seguito sono riportate alcune delle differenze principali:</span><span class="sxs-lookup"><span data-stu-id="b2191-111">(Indexes on memory-optimized tables are referred to as memory-optimized indexes.) Some of the key differences are:</span></span>  
  
-   <span data-ttu-id="b2191-112">Gli indici con ottimizzazione per la memoria devono essere creati con [CREATE TABLE &#40;&#41;Transact-SQL ](/sql/t-sql/statements/create-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b2191-112">Memory-optimized indexes must be created with [CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql).</span></span> <span data-ttu-id="b2191-113">Gli indici basati su disco possono essere creati con `CREATE TABLE` e `CREATE INDEX`.</span><span class="sxs-lookup"><span data-stu-id="b2191-113">Disk-based indexes can be created with `CREATE TABLE` and `CREATE INDEX`.</span></span>  
  
-   <span data-ttu-id="b2191-114">Gli indici con ottimizzazione per la memoria esistono solo in memoria.</span><span class="sxs-lookup"><span data-stu-id="b2191-114">Memory-optimized indexes exist only in memory.</span></span> <span data-ttu-id="b2191-115">Le strutture di indice non vengono salvate in modo permanente sul disco e le operazioni sugli indici vengono registrate nel log delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="b2191-115">Index structures are not persisted to disk and index operations are not logged in the transaction log.</span></span> <span data-ttu-id="b2191-116">La struttura di indice viene creata contemporaneamente alla creazione in memoria della tabella ottimizzata per la memoria, sia durante l'esecuzione di CREATE TABLE che durante l'avvio del database.</span><span class="sxs-lookup"><span data-stu-id="b2191-116">The index structure is created when the memory-optimized table is created in memory, both during CREATE TABLE and during database startup.</span></span>  
  
-   <span data-ttu-id="b2191-117">Gli indici con ottimizzazione per la memoria sono implicitamente di copertura,</span><span class="sxs-lookup"><span data-stu-id="b2191-117">Memory-optimized indexes are inherently covering.</span></span> <span data-ttu-id="b2191-118">ovvero tutte le colonne sono virtualmente incluse nell'indice e le ricerche tramite segnalibro non sono richieste per le tabelle ottimizzate per la memoria.</span><span class="sxs-lookup"><span data-stu-id="b2191-118">Covering means that all columns are virtually included in the index and bookmark lookups are not needed for memory-optimized tables.</span></span> <span data-ttu-id="b2191-119">Anziché un riferimento alla chiave primaria, gli indici ottimizzati per la memoria includono solo un puntatore alla memoria per la riga effettiva nella struttura dei dati della tabella.</span><span class="sxs-lookup"><span data-stu-id="b2191-119">Rather than a reference to the primary key, memory-optimized indexes simply contain a memory pointer to the actual row in the table data structure.</span></span>  
  
-   <span data-ttu-id="b2191-120">La frammentazione e il fattore di riempimento non si applicano agli indici ottimizzati per la memoria.</span><span class="sxs-lookup"><span data-stu-id="b2191-120">Fragmentation and fillfactor do not apply to memory-optimized indexes.</span></span> <span data-ttu-id="b2191-121">Negli indici basati su disco la frammentazione si riferisce alle pagine nell'albero B scritte su disco non in ordine.</span><span class="sxs-lookup"><span data-stu-id="b2191-121">In disk-based indexes, fragmentation refers to pages in the B-tree being written to disk out-of-order.</span></span> <span data-ttu-id="b2191-122">Gli indici con ottimizzazione per la memoria non vengono scritti sul disco o letti dal disco.</span><span class="sxs-lookup"><span data-stu-id="b2191-122">Memory-optimized indexes are not written to or read from disk.</span></span> <span data-ttu-id="b2191-123">Il fattore di riempimento negli indici ad albero B basati su disco indica il livello di riempimento delle strutture fisiche delle pagine con i dati effettivi.</span><span class="sxs-lookup"><span data-stu-id="b2191-123">Fillfactor in disk-based B-tree indexes refers to the degree to which the physical page structures are filled with actual data.</span></span> <span data-ttu-id="b2191-124">Per le strutture di indice ottimizzate per la memoria non sono previste pagine a dimensione fissa.</span><span class="sxs-lookup"><span data-stu-id="b2191-124">The memory-optimized index structures do not have fixed-size pages.</span></span>  
  
 <span data-ttu-id="b2191-125">Esistono due tipi di indici ottimizzati per la memoria:</span><span class="sxs-lookup"><span data-stu-id="b2191-125">There are two types of memory-optimized indexes:</span></span>  
  
-   <span data-ttu-id="b2191-126">Indici hash non cluster, concepiti per le ricerche di punti.</span><span class="sxs-lookup"><span data-stu-id="b2191-126">Nonclustered hash indexes, which are made for point lookups.</span></span> <span data-ttu-id="b2191-127">Per ulteriori informazioni sugli indici hash, vedere [hash Indexes](hash-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="b2191-127">For more information about hash indexes, see [Hash Indexes](hash-indexes.md).</span></span>  
  
-   <span data-ttu-id="b2191-128">Indici non cluster, concepiti per le analisi di intervalli e le analisi ordinate.</span><span class="sxs-lookup"><span data-stu-id="b2191-128">Nonclustered indexes, which are made for range scans and ordered scans.</span></span>  
  
 <span data-ttu-id="b2191-129">Con un indice hash l'accesso ai dati viene eseguito tramite una tabella hash in memoria.</span><span class="sxs-lookup"><span data-stu-id="b2191-129">With a hash index, data is accessed through an in-memory hash table.</span></span> <span data-ttu-id="b2191-130">Gli indici hash non includono pagine e hanno sempre una dimensione fissa.</span><span class="sxs-lookup"><span data-stu-id="b2191-130">Hash indexes do not have pages and are always of a fixed size.</span></span> <span data-ttu-id="b2191-131">Possono tuttavia includere bucket di hash vuoti, con la conseguente limitazione dello spazio inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="b2191-131">However, a hash index can have empty hash buckets, which result in limited wasted space.</span></span> <span data-ttu-id="b2191-132">I valori restituiti da una query che utilizza un indice hash non vengono ordinati.</span><span class="sxs-lookup"><span data-stu-id="b2191-132">The values returned from a query using a hash index are not sorted.</span></span> <span data-ttu-id="b2191-133">Gli indici hash sono ottimizzati per le ricerche eseguite negli indici sui predicati di uguaglianza e supportano inoltre le analisi complete degli indici.</span><span class="sxs-lookup"><span data-stu-id="b2191-133">Hash indexes are optimized for index seeks on equality predicates and also support full index scans.</span></span>  
  
 <span data-ttu-id="b2191-134">Gli indici non cluster (non indici hash) supportano tutto ciò che è supportato dagli indici hash più le operazioni di ricerca sui predicati di disuguaglianza, come maggiore di o minore di, nonché l'ordinamento.</span><span class="sxs-lookup"><span data-stu-id="b2191-134">Nonclustered indexes (not hash indexes) support everything that hash indexes supports plus seek operations on inequality predicates such as greater than or less than, as well as sort order.</span></span> <span data-ttu-id="b2191-135">Le righe possono essere recuperate in base all'ordine specificato con la creazione dell'indice.</span><span class="sxs-lookup"><span data-stu-id="b2191-135">Rows can be retrieved according to the order specified with index creation.</span></span> <span data-ttu-id="b2191-136">Se l'ordinamento dell'indice corrisponde all'ordinamento richiesto per una determinata query, ad esempio se la chiave di indice corrisponde alla clausola ORDER BY, non è necessario ordinare le righe come parte dell'esecuzione della query.</span><span class="sxs-lookup"><span data-stu-id="b2191-136">If the sort order of the index matches the sort order required for a particular query, for example if the index key matches the ORDER BY clause, there is no need to sort the rows as part of query execution.</span></span> <span data-ttu-id="b2191-137">Gli indici non cluster con ottimizzazione per la memoria sono unidirezionali; non supportano il recupero delle righe in un ordinamento che è inverso all'ordinamento dell'indice.</span><span class="sxs-lookup"><span data-stu-id="b2191-137">Memory-optimized nonclustered indexes are unidirectional; they do not support retrieving rows in a sort order that is the reverse of the sort order of the index.</span></span> <span data-ttu-id="b2191-138">Ad esempio, per un indice specificato come (c1 ASC), non è possibile analizzare l'indice in ordine inverso, come (c1 DESC).</span><span class="sxs-lookup"><span data-stu-id="b2191-138">For example, for an index specified as (c1 ASC), it is not possible to scan the index in reverse order, as (c1 DESC).</span></span>  
  
 <span data-ttu-id="b2191-139">Ogni indice utilizza memoria.</span><span class="sxs-lookup"><span data-stu-id="b2191-139">Each index consumes memory.</span></span> <span data-ttu-id="b2191-140">Gli indici hash utilizzano una quantità di memoria fissa (una funzione del numero di bucket).</span><span class="sxs-lookup"><span data-stu-id="b2191-140">Hash indexes consume a fixed amount of memory, which is a function of the bucket count.</span></span> <span data-ttu-id="b2191-141">Per gli indici non cluster l'utilizzo della memoria è una funzione del conteggio delle righe e della dimensione delle colonne chiave di indice, con un overhead aggiuntivo a seconda del carico di lavoro.</span><span class="sxs-lookup"><span data-stu-id="b2191-141">For nonclustered indexes, memory consumption is a function of the row count and the size of the index key columns, with some additional overhead depending on the workload.</span></span> <span data-ttu-id="b2191-142">La memoria per gli indici ottimizzati per la memoria è in aggiunta ed è separata dalla memoria utilizzata per archiviare le righe nelle tabelle ottimizzate per la memoria.</span><span class="sxs-lookup"><span data-stu-id="b2191-142">Memory for memory-optimized indexes is in addition to and separate from the memory used to store rows in memory-optimized tables.</span></span>  
  
 <span data-ttu-id="b2191-143">I valori di chiave duplicati condividono sempre lo stesso bucket di hash.</span><span class="sxs-lookup"><span data-stu-id="b2191-143">Duplicate key values always share the same hash bucket.</span></span> <span data-ttu-id="b2191-144">Se un indice hash contiene molti valori di chiave duplicati, le lunghe catene di hash risultanti influiranno negativamente sulle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="b2191-144">If a hash index contains many duplicate key values, the resulting long hash chains will harm performance.</span></span> <span data-ttu-id="b2191-145">Le collisioni hash, che si verificano in un qualsiasi indice hash, ridurranno ulteriormente le prestazioni in questo scenario.</span><span class="sxs-lookup"><span data-stu-id="b2191-145">Hash collisions, which occur in any hash index, will further reduce performance in this scenario.</span></span> <span data-ttu-id="b2191-146">Per questo motivo, se il numero di chiavi di indice univoche è almeno 100 volte inferiore al numero di righe, è possibile ridurre il rischio di collisioni hash rendendo il numero di bucket molto più grande (almeno otto volte il numero di chiavi di indice univoche. per ulteriori informazioni, vedere [determinare il numero di bucket corretto per gli indici hash](../../2014/database-engine/determining-the-correct-bucket-count-for-hash-indexes.md) ) oppure eliminare completamente le collisioni hash usando un indice non cluster.</span><span class="sxs-lookup"><span data-stu-id="b2191-146">For that reason, if the number of unique index keys is at least 100 times smaller than the row count, you can reduce the risk of hash collisions by making the bucket count much larger (at least eight times the number of unique index keys; see [Determining the Correct Bucket Count for Hash Indexes](../../2014/database-engine/determining-the-correct-bucket-count-for-hash-indexes.md) for more information) or you can eliminate hash collisions entirely by using a nonclustered index.</span></span>  
  
## <a name="determining-which-indexes-to-use-for-a-memory-optimized-table"></a><span data-ttu-id="b2191-147">Determinazione degli indici da utilizzare per una tabella con ottimizzazione per la memoria</span><span class="sxs-lookup"><span data-stu-id="b2191-147">Determining Which Indexes to Use for a Memory-Optimized Table</span></span>  
 <span data-ttu-id="b2191-148">Ogni tabella ottimizzata per la memoria deve contenere almeno un indice.</span><span class="sxs-lookup"><span data-stu-id="b2191-148">Each memory-optimized table must have at least one index.</span></span> <span data-ttu-id="b2191-149">Si noti che con ogni vincolo PRIMARY KEY viene creato un indice in modo implicito,</span><span class="sxs-lookup"><span data-stu-id="b2191-149">Note that each PRIMARY KEY constraint implicitly creates an index.</span></span> <span data-ttu-id="b2191-150">pertanto se una tabella dispone di una chiave primaria, include un indice.</span><span class="sxs-lookup"><span data-stu-id="b2191-150">Therefore, if a table has a primary key, it has an index.</span></span> <span data-ttu-id="b2191-151">Una chiave primaria è un requisito per una tabella durevole ottimizzata per la memoria.</span><span class="sxs-lookup"><span data-stu-id="b2191-151">A primary key is a requirement for a durable memory-optimized table.</span></span>  
  
 <span data-ttu-id="b2191-152">Quando si esegue una query su una tabella ottimizzata per la memoria, gli indici hash offrono prestazioni migliori se la clausola del predicato contiene solo predicati di uguaglianza.</span><span class="sxs-lookup"><span data-stu-id="b2191-152">When querying a memory-optimized table, hash indexes perform better when the predicate clause contains only equality predicates.</span></span> <span data-ttu-id="b2191-153">Il predicato deve includere tutte le colonne nella chiave di indice hash.</span><span class="sxs-lookup"><span data-stu-id="b2191-153">The predicate must include all columns in the hash index key.</span></span> <span data-ttu-id="b2191-154">Se viene fornito un predicato di disuguaglianza, l'indice hash verrà ripristinato in un'analisi.</span><span class="sxs-lookup"><span data-stu-id="b2191-154">A hash index will revert to a scan given an inequality predicate.</span></span>  
  
 <span data-ttu-id="b2191-155">Una colonna di una tabella ottimizzata per la memoria può far parte sia di un indice hash che di un indice non cluster.</span><span class="sxs-lookup"><span data-stu-id="b2191-155">A column in a memory-optimized table can be part of both a hash index and a nonclustered index.</span></span>  
  
 <span data-ttu-id="b2191-156">Quando si esegue una query su una tabella ottimizzata per la memoria con predicati di disuguaglianza, gli indici non cluster offriranno prestazioni migliori rispetto agli indici hash non cluster.</span><span class="sxs-lookup"><span data-stu-id="b2191-156">When querying a memory-optimized table with inequality predicates, nonclustered indexes will perform better than nonclustered hash indexes.</span></span>  
  
 <span data-ttu-id="b2191-157">L'indice hash richiede una chiave per eseguire l'hashing ovvero eseguire ricerche nell'indice.</span><span class="sxs-lookup"><span data-stu-id="b2191-157">The hash index requires a key (to hash) to seek into the index.</span></span> <span data-ttu-id="b2191-158">Se una chiave di indice è costituita da due colonne e si specifica solo la prima colonna, in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] non sarà disponibile una chiave completa di cui eseguire l'hashing.</span><span class="sxs-lookup"><span data-stu-id="b2191-158">If an index key consists of two columns and you only provide the first column, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] does not have a complete key to hash.</span></span> <span data-ttu-id="b2191-159">Verrà pertanto generato un piano di query per l'analisi di indice.</span><span class="sxs-lookup"><span data-stu-id="b2191-159">This will result in an index scan query plan.</span></span> <span data-ttu-id="b2191-160">L'utilizzo determina le colonne da indicizzare.</span><span class="sxs-lookup"><span data-stu-id="b2191-160">Usage determines which columns should be indexed.</span></span>  
  
 <span data-ttu-id="b2191-161">Quando una colonna in un indice non cluster contiene lo stesso valore in molte righe, ovvero le colonne chiave dell'indice contengono molti valori duplicati, le prestazioni per le operazioni di aggiornamento, inserimento ed eliminazione potrebbero risultare ridotte.</span><span class="sxs-lookup"><span data-stu-id="b2191-161">When a column in a nonclustered index has the same value in many rows (index key columns have a lot of duplicate values), performance can degrade for updates, inserts, and deletions.</span></span>  <span data-ttu-id="b2191-162">Un modo per migliorare le prestazioni in questa situazione è aggiungere un'altra colonna nell'indice non cluster.</span><span class="sxs-lookup"><span data-stu-id="b2191-162">One way to improve performance in this situation is to add another column to the nonclustered index.</span></span>  
  
### <a name="operations-on-memory-optimized-and-disk-based-indexes"></a><span data-ttu-id="b2191-163">Operazioni sugli indici ottimizzati per la memoria e basati su disco.</span><span class="sxs-lookup"><span data-stu-id="b2191-163">Operations on memory-optimized and disk-based indexes.</span></span>  
  
|<span data-ttu-id="b2191-164">Operazione</span><span class="sxs-lookup"><span data-stu-id="b2191-164">Operation</span></span>|<span data-ttu-id="b2191-165">Indice hash non cluster con ottimizzazione per la memoria</span><span class="sxs-lookup"><span data-stu-id="b2191-165">Memory-optimized, nonclustered hash, index</span></span>|<span data-ttu-id="b2191-166">Indice non cluster con ottimizzazione per la memoria</span><span class="sxs-lookup"><span data-stu-id="b2191-166">Memory-optimized nonclustered index</span></span>|<span data-ttu-id="b2191-167">Indice basato su disco</span><span class="sxs-lookup"><span data-stu-id="b2191-167">Disk-based index</span></span>|  
|---------------|-------------------------------------------------|------------------------------------------|-----------------------|  
|<span data-ttu-id="b2191-168">Index Scan, recupera tutte le righe della tabella.</span><span class="sxs-lookup"><span data-stu-id="b2191-168">Index Scan, retrieve all table rows.</span></span>|<span data-ttu-id="b2191-169">Sì</span><span class="sxs-lookup"><span data-stu-id="b2191-169">Yes</span></span>|<span data-ttu-id="b2191-170">Sì</span><span class="sxs-lookup"><span data-stu-id="b2191-170">Yes</span></span>|<span data-ttu-id="b2191-171">Sì</span><span class="sxs-lookup"><span data-stu-id="b2191-171">Yes</span></span>|  
|<span data-ttu-id="b2191-172">Index Seek su predicati di uguaglianza (=).</span><span class="sxs-lookup"><span data-stu-id="b2191-172">Index seek on equality predicate(s) (=).</span></span>|<span data-ttu-id="b2191-173">Sì</span><span class="sxs-lookup"><span data-stu-id="b2191-173">Yes</span></span><br /><br /> <span data-ttu-id="b2191-174">(chiave completa necessaria)</span><span class="sxs-lookup"><span data-stu-id="b2191-174">(Full key required.)</span></span>|<span data-ttu-id="b2191-175">Sì <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="b2191-175">Yes <sup>1</sup></span></span>|<span data-ttu-id="b2191-176">Sì</span><span class="sxs-lookup"><span data-stu-id="b2191-176">Yes</span></span>|  
|<span data-ttu-id="b2191-177">Index Seek su predicati di disuguaglianza (>, <, \<=, > =, between).</span><span class="sxs-lookup"><span data-stu-id="b2191-177">Index seek on inequality predicates (>, <, \<=, >=, BETWEEN).</span></span>|<span data-ttu-id="b2191-178">No (risultati in un'analisi di indice)</span><span class="sxs-lookup"><span data-stu-id="b2191-178">No (results in an index scan)</span></span>|<span data-ttu-id="b2191-179">Sì <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="b2191-179">Yes <sup>1</sup></span></span>|<span data-ttu-id="b2191-180">Sì</span><span class="sxs-lookup"><span data-stu-id="b2191-180">Yes</span></span>|  
|<span data-ttu-id="b2191-181">Recupero di righe con un ordinamento corrispondente alla definizione dell'indice.</span><span class="sxs-lookup"><span data-stu-id="b2191-181">Retrieve rows in a sort-order matching the index definition.</span></span>|<span data-ttu-id="b2191-182">No</span><span class="sxs-lookup"><span data-stu-id="b2191-182">No</span></span>|<span data-ttu-id="b2191-183">Sì</span><span class="sxs-lookup"><span data-stu-id="b2191-183">Yes</span></span>|<span data-ttu-id="b2191-184">Sì</span><span class="sxs-lookup"><span data-stu-id="b2191-184">Yes</span></span>|  
|<span data-ttu-id="b2191-185">Recupero di righe con un ordinamento inverso alla definizione dell'indice.</span><span class="sxs-lookup"><span data-stu-id="b2191-185">Retrieve rows in a sort-order matching the reverse of the index definition.</span></span>|<span data-ttu-id="b2191-186">No</span><span class="sxs-lookup"><span data-stu-id="b2191-186">No</span></span>|<span data-ttu-id="b2191-187">No</span><span class="sxs-lookup"><span data-stu-id="b2191-187">No</span></span>|<span data-ttu-id="b2191-188">Sì</span><span class="sxs-lookup"><span data-stu-id="b2191-188">Yes</span></span>|  
  
 <span data-ttu-id="b2191-189">Nella tabella, Sì significa che l'indice può soddisfare la richiesta in modo appropriato e No significa che l'indice non può essere usato per soddisfare correttamente la richiesta.</span><span class="sxs-lookup"><span data-stu-id="b2191-189">In the table, Yes means that the index can adequately service the request and No means that the index cannot be used successfully to satisfy the request.</span></span>  
  
 <span data-ttu-id="b2191-190"><sup>1</sup> per un indice non cluster ottimizzato per la memoria, non è necessaria la chiave completa per eseguire una ricerca nell'indice.</span><span class="sxs-lookup"><span data-stu-id="b2191-190"><sup>1</sup> For a nonclustered memory-optimized index, the full key is not required to perform an index seek.</span></span> <span data-ttu-id="b2191-191">Tuttavia, se un valore di una colonna segue una colonna mancante, l'analisi verrà eseguita in base all'ordine delle colonne della chiave di indice.</span><span class="sxs-lookup"><span data-stu-id="b2191-191">Although, given the column order of the index key, a scan will occur if a value for a column comes after a missing column.</span></span>  
  
## <a name="index-count"></a><span data-ttu-id="b2191-192">Numero di indici</span><span class="sxs-lookup"><span data-stu-id="b2191-192">Index Count</span></span>  
 <span data-ttu-id="b2191-193">Per una tabella ottimizzata per la memoria possono essere presenti un massimo di 8 indici, incluso quello creato con la chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="b2191-193">A memory-optimized table can have up to 8 indexes, including the index created with the primary key.</span></span>  
  
 <span data-ttu-id="b2191-194">Per quanto riguarda il numero degli indici creati in una tabella ottimizzata per la memoria, considerare quanto indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="b2191-194">Regarding the number of indexes created on a memory-optimized table, consider the following:</span></span>  
  
-   <span data-ttu-id="b2191-195">Specificare gli indici necessari quando si crea la tabella.</span><span class="sxs-lookup"><span data-stu-id="b2191-195">Specify the indexes you need when you create the table.</span></span> <span data-ttu-id="b2191-196">Non è possibile creare un indice per una tabella ottimizzata per la memoria dopo è stata creata.</span><span class="sxs-lookup"><span data-stu-id="b2191-196">You cannot create an index for a memory-optimized table after the table is created.</span></span> <span data-ttu-id="b2191-197">Se si desidera aggiungere un indice per una tabella ottimizzata per la memoria, eliminarla e ricrearla.</span><span class="sxs-lookup"><span data-stu-id="b2191-197">If you want to add an index to a memory-optimized table, drop and recreate that table.</span></span>  
  
-   <span data-ttu-id="b2191-198">Evitare di creare un indice utilizzato raramente:</span><span class="sxs-lookup"><span data-stu-id="b2191-198">Do not create an index that you rarely use:</span></span>  
  
     <span data-ttu-id="b2191-199">Il processo di Garbage Collection funziona meglio se tutti gli indici della tabella vengono utilizzati di frequente.</span><span class="sxs-lookup"><span data-stu-id="b2191-199">Garbage collection works best if all indexes on the table are frequently used.</span></span> <span data-ttu-id="b2191-200">Gli indici utilizzati raramente possono causare un funzionamento non ottimale del sistema di Garbage Collection per le versioni di riga precedenti.</span><span class="sxs-lookup"><span data-stu-id="b2191-200">Rarely-used indexes may cause the garbage collection system to not perform optimally for old row versions.</span></span>  
  
## <a name="creating-a-memory-optimized-index-code-samples"></a><span data-ttu-id="b2191-201">Creazione di un indice con ottimizzazione per la memoria: esempi di codice</span><span class="sxs-lookup"><span data-stu-id="b2191-201">Creating a Memory-Optimized Index: Code Samples</span></span>  
 <span data-ttu-id="b2191-202">Indice hash a livello di colonna:</span><span class="sxs-lookup"><span data-stu-id="b2191-202">Column level hash index:</span></span>  
  
```sql  
CREATE TABLE t1   
   (c1 INT NOT NULL INDEX idx HASH WITH (BUCKET_COUNT = 100))   
   WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_ONLY)  
```  
  
 <span data-ttu-id="b2191-203">Indice hash a livello di tabella:</span><span class="sxs-lookup"><span data-stu-id="b2191-203">Table level hash index:</span></span>  
  
```sql  
CREATE TABLE t1_1   
   (c1 INT NOT NULL,   
   INDEX IDX HASH (c1) WITH (BUCKET_COUNT = 100))   
   WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_ONLY)  
```  
  
 <span data-ttu-id="b2191-204">Indice hash di chiave primaria a livello di colonna:</span><span class="sxs-lookup"><span data-stu-id="b2191-204">Column level primary key hash index:</span></span>  
  
```sql  
CREATE TABLE t2   
   (c1 INT NOT NULL PRIMARY KEY NONCLUSTERED HASH WITH (BUCKET_COUNT = 100))   
   WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_AND_DATA)  
```  
  
 <span data-ttu-id="b2191-205">Indice hash di chiave primaria a livello di tabella:</span><span class="sxs-lookup"><span data-stu-id="b2191-205">Table level primary key hash index:</span></span>  
  
```sql  
CREATE TABLE t2_2   
   (c1 INT NOT NULL,   
   PRIMARY KEY NONCLUSTERED HASH (c1) WITH (BUCKET_COUNT = 100))   
   WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_AND_DATA)  
```  
  
 <span data-ttu-id="b2191-206">Indice non cluster a livello di colonna:</span><span class="sxs-lookup"><span data-stu-id="b2191-206">Column level nonclustered index:</span></span>  
  
```sql  
CREATE TABLE t3   
   (c1 INT NOT NULL INDEX ID)   
   WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_ONLY)  
```  
  
 <span data-ttu-id="b2191-207">Indice non cluster a livello di tabella:</span><span class="sxs-lookup"><span data-stu-id="b2191-207">Table level nonclustered  index:</span></span>  
  
```sql  
CREATE TABLE t3_3   
   (c1 INT NOT NULL,   
   INDEX IDX NONCLUSTERED (c1))   
   WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_ONLY)  
```  
  
 <span data-ttu-id="b2191-208">Indice non cluster di chiave primaria a livello di colonna:</span><span class="sxs-lookup"><span data-stu-id="b2191-208">Column level primary key nonclustered  index:</span></span>  
  
```sql  
CREATE TABLE t4   
   (c1 INT NOT NULL PRIMARY KEY NONCLUSTERED)   
   WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_AND_DATA)  
```  
  
 <span data-ttu-id="b2191-209">Indice non cluster di chiave primaria a livello di tabella:</span><span class="sxs-lookup"><span data-stu-id="b2191-209">Table level primary key nonclustered index:</span></span>  
  
```sql  
CREATE TABLE t4_4   
   (c1 INT NOT NULL,   
   PRIMARY KEY NONCLUSTERED (c1))   
   WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_AND_DATA)  
```  
  
 <span data-ttu-id="b2191-210">Indice multicolonna definito dopo la definizione delle colonne:</span><span class="sxs-lookup"><span data-stu-id="b2191-210">Multicolumn index defined after columns are defined:</span></span>  
  
```sql  
create table t (  
       a int not null constraint ta primary key nonclustered,  
       b int not null,  
       c int not null,  
       d int not null,  
       index idx_t_b_c_d nonclustered (b, c asc, d desc)  
) with (memory_optimized = on, durability = SCHEMA_AND_DATA)  
go  
```  
  
## <a name="see-also"></a><span data-ttu-id="b2191-211">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b2191-211">See Also</span></span>  
 <span data-ttu-id="b2191-212">[Indici nelle tabelle ottimizzate per la memoria](../relational-databases/in-memory-oltp/memory-optimized-tables.md) </span><span class="sxs-lookup"><span data-stu-id="b2191-212">[Indexes on Memory-Optimized Tables](../relational-databases/in-memory-oltp/memory-optimized-tables.md) </span></span>  
 <span data-ttu-id="b2191-213">[Determinazione del numero di bucket corretto per gli indici hash](../../2014/database-engine/determining-the-correct-bucket-count-for-hash-indexes.md) </span><span class="sxs-lookup"><span data-stu-id="b2191-213">[Determining the Correct Bucket Count for Hash Indexes](../../2014/database-engine/determining-the-correct-bucket-count-for-hash-indexes.md) </span></span>  
 [<span data-ttu-id="b2191-214">Indici hash</span><span class="sxs-lookup"><span data-stu-id="b2191-214">Hash Indexes</span></span>](hash-indexes.md)  
  
  
