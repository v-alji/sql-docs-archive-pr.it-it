---
title: LEFT (espressione SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 5634dbfb-740d-4c93-8fd5-2854cc741327
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7f21d134988414c7d8579d720877feec45383270
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636274"
---
# <a name="left-ssis-expression"></a><span data-ttu-id="31570-102">LEFT (espressione SSIS)</span><span class="sxs-lookup"><span data-stu-id="31570-102">LEFT (SSIS Expression)</span></span>
  <span data-ttu-id="31570-103">Viene restituito il numero specificato di caratteri della parte più a sinistra dell'espressione di caratteri indicata.</span><span class="sxs-lookup"><span data-stu-id="31570-103">Returns the specified number of characters from the leftmost portion of the given character expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31570-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="31570-104">Syntax</span></span>  
  
```  
  
LEFT(character_expression,number)  
```  
  
## <a name="arguments"></a><span data-ttu-id="31570-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="31570-105">Arguments</span></span>  
 <span data-ttu-id="31570-106">*character_expression*</span><span class="sxs-lookup"><span data-stu-id="31570-106">*character_expression*</span></span>  
 <span data-ttu-id="31570-107">Espressione di caratteri da cui estrarre i caratteri.</span><span class="sxs-lookup"><span data-stu-id="31570-107">Is a character expression from which to extract characters.</span></span>  
  
 <span data-ttu-id="31570-108">*number*</span><span class="sxs-lookup"><span data-stu-id="31570-108">*number*</span></span>  
 <span data-ttu-id="31570-109">Espressione integer in cui viene indicato il numero di caratteri da restituire.</span><span class="sxs-lookup"><span data-stu-id="31570-109">Is an integer expression that indicates the number of characters to be returned.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="31570-110">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="31570-110">Result Types</span></span>  
 <span data-ttu-id="31570-111">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="31570-111">DT_WSTR</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="31570-112">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="31570-112">Remarks</span></span>  
 <span data-ttu-id="31570-113">Se *number* è maggiore della lunghezza di *character_expression*, la funzione restituisce *character_expression*.</span><span class="sxs-lookup"><span data-stu-id="31570-113">If *number* is greater than the length of *character_expression*, the function returns *character_expression*.</span></span>  
  
 <span data-ttu-id="31570-114">Se *number* ha valore zero, la funzione restituirà una stringa di lunghezza zero.</span><span class="sxs-lookup"><span data-stu-id="31570-114">If *number* is zero, the function returns a zero-length string.</span></span>  
  
 <span data-ttu-id="31570-115">Se *number* è un numero negativo, la funzione restituirà un errore.</span><span class="sxs-lookup"><span data-stu-id="31570-115">If *number* is a negative number, the function returns an error.</span></span>  
  
 <span data-ttu-id="31570-116">L'argomento *number* accetta variabili e colonne.</span><span class="sxs-lookup"><span data-stu-id="31570-116">The *number* argument can take variables and columns.</span></span>  
  
 <span data-ttu-id="31570-117">È possibile utilizzare LEFT solo con il tipo di dati DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="31570-117">LEFT works only with the DT_WSTR data type.</span></span> <span data-ttu-id="31570-118">Se l'argomento *character_expression* è un valore letterale stringa o una colonna di dati con tipo di dati DT_STR, prima di eseguire l'operazione prevista da LEFT verrà eseguito il cast implicito al tipo di dati DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="31570-118">A *character_expression* argument that is a string literal or a data column with the DT_STR data type is implicitly cast to the DT_WSTR data type before LEFT performs its operation.</span></span> <span data-ttu-id="31570-119">Per gli altri tipi di dati è necessario il cast esplicito al tipo di dati DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="31570-119">Other data types must be explicitly cast to the DT_WSTR data type.</span></span> <span data-ttu-id="31570-120">Per altre informazioni, vedere [Tipi di dati di Integration Services](../data-flow/integration-services-data-types.md) e [Cast &#40;espressione SSIS&#41;](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="31570-120">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md) and [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="31570-121">Se l'argomento è Null, verrà restituito Null da LEFT.</span><span class="sxs-lookup"><span data-stu-id="31570-121">LEFT returns a null result if either argument is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="31570-122">Esempi di espressione</span><span class="sxs-lookup"><span data-stu-id="31570-122">Expression Examples</span></span>  
 <span data-ttu-id="31570-123">Nell'esempio seguente viene utilizzato un valore letterale stringa.</span><span class="sxs-lookup"><span data-stu-id="31570-123">The following example uses a string literal.</span></span> <span data-ttu-id="31570-124">Il risultato restituito sarà `"Mountain"`.</span><span class="sxs-lookup"><span data-stu-id="31570-124">The return result is `"Mountain"`.</span></span>  
  
```  
LEFT("Mountain Bike", 8)  
```  
  
## <a name="see-also"></a><span data-ttu-id="31570-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="31570-125">See Also</span></span>  
 <span data-ttu-id="31570-126">[RIGHT &#40;espressione SSIS&#41;](right-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="31570-126">[RIGHT &#40;SSIS Expression&#41;](right-ssis-expression.md) </span></span>  
 [<span data-ttu-id="31570-127">Funzioni &#40;espressione SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="31570-127">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
