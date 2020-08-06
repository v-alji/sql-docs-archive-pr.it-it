---
title: MSSQLSERVER_41359 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 41359 (Database Engine error)
ms.assetid: 02b717c7-9170-4676-b0f6-4dec9eb5b5d4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 7cf45a117dcda0827672c6072c603a1fc0866a33
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636718"
---
# <a name="mssqlserver_41359"></a><span data-ttu-id="6d64b-102">MSSQLSERVER_41359</span><span class="sxs-lookup"><span data-stu-id="6d64b-102">MSSQLSERVER_41359</span></span>
    
## <a name="details"></a><span data-ttu-id="6d64b-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="6d64b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6d64b-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="6d64b-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="6d64b-105">ID evento</span><span class="sxs-lookup"><span data-stu-id="6d64b-105">Event ID</span></span>|<span data-ttu-id="6d64b-106">41359</span><span class="sxs-lookup"><span data-stu-id="6d64b-106">41359</span></span>|  
|<span data-ttu-id="6d64b-107">Origine evento</span><span class="sxs-lookup"><span data-stu-id="6d64b-107">Event Source</span></span>|<span data-ttu-id="6d64b-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="6d64b-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="6d64b-109">Componente</span><span class="sxs-lookup"><span data-stu-id="6d64b-109">Component</span></span>|<span data-ttu-id="6d64b-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="6d64b-110">SQLEngine</span></span>|  
|<span data-ttu-id="6d64b-111">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="6d64b-111">Symbolic Name</span></span>|<span data-ttu-id="6d64b-112">SQL_READ_COMMITTED_SNAPSHOT_NOT_SUPPORTED</span><span class="sxs-lookup"><span data-stu-id="6d64b-112">SQL_READ_COMMITTED_SNAPSHOT_NOT_SUPPORTED</span></span>|  
|<span data-ttu-id="6d64b-113">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="6d64b-113">Message Text</span></span>|<span data-ttu-id="6d64b-114">Una query che accede a tabelle con ottimizzazione per la memoria utilizzando il livello di isolamento READ COMMITTED non può accedere alle tabelle basate su disco quando l'opzione di database READ_COMMITTED_SNAPSHOT è impostata su ON.</span><span class="sxs-lookup"><span data-stu-id="6d64b-114">A query that accesses memory optimized tables using the READ COMMITTED isolation level, cannot access disk based tables when the database option READ_COMMITTED_SNAPSHOT is set to ON.</span></span> <span data-ttu-id="6d64b-115">Specificare un livello di isolamento supportato per la tabella con ottimizzazione per la memoria utilizzando un hint di tabella, ad esempio WITH (SNAPSHOT).</span><span class="sxs-lookup"><span data-stu-id="6d64b-115">Provide a supported isolation level for the memory optimized table using a table hint, such as WITH (SNAPSHOT).</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="6d64b-116">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="6d64b-116">Explanation</span></span>  
 <span data-ttu-id="6d64b-117">Il database con READ_COMMITTED_SNAPSHOT=ON non supporta le transazioni che accedono sia alle tabelle ottimizzate per la memoria che a tabelle basate su disco.</span><span class="sxs-lookup"><span data-stu-id="6d64b-117">The database with READ_COMMITTED_SNAPSHOT=ON does not support the transactions that access both memory-optimized tables and disk based tables.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6d64b-118">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="6d64b-118">User Action</span></span>  
 <span data-ttu-id="6d64b-119">Impostare READ_COMMITTED_SNAPSHOT su OFF o specificare un livello di isolamento supportato per la tabella ottimizzata per la memoria utilizzando un hint a livello di tabella, ad esempio WITH (SNAPSHOT).</span><span class="sxs-lookup"><span data-stu-id="6d64b-119">Set READ_COMMITTED_SNAPSHOT to OFF or supply a supported isolation level for the memory-optimized table using a table-level hint, such as WITH (SNAPSHOT).</span></span> <span data-ttu-id="6d64b-120">Per altre informazioni, vedere [OLTP in memoria &#40;ottimizzazione in memoria&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="6d64b-120">For more information, see [In-Memory OLTP &#40;In-Memory Optimization&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d64b-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6d64b-121">See Also</span></span>  
 [<span data-ttu-id="6d64b-122">OLTP in memoria &#40;ottimizzazione per la memoria&#41;</span><span class="sxs-lookup"><span data-stu-id="6d64b-122">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
