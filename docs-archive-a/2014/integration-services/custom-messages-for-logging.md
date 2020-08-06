---
title: Messaggi personalizzati per la registrazione | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- logs [Integration Services], custom
- writing log entries
- SSIS packages, logs
- custom messages for logging [Integration Services]
ms.assetid: 3c74bba9-02b7-4bf5-bad5-19278b680730
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2b9f450c74ef6d46876adfde45729c71b3262449
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628916"
---
# <a name="custom-messages-for-logging"></a><span data-ttu-id="53bb0-102">Messaggi personalizzati per la registrazione</span><span class="sxs-lookup"><span data-stu-id="53bb0-102">Custom Messages for Logging</span></span>
  <span data-ttu-id="53bb0-103">In [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] sono disponibili numerosi eventi personalizzati per la scrittura di voci di log per i pacchetti e per molte attività.</span><span class="sxs-lookup"><span data-stu-id="53bb0-103">[!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] provides a rich set of custom events for writing log entries for packages and many tasks.</span></span> <span data-ttu-id="53bb0-104">È possibile utilizzare tali voci per salvare informazioni dettagliate su stato di esecuzione, risultati e problemi, tramite la registrazione di eventi predefiniti o messaggi definiti dall'utente da analizzare in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="53bb0-104">You can use these entries to save detailed information about execution progress, results, and problems by recording predefined events or user-defined messages for later analysis.</span></span> <span data-ttu-id="53bb0-105">È ad esempio possibile registrare la data e l'ora di inizio e di fine di un'operazione di inserimento bulk per identificare problemi di prestazioni durante l'esecuzione del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="53bb0-105">For example, you can record when a bulk insert begins and ends to identify performance issues when the package runs.</span></span>  
  
 <span data-ttu-id="53bb0-106">Le voci di log personalizzate costituiscono un set diverso da quello degli eventi di registrazione standard, disponibili per i pacchetti e per tutti i contenitori e le attività.</span><span class="sxs-lookup"><span data-stu-id="53bb0-106">The custom log entries are a different set of entries than the set of standard logging events that are available for packages and all containers and tasks.</span></span> <span data-ttu-id="53bb0-107">Le voci di log personalizzate vengono create appositamente per acquisire informazioni utili su specifiche attività di un pacchetto.</span><span class="sxs-lookup"><span data-stu-id="53bb0-107">The custom log entries are tailored to capture useful information about a specific task in a package.</span></span> <span data-ttu-id="53bb0-108">Per l'attività Esegui SQL è ad esempio disponibile una voce di log personalizzata che registra nel log l'istruzione SQL eseguita dall'attività.</span><span class="sxs-lookup"><span data-stu-id="53bb0-108">For example, one of the custom log entries for the Execute SQL task records the SQL statement that the task executes in the log.</span></span>  
  
 <span data-ttu-id="53bb0-109">Tutte le voci di log includono informazioni di data e ora, comprese le voci di log scritte automaticamente all'inizio e alla fine dell'esecuzione di un pacchetto.</span><span class="sxs-lookup"><span data-stu-id="53bb0-109">All log entries include date and time information, including the log entries that are automatically written when a package begins and finishes.</span></span> <span data-ttu-id="53bb0-110">Per molti eventi vengono scritte più voci nel log.</span><span class="sxs-lookup"><span data-stu-id="53bb0-110">Many of the log events write multiple entries to the log.</span></span> <span data-ttu-id="53bb0-111">Questo avviene in genere per gli eventi che includono varie fasi.</span><span class="sxs-lookup"><span data-stu-id="53bb0-111">This typically occurs when the event has different phases.</span></span> <span data-ttu-id="53bb0-112">Per l'evento `ExecuteSQLExecutingQuery`, ad esempio, vengono scritte tre voci di log: una dopo l'acquisizione di una connessione al database da parte dell'attività, una dopo l'inizio della preparazione dell'istruzione SQL da parte dell'attività e un'altra al termine dell'esecuzione dell'istruzione SQL.</span><span class="sxs-lookup"><span data-stu-id="53bb0-112">For example, the `ExecuteSQLExecutingQuery` log event writes three entries: one entry after the task acquires a connection to the database, another after the task starts to prepare the SQL statement, and one more after the execution of the SQL statement is completed.</span></span>  
  
 <span data-ttu-id="53bb0-113">Sono disponibili voci di log personalizzate per gli oggetti [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] seguenti:</span><span class="sxs-lookup"><span data-stu-id="53bb0-113">The following [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] objects have custom log entries:</span></span>  
  
 [<span data-ttu-id="53bb0-114">Pacchetto</span><span class="sxs-lookup"><span data-stu-id="53bb0-114">Package</span></span>](#Package)  
  
 [<span data-ttu-id="53bb0-115">Attività Inserimento bulk</span><span class="sxs-lookup"><span data-stu-id="53bb0-115">Bulk Insert Task</span></span>](#BulkInsert)  
  
 [<span data-ttu-id="53bb0-116">Attività Flusso di dati</span><span class="sxs-lookup"><span data-stu-id="53bb0-116">Data Flow Task</span></span>](#DataFlow)  
  
 [<span data-ttu-id="53bb0-117">Attività Esegui pacchetto DTS 2000</span><span class="sxs-lookup"><span data-stu-id="53bb0-117">Execute DTS 2000 Task</span></span>](#ExecuteDTS200)  
  
 [<span data-ttu-id="53bb0-118">Attività Esegui processo</span><span class="sxs-lookup"><span data-stu-id="53bb0-118">Execute Process Task</span></span>](#ExecuteProcess)  
  
 [<span data-ttu-id="53bb0-119">Attività Esegui SQL</span><span class="sxs-lookup"><span data-stu-id="53bb0-119">Execute SQL Task</span></span>](#ExecuteSQL)  
  
 [<span data-ttu-id="53bb0-120">Attività File system</span><span class="sxs-lookup"><span data-stu-id="53bb0-120">File System Task</span></span>](#FileSystem)  
  
 [<span data-ttu-id="53bb0-121">Attività FTP</span><span class="sxs-lookup"><span data-stu-id="53bb0-121">FTP Task</span></span>](#FTP)  
  
 [<span data-ttu-id="53bb0-122">Attività Message Queue</span><span class="sxs-lookup"><span data-stu-id="53bb0-122">Message Queue Task</span></span>](#MessageQueue)  
  
 [<span data-ttu-id="53bb0-123">Attività Script</span><span class="sxs-lookup"><span data-stu-id="53bb0-123">Script Task</span></span>](#Script)  
  
 [<span data-ttu-id="53bb0-124">Attività Invia messaggi</span><span class="sxs-lookup"><span data-stu-id="53bb0-124">Send Mail Task</span></span>](#SendMail)  
  
 [<span data-ttu-id="53bb0-125">Attività Trasferisci database</span><span class="sxs-lookup"><span data-stu-id="53bb0-125">Transfer Database Task</span></span>](#TransferDatabase)  
  
 [<span data-ttu-id="53bb0-126">Attività Trasferisci messaggi di errore</span><span class="sxs-lookup"><span data-stu-id="53bb0-126">Transfer Error Messages Task</span></span>](#TransferErrorMessages)  
  
 [<span data-ttu-id="53bb0-127">Attività Trasferisci processi</span><span class="sxs-lookup"><span data-stu-id="53bb0-127">Transfer Jobs Task</span></span>](#TransferJobs)  
  
 [<span data-ttu-id="53bb0-128">Attività Trasferisci account di accesso</span><span class="sxs-lookup"><span data-stu-id="53bb0-128">Transfer Logins Task</span></span>](#TransferLogins)  
  
 [<span data-ttu-id="53bb0-129">Attività Trasferisci stored procedure master</span><span class="sxs-lookup"><span data-stu-id="53bb0-129">Transfer Master Stored Procedures Task</span></span>](#TransferMasterStoredProcedures)  
  
 [<span data-ttu-id="53bb0-130">Attività Trasferisci oggetti di SQL Server</span><span class="sxs-lookup"><span data-stu-id="53bb0-130">Transfer SQL Server Objects Task</span></span>](#TransferSQLServerObjects)  
  
 [<span data-ttu-id="53bb0-131">Attività Servizio Web</span><span class="sxs-lookup"><span data-stu-id="53bb0-131">Web Services Task</span></span>](#WebServices)  
  
 [<span data-ttu-id="53bb0-132">Attività Lettore di dati WMI</span><span class="sxs-lookup"><span data-stu-id="53bb0-132">WMI Data Reader Task</span></span>](#WMIDataReader)  
  
 [<span data-ttu-id="53bb0-133">Attività Monitoraggio eventi WMI</span><span class="sxs-lookup"><span data-stu-id="53bb0-133">WMI Event Watcher Task</span></span>](#WMIEventWatcher)  
  
 [<span data-ttu-id="53bb0-134">Attività XML</span><span class="sxs-lookup"><span data-stu-id="53bb0-134">XML Task</span></span>](#XML)  
  
## <a name="log-entries"></a><span data-ttu-id="53bb0-135">Voci di log</span><span class="sxs-lookup"><span data-stu-id="53bb0-135">Log Entries</span></span>  
  
###  <a name="package"></a><a name="Package"></a> <span data-ttu-id="53bb0-136">Pacchetto</span><span class="sxs-lookup"><span data-stu-id="53bb0-136">Package</span></span>  
 <span data-ttu-id="53bb0-137">Nella tabella seguente sono elencate le voci di log personalizzate disponibili per i pacchetti.</span><span class="sxs-lookup"><span data-stu-id="53bb0-137">The following table lists the custom log entries for packages.</span></span>  
  
|<span data-ttu-id="53bb0-138">Voce di log</span><span class="sxs-lookup"><span data-stu-id="53bb0-138">Log entry</span></span>|<span data-ttu-id="53bb0-139">Descrizione</span><span class="sxs-lookup"><span data-stu-id="53bb0-139">Description</span></span>|  
|---------------|-----------------|  
|`PackageStart`|<span data-ttu-id="53bb0-140">Indica che l'esecuzione del pacchetto è iniziata.</span><span class="sxs-lookup"><span data-stu-id="53bb0-140">Indicates that the package began to run.</span></span><br /><br /> <span data-ttu-id="53bb0-141">Nota: questa voce di log viene scritta automaticamente nel log.</span><span class="sxs-lookup"><span data-stu-id="53bb0-141">Note: This log entry is automatically written to the log.</span></span> <span data-ttu-id="53bb0-142">e non può essere esclusa.</span><span class="sxs-lookup"><span data-stu-id="53bb0-142">You cannot exclude it.</span></span>|  
|`PackageEnd`|<span data-ttu-id="53bb0-143">Indica che l'esecuzione del pacchetto è stata completata.</span><span class="sxs-lookup"><span data-stu-id="53bb0-143">Indicates that the package completed.</span></span><br /><br /> <span data-ttu-id="53bb0-144">Nota: questa voce di log viene scritta automaticamente nel log.</span><span class="sxs-lookup"><span data-stu-id="53bb0-144">Note: This log entry is automatically written to the log.</span></span> <span data-ttu-id="53bb0-145">e non può essere esclusa.</span><span class="sxs-lookup"><span data-stu-id="53bb0-145">You cannot exclude it.</span></span>|  
|`Diagnostic`|<span data-ttu-id="53bb0-146">Offre informazioni sulla configurazione del sistema che influisce sull'esecuzione dei pacchetti, ad esempio il numero di file eseguibili che è possibile eseguire simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="53bb0-146">Provides information about the system configuration that affects package execution such as the number executables that can be run concurrently.</span></span><br /><br /> <span data-ttu-id="53bb0-147">La voce di log `Diagnostic` include anche le voci precedenti e seguenti alle chiamate a provider di dati esterni.</span><span class="sxs-lookup"><span data-stu-id="53bb0-147">The `Diagnostic` log entry also includes before and after entries for calls to external data providers.</span></span> <span data-ttu-id="53bb0-148">Per altre informazioni, vedere [Risoluzione dei problemi relativi alla connettività dei pacchetti degli strumenti](troubleshooting/troubleshooting-tools-for-package-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="53bb0-148">For more information, see [Troubleshooting Tools Package Connectivity](troubleshooting/troubleshooting-tools-for-package-connectivity.md).</span></span>|  
  
###  <a name="bulk-insert-task"></a><a name="BulkInsert"></a> <span data-ttu-id="53bb0-149">Attività Inserimento bulk</span><span class="sxs-lookup"><span data-stu-id="53bb0-149">Bulk Insert Task</span></span>  
 <span data-ttu-id="53bb0-150">Nella tabella seguente sono elencate le voci di log personalizzate disponibili per l'attività Inserimento bulk.</span><span class="sxs-lookup"><span data-stu-id="53bb0-150">The following table lists the custom log entries for the Bulk Insert task.</span></span>  
  
|<span data-ttu-id="53bb0-151">Voce di log</span><span class="sxs-lookup"><span data-stu-id="53bb0-151">Log entry</span></span>|<span data-ttu-id="53bb0-152">Descrizione</span><span class="sxs-lookup"><span data-stu-id="53bb0-152">Description</span></span>|  
|---------------|-----------------|  
|`DTSBulkInsertTaskBegin`|<span data-ttu-id="53bb0-153">Indica che l'inserimento bulk è iniziato.</span><span class="sxs-lookup"><span data-stu-id="53bb0-153">Indicates that the bulk insert began.</span></span>|  
|`DTSBulkInsertTaskEnd`|<span data-ttu-id="53bb0-154">Indica che l'inserimento bulk è terminato.</span><span class="sxs-lookup"><span data-stu-id="53bb0-154">Indicates that the bulk insert finished.</span></span>|  
|`DTSBulkInsertTaskInfos`|<span data-ttu-id="53bb0-155">Offre informazioni descrittive sull'attività.</span><span class="sxs-lookup"><span data-stu-id="53bb0-155">Provides descriptive information about the task.</span></span>|  
  
###  <a name="data-flow-task"></a><a name="DataFlow"></a> <span data-ttu-id="53bb0-156">Data Flow Task</span><span class="sxs-lookup"><span data-stu-id="53bb0-156">Data Flow Task</span></span>  
 <span data-ttu-id="53bb0-157">Nella tabella seguente sono elencate le voci di log personalizzate disponibili per l'attività Flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="53bb0-157">The following table lists the custom log entries for the Data Flow task.</span></span>  
  
|<span data-ttu-id="53bb0-158">Voce di log</span><span class="sxs-lookup"><span data-stu-id="53bb0-158">Log entry</span></span>|<span data-ttu-id="53bb0-159">Descrizione</span><span class="sxs-lookup"><span data-stu-id="53bb0-159">Description</span></span>|  
|---------------|-----------------|  
|`BufferSizeTuning`|<span data-ttu-id="53bb0-160">Indica che l'attività Flusso di dati ha modificato le dimensioni del buffer.</span><span class="sxs-lookup"><span data-stu-id="53bb0-160">Indicates that the Data Flow task changed the size of the buffer.</span></span> <span data-ttu-id="53bb0-161">In questa voce di log vengono indicati i motivi della modifica delle dimensioni del buffer e le nuove dimensioni temporanee del buffer.</span><span class="sxs-lookup"><span data-stu-id="53bb0-161">The log entry describes the reasons for the size change and lists the temporary new buffer size.</span></span>|  
|`OnPipelinePostEndOfRowset`|<span data-ttu-id="53bb0-162">Indica che a un componente è stato inviato il segnale di fine del set di righe, che viene impostato dall'ultima chiamata al metodo `ProcessInput`.</span><span class="sxs-lookup"><span data-stu-id="53bb0-162">Denotes that a component has been given its end-of-rowset signal, which is set by the last call of the `ProcessInput` method.</span></span> <span data-ttu-id="53bb0-163">Viene scritta una voce per ogni componente del flusso di dati che elabora dati di input.</span><span class="sxs-lookup"><span data-stu-id="53bb0-163">An entry is written for each component in the data flow that processes input.</span></span> <span data-ttu-id="53bb0-164">Tale voce include il nome del componente.</span><span class="sxs-lookup"><span data-stu-id="53bb0-164">The entry includes the name of the component.</span></span>|  
|`OnPipelinePostPrimeOutput`|<span data-ttu-id="53bb0-165">Indica che il componente ha completato l'ultima chiamata al metodo `PrimeOutput`.</span><span class="sxs-lookup"><span data-stu-id="53bb0-165">Indicates that the component has completed its last call to the `PrimeOutput` method.</span></span> <span data-ttu-id="53bb0-166">A seconda del flusso di dati, è possibile che vengano scritte più voci di log.</span><span class="sxs-lookup"><span data-stu-id="53bb0-166">Depending on the data flow, multiple log entries may be written.</span></span> <span data-ttu-id="53bb0-167">Se il componente è un'origine, indica che tale componente ha terminato l'elaborazione delle righe.</span><span class="sxs-lookup"><span data-stu-id="53bb0-167">If the component is a source, this means that the component has finished processing rows.</span></span>|  
|`OnPipelinePreEndOfRowset`|<span data-ttu-id="53bb0-168">Indica che un componente sta per ricevere il segnale di fine del set di righe, che viene impostato dall'ultima chiamata al metodo `ProcessInput`.</span><span class="sxs-lookup"><span data-stu-id="53bb0-168">Indicates that a component is about to receive its end-of-rowset signal, which is set by the last call of the `ProcessInput` method.</span></span> <span data-ttu-id="53bb0-169">Viene scritta una voce per ogni componente del flusso di dati che elabora dati di input.</span><span class="sxs-lookup"><span data-stu-id="53bb0-169">An entry is written for each component in the data flow that processes input.</span></span> <span data-ttu-id="53bb0-170">Tale voce include il nome del componente.</span><span class="sxs-lookup"><span data-stu-id="53bb0-170">The entry includes the name of the component.</span></span>|  
|`OnPipelinePrePrimeOutput`|<span data-ttu-id="53bb0-171">Indica che un componente sta per ricevere una chiamata dal metodo `PrimeOutput`.</span><span class="sxs-lookup"><span data-stu-id="53bb0-171">Indicates that the component is about to receive its call from the `PrimeOutput` method.</span></span> <span data-ttu-id="53bb0-172">A seconda del flusso di dati, è possibile che vengano scritte più voci di log.</span><span class="sxs-lookup"><span data-stu-id="53bb0-172">Depending on the data flow, multiple log entries may be written.</span></span>|  
|`OnPipelineRowsSent`|<span data-ttu-id="53bb0-173">Specifica il numero delle righe inviate all'input di un componente da una chiamata al metodo `ProcessInput`.</span><span class="sxs-lookup"><span data-stu-id="53bb0-173">Reports the number of rows provided to a component input by a call to the `ProcessInput` method.</span></span> <span data-ttu-id="53bb0-174">La voce di log include il nome del componente.</span><span class="sxs-lookup"><span data-stu-id="53bb0-174">The log entry includes the component name.</span></span>|  
|`PipelineBufferLeak`|<span data-ttu-id="53bb0-175">Fornisce informazioni su tutti i componenti che hanno mantenuto attivi i buffer dopo la chiusura di Gestione buffer.</span><span class="sxs-lookup"><span data-stu-id="53bb0-175">Provides information about any component that kept buffers alive after the buffer manager goes away.</span></span> <span data-ttu-id="53bb0-176">Questo significa che le risorse dei buffer non sono state rilasciate e potrebbero verificarsi perdite di memoria.</span><span class="sxs-lookup"><span data-stu-id="53bb0-176">This means that buffers resources were not released and may cause memory leaks.</span></span> <span data-ttu-id="53bb0-177">Nella voce di log vengono indicati il nome del componente e l'ID del buffer.</span><span class="sxs-lookup"><span data-stu-id="53bb0-177">The log entry provides the name of the component and the ID of the buffer.</span></span>|  
|`PipelineExecutionPlan`|<span data-ttu-id="53bb0-178">Specifica il piano di esecuzione del flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="53bb0-178">Reports the execution plan of the data flow.</span></span> <span data-ttu-id="53bb0-179">Fornisce informazioni sulle modalità di invio dei buffer ai componenti.</span><span class="sxs-lookup"><span data-stu-id="53bb0-179">It provides information about how buffers will be sent to components.</span></span> <span data-ttu-id="53bb0-180">Insieme alla voce PipelineExecutionTrees, queste informazioni illustrano ciò che avviene nell'ambito dell'attività.</span><span class="sxs-lookup"><span data-stu-id="53bb0-180">This information, in combination with the PipelineExecutionTrees entry, describes what is occurring in the task.</span></span>|  
|`PipelineExecutionTrees`|<span data-ttu-id="53bb0-181">Specifica gli alberi di esecuzione del layout nel flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="53bb0-181">Reports the execution trees of the layout in the data flow.</span></span> <span data-ttu-id="53bb0-182">L'utilità di pianificazione del motore flusso di dati utilizza tali alberi per compilare il piano di esecuzione del flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="53bb0-182">The scheduler of the data flow engine use the trees to build the execution plan of the data flow.</span></span>|  
|`PipelineInitialization`|<span data-ttu-id="53bb0-183">Fornisce le informazioni di inizializzazione relative all'attività,</span><span class="sxs-lookup"><span data-stu-id="53bb0-183">Provides initialization information about the task.</span></span> <span data-ttu-id="53bb0-184">che includono le directory da utilizzare per l'archiviazione temporanea dei dati BLOB, le dimensioni predefinite del buffer e il numero di righe in un buffer.</span><span class="sxs-lookup"><span data-stu-id="53bb0-184">This information includes the directories to use for temporary storage of BLOB data, the default buffer size, and the number of rows in a buffer.</span></span> <span data-ttu-id="53bb0-185">A seconda della configurazione dell'attività Flusso di dati, è possibile che vengano scritte più voci di log.</span><span class="sxs-lookup"><span data-stu-id="53bb0-185">Depending on the configuration of the Data Flow task, multiple log entries may be written.</span></span>|  
  
###  <a name="execute-dts-2000-task"></a><a name="ExecuteDTS200"></a> <span data-ttu-id="53bb0-186">Attività Esegui pacchetto DTS 2000</span><span class="sxs-lookup"><span data-stu-id="53bb0-186">Execute DTS 2000 Task</span></span>  
 <span data-ttu-id="53bb0-187">Nella tabella seguente sono elencate le voci di log personalizzate disponibili per l'attività Esegui pacchetto DTS 2000.</span><span class="sxs-lookup"><span data-stu-id="53bb0-187">The following table lists the custom log entries for the Execute DTS 2000 task.</span></span>  
  
|<span data-ttu-id="53bb0-188">Voce di log</span><span class="sxs-lookup"><span data-stu-id="53bb0-188">Log entry</span></span>|<span data-ttu-id="53bb0-189">Descrizione</span><span class="sxs-lookup"><span data-stu-id="53bb0-189">Description</span></span>|  
|---------------|-----------------|  
|`ExecuteDTS80PackageTaskBegin`|<span data-ttu-id="53bb0-190">Indica che l'attività ha iniziato a eseguire un pacchetto DTS 2000.</span><span class="sxs-lookup"><span data-stu-id="53bb0-190">Indicates that the task began to run a DTS 2000 package.</span></span>|  
|`ExecuteDTS80PackageTaskEnd`|<span data-ttu-id="53bb0-191">Indica che l'attività è terminata.</span><span class="sxs-lookup"><span data-stu-id="53bb0-191">Indicates that the task finished.</span></span><br /><br /> <span data-ttu-id="53bb0-192">Nota: l'esecuzione del pacchetto DTS 2000 può continuare anche dopo il termine dell'attività.</span><span class="sxs-lookup"><span data-stu-id="53bb0-192">Note: The DTS 2000 package may continue to run after the task ends.</span></span>|  
|`ExecuteDTS80PackageTaskTaskInfo`|<span data-ttu-id="53bb0-193">Offre informazioni descrittive sull'attività.</span><span class="sxs-lookup"><span data-stu-id="53bb0-193">Provides descriptive information about the task.</span></span>|  
|`ExecuteDTS80PackageTaskTaskResult`|<span data-ttu-id="53bb0-194">Restituisce il risultato dell'esecuzione del pacchetto DTS 2000 eseguito dall'attività.</span><span class="sxs-lookup"><span data-stu-id="53bb0-194">Reports the execution result of the DTS 2000 package that the task ran.</span></span>|  
  
###  <a name="execute-process-task"></a><a name="ExecuteProcess"></a> <span data-ttu-id="53bb0-195">Attività Esegui processo</span><span class="sxs-lookup"><span data-stu-id="53bb0-195">Execute Process Task</span></span>  
 <span data-ttu-id="53bb0-196">Nella tabella seguente sono elencate le voci di log personalizzate disponibili per l'attività Esegui processo.</span><span class="sxs-lookup"><span data-stu-id="53bb0-196">The following table lists the custom log entries for the Execute Process task.</span></span>  
  
|<span data-ttu-id="53bb0-197">Voce di log</span><span class="sxs-lookup"><span data-stu-id="53bb0-197">Log entry</span></span>|<span data-ttu-id="53bb0-198">Descrizione</span><span class="sxs-lookup"><span data-stu-id="53bb0-198">Description</span></span>|  
|---------------|-----------------|  
|`ExecuteProcessExecutingProcess`|<span data-ttu-id="53bb0-199">Fornisce informazioni sul processo di esecuzione del file eseguibile che l'attività dovrà eseguire.</span><span class="sxs-lookup"><span data-stu-id="53bb0-199">Provides information about the process of running the executable that the task is configured to run.</span></span><br /><br /> <span data-ttu-id="53bb0-200">Vengono scritte due voci di log.</span><span class="sxs-lookup"><span data-stu-id="53bb0-200">Two log entries are written.</span></span> <span data-ttu-id="53bb0-201">Una contiene informazioni sul nome e la posizione del file eseguibile eseguito dall'attività, l'altra registra l'uscita dall'eseguibile.</span><span class="sxs-lookup"><span data-stu-id="53bb0-201">One contains information about the name and location of the executable that the task runs, and the other records the exit from the executable.</span></span>|  
|`ExecuteProcessVariableRouting`|<span data-ttu-id="53bb0-202">Fornisce informazioni sulle variabili indirizzate all'input e agli output del file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="53bb0-202">Provides information about which variables are routed to the input and outputs of the executable.</span></span> <span data-ttu-id="53bb0-203">Vengono scritte voci di log per stdin (l'input), stdout (l'output) e stderr (l'output degli errori).</span><span class="sxs-lookup"><span data-stu-id="53bb0-203">Log entries are written for stdin (the input), stdout (the output), and stderr (the error output).</span></span>|  
  
###  <a name="execute-sql-task"></a><a name="ExecuteSQL"></a> <span data-ttu-id="53bb0-204">Attività Esegui SQL</span><span class="sxs-lookup"><span data-stu-id="53bb0-204">Execute SQL Task</span></span>  
 <span data-ttu-id="53bb0-205">Nella tabella seguente è indicata la voce di log personalizzata disponibile per l'attività Esegui SQL.</span><span class="sxs-lookup"><span data-stu-id="53bb0-205">The following table describes the custom log entry for the Execute SQL task.</span></span>  
  
|<span data-ttu-id="53bb0-206">Voce di log</span><span class="sxs-lookup"><span data-stu-id="53bb0-206">Log entry</span></span>|<span data-ttu-id="53bb0-207">Descrizione</span><span class="sxs-lookup"><span data-stu-id="53bb0-207">Description</span></span>|  
|---------------|-----------------|  
|`ExecuteSQLExecutingQuery`|<span data-ttu-id="53bb0-208">Fornisce informazioni sulle fasi di esecuzione dell'istruzione SQL.</span><span class="sxs-lookup"><span data-stu-id="53bb0-208">Provides information about the execution phases of the SQL statement.</span></span> <span data-ttu-id="53bb0-209">Vengono scritte voci di log quando l'attività acquisisce la connessione al database, quando inizia a preparare l'istruzione SQL e al termine dell'esecuzione dell'istruzione SQL.</span><span class="sxs-lookup"><span data-stu-id="53bb0-209">Log entries are written when the task acquires connection to the database, when the task starts to prepare the SQL statement, and after the execution of the SQL statement is completed.</span></span> <span data-ttu-id="53bb0-210">La voce di log per la fase di preparazione include l'istruzione SQL utilizzata dall'attività.</span><span class="sxs-lookup"><span data-stu-id="53bb0-210">The log entry for the prepare phase includes the SQL statement that the task uses.</span></span>|  
  
###  <a name="file-system-task"></a><a name="FileSystem"></a> <span data-ttu-id="53bb0-211">Attività File system</span><span class="sxs-lookup"><span data-stu-id="53bb0-211">File System Task</span></span>  
 <span data-ttu-id="53bb0-212">Nella tabella seguente sono elencate le voci di log personalizzate disponibili per l'attività File system.</span><span class="sxs-lookup"><span data-stu-id="53bb0-212">The following table describes the custom log entry for the File System task.</span></span>  
  
|<span data-ttu-id="53bb0-213">Voce di log</span><span class="sxs-lookup"><span data-stu-id="53bb0-213">Log entry</span></span>|<span data-ttu-id="53bb0-214">Descrizione</span><span class="sxs-lookup"><span data-stu-id="53bb0-214">Description</span></span>|  
|---------------|-----------------|  
|`FileSystemOperation`|<span data-ttu-id="53bb0-215">Indica l'operazione eseguita dall'attività.</span><span class="sxs-lookup"><span data-stu-id="53bb0-215">Reports the operation that the task performs.</span></span> <span data-ttu-id="53bb0-216">Questa voce di log viene scritta all'inizio dell'operazione sul file system e include informazioni sull'origine e sulla destinazione.</span><span class="sxs-lookup"><span data-stu-id="53bb0-216">The log entry is written when the file system operation starts and includes information about the source and destination.</span></span>|  
  
###  <a name="ftp-task"></a><a name="FTP"></a> <span data-ttu-id="53bb0-217">Attività FTP</span><span class="sxs-lookup"><span data-stu-id="53bb0-217">FTP Task</span></span>  
 <span data-ttu-id="53bb0-218">Nella tabella seguente sono elencate le voci di log personalizzate disponibili per l'attività FTP.</span><span class="sxs-lookup"><span data-stu-id="53bb0-218">The following table lists the custom log entries for the FTP task.</span></span>  
  
|<span data-ttu-id="53bb0-219">Voce di log</span><span class="sxs-lookup"><span data-stu-id="53bb0-219">Log entry</span></span>|<span data-ttu-id="53bb0-220">Descrizione</span><span class="sxs-lookup"><span data-stu-id="53bb0-220">Description</span></span>|  
|---------------|-----------------|  
|`FTPConnectingToServer`|<span data-ttu-id="53bb0-221">Indica che l'attività ha stabilito una connessione al server FTP.</span><span class="sxs-lookup"><span data-stu-id="53bb0-221">Indicates that the task initiated a connection to the FTP server.</span></span>|  
|`FTPOperation`|<span data-ttu-id="53bb0-222">Specifica l'inizio e il tipo dell'operazione FTP eseguita dall'attività.</span><span class="sxs-lookup"><span data-stu-id="53bb0-222">Reports the beginning of and the type of FTP operation that the task performs.</span></span>|  
  
###  <a name="message-queue-task"></a><a name="MessageQueue"></a> <span data-ttu-id="53bb0-223">Attività Message Queue</span><span class="sxs-lookup"><span data-stu-id="53bb0-223">Message Queue Task</span></span>  
 <span data-ttu-id="53bb0-224">Nella tabella seguente sono elencate le voci di log personalizzate disponibili per l'attività Message Queue.</span><span class="sxs-lookup"><span data-stu-id="53bb0-224">The following table lists the custom log entries for the Message Queue task.</span></span>  
  
|<span data-ttu-id="53bb0-225">Voce di log</span><span class="sxs-lookup"><span data-stu-id="53bb0-225">Log entry</span></span>|<span data-ttu-id="53bb0-226">Descrizione</span><span class="sxs-lookup"><span data-stu-id="53bb0-226">Description</span></span>|  
|---------------|-----------------|  
|`MSMQAfterOpen`|<span data-ttu-id="53bb0-227">Indica che l'attività ha terminato l'apertura della coda di messaggi.</span><span class="sxs-lookup"><span data-stu-id="53bb0-227">Indicates that the task finished opening the message queue.</span></span>|  
|`MSMQBeforeOpen`|<span data-ttu-id="53bb0-228">Indica che l'attività ha iniziato ad aprire la coda di messaggi.</span><span class="sxs-lookup"><span data-stu-id="53bb0-228">Indicates that the task began to open the message queue.</span></span>|  
|`MSMQBeginReceive`|<span data-ttu-id="53bb0-229">Indica che l'attività ha iniziato a ricevere un messaggio.</span><span class="sxs-lookup"><span data-stu-id="53bb0-229">Indicates that the task began to receive a message.</span></span>|  
|`MSMQBeginSend`|<span data-ttu-id="53bb0-230">Indica che l'attività ha iniziato a inviare un messaggio.</span><span class="sxs-lookup"><span data-stu-id="53bb0-230">Indicates that the task began to send a message.</span></span>|  
|`MSMQEndReceive`|<span data-ttu-id="53bb0-231">Indica che l'attività ha terminato la ricezione di un messaggio.</span><span class="sxs-lookup"><span data-stu-id="53bb0-231">Indicates that the task finished receiving a message.</span></span>|  
|`MSMQEndSend`|<span data-ttu-id="53bb0-232">Indica che l'attività ha terminato l'invio di un messaggio.</span><span class="sxs-lookup"><span data-stu-id="53bb0-232">Indicates that the task finished sending a message</span></span>|  
|`MSMQTaskInfo`|<span data-ttu-id="53bb0-233">Offre informazioni descrittive sull'attività.</span><span class="sxs-lookup"><span data-stu-id="53bb0-233">Provides descriptive information about the task.</span></span>|  
|`MSMQTaskTimeOut`|<span data-ttu-id="53bb0-234">Indica che si è verificato il timeout dell'attività.</span><span class="sxs-lookup"><span data-stu-id="53bb0-234">Indicates that the task timed out.</span></span>|  
  
###  <a name="script-task"></a><a name="Script"></a> <span data-ttu-id="53bb0-235">Attività Script</span><span class="sxs-lookup"><span data-stu-id="53bb0-235">Script Task</span></span>  
 <span data-ttu-id="53bb0-236">Nella tabella seguente è indicata la voce di log personalizzata disponibile per l'attività Script.</span><span class="sxs-lookup"><span data-stu-id="53bb0-236">The following table describes the custom log entry for the Script task.</span></span>  
  
|<span data-ttu-id="53bb0-237">Voce di log</span><span class="sxs-lookup"><span data-stu-id="53bb0-237">Log entry</span></span>|<span data-ttu-id="53bb0-238">Descrizione</span><span class="sxs-lookup"><span data-stu-id="53bb0-238">Description</span></span>|  
|---------------|-----------------|  
|`ScriptTaskLogEntry`|<span data-ttu-id="53bb0-239">Restituisce i risultati dell'implementazione della registrazione nell'ambito dello script.</span><span class="sxs-lookup"><span data-stu-id="53bb0-239">Reports the results of implementing logging in the script.</span></span> <span data-ttu-id="53bb0-240">Viene scritta una voce di log per ogni chiamata al metodo `Log` dell'oggetto `Dts`.</span><span class="sxs-lookup"><span data-stu-id="53bb0-240">A log entry is written for each call to the `Log` method of the `Dts` object.</span></span> <span data-ttu-id="53bb0-241">Tale voce viene scritta al momento dell'esecuzione del codice.</span><span class="sxs-lookup"><span data-stu-id="53bb0-241">The entry is written when the code is run.</span></span> <span data-ttu-id="53bb0-242">Per altre informazioni, vedere [Registrazione nell'attività Script](extending-packages-scripting/task/logging-in-the-script-task.md).</span><span class="sxs-lookup"><span data-stu-id="53bb0-242">For more information, see [Logging in the Script Task](extending-packages-scripting/task/logging-in-the-script-task.md).</span></span>|  
  
###  <a name="send-mail-task"></a><a name="SendMail"></a> <span data-ttu-id="53bb0-243">Attività Invia messaggi</span><span class="sxs-lookup"><span data-stu-id="53bb0-243">Send Mail Task</span></span>  
 <span data-ttu-id="53bb0-244">Nella tabella seguente sono elencate le voci di log personalizzate disponibili per l'attività Invia messaggi.</span><span class="sxs-lookup"><span data-stu-id="53bb0-244">The following table lists the custom log entries for the Send Mail task.</span></span>  
  
|<span data-ttu-id="53bb0-245">Voce di log</span><span class="sxs-lookup"><span data-stu-id="53bb0-245">Log entry</span></span>|<span data-ttu-id="53bb0-246">Descrizione</span><span class="sxs-lookup"><span data-stu-id="53bb0-246">Description</span></span>|  
|---------------|-----------------|  
|`SendMailTaskBegin`|<span data-ttu-id="53bb0-247">Indica che l'attività ha iniziato a inviare un messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="53bb0-247">Indicates that the task began to send an e-mail message.</span></span>|  
|`SendMailTaskEnd`|<span data-ttu-id="53bb0-248">Indica che l'attività ha terminato l'invio di un messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="53bb0-248">Indicates that the task finished sending an e-mail message.</span></span>|  
|`SendMailTaskInfo`|<span data-ttu-id="53bb0-249">Offre informazioni descrittive sull'attività.</span><span class="sxs-lookup"><span data-stu-id="53bb0-249">Provides descriptive information about the task.</span></span>|  
  
###  <a name="transfer-database-task"></a><a name="TransferDatabase"></a> <span data-ttu-id="53bb0-250">Attività Trasferisci database</span><span class="sxs-lookup"><span data-stu-id="53bb0-250">Transfer Database Task</span></span>  
 <span data-ttu-id="53bb0-251">Nella tabella seguente sono elencate le voci di log personalizzate disponibili per l'attività Trasferisci database.</span><span class="sxs-lookup"><span data-stu-id="53bb0-251">The following table lists the custom log entries for the Transfer Database task.</span></span>  
  
|<span data-ttu-id="53bb0-252">Voce di log</span><span class="sxs-lookup"><span data-stu-id="53bb0-252">Log entry</span></span>|<span data-ttu-id="53bb0-253">Descrizione</span><span class="sxs-lookup"><span data-stu-id="53bb0-253">Description</span></span>|  
|---------------|-----------------|  
|`SourceDB`|<span data-ttu-id="53bb0-254">Specifica il database copiato dall'attività.</span><span class="sxs-lookup"><span data-stu-id="53bb0-254">Specifies the database that the task copied.</span></span>|  
|`SourceSQLServer`|<span data-ttu-id="53bb0-255">Specifica il computer da cui è stato copiato il database.</span><span class="sxs-lookup"><span data-stu-id="53bb0-255">Specifies the computer from which the database was copied.</span></span>|  
  
###  <a name="transfer-error-messages-task"></a><a name="TransferErrorMessages"></a> <span data-ttu-id="53bb0-256">Attività Trasferisci messaggi di errore</span><span class="sxs-lookup"><span data-stu-id="53bb0-256">Transfer Error Messages Task</span></span>  
 <span data-ttu-id="53bb0-257">Nella tabella seguente sono elencate le voci di log personalizzate disponibili per l'attività Trasferisci messaggi di errore.</span><span class="sxs-lookup"><span data-stu-id="53bb0-257">The following table lists the custom log entries for the Transfer Error Messages task.</span></span>  
  
|<span data-ttu-id="53bb0-258">Voce di log</span><span class="sxs-lookup"><span data-stu-id="53bb0-258">Log entry</span></span>|<span data-ttu-id="53bb0-259">Descrizione</span><span class="sxs-lookup"><span data-stu-id="53bb0-259">Description</span></span>|  
|---------------|-----------------|  
|`TransferErrorMessagesTaskFinishedTransferringObjects`|<span data-ttu-id="53bb0-260">Indica che l'attività ha terminato il trasferimento dei messaggi di errore.</span><span class="sxs-lookup"><span data-stu-id="53bb0-260">Indicates that the task finished transferring error messages.</span></span>|  
|`TransferErrorMessagesTaskStartTransferringObjects`|<span data-ttu-id="53bb0-261">Indica che l'attività ha iniziato a trasferire messaggi di errore.</span><span class="sxs-lookup"><span data-stu-id="53bb0-261">Indicates that the task started to transfer error messages.</span></span>|  
  
###  <a name="transfer-jobs-task"></a><a name="TransferJobs"></a> <span data-ttu-id="53bb0-262">Attività Trasferisci processi</span><span class="sxs-lookup"><span data-stu-id="53bb0-262">Transfer Jobs Task</span></span>  
 <span data-ttu-id="53bb0-263">Nella tabella seguente sono elencate le voci di log personalizzate disponibili per l'attività Trasferisci processi.</span><span class="sxs-lookup"><span data-stu-id="53bb0-263">The following table lists the custom log entries for the Transfer Jobs task.</span></span>  
  
|<span data-ttu-id="53bb0-264">Voce di log</span><span class="sxs-lookup"><span data-stu-id="53bb0-264">Log entry</span></span>|<span data-ttu-id="53bb0-265">Descrizione</span><span class="sxs-lookup"><span data-stu-id="53bb0-265">Description</span></span>|  
|---------------|-----------------|  
|`TransferJobsTaskFinishedTransferringObjects`|<span data-ttu-id="53bb0-266">Indica che l'attività ha terminato il trasferimento dei processi di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="53bb0-266">Indicates that the task finished transferring [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent jobs.</span></span>|  
|`TransferJobsTaskStartTransferringObjects`|<span data-ttu-id="53bb0-267">Indica che l'attività ha iniziato a trasferire processi di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="53bb0-267">Indicates that the task started to transfer [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent jobs.</span></span>|  
  
###  <a name="transfer-logins-task"></a><a name="TransferLogins"></a> <span data-ttu-id="53bb0-268">Attività Trasferisci account di accesso</span><span class="sxs-lookup"><span data-stu-id="53bb0-268">Transfer Logins Task</span></span>  
 <span data-ttu-id="53bb0-269">Nella tabella seguente sono elencate le voci di log personalizzate disponibili per l'attività Trasferisci account di accesso.</span><span class="sxs-lookup"><span data-stu-id="53bb0-269">The following table lists the custom log entries for the Transfer Logins task.</span></span>  
  
|<span data-ttu-id="53bb0-270">Voce di log</span><span class="sxs-lookup"><span data-stu-id="53bb0-270">Log entry</span></span>|<span data-ttu-id="53bb0-271">Descrizione</span><span class="sxs-lookup"><span data-stu-id="53bb0-271">Description</span></span>|  
|---------------|-----------------|  
|`TransferLoginsTaskFinishedTransferringObjects`|<span data-ttu-id="53bb0-272">Indica che l'attività ha terminato il trasferimento degli account di accesso.</span><span class="sxs-lookup"><span data-stu-id="53bb0-272">Indicates that the task finished transferring logins.</span></span>|  
|`TransferLoginsTaskStartTransferringObjects`|<span data-ttu-id="53bb0-273">Indica che l'attività ha iniziato a trasferire account di accesso.</span><span class="sxs-lookup"><span data-stu-id="53bb0-273">Indicates that the task started to transfer logins.</span></span>|  
  
###  <a name="transfer-master-stored-procedures-task"></a><a name="TransferMasterStoredProcedures"></a> <span data-ttu-id="53bb0-274">Attività Trasferisci stored procedure master</span><span class="sxs-lookup"><span data-stu-id="53bb0-274">Transfer Master Stored Procedures Task</span></span>  
 <span data-ttu-id="53bb0-275">Nella tabella seguente sono elencate le voci di log personalizzate disponibili per l'attività Trasferisci stored procedure master.</span><span class="sxs-lookup"><span data-stu-id="53bb0-275">The following table lists the custom log entries for the Transfer Master Stored Procedures task.</span></span>  
  
|<span data-ttu-id="53bb0-276">Voce di log</span><span class="sxs-lookup"><span data-stu-id="53bb0-276">Log entry</span></span>|<span data-ttu-id="53bb0-277">Descrizione</span><span class="sxs-lookup"><span data-stu-id="53bb0-277">Description</span></span>|  
|---------------|-----------------|  
|`TransferStoredProceduresTaskFinishedTransferringObjects`|<span data-ttu-id="53bb0-278">Indica che l'attività ha terminato il trasferimento delle stored procedure definite dall'utente archiviate nel database **master** .</span><span class="sxs-lookup"><span data-stu-id="53bb0-278">Indicates that the task finished transferring user-defined stored procedures that are stored in the **master** database.</span></span>|  
|`TransferStoredProceduresTaskStartTransferringObjects`|<span data-ttu-id="53bb0-279">Indica che l'attività ha iniziato a trasferire le stored procedure definite dall'utente archiviate nel database **master** .</span><span class="sxs-lookup"><span data-stu-id="53bb0-279">Indicates that the task started to transfer user-defined stored procedures that are stored in the **master** database.</span></span>|  
  
###  <a name="transfer-sql-server-objects-task"></a><a name="TransferSQLServerObjects"></a> <span data-ttu-id="53bb0-280">Attività Trasferisci oggetti di SQL Server</span><span class="sxs-lookup"><span data-stu-id="53bb0-280">Transfer SQL Server Objects Task</span></span>  
 <span data-ttu-id="53bb0-281">Nella tabella seguente sono elencate le voci di log personalizzate disponibili per l'attività Trasferisci oggetti di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="53bb0-281">The following table lists the custom log entries for the Transfer [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Objects task.</span></span>  
  
|<span data-ttu-id="53bb0-282">Voce di log</span><span class="sxs-lookup"><span data-stu-id="53bb0-282">Log entry</span></span>|<span data-ttu-id="53bb0-283">Descrizione</span><span class="sxs-lookup"><span data-stu-id="53bb0-283">Description</span></span>|  
|---------------|-----------------|  
|`TransferSqlServerObjectsTaskFinishedTransferringObjects`|<span data-ttu-id="53bb0-284">Indica che l'attività ha terminato il trasferimento degli oggetti di database di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="53bb0-284">Indicates that the task finished transferring [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database objects.</span></span>|  
|`TransferSqlServerObjectsTaskStartTransferringObjects`|<span data-ttu-id="53bb0-285">Indica che l'attività ha iniziato a trasferire oggetti di database di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="53bb0-285">Indicates that the task started to transfer [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database objects.</span></span>|  
  
###  <a name="web-services-task"></a><a name="WebServices"></a> <span data-ttu-id="53bb0-286">Attività Servizio Web</span><span class="sxs-lookup"><span data-stu-id="53bb0-286">Web Services Task</span></span>  
 <span data-ttu-id="53bb0-287">Nella tabella seguente sono elencate le voci di log personalizzate che è possibile abilitare per l'attività Servizio Web.</span><span class="sxs-lookup"><span data-stu-id="53bb0-287">The following table lists the custom log entries that you can enable for the Web Services task.</span></span>  
  
|<span data-ttu-id="53bb0-288">Voce di log</span><span class="sxs-lookup"><span data-stu-id="53bb0-288">Log entry</span></span>|<span data-ttu-id="53bb0-289">Descrizione</span><span class="sxs-lookup"><span data-stu-id="53bb0-289">Description</span></span>|  
|---------------|-----------------|  
|`WSTaskBegin`|<span data-ttu-id="53bb0-290">Indica che l'attività ha iniziato ad accedere a un servizio Web.</span><span class="sxs-lookup"><span data-stu-id="53bb0-290">The task began to access a Web service.</span></span>|  
|`WSTaskEnd`|<span data-ttu-id="53bb0-291">Indica che l'attività ha completato un metodo per il servizio Web.</span><span class="sxs-lookup"><span data-stu-id="53bb0-291">The task completed a Web service method.</span></span>|  
|`WSTaskInfo`|<span data-ttu-id="53bb0-292">Offre informazioni descrittive sull'attività.</span><span class="sxs-lookup"><span data-stu-id="53bb0-292">Descriptive information about the task.</span></span>|  
  
###  <a name="wmi-data-reader-task"></a><a name="WMIDataReader"></a> <span data-ttu-id="53bb0-293">Attività Lettore di dati WMI</span><span class="sxs-lookup"><span data-stu-id="53bb0-293">WMI Data Reader Task</span></span>  
 <span data-ttu-id="53bb0-294">Nella tabella seguente sono elencate le voci di log personalizzate disponibili per l'attività Lettore di dati WMI.</span><span class="sxs-lookup"><span data-stu-id="53bb0-294">The following table lists the custom log entries for the WMI Data Reader task.</span></span>  
  
|<span data-ttu-id="53bb0-295">Voce di log</span><span class="sxs-lookup"><span data-stu-id="53bb0-295">Log entry</span></span>|<span data-ttu-id="53bb0-296">Descrizione</span><span class="sxs-lookup"><span data-stu-id="53bb0-296">Description</span></span>|  
|---------------|-----------------|  
|`WMIDataReaderGettingWMIData`|<span data-ttu-id="53bb0-297">Indica che l'attività ha iniziato a leggere dati WMI.</span><span class="sxs-lookup"><span data-stu-id="53bb0-297">Indicates that the task began to read WMI data.</span></span>|  
|`WMIDataReaderOperation`|<span data-ttu-id="53bb0-298">Specifica la query WQL eseguita dall'attività.</span><span class="sxs-lookup"><span data-stu-id="53bb0-298">Reports the WQL query that the task ran.</span></span>|  
  
###  <a name="wmi-event-watcher-task"></a><a name="WMIEventWatcher"></a> <span data-ttu-id="53bb0-299">Attività Monitoraggio eventi WMI</span><span class="sxs-lookup"><span data-stu-id="53bb0-299">WMI Event Watcher Task</span></span>  
 <span data-ttu-id="53bb0-300">Nella tabella seguente sono elencate le voci di log personalizzate disponibili per l'attività Monitoraggio eventi WMI.</span><span class="sxs-lookup"><span data-stu-id="53bb0-300">The following table lists the custom log entries for the WMI Event Watcher task.</span></span>  
  
|<span data-ttu-id="53bb0-301">Voce di log</span><span class="sxs-lookup"><span data-stu-id="53bb0-301">Log entry</span></span>|<span data-ttu-id="53bb0-302">Descrizione</span><span class="sxs-lookup"><span data-stu-id="53bb0-302">Description</span></span>|  
|---------------|-----------------|  
|`WMIEventWatcherEventOccurred`|<span data-ttu-id="53bb0-303">Indica che l'evento monitorato dall'attività si è verificato.</span><span class="sxs-lookup"><span data-stu-id="53bb0-303">Denotes that the event occurred that the task was monitoring.</span></span>|  
|`WMIEventWatcherTimedout`|<span data-ttu-id="53bb0-304">Indica che si è verificato il timeout dell'attività.</span><span class="sxs-lookup"><span data-stu-id="53bb0-304">Indicates that the task timed out.</span></span>|  
|`WMIEventWatcherWatchingForWMIEvents`|<span data-ttu-id="53bb0-305">Indica che l'attività ha iniziato a eseguire la query WQL.</span><span class="sxs-lookup"><span data-stu-id="53bb0-305">Indicates that the task began to execute the WQL query.</span></span> <span data-ttu-id="53bb0-306">La voce include la query.</span><span class="sxs-lookup"><span data-stu-id="53bb0-306">The entry includes the query.</span></span>|  
  
###  <a name="xml-task"></a><a name="XML"></a> <span data-ttu-id="53bb0-307">Attività XML</span><span class="sxs-lookup"><span data-stu-id="53bb0-307">XML Task</span></span>  
 <span data-ttu-id="53bb0-308">Nella tabella seguente è indicata la voce di log personalizzata disponibile per l'attività XML.</span><span class="sxs-lookup"><span data-stu-id="53bb0-308">The following table describes the custom log entry for the XML task.</span></span>  
  
|<span data-ttu-id="53bb0-309">Voce di log</span><span class="sxs-lookup"><span data-stu-id="53bb0-309">Log entry</span></span>|<span data-ttu-id="53bb0-310">Descrizione</span><span class="sxs-lookup"><span data-stu-id="53bb0-310">Description</span></span>|  
|---------------|-----------------|  
|`XMLOperation`|<span data-ttu-id="53bb0-311">Fornisce informazioni sull'operazione eseguita dall'attività.</span><span class="sxs-lookup"><span data-stu-id="53bb0-311">Provides information about the operation that the task performs</span></span>|   
  
## <a name="see-also"></a><span data-ttu-id="53bb0-312">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="53bb0-312">See Also</span></span>  
 [<span data-ttu-id="53bb0-313">Registrazione di Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="53bb0-313">Integration Services &#40;SSIS&#41; Logging</span></span>](performance/integration-services-ssis-logging.md)  
  
