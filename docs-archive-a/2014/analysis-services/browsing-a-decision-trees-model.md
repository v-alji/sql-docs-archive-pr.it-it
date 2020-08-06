---
title: Esplorazione di un modello Decision Trees | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining models, browsing
- mining models, viewing
- tree viewer
- mining model, decision tree
- decision tree [data mining]
- dependency network
ms.assetid: 6b3dd1ae-caff-41c3-817b-802dc020ff88
author: minewiskan
ms.author: owend
ms.openlocfilehash: 809d2e494cfa7a6c4078acf95c2c70a0e68c188d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625822"
---
# <a name="browsing-a-decision-trees-model"></a><span data-ttu-id="1a2fd-102">Esplorazione di un modello Decision Trees</span><span class="sxs-lookup"><span data-stu-id="1a2fd-102">Browsing a Decision Trees Model</span></span>
  <span data-ttu-id="1a2fd-103">Quando si apre un modello di classificazione utilizzando **Sfoglia**, il modello viene visualizzato in un visualizzatore albero delle decisioni interattivo, simile al [!INCLUDE[msCoName](../includes/msconame-md.md)] Visualizzatore Decision Trees in [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1a2fd-103">When you open a classification model using **Browse**, the model is displayed in an interactive decision tree viewer, similar to the [!INCLUDE[msCoName](../includes/msconame-md.md)] Decision Trees viewer in [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="1a2fd-104">Nell visualizzatore vengono visualizzati i risultati di classificazione come grafico progettato per evidenziare i criteri che differenziano un gruppo di dati da un altro.</span><span class="sxs-lookup"><span data-stu-id="1a2fd-104">The viewer displays the results of classification as a graph that is designed to highlight the criteria that differentiate one group of data from another.</span></span> <span data-ttu-id="1a2fd-105">È inoltre possibile eseguire il drill-down in singoli subset dell'albero e recuperare i dati sottostanti.</span><span class="sxs-lookup"><span data-stu-id="1a2fd-105">You can also drill down into individual subsets of the tree and retrieve the underlying data.</span></span>  
  
##  <a name="explore-the-model"></a><a name="bkmk_Top"></a><span data-ttu-id="1a2fd-106">Esplorare il modello</span><span class="sxs-lookup"><span data-stu-id="1a2fd-106">Explore the Model</span></span>  
 <span data-ttu-id="1a2fd-107">I modelli basati sull'algoritmo Decision Trees contengono molte informazioni interessanti da esplorare.</span><span class="sxs-lookup"><span data-stu-id="1a2fd-107">Models based on the Decision Trees algorithm have lots of interesting information to explore.</span></span> <span data-ttu-id="1a2fd-108">La finestra **Esplora** include le schede e i riquadri seguenti che consentono di acquisire familiarità con i modelli e prevedere i risultati mediante il grafo:</span><span class="sxs-lookup"><span data-stu-id="1a2fd-108">The **Browse** window includes the following tabs and panes to help you learn the patterns and predict outcomes using the graph:</span></span>  
  
-   [<span data-ttu-id="1a2fd-109">Albero delle decisioni</span><span class="sxs-lookup"><span data-stu-id="1a2fd-109">Decision Tree</span></span>](#BKMK_DecisionTree)  
  
-   [<span data-ttu-id="1a2fd-110">Rete di dipendenze</span><span class="sxs-lookup"><span data-stu-id="1a2fd-110">Dependency Network</span></span>](#BKMK_DNetwork)  
  
 <span data-ttu-id="1a2fd-111">Per provare un modello di albero delle decisioni, è possibile utilizzare i dati di esempio nella scheda Dati di training (o Origine dati) della cartella di lavoro dei dati di esempio e compilare un modello di albero delle decisioni utilizzando Bike Buyer come attributo stimabile.</span><span class="sxs-lookup"><span data-stu-id="1a2fd-111">To experiment with a decision trees model, you can use the sample data on the Training Data (or Source Data) tab of the sample data workbook, and build a decision tree model using Bike Buyer as the predictable attribute.</span></span>  
  
###  <a name="decision-tree"></a><a name="BKMK_DecisionTree"></a><span data-ttu-id="1a2fd-112">Albero delle decisioni</span><span class="sxs-lookup"><span data-stu-id="1a2fd-112">Decision Tree</span></span>  
 <span data-ttu-id="1a2fd-113">Questa vista è stata progettata per comprendere ed esplorare i fattori che portano un risultato.</span><span class="sxs-lookup"><span data-stu-id="1a2fd-113">This view is intended to help you understand and explore the factors that lead to an outcome.</span></span>  
  
 <span data-ttu-id="1a2fd-114">Il grafico dell'albero delle decisioni può essere letto da sinistra a destra nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="1a2fd-114">The decision tree graph can be read from left to right as follows:</span></span>  
  
-   <span data-ttu-id="1a2fd-115">I rettangoli, denominati *nodi*, contengono subset dei dati.</span><span class="sxs-lookup"><span data-stu-id="1a2fd-115">The rectangles, which are referred to as *nodes*, contain subsets of the data.</span></span> <span data-ttu-id="1a2fd-116">L'etichetta del nodo indica le caratteristiche di definizione di tale subset.</span><span class="sxs-lookup"><span data-stu-id="1a2fd-116">The label on the node tells you the defining characteristics of that subset.</span></span>  
  
-   <span data-ttu-id="1a2fd-117">Il nodo più a sinistra, denominato **All**, rappresenta il set di dati completo.</span><span class="sxs-lookup"><span data-stu-id="1a2fd-117">The leftmost node, labeled **All**, represents the complete data set.</span></span> <span data-ttu-id="1a2fd-118">Tutti i nodi successivi rappresentano i subset di dati.</span><span class="sxs-lookup"><span data-stu-id="1a2fd-118">All subsequent nodes represent subsets of the data.</span></span>  
  
-   <span data-ttu-id="1a2fd-119">Un albero delle decisioni contiene molte *divisioni*o posizioni in cui i dati dipendono da più set in base agli attributi.</span><span class="sxs-lookup"><span data-stu-id="1a2fd-119">A decision tree contains many *splits*, or places where the data diverges into multiple sets based on attributes.</span></span>  
  
     <span data-ttu-id="1a2fd-120">Ad esempio, nella prima divisione nel modello di esempio il set di dati viene suddiviso in tre gruppi per età.</span><span class="sxs-lookup"><span data-stu-id="1a2fd-120">For example, the first split in the sample model divides the dataset into three groups by age.</span></span>  
  
-   <span data-ttu-id="1a2fd-121">La divisione subito dopo il nodo **tutti** è la più importante perché mostra la condizione primaria che divide il set di dati.</span><span class="sxs-lookup"><span data-stu-id="1a2fd-121">The split immediately after the **All** node is most important because it shows the primary condition that divides this dataset.</span></span>  
  
     <span data-ttu-id="1a2fd-122">Le altre divisioni si trovano a destra.</span><span class="sxs-lookup"><span data-stu-id="1a2fd-122">Additional splits occur to the right.</span></span> <span data-ttu-id="1a2fd-123">Pertanto, analizzando differenti segmenti dell'albero, è possibile sapere quali attributi hanno influito maggiormente sul comportamento di acquisto.</span><span class="sxs-lookup"><span data-stu-id="1a2fd-123">Thus, by analyzing different segments of the tree, you can learn which attributes had the most influence on purchasing behavior.</span></span>  
  
 <span data-ttu-id="1a2fd-124">![Grafico della rete di dipendenze per un modello di associazione](media/dm13-dec-tree-split-definition.gif "Grafico della rete di dipendenze per un modello di associazione")</span><span class="sxs-lookup"><span data-stu-id="1a2fd-124">![Dependency network graph for an association model](media/dm13-dec-tree-split-definition.gif "Dependency network graph for an association model")</span></span>  
  
 <span data-ttu-id="1a2fd-125">Utilizzando queste informazioni, è possibile concentrare una campagna di marketing sui clienti che potrebbero semplicemente aver bisogno di incoraggiamento per eseguire un acquisto.</span><span class="sxs-lookup"><span data-stu-id="1a2fd-125">Using this information, you might focus a marketing campaign on customers that might simply need encouragement to make a purchase.</span></span>  
  
##### <a name="explore-the-decision-tree"></a><span data-ttu-id="1a2fd-126">Esplorazione dell'albero delle decisioni</span><span class="sxs-lookup"><span data-stu-id="1a2fd-126">Explore the decision tree</span></span>  
  
1.  <span data-ttu-id="1a2fd-127">Fare clic sul nodo **tutti** ed esaminare **Legenda data mining**.</span><span class="sxs-lookup"><span data-stu-id="1a2fd-127">Click the **All** node, and look at the **Mining Legend**.</span></span>  
  
     <span data-ttu-id="1a2fd-128">Viene visualizzato il conteggio esatto di case nel training set e una descrizione dettagliata dei risultati.</span><span class="sxs-lookup"><span data-stu-id="1a2fd-128">It displays the exact count of cases in the training data set, as well as a breakdown of the outcomes.</span></span>  
  
     <span data-ttu-id="1a2fd-129">È possibile visualizzare le stesse informazioni in una descrizione comando se si posiziona il mouse su un nodo.</span><span class="sxs-lookup"><span data-stu-id="1a2fd-129">You can view the same information in a tooltip if you pause the mouse over a node.</span></span>  
  
2.  <span data-ttu-id="1a2fd-130">Fare clic sui segni più e meno accanto a ogni nodo per espandere o comprimere l'albero.</span><span class="sxs-lookup"><span data-stu-id="1a2fd-130">Click the plus and minus signs next to each node to expand or collapse the tree.</span></span>  
  
     <span data-ttu-id="1a2fd-131">È anche possibile usare il dispositivo di scorrimento **Mostra livello** per espandere o ridurre l'albero.</span><span class="sxs-lookup"><span data-stu-id="1a2fd-131">You can also use the **Show Level** slider to expand or shrink the tree.</span></span>  
  
3.  <span data-ttu-id="1a2fd-132">Si noti che alcuni nodi sono più scuri di altri.</span><span class="sxs-lookup"><span data-stu-id="1a2fd-132">Notice that some nodes are darker than others?</span></span>  
  
     <span data-ttu-id="1a2fd-133">Per impostazione predefinita, la **popolazione** viene utilizzata come variabile ombreggiatura, il che significa che l'intensità del colore mostra quali nodi hanno il maggior supporto.</span><span class="sxs-lookup"><span data-stu-id="1a2fd-133">By default, **Population** is used as the shading variable, which means that the intensity of the color shows you which nodes have the most support.</span></span>  
  
     <span data-ttu-id="1a2fd-134">Pertanto il nodo più a sinistra è il più scuro perché contiene l'intero set di dati.</span><span class="sxs-lookup"><span data-stu-id="1a2fd-134">Therefore the leftmost node is darkest, because it contains the entire dataset.</span></span>  
  
4.  <span data-ttu-id="1a2fd-135">Modificare il valore di **background** da **tutti i case** in **Sì**.</span><span class="sxs-lookup"><span data-stu-id="1a2fd-135">Change the value for **Background** from **All Cases** to **Yes**.</span></span>  
  
     <span data-ttu-id="1a2fd-136">![modifica del grafico dell'albero delle decisioni per evidenziare gli acquirenti](media/dm13-dectreeshadedbuyer.gif "modifica del grafico dell'albero delle decisioni per evidenziare gli acquirenti")</span><span class="sxs-lookup"><span data-stu-id="1a2fd-136">![changing decision tree graph to highlight buyers](media/dm13-dectreeshadedbuyer.gif "changing decision tree graph to highlight buyers")</span></span>  
  
5.  <span data-ttu-id="1a2fd-137">Ora l'intensità del colore indica quanti clienti in ogni nodo hanno acquistato una bicicletta, che rappresenta il comportamento di interesse.</span><span class="sxs-lookup"><span data-stu-id="1a2fd-137">Now the intensity of the color tells you how many customers in each node purchased a bike, which is the behavior you are interested in.</span></span>  
  
     <span data-ttu-id="1a2fd-138">Si notino le barre colorate all'interno di ogni nodo.</span><span class="sxs-lookup"><span data-stu-id="1a2fd-138">Notice the colored bars within each node.</span></span> <span data-ttu-id="1a2fd-139">Si tratta di un istogramma in cui è illustrata la distribuzione dei risultati all'interno di questo subset di dati.</span><span class="sxs-lookup"><span data-stu-id="1a2fd-139">This is a histogram that shows the distribution of outcomes within this subset of data.</span></span> <span data-ttu-id="1a2fd-140">Nell'albero delle decisioni di Sample Bike Buyer, ad esempio, la barra colorata Mostra la percentuale di clienti che hanno acquistato biciclette (sì valori) rispetto a quelli che non hanno (nessun valore).</span><span class="sxs-lookup"><span data-stu-id="1a2fd-140">For example, in the sample Bike Buyer decision tree, the colored bar shows the proportion of customers who bought bikes (Yes values) vs. those who did not (No values).</span></span> <span data-ttu-id="1a2fd-141">Per ottenere i valori esatti, è possibile fare clic sul nodo e visualizzare **Legenda data mining**.</span><span class="sxs-lookup"><span data-stu-id="1a2fd-141">To get the exact values, you can click the node and view the **Mining Legend**.</span></span>  
  
6.  <span data-ttu-id="1a2fd-142">Seguendo il grafico, è possibile vedere come ogni subset di dati è ulteriormente scomposto in gruppi più piccoli e quali attributi sono più utili per la stima di un risultato.</span><span class="sxs-lookup"><span data-stu-id="1a2fd-142">By following the graph, you can see how each subset of data is further decomposed into smaller groups, and which attributes are most useful in predicting an outcome.</span></span>  
  
     <span data-ttu-id="1a2fd-143">Esaminando solo l'intensità dell'ombreggiatura, è possibile concentrarsi su un paio di gruppi di interesse e ottenere dati più dettagliati su di essi per il confronto.</span><span class="sxs-lookup"><span data-stu-id="1a2fd-143">Just by looking at the intensity of the shading, you can focus on a couple groups of interest, and get more detailed data on them for comparison.</span></span> <span data-ttu-id="1a2fd-144">Ad esempio, questi gruppi hanno una probabilità piuttosto elevata di acquistare biciclette:</span><span class="sxs-lookup"><span data-stu-id="1a2fd-144">For example, these groups have a fairly high probability of buying bikes:</span></span>  
  
    -   <span data-ttu-id="1a2fd-145">Age >= 32 e \< 53 and Yearly Income > = 26000 e Children = 0</span><span class="sxs-lookup"><span data-stu-id="1a2fd-145">Age >= 32 and \< 53 and Yearly Income >= 26000 and Children = 0</span></span>  
  
         <span data-ttu-id="1a2fd-146">Case totali: 1150</span><span class="sxs-lookup"><span data-stu-id="1a2fd-146">Total cases: 1150</span></span>  
  
         <span data-ttu-id="1a2fd-147">Probabilità per gli acquirenti di biciclette: 18%</span><span class="sxs-lookup"><span data-stu-id="1a2fd-147">Bike buyer probability: 18%</span></span>  
  
    -   <span data-ttu-id="1a2fd-148">Age >= 32 e \< 53 and Yearly Income > = 26000 e Children not = 0 e coniuge status =' single '</span><span class="sxs-lookup"><span data-stu-id="1a2fd-148">Age >= 32 and \< 53 and Yearly Income >= 26000 and Children not = 0 and Marital Status = 'Single'</span></span>  
  
         <span data-ttu-id="1a2fd-149">Totale dei case: 402</span><span class="sxs-lookup"><span data-stu-id="1a2fd-149">Total cases: 402</span></span>  
  
         <span data-ttu-id="1a2fd-150">Probabilità Bike Buyer: 16%</span><span class="sxs-lookup"><span data-stu-id="1a2fd-150">Bike buyer probability: 16%</span></span>  
  
7.  <span data-ttu-id="1a2fd-151">Modificare il valore di **background** da **Yes** a **No** e vedere come viene modificato il grafico.</span><span class="sxs-lookup"><span data-stu-id="1a2fd-151">Change the value for **Background** from **Yes** to **No** and see how the graph changes.</span></span>  
  
     <span data-ttu-id="1a2fd-152">![Grafico della rete di dipendenze per un modello di associazione](media/dm13-dec-tree-background-no.gif "Grafico della rete di dipendenze per un modello di associazione")</span><span class="sxs-lookup"><span data-stu-id="1a2fd-152">![Dependency network graph for an association model](media/dm13-dec-tree-background-no.gif "Dependency network graph for an association model")</span></span>  
  
 <span data-ttu-id="1a2fd-153">**Suggerimenti**</span><span class="sxs-lookup"><span data-stu-id="1a2fd-153">**Tips**</span></span>  
  
-   <span data-ttu-id="1a2fd-154">Se i dati possono essere suddivisi in più serie, viene compilato un modello diverso per ogni set di dati che si desidera modellare.</span><span class="sxs-lookup"><span data-stu-id="1a2fd-154">If your data can be divided into multiple series, a different model is built for each set of data that you want to model.</span></span>  
  
-   <span data-ttu-id="1a2fd-155">Nel modello di dati di esempio, è presente un solo risultato stimabile-Bike Buyer, ma si supponga di avere informazioni sul fatto che il cliente abbia acquistato un piano di servizio e voglia prevedere anche questo.</span><span class="sxs-lookup"><span data-stu-id="1a2fd-155">In the sample data model, there is only one predictable outcome - Bike Buyer - but suppose you had information about whether the customer purchased a service plan and wanted to predict that as well.</span></span> <span data-ttu-id="1a2fd-156">In questo caso si disporrebbe di tali dati in una colonna separata e si includerebbero due attributi stimabili nel modello.</span><span class="sxs-lookup"><span data-stu-id="1a2fd-156">In that case you would have that data in a separate column, and include two predictable attributes in the model.</span></span>  
  
     <span data-ttu-id="1a2fd-157">Fare clic sull'opzione **istogramma** nell'angolo superiore sinistro del riquadro dell'albero delle decisioni per modificare il numero massimo di Stati che possono essere visualizzati negli istogrammi dell'albero.</span><span class="sxs-lookup"><span data-stu-id="1a2fd-157">Click the **Histogram** option, in the upper left corner of the Decision Tree pane, to change the maximum number of states that can appear in the histograms in the tree.</span></span> <span data-ttu-id="1a2fd-158">Tale opzione è utile se l'attributo stimabile include molti stati.</span><span class="sxs-lookup"><span data-stu-id="1a2fd-158">This is useful if the predictable attribute has many states.</span></span> <span data-ttu-id="1a2fd-159">Gli stati vengono visualizzati in un istogramma in ordine di diffusione da sinistra a destra.</span><span class="sxs-lookup"><span data-stu-id="1a2fd-159">The states appear in a histogram in order of popularity from left to right.</span></span>  
  
-   <span data-ttu-id="1a2fd-160">È inoltre possibile utilizzare le opzioni della scheda **albero delle decisioni** per influire sulla modalità di visualizzazione dell'albero, eseguendo lo zoom avanti o indietro o ridimensionando il grafico per adattarlo alla finestra.</span><span class="sxs-lookup"><span data-stu-id="1a2fd-160">You can also use the options on the **Decision Tree** tab to affect how the tree is displayed, by zooming in or out, or sizing the graph to fit the window.</span></span>  
  
-   <span data-ttu-id="1a2fd-161">Per impostare il numero predefinito di livelli visualizzati per tutti gli alberi del modello, usare **Espansione predefinita** .</span><span class="sxs-lookup"><span data-stu-id="1a2fd-161">Use **Default Expansion** to set the default number of levels that are displayed for all trees in the model.</span></span>  
  
-   <span data-ttu-id="1a2fd-162">Selezionare **Mostra nome lungo** per visualizzare il nome completo dell'attributo, inclusa l'origine dati.</span><span class="sxs-lookup"><span data-stu-id="1a2fd-162">Select **Show long name** to display the full name of the attribute, including the data source.</span></span> <span data-ttu-id="1a2fd-163">Il nome breve e il nome lungo coincidono a meno che i case non vengano recuperati da un'origine dati diversa da quella degli attributi per ogni case.</span><span class="sxs-lookup"><span data-stu-id="1a2fd-163">Short names and long names are the same unless your cases are obtained from a different data source than the attributes for each case.</span></span>  
  
 [<span data-ttu-id="1a2fd-164">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="1a2fd-164">Back To Top</span></span>](#bkmk_Top)  
  
###  <a name="dependency-network"></a><a name="BKMK_DNetwork"></a><span data-ttu-id="1a2fd-165">Rete di dipendenze</span><span class="sxs-lookup"><span data-stu-id="1a2fd-165">Dependency Network</span></span>  
 <span data-ttu-id="1a2fd-166">Nella visualizzazione **rete di dipendenze** vengono visualizzate le connessioni tra gli attributi di input e gli attributi stimabili nel modello.</span><span class="sxs-lookup"><span data-stu-id="1a2fd-166">The **Dependency Network** view displays the connections between the input attributes and the predictable attributes in the model.</span></span>  
  
1.  <span data-ttu-id="1a2fd-167">Fare clic e trascinare il dispositivo di scorrimento a sinistra del visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="1a2fd-167">Click and drag the slider at the left of the viewer</span></span>  
  
     <span data-ttu-id="1a2fd-168">Nella posizione in alto vengono visualizzate tutte le connessioni.</span><span class="sxs-lookup"><span data-stu-id="1a2fd-168">At the top position, all connections are shown.</span></span> <span data-ttu-id="1a2fd-169">Quando si trascina il dispositivo di scorrimento verso il basso, nel visualizzatore vengono visualizzati solo i collegamenti più attendibili.</span><span class="sxs-lookup"><span data-stu-id="1a2fd-169">When you drag the slider down, only the strongest links are shown in the viewer.</span></span>  
  
2.  <span data-ttu-id="1a2fd-170">Fare quindi clic sul nodo Bike Buyer.</span><span class="sxs-lookup"><span data-stu-id="1a2fd-170">Now click the Bike Buyer node.</span></span>  
  
     <span data-ttu-id="1a2fd-171">![Vista della rete di dipendenze per gli alberi delle decisioni](media/dm13-dectree-depnet.gif "Vista della rete di dipendenze per gli alberi delle decisioni")</span><span class="sxs-lookup"><span data-stu-id="1a2fd-171">![Dependency network view for decision trees](media/dm13-dectree-depnet.gif "Dependency network view for decision trees")</span></span>  
  
     <span data-ttu-id="1a2fd-172">Quando si seleziona un nodo, nel visualizzatore vengono evidenziate le dipendenze specifiche del nodo.</span><span class="sxs-lookup"><span data-stu-id="1a2fd-172">When you select a node, the viewer highlights the dependencies that are specific to the node.</span></span> <span data-ttu-id="1a2fd-173">In questo caso, nel visualizzatore viene evidenziato ogni nodo che consente di stimare il risultato.</span><span class="sxs-lookup"><span data-stu-id="1a2fd-173">In this case, the viewer highlights each node that helps predict the outcome.</span></span>  
  
3.  <span data-ttu-id="1a2fd-174">Se il visualizzatore contiene molti nodi, è possibile cercare nodi specifici tramite il pulsante **Trova nodo** .</span><span class="sxs-lookup"><span data-stu-id="1a2fd-174">If the viewer contains many nodes, you can search for specific nodes by using the **Find Node** button.</span></span> <span data-ttu-id="1a2fd-175">Se si fa clic sul pulsante **Trova nodo** , verrà visualizzata la finestra di dialogo **Trova nodo** , che consente di cercare e selezionare nodi specifici mediante un filtro.</span><span class="sxs-lookup"><span data-stu-id="1a2fd-175">Clicking **Find Node** opens the **Find Node** dialog box, in which you can use a filter to search for and select specific nodes.</span></span>  
  
4.  <span data-ttu-id="1a2fd-176">La legenda nella parte inferiore del visualizzatore consente di individuare le corrispondenze tra i colori e i tipi di dipendenza rappresentati nel grafico.</span><span class="sxs-lookup"><span data-stu-id="1a2fd-176">The legend at the bottom of the viewer links color codes to the type of dependency in the graph.</span></span> <span data-ttu-id="1a2fd-177">Ad esempio, quando si seleziona un nodo stimabile, a quest'ultimo viene applicata un'ombreggiatura turchese mentre ai nodi utilizzati per la stima del nodo selezionato viene applicata un'ombreggiatura arancione.</span><span class="sxs-lookup"><span data-stu-id="1a2fd-177">For example, when you select a predictable node, the predictable node is shaded turquoise, and the nodes that predict the selected node are shaded orange.</span></span>  
  
 [<span data-ttu-id="1a2fd-178">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="1a2fd-178">Back To Top</span></span>](#bkmk_Top)  
  
### <a name="drill-through-to-underlying-data"></a><span data-ttu-id="1a2fd-179">Drill-through sui dati sottostanti</span><span class="sxs-lookup"><span data-stu-id="1a2fd-179">Drill through to Underlying Data</span></span>  
 <span data-ttu-id="1a2fd-180">Diversi tipi di modelli supportano la possibilità di *eseguire il drill-through* dal modello ai dati del case sottostanti.</span><span class="sxs-lookup"><span data-stu-id="1a2fd-180">Several types of models support the ability to *drill through* from the model to the underlying case data.</span></span> <span data-ttu-id="1a2fd-181">Ciò può risultare molto utile se si desidera contattare i clienti in un segmento specifico o estrarre i dati per eseguire un'ulteriore analisi.</span><span class="sxs-lookup"><span data-stu-id="1a2fd-181">This can be very useful if you want to contact customers in a particular segment or pull out the data to perform further analysis.</span></span>  
  
##### <a name="get-case-data"></a><span data-ttu-id="1a2fd-182">Recupero di dati dei case</span><span class="sxs-lookup"><span data-stu-id="1a2fd-182">Get case data</span></span>  
  
1.  <span data-ttu-id="1a2fd-183">Fare clic con il pulsante destro del mouse sul nodo dell'albero contenente i dati desiderati e selezionare una di queste opzioni:</span><span class="sxs-lookup"><span data-stu-id="1a2fd-183">Right-click the node in the tree that contains the desired data and select one of these options:</span></span>  
  
    -   <span data-ttu-id="1a2fd-184">**Modello drill-through**.</span><span class="sxs-lookup"><span data-stu-id="1a2fd-184">**Drill Through Model**.</span></span> <span data-ttu-id="1a2fd-185">Questa opzione consente di ottenere i case che appartengono al nodo selezionato e di salvarli in una tabella in Excel.</span><span class="sxs-lookup"><span data-stu-id="1a2fd-185">This option gets the cases that belong to the selected node, and saves them to a table in Excel.</span></span> <span data-ttu-id="1a2fd-186">È possibile tornare solo alle colonne dei dati utilizzati effettivamente nella compilazione del modello.</span><span class="sxs-lookup"><span data-stu-id="1a2fd-186">You get back only the columns of data that were actually used in building the model.</span></span>  
  
    -   <span data-ttu-id="1a2fd-187">**Colonne della struttura drill-through**.</span><span class="sxs-lookup"><span data-stu-id="1a2fd-187">**Drill Through Structure Columns**.</span></span> <span data-ttu-id="1a2fd-188">Questa opzione consente di ottenere i case che appartengono al nodo selezionato e di salvarli in una tabella in Excel.</span><span class="sxs-lookup"><span data-stu-id="1a2fd-188">This option gets the cases that belong to the selected node, and saves them to a table in Excel.</span></span> <span data-ttu-id="1a2fd-189">È possibile ottenere tutte le informazioni disponibili nei dati sottostanti al momento della compilazione, anche se nel modello non è stata usata una colonna.</span><span class="sxs-lookup"><span data-stu-id="1a2fd-189">You get all information that was available in the underlying data when you built it, even of a column wasn't used in the model.</span></span> <span data-ttu-id="1a2fd-190">Ad esempio, si potrebbe aver escluso l'indirizzo e il CAP del cliente in quanto tali campi non sono utili con l'analisi, ma sono stati lasciati nella struttura.</span><span class="sxs-lookup"><span data-stu-id="1a2fd-190">For example, you might have excluded the customer address and zip code because those fields are not useful with analysis, but left them in the structure.</span></span>  
  
     <span data-ttu-id="1a2fd-191">Tornare a Excel per visualizzare i dati.</span><span class="sxs-lookup"><span data-stu-id="1a2fd-191">Return to Excel to view your data.</span></span> <span data-ttu-id="1a2fd-192">Nel visualizzatore Sfoglia viene eseguita una query, vengono salvati i dati in una tabella in un nuovo foglio di lavoro e vengono etichettati i risultati.</span><span class="sxs-lookup"><span data-stu-id="1a2fd-192">The Browse viewer runs a query, saves the data to a table in a new worksheet, and labels the results.</span></span>  
  
     <span data-ttu-id="1a2fd-193">![risultati di drill-through salvati in Excel](media/dm13-dectree-drillthroughresults.gif "risultati di drill-through salvati in Excel")</span><span class="sxs-lookup"><span data-stu-id="1a2fd-193">![results of drillthrough are saved to Excel](media/dm13-dectree-drillthroughresults.gif "results of drillthrough are saved to Excel")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a2fd-194">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1a2fd-194">See Also</span></span>  
 [<span data-ttu-id="1a2fd-195">Esplorazione di modelli in Excel &#40;SQL Server componenti aggiuntivi Data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="1a2fd-195">Browsing Models in Excel &#40;SQL Server Data Mining Add-ins&#41;</span></span>](browsing-models-in-excel-sql-server-data-mining-add-ins.md)  
  
  
