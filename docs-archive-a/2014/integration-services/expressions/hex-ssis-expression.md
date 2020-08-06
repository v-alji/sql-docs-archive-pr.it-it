---
title: HEX (espressione SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- hexadecimal data
- HEX function
ms.assetid: f5d471ee-aeef-421c-b6e1-55b9676c3842
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 640ae38ec5d2cd5ffb448e9aebde5ba5ceba2684
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721651"
---
# <a name="hex-ssis-expression"></a><span data-ttu-id="ee721-102">HEX (espressione SSIS)</span><span class="sxs-lookup"><span data-stu-id="ee721-102">HEX (SSIS Expression)</span></span>
  <span data-ttu-id="ee721-103">Viene restituita una stringa che rappresenta il valore esadecimale di un valore integer.</span><span class="sxs-lookup"><span data-stu-id="ee721-103">Returns a string representing the hexadecimal value of an integer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee721-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ee721-104">Syntax</span></span>  
  
```  
  
HEX(integer_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="ee721-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="ee721-105">Arguments</span></span>  
 <span data-ttu-id="ee721-106">*integer_expression*</span><span class="sxs-lookup"><span data-stu-id="ee721-106">*integer_expression*</span></span>  
 <span data-ttu-id="ee721-107">Valore integer con o senza segno.</span><span class="sxs-lookup"><span data-stu-id="ee721-107">Is a signed or unsigned integer.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="ee721-108">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="ee721-108">Result Types</span></span>  
 <span data-ttu-id="ee721-109">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="ee721-109">DT_WSTR</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ee721-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="ee721-110">Remarks</span></span>  
 <span data-ttu-id="ee721-111">HEX restituisce Null se *integer_expression* è Null.</span><span class="sxs-lookup"><span data-stu-id="ee721-111">HEX returns null if *integer_expression* is null.</span></span>  
  
 <span data-ttu-id="ee721-112">L'argomento *integer_expression* argomento deve valutare un numero intero.</span><span class="sxs-lookup"><span data-stu-id="ee721-112">The *integer_expression* argument must evaluate to an integer.</span></span> <span data-ttu-id="ee721-113">Per altre informazioni, vedere [Tipi di dati di Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="ee721-113">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="ee721-114">Il risultato restituito non include qualificatori, ad esempio il prefisso 0x.</span><span class="sxs-lookup"><span data-stu-id="ee721-114">The return result does not include qualifiers such as the 0x prefix.</span></span> <span data-ttu-id="ee721-115">Per includere un prefisso, utilizzare l'operatore di concatenazione (+).</span><span class="sxs-lookup"><span data-stu-id="ee721-115">To include a prefix, use the + (Concatenate) operator.</span></span> <span data-ttu-id="ee721-116">Per altre informazioni, vedere [+ &#40;concatenazione&#41; &#40;espressione SSIS&#41;](concatenate-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="ee721-116">For more information, see [+ &#40;Concatenate&#41; &#40;SSIS Expression&#41;](concatenate-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="ee721-117">Le lettere da A a F, usate nella notazione esadecimale, vengono visualizzate in maiuscolo.</span><span class="sxs-lookup"><span data-stu-id="ee721-117">The letters A - F, used in HEX notations, appear as uppercase characters.</span></span>  
  
 <span data-ttu-id="ee721-118">La lunghezza della stringa risultante per i tipi di dati integer è la seguente:</span><span class="sxs-lookup"><span data-stu-id="ee721-118">The length of the resulting string for integer data types is as follows:</span></span>  
  
-   <span data-ttu-id="ee721-119">Per i tipi di dati DT_I1 e DT_UI1 viene restituita una stringa con lunghezza massima pari a 2.</span><span class="sxs-lookup"><span data-stu-id="ee721-119">DT_I1 and DT_UI1 return a string with a maximum length of 2.</span></span>  
  
-   <span data-ttu-id="ee721-120">Per i tipi di dati DT_I2 e DT_UI2 viene restituita una stringa con lunghezza massima pari a 4.</span><span class="sxs-lookup"><span data-stu-id="ee721-120">DT_I2 and DT_UI2 return a string with a maximum length of 4.</span></span>  
  
-   <span data-ttu-id="ee721-121">Per i tipi di dati DT_I4 e DT_UI4 viene restituita una stringa con lunghezza massima pari a 8.</span><span class="sxs-lookup"><span data-stu-id="ee721-121">DT_I4 and DT_UI4 return a string with a maximum length of 8.</span></span>  
  
-   <span data-ttu-id="ee721-122">Per i tipi di dati DT_I8 e DT_UI8 viene restituita una stringa con lunghezza massima pari a 16.</span><span class="sxs-lookup"><span data-stu-id="ee721-122">DT_I8 and DT_UI8 return a string with a maximum length of 16.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="ee721-123">Esempi di espressione</span><span class="sxs-lookup"><span data-stu-id="ee721-123">Expression Examples</span></span>  
 <span data-ttu-id="ee721-124">In questo esempio viene utilizzato un valore letterale numerico.</span><span class="sxs-lookup"><span data-stu-id="ee721-124">This example uses a numeric literal.</span></span> <span data-ttu-id="ee721-125">La funzione restituisce il valore 190.</span><span class="sxs-lookup"><span data-stu-id="ee721-125">The function returns the value 190.</span></span>  
  
```  
HEX(400)   
```  
  
 <span data-ttu-id="ee721-126">In questo esempio viene usata la colonna **ReorderPoint** .</span><span class="sxs-lookup"><span data-stu-id="ee721-126">This example uses the **ReorderPoint** column.</span></span> <span data-ttu-id="ee721-127">Il tipo di dati della colonna è `smallint`.</span><span class="sxs-lookup"><span data-stu-id="ee721-127">The column data type is `smallint`.</span></span> <span data-ttu-id="ee721-128">Se **ReorderPoint** ha valore 750, la funzione restituirà 2EE.</span><span class="sxs-lookup"><span data-stu-id="ee721-128">If **ReorderPoint** is 750, the function returns 2EE.</span></span>  
  
```  
HEX(ReorderPoint)   
```  
  
 <span data-ttu-id="ee721-129">In questo esempio viene usata la variabile di sistema **LocaleID**.</span><span class="sxs-lookup"><span data-stu-id="ee721-129">This example uses **LocaleID**, a system variable.</span></span> <span data-ttu-id="ee721-130">Se **LocaleID** ha valore 1033, la funzione restituirà 409.</span><span class="sxs-lookup"><span data-stu-id="ee721-130">If **LocaleID** is 1033, the function returns 409.</span></span>  
  
```  
HEX(@LocaleID)  
```  
  
## <a name="see-also"></a><span data-ttu-id="ee721-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ee721-131">See Also</span></span>  
 [<span data-ttu-id="ee721-132">Funzioni &#40;espressione SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="ee721-132">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
