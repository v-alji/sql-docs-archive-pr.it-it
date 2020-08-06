---
title: SIGN (espressione SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- positive values [Integration Services]
- SIGN function
- negative values
ms.assetid: 1547db08-4329-4781-91c2-36898ed71b15
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a34992b0029cd378274e38ce4e37fcd313d2b788
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716480"
---
# <a name="sign-ssis-expression"></a><span data-ttu-id="8c543-102">SIGN (espressione SSIS)</span><span class="sxs-lookup"><span data-stu-id="8c543-102">SIGN (SSIS Expression)</span></span>
  <span data-ttu-id="8c543-103">Viene restituito il segno positivo (+1), negativo (-1) o zero (0) di un'espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="8c543-103">Returns the positive (+1), negative (-1), or zero (0) sign of a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c543-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8c543-104">Syntax</span></span>  
  
```  
  
SIGN(numeric_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="8c543-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="8c543-105">Arguments</span></span>  
 <span data-ttu-id="8c543-106">*numeric_expression*</span><span class="sxs-lookup"><span data-stu-id="8c543-106">*numeric_expression*</span></span>  
 <span data-ttu-id="8c543-107">Espressione numerica valida con segno.</span><span class="sxs-lookup"><span data-stu-id="8c543-107">Is a valid signed numeric expression.</span></span> <span data-ttu-id="8c543-108">Per altre informazioni, vedere [Tipi di dati di Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="8c543-108">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="8c543-109">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="8c543-109">Result Types</span></span>  
 <span data-ttu-id="8c543-110">DT_I4</span><span class="sxs-lookup"><span data-stu-id="8c543-110">DT_I4</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8c543-111">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="8c543-111">Remarks</span></span>  
 <span data-ttu-id="8c543-112">Se l'argomento è Null, SIGN restituirà Null.</span><span class="sxs-lookup"><span data-stu-id="8c543-112">SIGN returns a null result if the argument is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="8c543-113">Esempi di espressione</span><span class="sxs-lookup"><span data-stu-id="8c543-113">Expression Examples</span></span>  
 <span data-ttu-id="8c543-114">In questo esempio viene restituito il segno di un valore letterale numerico.</span><span class="sxs-lookup"><span data-stu-id="8c543-114">This example returns the sign of a numeric literal.</span></span> <span data-ttu-id="8c543-115">Il risultato restituito sarà -1.</span><span class="sxs-lookup"><span data-stu-id="8c543-115">The return result is -1.</span></span>  
  
```  
SIGN(-123.45)  
```  
  
 <span data-ttu-id="8c543-116">In questo esempio viene restituito il segno del risultato della sottrazione della colonna **StandardCost** dalla colonna **DealerPrice** .</span><span class="sxs-lookup"><span data-stu-id="8c543-116">This example returns the sign of the result of subtracting the **StandardCost** column from the **DealerPrice** column.</span></span>  
  
```  
SIGN(DealerPrice - StandardCost)  
```  
  
## <a name="see-also"></a><span data-ttu-id="8c543-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8c543-117">See Also</span></span>  
 [<span data-ttu-id="8c543-118">Funzioni &#40;espressione SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="8c543-118">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
