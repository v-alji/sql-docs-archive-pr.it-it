---
title: () (parentesi) (espressione SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- () (parentheses operator)
- evaluation order [Integration Services]
- parentheses operator ()
ms.assetid: 931e10eb-1707-4121-b2f1-43565561119f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e390e10e485bd9cc22480300b6a9c33098bda8f1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724000"
---
# <a name="-parentheses-ssis-expression"></a><span data-ttu-id="7f88a-102">() (parentesi) (espressione SSIS)</span><span class="sxs-lookup"><span data-stu-id="7f88a-102">() (Parentheses) (SSIS Expression)</span></span>
  <span data-ttu-id="7f88a-103">Viene identificato l'ordine di valutazione delle espressioni.</span><span class="sxs-lookup"><span data-stu-id="7f88a-103">Identifies the evaluation order of expressions.</span></span> <span data-ttu-id="7f88a-104">Le espressioni racchiuse tra parentesi hanno la massima precedenza di valutazione.</span><span class="sxs-lookup"><span data-stu-id="7f88a-104">Expressions enclosed in parentheses have the highest evaluation precedence.</span></span> <span data-ttu-id="7f88a-105">Le espressioni nidificate racchiuse tra parentesi vengono valutate procedendo dall'interno verso l'esterno.</span><span class="sxs-lookup"><span data-stu-id="7f88a-105">Nested expressions enclosed in parentheses are evaluated in inner-to-outer order.</span></span>  
  
 <span data-ttu-id="7f88a-106">È possibile utilizzare le parentesi anche per semplificare la comprensione delle espressioni complesse.</span><span class="sxs-lookup"><span data-stu-id="7f88a-106">Parentheses are also used to make complex expressions easier to understand.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f88a-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7f88a-107">Syntax</span></span>  
  
```  
  
(expression)  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="7f88a-108">Argomenti</span><span class="sxs-lookup"><span data-stu-id="7f88a-108">Arguments</span></span>  
 <span data-ttu-id="7f88a-109">*expression*</span><span class="sxs-lookup"><span data-stu-id="7f88a-109">*expression*</span></span>  
 <span data-ttu-id="7f88a-110">È qualsiasi espressione valida.</span><span class="sxs-lookup"><span data-stu-id="7f88a-110">Is any valid expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="7f88a-111">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="7f88a-111">Result Types</span></span>  
 <span data-ttu-id="7f88a-112">Tipo di dati di *espressione*.</span><span class="sxs-lookup"><span data-stu-id="7f88a-112">The data type of *expression*.</span></span> <span data-ttu-id="7f88a-113">Per altre informazioni, vedere [Tipi di dati di Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="7f88a-113">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="7f88a-114">Esempi di espressione</span><span class="sxs-lookup"><span data-stu-id="7f88a-114">Expression Examples</span></span>  
 <span data-ttu-id="7f88a-115">In questo esempio viene illustrato come l'utilizzo delle parentesi modifichi la precedenza degli operatori.</span><span class="sxs-lookup"><span data-stu-id="7f88a-115">This example shows how the use of parenthesis modifies the precedence of operators.</span></span> <span data-ttu-id="7f88a-116">La prima espressione restituisce 100, mentre la seconda restituisce 31.</span><span class="sxs-lookup"><span data-stu-id="7f88a-116">The first expression evaluates to 100, whereas the second one evaluates to 31.</span></span>  
  
```  
(5 + 5) * (4 + 6)  
5 + 5 * 4 + 6  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="7f88a-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7f88a-117">See Also</span></span>  
 <span data-ttu-id="7f88a-118">[Precedenza e associatività degli operatori](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="7f88a-118">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="7f88a-119">Operatori &#40;espressione SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="7f88a-119">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
