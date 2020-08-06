---
title: Funzione RowNumber (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 9d718ba8-d323-49fb-aac8-e7013a117b75
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9f3d16188138c2f268305fddb092d56be870a3f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628403"
---
# <a name="rownumber-function-report-builder-and-ssrs"></a><span data-ttu-id="450d6-102">Funzione RowNumber (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="450d6-102">RowNumber Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="450d6-103">Restituisce il conteggio parziale del numero di righe per l'ambito specificato.</span><span class="sxs-lookup"><span data-stu-id="450d6-103">Returns a running count of the number of rows for the specified scope.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="450d6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="450d6-104">Syntax</span></span>  
  
```  
  
RowNumber(scope)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="450d6-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="450d6-105">Parameters</span></span>  
 <span data-ttu-id="450d6-106">*ambito*</span><span class="sxs-lookup"><span data-stu-id="450d6-106">*scope*</span></span>  
 <span data-ttu-id="450d6-107">(`String`) Nome di un set di dati, area dati o gruppo oppure valore Null (`Nothing` in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]) tramite cui viene specificato il contesto in cui valutare il numero di righe.</span><span class="sxs-lookup"><span data-stu-id="450d6-107">(`String`) The name of a dataset, data region, or group, or null (`Nothing` in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]), that specifies the context in which to evaluate the number of rows.</span></span> <span data-ttu-id="450d6-108">Tramite `Nothing` viene specificato il contesto più esterno, generalmente il set di dati del report.</span><span class="sxs-lookup"><span data-stu-id="450d6-108">`Nothing` specifies the outermost context, usually the report dataset.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="450d6-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="450d6-109">Remarks</span></span>  
 <span data-ttu-id="450d6-110">`RowNumber`Restituisce un valore corrente del conteggio di righe all'interno dell'ambito specificato, così come [RunningValue](report-builder-functions-runningvalue-function.md) restituisce il valore corrente di una funzione di aggregazione.</span><span class="sxs-lookup"><span data-stu-id="450d6-110">`RowNumber` returns a running value of the count of rows within the specified scope, just as [RunningValue](report-builder-functions-runningvalue-function.md) returns the running value of an aggregate function.</span></span> <span data-ttu-id="450d6-111">Durante la definizione di un ambito, si specifica quando reimpostare il conteggio delle righe su 1.</span><span class="sxs-lookup"><span data-stu-id="450d6-111">When you specify a scope, you specify when to reset the row count to 1.</span></span>  
  
 <span data-ttu-id="450d6-112">*scope* non può essere un'espressione.</span><span class="sxs-lookup"><span data-stu-id="450d6-112">*scope* cannot be an expression.</span></span> <span data-ttu-id="450d6-113">Il parametro*scope* deve essere un ambito contenitore.</span><span class="sxs-lookup"><span data-stu-id="450d6-113">*scope* must be a containing scope.</span></span> <span data-ttu-id="450d6-114">I tipici ambiti, dal contenuto più esterno fino al più interno, sono set di dati di report, aree dati, gruppi di righe o di colonne.</span><span class="sxs-lookup"><span data-stu-id="450d6-114">Typical scopes, from the outermost to the innermost containment, are report dataset, data region, row groups or column groups.</span></span>  
  
 <span data-ttu-id="450d6-115">Per incrementare i valori nelle colonne, specificare un ambito che corrisponde al nome di un gruppo di colonne.</span><span class="sxs-lookup"><span data-stu-id="450d6-115">To increment values across columns, specify a scope that is the name of a column group.</span></span> <span data-ttu-id="450d6-116">Per incrementare i numeri verso il basso delle righe, specificare un ambito che corrisponde al nome di un gruppo di righe.</span><span class="sxs-lookup"><span data-stu-id="450d6-116">To increment numbers down rows, specify a scope that is the name of a row group.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="450d6-117">Non è possibile includere aggregazioni che specificano sia un gruppo di righe che un gruppo di colonne in un'unica espressione.</span><span class="sxs-lookup"><span data-stu-id="450d6-117">Including aggregates that specify both a row group and a column group in a single expression is not supported.</span></span>  
  
 <span data-ttu-id="450d6-118">Per altre informazioni, vedere [Riferimento a funzioni di aggregazione &#40;Generatore report e SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) e [Ambito di espressioni per totali, aggregazioni e raccolte predefinite &#40;Generatore report e SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="450d6-118">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) and [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
## <a name="code-example"></a><span data-ttu-id="450d6-119">Esempio di codice</span><span class="sxs-lookup"><span data-stu-id="450d6-119">Code Example</span></span>  
 <span data-ttu-id="450d6-120">Di seguito è riportata un'espressione che è possibile usare per la proprietà `BackgroundColor` della riga di dettaglio di un'area dati Tablix per alternare il colore di tali righe per ogni gruppo, sempre a partire dal bianco.</span><span class="sxs-lookup"><span data-stu-id="450d6-120">The following is an expression that you can use for the `BackgroundColor` property of a Tablix data region detail row to alternate the color of detail rows for each group, always beginning with White.</span></span>  
  
```  
=IIF(RowNumber("GroupbyCategory") Mod 2, "White", "PaleGreen")  
```  
  
## <a name="see-also"></a><span data-ttu-id="450d6-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="450d6-121">See Also</span></span>  
 <span data-ttu-id="450d6-122">[Utilizzo delle espressioni nei report &#40;Generatore report e SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="450d6-122">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="450d6-123">[Esempi di espressioni &#40;Generatore report e SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="450d6-123">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="450d6-124">[Tipi di dati nelle espressioni &#40;Generatore report e SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="450d6-124">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="450d6-125">Ambito di espressioni per totali, aggregazioni e raccolte predefinite &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="450d6-125">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
