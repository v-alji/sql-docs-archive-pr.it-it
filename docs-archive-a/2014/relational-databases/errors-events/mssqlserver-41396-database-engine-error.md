---
title: MSSQLSERVER_41396 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 41396 (Database Engine error)
ms.assetid: 4ff04042-8367-46f3-8a16-c94682d6eedb
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2386c805b61631c9b843753d74ba6616e7344223
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715300"
---
# <a name="mssqlserver_41396"></a><span data-ttu-id="0507f-102">MSSQLSERVER_41396</span><span class="sxs-lookup"><span data-stu-id="0507f-102">MSSQLSERVER_41396</span></span>
    
## <a name="details"></a><span data-ttu-id="0507f-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="0507f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0507f-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="0507f-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="0507f-105">ID evento</span><span class="sxs-lookup"><span data-stu-id="0507f-105">Event ID</span></span>|<span data-ttu-id="0507f-106">41396</span><span class="sxs-lookup"><span data-stu-id="0507f-106">41396</span></span>|  
|<span data-ttu-id="0507f-107">Origine evento</span><span class="sxs-lookup"><span data-stu-id="0507f-107">Event Source</span></span>|<span data-ttu-id="0507f-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="0507f-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="0507f-109">Componente</span><span class="sxs-lookup"><span data-stu-id="0507f-109">Component</span></span>|<span data-ttu-id="0507f-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="0507f-110">SQLEngine</span></span>|  
|<span data-ttu-id="0507f-111">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="0507f-111">Symbolic Name</span></span>|<span data-ttu-id="0507f-112">MAX_SORT_ROWS_EXCEEDED</span><span class="sxs-lookup"><span data-stu-id="0507f-112">MAX_SORT_ROWS_EXCEEDED</span></span>|  
|<span data-ttu-id="0507f-113">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="0507f-113">Message Text</span></span>|<span data-ttu-id="0507f-114">L'operazione di ordinamento ha superato il limite del buffer.</span><span class="sxs-lookup"><span data-stu-id="0507f-114">The sort operation exceeded the buffer limit.</span></span> <span data-ttu-id="0507f-115">L'esecuzione della stored procedure è stata interrotta.</span><span class="sxs-lookup"><span data-stu-id="0507f-115">The stored procedure execution was aborted.</span></span> <span data-ttu-id="0507f-116">Per ulteriori informazioni, vedere la documentazione online di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0507f-116">Consult SQL Server Books Online for more information.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0507f-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="0507f-117">Explanation</span></span>  
 <span data-ttu-id="0507f-118">Le stored procedure compilate in modo nativo eseguono le operazioni di ordinamento in memoria.</span><span class="sxs-lookup"><span data-stu-id="0507f-118">Natively compiled stored procedures perform sort operations in memory.</span></span> <span data-ttu-id="0507f-119">Esiste un limite di dimensioni nel buffer di ordinamento.</span><span class="sxs-lookup"><span data-stu-id="0507f-119">There is a limit on the size of the sort buffer.</span></span> <span data-ttu-id="0507f-120">Questo errore indica che la dimensione del buffer di ordinamento supera questo limite.</span><span class="sxs-lookup"><span data-stu-id="0507f-120">This error means that the size of the sort buffer exceeds this limit.</span></span> <span data-ttu-id="0507f-121">L'esecuzione della stored procedure e dell'operazione di ordinamento è stata interrotta.</span><span class="sxs-lookup"><span data-stu-id="0507f-121">The sort operation and the stored procedure execution aborted.</span></span>  
  
 <span data-ttu-id="0507f-122">Le dimensioni di ciascuna riga o voce nel buffer di ordinamento sono determinate dal numero di righe ordinate nonché dal numero di join e dal numero di funzioni di aggregazioni nella query.</span><span class="sxs-lookup"><span data-stu-id="0507f-122">The size of each row or entry in the sort buffer is determined by the number of rows sorted as well as the number of joins and the number and type of aggregate functions in the query.</span></span> <span data-ttu-id="0507f-123">Attraverso la semplificazione della query è possibile ridurre le dimensioni di ciascuna riga permettendo così di adattare un numero maggiore di righe nel buffer di ordinamento.</span><span class="sxs-lookup"><span data-stu-id="0507f-123">By simplifying the query, you can reduce the size of each row thereby fitting more rows in the sort buffer.</span></span> <span data-ttu-id="0507f-124">Le dimensioni delle righe nelle tabelle di base non influiscono sulle dimensioni di ciascuna riga o voce nel buffer di ordinamento.</span><span class="sxs-lookup"><span data-stu-id="0507f-124">The size of the rows in the base tables does not affect the size of each row or entry in the sort buffer.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0507f-125">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="0507f-125">User Action</span></span>  
 <span data-ttu-id="0507f-126">Selezionare alcune righe o ridurre la complessità della query rimuovendo i join o le funzioni di aggregazione.</span><span class="sxs-lookup"><span data-stu-id="0507f-126">Select fewer rows or decrease the complexity of the query by removing joins or aggregate functions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0507f-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0507f-127">See Also</span></span>  
 [<span data-ttu-id="0507f-128">OLTP in memoria &#40;ottimizzazione per la memoria&#41;</span><span class="sxs-lookup"><span data-stu-id="0507f-128">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
