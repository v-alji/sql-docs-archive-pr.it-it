---
title: Categoria di eventi Broker | Microsoft Docs
ms.custom: ''
ms.date: 07/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- SQL Server event classes, Broker event category
- Broker event category [SQL Server]
- event classes [SQL Server], Broker event category
ms.assetid: 470dc93c-0dda-4d89-829b-937738d59b31
author: stevestein
ms.author: sstein
ms.openlocfilehash: 23f839416e3404bfdf0a7e61d1b1e8dbbb90ec95
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624772"
---
# <a name="broker-event-category"></a><span data-ttu-id="d4572-102">Categoria di eventi Broker</span><span class="sxs-lookup"><span data-stu-id="d4572-102">Broker Event Category</span></span>
  <span data-ttu-id="d4572-103">La categoria di eventi **Broker** include gli eventi generali di Service Broker.</span><span class="sxs-lookup"><span data-stu-id="d4572-103">The **Broker** event category contains general Service Broker events.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d4572-104">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="d4572-104">In This Section</span></span>  
  
|<span data-ttu-id="d4572-105">Argomento</span><span class="sxs-lookup"><span data-stu-id="d4572-105">Topic</span></span>|<span data-ttu-id="d4572-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d4572-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="d4572-107">Classe di evento Broker:Activation</span><span class="sxs-lookup"><span data-stu-id="d4572-107">Broker:Activation Event Class</span></span>](broker-activation-event-class.md)|<span data-ttu-id="d4572-108">Evento generato quando un monitoraggio di coda avvia una stored procedure di attivazione.</span><span class="sxs-lookup"><span data-stu-id="d4572-108">An event generated when a queue monitor starts an activation stored procedure.</span></span>|  
|[<span data-ttu-id="d4572-109">Classe di evento Broker:Connection</span><span class="sxs-lookup"><span data-stu-id="d4572-109">Broker:Connection Event Class</span></span>](broker-connection-event-class.md)|<span data-ttu-id="d4572-110">Evento generato per indicare lo stato di una connessione di trasporto gestita da Service Broker.</span><span class="sxs-lookup"><span data-stu-id="d4572-110">An event generated to report the status of a transport connection managed by Service Broker.</span></span>|  
|[<span data-ttu-id="d4572-111">Classe di evento Broker:Conversation</span><span class="sxs-lookup"><span data-stu-id="d4572-111">Broker:Conversation Event Class</span></span>](broker-conversation-event-class.md)|<span data-ttu-id="d4572-112">Evento generato per indicare lo stato di una conversazione.</span><span class="sxs-lookup"><span data-stu-id="d4572-112">An event generated to report the progress of a conversation.</span></span>|  
|[<span data-ttu-id="d4572-113">Classe di evento Broker:Conversation Group</span><span class="sxs-lookup"><span data-stu-id="d4572-113">Broker:Conversation Group Event Class</span></span>](broker-conversation-group-event-class.md)|<span data-ttu-id="d4572-114">Evento generato quando il database crea o elimina un gruppo di conversazione.</span><span class="sxs-lookup"><span data-stu-id="d4572-114">An event generated when the database creates or drops a conversation group.</span></span>|  
|[<span data-ttu-id="d4572-115">Classe di evento Broker:Corrupted Message</span><span class="sxs-lookup"><span data-stu-id="d4572-115">Broker:Corrupted Message Event Class</span></span>](broker-corrupted-message-event-class.md)|<span data-ttu-id="d4572-116">Evento generato per indicare che il database ha ricevuto un messaggio danneggiato.</span><span class="sxs-lookup"><span data-stu-id="d4572-116">An event generated to report that the database has received a corrupt message.</span></span>|  
|[<span data-ttu-id="d4572-117">Classe di evento Broker:Forwarded Message Dropped</span><span class="sxs-lookup"><span data-stu-id="d4572-117">Broker:Forwarded Message Dropped Event Class</span></span>](broker-forwarded-message-dropped-event-class.md)|<span data-ttu-id="d4572-118">Evento generato quando SQL Server elimina un messaggio di Service Broker per cui era previsto l'inoltro.</span><span class="sxs-lookup"><span data-stu-id="d4572-118">An event generated when SQL Server drops a Service Broker message that was to have been forwarded.</span></span>|  
|[<span data-ttu-id="d4572-119">Classe di evento Broker:Forwarded Message Sent</span><span class="sxs-lookup"><span data-stu-id="d4572-119">Broker:Forwarded Message Sent Event Class</span></span>](broker-forwarded-message-sent-event-class.md)|<span data-ttu-id="d4572-120">Evento generato quando SQL Server inoltra un messaggio di Service Broker.</span><span class="sxs-lookup"><span data-stu-id="d4572-120">An event generated when SQL Server forwards a Service Broker message.</span></span>|  
|[<span data-ttu-id="d4572-121">Classe di evento Broker:Message Classify</span><span class="sxs-lookup"><span data-stu-id="d4572-121">Broker:Message Classify Event Class</span></span>](broker-message-classify-event-class.md)|<span data-ttu-id="d4572-122">Evento generato quando Service Broker stabilisce il routing di un messaggio.</span><span class="sxs-lookup"><span data-stu-id="d4572-122">An event generated when Service Broker determines the routing for a message.</span></span>|  
|[<span data-ttu-id="d4572-123">Classe di evento Broker:Message Drop</span><span class="sxs-lookup"><span data-stu-id="d4572-123">Broker:Message Drop Event Class</span></span>](broker-message-drop-event-class.md)|<span data-ttu-id="d4572-124">Evento generato quando Service Broker non è in grado di memorizzare un messaggio ricevuto che avrebbe dovuto essere recapitato a un servizio nell'istanza corrente.</span><span class="sxs-lookup"><span data-stu-id="d4572-124">An event generated when Service Broker is unable to retain a received message that should have been delivered to a service in this instance</span></span>|  
|[<span data-ttu-id="d4572-125">Classe di evento Broker:Remote Message Ack</span><span class="sxs-lookup"><span data-stu-id="d4572-125">Broker:Remote Message Ack Event Class</span></span>](broker-remote-message-ack-event-class.md)|<span data-ttu-id="d4572-126">Evento generato quando Service Broker invia o riceve l'acknowledgement di un messaggio.</span><span class="sxs-lookup"><span data-stu-id="d4572-126">An event generated when Service Broker sends or receives a message acknowledgement.</span></span>|  
  
 <span data-ttu-id="d4572-127">Vengono inoltre generati due eventi di controllo della sicurezza per Service Broker.</span><span class="sxs-lookup"><span data-stu-id="d4572-127">Two security audit events are also provided for Service Broker.</span></span> <span data-ttu-id="d4572-128">Per altre informazioni sugli eventi, vedere [Classe di evento Audit Broker Login](audit-broker-login-event-class.md) e [Classe di evento Audit Broker Conversation](audit-broker-conversation-event-class.md).</span><span class="sxs-lookup"><span data-stu-id="d4572-128">For more information on those events, see [Audit Broker Login Event Class](audit-broker-login-event-class.md) and [Audit Broker Conversation Event Class](audit-broker-conversation-event-class.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4572-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d4572-129">See Also</span></span>  
 [<span data-ttu-id="d4572-130">Categoria di eventi Controllo di sicurezza</span><span class="sxs-lookup"><span data-stu-id="d4572-130">Security Audit Event Category</span></span>](https://docs.microsoft.com/bi-reference/trace-events/security-audit-event-category)  
  
  
