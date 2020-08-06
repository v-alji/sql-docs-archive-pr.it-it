---
title: TRIM (espressione SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- leading blanks
- TRIM function
- trailing blanks
ms.assetid: 7dd9081d-a3d4-483a-bf7e-bf2bd7692d39
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 42cef8a816f399e39ac99061f34c394156bde45f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716440"
---
# <a name="trim-ssis-expression"></a><span data-ttu-id="c718d-102">TRIM (espressione SSIS)</span><span class="sxs-lookup"><span data-stu-id="c718d-102">TRIM (SSIS Expression)</span></span>
  <span data-ttu-id="c718d-103">Restituisce un'espressione di caratteri dopo aver rimosso gli spazi iniziali e finali.</span><span class="sxs-lookup"><span data-stu-id="c718d-103">Returns a character expression after removing leading and trailing spaces.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c718d-104">TRIM non rimuove altri caratteri spazio quali i caratteri di tabulazione o avanzamento riga.</span><span class="sxs-lookup"><span data-stu-id="c718d-104">TRIM does not remove white-space characters such as the tab or line feed characters.</span></span> <span data-ttu-id="c718d-105">Unicode offre elementi di codice per molti tipi diversi di spazi, ma questa funzione riconosce solo l'elemento di codice Unicode 0x0020.</span><span class="sxs-lookup"><span data-stu-id="c718d-105">Unicode provides code points for many different types of spaces, but this function recognizes only the Unicode code point 0x0020.</span></span> <span data-ttu-id="c718d-106">Quando stringhe DBCS (Double-Byte Character Set) vengono convertite in Unicode, possono includere caratteri spazio diversi da 0x0020 e la funzione non può rimuovere tali spazi.</span><span class="sxs-lookup"><span data-stu-id="c718d-106">When double-byte character set (DBCS) strings are converted to Unicode they may include space characters other than 0x0020 and the function cannot remove such spaces.</span></span> <span data-ttu-id="c718d-107">Per rimuovere qualsiasi tipo di spazi, è possibile utilizzare il metodo Microsoft Visual Basic .NET Trim in uno script eseguito dal componente Script.</span><span class="sxs-lookup"><span data-stu-id="c718d-107">To remove all kinds of spaces, you can use the Microsoft Visual Basic .NET Trim method in a script run from the Script component.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c718d-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c718d-108">Syntax</span></span>  
  
```  
  
TRIM(character_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="c718d-109">Argomenti</span><span class="sxs-lookup"><span data-stu-id="c718d-109">Arguments</span></span>  
 <span data-ttu-id="c718d-110">*character_expression*</span><span class="sxs-lookup"><span data-stu-id="c718d-110">*character_expression*</span></span>  
 <span data-ttu-id="c718d-111">Espressione di caratteri da cui rimuovere gli spazi.</span><span class="sxs-lookup"><span data-stu-id="c718d-111">Is a character expression from which to remove spaces.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="c718d-112">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="c718d-112">Result Types</span></span>  
 <span data-ttu-id="c718d-113">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="c718d-113">DT_WSTR</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c718d-114">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="c718d-114">Remarks</span></span>  
 <span data-ttu-id="c718d-115">Se l'argomento è Null, TRIM restituirà Null.</span><span class="sxs-lookup"><span data-stu-id="c718d-115">TRIM returns a null result if the argument is null.</span></span>  
  
 <span data-ttu-id="c718d-116">È possibile utilizzare TRIM solo con il tipo di dati DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="c718d-116">TRIM works only with the DT_WSTR data type.</span></span> <span data-ttu-id="c718d-117">Se l'argomento *character_expression* è un valore letterale stringa o una colonna di dati con tipo di dati DT_STR, prima di eseguire l'operazione prevista da TRIM verrà eseguito il cast implicito al tipo di dati DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="c718d-117">A *character_expression* argument that is a string literal or a data column with the DT_STR data type is implicitly cast to the DT_WSTR data type before TRIM performs its operation.</span></span> <span data-ttu-id="c718d-118">Per gli altri tipi di dati è necessario il cast esplicito al tipo di dati DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="c718d-118">Other data types must be explicitly cast to the DT_WSTR data type.</span></span> <span data-ttu-id="c718d-119">Per altre informazioni, vedere [Tipi di dati di Integration Services](../data-flow/integration-services-data-types.md) e [Cast &#40;espressione SSIS&#41;](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="c718d-119">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md) and [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="c718d-120">Esempi di espressione</span><span class="sxs-lookup"><span data-stu-id="c718d-120">Expression Examples</span></span>  
 <span data-ttu-id="c718d-121">In questo esempio vengono rimossi gli spazi iniziali e finali da un valore letterale stringa.</span><span class="sxs-lookup"><span data-stu-id="c718d-121">This example removes leading and trailing spaces from a string literal.</span></span> <span data-ttu-id="c718d-122">Il risultato restituito è "New York".</span><span class="sxs-lookup"><span data-stu-id="c718d-122">The return result is "New York".</span></span>  
  
```  
TRIM("   New York   ")  
```  
  
 <span data-ttu-id="c718d-123">In questo esempio vengono rimossi gli spazi iniziali e finali dal risultato della concatenazione delle colonne **FirstName** e **LastName** .</span><span class="sxs-lookup"><span data-stu-id="c718d-123">This example removes leading and trailing spaces from the result of concatenating the **FirstName** and **LastName** columns.</span></span> <span data-ttu-id="c718d-124">La stringa vuota tra **FirstName** e **LastName** non viene rimossa.</span><span class="sxs-lookup"><span data-stu-id="c718d-124">The empty string between **FirstName** and **LastName** is not removed.</span></span>  
  
```  
TRIM(FirstName + " "+ LastName)  
```  
  
## <a name="see-also"></a><span data-ttu-id="c718d-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c718d-125">See Also</span></span>  
 <span data-ttu-id="c718d-126">[LTRIM &#40;espressione SSIS&#41;](trim-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="c718d-126">[LTRIM &#40;SSIS Expression&#41;](trim-ssis-expression.md) </span></span>  
 <span data-ttu-id="c718d-127">[RTRIM &#40;espressione SSIS&#41;](rtrim-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="c718d-127">[RTRIM &#40;SSIS Expression&#41;](rtrim-ssis-expression.md) </span></span>  
 [<span data-ttu-id="c718d-128">Funzioni &#40;espressione SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="c718d-128">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
