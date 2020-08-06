---
title: Disabilitare indici e vincoli | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
f1_keywords:
- sql12.swb.disableindexes.f1
helpviewer_keywords:
- disabled indexes [SQL Server], index operations
- nonclustered indexes [SQL Server], disabling
- disabled indexes [SQL Server], guidelines
- clustered indexes, disabling
- constraints [SQL Server], disabling
- disabled indexes [SQL Server], viewing
- FOREIGN KEY constraints, disabling
- statistical information [SQL Server], indexes
- index disabling [SQL Server]
- indexed views [SQL Server], disabled indexes
ms.assetid: 2198f1af-fa44-47e9-92df-f4fde322ba18
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 40f9de4108be4defeb2353a9e7835c289641a819
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724604"
---
# <a name="disable-indexes-and-constraints"></a><span data-ttu-id="418ed-102">Disabilitazione di indici e vincoli</span><span class="sxs-lookup"><span data-stu-id="418ed-102">Disable Indexes and Constraints</span></span>
  <span data-ttu-id="418ed-103">In questo argomento si descrive come disabilitare un indice o i vincoli in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="418ed-103">This topic describes how to disable an index or constraints in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="418ed-104">La disabilitazione di un indice impedisce all'utente di accedere all'indice e, per gli indici cluster, ai dati della tabella sottostante.</span><span class="sxs-lookup"><span data-stu-id="418ed-104">Disabling an index prevents user access to the index, and for clustered indexes to the underlying table data.</span></span> <span data-ttu-id="418ed-105">La definizione dell'indice viene mantenuta nei metadati e le statistiche relative all'indice vengono preservate negli indici non cluster.</span><span class="sxs-lookup"><span data-stu-id="418ed-105">The index definition remains in metadata, and index statistics are kept on nonclustered indexes.</span></span> <span data-ttu-id="418ed-106">La disabilitazione di un indice non cluster o cluster di una vista consente di eliminare fisicamente i dati dell'indice.</span><span class="sxs-lookup"><span data-stu-id="418ed-106">Disabling a nonclustered or clustered index on a view physically deletes the index data.</span></span> <span data-ttu-id="418ed-107">La disabilitazione di un indice cluster in una tabella impedisce l'accesso ai dati. Questi ultimi vengono comunque mantenuti nella tabella, ma non sono disponibili per le operazioni DML (Data Manipulation Language) finché l'indice non viene eliminato o ricompilato.</span><span class="sxs-lookup"><span data-stu-id="418ed-107">Disabling a clustered index on a table prevents access to the data; the data still remains in the table, but is unavailable for data manipulation language (DML) operations until the index is dropped or rebuilt.</span></span>  
  
 <span data-ttu-id="418ed-108">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="418ed-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="418ed-109">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="418ed-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="418ed-110">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="418ed-110">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="418ed-111">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="418ed-111">Security</span></span>](#Security)  
  
-   <span data-ttu-id="418ed-112">**Per disabilitare un indice tramite:**</span><span class="sxs-lookup"><span data-stu-id="418ed-112">**To disable an index, using:**</span></span>  
  
     [<span data-ttu-id="418ed-113">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="418ed-113">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="418ed-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="418ed-114">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="418ed-115">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="418ed-115">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="418ed-116">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="418ed-116">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="418ed-117">In caso di disabilitazione, un indice non viene aggiornato.</span><span class="sxs-lookup"><span data-stu-id="418ed-117">The index is not maintained while it is disabled.</span></span>  
  
-   <span data-ttu-id="418ed-118">In Query Optimizer l'indice disabilitato non viene considerato durante la creazione dei piani di esecuzione della query.</span><span class="sxs-lookup"><span data-stu-id="418ed-118">The query optimizer does not consider the disabled index when creating query execution plans.</span></span> <span data-ttu-id="418ed-119">Inoltre, le query che fanno riferimento all'indice disabilitato con un hint di tabella non vengono eseguite correttamente.</span><span class="sxs-lookup"><span data-stu-id="418ed-119">Also, queries that reference the disabled index with a table hint fail.</span></span>  
  
-   <span data-ttu-id="418ed-120">Non è possibile creare un indice assegnandogli lo stesso nome di un indice disabilitato esistente.</span><span class="sxs-lookup"><span data-stu-id="418ed-120">You cannot create an index that uses the same name as an existing disabled index.</span></span>  
  
-   <span data-ttu-id="418ed-121">Un indice disabilitato può essere eliminato.</span><span class="sxs-lookup"><span data-stu-id="418ed-121">A disabled index can be dropped.</span></span>  
  
-   <span data-ttu-id="418ed-122">Quando si disabilita un indice univoco, vengono disabilitati anche il vincolo PRIMARY KEY o UNIQUE e tutti i vincoli FOREIGN KEY che fanno riferimento alle colonne indicizzate di altre tabelle.</span><span class="sxs-lookup"><span data-stu-id="418ed-122">When disabling a unique index, the PRIMARY KEY or UNIQUE constraint and all FOREIGN KEY constraints that reference the indexed columns from other tables are also disabled.</span></span> <span data-ttu-id="418ed-123">Quando si disabilita un indice cluster, vengono disabilitati anche tutti i vincoli FOREIGN KEY in ingresso e in uscita nella tabella sottostante.</span><span class="sxs-lookup"><span data-stu-id="418ed-123">When disabling a clustered index, all incoming and outgoing FOREIGN KEY constraints on the underlying table are also disabled.</span></span> <span data-ttu-id="418ed-124">Quando viene disabilitato l'indice, i nomi dei vincoli vengono elencati in un messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="418ed-124">The constraint names are listed in a warning message when the index is disabled.</span></span> <span data-ttu-id="418ed-125">Dopo aver ricompilato l'indice, è necessario abilitare manualmente tutti i vincoli utilizzando l'istruzione ALTER TABLE CHECK CONSTRAINT.</span><span class="sxs-lookup"><span data-stu-id="418ed-125">After rebuilding the index, all constraints must be manually enabled by using the ALTER TABLE CHECK CONSTRAINT statement.</span></span>  
  
-   <span data-ttu-id="418ed-126">Gli indici non cluster vengono disabilitati automaticamente quando viene disabilitato l'indice cluster associato</span><span class="sxs-lookup"><span data-stu-id="418ed-126">Nonclustered indexes are automatically disabled when the associated clustered index is disabled.</span></span> <span data-ttu-id="418ed-127">e non possono essere abilitati fino all'abilitazione dell'indice cluster nella tabella o nella vista o all'eliminazione dell'indice cluster nella tabella.</span><span class="sxs-lookup"><span data-stu-id="418ed-127">They cannot be enabled until either the clustered index on the table or view is enabled or the clustered index on the table is dropped.</span></span> <span data-ttu-id="418ed-128">Gli indici non cluster devono essere abilitati in modo esplicito, a meno che l'indice cluster non sia stato abilitato utilizzando l'istruzione ALTER INDEX ALL REBUILD.</span><span class="sxs-lookup"><span data-stu-id="418ed-128">Nonclustered indexes must be explicitly enabled, unless the clustered index was enabled by using the ALTER INDEX ALL REBUILD statement.</span></span>  
  
-   <span data-ttu-id="418ed-129">L'istruzione ALTER INDEX ALL REBUILD consente di ricompilare e abilitare tutti gli indici disabilitati nella tabella, ad eccezione degli indici disabilitati nelle viste.</span><span class="sxs-lookup"><span data-stu-id="418ed-129">The ALTER INDEX ALL REBUILD statement rebuilds and enables all disabled indexes on the table, except for disabled indexes on views.</span></span> <span data-ttu-id="418ed-130">Gli indici nelle viste devono essere abilitati in un'istruzione ALTER INDEX ALL REBUILD distinta.</span><span class="sxs-lookup"><span data-stu-id="418ed-130">Indexes on views must be enabled in a separate ALTER INDEX ALL REBUILD statement.</span></span>  
  
-   <span data-ttu-id="418ed-131">La disabilitazione di un indice cluster in una tabella consente di disabilitare anche tutti gli indici cluster e non cluster nelle viste che fanno riferimento a quella tabella.</span><span class="sxs-lookup"><span data-stu-id="418ed-131">Disabling a clustered index on a table also disables all clustered and nonclustered indexes on views that reference that table.</span></span> <span data-ttu-id="418ed-132">Questi indici devono essere ricompilati immediatamente dopo quelli inclusi nella tabella cui viene fatto riferimento.</span><span class="sxs-lookup"><span data-stu-id="418ed-132">These indexes must be rebuilt just as those on the referenced table.</span></span>  
  
-   <span data-ttu-id="418ed-133">È possibile accedere alle righe di dati degli indici cluster disabilitati solo per eliminare o ricompilare l'indice cluster.</span><span class="sxs-lookup"><span data-stu-id="418ed-133">The data rows of the disabled clustered index cannot be accessed except to drop or rebuild the clustered index.</span></span>  
  
-   <span data-ttu-id="418ed-134">È possibile ricompilare online un indice non cluster disabilitato quando nella tabella non è incluso un indice cluster disabilitato.</span><span class="sxs-lookup"><span data-stu-id="418ed-134">You can rebuild a disabled nonclustered index online when the table does not have a disabled clustered index.</span></span> <span data-ttu-id="418ed-135">Tuttavia, è sempre necessario ricompilare offline un indice cluster disabilitato se si utilizza l'istruzione ALTER INDEX REBUILD o CREATE INDEX WITH DROP_EXISTING.</span><span class="sxs-lookup"><span data-stu-id="418ed-135">However, you must always rebuild a disabled clustered index offline if you use either the ALTER INDEX REBUILD or CREATE INDEX WITH DROP_EXISTING statement.</span></span> <span data-ttu-id="418ed-136">Per altre informazioni sulle operazioni online sugli indici, vedere [Eseguire operazioni online sugli indici](perform-index-operations-online.md).</span><span class="sxs-lookup"><span data-stu-id="418ed-136">For more information about online index operations, see [Perform Index Operations Online](perform-index-operations-online.md).</span></span>  
  
-   <span data-ttu-id="418ed-137">L'istruzione CREATE STATISTICS non può essere eseguita correttamente in una tabella in cui è incluso un indice cluster disabilitato.</span><span class="sxs-lookup"><span data-stu-id="418ed-137">The CREATE STATISTICS statement cannot be successfully executed on a table that has a disabled clustered index.</span></span>  
  
-   <span data-ttu-id="418ed-138">L'opzione di database AUTO_CREATE_STATISTICS crea nuove statistiche per una colonna quando l'indice viene disabilitato e si verificano le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="418ed-138">The AUTO_CREATE_STATISTICS database option creates new statistics on a column when the index is disabled and the following conditions exist:</span></span>  
  
    -   <span data-ttu-id="418ed-139">L'opzione AUTO_CREATE_STATISTICS è impostata su ON</span><span class="sxs-lookup"><span data-stu-id="418ed-139">AUTO_CREATE_STATISTICS is set to ON</span></span>  
  
    -   <span data-ttu-id="418ed-140">Non è disponibile alcuna statistica esistente per la colonna.</span><span class="sxs-lookup"><span data-stu-id="418ed-140">There are no existing statistics for the column.</span></span>  
  
    -   <span data-ttu-id="418ed-141">Le statistiche sono necessarie durante l'ottimizzazione delle query.</span><span class="sxs-lookup"><span data-stu-id="418ed-141">Statistics are required during query optimization.</span></span>  
  
-   <span data-ttu-id="418ed-142">Se un indice cluster è disabilitato, tramite l'istruzione [DBCC CHECKDB](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) non possono essere restituite informazioni sulla tabella sottostante, ma può essere indicato che l'indice cluster è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="418ed-142">If a clustered index is disabled, [DBCC CHECKDB](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) cannot return information about the underlying table; instead, the statement reports that the clustered index is disabled.</span></span> <span data-ttu-id="418ed-143">L'istruzione[DBCC INDEXDEFRAG](/sql/t-sql/database-console-commands/dbcc-indexdefrag-transact-sql) non può essere utilizzata per deframmentare un indice disabilitato, altrimenti l'operazione non viene completata e viene visualizzato un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="418ed-143">[DBCC INDEXDEFRAG](/sql/t-sql/database-console-commands/dbcc-indexdefrag-transact-sql) cannot be used to defragment a disabled index; the statement fails with an error message.</span></span> <span data-ttu-id="418ed-144">Per ricompilare un indice disabilitato, è possibile utilizzare l'istruzione [DBCC DBREINDEX](/sql/t-sql/database-console-commands/dbcc-dbreindex-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="418ed-144">You can use [DBCC DBREINDEX](/sql/t-sql/database-console-commands/dbcc-dbreindex-transact-sql) to rebuild a disabled index.</span></span>  
  
-   <span data-ttu-id="418ed-145">La creazione di un nuovo indice cluster comporta l'abilitazione degli indici non cluster disabilitati precedentemente.</span><span class="sxs-lookup"><span data-stu-id="418ed-145">Creating a new clustered index enables previously disabled nonclustered indexes.</span></span> <span data-ttu-id="418ed-146">Per altre informazioni, vedere [Enable Indexes and Constraints](enable-indexes-and-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="418ed-146">For more information, see [Enable Indexes and Constraints](enable-indexes-and-constraints.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="418ed-147">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="418ed-147">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="418ed-148">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="418ed-148">Permissions</span></span>  
 <span data-ttu-id="418ed-149">Per eseguire l'istruzione ALTER INDEX, è necessario disporre almeno dell'autorizzazione ALTER per la tabella o la vista.</span><span class="sxs-lookup"><span data-stu-id="418ed-149">To execute ALTER INDEX, at a minimum, ALTER permission on the table or view is required.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="418ed-150">Con SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="418ed-150">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-disable-an-index"></a><span data-ttu-id="418ed-151">Per disabilitare un indice</span><span class="sxs-lookup"><span data-stu-id="418ed-151">To disable an index</span></span>  
  
1.  <span data-ttu-id="418ed-152">In Esplora oggetti fare clic sul segno più per espandere il database contenente la tabella in cui si desidera disabilitare un indice.</span><span class="sxs-lookup"><span data-stu-id="418ed-152">In Object Explorer, click the plus sign to expand the database that contains the table on which you want to disable an index.</span></span>  
  
2.  <span data-ttu-id="418ed-153">Fare clic sul segno più per espandere la cartella **Tabelle** .</span><span class="sxs-lookup"><span data-stu-id="418ed-153">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="418ed-154">Fare clic sul segno più per espandere la tabella in cui si desidera disabilitare un indice.</span><span class="sxs-lookup"><span data-stu-id="418ed-154">Click the plus sign to expand the table on which you want to disable an index.</span></span>  
  
4.  <span data-ttu-id="418ed-155">Fare clic sul segno più per espandere la cartella **Indici** .</span><span class="sxs-lookup"><span data-stu-id="418ed-155">Click the plus sign to expand the **Indexes** folder.</span></span>  
  
5.  <span data-ttu-id="418ed-156">Fare clic con il pulsante destro del mouse sull'indice che si vuole disabilitare e selezionare **Disabilita**.</span><span class="sxs-lookup"><span data-stu-id="418ed-156">Right-click the index you want to disable and select **Disable**.</span></span>  
  
6.  <span data-ttu-id="418ed-157">Nella finestra di dialogo **Disabilita indici** verificare che nella griglia **Indici da disabilitare** sia presente l'indice corretto e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="418ed-157">In the **Disable Indexes** dialog box, verify that the correct index is in the **Indexes to disable** grid and click **OK**.</span></span>  
  
#### <a name="to-disable-all-indexes-on-a-table"></a><span data-ttu-id="418ed-158">Per disabilitare tutti gli indici di una tabella</span><span class="sxs-lookup"><span data-stu-id="418ed-158">To disable all indexes on a table</span></span>  
  
1.  <span data-ttu-id="418ed-159">In Esplora oggetti fare clic sul segno più per espandere il database contenente la tabella in cui si desidera disabilitare gli indici.</span><span class="sxs-lookup"><span data-stu-id="418ed-159">In Object Explorer, click the plus sign to expand the database that contains the table on which you want to disable the indexes.</span></span>  
  
2.  <span data-ttu-id="418ed-160">Fare clic sul segno più per espandere la cartella **Tabelle** .</span><span class="sxs-lookup"><span data-stu-id="418ed-160">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="418ed-161">Fare clic sul segno più per espandere la tabella in cui si desidera disabilitare gli indici.</span><span class="sxs-lookup"><span data-stu-id="418ed-161">Click the plus sign to expand the table on which you want to disable the indexes.</span></span>  
  
4.  <span data-ttu-id="418ed-162">Fare clic con il pulsante destro del mouse sulla cartella **Indici** e selezionare **Disabilita tutti**.</span><span class="sxs-lookup"><span data-stu-id="418ed-162">Right-click the **Indexes** folder and select **Disable All**.</span></span>  
  
5.  <span data-ttu-id="418ed-163">Nella finestra di dialogo **Disabilita indici** verificare che nella griglia **Indici da disabilitare** siano presenti gli indici corretti e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="418ed-163">In the **Disable Indexes** dialog box, verify that the correct indexes are in the **Indexes to disable** grid and click **OK**.</span></span> <span data-ttu-id="418ed-164">Per rimuovere un indice dalla griglia **Indici da disabilitare** , selezionare l'indice desiderato, quindi premere il tasto CANC.</span><span class="sxs-lookup"><span data-stu-id="418ed-164">To remove an index from the **Indexes to disable** grid, select the index and then press the Delete key.</span></span>  
  
 <span data-ttu-id="418ed-165">Le informazioni seguenti sono disponibili nella finestra di dialogo **Disabilita indici** :</span><span class="sxs-lookup"><span data-stu-id="418ed-165">The following information is available in the **Disable Indexes** dialog box:</span></span>  
  
 <span data-ttu-id="418ed-166">**Index Name**</span><span class="sxs-lookup"><span data-stu-id="418ed-166">**Index Name**</span></span>  
 <span data-ttu-id="418ed-167">Consente di visualizzare il nome dell'indice.</span><span class="sxs-lookup"><span data-stu-id="418ed-167">Displays the name of the index.</span></span> <span data-ttu-id="418ed-168">Durante l'esecuzione, in questa colonna viene anche visualizzata un'icona che ne indica lo stato.</span><span class="sxs-lookup"><span data-stu-id="418ed-168">During execution, this column also displays an icon representing the status.</span></span>  
  
 <span data-ttu-id="418ed-169">**Nome tabella**</span><span class="sxs-lookup"><span data-stu-id="418ed-169">**Table Name**</span></span>  
 <span data-ttu-id="418ed-170">Visualizza il nome della tabella o della vista in cui l'indice è stato creato.</span><span class="sxs-lookup"><span data-stu-id="418ed-170">Displays the name of the table or view that the index was created on.</span></span>  
  
 <span data-ttu-id="418ed-171">**Tipo di indice**</span><span class="sxs-lookup"><span data-stu-id="418ed-171">**Index Type**</span></span>  
 <span data-ttu-id="418ed-172">Visualizza il tipo di indice: **Cluster**, **Non cluster**, **Spaziale**o **XML**.</span><span class="sxs-lookup"><span data-stu-id="418ed-172">Displays the type of the index: **Clustered**, **Nonclustered**, **Spatial**, or **XML**.</span></span>  
  
 <span data-ttu-id="418ed-173">**Status**</span><span class="sxs-lookup"><span data-stu-id="418ed-173">**Status**</span></span>  
 <span data-ttu-id="418ed-174">Visualizza lo stato dell'operazione di disabilitazione.</span><span class="sxs-lookup"><span data-stu-id="418ed-174">Displays the status of the disable operation.</span></span> <span data-ttu-id="418ed-175">I valori possibili al termine dell'esecuzione sono:</span><span class="sxs-lookup"><span data-stu-id="418ed-175">Possible values after execution are:</span></span>  
  
-   <span data-ttu-id="418ed-176">Vuoto</span><span class="sxs-lookup"><span data-stu-id="418ed-176">Blank</span></span>  
  
     <span data-ttu-id="418ed-177">Prima dell'esecuzione l'indicazione **Stato** è vuota.</span><span class="sxs-lookup"><span data-stu-id="418ed-177">Prior to execution **Status** is blank.</span></span>  
  
-   <span data-ttu-id="418ed-178">**In corso**</span><span class="sxs-lookup"><span data-stu-id="418ed-178">**In progress**</span></span>  
  
     <span data-ttu-id="418ed-179">L'operazione di disabilitazione degli indici è stata avviata ma non ancora completata.</span><span class="sxs-lookup"><span data-stu-id="418ed-179">Disabling of the indexes has been started but is not complete.</span></span>  
  
-   <span data-ttu-id="418ed-180">**Success**</span><span class="sxs-lookup"><span data-stu-id="418ed-180">**Success**</span></span>  
  
     <span data-ttu-id="418ed-181">L'operazione di disabilitazione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="418ed-181">The disable operation completed successfully.</span></span>  
  
-   <span data-ttu-id="418ed-182">**Error (Errore) (Error (Errore)e)**</span><span class="sxs-lookup"><span data-stu-id="418ed-182">**Error**</span></span>  
  
     <span data-ttu-id="418ed-183">Si è verificato un errore durante la disabilitazione degli indici e non è stato possibile completare correttamente l'operazione.</span><span class="sxs-lookup"><span data-stu-id="418ed-183">An error was encountered during the index disable operation, and the operation did not complete successfully.</span></span>  
  
-   <span data-ttu-id="418ed-184">**Stopped**</span><span class="sxs-lookup"><span data-stu-id="418ed-184">**Stopped**</span></span>  
  
     <span data-ttu-id="418ed-185">La disabilitazione dell'indice non è stata completata poiché l'operazione è stata arrestata dall'utente.</span><span class="sxs-lookup"><span data-stu-id="418ed-185">The disable of the index was not completed successfully because the user stopped the operation.</span></span>  
  
 <span data-ttu-id="418ed-186">**Messaggio**</span><span class="sxs-lookup"><span data-stu-id="418ed-186">**Message**</span></span>  
 <span data-ttu-id="418ed-187">Visualizza il testo dei messaggi di errore generati durante l'operazione.</span><span class="sxs-lookup"><span data-stu-id="418ed-187">Provides the text of error messages during the disable operation.</span></span> <span data-ttu-id="418ed-188">Durante l'esecuzione dell'operazione, gli errori vengono visualizzati come collegamenti ipertestuali.</span><span class="sxs-lookup"><span data-stu-id="418ed-188">During execution, errors appear as hyperlinks.</span></span> <span data-ttu-id="418ed-189">Nel testo di tali collegamenti è descritto l'errore verificatosi.</span><span class="sxs-lookup"><span data-stu-id="418ed-189">The text of the hyperlinks describes the body of the error.</span></span> <span data-ttu-id="418ed-190">La colonna **Messaggio** in genere non è sufficientemente ampia per contenere il testo completo del messaggio.</span><span class="sxs-lookup"><span data-stu-id="418ed-190">The **Message** column is rarely wide enough to read the full message text.</span></span> <span data-ttu-id="418ed-191">Per leggere il messaggio completo, eseguire una delle seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="418ed-191">There are two ways to get the full text:</span></span>  
  
-   <span data-ttu-id="418ed-192">Spostare il puntatore del mouse sulla cella del messaggio per visualizzare una descrizione comando contenente il testo dell'errore.</span><span class="sxs-lookup"><span data-stu-id="418ed-192">Move the mouse pointer over the message cell to display a ToolTip with the error text.</span></span>  
  
-   <span data-ttu-id="418ed-193">Fare clic sul collegamento ipertestuale per visualizzare una finestra di dialogo contenente l'errore completo.</span><span class="sxs-lookup"><span data-stu-id="418ed-193">Click the hyperlink to display a dialog box displaying the full error.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="418ed-194">Con Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="418ed-194">Using Transact-SQL</span></span>  
  
#### <a name="to-disable-an-index"></a><span data-ttu-id="418ed-195">Per disabilitare un indice</span><span class="sxs-lookup"><span data-stu-id="418ed-195">To disable an index</span></span>  
  
1.  <span data-ttu-id="418ed-196">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="418ed-196">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="418ed-197">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="418ed-197">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="418ed-198">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="418ed-198">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- disables the IX_Employee_OrganizationLevel_OrganizationNode index  
    -- on the HumanResources.Employee table  
    ALTER INDEX IX_Employee_OrganizationLevel_OrganizationNode ON HumanResources.Employee  
    DISABLE;  
    ```  
  
#### <a name="to-disable-all-indexes-on-a-table"></a><span data-ttu-id="418ed-199">Per disabilitare tutti gli indici di una tabella</span><span class="sxs-lookup"><span data-stu-id="418ed-199">To disable all indexes on a table</span></span>  
  
1.  <span data-ttu-id="418ed-200">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="418ed-200">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="418ed-201">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="418ed-201">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="418ed-202">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="418ed-202">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Disables all indexes on the HumanResources.Employee table.  
    ALTER INDEX ALL ON HumanResources.Employee  
    DISABLE;  
    ```  
  
 <span data-ttu-id="418ed-203">Per altre informazioni, vedere [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="418ed-203">For more information, see [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span></span>  
  
  
