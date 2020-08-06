---
title: MSSQLSERVER_8645 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8645 (Database Engine error)
ms.assetid: 63d6d6d7-3850-4061-8e96-b1fa665e3180
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 7be9774452e2008c34ecb52d228a0123992c5368
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635065"
---
# <a name="mssqlserver_8645"></a><span data-ttu-id="9ba01-102">MSSQLSERVER_8645</span><span class="sxs-lookup"><span data-stu-id="9ba01-102">MSSQLSERVER_8645</span></span>
    
## <a name="details"></a><span data-ttu-id="9ba01-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="9ba01-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9ba01-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="9ba01-104">Product Name</span></span>|<span data-ttu-id="9ba01-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="9ba01-105">SQL Server</span></span>|  
|<span data-ttu-id="9ba01-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="9ba01-106">Event ID</span></span>|<span data-ttu-id="9ba01-107">8645</span><span class="sxs-lookup"><span data-stu-id="9ba01-107">8645</span></span>|  
|<span data-ttu-id="9ba01-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="9ba01-108">Event Source</span></span>|<span data-ttu-id="9ba01-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="9ba01-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="9ba01-110">Componente</span><span class="sxs-lookup"><span data-stu-id="9ba01-110">Component</span></span>|<span data-ttu-id="9ba01-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="9ba01-111">SQLEngine</span></span>|  
|<span data-ttu-id="9ba01-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="9ba01-112">Symbolic Name</span></span>|<span data-ttu-id="9ba01-113">MEMTIMEDOUT_ERR</span><span class="sxs-lookup"><span data-stu-id="9ba01-113">MEMTIMEDOUT_ERR</span></span>|  
|<span data-ttu-id="9ba01-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="9ba01-114">Message Text</span></span>|<span data-ttu-id="9ba01-115">Timeout durante l'attesa di risorse di memoria per l'esecuzione della query.</span><span class="sxs-lookup"><span data-stu-id="9ba01-115">A time out occurred while waiting for memory resources to execute the query.</span></span> <span data-ttu-id="9ba01-116">Eseguire nuovamente la query.</span><span class="sxs-lookup"><span data-stu-id="9ba01-116">Rerun the query.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="9ba01-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="9ba01-117">Explanation</span></span>  
 <span data-ttu-id="9ba01-118">Timeout durante l'attesa di risorse di memoria per l'esecuzione della query nel pool di risorse 'predefinito'.</span><span class="sxs-lookup"><span data-stu-id="9ba01-118">A timeout occurred while waiting for memory resources to execute the query in the resource pool 'default'.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9ba01-119">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="9ba01-119">User Action</span></span>  
 <span data-ttu-id="9ba01-120">Se non si utilizza Resource Governor, si consiglia di verificare lo stato generale del server e di caricare o controllare il pool di risorse o le impostazioni del gruppo del carico di lavoro.</span><span class="sxs-lookup"><span data-stu-id="9ba01-120">If you are not using Resource Governor, we recommend that you verify the overall server state and load, or check the resource pool or workload group settings.</span></span>  
  
 <span data-ttu-id="9ba01-121">Nell'elenco seguente viene illustrata la procedura generale per la risoluzione degli errori di memoria:</span><span class="sxs-lookup"><span data-stu-id="9ba01-121">The following list outlines general steps that will help in troubleshooting memory errors:</span></span>  
  
1.  <span data-ttu-id="9ba01-122">Verificare se altre applicazioni o servizi utilizzano la memoria nel server specificato.</span><span class="sxs-lookup"><span data-stu-id="9ba01-122">Verify whether other applications or services are consuming memory on this server.</span></span> <span data-ttu-id="9ba01-123">Riconfigurare le applicazioni o i servizi meno critici per utilizzare una quantità di memoria inferiore.</span><span class="sxs-lookup"><span data-stu-id="9ba01-123">Reconfigure less critical applications or services to consume less memory.</span></span>  
  
2.  <span data-ttu-id="9ba01-124">Iniziare a raccogliere i dati dei contatori di Performance Monitor per **SQL Server: Gestione buffer**, **SQL Server: Memory Manager**.</span><span class="sxs-lookup"><span data-stu-id="9ba01-124">Start collecting performance monitor counters for **SQL Server: Buffer Manager**, **SQL Server: Memory Manager**.</span></span>  
  
3.  <span data-ttu-id="9ba01-125">Verificare i seguenti parametri di configurazione della memoria di SQL Server:</span><span class="sxs-lookup"><span data-stu-id="9ba01-125">Check the following SQL Server memory configuration parameters:</span></span>  
  
    -   <span data-ttu-id="9ba01-126">**max server memory**</span><span class="sxs-lookup"><span data-stu-id="9ba01-126">**max server memory**</span></span>  
  
    -   <span data-ttu-id="9ba01-127">**min server memory**</span><span class="sxs-lookup"><span data-stu-id="9ba01-127">**min server memory**</span></span>  
  
    -   <span data-ttu-id="9ba01-128">**min memory per query**</span><span class="sxs-lookup"><span data-stu-id="9ba01-128">**min memory per query**</span></span>  
  
     <span data-ttu-id="9ba01-129">Valutare eventuali impostazioni non comuni</span><span class="sxs-lookup"><span data-stu-id="9ba01-129">Notice unusual settings.</span></span> <span data-ttu-id="9ba01-130">e, se necessario, correggerle.</span><span class="sxs-lookup"><span data-stu-id="9ba01-130">Correct them as necessary.</span></span> <span data-ttu-id="9ba01-131">Considerare i requisiti di memoria aggiuntivi per [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9ba01-131">Account for increased memory requirements for [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="9ba01-132">Le impostazioni predefinite sono elencate nell'argomento "Impostazione delle opzioni di configurazione del server" nella documentazione online di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="9ba01-132">Default settings are listed in "Setting Server Configuration Options" in SQL Server Books Online.</span></span>  
  
4.  <span data-ttu-id="9ba01-133">Osservare l'output di DBCC MEMORYSTATUS e il modo in cui viene modificato quando vengono visualizzati questi messaggi di errore.</span><span class="sxs-lookup"><span data-stu-id="9ba01-133">Observe DBCC MEMORYSTATUS output and the way it changes when you see these error messages.</span></span>  
  
5.  <span data-ttu-id="9ba01-134">Verificare il carico di lavoro (ad esempio, numero di sessioni simultanee, query attualmente in esecuzione).</span><span class="sxs-lookup"><span data-stu-id="9ba01-134">Check the workload (for example, number of concurrent sessions, currently executing queries).</span></span>  
  
 <span data-ttu-id="9ba01-135">Per aumentare la quantità di memoria disponibile per [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9ba01-135">The following actions may make more memory available to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="9ba01-136">Se le risorse vengono utilizzate da altre applicazioni oltre a SQL Server, provare a interromperne l'esecuzione o a eseguirle in un server distinto.</span><span class="sxs-lookup"><span data-stu-id="9ba01-136">If applications besides SQL Server are consuming resources, try stopping running these applications or consider running them on a separate server.</span></span> <span data-ttu-id="9ba01-137">In questo modo sarà possibile eliminare le richieste di memoria esterne.</span><span class="sxs-lookup"><span data-stu-id="9ba01-137">This will remove external memory pressure.</span></span>  
  
-   <span data-ttu-id="9ba01-138">Se è stata configurata l'opzione **max server memory,** , aumentarne il valore impostato.</span><span class="sxs-lookup"><span data-stu-id="9ba01-138">If you have configured **max server memory,** increase its setting.</span></span>  
  
 <span data-ttu-id="9ba01-139">Eseguire i comandi DBCC seguenti per liberare diverse cache in memoria di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="9ba01-139">Run the following DBCC commands to free several SQL Server memory caches.</span></span>  
  
-   <span data-ttu-id="9ba01-140">DBCC FREESYSTEMCACHE</span><span class="sxs-lookup"><span data-stu-id="9ba01-140">DBCC FREESYSTEMCACHE</span></span>  
  
-   <span data-ttu-id="9ba01-141">DBCC FREESESSIONCACHE</span><span class="sxs-lookup"><span data-stu-id="9ba01-141">DBCC FREESESSIONCACHE</span></span>  
  
-   <span data-ttu-id="9ba01-142">DBCC FREEPROCCACHE</span><span class="sxs-lookup"><span data-stu-id="9ba01-142">DBCC FREEPROCCACHE</span></span>  
  
 <span data-ttu-id="9ba01-143">Se il problema persiste, sarà necessario analizzarlo in modo più dettagliato e cercare di ridurre il carico di lavoro.</span><span class="sxs-lookup"><span data-stu-id="9ba01-143">If the problem continues, you will need to investigate further and possibly reduce workload.</span></span>  
  
  
