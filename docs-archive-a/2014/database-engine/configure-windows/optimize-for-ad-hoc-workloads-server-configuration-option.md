---
title: Opzione di configurazione del server optimize for ad hoc workloads | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- optimize for ad hoc workloads option
ms.assetid: 0972e028-3a8e-454b-a186-e814a1d431f2
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b217e48d6e4b0ffa0f687ff170f16d4d77ad17d8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713483"
---
# <a name="optimize-for-ad-hoc-workloads-server-configuration-option"></a><span data-ttu-id="b6fc7-102">ottimizzare per l'opzione di configurazione del server dei carichi di lavoro a hoc</span><span class="sxs-lookup"><span data-stu-id="b6fc7-102">optimize for ad hoc workloads Server Configuration Option</span></span>
  <span data-ttu-id="b6fc7-103">L'opzione **optimize for ad hoc workloads** consente di migliorare l'efficienza della cache dei piani per carichi di lavoro che contengono molti batch ad hoc a uso singolo.</span><span class="sxs-lookup"><span data-stu-id="b6fc7-103">The **optimize for ad hoc workloads** option is used to improve the efficiency of the plan cache for workloads that contain many single use ad hoc batches.</span></span> <span data-ttu-id="b6fc7-104">Quando questa opzione viene impostata su 1, alla prima compilazione di un batch il [!INCLUDE[ssDE](../../includes/ssde-md.md)] archivia un piccolo stub del piano compilato nella cache dei piani, anziché il piano compilato completo.</span><span class="sxs-lookup"><span data-stu-id="b6fc7-104">When this option is set to 1, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] stores a small compiled plan stub in the plan cache when a batch is compiled for the first time, instead of the full compiled plan.</span></span> <span data-ttu-id="b6fc7-105">In questo modo si riducono le richieste di memoria evitando che la cache dei piani si riempia con piani compilati che non vengono riutilizzati.</span><span class="sxs-lookup"><span data-stu-id="b6fc7-105">This helps to relieve memory pressure by not allowing the plan cache to become filled with compiled plans that are not reused.</span></span>  
  
 <span data-ttu-id="b6fc7-106">Poiché grazie allo stub del piano compilato il [!INCLUDE[ssDE](../../includes/ssde-md.md)] riconosce che il batch ad hoc è stato compilato in precedenza e ha archiviato solo uno stub del piano compilato, quando il batch viene nuovamente richiamato (compilato o eseguito), il [!INCLUDE[ssDE](../../includes/ssde-md.md)] compila il batch, rimuove lo stub del piano compilato dalla cache dei piani e aggiunge il piano compilato completo alla cache dei piani.</span><span class="sxs-lookup"><span data-stu-id="b6fc7-106">The compiled plan stub allows the [!INCLUDE[ssDE](../../includes/ssde-md.md)] to recognize that this ad hoc batch has been compiled before but has only stored a compiled plan stub, so when this batch is invoked (compiled or executed) again, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] compiles the batch, removes the compiled plan stub from the plan cache, and adds the full compiled plan to the plan cache.</span></span>  
  
 <span data-ttu-id="b6fc7-107">L'impostazione dell'opzione **optimize for ad hoc workloads** su 1 influisce solo sui nuovi piani, mentre non si applica ai piani già presenti nella cache dei piani.</span><span class="sxs-lookup"><span data-stu-id="b6fc7-107">Setting the **optimize for ad hoc workloads** to 1 affects only new plans; plans that are already in the plan cache are unaffected.</span></span>  
  
 <span data-ttu-id="b6fc7-108">Lo stub del piano compilato è uno dei cacheobjtype visualizzato nella vista del catalogo sys.dm_exec_cached_plans.</span><span class="sxs-lookup"><span data-stu-id="b6fc7-108">The compiled plan stub is one of the cacheobjtypes displayed by the sys.dm_exec_cached_plans catalog view.</span></span> <span data-ttu-id="b6fc7-109">Dispone di handle SQL e del piano univoci.</span><span class="sxs-lookup"><span data-stu-id="b6fc7-109">It has a unique sql handle and plan handle.</span></span> <span data-ttu-id="b6fc7-110">Lo stub del piano compilato non ha un piano di esecuzione associato e l'esecuzione di query per l'handle del piano non restituisce uno showplan XML.</span><span class="sxs-lookup"><span data-stu-id="b6fc7-110">The compiled plan stub does not have an execution plan associated with it and querying for the plan handle will not return an XML Showplan.</span></span>  
  
 <span data-ttu-id="b6fc7-111">Con il flag di traccia 8032 è possibile ripristinare i parametri dei limiti di cache all'impostazione RTM di [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] che consente, in generale, di aumentare le dimensioni delle cache.</span><span class="sxs-lookup"><span data-stu-id="b6fc7-111">Trace flag 8032 reverts the cache limit parameters to the [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] RTM setting which in general allows caches to be larger.</span></span> <span data-ttu-id="b6fc7-112">Usare questa impostazione quando le voci della cache riutilizzate di frequente non rientrano nella cache e quando non è possibile *ottimizzare per l'opzione di configurazione del server dei carichi di lavoro a hoc* per risolvere il problema della cache dei piani.</span><span class="sxs-lookup"><span data-stu-id="b6fc7-112">Use this setting when frequently reused cache entries do not fit into the cache and when the *optimize for ad hoc workloads Server Configuration Option* has failed to resolve the problem with plan cache.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="b6fc7-113">Il flag di traccia 8032 può provocare prestazioni ridotte se cache di grandi dimensioni rendono disponibile meno memoria per altri consumer di memoria, ad esempio il pool di buffer.</span><span class="sxs-lookup"><span data-stu-id="b6fc7-113">Trace flag 8032 can cause poor performance if large caches make less memory available for other memory consumers, such as the buffer pool.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6fc7-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b6fc7-114">See Also</span></span>  
 <span data-ttu-id="b6fc7-115">[sys.dm_exec_cached_plans &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-cached-plans-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b6fc7-115">[sys.dm_exec_cached_plans &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-cached-plans-transact-sql) </span></span>  
 [<span data-ttu-id="b6fc7-116">Opzioni di configurazione del server &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b6fc7-116">Server Configuration Options &#40;SQL Server&#41;</span></span>](server-configuration-options-sql-server.md)  
  
  
