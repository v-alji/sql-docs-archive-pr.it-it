---
title: Utilizzo delle proprietà membro (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- DIMENSION PROPERTIES keyword
- Properties function
- member properties [MDX]
- members [MDX], properties
ms.assetid: 26b5ad08-3799-4a5e-89f3-dca25e637d45
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5b7fdf989fc23ea70be7d7863f5d4c6ac0b61d8a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714635"
---
# <a name="using-member-properties-mdx"></a><span data-ttu-id="f26dd-102">Utilizzo delle proprietà dei membri (MDX)</span><span class="sxs-lookup"><span data-stu-id="f26dd-102">Using Member Properties (MDX)</span></span>
  <span data-ttu-id="f26dd-103">Le proprietà dei membri contengono informazioni di base su ogni membro di ogni tupla.</span><span class="sxs-lookup"><span data-stu-id="f26dd-103">Member properties cover the basic information about each member in each tuple.</span></span> <span data-ttu-id="f26dd-104">Tali informazioni di base includono il nome del membro, il livello padre, il numero di elementi figli e così via.</span><span class="sxs-lookup"><span data-stu-id="f26dd-104">This basic information includes the member name, parent level, the number of children, and so on.</span></span> <span data-ttu-id="f26dd-105">Le proprietà dei membri sono disponibili per tutti i membri a un livello specifico.</span><span class="sxs-lookup"><span data-stu-id="f26dd-105">Member properties are available for all members at a given level.</span></span> <span data-ttu-id="f26dd-106">Per quanto riguarda l'organizzazione, le proprietà dei membri vengono gestite come dati organizzati a livello di dimensione, archiviati in una singola dimensione.</span><span class="sxs-lookup"><span data-stu-id="f26dd-106">In terms of organization, member properties are treated as dimensionally organized data, stored on a single dimension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f26dd-107">In [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]le proprietà dei membri sono dette relazioni tra attributi.</span><span class="sxs-lookup"><span data-stu-id="f26dd-107">In [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], member properties are know as attribute relationships.</span></span> <span data-ttu-id="f26dd-108">Per altre informazioni, vedere [Relazioni tra attributi](../../multidimensional-models-olap-logical-dimension-objects/attribute-relationships.md).</span><span class="sxs-lookup"><span data-stu-id="f26dd-108">For more information, see [Attribute Relationships](../../multidimensional-models-olap-logical-dimension-objects/attribute-relationships.md).</span></span>  
  
 <span data-ttu-id="f26dd-109">Le proprietà dei membri possono essere *intrinseche* o *personalizzate*:</span><span class="sxs-lookup"><span data-stu-id="f26dd-109">Member properties are either *intrinsic* or *custom*:</span></span>  
  
 <span data-ttu-id="f26dd-110">Proprietà intrinseche dei membri</span><span class="sxs-lookup"><span data-stu-id="f26dd-110">Intrinsic member properties</span></span>  
 <span data-ttu-id="f26dd-111">Tutti i membri supportano le proprietà intrinseche dei membri, ad esempio il valore formattato di un membro, mentre per le dimensioni e i livelli sono disponibili ulteriori proprietà intrinseche dei membri per livelli e dimensioni, quale l'ID di un membro.</span><span class="sxs-lookup"><span data-stu-id="f26dd-111">All members support intrinsic member properties, such as the formatted value of a member, while dimensions and levels supply additional intrinsic dimension and level member properties, such as the ID of a member.</span></span>  
  
 <span data-ttu-id="f26dd-112">Per altre informazioni, vedere [Proprietà intrinseche dei membri &#40;MDX&#41;](mdx-member-properties-intrinsic-member-properties.md).</span><span class="sxs-lookup"><span data-stu-id="f26dd-112">For more information, see [Intrinsic Member Properties &#40;MDX&#41;](mdx-member-properties-intrinsic-member-properties.md).</span></span>  
  
 <span data-ttu-id="f26dd-113">Proprietà dei membri definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="f26dd-113">User-defined member properties</span></span>  
 <span data-ttu-id="f26dd-114">Ai membri sono spesso associate proprietà aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="f26dd-114">Members often have additional properties associated with them.</span></span> <span data-ttu-id="f26dd-115">Il livello Products, ad esempio, può includere le proprietà SKU, SRP, Weight e Volume per ogni prodotto.</span><span class="sxs-lookup"><span data-stu-id="f26dd-115">For example, the Products level may offer the SKU, SRP, Weight, and Volume properties for each product.</span></span> <span data-ttu-id="f26dd-116">Tali proprietà non sono membri, ma includono informazioni aggiuntive sui membri del livello Products.</span><span class="sxs-lookup"><span data-stu-id="f26dd-116">These properties are not members, but contain additional information about members at the Products level.</span></span>  
  
 <span data-ttu-id="f26dd-117">Per altre informazioni, vedere [Proprietà dei membri definite dall'utente &#40;MDX&#41;](mdx-member-properties-user-defined-member-properties.md).</span><span class="sxs-lookup"><span data-stu-id="f26dd-117">For more information, see [User-Defined Member Properties &#40;MDX&#41;](mdx-member-properties-user-defined-member-properties.md).</span></span>  
  
 <span data-ttu-id="f26dd-118">Sia le proprietà intrinseche dei membri che quelle definite dall'utente possono essere recuperate usando la `PROPERTIES` parola chiave o la funzione [Properties](/sql/mdx/properties-mdx) .</span><span class="sxs-lookup"><span data-stu-id="f26dd-118">Both intrinsic and user-defined member properties can be retrieved through the use of the `PROPERTIES` keyword or the [Properties](/sql/mdx/properties-mdx) function.</span></span>  
  
## <a name="using-the-properties-keyword"></a><span data-ttu-id="f26dd-119">Utilizzo della parola chiave PROPERTIES</span><span class="sxs-lookup"><span data-stu-id="f26dd-119">Using the PROPERTIES Keyword</span></span>  
 <span data-ttu-id="f26dd-120">La parola chiave `PROPERTIES` specifica le proprietà dei membri che devono essere utilizzate per una determinata dimensione dell'asse.</span><span class="sxs-lookup"><span data-stu-id="f26dd-120">The `PROPERTIES` keyword specifies the member properties that are to be used for a given axis dimension.</span></span> <span data-ttu-id="f26dd-121">La `PROPERTIES` parola chiave viene nascosta all'interno della `<axis specification>` clausola dell'istruzione MDX [Select](/sql/mdx/mdx-data-manipulation-select) :</span><span class="sxs-lookup"><span data-stu-id="f26dd-121">The `PROPERTIES` keyword is buried within the `<axis specification>` clause of the MDX [SELECT](/sql/mdx/mdx-data-manipulation-select) statement:</span></span>  
  
```  
SELECT [<axis_specification>  
       [, <axis_specification>...]]  
  FROM [<cube_specification>]  
[WHERE [<slicer_specification>]]  
```  
  
 <span data-ttu-id="f26dd-122">La clausola `<axis_specification>` include la clausola facoltativa `<dim_props>` , come illustrato nella sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="f26dd-122">The `<axis_specification>` clause includes an optional `<dim_props>` clause, as shown in the following syntax:</span></span>  
  
```  
<axis_specification> ::= <set> [<dim_props>] ON <axis_name>  
```  
  
> [!NOTE]  
>  <span data-ttu-id="f26dd-123">Per altre informazioni sui valori di `<set>` e `<axis_name>`, vedere [Impostazione del contenuto di un asse della query &#40;MDX&#41;](mdx-query-and-slicer-axes-specify-the-contents-of-a-query-axis.md).</span><span class="sxs-lookup"><span data-stu-id="f26dd-123">For more information about the `<set>` and `<axis_name>` values, see [Specifying the Contents of a Query Axis &#40;MDX&#41;](mdx-query-and-slicer-axes-specify-the-contents-of-a-query-axis.md).</span></span>  
  
 <span data-ttu-id="f26dd-124">La clausola `<dim_props>` consente di eseguire query sulle proprietà di dimensioni, livelli e membri, tramite la parola chiave `PROPERTIES`.</span><span class="sxs-lookup"><span data-stu-id="f26dd-124">The `<dim_props>` clause lets you query dimension, level, and member properties using the `PROPERTIES` keyword.</span></span> <span data-ttu-id="f26dd-125">Il formato della clausola `<dim_props>` è illustrato nella sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="f26dd-125">The following syntax shows the formatting of the `<dim_props>` clause:</span></span>  
  
```  
<dim_props> ::= [DIMENSION] PROPERTIES <property> [,<property>...]  
```  
  
 <span data-ttu-id="f26dd-126">Il dettaglio della sintassi di `<property>` dipende dalla proprietà su cui viene eseguita la query:</span><span class="sxs-lookup"><span data-stu-id="f26dd-126">The breakdown of the `<property>` syntax varies depending on the property that you are querying:</span></span>  
  
-   <span data-ttu-id="f26dd-127">Le proprietà dei membri intrinseche e sensibili al contesto devono essere precedute dal nome della dimensione o del livello.</span><span class="sxs-lookup"><span data-stu-id="f26dd-127">Context sensitive intrinsic member properties must be preceded with the name of the dimension or level.</span></span> <span data-ttu-id="f26dd-128">Le proprietà dei membri intrinseche e non sensibili al contesto non possono essere invece qualificate dal nome della dimensione o del livello.</span><span class="sxs-lookup"><span data-stu-id="f26dd-128">However, non-context sensitive intrinsic member properties cannot be qualified by the dimension or level name.</span></span> <span data-ttu-id="f26dd-129">Per ulteriori informazioni sull'utilizzo della `PROPERTIES` parola chiave con le proprietà intrinseche dei membri, vedere [proprietà intrinseche dei membri &#40;&#41;MDX ](mdx-member-properties-intrinsic-member-properties.md).</span><span class="sxs-lookup"><span data-stu-id="f26dd-129">For more information about how to use the `PROPERTIES` keyword with intrinsic member properties, see [Intrinsic Member Properties &#40;MDX&#41;](mdx-member-properties-intrinsic-member-properties.md).</span></span>  
  
-   <span data-ttu-id="f26dd-130">Le proprietà dei membri definite dall'utente devono essere precedute dal nome del livello in cui si trovano.</span><span class="sxs-lookup"><span data-stu-id="f26dd-130">User-defined member properties should be preceded by the name of the level in which they reside.</span></span> <span data-ttu-id="f26dd-131">Per ulteriori informazioni sull'utilizzo della `PROPERTIES` parola chiave con le proprietà dei membri definite dall'utente, vedere [proprietà dei membri definite dall'utente &#40;&#41;MDX ](mdx-member-properties-user-defined-member-properties.md).</span><span class="sxs-lookup"><span data-stu-id="f26dd-131">For more information about how to use the `PROPERTIES` keyword with user-defined member properties, see [User-Defined Member Properties &#40;MDX&#41;](mdx-member-properties-user-defined-member-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f26dd-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f26dd-132">See Also</span></span>  
 [<span data-ttu-id="f26dd-133">Creazione e utilizzo di valori di proprietà &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="f26dd-133">Creating and Using Property Values &#40;MDX&#41;</span></span>](../../creating-and-using-property-values-mdx.md)  
  
  
