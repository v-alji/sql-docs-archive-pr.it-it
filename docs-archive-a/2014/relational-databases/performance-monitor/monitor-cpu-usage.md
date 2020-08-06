---
title: Monitorare l'uso della CPU | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- monitoring performance [SQL Server], CPU usage
- tuning databases [SQL Server], CPU usage
- processors [SQL Server], monitoring usage
- database performance [SQL Server], CPU usage
- monitoring CPU usage [SQL Server]
- server performance [SQL Server], CPU usage
- database monitoring [SQL Server], CPU usage
- monitoring [SQL Server], CPU usage
- processors [SQL Server]
- CPU [SQL Server], monitoring
- monitoring server performance [SQL Server], CPU usage
ms.assetid: 2a02a3b6-07b2-4ad0-8a24-670414d19812
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f08d49348fd25593f27a87f2b0123f7ce43e35b5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723728"
---
# <a name="monitor-cpu-usage"></a><span data-ttu-id="9ee37-102">Monitorare l'utilizzo della CPU</span><span class="sxs-lookup"><span data-stu-id="9ee37-102">Monitor CPU Usage</span></span>
  <span data-ttu-id="9ee37-103">È opportuno monitorare periodicamente un'istanza di Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per verificare che i valori di utilizzo della CPU rientrino nei normali intervalli.</span><span class="sxs-lookup"><span data-stu-id="9ee37-103">Monitor an instance of Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] periodically to determine whether CPU usage rates are within normal ranges.</span></span> <span data-ttu-id="9ee37-104">Se la frequenza di utilizzo della CPU è costantemente elevata può essere necessario eseguire un aggiornamento della CPU o aggiungere più processori.</span><span class="sxs-lookup"><span data-stu-id="9ee37-104">A continually high rate of CPU usage may indicate the need to upgrade the CPU or add multiple processors.</span></span> <span data-ttu-id="9ee37-105">Una valore costantemente elevato di utilizzo della CPU può inoltre indicare la presenza di un'applicazione non progettata o ottimizzata correttamente.</span><span class="sxs-lookup"><span data-stu-id="9ee37-105">Alternatively, a high CPU usage rate may indicate a poorly tuned or designed application.</span></span> <span data-ttu-id="9ee37-106">L'ottimizzazione dell'applicazione potrebbe ridurre l'utilizzo della CPU.</span><span class="sxs-lookup"><span data-stu-id="9ee37-106">Optimizing the application can lower CPU utilization.</span></span>  
  
 <span data-ttu-id="9ee37-107">Una soluzione efficiente per determinare l'utilizzo della CPU consiste nell'usare il contatore **Processore:% Tempo processore** in Monitoraggio di sistema.</span><span class="sxs-lookup"><span data-stu-id="9ee37-107">An efficient way to determine CPU usage is to use the **Processor:% Processor Time** counter in System Monitor.</span></span> <span data-ttu-id="9ee37-108">Questo contatore consente di monitorare la quantità di tempo utilizzata dalla CPU per l'esecuzione di un thread non inattivo.</span><span class="sxs-lookup"><span data-stu-id="9ee37-108">This counter monitors the amount of time the CPU spends executing a thread that is not idle.</span></span> <span data-ttu-id="9ee37-109">Se il valore relativo a tale stato è incluso tra l'80% e il 90%, può essere necessario eseguire un aggiornamento della CPU o aggiungere ulteriori processori.</span><span class="sxs-lookup"><span data-stu-id="9ee37-109">A consistent state of 80 percent to 90 percent may indicate the need to upgrade your CPU or add more processors.</span></span> <span data-ttu-id="9ee37-110">Nel caso dei sistemi multiprocessore, è necessario monitorare un'istanza del contatore per ogni processore.</span><span class="sxs-lookup"><span data-stu-id="9ee37-110">For multiprocessor systems, monitor a separate instance of this counter for each processor.</span></span> <span data-ttu-id="9ee37-111">Il valore rappresenta il tempo totale di un processore specifico.</span><span class="sxs-lookup"><span data-stu-id="9ee37-111">This value represents the sum of processor time on a specific processor.</span></span> <span data-ttu-id="9ee37-112">Per determinare la media di tutti i processori, usare il contatore **Sistema: % Tempo totale processore** .</span><span class="sxs-lookup"><span data-stu-id="9ee37-112">To determine the average for all processors, use the **System: %Total Processor Time** counter instead.</span></span>  
  
 <span data-ttu-id="9ee37-113">Facoltativamente, per monitorare l'utilizzo del processore è inoltre possibile utilizzare i contatori seguenti:</span><span class="sxs-lookup"><span data-stu-id="9ee37-113">Optionally, you can also monitor the following counters to monitor processor usage:</span></span>  
  
-   <span data-ttu-id="9ee37-114">**Processore: % Tempo privilegiato**</span><span class="sxs-lookup"><span data-stu-id="9ee37-114">**Processor: % Privileged Time**</span></span>  
  
     <span data-ttu-id="9ee37-115">Indica la percentuale di tempo richiesta dal processore per l'esecuzione dei comandi kernel di Microsoft Windows, ad esempio l'elaborazione delle richieste di I/O di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9ee37-115">Corresponds to the percentage of time the processor spends on execution of Microsoft Windows kernel commands, such as processing of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] I/O requests.</span></span> <span data-ttu-id="9ee37-116">Se il valore di questo contatore è costantemente elevato e anche i contatori **Disco fisico** presentano valori elevati, valutare la possibilità di installare un sottosistema di disco più veloce o più efficiente.</span><span class="sxs-lookup"><span data-stu-id="9ee37-116">If this counter is consistently high when the **Physical Disk** counters are high, consider installing a faster or more efficient disk subsystem.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9ee37-117">I diversi tipi di controller del disco e driver utilizzano quantità diverse di tempo di elaborazione del kernel.</span><span class="sxs-lookup"><span data-stu-id="9ee37-117">Different disk controllers and drivers use different amounts of kernel processing time.</span></span> <span data-ttu-id="9ee37-118">I controller e i driver efficienti richiedono meno tempo privilegiato, lasciando una maggior quantità di tempo di elaborazione disponibile per le applicazioni utente, migliorando di conseguenza il throughput generale.</span><span class="sxs-lookup"><span data-stu-id="9ee37-118">Efficient controllers and drivers use less privileged time, leaving more processing time available for user applications, increasing overall throughput.</span></span>  
  
-   <span data-ttu-id="9ee37-119">**Processore: % Tempo utente**</span><span class="sxs-lookup"><span data-stu-id="9ee37-119">**Processor: %User Time**</span></span>  
  
     <span data-ttu-id="9ee37-120">Indica la percentuale di tempo richiesta dal processore per l'esecuzione dei processi utente, ad esempio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9ee37-120">Corresponds to the percentage of time that the processor spends on executing user processes such as [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="9ee37-121">**Sistema: Lunghezza coda processore**</span><span class="sxs-lookup"><span data-stu-id="9ee37-121">**System: Processor Queue Length**</span></span>  
  
     <span data-ttu-id="9ee37-122">Indica il numero di thread in attesa di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="9ee37-122">Corresponds to the number of threads waiting for processor time.</span></span> <span data-ttu-id="9ee37-123">Se i thread di un processo richiedono un numero di cicli del processore maggiore di quello disponibile, si verifica un collo di bottiglia a livello del processore.</span><span class="sxs-lookup"><span data-stu-id="9ee37-123">A processor bottleneck develops when threads of a process require more processor cycles than are available.</span></span> <span data-ttu-id="9ee37-124">Se una quantità notevole di processi tenta di utilizzare il tempo del processore, può essere necessario installare un processore più veloce</span><span class="sxs-lookup"><span data-stu-id="9ee37-124">If more than a few processes attempt to utilize the processor's time, you might need to install a faster processor.</span></span> <span data-ttu-id="9ee37-125">o, nel caso di sistemi multiprocessore, aggiungere un processore.</span><span class="sxs-lookup"><span data-stu-id="9ee37-125">Or, if you have a multiprocessor system, you could add a processor.</span></span>  
  
 <span data-ttu-id="9ee37-126">Quando si analizza l'utilizzo del processore, è necessario tenere presente il tipo di attività eseguita dall'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9ee37-126">When you examine processor usage, consider the type of work that the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] performs.</span></span> <span data-ttu-id="9ee37-127">Se [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] esegue numerosi calcoli, ad esempio query che riguardano aggregazioni o query gestite in memoria che non richiedono I/O su disco, è possibile che venga utilizzato il 100% del tempo del processore.</span><span class="sxs-lookup"><span data-stu-id="9ee37-127">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] performs many calculations, such as queries involving aggregates or memory-bound queries that require no disk I/O, 100 percent of the processor's time can be used.</span></span> <span data-ttu-id="9ee37-128">In tal caso, se le prestazioni delle altre applicazioni peggiorano, provare a modificare il carico di lavoro,</span><span class="sxs-lookup"><span data-stu-id="9ee37-128">If this causes the performance of other applications to suffer, try changing the workload.</span></span> <span data-ttu-id="9ee37-129">ad esempio dedicando il computer all'esecuzione dell'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9ee37-129">For example, dedicate the computer to running the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="9ee37-130">I valori di utilizzo prossimi al 100%, sintomo dell'elaborazione di numerose richieste client, possono indicare la presenza di processi in coda in attesa del tempo del processore che causano un collo di bottiglia.</span><span class="sxs-lookup"><span data-stu-id="9ee37-130">Usage rates around 100 percent, where many client requests are being processed, may indicate that processes are queuing up, waiting for processor time, and causing a bottleneck.</span></span> <span data-ttu-id="9ee37-131">Risolvere il problema aggiungendo processori più veloci.</span><span class="sxs-lookup"><span data-stu-id="9ee37-131">Resolve the problem by adding faster processors.</span></span>  
  
  
