---
title: Utilizzo di membri, Tuple e set (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- MDX [Analysis Services], tuples
- member keys [MDX]
- MDX [Analysis Services], sets
- calculated members [MDX]
- members [MDX]
- Multidimensional Expressions [Analysis Services], members
- named sets [MDX]
- Multidimensional Expressions [Analysis Services], tuples
- member functions [MDX]
- sets [MDX]
- MDX [Analysis Services], members
- member names [MDX]
- Multidimensional Expressions [Analysis Services], sets
- tuple functions
- tuples
- set functions [MDX]
ms.assetid: b6ec2439-caef-46d3-9fd7-5f4526cee334
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5ce3bf2d5ad7df2b1cd74897b3b49c7cef97e8ed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624388"
---
# <a name="working-with-members-tuples-and-sets-mdx"></a><span data-ttu-id="13452-102">Utilizzo di membri, tuple e set (MDX)</span><span class="sxs-lookup"><span data-stu-id="13452-102">Working with Members, Tuples, and Sets (MDX)</span></span>
  <span data-ttu-id="13452-103">MDX offre numerose funzioni che restituiscono uno o più membri, tuple o set oppure eseguono operazioni su un membro, una tupla o un set.</span><span class="sxs-lookup"><span data-stu-id="13452-103">MDX provides numerous functions that return one or more members, tuples, or sets; or that act upon a member, tuple, or set.</span></span>  
  
## <a name="member-functions"></a><span data-ttu-id="13452-104">Funzioni di membro</span><span class="sxs-lookup"><span data-stu-id="13452-104">Member Functions</span></span>  
 <span data-ttu-id="13452-105">MDX offre diverse funzioni per il recupero di membri da altre entità MDX, ad esempio dimensioni, livelli, set o tuple.</span><span class="sxs-lookup"><span data-stu-id="13452-105">MDX provides several functions for retrieving members from other MDX entities, such as from dimensions, levels, sets, or tuples.</span></span> <span data-ttu-id="13452-106">Con la funzione [FirstChild](/sql/mdx/firstchild-mdx) , ad esempio, vengono eseguite operazioni su un membro e viene restituito un membro.</span><span class="sxs-lookup"><span data-stu-id="13452-106">For example, the [FirstChild](/sql/mdx/firstchild-mdx) function is a function that acts upon a member and returns a member.</span></span>  
  
 <span data-ttu-id="13452-107">Per ottenere il primo membro figlio di una dimensione temporale, è possibile indicare il membro in modo esplicito come nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="13452-107">To obtain the first child member of the Time dimension, you can explicitly state the member, as in the following example.</span></span>  
  
```  
SELECT [Date].[Calendar Year].[CY 2001] on 0  
FROM [Adventure Works]  
  
```  
  
 <span data-ttu-id="13452-108">È inoltre possibile restituire lo stesso membro utilizzando la funzione `FirstChild`, come nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="13452-108">You can also use the `FirstChild` function to return the same member, as in the following example.</span></span>  
  
```  
SELECT [Date].[Calendar Year].FirstChild on 0  
FROM [Adventure Works]  
  
```  
  
 <span data-ttu-id="13452-109">Per altre informazioni sulle funzioni di membro MDX, vedere [Guida di riferimento alle funzioni MDX &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span><span class="sxs-lookup"><span data-stu-id="13452-109">For more information about MDX member functions, see [MDX Function Reference &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span></span>  
  
## <a name="tuple-functions"></a><span data-ttu-id="13452-110">funzioni di tupla</span><span class="sxs-lookup"><span data-stu-id="13452-110">Tuple Functions</span></span>  
 <span data-ttu-id="13452-111">MDX offre diverse funzioni che restituiscono tuple e che possono essere utilizzate in tutti i casi in cui viene accettata una tupla.</span><span class="sxs-lookup"><span data-stu-id="13452-111">MDX provides several functions that return tuples, and they can be used anywhere that a tuple is accepted.</span></span> <span data-ttu-id="13452-112">La funzione [Item &#40;Tuple&#41; &#40;MDX&#41;](/sql/mdx/item-tuple-mdx), ad esempio, può essere usata per estrarre la prima tupla dal set e si rivela estremamente utile quando si è certi che un set è costituito da una singola tupla e si desidera specificare tale tupla per una funzione che ne richiede una.</span><span class="sxs-lookup"><span data-stu-id="13452-112">For example, the [Item &#40;Tuple&#41; &#40;MDX&#41;](/sql/mdx/item-tuple-mdx) function can be used to extract the first tuple from set, which is very useful when you know that a set is composed of a single tuple and you want to supply that tuple to a function that requires a tuple.</span></span>  
  
 <span data-ttu-id="13452-113">Nell'esempio seguente viene restituita la prima tupla dal set di tuple sull'asse delle colonne.</span><span class="sxs-lookup"><span data-stu-id="13452-113">The following example returns the first tuple from within the set of tuples on the column axis.</span></span>  
  
```  
SELECT {  
   ([Measures].[Reseller Sales Amount]  
      ,[Date].[Calendar Year].[CY 2003]  
   )  
, ([Measures].[Reseller Sales Amount]  
      ,[Date].[Calendar Year].[CY 2004]  
   )  
}.Item(0)  
ON COLUMNS   
FROM [Adventure Works]  
```  
  
 <span data-ttu-id="13452-114">Per altre informazioni sulle funzioni di tupla, vedere [Guida di riferimento alle funzioni MDX &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span><span class="sxs-lookup"><span data-stu-id="13452-114">For more information about tuple functions, see [MDX Function Reference &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span></span>  
  
## <a name="set-functions"></a><span data-ttu-id="13452-115">Funzioni di set</span><span class="sxs-lookup"><span data-stu-id="13452-115">Set Functions</span></span>  
 <span data-ttu-id="13452-116">MDX offre diverse funzioni che restituiscono set.</span><span class="sxs-lookup"><span data-stu-id="13452-116">MDX provides several functions that return sets.</span></span> <span data-ttu-id="13452-117">La digitazione esplicita di tuple racchiuse tra parentesi graffe non è l'unico metodo disponibile per il recupero di un set.</span><span class="sxs-lookup"><span data-stu-id="13452-117">Explicitly typing tuples and enclosing them in braces is not the only way to retrieve a set.</span></span> <span data-ttu-id="13452-118">Per altre informazioni sulle funzioni relative ai membri che restituiscono un set, vedere [Concetti chiave di MDX &#40;Analysis Services&#41;](../key-concepts-in-mdx-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="13452-118">For more information about the members function to return a set, see [Key Concepts in MDX &#40;Analysis Services&#41;](../key-concepts-in-mdx-analysis-services.md).</span></span> <span data-ttu-id="13452-119">Sono disponibili numerose funzioni aggiuntive di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="13452-119">There are many additional set functions.</span></span>  
  
 <span data-ttu-id="13452-120">L'operatore Range (:) consente di utilizzare l'ordine naturale dei membri per la creazione di un set.</span><span class="sxs-lookup"><span data-stu-id="13452-120">The colon operator lets you use the natural order of members to create a set.</span></span> <span data-ttu-id="13452-121">Il set illustrato nell'esempio seguente contiene le tuple per i primi quattro trimestri dell'anno di calendario 2002.</span><span class="sxs-lookup"><span data-stu-id="13452-121">For example, the set shown in the following example contains tuples for the 1st through the 4th quarter of calendar year 2002.</span></span>  
  
```  
SELECT   
   {[Calendar Quarter].[Q1 CY 2002]:[Calendar Quarter].[Q4 CY 2002]}   
ON 0  
FROM [Adventure Works]  
```  
  
 <span data-ttu-id="13452-122">Se non si utilizza l'operatore Range (:) per creare il set, è possibile creare lo stesso set di membri specificando le tuple come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="13452-122">If you do not use the colon operator to create the set, you can create the same set of members by specifying the tuples in the following example.</span></span>  
  
```  
SELECT {  
   [Calendar Quarter].[Q1 CY 2002],   
   [Calendar Quarter].[Q2 CY 2002],   
   [Calendar Quarter].[Q3 CY 2002],   
   [Calendar Quarter].[Q4 CY 2002]  
   } ON 0  
FROM [Adventure Works]  
  
```  
  
 <span data-ttu-id="13452-123">L'operatore Range (:) è una funzione inclusiva.</span><span class="sxs-lookup"><span data-stu-id="13452-123">The colon operator is an inclusive function.</span></span> <span data-ttu-id="13452-124">I membri ai due lati dell'operatore vengono infatti inclusi nel set risultante.</span><span class="sxs-lookup"><span data-stu-id="13452-124">The members on both sides of the colon operator are included in the resulting set.</span></span>  
  
 <span data-ttu-id="13452-125">Per altre informazioni sulle funzioni di set, vedere [Guida di riferimento alle funzioni MDX &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span><span class="sxs-lookup"><span data-stu-id="13452-125">For more information about set functions, see [MDX Function Reference &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span></span>  
  
## <a name="array-functions"></a><span data-ttu-id="13452-126">Funzioni di matrice</span><span class="sxs-lookup"><span data-stu-id="13452-126">Array Functions</span></span>  
 <span data-ttu-id="13452-127">Con una funzione per matrici vengono eseguite operazioni su un set e viene restituita una matrice.</span><span class="sxs-lookup"><span data-stu-id="13452-127">An array function acts upon a set and returns an array.</span></span> <span data-ttu-id="13452-128">Per altre informazioni sulle funzioni del di matrice, vedere [Guida di riferimento alle funzioni MDX &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span><span class="sxs-lookup"><span data-stu-id="13452-128">For more information about array functions, see [MDX Function Reference &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span></span>  
  
## <a name="hierarchy-functions"></a><span data-ttu-id="13452-129">Funzioni di gerarchia</span><span class="sxs-lookup"><span data-stu-id="13452-129">Hierarchy Functions</span></span>  
 <span data-ttu-id="13452-130">Una funzione di gerarchia restituisce una gerarchia eseguendo operazioni su un membro, un livello, una gerarchia o una stringa.</span><span class="sxs-lookup"><span data-stu-id="13452-130">A hierarchy function returns a hierarchy by acting upon a member, level, hierarchy, or string.</span></span> <span data-ttu-id="13452-131">Per altre informazioni sulle funzioni di gerarchia, vedere [Guida di riferimento alle funzioni MDX &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span><span class="sxs-lookup"><span data-stu-id="13452-131">For more information about hierarchy functions, see [MDX Function Reference &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span></span>  
  
## <a name="level-functions"></a><span data-ttu-id="13452-132">Funzioni di livello</span><span class="sxs-lookup"><span data-stu-id="13452-132">Level Functions</span></span>  
 <span data-ttu-id="13452-133">Una funzione di livello restituisce un livello eseguendo operazioni su un membro, un livello o una stringa.</span><span class="sxs-lookup"><span data-stu-id="13452-133">A level function returns a level by acting upon a member, level, or string.</span></span> <span data-ttu-id="13452-134">Per altre informazioni sulle funzioni di livello, vedere [Guida di riferimento alle funzioni MDX &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span><span class="sxs-lookup"><span data-stu-id="13452-134">For more information about level functions, see [MDX Function Reference &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span></span>  
  
## <a name="logical-functions"></a><span data-ttu-id="13452-135">Funzioni logiche</span><span class="sxs-lookup"><span data-stu-id="13452-135">Logical Functions</span></span>  
 <span data-ttu-id="13452-136">Con una funzione logica vengono eseguite operazioni su un'espressione MDX per la restituzione di informazioni sulle tuple, sui membri o sui set nell'espressione.</span><span class="sxs-lookup"><span data-stu-id="13452-136">A logical function acts upon a MDX expression to return information about the tuples, members, or sets in the expression.</span></span> <span data-ttu-id="13452-137">La funzione [IsEmpty &#40;MDX&#41;](/sql/mdx/isempty-mdx), ad esempio, valuta se un'espressione ha restituito un valore di cella vuota.</span><span class="sxs-lookup"><span data-stu-id="13452-137">For example, the [IsEmpty &#40;MDX&#41;](/sql/mdx/isempty-mdx) function evaluates whether an expression has returned an empty cell value.</span></span> <span data-ttu-id="13452-138">Per altre informazioni sulle funzioni logiche, vedere [Guida di riferimento alle funzioni MDX &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span><span class="sxs-lookup"><span data-stu-id="13452-138">For more information about logical functions, see [MDX Function Reference &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span></span>  
  
## <a name="numeric-functions"></a><span data-ttu-id="13452-139">Funzioni numeriche</span><span class="sxs-lookup"><span data-stu-id="13452-139">Numeric Functions</span></span>  
 <span data-ttu-id="13452-140">Con una funzione numerica vengono eseguite operazioni su un'espressione MDX per la restituzione di un valore scalare.</span><span class="sxs-lookup"><span data-stu-id="13452-140">A numeric function acts upon a MDX expression to return a scalar value.</span></span> <span data-ttu-id="13452-141">La funzione [Aggregate &#40;MDX&#41;](/sql/mdx/aggregate-mdx), ad esempio, restituisce un valore scalare calcolato mediante l'aggregazione di misure sulle tuple in un set specificato.</span><span class="sxs-lookup"><span data-stu-id="13452-141">For example, the [Aggregate &#40;MDX&#41;](/sql/mdx/aggregate-mdx) function returns a scalar value calculated by aggregating measures over the tuples in a specified set.</span></span> <span data-ttu-id="13452-142">Per altre informazioni sulle funzioni numeriche, vedere [Guida di riferimento alle funzioni MDX &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span><span class="sxs-lookup"><span data-stu-id="13452-142">For more information about numeric functions, see [MDX Function Reference &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span></span>  
  
## <a name="string-functions"></a><span data-ttu-id="13452-143">Funzioni di stringa</span><span class="sxs-lookup"><span data-stu-id="13452-143">String Functions</span></span>  
 <span data-ttu-id="13452-144">Con una funzione per i valori stringa vengono eseguite operazioni su un'espressione MDX per la restituzione di una stringa.</span><span class="sxs-lookup"><span data-stu-id="13452-144">A string function acts upon a MDX expression to return a string.</span></span> <span data-ttu-id="13452-145">La funzione [UniqueName &#40;MDX&#41;](/sql/mdx/uniquename-mdx), ad esempio, restituisce un valore stringa contenente il nome univoco di una dimensione, una gerarchia, un livello o un membro.</span><span class="sxs-lookup"><span data-stu-id="13452-145">For example, the [UniqueName &#40;MDX&#41;](/sql/mdx/uniquename-mdx) function returns a string value containing the unique name of a dimension, hierarchy, level, or member.</span></span> <span data-ttu-id="13452-146">Per altre informazioni sulle funzioni per i valori stringa, vedere [Guida di riferimento alle funzioni MDX &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span><span class="sxs-lookup"><span data-stu-id="13452-146">For more information about string functions, see [MDX Function Reference &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13452-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="13452-147">See Also</span></span>  
 <span data-ttu-id="13452-148">[Concetti chiave di MDX &#40;Analysis Services&#41;](../key-concepts-in-mdx-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="13452-148">[Key Concepts in MDX &#40;Analysis Services&#41;](../key-concepts-in-mdx-analysis-services.md) </span></span>  
 <span data-ttu-id="13452-149">[Nozioni fondamentali sulle query MDX &#40;Analysis Services&#41;](mdx-query-fundamentals-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="13452-149">[MDX Query Fundamentals &#40;Analysis Services&#41;](mdx-query-fundamentals-analysis-services.md) </span></span>  
 [<span data-ttu-id="13452-150">Guida di riferimento alle funzioni MDX &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="13452-150">MDX Function Reference &#40;MDX&#41;</span></span>](/sql/mdx/mdx-function-reference-mdx)  
  
  
