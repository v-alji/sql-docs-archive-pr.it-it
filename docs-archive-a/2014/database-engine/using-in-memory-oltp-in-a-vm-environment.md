---
title: Uso di OLTP in memoria in un ambiente di macchina virtuale | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 27ec7eb3-3a24-41db-aa65-2f206514c6f9
author: stevestein
ms.author: sstein
ms.openlocfilehash: 83cf785fbcd2df9449d61e328e3bf8e374a6656d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715687"
---
# <a name="using-in-memory-oltp-in-a-vm-environment"></a><span data-ttu-id="62249-102">Uso di OLTP in memoria in un ambiente di VM</span><span class="sxs-lookup"><span data-stu-id="62249-102">Using In-Memory OLTP in a VM Environment</span></span>
  <span data-ttu-id="62249-103">La virtualizzazione del server può aiutare a ridurre i costi operativi e il capitale IT aumentandone l'efficienza grazie a provisioning di applicazioni, manutenzione, disponibilità e processi di backup/recupero migliorati.</span><span class="sxs-lookup"><span data-stu-id="62249-103">Server virtualization can help you lower IT capital and operational costs and attain greater IT efficiency with improved application provisioning, maintenance, availability, and backup/recovery processes.</span></span> <span data-ttu-id="62249-104">Grazie ai recenti progressi tecnologici, ora è possibile consolidare più rapidamente complessi carichi di lavoro del database utilizzando la virtualizzazione.</span><span class="sxs-lookup"><span data-stu-id="62249-104">With recent technological advances, complex database workloads can be more readily consolidated using virtualization.</span></span> <span data-ttu-id="62249-105">Questo argomento illustra le procedure consigliate per l'uso di [!INCLUDE[hek_1](../includes/hek-1-md.md)] in un ambiente virtualizzato.</span><span class="sxs-lookup"><span data-stu-id="62249-105">This topic covers best practices for using [!INCLUDE[hek_1](../includes/hek-1-md.md)] in a virtualized environment.</span></span>  
  
##  <a name="memory-pre-allocation"></a><a name="bkmk_memoryPreAllocation"></a><span data-ttu-id="62249-106">Pre-allocazione della memoria</span><span class="sxs-lookup"><span data-stu-id="62249-106">Memory pre-allocation</span></span>  
 <span data-ttu-id="62249-107">Per la memoria in un ambiente virtualizzato, prestazioni e supporto migliorati sono fattori molto importanti.</span><span class="sxs-lookup"><span data-stu-id="62249-107">For memory in a virtualized environment, better performance and enhanced support are essential considerations.</span></span> <span data-ttu-id="62249-108">È necessario essere in grado di allocare rapidamente la memoria alle macchine virtuali a seconda dei requisiti e dei carichi di lavoro nonché di fare in modo che non ci siano sprechi di memoria.</span><span class="sxs-lookup"><span data-stu-id="62249-108">You must be able to both quickly allocate memory to virtual machines depending on their requirements (peak and off-peak loads) and ensure that the memory is not wasted.</span></span> <span data-ttu-id="62249-109">La funzionalità di memoria dinamica di Hyper-V migliora la flessibilità nell'allocazione e gestione della memoria tra le macchine virtuali in esecuzione in un host.</span><span class="sxs-lookup"><span data-stu-id="62249-109">The Hyper-V Dynamic Memory feature increases agility in how the memory is allocated and managed between virtual machines running on a host.</span></span>  
  
 <span data-ttu-id="62249-110">Quando si esegue la virtualizzazione di un database con tabelle ottimizzate per la memoria è necessario modificare alcune procedure consigliate per la virtualizzazione e la gestione di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="62249-110">Some best practices for virtualizing and managing [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] need to be modified when virtualizing a database with memory-optimized tables.</span></span> <span data-ttu-id="62249-111">Senza tabelle ottimizzate per la memoria, due delle procedure consigliate sono:</span><span class="sxs-lookup"><span data-stu-id="62249-111">Without memory-optimized tables, two of the best practices are:</span></span>  
  
-   <span data-ttu-id="62249-112">Se si usa MIN_SERVER_MEMORY, è consigliabile assegnare solo la quantità di memoria necessaria in modo che rimanga memoria sufficiente per altri processi (evitando quindi il paging).</span><span class="sxs-lookup"><span data-stu-id="62249-112">If you use MIN_SERVER_MEMORY, it is better to assign only the amount of memory that is required so sufficient memory remains for other processes (thereby avoiding paging).</span></span>  
  
-   <span data-ttu-id="62249-113">Non impostare un valore di preallocazione della memoria troppo elevato.</span><span class="sxs-lookup"><span data-stu-id="62249-113">Do not set the memory pre-allocation value too high.</span></span> <span data-ttu-id="62249-114">In caso contrario, è possibile che non ci sia memoria sufficiente per altri processi che la richiedono, con conseguente paging della memoria.</span><span class="sxs-lookup"><span data-stu-id="62249-114">Otherwise, other processes may not get sufficient memory at the time when they require it, and this can result in memory paging.</span></span>  
  
 <span data-ttu-id="62249-115">Se si seguono le procedure sopra indicate per un database con tabelle ottimizzate per la memoria, un tentativo di ripristinare e recuperare il database potrebbe determinare lo stato di "Recupero in sospeso" anche se la quantità di memoria disponibile è sufficiente per il recupero del database.</span><span class="sxs-lookup"><span data-stu-id="62249-115">If you follow the above practices for a database with memory-optimized tables, an attempt to restore and recover a database could result in the database being in a "Recovery Pending" state, even if you have sufficient memory to recover the database.</span></span> <span data-ttu-id="62249-116">Il motivo è che all'avvio di [!INCLUDE[hek_2](../includes/hek-2-md.md)] i dati vengono inseriti nella memoria in maniera più drastica rispetto all'allocazione della memoria al database da parte dell'allocazione dinamica della memoria.</span><span class="sxs-lookup"><span data-stu-id="62249-116">The reason for this is that, when starting up, [!INCLUDE[hek_2](../includes/hek-2-md.md)] brings data into memory more aggressively than dynamic memory allocation allocates memory to the database.</span></span>  
  
 <span data-ttu-id="62249-117">**Risoluzione**</span><span class="sxs-lookup"><span data-stu-id="62249-117">**Resolution**</span></span>  
  
 <span data-ttu-id="62249-118">Per risolvere questo problema, preallocare al database una quantità di memoria sufficiente per il recupero o il riavvio del database, anziché un valore minimo che si basa sulla memoria dinamica per ottenere memoria aggiuntiva se necessario.</span><span class="sxs-lookup"><span data-stu-id="62249-118">To mitigate this, pre-allocate sufficient memory to the database to recover or restart the database, not a minimum value relying on dynamic memory to provide the additional memory when needed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62249-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="62249-119">See Also</span></span>  
 [<span data-ttu-id="62249-120">OLTP in memoria &#40;ottimizzazione per la memoria&#41;</span><span class="sxs-lookup"><span data-stu-id="62249-120">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../relational-databases/in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
