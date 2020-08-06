---
title: Inizializzare le sottoscrizioni | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.newsubwizard.initializesubscriptions.f1
ms.assetid: 7b170e4e-470d-4828-a9ed-7435b0b03514
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f8c9388138ddec275dc1abd2b75e0b0c7fc99de4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624576"
---
# <a name="initialize-subscriptions"></a><span data-ttu-id="b52db-102">Inizializzazione sottoscrizioni</span><span class="sxs-lookup"><span data-stu-id="b52db-102">Initialize Subscriptions</span></span>
  <span data-ttu-id="b52db-103">È necessario inizializzare i Sottoscrittori prima che possano iniziare a ricevere dati replicati.</span><span class="sxs-lookup"><span data-stu-id="b52db-103">Subscribers must be initialized before they can begin receiving replicated data.</span></span> <span data-ttu-id="b52db-104">Non è necessario un set di dati iniziale, ma è necessario che il Sottoscrittore disponga almeno dello schema per ogni oggetto replicato, nonché delle tabelle dei metadati e delle procedure necessarie per la replica.</span><span class="sxs-lookup"><span data-stu-id="b52db-104">An initial dataset is not required, but the Subscriber must at least have the schema for each replicated object and any metadata tables and procedures required by replication.</span></span>  
  
## <a name="options"></a><span data-ttu-id="b52db-105">Opzioni</span><span class="sxs-lookup"><span data-stu-id="b52db-105">Options</span></span>  
 <span data-ttu-id="b52db-106">**Proprietà sottoscrizione**</span><span class="sxs-lookup"><span data-stu-id="b52db-106">**Subscription properties**</span></span>  
 <span data-ttu-id="b52db-107">Selezionare la casella di controllo nella colonna **Inizializza** per ogni Sottoscrittore che necessita di un set di dati iniziale.</span><span class="sxs-lookup"><span data-stu-id="b52db-107">Select the check box in the **Initialize** column for each Subscriber that requires an initial data set.</span></span> <span data-ttu-id="b52db-108">Se la casella di controllo non è selezionata, verranno inizializzati solo i metadati e le procedure della replica.</span><span class="sxs-lookup"><span data-stu-id="b52db-108">If the check box is cleared, only the replication metadata and procedures will be initialized.</span></span> <span data-ttu-id="b52db-109">Per altre informazioni sull'inizializzazione di una sottoscrizione senza uno snapshot, vedere [Inizializzare una sottoscrizione transazionale senza uno snapshot](initialize-a-transactional-subscription-without-a-snapshot.md).</span><span class="sxs-lookup"><span data-stu-id="b52db-109">For more information about initializing a subscription without a snapshot, see [Initialize a Transactional Subscription Without a Snapshot](initialize-a-transactional-subscription-without-a-snapshot.md).</span></span>  
  
 <span data-ttu-id="b52db-110">Selezionare **Immediatamente** nell'elenco a discesa della colonna **Quando** per fare in modo che l'agente di merge o l'agente di distribuzione trasferisca i file di snapshot al Sottoscrittore al termine della procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="b52db-110">Select **Immediately** from the drop-down list box in the **Initialize When** column to have the Merge Agent or Distribution Agent transfer snapshot files to the Subscriber after this wizard is completed.</span></span> <span data-ttu-id="b52db-111">Selezionare **Alla prima sincronizzazione** per fare in modo che l'agente trasferisca i file alla successiva esecuzione pianificata dell'agente.</span><span class="sxs-lookup"><span data-stu-id="b52db-111">Select **At first synchronization** to have the agent transfer the files the next time it is scheduled to run.</span></span> <span data-ttu-id="b52db-112">L'opzione **Immediatamente** non è disponibile per le sottoscrizioni pull di [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b52db-112">The **Immediately** option is not available for pull subscriptions to [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)].</span></span> <span data-ttu-id="b52db-113">L'agente di merge e l'agente di distribuzione non vengono eseguiti nelle istanze di [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)]. È pertanto necessario inizializzare la sottoscrizione utilizzando un altro metodo.</span><span class="sxs-lookup"><span data-stu-id="b52db-113">The Merge Agent and Distribution Agent do not run on instances of [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)]; therefore the subscription must be initialized through another method.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b52db-114">Durante la procedura guidata è possibile che venga richiesto di selezionare la connessione al server di distribuzione per consentire l'avvio del processo appropriato per l'agente di distribuzione o l'agente di merge.</span><span class="sxs-lookup"><span data-stu-id="b52db-114">The wizard might prompt for a connection to the Distributor in order to start the appropriate job for the Distribution Agent or Merge Agent.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b52db-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b52db-115">See Also</span></span>  
 <span data-ttu-id="b52db-116">[Create a Pull Subscription](create-a-pull-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="b52db-116">[Create a Pull Subscription](create-a-pull-subscription.md) </span></span>  
 <span data-ttu-id="b52db-117">[Create a Push Subscription](create-a-push-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="b52db-117">[Create a Push Subscription](create-a-push-subscription.md) </span></span>  
 <span data-ttu-id="b52db-118">[Inizializzare una sottoscrizione](initialize-a-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="b52db-118">[Initialize a Subscription](initialize-a-subscription.md) </span></span>  
 [<span data-ttu-id="b52db-119">Sottoscrizione delle pubblicazioni</span><span class="sxs-lookup"><span data-stu-id="b52db-119">Subscribe to Publications</span></span>](subscribe-to-publications.md)  
  
  
