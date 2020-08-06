---
title: '&lt;= (minore o uguale a) (espressione SSIS) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- <= (less than or equal to operator)
- less than or equal to operator (<=)
ms.assetid: 946c5630-dccf-4dae-9cfd-6ea823641ab2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c1c0b5ef0a8467cedbc5e390b42f3307cceb7c75
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627301"
---
# <a name="lt-less-than-or-equal-to-ssis-expression"></a><span data-ttu-id="d3317-102">&lt;= (minore o uguale a) (espressione SSIS)</span><span class="sxs-lookup"><span data-stu-id="d3317-102">&lt;= (Less Than or Equal To) (SSIS Expression)</span></span>
  <span data-ttu-id="d3317-103">Viene eseguito un confronto per determinare se la prima espressione è minore o uguale alla seconda.</span><span class="sxs-lookup"><span data-stu-id="d3317-103">Performs a comparison to determine if the first expression is less than or equal to the second one.</span></span> <span data-ttu-id="d3317-104">L'analizzatore di espressioni converte automaticamente numerosi tipi di dati prima di eseguire il confronto.</span><span class="sxs-lookup"><span data-stu-id="d3317-104">The expression evaluator automatically converts many data types before it performs the comparison.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d3317-105">Questo operatore non supporta confronti tra espressioni che utilizzano il tipo di dati DT_TEXT, DT_NTEXT o DT_IMAGE.</span><span class="sxs-lookup"><span data-stu-id="d3317-105">This operator does not support comparisons that use the DT_TEXT, DT_NTEXT, or DT_IMAGE data types.</span></span>  
  
 <span data-ttu-id="d3317-106">Per alcuni tipi di dati, tuttavia, è necessario che l'espressione includa un cast esplicito per consentirne la corretta valutazione.</span><span class="sxs-lookup"><span data-stu-id="d3317-106">However, some data types require that the expression include an explicit cast before the expression can be evaluated successfully.</span></span> <span data-ttu-id="d3317-107">Per altre informazioni sui cast supportati tra tipi di dati, vedere [Cast &#40;espressione SSIS&#41;](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="d3317-107">For more information about legal casts between data types, see [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d3317-108">Tra i due caratteri di questo operatore non sono presenti spazi.</span><span class="sxs-lookup"><span data-stu-id="d3317-108">There are no spaces between the two characters in this operator.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3317-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d3317-109">Syntax</span></span>  
  
```  
  
expression1 <= expression2  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="d3317-110">Argomenti</span><span class="sxs-lookup"><span data-stu-id="d3317-110">Arguments</span></span>  
 <span data-ttu-id="d3317-111">*expression1, expression2*</span><span class="sxs-lookup"><span data-stu-id="d3317-111">*expression1, expression2*</span></span>  
 <span data-ttu-id="d3317-112">È qualsiasi espressione valida.</span><span class="sxs-lookup"><span data-stu-id="d3317-112">Is any valid expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="d3317-113">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="d3317-113">Result Types</span></span>  
 <span data-ttu-id="d3317-114">DT_BOOL</span><span class="sxs-lookup"><span data-stu-id="d3317-114">DT_BOOL</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d3317-115">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="d3317-115">Remarks</span></span>  
 <span data-ttu-id="d3317-116">Se una delle espressioni nel confronto è Null, il risultato del confronto sarà Null.</span><span class="sxs-lookup"><span data-stu-id="d3317-116">If either expression in the comparison is null, the comparison result is null.</span></span> <span data-ttu-id="d3317-117">Se entrambe le espressioni sono Null, il risultato sarà Null.</span><span class="sxs-lookup"><span data-stu-id="d3317-117">If both expressions are null, the result is null.</span></span>  
  
 <span data-ttu-id="d3317-118">Il set di espressioni *expression1* e *expression2*deve seguire una di queste regole:</span><span class="sxs-lookup"><span data-stu-id="d3317-118">The expression set, *expression1* and *expression2*, must follow one of these rules:</span></span>  
  
-   <span data-ttu-id="d3317-119">**Numeric** Sia *expression1* che *expression2* devono essere un tipo di dati numerici.</span><span class="sxs-lookup"><span data-stu-id="d3317-119">**Numeric** Both *expression1* and *expression2* must be a numeric data type.</span></span> <span data-ttu-id="d3317-120">L'intersezione dei tipi di dati deve essere un tipo di dati numeric come specificato dalle regole relative alle conversioni numeriche implicite eseguite dall'analizzatore di espressioni.</span><span class="sxs-lookup"><span data-stu-id="d3317-120">The intersection of the data types must be a numeric data type as specified in the rules about the implicit numeric conversions that the expression evaluator performs.</span></span> <span data-ttu-id="d3317-121">L'intersezione dei due tipi di dati numeric non può essere Null.</span><span class="sxs-lookup"><span data-stu-id="d3317-121">The intersection of the two numeric data types cannot be null.</span></span> <span data-ttu-id="d3317-122">Per altre informazioni, vedere [Tipi di dati nelle espressioni di Integration Services](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="d3317-122">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
-   <span data-ttu-id="d3317-123">**Character** Sia *expression1* che *expression2* devono restituire un tipo di dati DT_STR o DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="d3317-123">**Character** Both *expression1* and *expression2* must evaluate to either a DT_STR or a DT_WSTR data type.</span></span> <span data-ttu-id="d3317-124">Le due espressioni possono restituire tipi di dati string diversi.</span><span class="sxs-lookup"><span data-stu-id="d3317-124">The two expressions can evaluate to different string data types.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d3317-125">Per i confronti di stringa viene applicata la distinzione tra maiuscole e minuscole, tra caratteri accentati e non accentati, la distinzione Kana e di larghezza.</span><span class="sxs-lookup"><span data-stu-id="d3317-125">String comparisons are case, accent, kana, and width-sensitive.</span></span>  
  
-   <span data-ttu-id="d3317-126">**Date, Time o Date/Time** Sia *expression1* che *expression2* devono restituire uno dei tipi di dati seguenti: DT_DBDATE, DT_DATE, DT_DBTIME, DT_DBTIME2, DT_DBTIMESTAMP, DT_DBTIMESTAMP2, DT_DBTIMESTAPMOFFSET o DT_FILETIME.</span><span class="sxs-lookup"><span data-stu-id="d3317-126">**Date, Time, or Date/Time** Both *expression1* and *expression2* must evaluate to one of the following data types: DT_DBDATE, DT_DATE, DT_DBTIME, DT_DBTIME2, DT_DBTIMESTAMP, DT_DBTIMESTAMP2, DT_DBTIMESTAPMOFFSET, or DT_FILETIME.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d3317-127">Il sistema non supporta i confronti tra un'espressione che restituisce un tipo di dati di ora e un'espressione che restituisce una data o un tipo di dati di data/ora.</span><span class="sxs-lookup"><span data-stu-id="d3317-127">The system does not support comparisons between an expression that evaluates to a time data type and an expression that evaluates to either a date or a date/time data type.</span></span> <span data-ttu-id="d3317-128">Viene generato un errore.</span><span class="sxs-lookup"><span data-stu-id="d3317-128">The system generates an error.</span></span>  
  
     <span data-ttu-id="d3317-129">In caso di confronto delle espressioni, vengono applicate le regole di conversione seguenti nell'ordine elencato:</span><span class="sxs-lookup"><span data-stu-id="d3317-129">When comparing the expressions, the system applies the following conversion rules in the order listed:</span></span>  
  
    -   <span data-ttu-id="d3317-130">Quando le due espressioni restituiscono lo stesso tipo di dati, viene effettuato un confronto del tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="d3317-130">When the two expressions evaluate to the same data type, a comparison of that data type is performed.</span></span>  
  
    -   <span data-ttu-id="d3317-131">Se un'espressione è un tipo di dati DT_DBTIMESTAMPOFFSET, l'altra espressione viene convertita implicitamente in DT_DBTIMESTAMPOFFSET e viene eseguito un confronto DT_DBTIMESTAMPOFFSET.</span><span class="sxs-lookup"><span data-stu-id="d3317-131">If one expression is a DT_DBTIMESTAMPOFFSET data type, the other expression is implicitly converted to DT_DBTIMESTAMPOFFSET and a DT_DBTIMESTAMPOFFSET comparison is performed.</span></span> <span data-ttu-id="d3317-132">Per altre informazioni, vedere [Tipi di dati nelle espressioni di Integration Services](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="d3317-132">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
    -   <span data-ttu-id="d3317-133">Se un'espressione è un tipo di dati DT_DBTIMESTAMP2, l'altra espressione viene convertita implicitamente in DT_DBTIMESTAMP2 e viene eseguito un confronto DT_DBTIMESTAMP2.</span><span class="sxs-lookup"><span data-stu-id="d3317-133">If one expression is a DT_DBTIMESTAMP2 data type, the other expression is implicitly converted to DT_DBTIMESTAMP2 and a DT_DBTIMESTAMP2 comparison is performed.</span></span>  
  
    -   <span data-ttu-id="d3317-134">Se un'espressione è un tipo di dati DT_DBTIME2, l'altra espressione viene convertita implicitamente in DT_DBTIME2 e viene eseguito un confronto DT_DBTIME2.</span><span class="sxs-lookup"><span data-stu-id="d3317-134">If one expression is a DT_DBTIME2 data type, the other expression is implicitly converted to DT_DBTIME2, and a DT_DBTIME2 comparison is performed.</span></span>  
  
    -   <span data-ttu-id="d3317-135">Se un'espressione è di un tipo diverso da DT_DBTIMESTAMPOFFSET, DT_DBTIMESTAMP2 o DT_DBTIME2, le espressioni vengono convertite nel tipo di dati DT_DBTIMESTAMP prima del confronto.</span><span class="sxs-lookup"><span data-stu-id="d3317-135">If one expression is of a type other than DT_DBTIMESTAMPOFFSET, DT_DBTIMESTAMP2, or DT_DBTIME2, the expressions are converted to the DT_DBTIMESTAMP data type before they are compared.</span></span>  
  
     <span data-ttu-id="d3317-136">In caso di confronto delle espressioni, il sistema presuppone quanto segue:</span><span class="sxs-lookup"><span data-stu-id="d3317-136">When comparing the expressions, the system makes the following assumptions:</span></span>  
  
    -   <span data-ttu-id="d3317-137">Se ogni espressione è un tipo di dati che include secondi frazionari, il sistema presuppone che il tipo di dati con il numero di cifre più basso per secondi frazionari presenti un valore pari a zero per le cifre rimanenti.</span><span class="sxs-lookup"><span data-stu-id="d3317-137">If each expression is a data type that includes fractional seconds, the system assumes that the data type with the least number of digits for fractional seconds has zeros for the remaining digits.</span></span>  
  
    -   <span data-ttu-id="d3317-138">Se ogni espressione è un tipo di dati relativo alla data, ma solo una dispone di una differenza di fuso orario, il sistema presuppone che il tipo di dati senza la differenza di fuso orario sia espresso in formato UTC (Coordinated Universal Time).</span><span class="sxs-lookup"><span data-stu-id="d3317-138">If each expression is a date data type, but only one has a time zone offset, the system assumes that the date data type without the time zone offset is in Coordinated Universal Time (UTC).</span></span>  
  
 <span data-ttu-id="d3317-139">Per altre informazioni sui tipi di dati, vedere [Tipi di dati di Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="d3317-139">For more information about data types, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="d3317-140">Esempi di espressione</span><span class="sxs-lookup"><span data-stu-id="d3317-140">Expression Examples</span></span>  
 <span data-ttu-id="d3317-141">In questo esempio viene restituito TRUE se la data corrente è il 4 luglio 2003 o una data successiva.</span><span class="sxs-lookup"><span data-stu-id="d3317-141">This example evaluates to TRUE if the current date is July 4, 2003 or later.</span></span> <span data-ttu-id="d3317-142">Per altre informazioni, vedere [GETDATE &#40;espressione SSIS&#41;](getdate-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="d3317-142">For more information, see [GETDATE &#40;SSIS Expression&#41;](getdate-ssis-expression.md).</span></span>  
  
```  
"7/4/2003" <= GETDATE()  
```  
  
 <span data-ttu-id="d3317-143">Questo esempio restituisce TRUE se il valore nella colonna **ListPrice** è minore o uguale a 500.</span><span class="sxs-lookup"><span data-stu-id="d3317-143">This example evaluates to TRUE if the value in the **ListPrice** column is less than or equal to 500.</span></span>  
  
```  
ListPrice <= 500  
```  
  
 <span data-ttu-id="d3317-144">In questo esempio viene valutata la variabile **LPrice** e viene restituito TRUE se il valore è minore o uguale a 500.</span><span class="sxs-lookup"><span data-stu-id="d3317-144">This example evaluates the variable **LPrice** and evaluates to TRUE if the value is less than or equal to 500.</span></span> <span data-ttu-id="d3317-145">Per consentire l'analisi dell'espressione, il tipo di dati di **LPrice** deve essere numeric.</span><span class="sxs-lookup"><span data-stu-id="d3317-145">The data type of **LPrice** must be numeric in order for the expression to parse.</span></span>  
  
```  
@LPrice <= 500  
```  
  
## <a name="see-also"></a><span data-ttu-id="d3317-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d3317-146">See Also</span></span>  
 <span data-ttu-id="d3317-147">[&#62; &#40;maggiore di&#41; &#40;espressione SSIS&#41;](greater-than-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="d3317-147">[&#62; &#40;Greater Than&#41; &#40;SSIS Expression&#41;](greater-than-ssis-expression.md) </span></span>  
 <span data-ttu-id="d3317-148">[&#60; &#40;minore di&#41; &#40;espressione SSIS&#41;](less-than-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="d3317-148">[&#60; &#40;Less Than&#41; &#40;SSIS Expression&#41;](less-than-ssis-expression.md) </span></span>  
 <span data-ttu-id="d3317-149">[&#62;= &#40;maggiore o uguale a&#41; &#40;espressione SSIS&#41;](greater-than-or-equal-to-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="d3317-149">[&#62;= &#40;Greater Than or Equal To&#41; &#40;SSIS Expression&#41;](greater-than-or-equal-to-ssis-expression.md) </span></span>  
 <span data-ttu-id="d3317-150">[Precedenza e associatività degli operatori](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="d3317-150">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="d3317-151">Operatori &#40;espressione SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="d3317-151">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
