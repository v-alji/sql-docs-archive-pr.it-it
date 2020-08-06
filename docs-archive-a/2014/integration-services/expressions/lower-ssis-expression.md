---
title: LOWER (espressione SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- converting uppercase to lowercase
- LOWER function
- uppercase characters [Integration Services]
- lowercase characters
ms.assetid: 109328e1-5604-40ff-895e-f2e7c13fff41
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 180be8f3cfb5a15eb0fcd6ddd3d63b09fe874af5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627906"
---
# <a name="lower-ssis-expression"></a><span data-ttu-id="60612-102">LOWER (espressione SSIS)</span><span class="sxs-lookup"><span data-stu-id="60612-102">LOWER (SSIS Expression)</span></span>
  <span data-ttu-id="60612-103">Viene restituita un'espressione di caratteri dopo aver convertito i caratteri maiuscoli in caratteri minuscoli.</span><span class="sxs-lookup"><span data-stu-id="60612-103">Returns a character expression after converting uppercase characters to lowercase characters.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60612-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="60612-104">Syntax</span></span>  
  
```  
  
LOWER(character_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="60612-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="60612-105">Arguments</span></span>  
 <span data-ttu-id="60612-106">*character_expression*</span><span class="sxs-lookup"><span data-stu-id="60612-106">*character_expression*</span></span>  
 <span data-ttu-id="60612-107">Espressione di caratteri da convertire in caratteri minuscoli.</span><span class="sxs-lookup"><span data-stu-id="60612-107">Is a character expression to convert to lowercase characters.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="60612-108">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="60612-108">Result Types</span></span>  
 <span data-ttu-id="60612-109">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="60612-109">DT_WSTR</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="60612-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="60612-110">Remarks</span></span>  
 <span data-ttu-id="60612-111">È possibile utilizzare LOWER solo con il tipo di dati DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="60612-111">LOWER works only with the DT_WSTR data type.</span></span> <span data-ttu-id="60612-112">Se l'argomento *character_expression* è un valore letterale stringa o una colonna di dati con tipo di dati DT_STR, prima di eseguire l'operazione prevista da LOWER verrà eseguito il cast implicito al tipo di dati DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="60612-112">A *character_expression* argument that is a string literal or a data column with the DT_STR data type is implicitly cast to the DT_WSTR data type before LOWER performs its operation.</span></span> <span data-ttu-id="60612-113">Per gli altri tipi di dati è necessario il cast esplicito al tipo di dati DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="60612-113">Other data types must be explicitly cast to the DT_WSTR data type.</span></span> <span data-ttu-id="60612-114">Per altre informazioni, vedere [Tipi di dati di Integration Services](../data-flow/integration-services-data-types.md) e [Cast &#40;espressione SSIS&#41;](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="60612-114">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md) and [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="60612-115">Se l'argomento è Null, LOWER restituirà Null.</span><span class="sxs-lookup"><span data-stu-id="60612-115">LOWER returns a null result if the argument is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="60612-116">Esempi di espressione</span><span class="sxs-lookup"><span data-stu-id="60612-116">Expression Examples</span></span>  
 <span data-ttu-id="60612-117">In questo esempio un valore letterale stringa viene convertito in caratteri minuscoli.</span><span class="sxs-lookup"><span data-stu-id="60612-117">This example converts a string literal to lowercase characters.</span></span> <span data-ttu-id="60612-118">Il risultato restituito è "new york".</span><span class="sxs-lookup"><span data-stu-id="60612-118">The return result is "new york".</span></span>  
  
```  
LOWER("New York")  
```  
  
 <span data-ttu-id="60612-119">In questo esempio tutti i caratteri della colonna di input **Color** , ad eccezione del primo, vengono convertiti in caratteri minuscoli.</span><span class="sxs-lookup"><span data-stu-id="60612-119">This example converts all characters from the **Color** input column, except the first character, to lowercase characters.</span></span> <span data-ttu-id="60612-120">Se Color ha valore YELLOW, il risultato restituito sarà "Yellow".</span><span class="sxs-lookup"><span data-stu-id="60612-120">If Color is YELLOW, the return result is "Yellow".</span></span> <span data-ttu-id="60612-121">Per altre informazioni, vedere [SUBSTRING &#40;espressione SSIS&#41;](substring-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="60612-121">For more information, see [SUBSTRING &#40;SSIS Expression&#41;](substring-ssis-expression.md).</span></span>  
  
```  
LOWER(SUBSTRING(Color, 2, 15))  
```  
  
 <span data-ttu-id="60612-122">In questo esempio il valore della variabile **CityName** viene convertito in caratteri minuscoli.</span><span class="sxs-lookup"><span data-stu-id="60612-122">This example converts the value in the **CityName** variable to lowercase characters.</span></span>  
  
```  
LOWER(@CityName)  
```  
  
## <a name="see-also"></a><span data-ttu-id="60612-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="60612-123">See Also</span></span>  
 <span data-ttu-id="60612-124">[UPPER &#40;espressione SSIS&#41;](upper-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="60612-124">[UPPER &#40;SSIS Expression&#41;](upper-ssis-expression.md) </span></span>  
 [<span data-ttu-id="60612-125">Funzioni &#40;espressione SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="60612-125">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
