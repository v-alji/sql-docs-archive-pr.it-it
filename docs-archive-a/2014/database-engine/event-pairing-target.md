---
title: Destinazione di abbinamento degli eventi | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- pairing target [SQL Server extended events]
- event pairing target
- targets [SQL Server extended events], pairing target
ms.assetid: 3c87dcfb-543a-4bd8-a73d-1390bdf4ffa3
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: a1a6beb1c6996e6e12f16c4555fd9dfcab97617d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716623"
---
# <a name="event-pairing-target"></a><span data-ttu-id="9324c-102">Destinazione di abbinamento degli eventi</span><span class="sxs-lookup"><span data-stu-id="9324c-102">Event Pairing Target</span></span>
  <span data-ttu-id="9324c-103">La destinazione di abbinamento degli eventi stabilisce la corrispondenza di due eventi utilizzando una o più colonne di dati presenti in ciascun evento.</span><span class="sxs-lookup"><span data-stu-id="9324c-103">The event pairing target matches two events using one or more columns of data that are present in each event.</span></span> <span data-ttu-id="9324c-104">Molti eventi entrano nelle coppie, ad esempio, le acquisizioni e i rilasci del blocco.</span><span class="sxs-lookup"><span data-stu-id="9324c-104">Many events come in pairs, for example, lock acquires and lock releases.</span></span> <span data-ttu-id="9324c-105">Dopo che una sequenza dell'evento viene abbinata, entrambi gli eventi sono ignorati.</span><span class="sxs-lookup"><span data-stu-id="9324c-105">After an event sequence is paired, both events are discarded.</span></span> <span data-ttu-id="9324c-106">Il fatto di ignorare i set corrispondenti consente un facile rilevamento di acquisizioni del blocco che non sono state rilasciate.</span><span class="sxs-lookup"><span data-stu-id="9324c-106">Discarding matched sets allows for easy detection of lock acquisitions that have not been released.</span></span>  
  
 <span data-ttu-id="9324c-107">Utilizzando filtri a livello di evento, la destinazione di abbinamento può essere utilizzata solo per acquisire eventi che non corrispondono a criteri preimpostati.</span><span class="sxs-lookup"><span data-stu-id="9324c-107">By using event-level filters, the pairing target can be used to only capture events that do not match pre-set criteria.</span></span>  
  
 <span data-ttu-id="9324c-108">Quando si utilizza la destinazione di abbinamento degli eventi, è possibile scegliere due eventi di cui verrà stabilita la corrispondenza, insieme a una sequenza di colonne su cui eseguire la corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="9324c-108">When you use the event pairing target, you can choose two events that will be matched, together with a sequence of columns to perform the matching on.</span></span> <span data-ttu-id="9324c-109">Tutte le colonne nella sequenza devono essere dello stesso tipo.</span><span class="sxs-lookup"><span data-stu-id="9324c-109">All the columns in this sequence must be of the same type.</span></span>  
  
 <span data-ttu-id="9324c-110">Nella tabella seguente vengono descritte le opzioni disponibili per configurare l'abbinamento degli eventi.</span><span class="sxs-lookup"><span data-stu-id="9324c-110">The following table describes the available options for configuring event pairing.</span></span>  
  
|<span data-ttu-id="9324c-111">Opzione</span><span class="sxs-lookup"><span data-stu-id="9324c-111">Option</span></span>|<span data-ttu-id="9324c-112">Valori consentiti</span><span class="sxs-lookup"><span data-stu-id="9324c-112">Allowed values</span></span>|<span data-ttu-id="9324c-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9324c-113">Description</span></span>|  
|------------|--------------------|-----------------|  
|<span data-ttu-id="9324c-114">begin_event</span><span class="sxs-lookup"><span data-stu-id="9324c-114">begin_event</span></span>|<span data-ttu-id="9324c-115">Qualsiasi nome di evento presente nella sessione corrente.</span><span class="sxs-lookup"><span data-stu-id="9324c-115">Any event name that is present in the current session.</span></span>|<span data-ttu-id="9324c-116">Nome di evento che specifica l'evento di inizio in una sequenza abbinata.</span><span class="sxs-lookup"><span data-stu-id="9324c-116">The event name specifying the beginning event in a paired sequence.</span></span>|  
|<span data-ttu-id="9324c-117">end_event</span><span class="sxs-lookup"><span data-stu-id="9324c-117">end_event</span></span>|<span data-ttu-id="9324c-118">Qualsiasi nome di evento presente nella sessione corrente.</span><span class="sxs-lookup"><span data-stu-id="9324c-118">Any event name that is present in the current session.</span></span>|<span data-ttu-id="9324c-119">Nome di evento che specifica l'evento di fine in una sequenza abbinata.</span><span class="sxs-lookup"><span data-stu-id="9324c-119">The event name specifying the ending event in a paired sequence.</span></span>|  
|<span data-ttu-id="9324c-120">begin_matching_columns</span><span class="sxs-lookup"><span data-stu-id="9324c-120">begin_matching_columns</span></span>|<span data-ttu-id="9324c-121">Elenco ordinato di nomi di colonne separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="9324c-121">A comma-delimited, ordered list of column names.</span></span>|<span data-ttu-id="9324c-122">Colonne su cui eseguire la corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="9324c-122">The columns to perform matching on.</span></span>|  
|<span data-ttu-id="9324c-123">end_matching_columns</span><span class="sxs-lookup"><span data-stu-id="9324c-123">end_matching_columns</span></span>|<span data-ttu-id="9324c-124">Elenco ordinato di nomi di colonne separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="9324c-124">A comma-delimited, ordered list of column names.</span></span>|<span data-ttu-id="9324c-125">Colonne su cui eseguire la corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="9324c-125">The columns to perform matching on.</span></span>|  
|<span data-ttu-id="9324c-126">begin_matching_actions</span><span class="sxs-lookup"><span data-stu-id="9324c-126">begin_matching_actions</span></span>|<span data-ttu-id="9324c-127">Elenco ordinato di azioni separate da virgole.</span><span class="sxs-lookup"><span data-stu-id="9324c-127">A comma-delimited, ordered list of actions.</span></span>|<span data-ttu-id="9324c-128">Azioni su cui eseguire la corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="9324c-128">The actions to perform matching on.</span></span>|  
|<span data-ttu-id="9324c-129">end_matching_actions</span><span class="sxs-lookup"><span data-stu-id="9324c-129">end_matching_actions</span></span>|<span data-ttu-id="9324c-130">Elenco ordinato di azioni separate da virgole.</span><span class="sxs-lookup"><span data-stu-id="9324c-130">A comma-delimited, ordered list of actions.</span></span>|<span data-ttu-id="9324c-131">Azioni su cui eseguire la corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="9324c-131">The actions to perform matching on.</span></span>|  
|<span data-ttu-id="9324c-132">respond_to_memory_pressure</span><span class="sxs-lookup"><span data-stu-id="9324c-132">respond_to_memory_pressure</span></span>|<span data-ttu-id="9324c-133">Uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="9324c-133">One of the following values:</span></span><br /><br /> <span data-ttu-id="9324c-134">0 = non rispondere.</span><span class="sxs-lookup"><span data-stu-id="9324c-134">0 = Do not respond.</span></span><br /><br /> <span data-ttu-id="9324c-135">1 = arrestare l'aggiunta di nuovi orfani all'elenco quando sono presenti richieste di memoria.</span><span class="sxs-lookup"><span data-stu-id="9324c-135">1 = Stop adding new orphans to the list when there is memory pressure.</span></span>|<span data-ttu-id="9324c-136">Risposta della destinazione agli eventi della memoria.</span><span class="sxs-lookup"><span data-stu-id="9324c-136">The target response to memory events.</span></span> <span data-ttu-id="9324c-137">Se il valore è impostato su 1 e la memoria del server è insufficiente, le informazioni non abbinate mantenute vengono rimosse.</span><span class="sxs-lookup"><span data-stu-id="9324c-137">If set to 1 and the server is low on memory, unpaired information that is being maintained is removed.</span></span>|  
|<span data-ttu-id="9324c-138">max_orphans</span><span class="sxs-lookup"><span data-stu-id="9324c-138">max_orphans</span></span>||<span data-ttu-id="9324c-139">Specifica il numero totale di eventi non abbinati che saranno raccolti nella destinazione.</span><span class="sxs-lookup"><span data-stu-id="9324c-139">Specifies the total number of unpaired events that will be collected in the target.</span></span> <span data-ttu-id="9324c-140">Una volta raggiunto il limite, gli eventi non abbinati vengono rimossi secondo la modalità FIFO.</span><span class="sxs-lookup"><span data-stu-id="9324c-140">Once the limit is reached, unpaired events are removed on a first-in, first-out (FIFO) basis.</span></span> <span data-ttu-id="9324c-141">Valore predefinito = 10,000.</span><span class="sxs-lookup"><span data-stu-id="9324c-141">Default = 10,000.</span></span>|  
  
 <span data-ttu-id="9324c-142">Tutti i dati associati a un evento sono acquisiti e archiviati per un abbinamento futuro.</span><span class="sxs-lookup"><span data-stu-id="9324c-142">All the data associated with an event is captured and stored for future pairing.</span></span> <span data-ttu-id="9324c-143">Vengono raccolti anche i dati aggiunti dalle azioni.</span><span class="sxs-lookup"><span data-stu-id="9324c-143">In addition, data added by actions is also collected.</span></span> <span data-ttu-id="9324c-144">I dati degli eventi raccolti vengono archiviati in memoria e, come tali, hanno un limite finito.</span><span class="sxs-lookup"><span data-stu-id="9324c-144">The collected event data is stored in memory, and therefore has a finite limit.</span></span> <span data-ttu-id="9324c-145">Questo limite è basato sulla capacità e sull'attività del sistema.</span><span class="sxs-lookup"><span data-stu-id="9324c-145">This limit is based on system capacity and activity.</span></span> <span data-ttu-id="9324c-146">Anziché utilizzare il valore massimo di memoria come parametro, la quantità di memoria utilizzata sarà basata sulle risorse di sistema disponibili.</span><span class="sxs-lookup"><span data-stu-id="9324c-146">Instead of taking the maximum amount of memory to be used as a parameter, the amount of memory used will be based on available system resources.</span></span> <span data-ttu-id="9324c-147">Quando queste non sono disponibili, gli eventi non abbinati che sono stati mantenuti saranno eliminati.</span><span class="sxs-lookup"><span data-stu-id="9324c-147">When these are not available, unpaired events that have been retained will be dropped.</span></span> <span data-ttu-id="9324c-148">Se un evento non è stato abbinato ed è stato eliminato, l'evento corrispondente comparirà come un evento non abbinato.</span><span class="sxs-lookup"><span data-stu-id="9324c-148">If an event has not been paired and is dropped, the matching event will appear as an unpaired event.</span></span>  
  
 <span data-ttu-id="9324c-149">La destinazione abbinamento serializza gli eventi non abbinati a un formato XML.</span><span class="sxs-lookup"><span data-stu-id="9324c-149">The pairing target serializes unpaired events to an XML format.</span></span> <span data-ttu-id="9324c-150">Questo formato non è conforme ad alcuno schema.</span><span class="sxs-lookup"><span data-stu-id="9324c-150">This format does not conform to any schema.</span></span> <span data-ttu-id="9324c-151">Il formato contiene solo due tipi di elementi.</span><span class="sxs-lookup"><span data-stu-id="9324c-151">The format only contains two element types.</span></span> <span data-ttu-id="9324c-152">L' **\<unpaired>** elemento è la radice, seguita da uno.</span><span class="sxs-lookup"><span data-stu-id="9324c-152">The **\<unpaired>** element is the root, followed by one.</span></span> <span data-ttu-id="9324c-153">**\<event>** elemento per ogni evento non abbinato attualmente rilevato.</span><span class="sxs-lookup"><span data-stu-id="9324c-153">**\<event>** element for each unpaired event that is currently being tracked.</span></span> <span data-ttu-id="9324c-154">L' **\<event>** elemento contiene un attributo che contiene il nome dell'evento non abbinato.</span><span class="sxs-lookup"><span data-stu-id="9324c-154">The **\<event>** element contains one attribute that contains the name of the unpaired event.</span></span>  
  
## <a name="adding-the-target-to-a-session"></a><span data-ttu-id="9324c-155">Aggiunta della destinazione a una sessione</span><span class="sxs-lookup"><span data-stu-id="9324c-155">Adding the Target to a Session</span></span>  
 <span data-ttu-id="9324c-156">Per aggiungere la destinazione di corrispondenza delle coppie a una sessione di eventi estesi, è necessario includere l'istruzione seguente quando si crea o modifica una sessione eventi:</span><span class="sxs-lookup"><span data-stu-id="9324c-156">To add the pair matching target to an Extended Events session, you must include the following statement when you create or alter an event session:</span></span>  
  
```  
ADD TARGET package0.pair_matching   
```  
  
 <span data-ttu-id="9324c-157">Far seguire all'istruzione un'istruzione SET per definire gli eventi di inizio e di fine e le azioni o le colonne di cui eseguire la corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="9324c-157">You would follow this with a SET statement, to define the beginning and ending events, and which actions or columns to match.</span></span> <span data-ttu-id="9324c-158">L'esempio seguente mostra la sintassi di esempio per la corrispondenza della coppia di eventi sqlserver.lock_acquired e sqlserver.lock_released.</span><span class="sxs-lookup"><span data-stu-id="9324c-158">The following example shows sample syntax for pair matching the sqlserver.lock_acquired and sqlserver.lock_released events.</span></span>  
  
```  
   ( SET begin_event = 'sqlserver.lock_acquired',  
      begin_matching_columns = 'database_id, resource_0, resource_1, resource_2, transaction_id, mode',  
      end_event = 'sqlserver.lock_released',  
      end_matching_columns = 'database_id, resource_0, resource_1, resource_2, transaction_id, mode',  
   respond_to_memory_pressure = 1)  
```  
  
 <span data-ttu-id="9324c-159">Per altre informazioni, vedere [Individuare le query che mantengono attivi i blocchi](../relational-databases/extended-events/determine-which-queries-are-holding-locks.md).</span><span class="sxs-lookup"><span data-stu-id="9324c-159">For more information, see [Determine Which Queries Are Holding Locks](../relational-databases/extended-events/determine-which-queries-are-holding-locks.md).</span></span>  
  
## <a name="reviewing-the-target-output"></a><span data-ttu-id="9324c-160">Analisi dell'output di destinazione</span><span class="sxs-lookup"><span data-stu-id="9324c-160">Reviewing the Target Output</span></span>  
 <span data-ttu-id="9324c-161">Per esaminare l'output per la destinazione di corrispondenza delle coppie, è possibile usare la query seguente sostituendo *session_name* con il nome della sessione eventi.</span><span class="sxs-lookup"><span data-stu-id="9324c-161">To review the output for the pair matching target, you can use the following query, replacing *session_name* with the name of the event session.</span></span>  
  
```  
SELECT name, target_name, CAST(xet.target_data AS xml)  
FROM sys.dm_xe_session_targets AS xet  
JOIN sys.dm_xe_sessions AS xe  
   ON (xe.address = xet.event_session_address)  
WHERE xe.name = 'session_name'  
```  
  
 <span data-ttu-id="9324c-162">Nell'esempio seguente viene illustrato il formato di output della destinazione di abbinamento.</span><span class="sxs-lookup"><span data-stu-id="9324c-162">The following example shows the pairing target output format.</span></span>  
  
```  
<unpaired truncated = "0" matchedCount = "[matched count]" memoryPressureDroppedCount = " [lost count]">  
    <event name  = "[event name]" package = "[package]" id= "[event ID value]" version = "[event version]">  
    <data name = "[column name]">   
    <type name = "[column type]" package = "[type package]" />   
    <value>[column value]</value>  
    <text value>[text value]</text>>  
        </data>  
    </event>  
</unpaired>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9324c-163">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9324c-163">See Also</span></span>  
 <span data-ttu-id="9324c-164">[Destinazioni degli eventi estesi di SQL Server](../../2014/database-engine/sql-server-extended-events-targets.md) </span><span class="sxs-lookup"><span data-stu-id="9324c-164">[SQL Server Extended Events Targets](../../2014/database-engine/sql-server-extended-events-targets.md) </span></span>  
 <span data-ttu-id="9324c-165">[sys.dm_xe_session_targets &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-xe-session-targets-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9324c-165">[sys.dm_xe_session_targets &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-xe-session-targets-transact-sql) </span></span>  
 <span data-ttu-id="9324c-166">[CREATE EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-event-session-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9324c-166">[CREATE EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-event-session-transact-sql) </span></span>  
 [<span data-ttu-id="9324c-167">ALTER EVENT SESSION &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9324c-167">ALTER EVENT SESSION &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-event-session-transact-sql)  
  
  
