---
title: Tuple | Microsoft Docs
ms.custom: ''
ms.date: 07/17/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 35b629ae-b1ef-44b1-b556-96956aeb56e7
author: minewiskan
ms.author: owend
ms.openlocfilehash: c39d03d60cb66f3b2e26b2e660bd85f4e5e9d4ec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721892"
---
# <a name="tuples"></a><span data-ttu-id="ebc83-102">Tuple</span><span class="sxs-lookup"><span data-stu-id="ebc83-102">Tuples</span></span>
  <span data-ttu-id="ebc83-103">Una tupla consente di identificare in modo univoco una sezione di dati di un cubo.</span><span class="sxs-lookup"><span data-stu-id="ebc83-103">A tuple uniquely identifies a slice of data from a cube.</span></span> <span data-ttu-id="ebc83-104">La tupla viene creata da una combinazione di membri di dimensione, finché non esistono due o più membri che appartengono alla medesima gerarchia.</span><span class="sxs-lookup"><span data-stu-id="ebc83-104">The tuple is formed by a combination of dimension members, as long as there are no two or more members that belong to the same hierarchy.</span></span>  
  
## <a name="implicit-or-default-attribute-members-in-a-tuple"></a><span data-ttu-id="ebc83-105">Membri dell'attributo impliciti o predefiniti in una tupla</span><span class="sxs-lookup"><span data-stu-id="ebc83-105">Implicit or default attribute members in a tuple</span></span>  
 <span data-ttu-id="ebc83-106">Quando si definisce una tupla in una query o espressione MDX, non è necessario includere in modo esplicito il membro dell'attributo di ogni gerarchia dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="ebc83-106">When defining a tuple in an MDX query or expression, you do not need to explicitly include the attribute member from every attribute hierarchy.</span></span> <span data-ttu-id="ebc83-107">Se un membro di una gerarchia dell'attributo non viene incluso in una query o espressione in modo esplicito, il membro predefinito della gerarchia dell'attributo è il membro dell'attributo incluso nella tupla in modo implicito.</span><span class="sxs-lookup"><span data-stu-id="ebc83-107">If a member from an attribute hierarchy is not explicitly included in a query or an expression, the default member for that attribute hierarchy is the attribute member implicitly included in the tuple.</span></span> <span data-ttu-id="ebc83-108">Se non altrimenti definito in modo esplicito in un cubo, il membro predefinito per ogni gerarchia dell'attributo è il membro (Totale), se esistente.</span><span class="sxs-lookup"><span data-stu-id="ebc83-108">Unless otherwise explicitly defined in a cube, the default member for every attribute hierarchy is the (All) member, if an (All) member exists.</span></span> <span data-ttu-id="ebc83-109">Se non esiste un membro (Totale) all'interno di una gerarchia dell'attributo, il membro predefinito è un membro del livello principale della gerarchia dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="ebc83-109">If an (All) member does not exist within an attribute hierarchy, the default member is a member of the attribute hierarchy's top level.</span></span> <span data-ttu-id="ebc83-110">La misura predefinita è la prima misura specificata nel cubo, a meno che non venga definita in modo esplicito una misura predefinita.</span><span class="sxs-lookup"><span data-stu-id="ebc83-110">The default measure is the first measure specified in the cube, unless a default measure is explicitly defined.</span></span> <span data-ttu-id="ebc83-111">Per altre informazioni, vedere [Definire un membro predefinito](../attribute-properties-define-a-default-member.md) e [DefaultMember &#40;MDX&#41;](/sql/mdx/defaultmember-mdx).</span><span class="sxs-lookup"><span data-stu-id="ebc83-111">For more information, see [Define a Default Member](../attribute-properties-define-a-default-member.md) and [DefaultMember &#40;MDX&#41;](/sql/mdx/defaultmember-mdx).</span></span>  
  
 <span data-ttu-id="ebc83-112">La tupla seguente identifica ad esempio una singola cella nel database Adventure Works definendo in modo esplicito un solo membro della dimensione Measures.</span><span class="sxs-lookup"><span data-stu-id="ebc83-112">For example, the following tuple identifies a single cell in the Adventure Works database by explicitly defining only a single member of the Measures dimension.</span></span>  
  
```  
(Measures.[Reseller Sales Amount])  
```  
  
 <span data-ttu-id="ebc83-113">Nell'esempio precedente viene identificata in modo univoco la cella costituita dal membro Reseller Sales Amount della dimensione Measures e dal membro predefinito di ogni gerarchia dell'attributo del cubo.</span><span class="sxs-lookup"><span data-stu-id="ebc83-113">The previous example uniquely identifies the cell consisting of the Reseller Sales Amount member from the Measures dimension and the default member from every attribute hierarchy in the cube.</span></span> <span data-ttu-id="ebc83-114">Il membro predefinito è il membro (Totale) per ogni gerarchia dell'attributo diversa dalla gerarchia dell'attributo Destination Currency.</span><span class="sxs-lookup"><span data-stu-id="ebc83-114">The default member is the (All) member for every attribute hierarchy other than the Destination Currency attribute hierarchy.</span></span> <span data-ttu-id="ebc83-115">Il membro predefinito per la gerarchia Destination Currency, è il membro US Dollar. Questo membro predefinito viene definito nello script MDX del cubo Adventure Works.</span><span class="sxs-lookup"><span data-stu-id="ebc83-115">The default member for the Destination Currency hierarchy is the US Dollar member (this default member is defined in the MDX script for the Adventure Works cube).</span></span>  
  
 <span data-ttu-id="ebc83-116">Nella query seguente viene restituito il valore della cella a cui fa riferimento la tupla specificata nell'esempio precedente, ($80,450.596.98).</span><span class="sxs-lookup"><span data-stu-id="ebc83-116">The following query returns the value for the cell referenced by the tuple specified in the previous example, ($80,450.596.98).</span></span>  
  
```  
SELECT   
Measures.[Reseller Sales Amount] ON COLUMNS   
FROM [Adventure Works]  
```  
  
> [!NOTE]  
>  <span data-ttu-id="ebc83-117">Quando in una query si specifica un asse per un set (in questo caso costituito da una sola tupla), è necessario specificare innanzitutto un set per l'asse delle colonne prima di specificare un set per l'asse delle righe.</span><span class="sxs-lookup"><span data-stu-id="ebc83-117">When you specify an axis for a set (in this case composed of a single tuple) in a query, you must begin by specifying a set for the column axis before specifying a set for the row axis.</span></span> <span data-ttu-id="ebc83-118">L'asse delle colonne è inoltre noto come *Axis(0)* o semplicemente *0*.</span><span class="sxs-lookup"><span data-stu-id="ebc83-118">The column axis can also be referred to as *axis(0)* or simply *0*.</span></span> <span data-ttu-id="ebc83-119">Per altre informazioni, vedere [Query MDX di base &#40;MDX&#41;](mdx-query-the-basic-query.md).</span><span class="sxs-lookup"><span data-stu-id="ebc83-119">For more information about MDX queries, see [The Basic MDX Query &#40;MDX&#41;](mdx-query-the-basic-query.md).</span></span>  
  
### <a name="tuples-as-values-or-member-references"></a><span data-ttu-id="ebc83-120">Tuple come riferimenti a valori o al membro</span><span class="sxs-lookup"><span data-stu-id="ebc83-120">Tuples as values or member references</span></span>  
 <span data-ttu-id="ebc83-121">È inoltre possibile usare una tupla in una query per restituire il valore della cella a cui fa riferimento la tupla, come nell'esempio precedente,</span><span class="sxs-lookup"><span data-stu-id="ebc83-121">You can use a tuple in a query to return the value in the cell that is referenced by the tuple, as in the previous example.</span></span> <span data-ttu-id="ebc83-122">oppure è possibile usarla in un'espressione per fare riferimento in modo esplicito ai membri specificati nella tupla.</span><span class="sxs-lookup"><span data-stu-id="ebc83-122">Or you can use a tuple in an expression to explicitly refer to the members specified in the tuple.</span></span> <span data-ttu-id="ebc83-123">La query o l'espressione consente di impiegare funzioni che restituiscono o usano le tuple.</span><span class="sxs-lookup"><span data-stu-id="ebc83-123">The query or the expression can utilize functions that either return or consume tuples.</span></span> <span data-ttu-id="ebc83-124">Una tupla può essere usata per fare riferimento al valore della cella specificata dalla tupla o per specificare una combinazione di membri quando viene usata in una funzione.</span><span class="sxs-lookup"><span data-stu-id="ebc83-124">A tuple can be used to either refer to the value of the cell that the tuple specifies, or to specify a combination of members when utilized in a function.</span></span>  
  
### <a name="tuple-dimensionality"></a><span data-ttu-id="ebc83-125">Dimensionalità della tupla</span><span class="sxs-lookup"><span data-stu-id="ebc83-125">Tuple dimensionality</span></span>  
 <span data-ttu-id="ebc83-126">Per *dimensionalità* di una tupla si intende la sequenza o l'ordine dei membri nella tupla.</span><span class="sxs-lookup"><span data-stu-id="ebc83-126">The *dimensionality* of a tuple refers to the sequence or order of the members in the tuple.</span></span> <span data-ttu-id="ebc83-127">Dal momento che i membri impliciti ricorrono sempre nello stesso ordine, la dimensionalità viene spesso considerata in relazione ai membri della tupla definiti in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="ebc83-127">Since the implicit members always occur in the same order, dimensionality is most often thought of in terms of the explicitly defined members of the tuple.</span></span> <span data-ttu-id="ebc83-128">L'ordinamento dei membri della tupla è importante quando si definisce un set di tuple.</span><span class="sxs-lookup"><span data-stu-id="ebc83-128">The ordering of the members of the tuple is important when you define a set of tuples.</span></span> <span data-ttu-id="ebc83-129">Nell'esempio seguente vengono inclusi due membri di una tupla nell'asse delle colonne.</span><span class="sxs-lookup"><span data-stu-id="ebc83-129">The following example includes two members in a tuple on the column axis.</span></span>  
  
```  
SELECT   
([Measures].[Reseller Sales Amount],[Date].[Calendar Year].[CY 2004]) ON COLUMNS   
FROM [Adventure Works]  
```  
  
> [!NOTE]  
>  <span data-ttu-id="ebc83-130">Quando si specifica in modo esplicito un membro in una tupla da più di una dimensione, è necessario includere l'intera tupla tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="ebc83-130">When you explicitly specify a member in a tuple from more than one dimension, you must include the entire tuple in parentheses.</span></span> <span data-ttu-id="ebc83-131">Quando si specifica un solo membro in una tupla, le parentesi sono facoltative.</span><span class="sxs-lookup"><span data-stu-id="ebc83-131">When only specifying a single member in a tuple, parentheses are optional.</span></span>  
  
 <span data-ttu-id="ebc83-132">La tupla nella query dell'esempio precedente specifica la restituzione della cella del cubo nel punto di intersezione tra la misura Reseller Sales Amount della dimensione Measures e il membro CY 2004 della gerarchia dell'attributo Calendar Year nella dimensione Date.</span><span class="sxs-lookup"><span data-stu-id="ebc83-132">The tuple in the query in the previous example specifies the return of the cube cell at the intersection of the Reseller Sales Amount Measure of the Measures dimension and the CY 2004 member of the Calendar Year attribute hierarchy in the Date dimension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ebc83-133">È possibile fare riferimento a un membro dell'attributo tramite il nome o la chiave del membro.</span><span class="sxs-lookup"><span data-stu-id="ebc83-133">An attribute member can be referred by either its member name or its member key.</span></span> <span data-ttu-id="ebc83-134">Nell'esempio precedente, è possibile sostituire il riferimento a [CY 2004] con &[2004].</span><span class="sxs-lookup"><span data-stu-id="ebc83-134">In the previous example, you could replace the reference to [CY 2004] with &[2004].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebc83-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ebc83-135">See Also</span></span>  
 <span data-ttu-id="ebc83-136">[Concetti chiave di MDX &#40;Analysis Services&#41;](../key-concepts-in-mdx-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="ebc83-136">[Key Concepts in MDX &#40;Analysis Services&#41;](../key-concepts-in-mdx-analysis-services.md) </span></span>  
 <span data-ttu-id="ebc83-137">[Spazio del cubo](cube-space.md) </span><span class="sxs-lookup"><span data-stu-id="ebc83-137">[Cube Space](cube-space.md) </span></span>  
 <span data-ttu-id="ebc83-138">[Autoexists](autoexists.md) </span><span class="sxs-lookup"><span data-stu-id="ebc83-138">[Autoexists](autoexists.md) </span></span>  
 [<span data-ttu-id="ebc83-139">Utilizzo di membri, tuple e set &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="ebc83-139">Working with Members, Tuples, and Sets &#40;MDX&#41;</span></span>](working-with-members-tuples-and-sets-mdx.md)  
  
  
