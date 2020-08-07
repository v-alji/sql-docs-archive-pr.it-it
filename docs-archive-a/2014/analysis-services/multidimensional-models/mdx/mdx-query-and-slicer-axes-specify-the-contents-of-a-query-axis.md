---
title: Impostazione del contenuto di un asse della query (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- cellsets [MDX]
- query axis [MDX]
ms.assetid: c745ade0-738e-4a98-a3f0-3eabfd3eeba2
author: minewiskan
ms.author: owend
ms.openlocfilehash: 28fd867b8f8caaf74e4dd704753c354368da2e89
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718773"
---
# <a name="specifying-the-contents-of-a-query-axis-mdx"></a><span data-ttu-id="f5330-102">Impostazione del contenuto di un asse della query (MDX)</span><span class="sxs-lookup"><span data-stu-id="f5330-102">Specifying the Contents of a Query Axis (MDX)</span></span>
  <span data-ttu-id="f5330-103">Gli assi della query specificano i bordi di un set di celle restituito dall'istruzione SELECT di MDX (Multidimensional Expression).</span><span class="sxs-lookup"><span data-stu-id="f5330-103">Query axes specify the edges of a cellset returned by a Multidimensional Expressions (MDX) SELECT statement.</span></span> <span data-ttu-id="f5330-104">L'impostazione dei bordi di un set di celle consente di limitare i dati restituiti visibili al client.</span><span class="sxs-lookup"><span data-stu-id="f5330-104">Specifying the edges of a cellset lets you restrict the returned data that is visible to the client.</span></span>  
  
 <span data-ttu-id="f5330-105">Per specificare gli assi della query è necessario assegnare un set a un asse particolare utilizzando `<SELECT query axis clause>` .</span><span class="sxs-lookup"><span data-stu-id="f5330-105">To specify query axes, you use the `<SELECT query axis clause>` to assign a set to a particular query axis.</span></span> <span data-ttu-id="f5330-106">Ogni valore `<SELECT query axis clause>` definisce un asse della query.</span><span class="sxs-lookup"><span data-stu-id="f5330-106">Each `<SELECT query axis clause>` value defines one query axis.</span></span> <span data-ttu-id="f5330-107">Il numero di assi nel set di dati è pari al numero di valori `<SELECT query axis clause>` nell'istruzione SELECT.</span><span class="sxs-lookup"><span data-stu-id="f5330-107">The number of axes in the dataset is equal to the number of `<SELECT query axis clause>` values in the SELECT statement.</span></span>  
  
## <a name="query-axis-syntax"></a><span data-ttu-id="f5330-108">Sintassi degli assi della query</span><span class="sxs-lookup"><span data-stu-id="f5330-108">Query Axis Syntax</span></span>  
 <span data-ttu-id="f5330-109">Di seguito è illustrata la sintassi per `<SELECT query axis clause>`:</span><span class="sxs-lookup"><span data-stu-id="f5330-109">The following syntax shows the syntax for the `<SELECT query axis clause>`:</span></span>  
  
```  
  
<SELECT query axis clause> ::=  
   [ NON EMPTY ] Set_Expression [ <SELECT dimension property list clause> ] [<HAVING clause>]  
   ON {  
      Integer_Expression |   
      AXIS( Integer_Expression ) |   
      {COLUMNS | ROWS | PAGES | SECTIONS | CHAPTERS}     
      }  
  
```  
  
 <span data-ttu-id="f5330-110">Ogni asse della query è associato a un numero: zero (0) per l'asse X, 1 per l'asse Y, 2 per l'asse Z e così via.</span><span class="sxs-lookup"><span data-stu-id="f5330-110">Each query axis has a number: zero (0) for the x-axis, 1 for the y-axis, 2 for the z-axis, and so on.</span></span> <span data-ttu-id="f5330-111">Nella sintassi per `<SELECT query axis clause>`, il valore `Integer_Expression` specifica il numero dell'asse.</span><span class="sxs-lookup"><span data-stu-id="f5330-111">In the syntax for the `<SELECT query axis clause>`, the `Integer_Expression` value specifies the axis number.</span></span> <span data-ttu-id="f5330-112">Una query MDX può supportare fino a 128 assi specificati ma pochissime query MDX utilizzano più di cinque assi.</span><span class="sxs-lookup"><span data-stu-id="f5330-112">An MDX query can support up to 128 specified axes, but very few MDX queries will use more than 5 axes.</span></span> <span data-ttu-id="f5330-113">Per i primi cinque assi è possibile utilizzare gli alias COLUMNS, ROWS, PAGES, SECTIONS e CHAPTERS.</span><span class="sxs-lookup"><span data-stu-id="f5330-113">For the first 5 axes, the aliases COLUMNS, ROWS, PAGES, SECTIONS, and CHAPTERS can instead be used.</span></span>  
  
 <span data-ttu-id="f5330-114">Una query MDX non può ignorare gli assi della query.</span><span class="sxs-lookup"><span data-stu-id="f5330-114">An MDX query cannot skip query axes.</span></span> <span data-ttu-id="f5330-115">In altre parole, una query che include almeno un asse della query non deve escludere gli assi con una numerazione più bassa o intermedia.</span><span class="sxs-lookup"><span data-stu-id="f5330-115">That is, a query that includes one or more query axes must not exclude lower-numbered or intermediate axes.</span></span> <span data-ttu-id="f5330-116">Ad esempio, una query non può includere un asse ROWS senza un asse COLUMNS oppure gli assi COLUMNS e PAGES senza un asse ROWS.</span><span class="sxs-lookup"><span data-stu-id="f5330-116">For example, a query cannot have a ROWS axis without a COLUMNS axis, or have COLUMNS and PAGES axes without a ROWS axis.</span></span>  
  
 <span data-ttu-id="f5330-117">È tuttavia possibile specificare una clausola SELECT senza assi, ovvero una clausola SELECT vuota.</span><span class="sxs-lookup"><span data-stu-id="f5330-117">However, you can specify a SELECT clause without any axes (that is, an empty SELECT clause).</span></span> <span data-ttu-id="f5330-118">In questo caso, tutte le dimensioni sono dimensioni di sezionamento e la query MDX seleziona una cella.</span><span class="sxs-lookup"><span data-stu-id="f5330-118">In this case, all dimensions are slicer dimensions, and the MDX query selects one cell.</span></span>  
  
 <span data-ttu-id="f5330-119">Nella sintassi dell'asse della query riportata in precedenza, ogni valore `Set_Expression` specifica il set che definisce il contenuto dell'asse della query.</span><span class="sxs-lookup"><span data-stu-id="f5330-119">In the query axis syntax previously shown, each `Set_Expression` value specifies the set that defines the contents of the query axis.</span></span> <span data-ttu-id="f5330-120">Per altre informazioni sui set, vedere [Utilizzo di membri, tuple e set &#40;MDX&#41;](working-with-members-tuples-and-sets-mdx.md).</span><span class="sxs-lookup"><span data-stu-id="f5330-120">For more information about sets, see [Working with Members, Tuples, and Sets &#40;MDX&#41;](working-with-members-tuples-and-sets-mdx.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="f5330-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="f5330-121">Examples</span></span>  
 <span data-ttu-id="f5330-122">L'istruzione SELECT semplice seguente restituisce la misura Internet Sales Amount nell'asse Columns e utilizza la funzione MDX MEMBERS per restituire tutti i membri della gerarchia Calendar nella dimensione Date sull'asse delle righe:</span><span class="sxs-lookup"><span data-stu-id="f5330-122">The following simple SELECT statement returns the measure Internet Sales Amount on the Columns axis, and uses the MDX MEMBERS function to return all the members from the Calendar hierarchy on the Date dimension on the Rows axis:</span></span>  
  
```  
SELECT {[Measures].[Internet Sales Amount]} ON COLUMNS,  
{[Date].[Calendar].MEMBERS} ON ROWS  
FROM [Adventure Works]  
  
```  
  
 <span data-ttu-id="f5330-123">Le due query seguenti restituiscono esattamente gli stessi risultati, ma illustrano l'utilizzo dei numeri degli assi anziché degli alias.</span><span class="sxs-lookup"><span data-stu-id="f5330-123">The two following queries return exactly the same results but demonstrate the use of axis numbers rather than aliases:</span></span>  
  
```  
SELECT {[Measures].[Internet Sales Amount]} ON 0,  
{[Date].[Calendar].MEMBERS} ON 1  
FROM [Adventure Works]  
  
SELECT {[Measures].[Internet Sales Amount]} ON AXIS(0),  
{[Date].[Calendar].MEMBERS} ON AXIS(1)  
FROM [Adventure Works]  
  
```  
  
 <span data-ttu-id="f5330-124">La parola chiave NON EMPTY, utilizzata prima delle definizione del set, è un rapido metodo per rimuovere tutte tuple vuote da un asse.</span><span class="sxs-lookup"><span data-stu-id="f5330-124">The NON EMPTY keyword, used before the set definition, is an easy way to remove all empty tuples from an axis.</span></span> <span data-ttu-id="f5330-125">Ad esempio, negli esempi che abbiamo visto finora non sono presenti dati nel cubo a partire dal 2004 agosto.</span><span class="sxs-lookup"><span data-stu-id="f5330-125">For example, in the examples we've seen so far there is no data in the cube from August 2004 onwards.</span></span> <span data-ttu-id="f5330-126">Per rimuovere tutte le righe dal set di celle che non includono dati in alcuna colonna, è sufficiente aggiungere NON EMPTY prima del set nella definizione dell'asse delle righe, nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="f5330-126">To remove all rows from the cellset that have no data in any column, simply add NON EMPTY before the set on the Rows axis definition as follows:</span></span>  
  
```  
SELECT {[Measures].[Internet Sales Amount]} ON COLUMNS,  
NON EMPTY  
{[Date].[Calendar].MEMBERS} ON ROWS  
FROM [Adventure Works]  
  
```  
  
 <span data-ttu-id="f5330-127">È possibile utilizzare NON EMPTY in tutti gli assi in una query.</span><span class="sxs-lookup"><span data-stu-id="f5330-127">NON EMPTY can be used on all axes in a query.</span></span> <span data-ttu-id="f5330-128">Confrontare i risultati delle due query seguenti, la prima delle quali non utilizza NON EMPTY, mentre la seconda delle quali utilizza NON EMPTY su entrambi gli assi.</span><span class="sxs-lookup"><span data-stu-id="f5330-128">Compare the results of the following two queries, the first of which does not use NON EMPTY and the second of which does on both axes:</span></span>  
  
```  
SELECT {[Measures].[Internet Sales Amount]}   
* [Promotion].[Promotion].[Promotion].MEMBERS  
ON COLUMNS,  
{[Date].[Calendar].[Calendar Year].MEMBERS} ON ROWS  
FROM [Adventure Works]  
WHERE([Product].[Subcategory].&[19])  
  
SELECT NON EMPTY {[Measures].[Internet Sales Amount]}   
* [Promotion].[Promotion].[Promotion].MEMBERS  
ON COLUMNS,  
NON EMPTY  
{[Date].[Calendar].[Calendar Year].MEMBERS} ON ROWS  
FROM [Adventure Works]  
WHERE([Product].[Subcategory].&[19])  
  
```  
  
 <span data-ttu-id="f5330-129">È possibile utilizzare la clausola HAVING per filtrare il contenuto di un asse in base a criteri specifici. Benché sia meno flessibile di altri metodi che producono gli stessi risultati, ad esempio la funzione FILTER, è più semplice da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="f5330-129">The HAVING clause can be used to filter the contents of an axis based on a specific criteria; it is less flexible than other methods that can achieve the same results, such as the FILTER function, but it is simpler to use.</span></span> <span data-ttu-id="f5330-130">Nell'esempio seguente vengono restituite solo le date in cui Internet Sales Amount è maggiore di $15,000:</span><span class="sxs-lookup"><span data-stu-id="f5330-130">Here is an example that returns only those dates where Internet Sales Amount is greater than $15,000:</span></span>  
  
```  
SELECT {[Measures].[Internet Sales Amount]}   
ON COLUMNS,  
NON EMPTY  
{[Date].[Calendar].[Date].MEMBERS}   
HAVING [Measures].[Internet Sales Amount]>15000  
ON ROWS  
FROM [Adventure Works]  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="f5330-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f5330-131">See Also</span></span>  
 [<span data-ttu-id="f5330-132">Impostazione del contenuto di un asse di sezionamento &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="f5330-132">Specifying the Contents of a Slicer Axis &#40;MDX&#41;</span></span>](mdx-query-and-slicer-axes-specify-the-contents-of-a-slicer-axis.md)  
  
  
