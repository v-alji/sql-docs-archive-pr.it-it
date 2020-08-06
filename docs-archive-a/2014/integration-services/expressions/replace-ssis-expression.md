---
title: REPLACE (espressione SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- replacing string expression
- REPLACE function
ms.assetid: a6837043-ea70-4c6a-9c7a-6868b02b2adc
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e483ba6c9c72cb777f2955929a717c6c2e17a8c5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716503"
---
# <a name="replace-ssis-expression"></a><span data-ttu-id="25707-102">REPLACE (espressione SSIS)</span><span class="sxs-lookup"><span data-stu-id="25707-102">REPLACE (SSIS Expression)</span></span>
  <span data-ttu-id="25707-103">Viene restituita un'espressione di caratteri dopo aver sostituito una stringa di caratteri nell'espressione con un'altra stringa di caratteri o una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="25707-103">Returns a character expression after replacing a character string within the expression with either a different character string or an empty string.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="25707-104">Vengono utilizzate spesso stringhe lunghe dalla funzione REPLACE.</span><span class="sxs-lookup"><span data-stu-id="25707-104">The REPLACE function frequently uses long strings.</span></span> <span data-ttu-id="25707-105">Le conseguenze del troncamento possono essere gestite normalmente oppure generare un avviso o un errore.</span><span class="sxs-lookup"><span data-stu-id="25707-105">The consequences of truncation can be handled gracefully or cause a warning or an error.</span></span> <span data-ttu-id="25707-106">Per altre informazioni, vedere [Sintassi &#40;SSIS&#41;](syntax-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="25707-106">For more information, see [Syntax &#40;SSIS&#41;](syntax-ssis.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25707-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="25707-107">Syntax</span></span>  
  
```  
  
REPLACE(character_expression,searchstring,replacementstring)  
```  
  
## <a name="arguments"></a><span data-ttu-id="25707-108">Argomenti</span><span class="sxs-lookup"><span data-stu-id="25707-108">Arguments</span></span>  
 <span data-ttu-id="25707-109">*character_expression*</span><span class="sxs-lookup"><span data-stu-id="25707-109">*character_expression*</span></span>  
 <span data-ttu-id="25707-110">Espressione di caratteri valida in cui la funzione esegue la ricerca.</span><span class="sxs-lookup"><span data-stu-id="25707-110">Is a valid character expression that the function searches.</span></span>  
  
 <span data-ttu-id="25707-111">*searchstring*</span><span class="sxs-lookup"><span data-stu-id="25707-111">*searchstring*</span></span>  
 <span data-ttu-id="25707-112">Espressione di caratteri valida che la funzione tenta di individuare.</span><span class="sxs-lookup"><span data-stu-id="25707-112">Is a valid character expression that the function attempts to locate.</span></span>  
  
 <span data-ttu-id="25707-113">*replacementstring*</span><span class="sxs-lookup"><span data-stu-id="25707-113">*replacementstring*</span></span>  
 <span data-ttu-id="25707-114">Espressione di caratteri valida che costituisce l'espressione da sostituire.</span><span class="sxs-lookup"><span data-stu-id="25707-114">Is a valid character expression that is the replacement expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="25707-115">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="25707-115">Result Types</span></span>  
 <span data-ttu-id="25707-116">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="25707-116">DT_WSTR</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="25707-117">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="25707-117">Remarks</span></span>  
 <span data-ttu-id="25707-118">La lunghezza di *searchstring* deve essere diversa da zero.</span><span class="sxs-lookup"><span data-stu-id="25707-118">The length of *searchstring* must not be zero.</span></span>  
  
 <span data-ttu-id="25707-119">La lunghezza di *replacementstring* può essere zero.</span><span class="sxs-lookup"><span data-stu-id="25707-119">The length of *replacementstring* may be zero.</span></span>  
  
 <span data-ttu-id="25707-120">Gli argomenti *searchstring* e *replacementstring* possono usare variabili e colonne.</span><span class="sxs-lookup"><span data-stu-id="25707-120">The *searchstring* and *replacementstring* arguments can use variables and columns.</span></span>  
  
 <span data-ttu-id="25707-121">È possibile utilizzare REPLACE solo con il tipo di dati DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="25707-121">REPLACE works only with the DT_WSTR data type.</span></span> <span data-ttu-id="25707-122">Per gli argomenti*character_expression1, character_expression2,* e *character_expression3* costituiti da valori letterali stringa o da colonne di dati con tipo di dati DT_STR, prima di eseguire l'operazione della funzione REPLACE viene eseguito il cast implicito al tipo di dati DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="25707-122">*character_expression1, character_expression2,* and *character_expression3* arguments that are string literals or data columns with the DT_STR data type are implicitly cast to the DT_WSTR data type before REPLACE performs its operation.</span></span> <span data-ttu-id="25707-123">Per gli altri tipi di dati è necessario il cast esplicito al tipo di dati DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="25707-123">Other data types must be explicitly cast to the DT_WSTR data type.</span></span> <span data-ttu-id="25707-124">Per altre informazioni, vedere [Cast &#40;espressione SSIS&#41;](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="25707-124">For more information, see [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="25707-125">Se un argomento qualsiasi è Null, REPLACE restituirà Null.</span><span class="sxs-lookup"><span data-stu-id="25707-125">REPLACE returns a null result if any argument is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="25707-126">Esempi di espressione</span><span class="sxs-lookup"><span data-stu-id="25707-126">Expression Examples</span></span>  
 <span data-ttu-id="25707-127">In questo esempio viene utilizzato un valore letterale stringa.</span><span class="sxs-lookup"><span data-stu-id="25707-127">This example uses a string literal.</span></span> <span data-ttu-id="25707-128">Il risultato restituito è "All Terrain Bike".</span><span class="sxs-lookup"><span data-stu-id="25707-128">The return result is "All Terrain Bike".</span></span>  
  
```  
REPLACE("Mountain Bike", "Mountain","All Terrain")  
```  
  
 <span data-ttu-id="25707-129">In questo esempio viene rimossa la stringa "Bike" dalla colonna **Product** .</span><span class="sxs-lookup"><span data-stu-id="25707-129">This example removes the string "Bike" from the **Product** column.</span></span>  
  
```  
REPLACE(Product, "Bike","")  
```  
  
 <span data-ttu-id="25707-130">In questo esempio vengono sostituiti alcuni valori nella colonna **DaysToManufacture** .</span><span class="sxs-lookup"><span data-stu-id="25707-130">This example replaces values in the **DaysToManufacture** column.</span></span> <span data-ttu-id="25707-131">La colonna ha tipo di dati integer e l'espressione include il cast di **DaysToManufacture** al tipo di dati DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="25707-131">The column has an integer data type and the expression includes casting **DaysToManufacture** to the DT_WSTR data type.</span></span>  
  
```  
REPLACE((DT_WSTR,8)DaysToManufacture,"6","5")  
```  
  
## <a name="see-also"></a><span data-ttu-id="25707-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="25707-132">See Also</span></span>  
 <span data-ttu-id="25707-133">[SUBSTRING &#40;espressione SSIS&#41;](substring-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="25707-133">[SUBSTRING &#40;SSIS Expression&#41;](substring-ssis-expression.md) </span></span>  
 [<span data-ttu-id="25707-134">Funzioni &#40;espressione SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="25707-134">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
