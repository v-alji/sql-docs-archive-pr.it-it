---
title: FLOOR (espressione SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- largest integer less than or equal to expression
- FLOOR function [SSIS]
ms.assetid: 168084db-badd-40f2-87b4-1f5bc45c3e24
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b638c9a7215d120c562e416cdecee463f031ad2a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627909"
---
# <a name="floor-ssis-expression"></a><span data-ttu-id="bcd0e-102">FLOOR (espressione SSIS)</span><span class="sxs-lookup"><span data-stu-id="bcd0e-102">FLOOR (SSIS Expression)</span></span>
  <span data-ttu-id="bcd0e-103">Restituisce il più alto valore integer minore o uguale a un'espressione numerica specificata.</span><span class="sxs-lookup"><span data-stu-id="bcd0e-103">Returns the largest integer that is less than or equal to a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bcd0e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bcd0e-104">Syntax</span></span>  
  
```  
  
FLOOR(numeric_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="bcd0e-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="bcd0e-105">Arguments</span></span>  
 <span data-ttu-id="bcd0e-106">*numeric_expression*</span><span class="sxs-lookup"><span data-stu-id="bcd0e-106">*numeric_expression*</span></span>  
 <span data-ttu-id="bcd0e-107">Espressione numerica valida.</span><span class="sxs-lookup"><span data-stu-id="bcd0e-107">Is a valid numeric expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="bcd0e-108">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="bcd0e-108">Result Types</span></span>  
 <span data-ttu-id="bcd0e-109">Tipo di dati numeric dell'espressione passata come argomento.</span><span class="sxs-lookup"><span data-stu-id="bcd0e-109">The numeric data type of the argument expression.</span></span> <span data-ttu-id="bcd0e-110">Il risultato è rappresentato dalla parte intera del valore calcolato con tipo di dati corrispondente al tipo del parametro *numeric_expression*.</span><span class="sxs-lookup"><span data-stu-id="bcd0e-110">The result is the integer portion of the calculated value in the same data type as *numeric_expression.*</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bcd0e-111">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="bcd0e-111">Remarks</span></span>  
 <span data-ttu-id="bcd0e-112">Se l'argomento è Null, FLOOR restituirà Null.</span><span class="sxs-lookup"><span data-stu-id="bcd0e-112">FLOOR returns a null result if the argument is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="bcd0e-113">Esempi di espressione</span><span class="sxs-lookup"><span data-stu-id="bcd0e-113">Expression Examples</span></span>  
 <span data-ttu-id="bcd0e-114">In questi esempi la funzione FLOOR viene applicata a valori positivi, negativi e zero.</span><span class="sxs-lookup"><span data-stu-id="bcd0e-114">These examples apply the FLOOR function to positive, negative, and zero values.</span></span>  
  
```  
FLOOR(123.45)  
```  
  
 <span data-ttu-id="bcd0e-115">Restituisce 123,00.</span><span class="sxs-lookup"><span data-stu-id="bcd0e-115">Returns 123.00</span></span>  
  
```  
FLOOR(-123.45)  
```  
  
 <span data-ttu-id="bcd0e-116">Restituisce -124,00.</span><span class="sxs-lookup"><span data-stu-id="bcd0e-116">Returns -124.00</span></span>  
  
```  
FLOOR(0.00)  
```  
  
 <span data-ttu-id="bcd0e-117">Restituisce 0,00.</span><span class="sxs-lookup"><span data-stu-id="bcd0e-117">Returns 0.00</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcd0e-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bcd0e-118">See Also</span></span>  
 <span data-ttu-id="bcd0e-119">[CEILING &#40;espressione SSIS&#41;](ceiling-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="bcd0e-119">[CEILING &#40;SSIS Expression&#41;](ceiling-ssis-expression.md) </span></span>  
 [<span data-ttu-id="bcd0e-120">Funzioni &#40;espressione SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="bcd0e-120">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
