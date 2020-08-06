---
title: Ripubblicare i dati | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- republishing data
- publishing [SQL Server replication], Subscribers
- Subscribers [SQL Server replication], republishing data
ms.assetid: a1485cf4-b1c4-49e9-ab06-8ccfaad998f3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f1e4213266121b3bf55bf2857e15f71f1e94e301
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624022"
---
# <a name="republish-data"></a><span data-ttu-id="5b191-102">Ripubblicazione dei dati</span><span class="sxs-lookup"><span data-stu-id="5b191-102">Republish Data</span></span>
  <span data-ttu-id="5b191-103">In un modello di ripubblicazione il server di pubblicazione invia i dati a un Sottoscrittore, il quale ripubblica i dati in un numero qualsiasi di altri Sottoscrittori.</span><span class="sxs-lookup"><span data-stu-id="5b191-103">In a republishing model, the Publisher sends data to a Subscriber, which then republishes the data to any number of other Subscribers.</span></span> <span data-ttu-id="5b191-104">Si tratta di un comportamento utile quando un server di pubblicazione deve inviare dati ai Sottoscrittori tramite un collegamento di comunicazione lento o costoso.</span><span class="sxs-lookup"><span data-stu-id="5b191-104">This is useful when a Publisher must send data to Subscribers over a slow or expensive communications link.</span></span> <span data-ttu-id="5b191-105">Se all'altro capo del collegamento sono presenti più Sottoscrittori, l'utilizzo di un server di ripubblicazione consente di trasferirvi il carico dell'attività di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="5b191-105">If there are a number of Subscribers on the far side of that link, using a republisher shifts the bulk of the distribution load to that side of the link.</span></span>  
  
 <span data-ttu-id="5b191-106">La ripubblicazione dei dati comprende i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="5b191-106">Republishing data involves the following steps:</span></span>  
  
1.  <span data-ttu-id="5b191-107">Creare una pubblicazione nel server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="5b191-107">Create a publication at the Publisher.</span></span>  
  
2.  <span data-ttu-id="5b191-108">Creare una sottoscrizione della pubblicazione per il Sottoscrittore di ripubblicazione.</span><span class="sxs-lookup"><span data-stu-id="5b191-108">Create a subscription to the publication for the republishing Subscriber.</span></span>  
  
3.  <span data-ttu-id="5b191-109">Inizializzare la sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="5b191-109">Initialize the subscription.</span></span> <span data-ttu-id="5b191-110">Perché la replica non abbia esito negativo, è necessario che la sottoscrizione sia inizializzata prima della creazione della pubblicazione nel Sottoscrittore di ripubblicazione.</span><span class="sxs-lookup"><span data-stu-id="5b191-110">The subscription must be initialized before the publication is created at the republishing Subscriber, or replication will fail.</span></span>  
  
4.  <span data-ttu-id="5b191-111">Creare una pubblicazione nel database di sottoscrizione del Sottoscrittore di ripubblicazione.</span><span class="sxs-lookup"><span data-stu-id="5b191-111">Create a publication in the subscription database at the republishing Subscriber.</span></span>  
  
5.  <span data-ttu-id="5b191-112">Creare sottoscrizioni della pubblicazione nel Sottoscrittore di ripubblicazione per altri Sottoscrittori.</span><span class="sxs-lookup"><span data-stu-id="5b191-112">Create subscriptions to the publication at the republishing Subscriber for the other Subscribers.</span></span>  
  
6.  <span data-ttu-id="5b191-113">Inizializzare le sottoscrizioni.</span><span class="sxs-lookup"><span data-stu-id="5b191-113">Initialize the subscriptions.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5b191-114">Se si utilizza la replica di tipo merge in una topologia di ripubblicazione, tutti i Sottoscrittori di ripubblicazione devono utilizzare sottoscrizioni server.</span><span class="sxs-lookup"><span data-stu-id="5b191-114">If you use merge replication in a republishing topology, all republishing Subscribers must use server subscriptions.</span></span> <span data-ttu-id="5b191-115">Per altre informazioni sui tipi di sottoscrizioni, vedere [Sottoscrivere le pubblicazioni](subscribe-to-publications.md).</span><span class="sxs-lookup"><span data-stu-id="5b191-115">For more information about subscription types, see [Subscribe to Publications](subscribe-to-publications.md).</span></span>  
  
 <span data-ttu-id="5b191-116">Nell'illustrazione seguente il server di pubblicazione e il server di ripubblicazione operano entrambi come server di distribuzione locali.</span><span class="sxs-lookup"><span data-stu-id="5b191-116">In the following illustration, both the Publisher and the republisher are acting as their own local Distributors.</span></span> <span data-ttu-id="5b191-117">Se sono stati configurati per l'utilizzo di un server di distribuzione remoto, ogni server di distribuzione deve trovarsi allo stesso capo di un collegamento di comunicazione lento o costoso e operare come server di pubblicazione proprio.</span><span class="sxs-lookup"><span data-stu-id="5b191-117">If each were set up to use a remote Distributor, each Distributor would need to be on the same side of the slow or expensive communications link as its Publisher.</span></span> <span data-ttu-id="5b191-118">È necessario che i server di pubblicazione siano connessi ai server di distribuzione remoti tramite collegamenti di comunicazioni affidabili e ad alta velocità.</span><span class="sxs-lookup"><span data-stu-id="5b191-118">Publishers must be connected to remote Distributors by reliable, high-speed communications links.</span></span>  
  
 <span data-ttu-id="5b191-119">![Ripubblicazione dei dati](media/repl-06a.gif "Ripubblicazione dei dati")</span><span class="sxs-lookup"><span data-stu-id="5b191-119">![Republishing data](media/repl-06a.gif "Republishing data")</span></span>  
  
 <span data-ttu-id="5b191-120">Ogni server può operare sia come server di pubblicazione che come Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="5b191-120">Any server can act as both a Publisher and Subscriber.</span></span> <span data-ttu-id="5b191-121">Si consideri ad esempio la figura seguente, in cui la pubblicazione di una tabella ubicata a Londra deve essere distribuita in quattro diverse città degli Stati Uniti: Chicago, New York, San Diego e Seattle.</span><span class="sxs-lookup"><span data-stu-id="5b191-121">For example, consider the following diagram in which a publication of a table exists in London and must be distributed to four different cities in the United States: Chicago, New York, San Diego, and Seattle.</span></span> <span data-ttu-id="5b191-122">Per la sottoscrizione della tabella pubblicata creata a Londra viene scelto il server di New York, in quanto risponde ai requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="5b191-122">The server in New York is chosen to subscribe to the published table originating in London, because the New York site meets these conditions:</span></span>  
  
-   <span data-ttu-id="5b191-123">La connessione di rete con Londra è relativamente affidabile.</span><span class="sxs-lookup"><span data-stu-id="5b191-123">The network link back to London is relatively reliable.</span></span>  
  
-   <span data-ttu-id="5b191-124">I costi di comunicazione tra Londra e New York sono accettabili.</span><span class="sxs-lookup"><span data-stu-id="5b191-124">The London-to-New York communication costs are acceptable.</span></span>  
  
-   <span data-ttu-id="5b191-125">Le linee di comunicazione di rete tra New York e tutti gli altri Sottoscrittori statunitensi sono efficienti.</span><span class="sxs-lookup"><span data-stu-id="5b191-125">There are good network communications lines from New York to all other Subscriber sites in the United States.</span></span>  
  
     <span data-ttu-id="5b191-126">![Ripubblicazione dei dati in varie posizioni](media/repl-06.gif "Ripubblicazione dei dati in varie posizioni")</span><span class="sxs-lookup"><span data-stu-id="5b191-126">![Republishing data to dispersed locations](media/repl-06.gif "Republishing data to dispersed locations")</span></span>  
  
 <span data-ttu-id="5b191-127">La replica supporta gli scenari di ripubblicazione illustrati nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="5b191-127">Replication supports the republishing scenarios shown in the following table.</span></span>  
  
|<span data-ttu-id="5b191-128">Editore</span><span class="sxs-lookup"><span data-stu-id="5b191-128">Publisher</span></span>|<span data-ttu-id="5b191-129">Sottoscrittore di pubblicazione</span><span class="sxs-lookup"><span data-stu-id="5b191-129">Publishing Subscriber</span></span>|<span data-ttu-id="5b191-130">Sottoscrittore</span><span class="sxs-lookup"><span data-stu-id="5b191-130">Subscriber</span></span>|  
|---------------|---------------------------|----------------|  
|<span data-ttu-id="5b191-131">Pubblicazione transazionale</span><span class="sxs-lookup"><span data-stu-id="5b191-131">Transactional publication</span></span>|<span data-ttu-id="5b191-132">Sottoscrizione transazionale/pubblicazione transazionale</span><span class="sxs-lookup"><span data-stu-id="5b191-132">Transactional subscription/transactional publication</span></span>|<span data-ttu-id="5b191-133">Sottoscrizione transazionale</span><span class="sxs-lookup"><span data-stu-id="5b191-133">Transactional subscription</span></span>|  
|<span data-ttu-id="5b191-134">Pubblicazione transazionale</span><span class="sxs-lookup"><span data-stu-id="5b191-134">Transactional publication</span></span>|<span data-ttu-id="5b191-135">Sottoscrizione transazionale/pubblicazione di tipo merge<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="5b191-135">Transactional subscription/merge publication<sup>1</sup></span></span>|<span data-ttu-id="5b191-136">Sottoscrizione di tipo merge</span><span class="sxs-lookup"><span data-stu-id="5b191-136">Merge subscription</span></span>|  
|<span data-ttu-id="5b191-137">Pubblicazione di tipo merge</span><span class="sxs-lookup"><span data-stu-id="5b191-137">Merge publication</span></span>|<span data-ttu-id="5b191-138">Sottoscrizione di tipo merge/pubblicazione di tipo merge</span><span class="sxs-lookup"><span data-stu-id="5b191-138">Merge subscription/merge publication</span></span>|<span data-ttu-id="5b191-139">Sottoscrizione di tipo merge</span><span class="sxs-lookup"><span data-stu-id="5b191-139">Merge subscription</span></span>|  
|<span data-ttu-id="5b191-140">Pubblicazione di tipo merge</span><span class="sxs-lookup"><span data-stu-id="5b191-140">Merge publication</span></span>|<span data-ttu-id="5b191-141">Sottoscrizione di tipo merge/pubblicazione transazionale</span><span class="sxs-lookup"><span data-stu-id="5b191-141">Merge subscription/transactional publication</span></span>|<span data-ttu-id="5b191-142">Sottoscrizione transazionale</span><span class="sxs-lookup"><span data-stu-id="5b191-142">Transactional subscription</span></span>|  
  
 <span data-ttu-id="5b191-143"><sup>1</sup> È necessario impostare la `@published_in_tran_pub` proprietà sulla pubblicazione di tipo merge.</span><span class="sxs-lookup"><span data-stu-id="5b191-143"><sup>1</sup>You should set the `@published_in_tran_pub` property on the merge publication.</span></span> <span data-ttu-id="5b191-144">Per impostazione predefinita, la replica transazionale prevede che le tabelle nel Sottoscrittore vengano considerate di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="5b191-144">By default, transactional replication expects tables at the Subscriber to be treated as read-only.</span></span> <span data-ttu-id="5b191-145">Se durante la replica di tipo merge vengono apportate modifiche a una tabella in una sottoscrizione transazionale, si potrà verificare una mancata convergenza dei dati.</span><span class="sxs-lookup"><span data-stu-id="5b191-145">If merge replication makes data changes to a table in a transactional subscription, non-convergence of data can occur.</span></span> <span data-ttu-id="5b191-146">Per evitare questo rischio, si suggerisce di specificare queste tabelle come di solo download nella pubblicazione di tipo merge.</span><span class="sxs-lookup"><span data-stu-id="5b191-146">To avoid this risk, we recommend that any such table be specified as download-only in the merge publication.</span></span> <span data-ttu-id="5b191-147">In tal modo si impedisce al Sottoscrittore di tipo merge di caricare le modifiche ai dati nella tabella.</span><span class="sxs-lookup"><span data-stu-id="5b191-147">This prevents a merge Subscriber from uploading data changes to the table.</span></span> <span data-ttu-id="5b191-148">Per altre informazioni, vedere [Ottimizzare le prestazioni della replica di tipo merge con gli articoli di solo download](merge/optimize-merge-replication-performance-with-download-only-articles.md).</span><span class="sxs-lookup"><span data-stu-id="5b191-148">For more information, see [Optimize Merge Replication Performance with Download-Only Articles](merge/optimize-merge-replication-performance-with-download-only-articles.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b191-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5b191-149">See Also</span></span>  
 <span data-ttu-id="5b191-150">[Configura distribuzione](configure-distribution.md) </span><span class="sxs-lookup"><span data-stu-id="5b191-150">[Configure Distribution](configure-distribution.md) </span></span>  
 <span data-ttu-id="5b191-151">[Pubblicare dati e oggetti di database](publish/publish-data-and-database-objects.md) </span><span class="sxs-lookup"><span data-stu-id="5b191-151">[Publish Data and Database Objects](publish/publish-data-and-database-objects.md) </span></span>  
 <span data-ttu-id="5b191-152">[Subscribe to Publications](subscribe-to-publications.md) </span><span class="sxs-lookup"><span data-stu-id="5b191-152">[Subscribe to Publications](subscribe-to-publications.md) </span></span>  
 <span data-ttu-id="5b191-153">[Inizializzare una sottoscrizione](initialize-a-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="5b191-153">[Initialize a Subscription](initialize-a-subscription.md) </span></span>  
 [<span data-ttu-id="5b191-154">Sincronizzare i dati</span><span class="sxs-lookup"><span data-stu-id="5b191-154">Synchronize Data</span></span>](synchronize-data.md)  
  
  
