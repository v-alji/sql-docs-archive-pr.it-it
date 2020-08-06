---
title: Sottoscrizioni aggiornabili | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.newsubwizard.updatablesubscriptions.f1
ms.assetid: 8e9a13a0-6b24-47c6-9d83-3cbaf08f673d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 447114152365e098420f46d4b7e880e8f2907864
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714144"
---
# <a name="updatable-subscriptions"></a><span data-ttu-id="efe41-102">Sottoscrizioni aggiornabili</span><span class="sxs-lookup"><span data-stu-id="efe41-102">Updatable Subscriptions</span></span>
  <span data-ttu-id="efe41-103">Con la replica transazionale, è consigliabile usare i dati replicati in sola lettura. È tuttavia possibile modificare i dati replicati nel Sottoscrittore [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando le sottoscrizioni aggiornabili.</span><span class="sxs-lookup"><span data-stu-id="efe41-103">With transactional replication, replicated data should be treated as read-only; however, you can modify replicated data at a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Subscriber by using updatable subscriptions.</span></span> <span data-ttu-id="efe41-104">Se è necessario modificare i dati nel Sottoscrittore, scegliere una delle opzioni seguenti in base ai requisiti specifici.</span><span class="sxs-lookup"><span data-stu-id="efe41-104">If you need to modify data at the Subscriber, choose one of the following options depending on your requirements.</span></span>  
  
|<span data-ttu-id="efe41-105">Tipo di sottoscrizione aggiornabile</span><span class="sxs-lookup"><span data-stu-id="efe41-105">Updatable Subscription Type</span></span>|<span data-ttu-id="efe41-106">Requisiti</span><span class="sxs-lookup"><span data-stu-id="efe41-106">Requirements</span></span>|  
|---------------------------------|------------------|  
|<span data-ttu-id="efe41-107">Aggiornamento immediato</span><span class="sxs-lookup"><span data-stu-id="efe41-107">Immediate Updating</span></span>|<span data-ttu-id="efe41-108">Per aggiornare i dati nel Sottoscrittore è necessario che il server di pubblicazione e il Sottoscrittore siano connessi.</span><span class="sxs-lookup"><span data-stu-id="efe41-108">Publisher and Subscriber must be connected to update data at the Subscriber.</span></span>|  
|<span data-ttu-id="efe41-109">Aggiornamento in coda</span><span class="sxs-lookup"><span data-stu-id="efe41-109">Queued Updating</span></span>|<span data-ttu-id="efe41-110">Per aggiornare i dati nel Sottoscrittore non è necessario che il server di pubblicazione e il Sottoscrittore siano connessi.</span><span class="sxs-lookup"><span data-stu-id="efe41-110">Publisher and Subscriber do not have to be connected to update data at the Subscriber.</span></span> <span data-ttu-id="efe41-111">È possibile eseguire gli aggiornamenti in modalità offline ed eseguire in seguito la sincronizzazione tra il server di pubblicazione e il Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="efe41-111">Updates can be made while offline, and later synchronized between the Publisher and Subscriber.</span></span>|  
  
## <a name="options"></a><span data-ttu-id="efe41-112">Opzioni</span><span class="sxs-lookup"><span data-stu-id="efe41-112">Options</span></span>  
 <span data-ttu-id="efe41-113">**Replica modifiche del Sottoscrittore**</span><span class="sxs-lookup"><span data-stu-id="efe41-113">**Replicate Subscriber changes**</span></span>  
 <span data-ttu-id="efe41-114">Selezionare questa casella di controllo nella colonna **Replica** per ogni Sottoscrittore che deve essere in grado di eseguire aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="efe41-114">Select the check box in the **Replicate** column for each Subscriber that should be able to make updates.</span></span> <span data-ttu-id="efe41-115">Per i Sottoscrittori che possono eseguire aggiornamenti, selezionare l'opzione appropriata nell'elenco a discesa della colonna **Commit nel server di pubblicazione** :</span><span class="sxs-lookup"><span data-stu-id="efe41-115">For those Subscribers that can make updates, select the appropriate option from the drop-down list box in the **Commit at Publisher** column:</span></span>  
  
-   <span data-ttu-id="efe41-116">Selezionare **Commit delle modifiche simultaneo** per una sottoscrizione ad aggiornamento immediato.</span><span class="sxs-lookup"><span data-stu-id="efe41-116">Select **Simultaneously commit changes** for an immediate updating subscription.</span></span>  
  
-   <span data-ttu-id="efe41-117">Selezionare **Accoda le modifiche ed esegui il commit appena possibile** per una sottoscrizione ad aggiornamento in coda.</span><span class="sxs-lookup"><span data-stu-id="efe41-117">Select **Queue changes and commit when possible** for a queued updating subscription.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efe41-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="efe41-118">See Also</span></span>  
 <span data-ttu-id="efe41-119">[Create a Pull Subscription](create-a-pull-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="efe41-119">[Create a Pull Subscription](create-a-pull-subscription.md) </span></span>  
 <span data-ttu-id="efe41-120">[Create a Push Subscription](create-a-push-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="efe41-120">[Create a Push Subscription](create-a-push-subscription.md) </span></span>  
 <span data-ttu-id="efe41-121">[Subscribe to Publications](subscribe-to-publications.md) </span><span class="sxs-lookup"><span data-stu-id="efe41-121">[Subscribe to Publications](subscribe-to-publications.md) </span></span>  
 [<span data-ttu-id="efe41-122">Updatable Subscriptions for Transactional Replication</span><span class="sxs-lookup"><span data-stu-id="efe41-122">Updatable Subscriptions for Transactional Replication</span></span>](transactional/updatable-subscriptions-for-transactional-replication.md)  
  
  
