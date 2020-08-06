---
title: Oggetto Processi di SQL Server Agent | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- SQLAgent:Jobs
- Jobs object
ms.assetid: 225b5e2d-4a78-4178-b2b6-b419df83c4aa
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 82ee57eba20d44c08eadc125e9dfd69e73c35751
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626047"
---
# <a name="sql-server-agent-jobs-object"></a><span data-ttu-id="f8f62-102">Oggetto Processi di SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="f8f62-102">SQL Server Agent, Jobs Object</span></span>
  <span data-ttu-id="f8f62-103">L'oggetto prestazioni **Processi** di SQL Server Agent include contatori delle prestazioni che forniscono informazioni relative ai processi di SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="f8f62-103">The SQL Server Agent **Jobs** performance object contains performance counters that report information about SQL Server Agent jobs.</span></span> <span data-ttu-id="f8f62-104">Nella tabella seguente sono elencati i contatori inclusi nell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="f8f62-104">The table below lists the counters that this object contains.</span></span>  
  
 <span data-ttu-id="f8f62-105">Nella tabella seguente sono illustrati i contatori di **SQLAgent:Processi** .</span><span class="sxs-lookup"><span data-stu-id="f8f62-105">The table below contains the **SQLAgent:Jobs** counters.</span></span>  
  
|<span data-ttu-id="f8f62-106">Nome</span><span class="sxs-lookup"><span data-stu-id="f8f62-106">Name</span></span>|<span data-ttu-id="f8f62-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f8f62-107">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="f8f62-108">**Processi attivi**</span><span class="sxs-lookup"><span data-stu-id="f8f62-108">**Active Jobs**</span></span>|<span data-ttu-id="f8f62-109">Questo contatore indica il numero di processi attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="f8f62-109">This counter reports the number of jobs currently running.</span></span>|  
|<span data-ttu-id="f8f62-110">**Processi non riusciti**</span><span class="sxs-lookup"><span data-stu-id="f8f62-110">**Failed jobs**</span></span>|<span data-ttu-id="f8f62-111">Questo contatore indica il numero di processi chiusi con un errore.</span><span class="sxs-lookup"><span data-stu-id="f8f62-111">This counter reports the number of jobs that exited with failure.</span></span>|  
|<span data-ttu-id="f8f62-112">**Percentuale processi completati**</span><span class="sxs-lookup"><span data-stu-id="f8f62-112">**Job success rate**</span></span>|<span data-ttu-id="f8f62-113">Questo contatore indica la percentuale di processi eseguiti completati correttamente.</span><span class="sxs-lookup"><span data-stu-id="f8f62-113">This counter reports the percentage of executed jobs that completed successfully.</span></span>|  
|<span data-ttu-id="f8f62-114">**Processi attivati/minuto**</span><span class="sxs-lookup"><span data-stu-id="f8f62-114">**Jobs activated/minute**</span></span>|<span data-ttu-id="f8f62-115">Questo contatore indica il numero di processi avviati nell'ultimo minuto.</span><span class="sxs-lookup"><span data-stu-id="f8f62-115">This counter reports the number of jobs launched within the last minute.</span></span>|  
|<span data-ttu-id="f8f62-116">**Processi in coda**</span><span class="sxs-lookup"><span data-stu-id="f8f62-116">**Queued jobs**</span></span>|<span data-ttu-id="f8f62-117">Questo contatore indica il numero di processi pronti per l'esecuzione in SQL Server Agent, ma la cui esecuzione non è ancora stata avviata.</span><span class="sxs-lookup"><span data-stu-id="f8f62-117">This counter reports the number of jobs that are ready for SQL Server Agent to run, but which have not yet started running.</span></span>|  
|<span data-ttu-id="f8f62-118">**Processi completati**</span><span class="sxs-lookup"><span data-stu-id="f8f62-118">**Successful jobs**</span></span>|<span data-ttu-id="f8f62-119">Questo contatore indica il numero di processi chiusi correttamente.</span><span class="sxs-lookup"><span data-stu-id="f8f62-119">This counter reports the number of jobs that exited with success.</span></span>|  
  
 <span data-ttu-id="f8f62-120">Per ogni contatore nell'oggetto sono disponibili le istanze seguenti:</span><span class="sxs-lookup"><span data-stu-id="f8f62-120">Each counter in the object contains the following instances:</span></span>  
  
|<span data-ttu-id="f8f62-121">Istanza</span><span class="sxs-lookup"><span data-stu-id="f8f62-121">Instance</span></span>|<span data-ttu-id="f8f62-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f8f62-122">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="f8f62-123">**_Total**</span><span class="sxs-lookup"><span data-stu-id="f8f62-123">**_Total**</span></span>|<span data-ttu-id="f8f62-124">Informazioni relative a tutti i processi.</span><span class="sxs-lookup"><span data-stu-id="f8f62-124">Information for all jobs.</span></span>|  
|<span data-ttu-id="f8f62-125">**Avvisi**</span><span class="sxs-lookup"><span data-stu-id="f8f62-125">**Alerts**</span></span>|<span data-ttu-id="f8f62-126">Informazioni relative ai processi avviati da avvisi.</span><span class="sxs-lookup"><span data-stu-id="f8f62-126">Information for jobs started by alerts.</span></span>|  
|<span data-ttu-id="f8f62-127">**Altro**</span><span class="sxs-lookup"><span data-stu-id="f8f62-127">**Others**</span></span>|<span data-ttu-id="f8f62-128">Informazioni relative a processi non avviati da avvisi o pianificazioni.</span><span class="sxs-lookup"><span data-stu-id="f8f62-128">Information for jobs that were not started by alerts or schedules.</span></span> <span data-ttu-id="f8f62-129">In genere, si tratta di processi avviati manualmente tramite **sp_start_job**.</span><span class="sxs-lookup"><span data-stu-id="f8f62-129">Typically these are jobs started manually using **sp_start_job**.</span></span>|  
|<span data-ttu-id="f8f62-130">**Pianificazioni**</span><span class="sxs-lookup"><span data-stu-id="f8f62-130">**Schedules**</span></span>|<span data-ttu-id="f8f62-131">Informazioni relative ai processi avviati da pianificazioni.</span><span class="sxs-lookup"><span data-stu-id="f8f62-131">Information for jobs started by schedules.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f8f62-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f8f62-132">See Also</span></span>  
 <span data-ttu-id="f8f62-133">[Implementazione di processi](../../ssms/agent/implement-jobs.md) </span><span class="sxs-lookup"><span data-stu-id="f8f62-133">[Implement Jobs](../../ssms/agent/implement-jobs.md) </span></span>  
 <span data-ttu-id="f8f62-134">[Utilizzo degli oggetti prestazioni](../../ssms/agent/use-performance-objects.md) </span><span class="sxs-lookup"><span data-stu-id="f8f62-134">[Use Performance Objects](../../ssms/agent/use-performance-objects.md) </span></span>  
 [<span data-ttu-id="f8f62-135">Monitorare l'utilizzo delle risorse &#40;Monitor di sistema&#41;</span><span class="sxs-lookup"><span data-stu-id="f8f62-135">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](monitor-resource-usage-system-monitor.md)  
  
  
