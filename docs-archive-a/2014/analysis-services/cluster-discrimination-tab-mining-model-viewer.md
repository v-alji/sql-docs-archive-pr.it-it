---
title: Scheda Analisi discriminante tra cluster (Visualizzatore modello di data mining) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.clustering.discrimination.f1
ms.assetid: ae7cfff7-ab1c-4cf5-9a91-97b21d15d85f
author: minewiskan
ms.author: owend
ms.openlocfilehash: 35435736bcdf1b1962de6babace2def953bbfff0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626395"
---
# <a name="cluster-discrimination-tab-mining-model-viewer"></a><span data-ttu-id="00312-102">Scheda Analisi discriminante tra cluster (Visualizzatore modello di data mining)</span><span class="sxs-lookup"><span data-stu-id="00312-102">Cluster Discrimination Tab (Mining Model Viewer)</span></span>
  <span data-ttu-id="00312-103">Usare la scheda **Analisi discriminante tra cluster** per confrontare due cluster esistenti in un modello di clustering.</span><span class="sxs-lookup"><span data-stu-id="00312-103">Use the **Cluster Discrimination** tab to compare two clusters that exist in a clustering model.</span></span> <span data-ttu-id="00312-104">È possibile vedere la modalità di rappresentazione di combinazioni diverse di attributi e valori all'interno dei cluster.</span><span class="sxs-lookup"><span data-stu-id="00312-104">You can see how different combinations of attributes and values are represented within the clusters.</span></span>  
  
 <span data-ttu-id="00312-105">**Per altre informazioni:** [Algoritmo Microsoft Clustering](data-mining/microsoft-clustering-algorithm.md), [Visualizzare un modello usando il Visualizzatore Microsoft Clustering](data-mining/browse-a-model-using-the-microsoft-cluster-viewer.md)</span><span class="sxs-lookup"><span data-stu-id="00312-105">**For More Information:** [Microsoft Clustering Algorithm](data-mining/microsoft-clustering-algorithm.md), [Browse a Model Using the Microsoft Cluster Viewer](data-mining/browse-a-model-using-the-microsoft-cluster-viewer.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="00312-106">Opzioni</span><span class="sxs-lookup"><span data-stu-id="00312-106">Options</span></span>  
 <span data-ttu-id="00312-107">**Aggiorna contenuto visualizzatore**</span><span class="sxs-lookup"><span data-stu-id="00312-107">**Refresh viewer content**</span></span>  
 <span data-ttu-id="00312-108">Consente di ricaricare il modello di data mining nel visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="00312-108">Reload the mining model in the viewer.</span></span>  
  
 <span data-ttu-id="00312-109">**Modello di data mining**</span><span class="sxs-lookup"><span data-stu-id="00312-109">**Mining Model**</span></span>  
 <span data-ttu-id="00312-110">Consente di scegliere un modello di data mining tra quelli presenti nella struttura di data mining corrente.</span><span class="sxs-lookup"><span data-stu-id="00312-110">Choose a mining model from those in the current mining structure.</span></span> <span data-ttu-id="00312-111">Il modello di data mining verrà aperto nel visualizzatore associato.</span><span class="sxs-lookup"><span data-stu-id="00312-111">The mining model will open in its associated viewer.</span></span>  
  
 <span data-ttu-id="00312-112">**Visualizzatore**</span><span class="sxs-lookup"><span data-stu-id="00312-112">**Viewer**</span></span>  
 <span data-ttu-id="00312-113">Consente di scegliere un visualizzatore da utilizzare per l'esplorazione del modello di data mining selezionato.</span><span class="sxs-lookup"><span data-stu-id="00312-113">Choose a viewer to use to explore the selected mining model.</span></span> <span data-ttu-id="00312-114">È possibile usare il visualizzatore personalizzato per i modelli di data mining o il Visualizzatore contenuto di data mining [!INCLUDE[msCoName](../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="00312-114">You can use the custom viewer for clustering models, or the [!INCLUDE[msCoName](../includes/msconame-md.md)] Mining Content Viewer.</span></span> <span data-ttu-id="00312-115">Se disponibili, è anche possibile utilizzare i visualizzatori plug-in.</span><span class="sxs-lookup"><span data-stu-id="00312-115">You can also use plug-in viewers if available.</span></span>  
  
 <span data-ttu-id="00312-116">**Cluster 1**</span><span class="sxs-lookup"><span data-stu-id="00312-116">**Cluster 1**</span></span>  
 <span data-ttu-id="00312-117">Consente di selezionare un cluster per poter confrontarlo con un altro cluster.</span><span class="sxs-lookup"><span data-stu-id="00312-117">Select a cluster, so that you can compare it to another cluster.</span></span>  
  
 <span data-ttu-id="00312-118">**Cluster 2**</span><span class="sxs-lookup"><span data-stu-id="00312-118">**Cluster 2**</span></span>  
 <span data-ttu-id="00312-119">Consente di selezionare un secondo cluster dal relativo elenco nel modello di data mining per il confronto con **Cluster 1**.</span><span class="sxs-lookup"><span data-stu-id="00312-119">Select a second cluster from the list of clusters in the mining model, to compare to **Cluster 1**.</span></span> <span data-ttu-id="00312-120">È inoltre possibile confrontare un cluster con il complemento, ovvero con tutti i case del modello eccetto quelli presenti nel cluster selezionato.</span><span class="sxs-lookup"><span data-stu-id="00312-120">You can also compare a cluster to its complement, meaning all cases in the model except those in the selected cluster.</span></span>  
  
 <span data-ttu-id="00312-121">**Punteggi discriminanti per \<cluster 1> e\<cluster 2>**</span><span class="sxs-lookup"><span data-stu-id="00312-121">**Discrimination scores for \<cluster 1> and \<cluster 2>**</span></span>  
 <span data-ttu-id="00312-122">Nelle colonne del grafico vengono fornite informazioni sulle modalità di correlazione tra ogni coppia attributo-valore e i due cluster selezionati.</span><span class="sxs-lookup"><span data-stu-id="00312-122">The columns in the graph provide information about how each attribute-value pair is related to the two selected clusters.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="00312-123">**Variabili**</span><span class="sxs-lookup"><span data-stu-id="00312-123">**Variables**</span></span>|<span data-ttu-id="00312-124">Un attributo nel modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="00312-124">An attribute in the mining model.</span></span>|  
|<span data-ttu-id="00312-125">**Valori**</span><span class="sxs-lookup"><span data-stu-id="00312-125">**Values**</span></span>|<span data-ttu-id="00312-126">Un valore dell'attributo selezionato in **Variabili**.</span><span class="sxs-lookup"><span data-stu-id="00312-126">A value of the attribute selected in **Variables**.</span></span>|  
|<span data-ttu-id="00312-127">**Predilige\<cluster 1>**</span><span class="sxs-lookup"><span data-stu-id="00312-127">**Favors \<cluster 1>**</span></span>|<span data-ttu-id="00312-128">Il grafico a barre a sinistra rappresenta la probabilità che la coppia attributo-valore selezionata sia rappresentativa del cluster selezionato in **Cluster 1**.</span><span class="sxs-lookup"><span data-stu-id="00312-128">The bar graph on the left represents the probability that the selected attribute-value pair is representative of the cluster selected in **Cluster 1**.</span></span> <span data-ttu-id="00312-129">È possibile posizionare il mouse sulla barra per vedere il valore rappresentato in percentuale.</span><span class="sxs-lookup"><span data-stu-id="00312-129">You can pause the mouse over the bar to see the value, represented as a percentage.</span></span> <span data-ttu-id="00312-130">Si noti che, anche se il valore è zero, non significa che il valore dell'attributo è necessariamente mancante dal cluster, solo che la distribuzione predilige fortemente un cluster rispetto all'altro.</span><span class="sxs-lookup"><span data-stu-id="00312-130">Note that even if the value is zero, it doesn't mean the attribute-value is necessarily missing from the cluster, just that the distribution strongly favors one cluster over the other.</span></span>|  
|<span data-ttu-id="00312-131">**Predilige\<cluster 2>**</span><span class="sxs-lookup"><span data-stu-id="00312-131">**Favors \<cluster 2>**</span></span>|<span data-ttu-id="00312-132">Il grafico a barre a destra rappresenta la probabilità che la coppia attributo-valore selezionata sia rappresentativa del cluster selezionato in **Cluster 2**.</span><span class="sxs-lookup"><span data-stu-id="00312-132">The bar graph on the right represents the probability that the selected attribute-value pair is representative of the cluster selected in **Cluster 2**.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="00312-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="00312-133">See Also</span></span>  
 <span data-ttu-id="00312-134">[Algoritmi di data mining &#40;Analysis Services-&#41;di data mining](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="00312-134">[Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="00312-135">[Visualizzatori modello di data mining &#40;Progettazione modelli di data mining&#41;](mining-model-viewers-data-mining-model-designer.md) </span><span class="sxs-lookup"><span data-stu-id="00312-135">[Mining Model Viewers &#40;Data Mining Model Designer&#41;](mining-model-viewers-data-mining-model-designer.md) </span></span>  
 [<span data-ttu-id="00312-136">Visualizzatori modello di data mining</span><span class="sxs-lookup"><span data-stu-id="00312-136">Data Mining Model Viewers</span></span>](data-mining/data-mining-model-viewers.md)  
  
  
