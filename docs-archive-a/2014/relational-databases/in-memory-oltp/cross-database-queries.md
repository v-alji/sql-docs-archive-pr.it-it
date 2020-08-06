---
title: Query tra database | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: a0305f5b-91bd-4d18-a2fc-ec235b062fd3
author: rothja
ms.author: jroth
ms.openlocfilehash: 4afbb580a55273ec241005493fd37f99e98ec0e7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626093"
---
# <a name="cross-database-queries"></a><span data-ttu-id="366b0-102">Query tra database</span><span class="sxs-lookup"><span data-stu-id="366b0-102">Cross-Database Queries</span></span>
  <span data-ttu-id="366b0-103">In [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] le tabelle ottimizzate per la memoria non supportano le transazioni tra database.</span><span class="sxs-lookup"><span data-stu-id="366b0-103">In [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)], memory-optimized tables do not support cross-database transactions.</span></span> <span data-ttu-id="366b0-104">Non è possibile accedere a un altro database dalla stessa transazione o dalla stessa query che accede anche a una tabella ottimizzata per la memoria.</span><span class="sxs-lookup"><span data-stu-id="366b0-104">You cannot access another database from the same transaction or the same query that also accesses a memory-optimized table.</span></span> <span data-ttu-id="366b0-105">Non è possibile copiare facilmente i dati da una tabella in un database a una tabella ottimizzata per la memoria in un altro database.</span><span class="sxs-lookup"><span data-stu-id="366b0-105">You cannot easily copy data from a table in one database, to a memory-optimized table in another database.</span></span>  
  
 <span data-ttu-id="366b0-106">Le variabili di tabella non sono transazionali.</span><span class="sxs-lookup"><span data-stu-id="366b0-106">Table variables are not transactional.</span></span> <span data-ttu-id="366b0-107">Pertanto, le variabili di tabella ottimizzata per la memoria possono essere utilizzate nelle query tra database e possono quindi facilitare lo spostamento di dati da un database nelle tabelle ottimizzate per la memoria a un altro.</span><span class="sxs-lookup"><span data-stu-id="366b0-107">Therefore, memory-optimized table variables can be used in cross-database queries, and can thus facilitate moving data from one database into memory-optimized tables in another.</span></span> <span data-ttu-id="366b0-108">È possibile utilizzare due transazioni.</span><span class="sxs-lookup"><span data-stu-id="366b0-108">You can use two transactions.</span></span> <span data-ttu-id="366b0-109">Nella prima transazione, inserire i dati della tabella remota nella variabile.</span><span class="sxs-lookup"><span data-stu-id="366b0-109">In the first transaction, insert the data from the remote table into the variable.</span></span> <span data-ttu-id="366b0-110">Nella seconda transazione, inserire i dati nella tabella ottimizzata per la memoria locale dalla variabile.</span><span class="sxs-lookup"><span data-stu-id="366b0-110">In the second transaction, insert the data into the local memory-optimized table from the variable.</span></span>  
  
 <span data-ttu-id="366b0-111">Ad esempio, per copiare la riga dalla tabella T1 nel database DB1 alla tabella T2 in DB2, usando @v1 una variabile di tipo dbo. TT1, è possibile usare qualcosa di simile a quanto segue:</span><span class="sxs-lookup"><span data-stu-id="366b0-111">For example, to copy the row from table t1 in database db1 to table t2 in db2, using variable @v1 of type dbo.tt1, you can use something like:</span></span>  
  
```sql  
USE db2   
GO   
DECLARE @v1 dbo.tt1   
INSERT @v1 SELECT * FROM db1.dbo.t1   
INSERT dbo.t2 SELECT * FROM @v1   
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="366b0-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="366b0-112">See Also</span></span>  
 [<span data-ttu-id="366b0-113">Migrazione a OLTP in memoria</span><span class="sxs-lookup"><span data-stu-id="366b0-113">Migrating to In-Memory OLTP</span></span>](migrating-to-in-memory-oltp.md)  
  
  
