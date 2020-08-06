---
title: Ottimizzare le prestazioni della replica di tipo merge con il rilevamento condizionale delle eliminazioni | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- conditional delete tracking [SQL Server replication]
- merge replication [SQL Server replication], conditional delete tracking
- articles [SQL Server replication], conditional delete tracking
ms.assetid: 58f120a3-ea3a-4e97-93f0-0eb4e580ecf2
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 46fc189d2a2e0ebf5ea44775585a69d52783a7e3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623192"
---
# <a name="optimize-merge-replication-performance-with-conditional-delete-tracking"></a><span data-ttu-id="09fb5-102">Ottimizzazione delle prestazioni della replica di tipo merge con il rilevamento condizionale delle eliminazioni</span><span class="sxs-lookup"><span data-stu-id="09fb5-102">Optimize Merge Replication Performance with Conditional Delete Tracking</span></span>
    
> [!NOTE]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../../includes/ssnotedepfutureavoid-md.md)]  
  
 <span data-ttu-id="09fb5-103">Con la replica di tipo merge è possibile specificare che le eliminazioni per uno o più articoli non devono essere rilevate dai trigger di replica e dalle tabelle di sistema.</span><span class="sxs-lookup"><span data-stu-id="09fb5-103">With merge replication you can specify that deletes for one or more articles should not be tracked by replication triggers and system tables.</span></span> <span data-ttu-id="09fb5-104">Se si specifica questa opzione per un articolo, le eliminazioni non vengono rilevate o replicate dal server di pubblicazione o da qualsiasi Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="09fb5-104">If you specify this option for an article, deletes are not tracked or replicated from the Publisher or any Subscribers.</span></span> <span data-ttu-id="09fb5-105">Questa opzione è disponibile per il supporto di numerosi scenari applicativi e per offrire l'ottimizzazione delle prestazioni, nei casi in cui la replica delle eliminazioni non è necessaria o desiderata.</span><span class="sxs-lookup"><span data-stu-id="09fb5-105">This option is available to support a number of application scenarios and to provide a performance optimization for cases in which the replication of deletes is not necessary or desirable.</span></span> <span data-ttu-id="09fb5-106">Il miglioramento delle prestazioni avviene per tre motivi: non vengono archiviati i metadati delle eliminazioni, le eliminazioni non vengono enumerate durante la sincronizzazione e, infine, non vengono replicate nel Sottoscrittore e applicate allo stesso.</span><span class="sxs-lookup"><span data-stu-id="09fb5-106">Performance is enhanced in three ways: metadata for deletes is not stored; deletes are not enumerated during synchronization; deletes are not replicated to and applied at the Subscriber.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="09fb5-107">Per utilizzare questo tipo di articoli è necessario che il livello di compatibilità della pubblicazione sia impostato almeno su 90RTM.</span><span class="sxs-lookup"><span data-stu-id="09fb5-107">To use download-only articles, the compatibility level of the publication must be at least 90RTM.</span></span>  
  
 <span data-ttu-id="09fb5-108">Questa opzione può essere specificata alla creazione della pubblicazione oppure attivata e disattivata se un'applicazione richiede la replica di alcune eliminazioni e non di altre, ad esempio eliminazioni batch.</span><span class="sxs-lookup"><span data-stu-id="09fb5-108">The option can be specified when a publication is created or it can be toggled on and off if an application requires that some deletes be replicated and that others not be replicated, such as batch deletes.</span></span> <span data-ttu-id="09fb5-109">Gli esempi seguenti illustrano le modalità di utilizzo di questa opzione in un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="09fb5-109">The following examples illustrate ways in which this option might be used in an application:</span></span>  
  
-   <span data-ttu-id="09fb5-110">Un'applicazione per la forza vendita mobile in genere contiene tabelle come **SalesOrderHeader**, **SalesOrderDetail** e **Product**.</span><span class="sxs-lookup"><span data-stu-id="09fb5-110">An application for a mobile sales force typically has tables such as **SalesOrderHeader**, **SalesOrderDetail** and **Product**.</span></span> <span data-ttu-id="09fb5-111">Gli ordini vengono immessi nel Sottoscrittore e poi replicati nel server di pubblicazione, che spesso assicura i dati a un sistema di evasione degli ordini.</span><span class="sxs-lookup"><span data-stu-id="09fb5-111">Orders are entered at the Subscriber and then replicated to the Publisher, which often supplies data to an order fulfillment system.</span></span> <span data-ttu-id="09fb5-112">Molti lavoratori mobili utilizzano dispositivi palmari che hanno una capacità di archiviazione limitata: quando l'ordine viene ricevuto nel server di pubblicazione, può essere eliminato nel Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="09fb5-112">Many mobile workers use handheld devices which have limited storage: after the order is received at the Publisher, it can be deleted at the Subscriber.</span></span> <span data-ttu-id="09fb5-113">L'eliminazione non viene propagata al server di pubblicazione, perché l'ordine è ancora attivo nel sistema.</span><span class="sxs-lookup"><span data-stu-id="09fb5-113">The delete is not propagated to the Publisher, because the order is still active in the system.</span></span>  
  
     <span data-ttu-id="09fb5-114">In questo scenario, le eliminazioni non verrebbero rilevate per le tabelle **SalesOrderHeader** e **SalesOrderDetail** .</span><span class="sxs-lookup"><span data-stu-id="09fb5-114">In this scenario, deletes would not be tracked for the **SalesOrderHeader** and **SalesOrderDetail** tables.</span></span> <span data-ttu-id="09fb5-115">Verrebbero invece rilevate per la tabella **Product** perché se un prodotto viene eliminato nel server di pubblicazione l'eliminazione deve essere inviata al Sottoscrittore per mantenere aggiornato l'elenco dei prodotti.</span><span class="sxs-lookup"><span data-stu-id="09fb5-115">Deletes would be tracked for the **Product** table, because if a product is deleted at the Publisher, the delete should be sent to the Subscriber to keep the product list up to date.</span></span>  
  
-   <span data-ttu-id="09fb5-116">Un'applicazione potrebbe archiviare i dati storici in una tabella come **TransactionHistory**, da cui vengono periodicamente eliminati i record più vecchi di un anno.</span><span class="sxs-lookup"><span data-stu-id="09fb5-116">An application could store historical data in a table such as **TransactionHistory**, which is periodically purged of records older than a year.</span></span> <span data-ttu-id="09fb5-117">La tabella potrebbe essere filtrata in modo che i Sottoscrittori ricevano solo i dati delle transazioni del mese corrente.</span><span class="sxs-lookup"><span data-stu-id="09fb5-117">The table could be filtered such that Subscribers only receive data on transactions within the current month.</span></span> <span data-ttu-id="09fb5-118">Le eliminazioni batch mensili del server di pubblicazione, con cui vengono eliminati i dati più vecchi, non interessano i Sottoscrittori, ma verrebbero comunque rilevate ed enumerate per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="09fb5-118">Monthly batch deletes at the Publisher that purge older data are not relevant to Subscribers, but they would still be tracked and enumerated by default.</span></span>  
  
     <span data-ttu-id="09fb5-119">In questo scenario, prima che abbia luogo l'elaborazione batch, sarebbe possibile arrestare l'attività del sistema e disabilitare il rilevamento delle eliminazioni dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="09fb5-119">In this scenario, before the batch processing occurred, activity could be stopped on the system, and the application could disable the tracking of deletes.</span></span> <span data-ttu-id="09fb5-120">Al termine dell'elaborazione, sarebbe possibile riabilitare la rilevazione.</span><span class="sxs-lookup"><span data-stu-id="09fb5-120">After the processing has finished, tracking could again be enabled.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="09fb5-121">Se nel server di pubblicazione prosegue l'attività, è necessario verificare che le eliminazioni che dovrebbero essere propagate ai Sottoscrittori non abbiano luogo mentre il rilevamento delle eliminazioni è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="09fb5-121">If other activity continues at the Publisher, you must ensure that deletes that should be propagated to Subscribers do not occur while delete tracking is disabled.</span></span>  
  
 <span data-ttu-id="09fb5-122">**Per specificare di non rilevare le eliminazioni**</span><span class="sxs-lookup"><span data-stu-id="09fb5-122">**To specify that deletes should not be tracked**</span></span>  
  
-   <span data-ttu-id="09fb5-123">Programmazione [!INCLUDE[tsql](../../../includes/tsql-md.md)] della replica: [Disattivare del rilevamento delle eliminazioni per gli articoli di merge &#40;programmazione Transact-SQL della replica&#41;](..//publish/specify-merge-replication-properties.md#tracking-deletes)</span><span class="sxs-lookup"><span data-stu-id="09fb5-123">Replication [!INCLUDE[tsql](../../../includes/tsql-md.md)] programming: [Specify That Deletes Should Not Be Tracked For Merge Articles &#40;Replication Transact-SQL Programming&#41;](..//publish/specify-merge-replication-properties.md#tracking-deletes)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09fb5-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="09fb5-124">See Also</span></span>  
 <span data-ttu-id="09fb5-125">[Opzioni degli articoli per la replica di tipo merge](article-options-for-merge-replication.md) </span><span class="sxs-lookup"><span data-stu-id="09fb5-125">[Article Options for Merge Replication](article-options-for-merge-replication.md) </span></span>  
 [<span data-ttu-id="09fb5-126">Ottimizzare le prestazioni della replica di tipo merge con gli articoli di solo download</span><span class="sxs-lookup"><span data-stu-id="09fb5-126">Optimize Merge Replication Performance with Download-Only Articles</span></span>](optimize-merge-replication-performance-with-download-only-articles.md)  
  
  
