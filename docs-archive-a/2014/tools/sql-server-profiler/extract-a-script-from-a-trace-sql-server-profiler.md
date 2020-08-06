---
title: Estrarre uno script da una traccia (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- scripts [SQL Server], traces
- extracting script from trace [SQL Server]
ms.assetid: 431126a6-ff91-4818-8763-4442152bd571
author: stevestein
ms.author: sstein
ms.openlocfilehash: f6633fafb8a39b189093044ef39694afa601af7c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711247"
---
# <a name="extract-a-script-from-a-trace-sql-server-profiler"></a><span data-ttu-id="03387-102">Estrarre uno script da una traccia (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="03387-102">Extract a Script from a Trace (SQL Server Profiler)</span></span>
  <span data-ttu-id="03387-103">In questo argomento vengono descritti l'estrazione di eventi [!INCLUDE[tsql](../../includes/tsql-md.md)] da un file o da una tabella di traccia e il relativo salvataggio come file script [!INCLUDE[tsql](../../includes/tsql-md.md)] tramite [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="03387-103">This topic describes how to extract [!INCLUDE[tsql](../../includes/tsql-md.md)] events from a trace file or table and save them as a [!INCLUDE[tsql](../../includes/tsql-md.md)] script file by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="to-extract-a-transact-sql-script-from-a-trace-file-or-table"></a><span data-ttu-id="03387-104">Per estrarre uno script Transact-SQL da un file o una tabella di traccia</span><span class="sxs-lookup"><span data-stu-id="03387-104">To extract a Transact-SQL script from a trace file or table</span></span>  
  
1.  <span data-ttu-id="03387-105">Aprire il file o la tabella di traccia contenente gli eventi [!INCLUDE[tsql](../../includes/tsql-md.md)] che si desidera salvare in un file script [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="03387-105">Open a trace file or table that contains [!INCLUDE[tsql](../../includes/tsql-md.md)] events that you want to save to a [!INCLUDE[tsql](../../includes/tsql-md.md)] script file.</span></span> <span data-ttu-id="03387-106">Per altre informazioni, vedere [Aprire un file di traccia &#40;SQL Server Profiler&#41;](open-a-trace-file-sql-server-profiler.md) o Ottimizzazione guidata [Aprire una tabella di traccia &#40;SQL Server Profiler&#41;](open-a-trace-table-sql-server-profiler.md).</span><span class="sxs-lookup"><span data-stu-id="03387-106">For more information, see [Open a Trace File &#40;SQL Server Profiler&#41;](open-a-trace-file-sql-server-profiler.md) or [Open a Trace Table &#40;SQL Server Profiler&#41;](open-a-trace-table-sql-server-profiler.md).</span></span>  
  
2.  <span data-ttu-id="03387-107">Nel menu **File** scegliere **Esporta**, **Estrai eventi di SQL Server**e quindi **Estrai eventi Transact-SQL**.</span><span class="sxs-lookup"><span data-stu-id="03387-107">On the **File** menu, point to **Export**, point to **Extract SQL Server Events**, and then click **Extract Transact-SQL Events**.</span></span>  
  
3.  <span data-ttu-id="03387-108">Nella finestra di dialogo **Salva con nome** digitare un nome per il file [!INCLUDE[tsql](../../includes/tsql-md.md)] e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="03387-108">In the **Save As** dialog box, type a name for the [!INCLUDE[tsql](../../includes/tsql-md.md)] file, and click **Save**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03387-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="03387-109">See Also</span></span>  
 [<span data-ttu-id="03387-110">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="03387-110">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
