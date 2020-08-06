---
title: POWER (espressione SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- POWER function
ms.assetid: db48ae65-bfa6-4db1-8d3c-d0d4f8a399bc
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e1f5742f482ae52620ec11d95b84cb3d06199fab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629486"
---
# <a name="power-ssis-expression"></a><span data-ttu-id="ba69e-102">POWER (espressione SSIS)</span><span class="sxs-lookup"><span data-stu-id="ba69e-102">POWER (SSIS Expression)</span></span>
  <span data-ttu-id="ba69e-103">Restituisce il risultato dell'elevamento a potenza di un'espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="ba69e-103">Returns the result of raising a numeric expression to a power.</span></span> <span data-ttu-id="ba69e-104">Il parametro power deve restituire un valore integer.</span><span class="sxs-lookup"><span data-stu-id="ba69e-104">The power parameter must evaluate to an integer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba69e-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ba69e-105">Syntax</span></span>  
  
```  
  
POWER(numeric_expression,power)  
```  
  
## <a name="arguments"></a><span data-ttu-id="ba69e-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="ba69e-106">Arguments</span></span>  
 <span data-ttu-id="ba69e-107">*numeric_expression*</span><span class="sxs-lookup"><span data-stu-id="ba69e-107">*numeric_expression*</span></span>  
 <span data-ttu-id="ba69e-108">Espressione numerica valida.</span><span class="sxs-lookup"><span data-stu-id="ba69e-108">Is a valid numeric expression.</span></span>  
  
 <span data-ttu-id="ba69e-109">*power*</span><span class="sxs-lookup"><span data-stu-id="ba69e-109">*power*</span></span>  
 <span data-ttu-id="ba69e-110">Espressione numerica valida.</span><span class="sxs-lookup"><span data-stu-id="ba69e-110">Is a valid numeric expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="ba69e-111">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="ba69e-111">Result Types</span></span>  
 <span data-ttu-id="ba69e-112">DT_R8</span><span class="sxs-lookup"><span data-stu-id="ba69e-112">DT_R8</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ba69e-113">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="ba69e-113">Remarks</span></span>  
 <span data-ttu-id="ba69e-114">Prima del calcolo della potenza, viene eseguito il cast degli argomenti *numeric_expression* e *power* nel tipo di dati DT_R8.</span><span class="sxs-lookup"><span data-stu-id="ba69e-114">The *numeric_expression* and *power* arguments are cast to the DT_R8 data type before the power is computed.</span></span> <span data-ttu-id="ba69e-115">Per altre informazioni, vedere [Tipi di dati di Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="ba69e-115">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="ba69e-116">Se *numeric_expression* restituisce zero e *power* è negativo, l'analizzatore di espressioni restituisce un errore e imposta il risultato restituito su Null.</span><span class="sxs-lookup"><span data-stu-id="ba69e-116">If *numeric_expression* evaluates to zero and *power* is negative, the expression evaluator returns an error and sets the return result to null.</span></span>  
  
 <span data-ttu-id="ba69e-117">Se *numeric_expression* o *power* restituisce risultati indeterminati, viene restituito Null.</span><span class="sxs-lookup"><span data-stu-id="ba69e-117">If *numeric_expression* or *power* evaluate to indeterminate results, the return result is null.</span></span>  
  
 <span data-ttu-id="ba69e-118">L'argomento *power* può essere una frazione.</span><span class="sxs-lookup"><span data-stu-id="ba69e-118">The *power* argument can be a fraction.</span></span> <span data-ttu-id="ba69e-119">ad esempio 0,5.</span><span class="sxs-lookup"><span data-stu-id="ba69e-119">For example, you can use the value 0.5 as the power.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="ba69e-120">Esempi di espressione</span><span class="sxs-lookup"><span data-stu-id="ba69e-120">Expression Examples</span></span>  
 <span data-ttu-id="ba69e-121">In questo esempio viene utilizzato un valore letterale numerico.</span><span class="sxs-lookup"><span data-stu-id="ba69e-121">This example uses a numeric literal.</span></span> <span data-ttu-id="ba69e-122">La funzione eleva 4 all'esponente 3 e restituisce 64.</span><span class="sxs-lookup"><span data-stu-id="ba69e-122">The function raises 4 to the power of 3 and returns 64.</span></span>  
  
```  
POWER(4,3)  
```  
  
 <span data-ttu-id="ba69e-123">Questo esempio usa la colonna **Length** e la variabile **DimensionCount** .</span><span class="sxs-lookup"><span data-stu-id="ba69e-123">This example uses the **Length** column and the **DimensionCount** variable.</span></span> <span data-ttu-id="ba69e-124">Se **Length** è 8 e **DimensionCount** è 2, il risultato restituito è 64.</span><span class="sxs-lookup"><span data-stu-id="ba69e-124">If **Length** is 8, and **DimensionCount** is 2, the return result is 64.</span></span>  
  
```  
POWER(Length, @DimensionCount)   
```  
  
## <a name="see-also"></a><span data-ttu-id="ba69e-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ba69e-125">See Also</span></span>  
 [<span data-ttu-id="ba69e-126">Funzioni &#40;espressione SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="ba69e-126">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
