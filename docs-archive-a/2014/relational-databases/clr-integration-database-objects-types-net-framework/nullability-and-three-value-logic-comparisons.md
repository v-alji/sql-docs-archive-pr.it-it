---
title: Supporto dei valori null e confronti di logica a tre valori | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- precision [CLR integration]
- overflow detections [CLR integration]
- null values [CLR integration]
- three-value logic comparisons [CLR integration]
- data types [CLR integration]
- SqlBoolean data type
ms.assetid: 13da4c7f-1010-4b2d-a63c-c69b6bfd96f1
author: rothja
ms.author: jroth
ms.openlocfilehash: 7b8000c1c28d5a1d3d129b6e8d01c4ab2fbbbc7d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725952"
---
# <a name="nullability-and-three-value-logic-comparisons"></a><span data-ttu-id="13ccd-102">Supporto dei valori Null e confronti di logica a tre valori</span><span class="sxs-lookup"><span data-stu-id="13ccd-102">Nullability and Three-Value Logic Comparisons</span></span>
  <span data-ttu-id="13ccd-103">Se si ha familiarità con i tipi di dati di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], è possibile notare la somiglianza nella semantica e nella precisione dello spazio dei nomi `System.Data.SqlTypes` in [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="13ccd-103">If you are familiar with the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types, you will find similar semantics and precision in the `System.Data.SqlTypes` namespace in the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="13ccd-104">Esistono tuttavia alcune differenze, le più importanti delle quali sono illustrate nel presente argomento.</span><span class="sxs-lookup"><span data-stu-id="13ccd-104">There are some differences, however, and this topic covers the most important of these differences.</span></span>  
  
## <a name="null-values"></a><span data-ttu-id="13ccd-105">Valori NULL</span><span class="sxs-lookup"><span data-stu-id="13ccd-105">NULL Values</span></span>  
 <span data-ttu-id="13ccd-106">Una differenza importante tra i tipi di dati Common Language Runtime (CLR) nativi e i tipi di dati di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] consiste nel fatto che i primi non consentono valori NULL, mentre i secondi forniscono semantica NULL completa.</span><span class="sxs-lookup"><span data-stu-id="13ccd-106">A primary difference between native common language runtime (CLR) data types and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types is that the former do not allow for NULL values, while the latter provide full NULL semantics.</span></span>  
  
 <span data-ttu-id="13ccd-107">La presenza di valori NULL influisce sui confronti.</span><span class="sxs-lookup"><span data-stu-id="13ccd-107">Comparisons are affected by NULL values.</span></span> <span data-ttu-id="13ccd-108">Quando si confrontano due valori x e y, se x o y è NULL, alcuni confronti logici restituiscono un valore UNKNOWN anziché True o False.</span><span class="sxs-lookup"><span data-stu-id="13ccd-108">When comparing two values x and y, if either x or y is NULL, then some logical comparisons evaluate to an UNKNOWN value rather than true or false.</span></span>  
  
## <a name="sqlboolean-data-type"></a><span data-ttu-id="13ccd-109">Tipo di dati SqlBoolean</span><span class="sxs-lookup"><span data-stu-id="13ccd-109">SqlBoolean Data Type</span></span>  
 <span data-ttu-id="13ccd-110">Lo spazio dei nomi `System.Data.SqlTypes` introduce un tipo `SqlBoolean` per rappresentare questa logica a 3 valori.</span><span class="sxs-lookup"><span data-stu-id="13ccd-110">The `System.Data.SqlTypes` namespace introduces a `SqlBoolean` type to represent this 3-value logic.</span></span> <span data-ttu-id="13ccd-111">I confronti tra gli spazi dei nomi `SqlTypes` restituiscono un tipo di valore `SqlBoolean`.</span><span class="sxs-lookup"><span data-stu-id="13ccd-111">Comparisons between any `SqlTypes` return a `SqlBoolean` value type.</span></span> <span data-ttu-id="13ccd-112">Il valore UNKNOWN viene rappresentato dal valore Null del tipo `SqlBoolean`.</span><span class="sxs-lookup"><span data-stu-id="13ccd-112">The UNKNOWN value is represented by the null value of the `SqlBoolean` type.</span></span> <span data-ttu-id="13ccd-113">Vengono fornite le proprietà `IsTrue`, `IsFalse` e `IsNull` per controllare il valore di un tipo `SqlBoolean`.</span><span class="sxs-lookup"><span data-stu-id="13ccd-113">The properties `IsTrue`, `IsFalse`, and `IsNull` are provided to check the value of a `SqlBoolean` type.</span></span>  
  
## <a name="operations-functions-and-null-values"></a><span data-ttu-id="13ccd-114">Operazioni, funzioni e valori NULL</span><span class="sxs-lookup"><span data-stu-id="13ccd-114">Operations, Functions, and NULL Values</span></span>  
 <span data-ttu-id="13ccd-115">Tutti gli operatori aritmetici (+,-, \* ,/,%), gli operatori bit per bit (~, & e |) e la maggior parte delle funzioni restituiscono null se uno degli operandi o degli argomenti di `SqlTypes` è null.</span><span class="sxs-lookup"><span data-stu-id="13ccd-115">All arithmetic operators (+, -, \*, /, %), bitwise operators (~, &, and |), and most functions return NULL if any of the operands or arguments of `SqlTypes` are NULL.</span></span> <span data-ttu-id="13ccd-116">La proprietà `IsNull` restituisce sempre un valore True o False.</span><span class="sxs-lookup"><span data-stu-id="13ccd-116">The `IsNull` property always returns a true or false value.</span></span>  
  
## <a name="precision"></a><span data-ttu-id="13ccd-117">Precisione</span><span class="sxs-lookup"><span data-stu-id="13ccd-117">Precision</span></span>  
 <span data-ttu-id="13ccd-118">I valori massimi dei tipi di dati decimali CLR di [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] sono diversi da quelli dei tipi di dati numerici e decimali di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="13ccd-118">Decimal data types in the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] CLR have different maximum values than those of the numeric and decimal data types in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="13ccd-119">Per i tipi di dati CLR decimali di [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], inoltre, si presuppone la massima precisione.</span><span class="sxs-lookup"><span data-stu-id="13ccd-119">In addition, in the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] CLR decimal data types assume the maximum precision.</span></span> <span data-ttu-id="13ccd-120">Nei tipi di dati CLR per [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], tuttavia, `SqlDecimal` fornisce la stessa scala e precisione massima e la stessa semantica del tipo di dati decimali di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="13ccd-120">In the CLR for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], however, `SqlDecimal` provides the same maximum precision and scale, and the same semantics as the decimal data type in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="overflow-detection"></a><span data-ttu-id="13ccd-121">Rilevamento dell'overflow</span><span class="sxs-lookup"><span data-stu-id="13ccd-121">Overflow Detection</span></span>  
 <span data-ttu-id="13ccd-122">Nei tipi di dati CLR di [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] è possibile che l'aggiunta di due numeri molto grandi non generi un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="13ccd-122">In the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] CLR, the addition of two very large numbers may not throw an exception.</span></span> <span data-ttu-id="13ccd-123">Se invece non è stato utilizzato alcun operatore di controllo, il risultato restituito potrebbe essere un numero intero negativo.</span><span class="sxs-lookup"><span data-stu-id="13ccd-123">Instead, if no check operator has been used, the returned result may "wrap around" as a negative integer.</span></span> <span data-ttu-id="13ccd-124">In `System.Data.SqlTypes` vengono generate eccezioni per tutti gli errori di overflow e underflow e per gli errori dovuti alla divisione per zero.</span><span class="sxs-lookup"><span data-stu-id="13ccd-124">In `System.Data.SqlTypes`, exceptions are thrown for all overflow and underflow errors, and divide-by-zero errors.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13ccd-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="13ccd-125">See Also</span></span>  
 [<span data-ttu-id="13ccd-126">Tipi di dati di SQL Server in .NET Framework</span><span class="sxs-lookup"><span data-stu-id="13ccd-126">SQL Server Data Types in the .NET Framework</span></span>](sql-server-data-types-in-the-net-framework.md)  
  
  
