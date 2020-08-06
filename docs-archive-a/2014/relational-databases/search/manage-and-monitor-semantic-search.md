---
title: Gestire e monitorare la ricerca semantica | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
helpviewer_keywords:
- semantic search [SQL Server], managing
- semantic search [SQL Server], monitoring
ms.assetid: eb5c3b29-da70-42aa-aa97-7d35a3f1eb98
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 16e3af1d37f177dfe6d4e0cb090e7b8b0a4988d9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717681"
---
# <a name="manage-and-monitor-semantic-search"></a><span data-ttu-id="045d8-102">Gestire e monitorare la ricerca semantica</span><span class="sxs-lookup"><span data-stu-id="045d8-102">Manage and Monitor Semantic Search</span></span>
  <span data-ttu-id="045d8-103">Vengono illustrati il processo di indicizzazione semantica e le attività correlate alla gestione e al monitoraggio degli indici.</span><span class="sxs-lookup"><span data-stu-id="045d8-103">Describes the process of semantic indexing and the tasks related to managing and monitoring the indexes.</span></span>  
  
##  <a name="how-to-check-the-status-of-semantic-indexing"></a><a name="HowToMonitorStatus"></a><span data-ttu-id="045d8-104">Procedura: controllare lo stato dell'indicizzazione semantica</span><span class="sxs-lookup"><span data-stu-id="045d8-104">How To: Check the Status of Semantic Indexing</span></span>  
 <span data-ttu-id="045d8-105">**Verifica del completamento della prima fase dell'indicizzazione semantica**</span><span class="sxs-lookup"><span data-stu-id="045d8-105">**Is the first phase of semantic indexing complete?**</span></span>  
 <span data-ttu-id="045d8-106">Eseguire una query sulla DMV [sys.dm_fts_index_population &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-index-population-transact-sql) e verificare lo **stato** e le colonne **status_description**.</span><span class="sxs-lookup"><span data-stu-id="045d8-106">Query the dynamic management view, [sys.dm_fts_index_population &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-index-population-transact-sql), and check the **status** and **status_description** columns.</span></span>  
  
 <span data-ttu-id="045d8-107">La prima fase dell'indicizzazione include il popolamento dell'indice di parole chiave full-text e dell'indice di frasi chiave semantico, nonché l'estrazione dei dati di somiglianza dei documenti.</span><span class="sxs-lookup"><span data-stu-id="045d8-107">The first phase of indexing includes the population of the full-text keyword index and the semantic key phrase index, as well as the extraction of document similarity data.</span></span>  
  
```sql  
USE database_name  
GO  
  
SELECT * FROM sys.dm_fts_index_population WHERE table_id = OBJECT_ID('table_name')  
GO  
```  
  
 <span data-ttu-id="045d8-108">**Verifica del completamento della seconda fase dell'indicizzazione semantica**</span><span class="sxs-lookup"><span data-stu-id="045d8-108">**Is the second phase of semantic indexing complete?**</span></span>  
 <span data-ttu-id="045d8-109">Eseguire una query sulla DMV [sys.dm_fts_semantic_similarity_population &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-semantic-similarity-population-transact-sql) e verificare lo **stato** e le colonne **status_description**.</span><span class="sxs-lookup"><span data-stu-id="045d8-109">Query the dynamic management view, [sys.dm_fts_semantic_similarity_population &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-semantic-similarity-population-transact-sql), and check the **status** and **status_description** columns..</span></span>  
  
 <span data-ttu-id="045d8-110">La seconda fase dell'indicizzazione include il popolamento dell'indice di somiglianza dei documenti semantico.</span><span class="sxs-lookup"><span data-stu-id="045d8-110">The second phase of indexing includes the population of the semantic document similarity index.</span></span>  
  
```wql  
USE database_name  
GO  
  
SELECT * FROM sys.dm_fts_semantic_similarity_population WHERE table_id = OBJECT_ID('table_name')  
GO  
```  
  
##  <a name="how-to-check-the-size-of-the-semantic-indexes"></a><a name="HowToCheckSize"></a><span data-ttu-id="045d8-111">Procedura: controllare le dimensioni degli indici semantici</span><span class="sxs-lookup"><span data-stu-id="045d8-111">How To: Check the Size of the Semantic Indexes</span></span>  
 <span data-ttu-id="045d8-112">**Individuazione della dimensione logica di un indice di frasi chiave semantico o di un indice di somiglianza dei documenti semantico**</span><span class="sxs-lookup"><span data-stu-id="045d8-112">**What is the logical size of a semantic key phrase index or a semantic document similarity index?**</span></span>  
 <span data-ttu-id="045d8-113">Eseguire una query sulla DMV [sys.dm_db_fts_index_physical_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-fts-index-physical-stats-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="045d8-113">Query the dynamic management view, [sys.dm_db_fts_index_physical_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-fts-index-physical-stats-transact-sql).</span></span>  
  
 <span data-ttu-id="045d8-114">La dimensione logica viene visualizzata in numero di pagine di indice.</span><span class="sxs-lookup"><span data-stu-id="045d8-114">The logical size is displayed in number of index pages.</span></span>  
  
```sql  
USE database_name  
GO  
  
SELECT * FROM sys.dm_db_fts_index_physical_stats WHERE object_id = OBJECT_ID('table_name')  
GO  
```  
  
 <span data-ttu-id="045d8-115">**Individuazione delle dimensioni totali degli indici full-text e semantici per un catalogo full-text**</span><span class="sxs-lookup"><span data-stu-id="045d8-115">**What is the total size of the full-text and semantic indexes for a full-text catalog?**</span></span>  
 <span data-ttu-id="045d8-116">Eseguire una query sulla proprietà **IndexSize** della funzione per i metadati [FULLTEXTCATALOGPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/fulltextcatalogproperty-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="045d8-116">Query the **IndexSize** property of the [FULLTEXTCATALOGPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/fulltextcatalogproperty-transact-sql) metadata function.</span></span>  
  
```sql  
SELECT FULLTEXTCATALOGPROPERTY('catalog_name', 'IndexSize')  
GO  
```  
  
 <span data-ttu-id="045d8-117">**Individuazione del numero di elementi indicizzati negli indici full-text e semantico per un catalogo full-text**</span><span class="sxs-lookup"><span data-stu-id="045d8-117">**How many items are indexed in the full-text and semantic indexes for a full-text catalog?**</span></span>  
 <span data-ttu-id="045d8-118">Eseguire una query sulla proprietà **ItemCount** della funzione per i metadati [FULLTEXTCATALOGPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/fulltextcatalogproperty-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="045d8-118">Query the **ItemCount** property of the [FULLTEXTCATALOGPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/fulltextcatalogproperty-transact-sql) metadata function.</span></span>  
  
```sql  
SELECT FULLTEXTCATALOGPROPERTY('catalog_name', 'ItemCount')  
GO  
```  
  
##  <a name="how-to-force-the-population-of-the-semantic-indexes"></a><a name="HowToForcePopulation"></a><span data-ttu-id="045d8-119">Procedura: forzare il popolamento degli indici semantici</span><span class="sxs-lookup"><span data-stu-id="045d8-119">How To: Force the Population of the Semantic Indexes</span></span>  
 <span data-ttu-id="045d8-120">È possibile forzare il popolamento degli indici full-text e semantici utilizzando la clausola START/STOP/PAUSE o RESUME POPULATION con la stessa sintassi e lo stesso comportamento descritti per gli indici full-text.</span><span class="sxs-lookup"><span data-stu-id="045d8-120">You can force the population of full-text and semantic indexes by using the START/STOP/PAUSE or RESUME POPULATION clause with the same syntax and behavior that is described for full-text indexes.</span></span> <span data-ttu-id="045d8-121">Per altre informazioni, vedere [ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-index-transact-sql) e [Popolamento degli indici full-texts](../indexes/indexes.md).</span><span class="sxs-lookup"><span data-stu-id="045d8-121">For more information, see [ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-index-transact-sql) and [Populate Full-Text Indexes](../indexes/indexes.md).</span></span>  
  
 <span data-ttu-id="045d8-122">Poiché l'indicizzazione semantica dipende dall'indicizzazione full-text, gli indici semantici vengono popolati solo al popolamento degli indici full-text associati.</span><span class="sxs-lookup"><span data-stu-id="045d8-122">Since semantic indexing is dependent on full-text indexing, semantic indexes are only populated when the associated full-text indexes are populated.</span></span>  
  
 <span data-ttu-id="045d8-123">**Esempio: Avviare un popolamento completo di indici full-text e semantici**</span><span class="sxs-lookup"><span data-stu-id="045d8-123">**Example: Start a full population of full-text and semantic indexes**</span></span>  
  
 <span data-ttu-id="045d8-124">Nell'esempio seguente viene avviato il popolamento completo degli indici semantici e full-text mediante la modifica di un indice full-text esistente nella tabella **Production.Document** del database di esempio AdventureWorks2012.</span><span class="sxs-lookup"><span data-stu-id="045d8-124">The following example starts full population of both full-text and semantic indexes by altering an existing full-text index on the **Production.Document** table in the AdventureWorks2012 sample database.</span></span>  
  
```vb  
USE AdventureWorks2012  
GO  
  
ALTER FULLTEXT INDEX ON Production.Document  
    START FULL POPULATION  
GO  
```  
  
##  <a name="how-to-disable-or-re-enable-semantic-indexing"></a><a name="HowToDisableIndexing"></a><span data-ttu-id="045d8-125">Procedura: disabilitare o riabilitare l'indicizzazione semantica</span><span class="sxs-lookup"><span data-stu-id="045d8-125">How To: Disable or Re-enable Semantic Indexing</span></span>  
 <span data-ttu-id="045d8-126">È possibile abilitare o disabilitare l'indicizzazione full-text o semantica utilizzando la clausola ENABLE/DISABLE con la stessa sintassi e lo stesso comportamento descritti per gli indici full-text.</span><span class="sxs-lookup"><span data-stu-id="045d8-126">You can enable or disable full-text or semantic indexing by using the ENABLE/DISABLE clause with the same syntax and behavior that is described for full-text indexes.</span></span> <span data-ttu-id="045d8-127">Per altre informazioni, vedere [ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="045d8-127">For more information, see [ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-index-transact-sql).</span></span>  
  
 <span data-ttu-id="045d8-128">Quando l'indicizzazione semantica è disabilitata e sospesa, le query sui dati semantici continuano a funzionare correttamente e a restituire dati precedentemente indicizzati.</span><span class="sxs-lookup"><span data-stu-id="045d8-128">When semantic indexing is disabled and suspended, queries over semantic data continue to work successfully and to return previously indexed data.</span></span> <span data-ttu-id="045d8-129">Questo comportamento non è coerente con quello della ricerca full-text.</span><span class="sxs-lookup"><span data-stu-id="045d8-129">This behavior is not consistent with the behavior of Full-Text Search.</span></span>  
  
```sql  
-- To disable semantic indexing on a table  
USE database_name  
GO  
  
ALTER FULLTEXT INDEX ON table_name DISABLE  
GO  
  
-- To re-enable semantic indexing on a table  
USE database_name  
GO  
  
ALTER FULLTEXT INDEX ON table_name ENABLE  
GO  
```  
  
##  <a name="phases-of-semantic-indexing"></a><a name="SemanticIndexing"></a><span data-ttu-id="045d8-130">Fasi di indicizzazione semantica</span><span class="sxs-lookup"><span data-stu-id="045d8-130">Phases of Semantic Indexing</span></span>  
 <span data-ttu-id="045d8-131">Tramite la ricerca semantica vengono indicizzati due tipi di dati per ogni colonna in cui è abilitata:</span><span class="sxs-lookup"><span data-stu-id="045d8-131">Semantic Search indexes two kinds of data for each column on which it is enabled:</span></span>  
  
1.  <span data-ttu-id="045d8-132">**Frasi chiave**</span><span class="sxs-lookup"><span data-stu-id="045d8-132">**Key phrases**</span></span>  
  
2.  <span data-ttu-id="045d8-133">**Somiglianza dei documenti**</span><span class="sxs-lookup"><span data-stu-id="045d8-133">**Document similarity**</span></span>  
  
 <span data-ttu-id="045d8-134">L'indicizzazione semantica viene eseguita in due fasi, insieme all'indicizzazione full-text:</span><span class="sxs-lookup"><span data-stu-id="045d8-134">Semantic indexing occurs in two phases, in conjunction with full-text indexing:</span></span>  
  
1.  <span data-ttu-id="045d8-135">**Fase 1**.</span><span class="sxs-lookup"><span data-stu-id="045d8-135">**Phase 1**.</span></span> <span data-ttu-id="045d8-136">L'indice delle parole chiave full-text e l'indice delle frasi chiave semantico vengono popolati in parallelo.</span><span class="sxs-lookup"><span data-stu-id="045d8-136">The full-text keyword index and the semantic key phrase index are populated in parallel at the same time.</span></span> <span data-ttu-id="045d8-137">In questa fase vengono anche estratti i dati necessari per indicizzare la somiglianza dei documenti.</span><span class="sxs-lookup"><span data-stu-id="045d8-137">The data required to index document similarity is also extracted at this time.</span></span>  
  
2.  <span data-ttu-id="045d8-138">**Fase 2**.</span><span class="sxs-lookup"><span data-stu-id="045d8-138">**Phase 2**.</span></span> <span data-ttu-id="045d8-139">Viene quindi popolato l'indice di somiglianza dei documenti semantico.</span><span class="sxs-lookup"><span data-stu-id="045d8-139">The semantic document similarity index is then populated.</span></span> <span data-ttu-id="045d8-140">Questo indice dipende da entrambi gli indici popolati nella fase precedente.</span><span class="sxs-lookup"><span data-stu-id="045d8-140">This index depends on both indexes that were populated in the preceding phase.</span></span>  
  
##  <a name="BestPracticeUnderstand"></a>   
##  <a name="problem-semantic-indexes-are-not-populated"></a><a name="ProblemNotPopulated"></a><span data-ttu-id="045d8-141">Problema: gli indici semantici non vengono popolati</span><span class="sxs-lookup"><span data-stu-id="045d8-141">Problem: Semantic Indexes Are Not Populated</span></span>  
 <span data-ttu-id="045d8-142">**Verificare se gli indici full-text associati sono stati popolati.**</span><span class="sxs-lookup"><span data-stu-id="045d8-142">**Are the associated full-text indexes populated?**</span></span>  
 <span data-ttu-id="045d8-143">Poiché l'indicizzazione semantica dipende dall'indicizzazione full-text, gli indici semantici vengono popolati solo al popolamento degli indici full-text associati.</span><span class="sxs-lookup"><span data-stu-id="045d8-143">Since semantic indexing is dependent on full-text indexing, semantic indexes are only populated when the associated full-text indexes are populated.</span></span>  
  
 <span data-ttu-id="045d8-144">**Verificare se la ricerca full-text e la ricerca semantica sono state installate e configurate correttamente.**</span><span class="sxs-lookup"><span data-stu-id="045d8-144">**Are full-text search and semantic search properly installed and configured?**</span></span>  
 <span data-ttu-id="045d8-145">Per altre informazioni, vedere [Installazione e configurazione della ricerca semantica](install-and-configure-semantic-search.md).</span><span class="sxs-lookup"><span data-stu-id="045d8-145">For more information, see [Install and Configure Semantic Search](install-and-configure-semantic-search.md).</span></span>  
  
 <span data-ttu-id="045d8-146">**Controllare se il servizio FDHOST è disponibile o se si è verificata un'altra condizione che provoca la mancata esecuzione dell'indicizzazione full-text.**</span><span class="sxs-lookup"><span data-stu-id="045d8-146">**Is the FDHOST service not available, or is there another condition that would cause full-text indexing to fail?**</span></span>  
 <span data-ttu-id="045d8-147">Per altre informazioni, vedere [Risoluzione dei problemi nell'indicizzazione full-text](troubleshoot-full-text-indexing.md).</span><span class="sxs-lookup"><span data-stu-id="045d8-147">For more information, see [Troubleshoot Full-Text Indexing](troubleshoot-full-text-indexing.md).</span></span>  
  
  
