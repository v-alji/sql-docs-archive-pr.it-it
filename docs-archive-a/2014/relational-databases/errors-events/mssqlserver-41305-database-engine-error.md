---
title: MSSQLSERVER_41305 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 41305 (Database Engine error)
ms.assetid: a96e5083-ff97-4003-a900-07942454151d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 9c00e20ec220d7fcee0da4e99c2ef35817dae67f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629848"
---
# <a name="mssqlserver_41305"></a><span data-ttu-id="3c1e6-102">MSSQLSERVER_41305</span><span class="sxs-lookup"><span data-stu-id="3c1e6-102">MSSQLSERVER_41305</span></span>
    
## <a name="details"></a><span data-ttu-id="3c1e6-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="3c1e6-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3c1e6-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="3c1e6-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="3c1e6-105">ID evento</span><span class="sxs-lookup"><span data-stu-id="3c1e6-105">Event ID</span></span>|<span data-ttu-id="3c1e6-106">41305</span><span class="sxs-lookup"><span data-stu-id="3c1e6-106">41305</span></span>|  
|<span data-ttu-id="3c1e6-107">Origine evento</span><span class="sxs-lookup"><span data-stu-id="3c1e6-107">Event Source</span></span>|<span data-ttu-id="3c1e6-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="3c1e6-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="3c1e6-109">Componente</span><span class="sxs-lookup"><span data-stu-id="3c1e6-109">Component</span></span>|<span data-ttu-id="3c1e6-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="3c1e6-110">SQLEngine</span></span>|  
|<span data-ttu-id="3c1e6-111">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="3c1e6-111">Symbolic Name</span></span>|<span data-ttu-id="3c1e6-112">HK_TX_COMMIT_RR_VALIDATION</span><span class="sxs-lookup"><span data-stu-id="3c1e6-112">HK_TX_COMMIT_RR_VALIDATION</span></span>|  
|<span data-ttu-id="3c1e6-113">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="3c1e6-113">Message Text</span></span>|<span data-ttu-id="3c1e6-114">Impossibile eseguire il commit della transazione corrente a causa di un errore di convalida di lettura ripetibile.</span><span class="sxs-lookup"><span data-stu-id="3c1e6-114">The current transaction failed to commit due to a repeatable read validation failure.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="3c1e6-115">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="3c1e6-115">Explanation</span></span>  
 <span data-ttu-id="3c1e6-116">La transazione ha rilevato un errore di convalida ed è stata eliminata.</span><span class="sxs-lookup"><span data-stu-id="3c1e6-116">The transaction encountered a validation failure and is now doomed.</span></span>  
  
 <span data-ttu-id="3c1e6-117">Per altre informazioni, vedere [OLTP in memoria &#40;ottimizzazione in memoria&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="3c1e6-117">For more information, see [In-Memory OLTP &#40;In-Memory Optimization&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3c1e6-118">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="3c1e6-118">User Action</span></span>  
 <span data-ttu-id="3c1e6-119">Ripetere la transazione non riuscita.</span><span class="sxs-lookup"><span data-stu-id="3c1e6-119">Retry the failed transaction.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c1e6-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3c1e6-120">See Also</span></span>  
 [<span data-ttu-id="3c1e6-121">OLTP in memoria &#40;ottimizzazione per la memoria&#41;</span><span class="sxs-lookup"><span data-stu-id="3c1e6-121">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
