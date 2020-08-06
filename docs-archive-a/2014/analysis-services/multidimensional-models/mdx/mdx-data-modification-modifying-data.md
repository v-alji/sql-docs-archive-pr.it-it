---
title: Modifica di dati (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- modifying data [MDX]
- Multidimensional Expressions [Analysis Services], data modifications
- MDX [Analysis Services], data modifications
- data modifications [MDX]
ms.assetid: 363b662c-b839-4971-bbd7-1842f73ce141
author: minewiskan
ms.author: owend
ms.openlocfilehash: 01df67471753922e3e7db39c56a9ed50aae900dc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629630"
---
# <a name="modifying-data-mdx"></a><span data-ttu-id="29a36-102">Modifica dei dati (MDX)</span><span class="sxs-lookup"><span data-stu-id="29a36-102">Modifying Data (MDX)</span></span>
  <span data-ttu-id="29a36-103">Oltre che per recuperare e gestire i dati di dimensioni e cubi, il linguaggio MDX (Multidimensional Expressions) può essere usato anche per aggiornarli o eseguirne il *writeback* .</span><span class="sxs-lookup"><span data-stu-id="29a36-103">Besides using Multidimensional Expressions (MDX) to retrieve and handle data from dimensions and cubes, you can use MDX to update or *writeback* dimension and cube data.</span></span> <span data-ttu-id="29a36-104">Tali aggiornamenti possono essere temporanei, come nel caso delle analisi speculative, o di simulazione, oppure permanenti, come nel caso in cui le modifiche dipendono dall'analisi dei dati.</span><span class="sxs-lookup"><span data-stu-id="29a36-104">These updates can be temporary, as with speculative, or "what if", analysis, or permanent, as when changes must occur based upon data analysis.</span></span>  
  
 <span data-ttu-id="29a36-105">Gli aggiornamenti possono essere eseguiti a livello di dimensione o di cubo:</span><span class="sxs-lookup"><span data-stu-id="29a36-105">Updates to data can occur at the dimension or cube level:</span></span>  
  
 <span data-ttu-id="29a36-106">**Writeback delle dimensioni**</span><span class="sxs-lookup"><span data-stu-id="29a36-106">**Dimension writebacks**</span></span>  
 <span data-ttu-id="29a36-107">È possibile usare l'istruzione [ALTER CUBE Statement (MDX)](/sql/mdx/mdx-data-definition-alter-cube) per modificare i dati di una dimensione abilitata per la scrittura e [REFRESH CUBE Statement (MDX)](/sql/mdx/mdx-data-definition-refresh-cube) per riflettere l'eliminazione, la creazione e l'aggiornamento dei valori degli attributi.</span><span class="sxs-lookup"><span data-stu-id="29a36-107">You use the [ALTER CUBE Statement (MDX)](/sql/mdx/mdx-data-definition-alter-cube) statement to change a write-enabled dimension's data and the [REFRESH CUBE Statement (MDX)](/sql/mdx/mdx-data-definition-refresh-cube) to reflect the deletion, creation, and updating of attribute values.</span></span> <span data-ttu-id="29a36-108">L'istruzione ALTER CUBE può essere inoltre utilizzata per svolgere operazioni complesse, ad esempio l'eliminazione di un intero sottoalbero di una gerarchia e la promozione dei figli di un membro eliminato.</span><span class="sxs-lookup"><span data-stu-id="29a36-108">You can also use the ALTER CUBE statement to perform complex operations, such as deleting a whole sub-tree in a hierarchy and promoting the children of a deleted member.</span></span>  
  
 <span data-ttu-id="29a36-109">**Writeback dei cubi**</span><span class="sxs-lookup"><span data-stu-id="29a36-109">**Cube writebacks**</span></span>  
 <span data-ttu-id="29a36-110">È possibile usare l'istruzione [UPDATE CUBE](/sql/mdx/mdx-data-manipulation-update-cube) per aggiornare un cubo abilitato per la scrittura.</span><span class="sxs-lookup"><span data-stu-id="29a36-110">You use the [UPDATE CUBE](/sql/mdx/mdx-data-manipulation-update-cube) statement to make updates to a write-enabled cube.</span></span> <span data-ttu-id="29a36-111">L'istruzione UPDATE CUBE consente di aggiornare una tupla con un valore specifico.</span><span class="sxs-lookup"><span data-stu-id="29a36-111">The UPDATE CUBE statement lets you update a tuple with a specific value.</span></span> <span data-ttu-id="29a36-112">È possibile usare l'istruzione [REFRESH CUBE Statement (MDX)](/sql/mdx/mdx-data-definition-refresh-cube) per aggiornare i dati in una sessione client con i dati aggiornati del server.</span><span class="sxs-lookup"><span data-stu-id="29a36-112">You use the [REFRESH CUBE Statement (MDX)](/sql/mdx/mdx-data-definition-refresh-cube) to refresh data in a client session with updated data from the server.</span></span>  
  
 <span data-ttu-id="29a36-113">Per altre informazioni, vedere [Utilizzo dei writeback dei cubi &#40;MDX&#41;](mdx-data-modification-using-cube-writebacks.md).</span><span class="sxs-lookup"><span data-stu-id="29a36-113">For more information, see [Using Cube Writebacks &#40;MDX&#41;](mdx-data-modification-using-cube-writebacks.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29a36-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="29a36-114">See Also</span></span>  
 [<span data-ttu-id="29a36-115">Nozioni fondamentali sulle query MDX &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="29a36-115">MDX Query Fundamentals &#40;Analysis Services&#41;</span></span>](mdx-query-fundamentals-analysis-services.md)  
  
  
