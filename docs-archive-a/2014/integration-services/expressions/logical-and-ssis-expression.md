---
title: '&amp;&amp; (AND logico) (espressione SSIS) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- '&& (logical AND)'
- AND, logical AND
- logical AND (&&)
ms.assetid: a8cb3517-d5d1-4861-9f04-905c719185ff
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8d973d7d4e86f88f7ae88c820ed4e4a5c1ce526f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713348"
---
# <a name="ampamp-logical-and-ssis-expression"></a><span data-ttu-id="20741-102">&amp;&amp; (AND logico) (espressione SSIS)</span><span class="sxs-lookup"><span data-stu-id="20741-102">&amp;&amp; (Logical AND) (SSIS Expression)</span></span>
  <span data-ttu-id="20741-103">Viene eseguita un'operazione con AND logico.</span><span class="sxs-lookup"><span data-stu-id="20741-103">Performs a logical AND operation.</span></span> <span data-ttu-id="20741-104">Viene restituito TRUE dall'espressione se tutte le condizioni sono TRUE.</span><span class="sxs-lookup"><span data-stu-id="20741-104">The expression evaluates to TRUE if all conditions are TRUE.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20741-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="20741-105">Syntax</span></span>  
  
```  
  
boolean_expression1 && boolean_expression2  
```  
  
## <a name="arguments"></a><span data-ttu-id="20741-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="20741-106">Arguments</span></span>  
 <span data-ttu-id="20741-107">*boolean _expression1, boolean_expression2*</span><span class="sxs-lookup"><span data-stu-id="20741-107">*boolean _expression1, boolean_expression2*</span></span>  
 <span data-ttu-id="20741-108">Qualsiasi espressione valida che restituisce TRUE, FALSE o NULL.</span><span class="sxs-lookup"><span data-stu-id="20741-108">Is any valid expression that evaluates to TRUE, FALSE, or NULL.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="20741-109">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="20741-109">Result Types</span></span>  
 <span data-ttu-id="20741-110">DT_BOOL</span><span class="sxs-lookup"><span data-stu-id="20741-110">DT_BOOL</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="20741-111">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="20741-111">Remarks</span></span>  
 <span data-ttu-id="20741-112">Il risultato dell'operatore && è illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="20741-112">The following table shows the result of the && operator.</span></span>  
  
|<span data-ttu-id="20741-113">Risultato</span><span class="sxs-lookup"><span data-stu-id="20741-113">Result</span></span>|<span data-ttu-id="20741-114">Expression</span><span class="sxs-lookup"><span data-stu-id="20741-114">Expression</span></span>|<span data-ttu-id="20741-115">Expression</span><span class="sxs-lookup"><span data-stu-id="20741-115">Expression</span></span>|  
|------------|----------------|----------------|  
|<span data-ttu-id="20741-116">TRUE</span><span class="sxs-lookup"><span data-stu-id="20741-116">TRUE</span></span>|<span data-ttu-id="20741-117">TRUE</span><span class="sxs-lookup"><span data-stu-id="20741-117">TRUE</span></span>|<span data-ttu-id="20741-118">TRUE</span><span class="sxs-lookup"><span data-stu-id="20741-118">TRUE</span></span>|  
|<span data-ttu-id="20741-119">FALSE</span><span class="sxs-lookup"><span data-stu-id="20741-119">FALSE</span></span>|<span data-ttu-id="20741-120">TRUE</span><span class="sxs-lookup"><span data-stu-id="20741-120">TRUE</span></span>|<span data-ttu-id="20741-121">FALSE</span><span class="sxs-lookup"><span data-stu-id="20741-121">FALSE</span></span>|  
|<span data-ttu-id="20741-122">FALSE</span><span class="sxs-lookup"><span data-stu-id="20741-122">FALSE</span></span>|<span data-ttu-id="20741-123">FALSE</span><span class="sxs-lookup"><span data-stu-id="20741-123">FALSE</span></span>|<span data-ttu-id="20741-124">FALSE</span><span class="sxs-lookup"><span data-stu-id="20741-124">FALSE</span></span>|  
|<span data-ttu-id="20741-125">NULL</span><span class="sxs-lookup"><span data-stu-id="20741-125">NULL</span></span>|<span data-ttu-id="20741-126">NULL</span><span class="sxs-lookup"><span data-stu-id="20741-126">NULL</span></span>|<span data-ttu-id="20741-127">NULL</span><span class="sxs-lookup"><span data-stu-id="20741-127">NULL</span></span>|  
|<span data-ttu-id="20741-128">NULL</span><span class="sxs-lookup"><span data-stu-id="20741-128">NULL</span></span>|<span data-ttu-id="20741-129">NULL</span><span class="sxs-lookup"><span data-stu-id="20741-129">NULL</span></span>|<span data-ttu-id="20741-130">TRUE</span><span class="sxs-lookup"><span data-stu-id="20741-130">TRUE</span></span>|  
|<span data-ttu-id="20741-131">FALSE</span><span class="sxs-lookup"><span data-stu-id="20741-131">FALSE</span></span>|<span data-ttu-id="20741-132">NULL</span><span class="sxs-lookup"><span data-stu-id="20741-132">NULL</span></span>|<span data-ttu-id="20741-133">FALSE</span><span class="sxs-lookup"><span data-stu-id="20741-133">FALSE</span></span>|  
  
## <a name="expression-examples"></a><span data-ttu-id="20741-134">Esempi di espressione</span><span class="sxs-lookup"><span data-stu-id="20741-134">Expression Examples</span></span>  
 <span data-ttu-id="20741-135">In questo esempio vengono usate le colonne **StandardCost** e **ListPrice** .</span><span class="sxs-lookup"><span data-stu-id="20741-135">This example uses the **StandardCost** and the **ListPrice** columns.</span></span> <span data-ttu-id="20741-136">Viene restituito TRUE se il valore della colonna **StandardCost** è minore di 300 e quello della colonna **ListPrice** è maggiore di 500.</span><span class="sxs-lookup"><span data-stu-id="20741-136">The example evaluates to TRUE if the value of the **StandardCost** column is less than 300 and the **ListPrice** column is greater than 500.</span></span>  
  
```  
StandardCost < 300 && ListPrice > 500  
```  
  
 <span data-ttu-id="20741-137">In questo esempio vengono usate le variabili **SPrice** e **LPrice** anziché valori letterali.</span><span class="sxs-lookup"><span data-stu-id="20741-137">This example uses the variables **SPrice** and **LPrice** instead of literals.</span></span>  
  
```  
StandardCost < @SPrice && ListPrice > @LPrice  
```  
  
## <a name="see-also"></a><span data-ttu-id="20741-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="20741-138">See Also</span></span>  
 <span data-ttu-id="20741-139">[&& &#40;AND bit per bit&#41; &#40;espressione SSIS&#41;](bitwise-and-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="20741-139">[& &#40;Bitwise AND&#41; &#40;SSIS Expression&#41;](bitwise-and-ssis-expression.md) </span></span>  
 <span data-ttu-id="20741-140">[Precedenza e associatività degli operatori](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="20741-140">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="20741-141">Operatori &#40;espressione SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="20741-141">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
