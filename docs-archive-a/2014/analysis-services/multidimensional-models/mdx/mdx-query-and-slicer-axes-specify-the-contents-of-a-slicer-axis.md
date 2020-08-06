---
title: Specifica del contenuto di un asse di sezionamento (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- slicer axis
- filtering data [MDX]
ms.assetid: c56b0a70-cdec-427f-990e-425290344e7d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 8620c54970ea14a2ac01c85262a372d2b3db0d68
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712559"
---
# <a name="specifying-the-contents-of-a-slicer-axis-mdx"></a><span data-ttu-id="264ad-102">Impostazione del contenuto di un asse di sezionamento (MDX)</span><span class="sxs-lookup"><span data-stu-id="264ad-102">Specifying the Contents of a Slicer Axis (MDX)</span></span>
  <span data-ttu-id="264ad-103">L'asse di sezionamento filtra i dati restituiti dall'istruzione SELECT di MDX (Multidimensional Expression), limitando la restituzione ai soli dati che si intersecano con i membri specificati.</span><span class="sxs-lookup"><span data-stu-id="264ad-103">The slicer axis filters the data returned by the Multidimensional Expressions (MDX) SELECT statement, restricting the returned data so that only data intersecting with the specified members will be returned.</span></span> <span data-ttu-id="264ad-104">Può essere considerato un asse aggiuntivo invisibile in una query.</span><span class="sxs-lookup"><span data-stu-id="264ad-104">It can be thought of as an invisible extra axis in a query.</span></span> <span data-ttu-id="264ad-105">L'asse di sezionamento è definito nella clausola WHERE dell'istruzione SELECT in MDX.</span><span class="sxs-lookup"><span data-stu-id="264ad-105">The slicer axis is defined in the WHERE clause of the SELECT statement in MDX.</span></span>  
  
## <a name="slicer-axis-syntax"></a><span data-ttu-id="264ad-106">Sintassi dell'asse di sezionamento</span><span class="sxs-lookup"><span data-stu-id="264ad-106">Slicer Axis Syntax</span></span>  
 <span data-ttu-id="264ad-107">Per specificare in modo esplicito un asse di sezionamento, è necessario utilizzare `<SELECT slicer axis clause>` in MDX, come descritto nella sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="264ad-107">To explicitly specify a slicer axis, you  using the `<SELECT slicer axis clause>` in MDX, as described in the following syntax:</span></span>  
  
```  
<SELECT slicer axis clause> ::=  WHERE Set_Expression  
```  
  
 <span data-ttu-id="264ad-108">Nella sintassi dell'asse di sezionamento riportata sopra `Set_Expression` può accettare un'espressione di tupla, che viene considerata come set per la valutazione della clausola, o un'espressione set.</span><span class="sxs-lookup"><span data-stu-id="264ad-108">In the slicer axis syntax shown, `Set_Expression` can take either a tuple expression, which is treated as a set for the purposes of evaluating the clause, or a set expression.</span></span> <span data-ttu-id="264ad-109">Se viene specificata un'espressione set, viene tentata la valutazione del set mediante l'aggregazione delle celle dei risultati in ogni tupla del set.</span><span class="sxs-lookup"><span data-stu-id="264ad-109">If a set expression is specified, MDX will try to evaluate the set, aggregating the result cells in every tuple along the set.</span></span> <span data-ttu-id="264ad-110">In altre parole, MDX tenta di utilizzare la funzione [Aggregate](/sql/mdx/aggregate-mdx) sul set aggregando ogni misura in base alla funzione di aggregazione associata.</span><span class="sxs-lookup"><span data-stu-id="264ad-110">In other words, MDX will try to use the [Aggregate](/sql/mdx/aggregate-mdx) function on the set, aggregating each measure by its associated aggregation function.</span></span> <span data-ttu-id="264ad-111">Inoltre, se non è possibile esprimere l'espressione set come crossjoin di membri della gerarchia dell'attributo, ai fini della valutazione le celle esterne all'espressione set per il sezionamento vengono considerate Null.</span><span class="sxs-lookup"><span data-stu-id="264ad-111">Also, if the set expression cannot be expressed as a crossjoin of attribute hierarchy members, MDX treats cells that fall outside of the set expression for the slicer as null for evaluation purposes.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="264ad-112">A differenza della clausola WHERE in SQL, la clausola WHERE di un'istruzione MDX SELECT non filtra mai direttamente i valori restituiti nell'asse delle righe di una query.</span><span class="sxs-lookup"><span data-stu-id="264ad-112">Unlike the WHERE clause in SQL, the WHERE clause of an MDX SELECT statement never directly filters what is returned on the Rows axis of a query.</span></span> <span data-ttu-id="264ad-113">Per filtrare quanto visualizzato nell'asse delle righe o delle colonne di una query, è possibile utilizzare un'ampia gamma di funzioni MDX, ad esempio FILTER, NONEMPTY e TOPCOUNT.</span><span class="sxs-lookup"><span data-stu-id="264ad-113">To filter what appears on the Rows or Columns axis of a query, you can use a variety of MDX functions, for example FILTER, NONEMPTY and TOPCOUNT.</span></span>  
  
### <a name="implicit-slicer-axis"></a><span data-ttu-id="264ad-114">Asse di sezionamento implicito</span><span class="sxs-lookup"><span data-stu-id="264ad-114">Implicit Slicer Axis</span></span>  
 <span data-ttu-id="264ad-115">Se un membro di una gerarchia all'interno del cubo non viene incluso in un'asse della query in modo esplicito, il membro predefinito della gerarchia viene incluso nell'asse di sezionamento in modo implicito.</span><span class="sxs-lookup"><span data-stu-id="264ad-115">If a member from a hierarchy within the cube is not explicitly included in a query axis, the default member from that hierarchy is implicitly included in the slicer axis.</span></span> <span data-ttu-id="264ad-116">Per altre informazioni, vedere [Definire un membro predefinito](../attribute-properties-define-a-default-member.md).</span><span class="sxs-lookup"><span data-stu-id="264ad-116">For more information about default members, see [Define a Default Member](../attribute-properties-define-a-default-member.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="264ad-117">Esempi</span><span class="sxs-lookup"><span data-stu-id="264ad-117">Examples</span></span>  
 <span data-ttu-id="264ad-118">Nella query seguente non è inclusa una clausola WHERE e viene restituito il valore della misura Internet Sales Amount per tutti gli anni di calendario:</span><span class="sxs-lookup"><span data-stu-id="264ad-118">The following query does not include a WHERE clause, and returns the value of the Internet Sales Amount measure for all Calendar Years:</span></span>  
  
```  
SELECT {[Measures].[Internet Sales Amount]} ON COLUMNS,  
[Date].[Calendar Year].MEMBERS ON ROWS  
FROM [Adventure Works]  
```  
  
 <span data-ttu-id="264ad-119">L'aggiunta di una clausola WHERE, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="264ad-119">Adding a WHERE clause, as follows:</span></span>  
  
```  
SELECT {[Measures].[Internet Sales Amount]} ON COLUMNS,  
[Date].[Calendar Year].MEMBERS ON ROWS  
FROM [Adventure Works]  
WHERE([Customer].[Customer Geography].[Country].&[United States])  
  
```  
  
 <span data-ttu-id="264ad-120">non modifica i valori restituiti nelle righe o nelle colonne nella query, ma modifica i valori restituiti per ogni cella.</span><span class="sxs-lookup"><span data-stu-id="264ad-120">does not change what is returned on Rows or Columns in the query; it changes the values returned for each cell.</span></span> <span data-ttu-id="264ad-121">In questo esempio la query viene sezionata in modo da restituire il valore di Internet Sales Amount per tutti gli anni di calendario, ma solo per i clienti che vivono negli Stati Uniti. È possibile aggiungere più membri di gerarchie diverse alla clausola WHERE.</span><span class="sxs-lookup"><span data-stu-id="264ad-121">In this example, the query is sliced so that it returns the value of Internet Sales Amount for all Calendar Years but only for Customers who live in the United States.Multiple members from different hierarchies can be added to the WHERE clause.</span></span> <span data-ttu-id="264ad-122">Nella query seguente viene illustrato il valore di Internet Sales Amount per tutti gli anni di calendario per i clienti che vivono negli Stati Uniti e che hanno acquistato prodotti nella categoria Bikes:</span><span class="sxs-lookup"><span data-stu-id="264ad-122">The following query shows the value of Internet Sales Amount for all Calendar Years for Customers who live in the United States and who bought Products in the Category Bikes:</span></span>  
  
```  
SELECT {[Measures].[Internet Sales Amount]} ON COLUMNS,  
[Date].[Calendar Year].MEMBERS ON ROWS  
FROM [Adventure Works]  
WHERE([Customer].[Customer Geography].[Country].&[United States], [Product].[Category].&[1])  
```  
  
 <span data-ttu-id="264ad-123">Se si desidera utilizzare più membri della stessa gerarchia, è necessario includere un set nella clausola WHERE.</span><span class="sxs-lookup"><span data-stu-id="264ad-123">If you want to use multiple members from the same hierarchy, you need to include a set in the WHERE clause.</span></span> <span data-ttu-id="264ad-124">Nella query seguente, ad esempio, viene indicato il valore di Internet Sales Amount per tutti gli anni di calendario per i clienti che hanno acquistato prodotti nella categoria Bikes e che vivono negli Stati Uniti o in Regno Unito:</span><span class="sxs-lookup"><span data-stu-id="264ad-124">For example, the following query shows the value of Internet Sales Amount for all Calendar Years for Customers who bought Products in the Category Bikes and live in either the United States or the United Kingdom:</span></span>  
  
```  
SELECT {[Measures].[Internet Sales Amount]} ON COLUMNS,  
[Date].[Calendar Year].MEMBERS ON ROWS  
FROM [Adventure Works]  
WHERE(  
{[Customer].[Customer Geography].[Country].&[United States]  
, [Customer].[Customer Geography].[Country].&[United Kingdom]}  
, [Product].[Category].&[1])  
  
```  
  
 <span data-ttu-id="264ad-125">Come indicato in precedenza, l'utilizzo di un set nella clausola WHERE consente di aggregare in modo implicito valori per tutti i membri del set.</span><span class="sxs-lookup"><span data-stu-id="264ad-125">As mentioned above, using a set in the WHERE clause will implicitly aggregate values for all members in the set.</span></span> <span data-ttu-id="264ad-126">In questo caso, la query indica i valori aggregati per gli Stati Uniti e il Regno Unito in ogni cella.</span><span class="sxs-lookup"><span data-stu-id="264ad-126">In this case, the query shows aggregated values for the United States and the United Kingdom in each cell.</span></span>  
  
  
