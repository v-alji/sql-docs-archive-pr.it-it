---
title: Riprodurre un file di traccia (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- traces [SQL Server], replaying
- replaying traces
ms.assetid: 9e361275-c8fd-4499-8389-242cf8e27415
author: stevestein
ms.author: sstein
ms.openlocfilehash: d3a9f007b9b6d2b46be43abdb10db286a75c33fd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722059"
---
# <a name="replay-a-trace-file-sql-server-profiler"></a><span data-ttu-id="f045c-102">Riprodurre un file di traccia (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="f045c-102">Replay a Trace File (SQL Server Profiler)</span></span>
  <span data-ttu-id="f045c-103">La funzionalità di riproduzione è la capacità di aprire una traccia salvata e riprodurla nuovamente.</span><span class="sxs-lookup"><span data-stu-id="f045c-103">Replay is the ability to open a saved trace and replay it again.</span></span> [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="f045c-104">include un motore di riproduzione a thread multipli in grado di simulare le connessioni utente e l'autenticazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f045c-104">features a multithreaded playback engine that can simulate user connections and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="f045c-105">La funzionalità di riproduzione risulta utile per la risoluzione dei problemi a livello di applicazione o di processo.</span><span class="sxs-lookup"><span data-stu-id="f045c-105">Replay is useful to troubleshoot an application or process problem.</span></span> <span data-ttu-id="f045c-106">Quando si identifica il problema e si implementano le correzioni adeguate, eseguire nell'applicazione o nel processo la traccia con cui è stato rilevato il possibile problema.</span><span class="sxs-lookup"><span data-stu-id="f045c-106">When you identify the problem and implement corrections, run the trace that found the potential problem against the corrected application or process.</span></span> <span data-ttu-id="f045c-107">Riprodurre quindi la traccia originale e confrontare i risultati.</span><span class="sxs-lookup"><span data-stu-id="f045c-107">Then, replay the original trace and compare results.</span></span>  
  
 <span data-ttu-id="f045c-108">Per consentire la riproduzione è necessario acquisire classi di evento specifiche oltre alle classi di evento che si desidera monitorare.</span><span class="sxs-lookup"><span data-stu-id="f045c-108">In addition to any other event classes you want to monitor, specific event classes must be captured to enable replay.</span></span> <span data-ttu-id="f045c-109">Questi eventi vengono acquisiti per impostazione predefinita se si usa il modello di traccia **TSQL_Replay** .</span><span class="sxs-lookup"><span data-stu-id="f045c-109">These events are captured by default if you use the **TSQL_Replay** trace template.</span></span> <span data-ttu-id="f045c-110">Per altre informazioni, vedere [Requisiti per la riproduzione](replay-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f045c-110">For more information, see [Replay Requirements](replay-requirements.md).</span></span>  
  
### <a name="to-replay-a-trace-file"></a><span data-ttu-id="f045c-111">Per riprodurre un file di traccia</span><span class="sxs-lookup"><span data-stu-id="f045c-111">To replay a trace file</span></span>  
  
1.  <span data-ttu-id="f045c-112">Scegliere **Apri** dal menu **File**e quindi **File di traccia**.</span><span class="sxs-lookup"><span data-stu-id="f045c-112">On the **File** menu, point to **Open**, and then click **Trace File**.</span></span> <span data-ttu-id="f045c-113">Selezionare un file di traccia che contiene le classi di evento necessarie per la riproduzione.</span><span class="sxs-lookup"><span data-stu-id="f045c-113">Select a trace file that contains the event classes necessary for replay.</span></span>  
  
2.  <span data-ttu-id="f045c-114">Scegliere **Avvia** dal menu **Riproduci**e connettersi all'istanza del server in cui si vuole riprodurre la traccia.</span><span class="sxs-lookup"><span data-stu-id="f045c-114">On the **Replay** menu, click **Start**, and connect to the server instance where you want to replay the trace.</span></span>  
  
3.  <span data-ttu-id="f045c-115">Specificare il **Server di riproduzione** nella scheda **Opzioni di base di riproduzione** della finestra di dialogo **Configurazione riproduzione**.</span><span class="sxs-lookup"><span data-stu-id="f045c-115">In the **Replay Configuration** dialog box, on the **Basic Replay Options** tab, specify the **Replay server**.</span></span> <span data-ttu-id="f045c-116">Fare clic su **Cambia** per modificare il server visualizzato nella casella **Server di riproduzione** .</span><span class="sxs-lookup"><span data-stu-id="f045c-116">Click **Change** to change the server displayed in the **Replay server** box.</span></span>  
  
4.  <span data-ttu-id="f045c-117">È facoltativamente possibile selezionare una delle destinazioni seguenti in cui salvare la riproduzione:</span><span class="sxs-lookup"><span data-stu-id="f045c-117">Optionally, select one of the following destinations in which to save the replay:</span></span>  
  
    -   <span data-ttu-id="f045c-118">**Salva nel file**che consente di specificare un file in cui salvare la riproduzione.</span><span class="sxs-lookup"><span data-stu-id="f045c-118">**Save to file**, which specifies a file in which to save the replay.</span></span>  
  
    -   <span data-ttu-id="f045c-119">**Salva nella tabella**che consente di specificare una tabella di database in cui salvare la riproduzione.</span><span class="sxs-lookup"><span data-stu-id="f045c-119">**Save to table**, which specifies a database table in which to save the replay.</span></span>  
  
5.  <span data-ttu-id="f045c-120">Selezionare **Riproduci gli eventi nell'ordine in cui sono stati inseriti nella traccia**oppure **Riproduci gli eventi usando più thread**.</span><span class="sxs-lookup"><span data-stu-id="f045c-120">Choose either **Replay the events in the order they were traced**or **Replay events using multiple threads**.</span></span> <span data-ttu-id="f045c-121">Nella tabella seguente viene spiegata la differenza tra queste impostazioni.</span><span class="sxs-lookup"><span data-stu-id="f045c-121">The following table explains the difference between these settings.</span></span>  
  
    |<span data-ttu-id="f045c-122">Opzione</span><span class="sxs-lookup"><span data-stu-id="f045c-122">Option</span></span>|<span data-ttu-id="f045c-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f045c-123">Description</span></span>|  
    |------------|-----------------|  
    |<span data-ttu-id="f045c-124">**Riproduci gli eventi nell'ordine in cui sono stati inseriti nella traccia**</span><span class="sxs-lookup"><span data-stu-id="f045c-124">**Replay events in the order they were traced**</span></span>|<span data-ttu-id="f045c-125">Gli eventi vengono riprodotti nell'ordine in cui sono stati inseriti nella traccia.</span><span class="sxs-lookup"><span data-stu-id="f045c-125">Replays events in the order they were recorded.</span></span> <span data-ttu-id="f045c-126">Questa opzione consente il debug.</span><span class="sxs-lookup"><span data-stu-id="f045c-126">This option enables debugging.</span></span>|  
    |<span data-ttu-id="f045c-127">**Riproduci gli eventi usando più thread**</span><span class="sxs-lookup"><span data-stu-id="f045c-127">**Replay events using multiple threads**</span></span>|<span data-ttu-id="f045c-128">Vengono utilizzati più thread per riprodurre i vari eventi, indipendentemente dalla sequenza.</span><span class="sxs-lookup"><span data-stu-id="f045c-128">This option uses multiple threads to replay each event regardless of the sequence.</span></span> <span data-ttu-id="f045c-129">Questa opzione consente di ottimizzare le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="f045c-129">This option optimizes performance.</span></span>|  
  
6.  <span data-ttu-id="f045c-130">Selezionare **Visualizza risultati di riproduzione** per visualizzare la riproduzione quando si verifica.</span><span class="sxs-lookup"><span data-stu-id="f045c-130">Select **Display replay results** to view the replay as it occurs.</span></span>  
  
7.  <span data-ttu-id="f045c-131">Se si vuole, è possibile fare clic sulla scheda **Opzioni avanzate di riproduzione**per configurare le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f045c-131">Optionally click the **Advanced Replay Options**tab to configure the following options:</span></span>  
  
    -   <span data-ttu-id="f045c-132">Per riprodurre tutti gli ID dei processi server (SPID), selezionare **Riproduci SPID di sistema**.</span><span class="sxs-lookup"><span data-stu-id="f045c-132">To replay all server process IDs (SPIDs), select **Replay system SPIDs**.</span></span>  
  
    -   <span data-ttu-id="f045c-133">Per limitare la riproduzione ai processi appartenenti a uno specifico SPID, selezionare **Riproduci un solo SPID**.</span><span class="sxs-lookup"><span data-stu-id="f045c-133">To limit the replay to processes belonging to a specific SPID, select **Replay one SPID only**.</span></span> <span data-ttu-id="f045c-134">Digitare lo SPID nella casella **SPID da riprodurre** .</span><span class="sxs-lookup"><span data-stu-id="f045c-134">In the **SPID to replay** box, type the SPID.</span></span>  
  
    -   <span data-ttu-id="f045c-135">Per riprodurre gli eventi che si sono verificati in un determinato periodo di tempo, selezionare **Limite di tempo per la riproduzione**.</span><span class="sxs-lookup"><span data-stu-id="f045c-135">To replay events that occurred during a specific time period, select **Limit the replay by date and time**.</span></span> <span data-ttu-id="f045c-136">Impostare i valori di data e ora in **Ora inizio**e **Ora fine**per specificare il periodo di tempo da includere nella riproduzione.</span><span class="sxs-lookup"><span data-stu-id="f045c-136">Select a date and time for the **Start time**and **End time**to specify the time period to include in the replay.</span></span>  
  
    -   <span data-ttu-id="f045c-137">Per controllare la modalità di gestione dei processi da parte di SQL Server durante la riproduzione, configurare le **Opzioni Health Monitor**.</span><span class="sxs-lookup"><span data-stu-id="f045c-137">To control how SQL Server manages processes during replay, configure **Health Monitor Options**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f045c-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f045c-138">See Also</span></span>  
 <span data-ttu-id="f045c-139">[Autorizzazioni necessarie per l'esecuzione di SQL Server Profiler](sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="f045c-139">[Permissions Required to Run SQL Server Profiler](sql-server-profiler.md) </span></span>  
 <span data-ttu-id="f045c-140">[Riprodurre le tracce](replay-traces.md) </span><span class="sxs-lookup"><span data-stu-id="f045c-140">[Replay Traces](replay-traces.md) </span></span>  
 <span data-ttu-id="f045c-141">[Aprire un file di traccia &#40;SQL Server Profiler&#41;](open-a-trace-file-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="f045c-141">[Open a Trace File &#40;SQL Server Profiler&#41;](open-a-trace-file-sql-server-profiler.md) </span></span>  
 [<span data-ttu-id="f045c-142">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="f045c-142">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
