---
title: CEILING (espressione SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- smallest integer great than or equal to expression
- CEILING function [SSIS]
ms.assetid: c35bd4ee-1ab6-46ab-89a7-cf771527faa2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: cd2f9f455226925d6bf00842e80a8713e6c72771
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637999"
---
# <a name="ceiling-ssis-expression"></a><span data-ttu-id="260d7-102">CEILING (espressione SSIS)</span><span class="sxs-lookup"><span data-stu-id="260d7-102">CEILING (SSIS Expression)</span></span>
  <span data-ttu-id="260d7-103">Restituisce il più piccolo valore integer maggiore o uguale a un'espressione numerica specificata.</span><span class="sxs-lookup"><span data-stu-id="260d7-103">Returns the smallest integer that is greater than or equal to a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="260d7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="260d7-104">Syntax</span></span>  
  
```  
  
CEILING(numeric_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="260d7-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="260d7-105">Arguments</span></span>  
 <span data-ttu-id="260d7-106">*numeric_expression*</span><span class="sxs-lookup"><span data-stu-id="260d7-106">*numeric_expression*</span></span>  
 <span data-ttu-id="260d7-107">Espressione numerica valida.</span><span class="sxs-lookup"><span data-stu-id="260d7-107">Is a valid numeric expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="260d7-108">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="260d7-108">Result Types</span></span>  
 <span data-ttu-id="260d7-109">Tipo di dati dell'espressione numerica inviata alla funzione.</span><span class="sxs-lookup"><span data-stu-id="260d7-109">The data type of the numeric expression submitted to the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="260d7-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="260d7-110">Remarks</span></span>  
 <span data-ttu-id="260d7-111">Se l'argomento è Null, CEILING restituirà Null.</span><span class="sxs-lookup"><span data-stu-id="260d7-111">CEILING returns a null result if the argument is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="260d7-112">Esempi di espressione</span><span class="sxs-lookup"><span data-stu-id="260d7-112">Expression Examples</span></span>  
 <span data-ttu-id="260d7-113">In questi esempi la funzione CEILING viene applicata a valori positivi, negativi e zero.</span><span class="sxs-lookup"><span data-stu-id="260d7-113">These examples apply the CEILING function to positive, negative, and zero values.</span></span>  
  
```  
CEILING(123.74)  
```  
  
 <span data-ttu-id="260d7-114">Restituisce 124,00.</span><span class="sxs-lookup"><span data-stu-id="260d7-114">Returns 124.00</span></span>  
  
```  
CEILING(-124.27)  
```  
  
 <span data-ttu-id="260d7-115">Restituisce -124,00.</span><span class="sxs-lookup"><span data-stu-id="260d7-115">Returns -124.00</span></span>  
  
```  
CEILING(0.00)  
```  
  
 <span data-ttu-id="260d7-116">Restituisce 0,00.</span><span class="sxs-lookup"><span data-stu-id="260d7-116">Returns 0.00</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="260d7-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="260d7-117">See Also</span></span>  
 <span data-ttu-id="260d7-118">[FLOOR &#40;espressione SSIS&#41;](floor-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="260d7-118">[FLOOR &#40;SSIS Expression&#41;](floor-ssis-expression.md) </span></span>  
 [<span data-ttu-id="260d7-119">Funzioni &#40;espressione SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="260d7-119">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
