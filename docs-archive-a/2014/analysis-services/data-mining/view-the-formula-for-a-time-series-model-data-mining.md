---
title: Visualizzazione della formula per un modello Time Series (data mining) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data mining [Analysis Services], how-to topics
- ARTXP
- time series algorithms [Analysis Services]
- ARIMA
- time series [Analysis Services]
- Time Series Viewer [Analysis Services]
ms.assetid: 825ef719-2f44-4979-be01-5a81f54e1a53
author: minewiskan
ms.author: owend
ms.openlocfilehash: eff61c469d34f084e6a0eb11c49a1c37c7cc97c4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623580"
---
# <a name="view-the-formula-for-a-time-series-model-data-mining"></a><span data-ttu-id="ef996-102">Visualizzare la formula per un modello Time Series (Data Mining)</span><span class="sxs-lookup"><span data-stu-id="ef996-102">View the Formula for a Time Series Model (Data Mining)</span></span>
  <span data-ttu-id="ef996-103">Nella [!INCLUDE[msCoName](../../includes/msconame-md.md)] finestra di progettazione di data mining Visualizzatore Time Series è disponibile il modo più semplice per visualizzare i dettagli dell'equazione di regressione utilizzata in un modello Time Series.</span><span class="sxs-lookup"><span data-stu-id="ef996-103">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Time Series viewer inData Mining Designer provides the easiest way to view the details of the regression equation used in a time series model.</span></span>  
  
 <span data-ttu-id="ef996-104">È possibile estrarre la formula di regressione per un modello Time Series eseguendo una query sul contenuto del modello.</span><span class="sxs-lookup"><span data-stu-id="ef996-104">You can extract the regression formula for a time series model by querying the model content.</span></span> <span data-ttu-id="ef996-105">Tuttavia, per visualizzare la formula ARTXP o ARIMA completa, è consigliabile utilizzare **Legenda data mining** del [Visualizzatore Microsoft Time Series](browse-a-model-using-the-microsoft-time-series-viewer.md), che presenta tutte le costanti in un formato leggibile.</span><span class="sxs-lookup"><span data-stu-id="ef996-105">However, to view the complete ARTXP or ARIMA formula, we recommend that you use the **Mining Legend** of the [Microsoft Time Series Viewer](browse-a-model-using-the-microsoft-time-series-viewer.md), which presents all the constants in a readable format.</span></span>  
  
 <span data-ttu-id="ef996-106">Se si crea un modello misto, le analisi ARIMA e ARTXP vengono create in alberi separati e unite in join al nodo radice che rappresenta il modello.</span><span class="sxs-lookup"><span data-stu-id="ef996-106">If you create a mixed model, the ARIMA and ARTXP analyses are created in separate trees, joined at the root node representing the model.</span></span> <span data-ttu-id="ef996-107">Le strutture degli alberi ARIMA e ARTXP sono molto diverse.</span><span class="sxs-lookup"><span data-stu-id="ef996-107">The structures of the ARIMA and ARTXP trees are very different.</span></span> <span data-ttu-id="ef996-108">Ad esempio, l'albero ARTXP è di fatto un albero, come un albero delle decisioni, mentre l'albero ARIMA rappresenta una serie di medie mobili.</span><span class="sxs-lookup"><span data-stu-id="ef996-108">For example, the ARTXP tree is in fact a tree structure, like a decision tree, whereas the ARIMA tree represents a series of moving averages.</span></span> <span data-ttu-id="ef996-109">Pertanto, anche se le due rappresentazioni vengono presentate per praticità in un solo modello, devono essere considerate come due modelli indipendenti.</span><span class="sxs-lookup"><span data-stu-id="ef996-109">Therefore, although the two representations are presented in one model for convenience, they should be treated as two independent models.</span></span> <span data-ttu-id="ef996-110">Anche le equazioni sono completamente diverse e non possono essere combinate né confrontate.</span><span class="sxs-lookup"><span data-stu-id="ef996-110">The equations are also completely different and cannot be combined or compared.</span></span>  
  
 <span data-ttu-id="ef996-111">È inoltre possibile visualizzare i modelli Time Series utilizzando [Microsoft Generic Content Tree Viewer](../microsoft-generic-content-tree-viewer-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="ef996-111">You can also view time series models by using the [Microsoft Generic Content Tree Viewer](../microsoft-generic-content-tree-viewer-data-mining.md).</span></span> <span data-ttu-id="ef996-112">Per ulteriori informazioni sul contenuto di un modello Time Series, vedere il contenuto dei modelli di [data mining per i modelli Time series &#40;Analysis Services-Data mining&#41;](mining-model-content-for-time-series-models-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="ef996-112">For more information about the content of a time series model, see [Mining Model Content for Time Series Models &#40;Analysis Services - Data Mining&#41;](mining-model-content-for-time-series-models-analysis-services-data-mining.md).</span></span>  
  
### <a name="to-view-the-artxp-regression-formula-for-a-time-series-model"></a><span data-ttu-id="ef996-113">Per visualizzare la formula di regressione ARTXP per un modello Time Series</span><span class="sxs-lookup"><span data-stu-id="ef996-113">To view the ARTXP regression formula for a time series model</span></span>  
  
1.  <span data-ttu-id="ef996-114">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]selezionare il modello Time Series da visualizzare e fare clic su **Sfoglia**.</span><span class="sxs-lookup"><span data-stu-id="ef996-114">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], select the time series model that you want to view, and click **Browse**.</span></span>  
  
     <span data-ttu-id="ef996-115">-- o --</span><span class="sxs-lookup"><span data-stu-id="ef996-115">-- or --</span></span>  
  
     <span data-ttu-id="ef996-116">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]selezionare il modello Time Series e fare clic sulla scheda **Visualizzatore modello di data mining** .</span><span class="sxs-lookup"><span data-stu-id="ef996-116">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], select the time series model, and then click the **Mining Model Viewer** tab.</span></span>  
  
2.  <span data-ttu-id="ef996-117">Fare clic sulla scheda **Model** (Modello).</span><span class="sxs-lookup"><span data-stu-id="ef996-117">Click the **Model** tab.</span></span>  
  
3.  <span data-ttu-id="ef996-118">Se il modello contiene più alberi, selezionare un solo albero nell'elenco a discesa **Albero** .</span><span class="sxs-lookup"><span data-stu-id="ef996-118">If the model contains multiple trees, select a single tree from the **Tree** drop-down list.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ef996-119">In presenza di più serie di dati un modello presenta sempre più alberi.</span><span class="sxs-lookup"><span data-stu-id="ef996-119">A model will always have multiple trees if you have more than one data series.</span></span> <span data-ttu-id="ef996-120">Tuttavia, il numero di alberi visualizzati nel **Visualizzatore Time Series** non sarà uguale a quello degli alberi visualizzati in [Microsoft Generic Content Tree Viewer](../microsoft-generic-content-tree-viewer-data-mining.md),</span><span class="sxs-lookup"><span data-stu-id="ef996-120">However, you will not see as many trees in the **Time Series viewer** as you will see in the [Microsoft Generic Content Tree Viewer](../microsoft-generic-content-tree-viewer-data-mining.md).</span></span> <span data-ttu-id="ef996-121">in quanto nel primo caso le informazioni ARIMA e ARTXP di ogni serie di dati vengono combinate in una sola rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="ef996-121">That is because the Time Series viewer combines the ARIMA and ARTXP information for each data series into a single representation.</span></span>  
  
4.  <span data-ttu-id="ef996-122">Fare clic su un nodo foglia dell'albero.</span><span class="sxs-lookup"><span data-stu-id="ef996-122">Click any leaf node in the tree.</span></span>  
  
     <span data-ttu-id="ef996-123">I nodi identificati come **Serie di dati** sono sempre nodi foglia e possono contenere un'equazione.</span><span class="sxs-lookup"><span data-stu-id="ef996-123">Nodes that are labeled as **Data Series** are always leaf nodes and can contain an equation.</span></span> <span data-ttu-id="ef996-124">Se un nodo **(Tutto)** non presenta nodi figlio, può contenere anch'esso un'equazione.</span><span class="sxs-lookup"><span data-stu-id="ef996-124">If an **(All)** node has no child nodes, it can also contain an equation.</span></span>  
  
5.  <span data-ttu-id="ef996-125">Se **Legenda data mining** non è disponibile, fare clic con il pulsante destro del mouse sul nodo e scegliere **Mostra legenda**.</span><span class="sxs-lookup"><span data-stu-id="ef996-125">If the **Mining Legend** is not available, right-click the node, and select **Show Legend**.</span></span>  
  
     <span data-ttu-id="ef996-126">La formula ARTXP viene visualizzata nella prima metà di **Legenda data mining**come **Equazione nodo dell'albero**.</span><span class="sxs-lookup"><span data-stu-id="ef996-126">The ARTXP formula is displayed in the first half of the **Mining Legend**, as the **Tree node equation**.</span></span>  
  
### <a name="to-view-the-arima-formula-for-a-time-series-model"></a><span data-ttu-id="ef996-127">Per visualizzare la formula ARIMA per un modello Time Series</span><span class="sxs-lookup"><span data-stu-id="ef996-127">To view the ARIMA formula for a time series model</span></span>  
  
1.  <span data-ttu-id="ef996-128">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]selezionare il modello Time Series da visualizzare e fare clic su **Sfoglia**.</span><span class="sxs-lookup"><span data-stu-id="ef996-128">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], select the time series model that you want to view, and click **Browse**.</span></span>  
  
     <span data-ttu-id="ef996-129">-- o --</span><span class="sxs-lookup"><span data-stu-id="ef996-129">-- or --</span></span>  
  
     <span data-ttu-id="ef996-130">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]selezionare il modello Time Series e fare clic sulla scheda **Visualizzatore modello di data mining** .</span><span class="sxs-lookup"><span data-stu-id="ef996-130">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], select the time series model, and then click the **Mining Model Viewer** tab.</span></span>  
  
2.  <span data-ttu-id="ef996-131">Fare clic sulla scheda **Model** (Modello).</span><span class="sxs-lookup"><span data-stu-id="ef996-131">Click the **Model** tab.</span></span>  
  
3.  <span data-ttu-id="ef996-132">Se il modello contiene più alberi, selezionare un solo albero nell'elenco a discesa **Albero** .</span><span class="sxs-lookup"><span data-stu-id="ef996-132">If the model contains multiple trees, select a single tree from the **Tree** drop-down list.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ef996-133">Se vengono incluse più serie di dati, il modello presenta sempre più alberi.</span><span class="sxs-lookup"><span data-stu-id="ef996-133">The model will always have multiple trees if you include more than one data series.</span></span>  
  
4.  <span data-ttu-id="ef996-134">Fare clic su un nodo dell'albero.</span><span class="sxs-lookup"><span data-stu-id="ef996-134">Click any node in the tree.</span></span>  
  
     <span data-ttu-id="ef996-135">La formula ARIMA viene visualizzata nella seconda metà di **Legenda data mining**come **Equazione ARIMA**.</span><span class="sxs-lookup"><span data-stu-id="ef996-135">The ARIMA formula is displayed in the second half of the **Mining Legend**, as the **ARIMA equation**.</span></span>  
  
5.  <span data-ttu-id="ef996-136">Se **Legenda data mining** non è disponibile, fare clic con il pulsante destro del mouse sul nodo e scegliere **Mostra legenda**.</span><span class="sxs-lookup"><span data-stu-id="ef996-136">If the **Mining Legend** is not available, right-click the node, and select **Show Legend**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef996-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ef996-137">See Also</span></span>  
 <span data-ttu-id="ef996-138">[Attività e procedure relative al Visualizzatore modello di data mining](mining-model-viewer-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="ef996-138">[Mining Model Viewer Tasks and How-tos](mining-model-viewer-tasks-and-how-tos.md) </span></span>  
 <span data-ttu-id="ef996-139">[Visualizzare un modello utilizzando il Visualizzatore Microsoft Time Series](browse-a-model-using-the-microsoft-time-series-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="ef996-139">[Browse a Model Using the Microsoft Time Series Viewer](browse-a-model-using-the-microsoft-time-series-viewer.md) </span></span>  
 [<span data-ttu-id="ef996-140">Time Series Model Query Examples</span><span class="sxs-lookup"><span data-stu-id="ef996-140">Time Series Model Query Examples</span></span>](time-series-model-query-examples.md)  
  
  
