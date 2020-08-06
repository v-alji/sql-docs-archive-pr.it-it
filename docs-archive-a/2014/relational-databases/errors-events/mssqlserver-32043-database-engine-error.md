---
title: MSSQLSERVER_32043 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 32043 (Database Engine error)
ms.assetid: a0c48ae3-4c8c-419c-afb5-579fcefac01d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2febc7173c8144451c7a9b0576f2293d5594c6df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624229"
---
# <a name="mssqlserver_32043"></a><span data-ttu-id="4ef47-102">MSSQLSERVER_32043</span><span class="sxs-lookup"><span data-stu-id="4ef47-102">MSSQLSERVER_32043</span></span>
    
## <a name="details"></a><span data-ttu-id="4ef47-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="4ef47-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4ef47-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="4ef47-104">Product Name</span></span>|<span data-ttu-id="4ef47-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="4ef47-105">SQL Server</span></span>|  
|<span data-ttu-id="4ef47-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="4ef47-106">Event ID</span></span>|<span data-ttu-id="4ef47-107">32043</span><span class="sxs-lookup"><span data-stu-id="4ef47-107">32043</span></span>|  
|<span data-ttu-id="4ef47-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="4ef47-108">Event Source</span></span>|<span data-ttu-id="4ef47-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="4ef47-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="4ef47-110">Componente</span><span class="sxs-lookup"><span data-stu-id="4ef47-110">Component</span></span>|<span data-ttu-id="4ef47-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="4ef47-111">SQLEngine</span></span>|  
|<span data-ttu-id="4ef47-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="4ef47-112">Symbolic Name</span></span>|<span data-ttu-id="4ef47-113">SQLErrorNum32043</span><span class="sxs-lookup"><span data-stu-id="4ef47-113">SQLErrorNum32043</span></span>|  
|<span data-ttu-id="4ef47-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="4ef47-114">Message Text</span></span>|<span data-ttu-id="4ef47-115">Generato avviso relativo a un log non ripristinato.</span><span class="sxs-lookup"><span data-stu-id="4ef47-115">The alert for 'unrestored log' has been raised.</span></span> <span data-ttu-id="4ef47-116">Il valore corrente di '%d' è maggiore della soglia '%d'.</span><span class="sxs-lookup"><span data-stu-id="4ef47-116">The current value of '%d' surpasses the threshold '%d'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="4ef47-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="4ef47-117">Explanation</span></span>  
 <span data-ttu-id="4ef47-118">Questo evento di mirroring del database viene generato nell'istanza del server mirror per indicare che la quantità di log non ripristinato ha raggiunto un valore soglia specificato dall'utente.</span><span class="sxs-lookup"><span data-stu-id="4ef47-118">This database mirroring event is issued on the mirror server instance to indicate that the amount of unrestored log reached a user-specified threshold value.</span></span> <span data-ttu-id="4ef47-119">In genere questo evento viene generato a causa di un cambiamento delle prestazioni del sistema.</span><span class="sxs-lookup"><span data-stu-id="4ef47-119">Typically, this event occurs because the performance of the system has changed.</span></span> <span data-ttu-id="4ef47-120">La larghezza di banda disponibile tra i due sistemi è diminuita o il carico è aumentato.</span><span class="sxs-lookup"><span data-stu-id="4ef47-120">Either the bandwidth between the two systems has decreased, or the load has increased.</span></span>  
  
 <span data-ttu-id="4ef47-121">Per log non ripristinato si intende un log ricevuto dall'istanza del server mirror e scritto su disco ma in attesa di essere ripristinato nel database mirror.</span><span class="sxs-lookup"><span data-stu-id="4ef47-121">An unrestored log is a log that has been received by the mirror server instance and written to disk but is waiting to be restored to the mirror database.</span></span> <span data-ttu-id="4ef47-122">La quantità di log non ripristinato espressa in KB corrisponde a una misurazione delle prestazioni che consente di valutare il tempo di failover corrente.</span><span class="sxs-lookup"><span data-stu-id="4ef47-122">The amount of unrestored log in kilobytes (KB) is a performance metric that can help you evaluate the current failover time.</span></span> <span data-ttu-id="4ef47-123">Il tempo necessario per l'applicazione del log non ripristinato rappresenta il fattore principale del tempo di failover, unitamente all'ulteriore tempo necessario per recuperare il database e portarlo online.</span><span class="sxs-lookup"><span data-stu-id="4ef47-123">The time that is required to apply the unrestored log is the main factor in failover time, along with a short additional time that is required to recover the database and bring it online.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4ef47-124">Per un failover automatico, il tempo necessario al sistema per rilevare l'errore è indipendente dal tempo di failover.</span><span class="sxs-lookup"><span data-stu-id="4ef47-124">For an automatic failover, the time for the system to notice the failure is independent of the failover time.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4ef47-125">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="4ef47-125">User Action</span></span>  
 <span data-ttu-id="4ef47-126">Controllare il carico delle istanze del server principale e del server mirror e la connessione di rete tra i sistemi per determinare la causa del problema.</span><span class="sxs-lookup"><span data-stu-id="4ef47-126">Check the loads on the principal and mirror server instances and their network connection for the cause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ef47-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4ef47-127">See Also</span></span>  
 <span data-ttu-id="4ef47-128">[Mirroring del database &#40;SQL Server&#41;](../../database-engine/database-mirroring/database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="4ef47-128">[Database Mirroring &#40;SQL Server&#41;](../../database-engine/database-mirroring/database-mirroring-sql-server.md) </span></span>  
 [<span data-ttu-id="4ef47-129">Usare valori di soglia avvisi e avvisi sulle metriche delle prestazioni di mirroring &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4ef47-129">Use Warning Thresholds and Alerts on Mirroring Performance Metrics &#40;SQL Server&#41;</span></span>](../../database-engine/database-mirroring/use-warning-thresholds-and-alerts-on-mirroring-performance-metrics-sql-server.md)  
  
  
