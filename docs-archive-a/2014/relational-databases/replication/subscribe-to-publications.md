---
title: Sottoscrivere le pubblicazioni | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.conc.subtopubs.f1
helpviewer_keywords:
- subscriptions [SQL Server replication], about subscriptions
- pull subscriptions [SQL Server replication]
- subscriptions [SQL Server replication]
- push subscriptions [SQL Server replication], about push subscriptions
- merge replication subscribing [SQL Server replication]
- merge replication subscribing [SQL Server replication], about subscribing
- publications [SQL Server replication], subscribing
- push subscriptions [SQL Server replication]
- pull subscriptions [SQL Server replication], about pull subscriptions
- snapshot replication [SQL Server], subscribing
- transactional replication, subscribing
ms.assetid: 088ee30a-05ab-47c4-92ed-316b93e12445
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c565aae26c6d549eb67043168797d5fb059c8e2a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624015"
---
# <a name="subscribe-to-publications"></a><span data-ttu-id="9c7e9-102">Subscribe to Publications</span><span class="sxs-lookup"><span data-stu-id="9c7e9-102">Subscribe to Publications</span></span>
  <span data-ttu-id="9c7e9-103">Una sottoscrizione è la richiesta di una copia di dati o di oggetti di database in una pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="9c7e9-103">A subscription is a request for a copy of the data and database objects in a publication.</span></span> <span data-ttu-id="9c7e9-104">Una sottoscrizione definisce quale pubblicazione verrà ricevuta, insieme alla posizione e al momento in cui verrà ricevuta.</span><span class="sxs-lookup"><span data-stu-id="9c7e9-104">A subscription defines which publication will be received, and where and when it will be received.</span></span> <span data-ttu-id="9c7e9-105">Quando si pianificano le sottoscrizioni, è necessario decidere dove si desidera eseguire l'elaborazione dell'agente.</span><span class="sxs-lookup"><span data-stu-id="9c7e9-105">When planning for subscriptions, consider where you want agent processing to occur.</span></span> <span data-ttu-id="9c7e9-106">La posizione di esecuzione dell'agente varia in base al tipo di sottoscrizione selezionato.</span><span class="sxs-lookup"><span data-stu-id="9c7e9-106">The type of subscription you choose controls where the agent runs.</span></span> <span data-ttu-id="9c7e9-107">In una sottoscrizione push, l'agente di merge o l'agente di distribuzione viene eseguito nel server di distribuzione, mentre in una sottoscrizione pull gli agenti vengono eseguiti nei Sottoscrittori.</span><span class="sxs-lookup"><span data-stu-id="9c7e9-107">With a push subscription, the Merge Agent or Distribution Agent runs at the Distributor, whereas with a pull subscription, agents run at the Subscribers.</span></span> <span data-ttu-id="9c7e9-108">Dopo la creazione di una sottoscrizione non è più possibile modificarne il tipo.</span><span class="sxs-lookup"><span data-stu-id="9c7e9-108">After a subscription is created, it cannot be changed from one type to another.</span></span>  
  
|<span data-ttu-id="9c7e9-109">Subscription</span><span class="sxs-lookup"><span data-stu-id="9c7e9-109">Subscription</span></span>|<span data-ttu-id="9c7e9-110">Caratteristiche</span><span class="sxs-lookup"><span data-stu-id="9c7e9-110">Characteristics</span></span>|<span data-ttu-id="9c7e9-111">Situazioni in cui utilizzarla</span><span class="sxs-lookup"><span data-stu-id="9c7e9-111">Use When</span></span>|  
|------------------|---------------------|--------------|  
|<span data-ttu-id="9c7e9-112">Sottoscrizione push</span><span class="sxs-lookup"><span data-stu-id="9c7e9-112">Push Subscription</span></span>|<span data-ttu-id="9c7e9-113">Nelle sottoscrizioni push il server di pubblicazione propaga le modifiche a un Sottoscrittore senza che il Sottoscrittore ne faccia richiesta.</span><span class="sxs-lookup"><span data-stu-id="9c7e9-113">With a push subscription, the Publisher propagates changes to a Subscriber without a request from the Subscriber.</span></span> <span data-ttu-id="9c7e9-114">È possibile inviare le modifiche ai Sottoscrittori su richiesta, in modo continuato o in base a una pianificazione definita.</span><span class="sxs-lookup"><span data-stu-id="9c7e9-114">Changes can be pushed to Subscribers on demand, continuously, or on a scheduled basis.</span></span> <span data-ttu-id="9c7e9-115">L'agente di distribuzione o l'agente di merge viene eseguito nel server di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="9c7e9-115">The Distribution Agent or Merge Agent runs at the Distributor.</span></span>|<span data-ttu-id="9c7e9-116">I dati vengono sincronizzati in modo continuato o in modo ricorrente in base a una pianificazione specifica.</span><span class="sxs-lookup"><span data-stu-id="9c7e9-116">Data will typically be synchronized continuously or on a frequently recurring schedule.</span></span><br /><br /> <span data-ttu-id="9c7e9-117">Le pubblicazioni richiedono lo spostamento dei dati quasi in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="9c7e9-117">Publications require near real-time movement of data.</span></span><br /><br /> <span data-ttu-id="9c7e9-118">In un server di distribuzione l'aumento dell'overhead del processore non compromette le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="9c7e9-118">The higher processor overhead at the Distributor does not affect performance.</span></span><br /><br /> <span data-ttu-id="9c7e9-119">Generalmente utilizzato con la replica snapshot e transazionale.</span><span class="sxs-lookup"><span data-stu-id="9c7e9-119">Most often used with snapshot and transactional replication.</span></span>|  
|<span data-ttu-id="9c7e9-120">Sottoscrizione pull</span><span class="sxs-lookup"><span data-stu-id="9c7e9-120">Pull Subscription</span></span>|<span data-ttu-id="9c7e9-121">Tramite le sottoscrizioni pull il Sottoscrittore richiede le modifiche eseguite nel server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="9c7e9-121">With a pull subscription, the Subscriber requests changes made at the Publisher.</span></span> <span data-ttu-id="9c7e9-122">Le sottoscrizioni pull consentono al Sottoscrittore di stabilire quando sincronizzare le modifiche apportate ai dati.</span><span class="sxs-lookup"><span data-stu-id="9c7e9-122">Pull subscriptions allow the user at the Subscriber to determine when the data changes are synchronized.</span></span> <span data-ttu-id="9c7e9-123">L'agente di distribuzione o l'agente di merge viene eseguito nel Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="9c7e9-123">The Distribution Agent or the Merge Agent runs at the Subscriber.</span></span>|<span data-ttu-id="9c7e9-124">I dati vengono sincronizzati su richiesta o in base a una pianificazione anziché in modo continuo.</span><span class="sxs-lookup"><span data-stu-id="9c7e9-124">Data will typically be synchronized on demand or on a schedule rather than continuously.</span></span><br /><br /> <span data-ttu-id="9c7e9-125">Alla pubblicazione è associato un numero elevato di Sottoscrittori e/o l'esecuzione di tutti gli agenti nel server di distribuzione richiederebbe un numero di risorse eccessivo.</span><span class="sxs-lookup"><span data-stu-id="9c7e9-125">The publication has a large number of Subscribers, and/or it would be too resource-intensive to run all the agents at the Distributor.</span></span><br /><br /> <span data-ttu-id="9c7e9-126">I Sottoscrittori sono autonomi, scollegati e/o mobili.</span><span class="sxs-lookup"><span data-stu-id="9c7e9-126">Subscribers are autonomous, disconnected, and/or mobile.</span></span> <span data-ttu-id="9c7e9-127">I Sottoscrittori determinano quando eseguire la connessione e quando sincronizzare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="9c7e9-127">Subscribers will determine when they will connect and synchronize changes.</span></span><br /><br /> <span data-ttu-id="9c7e9-128">Generalmente utilizzato con la replica di tipo merge.</span><span class="sxs-lookup"><span data-stu-id="9c7e9-128">Most often used with merge replication.</span></span>|  
  
## <a name="merge-replication-subscription-types"></a><span data-ttu-id="9c7e9-129">Tipi di sottoscrizione della replica di tipo merge</span><span class="sxs-lookup"><span data-stu-id="9c7e9-129">Merge Replication Subscription Types</span></span>  
 <span data-ttu-id="9c7e9-130">Tutti i tipi di replica consentono le sottoscrizioni push e pull.</span><span class="sxs-lookup"><span data-stu-id="9c7e9-130">All replication types allow push and pull subscriptions.</span></span> <span data-ttu-id="9c7e9-131">Per la replica di tipo merge vengono usati due termini aggiuntivi per distinguere le sottoscrizioni: sottoscrizioni client e sottoscrizioni server.</span><span class="sxs-lookup"><span data-stu-id="9c7e9-131">Merge replication uses two additional terms to distinguish subscriptions: client subscriptions and server subscriptions.</span></span> <span data-ttu-id="9c7e9-132">Le sottoscrizioni client e server possono essere entrambe utilizzate con le sottoscrizioni push e pull.</span><span class="sxs-lookup"><span data-stu-id="9c7e9-132">Both client and server subscription types can be used with push and pull subscriptions.</span></span> <span data-ttu-id="9c7e9-133">Le sottoscrizioni client sono appropriate per la maggior parte dei Sottoscrittori, mentre le sottoscrizioni server sono generalmente utilizzate per i Sottoscrittori che ripubblicano i dati in altri Sottoscrittori.</span><span class="sxs-lookup"><span data-stu-id="9c7e9-133">Client subscriptions are appropriate for most Subscribers, whereas server subscriptions are typically used for Subscribers that republish data to other Subscribers.</span></span> <span data-ttu-id="9c7e9-134">La scelta del tipo di sottoscrizione influisce anche sulla risoluzione dei conflitti.</span><span class="sxs-lookup"><span data-stu-id="9c7e9-134">Subscription choice also affects conflict resolution.</span></span>  
  
## <a name="non-sql-server-subscribers"></a><span data-ttu-id="9c7e9-135">Sottoscrittori non SQL Server</span><span class="sxs-lookup"><span data-stu-id="9c7e9-135">Non-SQL Server Subscribers</span></span>  
 <span data-ttu-id="9c7e9-136">Nei sistemi Oracle e IBM DB2 è possibile sottoscrivere pubblicazioni snapshot e transazionali mediante le sottoscrizioni push.</span><span class="sxs-lookup"><span data-stu-id="9c7e9-136">Oracle and IBM DB2 can subscribe to snapshot and transactional publications using push subscriptions.</span></span> <span data-ttu-id="9c7e9-137">Per altre informazioni, vedere [Non-SQL Server Subscribers](non-sql/non-sql-server-subscribers.md).</span><span class="sxs-lookup"><span data-stu-id="9c7e9-137">For more information, see [Non-SQL Server Subscribers](non-sql/non-sql-server-subscribers.md).</span></span>  
  
## <a name="creating-subscriptions"></a><span data-ttu-id="9c7e9-138">Creazione di sottoscrizioni</span><span class="sxs-lookup"><span data-stu-id="9c7e9-138">Creating Subscriptions</span></span>  
 <span data-ttu-id="9c7e9-139">Per creare una sottoscrizione, è necessario specificare le seguenti informazioni:</span><span class="sxs-lookup"><span data-stu-id="9c7e9-139">To create a subscription, you supply the following information:</span></span>  
  
-   <span data-ttu-id="9c7e9-140">Nome della pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="9c7e9-140">The name of the publication.</span></span>  
  
-   <span data-ttu-id="9c7e9-141">Nome del Sottoscrittore e database di sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="9c7e9-141">The name of the Subscriber and the subscription database.</span></span>  
  
-   <span data-ttu-id="9c7e9-142">Se l'agente di distribuzione o l'agente di merge viene eseguito nel server di distribuzione o nel Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="9c7e9-142">Whether the Distribution Agent or Merge Agent runs at the Distributor or at the Subscriber.</span></span>  
  
-   <span data-ttu-id="9c7e9-143">Se l'agente di distribuzione o di merge viene eseguito in modo continuato, in base a una pianificazione specifica oppure solo su richiesta.</span><span class="sxs-lookup"><span data-stu-id="9c7e9-143">Whether the Distribution Agent or Merge Agent runs continuously, on a scheduled basis, or on demand only.</span></span>  
  
-   <span data-ttu-id="9c7e9-144">Se l'agente di snapshot deve creare uno snapshot iniziale per la sottoscrizione e l'agente di distribuzione o di merge deve applicare lo snapshot al Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="9c7e9-144">Whether the Snapshot Agent should create an initial snapshot for the subscription and whether the Distribution Agent or Merge Agent should apply that snapshot at the Subscriber.</span></span>  
  
-   <span data-ttu-id="9c7e9-145">Account utilizzati per eseguire l'agente di distribuzione o di merge.</span><span class="sxs-lookup"><span data-stu-id="9c7e9-145">Accounts under which the Distribution Agent or Merge Agent will run.</span></span>  
  
-   <span data-ttu-id="9c7e9-146">Per la replica di tipo merge, il tipo di sottoscrizione: server o client.</span><span class="sxs-lookup"><span data-stu-id="9c7e9-146">For merge replication, the type of subscription: server or client.</span></span>  
  
 <span data-ttu-id="9c7e9-147">**Per creare una sottoscrizione push**</span><span class="sxs-lookup"><span data-stu-id="9c7e9-147">**To create a push subscription**</span></span>  
  
 [<span data-ttu-id="9c7e9-148">Creare una sottoscrizione push</span><span class="sxs-lookup"><span data-stu-id="9c7e9-148">Create a Push Subscription</span></span>](create-a-push-subscription.md)  
  
 <span data-ttu-id="9c7e9-149">**Per visualizzare o modificare le proprietà di sottoscrizione push**</span><span class="sxs-lookup"><span data-stu-id="9c7e9-149">**To view or modify push subscription properties**</span></span>  
  
 [<span data-ttu-id="9c7e9-150">Visualizzare e modificare le proprietà delle sottoscrizioni push</span><span class="sxs-lookup"><span data-stu-id="9c7e9-150">View and Modify Push Subscription Properties</span></span>](view-and-modify-push-subscription-properties.md)  
  
 <span data-ttu-id="9c7e9-151">**Per eliminare una sottoscrizione push**</span><span class="sxs-lookup"><span data-stu-id="9c7e9-151">**To delete a push subscription**</span></span>  
  
 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]<span data-ttu-id="9c7e9-152">: [Eliminare una sottoscrizione push](delete-a-push-subscription.md)</span><span class="sxs-lookup"><span data-stu-id="9c7e9-152">: [Delete a Push Subscription](delete-a-push-subscription.md)</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9c7e9-153">Se si elimina una sottoscrizione non si rimuovono gli oggetti pubblicati dal Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="9c7e9-153">Deleting a subscription does not remove published objects from the Subscriber.</span></span>  
  
 <span data-ttu-id="9c7e9-154">**Per creare una sottoscrizione pull**</span><span class="sxs-lookup"><span data-stu-id="9c7e9-154">**To create a pull subscription**</span></span>  
  
 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]<span data-ttu-id="9c7e9-155">: [Create a Pull Subscription](create-a-pull-subscription.md)</span><span class="sxs-lookup"><span data-stu-id="9c7e9-155">: [Create a Pull Subscription](create-a-pull-subscription.md)</span></span>  
  
 <span data-ttu-id="9c7e9-156">**Per visualizzare o modificare le proprietà di sottoscrizione pull**</span><span class="sxs-lookup"><span data-stu-id="9c7e9-156">**To view or modify pull subscription properties**</span></span>  
  
 [<span data-ttu-id="9c7e9-157">Visualizzare e modificare le proprietà delle sottoscrizioni pull</span><span class="sxs-lookup"><span data-stu-id="9c7e9-157">View and Modify Pull Subscription Properties</span></span>](view-and-modify-pull-subscription-properties.md)  
  
 <span data-ttu-id="9c7e9-158">**Per eliminare una sottoscrizione pull**</span><span class="sxs-lookup"><span data-stu-id="9c7e9-158">**To delete a pull subscription**</span></span>  
  
 [<span data-ttu-id="9c7e9-159">Eliminare una sottoscrizione pull</span><span class="sxs-lookup"><span data-stu-id="9c7e9-159">Delete a Pull Subscription</span></span>](delete-a-pull-subscription.md)  
  
## <a name="see-also"></a><span data-ttu-id="9c7e9-160">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9c7e9-160">See Also</span></span>  
 <span data-ttu-id="9c7e9-161">[Proteggere il Sottoscrittore](security/secure-the-subscriber.md) </span><span class="sxs-lookup"><span data-stu-id="9c7e9-161">[Secure the Subscriber](security/secure-the-subscriber.md) </span></span>  
 [<span data-ttu-id="9c7e9-162">Scadenza e disattivazione delle sottoscrizioni</span><span class="sxs-lookup"><span data-stu-id="9c7e9-162">Subscription Expiration and Deactivation</span></span>](subscription-expiration-and-deactivation.md)  
  
  
