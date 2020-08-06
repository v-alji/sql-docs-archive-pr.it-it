---
title: Creazione di celle calcolate con ambito sessione | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- session-scoped calculated members [MDX]
ms.assetid: f2d14a89-6286-4e74-9afb-091076f93f21
author: minewiskan
ms.author: owend
ms.openlocfilehash: 199de07778a153cd1bc40b5033d364e5e0055bd3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627445"
---
# <a name="creating-session-scoped-calculated-cells"></a><span data-ttu-id="582ca-102">Creazione di celle calcolate con ambito sessione</span><span class="sxs-lookup"><span data-stu-id="582ca-102">Creating Session-Scoped Calculated Cells</span></span>
    
> [!IMPORTANT]  
>  <span data-ttu-id="582ca-103">Questa sintassi è deprecata</span><span class="sxs-lookup"><span data-stu-id="582ca-103">This syntax has been deprecated.</span></span> <span data-ttu-id="582ca-104">e deve essere sostituita da istruzioni MDX di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="582ca-104">You should use MDX assignments should instead.</span></span> <span data-ttu-id="582ca-105">Per altre informazioni sull'assegnazione, vedere [Script MDX di base &#40;MDX&#41;](the-basic-mdx-script-mdx.md).</span><span class="sxs-lookup"><span data-stu-id="582ca-105">For more information on assignments, see [The Basic MDX Script &#40;MDX&#41;](the-basic-mdx-script-mdx.md).</span></span>  
  
 <span data-ttu-id="582ca-106">Per creare celle calcolate disponibili a tutte le query di una stessa sessione, è possibile usare l'istruzione [CREATE CELL CALCULATION](/sql/mdx/mdx-data-definition-create-cell-calculation) oppure l'istruzione [ALTER CUBE](/sql/mdx/mdx-data-definition-alter-cube) .</span><span class="sxs-lookup"><span data-stu-id="582ca-106">To create calculated cells that are available to all queries in the same session, you can use either the [CREATE CELL CALCULATION](/sql/mdx/mdx-data-definition-create-cell-calculation) statement or the [ALTER CUBE](/sql/mdx/mdx-data-definition-alter-cube) statement.</span></span> <span data-ttu-id="582ca-107">Entrambe le istruzioni restituiscono lo stesso risultato.</span><span class="sxs-lookup"><span data-stu-id="582ca-107">Both statements have the same result.</span></span>  
  
## <a name="create-cell-calculation-syntax"></a><span data-ttu-id="582ca-108">Sintassi di CREATE CELL CALCULATION</span><span class="sxs-lookup"><span data-stu-id="582ca-108">CREATE CELL CALCULATION Syntax</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="582ca-109">Questa sintassi è deprecata</span><span class="sxs-lookup"><span data-stu-id="582ca-109">This syntax has been deprecated.</span></span> <span data-ttu-id="582ca-110">e deve essere sostituita da istruzioni MDX di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="582ca-110">You should use MDX assignments should instead.</span></span> <span data-ttu-id="582ca-111">Per altre informazioni sull'assegnazione, vedere [Script MDX di base &#40;MDX&#41;](the-basic-mdx-script-mdx.md).</span><span class="sxs-lookup"><span data-stu-id="582ca-111">For more information on assignments, see [The Basic MDX Script &#40;MDX&#41;](the-basic-mdx-script-mdx.md).</span></span>  
  
 <span data-ttu-id="582ca-112">Per utilizzare l'istruzione CREATE CELL CALCULATION per definire una cella calcolata con ambito sessione, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="582ca-112">Use the following syntax to use the CREATE CELL CALCULATION statement to define a session-scoped calculated cell:</span></span>  
  
```  
CREATE CELL CALCULATION Cube_Expression.<CREATE CELL CALCULATION body clause>  
  
<CREATE CELL CALCULATION body clause> ::=CellCalc_Identifier FOR String_Expression AS 'MDX_Expression'   
   [ <CREATE CELL CALCULATION property clause> [ , <CREATE CELL CALCULATION property clause> ... ] ]  
  
<CREATE CELL CALCULATION property clause> ::=  
   ( CONDITION = 'Logical_Expression' ) |   
   ( DISABLED = { TRUE | FALSE } ) |   
   ( DESCRIPTION =String_Expression ) |   
   ( CALCULATION_PASS_NUMBER = Integer_Expression ) |   
   ( CALCULATION_PASS_DEPTH = Integer_Expression ) |   
   ( SOLVE_ORDER = Integer_Expression ) |   
   ( FORMAT_STRING = String_Expression ) |   
   ( CellProperty_Identifier = Scalar_Expression )  
```  
  
## <a name="alter-cube-syntax"></a><span data-ttu-id="582ca-113">Sintassi di ALTER CUBE</span><span class="sxs-lookup"><span data-stu-id="582ca-113">ALTER CUBE Syntax</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="582ca-114">Questa sintassi è deprecata</span><span class="sxs-lookup"><span data-stu-id="582ca-114">This syntax has been deprecated.</span></span> <span data-ttu-id="582ca-115">e deve essere sostituita da istruzioni MDX di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="582ca-115">You should use MDX assignments should instead.</span></span> <span data-ttu-id="582ca-116">Per altre informazioni sull'assegnazione, vedere [Script MDX di base &#40;MDX&#41;](the-basic-mdx-script-mdx.md).</span><span class="sxs-lookup"><span data-stu-id="582ca-116">For more information on assignments, see [The Basic MDX Script &#40;MDX&#41;](the-basic-mdx-script-mdx.md).</span></span>  
  
 <span data-ttu-id="582ca-117">Per utilizzare l'istruzione ALTER CUBE per definire una cella calcolata con ambito sessione, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="582ca-117">Use the following syntax to use the ALTER CUBE statement to define a session-scoped calculated cell:</span></span>  
  
```  
ALTER CUBE Cube_Identifier CREATE CELL CALCULATION  
FOR String_Expression AS 'MDX_Expression'   
   [ <CREATE CELL CALCULATION property clause> [ , <CREATE CELL CALCULATION property clause> ... ] ]  
  
<CREATE CELL CALCULATION property clause> ::=  
   ( CONDITION = 'Logical_Expression' ) |   
   ( DISABLED = { TRUE | FALSE } ) |   
   ( DESCRIPTION =String_Expression ) |   
   ( CALCULATION_PASS_NUMBER = Integer_Expression ) |   
   ( CALCULATION_PASS_DEPTH = Integer_Expression ) |   
   ( SOLVE_ORDER = Integer_Expression ) |   
   ( FORMAT_STRING = String_Expression ) |   
   ( CellProperty_Identifier = Scalar_Expression )  
```  
  
 <span data-ttu-id="582ca-118">Il valore `String_Expression` contiene un elenco di espressioni set MDX unidimensionali ortogonali, ognuna delle quali deve essere risolta in una delle categorie di set elencate nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="582ca-118">The `String_Expression` value contains a list of orthogonal, single-dimensional MDX set expressions, each of which must resolve to one of the categories of sets that are listed in the following table.</span></span>  
  
|<span data-ttu-id="582ca-119">Category</span><span class="sxs-lookup"><span data-stu-id="582ca-119">Category</span></span>|<span data-ttu-id="582ca-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="582ca-120">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="582ca-121">Set vuoto</span><span class="sxs-lookup"><span data-stu-id="582ca-121">Empty set</span></span>|<span data-ttu-id="582ca-122">Espressione set MDX che restituisce un set vuoto.</span><span class="sxs-lookup"><span data-stu-id="582ca-122">An MDX set expression that resolves into an empty set.</span></span> <span data-ttu-id="582ca-123">In questo caso l'ambito della cella calcolata è costituito dall'intero cubo.</span><span class="sxs-lookup"><span data-stu-id="582ca-123">In this case, the scope of the calculated cell is the whole cube.</span></span>|  
|<span data-ttu-id="582ca-124">Set con un singolo membro</span><span class="sxs-lookup"><span data-stu-id="582ca-124">Single member set</span></span>|<span data-ttu-id="582ca-125">Espressione set MDX che restituisce un singolo membro.</span><span class="sxs-lookup"><span data-stu-id="582ca-125">An MDX set expression that resolves into a single member.</span></span>|  
|<span data-ttu-id="582ca-126">Set di membri di un livello</span><span class="sxs-lookup"><span data-stu-id="582ca-126">Set of level members</span></span>|<span data-ttu-id="582ca-127">Espressione set MDX che restituisce i membri di un singolo livello.</span><span class="sxs-lookup"><span data-stu-id="582ca-127">An MDX set expression that resolves into the members of a single level.</span></span> <span data-ttu-id="582ca-128">Un esempio è la *Level_Expression*.`Members`</span><span class="sxs-lookup"><span data-stu-id="582ca-128">An example of this is the *Level_Expression*.`Members`</span></span> <span data-ttu-id="582ca-129">.</span><span class="sxs-lookup"><span data-stu-id="582ca-129">MDX function.</span></span> <span data-ttu-id="582ca-130">Per includere i membri calcolati, utilizzare il *Level_Expression*.`AllMembers`</span><span class="sxs-lookup"><span data-stu-id="582ca-130">To include calculated members, use the *Level_Expression*.`AllMembers`</span></span> <span data-ttu-id="582ca-131">.</span><span class="sxs-lookup"><span data-stu-id="582ca-131">MDX function.</span></span><br /><br /> <span data-ttu-id="582ca-132">Per altre informazioni, vedere [AllMembers &#40;MDX&#41;](/sql/mdx/allmembers-mdx).</span><span class="sxs-lookup"><span data-stu-id="582ca-132">For more information, see [AllMembers &#40;MDX&#41;](/sql/mdx/allmembers-mdx).</span></span>|  
|<span data-ttu-id="582ca-133">Set di discendenti</span><span class="sxs-lookup"><span data-stu-id="582ca-133">Set of descendants</span></span>|<span data-ttu-id="582ca-134">Espressione set MDX che restituisce i discendenti di un membro specificato.</span><span class="sxs-lookup"><span data-stu-id="582ca-134">An MDX set expression that resolves into the descendants of a specified member.</span></span> <span data-ttu-id="582ca-135">Un esempio è la `Descendants` funzione MDX (*Member_Expression*, *Level_Expression* *Desc_Flag*).</span><span class="sxs-lookup"><span data-stu-id="582ca-135">An example of this is the `Descendants`(*Member_Expression*, *Level_Expression*, *Desc_Flag*) MDX function.</span></span><br /><br /> <span data-ttu-id="582ca-136">Per altre informazioni, vedere [Descendants &#40;MDX&#41;](/sql/mdx/descendants-mdx).</span><span class="sxs-lookup"><span data-stu-id="582ca-136">For more information, see [Descendants &#40;MDX&#41;](/sql/mdx/descendants-mdx).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="582ca-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="582ca-137">See Also</span></span>  
 [<span data-ttu-id="582ca-138">Compilazione di formule per il calcolo di celle in MDX &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="582ca-138">Building Cell Calculations in MDX &#40;MDX&#41;</span></span>](../../multidimensional-models-olap-logical-cube-objects/calculations.md)  
  
  
