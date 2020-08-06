---
title: MSSQLSERVER_17084 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 17084 (Database Engine error)
ms.assetid: e579d104-3307-4edd-8587-b14ecbc02ed9
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 59b0fc3e0884ddd89809767a068b937b5c145f9e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636141"
---
# <a name="mssqlserver_17084"></a><span data-ttu-id="5a41d-102">MSSQLSERVER_17084</span><span class="sxs-lookup"><span data-stu-id="5a41d-102">MSSQLSERVER_17084</span></span>
    
## <a name="details"></a><span data-ttu-id="5a41d-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="5a41d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5a41d-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="5a41d-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="5a41d-105">ID evento</span><span class="sxs-lookup"><span data-stu-id="5a41d-105">Event ID</span></span>|<span data-ttu-id="5a41d-106">17084</span><span class="sxs-lookup"><span data-stu-id="5a41d-106">17084</span></span>|  
|<span data-ttu-id="5a41d-107">Origine evento</span><span class="sxs-lookup"><span data-stu-id="5a41d-107">Event Source</span></span>|<span data-ttu-id="5a41d-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="5a41d-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="5a41d-109">Componente</span><span class="sxs-lookup"><span data-stu-id="5a41d-109">Component</span></span>|<span data-ttu-id="5a41d-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="5a41d-110">SQLEngine</span></span>|  
|<span data-ttu-id="5a41d-111">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="5a41d-111">Symbolic Name</span></span>|<span data-ttu-id="5a41d-112">P3_ATOMIC_WITH_MISSING_OPTION</span><span class="sxs-lookup"><span data-stu-id="5a41d-112">P3_ATOMIC_WITH_MISSING_OPTION</span></span>|  
|<span data-ttu-id="5a41d-113">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="5a41d-113">Message Text</span></span>|<span data-ttu-id="5a41d-114">La clausola WITH dell'istruzione BEGIN ATOMIC deve specificare un valore per l'opzione "%ls".</span><span class="sxs-lookup"><span data-stu-id="5a41d-114">The WITH clause of BEGIN ATOMIC statement must specify a value for the option '%ls'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5a41d-115">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="5a41d-115">Explanation</span></span>  
 <span data-ttu-id="5a41d-116">La clausola WITH dell'istruzione BEGIN ATOMIC non specificava un valore per un'opzione.</span><span class="sxs-lookup"><span data-stu-id="5a41d-116">The WITH clause of BEGIN ATOMIC statement did not specify a value for an option.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5a41d-117">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="5a41d-117">User Action</span></span>  
 <span data-ttu-id="5a41d-118">I blocchi`ATOMIC` richiedono valori per le opzioni `WITH``TRANSACTION ISOLATION LEVEL` e `LANGUAGE`.</span><span class="sxs-lookup"><span data-stu-id="5a41d-118">`ATOMIC` blocks require values for the `WITH` options `TRANSACTION ISOLATION LEVEL` and `LANGUAGE`.</span></span> <span data-ttu-id="5a41d-119">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="5a41d-119">For example::</span></span>  
  
```  
BEGIN ATOMIC WITH (TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE= N'us_english')  
```  
  
 <span data-ttu-id="5a41d-120">Per altre informazioni, vedere [OLTP in memoria &#40;ottimizzazione in memoria&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="5a41d-120">For more information, see [In-Memory OLTP &#40;In-Memory Optimization&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a41d-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5a41d-121">See Also</span></span>  
 [<span data-ttu-id="5a41d-122">OLTP in memoria &#40;ottimizzazione per la memoria&#41;</span><span class="sxs-lookup"><span data-stu-id="5a41d-122">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
