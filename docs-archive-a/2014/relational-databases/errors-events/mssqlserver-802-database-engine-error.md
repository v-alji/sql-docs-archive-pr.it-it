---
title: MSSQLSERVER_802 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 802 (Database Engine error)
ms.assetid: 5892ed24-4dcb-4bf9-a8a4-a7ca898832d5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 9edcdda1410d7651f7c7531ef98c64c85741f15a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638423"
---
# <a name="mssqlserver_802"></a><span data-ttu-id="48f69-102">MSSQLSERVER_802</span><span class="sxs-lookup"><span data-stu-id="48f69-102">MSSQLSERVER_802</span></span>
    
## <a name="details"></a><span data-ttu-id="48f69-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="48f69-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="48f69-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="48f69-104">Product Name</span></span>|<span data-ttu-id="48f69-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="48f69-105">SQL Server</span></span>|  
|<span data-ttu-id="48f69-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="48f69-106">Event ID</span></span>|<span data-ttu-id="48f69-107">802</span><span class="sxs-lookup"><span data-stu-id="48f69-107">802</span></span>|  
|<span data-ttu-id="48f69-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="48f69-108">Event Source</span></span>|<span data-ttu-id="48f69-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="48f69-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="48f69-110">Componente</span><span class="sxs-lookup"><span data-stu-id="48f69-110">Component</span></span>|<span data-ttu-id="48f69-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="48f69-111">SQLEngine</span></span>|  
|<span data-ttu-id="48f69-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="48f69-112">Symbolic Name</span></span>|<span data-ttu-id="48f69-113">NO_BUFS</span><span class="sxs-lookup"><span data-stu-id="48f69-113">NO_BUFS</span></span>|  
|<span data-ttu-id="48f69-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="48f69-114">Message Text</span></span>|<span data-ttu-id="48f69-115">Memoria insufficiente nel pool di buffer.</span><span class="sxs-lookup"><span data-stu-id="48f69-115">There is insufficient memory available in the buffer pool.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="48f69-116">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="48f69-116">Explanation</span></span>  
 <span data-ttu-id="48f69-117">L'errore è causato dal fatto che il pool di buffer è pieno e non è possibile aumentarne le dimensioni.</span><span class="sxs-lookup"><span data-stu-id="48f69-117">This is caused when the buffer pool is full and the buffer pool can not grow any larger.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="48f69-118">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="48f69-118">User Action</span></span>  
 <span data-ttu-id="48f69-119">Nell'elenco seguente viene illustrata la procedura generale per la risoluzione degli errori di memoria:</span><span class="sxs-lookup"><span data-stu-id="48f69-119">The following list outlines general steps that will help in troubleshooting memory errors:</span></span>  
  
1.  <span data-ttu-id="48f69-120">Verificare se altre applicazioni o servizi utilizzano la memoria nel server specificato.</span><span class="sxs-lookup"><span data-stu-id="48f69-120">Verify whether other applications or services are consuming memory on this server.</span></span> <span data-ttu-id="48f69-121">Riconfigurare le applicazioni o i servizi meno critici per utilizzare una quantità di memoria inferiore.</span><span class="sxs-lookup"><span data-stu-id="48f69-121">Reconfigure less critical applications or services to consume less memory.</span></span>  
  
2.  <span data-ttu-id="48f69-122">Iniziare a raccogliere i dati dei contatori di Performance Monitor per [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **: Gestione buffer**, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **: Memory Manager**.</span><span class="sxs-lookup"><span data-stu-id="48f69-122">Start collecting performance monitor counters for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]**: Buffer Manager**, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]**: Memory Manager**.</span></span>  
  
3.  <span data-ttu-id="48f69-123">Verificare i seguenti parametri di configurazione della memoria di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="48f69-123">Check the following [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] memory configuration parameters:</span></span>  
  
    -   <span data-ttu-id="48f69-124">**max server memory**</span><span class="sxs-lookup"><span data-stu-id="48f69-124">**max server memory**</span></span>  
  
    -   <span data-ttu-id="48f69-125">**min server memory**</span><span class="sxs-lookup"><span data-stu-id="48f69-125">**min server memory**</span></span>  
  
    -   <span data-ttu-id="48f69-126">**min memory per query**</span><span class="sxs-lookup"><span data-stu-id="48f69-126">**min memory per query**</span></span>  
  
     <span data-ttu-id="48f69-127">Valutare eventuali impostazioni non comuni e correggerle se necessario.</span><span class="sxs-lookup"><span data-stu-id="48f69-127">Notice any unusual settings and correct them as necessary.</span></span> <span data-ttu-id="48f69-128">Considerare i requisiti di memoria aggiuntivi per [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="48f69-128">Account for increased memory requirements for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="48f69-129">Le impostazioni predefinite sono elencate nell'argomento "Impostazione delle opzioni di configurazione del server" nella documentazione online di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="48f69-129">Default settings are listed in "Setting Server Configuration Options" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
4.  <span data-ttu-id="48f69-130">Osservare l'output di DBCC MEMORYSTATUS e il modo in cui viene modificato quando vengono visualizzati questi messaggi di errore.</span><span class="sxs-lookup"><span data-stu-id="48f69-130">Observe DBCC MEMORYSTATUS output and the way it changes when you see these error messages.</span></span>  
  
5.  <span data-ttu-id="48f69-131">Verificare il carico di lavoro (numero di sessioni simultanee, query attualmente in esecuzione).</span><span class="sxs-lookup"><span data-stu-id="48f69-131">Check the workload (number of concurrent sessions, currently executing queries).</span></span>  
  
 <span data-ttu-id="48f69-132">Per aumentare la quantità di memoria disponibile per [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="48f69-132">The following actions may make more memory available to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="48f69-133">Se le risorse vengono utilizzate da altre applicazioni oltre a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], provare ad arrestare tali applicazioni o a eseguirle in un server distinto.</span><span class="sxs-lookup"><span data-stu-id="48f69-133">If applications besides [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are consuming resources, try stopping these applications or running them on a separate server.</span></span>  
  
-   <span data-ttu-id="48f69-134">Se è stata configurata l'opzione **max server memory,** , aumentarne il valore impostato.</span><span class="sxs-lookup"><span data-stu-id="48f69-134">If you have configured **max server memory,** increase the setting.</span></span>  
  
 <span data-ttu-id="48f69-135">Eseguire i comandi DBCC seguenti per liberare diverse cache in memoria di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="48f69-135">Run the following DBCC commands to free several [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] memory caches.</span></span>  
  
-   <span data-ttu-id="48f69-136">DBCC FREESYSTEMCACHE</span><span class="sxs-lookup"><span data-stu-id="48f69-136">DBCC FREESYSTEMCACHE</span></span>  
  
-   <span data-ttu-id="48f69-137">DBCC FREESESSIONCACHE</span><span class="sxs-lookup"><span data-stu-id="48f69-137">DBCC FREESESSIONCACHE</span></span>  
  
-   <span data-ttu-id="48f69-138">DBCC FREEPROCCACHE</span><span class="sxs-lookup"><span data-stu-id="48f69-138">DBCC FREEPROCCACHE</span></span>  
  
 <span data-ttu-id="48f69-139">Se il problema persiste, sarà necessario analizzarlo in modo più dettagliato e cercare di ridurre il carico di lavoro.</span><span class="sxs-lookup"><span data-stu-id="48f69-139">If the problem continues, you will need to investigate further and possibly reduce workload.</span></span>  
  
  
