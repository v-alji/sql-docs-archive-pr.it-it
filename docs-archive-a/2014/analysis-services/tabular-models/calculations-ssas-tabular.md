---
title: Calcoli (SSAS tabulare) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 738816e3-0e1d-44a5-8d1b-81068dce8ac0
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2da86ae5c5652c8b2614cae4bbb721802700d973
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627419"
---
# <a name="calculations-ssas-tabular"></a><span data-ttu-id="58f0e-102">Calcoli (SSAS tabulare)</span><span class="sxs-lookup"><span data-stu-id="58f0e-102">Calculations (SSAS Tabular)</span></span>
  <span data-ttu-id="58f0e-103">Dopo aver importato dati nel modello, è possibile aggiungere calcoli per aggregare, filtrare, estendere, combinare e proteggere tali dati.</span><span class="sxs-lookup"><span data-stu-id="58f0e-103">After you have imported data into your model, you can add calculations to aggregate, filter, extend, combine, and secure that data.</span></span> <span data-ttu-id="58f0e-104">Nei modelli tabulari viene utilizzato DAX (Data Analysis Expressions), un linguaggio delle formule per la creazione di calcoli personalizzati.</span><span class="sxs-lookup"><span data-stu-id="58f0e-104">Tabular models use Data Analysis Expressions (DAX), a formula language for creating custom calculations.</span></span> <span data-ttu-id="58f0e-105">In un modello tabulare, i calcoli che vengono creati tramite formule DAX vengono usati in *Colonne calcolate*, *Misure*e *Filtri di riga*.</span><span class="sxs-lookup"><span data-stu-id="58f0e-105">In tabular models, the calculations you create by using DAX formulas are used in *Calculated Columns*, *Measures*, and *Row Filters*.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="58f0e-106">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="58f0e-106">In This Section</span></span>  
  
|<span data-ttu-id="58f0e-107">Argomento</span><span class="sxs-lookup"><span data-stu-id="58f0e-107">Topic</span></span>|<span data-ttu-id="58f0e-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="58f0e-108">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="58f0e-109">Informazioni su DAX nei modelli tabulari &#40;SSAS tabulare&#41;</span><span class="sxs-lookup"><span data-stu-id="58f0e-109">Understanding DAX in Tabular Models &#40;SSAS Tabular&#41;</span></span>](understanding-dax-in-tabular-models-ssas-tabular.md)|<span data-ttu-id="58f0e-110">Viene descritto il linguaggio delle formule Data Analysis Expressions (DAX) utilizzato per creare calcoli per colonne calcolate, misure e filtri di riga nei modelli tabulari.</span><span class="sxs-lookup"><span data-stu-id="58f0e-110">Describes the Data Analysis Expressions (DAX) formula language used to create calculations for calculated columns, measures, and row filters in tabular models.</span></span>|  
|[<span data-ttu-id="58f0e-111">Compatibilità delle formule nella modalità DirectQuery</span><span class="sxs-lookup"><span data-stu-id="58f0e-111">Formula Compatibility in DirectQuery Mode</span></span>](../dax-formula-compatibility-in-directquery-mode-ssas-2014.md)|<span data-ttu-id="58f0e-112">Vengono descritte le differenze e vengono elencate le funzioni non supportate nella modalità DirectQuery e quelle supportate, ma che potrebbero restituire risultati diversi.</span><span class="sxs-lookup"><span data-stu-id="58f0e-112">Describes the differences, lists the functions that are not supported in DirectQuery mode, and lists the functions that are supported but could return different results.</span></span>|  
|[<span data-ttu-id="58f0e-113">Informazioni di riferimento sulle espressioni di analisi dei dati &#40;&#41; DAX</span><span class="sxs-lookup"><span data-stu-id="58f0e-113">Data Analysis Expressions &#40;DAX&#41; Reference</span></span>](/dax/data-analysis-expressions-dax-reference)|<span data-ttu-id="58f0e-114">In questa sezione vengono fornite descrizioni dettagliate della sintassi, degli operatori e delle funzioni DAX.</span><span class="sxs-lookup"><span data-stu-id="58f0e-114">This section provides detailed descriptions of DAX syntax, operators, and functions.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="58f0e-115">In questa sezione non vengono fornite attività dettagliate per la creazione dei calcoli.</span><span class="sxs-lookup"><span data-stu-id="58f0e-115">Step-by-step tasks for creating calculations are not provided in this section.</span></span> <span data-ttu-id="58f0e-116">Poiché i calcoli vengono specificati in colonne calcolate, misure e filtri di riga (nei ruoli), le istruzioni sulla posizione in cui creare formule DAX vengono fornite nelle attività correlate a tali funzionalità.</span><span class="sxs-lookup"><span data-stu-id="58f0e-116">Because calculations are specified in calculated columns, measures, and row filters (in roles), instructions on where to create DAX formulas are provided in tasks related to those features.</span></span> <span data-ttu-id="58f0e-117">Per altre informazioni, vedere [Creare una colonna calcolata &#40;SSAS tabulare&#41;](ssas-calculated-columns-create-a-calculated-column.md), [Creare e gestire misure &#40;SSAS tabulare&#41;](measures-ssas-tabular.md), e [Creare e gestire ruoli &#40;SSAS tabulare&#41;](roles-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="58f0e-117">For more information, see [Create a Calculated Column &#40;SSAS Tabular&#41;](ssas-calculated-columns-create-a-calculated-column.md), [Create and Manage Measures &#40;SSAS Tabular&#41;](measures-ssas-tabular.md), and [Create and Manage Roles &#40;SSAS Tabular&#41;](roles-ssas-tabular.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="58f0e-118">Mentre DAX può essere utilizzato anche per eseguire query su un modello tabulare, gli argomenti in questa sezione riguardano in particolare l'utilizzo di formule DAX per creare calcoli.</span><span class="sxs-lookup"><span data-stu-id="58f0e-118">While DAX can also be used to query a tabular model, topics in this section focus specifically on using DAX formulas to create calculations.</span></span>  
  
  
