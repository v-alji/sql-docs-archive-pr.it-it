---
title: '| (OR inclusivo bit per bit) (espressione SSIS) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- '| (bitwise inclusive OR)'
- bitwise inclusive OR (|)
ms.assetid: 4dce9eb2-3680-4adc-81a3-816ea52cef49
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 73d64886b433ffe5b4e06dc4870bbca06b2a53dc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635176"
---
# <a name="-bitwise-inclusive-or-ssis-expression"></a><span data-ttu-id="cbba3-102">| (OR inclusivo bit per bit) (espressione SSIS)</span><span class="sxs-lookup"><span data-stu-id="cbba3-102">| (Bitwise Inclusive OR) (SSIS Expression)</span></span>
  <span data-ttu-id="cbba3-103">Viene eseguita un'operazione con OR bit per bit su due valori integer.</span><span class="sxs-lookup"><span data-stu-id="cbba3-103">Performs a bitwise OR operation of two integer values.</span></span> <span data-ttu-id="cbba3-104">Confronta ogni bit del primo operando con il bit corrispondente del secondo operando.</span><span class="sxs-lookup"><span data-stu-id="cbba3-104">It compares each bit of its first operand to the corresponding bit of its second operand.</span></span> <span data-ttu-id="cbba3-105">Se uno dei due bit ha valore 1, il bit del risultato verrà impostato su 1,</span><span class="sxs-lookup"><span data-stu-id="cbba3-105">If either bit is 1, the corresponding result bit is set to 1.</span></span> <span data-ttu-id="cbba3-106">altrimenti verrà impostato su 0 (0).</span><span class="sxs-lookup"><span data-stu-id="cbba3-106">Otherwise, the corresponding result bit is set to zero (0).</span></span>  
  
 <span data-ttu-id="cbba3-107">Entrambe le condizioni devono essere costituite da un valore con tipo di dati Integer con segno o da un valore con tipo di dati Integer senza segno.</span><span class="sxs-lookup"><span data-stu-id="cbba3-107">Both conditions must be a signed integer data type or both conditions must be an unsigned integer data type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cbba3-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cbba3-108">Syntax</span></span>  
  
```  
  
integer_expression1 | integer_expression2  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="cbba3-109">Argomenti</span><span class="sxs-lookup"><span data-stu-id="cbba3-109">Arguments</span></span>  
 <span data-ttu-id="cbba3-110">*integer_expression1, integer_ expression2*</span><span class="sxs-lookup"><span data-stu-id="cbba3-110">*integer_expression1 ,integer_ expression2*</span></span>  
 <span data-ttu-id="cbba3-111">Qualsiasi espressione valida con tipo di dati Integer con o senza segno.</span><span class="sxs-lookup"><span data-stu-id="cbba3-111">Is any valid expression of a signed or unsigned integer data type.</span></span> <span data-ttu-id="cbba3-112">Per altre informazioni, vedere [Tipi di dati di Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="cbba3-112">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="cbba3-113">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="cbba3-113">Result Types</span></span>  
 <span data-ttu-id="cbba3-114">Dipendenti dai tipi di dati dei due argomenti.</span><span class="sxs-lookup"><span data-stu-id="cbba3-114">Determined by data types of the two arguments.</span></span> <span data-ttu-id="cbba3-115">Per altre informazioni, vedere [Tipi di dati nelle espressioni di Integration Services](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="cbba3-115">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cbba3-116">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="cbba3-116">Remarks</span></span>  
 <span data-ttu-id="cbba3-117">Se una delle due condizioni è Null, il risultato dell'espressione sarà Null.</span><span class="sxs-lookup"><span data-stu-id="cbba3-117">If either condition is null, the expression result is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="cbba3-118">Esempi di espressione</span><span class="sxs-lookup"><span data-stu-id="cbba3-118">Expression Examples</span></span>  
 <span data-ttu-id="cbba3-119">Questo esempio esegue un'operazione con OR inclusivo bit per bit tra le variabili **NumberA** e **NumberB**.</span><span class="sxs-lookup"><span data-stu-id="cbba3-119">This example performs a bitwise inclusive OR operation between the variables **NumberA** and **NumberB**.</span></span> <span data-ttu-id="cbba3-120">**NumberA** contiene 3 (00000011) e **NumberB** contiene 9 (00001001).</span><span class="sxs-lookup"><span data-stu-id="cbba3-120">**NumberA** contains 3 (00000011) and **NumberB** contains 9 (00001001).</span></span>  
  
```  
@NumberA | @NumberB  
```  
  
 <span data-ttu-id="cbba3-121">L'espressione restituisce 11 (00001011).</span><span class="sxs-lookup"><span data-stu-id="cbba3-121">The expression evaluates to 11 (00001011).</span></span>  
  
 <span data-ttu-id="cbba3-122">00000011</span><span class="sxs-lookup"><span data-stu-id="cbba3-122">00000011</span></span>  
  
 <span data-ttu-id="cbba3-123">00001001</span><span class="sxs-lookup"><span data-stu-id="cbba3-123">00001001</span></span>  
  
 ----------\-  
  
 <span data-ttu-id="cbba3-124">00001011</span><span class="sxs-lookup"><span data-stu-id="cbba3-124">00001011</span></span>  
  
 <span data-ttu-id="cbba3-125">Questo esempio esegue un'operazione con OR inclusivo bit per bit tra le colonne **ReorderPoint** e **SafetyStockLevel** .</span><span class="sxs-lookup"><span data-stu-id="cbba3-125">This example performs a bitwise inclusive OR operation between the **ReorderPoint** and **SafetyStockLevel** columns.</span></span>  
  
```  
ReorderPoint | SafetyStockLevel  
```  
  
 <span data-ttu-id="cbba3-126">Se **ReorderPoint** ha valore 10 e **SafetyStockLevel** ha valore 8, l'espressione restituirà 10 (00001010).</span><span class="sxs-lookup"><span data-stu-id="cbba3-126">If **ReorderPoint** is 10 and **SafetyStockLevel** is 8, the expression evaluates to 10 (00001010).</span></span>  
  
 <span data-ttu-id="cbba3-127">00001010</span><span class="sxs-lookup"><span data-stu-id="cbba3-127">00001010</span></span>  
  
 <span data-ttu-id="cbba3-128">00001000</span><span class="sxs-lookup"><span data-stu-id="cbba3-128">00001000</span></span>  
  
 ----------\-  
  
 <span data-ttu-id="cbba3-129">00001010</span><span class="sxs-lookup"><span data-stu-id="cbba3-129">00001010</span></span>  
  
 <span data-ttu-id="cbba3-130">In questo esempio viene eseguita un'operazione con OR inclusivo bit per bit tra due valori integer.</span><span class="sxs-lookup"><span data-stu-id="cbba3-130">This example performs a bitwise inclusive OR operation between two integers.</span></span>  
  
```  
3 | 5   
```  
  
 <span data-ttu-id="cbba3-131">L'espressione restituisce 7 (00000111).</span><span class="sxs-lookup"><span data-stu-id="cbba3-131">The expression evaluates to 7 (00000111).</span></span>  
  
 <span data-ttu-id="cbba3-132">00000011</span><span class="sxs-lookup"><span data-stu-id="cbba3-132">00000011</span></span>  
  
 <span data-ttu-id="cbba3-133">00000101</span><span class="sxs-lookup"><span data-stu-id="cbba3-133">00000101</span></span>  
  
 ----------\-  
  
 <span data-ttu-id="cbba3-134">00000111</span><span class="sxs-lookup"><span data-stu-id="cbba3-134">00000111</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbba3-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cbba3-135">See Also</span></span>  
 <span data-ttu-id="cbba3-136">[&#124;&#124; &#40;OR logico&#41; &#40;espressione SSIS&#41;](logical-or-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="cbba3-136">[&#124;&#124; &#40;Logical OR&#41; &#40;SSIS Expression&#41;](logical-or-ssis-expression.md) </span></span>  
 <span data-ttu-id="cbba3-137">[^ &#40;OR esclusivo bit per bit&#41; &#40;Espressione SSIS&#41;](bitwise-exclusive-or-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="cbba3-137">[^ &#40;Bitwise Exclusive OR&#41; &#40;SSIS Expression&#41;](bitwise-exclusive-or-ssis-expression.md) </span></span>  
 <span data-ttu-id="cbba3-138">[Precedenza e associatività degli operatori](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="cbba3-138">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="cbba3-139">Operatori &#40;espressione SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="cbba3-139">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
