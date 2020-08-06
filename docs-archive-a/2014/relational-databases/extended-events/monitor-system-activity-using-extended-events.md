---
title: Monitorare l'attività del sistema mediante gli eventi estesi | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xevents
ms.topic: conceptual
helpviewer_keywords:
- xe
- extended events [SQL Server], monitoring system activity
ms.assetid: d83ad88f-818c-49fe-a9a9-299f704fca53
author: rothja
ms.author: jroth
ms.openlocfilehash: d847d156d8244ede533e684c9e6b753d7d7b5047
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624170"
---
# <a name="monitor-system-activity-using-extended-events"></a><span data-ttu-id="4e790-102">Monitorare l'attività del sistema mediante gli eventi estesi</span><span class="sxs-lookup"><span data-stu-id="4e790-102">Monitor System Activity Using Extended Events</span></span>
  <span data-ttu-id="4e790-103">In questa procedura viene illustrato come utilizzare gli eventi estesi con Analisi eventi per Windows (ETW) al fine di monitorare l'attività del sistema.</span><span class="sxs-lookup"><span data-stu-id="4e790-103">This procedure illustrates how Extended Events can be used with Event Tracing for Windows (ETW) to monitor system activity.</span></span> <span data-ttu-id="4e790-104">Viene inoltre indicata la modalità di utilizzo delle istruzioni CREATE EVENT SESSION, ALTER EVENT SESSION e DROP EVENT SESSION.</span><span class="sxs-lookup"><span data-stu-id="4e790-104">The procedure also shows how the CREATE EVENT SESSION, ALTER EVENT SESSION, and DROP EVENT SESSION statements are used.</span></span>  
  
 <span data-ttu-id="4e790-105">Il completamento di tali attività comporta l'utilizzo dell'editor di query in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] per effettuare la procedura descritta di seguito.</span><span class="sxs-lookup"><span data-stu-id="4e790-105">Accomplishing these tasks involves using Query Editor in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to carry out the following procedure.</span></span> <span data-ttu-id="4e790-106">La procedura richiede anche l'utilizzo del prompt dei comandi per eseguire comandi ETW.</span><span class="sxs-lookup"><span data-stu-id="4e790-106">The procedure also requires using the command prompt to run ETW commands.</span></span>  
  
### <a name="to-monitor-system-activity-using-extended-events"></a><span data-ttu-id="4e790-107">Per monitorare l'attività del sistema mediante gli eventi estesi</span><span class="sxs-lookup"><span data-stu-id="4e790-107">To monitor system activity using Extended Events</span></span>  
  
1.  <span data-ttu-id="4e790-108">Nell'editor di query eseguire le istruzioni indicate di seguito per creare una sessione eventi e aggiungere due eventi.</span><span class="sxs-lookup"><span data-stu-id="4e790-108">In Query Editor, issue the following statements to create an event session and add two events.</span></span> <span data-ttu-id="4e790-109">Tali eventi, ovvero checkpoint_begin e checkpoint_end, vengono generati all'inizio e alla fine di un checkpoint del database.</span><span class="sxs-lookup"><span data-stu-id="4e790-109">These events, checkpoint_begin and checkpoint_end, fire at the beginning and end of a database checkpoint.</span></span>  
  
    ```  
    CREATE EVENT SESSION test0  
    ON SERVER  
    ADD EVENT sqlserver.checkpoint_begin,  
    ADD EVENT sqlserver.checkpoint_end  
    WITH (MAX_DISPATCH_LATENCY = 1 SECONDS)  
    go  
    ```  
  
2.  <span data-ttu-id="4e790-110">Aggiungere la destinazione di bucket con 32 bucket per contare il numero di checkpoint in base all'ID del database.</span><span class="sxs-lookup"><span data-stu-id="4e790-110">Add the bucketing target with 32 buckets to count the number of checkpoints based on the database ID.</span></span>  
  
    ```  
    ALTER EVENT SESSION test0  
    ON SERVER  
    ADD TARGET package0.histogram  
    (  
          SET slots = 32, filtering_event_name = 'sqlserver.checkpoint_end', source_type = 0, source = 'database_id'  
    )  
    go  
    ```  
  
3.  <span data-ttu-id="4e790-111">Eseguire le istruzioni indicate di seguito per aggiungere la destinazione ETW.</span><span class="sxs-lookup"><span data-stu-id="4e790-111">Issue the following statements to add the ETW target.</span></span> <span data-ttu-id="4e790-112">Verranno visualizzati gli eventi di inizio e di fine utilizzati per determinare il tempo necessario per il checkpoint.</span><span class="sxs-lookup"><span data-stu-id="4e790-112">This will enable you to see the begin and end events, which is used to determine how long the checkpoint takes.</span></span>  
  
    ```  
    ALTER EVENT SESSION test0  
    ON SERVER  
    ADD TARGET package0.etw_classic_sync_target  
    go  
    ```  
  
4.  <span data-ttu-id="4e790-113">Eseguire le istruzioni indicate di seguito per avviare la sessione e iniziare la raccolta degli eventi.</span><span class="sxs-lookup"><span data-stu-id="4e790-113">Issue the following statements to start the session and begin event collection.</span></span>  
  
    ```  
    ALTER EVENT SESSION test0  
    ON SERVER  
    STATE = start  
    go  
    ```  
  
5.  <span data-ttu-id="4e790-114">Eseguire le istruzioni indicate di seguito per generare tre eventi.</span><span class="sxs-lookup"><span data-stu-id="4e790-114">Issue the following statements to cause three events to fire.</span></span>  
  
    ```  
    USE tempdb  
          checkpoint  
    go  
    USE master  
          checkpoint  
          checkpoint  
    go  
    ```  
  
6.  <span data-ttu-id="4e790-115">Eseguire le istruzioni indicate di seguito per visualizzare il conteggio degli eventi.</span><span class="sxs-lookup"><span data-stu-id="4e790-115">Issue the following statements to view the event counts.</span></span>  
  
    ```  
    SELECT CAST(xest.target_data AS xml) Bucketizer_Target_Data_in_XML  
    FROM sys.dm_xe_session_targets xest  
    JOIN sys.dm_xe_sessions xes ON xes.address = xest.event_session_address  
    JOIN sys.server_event_sessions ses ON xes.name = ses.name  
    WHERE xest.target_name = 'histogram' AND xes.name = 'test0'  
    go  
    ```  
  
7.  <span data-ttu-id="4e790-116">Al prompt dei comandi eseguire i comandi indicati di seguito per visualizzare i dati ETW.</span><span class="sxs-lookup"><span data-stu-id="4e790-116">At the command prompt, issue the following commands to view the ETW data.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4e790-117">Per informazioni sul comando **tracerpt** , al prompt dei comandi immettere `tracerpt /?`.</span><span class="sxs-lookup"><span data-stu-id="4e790-117">To get help for the **tracerpt** command, at the command prompt, enter `tracerpt /?`.</span></span>  
  
    ```  
    logman query -ets --- List the ETW sessions. This is optional.  
    logman update XE_DEFAULT_ETW_SESSION -fd -ets --- Flush the ETW log.  
    tracerpt %temp%\xeetw.etl -o xeetw.txt --- Dump the events so they can be seen.  
    ```  
  
8.  <span data-ttu-id="4e790-118">Eseguire le istruzioni indicate di seguito per arrestare la sessione eventi e rimuoverla dal server.</span><span class="sxs-lookup"><span data-stu-id="4e790-118">Issue the following statements to stop the event session and remove it from the server.</span></span>  
  
    ```  
    ALTER EVENT SESSION test0  
    ON SERVER  
    STATE = STOP  
    go  
  
    DROP EVENT SESSION test0  
    ON SERVER  
    go  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="4e790-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4e790-119">See Also</span></span>  
 <span data-ttu-id="4e790-120">[CREATE EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-event-session-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4e790-120">[CREATE EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-event-session-transact-sql) </span></span>  
 <span data-ttu-id="4e790-121">[ALTER EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-event-session-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4e790-121">[ALTER EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-event-session-transact-sql) </span></span>  
 <span data-ttu-id="4e790-122">[DROP EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-event-session-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4e790-122">[DROP EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-event-session-transact-sql) </span></span>  
 [<span data-ttu-id="4e790-123">Viste del catalogo degli eventi estesi &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4e790-123">Extended Events Catalog Views &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/extended-events-catalog-views-transact-sql)  
 <span data-ttu-id="4e790-124">[Viste a gestione dinamica degli eventi estesi](../views/views.md) </span><span class="sxs-lookup"><span data-stu-id="4e790-124">[Extended Events Dynamic Management Views](../views/views.md) </span></span>  
 [<span data-ttu-id="4e790-125">Destinazioni degli eventi estesi di SQL Server</span><span class="sxs-lookup"><span data-stu-id="4e790-125">SQL Server Extended Events Targets</span></span>](../../database-engine/sql-server-extended-events-targets.md)  
  
  
