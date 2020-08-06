---
title: Troncamento dei dati (SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- truncating data
- data truncation [Integration Services]
- expressions [Integration Services], data truncation
- truncate options [Integration Services]
ms.assetid: 02461e15-49ca-445b-abb3-5c369c283ec2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e0c4280c9eacd22ebf84bf1570d485de51cab09b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637439"
---
# <a name="data-truncation-ssis"></a><span data-ttu-id="ca7cb-102">Troncamento dei dati (SSIS)</span><span class="sxs-lookup"><span data-stu-id="ca7cb-102">Data Truncation (SSIS)</span></span>
  <span data-ttu-id="ca7cb-103">Un'espressione può causare il troncamento accidentale dei dati.</span><span class="sxs-lookup"><span data-stu-id="ca7cb-103">An expression may inadvertently cause data to be truncated.</span></span> <span data-ttu-id="ca7cb-104">Il troncamento può verificarsi nelle circostanze seguenti:</span><span class="sxs-lookup"><span data-stu-id="ca7cb-104">Truncation can occur under the following circumstances:</span></span>  
  
-   <span data-ttu-id="ca7cb-105">Stringhe.</span><span class="sxs-lookup"><span data-stu-id="ca7cb-105">Strings.</span></span> <span data-ttu-id="ca7cb-106">Se ad esempio si convertono dati stringa con tipo di dati DT_WSTR in una stringa della stessa lunghezza in caratteri, ma con tipo di dati DT_STR e la stringa originale contiene caratteri DBCS (Double-Byte Character Set), si verificherà una perdita di dati.</span><span class="sxs-lookup"><span data-stu-id="ca7cb-106">For example, translating string data with a DT_WSTR data type to the same length string, measured in characters, with a DT_STR data type causes data loss if the original string contains double-byte characters.</span></span>  
  
-   <span data-ttu-id="ca7cb-107">Cifre significative.</span><span class="sxs-lookup"><span data-stu-id="ca7cb-107">Significant digits.</span></span> <span data-ttu-id="ca7cb-108">Questo tipo di troncamento si verifica ad esempio quando si esegue il cast di un valore integer dal tipo di dati DT_I4 al tipo di dati DT_I2 oppure da un intero senza segno a un intero con segno.</span><span class="sxs-lookup"><span data-stu-id="ca7cb-108">For example, casting an integer from a DT_I4 data type to a DT_I2 data type or an unsigned integer to a signed integer.</span></span>  
  
-   <span data-ttu-id="ca7cb-109">Cifre non significative.</span><span class="sxs-lookup"><span data-stu-id="ca7cb-109">Insignificant digits.</span></span> <span data-ttu-id="ca7cb-110">Questo tipo di troncamento si verifica ad esempio quando si esegue il cast di un numero reale dal tipo di dati DT_R8 al tipo di dati DT_R4 oppure di un valore integer dal tipo di dati DT_I4 al tipo di dati DT_R4.</span><span class="sxs-lookup"><span data-stu-id="ca7cb-110">For example, casting a real number from a DT_R8 to a DT_R4 or an integer from a DT_I4 data type to a DT_R4 data type.</span></span>  
  
 <span data-ttu-id="ca7cb-111">L'analizzatore di espressioni identifica i cast espliciti che possono causare troncamenti e genera un avviso durante l'analisi dell'espressione.</span><span class="sxs-lookup"><span data-stu-id="ca7cb-111">The expression evaluator identifies explicit casts that may cause truncation and issues a warning when the expression is parsed.</span></span> <span data-ttu-id="ca7cb-112">L'analizzatore di espressioni genera un avviso ad esempio quando viene eseguito il cast di una stringa di 30 caratteri in una stringa di 20 caratteri.</span><span class="sxs-lookup"><span data-stu-id="ca7cb-112">For example, the expression evaluator warns you if a 30-character string is cast into a 20-character string.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ca7cb-113">In fase di esecuzione il troncamento non viene verificato e i dati vengono troncati senza generare avvisi.</span><span class="sxs-lookup"><span data-stu-id="ca7cb-113">Truncation is not checked at run time; data is truncated without warning.</span></span> <span data-ttu-id="ca7cb-114">La maggior parte degli adattatori e delle trasformazioni supporta tuttavia output degli errori in grado di gestire la disposizione delle righe con errori.</span><span class="sxs-lookup"><span data-stu-id="ca7cb-114">However, most data adapters and transformations support error outputs that can handle the disposition of error rows.</span></span> <span data-ttu-id="ca7cb-115">Per ulteriori informazioni sulla gestione del troncamento dei dati, vedere [gestione degli errori nei dati](../data-flow/error-handling-in-data.md).</span><span class="sxs-lookup"><span data-stu-id="ca7cb-115">For more information about handling truncation of data, see [Error Handling in Data](../data-flow/error-handling-in-data.md).</span></span>  
  
  
