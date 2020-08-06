---
title: Creazione e gestione dell'archiviazione per gli oggetti con ottimizzazione per la memoria | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 622aabe6-95c7-42cc-8768-ac2e679c5089
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 118e5e582a284023dd8e5cc71629d635e79fb989
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627271"
---
# <a name="creating-and-managing-storage-for-memory-optimized-objects"></a><span data-ttu-id="a3d02-102">Creazione e gestione dell'archiviazione per gli oggetti con ottimizzazione per la memoria</span><span class="sxs-lookup"><span data-stu-id="a3d02-102">Creating and Managing Storage for Memory-Optimized Objects</span></span>
  <span data-ttu-id="a3d02-103">Il motore di [!INCLUDE[hek_2](../../includes/hek-2-md.md)] è integrato in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], in modo da consentire la presenza sia di tabelle ottimizzate per la memoria che di tabelle tradizionali basate su disco nello stesso database.</span><span class="sxs-lookup"><span data-stu-id="a3d02-103">The [!INCLUDE[hek_2](../../includes/hek-2-md.md)] engine is integrated into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], which lets you have both memory-optimized tables and (traditional) disk-based tables in the same database.</span></span> <span data-ttu-id="a3d02-104">Tuttavia, la struttura di archiviazione per le tabelle ottimizzate per la memoria è diversa rispetto alle tabelle basate su disco.</span><span class="sxs-lookup"><span data-stu-id="a3d02-104">However, the storage structure for memory-optimized tables is different from disk-based tables.</span></span>  
  
 <span data-ttu-id="a3d02-105">L'archiviazione per una tabella basata su disco presenta gli attributi chiave seguenti:</span><span class="sxs-lookup"><span data-stu-id="a3d02-105">Storage for disk-based table has following key attributes:</span></span>  
  
-   <span data-ttu-id="a3d02-106">È stato eseguito il mapping a un filegroup e il filegroup contiene uno o più file.</span><span class="sxs-lookup"><span data-stu-id="a3d02-106">Mapped to a filegroup and the filegroup contains one or more files.</span></span>  
  
-   <span data-ttu-id="a3d02-107">Ogni file è suddiviso in extent di 8 pagine e ogni pagina è 8 KB di dimensioni.</span><span class="sxs-lookup"><span data-stu-id="a3d02-107">Each file is divided into extents of 8 pages and each page is of size 8K bytes.</span></span>  
  
-   <span data-ttu-id="a3d02-108">Un extent può essere condiviso tra più tabelle, ma esiste un mapping 1 a 1 tra una pagina allocata e la tabella o l'indice.</span><span class="sxs-lookup"><span data-stu-id="a3d02-108">An extent can be shared across multiple tables, but a there is 1-to-1 mapping between an allocated page and the table or index.</span></span> <span data-ttu-id="a3d02-109">In altri termini, una pagina non può includere righe di due o più tabelle o indici.</span><span class="sxs-lookup"><span data-stu-id="a3d02-109">In other words, a page can't have rows from two or more tables or index.</span></span>  
  
-   <span data-ttu-id="a3d02-110">I dati vengono spostati in memoria (pool di buffer) in base alle esigenze e le pagine appena create o modificate vengono scritte in modo asincrono sul disco generando operazioni IO principalmente casuali.</span><span class="sxs-lookup"><span data-stu-id="a3d02-110">The data is moved into memory (the buffer pool) as needed and the modified or newly created pages are asynchronously written to the disk generating mostly random IO.</span></span>  
  
 <span data-ttu-id="a3d02-111">L'archiviazione per le tabelle ottimizzate per la memoria presenta gli attributi chiave seguenti:</span><span class="sxs-lookup"><span data-stu-id="a3d02-111">Storage for memory-optimized tables has following key attributes:</span></span>  
  
-   <span data-ttu-id="a3d02-112">Tutte le tabelle ottimizzate per la memoria sono mappate a un filegroup ottimizzato per la memoria.</span><span class="sxs-lookup"><span data-stu-id="a3d02-112">All memory-optimized tables are mapped to a memory-optimized filegroup.</span></span> <span data-ttu-id="a3d02-113">Questo filegroup viene compilato utilizzando il filegroup FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="a3d02-113">This filegroup is built using the filestream filegroup.</span></span>  
  
-   <span data-ttu-id="a3d02-114">Non sono presenti pagine e i dati vengono salvati in modo permanente come riga.</span><span class="sxs-lookup"><span data-stu-id="a3d02-114">There are no pages and the data is persisted as a row.</span></span>  
  
-   <span data-ttu-id="a3d02-115">Tutte le modifiche apportate alle tabelle ottimizzate per la memoria vengono archiviate aggiungendole ai file attivi.</span><span class="sxs-lookup"><span data-stu-id="a3d02-115">All changes to memory-optimized tables are stored by appending to active files.</span></span> <span data-ttu-id="a3d02-116">La lettura e la scrittura nei file è sequenziale.</span><span class="sxs-lookup"><span data-stu-id="a3d02-116">Both reading and writing to files is sequential.</span></span>  
  
-   <span data-ttu-id="a3d02-117">Un aggiornamento viene implementato come un'eliminazione seguita da un inserimento.</span><span class="sxs-lookup"><span data-stu-id="a3d02-117">An update is implemented as a delete followed by an insert.</span></span> <span data-ttu-id="a3d02-118">Le righe eliminate non vengono rimosse immediatamente dalla risorsa di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="a3d02-118">The deleted rows are not immediately removed from the storage.</span></span> <span data-ttu-id="a3d02-119">Le righe eliminate vengono rimosse da un processo in background, denominato MERGE, in base ai criteri descritti in [Durabilità per tabelle con ottimizzazione per la memoria](memory-optimized-tables.md).</span><span class="sxs-lookup"><span data-stu-id="a3d02-119">The deleted rows are removed by a background process, called MERGE, based on a policy as described in [Durability for Memory-Optimized Tables](memory-optimized-tables.md).</span></span>  
  
-   <span data-ttu-id="a3d02-120">A differenza delle tabelle basate su disco, lo spazio di archiviazione per le tabelle ottimizzate per la memoria non è compresso.</span><span class="sxs-lookup"><span data-stu-id="a3d02-120">Unlike disk-based tables, storage for memory-optimized tables is not compressed.</span></span> <span data-ttu-id="a3d02-121">Quando si esegue la migrazione di una tabella basata su disco (ROW o PAGE) compressa a una tabella ottimizzata per la memoria, è necessario tenere conto della variazione di dimensioni.</span><span class="sxs-lookup"><span data-stu-id="a3d02-121">When migrating a compressed (ROW or PAGE) disk-based table to memory-optimized table, you will need to account for the change in size.</span></span>  
  
-   <span data-ttu-id="a3d02-122">Una tabella ottimizzata per la memoria può essere durevole o non durevole.</span><span class="sxs-lookup"><span data-stu-id="a3d02-122">A memory-optimized table can be durable or can be non-durable.</span></span> <span data-ttu-id="a3d02-123">È sufficiente configurare l'archiviazione per le tabelle con ottimizzazione per la memoria durevoli.</span><span class="sxs-lookup"><span data-stu-id="a3d02-123">You only need to configure storage for durable memory-optimize tables.</span></span>  
  
 <span data-ttu-id="a3d02-124">In questa sezione vengono descritte le coppie di file di checkpoint e altri aspetti della modalità di archiviazione dei dati nelle tabelle ottimizzate per la memoria.</span><span class="sxs-lookup"><span data-stu-id="a3d02-124">This section describes checkpoint file pairs and other aspects of how data in memory-optimized tables is stored.</span></span>  
  
 <span data-ttu-id="a3d02-125">Contenuto della sezione:</span><span class="sxs-lookup"><span data-stu-id="a3d02-125">Topics in this section:</span></span>  
  
-   [<span data-ttu-id="a3d02-126">Configurazione dell'archiviazione per le tabelle con ottimizzazione per la memoria</span><span class="sxs-lookup"><span data-stu-id="a3d02-126">Configuring Storage for Memory-Optimized Tables</span></span>](configuring-storage-for-memory-optimized-tables.md)  
  
-   [<span data-ttu-id="a3d02-127">Filegroup con ottimizzazione per la memoria</span><span class="sxs-lookup"><span data-stu-id="a3d02-127">The Memory Optimized Filegroup</span></span>](the-memory-optimized-filegroup.md)  
  
-   [<span data-ttu-id="a3d02-128">Durabilità per tabelle con ottimizzazione per la memoria</span><span class="sxs-lookup"><span data-stu-id="a3d02-128">Durability for Memory-Optimized Tables</span></span>](memory-optimized-tables.md)  
  
-   [<span data-ttu-id="a3d02-129">Operazione su checkpoint per le tabelle con ottimizzazione per la memoria</span><span class="sxs-lookup"><span data-stu-id="a3d02-129">Checkpoint Operation for Memory-Optimized Tables</span></span>](checkpoint-operation-for-memory-optimized-tables.md)  
  
-   [<span data-ttu-id="a3d02-130">Definizione di durabilità per gli oggetti con ottimizzazione per la memoria</span><span class="sxs-lookup"><span data-stu-id="a3d02-130">Defining Durability for Memory-Optimized Objects</span></span>](defining-durability-for-memory-optimized-objects.md)  
  
-   [<span data-ttu-id="a3d02-131">Confronto dell'archiviazione delle tabelle basate su disco con quella delle tabelle con ottimizzazione per la memoria</span><span class="sxs-lookup"><span data-stu-id="a3d02-131">Comparing Disk-Based Table Storage to Memory-Optimized Table Storage</span></span>](comparing-disk-based-table-storage-to-memory-optimized-table-storage.md)  
  
-   [<span data-ttu-id="a3d02-132">Monitoraggio e risoluzione di problemi relativi all'unione di coppie di file di dati e differenziali</span><span class="sxs-lookup"><span data-stu-id="a3d02-132">Monitoring and Troubleshooting Merge for Data and Delta File Pairs</span></span>](../../database-engine/monitoring-and-troubleshooting-merge-for-data-and-delta-file-pairs.md)  
  
## <a name="see-also"></a><span data-ttu-id="a3d02-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a3d02-133">See Also</span></span>  
 [<span data-ttu-id="a3d02-134">OLTP in memoria &#40;ottimizzazione per la memoria&#41;</span><span class="sxs-lookup"><span data-stu-id="a3d02-134">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](in-memory-oltp-in-memory-optimization.md)  
  
  
