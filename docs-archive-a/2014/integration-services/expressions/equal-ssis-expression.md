---
title: == (uguale) (espressione SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- equal operator (==)
- == (equal operator)
ms.assetid: 36fd2354-7b93-4c95-9cf3-51ee24568950
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 12f92a267543c366dee4905010aeb84d93c4f408
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716539"
---
# <a name="-equal-ssis-expression"></a><span data-ttu-id="c4b08-102">== (uguale) (espressione SSIS)</span><span class="sxs-lookup"><span data-stu-id="c4b08-102">== (Equal) (SSIS Expression)</span></span>
  <span data-ttu-id="c4b08-103">Viene eseguito un confronto per determinare se due espressioni sono uguali.</span><span class="sxs-lookup"><span data-stu-id="c4b08-103">Performs a comparison to determine if two expressions are equal.</span></span> <span data-ttu-id="c4b08-104">L'analizzatore di espressioni converte automaticamente numerosi tipi di dati prima di eseguire il confronto.</span><span class="sxs-lookup"><span data-stu-id="c4b08-104">The expression evaluator automatically converts many data types before it performs the comparison.</span></span> <span data-ttu-id="c4b08-105">Per altre informazioni, vedere [Tipi di dati nelle espressioni di Integration Services](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="c4b08-105">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
 <span data-ttu-id="c4b08-106">Per alcuni tipi di dati, tuttavia, è necessario che l'espressione includa un cast esplicito per consentirne la corretta valutazione.</span><span class="sxs-lookup"><span data-stu-id="c4b08-106">However, some data types require that the expression include an explicit cast before the expression can be evaluated successfully.</span></span> <span data-ttu-id="c4b08-107">Per altre informazioni sui cast supportati tra tipi di dati, vedere [Cast &#40;espressione SSIS&#41;](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="c4b08-107">For more information about legal casts between data types, see [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4b08-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c4b08-108">Syntax</span></span>  
  
```  
  
expression1 == expression2  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="c4b08-109">Argomenti</span><span class="sxs-lookup"><span data-stu-id="c4b08-109">Arguments</span></span>  
 <span data-ttu-id="c4b08-110">*expression1, expression2*</span><span class="sxs-lookup"><span data-stu-id="c4b08-110">*expression1, expression2*</span></span>  
 <span data-ttu-id="c4b08-111">È qualsiasi espressione valida.</span><span class="sxs-lookup"><span data-stu-id="c4b08-111">Is any valid expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="c4b08-112">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="c4b08-112">Result Types</span></span>  
 <span data-ttu-id="c4b08-113">DT_BOOL</span><span class="sxs-lookup"><span data-stu-id="c4b08-113">DT_BOOL</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c4b08-114">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="c4b08-114">Remarks</span></span>  
 <span data-ttu-id="c4b08-115">Se una delle espressioni nel confronto è Null, il risultato del confronto sarà Null.</span><span class="sxs-lookup"><span data-stu-id="c4b08-115">If either expression in the comparison is null, the comparison result is null.</span></span> <span data-ttu-id="c4b08-116">Se entrambe le espressioni sono Null, il risultato sarà Null.</span><span class="sxs-lookup"><span data-stu-id="c4b08-116">If both expressions are null, the result is null.</span></span>  
  
 <span data-ttu-id="c4b08-117">Il set di espressioni *expression1* e *expression2*deve seguire una di queste regole:</span><span class="sxs-lookup"><span data-stu-id="c4b08-117">The expression set, *expression1* and *expression2*, must follow one of these rules:</span></span>  
  
-   <span data-ttu-id="c4b08-118">**Numeric** Sia *expression1* che *expression2* devono essere un tipo di dati numerici.</span><span class="sxs-lookup"><span data-stu-id="c4b08-118">**Numeric** Both *expression1* and *expression2* must be a numeric data type.</span></span> <span data-ttu-id="c4b08-119">L'intersezione dei tipi di dati deve essere un tipo di dati numeric come specificato dalle regole relative alle conversioni numeriche implicite eseguite dall'analizzatore di espressioni.</span><span class="sxs-lookup"><span data-stu-id="c4b08-119">The intersection of the data types must be a numeric data type, as specified in the rules about the implicit numeric conversions that the expression evaluator performs.</span></span> <span data-ttu-id="c4b08-120">L'intersezione dei due tipi di dati numeric non può essere Null.</span><span class="sxs-lookup"><span data-stu-id="c4b08-120">The intersection of the two numeric data types cannot be null.</span></span> <span data-ttu-id="c4b08-121">Per altre informazioni, vedere [Tipi di dati nelle espressioni di Integration Services](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="c4b08-121">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
-   <span data-ttu-id="c4b08-122">**Character** Sia *expression1* che *expression2* devono restituire un tipo di dati DT_STR o DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="c4b08-122">**Character** Both *expression1* and *expression2* must evaluate to either a DT_STR or a DT_WSTR data type.</span></span> <span data-ttu-id="c4b08-123">Le due espressioni possono restituire tipi di dati string diversi.</span><span class="sxs-lookup"><span data-stu-id="c4b08-123">The two expressions can evaluate to different string data types.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c4b08-124">Per i confronti di stringa viene applicata la distinzione tra maiuscole e minuscole, tra caratteri accentati e non accentati, la distinzione Kana e di larghezza.</span><span class="sxs-lookup"><span data-stu-id="c4b08-124">String comparisons are case, accent, kana, and width-sensitive.</span></span>  
  
-   <span data-ttu-id="c4b08-125">**Date, Time o Date/Time** Sia *expression1* che *expression2* devono restituire uno dei tipi di dati seguenti: DT_DBDATE, DT_DATE, DT_DBTIME, DT_DBTIME2, DT_DBTIMESTAMP, DT_DBTIMESTAMP2, DT_DBTIMESTAPMOFFSET o DT_FILETIME.</span><span class="sxs-lookup"><span data-stu-id="c4b08-125">**Date, Time, or Date/Time** Both *expression1* and *expression2* must evaluate to one of the following data types: DT_DBDATE, DT_DATE, DT_DBTIME, DT_DBTIME2, DT_DBTIMESTAMP, DT_DBTIMESTAMP2, DT_DBTIMESTAPMOFFSET, or DT_FILETIME.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c4b08-126">Il sistema non supporta i confronti tra un'espressione che restituisce un tipo di dati di ora e un'espressione che restituisce una data o un tipo di dati di data/ora.</span><span class="sxs-lookup"><span data-stu-id="c4b08-126">The system does not support comparisons between an expression that evaluates to a time data type and an expression that evaluates to either a date or a date/time data type.</span></span> <span data-ttu-id="c4b08-127">Viene generato un errore.</span><span class="sxs-lookup"><span data-stu-id="c4b08-127">The system generates an error.</span></span>  
  
     <span data-ttu-id="c4b08-128">In caso di confronto delle espressioni, vengono applicate le regole di conversione seguenti nell'ordine elencato:</span><span class="sxs-lookup"><span data-stu-id="c4b08-128">When comparing the expressions, the system applies the following conversion rules in the order listed:</span></span>  
  
    -   <span data-ttu-id="c4b08-129">Quando le due espressioni restituiscono lo stesso tipo di dati, viene effettuato un confronto del tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="c4b08-129">When the two expressions evaluate to the same data type, a comparison of that data type is performed.</span></span>  
  
    -   <span data-ttu-id="c4b08-130">Se un'espressione è un tipo di dati DT_DBTIMESTAMPOFFSET, l'altra espressione viene convertita implicitamente in DT_DBTIMESTAMPOFFSET e viene eseguito un confronto DT_DBTIMESTAMPOFFSET.</span><span class="sxs-lookup"><span data-stu-id="c4b08-130">If one expression is a DT_DBTIMESTAMPOFFSET data type, the other expression is implicitly converted to DT_DBTIMESTAMPOFFSET and a DT_DBTIMESTAMPOFFSET comparison is performed.</span></span> <span data-ttu-id="c4b08-131">Per altre informazioni, vedere [Tipi di dati nelle espressioni di Integration Services](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="c4b08-131">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
    -   <span data-ttu-id="c4b08-132">Se un'espressione è un tipo di dati DT_DBTIMESTAMP2, l'altra espressione viene convertita implicitamente in DT_DBTIMESTAMP2 e viene eseguito un confronto DT_DBTIMESTAMP2.</span><span class="sxs-lookup"><span data-stu-id="c4b08-132">If one expression is a DT_DBTIMESTAMP2 data type, the other expression is implicitly converted to DT_DBTIMESTAMP2 and a DT_DBTIMESTAMP2 comparison is performed.</span></span>  
  
    -   <span data-ttu-id="c4b08-133">Se un'espressione è un tipo di dati DT_DBTIME2, l'altra espressione viene convertita implicitamente in DT_DBTIME2 e viene eseguito un confronto DT_DBTIME2.</span><span class="sxs-lookup"><span data-stu-id="c4b08-133">If one expression is a DT_DBTIME2 data type, the other expression is implicitly converted to DT_DBTIME2, and a DT_DBTIME2 comparison is performed.</span></span>  
  
    -   <span data-ttu-id="c4b08-134">Se un'espressione è di un tipo diverso da DT_DBTIMESTAMPOFFSET, DT_DBTIMESTAMP2 o DT_DBTIME2, le espressioni vengono convertite nel tipo di dati DT_DBTIMESTAMP prima del confronto.</span><span class="sxs-lookup"><span data-stu-id="c4b08-134">If one expression is of a type other than DT_DBTIMESTAMPOFFSET, DT_DBTIMESTAMP2, or DT_DBTIME2, the expressions are converted to the DT_DBTIMESTAMP data type before they are compared.</span></span>  
  
     <span data-ttu-id="c4b08-135">In caso di confronto delle espressioni, il sistema presuppone quanto segue:</span><span class="sxs-lookup"><span data-stu-id="c4b08-135">When comparing the expressions, the system makes the following assumptions:</span></span>  
  
    -   <span data-ttu-id="c4b08-136">Se ogni espressione è un tipo di dati che include secondi frazionari, il sistema presuppone che il tipo di dati con il numero di cifre più basso per secondi frazionari presenti un valore pari a zero per le cifre rimanenti.</span><span class="sxs-lookup"><span data-stu-id="c4b08-136">If each expression is a data type that includes fractional seconds, the system assumes that the data type with the least number of digits for fractional seconds has zeros for the remaining digits.</span></span>  
  
    -   <span data-ttu-id="c4b08-137">Se ogni espressione è un tipo di dati relativo alla data, ma solo una dispone di una differenza di fuso orario, il sistema presuppone che il tipo di dati senza la differenza di fuso orario sia espresso in formato UTC (Coordinated Universal Time).</span><span class="sxs-lookup"><span data-stu-id="c4b08-137">If each expression is a date data type, but only one has a time zone offset, the system assumes that the date data type without the time zone offset is in Coordinated Universal Time (UTC).</span></span>  
  
-   <span data-ttu-id="c4b08-138">**Logical** Sia *expression1* che *expression2* devono restituire un valore booleano.</span><span class="sxs-lookup"><span data-stu-id="c4b08-138">**Logical** Both *expression1* and *expression2* must evaluate to a Boolean.</span></span>  
  
-   <span data-ttu-id="c4b08-139">**GUID** Sia *expression1* che *expression2* devono restituire il tipo di dati DT_GUID.</span><span class="sxs-lookup"><span data-stu-id="c4b08-139">**GUID** Both *expression1* and *expression2* must evaluate to the DT_GUID data type.</span></span>  
  
-   <span data-ttu-id="c4b08-140">**Binary** Sia *expression1* che *expression2* devono restituire il tipo di dati DT_BYTES.</span><span class="sxs-lookup"><span data-stu-id="c4b08-140">**Binary** Both *expression1* and *expression2* must evaluate to the DT_BYTES data type.</span></span>  
  
-   <span data-ttu-id="c4b08-141">**BLOB** Sia *expression1* che *expression2* devono restituire lo stesso tipo di dati BLOB (Binary Large Object Block), cioè DT_TEXT, DT_NTEXT o DT_IMAGE.</span><span class="sxs-lookup"><span data-stu-id="c4b08-141">**BLOB** Both *expression1* and *expression2* must evaluate to the same Binary Large Object Block (BLOB) data type: DT_TEXT, DT_NTEXT, or DT_IMAGE.</span></span>  
  
 <span data-ttu-id="c4b08-142">Per altre informazioni sui tipi di dati, vedere [Tipi di dati di Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="c4b08-142">For more information about data types, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="c4b08-143">Esempi di espressione</span><span class="sxs-lookup"><span data-stu-id="c4b08-143">Expression Examples</span></span>  
 <span data-ttu-id="c4b08-144">In questo esempio viene restituito TRUE se la data corrente è il 4 luglio 2003.</span><span class="sxs-lookup"><span data-stu-id="c4b08-144">This example evaluates to TRUE if the current date is July 4, 2003.</span></span> <span data-ttu-id="c4b08-145">Per altre informazioni, vedere [GETDATE &#40;espressione SSIS&#41;](getdate-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="c4b08-145">For more information, see [GETDATE &#40;SSIS Expression&#41;](getdate-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="c4b08-146">"7/4/2003" == GETDATE()</span><span class="sxs-lookup"><span data-stu-id="c4b08-146">"7/4/2003" == GETDATE()</span></span>  
  
 <span data-ttu-id="c4b08-147">In questo esempio viene restituito TRUE se il valore nella colonna **ListPrice** è 500.</span><span class="sxs-lookup"><span data-stu-id="c4b08-147">This example evaluates to TRUE if the value in the **ListPrice** column is 500.</span></span>  
  
```  
ListPrice == 500  
```  
  
 <span data-ttu-id="c4b08-148">In questo esempio viene usata la variabile **LPrice**.</span><span class="sxs-lookup"><span data-stu-id="c4b08-148">This example uses the variable **LPrice**.</span></span> <span data-ttu-id="c4b08-149">Viene restituito TRUE se il valore di **LPrice** è 500.</span><span class="sxs-lookup"><span data-stu-id="c4b08-149">It evaluates to TRUE if the value of **LPrice** is 500.</span></span> <span data-ttu-id="c4b08-150">Per consentire la corretta analisi dell'espressione, il tipo di dati della variabile deve essere numeric.</span><span class="sxs-lookup"><span data-stu-id="c4b08-150">The data type of the variable must be numeric for the expression to parse successfully.</span></span>  
  
```  
@LPrice == 500  
```  
  
## <a name="see-also"></a><span data-ttu-id="c4b08-151">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c4b08-151">See Also</span></span>  
 <span data-ttu-id="c4b08-152">[\! = &#40;diverso da&#41; &#40;espressione SSIS&#41;](equal-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="c4b08-152">[!= &#40;Unequal&#41; &#40;SSIS Expression&#41;](equal-ssis-expression.md) </span></span>  
 <span data-ttu-id="c4b08-153">[Precedenza e associatività degli operatori](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="c4b08-153">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="c4b08-154">Operatori &#40;espressione SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="c4b08-154">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
