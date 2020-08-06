---
title: CODEPOINT (espressione SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- CODEPOINT function
- leftmost character of expression
ms.assetid: 0783d05e-7f35-42fb-a2c4-9621c46effd6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: bf05cc0838763ba9e22707af57892133d449da07
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624265"
---
# <a name="codepoint-ssis-expression"></a><span data-ttu-id="9c0df-102">CODEPOINT (espressione SSIS)</span><span class="sxs-lookup"><span data-stu-id="9c0df-102">CODEPOINT (SSIS Expression)</span></span>
  <span data-ttu-id="9c0df-103">Viene restituito l'elemento di codice Unicode del carattere più a sinistra di un'espressione di caratteri.</span><span class="sxs-lookup"><span data-stu-id="9c0df-103">Returns the Unicode code point of the leftmost character of a character expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c0df-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9c0df-104">Syntax</span></span>  
  
```  
  
CODEPOINT(character_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="9c0df-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="9c0df-105">Arguments</span></span>  
 <span data-ttu-id="9c0df-106">*character_expression*</span><span class="sxs-lookup"><span data-stu-id="9c0df-106">*character_expression*</span></span>  
 <span data-ttu-id="9c0df-107">Espressione di caratteri di cui restituire il primo carattere a sinistra.</span><span class="sxs-lookup"><span data-stu-id="9c0df-107">Is a character expression whose leftmost character will be evaluated.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="9c0df-108">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="9c0df-108">Result Types</span></span>  
 <span data-ttu-id="9c0df-109">DT_UI2</span><span class="sxs-lookup"><span data-stu-id="9c0df-109">DT_UI2</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9c0df-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="9c0df-110">Remarks</span></span>  
 <span data-ttu-id="9c0df-111">Il tipo di dati di*character_expression* deve essere DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="9c0df-111">*character_expression* must have the DT_WSTR data type.</span></span>  
  
 <span data-ttu-id="9c0df-112">Se il parametro *character_expression* è una stringa vuota o Null, tramite CODEPOINT verrà restituito Null.</span><span class="sxs-lookup"><span data-stu-id="9c0df-112">CODEPOINT returns a null result if *character_expression* is null or an empty string.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="9c0df-113">Esempi di espressione</span><span class="sxs-lookup"><span data-stu-id="9c0df-113">Expression Examples</span></span>  
 <span data-ttu-id="9c0df-114">In questo esempio viene utilizzato un valore letterale stringa.</span><span class="sxs-lookup"><span data-stu-id="9c0df-114">This example uses a string literal.</span></span> <span data-ttu-id="9c0df-115">Il risultato restituito è 77, l'elemento di codice Unicode corrispondente alla lettera M.</span><span class="sxs-lookup"><span data-stu-id="9c0df-115">The return result is 77, the Unicode code point for M.</span></span>  
  
```  
CODEPOINT("Mountain Bike")  
```  
  
 <span data-ttu-id="9c0df-116">In questo esempio viene utilizzata una variabile.</span><span class="sxs-lookup"><span data-stu-id="9c0df-116">This example uses a variable.</span></span> <span data-ttu-id="9c0df-117">Se **Name** contiene la stringa Touring Front Wheel, il risultato restituito sarà 84, l'elemento di codice Unicode corrispondente alla lettera T.</span><span class="sxs-lookup"><span data-stu-id="9c0df-117">If **Name** is Touring Front Wheel, the return result is 84, the Unicode code point for T.</span></span>  
  
```  
CODEPOINT(@Name)  
```  
  
## <a name="see-also"></a><span data-ttu-id="9c0df-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9c0df-118">See Also</span></span>  
 [<span data-ttu-id="9c0df-119">Funzioni &#40;espressione SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="9c0df-119">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
