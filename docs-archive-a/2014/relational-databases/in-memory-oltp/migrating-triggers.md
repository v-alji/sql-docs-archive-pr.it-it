---
title: Migrazione di trigger | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: ad5385c5-5a50-40ca-a319-97d5606b8511
author: rothja
ms.author: jroth
ms.openlocfilehash: 25965e7cce84b0dcfcd3b6ce6176e8ad3ddabc6a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725767"
---
# <a name="migrating-triggers"></a><span data-ttu-id="b80df-102">Migrazione di trigger</span><span class="sxs-lookup"><span data-stu-id="b80df-102">Migrating Triggers</span></span>
  <span data-ttu-id="b80df-103">In questo argomento vengono illustrati i trigger DDL e DML e le tabelle ottimizzate per la memoria.</span><span class="sxs-lookup"><span data-stu-id="b80df-103">This topic discusses DDL and DML triggers and memory-optimized tables.</span></span>  
  
 <span data-ttu-id="b80df-104">I trigger LOGON sono trigger definiti per l'attivazione in corrispondenza di eventi LOGON.</span><span class="sxs-lookup"><span data-stu-id="b80df-104">LOGON triggers are triggers defined to fire on LOGON events.</span></span> <span data-ttu-id="b80df-105">I trigger LOGON non influiscono sulle tabelle ottimizzate per la memoria.</span><span class="sxs-lookup"><span data-stu-id="b80df-105">LOGON triggers do not affect memory-optimized tables.</span></span>  
  
## <a name="ddl-triggers"></a><span data-ttu-id="b80df-106">Trigger DDL</span><span class="sxs-lookup"><span data-stu-id="b80df-106">DDL Triggers</span></span>  
 <span data-ttu-id="b80df-107">I trigger DDL sono trigger definiti per l'attivazione quando un'istruzione CREATE, ALTER, DROP, GRANT, DENY, REVOKE o UPDATE STATISTICS viene eseguita nel database o nel server in cui è definita.</span><span class="sxs-lookup"><span data-stu-id="b80df-107">DDL triggers are triggers defined to fire when a CREATE, ALTER, DROP, GRANT, DENY, REVOKE, or UPDATE STATISTICS statement is executed on the database or server on which it is defined.</span></span>  
  
 <span data-ttu-id="b80df-108">Non è possibile creare tabelle ottimizzate per la memoria se nel database o nel server sono definiti uno o più trigger DDL per l'evento CREATE_TABLE o per qualsiasi gruppo di eventi in cui questo sia incluso.</span><span class="sxs-lookup"><span data-stu-id="b80df-108">You cannot create memory-optimized tables if the database or server has one or more DDL trigger defined on CREATE_TABLE or any event group that includes it.</span></span> <span data-ttu-id="b80df-109">Non è possibile eliminare una tabella ottimizzata per la memoria se nel database o nel server sono definiti uno o più trigger DDL per l'evento DROP_TABLE o per qualsiasi gruppo di eventi in cui questo sia incluso.</span><span class="sxs-lookup"><span data-stu-id="b80df-109">You cannot drop a memory-optimized table if the database or server has one or more DDL trigger defined on DROP_TABLE or any event group that includes it.</span></span>  
  
 <span data-ttu-id="b80df-110">Non è possibile creare stored procedure compilate in modo nativo se sono presenti uno o più trigger DDL per gli eventi CREATE_PROCEDURE, DROP_PROCEDURE o per qualsiasi gruppo di eventi in cui questi siano inclusi.</span><span class="sxs-lookup"><span data-stu-id="b80df-110">You cannot create natively compiled stored procedures if there are one or more DDL triggers on CREATE_PROCEDURE, DROP_PROCEDURE, or any event group that includes those events.</span></span>  
  
## <a name="dml-triggers"></a><span data-ttu-id="b80df-111">Trigger DML</span><span class="sxs-lookup"><span data-stu-id="b80df-111">DML Triggers</span></span>  
 <span data-ttu-id="b80df-112">Non è possibile definire trigger DML nelle tabelle ottimizzate per la memoria.</span><span class="sxs-lookup"><span data-stu-id="b80df-112">DML triggers cannot be defined on memory-optimized tables.</span></span> <span data-ttu-id="b80df-113">Tuttavia, OLTP in memoria consente ottenere un effetto simile a quello dei trigger DML se si utilizzano stored procedure in modo esplicito per inserire, aggiornare o eliminare dati.</span><span class="sxs-lookup"><span data-stu-id="b80df-113">However, In-Memory OLTP allows you to achieve an effect similar to DML triggers if you explicitly use stored procedures to insert, update, or delete data.</span></span> <span data-ttu-id="b80df-114">Se il sistema contiene query ad hoc, convertirle al fine di utilizzare queste stored procedure anziché simulare l'effetto dei trigger DML.</span><span class="sxs-lookup"><span data-stu-id="b80df-114">If your system contains ad-hoc queries, convert them to use these stored procedures instead to simulate the effect of DML triggers.</span></span>  
  
 <span data-ttu-id="b80df-115">A seconda dell'evento trigger (FOR/AFTER o INSTEAD OF), è possibile includere il contenuto del trigger nella stored procedure appropriata che esegue un'istruzione INSERT, UPDATE o DELETE su quella tabella.</span><span class="sxs-lookup"><span data-stu-id="b80df-115">Depending on the trigger event (FOR/AFTER or INSTEAD OF), you may include the content of the trigger in the appropriate stored procedure that performs INSERT, UPDATE, or DELETE on that table.</span></span> <span data-ttu-id="b80df-116">Ad esempio quando si esegue la migrazione di un trigger AFTER INSERT, è possibile modificare la stored procedure che esegue l'operazione di inserimento includendo il contenuto del trigger dopo l'istruzione INSERT appropriata.</span><span class="sxs-lookup"><span data-stu-id="b80df-116">For example, when migrating an AFTER INSERT trigger, you could alter the stored procedure that performs the insert operation by including the content of the trigger after the appropriate INSERT statement.</span></span>  
  
 <span data-ttu-id="b80df-117">È possibile utilizzare una stored procedure interpretata o una stored procedure compilata in modo nativo.</span><span class="sxs-lookup"><span data-stu-id="b80df-117">You can use an interpreted stored procedure or a natively compiled stored procedure.</span></span> <span data-ttu-id="b80df-118">La maggior parte dei costrutti di [!INCLUDE[tsql](../../includes/tsql-md.md)] in una stored procedure interpretata può essere eseguita in una tabella ottimizzata per la memoria.</span><span class="sxs-lookup"><span data-stu-id="b80df-118">Most [!INCLUDE[tsql](../../includes/tsql-md.md)] constructs in an interpreted stored procedure can execute on a memory-optimized table.</span></span> <span data-ttu-id="b80df-119">Tuttavia, solo un subset di costrutti di [!INCLUDE[tsql](../../includes/tsql-md.md)] è supportato nelle stored procedure compilate in modo nativo.</span><span class="sxs-lookup"><span data-stu-id="b80df-119">However, only a subset of [!INCLUDE[tsql](../../includes/tsql-md.md)] constructs are supported in natively compiled stored procedures.</span></span> <span data-ttu-id="b80df-120">Per informazioni sul [!INCLUDE[tsql](../../includes/tsql-md.md)] supporto per le tabelle ottimizzate per la memoria, vedere [accesso alle tabelle ottimizzate per la memoria usando Transact-SQL interpretato](accessing-memory-optimized-tables-using-interpreted-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="b80df-120">For information on [!INCLUDE[tsql](../../includes/tsql-md.md)] support on memory-optimized tables, see [Accessing Memory-Optimized Tables Using Interpreted Transact-SQL](accessing-memory-optimized-tables-using-interpreted-transact-sql.md).</span></span> <span data-ttu-id="b80df-121">Per informazioni sul [!INCLUDE[tsql](../../includes/tsql-md.md)] supporto di stored procedure compilate in modo nativo, vedere [costrutti Transact-SQL non supportati da OLTP in memoria](transact-sql-constructs-not-supported-by-in-memory-oltp.md).</span><span class="sxs-lookup"><span data-stu-id="b80df-121">For information on [!INCLUDE[tsql](../../includes/tsql-md.md)] support in natively compiled stored procedures, see [Transact-SQL Constructs Not Supported by In-Memory OLTP](transact-sql-constructs-not-supported-by-in-memory-oltp.md).</span></span>  
  
 <span data-ttu-id="b80df-122">Di seguito è riportato un semplice esempio di simulazione del comportamento del trigger DML in una tabella ottimizzata per la memoria.</span><span class="sxs-lookup"><span data-stu-id="b80df-122">The following is a simple example of simulating DML trigger behavior on a memory-optimized table.</span></span>  
  
 <span data-ttu-id="b80df-123">Il database contiene gli oggetti seguenti, inseriti nello script come istruzioni CREATE TABLE, CREATE TRIGGER e CREATE PROCEDURE:</span><span class="sxs-lookup"><span data-stu-id="b80df-123">The database contains the following objects, scripted as CREATE TABLE, CREATE TRIGGER, and CREATE PROCEDURE statements:</span></span>  
  
```sql  
CREATE TABLE OrderDetails  
(  
   OrderId int not null primary key,  
   ProductId int not null,  
   SalePrice money not null,  
   Quantity int not null,  
   Total money not null,  
   IsDeleted bit not null DEFAULT (0)  
)  
GO  
  
CREATE TRIGGER tr_order_details_insteadof_insert  
ON OrderDetails  
INSTEAD OF INSERT AS  
BEGIN  
   DECLARE @pid int, @qty_buy int, @qty_remain int  
   SELECT @pid = ProductId, @qty_buy = Quantity FROM inserted  
   SELECT @qty_remain = Quantity FROM Inventory WHERE ProductId = @pid  
   IF (@qty_remain <= @qty_buy)  
      THROW 51000, N'Insufficient inventory!', 1  
   ELSE  
   BEGIN  
      INSERT INTO dbo.OrderDetails (OrderId, ProductId, SalePrice, Quantity, Total)   
      SELECT OrderId, ProductId, SalePrice, Quantity, Total FROM inserted  
      UPDATE Inventory SET Quantity = Quantity - @qty_buy WHERE ProductId = @pid  
   END  
END  
GO  
  
CREATE TRIGGER tr_order_details_after_update  
ON OrderDetails  
AFTER UPDATE AS  
BEGIN  
   INSERT INTO UpdateNotifications (OrderId, UpdateTime) SELECT OrderId, GETDATE() FROM inserted     
END  
GO  
  
CREATE PROCEDURE sp_insert_order_details   
   @OrderId int, @ProductId int, @SalePrice money, @Quantity int, @total money  
AS BEGIN  
   INSERT INTO dbo.OrderDetails (OrderId, ProductId, SalePrice, Quantity, Total)  
   VALUES (@OrderId, @ProductId, @SalePrice, @Quantity, @total)  
END  
GO  
  
CREATE PROCEDURE sp_update_order_details_by_id  
   @OrderId int, @ProductId int, @SalePrice money, @Quantity int, @Total money  
AS BEGIN  
   UPDATE dbo.OrderDetails   
   SET ProductId = @ProductId, SalePrice = @SalePrice, Quantity = @Quantity, Total = @total  
   WHERE OrderId = @OrderId  
END  
GO  
```  
  
 <span data-ttu-id="b80df-124">Gli oggetti seguenti, dal punto di vista funzionale sono equivalenti allo stato precedente alla migrazione:</span><span class="sxs-lookup"><span data-stu-id="b80df-124">The following objects are functionally equivalent to the pre-migration state:</span></span>  
  
```sql  
CREATE TABLE OrderDetails  
(  
   OrderId int not null PRIMARY KEY NONCLUSTERED HASH WITH (BUCKET_COUNT = 1048576),  
   ProductId int not null,  
   SalePrice money not null,  
   Quantity int not null,  
   Total money not null,  
   IsDeleted bit not null DEFAULT (0)  
) WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_AND_DATA)  
GO  
  
CREATE TABLE Inventory  
(  
   ProductId int not null PRIMARY KEY NONCLUSTERED,  
   Quantity int not null  
) WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_AND_DATA)  
GO  
  
CREATE TABLE UpdateNotifications  
(  
   OrderId int not null,  
   UpdateTime datetime2 not null  
   CONSTRAINT pk_updateNotifications PRIMARY KEY NONCLUSTERED (OrderId, UpdateTime)  
) WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_AND_DATA)  
GO  
  
CREATE PROCEDURE sp_insert_order_details   
   @OrderId int, @ProductId int, @SalePrice money, @Quantity int, @total money  
WITH NATIVE_COMPILATION, SCHEMABINDING, EXECUTE AS OWNER  
AS BEGIN ATOMIC WITH (TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE = N'English')  
   DECLARE @qty_remain int  
   SELECT @qty_remain = Quantity FROM dbo.Inventory WHERE ProductId = @ProductId  
   IF (@qty_remain <= @Quantity)  
      THROW 51000, N'Insufficient inventory!', 1  
   ELSE  
   BEGIN  
      INSERT INTO dbo.OrderDetails (OrderId, ProductId, SalePrice, Quantity, Total)   
      VALUES (@OrderId, @ProductId, @SalePrice, @Quantity, @total)  
      UPDATE dbo.Inventory SET Quantity = Quantity - @Quantity WHERE ProductId = @ProductId  
   END  
END  
GO  
  
CREATE PROCEDURE sp_update_order_details_by_id  
   @OrderId int, @ProductId int, @SalePrice money, @Quantity int, @Total money  
WITH NATIVE_COMPILATION, SCHEMABINDING, EXECUTE AS OWNER  
AS BEGIN ATOMIC WITH (TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE = N'English')  
   UPDATE dbo.OrderDetails   
   SET ProductId = @ProductId, SalePrice = @SalePrice, Quantity = @Quantity, Total = @total  
   WHERE OrderId = @OrderId  
   INSERT INTO dbo.UpdateNotifications (OrderId, UpdateTime) VALUES (@OrderId, GETDATE())  
END  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="b80df-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b80df-125">See Also</span></span>  
 [<span data-ttu-id="b80df-126">Migrazione a OLTP in memoria</span><span class="sxs-lookup"><span data-stu-id="b80df-126">Migrating to In-Memory OLTP</span></span>](migrating-to-in-memory-oltp.md)  
  
  
