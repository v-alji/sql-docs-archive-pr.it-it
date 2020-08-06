---
title: Oggetto Wait Statistics di SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Wait Statistics object
- SQLServer:Wait Statistics
ms.assetid: cb7f917d-4291-4115-9b78-ee7692ebbb2d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5cfd2f1309cb118896ff7951b7f82feb38de60e7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713068"
---
# <a name="sql-server-wait-statistics-object"></a><span data-ttu-id="0a41c-102">Oggetto Statistiche attesa di SQL Server</span><span class="sxs-lookup"><span data-stu-id="0a41c-102">SQL Server, Wait Statistics Object</span></span>
  <span data-ttu-id="0a41c-103">L'oggetto prestazioni **SQLServer:Statistiche attesa** contiene contatori delle prestazioni che forniscono informazioni sullo stato di attesa.</span><span class="sxs-lookup"><span data-stu-id="0a41c-103">The **SQLServer:Wait Statistics** performance object contains performance counters that report information about wait status.</span></span>  
  
 <span data-ttu-id="0a41c-104">Nella tabella seguente sono elencati i contatori inclusi nell'oggetto Statistiche attesa.</span><span class="sxs-lookup"><span data-stu-id="0a41c-104">The table below lists the counters that the Wait Statistics object contains.</span></span>  
  
|<span data-ttu-id="0a41c-105">Contatori dell'oggetto Statistiche attesa di SQL Server</span><span class="sxs-lookup"><span data-stu-id="0a41c-105">SQL Server Wait Statistics counters</span></span>|<span data-ttu-id="0a41c-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0a41c-106">Description</span></span>|  
|-----------------------------------------|-----------------|  
|<span data-ttu-id="0a41c-107">**Attese di blocco**</span><span class="sxs-lookup"><span data-stu-id="0a41c-107">**Lock waits**</span></span>|<span data-ttu-id="0a41c-108">Statistiche relative ai processi in attesa di un blocco.</span><span class="sxs-lookup"><span data-stu-id="0a41c-108">Statistics for processes waiting on a lock.</span></span>|  
|<span data-ttu-id="0a41c-109">**Attese buffer log**</span><span class="sxs-lookup"><span data-stu-id="0a41c-109">**Log buffer waits**</span></span>|<span data-ttu-id="0a41c-110">Statistiche relative ai processi in attesa che il buffer del log diventi disponibile.</span><span class="sxs-lookup"><span data-stu-id="0a41c-110">Statistics for processes waiting for log buffer to be available.</span></span>|  
|<span data-ttu-id="0a41c-111">**Attese scrittura log**</span><span class="sxs-lookup"><span data-stu-id="0a41c-111">**Log write waits**</span></span>|<span data-ttu-id="0a41c-112">Statistiche relative ai processi in attesa di scrittura nel buffer del log.</span><span class="sxs-lookup"><span data-stu-id="0a41c-112">Statistics for processes waiting for log buffer to be written.</span></span>|  
|<span data-ttu-id="0a41c-113">**Attese coda concessione memoria**</span><span class="sxs-lookup"><span data-stu-id="0a41c-113">**Memory grant queue waits**</span></span>|<span data-ttu-id="0a41c-114">Statistiche relative ai processi in attesa di una concessione di memoria.</span><span class="sxs-lookup"><span data-stu-id="0a41c-114">Statistics for processes waiting for memory grant to become available.</span></span>|  
|<span data-ttu-id="0a41c-115">**Attese I/O di rete**</span><span class="sxs-lookup"><span data-stu-id="0a41c-115">**Network IO waits**</span></span>|<span data-ttu-id="0a41c-116">Statistiche relative alle attese per operazioni di I/O di rete.</span><span class="sxs-lookup"><span data-stu-id="0a41c-116">Statistics relevant to wait on network I/O.</span></span>|  
|<span data-ttu-id="0a41c-117">**Attese latch non di pagina**</span><span class="sxs-lookup"><span data-stu-id="0a41c-117">**Non-Page latch waits**</span></span>|<span data-ttu-id="0a41c-118">Statistiche relative ai latch non di pagina.</span><span class="sxs-lookup"><span data-stu-id="0a41c-118">Statistics relevant to non-page latches.</span></span>|  
|<span data-ttu-id="0a41c-119">**Attese latch I/O di pagina**</span><span class="sxs-lookup"><span data-stu-id="0a41c-119">**Page IO latch waits**</span></span>|<span data-ttu-id="0a41c-120">Statistiche relative ai latch di I/O di pagina.</span><span class="sxs-lookup"><span data-stu-id="0a41c-120">Statistics relevant to page I/O latches.</span></span>|  
|<span data-ttu-id="0a41c-121">**Attese latch pagina**</span><span class="sxs-lookup"><span data-stu-id="0a41c-121">**Page latch waits**</span></span>|<span data-ttu-id="0a41c-122">Statistiche relative ai latch di pagina, esclusi i latch di I/O.</span><span class="sxs-lookup"><span data-stu-id="0a41c-122">Statistics relevant to page latches, not including I/O latches.</span></span>|  
|<span data-ttu-id="0a41c-123">**Attesa oggetti memoria affidabili**</span><span class="sxs-lookup"><span data-stu-id="0a41c-123">**Thread-safe memory objects waits**</span></span>|<span data-ttu-id="0a41c-124">Statistiche relative ai processi in attesa di allocatori di memoria affidabili.</span><span class="sxs-lookup"><span data-stu-id="0a41c-124">Statistics for processes waiting on thread-safe memory allocators.</span></span>|  
|<span data-ttu-id="0a41c-125">**Attese proprietà transazione**</span><span class="sxs-lookup"><span data-stu-id="0a41c-125">**Transaction ownership waits**</span></span>|<span data-ttu-id="0a41c-126">Statistiche relative alla sincronizzazione dell'accesso dei processi alla transazione.</span><span class="sxs-lookup"><span data-stu-id="0a41c-126">Statistics relevant to processes synchronizing access to transaction.</span></span>|  
|<span data-ttu-id="0a41c-127">**Attesa thread di lavoro**</span><span class="sxs-lookup"><span data-stu-id="0a41c-127">**Wait for the worker**</span></span>|<span data-ttu-id="0a41c-128">Statistiche relative ai processi in attesa che il thread di lavoro diventi disponibile.</span><span class="sxs-lookup"><span data-stu-id="0a41c-128">Statistics relevant to processes waiting for worker to become available.</span></span>|  
|<span data-ttu-id="0a41c-129">**Attese sincronizzazione area di lavoro**</span><span class="sxs-lookup"><span data-stu-id="0a41c-129">**Workspace synchronization waits**</span></span>|<span data-ttu-id="0a41c-130">Statistiche relative alla sincronizzazione dell'accesso dei processi all'area di lavoro.</span><span class="sxs-lookup"><span data-stu-id="0a41c-130">Statistics relevant to processes synchronizing access to workspace.</span></span>|  
  
 <span data-ttu-id="0a41c-131">Per ogni contatore nell'oggetto sono disponibili le istanze seguenti:</span><span class="sxs-lookup"><span data-stu-id="0a41c-131">Each counter in the object contains the following instances:</span></span>  
  
|<span data-ttu-id="0a41c-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="0a41c-132">Item</span></span>|<span data-ttu-id="0a41c-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0a41c-133">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="0a41c-134">**Tempo medio di attesa (ms)**</span><span class="sxs-lookup"><span data-stu-id="0a41c-134">**Average wait time (ms)**</span></span>|<span data-ttu-id="0a41c-135">Tempo medio per il tipo di attesa selezionato.</span><span class="sxs-lookup"><span data-stu-id="0a41c-135">Average time for the selected type of wait.</span></span>|  
|<span data-ttu-id="0a41c-136">**Tempo di attesa (ms) cumulativo al secondo**</span><span class="sxs-lookup"><span data-stu-id="0a41c-136">**Cumulative wait time (ms) per second**</span></span>|<span data-ttu-id="0a41c-137">Tempo di attesa aggregato al secondo per il tipo di attesa selezionato</span><span class="sxs-lookup"><span data-stu-id="0a41c-137">Aggregated wait time per second, for the selected type of wait.</span></span>|  
|<span data-ttu-id="0a41c-138">**Attese in corso**</span><span class="sxs-lookup"><span data-stu-id="0a41c-138">**Waits in progress**</span></span>|<span data-ttu-id="0a41c-139">Numero di processi attualmente in attesa del tipo seguente.</span><span class="sxs-lookup"><span data-stu-id="0a41c-139">Number of processes currently waiting on the following type.</span></span>|  
|<span data-ttu-id="0a41c-140">**Attese avviate al secondo**</span><span class="sxs-lookup"><span data-stu-id="0a41c-140">**Waits started per second**</span></span>|<span data-ttu-id="0a41c-141">Numero di attese avviate al secondo del tipo di attesa selezionato.</span><span class="sxs-lookup"><span data-stu-id="0a41c-141">Number of waits started per second of the selected type of wait.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0a41c-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0a41c-142">See Also</span></span>  
 [<span data-ttu-id="0a41c-143">Monitorare l'utilizzo delle risorse &#40;Monitor di sistema&#41;</span><span class="sxs-lookup"><span data-stu-id="0a41c-143">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](monitor-resource-usage-system-monitor.md)  
  
  
