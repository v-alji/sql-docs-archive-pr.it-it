---
title: MSSQLSERVER_17083 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 17083 (Database Engine error)
ms.assetid: 6c83737d-0531-4fd9-88f6-2da5a150532d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 598cf9b0182178aa13a6d8b965ac10bedaaf5d15
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636146"
---
# <a name="mssqlserver_17083"></a><span data-ttu-id="239b3-102">MSSQLSERVER_17083</span><span class="sxs-lookup"><span data-stu-id="239b3-102">MSSQLSERVER_17083</span></span>
    
## <a name="details"></a><span data-ttu-id="239b3-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="239b3-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="239b3-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="239b3-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="239b3-105">ID evento</span><span class="sxs-lookup"><span data-stu-id="239b3-105">Event ID</span></span>|<span data-ttu-id="239b3-106">17083</span><span class="sxs-lookup"><span data-stu-id="239b3-106">17083</span></span>|  
|<span data-ttu-id="239b3-107">Origine evento</span><span class="sxs-lookup"><span data-stu-id="239b3-107">Event Source</span></span>|<span data-ttu-id="239b3-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="239b3-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="239b3-109">Componente</span><span class="sxs-lookup"><span data-stu-id="239b3-109">Component</span></span>|<span data-ttu-id="239b3-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="239b3-110">SQLEngine</span></span>|  
|<span data-ttu-id="239b3-111">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="239b3-111">Symbolic Name</span></span>|<span data-ttu-id="239b3-112">P3_HEKATON_NOT_ATOMIC</span><span class="sxs-lookup"><span data-stu-id="239b3-112">P3_HEKATON_NOT_ATOMIC</span></span>|  
|<span data-ttu-id="239b3-113">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="239b3-113">Message Text</span></span>|<span data-ttu-id="239b3-114">Il corpo di una stored procedure compilata in modo nativo deve essere un blocco ATOMIC.</span><span class="sxs-lookup"><span data-stu-id="239b3-114">The body of a natively compiled stored procedure must be an ATOMIC block.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="239b3-115">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="239b3-115">Explanation</span></span>  
 <span data-ttu-id="239b3-116">Il corpo di una stored procedure compilata in modo nativo non disponeva di un blocco ATOMIC.</span><span class="sxs-lookup"><span data-stu-id="239b3-116">The body of a natively compiled stored procedure did not have an ATOMIC block.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="239b3-117">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="239b3-117">User Action</span></span>  
 <span data-ttu-id="239b3-118">Una stored procedure compilata in modo nativo deve essere un blocco ATOMIC.</span><span class="sxs-lookup"><span data-stu-id="239b3-118">A natively compiled stored procedure must contain an ATOMIC block.</span></span> <span data-ttu-id="239b3-119">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="239b3-119">For example:</span></span>  
  
```  
BEGIN ATOMIC WITH (TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE= N'us_english')  
```  
  
 <span data-ttu-id="239b3-120">Per altre informazioni, vedere [OLTP in memoria &#40;ottimizzazione in memoria&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="239b3-120">For more information, see [In-Memory OLTP &#40;In-Memory Optimization&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="239b3-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="239b3-121">See Also</span></span>  
 [<span data-ttu-id="239b3-122">OLTP in memoria &#40;ottimizzazione per la memoria&#41;</span><span class="sxs-lookup"><span data-stu-id="239b3-122">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
