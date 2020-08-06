---
title: (Modulo) (espressione SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- '% (modulo operator)'
- remainder of division operation
- modulo operator (%)
ms.assetid: e2920821-2f5b-4c76-8db8-8b9eddf4606f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2e23152fca9c9f2c7c3ac11490a56b03d1a1f9dd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627905"
---
# <a name="modulo-ssis-expression"></a><span data-ttu-id="301f3-102">(Modulo) (espressione SSIS)</span><span class="sxs-lookup"><span data-stu-id="301f3-102">(Modulo) (SSIS Expression)</span></span>
  <span data-ttu-id="301f3-103">Viene restituito il resto Integer dopo aver diviso la prima espressione numerica per la seconda.</span><span class="sxs-lookup"><span data-stu-id="301f3-103">Provides the integer remainder after dividing the first numeric expression by the second one.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="301f3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="301f3-104">Syntax</span></span>  
  
```  
  
dividend % divisor  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="301f3-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="301f3-105">Arguments</span></span>  
 <span data-ttu-id="301f3-106">*dividend*</span><span class="sxs-lookup"><span data-stu-id="301f3-106">*dividend*</span></span>  
 <span data-ttu-id="301f3-107">Espressione numerica da dividere.</span><span class="sxs-lookup"><span data-stu-id="301f3-107">Is the numeric expression to divide.</span></span> <span data-ttu-id="301f3-108">*dividend* può essere qualsiasi espressione numerica valida.</span><span class="sxs-lookup"><span data-stu-id="301f3-108">*dividend* can be any valid numeric expression.</span></span> <span data-ttu-id="301f3-109">Per altre informazioni, vedere [Tipi di dati di Integration Services](../data-flow/integration-services-data-types.md)</span><span class="sxs-lookup"><span data-stu-id="301f3-109">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md)</span></span>  
  
 <span data-ttu-id="301f3-110">*divisor*</span><span class="sxs-lookup"><span data-stu-id="301f3-110">*divisor*</span></span>  
 <span data-ttu-id="301f3-111">Espressione numerica per cui dividere il dividendo.</span><span class="sxs-lookup"><span data-stu-id="301f3-111">Is the numeric expression to divide the dividend by.</span></span> <span data-ttu-id="301f3-112">*divisor* può essere qualsiasi espressione numerica valida, tranne zero.</span><span class="sxs-lookup"><span data-stu-id="301f3-112">*divisor* can be any valid numeric expression except zero.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="301f3-113">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="301f3-113">Result Types</span></span>  
 <span data-ttu-id="301f3-114">Dipendenti dai tipi di dati dei due argomenti.</span><span class="sxs-lookup"><span data-stu-id="301f3-114">Determined by data types of the two arguments.</span></span> <span data-ttu-id="301f3-115">Per altre informazioni, vedere [Tipi di dati nelle espressioni di Integration Services](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="301f3-115">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="301f3-116">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="301f3-116">Remarks</span></span>  
 <span data-ttu-id="301f3-117">Entrambe le espressioni devono restituire tipi di dati Integer con o senza segno.</span><span class="sxs-lookup"><span data-stu-id="301f3-117">Both expressions must evaluate to signed or unsigned integer data types.</span></span>  
  
 <span data-ttu-id="301f3-118">Se uno degli operandi è Null, il risultato sarà Null.</span><span class="sxs-lookup"><span data-stu-id="301f3-118">If either operand is null, the result is null.</span></span>  
  
 <span data-ttu-id="301f3-119">Non è consentito il calcolo del modulo di una divisione per zero.</span><span class="sxs-lookup"><span data-stu-id="301f3-119">Modulo zero is not legal.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="301f3-120">Esempi di espressione</span><span class="sxs-lookup"><span data-stu-id="301f3-120">Expression Examples</span></span>  
 <span data-ttu-id="301f3-121">In questo esempio viene calcolato il modulo di una divisione tra due valori letterali numerici.</span><span class="sxs-lookup"><span data-stu-id="301f3-121">This example computes the modulus from two numeric literals.</span></span> <span data-ttu-id="301f3-122">Il risultato è 3.</span><span class="sxs-lookup"><span data-stu-id="301f3-122">The result is 3.</span></span>  
  
```  
42 % 13  
```  
  
 <span data-ttu-id="301f3-123">In questo esempio viene calcolato il modulo della divisione della colonna **SalesQuota** per un valore letterale numerico.</span><span class="sxs-lookup"><span data-stu-id="301f3-123">This example computes the modulus from the **SalesQuota** column and a numeric literal.</span></span>  
  
```  
SalesQuota % 12  
```  
  
 <span data-ttu-id="301f3-124">In questo esempio viene calcolato il modulo di una divisione tra le due variabili numeriche **Sales$** e **Month**.</span><span class="sxs-lookup"><span data-stu-id="301f3-124">This example computes the modulus from two numeric variables **Sales$** and **Month**.</span></span> <span data-ttu-id="301f3-125">Poiché il nome include il carattere $, la variabile **Sales$** deve essere racchiusa tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="301f3-125">The variable **Sales$** must be enclosed in brackets because the name includes the $ character.</span></span> <span data-ttu-id="301f3-126">Per altre informazioni, vedere [Identificatori &#40;SSIS&#41;](identifiers-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="301f3-126">For more information, see [Identifiers &#40;SSIS&#41;](identifiers-ssis.md).</span></span>  
  
```  
@[Sales$] % @Month  
```  
  
 <span data-ttu-id="301f3-127">In questo esempio l'operatore Modulo viene usato per determinare se il valore della variabile **Value** è pari o dispari, quindi viene usato l'operatore condizionale per restituire una stringa che descrive il risultato.</span><span class="sxs-lookup"><span data-stu-id="301f3-127">This example uses the modulo operator to determine if the value of the **Value** variable is even or odd, and uses the conditional operator to return a string that describes the result.</span></span> <span data-ttu-id="301f3-128">Per altre informazioni, vedere [? : &#40;condizionale&#41; &#40;espressione SSIS&#41;](conditional-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="301f3-128">For more information, see [? : &#40;Conditional&#41; &#40;SSIS Expression&#41;](conditional-ssis-expression.md).</span></span>  
  
```  
@Value % 2 == 0? "even":"odd"  
```  
  
## <a name="see-also"></a><span data-ttu-id="301f3-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="301f3-129">See Also</span></span>  
 <span data-ttu-id="301f3-130">[Precedenza e associatività degli operatori](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="301f3-130">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="301f3-131">Operatori &#40;espressione SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="301f3-131">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
