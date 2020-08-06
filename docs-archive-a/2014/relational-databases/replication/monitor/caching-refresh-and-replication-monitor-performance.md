---
title: Memorizzazione nella cache, aggiornamento e prestazioni di Monitoraggio replica | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- monitoring performance [SQL Server replication], Replication Monitor
- cache [SQL Server], replication
- Replication Monitor, caching
- refreshing data
- Replication Monitor, refreshing
ms.assetid: a2d8b666-ed41-4f86-b2b8-c8e118416ab7
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b04a91e971e65d19c66cc36f142d8c4764b1b05a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626644"
---
# <a name="caching-refresh-and-replication-monitor-performance"></a><span data-ttu-id="cafd6-102">Memorizzazione nella cache, aggiornamento e prestazioni di Monitoraggio replica</span><span class="sxs-lookup"><span data-stu-id="cafd6-102">Caching, Refresh, and Replication Monitor Performance</span></span>
  <span data-ttu-id="cafd6-103"> Monitoraggio replica di [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] è progettato per monitorare in modo efficiente un numero elevato di computer all'interno di un sistema di produzione.</span><span class="sxs-lookup"><span data-stu-id="cafd6-103">[!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Replication Monitor is designed to efficiently monitor a large number of computers in a production system.</span></span> <span data-ttu-id="cafd6-104">Le query utilizzate in Monitoraggio replica per eseguire calcoli e raccogliere dati vengono memorizzate nella cache e aggiornate con frequenza periodica.</span><span class="sxs-lookup"><span data-stu-id="cafd6-104">The queries that Replication Monitor uses to perform calculations and gather data are cached and refreshed on a periodic basis.</span></span> <span data-ttu-id="cafd6-105">La memorizzazione nella cache riduce il numero di query e di calcoli necessari durante la visualizzazione di pagine diverse in Monitoraggio replica e consente di monitorare più utenti in modo efficiente.</span><span class="sxs-lookup"><span data-stu-id="cafd6-105">Caching reduces the number of queries and calculations required as you view different pages in Replication Monitor and allows monitoring to scale well for multiple users.</span></span>  
  
 <span data-ttu-id="cafd6-106">L'aggiornamento della cache è gestito da un processo di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent denominato **Aggiornamento monitoraggio replica per distribuzione**.</span><span class="sxs-lookup"><span data-stu-id="cafd6-106">Cache refresh is handled by a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent job, the **Replication monitoring refresher for distribution**.</span></span> <span data-ttu-id="cafd6-107">Il processo è impostato per l'esecuzione continua, ma la pianificazione dell'aggiornamento della cache è basata sull'attesa di una certa quantità di tempo dall'aggiornamento precedente:</span><span class="sxs-lookup"><span data-stu-id="cafd6-107">The job runs continuously, but the cache refresh schedule is based on waiting a certain amount time after the previous refresh:</span></span>  
  
-   <span data-ttu-id="cafd6-108">Se dopo l'ultima creazione della cache la cronologia dell'agente ha subito modifiche, il tempo di attesa sarà il valore minimo tra 4 secondi e la quantità di tempo impiegata per creare la cache precedente.</span><span class="sxs-lookup"><span data-stu-id="cafd6-108">If there were agent history changes since the cache was last created, the wait time is the minimum of: 4 seconds; or the amount of time taken to create the previous cache.</span></span>  
  
-   <span data-ttu-id="cafd6-109">Se dopo l'ultima creazione della cache la cronologia dell'agente non ha subito modifiche (ma possono essersi verificate modifiche di altro tipo), il tempo di attesa sarà il valore massimo tra 30 secondi e la quantità di tempo impiegata per creare la cache precedente.</span><span class="sxs-lookup"><span data-stu-id="cafd6-109">If there were no agent history changes since the cache was last created (there could have been other changes), the wait time is the maximum of: 30 seconds; or the amount of time taken to create the previous cache.</span></span>  
  
## <a name="refreshing-the-replication-monitor-user-interface"></a><span data-ttu-id="cafd6-110">Aggiornamento dell'interfaccia utente di Monitoraggio replica</span><span class="sxs-lookup"><span data-stu-id="cafd6-110">Refreshing the Replication Monitor User Interface</span></span>  
 <span data-ttu-id="cafd6-111">L'interfaccia utente di Monitoraggio replica può essere aggiornata nei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="cafd6-111">The Replication Monitor user interface can be refreshed in the following ways:</span></span>  
  
-   <span data-ttu-id="cafd6-112">La finestra principale di Monitoraggio replica, comprese tutte le schede, viene aggiornata automaticamente ogni cinque secondi per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="cafd6-112">The main Replication Monitor window (including all tabs), automatically refreshes by default every five seconds.</span></span> <span data-ttu-id="cafd6-113">Gli aggiornamenti automatici non forzano un aggiornamento della cache. Nell'interfaccia utente viene visualizzata la versione più recente dei dati della cache.</span><span class="sxs-lookup"><span data-stu-id="cafd6-113">Automatic refreshes do not force a refresh of the cache; the user interface displays the most recent version of the data from the cache.</span></span> <span data-ttu-id="cafd6-114">È possibile personalizzare la frequenza di aggiornamento utilizzata per tutte le finestre associate a un server di pubblicazione modificando le impostazioni di quest'ultimo.</span><span class="sxs-lookup"><span data-stu-id="cafd6-114">You can customize the refresh rate used for all windows associated with a Publisher by editing the Publisher settings.</span></span> <span data-ttu-id="cafd6-115">È inoltre possibile disabilitare gli aggiornamenti automatici per un server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="cafd6-115">You can also disable automatic refreshes for a Publisher.</span></span>  
  
-   <span data-ttu-id="cafd6-116">Le finestre dei dettagli che vengono avviate da Monitoraggio replica non vengono aggiornate automaticamente per impostazione predefinita, ad eccezione delle finestre relative alle sottoscrizioni di tipo merge di cui viene eseguita la sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="cafd6-116">The detail windows that are launched from Replication Monitor are not automatically refreshed by default, with the exception of windows related to merge subscriptions that are synchronizing.</span></span> <span data-ttu-id="cafd6-117">Se si specifica che le finestre dei dettagli devono essere aggiornate automaticamente, l'aggiornamento seguirà la stessa pianificazione della finestra principale di Monitoraggio replica.</span><span class="sxs-lookup"><span data-stu-id="cafd6-117">If you specify that detail windows should automatically refresh, they refresh on the same schedule as the main Replication Monitor window.</span></span>  
  
-   <span data-ttu-id="cafd6-118">Tutte le finestre possono essere aggiornate manualmente premendo F5 o facendo clic con il pulsante destro del mouse su un nodo dell'albero di Monitoraggio replica e quindi scegliendo **Aggiorna**.</span><span class="sxs-lookup"><span data-stu-id="cafd6-118">All windows can be manually refreshed by pressing F5 or by right-clicking a node in the Replication Monitor tree and clicking **Refresh**.</span></span> <span data-ttu-id="cafd6-119">Gli aggiornamenti manuali forzano un aggiornamento della cache.</span><span class="sxs-lookup"><span data-stu-id="cafd6-119">Manual refreshes force a refresh of the cache.</span></span>  
  
 <span data-ttu-id="cafd6-120">Per altre informazioni, vedere [Aggiornare i dati in Monitoraggio replica](refresh-data-in-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="cafd6-120">For more information, see [Refresh Data in Replication Monitor](refresh-data-in-replication-monitor.md).</span></span>  
  
## <a name="performance-considerations"></a><span data-ttu-id="cafd6-121">Considerazioni sulle prestazioni</span><span class="sxs-lookup"><span data-stu-id="cafd6-121">Performance Considerations</span></span>  
 <span data-ttu-id="cafd6-122">Sebbene Monitoraggio replica sia progettato per un funzionamento efficiente, considerare gli aspetti seguenti:</span><span class="sxs-lookup"><span data-stu-id="cafd6-122">Although Replication Monitor is designed to run efficiently, be aware of the following:</span></span>  
  
-   <span data-ttu-id="cafd6-123">Se si dispone di una quantità elevata di pubblicazioni o sottoscrizioni, è consigliabile pianificare aggiornamenti automatici meno frequenti per l'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="cafd6-123">If you have a large number of publications or subscriptions, consider setting a less frequent automatic refresh schedule for the user interface.</span></span>  
  
-   <span data-ttu-id="cafd6-124">Evitare di eseguire simultaneamente più istanze di Monitoraggio replica.</span><span class="sxs-lookup"><span data-stu-id="cafd6-124">Avoid concurrently running multiple instances of Replication Monitor.</span></span>  
  
-   <span data-ttu-id="cafd6-125">Evitare di registrare una quantità elevata di server di distribuzione e di configurare Monitoraggio replica affinché si connetta automaticamente a tutti.</span><span class="sxs-lookup"><span data-stu-id="cafd6-125">Avoid registering a large number of Distributors and setting Replication Monitor to automatically connect to all of them.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cafd6-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cafd6-126">See Also</span></span>  
 <span data-ttu-id="cafd6-127">[Eseguire processi di manutenzione della replica &#40;SQL Server Management Studio&#41;](../../../ssms/sql-server-management-studio-ssms.md) </span><span class="sxs-lookup"><span data-stu-id="cafd6-127">[Run Replication Maintenance Jobs &#40;SQL Server Management Studio&#41;](../../../ssms/sql-server-management-studio-ssms.md) </span></span>  
 [<span data-ttu-id="cafd6-128">Monitoraggio della replica</span><span class="sxs-lookup"><span data-stu-id="cafd6-128">Monitoring Replication</span></span>](../monitoring-replication.md)  
  
  
