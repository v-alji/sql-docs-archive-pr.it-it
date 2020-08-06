---
title: Funzione InScope (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: a8cd209a-e5d3-4dce-ab2d-f271f6c54955
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 62c4ad5de7af1ac0762df29deaa17953a8a378db
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628421"
---
# <a name="inscope-function-report-builder-and-ssrs"></a><span data-ttu-id="d288b-102">Funzione InScope (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="d288b-102">InScope Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="d288b-103">Indica se l'istanza corrente di un elemento è inclusa nell'ambito specificato.</span><span class="sxs-lookup"><span data-stu-id="d288b-103">Indicates whether the current instance of an item is in the specified scope.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="d288b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d288b-104">Syntax</span></span>  
  
```  
InScope(scope)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d288b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d288b-105">Parameters</span></span>  
 <span data-ttu-id="d288b-106">*ambito*</span><span class="sxs-lookup"><span data-stu-id="d288b-106">*scope*</span></span>  
 <span data-ttu-id="d288b-107">(`String`) Nome di un set di dati, area dati o gruppo che specifica un ambito.</span><span class="sxs-lookup"><span data-stu-id="d288b-107">(`String`) The name of a dataset, data region, or group that specifies a scope.</span></span>  
  
## <a name="return-type"></a><span data-ttu-id="d288b-108">Tipo restituito</span><span class="sxs-lookup"><span data-stu-id="d288b-108">Return Type</span></span>  
 <span data-ttu-id="d288b-109">Restituisce un valore `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="d288b-109">Returns a `Boolean`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d288b-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="d288b-110">Remarks</span></span>  
 <span data-ttu-id="d288b-111">La `InScope` funzione testa l'ambito dell'istanza corrente di un elemento del report per l'appartenenza all'ambito specificato dal parametro *scope*.</span><span class="sxs-lookup"><span data-stu-id="d288b-111">The `InScope` function tests the scope of the current instance of a report item for membership in the scope specified by the *scope*parameter.</span></span>  
  
 <span data-ttu-id="d288b-112">*Scope* non può essere un'espressione.</span><span class="sxs-lookup"><span data-stu-id="d288b-112">*Scope* cannot be an expression.</span></span>  
  
 <span data-ttu-id="d288b-113">La funzione `InScope` viene tipicamente utilizzata nelle aree dati con ambito dinamico.</span><span class="sxs-lookup"><span data-stu-id="d288b-113">A typical use for the `InScope` function is in data regions that have dynamic scoping.</span></span> <span data-ttu-id="d288b-114">È ad esempio possibile utilizzare `InScope` in un collegamento drill-through nelle celle di un'area dati per specificare un nome di report diverso e set di parametri diversi a seconda della cella su cui si fa clic.</span><span class="sxs-lookup"><span data-stu-id="d288b-114">For example, `InScope` can be used in a drillthrough link in a data region cells to provide a different report name and different sets of parameters depending on which cell is clicked.</span></span> <span data-ttu-id="d288b-115">Di seguito viene riportato un esempio:</span><span class="sxs-lookup"><span data-stu-id="d288b-115">An example of this is as follows:</span></span>  
  
-   <span data-ttu-id="d288b-116">L'espressione seguente, usata come nome del report in un collegamento drill-through, apre il report `ProductDetail` se la cella su cui si fa clic si trova nel gruppo `Month` e il report `ProductSummary` in caso contrario.</span><span class="sxs-lookup"><span data-stu-id="d288b-116">The following expression, used as the report name in a drillthrough link, opens the `ProductDetail` report if the clicked cell is in the `Month` group, and the `ProductSummary` report if it is not.</span></span>  
  
    ```  
    =Iif(InScope("Month"), "ProductDetail", "ProductSummary")  
    ```  
  
-   <span data-ttu-id="d288b-117">L'espressione seguente, utilizzata nella proprietà `Omit` di un parametro di report drill-through, passerà il parametro al report di destinazione solo se la cella su cui viene fatto clic si trova nel gruppo `Product`.</span><span class="sxs-lookup"><span data-stu-id="d288b-117">The following expression, used in the `Omit` property of a drillthrough report parameter, will pass the parameter to the target report only if the clicked cell is in the `Product` group.</span></span>  
  
    ```  
    =Not(InScope("Product"))  
    ```  
  
 <span data-ttu-id="d288b-118">Per altre informazioni, vedere [Riferimento a funzioni di aggregazione &#40;Generatore report e SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) e [Ambito di espressioni per totali, aggregazioni e raccolte predefinite &#40;Generatore report e SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="d288b-118">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) and [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d288b-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="d288b-119">Example</span></span>  
 <span data-ttu-id="d288b-120">Il codice di esempio seguente indica se l'istanza corrente dell'elemento si trova nell'ambito del set di dati, area dati o gruppo `Product` .</span><span class="sxs-lookup"><span data-stu-id="d288b-120">The following code example indicates whether the current instance of the item is in the `Product` dataset, data region, or group scope.</span></span>  
  
```  
=InScope("Product")  
```  
  
## <a name="see-also"></a><span data-ttu-id="d288b-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d288b-121">See Also</span></span>  
 <span data-ttu-id="d288b-122">[Utilizzo delle espressioni nei report &#40;Generatore report e SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d288b-122">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="d288b-123">[Esempi di espressioni &#40;Generatore report e SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d288b-123">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="d288b-124">[Tipi di dati nelle espressioni &#40;Generatore report e SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d288b-124">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="d288b-125">Ambito di espressioni per totali, aggregazioni e raccolte predefinite &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="d288b-125">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
