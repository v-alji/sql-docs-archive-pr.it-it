---
title: Visualizzare e leggere i file di log del programma di installazione di SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
helpviewer_keywords:
- viewing logs
- displaying log files
- Setup [SQL Server], logs
- installation log files [SQL Server]
- installing SQL Server, logs
- errors [SQL Server], Setup
- logs [SQL Server], Setup
ms.assetid: 9d77af64-9084-4375-908a-d90f99535062
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 70f9bbb9a8ed72503dc6fe90077232748b2c4ac2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714564"
---
# <a name="view-and-read-sql-server-setup-log-files"></a><span data-ttu-id="a23d2-102">Visualizzare e leggere i file di log del programma di installazione di SQL Server</span><span class="sxs-lookup"><span data-stu-id="a23d2-102">View and Read SQL Server Setup Log Files</span></span>
  <span data-ttu-id="a23d2-103">Ogni esecuzione del programma di installazione crea file di log con una nuova cartella dei log con timestamp in% ProgramFiles% \\ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \120\Setup Bootstrap\LOG \\ .</span><span class="sxs-lookup"><span data-stu-id="a23d2-103">Each execution of Setup creates log files are created with a new timestamped log folder at %programfiles%\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup Bootstrap\Log\\.</span></span> <span data-ttu-id="a23d2-104">Il formato del nome della cartella dei log con indicazione di data e ora è AAAAMMGG_hhmmss.</span><span class="sxs-lookup"><span data-stu-id="a23d2-104">The time-stamped log folder name format is YYYYMMDD_hhmmss.</span></span> <span data-ttu-id="a23d2-105">L'esecuzione del programma di installazione in modalità automatica determina la creazione dei file di log nel percorso % temp%\sqlsetup\*.log.</span><span class="sxs-lookup"><span data-stu-id="a23d2-105">When Setup is run in an unattended mode, the logs are created at % temp%\sqlsetup\*.log.</span></span> <span data-ttu-id="a23d2-106">Tutti i file inclusi nella cartella dei log vengono archiviati nel file Log\*.cab nella rispettiva cartella dei log.</span><span class="sxs-lookup"><span data-stu-id="a23d2-106">All files in the logs folder are archived into the Log\*.cab file in their respective log folder.</span></span>  
  
 <span data-ttu-id="a23d2-107">Una richiesta di installazione tipica viene eseguita in tre fasi:</span><span class="sxs-lookup"><span data-stu-id="a23d2-107">A typical Setup request goes through three execution phases:</span></span>  
  
1.  <span data-ttu-id="a23d2-108">Testo delle regole globali</span><span class="sxs-lookup"><span data-stu-id="a23d2-108">Global rules text</span></span>  
  
2.  <span data-ttu-id="a23d2-109">Aggiornamento del componente</span><span class="sxs-lookup"><span data-stu-id="a23d2-109">Component update</span></span>  
  
3.  <span data-ttu-id="a23d2-110">Azione richiesta dall'utente</span><span class="sxs-lookup"><span data-stu-id="a23d2-110">User-requested action</span></span>  
  
 <span data-ttu-id="a23d2-111">In ogni fase il programma di installazione genererà log di riepilogo e dettagliati e creerà log aggiuntivi in base alle necessità.</span><span class="sxs-lookup"><span data-stu-id="a23d2-111">In each phase, Setup generates detail and summary logs with additional logs created as appropriate.</span></span> <span data-ttu-id="a23d2-112">Il programma di installazione viene richiamato almeno tre volte per ogni azione di installazione richiesta dall'utente.</span><span class="sxs-lookup"><span data-stu-id="a23d2-112">Setup is called at least three times per user-requested Setup action.</span></span>  
  
 <span data-ttu-id="a23d2-113">I file dell'archivio dati contengono uno snapshot dello stato di tutti gli oggetti di configurazione registrati dal processo di installazione e contribuiscono a risolvere i problemi relativi agli errori di configurazione.</span><span class="sxs-lookup"><span data-stu-id="a23d2-113">Datastore files contain a snapshot of the state of all configuration objects being tracked by the Setup process, and are useful for troubleshooting configuration errors.</span></span> <span data-ttu-id="a23d2-114">Vengono creati file di dump XML per gli oggetti dell'archivio dati per ogni fase dell'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="a23d2-114">XML file dumps are created for datastore objects for each execution phase.</span></span> <span data-ttu-id="a23d2-115">Questi file vengono salvati nella rispettiva sottocartella dei log sotto la cartella dei log con indicazione di data e ora, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="a23d2-115">They are saved in their own log subfolder under the time-stamped log folder, as follows:</span></span>  
  
-   <span data-ttu-id="a23d2-116">Datastore_GlobalRules</span><span class="sxs-lookup"><span data-stu-id="a23d2-116">Datastore_GlobalRules</span></span>  
  
-   <span data-ttu-id="a23d2-117">Datastore_ComponentUpdated</span><span class="sxs-lookup"><span data-stu-id="a23d2-117">Datastore_ComponentUpdated</span></span>  
  
-   <span data-ttu-id="a23d2-118">Archivio dati</span><span class="sxs-lookup"><span data-stu-id="a23d2-118">Datastore</span></span>  
  
 <span data-ttu-id="a23d2-119">Nelle sezioni seguenti vengono illustrati i file di log del programma di installazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a23d2-119">The following sections describe [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup log files.</span></span>  
  
## <a name="summary-text"></a><span data-ttu-id="a23d2-120">Testo di riepilogo</span><span class="sxs-lookup"><span data-stu-id="a23d2-120">Summary Text</span></span>  
  
### <a name="overview"></a><span data-ttu-id="a23d2-121">Panoramica</span><span class="sxs-lookup"><span data-stu-id="a23d2-121">Overview</span></span>  
 <span data-ttu-id="a23d2-122">Nel file sono indicati i componenti di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] rilevati durante l'installazione, l'ambiente del sistema operativo, i valori dei parametri della riga di comando eventualmente specificati e lo stato globale di ogni MSI/MSP eseguito.</span><span class="sxs-lookup"><span data-stu-id="a23d2-122">This file shows the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] components that were detected during Setup, the operating system environment, command-line parameter values if they are specified, and the overall status of each MSI/MSP that was executed.</span></span>  
  
 <span data-ttu-id="a23d2-123">Il log è organizzato nelle sezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a23d2-123">The log is organized into the following sections:</span></span>  
  
-   <span data-ttu-id="a23d2-124">Riepilogo globale dell'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="a23d2-124">An overall summary of the execution</span></span>  
  
-   <span data-ttu-id="a23d2-125">Proprietà e configurazione del computer in cui è stato eseguito il programma di installazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a23d2-125">Properties and the configuration of the computer where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup was run</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="a23d2-126">funzionalità del prodotto installate in precedenza nel computer</span><span class="sxs-lookup"><span data-stu-id="a23d2-126">product features previously installed on the computer</span></span>  
  
-   <span data-ttu-id="a23d2-127">Descrizione delle proprietà relative alla versione dell'installazione e al pacchetto di installazione.</span><span class="sxs-lookup"><span data-stu-id="a23d2-127">Description of the installation version and installation package properties</span></span>  
  
-   <span data-ttu-id="a23d2-128">Impostazioni di input al runtime fornite durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="a23d2-128">Runtime input settings that are provided during install</span></span>  
  
-   <span data-ttu-id="a23d2-129">Percorso del file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="a23d2-129">Location of the configuration file</span></span>  
  
-   <span data-ttu-id="a23d2-130">Dettagli dei risultati di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="a23d2-130">Details of the execution results</span></span>  
  
-   <span data-ttu-id="a23d2-131">Regole globali.</span><span class="sxs-lookup"><span data-stu-id="a23d2-131">Global rules</span></span>  
  
-   <span data-ttu-id="a23d2-132">Regole specifiche per lo scenario di installazione.</span><span class="sxs-lookup"><span data-stu-id="a23d2-132">Rules specific to the installation scenario</span></span>  
  
-   <span data-ttu-id="a23d2-133">Regole non riuscite.</span><span class="sxs-lookup"><span data-stu-id="a23d2-133">Failed rules</span></span>  
  
-   <span data-ttu-id="a23d2-134">Percorso del file di report delle regole.</span><span class="sxs-lookup"><span data-stu-id="a23d2-134">Location of the rules report file</span></span>  
  
### <a name="location"></a><span data-ttu-id="a23d2-135">Location</span><span class="sxs-lookup"><span data-stu-id="a23d2-135">Location</span></span>  
 <span data-ttu-id="a23d2-136">Si trova nel percorso% ProgramFiles% \\ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \120\Setup Bootstrap\LOG \\ .</span><span class="sxs-lookup"><span data-stu-id="a23d2-136">It is located at %programfiles%\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup Bootstrap\Log\\.</span></span>  
  
 <span data-ttu-id="a23d2-137">Per individuare gli errori nel file del testo di riepilogo, eseguire una ricerca nel file utilizzando le parole chiave "error" o "failed".</span><span class="sxs-lookup"><span data-stu-id="a23d2-137">To find errors in the summary text file, search the file by using the "error" or "failed" keywords.</span></span>  
  
## <a name="summary_engine-base_yyyymmdd_hhmmsstxt"></a><span data-ttu-id="a23d2-138">Summary_engine-base_AAAAMMGG_HHMMss.txt</span><span class="sxs-lookup"><span data-stu-id="a23d2-138">Summary_engine-base_YYYYMMDD_HHMMss.txt</span></span>  
  
### <a name="overview"></a><span data-ttu-id="a23d2-139">Panoramica</span><span class="sxs-lookup"><span data-stu-id="a23d2-139">Overview</span></span>  
 <span data-ttu-id="a23d2-140">Il file di base summary_engine è simile al file di riepilogo e viene generato durante il flusso di lavoro principale.</span><span class="sxs-lookup"><span data-stu-id="a23d2-140">The summary_engine base file is similar to the summary file and is generated during the main workflow.</span></span>  
  
### <a name="location"></a><span data-ttu-id="a23d2-141">Location</span><span class="sxs-lookup"><span data-stu-id="a23d2-141">Location</span></span>  
 <span data-ttu-id="a23d2-142">Si trova nel percorso% ProgramFiles% \\ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \120\Setup Bootstrap\LOG \\<YYYYMMDD_HHMM>\\ .</span><span class="sxs-lookup"><span data-stu-id="a23d2-142">It is located at %programfiles%\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup Bootstrap\Log\\<YYYYMMDD_HHMM>\\.</span></span>  
  
## <a name="summary_engine-base_yyyymmdd_hhmmss_componentupdatetxt"></a><span data-ttu-id="a23d2-143">Summary_engine-base_AAAAMMGG_HHMMss_ComponentUpdate.txt</span><span class="sxs-lookup"><span data-stu-id="a23d2-143">Summary_engine-base_YYYYMMDD_HHMMss_ComponentUpdate.txt</span></span>  
  
### <a name="overview"></a><span data-ttu-id="a23d2-144">Panoramica</span><span class="sxs-lookup"><span data-stu-id="a23d2-144">Overview</span></span>  
 <span data-ttu-id="a23d2-145">Il file di log di riepilogo relativo all'aggiornamento del componente è simile al file di riepilogo e viene generato durante il flusso di lavoro di aggiornamento del componente.</span><span class="sxs-lookup"><span data-stu-id="a23d2-145">The component update summary log file is similar to the summary file and is generated during the component update workflow.</span></span>  
  
### <a name="location"></a><span data-ttu-id="a23d2-146">Location</span><span class="sxs-lookup"><span data-stu-id="a23d2-146">Location</span></span>  
 <span data-ttu-id="a23d2-147">Si trova nel percorso% ProgramFiles% \\ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \120\Setup Bootstrap\LOG \\<YYYYMMDD_HHMM>\\ .</span><span class="sxs-lookup"><span data-stu-id="a23d2-147">It is located at %programfiles%\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup Bootstrap\Log\\<YYYYMMDD_HHMM>\\.</span></span>  
  
## <a name="summary_engine-base_versionnumbermmdd_hhmmss_globalrulestxt"></a><span data-ttu-id="a23d2-148">MMDD_HHMMss_GlobalRules.txt base_ Summary_engine \<VersionNumber></span><span class="sxs-lookup"><span data-stu-id="a23d2-148">Summary_engine-base_\<VersionNumber>MMDD_HHMMss_GlobalRules.txt</span></span>  
  
### <a name="overview"></a><span data-ttu-id="a23d2-149">Panoramica</span><span class="sxs-lookup"><span data-stu-id="a23d2-149">Overview</span></span>  
 <span data-ttu-id="a23d2-150">Il file di log di riepilogo relativo alle regole globali è simile al file di riepilogo e viene generato durante il flusso di lavoro delle regole globali.</span><span class="sxs-lookup"><span data-stu-id="a23d2-150">The global rules summary log file is similar to the summary file generated during the global rules workflow.</span></span>  
  
### <a name="location"></a><span data-ttu-id="a23d2-151">Location</span><span class="sxs-lookup"><span data-stu-id="a23d2-151">Location</span></span>  
 <span data-ttu-id="a23d2-152">Si trova nel percorso% ProgramFiles% \\ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \120\Setup Bootstrap\LOG \\<YYYYMMDD_HHMM>\\ .</span><span class="sxs-lookup"><span data-stu-id="a23d2-152">It is located at %programfiles%\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup Bootstrap\Log\\<YYYYMMDD_HHMM>\\.</span></span>  
  
## <a name="detailtxt"></a><span data-ttu-id="a23d2-153">Detail.txt</span><span class="sxs-lookup"><span data-stu-id="a23d2-153">Detail.txt</span></span>  
  
### <a name="overview"></a><span data-ttu-id="a23d2-154">Panoramica</span><span class="sxs-lookup"><span data-stu-id="a23d2-154">Overview</span></span>  
 <span data-ttu-id="a23d2-155">Il file Detail.txt viene generato per il flusso di lavoro principale, ad esempio installazione o aggiornamento, e fornisce i dettagli dell'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="a23d2-155">Detail.txt is generated for the main workflow such as install or upgrade, and provides the details of the execution.</span></span> <span data-ttu-id="a23d2-156">Le registrazioni presenti nel file vengono generate in base al momento in cui viene richiamata ogni azione dell'installazione e indicano l'ordine in cui le azioni sono state eseguite, nonché le relative dipendenze.</span><span class="sxs-lookup"><span data-stu-id="a23d2-156">The logs in the file are generated based on the time when each action for the installation was invoked, and show the order in which the actions were executed, and their dependencies.</span></span>  
  
### <a name="location"></a><span data-ttu-id="a23d2-157">Location</span><span class="sxs-lookup"><span data-stu-id="a23d2-157">Location</span></span>  
 <span data-ttu-id="a23d2-158">Si trova nel percorso% ProgramFiles% \\ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \120\Setup</span><span class="sxs-lookup"><span data-stu-id="a23d2-158">It is located at %programfiles%\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup</span></span>  
  
 <span data-ttu-id="a23d2-159">Bootstrap\Log\\<AAAAMMGG_HHMM>\Detail.txt.</span><span class="sxs-lookup"><span data-stu-id="a23d2-159">Bootstrap\Log\\<YYYYMMDD_HHMM>\Detail.txt.</span></span>  
  
 <span data-ttu-id="a23d2-160">Se si verifica un errore durante il processo di installazione, l'eccezione o l'errore verrà registrato alla fine di questo file.</span><span class="sxs-lookup"><span data-stu-id="a23d2-160">If an error occurs during the Setup process, the exception or error are logged at the end of this file.</span></span> <span data-ttu-id="a23d2-161">Per individuare gli errori in questo file, esaminare innanzitutto la parte finale del file, quindi eseguire una ricerca nel file delle parole chiave "error" o "exception".</span><span class="sxs-lookup"><span data-stu-id="a23d2-161">To find the errors in this file, first examine the end of the file followed by a search of the file for the "error" or "exception" keywords.</span></span>  
  
## <a name="detail_componentupdatetxt"></a><span data-ttu-id="a23d2-162">Detail_ComponentUpdate.txt</span><span class="sxs-lookup"><span data-stu-id="a23d2-162">Detail_ComponentUpdate.txt</span></span>  
  
### <a name="overview"></a><span data-ttu-id="a23d2-163">Panoramica</span><span class="sxs-lookup"><span data-stu-id="a23d2-163">Overview</span></span>  
 <span data-ttu-id="a23d2-164">Il file Detail_ComponentUpdate.txt viene generato per il flusso di lavoro di aggiornamento del componente ed è simile al file Detail.txt.</span><span class="sxs-lookup"><span data-stu-id="a23d2-164">The Detail_ComponentUpdate.txt file is generated for the component update workflow and is similar to Detail.txt.</span></span>  
  
### <a name="location"></a><span data-ttu-id="a23d2-165">Location</span><span class="sxs-lookup"><span data-stu-id="a23d2-165">Location</span></span>  
 <span data-ttu-id="a23d2-166">Si trova nel percorso% ProgramFiles% \\ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \120\Setup Bootstrap\LOG \\<YYYYMMDD_HHMM>\\ .</span><span class="sxs-lookup"><span data-stu-id="a23d2-166">It is located at %programfiles%\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup Bootstrap\Log\\<YYYYMMDD_HHMM>\\.</span></span>  
  
## <a name="detail_globalrulestxt"></a><span data-ttu-id="a23d2-167">Detail_GlobalRules.txt</span><span class="sxs-lookup"><span data-stu-id="a23d2-167">Detail_GlobalRules.txt</span></span>  
  
### <a name="overview"></a><span data-ttu-id="a23d2-168">Panoramica</span><span class="sxs-lookup"><span data-stu-id="a23d2-168">Overview</span></span>  
 <span data-ttu-id="a23d2-169">Il file Detail_GlobalRules.txt viene generato per l'esecuzione delle regole globali ed è simile al file Detail.txt.</span><span class="sxs-lookup"><span data-stu-id="a23d2-169">Detail_GlobalRules.txt is generated for the global rules execution and is similar to Detail.txt.</span></span>  
  
### <a name="location"></a><span data-ttu-id="a23d2-170">Location</span><span class="sxs-lookup"><span data-stu-id="a23d2-170">Location</span></span>  
 <span data-ttu-id="a23d2-171">Si trova nel percorso% ProgramFiles% \\ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \120\Setup Bootstrap\LOG \\<YYYYMMDD_HHMM>\\ .</span><span class="sxs-lookup"><span data-stu-id="a23d2-171">It is located at %programfiles%\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup Bootstrap\Log\\<YYYYMMDD_HHMM>\\.</span></span>  
  
## <a name="msi-log-files"></a><span data-ttu-id="a23d2-172">File di log MSI</span><span class="sxs-lookup"><span data-stu-id="a23d2-172">MSI log files</span></span>  
  
### <a name="overview"></a><span data-ttu-id="a23d2-173">Panoramica</span><span class="sxs-lookup"><span data-stu-id="a23d2-173">Overview</span></span>  
 <span data-ttu-id="a23d2-174">I file di log MSI forniscono dettagli sul processo del pacchetto di installazione.</span><span class="sxs-lookup"><span data-stu-id="a23d2-174">The MSI log files provide details of the installation package process.</span></span> <span data-ttu-id="a23d2-175">Vengono generati da MSIEXEC durante l'installazione del pacchetto specificato.</span><span class="sxs-lookup"><span data-stu-id="a23d2-175">They are generated by the MSIEXEC during the installation of the specified package.</span></span>  
  
 <span data-ttu-id="a23d2-176">Tipi di file di log MSI:</span><span class="sxs-lookup"><span data-stu-id="a23d2-176">Types of MSI log files:</span></span>  
  
-   <span data-ttu-id="a23d2-177">\<Feature>_\<Architecture>\_\<Interaction>.log</span><span class="sxs-lookup"><span data-stu-id="a23d2-177">\<Feature>_\<Architecture>\_\<Interaction>.log</span></span>  
  
-   <span data-ttu-id="a23d2-178">\<Feature>_\<Architecture>\_\<Language>\_\<Interaction>.log</span><span class="sxs-lookup"><span data-stu-id="a23d2-178">\<Feature>_\<Architecture>\_\<Language>\_\<Interaction>.log</span></span>  
  
-   <span data-ttu-id="a23d2-179">\<Feature>_\<Architecture>\_\<Interaction>\_\<workflow>.log</span><span class="sxs-lookup"><span data-stu-id="a23d2-179">\<Feature>_\<Architecture>\_\<Interaction>\_\<workflow>.log</span></span>  
  
### <a name="location"></a><span data-ttu-id="a23d2-180">Location</span><span class="sxs-lookup"><span data-stu-id="a23d2-180">Location</span></span>  
 <span data-ttu-id="a23d2-181">I file di registro MSI si trovano nel percorso% ProgramFiles% \\ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \120\Setup Bootstrap\LOG \\<YYYYMMDD_HHMM>\\<Name \> . log.</span><span class="sxs-lookup"><span data-stu-id="a23d2-181">The MSI log files are located at %programfiles%\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup Bootstrap\Log\\<YYYYMMDD_HHMM>\\<Name\>.log.</span></span>  
  
 <span data-ttu-id="a23d2-182">Nella parte finale del file è incluso un riepilogo dell'esecuzione in cui sono indicati lo stato riuscito o non riuscito e le proprietà.</span><span class="sxs-lookup"><span data-stu-id="a23d2-182">At the end of the file is a summary of the execution which includes the success or failure status and properties.</span></span> <span data-ttu-id="a23d2-183">Per individuare l'errore nel file MSI, eseguire la ricerca di "value 3", poiché gli errori si trovano in genere in prossimità di tale stringa.</span><span class="sxs-lookup"><span data-stu-id="a23d2-183">To find the error in the MSI file, search for "value 3" and usually the errors can be found close to the string.</span></span>  
  
## <a name="configurationfileini"></a><span data-ttu-id="a23d2-184">ConfigurationFile.ini</span><span class="sxs-lookup"><span data-stu-id="a23d2-184">ConfigurationFile.ini</span></span>  
  
### <a name="overview"></a><span data-ttu-id="a23d2-185">Panoramica</span><span class="sxs-lookup"><span data-stu-id="a23d2-185">Overview</span></span>  
 <span data-ttu-id="a23d2-186">Il file di configurazione contiene le impostazioni di input fornite durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="a23d2-186">The configuration file contains the input settings that are provided during installation.</span></span> <span data-ttu-id="a23d2-187">Può essere utile riavviare l'installazione senza dover immettere manualmente le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="a23d2-187">It can be used to restart the installation without having to enter the settings manually.</span></span> <span data-ttu-id="a23d2-188">Nel file di configurazione non vengono tuttavia salvati le password degli account, i PID e alcuni parametri.</span><span class="sxs-lookup"><span data-stu-id="a23d2-188">However, passwords for the accounts, PID, and some parameters are not saved in the configuration file.</span></span> <span data-ttu-id="a23d2-189">Le impostazioni possono essere aggiunte al file o specificate tramite una riga di comando o l'interfaccia utente del programma di installazione.</span><span class="sxs-lookup"><span data-stu-id="a23d2-189">The settings can be either added to the file or provided by using the command line or the Setup user interface.</span></span> <span data-ttu-id="a23d2-190">Per altre informazioni, vedere [installare SQL Server 2014 usando un file di configurazione](install-sql-server-using-a-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="a23d2-190">For more information, see [Install SQL Server 2014 Using a Configuration File](install-sql-server-using-a-configuration-file.md).</span></span>  
  
### <a name="location"></a><span data-ttu-id="a23d2-191">Location</span><span class="sxs-lookup"><span data-stu-id="a23d2-191">Location</span></span>  
 <span data-ttu-id="a23d2-192">Si trova nel percorso% ProgramFiles% \\ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \120\Setup Bootstrap\LOG \\<YYYYMMDD_HHMM>\\ .</span><span class="sxs-lookup"><span data-stu-id="a23d2-192">It is located at %programfiles%\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup Bootstrap\Log\\<YYYYMMDD_HHMM>\\.</span></span>  
  
## <a name="systemconfigurationcheck_reporthtm"></a><span data-ttu-id="a23d2-193">SystemConfigurationCheck_Report.htm</span><span class="sxs-lookup"><span data-stu-id="a23d2-193">SystemConfigurationCheck_Report.htm</span></span>  
  
### <a name="overview"></a><span data-ttu-id="a23d2-194">Panoramica</span><span class="sxs-lookup"><span data-stu-id="a23d2-194">Overview</span></span>  
 <span data-ttu-id="a23d2-195">Il report di controllo della configurazione di sistema contiene una breve descrizione di ogni regola eseguita, nonché lo stato di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="a23d2-195">The system configuration check report contains a short description for each executed rule, and the execution status.</span></span>  
  
### <a name="location"></a><span data-ttu-id="a23d2-196">Location</span><span class="sxs-lookup"><span data-stu-id="a23d2-196">Location</span></span>  
 <span data-ttu-id="a23d2-197">Si trova nel percorso% ProgramFiles% \\ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \120\Setup Bootstrap\LOG \\<YYYYMMDD_HHMM>\\ .</span><span class="sxs-lookup"><span data-stu-id="a23d2-197">It is located at %programfiles%\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup Bootstrap\Log\\<YYYYMMDD_HHMM>\\.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a23d2-198">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a23d2-198">See Also</span></span>  
 <span data-ttu-id="a23d2-199">[Procedure per l'installazione](../../sql-server/install/installation-how-to-topics.md) </span><span class="sxs-lookup"><span data-stu-id="a23d2-199">[Installation How-to Topics](../../sql-server/install/installation-how-to-topics.md) </span></span>  
 [<span data-ttu-id="a23d2-200">Installare SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="a23d2-200">Install SQL Server 2014</span></span>](install-sql-server.md)  
  
  
