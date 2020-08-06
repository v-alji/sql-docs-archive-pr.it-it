---
title: Esplorazione del modello di clustering (esercitazione di base sul data mining) | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: ce8aa034-161b-473f-baec-9c29e0a8e5f5
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: cca9d395fece59f607c8faf209128b9d32663a06
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726400"
---
# <a name="exploring-the-clustering-model-basic-data-mining-tutorial"></a><span data-ttu-id="f90b2-102">Esplorazione del modello di clustering (Esercitazione di base sul data mining)</span><span class="sxs-lookup"><span data-stu-id="f90b2-102">Exploring the Clustering Model (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="f90b2-103">L' [!INCLUDE[msCoName](../includes/msconame-md.md)] algoritmo di Clustering raggruppa i case in cluster che contengono caratteristiche simili.</span><span class="sxs-lookup"><span data-stu-id="f90b2-103">The [!INCLUDE[msCoName](../includes/msconame-md.md)] Clustering algorithm groups cases into clusters that contain similar characteristics.</span></span> <span data-ttu-id="f90b2-104">Tali raggruppamenti sono utili per l'esplorazione dei dati, l'identificazione delle relative anomalie e la creazione di stime.</span><span class="sxs-lookup"><span data-stu-id="f90b2-104">These groupings are useful for exploring data, identifying anomalies in the data, and creating predictions.</span></span>  
  
 <span data-ttu-id="f90b2-105">Per l'esplorazione di modelli di data mining per il clustering, nel Visualizzatore [!INCLUDE[msCoName](../includes/msconame-md.md)] Clustering sono disponibili le schede seguenti:</span><span class="sxs-lookup"><span data-stu-id="f90b2-105">The [!INCLUDE[msCoName](../includes/msconame-md.md)] Cluster Viewer provides the following tabs for use in exploring clustering mining models:</span></span>  
  

  
##  <a name="cluster-diagram-tab"></a><a name="ClusterDiagramTab"></a><span data-ttu-id="f90b2-106">Scheda Diagramma cluster</span><span class="sxs-lookup"><span data-stu-id="f90b2-106">Cluster Diagram Tab</span></span>  
 <span data-ttu-id="f90b2-107">Nella scheda Diagramma dei cluster vengono visualizzati tutti i cluster di un modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="f90b2-107">The Cluster Diagram tab displays all the clusters that are in a mining model.</span></span> <span data-ttu-id="f90b2-108">Le linee tra i cluster rappresentano la prossimità e appaiono ombreggiate in base al grado di analogia dei cluster.</span><span class="sxs-lookup"><span data-stu-id="f90b2-108">The lines between the clusters represent "closeness" and are shaded based on how similar the clusters are.</span></span> <span data-ttu-id="f90b2-109">Il colore effettivo dei cluster rappresenta la frequenza della variabile e lo stato nel cluster.</span><span class="sxs-lookup"><span data-stu-id="f90b2-109">The actual color of each cluster represents the frequency of the variable and the state in the cluster.</span></span>  
  
#### <a name="to-explore-the-model-in-the-cluster-diagram-tab"></a><span data-ttu-id="f90b2-110">Per esplorare il modello nella scheda Diagramma dei cluster</span><span class="sxs-lookup"><span data-stu-id="f90b2-110">To explore the model in the Cluster Diagram tab</span></span>  
  
1.  <span data-ttu-id="f90b2-111">Utilizzare l'elenco **modello di data mining** nella parte superiore della scheda **Visualizzatore modello di data mining** per passare al `TM_Clustering` modello.</span><span class="sxs-lookup"><span data-stu-id="f90b2-111">Use the **Mining Model** list at the top of the **Mining Model Viewer** tab to switch to the `TM_Clustering` model.</span></span>  
  
2.  <span data-ttu-id="f90b2-112">Nell'elenco **Visualizzatore** selezionare **Microsoft cluster Viewer**.</span><span class="sxs-lookup"><span data-stu-id="f90b2-112">In the **Viewer** list, select **Microsoft Cluster Viewer**.</span></span>  
  
3.  <span data-ttu-id="f90b2-113">Nella casella **Variabile ombreggiatura** selezionare **Bike Buyer**.</span><span class="sxs-lookup"><span data-stu-id="f90b2-113">In the **Shading Variable** box, select **Bike Buyer**.</span></span>  
  
     <span data-ttu-id="f90b2-114">La variabile predefinita è **population**, ma è possibile modificarla in qualsiasi attributo del modello, per individuare i cluster che contengono membri che hanno gli attributi desiderati.</span><span class="sxs-lookup"><span data-stu-id="f90b2-114">The default variable is **Population**, but you can change this to any attribute in the model, to discover which clusters contain members that have the attributes you want.</span></span>  
  
4.  <span data-ttu-id="f90b2-115">Selezionare **1** nella casella **stato** per esplorare i casi in cui è stata acquistata una bicicletta.</span><span class="sxs-lookup"><span data-stu-id="f90b2-115">Select **1** in the **State** box to explore those cases where a bike was purchased.</span></span>  
  
     <span data-ttu-id="f90b2-116">La legenda **densità** descrive la densità della coppia di stati degli attributi selezionata nella variabile ombreggiatura e nello stato.</span><span class="sxs-lookup"><span data-stu-id="f90b2-116">The **Density** legend describes the density of the attribute state pair selected in the Shading Variable and the State.</span></span> <span data-ttu-id="f90b2-117">In questo esempio viene indicato che clusterwith l'ombreggiatura più scura ha la percentuale più alta di acquirenti di biciclette.</span><span class="sxs-lookup"><span data-stu-id="f90b2-117">In this example it tells us that the clusterwith the darkest shading has the highest percentage of bike buyers.</span></span>  
  
5.  <span data-ttu-id="f90b2-118">Posizionare il mouse sul cluster con l'ombreggiatura più scura.</span><span class="sxs-lookup"><span data-stu-id="f90b2-118">Pause your mouse over the cluster with the darkest shading.</span></span>  
  
     <span data-ttu-id="f90b2-119">Nella descrizione comando verrà visualizzata la percentuale di case che includono l'attributo `Bike Buyer = 1`.</span><span class="sxs-lookup"><span data-stu-id="f90b2-119">A tooltip displays the percentage of cases that have the attribute, `Bike Buyer = 1`.</span></span>  
  
6.  <span data-ttu-id="f90b2-120">Selezionare il cluster con la densità più elevata, fare clic con il pulsante destro del mouse sul cluster, scegliere **Rinomina cluster** e digitare **Bike Buyers High** per identificarlo in seguito.</span><span class="sxs-lookup"><span data-stu-id="f90b2-120">Select the cluster that has the highest density, right-click the cluster, select **Rename Cluster** and type **Bike Buyers High** for later identification.</span></span> [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
7.  <span data-ttu-id="f90b2-121">Individuare il cluster con l'ombreggiatura più leggera (e la densità più bassa).</span><span class="sxs-lookup"><span data-stu-id="f90b2-121">Find the cluster that has the lightest shading (and the lowest density).</span></span> <span data-ttu-id="f90b2-122">Fare clic con il pulsante destro del mouse sul cluster, scegliere **Rinomina cluster** e digitare **Bike Buyers Low**.</span><span class="sxs-lookup"><span data-stu-id="f90b2-122">Right-click the cluster, select **Rename Cluster** and type **Bike Buyers Low**.</span></span> [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
8.  <span data-ttu-id="f90b2-123">Fare clic sul cluster **Bike Buyers High** e trascinarlo in un'area del riquadro che fornirà una visualizzazione chiara delle connessioni agli altri cluster.</span><span class="sxs-lookup"><span data-stu-id="f90b2-123">Click the **Bike Buyers High** cluster and drag it to an area of the pane that will give you a clear view of its connections to the other clusters.</span></span>  
  
     <span data-ttu-id="f90b2-124">Quando si seleziona un cluster, le linee che lo connettono agli altri cluster vengono evidenziate, in modo che sia possibile vedere facilmente tutte le relazioni del cluster.</span><span class="sxs-lookup"><span data-stu-id="f90b2-124">When you select a cluster, the lines that connect this cluster to other clusters are highlighted, so that you can easily see all the relationships for this cluster.</span></span> <span data-ttu-id="f90b2-125">Quando il cluster non è selezionato, dal colore delle linee è possibile dedurre il livello di relazione tra tutti i cluster del diagramma.</span><span class="sxs-lookup"><span data-stu-id="f90b2-125">When the cluster is not selected, you can tell by the darkness of the lines how strong the relationships are amongst all the clusters in the diagram.</span></span> <span data-ttu-id="f90b2-126">Se l'ombreggiatura è chiara o inesistente, il grado di somiglianza dei cluster è basso.</span><span class="sxs-lookup"><span data-stu-id="f90b2-126">If the shading is light or nonexistent, the clusters are not very similar.</span></span>  
  
9. <span data-ttu-id="f90b2-127">Utilizzare il dispositivo di scorrimento nella parte sinistra della rete per escludere i collegamenti meno attendibili e individuare i cluster con le relazioni più strette.</span><span class="sxs-lookup"><span data-stu-id="f90b2-127">Use the slider to the left of the network, to filter out the weaker links and find the clusters with the closest relationships.</span></span> <span data-ttu-id="f90b2-128">Il reparto marketing di [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] potrebbe ad esempio raggruppare i cluster simili durante l'individuazione del metodo migliore per inviare i mailing diretti.</span><span class="sxs-lookup"><span data-stu-id="f90b2-128">The [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] marketing department might want to combine similar clusters together when determining the best method for delivering the targeted mailing.</span></span>  
  

  
##  <a name="cluster-profiles-tab"></a><a name="ClusterProfilesTab"></a><span data-ttu-id="f90b2-129">Scheda Profili cluster</span><span class="sxs-lookup"><span data-stu-id="f90b2-129">Cluster Profiles Tab</span></span>  
 <span data-ttu-id="f90b2-130">La scheda **Profili cluster** fornisce una visualizzazione complessiva del `TM_Clustering` modello.</span><span class="sxs-lookup"><span data-stu-id="f90b2-130">The **Cluster Profiles** tab provides an overall view of the `TM_Clustering` model.</span></span> <span data-ttu-id="f90b2-131">La scheda **Profili cluster** contiene una colonna per ogni cluster nel modello.</span><span class="sxs-lookup"><span data-stu-id="f90b2-131">The **Cluster Profiles** tab contains a column for each cluster in the model.</span></span> <span data-ttu-id="f90b2-132">Nella prima colonna sono elencati gli attributi associati ad almeno un cluster.</span><span class="sxs-lookup"><span data-stu-id="f90b2-132">The first column lists the attributes that are associated with at least one cluster.</span></span> <span data-ttu-id="f90b2-133">La parte rimanente del visualizzatore contiene la distribuzione degli stati di un attributo per ogni cluster.</span><span class="sxs-lookup"><span data-stu-id="f90b2-133">The rest of the viewer contains the distribution of the states of an attribute for each cluster.</span></span> <span data-ttu-id="f90b2-134">La distribuzione di una variabile discreta viene visualizzata come una barra colorata con il numero massimo di barre visualizzate nell'elenco **Barre istogramma** .</span><span class="sxs-lookup"><span data-stu-id="f90b2-134">The distribution of a discrete variable is shown as a colored bar with the maximum number of bars displayed in the **Histogram bars** list.</span></span> <span data-ttu-id="f90b2-135">Gli attributi continui sono visualizzati sotto forma di un grafico a rombi che rappresenta la deviazione media e standard in ogni cluster.</span><span class="sxs-lookup"><span data-stu-id="f90b2-135">Continuous attributes are displayed with a diamond chart, which represents the mean and standard deviation in each cluster.</span></span>  
  
#### <a name="to-explore-the-model-in-the-cluster-profiles-tab"></a><span data-ttu-id="f90b2-136">Per esplorare il modello nella scheda Profili cluster</span><span class="sxs-lookup"><span data-stu-id="f90b2-136">To explore the model in the Cluster Profiles tab</span></span>  
  
1.  <span data-ttu-id="f90b2-137">Impostare le barre **istogramma** su **5**.</span><span class="sxs-lookup"><span data-stu-id="f90b2-137">Set **Histogram** bars to **5**.</span></span>  
  
     <span data-ttu-id="f90b2-138">Nel modello utilizzato in questo esempio 5 è il numero massimo di stati per ogni singola variabile.</span><span class="sxs-lookup"><span data-stu-id="f90b2-138">In our model, 5 is the maximum number of states for any one variable.</span></span>  
  
2.  <span data-ttu-id="f90b2-139">Se la **Legenda data mining** blocca la visualizzazione dei **Profili attributo**, spostarla all'esterno del percorso.</span><span class="sxs-lookup"><span data-stu-id="f90b2-139">If the **Mining Legend** blocks the display of the **Attribute profiles**, move it out of the way.</span></span>  
  
3.  <span data-ttu-id="f90b2-140">Selezionare la colonna **Bike Buyers High** e trascinarla a destra della colonna **popolazione** .</span><span class="sxs-lookup"><span data-stu-id="f90b2-140">Select the **Bike Buyers High** column and drag it to the right of the **Population** column.</span></span>  
  
4.  <span data-ttu-id="f90b2-141">Selezionare la colonna **Bike Buyers Low** e trascinarla a destra della colonna **Bike Buyers High** .</span><span class="sxs-lookup"><span data-stu-id="f90b2-141">Select the **Bike Buyers Low** column and drag it to the right of the **Bike Buyers High** column.</span></span>  
  
5.  <span data-ttu-id="f90b2-142">Fare clic sulla colonna **Bike Buyers High** .</span><span class="sxs-lookup"><span data-stu-id="f90b2-142">Click the **Bike Buyers High** column.</span></span>  
  
     <span data-ttu-id="f90b2-143">La colonna **variables** è ordinata in ordine di importanza per il cluster.</span><span class="sxs-lookup"><span data-stu-id="f90b2-143">The **Variables** column is sorted in order of importance for that cluster.</span></span> <span data-ttu-id="f90b2-144">Scorrere la colonna e verificare le caratteristiche del cluster Bike Buyers High.</span><span class="sxs-lookup"><span data-stu-id="f90b2-144">Scroll through the column and review characteristics of the Bike Buyer High cluster.</span></span> <span data-ttu-id="f90b2-145">È ad esempio più probabile che i clienti raggruppati in questo cluster abitino a breve distanza dal luogo di lavoro.</span><span class="sxs-lookup"><span data-stu-id="f90b2-145">For example, they are more likely to have a short commute.</span></span>  
  
6.  <span data-ttu-id="f90b2-146">Fare doppio clic sulla cella **Age** nella colonna **Bike Buyers High** .</span><span class="sxs-lookup"><span data-stu-id="f90b2-146">Double-click the **Age** cell in the **Bike Buyers High** column.</span></span>  
  
     <span data-ttu-id="f90b2-147">In **Legenda data mining** viene visualizzata una visualizzazione più dettagliata ed è possibile visualizzare l'intervallo di tempo di questi clienti, oltre alla durata media.</span><span class="sxs-lookup"><span data-stu-id="f90b2-147">The **Mining Legend** displays a more detailed view and you can see the age range of these customers as well as the mean age.</span></span>  
  
7.  <span data-ttu-id="f90b2-148">Fare clic con il pulsante destro del mouse sulla colonna **Bike Buyers Low** e selezionare **Nascondi colonna**.</span><span class="sxs-lookup"><span data-stu-id="f90b2-148">Right-click the **Bike Buyers Low** column and select **Hide Column**.</span></span>  
  

  
##  <a name="cluster-characteristics-tab"></a><a name="ClusterCharacteristicsTab"></a><span data-ttu-id="f90b2-149">Scheda Caratteristiche cluster</span><span class="sxs-lookup"><span data-stu-id="f90b2-149">Cluster Characteristics Tab</span></span>  
 <span data-ttu-id="f90b2-150">Con la scheda **Caratteristiche cluster** è possibile esaminare più in dettaglio le caratteristiche che costituiscono un cluster.</span><span class="sxs-lookup"><span data-stu-id="f90b2-150">With the **Cluster Characteristics** tab, you can examine in more detail the characteristics that make up a cluster.</span></span> <span data-ttu-id="f90b2-151">Anziché confrontare le caratteristiche di tutti i cluster (come nella scheda Profili cluster), è possibile esplorare un cluster alla volta.</span><span class="sxs-lookup"><span data-stu-id="f90b2-151">Instead of comparing the characteristics of all of the clusters (as in the Cluster Profiles tab), you can explore one cluster at a time.</span></span> <span data-ttu-id="f90b2-152">Ad esempio, se si seleziona **Bike Buyers High** dall'elenco **cluster** , è possibile visualizzare le caratteristiche dei clienti in questo cluster.</span><span class="sxs-lookup"><span data-stu-id="f90b2-152">For example, if you select **Bike Buyers High** from the **Cluster** list, you can see the characteristics of the customers in this cluster.</span></span> <span data-ttu-id="f90b2-153">Sebbene la visualizzazione sia diversa dalla scheda Profili cluster, i risultati sono gli stessi.</span><span class="sxs-lookup"><span data-stu-id="f90b2-153">Though the display is different from the Cluster Profiles viewer, the findings are the same.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f90b2-154">A meno che non si imposti un valore iniziale per **HoldoutSeed**, i risultati variano ogni volta che si elabora il modello.</span><span class="sxs-lookup"><span data-stu-id="f90b2-154">Unless you set an initial value for **holdoutseed**, results will vary each time you process the model.</span></span> <span data-ttu-id="f90b2-155">Per altre informazioni, vedere [elemento HoldoutSeed](https://docs.microsoft.com/bi-reference/assl/properties/holdoutseed-element)</span><span class="sxs-lookup"><span data-stu-id="f90b2-155">For more information, see [HoldoutSeed Element](https://docs.microsoft.com/bi-reference/assl/properties/holdoutseed-element)</span></span>  
  

  
##  <a name="cluster-discrimination-tab"></a><a name="ClusterDiscriminationTab"></a><span data-ttu-id="f90b2-156">Scheda Analisi discriminante tra cluster</span><span class="sxs-lookup"><span data-stu-id="f90b2-156">Cluster Discrimination Tab</span></span>  
 <span data-ttu-id="f90b2-157">Con la scheda analisi **discriminante tra cluster** è possibile esplorare le caratteristiche che distinguono un cluster da un altro.</span><span class="sxs-lookup"><span data-stu-id="f90b2-157">With the **Cluster Discrimination** tab, you can explore the characteristics that distinguish one cluster from another.</span></span> <span data-ttu-id="f90b2-158">Dopo aver selezionato due cluster, uno dall'elenco **cluster 1** e uno dall'elenco **cluster 2** , il Visualizzatore calcola le differenze tra i cluster e visualizza un elenco degli attributi che distinguono maggiormente i cluster.</span><span class="sxs-lookup"><span data-stu-id="f90b2-158">After you select two clusters, one from the **Cluster 1** list, and one from the **Cluster 2** list, the viewer calculates the differences between the clusters and displays a list of the attributes that distinguish the clusters most.</span></span>  
  
#### <a name="to-explore-the-model-in-the-cluster-discrimination-tab"></a><span data-ttu-id="f90b2-159">Per esplorare il modello nella scheda Analisi discriminante tra cluster</span><span class="sxs-lookup"><span data-stu-id="f90b2-159">To explore the model in the Cluster Discrimination tab</span></span>  
  
1.  <span data-ttu-id="f90b2-160">Nella casella **cluster 1** selezionare **Bike Buyers High**.</span><span class="sxs-lookup"><span data-stu-id="f90b2-160">In the **Cluster 1** box, select **Bike Buyers High**.</span></span>  
  
2.  <span data-ttu-id="f90b2-161">Nella casella **cluster 2** selezionare **Bike Buyers Low**.</span><span class="sxs-lookup"><span data-stu-id="f90b2-161">In the **Cluster 2** box, select **Bike Buyers Low**.</span></span>  
  
3.  <span data-ttu-id="f90b2-162">Fare clic su **variabili** per ordinare alfabeticamente.</span><span class="sxs-lookup"><span data-stu-id="f90b2-162">Click **Variables** to sort alphabetically.</span></span>  
  
     <span data-ttu-id="f90b2-163">Alcune delle differenze più sostanziali tra i clienti nei cluster **Bike Buyers Low** e Bike Buyers **High** includono Age, auto ownership, Number of Children e Region.</span><span class="sxs-lookup"><span data-stu-id="f90b2-163">Some of the more substantial differences among the customers in the **Bike Buyers Low** and **Bike Buyers High** clusters include age, car ownership, number of children, and region.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="f90b2-164">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="f90b2-164">Related Tasks</span></span>  
 <span data-ttu-id="f90b2-165">Per esplorare gli altri modelli di data mining, vedere gli argomenti seguenti.</span><span class="sxs-lookup"><span data-stu-id="f90b2-165">See the following topics to explore the other mining models.</span></span>  
  
-   [<span data-ttu-id="f90b2-166">Esplorazione del modello Decision Trees &#40;esercitazione di base sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="f90b2-166">Exploring the Decision Tree Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-decision-tree-model-basic-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="f90b2-167">Esplorazione del modello Naive Bayes &#40;esercitazione di base sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="f90b2-167">Exploring the Naive Bayes Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-naive-bayes-model-basic-data-mining-tutorial.md)  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="f90b2-168">Attività successiva della lezione</span><span class="sxs-lookup"><span data-stu-id="f90b2-168">Next Task in Lesson</span></span>  
 [<span data-ttu-id="f90b2-169">Esplorazione del modello Naive Bayes &#40;esercitazione di base sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="f90b2-169">Exploring the Naive Bayes Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-naive-bayes-model-basic-data-mining-tutorial.md)  
  
## <a name="previous-task-in-lesson"></a><span data-ttu-id="f90b2-170">Attività precedente della lezione</span><span class="sxs-lookup"><span data-stu-id="f90b2-170">Previous Task in Lesson</span></span>  
 [<span data-ttu-id="f90b2-171">Esplorazione del modello Decision Trees &#40;esercitazione di base sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="f90b2-171">Exploring the Decision Tree Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-decision-tree-model-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="f90b2-172">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f90b2-172">See Also</span></span>  
 <span data-ttu-id="f90b2-173">[Visualizzare un modello utilizzando il Visualizzatore Microsoft Clustering](../../2014/analysis-services/data-mining/browse-a-model-using-the-microsoft-cluster-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="f90b2-173">[Browse a Model Using the Microsoft Cluster Viewer](../../2014/analysis-services/data-mining/browse-a-model-using-the-microsoft-cluster-viewer.md) </span></span>  
 <span data-ttu-id="f90b2-174">[Scheda Analisi discriminante tra cluster &#40;Visualizzatore modello di data mining&#41;](../../2014/analysis-services/cluster-discrimination-tab-mining-model-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="f90b2-174">[Cluster Discrimination Tab &#40;Mining Model Viewer&#41;](../../2014/analysis-services/cluster-discrimination-tab-mining-model-viewer.md) </span></span>  
 <span data-ttu-id="f90b2-175">[Scheda Profili cluster &#40;Visualizzatore modello di data mining&#41;](../../2014/analysis-services/cluster-profiles-tab-mining-model-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="f90b2-175">[Cluster Profiles Tab &#40;Mining Model Viewer&#41;](../../2014/analysis-services/cluster-profiles-tab-mining-model-viewer.md) </span></span>  
 <span data-ttu-id="f90b2-176">[Scheda Caratteristiche cluster &#40;Visualizzatore modello di data mining&#41;](../../2014/analysis-services/cluster-characteristics-tab-mining-model-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="f90b2-176">[Cluster Characteristics Tab &#40;Mining Model Viewer&#41;](../../2014/analysis-services/cluster-characteristics-tab-mining-model-viewer.md) </span></span>  
 [<span data-ttu-id="f90b2-177">Scheda Diagramma cluster &#40;Visualizzatore modello di data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="f90b2-177">Cluster Diagram Tab &#40;Mining Model Viewer&#41;</span></span>](../../2014/analysis-services/cluster-diagram-tab-mining-model-viewer.md)  
  
  
