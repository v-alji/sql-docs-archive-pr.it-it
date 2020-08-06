---
title: Scheda Caratteristiche attributo (Visualizzatore modello di data mining) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.naivebayse.characteristics.f1
ms.assetid: f0c3350d-84c0-4ab8-9fb8-1527c2647299
author: minewiskan
ms.author: owend
ms.openlocfilehash: b29ba482c21bb674a10bc4c9e6c6eccdf30905dd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625882"
---
# <a name="attribute-characteristics-tab-mining-model-viewer"></a><span data-ttu-id="c8f76-102">Scheda Caratteristiche attributo (Visualizzatore modello di data mining)</span><span class="sxs-lookup"><span data-stu-id="c8f76-102">Attribute Characteristics Tab (Mining Model Viewer)</span></span>
  <span data-ttu-id="c8f76-103">Usare il riquadro **Caratteristiche attributo** per esplorare le relazioni tra i risultati e gli attributi di input in un modello Naive Bayes.</span><span class="sxs-lookup"><span data-stu-id="c8f76-103">Use the **Attribute Characteristics** pane to explore the relationships between outcomes and input attributes in a Naïve Bayes model.</span></span> <span data-ttu-id="c8f76-104">È possibile scegliere il valore dell'attributo di destinazione, quindi visualizzare un elenco degli attributi di input che influiscono maggiormente sui risultati.</span><span class="sxs-lookup"><span data-stu-id="c8f76-104">You can choose the value of the target attribute, and then see a list of the input attributes that have the strongest effect on the outcomes.</span></span>  
  
 <span data-ttu-id="c8f76-105">**Per altre informazioni:** [Algoritmo Microsoft Naive Bayes](data-mining/microsoft-naive-bayes-algorithm.md)e [Visualizzare un modello utilizzando il Visualizzatore Microsoft Naive Bayes](data-mining/browse-a-model-using-the-microsoft-naive-bayes-viewer.md)</span><span class="sxs-lookup"><span data-stu-id="c8f76-105">**For More Information:** [Microsoft Naive Bayes Algorithm](data-mining/microsoft-naive-bayes-algorithm.md), [Browse a Model Using the Microsoft Naive Bayes Viewer](data-mining/browse-a-model-using-the-microsoft-naive-bayes-viewer.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="c8f76-106">Opzioni</span><span class="sxs-lookup"><span data-stu-id="c8f76-106">Options</span></span>  
 <span data-ttu-id="c8f76-107">**Aggiorna contenuto visualizzatore**</span><span class="sxs-lookup"><span data-stu-id="c8f76-107">**Refresh viewer content**</span></span>  
 <span data-ttu-id="c8f76-108">Consente di ricaricare il modello di data mining nel visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="c8f76-108">Reload the mining model in the viewer.</span></span>  
  
 <span data-ttu-id="c8f76-109">**Modello di data mining**</span><span class="sxs-lookup"><span data-stu-id="c8f76-109">**Mining Model**</span></span>  
 <span data-ttu-id="c8f76-110">Consente di scegliere un modello di data mining da visualizzare tra i modelli presenti nella struttura di data mining corrente.</span><span class="sxs-lookup"><span data-stu-id="c8f76-110">Choose a mining model to view, from the models in the current mining structure.</span></span> <span data-ttu-id="c8f76-111">Il modello di data mining verrà aperto automaticamente nel visualizzatore personalizzato migliore per il particolare tipo di modello scelto.</span><span class="sxs-lookup"><span data-stu-id="c8f76-111">The mining model will automatically open in a custom viewer that is best for the particular type of model you chose.</span></span>  
  
 <span data-ttu-id="c8f76-112">**Visualizzatore**</span><span class="sxs-lookup"><span data-stu-id="c8f76-112">**Viewer**</span></span>  
 <span data-ttu-id="c8f76-113">Consente di scegliere un visualizzatore da utilizzare per l'esplorazione del modello di data mining selezionato.</span><span class="sxs-lookup"><span data-stu-id="c8f76-113">Choose a viewer to use to explore the selected mining model.</span></span> <span data-ttu-id="c8f76-114">Per ogni modello è possibile scegliere tra un visualizzatore personalizzato o Visualizzatore contenuto di data mining [!INCLUDE[msCoName](../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c8f76-114">For each model, you have the choice of a custom viewer, or the [!INCLUDE[msCoName](../includes/msconame-md.md)] Mining Content Viewer.</span></span> <span data-ttu-id="c8f76-115">Se disponibili, nell'elenco vengono visualizzati anche i visualizzatori plug-in.</span><span class="sxs-lookup"><span data-stu-id="c8f76-115">Plug-in viewers also appear in this list if available.</span></span>  
  
 <span data-ttu-id="c8f76-116">**Attributo**</span><span class="sxs-lookup"><span data-stu-id="c8f76-116">**Attribute**</span></span>  
 <span data-ttu-id="c8f76-117">Consente di scegliere l'attributo stimabile che si desidera analizzare.</span><span class="sxs-lookup"><span data-stu-id="c8f76-117">Choose the predictable attribute that you want to analyze.</span></span>  
  
 <span data-ttu-id="c8f76-118">**Valore**</span><span class="sxs-lookup"><span data-stu-id="c8f76-118">**Value**</span></span>  
 <span data-ttu-id="c8f76-119">Consente di scegliere uno stato per l'attributo stimabile impostato in **Attributo**.</span><span class="sxs-lookup"><span data-stu-id="c8f76-119">Choose a state for the predictable attribute that you set in **Attribute**.</span></span> <span data-ttu-id="c8f76-120">Poiché i modelli Naive Bayes non supportano le variabili continue, tutti gli attributi di destinazione dispongono di risultati discreti o discretizzati.</span><span class="sxs-lookup"><span data-stu-id="c8f76-120">Because Naïve Bayes models do not support continuous variables, all target attributes have discrete or discretized outcomes.</span></span> <span data-ttu-id="c8f76-121">L'attributo Missing viene sempre aggiunto automaticamente all'elenco.</span><span class="sxs-lookup"><span data-stu-id="c8f76-121">The Missing attribute is always automatically added to the list.</span></span>  
  
 <span data-ttu-id="c8f76-122">**Caratteristiche per\<predictable state>**</span><span class="sxs-lookup"><span data-stu-id="c8f76-122">**Characteristics for \<predictable state>**</span></span>  
 <span data-ttu-id="c8f76-123">Nel grafico sono contenute le colonne seguenti in cui viene descritta la modalità di correlazione tra gli stati dell'attributo di input e lo stato dell'attributo stimabile selezionato.</span><span class="sxs-lookup"><span data-stu-id="c8f76-123">The graph contains the following columns, which describe how states of the input attributes are related to the selected predictable attribute state.</span></span>  
  
|<span data-ttu-id="c8f76-124">Valore</span><span class="sxs-lookup"><span data-stu-id="c8f76-124">Value</span></span>|<span data-ttu-id="c8f76-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c8f76-125">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c8f76-126">**Variabile**</span><span class="sxs-lookup"><span data-stu-id="c8f76-126">**Variable**</span></span>|<span data-ttu-id="c8f76-127">Vengono elencati gli attributi di input nel modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="c8f76-127">Lists the input attributes in the mining model.</span></span>|  
|<span data-ttu-id="c8f76-128">**Valori**</span><span class="sxs-lookup"><span data-stu-id="c8f76-128">**Values**</span></span>|<span data-ttu-id="c8f76-129">Viene elencato ogni stato dell'attributo di input in **Variabile**.</span><span class="sxs-lookup"><span data-stu-id="c8f76-129">Lists each state of the input attribute in **Variable**.</span></span>|  
|<span data-ttu-id="c8f76-130">**Probabilità**</span><span class="sxs-lookup"><span data-stu-id="c8f76-130">**Probability**</span></span>|<span data-ttu-id="c8f76-131">La barra rappresenta la probabilità che l'attributo e il valore in tale riga siano associati allo stato selezionato dell'attributo stimabile.</span><span class="sxs-lookup"><span data-stu-id="c8f76-131">The bar represents the probability that the attribute and value in that row are associated with the selected state of the predictable attribute.</span></span> <span data-ttu-id="c8f76-132">Posizionare il mouse sulla barra per visualizzare la probabilità in percentuale.</span><span class="sxs-lookup"><span data-stu-id="c8f76-132">Hover the mouse over the bar to view the probability as a percentage.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c8f76-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c8f76-133">See Also</span></span>  
 <span data-ttu-id="c8f76-134">[Algoritmi di data mining &#40;Analysis Services-&#41;di data mining](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="c8f76-134">[Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="c8f76-135">[Visualizzatori modello di data mining &#40;Progettazione modelli di data mining&#41;](mining-model-viewers-data-mining-model-designer.md) </span><span class="sxs-lookup"><span data-stu-id="c8f76-135">[Mining Model Viewers &#40;Data Mining Model Designer&#41;](mining-model-viewers-data-mining-model-designer.md) </span></span>  
 [<span data-ttu-id="c8f76-136">Visualizzatori modello di data mining</span><span class="sxs-lookup"><span data-stu-id="c8f76-136">Data Mining Model Viewers</span></span>](data-mining/data-mining-model-viewers.md)  
  
  
