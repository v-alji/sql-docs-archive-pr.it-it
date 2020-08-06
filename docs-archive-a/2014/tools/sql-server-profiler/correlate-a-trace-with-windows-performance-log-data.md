---
title: Correlare una traccia con i dati del log delle prestazioni di Windows | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- correlating trace with log data
- logs [SQL Server], traces
- Profiler [SQL Server Profiler], correlating trace with log data
- traces [SQL Server], logs
- SQL Server Profiler, correlating trace with log data
ms.assetid: 1e4412c8-d27c-4aae-9b35-214128d1d00a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 879441c948f0ad04b971159a37ec0dcec90e3ada
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711280"
---
# <a name="correlate-a-trace-with-windows-performance-log-data"></a><span data-ttu-id="95af3-102">Correlare una traccia con i dati del log delle prestazioni di Windows</span><span class="sxs-lookup"><span data-stu-id="95af3-102">Correlate a Trace with Windows Performance Log Data</span></span>
  <span data-ttu-id="95af3-103">[!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]consente di aprire un log delle prestazioni di Microsoft Windows, scegliere i contatori da correlare a una traccia e visualizzare i contatori delle prestazioni selezionati insieme alla traccia nell'interfaccia utente grafica di [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="95af3-103">Using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], you can open a Microsoft Windows performance log, choose the counters you want to correlate with a trace, and display the selected performance counters alongside the trace in the [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] graphical user interface.</span></span> <span data-ttu-id="95af3-104">Quando si seleziona un evento nella finestra della traccia, una barra rossa verticale nel riquadro della finestra dei dati di Monitoraggio di sistema di [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] indica i dati del log delle prestazioni correlati all'evento di traccia selezionato.</span><span class="sxs-lookup"><span data-stu-id="95af3-104">When you select an event in the trace window, a vertical red bar in the System Monitor data window pane of [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] indicates the performance log data that correlates with the selected trace event.</span></span>  
  
 <span data-ttu-id="95af3-105">Per correlare una traccia con i contatori delle prestazioni, aprire un file di traccia o una tabella contenente le colonne di dati **StartTime** ed **EndTime** e quindi scegliere **Importa dati prestazioni** dal menu [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]File**di**.</span><span class="sxs-lookup"><span data-stu-id="95af3-105">To correlate a trace with performance counters, open a trace file or table that contains the **StartTime** and **EndTime** data columns, and then click **Import Performance Data** on the [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] **File** menu.</span></span> <span data-ttu-id="95af3-106">È quindi possibile aprire un log delle prestazioni e selezionare gli oggetti e i contatori di Monitoraggio di sistema da correlare alla traccia.</span><span class="sxs-lookup"><span data-stu-id="95af3-106">You can then open a performance log, and select the System Monitor objects and counters that you want to correlate with the trace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95af3-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="95af3-107">See Also</span></span>  
 [<span data-ttu-id="95af3-108">Correlare una traccia e i dati dei registri di prestazioni di Windows &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="95af3-108">Correlate a Trace with Windows Performance Log Data &#40;SQL Server Profiler&#41;</span></span>](correlate-a-trace-with-windows-performance-log-data.md)  
  
  
