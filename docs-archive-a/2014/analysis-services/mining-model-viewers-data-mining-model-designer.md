---
title: Visualizzatori modello di data mining (Progettazione modelli di data mining) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.viewers.f1
ms.assetid: 4ba391d5-c97b-4848-ba7c-7d096fa4b7dd
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4cc1c9d72a08ef49ed2f4f466953d2ba61394178
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724272"
---
# <a name="mining-model-viewers-data-mining-model-designer"></a><span data-ttu-id="d780c-102">Visualizzatori modello di data mining (Progettazione modelli di data mining)</span><span class="sxs-lookup"><span data-stu-id="d780c-102">Mining Model Viewers (Data Mining Model Designer)</span></span>
  <span data-ttu-id="d780c-103">Usare la scheda **Visualizzatore modello di data mining** per l'esplorazione dei modelli di data mining contenuti in una struttura di data mining.</span><span class="sxs-lookup"><span data-stu-id="d780c-103">Use the **Mining Model Viewer** tab to explore the mining models that a mining structure contains.</span></span>

 <span data-ttu-id="d780c-104">Prima si seleziona il modello di data mining, quindi si seleziona un visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="d780c-104">First you select the mining model and then you select a viewer.</span></span> <span data-ttu-id="d780c-105">In ogni modello sono sempre presenti due visualizzatori: un visualizzatore personalizzato in cui possono essere incluse più schede e il visualizzatore generico.</span><span class="sxs-lookup"><span data-stu-id="d780c-105">Each model always has two viewers available: a custom viewer, which can include multiple tabs, and the generic viewer.</span></span>

 <span data-ttu-id="d780c-106">Per una procedura dettagliata sull'utilizzo di ogni visualizzatore, vedere [Visualizzatori modello di Data Mining](data-mining/data-mining-model-viewers.md).</span><span class="sxs-lookup"><span data-stu-id="d780c-106">For a walkthrough of how to use each viewer, see [Data Mining Model Viewers](data-mining/data-mining-model-viewers.md).</span></span>

## <a name="common-options"></a><span data-ttu-id="d780c-107">Opzioni comuni</span><span class="sxs-lookup"><span data-stu-id="d780c-107">Common Options</span></span>
 <span data-ttu-id="d780c-108">**Aggiorna contenuto visualizzatore** Consente di ricaricare il modello di data mining nel visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="d780c-108">**Refresh viewer content** Reload the mining model in the viewer.</span></span>

 <span data-ttu-id="d780c-109">**Modello di data mining** Fare clic su un modello di data mining da visualizzare contenuto nella struttura di data mining corrente.</span><span class="sxs-lookup"><span data-stu-id="d780c-109">**Mining Model** Choose a mining model to view that is contained in the current mining structure.</span></span> <span data-ttu-id="d780c-110">Il modello di data mining verrà prima aperto nel visualizzatore personalizzato associato.</span><span class="sxs-lookup"><span data-stu-id="d780c-110">The mining model will first open in its associated custom viewer.</span></span>

 <span data-ttu-id="d780c-111">**Visualizzatore** Consente di scegliere un visualizzatore da utilizzare per l'esplorazione del modello di data mining selezionato.</span><span class="sxs-lookup"><span data-stu-id="d780c-111">**Viewer** Choose a viewer to use to explore the selected mining model.</span></span> <span data-ttu-id="d780c-112">In questo elenco sono inclusi i visualizzatori [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] forniti da per ogni modello di data mining, il [!INCLUDE[msCoName](../includes/msconame-md.md)] Visualizzatore contenuto di data mining e gli eventuali visualizzatori plug-in.</span><span class="sxs-lookup"><span data-stu-id="d780c-112">This list includes the viewers that [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] provides for each mining model, the [!INCLUDE[msCoName](../includes/msconame-md.md)] Mining Content Viewer, and any plug-in viewers.</span></span>

 <span data-ttu-id="d780c-113">Nel diagramma seguente vengono mostrati il visualizzatore personalizzato e quello generico per lo stesso modello.</span><span class="sxs-lookup"><span data-stu-id="d780c-113">The following diagram shows a custom viewer and the generic viewer for the same model.</span></span>

-   <span data-ttu-id="d780c-114">Nel diagramma superiore viene mostrato il visualizzatore per un modello di data mining basato sull'algoritmo Microsoft Time Series.</span><span class="sxs-lookup"><span data-stu-id="d780c-114">The upper diagram shows the viewer for a mining model based on the Microsoft Time Series algorithm.</span></span> <span data-ttu-id="d780c-115">Questo particolare visualizzatore personalizzato consente di creare automaticamente un grafico della serie temporale e fornisce cinque stime.</span><span class="sxs-lookup"><span data-stu-id="d780c-115">This particular custom viewer automatically creates a graph of the time series and provides five predictions.</span></span>

-   <span data-ttu-id="d780c-116">L'immagine inferiore illustra lo stesso modello visualizzato usando **Microsoft Generic Content Tree Viewer**.</span><span class="sxs-lookup"><span data-stu-id="d780c-116">The lower diagram shows the same model displayed using the **Microsoft Generic Content Tree Viewer**.</span></span> <span data-ttu-id="d780c-117">In questo visualizzatore viene presentato il contenuto del modello di data mining in base a uno schema standardizzato.</span><span class="sxs-lookup"><span data-stu-id="d780c-117">This viewer presents the contents of the mining model according to a standardized schema.</span></span> <span data-ttu-id="d780c-118">Per altre informazioni, vedere [Microsoft Generic Content Tree Viewer &#40;Data Mining&#41;](microsoft-generic-content-tree-viewer-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="d780c-118">For more information, see [Microsoft Generic Content Tree Viewer &#40;Data Mining&#41;](microsoft-generic-content-tree-viewer-data-mining.md).</span></span>

 <span data-ttu-id="d780c-119">![Panoramica di Progettazione modelli di data mining](media/generic-mining-model-tab1.gif "Panoramica di Progettazione modelli di data mining")</span><span class="sxs-lookup"><span data-stu-id="d780c-119">![Overview of mining model designer](media/generic-mining-model-tab1.gif "Overview of mining model designer")</span></span>

## <a name="viewers-and-their-components"></a><span data-ttu-id="d780c-120">Visualizzatori e relativi componenti</span><span class="sxs-lookup"><span data-stu-id="d780c-120">Viewers and Their Components</span></span>
 <span data-ttu-id="d780c-121">A seconda del modello selezionato, verrà mostrato un visualizzatore diverso, adattato all'algoritmo utilizzato per creare il modello di data mining selezionato.</span><span class="sxs-lookup"><span data-stu-id="d780c-121">Depending on the model that you select, you will see a different custom viewer, tailored to the algorithm that you used to create the selected data mining model.</span></span> <span data-ttu-id="d780c-122">In ogni visualizzatore personalizzato sono disponibili molti strumenti e finestre di dialogo che consentono di esplorare le statistiche e gli schemi del modello.</span><span class="sxs-lookup"><span data-stu-id="d780c-122">Each custom viewer has a variety of tools and dialog boxes for helping you explore the statistics and patterns in the model.</span></span>

 <span data-ttu-id="d780c-123">Nell'elenco seguente vengono descritte le opzioni di ogni visualizzatore personalizzato.</span><span class="sxs-lookup"><span data-stu-id="d780c-123">The following list describes the options in each of the custom viewers.</span></span>

### <a name="microsoft-association-rules-algorithm"></a><span data-ttu-id="d780c-124">Algoritmo Microsoft Association Rules</span><span class="sxs-lookup"><span data-stu-id="d780c-124">Microsoft Association Rules Algorithm</span></span>

-   [<span data-ttu-id="d780c-125">Visualizzare un modello utilizzando il Visualizzatore Microsoft Association Rules</span><span class="sxs-lookup"><span data-stu-id="d780c-125">Browse a Model Using the Microsoft Association Rules Viewer</span></span>](data-mining/browse-a-model-using-the-microsoft-association-rules-viewer.md)

    -   [<span data-ttu-id="d780c-126">Scheda set di elementi &#40;Visualizzatore modello di data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="d780c-126">Itemsets Tab &#40;Mining Model Viewer&#41;</span></span>](itemsets-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="d780c-127">Scheda regole &#40;Visualizzatore modello di data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="d780c-127">Rules Tab &#40;Mining Model Viewer&#41;</span></span>](rules-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="d780c-128">Scheda rete di dipendenze &#40;Visualizzatore modello di data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="d780c-128">Dependency Network Tab &#40;Mining Model Viewer&#41;</span></span>](dependency-network-tab-mining-model-viewer.md)

### <a name="microsoft-clustering-algorithm"></a><span data-ttu-id="d780c-129">Algoritmo Microsoft Clustering</span><span class="sxs-lookup"><span data-stu-id="d780c-129">Microsoft Clustering Algorithm</span></span>

-   [<span data-ttu-id="d780c-130">Visualizzare un modello utilizzando il Visualizzatore Microsoft Clustering</span><span class="sxs-lookup"><span data-stu-id="d780c-130">Browse a Model Using the Microsoft Cluster Viewer</span></span>](data-mining/browse-a-model-using-the-microsoft-cluster-viewer.md)

    -   [<span data-ttu-id="d780c-131">Scheda Diagramma cluster &#40;Visualizzatore modello di data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="d780c-131">Cluster Diagram Tab &#40;Mining Model Viewer&#41;</span></span>](cluster-diagram-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="d780c-132">Scheda Profili cluster &#40;Visualizzatore modello di data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="d780c-132">Cluster Profiles Tab &#40;Mining Model Viewer&#41;</span></span>](cluster-profiles-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="d780c-133">Scheda Caratteristiche cluster &#40;Visualizzatore modello di data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="d780c-133">Cluster Characteristics Tab &#40;Mining Model Viewer&#41;</span></span>](cluster-characteristics-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="d780c-134">Scheda Analisi discriminante tra cluster &#40;Visualizzatore modello di data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="d780c-134">Cluster Discrimination Tab &#40;Mining Model Viewer&#41;</span></span>](cluster-discrimination-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="d780c-135">Finestra di dialogo Legenda data mining &#40;Visualizzatore modello di data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="d780c-135">Mining Legend Dialog Box &#40;Mining Model Viewer&#41;</span></span>](mining-legend-dialog-box-mining-model-viewer.md)

### <a name="microsoft-decision-tree-algorithm"></a><span data-ttu-id="d780c-136">Algoritmo Microsoft Decision Trees</span><span class="sxs-lookup"><span data-stu-id="d780c-136">Microsoft Decision Tree Algorithm</span></span>

-   [<span data-ttu-id="d780c-137">Visualizzare un modello utilizzando il Visualizzatore Microsoft Decision Trees</span><span class="sxs-lookup"><span data-stu-id="d780c-137">Browse a Model Using the Microsoft Tree Viewer</span></span>](data-mining/browse-a-model-using-the-microsoft-tree-viewer.md)

    -   [<span data-ttu-id="d780c-138">Scheda albero delle decisioni &#40;Visualizzatore modello di data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="d780c-138">Decision Tree Tab &#40;Mining Model Viewer&#41;</span></span>](decision-tree-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="d780c-139">Scheda rete di dipendenze &#40;Visualizzatore modello di data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="d780c-139">Dependency Network Tab &#40;Mining Model Viewer&#41;</span></span>](dependency-network-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="d780c-140">Finestra di dialogo Legenda data mining &#40;Visualizzatore modello di data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="d780c-140">Mining Legend Dialog Box &#40;Mining Model Viewer&#41;</span></span>](mining-legend-dialog-box-mining-model-viewer.md)

### <a name="microsoft-linear-regression-algorithm"></a><span data-ttu-id="d780c-141">Algoritmo Microsoft Linear Regression</span><span class="sxs-lookup"><span data-stu-id="d780c-141">Microsoft Linear Regression Algorithm</span></span>

-   [<span data-ttu-id="d780c-142">Visualizzare un modello utilizzando il Visualizzatore Microsoft Neural Network</span><span class="sxs-lookup"><span data-stu-id="d780c-142">Browse a Model Using the Microsoft Neural Network Viewer</span></span>](data-mining/browse-a-model-using-the-microsoft-neural-network-viewer.md)

    -   [<span data-ttu-id="d780c-143">Scheda albero delle decisioni &#40;Visualizzatore modello di data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="d780c-143">Decision Tree Tab &#40;Mining Model Viewer&#41;</span></span>](decision-tree-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="d780c-144">Scheda rete di dipendenze &#40;Visualizzatore modello di data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="d780c-144">Dependency Network Tab &#40;Mining Model Viewer&#41;</span></span>](dependency-network-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="d780c-145">Finestra di dialogo Legenda data mining &#40;Visualizzatore modello di data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="d780c-145">Mining Legend Dialog Box &#40;Mining Model Viewer&#41;</span></span>](mining-legend-dialog-box-mining-model-viewer.md)

### <a name="microsoft-logistic-regression-algorithm"></a><span data-ttu-id="d780c-146">Algoritmo Microsoft Logistic Regression</span><span class="sxs-lookup"><span data-stu-id="d780c-146">Microsoft Logistic Regression Algorithm</span></span>

-   [<span data-ttu-id="d780c-147">Visualizzare un modello utilizzando il Visualizzatore Microsoft Neural Network</span><span class="sxs-lookup"><span data-stu-id="d780c-147">Browse a Model Using the Microsoft Neural Network Viewer</span></span>](data-mining/browse-a-model-using-the-microsoft-neural-network-viewer.md)

### <a name="microsoft-nave-bayes-algorithm"></a><span data-ttu-id="d780c-148">Algoritmo Microsoft Naive Bayes</span><span class="sxs-lookup"><span data-stu-id="d780c-148">Microsoft Naïve Bayes Algorithm</span></span>

-   [<span data-ttu-id="d780c-149">Visualizzare un modello utilizzando il Visualizzatore Microsoft Naive Bayes</span><span class="sxs-lookup"><span data-stu-id="d780c-149">Browse a Model Using the Microsoft Naive Bayes Viewer</span></span>](data-mining/browse-a-model-using-the-microsoft-naive-bayes-viewer.md)

    -   [<span data-ttu-id="d780c-150">Scheda rete di dipendenze &#40;Visualizzatore modello di data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="d780c-150">Dependency Network Tab &#40;Mining Model Viewer&#41;</span></span>](dependency-network-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="d780c-151">Scheda Profili attributo &#40;Visualizzatore modello di data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="d780c-151">Attribute Profiles Tab &#40;Mining Model Viewer&#41;</span></span>](attribute-profiles-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="d780c-152">Scheda Caratteristiche attributo &#40;Visualizzatore modello di data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="d780c-152">Attribute Characteristics Tab &#40;Mining Model Viewer&#41;</span></span>](attribute-characteristics-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="d780c-153">Scheda Analisi discriminante attributi &#40;Visualizzatore modello di data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="d780c-153">Attribute Discrimination Tab &#40;Mining Model Viewer&#41;</span></span>](attribute-discrimination-tab-mining-model-viewer.md)

### <a name="microsoft-neural-network-algorithm"></a><span data-ttu-id="d780c-154">Microsoft Neural Network Algorithm</span><span class="sxs-lookup"><span data-stu-id="d780c-154">Microsoft Neural Network Algorithm</span></span>

-   [<span data-ttu-id="d780c-155">Visualizzare un modello utilizzando il Visualizzatore Microsoft Neural Network</span><span class="sxs-lookup"><span data-stu-id="d780c-155">Browse a Model Using the Microsoft Neural Network Viewer</span></span>](data-mining/browse-a-model-using-the-microsoft-neural-network-viewer.md)

    -   [<span data-ttu-id="d780c-156">Scheda rete di dipendenze &#40;Visualizzatore modello di data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="d780c-156">Dependency Network Tab &#40;Mining Model Viewer&#41;</span></span>](dependency-network-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="d780c-157">Visualizzatore modello di data mining &#40;di rete neurale&#41;</span><span class="sxs-lookup"><span data-stu-id="d780c-157">Neural Network &#40;Mining Model Viewer&#41;</span></span>](neural-network-mining-model-viewer.md)

    -   [<span data-ttu-id="d780c-158">Finestra di dialogo Trova nodo &#40;Visualizzatore modello di data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="d780c-158">Find Node Dialog Box &#40;Mining Model Viewer&#41;</span></span>](find-node-dialog-box-mining-model-viewer.md)

### <a name="microsoft-sequence-clustering-algorithm"></a><span data-ttu-id="d780c-159">Algoritmo Microsoft Sequence Clustering</span><span class="sxs-lookup"><span data-stu-id="d780c-159">Microsoft Sequence Clustering Algorithm</span></span>

-   [<span data-ttu-id="d780c-160">Visualizzare un modello usando il Visualizzatore Microsoft Sequence Clustering</span><span class="sxs-lookup"><span data-stu-id="d780c-160">Browse a Model Using the Microsoft Sequence Cluster Viewer</span></span>](data-mining/browse-a-model-using-the-microsoft-sequence-cluster-viewer.md)

    -   [<span data-ttu-id="d780c-161">Scheda Diagramma cluster Sequence Clustering &#40;Visualizzatore modello di data mining</span><span class="sxs-lookup"><span data-stu-id="d780c-161">Sequence Clustering Cluster Diagram Tab &#40;Mining Model Viewer</span></span>](sequence-clustering-cluster-diagram-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="d780c-162">Scheda Profili cluster Sequence Clustering &#40;Visualizzatore modello di data mining</span><span class="sxs-lookup"><span data-stu-id="d780c-162">Sequence Clustering Cluster Profiles Tab &#40;Mining Model Viewer</span></span>](sequence-clustering-cluster-profiles-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="d780c-163">Scheda Caratteristiche cluster Sequence Clustering &#40;Visualizzatore modello di data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="d780c-163">Sequence Clustering Cluster Characteristics Tab &#40;Mining Model Viewer&#41;</span></span>](sequence-clustering-cluster-characteristics-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="d780c-164">Scheda Analisi discriminante cluster Sequence Clustering &#40;Visualizzatore modello di data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="d780c-164">Sequence Clustering Cluster Discrimination Tab &#40;Mining Model Viewer&#41;</span></span>](sequence-clustering-cluster-discrimination-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="d780c-165">Scheda transizione cluster Sequence Clustering &#40;Visualizzatore modello di data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="d780c-165">Sequence Clustering Cluster Transition Tab &#40;Mining Model Viewer&#41;</span></span>](sequence-clustering-cluster-transition-tab-mining-model-viewer.md)

### <a name="microsoft-time-series-algorithm"></a><span data-ttu-id="d780c-166">Algoritmo Microsoft Time Series</span><span class="sxs-lookup"><span data-stu-id="d780c-166">Microsoft Time Series Algorithm</span></span>

-   [<span data-ttu-id="d780c-167">Visualizzare un modello utilizzando il Visualizzatore Microsoft Times Series</span><span class="sxs-lookup"><span data-stu-id="d780c-167">Browse a Model Using the Microsoft Time Series Viewer</span></span>](data-mining/browse-a-model-using-the-microsoft-time-series-viewer.md)

    -   [<span data-ttu-id="d780c-168">Scheda modello &#40;visualizzatori modello di data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="d780c-168">Model Tab &#40;Mining Model Viewers&#41;</span></span>](model-tab-mining-model-viewers.md)

    -   [<span data-ttu-id="d780c-169">Scheda grafico &#40;visualizzatori modello di data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="d780c-169">Chart Tab &#40;Mining Model Viewers&#41;</span></span>](chart-tab-mining-model-viewers.md)

    -   [<span data-ttu-id="d780c-170">Finestra di dialogo Legenda data mining &#40;Visualizzatore modello di data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="d780c-170">Mining Legend Dialog Box &#40;Mining Model Viewer&#41;</span></span>](mining-legend-dialog-box-mining-model-viewer.md)

## <a name="see-also"></a><span data-ttu-id="d780c-171">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d780c-171">See Also</span></span>
 <span data-ttu-id="d780c-172">[Visualizzazione modelli](mining-models-view-data-mining-model-designer.md) di data mining &#40;Progettazione modelli di data mining&#41;visualizzazione struttura di data mining [&#40;Progettazione modelli di data mining&#41;](mining-structure-view-data-mining-model-designer.md) [progettazione grafico di accuratezza](mining-accuracy-chart-designer-data-mining.md) modello di data mining &#40;[PREDICTION](prediction-query-builder-data-mining.md)&#41;generatore di query &#40;data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="d780c-172">[Mining Models View &#40;Data Mining Model Designer&#41;](mining-models-view-data-mining-model-designer.md) [Mining Structure View &#40;Data Mining Model Designer&#41;](mining-structure-view-data-mining-model-designer.md) [Mining Accuracy Chart Designer &#40;Data Mining&#41;](mining-accuracy-chart-designer-data-mining.md) [Prediction Query Builder &#40;Data Mining&#41;](prediction-query-builder-data-mining.md)</span></span>


