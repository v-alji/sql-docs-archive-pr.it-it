---
title: Gestire eventi | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- event forwarding servers [SQL Server]
- events [SQL Server], forwarding
- event-triggered jobs [SQL Server]
- forwarding events [SQL Server]
- alerts [SQL Server], forwarded events
- alerts [SQL Server], management servers
- SQL Server Agent alerts, management servers
ms.assetid: 8f4ee7f5-80df-49fd-b2b8-d020e04b6e1b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7ca6d56440b06d285cbb90f8d92325d59a452c16
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711579"
---
# <a name="manage-events"></a><span data-ttu-id="9debf-102">Gestione di eventi</span><span class="sxs-lookup"><span data-stu-id="9debf-102">Manage Events</span></span>
  <span data-ttu-id="9debf-103">È possibile inoltrare a un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tutti i messaggi di evento con livello di gravità dell'errore corrispondente o superiore a un determinato valore.</span><span class="sxs-lookup"><span data-stu-id="9debf-103">You can forward to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] all event messages that meet or exceed a specific error severity level.</span></span> <span data-ttu-id="9debf-104">Questa caratteristica è nota come *inoltro degli eventi*.</span><span class="sxs-lookup"><span data-stu-id="9debf-104">This is called *event forwarding*.</span></span> <span data-ttu-id="9debf-105">Il server di inoltro è un server dedicato che può essere anche un server master.</span><span class="sxs-lookup"><span data-stu-id="9debf-105">The forwarding server is a dedicated server that can also be a master server.</span></span> <span data-ttu-id="9debf-106">L'inoltro degli eventi consente di gestire in modo centralizzato gli avvisi per un gruppo di server, riducendo in tal modo il carico di lavoro per i server utilizzati molto frequentemente.</span><span class="sxs-lookup"><span data-stu-id="9debf-106">You can use event forwarding to centralize alert management for a group of servers, thereby reducing the workload on heavily used servers.</span></span>  
  
 <span data-ttu-id="9debf-107">Un singolo server che riceve gli eventi per un gruppo di altri server è denominato *server di gestione avvisi*.</span><span class="sxs-lookup"><span data-stu-id="9debf-107">When one server receives events for a group of other servers, the server that receives events is called an *alerts management server*.</span></span> <span data-ttu-id="9debf-108">In un ambiente multiserver come server di gestione degli avvisi viene scelto il server master.</span><span class="sxs-lookup"><span data-stu-id="9debf-108">In a multiserver environment, you designate the master server as the alerts management server.</span></span>  
  
## <a name="advantages-of-using-an-alerts-management-server"></a><span data-ttu-id="9debf-109">Vantaggi derivanti dall'utilizzo di un server di gestione degli avvisi</span><span class="sxs-lookup"><span data-stu-id="9debf-109">Advantages of Using an Alerts Management Server</span></span>  
 <span data-ttu-id="9debf-110">I vantaggi derivanti dall'impostazione di un server di gestione degli avvisi sono:</span><span class="sxs-lookup"><span data-stu-id="9debf-110">The advantages of setting up an alerts management server include:</span></span>  
  
-   <span data-ttu-id="9debf-111">**Centralizzazione**.</span><span class="sxs-lookup"><span data-stu-id="9debf-111">**Centralization**.</span></span> <span data-ttu-id="9debf-112">Da un unico server è possibile controllare in modo centralizzato e visualizzare globalmente gli eventi di più istanze di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9debf-112">Centralized control and a consolidated view of the events of several instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are possible from a single server.</span></span>  
  
-   <span data-ttu-id="9debf-113">**Scalabilità**.</span><span class="sxs-lookup"><span data-stu-id="9debf-113">**Scalability**.</span></span> <span data-ttu-id="9debf-114">È possibile amministrare molti server fisici come un unico server logico,</span><span class="sxs-lookup"><span data-stu-id="9debf-114">Many physical servers can be administered as one logical server.</span></span> <span data-ttu-id="9debf-115">nonché aggiungere o rimuovere server da questo gruppo di server fisici a seconda delle necessità.</span><span class="sxs-lookup"><span data-stu-id="9debf-115">You can add or remove servers to this physical server group as needed.</span></span>  
  
-   <span data-ttu-id="9debf-116">**Efficienza**.</span><span class="sxs-lookup"><span data-stu-id="9debf-116">**Efficiency**.</span></span> <span data-ttu-id="9debf-117">Il tempo necessario per la configurazione risulta ridotto, in quanto è sufficiente definire avvisi e operatori una sola volta.</span><span class="sxs-lookup"><span data-stu-id="9debf-117">Configuration time is reduced, because you need to define alerts and operators only once.</span></span>  
  
## <a name="disadvantages-of-using-an-alerts-management-server"></a><span data-ttu-id="9debf-118">Svantaggi derivanti dall'utilizzo di un server di gestione degli avvisi</span><span class="sxs-lookup"><span data-stu-id="9debf-118">Disadvantages of Using an Alerts Management Server</span></span>  
 <span data-ttu-id="9debf-119">Gli svantaggi derivanti dall'impostazione di un server di gestione degli avvisi sono:</span><span class="sxs-lookup"><span data-stu-id="9debf-119">The disadvantages of setting up an alerts management server include:</span></span>  
  
-   <span data-ttu-id="9debf-120">**Aumento del traffico**.</span><span class="sxs-lookup"><span data-stu-id="9debf-120">**Increased traffic**.</span></span> <span data-ttu-id="9debf-121">L'inoltro di eventi a un server di gestione degli avvisi può determinare un aumento del traffico di rete.</span><span class="sxs-lookup"><span data-stu-id="9debf-121">Forwarding events to an alerts management server can increase network traffic.</span></span> <span data-ttu-id="9debf-122">È possibile ridurre il traffico limitando l'inoltro ai soli eventi con livello di gravità superiore a un determinato valore.</span><span class="sxs-lookup"><span data-stu-id="9debf-122">This increase can be moderated by restricting event forwarding to events that are above a designated severity level.</span></span>  
  
-   <span data-ttu-id="9debf-123">**Singolo punto di errore**.</span><span class="sxs-lookup"><span data-stu-id="9debf-123">**Single point of failure**.</span></span> <span data-ttu-id="9debf-124">Se il server di gestione degli avvisi viene portato offline, non verrà generato nessun avviso per qualsiasi evento del gruppo di server gestito.</span><span class="sxs-lookup"><span data-stu-id="9debf-124">If the alerts management server goes offline, no alerts are issued for any event on the managed group of servers.</span></span>  
  
-   <span data-ttu-id="9debf-125">**Carico del server**.</span><span class="sxs-lookup"><span data-stu-id="9debf-125">**Server load**.</span></span> <span data-ttu-id="9debf-126">La gestione degli avvisi per gli eventi inoltrati determina un aumento del carico di elaborazione nel server di gestione degli avvisi.</span><span class="sxs-lookup"><span data-stu-id="9debf-126">Handling alerts for the forwarded events causes an increased processing load on the alerts management server.</span></span>  
  
## <a name="guidelines-for-using-an-alerts-management-server"></a><span data-ttu-id="9debf-127">Linee guida per l'utilizzo di un server di gestione degli avvisi</span><span class="sxs-lookup"><span data-stu-id="9debf-127">Guidelines for Using an Alerts Management Server</span></span>  
 <span data-ttu-id="9debf-128">Per la configurazione di un server di gestione degli avvisi attenersi alle linee guida riportate di seguito.</span><span class="sxs-lookup"><span data-stu-id="9debf-128">When configuring an alerts management server, follow these guidelines:</span></span>  
  
-   <span data-ttu-id="9debf-129">Per ricevere eventi inoltrati, il server di gestione degli avvisi deve essere un'istanza predefinita di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="9debf-129">In order to receive forwarded events, the alerts management server must be a default instance of SQL Server.</span></span>  
  
-   <span data-ttu-id="9debf-130">Nel server di gestione degli avvisi evitare di eseguire applicazioni di primaria importanza o utilizzate molto frequentemente.</span><span class="sxs-lookup"><span data-stu-id="9debf-130">Avoid running critical or heavily used applications on the alerts management server.</span></span>  
  
-   <span data-ttu-id="9debf-131">Pianificare con attenzione il traffico di rete associato alla configurazione di molti server per la condivisione dello stesso server di gestione degli avvisi.</span><span class="sxs-lookup"><span data-stu-id="9debf-131">Carefully plan for the network traffic involved in configuring many servers to share the same alerts management server.</span></span> <span data-ttu-id="9debf-132">In caso di congestione, ridurre il numero di server che utilizzano lo stesso server di gestione degli avvisi.</span><span class="sxs-lookup"><span data-stu-id="9debf-132">If congestion results, reduce the number of servers that use a particular alerts management server.</span></span>  
  
     <span data-ttu-id="9debf-133">I server registrati in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] sono quelli selezionabili come server di inoltro degli avvisi.</span><span class="sxs-lookup"><span data-stu-id="9debf-133">The servers that are registered within [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] constitute the list of servers available to be chosen by that server as the alerts-forwarding server.</span></span>  
  
-   <span data-ttu-id="9debf-134">Definire nell'istanza locale di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] avvisi che richiedono una risposta specifica del server, anziché inoltrare gli avvisi al server di gestione degli avvisi.</span><span class="sxs-lookup"><span data-stu-id="9debf-134">Define alerts on the local instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that require a server-specific response, instead of forwarding the alerts to the alerts management server.</span></span>  
  
     <span data-ttu-id="9debf-135">Il server di gestione degli avvisi visualizza tutti i server che inoltrano avvisi come un insieme logico.</span><span class="sxs-lookup"><span data-stu-id="9debf-135">The alerts management server views all the servers forwarding to it as a logical whole.</span></span> <span data-ttu-id="9debf-136">Un server di gestione degli avvisi risponde ad esempio in modo identico a un evento 605 inoltrato dal server A e a un evento 605 inoltrato dal server B.</span><span class="sxs-lookup"><span data-stu-id="9debf-136">For example, an alerts management server responds in the same way to a 605 event from server A and a 605 event from server B.</span></span>  
  
-   <span data-ttu-id="9debf-137">Dopo aver configurato il sistema degli avvisi, controllare periodicamente se nel registro applicazioni di Microsoft Windows sono presenti eventi di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="9debf-137">After configuring your alert system, periodically check the Microsoft Windows application log for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent events.</span></span>  
  
     <span data-ttu-id="9debf-138">Le condizioni di errore rilevate dal motore degli avvisi vengono registrate nel registro applicazioni locale di Windows con il nome di origine "SQL Server Agent".</span><span class="sxs-lookup"><span data-stu-id="9debf-138">Failure conditions encountered by the alerts engine are written to the local Windows application log with a source name of "SQL Server Agent."</span></span> <span data-ttu-id="9debf-139">Se ad esempio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent non è in grado di inviare notifiche tramite posta elettronica in base alle impostazioni definite, nel registro applicazioni verrà registrato un evento.</span><span class="sxs-lookup"><span data-stu-id="9debf-139">For example, if [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent cannot send an e-mail notification as it has been defined, an event is logged in the application log.</span></span>  
  
 <span data-ttu-id="9debf-140">Se un avviso definito localmente è disattivato e viene generato un evento che avrebbe causato l'attivazione di tale avviso, l'evento verrà inoltrato al server di gestione degli avvisi purché soddisfi la condizione di inoltro degli avvisi.</span><span class="sxs-lookup"><span data-stu-id="9debf-140">If a locally defined alert is inactivated, and an event occurs that would have caused the alert to fire, the event is forwarded to the alerts management server (if it satisfies the alert-forwarding condition).</span></span> <span data-ttu-id="9debf-141">In tal modo, a seconda dei casi, gli utenti del sito locale potranno attivare o disattivare gli avvisi definiti sia localmente che nel server di gestione degli avvisi.</span><span class="sxs-lookup"><span data-stu-id="9debf-141">This forwarding allows local overrides (alerts defined locally that are also defined on the alerts management server) to be turned off and on as needed by the user at the local site.</span></span> <span data-ttu-id="9debf-142">È inoltre possibile richiedere che gli eventi siano sempre inoltrati, anche quando sono gestiti da avvisi locali.</span><span class="sxs-lookup"><span data-stu-id="9debf-142">You can also request that events always be forwarded, even if they are also handled by local alerts.</span></span>  
  
 <span data-ttu-id="9debf-143">Di seguito sono riportate le attività comuni per la gestione degli eventi in un ambiente multiserver:</span><span class="sxs-lookup"><span data-stu-id="9debf-143">The following are common tasks for managing events in a multiserver environment:</span></span>  
  
 <span data-ttu-id="9debf-144">**Per impostare un server di gestione degli avvisi**</span><span class="sxs-lookup"><span data-stu-id="9debf-144">**To designate an alerts management server**</span></span>  
  
-   [<span data-ttu-id="9debf-145">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9debf-145">SQL Server Management Studio</span></span>](../sql-server-management-studio-ssms.md)  
  
 <span data-ttu-id="9debf-146">**Per definire la risposta a un avviso**</span><span class="sxs-lookup"><span data-stu-id="9debf-146">**To define the response to an alert**</span></span>  
  
-   [<span data-ttu-id="9debf-147">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9debf-147">SQL Server Management Studio</span></span>](define-the-response-to-an-alert-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="9debf-148">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9debf-148">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-notification-transact-sql)  
  
## <a name="running-event-triggered-jobs"></a><span data-ttu-id="9debf-149">Esecuzione di processi attivati da eventi</span><span class="sxs-lookup"><span data-stu-id="9debf-149">Running Event-Triggered Jobs</span></span>  
 <span data-ttu-id="9debf-150">È possibile definire l'esecuzione di un processo in risposta a un avviso,</span><span class="sxs-lookup"><span data-stu-id="9debf-150">You can define a job to be executed in response to an alert.</span></span> <span data-ttu-id="9debf-151">ad esempio eseguendo un processo che corregga il problema segnalato dall'avviso o ne esegua un'analisi aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="9debf-151">For example, you can execute a job that corrects or further diagnoses a problem detected by the alert.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9debf-152">Poiché un processo può generare un evento, assicurarsi che non venga creato un ciclo ricorsivo avviso-processo.</span><span class="sxs-lookup"><span data-stu-id="9debf-152">Because a job can raise an event, be careful not to create a recursive alert-job loop.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9debf-153">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9debf-153">See Also</span></span>  
 [<span data-ttu-id="9debf-154">Messaggi disys.sys&#40;&#41;Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9debf-154">sys.sysmessages &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-compatibility-views/sys-sysmessages-transact-sql)  
  
  
