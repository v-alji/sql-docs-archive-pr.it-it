---
title: Indici hash | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: f4bdc9c1-7922-4fac-8183-d11ec58fec4e
author: stevestein
ms.author: sstein
ms.openlocfilehash: 05b8d1e3a5d92078cc2ec3fe7cd5b6d3fb5b47c9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724908"
---
# <a name="hash-indexes"></a><span data-ttu-id="219f6-102">Indici hash</span><span class="sxs-lookup"><span data-stu-id="219f6-102">Hash Indexes</span></span>
  <span data-ttu-id="219f6-103">Gli indici vengono utilizzati come punti di ingresso per le tabelle ottimizzate per la memoria.</span><span class="sxs-lookup"><span data-stu-id="219f6-103">Indexes are used as entry points for memory-optimized tables.</span></span> <span data-ttu-id="219f6-104">Per la lettura delle righe da una tabella è necessario un indice di individuare i dati in memoria.</span><span class="sxs-lookup"><span data-stu-id="219f6-104">Reading rows from a table requires an index to locate the data in memory.</span></span>  
  
 <span data-ttu-id="219f6-105">Un indice hash è costituito da una raccolta di bucket organizzati in una matrice.</span><span class="sxs-lookup"><span data-stu-id="219f6-105">A hash index consists of a collection of buckets organized in an array.</span></span> <span data-ttu-id="219f6-106">Una funzione hash esegue il mapping delle chiavi di indice ai bucket dell'indice hash.</span><span class="sxs-lookup"><span data-stu-id="219f6-106">A hash function maps index keys to corresponding buckets in the hash index.</span></span> <span data-ttu-id="219f6-107">Nella figura seguente sono illustrate tre chiavi di indice di cui viene eseguito il mapping a tre bucket diversi nell'indice hash.</span><span class="sxs-lookup"><span data-stu-id="219f6-107">The following figure shows three index keys that are mapped to three different buckets in the hash index.</span></span> <span data-ttu-id="219f6-108">A scopo illustrativo il nome della funzione hash è f(x).</span><span class="sxs-lookup"><span data-stu-id="219f6-108">For illustration purposes the hash function name is f(x).</span></span>  
  
 <span data-ttu-id="219f6-109">![Chiavi di indice di cui è stato eseguito il mapping a bucket diversi.](../../2014/database-engine/media/hekaton-tables-2.gif "Chiavi di indice di cui è stato eseguito il mapping a bucket diversi.")</span><span class="sxs-lookup"><span data-stu-id="219f6-109">![Index keys mapped to different buckets.](../../2014/database-engine/media/hekaton-tables-2.gif "Index keys mapped to different buckets.")</span></span>  
  
 <span data-ttu-id="219f6-110">La funzione di hashing utilizzata per gli indici hash presenta le caratteristiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="219f6-110">The hashing function used for hash indexes has the following characteristics:</span></span>  
  
-   <span data-ttu-id="219f6-111">In [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] è disponibile una funzione hash utilizzata per tutti gli indici hash.</span><span class="sxs-lookup"><span data-stu-id="219f6-111">[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] has one hash function that is used for all hash indexes.</span></span>  
  
-   <span data-ttu-id="219f6-112">La funzione hash è deterministica.</span><span class="sxs-lookup"><span data-stu-id="219f6-112">The hash function is deterministic.</span></span> <span data-ttu-id="219f6-113">Per la stessa chiave di indice viene sempre eseguito il mapping allo stesso bucket nell'indice hash.</span><span class="sxs-lookup"><span data-stu-id="219f6-113">The same index key is always mapped to the same bucket in the hash index.</span></span>  
  
-   <span data-ttu-id="219f6-114">È possibile che venga eseguito il mapping di più chiavi di indice allo stesso bucket di hash.</span><span class="sxs-lookup"><span data-stu-id="219f6-114">Multiple index keys may be mapped to the same hash bucket.</span></span>  
  
-   <span data-ttu-id="219f6-115">La funzione hash viene bilanciata, pertanto la distribuzione dei valori di chiave di indice in bucket di hash segue in genere una distribuzione di probabilità di Poisson.</span><span class="sxs-lookup"><span data-stu-id="219f6-115">The hash function is balanced, meaning that the distribution of index key values over hash buckets typically follows a Poisson distribution.</span></span>  
  
     <span data-ttu-id="219f6-116">La distribuzione di probabilità di Poisson non è uniforme.</span><span class="sxs-lookup"><span data-stu-id="219f6-116">Poisson distribution is not an even distribution.</span></span> <span data-ttu-id="219f6-117">I valori delle chiavi di indice non vengono distribuiti in modo uniforme nei bucket di hash.</span><span class="sxs-lookup"><span data-stu-id="219f6-117">Index key values are not evenly distributed in the hash buckets.</span></span> <span data-ttu-id="219f6-118">Ad esempio, una distribuzione di Poisson di *n* chiavi di indice DISTINCT su *n* bucket di hash comporta approssimativamente un terzo bucket vuoti, un terzo dei bucket contenenti una chiave di indice e l'altro terzo contenente due chiavi di indice.</span><span class="sxs-lookup"><span data-stu-id="219f6-118">For example, a Poisson distribution of *n* distinct index keys over *n* hash buckets results in approximately one third empty buckets, one third of the buckets containing one index key, and the other third containing two index keys.</span></span> <span data-ttu-id="219f6-119">Un piccolo numero di bucket conterrà più di due chiavi.</span><span class="sxs-lookup"><span data-stu-id="219f6-119">A small number of buckets will contain more than two keys.</span></span>  
  
 <span data-ttu-id="219f6-120">Se viene eseguito il mapping di due chiavi dell'indice allo stesso bucket di hash, si verifica una collisione hash.</span><span class="sxs-lookup"><span data-stu-id="219f6-120">If two index keys are mapped to the same hash bucket, there is a hash collision.</span></span> <span data-ttu-id="219f6-121">Un numero elevato di collisioni hash può influire negativamente sulle prestazioni nelle operazioni di lettura.</span><span class="sxs-lookup"><span data-stu-id="219f6-121">A large number of hash collisions can have a performance impact on read operations.</span></span>  
  
 <span data-ttu-id="219f6-122">La struttura dell'indice hash in memoria è costituita da una matrice di puntatori alla memoria.</span><span class="sxs-lookup"><span data-stu-id="219f6-122">The in-memory hash index structure consists of an array of memory pointers.</span></span> <span data-ttu-id="219f6-123">Per ogni bucket viene eseguito il mapping a un offset nella matrice.</span><span class="sxs-lookup"><span data-stu-id="219f6-123">Each bucket maps to an offset in this array.</span></span> <span data-ttu-id="219f6-124">Ogni bucket nella matrice punta alla prima riga in tale bucket di hash.</span><span class="sxs-lookup"><span data-stu-id="219f6-124">Each bucket in the array points to the first row in that hash bucket.</span></span> <span data-ttu-id="219f6-125">Ogni riga del bucket punta alla riga successiva, generando in tal modo una catena di righe per ogni bucket di hash, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="219f6-125">Each row in the bucket points to the next row, thus resulting in a chain of rows for each hash bucket, as illustrated in the following figure.</span></span>  
  
 <span data-ttu-id="219f6-126">![Struttura dell'indice hash in memoria.](../../2014/database-engine/media/hekaton-tables-3.gif "Struttura dell'indice hash in memoria.")</span><span class="sxs-lookup"><span data-stu-id="219f6-126">![The in-memory hash index structure.](../../2014/database-engine/media/hekaton-tables-3.gif "The in-memory hash index structure.")</span></span>  
  
 <span data-ttu-id="219f6-127">Nella figura sono illustrati tre bucket con righe.</span><span class="sxs-lookup"><span data-stu-id="219f6-127">The figure has three buckets with rows.</span></span> <span data-ttu-id="219f6-128">Il secondo bucket dall'alto contiene le tre righe rosse.</span><span class="sxs-lookup"><span data-stu-id="219f6-128">The second bucket from the top contains the three red rows.</span></span> <span data-ttu-id="219f6-129">Il quarto bucket contiene una singola riga blu.</span><span class="sxs-lookup"><span data-stu-id="219f6-129">The fourth bucket contains the single blue row.</span></span> <span data-ttu-id="219f6-130">Il bucket inferiore contiene due linee verdi.</span><span class="sxs-lookup"><span data-stu-id="219f6-130">The bottom bucket contains the two green rows.</span></span> <span data-ttu-id="219f6-131">Queste possono essere diverse versioni della stessa riga.</span><span class="sxs-lookup"><span data-stu-id="219f6-131">These could be different versions of the same row.</span></span>  
  
 <span data-ttu-id="219f6-132">Per altre informazioni sugli indici per le tabelle ottimizzate per la memoria, vedere [linee guida per l'uso di indici nelle tabelle ottimizzate per la memoria](../relational-databases/in-memory-oltp/memory-optimized-tables.md).</span><span class="sxs-lookup"><span data-stu-id="219f6-132">For more information about indexes for memory-optimized tables, see [Guidelines for Using Indexes on Memory-Optimized Tables](../relational-databases/in-memory-oltp/memory-optimized-tables.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="219f6-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="219f6-133">See Also</span></span>  
 [<span data-ttu-id="219f6-134">Indici in tabelle con ottimizzazione per la memoria</span><span class="sxs-lookup"><span data-stu-id="219f6-134">Indexes on Memory-Optimized Tables</span></span>](../../2014/database-engine/indexes-on-memory-optimized-tables.md)  
  
  
