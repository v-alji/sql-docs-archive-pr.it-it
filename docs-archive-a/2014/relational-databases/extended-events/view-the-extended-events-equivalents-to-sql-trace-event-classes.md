---
title: Visualizzare gli eventi estesi equivalenti alle classi di eventi di Traccia SQL | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xevents
ms.topic: conceptual
helpviewer_keywords:
- SQL Trace, extended events equivalents
- extended events [SQL Server], SQL Trace equivalents
- extended events [SQL Server], user configurable events
ms.assetid: 7f24104c-201d-4361-9759-f78a27936011
author: rothja
ms.author: jroth
ms.openlocfilehash: 37459359f9f6cb7e3951b705c4007477ec43e36a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711923"
---
# <a name="view-the-extended-events-equivalents-to-sql-trace-event-classes"></a><span data-ttu-id="79deb-102">Visualizzare gli eventi estesi equivalenti alle classi di evento di traccia SQL</span><span class="sxs-lookup"><span data-stu-id="79deb-102">View the Extended Events Equivalents to SQL Trace Event Classes</span></span>
  <span data-ttu-id="79deb-103">Se si desidera utilizzare gli eventi estesi per raccogliere dati degli eventi equivalenti a colonne e classi di evento di Traccia SQL, è utile comprendere in che modo viene eseguito il mapping degli eventi di Traccia SQL a eventi e azioni degli eventi estesi.</span><span class="sxs-lookup"><span data-stu-id="79deb-103">If you want to use Extended Events to collect event data that is equivalent to SQL Trace event classes and columns, it is useful to understand how the SQL Trace events map to Extended Events events and actions.</span></span>  
  
 <span data-ttu-id="79deb-104">È possibile utilizzare la procedura seguente per visualizzare gli eventi e le azioni degli eventi estesi equivalenti a ogni evento di Traccia SQL e alle colonne associate.</span><span class="sxs-lookup"><span data-stu-id="79deb-104">You can use the following procedure to view the Extended Events events and actions that are equivalent to each SQL Trace event and its associated columns.</span></span>  
  
## <a name="to-view-the-extended-events-equivalents-to-sql-trace-events-using-query-editor"></a><span data-ttu-id="79deb-105">Per visualizzare gli eventi estesi equivalenti agli eventi di Traccia SQL tramite l'editor di query</span><span class="sxs-lookup"><span data-stu-id="79deb-105">To view the Extended Events equivalents to SQL Trace events using Query Editor</span></span>  
  
-   <span data-ttu-id="79deb-106">Dall'editor di query in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]eseguire la query seguente:</span><span class="sxs-lookup"><span data-stu-id="79deb-106">From Query Editor in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], run the following query:</span></span>  
  
    ```  
    USE MASTER;  
    GO  
    SELECT DISTINCT  
       tb.trace_event_id,  
       te.name AS 'Event Class',  
       em.package_name AS 'Package',  
       em.xe_event_name AS 'XEvent Name',  
       tb.trace_column_id,  
       tc.name AS 'SQL Trace Column',  
       am.xe_action_name as 'Extended Events action'  
    FROM (sys.trace_events te LEFT OUTER JOIN sys.trace_xe_event_map em  
       ON te.trace_event_id = em.trace_event_id) LEFT OUTER JOIN sys.trace_event_bindings tb  
       ON em.trace_event_id = tb.trace_event_id LEFT OUTER JOIN sys.trace_columns tc  
       ON tb.trace_column_id = tc.trace_column_id LEFT OUTER JOIN sys.trace_xe_action_map am  
       ON tc.trace_column_id = am.trace_column_id  
    ORDER BY te.name, tc.name  
    ```  
  
 <span data-ttu-id="79deb-107">Quando si visualizzano i risultati, notare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="79deb-107">When you view the results, note the following:</span></span>  
  
-   <span data-ttu-id="79deb-108">Se tutte le colonne restituiscono NULL, ad eccezione della colonna Event Class, significa che non è stata eseguita la migrazione della classe di evento da Traccia SQL.</span><span class="sxs-lookup"><span data-stu-id="79deb-108">If all columns return NULL except for the Event Class column, this indicates that the event class was not migrated from SQL Trace.</span></span>  
  
-   <span data-ttu-id="79deb-109">Se solo il valore nella colonna azione Extended Events è NULL, significa che una delle condizioni seguenti è vera:</span><span class="sxs-lookup"><span data-stu-id="79deb-109">If only the value in the Extended Events action column is NULL, this indicates that either of the following conditions is true:</span></span>  
  
    -   <span data-ttu-id="79deb-110">Per la colonna di Traccia SQL viene eseguito il mapping a uno dei campi dati associati con l'evento degli eventi estesi.</span><span class="sxs-lookup"><span data-stu-id="79deb-110">The SQL Trace column maps to one of the data fields that is associated with the Extended Events event.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="79deb-111">Ogni evento degli eventi estesi dispone di un set predefinito di campi dati che vengono inclusi automaticamente nel set di risultati.</span><span class="sxs-lookup"><span data-stu-id="79deb-111">Each Extended Events event has a default set of data fields that are automatically included in the result set.</span></span>  
  
    -   <span data-ttu-id="79deb-112">La colonna relativa all'azione non dispone di un equivalente significativo degli eventi estesi.</span><span class="sxs-lookup"><span data-stu-id="79deb-112">The action column does not have a meaningful Extended Events equivalent.</span></span> <span data-ttu-id="79deb-113">Ne è un esempio la colonna EventClass in Traccia SQL.</span><span class="sxs-lookup"><span data-stu-id="79deb-113">An example of this is the EventClass column in SQL Trace.</span></span> <span data-ttu-id="79deb-114">Questo colonna non è necessaria negli eventi estesi in quanto il nome dell'evento svolge lo stesso ruolo.</span><span class="sxs-lookup"><span data-stu-id="79deb-114">This column is not needed in Extended Events because the event name serves the same purpose.</span></span>  
  
-   <span data-ttu-id="79deb-115">Per le classi di eventi di Traccia SQL configurabili dall'utente (da UserConfigurable:1 a UserConfigurable:9), la funzionalità Eventi estesi usa un singolo evento in sostituzione di tali classi.</span><span class="sxs-lookup"><span data-stu-id="79deb-115">For user configurable SQL Trace event classes (UserConfigurable:1 through UserConfigurable:9), Extended Events uses a single event to replace these.</span></span> <span data-ttu-id="79deb-116">Il nome dell'evento è user_event.</span><span class="sxs-lookup"><span data-stu-id="79deb-116">The event is named user_event.</span></span> <span data-ttu-id="79deb-117">Questo evento viene generato usando sp_trace_generateevent, che è la stessa stored procedure usata da Traccia SQL.</span><span class="sxs-lookup"><span data-stu-id="79deb-117">This event is raised by using sp_trace_generateevent, which is the same stored procedure that is used by SQL Trace.</span></span> <span data-ttu-id="79deb-118">L'evento user_event viene restituito indipendentemente dall'ID evento passato alla stored procedure.</span><span class="sxs-lookup"><span data-stu-id="79deb-118">The user_event event is returned regardless of which event ID is passed to the stored procedure.</span></span> <span data-ttu-id="79deb-119">Viene tuttavia restituito un campo event_id come parte dei dati dell'evento.</span><span class="sxs-lookup"><span data-stu-id="79deb-119">However, an event_id field is returned as part of the event data.</span></span> <span data-ttu-id="79deb-120">In questo modo, è possibile compilare un predicato basato sull'ID evento.</span><span class="sxs-lookup"><span data-stu-id="79deb-120">This enables you to build a predicate that is based on the event ID.</span></span> <span data-ttu-id="79deb-121">Se, ad esempio, si usa UserConfigurable:0 (event ID = 82) nel codice, è possibile aggiungere l'evento user_event alla sessione e specificare un predicato di 'event_id = 82'.</span><span class="sxs-lookup"><span data-stu-id="79deb-121">For example, if you use UserConfigurable:0 (event ID = 82) in the code, you can add the user_event event to the session, and specify a predicate of 'event_id = 82'.</span></span> <span data-ttu-id="79deb-122">Non è quindi necessario modificare il codice perché la stored procedure sp_trace_generateevent genera l'evento user_event degli eventi estesi e la classe di evento di Traccia SQL equivalente.</span><span class="sxs-lookup"><span data-stu-id="79deb-122">Therefore, you do not have to change the code because the sp_trace_generateevent stored procedure generates the Extended Events user_event event, and the equivalent SQL Trace event class.</span></span>  
  
-   <span data-ttu-id="79deb-123">Se tutte le colonne restituiscono NULL, ad eccezione della colonna Event Class, significa che non è stata eseguita la migrazione della classe di evento da Traccia SQL.</span><span class="sxs-lookup"><span data-stu-id="79deb-123">If all columns return NULL except for the Event Class column, this indicates that the event class was not migrated from SQL Trace.</span></span>  
  
-   <span data-ttu-id="79deb-124">Se solo il valore nella colonna azione Extended Events è NULL, significa che una delle condizioni seguenti è vera:</span><span class="sxs-lookup"><span data-stu-id="79deb-124">If only the value in the Extended Events action column is NULL, this indicates that either of the following conditions is true:</span></span>  
  
    -   <span data-ttu-id="79deb-125">Per la colonna di Traccia SQL viene eseguito il mapping a uno dei campi dati associati con l'evento degli eventi estesi.</span><span class="sxs-lookup"><span data-stu-id="79deb-125">The SQL Trace column maps to one of the data fields that is associated with the Extended Events event.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="79deb-126">Ogni evento degli eventi estesi dispone di un set predefinito di campi dati che vengono inclusi automaticamente nel set di risultati.</span><span class="sxs-lookup"><span data-stu-id="79deb-126">Each Extended Events event has a default set of data fields that are automatically included in the result set.</span></span>  
  
    -   <span data-ttu-id="79deb-127">La colonna relativa all'azione non dispone di un equivalente significativo degli eventi estesi.</span><span class="sxs-lookup"><span data-stu-id="79deb-127">The action column does not have a meaningful Extended Events equivalent.</span></span> <span data-ttu-id="79deb-128">Ne è un esempio la colonna EventClass in Traccia SQL.</span><span class="sxs-lookup"><span data-stu-id="79deb-128">An example of this is the EventClass column in SQL Trace.</span></span> <span data-ttu-id="79deb-129">Questo colonna non è necessaria negli eventi estesi in quanto il nome dell'evento svolge lo stesso ruolo.</span><span class="sxs-lookup"><span data-stu-id="79deb-129">This column is not needed in Extended Events because the event name serves the same purpose.</span></span>  
  
-   <span data-ttu-id="79deb-130">Per le classi di eventi di Traccia SQL configurabili dall'utente (da UserConfigurable:1 a UserConfigurable:9), la funzionalità Eventi estesi usa un singolo evento in sostituzione di tali classi.</span><span class="sxs-lookup"><span data-stu-id="79deb-130">For user configurable SQL Trace event classes (UserConfigurable:1 through UserConfigurable:9), Extended Events uses a single event to replace these.</span></span> <span data-ttu-id="79deb-131">Il nome dell'evento è user_event.</span><span class="sxs-lookup"><span data-stu-id="79deb-131">The event is named user_event.</span></span> <span data-ttu-id="79deb-132">Questo evento viene generato usando sp_trace_generateevent, che è la stessa stored procedure usata da Traccia SQL.</span><span class="sxs-lookup"><span data-stu-id="79deb-132">This event is raised by using sp_trace_generateevent, which is the same stored procedure that is used by SQL Trace.</span></span> <span data-ttu-id="79deb-133">L'evento user_event viene restituito indipendentemente dall'ID evento passato alla stored procedure.</span><span class="sxs-lookup"><span data-stu-id="79deb-133">The user_event event is returned regardless of which event ID is passed to the stored procedure.</span></span> <span data-ttu-id="79deb-134">Viene tuttavia restituito un campo event_id come parte dei dati dell'evento.</span><span class="sxs-lookup"><span data-stu-id="79deb-134">However, an event_id field is returned as part of the event data.</span></span> <span data-ttu-id="79deb-135">In questo modo, è possibile compilare un predicato basato sull'ID evento.</span><span class="sxs-lookup"><span data-stu-id="79deb-135">This enables you to build a predicate that is based on the event ID.</span></span> <span data-ttu-id="79deb-136">Se, ad esempio, si usa UserConfigurable:0 (event ID = 82) nel codice, è possibile aggiungere l'evento user_event alla sessione e specificare un predicato di 'event_id = 82'.</span><span class="sxs-lookup"><span data-stu-id="79deb-136">For example, if you use UserConfigurable:0 (event ID = 82) in the code, you can add the user_event event to the session, and specify a predicate of 'event_id = 82'.</span></span> <span data-ttu-id="79deb-137">Non è quindi necessario modificare il codice perché la stored procedure sp_trace_generateevent genera l'evento user_event degli eventi estesi e la classe di evento di Traccia SQL equivalente.</span><span class="sxs-lookup"><span data-stu-id="79deb-137">Therefore, you do not have to change the code because the sp_trace_generateevent stored procedure generates the Extended Events user_event event, and the equivalent SQL Trace event class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79deb-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="79deb-138">See Also</span></span>  
 [<span data-ttu-id="79deb-139">sp_trace_generateevent &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="79deb-139">sp_trace_generateevent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-generateevent-transact-sql)  
  
  
