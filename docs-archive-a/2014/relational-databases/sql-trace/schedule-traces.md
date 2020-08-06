---
title: Pianificare tracce | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- filters [SQL Server], events
- traces [SQL Server]
- traces [SQL Server], stopping
- events [SQL Server], filters
- scheduling traces [SQL Server]
- traces [SQL Server], scheduling
- stopping traces
ms.assetid: 620b79db-924b-4502-8af3-39efcfca245d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: a698d88db35c84f7611293cf45807203c883865a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87634970"
---
# <a name="schedule-traces"></a><span data-ttu-id="5b6ff-102">Pianificare tracce</span><span class="sxs-lookup"><span data-stu-id="5b6ff-102">Schedule Traces</span></span>
  <span data-ttu-id="5b6ff-103">Esistono due modi per pianificare le tracce in Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5b6ff-103">There are two ways to schedule tracing in Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="5b6ff-104">È possibile:</span><span class="sxs-lookup"><span data-stu-id="5b6ff-104">You can:</span></span>  
  
-   <span data-ttu-id="5b6ff-105">Abilitare una data e un'ora di arresto della traccia</span><span class="sxs-lookup"><span data-stu-id="5b6ff-105">Enable a trace stop time.</span></span>  
  
-   <span data-ttu-id="5b6ff-106">Utilizzare [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent per pianificare una traccia.</span><span class="sxs-lookup"><span data-stu-id="5b6ff-106">Use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to schedule a trace.</span></span>  
  
## <a name="specifying-a-stop-time"></a><span data-ttu-id="5b6ff-107">Specifica di una data e un'ora di arresto</span><span class="sxs-lookup"><span data-stu-id="5b6ff-107">Specifying a Stop Time</span></span>  
 <span data-ttu-id="5b6ff-108">È possibile specificare una data e un'ora di arresto della traccia se si utilizzano le stored procedure di [!INCLUDE[tsql](../../includes/tsql-md.md)] o [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5b6ff-108">You can specify a trace stop time if you use [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedures or if you use [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span> <span data-ttu-id="5b6ff-109">L'impostazione della data e dell'ora di arresto deve essere eseguita durante la configurazione originale della traccia.</span><span class="sxs-lookup"><span data-stu-id="5b6ff-109">The stop time must be set when the trace is originally configured.</span></span>  
  
## <a name="scheduling-traces-by-using-sql-server-agent"></a><span data-ttu-id="5b6ff-110">Pianificazione di tracce tramite SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="5b6ff-110">Scheduling Traces by Using SQL Server Agent</span></span>  
 <span data-ttu-id="5b6ff-111">Il metodo migliore per pianificare le tracce consiste nell'avviare la traccia tramite [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent e quindi specificare una data e un'ora di arresto per la traccia tramite la stored procedure [!INCLUDE[tsql](../../includes/tsql-md.md)]**sp_trace_setstatus** o [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5b6ff-111">The best way to schedule traces is to use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to start the trace and then specify a trace stop time by using the [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedure **sp_trace_setstatus**, or [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
 <span data-ttu-id="5b6ff-112">**Per impostare un filtro basato sulla data e sull'ora di fine per una traccia**</span><span class="sxs-lookup"><span data-stu-id="5b6ff-112">**To set an end time filter for a trace**</span></span>  
  
 [<span data-ttu-id="5b6ff-113">Filtrare gli eventi in base all'ora di fine &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="5b6ff-113">Filter Events Based on the Event End Time &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/filter-events-based-on-the-event-end-time-sql-server-profiler.md)  
  
 [<span data-ttu-id="5b6ff-114">sp_trace_setstatus &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="5b6ff-114">sp_trace_setstatus &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-setstatus-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="5b6ff-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5b6ff-115">See Also</span></span>  
 [<span data-ttu-id="5b6ff-116">Automatizzazione delle attività amministrative &#40;SQL Server Agent&#41;</span><span class="sxs-lookup"><span data-stu-id="5b6ff-116">Automated Administration Tasks &#40;SQL Server Agent&#41;</span></span>](../../ssms/agent/sql-server-agent.md)  
  
  
