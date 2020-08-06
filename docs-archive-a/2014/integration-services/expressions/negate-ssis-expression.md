---
title: '- (negazione) (espressione SSIS) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- '- (negative)'
- negative operator (-)
ms.assetid: f0118dfc-aced-4de2-953e-5ebf9c962b8d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2a2d8ba292f2d24633598ab080ddf75ded5e8bd1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720268"
---
# <a name="--negate-ssis-expression"></a><span data-ttu-id="025ca-102">- (negazione) (espressione SSIS)</span><span class="sxs-lookup"><span data-stu-id="025ca-102">- (Negate) (SSIS Expression)</span></span>
  <span data-ttu-id="025ca-103">Viene applicato un segno negativo a un'espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="025ca-103">Negates a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="025ca-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="025ca-104">Syntax</span></span>  
  
```  
  
-numeric_expression  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="025ca-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="025ca-105">Arguments</span></span>  
 <span data-ttu-id="025ca-106">*numeric_expression*</span><span class="sxs-lookup"><span data-stu-id="025ca-106">*numeric_expression*</span></span>  
 <span data-ttu-id="025ca-107">Espressione valida con qualsiasi tipo di dati numeric.</span><span class="sxs-lookup"><span data-stu-id="025ca-107">Is any valid expression of any numeric data type.</span></span> <span data-ttu-id="025ca-108">Sono supportati solo i tipi di dati numeric con segno.</span><span class="sxs-lookup"><span data-stu-id="025ca-108">Only signed numeric data types are supported.</span></span> <span data-ttu-id="025ca-109">Per altre informazioni, vedere [Tipi di dati di Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="025ca-109">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="025ca-110">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="025ca-110">Result Types</span></span>  
 <span data-ttu-id="025ca-111">Restituisce il tipo di dati di *numeric_expression*.</span><span class="sxs-lookup"><span data-stu-id="025ca-111">Returns the data type of *numeric_expression*.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="025ca-112">Esempi di espressione</span><span class="sxs-lookup"><span data-stu-id="025ca-112">Expression Examples</span></span>  
 <span data-ttu-id="025ca-113">In questo esempio viene applicato un segno negativo al valore della variabile **Counter** e viene aggiunto il valore letterale numerico 50.</span><span class="sxs-lookup"><span data-stu-id="025ca-113">This example negates the value of the **Counter** variable and adds the numeric literal 50.</span></span>  
  
```  
-@Counter + 50  
```  
  
## <a name="see-also"></a><span data-ttu-id="025ca-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="025ca-114">See Also</span></span>  
 <span data-ttu-id="025ca-115">[Precedenza e associatività degli operatori](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="025ca-115">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="025ca-116">Operatori &#40;espressione SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="025ca-116">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
