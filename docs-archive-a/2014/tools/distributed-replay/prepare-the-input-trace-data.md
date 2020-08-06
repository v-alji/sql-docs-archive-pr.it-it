---
title: Preparare i dati di traccia di input | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
ms.assetid: c14fd3d2-5770-47c2-a851-cc13ddbc9bf5
author: stevestein
ms.author: sstein
ms.openlocfilehash: c13dddcf29f93940fa4eae6b2849dcfb278ae3b6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719254"
---
# <a name="prepare-the-input-trace-data"></a><span data-ttu-id="5c24a-102">Preparazione dei dati di traccia di input</span><span class="sxs-lookup"><span data-stu-id="5c24a-102">Prepare the Input Trace Data</span></span>
  <span data-ttu-id="5c24a-103">Prima di avviare una riesecuzione distribuita con la funzionalità Riesecuzione distribuita di [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], è necessario preparare i dati di traccia di input avviando la fase di pre-elaborazione dallo strumento di amministrazione Riesecuzione distribuita.</span><span class="sxs-lookup"><span data-stu-id="5c24a-103">Before you can start a distributed replay with the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Distributed Replay feature, you must prepare the input trace data by initiating the preprocess stage from the distributed replay administration tool.</span></span> <span data-ttu-id="5c24a-104">Nella fase di pre-elaborazione Distributed Replay Controller elabora i dati di traccia e genera un file intermedio:</span><span class="sxs-lookup"><span data-stu-id="5c24a-104">In the preprocess stage, the distributed replay controller processes the trace data and generates an intermediate file:</span></span>  
  
 <span data-ttu-id="5c24a-105">![Fase di pre-elaborazione di Riesecuzione distribuita](../../database-engine/media/preprocess.gif "Fase di pre-elaborazione di Riesecuzione distribuita")</span><span class="sxs-lookup"><span data-stu-id="5c24a-105">![Distributed replay preprocess stage](../../database-engine/media/preprocess.gif "Distributed replay preprocess stage")</span></span>  
  
 <span data-ttu-id="5c24a-106">Per altre informazioni sulla fase di pre-elaborazione, vedere [Riesecuzione distribuita di SQL Server](sql-server-distributed-replay.md).</span><span class="sxs-lookup"><span data-stu-id="5c24a-106">For more information about the preprocess stage, see [SQL Server Distributed Replay](sql-server-distributed-replay.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5c24a-107">È necessario acquisire i dati di traccia di input in una versione di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] compatibile con Distributed Replay.</span><span class="sxs-lookup"><span data-stu-id="5c24a-107">The input trace data must be captured in a version of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that is compatible with Distributed Replay.</span></span> <span data-ttu-id="5c24a-108">I dati di traccia di input devono essere compatibili anche con il server di destinazione su cui si desidera riprodurre i dati di traccia.</span><span class="sxs-lookup"><span data-stu-id="5c24a-108">The input trace data must also be compatible with the target server that you want to replay the trace data against.</span></span> <span data-ttu-id="5c24a-109">Per altre informazioni sui requisiti relativi alla versione, vedere [Requisiti relativi a Riesecuzione distribuita](distributed-replay-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5c24a-109">For more information about version requirements, see [Distributed Replay Requirements](distributed-replay-requirements.md).</span></span>  
  
### <a name="to-prepare-the-input-trace-data"></a><span data-ttu-id="5c24a-110">Per preparare i dati di traccia di input</span><span class="sxs-lookup"><span data-stu-id="5c24a-110">To prepare the input trace data</span></span>  
  
1.  <span data-ttu-id="5c24a-111">**(Facoltativo) Modificare le impostazioni di configurazione della pre-elaborazione**: se si vogliono modificare le impostazioni di configurazione della pre-elaborazione, ad esempio se filtrare o meno le sessioni di sistema o configurare il tempo di inattività massimo, è necessario modificare l'elemento `<PreprocessModifiers>` del file XML di configurazione della pre-elaborazione `DReplay.exe.preprocess.config`.</span><span class="sxs-lookup"><span data-stu-id="5c24a-111">**(Optional) Modify preprocess configuration settings**: If you want to modify the preprocess configuration settings, such as whether to filter system sessions or to configure the maximum idle time, you must modify the `<PreprocessModifiers>` element of the XML-based preprocess configuration file, `DReplay.exe.preprocess.config`.</span></span> <span data-ttu-id="5c24a-112">Se si modifica il file di configurazione della pre-elaborazione, è consigliabile modificarne una copia anziché l'originale.</span><span class="sxs-lookup"><span data-stu-id="5c24a-112">If you modify the preprocess configuration file, we recommend that you modify a copy rather than the original.</span></span> <span data-ttu-id="5c24a-113">Per modificare le impostazioni, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5c24a-113">To modify settings, follow these steps:</span></span>  
  
    1.  <span data-ttu-id="5c24a-114">Creare una copia del file di configurazione della pre-elaborazione predefinito `DReplay.exe.preprocess.config`e rinominare il nuovo file.</span><span class="sxs-lookup"><span data-stu-id="5c24a-114">Make a copy of the default preprocess configuration file, `DReplay.exe.preprocess.config`, and rename the new file.</span></span> <span data-ttu-id="5c24a-115">Il file di configurazione della pre-elaborazione predefinito si trova nella cartella di installazione dello strumento di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="5c24a-115">The default preprocess configuration file is located in the administration tool installation folder.</span></span>  
  
    2.  <span data-ttu-id="5c24a-116">Modificare le impostazioni di configurazione della pre-elaborazione nel nuovo file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="5c24a-116">Modify the preprocess configuration settings in the new configuration file.</span></span>  
  
    3.  <span data-ttu-id="5c24a-117">Quando si avvia la fase di pre-elaborazione dell'evento (fase successiva), usare il parametro *config_file* dell'opzione **preprocess** per specificare il percorso del file di configurazione modificato.</span><span class="sxs-lookup"><span data-stu-id="5c24a-117">When initiating the preprocess stage (the next step), use the *config_file* parameter of the **preprocess** option to specify the location of the modified configuration file.</span></span>  
  
     <span data-ttu-id="5c24a-118">Per altre informazioni sul file di configurazione della pre-elaborazione, vedere [Configurare Riesecuzione distribuita](configure-distributed-replay.md).</span><span class="sxs-lookup"><span data-stu-id="5c24a-118">For more information about the preprocess configuration file, see [Configure Distributed Replay](configure-distributed-replay.md).</span></span>  
  
2.  <span data-ttu-id="5c24a-119">**Avviare la fase di pre-elaborazione**: per preparare i dati di traccia di input, è necessario eseguire lo strumento di amministrazione con l'opzione **preprocess**.</span><span class="sxs-lookup"><span data-stu-id="5c24a-119">**Initiate the preprocess stage**: To prepare the input trace data, you must run the administration tool with the **preprocess** option.</span></span> <span data-ttu-id="5c24a-120">Per altre informazioni, vedere [Opzione preprocess &#40;strumento di amministrazione Riesecuzione distribuita&#41;](preprocess-option-distributed-replay-administration-tool.md).</span><span class="sxs-lookup"><span data-stu-id="5c24a-120">For more information, see [Preprocess Option &#40;Distributed Replay Administration Tool&#41;](preprocess-option-distributed-replay-administration-tool.md).</span></span>  
  
    1.  <span data-ttu-id="5c24a-121">Aprire l'utilità del prompt dei comandi di Windows (`CMD.exe`) e passare al percorso di installazione dello strumento di amministrazione di Distributed Replay (`DReplay.exe`).</span><span class="sxs-lookup"><span data-stu-id="5c24a-121">Open the Windows Command Prompt utility (`CMD.exe`), and navigate to the installation location of the Distributed Replay administration tool (`DReplay.exe`).</span></span>  
  
    2.  <span data-ttu-id="5c24a-122">(Facoltativo) Usare il parametro *controller* , **-m**, per specificare il controller, se il servizio controller viene eseguito in un computer diverso dallo strumento di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="5c24a-122">(Optional) Use the *controller* parameter, **-m**, to specify the controller, if the controller service is running on a computer different from the administration tool.</span></span>  
  
    3.  <span data-ttu-id="5c24a-123">Usare il parametro *input_trace_file* con **-i**per specificare il percorso e il nome dei file di traccia di input.</span><span class="sxs-lookup"><span data-stu-id="5c24a-123">Use the *input_trace_file* parameter, **-i**, to specify the location and name of the input trace files.</span></span>  
  
    4.  <span data-ttu-id="5c24a-124">Usare il parametro *controller_working_directory* con **-d**per specificare il percorso nel controller in cui salvare il file intermedio.</span><span class="sxs-lookup"><span data-stu-id="5c24a-124">Use the *controller_working_directory* parameter, **-d**, to specify where the intermediate file should be saved on the controller.</span></span>  
  
    5.  <span data-ttu-id="5c24a-125">Facoltativo: usare il parametro *config_file* con **-c**per specificare il percorso del file di configurazione della pre-elaborazione.</span><span class="sxs-lookup"><span data-stu-id="5c24a-125">(Optional) Use the *config_file* parameter, **-c**, to specify location of the preprocess configuration file.</span></span> <span data-ttu-id="5c24a-126">Utilizzare questo parametro per puntare al nuovo file di configurazione se è stata modificata una copia del file di configurazione della pre-elaborazione predefinito.</span><span class="sxs-lookup"><span data-stu-id="5c24a-126">Use this parameter to point to the new configuration file if you have modified a copy of the default preprocess configuration file.</span></span>  
  
    6.  <span data-ttu-id="5c24a-127">(Facoltativo) Usare il parametro *status_interval* con **-f**per specificare se si vuole che lo strumento di amministrazione visualizzi messaggi di stato a una frequenza diversa da 30 secondi.</span><span class="sxs-lookup"><span data-stu-id="5c24a-127">(Optional) Use the *status_interval* parameter, **-f**, to specify if you want the administration tool to display status messages at a frequency different than 30 seconds.</span></span>  
  
     <span data-ttu-id="5c24a-128">Avviando, ad esempio, la fase di pre-elaborazione nello stesso computer del servizio controller per un file di traccia in `c:\trace1.trc`, una directory di lavoro del controller in `c:\WorkingDir` e un messaggio di stato visualizzato con una frequenza predefinita pari a 30 secondi, è necessario usare la sintassi seguente: `dreplay preprocess -i c:\trace1.trc -d c:\WorkingDir`</span><span class="sxs-lookup"><span data-stu-id="5c24a-128">For example, initiating the preprocess stage on the same computer as the controller service, for a trace file located at `c:\trace1.trc`, a controller working directory located at `c:\WorkingDir` , and a status message displayed at the default value of 30 seconds, requires the syntax: `dreplay preprocess -i c:\trace1.trc -d c:\WorkingDir`</span></span>  
  
3.  <span data-ttu-id="5c24a-129">Al termine della fase di pre-elaborazione, il file intermedio viene archiviato nella directory di lavoro del controller.</span><span class="sxs-lookup"><span data-stu-id="5c24a-129">After the preprocess stage is complete, the intermediate file is stored in the controller working directory.</span></span> <span data-ttu-id="5c24a-130">Per avviare la fase di riproduzione dell'evento, è necessario eseguire lo strumento di amministrazione con l'opzione **replay** .</span><span class="sxs-lookup"><span data-stu-id="5c24a-130">To initiate the event replay stage, you must run the administration tool with the **replay** option.</span></span> <span data-ttu-id="5c24a-131">Per altre informazioni, vedere [Riprodurre dati di traccia](replay-trace-data.md).</span><span class="sxs-lookup"><span data-stu-id="5c24a-131">For more information, see [Replay Trace Data](replay-trace-data.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c24a-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5c24a-132">See Also</span></span>  
 <span data-ttu-id="5c24a-133">[SQL Server Distributed Replay](sql-server-distributed-replay.md) </span><span class="sxs-lookup"><span data-stu-id="5c24a-133">[SQL Server Distributed Replay](sql-server-distributed-replay.md) </span></span>  
 <span data-ttu-id="5c24a-134">[Requisiti relativi a Riesecuzione distribuita](distributed-replay-requirements.md) </span><span class="sxs-lookup"><span data-stu-id="5c24a-134">[Distributed Replay Requirements](distributed-replay-requirements.md) </span></span>  
 <span data-ttu-id="5c24a-135">[Opzioni della riga di comando dello strumento di amministrazione &#40;Distributed Replay Utility&#41;](administration-tool-command-line-options-distributed-replay-utility.md) </span><span class="sxs-lookup"><span data-stu-id="5c24a-135">[Administration Tool Command-line Options &#40;Distributed Replay Utility&#41;](administration-tool-command-line-options-distributed-replay-utility.md) </span></span>  
 [<span data-ttu-id="5c24a-136">Configurare Riesecuzione distribuita</span><span class="sxs-lookup"><span data-stu-id="5c24a-136">Configure Distributed Replay</span></span>](configure-distributed-replay.md)  
  
  