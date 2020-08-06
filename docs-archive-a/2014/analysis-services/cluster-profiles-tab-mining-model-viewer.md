---
title: Scheda Profili cluster (Visualizzatore modello di data mining) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.clustering.profiles.f1
ms.assetid: 1ebafa1f-74e9-4c05-b278-a690fa8543bd
author: minewiskan
ms.author: owend
ms.openlocfilehash: a7ec1ce5b5204ae81a9313ca7b7e5df58c98c5da
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626391"
---
# <a name="cluster-profiles-tab-mining-model-viewer"></a><span data-ttu-id="29283-102">Scheda Profili cluster (Visualizzatore modello di data mining)</span><span class="sxs-lookup"><span data-stu-id="29283-102">Cluster Profiles Tab (Mining Model Viewer)</span></span>
  <span data-ttu-id="29283-103">Usare la scheda **Profili cluster** per una vista complessiva dei cluster individuati dall'algoritmo all'interno di un modello di clustering.</span><span class="sxs-lookup"><span data-stu-id="29283-103">Use the **Cluster Profiles** tab for an overall view of the clusters that the algorithm discovered within a clustering model.</span></span> <span data-ttu-id="29283-104">In questa scheda viene visualizzato ogni attributo, insieme alla relativa distribuzione in ciascun cluster.</span><span class="sxs-lookup"><span data-stu-id="29283-104">The tab displays each attribute, together with the distribution of the attribute in each cluster.</span></span>  
  
 <span data-ttu-id="29283-105">**Per altre informazioni:** [Algoritmo Microsoft Clustering](data-mining/microsoft-clustering-algorithm.md), [Visualizzare un modello usando il Visualizzatore Microsoft Clustering](data-mining/browse-a-model-using-the-microsoft-cluster-viewer.md)</span><span class="sxs-lookup"><span data-stu-id="29283-105">**For More Information:** [Microsoft Clustering Algorithm](data-mining/microsoft-clustering-algorithm.md), [Browse a Model Using the Microsoft Cluster Viewer](data-mining/browse-a-model-using-the-microsoft-cluster-viewer.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="29283-106">Opzioni</span><span class="sxs-lookup"><span data-stu-id="29283-106">Options</span></span>  
 <span data-ttu-id="29283-107">**Aggiorna contenuto visualizzatore**</span><span class="sxs-lookup"><span data-stu-id="29283-107">**Refresh viewer content**</span></span>  
 <span data-ttu-id="29283-108">Consente di ricaricare il modello di data mining nel visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="29283-108">Reload the mining model in the viewer.</span></span>  
  
 <span data-ttu-id="29283-109">**Modello di data mining**</span><span class="sxs-lookup"><span data-stu-id="29283-109">**Mining Model**</span></span>  
 <span data-ttu-id="29283-110">Consente di scegliere un modello di data mining tra quelli presenti nella struttura di data mining corrente.</span><span class="sxs-lookup"><span data-stu-id="29283-110">Choose a mining model from those in the current mining structure.</span></span> <span data-ttu-id="29283-111">Il modello di data mining verrà aperto nel visualizzatore associato.</span><span class="sxs-lookup"><span data-stu-id="29283-111">The mining model will open in its associated viewer.</span></span>  
  
 <span data-ttu-id="29283-112">**Visualizzatore**</span><span class="sxs-lookup"><span data-stu-id="29283-112">**Viewer**</span></span>  
 <span data-ttu-id="29283-113">Consente di scegliere un visualizzatore da utilizzare per la visualizzazione del modello di data mining selezionato.</span><span class="sxs-lookup"><span data-stu-id="29283-113">Choose a viewer to use to view the selected mining model.</span></span> <span data-ttu-id="29283-114">È possibile utilizzare il visualizzatore personalizzato per il modello di data mining o il Visualizzatore contenuto di data mining [!INCLUDE[msCoName](../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="29283-114">You can use the custom viewer for the mining model, or the [!INCLUDE[msCoName](../includes/msconame-md.md)] Mining Content Viewer.</span></span> <span data-ttu-id="29283-115">Se disponibili, è anche possibile utilizzare i visualizzatori plug-in.</span><span class="sxs-lookup"><span data-stu-id="29283-115">You can also use plug-in viewers if available.</span></span>  
  
 <span data-ttu-id="29283-116">**Mostra legenda**</span><span class="sxs-lookup"><span data-stu-id="29283-116">**Show Legend**</span></span>  
 <span data-ttu-id="29283-117">Selezionare questa opzione per visualizzare una chiave in cui viene mostrato il mapping dei colori nel visualizzatore ai valori nella colonna **Stati** .</span><span class="sxs-lookup"><span data-stu-id="29283-117">Select this option to display a key that shows the mapping of colors in the viewer to values in the **States** column.</span></span>  
  
 <span data-ttu-id="29283-118">**Barre istogramma**</span><span class="sxs-lookup"><span data-stu-id="29283-118">**Histogram Bars**</span></span>  
 <span data-ttu-id="29283-119">Modificare questo valore per controllare il numero di stati inclusi in ogni istogramma.</span><span class="sxs-lookup"><span data-stu-id="29283-119">Change this value to control how many states are included in each histogram.</span></span> <span data-ttu-id="29283-120">Se esistono più stati di quelli scelti per la visualizzazione, gli stati con la probabilità più elevata vengono mostrati nell'istogramma, mentre quelli rimanenti vengono raggruppati in **Altro**.</span><span class="sxs-lookup"><span data-stu-id="29283-120">If there are more states than you choose to display, the states with the highest probability are shown in the histogram, and the remaining states are grouped together into **Other**.</span></span>  
  
 <span data-ttu-id="29283-121">**Attributes (Attributi)**</span><span class="sxs-lookup"><span data-stu-id="29283-121">**Attributes**</span></span>  
 <span data-ttu-id="29283-122">Vengono elencate le colonne presenti nel modello di clustering.</span><span class="sxs-lookup"><span data-stu-id="29283-122">Lists the columns that are in the clustering model.</span></span> <span data-ttu-id="29283-123">Negli istogrammi per ogni attributo viene mostrata la modalità di distribuzione dell'attributo tra i cluster identificati dall'algoritmo.</span><span class="sxs-lookup"><span data-stu-id="29283-123">The histograms for each attribute show how the attribute is distributed among the clusters identified by the algorithm.</span></span>  
  
 <span data-ttu-id="29283-124">**Stati**</span><span class="sxs-lookup"><span data-stu-id="29283-124">**States**</span></span>  
 <span data-ttu-id="29283-125">Viene fornita una chiave che indica il colore che rappresenta ogni stato nella riga corrispondente di cluster o un dispositivo di scorrimento con diamante che indica la distribuzione di valori numerici continui.</span><span class="sxs-lookup"><span data-stu-id="29283-125">Provides a key that either denotes what color represents each state in the corresponding row of clusters, or a slider with diamond that indicates the distribution of continuous numeric values.</span></span> <span data-ttu-id="29283-126">È possibile mostrare o nascondere questa colonna tramite la casella di controllo **Mostra legenda** .</span><span class="sxs-lookup"><span data-stu-id="29283-126">You can show or hide this column by using the **Show Legend** check box.</span></span>  
  
 <span data-ttu-id="29283-127">**Profili cluster**</span><span class="sxs-lookup"><span data-stu-id="29283-127">**Cluster Profiles**</span></span>  
 <span data-ttu-id="29283-128">In questa sezione è contenuta una colonna per ogni cluster nel modello.</span><span class="sxs-lookup"><span data-stu-id="29283-128">This section contains a column for each cluster in the model.</span></span> <span data-ttu-id="29283-129">Per ogni attributo, nell'istogramma viene mostrata la distribuzione dei valori nell'attributo solo per tale cluster.</span><span class="sxs-lookup"><span data-stu-id="29283-129">For each attribute, the histogram shows the distribution of the values in the attribute for just that cluster.</span></span> <span data-ttu-id="29283-130">Nel grafico è inoltre disponibile una colonna per **Popolazione**in cui vengono usati gli istogrammi per visualizzare la distribuzione dei valori per ogni attributo, ma per tutti i case nel modello.</span><span class="sxs-lookup"><span data-stu-id="29283-130">The chart also has a column for **Population**, which also uses histograms to display the distribution of values for each attribute, but for all cases in the model.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29283-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="29283-131">See Also</span></span>  
 <span data-ttu-id="29283-132">[Algoritmi di data mining &#40;Analysis Services-&#41;di data mining](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="29283-132">[Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="29283-133">[Visualizzatori modello di data mining &#40;Progettazione modelli di data mining&#41;](mining-model-viewers-data-mining-model-designer.md) </span><span class="sxs-lookup"><span data-stu-id="29283-133">[Mining Model Viewers &#40;Data Mining Model Designer&#41;](mining-model-viewers-data-mining-model-designer.md) </span></span>  
 [<span data-ttu-id="29283-134">Visualizzatori modello di data mining</span><span class="sxs-lookup"><span data-stu-id="29283-134">Data Mining Model Viewers</span></span>](data-mining/data-mining-model-viewers.md)  
  
  
