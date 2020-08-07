---
title: Analisi standard | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- standard parse [Integration Services]
- locales [Integration Services]
ms.assetid: dfe835b1-ea52-4e18-a23a-5188c5b6f013
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7cacff710870d372d6bbf8345e05397857c13a00
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718497"
---
# <a name="standard-parse"></a><span data-ttu-id="ccc32-102">Analisi standard</span><span class="sxs-lookup"><span data-stu-id="ccc32-102">Standard Parse</span></span>
  <span data-ttu-id="ccc32-103">L'analisi standard è un set di routine di analisi, dipendenti dalle impostazioni locali, da cui sono supportate tutte le conversioni previste dalle API per la conversione dei tipi di dati di automazione disponibili in Oleaut32.dll e Ole2dsip.dll.</span><span class="sxs-lookup"><span data-stu-id="ccc32-103">Standard parse is a locale-sensitive set of parsing routines that support all the data type conversions provided by the Automation data type conversion APIs that are available in Oleaut32.dll and Ole2dsip.dll.</span></span> <span data-ttu-id="ccc32-104">L'analisi standard è equivalente alle API di analisi di OLE DB.</span><span class="sxs-lookup"><span data-stu-id="ccc32-104">Standard parse is equivalent to the OLE DB parsing APIs.</span></span>  
  
 <span data-ttu-id="ccc32-105">L'analisi standard consente di eseguire conversioni tra tipi di dati utilizzati per dati internazionali e deve essere utilizzata quando il formato dei dati non è supportato dall'analisi veloce.</span><span class="sxs-lookup"><span data-stu-id="ccc32-105">Standard parse provides support for data type conversion of international data, and it should be used if the data format is not supported by Fast parse.</span></span> <span data-ttu-id="ccc32-106">Per ulteriori informazioni sull'API di conversione del tipo di dati di automazione, vedere la sezione relativa alle API di conversione dei tipi di dati nel sito Web [MSDN Library](https://go.microsoft.com/fwlink/?LinkId=79427).</span><span class="sxs-lookup"><span data-stu-id="ccc32-106">For more information about the Automation data type conversion API, see "Data Type Conversion APIs" in the [MSDN Library](https://go.microsoft.com/fwlink/?LinkId=79427).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccc32-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ccc32-107">See Also</span></span>  
 [<span data-ttu-id="ccc32-108">Analisi veloce</span><span class="sxs-lookup"><span data-stu-id="ccc32-108">Fast Parse</span></span>](../../2014/integration-services/fast-parse.md)  
  
  
