---
title: Migrazione di colonne calcolate | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 64a9eade-22c3-4a9d-ab50-956219e08df1
author: rothja
ms.author: jroth
ms.openlocfilehash: feb50ef64f42d95913ad4e13f9a79e6e0e4ecad3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725776"
---
# <a name="migrating-computed-columns"></a><span data-ttu-id="effeb-102">Migrazione di colonne calcolate</span><span class="sxs-lookup"><span data-stu-id="effeb-102">Migrating Computed Columns</span></span>
  <span data-ttu-id="effeb-103">Le colonne calcolate non sono supportate nelle tabelle ottimizzate per la memoria.</span><span class="sxs-lookup"><span data-stu-id="effeb-103">Computed columns are not supported in memory-optimized tables.</span></span> <span data-ttu-id="effeb-104">Tuttavia, è possibile simulare una colonna calcolata.</span><span class="sxs-lookup"><span data-stu-id="effeb-104">However, you can simulate a computed column.</span></span>  
  
 <span data-ttu-id="effeb-105">Valutare la necessità di rendere persistenti le colonne calcolate quando si esegue la migrazione delle tabelle basate su disco nelle tabelle ottimizzate per la memoria.</span><span class="sxs-lookup"><span data-stu-id="effeb-105">You should consider the need to persist your computed columns when you migrate your disk-based tables to memory-optimized tables.</span></span> <span data-ttu-id="effeb-106">Le diverse caratteristiche di prestazioni delle tabelle ottimizzate per la memoria e delle stored procedure compilate in modo nativo possono annullare la necessità della persistenza.</span><span class="sxs-lookup"><span data-stu-id="effeb-106">The different performance characteristics of memory-optimized tables and natively compiled stored procedures may negate the need for persistence.</span></span>  
  
## <a name="non-persisted-computed-columns"></a><span data-ttu-id="effeb-107">Colonne calcolate non persistenti</span><span class="sxs-lookup"><span data-stu-id="effeb-107">Non-Persisted Computed Columns</span></span>  
 <span data-ttu-id="effeb-108">Per simulare gli effetti di una colonna calcolata non persistente, creare una vista nella tabella ottimizzata per la memoria.</span><span class="sxs-lookup"><span data-stu-id="effeb-108">To simulate the effects of a non-persisted computed column, create a view on the memory-optimized table.</span></span> <span data-ttu-id="effeb-109">Nell'istruzione SELECT che definisce la vista, aggiungere la definizione della colonna calcolata nella vista.</span><span class="sxs-lookup"><span data-stu-id="effeb-109">In the SELECT statement that defines the view, add the computed column definition into the view.</span></span> <span data-ttu-id="effeb-110">Ad eccezione di una stored procedure compilata in modo nativo, le query che utilizzano i valori della colonna calcolata devono essere letti dalla vista.</span><span class="sxs-lookup"><span data-stu-id="effeb-110">Except in a natively compiled stored procedure, queries that use values from the computed column should read from the view.</span></span> <span data-ttu-id="effeb-111">All'interno delle stored procedure compilate in modo nativo, è consigliabile aggiornare tutte le istruzioni SELECT, UPDATE o DELETE in base alla definizione della colonna calcolata.</span><span class="sxs-lookup"><span data-stu-id="effeb-111">Inside natively compiled stored procedures, you should update any select, update, or delete statement according to your computed column definition.</span></span>  
  
```sql  
-- Schema for the table dbo.OrderDetails:  
-- OrderId int not null primary key,  
-- ProductId int not null,  
-- SalePrice money not null,  
-- Quantity int not null,  
-- Total money not null  
--  
-- Total is computed as SalePrice * Quantity and is not persisted.  
CREATE VIEW dbo.v_order_details AS  
   SELECT  
      OrderId,  
      ProductId,  
      SalePrice,  
      Quantity,  
      Quantity * SalePrice AS Total  
   FROM dbo.order_details  
```  
  
## <a name="persisted-computed-columns"></a><span data-ttu-id="effeb-112">Colonne calcolate persistenti</span><span class="sxs-lookup"><span data-stu-id="effeb-112">Persisted Computed Columns</span></span>  
 <span data-ttu-id="effeb-113">Per simulare gli effetti di una colonna calcolata persistente, creare una stored procedure per l'inserimento nella tabella e un'altra stored procedure per l'aggiornamento della tabella.</span><span class="sxs-lookup"><span data-stu-id="effeb-113">To simulate the effects of a persisted computed column, create a stored procedure for inserting into the table and another stored procedure for updating the table.</span></span> <span data-ttu-id="effeb-114">Quando si inserisce o si aggiorna la tabella, chiamare le stored procedure per eseguire queste attività.</span><span class="sxs-lookup"><span data-stu-id="effeb-114">When inserting or updating the table, invoke these stored procedures to perform these tasks.</span></span> <span data-ttu-id="effeb-115">All'interno delle stored procedure, calcolare il valore del campo calcolato in base agli input, analogamente al modo in cui viene definita la colonna calcolata nella tabella originale basata su disco.</span><span class="sxs-lookup"><span data-stu-id="effeb-115">Inside the stored procedures, calculate the value for the computed field according to the inputs, much like how the computed column is defined on the original disk-based table.</span></span> <span data-ttu-id="effeb-116">Quindi, inserire o aggiornare la tabella in base alle esigenze all'interno della stored procedure.</span><span class="sxs-lookup"><span data-stu-id="effeb-116">Then, insert or update the table as needed inside the stored procedure.</span></span>  
  
```sql  
-- Schema for the table dbo.OrderDetails:  
-- OrderId int not null primary key,  
-- ProductId int not null,  
-- SalePrice money not null,  
-- Quantity int not null,  
-- Total money not null  
--  
-- Total is computed as SalePrice * Quantity and is persisted.  
-- we need to create insert and update procedures to calculate Total.  
CREATE PROCEDURE sp_insert_order_details   
@OrderId int, @ProductId int, @SalePrice money, @Quantity int  
WITH NATIVE_COMPILATION, SCHEMABINDING, EXECUTE AS OWNER  
AS BEGIN ATOMIC WITH (LANGUAGE = N'english', TRANSACTION ISOLATION LEVEL = SNAPSHOT)  
-- compute the value here.   
-- this stored procedure works with single rows only.  
-- for bulk inserts, accept a table-valued parameter into the stored procedure  
-- and use an INSERT INTO SELECT statement.  
DECLARE @total money = @SalePrice * @Quantity  
INSERT INTO dbo.OrderDetails (OrderId, ProductId, SalePrice, Quantity, Total)  
VALUES (@OrderId, @ProductId, @SalePrice, @Quantity, @total)  
END  
GO  
  
CREATE PROCEDURE sp_update_order_details_by_id  
@OrderId int, @ProductId int, @SalePrice money, @Quantity int  
WITH NATIVE_COMPILATION, SCHEMABINDING, EXECUTE AS OWNER  
AS BEGIN ATOMIC WITH (LANGUAGE = N'english', TRANSACTION ISOLATION LEVEL = SNAPSHOT)  
-- compute the value here.   
-- this stored procedure works with single rows only.  
DECLARE @total money = @SalePrice * @Quantity  
UPDATE dbo.OrderDetails   
SET ProductId = @ProductId, SalePrice = @SalePrice, Quantity = @Quantity, Total = @total  
WHERE OrderId = @OrderId  
END  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="effeb-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="effeb-117">See Also</span></span>  
 [<span data-ttu-id="effeb-118">Migrazione a OLTP in memoria</span><span class="sxs-lookup"><span data-stu-id="effeb-118">Migrating to In-Memory OLTP</span></span>](migrating-to-in-memory-oltp.md)  
  
  
