---
title: Analisi dei dati | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- parsing [Integration Services]
- data parsing [Integration Services]
ms.assetid: 8893ea9d-634c-4309-b52c-6337222dcb39
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3bd34cd83351e31313ae96ff5709ec999a60f2f4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626182"
---
# <a name="parsing-data"></a><span data-ttu-id="24dcc-102">Analisi dei dati</span><span class="sxs-lookup"><span data-stu-id="24dcc-102">Parsing Data</span></span>
  <span data-ttu-id="24dcc-103">I flussi di dati nei pacchetti consentono di estrarre e caricare dati da archivi dati eterogenei, in cui possono venire utilizzati numerosi diversi tipi di dati standard e personalizzati.</span><span class="sxs-lookup"><span data-stu-id="24dcc-103">Data flows in packages extract and load data between heterogeneous data stores, which may use a variety of standard and custom data types.</span></span> <span data-ttu-id="24dcc-104">In un flusso di dati le origini di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sono responsabili dell'estrazione dei dati, dell'analisi dei dati stringa e della conversione dei dati in un tipo di dati di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="24dcc-104">In a data flow, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sources do the work of extracting data, parsing string data, and converting data to an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] data type.</span></span> <span data-ttu-id="24dcc-105">Le trasformazioni successive possono analizzare dati per convertirli in un tipo di dati diverso oppure creare copie delle colonne con tipi di dati diversi.</span><span class="sxs-lookup"><span data-stu-id="24dcc-105">Subsequent transformations may parse data to convert it to a different data type, or create column copies with different data types.</span></span> <span data-ttu-id="24dcc-106">Anche le espressioni utilizzate nei componenti possono eseguire il cast di argomenti e operandi a tipi di dati diversi.</span><span class="sxs-lookup"><span data-stu-id="24dcc-106">Expressions used in components may also cast arguments and operands to different data types.</span></span> <span data-ttu-id="24dcc-107">Quando infine i dati vengono caricati in un archivio dati, la destinazione può analizzare i dati per convertirli in un tipo di dati utilizzato dalla destinazione.</span><span class="sxs-lookup"><span data-stu-id="24dcc-107">Finally, when the data is loaded into a data store, the destination may parse the data to convert it to a data type that the destination uses.</span></span> <span data-ttu-id="24dcc-108">Per altre informazioni, vedere [Tipi di dati di Integration Services](integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="24dcc-108">For more information, see [Integration Services Data Types](integration-services-data-types.md).</span></span>  
  
## <a name="types-of-parsing"></a><span data-ttu-id="24dcc-109">Tipi di analisi</span><span class="sxs-lookup"><span data-stu-id="24dcc-109">Types of Parsing</span></span>  
 [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <span data-ttu-id="24dcc-110">offre due tipi di analisi per la conversione dei dati: l'analisi veloce e l'analisi standard.</span><span class="sxs-lookup"><span data-stu-id="24dcc-110">provides two types of parsing for converting data: Fast parse and Standard parse.</span></span>  
  
-   <span data-ttu-id="24dcc-111">L'analisi veloce è un semplice set di routine di analisi veloci, che non supportano conversioni di tipi di dati specifiche delle impostazioni locali e supportano solo i formati di data e ora utilizzati più di frequente.</span><span class="sxs-lookup"><span data-stu-id="24dcc-111">Fast parse is a fast, simple set of parsing routines that does not support locale-specific data type conversions, and supports only the most frequently used date and time formats.</span></span> <span data-ttu-id="24dcc-112">Per altre informazioni, vedere [Analisi veloce](../fast-parse.md).</span><span class="sxs-lookup"><span data-stu-id="24dcc-112">For more information, see [Fast Parse](../fast-parse.md).</span></span>  
  
-   <span data-ttu-id="24dcc-113">L'analisi standard è un set completo di routine di analisi che supportano tutte le conversioni dei tipi di dati offerte dalle API per la conversione dei tipi di dati di automazione disponibili in Oleaut32.dll e Ole2dsip.dll.</span><span class="sxs-lookup"><span data-stu-id="24dcc-113">Standard parse is a rich set of parsing routines that supports all the data type conversions that are provided by the Automation data type conversion APIs available in Oleaut32.dll and Ole2dsip.dll.</span></span> <span data-ttu-id="24dcc-114">Per altre informazioni, vedere [Analisi standard](../standard-parse.md).</span><span class="sxs-lookup"><span data-stu-id="24dcc-114">For more information, see [Standard Parse](../standard-parse.md).</span></span>  
  
  
