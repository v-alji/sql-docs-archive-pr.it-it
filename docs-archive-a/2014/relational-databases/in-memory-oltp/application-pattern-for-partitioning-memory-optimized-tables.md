---
title: Modello di applicazione per il partizionamento di tabelle con ottimizzazione per la memoria | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 3f867763-a8e6-413a-b015-20e9672cc4d1
author: rothja
ms.author: jroth
ms.openlocfilehash: d2633cdf1b631a1d9209adf26f4773e27c4c44c4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624714"
---
# <a name="application-pattern-for-partitioning-memory-optimized-tables"></a><span data-ttu-id="3f9ff-102">Modello di applicazione per il partizionamento di tabelle con ottimizzazione per la memoria</span><span class="sxs-lookup"><span data-stu-id="3f9ff-102">Application Pattern for Partitioning Memory-Optimized Tables</span></span>
  [!INCLUDE[hek_2](../../includes/hek-2-md.md)] <span data-ttu-id="3f9ff-103">supporta un modello in cui una quantità limitata di dati attivi viene mantenuta in una tabella ottimizzata per la memoria, mentre i dati usati meno di frequente vengono elaborati su disco.</span><span class="sxs-lookup"><span data-stu-id="3f9ff-103">supports a pattern where a limited amount of active data is kept in a memory-optimized table, while less-frequently accessed data is processed on disk.</span></span> <span data-ttu-id="3f9ff-104">In genere, si tratta di uno scenario in cui i dati vengono archiviati in base a una chiave `datetime`.</span><span class="sxs-lookup"><span data-stu-id="3f9ff-104">Typically, this would be a scenario where data is stored based on a `datetime` key.</span></span>  
  
 <span data-ttu-id="3f9ff-105">È possibile emulare tabelle partizionate con tabelle ottimizzate per la memoria mantenendo una tabella partizionata e una tabella ottimizzata per la memoria con uno schema comune.</span><span class="sxs-lookup"><span data-stu-id="3f9ff-105">You can emulate partitioned tables with memory-optimized tables by maintaining a partitioned table and a memory-optimized table with a common schema.</span></span> <span data-ttu-id="3f9ff-106">I dati correnti verranno inseriti e aggiornati nella tabella ottimizzata per la memoria, mentre i dati utilizzati meno frequentemente verranno gestiti nella tabella partizionata tradizionale.</span><span class="sxs-lookup"><span data-stu-id="3f9ff-106">Current data would be inserted and updated in the memory-optimized table, while less-frequently accessed data would be maintained in the traditional partitioned table.</span></span>  
  
 <span data-ttu-id="3f9ff-107">Un'applicazione che riconosce i dati attivi in una tabella ottimizzata per la memoria può utilizzare le stored procedure compilate in modo nativo per accedere ai dati.</span><span class="sxs-lookup"><span data-stu-id="3f9ff-107">An application that knows that the active data is in a memory-optimized table can use natively compiled stored procedures to access the data.</span></span> <span data-ttu-id="3f9ff-108">Le operazioni che devono accedere all'intero intervallo di dati, o che non sono in grado di riconoscere quale tabella contiene i dati rilevanti, utilizzano codice [!INCLUDE[tsql](../../includes/tsql-md.md)] interpretato per creare un join tra la tabella ottimizzata per la memoria e la tabella partizionata.</span><span class="sxs-lookup"><span data-stu-id="3f9ff-108">Operations that need to access the entire span of data, or which may not know which table holds relevant data, use interpreted [!INCLUDE[tsql](../../includes/tsql-md.md)] to join the memory-optimized table with the partitioned table.</span></span>  
  
 <span data-ttu-id="3f9ff-109">Questo cambio di partizione è descritto di seguito:</span><span class="sxs-lookup"><span data-stu-id="3f9ff-109">This partition switch is described as follows:</span></span>  
  
-   <span data-ttu-id="3f9ff-110">Inserire i dati dalla tabella di OLTP in memoria in una tabella di staging, eventualmente utilizzando una data limite.</span><span class="sxs-lookup"><span data-stu-id="3f9ff-110">Insert data from the In-Memory OLTP table into a staging table, possibly using a cutoff date.</span></span>  
  
-   <span data-ttu-id="3f9ff-111">Eliminare gli stessi dati dalla tabella ottimizzata per la memoria.</span><span class="sxs-lookup"><span data-stu-id="3f9ff-111">Delete the same data from the memory-optimized table.</span></span>  
  
-   <span data-ttu-id="3f9ff-112">Passare alla tabella di staging.</span><span class="sxs-lookup"><span data-stu-id="3f9ff-112">Swap in the staging table.</span></span>  
  
-   <span data-ttu-id="3f9ff-113">Aggiungere la partizione attiva.</span><span class="sxs-lookup"><span data-stu-id="3f9ff-113">Add the active partition.</span></span>  
  
 <span data-ttu-id="3f9ff-114">![Cambio di partizione.](../../database-engine/media/hekaton-partitioned-tables.gif "Cambio di partizione.")</span><span class="sxs-lookup"><span data-stu-id="3f9ff-114">![Partition switch.](../../database-engine/media/hekaton-partitioned-tables.gif "Partition switch.")</span></span>  
<span data-ttu-id="3f9ff-115">Manutenzione dei dati attivi</span><span class="sxs-lookup"><span data-stu-id="3f9ff-115">Active Data Maintenance</span></span>  
  
 <span data-ttu-id="3f9ff-116">Le azioni che iniziano con Deleting ActiveOrders devono essere eseguite durante una sessione di manutenzione per evitare che le query non rilevino i dati durante il periodo tra l'eliminazione dei dati e il passaggio alla tabella di staging.</span><span class="sxs-lookup"><span data-stu-id="3f9ff-116">The actions starting with Deleting ActiveOrders need to be done during a maintenance window to avoid queries missing data during the time between deleting data and switching in the staging table.</span></span>  
  
 <span data-ttu-id="3f9ff-117">Per un esempio correlato, vedere [Partizionamento a livello di applicazione](application-level-partitioning.md).</span><span class="sxs-lookup"><span data-stu-id="3f9ff-117">For a related sample, see [Application-Level Partitioning](application-level-partitioning.md).</span></span>  
  
## <a name="code-sample"></a><span data-ttu-id="3f9ff-118">Codice di esempio</span><span class="sxs-lookup"><span data-stu-id="3f9ff-118">Code Sample</span></span>  
 <span data-ttu-id="3f9ff-119">Nell'esempio seguente viene illustrato come utilizzare una tabella ottimizzata per la memoria con una tabella basata su disco partizionata.</span><span class="sxs-lookup"><span data-stu-id="3f9ff-119">The following sample shows how to use a memory-optimized table with a partitioned disk-based table.</span></span> <span data-ttu-id="3f9ff-120">I dati utilizzati frequentemente vengono archiviati in memoria.</span><span class="sxs-lookup"><span data-stu-id="3f9ff-120">Frequently-used data is stored in memory.</span></span> <span data-ttu-id="3f9ff-121">Per salvare i dati su disco, creare una nuova partizione e copiare i dati nella tabella partizionata.</span><span class="sxs-lookup"><span data-stu-id="3f9ff-121">To save the data to disk, create a new partition and copy the data to the partitioned table.</span></span>  
  
 <span data-ttu-id="3f9ff-122">Nella prima parte di questo esempio vengono creati il database e gli oggetti necessari.</span><span class="sxs-lookup"><span data-stu-id="3f9ff-122">The first part of this sample creates the database and necessary objects.</span></span> <span data-ttu-id="3f9ff-123">Nella seconda parte di questo esempio viene illustrato come spostare i dati da una tabella ottimizzata per la memoria in una tabella partizionata.</span><span class="sxs-lookup"><span data-stu-id="3f9ff-123">The second part of the sample shows how to move data from a memory-optimized table into a partitioned table.</span></span>  
  
```sql  
CREATE DATABASE partitionsample;  
GO  
  
-- enable for In-Memory OLTP - change file path as needed  
ALTER DATABASE partitionsample ADD FILEGROUP partitionsample_mod CONTAINS MEMORY_OPTIMIZED_DATA  
ALTER DATABASE partitionsample ADD FILE( NAME = 'partitionsample_mod' , FILENAME = 'c:\data\partitionsample_mod') TO FILEGROUP partitionsample_mod;  
GO  
  
USE partitionsample;  
GO  
  
-- frequently used portion of the SalesOrders - memory-optimized  
  
CREATE TABLE dbo.SalesOrders_hot (  
   so_id INT IDENTITY PRIMARY KEY NONCLUSTERED,  
   cust_id INT NOT NULL,  
   so_date DATETIME2 NOT NULL INDEX ix_date NONCLUSTERED,  
   so_total MONEY NOT NULL,  
   INDEX ix_date_total NONCLUSTERED (so_date desc, so_total desc)  
) WITH (MEMORY_OPTIMIZED=ON)  
GO  
  
-- cold portion of the SalesOrders - partitioned disk-based table  
CREATE PARTITION FUNCTION [ByDatePF](datetime2) AS RANGE RIGHT   
   FOR VALUES();  
GO  
  
CREATE PARTITION SCHEME [ByDateRange]   
   AS PARTITION [ByDatePF]   
   ALL TO ([PRIMARY]);  
GO  
  
CREATE TABLE dbo.SalesOrders_cold (  
   so_id INT NOT NULL,  
   cust_id INT NOT NULL,  
   so_date DATETIME2 NOT NULL,  
   so_total MONEY NOT NULL,  
   CONSTRAINT PK_SalesOrders_cold PRIMARY KEY (so_id, so_date),  
   INDEX ix_date_total NONCLUSTERED (so_date desc, so_total desc)  
) ON [ByDateRange](so_date)  
GO  
  
-- table for temporary partitions  
CREATE TABLE dbo.SalesOrders_cold_staging (  
   so_id INT NOT NULL,  
   cust_id INT NOT NULL,  
   so_date datetime2 NOT NULL,  
   so_total MONEY NOT NULL,  
   CONSTRAINT PK_SalesOrders_cold_staging PRIMARY KEY (so_id, so_date),  
   INDEX ix_date_total NONCLUSTERED (so_date desc, so_total desc),  
   CONSTRAINT CHK_SalesOrders_cold_staging CHECK (so_date >= '1900-01-01')  
)  
GO  
  
-- aggregate view of the hot and cold data  
CREATE VIEW dbo.SalesOrders  
AS SELECT so_id,  
   cust_id,  
   so_date,  
   so_total,  
   1 AS 'is_hot'  
   FROM dbo.SalesOrders_hot  
   UNION ALL  
   SELECT so_id,  
          cust_id,  
          so_date,  
          so_total,  
          0 AS 'is_hot'  
          FROM dbo.SalesOrders_cold;  
GO  
  
-- move all sales orders up to the split date to cold storage  
CREATE PROCEDURE dbo.usp_SalesOrdersOffloadToCold @splitdate datetime2  
   AS  
   BEGIN  
      BEGIN TRANSACTION;  
      -- create new heap based on the hot data to be moved to cold storage  
      INSERT INTO dbo.SalesOrders_cold_staging WITH( TABLOCKX)  
      SELECT so_id , cust_id , so_date , so_total  
         FROM dbo.SalesOrders_hot WITH ( serializable)  
         WHERE so_date <= @splitdate;  
  
      -- remove moved data  
      DELETE FROM dbo.SalesOrders_hot WITH( SERIALIZABLE)  
         WHERE so_date <= @splitdate;  
  
      -- update partition function, and switch in new partition  
      ALTER PARTITION SCHEME [ByDateRange] NEXT USED [PRIMARY];  
  
      DECLARE @p INT = ( SELECT MAX( partition_number) FROM sys.partitions WHERE object_id = OBJECT_ID( 'dbo.SalesOrders_cold'));  
      EXEC sp_executesql N'alter table dbo.SalesOrders_cold_staging  
         SWITCH TO dbo.SalesOrders_cold partition @i' , N'@i int' , @i = @p;  
  
      ALTER PARTITION FUNCTION [ByDatePF]()  
      SPLIT RANGE( @splitdate);  
  
      -- modify constraint on staging table to align with new partition  
      ALTER TABLE dbo.SalesOrders_cold_staging DROP CONSTRAINT CHK_SalesOrders_cold_staging;  
  
      DECLARE @s nvarchar( 100) = CONVERT( nvarchar( 100) , @splitdate , 121);  
      DECLARE @sql nvarchar( 1000) = N'alter table dbo.SalesOrders_cold_staging   
         add constraint CHK_SalesOrders_cold_staging check (so_date > ''' + @s + ''')';  
      PRINT @sql;  
      EXEC sp_executesql @sql;  
  
      COMMIT;  
END;  
GO  
  
-- insert sample values in the hot table  
INSERT INTO dbo.SalesOrders_hot VALUES(1,SYSDATETIME(), 1);   
GO  
  
INSERT INTO dbo.SalesOrders_hot VALUES(1, SYSDATETIME(), 1);  
GO  
  
INSERT INTO dbo.SalesOrders_hot VALUES(1, SYSDATETIME(), 1);  
GO  
  
-- verify contents of the table  
SELECT *  FROM dbo.SalesOrders;  
GO  
  
-- offload all sales orders to date to cold storage  
DECLARE  @t datetime2 = SYSDATETIME();  
EXEC dbo.usp_SalesOrdersOffloadToCold @t;  
  
-- verify contents of the tables  
SELECT * FROM dbo.SalesOrders;  
GO  
  
-- verify partitions  
SELECT OBJECT_NAME( object_id) , * FROM sys.dm_db_partition_stats ps  
   WHERE object_id = OBJECT_ID( 'dbo.SalesOrders_cold');  
  
-- insert more rows in the hot table  
INSERT INTO dbo.SalesOrders_hot VALUES(2, SYSDATETIME(), 1);  
GO  
  
INSERT INTO dbo.SalesOrders_hot VALUES(2, SYSDATETIME(), 1);  
GO  
  
INSERT INTO dbo.SalesOrders_hot VALUES(2, SYSDATETIME(), 1);  
GO  
  
-- verify contents of the tables  
SELECT * FROM dbo.SalesOrders;  
GO  
  
-- offload all sales orders to date to cold storage  
DECLARE @t datetime2 = SYSDATETIME();  
EXEC dbo.usp_SalesOrdersOffloadToCold @t;  
  
-- verify contents of the tables  
SELECT * FROM dbo.SalesOrders;  
GO  
  
-- verify partitions  
SELECT OBJECT_NAME( object_id) , partition_number , row_count  FROM sys.dm_db_partition_stats ps  
  WHERE object_id = OBJECT_ID( 'dbo.SalesOrders_cold') AND index_id = 1;  
```  
  
## <a name="see-also"></a><span data-ttu-id="3f9ff-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3f9ff-124">See Also</span></span>  
 [<span data-ttu-id="3f9ff-125">Tabelle ottimizzate per la memoria</span><span class="sxs-lookup"><span data-stu-id="3f9ff-125">Memory-Optimized Tables</span></span>](memory-optimized-tables.md)  
  
  
