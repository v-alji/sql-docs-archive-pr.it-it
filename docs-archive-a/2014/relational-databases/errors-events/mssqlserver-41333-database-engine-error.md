---
title: MSSQLSERVER_41333 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 41333 (Database Engine error)
ms.assetid: c3c3ae9a-1e4c-4de6-ba72-2f393375b053
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6ba3cfc9627b4b44c3c9eccc620fb16bb94b861b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716375"
---
# <a name="mssqlserver_41333"></a><span data-ttu-id="aa63a-102">MSSQLSERVER_41333</span><span class="sxs-lookup"><span data-stu-id="aa63a-102">MSSQLSERVER_41333</span></span>
    
## <a name="details"></a><span data-ttu-id="aa63a-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="aa63a-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="aa63a-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="aa63a-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="aa63a-105">ID evento</span><span class="sxs-lookup"><span data-stu-id="aa63a-105">Event ID</span></span>|<span data-ttu-id="aa63a-106">41333</span><span class="sxs-lookup"><span data-stu-id="aa63a-106">41333</span></span>|  
|<span data-ttu-id="aa63a-107">Origine evento</span><span class="sxs-lookup"><span data-stu-id="aa63a-107">Event Source</span></span>|<span data-ttu-id="aa63a-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="aa63a-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="aa63a-109">Componente</span><span class="sxs-lookup"><span data-stu-id="aa63a-109">Component</span></span>|<span data-ttu-id="aa63a-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="aa63a-110">SQLEngine</span></span>|  
|<span data-ttu-id="aa63a-111">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="aa63a-111">Symbolic Name</span></span>|<span data-ttu-id="aa63a-112">CROSS_CONTAINER_ISOLATION_FAILURE</span><span class="sxs-lookup"><span data-stu-id="aa63a-112">CROSS_CONTAINER_ISOLATION_FAILURE</span></span>|  
|<span data-ttu-id="aa63a-113">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="aa63a-113">Message Text</span></span>|<span data-ttu-id="aa63a-114">Le seguenti transazioni devono accedere alle tabelle con ottimizzazione per la memoria e alle stored procedure compilate in modo nativo con isolamento dello snapshot: transazioni RepeatableRead, transazioni Serializable e transazioni che accedono alle tabelle senza ottimizzazione per la memoria in isolamento RepeatableRead o Serializable.</span><span class="sxs-lookup"><span data-stu-id="aa63a-114">The following transactions must access memory optimized tables and natively compiled stored procedures under snapshot isolation: RepeatableRead transactions, Serializable transactions, and transactions that access tables that are not memory optimized in RepeatableRead or Serializable isolation.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="aa63a-115">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="aa63a-115">Explanation</span></span>  
 <span data-ttu-id="aa63a-116">Sono presenti restrizioni relative all'uso di livelli di isolamento più elevati tra le transazioni basate su disco e le transazioni di XTP.</span><span class="sxs-lookup"><span data-stu-id="aa63a-116">There are restrictions against the user of the higher isolation levels between disk based transactions and XTP transactions.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="aa63a-117">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="aa63a-117">User Action</span></span>  
 <span data-ttu-id="aa63a-118">Non tentare operazioni con un livello di isolamento alto nelle tabelle ottimizzate per la memoria (e procedure compilate in modo nativo) e nelle tabelle basate su disco.</span><span class="sxs-lookup"><span data-stu-id="aa63a-118">Don't attempt high level isolation operations on memory-optimized tables (and natively compiled procedures) and disk based tables.</span></span>  
  
 <span data-ttu-id="aa63a-119">Per altre informazioni, vedere [OLTP in memoria &#40;ottimizzazione in memoria&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="aa63a-119">For more information, see [In-Memory OLTP &#40;In-Memory Optimization&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa63a-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aa63a-120">See Also</span></span>  
 [<span data-ttu-id="aa63a-121">OLTP in memoria &#40;ottimizzazione per la memoria&#41;</span><span class="sxs-lookup"><span data-stu-id="aa63a-121">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
