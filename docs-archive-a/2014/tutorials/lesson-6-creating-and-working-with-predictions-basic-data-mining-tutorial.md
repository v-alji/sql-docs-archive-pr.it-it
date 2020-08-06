---
title: 'Lezione 6: creazione e utilizzo di stime (esercitazione di base sul data mining) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: b213cb58-2c40-4c89-b08b-d3c36a4afad3
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: d0a8bfdf83e96622a19ac72490e8602d12afc9df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626417"
---
# <a name="lesson-6-creating-and-working-with-predictions-basic-data-mining-tutorial"></a><span data-ttu-id="b1b43-102">Lezione 6: Creazione e utilizzo di stime (Esercitazione di base sul data mining)</span><span class="sxs-lookup"><span data-stu-id="b1b43-102">Lesson 6: Creating and Working with Predictions (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="b1b43-103">Finora si è eseguito il training, il testing e l'esplorazione dei modelli di data mining creati.</span><span class="sxs-lookup"><span data-stu-id="b1b43-103">You have trained, tested, and explored the data mining models you created.</span></span> <span data-ttu-id="b1b43-104">Ora è possibile iniziare a utilizzare i modelli per identificare le persone con la più alta probabilità di rispondere alla nuova campagna di mailing diretto.</span><span class="sxs-lookup"><span data-stu-id="b1b43-104">Now you are ready to use the models to identify the people most likely to respond to the new targeted mailing campaign.</span></span>  
  
 <span data-ttu-id="b1b43-105">In questa lezione verrà creata una query per individuare i clienti che con maggiore probabilità acquisteranno una bicicletta.</span><span class="sxs-lookup"><span data-stu-id="b1b43-105">In this lesson you will create a query to predict which customers are most likely to purchase a bike.</span></span> <span data-ttu-id="b1b43-106">Verrà inoltre recuperata la *probabilità* che la stima sia corretta, quindi il reparto marketing può decidere se è possibile decidere se utilizzare o meno la stima.</span><span class="sxs-lookup"><span data-stu-id="b1b43-106">You will also retrieve the *probability* that the prediction is correct, so the marketing department can decide whether to you can decide whether to use the prediction or not.</span></span>  
  
 <span data-ttu-id="b1b43-107">Una volta identificati i clienti con una probabilità di acquisto elevata, si eseguirà il drill-through sui dettagli dei case nel modello di data mining per recuperare nomi e informazioni di contatto per questi clienti.</span><span class="sxs-lookup"><span data-stu-id="b1b43-107">Once you have identified customers with a high probability of purchasing a bike, you will drill through to the details of the cases in the mining model to retrieve names and contact information for these customers.</span></span>  
  
 <span data-ttu-id="b1b43-108">In questa lezione sono inclusi gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="b1b43-108">This lesson contains the following topics:</span></span>  
  
 [<span data-ttu-id="b1b43-109">Creazione di stime &#40;Esercitazione di base sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="b1b43-109">Creating Predictions &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-predictions-basic-data-mining-tutorial.md)  
  
 [<span data-ttu-id="b1b43-110">Utilizzo del drill-through sui dati della struttura &#40;esercitazione di base sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="b1b43-110">Using Drillthrough on Structure Data &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/using-drillthrough-on-structure-data-basic-data-mining-tutorial.md)  
  
## <a name="next-lesson"></a><span data-ttu-id="b1b43-111">Lezione successiva</span><span class="sxs-lookup"><span data-stu-id="b1b43-111">Next Lesson</span></span>  
 [<span data-ttu-id="b1b43-112">Esercitazione intermedia sul data mining &#40;Analysis Services-&#41;di data mining</span><span class="sxs-lookup"><span data-stu-id="b1b43-112">Intermediate Data Mining Tutorial &#40;Analysis Services - Data Mining&#41;</span></span>](../../2014/tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md)  
  
## <a name="previous-lesson"></a><span data-ttu-id="b1b43-113">Lezione precedente</span><span class="sxs-lookup"><span data-stu-id="b1b43-113">Previous Lesson</span></span>  
 [<span data-ttu-id="b1b43-114">Lezione 5: Testing models &#40;esercitazione di base sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="b1b43-114">Lesson 5: Testing Models &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-5-testing-models-basic-data-mining-tutorial.md)  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="b1b43-115">Attività successiva della lezione</span><span class="sxs-lookup"><span data-stu-id="b1b43-115">Next Task in Lesson</span></span>  
 [<span data-ttu-id="b1b43-116">Creazione di stime &#40;Esercitazione di base sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="b1b43-116">Creating Predictions &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-predictions-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="b1b43-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b1b43-117">See Also</span></span>  
 <span data-ttu-id="b1b43-118">[Contenuto del modello di data mining per i modelli di albero delle decisioni &#40;Analysis Services-Data mining&#41;](../../2014/analysis-services/data-mining/mining-model-content-for-decision-tree-models-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="b1b43-118">[Mining Model Content for Decision Tree Models &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/mining-model-content-for-decision-tree-models-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="b1b43-119">Creare una query di stima utilizzando Generatore query di stima</span><span class="sxs-lookup"><span data-stu-id="b1b43-119">Create a Prediction Query Using the Prediction Query Builder</span></span>](../../2014/analysis-services/data-mining/create-a-prediction-query-using-the-prediction-query-builder.md)  
  
  
