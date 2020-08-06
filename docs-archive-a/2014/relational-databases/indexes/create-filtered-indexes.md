---
title: Creare indici filtrati | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- filtered indexes [SQL Server], about filtered indexes
- designing indexes [SQL Server], filtered
- filtered indexes [SQL Server]
- nonclustered indexes [SQL Server], filtered
- indexes [SQL Server], filtered
ms.assetid: 25e1fcc5-45d7-4c53-8c79-5493dfaa1c74
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 77cf641ca84181496f26a995244029d0525ade63
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724643"
---
# <a name="create-filtered-indexes"></a><span data-ttu-id="de15b-102">Creare indici filtrati</span><span class="sxs-lookup"><span data-stu-id="de15b-102">Create Filtered Indexes</span></span>
  <span data-ttu-id="de15b-103">In questo argomento si descrive come creare un indice filtrato in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="de15b-103">This topic describes how to create a filtered index in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="de15b-104">Un indice filtrato è un indice non cluster ottimizzato, particolarmente indicato per coprire query per le quali i dati vengono selezionati da un subset ben definito.</span><span class="sxs-lookup"><span data-stu-id="de15b-104">A filtered index is an optimized nonclustered index especially suited to cover queries that select from a well-defined subset of data.</span></span> <span data-ttu-id="de15b-105">Un indice di questo tipo utilizza un predicato del filtro per indicizzare una parte di righe nella tabella.</span><span class="sxs-lookup"><span data-stu-id="de15b-105">It uses a filter predicate to index a portion of rows in the table.</span></span> <span data-ttu-id="de15b-106">Se confrontato con indici di tabella completa, un indice filtrato progettato correttamente consente di migliorare le prestazioni delle query e di ridurre i costi di gestione e di archiviazione dell'indice stesso.</span><span class="sxs-lookup"><span data-stu-id="de15b-106">A well-designed filtered index can improve query performance as well as reduce index maintenance and storage costs compared with full-table indexes.</span></span>  
  
 <span data-ttu-id="de15b-107">Rispetto agli indici di tabella completa, gli indici filtrati consentono di ottenere i vantaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="de15b-107">Filtered indexes can provide the following advantages over full-table indexes:</span></span>  
  
-   <span data-ttu-id="de15b-108">**Prestazioni di esecuzione delle query e qualità del piano migliorate**</span><span class="sxs-lookup"><span data-stu-id="de15b-108">**Improved query performance and plan quality**</span></span>  
  
     <span data-ttu-id="de15b-109">Un indice filtrato progettato correttamente migliora le prestazioni di esecuzione delle query e la qualità del piano di esecuzione poiché è caratterizzato da dimensioni minori rispetto a un indice non cluster di tabella completa e dispone di statistiche filtrate.</span><span class="sxs-lookup"><span data-stu-id="de15b-109">A well-designed filtered index improves query performance and execution plan quality because it is smaller than a full-table nonclustered index and has filtered statistics.</span></span> <span data-ttu-id="de15b-110">Queste ultime sono più accurate delle statistiche di tabella completa poiché coprono solo le righe nell'indice filtrato.</span><span class="sxs-lookup"><span data-stu-id="de15b-110">The filtered statistics are more accurate than full-table statistics because they cover only the rows in the filtered index.</span></span>  
  
-   <span data-ttu-id="de15b-111">**Costi di manutenzione dell'indice ridotti**</span><span class="sxs-lookup"><span data-stu-id="de15b-111">**Reduced index maintenance costs**</span></span>  
  
     <span data-ttu-id="de15b-112">La manutenzione di un indice viene eseguita solo quando le istruzioni DML (Data Manipulation Language) influiscono sui dati relativi all'indice.</span><span class="sxs-lookup"><span data-stu-id="de15b-112">An index is maintained only when data manipulation language (DML) statements affect the data in the index.</span></span> <span data-ttu-id="de15b-113">Un indice filtrato consente di ridurre i costi di gestione rispetto a un indice non cluster di tabella completa poiché è caratterizzato da dimensioni minori e viene gestito solo se i dati relativi vengono modificati.</span><span class="sxs-lookup"><span data-stu-id="de15b-113">A filtered index reduces index maintenance costs compared with a full-table nonclustered index because it is smaller and is only maintained when the data in the index is changed.</span></span> <span data-ttu-id="de15b-114">È possibile disporre di un numero elevato di indici filtrati, soprattutto quando in essi sono contenuti dati modificati raramente.</span><span class="sxs-lookup"><span data-stu-id="de15b-114">It is possible to have a large number of filtered indexes, especially when they contain data that is changed infrequently.</span></span> <span data-ttu-id="de15b-115">In modo analogo, se in un indice filtrato sono contenuti solo i dati modificati di frequente, la dimensione minore dell'indice consente di ridurre il costo di aggiornamento delle statistiche.</span><span class="sxs-lookup"><span data-stu-id="de15b-115">Similarly, if a filtered index contains only the frequently modified data, the smaller size of the index reduces the cost of updating the statistics.</span></span>  
  
-   <span data-ttu-id="de15b-116">**Costi di archiviazione dell'indice ridotti**</span><span class="sxs-lookup"><span data-stu-id="de15b-116">**Reduced index storage costs**</span></span>  
  
     <span data-ttu-id="de15b-117">La creazione di un indice filtrato può ridurre lo spazio di archiviazione su disco per gli indici non cluster nel caso in cui non sia necessario un indice di tabella completa.</span><span class="sxs-lookup"><span data-stu-id="de15b-117">Creating a filtered index can reduce disk storage for nonclustered indexes when a full-table index is not necessary.</span></span> <span data-ttu-id="de15b-118">È possibile sostituire un indice non cluster di tabella completa con più indici filtrati senza aumentare in modo significativo i requisiti di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="de15b-118">You can replace a full-table nonclustered index with multiple filtered indexes without significantly increasing the storage requirements.</span></span>  
  
 <span data-ttu-id="de15b-119">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="de15b-119">**In This Topic**</span></span>  
  
-   <span data-ttu-id="de15b-120">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="de15b-120">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="de15b-121">Considerazioni sulla progettazione</span><span class="sxs-lookup"><span data-stu-id="de15b-121">Design Considerations</span></span>](#Design)  
  
     [<span data-ttu-id="de15b-122">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="de15b-122">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="de15b-123">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="de15b-123">Security</span></span>](#Security)  
  
-   <span data-ttu-id="de15b-124">**Per creare un indice filtrato tramite:**</span><span class="sxs-lookup"><span data-stu-id="de15b-124">**To create a filtered index, using:**</span></span>  
  
     [<span data-ttu-id="de15b-125">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="de15b-125">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="de15b-126">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="de15b-126">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="de15b-127">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="de15b-127">Before You Begin</span></span>  
  
###  <a name="design-considerations"></a><a name="Design"></a> <span data-ttu-id="de15b-128">Considerazioni sulla progettazione</span><span class="sxs-lookup"><span data-stu-id="de15b-128">Design Considerations</span></span>  
  
-   <span data-ttu-id="de15b-129">Quando una colonna dispone solo di un numero ridotto di valori rilevanti per le query, è possibile creare un indice filtrato sul subset di valori.</span><span class="sxs-lookup"><span data-stu-id="de15b-129">When a column only has a small number of relevant values for queries, you can create a filtered index on the subset of values.</span></span> <span data-ttu-id="de15b-130">Ad esempio, quando la maggior parte dei valori di una colonna è costituita da valori NULL e la query esegue la selezione solo dai valori non NULL, è possibile creare un indice filtrato per le righe di dati non NULL.</span><span class="sxs-lookup"><span data-stu-id="de15b-130">For example, when the values in a column are mostly NULL and the query selects only from the non-NULL values, you can create a filtered index for the non-NULL data rows.</span></span> <span data-ttu-id="de15b-131">L'indice risultante sarà minore e sarà possibile gestirlo con costi ridotti rispetto a un indice non cluster di tabella completa definito sulle stesse colonne chiave.</span><span class="sxs-lookup"><span data-stu-id="de15b-131">The resulting index will be smaller and cost less to maintain than a full-table nonclustered index defined on the same key columns.</span></span>  
  
-   <span data-ttu-id="de15b-132">Se in una tabella sono presenti righe di dati eterogenei, è possibile creare un indice filtrato per una o più categorie di dati.</span><span class="sxs-lookup"><span data-stu-id="de15b-132">When a table has heterogeneous data rows, you can create a filtered index for one or more categories of data.</span></span> <span data-ttu-id="de15b-133">In questo modo è possibile migliorare le prestazioni delle query in queste righe di dati restringendo lo stato attivo di una query a un'area specifica della tabella.</span><span class="sxs-lookup"><span data-stu-id="de15b-133">This can improve the performance of queries on these data rows by narrowing the focus of a query to a specific area of the table.</span></span> <span data-ttu-id="de15b-134">L'indice risultante sarà di nuovo più piccolo e sarà possibile gestirlo con costi ridotti rispetto a un indice non cluster di tabella completa.</span><span class="sxs-lookup"><span data-stu-id="de15b-134">Again, the resulting index will be smaller and cost less to maintain than a full-table nonclustered index.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="de15b-135">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="de15b-135">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="de15b-136">Non è possibile creare un indice filtrato in una vista.</span><span class="sxs-lookup"><span data-stu-id="de15b-136">You cannot create a filtered index on a view.</span></span> <span data-ttu-id="de15b-137">Con Query Optimizer è tuttavia possibile sfruttare i vantaggi offerti da un indice filtrato definito in una tabella a cui si fa riferimento in una vista</span><span class="sxs-lookup"><span data-stu-id="de15b-137">However, the query optimizer can benefit from a filtered index defined on a table that is referenced in a view.</span></span> <span data-ttu-id="de15b-138">e, se i risultati della query saranno corretti, viene considerato un indice filtrato per una query per la quale la selezione viene effettuata da una vista.</span><span class="sxs-lookup"><span data-stu-id="de15b-138">The query optimizer considers a filtered index for a query that selects from a view if the query results will be correct.</span></span>  
  
-   <span data-ttu-id="de15b-139">Rispetto alle viste indicizzate gli indici filtrati offrono i vantaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="de15b-139">Filtered indexes have the following advantages over indexed views:</span></span>  
  
    -   <span data-ttu-id="de15b-140">Costi di manutenzione dell'indice ridotti.</span><span class="sxs-lookup"><span data-stu-id="de15b-140">Reduced index maintenance costs.</span></span> <span data-ttu-id="de15b-141">Query Processor, ad esempio, utilizza una quantità inferiore di risorse della CPU per aggiornare un indice filtrato rispetto a una vista indicizzata.</span><span class="sxs-lookup"><span data-stu-id="de15b-141">For example, the query processor uses fewer CPU resources to update a filtered index than an indexed view.</span></span>  
  
    -   <span data-ttu-id="de15b-142">Qualità del piano migliorata.</span><span class="sxs-lookup"><span data-stu-id="de15b-142">Improved plan quality.</span></span> <span data-ttu-id="de15b-143">Durante la compilazione della query, ad esempio, Query Optimizer preferisce in molte situazioni utilizzare l'indice filtrato anziché la vista indicizzata equivalente.</span><span class="sxs-lookup"><span data-stu-id="de15b-143">For example, during query compilation, the query optimizer considers using a filtered index in more situations than the equivalent indexed view.</span></span>  
  
    -   <span data-ttu-id="de15b-144">L'indice online viene ricompilato.</span><span class="sxs-lookup"><span data-stu-id="de15b-144">Online index rebuilds.</span></span> <span data-ttu-id="de15b-145">È possibile ricompilare gli indici filtrati mentre sono disponibili per le query.</span><span class="sxs-lookup"><span data-stu-id="de15b-145">You can rebuild filtered indexes while they are available for queries.</span></span> <span data-ttu-id="de15b-146">La ricompilazione dell'indice online non è supportata per le viste indicizzate.</span><span class="sxs-lookup"><span data-stu-id="de15b-146">Online index rebuilds are not supported for indexed views.</span></span> <span data-ttu-id="de15b-147">Per altre informazioni, vedere l'opzione REBUILD per [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="de15b-147">For more information, see the REBUILD option for [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span></span>  
  
    -   <span data-ttu-id="de15b-148">Indici non univoci.</span><span class="sxs-lookup"><span data-stu-id="de15b-148">Non-unique indexes.</span></span> <span data-ttu-id="de15b-149">Gli indici filtrati possono essere non univoci, mentre le viste indicizzate devono essere univoche.</span><span class="sxs-lookup"><span data-stu-id="de15b-149">Filtered indexes can be non-unique, whereas indexed views must be unique.</span></span>  
  
-   <span data-ttu-id="de15b-150">Gli indici filtrati sono definiti in una tabella e supportano solo operatori di confronto semplici.</span><span class="sxs-lookup"><span data-stu-id="de15b-150">Filtered indexes are defined on one table and only support simple comparison operators.</span></span> <span data-ttu-id="de15b-151">Se è necessaria un'espressione di filtro in cui viene fatto riferimento a più tabelle o in cui è presente della logica complessa, è necessario creare una vista.</span><span class="sxs-lookup"><span data-stu-id="de15b-151">If you need a filter expression that references multiple tables or has complex logic, you should create a view.</span></span>  
  
-   <span data-ttu-id="de15b-152">Non è necessario che una colonna nell'espressione che definisce l'indice filtrato sia una colonna chiave o inclusa nella definizione dell'indice stesso se l'espressione che definisce l'indice filtrato è equivalente al predicato della query e la query non restituisce la colonna in tale espressione con i risultati della query.</span><span class="sxs-lookup"><span data-stu-id="de15b-152">A column in the filtered index expression does not need to be a key or included column in the filtered index definition if the filtered index expression is equivalent to the query predicate and the query does not return the column in the filtered index expression with the query results.</span></span>  
  
-   <span data-ttu-id="de15b-153">Una colonna nell'espressione che definisce l'indice filtrato deve essere una colonna chiave o inclusa nella definizione dell'indice se il predicato della query la utilizza in un confronto non equivalente all'espressione che definisce l'indice filtrato.</span><span class="sxs-lookup"><span data-stu-id="de15b-153">A column in the filtered index expression should be a key or included column in the filtered index definition if the query predicate uses the column in a comparison that is not equivalent to the filtered index expression.</span></span>  
  
-   <span data-ttu-id="de15b-154">Una colonna nell'espressione che definisce l'indice filtrato deve essere una colonna chiave o inclusa nella definizione dell'indice se è presente nel set di risultati della query.</span><span class="sxs-lookup"><span data-stu-id="de15b-154">A column in the filtered index expression should be a key or included column in the filtered index definition if the column is in the query result set.</span></span>  
  
-   <span data-ttu-id="de15b-155">Non è necessario che la chiave di indice cluster della tabella sia una colonna chiave o inclusa nella definizione dell'indice filtrato</span><span class="sxs-lookup"><span data-stu-id="de15b-155">The clustered index key of the table does not need to be a key or included column in the filtered index definition.</span></span> <span data-ttu-id="de15b-156">poiché viene inclusa automaticamente in tutti gli indici non cluster, inclusi quelli filtrati.</span><span class="sxs-lookup"><span data-stu-id="de15b-156">The clustered index key is automatically included in all nonclustered indexes, including filtered indexes.</span></span>  
  
-   <span data-ttu-id="de15b-157">Se l'operatore di confronto specificato nell'espressione che definisce l'indice filtrato determina una conversione dei dati implicita o esplicita, si verificherà un errore se la conversione viene eseguita sul lato sinistro di un operatore di confronto.</span><span class="sxs-lookup"><span data-stu-id="de15b-157">If the comparison operator specified in the filtered index expression of the filtered index results in an implicit or explicit data conversion, an error will occur if the conversion occurs on the left side of a comparison operator.</span></span> <span data-ttu-id="de15b-158">Una soluzione consiste nello scrivere l'espressione che definisce l'indice filtrato con l'operatore di conversione dei dati (CAST o CONVERT) sul lato destro dell'operatore di confronto.</span><span class="sxs-lookup"><span data-stu-id="de15b-158">A solution is to write the filtered index expression with the data conversion operator (CAST or CONVERT) on the right side of the comparison operator.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="de15b-159">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="de15b-159">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="de15b-160">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="de15b-160">Permissions</span></span>  
 <span data-ttu-id="de15b-161">È richiesta l'autorizzazione ALTER per la tabella o la vista.</span><span class="sxs-lookup"><span data-stu-id="de15b-161">Requires ALTER permission on the table or view.</span></span> <span data-ttu-id="de15b-162">L'utente deve essere un membro del ruolo predefinito del server **sysadmin** o dei ruoli predefiniti del database **db_ddladmin** e **db_owner** .</span><span class="sxs-lookup"><span data-stu-id="de15b-162">User must be a member of the **sysadmin** fixed server role or the **db_ddladmin** and **db_owner** fixed database roles.</span></span> <span data-ttu-id="de15b-163">Per modificare l'espressione dell'indice filtrato, utilizzare CREATE INDEX WITH DROP_EXISTING.</span><span class="sxs-lookup"><span data-stu-id="de15b-163">To modify the filtered index expression, use CREATE INDEX WITH DROP_EXISTING.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="de15b-164">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="de15b-164">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-filtered-index"></a><span data-ttu-id="de15b-165">Per creare un indice filtrato</span><span class="sxs-lookup"><span data-stu-id="de15b-165">To create a filtered index</span></span>  
  
1.  <span data-ttu-id="de15b-166">In Esplora oggetti fare clic sul segno più per espandere il database contenente la tabella in cui si desidera creare un indice filtrato.</span><span class="sxs-lookup"><span data-stu-id="de15b-166">In Object Explorer, click the plus sign to expand the database that contains the table on which you want to create a filtered index.</span></span>  
  
2.  <span data-ttu-id="de15b-167">Fare clic sul segno più per espandere la cartella **Tabelle** .</span><span class="sxs-lookup"><span data-stu-id="de15b-167">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="de15b-168">Fare clic sul segno più per espandere la tabella in cui si desidera creare un indice filtrato.</span><span class="sxs-lookup"><span data-stu-id="de15b-168">Click the plus sign to expand the table on which you want to create a filtered index.</span></span>  
  
4.  <span data-ttu-id="de15b-169">Fare clic con il pulsante destro del mouse sulla cartella **Indici**, scegliere **Nuovo indice**e selezionare **Indice non cluster**.</span><span class="sxs-lookup"><span data-stu-id="de15b-169">Right-click the **Indexes** folder, point to **New Index**, and select **Non-Clustered Index...**.</span></span>  
  
5.  <span data-ttu-id="de15b-170">Nella pagina **Generale** della finestra di dialogo **Nuovo indice** immettere il nome del nuovo indice nella casella **Nome indice** .</span><span class="sxs-lookup"><span data-stu-id="de15b-170">In the **New Index** dialog box, on the **General** page, enter the name of the new index in the **Index name** box.</span></span>  
  
6.  <span data-ttu-id="de15b-171">In **Colonne chiave indice**fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="de15b-171">Under **Index key columns**, click **Add...**.</span></span>  
  
7.  <span data-ttu-id="de15b-172">Nella finestra di dialogo **Seleziona colonne da**_table_name_ Selezionare le caselle di controllo delle colonne della tabella da aggiungere all'indice univoco.</span><span class="sxs-lookup"><span data-stu-id="de15b-172">In the **Select Columns from**_table_name_ dialog box, select the check box or check boxes of the table column or columns to be added to the unique index.</span></span>  
  
8.  <span data-ttu-id="de15b-173">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="de15b-173">Click **OK**.</span></span>  
  
9. <span data-ttu-id="de15b-174">Nella pagina **Filtro** immettere l'espressione SQL che verrà usata per creare l'indice filtrato in **Espressione filtro**.</span><span class="sxs-lookup"><span data-stu-id="de15b-174">On the **Filter** page, under **Filter Expression**, enter SQL expression that you'll use to create the filtered index.</span></span>  
  
10. <span data-ttu-id="de15b-175">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="de15b-175">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="de15b-176">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="de15b-176">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-filtered-index"></a><span data-ttu-id="de15b-177">Per creare un indice filtrato</span><span class="sxs-lookup"><span data-stu-id="de15b-177">To create a filtered index</span></span>  
  
1.  <span data-ttu-id="de15b-178">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="de15b-178">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="de15b-179">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="de15b-179">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="de15b-180">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="de15b-180">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Looks for an existing filtered index named "FIBillOfMaterialsWithEndDate"  
    -- and deletes it from the table Production.BillOfMaterials if found.   
    IF EXISTS (SELECT name FROM sys.indexes  
        WHERE name = N'FIBillOfMaterialsWithEndDate'  
        AND object_id = OBJECT_ID (N'Production.BillOfMaterials'))  
    DROP INDEX FIBillOfMaterialsWithEndDate  
        ON Production.BillOfMaterials  
    GO  
    -- Creates a filtered index "FIBillOfMaterialsWithEndDate"  
    -- on the table Production.BillOfMaterials   
    -- using the columms ComponentID and StartDate.  
  
    CREATE NONCLUSTERED INDEX FIBillOfMaterialsWithEndDate  
        ON Production.BillOfMaterials (ComponentID, StartDate)  
        WHERE EndDate IS NOT NULL ;  
    GO  
    ```  
  
     <span data-ttu-id="de15b-181">L'indice filtrato riportato in precedenza è valido per la query seguente.</span><span class="sxs-lookup"><span data-stu-id="de15b-181">The filtered index above is valid for the following query.</span></span> <span data-ttu-id="de15b-182">È possibile visualizzare il piano di esecuzione della query per determinare se in Query Optimizer è stato utilizzato l'indice filtrato.</span><span class="sxs-lookup"><span data-stu-id="de15b-182">You can display the query execution plan to determine if the query optimizer used the filtered index.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT ProductAssemblyID, ComponentID, StartDate   
    FROM Production.BillOfMaterials  
    WHERE EndDate IS NOT NULL   
        AND ComponentID = 5   
        AND StartDate > '01/01/2008' ;  
    GO  
    ```  
  
#### <a name="to-ensure-that-a-filtered-index-is-used-in-a-sql-query"></a><span data-ttu-id="de15b-183">Per assicurarsi che un indice filtrato venga utilizzato in una query SQL</span><span class="sxs-lookup"><span data-stu-id="de15b-183">To ensure that a filtered index is used in a SQL query</span></span>  
  
1.  <span data-ttu-id="de15b-184">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="de15b-184">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="de15b-185">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="de15b-185">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="de15b-186">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="de15b-186">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT ComponentID, StartDate FROM Production.BillOfMaterials  
        WITH ( INDEX ( FIBillOfMaterialsWithEndDate ) )   
    WHERE EndDate IN ('20000825', '20000908', '20000918');   
    GO  
    ```  
  
 <span data-ttu-id="de15b-187">Per altre informazioni, vedere [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="de15b-187">For more information, see  [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span></span>  
  
  
