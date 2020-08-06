---
title: REPLICATE (espressione SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- REPLICATE function
ms.assetid: e7a37b93-6d1d-42d5-9a65-de1790abf6a5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9502df5bc20c6ad85f1f98fb57fe6b3cf431cc20
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716496"
---
# <a name="replicate-ssis-expression"></a><span data-ttu-id="4c06d-102">REPLICATE (espressione SSIS)</span><span class="sxs-lookup"><span data-stu-id="4c06d-102">REPLICATE (SSIS Expression)</span></span>
  <span data-ttu-id="4c06d-103">Viene restituita un'espressione di caratteri ripetuta per il numero di volte specificato.</span><span class="sxs-lookup"><span data-stu-id="4c06d-103">Returns a character expression that is replicated a number of times.</span></span> <span data-ttu-id="4c06d-104">L'argomento *numero di volte* deve restituire un Integer.</span><span class="sxs-lookup"><span data-stu-id="4c06d-104">The *times* argument must evaluate to an integer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4c06d-105">La funzione REPLICATE utilizza spesso stringhe lunghe e pertanto è più facile che un'espressione superi il limite di 4000 caratteri di lunghezza.</span><span class="sxs-lookup"><span data-stu-id="4c06d-105">The REPLICATE function frequently uses long strings, and therefore is more likely to incur the 4000-character limit on expression length.</span></span> <span data-ttu-id="4c06d-106">Se il risultato della valutazione di un'espressione ha il tipo di dati Integration Services DT_WSTR o DT_STR, l'espressione verrà troncata a 4000 caratteri.</span><span class="sxs-lookup"><span data-stu-id="4c06d-106">If the evaluation result of an expression has the Integration Services data type DT_WSTR or DT_STR, the expression will be truncated at 4000 characters.</span></span> <span data-ttu-id="4c06d-107">Se il tipo di risultato di una sottoespressione è DT_STR o DT_WSTR, probabilmente la sottoespressione verrà troncata a 4000 caratteri, indipendentemente dal tipo di risultato dell'espressione globale.</span><span class="sxs-lookup"><span data-stu-id="4c06d-107">If the result type of a sub-expression is DT_STR or DT_WSTR, that sub-expression likewise will be truncated to 4000 characters, regardless of the overall expression result type.</span></span> <span data-ttu-id="4c06d-108">Le conseguenze del troncamento possono essere gestite normalmente oppure generare un avviso o un errore.</span><span class="sxs-lookup"><span data-stu-id="4c06d-108">The consequences of truncation can be handled gracefully or cause a warning or an error.</span></span> <span data-ttu-id="4c06d-109">Per altre informazioni, vedere [Sintassi &#40;SSIS&#41;](syntax-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="4c06d-109">For more information, see [Syntax &#40;SSIS&#41;](syntax-ssis.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c06d-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4c06d-110">Syntax</span></span>  
  
```  
  
REPLICATE(character_expression,times)  
```  
  
## <a name="arguments"></a><span data-ttu-id="4c06d-111">Argomenti</span><span class="sxs-lookup"><span data-stu-id="4c06d-111">Arguments</span></span>  
 <span data-ttu-id="4c06d-112">*character_expression*</span><span class="sxs-lookup"><span data-stu-id="4c06d-112">*character_expression*</span></span>  
 <span data-ttu-id="4c06d-113">Espressione di caratteri da replicare.</span><span class="sxs-lookup"><span data-stu-id="4c06d-113">Is a character expression to replicate.</span></span>  
  
 <span data-ttu-id="4c06d-114">*numero di volte*</span><span class="sxs-lookup"><span data-stu-id="4c06d-114">*times*</span></span>  
 <span data-ttu-id="4c06d-115">Espressione Integer che specifica il numero di volte in cui *character_expression* viene replicata.</span><span class="sxs-lookup"><span data-stu-id="4c06d-115">Is an integer expression that specifies the number of times *character_expression* is replicated.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="4c06d-116">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="4c06d-116">Result Types</span></span>  
 <span data-ttu-id="4c06d-117">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="4c06d-117">DT_WSTR</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4c06d-118">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="4c06d-118">Remarks</span></span>  
 <span data-ttu-id="4c06d-119">Se il *numero di volte* ha valore zero, la funzione restituirà una stringa di lunghezza zero.</span><span class="sxs-lookup"><span data-stu-id="4c06d-119">If *times* is zero, the function returns a zero-length string.</span></span>  
  
 <span data-ttu-id="4c06d-120">Se il *numero di volte* è un numero negativo, la funzione restituirà un errore.</span><span class="sxs-lookup"><span data-stu-id="4c06d-120">If *times* is a negative number, the function returns an error.</span></span>  
  
 <span data-ttu-id="4c06d-121">L'argomento *numero di volte* può usare anche variabili e colonne.</span><span class="sxs-lookup"><span data-stu-id="4c06d-121">The *times* argument can also use variables and columns.</span></span>  
  
 <span data-ttu-id="4c06d-122">È possibile utilizzare REPLICATE solo con il tipo di dati DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="4c06d-122">REPLICATE works only with the DT_WSTR data type.</span></span> <span data-ttu-id="4c06d-123">Se l'argomento *character_expression* è un valore letterale stringa o una colonna di dati con tipo di dati DT_STR, prima di eseguire l'operazione prevista da REPLICATE verrà eseguito il cast implicito al tipo di dati DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="4c06d-123">A *character_expression* argument that is a string literal or a data column with the DT_STR data type is implicitly cast to the DT_WSTR data type before REPLICATE performs its operation.</span></span> <span data-ttu-id="4c06d-124">Per gli altri tipi di dati è necessario il cast esplicito al tipo di dati DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="4c06d-124">Other data types must be explicitly cast to the DT_WSTR data type.</span></span> <span data-ttu-id="4c06d-125">Per altre informazioni, vedere [Tipi di dati di Integration Services](../data-flow/integration-services-data-types.md) e [Cast &#40;espressione SSIS&#41;](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="4c06d-125">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md) and [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="4c06d-126">Se l'argomento è Null, REPLICATE restituirà Null.</span><span class="sxs-lookup"><span data-stu-id="4c06d-126">REPLICATE returns a null result if either argument is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="4c06d-127">Esempi di espressione</span><span class="sxs-lookup"><span data-stu-id="4c06d-127">Expression Examples</span></span>  
 <span data-ttu-id="4c06d-128">In questo esempio un valore letterale stringa viene replicato tre volte.</span><span class="sxs-lookup"><span data-stu-id="4c06d-128">This example replicates a string literal three times.</span></span> <span data-ttu-id="4c06d-129">Il risultato restituito è "Mountain BikeMountain BikeMountain Bike".</span><span class="sxs-lookup"><span data-stu-id="4c06d-129">The return result is "Mountain BikeMountain BikeMountain Bike".</span></span>  
  
```  
REPLICATE("Mountain Bike", 3)  
```  
  
 <span data-ttu-id="4c06d-130">In questo esempio i valori nella colonna **Nome** vengono replicati per il numero di volte indicato dal valore della variabile **Numero di volte** .</span><span class="sxs-lookup"><span data-stu-id="4c06d-130">This example replicates values in the **Name** column by the value in the **Times** variable.</span></span> <span data-ttu-id="4c06d-131">Se **Numero di volte** ha valore 3 e **Nome** contiene Touring Front Wheel, il risultato restituito sarà Touring Front WheelTouring Front WheelTouring Front Wheel.</span><span class="sxs-lookup"><span data-stu-id="4c06d-131">If **Times** is 3 and **Name** is Touring Front Wheel, the return result is Touring Front WheelTouring Front WheelTouring Front Wheel.</span></span>  
  
```  
REPLICATE(Name, @Times)  
```  
  
 <span data-ttu-id="4c06d-132">In questo esempio i valori nella variabile **Nome** vengono replicati per il numero di volte indicato dal valore nella colonna **Numero di volte** .</span><span class="sxs-lookup"><span data-stu-id="4c06d-132">This example replicates the value in the **Name** variable by the value in the **Times** column.</span></span> <span data-ttu-id="4c06d-133">La variabile**Nome** ha un tipo di dati diverso da Integer e l'espressione include un cast esplicito a un tipo di dati Integer.</span><span class="sxs-lookup"><span data-stu-id="4c06d-133">**Times** has a non-integer data type and the expression includes an explicit cast to an integer data type.</span></span> <span data-ttu-id="4c06d-134">Se **Nome** contiene il testo Helmet e **Numero di volte** ha valore 2, il risultato restituito sarà "HelmetHelmet".</span><span class="sxs-lookup"><span data-stu-id="4c06d-134">If **Name** contains Helmet and **Times** is 2, the return result is "HelmetHelmet".</span></span>  
  
```  
REPLICATE(@Name, (DT_I4(Times))  
```  
  
## <a name="see-also"></a><span data-ttu-id="4c06d-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4c06d-135">See Also</span></span>  
 [<span data-ttu-id="4c06d-136">Funzioni &#40;espressione SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="4c06d-136">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
