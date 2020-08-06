---
title: MSSQL_ENG014164 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014164 error
ms.assetid: cd81b601-2ec3-4358-ad58-c2655496e6a1
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ddf88cbdfd25d77ca3f2eadf4176309d02a084e6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625327"
---
# <a name="mssql_eng014164"></a><span data-ttu-id="e043f-102">MSSQL_ENG014164</span><span class="sxs-lookup"><span data-stu-id="e043f-102">MSSQL_ENG014164</span></span>
    
## <a name="message-details"></a><span data-ttu-id="e043f-103">Dettagli messaggio</span><span class="sxs-lookup"><span data-stu-id="e043f-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e043f-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="e043f-104">Product Name</span></span>|<span data-ttu-id="e043f-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="e043f-105">SQL Server</span></span>|  
|<span data-ttu-id="e043f-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="e043f-106">Event ID</span></span>|<span data-ttu-id="e043f-107">14164</span><span class="sxs-lookup"><span data-stu-id="e043f-107">14164</span></span>|  
|<span data-ttu-id="e043f-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="e043f-108">Event Source</span></span>|<span data-ttu-id="e043f-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="e043f-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="e043f-110">Componente</span><span class="sxs-lookup"><span data-stu-id="e043f-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="e043f-111">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="e043f-111">Symbolic Name</span></span>||  
|<span data-ttu-id="e043f-112">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="e043f-112">Message Text</span></span>|<span data-ttu-id="e043f-113">È stata impostata la soglia [%s:%s] per la pubblicazione [%s].</span><span class="sxs-lookup"><span data-stu-id="e043f-113">The threshold [%s:%s] for the publication [%s] has been set.</span></span> <span data-ttu-id="e043f-114">Verificare che l'agente di merge sia in esecuzione e sia in grado di rispettare i requisiti previsti.</span><span class="sxs-lookup"><span data-stu-id="e043f-114">Please make sure that the merge agent is running and can match the expected requirement.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e043f-115">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="e043f-115">Explanation</span></span>  
 <span data-ttu-id="e043f-116">La replica consente di attivare avvisi per numerose condizioni,</span><span class="sxs-lookup"><span data-stu-id="e043f-116">Replication lets you enable warnings for several conditions.</span></span> <span data-ttu-id="e043f-117">tra cui la mancata elaborazione di un numero di righe sufficiente durante la sincronizzazione delle modifiche tra un server di pubblicazione e un Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="e043f-117">This includes failure to process a sufficient number of rows when synchronizing changes between a merge Publisher and Subscriber.</span></span> <span data-ttu-id="e043f-118">È possibile specificare momenti diversi per connessioni LAN e remote.</span><span class="sxs-lookup"><span data-stu-id="e043f-118">Different times can be specified for LAN connections and dial-up connections.</span></span>  
  
 <span data-ttu-id="e043f-119">Quando si attiva un avviso utilizzando Monitoraggio replica o [sp_replmonitorchangepublicationthreshold](/sql/relational-databases/system-stored-procedures/sp-replmonitorchangepublicationthreshold-transact-sql), viene specificata una soglia che determina quando è generato l'avviso.</span><span class="sxs-lookup"><span data-stu-id="e043f-119">When you enable a warning by using Replication Monitor or [sp_replmonitorchangepublicationthreshold](/sql/relational-databases/system-stored-procedures/sp-replmonitorchangepublicationthreshold-transact-sql), you specify a threshold that determines when a warning is triggered.</span></span> <span data-ttu-id="e043f-120">Quando tale soglia viene raggiunta o superata, viene visualizzato un avviso in Monitoraggio replica e viene registrato un evento nel registro eventi di Windows.</span><span class="sxs-lookup"><span data-stu-id="e043f-120">When that threshold is met or exceeded, a warning is displayed in Replication Monitor, and an event is written to the Windows event log.</span></span> <span data-ttu-id="e043f-121">Il raggiungimento di una soglia può inoltre generare un avviso SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="e043f-121">Reaching a threshold can also trigger a SQL Server Agent alert.</span></span> <span data-ttu-id="e043f-122">Per altre informazioni, vedere [Impostare valori di soglia e avvisi in Monitoraggio replica](monitor/set-thresholds-and-warnings-in-replication-monitor.md) e [Monitorare la replica a livello di programmazione](monitoring-replication.md).</span><span class="sxs-lookup"><span data-stu-id="e043f-122">For more information, see [Set Thresholds and Warnings in Replication Monitor](monitor/set-thresholds-and-warnings-in-replication-monitor.md) and [Programmatically Monitor Replication](monitoring-replication.md).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e043f-123">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="e043f-123">User Action</span></span>  
 <span data-ttu-id="e043f-124">Se una sottoscrizione non è conforme a una soglia di elaborazione delle righe, è necessario stabilire se il fenomeno dipende da un problema di prestazioni del sistema o se la soglia deve essere regolata.</span><span class="sxs-lookup"><span data-stu-id="e043f-124">If a subscription is not meeting a row processing threshold, you must determine whether there is a performance issue with the system or whether the threshold should be adjusted.</span></span> <span data-ttu-id="e043f-125">Dopo avere configurato la replica, sviluppare dati di riferimento per le prestazioni in modo da poter stabilire il comportamento della replica in presenza del carico di lavoro tipico delle applicazioni e della topologia in uso.</span><span class="sxs-lookup"><span data-stu-id="e043f-125">After you configure replication, develop a performance baseline that will let you determine how replication behaves with a workload that is typical for your applications and topology.</span></span> <span data-ttu-id="e043f-126">Includere nei dati di riferimento anche il numero di righe elaborate al fine di poter impostare un valore appropriato per la soglia.</span><span class="sxs-lookup"><span data-stu-id="e043f-126">Include number of rows processed in this baseline so that you can set an appropriate value for the threshold.</span></span>  
  
 <span data-ttu-id="e043f-127">Se il valore soglia è appropriato ma viene superato, è necessario individuare l'area del sistema a cui è dovuto il collo di bottiglia a livello di prestazioni.</span><span class="sxs-lookup"><span data-stu-id="e043f-127">If the threshold value is appropriate, but it is being exceeded, you must determine where the performance bottleneck is in the system.</span></span> <span data-ttu-id="e043f-128">Per ulteriori informazioni sul monitoraggio e la risoluzione dei problemi delle prestazioni di replica, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="e043f-128">For more information about how to monitor and troubleshoot replication performance, see the following topics:</span></span>  
  
-   <span data-ttu-id="e043f-129">[Monitorare le prestazioni con Monitoraggio replica](monitor/monitor-performance-with-replication-monitor.md) (in particolare la sezione "Visualizzazione di statistiche dettagliate sulle prestazioni di sincronizzazione per la replica di tipo merge")</span><span class="sxs-lookup"><span data-stu-id="e043f-129">[Monitor Performance with Replication Monitor](monitor/monitor-performance-with-replication-monitor.md) (especially the section "Viewing Detailed Synchronization Performance for Merge Replication")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e043f-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e043f-130">See Also</span></span>  
 [<span data-ttu-id="e043f-131">Guida di riferimento a errori ed eventi &#40;replica&#41;</span><span class="sxs-lookup"><span data-stu-id="e043f-131">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
