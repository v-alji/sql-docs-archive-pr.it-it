---
title: Requisiti di Riesecuzione distribuita | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: 6fffee7d-891f-4d9d-b2c3-dd19855a1c2c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 66be93534756360e722fcccaf405815e14ffa7ee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628030"
---
# <a name="distributed-replay-requirements"></a><span data-ttu-id="51ad8-102">Requisiti relativi a Riesecuzione distribuita</span><span class="sxs-lookup"><span data-stu-id="51ad8-102">Distributed Replay Requirements</span></span>
  <span data-ttu-id="51ad8-103">Prima di usare la funzionalità Riesecuzione distribuita di [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , esaminare i requisiti del prodotto indicati in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="51ad8-103">Before using the [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay feature, consider the product requirements that are outlined in this topic.</span></span>  
  
## <a name="input-trace-requirements"></a><span data-ttu-id="51ad8-104">Requisiti della traccia di input</span><span class="sxs-lookup"><span data-stu-id="51ad8-104">Input Trace Requirements</span></span>  
 <span data-ttu-id="51ad8-105">Affinché possano essere riprodotti correttamente, i dati di traccia devono soddisfare i requisiti per la versione e il formato e contenere le colonne e gli eventi necessari.</span><span class="sxs-lookup"><span data-stu-id="51ad8-105">To successfully replay trace data, it must meet the requirements for version and format, and contain the required events and columns.</span></span>  
  
### <a name="input-trace-versions"></a><span data-ttu-id="51ad8-106">Versioni della traccia di input</span><span class="sxs-lookup"><span data-stu-id="51ad8-106">Input Trace Versions</span></span>  
 <span data-ttu-id="51ad8-107">Riesecuzione distribuita supporta dati di traccia di input raccolti nelle versioni di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]seguenti:</span><span class="sxs-lookup"><span data-stu-id="51ad8-107">Distributed Replay supports input trace data that is collected on the following versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
-   [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]  
  
-   [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]  
  
-   [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]  
  
-   [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]  
  
-   [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]  
  
### <a name="input-trace-formats"></a><span data-ttu-id="51ad8-108">Formati della traccia di input</span><span class="sxs-lookup"><span data-stu-id="51ad8-108">Input Trace Formats</span></span>  
 <span data-ttu-id="51ad8-109">I dati di traccia di input possono utilizzare uno dei formati seguenti:</span><span class="sxs-lookup"><span data-stu-id="51ad8-109">The input trace data can be in any of the following formats:</span></span>  
  
-   <span data-ttu-id="51ad8-110">Singolo file di traccia con estensione `.trc` .</span><span class="sxs-lookup"><span data-stu-id="51ad8-110">A single trace file that has the `.trc` extension.</span></span>  
  
-   <span data-ttu-id="51ad8-111">Set di file di traccia di rollover che rispettano la convenzione di denominazione per il rollover dei file, ad esempio `<TraceFile>.trc`, `<TraceFile>_1.trc`, `<TraceFile>_2.trc`, `<TraceFile>_3.trc`, ... `<TraceFile>_n.trc`.</span><span class="sxs-lookup"><span data-stu-id="51ad8-111">A set of rollover trace files that follow the file rollover naming convention, for example: `<TraceFile>.trc`, `<TraceFile>_1.trc`, `<TraceFile>_2.trc`, `<TraceFile>_3.trc`, ... `<TraceFile>_n.trc`.</span></span>  
  
### <a name="input-trace-events-and-columns"></a><span data-ttu-id="51ad8-112">Eventi e colonne della traccia di input</span><span class="sxs-lookup"><span data-stu-id="51ad8-112">Input Trace Events and Columns</span></span>  
 <span data-ttu-id="51ad8-113">I dati di traccia di input devono contenere colonne ed eventi specifici, che devono essere rieseguiti da Riesecuzione distribuita.</span><span class="sxs-lookup"><span data-stu-id="51ad8-113">The input trace data must contain specific events and columns to be replayed by Distributed Replay.</span></span> <span data-ttu-id="51ad8-114">Il modello **TSQL_Replay** in [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] contiene tutte le colonne e tutti gli eventi necessari, oltre a informazioni aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="51ad8-114">The **TSQL_Replay** template in [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] contains all of the required events and columns, in addition to extra information.</span></span> <span data-ttu-id="51ad8-115">Per altre informazioni sul modello, vedere [Requisiti per la riproduzione](../sql-server-profiler/replay-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="51ad8-115">For more information about that template, see [Replay Requirements](../sql-server-profiler/replay-requirements.md).</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="51ad8-116">Se non si usa il modello **TSQL_Replay** per acquisire i dati di traccia di input o se i requisiti della traccia di input non sono soddisfatti, è possibile che si verifichino risultati di riproduzione imprevisti.</span><span class="sxs-lookup"><span data-stu-id="51ad8-116">If you do not use the **TSQL_Replay** template to capture the input trace data, or if the input trace requirements are not satisfied, you may receive unexpected replay results.</span></span>  
  
 <span data-ttu-id="51ad8-117">È inoltre possibile creare un modello di traccia personalizzato e utilizzarlo per riprodurre eventi con Riesecuzione distribuita, purché contenga gli eventi seguenti:</span><span class="sxs-lookup"><span data-stu-id="51ad8-117">You can also create a custom trace template and use it to replay events with Distributed Replay, as long as it contains the following events:</span></span>  
  
-   <span data-ttu-id="51ad8-118">Connessione di controllo</span><span class="sxs-lookup"><span data-stu-id="51ad8-118">Audit Login</span></span>  
  
-   <span data-ttu-id="51ad8-119">Disconnessione di controllo</span><span class="sxs-lookup"><span data-stu-id="51ad8-119">Audit Logout</span></span>  
  
-   <span data-ttu-id="51ad8-120">ExistingConnection</span><span class="sxs-lookup"><span data-stu-id="51ad8-120">ExistingConnection</span></span>  
  
-   <span data-ttu-id="51ad8-121">RPC Output Parameter</span><span class="sxs-lookup"><span data-stu-id="51ad8-121">RPC Output Parameter</span></span>  
  
-   <span data-ttu-id="51ad8-122">RPC:Completed</span><span class="sxs-lookup"><span data-stu-id="51ad8-122">RPC:Completed</span></span>  
  
-   <span data-ttu-id="51ad8-123">RPC:Starting</span><span class="sxs-lookup"><span data-stu-id="51ad8-123">RPC:Starting</span></span>  
  
-   <span data-ttu-id="51ad8-124">SQL:BatchCompleted</span><span class="sxs-lookup"><span data-stu-id="51ad8-124">SQL:BatchCompleted</span></span>  
  
-   <span data-ttu-id="51ad8-125">SQL:BatchStarting</span><span class="sxs-lookup"><span data-stu-id="51ad8-125">SQL:BatchStarting</span></span>  
  
 <span data-ttu-id="51ad8-126">Se si riproducono cursori sul lato server, sono necessari anche gli eventi seguenti:</span><span class="sxs-lookup"><span data-stu-id="51ad8-126">If you are replaying server-side cursors, the following events are also required:</span></span>  
  
-   <span data-ttu-id="51ad8-127">CursorClose</span><span class="sxs-lookup"><span data-stu-id="51ad8-127">CursorClose</span></span>  
  
-   <span data-ttu-id="51ad8-128">CursorExecute</span><span class="sxs-lookup"><span data-stu-id="51ad8-128">CursorExecute</span></span>  
  
-   <span data-ttu-id="51ad8-129">CursorOpen</span><span class="sxs-lookup"><span data-stu-id="51ad8-129">CursorOpen</span></span>  
  
-   <span data-ttu-id="51ad8-130">CursorPrepare</span><span class="sxs-lookup"><span data-stu-id="51ad8-130">CursorPrepare</span></span>  
  
-   <span data-ttu-id="51ad8-131">CursorUnprepare</span><span class="sxs-lookup"><span data-stu-id="51ad8-131">CursorUnprepare</span></span>  
  
 <span data-ttu-id="51ad8-132">Se si riproducono istruzioni SQL preparate sul lato server, sono necessari anche gli eventi seguenti:</span><span class="sxs-lookup"><span data-stu-id="51ad8-132">If you are replaying server-side prepared SQL statements, the following events are also required:</span></span>  
  
-   <span data-ttu-id="51ad8-133">Exec Prepared SQL</span><span class="sxs-lookup"><span data-stu-id="51ad8-133">Exec Prepared SQL</span></span>  
  
-   <span data-ttu-id="51ad8-134">Prepare SQL</span><span class="sxs-lookup"><span data-stu-id="51ad8-134">Prepare SQL</span></span>  
  
 <span data-ttu-id="51ad8-135">Tutti i dati di traccia di input devono contenere le colonne seguenti:</span><span class="sxs-lookup"><span data-stu-id="51ad8-135">All input trace data must contain the following columns:</span></span>  
  
-   <span data-ttu-id="51ad8-136">Event Class</span><span class="sxs-lookup"><span data-stu-id="51ad8-136">Event Class</span></span>  
  
-   <span data-ttu-id="51ad8-137">EventSequence</span><span class="sxs-lookup"><span data-stu-id="51ad8-137">EventSequence</span></span>  
  
-   <span data-ttu-id="51ad8-138">TextData</span><span class="sxs-lookup"><span data-stu-id="51ad8-138">TextData</span></span>  
  
-   <span data-ttu-id="51ad8-139">Nome dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="51ad8-139">Application Name</span></span>  
  
-   <span data-ttu-id="51ad8-140">LoginName</span><span class="sxs-lookup"><span data-stu-id="51ad8-140">LoginName</span></span>  
  
-   <span data-ttu-id="51ad8-141">DatabaseName</span><span class="sxs-lookup"><span data-stu-id="51ad8-141">DatabaseName</span></span>  
  
-   <span data-ttu-id="51ad8-142">ID database</span><span class="sxs-lookup"><span data-stu-id="51ad8-142">Database ID</span></span>  
  
-   <span data-ttu-id="51ad8-143">HostName</span><span class="sxs-lookup"><span data-stu-id="51ad8-143">HostName</span></span>  
  
-   <span data-ttu-id="51ad8-144">Binary Data</span><span class="sxs-lookup"><span data-stu-id="51ad8-144">Binary Data</span></span>  
  
-   <span data-ttu-id="51ad8-145">SPID</span><span class="sxs-lookup"><span data-stu-id="51ad8-145">SPID</span></span>  
  
-   <span data-ttu-id="51ad8-146">Ora di Inizio</span><span class="sxs-lookup"><span data-stu-id="51ad8-146">Start Time</span></span>  
  
-   <span data-ttu-id="51ad8-147">EndTime</span><span class="sxs-lookup"><span data-stu-id="51ad8-147">EndTime</span></span>  
  
-   <span data-ttu-id="51ad8-148">IsSystem</span><span class="sxs-lookup"><span data-stu-id="51ad8-148">IsSystem</span></span>  
  
## <a name="supported-input-trace-and-target-server-combinations"></a><span data-ttu-id="51ad8-149">Combinazioni di traccia di input e server di destinazione supportate</span><span class="sxs-lookup"><span data-stu-id="51ad8-149">Supported Input Trace and Target Server Combinations</span></span>  
 <span data-ttu-id="51ad8-150">Nella tabella seguente sono elencate le versioni supportate dei dati di traccia e, per ciascuna di esse, sono indicate le versioni supportate di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] su cui è possibile riprodurre i dati.</span><span class="sxs-lookup"><span data-stu-id="51ad8-150">The following table lists the supported versions of trace data, and for each, the supported versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that data can be replayed against.</span></span>  
  
|<span data-ttu-id="51ad8-151">Versione dei dati di traccia di input</span><span class="sxs-lookup"><span data-stu-id="51ad8-151">Version of Input Trace Data</span></span>|<span data-ttu-id="51ad8-152">Versioni supportate di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per l'istanza del server di destinazione</span><span class="sxs-lookup"><span data-stu-id="51ad8-152">Supported Versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] for the Target Server Instance</span></span>|  
|---------------------------------|------------------------------------------------------------------------------------|  
|[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]|[!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]<span data-ttu-id="51ad8-153">, [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51ad8-153">, [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span></span>|  
|[!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]|[!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]<span data-ttu-id="51ad8-154">, [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51ad8-154">, [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span></span>|  
|[!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]|[!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]<span data-ttu-id="51ad8-155">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51ad8-155">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span></span>|  
|[!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]|[!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]<span data-ttu-id="51ad8-156">, [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51ad8-156">, [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span></span>|  
|[!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]|[!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]|  
  
## <a name="operating-system-requirements"></a><span data-ttu-id="51ad8-157">Requisiti del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="51ad8-157">Operating System Requirements</span></span>  
 <span data-ttu-id="51ad8-158">I sistemi operativi supportati per l'esecuzione dello strumento di amministrazione e dei servizi client e del controller sono gli stessi dell'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="51ad8-158">Supported operating systems for running the administration tool and the controller and client services is the same as your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="51ad8-159">Per ulteriori informazioni sui sistemi operativi supportati per l'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , vedere [requisiti hardware e software per l'installazione di SQL Server 2014](../../sql-server/install/hardware-and-software-requirements-for-installing-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="51ad8-159">For more information about which operating systems are supported for your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance, see [Hardware and Software Requirements for Installing SQL Server 2014](../../sql-server/install/hardware-and-software-requirements-for-installing-sql-server.md).</span></span>  
  
 <span data-ttu-id="51ad8-160">Le funzionalità di Riesecuzione distribuita sono supportate sia in sistemi operativi x86 che x64.</span><span class="sxs-lookup"><span data-stu-id="51ad8-160">Distributed Replay features are supported on both x86-based and x64-based operating systems.</span></span> <span data-ttu-id="51ad8-161">Per i sistemi operativi basati su x64, è supportata solo la modalità Windows on Windows (WOW).</span><span class="sxs-lookup"><span data-stu-id="51ad8-161">For x64-based operating systems, only Windows on Windows (WOW) mode is supported.</span></span>  
  
## <a name="installation-limitations"></a><span data-ttu-id="51ad8-162">Limitazioni relative all'installazione</span><span class="sxs-lookup"><span data-stu-id="51ad8-162">Installation Limitations</span></span>  
 <span data-ttu-id="51ad8-163">In ogni computer può essere installata una sola istanza di ogni funzionalità di Riesecuzione distribuita.</span><span class="sxs-lookup"><span data-stu-id="51ad8-163">Any one computer can only have a single instance of each Distributed Replay feature installed.</span></span> <span data-ttu-id="51ad8-164">Nella tabella seguente viene indicato il numero di installazioni consentito per ogni funzionalità in un singolo ambiente di Riesecuzione distribuita.</span><span class="sxs-lookup"><span data-stu-id="51ad8-164">The following table lists how many installations of each feature are allowed in a single Distributed Replay environment.</span></span>  
  
|<span data-ttu-id="51ad8-165">Funzionalità di Riesecuzione distribuita</span><span class="sxs-lookup"><span data-stu-id="51ad8-165">Distributed Replay Feature</span></span>|<span data-ttu-id="51ad8-166">Numero massimo di installazioni per ambiente di riproduzione</span><span class="sxs-lookup"><span data-stu-id="51ad8-166">Maximum Installations Per Replay Environment</span></span>|  
|--------------------------------|--------------------------------------------------|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="51ad8-167">Servizio controller di Riesecuzione distribuita</span><span class="sxs-lookup"><span data-stu-id="51ad8-167">Distributed Replay controller service</span></span>|<span data-ttu-id="51ad8-168">1</span><span class="sxs-lookup"><span data-stu-id="51ad8-168">1</span></span>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="51ad8-169">Servizio client Riesecuzione distribuita</span><span class="sxs-lookup"><span data-stu-id="51ad8-169">Distributed Replay client service</span></span>|<span data-ttu-id="51ad8-170">16 (computer fisici o virtuali)</span><span class="sxs-lookup"><span data-stu-id="51ad8-170">16 (physical or virtual computers)</span></span>|  
|<span data-ttu-id="51ad8-171">Strumento di amministrazione</span><span class="sxs-lookup"><span data-stu-id="51ad8-171">Administration tool</span></span>|<span data-ttu-id="51ad8-172">Nessuna limitazione</span><span class="sxs-lookup"><span data-stu-id="51ad8-172">Unlimited</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="51ad8-173">Benché sia possibile installare solo un'istanza dello strumento di amministrazione in ogni computer, è possibile avviare più istanze dello strumento di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="51ad8-173">Although only one instance of the administration tool can be installed on a single computer, you can start multiple instances of the administration tool.</span></span> <span data-ttu-id="51ad8-174">I comandi eseguiti da più strumenti di amministrazione vengono risolti in base all'ordine di ricezione.</span><span class="sxs-lookup"><span data-stu-id="51ad8-174">Commands issued from multiple administration tools are resolved in the order in which they are received.</span></span>  
  
## <a name="data-access-provider"></a><span data-ttu-id="51ad8-175">Provider di accesso ai dati</span><span class="sxs-lookup"><span data-stu-id="51ad8-175">Data Access Provider</span></span>  
 <span data-ttu-id="51ad8-176">Riesecuzione distribuita supporta solo il provider di accesso ai dati ODBC di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="51ad8-176">Distributed Replay only supports the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC data access provider.</span></span>  
  
## <a name="target-server-preparation-requirements"></a><span data-ttu-id="51ad8-177">Requisiti di preparazione del server di destinazione</span><span class="sxs-lookup"><span data-stu-id="51ad8-177">Target Server Preparation Requirements</span></span>  
 <span data-ttu-id="51ad8-178">È consigliabile posizionare il server di destinazione in un ambiente di testing.</span><span class="sxs-lookup"><span data-stu-id="51ad8-178">We recommend that the target server be located in a test environment.</span></span> <span data-ttu-id="51ad8-179">Per riprodurre dati di traccia su un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] diversa rispetto a quella in cui sono stati registrati in origine, verificare che nel server di destinazione siano state effettuate le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="51ad8-179">To replay trace data against a different instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] than it was originally recorded, make sure that the following has been done to the target server:</span></span>  
  
-   <span data-ttu-id="51ad8-180">Tutti gli account di accesso e gli utenti contenuti nei dati di traccia devono essere presenti nello stesso database nel server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="51ad8-180">All logins and users that are contained in the trace data must be present in the same database on the target server.</span></span>  
  
-   <span data-ttu-id="51ad8-181">Tutti gli account di accesso e gli utenti presenti nel server di destinazione devono disporre delle stesse autorizzazioni di cui disponevano nel server originale.</span><span class="sxs-lookup"><span data-stu-id="51ad8-181">All logins and users on the target server must have the same permissions they had on the original server.</span></span>  
  
-   <span data-ttu-id="51ad8-182">È consigliabile che gli ID di database nella destinazione e nell'origine siano uguali.</span><span class="sxs-lookup"><span data-stu-id="51ad8-182">The database IDs on the target ideally should be the same as those on the source.</span></span> <span data-ttu-id="51ad8-183">In caso contrario, tuttavia, è possibile trovare una corrispondenza in base a **DatabaseName** , se presente nella traccia.</span><span class="sxs-lookup"><span data-stu-id="51ad8-183">However, if they are not the same, matching can be performed based on **DatabaseName** if it is present in the trace.</span></span>  
  
-   <span data-ttu-id="51ad8-184">Il database predefinito per ogni account di accesso contenuto nei dati di traccia deve essere impostato (nel server di destinazione) sul rispettivo database di destinazione dell'account di accesso.</span><span class="sxs-lookup"><span data-stu-id="51ad8-184">The default database for each login that is contained in the trace data must be set (on the target server) to the respective target database of the login.</span></span> <span data-ttu-id="51ad8-185">Si supponga, ad esempio, che i dati di traccia da riprodurre contengano attività per l'account di accesso **Fred**nel database **Fred_Db** nell'istanza originale di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="51ad8-185">For example, the trace data to be replayed contains activity for the login, **Fred**, in the database **Fred_Db** on the original instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="51ad8-186">Di conseguenza, nel server di destinazione il database predefinito per l'account di accesso **Fred**deve essere impostato sul database corrispondente a **Fred_Db** , anche se il nome del database è diverso.</span><span class="sxs-lookup"><span data-stu-id="51ad8-186">Therefore, on the target server, the default database for the login, **Fred**, must be set to the database that matches **Fred_Db** (even if the database name is different).</span></span> <span data-ttu-id="51ad8-187">Per impostare il database predefinito dell'account di accesso, utilizzare la stored procedure di sistema `sp_defaultdb` .</span><span class="sxs-lookup"><span data-stu-id="51ad8-187">To set the default database of the login, use the `sp_defaultdb` system stored procedure.</span></span>  
  
 <span data-ttu-id="51ad8-188">La riproduzione degli eventi associati ad account di accesso mancanti o non corretti genera errori di riproduzione, ma l'operazione non viene interrotta.</span><span class="sxs-lookup"><span data-stu-id="51ad8-188">Replaying events associated with missing or incorrect logins results in replay errors, but the replay operation continues.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51ad8-189">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="51ad8-189">See Also</span></span>  
 <span data-ttu-id="51ad8-190">[SQL Server Distributed Replay](sql-server-distributed-replay.md) </span><span class="sxs-lookup"><span data-stu-id="51ad8-190">[SQL Server Distributed Replay](sql-server-distributed-replay.md) </span></span>  
 <span data-ttu-id="51ad8-191">[Sicurezza Riesecuzione distribuita](distributed-replay-security.md) </span><span class="sxs-lookup"><span data-stu-id="51ad8-191">[Distributed Replay Security](distributed-replay-security.md) </span></span>  
 [<span data-ttu-id="51ad8-192">Installare Riesecuzione distribuita</span><span class="sxs-lookup"><span data-stu-id="51ad8-192">Install Distributed Replay</span></span>](install-distributed-replay-overview.md)  
  
  
