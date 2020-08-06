---
title: Memorizzare nella cache set di dati condivisi (SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 4acb1bbe-1c04-4979-b893-dc1b1c5039b6
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5b08149b075ae3fd267baf2dad0ca342457958c5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630319"
---
# <a name="cache-shared-datasets-ssrs"></a><span data-ttu-id="d0639-102">Memorizzare nella cache set di dati condivisi (SSRS)</span><span class="sxs-lookup"><span data-stu-id="d0639-102">Cache Shared Datasets (SSRS)</span></span>
  <span data-ttu-id="d0639-103">I risultati della query per un set di dati condiviso possono essere copiati in una cache per fornire dati coerenti per più report e migliorare il tempo di risposta per la query del set di dati.</span><span class="sxs-lookup"><span data-stu-id="d0639-103">Query results for a shared dataset can be copied to a cache to provide consistent data for multiple reports and to improve response time for the dataset query.</span></span> <span data-ttu-id="d0639-104">In modo analogo ai report, è possibile configurare un set di dati condiviso da memorizzare nella cache al momento del primo utilizzo o specificando una pianificazione.</span><span class="sxs-lookup"><span data-stu-id="d0639-104">Like reports, you can configure a shared dataset to be cached on first use or by specifying a schedule.</span></span>  
  
 <span data-ttu-id="d0639-105">Un set di dati condiviso può essere incluso in più report o come parte di definizioni del componente.</span><span class="sxs-lookup"><span data-stu-id="d0639-105">A shared dataset can be included in multiple reports or as part of component definitions.</span></span> <span data-ttu-id="d0639-106">Memorizzando nella cache il set di dati condiviso, viene fornito un set di dati coerente per tutti i report che lo utilizzano e viene inoltre ridotto il numero di esecuzioni della query del set di dati sull'origine dati esterna.</span><span class="sxs-lookup"><span data-stu-id="d0639-106">By caching the shared dataset, you provide a consistent set of data for all reports that use it, and also reduce the number of times that the dataset query runs against the external data source.</span></span>  
  
 <span data-ttu-id="d0639-107">Nell'elenco seguente vengono indicate le situazioni in cui è opportuno memorizzare nella cache un set di dati condiviso:</span><span class="sxs-lookup"><span data-stu-id="d0639-107">The following list provides examples of when to cache a shared dataset:</span></span>  
  
-   <span data-ttu-id="d0639-108">L'esecuzione della query richiede una notevole quantità di tempo.</span><span class="sxs-lookup"><span data-stu-id="d0639-108">The query takes a substantial amount of time to run.</span></span>  
  
-   <span data-ttu-id="d0639-109">La query accetta parametri, ma il numero di combinazioni di parametri è ridotto durante la maggior parte del tempo.</span><span class="sxs-lookup"><span data-stu-id="d0639-109">The query takes parameters, but most of the time, the number of parameter combinations is small.</span></span> <span data-ttu-id="d0639-110">Ogni combinazione crea risultati della query memorizzati nella cache.</span><span class="sxs-lookup"><span data-stu-id="d0639-110">Each combination creates cached query results.</span></span>  
  
-   <span data-ttu-id="d0639-111">La query viene eseguita in ore stimabili del giorno, della settimana o del mese.</span><span class="sxs-lookup"><span data-stu-id="d0639-111">The query runs at predictable times of the day, week, or month.</span></span>  
  
-   <span data-ttu-id="d0639-112">La query viene eseguita come risultato di un riferimento a un set di dati condiviso in un report recapitato tramite posta elettronica. In questo caso è probabile che un elevato numero di utenti selezioni il collegamento in un breve intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="d0639-112">The query runs as the result of a shared dataset reference in a report that is delivered via e-mail, where a large number of people are likely to click the link in a short span of time.</span></span>  
  
-   <span data-ttu-id="d0639-113">Nell'elenco seguente vengono indicate le situazioni in cui non è opportuno memorizzare nella cache un set di dati condiviso:</span><span class="sxs-lookup"><span data-stu-id="d0639-113">The following list provides examples of when not to cache a shared dataset:</span></span>  
  
-   <span data-ttu-id="d0639-114">I risultati della query devono includere sempre i dati più recenti.</span><span class="sxs-lookup"><span data-stu-id="d0639-114">The query results must always include the most recent data.</span></span>  
  
-   <span data-ttu-id="d0639-115">La query viene eseguita rapidamente.</span><span class="sxs-lookup"><span data-stu-id="d0639-115">The query runs quickly.</span></span>  
  
-   <span data-ttu-id="d0639-116">La query viene eseguita raramente.</span><span class="sxs-lookup"><span data-stu-id="d0639-116">The query runs infrequently.</span></span>  
  
-   <span data-ttu-id="d0639-117">La query accetta parametri, il numero di combinazioni di parametri è elevato e nessuna combinazione è più probabile di un'altra.</span><span class="sxs-lookup"><span data-stu-id="d0639-117">The query takes parameters, the number of parameter combinations is large, and no combination is more likely than another.</span></span>  
  
-   <span data-ttu-id="d0639-118">All'origine dati su cui si basa il set di dati condiviso sono associate credenziali richieste o della sicurezza integrata di Windows.</span><span class="sxs-lookup"><span data-stu-id="d0639-118">The data source that the shared dataset is based on has Prompt or Windows Integrated credentials.</span></span>  
  
-   <span data-ttu-id="d0639-119">Il filtro o la query del set di dati condiviso contiene un'espressione con un riferimento alla raccolta globale dell'utente.</span><span class="sxs-lookup"><span data-stu-id="d0639-119">The shared dataset filter or the query contains an expression with a reference to the global collection User.</span></span>  
  
 <span data-ttu-id="d0639-120">Se un utente sceglie valori dei parametri del report diversi dai valori predefiniti specificati per il set di risultati memorizzati nella cache, la query del set di dati viene eseguita in modo attivo e i risultati memorizzati nella cache non vengono utilizzati per tale query.</span><span class="sxs-lookup"><span data-stu-id="d0639-120">If a user chooses report parameter values that differ from the default values that are specified for the cached result set, the dataset query runs actively and the cached results are not used for that query.</span></span>  
  
## <a name="caching-shared-datasets"></a><span data-ttu-id="d0639-121">Memorizzazione nella cache di set di dati condivisi</span><span class="sxs-lookup"><span data-stu-id="d0639-121">Caching Shared Datasets</span></span>  
 <span data-ttu-id="d0639-122">Per abilitare la memorizzazione nella cache per un set di dati condiviso, è necessario selezionare l'opzione relativa nel set stesso.</span><span class="sxs-lookup"><span data-stu-id="d0639-122">To enable caching for a shared dataset, you must select the cache option on the shared dataset.</span></span> <span data-ttu-id="d0639-123">Dopo che la memorizzazione nella cache è stata abilitata, i risultati della query per un set di dati condiviso vengono copiati nella cache al momento del primo utilizzo.</span><span class="sxs-lookup"><span data-stu-id="d0639-123">After caching is enabled, the query results for a shared dataset are copied to the cache on first use.</span></span> <span data-ttu-id="d0639-124">Se al set di dati condiviso sono associati parametri, ogni combinazione di parametri crea una nuova voce nella cache.</span><span class="sxs-lookup"><span data-stu-id="d0639-124">If the shared dataset has parameters, each combination of parameters creates a new entry in the cache.</span></span>  
  
 <span data-ttu-id="d0639-125">Durante la permanenza nella cache dei risultati della query per una combinazione di parametri specifica, ogni report avviato per l'elaborazione che include un riferimento al set di dati condiviso con tali valori dei parametri utilizzerà i dati memorizzati nella cache.</span><span class="sxs-lookup"><span data-stu-id="d0639-125">While the query results for a specific parameter combination are in the cache, each report that is launched for processing and that includes a reference to the shared dataset with those parameter values will use the cached data.</span></span>  
  
 <span data-ttu-id="d0639-126">È possibile specificare la quantità di tempo in cui mantenere i dati nella cache prima che scadano.</span><span class="sxs-lookup"><span data-stu-id="d0639-126">You can specify how long to keep data in the cache before it expires.</span></span> <span data-ttu-id="d0639-127">Per altre informazioni, vedere [Pagina Memorizzazione nella cache, set di dati condivisi &40 #;Gestione report&#41;](../caching-page-shared-datasets-report-manager.md).</span><span class="sxs-lookup"><span data-stu-id="d0639-127">For more information, see [Caching Page, Shared Datasets &#40;Report Manager&#41;](../caching-page-shared-datasets-report-manager.md).</span></span>  
  
## <a name="preloading-the-cache"></a><span data-ttu-id="d0639-128">Precaricamento della cache</span><span class="sxs-lookup"><span data-stu-id="d0639-128">Preloading the Cache</span></span>  
 <span data-ttu-id="d0639-129">È possibile precaricare la cache creando un piano di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="d0639-129">You can preload the cache by creating a cache refresh plan.</span></span> <span data-ttu-id="d0639-130">che consente di specificare la frequenza di aggiornamento della cache tramite una pianificazione condivisa o specifica per l'elemento.</span><span class="sxs-lookup"><span data-stu-id="d0639-130">With a refresh plan, you can specify how often to refresh the cache by using an item-specific schedule or a shared schedule.</span></span> <span data-ttu-id="d0639-131">Per evitare che per uno stesso elemento siano presenti più voci nella cache, è necessario specificare una pianificazione in base alla quale il tempo per l'elaborazione della query sull'origine dati esterna sia sufficiente.</span><span class="sxs-lookup"><span data-stu-id="d0639-131">To avoid multiple cache entries for the same item, the schedule that you specify should allow enough time for query processing on the external data source.</span></span> <span data-ttu-id="d0639-132">Se ad esempio il tempo necessario per l'esecuzione della query è di 20 minuti, l'aggiornamento deve essere pianificato con frequenza maggiore di 20 minuti.</span><span class="sxs-lookup"><span data-stu-id="d0639-132">For example, if the query takes 20 minutes to run, the refresh schedule should be greater than 20 minutes.</span></span> <span data-ttu-id="d0639-133">Per altre informazioni, vedere [Schedules](../subscriptions/schedules.md).</span><span class="sxs-lookup"><span data-stu-id="d0639-133">For more information, see [Schedules](../subscriptions/schedules.md).</span></span>  
  
 <span data-ttu-id="d0639-134">Per creare un piano di aggiornamento della cache per un set di dati condiviso, è necessario che siano rispettate le condizioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="d0639-134">To create a cache refresh plan for a shared dataset, the following conditions apply.</span></span>  
  
-   <span data-ttu-id="d0639-135">Il set di dati condiviso deve essere abilitato per la memorizzazione nella cache.</span><span class="sxs-lookup"><span data-stu-id="d0639-135">The shared dataset must be enabled for caching.</span></span>  
  
-   <span data-ttu-id="d0639-136">L'origine dati condivisa da cui dipende il set di dati condiviso non può utilizzare credenziali richieste o della sicurezza integrata di Windows.</span><span class="sxs-lookup"><span data-stu-id="d0639-136">The shared data source that the shared dataset depends on cannot use Prompt or Windows Integrated credentials.</span></span>  
  
-   <span data-ttu-id="d0639-137">Se al set di dati condiviso sono associati parametri, è necessario specificare valori predefiniti statici per ogni parametro non contrassegnato come valore di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="d0639-137">If the shared dataset has parameters, you must specify static default values for each parameter that is not marked read-only.</span></span> <span data-ttu-id="d0639-138">I parametri di sola lettura utilizzeranno sempre il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="d0639-138">Read-only parameters will always use the default value.</span></span> <span data-ttu-id="d0639-139">Per memorizzare nella cache un set di dati condiviso per più combinazioni di parametri, è necessario creare un piano di aggiornamento della cache separato per ogni combinazione di valori.</span><span class="sxs-lookup"><span data-stu-id="d0639-139">To cache a shared dataset for multiple combinations of parameters, you must create a separate cache refresh plan for each combination of values.</span></span> <span data-ttu-id="d0639-140">I parametri non possono contenere riferimenti ad altri set di dati.</span><span class="sxs-lookup"><span data-stu-id="d0639-140">Parameters cannot contain references to other datasets.</span></span>  
  
-   <span data-ttu-id="d0639-141">Ogni piano di aggiornamento della cache è associato a un unico set di dati condiviso o report.</span><span class="sxs-lookup"><span data-stu-id="d0639-141">Each cache refresh plan is associated with only one shared dataset or report.</span></span>  
  
-   <span data-ttu-id="d0639-142">È necessario disporre delle autorizzazioni ReadPolicy e UpdatePolicy sul set di dati condiviso.</span><span class="sxs-lookup"><span data-stu-id="d0639-142">You must have ReadPolicy and UpdatePolicy permissions on the shared dataset.</span></span>  
  
 <span data-ttu-id="d0639-143">I piani di aggiornamento della cache si applicano sia ai set di dati condivisi che ai report.</span><span class="sxs-lookup"><span data-stu-id="d0639-143">Cache refresh plans apply to both shared datasets and reports.</span></span> <span data-ttu-id="d0639-144">Per altre informazioni, vedere [Opzioni di aggiornamento cache &#40;Gestione report&#41;](../cache-refresh-options-report-manager.md).</span><span class="sxs-lookup"><span data-stu-id="d0639-144">For more information, see [Cache Refresh Options &#40;Report Manager&#41;](../cache-refresh-options-report-manager.md).</span></span>  
  
## <a name="conditions-that-cause-cache-expiration"></a><span data-ttu-id="d0639-145">Condizioni che determinano la scadenza della cache</span><span class="sxs-lookup"><span data-stu-id="d0639-145">Conditions that Cause Cache Expiration</span></span>  
 <span data-ttu-id="d0639-146">Le condizioni seguenti possono provocare l'invalidità di una cache di un set di dati condiviso.</span><span class="sxs-lookup"><span data-stu-id="d0639-146">The following conditions can cause a shared dataset cache to become not valid.</span></span>  
  
-   <span data-ttu-id="d0639-147">Scadenza di una condizione della pianificazione</span><span class="sxs-lookup"><span data-stu-id="d0639-147">A schedule condition expires.</span></span> <span data-ttu-id="d0639-148">per timeout o scadenza della cache.</span><span class="sxs-lookup"><span data-stu-id="d0639-148">The cache times out or the expiration time occurs.</span></span>  
  
-   <span data-ttu-id="d0639-149">Eliminazione di una pianificazione condivisa.</span><span class="sxs-lookup"><span data-stu-id="d0639-149">A shared schedule is deleted.</span></span>  
  
-   <span data-ttu-id="d0639-150">Applicazione di modifiche a una pianificazione condivisa.</span><span class="sxs-lookup"><span data-stu-id="d0639-150">Changes to a shared schedule.</span></span> <span data-ttu-id="d0639-151">L'eventuale sospensione di pianificazioni condivise può influire sulla scadenza di una cache.</span><span class="sxs-lookup"><span data-stu-id="d0639-151">Shared schedules can be paused, which also affects when a cache expires.</span></span>  
  
-   <span data-ttu-id="d0639-152">Esecuzione di modifiche alla definizione della query per il set di dati condiviso.</span><span class="sxs-lookup"><span data-stu-id="d0639-152">The query definition for the shared dataset changes.</span></span>  
  
-   <span data-ttu-id="d0639-153">Modifica delle credenziali per l'origine dati condivisa da cui dipende il set di dati condiviso.</span><span class="sxs-lookup"><span data-stu-id="d0639-153">The credentials for the shared data source that the shared dataset depends on change.</span></span>  
  
-   <span data-ttu-id="d0639-154">Modifica delle opzioni della cache per il set di dati condiviso.</span><span class="sxs-lookup"><span data-stu-id="d0639-154">The cache options for the shared dataset change.</span></span>  
  
-   <span data-ttu-id="d0639-155">Modifica dei valori predefiniti per i parametri di sola lettura per il set di dati condiviso.</span><span class="sxs-lookup"><span data-stu-id="d0639-155">The default values for read-only parameters for the shared dataset change.</span></span>  
  
-   <span data-ttu-id="d0639-156">Modifica dei filtri che appartengono alla definizione del set di dati condiviso.</span><span class="sxs-lookup"><span data-stu-id="d0639-156">The filters that are part of the shared dataset definition change.</span></span>  
  
-   <span data-ttu-id="d0639-157">Eliminazione del set di dati condiviso dal server di report.</span><span class="sxs-lookup"><span data-stu-id="d0639-157">The shared dataset is deleted from the report server.</span></span> <span data-ttu-id="d0639-158">L'eliminazione di un set di dati condiviso comporta l'eliminazione delle copie memorizzate nella cache associate e dei piani di aggiornamento della cache stessa.</span><span class="sxs-lookup"><span data-stu-id="d0639-158">When a shared dataset is deleted, associated cached copies and cache refresh plans are also deleted.</span></span>  
  
 <span data-ttu-id="d0639-159">Gli aggiornamenti dei piani di aggiornamento della cache per i set di dati condivisi non influiscono sui report già in elaborazione,</span><span class="sxs-lookup"><span data-stu-id="d0639-159">Updates to cache refresh plans for shared datasets do not affect reports that are already being processed.</span></span> <span data-ttu-id="d0639-160">ma influiscono solo su avvii futuri di report che fanno riferimento al set di dati condiviso.</span><span class="sxs-lookup"><span data-stu-id="d0639-160">Updating a cache refresh plan affects only future launches of reports that reference the shared dataset.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0639-161">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d0639-161">See Also</span></span>  
 [<span data-ttu-id="d0639-162">Gestire set di dati condivisi</span><span class="sxs-lookup"><span data-stu-id="d0639-162">Manage Shared Datasets</span></span>](../report-data/manage-shared-datasets.md)  
  
  
