---
title: Compilazione di membri calcolati in MDX (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- MDX [Analysis Services], calculated members
- calculated members [MDX]
- Multidimensional Expressions [Analysis Services], calculated members
- queries [MDX], calculated members
ms.assetid: 9322e8b8-43e1-4e02-a7d1-e41a586a5bb8
author: minewiskan
ms.author: owend
ms.openlocfilehash: 30dc6562ec394065cf2f177608d4e5679cbd7df3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627440"
---
# <a name="building-calculated-members-in-mdx-mdx"></a><span data-ttu-id="95d8e-102">Compilazione di membri calcolati in MDX</span><span class="sxs-lookup"><span data-stu-id="95d8e-102">Building Calculated Members in MDX (MDX)</span></span>
  <span data-ttu-id="95d8e-103">In MDX (Multidimensional Expressions) un membro calcolato viene definito come membro che è stato risolto tramite il calcolo di un'espressione MDX per la restituzione di un valore.</span><span class="sxs-lookup"><span data-stu-id="95d8e-103">In Multidimensional Expressions (MDX), a calculated member is a member that is resolved by calculating an MDX expression to return a value.</span></span> <span data-ttu-id="95d8e-104">Dietro a questa definizione apparentemente semplice si nasconde un'enorme quantità di informazioni.</span><span class="sxs-lookup"><span data-stu-id="95d8e-104">This innocuous definition covers an incredible amount of ground.</span></span> <span data-ttu-id="95d8e-105">La capacità di creare e utilizzare membri calcolati in una query MDX offre capacità notevoli per la manipolazione dei dati multidimensionali.</span><span class="sxs-lookup"><span data-stu-id="95d8e-105">The ability to construct and use calculated members in an MDX query provides a great deal of manipulation capability for multidimensional data.</span></span>  
  
 <span data-ttu-id="95d8e-106">I membri calcolati possono essere creati in qualsiasi posizione di una gerarchia.</span><span class="sxs-lookup"><span data-stu-id="95d8e-106">You can create calculated members at any point within a hierarchy.</span></span> <span data-ttu-id="95d8e-107">È inoltre possibile creare membri calcolati dipendenti non solo dai membri esistenti di un cubo, ma anche da altri membri calcolati definiti nella stessa espressione MDX.</span><span class="sxs-lookup"><span data-stu-id="95d8e-107">You can also create calculated members that depend not only on existing members in a cube, but also on other calculated members defined in the same MDX expression.</span></span>  
  
 <span data-ttu-id="95d8e-108">È possibile definire un membro calcolato in modo da associarvi uno dei contesti seguenti:</span><span class="sxs-lookup"><span data-stu-id="95d8e-108">You can define a calculated member to have one of the following contexts:</span></span>  
  
-   <span data-ttu-id="95d8e-109">**Con ambito query** Per creare un membro calcolato definito come parte di una query MDX e il cui ambito è pertanto limitato alla query, è necessario specificare la parola chiave WITH.</span><span class="sxs-lookup"><span data-stu-id="95d8e-109">**Query-scoped** To create a calculated member that is defined as part of an MDX query, and therefore whose scope is limited to the query, you use the WITH keyword.</span></span> <span data-ttu-id="95d8e-110">Il membro calcolato può essere utilizzato quindi in un'istruzione MDX SELECT.</span><span class="sxs-lookup"><span data-stu-id="95d8e-110">You can then use the calculated member within an MDX SELECT statement.</span></span> <span data-ttu-id="95d8e-111">In tal modo, è possibile modificare il membro calcolato creato utilizzando la parola chiave WITH senza alterare l'istruzione SELECT.</span><span class="sxs-lookup"><span data-stu-id="95d8e-111">Using this approach, the calculated member created by using the WITH keyword can be changed without disturbing the SELECT statement.</span></span>  
  
     <span data-ttu-id="95d8e-112">Per altre informazioni sulla creazione di membri calcolati mediante la parola chiave WITH, vedere [Creazione di formule per il calcolo di celle con ambito query &#40;MDX&#41;](mdx-calculated-members-query-scoped-calculated-members.md).</span><span class="sxs-lookup"><span data-stu-id="95d8e-112">For more information about how to use the WITH keyword to create calculated members, see [Creating Query-Scoped Calculated Members &#40;MDX&#41;](mdx-calculated-members-query-scoped-calculated-members.md).</span></span>  
  
-   <span data-ttu-id="95d8e-113">**Con ambito sessione** Per creare un membro calcolato il cui ambito risulti più ampio del contesto della query, ovvero il cui ambito corrisponde alla durata della sessione MDX, è necessario usare l'istruzione CREATE MEMBER.</span><span class="sxs-lookup"><span data-stu-id="95d8e-113">**Session-scoped** To create a calculated member whose scope is wider than the context of the query, that is, whose scope is the lifetime of the MDX session, you use the CREATE MEMBER statement.</span></span> <span data-ttu-id="95d8e-114">I membri calcolati definiti tramite questa istruzione sono disponibili in tutte le query MDX della sessione.</span><span class="sxs-lookup"><span data-stu-id="95d8e-114">A calculated member defined by using the CREATE MEMBER statement is available to all MDX queries in that session.</span></span> <span data-ttu-id="95d8e-115">L'istruzione CREATE MEMBER risulta utile, ad esempio, in un'applicazione client che riutilizza costantemente un set in vari tipi di query.</span><span class="sxs-lookup"><span data-stu-id="95d8e-115">The CREATE MEMBER statement makes sense, for example, in a client application that consistently reuses the same set in a variety of queries.</span></span>  
  
     <span data-ttu-id="95d8e-116">Per altre informazioni sulla creazione di membri calcolati in una sessione tramite l'istruzione CREATE MEMBER, vedere [Creazione di membri calcolati con ambito sessione &#40;MDX&#41;](mdx-calculated-members-session-scoped-calculated-members.md).</span><span class="sxs-lookup"><span data-stu-id="95d8e-116">For more information about how to use the CREATE MEMBER statement to create calculated members in a session, see [Creating Session-Scoped Calculated Members &#40;MDX&#41;](mdx-calculated-members-session-scoped-calculated-members.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95d8e-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="95d8e-117">See Also</span></span>  
 <span data-ttu-id="95d8e-118">[Istruzione CREATE MEMBER &#40;MDX&#41;](/sql/mdx/mdx-data-definition-create-member) </span><span class="sxs-lookup"><span data-stu-id="95d8e-118">[CREATE MEMBER Statement &#40;MDX&#41;](/sql/mdx/mdx-data-definition-create-member) </span></span>  
 <span data-ttu-id="95d8e-119">[Guida di riferimento alle funzioni MDX &#40;&#41;MDX](/sql/mdx/mdx-function-reference-mdx) </span><span class="sxs-lookup"><span data-stu-id="95d8e-119">[MDX Function Reference &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx) </span></span>  
 [<span data-ttu-id="95d8e-120">Istruzione SELECT &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="95d8e-120">SELECT Statement &#40;MDX&#41;</span></span>](/sql/mdx/mdx-data-manipulation-select)  
  
  
