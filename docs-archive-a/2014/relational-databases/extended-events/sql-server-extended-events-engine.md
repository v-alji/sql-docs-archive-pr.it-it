---
title: Motore degli eventi estesi di SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xevents
ms.topic: conceptual
helpviewer_keywords:
- extended events [SQL Server], engine
ms.assetid: d74642a5-42b9-4a15-aa3d-f98bfe695050
author: rothja
ms.author: jroth
ms.openlocfilehash: ef11ac8e2cfaf39d2bca90f1d5d52439989ee327
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624164"
---
# <a name="sql-server-extended-events-engine"></a><span data-ttu-id="a6aea-102">Motore degli eventi estesi di SQL Server</span><span class="sxs-lookup"><span data-stu-id="a6aea-102">SQL Server Extended Events Engine</span></span>
  <span data-ttu-id="a6aea-103">Il motore degli eventi estesi di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] è una raccolta di servizi e oggetti che:</span><span class="sxs-lookup"><span data-stu-id="a6aea-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Extended Events engine is a collection of services and objects that:</span></span>  
  
-   <span data-ttu-id="a6aea-104">Abilitano la definizione degli eventi.</span><span class="sxs-lookup"><span data-stu-id="a6aea-104">Enable the definition of events.</span></span>  
  
-   <span data-ttu-id="a6aea-105">Abilitano l'elaborazione dei dati degli eventi.</span><span class="sxs-lookup"><span data-stu-id="a6aea-105">Enable processing event data.</span></span>  
  
-   <span data-ttu-id="a6aea-106">Gestiscono i servizi e gli oggetti degli eventi estesi nel sistema.</span><span class="sxs-lookup"><span data-stu-id="a6aea-106">Manage Extended Events services and objects in the system.</span></span>  
  
-   <span data-ttu-id="a6aea-107">Mantengono un elenco di sessioni degli eventi estesi e gestiscono l'accesso a tale elenco.</span><span class="sxs-lookup"><span data-stu-id="a6aea-107">Maintain a list of Extended Events sessions and manage access to that list.</span></span>  
  
 <span data-ttu-id="a6aea-108">Il motore degli eventi estesi stesso non fornisce alcun evento o azione da intraprendere quando viene generato un evento.</span><span class="sxs-lookup"><span data-stu-id="a6aea-108">The Extended Events engine itself does not provide any events or actions to take when an event fires.</span></span> <span data-ttu-id="a6aea-109">I processi che utilizzano il motore degli eventi estesi definiscono l'interazione con il motore.</span><span class="sxs-lookup"><span data-stu-id="a6aea-109">The processes that use the Extended Events engine define interaction with the engine.</span></span> <span data-ttu-id="a6aea-110">Questi processi aggiungono dei punti evento e forniscono le azioni da intraprendere in risposta alla generazione dell'evento.</span><span class="sxs-lookup"><span data-stu-id="a6aea-110">These processes add event points and supply the actions to take in response to event firing.</span></span>  
  
 <span data-ttu-id="a6aea-111">Nell'illustrazione seguente è mostrata una vista semplificata di una sessione degli eventi estesi.</span><span class="sxs-lookup"><span data-stu-id="a6aea-111">The following illustration shows a simplified view of an Extended Events session.</span></span> <span data-ttu-id="a6aea-112">Per altre informazioni, vedere [Sessioni degli eventi estesi di SQL Server](sql-server-extended-events-sessions.md).</span><span class="sxs-lookup"><span data-stu-id="a6aea-112">For more information, see [SQL Server Extended Events Sessions](sql-server-extended-events-sessions.md).</span></span>  
  
 <span data-ttu-id="a6aea-113">![Architettura dettagliata di eventi estesi](../../database-engine/media/xearchitecturedetailed.gif "Architettura dettagliata di eventi estesi")</span><span class="sxs-lookup"><span data-stu-id="a6aea-113">![Detailed extended events architecture](../../database-engine/media/xearchitecturedetailed.gif "Detailed extended events architecture")</span></span>  
  
 <span data-ttu-id="a6aea-114">Tenere presente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="a6aea-114">Note the following:</span></span>  
  
-   <span data-ttu-id="a6aea-115">Ogni processo di Windows può avere uno o più moduli (**processo Win32**, **modulo Win32**).</span><span class="sxs-lookup"><span data-stu-id="a6aea-115">Each Windows process can have one or more modules (**Win32 process**, **Win32 module**).</span></span> <span data-ttu-id="a6aea-116">Questi sono anche noti come *binari* o *moduli eseguibili*.</span><span class="sxs-lookup"><span data-stu-id="a6aea-116">These are also known as *binaries* or *executable modules*.</span></span>  
  
-   <span data-ttu-id="a6aea-117">Ciascun modulo del processo di Windows può contenere uno o più pacchetti di eventi estesi (**Pacchetto**) contenenti uno o più oggetti eventi estesi (**Tipo**, **Destinazione**, **Azione**, **Mappa**, **Predicato**ed **Evento**).</span><span class="sxs-lookup"><span data-stu-id="a6aea-117">Each of the Windows process modules can contain one or more Extended Events packages (**Package**), which contain one or more Extended Events objects (**Type**, **Target**, **Action**, **Map**, **Predicate**, and **Event**).</span></span>  
  
-   <span data-ttu-id="a6aea-118">In un processo host può esservi solo un'istanza del motore degli eventi estesi (**motore degli eventi estesi**) che:</span><span class="sxs-lookup"><span data-stu-id="a6aea-118">Inside a host process there can only be one instance of the Extended Events engine (**Extended event engine**), which:</span></span>  
  
    -   <span data-ttu-id="a6aea-119">Gestisce alcuni aspetti della sessione (ad esempio, l'enumerazione delle sessioni).</span><span class="sxs-lookup"><span data-stu-id="a6aea-119">Manages some aspects of the session (for example, enumerating sessions).</span></span>  
  
    -   <span data-ttu-id="a6aea-120">Gestisce la distribuzione (**Dispatcher**).</span><span class="sxs-lookup"><span data-stu-id="a6aea-120">Handles dispatching (**Dispatcher**).</span></span> <span data-ttu-id="a6aea-121">Ciò è simile a un pool di thread.</span><span class="sxs-lookup"><span data-stu-id="a6aea-121">This is similar to a thread pool.</span></span>  
  
    -   <span data-ttu-id="a6aea-122">Gestisce buffer di memoria (**Buffer**) per gli eventi.</span><span class="sxs-lookup"><span data-stu-id="a6aea-122">Handles memory buffers (**Buffer**) for events.</span></span> <span data-ttu-id="a6aea-123">Quando i buffer sono riempiti, vengono inviati alle destinazioni.</span><span class="sxs-lookup"><span data-stu-id="a6aea-123">When buffers are filled, the buffers are dispatched to targets.</span></span>  
  
-   <span data-ttu-id="a6aea-124">Dopo che una sessione è stata creata e gli eventi sono associati facoltativamente alla sessione (**Contesto della sessione**):</span><span class="sxs-lookup"><span data-stu-id="a6aea-124">After a session is created and events are optionally bound to the session (**Session context**):</span></span>  
  
    -   <span data-ttu-id="a6aea-125">È possibile creare anche istanze di destinazioni (**Istanza di destinazione**) e aggiungerle alla sessione.</span><span class="sxs-lookup"><span data-stu-id="a6aea-125">Instances of targets (**Target instance**) may be also be created and added to the session.</span></span>  
  
    -   <span data-ttu-id="a6aea-126">Quando i buffer sono riempiti, questi buffer vengono inviati alle destinazioni.</span><span class="sxs-lookup"><span data-stu-id="a6aea-126">When buffers are filled, those buffers are dispatched to targets.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6aea-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a6aea-127">See Also</span></span>  
 [<span data-ttu-id="a6aea-128">Eventi estesi</span><span class="sxs-lookup"><span data-stu-id="a6aea-128">Extended Events</span></span>](extended-events.md)  
  
  
