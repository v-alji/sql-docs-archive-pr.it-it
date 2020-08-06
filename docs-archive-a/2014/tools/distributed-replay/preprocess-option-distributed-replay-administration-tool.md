---
title: Opzione preprocess (strumento di amministrazione Riesecuzione distribuita) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
ms.assetid: 9b5012fd-233e-4a25-a2e1-585c63b70502
author: stevestein
ms.author: sstein
ms.openlocfilehash: e7f168d45b03473d958e202bd75116f4519d2fc4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626436"
---
# <a name="preprocess-option-distributed-replay-administration-tool"></a><span data-ttu-id="87b3a-102">Opzione preprocess (strumento di amministrazione Distributed Replay)</span><span class="sxs-lookup"><span data-stu-id="87b3a-102">Preprocess Option (Distributed Replay Administration Tool)</span></span>
  <span data-ttu-id="87b3a-103">Lo [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] strumento di amministrazione riesecuzione distribuita, `DReplay.exe` , è uno strumento da riga di comando che è possibile utilizzare per comunicare con il controller di riesecuzione distribuita.</span><span class="sxs-lookup"><span data-stu-id="87b3a-103">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay administration tool, `DReplay.exe`, is a command-line tool that you can use to communicate with the distributed replay controller.</span></span> <span data-ttu-id="87b3a-104">Questo argomento descrive l'opzione della riga di comando **preprocess** e la sintassi corrispondente.</span><span class="sxs-lookup"><span data-stu-id="87b3a-104">This topic describes the **preprocess** command-line option and corresponding syntax.</span></span>

 <span data-ttu-id="87b3a-105">L'opzione **preprocess** avvia la fase di pre-elaborazione.</span><span class="sxs-lookup"><span data-stu-id="87b3a-105">The **preprocess** option initiates the preprocess stage.</span></span> <span data-ttu-id="87b3a-106">Durante questa fase il controller prepara i dati di traccia di input per la riproduzione sul server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="87b3a-106">During this stage, the controller prepares the input trace data for replay against the target server.</span></span>

 <span data-ttu-id="87b3a-107">![Icona di collegamento all'argomento](../../database-engine/media/topic-link.gif "Icona di collegamento a un argomento") Per altre informazioni sulle convenzioni relative alla sintassi dello strumento di amministrazione, vedere [Convenzioni della sintassi Transact-SQL &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/transact-sql-syntax-conventions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="87b3a-107">![Topic link icon](../../database-engine/media/topic-link.gif "Topic link icon") For more information about the syntax conventions that are used with the administration tool syntax, see [Transact-SQL Syntax Conventions &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/transact-sql-syntax-conventions-transact-sql).</span></span>

## <a name="syntax"></a><span data-ttu-id="87b3a-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="87b3a-108">Syntax</span></span>

```

      dreplay preprocess [-mcontroller] -iinput_trace_file
    -dcontroller_working_dir [-cconfig_file] [-fstatus_interval]
```

#### <a name="parameters"></a><span data-ttu-id="87b3a-109">Parametri</span><span class="sxs-lookup"><span data-stu-id="87b3a-109">Parameters</span></span>
 <span data-ttu-id="87b3a-110">**-m** *controller* specifica il nome computer del controller.</span><span class="sxs-lookup"><span data-stu-id="87b3a-110">**-m** *controller* Specifies the computer name of the controller.</span></span> <span data-ttu-id="87b3a-111">È possibile utilizzare "`localhost`" o "`.`" per fare riferimento al computer locale.</span><span class="sxs-lookup"><span data-stu-id="87b3a-111">You can use "`localhost`" or "`.`" to refer to the local computer.</span></span>

 <span data-ttu-id="87b3a-112">Se il parametro **-m** non è specificato, viene usato il computer locale.</span><span class="sxs-lookup"><span data-stu-id="87b3a-112">If the **-m** parameter is not specified, the local computer is used.</span></span>

 <span data-ttu-id="87b3a-113">**-i** *input_trace_file* specifica il percorso completo del file di traccia di input nel controller, ad esempio `D:\Mytrace.trc` .</span><span class="sxs-lookup"><span data-stu-id="87b3a-113">**-i** *input_trace_file* Specifies the full path of the input trace file on the controller, such as `D:\Mytrace.trc`.</span></span> <span data-ttu-id="87b3a-114">Il parametro **-i** è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="87b3a-114">The **-i** parameter is required.</span></span>

 <span data-ttu-id="87b3a-115">Se nella stessa directory sono presenti file di rollover, questi verranno caricati e utilizzati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="87b3a-115">If there are rollover files in the same directory, they will be loaded and used automatically.</span></span> <span data-ttu-id="87b3a-116">I file devono rispettare la convenzione di denominazione per il rollover dei file, ad esempio `Mytrace.trc`, `Mytrace_1.trc`, `Mytrace_2.trc`, `Mytrace_3.trc`, ... `Mytrace_n.trc`.</span><span class="sxs-lookup"><span data-stu-id="87b3a-116">The files must follow the file rollover naming convention, for example: `Mytrace.trc`, `Mytrace_1.trc`, `Mytrace_2.trc`, `Mytrace_3.trc`, ... `Mytrace_n.trc`.</span></span>

> [!NOTE]
>  <span data-ttu-id="87b3a-117">Se si utilizza lo strumento di amministrazione in un computer diverso dal controller, sarà necessario copiare i file di traccia di input nel controller in modo da poter utilizzare un percorso locale per questo parametro.</span><span class="sxs-lookup"><span data-stu-id="87b3a-117">If you are using the administration tool on a different computer than the controller, you will need to copy the input trace files to the controller so that a local path can be used for this parameter.</span></span>

 <span data-ttu-id="87b3a-118">**-d** *controller_working_dir* specifica la directory nel controller in cui verrà archiviato il file intermedio.</span><span class="sxs-lookup"><span data-stu-id="87b3a-118">**-d** *controller_working_dir* Specifies the directory on the controller where the intermediate file will be stored.</span></span> <span data-ttu-id="87b3a-119">Il parametro **-d** è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="87b3a-119">The **-d** parameter is required.</span></span>

 <span data-ttu-id="87b3a-120">Di seguito vengono indicati i requisiti per questo parametro:</span><span class="sxs-lookup"><span data-stu-id="87b3a-120">The following requirements apply:</span></span>

-   <span data-ttu-id="87b3a-121">La directory deve trovarsi nel controller.</span><span class="sxs-lookup"><span data-stu-id="87b3a-121">The directory must reside on the controller.</span></span>

-   <span data-ttu-id="87b3a-122">È necessario specificare il percorso completo, che inizia con una lettera di unità, ad esempio `c:\WorkingDir`.</span><span class="sxs-lookup"><span data-stu-id="87b3a-122">You must specify the full path, starting with a drive letter (for example, `c:\WorkingDir`).</span></span>

-   <span data-ttu-id="87b3a-123">Il percorso non deve terminare con una barra rovesciata "`\`".</span><span class="sxs-lookup"><span data-stu-id="87b3a-123">The path must not end with a backslash "`\`".</span></span>

-   <span data-ttu-id="87b3a-124">I percorsi UNC non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="87b3a-124">UNC paths are not supported.</span></span>

 <span data-ttu-id="87b3a-125">**-c** *CONFIG_FILE* è il percorso completo del file di configurazione della pre-elaborazione; utilizzato per specificare il percorso del file di configurazione della pre-elaborazione quando viene archiviato in un percorso diverso.</span><span class="sxs-lookup"><span data-stu-id="87b3a-125">**-c** *config_file* Is the full path of the preprocess configuration file; used to specify the location of the preprocess configuration file when stored in a different location.</span></span> <span data-ttu-id="87b3a-126">Questo parametro può essere un percorso UNC o un percorso locale nel computer in cui viene eseguito lo strumento di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="87b3a-126">This parameter can be a UNC path, or can reside locally on the computer where you run the administration tool.</span></span>

 <span data-ttu-id="87b3a-127">Il parametro **-c** non è obbligatorio se non è necessario applicare filtri o non si vuole modificare il tempo massimo di inattività.</span><span class="sxs-lookup"><span data-stu-id="87b3a-127">The **-c** parameter is not required if no filtering is needed, or if you do not want to modify the maximum idle time.</span></span>

 <span data-ttu-id="87b3a-128">Senza il parametro **-c** , viene usato il file di configurazione della pre-elaborazione predefinito, ovvero `DReplay.exe.preprocess.config`.</span><span class="sxs-lookup"><span data-stu-id="87b3a-128">Without the **-c** parameter, the default preprocess configuration file, `DReplay.exe.preprocess.config`, is used.</span></span>

 <span data-ttu-id="87b3a-129">**-f** *status_interval* specifica la frequenza (in secondi) in cui visualizzare i messaggi di stato.</span><span class="sxs-lookup"><span data-stu-id="87b3a-129">**-f** *status_interval* Specifies the frequency (in seconds) at which to display status messages.</span></span>

 <span data-ttu-id="87b3a-130">Se **-f** non è specificato, l'intervallo predefinito è 30 secondi.</span><span class="sxs-lookup"><span data-stu-id="87b3a-130">If **-f** is not specified, the default interval is 30 seconds.</span></span>

## <a name="examples"></a><span data-ttu-id="87b3a-131">Esempi</span><span class="sxs-lookup"><span data-stu-id="87b3a-131">Examples</span></span>
 <span data-ttu-id="87b3a-132">In questo esempio la fase di pre-elaborazione viene avviata con tutte le impostazioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="87b3a-132">In this example, the preprocess stage is initiated with all of the default settings.</span></span> <span data-ttu-id="87b3a-133">Il valore `localhost` indica che il servizio controller viene eseguito nello stesso computer dello strumento di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="87b3a-133">The value `localhost` indicates that the controller service is running on the same computer as the administration tool.</span></span> <span data-ttu-id="87b3a-134">Il parametro *input_trace_file* specifica il percorso dei dati di traccia di input, ad esempio `c:\mytrace.trc`.</span><span class="sxs-lookup"><span data-stu-id="87b3a-134">The *input_trace_file* parameter specifies the location of the input trace data, `c:\mytrace.trc`.</span></span> <span data-ttu-id="87b3a-135">Il file di traccia non viene filtrato, quindi è necessario specificare il parametro **-c** .</span><span class="sxs-lookup"><span data-stu-id="87b3a-135">Because there is no trace file filtering involved, the **-c** parameter does have to be specified.</span></span>

```
dreplay preprocess -m localhost -i c:\mytrace.trc -d c:\WorkingDir
```

 <span data-ttu-id="87b3a-136">In questo esempio viene avviata la fase di pre-elaborazione e viene specificato un file di configurazione della pre-elaborazione modificato.</span><span class="sxs-lookup"><span data-stu-id="87b3a-136">In this example, the preprocess stage is initiated and a modified preprocess configuration file is specified.</span></span> <span data-ttu-id="87b3a-137">A differenza dell'esempio precedente, il parametro **-c** viene usato per puntare al file di configurazione modificato, se è stato archiviato in un percorso diverso.</span><span class="sxs-lookup"><span data-stu-id="87b3a-137">Unlike the previous example, the **-c** parameter is used to point to the modified configuration file, if you have stored it in a different location.</span></span> <span data-ttu-id="87b3a-138">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="87b3a-138">For example:</span></span>

```
dreplay preprocess -m localhost -i c:\mytrace.trc -d c:\WorkingDir -c c:\DReplay.exe.preprocess.config
```

 <span data-ttu-id="87b3a-139">Nel file di configurazione della pre-elaborazione modificato, viene aggiunta una condizione di filtro per filtrare le sessioni di sistema durante la riproduzione distribuita.</span><span class="sxs-lookup"><span data-stu-id="87b3a-139">In the modified preprocess configuration file, a filter condition is added that filters out system sessions during distributed replay.</span></span> <span data-ttu-id="87b3a-140">Il filtro viene aggiunto modificando l'elemento `<PreprocessModifiers>` nel file di configurazione della pre-elaborazione `DReplay.exe.preprocess.config`.</span><span class="sxs-lookup"><span data-stu-id="87b3a-140">The filter is added by modifying the `<PreprocessModifiers>` element in the preprocess configuration file, `DReplay.exe.preprocess.config`.</span></span>

 <span data-ttu-id="87b3a-141">Nell'esempio seguente viene illustrato un file di configurazione modificato:</span><span class="sxs-lookup"><span data-stu-id="87b3a-141">The following shows an example of the modified configuration file:</span></span>

```
<?xml version='1.0'?>
<Options>
    <PreprocessModifiers>
        <IncSystemSession>No</IncSystemSession>
        <MaxIdleTime>-1</MaxIdleTime>
    </PreprocessModifiers>
</Options>
```

## <a name="permissions"></a><span data-ttu-id="87b3a-142">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="87b3a-142">Permissions</span></span>
 <span data-ttu-id="87b3a-143">È necessario eseguire lo strumento di amministrazione come utente interattivo, scegliendo tra utente locale e account utente di dominio.</span><span class="sxs-lookup"><span data-stu-id="87b3a-143">You must run the administration tool as an interactive user, as either a local user or a domain user account.</span></span> <span data-ttu-id="87b3a-144">Per utilizzare un account utente locale, lo strumento di amministrazione e il controller devono essere eseguiti nello stesso computer.</span><span class="sxs-lookup"><span data-stu-id="87b3a-144">To use a local user account, the administration tool and controller must be running on the same computer.</span></span>

 <span data-ttu-id="87b3a-145">Per altre informazioni, vedere [Sicurezza di Distributed Replay](distributed-replay-security.md).</span><span class="sxs-lookup"><span data-stu-id="87b3a-145">For more information, see [Distributed Replay Security](distributed-replay-security.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="87b3a-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="87b3a-146">See Also</span></span>
 <span data-ttu-id="87b3a-147">[Preparare i dati di traccia di Input](prepare-the-input-trace-data.md) [SQL Server riesecuzione distribuita](sql-server-distributed-replay.md) [configurare riesecuzione distribuita](configure-distributed-replay.md)</span><span class="sxs-lookup"><span data-stu-id="87b3a-147">[Prepare the Input Trace Data](prepare-the-input-trace-data.md) [SQL Server Distributed Replay](sql-server-distributed-replay.md) [Configure Distributed Replay](configure-distributed-replay.md)</span></span>


