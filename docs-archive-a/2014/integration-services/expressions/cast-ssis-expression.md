---
title: Cast (espressione SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- CAST function
- cast operator
- converting data types [Integration Services]
- data types [Integration Services], expressions
- data types [Integration Services], converting
ms.assetid: d4e915cc-1c7b-4b2e-93b0-13a8b0cb9242
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 65d60eca4340b65b8a82855c3f2b29a6cda56e15
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721672"
---
# <a name="cast-ssis-expression"></a><span data-ttu-id="7d1e9-102">Cast (espressione SSIS)</span><span class="sxs-lookup"><span data-stu-id="7d1e9-102">Cast (SSIS Expression)</span></span>
  <span data-ttu-id="7d1e9-103">Viene convertita esplicitamente un'espressione da un tipo di dati a un altro.</span><span class="sxs-lookup"><span data-stu-id="7d1e9-103">Explicitly converts an expression from one data type to a different data type.</span></span> <span data-ttu-id="7d1e9-104">L'operatore cast può essere utilizzato anche come operatore di troncamento.</span><span class="sxs-lookup"><span data-stu-id="7d1e9-104">The cast operator can also function as a truncation operator.</span></span>

## <a name="syntax"></a><span data-ttu-id="7d1e9-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7d1e9-105">Syntax</span></span>

```

(type_spec) expression

```

## <a name="arguments"></a><span data-ttu-id="7d1e9-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="7d1e9-106">Arguments</span></span>
 <span data-ttu-id="7d1e9-107">*type_spec* È un [!INCLUDE[ssIS](../../includes/ssis-md.md)] tipo di dati valido.</span><span class="sxs-lookup"><span data-stu-id="7d1e9-107">*type_spec* Is a valid [!INCLUDE[ssIS](../../includes/ssis-md.md)] data type.</span></span>

 <span data-ttu-id="7d1e9-108">*espressione* Espressione valida.</span><span class="sxs-lookup"><span data-stu-id="7d1e9-108">*expression* Is a valid expression.</span></span>

## <a name="result-types"></a><span data-ttu-id="7d1e9-109">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="7d1e9-109">Result Types</span></span>
 <span data-ttu-id="7d1e9-110">Tipo di dati *type_spec*.</span><span class="sxs-lookup"><span data-stu-id="7d1e9-110">The data type of *type_spec*.</span></span> <span data-ttu-id="7d1e9-111">Per altre informazioni, vedere [Tipi di dati di Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="7d1e9-111">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>

## <a name="remarks"></a><span data-ttu-id="7d1e9-112">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="7d1e9-112">Remarks</span></span>
 <span data-ttu-id="7d1e9-113">Nella figura seguente vengono illustrate alcune operazioni di cast valide.</span><span class="sxs-lookup"><span data-stu-id="7d1e9-113">The following diagram shows legal cast operations.</span></span>

 <span data-ttu-id="7d1e9-114">![Cast validi e non validi tra tipi di dati](../media/data-conversion.gif "Cast validi e non validi tra tipi di dati")</span><span class="sxs-lookup"><span data-stu-id="7d1e9-114">![Legal and not legal casts between data types](../media/data-conversion.gif "Legal and not legal casts between data types")</span></span>

 <span data-ttu-id="7d1e9-115">Per eseguire il cast a determinati tipi di dati è necessario specificare i parametri appropriati.</span><span class="sxs-lookup"><span data-stu-id="7d1e9-115">Casting to some data types requires parameters.</span></span> <span data-ttu-id="7d1e9-116">Nella tabella seguente vengono elencati tali tipi di dati e i parametri corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="7d1e9-116">The following table lists these data types and their parameters.</span></span>

|<span data-ttu-id="7d1e9-117">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="7d1e9-117">Data type</span></span>|<span data-ttu-id="7d1e9-118">Parametro</span><span class="sxs-lookup"><span data-stu-id="7d1e9-118">Parameter</span></span>|<span data-ttu-id="7d1e9-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="7d1e9-119">Example</span></span>|
|---------------|---------------|-------------|
|<span data-ttu-id="7d1e9-120">DT_STR</span><span class="sxs-lookup"><span data-stu-id="7d1e9-120">DT_STR</span></span>|<span data-ttu-id="7d1e9-121">*charcount*</span><span class="sxs-lookup"><span data-stu-id="7d1e9-121">*charcount*</span></span><br /><br /> <span data-ttu-id="7d1e9-122">*CodePage*</span><span class="sxs-lookup"><span data-stu-id="7d1e9-122">*codepage*</span></span>|<span data-ttu-id="7d1e9-123">(DT_STR,30,1252): esegue il cast di 30 byte, ovvero 30 caratteri singoli, al tipo di dati DT_STR utilizzando la tabella codici 1252.</span><span class="sxs-lookup"><span data-stu-id="7d1e9-123">(DT_STR,30,1252) casts 30 bytes, or 30 single characters, to the DT_STR data type using the 1252 code page.</span></span>|
|<span data-ttu-id="7d1e9-124">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="7d1e9-124">DT_WSTR</span></span>|<span data-ttu-id="7d1e9-125">*CharCount*</span><span class="sxs-lookup"><span data-stu-id="7d1e9-125">*Charcount*</span></span>|<span data-ttu-id="7d1e9-126">(DT_WSTR,20): esegue il cast di 20 coppie di byte, ovvero 20 caratteri Unicode, al tipo di dati DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="7d1e9-126">(DT_WSTR,20) casts 20 byte pairs, or 20 Unicode characters, to the DT_WSTR data type.</span></span>|
|<span data-ttu-id="7d1e9-127">DT_BYTES</span><span class="sxs-lookup"><span data-stu-id="7d1e9-127">DT_BYTES</span></span>|<span data-ttu-id="7d1e9-128">*ByteCount*</span><span class="sxs-lookup"><span data-stu-id="7d1e9-128">*Bytecount*</span></span>|<span data-ttu-id="7d1e9-129">(DT_BYTES,50): esegue il cast di 50 byte al tipo di dati DT_BYTES.</span><span class="sxs-lookup"><span data-stu-id="7d1e9-129">(DT_BYTES,50) casts 50 bytes to the DT_BYTES data type.</span></span>|
|<span data-ttu-id="7d1e9-130">DT_DECIMAL</span><span class="sxs-lookup"><span data-stu-id="7d1e9-130">DT_DECIMAL</span></span>|<span data-ttu-id="7d1e9-131">*Ridimensionamento*</span><span class="sxs-lookup"><span data-stu-id="7d1e9-131">*Scale*</span></span>|<span data-ttu-id="7d1e9-132">(DT_DECIMAL,2): esegue il cast di un valore numerico al tipo di dati DT_DECIMAL, utilizzando una scala pari a 2.</span><span class="sxs-lookup"><span data-stu-id="7d1e9-132">(DT_DECIMAL,2) casts a numeric value to the DT_DECIMAL data type using a scale of 2.</span></span>|
|<span data-ttu-id="7d1e9-133">DT_NUMERIC</span><span class="sxs-lookup"><span data-stu-id="7d1e9-133">DT_NUMERIC</span></span>|<span data-ttu-id="7d1e9-134">*Precisione*</span><span class="sxs-lookup"><span data-stu-id="7d1e9-134">*Precision*</span></span><br /><br /> <span data-ttu-id="7d1e9-135">*Ridimensionamento*</span><span class="sxs-lookup"><span data-stu-id="7d1e9-135">*Scale*</span></span>|<span data-ttu-id="7d1e9-136">(DT_NUMERIC,10,3): esegue il cast di un valore numerico al tipo di dati DT_NUMERIC, utilizzando una precisione pari a 10 e una scala pari a 3.</span><span class="sxs-lookup"><span data-stu-id="7d1e9-136">(DT_NUMERIC,10,3) casts a numeric value to the DT_NUMERIC data type using a precision of 10 and a scale of 3.</span></span>|
|<span data-ttu-id="7d1e9-137">DT_TEXT</span><span class="sxs-lookup"><span data-stu-id="7d1e9-137">DT_TEXT</span></span>|<span data-ttu-id="7d1e9-138">*CodePage*</span><span class="sxs-lookup"><span data-stu-id="7d1e9-138">*Codepage*</span></span>|<span data-ttu-id="7d1e9-139">(DT_TEXT,1252): esegue il cast di un valore al tipo di dati DT_TEXT utilizzando la tabella codici 1252.</span><span class="sxs-lookup"><span data-stu-id="7d1e9-139">(DT_TEXT,1252) casts a value to the DT_TEXT data type using the 1252 code page.</span></span>|

 <span data-ttu-id="7d1e9-140">Quando si esegue il cast di una stringa a un tipo di dati DT_DATE, o viceversa, vengono utilizzate le impostazioni locali della trasformazione.</span><span class="sxs-lookup"><span data-stu-id="7d1e9-140">When a string is cast to a DT_DATE, or vice versa, the locale of the transformation is used.</span></span> <span data-ttu-id="7d1e9-141">Tuttavia, la data è nel formato ISO AAAA-MM-GG, indipendentemente dal fatto che le impostazioni locali utilizzino il formato ISO.</span><span class="sxs-lookup"><span data-stu-id="7d1e9-141">However, the date is in the ISO format of YYYY-MM-DD, regardless of whether the locale preference uses the ISO format.</span></span>

> [!NOTE]
>  <span data-ttu-id="7d1e9-142">Per convertire una stringa in un tipo di dati date diverso da DT_DATE, vedere [Tipi di dati di Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="7d1e9-142">To convert a string to a date data type other than DT_DATE, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>

 <span data-ttu-id="7d1e9-143">Se la tabella codici è di tipo MBCS (Multibyte Character Set), il numero dei byte potrebbe non corrispondere a quello dei caratteri.</span><span class="sxs-lookup"><span data-stu-id="7d1e9-143">If the code page is a multibyte character code page, the number of bytes and characters may differ.</span></span> <span data-ttu-id="7d1e9-144">Il cast da DT_WSTR a DT_STR con lo stesso valore di *charcount* potrebbe provocare il troncamento dei caratteri finali nella stringa convertita.</span><span class="sxs-lookup"><span data-stu-id="7d1e9-144">Casting from a DT_WSTR to a DT_STR with the same *charcount* value may cause truncation of the final characters in the converted string.</span></span> <span data-ttu-id="7d1e9-145">Se nella colonna della tabella di destinazione è disponibile spazio di archiviazione sufficiente, impostare il valore del parametro *charcount* in modo da riflettere il numero di byte richiesto dalla tabella codici MBCS.</span><span class="sxs-lookup"><span data-stu-id="7d1e9-145">If sufficient storage is available in the column of the destination table, set the value of the *charcount* parameter to reflect the number of bytes that the multibyte code page requires.</span></span> <span data-ttu-id="7d1e9-146">Se ad esempio si esegue il cast di dati di tipo carattere a un tipo di dati DT_STR usando la tabella codici 936, sarà necessario impostare *charcount* su un valore fino a due volte più grande del numero di caratteri che si prevede sarà contenuto nei dati. Se si esegue il cast di dati di tipo carattere utilizzando la tabella codici UTF-8, sarà necessario impostare *charcount* su un valore fino a quattro volte più grande.</span><span class="sxs-lookup"><span data-stu-id="7d1e9-146">For example, if you cast character data to a DT_STR data type using the 936 code page, you should set *charcount* to a value up to two times greater than the number of characters that you expect the data to contain; if you cast character data using the UTF-8 code page, you should set *charcount* to a value up to four times greater.</span></span>

 <span data-ttu-id="7d1e9-147">Per altre informazioni sulla struttura dei tipi di dati di data, vedere [Tipi di dati di Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="7d1e9-147">For more information about the structure of date data types, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>

## <a name="ssis-expression-examples"></a><span data-ttu-id="7d1e9-148">Esempi di espressione SSIS</span><span class="sxs-lookup"><span data-stu-id="7d1e9-148">SSIS Expression Examples</span></span>
 <span data-ttu-id="7d1e9-149">In questo esempio viene eseguito il cast di un valore numerico a un valore integer.</span><span class="sxs-lookup"><span data-stu-id="7d1e9-149">This example casts a numeric value to an integer.</span></span>

```
(DT_I4) 3.57
```

 <span data-ttu-id="7d1e9-150">In questo esempio viene eseguito il cast di un valore integer a una stringa di caratteri utilizzando la tabella codici 1252.</span><span class="sxs-lookup"><span data-stu-id="7d1e9-150">This example casts an integer to a character string using the 1252 code page.</span></span>

```
(DT_STR,1,1252)5
```

 <span data-ttu-id="7d1e9-151">In questo esempio viene eseguito il cast di una stringa di tre caratteri a caratteri DBCS (Double-Byte Character Set).</span><span class="sxs-lookup"><span data-stu-id="7d1e9-151">This example casts a three-character string to double-byte characters.</span></span>

```
(DT_WSTR,3)"Cat"
```

 <span data-ttu-id="7d1e9-152">In questo esempio viene eseguito il cast di un valore integer a un valore decimale con scala pari a 2.</span><span class="sxs-lookup"><span data-stu-id="7d1e9-152">This example casts an integer to a decimal with a scale of two.</span></span>

```
(DT_DECIMAl,2)500
```

 <span data-ttu-id="7d1e9-153">In questo esempio viene eseguito il cast di un valore integer a un valore numerico con precisione pari a 7 e scala pari a 3.</span><span class="sxs-lookup"><span data-stu-id="7d1e9-153">This example casts an integer to a numeric with a precision of seven and scale of three.</span></span>

```
(DT_NUMERIC,7,3)4000
```

 <span data-ttu-id="7d1e9-154">In questo esempio viene eseguito il cast dei valori nella colonna **FirstName** , definita con un tipo di dati **nvarchar** e lunghezza 50, a una stringa di caratteri tramite la tabella codici 1252.</span><span class="sxs-lookup"><span data-stu-id="7d1e9-154">This example casts values in the **FirstName** column, defined with an **nvarchar** data type and a length of 50, to a character string using the 1252 code page.</span></span>

```
(DT_STR,50,1252)FirstName
```

 <span data-ttu-id="7d1e9-155">In questo esempio viene eseguito il cast dei valori nella colonna **DateFirstPurchase** di tipo DT_DBDATE a una stringa di caratteri Unicode con lunghezza 20.</span><span class="sxs-lookup"><span data-stu-id="7d1e9-155">This example casts values in the **DateFirstPurchase** column of type DT_DBDATE, to a Unicode character string with a length of 20.</span></span>

```
(DT_WSTR,20)DateFirstPurchase
```

 <span data-ttu-id="7d1e9-156">In questo esempio viene eseguito il cast del valore letterale stringa "True" a un valore booleano.</span><span class="sxs-lookup"><span data-stu-id="7d1e9-156">This example casts the string literal "True" to a Boolean.</span></span>

```
(DT_BOOL)"True"
```

 <span data-ttu-id="7d1e9-157">In questo esempio viene eseguito il cast di un valore letterale stringa a DT_DBDATE.</span><span class="sxs-lookup"><span data-stu-id="7d1e9-157">This example casts a string literal to DT_DBDATE.</span></span>

```
(DT_DBDATE) "1999-10-11"
```

 <span data-ttu-id="7d1e9-158">In questo esempio viene eseguito il cast di un valore letterale stringa al tipo di dati DT_DBTIME2 che utilizza 5 cifre per i secondi frazionari.</span><span class="sxs-lookup"><span data-stu-id="7d1e9-158">This example casts a string literal to the DT_DBTIME2 data type that uses 5 digits for fractional seconds.</span></span> <span data-ttu-id="7d1e9-159">Nel tipo di dati DT_DBTIME2 possono essere specificate da 0 a 7 cifre per i secondi frazionari.</span><span class="sxs-lookup"><span data-stu-id="7d1e9-159">(The DT_DBTIME2 data type can have between 0 and 7 digits specified for fractional seconds.)</span></span>

```
(DT_DBTIME2, 5) "16:34:52.12345"
```

 <span data-ttu-id="7d1e9-160">In questo esempio viene eseguito il cast di un valore letterale stringa al tipo di dati DT_DBTIMESTAMP2 che utilizza 4 cifre per i secondi frazionari.</span><span class="sxs-lookup"><span data-stu-id="7d1e9-160">This example casts a string literal to the DT_DBTIMESTAMP2 data type that uses 4 digits for fractional seconds.</span></span> <span data-ttu-id="7d1e9-161">Nel tipo di dati DT_DBTIMESTAMP2 possono essere specificate da 0 a 7 cifre per i secondi frazionari.</span><span class="sxs-lookup"><span data-stu-id="7d1e9-161">(The DT_DBTIMESTAMP2 data type can have between 0 and 7 digits specified for fractional seconds.)</span></span>

```
(DT_DBTIMESTAMP2, 4) "1999-10-11 16:34:52.1234"
```

 <span data-ttu-id="7d1e9-162">In questo esempio viene eseguito il cast di un valore letterale stringa al tipo di dati DT_DBTIMESTAMPOFFSET che utilizza 7 cifre per i secondi frazionari.</span><span class="sxs-lookup"><span data-stu-id="7d1e9-162">This example casts a string literal to the DT_DBTIMESTAMPOFFSET data type that uses 7 digits for fractional seconds.</span></span> <span data-ttu-id="7d1e9-163">Nel tipo di dati DT_DBTIMESTAMPOFFSET possono essere specificate da 0 a 7 cifre per i secondi frazionari.</span><span class="sxs-lookup"><span data-stu-id="7d1e9-163">(The DT_DBTIMESTAMPOFFSET data typecan have between 0 and 7 digits specified for fractional seconds.)</span></span>

```
(DT_DBTIMESTAMPOFFSET, 7) "1999-10-11 16:34:52.1234567 + 5:35"
```

## <a name="see-also"></a><span data-ttu-id="7d1e9-164">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7d1e9-164">See Also</span></span>
 <span data-ttu-id="7d1e9-165">Operatori di [precedenza e associatività](operator-precedence-and-associativity.md) [degli operatori &#40;espressione ssis&#41;](operators-ssis-expression.md) [Integration Services &#40;espressioni SSIS&#41;](integration-services-ssis-expressions.md) [Integration Services tipi di dati nelle espressioni](integration-services-data-types-in-expressions.md)</span><span class="sxs-lookup"><span data-stu-id="7d1e9-165">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) [Operators &#40;SSIS Expression&#41;](operators-ssis-expression.md) [Integration Services &#40;SSIS&#41; Expressions](integration-services-ssis-expressions.md) [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md)</span></span>


