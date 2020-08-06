---
title: Avviare una traccia | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Profiler, stopping traces
- pausing traces
- Profiler [SQL Server Profiler], stopping traces
- Profiler [SQL Server Profiler], starting traces
- traces [SQL Server], starting
- SQL Server Profiler, pausing traces
- traces [SQL Server], stopping
- Profiler [SQL Server Profiler], pausing traces
- traces [SQL Server], pausing
- SQL Server Profiler, starting traces
- stopping traces
- starting traces
ms.assetid: aeeb38eb-229a-4c8b-ad66-57e9ce45fb6a
author: stevestein
ms.author: sstein
ms.openlocfilehash: f2b75519631269a1213077a4e295ac73fca1b950
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719163"
---
# <a name="start-a-trace"></a><span data-ttu-id="dfc76-102">Avviare una traccia</span><span class="sxs-lookup"><span data-stu-id="dfc76-102">Start a Trace</span></span>
  <span data-ttu-id="dfc76-103">Dopo aver definito una nuova traccia o creato un modello con [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], è possibile avviare, sospendere o arrestare l'acquisizione dei dati in base alla nuova definizione di traccia o modello.</span><span class="sxs-lookup"><span data-stu-id="dfc76-103">After you have defined a new trace or created a template by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], you can start, pause, or stop capturing data by using the new trace definition or template.</span></span>  
  
## <a name="starting-a-trace"></a><span data-ttu-id="dfc76-104">Avvio di una traccia</span><span class="sxs-lookup"><span data-stu-id="dfc76-104">Starting a Trace</span></span>  
 <span data-ttu-id="dfc76-105">Quando viene avviata una traccia e l'origine definita è un'istanza di [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] o [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] crea una coda come posizione temporanea per gli eventi del server acquisiti.</span><span class="sxs-lookup"><span data-stu-id="dfc76-105">When you start a trace and the defined source is an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] or [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] creates a queue that provides a temporary holding place for captured server events.</span></span>  
  
 <span data-ttu-id="dfc76-106">Se si utilizza [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] per accedere a Traccia SQL, l'avvio di una traccia comporta l'apertura di una nuova finestra di traccia (se non vi è una finestra già aperta) e i dati vengono acquisiti immediatamente.</span><span class="sxs-lookup"><span data-stu-id="dfc76-106">When you use [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] to access SQL Trace, a new trace window opens (if one is not already open) when a trace is started, and data is immediately captured.</span></span>  
  
 <span data-ttu-id="dfc76-107">Quando si utilizzano le stored procedure di sistema di [!INCLUDE[tsql](../../includes/tsql-md.md)] per l'accesso a Traccia SQL, perché i dati vengano acquisiti è necessario avviare una traccia a ogni avvio di un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="dfc76-107">When you use [!INCLUDE[tsql](../../includes/tsql-md.md)] system stored procedures to access SQL Trace, you must start a trace every time an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] starts for data to be captured.</span></span> <span data-ttu-id="dfc76-108">Dopo l'avvio di una traccia è possibile modificarne unicamente il nome.</span><span class="sxs-lookup"><span data-stu-id="dfc76-108">When a trace has been started, you can modify only the name of the trace.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dfc76-109">Quando si utilizzano tracce esistenti, è possibile visualizzare le proprietà ma non modificarle.</span><span class="sxs-lookup"><span data-stu-id="dfc76-109">When working with existing traces, you can view the properties, but you cannot modify the properties.</span></span> <span data-ttu-id="dfc76-110">Per modificare le proprietà, arrestare o sospendere la traccia.</span><span class="sxs-lookup"><span data-stu-id="dfc76-110">To modify the properties, stop or pause the trace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfc76-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dfc76-111">See Also</span></span>  
 <span data-ttu-id="dfc76-112">[Avviare una traccia automaticamente dopo la connessione a un server &#40;SQL Server Profiler&#41;](start-a-trace-automatically-after-connecting-to-a-server-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="dfc76-112">[Start a Trace Automatically after Connecting to a Server &#40;SQL Server Profiler&#41;](start-a-trace-automatically-after-connecting-to-a-server-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="dfc76-113">[Sospendere una traccia &#40;SQL Server Profiler&#41;](pause-a-trace-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="dfc76-113">[Pause a Trace &#40;SQL Server Profiler&#41;](pause-a-trace-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="dfc76-114">[Arrestare una traccia &#40;SQL Server Profiler&#41;](stop-a-trace-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="dfc76-114">[Stop a Trace &#40;SQL Server Profiler&#41;](stop-a-trace-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="dfc76-115">[Deselezionare una finestra di traccia &#40;SQL Server Profiler&#41;](clear-a-trace-window-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="dfc76-115">[Clear a Trace Window &#40;SQL Server Profiler&#41;](clear-a-trace-window-sql-server-profiler.md) </span></span>  
 [<span data-ttu-id="dfc76-116">Eseguire una traccia dopo la sospensione o l'arresto &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="dfc76-116">Run a Trace After It Has Been Paused or Stopped &#40;SQL Server Profiler&#41;</span></span>](run-a-trace-after-it-has-been-paused-or-stopped-sql-server-profiler.md)  
  
  
