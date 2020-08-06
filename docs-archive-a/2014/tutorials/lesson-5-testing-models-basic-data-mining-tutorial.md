---
title: 'Lezione 5: Testing models (esercitazione di base sul data mining) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: e9a7ddcf-2b01-485f-bbb5-62638b303bc6
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: fcfd9a9e90d9c6800af4dfd1599bbdd62d9520ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719067"
---
# <a name="lesson-5-testing-models-basic-data-mining-tutorial"></a><span data-ttu-id="a96f1-102">Lezione 5: Test di modelli (Esercitazione di base sul data mining)</span><span class="sxs-lookup"><span data-stu-id="a96f1-102">Lesson 5: Testing Models (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="a96f1-103">Ora che è stato elaborato il modello tramite il set di training dello scenario relativo al mailing diretto, verranno testati i modelli sul set di testing.</span><span class="sxs-lookup"><span data-stu-id="a96f1-103">Now that you have processed the model by using the targeted mailing scenario training set, you will test your models against the testing set.</span></span> <span data-ttu-id="a96f1-104">La convalida è un passaggio importante del processo di data mining.</span><span class="sxs-lookup"><span data-stu-id="a96f1-104">Validation is an important step in the data mining process.</span></span> <span data-ttu-id="a96f1-105">Prima di distribuire i modelli per il mailing diretto in un ambiente di produzione, è fondamentale verificarne il comportamento in caso di applicazione ai dati real.</span><span class="sxs-lookup"><span data-stu-id="a96f1-105">Knowing how well your targeted mailing mining models perform against real data is important before you deploy the models into a production environment.</span></span>  
  
 <span data-ttu-id="a96f1-106">Poiché i dati nel set di testing contengono già valori noti per l'acquisto di biciclette, la correttezza delle stime del modello può essere determinata facilmente.</span><span class="sxs-lookup"><span data-stu-id="a96f1-106">Because the data in the testing set already contains known values for bike buying, it is easy to determine whether the model's predictions are correct.</span></span> <span data-ttu-id="a96f1-107">Il modello che esegue il migliore verrà usato dal [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] reparto marketing per identificare i clienti per la campagna di mailing diretto.</span><span class="sxs-lookup"><span data-stu-id="a96f1-107">The model that performs the best will be used by the [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] marketing department to identify the customers for their targeted mailing campaign.</span></span>  
  
 <span data-ttu-id="a96f1-108">In questa lezione verranno convalidati i modelli utilizzando più metodi:</span><span class="sxs-lookup"><span data-stu-id="a96f1-108">In this lesson you will validate your models using multiple methods:</span></span>  
  
1.  <span data-ttu-id="a96f1-109">Si eseguiranno stime sul set di testing per verificare l'accuratezza del modello nei risultati noti.</span><span class="sxs-lookup"><span data-stu-id="a96f1-109">You'll make predictions against the testing set to see how accurate the model is on known results.</span></span> <span data-ttu-id="a96f1-110">Si userà un *grafico di accuratezza* per misurarne l'efficacia.</span><span class="sxs-lookup"><span data-stu-id="a96f1-110">You'll use a *lift chart* to measure its effectiveness.</span></span>  
  
     [<span data-ttu-id="a96f1-111">Test dell'accuratezza con i grafici di accuratezza &#40;Esercitazione di base sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="a96f1-111">Testing Accuracy with Lift Charts &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/testing-accuracy-with-lift-charts-basic-data-mining-tutorial.md)  
  
2.  <span data-ttu-id="a96f1-112">I modelli verranno quindi testati su un subset filtrato dei dati.</span><span class="sxs-lookup"><span data-stu-id="a96f1-112">You will test your models on a filtered subset of the data.</span></span> <span data-ttu-id="a96f1-113">Sarà possibile confrontare più modelli nello stesso grafico di accuratezza.</span><span class="sxs-lookup"><span data-stu-id="a96f1-113">You can compare multiple models in the same lift chart.</span></span>  
  
     [<span data-ttu-id="a96f1-114">Test di un modello filtrato &#40;esercitazione di base sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="a96f1-114">Testing a Filtered Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/testing-a-filtered-model-basic-data-mining-tutorial.md)  
  
 <span data-ttu-id="a96f1-115">Per ulteriori informazioni sulla convalida dei modelli in generale, vedere [concetti di data mining](../../2014/analysis-services/data-mining/data-mining-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="a96f1-115">For more information about how model validation in general, see [Data Mining Concepts](../../2014/analysis-services/data-mining/data-mining-concepts.md).</span></span>  
  
## <a name="first-task-in-lesson"></a><span data-ttu-id="a96f1-116">Prima attività della lezione</span><span class="sxs-lookup"><span data-stu-id="a96f1-116">First Task in Lesson</span></span>  
 [<span data-ttu-id="a96f1-117">Test dell'accuratezza con i grafici di accuratezza &#40;Esercitazione di base sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="a96f1-117">Testing Accuracy with Lift Charts &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/testing-accuracy-with-lift-charts-basic-data-mining-tutorial.md)  
  
## <a name="previous-lesson"></a><span data-ttu-id="a96f1-118">Lezione precedente</span><span class="sxs-lookup"><span data-stu-id="a96f1-118">Previous Lesson</span></span>  
 [<span data-ttu-id="a96f1-119">Lezione 4: esplorazione dei modelli di mailing diretto &#40;esercitazione di base sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="a96f1-119">Lesson 4: Exploring the Targeted Mailing Models &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-4-exploring-the-targeted-mailing-models-basic-data-mining-tutorial.md)  
  
## <a name="next-lesson"></a><span data-ttu-id="a96f1-120">Lezione successiva</span><span class="sxs-lookup"><span data-stu-id="a96f1-120">Next Lesson</span></span>  
 [<span data-ttu-id="a96f1-121">Lezione 6: Creazione e utilizzo di stime &#40;Esercitazione di base sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="a96f1-121">Lesson 6: Creating and Working with Predictions &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-6-creating-and-working-with-predictions-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="a96f1-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a96f1-122">See Also</span></span>  
 <span data-ttu-id="a96f1-123">[Scheda grafico di accuratezza &#40;vista Grafico accuratezza modello di data mining&#41;](../../2014/analysis-services/lift-chart-tab-mining-accuracy-chart-view.md) </span><span class="sxs-lookup"><span data-stu-id="a96f1-123">[Lift Chart Tab &#40;Mining Accuracy Chart View&#41;](../../2014/analysis-services/lift-chart-tab-mining-accuracy-chart-view.md) </span></span>  
 <span data-ttu-id="a96f1-124">[Grafico di accuratezza &#40;Analysis Services-&#41;di data mining](../../2014/analysis-services/data-mining/lift-chart-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="a96f1-124">[Lift Chart &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/lift-chart-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="a96f1-125">[Test e convalida &#40;&#41;di data mining](../../2014/analysis-services/data-mining/testing-and-validation-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="a96f1-125">[Testing and Validation &#40;Data Mining&#41;](../../2014/analysis-services/data-mining/testing-and-validation-data-mining.md) </span></span>  
 <span data-ttu-id="a96f1-126">[Scheda matrice di classificazione &#40;vista Grafico accuratezza modello di data mining&#41;](../../2014/analysis-services/classification-matrix-tab-mining-accuracy-chart-view.md) </span><span class="sxs-lookup"><span data-stu-id="a96f1-126">[Classification Matrix Tab &#40;Mining Accuracy Chart View&#41;](../../2014/analysis-services/classification-matrix-tab-mining-accuracy-chart-view.md) </span></span>  
 [<span data-ttu-id="a96f1-127">Matrice di classificazione &#40;Analysis Services - Data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="a96f1-127">Classification Matrix &#40;Analysis Services - Data Mining&#41;</span></span>](../../2014/analysis-services/data-mining/classification-matrix-analysis-services-data-mining.md)  
  
  
