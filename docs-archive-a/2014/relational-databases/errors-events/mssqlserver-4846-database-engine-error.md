---
title: MSSQLSERVER_4846 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 4846 (Database Engine error)
ms.assetid: a455e809-1883-4c7d-b3e3-835ee5bfe258
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 923137645aae72476fb4b2ae33f0cbbf3e81c2a3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714383"
---
# <a name="mssqlserver_4846"></a><span data-ttu-id="d0738-102">MSSQLSERVER_4846</span><span class="sxs-lookup"><span data-stu-id="d0738-102">MSSQLSERVER_4846</span></span>
    
## <a name="details"></a><span data-ttu-id="d0738-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="d0738-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d0738-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="d0738-104">Product Name</span></span>|<span data-ttu-id="d0738-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="d0738-105">SQL Server</span></span>|  
|<span data-ttu-id="d0738-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="d0738-106">Event ID</span></span>|<span data-ttu-id="d0738-107">4846</span><span class="sxs-lookup"><span data-stu-id="d0738-107">4846</span></span>|  
|<span data-ttu-id="d0738-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="d0738-108">Event Source</span></span>|<span data-ttu-id="d0738-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="d0738-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="d0738-110">Componente</span><span class="sxs-lookup"><span data-stu-id="d0738-110">Component</span></span>|<span data-ttu-id="d0738-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="d0738-111">SQLEngine</span></span>|  
|<span data-ttu-id="d0738-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="d0738-112">Symbolic Name</span></span>|<span data-ttu-id="d0738-113">BULKPROV_MEMORY</span><span class="sxs-lookup"><span data-stu-id="d0738-113">BULKPROV_MEMORY</span></span>|  
|<span data-ttu-id="d0738-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="d0738-114">Message Text</span></span>|<span data-ttu-id="d0738-115">Il provider di dati bulk non è in grado di allocare memoria.</span><span class="sxs-lookup"><span data-stu-id="d0738-115">The bulk data provider failed to allocate memory.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d0738-116">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="d0738-116">Explanation</span></span>  
 <span data-ttu-id="d0738-117">L'allocazione di memoria ha avuto esito negativo.</span><span class="sxs-lookup"><span data-stu-id="d0738-117">Memory allocation failed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d0738-118">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="d0738-118">User Action</span></span>  
 <span data-ttu-id="d0738-119">Per risolvere gli errori di memoria, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="d0738-119">Follow these general steps to troubleshoot memory errors:</span></span>  
  
1.  <span data-ttu-id="d0738-120">Verificare se altre applicazioni o servizi utilizzano la memoria nel server specificato.</span><span class="sxs-lookup"><span data-stu-id="d0738-120">Verify whether other applications or services are consuming memory on this server.</span></span> <span data-ttu-id="d0738-121">Riconfigurare le applicazioni o i servizi meno critici per utilizzare una quantità di memoria inferiore.</span><span class="sxs-lookup"><span data-stu-id="d0738-121">Reconfigure less critical applications or services to consume less memory.</span></span>  
  
2.  <span data-ttu-id="d0738-122">Iniziare a raccogliere i dati dei contatori di Performance Monitor per **SQL Server: Gestione buffer**, **SQL Server: Memory Manager**.</span><span class="sxs-lookup"><span data-stu-id="d0738-122">Start collecting performance monitor counters for **SQL Server: Buffer Manager**, **SQL Server: Memory Manager**.</span></span>  
  
3.  <span data-ttu-id="d0738-123">Verificare i seguenti parametri di configurazione della memoria di SQL Server:</span><span class="sxs-lookup"><span data-stu-id="d0738-123">Check the following SQL Server memory configuration parameters:</span></span>  
  
    -   <span data-ttu-id="d0738-124">**max server memory**</span><span class="sxs-lookup"><span data-stu-id="d0738-124">**max server memory**</span></span>  
  
    -   <span data-ttu-id="d0738-125">**min server memory**</span><span class="sxs-lookup"><span data-stu-id="d0738-125">**min server memory**</span></span>  
  
    -   <span data-ttu-id="d0738-126">**min memory per query**</span><span class="sxs-lookup"><span data-stu-id="d0738-126">**min memory per query**</span></span>  
  
     <span data-ttu-id="d0738-127">Valutare eventuali impostazioni non comuni</span><span class="sxs-lookup"><span data-stu-id="d0738-127">Notice any unusual settings.</span></span> <span data-ttu-id="d0738-128">e, se necessario, correggerle.</span><span class="sxs-lookup"><span data-stu-id="d0738-128">Correct them as necessary.</span></span> <span data-ttu-id="d0738-129">Considerare i requisiti di memoria per [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d0738-129">Account for memory requirements for [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="d0738-130">Le impostazioni predefinite sono elencate nell'argomento "Impostazione delle opzioni di configurazione del server" nella documentazione online di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d0738-130">Default settings are listed in "Setting Server Configuration Options" in SQL Server Books Online.</span></span>  
  
4.  <span data-ttu-id="d0738-131">Osservare l'output di DBCC MEMORYSTATUS e il modo in cui viene modificato quando vengono visualizzati questi messaggi di errore.</span><span class="sxs-lookup"><span data-stu-id="d0738-131">Observe DBCC MEMORYSTATUS output and the way it changes when you see these error messages.</span></span>  
  
5.  <span data-ttu-id="d0738-132">Verificare il carico di lavoro (ad esempio, numero di sessioni simultanee, query attualmente in esecuzione).</span><span class="sxs-lookup"><span data-stu-id="d0738-132">Check the workload (for example, number of concurrent sessions, currently executing queries).</span></span>  
  
 <span data-ttu-id="d0738-133">Per aumentare la quantità di memoria disponibile per [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d0738-133">The following actions may make more memory available to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="d0738-134">Se le risorse vengono utilizzate da altre applicazioni oltre a SQL Server, provare a interromperne l'esecuzione o a eseguirle in un server distinto.</span><span class="sxs-lookup"><span data-stu-id="d0738-134">If applications besides SQL Server are consuming resources, try stopping running these applications or consider running them on a separate server.</span></span> <span data-ttu-id="d0738-135">In questo modo sarà possibile eliminare le richieste di memoria esterne.</span><span class="sxs-lookup"><span data-stu-id="d0738-135">This will remove external memory pressure.</span></span>  
  
-   <span data-ttu-id="d0738-136">Se è stata configurata l'opzione **max server memory,** , aumentarne il valore impostato.</span><span class="sxs-lookup"><span data-stu-id="d0738-136">If you have configured **max server memory,** increase its setting.</span></span>  
  
 <span data-ttu-id="d0738-137">Eseguire i comandi DBCC seguenti per liberare diverse cache in memoria di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d0738-137">Run the following DBCC commands to free several [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] memory caches.</span></span>  
  
-   <span data-ttu-id="d0738-138">DBCC FREESYSTEMCACHE</span><span class="sxs-lookup"><span data-stu-id="d0738-138">DBCC FREESYSTEMCACHE</span></span>  
  
-   <span data-ttu-id="d0738-139">DBCC FREESESSIONCACHE</span><span class="sxs-lookup"><span data-stu-id="d0738-139">DBCC FREESESSIONCACHE</span></span>  
  
-   <span data-ttu-id="d0738-140">DBCC FREEPROCCACHE</span><span class="sxs-lookup"><span data-stu-id="d0738-140">DBCC FREEPROCCACHE</span></span>  
  
 <span data-ttu-id="d0738-141">Se il problema persiste, sarà necessario analizzarlo in modo più dettagliato e cercare di ridurre il carico di lavoro.</span><span class="sxs-lookup"><span data-stu-id="d0738-141">If the problem continues, you will need to investigate further and possibly reduce workload.</span></span>  
  
  
