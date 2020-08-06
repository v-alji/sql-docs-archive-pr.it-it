---
title: MSSQLSERVER_8651 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8651 (Database Engine error)
ms.assetid: 4cc3498d-5449-4c4e-b1f9-3271831c725a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 43a385350a05edee3759ab83d318e365f5b4f3e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714376"
---
# <a name="mssqlserver_8651"></a><span data-ttu-id="bbde6-102">MSSQLSERVER_8651</span><span class="sxs-lookup"><span data-stu-id="bbde6-102">MSSQLSERVER_8651</span></span>
    
## <a name="details"></a><span data-ttu-id="bbde6-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="bbde6-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bbde6-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="bbde6-104">Product Name</span></span>|<span data-ttu-id="bbde6-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="bbde6-105">SQL Server</span></span>|  
|<span data-ttu-id="bbde6-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="bbde6-106">Event ID</span></span>|<span data-ttu-id="bbde6-107">8651</span><span class="sxs-lookup"><span data-stu-id="bbde6-107">8651</span></span>|  
|<span data-ttu-id="bbde6-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="bbde6-108">Event Source</span></span>|<span data-ttu-id="bbde6-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="bbde6-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="bbde6-110">Componente</span><span class="sxs-lookup"><span data-stu-id="bbde6-110">Component</span></span>|<span data-ttu-id="bbde6-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="bbde6-111">SQLEngine</span></span>|  
|<span data-ttu-id="bbde6-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="bbde6-112">Symbolic Name</span></span>|<span data-ttu-id="bbde6-113">MEMGRANT_ERR</span><span class="sxs-lookup"><span data-stu-id="bbde6-113">MEMGRANT_ERR</span></span>|  
|<span data-ttu-id="bbde6-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="bbde6-114">Message Text</span></span>|<span data-ttu-id="bbde6-115">Impossibile eseguire l'operazione richiesta perché non è disponibile la quantità di memoria minima per la query.</span><span class="sxs-lookup"><span data-stu-id="bbde6-115">Could not perform the requested operation because the minimum query memory is not available.</span></span> <span data-ttu-id="bbde6-116">Diminuire il valore dell'opzione di configurazione del server 'min memory per query'.</span><span class="sxs-lookup"><span data-stu-id="bbde6-116">Decrease the configured value for the 'min memory per query' server configuration option.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="bbde6-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="bbde6-117">Explanation</span></span>  
 <span data-ttu-id="bbde6-118">Altri processi stanno utilizzando la memoria del server, ovvero stanno inviando un numero eccessivo di richieste di memoria al server.</span><span class="sxs-lookup"><span data-stu-id="bbde6-118">Other processes are consuming server memory (exerting memory pressure in the server).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="bbde6-119">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="bbde6-119">User Action</span></span>  
 <span data-ttu-id="bbde6-120">Diminuire il valore dell'opzione di configurazione del server 'min memory per query' oppure ridurre il carico di query inviate al server.</span><span class="sxs-lookup"><span data-stu-id="bbde6-120">Either decrease the configured value for the min memory per query' server configuration option or reduce the query load to the server.</span></span>  
  
 <span data-ttu-id="bbde6-121">Nell'elenco seguente viene illustrata la procedura generale per la risoluzione degli errori di memoria:</span><span class="sxs-lookup"><span data-stu-id="bbde6-121">The following list outlines general steps that will help in troubleshooting memory errors:</span></span>  
  
1.  <span data-ttu-id="bbde6-122">Verificare se altre applicazioni o servizi utilizzano la memoria nel server specificato.</span><span class="sxs-lookup"><span data-stu-id="bbde6-122">Verify whether other applications or services are consuming memory on this server.</span></span> <span data-ttu-id="bbde6-123">Riconfigurare le applicazioni o i servizi meno critici per utilizzare una quantità di memoria inferiore.</span><span class="sxs-lookup"><span data-stu-id="bbde6-123">Reconfigure less critical applications or services to consume less memory.</span></span>  
  
2.  <span data-ttu-id="bbde6-124">Iniziare a raccogliere i dati dei contatori di Performance Monitor per **SQL Server: Gestione buffer**, **SQL Server: Memory Manager**.</span><span class="sxs-lookup"><span data-stu-id="bbde6-124">Start collecting performance monitor counters for **SQL Server: Buffer Manager**, **SQL Server: Memory Manager**.</span></span>  
  
3.  <span data-ttu-id="bbde6-125">Verificare i seguenti parametri di configurazione della memoria di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="bbde6-125">Check the following [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] memory configuration parameters:</span></span>  
  
    -   <span data-ttu-id="bbde6-126">**max server memory**</span><span class="sxs-lookup"><span data-stu-id="bbde6-126">**max server memory**</span></span>  
  
    -   <span data-ttu-id="bbde6-127">**min server memory**</span><span class="sxs-lookup"><span data-stu-id="bbde6-127">**min server memory**</span></span>  
  
    -   <span data-ttu-id="bbde6-128">**min memory per query**</span><span class="sxs-lookup"><span data-stu-id="bbde6-128">**min memory per query**</span></span>  
  
     <span data-ttu-id="bbde6-129">Valutare eventuali impostazioni non comuni</span><span class="sxs-lookup"><span data-stu-id="bbde6-129">Notice unusual settings.</span></span> <span data-ttu-id="bbde6-130">e, se necessario, correggerle.</span><span class="sxs-lookup"><span data-stu-id="bbde6-130">Correct them as necessary.</span></span> <span data-ttu-id="bbde6-131">Le impostazioni predefinite sono elencate nell'argomento "Impostazione delle opzioni di configurazione del server" nella documentazione online di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="bbde6-131">Default settings are listed in "Setting Server Configuration Options" in SQL Server Books Online.</span></span>  
  
4.  <span data-ttu-id="bbde6-132">Verificare il carico di lavoro (ad esempio, numero di sessioni simultanee, query attualmente in esecuzione).</span><span class="sxs-lookup"><span data-stu-id="bbde6-132">Check the workload (for example, number of concurrent sessions, currently executing queries).</span></span>  
  
 <span data-ttu-id="bbde6-133">Per aumentare la quantità di memoria disponibile per [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="bbde6-133">The following actions may make more memory available to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="bbde6-134">Se le risorse vengono utilizzate da altre applicazioni oltre a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], provare ad arrestarne l'esecuzione oppure a eseguirle in un server distinto.</span><span class="sxs-lookup"><span data-stu-id="bbde6-134">If applications besides [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are consuming resources, try stopping running these applications or consider running them on a separate server.</span></span> <span data-ttu-id="bbde6-135">In questo modo sarà possibile eliminare le richieste di memoria esterne.</span><span class="sxs-lookup"><span data-stu-id="bbde6-135">This will remove external memory pressure.</span></span>  
  
-   <span data-ttu-id="bbde6-136">Se è stata configurata l'opzione **max server memory,** , aumentarne il valore impostato.</span><span class="sxs-lookup"><span data-stu-id="bbde6-136">If you have configured **max server memory,** increase its setting.</span></span>  
  
 <span data-ttu-id="bbde6-137">Eseguire i comandi DBCC seguenti per liberare diverse cache in memoria di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bbde6-137">Run the following DBCC commands to free several [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] memory caches.</span></span>  
  
-   <span data-ttu-id="bbde6-138">DBCC FREESYSTEMCACHE</span><span class="sxs-lookup"><span data-stu-id="bbde6-138">DBCC FREESYSTEMCACHE</span></span>  
  
-   <span data-ttu-id="bbde6-139">DBCC FREESESSIONCACHE</span><span class="sxs-lookup"><span data-stu-id="bbde6-139">DBCC FREESESSIONCACHE</span></span>  
  
-   <span data-ttu-id="bbde6-140">DBCC FREEPROCCACHE</span><span class="sxs-lookup"><span data-stu-id="bbde6-140">DBCC FREEPROCCACHE</span></span>  
  
 <span data-ttu-id="bbde6-141">Se il problema persiste, sarà necessario analizzarlo in modo più dettagliato e cercare di ridurre il carico di lavoro.</span><span class="sxs-lookup"><span data-stu-id="bbde6-141">If the problem continues, you will need to investigate further and possibly reduce workload.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbde6-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bbde6-142">See Also</span></span>  
 <span data-ttu-id="bbde6-143">[DBCC FREESYSTEMCACHE &#40;&#41;Transact-SQL](/sql/t-sql/database-console-commands/dbcc-freesystemcache-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="bbde6-143">[DBCC FREESYSTEMCACHE &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-freesystemcache-transact-sql) </span></span>  
 <span data-ttu-id="bbde6-144">[DBCC FREESESSIONCACHE &#40;&#41;Transact-SQL](/sql/t-sql/database-console-commands/dbcc-freesessioncache-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="bbde6-144">[DBCC FREESESSIONCACHE &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-freesessioncache-transact-sql) </span></span>  
 <span data-ttu-id="bbde6-145">[DBCC FREEPROCCACHE &#40;&#41;Transact-SQL](/sql/t-sql/database-console-commands/dbcc-freeproccache-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="bbde6-145">[DBCC FREEPROCCACHE &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-freeproccache-transact-sql) </span></span>  
 <span data-ttu-id="bbde6-146">[Opzioni di configurazione del server &#40;SQL Server&#41;](../../database-engine/configure-windows/server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="bbde6-146">[Server Configuration Options &#40;SQL Server&#41;](../../database-engine/configure-windows/server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="bbde6-147">[Oggetto di Gestione buffer di SQL Server](../performance-monitor/sql-server-buffer-manager-object.md) </span><span class="sxs-lookup"><span data-stu-id="bbde6-147">[SQL Server, Buffer Manager Object](../performance-monitor/sql-server-buffer-manager-object.md) </span></span>  
 [<span data-ttu-id="bbde6-148">Oggetto Memory Manager di SQL Server</span><span class="sxs-lookup"><span data-stu-id="bbde6-148">SQL Server, Memory Manager Object</span></span>](../performance-monitor/sql-server-memory-manager-object.md)  
  
  
