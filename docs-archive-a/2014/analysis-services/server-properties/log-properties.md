---
title: Proprietà log | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- QueryLogFileSize property
- QueryLogTableName property
- TraceBackgroundDistributionPeriod property
- TraceMaxRowsetSize property
- NullKeyConvertedToUnknown property
- CrashReportsFolder property
- TraceDefinitionFile property
- SQLDumperFlagsOn property
- KeyErrorLimit property
- SnapshotDefinitionFile property
- MinidumpErrorList property
- ErrorLogFileName property
- KeyDuplicate property
- IgnoreDataTruncation property
- logs [Analysis Services]
- Enabled property
- FileSizeMB property
- TraceFileWriteTrailerPeriod property
- TraceQueryResponseTextChunkSize property
- File property
- FileBufferSize property
- TraceRowsetBackgroundFlushPeriod property
- ErrorLogFileSize property
- TraceRequestParameters property
- KeyErrorLimitAction property
- CreateQueryLogTable property
- LogDir property
- TraceBackgroundFlushPeriod property
- TraceFileBufferSize property
- SQLDumperFlagsOff property
- QueryLogConnectionString property
- KeyNotFound property
- KeyErrorLogFile property
- TraceReportFQDN property
- KeyErrorAction property
- QueryLogFileName property
- MessageLogs property
- MiniDumpFlagsOn property
- SnapshotFrequencySec property
- QueryLogSampling property
- CreateAndSendCrashReports property
- LogDurationSec property
ms.assetid: 33fd90ee-cead-48f0-8ff9-9b458994c766
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3761ce3dca232db8968a2a7cba083dcc5554d792
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727167"
---
# <a name="log-properties"></a><span data-ttu-id="69b5b-102">Proprietà dei log</span><span class="sxs-lookup"><span data-stu-id="69b5b-102">Log Properties</span></span>
  [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="69b5b-103">supporta le proprietà dei log server elencate nelle tabelle seguenti.</span><span class="sxs-lookup"><span data-stu-id="69b5b-103">supports the log server properties listed in the following tables.</span></span> <span data-ttu-id="69b5b-104">Per altre informazioni sulle proprietà aggiuntive del server e sulla relativa impostazione, vedere [Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="69b5b-104">For more information about additional server properties and how to set them, see [Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md).</span></span>  
  
## <a name="general"></a><span data-ttu-id="69b5b-105">Generale</span><span class="sxs-lookup"><span data-stu-id="69b5b-105">General</span></span>  
 `File`  
 <span data-ttu-id="69b5b-106">Proprietà stringa che identifica il nome del file di log del server.</span><span class="sxs-lookup"><span data-stu-id="69b5b-106">A string property that identifies the name of the server log file.</span></span> <span data-ttu-id="69b5b-107">Questa proprietà viene applicata solo quando viene usato un file su disco per la registrazione invece che una tabella di database (condizione predefinita).</span><span class="sxs-lookup"><span data-stu-id="69b5b-107">This property only applies when a disk file is used for logging, as opposed to a database table (the default behavior).</span></span>  
  
 <span data-ttu-id="69b5b-108">Il valore predefinito di questa proprietà è msmdsrv.log.</span><span class="sxs-lookup"><span data-stu-id="69b5b-108">The default value for this property is msmdsrv.log.</span></span>  
  
 `FileBufferSize`  
 <span data-ttu-id="69b5b-109">Proprietà avanzata che deve essere modificata solo sotto la supervisione del servizio di supporto tecnico [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="69b5b-109">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MessageLogs`  
 <span data-ttu-id="69b5b-110">Proprietà avanzata che deve essere modificata solo sotto la supervisione del servizio di supporto tecnico [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="69b5b-110">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
## <a name="error-log"></a><span data-ttu-id="69b5b-111">log degli errori</span><span class="sxs-lookup"><span data-stu-id="69b5b-111">Error Log</span></span>  
 <span data-ttu-id="69b5b-112">È possibile impostare queste proprietà a livello di istanza del server per modificare i valori predefiniti per la configurazione errori visualizzati in altri strumenti e finestre di progettazione.</span><span class="sxs-lookup"><span data-stu-id="69b5b-112">You can set these properties at the server instance level to modify the default values for Error Configuration that appear in other tools and designers.</span></span> <span data-ttu-id="69b5b-113">Per ulteriori informazioni [, vedere la pagina relativa alla configurazione degli errori per l'elaborazione di cubi, partizioni e dimensioni &#40;SSAS-&#41;multidimensionali](../multidimensional-models/error-configuration-for-cube-partition-and-dimension-processing.md) <xref:Microsoft.AnalysisServices.MiningStructure.ErrorConfiguration%2A> .</span><span class="sxs-lookup"><span data-stu-id="69b5b-113">See [Error Configuration for Cube, Partition, and Dimension Processing &#40;SSAS - Multidimensional&#41;](../multidimensional-models/error-configuration-for-cube-partition-and-dimension-processing.md) and <xref:Microsoft.AnalysisServices.MiningStructure.ErrorConfiguration%2A> for more information.</span></span>  
  
 <span data-ttu-id="69b5b-114">**ErrorLog\ErrorLogFileName**</span><span class="sxs-lookup"><span data-stu-id="69b5b-114">**ErrorLog\ErrorLogFileName**</span></span>  
 <span data-ttu-id="69b5b-115">Proprietà usata come impostazione predefinita durante operazioni di elaborazione eseguite sul server.</span><span class="sxs-lookup"><span data-stu-id="69b5b-115">A property used as a default during processing operation performed by the server.</span></span>  
  
 <span data-ttu-id="69b5b-116">**ErrorLog\ErrorLogFileSize**</span><span class="sxs-lookup"><span data-stu-id="69b5b-116">**ErrorLog\ErrorLogFileSize**</span></span>  
 <span data-ttu-id="69b5b-117">Proprietà usata come impostazione predefinita durante operazioni di elaborazione eseguite sul server.</span><span class="sxs-lookup"><span data-stu-id="69b5b-117">A property used as a default during processing operation performed by the server.</span></span>  
  
 <span data-ttu-id="69b5b-118">**ErrorLog\KeyErrorAction**</span><span class="sxs-lookup"><span data-stu-id="69b5b-118">**ErrorLog\KeyErrorAction**</span></span>  
 <span data-ttu-id="69b5b-119">Specifica l'azione eseguita dal server quando si verifica un errore `KeyNotFound`.</span><span class="sxs-lookup"><span data-stu-id="69b5b-119">Specifies the action taken by the server when a `KeyNotFound` error occurs.</span></span> <span data-ttu-id="69b5b-120">Le risposte valide a questo errore sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="69b5b-120">Valid responses to this error include:</span></span>  
  
-   <span data-ttu-id="69b5b-121">`ConvertToUnknown`: indica al server di allocare il valore della chiave con errore al membro sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="69b5b-121">`ConvertToUnknown` tells the server to allocate the error key value to the unknown member.</span></span>  
  
-   <span data-ttu-id="69b5b-122">`DiscardRecord`: indica al server di escludere il record.</span><span class="sxs-lookup"><span data-stu-id="69b5b-122">`DiscardRecord` tells the server to exclude the record.</span></span>  
  
 <span data-ttu-id="69b5b-123">**ErrorLog\KeyErrorLogFile**</span><span class="sxs-lookup"><span data-stu-id="69b5b-123">**ErrorLog\KeyErrorLogFile**</span></span>  
 <span data-ttu-id="69b5b-124">Si tratta di un nome di file definito dall'utente che deve avere un'estensione di file log ed essere posizionato in una cartella in cui l'account del servizio dispone delle autorizzazioni di lettura-scrittura.</span><span class="sxs-lookup"><span data-stu-id="69b5b-124">This is a user-defined filename that must have a .log file extension, located in a folder on which the service account has read-write permissions.</span></span> <span data-ttu-id="69b5b-125">Il file di log conterrà solo gli errori generati durante l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="69b5b-125">This log file will only contain errors generated during processing.</span></span> <span data-ttu-id="69b5b-126">Se sono necessarie informazioni più dettagliate, usare utilità Traccia eventi.</span><span class="sxs-lookup"><span data-stu-id="69b5b-126">Use the Flight Recorder if you require more detailed information.</span></span>  
  
 <span data-ttu-id="69b5b-127">**ErrorLog\KeyErrorLimit**</span><span class="sxs-lookup"><span data-stu-id="69b5b-127">**ErrorLog\KeyErrorLimit**</span></span>  
 <span data-ttu-id="69b5b-128">Numero massimo di errori di integrità dei dati che il server consentirà prima di interrompere l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="69b5b-128">This is the maximum number of data integrity errors that the server will allow before failing the processing.</span></span> <span data-ttu-id="69b5b-129">Un valore pari a 1 indica che non vi sono limiti.</span><span class="sxs-lookup"><span data-stu-id="69b5b-129">A value of -1 indicates that there is no limit.</span></span> <span data-ttu-id="69b5b-130">L'impostazione predefinita è 0, che indica l'arresto dell'elaborazione dopo il primo errore.</span><span class="sxs-lookup"><span data-stu-id="69b5b-130">The default is 0, which means processing stops after the first error occurs.</span></span> <span data-ttu-id="69b5b-131">È inoltre possibile impostare come valore un numero intero.</span><span class="sxs-lookup"><span data-stu-id="69b5b-131">You can also set it to a whole number.</span></span>  
  
 <span data-ttu-id="69b5b-132">**ErrorLog\KeyErrorLimitAction**</span><span class="sxs-lookup"><span data-stu-id="69b5b-132">**ErrorLog\KeyErrorLimitAction**</span></span>  
 <span data-ttu-id="69b5b-133">Specifica l'azione eseguita dal server quando il numero di errori di chiave ha raggiunto il limite superiore.</span><span class="sxs-lookup"><span data-stu-id="69b5b-133">Specifies the action taken by the server when the number of key errors has reached the upper limit.</span></span> <span data-ttu-id="69b5b-134">Le risposte valide a questa azione sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="69b5b-134">Valid responses to this action include:</span></span>  
  
-   <span data-ttu-id="69b5b-135">`StopProcessing` indica al server di arrestare l'elaborazione quando il limite errori viene raggiunto.</span><span class="sxs-lookup"><span data-stu-id="69b5b-135">`StopProcessing` tells the server to stop processing when the error limit is reached.</span></span>  
  
-   <span data-ttu-id="69b5b-136">`StopLogging` indica al server di arrestare la registrazione degli errori quando il limite errori viene raggiunto, senza interrompere però l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="69b5b-136">`StopLogging` tells the server to stop logging errors when the error limit is reached, but allow processing to continue.</span></span>  
  
 <span data-ttu-id="69b5b-137">**ErrorLog\ LogErrorTypes\KeyNotFound**</span><span class="sxs-lookup"><span data-stu-id="69b5b-137">**ErrorLog\ LogErrorTypes\KeyNotFound**</span></span>  
 <span data-ttu-id="69b5b-138">Specifica l'azione eseguita dal server quando si verifica un errore `KeyNotFound`.</span><span class="sxs-lookup"><span data-stu-id="69b5b-138">Specifies the action taken by the server when a `KeyNotFound` error occurs.</span></span> <span data-ttu-id="69b5b-139">Le risposte valide a questo errore sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="69b5b-139">Valid responses to this error include:</span></span>  
  
-   <span data-ttu-id="69b5b-140">`IgnoreError`: indica al server di continuare l'elaborazione senza registrare l'errore né conteggiarlo ai fini del limite degli errori di chiave.</span><span class="sxs-lookup"><span data-stu-id="69b5b-140">`IgnoreError` tells the server to continue processing without logging the error or counting it towards the key error limit.</span></span> <span data-ttu-id="69b5b-141">Ignorando l'errore, si consente semplicemente la continuazione dell'elaborazione senza aggiungere l'errore al numero complessivo e senza registrarlo nella schermata o nel file di log.</span><span class="sxs-lookup"><span data-stu-id="69b5b-141">By ignoring the error, you simply allow processing to continue without adding to the error count or logging it to the screen or log file.</span></span> <span data-ttu-id="69b5b-142">Per il record specifico è presente un problema di integrità dei dati. Di conseguenza, il record non può essere aggiunto al database</span><span class="sxs-lookup"><span data-stu-id="69b5b-142">The record in question has a data integrity problem and cannot be added to the database.</span></span> <span data-ttu-id="69b5b-143">e verrà rimosso o aggregato al membro sconosciuto, come determinato dalla proprietà `KeyErrorAction`.</span><span class="sxs-lookup"><span data-stu-id="69b5b-143">The record will either be discarded or aggregated to Unknown Member, as determined by the `KeyErrorAction` property.</span></span>  
  
-   <span data-ttu-id="69b5b-144">`ReportAndContinue` indica al server di registrare l'errore, di conteggiarlo per il limite di errori di chiave e di continuare l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="69b5b-144">`ReportAndContinue` tells the server to log the error, count it towards the key error limit, and continue processing.</span></span> <span data-ttu-id="69b5b-145">Il record che ha attivato l'errore viene rimosso o convertito in membro sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="69b5b-145">The record triggering the error is discarded or converted to Unknown Member.</span></span>  
  
-   <span data-ttu-id="69b5b-146">`ReportAndStop` indica al server di registrare l'errore e di arrestare immediatamente l'elaborazione, indipendentemente dal limite di errori di chiave.</span><span class="sxs-lookup"><span data-stu-id="69b5b-146">`ReportAndStop` tells the server to log the error and stop processing immediately, regardless of the key error limit.</span></span> <span data-ttu-id="69b5b-147">Il record che ha attivato l'errore viene rimosso o convertito in membro sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="69b5b-147">The record triggering the error is discarded or converted to Unknown Member.</span></span>  
  
 <span data-ttu-id="69b5b-148">**ErrorLog\ LogErrorTypes\KeyDuplicate**</span><span class="sxs-lookup"><span data-stu-id="69b5b-148">**ErrorLog\ LogErrorTypes\KeyDuplicate**</span></span>  
 <span data-ttu-id="69b5b-149">Specifica l'azione eseguita dal server in caso di chiave duplicata.</span><span class="sxs-lookup"><span data-stu-id="69b5b-149">Specifies the action taken by the server when a duplicate key is found.</span></span> <span data-ttu-id="69b5b-150">I valori validi includono `IgnoreError` per continuare l'elaborazione come se non si fosse verificato alcun errore, `ReportAndContinue` per registrare l'errore e continuare l'elaborazione e `ReportAndStop` per registrare l'errore e arrestare immediatamente l'elaborazione, anche se il numero di errori è inferiore al limite.</span><span class="sxs-lookup"><span data-stu-id="69b5b-150">Valid values include `IgnoreError` to continue processing as if the error did not occur, `ReportAndContinue` to log the error and continue processing, and `ReportAndStop` to log the error and stop processing immediately, even if the error count is below the error limit.</span></span>  
  
 <span data-ttu-id="69b5b-151">**ErrorLog\ LogErrorTypes\NullKeyConvertedToUnknown**</span><span class="sxs-lookup"><span data-stu-id="69b5b-151">**ErrorLog\ LogErrorTypes\NullKeyConvertedToUnknown**</span></span>  
 <span data-ttu-id="69b5b-152">Specifica l'azione eseguita dal server quando una chiave Null è stata convertita nel membro sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="69b5b-152">Specifies the action taken by the server when a null key has been converted to Unknown Member.</span></span> <span data-ttu-id="69b5b-153">I valori validi includono `IgnoreError` per continuare l'elaborazione come se non si fosse verificato alcun errore, `ReportAndContinue` per registrare l'errore e continuare l'elaborazione e `ReportAndStop` per registrare l'errore e arrestare immediatamente l'elaborazione, anche se il numero di errori è inferiore al limite.</span><span class="sxs-lookup"><span data-stu-id="69b5b-153">Valid values include `IgnoreError` to continue processing as if the error did not occur, `ReportAndContinue` to log the error and continue processing, and `ReportAndStop` to log the error and stop processing immediately, even if the error count is below the error limit.</span></span>  
  
 <span data-ttu-id="69b5b-154">**ErrorLog\ LogErrorTypes\NullKeyNotAllowed**</span><span class="sxs-lookup"><span data-stu-id="69b5b-154">**ErrorLog\ LogErrorTypes\NullKeyNotAllowed**</span></span>  
 <span data-ttu-id="69b5b-155">Specifica l'azione eseguita dal server quando `NullProcessing` è impostato su `Error` per un attributo della dimensione.</span><span class="sxs-lookup"><span data-stu-id="69b5b-155">Specifies the action taken by the server when `NullProcessing` is set to `Error` for a dimension attribute.</span></span> <span data-ttu-id="69b5b-156">Viene generato un errore quando un valore Null non è consentito in un attributo specificato.</span><span class="sxs-lookup"><span data-stu-id="69b5b-156">An error is generated when a null value is not allowed in a given attribute.</span></span> <span data-ttu-id="69b5b-157">Questa proprietà di configurazione errori indica il passaggio successivo, ovvero la segnalazione dell'errore e la continuazione dell'elaborazione fino al raggiungimento del limite degli errori.</span><span class="sxs-lookup"><span data-stu-id="69b5b-157">This error configuration property informs the next step, which is to report the error and continue processing until the error limit is reached.</span></span> <span data-ttu-id="69b5b-158">I valori validi includono `IgnoreError` per continuare l'elaborazione come se non si fosse verificato alcun errore, `ReportAndContinue` per registrare l'errore e continuare l'elaborazione e `ReportAndStop` per registrare l'errore e arrestare immediatamente l'elaborazione, anche se il numero di errori è inferiore al limite.</span><span class="sxs-lookup"><span data-stu-id="69b5b-158">Valid values include `IgnoreError` to continue processing as if the error did not occur, `ReportAndContinue` to log the error and continue processing, and `ReportAndStop` to log the error and stop processing immediately, even if the error count is below the error limit.</span></span>  
  
 <span data-ttu-id="69b5b-159">**ErrorLog\ LogErrorTypes\CalculationError**</span><span class="sxs-lookup"><span data-stu-id="69b5b-159">**ErrorLog\ LogErrorTypes\CalculationError**</span></span>  
 <span data-ttu-id="69b5b-160">Proprietà usata come impostazione predefinita durante operazioni di elaborazione eseguite sul server.</span><span class="sxs-lookup"><span data-stu-id="69b5b-160">A property used as a default during processing operation performed by the server.</span></span>  
  
 <span data-ttu-id="69b5b-161">**ErrorLog\IgnoreDataTruncation**</span><span class="sxs-lookup"><span data-stu-id="69b5b-161">**ErrorLog\IgnoreDataTruncation**</span></span>  
 <span data-ttu-id="69b5b-162">Proprietà usata come impostazione predefinita durante operazioni di elaborazione eseguite sul server.</span><span class="sxs-lookup"><span data-stu-id="69b5b-162">A property used as a default during processing operation performed by the server.</span></span>  
  
## <a name="exception"></a><span data-ttu-id="69b5b-163">Eccezione</span><span class="sxs-lookup"><span data-stu-id="69b5b-163">Exception</span></span>  
 <span data-ttu-id="69b5b-164">**Exception\CreateAndSendCrashReports**</span><span class="sxs-lookup"><span data-stu-id="69b5b-164">**Exception\CreateAndSendCrashReports**</span></span>  
 <span data-ttu-id="69b5b-165">Proprietà avanzata che deve essere modificata solo sotto la supervisione del servizio di supporto tecnico [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="69b5b-165">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="69b5b-166">**Exception\CrashReportsFolder**</span><span class="sxs-lookup"><span data-stu-id="69b5b-166">**Exception\CrashReportsFolder**</span></span>  
 <span data-ttu-id="69b5b-167">Proprietà avanzata che deve essere modificata solo sotto la supervisione del servizio di supporto tecnico [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="69b5b-167">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="69b5b-168">**Exception\SQLDumperFlagsOn**</span><span class="sxs-lookup"><span data-stu-id="69b5b-168">**Exception\SQLDumperFlagsOn**</span></span>  
 <span data-ttu-id="69b5b-169">Proprietà avanzata che deve essere modificata solo sotto la supervisione del servizio di supporto tecnico [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="69b5b-169">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="69b5b-170">**Exception\SQLDumperFlagsOff**</span><span class="sxs-lookup"><span data-stu-id="69b5b-170">**Exception\SQLDumperFlagsOff**</span></span>  
 <span data-ttu-id="69b5b-171">Proprietà avanzata che deve essere modificata solo sotto la supervisione del servizio di supporto tecnico [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="69b5b-171">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="69b5b-172">**Exception\MiniDumpFlagsOn**</span><span class="sxs-lookup"><span data-stu-id="69b5b-172">**Exception\MiniDumpFlagsOn**</span></span>  
 <span data-ttu-id="69b5b-173">Proprietà avanzata che deve essere modificata solo sotto la supervisione del servizio di supporto tecnico [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="69b5b-173">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="69b5b-174">**Exception\MinidumpErrorList**</span><span class="sxs-lookup"><span data-stu-id="69b5b-174">**Exception\MinidumpErrorList**</span></span>  
 <span data-ttu-id="69b5b-175">Proprietà avanzata che deve essere modificata solo sotto la supervisione del servizio di supporto tecnico [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="69b5b-175">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
## <a name="flight-recorder"></a><span data-ttu-id="69b5b-176">Flight Recorder</span><span class="sxs-lookup"><span data-stu-id="69b5b-176">Flight Recorder</span></span>  
 <span data-ttu-id="69b5b-177">**FlightRecorder\Enabled**</span><span class="sxs-lookup"><span data-stu-id="69b5b-177">**FlightRecorder\Enabled**</span></span>  
 <span data-ttu-id="69b5b-178">Proprietà booleana che indica se la funzionalità Traccia eventi è abilitata.</span><span class="sxs-lookup"><span data-stu-id="69b5b-178">A Boolean property that indicates whether the flight recorder feature is enabled.</span></span>  
  
 <span data-ttu-id="69b5b-179">**FlightRecorder\FileSizeMB**</span><span class="sxs-lookup"><span data-stu-id="69b5b-179">**FlightRecorder\FileSizeMB**</span></span>  
 <span data-ttu-id="69b5b-180">Proprietà a valore integer a 32 bit con segno che definisce la dimensione in megabyte del file su disco della Traccia eventi.</span><span class="sxs-lookup"><span data-stu-id="69b5b-180">A signed 32-bit integer property that defines the size of the flight recorder disk file, in megabytes.</span></span>  
  
 <span data-ttu-id="69b5b-181">**FlightRecorder\LogDurationSec**</span><span class="sxs-lookup"><span data-stu-id="69b5b-181">**FlightRecorder\LogDurationSec**</span></span>  
 <span data-ttu-id="69b5b-182">Proprietà a valore integer a 32 bit con segno che definisce la frequenza in secondi del rollover della Traccia eventi.</span><span class="sxs-lookup"><span data-stu-id="69b5b-182">A signed 32-bit integer property that defines the frequency that the flight recorder is rolled over, in seconds.</span></span>  
  
 <span data-ttu-id="69b5b-183">**FlightRecorder\SnapshotDefinitionFile**</span><span class="sxs-lookup"><span data-stu-id="69b5b-183">**FlightRecorder\SnapshotDefinitionFile**</span></span>  
 <span data-ttu-id="69b5b-184">Proprietà stringa che definisce il nome del file di definizione dello snapshot, contenente comandi di individuazione inviati al server quando viene eseguito uno snapshot.</span><span class="sxs-lookup"><span data-stu-id="69b5b-184">A string property that defines the name of the snapshot definition file, containing discover commands that are issued to the server when a snapshot is taken.</span></span>  
  
 <span data-ttu-id="69b5b-185">Il valore predefinito di questa proprietà è vuoto, al quale per impostazione predefinita viene assegnato il nome di file FlightRecorderSnapshotDef.xml.</span><span class="sxs-lookup"><span data-stu-id="69b5b-185">The default value for this property is blank, which in turn defaults to file name FlightRecorderSnapshotDef.xml.</span></span>  
  
 <span data-ttu-id="69b5b-186">**FlightRecorder\SnapshotFrequencySec**</span><span class="sxs-lookup"><span data-stu-id="69b5b-186">**FlightRecorder\SnapshotFrequencySec**</span></span>  
 <span data-ttu-id="69b5b-187">Proprietà a valore integer a 32 bit con segno che definisce la frequenza in secondi dello snapshot.</span><span class="sxs-lookup"><span data-stu-id="69b5b-187">A signed 32-bit integer property that defines the snapshot frequency, in seconds.</span></span>  
  
 <span data-ttu-id="69b5b-188">**FlightRecorder\TraceDefinitionFile**</span><span class="sxs-lookup"><span data-stu-id="69b5b-188">**FlightRecorder\TraceDefinitionFile**</span></span>  
 <span data-ttu-id="69b5b-189">Proprietà stringa che identifica il nome del file di definizione della traccia eventi.</span><span class="sxs-lookup"><span data-stu-id="69b5b-189">A string property that specifies the name of the flight recorder trace definition file.</span></span>  
  
 <span data-ttu-id="69b5b-190">Il valore predefinito di questa proprietà è vuoto, al quale per impostazione predefinita viene assegnato il nome di file FlightRecorderTraceDef.xml.</span><span class="sxs-lookup"><span data-stu-id="69b5b-190">The default value for this property is blank, which in turn defaults to FlightRecorderTraceDef.xml.</span></span>  
  
## <a name="query-log"></a><span data-ttu-id="69b5b-191">Query Log</span><span class="sxs-lookup"><span data-stu-id="69b5b-191">Query Log</span></span>  
 <span data-ttu-id="69b5b-192">**Si applica a:** Solo modalità server multidimensionale</span><span class="sxs-lookup"><span data-stu-id="69b5b-192">**Applies to:** Multidimensional server mode only</span></span>  
  
 <span data-ttu-id="69b5b-193">**QueryLog\QueryLogFileName**</span><span class="sxs-lookup"><span data-stu-id="69b5b-193">**QueryLog\QueryLogFileName**</span></span>  
 <span data-ttu-id="69b5b-194">Proprietà stringa che identifica il nome del file di log delle query.</span><span class="sxs-lookup"><span data-stu-id="69b5b-194">A string property that specifies the name of the query log file.</span></span> <span data-ttu-id="69b5b-195">Questa proprietà viene applicata solo quando viene usato un file su disco per la registrazione invece che una tabella di database (condizione predefinita).</span><span class="sxs-lookup"><span data-stu-id="69b5b-195">This property only applies when a disk file is used for logging, as opposed to a database table (the default behavior).</span></span>  
  
 <span data-ttu-id="69b5b-196">**QueryLog\QueryLogSampling**</span><span class="sxs-lookup"><span data-stu-id="69b5b-196">**QueryLog\QueryLogSampling**</span></span>  
 <span data-ttu-id="69b5b-197">Proprietà a valore integer a 32 bit con segno che definisce la frequenza di campionamento del log delle query.</span><span class="sxs-lookup"><span data-stu-id="69b5b-197">A signed 32-bit integer property that specifies the query log sampling rate.</span></span>  
  
 <span data-ttu-id="69b5b-198">Il valore predefinito di questa proprietà è 10, corrispondente alla registrazione di 1 query di server su 10.</span><span class="sxs-lookup"><span data-stu-id="69b5b-198">The default value for this property is 10, meaning that 1 out of every 10 server queries is logged.</span></span>  
  
 <span data-ttu-id="69b5b-199">**QueryLog\QueryLogFileSize**</span><span class="sxs-lookup"><span data-stu-id="69b5b-199">**QueryLog\QueryLogFileSize**</span></span>  
 <span data-ttu-id="69b5b-200">Proprietà avanzata che deve essere modificata solo sotto la supervisione del servizio di supporto tecnico [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="69b5b-200">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="69b5b-201">**QueryLog\QueryLogConnectionString**</span><span class="sxs-lookup"><span data-stu-id="69b5b-201">**QueryLog\QueryLogConnectionString**</span></span>  
 <span data-ttu-id="69b5b-202">Proprietà stringa che identifica la connessione al database del log delle query.</span><span class="sxs-lookup"><span data-stu-id="69b5b-202">A string property that specifies the connection to the query log database.</span></span>  
  
 <span data-ttu-id="69b5b-203">**QueryLog\QueryLogTableName**</span><span class="sxs-lookup"><span data-stu-id="69b5b-203">**QueryLog\QueryLogTableName**</span></span>  
 <span data-ttu-id="69b5b-204">Proprietà stringa che identifica il nome della tabella del log delle query.</span><span class="sxs-lookup"><span data-stu-id="69b5b-204">A string property that specifies the name of the query log table.</span></span>  
  
 <span data-ttu-id="69b5b-205">Il valore predefinito di questa proprietà è OlapQueryLog.</span><span class="sxs-lookup"><span data-stu-id="69b5b-205">The default value for this property is OlapQueryLog.</span></span>  
  
 <span data-ttu-id="69b5b-206">**QueryLog\CreateQueryLogTable**</span><span class="sxs-lookup"><span data-stu-id="69b5b-206">**QueryLog\CreateQueryLogTable**</span></span>  
 <span data-ttu-id="69b5b-207">Proprietà booleana che indica se creare la tabella del log delle query.</span><span class="sxs-lookup"><span data-stu-id="69b5b-207">A Boolean property that specifies whether to create the query log table.</span></span>  
  
 <span data-ttu-id="69b5b-208">Il valore predefinito di questa proprietà è False e indica che il server non crea automaticamente la tabella del log e non registra eventi di query.</span><span class="sxs-lookup"><span data-stu-id="69b5b-208">The default value for this property is false, which indicates the server will not automatically create the log table and will not log query events.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="69b5b-209">Per ulteriori informazioni sulla configurazione del log di query, vedere [operazioni di log in Analysis Services](../instances/log-operations-in-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="69b5b-209">For more information about configuring the query log, see [Log operations in Analysis Services](../instances/log-operations-in-analysis-services.md).</span></span>  
  
## <a name="trace"></a><span data-ttu-id="69b5b-210">Trace</span><span class="sxs-lookup"><span data-stu-id="69b5b-210">Trace</span></span>  
 <span data-ttu-id="69b5b-211">**Trace\TraceBackgroundDistributionPeriod**</span><span class="sxs-lookup"><span data-stu-id="69b5b-211">**Trace\TraceBackgroundDistributionPeriod**</span></span>  
 <span data-ttu-id="69b5b-212">Proprietà avanzata che deve essere modificata solo sotto la supervisione del servizio di supporto tecnico [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="69b5b-212">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="69b5b-213">**Trace\TraceBackgroundFlushPeriod**</span><span class="sxs-lookup"><span data-stu-id="69b5b-213">**Trace\TraceBackgroundFlushPeriod**</span></span>  
 <span data-ttu-id="69b5b-214">Proprietà avanzata che deve essere modificata solo sotto la supervisione del servizio di supporto tecnico [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="69b5b-214">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="69b5b-215">**Trace\TraceFileBufferSize**</span><span class="sxs-lookup"><span data-stu-id="69b5b-215">**Trace\TraceFileBufferSize**</span></span>  
 <span data-ttu-id="69b5b-216">Proprietà avanzata che deve essere modificata solo sotto la supervisione del servizio di supporto tecnico [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="69b5b-216">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="69b5b-217">**Trace\TraceFileWriteTrailerPeriod**</span><span class="sxs-lookup"><span data-stu-id="69b5b-217">**Trace\TraceFileWriteTrailerPeriod**</span></span>  
 <span data-ttu-id="69b5b-218">Proprietà avanzata che deve essere modificata solo sotto la supervisione del servizio di supporto tecnico [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="69b5b-218">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="69b5b-219">**Trace\TraceMaxRowsetSize**</span><span class="sxs-lookup"><span data-stu-id="69b5b-219">**Trace\TraceMaxRowsetSize**</span></span>  
 <span data-ttu-id="69b5b-220">Proprietà avanzata che deve essere modificata solo sotto la supervisione del servizio di supporto tecnico [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="69b5b-220">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="69b5b-221">**Trace\TraceProtocolTraffic**</span><span class="sxs-lookup"><span data-stu-id="69b5b-221">**Trace\TraceProtocolTraffic**</span></span>  
 <span data-ttu-id="69b5b-222">Proprietà avanzata che deve essere modificata solo sotto la supervisione del servizio di supporto tecnico [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="69b5b-222">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="69b5b-223">**Trace\TraceQueryResponseTextChunkSize**</span><span class="sxs-lookup"><span data-stu-id="69b5b-223">**Trace\TraceQueryResponseTextChunkSize**</span></span>  
 <span data-ttu-id="69b5b-224">Proprietà avanzata che deve essere modificata solo sotto la supervisione del servizio di supporto tecnico [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="69b5b-224">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="69b5b-225">**Trace\TraceReportFQDN**</span><span class="sxs-lookup"><span data-stu-id="69b5b-225">**Trace\TraceReportFQDN**</span></span>  
 <span data-ttu-id="69b5b-226">Proprietà avanzata che deve essere modificata solo sotto la supervisione del servizio di supporto tecnico [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="69b5b-226">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="69b5b-227">**Trace\TraceRequestParameters**</span><span class="sxs-lookup"><span data-stu-id="69b5b-227">**Trace\TraceRequestParameters**</span></span>  
 <span data-ttu-id="69b5b-228">Proprietà avanzata che deve essere modificata solo sotto la supervisione del servizio di supporto tecnico [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="69b5b-228">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="69b5b-229">**Trace\TraceRowsetBackgroundFlushPeriod**</span><span class="sxs-lookup"><span data-stu-id="69b5b-229">**Trace\TraceRowsetBackgroundFlushPeriod**</span></span>  
 <span data-ttu-id="69b5b-230">Proprietà avanzata che deve essere modificata solo sotto la supervisione del servizio di supporto tecnico [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="69b5b-230">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69b5b-231">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="69b5b-231">See Also</span></span>  
 <span data-ttu-id="69b5b-232">[Configurare le proprietà del server in Analysis Services](server-properties-in-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="69b5b-232">[Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md) </span></span>  
 [<span data-ttu-id="69b5b-233">Determinare la modalità server di un'istanza di Analysis Services</span><span class="sxs-lookup"><span data-stu-id="69b5b-233">Determine the Server Mode of an Analysis Services Instance</span></span>](../instances/determine-the-server-mode-of-an-analysis-services-instance.md)  
  
  
