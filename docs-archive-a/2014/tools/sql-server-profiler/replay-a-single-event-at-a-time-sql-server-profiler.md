---
title: Riprodurre un solo evento alla volta (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- events [SQL Server], replaying single event at a time
- traces [SQL Server], replaying
- replaying traces
ms.assetid: 220fb192-9636-41a2-b15c-62af6cab8fff
author: stevestein
ms.author: sstein
ms.openlocfilehash: 457bc94d9d8eae470fb60b450d30441c07e676df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722071"
---
# <a name="replay-a-single-event-at-a-time-sql-server-profiler"></a><span data-ttu-id="fb04a-102">Riprodurre un solo evento alla volta (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="fb04a-102">Replay a Single Event at a Time (SQL Server Profiler)</span></span>
  <span data-ttu-id="fb04a-103">In questo argomento viene illustrato come riprodurre un evento alla volta in un file o tabella di traccia di riproduzione utilizzando [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fb04a-103">This topic describes how to replay one event at a time in a replay trace file or table by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="to-replay-a-single-event-at-a-time"></a><span data-ttu-id="fb04a-104">Per riprodurre un solo evento alla volta</span><span class="sxs-lookup"><span data-stu-id="fb04a-104">To replay a single event at a time</span></span>  
  
1.  <span data-ttu-id="fb04a-105">Aprire il file o la tabella di traccia che si desidera riprodurre.</span><span class="sxs-lookup"><span data-stu-id="fb04a-105">Open the trace file or trace table you want to replay.</span></span> <span data-ttu-id="fb04a-106">Per altre informazioni, vedere [Aprire un file di traccia &#40;SQL Server Profiler&#41;](open-a-trace-file-sql-server-profiler.md) o Ottimizzazione guidata [Aprire una tabella di traccia &#40;SQL Server Profiler&#41;](open-a-trace-table-sql-server-profiler.md).</span><span class="sxs-lookup"><span data-stu-id="fb04a-106">For more information, see [Open a Trace File &#40;SQL Server Profiler&#41;](open-a-trace-file-sql-server-profiler.md) or [Open a Trace Table &#40;SQL Server Profiler&#41;](open-a-trace-table-sql-server-profiler.md).</span></span>  
  
     <span data-ttu-id="fb04a-107">Verificare che il file o la tabella di traccia aperta contenga le classi di evento necessarie per la riproduzione.</span><span class="sxs-lookup"><span data-stu-id="fb04a-107">Make sure that the trace file or table you open contains the event classes necessary for replay.</span></span> <span data-ttu-id="fb04a-108">Per altre informazioni, vedere [Requisiti per la riproduzione](replay-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fb04a-108">For more information, see [Replay Requirements](replay-requirements.md).</span></span>  
  
2.  <span data-ttu-id="fb04a-109">Scegliere **Passaggio** dal menu **Riproduci**e quindi connettersi all'istanza del server in cui si vuole riprodurre la traccia.</span><span class="sxs-lookup"><span data-stu-id="fb04a-109">On the **Replay** menu, click **Step**, and connect to the server instance where you want to replay the trace.</span></span>  
  
3.  <span data-ttu-id="fb04a-110">Nella finestra di dialogo **Configurazione riproduzione** verificare le impostazioni e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="fb04a-110">In the **Replay Configuration** dialog box, verify the settings, and then click **OK**.</span></span> <span data-ttu-id="fb04a-111">Per altre informazioni sulla specifica delle impostazioni nella finestra di dialogo **Configurazione riproduzione**, vedere [Riprodurre un file di traccia &#40;SQL Server Profiler&#41;](replay-a-trace-file-sql-server-profiler.md) o [Riprodurre una tabella di traccia &#40;SQL Server Profiler&#41;](replay-a-trace-table-sql-server-profiler.md).</span><span class="sxs-lookup"><span data-stu-id="fb04a-111">For more information about specifying settings on the **Replay Configuration** dialog box, see [Replay a Trace File &#40;SQL Server Profiler&#41;](replay-a-trace-file-sql-server-profiler.md) or [Replay a Trace Table &#40;SQL Server Profiler&#41;](replay-a-trace-table-sql-server-profiler.md).</span></span>  
  
4.  <span data-ttu-id="fb04a-112">Per riprodurre il primo evento, fare clic su **OK** nella finestra di dialogo **Configurazione riproduzione** .</span><span class="sxs-lookup"><span data-stu-id="fb04a-112">To replay the first event, click **OK** in the **Replay Configuration** dialog box.</span></span>  
  
5.  <span data-ttu-id="fb04a-113">Per riprodurre gli eventi successivi, scegliere **Passaggio** dal menu **Riproduci**oppure premere F10.</span><span class="sxs-lookup"><span data-stu-id="fb04a-113">To replay subsequent events, on the **Replay** menu, click **Step**, or press F10.</span></span> <span data-ttu-id="fb04a-114">Fare di nuovo clic su **Passaggio** oppure premere di nuovo F10 per ogni evento.</span><span class="sxs-lookup"><span data-stu-id="fb04a-114">Repeat clicking **Step** or pressing F10 for each event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb04a-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fb04a-115">See Also</span></span>  
 <span data-ttu-id="fb04a-116">[Riprodurre le tracce](replay-traces.md) </span><span class="sxs-lookup"><span data-stu-id="fb04a-116">[Replay Traces](replay-traces.md) </span></span>  
 [<span data-ttu-id="fb04a-117">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="fb04a-117">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
