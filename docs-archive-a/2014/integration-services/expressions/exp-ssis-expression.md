---
title: EXP (espressione SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- exponential functions
- EXP function
ms.assetid: 4cd96d3c-58c9-4a67-a6f6-b72758232912
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 150c92355ab3e0d3a028c98defe2e2fa9a1bf8ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629489"
---
# <a name="exp-ssis-expression"></a><span data-ttu-id="c66e2-102">EXP (espressione SSIS)</span><span class="sxs-lookup"><span data-stu-id="c66e2-102">EXP (SSIS Expression)</span></span>
  <span data-ttu-id="c66e2-103">Viene restituito l'esponente in base e di un'espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="c66e2-103">Returns the exponent to base e of a numeric expression.</span></span> <span data-ttu-id="c66e2-104">EXP è la funzione inversa della funzione LN ed è talvolta chiamata antilogaritmo.</span><span class="sxs-lookup"><span data-stu-id="c66e2-104">The EXP function complements the action of the LN function and is sometimes referred to as the antilogarithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c66e2-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c66e2-105">Syntax</span></span>  
  
```  
  
EXP(numeric_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="c66e2-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="c66e2-106">Arguments</span></span>  
 <span data-ttu-id="c66e2-107">*numeric_expression*</span><span class="sxs-lookup"><span data-stu-id="c66e2-107">*numeric_expression*</span></span>  
 <span data-ttu-id="c66e2-108">Espressione numerica valida.</span><span class="sxs-lookup"><span data-stu-id="c66e2-108">Is a valid numeric expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="c66e2-109">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="c66e2-109">Result Types</span></span>  
 <span data-ttu-id="c66e2-110">DT_R8</span><span class="sxs-lookup"><span data-stu-id="c66e2-110">DT_R8</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c66e2-111">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="c66e2-111">Remarks</span></span>  
 <span data-ttu-id="c66e2-112">Prima del calcolo dell'esponente viene eseguito il cast dell'espressione numerica al tipo di dati DT_R8.</span><span class="sxs-lookup"><span data-stu-id="c66e2-112">The numeric expression is cast to the DT_R8 data type before the exponent is computed.</span></span> <span data-ttu-id="c66e2-113">Per altre informazioni, vedere [Tipi di dati di Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="c66e2-113">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="c66e2-114">Il risultato restituito è sempre un numero positivo.</span><span class="sxs-lookup"><span data-stu-id="c66e2-114">The return result is always a positive number.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="c66e2-115">Esempi di espressione</span><span class="sxs-lookup"><span data-stu-id="c66e2-115">Expression Examples</span></span>  
 <span data-ttu-id="c66e2-116">In questi esempi la funzione EXP viene applicata a valori positivi e negativi e allo zero.</span><span class="sxs-lookup"><span data-stu-id="c66e2-116">These examples apply the EXP function to positive and negative values and to zero.</span></span>  
  
```  
EXP(74)  
```  
  
 <span data-ttu-id="c66e2-117">Restituisce 1,373382979540176E+32.</span><span class="sxs-lookup"><span data-stu-id="c66e2-117">Returns 1.373382979540176E+32.</span></span>  
  
```  
EXP(-27)  
```  
  
 <span data-ttu-id="c66e2-118">Restituisce 1,879528816539083E-12.</span><span class="sxs-lookup"><span data-stu-id="c66e2-118">Returns 1.879528816539083E-12.</span></span>  
  
```  
EXP(0)  
```  
  
 <span data-ttu-id="c66e2-119">Restituisce 1.</span><span class="sxs-lookup"><span data-stu-id="c66e2-119">Returns 1.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c66e2-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c66e2-120">See Also</span></span>  
 <span data-ttu-id="c66e2-121">[LOG &#40;espressione SSIS&#41;](log-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="c66e2-121">[LOG &#40;SSIS Expression&#41;](log-ssis-expression.md) </span></span>  
 [<span data-ttu-id="c66e2-122">Funzioni &#40;espressione SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="c66e2-122">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
