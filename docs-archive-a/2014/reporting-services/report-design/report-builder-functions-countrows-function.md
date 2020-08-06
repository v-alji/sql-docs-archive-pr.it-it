---
title: Funzione CountRows (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 5b1c403d-6afd-44c8-b5f6-5ecff2a29a45
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 6d5311dfc5dfcb89449a4039fdac4100fc5a3b47
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628428"
---
# <a name="countrows-function-report-builder-and-ssrs"></a><span data-ttu-id="81f0f-102">Funzione CountRows (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="81f0f-102">CountRows Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="81f0f-103">Restituisce il numero di righe nell'ambito specificato, incluse le righe con valori Null.</span><span class="sxs-lookup"><span data-stu-id="81f0f-103">Returns the number of rows in the specified scope, including rows with null values.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="81f0f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="81f0f-104">Syntax</span></span>  
  
```  
  
CountRows(scope, recursive)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="81f0f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="81f0f-105">Parameters</span></span>  
 <span data-ttu-id="81f0f-106">*ambito*</span><span class="sxs-lookup"><span data-stu-id="81f0f-106">*scope*</span></span>  
 <span data-ttu-id="81f0f-107">(`String`) Nome di un set di dati, area dati o gruppo che contiene gli elementi del report da conteggiare.</span><span class="sxs-lookup"><span data-stu-id="81f0f-107">(`String`) The name of a dataset, data region, or group that contains the report items to count.</span></span>  
  
 <span data-ttu-id="81f0f-108">*ricorsivi*</span><span class="sxs-lookup"><span data-stu-id="81f0f-108">*recursive*</span></span>  
 <span data-ttu-id="81f0f-109">(**Enumerated Type**) Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="81f0f-109">(**Enumerated Type**) Optional.</span></span> <span data-ttu-id="81f0f-110">`Simple` (valore predefinito) o `RdlRecursive`.</span><span class="sxs-lookup"><span data-stu-id="81f0f-110">`Simple` (default) or `RdlRecursive`.</span></span> <span data-ttu-id="81f0f-111">Specifica se eseguire l'aggregazione in modo ricorsivo.</span><span class="sxs-lookup"><span data-stu-id="81f0f-111">Specifies whether to perform the aggregation recursively.</span></span>  
  
## <a name="return-type"></a><span data-ttu-id="81f0f-112">Tipo restituito</span><span class="sxs-lookup"><span data-stu-id="81f0f-112">Return Type</span></span>  
 <span data-ttu-id="81f0f-113">Restituisce un valore `Integer`.</span><span class="sxs-lookup"><span data-stu-id="81f0f-113">Returns an `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="81f0f-114">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="81f0f-114">Remarks</span></span>  
 <span data-ttu-id="81f0f-115">`CountRows` conteggia tutte le righe nell'ambito specificato, incluse le righe con valori Null.</span><span class="sxs-lookup"><span data-stu-id="81f0f-115">`CountRows` counts all rows in the specified scope, including rows that have null values.</span></span>  
  
 <span data-ttu-id="81f0f-116">Il valore di *scope* non può essere un'espressione e deve fare riferimento all'ambito corrente o a un ambito di contenuto.</span><span class="sxs-lookup"><span data-stu-id="81f0f-116">The value of *scope* cannot be an expression and must refer to the current scope or a containing scope.</span></span>  
  
 <span data-ttu-id="81f0f-117">Per altre informazioni, vedere [Riferimento a funzioni di aggregazione &#40;Generatore report e SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) e [Ambito di espressioni per totali, aggregazioni e raccolte predefinite &#40;Generatore report e SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="81f0f-117">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) and [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
 <span data-ttu-id="81f0f-118">Per altre informazioni sulle aggregazioni ricorsive, vedere [Creazione di gruppi di gerarchie ricorsive &#40;Generatore report e SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="81f0f-118">For more information about recursive aggregates, see [Creating Recursive Hierarchy Groups &#40;Report Builder and SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="81f0f-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="81f0f-119">Example</span></span>  
 <span data-ttu-id="81f0f-120">Nell'esempio di codice seguente è illustrata un'espressione che calcola il numero di righe in un gruppo di righe denominato `GroupbyCategory` (in base all'espressione `[Category]`).</span><span class="sxs-lookup"><span data-stu-id="81f0f-120">The following code example shows an expression that calculates the number of rows in a row group named `GroupbyCategory` (based on the expression `[Category]`).</span></span>  
  
```  
="Number of rows: " & CountRows("GroupbyCategory")  
```  
  
## <a name="see-also"></a><span data-ttu-id="81f0f-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="81f0f-121">See Also</span></span>  
 <span data-ttu-id="81f0f-122">[Utilizzo delle espressioni nei report &#40;Generatore report e SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="81f0f-122">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="81f0f-123">[Esempi di espressioni &#40;Generatore report e SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="81f0f-123">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="81f0f-124">[Tipi di dati nelle espressioni &#40;Generatore report e SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="81f0f-124">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="81f0f-125">Ambito di espressioni per totali, aggregazioni e raccolte predefinite &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="81f0f-125">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
