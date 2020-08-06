---
title: Scheda profili attributi (Visualizzatore modello di data mining) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.naivebayse.profiles.f1
ms.assetid: 17c7e7ae-273c-4a6b-9a35-e8b9b8e65999
author: minewiskan
ms.author: owend
ms.openlocfilehash: 61c81b95f030bf1a69aed165bd64e58ff9af8339
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625872"
---
# <a name="attribute-profiles-tab-mining-model-viewer"></a><span data-ttu-id="c0434-102">Scheda Profili attributo (Visualizzatore modello di data mining)</span><span class="sxs-lookup"><span data-stu-id="c0434-102">Attribute Profiles Tab (Mining Model Viewer)</span></span>
  <span data-ttu-id="c0434-103">Usare la scheda **Profili attributo** per vedere il modo in cui la distribuzione dei valori di input in uno stato del modello Naive Bayes contribuisce a ogni stato dell'attributo risultante.</span><span class="sxs-lookup"><span data-stu-id="c0434-103">Use the **Attribute Profiles** tab to see how the distribution of input values in a Naive Bayes model state contribute to each state of the outcome attribute.</span></span> <span data-ttu-id="c0434-104">La distribuzione dei valori viene mostrata come un istogramma colorato e tutte le distribuzioni vengono presentate in un formato tabulare per rendere più semplice il confronto dei valori.</span><span class="sxs-lookup"><span data-stu-id="c0434-104">The distribution of values is shown as a colored histogram, all distributions presented in a tabular format, to make it easier to compare values.</span></span>  
  
 <span data-ttu-id="c0434-105">**Per altre informazioni:** [Algoritmo Microsoft Naive Bayes](data-mining/microsoft-naive-bayes-algorithm.md)e [Visualizzare un modello utilizzando il Visualizzatore Microsoft Naive Bayes](data-mining/browse-a-model-using-the-microsoft-naive-bayes-viewer.md)</span><span class="sxs-lookup"><span data-stu-id="c0434-105">**For More Information:** [Microsoft Naive Bayes Algorithm](data-mining/microsoft-naive-bayes-algorithm.md), [Browse a Model Using the Microsoft Naive Bayes Viewer](data-mining/browse-a-model-using-the-microsoft-naive-bayes-viewer.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="c0434-106">Opzioni</span><span class="sxs-lookup"><span data-stu-id="c0434-106">Options</span></span>  
 <span data-ttu-id="c0434-107">**Aggiorna contenuto visualizzatore**</span><span class="sxs-lookup"><span data-stu-id="c0434-107">**Refresh viewer content**</span></span>  
 <span data-ttu-id="c0434-108">Consente di ricaricare il modello di data mining nel visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="c0434-108">Reload the mining model in the viewer.</span></span>  
  
 <span data-ttu-id="c0434-109">**Modello di data mining**</span><span class="sxs-lookup"><span data-stu-id="c0434-109">**Mining Model**</span></span>  
 <span data-ttu-id="c0434-110">Consente di scegliere un modello di data mining da visualizzare tra quelli presenti nella struttura di data mining corrente.</span><span class="sxs-lookup"><span data-stu-id="c0434-110">Choose a mining model to view, from those in the current mining structure.</span></span> <span data-ttu-id="c0434-111">Il modello di data mining verrà aperto nel visualizzatore associato.</span><span class="sxs-lookup"><span data-stu-id="c0434-111">The mining model will open in its associated viewer.</span></span>  
  
 <span data-ttu-id="c0434-112">**Visualizzatore**</span><span class="sxs-lookup"><span data-stu-id="c0434-112">**Viewer**</span></span>  
 <span data-ttu-id="c0434-113">Consente di scegliere un visualizzatore da utilizzare per l'esplorazione del modello di data mining selezionato.</span><span class="sxs-lookup"><span data-stu-id="c0434-113">Choose a viewer to use to explore the selected mining model.</span></span> <span data-ttu-id="c0434-114">È possibile scegliere il visualizzatore personalizzato fornito per ogni modello di data mining o il Visualizzatore contenuto di data mining [!INCLUDE[msCoName](../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c0434-114">You can choose the custom viewer provided for each mining model, or the [!INCLUDE[msCoName](../includes/msconame-md.md)] Mining Content Viewer.</span></span> <span data-ttu-id="c0434-115">Se disponibili, è anche possibile utilizzare i visualizzatori plug-in.</span><span class="sxs-lookup"><span data-stu-id="c0434-115">You can also use plug-in viewers if they are available.</span></span>  
  
 <span data-ttu-id="c0434-116">**Mostra legenda**</span><span class="sxs-lookup"><span data-stu-id="c0434-116">**Show Legend**</span></span>  
 <span data-ttu-id="c0434-117">Selezionare questa opzione per visualizzare una chiave che consente di far corrispondere ogni valore disponibile in **Stati** a uno dei colori usati nel grafico di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="c0434-117">Select this option to display a key that matches each value in **States** to one of the colors used in the distribution chart.</span></span>  
  
 <span data-ttu-id="c0434-118">**Barre istogramma**</span><span class="sxs-lookup"><span data-stu-id="c0434-118">**Histogram bars**</span></span>  
 <span data-ttu-id="c0434-119">Consente di selezionare il numero di barre da includere nell'istogramma.</span><span class="sxs-lookup"><span data-stu-id="c0434-119">Select how many bars to include in the histogram.</span></span> <span data-ttu-id="c0434-120">Se esistono più barre di quante ne sono state scelte per la visualizzazione, le barre di importanza più alta vengono mantenute, mentre le barre rimanenti vengono raggruppate in **Altro**.</span><span class="sxs-lookup"><span data-stu-id="c0434-120">If more bars exist than you choose to display, the bars of highest importance are retained, and the remaining bars are grouped together into **Other**.</span></span>  
  
 <span data-ttu-id="c0434-121">**Stimabile**</span><span class="sxs-lookup"><span data-stu-id="c0434-121">**Predictable**</span></span>  
 <span data-ttu-id="c0434-122">Consente di selezionare una colonna stimabile nel modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="c0434-122">Select a predictable column from the mining model.</span></span>  
  
 <span data-ttu-id="c0434-123">**Profili attributo**</span><span class="sxs-lookup"><span data-stu-id="c0434-123">**Attribute Profiles**</span></span>  
 <span data-ttu-id="c0434-124">La tabella contiene le colonne seguenti:</span><span class="sxs-lookup"><span data-stu-id="c0434-124">The table contains the following columns:</span></span>  
  
|<span data-ttu-id="c0434-125">Valore</span><span class="sxs-lookup"><span data-stu-id="c0434-125">Value</span></span>|<span data-ttu-id="c0434-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c0434-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c0434-127">**Attributes (Attributi)**</span><span class="sxs-lookup"><span data-stu-id="c0434-127">**Attributes**</span></span>|<span data-ttu-id="c0434-128">Elenca le colonne del modello di data mining contenute nel modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="c0434-128">Lists the mining model columns contained within the mining model.</span></span>|  
|<span data-ttu-id="c0434-129">**Stati**</span><span class="sxs-lookup"><span data-stu-id="c0434-129">**States**</span></span>|<span data-ttu-id="c0434-130">Colonna facoltativa che descrive lo stato rappresentato dal colore nella riga degli attributi.</span><span class="sxs-lookup"><span data-stu-id="c0434-130">An optional column that describes what state the color in the corresponding row of attributes represents.</span></span> <span data-ttu-id="c0434-131">Aggiungere o rimuovere la colonna usando la casella di controllo **Mostra legenda** .</span><span class="sxs-lookup"><span data-stu-id="c0434-131">Add or remove by using the **Show Legend** check box.</span></span>|  
|<span data-ttu-id="c0434-132">**Popolazione**</span><span class="sxs-lookup"><span data-stu-id="c0434-132">**Population**</span></span>|<span data-ttu-id="c0434-133">Consente di visualizzare la distribuzione dell'attributo nell'intero set di dati.</span><span class="sxs-lookup"><span data-stu-id="c0434-133">Displays the distribution of the attribute across the whole dataset.</span></span>|  
|<span data-ttu-id="c0434-134">**Colonna per gli stati dell'attributo stimabile**</span><span class="sxs-lookup"><span data-stu-id="c0434-134">**Column for states of predictable attribute**</span></span>|<span data-ttu-id="c0434-135">Consente di visualizzare una colonna per ogni stato della colonna stimabile, con ogni riga corrispondente a un attributo di input nel modello.</span><span class="sxs-lookup"><span data-stu-id="c0434-135">Displays a column for each state of the predictable column, with each row corresponding to an input attribute in the model.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c0434-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c0434-136">See Also</span></span>  
 <span data-ttu-id="c0434-137">[Algoritmi di data mining &#40;Analysis Services-&#41;di data mining](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="c0434-137">[Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="c0434-138">[Visualizzatori modello di data mining &#40;Progettazione modelli di data mining&#41;](mining-model-viewers-data-mining-model-designer.md) </span><span class="sxs-lookup"><span data-stu-id="c0434-138">[Mining Model Viewers &#40;Data Mining Model Designer&#41;](mining-model-viewers-data-mining-model-designer.md) </span></span>  
 [<span data-ttu-id="c0434-139">Visualizzatori modello di data mining</span><span class="sxs-lookup"><span data-stu-id="c0434-139">Data Mining Model Viewers</span></span>](data-mining/data-mining-model-viewers.md)  
  
  
