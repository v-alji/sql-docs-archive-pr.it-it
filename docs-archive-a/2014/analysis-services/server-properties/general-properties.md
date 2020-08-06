---
title: Proprietà generali | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- IdleConnectionTimeout property
- InstanceVisible property
- TempDir property
- AdminTimeout property
- MinIdleSessionTimeout property
- MaxIdleSessionTimeout property
- IdleOrphanSessionTimeout property
- BackupDir property
- CommitTimeout property
- ExternalCommandTimeout property
- Enabled property
- ForceCommitTimeout property
- Port property
- CoordinatorShutdownMode property
- ServerTimeout property
- AllowedBrowsingFolders property
- CoordinatorCancelCount property
- DataDir property
- CoordinatorQueryMaxThreads property
- CoordinatorExecutionMode property
- ExternalConnectionTimeout property
- CollationName property
- EnableFast1033Locale property
- CoordinatorBuildMaxThreads property
- Language property
- StatisticsStoreSize property
- RepositoryConnectionString property
ms.assetid: 88a8117c-396a-469f-a62d-c6f262504021
author: minewiskan
ms.author: owend
ms.openlocfilehash: ca746a1bb57e84cf0f6a8f47622b118c7180eb1c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727179"
---
# <a name="general-properties"></a><span data-ttu-id="ac3ae-102">Proprietà generali</span><span class="sxs-lookup"><span data-stu-id="ac3ae-102">General Properties</span></span>
  [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="ac3ae-103">supporta le proprietà del server elencate nelle tabelle seguenti.</span><span class="sxs-lookup"><span data-stu-id="ac3ae-103">supports the server properties listed in the following tables.</span></span> <span data-ttu-id="ac3ae-104">In questo argomento vengono documentate le proprietà del server disponibili nel file msmdsrv.ini che non sono incluse in una sezione specifica, ad esempio Sicurezza, Rete o Pool di thread.</span><span class="sxs-lookup"><span data-stu-id="ac3ae-104">This topic documents those server properties in the msmdsrv.ini file that are not otherwise included in a specific section, such as Security, Network, or ThreadPool.</span></span> <span data-ttu-id="ac3ae-105">Per altre informazioni sulle proprietà aggiuntive del server e sulla relativa impostazione, vedere [Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="ac3ae-105">For more information about additional server properties and how to set them, see [Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md).</span></span>  
  
 <span data-ttu-id="ac3ae-106">**Si applica a:** modalità server multidimensionale e tabulare, se non specificato diversamente.</span><span class="sxs-lookup"><span data-stu-id="ac3ae-106">**Applies to:** Multidimensional and Tabular server mode, unless noted otherwise</span></span>  
  
## <a name="non-specific-category"></a><span data-ttu-id="ac3ae-107">Categoria Non-Specific</span><span class="sxs-lookup"><span data-stu-id="ac3ae-107">Non-Specific Category</span></span>  
 `AdminTimeout`  
 <span data-ttu-id="ac3ae-108">Proprietà Integer a 32 bit con segno che definisce il timeout per l'amministratore in secondi.</span><span class="sxs-lookup"><span data-stu-id="ac3ae-108">A signed 32-bit integer property that defines the administrator timeout in seconds.</span></span> <span data-ttu-id="ac3ae-109">Si tratta di una proprietà avanzata che deve essere modificata solo sotto la supervisione del servizio di supporto tecnico [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ac3ae-109">This is an advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="ac3ae-110">Il valore predefinito di questa proprietà è zero (0), corrispondente all'assenza di un timeout.</span><span class="sxs-lookup"><span data-stu-id="ac3ae-110">The default value for this property is zero (0), which indicates there is no timeout.</span></span>  
  
 `AllowedBrowsingFolders`  
 <span data-ttu-id="ac3ae-111">Proprietà stringa che specifica in un elenco delimitato le cartelle che è possibile esplorare durante il salvataggio, l'apertura e la ricerca di file nelle finestra di dialogo di Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="ac3ae-111">A string property that specifies in a delimited list the folders that can be browsed when saving, opening, and finding files in Analysis Services dialog boxes.</span></span> <span data-ttu-id="ac3ae-112">È necessario che l'account del servizio Analysis Services abbia letto e scritto le autorizzazioni a qualsiasi cartella aggiunta all'elenco.</span><span class="sxs-lookup"><span data-stu-id="ac3ae-112">The Analysis Services service account must have read and write permissions to any folders that you add to the list.</span></span>  
  
 `BackupDir`  
 <span data-ttu-id="ac3ae-113">Proprietà di stringa che identifica il nome della directory in cui vengono archiviati i file di backup per impostazione predefinita, nel caso in cui non sia stato specificato un percorso come parte del comando backup.</span><span class="sxs-lookup"><span data-stu-id="ac3ae-113">A string property that identifies the name of the directory where backup files are stored by default, in the event a path is not specified as part of the Backup command.</span></span>  
  
 `CollationName`  
 <span data-ttu-id="ac3ae-114">Proprietà di stringa che identifica le regole di confronto del server.</span><span class="sxs-lookup"><span data-stu-id="ac3ae-114">A string property that identifies the server collation.</span></span> <span data-ttu-id="ac3ae-115">Per altre informazioni, vedere [Lingue e regole di confronto &#40;Analysis Services&#41;](../languages-and-collations-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="ac3ae-115">For more information, see [Languages and Collations &#40;Analysis Services&#41;](../languages-and-collations-analysis-services.md).</span></span>  
  
 `CommitTimeout`  
 <span data-ttu-id="ac3ae-116">Proprietà Integer che specifica per quanto tempo (in millisecondi) il server attenderà prima di acquisire un blocco in scrittura allo scopo di eseguire il commit di una transazione.</span><span class="sxs-lookup"><span data-stu-id="ac3ae-116">An integer property that specifies how long (in milliseconds) the server will wait to acquire a write lock for the purpose of committing a transaction.</span></span> <span data-ttu-id="ac3ae-117">Un periodo di attesa è spesso necessario perché il server deve attendere che eventuali altri blocchi vengano rilasciati prima di acquisire un blocco in scrittura per il commit della transazione.</span><span class="sxs-lookup"><span data-stu-id="ac3ae-117">A waiting period is often required because the server must wait for other locks to be released before it can take a write lock that commits the transaction.</span></span>  
  
 <span data-ttu-id="ac3ae-118">Il valore predefinito di questa proprietà è zero (0). Ciò significa che il server attenderà per un periodo di tempo indefinito.</span><span class="sxs-lookup"><span data-stu-id="ac3ae-118">The default value for this property is zero (0), which indicates that the server will wait indefinitely.</span></span> <span data-ttu-id="ac3ae-119">Per altre informazioni sulle proprietà correlate al blocco, vedere [SQL Server 2008 R2 Analysis Services Operations Guide](https://go.microsoft.com/fwlink/?LinkID=225539)(Guida operativa di SQL Server 2008 R2 Analysis Services).</span><span class="sxs-lookup"><span data-stu-id="ac3ae-119">For more information about lock-related properties, see [SQL Server 2008 R2 Analysis Services Operations Guide](https://go.microsoft.com/fwlink/?LinkID=225539).</span></span>  
  
 `CoordinatorBuildMaxThreads`  
 <span data-ttu-id="ac3ae-120">Proprietà Integer a 32 bit con segno che definisce il numero massimo di thread allocati alla compilazione di indici di partizioni.</span><span class="sxs-lookup"><span data-stu-id="ac3ae-120">A signed 32-bit integer property that defines the maximum number of threads allocated to building partition indexes.</span></span> <span data-ttu-id="ac3ae-121">Per rendere più veloce l'indicizzazione delle partizioni a scapito della quantità di memoria utilizzata, è necessario aumentare il valore di questa proprietà.</span><span class="sxs-lookup"><span data-stu-id="ac3ae-121">Increase this value in order to speed-up partition indexing, at the cost of memory usage.</span></span> <span data-ttu-id="ac3ae-122">Per altre informazioni su questa proprietà, vedere [SQL Server 2008 R2 Analysis Services Operations Guide](https://go.microsoft.com/fwlink/?LinkID=225539)(Guida operativa di SQL Server 2008 R2 Analysis Services).</span><span class="sxs-lookup"><span data-stu-id="ac3ae-122">For more information about this property, see [SQL Server 2008 R2 Analysis Services Operations Guide](https://go.microsoft.com/fwlink/?LinkID=225539).</span></span>  
  
 `CoordinatorCancelCount`  
 <span data-ttu-id="ac3ae-123">Proprietà Integer a 32 bit con segno che definisce la frequenza con la quale il server controlla se si è verificato un evento di annullamento (basato su un conteggio di iterazione interno).</span><span class="sxs-lookup"><span data-stu-id="ac3ae-123">A signed 32-bit integer property that defines how frequently the server should check whether a Cancel event occurred (based on internal iteration count).</span></span> <span data-ttu-id="ac3ae-124">Per aumentare la frequenza di controllo degli eventi di annullamento, a scapito delle prestazioni generali, è necessario diminuire il valore di questa proprietà.</span><span class="sxs-lookup"><span data-stu-id="ac3ae-124">Decrease this number in order to check for Cancel more frequently, at the expense of general performance.</span></span>  
  
 <span data-ttu-id="ac3ae-125">`CoordinatorCancelCount` in modalità server tabulare viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="ac3ae-125">`CoordinatorCancelCount` is ignored in tabular server mode.</span></span>  
  
 `CoordinatorExecutionMode`  
 <span data-ttu-id="ac3ae-126">Proprietà Integer a 32 bit con segno che definisce il numero massimo di operazioni parallele accettate dal server, comprese operazioni di elaborazione e query.</span><span class="sxs-lookup"><span data-stu-id="ac3ae-126">A signed 32-bit integer property that defines the maximum number of parallel operations the server will attempt, including processing and querying operations.</span></span> <span data-ttu-id="ac3ae-127">Zero (0) indica che il numero delle operazioni verrà deciso dal server in base a un algoritmo interno.</span><span class="sxs-lookup"><span data-stu-id="ac3ae-127">Zero (0) indicates that the server will decide, based on an internal algorithm.</span></span> <span data-ttu-id="ac3ae-128">Un numero positivo indica il numero massimo totale delle operazioni.</span><span class="sxs-lookup"><span data-stu-id="ac3ae-128">A positive number indicates the maximum number of operations in total.</span></span> <span data-ttu-id="ac3ae-129">Un numero negativo indica il numero massimo di operazioni per processore.</span><span class="sxs-lookup"><span data-stu-id="ac3ae-129">A negative number, with the sign reversed, indicates the maximum number of operations per processor.</span></span>  
  
 <span data-ttu-id="ac3ae-130">`CoordinatorExecutionMode` in modalità server tabulare viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="ac3ae-130">`CoordinatorExecutionMode` is ignored in tabular server mode.</span></span>  
  
 <span data-ttu-id="ac3ae-131">Il valore predefinito di questa proprietà è -4. Ciò significa che il funzionamento del server è limitato a 4 operazioni parallele per processore.</span><span class="sxs-lookup"><span data-stu-id="ac3ae-131">The default value for this property is -4, which indicates the server is limited to 4 parallel operations per processor.</span></span> <span data-ttu-id="ac3ae-132">Per altre informazioni su questa proprietà, vedere [SQL Server 2008 R2 Analysis Services Operations Guide](https://go.microsoft.com/fwlink/?LinkID=225539)(Guida operativa di SQL Server 2008 R2 Analysis Services).</span><span class="sxs-lookup"><span data-stu-id="ac3ae-132">For more information about this property, see [SQL Server 2008 R2 Analysis Services Operations Guide](https://go.microsoft.com/fwlink/?LinkID=225539).</span></span>  
  
 `CoordinatorQueryMaxThreads`  
 <span data-ttu-id="ac3ae-133">Proprietà Integer a 32 bit con segno che definisce il numero massimo di thread per segmento di partizione durante la risoluzione delle query.</span><span class="sxs-lookup"><span data-stu-id="ac3ae-133">A signed 32-bit integer property that defines the maximum number of threads per partition segment during query resolution.</span></span> <span data-ttu-id="ac3ae-134">Minore è il numero di utenti concorrenti e maggiore è il valore assegnabile a questa proprietà, a scapito della memoria.</span><span class="sxs-lookup"><span data-stu-id="ac3ae-134">The fewer the number of concurrent users, the higher this value can be, at the cost of memory.</span></span> <span data-ttu-id="ac3ae-135">Viceversa, se il numero di utenti concorrente è elevato, è necessario abbassare il valore di questa proprietà.</span><span class="sxs-lookup"><span data-stu-id="ac3ae-135">Conversely, it may need to be lowered if there are a large number of concurrent users.</span></span>  
  
 `CoordinatorShutdownMode`  
 <span data-ttu-id="ac3ae-136">Proprietà booleana che definisce la modalità di arresto del coordinatore.</span><span class="sxs-lookup"><span data-stu-id="ac3ae-136">A Boolean property that defines coordinator shutdown mode.</span></span> <span data-ttu-id="ac3ae-137">Si tratta di una proprietà avanzata che deve essere modificata solo sotto la supervisione del servizio di supporto tecnico [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ac3ae-137">This is an advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DataDir`  
 <span data-ttu-id="ac3ae-138">Proprietà di stringa che consente l'identificazione del nome della directory in cui sono archiviati i dati.</span><span class="sxs-lookup"><span data-stu-id="ac3ae-138">A string property that identifies the name of the directory where data is stored.</span></span>  
  
 `DeploymentMode`  
 <span data-ttu-id="ac3ae-139">Consente di determinare il contesto operativo di un'istanza del server Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="ac3ae-139">Determines the operational context of an Analysis Services server instance.</span></span> <span data-ttu-id="ac3ae-140">Questa proprietà viene definità modalità server ' in finestre di dialogo, messaggi e documentazione.</span><span class="sxs-lookup"><span data-stu-id="ac3ae-140">This property is referred to as 'server mode' in dialog boxes, messages, and documentation.</span></span> <span data-ttu-id="ac3ae-141">Questa proprietà viene configurata tramite il programma di installazione di SQL Server in base alla modalità server selezionata durante l'installazione di Analysis Services</span><span class="sxs-lookup"><span data-stu-id="ac3ae-141">This property is configured by SQL Server Setup based on the server mode you selected when installing Analysis Services.</span></span> <span data-ttu-id="ac3ae-142">e deve essere considerata solo per uso interno, usando sempre il valore specificato dal programma di installazione.</span><span class="sxs-lookup"><span data-stu-id="ac3ae-142">This property should be considered internal only, always using the value specified by Setup.</span></span>  
  
 <span data-ttu-id="ac3ae-143">Tra i valori validi per questa proprietà sono inclusi i seguenti:</span><span class="sxs-lookup"><span data-stu-id="ac3ae-143">Valid values for this property include the following:</span></span>  
  
|<span data-ttu-id="ac3ae-144">Valore</span><span class="sxs-lookup"><span data-stu-id="ac3ae-144">Value</span></span>|<span data-ttu-id="ac3ae-145">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ac3ae-145">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ac3ae-146">0</span><span class="sxs-lookup"><span data-stu-id="ac3ae-146">0</span></span>|<span data-ttu-id="ac3ae-147">Rappresenta il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="ac3ae-147">This is the default value.</span></span> <span data-ttu-id="ac3ae-148">Specifica la modalità multidimensionale, usata per i database multidimensionali che usano l'archiviazione MOLAP, HOLAP e ROLAP, nonché i modelli di data mining.</span><span class="sxs-lookup"><span data-stu-id="ac3ae-148">It specifies multidimensional mode, used to service multidimensional databases that use MOLAP, HOLAP, and ROLAP storage, as well as data mining models.</span></span>|  
|<span data-ttu-id="ac3ae-149">1</span><span class="sxs-lookup"><span data-stu-id="ac3ae-149">1</span></span>|<span data-ttu-id="ac3ae-150">Consente di specificare le istanze di Analysis Services installate come parte di una distribuzione di PowerPivot per SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ac3ae-150">Specifies Analysis Services instances that were installed as part of a PowerPivot for SharePoint deployment.</span></span> <span data-ttu-id="ac3ae-151">Non modificare la proprietà della modalità di distribuzione dell'istanza di Analysis Services che è parte di un'installazione di PowerPivot per SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ac3ae-151">Do not change the deployment mode property of Analysis Services instance that is part of a PowerPivot for SharePoint installation.</span></span> <span data-ttu-id="ac3ae-152">I dati PowerPivot non verranno più eseguiti nel server se si cambia modalità.</span><span class="sxs-lookup"><span data-stu-id="ac3ae-152">PowerPivot data will no longer run on the server if you change the mode.</span></span>|  
|<span data-ttu-id="ac3ae-153">2</span><span class="sxs-lookup"><span data-stu-id="ac3ae-153">2</span></span>|<span data-ttu-id="ac3ae-154">Specifica la modalità tabulare usata per l'hosting dei database del modello tabulare che usano l'archiviazione in memoria o DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="ac3ae-154">Specifies Tabular mode used for hosting tabular model databases that use in-memory storage or DirectQuery storage.</span></span>|  
  
 <span data-ttu-id="ac3ae-155">Ogni modalità comporta l'esclusione dell'altra.</span><span class="sxs-lookup"><span data-stu-id="ac3ae-155">Each mode is exclusive of the other.</span></span> <span data-ttu-id="ac3ae-156">In un server configurato per la modalità tabulare non è possibile eseguire i database di Analysis Services che contengono cubi e dimensioni.</span><span class="sxs-lookup"><span data-stu-id="ac3ae-156">A server that is configured for tabular mode cannot run Analysis Services databases that contain cubes and dimensions.</span></span> <span data-ttu-id="ac3ae-157">Se l'hardware del computer sottostante può supportare tale condizione, è possibile installare più istanze di Analysis Services nello stesso computer e configurare ogni istanza per l'utilizzo di una modalità di distribuzione diversa.</span><span class="sxs-lookup"><span data-stu-id="ac3ae-157">If the underlying computer hardware can support it, you can install multiple instances of Analysis Services on the same computer and configure each instance to use a different deployment mode.</span></span> <span data-ttu-id="ac3ae-158">Analysis Services è un'applicazione a elevato utilizzo di risorse.</span><span class="sxs-lookup"><span data-stu-id="ac3ae-158">Remember that Analysis Services is a resource intensive application.</span></span> <span data-ttu-id="ac3ae-159">La distribuzione di più istanze sullo stesso sistema viene consigliata solo per server di fascia alta.</span><span class="sxs-lookup"><span data-stu-id="ac3ae-159">Deploying multiple instances on the same system is recommended only for high-end servers.</span></span>  
  
 `EnableFast1033Locale`  
 <span data-ttu-id="ac3ae-160">Proprietà avanzata che deve essere modificata solo sotto la supervisione del servizio di supporto tecnico [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ac3ae-160">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `ExternalCommandTimeout`  
 <span data-ttu-id="ac3ae-161">Proprietà Integer che definisce il timeout in secondi per i comandi inviati a server esterni, incluse le origini dati relazionali e i server [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] esterni.</span><span class="sxs-lookup"><span data-stu-id="ac3ae-161">An integer property that defines the timeout, in seconds, for commands issued to external servers, including relational data sources and external [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] servers.</span></span>  
  
 <span data-ttu-id="ac3ae-162">Il valore predefinito di questa proprietà è 3600 (secondi).</span><span class="sxs-lookup"><span data-stu-id="ac3ae-162">The default value for this property is 3600 (seconds).</span></span>  
  
 `ExternalConnectionTimeout`  
 <span data-ttu-id="ac3ae-163">Proprietà Integer che definisce il timeout in secondi per la creazione di connessioni a server esterni, incluse le origini dati relazionali e i server [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] esterni.</span><span class="sxs-lookup"><span data-stu-id="ac3ae-163">An integer property that defines the timeout, in seconds, for creating connections to external servers, including relational data sources and external [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] servers.</span></span> <span data-ttu-id="ac3ae-164">Questa proprietà viene ignorata se nella stringa di connessione è specificato un timeout di connessione.</span><span class="sxs-lookup"><span data-stu-id="ac3ae-164">This property is ignored if a connection timeout is specified on the connection string.</span></span>  
  
 <span data-ttu-id="ac3ae-165">Il valore predefinito di questa proprietà è 60 (secondi).</span><span class="sxs-lookup"><span data-stu-id="ac3ae-165">The default value for this property is 60 (seconds).</span></span>  
  
 `ForceCommitTimeout`  
 <span data-ttu-id="ac3ae-166">Proprietà Integer che specifica quanto tempo (millisecondi) deve trascorrere prima che un commit annulli altri comandi che precedono quello corrente, incluse le query in corso.</span><span class="sxs-lookup"><span data-stu-id="ac3ae-166">An integer property that specifies how long, in milliseconds, a write commit operation should wait before canceling other commands that preceded the current command, including queries in progress.</span></span> <span data-ttu-id="ac3ae-167">In questo modo la transazione di commit procederà annullando le operazioni a priorità più bassa, ad esempio le query.</span><span class="sxs-lookup"><span data-stu-id="ac3ae-167">This allows the commit transaction to proceed by canceling lower priority operations, such as queries.</span></span>  
  
 <span data-ttu-id="ac3ae-168">Il valore predefinito di questa proprietà è 30 secondi (30000 millisecondi). Ciò significa che non verrà imposto un timeout agli altri comandi finché la transazione di commit non aspetta 30 secondi.</span><span class="sxs-lookup"><span data-stu-id="ac3ae-168">The default value for this property is 30 seconds (30000 milliseconds), which indicates that other commands will not be forced to timeout until the commit transaction has been waiting for 30 seconds.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ac3ae-169">Le query e i processi annullati da questo evento restituiranno il seguente messaggio di errore: "`Server: The operation has been cancelled`"</span><span class="sxs-lookup"><span data-stu-id="ac3ae-169">Queries and processes cancelled by this event will report the following error message: "`Server: The operation has been cancelled`"</span></span>  
  
 <span data-ttu-id="ac3ae-170">Per altre informazioni su questa proprietà, vedere [SQL Server 2008 R2 Analysis Services Operations Guide](https://go.microsoft.com/fwlink/?LinkID=225539)(Guida operativa di SQL Server 2008 R2 Analysis Services).</span><span class="sxs-lookup"><span data-stu-id="ac3ae-170">For more information about this property, see [SQL Server 2008 R2 Analysis Services Operations Guide](https://go.microsoft.com/fwlink/?LinkID=225539).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="ac3ae-171">`ForceCommitTimeout` si applica ai comandi di elaborazione dei cubi e alle operazioni di writeback.</span><span class="sxs-lookup"><span data-stu-id="ac3ae-171">`ForceCommitTimeout` applies to cube processing commands and to writeback operations.</span></span>  
  
 `IdleConnectionTimeout`  
 <span data-ttu-id="ac3ae-172">Proprietà Integer che specifica un timeout, espresso in secondi, per le connessioni inattive.</span><span class="sxs-lookup"><span data-stu-id="ac3ae-172">An integer property that specifies a timeout, in seconds, for connections that are inactive.</span></span>  
  
 <span data-ttu-id="ac3ae-173">Il valore predefinito di questa proprietà è zero (0). Ciò significa che non verrà imposto un timeout per le connessioni inattive.</span><span class="sxs-lookup"><span data-stu-id="ac3ae-173">The default value for this property is zero (0), which indicates that idle connections will not be timed out.</span></span>  
  
 `IdleOrphanSessionTimeout`  
 <span data-ttu-id="ac3ae-174">Proprietà Integer che definisce per quanti secondi le sessioni isolate (orfane) vengono mantenute nella memoria del server.</span><span class="sxs-lookup"><span data-stu-id="ac3ae-174">An integer property that defines how long, in seconds, orphaned sessions will be retained in server memory.</span></span> <span data-ttu-id="ac3ae-175">Una sessione orfana è una sessione a cui non è associata alcuna connessione.</span><span class="sxs-lookup"><span data-stu-id="ac3ae-175">An orphaned session is one that no longer has an associated connection.</span></span> <span data-ttu-id="ac3ae-176">Il valore predefinito è 120 secondi.</span><span class="sxs-lookup"><span data-stu-id="ac3ae-176">The default is 120 seconds.</span></span>  
  
 `InstanceVisible`  
 <span data-ttu-id="ac3ae-177">Proprietà booleana che indica se è l'istanza del server è visibile alle richieste di individuazione di istanze provenienti dal servizio per SQL Server Browser.</span><span class="sxs-lookup"><span data-stu-id="ac3ae-177">A Boolean property that indicates whether the server instance is visible to discover instance requests from SQL Server Browser service.</span></span> <span data-ttu-id="ac3ae-178">Il valore predefinito è True.</span><span class="sxs-lookup"><span data-stu-id="ac3ae-178">The default is True.</span></span> <span data-ttu-id="ac3ae-179">Se si imposta questa proprietà su false, l'istanza non sarà visibile a SQL Server Browser.</span><span class="sxs-lookup"><span data-stu-id="ac3ae-179">If you set it to false, the instance is not visible to SQL Server Browser.</span></span>  
  
 `Language`  
 <span data-ttu-id="ac3ae-180">Proprietà stringa che definisce la lingua, inclusi i messaggi di errore e la formattazione dei numeri.</span><span class="sxs-lookup"><span data-stu-id="ac3ae-180">A string property that defines the language, including error messages and number formatting.</span></span> <span data-ttu-id="ac3ae-181">Questa proprietà ha la priorità sulla proprietà CollationName.</span><span class="sxs-lookup"><span data-stu-id="ac3ae-181">This property overrides the CollationName property.</span></span>  
  
 <span data-ttu-id="ac3ae-182">Il valore predefinito di questa proprietà è vuoto. Ciò significa che la lingua viene definita dalla proprietà CollationName.</span><span class="sxs-lookup"><span data-stu-id="ac3ae-182">The default value for this property is blank, which indicates that the CollationName property defines the language.</span></span>  
  
 `LogDir`  
 <span data-ttu-id="ac3ae-183">Proprietà stringa che identifica il nome della directory contenente i log del server.</span><span class="sxs-lookup"><span data-stu-id="ac3ae-183">A string property that identifies the name of the directory that contains server logs.</span></span> <span data-ttu-id="ac3ae-184">Questa proprietà viene applicata solo quando per la registrazione vengono utilizzati file su disco invece di tabelle di database (condizione predefinita).</span><span class="sxs-lookup"><span data-stu-id="ac3ae-184">This property only applies when disk files are used for logging, as opposed to database tables (the default behavior).</span></span>  
  
 `MaxIdleSessionTimeout`  
 <span data-ttu-id="ac3ae-185">Proprietà Integer che definisce il timeout massimo in secondi per le sessioni inattive.</span><span class="sxs-lookup"><span data-stu-id="ac3ae-185">An integer property that defines the maximum idle session timeout, in seconds.</span></span> <span data-ttu-id="ac3ae-186">Il valore predefinito è zero (0), che indica che non si è mai verificato il timeout delle sessioni. Tuttavia, le sessioni inattive verranno comunque rimosse se il server è sottoposto a vincoli di risorse.</span><span class="sxs-lookup"><span data-stu-id="ac3ae-186">The default is zero (0), indicating that sessions are never timed out. However, idle sessions will still be removed if the server is under resource constraints.</span></span>  
  
 `MinIdleSessionTimeout`  
 <span data-ttu-id="ac3ae-187">Proprietà Integer che definisce il timeout minimo in secondi per le sessioni inattive.</span><span class="sxs-lookup"><span data-stu-id="ac3ae-187">An integer property that defines the minimum time, in seconds, that idle sessions will timeout.</span></span> <span data-ttu-id="ac3ae-188">Il valore predefinito è 2700 secondi.</span><span class="sxs-lookup"><span data-stu-id="ac3ae-188">The default is 2700 seconds.</span></span> <span data-ttu-id="ac3ae-189">Trascorso questo tempo, al server è consentito terminare la sessione inattiva, operazione che viene eseguita solo quando è richiesta memoria.</span><span class="sxs-lookup"><span data-stu-id="ac3ae-189">After this time expires, the server is permitted to end the idle session, but will only do so as memory is needed.</span></span>  
  
 `Port`  
 <span data-ttu-id="ac3ae-190">Proprietà Integer che definisce il numero di porta su cui il server rimarrà in attesa di connessioni client.</span><span class="sxs-lookup"><span data-stu-id="ac3ae-190">An integer property that defines the port number on which server will listen for client connections.</span></span> <span data-ttu-id="ac3ae-191">Se questa proprietà non viene impostata, il server trova in modo dinamico la prima porta non utilizzata.</span><span class="sxs-lookup"><span data-stu-id="ac3ae-191">If not set, server dynamically finds first unused port.</span></span>  
  
 <span data-ttu-id="ac3ae-192">Il valore predefinito di questa proprietà è zero (0) al quale per impostazione predefinita viene assegnata la porta 2383.</span><span class="sxs-lookup"><span data-stu-id="ac3ae-192">The default value for this property is zero (0), which in turn defaults to port 2383.</span></span> <span data-ttu-id="ac3ae-193">Per altre informazioni sulla configurazione della porta, vedere [Configure the Windows Firewall to Allow Analysis Services Access](../instances/configure-the-windows-firewall-to-allow-analysis-services-access.md).</span><span class="sxs-lookup"><span data-stu-id="ac3ae-193">For more information about port configuration, see [Configure the Windows Firewall to Allow Analysis Services Access](../instances/configure-the-windows-firewall-to-allow-analysis-services-access.md).</span></span>  
  
 `ServerTimeout`  
 <span data-ttu-id="ac3ae-194">Proprietà Integer che definisce il timeout, in secondi, per le query.</span><span class="sxs-lookup"><span data-stu-id="ac3ae-194">An integer that defines the timeout, in seconds, for queries.</span></span> <span data-ttu-id="ac3ae-195">L'impostazione predefinita è 3600 secondi (o 60 minuti).</span><span class="sxs-lookup"><span data-stu-id="ac3ae-195">The default is 3600 seconds (or 60 minutes).</span></span> <span data-ttu-id="ac3ae-196">Il valore zero (0) indica che non si verificherà alcun timeout per le query.</span><span class="sxs-lookup"><span data-stu-id="ac3ae-196">Zero (0) specifies that no queries will timeout.</span></span>  
  
 `TempDir`  
 <span data-ttu-id="ac3ae-197">Proprietà stringa che specifica il percorso per l'archiviazione dei file temporanei utilizzati durante operazioni quali elaborazione o ripristino.</span><span class="sxs-lookup"><span data-stu-id="ac3ae-197">A string property that specifies the location for storing temporary files used during processing, restoring, and other operations.</span></span> <span data-ttu-id="ac3ae-198">Il valore predefinito di questa proprietà è determinato dal programma di installazione.</span><span class="sxs-lookup"><span data-stu-id="ac3ae-198">The default value for this property is determined by setup.</span></span> <span data-ttu-id="ac3ae-199">Se questa proprietà non viene impostata, il valore predefinito è la directory dati.</span><span class="sxs-lookup"><span data-stu-id="ac3ae-199">If not specified, the default is the Data directory.</span></span>  
  
## <a name="requestprioritization-category"></a><span data-ttu-id="ac3ae-200">Categoria RequestPrioritization</span><span class="sxs-lookup"><span data-stu-id="ac3ae-200">RequestPrioritization Category</span></span>  
 `Enabled`  
 <span data-ttu-id="ac3ae-201">Proprietà avanzata che deve essere modificata solo sotto la supervisione del servizio di supporto tecnico [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ac3ae-201">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `StatisticsStoreSize`  
 <span data-ttu-id="ac3ae-202">Proprietà avanzata che deve essere modificata solo sotto la supervisione del servizio di supporto tecnico [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ac3ae-202">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac3ae-203">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ac3ae-203">See Also</span></span>  
 <span data-ttu-id="ac3ae-204">[Configurare le proprietà del server in Analysis Services](server-properties-in-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="ac3ae-204">[Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md) </span></span>  
 [<span data-ttu-id="ac3ae-205">Determinare la modalità server di un'istanza di Analysis Services</span><span class="sxs-lookup"><span data-stu-id="ac3ae-205">Determine the Server Mode of an Analysis Services Instance</span></span>](../instances/determine-the-server-mode-of-an-analysis-services-instance.md)  
  
  
