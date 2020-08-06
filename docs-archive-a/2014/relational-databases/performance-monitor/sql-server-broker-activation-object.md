---
title: Oggetto Broker Activation di SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- SQLServer:Broker Activation
- Broker Activation object
ms.assetid: cd9b6880-c924-42c7-b333-09c303317c0b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 4048c2baecaeb4bde7a1e215a15e8c51a60a01bd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715235"
---
# <a name="sql-server-broker-activation-object"></a><span data-ttu-id="2061a-102">Oggetto Attivazione Broker di SQL Server</span><span class="sxs-lookup"><span data-stu-id="2061a-102">SQL Server, Broker Activation Object</span></span>
  <span data-ttu-id="2061a-103">L'oggetto prestazione **SQLServer:Attivazione Broker** include contatori delle prestazioni che contengono informazioni sull'attivazione tramite stored procedure.</span><span class="sxs-lookup"><span data-stu-id="2061a-103">The **SQLServer:BrokerActivation** performance object contains performance counters that report information on stored procedure activation.</span></span> <span data-ttu-id="2061a-104">Nella tabella seguente sono elencati i contatori inclusi nell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="2061a-104">The table below lists the counters that this object contains.</span></span>  
  
|<span data-ttu-id="2061a-105">Contatori dell'oggetto Attivazione Broker di SQL Server</span><span class="sxs-lookup"><span data-stu-id="2061a-105">SQL Server Broker Activation counters</span></span>|<span data-ttu-id="2061a-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2061a-106">Description</span></span>|  
|-------------------------------------------|-----------------|  
|<span data-ttu-id="2061a-107">**Stored procedure richiamate/sec**</span><span class="sxs-lookup"><span data-stu-id="2061a-107">**Stored Procedures Invoked/sec**</span></span>|<span data-ttu-id="2061a-108">Questo contatore indica il numero totale di stored procedure di attivazione richiamate al secondo da tutti i monitoraggi di coda dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="2061a-108">This counter reports the total number of activation stored procedures invoked by all queue monitors in the instance per second.</span></span>|  
|<span data-ttu-id="2061a-109">**Totale limite attività raggiunto**</span><span class="sxs-lookup"><span data-stu-id="2061a-109">**Task Limit Reached**</span></span>|<span data-ttu-id="2061a-110">Questo contatore indica il numero totale di casi in cui un monitoraggio di coda non ha potuto avviare nuove attività in quanto è stato già raggiunto il numero massimo di attività in esecuzione per la coda.</span><span class="sxs-lookup"><span data-stu-id="2061a-110">This counter reports the total number of times that a queue monitor would have started a new task, but did not because the maximum number of tasks for the queue is already running.</span></span>|  
|<span data-ttu-id="2061a-111">**Limite attività raggiunto/sec**</span><span class="sxs-lookup"><span data-stu-id="2061a-111">**Task Limit Reached/sec**</span></span>|<span data-ttu-id="2061a-112">Questo contatore indica il numero di casi al secondo in cui un monitoraggio di coda non ha potuto avviare nuove attività in quanto è stato già raggiunto il numero massimo di attività in esecuzione per la coda.</span><span class="sxs-lookup"><span data-stu-id="2061a-112">This counter reports the number of times per second that a queue monitor would have started a new task, but did not because the maximum number of tasks for the queue is already running.</span></span>|  
|<span data-ttu-id="2061a-113">**Attività interrotte/sec**</span><span class="sxs-lookup"><span data-stu-id="2061a-113">**Tasks Aborted/sec**</span></span>|<span data-ttu-id="2061a-114">Questo contatore indica il numero di stored procedure di attivazione terminate con un errore o interrotte da un monitoraggio di coda per la mancata ricezione di messaggi.</span><span class="sxs-lookup"><span data-stu-id="2061a-114">This counter reports the number of activation stored procedure tasks that end with an error, or are aborted by a queue monitor for failing to receive messages.</span></span>|  
|<span data-ttu-id="2061a-115">**Attività in esecuzione**</span><span class="sxs-lookup"><span data-stu-id="2061a-115">**Tasks Running**</span></span>|<span data-ttu-id="2061a-116">Questo contatore indica il numero di stored procedure di attivazione attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="2061a-116">This counter reports the number of activation stored procedures that are currently running.</span></span>|  
|<span data-ttu-id="2061a-117">**Attività avviate/sec**</span><span class="sxs-lookup"><span data-stu-id="2061a-117">**Tasks Started/sec**</span></span>|<span data-ttu-id="2061a-118">Questo contatore indica il numero totale di stored procedure di attivazione avviate al secondo da tutti i monitoraggi di coda dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="2061a-118">This counter reports the number of activation stored procedures started per second by all queue monitors in the instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2061a-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2061a-119">See Also</span></span>  
 <span data-ttu-id="2061a-120">[sys.dm_broker_activated_tasks &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-broker-activated-tasks-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2061a-120">[sys.dm_broker_activated_tasks &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-broker-activated-tasks-transact-sql) </span></span>  
 <span data-ttu-id="2061a-121">[sys.dm_broker_queue_monitors &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-broker-queue-monitors-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2061a-121">[sys.dm_broker_queue_monitors &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-broker-queue-monitors-transact-sql) </span></span>  
 [<span data-ttu-id="2061a-122">Monitorare l'utilizzo delle risorse &#40;Monitor di sistema&#41;</span><span class="sxs-lookup"><span data-stu-id="2061a-122">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](monitor-resource-usage-system-monitor.md)  
  
  
