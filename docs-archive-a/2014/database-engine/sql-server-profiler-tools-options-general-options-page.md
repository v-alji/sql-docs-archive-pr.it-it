---
title: SQL Server Profiler-Tools-Options (pagina Opzioni generali) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.pro.replay.tools.generaloptions.f1
helpviewer_keywords:
- General Options dialog box
ms.assetid: a888246d-ccfe-415f-bbdc-d6adafac250a
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: fad4d3529482835367898276a973bd7c8827b553
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635195"
---
# <a name="sql-server-profiler---tools-options-general-options-page"></a><span data-ttu-id="00f06-102">SQL Server Profiler-Tools-Options (pagina Opzioni generali)</span><span class="sxs-lookup"><span data-stu-id="00f06-102">SQL Server Profiler - Tools-Options (General Options Page)</span></span>
  <span data-ttu-id="00f06-103">Usare la finestra di dialogo **Opzioni generali** per visualizzare o specificare le opzioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="00f06-103">Use the **General Options** dialog box to view or specify the following options.</span></span>  
  
## <a name="options"></a><span data-ttu-id="00f06-104">Opzioni</span><span class="sxs-lookup"><span data-stu-id="00f06-104">Options</span></span>  
  
### <a name="display-options"></a><span data-ttu-id="00f06-105">Opzioni di visualizzazione</span><span class="sxs-lookup"><span data-stu-id="00f06-105">Display Options</span></span>  
 <span data-ttu-id="00f06-106">**Nome carattere**</span><span class="sxs-lookup"><span data-stu-id="00f06-106">**Font name**</span></span>  
 <span data-ttu-id="00f06-107">Visualizza il nome del carattere utilizzato nella griglia dei risultati della traccia durante l'esecuzione delle tracce.</span><span class="sxs-lookup"><span data-stu-id="00f06-107">Displays the name of the font used in the trace results grid during traces.</span></span>  
  
 <span data-ttu-id="00f06-108">**Dimensioni del carattere**</span><span class="sxs-lookup"><span data-stu-id="00f06-108">**Font size**</span></span>  
 <span data-ttu-id="00f06-109">Visualizza le dimensioni del carattere utilizzato nella griglia dei risultati della traccia durante l'esecuzione delle tracce.</span><span class="sxs-lookup"><span data-stu-id="00f06-109">Displays the size of the font used in the trace results grid during traces.</span></span>  
  
 <span data-ttu-id="00f06-110">**Scegli carattere**</span><span class="sxs-lookup"><span data-stu-id="00f06-110">**Choose Font**</span></span>  
 <span data-ttu-id="00f06-111">Consente di aprire una finestra di dialogo per la modifica delle impostazioni del carattere.</span><span class="sxs-lookup"><span data-stu-id="00f06-111">Opens a dialog to change the font settings.</span></span>  
  
 <span data-ttu-id="00f06-112">**Visualizza valori di data e ora in base alle impostazioni internazionali**</span><span class="sxs-lookup"><span data-stu-id="00f06-112">**Use regional settings to display date and time values**</span></span>  
 <span data-ttu-id="00f06-113">Visualizza i valori di data e ora in base alle impostazioni internazionali configurate nel computer in uso.</span><span class="sxs-lookup"><span data-stu-id="00f06-113">Displays date and time values in regional settings configured for your computer.</span></span> <span data-ttu-id="00f06-114">Se questa opzione non viene selezionata, i valori di data e ora vengono visualizzati in base al formato predefinito utilizzato da Microsoft [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]in cui sono inclusi i millisecondi.</span><span class="sxs-lookup"><span data-stu-id="00f06-114">If you do not select this option, the date and time values are displayed in the fixed format used by Microsoft [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], which includes milliseconds.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="00f06-115">L'abilitazione o disabilitazione di questa casella di controllo consente di modificare il formato di visualizzazione delle colonne relative all'ora, ad esempio **StartTime** ed **EndTime**.</span><span class="sxs-lookup"><span data-stu-id="00f06-115">Toggling this checkbox changes the time columns display format such as **StartTime** and **EndTime**.</span></span> <span data-ttu-id="00f06-116">Tuttavia, non vengono modificati i parametri del valore **DateTime** negli eventi del linguaggio o nelle RPC (Remote Procedure Call).</span><span class="sxs-lookup"><span data-stu-id="00f06-116">However, it does not change the **DateTime** value parameters inside the language events or remote procedure calls (RPCs).</span></span>  
  
 <span data-ttu-id="00f06-117">**Mostra i valori nella colonna Durata in microsecondi**</span><span class="sxs-lookup"><span data-stu-id="00f06-117">**Show values in Duration column in microseconds**</span></span>  
 <span data-ttu-id="00f06-118">Visualizza i valori in microsecondi nella colonna di dati **Durata** delle tracce.</span><span class="sxs-lookup"><span data-stu-id="00f06-118">Displays the values in microseconds in the **Duration** data column of traces.</span></span> <span data-ttu-id="00f06-119">Per impostazione predefinita, i valori nella colonna **Durata** vengono visualizzati in millisecondi.</span><span class="sxs-lookup"><span data-stu-id="00f06-119">By default, the **Duration** column displays values in milliseconds.</span></span>  
  
### <a name="tracing-options"></a><span data-ttu-id="00f06-120">Opzioni di traccia</span><span class="sxs-lookup"><span data-stu-id="00f06-120">Tracing Options</span></span>  
 <span data-ttu-id="00f06-121">**Avvia traccia non appena viene stabilita una connessione**</span><span class="sxs-lookup"><span data-stu-id="00f06-121">**Start tracing immediately after making connection**</span></span>  
 <span data-ttu-id="00f06-122">La traccia viene avviata utilizzando il modello predefinito non appena viene stabilita una connessione.</span><span class="sxs-lookup"><span data-stu-id="00f06-122">Begin a trace using the default template as soon as a connection is made.</span></span>  
  
 <span data-ttu-id="00f06-123">**Aggiorna la definizione di traccia in caso di modifica della versione del provider**</span><span class="sxs-lookup"><span data-stu-id="00f06-123">**Update trace definition when provider version changes**</span></span>  
 <span data-ttu-id="00f06-124">Consente di applicare a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] la definizione di traccia più recente quando il provider viene aggiornato.</span><span class="sxs-lookup"><span data-stu-id="00f06-124">Apply the most current trace definition to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] when the provider is updated.</span></span> <span data-ttu-id="00f06-125">Questo elemento non è selezionato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="00f06-125">This item is not checked by default.</span></span> <span data-ttu-id="00f06-126">[!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] viene forzato a recuperare la definizione di traccia dal server e a ricreare il file su disco, se un file esiste.</span><span class="sxs-lookup"><span data-stu-id="00f06-126">This forces [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] to query the server for the trace definition and re-create, if one exists, the file on disk.</span></span>  
  
### <a name="file-rollover-options"></a><span data-ttu-id="00f06-127">Opzioni rollover file</span><span class="sxs-lookup"><span data-stu-id="00f06-127">File Rollover Options</span></span>  
 <span data-ttu-id="00f06-128">**Carica tutti i file di rollover in sequenza senza chiedere conferma**</span><span class="sxs-lookup"><span data-stu-id="00f06-128">**Load all rollover files in sequence without prompting**</span></span>  
 <span data-ttu-id="00f06-129">I file di rollover vengono caricati automaticamente all'apertura del file di traccia.</span><span class="sxs-lookup"><span data-stu-id="00f06-129">Load rollover files automatically when a trace file is opened.</span></span> <span data-ttu-id="00f06-130">Se durante la creazione della traccia sono stati creati più file, la selezione di questa opzione determina il caricamento automatico di tutti i file di rollover.</span><span class="sxs-lookup"><span data-stu-id="00f06-130">If more than one file was created while tracing, selecting this option automatically loads all rollover files.</span></span>  
  
 <span data-ttu-id="00f06-131">**Chiedi conferma prima di caricare file di rollover**</span><span class="sxs-lookup"><span data-stu-id="00f06-131">**Prompt before loading rollover files**</span></span>  
 <span data-ttu-id="00f06-132">[!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] chiede conferma prima di aggiungere un file di rollover quando è aperto un file di traccia.</span><span class="sxs-lookup"><span data-stu-id="00f06-132">Have [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] prompt you before adding a rollover file when a trace file is opened.</span></span>  
  
 <span data-ttu-id="00f06-133">**Non caricare mai file di rollover successivi**</span><span class="sxs-lookup"><span data-stu-id="00f06-133">**Never load subsequent rollover files**</span></span>  
 [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] <span data-ttu-id="00f06-134">non esegue mai il caricamento di file di rollover consecutivi quando è aperto un file di traccia.</span><span class="sxs-lookup"><span data-stu-id="00f06-134">never loads subsequent rollover files when a trace file is opened.</span></span>  
  
### <a name="replay-options"></a><span data-ttu-id="00f06-135">Opzioni di riproduzione</span><span class="sxs-lookup"><span data-stu-id="00f06-135">Replay Options</span></span>  
 <span data-ttu-id="00f06-136">**Numero predefinito di thread di riproduzione**</span><span class="sxs-lookup"><span data-stu-id="00f06-136">**Default number of replay threads**</span></span>  
 <span data-ttu-id="00f06-137">Consente di specificare il numero di thread di riproduzione da utilizzare simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="00f06-137">Specify the number of replay threads to use concurrently.</span></span> <span data-ttu-id="00f06-138">Un numero elevato determina un maggior consumo di risorse durante la riproduzione, ma migliora la simultaneità della riproduzione.</span><span class="sxs-lookup"><span data-stu-id="00f06-138">A higher number consumes more resources during replay, but increases replay concurrency.</span></span>  
  
 <span data-ttu-id="00f06-139">**Intervallo di attesa predefinito Health Monitor (sec)**</span><span class="sxs-lookup"><span data-stu-id="00f06-139">**Default health monitor wait interval (sec)**</span></span>  
 <span data-ttu-id="00f06-140">Consente di specificare l'intervallo di attesa in secondi per la riproduzione.</span><span class="sxs-lookup"><span data-stu-id="00f06-140">Specify the wait interval to replay in seconds.</span></span> <span data-ttu-id="00f06-141">Il valore predefinito è 3600 secondi (1 ora).</span><span class="sxs-lookup"><span data-stu-id="00f06-141">Default is 3600 seconds (1 hour).</span></span> <span data-ttu-id="00f06-142">Questa impostazione influisce sulla quantità di tempo durante la quale è consentita l'esecuzione di un thread prima che questo venga terminato da Health Monitor.</span><span class="sxs-lookup"><span data-stu-id="00f06-142">This setting affects the amount of time a thread is allowed to run before being terminated by the health monitor.</span></span>  
  
 <span data-ttu-id="00f06-143">**Intervallo di polling predefinito Health Monitor (sec)**</span><span class="sxs-lookup"><span data-stu-id="00f06-143">**Default health monitor poll interval (sec)**</span></span>  
 <span data-ttu-id="00f06-144">Consente di specificare l'intervallo di polling in secondi di Health Monitor durante la riproduzione.</span><span class="sxs-lookup"><span data-stu-id="00f06-144">Specify the health monitor poll interval during replay in seconds.</span></span> <span data-ttu-id="00f06-145">Il valore predefinito è 60 secondi.</span><span class="sxs-lookup"><span data-stu-id="00f06-145">Default is 60 seconds.</span></span> <span data-ttu-id="00f06-146">Questo valore consente di configurare la frequenza con cui Health Monitor esegue il polling di candidati per la terminazione.</span><span class="sxs-lookup"><span data-stu-id="00f06-146">This value allows the user to configure how often the health monitor polls for candidates for termination.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00f06-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="00f06-147">See Also</span></span>  
 <span data-ttu-id="00f06-148">[Avviare una traccia automaticamente dopo la connessione a un server &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/start-a-trace-automatically-after-connecting-to-a-server-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="00f06-148">[Start a Trace Automatically after Connecting to a Server &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/start-a-trace-automatically-after-connecting-to-a-server-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="00f06-149">[Imposta impostazioni predefinite per la visualizzazione della traccia &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/set-trace-display-defaults-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="00f06-149">[Set Trace Display Defaults &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/set-trace-display-defaults-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="00f06-150">[Riprodurre una tabella di traccia &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/replay-a-trace-table-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="00f06-150">[Replay a Trace Table &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/replay-a-trace-table-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="00f06-151">[Riprodurre un file di traccia &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/replay-a-trace-file-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="00f06-151">[Replay a Trace File &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/replay-a-trace-file-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="00f06-152">[Riproduzione di tracce](../tools/sql-server-profiler/replay-traces.md) </span><span class="sxs-lookup"><span data-stu-id="00f06-152">[Replay Traces](../tools/sql-server-profiler/replay-traces.md) </span></span>  
 <span data-ttu-id="00f06-153">[Impostare opzioni di traccia globali &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/set-global-trace-options-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="00f06-153">[Set Global Trace Options &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/set-global-trace-options-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="00f06-154">[Modelli e autorizzazioni di SQL Server Profiler](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="00f06-154">[SQL Server Profiler Templates and Permissions](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span></span>  
 [<span data-ttu-id="00f06-155">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="00f06-155">SQL Server Profiler</span></span>](../tools/sql-server-profiler/sql-server-profiler.md)  
  
  
