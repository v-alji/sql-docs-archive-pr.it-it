---
title: Agente snapshot (Creazione guidata nuova pubblicazione) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.newpubwizard.configuresnapshotagent.f1
ms.assetid: 0257d4ee-1f7b-49fd-b4ef-65bfc1ef6951
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c45fa3444fb2f81436a40a2bfb80519aea105c47
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637754"
---
# <a name="snapshot-agent-new-publication-wizard"></a><span data-ttu-id="f7205-102">Agente snapshot (Creazione guidata nuova pubblicazione)</span><span class="sxs-lookup"><span data-stu-id="f7205-102">Snapshot Agent (New Publication Wizard)</span></span>
  <span data-ttu-id="f7205-103">L'agente snapshot crea file contenenti lo schema della pubblicazione e i dati utilizzati per inizializzare nuove sottoscrizioni.</span><span class="sxs-lookup"><span data-stu-id="f7205-103">The Snapshot Agent creates files containing the publication schema and data that are used to initialize new subscriptions.</span></span> <span data-ttu-id="f7205-104">Per impostazione predefinita, l'agente snapshot viene eseguito immediatamente dopo la creazione della pubblicazione mediante Creazione guidata nuova pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="f7205-104">By default, the Snapshot Agent runs immediately after the publication is created in the New Publication Wizard.</span></span> <span data-ttu-id="f7205-105">L'agente verrà successivamente eseguito in base alla pianificazione impostata dall'utente.</span><span class="sxs-lookup"><span data-stu-id="f7205-105">Subsequently, the agent runs according to a schedule you specify.</span></span> <span data-ttu-id="f7205-106">L'eventuale creazione di nuovi file di snapshot a ogni esecuzione dell'agente dipende dal tipo di replica e dalle opzioni scelte.</span><span class="sxs-lookup"><span data-stu-id="f7205-106">Whether the agent creates new snapshot files each time it runs depends on the type of replication and options chosen.</span></span> <span data-ttu-id="f7205-107">Per altre informazioni, vedere [Creare e applicare lo snapshot](create-and-apply-the-snapshot.md).</span><span class="sxs-lookup"><span data-stu-id="f7205-107">For more information, see [Create and Apply the Snapshot](create-and-apply-the-snapshot.md).</span></span>  
  
 <span data-ttu-id="f7205-108">Per le pubblicazioni di tipo merge che utilizzano filtri con parametri, è necessario creare uno snapshot per ogni partizione di dati dopo il completamento dello snapshot di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="f7205-108">For merge publications that use parameterized filters, you must create a snapshot for each partition of data after the publication snapshot has completed.</span></span> <span data-ttu-id="f7205-109">Per altre informazioni, vedere [Snapshots for Merge Publications with Parameterized Filters](snapshots-for-merge-publications-with-parameterized-filters.md).</span><span class="sxs-lookup"><span data-stu-id="f7205-109">For more information, see [Snapshots for Merge Publications with Parameterized Filters](snapshots-for-merge-publications-with-parameterized-filters.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="f7205-110">Opzioni</span><span class="sxs-lookup"><span data-stu-id="f7205-110">Options</span></span>  
 <span data-ttu-id="f7205-111">**Crea snapshot immediatamente** (replica di tipo merge) o **Crea uno snapshot immediatamente e mantieni lo snapshot disponibile per l'inizializzazione delle sottoscrizioni** (replica transazionale)</span><span class="sxs-lookup"><span data-stu-id="f7205-111">**Create a snapshot immediately** (merge replication) or **Create a snapshot immediately and keep the snapshot available to initialize subscriptions** (transactional replication)</span></span>  
 <span data-ttu-id="f7205-112">Selezionare questa casella di controllo per creare uno snapshot non appena viene completata la Creazione guidata nuova pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="f7205-112">Select this check box to create a snapshot immediately after the New Publication Wizard is completed.</span></span> <span data-ttu-id="f7205-113">Deselezionarla invece se si prevede di modificare le proprietà dello snapshot nella finestra di dialogo **Proprietà pubblicazione** prima di generare uno snapshot oppure se il Sottoscrittore verrà inizializzato senza alcuno snapshot.</span><span class="sxs-lookup"><span data-stu-id="f7205-113">Clear this check box if you plan to change snapshot properties in the **Publication Properties** dialog box before generating a snapshot, or if you will initialize the Subscriber without a snapshot.</span></span> <span data-ttu-id="f7205-114">Per altre informazioni, vedere [Inizializzazione di una sottoscrizione transazionale senza uno snapshot](initialize-a-transactional-subscription-without-a-snapshot.md).</span><span class="sxs-lookup"><span data-stu-id="f7205-114">For more information, see [Initialize a Transactional Subscription Without a Snapshot](initialize-a-transactional-subscription-without-a-snapshot.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f7205-115">Durante la procedura guidata è possibile che venga richiesto di selezionare la connessione al server di distribuzione per consentire l'avvio del processo appropriato per l'agente di distribuzione o l'agente di merge.</span><span class="sxs-lookup"><span data-stu-id="f7205-115">The wizard might prompt for a connection to the Distributor in order to start the appropriate job for the Distribution Agent or Merge Agent.</span></span>  
  
 <span data-ttu-id="f7205-116">**Usa la pianificazione seguente per l'esecuzione dell'agente snapshot**</span><span class="sxs-lookup"><span data-stu-id="f7205-116">**Schedule the Snapshot Agent to run at the following times**</span></span>  
 <span data-ttu-id="f7205-117">Accettare la pianificazione predefinita per l'esecuzione dell'agente snapshot oppure fare clic su **Cambia** per specificare una pianificazione diversa.</span><span class="sxs-lookup"><span data-stu-id="f7205-117">Accept the default schedule for running the Snapshot Agent, or click **Change** to specify a schedule.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7205-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f7205-118">See Also</span></span>  
 <span data-ttu-id="f7205-119">[Create a Publication](publish/create-a-publication.md) </span><span class="sxs-lookup"><span data-stu-id="f7205-119">[Create a Publication](publish/create-a-publication.md) </span></span>  
 <span data-ttu-id="f7205-120">[Creare e applicare lo snapshot iniziale](create-and-apply-the-initial-snapshot.md) </span><span class="sxs-lookup"><span data-stu-id="f7205-120">[Create and Apply the Initial Snapshot](create-and-apply-the-initial-snapshot.md) </span></span>  
 <span data-ttu-id="f7205-121">[Visualizzare e modificare le proprietà della pubblicazione](publish/view-and-modify-publication-properties.md) </span><span class="sxs-lookup"><span data-stu-id="f7205-121">[View and Modify Publication Properties](publish/view-and-modify-publication-properties.md) </span></span>  
 <span data-ttu-id="f7205-122">[Inizializzare una sottoscrizione con uno snapshot](initialize-a-subscription-with-a-snapshot.md) </span><span class="sxs-lookup"><span data-stu-id="f7205-122">[Initialize a Subscription with a Snapshot](initialize-a-subscription-with-a-snapshot.md) </span></span>  
 <span data-ttu-id="f7205-123">[Pubblicare dati e oggetti di database](publish/publish-data-and-database-objects.md) </span><span class="sxs-lookup"><span data-stu-id="f7205-123">[Publish Data and Database Objects](publish/publish-data-and-database-objects.md) </span></span>  
 [<span data-ttu-id="f7205-124">Panoramica degli agenti di replica</span><span class="sxs-lookup"><span data-stu-id="f7205-124">Replication Agents Overview</span></span>](agents/replication-agents-overview.md)  
  
  
