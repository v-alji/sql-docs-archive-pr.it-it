---
title: MSSQLSERVER_41332 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 41332 (Database Engine error)
ms.assetid: d3403c3e-d178-4006-b6c9-c18609562db5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 72a87838673f07f7a40596517ab54533d944e15e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635086"
---
# <a name="mssqlserver_41332"></a><span data-ttu-id="fad95-102">MSSQLSERVER_41332</span><span class="sxs-lookup"><span data-stu-id="fad95-102">MSSQLSERVER_41332</span></span>
    
## <a name="details"></a><span data-ttu-id="fad95-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="fad95-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fad95-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="fad95-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="fad95-105">ID evento</span><span class="sxs-lookup"><span data-stu-id="fad95-105">Event ID</span></span>|<span data-ttu-id="fad95-106">41332</span><span class="sxs-lookup"><span data-stu-id="fad95-106">41332</span></span>|  
|<span data-ttu-id="fad95-107">Origine evento</span><span class="sxs-lookup"><span data-stu-id="fad95-107">Event Source</span></span>|<span data-ttu-id="fad95-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="fad95-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="fad95-109">Componente</span><span class="sxs-lookup"><span data-stu-id="fad95-109">Component</span></span>|<span data-ttu-id="fad95-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="fad95-110">SQLEngine</span></span>|  
|<span data-ttu-id="fad95-111">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="fad95-111">Symbolic Name</span></span>|<span data-ttu-id="fad95-112">SQL_SNAPSHOT_NOT_SUPPORTED</span><span class="sxs-lookup"><span data-stu-id="fad95-112">SQL_SNAPSHOT_NOT_SUPPORTED</span></span>|  
|<span data-ttu-id="fad95-113">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="fad95-113">Message Text</span></span>|<span data-ttu-id="fad95-114">Non è possibile creare o accedere alle tabelle con ottimizzazione per la memoria e alle stored procedure compilate in modo nativo quando la sessione TRANSACTION ISOLATION LEVEL è impostata su SNAPSHOT.</span><span class="sxs-lookup"><span data-stu-id="fad95-114">Memory optimized tables and natively compiled stored procedures cannot be accessed or created when the session TRANSACTION ISOLATION LEVEL is set to SNAPSHOT.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="fad95-115">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="fad95-115">Explanation</span></span>  
 <span data-ttu-id="fad95-116">La transazione è stata avviata nel livello di isolamento dello snapshot e quindi ha tentato di utilizzare una funzionalità non compatibile.</span><span class="sxs-lookup"><span data-stu-id="fad95-116">The transaction was started in snapshot isolation level and then attempted to use an incompatible feature.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="fad95-117">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="fad95-117">User Action</span></span>  
 <span data-ttu-id="fad95-118">Avviare la transazione con un livello di isolamento diverso.</span><span class="sxs-lookup"><span data-stu-id="fad95-118">Start the transaction with a different isolation level.</span></span> <span data-ttu-id="fad95-119">Per altre informazioni, vedere [OLTP in memoria &#40;ottimizzazione in memoria&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="fad95-119">For more information, see [In-Memory OLTP &#40;In-Memory Optimization&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fad95-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fad95-120">See Also</span></span>  
 [<span data-ttu-id="fad95-121">OLTP in memoria &#40;ottimizzazione per la memoria&#41;</span><span class="sxs-lookup"><span data-stu-id="fad95-121">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
