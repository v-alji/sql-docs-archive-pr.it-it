---
title: Pacchetti degli eventi estesi di SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xevents
ms.topic: conceptual
helpviewer_keywords:
- extended events [SQL Server], packages
- xe
ms.assetid: 6bcb04fc-ca04-48f4-b96a-20b604973447
author: rothja
ms.author: jroth
ms.openlocfilehash: 45c452300c008d486bd1f4ab4c92b5f76b96ecd8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624162"
---
# <a name="sql-server-extended-events-packages"></a><span data-ttu-id="f4299-102">Pacchetti degli eventi estesi di SQL Server</span><span class="sxs-lookup"><span data-stu-id="f4299-102">SQL Server Extended Events Packages</span></span>
  <span data-ttu-id="f4299-103">Un pacchetto è un contenitore per oggetti eventi estesi di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f4299-103">A package is a container for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Extended Events objects.</span></span> <span data-ttu-id="f4299-104">Di seguito vengono indicati i tre tipi di pacchetti di eventi estesi:</span><span class="sxs-lookup"><span data-stu-id="f4299-104">There are three kinds of Extended Events packages, which include the following:</span></span>  
  
-   <span data-ttu-id="f4299-105">package0 – Oggetti di sistema Eventi estesi.</span><span class="sxs-lookup"><span data-stu-id="f4299-105">package0 - Extended Events system objects.</span></span> <span data-ttu-id="f4299-106">Questo è il pacchetto predefinito.</span><span class="sxs-lookup"><span data-stu-id="f4299-106">This is the default package.</span></span>  
  
-   <span data-ttu-id="f4299-107">sqlserver: oggetti correlati a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f4299-107">sqlserver - [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] related objects.</span></span>  
  
-   <span data-ttu-id="f4299-108">sqlos: oggetti correlati al sistema operativo di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (SQLOS).</span><span class="sxs-lookup"><span data-stu-id="f4299-108">sqlos - [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Operating System (SQLOS) related objects.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f4299-109">Il pacchetto SecAudit viene utilizzato da [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Audit.</span><span class="sxs-lookup"><span data-stu-id="f4299-109">The SecAudit package is used by [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Audit.</span></span> <span data-ttu-id="f4299-110">Nessuno degli oggetti nel pacchetto è disponibile tramite DDL (Data Definition Language) di eventi estesi.</span><span class="sxs-lookup"><span data-stu-id="f4299-110">None of the objects in the package are available through the Extended Events data definition language (DDL).</span></span>  
  
 <span data-ttu-id="f4299-111">I pacchetti sono identificati da un nome, da un GUID e dal modulo binario che contiene il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="f4299-111">Packages are identified by a name, a GUID, and the binary module that contains the package.</span></span> <span data-ttu-id="f4299-112">Per altre informazioni, vedere [sys.dm_xe_packages &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-xe-packages-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f4299-112">For more information, see [sys.dm_xe_packages &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-xe-packages-transact-sql).</span></span>  
  
 <span data-ttu-id="f4299-113">Un pacchetto può contenere alcuni o tutti gli oggetti seguenti, che vengono discussi in maggior dettaglio più avanti in questo argomento:</span><span class="sxs-lookup"><span data-stu-id="f4299-113">A package can contain any or all of the following objects, which are discussed in greater detail later in this topic:</span></span>  
  
-   <span data-ttu-id="f4299-114">Events</span><span class="sxs-lookup"><span data-stu-id="f4299-114">Events</span></span>  
  
-   <span data-ttu-id="f4299-115">Destinazioni</span><span class="sxs-lookup"><span data-stu-id="f4299-115">Targets</span></span>  
  
-   <span data-ttu-id="f4299-116">Azioni</span><span class="sxs-lookup"><span data-stu-id="f4299-116">Actions</span></span>  
  
-   <span data-ttu-id="f4299-117">Tipi</span><span class="sxs-lookup"><span data-stu-id="f4299-117">Types</span></span>  
  
-   <span data-ttu-id="f4299-118">Predicati</span><span class="sxs-lookup"><span data-stu-id="f4299-118">Predicates</span></span>  
  
-   <span data-ttu-id="f4299-119">Mappe</span><span class="sxs-lookup"><span data-stu-id="f4299-119">Maps</span></span>  
  
 <span data-ttu-id="f4299-120">Oggetti da pacchetti diversi possono essere combinati in una sessione dell'evento.</span><span class="sxs-lookup"><span data-stu-id="f4299-120">Objects from different packages can be mixed in an event session.</span></span> <span data-ttu-id="f4299-121">Per altre informazioni, vedere [Sessioni degli eventi estesi di SQL Server](sql-server-extended-events-sessions.md).</span><span class="sxs-lookup"><span data-stu-id="f4299-121">For more information, see [SQL Server Extended Events Sessions](sql-server-extended-events-sessions.md).</span></span>  
  
## <a name="package-contents"></a><span data-ttu-id="f4299-122">Contenuti del pacchetto</span><span class="sxs-lookup"><span data-stu-id="f4299-122">Package Contents</span></span>  
 <span data-ttu-id="f4299-123">Nella figura seguente si illustrano gli oggetti che possono essere presenti nei pacchetti, che sono contenuti in un modulo.</span><span class="sxs-lookup"><span data-stu-id="f4299-123">The following illustration shows the objects that can exist in packages, which are contained in a module.</span></span> <span data-ttu-id="f4299-124">Un modulo può essere un file eseguibile o una libreria a collegamento dinamico (DLL).</span><span class="sxs-lookup"><span data-stu-id="f4299-124">A module can be an executable or a dynamic link library.</span></span>  
  
 <span data-ttu-id="f4299-125">![Relazione tra un modulo, pacchetti e un oggetto](../../database-engine/media/xepackagesobjects.gif "Relazione tra un modulo, pacchetti e un oggetto")</span><span class="sxs-lookup"><span data-stu-id="f4299-125">![The relationship of a module, packages, and object](../../database-engine/media/xepackagesobjects.gif "The relationship of a module, packages, and object")</span></span>  
  
### <a name="events"></a><span data-ttu-id="f4299-126">Events</span><span class="sxs-lookup"><span data-stu-id="f4299-126">Events</span></span>  
 <span data-ttu-id="f4299-127">Gli eventi monitorano i punti di interesse nel percorso di esecuzione di un programma, ad esempio [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f4299-127">Events are monitoring points of interest in the execution path of a program, such as [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="f4299-128">La generazione di un evento implica che il punto di interesse è stato raggiunto e fornisce informazioni sullo stato derivanti dall'ora in cui l'evento è stato generato.</span><span class="sxs-lookup"><span data-stu-id="f4299-128">An event firing carries with it the fact that the point of interest was reached, and state information from the time the event was fired.</span></span>  
  
 <span data-ttu-id="f4299-129">Gli eventi possono essere utilizzati solamente per scopi di traccia o per azioni di trigger.</span><span class="sxs-lookup"><span data-stu-id="f4299-129">Events can be used solely for tracing purposes or for triggering actions.</span></span> <span data-ttu-id="f4299-130">Queste azioni possono essere sincrone o asincrone.</span><span class="sxs-lookup"><span data-stu-id="f4299-130">These actions can either be synchronous or asynchronous.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f4299-131">Un evento non ha alcuna conoscenza delle azioni che possono essere lanciate in risposta all'attivazione di eventi.</span><span class="sxs-lookup"><span data-stu-id="f4299-131">An event does not have any knowledge of the actions that may be triggered in response to the event firing.</span></span>  
  
 <span data-ttu-id="f4299-132">Un set di eventi in un pacchetto non può essere modificato dopo che il pacchetto viene registrato con gli eventi estesi.</span><span class="sxs-lookup"><span data-stu-id="f4299-132">A set of events in a package cannot change after the package is registered with Extended Events.</span></span>  
  
 <span data-ttu-id="f4299-133">A tutti gli eventi è associato uno schema con versione che ne definisce il contenuto.</span><span class="sxs-lookup"><span data-stu-id="f4299-133">All events have a versioned schema which defines their contents.</span></span> <span data-ttu-id="f4299-134">Questo schema è costituito da colonne di evento con tipi ben definiti.</span><span class="sxs-lookup"><span data-stu-id="f4299-134">This schema is composed of event columns with well defined types.</span></span> <span data-ttu-id="f4299-135">Un evento di un tipo specifico deve sempre fornire i propri dati nell'ordine esatto specificato nello schema.</span><span class="sxs-lookup"><span data-stu-id="f4299-135">An event of a specific type must always provide its data in exactly the same order that is specified in the schema.</span></span> <span data-ttu-id="f4299-136">Una destinazione dell'evento non deve tuttavia utilizzare tutti i dati forniti.</span><span class="sxs-lookup"><span data-stu-id="f4299-136">However, an event target does not have to consume all the data that is provided.</span></span>  
  
#### <a name="event-categorization"></a><span data-ttu-id="f4299-137">Categorizzazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="f4299-137">Event Categorization</span></span>  
 <span data-ttu-id="f4299-138">Negli eventi estesi viene utilizzato un modello di categorizzazione dell'evento simile a Analisi eventi per Windows (ETW).</span><span class="sxs-lookup"><span data-stu-id="f4299-138">Extended Events uses an event categorization model similar to Event Tracing for Windows (ETW).</span></span> <span data-ttu-id="f4299-139">Due proprietà dell'evento sono utilizzate per categorizzazione, canale e parola chiave.</span><span class="sxs-lookup"><span data-stu-id="f4299-139">Two event properties are used for categorization, channel and keyword.</span></span> <span data-ttu-id="f4299-140">L'utilizzo di queste proprietà supporta l'integrazione degli eventi estesi con ETW e i suoi strumenti.</span><span class="sxs-lookup"><span data-stu-id="f4299-140">Using these properties supports the integration of Extended Events with ETW and its tools.</span></span>  
  
 <span data-ttu-id="f4299-141">**Channel**</span><span class="sxs-lookup"><span data-stu-id="f4299-141">**Channel**</span></span>  
  
 <span data-ttu-id="f4299-142">Un canale identifica il pubblico per un evento.</span><span class="sxs-lookup"><span data-stu-id="f4299-142">A channel identifies the audience for an event.</span></span> <span data-ttu-id="f4299-143">Questi canali sono descritti nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="f4299-143">These channels are described in the following table.</span></span>  
  
|<span data-ttu-id="f4299-144">Termine</span><span class="sxs-lookup"><span data-stu-id="f4299-144">Term</span></span>|<span data-ttu-id="f4299-145">Definizione</span><span class="sxs-lookup"><span data-stu-id="f4299-145">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="f4299-146">Amministrativi</span><span class="sxs-lookup"><span data-stu-id="f4299-146">Admin</span></span>|<span data-ttu-id="f4299-147">Gli eventi amministrativi sono indirizzati principalmente agli utenti finali, agli 'amministratori e al supporto.</span><span class="sxs-lookup"><span data-stu-id="f4299-147">Admin events are primarily targeted to the end users, administrators, and support.</span></span> <span data-ttu-id="f4299-148">Gli eventi trovati nei canali amministrativi indicano un problema con una soluzione ben definita sul quale può agire un amministratore.</span><span class="sxs-lookup"><span data-stu-id="f4299-148">The events that are found in the admin channels indicate a problem with a well-defined solution that an administrator can act on.</span></span> <span data-ttu-id="f4299-149">Un esempio di evento amministrativo è quando un'applicazione non riesce a connettersi a una stampante.</span><span class="sxs-lookup"><span data-stu-id="f4299-149">An example of an admin event is when an application fails to connect to a printer.</span></span> <span data-ttu-id="f4299-150">Questi eventi sono ben documentati oppure hanno un messaggio ad essi associato che comunica a chi legge che cosa fare per risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="f4299-150">These events are either well-documented or have a message associated with them that tells the reader what to do to rectify the problem.</span></span>|  
|<span data-ttu-id="f4299-151">Operativo</span><span class="sxs-lookup"><span data-stu-id="f4299-151">Operational</span></span>|<span data-ttu-id="f4299-152">Gli eventi operativi sono utilizzati per l'analisi e la diagnostica di un problema o di un'occorrenza.</span><span class="sxs-lookup"><span data-stu-id="f4299-152">Operational events are used for analyzing and diagnosing a problem or occurrence.</span></span> <span data-ttu-id="f4299-153">Si possono utilizzare per lanciare strumenti o attività basati sul problema o sull'occorrenza.</span><span class="sxs-lookup"><span data-stu-id="f4299-153">They can be used to trigger tools or tasks based on the problem or occurrence.</span></span> <span data-ttu-id="f4299-154">Un esempio di un evento operativo è quando una stampante viene aggiunta o rimossa da un sistema.</span><span class="sxs-lookup"><span data-stu-id="f4299-154">An example of an operational event is when a printer is added or removed from a system.</span></span>|  
|<span data-ttu-id="f4299-155">Analitici</span><span class="sxs-lookup"><span data-stu-id="f4299-155">Analytic</span></span>|<span data-ttu-id="f4299-156">Gli eventi analitici sono pubblicati in volumi elevati.</span><span class="sxs-lookup"><span data-stu-id="f4299-156">Analytic events are published in high volume.</span></span> <span data-ttu-id="f4299-157">Descrivono il funzionamento del programma e sono in genere utilizzati nell'analisi delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="f4299-157">They describe program operation and are typically used in performance investigations.</span></span>|  
|<span data-ttu-id="f4299-158">Debug</span><span class="sxs-lookup"><span data-stu-id="f4299-158">Debug</span></span>|<span data-ttu-id="f4299-159">Gli eventi di debug sono utilizzati solamente dagli sviluppatori per diagnosticare un problema nelle operazioni di debug.</span><span class="sxs-lookup"><span data-stu-id="f4299-159">Debug events are used solely by developers to diagnose a problem for debugging.</span></span><br /><br /> <span data-ttu-id="f4299-160">Nota: gli eventi nel canale di debug restituiscono dati di stato interni specifici dell'implementazione.</span><span class="sxs-lookup"><span data-stu-id="f4299-160">Note: Events in the Debug channel return internal implementation-specific state data.</span></span> <span data-ttu-id="f4299-161">Gli schemi e i dati restituiti dagli eventi potrebbero cambiare o non essere più validi nelle versioni future di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f4299-161">The schemas and data that the events return may change or become invalid in future versions of SQL Server.</span></span> <span data-ttu-id="f4299-162">Pertanto, gli eventi nel canale di debug potrebbero cambiare o essere rimossi senza preavviso nelle versioni future di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f4299-162">Therefore, events in the Debug channel may change or be removed in future versions of SQL Server without notice.</span></span>|  
  
 <span data-ttu-id="f4299-163">**Parola chiave**</span><span class="sxs-lookup"><span data-stu-id="f4299-163">**Keyword**</span></span>  
  
 <span data-ttu-id="f4299-164">Una parola chiave è un'applicazione specifica e abilita un raggruppamento più preciso di eventi correlati, ciò rende più facile specificare e recuperare un evento che si desidera utilizzare in una sessione.</span><span class="sxs-lookup"><span data-stu-id="f4299-164">A keyword is application specific and enables a finer-grained grouping of related events, which makes it easier for you to specify and retrieve an event that you want to use in a session.</span></span> <span data-ttu-id="f4299-165">È possibile utilizzare la seguente query ottenere informazioni sulla parola chiave:</span><span class="sxs-lookup"><span data-stu-id="f4299-165">You can use the following query to obtain keyword information.</span></span>  
  
```  
select map_value Keyword from sys.dm_xe_map_values  
where name = 'keyword_map'  
```  
  
> [!NOTE]  
>  <span data-ttu-id="f4299-166">Le parole chiave eseguono il mapping ravvicinato degli eventi Traccia SQL.</span><span class="sxs-lookup"><span data-stu-id="f4299-166">Keywords map closely to the current grouping of SQL Trace events.</span></span>  
  
### <a name="targets"></a><span data-ttu-id="f4299-167">Destinazioni</span><span class="sxs-lookup"><span data-stu-id="f4299-167">Targets</span></span>  
 <span data-ttu-id="f4299-168">Le destinazioni sono consumer di eventi.</span><span class="sxs-lookup"><span data-stu-id="f4299-168">Targets are event consumers.</span></span> <span data-ttu-id="f4299-169">Le destinazioni elaborano gli eventi, in modo sincrono nel thread che genera l'evento o in modo asincrono in un thread fornito dal sistema.</span><span class="sxs-lookup"><span data-stu-id="f4299-169">Targets process events, either synchronously on the thread that fires the event or asynchronously on a system provided thread.</span></span> <span data-ttu-id="f4299-170">Gli eventi estesi forniscono diverse destinazioni che è possibile utilizzare in base alle proprie esigenze per indirizzare l'output dell'evento.</span><span class="sxs-lookup"><span data-stu-id="f4299-170">Extended Events provides several targets that you can use as appropriate for directing event output.</span></span> <span data-ttu-id="f4299-171">Per ulteriori informazioni, vedere [SQL Server Extended Events Targets](../../database-engine/sql-server-extended-events-targets.md).</span><span class="sxs-lookup"><span data-stu-id="f4299-171">For more information, see [SQL Server Extended Events Targets](../../database-engine/sql-server-extended-events-targets.md).</span></span>  
  
### <a name="actions"></a><span data-ttu-id="f4299-172">Azioni</span><span class="sxs-lookup"><span data-stu-id="f4299-172">Actions</span></span>  
 <span data-ttu-id="f4299-173">Un'azione è una risposta o una serie di risposte a un evento a livello di programmazione.</span><span class="sxs-lookup"><span data-stu-id="f4299-173">An action is a programmatic response or series of responses to an event.</span></span> <span data-ttu-id="f4299-174">Le azioni sono associate a un evento e a ogni evento può essere associato un set univoco di azioni.</span><span class="sxs-lookup"><span data-stu-id="f4299-174">Actions are bound to an event, and each event may have a unique set of actions.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f4299-175">Le azioni destinate a un set specifico di eventi non possono essere associate a eventi sconosciuti.</span><span class="sxs-lookup"><span data-stu-id="f4299-175">Actions that are intended for a specific set of events cannot bind to unknown events.</span></span>  
  
 <span data-ttu-id="f4299-176">Un'azione associata a un evento viene richiamata in modo sincrono sul thread che ha attivato l'evento.</span><span class="sxs-lookup"><span data-stu-id="f4299-176">An action bound to an event is invoked synchronously on the thread that fired the event.</span></span> <span data-ttu-id="f4299-177">Vi sono molti tipi di azioni e hanno un'ampia gamma di funzionalità.</span><span class="sxs-lookup"><span data-stu-id="f4299-177">There are many types of actions and they have a wide range of capabilities.</span></span> <span data-ttu-id="f4299-178">Le azioni possono:</span><span class="sxs-lookup"><span data-stu-id="f4299-178">Actions can:</span></span>  
  
-   <span data-ttu-id="f4299-179">Acquisire un dump dello stack e verificare dati.</span><span class="sxs-lookup"><span data-stu-id="f4299-179">Capture a stack dump and inspect data.</span></span>  
  
-   <span data-ttu-id="f4299-180">Archiviare informazioni sullo stato in un contesto locale utilizzando l'archiviazione variabile.</span><span class="sxs-lookup"><span data-stu-id="f4299-180">Store state information in a local context using variable storage.</span></span>  
  
-   <span data-ttu-id="f4299-181">Aggregare dati dell'evento.</span><span class="sxs-lookup"><span data-stu-id="f4299-181">Aggregate event data.</span></span>  
  
-   <span data-ttu-id="f4299-182">Accodare dati ai dati dell'evento.</span><span class="sxs-lookup"><span data-stu-id="f4299-182">Append data to event data.</span></span>  
  
 <span data-ttu-id="f4299-183">Di seguito vengono riportati alcuni esempi tipici e noti di azioni:</span><span class="sxs-lookup"><span data-stu-id="f4299-183">Some typical and well known examples of actions are:</span></span>  
  
-   <span data-ttu-id="f4299-184">Dumper dello stack</span><span class="sxs-lookup"><span data-stu-id="f4299-184">Stack dumper</span></span>  
  
-   <span data-ttu-id="f4299-185">Rilevamento del piano di esecuzione (solo[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] )</span><span class="sxs-lookup"><span data-stu-id="f4299-185">Execution plan detection ([!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] only)</span></span>  
  
-   [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="f4299-186">raccolta di stack (solo[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] )</span><span class="sxs-lookup"><span data-stu-id="f4299-186">stack collection ([!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] only)</span></span>  
  
-   <span data-ttu-id="f4299-187">Esecuzione di calcoli di statistiche temporali</span><span class="sxs-lookup"><span data-stu-id="f4299-187">Run time statistics calculation</span></span>  
  
-   <span data-ttu-id="f4299-188">Raccolta di input utente in caso di eccezione</span><span class="sxs-lookup"><span data-stu-id="f4299-188">Gather user input on exception</span></span>  
  
### <a name="predicates"></a><span data-ttu-id="f4299-189">Predicati</span><span class="sxs-lookup"><span data-stu-id="f4299-189">Predicates</span></span>  
 <span data-ttu-id="f4299-190">I predicati rappresentano un set di regole logiche utilizzate per valutare gli eventi quando vengono elaborati.</span><span class="sxs-lookup"><span data-stu-id="f4299-190">Predicates are a set of logical rules that are used to evaluate events when they are processed.</span></span> <span data-ttu-id="f4299-191">In questo modo l'utente degli eventi estesi è in grado di acquisire selettivamente i dati dell'evento in base a criteri specifici.</span><span class="sxs-lookup"><span data-stu-id="f4299-191">This enables the Extended Events user to selectively capture event data based on specific criteria.</span></span>  
  
 <span data-ttu-id="f4299-192">I predicati possono archiviare i dati in un contesto locale che può essere usato per la creazione di predicati che restituiscono True ogni *n* minuti o ogni *n* volte che un evento viene generato.</span><span class="sxs-lookup"><span data-stu-id="f4299-192">Predicates can store data in a local context that can be used for creating predicates that return true once every *n* minutes or every *n* times that an event fires.</span></span> <span data-ttu-id="f4299-193">Questa archiviazione del contesto locale può essere utilizzata anche per aggiornare dinamicamente il predicato, sopprimendo con ciò le generazioni future dell'evento se l'evento contiene dati simili.</span><span class="sxs-lookup"><span data-stu-id="f4299-193">This local context storage can also be used to dynamically update the predicate, thereby suppressing future event firing if the events contain similar data.</span></span>  
  
 <span data-ttu-id="f4299-194">I predicati hanno la possibilità di recuperare informazioni sul contesto, ad esempio l'ID del thread, così come dati specifici sull'evento.</span><span class="sxs-lookup"><span data-stu-id="f4299-194">Predicates have the ability to retrieve context information, such as the thread ID, as well as event specific data.</span></span> <span data-ttu-id="f4299-195">I predicati sono valutati come espressioni booleane complete e supportano operazioni di corto circuito nel primo punto dove viene individuato che l'intera l'espressione è falsa.</span><span class="sxs-lookup"><span data-stu-id="f4299-195">Predicates are evaluated as full Boolean expressions, and support short circuiting at the first point where the entire expression is found to be false.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f4299-196">I predicati con effetti collaterali non possono essere valutati se una precedente verifica del predicato non riesce.</span><span class="sxs-lookup"><span data-stu-id="f4299-196">Predicates with side effects may not be evaluated if an earlier predicate check fails.</span></span>  
  
### <a name="types"></a><span data-ttu-id="f4299-197">Tipi</span><span class="sxs-lookup"><span data-stu-id="f4299-197">Types</span></span>  
 <span data-ttu-id="f4299-198">Poiché i dati sono una raccolta di byte, la lunghezza e le funzionalità della raccolta dei byte sono necessarie per interpretarli.</span><span class="sxs-lookup"><span data-stu-id="f4299-198">Because data is a collection of bytes strung together, the length and characteristics of the byte collection are required in order to interpret the data.</span></span> <span data-ttu-id="f4299-199">Queste informazioni sono incapsulate nell'oggetto Tipo.</span><span class="sxs-lookup"><span data-stu-id="f4299-199">This information is encapsulated in the Type object.</span></span> <span data-ttu-id="f4299-200">I tipi seguenti sono forniti per gli oggetti del pacchetto:</span><span class="sxs-lookup"><span data-stu-id="f4299-200">The following types are provided for package objects:</span></span>  
  
-   <span data-ttu-id="f4299-201">event</span><span class="sxs-lookup"><span data-stu-id="f4299-201">event</span></span>  
  
-   <span data-ttu-id="f4299-202">action</span><span class="sxs-lookup"><span data-stu-id="f4299-202">action</span></span>  
  
-   <span data-ttu-id="f4299-203">target</span><span class="sxs-lookup"><span data-stu-id="f4299-203">target</span></span>  
  
-   <span data-ttu-id="f4299-204">pred_source</span><span class="sxs-lookup"><span data-stu-id="f4299-204">pred_source</span></span>  
  
-   <span data-ttu-id="f4299-205">pred_compare</span><span class="sxs-lookup"><span data-stu-id="f4299-205">pred_compare</span></span>  
  
-   <span data-ttu-id="f4299-206">type</span><span class="sxs-lookup"><span data-stu-id="f4299-206">type</span></span>  
  
 <span data-ttu-id="f4299-207">Per altre informazioni, vedere [sys.dm_xe_objects &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-xe-objects-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f4299-207">For more information, see [sys.dm_xe_objects &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-xe-objects-transact-sql).</span></span>  
  
### <a name="maps"></a><span data-ttu-id="f4299-208">Mappe</span><span class="sxs-lookup"><span data-stu-id="f4299-208">Maps</span></span>  
 <span data-ttu-id="f4299-209">Una tabella della mappa esegue il mapping di un valore interno a una stringa e ciò consente a un utente di conoscere ciò che rappresenta il valore.</span><span class="sxs-lookup"><span data-stu-id="f4299-209">A map table maps an internal value to a string, which enables a user to know what the value represents.</span></span> <span data-ttu-id="f4299-210">Anziché essere in grado di ottenere solo un valore numerico, un utente può ottenere una descrizione significativa del valore interno.</span><span class="sxs-lookup"><span data-stu-id="f4299-210">Instead of only being able to obtain a numeric value, a user can get a meaningful description of the internal value.</span></span> <span data-ttu-id="f4299-211">Nella query seguente si illustra come ottenere valori della mappa.</span><span class="sxs-lookup"><span data-stu-id="f4299-211">The following query shows how to obtain map values.</span></span>  
  
```  
select map_key, map_value from sys.dm_xe_map_values  
where name = 'lock_mode'  
```  
  
 <span data-ttu-id="f4299-212">La query precedente produce l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="f4299-212">The preceding query produces the following output.</span></span>  
  
 `map_key     map_value`  
  
 `---------------------`  
  
 `0           NL`  
  
 `1           SCH_S`  
  
 `2           SCH_M`  
  
 `3           S`  
  
 `4           U`  
  
 `5           X`  
  
 `6           IS`  
  
 `7           IU`  
  
 `8           IX`  
  
 `9           SIU`  
  
 `10          SIX`  
  
 `11          UIX`  
  
 `12          BU`  
  
 `13          RS_S`  
  
 `14          RS_U`  
  
 `15          RI_NL`  
  
 `16          RI_S`  
  
 `17          RI_U`  
  
 `18          RI_X`  
  
 `19          RX_S`  
  
 `20          RX_U`  
  
 `21          RX_X`  
  
 `21          RX_X`  
  
 <span data-ttu-id="f4299-213">Utilizzare tabella come esempio, supponendo di avere una modalità di colonna denominata il cui valore è 5.</span><span class="sxs-lookup"><span data-stu-id="f4299-213">Using this table as an example, assume that you have a column named mode, and its value is 5.</span></span> <span data-ttu-id="f4299-214">La tabella indica che è stato eseguito il mapping di 5 a X, ovvero il tipo di blocco è Esclusivo.</span><span class="sxs-lookup"><span data-stu-id="f4299-214">The table indicates that 5 maps to X, which means the lock type is Exclusive.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4299-215">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f4299-215">See Also</span></span>  
 <span data-ttu-id="f4299-216">[SQL Server sessioni eventi estesi](sql-server-extended-events-sessions.md) </span><span class="sxs-lookup"><span data-stu-id="f4299-216">[SQL Server Extended Events Sessions](sql-server-extended-events-sessions.md) </span></span>  
 <span data-ttu-id="f4299-217">[Motore degli eventi estesi di SQL Server](sql-server-extended-events-engine.md) </span><span class="sxs-lookup"><span data-stu-id="f4299-217">[SQL Server Extended Events Engine](sql-server-extended-events-engine.md) </span></span>  
 [<span data-ttu-id="f4299-218">Destinazioni degli eventi estesi di SQL Server</span><span class="sxs-lookup"><span data-stu-id="f4299-218">SQL Server Extended Events Targets</span></span>](../../database-engine/sql-server-extended-events-targets.md)  
  
  
