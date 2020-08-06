---
title: Scheda set di elementi (Visualizzatore modello di data mining) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.associationrules.itemsets.f1
ms.assetid: 95b2b805-b142-4064-9c80-4b1b3fe2fe63
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2b99b62b01b196fd62e1ef264e530487018f6a60
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625665"
---
# <a name="itemsets-tab-mining-model-viewer"></a><span data-ttu-id="c81a2-102">Scheda Set di elementi (Visualizzatore modello di data mining)</span><span class="sxs-lookup"><span data-stu-id="c81a2-102">Itemsets Tab (Mining Model Viewer)</span></span>
  <span data-ttu-id="c81a2-103">È possibile usare il riquadro **Set di elementi** per visualizzare i set di elementi frequenti inclusi in un modello di data mining delle regole di associazione.</span><span class="sxs-lookup"><span data-stu-id="c81a2-103">You can use the **Itemsets** pane to view the frequent itemsets that an association rules mining model contains.</span></span> <span data-ttu-id="c81a2-104">Poiché in un modello di associazione possono essere inclusi molti set di elementi, i controlli vengono forniti nel visualizzatore come supporto per filtrare i set di elementi mostrati nel visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="c81a2-104">Because an association model can contain many itemsets, controls are provided in the viewer to help you filter the itemsets that are displayed in the viewer.</span></span>  
  
 <span data-ttu-id="c81a2-105">**Per altre informazioni:** [Algoritmo Microsoft Association Rules](data-mining/microsoft-association-algorithm.md)e [Visualizzare un modello usando il Visualizzatore Microsoft Association Rules](data-mining/browse-a-model-using-the-microsoft-association-rules-viewer.md)</span><span class="sxs-lookup"><span data-stu-id="c81a2-105">**For More Information:** [Microsoft Association Algorithm](data-mining/microsoft-association-algorithm.md), [Browse a Model Using the Microsoft Association Rules Viewer](data-mining/browse-a-model-using-the-microsoft-association-rules-viewer.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="c81a2-106">Opzioni</span><span class="sxs-lookup"><span data-stu-id="c81a2-106">Options</span></span>  
 <span data-ttu-id="c81a2-107">**Aggiorna contenuto visualizzatore**</span><span class="sxs-lookup"><span data-stu-id="c81a2-107">**Refresh viewer content**</span></span>  
 <span data-ttu-id="c81a2-108">Consente di ricaricare il modello di data mining nel visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="c81a2-108">Reload the mining model in the viewer.</span></span>  
  
 <span data-ttu-id="c81a2-109">**Modello di data mining**</span><span class="sxs-lookup"><span data-stu-id="c81a2-109">**Mining Model**</span></span>  
 <span data-ttu-id="c81a2-110">Fare clic su un modello di data mining da visualizzare contenuto nella struttura di data mining corrente.</span><span class="sxs-lookup"><span data-stu-id="c81a2-110">Choose a mining model to view that is contained in the current mining structure.</span></span> <span data-ttu-id="c81a2-111">Il modello di data mining verrà aperto nel visualizzatore associato.</span><span class="sxs-lookup"><span data-stu-id="c81a2-111">The mining model will open in its associated viewer.</span></span>  
  
 <span data-ttu-id="c81a2-112">**Visualizzatore**</span><span class="sxs-lookup"><span data-stu-id="c81a2-112">**Viewer**</span></span>  
 <span data-ttu-id="c81a2-113">Consente di scegliere un visualizzatore da utilizzare per la visualizzazione del modello di data mining selezionato.</span><span class="sxs-lookup"><span data-stu-id="c81a2-113">Choose a viewer to use to view the selected mining model.</span></span> <span data-ttu-id="c81a2-114">È possibile utilizzare il visualizzatore personalizzato per i modelli di associazione o [!INCLUDE[msCoName](../includes/msconame-md.md)] Generic Content Tree Viewer.</span><span class="sxs-lookup"><span data-stu-id="c81a2-114">You can use either the custom viewer for association models, or the [!INCLUDE[msCoName](../includes/msconame-md.md)] Generic Content Tree viewer.</span></span> <span data-ttu-id="c81a2-115">Se disponibili, è anche possibile utilizzare i visualizzatori plug-in.</span><span class="sxs-lookup"><span data-stu-id="c81a2-115">You can also use plug-in viewers if available.</span></span>  
  
 <span data-ttu-id="c81a2-116">**Supporto minimo**</span><span class="sxs-lookup"><span data-stu-id="c81a2-116">**Minimum support**</span></span>  
 <span data-ttu-id="c81a2-117">Modificare questo valore per impostare il supporto minimo che può essere contenuto in un set di elementi da visualizzare nel visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="c81a2-117">Change this value to set the minimum support that an itemset must contain to appear in the viewer.</span></span> <span data-ttu-id="c81a2-118">Il valore predefinito visualizzato alla prima apertura del modello è calcolato dal modello, tuttavia è possibile modificarlo per vedere un numero maggiore o inferiore di set di elementi.</span><span class="sxs-lookup"><span data-stu-id="c81a2-118">The default value that is displayed when you first open the model is calculated by the model, but you can change it to see more or fewer itemsets.</span></span>  
  
 <span data-ttu-id="c81a2-119">**Dimensioni minime set di elementi**</span><span class="sxs-lookup"><span data-stu-id="c81a2-119">**Minimum itemset size**</span></span>  
 <span data-ttu-id="c81a2-120">Modificare questo valore per impostare il numero minimo di elementi che devono essere inclusi in un set di elementi prima che quest'ultimo possa essere visualizzato nel visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="c81a2-120">Change this value to set the minimum number of items that must be included in an itemset before the itemset can be displayed in the viewer.</span></span>  
  
 <span data-ttu-id="c81a2-121">**Filtra set di elementi**</span><span class="sxs-lookup"><span data-stu-id="c81a2-121">**Filter Itemset**</span></span>  
 <span data-ttu-id="c81a2-122">Consente di digitare un valore stringa per filtrare il numero di set di elementi da mostrare nel visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="c81a2-122">Type a string value to filter the number of itemsets that appear in the viewer.</span></span>  
  
 <span data-ttu-id="c81a2-123">È anche possibile digitare espressioni regolari .NET come criteri di filtro.</span><span class="sxs-lookup"><span data-stu-id="c81a2-123">You can also type .NET regular expressions as filter criteria.</span></span> <span data-ttu-id="c81a2-124">Ad esempio, tramite l'espressione seguente vengono restituiti tutti i set di elementi contenenti 'Road Bottle Cage':</span><span class="sxs-lookup"><span data-stu-id="c81a2-124">For example, the following expression returns all itemsets that contain 'Road Bottle Cage':</span></span>  
  
 `\bRoad\b.\bBottle\b.\bCage\b.*`  
  
 <span data-ttu-id="c81a2-125">Si noti che potrebbe essere necessario aggiornare la vista per visualizzare l'applicazione dei criteri di filtro.</span><span class="sxs-lookup"><span data-stu-id="c81a2-125">Note that you might need to refresh the view to see the filter criteria apply.</span></span> <span data-ttu-id="c81a2-126">È anche possibile attivare e disattivare l'opzione **Mostra nomi lunghi** per aggiornare l'elenco.</span><span class="sxs-lookup"><span data-stu-id="c81a2-126">You can also toggle the **Show long name** option on and off to refresh the list.</span></span>  
  
 <span data-ttu-id="c81a2-127">Per impostazione predefinita, i criteri di filtro si applicano alla combinazione nome e cognome dell'attributo-valore; pertanto, se viene visualizzato solo il nome dell'attributo, è probabile che i criteri di filtro non siano stati applicati correttamente.</span><span class="sxs-lookup"><span data-stu-id="c81a2-127">By default the filter criteria applies to the full name of the attribute-value combination; therefore, if you are viewing the attribute name only, it might not be obvious that the filter criteria has applied correctly.</span></span> <span data-ttu-id="c81a2-128">Usare l'elenco a discesa **Mostra** per selezionare **Mostra nome e valore dell'attributo**, quindi verificare che l'elenco di set di elementi sia filtrato correttamente.</span><span class="sxs-lookup"><span data-stu-id="c81a2-128">Use the **Show** dropdown list to select **Show attribute name and value**, and verify that the list of itemsets is filtered correctly.</span></span>  
  
 <span data-ttu-id="c81a2-129">**Mostra**</span><span class="sxs-lookup"><span data-stu-id="c81a2-129">**Show**</span></span>  
 <span data-ttu-id="c81a2-130">Consente di impostare la modalità di visualizzazione del set di elementi nel visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="c81a2-130">Adjust how the itemset is displayed in the viewer.</span></span> <span data-ttu-id="c81a2-131">È possibile selezionare una delle tre opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c81a2-131">You can select one of the three following options:</span></span>  
  
-   <span data-ttu-id="c81a2-132">Mostra nome e valore dell'attributo</span><span class="sxs-lookup"><span data-stu-id="c81a2-132">Show attribute name and value</span></span>  
  
-   <span data-ttu-id="c81a2-133">Mostra solo il valore dell'attributo</span><span class="sxs-lookup"><span data-stu-id="c81a2-133">Show attribute value only</span></span>  
  
-   <span data-ttu-id="c81a2-134">Mostra solo il nome dell'attributo</span><span class="sxs-lookup"><span data-stu-id="c81a2-134">Show attribute name only</span></span>  
  
 <span data-ttu-id="c81a2-135">Si noti che questa opzione non consente di eseguire nuovamente una query sul modello, ma solo di filtrare gli attributi o i valori visualizzati.</span><span class="sxs-lookup"><span data-stu-id="c81a2-135">Note that this option does not requery the model; it only filters the attributes or values that are displayed.</span></span>  
  
 <span data-ttu-id="c81a2-136">**Mostra nomi lunghi**</span><span class="sxs-lookup"><span data-stu-id="c81a2-136">**Show long name**</span></span>  
 <span data-ttu-id="c81a2-137">Selezionare questa opzione per visualizzare il nome completo del set di elementi come viene visualizzato nel contenuto del modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="c81a2-137">Select this option to display the full name of the itemset as it appears in the mining model content.</span></span>  
  
 <span data-ttu-id="c81a2-138">**Numero massimo di righe**</span><span class="sxs-lookup"><span data-stu-id="c81a2-138">**Maximum rows**</span></span>  
 <span data-ttu-id="c81a2-139">Consente di impostare il limite del numero di set di elementi che è possibile visualizzare.</span><span class="sxs-lookup"><span data-stu-id="c81a2-139">Limit the number of itemsets that are displayed in the viewer.</span></span> <span data-ttu-id="c81a2-140">Per impostazione predefinita, i set di elementi vengono ordinati per supporto in modo decrescente, pertanto abbassando questo valore, l'elenco viene limitato ai set di elementi più comuni.</span><span class="sxs-lookup"><span data-stu-id="c81a2-140">By default, itemsets are ordered by support in descending order, so lowering this value restricts the list to the most common itemsets.</span></span>  
  
 <span data-ttu-id="c81a2-141">**Supporto**</span><span class="sxs-lookup"><span data-stu-id="c81a2-141">**Support**</span></span>  
 <span data-ttu-id="c81a2-142">Consente di visualizzare il supporto per ogni set di elementi.</span><span class="sxs-lookup"><span data-stu-id="c81a2-142">Displays the support for each itemset.</span></span>  
  
 <span data-ttu-id="c81a2-143">**Dimensione**</span><span class="sxs-lookup"><span data-stu-id="c81a2-143">**Size**</span></span>  
 <span data-ttu-id="c81a2-144">Consente di visualizzare il numero di elementi esistenti in ogni set.</span><span class="sxs-lookup"><span data-stu-id="c81a2-144">Displays the number of items that exist in each itemset.</span></span>  
  
 <span data-ttu-id="c81a2-145">**Set di elementi**</span><span class="sxs-lookup"><span data-stu-id="c81a2-145">**Itemset**</span></span>  
 <span data-ttu-id="c81a2-146">Consente di visualizzare la descrizione di ogni set di elementi.</span><span class="sxs-lookup"><span data-stu-id="c81a2-146">Displays the description of each itemset.</span></span> <span data-ttu-id="c81a2-147">Per impostazione predefinita, i set di elementi vengono presentati come un elenco delimitato da virgole di attributi e dei relativi valori.</span><span class="sxs-lookup"><span data-stu-id="c81a2-147">By default, itemsets are presented as a comma-delimited list of attributes and their values.</span></span> <span data-ttu-id="c81a2-148">È possibile modificare la modalità di visualizzazione tramite l'opzione **Mostra** .</span><span class="sxs-lookup"><span data-stu-id="c81a2-148">You can change the way they are displayed by using the **Show** option.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c81a2-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c81a2-149">See Also</span></span>  
 <span data-ttu-id="c81a2-150">[Algoritmi di data mining &#40;Analysis Services-&#41;di data mining](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="c81a2-150">[Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="c81a2-151">[Visualizzatori modello di data mining &#40;Progettazione modelli di data mining&#41;](mining-model-viewers-data-mining-model-designer.md) </span><span class="sxs-lookup"><span data-stu-id="c81a2-151">[Mining Model Viewers &#40;Data Mining Model Designer&#41;](mining-model-viewers-data-mining-model-designer.md) </span></span>  
 [<span data-ttu-id="c81a2-152">Visualizzatori modello di data mining</span><span class="sxs-lookup"><span data-stu-id="c81a2-152">Data Mining Model Viewers</span></span>](data-mining/data-mining-model-viewers.md)  
  
  
