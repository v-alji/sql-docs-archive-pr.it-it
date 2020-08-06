---
title: Sottoscrizione, comandi non distribuiti (sottoscrizione transazionale, SQL Server 2005 e versioni successive) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.subscription.performance.f1
ms.assetid: 5451561e-0ce3-4bb5-844a-88cd15b0b371
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6bbd82b4f4855c99076404d8b621edca11a7e1e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715184"
---
# <a name="subscription-undistributed-commands-transactional-subscription-sql-server-2005-and-later"></a><span data-ttu-id="c4ab3-102">Sottoscrizione, Comandi non distribuiti (sottoscrizione transazionale, SQL Server 2005 e versioni successive)</span><span class="sxs-lookup"><span data-stu-id="c4ab3-102">Subscription, Undistributed Commands (Transactional Subscription, SQL Server 2005 and Later)</span></span>
  <span data-ttu-id="c4ab3-103">La scheda **Comandi non distribuiti** visualizza informazioni sul numero di comandi nel database di distribuzione che non sono stati recapitati al Sottoscrittore selezionato e il tempo previsto per il recapito di tali comandi.</span><span class="sxs-lookup"><span data-stu-id="c4ab3-103">The **Undistributed Commands** tab displays information about the number of commands in the distribution database that have not been delivered to the selected Subscriber, and the estimated time to deliver those commands.</span></span> <span data-ttu-id="c4ab3-104">Per informazioni sulla visualizzazione dei comandi nel database di distribuzione, vedere [sp_replshowcmds &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replshowcmds-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c4ab3-104">For information about viewing the commands in the distribution database, see [sp_replshowcmds &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replshowcmds-transact-sql).</span></span>  
  
## <a name="options"></a><span data-ttu-id="c4ab3-105">Opzioni</span><span class="sxs-lookup"><span data-stu-id="c4ab3-105">Options</span></span>  
 <span data-ttu-id="c4ab3-106">**Numero di comandi nel database di distribuzione in attesa di essere applicati al Sottoscrittore**</span><span class="sxs-lookup"><span data-stu-id="c4ab3-106">**Number of commands in the distribution database waiting to be applied to this Subscriber**</span></span>  
 <span data-ttu-id="c4ab3-107">Numero di comandi nel database di distribuzione che non sono stati recapitati al Sottoscrittore selezionato.</span><span class="sxs-lookup"><span data-stu-id="c4ab3-107">The number of commands in the distribution database that have not been delivered to the selected Subscriber.</span></span> <span data-ttu-id="c4ab3-108">Un comando è composto da un'istruzione DDL (Data Definition Language) o da un'istruzione DML (Data Manipulation Language) Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="c4ab3-108">A command consists of one Transact-SQL data manipulation language (DML) statement or one data definition language (DDL) statement.</span></span>  
  
 <span data-ttu-id="c4ab3-109">**Tempo previsto per l'applicazione di questi comandi, sulla base delle prestazioni passate**</span><span class="sxs-lookup"><span data-stu-id="c4ab3-109">**Estimated time to apply these commands, based on past performance**</span></span>  
 <span data-ttu-id="c4ab3-110">Tempo stimato per il recapito dei comandi al Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="c4ab3-110">The estimated amount of time to deliver commands to the Subscriber.</span></span> <span data-ttu-id="c4ab3-111">Se questo valore è maggiore del tempo necessario per generare uno snapshot e applicarlo al Sottoscrittore, potrebbe risultare conveniente reinizializzare il Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="c4ab3-111">If this value is greater than the amount of time required to generate and apply a snapshot to the Subscriber, consider reinitializing the Subscriber.</span></span> <span data-ttu-id="c4ab3-112">Per altre informazioni, vedere [Reinizializzare le sottoscrizioni](reinitialize-subscriptions.md).</span><span class="sxs-lookup"><span data-stu-id="c4ab3-112">For more information, see [Reinitialize Subscriptions](reinitialize-subscriptions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4ab3-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c4ab3-113">See Also</span></span>  
 <span data-ttu-id="c4ab3-114">[Avviare Monitoraggio replica](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="c4ab3-114">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="c4ab3-115">[Monitorare le prestazioni con monitoraggio replica](monitor/monitor-performance-with-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="c4ab3-115">[Monitor Performance with Replication Monitor](monitor/monitor-performance-with-replication-monitor.md) </span></span>  
 [<span data-ttu-id="c4ab3-116">Monitoraggio della replica</span><span class="sxs-lookup"><span data-stu-id="c4ab3-116">Monitoring Replication</span></span>](monitoring-replication.md)  
  
  
