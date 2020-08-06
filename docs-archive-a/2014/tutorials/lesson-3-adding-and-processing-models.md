---
title: 'Lezione 3: aggiunta ed elaborazione di modelli | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: cc29927a-c368-4b8a-bbd0-af89a9f54dc9
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 5da034089d8bbe7f1a967258d195a56ddbf13c03
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624453"
---
# <a name="lesson-3-adding-and-processing-models"></a><span data-ttu-id="a9740-102">Lezione 3: Aggiunta ed elaborazione di modelli</span><span class="sxs-lookup"><span data-stu-id="a9740-102">Lesson 3: Adding and Processing Models</span></span>
  <span data-ttu-id="a9740-103">La struttura di data mining creata nella lezione precedente contiene un singolo modello di data mining basato sull'algoritmo [!INCLUDE[msCoName](../includes/msconame-md.md)] Decision Trees.</span><span class="sxs-lookup"><span data-stu-id="a9740-103">The mining structure that you created in the previous lesson contains a single mining model that is based on the [!INCLUDE[msCoName](../includes/msconame-md.md)] Decision Trees algorithm.</span></span> <span data-ttu-id="a9740-104">È possibile utilizzare questo modello per identificare i clienti per la campagna di mailing diretto.</span><span class="sxs-lookup"><span data-stu-id="a9740-104">You can use this model to identify customers for the targeted mailing campaign.</span></span> <span data-ttu-id="a9740-105">Tuttavia, per assicurarsi che l'analisi sia approfondita, è consigliabile creare modelli correlati utilizzando algoritmi diversi e confrontarne i risultati.</span><span class="sxs-lookup"><span data-stu-id="a9740-105">However, to ensure that your analysis is thorough, it is a common practice to create related models using different algorithms and compare their results.</span></span> <span data-ttu-id="a9740-106">In questo modo è possibile ottenere anche informazioni diverse.</span><span class="sxs-lookup"><span data-stu-id="a9740-106">That way you can get different insights as well.</span></span> <span data-ttu-id="a9740-107">Pertanto, verranno creati due modelli aggiuntivi, che verranno quindi elaborati e distribuiti.</span><span class="sxs-lookup"><span data-stu-id="a9740-107">Therefore, you will create two additional models, then process and deploy the models.</span></span>  
  
 <span data-ttu-id="a9740-108">In questa lezione verranno illustrate le procedure per la creazione di un set di modelli di data mining in grado di suggerire i clienti più probabili all'interno di un elenco di potenziali clienti.</span><span class="sxs-lookup"><span data-stu-id="a9740-108">In this lesson, you will create a set of mining models that will suggest the most likely customers from a list of potential customers.</span></span>  
  
 <span data-ttu-id="a9740-109">Per completare le attività in questa lezione, si utilizzeranno l' [algoritmo Microsoft Clustering](../../2014/analysis-services/data-mining/microsoft-clustering-algorithm.md) e l' [algoritmo Microsoft Naive Bayes](../../2014/analysis-services/data-mining/microsoft-naive-bayes-algorithm.md).</span><span class="sxs-lookup"><span data-stu-id="a9740-109">To complete the tasks in this lesson, you will use the [Microsoft Clustering Algorithm](../../2014/analysis-services/data-mining/microsoft-clustering-algorithm.md) and the [Microsoft Naive Bayes Algorithm](../../2014/analysis-services/data-mining/microsoft-naive-bayes-algorithm.md).</span></span>  
  
 <span data-ttu-id="a9740-110">In questa lezione sono incluse le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="a9740-110">This lesson contains the following tasks:</span></span>  
  
 [<span data-ttu-id="a9740-111">Aggiunta di nuovi modelli alla struttura Targeted Mailing &#40;esercitazione di base sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="a9740-111">Adding New Models to the Targeted Mailing Structure &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/adding-new-models-to-the-targeted-mailing-structure-basic-data-mining-tutorial.md)  
  
 [<span data-ttu-id="a9740-112">Elaborazione di modelli nella struttura di mailing diretto &#40;esercitazione di base sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="a9740-112">Processing Models in the Targeted Mailing Structure &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/processing-models-in-the-targeted-mailing-structure-basic-data-mining-tutorial.md)  
  
## <a name="first-task-in-lesson"></a><span data-ttu-id="a9740-113">Prima attività della lezione</span><span class="sxs-lookup"><span data-stu-id="a9740-113">First Task in Lesson</span></span>  
 [<span data-ttu-id="a9740-114">Aggiunta di nuovi modelli alla struttura Targeted Mailing &#40;esercitazione di base sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="a9740-114">Adding New Models to the Targeted Mailing Structure &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/adding-new-models-to-the-targeted-mailing-structure-basic-data-mining-tutorial.md)  
  
## <a name="previous-lesson"></a><span data-ttu-id="a9740-115">Lezione precedente</span><span class="sxs-lookup"><span data-stu-id="a9740-115">Previous Lesson</span></span>  
 [<span data-ttu-id="a9740-116">Lezione 2: creazione di una struttura di mailing diretto &#40;esercitazione di base sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="a9740-116">Lesson 2: Building a Targeted Mailing Structure &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-2-building-a-targeted-mailing-structure-basic-data-mining-tutorial.md)  
  
## <a name="next-lesson"></a><span data-ttu-id="a9740-117">Lezione successiva</span><span class="sxs-lookup"><span data-stu-id="a9740-117">Next Lesson</span></span>  
 [<span data-ttu-id="a9740-118">Lezione 4: esplorazione dei modelli di mailing diretto &#40;esercitazione di base sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="a9740-118">Lesson 4: Exploring the Targeted Mailing Models &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-4-exploring-the-targeted-mailing-models-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="a9740-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a9740-119">See Also</span></span>  
 [<span data-ttu-id="a9740-120">Aggiungere modelli di data mining a una struttura &#40;Analysis Services - Data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="a9740-120">Add Mining Models to a Structure &#40;Analysis Services - Data Mining&#41;</span></span>](../../2014/analysis-services/data-mining/add-mining-models-to-a-structure-analysis-services-data-mining.md)  
  
  
