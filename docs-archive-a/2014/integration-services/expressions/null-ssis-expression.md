---
title: NULL (espressione SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- NULL function
- null values [Integration Services]
ms.assetid: df144237-3fbb-41ac-8624-efd92b6522b9
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e14cd51b4e245ca6984a4c62eae2b9d5536ab1f4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624264"
---
# <a name="null-ssis-expression"></a><span data-ttu-id="032e2-102">NULL (espressione SSIS)</span><span class="sxs-lookup"><span data-stu-id="032e2-102">NULL (SSIS Expression)</span></span>
  <span data-ttu-id="032e2-103">Restituisce un valore Null di un tipo di dati richiesto.</span><span class="sxs-lookup"><span data-stu-id="032e2-103">Returns a null value of a requested data type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="032e2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="032e2-104">Syntax</span></span>  
  
```  
  
NULL(typespec)  
```  
  
## <a name="arguments"></a><span data-ttu-id="032e2-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="032e2-105">Arguments</span></span>  
 <span data-ttu-id="032e2-106">*typespec*</span><span class="sxs-lookup"><span data-stu-id="032e2-106">*typespec*</span></span>  
 <span data-ttu-id="032e2-107">Tipo di dati valido.</span><span class="sxs-lookup"><span data-stu-id="032e2-107">Is a valid data type.</span></span> <span data-ttu-id="032e2-108">Per altre informazioni, vedere [Tipi di dati di Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="032e2-108">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="032e2-109">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="032e2-109">Result Types</span></span>  
 <span data-ttu-id="032e2-110">Qualsiasi tipo di dati valido con valore Null.</span><span class="sxs-lookup"><span data-stu-id="032e2-110">Any valid data type with a null value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="032e2-111">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="032e2-111">Remarks</span></span>  
 <span data-ttu-id="032e2-112">Se l'argomento è Null, NULL restituirà Null.</span><span class="sxs-lookup"><span data-stu-id="032e2-112">NULL returns a null result if the argument is null.</span></span>  
  
 <span data-ttu-id="032e2-113">Per ottenere un valore Null per determinati tipi di dati, è necessario specificare i parametri appropriati.</span><span class="sxs-lookup"><span data-stu-id="032e2-113">Parameters are required to request a null value for some data types.</span></span> <span data-ttu-id="032e2-114">Nella tabella seguente vengono elencati tali tipi di dati e i parametri corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="032e2-114">The following table lists these data types and their parameters.</span></span>  
  
|<span data-ttu-id="032e2-115">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="032e2-115">Data type</span></span>|<span data-ttu-id="032e2-116">Parametro</span><span class="sxs-lookup"><span data-stu-id="032e2-116">Parameter</span></span>|<span data-ttu-id="032e2-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="032e2-117">Example</span></span>|  
|---------------|---------------|-------------|  
|<span data-ttu-id="032e2-118">DT_STR</span><span class="sxs-lookup"><span data-stu-id="032e2-118">DT_STR</span></span>|<span data-ttu-id="032e2-119">*charcount*</span><span class="sxs-lookup"><span data-stu-id="032e2-119">*charcount*</span></span><br /><br /> <span data-ttu-id="032e2-120">*codepage*</span><span class="sxs-lookup"><span data-stu-id="032e2-120">*codepage*</span></span>|<span data-ttu-id="032e2-121">(DT_STR,30,1252): esegue il cast di 30 caratteri al tipo di dati DT_STR utilizzando la tabella codici 1252.</span><span class="sxs-lookup"><span data-stu-id="032e2-121">(DT_STR,30,1252) casts 30 characters to the DT_STR data type using the 1252 code page.</span></span>|  
|<span data-ttu-id="032e2-122">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="032e2-122">DT_WSTR</span></span>|<span data-ttu-id="032e2-123">*charcount*</span><span class="sxs-lookup"><span data-stu-id="032e2-123">*charcount*</span></span>|<span data-ttu-id="032e2-124">(DT_WSTR,20): esegue il cast di 20 caratteri al tipo di dati DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="032e2-124">(DT_WSTR,20) casts 20 characters to the DT_WSTR data type.</span></span>|  
|<span data-ttu-id="032e2-125">DT_BYTES</span><span class="sxs-lookup"><span data-stu-id="032e2-125">DT_BYTES</span></span>|<span data-ttu-id="032e2-126">*bytecount*</span><span class="sxs-lookup"><span data-stu-id="032e2-126">*bytecount*</span></span>|<span data-ttu-id="032e2-127">(DT_BYTES,50): esegue il cast di 50 byte al tipo di dati DT_BYTES.</span><span class="sxs-lookup"><span data-stu-id="032e2-127">(DT_BYTES,50) casts 50 bytes to the DT_BYTES data type.</span></span>|  
|<span data-ttu-id="032e2-128">DT_DECIMAL</span><span class="sxs-lookup"><span data-stu-id="032e2-128">DT_DECIMAL</span></span>|<span data-ttu-id="032e2-129">*scale*</span><span class="sxs-lookup"><span data-stu-id="032e2-129">*scale*</span></span>|<span data-ttu-id="032e2-130">(DT_DECIMAL,2): esegue il cast di un valore numerico al tipo di dati DT_DECIMAL, utilizzando una scala pari a 2.</span><span class="sxs-lookup"><span data-stu-id="032e2-130">(DT_DECIMAL,2) casts a numeric value to the DT_DECIMAL data type using a scale of 2.</span></span>|  
|<span data-ttu-id="032e2-131">DT_NUMERIC</span><span class="sxs-lookup"><span data-stu-id="032e2-131">DT_NUMERIC</span></span>|<span data-ttu-id="032e2-132">*precisione*</span><span class="sxs-lookup"><span data-stu-id="032e2-132">*precision*</span></span><br /><br /> <span data-ttu-id="032e2-133">*scale*</span><span class="sxs-lookup"><span data-stu-id="032e2-133">*scale*</span></span>|<span data-ttu-id="032e2-134">(DT_NUMERIC,10,3): esegue il cast di un valore numerico al tipo di dati DT_NUMERIC, utilizzando una precisione pari a 10 e una scala pari a 3.</span><span class="sxs-lookup"><span data-stu-id="032e2-134">(DT_NUMERIC,10,3) casts a numeric value to the DT_NUMERIC data type using a precision of 10 and a scale of 3.</span></span>|  
|<span data-ttu-id="032e2-135">DT_TEXT</span><span class="sxs-lookup"><span data-stu-id="032e2-135">DT_TEXT</span></span>|<span data-ttu-id="032e2-136">*codepage*</span><span class="sxs-lookup"><span data-stu-id="032e2-136">*codepage*</span></span>|<span data-ttu-id="032e2-137">(DT_TEXT,1252): esegue il cast di un valore al tipo di dati DT_TEXT utilizzando la tabella codici 1252.</span><span class="sxs-lookup"><span data-stu-id="032e2-137">(DT_TEXT,1252) casts a value to the DT_TEXT data type using the 1252 code page.</span></span>|  
  
## <a name="expression-examples"></a><span data-ttu-id="032e2-138">Esempi di espressione</span><span class="sxs-lookup"><span data-stu-id="032e2-138">Expression Examples</span></span>  
 <span data-ttu-id="032e2-139">In questi esempi viene restituito il valore Null per i tipi di dati DT_STR, DT_DATE e DT_BOOL.</span><span class="sxs-lookup"><span data-stu-id="032e2-139">These examples return the null value of the data types: DT_STR, DT_DATE, and DT_BOOL.</span></span>  
  
```  
NULL(DT_STR,10,1252)  
NULL(DT_DATE)  
NULL(DT_BOOL)  
```  
  
## <a name="see-also"></a><span data-ttu-id="032e2-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="032e2-140">See Also</span></span>  
 <span data-ttu-id="032e2-141">[ISNULL &#40;espressione SSIS&#41;](null-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="032e2-141">[ISNULL &#40;SSIS Expression&#41;](null-ssis-expression.md) </span></span>  
 [<span data-ttu-id="032e2-142">Funzioni &#40;espressione SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="032e2-142">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
