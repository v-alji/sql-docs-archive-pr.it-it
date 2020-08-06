---
title: 'Lezione 5: compilazione di modelli di rete neurale e di regressione logistica (Esercitazione intermedia sul data mining) | Microsoft Docs'
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- logistic regression [Analysis Services]
- data mining [Analysis Services], tutorials
- neural networks
- tutorials [Data Mining]
- neural network model [Analysis Services]
ms.assetid: 42c3701a-1fd2-44ff-b7de-377345bbbd6b
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: a8c9fcf0380582f15fa2bf30d6fdeb97bb2ab1fe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627571"
---
# <a name="lesson-5-building-neural-network-and-logistic-regression-models-intermediate-data-mining-tutorial"></a><span data-ttu-id="33df3-102">Lezione 5: Compilazione dei modelli di rete neurale e di regressione logistica (Esercitazione intermedia sul data mining)</span><span class="sxs-lookup"><span data-stu-id="33df3-102">Lesson 5: Building Neural Network and Logistic Regression Models (Intermediate Data Mining Tutorial)</span></span>
  
  
 <span data-ttu-id="33df3-103">Il reparto operativo di [!INCLUDE[ssSampleDBCoShort](../includes/sssampledbcoshort-md.md)] è coinvolto in un progetto per migliorare il livello di soddisfazione dei clienti del call center.</span><span class="sxs-lookup"><span data-stu-id="33df3-103">The Operations department of [!INCLUDE[ssSampleDBCoShort](../includes/sssampledbcoshort-md.md)] is engaged in a project to improve customer satisfaction with their call center.</span></span> <span data-ttu-id="33df3-104">La gestione del call center è stata affidata a un fornitore che deve anche raccogliere dati sull'efficienza del call center che dovranno essere analizzati.</span><span class="sxs-lookup"><span data-stu-id="33df3-104">They hired a vendor to manage the call center and to report metrics on call center effectiveness, and have asked you to analyze some preliminary data provided by the vendor.</span></span> <span data-ttu-id="33df3-105">Si desidera sapere se sono presenti dati interessanti,</span><span class="sxs-lookup"><span data-stu-id="33df3-105">They want to know if there are any interesting findings.</span></span> <span data-ttu-id="33df3-106">in particolare se i dati suggeriscono problemi del personale o soluzioni per migliorare la soddisfazione dei clienti.</span><span class="sxs-lookup"><span data-stu-id="33df3-106">In particular, they would like to know if the data suggests any staffing problems with staffing or ways to improve customer satisfaction.</span></span>  
  
 <span data-ttu-id="33df3-107">Il set di dati è piccolo e riguarda solo un periodo di 30 giorni di funzionamento del call center.</span><span class="sxs-lookup"><span data-stu-id="33df3-107">The data set is small and covers only a 30-day period in the operation of the call center.</span></span> <span data-ttu-id="33df3-108">I dati includono il numero di operatori esperti per ogni turno, il numero di chiamate in ingresso, il numero di ordini e i problemi che è necessario risolvere, nonché il tempo medio che un cliente attende che qualcuno risponda a una chiamata.</span><span class="sxs-lookup"><span data-stu-id="33df3-108">The data tracks the number of new and experienced operators in each shift, the number of incoming calls, the number of orders as well as issues that must be resolved, and the average time a customer waits for someone to respond to a call.</span></span> <span data-ttu-id="33df3-109">I dati includono anche una metrica della qualità del servizio basata sulla *frequenza di abbandono*, che è un indicatore della frustrazione del cliente.</span><span class="sxs-lookup"><span data-stu-id="33df3-109">The data also includes a service quality metric based on *abandon rate*, which is an indicator of customer frustration.</span></span>  
  
 <span data-ttu-id="33df3-110">Poiché non esistono previsioni per i risultati dei dati, si decide di utilizzare un modello di rete neurale per esplorare le possibili correlazioni.</span><span class="sxs-lookup"><span data-stu-id="33df3-110">Because you do not have any prior expectations about what the data will show, you decide to use a neural network model to explore possible correlations.</span></span> <span data-ttu-id="33df3-111">I modelli di rete neurale vengono spesso utilizzati per l'esplorazione perché consentono di analizzare relazioni complesse tra molti input e output.</span><span class="sxs-lookup"><span data-stu-id="33df3-111">Neural network models are often used for exploration because they can analyze complex relationships between many inputs and outputs.</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="33df3-112">Lezioni dell'esercitazione</span><span class="sxs-lookup"><span data-stu-id="33df3-112">What You Will Learn</span></span>  
 <span data-ttu-id="33df3-113">In questa lezione verrà utilizzato l'algoritmo Microsoft Neural Network per compilare un modello che sarà possibile utilizzare con il team del reparto operativo per comprendere i dati.</span><span class="sxs-lookup"><span data-stu-id="33df3-113">In this lesson, you will use the neural network algorithm to build a model that you and the Operations team can use to understand the trends in the data.</span></span> <span data-ttu-id="33df3-114">In questa lezione si tenterà di rispondere alle domande seguenti:</span><span class="sxs-lookup"><span data-stu-id="33df3-114">As part of this lesson, you will try to answer the following questions:</span></span>  
  
-   <span data-ttu-id="33df3-115">Quali fattori influiscono sulla soddisfazione dei clienti?</span><span class="sxs-lookup"><span data-stu-id="33df3-115">What factors affect customer satisfaction?</span></span>  
  
-   <span data-ttu-id="33df3-116">Che cosa può fare il call center per migliorare la qualità del servizio?</span><span class="sxs-lookup"><span data-stu-id="33df3-116">What can the call center do to improve service quality?</span></span>  
  
 <span data-ttu-id="33df3-117">In base ai risultati si compilerà quindi un modello di regressione logistica che risulterà utile per ottenere le stime</span><span class="sxs-lookup"><span data-stu-id="33df3-117">Based on the results, you will then build a logistic regression model that you can use for predictions.</span></span> <span data-ttu-id="33df3-118">che saranno utilizzate dal team operativo per supportare la pianificazione del funzionamento del call center.</span><span class="sxs-lookup"><span data-stu-id="33df3-118">The predictions will be used by the Operations team as an aid in planning call center operation.</span></span>  
  
 <span data-ttu-id="33df3-119">In questa lezione sono inclusi gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="33df3-119">This lesson contains the following topics:</span></span>  
  
-   [<span data-ttu-id="33df3-120">Aggiunta di una vista origine dati per i dati del Call Center &#40;esercitazione intermedia sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="33df3-120">Adding a Data Source View for Call Center Data &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/add-data-source-view-call-center-data-intermediate-data-mining.md)  
  
-   [<span data-ttu-id="33df3-121">Creazione di una struttura e di un modello di rete neurale &#40;esercitazione intermedia sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="33df3-121">Creating a Neural Network Structure and Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-a-neural-network-structure-and-model-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="33df3-122">Esplorazione del modello di Call Center &#40;esercitazione intermedia sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="33df3-122">Exploring the Call Center Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-call-center-model-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="33df3-123">Aggiunta di un modello di regressione logistica alla struttura del Call Center &#40;esercitazione intermedia sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="33df3-123">Adding a Logistic Regression Model to the Call Center Structure &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/add-logistic-regression-model-to-call-center-intermediate-data-mining.md)  
  
-   [<span data-ttu-id="33df3-124">Creazione di stime per i modelli di Call Center &#40;esercitazione intermedia sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="33df3-124">Creating Predictions for the Call Center Models &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/create-predictions-call-center-models-intermediate-data-mining-tutorial.md)  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="33df3-125">Attività successiva della lezione</span><span class="sxs-lookup"><span data-stu-id="33df3-125">Next Task in Lesson</span></span>  
 [<span data-ttu-id="33df3-126">Aggiunta di una vista origine dati per i dati del Call Center &#40;esercitazione intermedia sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="33df3-126">Adding a Data Source View for Call Center Data &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/add-data-source-view-call-center-data-intermediate-data-mining.md)  
  
## <a name="all-lessons"></a><span data-ttu-id="33df3-127">Tutte le lezioni</span><span class="sxs-lookup"><span data-stu-id="33df3-127">All Lessons</span></span>  
 [<span data-ttu-id="33df3-128">Lezione 1: creazione della soluzione intermedia di data mining &#40;esercitazione intermedia sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="33df3-128">Lesson 1: Creating the Intermediate Data Mining Solution &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-1-create-solution-intermediate-data-mining-tutorial.md)  
  
 [<span data-ttu-id="33df3-129">Lezione 2: compilazione di uno scenario di previsione &#40;esercitazione intermedia sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="33df3-129">Lesson 2: Building a Forecasting Scenario &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-2-building-a-forecasting-scenario-intermediate-data-mining-tutorial.md)  
  
 [<span data-ttu-id="33df3-130">Lezione 3: Compilazione di uno scenario Market Basket &#40;Esercitazione intermedia sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="33df3-130">Lesson 3: Building a Market Basket Scenario &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-3-building-a-market-basket-scenario-intermediate-data-mining-tutorial.md)  
  
 [<span data-ttu-id="33df3-131">Lezione 4: compilazione di uno scenario di clustering delle sequenze &#40;esercitazione intermedia sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="33df3-131">Lesson 4: Building a Sequence Clustering Scenario &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-4-build-sequence-clustering-scenario-intermediate-data-mining.md)  
  
 <span data-ttu-id="33df3-132">Lezione 5: Scenario di rete neurale e di regressione logistica (Esercitazione intermedia sul data mining)</span><span class="sxs-lookup"><span data-stu-id="33df3-132">Lesson 5: Neural Network and Logistic Regression Scenario (Intermediate Data Mining Tutorial)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33df3-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="33df3-133">See Also</span></span>  
 <span data-ttu-id="33df3-134">[Esercitazione di base sul data mining](../../2014/tutorials/basic-data-mining-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="33df3-134">[Basic Data Mining Tutorial](../../2014/tutorials/basic-data-mining-tutorial.md) </span></span>  
 [<span data-ttu-id="33df3-135">Esercitazione intermedia sul data mining &#40;Analysis Services-&#41;di data mining</span><span class="sxs-lookup"><span data-stu-id="33df3-135">Intermediate Data Mining Tutorial &#40;Analysis Services - Data Mining&#41;</span></span>](../../2014/tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md)  
  
  
