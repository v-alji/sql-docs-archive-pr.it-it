---
title: Stimare i requisiti di memoria delle tabelle con ottimizzazione per la memoria | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 5c5cc1fc-1fdf-4562-9443-272ad9ab5ba8
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 5c5218a96d3650cbae22501ab2794b1b553996b2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722824"
---
# <a name="estimate-memory-requirements-for-memory-optimized-tables"></a><span data-ttu-id="af99a-102">Stimare i requisiti di memoria delle tabelle con ottimizzazione per la memoria</span><span class="sxs-lookup"><span data-stu-id="af99a-102">Estimate Memory Requirements for Memory-Optimized Tables</span></span>
  <span data-ttu-id="af99a-103">Se si crea una nuova [!INCLUDE[hek_2](../../includes/hek-2-md.md)] tabella ottimizzata per la memoria o si esegue la migrazione di una tabella basata su disco esistente a una tabella ottimizzata per la memoria, è importante disporre di una stima ragionevole delle esigenze di memoria di ogni tabella, in modo da poter effettuare il provisioning del server con memoria sufficiente.</span><span class="sxs-lookup"><span data-stu-id="af99a-103">Whether you are creating a new [!INCLUDE[hek_2](../../includes/hek-2-md.md)] memory-optimized table or migrating an existing disk-based table to a memory-optimized table, it is important to have a reasonable estimate of each table's memory needs so you can provision the server with sufficient memory.</span></span> <span data-ttu-id="af99a-104">In questa sezione viene descritto come stimare la quantità di memoria necessaria per contenere i dati di una tabella ottimizzata per la memoria.</span><span class="sxs-lookup"><span data-stu-id="af99a-104">This section describes how to estimate the amount of memory that you need to hold data for a memory-optimized table.</span></span>  
  
 <span data-ttu-id="af99a-105">Se si prende in considerazione la migrazione da tabelle basate su disco a tabelle ottimizzate per la memoria, prima di procedere con questo argomento, vedere [Determinare se una tabella o una stored procedure deve essere trasferita a OLTP in memoria](determining-if-a-table-or-stored-procedure-should-be-ported-to-in-memory-oltp.md) per informazioni aggiuntive sulle tabelle più appropriate per la migrazione.</span><span class="sxs-lookup"><span data-stu-id="af99a-105">If you are contemplating migrating from disk-based tables to memory-optimized tables, before you proceed in this topic, see the topic [Determining if a Table or Stored Procedure Should Be Ported to In-Memory OLTP](determining-if-a-table-or-stored-procedure-should-be-ported-to-in-memory-oltp.md) for guidance on which tables are best to migrate.</span></span> <span data-ttu-id="af99a-106">Tutti gli argomenti disponibili in [Migrazione a OLTP in memoria](migrating-to-in-memory-oltp.md) offrono informazioni aggiuntive sulla migrazione da tabelle basate su disco a tabelle ottimizzate per la memoria.</span><span class="sxs-lookup"><span data-stu-id="af99a-106">All the topics under [Migrating to In-Memory OLTP](migrating-to-in-memory-oltp.md) provide guidance on migrating from disk-based to memory-optimized tables.</span></span>  
  
## <a name="sections-in-this-topic"></a><span data-ttu-id="af99a-107">Sezioni dell'argomento</span><span class="sxs-lookup"><span data-stu-id="af99a-107">Sections in this topic</span></span>  
  
-   [<span data-ttu-id="af99a-108">Esempio di tabella ottimizzata per la memoria</span><span class="sxs-lookup"><span data-stu-id="af99a-108">Example memory-optimized table</span></span>](#bkmk_ExampleTable)  
  
-   [<span data-ttu-id="af99a-109">Memoria per la tabella</span><span class="sxs-lookup"><span data-stu-id="af99a-109">Memory for the table</span></span>](#bkmk_MemoryForTable)  
  
-   [<span data-ttu-id="af99a-110">Memoria per gli indici</span><span class="sxs-lookup"><span data-stu-id="af99a-110">Memory for indexes</span></span>](#bkmk_IndexMeemory)  
  
-   [<span data-ttu-id="af99a-111">Memoria per il controllo delle versioni delle righe</span><span class="sxs-lookup"><span data-stu-id="af99a-111">Memory for row versioning</span></span>](#bkmk_MemoryForRowVersions)  
  
-   [<span data-ttu-id="af99a-112">Memoria per le variabili di tabella</span><span class="sxs-lookup"><span data-stu-id="af99a-112">Memory for table variables</span></span>](#bkmk_TableVariables)  
  
-   [<span data-ttu-id="af99a-113">Memoria in caso di aumento delle dimensioni</span><span class="sxs-lookup"><span data-stu-id="af99a-113">Memory for growth</span></span>](#bkmk_MemoryForGrowth)  
  
##  <a name="example-memory-optimized-table"></a><a name="bkmk_ExampleTable"></a> <span data-ttu-id="af99a-114">Esempio di tabella ottimizzata per la memoria</span><span class="sxs-lookup"><span data-stu-id="af99a-114">Example memory-optimized table</span></span>  
 <span data-ttu-id="af99a-115">Si consideri il seguente schema di tabella ottimizzata per la memoria:</span><span class="sxs-lookup"><span data-stu-id="af99a-115">Consider the following memory-optimized table schema:</span></span>  
  
```sql  
  
CREATE TABLE t_hk (  
col1 int NOT NULL PRIMARY KEY NONCLUSTERED,  
col2 int NOT NULL INDEX t1c2_index   
     HASH WITH (bucket_count = 5000000),  
col3 int NOT NULL INDEX t1c3_index   
     HASH WITH (bucket_count = 5000000),  
col4 int NOT NULL INDEX t1c4_index   
     HASH WITH (bucket_count = 5000000),  
col5 int NOT NULL INDEX t1c5_index NONCLUSTERED,  
col6 char (50) NOT NULL,  
col7 char (50) NOT NULL,   
col8 char (30) NOT NULL,   
col9 char (50) NOT NULL  
     WITH (memory_optimized = on)  
GO  
  
```  
  
 <span data-ttu-id="af99a-116">Utilizzando questo schema sarà possibile stabilire la memoria minima necessaria per questa tabella ottimizzata per la memoria.</span><span class="sxs-lookup"><span data-stu-id="af99a-116">Using this schema we will determine the minimum memory needed for this memory-optimized table.</span></span>  
  
##  <a name="memory-for-the-table"></a><a name="bkmk_MemoryForTable"></a> <span data-ttu-id="af99a-117">Memoria per la tabella</span><span class="sxs-lookup"><span data-stu-id="af99a-117">Memory for the table</span></span>  
 <span data-ttu-id="af99a-118">La riga di una tabella ottimizzata per la memoria è costituita da tre parti:</span><span class="sxs-lookup"><span data-stu-id="af99a-118">A memory-optimized table row is comprised of three parts:</span></span>  
  
-   <span data-ttu-id="af99a-119">**Timestamp** </span><span class="sxs-lookup"><span data-stu-id="af99a-119">**Timestamps** </span></span>  
    <span data-ttu-id="af99a-120">Intestazione di riga/timestamp = 24 byte.</span><span class="sxs-lookup"><span data-stu-id="af99a-120">Row header/timestamps = 24 bytes.</span></span>  
  
-   <span data-ttu-id="af99a-121">**Puntatori dell'indice** </span><span class="sxs-lookup"><span data-stu-id="af99a-121">**Index pointers** </span></span>  
    <span data-ttu-id="af99a-122">Per ogni indice hash nella tabella, a ogni riga è associato un puntatore all'indirizzo di 8 byte alla riga successiva nell'indice.</span><span class="sxs-lookup"><span data-stu-id="af99a-122">For each hash index in the table, each row has an 8-byte address pointer to the next row in the index.</span></span>  <span data-ttu-id="af99a-123">Poiché sono presenti 4 indici, tramite ogni riga vengono allocati 32 byte per i puntatori dell'indice (un puntatore di 8 byte per ogni indice).</span><span class="sxs-lookup"><span data-stu-id="af99a-123">Since there are 4 indexes, each row will allocate 32 bytes for index pointers (an 8 byte pointer for each index).</span></span>  
  
-   <span data-ttu-id="af99a-124">**Dati** </span><span class="sxs-lookup"><span data-stu-id="af99a-124">**Data** </span></span>  
    <span data-ttu-id="af99a-125">Le dimensioni della parte di dati della riga vengono determinate sommando le dimensioni di tipo per ogni colonna di dati.</span><span class="sxs-lookup"><span data-stu-id="af99a-125">The size of the data portion of the row is determined by summing the type size for each data column.</span></span>  <span data-ttu-id="af99a-126">Nella tabella di esempio sono contenuti cinque Integer a 4 byte, tre colonne di tipo carattere di 50 byte e una colonna di tipo carattere di 30 byte.</span><span class="sxs-lookup"><span data-stu-id="af99a-126">In our table we have five 4-byte integers, three 50-byte character columns, and one 30-byte character column.</span></span>  <span data-ttu-id="af99a-127">Pertanto la parte di dati di ogni riga è 4 + 4 + 4 + 4 + 4 + 50 + 50 + 30 + 50, vale a dire 200 byte.</span><span class="sxs-lookup"><span data-stu-id="af99a-127">Therefore the data portion of each row is 4 + 4 + 4 + 4 + 4 + 50 + 50 + 30 + 50 or 200 bytes.</span></span>  
  
 <span data-ttu-id="af99a-128">Di seguito è riportato un calcolo di dimensioni per 5.000.000 (5 milioni) di righe in una tabella ottimizzata per la memoria.</span><span class="sxs-lookup"><span data-stu-id="af99a-128">The following is a size computation for 5,000,000 (5 million) rows in a memory-optimized table.</span></span> <span data-ttu-id="af99a-129">La memoria totale utilizzata dalle righe di dati viene stimata come segue:</span><span class="sxs-lookup"><span data-stu-id="af99a-129">The total memory used by data rows is estimated as follows:</span></span>  
  
 <span data-ttu-id="af99a-130">**Memoria per le righe della tabella**</span><span class="sxs-lookup"><span data-stu-id="af99a-130">**Memory for the table's rows**</span></span>  
  
 <span data-ttu-id="af99a-131">Dai calcoli sopra riportati, le dimensioni di ogni riga della tabella ottimizzata per la memoria sono pari a 24 + 32 + 200, vale a dire 256 byte.</span><span class="sxs-lookup"><span data-stu-id="af99a-131">From the above calculations, the size of each row in the memory-optimized table is 24 + 32 + 200, or 256 bytes.</span></span>  <span data-ttu-id="af99a-132">Dal momento che sono presenti 5 milioni di righe, per la tabella verranno utilizzati 5.000.000 \* 256 byte, vale a dire 1.280.000.000 di byte, circa 1,28 GB.</span><span class="sxs-lookup"><span data-stu-id="af99a-132">Since we have 5 million rows, the table will consume 5,000,000 \* 256 bytes, or 1,280,000,000 bytes - approximately 1.28 GB.</span></span>  
  
##  <a name="memory-for-indexes"></a><a name="bkmk_IndexMeemory"></a> <span data-ttu-id="af99a-133">Memoria per gli indici</span><span class="sxs-lookup"><span data-stu-id="af99a-133">Memory for indexes</span></span>  
 <span data-ttu-id="af99a-134">**Memoria per ogni indice hash**</span><span class="sxs-lookup"><span data-stu-id="af99a-134">**Memory for each hash index**</span></span>  
  
 <span data-ttu-id="af99a-135">Ogni indice hash è una matrice di hash di puntatori all'indirizzo di 8 byte.</span><span class="sxs-lookup"><span data-stu-id="af99a-135">Each hash index is a hash array of 8-byte address pointers.</span></span>  <span data-ttu-id="af99a-136">Le dimensioni della matrice vengono determinata meglio in base al numero di valori di indice univoci per l'indice in questione, ad esempio il numero di valori Col2 univoci è un buon punto di partenza per le dimensioni della matrice per t1c2_index.</span><span class="sxs-lookup"><span data-stu-id="af99a-136">The size of the array is best determined by the number of unique index values for that index - e.g., the number of unique Col2 values is a good starting point for the array size for the t1c2_index.</span></span> <span data-ttu-id="af99a-137">Una matrice di hash eccessiva comporta uno spreco di memoria.</span><span class="sxs-lookup"><span data-stu-id="af99a-137">A hash array that is too big wastes memory.</span></span>  <span data-ttu-id="af99a-138">Una matrice di hash di piccole dimensioni determina un rallentamento delle prestazioni in quanto vi saranno troppe collisioni per i valori di indice con hashing nello stesso indice.</span><span class="sxs-lookup"><span data-stu-id="af99a-138">A hash array that is too small slows performance since there will be too many collisions by index values that hash to the same index.</span></span>  
  
 <span data-ttu-id="af99a-139">Tramite gli indici hash è possibile ottenere ricerche di uguaglianza estremamente veloci, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="af99a-139">Hash indexes achieve very fast equality lookups such as:</span></span>  
  
```sql  
  
SELECT * FROM t_hk  
   WHERE Col2 = 3  
  
```  
  
 <span data-ttu-id="af99a-140">Gli indici non cluster sono più veloci per le ricerche in intervalli, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="af99a-140">Nonclustered indexes are faster for range lookups such as:</span></span>  
  
```sql  
  
SELECT * FROM t_hk  
   WHERE Col2 >= 3  
  
```  
  
 <span data-ttu-id="af99a-141">Se si esegue la migrazione di una tabella basata su disco, è possibile utilizzare quando riportato di seguito per determinare il numero di valori univoci per l'indice t1c2_index.</span><span class="sxs-lookup"><span data-stu-id="af99a-141">If you are migrating a disk-based table you can use the following to determine the number of unique values for the index t1c2_index.</span></span>  
  
```sql  
  
SELECT COUNT(DISTINCT [Col2])  
  FROM t_hk  
  
```  
  
 <span data-ttu-id="af99a-142">Se si crea una nuova tabella, sarà necessario stimare le dimensioni della matrice o raccogliere i dati dal test prima di eseguire la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="af99a-142">If you are creating a new table, you'll need to estimate the array size or gather data from your testing prior to deployment.</span></span>  
  
 <span data-ttu-id="af99a-143">Per informazioni sul funzionamento degli indici hash in tabelle ottimizzate per la memoria [!INCLUDE[hek_2](../../includes/hek-2-md.md)], vedere [Indici hash](../../database-engine/hash-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="af99a-143">For information on how hash indexes work in [!INCLUDE[hek_2](../../includes/hek-2-md.md)] memory-optimized tables, see [Hash Indexes](../../database-engine/hash-indexes.md).</span></span>  
  
 <span data-ttu-id="af99a-144">**Nota:** Non è possibile modificare le dimensioni della matrice dell'indice hash in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="af99a-144">**Note:** You cannot change the hash index array size on the fly.</span></span> <span data-ttu-id="af99a-145">Per modificare queste dimensioni è necessario eliminare la tabella, modificare il valore di bucket_count e ricreare la tabella.</span><span class="sxs-lookup"><span data-stu-id="af99a-145">To change the hash index array size you must drop the table, change the bucket_count value and recreate the table.</span></span>  
  
 <span data-ttu-id="af99a-146">**Impostazione delle dimensioni della matrice dell'indice hash**</span><span class="sxs-lookup"><span data-stu-id="af99a-146">**Setting the hash index array size**</span></span>  
  
 <span data-ttu-id="af99a-147">Le dimensioni della matrice di hash vengono impostate tramite `(bucket_count= <value>)` dove \<value> è un intero maggiore di zero.</span><span class="sxs-lookup"><span data-stu-id="af99a-147">The hash array size is set by `(bucket_count= <value>)` where \<value> is an integer value greater than zero.</span></span> <span data-ttu-id="af99a-148">Se \<value> non è una potenza di 2, il numero effettivo di bucket_count viene arrotondato per eccesso alla potenza di 2 successiva più vicina.</span><span class="sxs-lookup"><span data-stu-id="af99a-148">If \<value> is not a power of 2, the actual bucket_count is rounded up to the next closest power of 2.</span></span>  <span data-ttu-id="af99a-149">Nella tabella di esempio (bucket_count = 5 milioni), poiché 5 milioni non è una potenza di 2, il numero effettivo di bucket viene arrotondato per eccesso a 8.388.608 (2<sup>23</sup>).</span><span class="sxs-lookup"><span data-stu-id="af99a-149">In our example table, (bucket_count = 5000000), since 5,000,000 is not a power of 2, the actual bucket count rounds up to 8,388,608 (2<sup>23</sup>).</span></span>  <span data-ttu-id="af99a-150">È necessario utilizzare questo numero, non 5.000.000, quando si calcola la memoria necessaria per la matrice di hash.</span><span class="sxs-lookup"><span data-stu-id="af99a-150">You must use this number, not 5,000,000 when calculating memory needed by the hash array.</span></span>  
  
 <span data-ttu-id="af99a-151">Pertanto, nell'esempio, la memoria necessaria per ogni matrice di hash è:</span><span class="sxs-lookup"><span data-stu-id="af99a-151">Thus, in our example, the memory needed for each hash array is:</span></span>  
  
 <span data-ttu-id="af99a-152">8.388.608 \* 8 = 2<sup>23</sup> \* 8 = 2<sup>23</sup> \* 2<sup>3</sup> = 2<sup>26</sup> = 67.108.864 o circa 64 MB.</span><span class="sxs-lookup"><span data-stu-id="af99a-152">8,388,608 \* 8 = 2<sup>23</sup> \* 8 = 2<sup>23</sup> \* 2<sup>3</sup> = 2<sup>26</sup> = 67,108,864 or approximately 64 MB.</span></span>  
  
 <span data-ttu-id="af99a-153">Poiché vi sono tre indici hash, la memoria necessaria per gli indici hash è 3 \* 64 MB = 192 MB.</span><span class="sxs-lookup"><span data-stu-id="af99a-153">Since we have three hash indexes, the memory needed for the hash indexes is 3 \* 64MB = 192MB.</span></span>  
  
 <span data-ttu-id="af99a-154">**Memoria per gli indici non cluster**</span><span class="sxs-lookup"><span data-stu-id="af99a-154">**Memory for nonclustered indexes**</span></span>  
  
 <span data-ttu-id="af99a-155">Gli indici non cluster vengono implementati come oggetti BTree con i nodi interni contenenti il valore di indice e i puntatori ai nodi successivi.</span><span class="sxs-lookup"><span data-stu-id="af99a-155">Nonclustered indexes are implemented as BTrees with the inner nodes containing the index value and pointers to subsequent nodes.</span></span>  <span data-ttu-id="af99a-156">Nei nodi foglia sono inclusi il valore di indice e un puntatore alla riga di tabella in memoria.</span><span class="sxs-lookup"><span data-stu-id="af99a-156">Leaf nodes contain the index value and a pointer to the table row in memory.</span></span>  
  
 <span data-ttu-id="af99a-157">A differenza degli indici hash, gli indici non cluster non hanno dimensioni fisse per il bucket.</span><span class="sxs-lookup"><span data-stu-id="af99a-157">Unlike hash indexes, nonclustered indexes do not have a fixed bucket size.</span></span> <span data-ttu-id="af99a-158">Le dimensioni dell'indice aumentano e si riducono dinamicamente in base ai dati.</span><span class="sxs-lookup"><span data-stu-id="af99a-158">The index grows and shrinks dynamically with the data.</span></span>  
  
 <span data-ttu-id="af99a-159">La memoria necessaria per gli indici non cluster può essere calcolata come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="af99a-159">Memory needed by nonclustered indexes can be computed as follows:</span></span>  
  
-   <span data-ttu-id="af99a-160">**Memoria allocata ai nodi non foglia** </span><span class="sxs-lookup"><span data-stu-id="af99a-160">**Memory allocated to non-leaf nodes** </span></span>  
    <span data-ttu-id="af99a-161">Per una configurazione tipica, la memoria allocata ai nodi non foglia è una percentuale minima della memoria globale utilizzata dall'indice,</span><span class="sxs-lookup"><span data-stu-id="af99a-161">For a typical configuration, the memory allocated to non-leaf nodes is a small percentage of the overall memory taken by the index.</span></span> <span data-ttu-id="af99a-162">che per le sue dimensioni contenute può essere sicuramente ignorata.</span><span class="sxs-lookup"><span data-stu-id="af99a-162">This is so small it can safely be ignored.</span></span>  
  
-   <span data-ttu-id="af99a-163">**Memoria per i nodi foglia** </span><span class="sxs-lookup"><span data-stu-id="af99a-163">**Memory for leaf nodes** </span></span>  
    <span data-ttu-id="af99a-164">I nodi foglia hanno una riga per ogni chiave univoca della tabella che punta alle righe di dati con questa chiave univoca.</span><span class="sxs-lookup"><span data-stu-id="af99a-164">The leaf nodes have one row for each unique key in the table that points to the data rows with that unique key.</span></span>  <span data-ttu-id="af99a-165">Se si hanno più righe con la stessa chiave, ovvero si ha un indice non cluster non univoco, c'è una sola riga nel nodo foglia dell'indice che punta a una delle righe, con le altre righe collegate tra loro.</span><span class="sxs-lookup"><span data-stu-id="af99a-165">If you have multiple rows with the same key (i.e., you have a non-unique nonclustered index), there is only one row in the index leaf node that points to one of the rows with the other rows linked to each other.</span></span>  <span data-ttu-id="af99a-166">Pertanto, la memoria totale necessaria può essere approssimata nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="af99a-166">Thus, the total memory required can be approximated by:</span></span>   
    <span data-ttu-id="af99a-167">memoryForNonClusteredIndex = (pointerSize + sum (keyColumnDataTypeSizes) \* rowsWithUniqueKeys</span><span class="sxs-lookup"><span data-stu-id="af99a-167">memoryForNonClusteredIndex = (pointerSize + sum(keyColumnDataTypeSizes)) \* rowsWithUniqueKeys</span></span>  
  
 <span data-ttu-id="af99a-168">Gli indici non cluster rappresentano la soluzione migliore in caso di ricerche in intervalli, come esemplificato dalla query seguente:</span><span class="sxs-lookup"><span data-stu-id="af99a-168">Nonclustered indexes are best when used for range lookups, as exemplified by the following query:</span></span>  
  
```sql  
  
SELECT * FROM t_hk  
   WHERE c2 > 5  
```  
  
##  <a name="memory-for-row-versioning"></a><a name="bkmk_MemoryForRowVersions"></a> <span data-ttu-id="af99a-169">Memoria per il controllo delle versioni delle righe</span><span class="sxs-lookup"><span data-stu-id="af99a-169">Memory for row versioning</span></span>  
 <span data-ttu-id="af99a-170">Per evitare blocchi, tramite OLTP in memoria viene utilizzata la concorrenza ottimistica durante l'aggiornamento o l'eliminazione di righe.</span><span class="sxs-lookup"><span data-stu-id="af99a-170">To avoid locks, In-Memory OLTP uses optimistic concurrency when updating or deleting rows.</span></span> <span data-ttu-id="af99a-171">Pertanto, quando una riga viene aggiornata, viene creata una versione aggiuntiva della riga.</span><span class="sxs-lookup"><span data-stu-id="af99a-171">This means that when a row is updated, an additional version of the row is created.</span></span> <span data-ttu-id="af99a-172">Il sistema mantiene le versioni precedenti disponibili fino a quando non viene completata l'esecuzione di tutte le transazioni che potrebbero eventualmente utilizzare la versione.</span><span class="sxs-lookup"><span data-stu-id="af99a-172">The system keeps the previous versions available until all transactions that could possibly use the version have finished execution.</span></span> <span data-ttu-id="af99a-173">Quando una riga viene eliminata, il sistema funziona in una modalità simile a un aggiornamento, mantenendo la versione disponibile fino a quando non è più necessaria.</span><span class="sxs-lookup"><span data-stu-id="af99a-173">When a row is deleted, the system acts in a similar way to an update, keeping the version available until it is no longer necessary.</span></span> <span data-ttu-id="af99a-174">Le operazioni di lettura e inserimento non comportano la creazione di versioni di righe aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="af99a-174">Reads and inserts do not create additional row versions.</span></span>  
  
 <span data-ttu-id="af99a-175">Poiché è possibile che vi sia un numero di righe aggiuntive in memoria in qualsiasi momento in attesa del ciclo di Garbage Collection per rilasciare la memoria, è necessario disporre di memoria sufficiente per contenere queste righe aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="af99a-175">Because there may be a number of additional rows in memory at any time waiting for the garbage collection cycle to release their memory, you must have sufficient memory to accommodate these additional rows.</span></span>  
  
 <span data-ttu-id="af99a-176">Il numero di righe aggiuntive può essere stimato calcolando il numero massimo di aggiornamenti ed eliminazioni di righe al secondo, quindi moltiplicando il risultato per il numero di secondi impiegati dalla transazione più lunga (almeno 1).</span><span class="sxs-lookup"><span data-stu-id="af99a-176">The number of additional rows can be estimated by computing the peak number of row updates and deletions per second, then multiplying that by the number of seconds the longest transaction takes (minimum of 1).</span></span>  
  
 <span data-ttu-id="af99a-177">Il valore viene quindi moltiplicato per le dimensioni della riga per ottenere il numero di byte necessari per il controllo delle versioni delle righe.</span><span class="sxs-lookup"><span data-stu-id="af99a-177">That value is then multiplied by the row size to get the number of bytes you need for row versioning.</span></span>  
  
 `rowVersions = durationOfLongestTransactionInSeconds * peakNumberOfRowUpdatesOrDeletesPerSecond`  
  
 <span data-ttu-id="af99a-178">Le esigenze di memoria per le righe non aggiornate vengono quindi stimate moltiplicando il numero di righe non aggiornate per le dimensioni di una riga di tabella ottimizzata per la memoria (vedere [memoria per la tabella](#bkmk_MemoryForTable) precedente).</span><span class="sxs-lookup"><span data-stu-id="af99a-178">Memory needs for stale rows is then estimated by multiplying the number of stale rows by the size of a memory-optimized table row (see [Memory for the table](#bkmk_MemoryForTable) above).</span></span>  
  
 `memoryForRowVersions = rowVersions * rowSize`  
  
##  <a name="memory-for-table-variables"></a><a name="bkmk_TableVariables"></a> <span data-ttu-id="af99a-179">Memoria per le variabili di tabella</span><span class="sxs-lookup"><span data-stu-id="af99a-179">Memory for table variables</span></span>  
 <span data-ttu-id="af99a-180">La memoria utilizzata per una variabile di tabella viene rilasciata solo quando la variabile di tabella abbandona l'ambito.</span><span class="sxs-lookup"><span data-stu-id="af99a-180">Memory used for a table variable is released only when the table variable goes out of scope.</span></span> <span data-ttu-id="af99a-181">Le righe eliminate, incluse quelle eliminate come parte di un aggiornamento, da una variabile di tabella non vengono sottoposte a Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="af99a-181">Deleted rows, including rows deleted as part of an update, from a table variable are not subject to garbage collection.</span></span> <span data-ttu-id="af99a-182">Finché la variabile di tabella non abbandona l'ambito, la memoria non viene rilasciata.</span><span class="sxs-lookup"><span data-stu-id="af99a-182">No memory is released until the table variable exits scope.</span></span>  
  
 <span data-ttu-id="af99a-183">Le variabili di tabella definite in un batch SQL di grandi dimensioni, a differenza di un ambito di procedura, utilizzate in molte transazioni, possono richiedere una grande quantità di memoria.</span><span class="sxs-lookup"><span data-stu-id="af99a-183">Table variables defined in a large SQL batch, as opposed to a procedure scope, which are used in many transactions, can consume a lot of memory.</span></span> <span data-ttu-id="af99a-184">Poiché non vengono sottoposte a Garbage Collection, le righe eliminate in una variabile di tabella possono utilizzare una grande quantità di memoria e influire negativamente sulle prestazioni poiché le operazioni di lettura devono eseguire l'analisi delle righe eliminate.</span><span class="sxs-lookup"><span data-stu-id="af99a-184">Because they are not garbage collected, deleted rows in a table variable can consume a lot memory and degrade performance since read operations need to scan past the deleted rows.</span></span>  
  
##  <a name="memory-for-growth"></a><a name="bkmk_MemoryForGrowth"></a> <span data-ttu-id="af99a-185">Memoria in caso di aumento delle dimensioni</span><span class="sxs-lookup"><span data-stu-id="af99a-185">Memory for growth</span></span>  
 <span data-ttu-id="af99a-186">Con i calcoli sopra riportati vengono stimati i requisiti di memoria della tabella attuale.</span><span class="sxs-lookup"><span data-stu-id="af99a-186">The above calculations estimate your memory needs for the table as it currently exists.</span></span> <span data-ttu-id="af99a-187">Oltre a questa memoria, è necessario stimare la crescita della tabella e fornire una memoria sufficiente per gestire questa crescita.</span><span class="sxs-lookup"><span data-stu-id="af99a-187">In addition to this memory, you need to estimate the growth of the table and provide sufficient memory to accommodate that growth.</span></span>  <span data-ttu-id="af99a-188">Ad esempio, se si prevede una crescita del 10%, sarà necessario moltiplicare i risultati precedenti per 1,1 per ottenere la memoria totale necessaria per la tabella.</span><span class="sxs-lookup"><span data-stu-id="af99a-188">For example, if you anticipate 10% growth then you need to multiple the results from above by 1.1 to get the total memory needed for your table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af99a-189">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="af99a-189">See Also</span></span>  
 [<span data-ttu-id="af99a-190">Migrazione a OLTP in memoria</span><span class="sxs-lookup"><span data-stu-id="af99a-190">Migrating to In-Memory OLTP</span></span>](migrating-to-in-memory-oltp.md)  
  
  
