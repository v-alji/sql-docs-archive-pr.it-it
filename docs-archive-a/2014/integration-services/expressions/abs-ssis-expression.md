---
title: ABS (espressione SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- ABS function
- absolute positive value
ms.assetid: 156747f6-e016-44cf-9a9f-ae8e4a1b4f17
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a2f429dda94282646ef769a1c393f9fa54b56e5e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635189"
---
# <a name="abs-ssis-expression"></a><span data-ttu-id="afe02-102">ABS (espressione SSIS)</span><span class="sxs-lookup"><span data-stu-id="afe02-102">ABS (SSIS Expression)</span></span>
  <span data-ttu-id="afe02-103">Restituisce il valore positivo assoluto di un'espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="afe02-103">Returns the absolute, positive value of a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="afe02-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="afe02-104">Syntax</span></span>  
  
```  
  
ABS(numeric_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="afe02-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="afe02-105">Arguments</span></span>  
 <span data-ttu-id="afe02-106">*numeric_expression*</span><span class="sxs-lookup"><span data-stu-id="afe02-106">*numeric_expression*</span></span>  
 <span data-ttu-id="afe02-107">Espressione numerica con o senza segno.</span><span class="sxs-lookup"><span data-stu-id="afe02-107">Is a signed or unsigned numeric expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="afe02-108">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="afe02-108">Result Types</span></span>  
 <span data-ttu-id="afe02-109">Tipo di dati dell'espressione numerica inviata alla funzione.</span><span class="sxs-lookup"><span data-stu-id="afe02-109">The data type of the numeric expression submitted to the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="afe02-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="afe02-110">Remarks</span></span>  
 <span data-ttu-id="afe02-111">Se l'argomento è Null, ABS restituirà Null.</span><span class="sxs-lookup"><span data-stu-id="afe02-111">ABS returns a null result if the argument is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="afe02-112">Esempi di espressione</span><span class="sxs-lookup"><span data-stu-id="afe02-112">Expression Examples</span></span>  
 <span data-ttu-id="afe02-113">In questi esempi la funzione ABS viene applicata a un numero positivo e a un numero negativo.</span><span class="sxs-lookup"><span data-stu-id="afe02-113">These examples apply the ABS function to a positive and a negative number.</span></span> <span data-ttu-id="afe02-114">In entrambi i casi viene restituito 1,23.</span><span class="sxs-lookup"><span data-stu-id="afe02-114">Both return 1.23.</span></span>  
  
```  
ABS(-1.23)  
ABS(1.23)  
```  
  
 <span data-ttu-id="afe02-115">In questo esempio la funzione ABS viene applicata a un'espressione che esegue una sottrazione tra i valori delle variabili **HighTemperature** e **LowTempature**.</span><span class="sxs-lookup"><span data-stu-id="afe02-115">This example applies the ABS function to an expression that subtracts values in the variables **HighTemperature** and **LowTempature**.</span></span>  
  
```  
ABS(@HighTemperature - @LowTemperature)  
```  
  
## <a name="see-also"></a><span data-ttu-id="afe02-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="afe02-116">See Also</span></span>  
 [<span data-ttu-id="afe02-117">Funzioni &#40;espressione SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="afe02-117">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
