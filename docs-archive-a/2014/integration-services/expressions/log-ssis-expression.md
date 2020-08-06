---
title: LOG (espressione SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- base-10 logarithms
- LOG function
ms.assetid: f7fccace-c178-4e13-bde9-7dc4ef1d98fa
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0de84c1a92f94507bcc69c47cc4d9b6cda50a4f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635170"
---
# <a name="log-ssis-expression"></a><span data-ttu-id="48bca-102">LOG (espressione SSIS)</span><span class="sxs-lookup"><span data-stu-id="48bca-102">LOG (SSIS Expression)</span></span>
  <span data-ttu-id="48bca-103">Viene restituito il logaritmo in base 10 di un'espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="48bca-103">Returns the base-10 logarithm of a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48bca-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="48bca-104">Syntax</span></span>  
  
```  
  
LOG(numeric_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="48bca-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="48bca-105">Arguments</span></span>  
 <span data-ttu-id="48bca-106">*numeric_expression*</span><span class="sxs-lookup"><span data-stu-id="48bca-106">*numeric_expression*</span></span>  
 <span data-ttu-id="48bca-107">Espressione numerica valida strettamente maggiore di zero.</span><span class="sxs-lookup"><span data-stu-id="48bca-107">Is a valid nonzero or nonnegative numeric expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="48bca-108">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="48bca-108">Result Types</span></span>  
 <span data-ttu-id="48bca-109">DT_R8</span><span class="sxs-lookup"><span data-stu-id="48bca-109">DT_R8</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="48bca-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="48bca-110">Remarks</span></span>  
 <span data-ttu-id="48bca-111">Prima del calcolo del logaritmo viene eseguito il cast dell' *espressione numerica* al tipo di dati DT_R8.</span><span class="sxs-lookup"><span data-stu-id="48bca-111">The *numeric expression* is cast to the DT_R8 data type before the logarithm is computed.</span></span> <span data-ttu-id="48bca-112">Per altre informazioni, vedere [Tipi di dati di Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="48bca-112">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="48bca-113">Se tramite il parametro *numeric_expression* viene restituito zero o un valore negativo, il risultato sarà Null.</span><span class="sxs-lookup"><span data-stu-id="48bca-113">If *numeric_expression* evaluates to zero or a negative value, the return result is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="48bca-114">Esempi di espressione</span><span class="sxs-lookup"><span data-stu-id="48bca-114">Expression Examples</span></span>  
 <span data-ttu-id="48bca-115">In questo esempio viene utilizzato un valore letterale numerico.</span><span class="sxs-lookup"><span data-stu-id="48bca-115">This example uses a numeric literal.</span></span> <span data-ttu-id="48bca-116">La funzione restituisce 1,988291341907488.</span><span class="sxs-lookup"><span data-stu-id="48bca-116">The function returns the value 1.988291341907488.</span></span>  
  
```  
LOG(97.34)  
```  
  
 <span data-ttu-id="48bca-117">In questo esempio viene usata la colonna **Length**.</span><span class="sxs-lookup"><span data-stu-id="48bca-117">This example uses the column **Length**.</span></span> <span data-ttu-id="48bca-118">Se il valore della colonna è 101,24, la funzione restituirà 2,005352136486217.</span><span class="sxs-lookup"><span data-stu-id="48bca-118">If the column is 101.24, the function returns 2.005352136486217.</span></span>  
  
```  
LOG(Length)   
```  
  
 <span data-ttu-id="48bca-119">In questo esempio viene usata la variabile **Length**.</span><span class="sxs-lookup"><span data-stu-id="48bca-119">This example uses the variable **Length**.</span></span> <span data-ttu-id="48bca-120">La variabile deve avere un tipo di dati numeric o l'espressione deve includere un cast esplicito a un tipo di dati numeric di [!INCLUDE[ssIS](../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="48bca-120">The variable must have a numeric data type or the expression must include an explicit cast to a numeric [!INCLUDE[ssIS](../../includes/ssis-md.md)] data type.</span></span> <span data-ttu-id="48bca-121">Se **Length** ha valore 234,567, la funzione restituirà 2,370266913465859.</span><span class="sxs-lookup"><span data-stu-id="48bca-121">If **Length** is 234.567, the function returns 2.370266913465859.</span></span>  
  
```  
LOG(@Length)   
```  
  
## <a name="see-also"></a><span data-ttu-id="48bca-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="48bca-122">See Also</span></span>  
 <span data-ttu-id="48bca-123">[EXP &#40;espressione SSIS&#41;](exp-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="48bca-123">[EXP &#40;SSIS Expression&#41;](exp-ssis-expression.md) </span></span>  
 <span data-ttu-id="48bca-124">[LN &#40;espressione SSIS&#41;](ln-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="48bca-124">[LN &#40;SSIS Expression&#41;](ln-ssis-expression.md) </span></span>  
 [<span data-ttu-id="48bca-125">Funzioni &#40;espressione SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="48bca-125">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
