---
title: MSSQLSERVER_32042 | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 32042 (Database Engine error)
ms.assetid: 53a51c7a-dcd4-4c15-b4d2-6aaa9dce76da
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: bd959d84da2c54310dea5156b1a45b73490211a3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627780"
---
# <a name="mssqlserver_32042"></a><span data-ttu-id="e8f99-102">MSSQLSERVER_32042</span><span class="sxs-lookup"><span data-stu-id="e8f99-102">MSSQLSERVER_32042</span></span>
    
## <a name="details"></a><span data-ttu-id="e8f99-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="e8f99-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e8f99-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="e8f99-104">Product Name</span></span>|<span data-ttu-id="e8f99-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="e8f99-105">SQL Server</span></span>|  
|<span data-ttu-id="e8f99-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="e8f99-106">Event ID</span></span>|<span data-ttu-id="e8f99-107">32042</span><span class="sxs-lookup"><span data-stu-id="e8f99-107">32042</span></span>|  
|<span data-ttu-id="e8f99-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="e8f99-108">Event Source</span></span>|<span data-ttu-id="e8f99-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="e8f99-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="e8f99-110">Componente</span><span class="sxs-lookup"><span data-stu-id="e8f99-110">Component</span></span>|<span data-ttu-id="e8f99-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="e8f99-111">SQLEngine</span></span>|  
|<span data-ttu-id="e8f99-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="e8f99-112">Symbolic Name</span></span>|<span data-ttu-id="e8f99-113">SQLErrorNum32042</span><span class="sxs-lookup"><span data-stu-id="e8f99-113">SQLErrorNum32042</span></span>|  
|<span data-ttu-id="e8f99-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="e8f99-114">Message Text</span></span>|<span data-ttu-id="e8f99-115">Generato avviso relativo a un log non inviato.</span><span class="sxs-lookup"><span data-stu-id="e8f99-115">The alert for 'unsent log' has been raised.</span></span> <span data-ttu-id="e8f99-116">Il valore corrente di '%d' è maggiore della soglia '%d'.</span><span class="sxs-lookup"><span data-stu-id="e8f99-116">The current value of '%d' surpasses the threshold '%d'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e8f99-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="e8f99-117">Explanation</span></span>  
 <span data-ttu-id="e8f99-118">Questo evento di mirroring del database viene generato nell'istanza del server principale per indicare che la quantità di log non inviato ha raggiunto un valore soglia specificato dall'utente.</span><span class="sxs-lookup"><span data-stu-id="e8f99-118">This database mirroring event is issued on the principal server instance to indicate that the amount of unsent log has reached a user-specified threshold value.</span></span> <span data-ttu-id="e8f99-119">In genere questo evento viene generato a causa di un cambiamento delle prestazioni del sistema.</span><span class="sxs-lookup"><span data-stu-id="e8f99-119">Typically, this event occurs because the performance of the system has changed.</span></span> <span data-ttu-id="e8f99-120">La larghezza di banda disponibile tra i due sistemi è diminuita o il carico è aumentato.</span><span class="sxs-lookup"><span data-stu-id="e8f99-120">Either the bandwidth between the two systems has decreased, or the load has increased.</span></span>  
  
 <span data-ttu-id="e8f99-121">La quantità di log non inviato è una misurazione delle prestazioni che consente di valutare possibili perdite di dati in termini di numero di KB di log non inviato.</span><span class="sxs-lookup"><span data-stu-id="e8f99-121">The amount of unsent log is a performance metric that can help you evaluate the potential for data loss in terms of the number of kilobytes (KB) of unsent log.</span></span> <span data-ttu-id="e8f99-122">Questa misurazione è particolarmente rilevante per le sessioni in modalità a prestazioni elevate.</span><span class="sxs-lookup"><span data-stu-id="e8f99-122">This metric is particularly relevant for high-performance mode sessions.</span></span> <span data-ttu-id="e8f99-123">Questa misurazione è inoltre utile come sessione in modalità a sicurezza elevata quando il mirroring viene sospeso in seguito alla disconnessione dei partner.</span><span class="sxs-lookup"><span data-stu-id="e8f99-123">However, this metric is also a relevant for high-safety mode session when mirroring is paused or suspended because the partners become disconnected.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e8f99-124">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="e8f99-124">User Action</span></span>  
 <span data-ttu-id="e8f99-125">Controllare il carico delle istanze del server principale e del server mirror e la connessione di rete tra i sistemi per determinare la causa del problema.</span><span class="sxs-lookup"><span data-stu-id="e8f99-125">Check the loads on the principal and mirror server instances and their network connection for the cause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8f99-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e8f99-126">See Also</span></span>  
 <span data-ttu-id="e8f99-127">[Mirroring del database &#40;SQL Server&#41;](../../database-engine/database-mirroring/database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="e8f99-127">[Database Mirroring &#40;SQL Server&#41;](../../database-engine/database-mirroring/database-mirroring-sql-server.md) </span></span>  
 [<span data-ttu-id="e8f99-128">Usare valori di soglia avvisi e avvisi sulle metriche delle prestazioni di mirroring &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e8f99-128">Use Warning Thresholds and Alerts on Mirroring Performance Metrics &#40;SQL Server&#41;</span></span>](../../database-engine/database-mirroring/use-warning-thresholds-and-alerts-on-mirroring-performance-metrics-sql-server.md)  
  
  
