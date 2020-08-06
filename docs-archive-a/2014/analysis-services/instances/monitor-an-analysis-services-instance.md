---
title: Monitorare un'istanza di Analysis Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- monitoring [Analysis Services - multidimensional data]
- multidimensional data [Analysis Services], monitoring
- monitoring performance [SQL Server], SQL Server Profiler
- performance [SQL Server], monitoring tools
ms.assetid: 2f0ab717-05f3-427e-b8cd-a8bdca374add
author: minewiskan
ms.author: owend
ms.openlocfilehash: b98037ea9f26c339cdf7aba22c37e2cfb3dfbb97
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635249"
---
# <a name="monitor-an-analysis-services-instance"></a><span data-ttu-id="4f37e-102">Monitorare un'istanza di Analysis Services</span><span class="sxs-lookup"><span data-stu-id="4f37e-102">Monitor an Analysis Services Instance</span></span>
  <span data-ttu-id="4f37e-103">È possibile monitorare le prestazioni di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] usando [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] o Performance Monitor, un'applicazione talvolta denominata **PerfMon**.</span><span class="sxs-lookup"><span data-stu-id="4f37e-103">You can monitor the performance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] or Performance Monitor, an application sometimes referred to as **PerfMon**.</span></span> [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="4f37e-104">consente di creare e gestire le tracce, nonché analizzare e riprodurre i risultati delle tracce.</span><span class="sxs-lookup"><span data-stu-id="4f37e-104">lets you create and manage traces and analyze and replay trace results.</span></span> <span data-ttu-id="4f37e-105">Tramite Performance Monitor vengono creati report sullo stato del server, indicizzato tramite contatori specifici, che verranno trattati nella sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="4f37e-105">Performance Monitor reports on server status, as indexed through certain counters, which are discussed in the next section.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4f37e-106">Per altre informazioni sul monitoraggio, vedere il documento [SQL Server 2008 R2 Operations Guide](https://go.microsoft.com/fwlink/?LinkID=225539)(Guida alle operazioni di SQL Server 2008 R2).</span><span class="sxs-lookup"><span data-stu-id="4f37e-106">For more information about monitoring, see the [SQL Server 2008 R2 Operations Guide](https://go.microsoft.com/fwlink/?LinkID=225539).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4f37e-107">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="4f37e-107">In This Section</span></span>  
 <span data-ttu-id="4f37e-108">Vedere i collegamenti seguenti per ulteriori informazioni sul monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="4f37e-108">Follow these links to learn more about monitoring.</span></span>  
  
 [<span data-ttu-id="4f37e-109">Eventi di traccia di Analysis Services</span><span class="sxs-lookup"><span data-stu-id="4f37e-109">Analysis Services Trace Events</span></span>](https://docs.microsoft.com/bi-reference/trace-events/analysis-services-trace-events)  
  
 [<span data-ttu-id="4f37e-110">Usare SQL Server Profiler per il monitoraggio di Analysis Services</span><span class="sxs-lookup"><span data-stu-id="4f37e-110">Use SQL Server Profiler to Monitor Analysis Services</span></span>](use-sql-server-profiler-to-monitor-analysis-services.md)  
  
 [<span data-ttu-id="4f37e-111">Usare SQL Server eventi estesi &#40;&#41; XEvent per monitorare Analysis Services</span><span class="sxs-lookup"><span data-stu-id="4f37e-111">Use SQL Server Extended Events &#40;XEvents&#41; to Monitor Analysis Services</span></span>](../instances/monitor-analysis-services-with-sql-server-extended-events.md)  
  
 [<span data-ttu-id="4f37e-112">Utilizzare DMV per monitorare Analysis Services</span><span class="sxs-lookup"><span data-stu-id="4f37e-112">Use Dynamic Management Views &#40;DMVs&#41; to Monitor Analysis Services</span></span>](use-dynamic-management-views-dmvs-to-monitor-analysis-services.md)  
  
 [<span data-ttu-id="4f37e-113">Contatori delle prestazioni &#40;SSAS&#41;</span><span class="sxs-lookup"><span data-stu-id="4f37e-113">Performance Counters &#40;SSAS&#41;</span></span>](performance-counters-ssas.md)  
  
  
