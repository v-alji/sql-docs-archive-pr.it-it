---
title: 'Lezione 2: compilazione di uno scenario di previsione (Esercitazione intermedia sul data mining) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- time series [Analysis Services]
- data mining [Analysis Services], tutorials
- tutorials [Data Mining]
ms.assetid: 9a988156-c900-4c22-97fa-f6b0c1aea9e2
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: c81d5846df0a37c2b4182cb92fea86ce6f3417a7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623679"
---
# <a name="lesson-2-building-a-forecasting-scenario-intermediate-data-mining-tutorial"></a><span data-ttu-id="ca6e5-102">Lezione 2: Compilazione di uno scenario di previsione (Esercitazione intermedia sul data mining)</span><span class="sxs-lookup"><span data-stu-id="ca6e5-102">Lesson 2: Building a Forecasting Scenario (Intermediate Data Mining Tutorial)</span></span>
  <span data-ttu-id="ca6e5-103">In qualità di analista delle vendite di [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)], si supponga di aver ricevuto la richiesta di stimare le vendite dei prodotti del prossimo anno.</span><span class="sxs-lookup"><span data-stu-id="ca6e5-103">As the sales analyst for [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)], you have been asked to forecast the sales of products for the next year.</span></span> <span data-ttu-id="ca6e5-104">In particolare, viene richiesto di confrontare le previsioni per le diverse regioni e linee di prodotti.</span><span class="sxs-lookup"><span data-stu-id="ca6e5-104">In particular, you have been asked to compare forecasts for the different regions and product lines.</span></span> <span data-ttu-id="ca6e5-105">È stato inoltre richiesto di determinare se le vendite dei singoli prodotti sono da mettere in relazione al periodo dell'anno.</span><span class="sxs-lookup"><span data-stu-id="ca6e5-105">Additionally, you have been asked to determine whether sales of different products vary depending on the time of the year.</span></span>  
  
 <span data-ttu-id="ca6e5-106">Per trovare le informazioni richieste, in questa lezione si riepilogano i dati di vendita mensili dell'azienda e le cifre sulle vendite verranno suddivise in tre regioni: Europa, America del nord e Pacifico.</span><span class="sxs-lookup"><span data-stu-id="ca6e5-106">To find the requested information, in this lesson you will summarize the company's sales data at the monthly level, and you will also summarize sales figures by three regions: Europe, North America, and the Pacific.</span></span>  
  
 <span data-ttu-id="ca6e5-107">Dopo aver completato le attività di questa lezione, sarà possibile rispondere alle domande seguenti:</span><span class="sxs-lookup"><span data-stu-id="ca6e5-107">After you complete the tasks in this lesson, you will be able to answer the following questions:</span></span>  
  
-   <span data-ttu-id="ca6e5-108">In che modo le vendite di modelli diversi di biciclette cambiano nel corso del tempo?</span><span class="sxs-lookup"><span data-stu-id="ca6e5-108">How do the sales of different bike models change over time?</span></span>  
  
-   <span data-ttu-id="ca6e5-109">Esistono differenze tra i modelli di vendita nelle tre aree?</span><span class="sxs-lookup"><span data-stu-id="ca6e5-109">Are there differences between the patterns for sales in the three regions?</span></span>  
  
-   <span data-ttu-id="ca6e5-110">È possibile prevedere i periodi di massima vendita?</span><span class="sxs-lookup"><span data-stu-id="ca6e5-110">Can we forecast sales peaks?</span></span>  
  
 <span data-ttu-id="ca6e5-111">È possibile completare la lezione in due parti:</span><span class="sxs-lookup"><span data-stu-id="ca6e5-111">The lesson can be completed in two parts:</span></span>  
  
-   <span data-ttu-id="ca6e5-112">Nella prima parte si illustrano i concetti di base relativi alla creazione e all'utilizzo di un modello Time Series.</span><span class="sxs-lookup"><span data-stu-id="ca6e5-112">Part One introduces the basics of how to create and use a time series model.</span></span>  
  
-   <span data-ttu-id="ca6e5-113">Nella seconda parte viene illustrata la creazione di un modello Time Series generale, basato su tutte le aree.</span><span class="sxs-lookup"><span data-stu-id="ca6e5-113">Part Two walks you through creation of a general time series model, based on all regions.</span></span> <span data-ttu-id="ca6e5-114">È possibile utilizzare questo modello generale per la *stima incrociata*.</span><span class="sxs-lookup"><span data-stu-id="ca6e5-114">You can use this general model for *cross-prediction*.</span></span>  
  
 <span data-ttu-id="ca6e5-115">Per completare le attività di questa lezione, elencate di seguito, verrà utilizzata l' [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] origine dati creata nella [lezione 1: creazione della soluzione intermedia di data mining &#40;esercitazione intermedia sul data mining&#41;](../../2014/tutorials/lesson-1-create-solution-intermediate-data-mining-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="ca6e5-115">To complete the tasks in this lesson, which are listed below, you will use the [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] data source that you created in [Lesson 1: Creating the Intermediate Data Mining Solution &#40;Intermediate Data Mining Tutorial&#41;](../../2014/tutorials/lesson-1-create-solution-intermediate-data-mining-tutorial.md).</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="ca6e5-116">Le date nel database di esempio [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] sono state aggiornate per questa versione.</span><span class="sxs-lookup"><span data-stu-id="ca6e5-116">The dates in the [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] sample database have been updated for this release.</span></span> <span data-ttu-id="ca6e5-117">Se si utilizza una versione precedente di [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)], è possibile compilare il modello seguendo questi passaggi, ma è possibile che vengano visualizzati risultati diversi.</span><span class="sxs-lookup"><span data-stu-id="ca6e5-117">If you use an earlier version of [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)], you can build the model following these steps, but you might see different results.</span></span>  
  
 <span data-ttu-id="ca6e5-118">**Creazione di un modello di stima semplice**</span><span class="sxs-lookup"><span data-stu-id="ca6e5-118">**Creating a Simple Forecasting Model**</span></span>  
  
-   [<span data-ttu-id="ca6e5-119">Aggiunta di una vista origine dati per la previsione &#40;esercitazione intermedia sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="ca6e5-119">Adding a Data Source View for Forecasting &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/adding-a-data-source-view-for-forecasting-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="ca6e5-120">Creazione di una struttura e di un modello di previsione &#40;esercitazione intermedia sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="ca6e5-120">Creating a Forecasting Structure and Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-a-forecasting-structure-and-model-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="ca6e5-121">Modifica della struttura di previsione &#40;esercitazione intermedia sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="ca6e5-121">Modifying the Forecasting Structure &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/modifying-the-forecasting-structure-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="ca6e5-122">Personalizzazione ed elaborazione del modello di previsione &#40;esercitazione intermedia sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="ca6e5-122">Customizing and Processing the Forecasting Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/customize-process-forecasting-model-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="ca6e5-123">Esplorazione del modello di previsione &#40;esercitazione intermedia sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="ca6e5-123">Exploring the Forecasting Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-forecasting-model-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="ca6e5-124">Creazione di stime basate su serie temporali &#40;esercitazione intermedia sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="ca6e5-124">Creating Time Series Predictions &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-time-series-predictions-intermediate-data-mining-tutorial.md)  
  
 <span data-ttu-id="ca6e5-125">**Creazione di un modello di stima generico per l'esecuzione di stime incrociate**</span><span class="sxs-lookup"><span data-stu-id="ca6e5-125">**Creating a General Forecasting Model for Cross-Prediction**</span></span>  
  
-   [<span data-ttu-id="ca6e5-126">Stime avanzate basate su serie temporali &#40;esercitazione intermedia sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="ca6e5-126">Advanced Time Series Predictions &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/advanced-time-series-predictions-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="ca6e5-127">Stime basate su serie temporali che utilizzano dati aggiornati &#40;esercitazione intermedia sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="ca6e5-127">Time Series Predictions using Updated Data &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/time-series-predictions-using-updated-data-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="ca6e5-128">Stime basate su serie temporali che utilizzano dati sostitutivi &#40;esercitazione intermedia sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="ca6e5-128">Time Series Predictions using Replacement Data &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/time-series-predictions-replacement-data-intermediate-data-mining.md)  
  
-   [<span data-ttu-id="ca6e5-129">Confronto delle stime per i modelli di previsione &#40;esercitazione intermedia sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="ca6e5-129">Comparing Predictions for Forecasting Models &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/comparing-predictions-for-forecasting-models-intermediate-data-mining-tutorial.md)  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="ca6e5-130">Attività successiva della lezione</span><span class="sxs-lookup"><span data-stu-id="ca6e5-130">Next Task in Lesson</span></span>  
 [<span data-ttu-id="ca6e5-131">Aggiunta di una vista origine dati per la previsione &#40;esercitazione intermedia sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="ca6e5-131">Adding a Data Source View for Forecasting &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/adding-a-data-source-view-for-forecasting-intermediate-data-mining-tutorial.md)  
  
 [<span data-ttu-id="ca6e5-132">Informazioni sui requisiti per un modello Time Series &#40;esercitazione intermedia sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="ca6e5-132">Understanding the Requirements for a Time Series Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/time-series-model-requirements-intermediate-data-mining-tutorial.md)  
  
## <a name="all-lessons"></a><span data-ttu-id="ca6e5-133">Tutte le lezioni</span><span class="sxs-lookup"><span data-stu-id="ca6e5-133">All Lessons</span></span>  
 [<span data-ttu-id="ca6e5-134">Lezione 1: creazione della soluzione intermedia di data mining &#40;esercitazione intermedia sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="ca6e5-134">Lesson 1: Creating the Intermediate Data Mining Solution &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-1-create-solution-intermediate-data-mining-tutorial.md)  
  
 <span data-ttu-id="ca6e5-135">Lezione 2: Scenario di previsione (Esercitazione intermedia sul data mining)</span><span class="sxs-lookup"><span data-stu-id="ca6e5-135">Lesson 2: Forecasting Scenario (Intermediate Data Mining Tutorial)</span></span>  
  
 [<span data-ttu-id="ca6e5-136">Lezione 3: Compilazione di uno scenario Market Basket &#40;Esercitazione intermedia sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="ca6e5-136">Lesson 3: Building a Market Basket Scenario &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-3-building-a-market-basket-scenario-intermediate-data-mining-tutorial.md)  
  
 [<span data-ttu-id="ca6e5-137">Lezione 4: compilazione di uno scenario di clustering delle sequenze &#40;esercitazione intermedia sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="ca6e5-137">Lesson 4: Building a Sequence Clustering Scenario &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-4-build-sequence-clustering-scenario-intermediate-data-mining.md)  
  
 [<span data-ttu-id="ca6e5-138">Lezione 5: Compilazione dei modelli di rete neurale e di regressione logistica &#40;Esercitazione intermedia sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="ca6e5-138">Lesson 5: Building Neural Network and Logistic Regression Models &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-5-build-models-intermediate-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="ca6e5-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ca6e5-139">See Also</span></span>  
 <span data-ttu-id="ca6e5-140">[Esercitazione di base sul data mining](../../2014/tutorials/basic-data-mining-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="ca6e5-140">[Basic Data Mining Tutorial](../../2014/tutorials/basic-data-mining-tutorial.md) </span></span>  
 <span data-ttu-id="ca6e5-141">[Esercitazione intermedia sul data mining &#40;Analysis Services-&#41;di data mining](../../2014/tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="ca6e5-141">[Intermediate Data Mining Tutorial &#40;Analysis Services - Data Mining&#41;](../../2014/tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="ca6e5-142">Algoritmo Microsoft Time Series</span><span class="sxs-lookup"><span data-stu-id="ca6e5-142">Microsoft Time Series Algorithm</span></span>](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm.md)  
  
  
