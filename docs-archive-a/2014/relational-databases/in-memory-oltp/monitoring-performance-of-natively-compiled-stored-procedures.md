---
title: Monitoraggio delle prestazioni di stored procedure compilate in modo nativo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 55548cb2-77a8-4953-8b5a-f2778a4f13cf
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: d14d27cdc20c0f090c7a030efe05cfce4842f437
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725748"
---
# <a name="monitoring-performance-of-natively-compiled-stored-procedures"></a><span data-ttu-id="1fc45-102">Monitoraggio delle prestazioni di stored procedure compilate in modo nativo</span><span class="sxs-lookup"><span data-stu-id="1fc45-102">Monitoring Performance of Natively Compiled Stored Procedures</span></span>
  <span data-ttu-id="1fc45-103">In questo argomento viene illustrato come è possibile monitorare le prestazioni di stored procedure compilate in modo nativo</span><span class="sxs-lookup"><span data-stu-id="1fc45-103">This topic discusses how you can monitor the performance of natively compiled stored procedures</span></span>  
  
## <a name="using-extended-events"></a><span data-ttu-id="1fc45-104">Utilizzo degli eventi estesi</span><span class="sxs-lookup"><span data-stu-id="1fc45-104">Using Extended Events</span></span>  
 <span data-ttu-id="1fc45-105">Utilizzare l'evento esteso `sp_statement_completed` per tracciare l'esecuzione di una query.</span><span class="sxs-lookup"><span data-stu-id="1fc45-105">Use the `sp_statement_completed` extended event to trace execution of a query.</span></span> <span data-ttu-id="1fc45-106">Creare una sessione di eventi estesi con questo evento, applicando facoltativamente un filtro a OBJECT_ID per una stored procedure compilata in modo nativo. L'evento esteso viene generato dopo l'esecuzione di ogni query.</span><span class="sxs-lookup"><span data-stu-id="1fc45-106">Create an extended event session with this event, optionally with a filter on object_id for a particular natively compiled stored procedure, The extended event is raised after the execution of each query.</span></span> <span data-ttu-id="1fc45-107">Il tempo e la durata della CPU segnalati dagli eventi estesi indicano la quantità di CPU utilizzata dalla query e il tempo di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="1fc45-107">The CPU time and duration reported by the extended event indicate how much CPU the query used and the execution time.</span></span> <span data-ttu-id="1fc45-108">Una stored procedure compilata in modo nativo che utilizza un tempo di CPU elevato può presentare problemi di prestazioni.</span><span class="sxs-lookup"><span data-stu-id="1fc45-108">A natively compiled stored procedure that uses a lot of CPU time may have performance problems.</span></span>  
  
 <span data-ttu-id="1fc45-109">È possibile utilizzare `line_number` e `object_id` nell'evento esteso per esaminare la query.</span><span class="sxs-lookup"><span data-stu-id="1fc45-109">`line_number`, along with the `object_id` in the extended event can be used to investigate the query.</span></span> <span data-ttu-id="1fc45-110">È possibile utilizzare la query seguente per recuperare la definizione della routine.</span><span class="sxs-lookup"><span data-stu-id="1fc45-110">The following query can be used to retrieve the procedure definition.</span></span> <span data-ttu-id="1fc45-111">Il numero di riga può essere utilizzato per identificare la query all'interno della definizione:</span><span class="sxs-lookup"><span data-stu-id="1fc45-111">The line number can be used to identify the query within the definition:</span></span>  
  
```sql  
select [definition] from sys.sql_modules where object_id=object_id  
```  
  
 <span data-ttu-id="1fc45-112">Per ulteriori informazioni sull' `sp_statement_completed` evento esteso, vedere [come recuperare l'istruzione che ha causato un evento](https://blogs.msdn.com/b/extended_events/archive/2010/05/07/making-a-statement-how-to-retrieve-the-t-sql-statement-that-caused-an-event.aspx).</span><span class="sxs-lookup"><span data-stu-id="1fc45-112">For more information about the `sp_statement_completed` extended event, see [How to retrieve the statement that caused an event](https://blogs.msdn.com/b/extended_events/archive/2010/05/07/making-a-statement-how-to-retrieve-the-t-sql-statement-that-caused-an-event.aspx).</span></span>  
  
## <a name="using-data-management-views"></a><span data-ttu-id="1fc45-113">Utilizzo delle viste di gestione dati</span><span class="sxs-lookup"><span data-stu-id="1fc45-113">Using Data Management Views</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="1fc45-114">supporta la raccolta delle statistiche di esecuzione per le stored procedure compilate in modo nativo, sia a livello di routine sia a livello di query.</span><span class="sxs-lookup"><span data-stu-id="1fc45-114">supports collecting execution statistics for natively compiled stored procedures, both on the procedure level and the query level.</span></span> <span data-ttu-id="1fc45-115">La raccolta delle statistiche di esecuzione non è abilitata per impostazione predefinita a causa dell'impatto sulle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="1fc45-115">Collecting execution statistics is not enabled by default due to performance impact.</span></span>  
  
 <span data-ttu-id="1fc45-116">Per abilitare e disabilitare la raccolta di statistiche sulle stored procedure compilate in modo nativo, usare [sys.sp_xtp_control_proc_exec_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-xtp-control-proc-exec-stats-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1fc45-116">You can enable and disable statistics collection on natively compiled stored procedures using [sys.sp_xtp_control_proc_exec_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-xtp-control-proc-exec-stats-transact-sql).</span></span>  
  
 <span data-ttu-id="1fc45-117">Quando la raccolta delle statistiche è abilitata con [sys.sp_xtp_control_proc_exec_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-xtp-control-proc-exec-stats-transact-sql), è possibile usare [sys.dm_exec_procedure_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-procedure-stats-transact-sql) per monitorare le prestazioni di una stored procedure compilata in modo nativo.</span><span class="sxs-lookup"><span data-stu-id="1fc45-117">When statistics collection is enabled with [sys.sp_xtp_control_proc_exec_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-xtp-control-proc-exec-stats-transact-sql), you can use [sys.dm_exec_procedure_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-procedure-stats-transact-sql) to monitor performance of a natively compiled stored procedure.</span></span>  
  
 <span data-ttu-id="1fc45-118">Quando la raccolta delle statistiche è abilitata con [sys.sp_xtp_control_query_exec_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-xtp-control-query-exec-stats-transact-sql), è possibile usare [sys.dm_exec_query_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-query-stats-transact-sql) per monitorare le prestazioni di una stored procedure compilata in modo nativo.</span><span class="sxs-lookup"><span data-stu-id="1fc45-118">When statistics collection is enabled with [sys.sp_xtp_control_query_exec_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-xtp-control-query-exec-stats-transact-sql), you can use [sys.dm_exec_query_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-query-stats-transact-sql) to monitor performance of a natively compiled stored procedure.</span></span>  
  
 <span data-ttu-id="1fc45-119">All'inizio dell'operazione di raccolta, abilitare la raccolta delle statistiche.</span><span class="sxs-lookup"><span data-stu-id="1fc45-119">At the start of collection, enable statistics collection.</span></span> <span data-ttu-id="1fc45-120">Eseguire quindi la stored procedure compilata in modo nativo.</span><span class="sxs-lookup"><span data-stu-id="1fc45-120">Then, execute the natively compiled stored procedure.</span></span> <span data-ttu-id="1fc45-121">Alla fine dell'operazione di raccolta, disabilitare la raccolta delle statistiche.</span><span class="sxs-lookup"><span data-stu-id="1fc45-121">At the end of collection, disable statistics collection.</span></span> <span data-ttu-id="1fc45-122">Analizzare quindi le statistiche di esecuzione restituite dalle viste a gestione dinamica.</span><span class="sxs-lookup"><span data-stu-id="1fc45-122">Then, analyze the execution statistics returned by the DMVs.</span></span>  
  
 <span data-ttu-id="1fc45-123">Dopo avere raccolto le statistiche, è possibile interrogare le statistiche di esecuzione delle stored procedure compilate in modo nativo per individuare una routine con [sys.dm_exec_procedure_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-procedure-stats-transact-sql) e per individuare query con [sys.dm_exec_query_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-query-stats-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1fc45-123">After you collect statistics, the execution statistics for natively compiled stored procedures can be queried for a procedure with [sys.dm_exec_procedure_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-procedure-stats-transact-sql), and for queries with [sys.dm_exec_query_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-query-stats-transact-sql).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1fc45-124">Quando la raccolta delle statistiche è abilitata, per le stored procedure compilate in modo nativo il tempo del processo viene raccolto in millisecondi.</span><span class="sxs-lookup"><span data-stu-id="1fc45-124">For natively compiled stored procedures when statistics collection is enabled, worker time is collected in milliseconds.</span></span> <span data-ttu-id="1fc45-125">Se la query viene eseguita in meno di un millisecondo, il valore sarà 0.</span><span class="sxs-lookup"><span data-stu-id="1fc45-125">If the query executes in less than a millisecond, the value will be 0.</span></span> <span data-ttu-id="1fc45-126">Per le stored procedure compilate in modo nativo, il valore di **total_worker_time** non può essere accurato se più esecuzioni richiedono meno di 1 millisecondo.</span><span class="sxs-lookup"><span data-stu-id="1fc45-126">For natively compiled stored procedures, **total_worker_time** may not be accurate if many executions take less than 1 millisecond.</span></span>  
  
 <span data-ttu-id="1fc45-127">La query seguente restituisce i nomi delle routine e le statistiche di esecuzione per le stored procedure compilate in modo nativo nel database corrente, dopo la raccolta delle statistiche:</span><span class="sxs-lookup"><span data-stu-id="1fc45-127">The following query returns the procedure names and execution statistics for natively compiled stored procedures in the current database, after statistics collection:</span></span>  
  
```sql  
select object_id,  
       object_name(object_id) as 'object name',  
       cached_time,  
       last_execution_time,  
       execution_count,  
       total_worker_time,  
       last_worker_time,  
       min_worker_time,  
       max_worker_time,  
       total_elapsed_time,  
       last_elapsed_time,  
       min_elapsed_time,  
       max_elapsed_time   
from sys.dm_exec_procedure_stats  
where database_id=db_id() and object_id in (select object_id   
from sys.sql_modules where uses_native_compilation=1)  
order by total_worker_time desc  
```  
  
 <span data-ttu-id="1fc45-128">La query seguente restituisce il testo della query nonché le statistiche di esecuzione per tutte le query nelle stored procedure compilate in modo nativo nel database corrente per il quale sono state raccolte le statistiche, ordinate in base al tempo del processo, in ordine decrescente.</span><span class="sxs-lookup"><span data-stu-id="1fc45-128">The following query returns the query text as well as execution statistics for all queries in natively compiled stored procedures in the current database for which statistics have been collected, ordered by total worker time, in descending order:</span></span>  
  
```sql  
select st.objectid,   
       object_name(st.objectid) as 'object name',   
       SUBSTRING(st.text, (qs.statement_start_offset/2) + 1, ((qs.statement_end_offset-qs.statement_start_offset)/2) + 1) as 'query text',   
       qs.creation_time,  
       qs.last_execution_time,  
       qs.execution_count,  
       qs.total_worker_time,  
       qs.last_worker_time,  
       qs.min_worker_time,  
       qs.max_worker_time,  
       qs.total_elapsed_time,  
       qs.last_elapsed_time,  
       qs.min_elapsed_time,  
       qs.max_elapsed_time  
from sys.dm_exec_query_stats qs cross apply sys.dm_exec_sql_text(sql_handle) st  
where  st.dbid=db_id() and st.objectid in (select object_id   
from sys.sql_modules where uses_native_compilation=1)  
order by qs.total_worker_time desc  
```  
  
 <span data-ttu-id="1fc45-129">Le stored procedure compilate in modo nativo supportano SHOWPLAN_XML (piano di esecuzione stimato).</span><span class="sxs-lookup"><span data-stu-id="1fc45-129">Natively compiled stored procedures support SHOWPLAN_XML (estimated execution plan).</span></span> <span data-ttu-id="1fc45-130">Il piano di esecuzione stimato può essere utilizzato per esaminare il piano di query al fine di rilevare eventuali problemi relativi a piani non validi.</span><span class="sxs-lookup"><span data-stu-id="1fc45-130">The estimated execution plan can be used to inspect the query plan, to find any bad plan issues.</span></span> <span data-ttu-id="1fc45-131">I motivi comuni per i piani non validi sono:</span><span class="sxs-lookup"><span data-stu-id="1fc45-131">Common reasons for bad plans are:</span></span>  
  
-   <span data-ttu-id="1fc45-132">Le statistiche non sono state aggiornate prima della creazione della routine.</span><span class="sxs-lookup"><span data-stu-id="1fc45-132">Stats were not updated before the procedure was created.</span></span>  
  
-   <span data-ttu-id="1fc45-133">Indici mancanti</span><span class="sxs-lookup"><span data-stu-id="1fc45-133">Missing indexes</span></span>  
  
 <span data-ttu-id="1fc45-134">Showplan XML viene ottenuto mediante l'esecuzione dell'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)]seguente:</span><span class="sxs-lookup"><span data-stu-id="1fc45-134">Showplan XML is obtained by executing the following [!INCLUDE[tsql](../../includes/tsql-md.md)]:</span></span>  
  
```sql  
SET SHOWPLAN_XML ON  
GO  
EXEC my_proc   
GO  
SET SHOWPLAN_XML OFF  
GO  
```  
  
 <span data-ttu-id="1fc45-135">In alternativa, in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]selezionare il nome della routine e fare clic su **Visualizza piano di esecuzione stimato**.</span><span class="sxs-lookup"><span data-stu-id="1fc45-135">Alternatively, in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], select the procedure name and click **Display Estimated Execution Plan**.</span></span>  
  
 <span data-ttu-id="1fc45-136">Nel piano di esecuzione stimato per le stored procedure compilate in modo nativo vengono illustrati gli operatori e le espressioni delle query per le query nella routine.</span><span class="sxs-lookup"><span data-stu-id="1fc45-136">The estimated execution plan for natively compiled stored procedures shows the query operators and expressions for the queries in the procedure.</span></span> [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] <span data-ttu-id="1fc45-137">non supporta tutti gli attributi di SHOWPLAN_XML per le stored procedure compilate in modo nativo.</span><span class="sxs-lookup"><span data-stu-id="1fc45-137">does not support all SHOWPLAN_XML attributes for natively compiled stored procedures.</span></span> <span data-ttu-id="1fc45-138">Ad esempio, gli attributi correlati ai costi di Query Optimizer non fanno parte di SHOWPLAN_XML per la routine.</span><span class="sxs-lookup"><span data-stu-id="1fc45-138">For example, attributes related to query optimizer costing are not part of the SHOWPLAN_XML for the procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fc45-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1fc45-139">See Also</span></span>  
 [<span data-ttu-id="1fc45-140">Stored procedure compilate in modo nativo</span><span class="sxs-lookup"><span data-stu-id="1fc45-140">Natively Compiled Stored Procedures</span></span>](natively-compiled-stored-procedures.md)  
  
  
