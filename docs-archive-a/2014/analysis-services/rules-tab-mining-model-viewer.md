---
title: Scheda regole (Visualizzatore modello di data mining) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.associationrules.rules.f1
ms.assetid: 705d5492-b58f-45d9-94d7-ed57b7025823
author: minewiskan
ms.author: owend
ms.openlocfilehash: d0d86931865fd9352074669de93b14dacfc84537
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625631"
---
# <a name="rules-tab-mining-model-viewer"></a><span data-ttu-id="9e601-102">Scheda Regole (Visualizzatore modello di data mining)</span><span class="sxs-lookup"><span data-stu-id="9e601-102">Rules Tab (Mining Model Viewer)</span></span>
  <span data-ttu-id="9e601-103">Usare il riquadro **Regole** in un modello di associazione per visualizzare le regole che l'algoritmo ha consentito di estrarre dai dati.</span><span class="sxs-lookup"><span data-stu-id="9e601-103">Use the **Rules** pane in an association model to view the rules that the algorithm extracted from the data.</span></span> <span data-ttu-id="9e601-104">Nelle regole vengono descritte le modalità di correlazione tra gli elementi e di relativo utilizzo per creare indicazioni.</span><span class="sxs-lookup"><span data-stu-id="9e601-104">Rules describe how items are related to each other, and can be used to create recommendations.</span></span>  
  
 <span data-ttu-id="9e601-105">È possibile utilizzare le opzioni nel visualizzatore per filtrare il numero di regole visualizzate.</span><span class="sxs-lookup"><span data-stu-id="9e601-105">You can use the options in the viewer to filter the number of rules that are displayed in the viewer.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="9e601-106">Per impostazione predefinita, nel visualizzatore vengono mostrate solo le regole che superano la soglia di probabilità definita in **Probabilità minima** .</span><span class="sxs-lookup"><span data-stu-id="9e601-106">By default, only the rules that are above the probability threshold defined in **Minimum probability** are displayed in the viewer.</span></span> <span data-ttu-id="9e601-107">Non è possibile rendere più piccolo questo valore tramite il visualizzatore, poiché la soglia di probabilità per l'output della regola viene determinata durante la creazione del modello.</span><span class="sxs-lookup"><span data-stu-id="9e601-107">You cannot make this value any smaller by using the viewer, because the probability threshold for rule output is determined when the model is created.</span></span> <span data-ttu-id="9e601-108">Per altre informazioni, vedere [Riferimento tecnico per l'algoritmo Microsoft Association Rules](data-mining/microsoft-association-algorithm-technical-reference.md).</span><span class="sxs-lookup"><span data-stu-id="9e601-108">For more information, see [Microsoft Association Algorithm Technical Reference](data-mining/microsoft-association-algorithm-technical-reference.md).</span></span>  
  
 <span data-ttu-id="9e601-109">**Per altre informazioni:** [Algoritmo Microsoft Association Rules](data-mining/microsoft-association-algorithm.md)e [Visualizzare un modello usando il Visualizzatore Microsoft Association Rules](data-mining/browse-a-model-using-the-microsoft-association-rules-viewer.md)</span><span class="sxs-lookup"><span data-stu-id="9e601-109">**For More Information:** [Microsoft Association Algorithm](data-mining/microsoft-association-algorithm.md), [Browse a Model Using the Microsoft Association Rules Viewer](data-mining/browse-a-model-using-the-microsoft-association-rules-viewer.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="9e601-110">Opzioni</span><span class="sxs-lookup"><span data-stu-id="9e601-110">Options</span></span>  
 <span data-ttu-id="9e601-111">**Aggiorna contenuto visualizzatore**</span><span class="sxs-lookup"><span data-stu-id="9e601-111">**Refresh viewer content**</span></span>  
 <span data-ttu-id="9e601-112">Consente di ricaricare il modello di data mining nel visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="9e601-112">Reload the mining model in the viewer.</span></span>  
  
 <span data-ttu-id="9e601-113">**Modello di data mining**</span><span class="sxs-lookup"><span data-stu-id="9e601-113">**Mining Model**</span></span>  
 <span data-ttu-id="9e601-114">Fare clic su un modello di data mining da visualizzare contenuto nella struttura di data mining corrente.</span><span class="sxs-lookup"><span data-stu-id="9e601-114">Choose a mining model to view that is contained in the current mining structure.</span></span> <span data-ttu-id="9e601-115">Il modello di data mining verrà aperto nel visualizzatore associato.</span><span class="sxs-lookup"><span data-stu-id="9e601-115">The mining model will open in its associated viewer.</span></span>  
  
 <span data-ttu-id="9e601-116">**Visualizzatore**</span><span class="sxs-lookup"><span data-stu-id="9e601-116">**Viewer**</span></span>  
 <span data-ttu-id="9e601-117">Consente di scegliere un visualizzatore da utilizzare per la visualizzazione del modello di data mining selezionato.</span><span class="sxs-lookup"><span data-stu-id="9e601-117">Choose a viewer to use to view the selected mining model.</span></span> <span data-ttu-id="9e601-118">È possibile usare il visualizzatore personalizzato per ogni modello di data mining o **Microsoft Generic Content Tree Viewer**.</span><span class="sxs-lookup"><span data-stu-id="9e601-118">You can use the custom viewer for each mining model, or the **Microsoft Generic Content Tree Viewer**.</span></span> <span data-ttu-id="9e601-119">Se disponibili, è anche possibile utilizzare i visualizzatori plug-in.</span><span class="sxs-lookup"><span data-stu-id="9e601-119">You can also use plug-in viewers if available.</span></span>  
  
 <span data-ttu-id="9e601-120">**Probabilità minima**</span><span class="sxs-lookup"><span data-stu-id="9e601-120">**Minimum probability**</span></span>  
 <span data-ttu-id="9e601-121">Modificare questo valore per impostare la probabilità minima richiesta per una regola da visualizzare nel visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="9e601-121">Change this value to set the minimum probability required for a rule to be displayed in the viewer.</span></span> <span data-ttu-id="9e601-122">Aumentando il valore della probabilità verrà ridotto il numero di regole visualizzate.</span><span class="sxs-lookup"><span data-stu-id="9e601-122">Increasing the value for probability will reduce the number of rules that are displayed.</span></span>  
  
 <span data-ttu-id="9e601-123">**Priorità minima**</span><span class="sxs-lookup"><span data-stu-id="9e601-123">**Minimum importance**</span></span>  
 <span data-ttu-id="9e601-124">Modificare questo valore per impostare la priorità minima richiesta per una regola da visualizzare nel visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="9e601-124">Change this value to set the minimum importance required for a rule to be displayed in the viewer.</span></span> <span data-ttu-id="9e601-125">Aumentando il valore della priorità verrà ridotto il numero di regole visualizzate.</span><span class="sxs-lookup"><span data-stu-id="9e601-125">Increasing the value for importance will reduce the number of rules that are displayed.</span></span>  
  
 <span data-ttu-id="9e601-126">**Filtro regola**</span><span class="sxs-lookup"><span data-stu-id="9e601-126">**Filter Rule**</span></span>  
 <span data-ttu-id="9e601-127">Consente di digitare un valore stringa per filtrare il numero di regole da mostrare nel visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="9e601-127">Type a string value to filter the number of rules that appear in the viewer.</span></span>  
  
 <span data-ttu-id="9e601-128">È anche possibile digitare espressioni regolari .NET come criteri di filtro.</span><span class="sxs-lookup"><span data-stu-id="9e601-128">You can also type .NET regular expressions as filter criteria.</span></span> <span data-ttu-id="9e601-129">Ad esempio, tramite l'espressione seguente vengono restituite tutte le regole contenenti 'Road Bottle Cage' sul lato sinistro della regola:</span><span class="sxs-lookup"><span data-stu-id="9e601-129">For example, the following expression returns all rules that contain 'Road Bottle Cage' on the left side of the rule:</span></span>  
  
 `\bRoad\b.\bBottle\b.\bCage\b.*->.*`  
  
 <span data-ttu-id="9e601-130">Si noti che potrebbe essere necessario aggiornare la vista per visualizzare l'applicazione dei criteri di filtro.</span><span class="sxs-lookup"><span data-stu-id="9e601-130">Note that you might need to refresh the view to see the filter criteria apply.</span></span> <span data-ttu-id="9e601-131">È anche possibile attivare e disattivare l'opzione **Mostra nomi lunghi** per aggiornare l'elenco.</span><span class="sxs-lookup"><span data-stu-id="9e601-131">You can also toggle the **Show long name** option on and off to refresh the list.</span></span>  
  
 <span data-ttu-id="9e601-132">Per impostazione predefinita, i criteri di filtro si applicano alla combinazione nome e cognome dell'attributo-valore; pertanto, se viene visualizzato solo il nome dell'attributo, è probabile che i criteri di filtro non siano stati applicati correttamente.</span><span class="sxs-lookup"><span data-stu-id="9e601-132">By default the filter criteria applies to the full name of the attribute-value combination; therefore, if you are viewing the attribute name only, it might not be obvious that the filter criteria has applied correctly.</span></span> <span data-ttu-id="9e601-133">Usare l'elenco a discesa **Mostra** per selezionare **Mostra nome e valore dell'attributo**, quindi verificare che l'elenco di set di elementi sia filtrato correttamente.</span><span class="sxs-lookup"><span data-stu-id="9e601-133">Use the **Show** dropdown list to select **Show attribute name and value**, and verify that the list of itemsets is filtered correctly.</span></span>  
  
 <span data-ttu-id="9e601-134">**Mostra**</span><span class="sxs-lookup"><span data-stu-id="9e601-134">**Show**</span></span>  
 <span data-ttu-id="9e601-135">Consente di impostare la modalità di visualizzazione della regola nel visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="9e601-135">Adjust the way that the rule is displayed in the viewer.</span></span> <span data-ttu-id="9e601-136">È possibile selezionare una delle tre opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9e601-136">You can select one of the three following options:</span></span>  
  
-   <span data-ttu-id="9e601-137">Mostra nome e valore dell'attributo</span><span class="sxs-lookup"><span data-stu-id="9e601-137">Show the attribute name and value</span></span>  
  
-   <span data-ttu-id="9e601-138">Mostra solo il valore dell'attributo</span><span class="sxs-lookup"><span data-stu-id="9e601-138">Show the attribute value only</span></span>  
  
-   <span data-ttu-id="9e601-139">Mostra solo il nome dell'attributo</span><span class="sxs-lookup"><span data-stu-id="9e601-139">Show the attribute name only</span></span>  
  
 <span data-ttu-id="9e601-140">**Mostra nomi lunghi**</span><span class="sxs-lookup"><span data-stu-id="9e601-140">**Show long name**</span></span>  
 <span data-ttu-id="9e601-141">Consente di visualizzare il nome della regola nel modo in cui viene visualizzato nel contenuto del modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="9e601-141">Show the full name of the rule as it appears in the mining model content.</span></span>  
  
 <span data-ttu-id="9e601-142">**Numero massimo di righe**</span><span class="sxs-lookup"><span data-stu-id="9e601-142">**Maximum rows**</span></span>  
 <span data-ttu-id="9e601-143">Consente di impostare il limite del numero di regole che è possibile visualizzare nel visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="9e601-143">Limit the number of rules that are displayed in the viewer.</span></span>  
  
 <span data-ttu-id="9e601-144">**Probabilità**</span><span class="sxs-lookup"><span data-stu-id="9e601-144">**Probability**</span></span>  
 <span data-ttu-id="9e601-145">In questa colonna del grafico viene visualizzata la probabilità per ogni regola.</span><span class="sxs-lookup"><span data-stu-id="9e601-145">This column in the chart displays the probability for each rule.</span></span>  
  
 <span data-ttu-id="9e601-146">È possibile fare clic sull'intestazione di colonna per ordinare in base alla probabilità.</span><span class="sxs-lookup"><span data-stu-id="9e601-146">You can click the column heading to sort by probability.</span></span>  
  
 <span data-ttu-id="9e601-147">**Priorità**</span><span class="sxs-lookup"><span data-stu-id="9e601-147">**Importance**</span></span>  
 <span data-ttu-id="9e601-148">In questa colonna del grafico viene visualizzata la priorità per ogni regola.</span><span class="sxs-lookup"><span data-stu-id="9e601-148">This column in the chart displays the importance for each rule.</span></span>  
  
 <span data-ttu-id="9e601-149">È possibile fare clic sull'intestazione di colonna per ordinare in base alla priorità.</span><span class="sxs-lookup"><span data-stu-id="9e601-149">You can click the column heading to sort by importance.</span></span>  
  
 <span data-ttu-id="9e601-150">**Regola**</span><span class="sxs-lookup"><span data-stu-id="9e601-150">**Rule**</span></span>  
 <span data-ttu-id="9e601-151">In questa colonna del grafico viene visualizzata la descrizione per ogni regola, in base al formato specificato tramite le opzioni **Mostra** e **Mostra nomi lunghi**.</span><span class="sxs-lookup"><span data-stu-id="9e601-151">This column in the chart displays the text description for each rule, according to the format specified by using the options, **Show** and **Show long name**.</span></span>  
  
 <span data-ttu-id="9e601-152">È possibile fare clic sull'intestazione di colonna per ordinare in base al testo della regola.</span><span class="sxs-lookup"><span data-stu-id="9e601-152">You can click the column heading to sort by the text of the rule.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e601-153">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9e601-153">See Also</span></span>  
 <span data-ttu-id="9e601-154">[Algoritmi di data mining &#40;Analysis Services-&#41;di data mining](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="9e601-154">[Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="9e601-155">[Visualizzatori modello di data mining &#40;Progettazione modelli di data mining&#41;](mining-model-viewers-data-mining-model-designer.md) </span><span class="sxs-lookup"><span data-stu-id="9e601-155">[Mining Model Viewers &#40;Data Mining Model Designer&#41;](mining-model-viewers-data-mining-model-designer.md) </span></span>  
 [<span data-ttu-id="9e601-156">Visualizzatori modello di data mining</span><span class="sxs-lookup"><span data-stu-id="9e601-156">Data Mining Model Viewers</span></span>](data-mining/data-mining-model-viewers.md)  
  
  
