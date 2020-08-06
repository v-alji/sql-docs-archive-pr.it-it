---
title: ROUND (espressione SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- rounding expressions
- ROUND function [SSIS]
ms.assetid: 376f1947-4fc5-4611-ad86-823e4db1b468
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9d77045787eafbc3dd402db9982d8d7a98190bc2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716487"
---
# <a name="round-ssis-expression"></a><span data-ttu-id="5db91-102">ROUND (espressione SSIS)</span><span class="sxs-lookup"><span data-stu-id="5db91-102">ROUND (SSIS Expression)</span></span>
  <span data-ttu-id="5db91-103">Restituisce un'espressione numerica arrotondata alla lunghezza o alla precisione specificata.</span><span class="sxs-lookup"><span data-stu-id="5db91-103">Returns a numeric expression that is rounded to the specified length or precision.</span></span> <span data-ttu-id="5db91-104">Il parametro length deve restituire un valore integer.</span><span class="sxs-lookup"><span data-stu-id="5db91-104">The length parameter must evaluate to an integer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5db91-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5db91-105">Syntax</span></span>  
  
```  
  
ROUND(numeric_expression,length)  
```  
  
## <a name="arguments"></a><span data-ttu-id="5db91-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="5db91-106">Arguments</span></span>  
 <span data-ttu-id="5db91-107">*numeric_expression*</span><span class="sxs-lookup"><span data-stu-id="5db91-107">*numeric_expression*</span></span>  
 <span data-ttu-id="5db91-108">Espressione di tipo numeric valido.</span><span class="sxs-lookup"><span data-stu-id="5db91-108">Is an expression of a valid numeric type.</span></span> <span data-ttu-id="5db91-109">Per altre informazioni, vedere [Tipi di dati di Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="5db91-109">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="5db91-110">*length*</span><span class="sxs-lookup"><span data-stu-id="5db91-110">*length*</span></span>  
 <span data-ttu-id="5db91-111">Espressione integer.</span><span class="sxs-lookup"><span data-stu-id="5db91-111">Is an integer expression.</span></span> <span data-ttu-id="5db91-112">Precisione per l'arrotondamento di *numeric_expression* .</span><span class="sxs-lookup"><span data-stu-id="5db91-112">It is the precision to which *numeric_expression* is rounded.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="5db91-113">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="5db91-113">Result Types</span></span>  
 <span data-ttu-id="5db91-114">Tipo identico a *numeric*_*expression*.</span><span class="sxs-lookup"><span data-stu-id="5db91-114">The same type as *numeric*_*expression.*</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5db91-115">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="5db91-115">Remarks</span></span>  
 <span data-ttu-id="5db91-116">Tramite l'argomento *length* deve essere restituito un numero intero positivo oppure zero.</span><span class="sxs-lookup"><span data-stu-id="5db91-116">The *length* argument must evaluate to a positive integer or zero.</span></span>  
  
 <span data-ttu-id="5db91-117">Se l'argomento è Null, ROUND restituirà Null.</span><span class="sxs-lookup"><span data-stu-id="5db91-117">ROUND returns a null result if the argument is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="5db91-118">Esempi di espressione</span><span class="sxs-lookup"><span data-stu-id="5db91-118">Expression Examples</span></span>  
 <span data-ttu-id="5db91-119">In questi esempi alcuni valori letterali numerici vengono arrotondati con lunghezza tre.</span><span class="sxs-lookup"><span data-stu-id="5db91-119">These examples round numeric literals to a length of three.</span></span> <span data-ttu-id="5db91-120">Il primo risultato restituito è 137,1570, il secondo 137,1580.</span><span class="sxs-lookup"><span data-stu-id="5db91-120">The first return result is 137.1570, the second 137.1580.</span></span>  
  
```  
ROUND(137.1574,3)  
ROUND(137.1575,3)  
```  
  
## <a name="see-also"></a><span data-ttu-id="5db91-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5db91-121">See Also</span></span>  
 [<span data-ttu-id="5db91-122">Funzioni &#40;espressione SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="5db91-122">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
