---
title: MSSQLSERVER_32044 | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 32044 (Database Engine error)
ms.assetid: f2d073be-d9a1-4837-8a38-028d3e3403bd
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 27d9655c3a908f1302f048c6f68159d4f610367a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627779"
---
# <a name="mssqlserver_32044"></a><span data-ttu-id="67291-102">MSSQLSERVER_32044</span><span class="sxs-lookup"><span data-stu-id="67291-102">MSSQLSERVER_32044</span></span>
    
## <a name="details"></a><span data-ttu-id="67291-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="67291-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="67291-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="67291-104">Product Name</span></span>|<span data-ttu-id="67291-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="67291-105">SQL Server</span></span>|  
|<span data-ttu-id="67291-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="67291-106">Event ID</span></span>|<span data-ttu-id="67291-107">32044</span><span class="sxs-lookup"><span data-stu-id="67291-107">32044</span></span>|  
|<span data-ttu-id="67291-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="67291-108">Event Source</span></span>|<span data-ttu-id="67291-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="67291-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="67291-110">Componente</span><span class="sxs-lookup"><span data-stu-id="67291-110">Component</span></span>|<span data-ttu-id="67291-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="67291-111">SQLEngine</span></span>|  
|<span data-ttu-id="67291-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="67291-112">Symbolic Name</span></span>|<span data-ttu-id="67291-113">SQLErrorNum32044</span><span class="sxs-lookup"><span data-stu-id="67291-113">SQLErrorNum32044</span></span>|  
|<span data-ttu-id="67291-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="67291-114">Message Text</span></span>|<span data-ttu-id="67291-115">Generato avviso relativo a un overhead di commit del mirror.</span><span class="sxs-lookup"><span data-stu-id="67291-115">The alert for 'mirror commit overhead' has been raised.</span></span> <span data-ttu-id="67291-116">Il valore corrente di '%d' è maggiore della soglia '%d'.</span><span class="sxs-lookup"><span data-stu-id="67291-116">The current value of '%d' surpasses the threshold '%d'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="67291-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="67291-117">Explanation</span></span>  
 <span data-ttu-id="67291-118">Questo evento di mirroring del database viene generato nell'istanza del server principale per indicare che il tempo di attesa del commit di aggregazione ha raggiunto o superato un valore soglia specificato dall'utente a causa del mirroring del database.</span><span class="sxs-lookup"><span data-stu-id="67291-118">This database mirroring event is issued on the principal server instance to indicate that the aggregate commit wait time reached or exceeded a user-specified threshold value because of database mirroring.</span></span> <span data-ttu-id="67291-119">L'intervallo di attesa viene ottenuto moltiplicando il numero di transazioni per la durata di ogni transazione.</span><span class="sxs-lookup"><span data-stu-id="67291-119">The wait time is the product of the number of transactions and the time of each.</span></span> <span data-ttu-id="67291-120">Ad esempio i casi seguenti richiedono entrambi 1000 millisecondi di tempo di attesa: 1000 transazioni \* 1 millisecondo e 1 transazione \* 1000 millisecondi.</span><span class="sxs-lookup"><span data-stu-id="67291-120">For example, the following cases both produce 1000 milliseconds of wait time: 1000 transactions \* 1 millisecond, and 1 transaction \* 1000 milliseconds.</span></span> <span data-ttu-id="67291-121">L'aumento del tempo di attesa del commit può dipendere da un picco nel numero di transazioni, da ritardi nell'invio del log o da ritardi nello scaricamento del log nell'istanza del server mirror.</span><span class="sxs-lookup"><span data-stu-id="67291-121">An increased commit wait time can be caused by a surge in the transaction count, delays in sending the log, or delays in flushing the log on the mirror server instance.</span></span>  
  
 <span data-ttu-id="67291-122">La quantità dell'overhead di commit del mirror è una metrica delle prestazioni che consente di valutare l'impatto sulle prestazioni correnti del funzionamento sincrono.</span><span class="sxs-lookup"><span data-stu-id="67291-122">The amount of mirror commit overhead is a performance metric that can help you evaluate the current performance impact of synchronous operation.</span></span> <span data-ttu-id="67291-123">Questa metrica è rilevante solo nella modalità a sicurezza elevata.</span><span class="sxs-lookup"><span data-stu-id="67291-123">This metric is relevant only in high-safety mode.</span></span> <span data-ttu-id="67291-124">Poiché la modalità a sicurezza elevata è sincrona, prima di eseguire il commit della transazione dopo aver inviato un record di log all'istanza del server mirror, l'istanza del server principale attende la conferma della scrittura del record di log sul disco.</span><span class="sxs-lookup"><span data-stu-id="67291-124">Because high-safety mode is synchronous, the principal server instance waits to commit the transaction after it sends a log record to the mirror server instance until it receives confirmation that the mirror server instance has written the log record to disk.</span></span> <span data-ttu-id="67291-125">Il record di log rimane sul disco dell'istanza del server mirror in attesa di essere ripristinato nel database mirror.</span><span class="sxs-lookup"><span data-stu-id="67291-125">The log record remains on disk on the mirror server instance while it waits to be restored to the mirror database.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="67291-126">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="67291-126">User Action</span></span>  
 <span data-ttu-id="67291-127">Controllare il carico delle istanze del server principale e del server mirror e la connessione di rete tra i sistemi per determinare la causa del problema.</span><span class="sxs-lookup"><span data-stu-id="67291-127">Check the loads on the principal and mirror server instances and their network connection for the cause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67291-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="67291-128">See Also</span></span>  
 <span data-ttu-id="67291-129">[Mirroring del database &#40;SQL Server&#41;](../../database-engine/database-mirroring/database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="67291-129">[Database Mirroring &#40;SQL Server&#41;](../../database-engine/database-mirroring/database-mirroring-sql-server.md) </span></span>  
 [<span data-ttu-id="67291-130">Usare valori di soglia avvisi e avvisi sulle metriche delle prestazioni di mirroring &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="67291-130">Use Warning Thresholds and Alerts on Mirroring Performance Metrics &#40;SQL Server&#41;</span></span>](../../database-engine/database-mirroring/use-warning-thresholds-and-alerts-on-mirroring-performance-metrics-sql-server.md)  
  
  
