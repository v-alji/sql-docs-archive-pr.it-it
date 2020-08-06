---
title: 'Lezione 4: esplorazione dei modelli di mailing diretto (esercitazione di base sul data mining) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 1e00c5b9-a9f8-4503-99ee-377c9cc02d7f
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 8659350b126164e06550acdbecec04bb07499c55
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720471"
---
# <a name="lesson-4-exploring-the-targeted-mailing-models-basic-data-mining-tutorial"></a><span data-ttu-id="d0682-102">Lezione 4: Esplorazione dei modelli di mailing diretto (Esercitazione di base sul data mining)</span><span class="sxs-lookup"><span data-stu-id="d0682-102">Lesson 4: Exploring the Targeted Mailing Models (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="d0682-103">Dopo avere elaborato i modelli nel progetto, è possibile esplorarli per individuare tendenze interessanti.</span><span class="sxs-lookup"><span data-stu-id="d0682-103">After the models in your project have been processed, you can explore them to look for interesting trends.</span></span> <span data-ttu-id="d0682-104">Poiché l'analisi dei numeri dei modelli può risultare difficile e complessa, SQL Server Data Mining offre alcuni strumenti visivi che consentono di analizzare i dati e comprendere le regole e le relazioni che gli algoritmi hanno individuato all'interno dei dati.</span><span class="sxs-lookup"><span data-stu-id="d0682-104">Because patterns can be complex and difficult simply by looking at numbers, SQL Server Data Mining provides some visual tools that help you investigate the data and understand the rules and relationships that the algorithms have discovered within the data.</span></span> <span data-ttu-id="d0682-105">È inoltre possibile utilizzare vari test di accuratezza per convalidare il set di dati o per individuare il modello che garantisce le prestazioni migliori prima di distribuirlo.</span><span class="sxs-lookup"><span data-stu-id="d0682-105">You can also use a variety of accuracy tests to validate your dataset or discover which model performs best before you deploy it.</span></span>  
  
 <span data-ttu-id="d0682-106">Quando si utilizza [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] per esplorare i modelli, ogni modello creato viene elencato nella scheda **Visualizzatore modello** di data mining di progettazione modelli di data mining.</span><span class="sxs-lookup"><span data-stu-id="d0682-106">When you use [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to explore your models, each model you created is listed in the **Mining Model Viewer** tab in Data Mining Designer.</span></span> <span data-ttu-id="d0682-107">Per esplorare i modelli, è possibile utilizzare i visualizzatori.</span><span class="sxs-lookup"><span data-stu-id="d0682-107">You can use the viewers to explore the models.</span></span> <span data-ttu-id="d0682-108">Questi visualizzatori sono disponibili anche in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d0682-108">These viewers are also available in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="d0682-109">Ognuno degli algoritmi utilizzati per compilare un modello in [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] restituisce un risultato di tipo diverso.</span><span class="sxs-lookup"><span data-stu-id="d0682-109">Each algorithm that you used to build a model in [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] returns a different type of result.</span></span> <span data-ttu-id="d0682-110">Di conseguenza, in [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] sono disponibili visualizzatori personalizzati per ogni tipo di modello di apprendimento automatico.</span><span class="sxs-lookup"><span data-stu-id="d0682-110">Therefore, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] provides custom viewers for each type of machine learning model.</span></span>  
  
 <span data-ttu-id="d0682-111">Per informazioni dettagliate, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] fornisce anche un visualizzatore HTML, denominato **Generic Content Tree Viewer**, che consente di visualizzare informazioni dettagliate sui dati del modello e sui modelli rilevati in un formato semi-tabulare.</span><span class="sxs-lookup"><span data-stu-id="d0682-111">If you want to get into details, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] also provides an HTML viewer, called the **Generic Content Tree Viewer**, that displays detailed information about the model data and any patterns that were found, in a semi-tabular format.</span></span> <span data-ttu-id="d0682-112">Per altre informazioni, vedere [Visualizzare un modello utilizzando Microsoft Generic Content Tree Viewer](../../2014/analysis-services/data-mining/browse-a-model-using-the-microsoft-generic-content-tree-viewer.md).</span><span class="sxs-lookup"><span data-stu-id="d0682-112">For more information, see [Browse a Model Using the Microsoft Generic Content Tree Viewer](../../2014/analysis-services/data-mining/browse-a-model-using-the-microsoft-generic-content-tree-viewer.md).</span></span>  
  
 <span data-ttu-id="d0682-113">In questa lezione verranno analizzati dei tre modelli creati.</span><span class="sxs-lookup"><span data-stu-id="d0682-113">In this lesson you will look at the results from your three models.</span></span> <span data-ttu-id="d0682-114">Ogni tipo di modello è basato su un algoritmo diverso e fornisce informazioni diverse sui dati.</span><span class="sxs-lookup"><span data-stu-id="d0682-114">Each model type is based on a different algorithm and provides different insights into the data.</span></span>  
  
-   <span data-ttu-id="d0682-115">Il modello Decision Trees offre informazioni sui fattori che influiscono sull'acquisto di biciclette.</span><span class="sxs-lookup"><span data-stu-id="d0682-115">The Decision Tree model tells you about factors that influence bike buying.</span></span>  
  
-   <span data-ttu-id="d0682-116">Il modello di clustering raggruppa i clienti per attributi che includono il comportamento relativo all'acquisto di biciclette e altri attributi selezionati.</span><span class="sxs-lookup"><span data-stu-id="d0682-116">The Clustering model groups your customers by attributes that include their bike buying behavior and other selected attributes.</span></span>  
  
-   <span data-ttu-id="d0682-117">Il modello Naive Bayes consente di esplorare la relazione tra attributi diversi.</span><span class="sxs-lookup"><span data-stu-id="d0682-117">The Naive Bayes model enables you to explore the relationship between different attributes.</span></span>  
  
 <span data-ttu-id="d0682-118">Per ulteriori informazioni su ogni visualizzatore dei modelli di data mining, vedere gli argomenti seguenti.</span><span class="sxs-lookup"><span data-stu-id="d0682-118">See the following topics to learn more about each of the mining model viewers.</span></span>  
  
-   [<span data-ttu-id="d0682-119">Esplorazione del modello Decision Trees &#40;esercitazione di base sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="d0682-119">Exploring the Decision Tree Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-decision-tree-model-basic-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="d0682-120">Esplorazione del modello di clustering &#40;esercitazione di base sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="d0682-120">Exploring the Clustering Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-clustering-model-basic-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="d0682-121">Esplorazione del modello Naive Bayes &#40;esercitazione di base sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="d0682-121">Exploring the Naive Bayes Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-naive-bayes-model-basic-data-mining-tutorial.md)  
  
 <span data-ttu-id="d0682-122">Tutti e tre i modelli possono essere visualizzati utilizzando **Generic Content Tree Viewer**, per estrarre formule, valori dei dati e così via.</span><span class="sxs-lookup"><span data-stu-id="d0682-122">All three models can be viewed using the **Generic Content Tree Viewer**, to extract formulas, data values, and so forth.</span></span>  
  
## <a name="first-task-in-lesson"></a><span data-ttu-id="d0682-123">Prima attività della lezione</span><span class="sxs-lookup"><span data-stu-id="d0682-123">First Task in Lesson</span></span>  
 [<span data-ttu-id="d0682-124">Esplorazione del modello Decision Trees &#40;esercitazione di base sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="d0682-124">Exploring the Decision Tree Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-decision-tree-model-basic-data-mining-tutorial.md)  
  
## <a name="previous-lesson"></a><span data-ttu-id="d0682-125">Lezione precedente</span><span class="sxs-lookup"><span data-stu-id="d0682-125">Previous Lesson</span></span>  
 [<span data-ttu-id="d0682-126">Lezione 3: Aggiunta ed elaborazione di modelli</span><span class="sxs-lookup"><span data-stu-id="d0682-126">Lesson 3: Adding and Processing Models</span></span>](../../2014/tutorials/lesson-3-adding-and-processing-models.md)  
  
## <a name="next-lesson"></a><span data-ttu-id="d0682-127">Lezione successiva</span><span class="sxs-lookup"><span data-stu-id="d0682-127">Next Lesson</span></span>  
 [<span data-ttu-id="d0682-128">Lezione 5: Testing models &#40;esercitazione di base sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="d0682-128">Lesson 5: Testing Models &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-5-testing-models-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="d0682-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d0682-129">See Also</span></span>  
 <span data-ttu-id="d0682-130">[Attività e procedure relative al Visualizzatore modello di data mining](../../2014/analysis-services/data-mining/mining-model-viewer-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="d0682-130">[Mining Model Viewer Tasks and How-tos](../../2014/analysis-services/data-mining/mining-model-viewer-tasks-and-how-tos.md) </span></span>  
 [<span data-ttu-id="d0682-131">Visualizzatori modello di data mining</span><span class="sxs-lookup"><span data-stu-id="d0682-131">Data Mining Model Viewers</span></span>](../../2014/analysis-services/data-mining/data-mining-model-viewers.md)  
  
  
