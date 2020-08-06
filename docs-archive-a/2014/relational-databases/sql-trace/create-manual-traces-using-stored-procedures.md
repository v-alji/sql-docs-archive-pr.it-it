---
title: Creare tracce manuali usando stored procedure | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: f6f47fa2-7c17-41d4-9f69-9be144d56832
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e2840dced22ccdba8fe71cc87c05d7fd6fb4be58
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629754"
---
# <a name="create-manual-traces-using-stored-procedures"></a><span data-ttu-id="1519a-102">Creare tracce manuali utilizzando stored procedure</span><span class="sxs-lookup"><span data-stu-id="1519a-102">Create Manual Traces using Stored Procedures</span></span>
  <span data-ttu-id="1519a-103">In Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sono disponibili stored procedure di sistema [!INCLUDE[tsql](../../includes/tsql-md.md)] per la creazione di tracce per un'istanza di [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1519a-103">Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provides [!INCLUDE[tsql](../../includes/tsql-md.md)] system stored procedures to create traces on an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span> <span data-ttu-id="1519a-104">È possibile utilizzare tali stored procedure di sistema all'interno di applicazioni personalizzate per creare tracce in modo manuale anziché tramite [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1519a-104">These system stored procedures can be used from within your own applications to create traces manually, instead of using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span> <span data-ttu-id="1519a-105">Ciò consente di creare applicazioni personalizzate in grado di soddisfare esigenze aziendali specifiche.</span><span class="sxs-lookup"><span data-stu-id="1519a-105">This allows you to write custom applications specific to the needs of your enterprise.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1519a-106">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="1519a-106">In This Section</span></span>  
 <span data-ttu-id="1519a-107">Nella tabella seguente sono elencate le stored procedure di sistema per la traccia di un'istanza di [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1519a-107">The following table lists the system stored procedures for tracing an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span>  
  
|<span data-ttu-id="1519a-108">Stored procedure</span><span class="sxs-lookup"><span data-stu-id="1519a-108">Stored procedure</span></span>|<span data-ttu-id="1519a-109">Operazione eseguita</span><span class="sxs-lookup"><span data-stu-id="1519a-109">Task performed</span></span>|  
|----------------------|--------------------|  
|[<span data-ttu-id="1519a-110">sys.fn_trace_geteventinfo &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1519a-110">sys.fn_trace_geteventinfo &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-functions/sys-fn-trace-geteventinfo-transact-sql)|<span data-ttu-id="1519a-111">Restituisce informazioni sugli eventi inclusi in una traccia.</span><span class="sxs-lookup"><span data-stu-id="1519a-111">Returns information about events included in a trace.</span></span>|  
|[<span data-ttu-id="1519a-112">sys.fn_trace_getinfo &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1519a-112">sys.fn_trace_getinfo &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-functions/sys-fn-trace-getinfo-transact-sql)|<span data-ttu-id="1519a-113">Restituisce informazioni sulla traccia specificata o sulle tracce esistenti.</span><span class="sxs-lookup"><span data-stu-id="1519a-113">Returns information about a specified trace or all existing traces.</span></span>|  
|[<span data-ttu-id="1519a-114">sp_trace_create &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1519a-114">sp_trace_create &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-create-transact-sql)|<span data-ttu-id="1519a-115">Crea la definizione di una nuova traccia</span><span class="sxs-lookup"><span data-stu-id="1519a-115">Creates a trace definition.</span></span> <span data-ttu-id="1519a-116">nello stato arrestato.</span><span class="sxs-lookup"><span data-stu-id="1519a-116">The new trace will be in a stopped state.</span></span>|  
|[<span data-ttu-id="1519a-117">sp_trace_generateevent &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1519a-117">sp_trace_generateevent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-generateevent-transact-sql)|<span data-ttu-id="1519a-118">Crea un evento definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="1519a-118">Creates a user-defined event.</span></span>|  
|[<span data-ttu-id="1519a-119">sp_trace_setevent &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1519a-119">sp_trace_setevent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql)|<span data-ttu-id="1519a-120">Aggiunge una classe di evento o una colonna dati in una traccia oppure rimuove uno di questi elementi dalla traccia.</span><span class="sxs-lookup"><span data-stu-id="1519a-120">Adds an event class or data column to a trace, or removes one from it.</span></span>|  
|[<span data-ttu-id="1519a-121">sp_trace_setstatus &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1519a-121">sp_trace_setstatus &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-setstatus-transact-sql)|<span data-ttu-id="1519a-122">Avvia, arresta o chiude una traccia.</span><span class="sxs-lookup"><span data-stu-id="1519a-122">Starts, stops, or closes a trace.</span></span>|  
|[<span data-ttu-id="1519a-123">sys.fn_trace_getfilterinfo &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1519a-123">sys.fn_trace_getfilterinfo &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-functions/sys-fn-trace-getfilterinfo-transact-sql)|<span data-ttu-id="1519a-124">Restituisce informazioni sui filtri applicati a una traccia.</span><span class="sxs-lookup"><span data-stu-id="1519a-124">Returns information about filters applied to a trace.</span></span>|  
|[<span data-ttu-id="1519a-125">sp_trace_setfilter &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1519a-125">sp_trace_setfilter &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-setfilter-transact-sql)|<span data-ttu-id="1519a-126">Applica a una traccia un nuovo filtro o un filtro modificato.</span><span class="sxs-lookup"><span data-stu-id="1519a-126">Applies a new or modified filter to a trace.</span></span>|  
  
 <span data-ttu-id="1519a-127">**Per definire una traccia personalizzata tramite stored procedure**</span><span class="sxs-lookup"><span data-stu-id="1519a-127">**To define your own trace using stored procedures**</span></span>  
  
1.  <span data-ttu-id="1519a-128">Tramite **sp_trace_setevent**specificare gli eventi da acquisire.</span><span class="sxs-lookup"><span data-stu-id="1519a-128">Specify the events to capture using **sp_trace_setevent**.</span></span>  
  
2.  <span data-ttu-id="1519a-129">Specificare eventuali filtri per gli eventi.</span><span class="sxs-lookup"><span data-stu-id="1519a-129">Specify any event filters.</span></span> <span data-ttu-id="1519a-130">Per altre informazioni, vedere [Impostare un filtro di traccia &#40;Transact-SQL&#41;](../../ssms/agent/set-sql-server-alias-for-sql-server-agent-service-ssms.md).</span><span class="sxs-lookup"><span data-stu-id="1519a-130">For more information, see [Set a Trace Filter &#40;Transact-SQL&#41;](../../ssms/agent/set-sql-server-alias-for-sql-server-agent-service-ssms.md).</span></span>  
  
3.  <span data-ttu-id="1519a-131">Tramite **sp_trace_create** specificare la destinazione per i dati degli eventi acquisiti.</span><span class="sxs-lookup"><span data-stu-id="1519a-131">Specify the destination for the captured event data using **sp_trace_create**.</span></span>  
  
 <span data-ttu-id="1519a-132">Per un esempio dell'uso di stored procedure relative alla traccia, vedere [Creare una traccia &#40;Transact-SQL&#41;](../sql-trace/create-a-trace-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="1519a-132">For an example of using trace stored procedures, see [Create a Trace &#40;Transact-SQL&#41;](../sql-trace/create-a-trace-transact-sql.md).</span></span>  
  
 <span data-ttu-id="1519a-133">**Per impostare i valori predefiniti per la definizione della traccia**</span><span class="sxs-lookup"><span data-stu-id="1519a-133">**To set trace definition defaults**</span></span>  
  
 [<span data-ttu-id="1519a-134">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="1519a-134">SQL Server Profiler</span></span>](../../tools/sql-server-profiler/sql-server-profiler.md)  
  
 <span data-ttu-id="1519a-135">**Per impostare i valori predefiniti per la visualizzazione della traccia**</span><span class="sxs-lookup"><span data-stu-id="1519a-135">**To set trace display defaults**</span></span>  
  
 [<span data-ttu-id="1519a-136">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="1519a-136">SQL Server Profiler</span></span>](../../tools/sql-server-profiler/set-trace-display-defaults-sql-server-profiler.md)  
  
 <span data-ttu-id="1519a-137">**Per creare una traccia**</span><span class="sxs-lookup"><span data-stu-id="1519a-137">**To create a trace**</span></span>  
  
 [<span data-ttu-id="1519a-138">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="1519a-138">SQL Server Profiler</span></span>](../../tools/sql-server-profiler/create-a-trace-sql-server-profiler.md)  
  
 [<span data-ttu-id="1519a-139">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1519a-139">Transact-SQL</span></span>](../sql-trace/create-a-trace-transact-sql.md)  
  
 <span data-ttu-id="1519a-140">**Per aggiungere o rimuovere eventi da un modello di traccia**</span><span class="sxs-lookup"><span data-stu-id="1519a-140">**To add or remove events from a trace template**</span></span>  
  
 [<span data-ttu-id="1519a-141">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="1519a-141">SQL Server Profiler</span></span>](../../tools/sql-server-profiler/specify-events-and-data-columns-for-a-trace-file-sql-server-profiler.md)  
  
 [<span data-ttu-id="1519a-142">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1519a-142">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql)  
  
  
