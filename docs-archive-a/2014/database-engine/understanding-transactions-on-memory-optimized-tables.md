---
title: Informazioni sulle transazioni nelle tabelle ottimizzate per la memoria | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 06075248-705e-4563-9371-b64cd609793c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0671bba8b7a0bda27ea27cf059cb9e3b1bb87b2b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716571"
---
# <a name="understanding-transactions-on-memory-optimized-tables"></a><span data-ttu-id="97896-102">Informazioni sulle transazioni in tabelle con ottimizzazione per la memoria</span><span class="sxs-lookup"><span data-stu-id="97896-102">Understanding Transactions on Memory-Optimized Tables</span></span>
  <span data-ttu-id="97896-103">Le transazioni accedono a tabelle ottimizzate per la memoria tramite una forma di controllo della concorrenza ottimistica con più versioni.</span><span class="sxs-lookup"><span data-stu-id="97896-103">Transactions access memory-optimized tables using a form of optimistic, multi-version concurrency control.</span></span> <span data-ttu-id="97896-104">Ciò significa che sono presenti versioni diverse dei dati.</span><span class="sxs-lookup"><span data-stu-id="97896-104">This means that there are different versions of the data.</span></span> <span data-ttu-id="97896-105">Ogni transazione viene eseguita nella propria versione del database coerente a livello di transazione, indipendentemente da altre transazioni in esecuzione simultanea.</span><span class="sxs-lookup"><span data-stu-id="97896-105">Each transaction operates on its own transactionally consistent version of the database, independent from other concurrently running transactions.</span></span> <span data-ttu-id="97896-106">Le transazioni vengono inoltre eseguite nel presupposto ottimistico che non saranno presenti conflitti con altre transazioni simultanee,</span><span class="sxs-lookup"><span data-stu-id="97896-106">In addition, transactions operate under the optimistic assumption that there will be no conflicts with other, concurrent, transactions.</span></span> <span data-ttu-id="97896-107">evitando in tal modo la necessità di utilizzare blocchi, ma richiedendo il rilevamento automatico di conflitti e l'interruzione di una delle transazioni in conflitto.</span><span class="sxs-lookup"><span data-stu-id="97896-107">This avoids the need to use locks, but does require the system to detect conflicts and terminate one of the conflicting transactions.</span></span> <span data-ttu-id="97896-108">I conflitti possono verificarsi solo per le transazioni di scrittura-scrittura e per le transazioni di lettura e scrittura.</span><span class="sxs-lookup"><span data-stu-id="97896-108">Conflicts can occur only for write-write transactions and for read-write transactions.</span></span> <span data-ttu-id="97896-109">Se si verifica un conflitto di scrittura-scrittura, una transazione di scrittura viene terminata.</span><span class="sxs-lookup"><span data-stu-id="97896-109">If there is a write-write conflict, one write transaction is terminated.</span></span>  
  
 <span data-ttu-id="97896-110">Esistono analogie tra il controllo della concorrenza per le tabelle ottimizzate per la memoria e il controllo della concorrenza per le tabelle basate su disco per i livelli di isolamento delle transazioni READ_COMMITTED_SNAPSHOT e SNAPSHOT.</span><span class="sxs-lookup"><span data-stu-id="97896-110">There are similarities between the concurrency control for memory-optimized tables and the concurrency control for disk-based tables for the READ_COMMITTED_SNAPSHOT and SNAPSHOT transaction isolation levels.</span></span> <span data-ttu-id="97896-111">Per ulteriori informazioni sulle tabelle basate su disco, vedere [livelli di isolamento basati sul controllo delle versioni delle righe nella motore di database](https://msdn.microsoft.com/library/ms177404\(v=sql.100\).aspx).</span><span class="sxs-lookup"><span data-stu-id="97896-111">(For more information about disk-based tables, see [Row Versioning-based Isolation Levels in the Database Engine](https://msdn.microsoft.com/library/ms177404\(v=sql.100\).aspx).)</span></span>  
  
## <a name="topics-in-this-section"></a><span data-ttu-id="97896-112">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="97896-112">Topics in This Section</span></span>  
 <span data-ttu-id="97896-113">In questa sezione sulle transazioni in tabelle ottimizzate per la memoria sono inclusi gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="97896-113">This section on transactions in memory-optimized tables includes the following topics:</span></span>  
  
-   [<span data-ttu-id="97896-114">Linee guida per i livelli di isolamento delle transazioni con tabelle con ottimizzazione per la memoria</span><span class="sxs-lookup"><span data-stu-id="97896-114">Guidelines for Transaction Isolation Levels with Memory-Optimized Tables</span></span>](../relational-databases/in-memory-oltp/memory-optimized-tables.md)  
  
-   [<span data-ttu-id="97896-115">Linee guida per la logica di riesecuzione per le transazioni in tabelle con ottimizzazione per la memoria</span><span class="sxs-lookup"><span data-stu-id="97896-115">Guidelines for Retry Logic for Transactions on Memory-Optimized Tables</span></span>](guidelines-for-retry-logic-for-transactions-on-memory-optimized-tables.md)  
  
-   [<span data-ttu-id="97896-116">Transazioni in tabelle con ottimizzazione per la memoria</span><span class="sxs-lookup"><span data-stu-id="97896-116">Transactions in Memory-Optimized Tables</span></span>](transactions-in-memory-optimized-tables.md)  
  
-   [<span data-ttu-id="97896-117">Livelli di isolamento delle transazioni</span><span class="sxs-lookup"><span data-stu-id="97896-117">Transaction Isolation Levels</span></span>](transaction-isolation-levels.md)  
  
-   [<span data-ttu-id="97896-118">Transazioni tra contenitori</span><span class="sxs-lookup"><span data-stu-id="97896-118">Cross-Container Transactions</span></span>](cross-container-transactions.md)  
  
 <span data-ttu-id="97896-119">Per altre informazioni, vedere [Controllo della durabilità delle transazioni](../relational-databases/logs/control-transaction-durability.md).</span><span class="sxs-lookup"><span data-stu-id="97896-119">For more information, see [Control Transaction Durability](../relational-databases/logs/control-transaction-durability.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97896-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="97896-120">See Also</span></span>  
 [<span data-ttu-id="97896-121">Tabelle ottimizzate per la memoria</span><span class="sxs-lookup"><span data-stu-id="97896-121">Memory-Optimized Tables</span></span>](../relational-databases/in-memory-oltp/memory-optimized-tables.md)  
  
  
