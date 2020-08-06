---
title: DATEPART (espressione SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- dates [Integration Services], DATEPART
- DATEPART function
ms.assetid: 3e590094-fc49-4144-805f-fdc1bf2fe509
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8aed7146c74c6738ba979f422bd65b7e1b539e15
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715596"
---
# <a name="datepart-ssis-expression"></a><span data-ttu-id="c4eb7-102">DATEPART (espressione SSIS)</span><span class="sxs-lookup"><span data-stu-id="c4eb7-102">DATEPART (SSIS Expression)</span></span>
  <span data-ttu-id="c4eb7-103">Restituisce un valore integer che rappresenta una parte di una data.</span><span class="sxs-lookup"><span data-stu-id="c4eb7-103">Returns an integer representing a datepart of a date.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4eb7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c4eb7-104">Syntax</span></span>  
  
```  
  
DATEPART(datepart, date)  
```  
  
## <a name="arguments"></a><span data-ttu-id="c4eb7-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="c4eb7-105">Arguments</span></span>  
 <span data-ttu-id="c4eb7-106">*datepart*</span><span class="sxs-lookup"><span data-stu-id="c4eb7-106">*datepart*</span></span>  
 <span data-ttu-id="c4eb7-107">Parametro che consente di specificare per quale parte della data si desidera restituire un nuovo valore.</span><span class="sxs-lookup"><span data-stu-id="c4eb7-107">Is the parameter that specifies for which part of the date to return a new value.</span></span>  
  
 <span data-ttu-id="c4eb7-108">*date*</span><span class="sxs-lookup"><span data-stu-id="c4eb7-108">*date*</span></span>  
 <span data-ttu-id="c4eb7-109">Espressione che restituisce una data valida o una stringa con formato di data.</span><span class="sxs-lookup"><span data-stu-id="c4eb7-109">Is an expression that returns a valid date or a string in date format.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="c4eb7-110">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="c4eb7-110">Result Types</span></span>  
 <span data-ttu-id="c4eb7-111">DT_I4</span><span class="sxs-lookup"><span data-stu-id="c4eb7-111">DT_I4</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c4eb7-112">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="c4eb7-112">Remarks</span></span>  
 <span data-ttu-id="c4eb7-113">Se l'argomento è Null, DATEPART restituirà Null.</span><span class="sxs-lookup"><span data-stu-id="c4eb7-113">DATEPART returns a null result if the argument is null.</span></span>  
  
 <span data-ttu-id="c4eb7-114">Per i valori letterali di data è necessario eseguire il cast esplicito a uno dei tipi di dati date.</span><span class="sxs-lookup"><span data-stu-id="c4eb7-114">A date literal must be explicitly cast to one of the date data types.</span></span> <span data-ttu-id="c4eb7-115">Per altre informazioni, vedere [Tipi di dati di Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="c4eb7-115">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="c4eb7-116">Nella tabella seguente sono elencate le parti della data e le abbreviazioni riconosciute dall'analizzatore di espressioni.</span><span class="sxs-lookup"><span data-stu-id="c4eb7-116">The following table lists the dateparts and abbreviations recognized by the expression evaluator.</span></span> <span data-ttu-id="c4eb7-117">Per i nomi delle parti della data non viene fatta distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="c4eb7-117">Datepart names are not case sensitive.</span></span>  
  
|<span data-ttu-id="c4eb7-118">parte di una data</span><span class="sxs-lookup"><span data-stu-id="c4eb7-118">Datepart</span></span>|<span data-ttu-id="c4eb7-119">Abbreviazioni</span><span class="sxs-lookup"><span data-stu-id="c4eb7-119">Abbreviations</span></span>|  
|--------------|-------------------|  
|<span data-ttu-id="c4eb7-120">Year</span><span class="sxs-lookup"><span data-stu-id="c4eb7-120">Year</span></span>|<span data-ttu-id="c4eb7-121">yy, yyyy</span><span class="sxs-lookup"><span data-stu-id="c4eb7-121">yy, yyyy</span></span>|  
|<span data-ttu-id="c4eb7-122">Quarter</span><span class="sxs-lookup"><span data-stu-id="c4eb7-122">Quarter</span></span>|<span data-ttu-id="c4eb7-123">qq, q</span><span class="sxs-lookup"><span data-stu-id="c4eb7-123">qq, q</span></span>|  
|<span data-ttu-id="c4eb7-124">Month</span><span class="sxs-lookup"><span data-stu-id="c4eb7-124">Month</span></span>|<span data-ttu-id="c4eb7-125">mm, m</span><span class="sxs-lookup"><span data-stu-id="c4eb7-125">mm, m</span></span>|  
|<span data-ttu-id="c4eb7-126">Dayofyear</span><span class="sxs-lookup"><span data-stu-id="c4eb7-126">Dayofyear</span></span>|<span data-ttu-id="c4eb7-127">dy, y</span><span class="sxs-lookup"><span data-stu-id="c4eb7-127">dy, y</span></span>|  
|<span data-ttu-id="c4eb7-128">Giorno</span><span class="sxs-lookup"><span data-stu-id="c4eb7-128">Day</span></span>|<span data-ttu-id="c4eb7-129">dd, d</span><span class="sxs-lookup"><span data-stu-id="c4eb7-129">dd, d</span></span>|  
|<span data-ttu-id="c4eb7-130">Week</span><span class="sxs-lookup"><span data-stu-id="c4eb7-130">Week</span></span>|<span data-ttu-id="c4eb7-131">wk, ww</span><span class="sxs-lookup"><span data-stu-id="c4eb7-131">wk, ww</span></span>|  
|<span data-ttu-id="c4eb7-132">Giorno della settimana</span><span class="sxs-lookup"><span data-stu-id="c4eb7-132">Weekday</span></span>|<span data-ttu-id="c4eb7-133">dw</span><span class="sxs-lookup"><span data-stu-id="c4eb7-133">dw</span></span>|  
|<span data-ttu-id="c4eb7-134">Ora</span><span class="sxs-lookup"><span data-stu-id="c4eb7-134">Hour</span></span>|<span data-ttu-id="c4eb7-135">Hh</span><span class="sxs-lookup"><span data-stu-id="c4eb7-135">Hh</span></span>|  
|<span data-ttu-id="c4eb7-136">Minuto</span><span class="sxs-lookup"><span data-stu-id="c4eb7-136">Minute</span></span>|<span data-ttu-id="c4eb7-137">mi, n</span><span class="sxs-lookup"><span data-stu-id="c4eb7-137">mi, n</span></span>|  
|<span data-ttu-id="c4eb7-138">Second</span><span class="sxs-lookup"><span data-stu-id="c4eb7-138">Second</span></span>|<span data-ttu-id="c4eb7-139">ss, s</span><span class="sxs-lookup"><span data-stu-id="c4eb7-139">ss, s</span></span>|  
|<span data-ttu-id="c4eb7-140">Millisecond</span><span class="sxs-lookup"><span data-stu-id="c4eb7-140">Millisecond</span></span>|<span data-ttu-id="c4eb7-141">Ms</span><span class="sxs-lookup"><span data-stu-id="c4eb7-141">Ms</span></span>|  
  
## <a name="ssis-expression-examples"></a><span data-ttu-id="c4eb7-142">Esempi di espressione SSIS</span><span class="sxs-lookup"><span data-stu-id="c4eb7-142">SSIS Expression Examples</span></span>  
 <span data-ttu-id="c4eb7-143">In questo esempio viene restituito un valore integer che rappresenta il mese in un valore letterale data.</span><span class="sxs-lookup"><span data-stu-id="c4eb7-143">This example returns the integer that represents the month in a date literal.</span></span> <span data-ttu-id="c4eb7-144">Se la data è in formato "mm/gg/aaaa", l'esempio restituirà 11.</span><span class="sxs-lookup"><span data-stu-id="c4eb7-144">If the date is in mm/dd/yyyy" format, this example returns 11.</span></span>  
  
```  
DATEPART("month", (DT_DBTIMESTAMP)"11/04/2002")  
```  
  
 <span data-ttu-id="c4eb7-145">In questo esempio viene restituito un Integer che rappresenta il giorno nella colonna **ModifiedDate** .</span><span class="sxs-lookup"><span data-stu-id="c4eb7-145">This example returns the integer that represents the day in the **ModifiedDate** column.</span></span>  
  
```  
DATEPART("dd", ModifiedDate)  
```  
  
 <span data-ttu-id="c4eb7-146">In questo esempio viene restituito un valore integer che rappresenta l'anno nella data corrente.</span><span class="sxs-lookup"><span data-stu-id="c4eb7-146">This example returns the integer that represents the year of the current date.</span></span>  
  
```  
DATEPART("yy",GETDATE())  
```  
  
## <a name="see-also"></a><span data-ttu-id="c4eb7-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c4eb7-147">See Also</span></span>  
 <span data-ttu-id="c4eb7-148">[DATEADD &#40;espressione SSIS&#41;](dateadd-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="c4eb7-148">[DATEADD &#40;SSIS Expression&#41;](dateadd-ssis-expression.md) </span></span>  
 <span data-ttu-id="c4eb7-149">[DATEDIFF &#40;espressione SSIS&#41;](datediff-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="c4eb7-149">[DATEDIFF &#40;SSIS Expression&#41;](datediff-ssis-expression.md) </span></span>  
 <span data-ttu-id="c4eb7-150">[DAY &#40;espressione SSIS&#41;](day-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="c4eb7-150">[DAY &#40;SSIS Expression&#41;](day-ssis-expression.md) </span></span>  
 <span data-ttu-id="c4eb7-151">[MONTH &#40;espressione SSIS&#41;](month-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="c4eb7-151">[MONTH &#40;SSIS Expression&#41;](month-ssis-expression.md) </span></span>  
 <span data-ttu-id="c4eb7-152">[YEAR &#40;espressione SSIS&#41;](year-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="c4eb7-152">[YEAR &#40;SSIS Expression&#41;](year-ssis-expression.md) </span></span>  
 [<span data-ttu-id="c4eb7-153">Funzioni &#40;espressione SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="c4eb7-153">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
