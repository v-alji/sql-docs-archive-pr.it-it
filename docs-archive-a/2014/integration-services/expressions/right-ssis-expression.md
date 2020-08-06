---
title: RIGHT (espressione SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- RIGHT function
ms.assetid: 83e70e75-4be5-4783-a8cf-032f82afe16e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2584ee33ecbf0436c4e3dc6e92b957e60ae396ce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716492"
---
# <a name="right-ssis-expression"></a><span data-ttu-id="55556-102">RIGHT (espressione SSIS)</span><span class="sxs-lookup"><span data-stu-id="55556-102">RIGHT (SSIS Expression)</span></span>
  <span data-ttu-id="55556-103">Viene restituito il numero specificato di caratteri della parte più a destra dell'espressione di caratteri indicata.</span><span class="sxs-lookup"><span data-stu-id="55556-103">Returns the specified number of characters from the rightmost portion of the given character expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55556-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="55556-104">Syntax</span></span>  
  
```  
  
RIGHT(character_expression,integer_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="55556-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="55556-105">Arguments</span></span>  
 <span data-ttu-id="55556-106">*character_expression*</span><span class="sxs-lookup"><span data-stu-id="55556-106">*character_expression*</span></span>  
 <span data-ttu-id="55556-107">Espressione di caratteri da cui estrarre i caratteri.</span><span class="sxs-lookup"><span data-stu-id="55556-107">Is a character expression from which to extract characters.</span></span>  
  
 <span data-ttu-id="55556-108">*integer_expression*</span><span class="sxs-lookup"><span data-stu-id="55556-108">*integer_expression*</span></span>  
 <span data-ttu-id="55556-109">Espressione integer in cui viene indicato il numero di caratteri da restituire.</span><span class="sxs-lookup"><span data-stu-id="55556-109">Is an integer expression that indicates the number of characters to be returned.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="55556-110">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="55556-110">Result Types</span></span>  
 <span data-ttu-id="55556-111">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="55556-111">DT_WSTR</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="55556-112">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="55556-112">Remarks</span></span>  
 <span data-ttu-id="55556-113">Se *integer_expression* è maggiore della lunghezza di *character_expression*, la funzione restituirà *character_expression*.</span><span class="sxs-lookup"><span data-stu-id="55556-113">If *integer_expression* is greater than the length of *character_expression*, the function returns *character_expression*.</span></span>  
  
 <span data-ttu-id="55556-114">Se *integer_expression* ha valore 0, la funzione restituirà una stringa di lunghezza zero.</span><span class="sxs-lookup"><span data-stu-id="55556-114">If *integer_expression* is zero, the function returns a zero-length string.</span></span>  
  
 <span data-ttu-id="55556-115">Se *integer_expression* è un numero negativo, la funzione restituirà un errore.</span><span class="sxs-lookup"><span data-stu-id="55556-115">If *integer_expression* is a negative number, the function returns an error.</span></span>  
  
 <span data-ttu-id="55556-116">L'argomento *integer_expression* accetta variabili e colonne.</span><span class="sxs-lookup"><span data-stu-id="55556-116">The *integer_expression* argument can take variables and columns.</span></span>  
  
 <span data-ttu-id="55556-117">È possibile utilizzare RIGHT solo con il tipo di dati DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="55556-117">RIGHT works only with the DT_WSTR data type.</span></span> <span data-ttu-id="55556-118">Se l'argomento *character_expression* è un valore letterale stringa o una colonna di dati con tipo di dati DT_STR, prima di eseguire l'operazione prevista da RIGHT verrà eseguito il cast implicito al tipo di dati DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="55556-118">A *character_expression* argument that is a string literal or a data column with the DT_STR data type is implicitly cast to the DT_WSTR data type before RIGHT performs its operation.</span></span> <span data-ttu-id="55556-119">Per gli altri tipi di dati è necessario il cast esplicito al tipo di dati DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="55556-119">Other data types must be explicitly cast to the DT_WSTR data type.</span></span> <span data-ttu-id="55556-120">Per altre informazioni, vedere [Tipi di dati di Integration Services](../data-flow/integration-services-data-types.md) e [Cast &#40;espressione SSIS&#41;](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="55556-120">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md) and [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="55556-121">Se l'argomento è Null, verrà restituito Null da RIGHT.</span><span class="sxs-lookup"><span data-stu-id="55556-121">RIGHT returns a null result if either argument is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="55556-122">Esempi di espressione</span><span class="sxs-lookup"><span data-stu-id="55556-122">Expression Examples</span></span>  
 <span data-ttu-id="55556-123">Nell'esempio seguente viene utilizzato un valore letterale stringa.</span><span class="sxs-lookup"><span data-stu-id="55556-123">The following example uses a string literal.</span></span> <span data-ttu-id="55556-124">Il risultato restituito sarà `"Bike"`.</span><span class="sxs-lookup"><span data-stu-id="55556-124">The return result is `"Bike"`.</span></span>  
  
```  
RIGHT("Mountain Bike", 4)  
```  
  
 <span data-ttu-id="55556-125">Nell'esempio seguente dalla colonna `Times` viene restituito il numero di caratteri più a destra specificato nella variabile `Name` .</span><span class="sxs-lookup"><span data-stu-id="55556-125">The following example returns the number of rightmost characters that is specified in the `Times` variable, from the `Name` column.</span></span> <span data-ttu-id="55556-126">Se `Name` è `Touring Front Wheel` e `Times` è 5, il risultato restituito sarà `"Wheel"`.</span><span class="sxs-lookup"><span data-stu-id="55556-126">If `Name` is `Touring Front Wheel` and `Times` is 5, the return result is `"Wheel"`.</span></span>  
  
```  
RIGHT(Name, @Times)  
```  
  
 <span data-ttu-id="55556-127">Nell'esempio seguente dalla colonna `Times` viene inoltre restituito il numero di caratteri più a destra specificato nella variabile `Name` .</span><span class="sxs-lookup"><span data-stu-id="55556-127">The following example also returns the number of rightmost characters that is specified in the `Times` variable, from the `Name` column.</span></span> <span data-ttu-id="55556-128">`Times` dispone di un tipo di dati non integer e nell'espressione è incluso un cast esplicito al tipo di dati DT_I2.</span><span class="sxs-lookup"><span data-stu-id="55556-128">`Times` has a noninteger data type and the expression includes an explicit cast to the DT_I2 data type.</span></span> <span data-ttu-id="55556-129">Se `Name` è `Touring Front Wheel` e `Times` è `4.32`, il risultato restituito sarà `"heel"` perché la funzione RIGHT converte il valore 4.32 in 4, quindi verranno restituiti i quattro caratteri più a destra.</span><span class="sxs-lookup"><span data-stu-id="55556-129">If `Name` is `Touring Front Wheel` and `Times` is `4.32`, the return result is `"heel"` because the RIGHT function converts the value of 4.32 to 4, and then returns the rightmost four characters.</span></span>  
  
```  
RIGHT(Name, (DT_I2)@Times))  
```  
  
## <a name="see-also"></a><span data-ttu-id="55556-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="55556-130">See Also</span></span>  
 <span data-ttu-id="55556-131">[LEFT &#40;espressione SSIS&#41;](left-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="55556-131">[LEFT &#40;SSIS Expression&#41;](left-ssis-expression.md) </span></span>  
 [<span data-ttu-id="55556-132">Funzioni &#40;espressione SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="55556-132">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
