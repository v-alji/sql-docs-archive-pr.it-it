---
title: MSSQLSERVER_41325 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 41325 (Database Engine error)
ms.assetid: 97c6a8bb-139a-44f3-9ed5-f46d047e8ed3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: a512d7db6529876259d889d04aabf3d07747cafe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716372"
---
# <a name="mssqlserver_41325"></a><span data-ttu-id="daab8-102">MSSQLSERVER_41325</span><span class="sxs-lookup"><span data-stu-id="daab8-102">MSSQLSERVER_41325</span></span>
    
## <a name="details"></a><span data-ttu-id="daab8-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="daab8-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="daab8-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="daab8-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="daab8-105">ID evento</span><span class="sxs-lookup"><span data-stu-id="daab8-105">Event ID</span></span>|<span data-ttu-id="daab8-106">41325</span><span class="sxs-lookup"><span data-stu-id="daab8-106">41325</span></span>|  
|<span data-ttu-id="daab8-107">Origine evento</span><span class="sxs-lookup"><span data-stu-id="daab8-107">Event Source</span></span>|<span data-ttu-id="daab8-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="daab8-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="daab8-109">Componente</span><span class="sxs-lookup"><span data-stu-id="daab8-109">Component</span></span>|<span data-ttu-id="daab8-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="daab8-110">SQLEngine</span></span>|  
|<span data-ttu-id="daab8-111">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="daab8-111">Symbolic Name</span></span>|<span data-ttu-id="daab8-112">HK_TX_COMMIT_SR_VALIDATION</span><span class="sxs-lookup"><span data-stu-id="daab8-112">HK_TX_COMMIT_SR_VALIDATION</span></span>|  
|<span data-ttu-id="daab8-113">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="daab8-113">Message Text</span></span>|<span data-ttu-id="daab8-114">Impossibile eseguire il commit della transazione corrente a causa di un errore di convalida serializzabile.</span><span class="sxs-lookup"><span data-stu-id="daab8-114">The current transaction failed to commit due to a serializable validation failure.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="daab8-115">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="daab8-115">Explanation</span></span>  
 <span data-ttu-id="daab8-116">La transazione ha rilevato un errore di convalida ed è stata eliminata.</span><span class="sxs-lookup"><span data-stu-id="daab8-116">The transaction encountered a validation failure and is now doomed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="daab8-117">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="daab8-117">User Action</span></span>  
 <span data-ttu-id="daab8-118">Ripetere la transazione non riuscita.</span><span class="sxs-lookup"><span data-stu-id="daab8-118">Retry the failed transaction.</span></span> <span data-ttu-id="daab8-119">Per altre informazioni, vedere [OLTP in memoria &#40;ottimizzazione in memoria&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="daab8-119">For more information, see [In-Memory OLTP &#40;In-Memory Optimization&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="daab8-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="daab8-120">See Also</span></span>  
 [<span data-ttu-id="daab8-121">OLTP in memoria &#40;ottimizzazione per la memoria&#41;</span><span class="sxs-lookup"><span data-stu-id="daab8-121">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
