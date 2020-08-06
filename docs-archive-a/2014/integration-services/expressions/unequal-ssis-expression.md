---
title: '!= (diverso da) (espressione SSIS) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- unequal operator (!=)
- '!= (not equal to)'
ms.assetid: fad20e85-c0e6-42bf-af70-2bc80ee09be5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: be3eadbac77d76a2b3aac9555d9f40cb56e38949
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716435"
---
# <a name="-unequal-ssis-expression"></a><span data-ttu-id="2f235-102">!= (diverso da) (espressione SSIS)</span><span class="sxs-lookup"><span data-stu-id="2f235-102">!= (Unequal) (SSIS Expression)</span></span>
  <span data-ttu-id="2f235-103">Viene eseguito un confronto per determinare se due espressioni con tipi di dati compatibili sono diverse.</span><span class="sxs-lookup"><span data-stu-id="2f235-103">Performs a comparison to determine if two expressions with compatible data types are not equal.</span></span> <span data-ttu-id="2f235-104">L'analizzatore di espressioni converte automaticamente numerosi tipi di dati prima di eseguire il confronto.</span><span class="sxs-lookup"><span data-stu-id="2f235-104">The expression evaluator automatically converts many data types before it performs the comparison.</span></span>  
  
 <span data-ttu-id="2f235-105">Per alcuni tipi di dati, tuttavia, è necessario che l'espressione includa un cast esplicito per consentirne la corretta valutazione.</span><span class="sxs-lookup"><span data-stu-id="2f235-105">However, some data types require that the expression include an explicit cast before the expression can be evaluated successfully.</span></span> <span data-ttu-id="2f235-106">Per altre informazioni sui cast supportati tra tipi di dati, vedere [Cast &#40;espressione SSIS&#41;](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="2f235-106">For more information about legal casts between data types, see [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f235-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2f235-107">Syntax</span></span>  
  
```  
  
expression1 != expression2  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="2f235-108">Argomenti</span><span class="sxs-lookup"><span data-stu-id="2f235-108">Arguments</span></span>  
 <span data-ttu-id="2f235-109">*expression1, expression2*</span><span class="sxs-lookup"><span data-stu-id="2f235-109">*expression1, expression2*</span></span>  
 <span data-ttu-id="2f235-110">È qualsiasi espressione valida.</span><span class="sxs-lookup"><span data-stu-id="2f235-110">Is any valid expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="2f235-111">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="2f235-111">Result Types</span></span>  
 <span data-ttu-id="2f235-112">DT_BOOL</span><span class="sxs-lookup"><span data-stu-id="2f235-112">DT_BOOL</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2f235-113">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="2f235-113">Remarks</span></span>  
 <span data-ttu-id="2f235-114">Se una delle espressioni nel confronto è Null, il risultato del confronto sarà Null.</span><span class="sxs-lookup"><span data-stu-id="2f235-114">If either expression in the comparison is null, the comparison result is null.</span></span> <span data-ttu-id="2f235-115">Se entrambe le espressioni sono Null, il risultato sarà Null.</span><span class="sxs-lookup"><span data-stu-id="2f235-115">If both expressions are null, the result is null.</span></span>  
  
 <span data-ttu-id="2f235-116">Il set di espressioni *expression1* e *expression2*deve seguire una di queste regole:</span><span class="sxs-lookup"><span data-stu-id="2f235-116">The expression set, *expression1* and *expression2*, must follow one of these rules:</span></span>  
  
-   <span data-ttu-id="2f235-117">**Numeric** Sia *expression1* che *expression2* devono essere un tipo di dati numerici.</span><span class="sxs-lookup"><span data-stu-id="2f235-117">**Numeric** Both *expression1* and *expression2* must be a numeric data type.</span></span> <span data-ttu-id="2f235-118">L'intersezione dei tipi di dati deve essere un tipo di dati numeric come specificato dalle regole relative alle conversioni numeriche implicite eseguite dall'analizzatore di espressioni.</span><span class="sxs-lookup"><span data-stu-id="2f235-118">The intersection of the data types must be a numeric data type, as specified in the rules about the implicit numeric conversions that the expression evaluator performs.</span></span> <span data-ttu-id="2f235-119">L'intersezione dei due tipi di dati numeric non può essere Null.</span><span class="sxs-lookup"><span data-stu-id="2f235-119">The intersection of the two numeric data types cannot be null.</span></span> <span data-ttu-id="2f235-120">Per altre informazioni, vedere [Tipi di dati nelle espressioni di Integration Services](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="2f235-120">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
-   <span data-ttu-id="2f235-121">**Character** Sia *expression1* che *expression2* devono restituire un tipo di dati DT_STR o DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="2f235-121">**Character** Both *expression1* and *expression2* must evaluate to either a DT_STR or a DT_WSTR data type.</span></span> <span data-ttu-id="2f235-122">Le due espressioni possono restituire tipi di dati string diversi.</span><span class="sxs-lookup"><span data-stu-id="2f235-122">The two expressions can evaluate to different string data types.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2f235-123">Per i confronti di stringa viene applicata la distinzione tra maiuscole e minuscole, tra caratteri accentati e non accentati, la distinzione Kana e di larghezza.</span><span class="sxs-lookup"><span data-stu-id="2f235-123">String comparisons are case, accent, kana, and width-sensitive.</span></span>  
  
-   <span data-ttu-id="2f235-124">**Date, Time o Date/Time** Sia *expression1* che *expression2* devono restituire uno dei tipi di dati seguenti: DT_DBDATE, DT_DATE, DT_DBTIME, DT_DBTIME2, DT_DBTIMESTAMP, DT_DBTIMESTAMP2, DT_DBTIMESTAPMOFFSET o DT_FILETIME.</span><span class="sxs-lookup"><span data-stu-id="2f235-124">**Date, Time, or Date/Time** Both *expression1* and *expression2* must evaluate to one of the following data types: DT_DBDATE, DT_DATE, DT_DBTIME, DT_DBTIME2, DT_DBTIMESTAMP, DT_DBTIMESTAMP2, DT_DBTIMESTAPMOFFSET, or DT_FILETIME.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2f235-125">Il sistema non supporta i confronti tra un'espressione che restituisce un tipo di dati di ora e un'espressione che restituisce una data o un tipo di dati di data/ora.</span><span class="sxs-lookup"><span data-stu-id="2f235-125">The system does not support comparisons between an expression that evaluates to a time data type and an expression that evaluates to either a date or a date/time data type.</span></span> <span data-ttu-id="2f235-126">Viene generato un errore.</span><span class="sxs-lookup"><span data-stu-id="2f235-126">The system generates an error.</span></span>  
  
     <span data-ttu-id="2f235-127">In caso di confronto delle espressioni, vengono applicate le regole di conversione seguenti nell'ordine elencato:</span><span class="sxs-lookup"><span data-stu-id="2f235-127">When comparing the expressions, the system applies the following conversion rules in the order listed:</span></span>  
  
    -   <span data-ttu-id="2f235-128">Quando le due espressioni restituiscono lo stesso tipo di dati, viene effettuato un confronto del tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="2f235-128">When the two expressions evaluate to the same data type, a comparison of that data type is performed.</span></span>  
  
    -   <span data-ttu-id="2f235-129">Se un'espressione è un tipo di dati DT_DBTIMESTAMPOFFSET, l'altra espressione viene convertita implicitamente in DT_DBTIMESTAMPOFFSET e viene eseguito un confronto DT_DBTIMESTAMPOFFSET.</span><span class="sxs-lookup"><span data-stu-id="2f235-129">If one expression is a DT_DBTIMESTAMPOFFSET data type, the other expression is implicitly converted to DT_DBTIMESTAMPOFFSET and a DT_DBTIMESTAMPOFFSET comparison is performed.</span></span> <span data-ttu-id="2f235-130">Per altre informazioni, vedere [Tipi di dati nelle espressioni di Integration Services](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="2f235-130">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
    -   <span data-ttu-id="2f235-131">Se un'espressione è un tipo di dati DT_DBTIMESTAMP2, l'altra espressione viene convertita implicitamente in DT_DBTIMESTAMP2 e viene eseguito un confronto DT_DBTIMESTAMP2.</span><span class="sxs-lookup"><span data-stu-id="2f235-131">If one expression is a DT_DBTIMESTAMP2 data type, the other expression is implicitly converted to DT_DBTIMESTAMP2 and a DT_DBTIMESTAMP2 comparison is performed.</span></span>  
  
    -   <span data-ttu-id="2f235-132">Se un'espressione è un tipo di dati DT_DBTIME2, l'altra espressione viene convertita implicitamente in DT_DBTIME2 e viene eseguito un confronto DT_DBTIME2.</span><span class="sxs-lookup"><span data-stu-id="2f235-132">If one expression is a DT_DBTIME2 data type, the other expression is implicitly converted to DT_DBTIME2, and a DT_DBTIME2 comparison is performed.</span></span>  
  
    -   <span data-ttu-id="2f235-133">Se un'espressione è di un tipo diverso da DT_DBTIMESTAMPOFFSET, DT_DBTIMESTAMP2 o DT_DBTIME2, le espressioni vengono convertite nel tipo di dati DT_DBTIMESTAMP prima del confronto.</span><span class="sxs-lookup"><span data-stu-id="2f235-133">If one expression is of a type other than DT_DBTIMESTAMPOFFSET, DT_DBTIMESTAMP2, or DT_DBTIME2, the expressions are converted to the DT_DBTIMESTAMP data type before they are compared.</span></span>  
  
     <span data-ttu-id="2f235-134">In caso di confronto delle espressioni, il sistema presuppone quanto segue:</span><span class="sxs-lookup"><span data-stu-id="2f235-134">When comparing the expressions, the system makes the following assumptions:</span></span>  
  
    -   <span data-ttu-id="2f235-135">Se ogni espressione è un tipo di dati che include secondi frazionari, il sistema presuppone che il tipo di dati con il numero di cifre più basso per secondi frazionari presenti un valore pari a zero per le cifre rimanenti.</span><span class="sxs-lookup"><span data-stu-id="2f235-135">If each expression is a data type that includes fractional seconds, the system assumes that the data type with the least number of digits for fractional seconds has zeros for the remaining digits.</span></span>  
  
    -   <span data-ttu-id="2f235-136">Se ogni espressione è un tipo di dati relativo alla data, ma solo una dispone di una differenza di fuso orario, il sistema presuppone che il tipo di dati senza la differenza di fuso orario sia espresso in formato UTC (Coordinated Universal Time).</span><span class="sxs-lookup"><span data-stu-id="2f235-136">If each expression is a date data type, but only one has a time zone offset, the system assumes that the date data type without the time zone offset is in Coordinated Universal Time (UTC).</span></span>  
  
-   <span data-ttu-id="2f235-137">**Logical** Sia *expression1* che *expression2* devono restituire un valore booleano.</span><span class="sxs-lookup"><span data-stu-id="2f235-137">**Logical** Both *expression1* and *expression2* must evaluate to a Boolean.</span></span>  
  
-   <span data-ttu-id="2f235-138">**GUID** Sia *expression1* che *expression2* devono restituire il tipo di dati DT_GUID.</span><span class="sxs-lookup"><span data-stu-id="2f235-138">**GUID** Both *expression1* and *expression2* must evaluate to the DT_GUID data type.</span></span>  
  
-   <span data-ttu-id="2f235-139">**Binary** Sia *expression1* che *expression2* devono restituire il tipo di dati DT_BYTES.</span><span class="sxs-lookup"><span data-stu-id="2f235-139">**Binary** Both *expression1* and *expression2* must evaluate to the DT_BYTES data type.</span></span>  
  
-   <span data-ttu-id="2f235-140">**BLOB** Sia *expression1* che *expression2* devono restituire lo stesso tipo di dati BLOB (Binary Large Object Block), cioè DT_TEXT, DT_NTEXT o DT_IMAGE.</span><span class="sxs-lookup"><span data-stu-id="2f235-140">**BLOB** Both *expression1* and *expression2* must evaluate to the same Binary Large Object Block (BLOB) data type: DT_TEXT, DT_NTEXT, or DT_IMAGE.</span></span>  
  
 <span data-ttu-id="2f235-141">Per altre informazioni sui tipi di dati, vedere [Tipi di dati di Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="2f235-141">For more information about data types, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="2f235-142">Esempi di espressione</span><span class="sxs-lookup"><span data-stu-id="2f235-142">Expression Examples</span></span>  
 <span data-ttu-id="2f235-143">In questo esempio viene restituito TRUE solo se la data corrente non è il 4 luglio 2003.</span><span class="sxs-lookup"><span data-stu-id="2f235-143">This example evaluates to TRUE only if the current date is not July 4, 2003.</span></span> <span data-ttu-id="2f235-144">Per altre informazioni, vedere [GETDATE &#40;espressione SSIS&#41;](getdate-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="2f235-144">For more information, see [GETDATE &#40;SSIS Expression&#41;](getdate-ssis-expression.md).</span></span>  
  
```  
"7/4/2003" != GETDATE()  
```  
  
 <span data-ttu-id="2f235-145">In questo esempio viene restituito TRUE se il valore nella colonna **ListPrice** non è 500.</span><span class="sxs-lookup"><span data-stu-id="2f235-145">This example evaluates to TRUE if the value in the **ListPrice** column is not 500.</span></span>  
  
```  
ListPrice != 500  
```  
  
 <span data-ttu-id="2f235-146">In questo esempio viene usata la variabile **LPrice**.</span><span class="sxs-lookup"><span data-stu-id="2f235-146">This example uses the variable **LPrice**.</span></span> <span data-ttu-id="2f235-147">Viene restituito TRUE se il valore di **LPrice** non è 500.</span><span class="sxs-lookup"><span data-stu-id="2f235-147">It evaluates to TRUE if the value of **LPrice** is not 500.</span></span> <span data-ttu-id="2f235-148">Per consentire l'analisi dell'espressione, il tipo di dati della variabile deve essere numeric.</span><span class="sxs-lookup"><span data-stu-id="2f235-148">The data type on the variable must be numeric in order for the expression to parse.</span></span>  
  
```  
@LPrice != 500  
```  
  
## <a name="see-also"></a><span data-ttu-id="2f235-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2f235-149">See Also</span></span>  
 <span data-ttu-id="2f235-150">[== &#40;uguale&#41; &#40;espressione SSIS&#41;](equal-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="2f235-150">[== &#40;Equal&#41; &#40;SSIS Expression&#41;](equal-ssis-expression.md) </span></span>  
 <span data-ttu-id="2f235-151">[Precedenza e associatività degli operatori](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="2f235-151">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="2f235-152">Operatori &#40;espressione SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="2f235-152">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
