---
title: Opzione replay (strumento di amministrazione Riesecuzione distribuita) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
ms.assetid: d7bce6a5-d414-488d-a3cd-50c1c62019c4
author: stevestein
ms.author: sstein
ms.openlocfilehash: a3114d7c2a2a7908e4e010fbf5d80c7d332d264c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724308"
---
# <a name="replay-option-distributed-replay-administration-tool"></a><span data-ttu-id="37a20-102">Opzione replay (strumento di amministrazione Distributed Replay)</span><span class="sxs-lookup"><span data-stu-id="37a20-102">Replay Option (Distributed Replay Administration Tool)</span></span>
  <span data-ttu-id="37a20-103">Lo [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] strumento di amministrazione riesecuzione distribuita, `DReplay.exe` , è uno strumento da riga di comando che è possibile utilizzare per comunicare con il controller di riesecuzione distribuita.</span><span class="sxs-lookup"><span data-stu-id="37a20-103">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Distributed Replay administration tool, `DReplay.exe`, is a command-line tool that you can use to communicate with the distributed replay controller.</span></span> <span data-ttu-id="37a20-104">Questo argomento descrive l'opzione della riga di comando **replay** e la sintassi corrispondente.</span><span class="sxs-lookup"><span data-stu-id="37a20-104">This topic describes the **replay** command-line option and corresponding syntax.</span></span>

 <span data-ttu-id="37a20-105">L'opzione **replay** avvia la fase di riproduzione dell'evento, in cui il controller recapita i dati di riproduzione ai client specificati, avvia la riesecuzione distribuita e sincronizza i client.</span><span class="sxs-lookup"><span data-stu-id="37a20-105">The **replay** option initiates the event replay stage, in which the controller dispatches replay data to the specified clients, launches the distributed replay and synchronizes the clients.</span></span> <span data-ttu-id="37a20-106">Ogni client che partecipa alla riproduzione può eventualmente registrare l'attività di riproduzione e salvare in locale un file di traccia dei risultati.</span><span class="sxs-lookup"><span data-stu-id="37a20-106">Optionally, each client participating in the replay can record the replay activity and save a result trace file locally.</span></span>

 <span data-ttu-id="37a20-107">![Icona di collegamento all'argomento](../../database-engine/media/topic-link.gif "Icona di collegamento a un argomento") Per altre informazioni sulle convenzioni relative alla sintassi dello strumento di amministrazione, vedere [Convenzioni della sintassi Transact-SQL &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/transact-sql-syntax-conventions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="37a20-107">![Topic link icon](../../database-engine/media/topic-link.gif "Topic link icon") For more information about the syntax conventions that are used with the administration tool syntax, see [Transact-SQL Syntax Conventions &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/transact-sql-syntax-conventions-transact-sql).</span></span>

## <a name="syntax"></a><span data-ttu-id="37a20-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="37a20-108">Syntax</span></span>

```

      dreplay replay [-mcontroller] -dcontroller_working_dir [-o]
    [-starget_server] -wclients [-cconfig_file]
    [-fstatus_interval]
```

#### <a name="parameters"></a><span data-ttu-id="37a20-109">Parametri</span><span class="sxs-lookup"><span data-stu-id="37a20-109">Parameters</span></span>
 <span data-ttu-id="37a20-110">**-m** *controller* specifica il nome computer del controller.</span><span class="sxs-lookup"><span data-stu-id="37a20-110">**-m** *controller* Specifies the computer name of the controller.</span></span> <span data-ttu-id="37a20-111">È possibile utilizzare "`localhost`" o "`.`" per fare riferimento al computer locale.</span><span class="sxs-lookup"><span data-stu-id="37a20-111">You can use "`localhost`" or "`.`" to refer to the local computer.</span></span>

 <span data-ttu-id="37a20-112">Se il parametro **-m** non è specificato, viene usato il computer locale.</span><span class="sxs-lookup"><span data-stu-id="37a20-112">If the **-m** parameter is not specified, the local computer is used.</span></span>

 <span data-ttu-id="37a20-113">**-d** *controller_working_dir* specifica la directory nel controller in cui verrà archiviato il file intermedio.</span><span class="sxs-lookup"><span data-stu-id="37a20-113">**-d** *controller_working_dir* Specifies the directory on the controller where the intermediate file will be stored.</span></span> <span data-ttu-id="37a20-114">Il parametro **-d** è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="37a20-114">The **-d** parameter is required.</span></span>

 <span data-ttu-id="37a20-115">Di seguito vengono indicati i requisiti per questo parametro:</span><span class="sxs-lookup"><span data-stu-id="37a20-115">The following requirements apply:</span></span>

-   <span data-ttu-id="37a20-116">La directory deve trovarsi nel controller.</span><span class="sxs-lookup"><span data-stu-id="37a20-116">The directory must reside on the controller.</span></span>

-   <span data-ttu-id="37a20-117">È necessario specificare il percorso completo, che inizia con una lettera di unità, ad esempio `c:\WorkingDir`.</span><span class="sxs-lookup"><span data-stu-id="37a20-117">You must specify the full path, starting with a drive letter (for example, `c:\WorkingDir`).</span></span>

-   <span data-ttu-id="37a20-118">Il percorso non deve terminare con una barra rovesciata "`\`".</span><span class="sxs-lookup"><span data-stu-id="37a20-118">The path must not end with a backslash "`\`".</span></span>

-   <span data-ttu-id="37a20-119">I percorsi UNC non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="37a20-119">UNC paths are not supported.</span></span>

 <span data-ttu-id="37a20-120">**-o** Acquisisce l'attività di riproduzione dei client e la Salva in un file di traccia dei risultati nel percorso specificato dall' `<ResultDirectory>` elemento nel file di configurazione del client, `DReplayClient.xml` .</span><span class="sxs-lookup"><span data-stu-id="37a20-120">**-o** Captures the clients' replay activity and saves it to a result trace file in the path specified by the `<ResultDirectory>` element in the client configuration file, `DReplayClient.xml`.</span></span>

 <span data-ttu-id="37a20-121">Quando il parametro **-o** non è specificato, il file di traccia dei risultati non viene generato.</span><span class="sxs-lookup"><span data-stu-id="37a20-121">When the **-o** parameter is not specified, the result trace file is not generated.</span></span> <span data-ttu-id="37a20-122">L'output della console restituisce informazioni di riepilogo al termine della riproduzione, ma non sono disponibili altre statistiche di riproduzione.</span><span class="sxs-lookup"><span data-stu-id="37a20-122">The console output returns summary information at the end of replay, but no other replay statistics are available.</span></span>

 <span data-ttu-id="37a20-123">**-s** *target_server* specifica l'istanza di destinazione di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] su cui deve essere riprodotto il carico di lavoro distribuito.</span><span class="sxs-lookup"><span data-stu-id="37a20-123">**-s** *target_server* Specifies the target instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that the distributed workload should be replayed against.</span></span> <span data-ttu-id="37a20-124">È necessario specificare questo parametro nel formato **nome_server[\nome istanza]** .</span><span class="sxs-lookup"><span data-stu-id="37a20-124">You must specify this parameter in the format **server_name[\instance name]**.</span></span>

 <span data-ttu-id="37a20-125">Non è possibile utilizzare "`localhost`" o "`.`" come server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="37a20-125">You cannot use "`localhost`" or "`.`" as the target server.</span></span>

 <span data-ttu-id="37a20-126">Il parametro **-s** non è obbligatorio se si specifica l'elemento `<Server>` nella sezione `<ReplayOptions>` del file di configurazione della riproduzione `DReplay.exe.replay.config`.</span><span class="sxs-lookup"><span data-stu-id="37a20-126">The **-s** parameter is not required if the `<Server>` element is specified in the `<ReplayOptions>` section of the replay configuration file, `DReplay.exe.replay.config`.</span></span>

 <span data-ttu-id="37a20-127">Se si usa il parametro **-s** , l'elemento `<Server>` nella sezione `<ReplayOptions>` del file di configurazione della riproduzione viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="37a20-127">If the **-s** parameter is used, the `<Server>` element in the `<ReplayOptions>` section of the replay configuration file will be ignored.</span></span>

 <span data-ttu-id="37a20-128">**-w** *client* questo parametro obbligatorio è un elenco delimitato da virgole (senza spazi) che specifica i nomi computer dei client che devono partecipare alla riesecuzione distribuita.</span><span class="sxs-lookup"><span data-stu-id="37a20-128">**-w** *clients* This required parameter is a comma-separated list (without spaces) that specifies the computer names of clients that should participate in the distributed replay.</span></span> <span data-ttu-id="37a20-129">Gli indirizzi IP non sono consentiti.</span><span class="sxs-lookup"><span data-stu-id="37a20-129">IP addresses are not allowed.</span></span> <span data-ttu-id="37a20-130">Tenere presente che i client devono essere già registrati nel controller.</span><span class="sxs-lookup"><span data-stu-id="37a20-130">Be aware that the clients must already be registered with the controller.</span></span>

> [!NOTE]
>  <span data-ttu-id="37a20-131">Ogni client viene registrato nel controller specificato nel file di configurazione del client all'avvio del servizio client.</span><span class="sxs-lookup"><span data-stu-id="37a20-131">Each client registers with the controller that is specified in the client configuration file when the client service starts.</span></span>

 <span data-ttu-id="37a20-132">**-c** *CONFIG_FILE* è il percorso completo del file di configurazione della riproduzione. utilizzato per specificare il percorso in cui viene archiviato in un percorso diverso.</span><span class="sxs-lookup"><span data-stu-id="37a20-132">**-c** *config_file* Is the full path of the replay configuration file; used to specify the location when it is stored in a different location.</span></span>

 <span data-ttu-id="37a20-133">Il parametro **-c** non è obbligatorio se si vuole usare i valori predefiniti del file di configurazione della riproduzione `DReplay.exe.replay.config`.</span><span class="sxs-lookup"><span data-stu-id="37a20-133">The **-c** parameter is not required if you want to use the default values of the replay configuration file, `DReplay.exe.replay.config`.</span></span>

 <span data-ttu-id="37a20-134">**-f** *status_interval* specifica la frequenza (in secondi) in cui visualizzare lo stato.</span><span class="sxs-lookup"><span data-stu-id="37a20-134">**-f** *status_interval* Specifies the frequency (in seconds) at which to display the status.</span></span>

 <span data-ttu-id="37a20-135">Se **-f** non è specificato, l'intervallo predefinito è 30 secondi.</span><span class="sxs-lookup"><span data-stu-id="37a20-135">If **-f** is not specified, the default interval is 30 seconds.</span></span>

## <a name="examples"></a><span data-ttu-id="37a20-136">Esempi</span><span class="sxs-lookup"><span data-stu-id="37a20-136">Examples</span></span>
 <span data-ttu-id="37a20-137">In questo esempio il comportamento della riproduzione distribuita deriva per lo più da un file di configurazione della riproduzione modificato, denominato `DReplay.exe.replay.config`.</span><span class="sxs-lookup"><span data-stu-id="37a20-137">In this example, the distributed replay derives much of its behavior from a modified replay configuration file, `DReplay.exe.replay.config`.</span></span>

-   <span data-ttu-id="37a20-138">Il parametro **-m** specifica che un computer denominato `controller1` funge da controller.</span><span class="sxs-lookup"><span data-stu-id="37a20-138">The **-m** parameter specifies that a computer named `controller1` acts as the controller.</span></span> <span data-ttu-id="37a20-139">È necessario specificare il nome computer quando il servizio controller viene eseguito in un computer diverso.</span><span class="sxs-lookup"><span data-stu-id="37a20-139">The computer name must be specified when the controller service is running on a different computer.</span></span>

-   <span data-ttu-id="37a20-140">Il parametro **-d** specifica il percorso del file intermedio nel controller, `c:\WorkingDir`.</span><span class="sxs-lookup"><span data-stu-id="37a20-140">The **-d** parameter specifies the location of the intermediate file on the controller, `c:\WorkingDir`.</span></span>

-   <span data-ttu-id="37a20-141">Il parametro **-o** indica che ogni client specificato acquisisce l'attività di riproduzione e la salva in un file di traccia dei risultati.</span><span class="sxs-lookup"><span data-stu-id="37a20-141">The **-o** parameter specifies that each specified client capture the replay activity and save it to a result trace file.</span></span> <span data-ttu-id="37a20-142">Nota: è possibile usare l'elemento `<ResultTrace>` nel file di configurazione per specificare se registrare il conteggio delle righe e il set di risultati.</span><span class="sxs-lookup"><span data-stu-id="37a20-142">Note: The `<ResultTrace>` element in the configuration file can be used to specify if row count and result set be recorded.</span></span>

-   <span data-ttu-id="37a20-143">Il parametro **-w** specifica che i computer compresi tra `client1` e `client4` partecipano come client alla riesecuzione distribuita.</span><span class="sxs-lookup"><span data-stu-id="37a20-143">The **-w** parameter specifies that computers `client1` through `client4` participate as clients in the distributed replay.</span></span>

-   <span data-ttu-id="37a20-144">Il parametro **-c** viene usato per puntare al file di configurazione modificato `DReplay.exe.replay.config`.</span><span class="sxs-lookup"><span data-stu-id="37a20-144">The **-c** parameter is used to point to the modified configuration file, `DReplay.exe.replay.config`.</span></span>

-   <span data-ttu-id="37a20-145">Il parametro **-s** non è obbligatorio perché è stato specificato l'elemento `<Server>` nell'elemento `<ReplayOptions>` del file di configurazione della riproduzione `DReplay.exe.replay.config`.</span><span class="sxs-lookup"><span data-stu-id="37a20-145">The **-s** parameter is not required because the `<Server>` element is specified in the `<ReplayOptions>` element of the replay configuration file, `DReplay.exe.replay.config`.</span></span>

 <span data-ttu-id="37a20-146">La fase di riproduzione dell'evento viene avviata con la sintassi seguente quando lo strumento di amministrazione viene eseguito da un computer diverso dal controller:</span><span class="sxs-lookup"><span data-stu-id="37a20-146">The event replay stage is initiated with the following syntax, when the administration tool is run from a different computer than the controller:</span></span>

```
dreplay replay -m controller1 -d c:\WorkingDir -o -w client1,client2,client3,client4 -c c:\DReplay.exe.replay.config
```

 <span data-ttu-id="37a20-147">Per specificare una modalità di sequenza sincrona, l'elemento `<SequencingMode>` del file `DReplay.exe.replay.config` viene impostato su un valore uguale al valore `synchronization`.</span><span class="sxs-lookup"><span data-stu-id="37a20-147">To specify a synchronous sequencing mode, the `<SequencingMode>` element of the `DReplay.exe.replay.config` file is set equal to the value `synchronization`.</span></span> <span data-ttu-id="37a20-148">La sezione `<ResultTrace>` del file di configurazione della riproduzione viene modificata per specificare la registrazione del conteggio delle righe.</span><span class="sxs-lookup"><span data-stu-id="37a20-148">The `<ResultTrace>` section of the replay configuration file is modified to specify that row count be recorded.</span></span> <span data-ttu-id="37a20-149">Queste modifiche vengono illustrate nell'esempio XML seguente.</span><span class="sxs-lookup"><span data-stu-id="37a20-149">These changes are shown in the following XML example:</span></span>

```
<?xml version='1.0'?>
<Options>
    <ReplayOptions>
        <Server>server_name\replay_target_instance</Server>
        <SequencingMode>synchronization</SequencingMode>
        <ConnectTimeScale></ConnectTimeScale>
        <ThinkTimeScale></ThinkTimeScale>
        <HealthmonInterval>60</HealthmonInterval>
        <QueryTimeout>3600</QueryTimeout>
        <ThreadsPerClient></ThreadsPerClient>
    </ReplayOptions>
    <OutputOptions>
        <ResultTrace>
            <RecordRowCount>Yes</RecordRowCount>
            <RecordResultSet>No</RecordResultSet>
        </ResultTrace>
    </OutputOptions>
</Options>
```

 <span data-ttu-id="37a20-150">Per specificare una modalità di sequenza di stress, l'elemento `<SequencingMode>` del file `DReplay.exe.replay.config` viene impostato su un valore uguale al valore `stress`.</span><span class="sxs-lookup"><span data-stu-id="37a20-150">To specify a stress sequencing mode, the `<SequencingMode>` element of the `DReplay.exe.replay.config` file is set equal to the value `stress`.</span></span> <span data-ttu-id="37a20-151">Gli elementi `<ConnectTimeScale>` e `<ThinkTimeScale>` vengono impostati sul valore `50` , per specificare 50%.</span><span class="sxs-lookup"><span data-stu-id="37a20-151">The `<ConnectTimeScale>` and `<ThinkTimeScale>` elements are set to the value `50` (to specify 50 percent).</span></span> <span data-ttu-id="37a20-152">Per altre informazioni sul tempo di connessione e il tempo interazione utente, vedere [Configurare Distributed Replay](configure-distributed-replay.md).</span><span class="sxs-lookup"><span data-stu-id="37a20-152">For more information about connect time and think time, see [Configure Distributed Replay](configure-distributed-replay.md).</span></span> <span data-ttu-id="37a20-153">Queste modifiche vengono illustrate nell'esempio XML seguente.</span><span class="sxs-lookup"><span data-stu-id="37a20-153">These changes are shown in the following XML example:</span></span>

```
<?xml version='1.0'?>
<Options>
    <ReplayOptions>
        <Server>server_name\replay_target_instance_name</Server>
        <SequencingMode>stress</SequencingMode>
        <ConnectTimeScale>50</ConnectTimeScale>
        <ThinkTimeScale>50</ThinkTimeScale>
        <HealthmonInterval>60</HealthmonInterval>
        <QueryTimeout>3600</QueryTimeout>
        <ThreadsPerClient></ThreadsPerClient>
    </ReplayOptions>
    <OutputOptions>
        <ResultTrace>
            <RecordRowCount>Yes</RecordRowCount>
            <RecordResultSet>No</RecordResultSet>
        </ResultTrace>
    </OutputOptions>
</Options>
```

## <a name="permissions"></a><span data-ttu-id="37a20-154">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="37a20-154">Permissions</span></span>
 <span data-ttu-id="37a20-155">È necessario eseguire lo strumento di amministrazione come utente interattivo, scegliendo tra utente locale e account utente di dominio.</span><span class="sxs-lookup"><span data-stu-id="37a20-155">You must run the administration tool as an interactive user, as either a local user or a domain user account.</span></span> <span data-ttu-id="37a20-156">Per utilizzare un account utente locale, lo strumento di amministrazione e il controller devono essere eseguiti nello stesso computer.</span><span class="sxs-lookup"><span data-stu-id="37a20-156">To use a local user account, the administration tool and controller must be running on the same computer.</span></span>

 <span data-ttu-id="37a20-157">Per altre informazioni, vedere [Sicurezza di Distributed Replay](distributed-replay-security.md).</span><span class="sxs-lookup"><span data-stu-id="37a20-157">For more information, see [Distributed Replay Security](distributed-replay-security.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="37a20-158">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="37a20-158">See Also</span></span>
 <span data-ttu-id="37a20-159">[Riprodurre i dati di traccia](replay-trace-data.md) [esaminare i risultati della riproduzione](review-the-replay-results.md) [SQL Server Riesecuzione distribuita](sql-server-distributed-replay.md) [configurare riesecuzione distribuita](configure-distributed-replay.md) [SQL Server Forum riesecuzione distribuita](https://social.technet.microsoft.com/Forums/sl/sqldru/) [con riesecuzione distribuita per eseguire il test di carico del SQL Server parte 2](https://docs.microsoft.com/archive/blogs/msdn/mspfe/using-distributed-replay-to-load-test-your-sql-serverpart-2) [usando riesecuzione distribuita per eseguire il test di carico del SQL Server-parte 1](https://docs.microsoft.com/archive/blogs/batuhanyildiz/using-distributed-replay-to-load-test-your-sql-serverpart-1)</span><span class="sxs-lookup"><span data-stu-id="37a20-159">[Replay Trace Data](replay-trace-data.md) [Review the Replay Results](review-the-replay-results.md) [SQL Server Distributed Replay](sql-server-distributed-replay.md) [Configure Distributed Replay](configure-distributed-replay.md) [SQL Server Distributed Replay Forum](https://social.technet.microsoft.com/Forums/sl/sqldru/) [Using Distributed Replay to Load Test Your SQL Server - Part 2](https://docs.microsoft.com/archive/blogs/msdn/mspfe/using-distributed-replay-to-load-test-your-sql-serverpart-2) [Using Distributed Replay to Load Test Your SQL Server - Part 1](https://docs.microsoft.com/archive/blogs/batuhanyildiz/using-distributed-replay-to-load-test-your-sql-serverpart-1)</span></span>


