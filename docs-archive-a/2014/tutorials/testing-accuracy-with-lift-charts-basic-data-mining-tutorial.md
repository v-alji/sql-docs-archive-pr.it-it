---
title: Verifica dell'accuratezza con i grafici di accuratezza (esercitazione di base sul data mining) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 822d414b-4a39-473f-80c3-53476e30655a
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 7a3dcdd1d1b78911f5ffd37a383532abdd4814c3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718990"
---
# <a name="testing-accuracy-with-lift-charts-basic-data-mining-tutorial"></a><span data-ttu-id="4570c-102">Test dell'accuratezza con i grafici di accuratezza (Esercitazione di base sul data mining)</span><span class="sxs-lookup"><span data-stu-id="4570c-102">Testing Accuracy with Lift Charts (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="4570c-103">Nella scheda **Grafico accuratezza** modello di data mining di progettazione modelli di data mining è possibile calcolare il modo in cui ognuno dei modelli esegue stime e confrontare i risultati di ogni modello direttamente con i risultati degli altri modelli.</span><span class="sxs-lookup"><span data-stu-id="4570c-103">On the **Mining Accuracy Chart** tab of Data Mining Designer, you can calculate how well each of your models makes predictions, and compare the results of each model directly against the results of the other models.</span></span> <span data-ttu-id="4570c-104">Questo metodo di confronto viene definito *grafico di accuratezza*.</span><span class="sxs-lookup"><span data-stu-id="4570c-104">This method of comparison is referred to as a *lift chart*.</span></span> <span data-ttu-id="4570c-105">In genere, l'accuratezza predittiva di un modello di data mining è misurata dall'accuratezza stessa del modello o dall'accuratezza della classificazione.</span><span class="sxs-lookup"><span data-stu-id="4570c-105">Typically, the predictive accuracy of a mining model is measured by either lift or classification accuracy.</span></span> <span data-ttu-id="4570c-106">Per questa esercitazione si utilizzerà solo il grafico di accuratezza.</span><span class="sxs-lookup"><span data-stu-id="4570c-106">For this tutorial we will use the lift chart only.</span></span>  
  
 <span data-ttu-id="4570c-107">In questo argomento verranno eseguite le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="4570c-107">In this topic, you will perform the following tasks:</span></span>  
  
-   [<span data-ttu-id="4570c-108">Scegliere i dati di input</span><span class="sxs-lookup"><span data-stu-id="4570c-108">Choose the Input Data</span></span>](#BKMK_InputData)  
  
-   [<span data-ttu-id="4570c-109">Configurare i parametri del grafico di accuratezza</span><span class="sxs-lookup"><span data-stu-id="4570c-109">Configure Accuracy Chart Parameters</span></span>](#BKMK_Selecting)  
  
##  <a name="choosing-the-input-data"></a><a name="BKMK_InputData"></a><span data-ttu-id="4570c-110">Scelta dei dati di input</span><span class="sxs-lookup"><span data-stu-id="4570c-110">Choosing the Input Data</span></span>  
 <span data-ttu-id="4570c-111">Il primo passaggio per verificare l'accuratezza dei modelli di data mining consiste nel selezionare l'origine dati che verrà utilizzata per il testing.</span><span class="sxs-lookup"><span data-stu-id="4570c-111">The first step in testing the accuracy of your mining models is to select the data source that you will use for testing.</span></span> <span data-ttu-id="4570c-112">Si testerà l'accuratezza dei modelli rispetto ai dati di testing, quindi li si utilizzerà con dati esterni.</span><span class="sxs-lookup"><span data-stu-id="4570c-112">You will test how well the models perform against your testing data and then you will use them with external data.</span></span>  
  
#### <a name="to-select-the-data-set"></a><span data-ttu-id="4570c-113">Per selezionare il set di dati</span><span class="sxs-lookup"><span data-stu-id="4570c-113">To select the data set</span></span>  
  
1.  <span data-ttu-id="4570c-114">Passare alla scheda **Grafico accuratezza** modello di data mining in Progettazione modelli di data mining in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] e selezionare la scheda **Selezione input** .</span><span class="sxs-lookup"><span data-stu-id="4570c-114">Switch to the **Mining Accuracy Chart** tab in Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] and select the **Input Selection** tab.</span></span>  
  
2.  <span data-ttu-id="4570c-115">Nella casella **di gruppo Seleziona set di dati da utilizzare per il grafico di accuratezza** selezionare **utilizza test case della struttura di data mining**.</span><span class="sxs-lookup"><span data-stu-id="4570c-115">In the **Select data set to be used for Accuracy Chart** group box, select **Use mining structure test cases**.</span></span> <span data-ttu-id="4570c-116">Si tratta dei dati di testing che sono stati riservati al momento della creazione della struttura di data mining.</span><span class="sxs-lookup"><span data-stu-id="4570c-116">This is the testing data that you set aside when you created the mining structure.</span></span>  
  
     <span data-ttu-id="4570c-117">Per ulteriori informazioni sulle altre opzioni, vedere [scegliere un tipo di grafico di accuratezza e impostare le opzioni del grafico](../../2014/analysis-services/data-mining/choose-an-accuracy-chart-type-and-set-chart-options.md).</span><span class="sxs-lookup"><span data-stu-id="4570c-117">For more information on the other options, see [Choose an Accuracy Chart Type and Set Chart Options](../../2014/analysis-services/data-mining/choose-an-accuracy-chart-type-and-set-chart-options.md).</span></span>  
  
##  <a name="setting-accuracy-chart-parameters"></a><a name="BKMK_Selecting"></a><span data-ttu-id="4570c-118">Impostazione dei parametri del grafico di accuratezza</span><span class="sxs-lookup"><span data-stu-id="4570c-118">Setting Accuracy Chart Parameters</span></span>  
 <span data-ttu-id="4570c-119">Per creare un grafico di accuratezza, è necessario definire tre elementi:</span><span class="sxs-lookup"><span data-stu-id="4570c-119">To create an accuracy chart, you must define three things:</span></span>  
  
-   <span data-ttu-id="4570c-120">I modelli da includere nel grafico di accuratezza</span><span class="sxs-lookup"><span data-stu-id="4570c-120">Which models should you include in the accuracy chart?</span></span>  
  
-   <span data-ttu-id="4570c-121">L'attributo stimabile da misurare</span><span class="sxs-lookup"><span data-stu-id="4570c-121">Which predictable attribute do you want to measure?</span></span> <span data-ttu-id="4570c-122">In alcuni modelli potrebbero essere presenti più destinazioni, ma ogni grafico può misurare un solo risultato alla volta.</span><span class="sxs-lookup"><span data-stu-id="4570c-122">Some models might have multiple targets, but each chart can measure only one outcome at a time.</span></span>  
  
     <span data-ttu-id="4570c-123">Per utilizzare una colonna come **nome di colonna stimabile** in un grafico di accuratezza, è necessario che il tipo di utilizzo delle colonne sia `Predict` o `Predict Only` .</span><span class="sxs-lookup"><span data-stu-id="4570c-123">To use a column as the **Predictable Column Name** in an accuracy chart, the columns must have the usage type of `Predict` or `Predict Only`.</span></span> <span data-ttu-id="4570c-124">Inoltre, il tipo di contenuto della colonna di destinazione deve essere `Discrete` o `Discretized`.</span><span class="sxs-lookup"><span data-stu-id="4570c-124">Also, the content type of the target column must be either `Discrete` or `Discretized`.</span></span> <span data-ttu-id="4570c-125">In altre parole, non è possibile utilizzare grafici di accuratezza per misurare l'accuratezza su risultati numerici continui.</span><span class="sxs-lookup"><span data-stu-id="4570c-125">In other words, you cannot measure accuracy against continuous numeric outputs using the lift chart.</span></span>  
  
-   <span data-ttu-id="4570c-126">Si desidera misurare l'accuratezza generale del modello o la relativa accuratezza nella stima di un particolare valore (ad esempio [Bike Buyer] =' Sì')</span><span class="sxs-lookup"><span data-stu-id="4570c-126">Do you want to measure the model's general accuracy, or its accuracy  in predicting a particular value (such as [Bike Buyer] = 'Yes')</span></span>  
  
#### <a name="to-generate-the-lift-chart"></a><span data-ttu-id="4570c-127">Per generare il grafico di accuratezza</span><span class="sxs-lookup"><span data-stu-id="4570c-127">To generate the lift chart</span></span>  
  
1.  <span data-ttu-id="4570c-128">Nella scheda **Selezione input** di progettazione modelli di data mining, in **selezionare le colonne stimabili del modello di data mining da visualizzare nel grafico di accuratezza**, selezionare la casella di controllo **Sincronizza colonne e valori di stima**.</span><span class="sxs-lookup"><span data-stu-id="4570c-128">On the **Input Selection** tab of Data Mining Designer, under **Select predictable mining model columns to show in the lift chart**, select the checkbox for **Synchronize Prediction Columns and Values**.</span></span>  
  
2.  <span data-ttu-id="4570c-129">Nella colonna **nome colonna stimabile** verificare che **Bike Buyer** sia selezionato per ogni modello.</span><span class="sxs-lookup"><span data-stu-id="4570c-129">In the **Predictable Column Name** column, verify that **Bike Buyer** is selected for each model.</span></span>  
  
3.  <span data-ttu-id="4570c-130">Nella colonna **Mostra** selezionare ogni modello.</span><span class="sxs-lookup"><span data-stu-id="4570c-130">In the **Show** column, select each of the models.</span></span>  
  
     <span data-ttu-id="4570c-131">Per impostazione predefinita, nella struttura di data mining sono selezionati tutti i modelli.</span><span class="sxs-lookup"><span data-stu-id="4570c-131">By default, all the models in the mining structure are selected.</span></span> <span data-ttu-id="4570c-132">È possibile decidere di non includere un modello. Tuttavia in questa esercitazione verranno lasciati selezionati tutti i modelli.</span><span class="sxs-lookup"><span data-stu-id="4570c-132">You can decide not to include a model, but for this tutorial leave all the models selected.</span></span>  
  
4.  <span data-ttu-id="4570c-133">Nella colonna **valore stima** selezionare **1**.</span><span class="sxs-lookup"><span data-stu-id="4570c-133">In the **Predict Value** column, select **1**.</span></span> <span data-ttu-id="4570c-134">Lo stesso valore viene inserito automaticamente per ciascun modello che ha la stessa colonna stimabile.</span><span class="sxs-lookup"><span data-stu-id="4570c-134">The same value is automatically filled in for each model that has the same predictable column.</span></span>  
  
5.  <span data-ttu-id="4570c-135">Selezionare la scheda **grafico di accuratezza** .</span><span class="sxs-lookup"><span data-stu-id="4570c-135">Select the **Lift Chart** tab.</span></span>  
  
     <span data-ttu-id="4570c-136">Quando si fa clic sulla scheda, viene eseguita una query di stima per ottenere le stime per i dati di test e i risultati vengono confrontati con valori noti.</span><span class="sxs-lookup"><span data-stu-id="4570c-136">When you click the tab, a prediction query is executed to get predictions for the test data, and the results are compared against the known values.</span></span> <span data-ttu-id="4570c-137">I risultati vengono tracciati sul grafico.</span><span class="sxs-lookup"><span data-stu-id="4570c-137">The results are plotted on the graph.</span></span>  
  
     <span data-ttu-id="4570c-138">Se è stato specificato un determinato risultato di destinazione utilizzando l'opzione **stima valore** , il grafico di accuratezza traccia i risultati delle ipotesi casuali e i risultati di un modello ideale.</span><span class="sxs-lookup"><span data-stu-id="4570c-138">If you specified a particular target outcome using the **Predict Value** option, the lift chart plots the results of random guesses and the results of an ideal model.</span></span>  
  
    -   <span data-ttu-id="4570c-139">La riga relativa alle ipotesi casuali mostra l'accuratezza presentata dal modello senza l'utilizzo di dati informativi per il calcolo delle stime, ovvero una divisione 50-50 tra due risultati.</span><span class="sxs-lookup"><span data-stu-id="4570c-139">The random guess line shows how accurate the model would be without using any data to inform its predictions: that is, a 50-50 split between two outcomes.</span></span> <span data-ttu-id="4570c-140">Il grafico di accuratezza consente di visualizzare le migliori prestazioni registrate dal modello rispetto a un'ipotesi casuale.</span><span class="sxs-lookup"><span data-stu-id="4570c-140">The lift chart helps you visualize how much better your model performs in comparison to a random guess.</span></span>  
  
    -   <span data-ttu-id="4570c-141">La linea del modello ideale rappresenta il limite superiore di accuratezza.</span><span class="sxs-lookup"><span data-stu-id="4570c-141">The ideal model line represents the upper bound of accuracy.</span></span> <span data-ttu-id="4570c-142">Mostra il massimo vantaggio che è possibile ottenere se le stime del modello fossero sempre accurate.</span><span class="sxs-lookup"><span data-stu-id="4570c-142">It shows you the maximum possible benefit you could achieve if your model always predicted accurately.</span></span>  
  
     <span data-ttu-id="4570c-143">I modelli di data mining creati ricadranno in genere tra questi due estremi.</span><span class="sxs-lookup"><span data-stu-id="4570c-143">The mining models you created will usually fall between these two extremes.</span></span> <span data-ttu-id="4570c-144">Qualsiasi miglioramento dall'ipotesi casuale viene considerato *Lift*.</span><span class="sxs-lookup"><span data-stu-id="4570c-144">Any improvement from the random guess is considered to be *lift*.</span></span>  
  
6.  <span data-ttu-id="4570c-145">Utilizzare la legenda per individuare le linee colorate che rappresentano il modello ideale e il modello di ipotesi casuale.</span><span class="sxs-lookup"><span data-stu-id="4570c-145">Use the legend to locate the colored lines representing the Ideal Model and the Random Guess Model.</span></span>  
  
     <span data-ttu-id="4570c-146">Si noterà che il `TM_Decision_Tree` modello fornisce il massimo livello di accuratezza, superando i modelli di clustering e Naive Bayes.</span><span class="sxs-lookup"><span data-stu-id="4570c-146">You'll notice that the `TM_Decision_Tree` model provides the greatest lift,  outperforming both the Clustering and Naive Bayes models.</span></span>  
  
 <span data-ttu-id="4570c-147">Per una spiegazione approfondita di un grafico di accuratezza simile a quello creato in questa lezione, vedere [grafico di accuratezza &#40;Analysis Services-&#41;di data mining ](../../2014/analysis-services/data-mining/lift-chart-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="4570c-147">For an in-depth explanation of a lift chart similar to the one created in this lesson, see [Lift Chart &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/lift-chart-analysis-services-data-mining.md).</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="4570c-148">Attività successiva della lezione</span><span class="sxs-lookup"><span data-stu-id="4570c-148">Next Task in Lesson</span></span>  
 [<span data-ttu-id="4570c-149">Test di un modello filtrato &#40;esercitazione di base sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="4570c-149">Testing a Filtered Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/testing-a-filtered-model-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="4570c-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4570c-150">See Also</span></span>  
 <span data-ttu-id="4570c-151">[Grafico di accuratezza &#40;Analysis Services-&#41;di data mining](../../2014/analysis-services/data-mining/lift-chart-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="4570c-151">[Lift Chart &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/lift-chart-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="4570c-152">Scheda grafico di accuratezza &#40;vista Grafico accuratezza modello di data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="4570c-152">Lift Chart Tab &#40;Mining Accuracy Chart View&#41;</span></span>](../../2014/analysis-services/lift-chart-tab-mining-accuracy-chart-view.md)  
  
  
