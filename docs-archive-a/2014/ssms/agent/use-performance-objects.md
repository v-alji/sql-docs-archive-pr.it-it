---
title: Usare gli oggetti prestazioni | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, monitoring
- SQL Server Agent service, monitoring
- SQL Server Agent service, performance objects
- SQL Server Agent, performance objects
- performance objects [SQL Server Agent]
- monitoring [SQL Server], SQL Server Agent
- monitoring [SQL Server Agent]
- performance counters [SQL Server], SQL Server Agent
- counters [SQL Server], SQL Server Agent
ms.assetid: 830b843a-6b2a-4620-a51b-98358e9fc54b
author: stevestein
ms.author: sstein
ms.openlocfilehash: d7c1fe3f4a7d9a5fec901f84d8e913e49a4dbd1b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630236"
---
# <a name="use-performance-objects"></a><span data-ttu-id="50997-102">Utilizzo degli oggetti prestazioni</span><span class="sxs-lookup"><span data-stu-id="50997-102">Use Performance Objects</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="50997-103">Agent include oggetti e contatori delle prestazioni che consentono di monitorare lo stato del servizio.</span><span class="sxs-lookup"><span data-stu-id="50997-103">Agent includes performance objects and counters to monitor how the service is performing.</span></span> <span data-ttu-id="50997-104">Tramite gli oggetti prestazione è possibile utilizzare Performance Monitor, uno strumento Windows che consente di identificare le attività eseguite in background dal servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="50997-104">These performance objects allow you to use Performance Monitor, a Windows tool, to identify what the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service is doing in the background.</span></span> <span data-ttu-id="50997-105">È possibile ad esempio identificare il numero dei processi attivi attualmente in esecuzione in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent e individuare quelli bloccati.</span><span class="sxs-lookup"><span data-stu-id="50997-105">For example, you can identify how many active jobs the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service is currently running to identify those jobs that are blocked.</span></span>  
  
 <span data-ttu-id="50997-106">Per ogni istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installata in un computer sono presenti oggetti prestazione e contatori delle prestazioni del servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="50997-106">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service performance objects and counters exist for each instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that is installed on a computer.</span></span> <span data-ttu-id="50997-107">Agli oggetti prestazione viene assegnato un nome in base all'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] rappresentata da ciascun oggetto.</span><span class="sxs-lookup"><span data-stu-id="50997-107">Performance objects are named according to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that each object represents.</span></span>  
  
 <span data-ttu-id="50997-108">Nella tabella seguente viene illustrata la modalità di assegnazione dei nomi per gli oggetti prestazione del servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent:</span><span class="sxs-lookup"><span data-stu-id="50997-108">The following table shows how the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service performance objects are named:</span></span>  
  
|<span data-ttu-id="50997-109">Tipo di istanza</span><span class="sxs-lookup"><span data-stu-id="50997-109">Instance type</span></span>|<span data-ttu-id="50997-110">Nome dell'oggetto</span><span class="sxs-lookup"><span data-stu-id="50997-110">Object name</span></span>|  
|-------------------|-----------------|  
|<span data-ttu-id="50997-111">Predefinito</span><span class="sxs-lookup"><span data-stu-id="50997-111">Default</span></span>|<span data-ttu-id="50997-112">**SQLAgent:** *oggetto*:*contatore*</span><span class="sxs-lookup"><span data-stu-id="50997-112">**SQLAgent:** *object*:*counter*</span></span>|  
|<span data-ttu-id="50997-113">denominata</span><span class="sxs-lookup"><span data-stu-id="50997-113">Named</span></span>|<span data-ttu-id="50997-114">**SQLAgent$**</span><span class="sxs-lookup"><span data-stu-id="50997-114">**SQLAgent$**</span></span><br /> <span data-ttu-id="50997-115">***instance_name* :** *oggetto*:*contatore*</span><span class="sxs-lookup"><span data-stu-id="50997-115">***instance_name* :** *object*:*counter*</span></span>|  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="50997-116">include gli oggetti prestazione seguenti per [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="50997-116">includes the following performance objects for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span>  
  
|<span data-ttu-id="50997-117">Nome dell'oggetto</span><span class="sxs-lookup"><span data-stu-id="50997-117">Object name</span></span>|<span data-ttu-id="50997-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="50997-118">Description</span></span>|  
|-----------------|-----------------|  
|[<span data-ttu-id="50997-119">SQLAgent:Processi</span><span class="sxs-lookup"><span data-stu-id="50997-119">SQLAgent:Jobs</span></span>](../../relational-databases/performance-monitor/sql-server-agent-jobs-object.md)|<span data-ttu-id="50997-120">Informazioni sulle prestazioni relative a processi avviati, alle percentuali di processi completati e allo stato corrente</span><span class="sxs-lookup"><span data-stu-id="50997-120">Performance information about jobs that have been started, success rates, and current status</span></span>|  
|[<span data-ttu-id="50997-121">SQLAgent:JobSteps</span><span class="sxs-lookup"><span data-stu-id="50997-121">SQLAgent:JobSteps</span></span>](../../relational-databases/performance-monitor/sql-server-agent-jobsteps-object.md)|<span data-ttu-id="50997-122">Informazioni sullo stato relative ai passaggi di processo</span><span class="sxs-lookup"><span data-stu-id="50997-122">Status information about job steps</span></span>|  
|[<span data-ttu-id="50997-123">SQLAgent:Avvisi</span><span class="sxs-lookup"><span data-stu-id="50997-123">SQLAgent:Alerts</span></span>](../../relational-databases/performance-monitor/sql-server-agent-alerts-object.md)|<span data-ttu-id="50997-124">Informazioni sul numero di avvisi e notifiche</span><span class="sxs-lookup"><span data-stu-id="50997-124">Information about number of alerts and notifications</span></span>|  
|[<span data-ttu-id="50997-125">SQLAgent:Statistiche</span><span class="sxs-lookup"><span data-stu-id="50997-125">SQLAgent:Statistics</span></span>](../../relational-databases/performance-monitor/sql-server-agent-statistics-object.md)|<span data-ttu-id="50997-126">Informazioni generali sulle prestazioni</span><span class="sxs-lookup"><span data-stu-id="50997-126">General performance information</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="50997-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="50997-127">See Also</span></span>  
 <span data-ttu-id="50997-128">[Monitoraggio e ottimizzazione delle prestazioni](../../relational-databases/performance/monitor-and-tune-for-performance.md) </span><span class="sxs-lookup"><span data-stu-id="50997-128">[Monitor and Tune for Performance](../../relational-databases/performance/monitor-and-tune-for-performance.md) </span></span>  
 [<span data-ttu-id="50997-129">Avviare il Monitoraggio di sistema &#40;Windows&#41;</span><span class="sxs-lookup"><span data-stu-id="50997-129">Start System Monitor &#40;Windows&#41;</span></span>](../../relational-databases/performance/start-system-monitor-windows.md)  
  
  
