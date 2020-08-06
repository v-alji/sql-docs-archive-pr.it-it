---
title: YEAR (espressione SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- dates [Integration Services], YEAR
- YEAR function
ms.assetid: 9d88dead-ace8-44b9-b8e2-916c1842e155
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 181375d489fbf7abf0718386efacf4167ba555d7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635710"
---
# <a name="year-ssis-expression"></a><span data-ttu-id="afe7b-102">YEAR (espressione SSIS)</span><span class="sxs-lookup"><span data-stu-id="afe7b-102">YEAR (SSIS Expression)</span></span>
  <span data-ttu-id="afe7b-103">Viene restituito un valore integer che rappresenta la parte corrispondente all'anno di una data.</span><span class="sxs-lookup"><span data-stu-id="afe7b-103">Returns an integer that represents the year datepart of a date.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="afe7b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="afe7b-104">Syntax</span></span>  
  
```  
  
YEAR(date)  
```  
  
## <a name="arguments"></a><span data-ttu-id="afe7b-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="afe7b-105">Arguments</span></span>  
 <span data-ttu-id="afe7b-106">*date*</span><span class="sxs-lookup"><span data-stu-id="afe7b-106">*date*</span></span>  
 <span data-ttu-id="afe7b-107">Data in qualsiasi formato di data.</span><span class="sxs-lookup"><span data-stu-id="afe7b-107">Is a date in any date format.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="afe7b-108">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="afe7b-108">Result Types</span></span>  
 <span data-ttu-id="afe7b-109">DT_I4</span><span class="sxs-lookup"><span data-stu-id="afe7b-109">DT_I4</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="afe7b-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="afe7b-110">Remarks</span></span>  
 <span data-ttu-id="afe7b-111">Se l'argomento è Null, YEAR restituirà Null.</span><span class="sxs-lookup"><span data-stu-id="afe7b-111">YEAR returns a null result if the argument is null.</span></span>  
  
 <span data-ttu-id="afe7b-112">Per i valori letterali di data è necessario eseguire il cast esplicito a uno dei tipi di dati date.</span><span class="sxs-lookup"><span data-stu-id="afe7b-112">A date literal must be explicitly cast to one of the date data types.</span></span> <span data-ttu-id="afe7b-113">Per altre informazioni, vedere [Tipi di dati di Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="afe7b-113">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="afe7b-114">La convalida dell'espressione non riesce quando viene eseguito il cast esplicito di un valore letterale di data a uno di questi tipi di dati relativi alle date: DT_DBTIMESTAMPOFFSET e DT_DBTIMESTAMP2.</span><span class="sxs-lookup"><span data-stu-id="afe7b-114">The expression fails to validate when a date literal is explicitly cast to one of these date data types: DT_DBTIMESTAMPOFFSET and DT_DBTIMESTAMP2.</span></span>  
  
 <span data-ttu-id="afe7b-115">La funzione YEAR costituisce una forma più breve, ma equivalente, della funzione DATEPART("Year", date).</span><span class="sxs-lookup"><span data-stu-id="afe7b-115">Using the YEAR function is briefer but equivalent to using the DATEPART("Year", date) function.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="afe7b-116">Esempi di espressione</span><span class="sxs-lookup"><span data-stu-id="afe7b-116">Expression Examples</span></span>  
 <span data-ttu-id="afe7b-117">In questo esempio viene restituito il numero dell'anno in un valore letterale di data.</span><span class="sxs-lookup"><span data-stu-id="afe7b-117">This example returns the number of the year in a date literal.</span></span> <span data-ttu-id="afe7b-118">Se la data è in formato mm/gg/aaaa, l'esempio restituirà "2002".</span><span class="sxs-lookup"><span data-stu-id="afe7b-118">If the date is in mm/dd/yyyy format, this example returns "2002".</span></span>  
  
```  
YEAR((DT_DBTIMESTAMP)"11/23/2002")  
```  
  
 <span data-ttu-id="afe7b-119">In questo esempio viene restituito un Integer che rappresenta l'anno nella colonna **ModifiedDate** .</span><span class="sxs-lookup"><span data-stu-id="afe7b-119">This example returns the integer that represents the year in the **ModifiedDate** column.</span></span>  
  
```  
YEAR(ModifiedDate)  
```  
  
 <span data-ttu-id="afe7b-120">In questo esempio viene restituito un valore integer che rappresenta l'anno nella data corrente.</span><span class="sxs-lookup"><span data-stu-id="afe7b-120">This example returns the integer that represents the year of the current date.</span></span>  
  
```  
YEAR(GETDATE())  
```  
  
## <a name="see-also"></a><span data-ttu-id="afe7b-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="afe7b-121">See Also</span></span>  
 <span data-ttu-id="afe7b-122">[DATEADD &#40;espressione SSIS&#41;](dateadd-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="afe7b-122">[DATEADD &#40;SSIS Expression&#41;](dateadd-ssis-expression.md) </span></span>  
 <span data-ttu-id="afe7b-123">[DATEDIFF &#40;espressione SSIS&#41;](datediff-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="afe7b-123">[DATEDIFF &#40;SSIS Expression&#41;](datediff-ssis-expression.md) </span></span>  
 <span data-ttu-id="afe7b-124">[DATEPART &#40;espressione SSIS&#41;](datepart-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="afe7b-124">[DATEPART &#40;SSIS Expression&#41;](datepart-ssis-expression.md) </span></span>  
 <span data-ttu-id="afe7b-125">[DAY &#40;espressione SSIS&#41;](day-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="afe7b-125">[DAY &#40;SSIS Expression&#41;](day-ssis-expression.md) </span></span>  
 <span data-ttu-id="afe7b-126">[MONTH &#40;espressione SSIS&#41;](month-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="afe7b-126">[MONTH &#40;SSIS Expression&#41;](month-ssis-expression.md) </span></span>  
 [<span data-ttu-id="afe7b-127">Funzioni &#40;espressione SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="afe7b-127">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
