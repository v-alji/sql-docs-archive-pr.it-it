---
title: Tipi di replica | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], types
ms.assetid: c1655e8d-d14c-455a-a7f9-9d2f43e88ab4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5576331004eca44bc32dbde8f430284f75e6eb70
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717802"
---
# <a name="types-of-replication"></a><span data-ttu-id="69d9b-102">Tipi di replica</span><span class="sxs-lookup"><span data-stu-id="69d9b-102">Types of Replication</span></span>
  [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="69d9b-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] offre i tipi di replica seguenti, utilizzabili nelle applicazioni distribuite:</span><span class="sxs-lookup"><span data-stu-id="69d9b-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provides the following types of replication for use in distributed applications:</span></span>  
  
-   <span data-ttu-id="69d9b-104">Replica transazionale.</span><span class="sxs-lookup"><span data-stu-id="69d9b-104">Transactional replication.</span></span> <span data-ttu-id="69d9b-105">Per altre informazioni, vedere [Replica transazionale](transactional/transactional-replication.md).</span><span class="sxs-lookup"><span data-stu-id="69d9b-105">For more information, see [Transactional Replication](transactional/transactional-replication.md).</span></span>  
  
-   <span data-ttu-id="69d9b-106">Replica di tipo merge.</span><span class="sxs-lookup"><span data-stu-id="69d9b-106">Merge replication.</span></span> <span data-ttu-id="69d9b-107">Per altre informazioni, vedere [Replica di tipo merge](merge/merge-replication.md).</span><span class="sxs-lookup"><span data-stu-id="69d9b-107">For more information, see [Merge Replication](merge/merge-replication.md).</span></span>  
  
-   <span data-ttu-id="69d9b-108">Replica snapshot.</span><span class="sxs-lookup"><span data-stu-id="69d9b-108">Snapshot replication.</span></span> <span data-ttu-id="69d9b-109">Per altre informazioni, vedere [Replica snapshot](snapshot-replication.md).</span><span class="sxs-lookup"><span data-stu-id="69d9b-109">For more information, see [Snapshot Replication](snapshot-replication.md).</span></span>  
  
 <span data-ttu-id="69d9b-110">Il tipo di replica selezionato per un'applicazione dipende da numerosi fattori, tra cui l'ambiente fisico di replica, il tipo e la quantità di dati da replicare e l'eventuale presenza di dati aggiornati nel Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="69d9b-110">The type of replication you choose for an application depends on many factors, including the physical replication environment, the type and quantity of data to be replicated, and whether the data is updated at the Subscriber.</span></span> <span data-ttu-id="69d9b-111">L'ambiente fisico include il numero e la posizione dei computer coinvolti nella replica, nonché se si tratti di computer client (workstation, computer portatili o dispositivi palmari) o server.</span><span class="sxs-lookup"><span data-stu-id="69d9b-111">The physical environment includes the number and location of computers involved in replication and whether these computers are clients (workstations, laptops, or handheld devices) or servers.</span></span>  
  
 <span data-ttu-id="69d9b-112">Ogni tipo di replica ha in genere inizio con una sincronizzazione degli oggetti pubblicati tra server di pubblicazione e Sottoscrittori.</span><span class="sxs-lookup"><span data-stu-id="69d9b-112">Each type of replication typically begins with an initial synchronization of the published objects between the Publisher and Subscribers.</span></span> <span data-ttu-id="69d9b-113">Questa sincronizzazione iniziale può essere eseguita dalla replica con uno *snapshot*, ovvero una copia di tutti gli oggetti e i dati specificati da una pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="69d9b-113">This initial synchronization can be performed by replication with a *snapshot*, which is a copy of all of the objects and data specified by a publication.</span></span> <span data-ttu-id="69d9b-114">Dopo la creazione, lo snapshot viene recapitato ai Sottoscrittori.</span><span class="sxs-lookup"><span data-stu-id="69d9b-114">After the snapshot is created, it is delivered to the Subscribers.</span></span> <span data-ttu-id="69d9b-115">Per alcune applicazioni, è sufficiente la replica snapshot.</span><span class="sxs-lookup"><span data-stu-id="69d9b-115">For some applications, snapshot replication is all that is required.</span></span> <span data-ttu-id="69d9b-116">Per altri tipi di applicazioni, è importante che esista un flusso incrementale nel tempo delle successive modifiche di dati al Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="69d9b-116">For other types of applications, it is important that subsequent data changes flow to the Subscriber incrementally over time.</span></span> <span data-ttu-id="69d9b-117">Alcune applicazioni richiedono inoltre il flusso delle modifiche dal Sottoscrittore al server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="69d9b-117">Some applications also require that changes flow from the Subscriber back to the Publisher.</span></span> <span data-ttu-id="69d9b-118">La replica transazionale e la replica di tipo merge offrono opzioni per questi tipi di applicazioni.</span><span class="sxs-lookup"><span data-stu-id="69d9b-118">Transactional replication and merge replication provide options for these types of applications.</span></span>  
  
 <span data-ttu-id="69d9b-119">Le modifiche di dati non vengono rilevate per la replica snapshot. Ogni volta che viene applicato uno snapshot, vengono completamente sovrascritti i dati esistenti.</span><span class="sxs-lookup"><span data-stu-id="69d9b-119">Data changes are not tracked for snapshot replication; each time a snapshot is applied, it completely overwrites the existing data.</span></span> <span data-ttu-id="69d9b-120">La replica transazionale rileva le modifiche tramite il log delle transazioni di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , mentre la replica di tipo merge utilizza a tale scopo trigger e tabelle di metadati.</span><span class="sxs-lookup"><span data-stu-id="69d9b-120">Transactional replication tracks changes through the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] transaction log, and merge replication tracks changes through triggers and metadata tables.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69d9b-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="69d9b-121">See Also</span></span>  
 [<span data-ttu-id="69d9b-122">Panoramica degli agenti di replica</span><span class="sxs-lookup"><span data-stu-id="69d9b-122">Replication Agents Overview</span></span>](agents/replication-agents-overview.md)  
  
  
