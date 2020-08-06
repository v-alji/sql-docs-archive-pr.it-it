---
title: Scheda Analisi discriminante tra cluster di Sequence Clustering (Visualizzatore modello di data mining) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.sequenceclustering.discrimination.f1
ms.assetid: 7dd16479-2633-4f4b-83bf-cf55972a2241
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9839a6185933fd87929331558ed63c1d81c6a748
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727204"
---
# <a name="sequence-clustering-cluster-discrimination-tab-mining-model-viewer"></a><span data-ttu-id="ac309-102">Scheda Analisi discriminante tra cluster di Sequence Clustering (Visualizzatore modello di data mining)</span><span class="sxs-lookup"><span data-stu-id="ac309-102">Sequence Clustering Cluster Discrimination Tab (Mining Model Viewer)</span></span>
  <span data-ttu-id="ac309-103">La scheda  **Analisi discriminante tra cluster** in **Visualizzatore Microsoft Sequence Clustering** consente di confrontare i cluster selezionati in un modello Sequence Clustering.</span><span class="sxs-lookup"><span data-stu-id="ac309-103">The  **Cluster Discrimination** tab in the **Microsoft Sequence Clustering Viewer** compares selected clusters from a sequence clustering model.</span></span>  
  
 <span data-ttu-id="ac309-104">Utilizzare questa vista di un modello Sequence Clustering per confrontare due cluster e vedere quali stati e transizioni sono diversi.</span><span class="sxs-lookup"><span data-stu-id="ac309-104">Use this view of a sequence clustering model to compare two clusters and see which states and transitions are different.</span></span>  
  
 <span data-ttu-id="ac309-105">**Per altre informazioni:** [Algoritmo Microsoft Sequence Clustering](data-mining/microsoft-sequence-clustering-algorithm.md), [Visualizzare un modello utilizzando il Visualizzatore Microsoft Sequence Clustering](data-mining/browse-a-model-using-the-microsoft-sequence-cluster-viewer.md)</span><span class="sxs-lookup"><span data-stu-id="ac309-105">**For More Information:** [Microsoft Sequence Clustering Algorithm](data-mining/microsoft-sequence-clustering-algorithm.md), [Browse a Model Using the Microsoft Sequence Cluster Viewer](data-mining/browse-a-model-using-the-microsoft-sequence-cluster-viewer.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="ac309-106">Opzioni</span><span class="sxs-lookup"><span data-stu-id="ac309-106">Options</span></span>  
 <span data-ttu-id="ac309-107">**Aggiorna contenuto visualizzatore**</span><span class="sxs-lookup"><span data-stu-id="ac309-107">**Refresh viewer content**</span></span>  
 <span data-ttu-id="ac309-108">Consente di ricaricare il modello di data mining nel visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="ac309-108">Reload the mining model in the viewer.</span></span>  
  
 <span data-ttu-id="ac309-109">**Modello di data mining**</span><span class="sxs-lookup"><span data-stu-id="ac309-109">**Mining Model**</span></span>  
 <span data-ttu-id="ac309-110">Fare clic su un modello di data mining da visualizzare contenuto nella struttura di data mining corrente.</span><span class="sxs-lookup"><span data-stu-id="ac309-110">Choose a mining model to view that is contained in the current mining structure.</span></span> <span data-ttu-id="ac309-111">Il modello di data mining verrà aperto nel visualizzatore associato.</span><span class="sxs-lookup"><span data-stu-id="ac309-111">The mining model will open in its associated viewer.</span></span>  
  
 <span data-ttu-id="ac309-112">**Visualizzatore**</span><span class="sxs-lookup"><span data-stu-id="ac309-112">**Viewer**</span></span>  
 <span data-ttu-id="ac309-113">Consente di scegliere un visualizzatore da utilizzare per l'esplorazione del modello di data mining selezionato.</span><span class="sxs-lookup"><span data-stu-id="ac309-113">Choose a viewer to use in exploring the selected mining model.</span></span> <span data-ttu-id="ac309-114">È possibile utilizzare il visualizzatore personalizzato o **Microsoft Generic Content Tree Viewer**.</span><span class="sxs-lookup"><span data-stu-id="ac309-114">You can use the custom viewer, or the **Microsoft Generic Content Tree Viewer**.</span></span> <span data-ttu-id="ac309-115">Se disponibili, è anche possibile utilizzare i visualizzatori plug-in.</span><span class="sxs-lookup"><span data-stu-id="ac309-115">You can also use plug-in viewers if available.</span></span>  
  
 <span data-ttu-id="ac309-116">**Cluster 1**</span><span class="sxs-lookup"><span data-stu-id="ac309-116">**Cluster 1**</span></span>  
 <span data-ttu-id="ac309-117">Consente di selezionare un cluster tra quelli presenti nel modello.</span><span class="sxs-lookup"><span data-stu-id="ac309-117">Select a cluster from those in the model.</span></span>  
  
 <span data-ttu-id="ac309-118">**Cluster 2**</span><span class="sxs-lookup"><span data-stu-id="ac309-118">**Cluster 2**</span></span>  
 <span data-ttu-id="ac309-119">Consente di selezionare un secondo cluster nel modello di data mining per il confronto con **Cluster 1**.</span><span class="sxs-lookup"><span data-stu-id="ac309-119">Select a second cluster in the mining model, to compare to **Cluster 1**.</span></span>  
  
 <span data-ttu-id="ac309-120">Se non si seleziona un altro cluster, per impostazione predefinita il cluster selezionato viene confrontato con il complemento, ovvero tutti i case nel modello che non sono presenti in Cluster 1.</span><span class="sxs-lookup"><span data-stu-id="ac309-120">If you do not select another cluster, by default the selected cluster is compared to its complement, meaning all cases in the model that are not in Cluster 1.</span></span>  
  
 <span data-ttu-id="ac309-121">**Punteggi discriminanti per \<cluster 1> e\<cluster 2>**</span><span class="sxs-lookup"><span data-stu-id="ac309-121">**Discrimination scores for \<cluster 1> and \<cluster 2>**</span></span>  
 <span data-ttu-id="ac309-122">In questo grafico è disponibile il confronto dettagliato tra i cluster selezionati.</span><span class="sxs-lookup"><span data-stu-id="ac309-122">This chart provides the detailed comparison of the clusters that you selected.</span></span> <span data-ttu-id="ac309-123">In generale, un modello di clustering consente raramente di assegnare stati o valori esclusivamente a un singolo cluster.</span><span class="sxs-lookup"><span data-stu-id="ac309-123">In general, a clustering model rarely assigns states or values exclusively to a single cluster.</span></span> <span data-ttu-id="ac309-124">Pertanto, il visualizzatore indica solo che un attributo o uno stato particolare *predilige* un determinato cluster.</span><span class="sxs-lookup"><span data-stu-id="ac309-124">Therefore, the viewer indicates only that a particular attribute or state *favors* a particular cluster.</span></span>  
  
 <span data-ttu-id="ac309-125">In generale, in un determinato cluster potrebbero essere contenuti più stati, ad esempio uno stato comune potrebbe essere l'acquisto in sequenza di una bottiglia di acqua e di un relativo contenitore.</span><span class="sxs-lookup"><span data-stu-id="ac309-125">Overall, a certain cluster might contain more of one state: for example, a common state might be the purchase of a Water Bottle and Water Bottle Cage in sequence.</span></span> <span data-ttu-id="ac309-126">Tuttavia, la sequenza potrebbe essere presente in altri cluster che dispongono di caratteristiche di definizione più importanti.</span><span class="sxs-lookup"><span data-stu-id="ac309-126">However, the sequence might be present in other clusters that have more important defining characteristics.</span></span> <span data-ttu-id="ac309-127">Ad esempio, un altro cluster potrebbe essere caratterizzato da tempi di transazione molto brevi e un'analisi rivelerebbe che gli elementi [Water Bottle e Water] sono posizionati in modo da essere raggruppati generalmente in questo cluster, ma non sempre.</span><span class="sxs-lookup"><span data-stu-id="ac309-127">For example, another cluster might be characterized most strongly by very short transaction times, and an analysis would reveal that [Water Bottle and Waterthe items are positioned to might usually be grouped in this cluster, but not always.</span></span>  
  
|<span data-ttu-id="ac309-128">Valore</span><span class="sxs-lookup"><span data-stu-id="ac309-128">Value</span></span>|<span data-ttu-id="ac309-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ac309-129">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ac309-130">**Variabili**</span><span class="sxs-lookup"><span data-stu-id="ac309-130">**Variables**</span></span>|<span data-ttu-id="ac309-131">Un attributo nel modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="ac309-131">An attribute in the mining model.</span></span>|  
|<span data-ttu-id="ac309-132">**Valori**</span><span class="sxs-lookup"><span data-stu-id="ac309-132">**Values**</span></span>|<span data-ttu-id="ac309-133">Uno stato dell'attributo contenuto nell'elenco **Variabili**.</span><span class="sxs-lookup"><span data-stu-id="ac309-133">A state of the attribute that is listed in **Variables**.</span></span>|  
|<span data-ttu-id="ac309-134">**Predilige\<cluster 1>**</span><span class="sxs-lookup"><span data-stu-id="ac309-134">**Favors \<cluster 1>**</span></span>|<span data-ttu-id="ac309-135">È contenuta una barra ombreggiata che indica il livello di predilezione dell'attributo e dello stato elencati in **Variabili** e **Valore** per il cluster selezionato in **Cluster 1**.</span><span class="sxs-lookup"><span data-stu-id="ac309-135">Contains a shaded bar that indicates how strongly the attribute and the state that are listed in **Variables** and **Value** favor the cluster that is selected in **Cluster 1**.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ac309-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ac309-136">See Also</span></span>  
 <span data-ttu-id="ac309-137">[Algoritmi di data mining &#40;Analysis Services-&#41;di data mining](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="ac309-137">[Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="ac309-138">[Visualizzatori modello di data mining &#40;Progettazione modelli di data mining&#41;](mining-model-viewers-data-mining-model-designer.md) </span><span class="sxs-lookup"><span data-stu-id="ac309-138">[Mining Model Viewers &#40;Data Mining Model Designer&#41;](mining-model-viewers-data-mining-model-designer.md) </span></span>  
 [<span data-ttu-id="ac309-139">Visualizzatori modello di data mining</span><span class="sxs-lookup"><span data-stu-id="ac309-139">Data Mining Model Viewers</span></span>](data-mining/data-mining-model-viewers.md)  
  
  
