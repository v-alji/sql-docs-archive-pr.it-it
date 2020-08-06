---
title: Oggetto Cursor Manager by Type di SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Cursor Manager by Type object
- SQLServer:Cursor Manager by Type
ms.assetid: d67fbd8a-7554-4a16-96f1-d9ee857a95e3
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 7bee15aa2917f7b8890e6c1d3f26cc0e210208a7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625351"
---
# <a name="sql-server-cursor-manager-by-type-object"></a><span data-ttu-id="c95d0-102">Oggetto Gestione cursori per tipo di SQL Server</span><span class="sxs-lookup"><span data-stu-id="c95d0-102">SQL Server, Cursor Manager by Type Object</span></span>
  <span data-ttu-id="c95d0-103">L'oggetto **SQLServer:Gestione cursori per tipo** include contatori per il monitoraggio dei cursori, raggruppati per tipo.</span><span class="sxs-lookup"><span data-stu-id="c95d0-103">The **SQLServer:Cursor Manager by Type** object provides counters to monitor cursors, grouped by type.</span></span>  
  
 <span data-ttu-id="c95d0-104">Nella tabella seguente vengono descritti i contatori dell'oggetto **Gestione cursori per tipo** di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c95d0-104">This table describes the SQL Server **Cursor Manager by Type** counters.</span></span>  
  
|<span data-ttu-id="c95d0-105">Contatori di Gestione cursori per tipo</span><span class="sxs-lookup"><span data-stu-id="c95d0-105">Cursor Manager by Type counters</span></span>|<span data-ttu-id="c95d0-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c95d0-106">Description</span></span>|  
|-------------------------------------|-----------------|  
|<span data-ttu-id="c95d0-107">**Cursori attivi**</span><span class="sxs-lookup"><span data-stu-id="c95d0-107">**Active cursors**</span></span>|<span data-ttu-id="c95d0-108">Numero di cursori attivi.</span><span class="sxs-lookup"><span data-stu-id="c95d0-108">Number of active cursors.</span></span>|  
|<span data-ttu-id="c95d0-109">**Percentuale riscontri cache**</span><span class="sxs-lookup"><span data-stu-id="c95d0-109">**Cache Hit Ratio**</span></span>|<span data-ttu-id="c95d0-110">Rapporto tra riscontri e ricerche nella cache.</span><span class="sxs-lookup"><span data-stu-id="c95d0-110">Ratio between cache hits and lookups.</span></span>|  
|<span data-ttu-id="c95d0-111">**Conteggio cursori nella cache**</span><span class="sxs-lookup"><span data-stu-id="c95d0-111">**Cached Cursor Counts**</span></span>|<span data-ttu-id="c95d0-112">Numero di cursori di un determinato tipo disponibili nella cache.</span><span class="sxs-lookup"><span data-stu-id="c95d0-112">Number of cursors of a given type in the cache.</span></span>|  
|<span data-ttu-id="c95d0-113">**Conteggio utilizzi cache cursori/sec**</span><span class="sxs-lookup"><span data-stu-id="c95d0-113">**Cursor Cache Use Count/sec**</span></span>|<span data-ttu-id="c95d0-114">Numero di utilizzi di ogni tipo di cursore nella cache.</span><span class="sxs-lookup"><span data-stu-id="c95d0-114">Times each type of cached cursor has been used.</span></span>|  
|<span data-ttu-id="c95d0-115">**Utilizzo memoria cursori**</span><span class="sxs-lookup"><span data-stu-id="c95d0-115">**Cursor memory usage**</span></span>|<span data-ttu-id="c95d0-116">Quantità di memoria utilizzata dai cursori in KB.</span><span class="sxs-lookup"><span data-stu-id="c95d0-116">Amount of memory consumed by cursors in kilobytes (KB).</span></span>|  
|<span data-ttu-id="c95d0-117">**Richieste cursori/sec**</span><span class="sxs-lookup"><span data-stu-id="c95d0-117">**Cursor Requests/sec**</span></span>|<span data-ttu-id="c95d0-118">Numero di richieste di cursori SQL ricevute dal server.</span><span class="sxs-lookup"><span data-stu-id="c95d0-118">Number of SQL cursor requests received by server.</span></span>|  
|<span data-ttu-id="c95d0-119">**Utilizzo tabelle di lavoro cursori**</span><span class="sxs-lookup"><span data-stu-id="c95d0-119">**Cursor worktable usage**</span></span>|<span data-ttu-id="c95d0-120">Numero di tabelle di lavoro utilizzate dai cursori.</span><span class="sxs-lookup"><span data-stu-id="c95d0-120">Number of worktables used by cursors.</span></span>|  
|<span data-ttu-id="c95d0-121">**Numero piani cursore attivi**</span><span class="sxs-lookup"><span data-stu-id="c95d0-121">**Number of active cursor plans**</span></span>|<span data-ttu-id="c95d0-122">Numero di piani di cursore.</span><span class="sxs-lookup"><span data-stu-id="c95d0-122">Number of cursor plans.</span></span>|  
  
 <span data-ttu-id="c95d0-123">Per ogni contatore nell'oggetto sono disponibili le istanze seguenti:</span><span class="sxs-lookup"><span data-stu-id="c95d0-123">Each counter in the object contains the following instances:</span></span>  
  
|<span data-ttu-id="c95d0-124">Istanza di Gestione cursori</span><span class="sxs-lookup"><span data-stu-id="c95d0-124">Cursor Manager instance</span></span>|<span data-ttu-id="c95d0-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c95d0-125">Description</span></span>|  
|-----------------------------|-----------------|  
|<span data-ttu-id="c95d0-126">**_Total**</span><span class="sxs-lookup"><span data-stu-id="c95d0-126">**_Total**</span></span>|<span data-ttu-id="c95d0-127">Informazioni relative a tutti i cursori.</span><span class="sxs-lookup"><span data-stu-id="c95d0-127">Information for all cursors.</span></span>|  
|<span data-ttu-id="c95d0-128">**API Cursor**</span><span class="sxs-lookup"><span data-stu-id="c95d0-128">**API Cursor**</span></span>|<span data-ttu-id="c95d0-129">Solo informazioni relative al cursore API.</span><span class="sxs-lookup"><span data-stu-id="c95d0-129">Only the API cursor information.</span></span>|  
|<span data-ttu-id="c95d0-130">**TSQL Global Cursor**</span><span class="sxs-lookup"><span data-stu-id="c95d0-130">**TSQL Global Cursor**</span></span>|<span data-ttu-id="c95d0-131">Solo informazioni relative al cursore [!INCLUDE[tsql](../../includes/tsql-md.md)] globale.</span><span class="sxs-lookup"><span data-stu-id="c95d0-131">Only the [!INCLUDE[tsql](../../includes/tsql-md.md)] global cursor information.</span></span>|  
|<span data-ttu-id="c95d0-132">**TSQL Local Cursor**</span><span class="sxs-lookup"><span data-stu-id="c95d0-132">**TSQL Local Cursor**</span></span>|<span data-ttu-id="c95d0-133">Solo informazioni relative al cursore [!INCLUDE[tsql](../../includes/tsql-md.md)] locale.</span><span class="sxs-lookup"><span data-stu-id="c95d0-133">Only the [!INCLUDE[tsql](../../includes/tsql-md.md)] local cursor information.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c95d0-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c95d0-134">See Also</span></span>  
 [<span data-ttu-id="c95d0-135">Monitorare l'utilizzo delle risorse &#40;Monitor di sistema&#41;</span><span class="sxs-lookup"><span data-stu-id="c95d0-135">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](monitor-resource-usage-system-monitor.md)  
  
  
