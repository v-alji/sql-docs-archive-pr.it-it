---
title: Definizione del contesto di cubo in una query (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- cubes [Analysis Services], MDX
- MDX [Analysis Services], cube context
- SELECT statement [MDX]
- Multidimensional Expressions [Analysis Services], cube context
- queries [MDX], cube context
ms.assetid: 79d6a1e8-2825-4eb9-97df-5071aecae8f0
author: minewiskan
ms.author: owend
ms.openlocfilehash: 72ae6e19f879651feb47841d70b444e9f845c74e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711075"
---
# <a name="establishing-cube-context-in-a-query-mdx"></a><span data-ttu-id="176e5-102">Definizione del contesto di cubo in una query (MDX)</span><span class="sxs-lookup"><span data-stu-id="176e5-102">Establishing Cube Context in a Query (MDX)</span></span>
  <span data-ttu-id="176e5-103">Ogni query MDX viene eseguita nel contesto di cubo specificato.</span><span class="sxs-lookup"><span data-stu-id="176e5-103">Every MDX query runs within a specified cube context.</span></span> <span data-ttu-id="176e5-104">Tale contesto definisce i membri che vengono valutati dalle espressioni incluse nella query.</span><span class="sxs-lookup"><span data-stu-id="176e5-104">This context defines the members that are evaluated by the expressions within the query.</span></span>  
  
 <span data-ttu-id="176e5-105">Il contesto di cubo è determinato dalla clausola FROM dell'istruzione SELECT.</span><span class="sxs-lookup"><span data-stu-id="176e5-105">In the SELECT statement, the FROM clause determines the cube context.</span></span> <span data-ttu-id="176e5-106">Può corrispondere all'intero cubo o a una sezione del cubo, o sottocubo.</span><span class="sxs-lookup"><span data-stu-id="176e5-106">This context can be the whole cube or just a subcube from that cube.</span></span> <span data-ttu-id="176e5-107">Dopo aver specificato il contesto di cubo tramite la clausola FROM, è possibile utilizzare funzioni aggiuntive per espandere o limitare tale contesto.</span><span class="sxs-lookup"><span data-stu-id="176e5-107">Having specified cube context through the FROM clause, you can use additional functions to expand or restrict that context.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="176e5-108">Per la gestione del contesto di cubo è inoltre possibile utilizzare le istruzioni SCOPE e CALCULATE che consentono di gestire il contesto in uno script MDX.</span><span class="sxs-lookup"><span data-stu-id="176e5-108">The SCOPE and CALCULATE statements also let you manage cube context from within an MDX script.</span></span> <span data-ttu-id="176e5-109">Per altre informazioni, vedere [Nozioni fondamentali sullo scripting MDX &#40;Analysis Services&#41;](mdx-scripting-fundamentals-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="176e5-109">For more information, see [MDX Scripting Fundamentals &#40;Analysis Services&#41;](mdx-scripting-fundamentals-analysis-services.md).</span></span>  
  
## <a name="from-clause-syntax"></a><span data-ttu-id="176e5-110">Sintassi della clausola FROM</span><span class="sxs-lookup"><span data-stu-id="176e5-110">FROM Clause Syntax</span></span>  
 <span data-ttu-id="176e5-111">La sintassi della clausola FROM è la seguente:</span><span class="sxs-lookup"><span data-stu-id="176e5-111">The following syntax describes the FROM clause:</span></span>  
  
```  
<SELECT subcube clause> ::=  
   Cube_Identifier |   
   (SELECT [  
      * |   
      ( <SELECT query axis clause> [ , <SELECT query axis clause> ... ] ) ]   
   FROM <SELECT subcube clause> <SELECT slicer axis clause> )  
```  
  
 <span data-ttu-id="176e5-112">Si noti che il cubo o sottocubo in cui viene eseguita l'istruzione SELECT è descritta nella clausola `<SELECT subcube clause>` .</span><span class="sxs-lookup"><span data-stu-id="176e5-112">In this syntax, notice that it is the `<SELECT subcube clause>` clause that describes the cube or subcube on which the SELECT statement is executed.</span></span>  
  
 <span data-ttu-id="176e5-113">Una clausola FROM semplice viene eseguita nell'intero cubo di esempio Adventure Works.</span><span class="sxs-lookup"><span data-stu-id="176e5-113">A simple example of a FROM clause would be one that runs against the entire Adventure Works sample cube.</span></span> <span data-ttu-id="176e5-114">Il formato di tale clausola è il seguente:</span><span class="sxs-lookup"><span data-stu-id="176e5-114">Such a FROM clause would have the following format:</span></span>  
  
```  
FROM [Adventure Works]  
```  
  
 <span data-ttu-id="176e5-115">Per altre informazioni sulla clausola FROM nell'istruzione MDX SELECT, vedere [Istruzione SELECT &#40;MDX&#41;](/sql/mdx/mdx-data-manipulation-select).</span><span class="sxs-lookup"><span data-stu-id="176e5-115">For more information about the FROM clause in the MDX SELECT statement, see [SELECT Statement &#40;MDX&#41;](/sql/mdx/mdx-data-manipulation-select).</span></span>  
  
## <a name="refining-the-context"></a><span data-ttu-id="176e5-116">Ridefinizione del contesto</span><span class="sxs-lookup"><span data-stu-id="176e5-116">Refining the Context</span></span>  
 <span data-ttu-id="176e5-117">Sebbene la clausola FROM specifichi il contesto di cubo come singolo cubo, ciò non impedisce di utilizzare i dati di più cubi contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="176e5-117">Although the FROM clause specifies the cube context as within a single cube, this does not have to limit you from working with data from more than one cube at a time.</span></span>  
  
 <span data-ttu-id="176e5-118">Tramite la funzione MDX [LookupCube](/sql/mdx/lookupcube-mdx) è possibile recuperare dati di cubi all'esterno del contesto di cubo.</span><span class="sxs-lookup"><span data-stu-id="176e5-118">You can use the MDX [LookupCube](/sql/mdx/lookupcube-mdx) function to retrieve data from cubes outside the cube context.</span></span> <span data-ttu-id="176e5-119">Sono inoltre disponibili funzioni che consentono una limitazione temporale del contesto durante la valutazione della query, ad esempio la funzione [Filter](/sql/mdx/filter-mdx) .</span><span class="sxs-lookup"><span data-stu-id="176e5-119">Additionally, functions such as the [Filter](/sql/mdx/filter-mdx) function, are available that allow temporary restriction of the context while evaluating the query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="176e5-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="176e5-120">See Also</span></span>  
 [<span data-ttu-id="176e5-121">Nozioni fondamentali sulle query MDX &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="176e5-121">MDX Query Fundamentals &#40;Analysis Services&#41;</span></span>](mdx-query-fundamentals-analysis-services.md)  
  
  
