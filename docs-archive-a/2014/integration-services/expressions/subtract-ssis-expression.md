---
title: '- (sottrazione) (espressione SSIS) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- '- (subtract)'
- subtract operator (-)
ms.assetid: b48da086-37dd-460a-8a4b-912f52c9b158
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 79c47689baf47c33952c6b208ac622e9920d05fe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716455"
---
# <a name="--subtract-ssis-expression"></a><span data-ttu-id="3c674-102">- (sottrazione) (espressione SSIS)</span><span class="sxs-lookup"><span data-stu-id="3c674-102">- (Subtract) (SSIS Expression)</span></span>
  <span data-ttu-id="3c674-103">Viene sottratta la seconda espressione numerica dalla prima.</span><span class="sxs-lookup"><span data-stu-id="3c674-103">Subtracts the second numeric expression from the first one.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c674-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3c674-104">Syntax</span></span>  
  
```  
  
numeric_expression1 - numeric_expression2  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="3c674-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="3c674-105">Arguments</span></span>  
 <span data-ttu-id="3c674-106">*numeric_expression1, numeric_expression2*</span><span class="sxs-lookup"><span data-stu-id="3c674-106">*numeric_expression1, numeric_expression2*</span></span>  
 <span data-ttu-id="3c674-107">Espressione valida con tipo di dati numeric.</span><span class="sxs-lookup"><span data-stu-id="3c674-107">Is any valid expression of a numeric data type.</span></span> <span data-ttu-id="3c674-108">Per altre informazioni, vedere [Tipi di dati di Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="3c674-108">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="3c674-109">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="3c674-109">Result Types</span></span>  
 <span data-ttu-id="3c674-110">Dipendenti dai tipi di dati dei due argomenti.</span><span class="sxs-lookup"><span data-stu-id="3c674-110">Determined by the data types of the two arguments.</span></span> <span data-ttu-id="3c674-111">Per altre informazioni, vedere [Tipi di dati nelle espressioni di Integration Services](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="3c674-111">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3c674-112">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="3c674-112">Remarks</span></span>  
 <span data-ttu-id="3c674-113">Racchiudere l'espressione con il meno unario tra parentesi per assicurarsi che l'espressione venga valutata nell'ordine corretto</span><span class="sxs-lookup"><span data-stu-id="3c674-113">Enclose the minus unary expression in parenthesis to ensure that the expression is evaluated in the correct order</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3c674-114">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="3c674-114">Remarks</span></span>  
 <span data-ttu-id="3c674-115">Se uno degli operandi è Null, il risultato sarà Null.</span><span class="sxs-lookup"><span data-stu-id="3c674-115">If either operand is null, the result is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="3c674-116">Esempi di espressione</span><span class="sxs-lookup"><span data-stu-id="3c674-116">Expression Examples</span></span>  
 <span data-ttu-id="3c674-117">In questo esempio viene eseguita una sottrazione tra alcuni valori letterali numerici.</span><span class="sxs-lookup"><span data-stu-id="3c674-117">This example subtracts numeric literals.</span></span>  
  
```  
5 - 6.09  
```  
  
 <span data-ttu-id="3c674-118">In questo esempio il valore nella colonna **StandardCost** viene sottratto dal valore nella colonna **ListPrice** .</span><span class="sxs-lookup"><span data-stu-id="3c674-118">This example subtracts the value in the **StandardCost** column from the value in the **ListPrice** column.</span></span>  
  
```  
ListPrice - StandardCost  
```  
  
 <span data-ttu-id="3c674-119">In questo esempio un valore calcolato viene sottratto dalla colonna **ListPrice** .</span><span class="sxs-lookup"><span data-stu-id="3c674-119">This example subtracts a calculated value from the **ListPrice** column.</span></span> <span data-ttu-id="3c674-120">Poiché il nome include il carattere %, la variabile **Discount%** deve essere racchiusa tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="3c674-120">The variable **Discount%** must be enclosed in brackets because the name includes the % character.</span></span> <span data-ttu-id="3c674-121">Per altre informazioni, vedere [Identificatori &#40;SSIS&#41;](identifiers-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="3c674-121">For more information, see [Identifiers &#40;SSIS&#41;](identifiers-ssis.md).</span></span>  
  
```  
ListPrice - (ListPrice * @[Discount%])  
```  
  
## <a name="see-also"></a><span data-ttu-id="3c674-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3c674-122">See Also</span></span>  
 <span data-ttu-id="3c674-123">[Precedenza e associatività degli operatori](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="3c674-123">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="3c674-124">Operatori &#40;espressione SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="3c674-124">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
