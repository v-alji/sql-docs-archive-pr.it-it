---
title: Formati di dati numerici | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- integer data types [Integration Services]
- numeric data formats for fast parse
- locale-sensitive parsing [Integration Services]
- fast parse [Integration Services]
ms.assetid: fa3975ce-9d21-408a-857d-f85e30af27b0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: cc54a331c3762e31ba9d9a431aaca7eda6374d8c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628797"
---
# <a name="numeric-data-formats"></a><span data-ttu-id="ac888-102">Formati di dati numerici</span><span class="sxs-lookup"><span data-stu-id="ac888-102">Numeric Data Formats</span></span>
  <span data-ttu-id="ac888-103">L'analisi veloce offre un set di routine semplici e veloci per l'analisi dei dati, indipendenti dalle impostazioni locali.</span><span class="sxs-lookup"><span data-stu-id="ac888-103">Fast parse provides a fast, simple, locale-insensitive set of routines for parsing data.</span></span> <span data-ttu-id="ac888-104">Supporta solo un limitato set di formati per i tipi di dati integer.</span><span class="sxs-lookup"><span data-stu-id="ac888-104">Fast parse supports only a limited set of formats for integer data types.</span></span>  
  
## <a name="integer-data-types"></a><span data-ttu-id="ac888-105">Tipi di dati integer</span><span class="sxs-lookup"><span data-stu-id="ac888-105">Integer Data Types</span></span>  
 <span data-ttu-id="ac888-106">In [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] sono disponibili i tipi di dati integer DT_I1, DT_UI1, DT_I2, DT_UI2, DT_I4, DT_UI4, DT_I8 e DT_UI8.</span><span class="sxs-lookup"><span data-stu-id="ac888-106">The integer data types that [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] provides are DT_I1, DT_UI1, DT_I2, DT_UI2, DT_I4, DT_UI4, DT_I8, and DT_UI8.</span></span> <span data-ttu-id="ac888-107">Per altre informazioni, vedere [Tipi di dati di Integration Services](data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="ac888-107">For more information, see [Integration Services Data Types](data-flow/integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="ac888-108">L'analisi veloce supporta i formati seguenti per i tipi di dati integer:</span><span class="sxs-lookup"><span data-stu-id="ac888-108">Fast parse supports the following formats for integer data types:</span></span>  
  
-   <span data-ttu-id="ac888-109">Zero o più spazi o tabulazioni iniziali e finali o arresti di tabulazioni.</span><span class="sxs-lookup"><span data-stu-id="ac888-109">Zero or more leading and trailing spaces or tab stops.</span></span> <span data-ttu-id="ac888-110">Ad esempio, il valore "  123  " è valido.</span><span class="sxs-lookup"><span data-stu-id="ac888-110">For example, the value "  123  " is valid.</span></span> <span data-ttu-id="ac888-111">Un valore costituito da soli spazi viene considerato equivalente a zero.</span><span class="sxs-lookup"><span data-stu-id="ac888-111">A value that is all spaces evaluates to zero.</span></span>  
  
-   <span data-ttu-id="ac888-112">Un segno più (+), un segno meno (-) o nessun segno iniziale.</span><span class="sxs-lookup"><span data-stu-id="ac888-112">A leading plus sign, minus sign, or neither.</span></span> <span data-ttu-id="ac888-113">Ad esempio, i valori +123, -123 e 123 sono validi.</span><span class="sxs-lookup"><span data-stu-id="ac888-113">For example, the values +123, -123, and 123 are valid.</span></span>  
  
-   <span data-ttu-id="ac888-114">Una o più cifre arabe (0-9).</span><span class="sxs-lookup"><span data-stu-id="ac888-114">One or more Hindu-Arabic numerals (0-9).</span></span> <span data-ttu-id="ac888-115">Ad esempio, il valore 345 è valido.</span><span class="sxs-lookup"><span data-stu-id="ac888-115">For example, the value 345 is valid.</span></span> <span data-ttu-id="ac888-116">Gli altri tipi di cifre non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="ac888-116">Other language numerals are not supported.</span></span>  
  
 <span data-ttu-id="ac888-117">Di seguito sono elencati alcuni formati di dati non supportati:</span><span class="sxs-lookup"><span data-stu-id="ac888-117">Non-supported data formats include the following:</span></span>  
  
-   <span data-ttu-id="ac888-118">Caratteri speciali.</span><span class="sxs-lookup"><span data-stu-id="ac888-118">Special characters.</span></span> <span data-ttu-id="ac888-119">Il carattere di valuta $, ad esempio, non è supportato e il valore $20 non può essere analizzato.</span><span class="sxs-lookup"><span data-stu-id="ac888-119">For example, the currency character $ is not supported, and the value $20 cannot be parsed.</span></span>  
  
-   <span data-ttu-id="ac888-120">Caratteri spazio quali i caratteri di avanzamento riga, ritorno a capo e spazio unificatore.</span><span class="sxs-lookup"><span data-stu-id="ac888-120">White-space characters such as line feed, carriage returns, and non-breaking spaces.</span></span> <span data-ttu-id="ac888-121">Il valore " 123", ad esempio, non può essere analizzato.</span><span class="sxs-lookup"><span data-stu-id="ac888-121">For example, the value " 123" cannot be parsed.</span></span>  
  
-   <span data-ttu-id="ac888-122">Rappresentazioni esadecimali di valori interi.</span><span class="sxs-lookup"><span data-stu-id="ac888-122">Hexadecimal representations of integers.</span></span> <span data-ttu-id="ac888-123">Il valore 2EE, ad esempio, non può essere analizzato.</span><span class="sxs-lookup"><span data-stu-id="ac888-123">For example, the value 2EE cannot be parsed.</span></span>  
  
-   <span data-ttu-id="ac888-124">Valori interi in notazione scientifica.</span><span class="sxs-lookup"><span data-stu-id="ac888-124">Scientific notation representation of integers.</span></span> <span data-ttu-id="ac888-125">Il valore 1E+10, ad esempio, non può essere analizzato.</span><span class="sxs-lookup"><span data-stu-id="ac888-125">For example, the value 1E+10 cannot be parsed.</span></span>  
  
 <span data-ttu-id="ac888-126">Di seguito sono elencati alcuni formati di output per i dati integer:</span><span class="sxs-lookup"><span data-stu-id="ac888-126">The following formats are output data formats for integers:</span></span>  
  
-   <span data-ttu-id="ac888-127">Un segno meno (-) per i numeri negativi e nessun segno per i numeri positivi.</span><span class="sxs-lookup"><span data-stu-id="ac888-127">A minus sign for negative numbers and nothing for positive ones.</span></span>  
  
-   <span data-ttu-id="ac888-128">Nessun carattere spazio.</span><span class="sxs-lookup"><span data-stu-id="ac888-128">No white spaces.</span></span>  
  
-   <span data-ttu-id="ac888-129">Una o più cifre arabe (0-9).</span><span class="sxs-lookup"><span data-stu-id="ac888-129">One or more Hindu-Arabic numerals (0-9).</span></span>  
  
  
