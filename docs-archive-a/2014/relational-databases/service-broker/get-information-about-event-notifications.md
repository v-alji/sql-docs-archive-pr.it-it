---
title: Recuperare informazioni sulle notifiche degli eventi | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- event notifications [SQL Server], metadata
- status information [SQL Server], event notifications
- metadata [SQL Server], event notifications
ms.assetid: 8bc10867-66d6-4f57-ac32-a6c29f3327cd
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c8d8271b6279910321058d01c7b2f96b1df62bd0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716163"
---
# <a name="get-information-about-event-notifications"></a><span data-ttu-id="27628-102">Recupero di informazioni sulle notifiche degli eventi</span><span class="sxs-lookup"><span data-stu-id="27628-102">Get Information About Event Notifications</span></span>
  <span data-ttu-id="27628-103">Le viste del catalogo seguenti sono disponibili per eseguire query sui metadati relative alle notifiche degli eventi.</span><span class="sxs-lookup"><span data-stu-id="27628-103">The following catalog views are available to query metadata about event notifications.</span></span>  
  
 <span data-ttu-id="27628-104">**Per ottenere informazioni relative alle notifiche degli eventi non a livello di server**</span><span class="sxs-lookup"><span data-stu-id="27628-104">**To get information about nonserver-level event notifications**</span></span>  
  
-   [<span data-ttu-id="27628-105">sys.event_notifications &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="27628-105">sys.event_notifications &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-event-notifications-transact-sql)  
  
> [!NOTE]  
>  <span data-ttu-id="27628-106">Per visualizzare i metadati relativi a notifiche degli eventi in **sys.event_notifications** creati a livello del database, è almeno necessario disporre dell'autorizzazione CONTROL, ALTER, TAKE OWNERSHIP oppure VIEW DEFINITION sul database, essere proprietario della notifica degli eventi oppure disporre dell'autorizzazione ALTER ANY DATABASE EVENT NOTIFICATION.</span><span class="sxs-lookup"><span data-stu-id="27628-106">To view metadata about any event notification in **sys.event_notifications** created at the database level, at the minimum you must have the following: CONTROL, ALTER, TAKE OWNERSHIP, or VIEW DEFINITION permission on the database, be the owner of the event notification, or have ALTER ANY DATABASE EVENT NOTIFICATION permission.</span></span> <span data-ttu-id="27628-107">Per le notifiche degli eventi create in una coda specifica, è almeno necessario disporre dell'autorizzazione CONTROL, ALTER, TAKE OWNERSHIP oppure VIEW DEFINITION sull'oggetto, essere proprietario della notifica degli eventi oppure disporre dell'autorizzazione ALTER ANY DATABASE EVENT NOTIFICATION.</span><span class="sxs-lookup"><span data-stu-id="27628-107">For event notifications created on a specific queue, at the minimum you must have the following: CONTROL, ALTER, TAKE OWNERSHIP, or VIEW DEFINITION permission on the object, be the owner of the event notification, or have ALTER ANY DATABASE EVENT NOTIFICATION permission.</span></span>  
  
 <span data-ttu-id="27628-108">**Per ottenere informazioni relative alle notifiche degli eventi a livello di server**</span><span class="sxs-lookup"><span data-stu-id="27628-108">**To get information about server-level event notifications**</span></span>  
  
-   [<span data-ttu-id="27628-109">sys.server_event_notifications &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="27628-109">sys.server_event_notifications &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-server-event-notifications-transact-sql)  
  
> [!NOTE]  
>  <span data-ttu-id="27628-110">È almeno necessario disporre dell'autorizzazione CONTROL o VIEW ANY DEFINITION sul server, essere dotati di accesso o essere il proprietario della notifica degli eventi oppure disporre dell'autorizzazione ALTER ANY EVENT NOTIFICATION per visualizzare i metadati relativi a eventuali notifiche degli eventi in **sys.server_event_notifications**.</span><span class="sxs-lookup"><span data-stu-id="27628-110">At the minimum, you must have the following: CONTROL or VIEW ANY DEFINITION permission on the server, be the logon or owner of the event notification, or have ALTER ANY EVENT NOTIFICATION permission to view metadata about any event notification in **sys.server_event_notifications**.</span></span>  
  
 <span data-ttu-id="27628-111">**Per ottenere informazioni relative a tutti gli eventi che possono attivare notifiche degli eventi**</span><span class="sxs-lookup"><span data-stu-id="27628-111">**To get information about all events that can fire event notifications**</span></span>  
  
-   [<span data-ttu-id="27628-112">sys.event_notification_event_types &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="27628-112">sys.event_notification_event_types &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-event-notification-event-types-transact-sql)  
  
> [!NOTE]  
>  <span data-ttu-id="27628-113">Questa vista del catalogo non restituisce gruppi di eventi.</span><span class="sxs-lookup"><span data-stu-id="27628-113">This catalog view does not return event groups.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27628-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="27628-114">See Also</span></span>  
 [<span data-ttu-id="27628-115">Notifiche degli eventi</span><span class="sxs-lookup"><span data-stu-id="27628-115">Event Notifications</span></span>](event-notifications.md)  
  
  
