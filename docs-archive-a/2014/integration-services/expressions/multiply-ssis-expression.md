---
title: '* \* (moltiplicazione) (espressione SSIS)* (moltiplicazione) (espressione SSIS) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- '* (multiply operator)'
- multiply operator (*)
ms.assetid: d457f052-ffbb-4485-833f-f4bed4349b69
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 16d8429a869b60be31a94244a2ce47d515770c6b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627902"
---
# <a name="-multiply-ssis-expression"></a><span data-ttu-id="2a4ec-102">\* (moltiplicazione) (espressione SSIS)</span><span class="sxs-lookup"><span data-stu-id="2a4ec-102">\* (Multiply) (SSIS Expression)</span></span>
  <span data-ttu-id="2a4ec-103">Vengono moltiplicate due espressioni numeriche.</span><span class="sxs-lookup"><span data-stu-id="2a4ec-103">Multiplies two numeric expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a4ec-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2a4ec-104">Syntax</span></span>  
  
```  
  
numeric_expression1 * numeric_expression2  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="2a4ec-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="2a4ec-105">Arguments</span></span>  
 <span data-ttu-id="2a4ec-106">*numeric_expression1, numeric_expression2*</span><span class="sxs-lookup"><span data-stu-id="2a4ec-106">*numeric_expression1, numeric_expression2*</span></span>  
 <span data-ttu-id="2a4ec-107">Espressione valida con tipo di dati numeric.</span><span class="sxs-lookup"><span data-stu-id="2a4ec-107">Is any valid expression of a numeric data type.</span></span> <span data-ttu-id="2a4ec-108">Per altre informazioni, vedere [Tipi di dati di Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="2a4ec-108">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="2a4ec-109">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="2a4ec-109">Result Types</span></span>  
 <span data-ttu-id="2a4ec-110">Dipendenti dai tipi di dati dei due argomenti.</span><span class="sxs-lookup"><span data-stu-id="2a4ec-110">Determined by data types of the two arguments.</span></span> <span data-ttu-id="2a4ec-111">Per altre informazioni, vedere [Tipi di dati nelle espressioni di Integration Services](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="2a4ec-111">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2a4ec-112">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="2a4ec-112">Remarks</span></span>  
 <span data-ttu-id="2a4ec-113">Se uno degli operandi è Null, il risultato sarà Null.</span><span class="sxs-lookup"><span data-stu-id="2a4ec-113">If either operand is null, the result is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="2a4ec-114">Esempi di espressione</span><span class="sxs-lookup"><span data-stu-id="2a4ec-114">Expression Examples</span></span>  
 <span data-ttu-id="2a4ec-115">In questo esempio vengono moltiplicati due valori letterali numerici.</span><span class="sxs-lookup"><span data-stu-id="2a4ec-115">This example multiplies numeric literals.</span></span>  
  
```  
5 * 6.09  
```  
  
 <span data-ttu-id="2a4ec-116">Questo esempio moltiplica i valori nella colonna **ListPrice** per il 10%.</span><span class="sxs-lookup"><span data-stu-id="2a4ec-116">This example multiplies values in the **ListPrice** column by 10 percent.</span></span>  
  
```  
ListPrice * .10  
```  
  
 <span data-ttu-id="2a4ec-117">Questo esempio sottrae il risultato di un'espressione dalla colonna **ListPrice** .</span><span class="sxs-lookup"><span data-stu-id="2a4ec-117">This example subtracts the result of an expression from the **ListPrice** column.</span></span> <span data-ttu-id="2a4ec-118">Poiché il nome include il carattere %, la variabile **Discount%** deve essere racchiusa tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="2a4ec-118">The variable **Discount%** must be enclosed in brackets because the name includes the % character.</span></span> <span data-ttu-id="2a4ec-119">Per altre informazioni, vedere [Identificatori &#40;SSIS&#41;](identifiers-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="2a4ec-119">For more information, see [Identifiers &#40;SSIS&#41;](identifiers-ssis.md).</span></span>  
  
```  
ListPrice - (ListPrice * @[Discount%])  
```  
  
## <a name="see-also"></a><span data-ttu-id="2a4ec-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2a4ec-120">See Also</span></span>  
 <span data-ttu-id="2a4ec-121">[Precedenza e associatività degli operatori](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="2a4ec-121">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="2a4ec-122">Operatori &#40;espressione SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="2a4ec-122">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
