---
title: Scheda Analisi discriminante attributi (Visualizzatore modello di data mining) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.naivebayse.discrimination.f1
ms.assetid: 68323f23-121e-44fc-be85-6f9915d6d3c7
author: minewiskan
ms.author: owend
ms.openlocfilehash: a8b0d4bc99b1c8f1c5de0269312f02eeb09df022
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625877"
---
# <a name="attribute-discrimination-tab-mining-model-viewer"></a><span data-ttu-id="1dd46-102">Scheda Analisi discriminante attributi (Visualizzatore modello di data mining)</span><span class="sxs-lookup"><span data-stu-id="1dd46-102">Attribute Discrimination Tab (Mining Model Viewer)</span></span>
  <span data-ttu-id="1dd46-103">Usare la scheda **Analisi discriminante attributi** per confrontare gli stati degli attributi di input e visualizzare la relativa correlazione con l'attributo risultante.</span><span class="sxs-lookup"><span data-stu-id="1dd46-103">Use the **Attribute Discrimination** tab to compare the states of the input attributes and see how they are related to the outcome attribute.</span></span> <span data-ttu-id="1dd46-104">I valori degli attributi che presentano le maggiori differenze tra i due stati di attributo stimabile selezionati vengono elencati per primi.</span><span class="sxs-lookup"><span data-stu-id="1dd46-104">The attribute values that make the most difference between the two selected predictable attribute states are listed first.</span></span>  
  
 <span data-ttu-id="1dd46-105">**Per altre informazioni:** [Algoritmo Microsoft Naive Bayes](data-mining/microsoft-naive-bayes-algorithm.md)e [Visualizzare un modello utilizzando il Visualizzatore Microsoft Naive Bayes](data-mining/browse-a-model-using-the-microsoft-naive-bayes-viewer.md)</span><span class="sxs-lookup"><span data-stu-id="1dd46-105">**For More Information:** [Microsoft Naive Bayes Algorithm](data-mining/microsoft-naive-bayes-algorithm.md), [Browse a Model Using the Microsoft Naive Bayes Viewer](data-mining/browse-a-model-using-the-microsoft-naive-bayes-viewer.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="1dd46-106">Opzioni</span><span class="sxs-lookup"><span data-stu-id="1dd46-106">Options</span></span>  
 <span data-ttu-id="1dd46-107">**Aggiorna contenuto visualizzatore**</span><span class="sxs-lookup"><span data-stu-id="1dd46-107">**Refresh viewer content**</span></span>  
 <span data-ttu-id="1dd46-108">Consente di ricaricare il modello di data mining nel visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="1dd46-108">Reload the mining model in the viewer.</span></span>  
  
 <span data-ttu-id="1dd46-109">**Modello di data mining**</span><span class="sxs-lookup"><span data-stu-id="1dd46-109">**Mining Model**</span></span>  
 <span data-ttu-id="1dd46-110">Consente di scegliere un modello di data mining tra quelli presenti nella struttura di data mining corrente.</span><span class="sxs-lookup"><span data-stu-id="1dd46-110">Choose a mining model from those in the current mining structure.</span></span> <span data-ttu-id="1dd46-111">Il modello di data mining viene aperto automaticamente nel visualizzatore personalizzato corretto.</span><span class="sxs-lookup"><span data-stu-id="1dd46-111">The mining model automatically opens in the correct custom viewer.</span></span>  
  
 <span data-ttu-id="1dd46-112">**Visualizzatore**</span><span class="sxs-lookup"><span data-stu-id="1dd46-112">**Viewer**</span></span>  
 <span data-ttu-id="1dd46-113">Consente di scegliere un visualizzatore da utilizzare per l'esplorazione del modello di data mining selezionato.</span><span class="sxs-lookup"><span data-stu-id="1dd46-113">Choose a viewer to use to explore the selected mining model.</span></span> <span data-ttu-id="1dd46-114">Per ogni modello è possibile scegliere il Visualizzatore personalizzato o [!INCLUDE[msCoName](../includes/msconame-md.md)] Mining Content Viewer.</span><span class="sxs-lookup"><span data-stu-id="1dd46-114">For each model, you can choose either the custom viewer, or the [!INCLUDE[msCoName](../includes/msconame-md.md)] Mining Content Viewer.</span></span> <span data-ttu-id="1dd46-115">Se disponibili, è anche possibile utilizzare i visualizzatori plug-in.</span><span class="sxs-lookup"><span data-stu-id="1dd46-115">You can also use plug-in viewers if available.</span></span>  
  
 <span data-ttu-id="1dd46-116">**Attributo**</span><span class="sxs-lookup"><span data-stu-id="1dd46-116">**Attribute**</span></span>  
 <span data-ttu-id="1dd46-117">Consente di scegliere un attributo stimabile.</span><span class="sxs-lookup"><span data-stu-id="1dd46-117">Choose a predictable attribute.</span></span>  
  
 <span data-ttu-id="1dd46-118">**Valore 1**</span><span class="sxs-lookup"><span data-stu-id="1dd46-118">**Value 1**</span></span>  
 <span data-ttu-id="1dd46-119">Consente di scegliere uno stato dell'attributo stimabile da confrontare con lo stato contenuto in **Valore 2**.</span><span class="sxs-lookup"><span data-stu-id="1dd46-119">Choose a state of the predictable attribute to compare to the state that is contained in **Value 2**.</span></span>  
  
 <span data-ttu-id="1dd46-120">**Valore 2**</span><span class="sxs-lookup"><span data-stu-id="1dd46-120">**Value 2**</span></span>  
 <span data-ttu-id="1dd46-121">Consente di scegliere uno stato dell'attributo stimabile da confrontare con lo stato contenuto in **Valore 1**.</span><span class="sxs-lookup"><span data-stu-id="1dd46-121">Select a state of the predictable attribute to compare to the state that is contained in **Value 1**.</span></span> <span data-ttu-id="1dd46-122">È anche possibile selezionare **tutti gli altri Stati** per confrontare il valore in **valore 1** con il relativo complemento, ovvero tutti gli altri valori eccetto valore 1.</span><span class="sxs-lookup"><span data-stu-id="1dd46-122">You can also select **All Other States** to compare the value in **Value 1** with its complement-that is, all other values except Value 1.</span></span>  
  
 <span data-ttu-id="1dd46-123">**Punteggi discriminanti per \<Value 1> e\<Value 2>**</span><span class="sxs-lookup"><span data-stu-id="1dd46-123">**Discrimination scores for \<Value 1> and \<Value 2>**</span></span>  
 <span data-ttu-id="1dd46-124">Nel grafico sono contenute le colonne seguenti in cui viene descritta la modalità di correlazione tra l'attributo di destinazione e gli stati specifici dell'attributo di input.</span><span class="sxs-lookup"><span data-stu-id="1dd46-124">The graph contains the following columns, which describe how the target attribute is related to specific states of the input attribute.</span></span>  
  
|<span data-ttu-id="1dd46-125">Valore</span><span class="sxs-lookup"><span data-stu-id="1dd46-125">Value</span></span>|<span data-ttu-id="1dd46-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1dd46-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="1dd46-127">**Attributes (Attributi)**</span><span class="sxs-lookup"><span data-stu-id="1dd46-127">**Attributes**</span></span>|<span data-ttu-id="1dd46-128">Un attributo di input nel modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="1dd46-128">An input attribute in the mining model.</span></span>|  
|<span data-ttu-id="1dd46-129">**Valori**</span><span class="sxs-lookup"><span data-stu-id="1dd46-129">**Values**</span></span>|<span data-ttu-id="1dd46-130">Uno stato dell'attributo contenuto nell'elenco **Attributi**.</span><span class="sxs-lookup"><span data-stu-id="1dd46-130">A state of the attribute that is listed in **Attributes**.</span></span>|  
|<span data-ttu-id="1dd46-131">**Predilige\<Value 1>**</span><span class="sxs-lookup"><span data-stu-id="1dd46-131">**Favors \<Value 1>**</span></span>|<span data-ttu-id="1dd46-132">La barra indica se l'attributo corrente e il valore prediligono il risultato di destinazione selezionato in **Valore 1**.</span><span class="sxs-lookup"><span data-stu-id="1dd46-132">The bar indicates whether the current attribute and value favor the target outcome selected in **Value 1**.</span></span>|  
|<span data-ttu-id="1dd46-133">**Predilige\<Value 2>**</span><span class="sxs-lookup"><span data-stu-id="1dd46-133">**Favors \<Value 2>**</span></span>|<span data-ttu-id="1dd46-134">La barra indica se l'attributo corrente e il valore prediligono il risultato di destinazione selezionato in **Valore 2**.</span><span class="sxs-lookup"><span data-stu-id="1dd46-134">The bar indicates whether the current attribute and value favor the target outcome selected in **Value 2**.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1dd46-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1dd46-135">See Also</span></span>  
 <span data-ttu-id="1dd46-136">[Algoritmi di data mining &#40;Analysis Services-&#41;di data mining](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="1dd46-136">[Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="1dd46-137">[Visualizzatori modello di data mining &#40;Progettazione modelli di data mining&#41;](mining-model-viewers-data-mining-model-designer.md) </span><span class="sxs-lookup"><span data-stu-id="1dd46-137">[Mining Model Viewers &#40;Data Mining Model Designer&#41;](mining-model-viewers-data-mining-model-designer.md) </span></span>  
 [<span data-ttu-id="1dd46-138">Visualizzatori modello di data mining</span><span class="sxs-lookup"><span data-stu-id="1dd46-138">Data Mining Model Viewers</span></span>](data-mining/data-mining-model-viewers.md)  
  
  
