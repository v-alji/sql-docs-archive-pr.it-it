---
title: Sincronizzare i dati | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- synchronization [SQL Server replication], about synchronization
- merge replication synchronization [SQL Server replication]
- scripts [SQL Server replication], synchronization and
- synchronization [SQL Server replication]
- snapshot replication [SQL Server], synchronization
- transactional replication, synchronization
- subscriptions [SQL Server replication], synchronizing
- on demand script execution
- replication [SQL Server], synchronization
- scripts [SQL Server replication]
ms.assetid: 724802f7-7d69-46d3-a330-bd8aa7f53114
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c92cc4d1ae8e836f169a731ecf3c37c81f3dbf10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716231"
---
# <a name="synchronize-data"></a><span data-ttu-id="9ae20-102">Sincronizzare i dati</span><span class="sxs-lookup"><span data-stu-id="9ae20-102">Synchronize Data</span></span>
  <span data-ttu-id="9ae20-103">La sincronizzazione dei dati è il processo di propagazione dei dati e delle modifiche di schema tra il server di pubblicazione e i Sottoscrittori dopo l'applicazione dello snapshot iniziale al Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="9ae20-103">Synchronizing data refers to the process of data and schema changes being propagated between the Publisher and Subscribers after the initial snapshot has been applied at the Subscriber.</span></span> <span data-ttu-id="9ae20-104">La sincronizzazione può verificarsi:</span><span class="sxs-lookup"><span data-stu-id="9ae20-104">Synchronization can occur:</span></span>  
  
-   <span data-ttu-id="9ae20-105">Continuamente, come avviene in genere per la replica transazionale.</span><span class="sxs-lookup"><span data-stu-id="9ae20-105">Continuously, which is typical for transactional replication.</span></span>  
  
-   <span data-ttu-id="9ae20-106">Su richiesta, come avviene in genere per la replica di tipo merge.</span><span class="sxs-lookup"><span data-stu-id="9ae20-106">On demand, which is typical for merge replication.</span></span>  
  
-   <span data-ttu-id="9ae20-107">In base a una pianificazione, come avviene in genere con la replica snapshot.</span><span class="sxs-lookup"><span data-stu-id="9ae20-107">On a schedule, which is typical for snapshot replication.</span></span>  
  
 <span data-ttu-id="9ae20-108">Quando una sottoscrizione viene sincronizzata, si verificano processi differenti in base al tipo di replica in uso:</span><span class="sxs-lookup"><span data-stu-id="9ae20-108">When a subscription is synchronized, different processes occur based on the type of replication you are using:</span></span>  
  
-   <span data-ttu-id="9ae20-109">Replica snapshot.</span><span class="sxs-lookup"><span data-stu-id="9ae20-109">Snapshot replication.</span></span> <span data-ttu-id="9ae20-110">La sincronizzazione indica che l'agente di distribuzione riapplica lo snapshot al Sottoscrittore in modo che i dati e lo schema del database di sottoscrizione siano consistenti con il database di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="9ae20-110">Synchronization means that the Distribution Agent reapplies the snapshot at the Subscriber so that schema and data at the subscription database is consistent with the publication database.</span></span>  
  
     <span data-ttu-id="9ae20-111">Se nel server di pubblicazione sono state apportate modifiche ai dati o allo schema, è necessario generare un nuovo snapshot per poter propagare le modifiche al Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="9ae20-111">If modifications to data or schema have been made at the Publisher, a new snapshot must be generated in order to propagate modifications to the Subscriber.</span></span>  
  
-   <span data-ttu-id="9ae20-112">Replica transazionale.</span><span class="sxs-lookup"><span data-stu-id="9ae20-112">Transactional replication.</span></span> <span data-ttu-id="9ae20-113">La sincronizzazione indica che l'agente di distribuzione trasferisce aggiornamenti, inserimenti, eliminazioni e qualsiasi altra modifica dal database di distribuzione al Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="9ae20-113">Synchronization means that the Distribution Agent transfers updates, inserts, deletes, and any other changes from the distribution database to the Subscriber.</span></span>  
  
-   <span data-ttu-id="9ae20-114">Replica di tipo merge.</span><span class="sxs-lookup"><span data-stu-id="9ae20-114">Merge replication.</span></span> <span data-ttu-id="9ae20-115">La sincronizzazione indica che l'agente di tipo merge carica le modifiche dal Sottoscrittore nel server di pubblicazione e quindi le scarica dal server di pubblicazione nel Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="9ae20-115">Synchronization means that the Merge Agent uploads changes from the Subscriber to the Publisher and then downloads changes from the Publisher to the Subscriber.</span></span> <span data-ttu-id="9ae20-116">Gli eventuali conflitti vengono rilevati e risolti.</span><span class="sxs-lookup"><span data-stu-id="9ae20-116">Conflicts, if any, are detected and resolved.</span></span> <span data-ttu-id="9ae20-117">Al termine viene eseguita la convergenza dei dati e nel server di pubblicazione e in tutti i Sottoscrittori saranno disponibili gli stessi valori di dati.</span><span class="sxs-lookup"><span data-stu-id="9ae20-117">Data is converged, and the Publisher and all Subscribers eventually end up with the same data values.</span></span> <span data-ttu-id="9ae20-118">Se sono stati rilevati e risolti dei conflitti, il commit del lavoro eseguito da alcuni utenti viene modificato allo scopo di risolvere il conflitto in base ai criteri definiti.</span><span class="sxs-lookup"><span data-stu-id="9ae20-118">If conflicts were detected and resolved, work that was committed by some of the users is changed to resolve the conflict according to policies you define.</span></span>  
  
 <span data-ttu-id="9ae20-119">Le pubblicazioni snapshot aggiornano completamente lo schema nel Sottoscrittore a ogni sincronizzazione, in modo da applicare a quest'ultimo tutte le modifiche di schema.</span><span class="sxs-lookup"><span data-stu-id="9ae20-119">Snapshot publications completely refresh the schema at the Subscriber every time synchronization occurs, so all schema changes are applied to the Subscriber.</span></span> <span data-ttu-id="9ae20-120">La replica transazionale e la replica di tipo merge supportano inoltre le modifiche di schema più comuni.</span><span class="sxs-lookup"><span data-stu-id="9ae20-120">Transactional replication and merge replication also support the most common schema changes.</span></span> <span data-ttu-id="9ae20-121">Per altre informazioni, vedere [Apportare modifiche allo schema nei database di pubblicazione](publish/make-schema-changes-on-publication-databases.md).</span><span class="sxs-lookup"><span data-stu-id="9ae20-121">For more information, see [Make Schema Changes on Publication Databases](publish/make-schema-changes-on-publication-databases.md).</span></span>  
  
 <span data-ttu-id="9ae20-122">Per sincronizzazione di una sottoscrizione push, vedere [Synchronize a Push Subscription](synchronize-a-push-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="9ae20-122">To synchronize a push subscription, see [Synchronize a Push Subscription](synchronize-a-push-subscription.md).</span></span>  
  
 <span data-ttu-id="9ae20-123">Per sincronizzazione di una sottoscrizione pull, vedere [Synchronize a Pull Subscription](synchronize-a-pull-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="9ae20-123">To synchronize a pull subscription, see [Synchronize a Pull Subscription](synchronize-a-pull-subscription.md).</span></span>  
  
 <span data-ttu-id="9ae20-124">Per impostare le pianificazioni della sincronizzazione, vedere [Specify Synchronization Schedules](specify-synchronization-schedules.md).</span><span class="sxs-lookup"><span data-stu-id="9ae20-124">To set synchronization schedules, see [Specify Synchronization Schedules](specify-synchronization-schedules.md).</span></span>  
  
 <span data-ttu-id="9ae20-125">**Per visualizzare e risolvere i conflitti di sincronizzazione**</span><span class="sxs-lookup"><span data-stu-id="9ae20-125">**To view and resolve synchronization conflicts**</span></span>  
  
-   [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]<span data-ttu-id="9ae20-126">: [Visualizzare e risolvere i conflitti di dati per le pubblicazioni di tipo merge &#40;SQL Server Management Studio&#41;](view-and-resolve-data-conflicts-for-merge-publications.md)</span><span class="sxs-lookup"><span data-stu-id="9ae20-126">: [View and Resolve Data Conflicts for Merge Publications &#40;SQL Server Management Studio&#41;](view-and-resolve-data-conflicts-for-merge-publications.md)</span></span>  
  
-   [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]<span data-ttu-id="9ae20-127">: [Visualizzare i conflitti di dati per le pubblicazioni transazionali &#40;SQL Server Management Studio&#41;](view-data-conflicts-for-transactional-publications-sql-server-management-studio.md)</span><span class="sxs-lookup"><span data-stu-id="9ae20-127">: [View Data Conflicts for Transactional Publications &#40;SQL Server Management Studio&#41;](view-data-conflicts-for-transactional-publications-sql-server-management-studio.md)</span></span>  
  
## <a name="executing-code-during-synchronization"></a><span data-ttu-id="9ae20-128">Esecuzione di codice durante la sincronizzazione</span><span class="sxs-lookup"><span data-stu-id="9ae20-128">Executing Code During Synchronization</span></span>  
 <span data-ttu-id="9ae20-129">La replica supporta due modalità di esecuzione del codice durante la sincronizzazione</span><span class="sxs-lookup"><span data-stu-id="9ae20-129">Replication supports two methods of executing code during synchronization</span></span>  
  
-   <span data-ttu-id="9ae20-130">L'esecuzione degli script su richiesta è supportata per la replica transazionale e di tipo merge.</span><span class="sxs-lookup"><span data-stu-id="9ae20-130">On demand script execution is supported for transactional replication and merge replication.</span></span> <span data-ttu-id="9ae20-131">L'utilizzo di questa modalità di esecuzione consente di specificare che uno script SQL venga eseguito durante la sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="9ae20-131">Using on demand script execution you can specify a SQL script to run during synchronization.</span></span> <span data-ttu-id="9ae20-132">Lo script viene copiato nel Sottoscrittore ed eseguito utilizzando **sqlcmd** all'inizio del processo di sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="9ae20-132">The script is copied to the Subscriber and executed using **sqlcmd** at the beginning of the synchronization process.</span></span> <span data-ttu-id="9ae20-133">Tale script non dispone di accesso alle modifiche replicate applicate al Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="9ae20-133">The script does not have access to the replicated changes as they are applied to the Subscriber.</span></span> <span data-ttu-id="9ae20-134">Per altre informazioni, vedere [Eseguire script durante la sincronizzazione &#40;programmazione Transact-SQL della replica&#41;](execute-scripts-during-synchronization-replication-transact-sql-programming.md).</span><span class="sxs-lookup"><span data-stu-id="9ae20-134">For more information, see [Execute Scripts During Synchronization &#40;Replication Transact-SQL Programming&#41;](execute-scripts-during-synchronization-replication-transact-sql-programming.md).</span></span>  
  
-   <span data-ttu-id="9ae20-135">La replica di tipo merge supporta i gestori della logica di business.</span><span class="sxs-lookup"><span data-stu-id="9ae20-135">Business logic handlers are supported for merge replication.</span></span> <span data-ttu-id="9ae20-136">Grazie all'utilizzo del framework di gestione della logica di business è possibile scrivere un assembly del codice gestito che viene chiamato durante il processo di sincronizzazione di tipo merge.</span><span class="sxs-lookup"><span data-stu-id="9ae20-136">Using the business logic handler framework you can write a managed code assembly that is called during the merge synchronization process.</span></span> <span data-ttu-id="9ae20-137">L'assembly include la logica di business che consente di rispondere a diverse situazioni durante la sincronizzazione, ad esempio modifiche ai dati, conflitti ed errori.</span><span class="sxs-lookup"><span data-stu-id="9ae20-137">The assembly includes business logic that can respond to a number of conditions during synchronization: data changes, conflicts, and errors.</span></span> <span data-ttu-id="9ae20-138">Per altre informazioni, vedere [Eseguire logiche di business durante la sincronizzazione di tipo merge](merge/execute-business-logic-during-merge-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="9ae20-138">For more information, see [Execute Business Logic During Merge Synchronization](merge/execute-business-logic-during-merge-synchronization.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ae20-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9ae20-139">See Also</span></span>  
 [<span data-ttu-id="9ae20-140">Rilevare e risolvere i conflitti tra repliche di tipo merge</span><span class="sxs-lookup"><span data-stu-id="9ae20-140">Detect and Resolve Merge Replication Conflicts</span></span>](merge/advanced-merge-replication-conflict-detection-and-resolution.md)  
  
  
