---
title: Scheda rete di dipendenze (Visualizzatore modello di data mining) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.dependencynetwork.f1
ms.assetid: e58ce1b7-20d6-42cb-ade5-916da8471e09
author: minewiskan
ms.author: owend
ms.openlocfilehash: 94ce82524445ffb8999c671c736087362ef0adfb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712615"
---
# <a name="dependency-network-tab-mining-model-viewer"></a><span data-ttu-id="27c8d-102">Scheda Rete di dipendenze (Visualizzatore modello di data mining)</span><span class="sxs-lookup"><span data-stu-id="27c8d-102">Dependency Network Tab (Mining Model Viewer)</span></span>
  <span data-ttu-id="27c8d-103">La scheda **Rete di dipendenze** consente di visualizzare graficamente tutti gli attributi contenuti nel modello di dati mining e la relativa modalità di correlazione.</span><span class="sxs-lookup"><span data-stu-id="27c8d-103">The **Dependency Net** tab provides a graphical view of all attributes that the mining model contains, and shows how the attributes are related.</span></span>  
  
 <span data-ttu-id="27c8d-104">La scheda **Rete di dipendenze**  viene utilizzata per diversi tipi di modelli di data mining, inclusi i modelli Naive Bayes, di albero delle decisioni e di associazione.</span><span class="sxs-lookup"><span data-stu-id="27c8d-104">The **Dependency Net**  tab is used for several types of mining models, including Naïve Bayes models, decision tree models, and association models.</span></span> <span data-ttu-id="27c8d-105">Per ulteriori informazioni su come interpretare il contenuto della scheda **Rete di dipendenze**  nel contesto di questi modelli, vedere i collegamenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="27c8d-105">For more information about how to interpret the contents of the **Dependency Net**  tab in the context of these models, see the following links:</span></span>  
  
 [<span data-ttu-id="27c8d-106">Visualizzare un modello utilizzando il Visualizzatore Microsoft Decision Trees</span><span class="sxs-lookup"><span data-stu-id="27c8d-106">Browse a Model Using the Microsoft Tree Viewer</span></span>](data-mining/browse-a-model-using-the-microsoft-tree-viewer.md)  
  
 [<span data-ttu-id="27c8d-107">Visualizzare un modello utilizzando il Visualizzatore Microsoft Naive Bayes</span><span class="sxs-lookup"><span data-stu-id="27c8d-107">Browse a Model Using the Microsoft Naive Bayes Viewer</span></span>](data-mining/browse-a-model-using-the-microsoft-naive-bayes-viewer.md)  
  
 [<span data-ttu-id="27c8d-108">Visualizzare un modello utilizzando il Visualizzatore Microsoft Association Rules</span><span class="sxs-lookup"><span data-stu-id="27c8d-108">Browse a Model Using the Microsoft Association Rules Viewer</span></span>](data-mining/browse-a-model-using-the-microsoft-association-rules-viewer.md)  
  
## <a name="options"></a><span data-ttu-id="27c8d-109">Opzioni</span><span class="sxs-lookup"><span data-stu-id="27c8d-109">Options</span></span>  
 <span data-ttu-id="27c8d-110">**Aggiorna contenuto visualizzatore**</span><span class="sxs-lookup"><span data-stu-id="27c8d-110">**Refresh viewer content**</span></span>  
 <span data-ttu-id="27c8d-111">Consente di ricaricare il modello di data mining nel visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="27c8d-111">Reload the mining model in the viewer.</span></span>  
  
 <span data-ttu-id="27c8d-112">**Modello di data mining**</span><span class="sxs-lookup"><span data-stu-id="27c8d-112">**Mining Model**</span></span>  
 <span data-ttu-id="27c8d-113">Consente di scegliere un modello di data mining da visualizzare tra quelli presenti nella struttura di data mining corrente.</span><span class="sxs-lookup"><span data-stu-id="27c8d-113">Choose a mining model to view, from those in the current mining structure.</span></span> <span data-ttu-id="27c8d-114">Il modello di data mining verrà aperto in un visualizzatore personalizzato.</span><span class="sxs-lookup"><span data-stu-id="27c8d-114">The mining model will open in a custom viewer.</span></span> <span data-ttu-id="27c8d-115">Il tipo di visualizzatore personalizzato utilizzato per ogni modello viene determinato dall'algoritmo utilizzato per creare il modello.</span><span class="sxs-lookup"><span data-stu-id="27c8d-115">The type of custom viewer that is used for each model is determined by the algorithm that you used to create the model.</span></span>  
  
 <span data-ttu-id="27c8d-116">**Visualizzatore**</span><span class="sxs-lookup"><span data-stu-id="27c8d-116">**Viewer**</span></span>  
 <span data-ttu-id="27c8d-117">Consente di scegliere un visualizzatore da utilizzare per l'esplorazione del modello di data mining selezionato.</span><span class="sxs-lookup"><span data-stu-id="27c8d-117">Choose a viewer to use to explore the selected mining model.</span></span> <span data-ttu-id="27c8d-118">Per ogni modello è possibile utilizzare il visualizzatore personalizzato fornito per ogni modello di data mining o Visualizzatore contenuto di data mining [!INCLUDE[msCoName](../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="27c8d-118">For each model, you can use either the custom viewer is provided for each mining model, or the [!INCLUDE[msCoName](../includes/msconame-md.md)] Mining Content Viewer.</span></span> <span data-ttu-id="27c8d-119">Se disponibili, è anche possibile utilizzare i visualizzatori plug-in.</span><span class="sxs-lookup"><span data-stu-id="27c8d-119">You can also use plug-in viewers if available.</span></span> <span data-ttu-id="27c8d-120">Microsoft Generic Content Tree Viewer può essere utilizzato con tutti i modelli e rappresenta il contenuto del modello in una tabella HTML.</span><span class="sxs-lookup"><span data-stu-id="27c8d-120">The Microsoft Content Tree Viewer can be used with all models, and represents the model content in an HTML table.</span></span>  
  
 <span data-ttu-id="27c8d-121">**Zoom avanti**</span><span class="sxs-lookup"><span data-stu-id="27c8d-121">**Zoom In**</span></span>  
 <span data-ttu-id="27c8d-122">Consente di eseguire lo zoom avanti del diagramma in modo da poter visualizzare più dettagliatamente gli attributi.</span><span class="sxs-lookup"><span data-stu-id="27c8d-122">Zoom in to the diagram, so that you can see the attributes in more detail.</span></span>  
  
 <span data-ttu-id="27c8d-123">**Zoom indietro**</span><span class="sxs-lookup"><span data-stu-id="27c8d-123">**Zoom Out**</span></span>  
 <span data-ttu-id="27c8d-124">Consente di eseguire lo zoom indietro del diagramma in modo da poter visualizzare più attributi e i relativi collegamenti.</span><span class="sxs-lookup"><span data-stu-id="27c8d-124">Zoom out from the diagram, so that you can see more attributes and the links between them.</span></span>  
  
 <span data-ttu-id="27c8d-125">**Copia parte visibile del grafico**</span><span class="sxs-lookup"><span data-stu-id="27c8d-125">**Copy Graph View**</span></span>  
 <span data-ttu-id="27c8d-126">Consente di copiare la sezione visibile del diagramma negli Appunti.</span><span class="sxs-lookup"><span data-stu-id="27c8d-126">Copy the visible section of the diagram to the clipboard.</span></span>  
  
 <span data-ttu-id="27c8d-127">**Copia grafico intero**</span><span class="sxs-lookup"><span data-stu-id="27c8d-127">**Copy Entire Graph**</span></span>  
 <span data-ttu-id="27c8d-128">Consente di copiare tutto il diagramma negli Appunti.</span><span class="sxs-lookup"><span data-stu-id="27c8d-128">Copy the complete diagram to the clipboard.</span></span>  
  
 <span data-ttu-id="27c8d-129">**Collegamenti**</span><span class="sxs-lookup"><span data-stu-id="27c8d-129">**Links**</span></span>  
 <span data-ttu-id="27c8d-130">Consente di impostare il numero di collegamenti (bordi) e nodi mostrati dal visualizzatore regolando l'indicatore di scorrimento a destra degli attributi.</span><span class="sxs-lookup"><span data-stu-id="27c8d-130">Adjust how many links (edges) and nodes the viewer shows by adjusting the slider to the right of the attributes.</span></span> <span data-ttu-id="27c8d-131">Trascinando la barra del dispositivo di scorrimento verso il basso viene aumentato il valore soglia in modo da visualizzare solo i collegamenti più attendibili.</span><span class="sxs-lookup"><span data-stu-id="27c8d-131">Dragging the slider bar down increases the threshold value, so that only the strongest links are shown.</span></span> <span data-ttu-id="27c8d-132">Per ogni tipo di modello, viene utilizzato un valore leggermente diverso per rappresentare i collegamenti nel grafico:</span><span class="sxs-lookup"><span data-stu-id="27c8d-132">For each model type, a slightly different value is used to represent the links in the graph:</span></span>  
  
-   <span data-ttu-id="27c8d-133">In un modello di **albero delle decisioni** i bordi rappresentano l'attendibilità predittiva della connessione, determinata in parte dal punteggio di divisione.</span><span class="sxs-lookup"><span data-stu-id="27c8d-133">In a **decision tree** model, the edges represent the predictive strength of the connection, determined partly by the split score.</span></span>  
  
-   <span data-ttu-id="27c8d-134">In un modello **Naive Bayes** i collegamenti tra due nodi possono andare in entrambe le direzioni, ovvero il nodo A può consentire la stima del nodo B e viceversa.</span><span class="sxs-lookup"><span data-stu-id="27c8d-134">In a **Naïve Bayes** model, the links between two nodes can go either way: that is, node A can predict the node B, and vice versa.</span></span> <span data-ttu-id="27c8d-135">Il punteggio associato al bordo rappresenta l'attendibilità predittiva della connessione.</span><span class="sxs-lookup"><span data-stu-id="27c8d-135">The score associated with the edge represents the predictive strength of the connection.</span></span>  
  
-   <span data-ttu-id="27c8d-136">In un **modello di associazione**i bordi tra i nodi rappresentano il punteggio di priorità della regola tramite cui sono connessi due set di elementi.</span><span class="sxs-lookup"><span data-stu-id="27c8d-136">In an **association model**, the edges between nodes represent the importance score of the rule that connects two itemsets.</span></span>  
  
 <span data-ttu-id="27c8d-137">Una regola generale per tutti i tipi di modelli prevede che maggiore è l'attendibilità del collegamento, maggiore sarà l'attendibilità della relazione predittiva tra i due attributi.</span><span class="sxs-lookup"><span data-stu-id="27c8d-137">A general rule for all model types is that the stronger the link, the stronger the predictive relationship between the two attributes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27c8d-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="27c8d-138">See Also</span></span>  
 <span data-ttu-id="27c8d-139">[Algoritmi di data mining &#40;Analysis Services-&#41;di data mining](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="27c8d-139">[Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="27c8d-140">[Visualizzatori modello di data mining &#40;Progettazione modelli di data mining&#41;](mining-model-viewers-data-mining-model-designer.md) </span><span class="sxs-lookup"><span data-stu-id="27c8d-140">[Mining Model Viewers &#40;Data Mining Model Designer&#41;](mining-model-viewers-data-mining-model-designer.md) </span></span>  
 [<span data-ttu-id="27c8d-141">Visualizzatori modello di data mining</span><span class="sxs-lookup"><span data-stu-id="27c8d-141">Data Mining Model Viewers</span></span>](data-mining/data-mining-model-viewers.md)  
  
  
