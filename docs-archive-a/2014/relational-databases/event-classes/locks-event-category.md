---
title: Categoria di eventi Blocchi| Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- Locks event category [SQL Server]
- SQL Server event classes, Locks event category
- event classes [SQL Server], Locks event category
- lock escalation [SQL Server], locks event category
ms.assetid: 27d6afa2-7dab-4fe7-a1ad-064b879dc654
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3a202279021e3e6c7c3c44a167792bb9439567aa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625401"
---
# <a name="locks-event-category"></a><span data-ttu-id="abcee-102">Categoria di eventi Blocchi</span><span class="sxs-lookup"><span data-stu-id="abcee-102">Locks Event Category</span></span>
  <span data-ttu-id="abcee-103">Usare le classi di evento della categoria di eventi **Locks** per monitorare l'attività di blocco in un'istanza del [!INCLUDE[msCoName](../../includes/msconame-md.md)] di [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="abcee-103">Use the event classes in the **Locks** event category to monitor locking activity in an instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span> <span data-ttu-id="abcee-104">Queste classi di evento possono contribuire a esaminare problemi di blocco provocati dalla lettura e modifica dei dati da parte di più utenti simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="abcee-104">These event classes can help you investigate locking problems caused by multiple users reading and modifying data concurrently.</span></span>  
  
 <span data-ttu-id="abcee-105">Poiché nel [!INCLUDE[ssDE](../../includes/ssde-md.md)] vengono spesso elaborati più blocchi, l'acquisizione delle classi di evento **Locks** durante una traccia può provocare un overhead significativo e comportare la creazione di file o tabelle di traccia di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="abcee-105">Because the [!INCLUDE[ssDE](../../includes/ssde-md.md)] often processes many locks, capturing the **Locks** event classes during a trace can incur significant overhead and result in large trace files or tables.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="abcee-106">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="abcee-106">In This Section</span></span>  
  
|<span data-ttu-id="abcee-107">Argomento</span><span class="sxs-lookup"><span data-stu-id="abcee-107">Topic</span></span>|<span data-ttu-id="abcee-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="abcee-108">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="abcee-109">Classe di evento Deadlock Graph</span><span class="sxs-lookup"><span data-stu-id="abcee-109">Deadlock Graph Event Class</span></span>](deadlock-graph-event-class.md)|<span data-ttu-id="abcee-110">Include una descrizione XML di un deadlock.</span><span class="sxs-lookup"><span data-stu-id="abcee-110">Provides an XML description of a deadlock.</span></span>|  
|[<span data-ttu-id="abcee-111">Classe Lock:Acquired Event</span><span class="sxs-lookup"><span data-stu-id="abcee-111">Lock:Acquired Event Class</span></span>](lock-acquired-event-class.md)|<span data-ttu-id="abcee-112">Indica l'acquisizione di un blocco su una risorsa, ad esempio una riga in una tabella.</span><span class="sxs-lookup"><span data-stu-id="abcee-112">Indicates that a lock has been acquired on a resource, such as a row in a table.</span></span>|  
|[<span data-ttu-id="abcee-113">Classe di evento Lock:Cancel</span><span class="sxs-lookup"><span data-stu-id="abcee-113">Lock:Cancel Event Class</span></span>](lock-cancel-event-class.md)|<span data-ttu-id="abcee-114">Tiene traccia delle richieste di blocchi annullate prima dell'acquisizione del blocco, ad esempio per evitare un deadlock.</span><span class="sxs-lookup"><span data-stu-id="abcee-114">Tracks requests for locks that were canceled before the lock was acquired (for example, to prevent a deadlock).</span></span>|  
|[<span data-ttu-id="abcee-115">Classe di evento Lock:Deadlock Chain</span><span class="sxs-lookup"><span data-stu-id="abcee-115">Lock:Deadlock Chain Event Class</span></span>](lock-deadlock-chain-event-class.md)|<span data-ttu-id="abcee-116">Esegue il monitoraggio di condizioni di deadlock e degli oggetti coinvolti.</span><span class="sxs-lookup"><span data-stu-id="abcee-116">Monitors when deadlock conditions occur and which objects are involved.</span></span>|  
|[<span data-ttu-id="abcee-117">Classe di evento Lock:Deadlock</span><span class="sxs-lookup"><span data-stu-id="abcee-117">Lock:Deadlock Event Class</span></span>](lock-deadlock-event-class.md)|<span data-ttu-id="abcee-118">Tiene traccia di una richiesta di blocco da parte di una transazione su una risorsa già bloccata da un'altra transazione e del deadlock risultante.</span><span class="sxs-lookup"><span data-stu-id="abcee-118">Tracks when a transaction has requested a lock on a resource already locked by another transaction, resulting in a deadlock.</span></span>|  
|[<span data-ttu-id="abcee-119">Classe di evento Lock:Escalation</span><span class="sxs-lookup"><span data-stu-id="abcee-119">Lock:Escalation Event Class</span></span>](lock-escalation-event-class.md)|<span data-ttu-id="abcee-120">Indica la conversione di un blocco con granularità fine in un blocco con granularità grossolana.</span><span class="sxs-lookup"><span data-stu-id="abcee-120">Indicates that a finer-grained lock has been converted to a coarser-grained lock.</span></span>|  
|[<span data-ttu-id="abcee-121">Classe di evento Lock:Released</span><span class="sxs-lookup"><span data-stu-id="abcee-121">Lock:Released Event Class</span></span>](lock-released-event-class.md)|<span data-ttu-id="abcee-122">Tiene traccia del rilascio di un blocco.</span><span class="sxs-lookup"><span data-stu-id="abcee-122">Tracks when a lock is released.</span></span>|  
|[<span data-ttu-id="abcee-123">Lock:Timeout &#40;timeout &#62; 0&#41; Event Class</span><span class="sxs-lookup"><span data-stu-id="abcee-123">Lock:Timeout &#40;timeout &#62; 0&#41; Event Class</span></span>](lock-timeout-timeout-0-event-class.md)|<span data-ttu-id="abcee-124">Tiene traccia dell'impossibilità di completare richieste di blocco a causa del blocco della risorsa richiesta da parte di un'altra transazione.</span><span class="sxs-lookup"><span data-stu-id="abcee-124">Tracks when lock requests cannot be completed because another transaction has a blocking lock on the requested resource.</span></span> <span data-ttu-id="abcee-125">Questo evento viene generato solo nei casi in cui il valore specificato per il timeout del blocco è superiore a zero.</span><span class="sxs-lookup"><span data-stu-id="abcee-125">This event occurs only in situations where the lock time-out value is greater than zero.</span></span>|  
|[<span data-ttu-id="abcee-126">Classe di evento Lock:Timeout</span><span class="sxs-lookup"><span data-stu-id="abcee-126">Lock:Timeout Event Class</span></span>](lock-timeout-event-class.md)|<span data-ttu-id="abcee-127">Tiene traccia dell'impossibilità di completare richieste di blocco a causa del blocco della risorsa richiesta da parte di un'altra transazione.</span><span class="sxs-lookup"><span data-stu-id="abcee-127">Tracks when lock requests cannot be completed because another transaction has a blocking lock on the requested resource.</span></span>|  
  
  
