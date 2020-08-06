---
title: LEN (espressione SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- LEN function
- number of characters
ms.assetid: d961398b-e4d0-4936-be17-8f4c5882a640
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8863864168295a3a9a924df588312ee65b6f7fa7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627303"
---
# <a name="len-ssis-expression"></a><span data-ttu-id="7ba1d-102">LEN (espressione SSIS)</span><span class="sxs-lookup"><span data-stu-id="7ba1d-102">LEN (SSIS Expression)</span></span>
  <span data-ttu-id="7ba1d-103">Viene restituito il numero di caratteri in un'espressione di caratteri.</span><span class="sxs-lookup"><span data-stu-id="7ba1d-103">Returns the number of characters in a character expression.</span></span> <span data-ttu-id="7ba1d-104">Se la stringa contiene spazi vuoti iniziali e finali, la funzione li includerà nel conteggio.</span><span class="sxs-lookup"><span data-stu-id="7ba1d-104">If the string includes leading and trailing blanks, the function includes them in the count.</span></span> <span data-ttu-id="7ba1d-105">Per una stessa stringa rappresentata con caratteri a uno e due byte, LEN restituisce valori identici.</span><span class="sxs-lookup"><span data-stu-id="7ba1d-105">LEN returns identical values for the same string of single and double byte characters.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ba1d-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7ba1d-106">Syntax</span></span>  
  
```  
  
LEN(character_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="7ba1d-107">Argomenti</span><span class="sxs-lookup"><span data-stu-id="7ba1d-107">Arguments</span></span>  
 <span data-ttu-id="7ba1d-108">*character_expression*</span><span class="sxs-lookup"><span data-stu-id="7ba1d-108">*character_expression*</span></span>  
 <span data-ttu-id="7ba1d-109">Espressione da valutare.</span><span class="sxs-lookup"><span data-stu-id="7ba1d-109">Is the expression to evaluate.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="7ba1d-110">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="7ba1d-110">Result Types</span></span>  
 <span data-ttu-id="7ba1d-111">DT_I4</span><span class="sxs-lookup"><span data-stu-id="7ba1d-111">DT_I4</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7ba1d-112">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="7ba1d-112">Remarks</span></span>  
 <span data-ttu-id="7ba1d-113">L'argomento *character_expression* può essere un tipo di dati DT_WSTR, DT_TEXT, DT_NTEXT o DT_IMAGE.</span><span class="sxs-lookup"><span data-stu-id="7ba1d-113">The *character_expression* argument can be a DT_WSTR, DT_TEXT, DT_NTEXT, or DT_IMAGE data type.</span></span> <span data-ttu-id="7ba1d-114">Per altre informazioni, vedere [Tipi di dati di Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="7ba1d-114">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="7ba1d-115">Se *character_expression* è un valore letterale stringa o una colonna di dati con tipo di dati DT_STR, prima di eseguire l'operazione prevista da LEN verrà eseguito il cast implicito al tipo di dati DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="7ba1d-115">If *character_expression* is a string literal or a data column with the DT_STR data type, it is implicitly cast to the DT_WSTR data type before LEN performs its operation.</span></span> <span data-ttu-id="7ba1d-116">Per gli altri tipi di dati è necessario il cast esplicito al tipo di dati DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="7ba1d-116">Other data types must be explicitly cast to the DT_WSTR data type.</span></span> <span data-ttu-id="7ba1d-117">Per altre informazioni, vedere [Cast &#40;espressione SSIS&#41;](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="7ba1d-117">For more information, see [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="7ba1d-118">Se l'argomento passato alla funzione LEN ha un tipo di dati BLOB (Binary Large Object), ad esempio DT_TEXT, DT_NTEXT o DT_IMAGE, la funzione restituirà il numero dei byte.</span><span class="sxs-lookup"><span data-stu-id="7ba1d-118">If the argument passed to the LEN function has a Binary Large Object Block (BLOB) data type, such as DT_TEXT, DT_NTEXT, or DT_IMAGE, the function returns a byte count.</span></span>  
  
 <span data-ttu-id="7ba1d-119">Se l'argomento è Null, LEN restituirà Null.</span><span class="sxs-lookup"><span data-stu-id="7ba1d-119">LEN returns a null result if the argument is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="7ba1d-120">Esempi di espressione</span><span class="sxs-lookup"><span data-stu-id="7ba1d-120">Expression Examples</span></span>  
 <span data-ttu-id="7ba1d-121">In questo esempio viene restituita la lunghezza di un valore letterale stringa.</span><span class="sxs-lookup"><span data-stu-id="7ba1d-121">This example returns the length of a string literal.</span></span> <span data-ttu-id="7ba1d-122">Il risultato restituito è 12.</span><span class="sxs-lookup"><span data-stu-id="7ba1d-122">The return result is 12.</span></span>  
  
```  
LEN("Ball Bearing")  
```  
  
 <span data-ttu-id="7ba1d-123">In questo esempio viene restituita la differenza tra le lunghezze dei valori nelle colonne **FirstName** e **LastName** .</span><span class="sxs-lookup"><span data-stu-id="7ba1d-123">This example returns the difference between the length of values in the **FirstName** and **LastName** columns.</span></span>  
  
```  
LEN(FirstName) - LEN(LastName)  
```  
  
 <span data-ttu-id="7ba1d-124">In questo esempio viene restituita la lunghezza di un nome di computer usando la variabile di sistema **MachineName**.</span><span class="sxs-lookup"><span data-stu-id="7ba1d-124">Returns the length of a computer name using the System variable **MachineName**.</span></span>  
  
```  
LEN(@MachineName)  
```  
  
## <a name="see-also"></a><span data-ttu-id="7ba1d-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7ba1d-125">See Also</span></span>  
 [<span data-ttu-id="7ba1d-126">Funzioni &#40;espressione SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="7ba1d-126">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
