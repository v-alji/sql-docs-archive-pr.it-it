---
title: + (concatenazione) (espressione SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- concatenation [Integration Services]
- + (concatenate operator)
- concatenate operator (+)
ms.assetid: 0fed6334-7a4f-42dc-a611-191fcaa0e443
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1c01f82a50962f42862db836171b0ad683c97453
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716544"
---
# <a name="-concatenate-ssis-expression"></a><span data-ttu-id="8c45f-102">+ (concatenazione) (espressione SSIS)</span><span class="sxs-lookup"><span data-stu-id="8c45f-102">+ (Concatenate) (SSIS Expression)</span></span>
  <span data-ttu-id="8c45f-103">Vengono concatenate due espressioni in modo da formare un'unica espressione.</span><span class="sxs-lookup"><span data-stu-id="8c45f-103">Concatenates two expressions into one expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c45f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8c45f-104">Syntax</span></span>  
  
```  
  
character_expression1 + character_expression2  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="8c45f-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="8c45f-105">Arguments</span></span>  
 <span data-ttu-id="8c45f-106">*expression1, expression2*</span><span class="sxs-lookup"><span data-stu-id="8c45f-106">*expression1, expression2*</span></span>  
 <span data-ttu-id="8c45f-107">Qualsiasi espressione valida con tipo di dati DT_STR, DT_WSTR, DT_TEXT, DT_NTEXT o DT_IMAGE.</span><span class="sxs-lookup"><span data-stu-id="8c45f-107">Is any valid DT_STR, DT_WSTR, DT_TEXT, DT_NTEXT, or DT_IMAGE data type expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="8c45f-108">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="8c45f-108">Result Types</span></span>  
 <span data-ttu-id="8c45f-109">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="8c45f-109">DT_WSTR</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8c45f-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="8c45f-110">Remarks</span></span>  
 <span data-ttu-id="8c45f-111">Nell'espressione è possibile utilizzare sia il tipo di dati DT_STR che il tipo di dati DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="8c45f-111">The expression can use either or both of the DT_STR and DT_WSTR data types.</span></span>  
  
 <span data-ttu-id="8c45f-112">La concatenazione dei tipi di dati DT_STR e DT_WSTR restituisce un risultato di tipo DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="8c45f-112">The concatenation of the DT_STR and DT_WSTR data types returns a result of the DT_WSTR type.</span></span> <span data-ttu-id="8c45f-113">La lunghezza della stringa risultante è data dalla somma della lunghezza in caratteri delle due stringhe di origine.</span><span class="sxs-lookup"><span data-stu-id="8c45f-113">The length of the string is the sum of the lengths of the original strings expressed in characters.</span></span>  
  
 <span data-ttu-id="8c45f-114">È possibile concatenare solo dati con tipo di dati string DT_STR o DT_WSTR oppure dati con tipo di dati BLOB (Binary Large Object) DT_TEXT, DT_NTEXT o DT_IMAGE.</span><span class="sxs-lookup"><span data-stu-id="8c45f-114">Only data with the string data types DT_STR and DT_WSTR or the Binary Large Object Block (BLOB) data types DT_TEXT, DT_NTEXT, and DT_IMAGE can be concatenated.</span></span> <span data-ttu-id="8c45f-115">Per concatenare altri tipi di dati è prima necessario convertirli esplicitamente in uno dei tipi di dati indicati in precedenza.</span><span class="sxs-lookup"><span data-stu-id="8c45f-115">Other data types must be explicitly converted to one of these data types before concatenation occurs.</span></span> <span data-ttu-id="8c45f-116">Per altre informazioni sui cast supportati tra tipi di dati, vedere [Cast &#40;espressione SSIS&#41;](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="8c45f-116">For more information about legal casts between data types, see [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="8c45f-117">È necessario che le due espressioni abbiano lo stesso tipo di dati oppure che un'espressione possa essere convertita in modo implicito nel tipo di dati dell'altra.</span><span class="sxs-lookup"><span data-stu-id="8c45f-117">Both expressions must be of the same data type, or one expression must be implicitly convertible to the data type of the other expression.</span></span> <span data-ttu-id="8c45f-118">Se ad esempio si concatenano la stringa "Order date is " e la colonna **OrderDate** , i valori in **OrderDate** verranno convertiti in modo implicito in un tipo di dati string.</span><span class="sxs-lookup"><span data-stu-id="8c45f-118">For example, if the string "Order date is " and the column **OrderDate** are concatenated, the values in **OrderDate** are implicitly converted to a string data type.</span></span> <span data-ttu-id="8c45f-119">Per concatenare due valori numerici, è necessario eseguire il cast esplicito di entrambi a un tipo di dati string.</span><span class="sxs-lookup"><span data-stu-id="8c45f-119">To concatenate two numeric values, both numeric values must be explicitly cast to a string data type.</span></span>  
  
 <span data-ttu-id="8c45f-120">In un'operazione di concatenazione è possibile utilizzare un solo tipo di dati BLOB: DT_TEXT, DT_NTEXT o DT_IMAGE.</span><span class="sxs-lookup"><span data-stu-id="8c45f-120">A concatenation can use only one BLOB data type: DT_TEXT, DT_NTEXT, or DT_IMAGE.</span></span>  
  
 <span data-ttu-id="8c45f-121">Se uno degli elementi è Null, il risultato sarà Null.</span><span class="sxs-lookup"><span data-stu-id="8c45f-121">If either element is null, the result is null.</span></span>  
  
 <span data-ttu-id="8c45f-122">I valori letterali stringa devono essere racchiusi tra virgolette.</span><span class="sxs-lookup"><span data-stu-id="8c45f-122">String literals must be enclosed in quotation marks.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="8c45f-123">Esempi di espressione</span><span class="sxs-lookup"><span data-stu-id="8c45f-123">Expression Examples</span></span>  
 <span data-ttu-id="8c45f-124">In questo esempio vengono concatenati i valori delle colonne **FirstName** e **LastName** , separandoli con uno spazio.</span><span class="sxs-lookup"><span data-stu-id="8c45f-124">This example concatenates the values in the **FirstName** and **LastName** columns and inserts a space between them.</span></span>  
  
```  
FirstName + ' ' + LastName  
```  
  
 <span data-ttu-id="8c45f-125">In questo esempio vengono concatenate le variabili **ZIPCode** e **ZIPCode+4**,</span><span class="sxs-lookup"><span data-stu-id="8c45f-125">This example concatenates the variables **ZIPCode** and **ZIPCode+4**.</span></span> <span data-ttu-id="8c45f-126">che hanno entrambe un tipo di dati string.</span><span class="sxs-lookup"><span data-stu-id="8c45f-126">Both variables have a string data type.</span></span> <span data-ttu-id="8c45f-127">Poiché il nome della variabile**ZIPCode+4** include il carattere +, deve essere racchiuso tra parentesi quadre.</span><span class="sxs-lookup"><span data-stu-id="8c45f-127">**ZIPCode+4** must be enclosed in brackets because the variable name includes the + character.</span></span>  
  
```  
@ZIPCcode + "-" + @[ZipCode+4]  
```  
  
## <a name="see-also"></a><span data-ttu-id="8c45f-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8c45f-128">See Also</span></span>  
 <span data-ttu-id="8c45f-129">[Precedenza e associatività degli operatori](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="8c45f-129">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="8c45f-130">Operatori &#40;espressione SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="8c45f-130">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
