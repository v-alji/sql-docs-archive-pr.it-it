---
title: MSSQLSERVER_41307 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 41307 (Database Engine error)
ms.assetid: 56f56410-b07d-4379-b01c-702c95761070
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 98407a65d5529fd73bccc638df11167131bd9f8d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718186"
---
# <a name="mssqlserver_41307"></a><span data-ttu-id="57771-102">MSSQLSERVER_41307</span><span class="sxs-lookup"><span data-stu-id="57771-102">MSSQLSERVER_41307</span></span>
    
## <a name="details"></a><span data-ttu-id="57771-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="57771-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="57771-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="57771-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="57771-105">ID evento</span><span class="sxs-lookup"><span data-stu-id="57771-105">Event ID</span></span>|<span data-ttu-id="57771-106">41307</span><span class="sxs-lookup"><span data-stu-id="57771-106">41307</span></span>|  
|<span data-ttu-id="57771-107">Origine evento</span><span class="sxs-lookup"><span data-stu-id="57771-107">Event Source</span></span>|<span data-ttu-id="57771-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="57771-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="57771-109">Componente</span><span class="sxs-lookup"><span data-stu-id="57771-109">Component</span></span>|<span data-ttu-id="57771-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="57771-110">SQLEngine</span></span>|  
|<span data-ttu-id="57771-111">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="57771-111">Symbolic Name</span></span>|<span data-ttu-id="57771-112">HK_HEKATON_ROW_LIMIT</span><span class="sxs-lookup"><span data-stu-id="57771-112">HK_HEKATON_ROW_LIMIT</span></span>|  
|<span data-ttu-id="57771-113">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="57771-113">Message Text</span></span>|<span data-ttu-id="57771-114">Il limite di dimensioni riga di *numero* byte per le tabelle con ottimizzazione per la memoria è stato superato.</span><span class="sxs-lookup"><span data-stu-id="57771-114">The row size limit of *number* bytes for memory optimized tables has been exceeded.</span></span> <span data-ttu-id="57771-115">Semplificare la definizione di tabella.</span><span class="sxs-lookup"><span data-stu-id="57771-115">Please simplify the table definition.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="57771-116">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="57771-116">Explanation</span></span>  
 <span data-ttu-id="57771-117">Il limite di dimensioni riga per le tabelle con ottimizzazione per la memoria è di 8.060 byte.</span><span class="sxs-lookup"><span data-stu-id="57771-117">The row size limit for memory optimized tables is 8,060 bytes.</span></span> <span data-ttu-id="57771-118">Per altre informazioni, vedere [Dimensioni di tabelle e righe per le tabelle con ottimizzazione per la memoria](../in-memory-oltp/memory-optimized-tables.md).</span><span class="sxs-lookup"><span data-stu-id="57771-118">For more information, see [Table and Row Size in Memory-Optimized Tables](../in-memory-oltp/memory-optimized-tables.md).</span></span> <span data-ttu-id="57771-119">Per altre informazioni, vedere [OLTP in memoria &#40;ottimizzazione in memoria&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="57771-119">For more information, see [In-Memory OLTP &#40;In-Memory Optimization&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57771-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="57771-120">See Also</span></span>  
 [<span data-ttu-id="57771-121">OLTP in memoria &#40;ottimizzazione per la memoria&#41;</span><span class="sxs-lookup"><span data-stu-id="57771-121">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
