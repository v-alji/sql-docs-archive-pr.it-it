---
title: Supporto di Transact-SQL per OLTP in memoria | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: b1cc7c30-1747-4c21-88ac-e95a5e58baac
author: rothja
ms.author: jroth
ms.openlocfilehash: bf3708a258e3bb97231e45b10bea2c59351a06a2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724656"
---
# <a name="transact-sql-support-for-in-memory-oltp"></a><span data-ttu-id="849aa-102">Supporto di Transact-SQL per OLTP in memoria</span><span class="sxs-lookup"><span data-stu-id="849aa-102">Transact-SQL Support for In-Memory OLTP</span></span>
  <span data-ttu-id="849aa-103">È possibile accedere alle tabelle ottimizzate per la memoria usando qualsiasi query Transact-SQL o istruzione DML sta(SELECT, INSERT, UPDATE o DELETE), query ad hoc e modulo SQL, ad esempio stored procedure, funzioni con valori di tabella, funzioni scalari, trigger e visualizzazioni.</span><span class="sxs-lookup"><span data-stu-id="849aa-103">You can access memory-optimized tables using any Transact-SQL query or DML statement (SELECT, INSERT, UPDATE, or DELETE), ad hoc statement, and SQL module such as stored procedures, table-value functions, scalar functions, triggers, and views.</span></span> <span data-ttu-id="849aa-104">Per altre informazioni, vedere [accesso alle tabelle ottimizzate per la memoria usando Transact-SQL interpretato](accessing-memory-optimized-tables-using-interpreted-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="849aa-104">For more information see [Accessing Memory-Optimized Tables Using Interpreted Transact-SQL](accessing-memory-optimized-tables-using-interpreted-transact-sql.md).</span></span>  
  
 <span data-ttu-id="849aa-105">Le stored procedure che fanno riferimento solo alle tabelle ottimizzate per la memoria possono essere compilate in modo nativo nel codice macchina e in genere forniscono un notevole miglioramento delle prestazioni rispetto alle stored procedure interpretate (basate su disco).</span><span class="sxs-lookup"><span data-stu-id="849aa-105">Stored procedures that only reference memory-optimized tables can be natively compiled into machine code and typically provide significant performance gains over interpreted (disk-based) stored procedures.</span></span> <span data-ttu-id="849aa-106">Usare le stored procedure compilate in modo nativo per l'accesso alle tabelle ottimizzate per la memoria.</span><span class="sxs-lookup"><span data-stu-id="849aa-106">For optimized access to memory-optimized tables use natively compiled stored procedures.</span></span> <span data-ttu-id="849aa-107">Per altre informazioni, vedere [Natively Compiled Stored Procedures](natively-compiled-stored-procedures.md) (Stored procedure compilate in modo nativo).</span><span class="sxs-lookup"><span data-stu-id="849aa-107">For more information, see [Natively Compiled Stored Procedures](natively-compiled-stored-procedures.md).</span></span>  
  
 <span data-ttu-id="849aa-108">Durante la creazione e la modifica di oggetti database (istruzioni DDL) sarà necessario modificare le istruzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="849aa-108">When creating and modifying database objects (DDL statements), the following statements have been modified:</span></span>  
  
-   <span data-ttu-id="849aa-109">[Opzioni per file e filegroup ALTER DATABASE &#40;&#41;Transact-SQL](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options) (vedere `MEMORY_OPTIMIZED_DATA` )</span><span class="sxs-lookup"><span data-stu-id="849aa-109">[ALTER DATABASE File and Filegroup Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options) (see `MEMORY_OPTIMIZED_DATA`)</span></span>  
  
-   <span data-ttu-id="849aa-110">[Creazione di &#40;di DATABASE SQL Server&#41;Transact-SQL](/sql/t-sql/statements/create-database-sql-server-transact-sql) (vedere `MEMORY_OPTIMIZED_DATA` )</span><span class="sxs-lookup"><span data-stu-id="849aa-110">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) (see `MEMORY_OPTIMIZED_DATA`)</span></span>  
  
-   <span data-ttu-id="849aa-111">[Create procedure &#40;&#41;Transact-SQL](/sql/t-sql/statements/create-procedure-transact-sql) (vedere `NATIVE_COMPILATION` , `SCHEMABINDING` , `EXECUTE AS` e `BEGIN ATOMIC` )</span><span class="sxs-lookup"><span data-stu-id="849aa-111">[CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql) (see `NATIVE_COMPILATION`, `SCHEMABINDING`, `EXECUTE AS`, and `BEGIN ATOMIC`)</span></span>  
  
-   <span data-ttu-id="849aa-112">[Create Table &#40;&#41;Transact-SQL](/sql/t-sql/statements/create-table-transact-sql) (vedere `MEMORY_OPTIMIZED` ,,, `DURABILITY` `BUCKET_COUNT` `INDEX` e `HASH` )</span><span class="sxs-lookup"><span data-stu-id="849aa-112">[CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql) (see `MEMORY_OPTIMIZED`, `DURABILITY`, `BUCKET_COUNT`, `INDEX`, and `HASH`)</span></span>  
  
-   <span data-ttu-id="849aa-113">[Crea tipo &#40;&#41;Transact-SQL](/sql/t-sql/statements/create-type-transact-sql) (vedere `MEMORY_OPTIMIZED` , `BUCKET_COUNT` , `INDEX` e `HASH` )</span><span class="sxs-lookup"><span data-stu-id="849aa-113">[CREATE TYPE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-type-transact-sql) (see `MEMORY_OPTIMIZED`, `BUCKET_COUNT`, `INDEX`, and `HASH`)</span></span>  
  
-   <span data-ttu-id="849aa-114">[Dichiarare @local_variable &#40;&#41;Transact-SQL](/sql/t-sql/language-elements/declare-local-variable-transact-sql) (vedere `NULL`  |  `NOT NULL` )</span><span class="sxs-lookup"><span data-stu-id="849aa-114">[DECLARE @local_variable &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/declare-local-variable-transact-sql) (see `NULL` | `NOT NULL`)</span></span>  
  
 <span data-ttu-id="849aa-115">Le tabelle con ottimizzazione per la memoria supportano vincoli `PRIMARY KEY` e `NOT NULL`.</span><span class="sxs-lookup"><span data-stu-id="849aa-115">Memory-optimized tables support `PRIMARY KEY` and `NOT NULL` constraints.</span></span> <span data-ttu-id="849aa-116">Per informazioni sull'implementazione di vincoli non supportati, vedere [migrazione dei vincoli check e Foreign Key](../../database-engine/migrating-check-and-foreign-key-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="849aa-116">For information on implementing unsupported constraints, see [Migrating Check and Foreign Key Constraints](../../database-engine/migrating-check-and-foreign-key-constraints.md).</span></span>  
  
 <span data-ttu-id="849aa-117">Per informazioni su funzionalità non supportate, vedere [Costrutti Transact-SQL non supportati da OLTP in memoria](transact-sql-constructs-not-supported-by-in-memory-oltp.md).</span><span class="sxs-lookup"><span data-stu-id="849aa-117">For information on unsupported features, see [Transact-SQL Constructs Not Supported by In-Memory OLTP](transact-sql-constructs-not-supported-by-in-memory-oltp.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="849aa-118">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="849aa-118">In This Section</span></span>  
  
-   [<span data-ttu-id="849aa-119">Tipi di dati supportati</span><span class="sxs-lookup"><span data-stu-id="849aa-119">Supported Data Types</span></span>](supported-data-types-for-in-memory-oltp.md)  
  
-   [<span data-ttu-id="849aa-120">Accesso alle tabelle con ottimizzazione per la memoria utilizzando codice Transact-SQL interpretato</span><span class="sxs-lookup"><span data-stu-id="849aa-120">Accessing Memory-Optimized Tables Using Interpreted Transact-SQL</span></span>](accessing-memory-optimized-tables-using-interpreted-transact-sql.md)  
  
-   [<span data-ttu-id="849aa-121">Viste di sistema, stored procedure, tipi di attesa e DMV per OLTP in memoria</span><span class="sxs-lookup"><span data-stu-id="849aa-121">System Views, Stored Procedures, DMVs and Wait Types for In-Memory OLTP</span></span>](../../database-engine/system-views-stored-procedures-dmvs-and-wait-types-for-in-memory-oltp.md)  
  
## <a name="see-also"></a><span data-ttu-id="849aa-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="849aa-122">See Also</span></span>  
 <span data-ttu-id="849aa-123">[OLTP in memoria &#40;ottimizzazione per la memoria&#41;](in-memory-oltp-in-memory-optimization.md) </span><span class="sxs-lookup"><span data-stu-id="849aa-123">[In-Memory OLTP &#40;In-Memory Optimization&#41;](in-memory-oltp-in-memory-optimization.md) </span></span>  
 <span data-ttu-id="849aa-124">[Problemi di migrazione relativi alle stored procedure compilate in modo nativo](migration-issues-for-natively-compiled-stored-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="849aa-124">[Migration Issues for Natively Compiled Stored Procedures](migration-issues-for-natively-compiled-stored-procedures.md) </span></span>  
 <span data-ttu-id="849aa-125">[Funzionalità di SQL Server supportate](unsupported-sql-server-features-for-in-memory-oltp.md) </span><span class="sxs-lookup"><span data-stu-id="849aa-125">[Supported SQL Server Features](unsupported-sql-server-features-for-in-memory-oltp.md) </span></span>  
 [<span data-ttu-id="849aa-126">Stored procedure compilate in modo nativo</span><span class="sxs-lookup"><span data-stu-id="849aa-126">Natively Compiled Stored Procedures</span></span>](natively-compiled-stored-procedures.md)  
  
  
