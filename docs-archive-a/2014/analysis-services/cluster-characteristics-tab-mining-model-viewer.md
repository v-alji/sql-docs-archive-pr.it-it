---
title: Scheda Caratteristiche cluster (Visualizzatore modello di data mining) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.clustering.characteristics.f1
ms.assetid: 8e33ed1d-1ce4-405d-895b-7e995b2c910d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 959d94767b6cb27d9ebb6e06c592034fca20ac89
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625771"
---
# <a name="cluster-characteristics-tab-mining-model-viewer"></a><span data-ttu-id="9a993-102">Scheda Caratteristiche cluster (Visualizzatore modello di data mining)</span><span class="sxs-lookup"><span data-stu-id="9a993-102">Cluster Characteristics Tab (Mining Model Viewer)</span></span>
  <span data-ttu-id="9a993-103">La scheda **Caratteristiche cluster** consente di esplorare le caratteristiche di un cluster in un modello di clustering o il set di tutti i case nel modello.</span><span class="sxs-lookup"><span data-stu-id="9a993-103">The **Cluster Characteristics** tab lets you explore the characteristics of a cluster in a clustering model, or the set of all cases in the model.</span></span> <span data-ttu-id="9a993-104">Nel grafico viene mostrata l'importanza di ogni coppia attributo-valore come caratteristica tramite cui viene definito il cluster rispetto agli altri cluster.</span><span class="sxs-lookup"><span data-stu-id="9a993-104">The graph shows the importance of each attribute-value pair as a characteristic that defines the cluster, in comparison with other clusters.</span></span>  
  
 <span data-ttu-id="9a993-105">**Per altre informazioni:** [Algoritmo Microsoft Clustering](data-mining/microsoft-clustering-algorithm.md), [Visualizzare un modello usando il Visualizzatore Microsoft Clustering](data-mining/browse-a-model-using-the-microsoft-cluster-viewer.md)</span><span class="sxs-lookup"><span data-stu-id="9a993-105">**For More Information:** [Microsoft Clustering Algorithm](data-mining/microsoft-clustering-algorithm.md), [Browse a Model Using the Microsoft Cluster Viewer](data-mining/browse-a-model-using-the-microsoft-cluster-viewer.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="9a993-106">Opzioni</span><span class="sxs-lookup"><span data-stu-id="9a993-106">Options</span></span>  
 <span data-ttu-id="9a993-107">**Aggiorna contenuto visualizzatore**</span><span class="sxs-lookup"><span data-stu-id="9a993-107">**Refresh viewer content**</span></span>  
 <span data-ttu-id="9a993-108">Consente di ricaricare il modello di data mining nel visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="9a993-108">Reload the mining model in the viewer.</span></span>  
  
 <span data-ttu-id="9a993-109">**Modello di data mining**</span><span class="sxs-lookup"><span data-stu-id="9a993-109">**Mining Model**</span></span>  
 <span data-ttu-id="9a993-110">Consente di scegliere un modello di data mining tra quelli presenti nella struttura di data mining corrente.</span><span class="sxs-lookup"><span data-stu-id="9a993-110">Choose a mining model from those in the current mining structure.</span></span> <span data-ttu-id="9a993-111">Il modello di data mining verrà aperto nel visualizzatore personalizzato.</span><span class="sxs-lookup"><span data-stu-id="9a993-111">The mining model will open in the custom viewer.</span></span>  
  
 <span data-ttu-id="9a993-112">**Visualizzatore**</span><span class="sxs-lookup"><span data-stu-id="9a993-112">**Viewer**</span></span>  
 <span data-ttu-id="9a993-113">Consente di scegliere un visualizzatore da utilizzare per l'esplorazione del modello di data mining selezionato.</span><span class="sxs-lookup"><span data-stu-id="9a993-113">Choose a viewer to use to explore the selected mining model.</span></span> <span data-ttu-id="9a993-114">È possibile usare il visualizzatore personalizzato associato a questo tipo di modello o il Visualizzatore contenuto di data mining [!INCLUDE[msCoName](../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9a993-114">You can use the custom viewer associated with this model type, or the [!INCLUDE[msCoName](../includes/msconame-md.md)] Mining Content Viewer.</span></span> <span data-ttu-id="9a993-115">Se disponibili, è anche possibile utilizzare i visualizzatori plug-in.</span><span class="sxs-lookup"><span data-stu-id="9a993-115">You can also use any plug-in viewers that are available.</span></span>  
  
 <span data-ttu-id="9a993-116">**Cluster**</span><span class="sxs-lookup"><span data-stu-id="9a993-116">**Cluster**</span></span>  
 <span data-ttu-id="9a993-117">Consente di scegliere il cluster da visualizzare o **Popolazione (Tutto)** per vedere la distribuzione degli attributi per l'intero modello.</span><span class="sxs-lookup"><span data-stu-id="9a993-117">Choose the cluster you want to view, or choose **Population (All)** to see the distribution of attributes for the model as a whole.</span></span>  
  
 <span data-ttu-id="9a993-118">**Caratteristiche per\<cluster>**</span><span class="sxs-lookup"><span data-stu-id="9a993-118">**Characteristics for \<cluster>**</span></span>  
 <span data-ttu-id="9a993-119">Nel grafico sono contenute le colonne seguenti in cui sono descritte le caratteristiche del cluster selezionato.</span><span class="sxs-lookup"><span data-stu-id="9a993-119">The graph contains the following columns, which describe the characteristics of the selected cluster.</span></span>  
  
|<span data-ttu-id="9a993-120">Valore</span><span class="sxs-lookup"><span data-stu-id="9a993-120">Value</span></span>|<span data-ttu-id="9a993-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9a993-121">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9a993-122">**Variabile**</span><span class="sxs-lookup"><span data-stu-id="9a993-122">**Variable**</span></span>|<span data-ttu-id="9a993-123">Vengono elencati gli attributi del modello di data mining individuati nel cluster selezionato.</span><span class="sxs-lookup"><span data-stu-id="9a993-123">Lists the attributes from the mining model that are found in the selected cluster.</span></span>|  
|<span data-ttu-id="9a993-124">**Valori**</span><span class="sxs-lookup"><span data-stu-id="9a993-124">**Values**</span></span>|<span data-ttu-id="9a993-125">Vengono elencati i valori degli attributi correnti individuati nel cluster attualmente selezionato.</span><span class="sxs-lookup"><span data-stu-id="9a993-125">Lists the values of the current attributes that are found in the currently selected cluster.</span></span>|  
|<span data-ttu-id="9a993-126">**Probabilità**</span><span class="sxs-lookup"><span data-stu-id="9a993-126">**Probability**</span></span>|<span data-ttu-id="9a993-127">La barra indica l'attendibilità della coppia attributo-valore come caratteristica di distinzione di questo cluster.</span><span class="sxs-lookup"><span data-stu-id="9a993-127">The bar indicates the strength of the attribute-value pair as a distinguishing feature of this cluster.</span></span> <span data-ttu-id="9a993-128">Se si posiziona il mouse sulla barra è possibile vedere il valore di probabilità rappresentato in percentuale.</span><span class="sxs-lookup"><span data-stu-id="9a993-128">If you hover the mouse over the bar, you can see the probability value, represented as a percentage.</span></span> <span data-ttu-id="9a993-129">Con questa combinazione di attributo e valore in qualsiasi case particolare, tramite tale valore viene indicata la probabilità che il case appartenga a questo cluster.</span><span class="sxs-lookup"><span data-stu-id="9a993-129">What this indicates is, given this attribute and value combination in any particular case, what is the probability that the case would belong in this cluster.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9a993-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9a993-130">See Also</span></span>  
 <span data-ttu-id="9a993-131">[Algoritmi di data mining &#40;Analysis Services-&#41;di data mining](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="9a993-131">[Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="9a993-132">[Visualizzatori modello di data mining &#40;Progettazione modelli di data mining&#41;](mining-model-viewers-data-mining-model-designer.md) </span><span class="sxs-lookup"><span data-stu-id="9a993-132">[Mining Model Viewers &#40;Data Mining Model Designer&#41;](mining-model-viewers-data-mining-model-designer.md) </span></span>  
 [<span data-ttu-id="9a993-133">Visualizzatori modello di data mining</span><span class="sxs-lookup"><span data-stu-id="9a993-133">Data Mining Model Viewers</span></span>](data-mining/data-mining-model-viewers.md)  
  
  
