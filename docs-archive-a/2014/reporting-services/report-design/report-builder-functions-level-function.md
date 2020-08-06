---
title: Funzione Level (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 41235402-bb9e-4cb7-b91e-431e77db19cf
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: dedbf00ce8330242c95e9592f649d95171f0987a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628419"
---
# <a name="level-function-report-builder-and-ssrs"></a><span data-ttu-id="f8b82-102">Funzione Level (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="f8b82-102">Level Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="f8b82-103">Restituisce il livello di nidificazione corrente in una gerarchia ricorsiva.</span><span class="sxs-lookup"><span data-stu-id="f8b82-103">Returns the current level of depth in a recursive hierarchy.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="f8b82-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f8b82-104">Syntax</span></span>  
  
```  
  
Level(scope)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f8b82-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f8b82-105">Parameters</span></span>  
 <span data-ttu-id="f8b82-106">*ambito*</span><span class="sxs-lookup"><span data-stu-id="f8b82-106">*scope*</span></span>  
 <span data-ttu-id="f8b82-107">(`String`) (Facoltativo).</span><span class="sxs-lookup"><span data-stu-id="f8b82-107">(`String`) (Optional).</span></span> <span data-ttu-id="f8b82-108">Nome di un set di dati, gruppo o area dati che contiene gli elementi del report a cui applicare la funzione di aggregazione.</span><span class="sxs-lookup"><span data-stu-id="f8b82-108">The name of a dataset, group, or data region that contains the report items to which to apply the aggregate function.</span></span> <span data-ttu-id="f8b82-109">Se si omette *scope* , viene usato l'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="f8b82-109">If *scope* is not specified, the current scope is used.</span></span>  
  
## <a name="return-type"></a><span data-ttu-id="f8b82-110">Tipo restituito</span><span class="sxs-lookup"><span data-stu-id="f8b82-110">Return Type</span></span>  
 <span data-ttu-id="f8b82-111">Restituisce un valore `Integer`.</span><span class="sxs-lookup"><span data-stu-id="f8b82-111">Returns an `Integer`.</span></span> <span data-ttu-id="f8b82-112">Se *scope* specifica un set di dati o un'area dati oppure un raggruppamento non ricorsivo, ovvero un raggruppamento senza `Parent` elemento, `Level` restituisce 0.</span><span class="sxs-lookup"><span data-stu-id="f8b82-112">If *scope* specifies a dataset or data region, or specifies a nonrecursive grouping (that is, a grouping with no `Parent` element), `Level` returns 0.</span></span> <span data-ttu-id="f8b82-113">Se *scope* viene omesso, restituisce il livello dell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="f8b82-113">If *scope* is omitted, it returns the level of the current scope.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f8b82-114">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="f8b82-114">Remarks</span></span>  
 <span data-ttu-id="f8b82-115">Il valore restituito dalla funzione `Level` è a base zero, ovvero il primo livello di una gerarchia viene indicato con 0.</span><span class="sxs-lookup"><span data-stu-id="f8b82-115">The value returned by the `Level` function is zero based; that is, the first level in a hierarchy is 0.</span></span>  
  
 <span data-ttu-id="f8b82-116">È possibile utilizzare la funzione `Level` per consentire l'applicazione dei rientri in una gerarchia ricorsiva, ad esempio un elenco di dipendenti.</span><span class="sxs-lookup"><span data-stu-id="f8b82-116">The `Level` function can be used to provide indentation in a recursive hierarchy, such as an employee list.</span></span>  
  
 <span data-ttu-id="f8b82-117">Per altre informazioni sulle gerarchie ricorsive, vedere [Creazione di gruppi di gerarchie ricorsive &#40;Generatore report e SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="f8b82-117">For more information about recursive hierarchies, see [Creating Recursive Hierarchy Groups &#40;Report Builder and SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f8b82-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="f8b82-118">Example</span></span>  
 <span data-ttu-id="f8b82-119">L'esempio di codice seguente consente di ottenere il livello di riga nel gruppo Employees:</span><span class="sxs-lookup"><span data-stu-id="f8b82-119">The following code example provides the level of row in the Employees group:</span></span>  
  
```  
=Level("Employees")  
```  
  
## <a name="see-also"></a><span data-ttu-id="f8b82-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f8b82-120">See Also</span></span>  
 <span data-ttu-id="f8b82-121">[Utilizzo delle espressioni nei report &#40;Generatore report e SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f8b82-121">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="f8b82-122">[Esempi di espressioni &#40;Generatore report e SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f8b82-122">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="f8b82-123">[Tipi di dati nelle espressioni &#40;Generatore report e SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f8b82-123">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="f8b82-124">Ambito di espressioni per totali, aggregazioni e raccolte predefinite &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="f8b82-124">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
