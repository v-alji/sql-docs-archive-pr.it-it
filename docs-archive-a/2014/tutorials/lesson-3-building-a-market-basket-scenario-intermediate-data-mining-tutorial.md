---
title: 'Lezione 3: compilazione di uno scenario Market Basket (Esercitazione intermedia sul data mining) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data mining [Analysis Services], tutorials
- association algorithms [Analysis Services]
- nested tables
- tutorials [Data Mining]
ms.assetid: 651eef38-772e-4d97-af51-075b1b27fc5a
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: a281aa62fbf08393c95f12ded9886ac212b3165f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720483"
---
# <a name="lesson-3-building-a-market-basket-scenario-intermediate-data-mining-tutorial"></a><span data-ttu-id="343dc-102">Lezione 3: Compilazione di uno scenario Market Basket (Esercitazione intermedia sul data mining)</span><span class="sxs-lookup"><span data-stu-id="343dc-102">Lesson 3: Building a Market Basket Scenario (Intermediate Data Mining Tutorial)</span></span>
  <span data-ttu-id="343dc-103">Il reparto marketing di [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] intende migliorare il sito Web aziendale per promuovere le vendite.</span><span class="sxs-lookup"><span data-stu-id="343dc-103">The marketing department of [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] wants to improve the company Web site to promote cross-selling.</span></span> <span data-ttu-id="343dc-104">Durante l'aggiornamento del sito, si desidera essere in grado di prevedere quali siano i prodotti che i clienti potrebbero essere interessati ad acquistare sulla base dei prodotti già inclusi tra i rispettivi acquisti.</span><span class="sxs-lookup"><span data-stu-id="343dc-104">As part of the site update, they would like the ability to predict products that a customer might want to purchase, based on the other products that are already in the customer's online shopping basket.</span></span> <span data-ttu-id="343dc-105">Il reparto marketing desidera inoltre capire meglio il comportamento di acquisto del cliente, in modo da poter progettare il sito Web in modo da visualizzare nella stessa area gli elementi che tendono a essere acquistati insieme.</span><span class="sxs-lookup"><span data-stu-id="343dc-105">The marketing department also wants to understand customer purchasing behavior better, so that they can design the Web site so that the items that tend to be purchased together appear together.</span></span> <span data-ttu-id="343dc-106">Il team sa che il data mining è particolarmente utile per questo tipo di *Market basket analysis* e chiede di sviluppare un modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="343dc-106">They have learned that data mining is especially useful for this kind of *market basket analysis* and have asked you to develop a data mining model.</span></span>  
  
 <span data-ttu-id="343dc-107">Dopo aver completato le attività di questa lezione, si otterrà un modello di data mining in cui saranno visualizzati i gruppi di articoli riferiti a precedenti transazioni del cliente.</span><span class="sxs-lookup"><span data-stu-id="343dc-107">After you complete the tasks in this lesson, you will have a mining model that shows groups of items from historical customer transactions.</span></span> <span data-ttu-id="343dc-108">Inoltre, è possibile utilizzare il modello di data mining per prevedere gli ulteriori articoli che un cliente può essere interessato ad acquistare.</span><span class="sxs-lookup"><span data-stu-id="343dc-108">Additionally, you can use the mining model to predict additional items that a customer may want to purchase.</span></span>  
  
 <span data-ttu-id="343dc-109">Per completare le attività in questa lezione, si utilizzeranno la soluzione e l'origine dati create nella prima lezione dell' [esercitazione intermedia sul data mining &#40;Analysis Services-Data mining&#41;](../../2014/tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="343dc-109">To complete the tasks in this lesson, you will use the solution and data source that you created in the first lesson of the [Intermediate Data Mining Tutorial &#40;Analysis Services - Data Mining&#41;](../../2014/tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md).</span></span> <span data-ttu-id="343dc-110">Sarà possibile modificare la soluzione aggiungendo una vista origine dati che contiene le tabelle sul cliente, inclusa una tabella nidificata degli acquisti del cliente.</span><span class="sxs-lookup"><span data-stu-id="343dc-110">You will modify this solution by adding a data source view that contains tables about the customer, including a nested table of customer purchases.</span></span>  <span data-ttu-id="343dc-111">Si compilerà quindi un modello di data mining che utilizza l'algoritmo Microsoft Association Rules, indicato per gli scenari Market Basket.</span><span class="sxs-lookup"><span data-stu-id="343dc-111">You will then build a mining model that uses the Microsoft Association Rules algorithm, which is suited to market basket scenarios.</span></span>  
  
 <span data-ttu-id="343dc-112">In questa lezione sono inclusi gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="343dc-112">This lesson contains the following topics:</span></span>  
  
-   [<span data-ttu-id="343dc-113">Aggiunta di una vista origine dati con tabelle nidificate &#40;esercitazione intermedia sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="343dc-113">Adding a Data Source View with Nested Tables &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/adding-a-data-source-view-with-nested-tables-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="343dc-114">Creazione di una struttura e di un modello di Market basket &#40;esercitazione intermedia sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="343dc-114">Creating a Market Basket Structure and Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-a-market-basket-structure-and-model-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="343dc-115">Modifica ed elaborazione del modello Market basket &#40;esercitazione intermedia sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="343dc-115">Modifying and Processing the Market Basket Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/modify-process-market-basket-model-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="343dc-116">Esplorazione dei modelli Market basket &#40;esercitazione intermedia sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="343dc-116">Exploring the Market Basket Models &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-market-basket-models-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="343dc-117">Applicazione di filtri a una tabella nidificata in un modello di data mining &#40;esercitazione intermedia sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="343dc-117">Filtering a Nested Table in a Mining Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/filtering-a-nested-table-in-a-mining-model-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="343dc-118">Stima delle associazioni &#40;esercitazione intermedia sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="343dc-118">Predicting Associations &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/predicting-associations-intermediate-data-mining-tutorial.md)  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="343dc-119">Attività successiva della lezione</span><span class="sxs-lookup"><span data-stu-id="343dc-119">Next Task in Lesson</span></span>  
 [<span data-ttu-id="343dc-120">Aggiunta di una vista origine dati con tabelle nidificate &#40;esercitazione intermedia sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="343dc-120">Adding a Data Source View with Nested Tables &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/adding-a-data-source-view-with-nested-tables-intermediate-data-mining-tutorial.md)  
  
## <a name="all-lessons"></a><span data-ttu-id="343dc-121">Tutte le lezioni</span><span class="sxs-lookup"><span data-stu-id="343dc-121">All Lessons</span></span>  
 [<span data-ttu-id="343dc-122">Lezione 1: creazione della soluzione intermedia di data mining &#40;esercitazione intermedia sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="343dc-122">Lesson 1: Creating the Intermediate Data Mining Solution &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-1-create-solution-intermediate-data-mining-tutorial.md)  
  
 [<span data-ttu-id="343dc-123">Lezione 2: compilazione di uno scenario di previsione &#40;esercitazione intermedia sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="343dc-123">Lesson 2: Building a Forecasting Scenario &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-2-building-a-forecasting-scenario-intermediate-data-mining-tutorial.md)  
  
 <span data-ttu-id="343dc-124">Lezione 3: Scenario Market basket (Esercitazione intermedia sul data mining)</span><span class="sxs-lookup"><span data-stu-id="343dc-124">Lesson 3: Market Basket Scenario (Intermediate Data Mining Tutorial)</span></span>  
  
 [<span data-ttu-id="343dc-125">Lezione 4: compilazione di uno scenario di clustering delle sequenze &#40;esercitazione intermedia sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="343dc-125">Lesson 4: Building a Sequence Clustering Scenario &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-4-build-sequence-clustering-scenario-intermediate-data-mining.md)  
  
 [<span data-ttu-id="343dc-126">Lezione 5: Compilazione dei modelli di rete neurale e di regressione logistica &#40;Esercitazione intermedia sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="343dc-126">Lesson 5: Building Neural Network and Logistic Regression Models &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-5-build-models-intermediate-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="343dc-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="343dc-127">See Also</span></span>  
 <span data-ttu-id="343dc-128">[Esercitazione di base sul data mining](../../2014/tutorials/basic-data-mining-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="343dc-128">[Basic Data Mining Tutorial](../../2014/tutorials/basic-data-mining-tutorial.md) </span></span>  
 <span data-ttu-id="343dc-129">[Lezione 2: compilazione di uno scenario di previsione &#40;esercitazione intermedia sul data mining&#41;](../../2014/tutorials/lesson-2-building-a-forecasting-scenario-intermediate-data-mining-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="343dc-129">[Lesson 2: Building a Forecasting Scenario &#40;Intermediate Data Mining Tutorial&#41;](../../2014/tutorials/lesson-2-building-a-forecasting-scenario-intermediate-data-mining-tutorial.md) </span></span>  
 [<span data-ttu-id="343dc-130">Lezione 4: compilazione di uno scenario di clustering delle sequenze &#40;esercitazione intermedia sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="343dc-130">Lesson 4: Building a Sequence Clustering Scenario &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-4-build-sequence-clustering-scenario-intermediate-data-mining.md)  
  
  
