---
title: '? : (condizionale) (espressione SSIS) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- conditional operator (?:)
- '?: (conditional operator)'
ms.assetid: d38e6890-7338-4ce0-a837-2dbb41823a37
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e607f9ed495184ef47ac2e4f1139b9a9566055ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637440"
---
# <a name="--conditional-ssis-expression"></a><span data-ttu-id="43e76-103">?</span><span class="sxs-lookup"><span data-stu-id="43e76-103">?</span></span> <span data-ttu-id="43e76-104">: (condizionale) (espressione SSIS)</span><span class="sxs-lookup"><span data-stu-id="43e76-104">: (Conditional) (SSIS Expression)</span></span>
  <span data-ttu-id="43e76-105">Viene restituita una di due espressioni in base alla valutazione di un'espressione booleana.</span><span class="sxs-lookup"><span data-stu-id="43e76-105">Returns one of two expressions based on the evaluation of a Boolean expression.</span></span> <span data-ttu-id="43e76-106">Se l'espressione booleana restituisce TRUE, verrà valutata la prima espressione e il risultato sarà il risultato di tale espressione.</span><span class="sxs-lookup"><span data-stu-id="43e76-106">If the Boolean expression evaluates to TRUE, then the first expression is evaluated and the result is the expression result.</span></span> <span data-ttu-id="43e76-107">Se l'espressione booleana restituisce FALSE, verrà valutata la seconda espressione e il risultato sarà il risultato di tale espressione.</span><span class="sxs-lookup"><span data-stu-id="43e76-107">If the Boolean expression evaluates to FALSE then the second expression is evaluated and its result is the expression result.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43e76-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="43e76-108">Syntax</span></span>  
  
```  
  
boolean_expression?expression1:expression2  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="43e76-109">Argomenti</span><span class="sxs-lookup"><span data-stu-id="43e76-109">Arguments</span></span>  
 <span data-ttu-id="43e76-110">*boolean_expression*</span><span class="sxs-lookup"><span data-stu-id="43e76-110">*boolean_expression*</span></span>  
 <span data-ttu-id="43e76-111">Qualsiasi espressione valida che restituisce TRUE, FALSE o NULL.</span><span class="sxs-lookup"><span data-stu-id="43e76-111">Is any valid expression that evaluates to TRUE, FALSE, or NULL.</span></span>  
  
 <span data-ttu-id="43e76-112">*expression1*</span><span class="sxs-lookup"><span data-stu-id="43e76-112">*expression1*</span></span>  
 <span data-ttu-id="43e76-113">È qualsiasi espressione valida.</span><span class="sxs-lookup"><span data-stu-id="43e76-113">Is any valid expression.</span></span>  
  
 <span data-ttu-id="43e76-114">*expression2*</span><span class="sxs-lookup"><span data-stu-id="43e76-114">*expression2*</span></span>  
 <span data-ttu-id="43e76-115">È qualsiasi espressione valida.</span><span class="sxs-lookup"><span data-stu-id="43e76-115">Is any valid expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="43e76-116">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="43e76-116">Result Types</span></span>  
 <span data-ttu-id="43e76-117">Il tipo di dati *expression1* o *expression2*.</span><span class="sxs-lookup"><span data-stu-id="43e76-117">The data type of *expression1* or *expression2*.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="43e76-118">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="43e76-118">Remarks</span></span>  
 <span data-ttu-id="43e76-119">Se *boolean_expression* restituisce NULL, il risultato dell'espressione sarà NULL.</span><span class="sxs-lookup"><span data-stu-id="43e76-119">If the *boolean_expression* evaluates to NULL, the expression result is NULL.</span></span> <span data-ttu-id="43e76-120">Se un'espressione selezionata, *expression1* o *expression2* è NULL, il risultato sarà NULL.</span><span class="sxs-lookup"><span data-stu-id="43e76-120">If a selected expression, either *expression1* or *expression2* is NULL, the result is NULL.</span></span> <span data-ttu-id="43e76-121">Se l'espressione selezionata non è NULL, ma quella non selezionata è NULL, il risultato sarà il valore dell'espressione selezionata.</span><span class="sxs-lookup"><span data-stu-id="43e76-121">If a selected expression is not NULL, but the one not selected is NULL, the result is the value of the selected expression.</span></span>  
  
 <span data-ttu-id="43e76-122">Se *expression1* e *expression2* hanno lo stesso tipo di dati, anche il risultato sarà di tale tipo.</span><span class="sxs-lookup"><span data-stu-id="43e76-122">If *expression1* and *expression2* have the same data type, the result is that data type.</span></span> <span data-ttu-id="43e76-123">Ai tipi di risultato si applicano le seguenti ulteriori regole:</span><span class="sxs-lookup"><span data-stu-id="43e76-123">The following additional rules apply to result types:</span></span>  
  
-   <span data-ttu-id="43e76-124">Il tipo di dati DT_TEXT richiede che *expression1* e *expression2* abbiano la stessa tabella codici.</span><span class="sxs-lookup"><span data-stu-id="43e76-124">The DT_TEXT data type requires that *expression1* and *expression2* have the same code page.</span></span>  
  
-   <span data-ttu-id="43e76-125">La lunghezza di un risultato con tipo di dati DT_BYTES corrisponde a quella dell'argomento più lungo.</span><span class="sxs-lookup"><span data-stu-id="43e76-125">The length of a result with the DT_BYTES data type is the length of the longer argument.</span></span>  
  
 <span data-ttu-id="43e76-126">Il set di espressioni, *expression1* e *expression2*, deve restituire tipi di dati validi e seguire una di queste regole:</span><span class="sxs-lookup"><span data-stu-id="43e76-126">The expression set, *expression1* and *expression2*, must evaluate to valid data types and follow one of these rules:</span></span>  
  
-   <span data-ttu-id="43e76-127">**Numeric** Sia *expression1* che *expression2* devono essere un tipo di dati numerici.</span><span class="sxs-lookup"><span data-stu-id="43e76-127">**Numeric** Both *expression1* and *expression2* must be a numeric data type.</span></span> <span data-ttu-id="43e76-128">L'intersezione dei tipi di dati deve essere un tipo di dati numeric come specificato dalle regole relative alle conversioni numeriche implicite eseguite dall'analizzatore di espressioni.</span><span class="sxs-lookup"><span data-stu-id="43e76-128">The intersection of the data types must be a numeric data type as specified in the rules about the implicit numeric conversions that the expression evaluator performs.</span></span> <span data-ttu-id="43e76-129">L'intersezione dei due tipi di dati numeric non può essere Null.</span><span class="sxs-lookup"><span data-stu-id="43e76-129">The intersection of the two numeric data types cannot be null.</span></span> <span data-ttu-id="43e76-130">Per altre informazioni, vedere [Tipi di dati nelle espressioni di Integration Services](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="43e76-130">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
-   <span data-ttu-id="43e76-131">**String** Sia *expression1* che *expression2* devono avere un tipo di dati string, ovvero DT_STR o DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="43e76-131">**String** Both *expression1* and *expression2* must be a string data type: DT_STR or DT_WSTR.</span></span> <span data-ttu-id="43e76-132">Le due espressioni possono restituire tipi di dati string diversi.</span><span class="sxs-lookup"><span data-stu-id="43e76-132">The two expressions can evaluate to different string data types.</span></span> <span data-ttu-id="43e76-133">Il risultato ha tipo di dati DT_WSTR e lunghezza pari a quella dell'argomento più lungo.</span><span class="sxs-lookup"><span data-stu-id="43e76-133">The result has the DT_WSTR data type with a length of the longer argument.</span></span>  
  
-   <span data-ttu-id="43e76-134">**Date, Time o Date/Time** Sia *expression1* che *expression2* devono restituire uno dei tipi di dati seguenti: DT_DBDATE, DT_DATE, DT_DBTIME, DT_DBTIME2, DT_DBTIMESTAMP, DT_DBTIMESTAMP2, DT_DBTIMESTAPMOFFSET o DT_FILETIME.</span><span class="sxs-lookup"><span data-stu-id="43e76-134">**Date, Time, or Date/Time** Both *expression1* and *expression2* must evaluate to one of the following data types: DT_DBDATE, DT_DATE, DT_DBTIME, DT_DBTIME2, DT_DBTIMESTAMP, DT_DBTIMESTAMP2, DT_DBTIMESTAPMOFFSET, or DT_FILETIME.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="43e76-135">Il sistema non supporta i confronti tra un'espressione che restituisce un tipo di dati di ora e un'espressione che restituisce una data o un tipo di dati di data/ora.</span><span class="sxs-lookup"><span data-stu-id="43e76-135">The system does not support comparisons between an expression that evaluates to a time data type and an expression that evaluates to either a date or a date/time data type.</span></span> <span data-ttu-id="43e76-136">Viene generato un errore.</span><span class="sxs-lookup"><span data-stu-id="43e76-136">The system generates an error.</span></span>  
  
     <span data-ttu-id="43e76-137">In caso di confronto delle espressioni, vengono applicate le regole di conversione seguenti nell'ordine elencato:</span><span class="sxs-lookup"><span data-stu-id="43e76-137">When comparing the expressions, the system applies the following conversion rules in the order listed:</span></span>  
  
    -   <span data-ttu-id="43e76-138">Quando le due espressioni restituiscono lo stesso tipo di dati, viene effettuato un confronto del tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="43e76-138">When the two expressions evaluate to the same data type, a comparison of that data type is performed.</span></span>  
  
    -   <span data-ttu-id="43e76-139">Se un'espressione è un tipo di dati DT_DBTIMESTAMPOFFSET, l'altra espressione viene convertita implicitamente in DT_DBTIMESTAMPOFFSET e viene eseguito un confronto DT_DBTIMESTAMPOFFSET.</span><span class="sxs-lookup"><span data-stu-id="43e76-139">If one expression is a DT_DBTIMESTAMPOFFSET data type, the other expression is implicitly converted to DT_DBTIMESTAMPOFFSET and a DT_DBTIMESTAMPOFFSET comparison is performed.</span></span> <span data-ttu-id="43e76-140">Per altre informazioni, vedere [Tipi di dati nelle espressioni di Integration Services](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="43e76-140">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
    -   <span data-ttu-id="43e76-141">Se un'espressione è un tipo di dati DT_DBTIMESTAMP2, l'altra espressione viene convertita implicitamente in DT_DBTIMESTAMP2 e viene eseguito un confronto DT_DBTIMESTAMP2.</span><span class="sxs-lookup"><span data-stu-id="43e76-141">If one expression is a DT_DBTIMESTAMP2 data type, the other expression is implicitly converted to DT_DBTIMESTAMP2 and a DT_DBTIMESTAMP2 comparison is performed.</span></span>  
  
    -   <span data-ttu-id="43e76-142">Se un'espressione è un tipo di dati DT_DBTIME2, l'altra espressione viene convertita implicitamente in DT_DBTIME2 e viene eseguito un confronto DT_DBTIME2.</span><span class="sxs-lookup"><span data-stu-id="43e76-142">If one expression is a DT_DBTIME2 data type, the other expression is implicitly converted to DT_DBTIME2, and a DT_DBTIME2 comparison is performed.</span></span>  
  
    -   <span data-ttu-id="43e76-143">Se un'espressione è di un tipo diverso da DT_DBTIMESTAMPOFFSET, DT_DBTIMESTAMP2 o DT_DBTIME2, le espressioni vengono convertite nel tipo di dati DT_DBTIMESTAMP prima del confronto.</span><span class="sxs-lookup"><span data-stu-id="43e76-143">If one expression is of a type other than DT_DBTIMESTAMPOFFSET, DT_DBTIMESTAMP2, or DT_DBTIME2, the expressions are converted to the DT_DBTIMESTAMP data type before they are compared.</span></span>  
  
     <span data-ttu-id="43e76-144">In caso di confronto delle espressioni, il sistema presuppone quanto segue:</span><span class="sxs-lookup"><span data-stu-id="43e76-144">When comparing the expressions, the system makes the following assumptions:</span></span>  
  
    -   <span data-ttu-id="43e76-145">Se ogni espressione è un tipo di dati che include secondi frazionari, il sistema presuppone che il tipo di dati con il numero di cifre più basso per secondi frazionari presenti un valore pari a zero per le cifre rimanenti.</span><span class="sxs-lookup"><span data-stu-id="43e76-145">If each expression is a data type that includes fractional seconds, the system assumes that the data type with the least number of digits for fractional seconds has zeros for the remaining digits.</span></span>  
  
    -   <span data-ttu-id="43e76-146">Se ogni espressione è un tipo di dati relativo alla data, ma solo una dispone di una differenza di fuso orario, il sistema presuppone che il tipo di dati senza la differenza di fuso orario sia espresso in formato UTC (Coordinated Universal Time).</span><span class="sxs-lookup"><span data-stu-id="43e76-146">If each expression is a date data type, but only one has a time zone offset, the system assumes that the date data type without the time zone offset is in Coordinated Universal Time (UTC).</span></span>  
  
 <span data-ttu-id="43e76-147">Per altre informazioni sui tipi di dati, vedere [Tipi di dati di Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="43e76-147">For more information about data types, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="43e76-148">Esempi di espressione</span><span class="sxs-lookup"><span data-stu-id="43e76-148">Expression Examples</span></span>  
 <span data-ttu-id="43e76-149">In questo esempio viene illustrata un'espressione tramite cui viene restituito `savannah` o `unknown`, a seconda del valore restituito dalla condizione.</span><span class="sxs-lookup"><span data-stu-id="43e76-149">This example shows an expression that conditionally evaluates to `savannah` or `unknown`.</span></span>  
  
```  
@AnimalName == "Elephant"? "savannah": "unknown"  
```  
  
 <span data-ttu-id="43e76-150">In questo esempio viene illustrata un'espressione che fa riferimento a una colonna di nome **ListPrice** .</span><span class="sxs-lookup"><span data-stu-id="43e76-150">This example shows an expression that references a **ListPrice** column.</span></span> <span data-ttu-id="43e76-151">**ListPrice** ha tipo di dati DT_CY.</span><span class="sxs-lookup"><span data-stu-id="43e76-151">**ListPrice** has the DT_CY data type.</span></span> <span data-ttu-id="43e76-152">Tramite l'espressione **ListPrice** viene moltiplicato per 0,2 o 0,1, a seconda del valore restituito dalla condizione.</span><span class="sxs-lookup"><span data-stu-id="43e76-152">The expression conditionally multiplies **ListPrice** by .2 or .1.</span></span>  
  
```  
ListPrice < 350.00 ? ListPrice * .2 : ListPrice * .1  
```  
  
## <a name="see-also"></a><span data-ttu-id="43e76-153">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="43e76-153">See Also</span></span>  
 <span data-ttu-id="43e76-154">[Precedenza e associatività degli operatori](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="43e76-154">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="43e76-155">Operatori &#40;espressione SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="43e76-155">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
