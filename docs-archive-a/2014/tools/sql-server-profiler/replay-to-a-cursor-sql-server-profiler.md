---
title: Riprodurre fino a un cursore (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- replaying cursors
- traces [SQL Server], replaying
- replaying traces
ms.assetid: 89eadc41-4424-4a1c-ba61-0b52c851cdb1
author: stevestein
ms.author: sstein
ms.openlocfilehash: bfc5ba06b60100bf8ecc8d04909371021a5b00e5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722051"
---
# <a name="replay-to-a-cursor-sql-server-profiler"></a><span data-ttu-id="07379-102">Riprodurre fino a un cursore (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="07379-102">Replay to a Cursor (SQL Server Profiler)</span></span>
  <span data-ttu-id="07379-103">In questo argomento viene descritto come sospendere la riproduzione di tabelle o file di traccia in corrispondenza di un cursore utilizzando [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="07379-103">This topic describes how to replay trace files or tables that pause when a cursor is reached by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span> <span data-ttu-id="07379-104">La sospensione della riproduzione delle tracce in corrispondenza dei cursori supporta il debug in quanto è possibile interrompere la riproduzione di script di traccia lunghi in segmenti più brevi per eseguirne l'analisi incrementale.</span><span class="sxs-lookup"><span data-stu-id="07379-104">Pausing traces at cursors supports debugging because you can break the replay of long trace scripts into short segments that can be analyzed incrementally.</span></span>  
  
### <a name="to-replay-to-the-cursor"></a><span data-ttu-id="07379-105">Per eseguire la riproduzione fino al cursore</span><span class="sxs-lookup"><span data-stu-id="07379-105">To replay to the cursor</span></span>  
  
1.  <span data-ttu-id="07379-106">Aprire il file o la tabella di traccia che si desidera riprodurre.</span><span class="sxs-lookup"><span data-stu-id="07379-106">Open the trace file or trace table you want to replay.</span></span> <span data-ttu-id="07379-107">Per altre informazioni, vedere [Aprire un file di traccia &#40;SQL Server Profiler&#41;](open-a-trace-file-sql-server-profiler.md) o Ottimizzazione guidata [Aprire una tabella di traccia &#40;SQL Server Profiler&#41;](open-a-trace-table-sql-server-profiler.md).</span><span class="sxs-lookup"><span data-stu-id="07379-107">For more information, see [Open a Trace File &#40;SQL Server Profiler&#41;](open-a-trace-file-sql-server-profiler.md) or [Open a Trace Table &#40;SQL Server Profiler&#41;](open-a-trace-table-sql-server-profiler.md).</span></span>  
  
     <span data-ttu-id="07379-108">Verificare che il file o la tabella di traccia aperta contenga le classi di evento necessarie per la riproduzione.</span><span class="sxs-lookup"><span data-stu-id="07379-108">Make sure that the trace file or table you open contains the event classes necessary for replay.</span></span> <span data-ttu-id="07379-109">Per altre informazioni, vedere [Requisiti per la riproduzione](replay-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="07379-109">For more information, see [Replay Requirements](replay-requirements.md).</span></span>  
  
2.  <span data-ttu-id="07379-110">Nella finestra di traccia fare clic su un evento.</span><span class="sxs-lookup"><span data-stu-id="07379-110">In the trace window, click an event.</span></span>  
  
3.  <span data-ttu-id="07379-111">Scegliere **Esegui fino al cursore** dal menu **Riproduci**e quindi connettersi al server di cui si vuole riprodurre la traccia.</span><span class="sxs-lookup"><span data-stu-id="07379-111">On the **Replay** menu, click **Run to Cursor**, and then connect to the server where you want to replay the trace.</span></span>  
  
4.  <span data-ttu-id="07379-112">Nella finestra di dialogo **Configurazione riproduzione** verificare le impostazioni e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="07379-112">In the **Replay Configuration** dialog box, verify the settings, and then click **OK**.</span></span>  
  
     <span data-ttu-id="07379-113">La riproduzione viene avviata e quindi sospesa in corrispondenza del primo cursore.</span><span class="sxs-lookup"><span data-stu-id="07379-113">The replay starts, pausing when the first cursor is reached.</span></span>  
  
5.  <span data-ttu-id="07379-114">Premere F5 per riprendere la riproduzione della traccia.</span><span class="sxs-lookup"><span data-stu-id="07379-114">Press F5 to resume the trace.</span></span>  
  
6.  <span data-ttu-id="07379-115">Ripetere l'operazione descritta al passaggio 5 fino alla fine della traccia.</span><span class="sxs-lookup"><span data-stu-id="07379-115">Repeat Step 5 through the end of the trace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07379-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="07379-116">See Also</span></span>  
 <span data-ttu-id="07379-117">[Riprodurre fino a un punto di interruzione &#40;SQL Server Profiler&#41;](replay-to-a-breakpoint-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="07379-117">[Replay to a Breakpoint &#40;SQL Server Profiler&#41;](replay-to-a-breakpoint-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="07379-118">[Riprodurre le tracce](replay-traces.md) </span><span class="sxs-lookup"><span data-stu-id="07379-118">[Replay Traces](replay-traces.md) </span></span>  
 [<span data-ttu-id="07379-119">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="07379-119">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
