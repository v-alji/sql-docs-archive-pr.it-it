---
title: Creazione e utilizzo di valori di proprietà (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- property values [MDX]
- queries [MDX], property values
- MDX [Analysis Services], property values
- Multidimensional Expressions [Analysis Services], property values
ms.assetid: 0cafb269-03c8-4183-b6e9-220f071e4ef2
author: minewiskan
ms.author: owend
ms.openlocfilehash: 67eadc6bc2f0bf6f318f20ad42a5cc9e7a5afa5e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629651"
---
# <a name="creating-and-using-property-values-mdx"></a><span data-ttu-id="0ef08-102">Creazione e utilizzo di valori di proprietà (MDX)</span><span class="sxs-lookup"><span data-stu-id="0ef08-102">Creating and Using Property Values (MDX)</span></span>
  <span data-ttu-id="0ef08-103">Le espressioni MDX (Multidimensional Expressions) supportano proprietà intrinseche e definite dall'utente per dimensioni, livelli, membri e celle.</span><span class="sxs-lookup"><span data-stu-id="0ef08-103">Multidimensional Expressions (MDX) supports intrinsic and user-defined properties for dimensions, levels, members, and cells.</span></span> <span data-ttu-id="0ef08-104">Le proprietà intrinseche consentono di specificare nomi univoci, didascalie e persino attributi di formattazione e dimensione del carattere per le singole celle.</span><span class="sxs-lookup"><span data-stu-id="0ef08-104">The intrinsic properties provide unique names, captions, and even formatting and font sizes for individual cells.</span></span> <span data-ttu-id="0ef08-105">Le proprietà definite dall'utente consentono invece di assegnare ai membri pressoché qualsiasi tipo di attributo aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="0ef08-105">User-defined properties, on the other hand, can provide almost any kind of additional attribute to members.</span></span>  
  
 <span data-ttu-id="0ef08-106">Le proprietà intrinseche e definite dall'utente sono disponibili ai livelli seguenti:</span><span class="sxs-lookup"><span data-stu-id="0ef08-106">Intrinsic and user-defined properties are available at the following levels:</span></span>  
  
 <span data-ttu-id="0ef08-107">**Proprietà del membro**</span><span class="sxs-lookup"><span data-stu-id="0ef08-107">**Member properties**</span></span>  
 <span data-ttu-id="0ef08-108">Le proprietà dei membri contengono informazioni di base su ogni membro di ogni tupla.</span><span class="sxs-lookup"><span data-stu-id="0ef08-108">Member properties cover the basic information about each member in each tuple.</span></span> <span data-ttu-id="0ef08-109">Tali informazioni di base includono il nome del membro, il livello padre, il numero di elementi figli e così via.</span><span class="sxs-lookup"><span data-stu-id="0ef08-109">This basic information includes the member name, parent level, the number of children, and so on.</span></span>  
  
 <span data-ttu-id="0ef08-110">Per informazioni sulle proprietà dei membri e sul relativo uso, vedere [Utilizzo delle proprietà dei membri &#40;MDX&#41;](multidimensional-models/mdx/mdx-member-properties.md).</span><span class="sxs-lookup"><span data-stu-id="0ef08-110">For information about member properties and how to use them, see [Using Member Properties &#40;MDX&#41;](multidimensional-models/mdx/mdx-member-properties.md).</span></span>  
  
 <span data-ttu-id="0ef08-111">**Proprietà delle celle**</span><span class="sxs-lookup"><span data-stu-id="0ef08-111">**Cell properties**</span></span>  
 <span data-ttu-id="0ef08-112">Le proprietà delle celle contengono informazioni sul contenuto e il formato delle celle di un'origine dei dati multidimensionale, ad esempio un cubo.</span><span class="sxs-lookup"><span data-stu-id="0ef08-112">Cell properties contain information about the content and format of cells in a multidimensional data source, such as a cube.</span></span>  
  
 <span data-ttu-id="0ef08-113">Per altre informazioni sulle proprietà delle celle e sul relativo uso, vedere [Utilizzo delle proprietà delle celle &#40;MDX&#41;](multidimensional-models/mdx/mdx-cell-properties-using-cell-properties.md).</span><span class="sxs-lookup"><span data-stu-id="0ef08-113">For more information about cell properties and how to use them, see [Using Cell Properties &#40;MDX&#41;](multidimensional-models/mdx/mdx-cell-properties-using-cell-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ef08-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0ef08-114">See Also</span></span>  
 [<span data-ttu-id="0ef08-115">Nozioni fondamentali sulle query MDX &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="0ef08-115">MDX Query Fundamentals &#40;Analysis Services&#41;</span></span>](multidimensional-models/mdx/mdx-query-fundamentals-analysis-services.md)  
  
  
