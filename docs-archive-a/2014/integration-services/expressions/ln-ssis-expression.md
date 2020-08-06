---
title: LN (espressione SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- LN function
- natural logarithm of expression [Integration Services]
ms.assetid: 55d7b657-b5fd-4753-9c81-54ed7575e720
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4c06d6e246cfa51f8e84eb93ab7eb73eab40c392
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635174"
---
# <a name="ln-ssis-expression"></a><span data-ttu-id="2f88f-102">LN (espressione SSIS)</span><span class="sxs-lookup"><span data-stu-id="2f88f-102">LN (SSIS Expression)</span></span>
  <span data-ttu-id="2f88f-103">Restituisce il logaritmo naturale di un'espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="2f88f-103">Returns the natural logarithm of a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f88f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2f88f-104">Syntax</span></span>  
  
```  
  
LN(numeric_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="2f88f-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="2f88f-105">Arguments</span></span>  
 <span data-ttu-id="2f88f-106">*numeric_expression*</span><span class="sxs-lookup"><span data-stu-id="2f88f-106">*numeric_expression*</span></span>  
 <span data-ttu-id="2f88f-107">Espressione numerica valida strettamente maggiore di zero.</span><span class="sxs-lookup"><span data-stu-id="2f88f-107">Is a valid non-zero and non-negative numeric expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="2f88f-108">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="2f88f-108">Result Types</span></span>  
 <span data-ttu-id="2f88f-109">DT_R8</span><span class="sxs-lookup"><span data-stu-id="2f88f-109">DT_R8</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2f88f-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="2f88f-110">Remarks</span></span>  
 <span data-ttu-id="2f88f-111">Prima del calcolo del logaritmo viene eseguito il cast dell'espressione numerica al tipo di dati DT_R8.</span><span class="sxs-lookup"><span data-stu-id="2f88f-111">The numeric expression is cast to the DT_R8 data type before the logarithm is computed.</span></span> <span data-ttu-id="2f88f-112">Per altre informazioni, vedere [Tipi di dati di Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="2f88f-112">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="2f88f-113">Se tramite il parametro *numeric_expression* viene restituito zero o un valore negativo, il risultato sarà Null.</span><span class="sxs-lookup"><span data-stu-id="2f88f-113">If *numeric_expression* evaluates to zero or a negative value, the return result is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="2f88f-114">Esempi di espressione</span><span class="sxs-lookup"><span data-stu-id="2f88f-114">Expression Examples</span></span>  
 <span data-ttu-id="2f88f-115">In questo esempio viene utilizzato un valore letterale numerico.</span><span class="sxs-lookup"><span data-stu-id="2f88f-115">This example uses a numeric literal.</span></span> <span data-ttu-id="2f88f-116">La funzione restituisce 3,737766961828337.</span><span class="sxs-lookup"><span data-stu-id="2f88f-116">The function returns the value 3.737766961828337.</span></span>  
  
```  
LN(42)  
```  
  
 <span data-ttu-id="2f88f-117">In questo esempio viene usata la colonna **Length**.</span><span class="sxs-lookup"><span data-stu-id="2f88f-117">This example uses the column **Length**.</span></span> <span data-ttu-id="2f88f-118">Se il valore della colonna è 53,99, la funzione restituirà 3,9887988442302.</span><span class="sxs-lookup"><span data-stu-id="2f88f-118">If the column value is 53.99, the function returns 3.9887988442302.</span></span>  
  
```  
LN(Length)   
```  
  
 <span data-ttu-id="2f88f-119">In questo esempio viene usata la variabile **Length**.</span><span class="sxs-lookup"><span data-stu-id="2f88f-119">This example uses the variable **Length**.</span></span> <span data-ttu-id="2f88f-120">La variabile deve avere un tipo di dati numeric oppure l'espressione deve includere un cast esplicito a un tipo di dati numeric.</span><span class="sxs-lookup"><span data-stu-id="2f88f-120">The variable must have a numeric data type or the expression must include an explicit cast to a numeric data type.</span></span> <span data-ttu-id="2f88f-121">Se il valore di **Length** è 234,567, la funzione restituisce 5,45774126708797.</span><span class="sxs-lookup"><span data-stu-id="2f88f-121">If **Length** is 234.567, the function returns 5.45774126708797.</span></span>  
  
```  
LN(@Length)   
```  
  
## <a name="see-also"></a><span data-ttu-id="2f88f-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2f88f-122">See Also</span></span>  
 <span data-ttu-id="2f88f-123">[LOG &#40;espressione SSIS&#41;](log-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="2f88f-123">[LOG &#40;SSIS Expression&#41;](log-ssis-expression.md) </span></span>  
 [<span data-ttu-id="2f88f-124">Funzioni &#40;espressione SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="2f88f-124">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
