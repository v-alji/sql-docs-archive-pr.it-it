---
title: L'aggiornamento modificherà le sottoscrizioni ad aggiornamento in coda che utilizzano Accodamento messaggi | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- subscriptions [SQL Server replication]
- MSMQ [SQL Server replication]
- queues [SQL Server replication]
- queued updating subscriptions [SQL Server replication]
ms.assetid: 97944de3-fbad-4db1-939a-dcd550bf5893
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: d44cbad43d75634cbf8660110cc879522265c54d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726448"
---
# <a name="upgrading-will-modify-queued-updating-subscriptions-that-use-message-queuing"></a><span data-ttu-id="129f9-102">In seguito all'aggiornamento le sottoscrizioni ad aggiornamento in coda che utilizzano MSMQ verranno modificate in modo da utilizzare code di SQL Server</span><span class="sxs-lookup"><span data-stu-id="129f9-102">Upgrading will modify queued updating subscriptions that use Message Queuing</span></span>
  <span data-ttu-id="129f9-103">È possibile che una o più sottoscrizioni ad aggiornamento in coda utilizzino [!INCLUDE[msCoName](../../includes/msconame-md.md)] Message Queuing (noto anche come MSMQ).</span><span class="sxs-lookup"><span data-stu-id="129f9-103">Upgrade Advisor detected that you might have one or more queued updating subscriptions that use [!INCLUDE[msCoName](../../includes/msconame-md.md)] Message Queuing (also known as MSMQ).</span></span> <span data-ttu-id="129f9-104">Accodamento messaggi non è più supportato dalla replica, quindi le sottoscrizioni verranno modificate in modo che utilizzino una coda di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="129f9-104">Replication no longer supports Message Queuing; therefore, the subscriptions will be modified to use a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] queue.</span></span>  
  
 <span data-ttu-id="129f9-105">È consentito solo un valore **SQL** .</span><span class="sxs-lookup"><span data-stu-id="129f9-105">Only a value of **sql** is allowed.</span></span> <span data-ttu-id="129f9-106">Le pubblicazioni esistenti che utilizzano Accodamento messaggi vengono modificate durante l'aggiornamento in modo da utilizzare una coda di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="129f9-106">Existing publications that use Message Queuing are modified during upgrade to use a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] queue.</span></span> <span data-ttu-id="129f9-107">Se si dispone di applicazioni che dipendono da un aggiornamento in coda tramite Message Queuing, sarà necessario riscrivere tali applicazioni per includere una coda di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="129f9-107">If you have applications that depend on queued updating using Message Queuing, these applications will have to be rewritten to accommodate a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] queue.</span></span> <span data-ttu-id="129f9-108">Per ulteriori informazioni sulle sottoscrizioni ad aggiornamento in coda, vedere "Sottoscrizioni aggiornabili per la replica transazionale" nella documentazione online di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="129f9-108">For more information about queued updating subscriptions, see "Updatable Subscriptions for Transactional Replication" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
 <span data-ttu-id="129f9-109">Con l'aggiornamento, le code di sottoscrizione MSMQ vengono rimosse se il servizio di accodamento messaggi è in esecuzione durante l'aggiornamento di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="129f9-109">Upgrade will remove the existing Message Queuing subscription queues if the Message Queuing service is running while [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is being upgraded.</span></span>  
  
 <span data-ttu-id="129f9-110">Se il servizio di accodamento messaggi non è in esecuzione, rimuovere manualmente le code al termine dell'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="129f9-110">If the Message Queuing service is not running, remove the queues manually after upgrade is complete.</span></span> <span data-ttu-id="129f9-111">Per ulteriori informazioni sulla rimozione di code, vedere la documentazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="129f9-111">For more information about how to remove queues, see the Windows documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="129f9-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="129f9-112">See Also</span></span>  
 [<span data-ttu-id="129f9-113">Problemi di aggiornamento della replica</span><span class="sxs-lookup"><span data-stu-id="129f9-113">Replication Upgrade Issues</span></span>](../../../2014/sql-server/install/replication-upgrade-issues.md)  
  
  
