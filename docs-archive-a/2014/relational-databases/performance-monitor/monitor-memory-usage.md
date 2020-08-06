---
title: Monitorare l'uso della memoria | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- tuning databases [SQL Server], memory
- monitoring server performance [SQL Server], memory usage
- isolating memory [SQL Server]
- paging rate [SQL Server]
- memory [SQL Server], monitoring usage
- monitoring [SQL Server], memory usage
- low-memory conditions
- database monitoring [SQL Server], memory usage
- available memory [SQL Server]
- page faults [SQL Server]
- monitoring performance [SQL Server], memory usage
- server performance [SQL Server], memory
ms.assetid: 1aee3933-a11c-4b87-91b7-32f5ea38c87f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 1986d9576f9b067cad18f27d4febbf097ed52703
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723723"
---
# <a name="monitor-memory-usage"></a><span data-ttu-id="88825-102">Monitoraggio dell'utilizzo della memoria</span><span class="sxs-lookup"><span data-stu-id="88825-102">Monitor Memory Usage</span></span>
  <span data-ttu-id="88825-103">Monitorare periodicamente un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per verificare che l'utilizzo della memoria rientri negli intervalli standard.</span><span class="sxs-lookup"><span data-stu-id="88825-103">Monitor an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] periodically to confirm that memory usage is within typical ranges.</span></span>  
  
 <span data-ttu-id="88825-104">Per monitorare la quantità di memoria disponibile, usare i seguenti contatori:</span><span class="sxs-lookup"><span data-stu-id="88825-104">To monitor for a low-memory condition, use the following object counters:</span></span>  
  
-   <span data-ttu-id="88825-105">**Memoria: Byte disponibili**</span><span class="sxs-lookup"><span data-stu-id="88825-105">**Memory: Available Bytes**</span></span>  
  
-   <span data-ttu-id="88825-106">**Memoria: Pagine/sec**</span><span class="sxs-lookup"><span data-stu-id="88825-106">**Memory: Pages/sec**</span></span>  
  
 <span data-ttu-id="88825-107">Il contatore **Byte disponibili** indica il numero di byte di memoria disponibili per i processi.</span><span class="sxs-lookup"><span data-stu-id="88825-107">The **Available Bytes** counter indicates how many bytes of memory are currently available for use by processes.</span></span> <span data-ttu-id="88825-108">Il contatore **Pagine/sec** indica il numero di pagine richiamate dal disco o scritte su disco per liberare spazio nel set di lavoro in seguito a errori di pagina.</span><span class="sxs-lookup"><span data-stu-id="88825-108">The **Pages/sec** counter indicates the number of pages that either were retrieved from disk due to hard page faults or written to disk to free space in the working set due to page faults.</span></span>  
  
 <span data-ttu-id="88825-109">Valori bassi del contatore **Byte disponibili** possono indicare una quantità di memoria insufficiente nel computer o la presenza di un'applicazione che non rilascia la memoria.</span><span class="sxs-lookup"><span data-stu-id="88825-109">Low values for the **Available Bytes** counter can indicate that there is an overall shortage of memory on the computer or that an application is not releasing memory.</span></span> <span data-ttu-id="88825-110">Un valore elevato del contatore **Pagine/sec** può indicare un paging eccessivo.</span><span class="sxs-lookup"><span data-stu-id="88825-110">A high rate for the **Pages/sec** counter could indicate excessive paging.</span></span> <span data-ttu-id="88825-111">Monitorare il contatore **Memoria: Errori di pagina/sec** per assicurarsi che l'attività del disco non sia dovuta al paging.</span><span class="sxs-lookup"><span data-stu-id="88825-111">Monitor the **Memory: Page Faults/sec** counter to make sure that the disk activity is not caused by paging.</span></span>  
  
 <span data-ttu-id="88825-112">Anche nei computer con una notevole quantità di memoria disponibile, la frequenza di paging, e quindi di errori di pagina, dovrebbe essere bassa.</span><span class="sxs-lookup"><span data-stu-id="88825-112">A low rate of paging (and hence page faults) is typical, even if the computer has plenty of available memory.</span></span> <span data-ttu-id="88825-113">Microsoft Windows Virtual Memory Manager (VMM) sottrae pagine a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e agli altri processi in quanto riduce le dimensioni dei set di lavoro di tali processi.</span><span class="sxs-lookup"><span data-stu-id="88825-113">The Microsoft Windows Virtual Memory Manager (VMM) takes pages from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and other processes as it trims the working-set sizes of those processes.</span></span> <span data-ttu-id="88825-114">L'attività di VMM tende quindi a causare errori di pagina.</span><span class="sxs-lookup"><span data-stu-id="88825-114">This VMM activity tends to cause page faults.</span></span> <span data-ttu-id="88825-115">Per determinare se [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o un altro processo provoca un paging eccessivo, monitorare il contatore **Processo: Errori di pagina/sec** alla ricerca dell'istanza del processo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="88825-115">To determine whether [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or another process is the cause of excessive paging, monitor the **Process: Page Faults/sec** counter for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] process instance.</span></span>  
  
 <span data-ttu-id="88825-116">Per altre informazioni su come evitare il paging eccessivo, vedere la documentazione del sistema operativo Windows.</span><span class="sxs-lookup"><span data-stu-id="88825-116">For more information about resolving excessive paging, see the Windows operating system documentation.</span></span>  
  
## <a name="isolating-memory-used-by-sql-server"></a><span data-ttu-id="88825-117">Memoria usata da SQL Server</span><span class="sxs-lookup"><span data-stu-id="88825-117">Isolating Memory Used by SQL Server</span></span>  
 <span data-ttu-id="88825-118">Per impostazione predefinita, in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] i requisiti di memoria vengono modificati in modo dinamico in base alle risorse di sistema disponibili.</span><span class="sxs-lookup"><span data-stu-id="88825-118">By default, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] changes its memory requirements dynamically, on the basis of available system resources.</span></span> <span data-ttu-id="88825-119">Se [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] necessita di una maggior quantità di memoria, richiede al sistema operativo di determinare se è disponibile memoria fisica e utilizza la memoria disponibile.</span><span class="sxs-lookup"><span data-stu-id="88825-119">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] needs more memory, it queries the operating system to determine whether free physical memory is available and uses the available memory.</span></span> <span data-ttu-id="88825-120">Se [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] non utilizza completamente la memoria attualmente allocata, rilascia la memoria al sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="88825-120">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] does not need the memory currently allocated to it, it releases the memory to the operating system.</span></span> <span data-ttu-id="88825-121">È tuttavia possibile ignorare l'opzione per l'uso dinamico della memoria specificando le opzioni di configurazione del server **minservermemory**e **maxservermemory** .</span><span class="sxs-lookup"><span data-stu-id="88825-121">However, you can override the option to dynamically use memory by using the **minservermemory**, and **maxservermemory** server configuration options.</span></span> <span data-ttu-id="88825-122">Per altre informazioni, vedere [Opzioni per la memoria server](../../database-engine/configure-windows/server-memory-server-configuration-options.md).</span><span class="sxs-lookup"><span data-stu-id="88825-122">For more information, see [Server Memory Options](../../database-engine/configure-windows/server-memory-server-configuration-options.md).</span></span>  
  
 <span data-ttu-id="88825-123">Per monitorare la quantità di memoria usata da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , esaminare i contatori delle prestazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="88825-123">To monitor the amount of memory that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] uses, examine the following performance counters:</span></span>  
  
-   <span data-ttu-id="88825-124">**Processo: Working set**</span><span class="sxs-lookup"><span data-stu-id="88825-124">**Process: Working Set**</span></span>  
  
-   <span data-ttu-id="88825-125">**SQL Server: Gestione buffer: Percentuale riscontri cache del buffer**</span><span class="sxs-lookup"><span data-stu-id="88825-125">**SQL Server: Buffer Manager: Buffer Cache Hit Ratio**</span></span>  
  
-   <span data-ttu-id="88825-126">**SQL Server: Gestione buffer: Pagine di database**</span><span class="sxs-lookup"><span data-stu-id="88825-126">**SQL Server: Buffer Manager: Database Pages**</span></span>  
  
-   <span data-ttu-id="88825-127">**SQL Server: Gestione memoria: Memoria totale server (KB)**</span><span class="sxs-lookup"><span data-stu-id="88825-127">**SQL Server: Memory Manager: Total Server Memory (KB)**</span></span>  
  
 <span data-ttu-id="88825-128">Il contatore **Working set** indica la quantità di memoria usata da un processo.</span><span class="sxs-lookup"><span data-stu-id="88825-128">The **WorkingSet** counter shows the amount of memory that is used by a process.</span></span> <span data-ttu-id="88825-129">Se questo valore è costantemente inferiore alla quantità di memoria impostata dalle opzioni server **min server memory** e **max server memory** , [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] è stato configurato per usare una quantità eccessiva di memoria.</span><span class="sxs-lookup"><span data-stu-id="88825-129">If this number is consistently below the amount of memory that is set by the **min server memory** and **max server memory** server options, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is configured to use too much memory.</span></span>  
  
 <span data-ttu-id="88825-130">Il contatore **Percentuale riscontri cache del buffer** è specifico per un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="88825-130">The **Buffer Cache Hit Ratio** counter is specific to an application.</span></span> <span data-ttu-id="88825-131">È tuttavia preferibile un livello pari o superiore a 90%.</span><span class="sxs-lookup"><span data-stu-id="88825-131">However, a rate of 90 percent or higher is desirable.</span></span> <span data-ttu-id="88825-132">Aggiungere memoria fino a raggiungere un valore costantemente superiore a 90%.</span><span class="sxs-lookup"><span data-stu-id="88825-132">Add more memory until the value is consistently greater than 90 percent.</span></span> <span data-ttu-id="88825-133">Tale percentuale indica che è stato soddisfatto oltre il 90% di tutte le richieste di dati dalla cache dei dati.</span><span class="sxs-lookup"><span data-stu-id="88825-133">A value greater than 90 percent indicates that more than 90 percent of all requests for data were satisfied from the data cache.</span></span>  
  
 <span data-ttu-id="88825-134">Se il valore del contatore **Memoria totale server (KB)Memoria** è costantemente elevato rispetto alla quantità di memoria fisica del computer, può essere necessario aggiungere ulteriore memoria.</span><span class="sxs-lookup"><span data-stu-id="88825-134">If the **TotalServerMemory (KB)** counter is consistently high compared to the amount of physical memory in the computer, it may indicate that more memory is required.</span></span>  
  
## <a name="determining-current-memory-allocation"></a><span data-ttu-id="88825-135">Determinazione dell'allocazione di memoria corrente</span><span class="sxs-lookup"><span data-stu-id="88825-135">Determining Current Memory Allocation</span></span>  
 <span data-ttu-id="88825-136">La query seguente restituisce le informazioni sulla memoria attualmente allocata.</span><span class="sxs-lookup"><span data-stu-id="88825-136">The following query returns information about currently allocated memory.</span></span>  
  
```  
SELECT  
(physical_memory_in_use_kb/1024) AS Memory_usedby_Sqlserver_MB,  
(locked_page_allocations_kb/1024) AS Locked_pages_used_Sqlserver_MB,  
(total_virtual_address_space_kb/1024) AS Total_VAS_in_MB,  
process_physical_memory_low,  
process_virtual_memory_low  
FROM sys.dm_os_process_memory;  
```  
  
  
