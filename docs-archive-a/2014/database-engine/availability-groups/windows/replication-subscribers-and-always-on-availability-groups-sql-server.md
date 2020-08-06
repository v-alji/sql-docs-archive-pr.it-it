---
title: Sottoscrittori e Gruppi di disponibilità AlwaysOn di replica (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 01/16/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- failover subscribers with AlwaysOn
- Availability Groups [SQL Server], interoperability
- replication [SQL Server], AlwaysOn Availability Groups
ms.assetid: 0995f269-0580-43ed-b8bf-02b9ad2d7ee6
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 449b5ac416f2ae86395c40a984678ed4258b3b85
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629612"
---
# <a name="replication-subscribers-and-alwayson-availability-groups-sql-server"></a><span data-ttu-id="8d480-102">Sottoscrittori della replica e gruppi di disponibilità AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="8d480-102">Replication Subscribers and AlwaysOn Availability Groups (SQL Server)</span></span>
  <span data-ttu-id="8d480-103">Quando viene eseguito il failover di un gruppo di disponibilità AlwaysOn contenente un database che opera come sottoscrittore di replica, la sottoscrizione di replica potrebbe non venire completata.</span><span class="sxs-lookup"><span data-stu-id="8d480-103">When an AlwaysOn availability group containing a database that is a replication subscriber fails over, the replication subscription might fail.</span></span> <span data-ttu-id="8d480-104">Per i sottoscrittori push della replica transazionale, l'agente di distribuzione continuerà a replicare automaticamente dopo un failover se la sottoscrizione è stata creata usando il nome del listener del gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="8d480-104">For transactional replication push subscribers, the distribution agent will continue to replicate automatically after a failover if the subscription was created using the AG listener name.</span></span> <span data-ttu-id="8d480-105">Per i sottoscrittori pull della replica transazionale, l'agente di distribuzione continuerà a replicare automaticamente dopo un failover se la sottoscrizione è stata creata usando il nome del listener del gruppo di disponibilità e il server sottoscrizione originale è attivo e in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="8d480-105">For transactional replication pull subscribers, the distribution agent will continue to replicate automatically after a failover, if the subscription was created using the AG listener name and the original subscriber server is up and running.</span></span> <span data-ttu-id="8d480-106">Questo avviene perché i processi dell'agente di distribuzione vengono creati solo nel sottoscrittore originale (replica primaria del gruppo di disponibilità).</span><span class="sxs-lookup"><span data-stu-id="8d480-106">This is because the distribution agent jobs only get created on the original subscriber (primary replica of the AG).</span></span> <span data-ttu-id="8d480-107">Per i sottoscrittori di merge, un amministratore di replica deve riconfigurare manualmente il sottoscrittore ricreando la sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="8d480-107">For merge subscribers, a replication administrator must manually reconfigure the subscriber, by recreating the subscription.</span></span>  
  
## <a name="what-is-supported"></a><span data-ttu-id="8d480-108">Operazioni supportate</span><span class="sxs-lookup"><span data-stu-id="8d480-108">What is Supported</span></span>  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="8d480-109">supporta il failover automatico del server di pubblicazione, il failover automatico dei sottoscrittori transazionali e il failover manuale dei sottoscrittore di merge.</span><span class="sxs-lookup"><span data-stu-id="8d480-109">replication supports the automatic failover of the publisher, the automatic failover of transactional subscribers, and the manual failover of merge subscribers.</span></span> <span data-ttu-id="8d480-110">Il failover di un server di distribuzione in un database di disponibilità non è supportato.</span><span class="sxs-lookup"><span data-stu-id="8d480-110">The failover of a distributor on an availability database is not supported.</span></span> <span data-ttu-id="8d480-111">AlwaysOn non possono essere combinati con sincronizzazione Web e [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Compact scenari.</span><span class="sxs-lookup"><span data-stu-id="8d480-111">AlwaysOn cannot be combined with Websync and [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Compact scenarios.</span></span>  
  
 <span data-ttu-id="8d480-112">**Failover di una sottoscrizione pull di merge**</span><span class="sxs-lookup"><span data-stu-id="8d480-112">**Failover of a Merge Pull Subscription**</span></span>  
  
 <span data-ttu-id="8d480-113">Durante il failover del gruppo di disponibilità si verifica un errore nella sottoscrizione pull poiché l'agente pull non riesce a trovare i processi archiviati nel database **msdb** dell'istanza del server in cui è ospitata la replica primaria, che non è disponibile a causa dell'errore che si è verificato nell'istanza del server.</span><span class="sxs-lookup"><span data-stu-id="8d480-113">A pull subscription fails upon availability group failover, because pull agent cannot find the jobs stored in the **msdb** database of the server instance that hosts the primary replica; which is not available because the server instance has failed.</span></span>  
  
 <span data-ttu-id="8d480-114">**Failover di una sottoscrizione push di merge**</span><span class="sxs-lookup"><span data-stu-id="8d480-114">**Failover of a Merge Push Subscription**</span></span>  
  
 <span data-ttu-id="8d480-115">Durante il failover del gruppo di disponibilità si verifica un errore nella sottoscrizione push poiché l'agente push non può più connettersi al database di sottoscrizione originale nel sottoscrittore originale.</span><span class="sxs-lookup"><span data-stu-id="8d480-115">A push subscription fails upon availability group failover, because the push agent can no longer connect to original subscription database on original subscriber.</span></span>  
  
## <a name="how-to-create-transactional-subscription-in-an-alwayson-environment"></a><span data-ttu-id="8d480-116">Come creare una sottoscrizione transazionale in un ambiente AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="8d480-116">How to Create Transactional Subscription in an AlwaysOn Environment</span></span>  
 <span data-ttu-id="8d480-117">Per la replica transazionale, usare i passaggi seguenti per configurare un gruppo di disponibilità del sottoscrittore e impostarne il failover:</span><span class="sxs-lookup"><span data-stu-id="8d480-117">For transactional replication, use the following steps to configure and failover a subscriber availability group:</span></span>  
  
1.  <span data-ttu-id="8d480-118">Prima di creare la sottoscrizione, aggiungere il database sottoscrittore al gruppo di disponibilità AlwaysOn appropriato.</span><span class="sxs-lookup"><span data-stu-id="8d480-118">Before creating the subscription, add the subscriber database to the appropriate AlwaysOn availability group.</span></span>  
  
2.  <span data-ttu-id="8d480-119">Aggiungere il listener del gruppo di disponibilità del sottoscrittore come server collegato a tutti i nodi del gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="8d480-119">Add the subscriber's availability group Listener as a linked server to all nodes of the availability group.</span></span> <span data-ttu-id="8d480-120">Questa operazione assicura che tutti i partner di failover potenziali siano in grado di riconoscere e connettersi al listener.</span><span class="sxs-lookup"><span data-stu-id="8d480-120">This step ensures that all potential failover partners are aware of and can connect to the listener.</span></span>  
  
3.  <span data-ttu-id="8d480-121">Usare lo script riportato nella sezione **Creazione di una sottoscrizione push di una replica transazionale** sottostante per creare la sottoscrizione con il nome del listener del gruppo di disponibilità del sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="8d480-121">Using the script in the **Creating a Transactional Replication Push Subscription** section below, create the subscription using the name of the availability group listener of the subscriber.</span></span> <span data-ttu-id="8d480-122">Dopo un failover, il nome del listener rimane sempre valido, mentre il nome del server effettivo del sottoscrittore dipenderà dal nodo effettivo diventato il nuovo nodo primario.</span><span class="sxs-lookup"><span data-stu-id="8d480-122">After a failover, the listener name will always remain valid, whereas the actual server name of the subscriber will depend on the actual node that became the new primary.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8d480-123">La sottoscrizione deve essere creata usando uno script [!INCLUDE[tsql](../../../includes/tsql-md.md)] e non può essere creata con [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8d480-123">The subscription must be created by using a [!INCLUDE[tsql](../../../includes/tsql-md.md)] script and cannot be created using [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)].</span></span>  
  
4.  <span data-ttu-id="8d480-124">Se si crea una sottoscrizione pull:</span><span class="sxs-lookup"><span data-stu-id="8d480-124">If creating a pull subscription:</span></span>  
  
    1.  <span data-ttu-id="8d480-125">Nel nodo primario del sottoscrittore in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)]aprire l'albero [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="8d480-125">In [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)], on the primary subscriber node, open the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent tree.</span></span>  
  
    2.  <span data-ttu-id="8d480-126">Identificare il processo dell' **agente di distribuzione pull** e modificare il processo.</span><span class="sxs-lookup"><span data-stu-id="8d480-126">Identify the **Pull Distribution Agent** job and edit the job.</span></span>  
  
    3.  <span data-ttu-id="8d480-127">Nel passaggio del processo **Esecuzione dell'agente** verificare i parametri `-Publisher` e `-Distributor` .</span><span class="sxs-lookup"><span data-stu-id="8d480-127">On the **Run Agent** job step, check the `-Publisher` and `-Distributor` parameters.</span></span> <span data-ttu-id="8d480-128">Verificare che questi parametri contengano i nomi corretti del server diretto e dell'istanza del server di distribuzione e del database di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="8d480-128">Make sure that these parameters contain the correct direct server and instance names of the publisher and distributor server.</span></span>  
  
    4.  <span data-ttu-id="8d480-129">Modificare il parametro `-Subscriber` impostando il nome del listener del gruppo di disponibilità del sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="8d480-129">Change the `-Subscriber` parameter to the subscriber's availability group listener name.</span></span>  
  
 <span data-ttu-id="8d480-130">Quando si crea la sottoscrizione usando questa procedura, non si dovranno eseguire azioni dopo un failover.</span><span class="sxs-lookup"><span data-stu-id="8d480-130">When you create your subscription following these steps, then you won't have to do anything after a failover.</span></span>  
  
## <a name="creating-a-transactional-replication-push-subscription"></a><span data-ttu-id="8d480-131">Creazione di una sottoscrizione push di una replica transazionale</span><span class="sxs-lookup"><span data-stu-id="8d480-131">Creating a Transactional Replication Push Subscription</span></span>  
  
```  
-- commands to execute at the publisher, in the publisher database:  
use [<publisher database name>]  
EXEC sp_addsubscription @publication = N'<publication name>',   
       @subscriber = N'<availability group listener name>',   
       @destination_db = N'<subscriber database name>',   
       @subscription_type = N'Push',   
       @sync_type = N'automatic', @article = N'all', @update_mode = N'read only', @subscriber_type = 0;  
GO  
  
EXEC sp_addpushsubscription_agent @publication = N'<publication name>',   
       @subscriber = N'<availability group listener name>',   
       @subscriber_db = N'<subscriber database name>',   
       @job_login = null, @job_password = null, @subscriber_security_mode = 1;  
GO  
```  
  
## <a name="to-resume-the-merge-agents-after-the-availability-group-of-the-subscriber-fails-over"></a><span data-ttu-id="8d480-132">Per riprendere gli agenti di merge dopo il failover del gruppo di disponibilità del sottoscrittore</span><span class="sxs-lookup"><span data-stu-id="8d480-132">To Resume the Merge Agents After the Availability Group of the Subscriber Fails Over</span></span>  
 <span data-ttu-id="8d480-133">Per eseguire il merge della replica, un relativo amministratore deve riconfigurare manualmente il sottoscrittore attenendosi alla procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="8d480-133">For merge replication, a replication administrator must manually reconfigure the subscriber with the following steps:</span></span>  
  
1.  <span data-ttu-id="8d480-134">Per rimuovere la sottoscrizione precedente del sottoscrittore eseguire `sp_subscription_cleanup`.</span><span class="sxs-lookup"><span data-stu-id="8d480-134">Execute `sp_subscription_cleanup` to remove the old subscription for the subscriber.</span></span> <span data-ttu-id="8d480-135">Effettuare questa operazione nella nuova replica primaria, che precedentemente era la secondaria.</span><span class="sxs-lookup"><span data-stu-id="8d480-135">Perform this action on the new primary replica (which was formerly the secondary replica).</span></span>  
  
2.  <span data-ttu-id="8d480-136">Ricreare la sottoscrizione creando una nuova sottoscrizione a partire da un nuovo snapshot.</span><span class="sxs-lookup"><span data-stu-id="8d480-136">Recreate the subscription by creating a new subscription, beginning with a new snapshot.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8d480-137">Il processo corrente non è pratico per i sottoscrittori della replica di tipo merge. Tuttavia, lo scenario principale per la replica di tipo merge è composto da utenti disconnessi (desktop, portatili, dispositivi palmari) che non utilizzeranno i gruppi di disponibilità AlwaysOn sul sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="8d480-137">The current process is inconvenient for merge replication subscribers, however the main scenario for merge replication is disconnected users (desktops, laptops, handset devices) which will not use AlwaysOn availability groups on the subscriber.</span></span>  
  
  
