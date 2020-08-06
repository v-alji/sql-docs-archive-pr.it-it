---
title: Risoluzione dei problemi di prestazioni comuni con gli indici hash ottimizzati per la memoria | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 1954a997-7585-4713-81fd-76d429b8d095
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3cef98571edd7736bc45ba8caf17451007a74cf1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712351"
---
# <a name="troubleshooting-common-performance-problems-with-memory-optimized-hash-indexes"></a><span data-ttu-id="81c42-102">Risoluzione dei problemi comuni di prestazioni con gli indici hash con ottimizzazione per la memoria</span><span class="sxs-lookup"><span data-stu-id="81c42-102">Troubleshooting Common Performance Problems with Memory-Optimized Hash Indexes</span></span>
  <span data-ttu-id="81c42-103">In questo argomento verrà presentata la risoluzione di problemi comuni relativi agli indici hash.</span><span class="sxs-lookup"><span data-stu-id="81c42-103">This topic will focus on troubleshooting and working around common issues with hash indexes.</span></span>  
  
## <a name="search-requires-a-subset-of-hash-index-key-columns"></a><span data-ttu-id="81c42-104">La ricerca richiede un subset di colonne chiave di indice hash</span><span class="sxs-lookup"><span data-stu-id="81c42-104">Search Requires a Subset of Hash Index Key Columns</span></span>  
 <span data-ttu-id="81c42-105">**Problema:** Gli indici hash richiedono valori per tutte le colonne chiave di indice per calcolare il valore hash e individuare le righe corrispondenti nella tabella hash.</span><span class="sxs-lookup"><span data-stu-id="81c42-105">**Issue:** Hash indexes require values for all index key columns in order to compute the hash value, and locate the corresponding rows in the hash table.</span></span> <span data-ttu-id="81c42-106">Pertanto, se una query include i predicati di uguaglianza solo per un subset di chiavi di indice nella clausola WHERE, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] non può utilizzare una ricerca nell'indice per individuare le righe che corrispondono ai predicati nella clausola WHERE.</span><span class="sxs-lookup"><span data-stu-id="81c42-106">Therefore, if a query includes equality predicates for only a subset of the index keys in the WHERE clause, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] cannot use an index seek to locate the rows corresponding to the predicates in the WHERE clause.</span></span>  
  
 <span data-ttu-id="81c42-107">Al contrario, gli indici ordinati, come gli indici non cluster basati su disco e gli indici non cluster ottimizzati per la memoria supportano la ricerca nell'indice in un subset di colonne chiave di indice, purché siano colonne iniziali nell'indice.</span><span class="sxs-lookup"><span data-stu-id="81c42-107">In contrast, ordered indexes like the disk-based nonclustered indexes and the memory-optimized nonclustered indexes support index seek on a subset of the index key columns, as long as they are the leading columns in the index.</span></span>  
  
 <span data-ttu-id="81c42-108">**Sintomo:** Ciò comporta una riduzione delle prestazioni, in quanto [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] è necessario eseguire scansioni di tabella complete anziché una ricerca nell'indice, che in genere è un'operazione più veloce.</span><span class="sxs-lookup"><span data-stu-id="81c42-108">**Symptom:** This results in a performance degradation, as [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] needs to execute full table scans rather than an index seek, which is typically a faster operation.</span></span>  
  
 <span data-ttu-id="81c42-109">**Come risolvere i problemi:** Oltre alla riduzione delle prestazioni, l'ispezione dei piani di query mostrerà un'analisi anziché una ricerca nell'indice.</span><span class="sxs-lookup"><span data-stu-id="81c42-109">**How to troubleshoot:** Besides the performance degradation, inspection of the query plans will show a scan instead of an index seek.</span></span> <span data-ttu-id="81c42-110">Se la query è relativamente semplice, l'analisi del testo della query e della definizione dell'indice indicherà se la ricerca richiede un subset delle colonne chiave di indice.</span><span class="sxs-lookup"><span data-stu-id="81c42-110">If the query is fairly simple, inspection of the query text and index definition will also show whether the search requires a subset of the index key columns.</span></span>  
  
 <span data-ttu-id="81c42-111">Si considerino la tabella e la query seguenti:</span><span class="sxs-lookup"><span data-stu-id="81c42-111">Consider the following table and query:</span></span>  
  
```sql  
CREATE TABLE [dbo].[od]  
(  
     o_id INT NOT NULL,  
     od_id INT NOT NULL,  
     p_id INT NOT NULL,  
     CONSTRAINT PK_od PRIMARY KEY NONCLUSTERED HASH (o_id, od_id) WITH (BUCKET_COUNT = 10000)  
)  
WITH (MEMORY_OPTIMIZED = ON)  
  
 SELECT p_id  
 FROM dbo.od  
 WHERE o_id=1  
```  
  
 <span data-ttu-id="81c42-112">La tabella ha un indice hash su due colonne (o_id, od_id), mentre la query ha un predicato di uguaglianza su (o_id).</span><span class="sxs-lookup"><span data-stu-id="81c42-112">The table has a hash index on the two columns (o_id, od_id), while the query has an equality predicate on (o_id).</span></span> <span data-ttu-id="81c42-113">Poiché la query ha predicati di uguaglianza solo in un subset di colonne chiave di indice, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] non può eseguire un'operazione di ricerca nell'indice utilizzando PK_od; in alternativa, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] deve passare a un'analisi completa dell'indice.</span><span class="sxs-lookup"><span data-stu-id="81c42-113">As the query has equality predicates on only a subset of the index key columns, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] cannot perform an index seek operation using PK_od; instead, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] has to revert to a full index scan.</span></span>  
  
 <span data-ttu-id="81c42-114">**Soluzioni alternative:** Esistono diverse soluzioni possibili.</span><span class="sxs-lookup"><span data-stu-id="81c42-114">**Workarounds:** There are a number of possible workarounds.</span></span> <span data-ttu-id="81c42-115">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="81c42-115">For example:</span></span>  
  
-   <span data-ttu-id="81c42-116">Ricreare l'indice come tipo non cluster anziché hash non cluster.</span><span class="sxs-lookup"><span data-stu-id="81c42-116">Recreate the index as type nonclustered instead of nonclustered hash.</span></span> <span data-ttu-id="81c42-117">L'indice non cluster ottimizzato per la memoria è ordinato e, pertanto, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] può eseguire una ricerca nell'indice nelle colonne chiave di indice iniziali.</span><span class="sxs-lookup"><span data-stu-id="81c42-117">The memory-optimized nonclustered index is ordered, and thus [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] can perform an index seek on the leading index key columns.</span></span> <span data-ttu-id="81c42-118">La definizione di chiave primaria risultante per l'esempio sarebbe `constraint PK_od primary key nonclustered`.</span><span class="sxs-lookup"><span data-stu-id="81c42-118">The resulting primary key definition for the example would be `constraint PK_od primary key nonclustered`.</span></span>  
  
-   <span data-ttu-id="81c42-119">Modificare la chiave di indice corrente affinché corrisponda alle colonne nella clausola WHERE.</span><span class="sxs-lookup"><span data-stu-id="81c42-119">Change the current index key to match the columns in the WHERE clause.</span></span>  
  
-   <span data-ttu-id="81c42-120">Aggiungere un nuovo indice hash corrispondente alle colonne nella clausola WHERE della query.</span><span class="sxs-lookup"><span data-stu-id="81c42-120">Add a new hash index that matches with the columns in the WHERE clause of the query.</span></span> <span data-ttu-id="81c42-121">Nell'esempio, la definizione di tabella risultante sarebbe simile a quanto segue:</span><span class="sxs-lookup"><span data-stu-id="81c42-121">In the example, the resulting table definition would look at follows:</span></span>  
  
    ```sql  
    CREATE TABLE dbo.od  
     ( o_id INT NOT NULL,  
     od_id INT NOT NULL,  
     p_id INT NOT NULL,  
  
     CONSTRAINT PK_od PRIMARY KEY   
     NONCLUSTERED HASH (o_id,od_id) WITH (BUCKET_COUNT=10000),  
  
     INDEX ix_o_id NONCLUSTERED HASH (o_id) WITH (BUCKET_COUNT=10000)  
  
     ) WITH (MEMORY_OPTIMIZED=ON)  
    ```  
  
 <span data-ttu-id="81c42-122">Si noti che le prestazioni di un indice hash ottimizzato per la memoria non sono ottimali se sono presenti molte righe duplicate per un determinato valore di chiave di indice: nell'esempio, se il numero di valori univoci per la colonna o_id è molto minore del numero di righe nella tabella, non è ottimale aggiungere un indice su (o_id); in alternativa, la modifica del tipo dell'indice PK_od da hash a non cluster potrebbe essere la soluzione migliore.</span><span class="sxs-lookup"><span data-stu-id="81c42-122">Note that a memory-optimized hash index does not perform optimally if there are a lot of duplicate rows for a given index key value: in the example, if the number of unique values for the column o_id is much smaller than the number of rows in the table, it would not be optimal to add an index on (o_id); instead, changing the type of the index PK_od from hash to nonclustered would be the better solution.</span></span> <span data-ttu-id="81c42-123">Per ulteriori informazioni, vedere [Determining the Correct Bucket Count for Hash Indexes](../relational-databases/indexes/indexes.md).</span><span class="sxs-lookup"><span data-stu-id="81c42-123">For more information, see [Determining the Correct Bucket Count for Hash Indexes](../relational-databases/indexes/indexes.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81c42-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="81c42-124">See Also</span></span>  
 [<span data-ttu-id="81c42-125">Indici in tabelle con ottimizzazione per la memoria</span><span class="sxs-lookup"><span data-stu-id="81c42-125">Indexes on Memory-Optimized Tables</span></span>](../relational-databases/in-memory-oltp/memory-optimized-tables.md)  
  
  
