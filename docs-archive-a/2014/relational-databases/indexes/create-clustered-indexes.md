---
title: Creare indici cluster | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- index creation [SQL Server], clustered indexes
- clustered indexes, creating
- clustered indexes, PRIMARY KEY constraint
- clustered indexes, UNIQUE constraint
- indexes [SQL Server], clustered
ms.assetid: 47148383-c2c7-4f08-a9e4-7016bf2d1d13
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 567ff9a01bd93323149168b9e3aa0f34d78aee39
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627703"
---
# <a name="create-clustered-indexes"></a><span data-ttu-id="c1287-102">Creare indici cluster</span><span class="sxs-lookup"><span data-stu-id="c1287-102">Create Clustered Indexes</span></span>
  <span data-ttu-id="c1287-103">È possibile creare indici cluster nelle tabelle di [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c1287-103">You can create clustered indexes on tables in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="c1287-104">A parte poche eccezioni, ogni tabella deve disporre di un indice cluster.</span><span class="sxs-lookup"><span data-stu-id="c1287-104">With few exceptions, every table should have a clustered index.</span></span> <span data-ttu-id="c1287-105">Oltre a migliorare le prestazioni di esecuzione delle query, un indice può essere ricompilato o riorganizzato su richiesta per controllare la frammentazione della tabella.</span><span class="sxs-lookup"><span data-stu-id="c1287-105">Besides improving query performance, a clustered index can be rebuilt or reorganized on demand to control table fragmentation.</span></span> <span data-ttu-id="c1287-106">È inoltre possibile creare un indice cluster in una vista.</span><span class="sxs-lookup"><span data-stu-id="c1287-106">A clustered index can also be created on a view.</span></span> <span data-ttu-id="c1287-107">Gli indici cluster sono descritti nell'argomento [Descrizione di indici cluster e non cluster](clustered-and-nonclustered-indexes-described.md).</span><span class="sxs-lookup"><span data-stu-id="c1287-107">(Clustered indexes are defined in the topic [Clustered and Nonclustered Indexes Described](clustered-and-nonclustered-indexes-described.md).)</span></span>  
  
 <span data-ttu-id="c1287-108">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="c1287-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="c1287-109">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="c1287-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="c1287-110">Modalità di implementazione tipiche</span><span class="sxs-lookup"><span data-stu-id="c1287-110">Typical Implementations</span></span>](#Implementations)  
  
     [<span data-ttu-id="c1287-111">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="c1287-111">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="c1287-112">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="c1287-112">Security</span></span>](#Security)  
  
-   <span data-ttu-id="c1287-113">**Per creare un indice cluster in una tabella tramite:**</span><span class="sxs-lookup"><span data-stu-id="c1287-113">**To create a clustered index on a table, using:**</span></span>  
  
     [<span data-ttu-id="c1287-114">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c1287-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="c1287-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c1287-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c1287-116">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="c1287-116">Before You Begin</span></span>  
  
###  <a name="typical-implementations"></a><a name="Implementations"></a> <span data-ttu-id="c1287-117">Modalità di implementazione tipiche</span><span class="sxs-lookup"><span data-stu-id="c1287-117">Typical Implementations</span></span>  
 <span data-ttu-id="c1287-118">Gli indici cluster vengono implementati nei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="c1287-118">Clustered indexes are implemented in the following ways:</span></span>  
  
-   <span data-ttu-id="c1287-119">**Vincoli PRIMARY KEY e UNIQUE**</span><span class="sxs-lookup"><span data-stu-id="c1287-119">**PRIMARY KEY and UNIQUE constraints**</span></span>  
  
     <span data-ttu-id="c1287-120">Quando si crea un vincolo PRIMARY KEY, viene automaticamente creato un indice cluster univoco nella colonna o nelle colonne se nella tabella non esiste già un indice cluster e non si specifica un indice non cluster univoco.</span><span class="sxs-lookup"><span data-stu-id="c1287-120">When you create a PRIMARY KEY constraint, a unique clustered index on the column or columns is automatically created if a clustered index on the table does not already exist and you do not specify a unique nonclustered index.</span></span> <span data-ttu-id="c1287-121">La colonna chiave primaria non può supportare i valori NULL.</span><span class="sxs-lookup"><span data-stu-id="c1287-121">The primary key column cannot allow NULL values.</span></span>  
  
     <span data-ttu-id="c1287-122">Quando si crea un vincolo UNIQUE, viene creato un indice non cluster univoco per applicare un vincolo UNIQUE per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="c1287-122">When you create a UNIQUE constraint, a unique nonclustered index is created to enforce a UNIQUE constraint by default.</span></span> <span data-ttu-id="c1287-123">È possibile specificare un indice cluster univoco se nella tabella non ne esiste già uno.</span><span class="sxs-lookup"><span data-stu-id="c1287-123">You can specify a unique clustered index if a clustered index on the table does not already exist.</span></span>  
  
     <span data-ttu-id="c1287-124">A un indice creato come parte del vincolo viene automaticamente assegnato lo stesso nome del vincolo.</span><span class="sxs-lookup"><span data-stu-id="c1287-124">An index created as part of the constraint is automatically given the same name as the constraint name.</span></span> <span data-ttu-id="c1287-125">Per ulteriori informazioni, vedere [Primary and Foreign Key Constraints](../tables/primary-and-foreign-key-constraints.md) e [Unique Constraints and Check Constraints](../tables/unique-constraints-and-check-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="c1287-125">For more information, see [Primary and Foreign Key Constraints](../tables/primary-and-foreign-key-constraints.md) and [Unique Constraints and Check Constraints](../tables/unique-constraints-and-check-constraints.md).</span></span>  
  
-   <span data-ttu-id="c1287-126">**Indice indipendente da un vincolo**</span><span class="sxs-lookup"><span data-stu-id="c1287-126">**Index independent of a constraint**</span></span>  
  
     <span data-ttu-id="c1287-127">È possibile creare un indice cluster in una colonna diversa dalla colonna chiave primaria a condizione che sia stato specificato un vincolo di chiave primaria non cluster.</span><span class="sxs-lookup"><span data-stu-id="c1287-127">You can create a clustered index on a column other than primary key column if a nonclustered primary key constraint was specified.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="c1287-128">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="c1287-128">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="c1287-129">Quando viene creata una struttura dell'indice cluster, è necessario spazio su disco per la struttura vecchia (origine) e per quella nuova (destinazione) nei file e filegroup appropriati.</span><span class="sxs-lookup"><span data-stu-id="c1287-129">When a clustered index structure is created, disk space for both the old (source) and new (target) structures is required in their respective files and filegroups.</span></span> <span data-ttu-id="c1287-130">La struttura vecchia non viene deallocata fino a quando non viene eseguito il commit della transazione completa.</span><span class="sxs-lookup"><span data-stu-id="c1287-130">The old structure is not deallocated until the complete transaction commits.</span></span> <span data-ttu-id="c1287-131">Potrebbe inoltre essere necessario spazio su disco aggiuntivo temporaneo per l'ordinamento.</span><span class="sxs-lookup"><span data-stu-id="c1287-131">Additional temporary disk space for sorting may also be required.</span></span> <span data-ttu-id="c1287-132">Per altre informazioni, vedere [Disk Space Requirements for Index DDL Operations](disk-space-requirements-for-index-ddl-operations.md).</span><span class="sxs-lookup"><span data-stu-id="c1287-132">For more information, see [Disk Space Requirements for Index DDL Operations](disk-space-requirements-for-index-ddl-operations.md).</span></span>  
  
-   <span data-ttu-id="c1287-133">Se viene creato un indice cluster in un heap con molti indici non cluster esistenti, tutti gli indici non cluster devono essere ricompilati in modo che contengano il valore della chiave di clustering anziché l'identificatore di riga (RID, Row Identifier).</span><span class="sxs-lookup"><span data-stu-id="c1287-133">If a clustered index is created on a heap with several existing nonclustered indexes, all the nonclustered indexes must be rebuilt so that they contain the clustering key value instead of the row identifier (RID).</span></span> <span data-ttu-id="c1287-134">In modo analogo, se viene eliminato un indice cluster di una tabella con molti indici non cluster, tutti gli indici non cluster verranno ricompilati durante l'operazione DROP.</span><span class="sxs-lookup"><span data-stu-id="c1287-134">Similarly, if a clustered index is dropped on a table that has several nonclustered indexes, the nonclustered indexes are all rebuilt as part of the DROP operation.</span></span> <span data-ttu-id="c1287-135">Per tabelle di grandi dimensioni, la ricostruzione degli indici potrebbe richiedere una notevole quantità di tempo.</span><span class="sxs-lookup"><span data-stu-id="c1287-135">This may take significant time on large tables.</span></span>  
  
     <span data-ttu-id="c1287-136">La strategia ottimale per la compilazione di indici per tabelle di grandi dimensioni consiste nel compilare innanzitutto l'indice cluster e quindi eventuali indici non cluster.</span><span class="sxs-lookup"><span data-stu-id="c1287-136">The preferred way to build indexes on large tables is to start with the clustered index and then build any nonclustered indexes.</span></span> <span data-ttu-id="c1287-137">Quando si creano gli indici in tabelle esistenti, impostare l'opzione ONLINE su ON.</span><span class="sxs-lookup"><span data-stu-id="c1287-137">Consider setting the ONLINE option to ON when you create indexes on existing tables.</span></span> <span data-ttu-id="c1287-138">In questo modo, i blocchi di lunga durata a livello di tabella non vengono mantenuti,</span><span class="sxs-lookup"><span data-stu-id="c1287-138">When set to ON, long-term table locks are not held.</span></span> <span data-ttu-id="c1287-139">al fine di consentire l'esecuzione di query o l'aggiornamento della tabella sottostante.</span><span class="sxs-lookup"><span data-stu-id="c1287-139">This enables queries or updates to the underlying table to continue.</span></span> <span data-ttu-id="c1287-140">Per altre informazioni, vedere [Perform Index Operations Online](perform-index-operations-online.md).</span><span class="sxs-lookup"><span data-stu-id="c1287-140">For more information, see [Perform Index Operations Online](perform-index-operations-online.md).</span></span>  
  
-   <span data-ttu-id="c1287-141">La chiave di indice di un indice cluster non può contenere colonne di tipo `varchar` con dati esistenti nell'unità di allocazione ROW_OVERFLOW_DATA.</span><span class="sxs-lookup"><span data-stu-id="c1287-141">The index key of a clustered index cannot contain `varchar` columns that have existing data in the ROW_OVERFLOW_DATA allocation unit.</span></span> <span data-ttu-id="c1287-142">Se viene creato un indice cluster in una colonna `varchar` e i dati esistenti si trovano nell'unità di allocazione IN_ROW_DATA, le azioni di inserimento o aggiornamento successive eseguite nella colonna che comporterebbero lo spostamento dei dati all'esterno di righe non verranno eseguite correttamente.</span><span class="sxs-lookup"><span data-stu-id="c1287-142">If a clustered index is created on a `varchar` column and the existing data is in the IN_ROW_DATA allocation unit, subsequent insert or update actions on the column that would push the data off-row will fail.</span></span> <span data-ttu-id="c1287-143">Per ottenere informazioni sulle tabelle che potrebbero contenere dati di overflow della riga, usare la funzione a gestione dinamica [sys.dm_db_index_physical_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-index-physical-stats-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c1287-143">To obtain information about tables that might contain row-overflow data, use the [sys.dm_db_index_physical_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-index-physical-stats-transact-sql) dynamic management function.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="c1287-144">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="c1287-144">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="c1287-145">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="c1287-145">Permissions</span></span>  
 <span data-ttu-id="c1287-146">È richiesta l'autorizzazione ALTER per la tabella o la vista.</span><span class="sxs-lookup"><span data-stu-id="c1287-146">Requires ALTER permission on the table or view.</span></span> <span data-ttu-id="c1287-147">L'utente deve essere un membro del ruolo predefinito del server **sysadmin** o dei ruoli predefiniti del database **db_ddladmin** e **db_owner** .</span><span class="sxs-lookup"><span data-stu-id="c1287-147">User must be a member of the **sysadmin** fixed server role or the **db_ddladmin** and **db_owner** fixed database roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="c1287-148">Con SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c1287-148">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-clustered-index-by-using-object-explorer"></a><span data-ttu-id="c1287-149">Per creare un indice cluster tramite Esplora oggetti</span><span class="sxs-lookup"><span data-stu-id="c1287-149">To create a clustered index by using Object Explorer</span></span>  
  
1.  <span data-ttu-id="c1287-150">In Esplora oggetti espandere la tabella in cui si desidera creare un indice cluster.</span><span class="sxs-lookup"><span data-stu-id="c1287-150">In Object Explorer, expand the table on which you want to create a clustered index.</span></span>  
  
2.  <span data-ttu-id="c1287-151">Fare clic con il pulsante destro del mouse sulla cartella **Indici**, scegliere **Nuovo indice** e selezionare **Indice cluster**.</span><span class="sxs-lookup"><span data-stu-id="c1287-151">Right-click the **Indexes** folder, point to **New Index**, and select **Clustered Index...**.</span></span>  
  
3.  <span data-ttu-id="c1287-152">Nella pagina **Generale** della finestra di dialogo **Nuovo indice** immettere il nome del nuovo indice nella casella **Nome indice** .</span><span class="sxs-lookup"><span data-stu-id="c1287-152">In the **New Index** dialog box, on the **General** page, enter the name of the new index in the **Index name** box.</span></span>  
  
4.  <span data-ttu-id="c1287-153">In **Colonne chiave indice**fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="c1287-153">Under **Index key columns**, click **Add...**.</span></span>  
  
5.  <span data-ttu-id="c1287-154">Nella finestra di dialogo **Seleziona colonne da**_table_name_ Selezionare la casella di controllo della colonna della tabella da aggiungere all'indice cluster.</span><span class="sxs-lookup"><span data-stu-id="c1287-154">In the **Select Columns from**_table_name_ dialog box, select the check box of the table column to be added to the clustered index.</span></span>  
  
6.  <span data-ttu-id="c1287-155">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="c1287-155">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="c1287-156">Nella finestra di dialogo **Nuovo indice** fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="c1287-156">In the **New Index** dialog box, click **OK**.</span></span>  
  
#### <a name="to-create-a-clustered-index-by-using-the-table-designer"></a><span data-ttu-id="c1287-157">Per creare un indice cluster tramite Progettazione tabelle</span><span class="sxs-lookup"><span data-stu-id="c1287-157">To create a clustered index by using the Table Designer</span></span>  
  
1.  <span data-ttu-id="c1287-158">In Esplora oggetti espandere il database in cui si desidera creare una tabella con un indice cluster.</span><span class="sxs-lookup"><span data-stu-id="c1287-158">In Object Explorer, expand the database on which you want to create a table with a clustered index.</span></span>  
  
2.  <span data-ttu-id="c1287-159">Fare clic con il pulsante destro del mouse sulla cartella **Tabelle** e scegliere **Nuova tabella**.</span><span class="sxs-lookup"><span data-stu-id="c1287-159">Right-click the **Tables** folder and click **New Table...**.</span></span>  
  
3.  <span data-ttu-id="c1287-160">Creare una nuova tabella con il metodo tradizionale.</span><span class="sxs-lookup"><span data-stu-id="c1287-160">Create a new table as you normally would.</span></span> <span data-ttu-id="c1287-161">Per altre informazioni, vedere [Creare tabelle &#40;Motore di database&#41;](../tables/create-tables-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="c1287-161">For more information, see [Create Tables &#40;Database Engine&#41;](../tables/create-tables-database-engine.md).</span></span>  
  
4.  <span data-ttu-id="c1287-162">Fare clic con il pulsante destro del mouse sulla nuova tabella creata e scegliere **Progetta**.</span><span class="sxs-lookup"><span data-stu-id="c1287-162">Right-click the new table created above and click **Design**.</span></span>  
  
5.  <span data-ttu-id="c1287-163">Scegliere **Indici/chiavi** nel menu **Progettazione tabelle**.</span><span class="sxs-lookup"><span data-stu-id="c1287-163">On the **Table Designer** menu, click **Indexes/Keys**.</span></span>  
  
6.  <span data-ttu-id="c1287-164">Nella finestra di dialogo **Indici/chiavi** fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="c1287-164">In the **Indexes/Keys** dialog box, click **Add**.</span></span>  
  
7.  <span data-ttu-id="c1287-165">Selezionare il nuovo indice dalla casella di testo **Chiave o indice primario/univoco selezionato** .</span><span class="sxs-lookup"><span data-stu-id="c1287-165">Select the new index in the **Selected Primary/Unique Key or Index** text box.</span></span>  
  
8.  <span data-ttu-id="c1287-166">Nella griglia selezionare **Crea come CLUSTERED**, quindi selezionare **Sì** dall'elenco a discesa a destra della proprietà.</span><span class="sxs-lookup"><span data-stu-id="c1287-166">In the grid, select **Create as Clustered**, and choose **Yes** from the drop-down list to the right of the property.</span></span>  
  
9. <span data-ttu-id="c1287-167">Fare clic su **Close**.</span><span class="sxs-lookup"><span data-stu-id="c1287-167">Click **Close**.</span></span>  
  
10. <span data-ttu-id="c1287-168">Nel menu **File** scegliere **Salva**_table_name_.</span><span class="sxs-lookup"><span data-stu-id="c1287-168">On the **File** menu, click **Save**_table_name_.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="c1287-169">Con Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c1287-169">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-clustered-index"></a><span data-ttu-id="c1287-170">Per creare un indice cluster</span><span class="sxs-lookup"><span data-stu-id="c1287-170">To create a clustered index</span></span>  
  
1.  <span data-ttu-id="c1287-171">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c1287-171">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="c1287-172">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="c1287-172">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="c1287-173">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="c1287-173">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Create a new table with three columns.  
    CREATE TABLE dbo.TestTable  
        (TestCol1 int NOT NULL,  
         TestCol2 nchar(10) NULL,  
         TestCol3 nvarchar(50) NULL);  
    GO  
    -- Create a clustered index called IX_TestTable_TestCol1  
    -- on the dbo.TestTable table using the TestCol1 column.  
    CREATE CLUSTERED INDEX IX_TestTable_TestCol1   
        ON dbo.TestTable (TestCol1);   
    GO  
    ```  
  
 <span data-ttu-id="c1287-174">Per altre informazioni, vedere [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c1287-174">For more information, see [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1287-175">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c1287-175">See Also</span></span>  
 <span data-ttu-id="c1287-176">[Creazione di chiavi primarie](../tables/create-primary-keys.md) </span><span class="sxs-lookup"><span data-stu-id="c1287-176">[Create Primary Keys](../tables/create-primary-keys.md) </span></span>  
 [<span data-ttu-id="c1287-177">Creare vincoli UNIQUE</span><span class="sxs-lookup"><span data-stu-id="c1287-177">Create Unique Constraints</span></span>](../tables/create-unique-constraints.md)  
  
  
