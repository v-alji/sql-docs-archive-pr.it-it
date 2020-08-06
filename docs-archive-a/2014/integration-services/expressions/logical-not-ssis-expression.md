---
title: '! (Not logico) (espressione SSIS) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- logical Not (!)
- '! (logical Not)'
ms.assetid: d5c4d1e1-7be4-4d25-bcd9-5b6ddb53b3b3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1bbf313930575e864f1556952425567fca96db15
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627907"
---
# <a name="-logical-not-ssis-expression"></a><span data-ttu-id="f10a3-103">!</span><span class="sxs-lookup"><span data-stu-id="f10a3-103">!</span></span> <span data-ttu-id="f10a3-104">(Not logico) (espressione SSIS)</span><span class="sxs-lookup"><span data-stu-id="f10a3-104">(Logical Not) (SSIS Expression)</span></span>
  <span data-ttu-id="f10a3-105">NOT logico di un operando booleano.</span><span class="sxs-lookup"><span data-stu-id="f10a3-105">Negates a Boolean operand.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f10a3-106">L'operatore !</span><span class="sxs-lookup"><span data-stu-id="f10a3-106">The !</span></span> <span data-ttu-id="f10a3-107">non può essere utilizzato in combinazione con altri operatori.</span><span class="sxs-lookup"><span data-stu-id="f10a3-107">operator cannot be used in conjunction with other operators.</span></span> <span data-ttu-id="f10a3-108">Non è ad esempio possibile combinare gli operatori !</span><span class="sxs-lookup"><span data-stu-id="f10a3-108">For example, you cannot combine the !</span></span> <span data-ttu-id="f10a3-109">e > in modo da formare l'operatore !></span><span class="sxs-lookup"><span data-stu-id="f10a3-109">and the > operators into the !>.</span></span> <span data-ttu-id="f10a3-110">.</span><span class="sxs-lookup"><span data-stu-id="f10a3-110">operator.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f10a3-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f10a3-111">Syntax</span></span>  
  
```  
  
!boolean_expression  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="f10a3-112">Argomenti</span><span class="sxs-lookup"><span data-stu-id="f10a3-112">Arguments</span></span>  
 <span data-ttu-id="f10a3-113">*boolean_expression*</span><span class="sxs-lookup"><span data-stu-id="f10a3-113">*boolean_expression*</span></span>  
 <span data-ttu-id="f10a3-114">Qualsiasi espressione valida che restituisce un valore booleano.</span><span class="sxs-lookup"><span data-stu-id="f10a3-114">Is any valid expression that evaluates to a Boolean.</span></span> <span data-ttu-id="f10a3-115">Per altre informazioni, vedere [Tipi di dati di Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="f10a3-115">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="f10a3-116">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="f10a3-116">Result Types</span></span>  
 <span data-ttu-id="f10a3-117">DT_BOOL</span><span class="sxs-lookup"><span data-stu-id="f10a3-117">DT_BOOL</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f10a3-118">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="f10a3-118">Remarks</span></span>  
 <span data-ttu-id="f10a3-119">Il risultato dell'operazione ! è illustrato nella tabella seguente</span><span class="sxs-lookup"><span data-stu-id="f10a3-119">The following table shows the result of the !</span></span> <span data-ttu-id="f10a3-120">.</span><span class="sxs-lookup"><span data-stu-id="f10a3-120">operation.</span></span>  
  
|<span data-ttu-id="f10a3-121">Espressione booleana originale</span><span class="sxs-lookup"><span data-stu-id="f10a3-121">Original Boolean expression</span></span>|<span data-ttu-id="f10a3-122">Dopo l'applicazione dell'operatore !</span><span class="sxs-lookup"><span data-stu-id="f10a3-122">After applying the !</span></span> <span data-ttu-id="f10a3-123">operator</span><span class="sxs-lookup"><span data-stu-id="f10a3-123">operator</span></span>|  
|---------------------------------|------------------------------------|  
|<span data-ttu-id="f10a3-124">TRUE</span><span class="sxs-lookup"><span data-stu-id="f10a3-124">TRUE</span></span>|<span data-ttu-id="f10a3-125">FALSE</span><span class="sxs-lookup"><span data-stu-id="f10a3-125">FALSE</span></span>|  
|<span data-ttu-id="f10a3-126">NULL</span><span class="sxs-lookup"><span data-stu-id="f10a3-126">NULL</span></span>|<span data-ttu-id="f10a3-127">NULL</span><span class="sxs-lookup"><span data-stu-id="f10a3-127">NULL</span></span>|  
|<span data-ttu-id="f10a3-128">FALSE</span><span class="sxs-lookup"><span data-stu-id="f10a3-128">FALSE</span></span>|<span data-ttu-id="f10a3-129">TRUE</span><span class="sxs-lookup"><span data-stu-id="f10a3-129">TRUE</span></span>|  
  
## <a name="expression-examples"></a><span data-ttu-id="f10a3-130">Esempi di espressione</span><span class="sxs-lookup"><span data-stu-id="f10a3-130">Expression Examples</span></span>  
 <span data-ttu-id="f10a3-131">In questo esempio viene restituito FALSE se il valore della colonna **Color** è "red".</span><span class="sxs-lookup"><span data-stu-id="f10a3-131">This example evaluates to FALSE if the **Color** column value is "red".</span></span>  
  
```  
!(Color == "red")  
```  
  
 <span data-ttu-id="f10a3-132">In questo esempio viene restituito TRUE se il valore della variabile **MonthNumber** è uguale all'Integer che rappresenta il mese corrente.</span><span class="sxs-lookup"><span data-stu-id="f10a3-132">This example evaluates to TRUE if the value of the **MonthNumber** variable is the same as the integer that represents the current month.</span></span> <span data-ttu-id="f10a3-133">Per altre informazioni, vedere [MONTH &#40;espressione SSIS&#41;](month-ssis-expression.md) e [GETDATE &#40;espressione SSIS&#41;](getdate-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="f10a3-133">For more information, see [MONTH &#40;SSIS Expression&#41;](month-ssis-expression.md) and [GETDATE &#40;SSIS Expression&#41;](getdate-ssis-expression.md).</span></span>  
  
```  
!(@MonthNumber != MONTH(GETDATE())  
```  
  
## <a name="see-also"></a><span data-ttu-id="f10a3-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f10a3-134">See Also</span></span>  
 <span data-ttu-id="f10a3-135">[Precedenza e associatività degli operatori](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="f10a3-135">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="f10a3-136">Operatori &#40;espressione SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="f10a3-136">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
