---
title: Implementare notifiche degli eventi | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- event notifications [SQL Server], target service
- target service [SQL Server]
- event notifications [SQL Server], creating
ms.assetid: 29ac8f68-a28a-4a77-b67b-a8663001308c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6a89c66ca5c3b420fff14c087bd604b16c641369
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629312"
---
# <a name="implement-event-notifications"></a><span data-ttu-id="c4fc6-102">Implementazione di notifiche degli eventi</span><span class="sxs-lookup"><span data-stu-id="c4fc6-102">Implement Event Notifications</span></span>
  <span data-ttu-id="c4fc6-103">Per implementare una notifica degli eventi, è necessario prima creare un servizio di destinazione che riceverà le notifiche degli eventi.</span><span class="sxs-lookup"><span data-stu-id="c4fc6-103">To implement an event notification, you must first create a target service to receive event notifications, and then create the event notification.</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssSB](../../includes/sssb-md.md)] <span data-ttu-id="c4fc6-104">per le notifiche degli eventi che prevedono l'invio di messaggi a Service Broker su un server remoto.</span><span class="sxs-lookup"><span data-stu-id="c4fc6-104">dialog security should be configured for event notifications that send messages to a service broker on a remote server.</span></span> <span data-ttu-id="c4fc6-105">La sicurezza del dialogo deve essere configurata manualmente in base al modello di sicurezza avanzata.</span><span class="sxs-lookup"><span data-stu-id="c4fc6-105">Dialog security must be configured manually according to the full security model.</span></span>  
  
## <a name="creating-the-target-service"></a><span data-ttu-id="c4fc6-106">Creazione del servizio di destinazione</span><span class="sxs-lookup"><span data-stu-id="c4fc6-106">Creating the Target Service</span></span>  
 <span data-ttu-id="c4fc6-107">Non è necessario creare un servizio di origine di [!INCLUDE[ssSB](../../includes/sssb-md.md)]perché [!INCLUDE[ssSB](../../includes/sssb-md.md)] include il tipo di messaggio e di contratto seguente specifico per le notifiche degli eventi:</span><span class="sxs-lookup"><span data-stu-id="c4fc6-107">You do not have to create a [!INCLUDE[ssSB](../../includes/sssb-md.md)]-initiating service because [!INCLUDE[ssSB](../../includes/sssb-md.md)] includes the following specific message type and contract for event notifications:</span></span>  
  
```  
https://schemas.microsoft.com/SQL/Notifications/PostEventNotification  
```  
  
 <span data-ttu-id="c4fc6-108">Il servizio di destinazione che riceve le notifiche degli eventi deve rispettare il contratto esistente.</span><span class="sxs-lookup"><span data-stu-id="c4fc6-108">The target service that receives event notifications must honor this preexisting contract.</span></span>  
  
 <span data-ttu-id="c4fc6-109">**Per creare un server di destinazione**:</span><span class="sxs-lookup"><span data-stu-id="c4fc6-109">**To create a target service**:</span></span>  
  
1.  <span data-ttu-id="c4fc6-110">Creare una coda per ricevere messaggi.</span><span class="sxs-lookup"><span data-stu-id="c4fc6-110">Create a queue to receive messages.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c4fc6-111">La coda riceve il tipo di messaggio seguente: `https://schemas.microsoft.com/SQL/Notifications/QueryNotification`.</span><span class="sxs-lookup"><span data-stu-id="c4fc6-111">The queue receives the following message type: `https://schemas.microsoft.com/SQL/Notifications/QueryNotification`.</span></span>  
  
2.  <span data-ttu-id="c4fc6-112">Creare un servizio nella coda che faccia riferimento al contratto per le notifiche degli eventi.</span><span class="sxs-lookup"><span data-stu-id="c4fc6-112">Create a service on the queue that references the event notifications contract.</span></span>  
  
3.  <span data-ttu-id="c4fc6-113">Creare una route nel servizio per definire l'indirizzo a cui verranno inviati i messaggi per il servizio tramite [!INCLUDE[ssSB](../../includes/sssb-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c4fc6-113">Create a route on the service to define the address to which [!INCLUDE[ssSB](../../includes/sssb-md.md)] sends messages for the service.</span></span> <span data-ttu-id="c4fc6-114">Per le notifiche dell'evento la cui destinazione è rappresentata da un servizio nello stesso database, specificare `ADDRESS = 'LOCAL'`.</span><span class="sxs-lookup"><span data-stu-id="c4fc6-114">For event notifications that target a service in the same database, specify `ADDRESS = 'LOCAL'`.</span></span>  
  
    > [!NOTE]  
    >  [!INCLUDE[ssSB](../../includes/sssb-md.md)] <span data-ttu-id="c4fc6-115">Il routing determina il servizio che riceve i messaggi di notifica.</span><span class="sxs-lookup"><span data-stu-id="c4fc6-115">routing determines the service that receives the notification messages.</span></span> <span data-ttu-id="c4fc6-116">Se la destinazione della notifica degli eventi è rappresentata da un servizio in un server remoto, il server di origine e il server di destinazione dovranno entrambi disporre di route definite che assicurino la corretta comunicazione bidirezionale.</span><span class="sxs-lookup"><span data-stu-id="c4fc6-116">If the event notification targets a service on a remote server, both the source server and the target server must have routes defined on them to make sure that two-way communication occurs.</span></span>  
  
 <span data-ttu-id="c4fc6-117">Nell'esempio seguente vengono creati una coda, un servizio nella coda e una route nel servizio per gestire i messaggi provenienti dal contratto per le notifiche degli eventi.</span><span class="sxs-lookup"><span data-stu-id="c4fc6-117">The following example creates a queue, a service on the queue, and a route on the service to handle messages from the event notification contract.</span></span>  
  
```  
CREATE QUEUE NotifyQueue ;  
GO  
CREATE SERVICE NotifyService  
ON QUEUE NotifyQueue  
(  
[https://schemas.microsoft.com/SQL/Notifications/PostEventNotification]  
);  
GO  
CREATE ROUTE NotifyRoute  
WITH SERVICE_NAME = 'NotifyService',  
ADDRESS = 'LOCAL';  
GO  
```  
  
## <a name="creating-the-event-notification"></a><span data-ttu-id="c4fc6-118">Creazione della notifica degli eventi</span><span class="sxs-lookup"><span data-stu-id="c4fc6-118">Creating the Event Notification</span></span>  
 <span data-ttu-id="c4fc6-119">Le notifiche degli eventi vengono create utilizzando l'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] CREATE EVENT NOTIFICATION e vengono eliminate utilizzando l'istruzione DROP EVENT NOTIFICATION.</span><span class="sxs-lookup"><span data-stu-id="c4fc6-119">Event notifications are created by using the [!INCLUDE[tsql](../../includes/tsql-md.md)] CREATE EVENT NOTIFICATION statement, and are dropped by using the DROP EVENT NOTIFICATION STATEMENT.</span></span> <span data-ttu-id="c4fc6-120">Per modificare la notifica di un evento, è necessario eliminarla e quindi ricrearla.</span><span class="sxs-lookup"><span data-stu-id="c4fc6-120">To modify an event notification, you must drop and re-create the event notification.</span></span>  
  
 <span data-ttu-id="c4fc6-121">Nell'esempio seguente viene creata la notifica di evento `CreateDatabaseNotification`.</span><span class="sxs-lookup"><span data-stu-id="c4fc6-121">The following example creates the event notification `CreateDatabaseNotification`.</span></span> <span data-ttu-id="c4fc6-122">Per ogni evento `CREATE_DATABASE` generato nel server, questa notifica invia un messaggio al servizio `NotifyService` creato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="c4fc6-122">This notification sends a message about any `CREATE_DATABASE` event that occurs on the server to the `NotifyService` service that was previously created.</span></span>  
  
```  
CREATE EVENT NOTIFICATION CreateDatabaseNotification  
ON SERVER  
FOR CREATE_DATABASE  
TO SERVICE 'NotifyService', '8140a771-3c4b-4479-8ac0-81008ab17984' ;  
```  
  
> [!CAUTION]  
>  <span data-ttu-id="c4fc6-123">Le notifiche degli eventi riconoscono gli eventi CREATE_SCHEMA e le definizioni <schema_element> delle istruzioni CREATE SCHEMA come eventi distinti.</span><span class="sxs-lookup"><span data-stu-id="c4fc6-123">Event notifications recognize CREATE_SCHEMA events and the <schema_element> definitions of CREATE SCHEMA statements as separate events.</span></span> <span data-ttu-id="c4fc6-124">Si supponga ad esempio di creare una notifica di evento in entrambi gli eventi CREATE_SCHEMA e CREATE_TABLE e di eseguire il batch seguente.</span><span class="sxs-lookup"><span data-stu-id="c4fc6-124">For example, an event notification is created on both the CREATE_SCHEMA and CREATE_TABLE events, and you run the following batch.</span></span>  
>   
>  `CREATE SCHEMA s`  
>   
>  `CREATE TABLE t1 (col1 int)`  
>   
>  <span data-ttu-id="c4fc6-125">In questo caso la notifica dell'evento viene generata due volte, una prima volta quando viene generato l'evento CREATE_SCHEMA e una seconda volta quando viene generato l'evento CREATE_TABLE.</span><span class="sxs-lookup"><span data-stu-id="c4fc6-125">In this case, the event notification is raised two times: Onne time when the CREATE_SCHEMA event occurs, and again when the CREATE_TABLE event occurs.</span></span> <span data-ttu-id="c4fc6-126">È consigliabile non creare notifiche degli eventi sia negli eventi CREATE_SCHEMA che nel testo <schema_element> delle definizioni CREATE SCHEMA corrispondenti. In alternativa, compilare nell'applicazione la logica necessaria a evitare di acquisire dati per eventi non desiderati.</span><span class="sxs-lookup"><span data-stu-id="c4fc6-126">We recommend that you either avoid creating event notifications on both the CREATE_SCHEMA events and the <schema_element> texts of any corresponding CREATE SCHEMA definitions, or build logic into your application to avoid capturing unwanted event data.</span></span>  
  
 <span data-ttu-id="c4fc6-127">**Per creare la notifica di un evento**</span><span class="sxs-lookup"><span data-stu-id="c4fc6-127">**To create an event notification**</span></span>  
  
-   [<span data-ttu-id="c4fc6-128">CREATE EVENT NOTIFICATION &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c4fc6-128">CREATE EVENT NOTIFICATION &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-event-notification-transact-sql)  
  
 <span data-ttu-id="c4fc6-129">**Per eliminare la notifica di un evento**</span><span class="sxs-lookup"><span data-stu-id="c4fc6-129">**To drop an event notification**</span></span>  
  
-   [<span data-ttu-id="c4fc6-130">DROP EVENT NOTIFICATION &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c4fc6-130">DROP EVENT NOTIFICATION &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-event-notification-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="c4fc6-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c4fc6-131">See Also</span></span>  
 <span data-ttu-id="c4fc6-132">[Recupero di informazioni sulle notifiche degli eventi](event-notifications.md) </span><span class="sxs-lookup"><span data-stu-id="c4fc6-132">[Get Information About Event Notifications](event-notifications.md) </span></span>  
 [<span data-ttu-id="c4fc6-133">EVENTDATA &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c4fc6-133">EVENTDATA &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/eventdata-transact-sql)  
  
  
