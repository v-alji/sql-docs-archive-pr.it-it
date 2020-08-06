---
title: Heap (tabelle senza indici cluster) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- heaps
ms.assetid: df5c4dfb-d372-4d0f-859a-a2d2533ee0d7
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2a39bac2e0352f2adc7749e980d5cc91044f8ab2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637314"
---
# <a name="heaps-tables-without-clustered-indexes"></a><span data-ttu-id="d1b4a-102">Heap (tabelle senza indici cluster)</span><span class="sxs-lookup"><span data-stu-id="d1b4a-102">Heaps (Tables without Clustered Indexes)</span></span>
  <span data-ttu-id="d1b4a-103">Un heap è una tabella per cui non è disponibile un indice cluster.</span><span class="sxs-lookup"><span data-stu-id="d1b4a-103">A heap is a table without a clustered index.</span></span> <span data-ttu-id="d1b4a-104">Nelle tabelle archiviate come heap è possibile creare uno o più indici non cluster.</span><span class="sxs-lookup"><span data-stu-id="d1b4a-104">One or more nonclustered indexes can be created on tables stored as a heap.</span></span> <span data-ttu-id="d1b4a-105">I dati vengono archiviati nell'heap senza un ordine specificato.</span><span class="sxs-lookup"><span data-stu-id="d1b4a-105">Data is stored in the heap without specifying an order.</span></span> <span data-ttu-id="d1b4a-106">In genere i dati vengono inizialmente archiviati nell'ordine in cui le righe vengono inserite nella tabella, tuttavia [!INCLUDE[ssDE](../../includes/ssde-md.md)] può spostare i dati nell'heap in modo da archiviare le righe in modo efficiente, pertanto non è possibile prevedere l'ordine dei dati.</span><span class="sxs-lookup"><span data-stu-id="d1b4a-106">Usually data is initially stored in the order in which is the rows are inserted into the table, but the [!INCLUDE[ssDE](../../includes/ssde-md.md)] can move data around in the heap to store the rows efficiently; so the data order cannot be predicted.</span></span> <span data-ttu-id="d1b4a-107">Per garantire l'ordine delle righe restituite da un heap, è necessario utilizzare la clausola `ORDER BY`.</span><span class="sxs-lookup"><span data-stu-id="d1b4a-107">To guarantee the order of rows returned from a heap, you must use the `ORDER BY` clause.</span></span> <span data-ttu-id="d1b4a-108">Per specificare l'ordine di archiviazione delle righe, creare un indice cluster nella tabella, in modo che essa non sia un heap.</span><span class="sxs-lookup"><span data-stu-id="d1b4a-108">To specify the order for storage of the rows, create a clustered index on the table, so that the table is not a heap.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d1b4a-109">Esistono talvolta motivi per i quali è preferibile lasciare una tabella come heap invece di creare un indice cluster, tuttavia l'utilizzo efficiente degli heap richiede competenze avanzate.</span><span class="sxs-lookup"><span data-stu-id="d1b4a-109">There are sometimes good reasons to leave a table as a heap instead of creating a clustered index, but using heaps effectively is an advanced skill.</span></span> <span data-ttu-id="d1b4a-110">Alla maggior parte delle tabelle deve essere associato un indice cluster selezionato con attenzione a meno che non sussista un motivo valido per cui la tabella debba rimanere un heap.</span><span class="sxs-lookup"><span data-stu-id="d1b4a-110">Most tables should have a carefully chosen clustered index unless a good reason exists for leaving the table as a heap.</span></span>  
  
## <a name="when-to-use-a-heap"></a><span data-ttu-id="d1b4a-111">Quando utilizzare un heap</span><span class="sxs-lookup"><span data-stu-id="d1b4a-111">When to Use a Heap</span></span>  
 <span data-ttu-id="d1b4a-112">Se una tabella è un heap e non dispone di indici non cluster, per individuare qualsiasi riga è necessario esaminare l'intera tabella (analisi della tabella).</span><span class="sxs-lookup"><span data-stu-id="d1b4a-112">If a table is a heap and does not have any nonclustered indexes, then the entire table must be examined (a table scan) to find any row.</span></span> <span data-ttu-id="d1b4a-113">Ciò può risultare accettabile in caso di tabelle di piccole dimensioni, ad esempio un elenco di 12 sedi locali di una società.</span><span class="sxs-lookup"><span data-stu-id="d1b4a-113">This can be acceptable when the table is tiny, such as a list of the 12 regional offices of a company.</span></span>  
  
 <span data-ttu-id="d1b4a-114">Quando si archivia una tabella come heap, le singole righe sono identificate mediante il riferimento a un identificatore di riga (RID) costituito dal numero del file, dal numero della pagina di dati e dallo slot nella pagina.</span><span class="sxs-lookup"><span data-stu-id="d1b4a-114">When a table is stored as a heap, individual rows are identified by reference to a row identifier (RID) consisting of the file number, data page number, and slot on the page.</span></span> <span data-ttu-id="d1b4a-115">L'ID della riga è una struttura piccola ed efficiente.</span><span class="sxs-lookup"><span data-stu-id="d1b4a-115">The row id is a small and efficient structure.</span></span> <span data-ttu-id="d1b4a-116">Talvolta gli architetti specializzati utilizzano gli heap quando l'accesso ai dati avviene sempre tramite indici non cluster e il RID risulta più piccolo di una chiave di indice cluster.</span><span class="sxs-lookup"><span data-stu-id="d1b4a-116">Sometimes data architects use heaps when data is always accessed through nonclustered indexes and the RID is smaller than a clustered index key.</span></span>  
  
## <a name="when-not-to-use-a-heap"></a><span data-ttu-id="d1b4a-117">Quando non utilizzare un heap</span><span class="sxs-lookup"><span data-stu-id="d1b4a-117">When Not to Use a Heap</span></span>  
 <span data-ttu-id="d1b4a-118">Non utilizzare un heap quando i dati vengono restituiti di frequente con un ordinamento.</span><span class="sxs-lookup"><span data-stu-id="d1b4a-118">Do not use a heap when the data is frequently returned in a sorted order.</span></span> <span data-ttu-id="d1b4a-119">Un indice cluster nella colonna di ordinamento può evitare l'esecuzione dell'operazione di ordinamento.</span><span class="sxs-lookup"><span data-stu-id="d1b4a-119">A clustered index on the sorting column could avoid the sorting operation.</span></span>  
  
 <span data-ttu-id="d1b4a-120">Non utilizzare un heap quando i dati vengono spesso raggruppati insieme.</span><span class="sxs-lookup"><span data-stu-id="d1b4a-120">Do not use a heap when the data is frequently grouped together.</span></span> <span data-ttu-id="d1b4a-121">I dati devono essere ordinati prima di essere raggruppati, pertanto un indice cluster nella colonna di ordinamento può evitare l'esecuzione dell'operazione di ordinamento.</span><span class="sxs-lookup"><span data-stu-id="d1b4a-121">Data must be sorted before it is grouped, and a clustered index on the sorting column could avoid the sorting operation.</span></span>  
  
 <span data-ttu-id="d1b4a-122">Non utilizzare un heap quando si eseguono spesso query su intervalli di dati della tabella.</span><span class="sxs-lookup"><span data-stu-id="d1b4a-122">Do not use a heap when ranges of data are frequently queried from the table.</span></span>  <span data-ttu-id="d1b4a-123">Un indice cluster nella colonna dell'intervallo evita la necessità di ordinare l'intero heap.</span><span class="sxs-lookup"><span data-stu-id="d1b4a-123">A clustered index on the range column will avoid sorting the entire heap.</span></span>  
  
 <span data-ttu-id="d1b4a-124">Non utilizzare un heap quando non sono presenti indici non cluster e la tabella è di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="d1b4a-124">Do not use a heap when there are no nonclustered indexes and the table is large.</span></span> <span data-ttu-id="d1b4a-125">Per individuare qualsiasi riga in un heap, è necessario leggerne tutte le righe.</span><span class="sxs-lookup"><span data-stu-id="d1b4a-125">In a heap, all rows of the heap must be read to find any row.</span></span>  
  
## <a name="managing-heaps"></a><span data-ttu-id="d1b4a-126">Gestione di heap</span><span class="sxs-lookup"><span data-stu-id="d1b4a-126">Managing Heaps</span></span>  
 <span data-ttu-id="d1b4a-127">Per creare un heap, creare una tabella senza un indice cluster.</span><span class="sxs-lookup"><span data-stu-id="d1b4a-127">To create a heap, create a table without a clustered index.</span></span> <span data-ttu-id="d1b4a-128">Se la tabella dispone già di un indice cluster, rimuoverlo per restituire la tabella a un heap.</span><span class="sxs-lookup"><span data-stu-id="d1b4a-128">If a table already has a clustered index, drop the clustered index to return the table to a heap.</span></span>  
  
 <span data-ttu-id="d1b4a-129">Per rimuovere un heap, creare un indice cluster nell'heap.</span><span class="sxs-lookup"><span data-stu-id="d1b4a-129">To remove a heap, create a clustered index on the heap.</span></span>  
  
 <span data-ttu-id="d1b4a-130">Per ricompilare un heap in modo da recuperare spazio sprecato, creare un indice cluster nell'heap, quindi rimuovere quell'indice.</span><span class="sxs-lookup"><span data-stu-id="d1b4a-130">To rebuild a heap to reclaim wasted space, create a clustered index on the heap, and then drop that clustered index.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="d1b4a-131">Per la creazione o la rimozione di indici cluster è richiesta la riscrittura dell'intera tabella.</span><span class="sxs-lookup"><span data-stu-id="d1b4a-131">Creating or dropping clustered indexes requires rewriting the entire table.</span></span> <span data-ttu-id="d1b4a-132">Se la tabella dispone di indici non cluster, è necessario ricrearli tutti ogni volta che l'indice cluster viene modificato.</span><span class="sxs-lookup"><span data-stu-id="d1b4a-132">If the table has nonclustered indexes, all the nonclustered indexes must all be recreated whenever the clustered index is changed.</span></span> <span data-ttu-id="d1b4a-133">Pertanto, il passaggio da un heap a una struttura di indice cluster o viceversa può richiedere molto tempo e spazio su disco per riordinare i dati in tempdb.</span><span class="sxs-lookup"><span data-stu-id="d1b4a-133">Therefore, changing from a heap to a clustered index structure or back can take a lot of time and require disk space for reordering data in tempdb.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="d1b4a-134">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="d1b4a-134">Related Content</span></span>  
 [<span data-ttu-id="d1b4a-135">CREATE INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d1b4a-135">CREATE INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-index-transact-sql)  
  
 [<span data-ttu-id="d1b4a-136">DROP INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d1b4a-136">DROP INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-index-transact-sql)  
  
 [<span data-ttu-id="d1b4a-137">Descrizione di indici cluster e non cluster.</span><span class="sxs-lookup"><span data-stu-id="d1b4a-137">Clustered and Nonclustered Indexes Described</span></span>](clustered-and-nonclustered-indexes-described.md)  
  
  
