---
title: Compilazione di set denominati in MDX (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Multidimensional Expressions [Analysis Services], named sets
- named sets [MDX]
- sets [MDX]
- MDX [Analysis Services], named sets
- queries [MDX], named sets
- set expressions [MDX]
ms.assetid: 213b0035-e96d-4ba0-83f2-ded206905603
author: minewiskan
ms.author: owend
ms.openlocfilehash: 91296f8c5d47afb15c67f0b60435c7f961734573
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714652"
---
# <a name="building-named-sets-in-mdx-mdx"></a><span data-ttu-id="80c26-102">Compilazione di set denominati in MDX (MDX)</span><span class="sxs-lookup"><span data-stu-id="80c26-102">Building Named Sets in MDX (MDX)</span></span>
  <span data-ttu-id="80c26-103">Un'espressione set può essere costituita da una dichiarazione lunga e complessa e risultare pertanto difficile da seguire o comprendere</span><span class="sxs-lookup"><span data-stu-id="80c26-103">A set expression can be a lengthy and complex declaration, and therefore be difficult to follow or understand.</span></span> <span data-ttu-id="80c26-104">oppure essere utilizzata con tale frequenza che la presenza di definizioni ripetute del set può creare confusione.</span><span class="sxs-lookup"><span data-stu-id="80c26-104">Or, a set expression may be used so frequently that repeatedly defining the set becomes burdensome.</span></span> <span data-ttu-id="80c26-105">Per semplificare l'utilizzo di espressioni lunghe, complesse o usate di frequente, le espressioni MDX (Multidimensional Expressions) consentono di definire un'espressione di questo tipo come *set denominato*.</span><span class="sxs-lookup"><span data-stu-id="80c26-105">To help make working with a lengthy, complex or commonly used expression easier, Multidimensional Expressions (MDX) lets you such an expression as a *named set*.</span></span>  
  
 <span data-ttu-id="80c26-106">Un set denominato è essenzialmente un'espressione set a cui è stato assegnato un alias.</span><span class="sxs-lookup"><span data-stu-id="80c26-106">Basically, a named set is a set expression to which an alias has been assigned.</span></span> <span data-ttu-id="80c26-107">Un set denominato può incorporare qualsiasi funzione o membro che è normalmente possibile incorporare in un set.</span><span class="sxs-lookup"><span data-stu-id="80c26-107">A named set can incorporate any members or functions that can ordinarily be incorporated into a set.</span></span> <span data-ttu-id="80c26-108">Poiché in MDX gli alias dei set denominati vengono gestiti come espressioni set, è possibile utilizzare tali alias in tutte le situazioni in cui è consentito utilizzare un'espressione set.</span><span class="sxs-lookup"><span data-stu-id="80c26-108">Because MDX treats the named set alias as a set expression, you can use that alias anywhere a set expression is accepted.</span></span>  
  
 <span data-ttu-id="80c26-109">Un set denominato può essere definito con uno dei contesti seguenti:</span><span class="sxs-lookup"><span data-stu-id="80c26-109">You can define a named set to have one of the following contexts:</span></span>  
  
-   <span data-ttu-id="80c26-110">**Ambito query** Per creare un set denominato definito come parte di una query MDX, pertanto con ambito limitato alla query, è necessario usare la parola chiave WITH.</span><span class="sxs-lookup"><span data-stu-id="80c26-110">**Query-scoped** To create a named set that is defined as part of an MDX query, and therefore whose scope is limited to the query, you use the WITH keyword.</span></span> <span data-ttu-id="80c26-111">Tale set denominato può essere quindi utilizzato in un'istruzione MDX SELECT.</span><span class="sxs-lookup"><span data-stu-id="80c26-111">You can then use the named set within an MDX SELECT statement.</span></span> <span data-ttu-id="80c26-112">In questo modo il set denominato creato utilizzando la parola chiave WITH può essere modificato senza alterare l'istruzione SELECT.</span><span class="sxs-lookup"><span data-stu-id="80c26-112">Using this approach, the named set created by using the WITH keyword can be changed without disturbing the SELECT statement.</span></span>  
  
     <span data-ttu-id="80c26-113">Per altre informazioni sull'uso della parola chiave WITH per la creazione di set denominati, vedere [Creazione di set denominati con ambito query &#40;MDX&#41;](mdx-named-sets-creating-query-scoped-named-sets.md).</span><span class="sxs-lookup"><span data-stu-id="80c26-113">For more information about how to use the WITH keyword to create named sets, see [Creating Query-Scoped Named Sets &#40;MDX&#41;](mdx-named-sets-creating-query-scoped-named-sets.md).</span></span>  
  
-   <span data-ttu-id="80c26-114">**Ambito sessione** Per creare un set denominato con ambito più ampio rispetto al contesto della query, ovvero con ambito corrispondente alla durata della sessione MDX, è possibile usare l'istruzione CREATE SET.</span><span class="sxs-lookup"><span data-stu-id="80c26-114">**Session-scoped** To create a named set whose scope is wider than the context of the query, that is, whose scope is the lifetime of the MDX session, you use the CREATE SET statement.</span></span> <span data-ttu-id="80c26-115">Un set denominato definito utilizzando un'istruzione CREATE SET è disponibile per tutte le query MDX in tale sessione.</span><span class="sxs-lookup"><span data-stu-id="80c26-115">A named set defined by using the CREATE SET statement is available to all MDX queries in that session.</span></span> <span data-ttu-id="80c26-116">L'istruzione CREATE SET risulta utile, ad esempio, in un'applicazione client che riutilizza in modo consistente un set in vari tipi di query.</span><span class="sxs-lookup"><span data-stu-id="80c26-116">The CREATE SET statement makes sense, for example, in a client application that consistently reuses a set in a variety of queries.</span></span>  
  
     <span data-ttu-id="80c26-117">Per altre informazioni sull'uso dell'istruzione CREATE SET per la creazione di set denominati in una sessione, vedere [Creazione di set denominati con ambito sessione &#40;MDX&#41;](mdx-named-sets-creating-session-scoped-named-sets.md).</span><span class="sxs-lookup"><span data-stu-id="80c26-117">For more information about how to use the CREATE SET statement to create named sets in a session, see [Creating Session-Scoped Named Sets &#40;MDX&#41;](mdx-named-sets-creating-session-scoped-named-sets.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80c26-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="80c26-118">See Also</span></span>  
 <span data-ttu-id="80c26-119">[Istruzione SELECT &#40;MDX&#41;](/sql/mdx/mdx-data-manipulation-select) </span><span class="sxs-lookup"><span data-stu-id="80c26-119">[SELECT Statement &#40;MDX&#41;](/sql/mdx/mdx-data-manipulation-select) </span></span>  
 <span data-ttu-id="80c26-120">[Istruzione CREATE SET &#40;MDX&#41;](/sql/mdx/mdx-data-definition-create-set) </span><span class="sxs-lookup"><span data-stu-id="80c26-120">[CREATE SET Statement &#40;MDX&#41;](/sql/mdx/mdx-data-definition-create-set) </span></span>  
 [<span data-ttu-id="80c26-121">Nozioni fondamentali sulle query MDX &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="80c26-121">MDX Query Fundamentals &#40;Analysis Services&#41;</span></span>](mdx-query-fundamentals-analysis-services.md)  
  
  
