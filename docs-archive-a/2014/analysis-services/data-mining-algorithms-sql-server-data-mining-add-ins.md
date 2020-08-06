---
title: Algoritmi di data mining (SQL Server componenti aggiuntivi Data mining) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- segmentation
- data mining algorithms
- clustering [data mining]
- linear regression
- association [data mining]
- neural networks
- logistic regression
- regression
- sequence analysis
- decision tree [data mining]
- Naive Bayes
- time series [data mining]
ms.assetid: 3a1a62e4-9fb5-4cdb-a6c6-1b8b30d417ef
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3a73ce5a538756a740afd2db72d585fa54f03cae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636490"
---
# <a name="data-mining-algorithms-sql-server-data-mining-add-ins"></a><span data-ttu-id="9d3b0-102">Algoritmi di data mining (componenti aggiuntivi Data mining di SQL Server)</span><span class="sxs-lookup"><span data-stu-id="9d3b0-102">Data Mining Algorithms (SQL Server Data Mining Add-ins)</span></span>
  <span data-ttu-id="9d3b0-103">I componenti aggiuntivi Data mining per Office supportano la creazione di modelli analitici utilizzando gli algoritmi di data mining seguenti.</span><span class="sxs-lookup"><span data-stu-id="9d3b0-103">The Data Mining Add-ins for Office supports creation of analytical models using the following data mining algorithms.</span></span> <span data-ttu-id="9d3b0-104">Tutti gli algoritmi sono basati sui metodi di apprendimento automatico noti e sono stati implementati da Microsoft Research.</span><span class="sxs-lookup"><span data-stu-id="9d3b0-104">All algorithms are based on well-known machine learning methods and have been implemented by Microsoft Research.</span></span>  
  
## <a name="algorithms"></a><span data-ttu-id="9d3b0-105">Algoritmi</span><span class="sxs-lookup"><span data-stu-id="9d3b0-105">Algorithms</span></span>  
  
|<span data-ttu-id="9d3b0-106">Metodo di apprendimento automatico</span><span class="sxs-lookup"><span data-stu-id="9d3b0-106">Machine learning method</span></span>|<span data-ttu-id="9d3b0-107">Funzionamento</span><span class="sxs-lookup"><span data-stu-id="9d3b0-107">How it works</span></span>|  
|-----------------------------|------------------|  
|<span data-ttu-id="9d3b0-108">Algoritmo Microsoft Association Rules</span><span class="sxs-lookup"><span data-stu-id="9d3b0-108">Microsoft Association Rules  algorithm</span></span>|<span data-ttu-id="9d3b0-109">Consente di individuare i prodotti che vengono acquistati insieme o gli eventi che ricorrono insieme e di utilizzare il modello per creare indicazioni.</span><span class="sxs-lookup"><span data-stu-id="9d3b0-109">Discover which products are purchased together or which events occur together, and use the model to create recommendations.</span></span><br /><br /> [https://msdn.microsoft.com/library/ms174916.aspx](https://msdn.microsoft.com/library/ms174916.aspx)|  
|<span data-ttu-id="9d3b0-110">Algoritmo Microsoft Clustering</span><span class="sxs-lookup"><span data-stu-id="9d3b0-110">Microsoft Clustering algorithm</span></span>|<span data-ttu-id="9d3b0-111">Consente di definire i segmenti di mercato, raggruppare automaticamente clienti correlati o individuare relazioni nei dati da utilizzare per ulteriori analisi di data mining.</span><span class="sxs-lookup"><span data-stu-id="9d3b0-111">Define market segments, automatically group related customers together, or find relationships in data to use in further mining.</span></span><br /><br /> [https://msdn.microsoft.com/library/ms174879.aspx](https://msdn.microsoft.com/library/ms174879.aspx)|  
|<span data-ttu-id="9d3b0-112">Algoritmo Microsoft Decision Trees</span><span class="sxs-lookup"><span data-stu-id="9d3b0-112">Microsoft Decision Trees algorithm</span></span>|<span data-ttu-id="9d3b0-113">Consente di identificare le relazioni precedentemente non note tra i diversi elementi dei dati per permettere all'utente di prendere decisioni informate o individuare i fattori che generano risultati specifici.</span><span class="sxs-lookup"><span data-stu-id="9d3b0-113">Identify previously unknown relationships between various elements of your data to better inform your decisions, or find the factors that lead to specific outcomes.</span></span><br /><br /> [https://msdn.microsoft.com/library/ms174923.aspx](https://msdn.microsoft.com/library/ms174923.aspx)|  
|<span data-ttu-id="9d3b0-114">Algoritmo Microsoft Linear Regression</span><span class="sxs-lookup"><span data-stu-id="9d3b0-114">Microsoft Linear Regression algorithm</span></span>|<span data-ttu-id="9d3b0-115">Consente di trovare una formula matematica che descrive i fattori che contribuiscono a un risultato numerico.</span><span class="sxs-lookup"><span data-stu-id="9d3b0-115">Find a mathematical formula that describes factors that contribute to a numeric outcome.</span></span><br /><br /> [https://msdn.microsoft.com/library/ms174824.aspx](https://msdn.microsoft.com/library/ms174824.aspx)|  
|<span data-ttu-id="9d3b0-116">Algoritmo Microsoft Logistic Regression</span><span class="sxs-lookup"><span data-stu-id="9d3b0-116">Microsoft Logistic Regression algorithm</span></span>|<span data-ttu-id="9d3b0-117">Consente di identificare i fattori che contribuiscono a risultati binari e spiega come utilizzare tali informazioni per influire sui risultati.</span><span class="sxs-lookup"><span data-stu-id="9d3b0-117">Identify the factors that contribute to binary outcomes, and learn how to use those to affect results.</span></span><br /><br /> [https://msdn.microsoft.com/library/ms174828.aspx](https://msdn.microsoft.com/library/ms174828.aspx)|  
|<span data-ttu-id="9d3b0-118">Algoritmo Microsoft Naive Bayes</span><span class="sxs-lookup"><span data-stu-id="9d3b0-118">Microsoft Naïve Bayes algorithm</span></span>|<span data-ttu-id="9d3b0-119">Consente di esplorare le relazioni nei dati e trovare quelle più strettamente correlate a un risultato.</span><span class="sxs-lookup"><span data-stu-id="9d3b0-119">Explore relationships in your data and find those mostly closely correlated with an outcome.</span></span><br /><br /> [https://msdn.microsoft.com/library/ms174806.aspx](https://msdn.microsoft.com/library/ms174806.aspx)|  
|<span data-ttu-id="9d3b0-120">Algoritmo Microsoft Neural Network</span><span class="sxs-lookup"><span data-stu-id="9d3b0-120">Microsoft Neural Networks algorithm</span></span>|<span data-ttu-id="9d3b0-121">Consente di individuare le relazioni nascoste tra più input e più output.</span><span class="sxs-lookup"><span data-stu-id="9d3b0-121">Find hidden relationships among multiple inputs and even multiple outputs.</span></span> <span data-ttu-id="9d3b0-122">Da utilizzare per l'esplorazione o per la stima.</span><span class="sxs-lookup"><span data-stu-id="9d3b0-122">Use for exploration or for prediction.</span></span><br /><br /> [https://msdn.microsoft.com/library/ms174941.aspx](https://msdn.microsoft.com/library/ms174941.aspx)|  
|<span data-ttu-id="9d3b0-123">Algoritmo Microsoft Time Series</span><span class="sxs-lookup"><span data-stu-id="9d3b0-123">Microsoft Time Series algorithm</span></span>|<span data-ttu-id="9d3b0-124">Utilizza dati cronologici per stimare valori futuri.</span><span class="sxs-lookup"><span data-stu-id="9d3b0-124">Use historical data to forecast future values.</span></span><br /><br /> [https://msdn.microsoft.com/library/ms174923.aspx](https://msdn.microsoft.com/library/ms174923.aspx)|  
  
## <a name="advanced-options"></a><span data-ttu-id="9d3b0-125">Opzioni avanzate</span><span class="sxs-lookup"><span data-stu-id="9d3b0-125">Advanced Options</span></span>  
 <span data-ttu-id="9d3b0-126">Quando si utilizza il client di data mining per Excel, è possibile scegliere di creare le strutture e i modelli di data mining oppure di ottimizzare i parametri degli algoritmi.</span><span class="sxs-lookup"><span data-stu-id="9d3b0-126">When you use the Data Mining Client for Excel, you have the option to create your own data mining structures and models, or to fine-tune the parameters of the algorithms.</span></span>  
  
 [<span data-ttu-id="9d3b0-127">Parametri dell'algoritmo &#40;SQL Server i componenti aggiuntivi Data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="9d3b0-127">Algorithm Parameters &#40;SQL Server Data Mining Add-ins&#41;</span></span>](algorithm-parameters-sql-server-data-mining-add-ins.md)  
  
 <span data-ttu-id="9d3b0-128">Per personalizzare i modelli utilizzando queste opzioni avanzate, è possibile procedere in due modi:</span><span class="sxs-lookup"><span data-stu-id="9d3b0-128">There are two ways to customize your models using these advanced options:</span></span>  
  
-   <span data-ttu-id="9d3b0-129">Utilizzare la procedura guidata **query di data mining** per creare il modello.</span><span class="sxs-lookup"><span data-stu-id="9d3b0-129">Use the **Data Mining Query** wizard to create your model.</span></span>  
  
-   <span data-ttu-id="9d3b0-130">Nel **client di data mining**, dopo l'avvio della procedura guidata, fare clic su **parametri**.</span><span class="sxs-lookup"><span data-stu-id="9d3b0-130">In the **Data Mining Client**, after you start the wizard, click **Parameters**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d3b0-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9d3b0-131">See Also</span></span>  
 <span data-ttu-id="9d3b0-132">[&#40;di query SQL Server componenti aggiuntivi Data mining&#41;](query-sql-server-data-mining-add-ins.md) </span><span class="sxs-lookup"><span data-stu-id="9d3b0-132">[Query &#40;SQL Server Data Mining Add-ins&#41;](query-sql-server-data-mining-add-ins.md) </span></span>  
 [<span data-ttu-id="9d3b0-133">Modellazione avanzata &#40;componenti aggiuntivi Data mining per Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="9d3b0-133">Advanced Modeling &#40;Data Mining Add-ins for Excel&#41;</span></span>](advanced-modeling-data-mining-add-ins-for-excel.md)  
  
  
