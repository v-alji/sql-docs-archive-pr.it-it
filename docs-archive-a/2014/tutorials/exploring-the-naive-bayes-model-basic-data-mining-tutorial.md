---
title: Esplorazione del modello Naive Bayes (esercitazione di base sul data mining) | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: b06708d5-4477-4a51-bf8d-0b1e3c1f9ebb
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 7a26fa972e1ed50e2f4107026210a5935fcb86d8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719110"
---
# <a name="exploring-the-naive-bayes-model-basic-data-mining-tutorial"></a><span data-ttu-id="92e7c-102">Esplorazione del modello Naive Bayes (Esercitazione di base sul data mining)</span><span class="sxs-lookup"><span data-stu-id="92e7c-102">Exploring the Naive Bayes Model (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="92e7c-103">L' [!INCLUDE[msCoName](../includes/msconame-md.md)] algoritmo Naive Bayes offre diversi metodi per la visualizzazione dell'interazione tra l'acquisto di biciclette e gli attributi di input.</span><span class="sxs-lookup"><span data-stu-id="92e7c-103">The [!INCLUDE[msCoName](../includes/msconame-md.md)] Naive Bayes algorithm provides several methods for displaying the interaction between bike buying and the input attributes.</span></span>  
  
 <span data-ttu-id="92e7c-104">[!INCLUDE[msCoName](../includes/msconame-md.md)]Nel Visualizzatore Naive Bayes sono disponibili le schede seguenti da utilizzare per l'esplorazione dei modelli di data mining Naive Bayes:</span><span class="sxs-lookup"><span data-stu-id="92e7c-104">The [!INCLUDE[msCoName](../includes/msconame-md.md)] Naive Bayes Viewer provides the following tabs for use in exploring Naive Bayes mining models:</span></span>  
  
 
  
##  <a name="dependency-network"></a><a name="DependencyNetwork"></a><span data-ttu-id="92e7c-105">Rete di dipendenze</span><span class="sxs-lookup"><span data-stu-id="92e7c-105">Dependency Network</span></span>  
 <span data-ttu-id="92e7c-106">La scheda **rete di dipendenze** funziona in modo analogo alla scheda **rete di dipendenze** per il [!INCLUDE[msCoName](../includes/msconame-md.md)] Visualizzatore albero.</span><span class="sxs-lookup"><span data-stu-id="92e7c-106">The **Dependency Network** tab works in the same way as the **Dependency Network** tab for the [!INCLUDE[msCoName](../includes/msconame-md.md)] Tree Viewer.</span></span> <span data-ttu-id="92e7c-107">Ogni nodo nel visualizzatore rappresenta un attributo e le righe tra i nodi rappresentano le relazioni.</span><span class="sxs-lookup"><span data-stu-id="92e7c-107">Each node in the viewer represents an attribute, and the lines between nodes represent relationships.</span></span> <span data-ttu-id="92e7c-108">Nel visualizzatore è possibile osservare tutti gli attributi che influiscono sullo stato dell'attributo stimabile, ovvero Bike Buyer.</span><span class="sxs-lookup"><span data-stu-id="92e7c-108">In the viewer, you can see all the attributes that affect the state of the predictable attribute, Bike Buyer.</span></span>  
  
#### <a name="to-explore-the-model-in-the-dependency-network-tab"></a><span data-ttu-id="92e7c-109">Per esplorare il modello nella scheda Rete di dipendenze</span><span class="sxs-lookup"><span data-stu-id="92e7c-109">To explore the model in the Dependency Network tab</span></span>  
  
1.  <span data-ttu-id="92e7c-110">Utilizzare l'elenco **modello di data mining** nella parte superiore della scheda **Visualizzatore modello di data mining** per passare al `TM_NaiveBayes` modello.</span><span class="sxs-lookup"><span data-stu-id="92e7c-110">Use the **Mining Model** list at the top of the **Mining Model Viewer** tab to switch to the `TM_NaiveBayes` model.</span></span>  
  
2.  <span data-ttu-id="92e7c-111">Utilizzare l'elenco **Visualizzatore** per passare al **Visualizzatore Microsoft Naive Bayes**.</span><span class="sxs-lookup"><span data-stu-id="92e7c-111">Use the **Viewer** list to switch to **Microsoft Naive Bayes Viewer**.</span></span>  
  
3.  <span data-ttu-id="92e7c-112">Fare clic sul `Bike Buyer` nodo per identificarne le dipendenze.</span><span class="sxs-lookup"><span data-stu-id="92e7c-112">Click the `Bike Buyer` node to identify its dependencies.</span></span>  
  
     <span data-ttu-id="92e7c-113">L'ombreggiatura rosa indica che tutti gli attributi influenzano l'acquisto di biciclette.</span><span class="sxs-lookup"><span data-stu-id="92e7c-113">The pink shading indicates that all of the attributes have an effect on bike buying.</span></span>  
  
4.  <span data-ttu-id="92e7c-114">Regolare il dispositivo di scorrimento per identificare l'attributo più influente.</span><span class="sxs-lookup"><span data-stu-id="92e7c-114">Adjust the slider to identify the most influential attribute.</span></span>  
  
     <span data-ttu-id="92e7c-115">Spostando verso il basso il dispositivo di scorrimento rimangono visibili solo gli attributi che incidono maggiormente sulla colonna [Bike Buyer].</span><span class="sxs-lookup"><span data-stu-id="92e7c-115">As you lower the slider, only the attributes that have the greatest effect on the [Bike Buyer] column remain.</span></span> <span data-ttu-id="92e7c-116">Se si sposta il dispositivo di scorrimento è possibile individuare che alcuni degli attributi più influenti sono il numero di automobili possedute, la distanza dal luogo di lavoro e il numero complessivo di figli.</span><span class="sxs-lookup"><span data-stu-id="92e7c-116">By adjusting the slider, you can discover that a few of the most influential attributes are: number of cars owned, commute distance, and total number of children.</span></span>  
 
  
##  <a name="attribute-profiles"></a><a name="AttributeProfiles"></a> <span data-ttu-id="92e7c-117">Profili attributo</span><span class="sxs-lookup"><span data-stu-id="92e7c-117">Attribute Profiles</span></span>  
 <span data-ttu-id="92e7c-118">Nella scheda **Profili attributo** viene descritto il modo in cui diversi stati degli attributi di input influiscono sul risultato dell'attributo stimabile.</span><span class="sxs-lookup"><span data-stu-id="92e7c-118">The **Attribute Profiles** tab describes how different states of the input attributes affect the outcome of the predictable attribute.</span></span>  
  
#### <a name="to-explore-the-model-in-the-attribute-profiles-tab"></a><span data-ttu-id="92e7c-119">Per esplorare il modello nella scheda Profili attributo</span><span class="sxs-lookup"><span data-stu-id="92e7c-119">To explore the model in the Attribute Profiles tab</span></span>  
  
1.  <span data-ttu-id="92e7c-120">Nella casella **stimabile** verificare che `Bike Buyer` sia selezionato.</span><span class="sxs-lookup"><span data-stu-id="92e7c-120">In the **Predictable** box, verify that `Bike Buyer` is selected.</span></span>  
  
2.  <span data-ttu-id="92e7c-121">Se la **Legenda data mining** blocca la visualizzazione dei **Profili attributo**, spostarla all'esterno del percorso.</span><span class="sxs-lookup"><span data-stu-id="92e7c-121">If the **Mining Legend** is blocking display of the **Attribute profiles**, move it out of the way.</span></span>  
  
3.  <span data-ttu-id="92e7c-122">Nella casella barre **istogramma** selezionare **5**.</span><span class="sxs-lookup"><span data-stu-id="92e7c-122">In the **Histogram** bars box, select **5**.</span></span>  
  
     <span data-ttu-id="92e7c-123">Nel modello utilizzato in questo esempio 5 è il numero massimo di stati per ogni singola variabile.</span><span class="sxs-lookup"><span data-stu-id="92e7c-123">In our model, 5 is the maximum number of states for any one variable.</span></span>  
  
     <span data-ttu-id="92e7c-124">Gli attributi che influiscono sullo stato di questo attributo stimabile vengono elencati in combinazione con i valori di ogni stato degli attributi di input e la loro distribuzione in ogni stato dell'attributo stimabile.</span><span class="sxs-lookup"><span data-stu-id="92e7c-124">The attributes that affect the state of this predictable attribute are listed together with the values of each state of the input attributes and their distributions in each state of the predictable attribute.</span></span>  
  
4.  <span data-ttu-id="92e7c-125">Nella colonna **attributi** trovare il **numero di automobili possedute**.</span><span class="sxs-lookup"><span data-stu-id="92e7c-125">In the **Attributes** column, find **Number Cars Owned**.</span></span>  <span data-ttu-id="92e7c-126">Si notino le differenze negli istogrammi tra gli acquirenti di biciclette (la colonna con etichetta 1) e i non acquirenti (la colonna con etichetta 0).</span><span class="sxs-lookup"><span data-stu-id="92e7c-126">Notice the differences in the histograms for bike buyers (column labeled 1) and non-buyers (column labeled 0).</span></span> <span data-ttu-id="92e7c-127">È molto più probabile che una bicicletta venga acquistata da una persona priva di automobili o che ne possiede una sola.</span><span class="sxs-lookup"><span data-stu-id="92e7c-127">A person with zero or one car is much more likely to buy a bike.</span></span>  
  
5.  <span data-ttu-id="92e7c-128">Fare doppio clic sulla cella **numero Cars di proprietà** nella colonna Bike Buyer (colonna con etichetta 1).</span><span class="sxs-lookup"><span data-stu-id="92e7c-128">Double-click the **Number Cars Owned** cell in the bike buyer (column labeled 1) column.</span></span>  
  
     <span data-ttu-id="92e7c-129">In **Legenda data mining** viene visualizzata una visualizzazione più dettagliata.</span><span class="sxs-lookup"><span data-stu-id="92e7c-129">The **Mining Legend** displays a more detailed view.</span></span>  
  
  
##  <a name="attribute-characteristics"></a><a name="AttributeCharacteristics"></a><span data-ttu-id="92e7c-130">Caratteristiche degli attributi</span><span class="sxs-lookup"><span data-stu-id="92e7c-130">Attribute Characteristics</span></span>  
 <span data-ttu-id="92e7c-131">Con la scheda **Caratteristiche attributo** è possibile selezionare un attributo e un valore per vedere la frequenza con cui vengono visualizzati i valori per gli altri attributi nei case del valore selezionato.</span><span class="sxs-lookup"><span data-stu-id="92e7c-131">With the **Attribute Characteristics** tab, you can select an attribute and value to see how frequently values for other attributes appear in the selected value cases.</span></span>  
  
#### <a name="to-explore-the-model-in-the-attribute-characteristics-tab"></a><span data-ttu-id="92e7c-132">Per esplorare il modello nella scheda Caratteristiche attributo</span><span class="sxs-lookup"><span data-stu-id="92e7c-132">To explore the model in the Attribute Characteristics tab</span></span>  
  
1.  <span data-ttu-id="92e7c-133">Nell'elenco **attributo** verificare che `Bike Buyer` sia selezionato.</span><span class="sxs-lookup"><span data-stu-id="92e7c-133">In the **Attribute** list, verify that `Bike Buyer` is selected.</span></span>  
  
2.  <span data-ttu-id="92e7c-134">Impostare il **valore** su **1**.</span><span class="sxs-lookup"><span data-stu-id="92e7c-134">Set the **Value** to **1**.</span></span>  
  
     <span data-ttu-id="92e7c-135">Nel visualizzatore si osserverà che è più probabile che una bicicletta venga acquistata dai clienti senza figli, che abitano a breve distanza dal luogo di lavoro e che vivono nell'area dell'America del nord.</span><span class="sxs-lookup"><span data-stu-id="92e7c-135">In the viewer, you will see that customers who have no children at home, short commutes, and live in the North America region are more likely to buy a bike.</span></span>  
  
  
##  <a name="attribute-discrimination"></a><a name="AttributeDiscrimination"></a><span data-ttu-id="92e7c-136">Discriminazione degli attributi</span><span class="sxs-lookup"><span data-stu-id="92e7c-136">Attribute Discrimination</span></span>  
 <span data-ttu-id="92e7c-137">Con la scheda analisi **discriminante attributi** è possibile analizzare la relazione tra due valori discreti di acquisto di biciclette e altri valori di attributo.</span><span class="sxs-lookup"><span data-stu-id="92e7c-137">With the **Attribute Discrimination** tab, you can investigate the relationship between two discrete values of bike buying and other attribute values.</span></span> <span data-ttu-id="92e7c-138">Poiché il `TM_NaiveBayes` modello dispone solo di due Stati, 1 e 0, non è necessario apportare alcuna modifica al visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="92e7c-138">Because the `TM_NaiveBayes` model has only two states, 1 and 0, you do not have to make any changes to the viewer.</span></span>  
  
 <span data-ttu-id="92e7c-139">Nel visualizzatore è possibile osservare che le persone che non possiedono un'automobile tendenzialmente acquistano biciclette, mentre le persone che possiedono due automobili in genere non ne acquistano.</span><span class="sxs-lookup"><span data-stu-id="92e7c-139">In the viewer, you can see that people who do not own cars tend to buy bicycles, and people who own two cars tend not to buy bicycles.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="92e7c-140">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="92e7c-140">Related Tasks</span></span>  
 <span data-ttu-id="92e7c-141">Per esplorare gli altri modelli di data mining, vedere gli argomenti seguenti.</span><span class="sxs-lookup"><span data-stu-id="92e7c-141">See the following topics to explore the other mining models.</span></span>  
  
-   [<span data-ttu-id="92e7c-142">Esplorazione del modello Decision Trees &#40;esercitazione di base sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="92e7c-142">Exploring the Decision Tree Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-decision-tree-model-basic-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="92e7c-143">Esplorazione del modello di clustering &#40;esercitazione di base sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="92e7c-143">Exploring the Clustering Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-clustering-model-basic-data-mining-tutorial.md)  
  
## <a name="next-lesson"></a><span data-ttu-id="92e7c-144">Lezione successiva</span><span class="sxs-lookup"><span data-stu-id="92e7c-144">Next Lesson</span></span>  
 [<span data-ttu-id="92e7c-145">Lezione 5: Testing models &#40;esercitazione di base sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="92e7c-145">Lesson 5: Testing Models &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-5-testing-models-basic-data-mining-tutorial.md)  
  
## <a name="previous-task-in-lesson"></a><span data-ttu-id="92e7c-146">Attività precedente della lezione</span><span class="sxs-lookup"><span data-stu-id="92e7c-146">Previous Task in Lesson</span></span>  
 [<span data-ttu-id="92e7c-147">Esplorazione del modello di clustering &#40;esercitazione di base sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="92e7c-147">Exploring the Clustering Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-clustering-model-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="92e7c-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="92e7c-148">See Also</span></span>  
 <span data-ttu-id="92e7c-149">[Visualizzare un modello utilizzando il Visualizzatore Microsoft Naive Bayes](../../2014/analysis-services/data-mining/browse-a-model-using-the-microsoft-naive-bayes-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="92e7c-149">[Browse a Model Using the Microsoft Naive Bayes Viewer](../../2014/analysis-services/data-mining/browse-a-model-using-the-microsoft-naive-bayes-viewer.md) </span></span>  
 <span data-ttu-id="92e7c-150">[Scheda Analisi discriminante attributi &#40;Visualizzatore modello di data mining&#41;](../../2014/analysis-services/attribute-discrimination-tab-mining-model-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="92e7c-150">[Attribute Discrimination Tab &#40;Mining Model Viewer&#41;](../../2014/analysis-services/attribute-discrimination-tab-mining-model-viewer.md) </span></span>  
 <span data-ttu-id="92e7c-151">[Scheda Profili attributo &#40;Visualizzatore modello di data mining&#41;](../../2014/analysis-services/attribute-profiles-tab-mining-model-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="92e7c-151">[Attribute Profiles Tab &#40;Mining Model Viewer&#41;](../../2014/analysis-services/attribute-profiles-tab-mining-model-viewer.md) </span></span>  
 <span data-ttu-id="92e7c-152">[Scheda Caratteristiche attributo &#40;Visualizzatore modello di data mining&#41;](../../2014/analysis-services/attribute-characteristics-tab-mining-model-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="92e7c-152">[Attribute Characteristics Tab &#40;Mining Model Viewer&#41;](../../2014/analysis-services/attribute-characteristics-tab-mining-model-viewer.md) </span></span>  
 [<span data-ttu-id="92e7c-153">Scheda rete di dipendenze &#40;Visualizzatore modello di data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="92e7c-153">Dependency Network Tab &#40;Mining Model Viewer&#41;</span></span>](../../2014/analysis-services/dependency-network-tab-mining-model-viewer.md)  
  
  
