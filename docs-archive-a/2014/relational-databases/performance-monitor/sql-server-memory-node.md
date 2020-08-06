---
title: Memory Node di SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
ms.assetid: 55b28ba9-b6d5-4ea9-8103-db8a72f42982
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d5bbc3f581ea9ececeb7d55a614ef27c3c72de7f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637252"
---
# <a name="sql-server-memory-node"></a><span data-ttu-id="82aa6-102">SQL Server, Memory Node</span><span class="sxs-lookup"><span data-stu-id="82aa6-102">SQL Server, Memory Node</span></span>
  <span data-ttu-id="82aa6-103">L'oggetto **Memory Node** di Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fornisce contatori per il monitoraggio dell'utilizzo della memoria del server in nodi NUMA.</span><span class="sxs-lookup"><span data-stu-id="82aa6-103">The **Memory Node** object in Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provides counters to monitor server memory usage on NUMA nodes.</span></span>  
  
## <a name="memory-node-counters"></a><span data-ttu-id="82aa6-104">Contatori Memory Node</span><span class="sxs-lookup"><span data-stu-id="82aa6-104">Memory Node Counters</span></span>  
 <span data-ttu-id="82aa6-105">Nella tabella seguente vengono descritti i contatori dell'oggetto **Memory Node** di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="82aa6-105">This table describes the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **Memory Node** counters.</span></span>  
  
|<span data-ttu-id="82aa6-106">Contatori Memory Manager di SQL Server</span><span class="sxs-lookup"><span data-stu-id="82aa6-106">SQL Server Memory Manager counters</span></span>|<span data-ttu-id="82aa6-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="82aa6-107">Description</span></span>|  
|----------------------------------------|-----------------|  
|<span data-ttu-id="82aa6-108">**Memoria nodo database (KB)**</span><span class="sxs-lookup"><span data-stu-id="82aa6-108">**Database Node Memory (KB)**</span></span>|<span data-ttu-id="82aa6-109">Specifica la quantità di memoria utilizzata dal server nel nodo per le pagine del database.</span><span class="sxs-lookup"><span data-stu-id="82aa6-109">Specifies the amount of memory the server is currently using on this node for database pages.</span></span>|  
|<span data-ttu-id="82aa6-110">**Memoria nodo disponibile (KB)**</span><span class="sxs-lookup"><span data-stu-id="82aa6-110">**Free Node Memory (KB)**</span></span>|<span data-ttu-id="82aa6-111">Specifica la quantità di memoria non utilizzata dal server nel nodo.</span><span class="sxs-lookup"><span data-stu-id="82aa6-111">Specifies the amount of memory the server is not using on this node.</span></span>|  
|<span data-ttu-id="82aa6-112">**Memoria nodo esterna (KB)**</span><span class="sxs-lookup"><span data-stu-id="82aa6-112">**Foreign Node Memory (KB)**</span></span>|<span data-ttu-id="82aa6-113">Specifica la quantità di memoria non locale NUMA nel nodo.</span><span class="sxs-lookup"><span data-stu-id="82aa6-113">Specifies the amount of non NUMA-local memory on this node.</span></span>|  
|<span data-ttu-id="82aa6-114">**Memoria nodo prelevata (KB)**</span><span class="sxs-lookup"><span data-stu-id="82aa6-114">**Stolen Memory Node (KB)**</span></span>|<span data-ttu-id="82aa6-115">Specifica la quantità di memoria utilizzata dal server nel nodo per scopi diversi dalle pagine del database.</span><span class="sxs-lookup"><span data-stu-id="82aa6-115">Specifies the amount of memory the server is using on this node for purposes other than database pages.</span></span>|  
|<span data-ttu-id="82aa6-116">**Memoria nodo di destinazione**</span><span class="sxs-lookup"><span data-stu-id="82aa6-116">**Target Node Memory**</span></span>|<span data-ttu-id="82aa6-117">Specifica la quantità di memoria ideale per il nodo.</span><span class="sxs-lookup"><span data-stu-id="82aa6-117">Specifies the ideal amount of memory for this node.</span></span>|  
|<span data-ttu-id="82aa6-118">**Memoria nodo totale**</span><span class="sxs-lookup"><span data-stu-id="82aa6-118">**Total Node Memory**</span></span>|<span data-ttu-id="82aa6-119">Indica la quantità totale di memoria riservata dal server nel nodo.</span><span class="sxs-lookup"><span data-stu-id="82aa6-119">Indicates the total amount of memory the server has committed on this node.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="82aa6-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="82aa6-120">See Also</span></span>  
 <span data-ttu-id="82aa6-121">[Monitoraggio dell'utilizzo delle risorse &#40;Monitor di sistema&#41;](monitor-resource-usage-system-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="82aa6-121">[Monitor Resource Usage &#40;System Monitor&#41;](monitor-resource-usage-system-monitor.md) </span></span>  
 <span data-ttu-id="82aa6-122">[Oggetto di Gestione buffer di SQL Server](sql-server-buffer-manager-object.md) </span><span class="sxs-lookup"><span data-stu-id="82aa6-122">[SQL Server, Buffer Manager Object](sql-server-buffer-manager-object.md) </span></span>  
 [<span data-ttu-id="82aa6-123">sys.dm_os_performance_counters &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="82aa6-123">sys.dm_os_performance_counters &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-os-performance-counters-transact-sql)  
  
  
