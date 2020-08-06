---
title: Tabelle con ottimizzazione per la memoria | Microsoft Docs
ms.custom: ''
ms.date: 10/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 14dddf81-b502-49dc-a6b6-d18b1ae32d2b
author: rothja
ms.author: jroth
ms.openlocfilehash: 73430505e55230daf31c492d882eadeb6d35d29f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724679"
---
# <a name="memory-optimized-tables"></a><span data-ttu-id="048bc-102">Tabelle con ottimizzazione per la memoria</span><span class="sxs-lookup"><span data-stu-id="048bc-102">Memory-Optimized Tables</span></span>
  <span data-ttu-id="048bc-103">Con la funzionalità OLTP in memoria di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] è possibile migliorare le prestazioni delle applicazioni OLTP tramite l'accesso ai dati efficiente e ottimizzato per la memoria, la compilazione nativa della logica di business e gli algoritmi senza blocchi e latch.</span><span class="sxs-lookup"><span data-stu-id="048bc-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] In-Memory OLTP helps improve performance of OLTP applications through efficient, memory-optimized data access, native compilation of business logic, and lock- and latch free algorithms.</span></span> <span data-ttu-id="048bc-104">La funzionalità include tabelle ottimizzate per la memoria e tipi di tabella, nonché la compilazione nativa delle stored procedure [!INCLUDE[tsql](../../includes/tsql-md.md)] per l'accesso efficiente a queste tabelle.</span><span class="sxs-lookup"><span data-stu-id="048bc-104">The In-Memory OLTP feature includes memory-optimized tables and table types, as well as native compilation of [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedures for efficient access to these tables.</span></span>  
  
 <span data-ttu-id="048bc-105">Per ulteriori informazioni sulle tabelle ottimizzate per la memoria, vedere:</span><span class="sxs-lookup"><span data-stu-id="048bc-105">For more information about memory-optimized tables, see:</span></span>  
  
-   [<span data-ttu-id="048bc-106">Introduzione alle tabelle con ottimizzazione per la memoria</span><span class="sxs-lookup"><span data-stu-id="048bc-106">Introduction to Memory-Optimized Tables</span></span>](memory-optimized-tables.md)  
  
     <span data-ttu-id="048bc-107">Descrive le tabelle ottimizzate per la memoria e fornisce informazioni sulla durabilità dei dati, sull'accesso ai dati nelle tabelle ottimizzate per la memoria e sulle prestazioni e la scalabilità.</span><span class="sxs-lookup"><span data-stu-id="048bc-107">Details what memory-optimized tables are and provides information about data durability, accessing data in memory-optimized tables, and performance and scalability.</span></span>  
  
-   [<span data-ttu-id="048bc-108">Compilazione nativa di tabelle e stored procedure</span><span class="sxs-lookup"><span data-stu-id="048bc-108">Native Compilation of Tables and Stored Procedures</span></span>](../in-memory-oltp/natively-compiled-stored-procedures.md)  
  
     <span data-ttu-id="048bc-109">Descrive come vengono compilate in DLL le tabelle ottimizzate per la memoria e le stored procedure compilate in modo nativo e fornisce considerazioni correlate alla sicurezza.</span><span class="sxs-lookup"><span data-stu-id="048bc-109">Details how memory-optimized tables and natively compiled stored procedures are compiled into DLLs, and provides related security considerations.</span></span>  
  
-   [<span data-ttu-id="048bc-110">Modifica di tabelle con ottimizzazione per la memoria</span><span class="sxs-lookup"><span data-stu-id="048bc-110">Altering Memory-Optimized Tables</span></span>](altering-memory-optimized-tables.md)  
  
     <span data-ttu-id="048bc-111">Linee guida per l'aggiornamento delle tabelle ottimizzate per la memoria, compresa la modifica di colonne di tabella, indici e bucket_count.</span><span class="sxs-lookup"><span data-stu-id="048bc-111">Guidelines for updating memory-optimized tables (including changing table columns, indexes, and bucket_count).</span></span>  
  
-   [<span data-ttu-id="048bc-112">Informazioni sulle transazioni in tabelle con ottimizzazione per la memoria</span><span class="sxs-lookup"><span data-stu-id="048bc-112">Understanding Transactions on Memory-Optimized Tables</span></span>](../../database-engine/understanding-transactions-on-memory-optimized-tables.md)  
  
     <span data-ttu-id="048bc-113">Questa sezione fornisce diversi argomenti relativi all'esecuzione di transazioni in tabelle ottimizzate per la memoria compresi i livelli di isolamento delle transazioni e le transazioni tra contenitori.</span><span class="sxs-lookup"><span data-stu-id="048bc-113">This section provides several topics related to performing transactions on memory-optimized tables including transaction isolation levels, and cross-container transactions.</span></span>  
  
-   [<span data-ttu-id="048bc-114">Modello di applicazione per il partizionamento di tabelle con ottimizzazione per la memoria</span><span class="sxs-lookup"><span data-stu-id="048bc-114">Application Pattern for Partitioning Memory-Optimized Tables</span></span>](application-pattern-for-partitioning-memory-optimized-tables.md)  
  
     <span data-ttu-id="048bc-115">Esempio di codice dettagliato che mostra come emulare le tabelle partizionate quando vengono usate le tabelle ottimizzate per la memoria.</span><span class="sxs-lookup"><span data-stu-id="048bc-115">Detailed code sample that shows how to emulate partitioned tables when using memory-optimized tables.</span></span>  
  
-   [<span data-ttu-id="048bc-116">Statistiche per tabelle con ottimizzazione per la memoria</span><span class="sxs-lookup"><span data-stu-id="048bc-116">Statistics for Memory-Optimized Tables</span></span>](statistics-for-memory-optimized-tables.md)  
  
     <span data-ttu-id="048bc-117">Descrive come vengono compilate le statistiche per le tabelle ottimizzate per la memoria e come gestire e aggiornare manualmente le statistiche per le tabelle ottimizzate per la memoria.</span><span class="sxs-lookup"><span data-stu-id="048bc-117">Details how statistics are compiled for memory-optimized tables and how to maintain and manually update statistics for memory-optimized tables.</span></span>  
  
-   [<span data-ttu-id="048bc-118">Tabelle codici e regole di confronto</span><span class="sxs-lookup"><span data-stu-id="048bc-118">Collations and Code Pages</span></span>](../../database-engine/collations-and-code-pages.md)  
  
     <span data-ttu-id="048bc-119">Descrive le restrizioni sulle tabelle codici e le regole di confronto supportate per le tabelle ottimizzate per la memoria.</span><span class="sxs-lookup"><span data-stu-id="048bc-119">Details the restrictions on supported collations and code pages for memory-optimized tables.</span></span>  
  
-   [<span data-ttu-id="048bc-120">Dimensioni di tabelle e righe per le tabelle con ottimizzazione per la memoria</span><span class="sxs-lookup"><span data-stu-id="048bc-120">Table and Row Size in Memory-Optimized Tables</span></span>](table-and-row-size-in-memory-optimized-tables.md)  
  
     <span data-ttu-id="048bc-121">Descrive il limite di 8.060 byte per le righe delle tabelle ottimizzate per la memoria e fornisce un esempio per calcolare le dimensioni di righe e tabelle.</span><span class="sxs-lookup"><span data-stu-id="048bc-121">Details the 8060 byte limit on memory-optimized table rows, and provides an example for calculating table and row sizes.</span></span>  
  
-   [<span data-ttu-id="048bc-122">Guida all'elaborazione delle query per le tabelle con ottimizzazione per la memoria</span><span class="sxs-lookup"><span data-stu-id="048bc-122">A Guide to Query Processing for Memory-Optimized Tables</span></span>](a-guide-to-query-processing-for-memory-optimized-tables.md)  
  
     <span data-ttu-id="048bc-123">Fornisce una panoramica sull'elaborazione delle query per le tabelle ottimizzate per la memoria e le stored procedure compilate in modo nativo.</span><span class="sxs-lookup"><span data-stu-id="048bc-123">Provides an overview of query processing for both memory-optimized tables, and natively compiled stored procedures.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="048bc-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="048bc-124">See Also</span></span>  
 [<span data-ttu-id="048bc-125">OLTP in memoria &#40;ottimizzazione per la memoria&#41;</span><span class="sxs-lookup"><span data-stu-id="048bc-125">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](in-memory-oltp-in-memory-optimization.md)  
  
  
