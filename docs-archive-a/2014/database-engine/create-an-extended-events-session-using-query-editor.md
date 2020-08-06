---
title: Creare una sessione eventi estesi tramite l'editor di query | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- create extended events session
- extended events [SQL Server], create session
ms.assetid: cba0e02b-b201-4863-bf1b-9164e68e5fa8
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 648370ecdd2938b6fb425955dc02da8960f884c2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628965"
---
# <a name="create-an-extended-events-session-using-query-editor"></a><span data-ttu-id="8fe42-102">Creare una sessione Eventi estesi tramite l'editor di query</span><span class="sxs-lookup"><span data-stu-id="8fe42-102">Create an Extended Events Session Using Query Editor</span></span>
  <span data-ttu-id="8fe42-103">È possibile creare una sessione Eventi estesi tramite l'editor di query o è possibile creare una sessione in Esplora oggetti.</span><span class="sxs-lookup"><span data-stu-id="8fe42-103">You can create an Extended Events session by using the Query Editor, or you can create a session in Object Explorer.</span></span> <span data-ttu-id="8fe42-104">In Esplora oggetti, gli eventi estesi forniscono due interfacce utente che è possibile usare per creare, modificare e visualizzare i dati della sessione eventi, una procedura guidata che guida l'utente durante il processo di creazione della sessione eventi e una nuova interfaccia utente della sessione che fornisce opzioni di configurazione più avanzate.</span><span class="sxs-lookup"><span data-stu-id="8fe42-104">In Object Explorer, Extended Events provides two user interfaces you can use to create, modify, and view event session data - a wizard that guides you through the event session creation process, and a New Session UI that provides more advanced configuration options.</span></span> <span data-ttu-id="8fe42-105">È possibile creare sessioni di eventi estesi per la diagnosi della traccia di SQL Server, che consente di risolvere problemi come i seguenti:</span><span class="sxs-lookup"><span data-stu-id="8fe42-105">You can create Extended Events sessions to diagnose SQL Server tracing, which enables you to resolve issues such as the following:</span></span>  
  
-   <span data-ttu-id="8fe42-106">Trovare le query con il costo più elevato</span><span class="sxs-lookup"><span data-stu-id="8fe42-106">Find your most expensive queries</span></span>  
  
-   <span data-ttu-id="8fe42-107">Trovare le cause principali di contese di latch</span><span class="sxs-lookup"><span data-stu-id="8fe42-107">Find root causes of latch contention</span></span>  
  
-   <span data-ttu-id="8fe42-108">Trovare una query tramite cui vengono bloccate altre query</span><span class="sxs-lookup"><span data-stu-id="8fe42-108">Find a query that is blocking other queries</span></span>  
  
-   <span data-ttu-id="8fe42-109">Risolvere i problemi relativi all'utilizzo eccessivo della CPU causato dalla ricompilazione di query</span><span class="sxs-lookup"><span data-stu-id="8fe42-109">Troubleshoot excessive CPU usage caused by query recompilation</span></span>  
  
-   <span data-ttu-id="8fe42-110">Risolvere problemi relativi ai deadlock</span><span class="sxs-lookup"><span data-stu-id="8fe42-110">Troubleshoot deadlocks</span></span>  
  
 <span data-ttu-id="8fe42-111">Per informazioni su come creare una sessione eventi estesi usando la Creazione guidata nuova sessione, vedere [Creare una sessione Eventi estesi usando la procedura guidata &#40;Esplora oggetti&#41;](../ssms/object/object-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="8fe42-111">For information about how to create an Extended Events session using the New Session Wizard, see [Create an Extended Events Session Using the Wizard &#40;Object Explorer&#41;](../ssms/object/object-explorer.md).</span></span> <span data-ttu-id="8fe42-112">Per informazioni su come creare una sessione eventi estesi usando l'interfaccia utente Nuova sessione, vedere [Creare una sessione Eventi estesi usando la finestra di dialogo Nuova sessione](../../2014/database-engine/create-an-extended-events-session-using-the-new-session-dialog.md).</span><span class="sxs-lookup"><span data-stu-id="8fe42-112">For information about how to create an Extended Events session using the New Session UI, see [Create an Extended Events Session Using the New Session Dialog](../../2014/database-engine/create-an-extended-events-session-using-the-new-session-dialog.md).</span></span>  
  
##  <a name="permissions"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="8fe42-113">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="8fe42-113">Permissions</span></span>  
 <span data-ttu-id="8fe42-114">Per creare una sessione Eventi estesi, è necessario disporre dell'autorizzazione ALTER ANY EVENT SESSION.</span><span class="sxs-lookup"><span data-stu-id="8fe42-114">To create an Extended Events session, you must have the ALTER ANY EVENT SESSION permission.</span></span>  
  
## <a name="creating-an-extended-events-session-using-query-editor"></a><span data-ttu-id="8fe42-115">Creazione di una sessione Eventi estesi tramite l'editor di query</span><span class="sxs-lookup"><span data-stu-id="8fe42-115">Creating an Extended Events session using Query Editor</span></span>  
  
#### <a name="to-create-an-extended-events-session"></a><span data-ttu-id="8fe42-116">Per creare una sessione Eventi estesi</span><span class="sxs-lookup"><span data-stu-id="8fe42-116">To create an Extended Events session</span></span>  
  
1.  <span data-ttu-id="8fe42-117">Nella procedura seguente viene illustrato come creare una sessione Eventi estesi utilizzando l'editor di query in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8fe42-117">The following procedure shows how to create an Extended Events session by using Query Editor in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
     <span data-ttu-id="8fe42-118">Determinare gli eventi che si desidera utilizzare nella sessione.</span><span class="sxs-lookup"><span data-stu-id="8fe42-118">Determine which events that you want to use in the session.</span></span> <span data-ttu-id="8fe42-119">Per visualizzare tutti gli eventi disponibili, insieme alla parola chiave e al canale, utilizzare la query seguente:</span><span class="sxs-lookup"><span data-stu-id="8fe42-119">To see all the events that are available, together with the keyword and channel, use the following query:</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8fe42-120">Per informazioni sulle parole chiave e i canali, vedere [Pacchetti degli eventi estesi di SQL Server](../relational-databases/extended-events/sql-server-extended-events-packages.md).</span><span class="sxs-lookup"><span data-stu-id="8fe42-120">For information about keywords and channels, see [SQL Server Extended Events Packages](../relational-databases/extended-events/sql-server-extended-events-packages.md).</span></span>  
  
    ```  
    SELECT p.name, c.event, k.keyword, c.channel, c.description FROM  
       (  
       SELECT event_package = o.package_guid, o.description,   
       event=c.object_name, channel = v.map_value  
       FROM sys.dm_xe_objects o  
       LEFT JOIN sys.dm_xe_object_columns c ON o.name = c.object_name  
       INNER JOIN sys.dm_xe_map_values v ON c.type_name = v.name   
       AND c.column_value = cast(v.map_key AS nvarchar)  
       WHERE object_type = 'event' AND (c.name = 'CHANNEL' or c.name IS NULL)  
       ) c LEFT JOIN   
       (  
       SELECT event_package = c.object_package_guid, event = c.object_name,   
       keyword = v.map_value  
       FROM sys.dm_xe_object_columns c INNER JOIN sys.dm_xe_map_values v   
       ON c.type_name = v.name AND c.column_value = v.map_key   
       AND c.type_package_guid = v.object_package_guid  
       INNER JOIN sys.dm_xe_objects o ON o.name = c.object_name   
       AND o.package_guid = c.object_package_guid  
       WHERE object_type = 'event' AND c.name = 'KEYWORD'   
       ) k  
       ON  
       k.event_package = c.event_package AND (k.event=c.event or k.event IS NULL)  
       INNER JOIN sys.dm_xe_packages p ON p.guid = c.event_package  
    ORDER BY keyword desc, channel, event  
    ```  
  
2.  <span data-ttu-id="8fe42-121">In una nuova finestra di query aggiungere le istruzioni seguenti per creare una sessione eventi, sostituendo *session_name* con il nome che si vuole usare per la sessione:</span><span class="sxs-lookup"><span data-stu-id="8fe42-121">In a new query window, add the following statements to create an event session, replacing *session_name* with the session name that you want to use:</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="8fe42-122">Nei passaggi da 2 a 6 di questa procedura viene descritta ogni sezione della definizione della sessione eventi.</span><span class="sxs-lookup"><span data-stu-id="8fe42-122">Steps 2 through 6 of this procedure describe each section of the event session definition.</span></span> <span data-ttu-id="8fe42-123">Tutte le istruzioni vengono aggiunte a una singola finestra di query prima dell'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="8fe42-123">You would add all the statements to a single query window before executing.</span></span> <span data-ttu-id="8fe42-124">Per un esempio completo, vedere la sezione Esempio di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="8fe42-124">For a full example, see the Example section of this topic.</span></span>  
  
    ```  
    CREATE EVENT SESSION session_name   
    ON SERVER  
    ```  
  
3.  <span data-ttu-id="8fe42-125">Aggiungere gli eventi da monitorare, nel formato *nome_pacchetto*.*nome_evento*.</span><span class="sxs-lookup"><span data-stu-id="8fe42-125">Add the events that you want to monitor, in the format *package_name*.*event_name*.</span></span> <span data-ttu-id="8fe42-126">Per ogni evento, aggiungere una riga simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="8fe42-126">For each event, add a line similar to the following:</span></span>  
  
    ```  
    ADD EVENT package_name.event_name  
    ```  
  
     <span data-ttu-id="8fe42-127">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="8fe42-127">For example:</span></span>  
  
    ```  
    ADD EVENT sqlserver.file_read_completed,  
    ADD EVENT sqlserver.file_write_completed  
    ```  
  
4.  <span data-ttu-id="8fe42-128">(Facoltativo) Dopo avere aggiunto un evento, è possibile aggiungere azioni da eseguire.</span><span class="sxs-lookup"><span data-stu-id="8fe42-128">(Optional) After you add an event, you can add actions to take.</span></span> <span data-ttu-id="8fe42-129">È inoltre possibile aggiungere predicati.</span><span class="sxs-lookup"><span data-stu-id="8fe42-129">You can also add predicates.</span></span> <span data-ttu-id="8fe42-130">I predicati vengono utilizzati per stabilire i criteri relativi a quando le informazioni sull'evento devono essere utilizzate dalla destinazione.</span><span class="sxs-lookup"><span data-stu-id="8fe42-130">Predicates are used to establish criteria for when the event information should be consumed by the target.</span></span> <span data-ttu-id="8fe42-131">Le azioni vengono aggiunte utilizzando una clausola ACTION, mentre i predicati vengono aggiunti utilizzando una clausola WHERE.</span><span class="sxs-lookup"><span data-stu-id="8fe42-131">Actions are added by using an ACTION clause, and predicates are added by using a WHERE clause.</span></span> <span data-ttu-id="8fe42-132">Ad esempio, per aggiungere un'azione e un predicato in cui viene acquisito il testo [!INCLUDE[tsql](../includes/tsql-md.md)] per l'evento sqlserver.file_read_completed, quando l'ID del file corrisponde a 1, includere l'istruzione seguente:</span><span class="sxs-lookup"><span data-stu-id="8fe42-132">For example, to add an action and predicate where the [!INCLUDE[tsql](../includes/tsql-md.md)] text is captured for the sqlserver.file_read_completed event, where the file ID equals 1, you would include the following statement:</span></span>  
  
    ```  
    ADD EVENT sqlserver.file_read_completed  
       (ACTION (sqlserver.sql_text)  
       WHERE file_id = 1),  
    ```  
  
    -   <span data-ttu-id="8fe42-133">Per visualizzare le azioni disponibili, utilizzare la query seguente:</span><span class="sxs-lookup"><span data-stu-id="8fe42-133">To view which actions are available, use the following query:</span></span>  
  
        ```  
        SELECT p.name AS 'package_name', xo.name AS 'action_name', xo.description, xo.object_type  
        FROM sys.dm_xe_objects AS xo  
        JOIN sys.dm_xe_packages AS p  
           ON xo.package_guid = p.guid  
        WHERE xo.object_type = 'action'  
        AND (xo.capabilities & 1 = 0   
        OR xo.capabilities IS NULL)  
        ORDER BY p.name, xo.name  
        ```  
  
    -   <span data-ttu-id="8fe42-134">Per visualizzare i predicati disponibili per un evento, usare la query seguente, sostituendo *event_name* con il nome dell'evento per cui si vuole aggiungere un predicato:</span><span class="sxs-lookup"><span data-stu-id="8fe42-134">To view which predicates are available for an event, use the following query, replacing *event_name* with the name of the event for which you want to add a predicate:</span></span>  
  
        ```  
        SELECT *  
        FROM sys.dm_xe_object_columns  
        WHERE object_name = 'event_name'  
        AND column_type = 'data'  
        ```  
  
         <span data-ttu-id="8fe42-135">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="8fe42-135">For example:</span></span>  
  
        ```  
        SELECT *   
        FROM sys.dm_xe_object_columns   
        WHERE object_name = 'file_read_completed'  
        AND column_type = 'data'  
        ```  
  
         <span data-ttu-id="8fe42-136">Tenere presente che è anche possibile aggiungere origini di predicati globali.</span><span class="sxs-lookup"><span data-stu-id="8fe42-136">Be aware that you can also add global predicate sources.</span></span> <span data-ttu-id="8fe42-137">Un'origine di predicato globale può essere utilizzata in qualsiasi espressione di predicato.</span><span class="sxs-lookup"><span data-stu-id="8fe42-137">A global predicate source can be used in any predicate expression.</span></span> <span data-ttu-id="8fe42-138">Per visualizzare le origini di predicati globali disponibili, utilizzare la query seguente:</span><span class="sxs-lookup"><span data-stu-id="8fe42-138">To view which global predicate sources are available, use the following query:</span></span>  
  
        ```  
        SELECT p.name AS package_name, xo.name AS predicate_name  
           , xo.description, xo.object_type  
        FROM sys.dm_xe_objects AS xo  
        JOIN sys.dm_xe_packages AS p  
           ON xo.package_guid = p.guid  
        WHERE xo.object_type = 'pred_source'  
        ORDER BY p.name, xo.name  
        ```  
  
         <span data-ttu-id="8fe42-139">È ad esempio possibile utilizzare l'espressione di predicato seguente per specificare che devono essere raccolti dati per un evento solo le prime cinque volte che l'evento si verifica.</span><span class="sxs-lookup"><span data-stu-id="8fe42-139">For example, you could use the following predicate expression to specify that data should only be collected for an event the first five times that an event occurs.</span></span>  
  
        ```  
        WHERE package0.counter <= 5  
        ```  
  
5.  <span data-ttu-id="8fe42-140">Aggiungere la destinazione desiderata, dove verranno elaborati e utilizzati i dati degli eventi.</span><span class="sxs-lookup"><span data-stu-id="8fe42-140">Add the desired target, where the event data will be processed and consumed.</span></span> <span data-ttu-id="8fe42-141">Utilizzare il seguente formato:</span><span class="sxs-lookup"><span data-stu-id="8fe42-141">Use the following format:</span></span>  
  
    ```  
    ADD TARGET package_name.target_name  
    ```  
  
     <span data-ttu-id="8fe42-142">Nell'esempio seguente viene aggiunta la destinazione file asincrona:</span><span class="sxs-lookup"><span data-stu-id="8fe42-142">The following example adds the asynchronous file target:</span></span>  
  
    ```  
    ADD TARGET package0.asynchronous_file_target  
       (SET filename = 'c:\temp\xelog.xel', metadatafile = 'c:\temp\xelog.xem')  
    ```  
  
     <span data-ttu-id="8fe42-143">Per visualizzare l'elenco di destinazioni disponibili, utilizzare la query seguente:</span><span class="sxs-lookup"><span data-stu-id="8fe42-143">To view the list of available targets, use the following query:</span></span>  
  
    ```  
    SELECT p.name AS 'package_name', xo.name AS 'target_name'  
       , xo.description, xo.object_type   
    FROM sys.dm_xe_objects AS xo  
    JOIN sys.dm_xe_packages AS p  
       ON xo.package_guid = p.guid  
    WHERE xo.object_type = 'target'  
    AND (xo.capabilities & 1 = 0  
    OR xo.capabilities IS NULL)  
    ORDER BY p.name, xo.name  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="8fe42-144">Per informazioni sui diversi tipi di destinazione, vedere [Destinazioni degli eventi estesi di SQL Server](../../2014/database-engine/sql-server-extended-events-targets.md).</span><span class="sxs-lookup"><span data-stu-id="8fe42-144">For information about the different target types, see [SQL Server Extended Events Targets](../../2014/database-engine/sql-server-extended-events-targets.md).</span></span>  
  
6.  <span data-ttu-id="8fe42-145">Rivedere e aggiungere eventuali opzioni di configurazione aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="8fe42-145">Review and add any additional configuration options.</span></span> <span data-ttu-id="8fe42-146">È ad esempio possibile configurare opzioni come la modalità di memorizzazione degli eventi, il tempo di permanenza degli eventi nel buffer in memoria o l'avvio automatico della sessione eventi all'avvio di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8fe42-146">For example, you can configure options such as the event retention mode, how long events are buffered in memory, or whether the event session should start automatically when [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] starts.</span></span> <span data-ttu-id="8fe42-147">Le opzioni sono descritte nell'argomento [ALTER EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-event-session-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="8fe42-147">The options are described in the topic [ALTER EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-event-session-transact-sql).</span></span> <span data-ttu-id="8fe42-148">Tenere presente che, se queste opzioni non vengono specificate, vengono assegnati valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="8fe42-148">Be aware that default values are assigned if these options are not specified.</span></span>  
  
7.  <span data-ttu-id="8fe42-149">Avviare la sessione.</span><span class="sxs-lookup"><span data-stu-id="8fe42-149">Start the session.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8fe42-150">Per altre informazioni su come visualizzare i risultati della sessione, vedere l'argomento corrispondente per il tipo di destinazione usato nel nodo [Destinazioni degli eventi estesi di SQL Server](../../2014/database-engine/sql-server-extended-events-targets.md) della documentazione online.</span><span class="sxs-lookup"><span data-stu-id="8fe42-150">For more information about how to view the session results, see the corresponding topic for the target type that you used in the [SQL Server Extended Events Targets](../../2014/database-engine/sql-server-extended-events-targets.md) node of Books Online.</span></span>  
  
 <span data-ttu-id="8fe42-151">Nell'esempio seguente viene creata una sessione Eventi estesi denominata IOActivity che consente di acquisire le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8fe42-151">The following example creates an Extended Events session named IOActivity that captures the following information:</span></span>  
  
-   <span data-ttu-id="8fe42-152">Dati degli eventi per le letture di file completate, incluso il testo [!INCLUDE[tsql](../includes/tsql-md.md)] associato per le letture di file in cui l'ID del file corrisponde a 1.</span><span class="sxs-lookup"><span data-stu-id="8fe42-152">Event data for completed file reads, including the associated [!INCLUDE[tsql](../includes/tsql-md.md)] text for file reads where the file ID is equal to 1.</span></span>  
  
-   <span data-ttu-id="8fe42-153">Dati degli eventi per le scritture di file completate.</span><span class="sxs-lookup"><span data-stu-id="8fe42-153">Event data for completed file writes.</span></span>  
  
-   <span data-ttu-id="8fe42-154">Dati degli eventi relativi a quando i dati vengono scritti dalla cache del log al file di log fisico.</span><span class="sxs-lookup"><span data-stu-id="8fe42-154">Event data for when data is written from the log cache to the physical log file.</span></span>  
  
 <span data-ttu-id="8fe42-155">L'output viene inviato dalla sessione a una destinazione file.</span><span class="sxs-lookup"><span data-stu-id="8fe42-155">The session sends the output to a file target.</span></span>  
  
```  
CREATE EVENT SESSION IOActivity  
ON SERVER  
  
ADD EVENT sqlserver.file_read_completed  
   (  
   ACTION (sqlserver.sql_text)  
   WHERE file_id = 1),  
ADD EVENT sqlserver.file_write_completed,  
ADD EVENT sqlserver.databases_log_flush  
  
ADD TARGET package0.asynchronous_file_target   
   (SET filename = 'c:\temp\xelog.xel', metadatafile = 'c:\temp\xelog.xem')  
```  
  
## <a name="see-also"></a><span data-ttu-id="8fe42-156">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8fe42-156">See Also</span></span>  
 <span data-ttu-id="8fe42-157">[CREATE EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-event-session-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8fe42-157">[CREATE EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-event-session-transact-sql) </span></span>  
 <span data-ttu-id="8fe42-158">[Destinazioni degli eventi estesi di SQL Server](../../2014/database-engine/sql-server-extended-events-targets.md) </span><span class="sxs-lookup"><span data-stu-id="8fe42-158">[SQL Server Extended Events Targets](../../2014/database-engine/sql-server-extended-events-targets.md) </span></span>  
 [<span data-ttu-id="8fe42-159">Pacchetti degli eventi estesi di SQL Server</span><span class="sxs-lookup"><span data-stu-id="8fe42-159">SQL Server Extended Events Packages</span></span>](../relational-databases/extended-events/sql-server-extended-events-packages.md)  
  
  
