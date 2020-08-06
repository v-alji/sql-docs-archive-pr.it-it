---
title: Creazione di set denominati con ambito query (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- query-scoped named sets [MDX]
- WITH keyword
ms.assetid: 78bc1e9a-1bc4-4a5a-ab0b-cf430c8fbfe1
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6eccb4e20fca03079a04a0219b07f6411b80a433
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714639"
---
# <a name="creating-query-scoped-named-sets-mdx"></a><span data-ttu-id="be9eb-102">Creazione di set denominati con ambito query (MDX)</span><span class="sxs-lookup"><span data-stu-id="be9eb-102">Creating Query-Scoped Named Sets (MDX)</span></span>
  <span data-ttu-id="be9eb-103">Se un set denominato è richiesto esclusivamente per una sola query MDX (Multidimensional Expressions), è possibile definirlo specificando la parola chiave WITH.</span><span class="sxs-lookup"><span data-stu-id="be9eb-103">If a named set is only required for a single Multidimensional Expressions (MDX) query, you can define that named set by using the WITH keyword.</span></span> <span data-ttu-id="be9eb-104">Un set denominato creato specificando questa parola chiave non esiste più dopo l'esecuzione della query.</span><span class="sxs-lookup"><span data-stu-id="be9eb-104">A named set that is created by using the WITH keyword no longer exists after the query has finished running.</span></span>  
  
 <span data-ttu-id="be9eb-105">Come descritto in questo argomento, la sintassi della parola chiave WITH è piuttosto flessibile e consente addirittura di definire un set denominato tramite l'utilizzo di funzioni.</span><span class="sxs-lookup"><span data-stu-id="be9eb-105">As discussed in this topic, the syntax of the WITH keyword is quite flexible, even accommodating the use of functions to define the named set.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="be9eb-106">Per altre informazioni sui set denominati, vedere [Compilazione di set denominati in MDX &#40;MDX&#41;](mdx-named-sets-building-named-sets.md).</span><span class="sxs-lookup"><span data-stu-id="be9eb-106">For more information about named sets, see [Building Named Sets in MDX &#40;MDX&#41;](mdx-named-sets-building-named-sets.md).</span></span>  
  
## <a name="with-keyword-syntax"></a><span data-ttu-id="be9eb-107">Sintassi della parola chiave WITH</span><span class="sxs-lookup"><span data-stu-id="be9eb-107">WITH Keyword Syntax</span></span>  
 <span data-ttu-id="be9eb-108">Per aggiungere la parola chiave WITH a un'istruzione MDX SELECT, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="be9eb-108">Use the following syntax to add the WITH keyword to a MDX SELECT statement:</span></span>  
  
```  
[ WITH <SELECT WITH clause> [ , <SELECT WITH clause> ... ] ]   
SELECT [ * | ( <SELECT query axis clause> [ , <SELECT query axis clause> ... ] ) ]  
FROM <SELECT subcube clause>   
[ <SELECT slicer axis clause> ]  
[ <SELECT cell property list clause> ]  
  
<SELECT WITH clause> ::=  
   ( SET Set_Identifier AS 'Set_Expression')  
  
```  
  
 <span data-ttu-id="be9eb-109">Il parametro `Set_Identifier` include l'alias del set denominato.</span><span class="sxs-lookup"><span data-stu-id="be9eb-109">In the syntax for the WITH keyword, the `Set_Identifier` parameter contains the alias for the named set.</span></span> <span data-ttu-id="be9eb-110">Il parametro `Set_Expression` include l'espressione set a cui fa riferimento l'alias del set denominato.</span><span class="sxs-lookup"><span data-stu-id="be9eb-110">The `Set_Expression` parameter contains the set expression to which the named set alias refers.</span></span>  
  
## <a name="with-keyword-example"></a><span data-ttu-id="be9eb-111">Esempio della parola chiave WITH</span><span class="sxs-lookup"><span data-stu-id="be9eb-111">WITH Keyword Example</span></span>  
 <span data-ttu-id="be9eb-112">Nella query MDX seguente vengono esaminate le vendite unitarie dei vari vini Chardonnay e Chablis in `FoodMart 2000`, il database di esempio per Microsoft SQL Server 2000 Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="be9eb-112">The following MDX query examines the unit sales of the various Chardonnay and Chablis wines in `FoodMart 2000`, the sample database for Microsoft SQL Server 2000 Analysis Services.</span></span> <span data-ttu-id="be9eb-113">Questa query, sebbene piuttosto semplice dal punto di vista del set di risultati, è lunga e laboriosa per quanto riguarda la manutenzione.</span><span class="sxs-lookup"><span data-stu-id="be9eb-113">This query, although fairly simple in terms of the result set, is lengthy and unwieldy when you have to maintenance such a query.</span></span>  
  
```  
SELECT  
   {[Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Good].[Good Chardonnay],   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Pearl].[Pearl Chardonnay],   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Portsmouth].[Portsmouth Chardonnay],   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Top Measure].[Top Measure Chardonnay],   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Walrus].[Walrus Chardonnay],   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Good].[Good Chablis Wine],   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Pearl].[Pearl Chablis Wine],   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Portsmouth].[Portsmouth Chablis Wine],   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Top Measure].[Top Measure Chablis Wine],   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Walrus].[Walrus Chablis Wine]} ON COLUMNS,  
   {Measures.[Unit Sales]} ON ROWS  
FROM Sales  
```  
  
 <span data-ttu-id="be9eb-114">Per semplificare la manutenzione della query, è possibile creare un set denominato specificando la parola chiave WITH.</span><span class="sxs-lookup"><span data-stu-id="be9eb-114">To make the previous MDX query easier to maintain, you can create a named set for the query by using the WITH keyword.</span></span> <span data-ttu-id="be9eb-115">Nel codice seguente viene illustrato l'utilizzo della parola chiave WITH per creare il set denominato `[ChardonnayChablis]`. Viene illustrato inoltre come grazie al set denominato l'istruzione SELECT risulti più breve e di più semplice manutenzione.</span><span class="sxs-lookup"><span data-stu-id="be9eb-115">The following code shows how to use the WITH keyword to create a named set, `[ChardonnayChablis]`, and how the named set makes the SELECT statement shorter and easier to maintain.</span></span>  
  
```  
WITH SET [ChardonnayChablis] AS  
   {[Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Good].[Good Chardonnay],  
   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Pearl].[Pearl Chardonnay],  
   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Portsmouth].[Portsmouth Chardonnay],  
   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Top Measure].[Top Measure Chardonnay],  
   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Walrus].[Walrus Chardonnay],  
   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Good].[Good Chablis Wine],  
   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Pearl].[Pearl Chablis Wine],  
   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Portsmouth].[Portsmouth Chablis Wine],  
   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Top Measure].[Top Measure Chablis Wine],  
   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Walrus].[Walrus Chablis Wine]}  
  
SELECT  
   [ChardonnayChablis] ON COLUMNS,  
   {Measures.[Unit Sales]} ON ROWS  
FROM Sales  
```  
  
### <a name="using-functions-together-with-the-with-keyword"></a><span data-ttu-id="be9eb-116">Utilizzo di funzioni insieme alla parola chiave WITH</span><span class="sxs-lookup"><span data-stu-id="be9eb-116">Using Functions Together with the WITH Keyword</span></span>  
 <span data-ttu-id="be9eb-117">Sebbene sia possibile definire ogni membro di un set denominato in modo esplicito, con questo approccio si potrebbe ottenere un'istruzione eccessivamente lunga.</span><span class="sxs-lookup"><span data-stu-id="be9eb-117">Although you can explicitly define each member of a named set, this approach can produce a lengthy statement.</span></span> <span data-ttu-id="be9eb-118">Per semplificare la creazione e la manutenzione di un set denominato, è possibile definirne i membri tramite funzioni MDX.</span><span class="sxs-lookup"><span data-stu-id="be9eb-118">To make the creation and maintenance of a named set easier, you can use MDX functions to define the members.</span></span>  
  
 <span data-ttu-id="be9eb-119">Nella query MDX seguente vengono ad esempio utilizzate le funzioni MDX [Filter](/sql/mdx/filter-mdx), [CurrentMember](/sql/mdx/current-mdx)e [Name](/sql/mdx/members-string-mdx) e la funzione VBA InStr per creare il set denominato `[ChardonnayChablis]` .</span><span class="sxs-lookup"><span data-stu-id="be9eb-119">For example, the following MDX query example uses the [Filter](/sql/mdx/filter-mdx), [CurrentMember](/sql/mdx/current-mdx), and [Name](/sql/mdx/members-string-mdx) MDX functions and the InStr VBA function to create the `[ChardonnayChablis]` named set.</span></span> <span data-ttu-id="be9eb-120">Questa versione del set denominato `[ChardonnayChablis]` è equivalente alla versione definita in modo esplicito descritta più indietro in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="be9eb-120">This version of the `[ChardonnayChablis]` named set is the same as the explicitly defined version shown previously in this topic.</span></span>  
  
```  
WITH SET [ChardonnayChablis] AS  
   'Filter([Product].Members, (InStr(1, [Product].CurrentMember.Name, "chardonnay") <> 0) OR (InStr(1, [Product].CurrentMember.Name, "chablis") <> 0))'  
  
SELECT  
   [ChardonnayChablis] ON COLUMNS,  
   {Measures.[Unit Sales]} ON ROWS  
FROM Sales  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="be9eb-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="be9eb-121">See Also</span></span>  
 <span data-ttu-id="be9eb-122">[Istruzione SELECT &#40;MDX&#41;](/sql/mdx/mdx-data-manipulation-select) </span><span class="sxs-lookup"><span data-stu-id="be9eb-122">[SELECT Statement &#40;MDX&#41;](/sql/mdx/mdx-data-manipulation-select) </span></span>  
 [<span data-ttu-id="be9eb-123">Creazione di set denominati con ambito sessione &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="be9eb-123">Creating Session-Scoped Named Sets &#40;MDX&#41;</span></span>](mdx-named-sets-creating-session-scoped-named-sets.md)  
  
  
