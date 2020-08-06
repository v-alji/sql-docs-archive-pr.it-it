---
title: Creazione di membri calcolati con ambito sessione (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- CREATE MEMBER statement
- session-scoped calculated members [MDX]
ms.assetid: 2875ed89-2c26-4645-8ed9-8848479d110f
author: minewiskan
ms.author: owend
ms.openlocfilehash: 8fe7a9f137d8b74eaa5bad104dbfdb471dd14588
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635827"
---
# <a name="creating-session-scoped-calculated-members-mdx"></a><span data-ttu-id="7ccf9-102">Creazione di membri calcolati con ambito sessione (MDX)</span><span class="sxs-lookup"><span data-stu-id="7ccf9-102">Creating Session-Scoped Calculated Members (MDX)</span></span>
  <span data-ttu-id="7ccf9-103">Per creare un membro calcolato disponibile nell'ambito di un'intera sessione MDX (Multidimensional Expressions), è possibile usare l'istruzione [CREATE MEMBER](/sql/mdx/mdx-data-definition-create-member) .</span><span class="sxs-lookup"><span data-stu-id="7ccf9-103">To create a calculated member that is available throughout a Multidimensional Expressions (MDX) session, you use the [CREATE MEMBER](/sql/mdx/mdx-data-definition-create-member) statement.</span></span> <span data-ttu-id="7ccf9-104">Un membro calcolato creato utilizzando l'istruzione CREATE MEMBER non viene rimosso fino alla chiusura della sessione MDX.</span><span class="sxs-lookup"><span data-stu-id="7ccf9-104">A calculated member that is created by using the CREATE MEMBER statement will not be removed until after the MDX session closes.</span></span>  
  
 <span data-ttu-id="7ccf9-105">Come descritto in questo argomento, la sintassi dell'istruzione CREATE MEMBER è intuitiva e facile da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="7ccf9-105">As discussed in this topic, the syntax of the CREATE MEMBER statement is straightforward and easy to use.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7ccf9-106">Per altre informazioni sui membri calcolati, vedere [Compilazione di membri calcolati in MDX &#40;MDX&#41;](mdx-calculated-members-building-calculated-members.md).</span><span class="sxs-lookup"><span data-stu-id="7ccf9-106">For more information about calculated members, see [Building Calculated Members in MDX &#40;MDX&#41;](mdx-calculated-members-building-calculated-members.md).</span></span>  
  
## <a name="create-member-syntax"></a><span data-ttu-id="7ccf9-107">Sintassi dell'istruzione CREATE MEMBER</span><span class="sxs-lookup"><span data-stu-id="7ccf9-107">CREATE MEMBER Syntax</span></span>  
 <span data-ttu-id="7ccf9-108">Per aggiungere l'istruzione CREATE MEMBER a un'istruzione MDX, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="7ccf9-108">Use the following syntax to add the CREATE MEMBER statement to the MDX statement:</span></span>  
  
```  
CREATE [SESSION] MEMBER [<cube-name>.]<fully-qualified-member-name> AS <expression> [,<property-definition-list>]  
<cube name> ::= CURRENTCUBE | <Cube Name>  
<property-definition-list> ::= <property-definition>  
  | <property-definition>, <property-definition-list>  
<property-definition> ::= <property-identifier> = <property-value>  
<property-identifier> ::= VISIBLE | SOLVEORDER | SOLVE_ORDER | FORMAT_STRING | NON_EMPTY_BEHAVIOR <ole db member properties>  
```  
  
 <span data-ttu-id="7ccf9-109">Nella sintassi dell'istruzione CREATE MEMBER il valore `fully-qualified-member-name` rappresenta il nome completo del membro calcolato.</span><span class="sxs-lookup"><span data-stu-id="7ccf9-109">In the syntax for the CREATE MEMBER statement, the `fully-qualified-member-name` value is the fully qualified name of the calculated member.</span></span> <span data-ttu-id="7ccf9-110">Il nome completo include la dimensione o il livello a cui è associato il membro calcolato.</span><span class="sxs-lookup"><span data-stu-id="7ccf9-110">The fully qualified name includes the dimension or level to which the calculated member is associated.</span></span> <span data-ttu-id="7ccf9-111">Il valore `expression` restituisce il valore del membro calcolato dopo la valutazione del valore dell'espressione.</span><span class="sxs-lookup"><span data-stu-id="7ccf9-111">The `expression` value returns the value of the calculated member after the expression value has been evaluated,.</span></span>  
  
## <a name="create-member-example"></a><span data-ttu-id="7ccf9-112">Esempio sull'istruzione CREATE MEMBER</span><span class="sxs-lookup"><span data-stu-id="7ccf9-112">CREATE MEMBER Example</span></span>  
 <span data-ttu-id="7ccf9-113">Nell'esempio seguente l'istruzione CREATE MEMBER viene utilizzata per creare il membro calcolato `LastFourStores` ,</span><span class="sxs-lookup"><span data-stu-id="7ccf9-113">The following example uses the CREATE MEMBER statement to create the `LastFourStores` calculated member.</span></span> <span data-ttu-id="7ccf9-114">che restituisce la somma delle unità vendute negli ultimi quattro punti vendita e sarà disponibile per l'intera sessione del cubo.</span><span class="sxs-lookup"><span data-stu-id="7ccf9-114">This calculated member returns the sum of units sold for the last four stores, and will be available throughout the whole session of the cube.</span></span>  
  
```  
Create Session Member [Store].[Measures].LastFourStores as   
sum(([Stores].[ByLocation].Lag(3) :  
[Stores].[ByLocation].NextMember), [Measures].[Units Sold])  
```  
  
## <a name="see-also"></a><span data-ttu-id="7ccf9-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7ccf9-115">See Also</span></span>  
 [<span data-ttu-id="7ccf9-116">Creazione di membri calcolati con ambito query &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="7ccf9-116">Creating Query-Scoped Calculated Members &#40;MDX&#41;</span></span>](mdx-calculated-members-query-scoped-calculated-members.md)  
  
  
