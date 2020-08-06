---
title: Oggetto JobSteps di SQL Server Agent | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- JobSteps object
- SQLAgent:JobSteps
ms.assetid: 44f9983c-1753-4fe0-8475-973aa2460b3a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 3759303807714e2bb7f71f59e644bc485d36cfcb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626046"
---
# <a name="sql-server-agent-jobsteps-object"></a><span data-ttu-id="c4729-102">Oggetto JobSteps di SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="c4729-102">SQL Server Agent, JobSteps Object</span></span>
  <span data-ttu-id="c4729-103">L'oggetto prestazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] JobSteps **di** Agent contiene contatori delle prestazioni che forniscono informazioni relative ai passaggi di processo di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="c4729-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent **JobSteps** performance object contains performance counters that report information about [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job steps.</span></span> <span data-ttu-id="c4729-104">Nella tabella seguente sono elencati i contatori inclusi nell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="c4729-104">The table below lists the counters that this object contains.</span></span>  
  
 <span data-ttu-id="c4729-105">Nella tabella seguente sono inclusi i contatori **SQLAgent:Passaggi processi** .</span><span class="sxs-lookup"><span data-stu-id="c4729-105">The table below contains the **SQLAgent:JobSteps** counters.</span></span>  
  
|<span data-ttu-id="c4729-106">Nome</span><span class="sxs-lookup"><span data-stu-id="c4729-106">Name</span></span>|<span data-ttu-id="c4729-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c4729-107">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="c4729-108">**Passaggi attivi**</span><span class="sxs-lookup"><span data-stu-id="c4729-108">**Active steps**</span></span>|<span data-ttu-id="c4729-109">In questo contatore viene visualizzato il numero di passaggi del processo attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="c4729-109">This counter reports the number of job steps currently running.</span></span>|  
|<span data-ttu-id="c4729-110">**Passaggi in coda**</span><span class="sxs-lookup"><span data-stu-id="c4729-110">**Queued steps**</span></span>|<span data-ttu-id="c4729-111">In questo contatore viene visualizzato il numero di passaggi del processo pronti per l'esecuzione in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, ma la cui esecuzione non è ancora stata avviata.</span><span class="sxs-lookup"><span data-stu-id="c4729-111">This counter reports the number of job steps that are ready for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to run, but which have not yet started running.</span></span>|  
|<span data-ttu-id="c4729-112">**Totale tentativi passaggio**</span><span class="sxs-lookup"><span data-stu-id="c4729-112">**Total step retries**</span></span>|<span data-ttu-id="c4729-113">In questo contatore viene visualizzato il numero totale di tentativi di esecuzione di un passaggio del processo in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] dall'ultimo riavvio del server.</span><span class="sxs-lookup"><span data-stu-id="c4729-113">This counter reports the total number of times that [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has retried a job step since the last server restart.</span></span>|  
  
 <span data-ttu-id="c4729-114">Per ogni contatore nell'oggetto sono disponibili le istanze seguenti:</span><span class="sxs-lookup"><span data-stu-id="c4729-114">Each counter in the object contains the following instances:</span></span>  
  
|<span data-ttu-id="c4729-115">Istanza</span><span class="sxs-lookup"><span data-stu-id="c4729-115">Instance</span></span>|<span data-ttu-id="c4729-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c4729-116">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="c4729-117">**_Total**</span><span class="sxs-lookup"><span data-stu-id="c4729-117">**_Total**</span></span>|<span data-ttu-id="c4729-118">Informazioni su tutti i passaggi del processo.</span><span class="sxs-lookup"><span data-stu-id="c4729-118">Information for all job steps.</span></span>|  
|<span data-ttu-id="c4729-119">**ActiveScripting**</span><span class="sxs-lookup"><span data-stu-id="c4729-119">**ActiveScripting**</span></span>|<span data-ttu-id="c4729-120">Informazioni per i passaggi del processo che utilizzano il sottosistema **ActiveScripting** .</span><span class="sxs-lookup"><span data-stu-id="c4729-120">Information for job steps that use the **ActiveScripting** subsystem.</span></span>|  
|<span data-ttu-id="c4729-121">**ANALYSISCOMMAND**</span><span class="sxs-lookup"><span data-stu-id="c4729-121">**ANALYSISCOMMAND**</span></span>|<span data-ttu-id="c4729-122">Informazioni per i passaggi del processo che utilizzano il sottosistema ANALYSISCOMMAND.</span><span class="sxs-lookup"><span data-stu-id="c4729-122">Information for job steps that use the ANALYSISCOMMAND subsystem.</span></span>|  
|<span data-ttu-id="c4729-123">**ANALYSISQUERY**</span><span class="sxs-lookup"><span data-stu-id="c4729-123">**ANALYSISQUERY**</span></span>|<span data-ttu-id="c4729-124">Informazioni per i passaggi del processo che utilizzano il sottosistema ANALYSISQUERY.</span><span class="sxs-lookup"><span data-stu-id="c4729-124">Information for job steps that use the ANALYSISQUERY subsystem.</span></span>|  
|<span data-ttu-id="c4729-125">**CmdExec**</span><span class="sxs-lookup"><span data-stu-id="c4729-125">**CmdExec**</span></span>|<span data-ttu-id="c4729-126">Informazioni per i passaggi del processo che utilizzano il sottosistema **CmdExec** .</span><span class="sxs-lookup"><span data-stu-id="c4729-126">Information for job steps that use the **CmdExec** subsystem.</span></span>|  
|<span data-ttu-id="c4729-127">**Distribuzione**</span><span class="sxs-lookup"><span data-stu-id="c4729-127">**Distribution**</span></span>|<span data-ttu-id="c4729-128">Informazioni per i passaggi del processo che utilizzano il sottosistema **Distribution** .</span><span class="sxs-lookup"><span data-stu-id="c4729-128">Information for job steps that use the **Distribution** subsystem.</span></span>|  
|<span data-ttu-id="c4729-129">**Dts**</span><span class="sxs-lookup"><span data-stu-id="c4729-129">**Dts**</span></span>|<span data-ttu-id="c4729-130">Informazioni per i passaggi del processo che utilizzano il sottosistema [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c4729-130">Information for job steps that use the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] subsystem.</span></span>|  
|<span data-ttu-id="c4729-131">**LogReader**</span><span class="sxs-lookup"><span data-stu-id="c4729-131">**LogReader**</span></span>|<span data-ttu-id="c4729-132">Informazioni per i passaggi del processo che utilizzano il sottosistema **LogReader** .</span><span class="sxs-lookup"><span data-stu-id="c4729-132">Information for job steps that use the **LogReader** subsystem.</span></span>|  
|<span data-ttu-id="c4729-133">**Merge**</span><span class="sxs-lookup"><span data-stu-id="c4729-133">**Merge**</span></span>|<span data-ttu-id="c4729-134">Informazioni per i passaggi del processo che utilizzano il sottosistema **Merge** .</span><span class="sxs-lookup"><span data-stu-id="c4729-134">Information for job steps that use the **Merge** subsystem.</span></span>|  
|<span data-ttu-id="c4729-135">**PowerShell**</span><span class="sxs-lookup"><span data-stu-id="c4729-135">**PowerShell**</span></span>|<span data-ttu-id="c4729-136">Informazioni per i passaggi del processo che utilizzano il sottosistema **PowerShell** .</span><span class="sxs-lookup"><span data-stu-id="c4729-136">Information for job steps that use the **PowerShell** subsystem.</span></span>|  
|<span data-ttu-id="c4729-137">**QueueReader**</span><span class="sxs-lookup"><span data-stu-id="c4729-137">**QueueReader**</span></span>|<span data-ttu-id="c4729-138">Informazioni per i passaggi del processo che utilizzano il sottosistema **QueueReader** .</span><span class="sxs-lookup"><span data-stu-id="c4729-138">Information for job steps that use the **QueueReader** subsystem.</span></span>|  
|<span data-ttu-id="c4729-139">**Snapshot**</span><span class="sxs-lookup"><span data-stu-id="c4729-139">**Snapshot**</span></span>|<span data-ttu-id="c4729-140">Informazioni per i passaggi del processo che utilizzano il sottosistema **Snapshot** .</span><span class="sxs-lookup"><span data-stu-id="c4729-140">Information for job steps that use the **Snapshot** subsystem.</span></span>|  
|<span data-ttu-id="c4729-141">**TSQL**</span><span class="sxs-lookup"><span data-stu-id="c4729-141">**TSQL**</span></span>|<span data-ttu-id="c4729-142">Informazioni per i passaggi del processo che comportano l'esecuzione di [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c4729-142">Information for job steps that execute [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c4729-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c4729-143">See Also</span></span>  
 <span data-ttu-id="c4729-144">[Gestire passaggi di processo](../../ssms/agent/manage-job-steps.md) </span><span class="sxs-lookup"><span data-stu-id="c4729-144">[Manage Job Steps](../../ssms/agent/manage-job-steps.md) </span></span>  
 <span data-ttu-id="c4729-145">[Utilizzo degli oggetti prestazioni](../../ssms/agent/use-performance-objects.md) </span><span class="sxs-lookup"><span data-stu-id="c4729-145">[Use Performance Objects](../../ssms/agent/use-performance-objects.md) </span></span>  
 [<span data-ttu-id="c4729-146">Monitorare l'utilizzo delle risorse &#40;Monitor di sistema&#41;</span><span class="sxs-lookup"><span data-stu-id="c4729-146">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](monitor-resource-usage-system-monitor.md)  
  
  
