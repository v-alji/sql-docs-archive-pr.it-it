---
title: Esplorazione di un modello di clustering | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining models, browsing
- mining models, viewing
- clustering [data mining]
- mining model, clustering
ms.assetid: 7f3f0949-d791-403a-88e2-54cb1a803dae
author: minewiskan
ms.author: owend
ms.openlocfilehash: f1d508603acd29fde981bddc5642b54ca9413f5f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625837"
---
# <a name="browsing-a-clustering-model"></a><span data-ttu-id="9daa5-102">Esplorazione di un modello di clustering</span><span class="sxs-lookup"><span data-stu-id="9daa5-102">Browsing a Clustering Model</span></span>
  <span data-ttu-id="9daa5-103">Quando si apre un modello di clustering utilizzando **Sfoglia**, il modello viene visualizzato in un visualizzatore interattivo, simile al visualizzatore clustering in [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9daa5-103">When you open a clustering model using **Browse**, the model is displayed in an interactive viewer, similar to the clustering viewer in [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="9daa5-104">Il visualizzatore consente di esplorare i cluster creati e comprenderne le caratteristiche.</span><span class="sxs-lookup"><span data-stu-id="9daa5-104">The viewer helps you explore the clusters that were created, and understand cluster characteristics.</span></span> <span data-ttu-id="9daa5-105">È inoltre possibile confrontare e contrapporre singoli segmenti con altri segmenti o con la popolazione.</span><span class="sxs-lookup"><span data-stu-id="9daa5-105">You can also compare and contrast individual segments with other segments or with the population.</span></span>  
  
##  <a name="explore-the-model"></a><a name="BKMK_Tabs"></a><span data-ttu-id="9daa5-106">Esplorare il modello</span><span class="sxs-lookup"><span data-stu-id="9daa5-106">Explore the Model</span></span>  
 <span data-ttu-id="9daa5-107">Nella finestra **Sfoglia** sono inclusi gli strumenti seguenti che consentono di comprendere il modello di clustering ed esplorare gli attributi dei gruppi di dati sottostanti:</span><span class="sxs-lookup"><span data-stu-id="9daa5-107">The **Browse** window includes the following tools to help you understand your clustering model and explore the attributes of the underlying data groups:</span></span>  
  
-   [<span data-ttu-id="9daa5-108">Diagramma dei cluster</span><span class="sxs-lookup"><span data-stu-id="9daa5-108">Cluster Diagram</span></span>](#BKMK_ClusterDiagram)  
  
-   [<span data-ttu-id="9daa5-109">Profili cluster</span><span class="sxs-lookup"><span data-stu-id="9daa5-109">Cluster Profiles</span></span>](#BKMK_ClusterProfiles)  
  
-   [<span data-ttu-id="9daa5-110">Caratteristiche del cluster</span><span class="sxs-lookup"><span data-stu-id="9daa5-110">Cluster Characteristics</span></span>](#BKMK_ClusterCharacteristics)  
  
-   [<span data-ttu-id="9daa5-111">Analisi discriminante tra cluster</span><span class="sxs-lookup"><span data-stu-id="9daa5-111">Cluster Discrimination</span></span>](#BKMK_ClusterDiscrimination)  
  
 <span data-ttu-id="9daa5-112">Per sperimentare un modello di clustering, è possibile utilizzare i dati di esempio nella scheda Training della cartella di lavoro dei dati di esempio e compilare un modello di clustering utilizzando la [creazione guidata cluster &#40;componenti aggiuntivi Data mining per Excel&#41;](cluster-wizard-data-mining-add-ins-for-excel.md) e tutte le impostazioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="9daa5-112">To experiment with a clustering model, you can use the sample data on the Training tab of the sample data workbook, and build a clustering model using [Cluster Wizard &#40;Data Mining Add-ins for Excel&#41;](cluster-wizard-data-mining-add-ins-for-excel.md) and all the defaults.</span></span>  
  
###  <a name="cluster-diagram"></a><a name="BKMK_ClusterDiagram"></a><span data-ttu-id="9daa5-113">Diagramma del cluster</span><span class="sxs-lookup"><span data-stu-id="9daa5-113">Cluster Diagram</span></span>  
 <span data-ttu-id="9daa5-114">Nella scheda **diagramma dei cluster** vengono visualizzati tutti i cluster presenti in un modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="9daa5-114">The **Cluster Diagram** tab displays all the clusters that are in a mining model.</span></span> <span data-ttu-id="9daa5-115">Di seguito è possibile visualizzare il numero di raggruppamenti differenti trovati nel set di dati e la posizione che occupano gli uni rispetto agli altri.</span><span class="sxs-lookup"><span data-stu-id="9daa5-115">Here you can see how many different groupings were found in your data set, and how near or far they are from each other.</span></span>  
  
##### <a name="explore-the-cluster-diagram"></a><span data-ttu-id="9daa5-116">Esplorazione del diagramma dei cluster</span><span class="sxs-lookup"><span data-stu-id="9daa5-116">Explore the cluster diagram</span></span>  
  
1.  <span data-ttu-id="9daa5-117">Fare clic su Cluster 1 nel diagramma.</span><span class="sxs-lookup"><span data-stu-id="9daa5-117">Click Cluster 1 in the diagram.</span></span>  
  
     <span data-ttu-id="9daa5-118">Si noti come le linee grigie che collegano tutti i cluster cambiano in modo che le linee che conducono al cluster selezionato vengano evidenziate in blu luminoso.</span><span class="sxs-lookup"><span data-stu-id="9daa5-118">Note how the gray lines connecting all clusters change so that lines leading to the selected cluster are highlighted in bright blue.</span></span>  
  
     <span data-ttu-id="9daa5-119">![Introduzione al diagramma dei cluster](media/dm13-cluster-diagram-intro.gif "Introduzione al diagramma dei cluster")</span><span class="sxs-lookup"><span data-stu-id="9daa5-119">![cluster diagram intro](media/dm13-cluster-diagram-intro.gif "cluster diagram intro")</span></span>  
  
     <span data-ttu-id="9daa5-120">L'intensità della linea che collega un cluster all'altro rappresenta il grado di somiglianza dei cluster.</span><span class="sxs-lookup"><span data-stu-id="9daa5-120">The intensity of the line that connects one cluster to another represents the strength of the similarity of the clusters.</span></span> <span data-ttu-id="9daa5-121">Se l'ombreggiatura è chiara o inesistente, il grado di somiglianza dei cluster è basso.</span><span class="sxs-lookup"><span data-stu-id="9daa5-121">If the shading is light or nonexistent, the clusters are not very similar.</span></span> <span data-ttu-id="9daa5-122">Man mano che la linea diventa più scura, il grado di somiglianza tra i due cluster aumenta.</span><span class="sxs-lookup"><span data-stu-id="9daa5-122">As the line becomes darker, it indicates that the similarity between the two clusters is stronger.</span></span>  
  
2.  <span data-ttu-id="9daa5-123">Fare clic e trascinare il dispositivo di scorrimento a sinistra del diagramma dei cluster per modificare il numero di linee visualizzate nel visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="9daa5-123">Click and drag the slider to the left of the cluster diagram, to adjust how many lines the viewer shows.</span></span>  
  
     <span data-ttu-id="9daa5-124">Quando si trascina il dispositivo di scorrimento verso il basso, vengono visualizzati solo i collegamenti più attendibili tra i cluster.</span><span class="sxs-lookup"><span data-stu-id="9daa5-124">When you drag the slider down, only the strongest links between clusters are shown.</span></span> <span data-ttu-id="9daa5-125">Ciò consente di concentrarsi sui gruppi correlati.</span><span class="sxs-lookup"><span data-stu-id="9daa5-125">This helps you focus on related groups.</span></span>  
  
3.  <span data-ttu-id="9daa5-126">Si noti il controllo **Variabile ombreggiatura** nell'angolo superiore destro della finestra **diagramma del cluster** .</span><span class="sxs-lookup"><span data-stu-id="9daa5-126">Notice the **Shading Variable** control in the upper right corner of the **Cluster Diagram** window.</span></span>  
  
     <span data-ttu-id="9daa5-127">Per impostazione predefinita, è impostato su **population**.</span><span class="sxs-lookup"><span data-stu-id="9daa5-127">By default, it is set to **Population**.</span></span> <span data-ttu-id="9daa5-128">Ciò significa che i cluster più scuri dispongono di maggiore supporto.</span><span class="sxs-lookup"><span data-stu-id="9daa5-128">What this means is that the darker clusters have greater support.</span></span>  
  
4.  <span data-ttu-id="9daa5-129">Posizionare il cursore del mouse su qualsiasi cluster.</span><span class="sxs-lookup"><span data-stu-id="9daa5-129">Pause over any cluster with the cursor.</span></span>  
  
     <span data-ttu-id="9daa5-130">Viene visualizzata una descrizione comando contenente la popolazione di tale cluster.</span><span class="sxs-lookup"><span data-stu-id="9daa5-130">A ToolTip is displayed that contains the population of that cluster.</span></span>  
  
5.  <span data-ttu-id="9daa5-131">A questo punto, fare clic sull'elenco a discesa **Variabile ombreggiatura** e scegliere la variabile **Age** .</span><span class="sxs-lookup"><span data-stu-id="9daa5-131">Now, click the **Shading Variable** dropdown list and choose the **Age** variable.</span></span> <span data-ttu-id="9daa5-132">A tale scopo, nella casella di testo **stato** verrà visualizzato un elenco di valori.</span><span class="sxs-lookup"><span data-stu-id="9daa5-132">As you do so, a list of values appears in the **State** text box.</span></span>  
  
     <span data-ttu-id="9daa5-133">Nella colonna Age utilizzata come input per questo modello sono contenuti valori numerici continui, ma ai fini del clustering, tramite l'algoritmo vengono sempre discretizzati i numeri.</span><span class="sxs-lookup"><span data-stu-id="9daa5-133">The Age column used as input to this model contains continuous numeric values, but for the purpose of clustering, the algorithm always discretizes numbers.</span></span> <span data-ttu-id="9daa5-134">Qui è possibile visualizzare i contenitori o i gruppi creati dall'algoritmo, ad esempio "molto basso ( \<=27)" and "Very High (> = 63)".</span><span class="sxs-lookup"><span data-stu-id="9daa5-134">Here you can see the bins, or groups that the algorithm created, such as "Very Low (\<=27)" and "Very High (>=63)".</span></span>  
  
6.  <span data-ttu-id="9daa5-135">Dagli elenchi a discesa **stato** selezionare **molto alta** e vedere come cambia il diagramma.</span><span class="sxs-lookup"><span data-stu-id="9daa5-135">From the **State** dropdown lists, select **Very High** and see how the diagram changes.</span></span>  
  
     <span data-ttu-id="9daa5-136">Modificando la variabile ombreggiatura, è possibile vedere immediatamente quali cluster contengono più clienti di questa fascia di età di destinazione e quali cluster contengono meno clienti in questa fascia di età.</span><span class="sxs-lookup"><span data-stu-id="9daa5-136">By changing the shading variable, you can see at a glance which clusters contain more of this targeted age group, and which clusters contain very few customers in this age group.</span></span>  
  
     <span data-ttu-id="9daa5-137">![Modificare il diagramma dei cluster per mostrare l'età](media/dm13-cluster-diagramshadebyage.gif "Modificare il diagramma dei cluster per mostrare l'età")</span><span class="sxs-lookup"><span data-stu-id="9daa5-137">![Modify the cluster diagram to show age](media/dm13-cluster-diagramshadebyage.gif "Modify the cluster diagram to show age")</span></span>  
  
     <span data-ttu-id="9daa5-138">Più scura è l'ombreggiatura, maggiore è la proporzione dell'attributo di destinazione e della distribuzione dei valori di tale cluster.</span><span class="sxs-lookup"><span data-stu-id="9daa5-138">The darker the shading, the larger the proportion of the target attribute and value distribution that cluster.</span></span>  
  
7.  <span data-ttu-id="9daa5-139">Individuare il cluster con ombreggiatura più scura quando la **Variabile ombreggiatura** è impostata su Age >65.</span><span class="sxs-lookup"><span data-stu-id="9daa5-139">Locate the cluster that is shaded darkest when the **Shading Variable** is set to Age >65.</span></span>  
  
     <span data-ttu-id="9daa5-140">Posizionare il mouse sul cluster.</span><span class="sxs-lookup"><span data-stu-id="9daa5-140">Hover the mouse over the cluster.</span></span>  
  
     <span data-ttu-id="9daa5-141">Il valore visualizzato nella descrizione comando ora mostra la popolazione di clienti contenuti in questo cluster maggiori di 65 anni.</span><span class="sxs-lookup"><span data-stu-id="9daa5-141">The value displayed in the ToolTip now shows you the population of customers in this cluster who are over 65.</span></span>  
  
8.  <span data-ttu-id="9daa5-142">Fare clic con il pulsante destro del mouse sul cluster e scegliere **Rinomina cluster**.</span><span class="sxs-lookup"><span data-stu-id="9daa5-142">Right-click the cluster and select **Rename Cluster**.</span></span> <span data-ttu-id="9daa5-143">Digitare un nuovo nome descrittivo, ad esempio **oltre 65**.</span><span class="sxs-lookup"><span data-stu-id="9daa5-143">Type a new name that is descriptive, such as **Over 65**.</span></span> <span data-ttu-id="9daa5-144">Il nuovo nome viene salvato con il modello nel server e può essere utilizzato per l'identificazione del cluster nelle altre viste di clustering.</span><span class="sxs-lookup"><span data-stu-id="9daa5-144">The new name is saved with the model to the server and can be used for identifying the cluster in the other clustering views.</span></span>  
  
 [<span data-ttu-id="9daa5-145">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="9daa5-145">Back To Top</span></span>](#BKMK_Tabs)  
  
###  <a name="cluster-profiles"></a><a name="BKMK_ClusterProfiles"></a><span data-ttu-id="9daa5-146">Profili cluster</span><span class="sxs-lookup"><span data-stu-id="9daa5-146">Cluster Profiles</span></span>  
 <span data-ttu-id="9daa5-147">La scheda **Profili cluster** consente di confrontare a colpo d'occhio la composizione di tutti i cluster.</span><span class="sxs-lookup"><span data-stu-id="9daa5-147">The **Cluster Profiles** tab lets you compare the makeup of all clusters at a glance.</span></span> <span data-ttu-id="9daa5-148">In questa scheda è possibile iniziare quando si sta acquisendo familiarità con il modello.</span><span class="sxs-lookup"><span data-stu-id="9daa5-148">This is a good place to start when you are getting familiar with the model.</span></span> <span data-ttu-id="9daa5-149">Questa vista è anche utile successivamente, se, dopo aver esplorato un cluster specifico, si stabilisce che è necessario trovare quelli correlati.</span><span class="sxs-lookup"><span data-stu-id="9daa5-149">This view is also useful later on, if you have been exploring a particular cluster and decide you need to find related ones.</span></span>  
  
 <span data-ttu-id="9daa5-150">I **Profili cluster** offrono anche una panoramica di come i cluster sono diversi tra loro.</span><span class="sxs-lookup"><span data-stu-id="9daa5-150">**Cluster Profiles** also gives you a good overview of how the clusters are different from each other.</span></span> <span data-ttu-id="9daa5-151">Di conseguenza, potrebbe risultare comodo utilizzare questa vista per assegnare a ogni cluster un nome descrittivo.</span><span class="sxs-lookup"><span data-stu-id="9daa5-151">Therefore, you might find it convenient to use this view to give each cluster a descriptive name.</span></span>  
  
##### <a name="explore-the-cluster-profiles"></a><span data-ttu-id="9daa5-152">Esplorazione del profili dei cluster</span><span class="sxs-lookup"><span data-stu-id="9daa5-152">Explore the cluster profiles</span></span>  
  
1.  <span data-ttu-id="9daa5-153">Fare clic sulla cella per le professioni, nella colonna **Stati** , per visualizzare l'elenco di tutti i valori per il lavoro.</span><span class="sxs-lookup"><span data-stu-id="9daa5-153">Click the cell for Occupations, in the **States** column, to see the list of all values for Occupation.</span></span>  
  
2.  <span data-ttu-id="9daa5-154">Ora spostare il cursore su Occupation nei profili dei cluster.</span><span class="sxs-lookup"><span data-stu-id="9daa5-154">Now move the cursor over Occupation in the cluster profiles.</span></span>  
  
     <span data-ttu-id="9daa5-155">Nella descrizione comando viene visualizzata la distribuzione di occupazioni in quel cluster.</span><span class="sxs-lookup"><span data-stu-id="9daa5-155">The ToolTip shows the distribution of occupations in that cluster.</span></span>  
  
     <span data-ttu-id="9daa5-156">![Visualizzare i valori dettagliati nelle descrizioni comandi o nella legenda](media/dm13-cluster-profile-age-tooltip.gif "Visualizzare i valori dettagliati nelle descrizioni comandi o nella legenda")</span><span class="sxs-lookup"><span data-stu-id="9daa5-156">![View detailed values in Tooltips or in Legend](media/dm13-cluster-profile-age-tooltip.gif "View detailed values in Tooltips or in Legend")</span></span>  
  
     <span data-ttu-id="9daa5-157">Si noti che, in alcuni cluster, ad esempio quello nell'immagine, l'elenco delle occupazioni non è completo e alcune occupazioni vengono sostituite con l'etichetta, **other**.</span><span class="sxs-lookup"><span data-stu-id="9daa5-157">Notice that, in some clusters (such as the one in the graphic), the list of occupations is not complete, and some occupations are replaced with the label, **Other**.</span></span>  
  
     <span data-ttu-id="9daa5-158">Ciò avviene per motivi strutturali poiché può essere difficile capire la differenza tra molte piccole barre in un istogramma.</span><span class="sxs-lookup"><span data-stu-id="9daa5-158">This is by design, because it can be hard to tell the difference between many small bars in a histogram.</span></span> <span data-ttu-id="9daa5-159">Per impostazione predefinita vengono mantenute solo le barre di importanza più alta e le barre rimanenti vengono raggruppate in un **altro** bucket grigio.</span><span class="sxs-lookup"><span data-stu-id="9daa5-159">By default only the bars of highest importance are retained, and the remaining bars are grouped together into a gray **Other** bucket.</span></span>  
  
     <span data-ttu-id="9daa5-160">Per modificare il numero di barre visibili in qualsiasi istogramma, usare l'opzione **Barre istogramma**.</span><span class="sxs-lookup"><span data-stu-id="9daa5-160">To change the number of bars that are visible in any histogram, use the option **Histogram bars**.</span></span>  
  
3.  <span data-ttu-id="9daa5-161">Si noti che la colonna **Age** ha un aspetto diverso dagli altri.</span><span class="sxs-lookup"><span data-stu-id="9daa5-161">Note that the **Age** column looks different from the others.</span></span> <span data-ttu-id="9daa5-162">Fare clic sul rombo nel grafico utilizzato per rappresentare Age.</span><span class="sxs-lookup"><span data-stu-id="9daa5-162">Click the diamond in the chart used to represent Age.</span></span>  
  
     <span data-ttu-id="9daa5-163">Nella colonna Age originalmente erano contenuti solo numeri continui.</span><span class="sxs-lookup"><span data-stu-id="9daa5-163">The column Age originally contained only continuous numbers.</span></span> <span data-ttu-id="9daa5-164">Per l'algoritmo di clustering sono richiesti valori discreti, pertanto vengono raggruppati i valori numerici nella colonna Age in un numero limitato di fasce di età, in base alla distribuzione di valori.</span><span class="sxs-lookup"><span data-stu-id="9daa5-164">The clustering algorithm requires discrete values, so it grouped the numeric values in the Age column into a limited number of age groups, based on the distribution of values.</span></span>  
  
4.  <span data-ttu-id="9daa5-165">Fare clic su uno dei grafici a rombo in un profilo di cluster.</span><span class="sxs-lookup"><span data-stu-id="9daa5-165">Click one of the diamond charts in a cluster profile.</span></span>  
  
     <span data-ttu-id="9daa5-166">Questi grafici a rombi vengono visualizzati solo quando nei dati di origine si utilizzano valori numerici continui.</span><span class="sxs-lookup"><span data-stu-id="9daa5-166">These diamond charts are displayed only when the source data uses continuous numeric values.</span></span> <span data-ttu-id="9daa5-167">Nei grafici a rombi vengono fornite alcune statistiche descrittive utili, inclusa la deviazione media e standard per tale valore in ogni cluster:</span><span class="sxs-lookup"><span data-stu-id="9daa5-167">The diamond charts provide some useful descriptive statistics, including the mean and standard deviation for that value in each cluster:</span></span>  
  
    -   <span data-ttu-id="9daa5-168">La linea nel grafico a rombi rappresenta l'intervallo di valori per l'attributo.</span><span class="sxs-lookup"><span data-stu-id="9daa5-168">The line in the diamond chart represents the range of values for the attribute.</span></span> <span data-ttu-id="9daa5-169">I valori vengono visualizzati anche nella colonna **Stati** a sinistra del grafico dei **profili** .</span><span class="sxs-lookup"><span data-stu-id="9daa5-169">The values are also shown in the **States** column at the left of the **Profiles** chart.</span></span>  
  
    -   <span data-ttu-id="9daa5-170">Il centro del rombo è posizionato in corrispondenza della media del nodo.</span><span class="sxs-lookup"><span data-stu-id="9daa5-170">The center of the diamond is positioned at the mean for the node.</span></span>  
  
    -   <span data-ttu-id="9daa5-171">La larghezza del rombo rappresenta la varianza dell'attributo in corrispondenza di quel nodo.</span><span class="sxs-lookup"><span data-stu-id="9daa5-171">The width of the diamond represents the variance of the attribute at that node.</span></span> <span data-ttu-id="9daa5-172">Pertanto, un rombo con spessore minore indica che il nodo può creare una stima più accurata.</span><span class="sxs-lookup"><span data-stu-id="9daa5-172">Therefore, a thinner diamond indicates that the node can create a more accurate prediction.</span></span>  
  
5.  <span data-ttu-id="9daa5-173">Per creare più spazio nel grafico, fare clic con il pulsante destro del mouse su un cluster che non è necessario visualizzare immediatamente e selezionare **Nascondi colonna**.</span><span class="sxs-lookup"><span data-stu-id="9daa5-173">To make more room in the graph, right-click a cluster you don't need to view right away, and select **Hide Column**.</span></span> <span data-ttu-id="9daa5-174">Questa operazione non viene eliminata dal modello, ma la colonna viene compressa temporaneamente.</span><span class="sxs-lookup"><span data-stu-id="9daa5-174">This doesn't delete it from the model, just collapses the column temporarily.</span></span>  
  
     <span data-ttu-id="9daa5-175">Per visualizzare i cluster nascosti, è possibile fare clic e trascinare il bordo della colonna oppure selezionare il nome del cluster dall'elenco, **più cluster**.</span><span class="sxs-lookup"><span data-stu-id="9daa5-175">To view clusters that you've hidden, you can click and drag the column edge, or select the cluster name from the list, **More clusters**.</span></span>  
  
6.  <span data-ttu-id="9daa5-176">Scorrere verso il basso l'elenco di attributi fino a visualizzare Bike Buyer, quindi individuare il cluster con la percentuale più elevata di valori Sì.</span><span class="sxs-lookup"><span data-stu-id="9daa5-176">Scroll down the attribute list till you find Bike Buyer, and then find the cluster that has the highest percentage of Yes values.</span></span>  
  
     <span data-ttu-id="9daa5-177">Fare clic con il pulsante destro del mouse sull'intestazione di colonna per il cluster che si desidera rinominare, selezionare **Rinomina cluster**e digitare **Bike Buyers**.</span><span class="sxs-lookup"><span data-stu-id="9daa5-177">Right-click the column heading for the cluster that you want to rename, select **Rename cluster**, and type **Bike Buyers**.</span></span>  
  
     <span data-ttu-id="9daa5-178">Il nuovo nome del cluster è persistente in tutte le viste e nel server, fino a quando non si rielabora il modello.</span><span class="sxs-lookup"><span data-stu-id="9daa5-178">The new cluster name is persisted in all views, and on the server, until you reprocess the model.</span></span>  
  
     <span data-ttu-id="9daa5-179">![Rinominare i cluster per rendere il grafico più semplice da usare](media/dm13-cluster-rename.gif "Rinominare i cluster per rendere il grafico più semplice da usare")</span><span class="sxs-lookup"><span data-stu-id="9daa5-179">![Rename clusters to make chart easier to use](media/dm13-cluster-rename.gif "Rename clusters to make chart easier to use")</span></span>  
  
 <span data-ttu-id="9daa5-180">**Suggerimenti**</span><span class="sxs-lookup"><span data-stu-id="9daa5-180">**Tips**</span></span>  
  
-   <span data-ttu-id="9daa5-181">Fare clic su un'intestazione di colonna per disporre gli attributi in ordine di importanza per il cluster.</span><span class="sxs-lookup"><span data-stu-id="9daa5-181">Click a column heading to sort the attributes in order of importance for that cluster.</span></span>  
  
-   <span data-ttu-id="9daa5-182">Trascinare le colonne per riordinarle nel visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="9daa5-182">Drag columns to reorder them in the viewer.</span></span>  
  
-   <span data-ttu-id="9daa5-183">Fare clic su una cella del grafico profili per visualizzare le statistiche dettagliate in **Legenda data mining**.</span><span class="sxs-lookup"><span data-stu-id="9daa5-183">Click any cell in the profiles chart to view detailed statistics in the **Mining Legend**.</span></span>  
  
-   <span data-ttu-id="9daa5-184">Fare clic con il pulsante destro del mouse su una cella e selezionare **colonne modello drill-through** per restituire i dati sottostanti in un nuovo foglio di lavoro di Excel</span><span class="sxs-lookup"><span data-stu-id="9daa5-184">Right-click any cell and select **Drillthrough model columns** to output the underlying data to a new worksheet in Excel.</span></span>  
  
-   <span data-ttu-id="9daa5-185">Fare clic con il pulsante destro del mouse sull'intestazione di colonna del cluster e selezionare **drill-through per strutturare i dati** per ottenere informazioni dettagliate sui membri del cluster non inclusi nel modello.</span><span class="sxs-lookup"><span data-stu-id="9daa5-185">Right-click the cluster's column heading and select **Drillthrough to structure data** to get detailed information about the cluster members that wasn't included in the model.</span></span>  
  
     <span data-ttu-id="9daa5-186">Se, ad esempio, si esegue la profilatura dei clienti, è possibile lasciare le informazioni di contatto nei dati sottostanti, ovvero la struttura di data mining, ma non includerle nel modello, perché non è utile per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="9daa5-186">For example, if you are profiling customers, you might leave the contact information in the underlying data (the mining structure) but not include it in the model, because it's not useful for analysis.</span></span> <span data-ttu-id="9daa5-187">Tuttavia, dopo che i clienti sono stati assegnati ai cluster, è possibile visualizzare i dati dettagliati tramite il drill-through.</span><span class="sxs-lookup"><span data-stu-id="9daa5-187">However, after customers have been assigned to clusters, you can view the detailed data by using drillthrough.</span></span>  
  
 [<span data-ttu-id="9daa5-188">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="9daa5-188">Back To Top</span></span>](#BKMK_Tabs)  
  
###  <a name="cluster-characteristics"></a><a name="BKMK_ClusterCharacteristics"></a> <span data-ttu-id="9daa5-189">Caratteristiche cluster</span><span class="sxs-lookup"><span data-stu-id="9daa5-189">Cluster Characteristics</span></span>  
 <span data-ttu-id="9daa5-190">La vista Caratteristiche cluster consente di esplorare realmente un singolo cluster per trovare gli attributi che caratterizzano più fortemente questo gruppo di dati.</span><span class="sxs-lookup"><span data-stu-id="9daa5-190">The Cluster Characteristics view lets you really explore a single cluster, to find which attributes most strongly characterize this group of data.</span></span>  
  
##### <a name="explore-the-cluster-characteristics"></a><span data-ttu-id="9daa5-191">Esplorazione delle caratteristiche del cluster</span><span class="sxs-lookup"><span data-stu-id="9daa5-191">Explore the cluster characteristics</span></span>  
  
1.  <span data-ttu-id="9daa5-192">Selezionare il cluster **Over 65** dall'elenco **cluster** .</span><span class="sxs-lookup"><span data-stu-id="9daa5-192">Select the **Over 65** cluster from the **Cluster** list.</span></span>  
  
     <span data-ttu-id="9daa5-193">Dopo aver selezionato un cluster, è possibile visualizzare nel dettaglio le caratteristiche del cluster specifico.</span><span class="sxs-lookup"><span data-stu-id="9daa5-193">After you select a cluster, you can see in detail the characteristics that make up that specific cluster.</span></span>  
  
     <span data-ttu-id="9daa5-194">Gli attributi contenuti nel cluster sono elencati nelle colonne **Variabili** , mentre lo stato di ogni attributo è elencato nella colonna **Valori** .</span><span class="sxs-lookup"><span data-stu-id="9daa5-194">The attributes that the cluster contains are listed in the **Variables** columns, and the state of the listed attribute is listed in the **Values** column.</span></span>  
  
     <span data-ttu-id="9daa5-195">Gli Stati degli attributi sono elencati in ordine di importanza, accompagnati dalla relativa probabilità in questo cluster, rappresentati come una barra colorata nella colonna **probabilità** .</span><span class="sxs-lookup"><span data-stu-id="9daa5-195">Attribute states are listed in order of importance, accompanied by their probability in this cluster, represented as a colored bar in the **Probability** column.</span></span>  
  
     <span data-ttu-id="9daa5-196">![Caratteristiche di un modello di clustering](media/dm13-cluster-characteristics.gif "Caratteristiche di un modello di clustering")</span><span class="sxs-lookup"><span data-stu-id="9daa5-196">![Characteristics of a clustering model](media/dm13-cluster-characteristics.gif "Characteristics of a clustering model")</span></span>  
  
2.  <span data-ttu-id="9daa5-197">Fare clic sulla colonna **variabili** per eseguire l'ordinamento in base all'attributo.</span><span class="sxs-lookup"><span data-stu-id="9daa5-197">Click the **Variables** column to sort by attribute.</span></span>  
  
     <span data-ttu-id="9daa5-198">Modificando la variabile di ordinamento, è possibile vedere più facilmente come i valori per le variabili, ad esempio il reddito o la proprietà di un'automobile, vengono distribuiti nel gruppo.</span><span class="sxs-lookup"><span data-stu-id="9daa5-198">By changing the sort variable, you can more easily see how values for variables such as income or car ownership are distributed in the group.</span></span>  
  
3.  <span data-ttu-id="9daa5-199">Fare clic su **copia in Excel**.</span><span class="sxs-lookup"><span data-stu-id="9daa5-199">Click **Copy to Excel**.</span></span>  
  
     <span data-ttu-id="9daa5-200">Un nuovo foglio di lavoro viene aggiunto alla cartella di lavoro contenente le caratteristiche del cluster selezionato.</span><span class="sxs-lookup"><span data-stu-id="9daa5-200">A new worksheet is added to your workbook that contains the characteristics of the selected cluster.</span></span>  
  
4.  <span data-ttu-id="9daa5-201">A questo punto, scegliere un cluster diverso dall'elenco **Bike Buyers**.</span><span class="sxs-lookup"><span data-stu-id="9daa5-201">Now choose a different cluster from the list, **Bike Buyers**.</span></span>  
  
5.  <span data-ttu-id="9daa5-202">Fare clic su **copia in Excel**.</span><span class="sxs-lookup"><span data-stu-id="9daa5-202">Click **Copy to Excel**.</span></span>  
  
     <span data-ttu-id="9daa5-203">Si noti che il grafico delle caratteristiche del nuovo cluster viene aggiunto al relativo foglio di lavoro.</span><span class="sxs-lookup"><span data-stu-id="9daa5-203">Note that the new cluster characteristics chart is added on its own worksheet.</span></span> <span data-ttu-id="9daa5-204">È possibile spostarlo nello stesso foglio di un altro profilo per semplificarne il confronto, operazione che verrà eseguita nel passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="9daa5-204">You can move it onto the same worksheet as the other profile to make it easier to compare them, which you'll do in the next step.</span></span>  
  
 <span data-ttu-id="9daa5-205">**Suggerimenti**</span><span class="sxs-lookup"><span data-stu-id="9daa5-205">**Tips**</span></span>  
  
-   <span data-ttu-id="9daa5-206">Si noti che la caratteristica principale del cliente nel cluster over 65 è che non acquistano il prodotto.</span><span class="sxs-lookup"><span data-stu-id="9daa5-206">Note that the primary characteristic of the customer in the Over 65 cluster is that they don't buy your product!</span></span> <span data-ttu-id="9daa5-207">Se si desidera saperne il motivo, è possibile esplorare i cluster e confrontare i gruppi o si potrebbe creare un modello correlato utilizzando un algoritmo che sia in grado di esplorare cause e risultati, ad esempio un modello di albero delle decisioni o un modello Naïve Bayes.</span><span class="sxs-lookup"><span data-stu-id="9daa5-207">If you want to know why this is so, you can browse clusters and compare groups, or you might create a related model using an algorithm that is good at exploring causes and outcomes, such as a decision tree model or a Naïve Bayes model.</span></span>  
  
-   <span data-ttu-id="9daa5-208">Se si desidera ottenere un elenco completo di attributi e probabilità per questo cluster (o tutti i cluster), è possibile creare una query.</span><span class="sxs-lookup"><span data-stu-id="9daa5-208">If you want to get a complete list of attributes and probabilities for this cluster (or all clusters) you can create a query.</span></span> <span data-ttu-id="9daa5-209">Per esempi di query sui modelli di clustering, vedere [esempi di query sul modello di clustering](data-mining/clustering-model-query-examples.md).</span><span class="sxs-lookup"><span data-stu-id="9daa5-209">For examples of queries on clustering models, see [Clustering Model Query Examples](data-mining/clustering-model-query-examples.md).</span></span>  
  
 [<span data-ttu-id="9daa5-210">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="9daa5-210">Back To Top</span></span>](#BKMK_Tabs)  
  
###  <a name="cluster-discrimination"></a><a name="BKMK_ClusterDiscrimination"></a><span data-ttu-id="9daa5-211">Analisi discriminante cluster</span><span class="sxs-lookup"><span data-stu-id="9daa5-211">Cluster Discrimination</span></span>  
 <span data-ttu-id="9daa5-212">Utilizzare la scheda analisi **discriminante tra cluster** per confrontare gli attributi tra due cluster o tra un cluster e tutti gli altri case del set di dati.</span><span class="sxs-lookup"><span data-stu-id="9daa5-212">You use the **Cluster Discrimination** tab to compare attributes between two clusters, or between a cluster and all the other cases in the data set.</span></span>  
  
 <span data-ttu-id="9daa5-213">Per evidenziare le funzionalità di questo visualizzatore, viene confrontato con le tabelle affiancate in Excel create in base alla visualizzazione delle **caratteristiche del cluster** .</span><span class="sxs-lookup"><span data-stu-id="9daa5-213">To highlight the features of this viewer, we'll compare it to the side-by-side tables in Excel that you created based on the **Cluster Characteristics** view.</span></span>  
  
##### <a name="explore-cluster-discrimination"></a><span data-ttu-id="9daa5-214">Esplorazione dell'analisi discriminante del cluster</span><span class="sxs-lookup"><span data-stu-id="9daa5-214">Explore cluster discrimination</span></span>  
  
1.  <span data-ttu-id="9daa5-215">Per selezionare i cluster da confrontare, usare gli elenchi **Cluster 1** e **Cluster 2** .</span><span class="sxs-lookup"><span data-stu-id="9daa5-215">Use the **Cluster 1** and **Cluster 2** lists to select the clusters to compare.</span></span>  
  
    -   <span data-ttu-id="9daa5-216">Per Cluster 1, selezionare Oltre 65.</span><span class="sxs-lookup"><span data-stu-id="9daa5-216">For Cluster 1, select Over 65.</span></span>  
  
    -   <span data-ttu-id="9daa5-217">Per Cluster 2, selezionare Bike Buyer.</span><span class="sxs-lookup"><span data-stu-id="9daa5-217">For Cluster 2, select Bike Buyers.</span></span>  
  
     <span data-ttu-id="9daa5-218">Il confronto dovrebbe essere simile a quello riportato nell'immagine seguente.</span><span class="sxs-lookup"><span data-stu-id="9daa5-218">The comparison should look similar to the following graphic.</span></span>  
  
     <span data-ttu-id="9daa5-219">![confronto dei cluster in un modello](media/dm13-cluster-compareclusters.gif "confronto dei cluster in un modello")</span><span class="sxs-lookup"><span data-stu-id="9daa5-219">![comparing clusters in a model](media/dm13-cluster-compareclusters.gif "comparing clusters in a model")</span></span>  
  
     <span data-ttu-id="9daa5-220">Si noti che, dietro le quinte, il Visualizzatore analisi **discriminante del cluster** invia query complesse al server data mining per estrarre gli attributi più importanti nella distinzione tra i due gruppi, semplificando il confronto di due set di clienti.</span><span class="sxs-lookup"><span data-stu-id="9daa5-220">Note that, under the covers, the **Cluster Discrimination** viewer sends complex queries to the data mining server, to extract the attributes that are most important in distinguishing between the two groups, making it easier to compare two sets of customers.</span></span>  
  
2.  <span data-ttu-id="9daa5-221">Fare clic su una delle colonne **predilige...** .</span><span class="sxs-lookup"><span data-stu-id="9daa5-221">Click either of the **Favors...** columns.</span></span>  
  
     <span data-ttu-id="9daa5-222">Nella barra a destra dell'elenco di valori e di attributi vengono visualizzati quali valori e funzionalità sono più importanti come caratteristica del cluster selezionato.</span><span class="sxs-lookup"><span data-stu-id="9daa5-222">The bar to the right of the attribute and value list shows which features or values are most important as a characteristic of the selected cluster.</span></span>  
  
3.  <span data-ttu-id="9daa5-223">Confrontare quindi gli elenchi in Excel.</span><span class="sxs-lookup"><span data-stu-id="9daa5-223">Now compare the lists in Excel.</span></span>  
  
     <span data-ttu-id="9daa5-224">![Grafico della rete di dipendenze per un modello di associazione](media/dm13-comparing-profiles-in-excel.gif "Grafico della rete di dipendenze per un modello di associazione")</span><span class="sxs-lookup"><span data-stu-id="9daa5-224">![Dependency network graph for an association model](media/dm13-comparing-profiles-in-excel.gif "Dependency network graph for an association model")</span></span>  
  
     <span data-ttu-id="9daa5-225">Poiché le statistiche sottostanti utilizzate per la compilazione dell'immagine nel visualizzatore vengono salvate in Excel come tabelle, è possibile filtrare, ordinare e visualizzare i valori effettivi di probabilità.</span><span class="sxs-lookup"><span data-stu-id="9daa5-225">Because the underlying statistics that were used to build the image in the viewer are saved to Excel as tables, you can filter and sort, and view the actual probability values.</span></span>  
  
     <span data-ttu-id="9daa5-226">Oltre a utilizzare Excel, è consigliabile provare il visualizzatore cluster per Visio, che consente non solo di visualizzare i punti dati ma anche di modificare e migliorare ampiamente il grafico.</span><span class="sxs-lookup"><span data-stu-id="9daa5-226">In addition to using Excel, we recommend that you try the cluster viewer for Visio, which also allows you to not just view data points but also extensively modify and enhance the graph.</span></span> <span data-ttu-id="9daa5-227">Per ulteriori informazioni, vedere la [procedura dettagliata relativa al diagramma dei Cluster &#40;componenti aggiuntivi Data Mining&#41;](cluster-diagram-walkthrough-data-mining-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="9daa5-227">For more information, see [Cluster Diagram Walkthrough &#40;Data Mining Add-ins&#41;](cluster-diagram-walkthrough-data-mining-add-ins.md).</span></span>  
  
 <span data-ttu-id="9daa5-228">**Suggerimenti**</span><span class="sxs-lookup"><span data-stu-id="9daa5-228">**Tips**</span></span>  
  
 <span data-ttu-id="9daa5-229">Una volta ottenute informazioni dettagliate sui gruppi di clienti, provare a utilizzare lo [scenario di simulazione &#40;strumenti di analisi tabelle per excel&#41;](what-if-scenario-table-analysis-tools-for-excel.md) o [uno scenario di ricerca obiettivo &#40;strumenti di analisi tabelle per Excel&#41;](goal-seek-scenario-table-analysis-tools-for-excel.md) strumenti, per esplorare i fattori del modello che potrebbero essere modificati per influire sul risultato.</span><span class="sxs-lookup"><span data-stu-id="9daa5-229">After getting some insights into groups of customers, try using the [What-If Scenario &#40;Table Analysis Tools for Excel&#41;](what-if-scenario-table-analysis-tools-for-excel.md) or [Goal Seek Scenario &#40;Table Analysis Tools for Excel&#41;](goal-seek-scenario-table-analysis-tools-for-excel.md) tools, to explore factors in the model that might be changed to affect the outcome.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9daa5-230">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9daa5-230">See Also</span></span>  
 <span data-ttu-id="9daa5-231">[Esplorazione di modelli in Excel &#40;SQL Server componenti aggiuntivi Data mining&#41;](browsing-models-in-excel-sql-server-data-mining-add-ins.md) </span><span class="sxs-lookup"><span data-stu-id="9daa5-231">[Browsing Models in Excel &#40;SQL Server Data Mining Add-ins&#41;](browsing-models-in-excel-sql-server-data-mining-add-ins.md) </span></span>  
 [<span data-ttu-id="9daa5-232">Creazione guidata cluster &#40;componenti aggiuntivi Data mining per Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="9daa5-232">Cluster Wizard &#40;Data Mining Add-ins for Excel&#41;</span></span>](cluster-wizard-data-mining-add-ins-for-excel.md)  
  
  
