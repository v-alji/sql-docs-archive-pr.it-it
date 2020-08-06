---
title: Esplorazione di un modello Naive Bayes | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: f9160b48-3beb-439c-9694-f084e1afa625
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3b0d18cd74e71f1ef18bffd6b0998e0b326e887a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625815"
---
# <a name="browsing-a-naive-bayes-model"></a><span data-ttu-id="74c5b-102">Esplorazione di un modello Naïve Bayes</span><span class="sxs-lookup"><span data-stu-id="74c5b-102">Browsing a Naive Bayes Model</span></span>
  <span data-ttu-id="74c5b-103">Quando si apre un modello Naive Bayes utilizzando **Sfoglia**, il modello viene visualizzato in un visualizzatore interattivo con quattro riquadri diversi.</span><span class="sxs-lookup"><span data-stu-id="74c5b-103">When you open a Naïve Bayes model using **Browse**, the model is displayed in an interactive viewer with four different panes.</span></span> <span data-ttu-id="74c5b-104">Il visualizzatore consente di esplorare le correlazioni e ottenere informazioni sul modello e sui dati sottostanti.</span><span class="sxs-lookup"><span data-stu-id="74c5b-104">Use the viewer to explore correlations, and get information about the model and the underlying data.</span></span>  
  
-   [<span data-ttu-id="74c5b-105">Rete di dipendenze</span><span class="sxs-lookup"><span data-stu-id="74c5b-105">Dependency Network</span></span>](#bkmk_DepNet)  
  
-   [<span data-ttu-id="74c5b-106">Profili attributo</span><span class="sxs-lookup"><span data-stu-id="74c5b-106">Attribute Profiles</span></span>](#bkmk_AttProf)  
  
-   [<span data-ttu-id="74c5b-107">Caratteristiche attributo</span><span class="sxs-lookup"><span data-stu-id="74c5b-107">Attribute Characteristics</span></span>](#bkmk_AttChar)  
  
-   [<span data-ttu-id="74c5b-108">Analisi discriminante attributi</span><span class="sxs-lookup"><span data-stu-id="74c5b-108">Attribute Discrimination</span></span>](#bkmk_AttDisc)  
  
##  <a name="explore-the-model"></a><a name="BKMK_Tabs"></a><span data-ttu-id="74c5b-109">Esplorare il modello</span><span class="sxs-lookup"><span data-stu-id="74c5b-109">Explore the Model</span></span>  
 <span data-ttu-id="74c5b-110">Lo scopo del visualizzatore è consentire di esplorare l'interazione tra gli attributi di input e output (input e variabili dipendenti) che sono stati individuati dal modello [!INCLUDE[msCoName](../includes/msconame-md.md)] Naïve Bayes.</span><span class="sxs-lookup"><span data-stu-id="74c5b-110">The purpose of the viewer is to help you explore the interaction between input and output attributes (inputs and dependent variables) that were discovered by the [!INCLUDE[msCoName](../includes/msconame-md.md)] Naive Bayes model.</span></span>  
  
 <span data-ttu-id="74c5b-111">Se si desidera provare il Visualizzatore Naive Bayes, utilizzare la [procedura guidata classificazione &#40;componenti aggiuntivi Data mining per&#41;](classify-wizard-data-mining-add-ins-for-excel.md) guidata di Excel sulla barra multifunzione data mining, fare clic sull'opzione **Avanzate** e modificare l'algoritmo in modo da utilizzare l'algoritmo Naive Bayes.</span><span class="sxs-lookup"><span data-stu-id="74c5b-111">If you want to experiment with the Naïve Bayes viewer, use the [Classify Wizard &#40;Data Mining Add-ins for Excel&#41;](classify-wizard-data-mining-add-ins-for-excel.md) wizard in the Data Mining ribbon, click the **Advanced** option, and change the algorithm to use the Naïve Bayes algorithm</span></span>  
  
 <span data-ttu-id="74c5b-112">Per questi esempi, sono stati usati i dati di origine nella cartella di lavoro di esempio e la colonna **Yearly Income**è stata raggruppata in cinque gruppi di reddito, da **molto bassa** a **molto alta**.</span><span class="sxs-lookup"><span data-stu-id="74c5b-112">For these examples, we used the Source data in the sample workbook, and grouped the column, **Yearly Income**, into five income groups, from **Very Low** to **Very High**.</span></span> <span data-ttu-id="74c5b-113">Nel modello Naïve Bayes sono stati quindi analizzati i fattori correlati a ogni categoria di reddito.</span><span class="sxs-lookup"><span data-stu-id="74c5b-113">The Naïve Bayes model then analyzed the factors correlated with each income category.</span></span>  
  
###  <a name="dependency-network"></a><a name="bkmk_DepNet"></a><span data-ttu-id="74c5b-114">Rete di dipendenze</span><span class="sxs-lookup"><span data-stu-id="74c5b-114">Dependency Network</span></span>  
 <span data-ttu-id="74c5b-115">La prima finestra che verrà usata è la **rete di dipendenze**.</span><span class="sxs-lookup"><span data-stu-id="74c5b-115">The first window you'll use is the **Dependency Network**.</span></span> <span data-ttu-id="74c5b-116">Vengono visualizzati immediatamente gli input strettamente correlati al risultato selezionato.</span><span class="sxs-lookup"><span data-stu-id="74c5b-116">It shows you at a glance which inputs are closely correlated to the selected outcome.</span></span>  
  
 <span data-ttu-id="74c5b-117">![Rete di dipendenze in Visualizzatore Naive Bayes](media/dm13-nb.gif "Rete di dipendenze in Visualizzatore Naive Bayes")</span><span class="sxs-lookup"><span data-stu-id="74c5b-117">![dependency network in Naive Bayes viewer](media/dm13-nb.gif "dependency network in Naive Bayes viewer")</span></span>  
  
##### <a name="explore-the-dependency-network"></a><span data-ttu-id="74c5b-118">Esplorare la rete di dipendenze</span><span class="sxs-lookup"><span data-stu-id="74c5b-118">Explore the dependency network</span></span>  
  
1.  <span data-ttu-id="74c5b-119">Innanzitutto, fare clic sul risultato di destinazione, **yearly**Income, che è rappresentato come un nodo nel grafico.</span><span class="sxs-lookup"><span data-stu-id="74c5b-119">First, click the target outcome, **Yearly Income**, which is represented as a node in the graph.</span></span>  
  
     <span data-ttu-id="74c5b-120">I nodi evidenziati che circondano la variabile di destinazione sono quelli correlati statisticamente con questo risultato.</span><span class="sxs-lookup"><span data-stu-id="74c5b-120">The highlighted nodes surrounding the target variable are those that are statistically correlated with this outcome.</span></span> <span data-ttu-id="74c5b-121">Utilizzare la legenda nella parte inferiore del visualizzatore per comprendere la natura della relazione.</span><span class="sxs-lookup"><span data-stu-id="74c5b-121">Use the legend at the bottom of the viewer to understand the nature of the relationship.</span></span>  
  
2.  <span data-ttu-id="74c5b-122">Fare clic sul dispositivo di scorrimento a sinistra del visualizzatore e trascinarlo verso il basso.</span><span class="sxs-lookup"><span data-stu-id="74c5b-122">Click the slider at the left of the viewer and drag it downward.</span></span>  
  
     <span data-ttu-id="74c5b-123">Questo controllo consente di filtrare le variabili indipendenti, in base ai livelli di attendibilità delle dipendenze.</span><span class="sxs-lookup"><span data-stu-id="74c5b-123">This control filters the independent variables, based on the strengths of the dependencies.</span></span> <span data-ttu-id="74c5b-124">Quando si trascina il dispositivo di scorrimento verso il basso, nel grafico restano solo i collegamenti più attendibili.</span><span class="sxs-lookup"><span data-stu-id="74c5b-124">When you drag the slider down, only the strongest links remain in the graph.</span></span>  
  
3.  <span data-ttu-id="74c5b-125">Dopo aver filtrato il grafico, fare clic sul pulsante **copia la visualizzazione del grafico**.</span><span class="sxs-lookup"><span data-stu-id="74c5b-125">After you have filtered the graph, click the button, **Copy Graph View**.</span></span> <span data-ttu-id="74c5b-126">Selezionare quindi un foglio di lavoro in Excel e premere CTRL+V.</span><span class="sxs-lookup"><span data-stu-id="74c5b-126">Then select a worksheet in Excel, and press Ctrl+V.</span></span>  
  
     <span data-ttu-id="74c5b-127">Questa opzione consente di copiare la vista selezionata, inclusi i filtri e l'evidenziazione.</span><span class="sxs-lookup"><span data-stu-id="74c5b-127">This option copies the view that you have selected, including filters and highlighting.</span></span>  
  
 [<span data-ttu-id="74c5b-128">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="74c5b-128">Back To Top</span></span>](#BKMK_Tabs)  
  
###  <a name="attribute-profiles"></a><a name="bkmk_AttProf"></a> <span data-ttu-id="74c5b-129">Profili attributo</span><span class="sxs-lookup"><span data-stu-id="74c5b-129">Attribute Profiles</span></span>  
 <span data-ttu-id="74c5b-130">Le finestre **Profili attributo** offrono un'indicazione visiva del modo in cui tutte le altre variabili sono correlate ai singoli risultati.</span><span class="sxs-lookup"><span data-stu-id="74c5b-130">The **Attribute Profiles** windows gives you a visual indication of how all other variables are related to the individual outcomes.</span></span>  
  
##### <a name="explore-the-profiles"></a><span data-ttu-id="74c5b-131">Esplorazione del profili</span><span class="sxs-lookup"><span data-stu-id="74c5b-131">Explore the profiles</span></span>  
  
1.  <span data-ttu-id="74c5b-132">Per nascondere alcuni valori in modo da poter confrontare più facilmente i risultati, fare clic sull'intestazione di colonna e trascinarla sotto un'altra colonna.</span><span class="sxs-lookup"><span data-stu-id="74c5b-132">To hide some values so that you can more easily compare outcomes, click the column heading and drag it under another column.</span></span>  
  
     <span data-ttu-id="74c5b-133">![Profili attributi in Visualizzatore Naive Bayes](media/dm13-nb-attprof.gif "Profili attributi in Visualizzatore Naive Bayes")</span><span class="sxs-lookup"><span data-stu-id="74c5b-133">![attribute profiles in Naive Bayes viewer](media/dm13-nb-attprof.gif "attribute profiles in Naive Bayes viewer")</span></span>  
  
2.  <span data-ttu-id="74c5b-134">Fare clic su una cella per visualizzare la distribuzione dei valori in **Legenda data mining**.</span><span class="sxs-lookup"><span data-stu-id="74c5b-134">Click in any cell to view the distribution of values in the **Mining Legend**.</span></span>  
  
     <span data-ttu-id="74c5b-135">Poiché gli attributi associati ai differenti risultati vengono rappresentati visivamente, è facile individuare correlazioni interessanti, ad esempio i redditi sono distribuiti per area.</span><span class="sxs-lookup"><span data-stu-id="74c5b-135">Because the attributes associated with different outcomes are displayed visually, it is easy to spot interesting correlations, such as how incomes are distributed by region.</span></span>  
  
3.  <span data-ttu-id="74c5b-136">Per ottenere i dati sottostanti a questa visualizzazione, fare clic su **copia in Excel**.</span><span class="sxs-lookup"><span data-stu-id="74c5b-136">To obtain the data underlying this view, click **Copy to Excel**.</span></span> <span data-ttu-id="74c5b-137">Viene generata una tabella in un nuovo foglio di lavoro in cui vengono visualizzate le correlazioni tra singoli attributi e risultati.</span><span class="sxs-lookup"><span data-stu-id="74c5b-137">A table is generated in a new worksheet that shows the correlations among individual attributes and outcomes.</span></span> <span data-ttu-id="74c5b-138">In questa tabella di Excel è possibile nascondere o filtrare facilmente le colonne.</span><span class="sxs-lookup"><span data-stu-id="74c5b-138">In this Excel table you can easily hide or filter columns.</span></span>  
  
 [<span data-ttu-id="74c5b-139">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="74c5b-139">Back To Top</span></span>](#BKMK_Tabs)  
  
###  <a name="attribute-characteristics"></a><a name="bkmk_AttChar"></a><span data-ttu-id="74c5b-140">Caratteristiche degli attributi</span><span class="sxs-lookup"><span data-stu-id="74c5b-140">Attribute Characteristics</span></span>  
 <span data-ttu-id="74c5b-141">La vista **Caratteristiche attributo** è utile per l'analisi approfondita di una determinata variabile di risultato e dei fattori che contribuiscono.</span><span class="sxs-lookup"><span data-stu-id="74c5b-141">The **Attribute Characteristics** view is useful for in-depth examination of a particular outcome variable and the contributing factors.</span></span>  
  
 <span data-ttu-id="74c5b-142">![Caratteristiche attributi in Visualizzatore Naive Bayes](media/dm13-nb-viewer.gif "Caratteristiche attributi in Visualizzatore Naive Bayes")</span><span class="sxs-lookup"><span data-stu-id="74c5b-142">![attribute characteristics in Naive Bayes viewer](media/dm13-nb-viewer.gif "attribute characteristics in Naive Bayes viewer")</span></span>  
  
##### <a name="explore-the-attribute-characteristics"></a><span data-ttu-id="74c5b-143">Esplorazione delle caratteristiche degli attributi</span><span class="sxs-lookup"><span data-stu-id="74c5b-143">Explore the attribute characteristics</span></span>  
  
1.  <span data-ttu-id="74c5b-144">Fare clic su **valore** e selezionare un elemento del **valore**.</span><span class="sxs-lookup"><span data-stu-id="74c5b-144">Click **Value** and select an item from the **Value**.</span></span>  
  
     <span data-ttu-id="74c5b-145">Quando si seleziona un risultato di destinazione, il grafico viene aggiornato per visualizzare i fattori associati in modo più sicuro al risultato, ordinati in base alla priorità.</span><span class="sxs-lookup"><span data-stu-id="74c5b-145">As you select a target outcome, the graph updates to show the factors that are most strongly associated with the outcome, sorted by importance.</span></span>  
  
     <span data-ttu-id="74c5b-146">Si noti che se si crea un modello utilizzando l'opzione [Analizza fattori di influenza chiave &#40;strumenti di analisi tabelle per Excel&#41;](analyze-key-influencers-table-analysis-tools-for-excel.md) , è possibile creare modelli con più di un attributo stimabile.</span><span class="sxs-lookup"><span data-stu-id="74c5b-146">Note that if you create a model using the [Analyze Key Influencers &#40;Table Analysis Tools for Excel&#41;](analyze-key-influencers-table-analysis-tools-for-excel.md) option, you can create models that have more than one predictable attribute.</span></span> <span data-ttu-id="74c5b-147">Tuttavia, tutte le altre procedure guidate nei componenti aggiuntivi Data mining limitano l'utente a un attributo stimabile.</span><span class="sxs-lookup"><span data-stu-id="74c5b-147">However, all other wizards in the Data Mining add-ins limit you to one predictable attribute.</span></span>  
  
2.  <span data-ttu-id="74c5b-148">Fare clic su **copia in Excel** per creare una tabella in un nuovo foglio di lavoro, elencando i punteggi per tutti gli attributi correlati al risultato di destinazione selezionato.</span><span class="sxs-lookup"><span data-stu-id="74c5b-148">Click **Copy to Excel** to create a table, in a new worksheet, listing the scores for all attributes that are related to the selected target outcome.</span></span>  
  
 [<span data-ttu-id="74c5b-149">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="74c5b-149">Back To Top</span></span>](#BKMK_Tabs)  
  
###  <a name="attribute-discrimination"></a><a name="bkmk_AttDisc"></a><span data-ttu-id="74c5b-150">Discriminazione degli attributi</span><span class="sxs-lookup"><span data-stu-id="74c5b-150">Attribute Discrimination</span></span>  
 <span data-ttu-id="74c5b-151">La visualizzazione analisi **discriminante attributi** consente di confrontare due risultati o un risultato rispetto a tutti gli altri risultati.</span><span class="sxs-lookup"><span data-stu-id="74c5b-151">The **Attribute Discrimination** view helps compare two outcomes, or one outcome vs. all other outcomes.</span></span>  
  
 <span data-ttu-id="74c5b-152">![Discriminante attributi in Visualizzatore Naive Bayes](media/dm13-nb-attdisc.gif "Discriminante attributi in Visualizzatore Naive Bayes")</span><span class="sxs-lookup"><span data-stu-id="74c5b-152">![attribute discrimination in Naive Bayes viewer](media/dm13-nb-attdisc.gif "attribute discrimination in Naive Bayes viewer")</span></span>  
  
##### <a name="explore-attribute-discrimination"></a><span data-ttu-id="74c5b-153">Esplorazione dell'analisi discriminante attributi</span><span class="sxs-lookup"><span data-stu-id="74c5b-153">Explore attribute discrimination</span></span>  
  
1.  <span data-ttu-id="74c5b-154">Utilizzare i controlli, **valore 1** e **valore 2**, per selezionare i risultati che si desidera confrontare.</span><span class="sxs-lookup"><span data-stu-id="74c5b-154">Use the controls, **Value 1** and **Value 2**, to select the outcomes that you want to compare.</span></span>  
  
     <span data-ttu-id="74c5b-155">Ad esempio, in questo modello sono presenti alcuni attributi interessanti nel gruppo low income, quindi è stato scelto il gruppo di reddito più basso nel primo elenco a discesa e sono **stati scelti tutti gli altri Stati** nel secondo elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="74c5b-155">For example, in this model there were some interesting attributes in the low income group, so we chose the lowest income group in the first dropdown list, and chose **All other states** in the second dropdown list.</span></span>  
  
     <span data-ttu-id="74c5b-156">Gli attributi vengono ordinati in ordine di importanza (calcolata in base ai dati di training).</span><span class="sxs-lookup"><span data-stu-id="74c5b-156">The attributes are sorted by order of importance (calculated based on the training data).</span></span> <span data-ttu-id="74c5b-157">Pertanto, occupazione è il fattore più strettamente correlato al reddito (almeno per questo gruppo di destinazione).</span><span class="sxs-lookup"><span data-stu-id="74c5b-157">Therefore, occupation is the factor most closely correlated with income (for this target group, at least),</span></span>  
  
     <span data-ttu-id="74c5b-158">Per visualizzare le cifre esatte, fare clic sulla barra colorata e visualizzare **Legenda data mining**.</span><span class="sxs-lookup"><span data-stu-id="74c5b-158">To see the exact figures, click the colored bar and view the **Mining Legend**.</span></span>  
  
2.  <span data-ttu-id="74c5b-159">Si noti che anche i redditi inferiori sono correlati con l'area Europa.</span><span class="sxs-lookup"><span data-stu-id="74c5b-159">Note that lower incomes are also correlated with the Europe region.</span></span>  
  
     <span data-ttu-id="74c5b-160">Il modello Naïve Bayes non supporta il drill-down; tuttavia, se si desidera esaminare i case associati a questo gruppo di risultati, è possibile utilizzare una query.</span><span class="sxs-lookup"><span data-stu-id="74c5b-160">The Naïve Bayes model does not support drilldown; however, if you wanted to investigate the cases associated with this outcome group, you could use a query.</span></span> <span data-ttu-id="74c5b-161">Per informazioni sulle query su questo tipo di modello, vedere [esempi di query sul modello Naive Bayes](data-mining/naive-bayes-model-query-examples.md).</span><span class="sxs-lookup"><span data-stu-id="74c5b-161">For information about queries on this type of model, see [Naive Bayes Model Query Examples](data-mining/naive-bayes-model-query-examples.md).</span></span>  
  
 [<span data-ttu-id="74c5b-162">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="74c5b-162">Back To Top</span></span>](#BKMK_Tabs)  
  
## <a name="see-also"></a><span data-ttu-id="74c5b-163">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="74c5b-163">See Also</span></span>  
 [<span data-ttu-id="74c5b-164">Esplorazione di modelli in Excel &#40;SQL Server componenti aggiuntivi Data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="74c5b-164">Browsing Models in Excel &#40;SQL Server Data Mining Add-ins&#41;</span></span>](browsing-models-in-excel-sql-server-data-mining-add-ins.md)  
  
  
