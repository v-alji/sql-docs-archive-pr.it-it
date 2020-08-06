---
title: Analisi veloce | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- fast parse [Integration Services]
ms.assetid: 6688707d-3c5b-404e-aa2f-e13092ac8d95
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 343b8b8b74338512dbf29b3d2efd436df1ffa8ae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720250"
---
# <a name="fast-parse"></a><span data-ttu-id="f9e45-102">Analisi veloce</span><span class="sxs-lookup"><span data-stu-id="f9e45-102">Fast Parse</span></span>
  <span data-ttu-id="f9e45-103">L'analisi veloce offre un set di routine semplici e veloci per l'analisi dei dati.</span><span class="sxs-lookup"><span data-stu-id="f9e45-103">Fast parse provides a fast, simple set of routines for parsing data.</span></span> <span data-ttu-id="f9e45-104">Tali routine sono indipendenti dalle impostazioni locali e supportano solo un subset dei formati di data, ora e integer.</span><span class="sxs-lookup"><span data-stu-id="f9e45-104">These routines are not locale-sensitive and they support only a subset of date, time, and integer formats.</span></span>  
  
## <a name="requirements-and-limitations"></a><span data-ttu-id="f9e45-105">Requisiti e limitazioni</span><span class="sxs-lookup"><span data-stu-id="f9e45-105">Requirements and Limitations</span></span>  
 <span data-ttu-id="f9e45-106">I pacchetti che implementano l'analisi veloce hanno una capacità limitata di interpretare le informazioni di data, ora e numeriche nei formati che dipendono dalle impostazioni locali e nei formati ISO 8601 di base ed estesi maggiormente utilizzati, ma offrono prestazioni superiori.</span><span class="sxs-lookup"><span data-stu-id="f9e45-106">By implementing fast parse, a package forfeits its ability to interpret date, time, and numeric data in locale-specific formats and many frequently used ISO 8601 basic and extended formats, but the package enhances its performance.</span></span> <span data-ttu-id="f9e45-107">L'analisi veloce supporta ad esempio solo le rappresentazioni dei formati di data utilizzate più di frequente, quali AAAAMMGG e AAAA-MM-GG, non esegue analisi specifiche delle impostazioni locali, non riconosce i caratteri speciali nei dati di valuta e non è in grado di convertire la rappresentazione esadecimale o scientifica dei valori interi.</span><span class="sxs-lookup"><span data-stu-id="f9e45-107">For example, fast parse supports only the most commonly used date format representations such as YYYYMMDD and YYYY-MM-DD, does not perform locale-specific parsing, does not recognize special characters in currency data, and cannot convert hexadecimal or scientific representation of integers.</span></span>  
  
 <span data-ttu-id="f9e45-108">L'analisi veloce è disponibile solo quando si utilizza l'origine file flat o la trasformazione Conversione dati.</span><span class="sxs-lookup"><span data-stu-id="f9e45-108">Fast parse is available only when you use the Flat File source or the Data Conversion transformation.</span></span> <span data-ttu-id="f9e45-109">Poiché l'aumento di prestazioni può essere significativo, se possibile in tali componenti del flusso di dati è consigliabile utilizzare l'analisi veloce.</span><span class="sxs-lookup"><span data-stu-id="f9e45-109">The increase in performance can be significant, and you should consider using fast parse in these data flow components if you can.</span></span>  
  
 <span data-ttu-id="f9e45-110">Se il flusso di dati nel pacchetto richiede analisi che dipendono dalle impostazioni locali, è consigliabile utilizzare l'analisi standard anziché l'analisi veloce.</span><span class="sxs-lookup"><span data-stu-id="f9e45-110">If the data flow in the package requires locale-sensitive parsing, standard parse is recommended instead of fast parse.</span></span> <span data-ttu-id="f9e45-111">L'analisi veloce non riconosce ad esempio dati dipendenti dalle impostazioni locali che includono simboli quali il separatore decimale, formati di data diversi dai formati anno-mese-giorno e simboli di valuta.</span><span class="sxs-lookup"><span data-stu-id="f9e45-111">For example, fast parse does not recognize locale-sensitive data that includes decimal symbols such as the comma, date formats other than year-month-date formats, and currency symbols.</span></span>  
  
 <span data-ttu-id="f9e45-112">Le rappresentazioni troncate che includono in modo implicito una o più parti della data, ad esempio il secolo, l'anno o il mese, non vengono riconosciute dall'analisi veloce.</span><span class="sxs-lookup"><span data-stu-id="f9e45-112">Truncated representations that imply one or more date parts, such as a century, a year, or a month, are not recognized by fast parse.</span></span> <span data-ttu-id="f9e45-113">L'analisi veloce non riconosce né il formato "**-AAMM**", che specifica l'anno e il mese in un secolo implicito, né il formato "**--MM**", che specifica un mese in un anno implicito.</span><span class="sxs-lookup"><span data-stu-id="f9e45-113">For example, fast parse recognizes neither the '**-YYMM**' format, which specifies a year and month in an implied century, nor '**--MM**', which specifies a month in an implied year.</span></span> <span data-ttu-id="f9e45-114">Vengono tuttavia riconosciute alcune rappresentazioni con precisione ridotta,</span><span class="sxs-lookup"><span data-stu-id="f9e45-114">However, some representations with reduced precision are recognized.</span></span> <span data-ttu-id="f9e45-115">ad esempio il formato "hhmm;" che indica solo le ore e i minuti, e il formato "**AAAA**", che indica solo l'anno.</span><span class="sxs-lookup"><span data-stu-id="f9e45-115">For example, fast parse recognizes the 'hhmm;' format, which indicates hour and minute only, and '**YYYY**', which indicates year only.</span></span>  
  
 <span data-ttu-id="f9e45-116">L'analisi veloce è specificata a livello di colonna.</span><span class="sxs-lookup"><span data-stu-id="f9e45-116">Fast parse is specified at the column level.</span></span> <span data-ttu-id="f9e45-117">Nell'origine file flat e nella trasformazione Conversione dati è possibile specificare l'analisi veloce nelle colonne di output.</span><span class="sxs-lookup"><span data-stu-id="f9e45-117">In the Flat File source and the Data Conversion transformation, you can specify Fast parse on output columns.</span></span> <span data-ttu-id="f9e45-118">Input e output possono includere sia colonne dipendenti dalle impostazioni locali che colonne indipendenti dalle impostazioni locali.</span><span class="sxs-lookup"><span data-stu-id="f9e45-118">Inputs and outputs can include both locale-sensitive and locale-insensitive columns.</span></span>  
  
 <span data-ttu-id="f9e45-119">Per ulteriori informazioni sui formati di data supportati dall'analisi veloce, vedere [Numeric Data Formats](../../2014/integration-services/numeric-data-formats.md) e [Date and Time Formats](../../2014/integration-services/date-and-time-formats.md).</span><span class="sxs-lookup"><span data-stu-id="f9e45-119">For more information about the data formats that Fast parse supports, see [Numeric Data Formats](../../2014/integration-services/numeric-data-formats.md) and [Date and Time Formats](../../2014/integration-services/date-and-time-formats.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="f9e45-120">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="f9e45-120">Related Tasks</span></span>  
 [<span data-ttu-id="f9e45-121">Impostazione dell'analisi veloce</span><span class="sxs-lookup"><span data-stu-id="f9e45-121">Set Fast Parse</span></span>](../../2014/integration-services/set-fast-parse.md)  
  
  
