---
title: ~ (NOT bit per bit) (espressione SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- bitwise NOT (~)
- ~ (bitwise NOT)
ms.assetid: e4413ddd-0d0e-40c3-9c76-b5ce323218ec
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 75745a0650c1744064f2a671659879e11464514e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635175"
---
# <a name="-bitwise-not-ssis-expression"></a><span data-ttu-id="4f546-102">~ (NOT bit per bit) (espressione SSIS)</span><span class="sxs-lookup"><span data-stu-id="4f546-102">~ (Bitwise Not) (SSIS Expression)</span></span>
  <span data-ttu-id="4f546-103">Viene eseguita una negazione bit per bit di un valore integer.</span><span class="sxs-lookup"><span data-stu-id="4f546-103">Performs a bitwise negation of an integer.</span></span> <span data-ttu-id="4f546-104">Questo operatore può essere applicato a tipi di dati integer con e senza segno.</span><span class="sxs-lookup"><span data-stu-id="4f546-104">This operator can be applied to signed and unsigned integer data types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f546-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4f546-105">Syntax</span></span>  
  
```  
  
~integer_expression  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="4f546-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="4f546-106">Arguments</span></span>  
 <span data-ttu-id="4f546-107">*integer_expression*</span><span class="sxs-lookup"><span data-stu-id="4f546-107">*integer_expression*</span></span>  
 <span data-ttu-id="4f546-108">Espressione valida con qualsiasi tipo di dati integer.</span><span class="sxs-lookup"><span data-stu-id="4f546-108">Is any valid expression of an integer data type.</span></span> <span data-ttu-id="4f546-109">*integer*_*expression* è un numero intero trasformato in un numero binario per l'operazione bit per bit.</span><span class="sxs-lookup"><span data-stu-id="4f546-109">*integer*_*expression* is an integer that is transformed into a binary number for the bitwise operation.</span></span> <span data-ttu-id="4f546-110">Per altre informazioni, vedere [Tipi di dati di Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="4f546-110">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="4f546-111">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="4f546-111">Result Types</span></span>  
 <span data-ttu-id="4f546-112">Restituisce il tipo di dati di *integer_expression.*</span><span class="sxs-lookup"><span data-stu-id="4f546-112">Returns the data type of *integer_expression.*</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4f546-113">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="4f546-113">Remarks</span></span>  
 <span data-ttu-id="4f546-114">nessuno</span><span class="sxs-lookup"><span data-stu-id="4f546-114">None</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="4f546-115">Esempi di espressione</span><span class="sxs-lookup"><span data-stu-id="4f546-115">Expression Examples</span></span>  
 <span data-ttu-id="4f546-116">In questo esempio viene applicato l'operatore ~ (NOT) bit per bit al numero 170 (0000 0000 1010 1010).</span><span class="sxs-lookup"><span data-stu-id="4f546-116">This example performs a bitwise ~ (NOT) operation on the number 170 (0000 0000 1010 1010).</span></span> <span data-ttu-id="4f546-117">Il numero è un valore integer con segno.</span><span class="sxs-lookup"><span data-stu-id="4f546-117">The number is a signed integer.</span></span>  
  
```  
  
~ 170  
```  
  
 <span data-ttu-id="4f546-118">L'espressione restituisce -170 (1111111101010101).</span><span class="sxs-lookup"><span data-stu-id="4f546-118">The expression evaluates to -170 (1111111101010101).</span></span>  
  
 <span data-ttu-id="4f546-119">0000000010101010</span><span class="sxs-lookup"><span data-stu-id="4f546-119">0000000010101010</span></span>  
  
 ---------------------\-  
  
 <span data-ttu-id="4f546-120">1111111101010101</span><span class="sxs-lookup"><span data-stu-id="4f546-120">1111111101010101</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f546-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4f546-121">See Also</span></span>  
 <span data-ttu-id="4f546-122">[Precedenza e associatività degli operatori](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="4f546-122">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="4f546-123">Operatori &#40;espressione SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="4f546-123">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
