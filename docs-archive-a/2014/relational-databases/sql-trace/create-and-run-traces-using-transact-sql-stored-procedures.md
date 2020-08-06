---
title: Creare ed eseguire tracce usando stored procedure Transact-SQL | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: 80347417-338d-4bea-8885-91fae5181cfe
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2905ce2822598502ef6337d1a083fb6fde001c2d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629756"
---
# <a name="create-and-run-traces-using-transact-sql-stored-procedures"></a><span data-ttu-id="4fba4-102">Creare ed eseguire tracce utilizzando stored procedure Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4fba4-102">Create and Run Traces Using Transact-SQL Stored Procedures</span></span>
  <span data-ttu-id="4fba4-103">Il processo di traccia eseguito tramite Traccia SQL varia a seconda che la traccia venga creata ed eseguita utilizzando Microsoft [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] o le stored procedure di sistema.</span><span class="sxs-lookup"><span data-stu-id="4fba4-103">The process of tracing with SQL Trace varies depending on whether you create and run your trace by using Microsoft [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] or by using system stored procedures.</span></span>  
  
 <span data-ttu-id="4fba4-104">In alternativa a [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], è possibile utilizzare le stored procedure di sistema [!INCLUDE[tsql](../../includes/tsql-md.md)] per creare ed eseguire le tracce.</span><span class="sxs-lookup"><span data-stu-id="4fba4-104">As an alternative to [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], you can use [!INCLUDE[tsql](../../includes/tsql-md.md)] system stored procedures to create and run traces.</span></span> <span data-ttu-id="4fba4-105">Il processo di traccia eseguito tramite le stored procedure di sistema include i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="4fba4-105">The process of tracing by using system stored procedures is as follows:</span></span>  
  
1.  <span data-ttu-id="4fba4-106">Creare una traccia usando **sp_trace_create**.</span><span class="sxs-lookup"><span data-stu-id="4fba4-106">Create a trace by using **sp_trace_create**.</span></span>  
  
2.  <span data-ttu-id="4fba4-107">Aggiungere gli eventi con **sp_trace_setevent**.</span><span class="sxs-lookup"><span data-stu-id="4fba4-107">Add events with **sp_trace_setevent**.</span></span>  
  
3.  <span data-ttu-id="4fba4-108">(Facoltativo) Impostare un filtro con **sp_trace_setfilter**.</span><span class="sxs-lookup"><span data-stu-id="4fba4-108">(Optional) Set a filter with **sp_trace_setfilter**.</span></span>  
  
4.  <span data-ttu-id="4fba4-109">Avviare la traccia con **sp_trace_setstatus**.</span><span class="sxs-lookup"><span data-stu-id="4fba4-109">Start the trace with **sp_trace_setstatus**.</span></span>  
  
5.  <span data-ttu-id="4fba4-110">Arrestare la traccia con **sp_trace_setstatus**.</span><span class="sxs-lookup"><span data-stu-id="4fba4-110">Stop the trace with **sp_trace_setstatus**.</span></span>  
  
6.  <span data-ttu-id="4fba4-111">Chiudere la traccia con **sp_trace_setstatus**.</span><span class="sxs-lookup"><span data-stu-id="4fba4-111">Close the trace with **sp_trace_setstatus**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4fba4-112">Mediante le stored procedure di sistema di [!INCLUDE[tsql](../../includes/tsql-md.md)] viene creata una traccia sul lato server, evitando in tal modo la perdita di eventi a condizione che lo spazio su disco sia sufficiente e non si verifichino errori di scrittura.</span><span class="sxs-lookup"><span data-stu-id="4fba4-112">Using [!INCLUDE[tsql](../../includes/tsql-md.md)] system stored procedures creates a server-side trace, which guarantees that no events will be lost as long as there is space on the disk and no write errors occur.</span></span> <span data-ttu-id="4fba4-113">Se il disco si riempie o si verifica un errore, l'esecuzione dell'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] continua ma la traccia viene arrestata.</span><span class="sxs-lookup"><span data-stu-id="4fba4-113">If the disk becomes full or the disk fails, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance continues to run, but tracing stops.</span></span> <span data-ttu-id="4fba4-114">Se l'opzione **c2 audit mode** è impostata e si verifica un errore di scrittura, la traccia viene arrestata e l'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] viene chiusa.</span><span class="sxs-lookup"><span data-stu-id="4fba4-114">If the **c2 audit mode** is set, and there is a write failure, tracing stops and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance shuts down.</span></span> <span data-ttu-id="4fba4-115">Per altre informazioni sull'impostazione **c2 audit mode** , vedere [Opzione di configurazione del server c2 audit mode](../../database-engine/configure-windows/c2-audit-mode-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="4fba4-115">For more information about the **c2 audit mode** setting, see [c2 audit mode Server Configuration Option](../../database-engine/configure-windows/c2-audit-mode-server-configuration-option.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4fba4-116">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="4fba4-116">In This Section</span></span>  
  
|<span data-ttu-id="4fba4-117">Argomento</span><span class="sxs-lookup"><span data-stu-id="4fba4-117">Topic</span></span>|<span data-ttu-id="4fba4-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4fba4-118">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="4fba4-119">Ottimizzare l'uso di Traccia SQL</span><span class="sxs-lookup"><span data-stu-id="4fba4-119">Optimize SQL Trace</span></span>](sql-trace.md)|<span data-ttu-id="4fba4-120">Contiene informazioni sulle strategie per ridurre gli effetti della traccia sulle prestazioni del sistema.</span><span class="sxs-lookup"><span data-stu-id="4fba4-120">Contains information about ways you can reduce the effects of tracing on system performance.</span></span>|  
|[<span data-ttu-id="4fba4-121">Filtrare una traccia</span><span class="sxs-lookup"><span data-stu-id="4fba4-121">Filter a Trace</span></span>](filter-a-trace.md)|<span data-ttu-id="4fba4-122">Contiene informazioni sull'utilizzo di filtri per la traccia.</span><span class="sxs-lookup"><span data-stu-id="4fba4-122">Contains information about using filters for tracing.</span></span>|  
|[<span data-ttu-id="4fba4-123">Limitare le dimensioni di file di traccia e tabelle</span><span class="sxs-lookup"><span data-stu-id="4fba4-123">Limit Trace File and Table Sizes</span></span>](limit-trace-file-and-table-sizes.md)|<span data-ttu-id="4fba4-124">Contiene informazioni sulla procedura per limitare le dimensioni di file e tabelle in cui sono registrati i dati di traccia.</span><span class="sxs-lookup"><span data-stu-id="4fba4-124">Contains information about how to limit the size of files and tables where trace data is written.</span></span> <span data-ttu-id="4fba4-125">Si noti che è possibile registrare informazioni di traccia nelle tabelle solo tramite [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4fba4-125">Note that only [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] can write trace information to tables.</span></span>|  
|[<span data-ttu-id="4fba4-126">Pianificare tracce</span><span class="sxs-lookup"><span data-stu-id="4fba4-126">Schedule Traces</span></span>](schedule-traces.md)|<span data-ttu-id="4fba4-127">Contiene informazioni sull'impostazione dell'ora di inizio e di fine della traccia.</span><span class="sxs-lookup"><span data-stu-id="4fba4-127">Contains information about how to set the start time and the end time for tracing.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4fba4-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4fba4-128">See Also</span></span>  
 <span data-ttu-id="4fba4-129">[sp_trace_create &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-create-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4fba4-129">[sp_trace_create &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-create-transact-sql) </span></span>  
 <span data-ttu-id="4fba4-130">[sp_trace_setevent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4fba4-130">[sp_trace_setevent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql) </span></span>  
 <span data-ttu-id="4fba4-131">[sp_trace_setfilter &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setfilter-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4fba4-131">[sp_trace_setfilter &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setfilter-transact-sql) </span></span>  
 [<span data-ttu-id="4fba4-132">sp_trace_setstatus &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4fba4-132">sp_trace_setstatus &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-setstatus-transact-sql)  
  
  
