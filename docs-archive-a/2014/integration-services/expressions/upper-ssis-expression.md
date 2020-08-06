---
title: UPPER (espressione SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- UPPER function
- converting lowercase to uppercase
- uppercase characters [Integration Services]
- lowercase characters
ms.assetid: d33985f7-1048-4023-83e4-274090acda78
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 181e231d735a8e98cd2bce10c692e35668a686f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716432"
---
# <a name="upper-ssis-expression"></a><span data-ttu-id="b451f-102">UPPER (espressione SSIS)</span><span class="sxs-lookup"><span data-stu-id="b451f-102">UPPER (SSIS Expression)</span></span>
  <span data-ttu-id="b451f-103">Restituisce un'espressione di caratteri dopo aver convertito i caratteri minuscoli in caratteri maiuscoli.</span><span class="sxs-lookup"><span data-stu-id="b451f-103">Returns a character expression after converting lowercase characters to uppercase characters.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b451f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b451f-104">Syntax</span></span>  
  
```  
  
UPPER(character_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="b451f-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="b451f-105">Arguments</span></span>  
 <span data-ttu-id="b451f-106">*character_expression*</span><span class="sxs-lookup"><span data-stu-id="b451f-106">*character_expression*</span></span>  
 <span data-ttu-id="b451f-107">Espressione di caratteri da convertire in caratteri maiuscoli.</span><span class="sxs-lookup"><span data-stu-id="b451f-107">Is a character expression to convert to uppercase characters.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="b451f-108">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="b451f-108">Result Types</span></span>  
 <span data-ttu-id="b451f-109">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="b451f-109">DT_WSTR</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b451f-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="b451f-110">Remarks</span></span>  
 <span data-ttu-id="b451f-111">È possibile utilizzare UPPER solo con il tipo di dati DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="b451f-111">UPPER works only with the DT_WSTR data type.</span></span> <span data-ttu-id="b451f-112">Se l'argomento *character_expression* è un valore letterale stringa o una colonna di dati con tipo di dati DT_STR, prima di eseguire l'operazione prevista da UPPER verrà eseguito il cast implicito al tipo di dati DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="b451f-112">A *character_expression* argument that is a string literal or a data column with the DT_STR data type is implicitly cast to the DT_WSTR data type before UPPER performs its operation.</span></span> <span data-ttu-id="b451f-113">Per gli altri tipi di dati è necessario il cast esplicito al tipo di dati DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="b451f-113">Other data types must be explicitly cast to the DT_WSTR data type.</span></span> <span data-ttu-id="b451f-114">Per altre informazioni, vedere [Tipi di dati di Integration Services](../data-flow/integration-services-data-types.md) e [Cast &#40;espressione SSIS&#41;](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="b451f-114">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md) and [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="b451f-115">Se l'argomento è Null, UPPER restituirà Null.</span><span class="sxs-lookup"><span data-stu-id="b451f-115">UPPER returns a null result if the argument is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="b451f-116">Esempi di espressione</span><span class="sxs-lookup"><span data-stu-id="b451f-116">Expression Examples</span></span>  
 <span data-ttu-id="b451f-117">In questo esempio un valore letterale stringa viene convertito in caratteri maiuscoli.</span><span class="sxs-lookup"><span data-stu-id="b451f-117">This example converts a string literal to uppercase characters.</span></span> <span data-ttu-id="b451f-118">Il risultato restituito è "HELLO".</span><span class="sxs-lookup"><span data-stu-id="b451f-118">The return result is "HELLO".</span></span>  
  
```  
UPPER("hello")  
```  
  
 <span data-ttu-id="b451f-119">In questo esempio viene convertito in maiuscolo il primo carattere della colonna **FirstName** .</span><span class="sxs-lookup"><span data-stu-id="b451f-119">This example converts the first character in the **FirstName** column to an uppercase character.</span></span> <span data-ttu-id="b451f-120">Se **FirstName** contiene anna, il risultato restituito sarà "A".</span><span class="sxs-lookup"><span data-stu-id="b451f-120">If **FirstName** is anna, the return result is "A".</span></span> <span data-ttu-id="b451f-121">Per altre informazioni, vedere [SUBSTRING &#40;espressione SSIS&#41;](substring-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="b451f-121">For more information, see [SUBSTRING &#40;SSIS Expression&#41;](substring-ssis-expression.md).</span></span>  
  
```  
UPPER(SUBSTRING(FirstName, 1, 1))  
```  
  
 <span data-ttu-id="b451f-122">In questo esempio il valore della variabile **PostalCode** viene convertito in caratteri maiuscoli.</span><span class="sxs-lookup"><span data-stu-id="b451f-122">This example converts the value in the **PostalCode** variable to uppercase characters.</span></span> <span data-ttu-id="b451f-123">Se **PostalCode** contiene k4b1s2, il risultato restituito sarà "K4B1S2".</span><span class="sxs-lookup"><span data-stu-id="b451f-123">If **PostalCode** is k4b1s2, the return result is "K4B1S2".</span></span>  
  
```  
UPPER(@PostalCode)  
```  
  
## <a name="see-also"></a><span data-ttu-id="b451f-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b451f-124">See Also</span></span>  
 <span data-ttu-id="b451f-125">[LOWER &#40;espressione SSIS&#41;](lower-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="b451f-125">[LOWER &#40;SSIS Expression&#41;](lower-ssis-expression.md) </span></span>  
 [<span data-ttu-id="b451f-126">Funzioni &#40;espressione SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="b451f-126">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
