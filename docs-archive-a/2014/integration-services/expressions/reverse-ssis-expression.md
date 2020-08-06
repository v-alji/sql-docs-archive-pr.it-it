---
title: REVERSE (espressione SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- REVERSE function
- reverse character expressions
ms.assetid: bcebcc55-7247-4896-8f53-4d582d58cfb4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2ace136eed0abcb9df7b25d9370c46d7556c1d48
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716495"
---
# <a name="reverse-ssis-expression"></a><span data-ttu-id="e25b5-102">REVERSE (espressione SSIS)</span><span class="sxs-lookup"><span data-stu-id="e25b5-102">REVERSE (SSIS Expression)</span></span>
  <span data-ttu-id="e25b5-103">Viene restituita un'espressione di caratteri in ordine inverso.</span><span class="sxs-lookup"><span data-stu-id="e25b5-103">Returns a character expression in reverse order.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e25b5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e25b5-104">Syntax</span></span>  
  
```  
  
REVERSE(character_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="e25b5-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="e25b5-105">Arguments</span></span>  
 <span data-ttu-id="e25b5-106">*character_expression*</span><span class="sxs-lookup"><span data-stu-id="e25b5-106">*character_expression*</span></span>  
 <span data-ttu-id="e25b5-107">Espressione di caratteri da invertire.</span><span class="sxs-lookup"><span data-stu-id="e25b5-107">Is a character expression to be reversed.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="e25b5-108">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="e25b5-108">Result Types</span></span>  
 <span data-ttu-id="e25b5-109">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="e25b5-109">DT_WSTR</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e25b5-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="e25b5-110">Remarks</span></span>  
 <span data-ttu-id="e25b5-111">Il tipo di dati dell’argomento *character_expression* deve essere DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="e25b5-111">The *character_expression* argument must have the DT_WSTR data type.</span></span>  
  
 <span data-ttu-id="e25b5-112">Se *character_expression* è null, REVERSE restituisce un risultato null.</span><span class="sxs-lookup"><span data-stu-id="e25b5-112">REVERSE returns a null result if *character_expression* is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="e25b5-113">Esempi di espressione</span><span class="sxs-lookup"><span data-stu-id="e25b5-113">Expression Examples</span></span>  
 <span data-ttu-id="e25b5-114">In questo esempio viene utilizzato un valore letterale stringa.</span><span class="sxs-lookup"><span data-stu-id="e25b5-114">This example uses a string literal.</span></span> <span data-ttu-id="e25b5-115">Il risultato restituito è "ekiB niatnuoM".</span><span class="sxs-lookup"><span data-stu-id="e25b5-115">The return result is "ekiB niatnuoM".</span></span>  
  
```  
REVERSE("Mountain Bike")  
```  
  
 <span data-ttu-id="e25b5-116">In questo esempio viene utilizzata una variabile.</span><span class="sxs-lookup"><span data-stu-id="e25b5-116">This example uses a variable.</span></span> <span data-ttu-id="e25b5-117">Se **Name** contiene Touring Bike, il risultato restituito sarà "ekiB gniruoT".</span><span class="sxs-lookup"><span data-stu-id="e25b5-117">If **Name** contains Touring Bike, the return result is "ekiB gniruoT".</span></span>  
  
```  
REVERSE(@Name)  
```  
  
## <a name="see-also"></a><span data-ttu-id="e25b5-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e25b5-118">See Also</span></span>  
 [<span data-ttu-id="e25b5-119">Funzioni &#40;espressione SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="e25b5-119">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
