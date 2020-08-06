---
title: Stimare le dimensioni di un tabella | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- pages [SQL Server], space
- space [SQL Server], tables
- row size [SQL Server]
- size [SQL Server], tables
- column size [SQL Server]
- predicting table size [SQL Server]
- table size [SQL Server]
- estimating table size
- clustered indexes, table size
- disk space [SQL Server], tables
- space allocation [SQL Server], table size
- designing databases [SQL Server], estimating size
- reserved free rows per page [SQL Server]
- calculating table size
ms.assetid: 15c17c92-616f-402e-894b-907a296efe5f
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4a16d439d3b2bc59479866b7bb36295ec4fc8950
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721479"
---
# <a name="estimate-the-size-of-a-table"></a><span data-ttu-id="aa33e-102">Stima delle dimensioni di una tabella</span><span class="sxs-lookup"><span data-stu-id="aa33e-102">Estimate the Size of a Table</span></span>
  <span data-ttu-id="aa33e-103">Per stimare la quantità di spazio necessario per archiviare dati in una tabella, è possibile utilizzare la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="aa33e-103">You can use the following steps to estimate the amount of space required to store data in a table:</span></span>  
  
1.  <span data-ttu-id="aa33e-104">Calcolare lo spazio necessario per l'heap o indice cluster seguendo le istruzioni in [Stima delle dimensioni di un heap](estimate-the-size-of-a-heap.md) o [Stima delle dimensioni di un indice cluster](estimate-the-size-of-a-clustered-index.md).</span><span class="sxs-lookup"><span data-stu-id="aa33e-104">Calculate the space required for the heap or clustered index following the instructions in [Estimate the Size of a Heap](estimate-the-size-of-a-heap.md) or [Estimate the Size of a Clustered Index](estimate-the-size-of-a-clustered-index.md).</span></span>  
  
2.  <span data-ttu-id="aa33e-105">Calcolare lo spazio necessario per ogni indice non cluster seguendo le istruzioni disponibili in [Stima delle dimensioni di un indice non cluster](estimate-the-size-of-a-nonclustered-index.md).</span><span class="sxs-lookup"><span data-stu-id="aa33e-105">For each nonclustered index, calculate the space required for it by following the instructions in [Estimate the Size of a Nonclustered Index](estimate-the-size-of-a-nonclustered-index.md).</span></span>  
  
3.  <span data-ttu-id="aa33e-106">Sommare i valori calcolati nei passaggi 1 e 2.</span><span class="sxs-lookup"><span data-stu-id="aa33e-106">Add the values calculated in steps 1 and 2.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa33e-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aa33e-107">See Also</span></span>  
 <span data-ttu-id="aa33e-108">[Stima delle dimensioni di un database](estimate-the-size-of-a-database.md) </span><span class="sxs-lookup"><span data-stu-id="aa33e-108">[Estimate the Size of a Database](estimate-the-size-of-a-database.md) </span></span>  
 <span data-ttu-id="aa33e-109">[Stima delle dimensioni di un heap](estimate-the-size-of-a-heap.md) </span><span class="sxs-lookup"><span data-stu-id="aa33e-109">[Estimate the Size of a Heap](estimate-the-size-of-a-heap.md) </span></span>  
 <span data-ttu-id="aa33e-110">[Stima delle dimensioni di un indice cluster](estimate-the-size-of-a-clustered-index.md) </span><span class="sxs-lookup"><span data-stu-id="aa33e-110">[Estimate the Size of a Clustered Index](estimate-the-size-of-a-clustered-index.md) </span></span>  
 [<span data-ttu-id="aa33e-111">Stima delle dimensioni di un indice non cluster</span><span class="sxs-lookup"><span data-stu-id="aa33e-111">Estimate the Size of a Nonclustered Index</span></span>](estimate-the-size-of-a-nonclustered-index.md)  
  
  
