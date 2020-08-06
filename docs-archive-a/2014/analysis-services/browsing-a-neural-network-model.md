---
title: Esplorazione di un modello di rete neurale | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining models, browsing
- mining models, viewing
- mining model, neural network
- neural networks
- dependency network
ms.assetid: e4224cb7-115b-4889-ac07-03f096fb55fc
author: minewiskan
ms.author: owend
ms.openlocfilehash: ab2673d5b1881f74c2bc146b084d2efc7b06d69b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625811"
---
# <a name="browsing-a-neural-network-model"></a><span data-ttu-id="06f82-102">Esplorazione di un modello di rete neurale</span><span class="sxs-lookup"><span data-stu-id="06f82-102">Browsing a Neural Network Model</span></span>
  <span data-ttu-id="06f82-103">Quando si apre un modello di regressione logistica o di rete neurale utilizzando **Sfoglia**, il modello viene visualizzato in un visualizzatore interattivo, simile al visualizzatore del modello di rete neurale in [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="06f82-103">When you open a neural network or logistic regression model using **Browse**, the model is displayed in an interactive viewer, similar to the neural network model viewer in [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="06f82-104">Il visualizzatore consente di esplorare le correlazioni e ottenere informazioni sugli schemi del modello e sui dati sottostanti.</span><span class="sxs-lookup"><span data-stu-id="06f82-104">The viewer helps you explore correlations, and get information about the patterns in the model and the underlying data.</span></span>

##  <a name="explore-the-model"></a><a name="BKMK_Tabs"></a><span data-ttu-id="06f82-105">Esplorare il modello</span><span class="sxs-lookup"><span data-stu-id="06f82-105">Explore the Model</span></span>
 <span data-ttu-id="06f82-106">I modelli basati sugli algoritmi di [!INCLUDE[msCoName](../includes/msconame-md.md)] Neural Network o Logistic Regression sono simili nel senso che analizzano i dati come set di connessioni tra gli input e gli output noti.</span><span class="sxs-lookup"><span data-stu-id="06f82-106">Models that are based on [!INCLUDE[msCoName](../includes/msconame-md.md)] Neural Network or Logistic Regression algorithms are similar in that they analyze data as a set of connections among known inputs and outputs.</span></span> <span data-ttu-id="06f82-107">Il visualizzatore **Sfoglia** consente di esplorare tali connessioni tramite i controlli seguenti:</span><span class="sxs-lookup"><span data-stu-id="06f82-107">The **Browse** viewer helps you to explore those connections, using the following controls:</span></span>

-   [<span data-ttu-id="06f82-108">Variabili</span><span class="sxs-lookup"><span data-stu-id="06f82-108">Variables</span></span>](#BKMK_Variables)

-   [<span data-ttu-id="06f82-109">Input</span><span class="sxs-lookup"><span data-stu-id="06f82-109">Inputs</span></span>](#BKMK_Inputs)

-   [<span data-ttu-id="06f82-110">Output</span><span class="sxs-lookup"><span data-stu-id="06f82-110">Outputs</span></span>](#BKMK_Outputs)

 <span data-ttu-id="06f82-111">Per provare questo visualizzatore, è possibile creare un modello tramite [Procedura guidata Classificazione &#40;componenti aggiuntivi Data Mining per Excel&#41;](classify-wizard-data-mining-add-ins-for-excel.md) e usare l'opzione **Avanzate** per modificare l'algoritmo in Microsoft Logistic Regression nella finestra di dialogo **Parametri algoritmo**.</span><span class="sxs-lookup"><span data-stu-id="06f82-111">If you want to experiment with this viewer, you can create a model using the [Classify Wizard &#40;Data Mining Add-ins for Excel&#41;](classify-wizard-data-mining-add-ins-for-excel.md) wizard, and use the **Advanced** option to change the algorithm to Microsoft Logistic Regression in the **Algorithm Parameters** dialog box.</span></span>

###  <a name="variables"></a><a name="BKMK_Variables"></a><span data-ttu-id="06f82-112">Variabili</span><span class="sxs-lookup"><span data-stu-id="06f82-112">Variables</span></span>
 <span data-ttu-id="06f82-113">Nel riquadro **Variabili** viene visualizzato un elenco di variabili di input nell'ordine del relativo effetto sul modello.</span><span class="sxs-lookup"><span data-stu-id="06f82-113">The **Variables** pane displays a list of input variables in order of their effect on the model.</span></span> <span data-ttu-id="06f82-114">Usare i controlli **Output** e **Input** per filtrare il modello, influendo sulle variabili visualizzate e sul relativo ordine.</span><span class="sxs-lookup"><span data-stu-id="06f82-114">You use the **Input** and **Output** controls to filter the model, affecting the variables that are displayed, as well as their order.</span></span>

 <span data-ttu-id="06f82-115">Utilizzando questo visualizzatore, è possibile esplorare i fattori che sono più importanti per determinare se è più probabile che un cliente appartenga alla categoria di acquirenti di biciclette o alla categoria di non acquirenti.</span><span class="sxs-lookup"><span data-stu-id="06f82-115">Using this viewer, you can explore the factors that are most important in determining whether a customer more likely belongs to the bike buyer category or the non-buyer category.</span></span>

 <span data-ttu-id="06f82-116">![Effetto dei test sui risultati degli attributi selezionati](media/dm13-neuralnet-agebuyer1.gif "Effetto dei test sui risultati degli attributi selezionati")</span><span class="sxs-lookup"><span data-stu-id="06f82-116">![Testing effect on outcome of selected attributes](media/dm13-neuralnet-agebuyer1.gif "Testing effect on outcome of selected attributes")</span></span>

##### <a name="explore-variables"></a><span data-ttu-id="06f82-117">Esplorazione delle variabili</span><span class="sxs-lookup"><span data-stu-id="06f82-117">Explore variables</span></span>

1.  <span data-ttu-id="06f82-118">Inizialmente, il riquadro **Variabili** viene ordinato in base agli attributi più importanti, dati i filtri correnti.</span><span class="sxs-lookup"><span data-stu-id="06f82-118">Initially, the **Variables** pane is sorted in order of the most important attributes, given the current filters.</span></span> <span data-ttu-id="06f82-119">La lunghezza della barra indica l'attendibilità del fattore.</span><span class="sxs-lookup"><span data-stu-id="06f82-119">The length of the bar indicates the strength of the factor.</span></span>

     <span data-ttu-id="06f82-120">Nell'esempio, è possibile osservare che il reddito è il fattore più influente, seguito dall'area.</span><span class="sxs-lookup"><span data-stu-id="06f82-120">In the example, you can see that income is the most influential factor, followed by region.</span></span> <span data-ttu-id="06f82-121">D'altra parte, è altamente improbabile che i clienti con molte automobili e molti figli acquisteranno una bicicletta.</span><span class="sxs-lookup"><span data-stu-id="06f82-121">On the other hand, customers with many cars and many children are highly unlikely to buy a bike.</span></span>

2.  <span data-ttu-id="06f82-122">Nel riquadro **Variabili** fare clic sull'intestazione di colonna **Attributo**.</span><span class="sxs-lookup"><span data-stu-id="06f82-122">In the **Variables** pane, click the column heading for **Attribute**.</span></span>

     <span data-ttu-id="06f82-123">Eseguendo l'ordinamento in base all'attributo, è possibile visualizzare i contenitori creati per ciascuna delle colonne di input.</span><span class="sxs-lookup"><span data-stu-id="06f82-123">By sorting on attribute, you can see the bins that were created for each of the input columns.</span></span> <span data-ttu-id="06f82-124">Le colonne con valori discreti, ad esempio occupation, sono *suddivise* dai valori letterali.</span><span class="sxs-lookup"><span data-stu-id="06f82-124">Columns with discrete values, such as occupation, are *binned* by the literal values.</span></span>

3.  <span data-ttu-id="06f82-125">Si notino gli intervalli di valori trovati per **Age** e **Income**.</span><span class="sxs-lookup"><span data-stu-id="06f82-125">Notice the ranges of values that were found for **Age** and **Income**.</span></span>

     <span data-ttu-id="06f82-126">Se una qualsiasi delle colonne di input è in numeri, ossia l'intera colonna di dati è un tipo di dati numerici continui, i numeri sono inseriti in bucket, o suddivisi, in intervalli discreti.</span><span class="sxs-lookup"><span data-stu-id="06f82-126">If any of your input columns are numbers (that is, the entire column of data is a continuous numeric data type), the numbers are bucketed, or binned, into discrete ranges.</span></span>

     <span data-ttu-id="06f82-127">Per Income, la colonna è stata suddivisa in raggruppamenti, ad esempio 78.4-154.06 (per l'intervallo di reddito superiore).</span><span class="sxs-lookup"><span data-stu-id="06f82-127">For Income, the column has been subdivided into groupings such as 78.4-154.06 (for the uppermost income range).</span></span>

     <span data-ttu-id="06f82-128">![Ordinamento per visualizzare la modalità di suddivisione delle variabili](media/dm13-nn-bucketing-variables.gif "Ordinamento per visualizzare la modalità di suddivisione delle variabili")</span><span class="sxs-lookup"><span data-stu-id="06f82-128">![sort to view how variables were binned](media/dm13-nn-bucketing-variables.gif "sort to view how variables were binned")</span></span>

     <span data-ttu-id="06f82-129">Se si desiderano raggruppamenti differenti, è necessario usare lo strumento [Modifica etichette &#40;componenti aggiuntivi Data Mining di SQL Server&#41;](relabel-sql-server-data-mining-add-ins.md) o le funzioni di Excel per creare nuove categorie di reddito prima di compilare il modello.</span><span class="sxs-lookup"><span data-stu-id="06f82-129">If you want different groupings, you should use the [Relabel &#40;SQL Server Data Mining Add-ins&#41;](relabel-sql-server-data-mining-add-ins.md) tool, or Excel functions, to create new income categories before building the model.</span></span>

4.  <span data-ttu-id="06f82-130">Fare clic su **Predilige Sì** per ripristinare la vista predefinita del grafico.</span><span class="sxs-lookup"><span data-stu-id="06f82-130">Click **Favors Yes** to restore the graph to the default view.</span></span>

     <span data-ttu-id="06f82-131">Per impostazione predefinita, la vista viene ordinata in base al valore di **Predilige** per il primo valore del risultato.</span><span class="sxs-lookup"><span data-stu-id="06f82-131">By default, the view is sorted by the value of **Favors** for the first outcome value.</span></span> <span data-ttu-id="06f82-132">È possibile modificare i risultati assegnati alla prima e alla seconda colonna scegliendo un nuovo valore per **Valore 1** e **Valore 2** in **Output**.</span><span class="sxs-lookup"><span data-stu-id="06f82-132">You can change which outcomes are assigned to the first and second columns by choosing a new value for **Value 1** and **Value 2** in **Output**.</span></span>

5.  <span data-ttu-id="06f82-133">Posizionare il mouse sulla barra colorata superiore del grafico.</span><span class="sxs-lookup"><span data-stu-id="06f82-133">Pause the mouse over the topmost colored bar in the chart.</span></span>

     <span data-ttu-id="06f82-134">Viene visualizzata una descrizione comando che include un punteggio della *priorità*, una coppia di punteggi di *probabilità* e una coppia di valori di *accuratezza*.</span><span class="sxs-lookup"><span data-stu-id="06f82-134">A ToolTip appears that includes an *importance* score, a pair of *probability* scores, and a pair of *lift* values.</span></span>

    -   <span data-ttu-id="06f82-135">La **priorità** viene calcolata nell'intero set di dati e identifica l'attributo che, dati tutti gli input, è più correlato al risultato di destinazione.</span><span class="sxs-lookup"><span data-stu-id="06f82-135">**Importance** is calculated across the entire dataset, and identifies the attribute that, given all inputs, is most correlated with the target outcome.</span></span> <span data-ttu-id="06f82-136">Nel visualizzatore vengono ordinati i valori nel grafico in base ai punteggi di priorità.</span><span class="sxs-lookup"><span data-stu-id="06f82-136">The viewer sorts the values in the chart by the importance scores.</span></span>

    -   <span data-ttu-id="06f82-137">La **probabilità** viene calcolata per ogni set di coppie attributo-valore, per i risultati di destinazione, nell'intero set di dati.</span><span class="sxs-lookup"><span data-stu-id="06f82-137">**Probability** is calculated for each set of attribute-value pairs, for the target outcomes, across the entire data set.</span></span>

    -   <span data-ttu-id="06f82-138">L'**accuratezza** indica quanto è utile questa determinata coppia attributo-valore per la promozione di un risultato o di un altro.</span><span class="sxs-lookup"><span data-stu-id="06f82-138">**Lift** tells you how useful this particular attribute-value pair is for promoting one outcome or another.</span></span>

     <span data-ttu-id="06f82-139">Nota: nella descrizione comando sono contenute le stesse informazioni indipendentemente dal fatto che si posizioni il mouse su una colonna o sull'altra.</span><span class="sxs-lookup"><span data-stu-id="06f82-139">Note: The ToolTip contains the same information no matter whether you position the mouse over one column or the other.</span></span>

 [<span data-ttu-id="06f82-140">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="06f82-140">Back To Top</span></span>](#BKMK_Tabs)

###  <a name="inputs"></a><a name="BKMK_Inputs"></a><span data-ttu-id="06f82-141">Input</span><span class="sxs-lookup"><span data-stu-id="06f82-141">Inputs</span></span>
 <span data-ttu-id="06f82-142">Il riquadro **Input** consente di scegliere un set di input e applicarlo come filtro al modello. In questo modo è possibile vedere l'influenza di tali scelte sul risultato, in base ai dati di training</span><span class="sxs-lookup"><span data-stu-id="06f82-142">The **Inputs** pane lets you choose a set of inputs and apply that as a filter to the model, which lets you see the influence of those choices on the outcome, based on the training data</span></span>

##### <a name="explore-inputs"></a><span data-ttu-id="06f82-143">Esplorazione degli input</span><span class="sxs-lookup"><span data-stu-id="06f82-143">Explore inputs</span></span>

1.  <span data-ttu-id="06f82-144">Si supponga di voler fare riferimento a un gruppo specifico e visualizzare i fattori che hanno influito maggiormente sugli acquisti in tale gruppo.</span><span class="sxs-lookup"><span data-stu-id="06f82-144">Suppose you want to target a particular group, and see the factors that most influence purchasing in that group.</span></span>

     <span data-ttu-id="06f82-145">Nel riquadro **input** fare clic sulla **\<All>** cella sotto **attributo**e selezionare **Age**.</span><span class="sxs-lookup"><span data-stu-id="06f82-145">In the **Input** pane, click the **\<All>** cell under **Attribute**, and select **Age**.</span></span>

     <span data-ttu-id="06f82-146">Per **Valore** selezionare la categoria di età più giovane.</span><span class="sxs-lookup"><span data-stu-id="06f82-146">For **Value**, select the youngest age category.</span></span>

2.  <span data-ttu-id="06f82-147">Si noti che anche quando si filtra una fascia di età specifica, l'area Pacifico viene inclusa nella parte superiore dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="06f82-147">Notice that even when you filter on a particular age group, the Pacific region comes to near the top of the list.</span></span> <span data-ttu-id="06f82-148">Questo avviene perché i clienti nell'area Pacifico hanno maggiore probabilità di acquistare una bicicletta rispetto ai clienti in altre aree.</span><span class="sxs-lookup"><span data-stu-id="06f82-148">This is because customers in the Pacific region are far more likely to buy a bike than customers in other regions.</span></span>

     <span data-ttu-id="06f82-149">Poiché l'area non è un fattore che è possibile influenzare, per non prendere in considerazione questa variabile e visualizzare altri fattori, è possibile modificare di nuovo gli input.</span><span class="sxs-lookup"><span data-stu-id="06f82-149">Since region is not something you can influence, to remove this variable from consideration and see other factors, you can change the inputs again.</span></span>

     <span data-ttu-id="06f82-150">Nel riquadro **Input** fare clic sulla cella vuota sotto **Age** e selezionare **Region**.</span><span class="sxs-lookup"><span data-stu-id="06f82-150">In the **Input** pane, click the empty cell under **Age**, and select **Region**.</span></span>

     <span data-ttu-id="06f82-151">Per **Valore** selezionare **Europa**.</span><span class="sxs-lookup"><span data-stu-id="06f82-151">For **Value**, select **Europe**.</span></span>

3.  <span data-ttu-id="06f82-152">Continuare ad aggiungere i filtri di input per concentrarsi su un gruppo di particolare interesse.</span><span class="sxs-lookup"><span data-stu-id="06f82-152">Continue adding input filters to focus on a group of particular interest.</span></span>

     <span data-ttu-id="06f82-153">Ad esempio, per l'attributo di input, aggiungere **Gender** e selezionare **Female** come valore.</span><span class="sxs-lookup"><span data-stu-id="06f82-153">For example, for the input attribute, add **Gender**, and select **Female** as the value.</span></span>

     <span data-ttu-id="06f82-154">![Effetto dei test sui risultati degli attributi selezionati](media/dm13-neuralnet-agebuyer2.gif "Effetto dei test sui risultati degli attributi selezionati")</span><span class="sxs-lookup"><span data-stu-id="06f82-154">![Testing effect on outcome of selected attributes](media/dm13-neuralnet-agebuyer2.gif "Testing effect on outcome of selected attributes")</span></span>

     <span data-ttu-id="06f82-155">Si noti come l'elenco di variabili cambia.</span><span class="sxs-lookup"><span data-stu-id="06f82-155">Notice how the list of variables changes.</span></span> <span data-ttu-id="06f82-156">Ora **Income** è la variabile più importante nella stima del risultato di destinazione.</span><span class="sxs-lookup"><span data-stu-id="06f82-156">Now **Income** is the variable that is most important in predicting the target outcome.</span></span>

     <span data-ttu-id="06f82-157">L'ordine in cui si applicano i filtri di input non influisce sui risultati.</span><span class="sxs-lookup"><span data-stu-id="06f82-157">The order in which you apply the input filters does not affect the results.</span></span>

 [<span data-ttu-id="06f82-158">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="06f82-158">Back To Top</span></span>](#BKMK_Tabs)

###  <a name="outputs"></a><a name="BKMK_Outputs"></a><span data-ttu-id="06f82-159">Uscite</span><span class="sxs-lookup"><span data-stu-id="06f82-159">Outputs</span></span>
 <span data-ttu-id="06f82-160">Nel riquadro **Output** è possibile scegliere il risultato a cui si è interessati.</span><span class="sxs-lookup"><span data-stu-id="06f82-160">In the **Outputs** pane, you can choose the outcome that you are interested in.</span></span> <span data-ttu-id="06f82-161">Le reti neurali consentono di specificare il numero di colonne di risultati desiderato, sebbene l'aggiunta di più output aumenti la complessità del modello e possa richiedere un tempo di elaborazione più lungo.</span><span class="sxs-lookup"><span data-stu-id="06f82-161">Neural networks let you specify as many outcome columns as you like, although adding more outputs adds to the complexity of the model and may require a much longer time to process.</span></span>

 <span data-ttu-id="06f82-162">Per confrontare due output, essi devono essere stati definiti come colonne **Stima** o **Solo stima**.</span><span class="sxs-lookup"><span data-stu-id="06f82-162">To compare two outputs, they must have been designated as **Predict** or **Predict Only** columns.</span></span>

##### <a name="explore-outputs"></a><span data-ttu-id="06f82-163">Esplorazione degli output</span><span class="sxs-lookup"><span data-stu-id="06f82-163">Explore outputs</span></span>

1.  <span data-ttu-id="06f82-164">Per selezionare un attributo, usare l'elenco **Attributo output**.</span><span class="sxs-lookup"><span data-stu-id="06f82-164">Use the **Output Attribute** list to select an attribute.</span></span>

2.  <span data-ttu-id="06f82-165">Selezionare due risultati dagli elenchi Valore 1 e Valore 2.</span><span class="sxs-lookup"><span data-stu-id="06f82-165">Select two outcomes from the Value 1 and Value 2 lists.</span></span> <span data-ttu-id="06f82-166">Questi due stati dell'attributo di output verranno confrontati nel riquadro **Variabili** .</span><span class="sxs-lookup"><span data-stu-id="06f82-166">These two states of the output attribute will be compared in the **Variables** pane.</span></span>

 [<span data-ttu-id="06f82-167">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="06f82-167">Back To Top</span></span>](#BKMK_Tabs)

## <a name="more-about-neural-network-models"></a><span data-ttu-id="06f82-168">Ulteriori informazioni sui modelli di rete neurale</span><span class="sxs-lookup"><span data-stu-id="06f82-168">More About Neural Network Models</span></span>
 <span data-ttu-id="06f82-169">Le informazioni nel visualizzatore vengono recuperate dal server utilizzando una stored procedure specifica di questo tipo di modello: System.Microsoft.AnalysisServices.System.DataMining.NeuralNet.GetAttributeScores.</span><span class="sxs-lookup"><span data-stu-id="06f82-169">The information in the viewer is retrieved from the server using a stored procedure specific to this model type: System.Microsoft.AnalysisServices.System.DataMining.NeuralNet.GetAttributeScores.</span></span>

 <span data-ttu-id="06f82-170">Se si desidera creare un modello con più attributi stimabili tramite i componenti aggiuntivi, usare le opzioni di modellazione **Avanzate**.</span><span class="sxs-lookup"><span data-stu-id="06f82-170">If you want to create a model with multiple predictable attributes using the add-ins, use the **Advanced** modeling options.</span></span>

 <span data-ttu-id="06f82-171">Per altre informazioni, vedere [Crea struttura di data mining &#40;componenti aggiuntivi Data Mining di SQL Server&#41;](create-mining-structure-sql-server-data-mining-add-ins.md) e [Aggiunta modello a struttura &#40;componenti aggiuntivi Data Mining per Excel&#41;](add-model-to-structure-data-mining-add-ins-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="06f82-171">For more information, see [Create Mining Structure &#40;SQL Server Data Mining Add-ins&#41;](create-mining-structure-sql-server-data-mining-add-ins.md) and [Add Model to Structure &#40;Data Mining Add-ins for Excel&#41;](add-model-to-structure-data-mining-add-ins-for-excel.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="06f82-172">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="06f82-172">See Also</span></span>
 [<span data-ttu-id="06f82-173">Esplorazione di modelli in Excel &#40;SQL Server componenti aggiuntivi Data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="06f82-173">Browsing Models in Excel &#40;SQL Server Data Mining Add-ins&#41;</span></span>](browsing-models-in-excel-sql-server-data-mining-add-ins.md)


