---
title: Proprietà database (pagina Archivio query) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- sql13.swb.databaseproperties.querystore.f1
ms.assetid: da47d75e-291a-4305-acef-4b0aaf5215da
author: stevestein
ms.author: sstein
ms.openlocfilehash: bab0d9b697e9ad9ec4b27f320d26b9b9edb5944e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718222"
---
# <a name="database-properties-query-store-page"></a><span data-ttu-id="e0974-102">Proprietà database (pagina Archivio query)</span><span class="sxs-lookup"><span data-stu-id="e0974-102">Database Properties (Query Store Page)</span></span>
  <span data-ttu-id="e0974-103">Accedere a questa pagina dal database principale e usarla per configurare e modificare le proprietà dell'archivio query del database.</span><span class="sxs-lookup"><span data-stu-id="e0974-103">Access this page from the principal database, and use it to configure and to modify the properties of the database query store.</span></span> <span data-ttu-id="e0974-104">È anche possibile configurare queste opzioni con le [opzioni ALTER DATABASE SET](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span><span class="sxs-lookup"><span data-stu-id="e0974-104">These options can also be configure by using the [ALTER DATABASE SET options](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span></span> <span data-ttu-id="e0974-105">Per informazioni sull'archivio query, vedere [Monitoring Performance By Using the Query Store](../performance/monitoring-performance-by-using-the-query-store.md).</span><span class="sxs-lookup"><span data-stu-id="e0974-105">For information about the query store, see [Monitoring Performance By Using the Query Store](../performance/monitoring-performance-by-using-the-query-store.md).</span></span>  
  
||  
|-|  
|<span data-ttu-id="e0974-106">**Si applica a**: [!INCLUDE[sqldbesa](../../includes/sqldbesa-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e0974-106">**Applies to**: [!INCLUDE[sqldbesa](../../includes/sqldbesa-md.md)].</span></span>|  
  
## <a name="options"></a><span data-ttu-id="e0974-107">Opzioni</span><span class="sxs-lookup"><span data-stu-id="e0974-107">Options</span></span>  
 <span data-ttu-id="e0974-108">Abilitare</span><span class="sxs-lookup"><span data-stu-id="e0974-108">Enable</span></span>  
 <span data-ttu-id="e0974-109">Abilita e disabilita l'archivio query.</span><span class="sxs-lookup"><span data-stu-id="e0974-109">Enables and disables the query store.</span></span>  
  
 <span data-ttu-id="e0974-110">Modalità operativa</span><span class="sxs-lookup"><span data-stu-id="e0974-110">Operation Mode</span></span>  
 <span data-ttu-id="e0974-111">I valori validi sono READ_ONLY e READ_WRITE.</span><span class="sxs-lookup"><span data-stu-id="e0974-111">Valid values are READ_ONLY and READ_WRITE.</span></span> <span data-ttu-id="e0974-112">In modalità READ_WRITE l'archivio query raccoglie e mantiene le informazioni di statistiche sull'esecuzione di runtime e piani di query.</span><span class="sxs-lookup"><span data-stu-id="e0974-112">In READ_WRITE mode, the query store collects and persists query plan and runtime execution statistics information.</span></span> <span data-ttu-id="e0974-113">In modalità READ_ONLY le informazioni possono essere lette dall'archivio query, ma non vengono aggiunte nuove informazioni.</span><span class="sxs-lookup"><span data-stu-id="e0974-113">In READ_ONLY mode, information can be read from the query store, but new information is not added.</span></span> <span data-ttu-id="e0974-114">Se lo spazio massimo allocato dell'archivio query è esaurito, la modalità operativa dell'archivio query passa a READ_ONLY.</span><span class="sxs-lookup"><span data-stu-id="e0974-114">If the maximum allocated space of the query store has been exhausted, the query store will change its operation mode to READ_ONLY.</span></span>  
  
 <span data-ttu-id="e0974-115">Modalità operativa (effettiva)</span><span class="sxs-lookup"><span data-stu-id="e0974-115">Operation Mode (Actual)</span></span>  
 <span data-ttu-id="e0974-116">Ottiene la modalità operativa effettiva dell'archivio query.</span><span class="sxs-lookup"><span data-stu-id="e0974-116">Gets the actual operation mode of the query store.</span></span>  
  
 <span data-ttu-id="e0974-117">Modalità operativa (richiesta)</span><span class="sxs-lookup"><span data-stu-id="e0974-117">Operation Mode (Requested)</span></span>  
 <span data-ttu-id="e0974-118">Ottiene e imposta la modalità operativa desiderata dell'archivio query.</span><span class="sxs-lookup"><span data-stu-id="e0974-118">Gets and sets the desired operation mode of the query store.</span></span>  
  
 <span data-ttu-id="e0974-119">Intervallo di scaricamento dati (minuti)</span><span class="sxs-lookup"><span data-stu-id="e0974-119">Data Flush Interval (Minutes)</span></span>  
 <span data-ttu-id="e0974-120">Determina la frequenza con cui i dati scritti nell'archivio query vengono mantenuti su disco.</span><span class="sxs-lookup"><span data-stu-id="e0974-120">Determines the frequency at which data written to the query store is persisted to disk.</span></span> <span data-ttu-id="e0974-121">Per ottimizzare le prestazioni, i dati raccolti dall'archivio query vengono scritti in modo asincrono sul disco.</span><span class="sxs-lookup"><span data-stu-id="e0974-121">To optimize for performance, data collected by the query store is asynchronously written to the disk.</span></span> <span data-ttu-id="e0974-122">La frequenza con cui si verifica questo trasferimento asincrono è configurabile.</span><span class="sxs-lookup"><span data-stu-id="e0974-122">The frequency at which this asynchronous transfer occurs is configured.</span></span>  
  
 <span data-ttu-id="e0974-123">Intervallo di raccolta statistiche</span><span class="sxs-lookup"><span data-stu-id="e0974-123">Statistics Collection Interval</span></span>  
 <span data-ttu-id="e0974-124">Ottiene e imposta il valore dell'intervallo di raccolta delle statistiche.</span><span class="sxs-lookup"><span data-stu-id="e0974-124">Gets and sets the statistics collection interval value.</span></span>  
  
 <span data-ttu-id="e0974-125">Dimensioni massime (MB)</span><span class="sxs-lookup"><span data-stu-id="e0974-125">Max Size (MB)</span></span>  
 <span data-ttu-id="e0974-126">Ottiene e imposta lo spazio totale allocato all'archivio query.</span><span class="sxs-lookup"><span data-stu-id="e0974-126">Gets and sets the total space allocated to the query store.</span></span>  
  
 <span data-ttu-id="e0974-127">Soglia per query non aggiornate (giorni)</span><span class="sxs-lookup"><span data-stu-id="e0974-127">Stale Query Threshold (Days)</span></span>  
 <span data-ttu-id="e0974-128">Ottiene e imposta la soglia per query non aggiornate.</span><span class="sxs-lookup"><span data-stu-id="e0974-128">Gets and sets the stale query threshold.</span></span> <span data-ttu-id="e0974-129">Configurare l'argomento STALE_QUERY_THRESHOLD_DAYS per specificare il numero di giorni per la conservazione dei dati nell'archivio query.</span><span class="sxs-lookup"><span data-stu-id="e0974-129">Configure the STALE_QUERY_THRESHOLD_DAYS argument to specify the number of days to retain data in the query store.</span></span>  
  
 <span data-ttu-id="e0974-130">Elimina dati query</span><span class="sxs-lookup"><span data-stu-id="e0974-130">Purge Query Data</span></span>  
 <span data-ttu-id="e0974-131">Rimuove il contenuto dell'archivio query.</span><span class="sxs-lookup"><span data-stu-id="e0974-131">Removes the contents of the query store.</span></span>  
  
 <span data-ttu-id="e0974-132">Grafici a torta</span><span class="sxs-lookup"><span data-stu-id="e0974-132">Pie Charts</span></span>  
 <span data-ttu-id="e0974-133">Il grafico a sinistra illustra l'utilizzo totale del file di database sul disco e la parte del file occupata dai dati dell'archivio query.</span><span class="sxs-lookup"><span data-stu-id="e0974-133">The left chart shows the total database file consumption on the disk, and the portion of the file which is filled with the query store data.</span></span>  
  
 <span data-ttu-id="e0974-134">Il grafico a destra illustra la parte della quota dell'archivio query attualmente utilizzata.</span><span class="sxs-lookup"><span data-stu-id="e0974-134">The right chart shows the portion of the query store quota which is currently used up.</span></span> <span data-ttu-id="e0974-135">Si noti che la quota non è visualizzata nel grafico a sinistra</span><span class="sxs-lookup"><span data-stu-id="e0974-135">Note that the quota is not shown in the left chart.</span></span> <span data-ttu-id="e0974-136">e può superare le dimensioni correnti del database.</span><span class="sxs-lookup"><span data-stu-id="e0974-136">The quota may exceed the current size of the database.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e0974-137">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="e0974-137">Remarks</span></span>  
 <span data-ttu-id="e0974-138">La funzionalità dell'archivio query mette a disposizione degli amministratori di database informazioni dettagliate sulle prestazioni e sulla scelta del piano di query.</span><span class="sxs-lookup"><span data-stu-id="e0974-138">The query store feature provides DBAs with insight on query plan choice and performance.</span></span> <span data-ttu-id="e0974-139">Semplifica la risoluzione dei problemi in quanto consente di individuare rapidamente le variazioni delle prestazioni causate da modifiche nei piani di query.</span><span class="sxs-lookup"><span data-stu-id="e0974-139">It simplifies performance troubleshooting by enabling you to quickly find performance differences caused by changes in query plans.</span></span> <span data-ttu-id="e0974-140">La funzionalità acquisisce automaticamente una cronologia delle query, dei piani e delle statistiche di runtime e li conserva in modo che sia possibile esaminarli successivamente.</span><span class="sxs-lookup"><span data-stu-id="e0974-140">The feature automatically captures a history of queries, plans, and runtime statistics, and retains these for your review.</span></span> <span data-ttu-id="e0974-141">I dati vengono separati dagli intervalli di tempo, consentendo di visualizzare i modelli di utilizzo del database e capire quando sono state apportate modifiche al piano di query nel server.</span><span class="sxs-lookup"><span data-stu-id="e0974-141">It separates data by time windows, allowing you to see database usage patterns and understand when query plan changes happened on the server.</span></span> <span data-ttu-id="e0974-142">Per configurare l'archivio query, si può usare questa pagina delle proprietà del database dell'archivio query oppure l'opzione [ALTER DATABASE SET](/sql/t-sql/statements/alter-database-transact-sql-set-options) .</span><span class="sxs-lookup"><span data-stu-id="e0974-142">The query store can be configured by using this query store database property page, or by using the [ALTER DATABASE SET](/sql/t-sql/statements/alter-database-transact-sql-set-options) option.</span></span> <span data-ttu-id="e0974-143">Per presentare le informazioni, nell'archivio query viene usata una finestra di dialogo di [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e0974-143">The query store presents information by using a [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] dialog box.</span></span> <span data-ttu-id="e0974-144">Per altre informazioni sull'archivio query, vedere [Monitoring Performance By Using the Query Store](../performance/monitoring-performance-by-using-the-query-store.md).</span><span class="sxs-lookup"><span data-stu-id="e0974-144">For more information about query store, see [Monitoring Performance By Using the Query Store](../performance/monitoring-performance-by-using-the-query-store.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0974-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e0974-145">See Also</span></span>  
 <span data-ttu-id="e0974-146">[Stored procedure di Archivio query &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/query-store-stored-procedures-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e0974-146">[Query Store Stored Procedures &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/query-store-stored-procedures-transact-sql) </span></span>  
 [<span data-ttu-id="e0974-147">Viste del catalogo di Archivio query &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e0974-147">Query Store Catalog Views &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/query-store-catalog-views-transact-sql)  
  
  
