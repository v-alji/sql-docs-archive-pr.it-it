---
title: Test di un modello filtrato (esercitazione di base sul data mining) | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: f0d74f8c-600d-4df5-a742-695e6947a071
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: a97b5ca3523d1fc73405baba52b179a9bef04767
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623634"
---
# <a name="testing-a-filtered-model-basic-data-mining-tutorial"></a><span data-ttu-id="31a52-102">Test di un modello filtrato (Esercitazione di base sul data mining)</span><span class="sxs-lookup"><span data-stu-id="31a52-102">Testing a Filtered Model (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="31a52-103">Ora che è stato stabilito che il `TM_Decision_Tree` modello è il più accurato, sarà possibile personalizzare il modello in base alle esigenze della [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] campagna di mailing diretto.</span><span class="sxs-lookup"><span data-stu-id="31a52-103">Now that you have determined that the `TM_Decision_Tree` model is the most accurate, you will customize the model to better suit the needs of the [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] targeted mailing campaign.</span></span> <span data-ttu-id="31a52-104">In particolare, il reparto marketing desidera sapere se esistono differenze tra i clienti di sesso maschile e femminile.</span><span class="sxs-lookup"><span data-stu-id="31a52-104">Specifically, the Marketing department would like to know if there are any differences between male and female customers.</span></span> <span data-ttu-id="31a52-105">Queste informazioni possono aiutarli a decidere quali riviste utilizzare per la pubblicità e quali prodotti includere nei mailing.</span><span class="sxs-lookup"><span data-stu-id="31a52-105">The information could help them decide which magazines to use for advertising and which products to feature in their mailings.</span></span>  
  
## <a name="using-filters"></a><span data-ttu-id="31a52-106">Utilizzo dei filtri</span><span class="sxs-lookup"><span data-stu-id="31a52-106">Using Filters</span></span>  
 <span data-ttu-id="31a52-107">I filtri consentono di creare facilmente modelli compilati in base a subset dei dati.</span><span class="sxs-lookup"><span data-stu-id="31a52-107">Filtering enables you to easily create models built on subsets of your data.</span></span> <span data-ttu-id="31a52-108">Il filtro viene applicato solo al modello e non modifica l'origine dati sottostante.</span><span class="sxs-lookup"><span data-stu-id="31a52-108">The filter is applied only to the model and does not change the underlying data source.</span></span>  
  
 <span data-ttu-id="31a52-109">In questa lezione verrà creato un modello filtrato in base al genere per determinare le caratteristiche che influiscono maggiormente sul comportamento di acquisto di persone di sesso maschile e femminile.</span><span class="sxs-lookup"><span data-stu-id="31a52-109">In this lesson, you will create a model that is filtered on gender, to predict the characteristics that most influence buying behavior in males and female.</span></span>  
  
 <span data-ttu-id="31a52-110">Prima di tutto si effettuerà una copia del `TM_Decision_Tree` modello.</span><span class="sxs-lookup"><span data-stu-id="31a52-110">First you will make a copy of the `TM_Decision_Tree` model.</span></span>  
  
#### <a name="to-copy-the-decision-tree-model"></a><span data-ttu-id="31a52-111">Per copiare il modello Decision Trees</span><span class="sxs-lookup"><span data-stu-id="31a52-111">To copy the Decision Tree Model</span></span>  
  
1.  <span data-ttu-id="31a52-112">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] Esplora soluzioni selezionare **BasicDataMining**.</span><span class="sxs-lookup"><span data-stu-id="31a52-112">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], in Solution Explorer, select **BasicDataMining**.</span></span>  
  
2.  <span data-ttu-id="31a52-113">Fare clic sulla scheda **Modelli di data mining** .</span><span class="sxs-lookup"><span data-stu-id="31a52-113">Click the **Mining Models** tab.</span></span>  
  
3.  <span data-ttu-id="31a52-114">Fare clic con il pulsante destro del mouse sul `TM_Decision_Tree` modello e scegliere **nuovo modello di data mining.**</span><span class="sxs-lookup"><span data-stu-id="31a52-114">Right click the `TM_Decision_Tree` model, and select **New Mining Model.**</span></span>  
  
4.  <span data-ttu-id="31a52-115">Nel campo **nome modello** Digitare `TM_Decision_Tree_Male` .</span><span class="sxs-lookup"><span data-stu-id="31a52-115">In the **Model name** field, type `TM_Decision_Tree_Male`.</span></span>  
  
5.  <span data-ttu-id="31a52-116">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="31a52-116">Click **OK**.</span></span>  
  
 <span data-ttu-id="31a52-117">Creare quindi un filtro per selezionare i clienti per il modello in base al sesso.</span><span class="sxs-lookup"><span data-stu-id="31a52-117">Next, create a filter to select customers for the model based on their gender.</span></span>  
  
#### <a name="to-create-a-case-filter-on-a-mining-model"></a><span data-ttu-id="31a52-118">Per creare un filtro di case su un modello di data mining</span><span class="sxs-lookup"><span data-stu-id="31a52-118">To create a case filter on a mining model</span></span>  
  
1.  <span data-ttu-id="31a52-119">`TM_Decision_Tree_Male`Per aprire il menu di scelta rapida, fare clic con il pulsante destro del mouse sul modello.</span><span class="sxs-lookup"><span data-stu-id="31a52-119">Right-click the `TM_Decision_Tree_Male` mining model to open the shortcut menu.</span></span>  
  
     <span data-ttu-id="31a52-120">-- o --</span><span class="sxs-lookup"><span data-stu-id="31a52-120">-- or --</span></span>  
  
     <span data-ttu-id="31a52-121">Selezionare il modello.</span><span class="sxs-lookup"><span data-stu-id="31a52-121">Select the model.</span></span> <span data-ttu-id="31a52-122">Scegliere **Imposta filtro modello** dal menu **Modello di data mining**.</span><span class="sxs-lookup"><span data-stu-id="31a52-122">On the **Mining Model** menu, select **Set Model Filter**.</span></span>  
  
2.  <span data-ttu-id="31a52-123">Nella finestra di dialogo **Filtro modello** fare clic sulla riga superiore nella griglia della casella di testo **Colonna struttura di data mining** .</span><span class="sxs-lookup"><span data-stu-id="31a52-123">In the **Model Filter** dialog box, click the top row in the grid, in the **Mining Structure Column** text box.</span></span>  
  
     <span data-ttu-id="31a52-124">Nell'elenco a discesa verranno visualizzati solo i nomi delle colonne della tabella.</span><span class="sxs-lookup"><span data-stu-id="31a52-124">The drop-down list displays only the names of the columns in that table.</span></span>  
  
3.  <span data-ttu-id="31a52-125">Nella casella di testo colonna struttura di data mining selezionare **Gender**.</span><span class="sxs-lookup"><span data-stu-id="31a52-125">In the Mining Structure Column text box, select **Gender**.</span></span>  
  
     <span data-ttu-id="31a52-126">L'icona a sinistra della casella di testo cambierà per indicare che l'elemento selezionato è una tabella o una colonna.</span><span class="sxs-lookup"><span data-stu-id="31a52-126">The icon at the left side of the text box changes to indicate that the selected item is a table or a column.</span></span>  
  
4.  <span data-ttu-id="31a52-127">Fare clic sulla casella di testo **operatore** e selezionare l'operatore di uguaglianza (=) nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="31a52-127">Click the **Operator** text box and select the equal (=) operator from the list.</span></span>  
  
5.  <span data-ttu-id="31a52-128">Fare clic sulla casella di testo **valore** e digitare **M**.</span><span class="sxs-lookup"><span data-stu-id="31a52-128">Click the **Value** text box, and type **M**.</span></span>  
  
6.  <span data-ttu-id="31a52-129">Fare clic sulla riga successiva nella griglia.</span><span class="sxs-lookup"><span data-stu-id="31a52-129">Click the next row in the grid.</span></span>  
  
7.  <span data-ttu-id="31a52-130">Fare clic su **OK** per chiudere la finestra di dialogo **filtro modello** .</span><span class="sxs-lookup"><span data-stu-id="31a52-130">Click **OK** to close the **Model Filter** dialog box.</span></span>  
  
     <span data-ttu-id="31a52-131">Il filtro viene visualizzato nella finestra **Proprietà** .</span><span class="sxs-lookup"><span data-stu-id="31a52-131">The filter displays in the **Properties** window.</span></span> <span data-ttu-id="31a52-132">In alternativa, è possibile avviare la finestra di dialogo **filtro modello** dalla finestra **Proprietà** .</span><span class="sxs-lookup"><span data-stu-id="31a52-132">Alternately, you can launch the **Model Filter** dialog from the **Properties** window.</span></span>  
  
8.  <span data-ttu-id="31a52-133">Ripetere i passaggi precedenti, ma questa volta denominare il modello `TM_Decision_Tree_Female` e digitare **F** nella casella di testo **valore** .</span><span class="sxs-lookup"><span data-stu-id="31a52-133">Repeat the above steps, but this time name the model `TM_Decision_Tree_Female` and type **F** in the **Value** text box.</span></span>  
  
## <a name="process-the-filtered-models"></a><span data-ttu-id="31a52-134">Elaborazione dei modelli filtrati</span><span class="sxs-lookup"><span data-stu-id="31a52-134">Process the Filtered Models</span></span>  
 <span data-ttu-id="31a52-135">Per utilizzare i modelli, è innanzitutto necessario distribuirli ed elaborarli.</span><span class="sxs-lookup"><span data-stu-id="31a52-135">Models cannot be used until they have been deployed and processed.</span></span> <span data-ttu-id="31a52-136">Per ulteriori informazioni sull'elaborazione dei modelli, vedere [elaborazione di modelli nella struttura Targeted mailing &#40;esercitazione di base sul Data Mining&#41;](../../2014/tutorials/processing-models-in-the-targeted-mailing-structure-basic-data-mining-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="31a52-136">For more information on processing models, see [Processing Models in the Targeted Mailing Structure &#40;Basic Data Mining Tutorial&#41;](../../2014/tutorials/processing-models-in-the-targeted-mailing-structure-basic-data-mining-tutorial.md).</span></span>  
  
#### <a name="to-process-the-filtered-model"></a><span data-ttu-id="31a52-137">Per elaborare i modello filtrati</span><span class="sxs-lookup"><span data-stu-id="31a52-137">To process the filtered model</span></span>  
  
1.  <span data-ttu-id="31a52-138">Fare clic con il pulsante destro del mouse sul `TM_Decision_Tree_Male` modello e scegliere **Elabora struttura di data mining e tutti i modelli**</span><span class="sxs-lookup"><span data-stu-id="31a52-138">Right-click the `TM_Decision_Tree_Male` model and select **Process Mining Structure and all Model**s</span></span>  
  
2.  <span data-ttu-id="31a52-139">Fare clic su **Esegui** per elaborare i nuovi modelli.</span><span class="sxs-lookup"><span data-stu-id="31a52-139">Click **Run** to process the new models.</span></span>  
  
3.  <span data-ttu-id="31a52-140">Al termine dell'elaborazione, fare clic su **Chiudi** in entrambe le finestre di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="31a52-140">After processing is complete, click **Close** on both processing windows.</span></span>  
  
     <span data-ttu-id="31a52-141">Sono ora disponibili due nuovi modelli nella scheda **modelli di data mining** .</span><span class="sxs-lookup"><span data-stu-id="31a52-141">You now have two new models displayed in the **Mining Models** tab.</span></span>  
  
## <a name="evaluate-the-results"></a><span data-ttu-id="31a52-142">Valutazione dei risultati</span><span class="sxs-lookup"><span data-stu-id="31a52-142">Evaluate the Results</span></span>  
 <span data-ttu-id="31a52-143">Visualizzare i risultati e stimare l'accuratezza dei modelli filtrati seguendo gli stessi passaggi effettuati per i tre modelli precedenti.</span><span class="sxs-lookup"><span data-stu-id="31a52-143">View the results and assess the accuracy of the filtered models in much the same way as you did for the previous three models.</span></span> <span data-ttu-id="31a52-144">Per altre informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="31a52-144">For more information, see:</span></span>  
  
 [<span data-ttu-id="31a52-145">Esplorazione del modello Decision Trees &#40;esercitazione di base sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="31a52-145">Exploring the Decision Tree Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-decision-tree-model-basic-data-mining-tutorial.md)  
  
 [<span data-ttu-id="31a52-146">Test dell'accuratezza con i grafici di accuratezza &#40;Esercitazione di base sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="31a52-146">Testing Accuracy with Lift Charts &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/testing-accuracy-with-lift-charts-basic-data-mining-tutorial.md)  
  
#### <a name="to-explore-the-filtered-models"></a><span data-ttu-id="31a52-147">Per esplorare i modelli filtrati</span><span class="sxs-lookup"><span data-stu-id="31a52-147">To explore the filtered models</span></span>  
  
1.  <span data-ttu-id="31a52-148">Selezionare la scheda **Visualizzatore modello di data mining** in Progettazione modelli di **data mining**.</span><span class="sxs-lookup"><span data-stu-id="31a52-148">Select the **Mining Model Viewer** tab in **Data Mining Designer**.</span></span>  
  
2.  <span data-ttu-id="31a52-149">Nella casella modello di data mining selezionare `TM_Decision_Tree_Male` .</span><span class="sxs-lookup"><span data-stu-id="31a52-149">In the Mining Model box, select `TM_Decision_Tree_Male`.</span></span>  
  
3.  <span data-ttu-id="31a52-150">Diapositiva **Mostra livello** a `3` .</span><span class="sxs-lookup"><span data-stu-id="31a52-150">Slide **Show Level** to `3`.</span></span>  
  
4.  <span data-ttu-id="31a52-151">Modificare il valore di **sfondo** in `1` .</span><span class="sxs-lookup"><span data-stu-id="31a52-151">Change the **Background** value to `1`.</span></span>  
  
5.  <span data-ttu-id="31a52-152">Posizionare il cursore sul nodo con l'etichetta **tutti** per visualizzare il numero di acquirenti di biciclette rispetto agli acquirenti non bike.</span><span class="sxs-lookup"><span data-stu-id="31a52-152">Place your cursor over the node labeled **All** to see the number of bike buyers versus non-bike buyers.</span></span>  
  
6.  <span data-ttu-id="31a52-153">Ripetere i passaggi 1-5 per `TM_Decision_Tree_Female` .</span><span class="sxs-lookup"><span data-stu-id="31a52-153">Repeat steps 1 - 5 for `TM_Decision_Tree_Female`.</span></span>  
  
7.  <span data-ttu-id="31a52-154">Esplorare i risultati per `TM_Decision_Tree` e i modelli filtrati per sesso.</span><span class="sxs-lookup"><span data-stu-id="31a52-154">Explore the results for the `TM_Decision_Tree` and the models filtered for gender.</span></span> <span data-ttu-id="31a52-155">Dal confronto fra tutti gli acquirenti di biciclette risulta che gli acquirenti di biciclette di sesso maschile e femminile condividono alcune caratteristiche con gli acquirenti di biciclette non filtrati, ma con alcune differenze interessanti.</span><span class="sxs-lookup"><span data-stu-id="31a52-155">Compared to all bike buyers, male and female bike buyers share some of the same characteristics as the unfiltered bike buyers but all three have interesting differences as well.</span></span> <span data-ttu-id="31a52-156">Si tratta di informazioni utili che [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] possono essere usate per sviluppare la campagna di marketing.</span><span class="sxs-lookup"><span data-stu-id="31a52-156">This is useful information that [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] can use to develop their marketing campaign.</span></span>  
  
#### <a name="to-test-the-lift-of-the-filtered-models"></a><span data-ttu-id="31a52-157">Per testare l'accuratezza dei modelli filtrati</span><span class="sxs-lookup"><span data-stu-id="31a52-157">To test the lift of the filtered models</span></span>  
  
1.  <span data-ttu-id="31a52-158">Passare alla scheda **Grafico accuratezza** modello di data mining in Progettazione modelli di data mining in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] e selezionare la scheda **Selezione input** .</span><span class="sxs-lookup"><span data-stu-id="31a52-158">Switch to the **Mining Accuracy Chart** tab in Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] and select the **Input Selection** tab.</span></span>  
  
2.  <span data-ttu-id="31a52-159">Nella casella **di gruppo Seleziona set di dati da utilizzare per il grafico di accuratezza** selezionare **utilizza test case della struttura di data mining**.</span><span class="sxs-lookup"><span data-stu-id="31a52-159">In the **Select data set to be used for Accuracy Chart** group box, select **Use mining structure test cases**.</span></span>  
  
3.  <span data-ttu-id="31a52-160">Nella scheda **Selezione input** di progettazione modelli di data mining, in **selezionare le colonne stimabili del modello di data mining da visualizzare nel grafico di accuratezza**, selezionare la casella di controllo **Sincronizza colonne e valori di stima**.</span><span class="sxs-lookup"><span data-stu-id="31a52-160">On the **Input Selection** tab of Data Mining Designer, under **Select predictable mining model columns to show in the lift chart**, select the checkbox for **Synchronize Prediction Columns and Values**.</span></span>  
  
4.  <span data-ttu-id="31a52-161">Nella colonna **nome colonna stimabile** verificare che **Bike Buyer** sia selezionato per ogni modello.</span><span class="sxs-lookup"><span data-stu-id="31a52-161">In the **Predictable Column Name** column, verify that **Bike Buyer** is selected for each model.</span></span>  
  
5.  <span data-ttu-id="31a52-162">Nella colonna **Mostra** selezionare ogni modello.</span><span class="sxs-lookup"><span data-stu-id="31a52-162">In the **Show** column, select each of the models.</span></span>  
  
6.  <span data-ttu-id="31a52-163">Nella colonna **stima valore** selezionare `1` .</span><span class="sxs-lookup"><span data-stu-id="31a52-163">In the **Predict Value** column, select `1`.</span></span>  
  
7.  <span data-ttu-id="31a52-164">Selezionare la scheda **grafico di accuratezza** per visualizzare il grafico di accuratezza.</span><span class="sxs-lookup"><span data-stu-id="31a52-164">Select the **Lift Chart** tab to display the lift chart.</span></span>  
  
     <span data-ttu-id="31a52-165">Si noterà ora che tutti e tre i modelli Decision Trees offrono un livello di accuratezza considerevole rispetto al modello di ipotesi casuale e prestazioni superiori rispetto ai modelli di clustering e Naive Bayes.</span><span class="sxs-lookup"><span data-stu-id="31a52-165">You will now notice that all three Decision Tree models provide significant lift compared to the random guess model, and also outperform the Clustering and Naive-Bayes models.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="31a52-166">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="31a52-166">Related Tasks</span></span>  
 <span data-ttu-id="31a52-167">Per ulteriori informazioni sui filtri, vedere [filtri per i modelli di data mining &#40;Analysis Services-&#41;di data mining ](../../2014/analysis-services/data-mining/filters-for-mining-models-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="31a52-167">For more information on filters, see [Filters for Mining Models &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/filters-for-mining-models-analysis-services-data-mining.md).</span></span>  
  
 <span data-ttu-id="31a52-168">Per un esempio di applicazione di filtri alle tabelle nidificate, vedere [esercitazione intermedia sul data mining &#40;Analysis Services-&#41;di data mining ](../../2014/tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="31a52-168">For an example of how to apply filters to nested tables, see [Intermediate Data Mining Tutorial &#40;Analysis Services - Data Mining&#41;](../../2014/tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md).</span></span>  
  
## <a name="previous-task-in-lesson"></a><span data-ttu-id="31a52-169">Attività precedente della lezione</span><span class="sxs-lookup"><span data-stu-id="31a52-169">Previous Task in Lesson</span></span>  
 [<span data-ttu-id="31a52-170">Test dell'accuratezza con i grafici di accuratezza &#40;Esercitazione di base sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="31a52-170">Testing Accuracy with Lift Charts &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/testing-accuracy-with-lift-charts-basic-data-mining-tutorial.md)  
  
## <a name="next-lesson"></a><span data-ttu-id="31a52-171">Lezione successiva</span><span class="sxs-lookup"><span data-stu-id="31a52-171">Next Lesson</span></span>  
 [<span data-ttu-id="31a52-172">Lezione 6: Creazione e utilizzo di stime &#40;Esercitazione di base sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="31a52-172">Lesson 6: Creating and Working with Predictions &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-6-creating-and-working-with-predictions-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="31a52-173">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="31a52-173">See Also</span></span>  
 <span data-ttu-id="31a52-174">[Esercitazione intermedia sul data mining &#40;Analysis Services-&#41;di data mining](../../2014/tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="31a52-174">[Intermediate Data Mining Tutorial &#40;Analysis Services - Data Mining&#41;](../../2014/tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="31a52-175">[Attività e procedure relative al modello di data mining](../../2014/analysis-services/data-mining/mining-model-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="31a52-175">[Mining Model Tasks and How-tos](../../2014/analysis-services/data-mining/mining-model-tasks-and-how-tos.md) </span></span>  
 <span data-ttu-id="31a52-176">[Eliminare un filtro da un modello di data mining](../../2014/analysis-services/data-mining/delete-a-filter-from-a-mining-model.md) </span><span class="sxs-lookup"><span data-stu-id="31a52-176">[Delete a Filter from a Mining Model](../../2014/analysis-services/data-mining/delete-a-filter-from-a-mining-model.md) </span></span>  
 [<span data-ttu-id="31a52-177">Filtri per i modelli di data mining &#40;Analysis Services - Data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="31a52-177">Filters for Mining Models &#40;Analysis Services - Data Mining&#41;</span></span>](../../2014/analysis-services/data-mining/filters-for-mining-models-analysis-services-data-mining.md)  
  
  
