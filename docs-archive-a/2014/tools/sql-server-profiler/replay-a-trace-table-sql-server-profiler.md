---
title: Riprodurre una tabella di traccia (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- traces [SQL Server], replaying
- replaying traces
ms.assetid: 6a0ad817-3d8d-4495-889d-c66a7ef9e8bb
author: stevestein
ms.author: sstein
ms.openlocfilehash: f3c26858fa852686bc3d9ccf4a26d47e04852647
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717117"
---
# <a name="replay-a-trace-table-sql-server-profiler"></a><span data-ttu-id="0522c-102">Riprodurre una tabella di traccia (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="0522c-102">Replay a Trace Table (SQL Server Profiler)</span></span>
  <span data-ttu-id="0522c-103">La funzionalità di riproduzione è la capacità di aprire una traccia salvata e riprodurla nuovamente.</span><span class="sxs-lookup"><span data-stu-id="0522c-103">Replay is the ability to open a saved trace and replay it again.</span></span> [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="0522c-104">include un motore di riproduzione a thread multipli in grado di simulare le connessioni utente e l'autenticazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0522c-104">features a multithreaded playback engine that can simulate user connections and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="0522c-105">La funzionalità di riproduzione risulta utile per la risoluzione dei problemi a livello di applicazione o di processo.</span><span class="sxs-lookup"><span data-stu-id="0522c-105">Replay is useful to troubleshoot an application or process problem.</span></span> <span data-ttu-id="0522c-106">Quando si identifica il problema e si implementano le correzioni adeguate, eseguire nell'applicazione o nel processo la traccia con cui è stato rilevato il possibile problema.</span><span class="sxs-lookup"><span data-stu-id="0522c-106">When you identify the problem and implement corrections, run the trace that found the potential problem against the corrected application or process.</span></span> <span data-ttu-id="0522c-107">Riprodurre quindi la traccia originale e confrontare i risultati.</span><span class="sxs-lookup"><span data-stu-id="0522c-107">Then, replay the original trace and compare results.</span></span>  
  
 <span data-ttu-id="0522c-108">Per consentire la riproduzione è necessario acquisire classi di evento specifiche oltre alle classi di evento che si desidera monitorare.</span><span class="sxs-lookup"><span data-stu-id="0522c-108">In addition to any other event classes you want to monitor, specific event classes must be captured to enable replay.</span></span> <span data-ttu-id="0522c-109">Questi eventi vengono acquisiti per impostazione predefinita se si usa il modello di traccia **TSQL_Replay** .</span><span class="sxs-lookup"><span data-stu-id="0522c-109">These events are captured by default if you use the **TSQL_Replay** trace template.</span></span> <span data-ttu-id="0522c-110">Per altre informazioni, vedere [Requisiti per la riproduzione](replay-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0522c-110">For more information, see [Replay Requirements](replay-requirements.md).</span></span>  
  
### <a name="to-replay-a-trace-table"></a><span data-ttu-id="0522c-111">Per riprodurre una tabella di traccia</span><span class="sxs-lookup"><span data-stu-id="0522c-111">To replay a trace table</span></span>  
  
1.  <span data-ttu-id="0522c-112">Aprire una tabella di traccia contenente le classi di eventi necessarie per la riproduzione.</span><span class="sxs-lookup"><span data-stu-id="0522c-112">Open a trace table that contains the event classes necessary for replay.</span></span>  
  
2.  <span data-ttu-id="0522c-113">Scegliere **Avvia** dal menu **Riproduci**e connettersi all'istanza del server in cui si vuole riprodurre la traccia.</span><span class="sxs-lookup"><span data-stu-id="0522c-113">On the **Replay** menu, click **Start**, and connect to the server instance where you want to replay the trace.</span></span>  
  
3.  <span data-ttu-id="0522c-114">Specificare **Server di riproduzione** nella scheda **Opzioni di base di riproduzione** della finestra di dialogo **Configurazione riproduzione**.</span><span class="sxs-lookup"><span data-stu-id="0522c-114">In the **Replay Configuration** dialog box, on the **Basic Replay Options** tab, specify **Replay server**.</span></span> <span data-ttu-id="0522c-115">Fare clic su **Cambia** per modificare il server visualizzato nella casella **Server di riproduzione** .</span><span class="sxs-lookup"><span data-stu-id="0522c-115">Click **Change** to change the server that is displayed in the **Replay server** box.</span></span>  
  
4.  <span data-ttu-id="0522c-116">È facoltativamente possibile selezionare una delle destinazioni seguenti in cui salvare la riproduzione:</span><span class="sxs-lookup"><span data-stu-id="0522c-116">Optionally, select one of the following destinations in which to save the replay:</span></span>  
  
    -   <span data-ttu-id="0522c-117">**Salva nel file** che consente di specificare un file in cui salvare la riproduzione.</span><span class="sxs-lookup"><span data-stu-id="0522c-117">**Save to file,** which specifies a file in which to save the replay.</span></span>  
  
    -   <span data-ttu-id="0522c-118">**Salva nella tabella**che consente di specificare una tabella di database in cui salvare la riproduzione.</span><span class="sxs-lookup"><span data-stu-id="0522c-118">**Save to table**, which specifies a database table in which to save the replay.</span></span>  
  
5.  <span data-ttu-id="0522c-119">Selezionare **Riproduci gli eventi nell'ordine in cui sono stati inseriti nella traccia**oppure **Riproduci gli eventi usando più thread**.</span><span class="sxs-lookup"><span data-stu-id="0522c-119">Choose either **Replay the events in the order they were traced**or **Replay events using multiple threads**.</span></span> <span data-ttu-id="0522c-120">Nella tabella seguente viene spiegata la differenza tra queste impostazioni.</span><span class="sxs-lookup"><span data-stu-id="0522c-120">The following table explains the difference between these settings.</span></span>  
  
    |<span data-ttu-id="0522c-121">Opzione</span><span class="sxs-lookup"><span data-stu-id="0522c-121">Option</span></span>|<span data-ttu-id="0522c-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0522c-122">Description</span></span>|  
    |------------|-----------------|  
    |<span data-ttu-id="0522c-123">**Riproduci gli eventi nell'ordine in cui sono stati inseriti nella traccia**</span><span class="sxs-lookup"><span data-stu-id="0522c-123">**Replay events in the order they were traced**</span></span>|<span data-ttu-id="0522c-124">Gli eventi vengono riprodotti nell'ordine in cui sono stati inseriti nella traccia.</span><span class="sxs-lookup"><span data-stu-id="0522c-124">Replays events in the order they were recorded.</span></span> <span data-ttu-id="0522c-125">Questa opzione consente il debug.</span><span class="sxs-lookup"><span data-stu-id="0522c-125">This option enables debugging.</span></span>|  
    |<span data-ttu-id="0522c-126">**Riproduci gli eventi usando più thread**</span><span class="sxs-lookup"><span data-stu-id="0522c-126">**Replay events using multiple threads**</span></span>|<span data-ttu-id="0522c-127">Vengono utilizzati più thread per riprodurre i vari eventi, indipendentemente dalla sequenza.</span><span class="sxs-lookup"><span data-stu-id="0522c-127">This option uses multiple threads to replay each event regardless of the sequence.</span></span> <span data-ttu-id="0522c-128">Questa opzione consente di ottimizzare le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="0522c-128">This option optimizes performance.</span></span>|  
  
6.  <span data-ttu-id="0522c-129">Selezionare **Visualizza risultati di riproduzione** per visualizzare la riproduzione quando si verifica.</span><span class="sxs-lookup"><span data-stu-id="0522c-129">Select **Display replay results** to view the replay as it occurs.</span></span>  
  
7.  <span data-ttu-id="0522c-130">Se si vuole, è possibile fare clic sulla scheda **Opzioni avanzate di riproduzione**per configurare le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0522c-130">Optionally, click the **Advanced Replay Options**tab to specify the following options:</span></span>  
  
    -   <span data-ttu-id="0522c-131">Per riprodurre tutti gli ID dei processi server (SPID), selezionare **Riproduci SPID di sistema**.</span><span class="sxs-lookup"><span data-stu-id="0522c-131">To replay all server process IDs (SPIDs), select **Replay system SPIDs**.</span></span>  
  
    -   <span data-ttu-id="0522c-132">Per limitare la riproduzione ai processi appartenenti a uno specifico SPID, selezionare **Riproduci un solo SPID**.</span><span class="sxs-lookup"><span data-stu-id="0522c-132">To limit the replay to processes belonging to a specific SPID, select **Replay one SPID only**.</span></span> <span data-ttu-id="0522c-133">Digitare lo SPID nella casella **SPID da riprodurre**.</span><span class="sxs-lookup"><span data-stu-id="0522c-133">In the **SPID to replay**box, type the SPID.</span></span>  
  
    -   <span data-ttu-id="0522c-134">Per riprodurre gli eventi che si sono verificati in un determinato periodo di tempo, selezionare **Limite di tempo per la riproduzione**.</span><span class="sxs-lookup"><span data-stu-id="0522c-134">To replay events that occurred during a specific time period, select **Limit replay by date and time**.</span></span> <span data-ttu-id="0522c-135">Impostare i valori di data e ora in **Ora inizio**e **Ora fine**per specificare il periodo di tempo da includere nella riproduzione.</span><span class="sxs-lookup"><span data-stu-id="0522c-135">Select a date and time for the **Start time**and **End time**to specify the time period to include in the replay.</span></span>  
  
    -   <span data-ttu-id="0522c-136">Per controllare la modalità di gestione dei processi da parte di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] durante la riproduzione, configurare le **Opzioni Health Monitor**.</span><span class="sxs-lookup"><span data-stu-id="0522c-136">To control how [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] manages processes during replay, configure **Health Monitor Options**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0522c-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0522c-137">See Also</span></span>  
 <span data-ttu-id="0522c-138">[Autorizzazioni necessarie per l'esecuzione di SQL Server Profiler](sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="0522c-138">[Permissions Required to Run SQL Server Profiler](sql-server-profiler.md) </span></span>  
 <span data-ttu-id="0522c-139">[Riprodurre le tracce](replay-traces.md) </span><span class="sxs-lookup"><span data-stu-id="0522c-139">[Replay Traces](replay-traces.md) </span></span>  
 <span data-ttu-id="0522c-140">[Aprire una tabella di traccia &#40;SQL Server Profiler&#41;](open-a-trace-table-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="0522c-140">[Open a Trace Table &#40;SQL Server Profiler&#41;](open-a-trace-table-sql-server-profiler.md) </span></span>  
 [<span data-ttu-id="0522c-141">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="0522c-141">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
