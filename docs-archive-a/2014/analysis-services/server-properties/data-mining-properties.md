---
title: Proprietà di data mining | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- ClusterCount property
- AllowedProvidersInOpenRowset property
- MinimumSeriesValue property
- ScoreMethod property
- MinimumImportance property
- ModellingCardinality property
- BrentTolerance property
- ComplexityPenalty property
- MaximumItemsetCount property
- MinimumSupport property
- AllowSessionMiningModels property
- HoldoutPercentage property
- ClusterCountPrior property
- MaximumSequenceStates property
- OptimizedPredictionCount property
- data mining [Analysis Services], properties
- MaximumStates property
- MaximumContinuousInputAttributes property
- MaximumOutputAttributes property
- AllowAdHocOpenRowsetQueries property
- Enabled property
- HistoricModelGap property
- SampleSize property
- MaximumInputAttributes property
- PeriodicityHint property
- MissingValueSubstitution property
- SplitMethod property
- ForceRegressor property
- MaximumBucketsForContinuousSplit property
- MaxConcurrentPredictionQueries property
- MinimumItemsetSize property
- AcyclicGraph property
- HoldoutMethod property
- StoppingTolerance property
- properties [data mining]
- AutoDetectPeriodicity property
- HoldoutTolerance property
- MinimumLeafCases property
- HoldoutSeed property
- MinimumClusterCases property
- ClusterCountDeviation property
- MinimumDependencyProbability property
- ClusteringMethod property
- MaximumItemsetSize property
- HiddenNodeRatio property
- MaximumSeriesValue property
ms.assetid: 9bc9abed-180a-4bd8-b2eb-89c62fa88110
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5ed1c47faafeb0c680e6afb6f8e509c426760da2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727188"
---
# <a name="data-mining-properties"></a><span data-ttu-id="597e0-102">Proprietà di data mining</span><span class="sxs-lookup"><span data-stu-id="597e0-102">Data Mining Properties</span></span>
  [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="597e0-103">supporta le proprietà di data mining del server elencate nelle tabelle seguenti.</span><span class="sxs-lookup"><span data-stu-id="597e0-103">supports the data mining server properties listed in the following tables.</span></span> <span data-ttu-id="597e0-104">Per altre informazioni sulle proprietà aggiuntive del server e sulla relativa impostazione, vedere [Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="597e0-104">For more information about additional server properties and how to set them, see [Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md).</span></span>  
  
 <span data-ttu-id="597e0-105">**Si applica a:** Solo modalità server multidimensionale</span><span class="sxs-lookup"><span data-stu-id="597e0-105">**Applies to:** Multidimensional server mode only</span></span>  
  
## <a name="non-specific-category"></a><span data-ttu-id="597e0-106">Categoria Non-Specific</span><span class="sxs-lookup"><span data-stu-id="597e0-106">Non-Specific Category</span></span>  
 `AllowSessionMiningModels`  
 <span data-ttu-id="597e0-107">Proprietà booleana che indica se è possibile creare modelli di data mining di sessione.</span><span class="sxs-lookup"><span data-stu-id="597e0-107">A Boolean property that indicates whether session mining models can be created.</span></span>  
  
 <span data-ttu-id="597e0-108">Il valore predefinito di questa proprietà è False per indicare che i modelli di data mining di sessione non possono essere creati.</span><span class="sxs-lookup"><span data-stu-id="597e0-108">The default value for this property is false, which indicates that session mining models cannot be created.</span></span>  
  
 `AllowAdHocOpenRowsetQueries`  
 <span data-ttu-id="597e0-109">Proprietà booleana che indica se sono consentite query ad hoc su set di righe aperti.</span><span class="sxs-lookup"><span data-stu-id="597e0-109">A Boolean property that indicates whether adhoc open rowset queries are allowed.</span></span>  
  
 <span data-ttu-id="597e0-110">Il valore predefinito di questa proprietà è False per indicare che le query su set di righe aperti non sono consentite durante una sessione.</span><span class="sxs-lookup"><span data-stu-id="597e0-110">The default value for this property is false, which indicates that open rowset queries are not allowed during a session.</span></span>  
  
 `AllowedProvidersInOpenRowset`  
 <span data-ttu-id="597e0-111">Proprietà stringa che indica i provider ammessi in un set di righe aperto; comprende un elenco separato da virgole/punti e virgola di ProgID di provider o il valore [All].</span><span class="sxs-lookup"><span data-stu-id="597e0-111">A string property that identifies which providers are allowed in an open rowset, consisting of a comma/semi-colon separated list of provider ProgIDs, or else [All].</span></span>  
  
 `MaxConcurrentPredictionQueries`  
 <span data-ttu-id="597e0-112">Proprietà a Signed Integer a 32 bit che definisce il numero massimo di query di stima simultanee.</span><span class="sxs-lookup"><span data-stu-id="597e0-112">A signed 32-bit integer property that defines the maximum number of concurrent prediction queries.</span></span>  
  
## <a name="algorithms-category"></a><span data-ttu-id="597e0-113">Categoria Algorithms</span><span class="sxs-lookup"><span data-stu-id="597e0-113">Algorithms Category</span></span>  
 `Microsoft_Association_Rules\ Enabled`  
 <span data-ttu-id="597e0-114">Proprietà booleana che indica se l'algoritmo Microsoft_Association_Rules è attivato.</span><span class="sxs-lookup"><span data-stu-id="597e0-114">A Boolean property that indicates whether the Microsoft_Association_Rules algorithm is enabled.</span></span>  
  
 `Microsoft_Clustering\ Enabled`  
 <span data-ttu-id="597e0-115">Proprietà booleana che indica se l'algoritmo Microsoft_Clustering è attivato.</span><span class="sxs-lookup"><span data-stu-id="597e0-115">A Boolean property that indicates whether the Microsoft_Clustering algorithm is enabled.</span></span>  
  
 `Microsoft_Decision_Trees\ Enabled`  
 <span data-ttu-id="597e0-116">Proprietà booleana che indica se l'algoritmo Microsoft_DecisionTrees è attivato.</span><span class="sxs-lookup"><span data-stu-id="597e0-116">A Boolean property that indicates whether the Microsoft_DecisionTrees algorithm is enabled.</span></span>  
  
 `Microsoft_Naive_Bayes\ Enabled`  
 <span data-ttu-id="597e0-117">Proprietà booleana che indica se l'algoritmo Microsoft_ Naive_Bayes è attivato.</span><span class="sxs-lookup"><span data-stu-id="597e0-117">A Boolean property that indicates whether the Microsoft_ Naive_Bayes algorithm is enabled.</span></span>  
  
 `Microsoft_Neural_Network\ Enabled`  
 <span data-ttu-id="597e0-118">Proprietà booleana che indica se l'algoritmo Microsoft_Neural_Network è attivato.</span><span class="sxs-lookup"><span data-stu-id="597e0-118">A Boolean property that indicates whether the Microsoft_Neural_Network algorithm is enabled.</span></span>  
  
 `Microsoft_Sequence_Clustering\ Enabled`  
 <span data-ttu-id="597e0-119">Proprietà booleana che indica se l'algoritmo Microsoft_Sequence_Clustering è attivato.</span><span class="sxs-lookup"><span data-stu-id="597e0-119">A Boolean property that indicates whether the Microsoft_Sequence_Clustering algorithm is enabled.</span></span>  
  
 `Microsoft_Time_Series\ Enabled`  
 <span data-ttu-id="597e0-120">Proprietà booleana che indica se l'algoritmo Microsoft_Time_Series è attivato.</span><span class="sxs-lookup"><span data-stu-id="597e0-120">A Boolean property that indicates whether the Microsoft_Time_Series algorithm is enabled.</span></span>  
  
 `Microsoft_Linear_Regression\ Enabled`  
 <span data-ttu-id="597e0-121">Proprietà booleana che indica se l'algoritmo Microsoft_Linear_Regression è attivato.</span><span class="sxs-lookup"><span data-stu-id="597e0-121">A Boolean property that indicates whether the Microsoft_Linear_Regression algorithm is enabled.</span></span>  
  
 `Microsoft_Logistic_Regression\ Enabled`  
 <span data-ttu-id="597e0-122">Proprietà booleana che indica se l'algoritmo Microsoft_Logistic_Regression è attivato.</span><span class="sxs-lookup"><span data-stu-id="597e0-122">A Boolean property that indicates whether the Microsoft_Logistic_Regression algorithm is enabled.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="597e0-123">Oltre alle proprietà che definiscono i servizi data mining disponibili nel server, esistono proprietà di data mining che definiscono il comportamento di algoritmi specifici.</span><span class="sxs-lookup"><span data-stu-id="597e0-123">In addition to properties that define the data mining services available on the server, there are data mining properties that define the behavior of specific algorithms.</span></span> <span data-ttu-id="597e0-124">Configurare tali proprietà quando si crea un modello di data mining singolo, non a livello di server.</span><span class="sxs-lookup"><span data-stu-id="597e0-124">You configure these properties when you create an individual data mining model, not at the server level.</span></span> <span data-ttu-id="597e0-125">Per altre informazioni, vedere [Algoritmi di data mining &#40;Analysis Services - Data mining&#41;](../data-mining/data-mining-algorithms-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="597e0-125">For more information, see [Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](../data-mining/data-mining-algorithms-analysis-services-data-mining.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="597e0-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="597e0-126">See Also</span></span>  
 <span data-ttu-id="597e0-127">[Architettura fisica &#40;Analysis Services-&#41;di data mining](../data-mining/physical-architecture-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="597e0-127">[Physical Architecture &#40;Analysis Services - Data Mining&#41;](../data-mining/physical-architecture-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="597e0-128">[Configurare le proprietà del server in Analysis Services](server-properties-in-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="597e0-128">[Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md) </span></span>  
 [<span data-ttu-id="597e0-129">Determinare la modalità server di un'istanza di Analysis Services</span><span class="sxs-lookup"><span data-stu-id="597e0-129">Determine the Server Mode of an Analysis Services Instance</span></span>](../instances/determine-the-server-mode-of-an-analysis-services-instance.md)  
  
  
