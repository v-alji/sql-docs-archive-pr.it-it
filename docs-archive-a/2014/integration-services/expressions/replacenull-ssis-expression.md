---
title: REPLACENULL (espressione SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 70db7832-b5a0-4db5-a8ad-42ad8630d8e8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f10bb6ef6102076fe7b1cc236461e2358ad96372
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716500"
---
# <a name="replacenull-ssis-expression"></a><span data-ttu-id="c1a6e-102">REPLACENULL (espressione SSIS)</span><span class="sxs-lookup"><span data-stu-id="c1a6e-102">REPLACENULL (SSIS Expression)</span></span>
  <span data-ttu-id="c1a6e-103">Restituisce il valore del parametro della seconda espressione se il valore del parametro della prima è NULL. In caso contrario, restituisce il valore della prima espressione.</span><span class="sxs-lookup"><span data-stu-id="c1a6e-103">Returns the value of second expression parameter if the value of first expression parameter is NULL; otherwise, returns the value of first expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1a6e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c1a6e-104">Syntax</span></span>  
  
```vb  
REPLACENULL(expression 1,expression 2)  
```  
  
## <a name="arguments"></a><span data-ttu-id="c1a6e-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="c1a6e-105">Arguments</span></span>  
 <span data-ttu-id="c1a6e-106">*expression 1*</span><span class="sxs-lookup"><span data-stu-id="c1a6e-106">*expression 1*</span></span>  
 <span data-ttu-id="c1a6e-107">Il risultato di questa espressione viene verificato rispetto a NULL.</span><span class="sxs-lookup"><span data-stu-id="c1a6e-107">The result of this expression is checked against NULL.</span></span>  
  
 <span data-ttu-id="c1a6e-108">*expression 2*</span><span class="sxs-lookup"><span data-stu-id="c1a6e-108">*expression 2*</span></span>  
 <span data-ttu-id="c1a6e-109">Il risultato di questa espressione viene restituito se la prima espressione restituisce NULL.</span><span class="sxs-lookup"><span data-stu-id="c1a6e-109">The result of this expression is returned if the first expression evaluates to NULL.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="c1a6e-110">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="c1a6e-110">Result Types</span></span>  
 <span data-ttu-id="c1a6e-111">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="c1a6e-111">DT_WSTR</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c1a6e-112">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="c1a6e-112">Remarks</span></span>  
  
-   <span data-ttu-id="c1a6e-113">La lunghezza di *expression 2* può essere zero.</span><span class="sxs-lookup"><span data-stu-id="c1a6e-113">The length of *expression 2* may be zero.</span></span>  
  
-   <span data-ttu-id="c1a6e-114">REPLACENULL restituisce un risultato Null se un argomento è Null.</span><span class="sxs-lookup"><span data-stu-id="c1a6e-114">REPLACENULL returns a null result if any argument is null.</span></span>  
  
-   <span data-ttu-id="c1a6e-115">Le colonne BLOB (DT_TEXT, DT_NTEXT, DT_IMAGE) non sono supportate per nessun parametro.</span><span class="sxs-lookup"><span data-stu-id="c1a6e-115">BLOB columns (DT_TEXT, DT_NTEXT, DT_IMAGE) are not supported for either parameter.</span></span>  
  
-   <span data-ttu-id="c1a6e-116">Le due espressioni devono avere lo stesso tipo restituito.</span><span class="sxs-lookup"><span data-stu-id="c1a6e-116">The two expressions are expected to have the same return type.</span></span> <span data-ttu-id="c1a6e-117">In caso contrario, la funzione tenta di eseguire il cast della seconda espressione al tipo restituito della prima espressione, cosa che potrebbe generare un errore se i tipi di dati non sono compatibili.</span><span class="sxs-lookup"><span data-stu-id="c1a6e-117">If they do not, the function attempts to cast the 2nd expression to the return type of the 1st expression, which may result in an error if the data types are incompatible.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="c1a6e-118">Esempi di espressione</span><span class="sxs-lookup"><span data-stu-id="c1a6e-118">Expression Examples</span></span>  
 <span data-ttu-id="c1a6e-119">Nell'esempio seguente qualsiasi valore NULL in una colonna del database viene sostituito con una stringa (1900-01-01).</span><span class="sxs-lookup"><span data-stu-id="c1a6e-119">The following example replaces any NULL value in a database column with a string (1900-01-01).</span></span> <span data-ttu-id="c1a6e-120">Questa funzione viene soprattutto utilizzata nei modelli comuni di colonna derivata in cui si desidera restituire i valori NULL con altri valori.</span><span class="sxs-lookup"><span data-stu-id="c1a6e-120">This function is especially used in common Derived Column patterns where you want to replace NULL values with something else.</span></span>  
  
```  
REPLACENULL(MyColumn, "1900-01-01")  
```  
  
> [!NOTE]  
>  <span data-ttu-id="c1a6e-121">Nell'esempio seguente viene illustrato come questa operazione veniva eseguita in [!INCLUDE[ssISversion2005](../../includes/ssisversion2005-md.md)]/[!INCLUDE[ssISversion10](../../includes/ssisversion10-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c1a6e-121">The following example shows how it was done in [!INCLUDE[ssISversion2005](../../includes/ssisversion2005-md.md)]/[!INCLUDE[ssISversion10](../../includes/ssisversion10-md.md)].</span></span>  
  
```  
(DT_DBTIMESTAMP) (ISNULL(MyColumn) ? "1900-01-01" : MyColumn)   
```  
  
  
