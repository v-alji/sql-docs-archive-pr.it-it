---
title: DAY (espressione SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- DAY function
- dates [Integration Services], DAY
ms.assetid: d8447187-49df-45b7-a98e-142ad44fd3e2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1b7acac3f3949cbbd07adbe6382ea3d875f94cb2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715592"
---
# <a name="day-ssis-expression"></a><span data-ttu-id="21de0-102">DAY (espressione SSIS)</span><span class="sxs-lookup"><span data-stu-id="21de0-102">DAY (SSIS Expression)</span></span>
  <span data-ttu-id="21de0-103">Viene restituito un valore integer che rappresenta la parte del giorno in una data.</span><span class="sxs-lookup"><span data-stu-id="21de0-103">Returns an integer that represents the day datepart of a date.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21de0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="21de0-104">Syntax</span></span>  
  
```  
  
DAY(date)  
```  
  
## <a name="arguments"></a><span data-ttu-id="21de0-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="21de0-105">Arguments</span></span>  
 <span data-ttu-id="21de0-106">*date*</span><span class="sxs-lookup"><span data-stu-id="21de0-106">*date*</span></span>  
 <span data-ttu-id="21de0-107">Espressione che restituisce una data valida o una stringa con formato di data.</span><span class="sxs-lookup"><span data-stu-id="21de0-107">Is an expression that returns a valid date or a string in date format.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="21de0-108">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="21de0-108">Result Types</span></span>  
 <span data-ttu-id="21de0-109">DT_I4</span><span class="sxs-lookup"><span data-stu-id="21de0-109">DT_I4</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="21de0-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="21de0-110">Remarks</span></span>  
 <span data-ttu-id="21de0-111">Se l'argomento è Null, DAY restituirà Null.</span><span class="sxs-lookup"><span data-stu-id="21de0-111">DAY returns a null result if the argument is null.</span></span>  
  
 <span data-ttu-id="21de0-112">Per i valori letterali di data è necessario eseguire il cast esplicito a uno dei tipi di dati date.</span><span class="sxs-lookup"><span data-stu-id="21de0-112">A date literal must be explicitly cast to one of the date data types.</span></span> <span data-ttu-id="21de0-113">Per altre informazioni, vedere [Tipi di dati di Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="21de0-113">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="21de0-114">La convalida dell'espressione non riesce quando viene eseguito il cast esplicito di un valore letterale di data a uno di questi tipi di dati relativi alle date: DT_DBTIMESTAMPOFFSET e DT_DBTIMESTAMP2.</span><span class="sxs-lookup"><span data-stu-id="21de0-114">The expression fails to validate when a date literal is explicitly cast to one of these date data types: DT_DBTIMESTAMPOFFSET and DT_DBTIMESTAMP2.</span></span>  
  
 <span data-ttu-id="21de0-115">La funzione DAY costituisce una forma più breve, ma equivalente, della funzione DATEPART("Day", date).</span><span class="sxs-lookup"><span data-stu-id="21de0-115">Using the DAY function is briefer but equivalent to using DATEPART("Day", date).</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="21de0-116">Esempi di espressione</span><span class="sxs-lookup"><span data-stu-id="21de0-116">Expression Examples</span></span>  
 <span data-ttu-id="21de0-117">In questo esempio viene restituito il numero del giorno in un valore letterale di data.</span><span class="sxs-lookup"><span data-stu-id="21de0-117">This example returns the number of the day in a date literal.</span></span> <span data-ttu-id="21de0-118">Se la data è in formato "mm/gg/aaaa", l'esempio restituirà 23.</span><span class="sxs-lookup"><span data-stu-id="21de0-118">If the date format is in "mm/dd/yyyy" format, this example returns 23.</span></span>  
  
```  
DAY((DT_DBTIMESTAMP)"11/23/2002")  
```  
  
 <span data-ttu-id="21de0-119">In questo esempio viene restituito un Integer che rappresenta il giorno nella colonna **ModifiedDate** .</span><span class="sxs-lookup"><span data-stu-id="21de0-119">This example returns the integer that represents the day in the **ModifiedDate** column.</span></span>  
  
```  
DAY(ModifiedDate)  
```  
  
 <span data-ttu-id="21de0-120">In questo esempio viene restituito un valore integer che rappresenta il giorno nella data corrente.</span><span class="sxs-lookup"><span data-stu-id="21de0-120">This example returns the integer that represents the day of the current date.</span></span>  
  
```  
DAY(GETDATE())  
```  
  
## <a name="see-also"></a><span data-ttu-id="21de0-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="21de0-121">See Also</span></span>  
 <span data-ttu-id="21de0-122">[DATEADD &#40;espressione SSIS&#41;](dateadd-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="21de0-122">[DATEADD &#40;SSIS Expression&#41;](dateadd-ssis-expression.md) </span></span>  
 <span data-ttu-id="21de0-123">[DATEDIFF &#40;espressione SSIS&#41;](datediff-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="21de0-123">[DATEDIFF &#40;SSIS Expression&#41;](datediff-ssis-expression.md) </span></span>  
 <span data-ttu-id="21de0-124">[DATEPART &#40;espressione SSIS&#41;](datepart-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="21de0-124">[DATEPART &#40;SSIS Expression&#41;](datepart-ssis-expression.md) </span></span>  
 <span data-ttu-id="21de0-125">[MONTH &#40;espressione SSIS&#41;](month-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="21de0-125">[MONTH &#40;SSIS Expression&#41;](month-ssis-expression.md) </span></span>  
 <span data-ttu-id="21de0-126">[YEAR &#40;espressione SSIS&#41;](year-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="21de0-126">[YEAR &#40;SSIS Expression&#41;](year-ssis-expression.md) </span></span>  
 [<span data-ttu-id="21de0-127">Funzioni &#40;espressione SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="21de0-127">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
