---
title: Stimare le dimensioni di un database | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- space allocation [SQL Server], database size
- calculating database size
- increasing database size
- database size [SQL Server], estimating
- predicting database size
- size [SQL Server], databases
- estimating database size
- designing databases [SQL Server], estimating size
ms.assetid: 5b240161-eba4-44b0-946c-61a8fc00fc8c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6e3a390c4ade2c2dc08f67d2d1461955516e866c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627804"
---
# <a name="estimate-the-size-of-a-database"></a><span data-ttu-id="91618-102">Stima delle dimensioni di un database</span><span class="sxs-lookup"><span data-stu-id="91618-102">Estimate the Size of a Database</span></span>
  <span data-ttu-id="91618-103">Durante la progettazione di un database potrebbe essere necessario stimare le dimensioni che il database può raggiungere quando viene riempito di dati.</span><span class="sxs-lookup"><span data-stu-id="91618-103">When you design a database, you may have to estimate how large the database will be when filled with data.</span></span> <span data-ttu-id="91618-104">La stima delle dimensioni del database può consentire di determinare la configurazione hardware necessaria per raggiungere gli obiettivi seguenti:</span><span class="sxs-lookup"><span data-stu-id="91618-104">Estimating the size of the database can help you determine the hardware configuration you will require to do the following:</span></span>  
  
-   <span data-ttu-id="91618-105">Ottenere il livello di prestazioni necessario per eseguire correttamente le applicazioni.</span><span class="sxs-lookup"><span data-stu-id="91618-105">Achieve the performance required by your applications.</span></span>  
  
-   <span data-ttu-id="91618-106">Assegnare la quantità di spazio su disco appropriata per l'archiviazione dei dati e degli indici.</span><span class="sxs-lookup"><span data-stu-id="91618-106">Guarantee the appropriate physical amount of disk space required to store the data and indexes.</span></span>  
  
 <span data-ttu-id="91618-107">La stima delle dimensioni del database consente inoltre di determinare se è necessario ottimizzare la struttura del database.</span><span class="sxs-lookup"><span data-stu-id="91618-107">Estimating the size of a database can also help you determine whether the database design needs refining.</span></span> <span data-ttu-id="91618-108">Ad esempio, si potrebbe determinare che le dimensioni del database stimate sono troppo grandi per implementarlo nell'organizzazione e che è necessaria una maggiore normalizzazione.</span><span class="sxs-lookup"><span data-stu-id="91618-108">For example, you may determine that the estimated size of the database is too large to implement in your organization and that more normalization is required.</span></span> <span data-ttu-id="91618-109">Al contrario, le dimensioni potrebbero essere inferiori a quanto previsto</span><span class="sxs-lookup"><span data-stu-id="91618-109">Conversely, the estimated size may be smaller than expected.</span></span> <span data-ttu-id="91618-110">e ciò consentirebbe di denormalizzare il database per ottimizzare le prestazioni delle query.</span><span class="sxs-lookup"><span data-stu-id="91618-110">This would allow you to denormalize the database to improve query performance.</span></span>  
  
 <span data-ttu-id="91618-111">Per stimare le dimensioni del database, è possibile stimare le dimensioni di ogni singola tabella e quindi sommare i valori ottenuti.</span><span class="sxs-lookup"><span data-stu-id="91618-111">To estimate the size of a database, estimate the size of each table individually and then add the values obtained.</span></span> <span data-ttu-id="91618-112">Le dimensioni di una tabella dipendono dalla presenza o meno di indici e dal tipo di indici.</span><span class="sxs-lookup"><span data-stu-id="91618-112">The size of a table depends on whether the table has indexes and, if they do, what type of indexes.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="91618-113">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="91618-113">In This Section</span></span>  
  
|<span data-ttu-id="91618-114">Argomento</span><span class="sxs-lookup"><span data-stu-id="91618-114">Topic</span></span>|<span data-ttu-id="91618-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="91618-115">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="91618-116">Stimare le dimensioni di una tabella</span><span class="sxs-lookup"><span data-stu-id="91618-116">Estimate the Size of a Table</span></span>](estimate-the-size-of-a-table.md)|<span data-ttu-id="91618-117">Definisce i passaggi e i calcoli necessari per stimare la quantità di spazio necessaria per archiviare i dati in una tabella e gli indici associati.</span><span class="sxs-lookup"><span data-stu-id="91618-117">Defines the steps and calculations needed to estimate the amount of space required to store the data in a table and associated indexes.</span></span>|  
|[<span data-ttu-id="91618-118">Stimare le dimensioni di un heap</span><span class="sxs-lookup"><span data-stu-id="91618-118">Estimate the Size of a Heap</span></span>](estimate-the-size-of-a-heap.md)|<span data-ttu-id="91618-119">Definisce i passaggi e i calcoli necessari per stimare la quantità di spazio necessaria per archiviare i dati in un heap,</span><span class="sxs-lookup"><span data-stu-id="91618-119">Defines the steps and calculations needed to estimate the amount of space required to store the data in a heap.</span></span> <span data-ttu-id="91618-120">ovvero in una tabella per cui non è disponibile un indice cluster.</span><span class="sxs-lookup"><span data-stu-id="91618-120">A heap is a table that does not have a clustered index.</span></span>|  
|[<span data-ttu-id="91618-121">Stima delle dimensioni di un indice cluster</span><span class="sxs-lookup"><span data-stu-id="91618-121">Estimate the Size of a Clustered Index</span></span>](estimate-the-size-of-a-clustered-index.md)|<span data-ttu-id="91618-122">Definisce i passaggi e i calcoli necessari per stimare la quantità di spazio necessaria per archiviare i dati in un indice cluster.</span><span class="sxs-lookup"><span data-stu-id="91618-122">Defines the steps and calculations needed to estimate the amount of space required to store the data in a clustered index.</span></span>|  
|[<span data-ttu-id="91618-123">Stima delle dimensioni di un indice non cluster</span><span class="sxs-lookup"><span data-stu-id="91618-123">Estimate the Size of a Nonclustered Index</span></span>](estimate-the-size-of-a-nonclustered-index.md)|<span data-ttu-id="91618-124">Definisce i passaggi e i calcoli necessari per stimare la quantità di spazio necessaria per archiviare i dati in un indice non cluster.</span><span class="sxs-lookup"><span data-stu-id="91618-124">Defines the steps and calculations needed to estimate the amount of space required to store the data in a nonclustered index.</span></span>|  
  
  
