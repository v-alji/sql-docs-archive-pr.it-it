---
title: MSSQLSERVER_41365 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 41365 (Database Engine error)
ms.assetid: 4fc7ec15-b722-4e3d-b7f9-3d39d171e96e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1382a6395f1929a5d5552113e07376bcbf80bf35
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629847"
---
# <a name="mssqlserver_41365"></a><span data-ttu-id="78d74-102">MSSQLSERVER_41365</span><span class="sxs-lookup"><span data-stu-id="78d74-102">MSSQLSERVER_41365</span></span>
    
## <a name="details"></a><span data-ttu-id="78d74-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="78d74-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="78d74-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="78d74-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="78d74-105">ID evento</span><span class="sxs-lookup"><span data-stu-id="78d74-105">Event ID</span></span>|<span data-ttu-id="78d74-106">41365</span><span class="sxs-lookup"><span data-stu-id="78d74-106">41365</span></span>|  
|<span data-ttu-id="78d74-107">Origine evento</span><span class="sxs-lookup"><span data-stu-id="78d74-107">Event Source</span></span>|<span data-ttu-id="78d74-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="78d74-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="78d74-109">Componente</span><span class="sxs-lookup"><span data-stu-id="78d74-109">Component</span></span>|<span data-ttu-id="78d74-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="78d74-110">SQLEngine</span></span>|  
|<span data-ttu-id="78d74-111">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="78d74-111">Symbolic Name</span></span>|<span data-ttu-id="78d74-112">HK_MERGE_SCHEDULE_ERROR</span><span class="sxs-lookup"><span data-stu-id="78d74-112">HK_MERGE_SCHEDULE_ERROR</span></span>|  
|<span data-ttu-id="78d74-113">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="78d74-113">Message Text</span></span>|<span data-ttu-id="78d74-114">La richiesta di unione per l'intervallo della transazioni [%ld, %ld) sul database %.\*ls non è stata pianificata.</span><span class="sxs-lookup"><span data-stu-id="78d74-114">Merge request for transaction range [%ld, %ld] on database %.\*ls was not scheduled.</span></span> <span data-ttu-id="78d74-115">I file del checkpoint che rappresentano l'intervallo non sono disponibili per unione o parte di un'unione in corso.</span><span class="sxs-lookup"><span data-stu-id="78d74-115">The checkpoint files representing the range are either not available for merge or part of an ongoing merge.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="78d74-116">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="78d74-116">Explanation</span></span>  
 <span data-ttu-id="78d74-117">I file del checkpoint che rappresentano l'intervallo non sono disponibili per unione o parte di un'unione in corso.</span><span class="sxs-lookup"><span data-stu-id="78d74-117">The checkpoint files representing the range are either not available for merge or part of an ongoing merge.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="78d74-118">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="78d74-118">User Action</span></span>  
 <span data-ttu-id="78d74-119">Fornire un migliore intervallo di transazioni per merge/attesa prima di eseguire la stessa richiesta.</span><span class="sxs-lookup"><span data-stu-id="78d74-119">Provide a better transaction range for merge/wait before issuing the same request again.</span></span> <span data-ttu-id="78d74-120">Per altre informazioni, vedere [OLTP in memoria &#40;ottimizzazione in memoria&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="78d74-120">For more information, see [In-Memory OLTP &#40;In-Memory Optimization&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78d74-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="78d74-121">See Also</span></span>  
 [<span data-ttu-id="78d74-122">OLTP in memoria &#40;ottimizzazione per la memoria&#41;</span><span class="sxs-lookup"><span data-stu-id="78d74-122">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
