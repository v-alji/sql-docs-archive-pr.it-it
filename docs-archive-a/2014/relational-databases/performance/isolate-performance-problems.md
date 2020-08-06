---
title: Isolare i problemi relativi alle prestazioni | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- isolating performance problems [SQL Server]
- monitoring performance [SQL Server], isolating problems
- database monitoring [SQL Server], isolating problems
- tuning databases [SQL Server], isolating problems
- monitoring server performance [SQL Server], isolating problems
- database performance [SQL Server], isolating problems
- server performance [SQL Server], isolating problems
ms.assetid: 2eb425cb-9166-4027-ae08-c8fc2d236f44
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b42d780a8174ab57d00de72e8b00ef7af0abc17e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716288"
---
# <a name="isolate-performance-problems"></a><span data-ttu-id="e563e-102">Isolare i problemi relativi alle prestazioni</span><span class="sxs-lookup"><span data-stu-id="e563e-102">Isolate Performance Problems</span></span>
  <span data-ttu-id="e563e-103">Per isolare i problemi relativi alle prestazioni del database, è in genere preferibile usare più strumenti di [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o di Microsoft Windows in combinazione, anziché uno per volta.</span><span class="sxs-lookup"><span data-stu-id="e563e-103">It is often more effective to use several [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or Microsoft Windows tools together to isolate database performance problems than to use one tool at a time.</span></span> <span data-ttu-id="e563e-104">La caratteristica grafica Piano di esecuzione, detta anche Showplan, consente, ad esempio, di individuare in modo semplice deadlock in una singola query.</span><span class="sxs-lookup"><span data-stu-id="e563e-104">For example, the graphical Execution Plan feature, also called Showplan, helps you quickly recognize deadlocks in a single query.</span></span> <span data-ttu-id="e563e-105">È tuttavia possibile rilevare in modo più semplice altri problemi relativi alle prestazioni utilizzando le caratteristiche di monitoraggio di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e Windows in combinazione.</span><span class="sxs-lookup"><span data-stu-id="e563e-105">However, you can recognize some other performance problems more easily if you use the monitoring features of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and Windows together.</span></span>  
  
 [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="e563e-106">può essere utilizzato per monitorare e risolvere i problemi correlati a Transact-SQL e alle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="e563e-106">can be used to monitor and troubleshoot Transact-SQL and application-related problems.</span></span> <span data-ttu-id="e563e-107">Per controllare l'hardware e altri problemi relativi al sistema è possibile utilizzare Monitoraggio di sistema.</span><span class="sxs-lookup"><span data-stu-id="e563e-107">System Monitor can be used to monitor hardware and other system-related problems.</span></span>  
  
 <span data-ttu-id="e563e-108">Per risolvere i problemi, è possibile eseguire il monitoraggio degli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="e563e-108">You can monitor the following areas to troubleshoot problems:</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="e563e-109">Stored procedure o batch di istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] inviate da applicazioni utente.</span><span class="sxs-lookup"><span data-stu-id="e563e-109">stored procedures or batches of [!INCLUDE[tsql](../../includes/tsql-md.md)] statements submitted by user applications.</span></span>  
  
-   <span data-ttu-id="e563e-110">Attività degli utenti, ad esempio blocchi o deadlock.</span><span class="sxs-lookup"><span data-stu-id="e563e-110">User activity, such as blocking locks or deadlocks.</span></span>  
  
-   <span data-ttu-id="e563e-111">Attività hardware, ad esempio utilizzo del disco.</span><span class="sxs-lookup"><span data-stu-id="e563e-111">Hardware activity, such as disk usage.</span></span>  
  
 <span data-ttu-id="e563e-112">Tra i problemi che possono verificarsi, sono inclusi i seguenti:</span><span class="sxs-lookup"><span data-stu-id="e563e-112">Problems can include:</span></span>  
  
-   <span data-ttu-id="e563e-113">Errori di sviluppo delle applicazioni correlati a istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] non corrette.</span><span class="sxs-lookup"><span data-stu-id="e563e-113">Application development errors involving incorrectly written [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span>  
  
-   <span data-ttu-id="e563e-114">Errori hardware, ad esempio errori correlati al disco o alla rete.</span><span class="sxs-lookup"><span data-stu-id="e563e-114">Hardware errors, such as disk- or network-related errors.</span></span>  
  
-   <span data-ttu-id="e563e-115">Un numero eccessivo di blocchi causato da un database progettato in modo non appropriato.</span><span class="sxs-lookup"><span data-stu-id="e563e-115">Excessive blocking due to an incorrectly designed database.</span></span>  
  
## <a name="tools-for-common-performance-problems"></a><span data-ttu-id="e563e-116">Strumenti per la risoluzione dei problemi comuni relativi alle prestazioni</span><span class="sxs-lookup"><span data-stu-id="e563e-116">Tools for Common Performance Problems</span></span>  
 <span data-ttu-id="e563e-117">È inoltre importante scegliere con attenzione lo strumento per il monitoraggio o l'ottimizzazione dei problemi relativi alle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="e563e-117">Equally important is careful selection of the performance problem that you want each tool to monitor or tune.</span></span> <span data-ttu-id="e563e-118">Lo strumento e l'utilità dipendono dal tipo di problema che si desidera risolvere.</span><span class="sxs-lookup"><span data-stu-id="e563e-118">The tool and the utility depend on the type of performance problem you want to resolve.</span></span>  
  
 <span data-ttu-id="e563e-119">Negli argomenti seguenti vengono descritti numerosi strumenti di monitoraggio e ottimizzazione e i problemi che tali strumenti consentono di rilevare.</span><span class="sxs-lookup"><span data-stu-id="e563e-119">The following topics describe a variety of monitoring and tuning tools and the problems they uncover.</span></span>  
  
 [<span data-ttu-id="e563e-120">Individuare i colli di bottiglia</span><span class="sxs-lookup"><span data-stu-id="e563e-120">Identify Bottlenecks</span></span>](identify-bottlenecks.md)  
  
 [<span data-ttu-id="e563e-121">Monitorare l'uso della memoria</span><span class="sxs-lookup"><span data-stu-id="e563e-121">Monitor Memory Usage</span></span>](../performance-monitor/monitor-memory-usage.md)  
  
  
