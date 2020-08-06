---
title: MSSQL_REPL027183 | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_REPL027183 error
ms.assetid: 52c271ac-1a0e-43d5-85d4-35886d1efd32
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4484318cd6ec6ff4f0b201be69dc9b7544dd2c2f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725475"
---
# <a name="mssql_repl027183"></a><span data-ttu-id="98117-102">MSSQL_REPL027183</span><span class="sxs-lookup"><span data-stu-id="98117-102">MSSQL_REPL027183</span></span>
    
## <a name="message-details"></a><span data-ttu-id="98117-103">Dettagli messaggio</span><span class="sxs-lookup"><span data-stu-id="98117-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="98117-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="98117-104">Product Name</span></span>|<span data-ttu-id="98117-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="98117-105">SQL Server</span></span>|  
|<span data-ttu-id="98117-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="98117-106">Event ID</span></span>|<span data-ttu-id="98117-107">27183</span><span class="sxs-lookup"><span data-stu-id="98117-107">27183</span></span>|  
|<span data-ttu-id="98117-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="98117-108">Event Source</span></span>|<span data-ttu-id="98117-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="98117-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="98117-110">Componente</span><span class="sxs-lookup"><span data-stu-id="98117-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="98117-111">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="98117-111">Symbolic Name</span></span>||  
|<span data-ttu-id="98117-112">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="98117-112">Message Text</span></span>|<span data-ttu-id="98117-113">Impossibile enumerare le modifiche negli articoli con filtri di riga con parametri.</span><span class="sxs-lookup"><span data-stu-id="98117-113">The merge process failed to enumerate changes in articles with parameterized row filters.</span></span> <span data-ttu-id="98117-114">Se il problema persiste, aumentare il timeout per le query per questo processo, ridurre il periodo di memorizzazione per la pubblicazione e migliorare gli indici delle tabelle pubblicate.</span><span class="sxs-lookup"><span data-stu-id="98117-114">If this failure continues, increase the query timeout for this process, reduce the retention period for the publication, and improve indexes on published tables.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="98117-115">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="98117-115">Explanation</span></span>  
 <span data-ttu-id="98117-116">Questo errore viene generato se si verifica un timeout dell'agente di merge durante l'elaborazione delle modifiche in una pubblicazione filtrata.</span><span class="sxs-lookup"><span data-stu-id="98117-116">This error is raised if a Merge Agent timeout occurs while processing changes in a filtered publication.</span></span> <span data-ttu-id="98117-117">Il timeout potrebbe essere provocato da uno dei problemi seguenti:</span><span class="sxs-lookup"><span data-stu-id="98117-117">The timeout might be caused by one of the following issues:</span></span>  
  
-   <span data-ttu-id="98117-118">Mancato uso dell'ottimizzazione delle partizioni pre-calcolate.</span><span class="sxs-lookup"><span data-stu-id="98117-118">Not using the precomputed partitions optimization.</span></span>  
  
-   <span data-ttu-id="98117-119">Frammentazione dell'indice nelle colonne utilizzate per il filtraggio.</span><span class="sxs-lookup"><span data-stu-id="98117-119">Index fragmentation on columns used for filtering.</span></span>  
  
-   <span data-ttu-id="98117-120">Tabelle di metadati di tipo merge di grandi dimensioni, come **MSmerge_tombstone**, **MSmerge_contents**e **MSmerge_genhistory**.</span><span class="sxs-lookup"><span data-stu-id="98117-120">Large merge metadata tables, such as **MSmerge_tombstone**, **MSmerge_contents**, and **MSmerge_genhistory**.</span></span>  
  
-   <span data-ttu-id="98117-121">Tabelle filtrate non unite in join in una chiave univoca e filtri join che coinvolgono un gran numero di tabelle.</span><span class="sxs-lookup"><span data-stu-id="98117-121">Filtered tables that are not joined on a unique key and join filters that involve a large number of tables.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="98117-122">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="98117-122">User Action</span></span>  
 <span data-ttu-id="98117-123">Per risolvere il problema:</span><span class="sxs-lookup"><span data-stu-id="98117-123">To resolve the issue:</span></span>  
  
-   <span data-ttu-id="98117-124">Aumentare il valore del parametro **-QueryTimeOut** per l'agente di merge, in modo da continuare l'elaborazione mentre si risolve il problema sottostante che causa l'errore.</span><span class="sxs-lookup"><span data-stu-id="98117-124">Increase the value of the **-QueryTimeOut** parameter for the Merge Agent to allow processing to continue while you address the underlying issues causing the error.</span></span> <span data-ttu-id="98117-125">I parametri degli agenti possono essere specificati nei profili agente e dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="98117-125">Agent parameters can be specified in agent profiles and on the command line.</span></span> <span data-ttu-id="98117-126">Per altre informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="98117-126">For more information, see:</span></span>  
  
    -   [<span data-ttu-id="98117-127">Usare i profili agenti di replica</span><span class="sxs-lookup"><span data-stu-id="98117-127">Work with Replication Agent Profiles</span></span>](agents/replication-agent-profiles.md)  
  
    -   [<span data-ttu-id="98117-128">Visualizzare e modificare i parametri del prompt dei comandi dell'agente di replica &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="98117-128">View and Modify Replication Agent Command Prompt Parameters &#40;SQL Server Management Studio&#41;</span></span>](agents/view-and-modify-replication-agent-command-prompt-parameters.md)  
  
    -   <span data-ttu-id="98117-129">[Replication Agent Executables Concepts](concepts/replication-agent-executables-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="98117-129">[Replication Agent Executables Concepts](concepts/replication-agent-executables-concepts.md).</span></span>  
  
-   <span data-ttu-id="98117-130">Se possibile, utilizzare l'ottimizzazione delle partizioni pre-calcolate.</span><span class="sxs-lookup"><span data-stu-id="98117-130">Use the precomputed partitions optimization if possible.</span></span> <span data-ttu-id="98117-131">Questa ottimizzazione viene utilizzata per impostazione predefinita se vengono soddisfatti alcuni requisiti di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="98117-131">This optimization is used by default if a number of publication requirements are met.</span></span> <span data-ttu-id="98117-132">Per altre informazioni su questi requisiti, vedere [Ottimizzare le prestazioni dei filtri con parametri con le partizioni pre-calcolate](merge/parameterized-filters-optimize-for-precomputed-partitions.md).</span><span class="sxs-lookup"><span data-stu-id="98117-132">For more information about these requirements, see [Optimize Parameterized Filter Performance with Precomputed Partitions](merge/parameterized-filters-optimize-for-precomputed-partitions.md).</span></span> <span data-ttu-id="98117-133">Se la pubblicazione non soddisfa questi requisiti, è necessario prendere in considerazione l'eventualità di riprogettare la pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="98117-133">If the publication does not meet these requirements, consider redesigning the publication.</span></span>  
  
-   <span data-ttu-id="98117-134">Specificare la minima impostazione possibile per il periodo di memorizzazione della pubblicazione, poiché la replica non è in grado di eliminare i metadati dei database di pubblicazione e sottoscrizione prima della scadenza del periodo di memorizzazione.</span><span class="sxs-lookup"><span data-stu-id="98117-134">Specify the lowest setting possible for the publication retention period, because replication cannot clean up metadata in the publication and subscription databases until the retention period is reached.</span></span> <span data-ttu-id="98117-135">Per altre informazioni, vedere [Subscription Expiration and Deactivation](subscription-expiration-and-deactivation.md).</span><span class="sxs-lookup"><span data-stu-id="98117-135">For more information, see [Subscription Expiration and Deactivation](subscription-expiration-and-deactivation.md).</span></span>  
  
-   <span data-ttu-id="98117-136">Come parte della manutenzione per la replica di tipo merge, controllare occasionalmente l'aumento delle dimensioni delle tabelle di sistema associate alla replica di tipo merge: **MSmerge_contents**, **MSmerge_genhistory**e **MSmerge_tombstone**, **MSmerge_current_partition_mappings**e **MSmerge_past_partition_mappings**.</span><span class="sxs-lookup"><span data-stu-id="98117-136">As part of maintenance for merge replication, occasionally check the growth of the system tables associated with merge replication: **MSmerge_contents**, **MSmerge_genhistory**, and **MSmerge_tombstone**, **MSmerge_current_partition_mappings**, and **MSmerge_past_partition_mappings**.</span></span> <span data-ttu-id="98117-137">Reindicizzare periodicamente queste tabelle.</span><span class="sxs-lookup"><span data-stu-id="98117-137">Periodically re-index these tables.</span></span> <span data-ttu-id="98117-138">Per altre informazioni, vedere [Riorganizzare e ricompilare gli indici](../indexes/indexes.md).</span><span class="sxs-lookup"><span data-stu-id="98117-138">For more information, see [Reorganize and Rebuild Indexes](../indexes/indexes.md).</span></span>  
  
-   <span data-ttu-id="98117-139">Verificare che le colonne utilizzate per il filtraggio siano indicizzate correttamente e, se necessario, ricompilare tali indici.</span><span class="sxs-lookup"><span data-stu-id="98117-139">Ensure that columns used for filtering are properly indexed and rebuild such indexes if necessary.</span></span> <span data-ttu-id="98117-140">Per altre informazioni, vedere [Riorganizzare e ricompilare gli indici](../indexes/indexes.md).</span><span class="sxs-lookup"><span data-stu-id="98117-140">For more information, see [Reorganize and Rebuild Indexes](../indexes/indexes.md).</span></span>  
  
-   <span data-ttu-id="98117-141">Impostare la proprietà **join_unique_key** per i filtri di join basati su colonne univoche.</span><span class="sxs-lookup"><span data-stu-id="98117-141">Set the **join_unique_key** property for join filters that are based on unique columns.</span></span> <span data-ttu-id="98117-142">Per altre informazioni, vedere [Join Filters](merge/join-filters.md).</span><span class="sxs-lookup"><span data-stu-id="98117-142">For more information, see [Join Filters](merge/join-filters.md).</span></span>  
  
-   <span data-ttu-id="98117-143">Limitare il numero massimo di tabelle nella gerarchia dei filtri di join.</span><span class="sxs-lookup"><span data-stu-id="98117-143">Limit the number of tables in the join filter hierarchy.</span></span> <span data-ttu-id="98117-144">Se si generano filtri di join di cinque o più tabelle, considerare altre soluzioni: non filtrare tabelle piccole, non soggette a modifica o tabelle che fungono principalmente da tabelle di ricerca.</span><span class="sxs-lookup"><span data-stu-id="98117-144">If you are generating join filters of five or more tables, consider other solutions: do not filter tables that are small, not subject to change, or are primarily lookup tables.</span></span> <span data-ttu-id="98117-145">Utilizzare i filtri di join solo tra tabelle che devono essere partizionate tra diverse sottoscrizioni.</span><span class="sxs-lookup"><span data-stu-id="98117-145">Use join filters only between tables that must be partitioned among subscriptions.</span></span>  
  
-   <span data-ttu-id="98117-146">Apportare un numero minore di modifiche sulle tabelle filtrate tra le sincronizzazioni, oppure eseguire l'agente di merge con maggiore frequenza.</span><span class="sxs-lookup"><span data-stu-id="98117-146">Make a smaller number of changes on filtered tables between synchronizations, or run the Merge Agent more frequently.</span></span> <span data-ttu-id="98117-147">Per ulteriori informazioni sull'impostazione delle pianificazioni della sincronizzazione, vedere [Specify Synchronization Schedules](specify-synchronization-schedules.md).</span><span class="sxs-lookup"><span data-stu-id="98117-147">For more information about setting synchronization schedules, see [Specify Synchronization Schedules](specify-synchronization-schedules.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98117-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="98117-148">See Also</span></span>  
 [<span data-ttu-id="98117-149">Guida di riferimento a errori ed eventi &#40;replica&#41;</span><span class="sxs-lookup"><span data-stu-id="98117-149">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
