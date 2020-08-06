---
title: Considerazioni relative alla riproduzione di tracce | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- traces [SQL Server], replaying
- replaying traces
ms.assetid: 73fa339f-b71a-4be4-97ca-d4ae84c8b90b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0c2f030a0191596e40ef1ee9e2b0b2d4da34c773
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711283"
---
# <a name="considerations-for-replaying-traces-sql-server-profiler"></a><span data-ttu-id="ec12d-102">Considerazioni relative alla riproduzione di tracce (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="ec12d-102">Considerations for Replaying Traces (SQL Server Profiler)</span></span>
  [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="ec12d-103">non può riprodurre i tipi di tracce seguenti:</span><span class="sxs-lookup"><span data-stu-id="ec12d-103">cannot replay the following kinds of traces:</span></span>  
  
-   <span data-ttu-id="ec12d-104">Tracce contenenti replica transazionale e altre attività del log delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="ec12d-104">Traces that contain transactional replication and other transaction log activity.</span></span> <span data-ttu-id="ec12d-105">Questi eventi verranno ignorati.</span><span class="sxs-lookup"><span data-stu-id="ec12d-105">These events are skipped.</span></span> <span data-ttu-id="ec12d-106">Gli altri tipi di replica non contrassegnano il log delle transazioni e pertanto non subiscono alcun effetto.</span><span class="sxs-lookup"><span data-stu-id="ec12d-106">Other types of replication do not mark the transaction log so they are not affected.</span></span>  
  
-   <span data-ttu-id="ec12d-107">Tracce contenenti operazioni che coinvolgono identificatori univoci globali (GUID).</span><span class="sxs-lookup"><span data-stu-id="ec12d-107">Traces that contain operations that involve globally unique identifiers (GUID).</span></span> <span data-ttu-id="ec12d-108">Questi eventi verranno ignorati.</span><span class="sxs-lookup"><span data-stu-id="ec12d-108">These events will be skipped.</span></span>  
  
-   <span data-ttu-id="ec12d-109">Tracce contenenti operazioni su colonne **text**, **ntext**e **image** che coinvolgono l'utilità **bcp** , istruzioni BULK INSERT, READTEXT, WRITETEXT e UPDATETEXT e operazioni full-text.</span><span class="sxs-lookup"><span data-stu-id="ec12d-109">Traces that contain operations on **text**, **ntext**, and **image** columns involving the **bcp** utility, the BULK INSERT, READTEXT, WRITETEXT, and UPDATETEXT statements, and full-text operations.</span></span> <span data-ttu-id="ec12d-110">Questi eventi verranno ignorati.</span><span class="sxs-lookup"><span data-stu-id="ec12d-110">These events are skipped.</span></span>  
  
-   <span data-ttu-id="ec12d-111">Tracce contenenti operazioni di associazione della sessione, ovvero le stored procedure di sistema **sp_getbindtoken** e **sp_bindsession** .</span><span class="sxs-lookup"><span data-stu-id="ec12d-111">Traces that contain session binding: **sp_getbindtoken** and **sp_bindsession** system stored procedures.</span></span> <span data-ttu-id="ec12d-112">Questi eventi verranno ignorati.</span><span class="sxs-lookup"><span data-stu-id="ec12d-112">These events are skipped.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ec12d-113">Se non si usa il modello di riproduzione preconfigurato (**TSQL_Replay**) e non si acquisiscono tutti i dati necessari, la traccia non verrà riprodotta in [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ec12d-113">If you do not use the preconfigured replay template (**TSQL_Replay**), and do not capture all required data, [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] does not replay the trace.</span></span> <span data-ttu-id="ec12d-114">Per altre informazioni, vedere [Requisiti per la riproduzione](replay-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ec12d-114">For more information, see [Replay Requirements](replay-requirements.md).</span></span>  
  
 <span data-ttu-id="ec12d-115">Per informazioni sulle autorizzazioni necessarie per riprodurre una traccia, vedere [Autorizzazioni necessarie per l'esecuzione di SQL Server Profiler](sql-server-profiler.md).</span><span class="sxs-lookup"><span data-stu-id="ec12d-115">For information about what permissions are required to replay a trace, see [Permissions Required to Run SQL Server Profiler](sql-server-profiler.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec12d-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ec12d-116">See Also</span></span>  
 <span data-ttu-id="ec12d-117">[Utilità bcp](../bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="ec12d-117">[bcp Utility](../bcp-utility.md) </span></span>  
 <span data-ttu-id="ec12d-118">[Guida di riferimento alle classi di evento SQL Server](../../relational-databases/event-classes/sql-server-event-class-reference.md) </span><span class="sxs-lookup"><span data-stu-id="ec12d-118">[SQL Server Event Class Reference](../../relational-databases/event-classes/sql-server-event-class-reference.md) </span></span>  
 <span data-ttu-id="ec12d-119">[sp_getbindtoken &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-getbindtoken-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ec12d-119">[sp_getbindtoken &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-getbindtoken-transact-sql) </span></span>  
 <span data-ttu-id="ec12d-120">[sp_bindsession &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-bindsession-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ec12d-120">[sp_bindsession &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-bindsession-transact-sql) </span></span>  
 <span data-ttu-id="ec12d-121">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ec12d-121">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span></span>  
 <span data-ttu-id="ec12d-122">[READTEXT &#40;Transact-SQL&#41;](/sql/t-sql/queries/readtext-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ec12d-122">[READTEXT &#40;Transact-SQL&#41;](/sql/t-sql/queries/readtext-transact-sql) </span></span>  
 <span data-ttu-id="ec12d-123">[WRITETEXT &#40;Transact-SQL&#41;](/sql/t-sql/queries/writetext-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ec12d-123">[WRITETEXT &#40;Transact-SQL&#41;](/sql/t-sql/queries/writetext-transact-sql) </span></span>  
 [<span data-ttu-id="ec12d-124">UPDATETEXT &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ec12d-124">UPDATETEXT &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/queries/updatetext-transact-sql)  
  
  
