---
title: Monitoraggio delle prestazioni con Query Store | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
ms.assetid: e06344a4-22a5-4c67-b6c6-a7060deb5de6
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: e5d74b9c4def9c0314569a8d0bd87939cdcb11b2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637250"
---
# <a name="monitoring-performance-by-using-the-query-store"></a><span data-ttu-id="b1501-102">Monitoraggio delle prestazioni con Archivio query</span><span class="sxs-lookup"><span data-stu-id="b1501-102">Monitoring Performance By Using the Query Store</span></span>
  <span data-ttu-id="b1501-103">La funzionalità dell'archivio query mette a disposizione degli amministratori di database informazioni dettagliate sulle prestazioni e sulla scelta del piano di query.</span><span class="sxs-lookup"><span data-stu-id="b1501-103">The query store feature provides DBAs with insight on query plan choice and performance.</span></span> <span data-ttu-id="b1501-104">Semplifica la risoluzione dei problemi in quanto consente di individuare rapidamente le variazioni delle prestazioni causate da modifiche nei piani di query.</span><span class="sxs-lookup"><span data-stu-id="b1501-104">It simplifies performance troubleshooting by enabling you to quickly find performance differences caused by changes in query plans.</span></span> <span data-ttu-id="b1501-105">La funzionalità acquisisce automaticamente una cronologia delle query, dei piani e delle statistiche di runtime e li conserva in modo che sia possibile esaminarli successivamente.</span><span class="sxs-lookup"><span data-stu-id="b1501-105">The feature automatically captures a history of queries, plans, and runtime statistics, and retains these for your review.</span></span> <span data-ttu-id="b1501-106">I dati vengono separati dagli intervalli di tempo, consentendo di visualizzare i modelli di utilizzo del database e capire quando sono state apportate modifiche al piano di query nel server.</span><span class="sxs-lookup"><span data-stu-id="b1501-106">It separates data by time windows, allowing you to see database usage patterns and understand when query plan changes happened on the server.</span></span> <span data-ttu-id="b1501-107">Per configurare l'archivio query, è possibile usare l'opzione [ALTER DATABASE SET](/sql/t-sql/statements/alter-database-transact-sql-set-options) .</span><span class="sxs-lookup"><span data-stu-id="b1501-107">The query store can be configured by using the [ALTER DATABASE SET](/sql/t-sql/statements/alter-database-transact-sql-set-options) option.</span></span>

||
|-|
|<span data-ttu-id="b1501-108">**Si applica a**: [!INCLUDE[sqldbesa](../../includes/sqldbesa-md.md)] ([Get it](http://azure.micosoft.com/documentation/articles/sql-database-preview-whats-new/?WT.mc_id=TSQL_GetItTag)).</span><span class="sxs-lookup"><span data-stu-id="b1501-108">**Applies to**: [!INCLUDE[sqldbesa](../../includes/sqldbesa-md.md)] ([Get it](http://azure.micosoft.com/documentation/articles/sql-database-preview-whats-new/?WT.mc_id=TSQL_GetItTag)).</span></span>|

> [!IMPORTANT]
>  <span data-ttu-id="b1501-109">Si tratta attualmente di una funzionalità di anteprima.</span><span class="sxs-lookup"><span data-stu-id="b1501-109">This is currently a preview feature.</span></span> <span data-ttu-id="b1501-110">Per usare la funzionalità Archivio query è necessario dichiarare di essere a conoscenza e di accettare che l'implementazione della funzionalità è soggetta alle condizioni per l'anteprima indicate nel contratto di licenza, ad esempio il Contratto Enterprise, il Contratto di Microsoft Azure o il Contratto di Sottoscrizione Microsoft Online, oltre a eventuali [condizioni per l'utilizzo aggiuntive per le anteprime di Microsoft Azure](https://azure.microsoft.com/support/legal/preview-supplemental-terms/).</span><span class="sxs-lookup"><span data-stu-id="b1501-110">To use the Query Store you must acknowledge and agree that implementation of Query Store is subject to the preview terms in your license agreement (e.g. the Enterprise Agreement, Microsoft Azure Agreement, or Microsoft Online Subscription Agreement), as well as any applicable [Supplemental Terms of Use for Microsoft Azure Preview](https://azure.microsoft.com/support/legal/preview-supplemental-terms/).</span></span>

##  <a name="enabling-the-query-store"></a><a name="Enabling"></a> <span data-ttu-id="b1501-111">Abilitazione di Archivio query</span><span class="sxs-lookup"><span data-stu-id="b1501-111">Enabling the Query Store</span></span>
 <span data-ttu-id="b1501-112">Per impostazione predefinita, la funzionalità Archivio query non è attiva per i nuovi database.</span><span class="sxs-lookup"><span data-stu-id="b1501-112">Query Store is not active for new databases by default.</span></span>

#### <a name="by-using-the-query-store-page-in-management-studio"></a><span data-ttu-id="b1501-113">Abilitazione nella pagina Archivio query in Management Studio</span><span class="sxs-lookup"><span data-stu-id="b1501-113">By Using the Query Store Page in Management Studio</span></span>

1.  <span data-ttu-id="b1501-114">In Esplora oggetti fare clic con il pulsante destro del mouse su un database e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="b1501-114">In Object Explorer, right-click a database, and then click **Properties**.</span></span> <span data-ttu-id="b1501-115">È richiesta la versione di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] inclusa in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)]2016.</span><span class="sxs-lookup"><span data-stu-id="b1501-115">(Requires [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 2016 version of [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)].)</span></span>

2.  <span data-ttu-id="b1501-116">Nella finestra di dialogo **Proprietà database** selezionare la pagina **Archivio query** .</span><span class="sxs-lookup"><span data-stu-id="b1501-116">In the **Database Properties** dialog box, select the **Query Store** page.</span></span>

3.  <span data-ttu-id="b1501-117">Nella casella di controllo **Abilita** selezionare **True**.</span><span class="sxs-lookup"><span data-stu-id="b1501-117">In the **Enable** box, select **True**.</span></span>

#### <a name="by-using-transact-sql-statements"></a><span data-ttu-id="b1501-118">Abilitazione con le istruzioni Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b1501-118">By Using Transact-SQL Statements</span></span>

1.  <span data-ttu-id="b1501-119">Per abilitare l'archivio query, usare l'istruzione `ALTER DATABASE`.</span><span class="sxs-lookup"><span data-stu-id="b1501-119">Use the `ALTER DATABASE` statement to enable the query store.</span></span> <span data-ttu-id="b1501-120">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="b1501-120">For example:</span></span>

    ```
    ALTER DATABASE AdventureWorks2012 SET QUERY_STORE = ON;
    ```

     <span data-ttu-id="b1501-121">Per altre opzioni di sintassi correlate all'archivio query, vedere [Opzioni ALTER DATABASE SET &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span><span class="sxs-lookup"><span data-stu-id="b1501-121">For more syntax options related to the query store, see [ALTER DATABASE SET Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span></span>

> [!NOTE]
>  <span data-ttu-id="b1501-122">Non è possibile abilitare l'archivio query per il database master.</span><span class="sxs-lookup"><span data-stu-id="b1501-122">You cannot enable the query store for the master database.</span></span>



##  <a name="information-in-the-query-store"></a><a name="About"></a> <span data-ttu-id="b1501-123">Informazioni presenti in Archivio query</span><span class="sxs-lookup"><span data-stu-id="b1501-123">Information in the Query Store</span></span>
 <span data-ttu-id="b1501-124">I piani di esecuzione per query specifiche in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in genere cambiano nel tempo per motivi diversi, quali modifiche delle statistiche, modifiche dello schema, creazione/eliminazione di indici e così via. Nella cache delle procedure, dove sono archiviati i piani di query memorizzati nella cache, viene archiviato solo il piano di esecuzione più recente.</span><span class="sxs-lookup"><span data-stu-id="b1501-124">Execution plans for any specific query in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] typically evolve over time due to a number of different reasons such as statistics changes, schema changes, creation/deletion of indexes, etc. The procedure cache (where cached query plans are stored) only stores the latest execution plan.</span></span> <span data-ttu-id="b1501-125">La rimozione dei piani dalla cache dei piani può dipendere anche da problemi di memoria.</span><span class="sxs-lookup"><span data-stu-id="b1501-125">Plans also get evicted from the plan cache due to memory pressure.</span></span> <span data-ttu-id="b1501-126">Di conseguenza, le regressioni delle prestazioni di esecuzione delle query causate da modifiche del piano di esecuzione possono essere rilevanti e richiedere tempo per la risoluzione.</span><span class="sxs-lookup"><span data-stu-id="b1501-126">As a result, query performance regressions caused by execution plan changes can be non-trivial and time consuming to resolve.</span></span>

 <span data-ttu-id="b1501-127">Dal momento che nell'archivio query vengono mantenuti più piani di esecuzione per ogni query, è possibile applicare i criteri in modo che il processore di query usi un piano di esecuzione specifico per una query.</span><span class="sxs-lookup"><span data-stu-id="b1501-127">Since the query store retains multiple execution plans per query, it can enforce policies to direct the query processor to use a specific execution plan for a query.</span></span> <span data-ttu-id="b1501-128">Questo processo viene chiamato utilizzo forzato del piano.</span><span class="sxs-lookup"><span data-stu-id="b1501-128">This is referred to as plan forcing.</span></span> <span data-ttu-id="b1501-129">Per applicare l'utilizzo forzato del piano in Archivio query, viene usato un meccanismo simile all'hint per la query [USE PLAN](/sql/t-sql/queries/hints-transact-sql-query) , che però non richiede modifiche nelle applicazioni utente.</span><span class="sxs-lookup"><span data-stu-id="b1501-129">Plan forcing in Query Store is provided by using a mechanism similar to the [USE PLAN](/sql/t-sql/queries/hints-transact-sql-query) query hint, but it does not require any change in user applications.</span></span> <span data-ttu-id="b1501-130">Grazie all'utilizzo forzato del piano è possibile risolvere molto rapidamente una regressione delle prestazioni di esecuzione delle query causata da una modifica del piano.</span><span class="sxs-lookup"><span data-stu-id="b1501-130">Plan forcing can resolve a query performance regression caused by a plan change in a very short period of time.</span></span>

 <span data-ttu-id="b1501-131">La funzionalità Archivio query viene usata in genere negli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="b1501-131">Common scenarios for using the Query Store feature are:</span></span>

-   <span data-ttu-id="b1501-132">Individuare e correggere rapidamente una regressione delle prestazioni di esecuzione delle query forzando un piano di query precedente.</span><span class="sxs-lookup"><span data-stu-id="b1501-132">Quickly find and fix a plan performance regression by forcing the previous query plan.</span></span> <span data-ttu-id="b1501-133">Correggere le query in cui si è verificata di recente una regressione delle prestazioni a causa di modifiche del piano di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="b1501-133">Fix queries that have recently regressed in performance due to execution plan changes.</span></span>

-   <span data-ttu-id="b1501-134">Determinare il numero di volte in cui una query è stata eseguita in un determinato intervallo di tempo, in modo da assistere un amministratore di database nella risoluzione dei problemi relativi alle prestazioni delle risorse.</span><span class="sxs-lookup"><span data-stu-id="b1501-134">Determine the number of times a query was executed in a given time window, assisting a DBA in troubleshooting performance resource problems.</span></span>

-   <span data-ttu-id="b1501-135">Identificare le prime *n* query (in base al tempo di esecuzione, al consumo della memoria e così via) nelle ultime *x* ore.</span><span class="sxs-lookup"><span data-stu-id="b1501-135">Identify top *n* queries (by execution time, memory consumption, etc.) in the past *x* hours.</span></span>

-   <span data-ttu-id="b1501-136">Controllare la cronologia dei piani di query per una determinata query.</span><span class="sxs-lookup"><span data-stu-id="b1501-136">Audit the history of query plans for a given query.</span></span>

-   <span data-ttu-id="b1501-137">Analizzare i modelli di utilizzo delle risorse (CPU, I/O e memoria) per un determinato database.</span><span class="sxs-lookup"><span data-stu-id="b1501-137">Analyze the resource (CPU, I/O, and Memory) usage patterns for a particular database.</span></span>

 <span data-ttu-id="b1501-138">L'archivio query contiene due archivi: un **archivio piani** per salvare in modo permanente le informazioni sul piano di esecuzione e un **archivio delle statistiche di runtime** per salvare in modo permanente le informazioni sulle statistiche di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="b1501-138">The query store contains two stores; a **plan store** for persisting the execution plan information, and a **runtime stats store** for persisting the execution statistics information.</span></span> <span data-ttu-id="b1501-139">Il numero di piani univoci che è possibile archiviare per una query nell'archivio piani è limitato dall'opzione di configurazione `max_plans_per_query`.</span><span class="sxs-lookup"><span data-stu-id="b1501-139">The number of unique plans that can be stored for a query in the plan store is limited by the `max_plans_per_query` configuration option.</span></span> <span data-ttu-id="b1501-140">Per migliorare le prestazioni, le informazioni vengono scritte nei due archivi in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="b1501-140">To enhance performance, the information is written to the two stores asynchronously.</span></span> <span data-ttu-id="b1501-141">Per ridurre al minimo l'utilizzo dello spazio, le statistiche di esecuzione di runtime nell'archivio delle statistiche di runtime vengono aggregate in un intervallo di tempo fisso.</span><span class="sxs-lookup"><span data-stu-id="b1501-141">To minimize space usage, the runtime execution statistics in the runtime stats store are aggregated over a fixed time window.</span></span> <span data-ttu-id="b1501-142">Per visualizzare le informazioni contenute in questi archivi, è possibile eseguire una query sulle viste del catalogo dell'archivio query.</span><span class="sxs-lookup"><span data-stu-id="b1501-142">The information in these stores is visible by querying the query store catalog views.</span></span>

 <span data-ttu-id="b1501-143">La query seguente restituisce le informazioni sulle query e sui piani inclusi nell'archivio query.</span><span class="sxs-lookup"><span data-stu-id="b1501-143">The following query returns information about queries and plans in the query store.</span></span>

```
SELECT Txt.query_text_id, Txt.query_sql_text, Pl.plan_id, Qry.*
FROM sys.query_store_plan AS Pl
JOIN sys.query_store_query AS Qry
    ON Pl.query_id = Qry.query_id
JOIN sys.query_store_query_text AS Txt
    ON Qry.query_text_id = Txt.query_text_id ;
```



## <a name="using-the-regressed-queries-feature"></a><span data-ttu-id="b1501-144">Uso della funzionalità Query regredite</span><span class="sxs-lookup"><span data-stu-id="b1501-144">Using the Regressed Queries Feature</span></span>
 <span data-ttu-id="b1501-145">Dopo aver abilitato l'archivio query, aggiornare la parte del database del riquadro Esplora oggetti per aggiungere la sezione **query Store** .</span><span class="sxs-lookup"><span data-stu-id="b1501-145">After enabling the query store, refresh the database portion of the Object Explorer pane to add the **Query Store** section.</span></span>

 <span data-ttu-id="b1501-146">![QueryStore](../../database-engine/media/querystore.PNG "QueryStore")</span><span class="sxs-lookup"><span data-stu-id="b1501-146">![QueryStore](../../database-engine/media/querystore.PNG "QueryStore")</span></span>

 <span data-ttu-id="b1501-147">Selezionando **Query regredite**, viene aperto il riquadro **Query regredite** in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b1501-147">Selecting **Regressed Queries**, opens the **Regressed Queries** pane in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)].</span></span> <span data-ttu-id="b1501-148">in cui sono visualizzati i piani e le query presenti nell'archivio query.</span><span class="sxs-lookup"><span data-stu-id="b1501-148">The Regressed Queries pane shows you the queries, and plans in the query store.</span></span> <span data-ttu-id="b1501-149">Le caselle a discesa nella parte superiore consentono di selezionare le query in base a diversi criteri.</span><span class="sxs-lookup"><span data-stu-id="b1501-149">Drop down boxes at the top allow you to select queries based on various criteria.</span></span> <span data-ttu-id="b1501-150">Selezionare un piano per visualizzare il piano di query con interfaccia grafica.</span><span class="sxs-lookup"><span data-stu-id="b1501-150">Select a plan to see the graphical query plan.</span></span> <span data-ttu-id="b1501-151">Sono disponibili pulsanti per visualizzare la query di origine, forzare e annullar e la forzatura di un piano di query e aggiornare la visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="b1501-151">Buttons are available to view the source query, force, and unforce a query plan, and refresh the display.</span></span>

 <span data-ttu-id="b1501-152">![RegressedQueries](../../database-engine/media/regressedqueries.PNG "RegressedQueries")</span><span class="sxs-lookup"><span data-stu-id="b1501-152">![RegressedQueries](../../database-engine/media/regressedqueries.PNG "RegressedQueries")</span></span>

 <span data-ttu-id="b1501-153">Per forzare un piano, selezionare una query e un piano, quindi fare clic su **forza piano.**</span><span class="sxs-lookup"><span data-stu-id="b1501-153">To force a plan, select a query and plan, and then click **Force Plan.**</span></span> <span data-ttu-id="b1501-154">È possibile forzare solo piani che sono stati salvati dalla funzionalità del piano di query e che sono ancora presenti nella relativa cache.</span><span class="sxs-lookup"><span data-stu-id="b1501-154">You can only force plans that were saved by the query plan feature and are still retained in the query plan cache.</span></span>



##  <a name="configuration-options"></a><a name="Options"></a> <span data-ttu-id="b1501-155">Opzioni di configurazione</span><span class="sxs-lookup"><span data-stu-id="b1501-155">Configuration Options</span></span>
 <span data-ttu-id="b1501-156">OPERATION_MODE possono essere READ_WRITE o READ_ONLY.</span><span class="sxs-lookup"><span data-stu-id="b1501-156">OPERATION_MODE Can be READ_WRITE or READ_ONLY.</span></span>

 <span data-ttu-id="b1501-157">CLEANUP_POLICY configurare l'argomento STALE_QUERY_THRESHOLD_DAYS per specificare il numero di giorni di conservazione dei dati nell'archivio query.</span><span class="sxs-lookup"><span data-stu-id="b1501-157">CLEANUP_POLICY Configure the STALE_QUERY_THRESHOLD_DAYS argument to specify the number of days to retain data in the query store.</span></span>

 <span data-ttu-id="b1501-158">DATA_FLUSH_INTERVAL_SECONDS determina la frequenza con cui i dati scritti nell'archivio query vengono mantenuti su disco.</span><span class="sxs-lookup"><span data-stu-id="b1501-158">DATA_FLUSH_INTERVAL_SECONDS Determines the frequency at which data written to the query store is persisted to disk.</span></span> <span data-ttu-id="b1501-159">Per ottimizzare le prestazioni, i dati raccolti dall'archivio query vengono scritti in modo asincrono sul disco.</span><span class="sxs-lookup"><span data-stu-id="b1501-159">To optimize for performance, data collected by the query store is asynchronously written to the disk.</span></span> <span data-ttu-id="b1501-160">La frequenza con cui si verifica questo trasferimento asincrono viene configurata tramite DATA_FLUSH_INTERVAL_SECONDS.</span><span class="sxs-lookup"><span data-stu-id="b1501-160">The frequency at which this asynchronous transfer occurs is configured via DATA_FLUSH_INTERVAL_SECONDS.</span></span>

 <span data-ttu-id="b1501-161">MAX_SIZE_MB configura le dimensioni massime dell'archivio query.</span><span class="sxs-lookup"><span data-stu-id="b1501-161">MAX_SIZE_MB Configures the maximum size of the query store.</span></span> <span data-ttu-id="b1501-162">Se i dati nell'archivio query raggiungono il limite impostato in MAX_SIZE_MB, lo stato cambia da lettura/scrittura a sola lettura e la raccolta di nuovi dati viene interrotta.</span><span class="sxs-lookup"><span data-stu-id="b1501-162">If the data in the query store hits the MAX_SIZE_MB limit, the query store automatically changes the state from read-write to read-only and stops collecting new data.</span></span>

 <span data-ttu-id="b1501-163">INTERVAL_LENGTH_MINUTES determina l'intervallo di tempo in cui vengono aggregati i dati delle statistiche di esecuzione di runtime nell'archivio query.</span><span class="sxs-lookup"><span data-stu-id="b1501-163">INTERVAL_LENGTH_MINUTES Determines the time interval at which runtime execution statistics data is aggregated into the query store.</span></span> <span data-ttu-id="b1501-164">Per ottimizzare l'utilizzo dello spazio, le statistiche di esecuzione di runtime nell'archivio delle statistiche di runtime vengono aggregate in un intervallo di tempo fisso.</span><span class="sxs-lookup"><span data-stu-id="b1501-164">To optimize for space usage, the runtime execution statistics in the Runtime Stats Store are aggregated over a fixed time window.</span></span> <span data-ttu-id="b1501-165">L'intervallo di tempo predefinito viene configurato tramite INTERVAL_LENGTH_MINUTES.</span><span class="sxs-lookup"><span data-stu-id="b1501-165">This fixed time window is configured via INTERVAL_LENGTH_MINUTES.</span></span>

 <span data-ttu-id="b1501-166">Per determinare le opzioni correnti dell'archivio query, eseguire una query sulla vista `sys.database_query_store_options`.</span><span class="sxs-lookup"><span data-stu-id="b1501-166">Query the `sys.database_query_store_options` view to determine the current options of the query store.</span></span>

 <span data-ttu-id="b1501-167">Per altre informazioni sull'impostazione di opzioni con istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] , vedere [Gestione delle opzioni](#OptionMgmt).</span><span class="sxs-lookup"><span data-stu-id="b1501-167">For more information about setting options by using [!INCLUDE[tsql](../../includes/tsql-md.md)] statements, see [Option Management](#OptionMgmt).</span></span>

 

##  <a name="related-views-functions-and-procedures"></a><a name="Related"></a> <span data-ttu-id="b1501-168">Viste, funzioni e procedure correlate</span><span class="sxs-lookup"><span data-stu-id="b1501-168">Related Views, Functions, and Procedures</span></span>
 <span data-ttu-id="b1501-169">È possibile visualizzare e gestire Archivio query con [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)] oppure usando le viste e le procedure seguenti.</span><span class="sxs-lookup"><span data-stu-id="b1501-169">The Query Store can be viewed and managed through [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)] or by using the following views and procedures.</span></span>

-   [<span data-ttu-id="b1501-170">sys.fn_stmt_sql_handle_from_sql_stmt &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b1501-170">sys.fn_stmt_sql_handle_from_sql_stmt &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-functions/sys-fn-stmt-sql-handle-from-sql-stmt-transact-sql)

### <a name="query-store-catalog-views"></a><span data-ttu-id="b1501-171">Viste del catalogo di Archivio query</span><span class="sxs-lookup"><span data-stu-id="b1501-171">Query Store Catalog Views</span></span>
 <span data-ttu-id="b1501-172">Le informazioni su Archivio query vengono presentate in sette viste del catalogo.</span><span class="sxs-lookup"><span data-stu-id="b1501-172">Seven catalog views present information about the Query Store.</span></span>

-   [<span data-ttu-id="b1501-173">sys.database_query_store_options &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b1501-173">sys.database_query_store_options &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-database-query-store-options-transact-sql)

-   [<span data-ttu-id="b1501-174">sys.query_context_settings &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b1501-174">sys.query_context_settings &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-query-context-settings-transact-sql)

-   [<span data-ttu-id="b1501-175">sys.query_store_plan &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b1501-175">sys.query_store_plan &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-query-store-plan-transact-sql)

-   [<span data-ttu-id="b1501-176">sys.query_store_query &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b1501-176">sys.query_store_query &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-query-store-query-transact-sql)

-   [<span data-ttu-id="b1501-177">sys.query_store_query_text &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b1501-177">sys.query_store_query_text &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-query-store-query-text-transact-sql)

-   [<span data-ttu-id="b1501-178">sys.query_store_runtime_stats &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b1501-178">sys.query_store_runtime_stats &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-query-store-runtime-stats-transact-sql)

-   [<span data-ttu-id="b1501-179">sys.query_store_runtime_stats_interval &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b1501-179">sys.query_store_runtime_stats_interval &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-query-store-runtime-stats-interval-transact-sql)

### <a name="query-store-stored-procedures"></a><span data-ttu-id="b1501-180">Stored procedure di Archivio query</span><span class="sxs-lookup"><span data-stu-id="b1501-180">Query Store Stored Procedures</span></span>
 <span data-ttu-id="b1501-181">Per configurare Archivio query, vengono invece usate sei stored procedure.</span><span class="sxs-lookup"><span data-stu-id="b1501-181">Six stored procedures configure the Query Store.</span></span>

-   [<span data-ttu-id="b1501-182">sp_query_store_flush_db &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b1501-182">sp_query_store_flush_db &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-query-store-flush-db-transact-sql)

-   [<span data-ttu-id="b1501-183">sp_query_store_reset_exec_stats &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b1501-183">sp_query_store_reset_exec_stats &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-query-store-reset-exec-stats-transact-sql)

-   [<span data-ttu-id="b1501-184">sp_query_store_force_plan &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b1501-184">sp_query_store_force_plan &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-query-store-force-plan-transact-sql)

-   [<span data-ttu-id="b1501-185">sp_query_store_unforce_plan &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b1501-185">sp_query_store_unforce_plan &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-query-store-unforce-plan-transact-sql)

-   [<span data-ttu-id="b1501-186">sp_query_store_remove_plan &#40;Transct-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b1501-186">sp_query_store_remove_plan &#40;Transct-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-query-store-remove-plan-transct-sql)

-   [<span data-ttu-id="b1501-187">sp_query_store_remove_query &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b1501-187">sp_query_store_remove_query &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-query-store-remove-query-transact-sql)



##  <a name="key-usage-scenarios"></a><a name="Scenarios"></a> <span data-ttu-id="b1501-188">Principali scenari di utilizzo</span><span class="sxs-lookup"><span data-stu-id="b1501-188">Key Usage Scenarios</span></span>

###  <a name="option-management"></a><a name="OptionMgmt"></a> <span data-ttu-id="b1501-189">Gestione delle opzioni</span><span class="sxs-lookup"><span data-stu-id="b1501-189">Option Management</span></span>
 <span data-ttu-id="b1501-190">Questa sezione fornisce alcune linee guida per la gestione della funzionalità Archivio query.</span><span class="sxs-lookup"><span data-stu-id="b1501-190">This section provides some guidelines on managing Query Store feature itself.</span></span>

 <span data-ttu-id="b1501-191">**Come sapere se la funzionalità Archivio query è attualmente attiva**</span><span class="sxs-lookup"><span data-stu-id="b1501-191">**Is Query Store currently active?**</span></span>

 <span data-ttu-id="b1501-192">I dati della funzionalità Query Store vengono archiviati nel database utente ed è quindi previsto un limite per le dimensioni, che viene configurato con `MAX_STORAGE_SIZE_MB`.</span><span class="sxs-lookup"><span data-stu-id="b1501-192">Query Store stores its data inside the user database and that is why it has size limit (configured  with `MAX_STORAGE_SIZE_MB`).</span></span> <span data-ttu-id="b1501-193">Se i dati in Archivio query raggiungono tale limite, lo stato cambia automaticamente da lettura/scrittura a sola lettura e la raccolta di nuovi dati viene interrotta.</span><span class="sxs-lookup"><span data-stu-id="b1501-193">If data in Query Store hits that limit Query Store will automatically change state from read-write to read-only and stop collecting new data.</span></span>

 <span data-ttu-id="b1501-194">Eseguire lo script seguente per determinare se la funzionalità Archivio query è attualmente attiva e se la raccolta delle statistiche di runtime viene eseguita o meno.</span><span class="sxs-lookup"><span data-stu-id="b1501-194">Execute the following script to determine if Query Store is currently active, and whether it is currently collects runtime stats or not.</span></span>

```
DECLARE @x nvarchar(100) = CAST(newid() AS nvarchar(100));
DECLARE @query nvarchar(max) = 
N'IF EXISTS
(
    SELECT * 
    FROM sys.query_store_query_text 
    WHERE query_sql_text LIKE ''%' + @x + N'%''
)
SELECT ''Query Store is active'' ;
ELSE SELECT ''Query Store is NOT active''' ;
EXEC sp_executesql @query;
```

 <span data-ttu-id="b1501-195">**Ottenere le opzioni di Archivio query**</span><span class="sxs-lookup"><span data-stu-id="b1501-195">**Get Query Store options**</span></span>

 <span data-ttu-id="b1501-196">Per informazioni dettagliate sullo stato di Archivio query, eseguire l'istruzione seguente in un database utente.</span><span class="sxs-lookup"><span data-stu-id="b1501-196">To find out detailed information about Query Store status, execute following in a user database.</span></span>

```
SELECT * FROM sys.database_query_store_options;
```

 <span data-ttu-id="b1501-197">**Impostazione dell'intervallo di Archivio query**</span><span class="sxs-lookup"><span data-stu-id="b1501-197">**Setting Query Store interval**</span></span>

 <span data-ttu-id="b1501-198">È possibile ignorare l'intervallo per l'aggregazione delle statistiche di runtime delle query (impostazione predefinita: 60 minuti).</span><span class="sxs-lookup"><span data-stu-id="b1501-198">You can override interval for aggregating query runtime statistics (default is 60 minutes).</span></span>

```

      USE master;
GO

ALTER DATABASE <database_name> 
SET QUERY_STORE (INTERVAL_LENGTH_MINUTES = 15);
```

 <span data-ttu-id="b1501-199">Si noti che non sono consentiti valori arbitrari. È necessario usare uno dei valori seguenti: 1, 5, 10, 15, 30 e 60.</span><span class="sxs-lookup"><span data-stu-id="b1501-199">Note that arbitrary values are not allowed - you should use one of the following: 1, 5, 10, 15, 30 and 60.</span></span>

 <span data-ttu-id="b1501-200">Il nuovo valore per l'intervallo viene esposto tramite la vista `sys.database_query_store_options`.</span><span class="sxs-lookup"><span data-stu-id="b1501-200">New value for interval is exposed through `sys.database_query_store_options` view.</span></span>

 <span data-ttu-id="b1501-201">Se lo spazio di archiviazione di Archivio query è esaurito, usare l'istruzione seguente per estenderlo.</span><span class="sxs-lookup"><span data-stu-id="b1501-201">If the Query Store storage is full use the following statement to extend the storage.</span></span>

```
ALTER DATABASE <database_name> 
SET QUERY_STORE (MAX_STORAGE_SIZE_MB = <new_size>);
```

 <span data-ttu-id="b1501-202">**Impostare tutte le opzioni di Archivio query**</span><span class="sxs-lookup"><span data-stu-id="b1501-202">**Set all Query Store options**</span></span>

 <span data-ttu-id="b1501-203">È possibile impostare più opzioni di Archivio query contemporaneamente con un'unica istruzione ALTER DATABASE.</span><span class="sxs-lookup"><span data-stu-id="b1501-203">You can set multiple Query Store options at once with a single ALTER DATABASE statement.</span></span>

```
ALTER DATABASE <database name> 
SET QUERY_STORE (
    OPERATION_MODE = READ_WRITE,
    CLEANUP_POLICY = 
    (STALE_QUERY_THRESHOLD_DAYS = 30),
    DATA_FLUSH_INTERVAL_SECONDS = 3000,
    MAX_STORAGE_SIZE_MB = 500,
    INTERVAL_LENGTH_MINUTES = 15
);
```

 <span data-ttu-id="b1501-204">**Pulizia dello spazio**</span><span class="sxs-lookup"><span data-stu-id="b1501-204">**Cleaning up the space**</span></span>

 <span data-ttu-id="b1501-205">Le tabelle interne di Archivio query vengono create nel filegroup PRIMARY durante la creazione del database e tale configurazione non è modificabile in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="b1501-205">Query Store internal tables are created in the PRIMARY filegroup during database creation and that configuration cannot be changed later.</span></span> <span data-ttu-id="b1501-206">Se si esaurisce lo spazio, è possibile cancellare dati di Archivio query meno recenti usando l'istruzione seguente.</span><span class="sxs-lookup"><span data-stu-id="b1501-206">If you are running out of space you might want to clear older Query Store data by using the following statement.</span></span>

```
ALTER DATABASE <db_name> SET QUERY_STORE CLEAR;
```

 <span data-ttu-id="b1501-207">In alternativa, è possibile cancellare solo dati di query ad hoc perché sono meno rilevanti per le ottimizzazioni query e l'analisi del piano, ma occupano molto spazio.</span><span class="sxs-lookup"><span data-stu-id="b1501-207">Alternatively, you might want to clear up only ad-hoc query data, since it is less relevant for query optimizations and plan analysis but takes up just as much space.</span></span>

 <span data-ttu-id="b1501-208">**Eliminare query ad-hoc** È possibile eliminare le query che sono state eseguite solo una volta e che risalgono a più di 24 ore prima.</span><span class="sxs-lookup"><span data-stu-id="b1501-208">**Delete ad-hoc queries** This deletes the queries that were only executed only once and that are more than 24 hours old.</span></span>

```
DECLARE @id int
DECLARE adhoc_queries_cursor CURSOR 
FOR 
SELECT q.query_id
FROM sys.query_store_query_text AS qt
JOIN sys.query_store_query AS q 
    ON q.query_text_id = qt.query_text_id
JOIN sys.query_store_plan AS p 
    ON p.query_id = q.query_id
JOIN sys.query_store_runtime_stats AS rs 
    ON rs.plan_id = p.plan_id
GROUP BY q.query_id
HAVING SUM(rs.count_executions) < 2 
AND MAX(rs.last_execution_time) < DATEADD (hour, -24, GETUTCDATE())
ORDER BY q.query_id ;

OPEN adhoc_queries_cursor ;
FETCH NEXT FROM adhoc_queries_cursor INTO @id;
WHILE @@fetch_status = 0
    BEGIN 
        PRINT @id
        EXEC sp_query_store_remove_query @id
        FETCH NEXT FROM adhoc_queries_cursor INTO @id
    END 
CLOSE adhoc_queries_cursor ;
DEALLOCATE adhoc_queries_cursor;
```

 <span data-ttu-id="b1501-209">Per la cancellazione dei dati che non sono più rilevanti, è possibile definire procedure personalizzate con logiche diverse.</span><span class="sxs-lookup"><span data-stu-id="b1501-209">You can define your own procedure with different logic for clearing up the data that is no longer important for you.</span></span>

 <span data-ttu-id="b1501-210">Per rimuovere i dati non necessari, nell'esempio precedente viene usata la stored procedure estesa `sp_query_store_remove_query`.</span><span class="sxs-lookup"><span data-stu-id="b1501-210">The example above uses the `sp_query_store_remove_query` extended stored procedure for removing unnecessary data.</span></span> <span data-ttu-id="b1501-211">È anche possibile usare altre due procedure.</span><span class="sxs-lookup"><span data-stu-id="b1501-211">You can also use two other procedures.</span></span>

-   <span data-ttu-id="b1501-212">`sp_query_store_reset_exec_stats`-Cancella le statistiche di runtime per un determinato piano.</span><span class="sxs-lookup"><span data-stu-id="b1501-212">`sp_query_store_reset_exec_stats` - clear runtime statistics for a given plan.</span></span>

-   <span data-ttu-id="b1501-213">`sp_query_store_remove_plan`-Rimuove un singolo piano.</span><span class="sxs-lookup"><span data-stu-id="b1501-213">`sp_query_store_remove_plan` - removes a single plan.</span></span>



###  <a name="performance-auditing-and-troubleshooting"></a><a name="Peformance"></a> <span data-ttu-id="b1501-214">Controllo delle prestazioni e risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="b1501-214">Performance Auditing and Troubleshooting</span></span>
 <span data-ttu-id="b1501-215">Dal momento che Archivio query conserva la cronologia delle metriche relative a compilazione e runtime per tutte le esecuzioni delle query, è possibile rispondere facilmente a numerose domande relative al carico di lavoro.</span><span class="sxs-lookup"><span data-stu-id="b1501-215">Because Query Store keeps history of compilation and runtime metrics throughout query executions there are many different questions you can easily answer with regards to your workload.</span></span>

 <span data-ttu-id="b1501-216">**Ultime *n* query eseguite sul database.**</span><span class="sxs-lookup"><span data-stu-id="b1501-216">**Last *n* queries executed on the database.**</span></span>

```
SELECT TOP 10 qt.query_sql_text, q.query_id, 
    qt.query_text_id, p.plan_id, rs.last_execution_time
FROM sys.query_store_query_text AS qt 
JOIN sys.query_store_query AS q 
    ON qt.query_text_id = q.query_text_id 
JOIN sys.query_store_plan AS p 
    ON q.query_id = p.query_id 
JOIN sys.query_store_runtime_stats AS rs 
    ON p.plan_id = rs.plan_id
ORDER BY rs.last_execution_time DESC;
```

 <span data-ttu-id="b1501-217">**Numero di esecuzioni per ogni query.**</span><span class="sxs-lookup"><span data-stu-id="b1501-217">**Number of executions for each query.**</span></span>

```
SELECT q.query_id, qt.query_text_id, qt.query_sql_text, 
    SUM(rs.count_executions) AS total_execution_count
FROM sys.query_store_query_text AS qt 
JOIN sys.query_store_query AS q 
    ON qt.query_text_id = q.query_text_id 
JOIN sys.query_store_plan AS p 
    ON q.query_id = p.query_id 
JOIN sys.query_store_runtime_stats AS rs 
    ON p.plan_id = rs.plan_id
GROUP BY q.query_id, qt.query_text_id, qt.query_sql_text
ORDER BY total_execution_count DESC;
```

 <span data-ttu-id="b1501-218">**Numero di query con il tempo medio di esecuzione più lungo nell'ultima ora.**</span><span class="sxs-lookup"><span data-stu-id="b1501-218">**The number of queries with the longest average execution time within last hour.**</span></span>

```
SELECT TOP 10 rs.avg_duration, qt.query_sql_text, q.query_id,
    qt.query_text_id, p.plan_id, GETUTCDATE() AS CurrentUTCTime, 
    rs.last_execution_time 
FROM sys.query_store_query_text AS qt 
JOIN sys.query_store_query AS q 
    ON qt.query_text_id = q.query_text_id 
JOIN sys.query_store_plan AS p 
    ON q.query_id = p.query_id 
JOIN sys.query_store_runtime_stats AS rs 
    ON p.plan_id = rs.plan_id
WHERE rs.last_execution_time > DATEADD(hour, -1, GETUTCDATE())
ORDER BY rs.avg_duration DESC;
```

 <span data-ttu-id="b1501-219">**Numero di query con il numero medio di operazioni di i/o fisico più grande nelle ultime 24 ore, con il numero medio di righe e il conteggio delle esecuzioni corrispondente.**</span><span class="sxs-lookup"><span data-stu-id="b1501-219">**The number of queries that had the biggest average physical IO reads in last 24 hours, with corresponding average row count and execution count.**</span></span>

```
SELECT TOP 10 rs.avg_physical_io_reads, qt.query_sql_text, 
    q.query_id, qt.query_text_id, p.plan_id, rs.runtime_stats_id, 
    rsi.start_time, rsi.end_time, rs.avg_rowcount, rs.count_executions
FROM sys.query_store_query_text AS qt 
JOIN sys.query_store_query AS q 
    ON qt.query_text_id = q.query_text_id 
JOIN sys.query_store_plan AS p 
    ON q.query_id = p.query_id 
JOIN sys.query_store_runtime_stats AS rs 
    ON p.plan_id = rs.plan_id 
JOIN sys.query_store_runtime_stats_interval AS rsi 
    ON rsi.runtime_stats_interval_id = rs.runtime_stats_interval_id
WHERE rsi.start_time >= DATEADD(hour, -24, GETUTCDATE()) 
ORDER BY rs.avg_physical_io_reads DESC;
```

 <span data-ttu-id="b1501-220">**Query con più piani.**</span><span class="sxs-lookup"><span data-stu-id="b1501-220">**Queries with multiple plans.**</span></span> <span data-ttu-id="b1501-221">Queste query sono particolarmente interessanti perché sono candidati a regressioni in seguito alla modifica del piano selezionato.</span><span class="sxs-lookup"><span data-stu-id="b1501-221">These queries are especially interesting because they are candidates for regressions due to plan choice change.</span></span> <span data-ttu-id="b1501-222">La query seguente consente di identificare queste query unitamente a tutti i piani:</span><span class="sxs-lookup"><span data-stu-id="b1501-222">The following query identifies these queries along with all plans:</span></span>

```
WITH Query_MultPlans
AS
(
    SELECT COUNT(*) AS cnt, q.query_id 
    FROM sys.query_store_query_text AS qt
    JOIN sys.query_store_query AS q
        ON qt.query_text_id = q.query_text_id
    JOIN sys.query_store_plan AS p
        ON p.query_id = q.query_id
    GROUP BY q.query_id
    HAVING COUNT(distinct plan_id) > 1
)

SELECT q.query_id, object_name(object_id) AS ContainingObject, query_sql_text,
plan_id, p.query_plan AS plan_xml,
p.last_compile_start_time, p.last_execution_time
FROM Query_MultPlans AS qm
JOIN sys.query_store_query AS q
    ON qm.query_id = q.query_id
JOIN sys.query_store_plan AS p
    ON q.query_id = p.query_id
JOIN sys.query_store_query_text qt 
    ON qt.query_text_id = q.query_text_id
ORDER BY query_id, plan_id;
```

 <span data-ttu-id="b1501-223">**Query di cui è stato recentemente effettuato il regresso in termini di prestazioni (confronto tra temporizzazioni diverse).**</span><span class="sxs-lookup"><span data-stu-id="b1501-223">**Queries that recently regressed in performance (comparing different point in time).**</span></span> <span data-ttu-id="b1501-224">L'esempio di query seguente restituisce tutte le query in cui il tempo di esecuzione è raddoppiato nelle ultime 48 ore in seguito alla modifica del piano selezionato.</span><span class="sxs-lookup"><span data-stu-id="b1501-224">The following query example returns all queries for which execution time doubled in last 48 hours due to a plan choice change.</span></span> <span data-ttu-id="b1501-225">La query confronta tutti gli intervalli delle statistiche di runtime affiancandoli.</span><span class="sxs-lookup"><span data-stu-id="b1501-225">Query compares all runtime stat intervals side by side.</span></span>

```
SELECT 
    qt.query_sql_text, 
    q.query_id, 
    qt.query_text_id, 
    rs1.runtime_stats_id AS runtime_stats_id_1,
    rsi1.start_time AS interval_1, 
    p1.plan_id AS plan_1, 
    rs1.avg_duration AS avg_duration_1, 
    rs2.avg_duration AS avg_duration_2,
    p2.plan_id AS plan_2, 
    rsi2.start_time AS interval_2, 
    rs2.runtime_stats_id AS runtime_stats_id_2
FROM sys.query_store_query_text AS qt 
JOIN sys.query_store_query AS q 
    ON qt.query_text_id = q.query_text_id 
JOIN sys.query_store_plan AS p1 
    ON q.query_id = p1.query_id 
JOIN sys.query_store_runtime_stats AS rs1 
    ON p1.plan_id = rs1.plan_id 
JOIN sys.query_store_runtime_stats_interval AS rsi1 
    ON rsi1.runtime_stats_interval_id = rs1.runtime_stats_interval_id 
JOIN sys.query_store_plan AS p2 
    ON q.query_id = p2.query_id 
JOIN sys.query_store_runtime_stats AS rs2 
    ON p2.plan_id = rs2.plan_id 
JOIN sys.query_store_runtime_stats_interval AS rsi2 
    ON rsi2.runtime_stats_interval_id = rs2.runtime_stats_interval_id
WHERE rsi1.start_time > DATEADD(hour, -48, GETUTCDATE()) 
    AND rsi2.start_time > rsi1.start_time 
    AND p1.plan_id <> p2.plan_id
    AND rs2.avg_duration > 2*rs1.avg_duration
ORDER BY q.query_id, rsi1.start_time, rsi2.start_time;
```

 <span data-ttu-id="b1501-226">Per visualizzare tutte le regressioni delle prestazioni, non solo quelle correlate alla modifica del piano selezionato, è sufficiente rimuovere la condizione `AND p1.plan_id <> p2.plan_id` dalla query precedente.</span><span class="sxs-lookup"><span data-stu-id="b1501-226">If you want to see performance all regressions (not only those related to plan choice change) than just remove condition `AND p1.plan_id <> p2.plan_id` from the previous query.</span></span>

 <span data-ttu-id="b1501-227">**Query che hanno recentemente regressione nelle prestazioni (confronto tra l'esecuzione recente e la cronologia).**</span><span class="sxs-lookup"><span data-stu-id="b1501-227">**Queries that recently regressed in performance (comparing recent vs. history execution).**</span></span> <span data-ttu-id="b1501-228">La query successiva confronta le esecuzioni di query in base ai periodi di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="b1501-228">The next query compares query execution based periods of execution.</span></span> <span data-ttu-id="b1501-229">In questo specifico esempio la query confronta le esecuzioni nel periodo recente (1 ora) con il periodo della cronologia (ultimo giorno) e identifica quelle che hanno introdotto additional_duration_workload.</span><span class="sxs-lookup"><span data-stu-id="b1501-229">In this particular example the query compares execution in recent period (1 hour) vs. history period (last day) and identifies those that introduced additional_duration_workload.</span></span> <span data-ttu-id="b1501-230">Questa metrica viene ottenuta moltiplicando la differenza tra l'esecuzione media recente e quella media della cronologia e il numero delle esecuzioni recenti.</span><span class="sxs-lookup"><span data-stu-id="b1501-230">This metrics is calculated as a difference between recent average execution and history average execution multiplied by the number of recent executions.</span></span> <span data-ttu-id="b1501-231">Rappresenta in effetti la quantità di esecuzioni recenti con durata aggiuntiva introdotte rispetto alla cronologia:</span><span class="sxs-lookup"><span data-stu-id="b1501-231">It actually represents how much of additional duration recent executions introduced compared to history:</span></span>

```
--- "Recent" workload - last 1 hour
DECLARE @recent_start_time datetimeoffset;
DECLARE @recent_end_time datetimeoffset;
SET @recent_start_time = DATEADD(hour, -1, SYSUTCDATETIME());
SET @recent_end_time = SYSUTCDATETIME();

--- "History" workload
DECLARE @history_start_time datetimeoffset;
DECLARE @history_end_time datetimeoffset;
SET @history_start_time = DATEADD(hour, -24, SYSUTCDATETIME());
SET @history_end_time = SYSUTCDATETIME();

WITH
hist AS
(
    SELECT 
        p.query_id query_id, 
        CONVERT(float, SUM(rs.avg_duration*rs.count_executions)) total_duration, 
        SUM(rs.count_executions) count_executions,
        COUNT(distinct p.plan_id) num_plans 
     FROM sys.query_store_runtime_stats AS rs
        JOIN sys.query_store_plan p ON p.plan_id = rs.plan_id
    WHERE  (rs.first_execution_time >= @history_start_time AND rs.last_execution_time < @history_end_time)
        OR (rs.first_execution_time <= @history_start_time AND rs.last_execution_time > @history_start_time)
        OR (rs.first_execution_time <= @history_end_time AND rs.last_execution_time > @history_end_time)
    GROUP BY p.query_id
),
recent AS
(
    SELECT 
        p.query_id query_id, 
        CONVERT(float, SUM(rs.avg_duration*rs.count_executions)) total_duration, 
        SUM(rs.count_executions) count_executions,
        COUNT(distinct p.plan_id) num_plans 
    FROM sys.query_store_runtime_stats AS rs
        JOIN sys.query_store_plan p ON p.plan_id = rs.plan_id
    WHERE  (rs.first_execution_time >= @recent_start_time AND rs.last_execution_time < @recent_end_time)
        OR (rs.first_execution_time <= @recent_start_time AND rs.last_execution_time > @recent_start_time)
        OR (rs.first_execution_time <= @recent_end_time AND rs.last_execution_time > @recent_end_time)
    GROUP BY p.query_id
)
SELECT 
    results.query_id query_id,
    results.query_text query_text,
    results.additional_duration_workload additional_duration_workload,
    results.total_duration_recent total_duration_recent,
    results.total_duration_hist total_duration_hist,
    ISNULL(results.count_executions_recent, 0) count_executions_recent,
    ISNULL(results.count_executions_hist, 0) count_executions_hist 
FROM
(
    SELECT
        hist.query_id query_id,
        qt.query_sql_text query_text,
        ROUND(CONVERT(float, recent.total_duration/recent.count_executions-hist.total_duration/hist.count_executions)*(recent.count_executions), 2) AS additional_duration_workload,
        ROUND(recent.total_duration, 2) total_duration_recent, 
        ROUND(hist.total_duration, 2) total_duration_hist,
        recent.count_executions count_executions_recent,
        hist.count_executions count_executions_hist   
    FROM hist 
        JOIN recent 
            ON hist.query_id = recent.query_id 
        JOIN sys.query_store_query AS q 
            ON q.query_id = hist.query_id
        JOIN sys.query_store_query_text AS qt 
            ON q.query_text_id = qt.query_text_id    
) AS results
WHERE additional_duration_workload > 0
ORDER BY additional_duration_workload DESC
OPTION (MERGE JOIN);
```



###  <a name="maintaining-query-performance-stability"></a><a name="Stability"></a><span data-ttu-id="b1501-232">Gestione della stabilità delle prestazioni delle query</span><span class="sxs-lookup"><span data-stu-id="b1501-232">Maintaining Query Performance Stability</span></span>
 <span data-ttu-id="b1501-233">Per le query eseguite più volte è possibile notare che in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] sono stati usati piani diversi che hanno comportato durate e utilizzi diversi delle risorse.</span><span class="sxs-lookup"><span data-stu-id="b1501-233">For queries that are executed multiple times you may notice that [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] used different plans which resulted in different resource utilization and duration.</span></span> <span data-ttu-id="b1501-234">Archivio query consente di rilevare facilmente il momento in cui si verifica una regressione delle prestazioni di esecuzione delle query e di determinare il piano ottimale in un periodo di interesse.</span><span class="sxs-lookup"><span data-stu-id="b1501-234">With Query Store you can easily detect when the query performance regressed and determine the optimal plan within a period of interest.</span></span> <span data-ttu-id="b1501-235">È quindi possibile forzare il piano ottimale per le future esecuzioni delle query.</span><span class="sxs-lookup"><span data-stu-id="b1501-235">Then you can force that optimal plan for future query execution.</span></span>

 <span data-ttu-id="b1501-236">È anche possibile identificare incoerenze nelle prestazioni di una query con parametri (impostati sia automaticamente che manualmente).</span><span class="sxs-lookup"><span data-stu-id="b1501-236">You can also identify inconsistent query performance for a query with parameters (either auto- parameterized or manually parameterized).</span></span> <span data-ttu-id="b1501-237">Tra i diversi piani è possibile identificare quello più rapido e adatto per tutti o per la maggior parte dei valori di parametro e forzarne l'uso in modo da garantire prestazioni prevedibili per un ampio numero di scenari utente.</span><span class="sxs-lookup"><span data-stu-id="b1501-237">Among different plans you can identify plan which is fast and optimal enough for all or most of the parameter values and force that plan; keeping predictable performance for the wider set of user scenarios.</span></span>

 <span data-ttu-id="b1501-238">**Forzare un piano per una query (applicando criteri di utilizzo forzato).**</span><span class="sxs-lookup"><span data-stu-id="b1501-238">**Force or a plan for a query (apply forcing policy).**</span></span> <span data-ttu-id="b1501-239">Quando si forza un piano per una determinata query, la query viene sempre eseguita con il piano di cui è stato forzato l'utilizzo.</span><span class="sxs-lookup"><span data-stu-id="b1501-239">When a plan is forced for a certain query, every time a query comes to execution it will be executed with the plan that is forced.</span></span>

```
EXEC sp_query_store_force_plan @query_id = 48, @plan_id = 49;
```

 <span data-ttu-id="b1501-240">Se si usa `sp_query_store_force_plan`, è possibile forzare solo piani che sono stati registrati da Archivio query come piani per tale query.</span><span class="sxs-lookup"><span data-stu-id="b1501-240">When using `sp_query_store_force_plan` you can only force plans that were recorded by Query Store as a plan for that query.</span></span> <span data-ttu-id="b1501-241">In altre parole, gli unici piani disponibili per una query sono quelli già usati per eseguire Q1 mentre Archivio query era attivo.</span><span class="sxs-lookup"><span data-stu-id="b1501-241">In other words, the only plans available for a query are those that were already used to execute Q1 while Query Store was active.</span></span>

 <span data-ttu-id="b1501-242">**Rimuovere l'utilizzo forzato del piano per una query.**</span><span class="sxs-lookup"><span data-stu-id="b1501-242">**Remove plan forcing for a query.**</span></span> <span data-ttu-id="b1501-243">Per basarsi nuovamente sul [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Query Optimizer per calcolare il piano di query ottimale, utilizzare `sp_query_store_unforce_plan` per disforzare il piano selezionato per la query.</span><span class="sxs-lookup"><span data-stu-id="b1501-243">To rely again on the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] query optimizer to calculate the optimal query plan, use `sp_query_store_unforce_plan` to unforce the plan that was selected for the query.</span></span>

```
EXEC sp_query_store_unforce_plan @query_id = 48, @plan_id = 49;
```



## <a name="see-also"></a><span data-ttu-id="b1501-244">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b1501-244">See Also</span></span>
 <span data-ttu-id="b1501-245">[Monitoraggio e ottimizzazione degli strumenti di](../performance/monitor-and-tune-for-performance.md) [monitoraggio e ottimizzazione delle prestazioni](../performance/performance-monitoring-and-tuning-tools.md) delle prestazioni aprire Monitoraggio [attività &#40;SQL Server Management Studio](../performance-monitor/open-activity-monitor-sql-server-management-studio.md) monitoraggio [attività](../performance-monitor/activity-monitor.md)&#41;</span><span class="sxs-lookup"><span data-stu-id="b1501-245">[Monitor and Tune for Performance](../performance/monitor-and-tune-for-performance.md) [Performance Monitoring and Tuning Tools](../performance/performance-monitoring-and-tuning-tools.md) [Open Activity Monitor &#40;SQL Server Management Studio&#41;](../performance-monitor/open-activity-monitor-sql-server-management-studio.md) [Activity Monitor](../performance-monitor/activity-monitor.md)</span></span>


