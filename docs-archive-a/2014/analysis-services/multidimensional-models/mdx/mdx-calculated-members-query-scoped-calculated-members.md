---
title: Creazione di membri calcolati con ambito query (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- WITH keyword
- query-scoped calculated members [MDX]
ms.assetid: c4507149-e67b-4e5d-9192-cc911acd9adc
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9c0b3e7184f3cc6abd189344bbce1b6e1f948ebb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627444"
---
# <a name="creating-query-scoped-calculated-members-mdx"></a><span data-ttu-id="7f4fe-102">Creazione di membri calcolati con ambito query (MDX)</span><span class="sxs-lookup"><span data-stu-id="7f4fe-102">Creating Query-Scoped Calculated Members (MDX)</span></span>
  <span data-ttu-id="7f4fe-103">Se un membro calcolato è necessario solo per un'unica query MDX (Multidimensional Expression), è possibile definire tale membro calcolato mediante la parola chiave WITH.</span><span class="sxs-lookup"><span data-stu-id="7f4fe-103">If a calculated member is only required for a single Multidimensional Expressions (MDX) query, you can define that calculated member by using the WITH keyword.</span></span> <span data-ttu-id="7f4fe-104">Un membro calcolato creato utilizzando la parola chiave WITH non esisterà più al termine dell'esecuzione della query.</span><span class="sxs-lookup"><span data-stu-id="7f4fe-104">A calculated member that is created by using the WITH keyword no longer exists after the query has finished running.</span></span>  
  
 <span data-ttu-id="7f4fe-105">Come illustrato in questo argomento, la sintassi della parola chiave WITH è molto flessibile e consente addirittura di basare un membro calcolato su un altro membro calcolato.</span><span class="sxs-lookup"><span data-stu-id="7f4fe-105">As discussed in this topic, the syntax of the WITH keyword is quite flexible, even allowing a calculated member to be based on another calculated member.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7f4fe-106">Per altre informazioni sui membri calcolati, vedere [Compilazione di membri calcolati in MDX &#40;MDX&#41;](mdx-calculated-members-building-calculated-members.md).</span><span class="sxs-lookup"><span data-stu-id="7f4fe-106">For more information about calculated members, see [Building Calculated Members in MDX &#40;MDX&#41;](mdx-calculated-members-building-calculated-members.md).</span></span>  
  
## <a name="with-keyword-syntax"></a><span data-ttu-id="7f4fe-107">Sintassi della parola chiave WITH</span><span class="sxs-lookup"><span data-stu-id="7f4fe-107">WITH Keyword Syntax</span></span>  
 <span data-ttu-id="7f4fe-108">Utilizzare la sintassi seguente per aggiungere la parola chiave WITH a un'istruzione SELECT MDX:</span><span class="sxs-lookup"><span data-stu-id="7f4fe-108">Use the following syntax to add the WITH keyword to an MDX SELECT statement:</span></span>  
  
```  
[ WITH <SELECT WITH clause> [ , <SELECT WITH clause> ... ] ] SELECT [ * | ( <SELECT query axis clause> [ , <SELECT query axis clause> ... ] ) ]FROM <SELECT subcube clause> [ <SELECT slicer axis clause> ][ <SELECT cell property list clause> ]  
<SELECT WITH clause> ::=  
   ( [ CALCULATED ] MEMBER <CREATE MEMBER body clause>) | <CREATE MEMBER body clause> ::= Member_Identifier AS 'MDX_Expression'  
   [ <CREATE MEMBER property clause> [ , <CREATE MEMBER property clause> ... ] ]  
<CREATE MEMBER property clause> ::=  
   ( MemberProperty_Identifier = Scalar_Expression )  
  
```  
  
 <span data-ttu-id="7f4fe-109">Nella sintassi della parola chiave WITH il valore `Member_Identifier` rappresenta il nome completo del membro calcolato.</span><span class="sxs-lookup"><span data-stu-id="7f4fe-109">In the syntax for the WITH keyword, the `Member_Identifier` value is the fully qualified name of the calculated member.</span></span> <span data-ttu-id="7f4fe-110">Il nome completo include la dimensione o il livello a cui è associato il membro calcolato.</span><span class="sxs-lookup"><span data-stu-id="7f4fe-110">This fully qualified name includes the dimension or level to which the calculated member is associated.</span></span> <span data-ttu-id="7f4fe-111">Il valore `MDX_Expression` restituisce il valore del membro calcolato dopo la valutazione del valore dell'espressione.</span><span class="sxs-lookup"><span data-stu-id="7f4fe-111">The `MDX_Expression` value returns the value of the calculated member after the expression value has been evaluated.</span></span> <span data-ttu-id="7f4fe-112">È possibile specificare i valori delle proprietà della cella intrinseche per un membro calcolato, se si desidera, indicando il nome della proprietà della cella nel valore `MemberProperty_Identifier` e il valore della proprietà della cella nel valore `Scalar_Expression` .</span><span class="sxs-lookup"><span data-stu-id="7f4fe-112">The values of intrinsic cell properties for a calculated member can be optionally specified by supplying the name of the cell property in the `MemberProperty_Identifier` value and the value of the cell property in the `Scalar_Expression` value.</span></span>  
  
## <a name="with-keyword-examples"></a><span data-ttu-id="7f4fe-113">Esempi di parola chiave WITH</span><span class="sxs-lookup"><span data-stu-id="7f4fe-113">WITH Keyword Examples</span></span>  
 <span data-ttu-id="7f4fe-114">La query MDX seguente definisce un membro calcolato, `[Measures].[Special Discount]`, che esegue il calcolo di uno sconto speciale in base all'importo dello sconto originale.</span><span class="sxs-lookup"><span data-stu-id="7f4fe-114">The following MDX query defines a calculated member, `[Measures].[Special Discount]`, calculating a special discount based on the original discount amount.</span></span>  
  
```  
WITH   
   MEMBER [Measures].[Special Discount] AS  
   [Measures].[Discount Amount] * 1.5  
SELECT   
   [Measures].[Special Discount] on COLUMNS,  
   NON EMPTY [Product].[Product].MEMBERS  ON Rows  
FROM [Adventure Works]  
WHERE [Product].[Category].[Bikes]  
```  
  
 <span data-ttu-id="7f4fe-115">È inoltre possibile creare membri calcolati in un punto qualsiasi di una gerarchia.</span><span class="sxs-lookup"><span data-stu-id="7f4fe-115">You can also create calculated members at any point within a hierarchy.</span></span> <span data-ttu-id="7f4fe-116">La query MDX seguente, ad esempio, definisce il membro calcolato `[BigSeller]` per un cubo Sales ipotetico.</span><span class="sxs-lookup"><span data-stu-id="7f4fe-116">For example, the following MDX query defines the `[BigSeller]` calculated member for a hypothetical Sales cube.</span></span> <span data-ttu-id="7f4fe-117">Questo membro calcolato determina se un particolare punto vendita ha registrato almeno 100,00 nelle vendite unitarie di birra e vino.</span><span class="sxs-lookup"><span data-stu-id="7f4fe-117">This calculated member determines whether a specified store has at least 100.00 in unit sales for beer and wine.</span></span> <span data-ttu-id="7f4fe-118">La query, tuttavia, crea il membro calcolato `[BigSeller]` non come membro figlio della dimensione `[Product]` ma come membro figlio del membro `[Beer and Wine]` .</span><span class="sxs-lookup"><span data-stu-id="7f4fe-118">However, the query creates the `[BigSeller]` calculated member not as a child member of the `[Product]` dimension, but instead as a child member of the `[Beer and Wine]` member.</span></span>  
  
```  
WITH   
   MEMBER [Product].[Beer and Wine].[BigSeller] AS  
  IIf([Product].[Beer and Wine] > 100, "Yes","No")  
SELECT  
   {[Product].[BigSeller]} ON COLUMNS,  
   Store.[Store Name].Members ON ROWS  
FROM Sales  
  
```  
  
 <span data-ttu-id="7f4fe-119">I membri calcolati non devono necessariamente dipendere solo dai membri esistenti in un cubo.</span><span class="sxs-lookup"><span data-stu-id="7f4fe-119">Calculated members do not have to depend only on existing members in a cube.</span></span> <span data-ttu-id="7f4fe-120">Un membro calcolato può inoltre basarsi su altri membri calcolati definiti nella stessa espressione MDX.</span><span class="sxs-lookup"><span data-stu-id="7f4fe-120">Calculated member can also be based on other calculated members defined in the same MDX expression.</span></span> <span data-ttu-id="7f4fe-121">La query MDX seguente, ad esempio, utilizza il valore creato nel primo membro calcolato, `[Measures].[Special Discount]`, per generare il valore del secondo membro calcolato, `[Measures].[Special Discounted Amount]`.</span><span class="sxs-lookup"><span data-stu-id="7f4fe-121">For example, the following MDX query uses the value created in the first calculated member, `[Measures].[Special Discount]`, to generate the value of the second calculated member, `[Measures].[Special Discounted Amount]`.</span></span>  
  
```  
WITH   
   MEMBER [Measures].[Special Discount] AS  
   [Measures].[Discount Percentage] * 1.5,   
   FORMAT_STRING = 'Percent'  
  
   MEMBER [Measures].[Special Discounted Amount] AS  
   [Measures].[Reseller Average Unit Price] * [Measures].[Special Discount],   
   FORMAT_STRING = 'Currency'  
  
SELECT   
   {[Measures].[Special Discount], [Measures].[Special Discounted Amount]} on COLUMNS,  
   NON EMPTY [Product].[Product].MEMBERS  ON Rows  
FROM [Adventure Works]  
WHERE [Product].[Category].[Bikes]  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="7f4fe-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7f4fe-122">See Also</span></span>  
 <span data-ttu-id="7f4fe-123">[Guida di riferimento alle funzioni MDX &#40;&#41;MDX](/sql/mdx/mdx-function-reference-mdx) </span><span class="sxs-lookup"><span data-stu-id="7f4fe-123">[MDX Function Reference &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx) </span></span>  
 <span data-ttu-id="7f4fe-124">[Istruzione SELECT &#40;MDX&#41;](/sql/mdx/mdx-data-manipulation-select) </span><span class="sxs-lookup"><span data-stu-id="7f4fe-124">[SELECT Statement &#40;MDX&#41;](/sql/mdx/mdx-data-manipulation-select) </span></span>  
 [<span data-ttu-id="7f4fe-125">Creazione di membri calcolati con ambito sessione &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="7f4fe-125">Creating Session-Scoped Calculated Members &#40;MDX&#41;</span></span>](mdx-calculated-members-session-scoped-calculated-members.md)  
  
  
