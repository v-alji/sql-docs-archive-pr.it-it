---
title: Variabili di tabella con ottimizzazione per la memoria | Microsoft Docs
ms.custom: ''
ms.date: 07/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: bd102e95-53e2-4da6-9b8b-0e4f02d286d3
author: stevestein
ms.author: sstein
ms.openlocfilehash: bec720c53c257240ee92274a6391ebc3f17faa25
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629585"
---
# <a name="memory-optimized-table-variables"></a><span data-ttu-id="8f56f-102">Variabili di tabella con ottimizzazione per la memoria</span><span class="sxs-lookup"><span data-stu-id="8f56f-102">Memory-Optimized Table Variables</span></span>
  <span data-ttu-id="8f56f-103">Oltre alle tabelle ottimizzate per la memoria per l'accesso efficiente ai dati e alle stored procedure compilate in modo nativo per l'elaborazione efficiente delle query e l'esecuzione della logica di business, [!INCLUDE[hek_2](../includes/hek-2-md.md)] introduce un terzo tipo di oggetto: il tipo di tabella ottimizzata per la memoria.</span><span class="sxs-lookup"><span data-stu-id="8f56f-103">In addition to memory-optimized tables (for efficient data access) and natively compiled stored procedures (for efficient query processing and business logic execution) [!INCLUDE[hek_2](../includes/hek-2-md.md)] introduces a third kind of object: the memory-optimized table type.</span></span> <span data-ttu-id="8f56f-104">Una variabile di tabella creata utilizzando un tipo di tabella ottimizzata per la memoria è una variabile di tabella ottimizzata per la memoria.</span><span class="sxs-lookup"><span data-stu-id="8f56f-104">A table variable created using a memory-optimized table type is a memory-optimized table variable.</span></span>  
  
 <span data-ttu-id="8f56f-105">Le variabili di tabella con ottimizzazione per la memoria offrono i vantaggi descritti di seguito rispetto alle variabili di tabella basate su disco:</span><span class="sxs-lookup"><span data-stu-id="8f56f-105">Memory-optimized table variables offer the following advantages when compared to disk-based table variables:</span></span>  
  
-   <span data-ttu-id="8f56f-106">Le variabili sono archiviate solo in memoria.</span><span class="sxs-lookup"><span data-stu-id="8f56f-106">The variables are only stored in memory.</span></span> <span data-ttu-id="8f56f-107">L'accesso ai dati è più efficiente poiché il tipo di tabella ottimizzata per la memoria utilizza lo stesso algoritmo e le stesse strutture dei dati ottimizzate per la memoria utilizzati per le tabelle ottimizzate per la memoria, in particolare quando le variabili sono utilizzate in stored procedure compilate in modo nativo.</span><span class="sxs-lookup"><span data-stu-id="8f56f-107">Data access is more efficient because memory-optimized table type use the same memory-optimized algorithm and data structures used for memory-optimized tables, especially when the variables are used in natively compiled stored procedures.</span></span>  
  
-   <span data-ttu-id="8f56f-108">Con le variabili di tabella ottimizzata per la memoria, non viene utilizzato tempdb.</span><span class="sxs-lookup"><span data-stu-id="8f56f-108">With memory-optimized table variables, there is no tempdb utilization.</span></span> <span data-ttu-id="8f56f-109">Le variabili di tabella non vengono archiviate in tempdb e non utilizzano alcuna risorsa in tempdb.</span><span class="sxs-lookup"><span data-stu-id="8f56f-109">Table variables are not stored in tempdb and do not use any resources in tempdb.</span></span>  
  
 <span data-ttu-id="8f56f-110">Gli scenari di utilizzo tipici per le variabili di tabella ottimizzata per la memoria sono:</span><span class="sxs-lookup"><span data-stu-id="8f56f-110">The typical usage scenarios for memory-optimized table variables are:</span></span>  
  
-   <span data-ttu-id="8f56f-111">Archiviazione dei risultati intermedi e creazione di singoli set di risultati basati su più query in stored procedure compilate in modo nativo.</span><span class="sxs-lookup"><span data-stu-id="8f56f-111">Storing intermediate results and creating single result sets based on multiple queries in natively compiled stored procedures.</span></span>  
  
-   <span data-ttu-id="8f56f-112">Passaggio di parametri con valori di tabella alle stored procedure compilate in modo nativo e alle stored procedure interpretate.</span><span class="sxs-lookup"><span data-stu-id="8f56f-112">Passing table-valued parameters into natively compiled stored procedures and interpreted stored procedures.</span></span>  
  
-   <span data-ttu-id="8f56f-113">Sostituzione delle variabili di tabella basata su disco e, in alcuni casi, delle tabelle #temp locali in una stored procedure.</span><span class="sxs-lookup"><span data-stu-id="8f56f-113">Replacing disk-based table variables, and in some cases #temp tables that are local to a stored procedure.</span></span> <span data-ttu-id="8f56f-114">Si tratta di un aspetto particolarmente utile se sono presenti contese di tempdb nel sistema.</span><span class="sxs-lookup"><span data-stu-id="8f56f-114">This is particularly useful if there is a lot of tempdb contention in the system.</span></span>  
  
-   <span data-ttu-id="8f56f-115">Le variabili di tabella possono essere utilizzate per simulare i cursori in stored procedure compilate in modo nativo, con cui è possibile risolvere le limitazioni della superficie di attacco in stored procedure compilate in modo nativo.</span><span class="sxs-lookup"><span data-stu-id="8f56f-115">Table variables can be used to simulate cursors in natively compiled stored procedures, which can help you work around surface area limitations in natively compiled stored procedures.</span></span>  
  
 <span data-ttu-id="8f56f-116">Come per le tabelle ottimizzate per la memoria, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] genera una DLL per ogni tipo di tabella ottimizzata per la memoria.</span><span class="sxs-lookup"><span data-stu-id="8f56f-116">Like memory-optimized tables, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] generates a DLL for each memory-optimized table type.</span></span> <span data-ttu-id="8f56f-117">La compilazione viene richiamata quando viene creato il tipo di tabella ottimizzata per la memoria e non quando viene utilizzata per creare variabili di tabella ottimizzata per la memoria. Questa DLL include le funzioni per l'accesso agli indici e il recupero dei dati dalle variabili di tabella.</span><span class="sxs-lookup"><span data-stu-id="8f56f-117">(Compilation is invoked when the memory-optimized table type is created and not when used to create memory-optimized table variables.) This DLL includes the functions for accessing indexes and retrieving data from the table variables.</span></span> <span data-ttu-id="8f56f-118">Quando una variabile di tabella ottimizzata per la memoria viene dichiarata in base al tipo di tabella, nella sessione utente viene creata un'istanza delle strutture di indice e della tabella corrispondenti al tipo di tabella.</span><span class="sxs-lookup"><span data-stu-id="8f56f-118">When a memory-optimized table variable is declared based on the table type, an instance of the table and index structures corresponding to the table type is created in the user session.</span></span> <span data-ttu-id="8f56f-119">La variabile di tabella può quindi essere utilizzata in modo analogo alle variabili di tabella basata su disco.</span><span class="sxs-lookup"><span data-stu-id="8f56f-119">The table variable can then be used in the same way as disk-based table variables.</span></span> <span data-ttu-id="8f56f-120">È possibile inserire, aggiornare ed eliminare righe nella variabile di tabella, nonché utilizzare le variabili nelle query di [!INCLUDE[tsql](../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8f56f-120">You can insert, update, and delete rows in the table variable, and you can use the variables in [!INCLUDE[tsql](../includes/tsql-md.md)] queries.</span></span> <span data-ttu-id="8f56f-121">È inoltre possibile passare le variabili alle stored procedure compilate in modo nativo e interpretate, come parametri con valori di tabella.</span><span class="sxs-lookup"><span data-stu-id="8f56f-121">You can also pass the variables into natively compiled and interpreted stored procedures, as table-valued parameters (TVP).</span></span>  
  
 <span data-ttu-id="8f56f-122">L'esempio seguente illustra un tipo di tabella ottimizzata per la memoria dall'esempio di OLTP in memoria basato su AdventureWorks ([SQL Server esempio di OLTP in memoria 2014](https://msftdbprodsamples.codeplex.com/releases/view/114491)).</span><span class="sxs-lookup"><span data-stu-id="8f56f-122">The following sample shows a memory-optimized table type from the AdventureWorks-based In-Memory OLTP sample ([SQL Server 2014 In-Memory OLTP Sample](https://msftdbprodsamples.codeplex.com/releases/view/114491)).</span></span>  
  
```sql
CREATE TYPE Sales.SalesOrderDetailType_inmem
   AS TABLE
(
   OrderQty         smallint   NOT NULL,
   ProductID        int        NOT NULL,

   SpecialOfferID   int        NOT NULL
      INDEX  IX_SpecialOfferID  NONCLUSTERED,

   LocalID          int        NOT NULL,

   INDEX IX_ProductID HASH (ProductID)
      WITH ( BUCKET_COUNT = 8 )
)
WITH ( MEMORY_OPTIMIZED = ON );
```  
  
 <span data-ttu-id="8f56f-123">Nell'esempio viene illustrato che la sintassi dei tipi di tabella ottimizzata per la memoria è simile ai tipi di tabella basati su disco, con le seguenti eccezioni:</span><span class="sxs-lookup"><span data-stu-id="8f56f-123">The sample shows that the syntax of memory-optimized table types is similar to disk-based table types, with the following exceptions:</span></span>  
  
-   <span data-ttu-id="8f56f-124">`MEMORY_OPTIMIZED=ON` indica se il tipo di tabella è ottimizzato per la memoria.</span><span class="sxs-lookup"><span data-stu-id="8f56f-124">`MEMORY_OPTIMIZED=ON` indicates that the table type is memory-optimized.</span></span>  
  
-   <span data-ttu-id="8f56f-125">Il tipo deve contenere almeno un indice.</span><span class="sxs-lookup"><span data-stu-id="8f56f-125">The type must have at least one index.</span></span> <span data-ttu-id="8f56f-126">Analogamente alle tabelle ottimizzate per la memoria, è possibile utilizzare indici hash e non cluster.</span><span class="sxs-lookup"><span data-stu-id="8f56f-126">As with memory-optimized tables, you can use hash and nonclustered indexes.</span></span>  
  
     <span data-ttu-id="8f56f-127">Per un indice hash, il numero di bucket deve essere da una a due volte il numero previsto di chiavi di indice univoche.</span><span class="sxs-lookup"><span data-stu-id="8f56f-127">For a hash index, the bucket count should be about one to two times the number of expected unique index keys.</span></span> <span data-ttu-id="8f56f-128">Per ulteriori informazioni, vedere [Determining the Correct Bucket Count for Hash Indexes](../relational-databases/indexes/indexes.md).</span><span class="sxs-lookup"><span data-stu-id="8f56f-128">For more information, see [Determining the Correct Bucket Count for Hash Indexes](../relational-databases/indexes/indexes.md).</span></span>  
  
-   <span data-ttu-id="8f56f-129">Il tipo di dati e le restrizioni relative ai vincoli nelle tabelle ottimizzate per la memoria si applicano anche ai tipi di tabella ottimizzata per la memoria.</span><span class="sxs-lookup"><span data-stu-id="8f56f-129">The data type and constraint restrictions on memory-optimized tables also apply to memory-optimized table types.</span></span> <span data-ttu-id="8f56f-130">Ad esempio, in [!INCLUDE[ssSQL14](../includes/sssql14-md.md)] sono supportati i vincoli predefiniti, ma non i vincoli CHECK.</span><span class="sxs-lookup"><span data-stu-id="8f56f-130">For example, in [!INCLUDE[ssSQL14](../includes/sssql14-md.md)] default constraints are supported, but check constraints are not.</span></span>  
  
 <span data-ttu-id="8f56f-131">Come le tabelle ottimizzate per la memoria, le variabili di tabella ottimizzata per la memoria</span><span class="sxs-lookup"><span data-stu-id="8f56f-131">Like memory-optimized tables, memory-optimized table variables,</span></span>  
  
-   <span data-ttu-id="8f56f-132">Non supportano piani paralleli.</span><span class="sxs-lookup"><span data-stu-id="8f56f-132">Do not support parallel plans.</span></span>  
  
-   <span data-ttu-id="8f56f-133">Non devono superare la memoria disponibile e non devono utilizzare le risorse del disco.</span><span class="sxs-lookup"><span data-stu-id="8f56f-133">Must fit in memory and do not use disk resources.</span></span>  
  
 <span data-ttu-id="8f56f-134">Le variabili di tabella basata su disco si trovano in tempdb.</span><span class="sxs-lookup"><span data-stu-id="8f56f-134">Disk-based table variables exist in tempdb.</span></span> <span data-ttu-id="8f56f-135">Le variabili di tabella con ottimizzazione per la memoria si trovano nel database utente, ma non utilizzano spazio di archiviazione e non vengono recuperate.</span><span class="sxs-lookup"><span data-stu-id="8f56f-135">Memory-optimized table variables exist in the user database (but they do not consume storage and are not recovered).</span></span>  
  
 <span data-ttu-id="8f56f-136">Non è possibile creare una variabile di tabella ottimizzata per la memoria utilizzando la sintassi inline.</span><span class="sxs-lookup"><span data-stu-id="8f56f-136">You cannot create a memory-optimized table variable using in-line syntax.</span></span> <span data-ttu-id="8f56f-137">A differenza delle variabili di tabella basate su disco, è necessario creare prima un tipo.</span><span class="sxs-lookup"><span data-stu-id="8f56f-137">Unlike disk-based table variables, you must create a type first.</span></span>  
  
## <a name="table-valued-parameters"></a><span data-ttu-id="8f56f-138">Parametri valutati a livello di tabella</span><span class="sxs-lookup"><span data-stu-id="8f56f-138">Table-Valued Parameters</span></span>  
 <span data-ttu-id="8f56f-139">Il seguente script di esempio illustra la dichiarazione di una variabile di tabella come tipo di tabella ottimizzata per la memoria `Sales.SalesOrderDetailType_inmem`, l'inserimento di tre righe nella variabile e il passaggio della variabile come parametro con valori di tabella in `Sales.usp_InsertSalesOrder_inmem`.</span><span class="sxs-lookup"><span data-stu-id="8f56f-139">The following sample script shows the declaration of a table variable as the memory-optimized table type `Sales.SalesOrderDetailType_inmem`, the insert of three rows into the variable, and passing the variable as a TVP into `Sales.usp_InsertSalesOrder_inmem`.</span></span>  
  
```sql  
DECLARE @od Sales.SalesOrderDetailType_inmem,  
  @SalesOrderID uniqueidentifier,  
  @DueDate datetime2 = SYSDATETIME()  
  
INSERT @od (LocalID, ProductID, OrderQty, SpecialOfferID) VALUES  
  (1, 888, 2, 1),  
  (2, 450, 13, 1),  
  (3, 841, 1, 1)  
  
EXEC Sales.usp_InsertSalesOrder_inmem  
  @SalesOrderID = @SalesOrderID,  
  @DueDate = @DueDate,  
 @OnlineOrderFlag = 1,  
  @SalesOrderDetails = @od  
```  
  
 <span data-ttu-id="8f56f-140">I tipi di tabella con ottimizzazione per la memoria possono essere utilizzati come tipo per i parametri con valori di tabella di stored procedure e i client possono fare riferimento a essi esattamente allo stesso modo di parametri con valori di tabella e tipi di tabella basata su disco.</span><span class="sxs-lookup"><span data-stu-id="8f56f-140">Memory-optimized table types can be used as the type for stored procedure table-valued parameters (TVPs) and can be referenced by clients exactly the same as disk-based table types and TVPs.</span></span> <span data-ttu-id="8f56f-141">Pertanto, la chiamata di stored procedure con parametri con valori di tabella ottimizzata per la memoria e stored procedure compilate in modo nativo ha un funzionamento analogo alla chiamata di stored procedure interpretate con parametri con valori di tabella basata su disco.</span><span class="sxs-lookup"><span data-stu-id="8f56f-141">Therefore, the invocation of stored procedures with memory-optimized TVPs, and natively compiled stored procedures works exactly the same as the invocation of interpreted stored procedures with disk-based TVPs.</span></span>  
  
## <a name="temp-table-replacement"></a><span data-ttu-id="8f56f-142">Sostituzione della tabella #temp</span><span class="sxs-lookup"><span data-stu-id="8f56f-142">#temp Table Replacement</span></span>  
 <span data-ttu-id="8f56f-143">Nell'esempio seguente vengono illustrati tipi di tabella e variabili di tabella ottimizzata per la memoria come sostituti di tabelle #temp locali in una stored procedure.</span><span class="sxs-lookup"><span data-stu-id="8f56f-143">The following sample shows memory-optimized table types and table variables as a replacement for #temp tables that are local to a stored procedure.</span></span>  
  
```sql  
-- Using SQL procedure and temp table  
CREATE TABLE #tempTable (c INT NOT NULL PRIMARY KEY NONCLUSTERED)  
  
CREATE PROCEDURE sqlProc  
AS  
BEGIN  
  TRUNCATE TABLE #tempTable  
  
  INSERT #tempTable VALUES (1)  
  INSERT #tempTable VALUES (2)  
  INSERT #tempTable VALUES (3)  
  SELECT * FROM #tempTable  
END  
GO  
  
-- Using natively compiled stored procedure and table variable  
CREATE TYPE TT AS TABLE (c INT NOT NULL PRIMARY KEY NONCLUSTERED)  
GO  
  
CREATE PROCEDURE NCSPProc  
WITH NATIVE_COMPILATION, SCHEMABINDING, EXECUTE AS OWNER  
AS  
BEGIN ATOMIC WITH (TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE = N'us_english')  
  DECLARE @tableVariable TT  
  INSERT @tableVariable VALUES (1)  
  INSERT @tableVariable VALUES (2)  
  INSERT @tableVariable VALUES (3)  
  SELECT c FROM @tableVariable  
END  
GO  
```  
  
## <a name="creating-a-single-result-set"></a><span data-ttu-id="8f56f-144">Creazione di un singolo set di risultati</span><span class="sxs-lookup"><span data-stu-id="8f56f-144">Creating a Single Result Set</span></span>  
 <span data-ttu-id="8f56f-145">Nell'esempio seguente viene illustrato come archiviare i risultati intermedi e creare singoli set di risultati basati su più query in stored procedure compilate in modo nativo.</span><span class="sxs-lookup"><span data-stu-id="8f56f-145">The following sample shows how to store intermediate results and create single result sets based on multiple queries in natively compiled stored procedures.</span></span> <span data-ttu-id="8f56f-146">L'esempio calcola l'unione `SELECT c1 FROM dbo.t1 UNION SELECT c1 FROM dbo.t2`.</span><span class="sxs-lookup"><span data-stu-id="8f56f-146">The sample is computing the union `SELECT c1 FROM dbo.t1 UNION SELECT c1 FROM dbo.t2`.</span></span>  
  
```sql  
CREATE DATABASE hk  
GO  
ALTER DATABASE hk ADD FILEGROUP hk_mod CONTAINS MEMORY_OPTIMIZED_DATA  
ALTER DATABASE hk ADD FILE( NAME = 'hk_mod' , FILENAME = 'c:\data\hk_mod') TO FILEGROUP hk_mod;  
  
USE hk  
GO  
  
CREATE TYPE tab1 AS TABLE (c1 INT NOT NULL, INDEX idx NONCLUSTERED(c1)) WITH (MEMORY_OPTIMIZED = ON)  
  
CREATE TABLE dbo.t1 (c1 INT NOT NULL, INDEX idx NONCLUSTERED(c1)) WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_ONLY)  
CREATE TABLE dbo.t2 (c1 INT NOT NULL, INDEX idx NONCLUSTERED(c1)) WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_ONLY)  
  
INSERT INTO dbo.t1 VALUES (1), (2)  
INSERT INTO dbo.t2 VALUES (3), (4)  
GO  
  
CREATE PROCEDURE dbo.p1  
  WITH NATIVE_COMPILATION, SCHEMABINDING, EXECUTE AS OWNER  
  AS  
  BEGIN ATOMIC WITH ( TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE = N'us_english' )  
  
    DECLARE @t dbo.tab1  
    INSERT @t (c1)  
    SELECT c1 FROM dbo.t1;  
  
    INSERT @t (c1)  
    SELECT c1 FROM dbo.t2;  
  
    SELECT c1 FROM @t;  
  END  
GO  
  
EXEC dbo.p1  
GO  
```  
  
## <a name="memory-consumption-for-table-variables"></a><span data-ttu-id="8f56f-147">Consumo di memoria per le variabili di tabella</span><span class="sxs-lookup"><span data-stu-id="8f56f-147">Memory Consumption for Table Variables</span></span>  
 <span data-ttu-id="8f56f-148">Il consumo di memoria per le variabili di tabella è simile alle tabelle ottimizzate per la memoria, ad eccezione degli indici non cluster.</span><span class="sxs-lookup"><span data-stu-id="8f56f-148">Memory consumption for table variables is similar to memory-optimized tables, with the exception of nonclustered indexes.</span></span> <span data-ttu-id="8f56f-149">Se si inseriscono molte righe nelle variabili di tabella ottimizzata per la memoria con indici non cluster e se le chiavi di indice sono di grandi dimensioni, queste variabili di tabella utilizzano una quantità di memoria sproporzionata.</span><span class="sxs-lookup"><span data-stu-id="8f56f-149">If you insert a lot of rows into memory-optimized table variables with nonclustered indexes and if the index keys are large, these table variables will use a disproportionate amount of memory.</span></span> <span data-ttu-id="8f56f-150">Gli indici non cluster nelle variabili di tabella di grandi dimensioni richiedono proporzionalmente una quantità di memoria superiore rispetto a quella richiesta da un indice non cluster per lo stesso numero di righe inserite in una tabella (maggiore quantità di memoria nelle pagine di indice).</span><span class="sxs-lookup"><span data-stu-id="8f56f-150">Nonclustered indexes on large table variables require proportionately more memory than a nonclustered index would require for the same number of rows inserted into a table (more memory in the index pages).</span></span>  
  
 <span data-ttu-id="8f56f-151">La memoria per le variabili di tabella proviene dal pool di risorse di Resource Governor del database.</span><span class="sxs-lookup"><span data-stu-id="8f56f-151">Memory for table variables comes from the database's Resource Governor resource pool.</span></span>  
  
 <span data-ttu-id="8f56f-152">A differenza delle tabelle ottimizzate per la memoria, la memoria utilizzata (incluse le righe eliminate) dalle variabili di tabella viene liberata quando la variabile di tabella abbandona l'ambito.</span><span class="sxs-lookup"><span data-stu-id="8f56f-152">Unlike memory-optimized tables, the memory consumed (including deleted rows) by table variables is freed when the table variable goes out of scope.</span></span>  
  
 <span data-ttu-id="8f56f-153">La memoria viene rappresentata come parte di un singolo consumer di memoria di PGPOOL del database.</span><span class="sxs-lookup"><span data-stu-id="8f56f-153">Memory is accounted for as part of the single PGPOOL memory consumer of the database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f56f-154">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8f56f-154">See Also</span></span>  
 [<span data-ttu-id="8f56f-155">Supporto di Transact-SQL per OLTP in memoria</span><span class="sxs-lookup"><span data-stu-id="8f56f-155">Transact-SQL Support for In-Memory OLTP</span></span>](../relational-databases/in-memory-oltp/transact-sql-support-for-in-memory-oltp.md)  
  
  
