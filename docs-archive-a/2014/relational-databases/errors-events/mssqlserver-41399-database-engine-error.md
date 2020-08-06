---
title: MSSQLSERVER_41399 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 41399 (Database Engine error)
ms.assetid: 5e5acb07-16ca-4329-8210-cd2bab0c904f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2e134cbc8b39a3c65d9c515183243f0b4caed434
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627279"
---
# <a name="mssqlserver_41399"></a><span data-ttu-id="b76fb-102">MSSQLSERVER_41399</span><span class="sxs-lookup"><span data-stu-id="b76fb-102">MSSQLSERVER_41399</span></span>
    
## <a name="details"></a><span data-ttu-id="b76fb-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="b76fb-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b76fb-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="b76fb-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="b76fb-105">ID evento</span><span class="sxs-lookup"><span data-stu-id="b76fb-105">Event ID</span></span>|<span data-ttu-id="b76fb-106">41399</span><span class="sxs-lookup"><span data-stu-id="b76fb-106">41399</span></span>|  
|<span data-ttu-id="b76fb-107">Origine evento</span><span class="sxs-lookup"><span data-stu-id="b76fb-107">Event Source</span></span>|<span data-ttu-id="b76fb-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="b76fb-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="b76fb-109">Componente</span><span class="sxs-lookup"><span data-stu-id="b76fb-109">Component</span></span>|<span data-ttu-id="b76fb-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="b76fb-110">SQLEngine</span></span>|  
|<span data-ttu-id="b76fb-111">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="b76fb-111">Symbolic Name</span></span>|<span data-ttu-id="b76fb-112">MAX_SORT_ROW_WIDTH_EXCEEDED</span><span class="sxs-lookup"><span data-stu-id="b76fb-112">MAX_SORT_ROW_WIDTH_EXCEEDED</span></span>|  
|<span data-ttu-id="b76fb-113">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="b76fb-113">Message Text</span></span>|<span data-ttu-id="b76fb-114">L'operazione di ordinamento è troppo complessa.</span><span class="sxs-lookup"><span data-stu-id="b76fb-114">The sort operation is too complex.</span></span> <span data-ttu-id="b76fb-115">Per ulteriori informazioni, vedere la documentazione online di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b76fb-115">Consult SQL Server Books Online for more information.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b76fb-116">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="b76fb-116">Explanation</span></span>  
 <span data-ttu-id="b76fb-117">L'ordinamento del risultato di operazioni di join e di aggregazione aumenta la complessità dell'operazione di ordinamento incrementando le dimensioni della riga nel buffer di ordinamento.</span><span class="sxs-lookup"><span data-stu-id="b76fb-117">Sorting the result of join and aggregation operations increases the complexity of the sort operation by increasing the size of the row in the sort buffer.</span></span> <span data-ttu-id="b76fb-118">Questo errore indica che le dimensioni della riga sono maggiori delle dimensioni massime supportate dall'operatore di ordinamento nelle stored procedure compilate in modo nativo.</span><span class="sxs-lookup"><span data-stu-id="b76fb-118">This error means that the size of the row is larger than the maximum size supported by the sort operator in natively compiled stored procedures.</span></span> <span data-ttu-id="b76fb-119">Notare che le dimensioni di una riga nel buffer di ordinamento sono determinate unicamente dal numero di join e dal numero e dal tipo di funzioni di aggregazione.</span><span class="sxs-lookup"><span data-stu-id="b76fb-119">Note that the size of a row in the sort buffer is determined solely by the number of joins and the number and type of aggregate functions.</span></span> <span data-ttu-id="b76fb-120">Le dimensioni delle righe nelle tabelle di base non influisce sulle dimensioni della riga nel buffer.</span><span class="sxs-lookup"><span data-stu-id="b76fb-120">The size of the rows in the base tables does not affect the size of the row in the buffer.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b76fb-121">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="b76fb-121">User Action</span></span>  
 <span data-ttu-id="b76fb-122">Ridurre la complessità della query rimuovendo le funzioni di aggregazione o i join.</span><span class="sxs-lookup"><span data-stu-id="b76fb-122">Decrease the complexity of the query by removing joins or aggregate functions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b76fb-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b76fb-123">See Also</span></span>  
 [<span data-ttu-id="b76fb-124">OLTP in memoria &#40;ottimizzazione per la memoria&#41;</span><span class="sxs-lookup"><span data-stu-id="b76fb-124">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
