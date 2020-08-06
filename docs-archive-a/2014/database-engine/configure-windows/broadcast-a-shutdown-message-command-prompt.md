---
title: Trasmettere un messaggio di chiusura (prompt dei comandi) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- SQL Server, stopping
- named instances [SQL Server], broadcasting shutdown messages
- shutdown message broadcast
- broadcasting shutdown message
- command prompt [SQL Server], broadcasting shutdown messages
- default instances [SQL Server], broadcasting shutdown messages
- stopping SQL Server
ms.assetid: 9f20ccd5-d952-431d-ba12-339911af9430
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 540baada4a78d7b5caf54cbabb9196ce5a79780e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716808"
---
# <a name="broadcast-a-shutdown-message-command-prompt"></a><span data-ttu-id="416d6-102">Trasmissione di un messaggio di chiusura (prompt dei comandi)</span><span class="sxs-lookup"><span data-stu-id="416d6-102">Broadcast a Shutdown Message (Command Prompt)</span></span>
  <span data-ttu-id="416d6-103">Questo argomento illustra come trasmettere un messaggio di arresto in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando il comando **net send** .</span><span class="sxs-lookup"><span data-stu-id="416d6-103">This topic describes how to broadcast a shutdown message in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using the **net send** command.</span></span> <span data-ttu-id="416d6-104">Specificare nel messaggio l'orario di arresto dell'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , in modo da consentire agli utenti di completare le attività in corso.</span><span class="sxs-lookup"><span data-stu-id="416d6-104">In the message, include the time the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will be stopped so that users can finish their tasks.</span></span>  
  
##  <a name="SSMSProcedure"></a>  
  
#### <a name="to-broadcast-a-shutdown-message"></a><span data-ttu-id="416d6-105">Per trasmettere un messaggio di arresto</span><span class="sxs-lookup"><span data-stu-id="416d6-105">To broadcast a shutdown message</span></span>  
  
1.  <span data-ttu-id="416d6-106">Dal prompt dei comandi digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="416d6-106">From a command prompt, enter:</span></span>  
  
     <span data-ttu-id="416d6-107">**net send /users "messaggio"**</span><span class="sxs-lookup"><span data-stu-id="416d6-107">**net send /users "message"**</span></span>  
  
     <span data-ttu-id="416d6-108">L'opzione **/users** specifica che il messaggio verrà inviato a tutti gli utenti connessi al server</span><span class="sxs-lookup"><span data-stu-id="416d6-108">The **/users** option specifies that the message be sent to all users connected to the server</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="416d6-109">Per usare il comando **net send** è necessario che sia in esecuzione il servizio Messenger sia sul computer che invia il messaggio sia sui computer che dovranno riceverlo.</span><span class="sxs-lookup"><span data-stu-id="416d6-109">The **net send** command requires the messenger service to be running on both the sending and the receiving computers.</span></span> <span data-ttu-id="416d6-110">In Windows Server 2003 il servizio Messenger è disabilitato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="416d6-110">The messenger service is disabled by default on Windows Server 2003.</span></span> <span data-ttu-id="416d6-111">Per informazioni sul comando **net send**, vedere la documentazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="416d6-111">For information about **net send**, see the Windows documentation.</span></span>  
  
 <span data-ttu-id="416d6-112">In alcune reti potrebbe essere più appropriato contattare gli utenti per posta elettronica o telefonicamente.</span><span class="sxs-lookup"><span data-stu-id="416d6-112">On your network, it may be more appropriate to contact users by e-mail or the telephone.</span></span> <span data-ttu-id="416d6-113">Utilizzare Monitor attività per determinare quali utenti sono attualmente connessi a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="416d6-113">To determine which users are currently connected to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], use the Activity Monitor.</span></span> <span data-ttu-id="416d6-114">Per informazioni su Monitoraggio attività, vedere [Monitoraggio attività](../../relational-databases/performance-monitor/activity-monitor.md) e [Aprire Monitoraggio attività &#40;SQL Server Management Studio&#41;](../../relational-databases/performance-monitor/open-activity-monitor-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="416d6-114">For information on the Activity Monitor, see [Activity Monitor](../../relational-databases/performance-monitor/activity-monitor.md) and [Open Activity Monitor &#40;SQL Server Management Studio&#41;](../../relational-databases/performance-monitor/open-activity-monitor-sql-server-management-studio.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="416d6-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="416d6-115">See Also</span></span>  
 [<span data-ttu-id="416d6-116">Avviare, arrestare, sospendere, riprendere, riavviare il motore di database, SQL Server Agent o SQL Server Browser</span><span class="sxs-lookup"><span data-stu-id="416d6-116">Start, Stop, Pause, Resume, Restart the Database Engine, SQL Server Agent, or SQL Server Browser Service</span></span>](start-stop-pause-resume-restart-sql-server-services.md)  
  
  
