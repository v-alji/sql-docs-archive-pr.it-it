---
title: RTRIM (espressione SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- RTRIM function
- trailing blanks
ms.assetid: 529bd43e-3f8a-4682-a33e-569176aa7fc4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 727c30fd72bfca5676b71f4ba42e936a9b926817
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716484"
---
# <a name="rtrim-ssis-expression"></a><span data-ttu-id="8a597-102">RTRIM (espressione SSIS)</span><span class="sxs-lookup"><span data-stu-id="8a597-102">RTRIM (SSIS Expression)</span></span>
  <span data-ttu-id="8a597-103">Viene restituita un'espressione di caratteri dopo aver rimosso gli spazi finali.</span><span class="sxs-lookup"><span data-stu-id="8a597-103">Returns a character expression after removing trailing spaces.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8a597-104">RTRIM non rimuove altri caratteri spazio quali i caratteri di tabulazione o avanzamento riga.</span><span class="sxs-lookup"><span data-stu-id="8a597-104">RTRIM does not remove white space characters such as the tab or line feed characters.</span></span> <span data-ttu-id="8a597-105">Unicode offre elementi di codice per molti tipi diversi di spazi, ma questa funzione riconosce solo l'elemento di codice Unicode 0x0020.</span><span class="sxs-lookup"><span data-stu-id="8a597-105">Unicode provides code points for many different types of spaces, but this function recognizes only the Unicode code point 0x0020.</span></span> <span data-ttu-id="8a597-106">Quando stringhe DBCS (Double-Byte Character Set) vengono convertite in Unicode, possono includere caratteri spazio diversi da 0x0020 e la funzione non può rimuovere tali spazi.</span><span class="sxs-lookup"><span data-stu-id="8a597-106">When double-byte character set (DBCS) strings are converted to Unicode they may include space characters other than 0x0020 and the function cannot remove such spaces.</span></span> <span data-ttu-id="8a597-107">Per rimuovere qualsiasi tipo di spazi, è possibile utilizzare il metodo Microsoft Visual Basic .NET RTrim in uno script eseguito dal componente Script.</span><span class="sxs-lookup"><span data-stu-id="8a597-107">To remove all kinds of spaces, you can use the Microsoft Visual Basic .NET RTrim method in a script run from the Script component.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a597-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8a597-108">Syntax</span></span>  
  
```  
  
RTRIM(character expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="8a597-109">Argomenti</span><span class="sxs-lookup"><span data-stu-id="8a597-109">Arguments</span></span>  
 <span data-ttu-id="8a597-110">*character_expression*</span><span class="sxs-lookup"><span data-stu-id="8a597-110">*character_expression*</span></span>  
 <span data-ttu-id="8a597-111">Espressione di caratteri da cui rimuovere gli spazi.</span><span class="sxs-lookup"><span data-stu-id="8a597-111">Is a character expression from which to remove spaces.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="8a597-112">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="8a597-112">Result Types</span></span>  
 <span data-ttu-id="8a597-113">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="8a597-113">DT_WSTR</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8a597-114">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="8a597-114">Remarks</span></span>  
 <span data-ttu-id="8a597-115">È possibile utilizzare RTRIM solo con il tipo di dati DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="8a597-115">RTRIM works only with the DT_WSTR data type.</span></span> <span data-ttu-id="8a597-116">Se l'argomento *character_expression* è un valore letterale stringa o una colonna di dati con tipo di dati DT_STR, prima di eseguire l'operazione prevista da RTRIM verrà eseguito il cast implicito al tipo di dati DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="8a597-116">A *character_expression* argument that is a string literal or a data column with the DT_STR data type is implicitly cast to the DT_WSTR data type before RTRIM performs its operation.</span></span> <span data-ttu-id="8a597-117">Per gli altri tipi di dati è necessario il cast esplicito al tipo di dati DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="8a597-117">Other data types must be explicitly cast to the DT_WSTR data type.</span></span> <span data-ttu-id="8a597-118">Per altre informazioni, vedere [Tipi di dati di Integration Services](../data-flow/integration-services-data-types.md) e [Cast &#40;espressione SSIS&#41;](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="8a597-118">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md) and [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="8a597-119">Se l'argomento è Null, RTRIM restituirà Null.</span><span class="sxs-lookup"><span data-stu-id="8a597-119">RTRIM returns a null result if the argument is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="8a597-120">Esempi di espressione</span><span class="sxs-lookup"><span data-stu-id="8a597-120">Expression Examples</span></span>  
 <span data-ttu-id="8a597-121">In questo esempio vengono rimossi gli spazi finali da un valore letterale stringa.</span><span class="sxs-lookup"><span data-stu-id="8a597-121">This example removes trailing spaces from a string literal.</span></span> <span data-ttu-id="8a597-122">Il risultato restituito è "Hello".</span><span class="sxs-lookup"><span data-stu-id="8a597-122">The return result is "Hello".</span></span>  
  
```  
RTRIM("Hello   ")  
```  
  
 <span data-ttu-id="8a597-123">In questo esempio vengono rimossi gli spazi finali dal risultato della concatenazione delle colonne **FirstName** e **LastName** .</span><span class="sxs-lookup"><span data-stu-id="8a597-123">This example removes trailing spaces from a concatenation of the **FirstName** and **LastName** columns.</span></span>  
  
```  
RTRIM(FirstName + " " + LastName)  
```  
  
 <span data-ttu-id="8a597-124">In questo esempio vengono rimossi gli spazi finali dalla variabile **FirstName** .</span><span class="sxs-lookup"><span data-stu-id="8a597-124">This example removes trailing spaces from the **FirstName** variable.</span></span>  
  
```  
RTRIM(@FirstName)  
```  
  
## <a name="see-also"></a><span data-ttu-id="8a597-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8a597-125">See Also</span></span>  
 <span data-ttu-id="8a597-126">[LTRIM &#40;espressione SSIS&#41;](trim-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="8a597-126">[LTRIM &#40;SSIS Expression&#41;](trim-ssis-expression.md) </span></span>  
 <span data-ttu-id="8a597-127">[TRIM &#40;espressione SSIS&#41;](trim-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="8a597-127">[TRIM &#40;SSIS Expression&#41;](trim-ssis-expression.md) </span></span>  
 [<span data-ttu-id="8a597-128">Funzioni &#40;espressione SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="8a597-128">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
