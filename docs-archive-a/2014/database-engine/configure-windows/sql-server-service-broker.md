---
title: SQL Server Service Broker | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- SQL12.SWB.SSBQUEUEPROPERTIES.GENERAL.F1
- SQL12.SWB.SSBREMSVCBINDPROPERTIES.GENERAL.F1
- SQL12.SWB.SSBMSGTYPEPROPERTIES.GENERAL.F1
- SQL12.SWB.SSBROUTEPROPERTIES.GENERAL.F1
- SQL12.SWB.SSBCONTRACTPROPERTIES.GENERAL.F1
- SQL12.SWB.SSBSERVICEPROPERTIES.GENERAL.F1
- SQL12.SWB.SSBPRIORITYPROPERTIES.GENERAL.F1
helpviewer_keywords:
- Broker See Service Broker
- SQL Server Service Broker
- Service Broker
ms.assetid: 8b8b3b57-fd46-44de-9a4e-e3a8e3999c1e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 3d3877dd8311e0fe5b65bd4b1e7f9c40fbd84751
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724152"
---
# <a name="sql-server-service-broker"></a><span data-ttu-id="65e55-102">SQL Server Service Broker</span><span class="sxs-lookup"><span data-stu-id="65e55-102">SQL Server Service Broker</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="65e55-103">[!INCLUDE[ssSB](../../includes/sssb-md.md)]fornisce supporto nativo per le applicazioni di messaggistica e Accodamento in [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="65e55-103">[!INCLUDE[ssSB](../../includes/sssb-md.md)] provides native support for messaging and queuing applications in the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span> <span data-ttu-id="65e55-104">Questa caratteristica semplifica il lavoro degli sviluppatori per creare applicazioni complesse che utilizzano i componenti di [!INCLUDE[ssDE](../../includes/ssde-md.md)] per comunicare tra database diversi.</span><span class="sxs-lookup"><span data-stu-id="65e55-104">This makes it easier for developers to create sophisticated applications that use the [!INCLUDE[ssDE](../../includes/ssde-md.md)] components to communicate between disparate databases.</span></span> <span data-ttu-id="65e55-105">Gli sviluppatori possono utilizzare [!INCLUDE[ssSB](../../includes/sssb-md.md)] per compilare con facilità applicazioni distribuite e affidabili.</span><span class="sxs-lookup"><span data-stu-id="65e55-105">Developers can use [!INCLUDE[ssSB](../../includes/sssb-md.md)] to easily build distributed and reliable applications.</span></span>  
  
 <span data-ttu-id="65e55-106">Gli sviluppatori di applicazioni che utilizzano [!INCLUDE[ssSB](../../includes/sssb-md.md)] possono distribuire il carico di lavoro su più database senza programmare interni di comunicazione e messaggistica complessi.</span><span class="sxs-lookup"><span data-stu-id="65e55-106">Application developers who use [!INCLUDE[ssSB](../../includes/sssb-md.md)] can distribute data workloads across several databases without programming complex communication and messaging internals.</span></span> <span data-ttu-id="65e55-107">In questo modo, è possibile ottenere una riduzione delle attività di sviluppo e test, in quanto [!INCLUDE[ssSB](../../includes/sssb-md.md)] gestisce i percorsi di comunicazione nel contesto di una conversazione,</span><span class="sxs-lookup"><span data-stu-id="65e55-107">This reduces development and test work because [!INCLUDE[ssSB](../../includes/sssb-md.md)] handles the communication paths in the context of a conversation.</span></span> <span data-ttu-id="65e55-108">con conseguente miglioramento delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="65e55-108">It also improves performance.</span></span> <span data-ttu-id="65e55-109">Ad esempio, i database front-end che supportano i siti Web possono registrare le informazioni e mettere in coda le attività con molti processi nei database back-end.</span><span class="sxs-lookup"><span data-stu-id="65e55-109">For example, front-end databases supporting Web sites can record information and send process intensive tasks to queue in back-end databases.</span></span> [!INCLUDE[ssSB](../../includes/sssb-md.md)] <span data-ttu-id="65e55-110">si assicura che tutte le attività vengano gestite nel contesto delle transazioni per garantire affidabilità e coerenza tecnica.</span><span class="sxs-lookup"><span data-stu-id="65e55-110">ensures that all tasks are managed in the context of transactions to assure reliability and technical consistency.</span></span>  
  
## <a name="where-is-the-documentation-for-service-broker"></a><span data-ttu-id="65e55-111">Dove si trova la documentazione per Service Broker?</span><span class="sxs-lookup"><span data-stu-id="65e55-111">Where is the documentation for Service Broker?</span></span>  
 <span data-ttu-id="65e55-112">La documentazione di riferimento per [!INCLUDE[ssSB](../../includes/sssb-md.md)] è inclusa nella documentazione di [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="65e55-112">The reference documentation for [!INCLUDE[ssSB](../../includes/sssb-md.md)] is included in the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] documentation.</span></span> <span data-ttu-id="65e55-113">Nella documentazione di riferimento sono incluse le sezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="65e55-113">This reference documentation includes the following sections:</span></span>  
  
-   <span data-ttu-id="65e55-114">[Istruzioni Data Definition Language &#40;DDL&#41; &#40;Transact-SQL&#41;](/sql/odbc/reference/develop-app/ddl-statements) per istruzioni CREATE, ALTER e DROP</span><span class="sxs-lookup"><span data-stu-id="65e55-114">[Data Definition Language &#40;DDL&#41; Statements &#40;Transact-SQL&#41;](/sql/odbc/reference/develop-app/ddl-statements) for CREATE, ALTER, and DROP statements</span></span>  
  
-   [<span data-ttu-id="65e55-115">Viste del catalogo di Service Broker &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="65e55-115">Service Broker Catalog Views &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/service-broker-catalog-views-transact-sql)  
  
-   [<span data-ttu-id="65e55-116">Viste a gestione dinamica relative a Service Broker &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="65e55-116">Service Broker Related Dynamic Management Views &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/service-broker-related-dynamic-management-views-transact-sql)  
  
-   [<span data-ttu-id="65e55-117">Utilità ssbdiagnose &#40;Service Broker&#41;</span><span class="sxs-lookup"><span data-stu-id="65e55-117">ssbdiagnose Utility &#40;Service Broker&#41;</span></span>](../../tools/ssbdiagnose/ssbdiagnose-utility-service-broker.md)  
  
 <span data-ttu-id="65e55-118">Vedere la [documentazione pubblicata in precedenza](https://go.microsoft.com/fwlink/?LinkId=231312) per i concetti relativi a [!INCLUDE[ssSB](../../includes/sssb-md.md)] e per le attività di gestione e sviluppo.</span><span class="sxs-lookup"><span data-stu-id="65e55-118">See the [previously published documentation](https://go.microsoft.com/fwlink/?LinkId=231312) for [!INCLUDE[ssSB](../../includes/sssb-md.md)] concepts and for development and management tasks.</span></span> <span data-ttu-id="65e55-119">Questa documentazione non è riprodotta nella documentazione di [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] a causa del numero esiguo di modifiche in [!INCLUDE[ssSB](../../includes/sssb-md.md)] in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="65e55-119">This documentation is not reproduced in the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] documentation due to the small number of changes in [!INCLUDE[ssSB](../../includes/sssb-md.md)] in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
## <a name="whats-new-in-service-broker"></a><span data-ttu-id="65e55-120">Novità di Service Broker</span><span class="sxs-lookup"><span data-stu-id="65e55-120">What's new in Service Broker</span></span>  
 <span data-ttu-id="65e55-121">Non è stata introdotta alcuna modifica significativa in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="65e55-121">No significant changes are introduced in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  <span data-ttu-id="65e55-122">In [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]sono state introdotte le modifiche riportate di seguito.</span><span class="sxs-lookup"><span data-stu-id="65e55-122">The following changes were introduced in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)].</span></span>  
  
### <a name="messages-can-be-sent-to-multiple-target-services-multicast"></a><span data-ttu-id="65e55-123">È possibile inviare messaggi a più servizi di destinazione (multicast)</span><span class="sxs-lookup"><span data-stu-id="65e55-123">Messages can be sent to multiple target services (multicast)</span></span>  
 <span data-ttu-id="65e55-124">La sintassi dell'istruzione [SEND &#40;Transact-SQL&#41;](/sql/t-sql/statements/send-transact-sql) è stata estesa per abilitare il multicast supportando più handle di conversazione.</span><span class="sxs-lookup"><span data-stu-id="65e55-124">The syntax of the [SEND &#40;Transact-SQL&#41;](/sql/t-sql/statements/send-transact-sql) statement has been extended to enable multicast by supporting multiple conversation handles.</span></span>  
  
### <a name="queues-expose-the-message-enqueued-time"></a><span data-ttu-id="65e55-125">Le code espongono il tempo di accodamento del messaggio</span><span class="sxs-lookup"><span data-stu-id="65e55-125">Queues expose the message enqueued time</span></span>  
 <span data-ttu-id="65e55-126">Le code dispongono di una nuova colonna, **message_enqueue_time**in cui è indicato il tempo di accodamento di un messaggio.</span><span class="sxs-lookup"><span data-stu-id="65e55-126">Queues have a new column, **message_enqueue_time**, that shows how long a message has been in the queue.</span></span>  
  
### <a name="poison-message-handling-can-be-disabled"></a><span data-ttu-id="65e55-127">La gestione dei messaggi non elaborabili può essere disabilitata</span><span class="sxs-lookup"><span data-stu-id="65e55-127">Poison message handling can be disabled</span></span>  
 <span data-ttu-id="65e55-128">Tramite le istruzioni [CREATE QUEUE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-queue-transact-sql) e [ALTER QUEUE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-queue-transact-sql) è possibile abilitare o disabilitare la gestione dei messaggi non elaborabili aggiungendo la clausola, `POISON_MESSAGE_HANDLING (STATUS = ON | OFF)`.</span><span class="sxs-lookup"><span data-stu-id="65e55-128">The [CREATE QUEUE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-queue-transact-sql) and [ALTER QUEUE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-queue-transact-sql) statements now have the ability to enable or disable poison message handling by adding the clause, `POISON_MESSAGE_HANDLING (STATUS = ON | OFF)`.</span></span> <span data-ttu-id="65e55-129">La vista del catalogo **sys.service_queues** contiene ora la colonna **is_poison_message_handling_enabled** per indicare se il messaggio non elaborabile è abilitato o disabilitato.</span><span class="sxs-lookup"><span data-stu-id="65e55-129">The catalog view **sys.service_queues** now has the column **is_poison_message_handling_enabled** to indicate whether poison message is enabled or disabled.</span></span>  
  
### <a name="alwayson-support-in-service-broker"></a><span data-ttu-id="65e55-130">Supporto AlwaysOn in Service Broker</span><span class="sxs-lookup"><span data-stu-id="65e55-130">AlwaysOn support in Service Broker</span></span>  
 <span data-ttu-id="65e55-131">Per altre informazioni, vedere [Service Broker con i gruppi di disponibilità Always On &#40;SQL Server&#41;](../availability-groups/windows/service-broker-with-always-on-availability-groups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="65e55-131">For more information, see [Service Broker with AlwaysOn Availability Groups &#40;SQL Server&#41;](../availability-groups/windows/service-broker-with-always-on-availability-groups-sql-server.md).</span></span>  
  
  
