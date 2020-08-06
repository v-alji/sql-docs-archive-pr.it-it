---
title: Divisione (espressione SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- / (divide)
- divide operator (/)
ms.assetid: 5bde9223-872d-443e-8a27-57735e1d8f3d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4541cd4601047770d1bf361077b1c474219e8833
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625467"
---
# <a name="divide-ssis-expression"></a><span data-ttu-id="da50c-102">Divisione (espressione SSIS)</span><span class="sxs-lookup"><span data-stu-id="da50c-102">Divide (SSIS Expression)</span></span>
  <span data-ttu-id="da50c-103">Viene divisa la prima espressione numerica per la seconda.</span><span class="sxs-lookup"><span data-stu-id="da50c-103">Divides the first numeric expression by the second one.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da50c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="da50c-104">Syntax</span></span>  
  
```  
  
dividend / divisor  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="da50c-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="da50c-105">Arguments</span></span>  
 <span data-ttu-id="da50c-106">*dividend*</span><span class="sxs-lookup"><span data-stu-id="da50c-106">*dividend*</span></span>  
 <span data-ttu-id="da50c-107">Espressione numerica da dividere.</span><span class="sxs-lookup"><span data-stu-id="da50c-107">Is the numeric expression to divide.</span></span> <span data-ttu-id="da50c-108">*dividend* può essere qualsiasi espressione numerica valida.</span><span class="sxs-lookup"><span data-stu-id="da50c-108">*dividend* can be any valid numeric expression.</span></span> <span data-ttu-id="da50c-109">Per altre informazioni, vedere [Tipi di dati di Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="da50c-109">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="da50c-110">*divisor*</span><span class="sxs-lookup"><span data-stu-id="da50c-110">*divisor*</span></span>  
 <span data-ttu-id="da50c-111">Espressione numerica per cui dividere il dividendo.</span><span class="sxs-lookup"><span data-stu-id="da50c-111">Is the numeric expression to divide the dividend by.</span></span> <span data-ttu-id="da50c-112">*divisor* può essere qualsiasi espressione numerica valida, tranne zero.</span><span class="sxs-lookup"><span data-stu-id="da50c-112">*divisor* can be any valid numeric expression except zero.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="da50c-113">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="da50c-113">Result Types</span></span>  
 <span data-ttu-id="da50c-114">Dipendenti dai tipi di dati dei due argomenti.</span><span class="sxs-lookup"><span data-stu-id="da50c-114">Determined by data types of the two arguments.</span></span> <span data-ttu-id="da50c-115">Per altre informazioni, vedere [Tipi di dati nelle espressioni di Integration Services](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="da50c-115">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="da50c-116">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="da50c-116">Remarks</span></span>  
 <span data-ttu-id="da50c-117">Se uno degli operandi è Null, il risultato sarà Null.</span><span class="sxs-lookup"><span data-stu-id="da50c-117">If either operand is null, the result is null.</span></span>  
  
 <span data-ttu-id="da50c-118">La divisione per zero non è consentita.</span><span class="sxs-lookup"><span data-stu-id="da50c-118">Dividing by zero is not legal.</span></span> <span data-ttu-id="da50c-119">A seconda della modalità con cui viene valutata la sottoespressione *divisor* , può verificarsi uno degli errori seguenti:</span><span class="sxs-lookup"><span data-stu-id="da50c-119">Depending on how the *divisor* subexpression is evaluated, one of following errors occurs:</span></span>  
  
-   <span data-ttu-id="da50c-120">Se la sottoespressione *divisor* che restituisce zero è una costante, l'errore verrà rilevato in fase di progettazione, impedendo la convalida dell'espressione.</span><span class="sxs-lookup"><span data-stu-id="da50c-120">If the *divisor* subexpression that evaluates to zero is a constant, the error appears at design time, causing the expression to fail validation.</span></span>  
  
-   <span data-ttu-id="da50c-121">Se la sottoespressione *divisor* che restituisce zero contiene variabili ma non colonne di input, il componente a cui appartiene l'espressione non supererà la convalida di pre-elaborazione, che avviene prima dell'esecuzione del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="da50c-121">If the *divisor* subexpression that evaluates to zero contains variables, but no input columns, the component to which the expression belongs fails the pre-execution validation that occurs before the package runs.</span></span>  
  
-   <span data-ttu-id="da50c-122">Se nella sottoespressione *divisor* tramite cui viene restituito zero sono contenute colonne di input, l'errore verrà visualizzato in fase di esecuzione e verrà gestito secondo le regole del flusso degli errori del componente flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="da50c-122">If the *divisor* subexpression that evaluates to zero contains input columns, the error appears at run time and is handled according to the error flow rules of the data flow component.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="da50c-123">Esempi di espressione</span><span class="sxs-lookup"><span data-stu-id="da50c-123">Expression Examples</span></span>  
 <span data-ttu-id="da50c-124">In questo esempio viene eseguita una divisione tra due valori letterali numerici.</span><span class="sxs-lookup"><span data-stu-id="da50c-124">This example divides two numeric literals.</span></span>  
  
```  
25 / 5  
```  
  
 <span data-ttu-id="da50c-125">In questo esempio i valori nella colonna **ListPrice** vengono divisi per i valori nella colonna **StandardCost** .</span><span class="sxs-lookup"><span data-stu-id="da50c-125">This example divides values in the **ListPrice** column by values in the **StandardCost** column.</span></span>  
  
```  
ListPrice / StandardCost  
```  
  
## <a name="see-also"></a><span data-ttu-id="da50c-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="da50c-126">See Also</span></span>  
 <span data-ttu-id="da50c-127">[Precedenza e associatività degli operatori](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="da50c-127">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="da50c-128">Operatori &#40;espressione SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="da50c-128">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
