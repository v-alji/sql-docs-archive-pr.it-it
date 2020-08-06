---
title: Aggiunta di nuovi modelli alla struttura Targeted Mailing (esercitazione di base sul data mining) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 512c6888-60f1-46e4-9639-bc448395b8d7
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: b83dfc6c9e218eecf3f2abe636b8c24d69d1b507
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720543"
---
# <a name="adding-new-models-to-the-targeted-mailing-structure-basic-data-mining-tutorial"></a><span data-ttu-id="44350-102">Aggiunta di nuovi modelli alla struttura Targeted Mailing (Esercitazione di base sul data mining)</span><span class="sxs-lookup"><span data-stu-id="44350-102">Adding New Models to the Targeted Mailing Structure (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="44350-103">In questa attività verranno definiti due modelli aggiuntivi utilizzando la scheda modelli di data mining di progettazione **modelli** di data mining.</span><span class="sxs-lookup"><span data-stu-id="44350-103">In this task, you will define two additional models by using the **Mining Models** tab of Data Mining Designer.</span></span> <span data-ttu-id="44350-104">Per creare i modelli, verranno utilizzati gli algoritmi Microsoft Clustering e Microsoft Naive Bayes,</span><span class="sxs-lookup"><span data-stu-id="44350-104">You will use the Microsoft Clustering and Microsoft Naive Bayes algorithms to create the models.</span></span> <span data-ttu-id="44350-105">per la loro capacità di stimare un valore discreto (ad esempio, l'acquisto di una bicicletta).</span><span class="sxs-lookup"><span data-stu-id="44350-105">These two algorithms are selected because of their ability to predict a discrete value (i.e., bike purchase).</span></span> <span data-ttu-id="44350-106">Per ulteriori informazioni su questi algoritmi, vedere [algoritmo Microsoft Clustering](../../2014/analysis-services/data-mining/microsoft-clustering-algorithm.md) e [algoritmo Microsoft Naive Bayes](../../2014/analysis-services/data-mining/microsoft-naive-bayes-algorithm.md)</span><span class="sxs-lookup"><span data-stu-id="44350-106">For more information about these algorithms, see [Microsoft Clustering Algorithm](../../2014/analysis-services/data-mining/microsoft-clustering-algorithm.md) and [Microsoft Naive Bayes Algorithm](../../2014/analysis-services/data-mining/microsoft-naive-bayes-algorithm.md)</span></span>  
  
### <a name="to-create-a-clustering-mining-model"></a><span data-ttu-id="44350-107">Per creare un modello di data mining Clustering</span><span class="sxs-lookup"><span data-stu-id="44350-107">To create a clustering mining model</span></span>  
  
1.  <span data-ttu-id="44350-108">Passare alla scheda **modelli** di data mining in Progettazione modelli di data mining in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="44350-108">Switch to the **Mining Models** tab in Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
     <span data-ttu-id="44350-109">Si noti che nella finestra di progettazione vengono visualizzate due colonne, una per la struttura di data mining e una per il `TM_Decision_Tree` modello di data mining creato nella lezione precedente.</span><span class="sxs-lookup"><span data-stu-id="44350-109">Notice that the designer displays two columns, one for the mining structure and one for the `TM_Decision_Tree` mining model, which you created in the previous lesson.</span></span>  
  
2.  <span data-ttu-id="44350-110">Fare clic con il pulsante destro del mouse sulla colonna **struttura** e scegliere **nuovo modello di data mining**.</span><span class="sxs-lookup"><span data-stu-id="44350-110">Right-click the **Structure** column and select **New Mining Model**.</span></span>  
  
3.  <span data-ttu-id="44350-111">Nella finestra di dialogo **nuovo modello di data mining** , in **nome modello**, digitare `TM_Clustering` .</span><span class="sxs-lookup"><span data-stu-id="44350-111">In the **New Mining Model** dialog box, in **Model name**, type `TM_Clustering`.</span></span>  
  
4.  <span data-ttu-id="44350-112">In **Nome algoritmo**selezionare **clustering Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="44350-112">In **Algorithm name**, select **Microsoft Clustering**.</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
 <span data-ttu-id="44350-113">Il nuovo modello verrà ora visualizzato nella scheda modelli di data mining di progettazione **modelli** di data mining.</span><span class="sxs-lookup"><span data-stu-id="44350-113">The new model now appears in the **Mining Models** tab of Data Mining Designer.</span></span> <span data-ttu-id="44350-114">Questo modello, creato con l' [!INCLUDE[msCoName](../includes/msconame-md.md)] algoritmo Clustering, raggruppa i clienti con caratteristiche simili in cluster e prevede l'acquisto di biciclette per ogni cluster.</span><span class="sxs-lookup"><span data-stu-id="44350-114">This model, built with the [!INCLUDE[msCoName](../includes/msconame-md.md)] Clustering algorithm, groups customers with similar characteristics into clusters and predicts bike buying for each cluster.</span></span> <span data-ttu-id="44350-115">Sebbene sia possibile modificare l'utilizzo e le proprietà delle colonne per il nuovo modello, `TM_Clustering` per questa esercitazione non sono necessarie modifiche al modello.</span><span class="sxs-lookup"><span data-stu-id="44350-115">Although you can modify the column usage and properties for the new model, no changes to the `TM_Clustering` model are necessary for this tutorial.</span></span>  
  
### <a name="to-create-a-naive-bayes-mining-model"></a><span data-ttu-id="44350-116">Per creare un modello di data mining Naive Bayes</span><span class="sxs-lookup"><span data-stu-id="44350-116">To create a Naive Bayes mining model</span></span>  
  
1.  <span data-ttu-id="44350-117">Nella scheda **modelli** di data mining di progettazione modelli di data mining, colonna **struttura** clickthe e selezionare **nuovo modello di data mining**.</span><span class="sxs-lookup"><span data-stu-id="44350-117">In the **Mining Models** tab of Data Mining Designer, right-clickthe **Structure** column, and select **New Mining Model**.</span></span>  
  
2.  <span data-ttu-id="44350-118">Nella finestra di dialogo **nuovo modello di data mining** , in **nome modello**, digitare `TM_NaiveBayes` .</span><span class="sxs-lookup"><span data-stu-id="44350-118">In the **New Mining Model** dialog box, under **Model name**, type `TM_NaiveBayes`.</span></span>  
  
3.  <span data-ttu-id="44350-119">In **Nome algoritmo**selezionare **Microsoft Naive Bayes**, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="44350-119">In **Algorithm name**, select **Microsoft Naive Bayes**, then click **OK**.</span></span>  
  
     <span data-ttu-id="44350-120">Viene visualizzato un messaggio che informa che l' [!INCLUDE[msCoName](../includes/msconame-md.md)] algoritmo Naive Bayes non supporta le colonne **Age** e **Yearly Income** , che sono continue.</span><span class="sxs-lookup"><span data-stu-id="44350-120">A message appears stating that the [!INCLUDE[msCoName](../includes/msconame-md.md)] Naive Bayes algorithm does not support the **Age** and **Yearly Income** columns, which are continuous.</span></span>  
  
4.  <span data-ttu-id="44350-121">Fare clic su **Sì** per confermare il messaggio e continuare.</span><span class="sxs-lookup"><span data-stu-id="44350-121">Click **Yes** to acknowledge the message and continue.</span></span>  
  
 <span data-ttu-id="44350-122">Un nuovo modello verrà visualizzato nella scheda modelli di data mining di progettazione **modelli** di data mining.</span><span class="sxs-lookup"><span data-stu-id="44350-122">A new model appears in the **Mining Models** tab of Data Mining Designer.</span></span> <span data-ttu-id="44350-123">Sebbene sia possibile modificare l'utilizzo e le proprietà delle colonne per tutti i modelli in questa scheda, `TM_NaiveBayes` per questa esercitazione non sono necessarie modifiche al modello.</span><span class="sxs-lookup"><span data-stu-id="44350-123">Although you can modify the column usage and properties for all the models in this tab, no changes to the `TM_NaiveBayes` model are necessary for this tutorial.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="44350-124">Attività successiva della lezione</span><span class="sxs-lookup"><span data-stu-id="44350-124">Next Task in Lesson</span></span>  
 [<span data-ttu-id="44350-125">Elaborazione di modelli nella struttura di mailing diretto &#40;esercitazione di base sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="44350-125">Processing Models in the Targeted Mailing Structure &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/processing-models-in-the-targeted-mailing-structure-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="44350-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="44350-126">See Also</span></span>  
 <span data-ttu-id="44350-127">[Aggiunta di modelli di data mining a una struttura &#40;Analysis Services-Data mining&#41;](../../2014/analysis-services/data-mining/add-mining-models-to-a-structure-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="44350-127">[Add Mining Models to a Structure &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/add-mining-models-to-a-structure-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="44350-128">[Progettazione modelli di data mining](../../2014/analysis-services/data-mining/data-mining-designer.md) </span><span class="sxs-lookup"><span data-stu-id="44350-128">[Data Mining Designer](../../2014/analysis-services/data-mining/data-mining-designer.md) </span></span>  
 [<span data-ttu-id="44350-129">Spostamento di oggetti di data mining</span><span class="sxs-lookup"><span data-stu-id="44350-129">Moving Data Mining Objects</span></span>](../../2014/analysis-services/data-mining/moving-data-mining-objects.md)  
  
  
