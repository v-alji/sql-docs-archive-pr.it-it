---
title: '|| (OR logico) (espressione SSIS) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- OR operator
- logical OR (||)
- '|| (logical OR)'
ms.assetid: a3c07c09-f121-4187-9617-b01adcf843c4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 72d4a1c7b54856675f0faa7f5f58452cb8bca450
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713351"
---
# <a name="-logical-or-ssis-expression"></a><span data-ttu-id="b2d2a-102">|| (OR logico) (espressione SSIS)</span><span class="sxs-lookup"><span data-stu-id="b2d2a-102">|| (Logical OR) (SSIS Expression)</span></span>
  <span data-ttu-id="b2d2a-103">Viene eseguita un'operazione con OR logico.</span><span class="sxs-lookup"><span data-stu-id="b2d2a-103">Performs a logical OR operation.</span></span> <span data-ttu-id="b2d2a-104">Viene restituito TRUE dall'espressione se una o entrambe le condizioni sono TRUE.</span><span class="sxs-lookup"><span data-stu-id="b2d2a-104">The expression evaluates to TRUE if one or both conditions are TRUE.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2d2a-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b2d2a-105">Syntax</span></span>  
  
```  
  
boolean_expression1 || boolean_expression2  
```  
  
## <a name="arguments"></a><span data-ttu-id="b2d2a-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="b2d2a-106">Arguments</span></span>  
 <span data-ttu-id="b2d2a-107">*boolean_expression1, boolean_expression2*</span><span class="sxs-lookup"><span data-stu-id="b2d2a-107">*boolean_expression1, boolean_expression2*</span></span>  
 <span data-ttu-id="b2d2a-108">Qualsiasi espressione valida che restituisce TRUE, FALSE o NULL.</span><span class="sxs-lookup"><span data-stu-id="b2d2a-108">Is any valid expression that evaluates to TRUE, FALSE, or NULL.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="b2d2a-109">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="b2d2a-109">Result Types</span></span>  
 <span data-ttu-id="b2d2a-110">DT_BOOL</span><span class="sxs-lookup"><span data-stu-id="b2d2a-110">DT_BOOL</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b2d2a-111">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="b2d2a-111">Remarks</span></span>  
 <span data-ttu-id="b2d2a-112">Il risultato dell'operatore || è illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="b2d2a-112">The following table shows the result of the || operator.</span></span>  
  
|<span data-ttu-id="b2d2a-113">Risultato</span><span class="sxs-lookup"><span data-stu-id="b2d2a-113">Result</span></span>|<span data-ttu-id="b2d2a-114">Expression</span><span class="sxs-lookup"><span data-stu-id="b2d2a-114">Expression</span></span>|<span data-ttu-id="b2d2a-115">Expression</span><span class="sxs-lookup"><span data-stu-id="b2d2a-115">Expression</span></span>|  
|------------|----------------|----------------|  
|<span data-ttu-id="b2d2a-116">TRUE</span><span class="sxs-lookup"><span data-stu-id="b2d2a-116">TRUE</span></span>|<span data-ttu-id="b2d2a-117">TRUE</span><span class="sxs-lookup"><span data-stu-id="b2d2a-117">TRUE</span></span>|<span data-ttu-id="b2d2a-118">TRUE</span><span class="sxs-lookup"><span data-stu-id="b2d2a-118">TRUE</span></span>|  
|<span data-ttu-id="b2d2a-119">TRUE</span><span class="sxs-lookup"><span data-stu-id="b2d2a-119">TRUE</span></span>|<span data-ttu-id="b2d2a-120">TRUE</span><span class="sxs-lookup"><span data-stu-id="b2d2a-120">TRUE</span></span>|<span data-ttu-id="b2d2a-121">FALSE</span><span class="sxs-lookup"><span data-stu-id="b2d2a-121">FALSE</span></span>|  
|<span data-ttu-id="b2d2a-122">FALSE</span><span class="sxs-lookup"><span data-stu-id="b2d2a-122">FALSE</span></span>|<span data-ttu-id="b2d2a-123">FALSE</span><span class="sxs-lookup"><span data-stu-id="b2d2a-123">FALSE</span></span>|<span data-ttu-id="b2d2a-124">FALSE</span><span class="sxs-lookup"><span data-stu-id="b2d2a-124">FALSE</span></span>|  
|<span data-ttu-id="b2d2a-125">NULL</span><span class="sxs-lookup"><span data-stu-id="b2d2a-125">NULL</span></span>|<span data-ttu-id="b2d2a-126">NULL</span><span class="sxs-lookup"><span data-stu-id="b2d2a-126">NULL</span></span>|<span data-ttu-id="b2d2a-127">NULL</span><span class="sxs-lookup"><span data-stu-id="b2d2a-127">NULL</span></span>|  
|<span data-ttu-id="b2d2a-128">TRUE</span><span class="sxs-lookup"><span data-stu-id="b2d2a-128">TRUE</span></span>|<span data-ttu-id="b2d2a-129">NULL</span><span class="sxs-lookup"><span data-stu-id="b2d2a-129">NULL</span></span>|<span data-ttu-id="b2d2a-130">TRUE</span><span class="sxs-lookup"><span data-stu-id="b2d2a-130">TRUE</span></span>|  
|<span data-ttu-id="b2d2a-131">NULL</span><span class="sxs-lookup"><span data-stu-id="b2d2a-131">NULL</span></span>|<span data-ttu-id="b2d2a-132">NULL</span><span class="sxs-lookup"><span data-stu-id="b2d2a-132">NULL</span></span>|<span data-ttu-id="b2d2a-133">FALSE</span><span class="sxs-lookup"><span data-stu-id="b2d2a-133">FALSE</span></span>|  
  
## <a name="ssis-expression-examples"></a><span data-ttu-id="b2d2a-134">Esempi di espressione SSIS</span><span class="sxs-lookup"><span data-stu-id="b2d2a-134">SSIS Expression Examples</span></span>  
 <span data-ttu-id="b2d2a-135">In questo esempio vengono utilizzate le colonne **StandardCost** e **ListPrice** .</span><span class="sxs-lookup"><span data-stu-id="b2d2a-135">This example uses the **StandardCost** and **ListPrice** columns.</span></span> <span data-ttu-id="b2d2a-136">Viene restituito TRUE se il valore della colonna **StandardCost** è minore di 300 o quello della colonna **ListPrice** è maggiore di 500.</span><span class="sxs-lookup"><span data-stu-id="b2d2a-136">The example evaluates to TRUE if the value of the **StandardCost** column is less than 300 or the **ListPrice** column is greater than 500.</span></span>  
  
```  
StandardCost < 300 || ListPrice > 500  
```  
  
 <span data-ttu-id="b2d2a-137">In questo esempio vengono utilizzate le variabili **SPrice** e **LPrice** anziché valori letterali numerici.</span><span class="sxs-lookup"><span data-stu-id="b2d2a-137">This example uses the variables **SPrice** and **LPrice** instead of numeric literals.</span></span>  
  
```  
StandardCost < @SPrice || ListPrice > @LPrice  
```  
  
## <a name="see-also"></a><span data-ttu-id="b2d2a-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b2d2a-138">See Also</span></span>  
 <span data-ttu-id="b2d2a-139">[&#124; &#40;OR inclusivo bit per bit&#41; &#40;espressione SSIS&#41;](bitwise-inclusive-or-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="b2d2a-139">[&#124; &#40;Bitwise Inclusive OR&#41; &#40;SSIS Expression&#41;](bitwise-inclusive-or-ssis-expression.md) </span></span>  
 <span data-ttu-id="b2d2a-140">[^ &#40;OR esclusivo bit per bit&#41; &#40;Espressione SSIS&#41;](bitwise-exclusive-or-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="b2d2a-140">[^ &#40;Bitwise Exclusive OR&#41; &#40;SSIS Expression&#41;](bitwise-exclusive-or-ssis-expression.md) </span></span>  
 <span data-ttu-id="b2d2a-141">[Precedenza e associatività degli operatori](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="b2d2a-141">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="b2d2a-142">Operatori &#40;espressione SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="b2d2a-142">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
