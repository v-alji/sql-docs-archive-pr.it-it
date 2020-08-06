---
title: Migrazione a OLTP in memoria | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 405cdac5-a0d4-47a4-9180-82876b773b82
author: rothja
ms.author: jroth
ms.openlocfilehash: ed764ce52d41d76667213b846cec51b26f634a27
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725772"
---
# <a name="migrating-to-in-memory-oltp"></a><span data-ttu-id="03651-102">Migrazione a OLTP in memoria</span><span class="sxs-lookup"><span data-stu-id="03651-102">Migrating to In-Memory OLTP</span></span>
  <span data-ttu-id="03651-103">In questa sezione viene illustrato come eseguire la migrazione di oggetti di database per utilizzare OLTP in memoria.</span><span class="sxs-lookup"><span data-stu-id="03651-103">This section discusses how to migrate database objects to use In-Memory OLTP.</span></span>  
  
-   [<span data-ttu-id="03651-104">Determinare se una tabella o una stored procedure deve essere trasferita a OLTP in memoria</span><span class="sxs-lookup"><span data-stu-id="03651-104">Determining if a Table or Stored Procedure Should Be Ported to In-Memory OLTP</span></span>](determining-if-a-table-or-stored-procedure-should-be-ported-to-in-memory-oltp.md)  
  
-   [<span data-ttu-id="03651-105">Ottimizzazione guidata per la memoria</span><span class="sxs-lookup"><span data-stu-id="03651-105">Memory Optimization Advisor</span></span>](memory-optimization-advisor.md)  
  
-   [<span data-ttu-id="03651-106">Assistente compilazione nativa</span><span class="sxs-lookup"><span data-stu-id="03651-106">Native Compilation Advisor</span></span>](native-compilation-advisor.md)  
  
-   [<span data-ttu-id="03651-107">Costrutti Transact-SQL non supportati da OLTP in memoria</span><span class="sxs-lookup"><span data-stu-id="03651-107">Transact-SQL Constructs Not Supported by In-Memory OLTP</span></span>](transact-sql-constructs-not-supported-by-in-memory-oltp.md)  
  
-   [<span data-ttu-id="03651-108">Implementazione di colonne LOB in una tabella con ottimizzazione per la memoria</span><span class="sxs-lookup"><span data-stu-id="03651-108">Implementing LOB Columns in a Memory-Optimized Table</span></span>](../../database-engine/implementing-lob-columns-in-a-memory-optimized-table.md)  
  
-   [<span data-ttu-id="03651-109">Implementazione di SQL_VARIANT in una tabella con ottimizzazione per la memoria</span><span class="sxs-lookup"><span data-stu-id="03651-109">Implementing SQL_VARIANT in a Memory-Optimized Table</span></span>](implementing-sql-variant-in-a-memory-optimized-table.md)  
  
-   [<span data-ttu-id="03651-110">Problemi di migrazione relativi alle stored procedure compilate in modo nativo</span><span class="sxs-lookup"><span data-stu-id="03651-110">Migration Issues for Natively Compiled Stored Procedures</span></span>](migration-issues-for-natively-compiled-stored-procedures.md)  
  
-   [<span data-ttu-id="03651-111">Migrazione di colonne calcolate</span><span class="sxs-lookup"><span data-stu-id="03651-111">Migrating Computed Columns</span></span>](migrating-computed-columns.md)  
  
-   [<span data-ttu-id="03651-112">Migrazione di trigger</span><span class="sxs-lookup"><span data-stu-id="03651-112">Migrating Triggers</span></span>](migrating-triggers.md)  
  
-   [<span data-ttu-id="03651-113">Query tra database</span><span class="sxs-lookup"><span data-stu-id="03651-113">Cross-Database Queries</span></span>](cross-database-queries.md)  
  
-   [<span data-ttu-id="03651-114">Migrazione di vincoli CHECK e di chiave esterna</span><span class="sxs-lookup"><span data-stu-id="03651-114">Migrating Check and Foreign Key Constraints</span></span>](../../database-engine/migrating-check-and-foreign-key-constraints.md)  
  
-   [<span data-ttu-id="03651-115">Implementazione di IDENTITY in una tabella con ottimizzazione per la memoria</span><span class="sxs-lookup"><span data-stu-id="03651-115">Implementing IDENTITY in a Memory-Optimized Table</span></span>](implementing-identity-in-a-memory-optimized-table.md)  
  
 <span data-ttu-id="03651-116">Per informazioni sulle metodologie di migrazione, vedere [In-Memory OLTP - Common Workload Patterns and Migration Considerations](https://msdn.microsoft.com/library/dn673538.aspx) (OLTP in memoria: considerazioni sulla migrazione e sui modelli di carico di lavoro comuni).</span><span class="sxs-lookup"><span data-stu-id="03651-116">For information about migration methodologies, see [In-Memory OLTP - Common Workload Patterns and Migration Considerations](https://msdn.microsoft.com/library/dn673538.aspx).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03651-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="03651-117">See Also</span></span>  
 <span data-ttu-id="03651-118">[OLTP in memoria &#40;ottimizzazione per la memoria&#41;](in-memory-oltp-in-memory-optimization.md) </span><span class="sxs-lookup"><span data-stu-id="03651-118">[In-Memory OLTP &#40;In-Memory Optimization&#41;](in-memory-oltp-in-memory-optimization.md) </span></span>  
 [<span data-ttu-id="03651-119">Stimare i requisiti di memoria delle tabelle con ottimizzazione per la memoria</span><span class="sxs-lookup"><span data-stu-id="03651-119">Estimate Memory Requirements for Memory-Optimized Tables</span></span>](memory-optimized-tables.md)  
  
  
