---
title: SQUARE (espressione SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- SQUARE
- square values
ms.assetid: cecf1bb2-3d55-40a6-9688-ed67bcc150b4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 09955e708aae707a88aa7821d2a72651a3a44d59
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716468"
---
# <a name="square-ssis-expression"></a><span data-ttu-id="ee82c-102">SQUARE (espressione SSIS)</span><span class="sxs-lookup"><span data-stu-id="ee82c-102">SQUARE (SSIS Expression)</span></span>
  <span data-ttu-id="ee82c-103">Restituisce il quadrato di un'espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="ee82c-103">Returns the square of a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee82c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ee82c-104">Syntax</span></span>  
  
```  
  
SQUARE(numeric_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="ee82c-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="ee82c-105">Arguments</span></span>  
 <span data-ttu-id="ee82c-106">*numeric_expression*</span><span class="sxs-lookup"><span data-stu-id="ee82c-106">*numeric_expression*</span></span>  
 <span data-ttu-id="ee82c-107">Espressione numerica valida con qualsiasi tipo di dati numeric.</span><span class="sxs-lookup"><span data-stu-id="ee82c-107">Is a numeric expression of any numeric data type.</span></span> <span data-ttu-id="ee82c-108">Per altre informazioni, vedere [Tipi di dati di Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="ee82c-108">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="ee82c-109">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="ee82c-109">Result Types</span></span>  
 <span data-ttu-id="ee82c-110">DT_R8</span><span class="sxs-lookup"><span data-stu-id="ee82c-110">DT_R8</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ee82c-111">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="ee82c-111">Remarks</span></span>  
 <span data-ttu-id="ee82c-112">Se l'argomento è Null, SQUARE restituirà Null.</span><span class="sxs-lookup"><span data-stu-id="ee82c-112">SQUARE returns a null result if the argument is null.</span></span>  
  
 <span data-ttu-id="ee82c-113">Prima del calcolo del quadrato viene eseguito il cast dell'argomento al tipo di dati DT_R8.</span><span class="sxs-lookup"><span data-stu-id="ee82c-113">The argument is cast to the DT_R8 data type before the square operation.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="ee82c-114">Esempi di espressione</span><span class="sxs-lookup"><span data-stu-id="ee82c-114">Expression Examples</span></span>  
 <span data-ttu-id="ee82c-115">In questo esempio viene restituito il quadrato di 12.</span><span class="sxs-lookup"><span data-stu-id="ee82c-115">This example returns the square of 12.</span></span> <span data-ttu-id="ee82c-116">Il risultato restituito è 144.</span><span class="sxs-lookup"><span data-stu-id="ee82c-116">The return result is 144.</span></span>  
  
```  
SQUARE(12)  
```  
  
 <span data-ttu-id="ee82c-117">In questo esempio viene restituito il quadrato del risultato della sottrazione dei valori di due colonne.</span><span class="sxs-lookup"><span data-stu-id="ee82c-117">This example returns the square of the result of subtracting values in two columns.</span></span> <span data-ttu-id="ee82c-118">Se **Value1** contiene 12 e **Value2** contiene 4, la funzione SQUARE restituirà 64.</span><span class="sxs-lookup"><span data-stu-id="ee82c-118">If **Value1** contains 12 and **Value2** contains 4, the SQUARE function returns 64.</span></span>  
  
```  
SQUARE(Value1 - Value2)  
```  
  
 <span data-ttu-id="ee82c-119">In questo esempio viene restituita la lunghezza del terzo lato di un triangolo rettangolo, ottenuta applicando la funzione SQUARE a due variabili e quindi calcolando la radice quadrata della somma.</span><span class="sxs-lookup"><span data-stu-id="ee82c-119">This example returns the length of the third side of a right angle triangle by applying the SQUARE function to two variables and then calculating the square root of their sum.</span></span> <span data-ttu-id="ee82c-120">Se **Side1** contiene 3 e **Side2** contiene 4, la funzione SQRT restituirà 5.</span><span class="sxs-lookup"><span data-stu-id="ee82c-120">If **Side1** contains 3 and **Side2** contains 4, the SQRT function returns 5.</span></span>  
  
```  
SQRT(SQUARE(@Side1) + SQUARE(@Side2))  
```  
  
> [!NOTE]  
>  <span data-ttu-id="ee82c-121">Nelle espressioni i nomi delle variabili includono sempre il prefisso \@.</span><span class="sxs-lookup"><span data-stu-id="ee82c-121">In expressions, variable names always include the \@ prefix.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee82c-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ee82c-122">See Also</span></span>  
 [<span data-ttu-id="ee82c-123">Funzioni &#40;espressione SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="ee82c-123">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
