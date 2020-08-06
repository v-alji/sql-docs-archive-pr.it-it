---
title: Distribuzioni di colonne (data mining) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- normal distribution type [data mining]
- uniform distribution type [data mining]
- columns [data mining], distributions
- log normal distribution type [data mining]
- continuous columns
- distributions [data mining]
ms.assetid: 87e700de-32be-4bc8-b01d-ba4ee1ab48de
author: minewiskan
ms.author: owend
ms.openlocfilehash: 29aad33535c4cc4d9baf4c453249ce3b51595e78
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638179"
---
# <a name="column-distributions-data-mining"></a><span data-ttu-id="1357d-102">Distribuzioni delle colonne (Data mining)</span><span class="sxs-lookup"><span data-stu-id="1357d-102">Column Distributions (Data Mining)</span></span>
  <span data-ttu-id="1357d-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] è possibile definire le distribuzioni delle colonne in una struttura di data mining per influire sul modo in cui gli algoritmi elaborano i dati in tali colonne durante la creazione dei modelli di data mining.</span><span class="sxs-lookup"><span data-stu-id="1357d-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], you can define column distributions in a mining structure, to affect how algorithms process the data in those columns when you create mining models.</span></span> <span data-ttu-id="1357d-104">Per alcuni algoritmi è utile definire la distribuzione dei dati nelle colonne continue prima di elaborare il modello, se è noto che tali colonne contengono valori con distribuzioni comuni.</span><span class="sxs-lookup"><span data-stu-id="1357d-104">For some algorithms, it is useful to define the distribution of any continuous columns before you process the model, if the columns are known to contain common distributions of values.</span></span> <span data-ttu-id="1357d-105">Se non si definiscono le distribuzioni, i modelli di data mining risultanti possono produrre stime meno accurate, perché gli algoritmi dispongono di meno informazioni per l'interpretazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="1357d-105">If you do not define the distributions, the resulting mining models may produce less accurate predictions than if the distributions were defined, because the algorithms will have less information from which to interpret the data.</span></span>

 <span data-ttu-id="1357d-106">Gli algoritmi disponibili in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] supportano i tipi di distribuzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1357d-106">The algorithms that are available in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] support the following distribution types:</span></span>

 <span data-ttu-id="1357d-107">`Normal`I valori per la colonna continua formano un istogramma con una distribuzione normale.</span><span class="sxs-lookup"><span data-stu-id="1357d-107">`Normal` The values for the continuous column form a histogram with a normal distribution.</span></span>

 <span data-ttu-id="1357d-108">![Istogramma con distribuzione normale](../media/normal-distribution.gif "Istogramma con distribuzione normale")</span><span class="sxs-lookup"><span data-stu-id="1357d-108">![Histogram with normal distribution](../media/normal-distribution.gif "Histogram with normal distribution")</span></span>

 <span data-ttu-id="1357d-109">`Log Normal`I valori per la colonna continua formano un istogramma, in cui la curva è allungata all'estremità superiore ed è inclinata verso l'estremità inferiore.</span><span class="sxs-lookup"><span data-stu-id="1357d-109">`Log Normal` The values for the continuous column form a histogram, where the curve is elongated at the upper end and is skewed toward the lower end.</span></span>

 <span data-ttu-id="1357d-110">![Istogramma con distribuzione normale dei log](../media/log-normal-distribution.gif "Istogramma con distribuzione normale dei log")</span><span class="sxs-lookup"><span data-stu-id="1357d-110">![Histogram with log normal distribution](../media/log-normal-distribution.gif "Histogram with log normal distribution")</span></span>

 <span data-ttu-id="1357d-111">`Uniform`I valori per la colonna continua formano una curva piatta, in cui tutti i valori sono ugualmente probabili.</span><span class="sxs-lookup"><span data-stu-id="1357d-111">`Uniform` The values for the continuous column form a flat curve, in which all values are equally likely.</span></span>

 <span data-ttu-id="1357d-112">![Istogramma con distribuzione uniforme](../media/uniform-distribution.gif "Istogramma con distribuzione uniforme")</span><span class="sxs-lookup"><span data-stu-id="1357d-112">![Histogram with uniform distribution](../media/uniform-distribution.gif "Histogram with uniform distribution")</span></span>

 <span data-ttu-id="1357d-113">Per altre informazioni sugli algoritmi forniti da [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], vedere [Algoritmi di data mining &#40;Analysis Services - Data mining&#41;](data-mining-algorithms-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="1357d-113">For more information about the algorithms that [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] provides, see [Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining-algorithms-analysis-services-data-mining.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1357d-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1357d-114">See Also</span></span>
 <span data-ttu-id="1357d-115">[Tipi di contenuto &#40;data mining&#41;](content-types-data-mining.md) le strutture di data mining &#40;i metodi [di discretizzazione Analysis Services di](mining-structures-analysis-services-data-mining.md) data mining&#41;le distribuzioni &#40;di [data mining](discretization-methods-data-mining.md)&#41;[DMX &#40;](/sql/dmx/distributions-dmx) [colonne della struttura](mining-structure-columns.md) di data mining</span><span class="sxs-lookup"><span data-stu-id="1357d-115">[Content Types &#40;Data Mining&#41;](content-types-data-mining.md) [Mining Structures &#40;Analysis Services - Data Mining&#41;](mining-structures-analysis-services-data-mining.md) [Discretization Methods &#40;Data Mining&#41;](discretization-methods-data-mining.md) [Distributions &#40;DMX&#41;](/sql/dmx/distributions-dmx) [Mining Structure Columns](mining-structure-columns.md)</span></span>


