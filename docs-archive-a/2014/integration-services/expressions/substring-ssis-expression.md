---
title: SUBSTRING (espressione SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- SUBSTRING function
- part of expression returned [Integration Services]
ms.assetid: 3a46748a-f5f8-4a6c-9108-673666754068
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ba53676bc6d13ed34892f48fca3b70372cb30604
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716459"
---
# <a name="substring-ssis-expression"></a><span data-ttu-id="458ea-102">SUBSTRING (espressione SSIS)</span><span class="sxs-lookup"><span data-stu-id="458ea-102">SUBSTRING (SSIS Expression)</span></span>
  <span data-ttu-id="458ea-103">Viene restituita la parte di un'espressione di caratteri che inizia in corrispondenza della posizione specificata e ha la lunghezza specificata.</span><span class="sxs-lookup"><span data-stu-id="458ea-103">Returns the part of a character expression that starts at the specified position and has the specified length.</span></span> <span data-ttu-id="458ea-104">I parametri *position* e *length* devono restituire valori integer.</span><span class="sxs-lookup"><span data-stu-id="458ea-104">The *position* parameter and the *length* parameter must evaluate to integers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="458ea-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="458ea-105">Syntax</span></span>  
  
```  
  
SUBSTRING(character_expression, position, length)  
```  
  
## <a name="arguments"></a><span data-ttu-id="458ea-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="458ea-106">Arguments</span></span>  
 <span data-ttu-id="458ea-107">*character_expression*</span><span class="sxs-lookup"><span data-stu-id="458ea-107">*character_expression*</span></span>  
 <span data-ttu-id="458ea-108">Espressione di caratteri da cui estrarre i caratteri.</span><span class="sxs-lookup"><span data-stu-id="458ea-108">Is a character expression from which to extract characters.</span></span>  
  
 <span data-ttu-id="458ea-109">*position*</span><span class="sxs-lookup"><span data-stu-id="458ea-109">*position*</span></span>  
 <span data-ttu-id="458ea-110">Numero intero che indica il punto iniziale della sottostringa.</span><span class="sxs-lookup"><span data-stu-id="458ea-110">Is an integer that specifies where the substring begins.</span></span>  
  
 <span data-ttu-id="458ea-111">*length*</span><span class="sxs-lookup"><span data-stu-id="458ea-111">*length*</span></span>  
 <span data-ttu-id="458ea-112">Valore integer che specifica la lunghezza della sottostringa come numero di caratteri.</span><span class="sxs-lookup"><span data-stu-id="458ea-112">Is an integer that specifies the length of the substring as number of characters.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="458ea-113">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="458ea-113">Result Types</span></span>  
 <span data-ttu-id="458ea-114">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="458ea-114">DT_WSTR</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="458ea-115">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="458ea-115">Remarks</span></span>  
 <span data-ttu-id="458ea-116">La funzione SUBSTRING utilizza un indice in base uno.</span><span class="sxs-lookup"><span data-stu-id="458ea-116">SUBSTRING uses a one-based index.</span></span> <span data-ttu-id="458ea-117">Se *position* ha valore 1, la sottostringa inizia dal primo carattere in *character_expression*.</span><span class="sxs-lookup"><span data-stu-id="458ea-117">If *position* is 1, the substring begins with the first character in *character_expression*.</span></span>  
  
 <span data-ttu-id="458ea-118">È possibile utilizzare SUBSTRING solo con il tipo di dati DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="458ea-118">SUBSTRING works only with the DT_WSTR data type.</span></span> <span data-ttu-id="458ea-119">Se l'argomento *character_expression* è un valore letterale stringa o una colonna di dati con tipo di dati DT_STR, prima di eseguire l'operazione prevista da SUBSTRING verrà eseguito il cast implicito al tipo di dati DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="458ea-119">A *character_expression* argument that is a string literal or a data column with the DT_STR data type is implicitly cast to the DT_WSTR data type before SUBSTRING performs its operation.</span></span> <span data-ttu-id="458ea-120">Per gli altri tipi di dati è necessario il cast esplicito al tipo di dati DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="458ea-120">Other data types must be explicitly cast to the DT_WSTR data type.</span></span> <span data-ttu-id="458ea-121">Per altre informazioni, vedere [Tipi di dati di Integration Services](../data-flow/integration-services-data-types.md) e [Cast &#40;espressione SSIS&#41;](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="458ea-121">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md) and [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="458ea-122">Se l'argomento è Null, SUBSTRING restituirà Null.</span><span class="sxs-lookup"><span data-stu-id="458ea-122">SUBSTRING returns a null result if the argument is null.</span></span>  
  
 <span data-ttu-id="458ea-123">Tutti gli argomenti nell'espressione possono utilizzare variabili e colonne.</span><span class="sxs-lookup"><span data-stu-id="458ea-123">All arguments in the expression can use variables and columns.</span></span>  
  
 <span data-ttu-id="458ea-124">Il valore dell'argomento *length* può superare la lunghezza della stringa.</span><span class="sxs-lookup"><span data-stu-id="458ea-124">The *length* argument can exceed the length of the string.</span></span> <span data-ttu-id="458ea-125">In questo caso la funzione restituisce la parte rimanente della stringa.</span><span class="sxs-lookup"><span data-stu-id="458ea-125">In that case, the function returns the remainder of the string.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="458ea-126">Esempi di espressione</span><span class="sxs-lookup"><span data-stu-id="458ea-126">Expression Examples</span></span>  
 <span data-ttu-id="458ea-127">In questo esempio vengono restituiti due caratteri da un valore letterale stringa, a partire dal carattere 4.</span><span class="sxs-lookup"><span data-stu-id="458ea-127">This example returns two characters, beginning with character 4, from a string literal.</span></span> <span data-ttu-id="458ea-128">Il risultato restituito è "ph".</span><span class="sxs-lookup"><span data-stu-id="458ea-128">The return result is "ph".</span></span>  
  
```  
SUBSTRING("elephant",4,2)  
```  
  
 <span data-ttu-id="458ea-129">In questo esempio viene restituita la parte rimanente da un valore letterale stringa, a partire dal quarto carattere.</span><span class="sxs-lookup"><span data-stu-id="458ea-129">This example returns the remainder of a string literal, beginning at the fourth character.</span></span> <span data-ttu-id="458ea-130">Il risultato restituito è "phant".</span><span class="sxs-lookup"><span data-stu-id="458ea-130">The return result is "phant".</span></span> <span data-ttu-id="458ea-131">Se il valore dell'argomento *length* supera la lunghezza delle stringa, non si tratta di un errore.</span><span class="sxs-lookup"><span data-stu-id="458ea-131">It is not an error for the *length* argument to exceed the length of the string.</span></span>  
  
```  
SUBSTRING ("elephant",4,50)  
```  
  
 <span data-ttu-id="458ea-132">In questo esempio viene restituita la prima lettera della colonna **MiddleName** .</span><span class="sxs-lookup"><span data-stu-id="458ea-132">This example returns the first letter from the **MiddleName** column.</span></span>  
  
```  
SUBSTRING(MiddleName,1,1)  
```  
  
 <span data-ttu-id="458ea-133">In questo esempio negli argomenti *position* e *length* vengono utilizzate alcune variabili.</span><span class="sxs-lookup"><span data-stu-id="458ea-133">This example uses variables in the *position* and *length* arguments.</span></span> <span data-ttu-id="458ea-134">Se **Start** ha valore 1 e **Length** ha valore 5, la funzione restituirà i primi cinque caratteri nella colonna **Name** .</span><span class="sxs-lookup"><span data-stu-id="458ea-134">If **Start** is 1 and **Length** is 5, the function returns the first five characters in the **Name** column.</span></span>  
  
```  
SUBSTRING(Name,@Start,@Length)  
```  
  
 <span data-ttu-id="458ea-135">In questo esempio vengono restituiti quattro caratteri nella variabile **PostalCode** , a partire dal sesto.</span><span class="sxs-lookup"><span data-stu-id="458ea-135">This example returns the last four characters from the **PostalCode** variable beginning at the sixth character.</span></span>  
  
```  
SUBSTRING (@PostalCode,6,4)  
```  
  
 <span data-ttu-id="458ea-136">In questo esempio viene restituita una stringa di lunghezza zero da un valore letterale stringa.</span><span class="sxs-lookup"><span data-stu-id="458ea-136">This example returns a zero-length string from a string literal.</span></span>  
  
```  
SUBSTRING ("Redmond",4,0)  
```  
  
## <a name="see-also"></a><span data-ttu-id="458ea-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="458ea-137">See Also</span></span>  
 [<span data-ttu-id="458ea-138">Funzioni &#40;espressione SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="458ea-138">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
