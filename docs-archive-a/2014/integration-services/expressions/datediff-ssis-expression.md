---
title: DATEDIFF (espressione SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- DATEDIFF statement
- dates [Integration Services], DATEDIFF
ms.assetid: 449b327f-47c7-4709-8bc6-4ee9a35cc330
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 33edf2a152f70bb8c5bbd1f69cb87354e099b246
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715600"
---
# <a name="datediff-ssis-expression"></a><span data-ttu-id="629ee-102">DATEDIFF (espressione SSIS)</span><span class="sxs-lookup"><span data-stu-id="629ee-102">DATEDIFF (SSIS Expression)</span></span>
  <span data-ttu-id="629ee-103">Restituisce il numero di unità di data e ora trascorse tra due date specificate.</span><span class="sxs-lookup"><span data-stu-id="629ee-103">Returns the number of date and time boundaries crossed between two specified dates.</span></span> <span data-ttu-id="629ee-104">Il parametro *datepart* identifica i limiti di data e ora da confrontare.</span><span class="sxs-lookup"><span data-stu-id="629ee-104">The *datepart* parameter identifies which date and time boundaries to compare.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="629ee-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="629ee-105">Syntax</span></span>  
  
```  
  
DATEDIFF(datepart, startdate, endate)  
```  
  
## <a name="arguments"></a><span data-ttu-id="629ee-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="629ee-106">Arguments</span></span>  
 <span data-ttu-id="629ee-107">*datepart*</span><span class="sxs-lookup"><span data-stu-id="629ee-107">*datepart*</span></span>  
 <span data-ttu-id="629ee-108">Parametro che specifica per quale parte della data si desidera eseguire il confronto e restituire un valore.</span><span class="sxs-lookup"><span data-stu-id="629ee-108">Is the parameter that specifies which part of the date to compare and return a value for.</span></span>  
  
 <span data-ttu-id="629ee-109">*startdate*</span><span class="sxs-lookup"><span data-stu-id="629ee-109">*startdate*</span></span>  
 <span data-ttu-id="629ee-110">Data di inizio dell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="629ee-110">Is the start date of the interval.</span></span>  
  
 <span data-ttu-id="629ee-111">*endate*</span><span class="sxs-lookup"><span data-stu-id="629ee-111">*endate*</span></span>  
 <span data-ttu-id="629ee-112">Data di fine dell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="629ee-112">Is the end date of the interval.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="629ee-113">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="629ee-113">Result Types</span></span>  
 <span data-ttu-id="629ee-114">DT_I4</span><span class="sxs-lookup"><span data-stu-id="629ee-114">DT_I4</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="629ee-115">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="629ee-115">Remarks</span></span>  
 <span data-ttu-id="629ee-116">Nella tabella seguente sono elencate le parti della data e le abbreviazioni riconosciute dall'analizzatore di espressioni.</span><span class="sxs-lookup"><span data-stu-id="629ee-116">The following table lists the dateparts and abbreviations recognized by the expression evaluator.</span></span>  
  
|<span data-ttu-id="629ee-117">parte di una data</span><span class="sxs-lookup"><span data-stu-id="629ee-117">Datepart</span></span>|<span data-ttu-id="629ee-118">Abbreviazioni</span><span class="sxs-lookup"><span data-stu-id="629ee-118">Abbreviations</span></span>|  
|--------------|-------------------|  
|<span data-ttu-id="629ee-119">Year</span><span class="sxs-lookup"><span data-stu-id="629ee-119">Year</span></span>|<span data-ttu-id="629ee-120">yy, yyyy</span><span class="sxs-lookup"><span data-stu-id="629ee-120">yy, yyyy</span></span>|  
|<span data-ttu-id="629ee-121">Quarter</span><span class="sxs-lookup"><span data-stu-id="629ee-121">Quarter</span></span>|<span data-ttu-id="629ee-122">qq, q</span><span class="sxs-lookup"><span data-stu-id="629ee-122">qq, q</span></span>|  
|<span data-ttu-id="629ee-123">Month</span><span class="sxs-lookup"><span data-stu-id="629ee-123">Month</span></span>|<span data-ttu-id="629ee-124">mm, m</span><span class="sxs-lookup"><span data-stu-id="629ee-124">mm, m</span></span>|  
|<span data-ttu-id="629ee-125">Dayofyear</span><span class="sxs-lookup"><span data-stu-id="629ee-125">Dayofyear</span></span>|<span data-ttu-id="629ee-126">dy, y</span><span class="sxs-lookup"><span data-stu-id="629ee-126">dy, y</span></span>|  
|<span data-ttu-id="629ee-127">Giorno</span><span class="sxs-lookup"><span data-stu-id="629ee-127">Day</span></span>|<span data-ttu-id="629ee-128">dd, d</span><span class="sxs-lookup"><span data-stu-id="629ee-128">dd, d</span></span>|  
|<span data-ttu-id="629ee-129">Week</span><span class="sxs-lookup"><span data-stu-id="629ee-129">Week</span></span>|<span data-ttu-id="629ee-130">wk, ww</span><span class="sxs-lookup"><span data-stu-id="629ee-130">wk, ww</span></span>|  
|<span data-ttu-id="629ee-131">Giorno della settimana</span><span class="sxs-lookup"><span data-stu-id="629ee-131">Weekday</span></span>|<span data-ttu-id="629ee-132">dw, w</span><span class="sxs-lookup"><span data-stu-id="629ee-132">dw, w</span></span>|  
|<span data-ttu-id="629ee-133">Ora</span><span class="sxs-lookup"><span data-stu-id="629ee-133">Hour</span></span>|<span data-ttu-id="629ee-134">Hh</span><span class="sxs-lookup"><span data-stu-id="629ee-134">Hh</span></span>|  
|<span data-ttu-id="629ee-135">Minuto</span><span class="sxs-lookup"><span data-stu-id="629ee-135">Minute</span></span>|<span data-ttu-id="629ee-136">mi, n</span><span class="sxs-lookup"><span data-stu-id="629ee-136">mi, n</span></span>|  
|<span data-ttu-id="629ee-137">Second</span><span class="sxs-lookup"><span data-stu-id="629ee-137">Second</span></span>|<span data-ttu-id="629ee-138">ss, s</span><span class="sxs-lookup"><span data-stu-id="629ee-138">ss, s</span></span>|  
|<span data-ttu-id="629ee-139">Millisecond</span><span class="sxs-lookup"><span data-stu-id="629ee-139">Millisecond</span></span>|<span data-ttu-id="629ee-140">Ms</span><span class="sxs-lookup"><span data-stu-id="629ee-140">Ms</span></span>|  
  
 <span data-ttu-id="629ee-141">Se un argomento qualsiasi è Null, DATEDIFF restituirà Null.</span><span class="sxs-lookup"><span data-stu-id="629ee-141">DATEDIFF returns a null result if any argument is null.</span></span>  
  
 <span data-ttu-id="629ee-142">Per i valori letterali di data è necessario eseguire il cast esplicito a uno dei tipi di dati date.</span><span class="sxs-lookup"><span data-stu-id="629ee-142">A date literal must be explicitly cast to one of the date data types.</span></span> <span data-ttu-id="629ee-143">Per altre informazioni, vedere [Tipi di dati di Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="629ee-143">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="629ee-144">Se la data non è valida, l'ora o la data non è una stringa oppure la data di inizio o fine non è una data, verrà generato un errore.</span><span class="sxs-lookup"><span data-stu-id="629ee-144">An error occurs if a date is not valid, if the date or time unit is not a string, if the start date is not a date, or if the end date is not a date.</span></span>  
  
 <span data-ttu-id="629ee-145">Se la data di fine è anteriore a quella di inizio, la funzione restituirà un numero negativo.</span><span class="sxs-lookup"><span data-stu-id="629ee-145">If the end date is earlier than the start date, the function returns a negative number.</span></span> <span data-ttu-id="629ee-146">Se le date di inizio e di fine coincidono o rientrano nello stesso intervallo, la funzione restituirà zero.</span><span class="sxs-lookup"><span data-stu-id="629ee-146">If the start and end dates are equal or fall within the same interval, the function returns zero.</span></span>  
  
## <a name="ssis-expression-examples"></a><span data-ttu-id="629ee-147">Esempi di espressione SSIS</span><span class="sxs-lookup"><span data-stu-id="629ee-147">SSIS Expression Examples</span></span>  
 <span data-ttu-id="629ee-148">In questo esempio viene calcolato il numero dei giorni tra due valori letterali di data.</span><span class="sxs-lookup"><span data-stu-id="629ee-148">This example calculates the number of days between two date literals.</span></span> <span data-ttu-id="629ee-149">Se la data è in formato "mm/gg/aaaa", la funzione restituirà 7.</span><span class="sxs-lookup"><span data-stu-id="629ee-149">If the date is in "mm/dd/yyyy" format, the function returns 7.</span></span>  
  
```  
DATEDIFF("dd", (DT_DBTIMESTAMP)"8/1/2003", (DT_DBTIMESTAMP)"8/8/2003")  
```  
  
 <span data-ttu-id="629ee-150">In questo esempio viene restituito il numero dei mesi tra un valore letterale data e la data corrente.</span><span class="sxs-lookup"><span data-stu-id="629ee-150">This example returns the number of months between a date literal and the current date.</span></span>  
  
```  
DATEDIFF("mm", (DT_DBTIMESTAMP)"8/1/2003",GETDATE())  
```  
  
 <span data-ttu-id="629ee-151">In questo esempio viene restituito il numero delle settimane tra la data nella colonna **ModifiedDate** e quella nella variabile **YearEndDate** .</span><span class="sxs-lookup"><span data-stu-id="629ee-151">This example returns the number of weeks between the date in the **ModifiedDate** column and the **YearEndDate** variable.</span></span> <span data-ttu-id="629ee-152">Se **YearEndDate** ha un `date` tipo di dati, non è necessario alcun cast esplicito.</span><span class="sxs-lookup"><span data-stu-id="629ee-152">If **YearEndDate** has a `date` data type, no explicit casting is required.</span></span>  
  
```  
DATEDIFF("Week", ModifiedDate,@YearEndDate)  
```  
  
## <a name="see-also"></a><span data-ttu-id="629ee-153">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="629ee-153">See Also</span></span>  
 <span data-ttu-id="629ee-154">[DATEADD &#40;espressione SSIS&#41;](dateadd-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="629ee-154">[DATEADD &#40;SSIS Expression&#41;](dateadd-ssis-expression.md) </span></span>  
 <span data-ttu-id="629ee-155">[DATEPART &#40;espressione SSIS&#41;](datepart-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="629ee-155">[DATEPART &#40;SSIS Expression&#41;](datepart-ssis-expression.md) </span></span>  
 <span data-ttu-id="629ee-156">[DAY &#40;espressione SSIS&#41;](day-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="629ee-156">[DAY &#40;SSIS Expression&#41;](day-ssis-expression.md) </span></span>  
 <span data-ttu-id="629ee-157">[MONTH &#40;espressione SSIS&#41;](month-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="629ee-157">[MONTH &#40;SSIS Expression&#41;](month-ssis-expression.md) </span></span>  
 <span data-ttu-id="629ee-158">[YEAR &#40;espressione SSIS&#41;](year-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="629ee-158">[YEAR &#40;SSIS Expression&#41;](year-ssis-expression.md) </span></span>  
 [<span data-ttu-id="629ee-159">Funzioni &#40;espressione SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="629ee-159">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
