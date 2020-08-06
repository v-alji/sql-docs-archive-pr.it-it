---
title: Monitorare e risolvere i problemi relativi all'utilizzo della memoria | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 7a458b9c-3423-4e24-823d-99573544c877
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 5805ed06ad78040dbdf6c8557e5f548ad57f618b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725759"
---
# <a name="monitor-and-troubleshoot-memory-usage"></a><span data-ttu-id="d6284-102">Monitorare e risolvere i problemi relativi all'utilizzo della memoria</span><span class="sxs-lookup"><span data-stu-id="d6284-102">Monitor and Troubleshoot Memory Usage</span></span>
  [!INCLUDE[hek_1](../../includes/hek-1-md.md)] <span data-ttu-id="d6284-103">utilizza la memoria in modi diversi rispetto alle tabelle basate su disco.</span><span class="sxs-lookup"><span data-stu-id="d6284-103">consumes memory in different patterns than disk-based tables.</span></span> <span data-ttu-id="d6284-104">È possibile monitorare la quantità di memoria allocata e utilizzata dagli indici e dalle tabelle ottimizzate per la memoria nel database tramite DMV o contatori delle prestazioni forniti per il sottosistema di Garbage Collection e memoria.</span><span class="sxs-lookup"><span data-stu-id="d6284-104">You can monitor the amount of memory allocated and used by memory-optimized tables and indexes in your database using the DMVs or performance counters provided for memory and the garbage collection subsystem.</span></span>  <span data-ttu-id="d6284-105">Ciò offre visibilità a livello di sistema e di database e consente di evitare problemi dovuti all'esaurimento della memoria.</span><span class="sxs-lookup"><span data-stu-id="d6284-105">This gives you visibility at both the system and database level and lets you prevent problems due to memory exhaustion.</span></span>

 <span data-ttu-id="d6284-106">In questo argomento viene illustrato il monitoraggio dell'utilizzo della memoria di [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d6284-106">This topic covers monitoring your [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] memory usage.</span></span>


##  <a name="create-a-sample-database-with-memory-optimized-tables"></a><a name="bkmk_CreateDB"></a> <span data-ttu-id="d6284-107">Creare un database di esempio con tabelle ottimizzate per la memoria</span><span class="sxs-lookup"><span data-stu-id="d6284-107">Create a sample database with memory-optimized tables</span></span>
 <span data-ttu-id="d6284-108">Se si dispone già di un database con tabelle ottimizzate per la memoria è possibile saltare questa sezione.</span><span class="sxs-lookup"><span data-stu-id="d6284-108">You can skip this section if you already have a database with memory-optimized tables.</span></span>

 <span data-ttu-id="d6284-109">Con i passaggi seguenti si crea un database con tre tabelle ottimizzate per la memoria che è possibile utilizzare nelle sezioni rimanenti di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="d6284-109">The following steps create a database with three memory-optimized tables that you can use in the remainder of this topic.</span></span> <span data-ttu-id="d6284-110">Nell'esempio è stato eseguito il mapping del database a un pool di risorse, in modo da poter controllare la quantità di memoria utilizzata dalle tabelle ottimizzate per la memoria.</span><span class="sxs-lookup"><span data-stu-id="d6284-110">In the example, we mapped the database to a resource pool so that we can control how much memory can be taken by memory-optimized tables.</span></span>

1.  <span data-ttu-id="d6284-111">Avviare [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d6284-111">Launch [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span></span>

2.  <span data-ttu-id="d6284-112">Fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="d6284-112">Click **New Query**.</span></span>

3.  <span data-ttu-id="d6284-113">Incollare il codice nella finestra della nuova query ed eseguire ogni sezione.</span><span class="sxs-lookup"><span data-stu-id="d6284-113">Paste this code into the new query window and execute each section.</span></span>

    ```
    -- create a database to be used
    CREATE DATABASE IMOLTP_DB
    GO

    ALTER DATABASE IMOLTP_DB ADD FILEGROUP IMOLTP_DB_xtp_fg CONTAINS MEMORY_OPTIMIZED_DATA
    ALTER DATABASE IMOLTP_DB ADD FILE( NAME = 'IMOLTP_DB_xtp' , FILENAME = 'C:\Data\IMOLTP_DB_xtp') TO FILEGROUP IMOLTP_DB_xtp_fg;
    GO

    USE IMOLTP_DB
    GO

    -- create the resoure pool
    CREATE RESOURCE POOL PoolIMOLTP WITH (MAX_MEMORY_PERCENT = 60);
    ALTER RESOURCE GOVERNOR RECONFIGURE;
    GO

    -- bind the database to a resource pool
    EXEC sp_xtp_bind_db_resource_pool 'IMOLTP_DB', 'PoolIMOLTP'

    -- you can query the binding using the catalog view as described here
    SELECT d.database_id
         , d.name
         , d.resource_pool_id
    FROM sys.databases d
    GO

    -- take database offline/online to finalize the binding to the resource pool
    USE master
    GO

    ALTER DATABASE IMOLTP_DB SET OFFLINE
    GO
    ALTER DATABASE IMOLTP_DB SET ONLINE
    GO

    -- create some tables
    USE IMOLTP_DB
    GO

    -- create table t1
    CREATE TABLE dbo.t1 (
           c1 int NOT NULL CONSTRAINT [pk_t1_c1] PRIMARY KEY NONCLUSTERED
         , c2 char(40) NOT NULL
         , c3 char(8000) NOT NULL
         ) WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_AND_DATA)
    GO

    -- load t1 150K rows
    DECLARE @i int = 0
    BEGIN TRAN
    WHILE (@i <= 150000)
       BEGIN
          INSERT t1 VALUES (@i, 'a', replicate ('b', 8000))
          SET @i += 1;
       END
    Commit
    GO

    -- Create another table, t2
    CREATE TABLE dbo.t2 (
           c1 int NOT NULL CONSTRAINT [pk_t2_c1] PRIMARY KEY NONCLUSTERED
         , c2 char(40) NOT NULL
         , c3 char(8000) NOT NULL
         ) WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_AND_DATA)
    GO

    -- Create another table, t3 
    CREATE TABLE dbo.t3 (
           c1 int NOT NULL CONSTRAINT [pk_t3_c1] PRIMARY KEY NONCLUSTERED HASH (c1) WITH (BUCKET_COUNT = 1000000)
         , c2 char(40) NOT NULL
         , c3 char(8000) NOT NULL
         ) WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_AND_DATA)
    GO
    ```

##  <a name="monitoring-memory-usage"></a><span data-ttu-id="d6284-114">Monitoraggio dell'utilizzo della memoria</span><span class="sxs-lookup"><span data-stu-id="d6284-114">Monitoring Memory Usage</span></span>

###  <a name="using-ssmanstudiofull"></a><span data-ttu-id="d6284-115">Uso di [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d6284-115">Using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]</span></span>
 [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] <span data-ttu-id="d6284-116">viene fornito con report standard predefiniti per monitorare la memoria utilizzata dalle tabelle in memoria.</span><span class="sxs-lookup"><span data-stu-id="d6284-116">ships with built-in standard reports to monitor the memory consumed by in-memory tables.</span></span> <span data-ttu-id="d6284-117">È possibile accedere a questi report usando Esplora oggetti.</span><span class="sxs-lookup"><span data-stu-id="d6284-117">You can access these reports using Object Explorer.</span></span> <span data-ttu-id="d6284-118">È inoltre possibile utilizzare Esplora oggetti per monitorare la memoria utilizzata dalle singole tabelle ottimizzate per la memoria.</span><span class="sxs-lookup"><span data-stu-id="d6284-118">You can also use the object explorer to monitor memory consumed by individual memory-optimized tables.</span></span>

#### <a name="consumption-at-the-database-level"></a><span data-ttu-id="d6284-119">Utilizzo a livello di database</span><span class="sxs-lookup"><span data-stu-id="d6284-119">Consumption at the database level</span></span>
 <span data-ttu-id="d6284-120">È possibile monitorare l'utilizzo della memoria a livello di database nel modo seguente.</span><span class="sxs-lookup"><span data-stu-id="d6284-120">You can monitor memory use at the database level as follows.</span></span>

1.  <span data-ttu-id="d6284-121">Avviare [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] e connettersi a un server.</span><span class="sxs-lookup"><span data-stu-id="d6284-121">Launch [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] and connect to a server.</span></span>

2.  <span data-ttu-id="d6284-122">In Esplora oggetti fare clic con il pulsante destro del mouse sul database in cui si desidera creare i report.</span><span class="sxs-lookup"><span data-stu-id="d6284-122">In Object Explorer, right-click the database you want reports on.</span></span>

3.  <span data-ttu-id="d6284-123">Dal menu di scelta rapida scegliere **Report** -> **Standard Report** -> **Utilizzo memoria da parte di oggetti con ottimizzazione per la memoria**.</span><span class="sxs-lookup"><span data-stu-id="d6284-123">In the context menu select, **Reports** -> **Standard Reports** -> **Memory Usage By Memory Optimized Objects**</span></span>

 <span data-ttu-id="d6284-124">![HK_MM_SSMS](../../database-engine/media/hk-mm-ssms-stdrpt-memuse.gif "HK_MM_SSMS")</span><span class="sxs-lookup"><span data-stu-id="d6284-124">![HK_MM_SSMS](../../database-engine/media/hk-mm-ssms-stdrpt-memuse.gif "HK_MM_SSMS")</span></span>

 <span data-ttu-id="d6284-125">In questo report viene indicato l'utilizzo della memoria da parte del database creato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="d6284-125">This report shows memory consumption by the database we created above.</span></span>

 <span data-ttu-id="d6284-126">![HK_MM_SSMS](../../database-engine/media/hk-mm-ssms-stdrpt-memuserpt.gif "HK_MM_SSMS")</span><span class="sxs-lookup"><span data-stu-id="d6284-126">![HK_MM_SSMS](../../database-engine/media/hk-mm-ssms-stdrpt-memuserpt.gif "HK_MM_SSMS")</span></span>

###  <a name="using-dmvs"></a><span data-ttu-id="d6284-127">Utilizzo di DMVs</span><span class="sxs-lookup"><span data-stu-id="d6284-127">Using DMVs</span></span>
 <span data-ttu-id="d6284-128">Sono disponibili alcune DMV per monitorare la memoria utilizzata da tabelle ottimizzate per la memoria, indici, oggetti di sistema e strutture di runtime.</span><span class="sxs-lookup"><span data-stu-id="d6284-128">There are a number of DMVs available to monitor memory consumed by memory-optimized tables, indexes, system objects, and by run-time structures.</span></span>

#### <a name="memory-consumption-by-memory-optimized-tables-and-indexes"></a><span data-ttu-id="d6284-129">Utilizzo della memoria da parte di indici e tabelle ottimizzate per la memoria</span><span class="sxs-lookup"><span data-stu-id="d6284-129">Memory consumption by memory-optimized tables and indexes</span></span>
 <span data-ttu-id="d6284-130">Per conoscere l'utilizzo della memoria da parte di tutte le tabelle utente, gli indici e gli oggetti di sistema, eseguire una query su `sys.dm_db_xtp_table_memory_stats` come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="d6284-130">You can find memory consumption for all user tables, indexes, and system objects by querying `sys.dm_db_xtp_table_memory_stats` as shown here.</span></span>

```sql
SELECT object_name(object_id) AS Name
     , *
   FROM sys.dm_db_xtp_table_memory_stats
```

 <span data-ttu-id="d6284-131">**Output di esempio**</span><span class="sxs-lookup"><span data-stu-id="d6284-131">**Sample Output**</span></span>

```
Name       object_id   memory_allocated_for_table_kb memory_used_by_table_kb memory_allocated_for_indexes_kb memory_used_by_indexes_kb
---------- ----------- ----------------------------- ----------------------- ------------------------------- -------------------------
t3         629577281   0                             0                       128                             0
t1         565577053   1372928                       1200008                 7872                            1942
t2         597577167   0                             0                       128                             0
NULL       -6          0                             0                       2                               2
NULL       -5          0                             0                       24                              24
NULL       -4          0                             0                       2                               2
NULL       -3          0                             0                       2                               2
NULL       -2          192                           25                      16                              16
```

 <span data-ttu-id="d6284-132">Per ulteriori informazioni, vedere [sys. dm_db_xtp_table_memory_stats](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-xtp-table-memory-stats-transact-sql?view=sql-server-2016).</span><span class="sxs-lookup"><span data-stu-id="d6284-132">For more information, see [sys.dm_db_xtp_table_memory_stats](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-xtp-table-memory-stats-transact-sql?view=sql-server-2016).</span></span>

#### <a name="memory-consumption-by-internal-system-structures"></a><span data-ttu-id="d6284-133">Utilizzo della memoria da parte delle strutture di sistema interne</span><span class="sxs-lookup"><span data-stu-id="d6284-133">Memory consumption by internal system structures</span></span>
 <span data-ttu-id="d6284-134">La memoria viene utilizzata anche dagli oggetti di sistema, ad esempio le strutture transazionali, i buffer per file di dati e differenziali, le strutture di Garbage Collection e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="d6284-134">Memory is also consumed by system objects, such as, transactional structures, buffers for data and delta files, garbage collection structures, and more.</span></span> <span data-ttu-id="d6284-135">Per conoscere la memoria utilizzata da parte di questi oggetti di sistema, eseguire una query su `sys.dm_xtp_system_memory_consumers` come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="d6284-135">You can find the memory used for these system objects by querying `sys.dm_xtp_system_memory_consumers` as shown here.</span></span>

```sql
SELECT memory_consumer_desc
     , allocated_bytes/1024 AS allocated_bytes_kb
     , used_bytes/1024 AS used_bytes_kb
     , allocation_count
   FROM sys.dm_xtp_system_memory_consumers
```

 <span data-ttu-id="d6284-136">**Output di esempio**</span><span class="sxs-lookup"><span data-stu-id="d6284-136">**Sample Output**</span></span>

```
memory_consumer_ desc allocated_bytes_kb   used_bytes_kb        allocation_count
------------------------- -------------------- -------------------- ----------------
VARHEAP                   0                    0                    0
VARHEAP                   384                  0                    0
DBG_GC_OUTSTANDING_T      64                   64                   910
ACTIVE_TX_MAP_LOOKAS      0                    0                    0
RECOVERY_TABLE_CACHE      0                    0                    0
RECENTLY_USED_ROWS_L      192                  192                  261
RANGE_CURSOR_LOOKSID      0                    0                    0
HASH_CURSOR_LOOKASID      128                  128                  455
SAVEPOINT_LOOKASIDE       0                    0                    0
PARTIAL_INSERT_SET_L      192                  192                  351
CONSTRAINT_SET_LOOKA      192                  192                  646
SAVEPOINT_SET_LOOKAS      0                    0                    0
WRITE_SET_LOOKASIDE       192                  192                  183
SCAN_SET_LOOKASIDE        64                   64                   31
READ_SET_LOOKASIDE        0                    0                    0
TRANSACTION_LOOKASID      448                  448                  156
PGPOOL:256K               768                  768                  3
PGPOOL: 64K               0                    0                    0
PGPOOL:  4K               0                    0                    0
```

 <span data-ttu-id="d6284-137">Per altre informazioni, vedere [sys.dm_xtp_system_memory_consumers &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-xtp-table-memory-stats-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d6284-137">For more information see [sys.dm_xtp_system_memory_consumers &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-xtp-table-memory-stats-transact-sql).</span></span>


#### <a name="memory-consumption-at-run-time-when-accessing-memory-optimized-tables"></a><span data-ttu-id="d6284-138">Utilizzo della memoria in fase di esecuzione quando si accede alle tabelle ottimizzate per la memoria</span><span class="sxs-lookup"><span data-stu-id="d6284-138">Memory consumption at run-time when accessing memory-optimized tables</span></span>
 <span data-ttu-id="d6284-139">Per determinare la memoria utilizzata dalle strutture di runtime, ad esempio la cache delle procedure, eseguire la query riportata di seguito.</span><span class="sxs-lookup"><span data-stu-id="d6284-139">You can determine the memory consumed by run time structures, such as the procedure cache with the following query: run this query to get the memory used by run-time structures such as for the procedure cache.</span></span> <span data-ttu-id="d6284-140">Tutte le strutture di runtime sono contrassegnate con XTP.</span><span class="sxs-lookup"><span data-stu-id="d6284-140">All run-time structures are tagged with XTP.</span></span>

```sql
SELECT memory_object_address
     , pages_in_bytes
     , bytes_used
     , type
   FROM sys.dm_os_memory_objects WHERE type LIKE '%xtp%'
```

 <span data-ttu-id="d6284-141">**Output di esempio**</span><span class="sxs-lookup"><span data-stu-id="d6284-141">**Sample Output**</span></span>

```
memory_object_address pages_ in_bytes bytes_used type
--------------------- ------------------- ---------- ----
0x00000001F1EA8040    507904              NULL       MEMOBJ_XTPDB
0x00000001F1EAA040    68337664            NULL       MEMOBJ_XTPDB
0x00000001FD67A040    16384               NULL       MEMOBJ_XTPPROCCACHE
0x00000001FD68C040    16384               NULL       MEMOBJ_XTPPROCPARTITIONEDHEAP
0x00000001FD284040    16384               NULL       MEMOBJ_XTPPROCPARTITIONEDHEAP
0x00000001FD302040    16384               NULL       MEMOBJ_XTPPROCPARTITIONEDHEAP
0x00000001FD382040    16384               NULL       MEMOBJ_XTPPROCPARTITIONEDHEAP
0x00000001FD402040    16384               NULL       MEMOBJ_XTPPROCPARTITIONEDHEAP
0x00000001FD482040    16384               NULL       MEMOBJ_XTPPROCPARTITIONEDHEAP
0x00000001FD502040    16384               NULL       MEMOBJ_XTPPROCPARTITIONEDHEAP
0x00000001FD67E040    16384               NULL       MEMOBJ_XTPPROCPARTITIONEDHEAP
0x00000001F813C040    8192                NULL       MEMOBJ_XTPBLOCKALLOC
0x00000001F813E040    16842752            NULL       MEMOBJ_XTPBLOCKALLOC
```

 <span data-ttu-id="d6284-142">Per ulteriori informazioni, vedere [sys. dm_os_memory_objects (Transact-SQL)](/sql/relational-databases/system-dynamic-management-views/sys-dm-os-memory-objects-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d6284-142">For more information, see [sys.dm_os_memory_objects (Transact-SQL)](/sql/relational-databases/system-dynamic-management-views/sys-dm-os-memory-objects-transact-sql).</span></span>

#### <a name="memory-consumed-by-hek_2-engine-across-the-instance"></a><span data-ttu-id="d6284-143">Memoria utilizzata dal motore [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] nell'istanza</span><span class="sxs-lookup"><span data-stu-id="d6284-143">Memory consumed by [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] engine across the instance</span></span>
 <span data-ttu-id="d6284-144">La memoria allocata al motore [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] e agli oggetti ottimizzati per la memoria viene gestita in modo analogo a qualsiasi altro consumer di memoria all'interno dell'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d6284-144">Memory allocated to the [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] engine and the memory-optimized objects is managed the same way as any other memory consumer within a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="d6284-145">I clerk di tipo MEMORYCLERK_XTP tengono conto di tutta la memoria allocata al motore [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d6284-145">The clerks of type MEMORYCLERK_XTP accounts for all the memory allocated to [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] engine.</span></span> <span data-ttu-id="d6284-146">Utilizzare la query seguente per trovare tutta la memoria utilizzata dal motore [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d6284-146">Use the following query to find all the memory used by the [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] engine.</span></span>

```sql
-- this DMV accounts for all memory used by the hek_2 engine
SELECT type
     , name
     , memory_node_id
     , pages_kb/1024 AS pages_MB 
   FROM sys.dm_os_memory_clerks WHERE type LIKE '%xtp%'
```

 <span data-ttu-id="d6284-147">Nell'output campione viene mostrato che la memoria totale allocata corrisponde all'utilizzo di memoria a livello di sistema pari a 18 MB e 1358 MB allocati a un ID 5 del database.</span><span class="sxs-lookup"><span data-stu-id="d6284-147">The sample output shows that the total memory allocated is 18 MB system-level memory consumption and 1358MB allocated to database id of 5.</span></span> <span data-ttu-id="d6284-148">Poiché viene eseguito il mapping di questo database a un pool di risorse dedicato, questa memoria incide sul pool di risorse in questione.</span><span class="sxs-lookup"><span data-stu-id="d6284-148">Since this database is mapped to a dedicated resource pool, this memory is accounted for in that resource pool.</span></span>

 <span data-ttu-id="d6284-149">**Output di esempio**</span><span class="sxs-lookup"><span data-stu-id="d6284-149">**Sample Output**</span></span>

```
type                 name       memory_node_id pages_MB
-------------------- ---------- -------------- --------------------
MEMORYCLERK_XTP      Default    0              18
MEMORYCLERK_XTP      DB_ID_5    0              1358
MEMORYCLERK_XTP      Default    64             0
```

 <span data-ttu-id="d6284-150">Per ulteriori informazioni, vedere [sys. dm_os_memory_clerks (Transact-SQL)](/sql/relational-databases/system-dynamic-management-views/sys-dm-os-memory-clerks-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d6284-150">For more information, see [sys.dm_os_memory_clerks (Transact-SQL)](/sql/relational-databases/system-dynamic-management-views/sys-dm-os-memory-clerks-transact-sql).</span></span>

##   <a name="managing-memory-consumed-by-memory-optimized-objects"></a><span data-ttu-id="d6284-151">Gestione della memoria utilizzata dagli oggetti ottimizzati per la memoria</span><span class="sxs-lookup"><span data-stu-id="d6284-151">Managing memory consumed by memory-optimized objects</span></span>
 <span data-ttu-id="d6284-152">È possibile controllare la memoria totale utilizzata dalle tabelle ottimizzate per la memoria mediante l'associazione a un pool di risorse denominato, come descritto nell'argomento [Associare un database con tabelle ottimizzate per la memoria a un pool di risorse](bind-a-database-with-memory-optimized-tables-to-a-resource-pool.md).</span><span class="sxs-lookup"><span data-stu-id="d6284-152">You can control the total memory consumed by memory-optimized tables by binding it to a named resource pool as described in the topic [Bind a Database with Memory-Optimized Tables to a Resource Pool](bind-a-database-with-memory-optimized-tables-to-a-resource-pool.md).</span></span>

##  <a name="troubleshooting-memory-issues"></a><span data-ttu-id="d6284-153">Risoluzione dei problemi relativi alla memoria</span><span class="sxs-lookup"><span data-stu-id="d6284-153">Troubleshooting Memory Issues</span></span>
 <span data-ttu-id="d6284-154">La risoluzione dei problemi relativi alla memoria è un processo in tre passaggi:</span><span class="sxs-lookup"><span data-stu-id="d6284-154">Troubleshooting memory issues is a three step process:</span></span>

1.  <span data-ttu-id="d6284-155">Identificare la quantità di memoria utilizzata dagli oggetti nel database o nell'istanza.</span><span class="sxs-lookup"><span data-stu-id="d6284-155">Identify how much memory is being consumed by the objects in your database or instance.</span></span> <span data-ttu-id="d6284-156">È possibile utilizzare un'ampia gamma di strumenti di monitoraggio disponibili per le tabelle ottimizzate per la memoria, come indicato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="d6284-156">You can use a rich set of monitoring tools available for memory-optimized tables as described earlier.</span></span>  <span data-ttu-id="d6284-157">Ad esempio, le DMV `sys.dm_db_xtp_table_memory_stats` o `sys.dm_os_memory_clerks`.</span><span class="sxs-lookup"><span data-stu-id="d6284-157">For example the DMVs `sys.dm_db_xtp_table_memory_stats` or `sys.dm_os_memory_clerks`.</span></span>

2.  <span data-ttu-id="d6284-158">Determinare la crescita dell'utilizzo della memoria e quanto spazio disponibile rimane.</span><span class="sxs-lookup"><span data-stu-id="d6284-158">Determine how memory consumption is growing and how much head room you have left.</span></span> <span data-ttu-id="d6284-159">Attraverso il monitoraggio periodico dell'utilizzo della memoria è possibile capire la relativa modalità di crescita.</span><span class="sxs-lookup"><span data-stu-id="d6284-159">By monitoring the memory consumption periodically, you can know how the memory use is growing.</span></span> <span data-ttu-id="d6284-160">Ad esempio, se è stato eseguito il mapping del database a un pool di risorse denominato, è possibile monitorare il contatore delle prestazioni Memoria utilizzata (KB) per capire come cresce la memoria.</span><span class="sxs-lookup"><span data-stu-id="d6284-160">For example, if you have mapped the database to a named resource pool, you can monitor the performance counter Used Memory (KB) to see how memory usage is growing.</span></span>

3.  <span data-ttu-id="d6284-161">Adottare misure adeguate per contenere i potenziali problemi di memoria.</span><span class="sxs-lookup"><span data-stu-id="d6284-161">Take action to mitigate the potential memory issues.</span></span> <span data-ttu-id="d6284-162">Per ulteriori informazioni, vedere [risolvere i problemi di memoria insufficiente](resolve-out-of-memory-issues.md).</span><span class="sxs-lookup"><span data-stu-id="d6284-162">For more information, see [Resolve Out Of Memory Issues](resolve-out-of-memory-issues.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d6284-163">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d6284-163">See Also</span></span>
 <span data-ttu-id="d6284-164">[Associare un database con tabelle ottimizzate per la memoria a un pool di risorse](bind-a-database-with-memory-optimized-tables-to-a-resource-pool.md) [modificare MIN_MEMORY_PERCENT e MAX_MEMORY_PERCENT in un pool esistente](bind-a-database-with-memory-optimized-tables-to-a-resource-pool.md#change-min-memory-percent-and-max-memory-percent-on-an-existing-pool)</span><span class="sxs-lookup"><span data-stu-id="d6284-164">[Bind a Database with Memory-Optimized Tables to a Resource Pool](bind-a-database-with-memory-optimized-tables-to-a-resource-pool.md) [Change MIN_MEMORY_PERCENT and MAX_MEMORY_PERCENT on an existing pool](bind-a-database-with-memory-optimized-tables-to-a-resource-pool.md#change-min-memory-percent-and-max-memory-percent-on-an-existing-pool)</span></span>


