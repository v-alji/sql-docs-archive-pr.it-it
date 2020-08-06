---
title: Oggetto Buffer Node di SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- SQLServer:Buffer Node
- Buffer Node object
ms.assetid: fd3f9f0f-7c38-4cfd-a0c5-ee93dd52d9a5
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 14659e4c1191e2260bccdbcd612f510770913629
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636026"
---
# <a name="sql-serverbuffer-node"></a><span data-ttu-id="8f442-102">Nodo SQLServer:Buffer</span><span class="sxs-lookup"><span data-stu-id="8f442-102">SQL Server:Buffer Node</span></span>
  <span data-ttu-id="8f442-103">L'oggetto **Buffer Node** fornisce contatori che integrano quelli inclusi nell'oggetto **Buffer Manager** .</span><span class="sxs-lookup"><span data-stu-id="8f442-103">The **Buffer Node** object provides counters that complement counters provided by the **Buffer Manager** object.</span></span> <span data-ttu-id="8f442-104">Tale oggetto consente di monitorare la distribuzione della pagina del pool di buffer di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per ogni nodo NUMA (Non-Uniform Memory Access).</span><span class="sxs-lookup"><span data-stu-id="8f442-104">It allows you to monitor the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] buffer pool page distribution for each non-uniform memory access (NUMA) node.</span></span> <span data-ttu-id="8f442-105">È disponibile un'istanza dell'oggetto **Buffer Node** per ogni nodo NUMA utilizzato.</span><span class="sxs-lookup"><span data-stu-id="8f442-105">There is an instance of the **Buffer Node** object for each NUMA node in use.</span></span> <span data-ttu-id="8f442-106">In un'architettura non NUMA è disponibile una singola istanza dell'oggetto **Buffer Node** .</span><span class="sxs-lookup"><span data-stu-id="8f442-106">On non-NUMA architecture, there will be a single instance of the **Buffer Node** object.</span></span>  
  
## <a name="buffer-node-performance-objects"></a><span data-ttu-id="8f442-107">Oggetti prestazioni Buffer Node</span><span class="sxs-lookup"><span data-stu-id="8f442-107">Buffer Node Performance Objects</span></span>  
 <span data-ttu-id="8f442-108">Nella tabella seguente vengono descritti gli oggetti prestazioni **Buffer Node** di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8f442-108">This table describes the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **Buffer Node** performance objects.</span></span>  
  
|<span data-ttu-id="8f442-109">Contatori Buffer Node di SQL Server</span><span class="sxs-lookup"><span data-stu-id="8f442-109">SQL Server Buffer Node counters</span></span>|<span data-ttu-id="8f442-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8f442-110">Description</span></span>|  
|-------------------------------------|-----------------|  
|<span data-ttu-id="8f442-111">**Pagine di database**</span><span class="sxs-lookup"><span data-stu-id="8f442-111">**Database pages**</span></span>|<span data-ttu-id="8f442-112">Indica il numero di pagine con contenuto di database nel pool di buffer nel nodo.</span><span class="sxs-lookup"><span data-stu-id="8f442-112">Indicates the number of pages in the buffer pool on this node with database content.</span></span>|  
|<span data-ttu-id="8f442-113">**Permanenza presunta delle pagine**</span><span class="sxs-lookup"><span data-stu-id="8f442-113">**Page life expectancy**</span></span>|<span data-ttu-id="8f442-114">Indica il numero minimo di secondi in cui una pagina viene mantenuta nel pool di buffer nel nodo senza riferimenti.</span><span class="sxs-lookup"><span data-stu-id="8f442-114">Indicates the minimum number of seconds a page will stay in the buffer pool on this node without references.</span></span>|  
|<span data-ttu-id="8f442-115">**Ricerche di pagina nodo locale/sec**</span><span class="sxs-lookup"><span data-stu-id="8f442-115">**Local Node page lookups/sec**</span></span>|<span data-ttu-id="8f442-116">Indica il numero di richieste di ricerca dal nodo soddisfatte dal nodo stesso.</span><span class="sxs-lookup"><span data-stu-id="8f442-116">Indicates the number of lookup requests from this node which were satisfied from this node.</span></span>|  
|<span data-ttu-id="8f442-117">**Ricerche di pagina nodo remoto/sec**</span><span class="sxs-lookup"><span data-stu-id="8f442-117">**Remote Note page lookups/sec**</span></span>|<span data-ttu-id="8f442-118">Indica il numero di richieste di ricerca dal nodo soddisfatte da altri nodi.</span><span class="sxs-lookup"><span data-stu-id="8f442-118">Indicates the number of lookup requests from this node which were satisfied from other nodes.</span></span>|  
  
 <span data-ttu-id="8f442-119">Se SQL Server viene eseguito in componenti hardware non NUMA, i contatori degli oggetti **Buffer Node** e **Buffer Manager** devono corrispondere.</span><span class="sxs-lookup"><span data-stu-id="8f442-119">If SQL Server is running on non-NUMA hardware, the counters of **Buffer Node** and **Buffer Manager** objects should match.</span></span>  
  
 <span data-ttu-id="8f442-120">In componenti hardware NUMA le somme dei rispettivi contatori di tutti gli oggetti **Buffer Node** devono corrispondere alle relative controparti di **Buffer Manager**.</span><span class="sxs-lookup"><span data-stu-id="8f442-120">On NUMA hardware, sums of respective counters of all **Buffer Nodes** should match their counterparts of **Buffer Manager**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8f442-121">I valori dei contatori e le somme potrebbero non corrispondere esattamente a causa della natura dinamica dei contatori e dell'accuratezza del campionamento.</span><span class="sxs-lookup"><span data-stu-id="8f442-121">The counter values and sums may not match precisely due to the dynamic nature of the counters and the sampling accuracy.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f442-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8f442-122">See Also</span></span>  
 <span data-ttu-id="8f442-123">[Oggetto di Gestione buffer di SQL Server](sql-server-buffer-manager-object.md) </span><span class="sxs-lookup"><span data-stu-id="8f442-123">[SQL Server, Buffer Manager Object](sql-server-buffer-manager-object.md) </span></span>  
 <span data-ttu-id="8f442-124">[Opzioni di configurazione del server Server Memory](../../database-engine/configure-windows/server-memory-server-configuration-options.md) </span><span class="sxs-lookup"><span data-stu-id="8f442-124">[Server Memory Server Configuration Options](../../database-engine/configure-windows/server-memory-server-configuration-options.md) </span></span>  
 <span data-ttu-id="8f442-125">[Monitoraggio dell'utilizzo delle risorse &#40;Monitor di sistema&#41;](monitor-resource-usage-system-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="8f442-125">[Monitor Resource Usage &#40;System Monitor&#41;](monitor-resource-usage-system-monitor.md) </span></span>  
 [<span data-ttu-id="8f442-126">sys.dm_os_performance_counters &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8f442-126">sys.dm_os_performance_counters &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-os-performance-counters-transact-sql)  
  
  
