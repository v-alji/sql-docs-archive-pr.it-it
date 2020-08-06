---
title: MSSQLSERVER_701 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 701 (Database Engine error)
ms.assetid: 3b975000-63a1-43c2-a40f-89d0a8a36bef
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 542535223d3e394c72079092411add143de61545
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626788"
---
# <a name="mssqlserver_701"></a><span data-ttu-id="333d6-102">MSSQLSERVER_701</span><span class="sxs-lookup"><span data-stu-id="333d6-102">MSSQLSERVER_701</span></span>
    
## <a name="details"></a><span data-ttu-id="333d6-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="333d6-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="333d6-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="333d6-104">Product Name</span></span>|<span data-ttu-id="333d6-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="333d6-105">SQL Server</span></span>|  
|<span data-ttu-id="333d6-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="333d6-106">Event ID</span></span>|<span data-ttu-id="333d6-107">701</span><span class="sxs-lookup"><span data-stu-id="333d6-107">701</span></span>|  
|<span data-ttu-id="333d6-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="333d6-108">Event Source</span></span>|<span data-ttu-id="333d6-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="333d6-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="333d6-110">Componente</span><span class="sxs-lookup"><span data-stu-id="333d6-110">Component</span></span>|<span data-ttu-id="333d6-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="333d6-111">SQLEngine</span></span>|  
|<span data-ttu-id="333d6-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="333d6-112">Symbolic Name</span></span>|<span data-ttu-id="333d6-113">NOSYSMEM</span><span class="sxs-lookup"><span data-stu-id="333d6-113">NOSYSMEM</span></span>|  
|<span data-ttu-id="333d6-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="333d6-114">Message Text</span></span>|<span data-ttu-id="333d6-115">Memoria di sistema insufficiente per l'esecuzione della query.</span><span class="sxs-lookup"><span data-stu-id="333d6-115">There is insufficient system memory to run this query.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="333d6-116">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="333d6-116">Explanation</span></span>  
 <span data-ttu-id="333d6-117">Non è stato possibile allocare memoria sufficiente per eseguire la query in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="333d6-117">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has failed to allocate sufficient memory to run the query.</span></span> <span data-ttu-id="333d6-118">Ciò può essere causato da diversi motivi, tra cui le impostazioni del sistema operativo, la disponibilità di memoria fisica o i limiti di memoria nel carico di lavoro corrente.</span><span class="sxs-lookup"><span data-stu-id="333d6-118">This can be caused by a variety of reasons including operating system settings, physical memory availability, or memory limits on the current workload.</span></span> <span data-ttu-id="333d6-119">Nella maggior parte dei casi, la transazione non riuscita non è la causa dell'errore.</span><span class="sxs-lookup"><span data-stu-id="333d6-119">In most cases, the transaction that failed is not the cause of this error.</span></span>  
  
 <span data-ttu-id="333d6-120">Le query di diagnostica, ad esempio le istruzioni DBCC, possono avere esito negativo perché il server non dispone di memoria sufficiente.</span><span class="sxs-lookup"><span data-stu-id="333d6-120">Diagnostic queries, such as DBCC statements, may fail because server the does not have sufficient memory.</span></span>  
  
 <span data-ttu-id="333d6-121">Timeout durante l'attesa di risorse di memoria per l'esecuzione della query nel pool di risorse 'predefinito'.</span><span class="sxs-lookup"><span data-stu-id="333d6-121">A timeout occurred while waiting for memory resources to execute the query in the resource pool 'default'.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="333d6-122">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="333d6-122">User Action</span></span>  
 <span data-ttu-id="333d6-123">Se non si utilizza Resource Governor, si consiglia di verificare lo stato generale del server e di caricare o controllare il pool di risorse o le impostazioni del gruppo del carico di lavoro.</span><span class="sxs-lookup"><span data-stu-id="333d6-123">If you are not using Resource Governor, we recommend that you verify the overall server state and load, or check the resource pool or workload group settings.</span></span>  
  
 <span data-ttu-id="333d6-124">Nell'elenco seguente viene illustrata la procedura generale per la risoluzione degli errori di memoria:</span><span class="sxs-lookup"><span data-stu-id="333d6-124">The following list outlines general steps that will help in troubleshooting memory errors:</span></span>  
  
1.  <span data-ttu-id="333d6-125">Verificare se altre applicazioni o servizi utilizzano la memoria nel server specificato.</span><span class="sxs-lookup"><span data-stu-id="333d6-125">Verify whether other applications or services are consuming memory on this server.</span></span> <span data-ttu-id="333d6-126">Riconfigurare le applicazioni o i servizi meno critici per utilizzare una quantità di memoria inferiore.</span><span class="sxs-lookup"><span data-stu-id="333d6-126">Reconfigure less critical applications or services to consume less memory.</span></span>  
  
2.  <span data-ttu-id="333d6-127">Iniziare a raccogliere i dati dei contatori di Performance Monitor per [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **: Gestione buffer**, **SQL Server: Memory Manager**.</span><span class="sxs-lookup"><span data-stu-id="333d6-127">Start collecting performance monitor counters for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]**: Buffer Manager**, **SQL Server: Memory Manager**.</span></span>  
  
3.  <span data-ttu-id="333d6-128">Verificare i seguenti parametri di configurazione della memoria di SQL Server:</span><span class="sxs-lookup"><span data-stu-id="333d6-128">Check the following SQL Server memory configuration parameters:</span></span>  
  
    -   <span data-ttu-id="333d6-129">**max server memory**</span><span class="sxs-lookup"><span data-stu-id="333d6-129">**max server memory**</span></span>  
  
    -   <span data-ttu-id="333d6-130">**min server memory**</span><span class="sxs-lookup"><span data-stu-id="333d6-130">**min server memory**</span></span>  
  
    -   <span data-ttu-id="333d6-131">**min memory per query**</span><span class="sxs-lookup"><span data-stu-id="333d6-131">**min memory per query**</span></span>  
  
     <span data-ttu-id="333d6-132">Valutare eventuali impostazioni non comuni</span><span class="sxs-lookup"><span data-stu-id="333d6-132">Notice unusual settings.</span></span> <span data-ttu-id="333d6-133">e, se necessario, correggerle.</span><span class="sxs-lookup"><span data-stu-id="333d6-133">Correct them as necessary.</span></span> <span data-ttu-id="333d6-134">Considerare i requisiti di memoria aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="333d6-134">Account for increased memory requirements.</span></span> <span data-ttu-id="333d6-135">Le impostazioni predefinite sono elencate nell'argomento "Impostazione delle opzioni di configurazione del server" nella documentazione online di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="333d6-135">Default settings are listed in "Setting Server Configuration Options" in SQL Server Books Online.</span></span>  
  
4.  <span data-ttu-id="333d6-136">Osservare l'output di DBCC MEMORYSTATUS e il modo in cui viene modificato quando vengono visualizzati questi messaggi di errore.</span><span class="sxs-lookup"><span data-stu-id="333d6-136">Observe DBCC MEMORYSTATUS output and the way it changes when you see these error messages.</span></span>  
  
5.  <span data-ttu-id="333d6-137">Verificare il carico di lavoro (ad esempio, numero di sessioni simultanee, query attualmente in esecuzione).</span><span class="sxs-lookup"><span data-stu-id="333d6-137">Check the workload (for example, number of concurrent sessions, currently executing queries).</span></span>  
  
 <span data-ttu-id="333d6-138">Per aumentare la quantità di memoria disponibile per [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="333d6-138">The following actions may make more memory available to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="333d6-139">Se le risorse vengono utilizzate da altre applicazioni oltre a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], provare ad arrestarne l'esecuzione oppure a eseguirle in un server distinto.</span><span class="sxs-lookup"><span data-stu-id="333d6-139">If applications besides [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are consuming resources, try stopping running these applications or consider running them on a separate server.</span></span> <span data-ttu-id="333d6-140">In questo modo sarà possibile eliminare le richieste di memoria esterne.</span><span class="sxs-lookup"><span data-stu-id="333d6-140">This will remove external memory pressure.</span></span>  
  
-   <span data-ttu-id="333d6-141">Se è stata configurata l'opzione **max server memory,** , aumentarne il valore impostato.</span><span class="sxs-lookup"><span data-stu-id="333d6-141">If you have configured **max server memory,** increase its setting.</span></span>  
  
 <span data-ttu-id="333d6-142">Eseguire i comandi DBCC seguenti per liberare diverse cache in memoria di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="333d6-142">Run the following DBCC commands to free several [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] memory caches.</span></span>  
  
-   <span data-ttu-id="333d6-143">DBCC FREESYSTEMCACHE</span><span class="sxs-lookup"><span data-stu-id="333d6-143">DBCC FREESYSTEMCACHE</span></span>  
  
-   <span data-ttu-id="333d6-144">DBCC FREESESSIONCACHE</span><span class="sxs-lookup"><span data-stu-id="333d6-144">DBCC FREESESSIONCACHE</span></span>  
  
-   <span data-ttu-id="333d6-145">DBCC FREEPROCCACHE</span><span class="sxs-lookup"><span data-stu-id="333d6-145">DBCC FREEPROCCACHE</span></span>  
  
 <span data-ttu-id="333d6-146">Se il problema persiste, sarà necessario analizzarlo in modo più dettagliato e cercare di ridurre il carico di lavoro.</span><span class="sxs-lookup"><span data-stu-id="333d6-146">If the problem continues, you will need to investigate further and possibly reduce workload.</span></span>  
  
  
