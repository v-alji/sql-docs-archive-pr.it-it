---
title: SQRT (espressione SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- SQRT function
- square root of given expression
ms.assetid: 54a75389-c501-4e22-87b8-905f66d6a3a5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9efa3f8da2e5280692aa65a25610211aba2fa40f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716472"
---
# <a name="sqrt-ssis-expression"></a><span data-ttu-id="cb648-102">SQRT (espressione SSIS)</span><span class="sxs-lookup"><span data-stu-id="cb648-102">SQRT (SSIS Expression)</span></span>
  <span data-ttu-id="cb648-103">Restituisce la radice quadrata di un'espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="cb648-103">Returns the square root of a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb648-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cb648-104">Syntax</span></span>  
  
```  
  
SQRT(numeric_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="cb648-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="cb648-105">Arguments</span></span>  
 <span data-ttu-id="cb648-106">*numeric_expression*</span><span class="sxs-lookup"><span data-stu-id="cb648-106">*numeric_expression*</span></span>  
 <span data-ttu-id="cb648-107">Espressione numerica valida con qualsiasi tipo di dati numeric.</span><span class="sxs-lookup"><span data-stu-id="cb648-107">Is a numeric expression of any numeric data type.</span></span> <span data-ttu-id="cb648-108">Per altre informazioni, vedere [Tipi di dati di Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="cb648-108">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="cb648-109">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="cb648-109">Result Types</span></span>  
 <span data-ttu-id="cb648-110">DT_R8</span><span class="sxs-lookup"><span data-stu-id="cb648-110">DT_R8</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cb648-111">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="cb648-111">Remarks</span></span>  
 <span data-ttu-id="cb648-112">Se l'argomento è Null, SQRT restituirà Null.</span><span class="sxs-lookup"><span data-stu-id="cb648-112">SQRT returns a null result if the argument is null.</span></span>  
  
 <span data-ttu-id="cb648-113">Se l'argomento è un valore negativo, SQRT restituirà un errore.</span><span class="sxs-lookup"><span data-stu-id="cb648-113">SQRT fails if the argument is a negative value.</span></span>  
  
 <span data-ttu-id="cb648-114">Prima del calcolo della radice quadrata viene eseguito il cast dell'argomento al tipo di dati DT_R8.</span><span class="sxs-lookup"><span data-stu-id="cb648-114">The argument is cast to the DT_R8 data type before the square root operation.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="cb648-115">Esempi di espressione</span><span class="sxs-lookup"><span data-stu-id="cb648-115">Expression Examples</span></span>  
 <span data-ttu-id="cb648-116">In questo esempio viene restituita la radice quadrata di un valore letterale numerico.</span><span class="sxs-lookup"><span data-stu-id="cb648-116">This example returns the square root of a numeric literal.</span></span> <span data-ttu-id="cb648-117">Il risultato restituito è 12.</span><span class="sxs-lookup"><span data-stu-id="cb648-117">The return result is 12.</span></span>  
  
```  
SQRT(144)  
```  
  
 <span data-ttu-id="cb648-118">In questo esempio viene restituita la radice quadrata di un'espressione, ovvero il risultato della sottrazione dei valori nelle colonne **Value1** e **Value2** .</span><span class="sxs-lookup"><span data-stu-id="cb648-118">This example returns the square root of an expression, the result of subtracting values in the **Value1** and **Value2** columns.</span></span>  
  
```  
SQRT(Value1 - Value2)  
```  
  
 <span data-ttu-id="cb648-119">In questo esempio viene restituita la lunghezza del terzo lato di un triangolo rettangolo, ottenuta applicando la funzione SQUARE a due variabili e quindi calcolando la radice quadrata della somma.</span><span class="sxs-lookup"><span data-stu-id="cb648-119">This example returns the length of the third side of a right triangle by applying the SQUARE function to two variables and then calculating the square root of their sum.</span></span> <span data-ttu-id="cb648-120">Se **Side1** contiene 3 e **Side2** contiene 4, la funzione SQRT restituirà 5.</span><span class="sxs-lookup"><span data-stu-id="cb648-120">If **Side1** contains 3 and **Side2** contains 4, the SQRT function returns 5.</span></span>  
  
```  
SQRT(SQUARE(@Side1) + SQUARE(@Side2))  
```  
  
> [!NOTE]  
>  <span data-ttu-id="cb648-121">Nelle espressioni i nomi delle variabili includono sempre il prefisso \@.</span><span class="sxs-lookup"><span data-stu-id="cb648-121">In expressions, variable names always include the \@ prefix.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb648-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cb648-122">See Also</span></span>  
 [<span data-ttu-id="cb648-123">Funzioni &#40;espressione SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="cb648-123">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
