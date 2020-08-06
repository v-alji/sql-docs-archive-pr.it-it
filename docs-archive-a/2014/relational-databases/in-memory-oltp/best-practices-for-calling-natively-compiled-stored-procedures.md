---
title: Procedure consigliate per chiamare stored procedure compilate in modo nativo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: f39fc1c7-cfec-4a95-97f6-6b95954694bb
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: d07d0e290d1fbd9b324235e64734a399bf7801d3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624709"
---
# <a name="best-practices-for-calling-natively-compiled-stored-procedures"></a><span data-ttu-id="6c46c-102">Procedure consigliate per chiamare stored procedure compilate in modo nativo</span><span class="sxs-lookup"><span data-stu-id="6c46c-102">Best Practices for Calling Natively Compiled Stored Procedures</span></span>
  <span data-ttu-id="6c46c-103">Le stored procedure compilate in modo nativo:</span><span class="sxs-lookup"><span data-stu-id="6c46c-103">Natively compiled stored procedures are:</span></span>  
  
-   <span data-ttu-id="6c46c-104">Vengono in genere utilizzate nelle parti critiche per le prestazioni di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="6c46c-104">Used typically in performance-critical parts of an application.</span></span>  
  
-   <span data-ttu-id="6c46c-105">Vengono eseguite di frequente.</span><span class="sxs-lookup"><span data-stu-id="6c46c-105">Frequently executed.</span></span>  
  
-   <span data-ttu-id="6c46c-106">Devono essere molto veloci.</span><span class="sxs-lookup"><span data-stu-id="6c46c-106">Expected to be very fast.</span></span>  
  
 <span data-ttu-id="6c46c-107">Il vantaggio a livello di prestazioni garantito dall'utilizzo di una stored procedure compilata in modo nativo aumenta con il numero di righe e la quantità di logica elaborata dalla procedura.</span><span class="sxs-lookup"><span data-stu-id="6c46c-107">The performance benefit of using a natively compiled stored procedure increases with the number of rows and the amount of logic that is processed by the procedure.</span></span> <span data-ttu-id="6c46c-108">Ad esempio, tramite una stored procedure compilata in modo nativo vengono garantite prestazioni migliori se si utilizzato uno o più degli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="6c46c-108">For example, a natively compiled stored procedure will exhibit better performance if it uses one or more of the following:</span></span>  
  
-   <span data-ttu-id="6c46c-109">Aggregazione.</span><span class="sxs-lookup"><span data-stu-id="6c46c-109">Aggregation.</span></span>  
  
-   <span data-ttu-id="6c46c-110">Join a cicli annidati.</span><span class="sxs-lookup"><span data-stu-id="6c46c-110">Nested-loops joins.</span></span>  
  
-   <span data-ttu-id="6c46c-111">Operazioni di selezione, inserimento, aggiornamento ed eliminazione a più istruzioni.</span><span class="sxs-lookup"><span data-stu-id="6c46c-111">Multi-statement select, insert, update, and delete operations.</span></span>  
  
-   <span data-ttu-id="6c46c-112">Espressioni complesse.</span><span class="sxs-lookup"><span data-stu-id="6c46c-112">Complex expressions.</span></span>  
  
-   <span data-ttu-id="6c46c-113">Logica procedurale, ad esempio cicli e istruzioni condizionali.</span><span class="sxs-lookup"><span data-stu-id="6c46c-113">Procedural logic, such as conditional statements and loops.</span></span>  
  
 <span data-ttu-id="6c46c-114">Se è necessario elaborare una sola riga, l'utilizzo di una stored procedure compilata in modo nativo non può garantire un vantaggio in termini di prestazioni.</span><span class="sxs-lookup"><span data-stu-id="6c46c-114">If you need to process only a single row, using a natively compiled stored procedure may not provide a performance benefit.</span></span>  
  
 <span data-ttu-id="6c46c-115">Per evitare che nel server debbano essere eseguiti il mapping dei nomi di parametro e la conversione dei tipi:</span><span class="sxs-lookup"><span data-stu-id="6c46c-115">To avoid the server having to map parameter names and convert types:</span></span>  
  
-   <span data-ttu-id="6c46c-116">Associare i tipi dei parametri passati alla stored procedure ai tipi nella definizione della stored procedure.</span><span class="sxs-lookup"><span data-stu-id="6c46c-116">Match the types of the parameters passed to the procedure with the types in the procedure definition.</span></span>  
  
-   <span data-ttu-id="6c46c-117">Utilizzare i parametri ordinali (senza nome) per chiamare le stored procedure compilate in modo nativo.</span><span class="sxs-lookup"><span data-stu-id="6c46c-117">Use ordinal (nameless) parameters when calling natively compiled stored procedures.</span></span> <span data-ttu-id="6c46c-118">Per un'esecuzione ottimale, non utilizzare parametri denominati.</span><span class="sxs-lookup"><span data-stu-id="6c46c-118">For the most efficient execution, do not use named parameters.</span></span>  
  
 <span data-ttu-id="6c46c-119">L'utilizzo di parametri denominati (inefficiente) con stored procedure compilate in modo nativo può essere rilevato tramite l'XEvent `hekaton_slow_parameter_passing` con `reason=named_parameters`.</span><span class="sxs-lookup"><span data-stu-id="6c46c-119">Use of (inefficient) named parameters with natively compiled stored procedures can be detected through the XEvent `hekaton_slow_parameter_passing`, with `reason=named_parameters`.</span></span>  
  
 <span data-ttu-id="6c46c-120">In modo analogo è possibile rilevare l'utilizzo di tipi non corrispondenti tramite lo stesso XEvent `hekaton_slow_parameter_passing` con `reason=parameter_conversion`.</span><span class="sxs-lookup"><span data-stu-id="6c46c-120">Similarly, you can detect use of mismatched types through the same XEvent `hekaton_slow_parameter_passing`, with `reason=parameter_conversion`.</span></span>  
  
 <span data-ttu-id="6c46c-121">Poiché è necessario implementare la logica per eseguire nuovi tentativi quando si utilizzano le tabelle ottimizzate per la memoria (in molti scenari) e poiché è necessario aggirare le limitazioni di alcune funzionalità, è possibile creare una stored procedure [!INCLUDE[tsql](../../includes/tsql-md.md)] interpretata dal wrapper.</span><span class="sxs-lookup"><span data-stu-id="6c46c-121">Because you will need to implement retry logic when using memory-optimized tables (in many scenarios), and because you will need to work around certain feature limitations, you may want to create a wrapper interpreted [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedure.</span></span> <span data-ttu-id="6c46c-122">Per un esempio, vedere [linee guida per la logica di ripetizione dei tentativi per le transazioni nelle tabelle ottimizzate](memory-optimized-tables.md)per la memoria.</span><span class="sxs-lookup"><span data-stu-id="6c46c-122">For an example, see [Guidelines for Retry Logic for Transactions on Memory-Optimized Tables](memory-optimized-tables.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c46c-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6c46c-123">See Also</span></span>  
 [<span data-ttu-id="6c46c-124">Stored procedure compilate in modo nativo</span><span class="sxs-lookup"><span data-stu-id="6c46c-124">Natively Compiled Stored Procedures</span></span>](natively-compiled-stored-procedures.md)  
  
  
