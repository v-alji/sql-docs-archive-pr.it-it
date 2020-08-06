---
title: MSSQLSERVER_41302 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 41302 (Database Engine error)
ms.assetid: 01e75618-afec-4232-ba68-93ab7bc31003
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 751dac91378c002a7e6c6c619ddaf12be8173400
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627280"
---
# <a name="mssqlserver_41302"></a><span data-ttu-id="7bb4f-102">MSSQLSERVER_41302</span><span class="sxs-lookup"><span data-stu-id="7bb4f-102">MSSQLSERVER_41302</span></span>
    
## <a name="details"></a><span data-ttu-id="7bb4f-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="7bb4f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7bb4f-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="7bb4f-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="7bb4f-105">ID evento</span><span class="sxs-lookup"><span data-stu-id="7bb4f-105">Event ID</span></span>|<span data-ttu-id="7bb4f-106">41302</span><span class="sxs-lookup"><span data-stu-id="7bb4f-106">41302</span></span>|  
|<span data-ttu-id="7bb4f-107">Origine evento</span><span class="sxs-lookup"><span data-stu-id="7bb4f-107">Event Source</span></span>|<span data-ttu-id="7bb4f-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="7bb4f-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="7bb4f-109">Componente</span><span class="sxs-lookup"><span data-stu-id="7bb4f-109">Component</span></span>|<span data-ttu-id="7bb4f-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="7bb4f-110">SQLEngine</span></span>|  
|<span data-ttu-id="7bb4f-111">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="7bb4f-111">Symbolic Name</span></span>|<span data-ttu-id="7bb4f-112">WRITE_WRITE_CONFLICT</span><span class="sxs-lookup"><span data-stu-id="7bb4f-112">WRITE_WRITE_CONFLICT</span></span>|  
|<span data-ttu-id="7bb4f-113">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="7bb4f-113">Message Text</span></span>|<span data-ttu-id="7bb4f-114">Tentativo da parte della transazione corrente di aggiornare un record che è già stato aggiornato dopo l'avvio della transazione.</span><span class="sxs-lookup"><span data-stu-id="7bb4f-114">The current transaction attempted to update a record that has been updated since this transaction started.</span></span> <span data-ttu-id="7bb4f-115">La transazione è stata interrotta.</span><span class="sxs-lookup"><span data-stu-id="7bb4f-115">The transaction was aborted.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7bb4f-116">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="7bb4f-116">Explanation</span></span>  
 <span data-ttu-id="7bb4f-117">La transazione ha rilevato un conflitto di scrittura/scrittura e l'istruzione è stata terminata.</span><span class="sxs-lookup"><span data-stu-id="7bb4f-117">The transaction encountered a write/write conflict and the statement terminated.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7bb4f-118">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="7bb4f-118">User Action</span></span>  
 <span data-ttu-id="7bb4f-119">Rieseguire l'operazione in una transazione diversa in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="7bb4f-119">Retry the operation later in a different transaction.</span></span> <span data-ttu-id="7bb4f-120">Per altre informazioni, vedere [OLTP in memoria &#40;ottimizzazione in memoria&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="7bb4f-120">For more information, see [In-Memory OLTP &#40;In-Memory Optimization&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bb4f-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7bb4f-121">See Also</span></span>  
 [<span data-ttu-id="7bb4f-122">OLTP in memoria &#40;ottimizzazione per la memoria&#41;</span><span class="sxs-lookup"><span data-stu-id="7bb4f-122">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
