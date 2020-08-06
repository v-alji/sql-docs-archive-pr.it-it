---
title: DATEADD (espressione SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- dates [Integration Services], DATEADD
- dates [Integration Services]
- DATEADD function
ms.assetid: fa5c37b1-2ddc-4857-8f8e-f6d5643b654f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9feb288318bdf9705928cb930f175f5c170c384e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721655"
---
# <a name="dateadd-ssis-expression"></a><span data-ttu-id="80816-102">DATEADD (espressione SSIS)</span><span class="sxs-lookup"><span data-stu-id="80816-102">DATEADD (SSIS Expression)</span></span>
  <span data-ttu-id="80816-103">Viene restituito un nuovo valore DT_DBTIMESTAMP dopo aver aggiunto alla parte specificata di una data un numero che rappresenta un intervallo di date o di ore.</span><span class="sxs-lookup"><span data-stu-id="80816-103">Returns a new DT_DBTIMESTAMP value after adding a number that represents a date or time interval to the specified datepart in a date.</span></span> <span data-ttu-id="80816-104">Il parametro number deve restituire un valore integer e il parametro date deve restituire una data valida.</span><span class="sxs-lookup"><span data-stu-id="80816-104">The number parameter must evaluate to an integer, and the date parameter must evaluate to a valid date.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80816-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="80816-105">Syntax</span></span>  
  
```  
  
DATEADD(datepart, number, date)  
```  
  
## <a name="arguments"></a><span data-ttu-id="80816-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="80816-106">Arguments</span></span>  
 <span data-ttu-id="80816-107">*datepart*</span><span class="sxs-lookup"><span data-stu-id="80816-107">*datepart*</span></span>  
 <span data-ttu-id="80816-108">Parametro che specifica la parte della data a cui aggiungere il numero.</span><span class="sxs-lookup"><span data-stu-id="80816-108">Is the parameter that specifies which part of the date to add a number to.</span></span>  
  
 <span data-ttu-id="80816-109">*number*</span><span class="sxs-lookup"><span data-stu-id="80816-109">*number*</span></span>  
 <span data-ttu-id="80816-110">Valore usato per incrementare il valore *datepart*.</span><span class="sxs-lookup"><span data-stu-id="80816-110">Is the value used to increment *datepart*.</span></span> <span data-ttu-id="80816-111">Deve essere un valore integer noto al momento dell'analisi dell'espressione.</span><span class="sxs-lookup"><span data-stu-id="80816-111">The value must be an integer value that is known when the expression is parsed.</span></span>  
  
 <span data-ttu-id="80816-112">*date*</span><span class="sxs-lookup"><span data-stu-id="80816-112">*date*</span></span>  
 <span data-ttu-id="80816-113">Espressione che restituisce una data valida o una stringa con formato di data.</span><span class="sxs-lookup"><span data-stu-id="80816-113">Is an expression that returns a valid date or a string in date format.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="80816-114">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="80816-114">Result Types</span></span>  
 <span data-ttu-id="80816-115">DT_DBTIMESTAMP</span><span class="sxs-lookup"><span data-stu-id="80816-115">DT_DBTIMESTAMP</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="80816-116">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="80816-116">Remarks</span></span>  
 <span data-ttu-id="80816-117">Nella tabella seguente sono elencate le parti della data e le abbreviazioni riconosciute dall'analizzatore di espressioni.</span><span class="sxs-lookup"><span data-stu-id="80816-117">The following table lists the dateparts and abbreviations recognized by the expression evaluator.</span></span> <span data-ttu-id="80816-118">Per i nomi delle parti della data non viene fatta distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="80816-118">Datepart names are not case sensitive.</span></span>  
  
|<span data-ttu-id="80816-119">parte di una data</span><span class="sxs-lookup"><span data-stu-id="80816-119">Datepart</span></span>|<span data-ttu-id="80816-120">Abbreviazioni</span><span class="sxs-lookup"><span data-stu-id="80816-120">Abbreviations</span></span>|  
|--------------|-------------------|  
|<span data-ttu-id="80816-121">Year</span><span class="sxs-lookup"><span data-stu-id="80816-121">Year</span></span>|<span data-ttu-id="80816-122">yy, yyyy</span><span class="sxs-lookup"><span data-stu-id="80816-122">yy, yyyy</span></span>|  
|<span data-ttu-id="80816-123">Quarter</span><span class="sxs-lookup"><span data-stu-id="80816-123">Quarter</span></span>|<span data-ttu-id="80816-124">qq, q</span><span class="sxs-lookup"><span data-stu-id="80816-124">qq, q</span></span>|  
|<span data-ttu-id="80816-125">Month</span><span class="sxs-lookup"><span data-stu-id="80816-125">Month</span></span>|<span data-ttu-id="80816-126">mm, m</span><span class="sxs-lookup"><span data-stu-id="80816-126">mm, m</span></span>|  
|<span data-ttu-id="80816-127">Dayofyear</span><span class="sxs-lookup"><span data-stu-id="80816-127">Dayofyear</span></span>|<span data-ttu-id="80816-128">dy, y</span><span class="sxs-lookup"><span data-stu-id="80816-128">dy, y</span></span>|  
|<span data-ttu-id="80816-129">Giorno</span><span class="sxs-lookup"><span data-stu-id="80816-129">Day</span></span>|<span data-ttu-id="80816-130">dd, d</span><span class="sxs-lookup"><span data-stu-id="80816-130">dd, d</span></span>|  
|<span data-ttu-id="80816-131">Week</span><span class="sxs-lookup"><span data-stu-id="80816-131">Week</span></span>|<span data-ttu-id="80816-132">wk, ww</span><span class="sxs-lookup"><span data-stu-id="80816-132">wk, ww</span></span>|  
|<span data-ttu-id="80816-133">Giorno della settimana</span><span class="sxs-lookup"><span data-stu-id="80816-133">Weekday</span></span>|<span data-ttu-id="80816-134">dw, w</span><span class="sxs-lookup"><span data-stu-id="80816-134">dw, w</span></span>|  
|<span data-ttu-id="80816-135">Ora</span><span class="sxs-lookup"><span data-stu-id="80816-135">Hour</span></span>|<span data-ttu-id="80816-136">Hh</span><span class="sxs-lookup"><span data-stu-id="80816-136">Hh</span></span>|  
|<span data-ttu-id="80816-137">Minuto</span><span class="sxs-lookup"><span data-stu-id="80816-137">Minute</span></span>|<span data-ttu-id="80816-138">mi, n</span><span class="sxs-lookup"><span data-stu-id="80816-138">mi, n</span></span>|  
|<span data-ttu-id="80816-139">Second</span><span class="sxs-lookup"><span data-stu-id="80816-139">Second</span></span>|<span data-ttu-id="80816-140">ss, s</span><span class="sxs-lookup"><span data-stu-id="80816-140">ss, s</span></span>|  
|<span data-ttu-id="80816-141">Millisecond</span><span class="sxs-lookup"><span data-stu-id="80816-141">Millisecond</span></span>|<span data-ttu-id="80816-142">Ms</span><span class="sxs-lookup"><span data-stu-id="80816-142">Ms</span></span>|  
  
 <span data-ttu-id="80816-143">L'argomento *number* deve essere disponibile al momento dell'analisi dell'espressione.</span><span class="sxs-lookup"><span data-stu-id="80816-143">The *number* argument must be available when the expression is parsed.</span></span> <span data-ttu-id="80816-144">Può essere una costante o una variabile.</span><span class="sxs-lookup"><span data-stu-id="80816-144">The argument can be a constant or a variable.</span></span> <span data-ttu-id="80816-145">Non è possibile utilizzare valori di colonna, perché tali valori non sono noti al momento dell'analisi dell'espressione.</span><span class="sxs-lookup"><span data-stu-id="80816-145">You cannot use column values because the values are not known when the expression is parsed.</span></span>  
  
 <span data-ttu-id="80816-146">L'argomento *datepart* deve essere racchiuso tra virgolette.</span><span class="sxs-lookup"><span data-stu-id="80816-146">The *datepart* argument must be enclosed by quotation marks.</span></span>  
  
 <span data-ttu-id="80816-147">Per i valori letterali di data è necessario eseguire il cast esplicito a uno dei tipi di dati date.</span><span class="sxs-lookup"><span data-stu-id="80816-147">A date literal must be explicitly cast to one of the date data types.</span></span> <span data-ttu-id="80816-148">Per altre informazioni, vedere [Tipi di dati di Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="80816-148">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="80816-149">Se l'argomento è Null, DATEADD restituirà Null.</span><span class="sxs-lookup"><span data-stu-id="80816-149">DATEADD returns a null result if the argument is null.</span></span>  
  
 <span data-ttu-id="80816-150">Se la data non è valida, l'unità di data o tempo non è una stringa oppure l'incremento non è un valore integer statico, verrà generato un errore.</span><span class="sxs-lookup"><span data-stu-id="80816-150">Errors occur if a date is invalid, if the date or time unit is not a string, or if the increment is not a static integer.</span></span>  
  
## <a name="ssis-expression-examples"></a><span data-ttu-id="80816-151">Esempi di espressione SSIS</span><span class="sxs-lookup"><span data-stu-id="80816-151">SSIS Expression Examples</span></span>  
 <span data-ttu-id="80816-152">In questo esempio viene aggiunto un mese alla data corrente.</span><span class="sxs-lookup"><span data-stu-id="80816-152">This example adds one month to the current date.</span></span>  
  
```  
DATEADD("Month", 1,GETDATE())  
```  
  
 <span data-ttu-id="80816-153">In questo esempio vengono aggiunti 21 giorni alle date nella colonna **ModifiedDate** .</span><span class="sxs-lookup"><span data-stu-id="80816-153">This example adds 21 days to the dates in the **ModifiedDate** column.</span></span>  
  
```  
DATEADD("day", 21, ModifiedDate)  
```  
  
 <span data-ttu-id="80816-154">In questo esempio vengono aggiunti 2 anni a un valore letterale data.</span><span class="sxs-lookup"><span data-stu-id="80816-154">This example adds 2 years to a literal date.</span></span>  
  
```  
DATEADD("yyyy", 2, (DT_DBTIMESTAMP)"8/6/2003")  
```  
  
## <a name="see-also"></a><span data-ttu-id="80816-155">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="80816-155">See Also</span></span>  
 <span data-ttu-id="80816-156">[DATEDIFF &#40;espressione SSIS&#41;](datediff-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="80816-156">[DATEDIFF &#40;SSIS Expression&#41;](datediff-ssis-expression.md) </span></span>  
 <span data-ttu-id="80816-157">[DATEPART &#40;espressione SSIS&#41;](datepart-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="80816-157">[DATEPART &#40;SSIS Expression&#41;](datepart-ssis-expression.md) </span></span>  
 <span data-ttu-id="80816-158">[DAY &#40;espressione SSIS&#41;](day-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="80816-158">[DAY &#40;SSIS Expression&#41;](day-ssis-expression.md) </span></span>  
 <span data-ttu-id="80816-159">[MONTH &#40;espressione SSIS&#41;](month-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="80816-159">[MONTH &#40;SSIS Expression&#41;](month-ssis-expression.md) </span></span>  
 <span data-ttu-id="80816-160">[YEAR &#40;espressione SSIS&#41;](year-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="80816-160">[YEAR &#40;SSIS Expression&#41;](year-ssis-expression.md) </span></span>  
 [<span data-ttu-id="80816-161">Funzioni &#40;espressione SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="80816-161">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
