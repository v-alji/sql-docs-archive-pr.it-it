---
title: Requisiti di spazio su disco per operazioni DLL sugli indici | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- disk space [SQL Server], indexes
- index disk space [SQL Server]
- space [SQL Server], indexes
- indexes [SQL Server], disk space requirements
- temporary disk space [SQL Server]
ms.assetid: 35930826-c870-44c1-a966-a6a4638f62ef
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 4ac25fc1555d6b6cfd8ee97b50d261cf5788f587
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637318"
---
# <a name="disk-space-requirements-for-index-ddl-operations"></a><span data-ttu-id="6ea8b-102">Requisiti di spazio su disco per operazioni DLL sugli indici</span><span class="sxs-lookup"><span data-stu-id="6ea8b-102">Disk Space Requirements for Index DDL Operations</span></span>
  <span data-ttu-id="6ea8b-103">Lo spazio su disco è un fattore che richiede particolare considerazione in fase di creazione, ricompilazione o eliminazione di indici.</span><span class="sxs-lookup"><span data-stu-id="6ea8b-103">Disk space is an important consideration when you create, rebuild, or drop indexes.</span></span> <span data-ttu-id="6ea8b-104">Uno spazio su disco non adeguato può comportare una riduzione delle prestazioni o provocare un errore dell'operazione sull'indice.</span><span class="sxs-lookup"><span data-stu-id="6ea8b-104">Inadequate disk space can degrade performance or even cause the index operation to fail.</span></span> <span data-ttu-id="6ea8b-105">In questo argomento vengono fornite informazioni generali utili per determinare la quantità di spazio su disco necessaria per operazioni DLL (Data Definition Language) sugli indici.</span><span class="sxs-lookup"><span data-stu-id="6ea8b-105">This topic provides general information that can help you determine the amount of disk space required for index data definition language (DDL) operations.</span></span>  
  
## <a name="index-operations-that-require-no-additional-disk-space"></a><span data-ttu-id="6ea8b-106">Operazioni sugli indici che non richiedono spazio su disco aggiuntivo</span><span class="sxs-lookup"><span data-stu-id="6ea8b-106">Index Operations That Require No Additional Disk Space</span></span>  
 <span data-ttu-id="6ea8b-107">Le operazioni seguenti non richiedono spazio su disco aggiuntivo:</span><span class="sxs-lookup"><span data-stu-id="6ea8b-107">The following index operations require no additional disk space:</span></span>  
  
-   <span data-ttu-id="6ea8b-108">ALTER INDEX REORGANIZE. È tuttavia richiesto spazio nel log.</span><span class="sxs-lookup"><span data-stu-id="6ea8b-108">ALTER INDEX REORGANIZE; however, log space is required.</span></span>  
  
-   <span data-ttu-id="6ea8b-109">DROP INDEX quando si elimina un indice non cluster.</span><span class="sxs-lookup"><span data-stu-id="6ea8b-109">DROP INDEX when you are dropping a nonclustered index.</span></span>  
  
-   <span data-ttu-id="6ea8b-110">DROP INDEX quando si elimina un indice cluster offline senza specificare la clausola MOVE TO e non sono presenti indici non cluster.</span><span class="sxs-lookup"><span data-stu-id="6ea8b-110">DROP INDEX when you are dropping a clustered index offline without specifying the MOVE TO clause and nonclustered indexes do not exist.</span></span>  
  
-   <span data-ttu-id="6ea8b-111">CREATE TABLE (vincoli PRIMARY KEY o UNIQUE)</span><span class="sxs-lookup"><span data-stu-id="6ea8b-111">CREATE TABLE (PRIMARY KEY or UNIQUE constraints)</span></span>  
  
## <a name="index-operations-that-require-additional-disk-space"></a><span data-ttu-id="6ea8b-112">Operazioni sugli indici che richiedono spazio su disco aggiuntivo</span><span class="sxs-lookup"><span data-stu-id="6ea8b-112">Index Operations That Require Additional Disk Space</span></span>  
 <span data-ttu-id="6ea8b-113">Tutte le altre operazioni DLL sugli indici richiedono spazio su disco aggiuntivo temporaneo da utilizzare durante l'operazione e spazio su disco permanente per l'archiviazione della nuova o delle nuove strutture dell'indice.</span><span class="sxs-lookup"><span data-stu-id="6ea8b-113">All other index DDL operations require additional temporary disk space to use during the operation, and permanent disk space to store the new index structure or structures.</span></span>  
  
 <span data-ttu-id="6ea8b-114">Quando viene creata una nuova struttura dell'indice, è necessario spazio su disco per la struttura vecchia (origine) e per quella nuova (destinazione) nei file e filegroup appropriati.</span><span class="sxs-lookup"><span data-stu-id="6ea8b-114">When a new index structure is created, disk space for both the old (source) and new (target) structures is required in their appropriate files and filegroups.</span></span> <span data-ttu-id="6ea8b-115">La struttura di origine non viene deallocata finché non viene eseguito il commit della transazione di creazione dell'indice.</span><span class="sxs-lookup"><span data-stu-id="6ea8b-115">The old structure is not deallocated until the index creation transaction commits.</span></span>  
  
 <span data-ttu-id="6ea8b-116">Le operazioni DLL sugli indici seguenti comportano la creazione di nuove strutture dell'indice e richiedono spazio su disco aggiuntivo:</span><span class="sxs-lookup"><span data-stu-id="6ea8b-116">The following index DDL operations create new index structures and require additional disk space:</span></span>  
  
-   <span data-ttu-id="6ea8b-117">CREATE INDEX</span><span class="sxs-lookup"><span data-stu-id="6ea8b-117">CREATE INDEX</span></span>  
  
-   <span data-ttu-id="6ea8b-118">CREATE INDEX WITH DROP_EXISTING</span><span class="sxs-lookup"><span data-stu-id="6ea8b-118">CREATE INDEX WITH DROP_EXISTING</span></span>  
  
-   <span data-ttu-id="6ea8b-119">ALTER INDEX REBUILD</span><span class="sxs-lookup"><span data-stu-id="6ea8b-119">ALTER INDEX REBUILD</span></span>  
  
-   <span data-ttu-id="6ea8b-120">ALTER TABLE ADD CONSTRAINT (PRIMARY KEY o UNIQUE)</span><span class="sxs-lookup"><span data-stu-id="6ea8b-120">ALTER TABLE ADD CONSTRAINT (PRIMARY KEY or UNIQUE)</span></span>  
  
-   <span data-ttu-id="6ea8b-121">ALTER TABLE DROP CONSTRAINT (PRIMARY KEY o UNIQUE) quando il vincolo è basato su un indice cluster</span><span class="sxs-lookup"><span data-stu-id="6ea8b-121">ALTER TABLE DROP CONSTRAINT (PRIMARY KEY or UNIQUE) when the constraint is based on a clustered index</span></span>  
  
-   <span data-ttu-id="6ea8b-122">DROP INDEX MOVE TO (solo per indici cluster)</span><span class="sxs-lookup"><span data-stu-id="6ea8b-122">DROP INDEX MOVE TO (Applies only to clustered indexes.)</span></span>  
  
## <a name="temporary-disk-space-for-sorting"></a><span data-ttu-id="6ea8b-123">Spazio su disco temporaneo per l'ordinamento</span><span class="sxs-lookup"><span data-stu-id="6ea8b-123">Temporary Disk Space for Sorting</span></span>  
 <span data-ttu-id="6ea8b-124">Oltre allo spazio su disco necessario per le strutture di origine e di destinazione, è necessario spazio su disco temporaneo per l'ordinamento, a meno che tramite Query Optimizer non venga individuato un piano di esecuzione che non richiede l'ordinamento.</span><span class="sxs-lookup"><span data-stu-id="6ea8b-124">Besides the disk space required for the source and target structures, temporary disk space is required for sorting, unless the query optimizer finds an execution plan that does not require sorting.</span></span>  
  
 <span data-ttu-id="6ea8b-125">L'ordinamento, se necessario, viene eseguito in un nuovo indice per volta.</span><span class="sxs-lookup"><span data-stu-id="6ea8b-125">If sorting is required, sorting occurs one new index at a time.</span></span> <span data-ttu-id="6ea8b-126">Quando, ad esempio, si ricompilano un indice cluster e gli indici non cluster associati in una singola istruzione, gli indici vengono ordinati uno dopo l'altro.</span><span class="sxs-lookup"><span data-stu-id="6ea8b-126">For example, when you rebuild a clustered index and associated nonclustered indexes within a single statement, the indexes are sorted one after the other.</span></span> <span data-ttu-id="6ea8b-127">Lo spazio su disco aggiuntivo temporaneo necessario per l'ordinamento corrisponde pertanto alle dimensioni dell'indice di dimensioni maggiori coinvolto nell'operazione,</span><span class="sxs-lookup"><span data-stu-id="6ea8b-127">Therefore, the additional temporary disk space that is required for sorting only has to be as large as the largest index in the operation.</span></span> <span data-ttu-id="6ea8b-128">che è solitamente l'indice cluster.</span><span class="sxs-lookup"><span data-stu-id="6ea8b-128">This is almost always the clustered index.</span></span>  
  
 <span data-ttu-id="6ea8b-129">Se l'opzione SORT_IN_TEMPDB è impostata su ON, l'indice di dimensioni maggiori deve poter essere contenuto in **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="6ea8b-129">If the SORT_IN_TEMPDB option is set to ON, the largest index must fit into **tempdb**.</span></span> <span data-ttu-id="6ea8b-130">Sebbene questa opzione comporti l'aumento della quantità di spazio su disco temporaneo necessario per creare un indice, potrebbe consentire di ridurre il tempo necessario per questa operazione quando **tempdb** si trova in un set di dischi diverso da quello in cui si trova il database utente.</span><span class="sxs-lookup"><span data-stu-id="6ea8b-130">Although this option increases the amount of temporary disk space that is used to create an index, it may reduce the time that is required to create an index when **tempdb** is on a set of disks different from the user database.</span></span>  
  
 <span data-ttu-id="6ea8b-131">Se l'opzione SORT_IN_TEMPDB è impostata su OFF, ovvero il valore predefinito, ogni indice, inclusi gli indici partizionati, viene archiviato nel relativo spazio su disco di destinazione ed è necessario solo lo spazio su disco per le nuove strutture dell'indice.</span><span class="sxs-lookup"><span data-stu-id="6ea8b-131">If SORT_IN_TEMPDB is set to OFF (the default) each index, including partitioned indexes, is sorted in its destination disk space; and only the disk space for the new index structures is required.</span></span>  
  
 <span data-ttu-id="6ea8b-132">Per un esempio di calcolo dello spazio su disco, vedere [Esempio di spazio su disco per gli indici](index-disk-space-example.md).</span><span class="sxs-lookup"><span data-stu-id="6ea8b-132">For an example of calculating disk space, see [Index Disk Space Example](index-disk-space-example.md).</span></span>  
  
## <a name="temporary-disk-space-for-online-index-operations"></a><span data-ttu-id="6ea8b-133">Spazio su disco temporaneo per operazioni sugli indici online</span><span class="sxs-lookup"><span data-stu-id="6ea8b-133">Temporary Disk Space for Online Index Operations</span></span>  
 <span data-ttu-id="6ea8b-134">Quando si eseguono operazioni sugli indici online, è necessario spazio su disco aggiuntivo temporaneo.</span><span class="sxs-lookup"><span data-stu-id="6ea8b-134">When you perform index operations online, additional temporary disk space is required.</span></span>  
  
 <span data-ttu-id="6ea8b-135">Quando viene creato, ricompilato o eliminato un indice cluster online, viene creato un indice non cluster temporaneo per l'esecuzione del mapping tra vecchi segnalibri e nuovi segnalibri.</span><span class="sxs-lookup"><span data-stu-id="6ea8b-135">If a clustered index is created, rebuilt, or dropped online, a temporary nonclustered index is created to map old bookmarks to new bookmarks.</span></span> <span data-ttu-id="6ea8b-136">Se l'opzione SORT_IN_TEMPDB è impostata su ON, questo indice temporaneo viene creato in **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="6ea8b-136">If the SORT_IN_TEMPDB option is set to ON, this temporary index is created in **tempdb**.</span></span> <span data-ttu-id="6ea8b-137">Se l'opzione SORT_IN_TEMPDB è impostata su OFF, viene utilizzato lo stesso filegroup o schema di partizione dell'indice di destinazione.</span><span class="sxs-lookup"><span data-stu-id="6ea8b-137">If SORT_IN_TEMPDB is set to OFF, the same filegroup or partition scheme as the target index is used.</span></span> <span data-ttu-id="6ea8b-138">L'indice di mapping temporaneo contiene un record per ogni riga della tabella e i contenuti sono costituiti dall'unione delle colonne di segnalibri vecchi e nuovi, inclusi uniqueifier e identificatori di record e includono una singola copia di ogni colonna utilizzata in entrambi i segnalibri.</span><span class="sxs-lookup"><span data-stu-id="6ea8b-138">The temporary mapping index contains one record for each row in the table, and its contents is the union of the old and new bookmark columns, including uniqueifiers and record identifiers and including only a single copy of any column used in both bookmarks.</span></span> <span data-ttu-id="6ea8b-139">Per altre informazioni sulle operazioni online sugli indici, vedere [Eseguire operazioni online sugli indici](perform-index-operations-online.md).</span><span class="sxs-lookup"><span data-stu-id="6ea8b-139">For more information about online index operations, see [Perform Index Operations Online](perform-index-operations-online.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6ea8b-140">Non è possibile impostare l'opzione SORT_IN_TEMPDB per le istruzioni DROP INDEX.</span><span class="sxs-lookup"><span data-stu-id="6ea8b-140">The SORT_IN_TEMPDB option cannot be set for DROP INDEX statements.</span></span> <span data-ttu-id="6ea8b-141">L'indice di mapping temporaneo viene sempre creato nello stesso filegroup o schema di partizione dell'indice di destinazione.</span><span class="sxs-lookup"><span data-stu-id="6ea8b-141">The temporary mapping index is always created in the same filegroup or partition scheme as the target index.</span></span>  
  
 <span data-ttu-id="6ea8b-142">Nelle operazioni sugli indici online viene utilizzato il controllo delle versioni delle righe per isolare le operazioni dagli effetti delle modifiche apportate da altre transazioni.</span><span class="sxs-lookup"><span data-stu-id="6ea8b-142">Online index operations use row versioning to isolate the index operation from the effects of modifications made by other transactions.</span></span> <span data-ttu-id="6ea8b-143">In questo modo, non è necessario richiedere blocchi di condivisione sulle righe lette.</span><span class="sxs-lookup"><span data-stu-id="6ea8b-143">This avoids the need for requesting share locks on rows that have been read.</span></span> <span data-ttu-id="6ea8b-144">Le operazioni utente simultanee di aggiornamento ed eliminazione durante le operazioni sugli indici online richiedono spazio per i record di versione in **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="6ea8b-144">Concurrent user update and delete operations during online index operations require space for version records in **tempdb**.</span></span> <span data-ttu-id="6ea8b-145">Per altre informazioni, vedere [Eseguire operazioni online sugli indici](perform-index-operations-online.md) .</span><span class="sxs-lookup"><span data-stu-id="6ea8b-145">For more information, see [Perform Index Operations Online](perform-index-operations-online.md) .</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="6ea8b-146">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="6ea8b-146">Related Tasks</span></span>  
 [<span data-ttu-id="6ea8b-147">Esempio di spazio su disco per gli indici</span><span class="sxs-lookup"><span data-stu-id="6ea8b-147">Index Disk Space Example</span></span>](index-disk-space-example.md)  
  
 [<span data-ttu-id="6ea8b-148">Spazio su disco per il log delle transazioni per operazioni sugli indici</span><span class="sxs-lookup"><span data-stu-id="6ea8b-148">Transaction Log Disk Space for Index Operations</span></span>](transaction-log-disk-space-for-index-operations.md)  
  
 [<span data-ttu-id="6ea8b-149">Stimare le dimensioni di una tabella</span><span class="sxs-lookup"><span data-stu-id="6ea8b-149">Estimate the Size of a Table</span></span>](../databases/estimate-the-size-of-a-table.md)  
  
 [<span data-ttu-id="6ea8b-150">Stima delle dimensioni di un indice cluster</span><span class="sxs-lookup"><span data-stu-id="6ea8b-150">Estimate the Size of a Clustered Index</span></span>](../databases/estimate-the-size-of-a-clustered-index.md)  
  
 [<span data-ttu-id="6ea8b-151">Stima delle dimensioni di un indice non cluster</span><span class="sxs-lookup"><span data-stu-id="6ea8b-151">Estimate the Size of a Nonclustered Index</span></span>](../databases/estimate-the-size-of-a-nonclustered-index.md)  
  
 [<span data-ttu-id="6ea8b-152">Stimare le dimensioni di un heap</span><span class="sxs-lookup"><span data-stu-id="6ea8b-152">Estimate the Size of a Heap</span></span>](../databases/estimate-the-size-of-a-heap.md)  
  
## <a name="related-content"></a><span data-ttu-id="6ea8b-153">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="6ea8b-153">Related Content</span></span>  
 [<span data-ttu-id="6ea8b-154">CREATE INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="6ea8b-154">CREATE INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-index-transact-sql)  
  
 [<span data-ttu-id="6ea8b-155">ALTER INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="6ea8b-155">ALTER INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-index-transact-sql)  
  
 [<span data-ttu-id="6ea8b-156">DROP INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="6ea8b-156">DROP INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-index-transact-sql)  
  
 [<span data-ttu-id="6ea8b-157">Specificare un fattore di riempimento per un indice</span><span class="sxs-lookup"><span data-stu-id="6ea8b-157">Specify Fill Factor for an Index</span></span>](specify-fill-factor-for-an-index.md)  
  
 [<span data-ttu-id="6ea8b-158">Riorganizzare e ricompilare gli indici</span><span class="sxs-lookup"><span data-stu-id="6ea8b-158">Reorganize and Rebuild Indexes</span></span>](indexes.md)  
  
  
