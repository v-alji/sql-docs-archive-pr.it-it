---
title: ISNULL (espressione SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- null values [Integration Services]
- ISNULL function
ms.assetid: 88dbf49e-1307-4dda-b9db-ff1632053550
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 51eda21b5c9b85c5f9cfd613d0d92df9729fe620
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716508"
---
# <a name="isnull-ssis-expression"></a><span data-ttu-id="e25cf-102">ISNULL (espressione SSIS)</span><span class="sxs-lookup"><span data-stu-id="e25cf-102">ISNULL (SSIS Expression)</span></span>
  <span data-ttu-id="e25cf-103">Restituisce un risultato booleano che varia a seconda che un'espressione abbia o meno un valore Null.</span><span class="sxs-lookup"><span data-stu-id="e25cf-103">Returns a Boolean result based on whether an expression is null.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e25cf-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e25cf-104">Syntax</span></span>  
  
```  
  
ISNULL(expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="e25cf-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="e25cf-105">Arguments</span></span>  
 <span data-ttu-id="e25cf-106">*expression*</span><span class="sxs-lookup"><span data-stu-id="e25cf-106">*expression*</span></span>  
 <span data-ttu-id="e25cf-107">Espressione valida con qualsiasi tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="e25cf-107">Is a valid expression of any data type.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="e25cf-108">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="e25cf-108">Result Types</span></span>  
 <span data-ttu-id="e25cf-109">DT_BOOL</span><span class="sxs-lookup"><span data-stu-id="e25cf-109">DT_BOOL</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="e25cf-110">Esempi di espressione</span><span class="sxs-lookup"><span data-stu-id="e25cf-110">Expression Examples</span></span>  
 <span data-ttu-id="e25cf-111">In questo esempio viene restituito TRUE se nella colonna **DiscontinuedDate** è contenuto un valore Null.</span><span class="sxs-lookup"><span data-stu-id="e25cf-111">This example returns TRUE if the **DiscontinuedDate** column contains a null value.</span></span>  
  
```  
ISNULL(DiscontinuedDate)  
```  
  
 <span data-ttu-id="e25cf-112">In questo esempio viene restituito il testo "Unknown last name" se il valore nella colonna **LastName** è Null, in caso contrario viene restituito il valore in **LastName**.</span><span class="sxs-lookup"><span data-stu-id="e25cf-112">This example returns "Unknown last name" if the value in the **LastName** column is null, otherwise it returns the value in **LastName**.</span></span>  
  
```  
ISNULL(LastName)? "Unknown last name":LastName  
```  
  
 <span data-ttu-id="e25cf-113">In questo esempio se la colonna **DaysToManufacture** ha valore Null, verrà sempre restituito TRUE indipendentemente dal valore della variabile **AddDays**.</span><span class="sxs-lookup"><span data-stu-id="e25cf-113">This example always returns TRUE if the **DaysToManufacture** column is null, regardless of the value of the variable **AddDays**.</span></span>  
  
```  
ISNULL(DaysToManufacture + @AddDays)  
```  
  
## <a name="see-also"></a><span data-ttu-id="e25cf-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e25cf-114">See Also</span></span>  
 <span data-ttu-id="e25cf-115">[Funzioni &#40;espressione SSIS&#41;](functions-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="e25cf-115">[Functions &#40;SSIS Expression&#41;](functions-ssis-expression.md) </span></span>  
 [<span data-ttu-id="e25cf-116">COALESCE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e25cf-116">COALESCE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/coalesce-transact-sql)  
  
  
