---
title: SQL Server Profiler-limite contatori prestazioni | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.pro.performancecounterlimit.f1
helpviewer_keywords:
- Performance Counters List dialog box
ms.assetid: d10140ef-36c4-449c-b365-1cff1b2524e4
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 27bda135abaf9d91b078e36a69a87098a734acbc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721695"
---
# <a name="sql-server-profiler---performance-counters-limit"></a><span data-ttu-id="184d2-102">SQL Server Profiler - Limite contatori prestazioni</span><span class="sxs-lookup"><span data-stu-id="184d2-102">SQL Server Profiler - Performance Counters Limit</span></span>
  <span data-ttu-id="184d2-103">Utilizzare la finestra di dialogo Limite contatori prestazioni per limitare le informazioni generate da un file di log delle prestazioni del monitoraggio di sistema quando viene correlato con una traccia di [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="184d2-103">Use the Performance Counters Limit dialog box to limit the information from a System Monitor performance log file when correlating it with a [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] trace.</span></span> <span data-ttu-id="184d2-104">La finestra di dialogo consente di selezionare i contatori da visualizzare e utilizzare per la correlazione.</span><span class="sxs-lookup"><span data-stu-id="184d2-104">You can use this dialog box to select counters that should be displayed and used for correlation.</span></span>  
  
 <span data-ttu-id="184d2-105">La finestra di dialogo **Limite contatori prestazioni** viene popolata con i contatori e gli oggetti prestazioni contenuti nel file di log delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="184d2-105">The **Performance Counters Limit** dialog box is populated with the performance objects and counters that the performance log file contains.</span></span>  
  
### <a name="to-select-performance-objects-and-counters-to-correlate-with-a-trace"></a><span data-ttu-id="184d2-106">Per selezionare i contatori e gli oggetti prestazioni da correlare con una traccia</span><span class="sxs-lookup"><span data-stu-id="184d2-106">To select performance objects and counters to correlate with a trace</span></span>  
  
1.  <span data-ttu-id="184d2-107">Espandere un oggetto prestazione per visualizzare i contatori inclusi nel file di log delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="184d2-107">Expand a performance object to see which counters are included in the performance log file.</span></span>  
  
2.  <span data-ttu-id="184d2-108">Selezionare i contatori da correlare con il file di traccia di [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="184d2-108">Check the counters that you want to correlate with the [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] trace file.</span></span>  
  
     <span data-ttu-id="184d2-109">Per selezionare tutti i contatori relativi a un oggetto prestazione, selezionare la casella adiacente all'oggetto in questione.</span><span class="sxs-lookup"><span data-stu-id="184d2-109">If you want to select all counters for a performance object, check the box that is adjacent to the performance object.</span></span> <span data-ttu-id="184d2-110">Se si seleziona il nodo di livello più alto, che indica il computer, verranno selezionati tutti i contatori e gli oggetti prestazioni contenuti nel file di log delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="184d2-110">Checking the topmost node, which indicates the computer, selects all performance objects and counters contained in the performance log file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="184d2-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="184d2-111">See Also</span></span>  
 [<span data-ttu-id="184d2-112">Correlare una traccia e i dati dei registri di prestazioni di Windows &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="184d2-112">Correlate a Trace with Windows Performance Log Data &#40;SQL Server Profiler&#41;</span></span>](../tools/sql-server-profiler/correlate-a-trace-with-windows-performance-log-data.md)  
  
  
