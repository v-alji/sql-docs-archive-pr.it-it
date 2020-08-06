---
title: FINDSTRING (espressione SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- FINDSTRING function
ms.assetid: c83cb1b1-3c52-4496-b518-4c9253b9336d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 72f2ff21cb179ce565e60c6550b8ecc2618a5adb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627908"
---
# <a name="findstring-ssis-expression"></a><span data-ttu-id="20e25-102">FINDSTRING (espressione SSIS)</span><span class="sxs-lookup"><span data-stu-id="20e25-102">FINDSTRING (SSIS Expression)</span></span>
  <span data-ttu-id="20e25-103">Viene restituita la posizione dell'occorrenza specificata di una determinata stringa in un'espressione di caratteri.</span><span class="sxs-lookup"><span data-stu-id="20e25-103">Returns the location of the specified occurrence of a string within a character expression.</span></span> <span data-ttu-id="20e25-104">Il risultato restituito è l'indice in base 1 dell'occorrenza.</span><span class="sxs-lookup"><span data-stu-id="20e25-104">The return result is the one-based index of the occurrence.</span></span> <span data-ttu-id="20e25-105">Il parametro stringa deve restituire un'espressione di caratteri, mentre il parametro che indica l'occorrenza deve restituire un valore integer.</span><span class="sxs-lookup"><span data-stu-id="20e25-105">The string parameter must evaluate to a character expression, and the occurrence parameter must evaluate to an integer.</span></span> <span data-ttu-id="20e25-106">Se la stringa non viene trovata, verrà restituito il valore 0.</span><span class="sxs-lookup"><span data-stu-id="20e25-106">If the string is not found, the return value is 0.</span></span> <span data-ttu-id="20e25-107">Se il numero delle occorrenze della stringa è inferiore a quello specificato dall'argomento occurrence, verrà restituito il valore 0.</span><span class="sxs-lookup"><span data-stu-id="20e25-107">If the string occurs fewer times than the occurrence argument specifies, the return value is 0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20e25-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="20e25-108">Syntax</span></span>  
  
```  
  
FINDSTRING(character_expression, searchstring, occurrence)  
```  
  
## <a name="arguments"></a><span data-ttu-id="20e25-109">Argomenti</span><span class="sxs-lookup"><span data-stu-id="20e25-109">Arguments</span></span>  
 <span data-ttu-id="20e25-110">*character_expression*</span><span class="sxs-lookup"><span data-stu-id="20e25-110">*character_expression*</span></span>  
 <span data-ttu-id="20e25-111">Stringa di caratteri in cui eseguire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="20e25-111">Is the character string to search in.</span></span>  
  
 <span data-ttu-id="20e25-112">*searchstring*</span><span class="sxs-lookup"><span data-stu-id="20e25-112">*searchstring*</span></span>  
 <span data-ttu-id="20e25-113">Stringa di caratteri da cercare.</span><span class="sxs-lookup"><span data-stu-id="20e25-113">Is the character string to search for.</span></span>  
  
 <span data-ttu-id="20e25-114">*occurrence*</span><span class="sxs-lookup"><span data-stu-id="20e25-114">*occurrence*</span></span>  
 <span data-ttu-id="20e25-115">Numero intero con o senza segno che specifica l'occorrenza di *searchstring* di cui restituire la posizione.</span><span class="sxs-lookup"><span data-stu-id="20e25-115">Is a signed or unsigned integer specifying which occurrence of *searchstring* to report.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="20e25-116">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="20e25-116">Result Types</span></span>  
 <span data-ttu-id="20e25-117">DT_I4</span><span class="sxs-lookup"><span data-stu-id="20e25-117">DT_I4</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="20e25-118">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="20e25-118">Remarks</span></span>  
 <span data-ttu-id="20e25-119">È possibile utilizzare FINDSTRING solo con il tipo di dati DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="20e25-119">FINDSTRING works only with the DT_WSTR data type.</span></span>  <span data-ttu-id="20e25-120">Per gli argomenti*character_expression* e *searchstring* costituiti da valori letterali stringa o da colonne di dati con tipo di dati DT_STR, prima di eseguire l'operazione della funzione FINDSTRING viene eseguito il cast implicito al tipo di dati DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="20e25-120">*character_expression* and *searchstring* arguments that are string literals or data columns with the DT_STR data type are implicitly cast to the DT_WSTR data type before FINDSTRING performs its operation.</span></span> <span data-ttu-id="20e25-121">Per gli altri tipi di dati è necessario il cast esplicito al tipo di dati DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="20e25-121">Other data types must be explicitly cast to the DT_WSTR data type.</span></span> <span data-ttu-id="20e25-122">Per altre informazioni, vedere [Tipi di dati di Integration Services](../data-flow/integration-services-data-types.md) e [Cast &#40;espressione SSIS&#41;](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="20e25-122">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md) and [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="20e25-123">FINDSTRING restituirà Null se il valore *character_expression* o *searchstring* sono Null.</span><span class="sxs-lookup"><span data-stu-id="20e25-123">FINDSTRING returns null if either *character_expression* or *searchstring* are null.</span></span>  
  
 <span data-ttu-id="20e25-124">Utilizzare un valore 1 nell'argomento *occurrence* per ottenere l'indice della prima occorrenza, 2 per la seconda occorrenza e così via.</span><span class="sxs-lookup"><span data-stu-id="20e25-124">Use a value of 1 in the *occurrence* argument to get the index of the first occurrence, 2 for the second occurrence and so forth.</span></span>  
  
 <span data-ttu-id="20e25-125">L'argomento *occurrence* deve essere un numero intero maggiore di 0.</span><span class="sxs-lookup"><span data-stu-id="20e25-125">The *occurrence* must be an integer with a value greater than 0.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="20e25-126">Esempi di espressione</span><span class="sxs-lookup"><span data-stu-id="20e25-126">Expression Examples</span></span>  
 <span data-ttu-id="20e25-127">In questo esempio viene utilizzato un valore letterale stringa.</span><span class="sxs-lookup"><span data-stu-id="20e25-127">This example uses a string literal.</span></span> <span data-ttu-id="20e25-128">Il valore restituito è 11.</span><span class="sxs-lookup"><span data-stu-id="20e25-128">It returns the value 11.</span></span>  
  
```  
FINDSTRING("New York, NY, NY", "NY", 1)   
```  
  
 <span data-ttu-id="20e25-129">In questo esempio viene utilizzato un valore letterale stringa.</span><span class="sxs-lookup"><span data-stu-id="20e25-129">This example uses a string literal.</span></span> <span data-ttu-id="20e25-130">Poiché la stringa "NY" ricorre solo due volte, il risultato restituito è 0.</span><span class="sxs-lookup"><span data-stu-id="20e25-130">Because the string "NY" occurs only two times, the return result is 0.</span></span>  
  
```  
FINDSTRING("New York, NY, NY", "NY", 3)   
```  
  
 <span data-ttu-id="20e25-131">In questo esempio viene utilizzata la colonna **Name** .</span><span class="sxs-lookup"><span data-stu-id="20e25-131">This example uses the **Name** column.</span></span> <span data-ttu-id="20e25-132">Viene restituita la posizione del valore n nella colonna **Name** .</span><span class="sxs-lookup"><span data-stu-id="20e25-132">It returns the location of the value n in the **Name** column.</span></span> <span data-ttu-id="20e25-133">Il risultato restituito dipende dal valore di **Name**.</span><span class="sxs-lookup"><span data-stu-id="20e25-133">The return result varies depending on the value in **Name**.</span></span> <span data-ttu-id="20e25-134">Se **Name** contiene Anderson, la funzione restituirà 8.</span><span class="sxs-lookup"><span data-stu-id="20e25-134">If **Name** contains Anderson, the function returns 8.</span></span>  
  
```  
FINDSTRING(Name,"n", 2)   
```  
  
 <span data-ttu-id="20e25-135">In questo esempio vengono utilizzate le colonne **Name** e **Size** .</span><span class="sxs-lookup"><span data-stu-id="20e25-135">This example uses the **Name** and **Size** columns.</span></span> <span data-ttu-id="20e25-136">Viene restituita la posizione del primo carattere a sinistra del valore **Size** nella colonna **Name** .</span><span class="sxs-lookup"><span data-stu-id="20e25-136">It returns the location of the leftmost character of the **Size** value in the **Name** column.</span></span> <span data-ttu-id="20e25-137">Il risultato restituito dipende dai valori delle colonne.</span><span class="sxs-lookup"><span data-stu-id="20e25-137">The return result varies depending on column values.</span></span> <span data-ttu-id="20e25-138">Se **Name** contiene Mountain,500Red,42 e **Size** contiene 42, il risultato restituito sarà 17.</span><span class="sxs-lookup"><span data-stu-id="20e25-138">If **Name** contains Mountain,500Red,42 and **Size** contains 42, the return result is 17.</span></span>  
  
```  
FINDSTRING(Name,Size,1)   
```  
  
## <a name="see-also"></a><span data-ttu-id="20e25-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="20e25-139">See Also</span></span>  
 <span data-ttu-id="20e25-140">[REPLACE &#40;espressione SSIS&#41;](replace-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="20e25-140">[REPLACE &#40;SSIS Expression&#41;](replace-ssis-expression.md) </span></span>  
 [<span data-ttu-id="20e25-141">Funzioni &#40;espressione SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="20e25-141">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
