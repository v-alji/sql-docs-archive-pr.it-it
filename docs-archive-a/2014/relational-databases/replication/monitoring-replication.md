---
title: Monitoraggio della replica | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- monitoring performance [SQL Server replication], about monitoring replication
- transactional replication, monitoring
- monitoring [SQL Server replication]
- merge replication monitoring [SQL Server replication]
- snapshot replication [SQL Server], monitoring
- replication [SQL Server], monitoring
- administering replication, monitoring
ms.assetid: f182f43a-6af8-45bc-a708-08d5f7a6984a
author: rothja
ms.author: jroth
ms.openlocfilehash: df2760e4ce04c95f38ceb9dfe9fa9f79c4c467f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718005"
---
# <a name="monitoring-replication"></a><span data-ttu-id="c7b23-102">Monitoraggio (replica)</span><span class="sxs-lookup"><span data-stu-id="c7b23-102">Monitoring (Replication)</span></span>
  <span data-ttu-id="c7b23-103">Il monitoraggio di una topologia di replica rappresenta un aspetto essenziale della distribuzione di una replica.</span><span class="sxs-lookup"><span data-stu-id="c7b23-103">Monitoring a replication topology is an important aspect of deploying replication.</span></span> <span data-ttu-id="c7b23-104">Dato che l'attività di replica viene distribuita, è fondamentale monitorarne l'attività e lo stato su tutti i computer interessati.</span><span class="sxs-lookup"><span data-stu-id="c7b23-104">Because replication activity is distributed, it is essential to track activity and status across all computers involved in replication.</span></span> <span data-ttu-id="c7b23-105">Per monitorare la replica è possibile utilizzare gli strumenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="c7b23-105">The following tools can be used to monitor replication:</span></span>  
  
-   [!INCLUDE[msCoName](../../includes/msCoName-md.md)]<span data-ttu-id="c7b23-106">[!INCLUDE[ssNoVersion](../../includes/ssNoVersion-md.md)]Monitoraggio replica</span><span class="sxs-lookup"><span data-stu-id="c7b23-106">[!INCLUDE[ssNoVersion](../../includes/ssNoVersion-md.md)] Replication Monitor</span></span>  
  
     <span data-ttu-id="c7b23-107">Monitoraggio replica è lo strumento principale per il monitoraggio della replica, caratterizzato da una vista dell'intera attività di replica con priorità al server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="c7b23-107">Replication Monitor is the most important tool for monitoring replication, presenting a Publisher-focused view of all replication activity.</span></span> <span data-ttu-id="c7b23-108">Per ulteriori informazioni, vedere [monitoraggio delle prestazioni con monitoraggio replica](monitor/monitor-performance-with-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="c7b23-108">For more information, see [Monitor performance with Replication Monitor](monitor/monitor-performance-with-replication-monitor.md).</span></span>  
  
-   [!INCLUDE[msCoName](../../includes/msCoName-md.md)] <span data-ttu-id="c7b23-109">[!INCLUDE[ssManStudioFull](../../includes/ssManStudioFull-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7b23-109">[!INCLUDE[ssManStudioFull](../../includes/ssManStudioFull-md.md)]</span></span>  
  
     [!INCLUDE[ssManStudio](../../includes/ssManStudio-md.md)] <span data-ttu-id="c7b23-110">consente di accedere a Monitoraggio replica.</span><span class="sxs-lookup"><span data-stu-id="c7b23-110">provides access to Replication Monitor.</span></span> <span data-ttu-id="c7b23-111">Consente anche di visualizzare lo stato attuale e l'ultimo messaggio registrato dagli agenti seguenti e di avviare e arrestare ogni agente: agente di lettura log, agente di snapshot, agente di merge e agente di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="c7b23-111">It also allows you to view the current status and last message logged by the following agents and allows you start and stop each agent: Log Reader Agent, Snapshot Agent, Merge Agent, and Distribution Agent.</span></span> <span data-ttu-id="c7b23-112">Per altre informazioni, vedere [Monitor Replication Agents](monitor/monitor-replication-agents.md).</span><span class="sxs-lookup"><span data-stu-id="c7b23-112">For more information, see [Monitor Replication Agents](monitor/monitor-replication-agents.md).</span></span>  
  
-   [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="c7b23-113">e oggetti RMO (Replication Management Objects)</span><span class="sxs-lookup"><span data-stu-id="c7b23-113">and Replication Management Objects (RMO)</span></span>  
  
     <span data-ttu-id="c7b23-114">Entrambe le interfacce consentono di monitorare tutti i tipi di replica dal server di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="c7b23-114">Both interfaces allow you to monitor all types of replication from the Distributor.</span></span> <span data-ttu-id="c7b23-115">La replica di tipo merge consente inoltre di monitorare la replica dal Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="c7b23-115">Merge replication also provides the ability to monitor replication from the Subscriber.</span></span>  
  
-   <span data-ttu-id="c7b23-116">Avvisi per gli eventi degli agenti di replica</span><span class="sxs-lookup"><span data-stu-id="c7b23-116">Alerts for replication agent events</span></span>  
  
     <span data-ttu-id="c7b23-117">Durante la replica sono disponibili vari avvisi predefiniti per gli eventi degli agenti di replica. Se necessario, è inoltre possibile crearne di nuovi.</span><span class="sxs-lookup"><span data-stu-id="c7b23-117">Replication provides a number of predefined alerts for replication agent events, and you can create additional alerts if necessary.</span></span> <span data-ttu-id="c7b23-118">Gli avvisi possono essere utilizzati per avviare una risposta automatica in seguito a un evento e/o per inviare notifiche all'amministratore.</span><span class="sxs-lookup"><span data-stu-id="c7b23-118">Alerts can be used to trigger an automated response to an event and/or notify an administrator.</span></span> <span data-ttu-id="c7b23-119">Per altre informazioni, vedere [Usare gli avvisi per gli eventi degli agenti di replica](agents/use-alerts-for-replication-agent-events.md).</span><span class="sxs-lookup"><span data-stu-id="c7b23-119">For more information, see [Use Alerts for Replication Agent Events](agents/use-alerts-for-replication-agent-events.md).</span></span>  
  
-   <span data-ttu-id="c7b23-120">Monitor di sistema</span><span class="sxs-lookup"><span data-stu-id="c7b23-120">System Monitor</span></span>  
  
     <span data-ttu-id="c7b23-121">Questa opzione può essere utile per monitorare le prestazioni della replica tramite vari contatori.</span><span class="sxs-lookup"><span data-stu-id="c7b23-121">System Monitor can be useful for monitoring performance, providing a number of counters for replication.</span></span> <span data-ttu-id="c7b23-122">Per altre informazioni, vedere [Monitoring Replication with System Monitor](monitor/monitoring-replication-with-system-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="c7b23-122">For more information, see [Monitoring Replication with System Monitor](monitor/monitoring-replication-with-system-monitor.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7b23-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c7b23-123">See Also</span></span>  
 <span data-ttu-id="c7b23-124">[Domande frequenti sull'amministrazione della replica](administration/frequently-asked-questions-for-replication-administrators.md) </span><span class="sxs-lookup"><span data-stu-id="c7b23-124">[Replication Administration FAQ](administration/frequently-asked-questions-for-replication-administrators.md) </span></span>  
 [<span data-ttu-id="c7b23-125">Best Practices for Replication Administration</span><span class="sxs-lookup"><span data-stu-id="c7b23-125">Best Practices for Replication Administration</span></span>](administration/best-practices-for-replication-administration.md)   

  
  
