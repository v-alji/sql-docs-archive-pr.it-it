---
title: ^ (OR esclusivo bit per bit) (espressione SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- ^ (bitwise exclusive OR operator)
- bitwise exclusive OR (^)
ms.assetid: 6ac53cab-29c4-4835-9f87-371b058b2f38
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d86c3d810e9e5572af93c97f82c2275db2c979b0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635183"
---
# <a name="-bitwise-exclusive-or-ssis-expression"></a><span data-ttu-id="5852d-102">^ (OR esclusivo bit per bit) (espressione SSIS)</span><span class="sxs-lookup"><span data-stu-id="5852d-102">^ (Bitwise Exclusive OR) (SSIS Expression)</span></span>
  <span data-ttu-id="5852d-103">Viene eseguita un'operazione con OR esclusivo bit per bit su due valori integer.</span><span class="sxs-lookup"><span data-stu-id="5852d-103">Performs a bitwise exclusive OR operation of two integer values.</span></span> <span data-ttu-id="5852d-104">Confronta ogni bit del primo operando con il bit corrispondente del secondo operando.</span><span class="sxs-lookup"><span data-stu-id="5852d-104">It compares each bit of its first operand to the corresponding bit of its second operand.</span></span> <span data-ttu-id="5852d-105">Se un bit ha valore 0 e l'altro 1, il bit del risultato corrispondente verrà impostato su 1.</span><span class="sxs-lookup"><span data-stu-id="5852d-105">If one bit is 0 and the other bit is 1, the corresponding result bit is set to 1.</span></span> <span data-ttu-id="5852d-106">Se entrambi i bit hanno valore 0 o 1, il bit del risultato corrispondente verrà impostato su 0.</span><span class="sxs-lookup"><span data-stu-id="5852d-106">If both bits are 0 or both bits are 1, the corresponding result bit is set to 0.</span></span>  
  
 <span data-ttu-id="5852d-107">Entrambe le condizioni devono essere costituite da un valore con tipo di dati Integer con segno o da un valore con tipo di dati Integer senza segno.</span><span class="sxs-lookup"><span data-stu-id="5852d-107">Both conditions must be a signed integer data type or both conditions must be an unsigned integer data type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5852d-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5852d-108">Syntax</span></span>  
  
```  
  
integer_expression1 ^ integer_expression2  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="5852d-109">Argomenti</span><span class="sxs-lookup"><span data-stu-id="5852d-109">Arguments</span></span>  
 <span data-ttu-id="5852d-110">*integer_expression1, integer_expression2*</span><span class="sxs-lookup"><span data-stu-id="5852d-110">*integer_expression1, integer_expression2*</span></span>  
 <span data-ttu-id="5852d-111">Qualsiasi espressione valida con tipo di dati Integer con o senza segno.</span><span class="sxs-lookup"><span data-stu-id="5852d-111">Is any valid expression of a signed or unsigned integer data type.</span></span> <span data-ttu-id="5852d-112">Per altre informazioni, vedere [Tipi di dati di Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="5852d-112">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="5852d-113">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="5852d-113">Result Types</span></span>  
 <span data-ttu-id="5852d-114">Dipendenti dai tipi di dati dei due argomenti.</span><span class="sxs-lookup"><span data-stu-id="5852d-114">Determined by data types of the two arguments.</span></span> <span data-ttu-id="5852d-115">Per altre informazioni, vedere [Tipi di dati nelle espressioni di Integration Services](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="5852d-115">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5852d-116">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="5852d-116">Remarks</span></span>  
 <span data-ttu-id="5852d-117">Se una delle due condizioni è Null, il risultato dell'espressione sarà Null.</span><span class="sxs-lookup"><span data-stu-id="5852d-117">If either condition is null, the expression result is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="5852d-118">Esempi di espressione</span><span class="sxs-lookup"><span data-stu-id="5852d-118">Expression Examples</span></span>  
 <span data-ttu-id="5852d-119">In questo esempio viene eseguita un'operazione con OR esclusivo bit per bit tra le variabili **NumberA** e **NumberB**.</span><span class="sxs-lookup"><span data-stu-id="5852d-119">This example performs a bitwise exclusive OR operation between variables **NumberA** and **NumberB**.</span></span> <span data-ttu-id="5852d-120">**NumberA** contiene 3 (00000011) e **NumberB** contiene 7 (00000111).</span><span class="sxs-lookup"><span data-stu-id="5852d-120">**NumberA** contains 3 (00000011) and **NumberB** contains 7 (00000111).</span></span>  
  
```  
@NumberA ^ @NumberB  
```  
  
 <span data-ttu-id="5852d-121">L'espressione restituisce 4 (00000100).</span><span class="sxs-lookup"><span data-stu-id="5852d-121">The expression evaluates to 4 (00000100).</span></span>  
  
 <span data-ttu-id="5852d-122">00000011</span><span class="sxs-lookup"><span data-stu-id="5852d-122">00000011</span></span>  
  
 <span data-ttu-id="5852d-123">00000111</span><span class="sxs-lookup"><span data-stu-id="5852d-123">00000111</span></span>  
  
 ----------\-  
  
 <span data-ttu-id="5852d-124">00000100</span><span class="sxs-lookup"><span data-stu-id="5852d-124">00000100</span></span>  
  
 <span data-ttu-id="5852d-125">In questo esempio viene eseguita un'operazione con OR esclusivo bit per bit tra le colonne **ReorderPoint** e **SafetyStockLevel** .</span><span class="sxs-lookup"><span data-stu-id="5852d-125">This example performs a bitwise exclusive OR operation between the **ReorderPoint** and **SafetyStockLevel** columns.</span></span>  
  
```  
ReorderPoint ^ SafetyStockLevel  
```  
  
 <span data-ttu-id="5852d-126">Se **ReorderPoint** ha valore 10 e **SafetyStockLevel** ha valore 8, l'espressione restituirà 2 (00000010).</span><span class="sxs-lookup"><span data-stu-id="5852d-126">If **ReorderPoint** is 10 and **SafetyStockLevel** is 8, the expression evaluates to 2 (00000010).</span></span>  
  
 <span data-ttu-id="5852d-127">00001010</span><span class="sxs-lookup"><span data-stu-id="5852d-127">00001010</span></span>  
  
 <span data-ttu-id="5852d-128">00001000</span><span class="sxs-lookup"><span data-stu-id="5852d-128">00001000</span></span>  
  
 ----------\-  
  
 <span data-ttu-id="5852d-129">00000010</span><span class="sxs-lookup"><span data-stu-id="5852d-129">00000010</span></span>  
  
 <span data-ttu-id="5852d-130">In questo esempio viene eseguita un'operazione con OR esclusivo bit per bit tra due valori integer.</span><span class="sxs-lookup"><span data-stu-id="5852d-130">This example performs a bitwise exclusive OR operation between two integers.</span></span>  
  
```  
3 ^ 5   
```  
  
 <span data-ttu-id="5852d-131">L'espressione restituisce 6 (00000110).</span><span class="sxs-lookup"><span data-stu-id="5852d-131">The expression evaluates to 6 (00000110).</span></span>  
  
 <span data-ttu-id="5852d-132">00000011</span><span class="sxs-lookup"><span data-stu-id="5852d-132">00000011</span></span>  
  
 <span data-ttu-id="5852d-133">00000101</span><span class="sxs-lookup"><span data-stu-id="5852d-133">00000101</span></span>  
  
 ----------\-  
  
 <span data-ttu-id="5852d-134">00000110</span><span class="sxs-lookup"><span data-stu-id="5852d-134">00000110</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5852d-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5852d-135">See Also</span></span>  
 <span data-ttu-id="5852d-136">[&#124;&#124; &#40;OR logico&#41; &#40;espressione SSIS&#41;](logical-or-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="5852d-136">[&#124;&#124; &#40;Logical OR&#41; &#40;SSIS Expression&#41;](logical-or-ssis-expression.md) </span></span>  
 <span data-ttu-id="5852d-137">[&#124; &#40;OR inclusivo bit per bit&#41; &#40;espressione SSIS&#41;](bitwise-inclusive-or-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="5852d-137">[&#124; &#40;Bitwise Inclusive OR&#41; &#40;SSIS Expression&#41;](bitwise-inclusive-or-ssis-expression.md) </span></span>  
 <span data-ttu-id="5852d-138">[Precedenza e associatività degli operatori](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="5852d-138">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="5852d-139">Operatori &#40;espressione SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="5852d-139">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
