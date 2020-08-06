---
title: '&amp; (AND bit per bit) (espressione SSIS) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- AND, bitwise AND
- '& (bitwise AND)'
- bitwise AND (&)
ms.assetid: 06d2958e-66a5-44d8-8bc4-56209ebe1ff2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: fbf3c8ffcef079e25c82478947bc3b92a6b4be93
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635182"
---
# <a name="amp-bitwise-and-ssis-expression"></a><span data-ttu-id="15c9d-102">&amp; (AND bit per bit) (espressione SSIS)</span><span class="sxs-lookup"><span data-stu-id="15c9d-102">&amp; (Bitwise AND) (SSIS Expression)</span></span>
  <span data-ttu-id="15c9d-103">Esegue un'operazione con AND bit per bit tra due valori integer.</span><span class="sxs-lookup"><span data-stu-id="15c9d-103">Performs a bitwise AND operation of two integer values.</span></span> <span data-ttu-id="15c9d-104">Confronta ogni bit del primo operando con il bit corrispondente del secondo operando.</span><span class="sxs-lookup"><span data-stu-id="15c9d-104">It compares each bit of its first operand to the corresponding bit of its second operand.</span></span> <span data-ttu-id="15c9d-105">Se entrambi i bit hanno valore 1, il bit del risultato verrà impostato su 1,</span><span class="sxs-lookup"><span data-stu-id="15c9d-105">If both bits are 1, the corresponding result bit is set to 1.</span></span> <span data-ttu-id="15c9d-106">altrimenti verrà impostato su 0.</span><span class="sxs-lookup"><span data-stu-id="15c9d-106">Otherwise, the corresponding result bit is set to 0.</span></span>  
  
 <span data-ttu-id="15c9d-107">Entrambe le condizioni devono essere costituite da un intero con segno o da un intero senza segno.</span><span class="sxs-lookup"><span data-stu-id="15c9d-107">Both conditions must be a signed integer type or both conditions must be an unsigned integer type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15c9d-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="15c9d-108">Syntax</span></span>  
  
```  
  
integer_expression1 & integer_expression2  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="15c9d-109">Argomenti</span><span class="sxs-lookup"><span data-stu-id="15c9d-109">Arguments</span></span>  
 <span data-ttu-id="15c9d-110">*integer_expression1, integer_expression2*</span><span class="sxs-lookup"><span data-stu-id="15c9d-110">*integer_expression1, integer_expression2*</span></span>  
 <span data-ttu-id="15c9d-111">Qualsiasi espressione valida con tipo di dati Integer con o senza segno.</span><span class="sxs-lookup"><span data-stu-id="15c9d-111">Is any valid expression of a signed or unsigned integer data type.</span></span> <span data-ttu-id="15c9d-112">Per altre informazioni, vedere [Tipi di dati di Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="15c9d-112">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="15c9d-113">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="15c9d-113">Result Types</span></span>  
 <span data-ttu-id="15c9d-114">Dipendenti dai tipi di dati dei due argomenti.</span><span class="sxs-lookup"><span data-stu-id="15c9d-114">Determined by data types of the two arguments.</span></span> <span data-ttu-id="15c9d-115">Per altre informazioni, vedere [Tipi di dati nelle espressioni di Integration Services](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="15c9d-115">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="15c9d-116">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="15c9d-116">Remarks</span></span>  
 <span data-ttu-id="15c9d-117">Se una delle due condizioni è Null, il risultato dell'espressione sarà Null.</span><span class="sxs-lookup"><span data-stu-id="15c9d-117">If either condition is null, the expression result is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="15c9d-118">Esempi di espressione</span><span class="sxs-lookup"><span data-stu-id="15c9d-118">Expression Examples</span></span>  
 <span data-ttu-id="15c9d-119">In questo esempio viene effettuata un'operazione con AND bit per bit tra le colonne **NumberA** e **NumberB**.</span><span class="sxs-lookup"><span data-stu-id="15c9d-119">This example performs a bitwise AND operation between the columns **NumberA** and **NumberB**.</span></span> <span data-ttu-id="15c9d-120">La colonna**NumberA** contiene 3 (0000011) e la colonna **NumberB** contiene 7 (00000111).</span><span class="sxs-lookup"><span data-stu-id="15c9d-120">**NumberA** contains 3 (0000011) and column **NumberB** contains 7 (00000111).</span></span>  
  
```  
NumberA & NumberB  
```  
  
 <span data-ttu-id="15c9d-121">L'espressione restituisce 3 (00000011).</span><span class="sxs-lookup"><span data-stu-id="15c9d-121">The expression evaluates to 3 (00000011).</span></span>  
  
 <span data-ttu-id="15c9d-122">00000011</span><span class="sxs-lookup"><span data-stu-id="15c9d-122">00000011</span></span>  
  
 <span data-ttu-id="15c9d-123">00000111</span><span class="sxs-lookup"><span data-stu-id="15c9d-123">00000111</span></span>  
  
 ----------\-  
  
 <span data-ttu-id="15c9d-124">00000011</span><span class="sxs-lookup"><span data-stu-id="15c9d-124">00000011</span></span>  
  
 <span data-ttu-id="15c9d-125">In questo esempio viene eseguita un'operazione con AND bit per bit tra le colonne **ReorderPoint** e **SafetyStockLevel** .</span><span class="sxs-lookup"><span data-stu-id="15c9d-125">This example performs a bitwise AND operation between the **ReorderPoint** and **SafetyStockLevel** columns.</span></span>  
  
```  
ReorderPoint & SafetyStockLevel  
```  
  
 <span data-ttu-id="15c9d-126">Se **ReorderPoint** ha valore 10 e **SafetyStockLevel** ha valore 8, l'espressione restituirà 8 (00001000).</span><span class="sxs-lookup"><span data-stu-id="15c9d-126">If **ReorderPoint** is 10 and **SafetyStockLevel** is 8, the expression evaluates to 8 (00001000).</span></span>  
  
 <span data-ttu-id="15c9d-127">00001010</span><span class="sxs-lookup"><span data-stu-id="15c9d-127">00001010</span></span>  
  
 <span data-ttu-id="15c9d-128">00001000</span><span class="sxs-lookup"><span data-stu-id="15c9d-128">00001000</span></span>  
  
 ----------\-  
  
 <span data-ttu-id="15c9d-129">00001000</span><span class="sxs-lookup"><span data-stu-id="15c9d-129">00001000</span></span>  
  
 <span data-ttu-id="15c9d-130">In questo esempio viene eseguita un'operazione con AND bit per bit tra due valori integer.</span><span class="sxs-lookup"><span data-stu-id="15c9d-130">This example performs a bitwise AND operation between two integers.</span></span>  
  
```  
3 & 5   
```  
  
 <span data-ttu-id="15c9d-131">L'espressione restituisce 1 (00000001).</span><span class="sxs-lookup"><span data-stu-id="15c9d-131">The expression evaluates to 1(00000001).</span></span>  
  
 <span data-ttu-id="15c9d-132">00000011</span><span class="sxs-lookup"><span data-stu-id="15c9d-132">00000011</span></span>  
  
 <span data-ttu-id="15c9d-133">00000101</span><span class="sxs-lookup"><span data-stu-id="15c9d-133">00000101</span></span>  
  
 ----------\-  
  
 <span data-ttu-id="15c9d-134">00000001</span><span class="sxs-lookup"><span data-stu-id="15c9d-134">00000001</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15c9d-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="15c9d-135">See Also</span></span>  
 <span data-ttu-id="15c9d-136">[&& &#40;AND logico&#41; &#40;espressione SSIS&#41;](logical-and-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="15c9d-136">[&& &#40;Logical AND&#41; &#40;SSIS Expression&#41;](logical-and-ssis-expression.md) </span></span>  
 <span data-ttu-id="15c9d-137">[Precedenza e associatività degli operatori](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="15c9d-137">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="15c9d-138">Operatori &#40;espressione SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="15c9d-138">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
