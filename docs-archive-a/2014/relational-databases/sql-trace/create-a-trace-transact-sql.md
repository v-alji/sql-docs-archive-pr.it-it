---
title: Creare una traccia (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- traces [SQL Server], example
- traces [SQL Server], creating
ms.assetid: 79dd4254-e3c6-467a-bb6f-f99e51757e99
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 35644891b2dca8359d6dc68fbddb67288d241cb4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629755"
---
# <a name="create-a-trace-transact-sql"></a><span data-ttu-id="3e021-102">Creare una traccia (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="3e021-102">Create a Trace (Transact-SQL)</span></span>
  <span data-ttu-id="3e021-103">In questo argomento viene descritto come utilizzare stored procedure per creare una traccia.</span><span class="sxs-lookup"><span data-stu-id="3e021-103">This topic describes how to use stored procedures to create a trace.</span></span>  
  
### <a name="to-create-a-trace"></a><span data-ttu-id="3e021-104">Per creare una traccia</span><span class="sxs-lookup"><span data-stu-id="3e021-104">To create a trace</span></span>  
  
1.  <span data-ttu-id="3e021-105">Eseguire **sp_trace_create** con i parametri necessari per creare una nuova traccia.</span><span class="sxs-lookup"><span data-stu-id="3e021-105">Execute **sp_trace_create** with the required parameters to create a new trace.</span></span> <span data-ttu-id="3e021-106">La nuova traccia sarà in stato di arresto (*status* uguale a **0**).</span><span class="sxs-lookup"><span data-stu-id="3e021-106">The new trace will be in a stopped state (*status* is **0**).</span></span>  
  
2.  <span data-ttu-id="3e021-107">Eseguire **sp_trace_setevent** con i parametri necessari per selezionare gli eventi e le colonne da tracciare.</span><span class="sxs-lookup"><span data-stu-id="3e021-107">Execute **sp_trace_setevent** with the required parameters to select the events and columns to trace.</span></span>  
  
3.  <span data-ttu-id="3e021-108">Facoltativamente, eseguire **sp_trace_setfilter** per impostare qualsiasi filtro o una combinazione di filtri.</span><span class="sxs-lookup"><span data-stu-id="3e021-108">Optionally, execute **sp_trace_setfilter** to set any or a combination of filters.</span></span>  
  
     <span data-ttu-id="3e021-109">È possibile eseguire**sp_trace_setevent** e **sp_trace_setfilter** solo su tracce esistenti arrestate.</span><span class="sxs-lookup"><span data-stu-id="3e021-109">**sp_trace_setevent** and **sp_trace_setfilter** can be executed only on existing traces that are stopped.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="3e021-110">A differenza di quanto avviene con le normali stored procedure, i parametri di tutte le stored procedure di SQL Server Profiler (<strong>sp_trace_*xx*</strong>) sono rigidamente tipizzati e non supportano la conversione automatica del tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="3e021-110">Unlike regular stored procedures, parameters of all SQL Server Profiler stored procedures (<strong>sp_trace_*xx*</strong>) are strictly typed and do not support automatic data type conversion.</span></span> <span data-ttu-id="3e021-111">Se tali parametri non vengono chiamati con i tipi di dati corretti per i parametri di input, come indicato nella descrizione dell'argomento, la stored procedure restituisce un errore.</span><span class="sxs-lookup"><span data-stu-id="3e021-111">If these parameters are not called with the correct input parameter data types, as specified in the argument description, the stored procedure returns an error.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3e021-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="3e021-112">Example</span></span>  
 <span data-ttu-id="3e021-113">Nell'esempio di codice riportato di seguito viene illustrata la creazione di una traccia utilizzando [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3e021-113">The following code demonstrates creating a trace using [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="3e021-114">L'esempio è costituito da tre sezioni, relative alla creazione della traccia, al popolamento del file di traccia e all'arresto della traccia.</span><span class="sxs-lookup"><span data-stu-id="3e021-114">It is in three sections: creating the trace, populating the trace file, and stopping the trace.</span></span> <span data-ttu-id="3e021-115">Personalizzare la traccia aggiungendo gli eventi per cui si desidera eseguirla.</span><span class="sxs-lookup"><span data-stu-id="3e021-115">Customize the trace by adding the events that you want to trace.</span></span> <span data-ttu-id="3e021-116">Per l'elenco di eventi e colonne, vedere [sp_trace_setevent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="3e021-116">For the list of events and columns, see [sp_trace_setevent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql).</span></span>  
  
 <span data-ttu-id="3e021-117">Nel codice seguente viene creata una traccia, vengono aggiunti eventi, quindi viene avviata la traccia:</span><span class="sxs-lookup"><span data-stu-id="3e021-117">The following code creates a trace, adds events to the trace, and then starts the trace:</span></span>  
  
```  
DECLARE @RC int, @TraceID int, @on BIT  
EXEC @rc = sp_trace_create @TraceID output, 0, N'C:\SampleTrace'  
  
-- Select the return code to see if the trace creation was successful.  
SELECT RC = @RC, TraceID = @TraceID  
  
-- Set the events and data columns you need to capture.  
SELECT @on = 1  
  
-- 10 is RPC:Completed event. 1 is TextData column.   
EXEC sp_trace_setevent @TraceID, 10, 1, @on   
-- 13 is SQL:BatchStarting, 11 is LoginName  
EXEC sp_trace_setevent @TraceID, 13, 11, @on   
-- 13 is SQL:BatchStarting, 14 is StartTime  
EXEC sp_trace_setevent @TraceID, 13, 14, @on   
-- 12 is SQL:BatchCompleted, 15 is EndTime  
EXEC sp_trace_setevent @TraceID, 12, 15, @on   
-- 13 is SQL:BatchStarting, 1 is TextData  
EXEC sp_trace_setevent @TraceID, 13, 1, @on   
  
-- Set any filter. Not provided in this example  
--EXEC sp_trace_setfilter 1, 10, 0, 6, N'%Profiler%'  
  
-- Start Trace (status 1 = start)  
EXEC @RC = sp_trace_setstatus @TraceID, 1  
GO  
  
```  
  
## <a name="example"></a><span data-ttu-id="3e021-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="3e021-118">Example</span></span>  
 <span data-ttu-id="3e021-119">Dopo che la traccia è stata creata e avviata, eseguire il codice seguente per popolare la traccia con attività.</span><span class="sxs-lookup"><span data-stu-id="3e021-119">Now that the trace has been created and started, execute the following code to populate the trace with activity.</span></span>  
  
```  
SELECT * FROM master.sys.databases  
GO  
SELECT * FROM ::fn_trace_getinfo(default)  
GO  
  
```  
  
## <a name="example"></a><span data-ttu-id="3e021-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="3e021-120">Example</span></span>  
 <span data-ttu-id="3e021-121">La traccia può essere arrestata e riavviata in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="3e021-121">The trace can be stopped and restarted at any time.</span></span> <span data-ttu-id="3e021-122">In questo esempio eseguire il seguente codice per arrestare e chiudere la traccia e successivamente eliminarne la definizione.</span><span class="sxs-lookup"><span data-stu-id="3e021-122">In this example, execute the following code to stop the trace, close the trace, and delete the trace definition.</span></span>  
  
```  
DECLARE @TraceID int  
-- Populate a variable with the trace_id of the current trace  
SELECT  @TraceID = TraceID FROM ::fn_trace_getinfo(default) WHERE VALUE = N'C:\SampleTrace.trc'  
  
-- First stop the trace.   
EXEC sp_trace_setstatus @TraceID, 0  
  
-- Close and then delete its definition from SQL Server.   
EXEC sp_trace_setstatus @TraceID, 2  
  
```  
  
## <a name="example"></a><span data-ttu-id="3e021-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="3e021-123">Example</span></span>  
 <span data-ttu-id="3e021-124">Per esaminare il file di traccia, aprire il file SampleTrace.trc utilizzando [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3e021-124">To examine the trace file, open the SampleTrace.trc file using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e021-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3e021-125">See Also</span></span>  
 <span data-ttu-id="3e021-126">[Stored procedure di SQL Server Profiler &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sql-server-profiler-stored-procedures-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3e021-126">[SQL Server Profiler Stored Procedures &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sql-server-profiler-stored-procedures-transact-sql) </span></span>  
 <span data-ttu-id="3e021-127">[sp_trace_create &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-create-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3e021-127">[sp_trace_create &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-create-transact-sql) </span></span>  
 <span data-ttu-id="3e021-128">[sp_trace_setevent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3e021-128">[sp_trace_setevent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql) </span></span>  
 [<span data-ttu-id="3e021-129">sp_trace_setfilter &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3e021-129">sp_trace_setfilter &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-setfilter-transact-sql)  
  
  
