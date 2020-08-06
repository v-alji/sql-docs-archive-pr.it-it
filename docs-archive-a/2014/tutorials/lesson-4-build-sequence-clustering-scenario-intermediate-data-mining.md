---
title: 'Lezione 4: compilazione di uno scenario di clustering delle sequenze (Esercitazione intermedia sul data mining) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data mining [Analysis Services], tutorials
- sequence clustering algorithms [Analysis Services]
- tutorials [Data Mining]
ms.assetid: 63436bbd-0f73-4012-b6f1-358c81e4d92a
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 0f417c685d8af898de7c66ffe82045fa76b582e6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711179"
---
# <a name="lesson-4-building-a-sequence-clustering-scenario-intermediate-data-mining-tutorial"></a><span data-ttu-id="dd043-102">Lezione 4: Compilazione di uno scenario di clustering delle sequenze (Esercitazione intermedia sul data mining)</span><span class="sxs-lookup"><span data-stu-id="dd043-102">Lesson 4: Building a Sequence Clustering Scenario (Intermediate Data Mining Tutorial)</span></span>
  <span data-ttu-id="dd043-103">Il reparto marketing di [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] intende comprendere in che modo i clienti visitano il sito Web di [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="dd043-103">The marketing department of [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] wants to understand how customers move through the [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] Web site.</span></span> <span data-ttu-id="dd043-104">L'azienda ritiene che esista un modello in base al quale i clienti inseriscono i prodotti nei rispettivi carrelli della spesa.</span><span class="sxs-lookup"><span data-stu-id="dd043-104">The company suspects that there is a pattern to the order in which customers put products into their shopping baskets.</span></span> <span data-ttu-id="dd043-105">Desidera quindi analizzare l'ordine delle sequenze di acquisto per sapere in che modo i clienti includono i prodotti tra gli acquisti.</span><span class="sxs-lookup"><span data-stu-id="dd043-105">They want to analyze the order of purchase sequences to learn how customers add related items to their baskets.</span></span> <span data-ttu-id="dd043-106">L'azienda può quindi utilizzare queste informazioni per rendere il sito Web più efficiente in modo da indurre i clienti ad acquistare altri prodotti.</span><span class="sxs-lookup"><span data-stu-id="dd043-106">They can then use this information to streamline the flow of the Web site so that it leads customers to purchase additional products.</span></span>  
  
 <span data-ttu-id="dd043-107">Dopo aver completato le attività incluse in questa lezione, si avrà creato un modello di data mining che utilizza l'algoritmo [!INCLUDE[msCoName](../includes/msconame-md.md)] Sequence Clustering per prevedere quale sarà il prodotto successivo che il cliente inserirà tra gli acquisti.</span><span class="sxs-lookup"><span data-stu-id="dd043-107">After you complete the tasks in this lesson, you will have created a mining model that uses the [!INCLUDE[msCoName](../includes/msconame-md.md)] Sequence Clustering algorithm to predict the next item that customers will put into their shopping baskets.</span></span> <span data-ttu-id="dd043-108">Verranno utilizzate due versioni del modello: una analizza solo l'ordine dei prodotti inclusi tra gli acquisti e l'altra contiene dati demografici aggiuntivi del cliente per il clustering.</span><span class="sxs-lookup"><span data-stu-id="dd043-108">You will experiment with two versions of the model: one that analyzes only the order of products in the basket, and one that contains some additional customer demographics for clustering.</span></span> <span data-ttu-id="dd043-109">Infine, si utilizzeranno i modelli per creare stime da utilizzare per consigliare prodotti ai clienti.</span><span class="sxs-lookup"><span data-stu-id="dd043-109">Finally, you will use the models to create predictions that you can use to recommend products to customers.</span></span>  
  
 <span data-ttu-id="dd043-110">Per completare le attività della lezione, si utilizzerà la struttura di data mining Market Basket creata nella [lezione 3: creazione di uno scenario Market basket &#40;esercitazione intermedia sul data mining&#41;](../../2014/tutorials/lesson-3-building-a-market-basket-scenario-intermediate-data-mining-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="dd043-110">To complete the tasks in the lesson, you will use the market basket mining structure that you created in [Lesson 3: Building a Market Basket Scenario &#40;Intermediate Data Mining Tutorial&#41;](../../2014/tutorials/lesson-3-building-a-market-basket-scenario-intermediate-data-mining-tutorial.md).</span></span> <span data-ttu-id="dd043-111">In questa lezione sono incluse le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="dd043-111">This lesson contains the following tasks:</span></span>  
  
-   [<span data-ttu-id="dd043-112">Creazione di una struttura del modello di data mining Sequence Clustering &#40;esercitazione intermedia sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="dd043-112">Creating a Sequence Clustering Mining Model Structure &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/create-sequence-clustering-mining-model-intermediate-data-mining.md)  
  
-   [<span data-ttu-id="dd043-113">Elaborazione del modello Sequence Clustering</span><span class="sxs-lookup"><span data-stu-id="dd043-113">Processing the Sequence Clustering Model</span></span>](../../2014/tutorials/processing-the-sequence-clustering-model.md)  
  
-   [<span data-ttu-id="dd043-114">Esplorazione del modello Sequence Clustering &#40;esercitazione intermedia sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="dd043-114">Exploring the Sequence Clustering Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-sequence-clustering-model-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="dd043-115">Creazione di un modello Sequence Clustering correlato &#40;esercitazione intermedia sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="dd043-115">Creating a Related Sequence Clustering Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-a-related-sequence-clustering-model-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="dd043-116">Creazione di stime in un modello Sequence Clustering &#40;esercitazione intermedia sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="dd043-116">Creating Predictions on a Sequence Clustering Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/create-predictions-on-model-intermediate-data-mining-tutorial.md)  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="dd043-117">Attività successiva della lezione</span><span class="sxs-lookup"><span data-stu-id="dd043-117">Next Task in Lesson</span></span>  
 [<span data-ttu-id="dd043-118">Creazione di una struttura del modello di data mining Sequence Clustering &#40;esercitazione intermedia sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="dd043-118">Creating a Sequence Clustering Mining Model Structure &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/create-sequence-clustering-mining-model-intermediate-data-mining.md)  
  
## <a name="all-lessons"></a><span data-ttu-id="dd043-119">Tutte le lezioni</span><span class="sxs-lookup"><span data-stu-id="dd043-119">All Lessons</span></span>  
 [<span data-ttu-id="dd043-120">Lezione 1: creazione della soluzione intermedia di data mining &#40;esercitazione intermedia sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="dd043-120">Lesson 1: Creating the Intermediate Data Mining Solution &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-1-create-solution-intermediate-data-mining-tutorial.md)  
  
 [<span data-ttu-id="dd043-121">Lezione 2: compilazione di uno scenario di previsione &#40;esercitazione intermedia sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="dd043-121">Lesson 2: Building a Forecasting Scenario &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-2-building-a-forecasting-scenario-intermediate-data-mining-tutorial.md)  
  
 [<span data-ttu-id="dd043-122">Lezione 3: Compilazione di uno scenario Market Basket &#40;Esercitazione intermedia sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="dd043-122">Lesson 3: Building a Market Basket Scenario &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-3-building-a-market-basket-scenario-intermediate-data-mining-tutorial.md)  
  
 <span data-ttu-id="dd043-123">Lezione 4: Scenario di clustering delle sequenze (Esercitazione intermedia sul data mining)</span><span class="sxs-lookup"><span data-stu-id="dd043-123">Lesson 4: Sequence Clustering Scenario (Intermediate Data Mining Tutorial)</span></span>  
  
 [<span data-ttu-id="dd043-124">Lezione 5: Compilazione dei modelli di rete neurale e di regressione logistica &#40;Esercitazione intermedia sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="dd043-124">Lesson 5: Building Neural Network and Logistic Regression Models &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-5-build-models-intermediate-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="dd043-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dd043-125">See Also</span></span>  
 <span data-ttu-id="dd043-126">[Esercitazione di base sul data mining](../../2014/tutorials/basic-data-mining-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="dd043-126">[Basic Data Mining Tutorial](../../2014/tutorials/basic-data-mining-tutorial.md) </span></span>  
 [<span data-ttu-id="dd043-127">Esercitazione intermedia sul data mining &#40;Analysis Services-&#41;di data mining</span><span class="sxs-lookup"><span data-stu-id="dd043-127">Intermediate Data Mining Tutorial &#40;Analysis Services - Data Mining&#41;</span></span>](../../2014/tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md)  
  
  
