---
title: Data warehouse di gestione | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- data collector [SQL Server], management data warehouse
- data warehouse
- management data warehouse
ms.assetid: 9874a8b2-7ccd-494a-944c-ad33b30b5499
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 96eb26c3e273832aead4aa0421304df17dc5b8ff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626808"
---
# <a name="management-data-warehouse"></a><span data-ttu-id="316c3-102">data warehouse di gestione</span><span class="sxs-lookup"><span data-stu-id="316c3-102">Management Data Warehouse</span></span>
  <span data-ttu-id="316c3-103">Il data warehouse di gestione è un database relazionale che contiene i dati raccolti da un server che costituisce una destinazione di raccolta dati.</span><span class="sxs-lookup"><span data-stu-id="316c3-103">The management data warehouse is a relational database that contains the data that is collected from a server that is a data collection target.</span></span> <span data-ttu-id="316c3-104">Questi dati vengono utilizzati per generare report per i set di raccolta dati di sistema e possono essere utilizzati anche per creare report personalizzati.</span><span class="sxs-lookup"><span data-stu-id="316c3-104">This data is used to generate the reports for the System Data collection sets, and can also be used to create custom reports.</span></span>  
  
 <span data-ttu-id="316c3-105">L'infrastruttura dell'agente di raccolta dati definisce i processi e piani di manutenzione necessari per implementare i criteri di memorizzazione definiti dall'amministratore del database.</span><span class="sxs-lookup"><span data-stu-id="316c3-105">The data collector infrastructure defines the jobs and maintenance plans that are needed to implement the retention policies defined by the database administrator.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="316c3-106">Per questa versione dell'agente di raccolta dati il data warehouse di gestione viene creato utilizzando il modello di recupero con registrazione minima per ridurre al minimo la registrazione.</span><span class="sxs-lookup"><span data-stu-id="316c3-106">For this release of the data collector, the management data warehouse is created using the Simple recovery model, to minimize logging.</span></span> <span data-ttu-id="316c3-107">È necessario implementare il modello di recupero adatto per la propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="316c3-107">You should implement the appropriate recovery model for your organization.</span></span>  
  
## <a name="deploying-and-using-the-data-warehouse"></a><span data-ttu-id="316c3-108">Distribuzione ed utilizzo del data warehouse</span><span class="sxs-lookup"><span data-stu-id="316c3-108">Deploying and Using the Data Warehouse</span></span>  
 <span data-ttu-id="316c3-109">È possibile installare il data warehouse di gestione nella stessa istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in cui viene eseguito l'agente di raccolta dati.</span><span class="sxs-lookup"><span data-stu-id="316c3-109">You can install the management data warehouse on the same instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that runs the data collector.</span></span> <span data-ttu-id="316c3-110">Tuttavia, se le risorse del server o le prestazioni costituiscono un problema per il server che si sta monitorando, è possibile installare il data warehouse di gestione in un computer diverso.</span><span class="sxs-lookup"><span data-stu-id="316c3-110">However, if server resources or performance is an issue on the server being monitored, you can install the management data warehouse on a different computer.</span></span>  
  
 <span data-ttu-id="316c3-111">Gli schemi richiesti e i relativi oggetti per i set di raccolta di sistema predefiniti vengono creati quando viene creato il data warehouse di gestione.</span><span class="sxs-lookup"><span data-stu-id="316c3-111">The required schemas and their objects for the predefined system collection sets are created when you create the management data warehouse.</span></span> <span data-ttu-id="316c3-112">Gli schemi creati sono core e snapshot. Un terzo schema, custom_snapshots, viene creato quando vengono creati set di raccolta definiti dall'utente nei quali sono inclusi elementi di raccolta che usano il tipo agente di raccolta Query T-SQL generico.</span><span class="sxs-lookup"><span data-stu-id="316c3-112">The schemas that are created are core and snapshots.A third schema, custom_snapshots, is created when user-defined collection sets are created that include collection items that use the Generic T-SQL Query collector type.</span></span>  
  
###### <a name="core-schema"></a><span data-ttu-id="316c3-113">Schema core</span><span class="sxs-lookup"><span data-stu-id="316c3-113">Core schema</span></span>  
 <span data-ttu-id="316c3-114">Nello schema core vengono descritte le tabelle, le stored procedure e le viste utilizzate per l'organizzazione e l'identificazione dei dati raccolti.</span><span class="sxs-lookup"><span data-stu-id="316c3-114">The core schema describes the tables, stored procedures, and views that are used to organize and to identify collected data.</span></span> <span data-ttu-id="316c3-115">Queste tabelle sono condivise da tutte le tabelle di dati create per singoli tipi di agente di raccolta.</span><span class="sxs-lookup"><span data-stu-id="316c3-115">These tables are shared among all the data tables created for individual collector types.</span></span> <span data-ttu-id="316c3-116">Tale schema è bloccato e può essere modificato esclusivamente dal proprietario del database del data warehouse di gestione.</span><span class="sxs-lookup"><span data-stu-id="316c3-116">This schema is locked and can only be modified by the owner of the management data warehouse database.</span></span> <span data-ttu-id="316c3-117">Ai nomi delle tabelle di questo schema viene aggiunto il prefisso "core".</span><span class="sxs-lookup"><span data-stu-id="316c3-117">The names of the tables in this schema are prefixed by "core".</span></span>  
  
 <span data-ttu-id="316c3-118">Nella tabella seguente vengono descritte le tabelle di database dello schema core.</span><span class="sxs-lookup"><span data-stu-id="316c3-118">The following table describes the database tables in the core schema.</span></span> <span data-ttu-id="316c3-119">Grazie a queste tabelle di database l'agente di raccolta dati è in grado di registrare la provenienza dei dati, da chi sono stati inseriti e quando sono stati caricati sul data warehouse.</span><span class="sxs-lookup"><span data-stu-id="316c3-119">These database tables enable the data collector to track where the data came from, who inserted it, and when it was uploaded to the data warehouse.</span></span>  
  
|<span data-ttu-id="316c3-120">Nome tabella</span><span class="sxs-lookup"><span data-stu-id="316c3-120">Table name</span></span>|<span data-ttu-id="316c3-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="316c3-121">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="316c3-122">core.performance_counter_report_group_items</span><span class="sxs-lookup"><span data-stu-id="316c3-122">core.performance_counter_report_group_items</span></span>|<span data-ttu-id="316c3-123">Archivia informazioni sul modo in cui i report del data warehouse di gestione devono raggruppare e aggregare i contatori delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="316c3-123">Stores information about how the management data warehouse reports should group and aggregate performance counters.</span></span>|  
|<span data-ttu-id="316c3-124">core.snapshots_internal</span><span class="sxs-lookup"><span data-stu-id="316c3-124">core.snapshots_internal</span></span>|<span data-ttu-id="316c3-125">Identifica ogni nuovo snapshot.</span><span class="sxs-lookup"><span data-stu-id="316c3-125">Identifies each new snapshot.</span></span> <span data-ttu-id="316c3-126">Una nuova riga viene inserita in questa tabella ogni volta che un pacchetto di caricamento inizia a caricare un nuovo batch di dati.</span><span class="sxs-lookup"><span data-stu-id="316c3-126">A new row is inserted into this table whenever an upload package starts uploading a new batch of data.</span></span>|  
|<span data-ttu-id="316c3-127">core.snapshot_timetable_internal</span><span class="sxs-lookup"><span data-stu-id="316c3-127">core.snapshot_timetable_internal</span></span>|<span data-ttu-id="316c3-128">Archivia informazioni sugli orari degli snapshot.</span><span class="sxs-lookup"><span data-stu-id="316c3-128">Stores information about the snapshot times.</span></span> <span data-ttu-id="316c3-129">L'ora dello snapshot viene archiviata in una tabella separata in quanto molti snapshot possono verificarsi quasi nello stesso momento.</span><span class="sxs-lookup"><span data-stu-id="316c3-129">The snapshot time is stored in a separate table because many snapshots can happen at nearly the same time.</span></span>|  
|<span data-ttu-id="316c3-130">core.source.info_internal</span><span class="sxs-lookup"><span data-stu-id="316c3-130">core.source.info_internal</span></span>|<span data-ttu-id="316c3-131">In questa tabella sono archiviate informazioni sull'origine dati.</span><span class="sxs-lookup"><span data-stu-id="316c3-131">This table stores information about the data source.</span></span> <span data-ttu-id="316c3-132">La tabella viene aggiornata ogni volta che un nuovo set di raccolta comincia a caricare dati nel data warehouse.</span><span class="sxs-lookup"><span data-stu-id="316c3-132">This table is updated whenever a new collection set starts uploading data to the data warehouse.</span></span>|  
|<span data-ttu-id="316c3-133">core.supported_collector_types_internal</span><span class="sxs-lookup"><span data-stu-id="316c3-133">core.supported_collector_types_internal</span></span>|<span data-ttu-id="316c3-134">Contiene gli ID dei tipi di agente di raccolta registrati che possono caricare dati nel data warehouse di gestione.</span><span class="sxs-lookup"><span data-stu-id="316c3-134">Contains the IDs of registered collector types that can upload data to the management data warehouse.</span></span> <span data-ttu-id="316c3-135">Questa tabella viene aggiornata solo quando lo schema del warehouse viene aggiornato per supportare un nuovo tipo di agente di raccolta.</span><span class="sxs-lookup"><span data-stu-id="316c3-135">This table is only updated when the schema of the warehouse is updated to support a new collector type.</span></span> <span data-ttu-id="316c3-136">Quando viene creato il data warehouse di gestione, questa tabella viene popolata con gli ID dei tipi di agente di raccolta forniti dall'agente di raccolta dati.</span><span class="sxs-lookup"><span data-stu-id="316c3-136">When the management data warehouse is created, this table is populated with the IDs of the collector types provided by the data collector.</span></span>|  
|<span data-ttu-id="316c3-137">core.wait_categories</span><span class="sxs-lookup"><span data-stu-id="316c3-137">core.wait_categories</span></span>|<span data-ttu-id="316c3-138">Contiene le categorie utilizzate per raggruppare i tipi di attesa in base alla caratteristica di wait_type.</span><span class="sxs-lookup"><span data-stu-id="316c3-138">Contains the categories used to group wait types according to wait_type characteristic.</span></span>|  
|<span data-ttu-id="316c3-139">core.wait_types</span><span class="sxs-lookup"><span data-stu-id="316c3-139">core.wait_types</span></span>|<span data-ttu-id="316c3-140">Contiene i tipi di attesa riconosciuti dall'agente di raccolta dati.</span><span class="sxs-lookup"><span data-stu-id="316c3-140">Contains the wait types recognized by the data collector.</span></span>|  
|<span data-ttu-id="316c3-141">core.purge_info_internal</span><span class="sxs-lookup"><span data-stu-id="316c3-141">core.purge_info_internal</span></span>|<span data-ttu-id="316c3-142">Indica che è stata effettuata una richiesta per arrestare la rimozione di dati dal data warehouse di gestione.</span><span class="sxs-lookup"><span data-stu-id="316c3-142">Indicates that a request has been made to stop the removal of data from the management data warehouse.</span></span>|  
  
 <span data-ttu-id="316c3-143">Le tabelle precedenti sono utilizzate con le tabelle del tipo di agente di raccolta per archiviare informazioni.</span><span class="sxs-lookup"><span data-stu-id="316c3-143">The preceding tables are used with collector type tables to store information.</span></span> <span data-ttu-id="316c3-144">Ad esempio, il tipo di agente di raccolta Traccia SQL generico utilizza le tabelle seguenti per archiviare dati di traccia:</span><span class="sxs-lookup"><span data-stu-id="316c3-144">For example, the Generic SQL Trace collector type uses the following tables to store trace data:</span></span>  
  
-   <span data-ttu-id="316c3-145">core.source_info_internal</span><span class="sxs-lookup"><span data-stu-id="316c3-145">core.source_info_internal</span></span>  
  
-   <span data-ttu-id="316c3-146">core.snapshots_internal</span><span class="sxs-lookup"><span data-stu-id="316c3-146">core.snapshots_internal</span></span>  
  
-   <span data-ttu-id="316c3-147">snapshots.trace_info</span><span class="sxs-lookup"><span data-stu-id="316c3-147">snapshots.trace_info</span></span>  
  
-   <span data-ttu-id="316c3-148">snapshots.trace_data</span><span class="sxs-lookup"><span data-stu-id="316c3-148">snapshots.trace_data</span></span>  
  
###### <a name="snapshots-schema"></a><span data-ttu-id="316c3-149">Schema snapshot</span><span class="sxs-lookup"><span data-stu-id="316c3-149">Snapshots schema</span></span>  
 <span data-ttu-id="316c3-150">Lo schema snapshot descrive gli oggetti necessari ad archiviare e gestire i dati raccolti dai tipi di agente di raccolta forniti.</span><span class="sxs-lookup"><span data-stu-id="316c3-150">The snapshots schema describes the objects needed to store and maintain the data collected by the collector types that are provided.</span></span> <span data-ttu-id="316c3-151">Le tabelle contenute in questo schema sono corrette, pertanto non è necessario modificarle per l'intera durata del tipo di agente di raccolta.</span><span class="sxs-lookup"><span data-stu-id="316c3-151">The tables in this schema are fixed and do not need to be changed during the lifetime of the collector type.</span></span> <span data-ttu-id="316c3-152">In caso di necessità, lo schema può essere modificato esclusivamente da membri del ruolo mdw_admin.</span><span class="sxs-lookup"><span data-stu-id="316c3-152">If changes are needed, the schema can only be changed by members of the mdw_admin role.</span></span> <span data-ttu-id="316c3-153">Queste tabelle sono create per archiviare i dati raccolti dai set di raccolta dati di sistema.</span><span class="sxs-lookup"><span data-stu-id="316c3-153">These tables are created to store the data collected by the System Data collection sets.</span></span>  
  
 <span data-ttu-id="316c3-154">Nelle tabelle seguenti è illustrata una parte dello schema del data warehouse di gestione richiesta per i set di raccolta Attività server e Statistiche query.</span><span class="sxs-lookup"><span data-stu-id="316c3-154">The following tables illustrate a portion of the management data warehouse schema that is required for the Server Activity and Query Statistics collection sets.</span></span>  
  
-   <span data-ttu-id="316c3-155">Tabelle delle risorse a livello di sistema</span><span class="sxs-lookup"><span data-stu-id="316c3-155">System-level resource tables</span></span>  
  
    -   <span data-ttu-id="316c3-156">**snapshots.os_wait_stats**</span><span class="sxs-lookup"><span data-stu-id="316c3-156">**snapshots.os_wait_stats**</span></span>  
  
    -   <span data-ttu-id="316c3-157">**snapshots.os_latch_stats**</span><span class="sxs-lookup"><span data-stu-id="316c3-157">**snapshots.os_latch_stats**</span></span>  
  
    -   <span data-ttu-id="316c3-158">**snapshots.os_schedulers**</span><span class="sxs-lookup"><span data-stu-id="316c3-158">**snapshots.os_schedulers**</span></span>  
  
    -   `snapshots.os_memory_clerks`  
  
    -   <span data-ttu-id="316c3-159">**snapshots.os_memory_nodes**</span><span class="sxs-lookup"><span data-stu-id="316c3-159">**snapshots.os_memory_nodes**</span></span>  
  
    -   <span data-ttu-id="316c3-160">snapshots.sql_process_and_system_memory</span><span class="sxs-lookup"><span data-stu-id="316c3-160">snapshots.sql_process_and_system_memory</span></span>  
  
-   <span data-ttu-id="316c3-161">Attività di sistema</span><span class="sxs-lookup"><span data-stu-id="316c3-161">System activity</span></span>  
  
    -   <span data-ttu-id="316c3-162">snapshots.active_sessions_and_requests</span><span class="sxs-lookup"><span data-stu-id="316c3-162">snapshots.active_sessions_and_requests</span></span>  
  
-   <span data-ttu-id="316c3-163">Statistiche query</span><span class="sxs-lookup"><span data-stu-id="316c3-163">Query statistics</span></span>  
  
    -   <span data-ttu-id="316c3-164">snapshots.query_stats</span><span class="sxs-lookup"><span data-stu-id="316c3-164">snapshots.query_stats</span></span>  
  
-   <span data-ttu-id="316c3-165">Statistiche di I/O</span><span class="sxs-lookup"><span data-stu-id="316c3-165">I/O statistics</span></span>  
  
    -   `snapshots.io_virtual_file_stats`  
  
-   <span data-ttu-id="316c3-166">Testo e piano di query</span><span class="sxs-lookup"><span data-stu-id="316c3-166">Query text and plan</span></span>  
  
    -   <span data-ttu-id="316c3-167">snapshots.notable_query_text</span><span class="sxs-lookup"><span data-stu-id="316c3-167">snapshots.notable_query_text</span></span>  
  
    -   <span data-ttu-id="316c3-168">snapshots.notable_query_plan</span><span class="sxs-lookup"><span data-stu-id="316c3-168">snapshots.notable_query_plan</span></span>  
  
-   <span data-ttu-id="316c3-169">Statistiche query normalizzate</span><span class="sxs-lookup"><span data-stu-id="316c3-169">Normalized query statistics</span></span>  
  
    -   <span data-ttu-id="316c3-170">snapshots.distinct_queries</span><span class="sxs-lookup"><span data-stu-id="316c3-170">snapshots.distinct_queries</span></span>  
  
    -   <span data-ttu-id="316c3-171">snapshots.distinct_query_to_handle</span><span class="sxs-lookup"><span data-stu-id="316c3-171">snapshots.distinct_query_to_handle</span></span>  
  
 <span data-ttu-id="316c3-172">**Schema custom_snapshot**</span><span class="sxs-lookup"><span data-stu-id="316c3-172">**Custom_snapshots schema**</span></span>  
  
 <span data-ttu-id="316c3-173">Lo schema del custom_snapshots descrive le nuove tabelle e viste create quando per creare set di raccolta definiti dall'utente vengono utilizzati tipi di agente di raccolta standard o di terze parti.</span><span class="sxs-lookup"><span data-stu-id="316c3-173">The custom_snapshots schema describes new tables and views that are created when standard or third-party collector types are used to create user-defined collection sets.</span></span> <span data-ttu-id="316c3-174">Qualora un tipo di agente di raccolta richieda una nuova tabella di dati per un elemento della raccolta può creare tale tabella in questo schema.</span><span class="sxs-lookup"><span data-stu-id="316c3-174">Any collector type that requires a new data table for a collection item can create that table in this schema.</span></span> <span data-ttu-id="316c3-175">Possono aggiungere nuove tabelle in questo schema i membri del ruolo mdw_writer.</span><span class="sxs-lookup"><span data-stu-id="316c3-175">New tables can be added in this schema by members of the mdw_writer role.</span></span> <span data-ttu-id="316c3-176">Qualsiasi altra modifica allo schema può essere apportata esclusivamente dai membri del ruolo mdw_admin.</span><span class="sxs-lookup"><span data-stu-id="316c3-176">Any other changes to the schema can only be made by members of the mdw_admin role.</span></span>  
  
 <span data-ttu-id="316c3-177">È possibile ottenere informazioni dettagliate sul contenuto e sul tipo di dati delle colonne delle tabelle di database leggendo la documentazione relativa alla stored procedure dell'agente di raccolta dati appropriata per ciascuna tabella.</span><span class="sxs-lookup"><span data-stu-id="316c3-177">You can get detailed data type and content information for the database table columns by reading the documentation for the appropriate data collector stored procedure for each of the tables.</span></span>  
  
### <a name="best-practices"></a><span data-ttu-id="316c3-178">Procedure consigliate</span><span class="sxs-lookup"><span data-stu-id="316c3-178">Best Practices</span></span>  
 <span data-ttu-id="316c3-179">Quando si utilizza il data warehouse di gestione si consiglia di attenersi alle seguenti procedure:</span><span class="sxs-lookup"><span data-stu-id="316c3-179">When working with the management data warehouse, we recommend following these best practices:</span></span>  
  
-   <span data-ttu-id="316c3-180">Non modificare i metadati di tabelle del data warehouse di gestione se non in caso di aggiunta di un nuovo tipo di agente di raccolta.</span><span class="sxs-lookup"><span data-stu-id="316c3-180">Do not modify the metadata of management data warehouse tables unless you are adding a new collector type.</span></span>  
  
-   <span data-ttu-id="316c3-181">Non modificare direttamente i dati contenuti nel data warehouse di gestione.</span><span class="sxs-lookup"><span data-stu-id="316c3-181">Do not directly modify the data in the management data warehouse.</span></span> <span data-ttu-id="316c3-182">La modifica dei dati raccolti invalida la legittimità di tali dati.</span><span class="sxs-lookup"><span data-stu-id="316c3-182">Changing the data that you have collected invalidates the legitimacy of the collected data.</span></span>  
  
-   <span data-ttu-id="316c3-183">Per accedere ai dati delle istanze e delle applicazioni, anziché utilizzare direttamente le tabelle, avvalersi delle stored procedure e delle funzioni fornite con l'agente di raccolta dati.</span><span class="sxs-lookup"><span data-stu-id="316c3-183">Instead of directly using the tables, use the documented stored procedures and functions that are provided with the data collector to access instance and application data.</span></span> <span data-ttu-id="316c3-184">I nomi e le definizioni delle tabelle possono cambiare, cambiano quando si aggiorna l'applicazione e potrebbero cambiare nelle versioni future.</span><span class="sxs-lookup"><span data-stu-id="316c3-184">The table names and definitions can change, do change when you update the application, and might change in future releases.</span></span>  
  
## <a name="change-history"></a><span data-ttu-id="316c3-185">Cronologia modifiche</span><span class="sxs-lookup"><span data-stu-id="316c3-185">Change History</span></span>  
  
|<span data-ttu-id="316c3-186">Contenuto aggiornato</span><span class="sxs-lookup"><span data-stu-id="316c3-186">Updated content</span></span>|  
|---------------------|  
|<span data-ttu-id="316c3-187">Aggiunta della tabella core.performance_counter_report_group_items alla sezione "Schema core".</span><span class="sxs-lookup"><span data-stu-id="316c3-187">Added the core.performance_counter_report_group_items table to the "Core schema" section.</span></span>|  
|<span data-ttu-id="316c3-188">Aggiornamento dell'elenco di tabelle nella sezione "Schema snapshot".</span><span class="sxs-lookup"><span data-stu-id="316c3-188">Updated the list of tables in the "Snapshots schema" section.</span></span> <span data-ttu-id="316c3-189">Aggiunta di snapshots.os_memory_clerks, snapshots.sql_process_and_system_memory e snapshots.io_virtual_file_stats.</span><span class="sxs-lookup"><span data-stu-id="316c3-189">Added snapshots.os_memory_clerks,snapshots.sql_process_and_system_memory, and snapshots.io_virtual_file_stats.</span></span> <span data-ttu-id="316c3-190">Rimozione di snapshots.os_process_memory e snapshots.distinct_query_stats.</span><span class="sxs-lookup"><span data-stu-id="316c3-190">Removedsnapshots.os_process_memory and snapshots.distinct_query_stats.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="316c3-191">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="316c3-191">See Also</span></span>  
 <span data-ttu-id="316c3-192">[Stored procedure del data warehouse di gestione &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/management-data-warehouse-stored-procedures-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="316c3-192">[Management Data Warehouse Stored Procedures &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/management-data-warehouse-stored-procedures-transact-sql) </span></span>  
 <span data-ttu-id="316c3-193">[Stored procedure dell'agente di raccolta dati &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/data-collector-stored-procedures-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="316c3-193">[Data Collector Stored Procedures &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/data-collector-stored-procedures-transact-sql) </span></span>  
 <span data-ttu-id="316c3-194">[Raccolta dati](data-collection.md) </span><span class="sxs-lookup"><span data-stu-id="316c3-194">[Data Collection](data-collection.md) </span></span>  
 [<span data-ttu-id="316c3-195">Visualizzare un report sui set di raccolta &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="316c3-195">View a Collection Set Report &#40;SQL Server Management Studio&#41;</span></span>](view-a-collection-set-report-sql-server-management-studio.md)  
  
  
