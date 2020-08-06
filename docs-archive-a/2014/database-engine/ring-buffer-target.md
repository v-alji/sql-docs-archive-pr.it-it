---
title: Destinazione buffer circolare | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- targets [SQL Server extended events], ring buffer target
- ring buffer target [SQL Server extended events]
ms.assetid: 54494e11-b56b-43b7-aa5e-c8724e56b251
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 186e847bb9f9b621543119c25510dc5d6107e274
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636366"
---
# <a name="ring-buffer-target"></a><span data-ttu-id="07f3c-102">Destinazione del buffer circolare</span><span class="sxs-lookup"><span data-stu-id="07f3c-102">Ring Buffer Target</span></span>
  <span data-ttu-id="07f3c-103">La destinazione del buffer circolare mantiene brevemente in memoria i dati relativi agli eventi.</span><span class="sxs-lookup"><span data-stu-id="07f3c-103">The ring buffer target briefly holds event data in memory.</span></span> <span data-ttu-id="07f3c-104">Questa destinazione può gestire gli eventi in due modalità diverse.</span><span class="sxs-lookup"><span data-stu-id="07f3c-104">This target can manage events in one of two modes.</span></span>  
  
-   <span data-ttu-id="07f3c-105">La prima è una modalità di tipo puramente FIFO, in base alla quale l'evento meno recente viene eliminato una volta utilizzata tutta la memoria allocata alla destinazione.</span><span class="sxs-lookup"><span data-stu-id="07f3c-105">The first mode is strict first-in first-out (FIFO), where the oldest event is discarded when all the memory allocated to the target is used.</span></span> <span data-ttu-id="07f3c-106">In questa modalità, che rappresenta quella predefinita, il valore dell'opzione occurrence_number è impostato su 0.</span><span class="sxs-lookup"><span data-stu-id="07f3c-106">In this mode (the default), the occurrence_number option is set to 0.</span></span>  
  
-   <span data-ttu-id="07f3c-107">La seconda è una modalità FIFO basata sul tipo di evento, che prevede di mantenere in memoria un numero specificato di eventi di ciascun tipo.</span><span class="sxs-lookup"><span data-stu-id="07f3c-107">The second mode is per-event FIFO, where a specified number of events of each type is kept.</span></span> <span data-ttu-id="07f3c-108">In questa modalità, gli eventi meno recenti di ogni tipo vengono eliminati quando viene utilizzata tutta la memoria allocata alla destinazione.</span><span class="sxs-lookup"><span data-stu-id="07f3c-108">In this mode, the oldest events of each type are discarded when all the memory allocated to the target is used.</span></span> <span data-ttu-id="07f3c-109">È possibile configurare occurrence_number per specificare il numero di eventi di ciascun tipo da mantenere.</span><span class="sxs-lookup"><span data-stu-id="07f3c-109">You can configure the occurrence_number option to specify the number of events of each type to keep.</span></span>  
  
 <span data-ttu-id="07f3c-110">Nella tabella seguente vengono descritte le opzioni disponibili per la configurazione della destinazione del buffer circolare.</span><span class="sxs-lookup"><span data-stu-id="07f3c-110">The following table describes the available options for configuring the ring buffer target.</span></span>  
  
|<span data-ttu-id="07f3c-111">Opzione</span><span class="sxs-lookup"><span data-stu-id="07f3c-111">Option</span></span>|<span data-ttu-id="07f3c-112">Valori consentiti</span><span class="sxs-lookup"><span data-stu-id="07f3c-112">Allowed values</span></span>|<span data-ttu-id="07f3c-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="07f3c-113">Description</span></span>|  
|------------|--------------------|-----------------|  
|<span data-ttu-id="07f3c-114">max_memory</span><span class="sxs-lookup"><span data-stu-id="07f3c-114">max_memory</span></span>|<span data-ttu-id="07f3c-115">Qualsiasi intero a 32 bit.</span><span class="sxs-lookup"><span data-stu-id="07f3c-115">Any 32-bit integer.</span></span> <span data-ttu-id="07f3c-116">Questo valore è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="07f3c-116">This value is optional.</span></span>|<span data-ttu-id="07f3c-117">Quantità massima di memoria che può essere utilizzata in kilobyte (KB).</span><span class="sxs-lookup"><span data-stu-id="07f3c-117">The maximum amount of memory in kilobytes (KB) to use.</span></span> <span data-ttu-id="07f3c-118">Gli eventi esistenti vengono eliminati sulla base del limite che viene raggiunto per primo: max_event_limit o max_memory.</span><span class="sxs-lookup"><span data-stu-id="07f3c-118">Existing events are dropped based on the limit that is first reached: max_event_limit or max_memory.</span></span> <span data-ttu-id="07f3c-119">Il valore massimo è 4194303 KB.</span><span class="sxs-lookup"><span data-stu-id="07f3c-119">The maximum value is 4194303 KB.</span></span> <span data-ttu-id="07f3c-120">Prima di impostare le dimensioni del buffer circolare su limiti nell'intervallo di GB, è necessario prendere in considerazione una particolare attenzione, in quanto può influito su altri consumer di memoria in SQL Server</span><span class="sxs-lookup"><span data-stu-id="07f3c-120">A careful consideration should be made before setting the ring buffer size to limits in the GB range as it may impact other memory consumers in SQL Server</span></span>|  
|<span data-ttu-id="07f3c-121">max_event_limit</span><span class="sxs-lookup"><span data-stu-id="07f3c-121">max_event_limit</span></span>|<span data-ttu-id="07f3c-122">Qualsiasi intero a 32 bit.</span><span class="sxs-lookup"><span data-stu-id="07f3c-122">Any 32-bit integer.</span></span> <span data-ttu-id="07f3c-123">Questo valore è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="07f3c-123">This value is optional.</span></span>|<span data-ttu-id="07f3c-124">Il numero massimo di eventi tenuto in ring_buffer.</span><span class="sxs-lookup"><span data-stu-id="07f3c-124">The maximum number of events kept in the ring_buffer.</span></span> <span data-ttu-id="07f3c-125">Gli eventi esistenti vengono eliminati sulla base del limite che viene raggiunto per primo: max_event_limit o max_memory.</span><span class="sxs-lookup"><span data-stu-id="07f3c-125">Existing events are dropped based on the limit that is first reached: max_event_limit or max_memory.</span></span> <span data-ttu-id="07f3c-126">Valore predefinito = 1000.</span><span class="sxs-lookup"><span data-stu-id="07f3c-126">Default = 1000.</span></span>|  
|<span data-ttu-id="07f3c-127">occurrence_number</span><span class="sxs-lookup"><span data-stu-id="07f3c-127">occurrence_number</span></span>|<span data-ttu-id="07f3c-128">Uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="07f3c-128">One of the following values:</span></span><br /><br /> <span data-ttu-id="07f3c-129">0 (valore predefinito) = l'evento meno recente viene eliminato una volta utilizzata tutta la memoria allocata alla destinazione.</span><span class="sxs-lookup"><span data-stu-id="07f3c-129">0 (the default) = Oldest event is discarded when all the memory allocated to the target is used.</span></span><br /><br /> <span data-ttu-id="07f3c-130">Qualsiasi Integer a 32 bit = il numero di eventi di ogni tipo da contenere prima di essere scartati per ogni singolo evento.</span><span class="sxs-lookup"><span data-stu-id="07f3c-130">Any 32-bit integer = The number of events of each type to keep before being discarded on a per-event FIFO basis.</span></span><br /><br /> <br /><br /> <span data-ttu-id="07f3c-131">Questo valore è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="07f3c-131">This value is optional.</span></span>|<span data-ttu-id="07f3c-132">Modalità FIFO da utilizzare e, se il valore impostato è maggiore di 0, numero desiderato di eventi di ciascun tipo da mantenere nel buffer.</span><span class="sxs-lookup"><span data-stu-id="07f3c-132">The FIFO mode to use, and, if set to a value greater than 0, the preferred number of events of each type to keep in the buffer.</span></span>|
| &nbsp; | &nbsp; | &nbsp; |
  
## <a name="adding-the-target-to-a-session"></a><span data-ttu-id="07f3c-133">Aggiunta della destinazione a una sessione</span><span class="sxs-lookup"><span data-stu-id="07f3c-133">Adding the Target to a Session</span></span>  
 <span data-ttu-id="07f3c-134">Per aggiungere la destinazione del buffer circolare a una sessione di eventi estesi, è necessario includere l'istruzione seguente quando si crea o modifica una sessione eventi:</span><span class="sxs-lookup"><span data-stu-id="07f3c-134">To add the ring buffer target to an Extended Events session, you must include the following statement when you create or alter an event session:</span></span>  
  
```sql
ADD TARGET package0.ring_buffer  
```  
  
## <a name="reviewing-the-target-output"></a><span data-ttu-id="07f3c-135">Analisi dell'output di destinazione</span><span class="sxs-lookup"><span data-stu-id="07f3c-135">Reviewing the Target Output</span></span>  
 <span data-ttu-id="07f3c-136">Per esaminare l'output dalla destinazione del buffer circolare, è possibile usare la query seguente, sostituendo *nome_sessione* con il nome della sessione eventi.</span><span class="sxs-lookup"><span data-stu-id="07f3c-136">To review the output from the ring buffer target, you can use the following query, replacing *session_name* with the name of the event session.</span></span>  
  
```sql
SELECT name, target_name, CAST(xet.target_data AS xml)  
FROM sys.dm_xe_session_targets AS xet  
JOIN sys.dm_xe_sessions AS xe  
   ON (xe.address = xet.event_session_address)  
WHERE xe.name = 'session_name'  
```  
  
 <span data-ttu-id="07f3c-137">Nell'esempio seguente viene illustrato il formato di output della destinazione del buffer circolare.</span><span class="sxs-lookup"><span data-stu-id="07f3c-137">The following example shows the ring buffer target output format.</span></span>  
  
```  
<RingBufferTarget eventsPerSec="" processingTime="" totalEventsProcessed="" eventCount="" droppedCount="" memoryUsed="">  
 <event name="" package="" id="" version="" timestamp="">  
    <data name="">  
      <type name="" package="" />  
      <value></value>  
      <text></text>  
    </data>  
    <action name="" package="">  
      <type name="" package="" />  
      <value></value>  
      <text></text>  
    </action>  
  </event>  
</RingBufferTarget>  
```


## <a name="see-also"></a><span data-ttu-id="07f3c-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="07f3c-138">See Also</span></span>

- [<span data-ttu-id="07f3c-139">Destinazioni degli eventi estesi di SQL Server</span><span class="sxs-lookup"><span data-stu-id="07f3c-139">SQL Server Extended Events Targets</span></span>](../../2014/database-engine/sql-server-extended-events-targets.md)
- [<span data-ttu-id="07f3c-140">sys.dm_xe_session_targets &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="07f3c-140">sys.dm_xe_session_targets &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-xe-session-targets-transact-sql?view=sql-server-2016)
- [<span data-ttu-id="07f3c-141">CREATE EVENT SESSION &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="07f3c-141">CREATE EVENT SESSION &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-event-session-transact-sql?view=sql-server-2016)
- [<span data-ttu-id="07f3c-142">ALTER EVENT SESSION &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="07f3c-142">ALTER EVENT SESSION &#40;Transact-SQL&#41;</span></span>](https://docs.microsoft.com/sql/t-sql/statements/alter-event-session-transact-sql?view=sql-server-2016)

