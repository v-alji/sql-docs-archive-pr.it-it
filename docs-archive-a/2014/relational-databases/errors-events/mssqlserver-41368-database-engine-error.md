---
title: MSSQLSERVER_41368 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 41368 (Database Engine error)
ms.assetid: abc71559-4c4d-4cce-a08f-3299dd167842
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 10e187223a3f35b4b21ede6965e3c9efea2e30c1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715308"
---
# <a name="mssqlserver_41368"></a><span data-ttu-id="ded10-102">MSSQLSERVER_41368</span><span class="sxs-lookup"><span data-stu-id="ded10-102">MSSQLSERVER_41368</span></span>
    
## <a name="details"></a><span data-ttu-id="ded10-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="ded10-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ded10-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="ded10-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="ded10-105">ID evento</span><span class="sxs-lookup"><span data-stu-id="ded10-105">Event ID</span></span>|<span data-ttu-id="ded10-106">41368</span><span class="sxs-lookup"><span data-stu-id="ded10-106">41368</span></span>|  
|<span data-ttu-id="ded10-107">Origine evento</span><span class="sxs-lookup"><span data-stu-id="ded10-107">Event Source</span></span>|<span data-ttu-id="ded10-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="ded10-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="ded10-109">Componente</span><span class="sxs-lookup"><span data-stu-id="ded10-109">Component</span></span>|<span data-ttu-id="ded10-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="ded10-110">SQLEngine</span></span>|  
|<span data-ttu-id="ded10-111">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="ded10-111">Symbolic Name</span></span>|<span data-ttu-id="ded10-112">SQL_IMPLICIT_AND_EXPLICIT_TX_NOT_SUPPORTED</span><span class="sxs-lookup"><span data-stu-id="ded10-112">SQL_IMPLICIT_AND_EXPLICIT_TX_NOT_SUPPORTED</span></span>|  
|<span data-ttu-id="ded10-113">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="ded10-113">Message Text</span></span>|<span data-ttu-id="ded10-114">L'accesso alle tabelle con ottimizzazione per la memoria utilizzando il livello di isolamento READ COMMITTED è supportato solo per transazioni in modalità autocommit.</span><span class="sxs-lookup"><span data-stu-id="ded10-114">Accessing memory optimized tables using the READ COMMITTED isolation level is supported only for autocommit transactions.</span></span> <span data-ttu-id="ded10-115">Non è invece supportato con le transazioni implicite o esplicite.</span><span class="sxs-lookup"><span data-stu-id="ded10-115">It is not supported for explicit or implicit transactions.</span></span> <span data-ttu-id="ded10-116">Specificare un livello di isolamento supportato per la tabella con ottimizzazione per la memoria utilizzando un hint di tabella, ad esempio WITH (SNAPSHOT).</span><span class="sxs-lookup"><span data-stu-id="ded10-116">Provide a supported isolation level for the memory optimized table using a table hint, such as WITH (SNAPSHOT).</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ded10-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="ded10-117">Explanation</span></span>  
 <span data-ttu-id="ded10-118">L'accesso alle tabelle ottimizzate per la memoria utilizzando il livello di isolamento READ COMMITTED è supportato solo per transazioni in modalità autocommit.</span><span class="sxs-lookup"><span data-stu-id="ded10-118">Accessing memory-optimized tables using the READ COMMITTED isolation level is supported only for autocommit transactions.</span></span> <span data-ttu-id="ded10-119">Per altre informazioni, vedere [Transaction Isolation Levels](../../database-engine/transaction-isolation-levels.md).</span><span class="sxs-lookup"><span data-stu-id="ded10-119">For more information, see [Transaction Isolation Levels](../../database-engine/transaction-isolation-levels.md).</span></span>  
  
 <span data-ttu-id="ded10-120">Quando si accede a una tabella ottimizzata per la memoria da una transazione esplicita avviata tramite un'istruzione BEGIN TRANSACTION o da una transazione implicita, se l'opzione IMPLICIT_TRANSACTIONS è impostata su ON, il livello di isolamento READ COMMITTED non è supportato.</span><span class="sxs-lookup"><span data-stu-id="ded10-120">When accessing a memory-optimized table from an explicit transaction that was started with BEGIN TRANSACTION, or from an implicit transaction, if IMPLICIT_TRANSACTIONS is set to ON, the READ COMMITTED isolation level is not supported.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ded10-121">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="ded10-121">User Action</span></span>  
 <span data-ttu-id="ded10-122">Quando si accede a una tabella ottimizzata per la memoria da una transazione esplicita o implicita READ COMMITTED, utilizzare l'istruzione SNAPSHOT per accedere alla tabella.</span><span class="sxs-lookup"><span data-stu-id="ded10-122">When accessing a memory-optimized table from an explicit or implicit READ COMMITTED transaction, use SNAPSHOT to access the table.</span></span> <span data-ttu-id="ded10-123">Questa operazione può essere eseguita tramite l'hint di tabella WITH (SNAPSHOT) (per ulteriori informazioni, vedere [linee guida per i livelli di isolamento delle transazioni con tabelle ottimizzate per la memoria](../in-memory-oltp/memory-optimized-tables.md)) oppure impostando l'opzione di database MEMORY_OPTIMIZED_ELEVATE_TO_SNAPSHOT su on (per ulteriori informazioni, vedere [Opzioni ALTER database set &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options)).</span><span class="sxs-lookup"><span data-stu-id="ded10-123">This can be achieved by using the table hint WITH (SNAPSHOT) (for more information, see [Guidelines for Transaction Isolation Levels with Memory-Optimized Tables](../in-memory-oltp/memory-optimized-tables.md)) or by setting the database option MEMORY_OPTIMIZED_ELEVATE_TO_SNAPSHOT to ON (for more information, see [ALTER DATABASE SET Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ded10-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ded10-124">See Also</span></span>  
 [<span data-ttu-id="ded10-125">OLTP in memoria &#40;ottimizzazione per la memoria&#41;</span><span class="sxs-lookup"><span data-stu-id="ded10-125">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
