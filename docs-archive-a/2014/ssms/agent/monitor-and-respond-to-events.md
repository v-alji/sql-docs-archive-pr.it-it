---
title: Monitorare e rispondere agli eventi | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- notifications [SQL Server], alert
- events [SQL Server], alerts
- alerts [SQL Server]
- notifications [SQL Server]
- events [SQL Server], automatically responding to
- administrator notifications [SQL Server Agent]
- automatic event responses
- SQL Server Agent alerts
- monitoring [SQL Server], events
- responding to events automatically
ms.assetid: f7fbe155-5b68-4777-bc71-a47637471f32
author: stevestein
ms.author: sstein
ms.openlocfilehash: afdf1beffd6099fce84f03a8ba65f7de9abb8f0b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715008"
---
# <a name="monitor-and-respond-to-events"></a><span data-ttu-id="fdc25-102">Monitoraggio e risposta agli eventi</span><span class="sxs-lookup"><span data-stu-id="fdc25-102">Monitor and Respond to Events</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="fdc25-103">Agent può monitorare e rispondere automaticamente agli *eventi*, ad esempio messaggi di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], a condizioni specifiche delle prestazioni e agli eventi del servizio Strumentazione gestione Windows (WMI).</span><span class="sxs-lookup"><span data-stu-id="fdc25-103">Agent can monitor and automatically respond to *events*, such as messages from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], specific performance conditions, and Windows Management Instrumentation (WMI) events.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fdc25-104">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="fdc25-104">In This Section</span></span>  
 [<span data-ttu-id="fdc25-105">Avvisi</span><span class="sxs-lookup"><span data-stu-id="fdc25-105">Alerts</span></span>](alerts.md)  
 <span data-ttu-id="fdc25-106">Sono incluse informazioni sulla denominazione di un avviso e sulla selezione di eventi o condizioni delle prestazioni a cui rispondono gli avvisi.</span><span class="sxs-lookup"><span data-stu-id="fdc25-106">Contains information about naming an alert and selecting the events or performance conditions to which alerts respond.</span></span>  
  
 [<span data-ttu-id="fdc25-107">Creazione di un evento definito dall'utente</span><span class="sxs-lookup"><span data-stu-id="fdc25-107">Create a User-Defined Event</span></span>](create-a-user-defined-event.md)  
 <span data-ttu-id="fdc25-108">Sono incluse informazioni sulla creazione di eventi diversi da quelli predefiniti di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fdc25-108">Contains information about how to create events other than those that are predefined by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="fdc25-109">Operatori</span><span class="sxs-lookup"><span data-stu-id="fdc25-109">Operators</span></span>](operators.md)  
 <span data-ttu-id="fdc25-110">Sono incluse informazioni sulla creazione di alias per gli amministratori che possono essere utilizzati da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent per inviare notifiche in caso di esito positivo o negativo dei processi.</span><span class="sxs-lookup"><span data-stu-id="fdc25-110">Contains information about creating aliases for administrators that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent can use to send notifications when jobs fail or succeed.</span></span>  
  
## <a name="about-monitoring-and-responding-to-events"></a><span data-ttu-id="fdc25-111">Informazioni sul monitoraggio e sulla risposta agli eventi</span><span class="sxs-lookup"><span data-stu-id="fdc25-111">About Monitoring and Responding to Events</span></span>  
 <span data-ttu-id="fdc25-112">Le risposte automatiche agli eventi sono denominate *Avvisi*.</span><span class="sxs-lookup"><span data-stu-id="fdc25-112">Automated responses to events are called *alerts*.</span></span> <span data-ttu-id="fdc25-113">È possibile definire un avviso relativo a uno o più eventi per specificare la risposta di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent quando vengono generati tali eventi.</span><span class="sxs-lookup"><span data-stu-id="fdc25-113">You can define an alert on one or more events to specify how you want [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to respond to their occurrence.</span></span> <span data-ttu-id="fdc25-114">Un avviso può rispondere a un evento informando un amministratore o eseguendo un processo oppure in entrambi i modi.</span><span class="sxs-lookup"><span data-stu-id="fdc25-114">An alert can respond to an event by notifying an administrator or running a job, or both.</span></span> <span data-ttu-id="fdc25-115">Un avviso può inoltre inviare un evento al registro applicazioni di Microsoft Windows in un computer diverso.</span><span class="sxs-lookup"><span data-stu-id="fdc25-115">An alert can also forward an event to the Microsoft Windows application log on a different computer.</span></span> <span data-ttu-id="fdc25-116">È possibile specificare che un operatore deve ricevere immediatamente una notifica se viene generato un evento con livello di gravità 19.</span><span class="sxs-lookup"><span data-stu-id="fdc25-116">For example, you can specify that an operator be notified immediately if an event of severity 19 occurs.</span></span> <span data-ttu-id="fdc25-117">La definizione di avvisi consente agli amministratori di database di monitorare e gestire [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]con maggiore efficienza.</span><span class="sxs-lookup"><span data-stu-id="fdc25-117">By defining alerts, database administrators can more effectively monitor and manage [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="fdc25-118">Agent risponde solo agli eventi per cui è stato definito un avviso.</span><span class="sxs-lookup"><span data-stu-id="fdc25-118">Agent only responds to events for which an alert is defined.</span></span> <span data-ttu-id="fdc25-119">Il metodo utilizzato in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent per il monitoraggio degli eventi varia in base al tipo di evento.</span><span class="sxs-lookup"><span data-stu-id="fdc25-119">The method that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent uses to monitor events depends on the type of event.</span></span>  
  
 <span data-ttu-id="fdc25-120">Se è stato definito un avviso di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent per un contatore delle prestazioni, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent esegue direttamente il monitoraggio di tale contatore.</span><span class="sxs-lookup"><span data-stu-id="fdc25-120">When a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alert is defined for a performance counter, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent directly monitors the performance counter.</span></span> <span data-ttu-id="fdc25-121">Per un evento WMI, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent registra la query di eventi.</span><span class="sxs-lookup"><span data-stu-id="fdc25-121">For a WMI event, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent registers an event query for the WMI event.</span></span>  
  
 <span data-ttu-id="fdc25-122">Per rispondere ai messaggi di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent esegue il monitoraggio del registro applicazioni di Windows.</span><span class="sxs-lookup"><span data-stu-id="fdc25-122">To respond to messages from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent monitors the Windows application log.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="fdc25-123">Agent può rispondere solo ai messaggi contenuti in tale registro.</span><span class="sxs-lookup"><span data-stu-id="fdc25-123">Agent can only respond to messages that appear in this log.</span></span> <span data-ttu-id="fdc25-124">Per impostazione predefinita, SQL Server inserisce nel registro applicazioni di Windows i messaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="fdc25-124">By default, SQL Server logs the following messages in the Windows application log:</span></span>  
  
-   <span data-ttu-id="fdc25-125">Errori sysmessages con livello di gravità 19 o superiore.</span><span class="sxs-lookup"><span data-stu-id="fdc25-125">Severity 19 or higher sysmessages errors.</span></span>  
  
     <span data-ttu-id="fdc25-126">Se si desidera registrare anche gli errori sysmessages con livello di gravità inferiore a 19, utilizzare la stored procedure sp_altermessage per designarli come errori da registrare sempre.</span><span class="sxs-lookup"><span data-stu-id="fdc25-126">If you also want to log specific sysmessages errors that have a severity lower than 19, use the sp_altermessage stored procedure to designate such errors as "always logged".</span></span>  
  
-   <span data-ttu-id="fdc25-127">Qualsiasi istruzione RAISERROR richiamata tramite la sintassi WITH LOG.</span><span class="sxs-lookup"><span data-stu-id="fdc25-127">Any RAISERROR statement invoked by using the WITH LOG syntax.</span></span>  
  
     <span data-ttu-id="fdc25-128">RAISERROR WITH LOG è il metodo consigliato per la scrittura nel registro applicazioni di Windows da un'istanza di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="fdc25-128">Using RAISERROR WITH LOG is the recommended way to write to the Windows application log from an instance of SQL Server.</span></span>  
  
-   <span data-ttu-id="fdc25-129">Qualsiasi evento dell'applicazione registrato tramite xp_logevent.</span><span class="sxs-lookup"><span data-stu-id="fdc25-129">Any application event that is logged by using xp_logevent.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="fdc25-130">La registrazione di eventi delle applicazioni occupa spazio nel registro applicazioni di Windows causando il superamento delle dimensioni massime.</span><span class="sxs-lookup"><span data-stu-id="fdc25-130">Logging application events consumes log space and can cause the Windows application log to exceed its maximum size.</span></span> <span data-ttu-id="fdc25-131">Per evitare la perdita di informazioni sugli eventi di SQL Server, verificare che le dimensioni massime del registro applicazioni di Windows siano sufficienti.</span><span class="sxs-lookup"><span data-stu-id="fdc25-131">Make sure that the maximum Windows application log size is large enough to avoid loss of SQL Server event information.</span></span>  
  
 <span data-ttu-id="fdc25-132">Quando [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] registra un messaggio, il servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent lo confronta con gli avvisi definiti dall'amministratore di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fdc25-132">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] logs a message, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service compares the message against the alerts defined by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] administrator.</span></span>  
  
 <span data-ttu-id="fdc25-133">Indipendentemente dall'origine dell'evento, il servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent risponde all'evento eseguendo le attività specificate nell'avviso corrispondente.</span><span class="sxs-lookup"><span data-stu-id="fdc25-133">Regardless of the source of the event, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service responds to the event by performing the tasks specified in the alert for the event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdc25-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fdc25-134">See Also</span></span>  
 [<span data-ttu-id="fdc25-135">sp_altermessage &#40;&#41;Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="fdc25-135">sp_altermessage &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-altermessage-transact-sql)  
  
  
