---
title: MSSQLSERVER_32040 | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 32040 (Database Engine error)
ms.assetid: 709219b1-f8b2-4696-8923-dd2e91492eb8
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 05692e2f20b0719c1ca8f48282c3b7aaed8e2341
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627781"
---
# <a name="mssqlserver_32040"></a><span data-ttu-id="2d50e-102">MSSQLSERVER_32040</span><span class="sxs-lookup"><span data-stu-id="2d50e-102">MSSQLSERVER_32040</span></span>
    
## <a name="details"></a><span data-ttu-id="2d50e-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="2d50e-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2d50e-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="2d50e-104">Product Name</span></span>|<span data-ttu-id="2d50e-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="2d50e-105">SQL Server</span></span>|  
|<span data-ttu-id="2d50e-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="2d50e-106">Event ID</span></span>|<span data-ttu-id="2d50e-107">32040</span><span class="sxs-lookup"><span data-stu-id="2d50e-107">32040</span></span>|  
|<span data-ttu-id="2d50e-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="2d50e-108">Event Source</span></span>|<span data-ttu-id="2d50e-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="2d50e-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="2d50e-110">Componente</span><span class="sxs-lookup"><span data-stu-id="2d50e-110">Component</span></span>|<span data-ttu-id="2d50e-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="2d50e-111">SQLEngine</span></span>|  
|<span data-ttu-id="2d50e-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="2d50e-112">Symbolic Name</span></span>|<span data-ttu-id="2d50e-113">SQLErrorNum32040</span><span class="sxs-lookup"><span data-stu-id="2d50e-113">SQLErrorNum32040</span></span>|  
|<span data-ttu-id="2d50e-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="2d50e-114">Message Text</span></span>|<span data-ttu-id="2d50e-115">Generato avviso relativo alla transazione non inviata meno recente.</span><span class="sxs-lookup"><span data-stu-id="2d50e-115">The alert for 'oldest unsent transaction' has been raised.</span></span> <span data-ttu-id="2d50e-116">Il valore corrente di '%d' è maggiore della soglia '%d'.</span><span class="sxs-lookup"><span data-stu-id="2d50e-116">The current value of '%d' surpasses the threshold '%d'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="2d50e-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="2d50e-117">Explanation</span></span>  
 <span data-ttu-id="2d50e-118">Questo evento di mirroring del database viene generato nell'istanza del server principale per indicare che il tempo di memorizzazione della transazione non inviata meno recente ha raggiunto un valore soglia specificato dall'utente.</span><span class="sxs-lookup"><span data-stu-id="2d50e-118">This database mirroring event is issued on the principal server instance to indicate that the age of the oldest unsent transaction has reached a user-specified threshold value.</span></span> <span data-ttu-id="2d50e-119">In genere questo evento viene generato a causa di un cambiamento delle prestazioni del sistema.</span><span class="sxs-lookup"><span data-stu-id="2d50e-119">Typically, this event occurs because the performance of the system has changed.</span></span> <span data-ttu-id="2d50e-120">La larghezza di banda disponibile tra i due sistemi è diminuita o il carico è aumentato.</span><span class="sxs-lookup"><span data-stu-id="2d50e-120">Either the bandwidth between the two systems has decreased, or the load has increased.</span></span>  
  
 <span data-ttu-id="2d50e-121">Il tempo di memorizzazione della transazione non inviata meno recente è una misurazione delle prestazioni che consente di valutare possibili perdite di dati misurate in base al numero di minuti corrispondenti alle transazioni non inviate.</span><span class="sxs-lookup"><span data-stu-id="2d50e-121">The age of the oldest unsent transaction is a performance metric that can help you evaluate the potential for data loss as measured by the number of minutes of unsent transactions.</span></span> <span data-ttu-id="2d50e-122">Questa misurazione è particolarmente rilevante per le sessioni in modalità a prestazioni elevate.</span><span class="sxs-lookup"><span data-stu-id="2d50e-122">This metric is especially relevant for high-performance mode sessions.</span></span> <span data-ttu-id="2d50e-123">Questa misurazione è inoltre utile come sessione in modalità a sicurezza elevata quando il mirroring viene sospeso in seguito alla disconnessione dei partner.</span><span class="sxs-lookup"><span data-stu-id="2d50e-123">However, this metric is also relevant for high-safety mode session when mirroring is paused or suspended because the partners become disconnected.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2d50e-124">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="2d50e-124">User Action</span></span>  
 <span data-ttu-id="2d50e-125">Controllare il carico delle istanze del server principale e del server mirror e la connessione di rete tra i sistemi per determinare la causa del problema.</span><span class="sxs-lookup"><span data-stu-id="2d50e-125">Check the loads on the principal and mirror server instances and their network connection for the cause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d50e-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2d50e-126">See Also</span></span>  
 <span data-ttu-id="2d50e-127">[Mirroring del database &#40;SQL Server&#41;](../../database-engine/database-mirroring/database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="2d50e-127">[Database Mirroring &#40;SQL Server&#41;](../../database-engine/database-mirroring/database-mirroring-sql-server.md) </span></span>  
 [<span data-ttu-id="2d50e-128">Usare valori di soglia avvisi e avvisi sulle metriche delle prestazioni di mirroring &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="2d50e-128">Use Warning Thresholds and Alerts on Mirroring Performance Metrics &#40;SQL Server&#41;</span></span>](../../database-engine/database-mirroring/use-warning-thresholds-and-alerts-on-mirroring-performance-metrics-sql-server.md)  
  
  
