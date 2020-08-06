---
title: MONTH (espressione SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- dates [Integration Services], MONTH
- MONTH function
ms.assetid: b5a47a11-c2ef-49bd-bd70-235632ff7bf6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d1f56906b4d25f2ba01f54fbdbc404d2c9ae4704
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627903"
---
# <a name="month-ssis-expression"></a><span data-ttu-id="582b0-102">MONTH (espressione SSIS)</span><span class="sxs-lookup"><span data-stu-id="582b0-102">MONTH (SSIS Expression)</span></span>
  <span data-ttu-id="582b0-103">Viene restituito un valore integer che rappresenta la parte corrispondente al mese di una data.</span><span class="sxs-lookup"><span data-stu-id="582b0-103">Returns an integer that represents the month datepart of a date.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="582b0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="582b0-104">Syntax</span></span>  
  
```  
  
MONTH(date)  
```  
  
## <a name="arguments"></a><span data-ttu-id="582b0-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="582b0-105">Arguments</span></span>  
 <span data-ttu-id="582b0-106">*date*</span><span class="sxs-lookup"><span data-stu-id="582b0-106">*date*</span></span>  
 <span data-ttu-id="582b0-107">Data in qualsiasi formato di data.</span><span class="sxs-lookup"><span data-stu-id="582b0-107">Is a date in any date format.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="582b0-108">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="582b0-108">Result Types</span></span>  
 <span data-ttu-id="582b0-109">DT_I4</span><span class="sxs-lookup"><span data-stu-id="582b0-109">DT_I4</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="582b0-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="582b0-110">Remarks</span></span>  
 <span data-ttu-id="582b0-111">Se l'argomento è Null, MONTH restituirà Null.</span><span class="sxs-lookup"><span data-stu-id="582b0-111">MONTH returns a null result if the argument is null.</span></span>  
  
 <span data-ttu-id="582b0-112">Per i valori letterali di data è necessario eseguire il cast esplicito a uno dei tipi di dati date.</span><span class="sxs-lookup"><span data-stu-id="582b0-112">A date literal must be explicitly cast to one of the date data types.</span></span> <span data-ttu-id="582b0-113">Per altre informazioni, vedere [Tipi di dati di Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="582b0-113">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="582b0-114">La convalida dell'espressione non riesce quando viene eseguito il cast esplicito di un valore letterale di data a uno di questi tipi di dati relativi alle date: DT_DBTIMESTAMPOFFSET e DT_DBTIMESTAMP2.</span><span class="sxs-lookup"><span data-stu-id="582b0-114">The expression fails to validate when a date literal is explicitly cast to one of these date data types: DT_DBTIMESTAMPOFFSET and DT_DBTIMESTAMP2.</span></span>  
  
 <span data-ttu-id="582b0-115">La funzione MONTH costituisce una forma più breve, ma equivalente, della funzione DATEPART("Month", date).</span><span class="sxs-lookup"><span data-stu-id="582b0-115">Using the MONTH function is briefer but equivalent to using DATEPART("Month", date).</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="582b0-116">Esempi di espressione</span><span class="sxs-lookup"><span data-stu-id="582b0-116">Expression Examples</span></span>  
 <span data-ttu-id="582b0-117">In questo esempio viene restituito il numero del mese in un valore letterale di data.</span><span class="sxs-lookup"><span data-stu-id="582b0-117">This example returns the number of the month in a date literal.</span></span> <span data-ttu-id="582b0-118">Se la data è in formato "mm/gg/aaaa", l'esempio restituirà 11.</span><span class="sxs-lookup"><span data-stu-id="582b0-118">If the date is in "mm/dd/yyyy" format, this example returns 11.</span></span>  
  
```  
MONTH((DT_DBTIMESTAMP)"11/23/2002")  
```  
  
 <span data-ttu-id="582b0-119">In questo esempio viene restituito un Integer che rappresenta il mese nella colonna **ModifiedDate** .</span><span class="sxs-lookup"><span data-stu-id="582b0-119">This example returns the integer that represents the month in the **ModifiedDate** column.</span></span>  
  
```  
MONTH(ModifiedDate)  
```  
  
 <span data-ttu-id="582b0-120">In questo esempio viene restituito un valore integer che rappresenta il mese nella data corrente.</span><span class="sxs-lookup"><span data-stu-id="582b0-120">This example returns the integer that represents the month of the current date.</span></span>  
  
```  
MONTH(GETDATE())  
```  
  
## <a name="see-also"></a><span data-ttu-id="582b0-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="582b0-121">See Also</span></span>  
 <span data-ttu-id="582b0-122">[DATEADD &#40;espressione SSIS&#41;](dateadd-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="582b0-122">[DATEADD &#40;SSIS Expression&#41;](dateadd-ssis-expression.md) </span></span>  
 <span data-ttu-id="582b0-123">[DATEDIFF &#40;espressione SSIS&#41;](datediff-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="582b0-123">[DATEDIFF &#40;SSIS Expression&#41;](datediff-ssis-expression.md) </span></span>  
 <span data-ttu-id="582b0-124">[DATEPART &#40;espressione SSIS&#41;](datepart-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="582b0-124">[DATEPART &#40;SSIS Expression&#41;](datepart-ssis-expression.md) </span></span>  
 <span data-ttu-id="582b0-125">[DAY &#40;espressione SSIS&#41;](day-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="582b0-125">[DAY &#40;SSIS Expression&#41;](day-ssis-expression.md) </span></span>  
 <span data-ttu-id="582b0-126">[YEAR &#40;espressione SSIS&#41;](year-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="582b0-126">[YEAR &#40;SSIS Expression&#41;](year-ssis-expression.md) </span></span>  
 [<span data-ttu-id="582b0-127">Funzioni &#40;espressione SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="582b0-127">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
