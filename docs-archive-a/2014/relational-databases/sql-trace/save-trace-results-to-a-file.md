---
title: Salvare i risultati della traccia in un file | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: 74f80667-62f3-4e14-bb1a-f0c2b6ef3402
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 644fc812bbb4863c336ff2f53f5b2d67ee0a4d5e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624545"
---
# <a name="save-trace-results-to-a-file"></a><span data-ttu-id="dfc2e-102">Salvare i risultati della traccia in un file</span><span class="sxs-lookup"><span data-stu-id="dfc2e-102">Save Trace Results to a File</span></span>
  <span data-ttu-id="dfc2e-103">È possibile salvare i risultati della traccia in un file.</span><span class="sxs-lookup"><span data-stu-id="dfc2e-103">You can save trace results to a file.</span></span> <span data-ttu-id="dfc2e-104">Un file di traccia è un file nel quale vengono scritti i risultati della traccia.</span><span class="sxs-lookup"><span data-stu-id="dfc2e-104">A trace file is a file where the trace results are written.</span></span> <span data-ttu-id="dfc2e-105">Un file di traccia può trovarsi in una directory locale (ad esempio C:\\*nomecartella*\\*nomefile.trc*) o in una directory di rete (ad esempio \\\nomecomputer\nomecondivisione\nomefile.trc).</span><span class="sxs-lookup"><span data-stu-id="dfc2e-105">A trace file can be located either in a local directory (such as C:\\*foldername*\\*filename.trc*) or a network directory (such as \\\computername\sharename\filename.trc).</span></span>  
  
 <span data-ttu-id="dfc2e-106">I file di traccia consentono di:</span><span class="sxs-lookup"><span data-stu-id="dfc2e-106">You can use the trace files to do the following:</span></span>  
  
-   <span data-ttu-id="dfc2e-107">Riprodurre le tracce</span><span class="sxs-lookup"><span data-stu-id="dfc2e-107">Replay traces</span></span>  
  
-   <span data-ttu-id="dfc2e-108">Controllare il funzionamento di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dfc2e-108">Audit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span></span>  
  
-   <span data-ttu-id="dfc2e-109">Condurre analisi sulle prestazioni</span><span class="sxs-lookup"><span data-stu-id="dfc2e-109">Conduct performance analysis</span></span>  
  
-   <span data-ttu-id="dfc2e-110">Correlare eventi di traccia a contatori delle prestazioni per migliorare il rilevamento dei problemi</span><span class="sxs-lookup"><span data-stu-id="dfc2e-110">Correlate trace events with performance counters to enhance problem detection</span></span>  
  
-   <span data-ttu-id="dfc2e-111">Eseguire analisi di Ottimizzazione guidata motore di database</span><span class="sxs-lookup"><span data-stu-id="dfc2e-111">Perform Database Engine Tuning Advisor analysis</span></span>  
  
-   <span data-ttu-id="dfc2e-112">Eseguire l'ottimizzazione delle query</span><span class="sxs-lookup"><span data-stu-id="dfc2e-112">Carry out query optimization</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="dfc2e-113">Salva i risultati della traccia in un file quando vengono specificati un percorso e un nome file per l' **@tracefile** argomento della **sp_trace_create**stored procedure.</span><span class="sxs-lookup"><span data-stu-id="dfc2e-113">saves trace results to a file when a path and file name are specified for the **@tracefile** argument of the stored procedure **sp_trace_create**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dfc2e-114">Se nella stored procedure **sp_trace_create** si specifica un percorso per il salvataggio del file di traccia, è necessario che la directory sia accessibile al server.</span><span class="sxs-lookup"><span data-stu-id="dfc2e-114">If a path is specified to the **sp_trace_create** stored procedure for saving the trace file, the directory must be accessible to the server.</span></span> <span data-ttu-id="dfc2e-115">Si noti anche che se viene specificata una directory locale in **sp_trace_create**, si tratta di una directory locale nel computer server.</span><span class="sxs-lookup"><span data-stu-id="dfc2e-115">Also be aware that if a local directory is specified to **sp_trace_create**, it is a local directory on the server computer.</span></span>  
  
 <span data-ttu-id="dfc2e-116">[!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] consente di salvare i risultati della traccia in un file o in una tabella.</span><span class="sxs-lookup"><span data-stu-id="dfc2e-116">If [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] is used, it allows you to save trace results to a file or to a table.</span></span> <span data-ttu-id="dfc2e-117">Il salvataggio in una tabella offre lo stesso accesso del salvataggio in un file e in più consente l'esecuzione di query sulla tabella per la ricerca di eventi specifici.</span><span class="sxs-lookup"><span data-stu-id="dfc2e-117">Saving trace results to a table allows the same access as saving the trace to a file plus you can query the table to search for specific events.</span></span>  
  
 <span data-ttu-id="dfc2e-118">Per altre informazioni sul salvataggio dei risultati della traccia, vedere [Salvare i risultati della traccia in una tabella &#40;SQL Server Profiler&#41;](../../tools/sql-server-profiler/save-trace-results-to-a-table-sql-server-profiler.md) e [Salvare i risultati della traccia in un file &#40;SQL Server Profiler&#41;](../../tools/sql-server-profiler/save-trace-results-to-a-file-sql-server-profiler.md).</span><span class="sxs-lookup"><span data-stu-id="dfc2e-118">For more information about saving trace results, see [Save Trace Results to a Table &#40;SQL Server Profiler&#41;](../../tools/sql-server-profiler/save-trace-results-to-a-table-sql-server-profiler.md) and [Save Trace Results to a File &#40;SQL Server Profiler&#41;](../../tools/sql-server-profiler/save-trace-results-to-a-file-sql-server-profiler.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfc2e-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dfc2e-119">See Also</span></span>  
 <span data-ttu-id="dfc2e-120">[sp_trace_create &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-create-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="dfc2e-120">[sp_trace_create &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-create-transact-sql) </span></span>  
 <span data-ttu-id="dfc2e-121">[Creare una traccia &#40;Transact-SQL&#41;](../sql-trace/create-a-trace-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="dfc2e-121">[Create a Trace &#40;Transact-SQL&#41;](../sql-trace/create-a-trace-transact-sql.md) </span></span>  
 [<span data-ttu-id="dfc2e-122">Creare una traccia &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="dfc2e-122">Create a Trace &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/create-a-trace-sql-server-profiler.md)  
  
  
