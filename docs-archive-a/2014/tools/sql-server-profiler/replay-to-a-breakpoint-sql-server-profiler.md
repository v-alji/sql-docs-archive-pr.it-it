---
title: Riprodurre fino a un punto di interruzione (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- breakpoints [SQL Server]
- traces [SQL Server], replaying
ms.assetid: 3caf751e-df3b-40c7-b5e8-4490ae178e0c
author: stevestein
ms.author: sstein
ms.openlocfilehash: f33b6862847b042a2613d8c2aa035dd5805493ca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722052"
---
# <a name="replay-to-a-breakpoint-sql-server-profiler"></a><span data-ttu-id="f9b4f-102">Riprodurre fino a un punto di interruzione (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="f9b4f-102">Replay to a Breakpoint (SQL Server Profiler)</span></span>
  <span data-ttu-id="f9b4f-103">In questo argomento viene illustrato come impostare i punti di interruzione in un file o in una tabella di traccia che si desidera riprodurre tramite [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f9b4f-103">This topic describes how to set breakpoints in a trace file or table that you want to replay by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span> <span data-ttu-id="f9b4f-104">L'impostazione di punti di interruzione in un file o in una tabella di traccia prima dell'avvio della riproduzione della traccia consente di sospendere la traccia in corrispondenza di eventi specifici.</span><span class="sxs-lookup"><span data-stu-id="f9b4f-104">Setting breakpoints in a trace file or table before you start to replay the trace, enables you to pause replay of the trace at specific events.</span></span> <span data-ttu-id="f9b4f-105">L'utilizzo di punti di interruzione durante la riproduzione di una traccia supporta il debug, in quanto è possibile suddividere la riproduzione di script di traccia lunghi in segmenti più brevi che possono essere analizzati in modo incrementale.</span><span class="sxs-lookup"><span data-stu-id="f9b4f-105">Using breakpoints while replaying a trace supports debugging because you can break the replay of long trace scripts into short segments that can be analyzed incrementally.</span></span>  
  
### <a name="to-replay-to-a-breakpoint"></a><span data-ttu-id="f9b4f-106">Per eseguire la riproduzione fino a un punto di interruzione</span><span class="sxs-lookup"><span data-stu-id="f9b4f-106">To replay to a breakpoint</span></span>  
  
1.  <span data-ttu-id="f9b4f-107">Aprire il file o la tabella di traccia che si desidera riprodurre.</span><span class="sxs-lookup"><span data-stu-id="f9b4f-107">Open the trace file or trace table you want to replay.</span></span> <span data-ttu-id="f9b4f-108">Per altre informazioni, vedere [Aprire un file di traccia &#40;SQL Server Profiler&#41;](open-a-trace-file-sql-server-profiler.md) o Ottimizzazione guidata [Aprire una tabella di traccia &#40;SQL Server Profiler&#41;](open-a-trace-table-sql-server-profiler.md).</span><span class="sxs-lookup"><span data-stu-id="f9b4f-108">For more information, see [Open a Trace File &#40;SQL Server Profiler&#41;](open-a-trace-file-sql-server-profiler.md) or [Open a Trace Table &#40;SQL Server Profiler&#41;](open-a-trace-table-sql-server-profiler.md).</span></span>  
  
     <span data-ttu-id="f9b4f-109">Verificare che il file o la tabella di traccia aperta contenga le classi di evento necessarie per la riproduzione.</span><span class="sxs-lookup"><span data-stu-id="f9b4f-109">Make sure that the trace file or table you open contains the event classes necessary for replay.</span></span> <span data-ttu-id="f9b4f-110">Per altre informazioni, vedere [Requisiti per la riproduzione](replay-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f9b4f-110">For more information, see [Replay Requirements](replay-requirements.md).</span></span>  
  
2.  <span data-ttu-id="f9b4f-111">Nella finestra di traccia fare clic su un evento che si desidera utilizzare come punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="f9b4f-111">In the trace window, click an event that you want to use as a breakpoint.</span></span> <span data-ttu-id="f9b4f-112">Per impostare un punto di interruzione, utilizzare uno dei tre modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="f9b4f-112">Use one of the following three methods to set a breakpoint:</span></span>  
  
    -   <span data-ttu-id="f9b4f-113">Premere F9.</span><span class="sxs-lookup"><span data-stu-id="f9b4f-113">Press F9.</span></span>  
  
    -   <span data-ttu-id="f9b4f-114">Scegliere **Imposta/Rimuovi punto di interruzione** dal menu **Riproduci**.</span><span class="sxs-lookup"><span data-stu-id="f9b4f-114">On the **Replay** menu, click **Toggle Breakpoint**.</span></span>  
  
    -   <span data-ttu-id="f9b4f-115">Fare clic con il pulsante destro del mouse sull'evento e quindi scegliere **Imposta/Rimuovi punto di interruzione**.</span><span class="sxs-lookup"><span data-stu-id="f9b4f-115">Right-click the event, and then click **Toggle Breakpoint**.</span></span>  
  
     <span data-ttu-id="f9b4f-116">Accanto all'evento di traccia selezionato verrà visualizzato un pallino rosso, per indicare che si tratta del punto di interruzione della traccia.</span><span class="sxs-lookup"><span data-stu-id="f9b4f-116">A red bullet appears next to the selected trace event, indicating that it is the trace breakpoint.</span></span>  
  
     <span data-ttu-id="f9b4f-117">Ripetere il passaggio per impostare più punti di interruzione.</span><span class="sxs-lookup"><span data-stu-id="f9b4f-117">Repeat this step to set several breakpoints.</span></span>  
  
3.  <span data-ttu-id="f9b4f-118">Scegliere **Avvia** dal menu **Riproduci**e quindi connettersi al server in cui si vuole riprodurre la traccia.</span><span class="sxs-lookup"><span data-stu-id="f9b4f-118">On the **Replay** menu, click **Start**, and connect to the server where you want to replay the trace.</span></span>  
  
4.  <span data-ttu-id="f9b4f-119">Nella finestra di dialogo **Configurazione riproduzione** verificare le impostazioni e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="f9b4f-119">In the **Replay Configuration** dialog box, verify the settings, and then click **OK**.</span></span>  
  
     <span data-ttu-id="f9b4f-120">La riproduzione verrà avviata e quindi verrà sospesa in corrispondenza del punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="f9b4f-120">The replay starts, pausing when the breakpoint is reached.</span></span>  
  
5.  <span data-ttu-id="f9b4f-121">Premere F5 per riprendere la riproduzione e passare al punto di interruzione successivo.</span><span class="sxs-lookup"><span data-stu-id="f9b4f-121">Press F5 to resume the replay and proceed to the next breakpoint.</span></span>  
  
6.  <span data-ttu-id="f9b4f-122">Ripetere l'operazione descritta al passaggio 5 fino alla fine della traccia.</span><span class="sxs-lookup"><span data-stu-id="f9b4f-122">Repeat Step 5 through the end of the trace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9b4f-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f9b4f-123">See Also</span></span>  
 <span data-ttu-id="f9b4f-124">[Riprodurre in corrispondenza di un cursore &#40;SQL Server Profiler&#41;](replay-to-a-cursor-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="f9b4f-124">[Replay to a Cursor &#40;SQL Server Profiler&#41;](replay-to-a-cursor-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="f9b4f-125">[Riprodurre le tracce](replay-traces.md) </span><span class="sxs-lookup"><span data-stu-id="f9b4f-125">[Replay Traces](replay-traces.md) </span></span>  
 [<span data-ttu-id="f9b4f-126">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="f9b4f-126">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
