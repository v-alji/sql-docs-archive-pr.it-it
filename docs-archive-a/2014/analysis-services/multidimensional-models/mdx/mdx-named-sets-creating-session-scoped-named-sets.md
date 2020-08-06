---
title: Creazione di set denominati con ambito sessione (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- CREATE SET statement
- session-scoped named sets [MDX]
ms.assetid: b751e1e4-6d4c-4d36-a28d-ffdaaee0f1c7
author: minewiskan
ms.author: owend
ms.openlocfilehash: d35bd61dcc59eca8bcb920ed99f2e791631047c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718786"
---
# <a name="creating-session-scoped-named-sets-mdx"></a><span data-ttu-id="31068-102">Creazione di set denominati con ambito sessione (MDX)</span><span class="sxs-lookup"><span data-stu-id="31068-102">Creating Session-Scoped Named Sets (MDX)</span></span>
  <span data-ttu-id="31068-103">Per creare un set denominato disponibile per un'intera sessione MDX (Multidimensional Expressions), è possibile usare l'istruzione [CREATE SET](/sql/mdx/mdx-data-definition-create-set) .</span><span class="sxs-lookup"><span data-stu-id="31068-103">To create a named set that is available throughout a Multidimensional Expressions (MDX) session, you use the [CREATE SET](/sql/mdx/mdx-data-definition-create-set) statement.</span></span> <span data-ttu-id="31068-104">Un set denominato creato utilizzando l'istruzione CREATE SET non viene rimosso fino alla chiusura della sessione MDX.</span><span class="sxs-lookup"><span data-stu-id="31068-104">A named set that is created by using the CREATE SET statement will not be removed until after the MDX session closes.</span></span>  
  
 <span data-ttu-id="31068-105">Come descritto in questo argomento, la sintassi della parola chiave WITH è intuitiva e facile da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="31068-105">As discussed in this topic, the syntax of the WITH keyword is straightforward and easy to use.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="31068-106">Per altre informazioni sui set denominati, vedere [Compilazione di set denominati in MDX &#40;MDX&#41;](mdx-named-sets-building-named-sets.md).</span><span class="sxs-lookup"><span data-stu-id="31068-106">For more information about named sets, see [Building Named Sets in MDX &#40;MDX&#41;](mdx-named-sets-building-named-sets.md).</span></span>  
  
## <a name="create-set-syntax"></a><span data-ttu-id="31068-107">Sintassi di CREATE SET</span><span class="sxs-lookup"><span data-stu-id="31068-107">CREATE SET Syntax</span></span>  
 <span data-ttu-id="31068-108">La sintassi dell'istruzione CREATE SET è la seguente:</span><span class="sxs-lookup"><span data-stu-id="31068-108">Use the following syntax for the CREATE SET statement:</span></span>  
  
```  
CREATE SESSION SET [CURRENTCUBE. | <cube name>.]<Set Identifier> AS <Set Expression>  
```  
  
 <span data-ttu-id="31068-109">Nella sintassi di CREATE SET il parametro `cube name` contiene il nome del cubo che include i membri per il set denominato.</span><span class="sxs-lookup"><span data-stu-id="31068-109">In the CREATE SET syntax, the `cube name` parameter contains the name of the cube that contains the members for the named set.</span></span> <span data-ttu-id="31068-110">Se il parametro `cube name` viene omesso, viene utilizzato il cubo corrente come cubo contenente il membro per il set denominato.</span><span class="sxs-lookup"><span data-stu-id="31068-110">If the `cube name` parameter is not specified, the current cube will be used as the cube that contains the member for the named set.</span></span> <span data-ttu-id="31068-111">Il parametro `Set_Identifier` contiene inoltre l'alias del set denominato e il parametro `Set_Expression` contiene l'espressione set a cui l'alias del set denominato farà riferimento.</span><span class="sxs-lookup"><span data-stu-id="31068-111">Also, the `Set_Identifier` parameter contains the alias for the named set, and the `Set_Expression` parameter contains the set expression to which the named set alias will refer.</span></span>  
  
## <a name="create-set-example"></a><span data-ttu-id="31068-112">Esempio di CREATE SET</span><span class="sxs-lookup"><span data-stu-id="31068-112">CREATE SET Example</span></span>  
 <span data-ttu-id="31068-113">Nell'esempio seguente l'istruzione CREATE SET viene utilizzata per creare il set denominato `SetCities_2_3` basato sul cubo Store.</span><span class="sxs-lookup"><span data-stu-id="31068-113">The following example uses the CREATE SET statement to create the `SetCities_2_3` named set based on the Store cube.</span></span> <span data-ttu-id="31068-114">I membri del set denominato `SetCities_2_3` sono i punti vendita presenti in City 2 e City 3.</span><span class="sxs-lookup"><span data-stu-id="31068-114">The members of the `SetCities_2_3` named set are the stores within City 2 and City 3.</span></span>  
  
```  
create Session set [Store].[SetCities_2_3] as  
{[Data Stores].[ByLocation].[State].&[CA].&[City 02],  
[Data Stores].[ByLocation].[State].&[NH].&[City 03]}  
```  
  
 <span data-ttu-id="31068-115">Poiché è stato definito utilizzando l'istruzione CREATE SET, il set denominato `SetCities_2_3` rimane disponibile per tutta la sessione MDX corrente.</span><span class="sxs-lookup"><span data-stu-id="31068-115">By using the CREATE SET statement to define the `SetCities_2_3` named set, this named set remains available for the length of the current MDX session.</span></span> <span data-ttu-id="31068-116">Nell'esempio seguente viene illustrata una query valida che restituisce i membri di City 2 e City 3 e può essere eseguita in qualsiasi momento dopo la creazione del set denominato `SetCities_2_3` e prima della chiusura della sessione.</span><span class="sxs-lookup"><span data-stu-id="31068-116">The following example is a valid query that would return City 2 and City 3 members, and that could be run anytime after you create the `SetCities_2_3` named set and before the session closes.</span></span>  
  
```  
select SetCities_2_3 on 0 from [Store]  
```  
  
## <a name="see-also"></a><span data-ttu-id="31068-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="31068-117">See Also</span></span>  
 [<span data-ttu-id="31068-118">Creazione di set denominati con ambito query &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="31068-118">Creating Query-Scoped Named Sets &#40;MDX&#41;</span></span>](mdx-named-sets-creating-query-scoped-named-sets.md)  
  
  
