---
title: Progettazione modelli di data mining | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data mining [Analysis Services], structure
- mining structures [Analysis Services], modifying
- data mining editor [Analysis Services]
- Data Mining Designer
- data mining [Analysis Services], modifying
ms.assetid: 2540db5b-2bf3-4b6c-87c8-79c48d71acce
author: minewiskan
ms.author: owend
ms.openlocfilehash: 820cde158dfabff525081060369daace0e83c8dc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624434"
---
# <a name="data-mining-designer"></a><span data-ttu-id="4d5b9-102">Data Mining Designer</span><span class="sxs-lookup"><span data-stu-id="4d5b9-102">Data Mining Designer</span></span>
  <span data-ttu-id="4d5b9-103">Progettazione modelli di data mining è l'ambiente principale in cui si utilizzano i modelli di data mining in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4d5b9-103">Data Mining Designer is the primary environment in which you work with mining models in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="4d5b9-104">È possibile accedere alla finestra di progettazione selezionando una struttura di data mining esistente o utilizzando la Creazione guidata modello di data mining per creare una nuova struttura e un nuovo modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="4d5b9-104">You can access the designer either by selecting an existing mining structure, or by using the Data Mining Wizard to create a new mining structure and mining model.</span></span> <span data-ttu-id="4d5b9-105">Progettazione modelli di data mining consente di eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="4d5b9-105">You can use Data Mining Designer to perform the following tasks:</span></span>  
  
-   <span data-ttu-id="4d5b9-106">Modificare la struttura e il modello di data mining creati inizialmente dalla Creazione guidata modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="4d5b9-106">Modify the mining structure and the mining model that were initially created by the Data Mining Wizard.</span></span>  
  
-   <span data-ttu-id="4d5b9-107">Creare nuovi modelli basati su una struttura di data mining esistente.</span><span class="sxs-lookup"><span data-stu-id="4d5b9-107">Create new models based on an existing mining structure.</span></span>  
  
-   <span data-ttu-id="4d5b9-108">Eseguire il training dei modelli di data mining e visualizzarli.</span><span class="sxs-lookup"><span data-stu-id="4d5b9-108">Train and browse mining models.</span></span>  
  
-   <span data-ttu-id="4d5b9-109">Confrontare i modelli mediante grafici di accuratezza.</span><span class="sxs-lookup"><span data-stu-id="4d5b9-109">Compare models by using accuracy charts.</span></span>  
  
-   <span data-ttu-id="4d5b9-110">Creare query di stima basate sui modelli di data mining.</span><span class="sxs-lookup"><span data-stu-id="4d5b9-110">Create prediction queries based on mining models.</span></span>  
  
## <a name="mining-structure-tab"></a><span data-ttu-id="4d5b9-111">Scheda Struttura di data mining</span><span class="sxs-lookup"><span data-stu-id="4d5b9-111">Mining Structure Tab</span></span>  
 <span data-ttu-id="4d5b9-112">Usare la scheda **Struttura di data mining** per aggiungere colonne e modificare le proprietà di una struttura di data mining esistente.</span><span class="sxs-lookup"><span data-stu-id="4d5b9-112">Use the **Mining Structure** tab to add columns and modify the properties of an existing mining structure.</span></span> <span data-ttu-id="4d5b9-113">Negli argomenti e nelle attività seguenti sono disponibili ulteriori informazioni sull'utilizzo delle strutture di data mining:</span><span class="sxs-lookup"><span data-stu-id="4d5b9-113">The following tasks and topics provide more information about working with mining structures:</span></span>  
  
 [<span data-ttu-id="4d5b9-114">Strutture di data mining &#40;Analysis Services - Data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="4d5b9-114">Mining Structures &#40;Analysis Services - Data Mining&#41;</span></span>](mining-structures-analysis-services-data-mining.md)  
  
 [<span data-ttu-id="4d5b9-115">Attività e procedure relative alla struttura di data mining</span><span class="sxs-lookup"><span data-stu-id="4d5b9-115">Mining Structure Tasks and How-tos</span></span>](mining-structure-tasks-and-how-tos.md)  
  
## <a name="mining-models-tab"></a><span data-ttu-id="4d5b9-116">Scheda Modelli di data mining</span><span class="sxs-lookup"><span data-stu-id="4d5b9-116">Mining Models Tab</span></span>  
 <span data-ttu-id="4d5b9-117">La scheda **Modelli di data mining** consente di gestire i modelli di data mining esistenti e di creare nuovi modelli.</span><span class="sxs-lookup"><span data-stu-id="4d5b9-117">Use the **Mining Models** tab to manage existing mining models and to create new models.</span></span> <span data-ttu-id="4d5b9-118">I modelli di data mining sono sempre basati su una struttura di data mining esistente.</span><span class="sxs-lookup"><span data-stu-id="4d5b9-118">Mining models are always based on an existing mining structure .</span></span>  
  
 <span data-ttu-id="4d5b9-119">Nella scheda **Modelli di data mining** è possibile modificare il tipo di algoritmo, aggiungere o rimuovere le colonne associate alla struttura del modello, modificare le proprietà delle colonne specifiche dell'algoritmo, specificare l'utilizzo delle colonne del modello di data mining e modificare i parametri dell'algoritmo associati al modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="4d5b9-119">In the **Mining Models** tab, you can change the algorithm type, add or remove columns that are associated with the model structure, adjust algorithm-specific column properties, specify the mining model column usage, and adjust algorithm parameters that are associated with the mining model.</span></span> <span data-ttu-id="4d5b9-120">È inoltre possibile elaborare la struttura di data mining insieme ai modelli selezionati o a tutti i modelli associati.</span><span class="sxs-lookup"><span data-stu-id="4d5b9-120">You can also process the mining structure together with selected models or with all the associated models.</span></span>  
  
 <span data-ttu-id="4d5b9-121">Per ulteriori informazioni su come utilizzare i modelli di data mining, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="4d5b9-121">See the following topics for more information about working with mining models:</span></span>  
  
 [<span data-ttu-id="4d5b9-122">Modelli di data mining &#40;Analysis Services - Data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="4d5b9-122">Mining Models &#40;Analysis Services - Data Mining&#41;</span></span>](mining-models-analysis-services-data-mining.md)  
  
 [<span data-ttu-id="4d5b9-123">Attività e procedure relative al modello di data mining</span><span class="sxs-lookup"><span data-stu-id="4d5b9-123">Mining Model Tasks and How-tos</span></span>](mining-model-tasks-and-how-tos.md)  
  
## <a name="mining-model-viewer-tab"></a><span data-ttu-id="4d5b9-124">Scheda Visualizzatore modello di data mining</span><span class="sxs-lookup"><span data-stu-id="4d5b9-124">Mining Model Viewer Tab</span></span>  
 <span data-ttu-id="4d5b9-125">La scheda **Visualizzatore modello di data mining** consente l'esplorazione visiva dei modelli di data mining.</span><span class="sxs-lookup"><span data-stu-id="4d5b9-125">Use the **Mining Model Viewer** tab to visually explore your mining models.</span></span> <span data-ttu-id="4d5b9-126">Ogni modello di data mining è associato a un visualizzatore personalizzato che mostra il contenuto specifico di tale modello.</span><span class="sxs-lookup"><span data-stu-id="4d5b9-126">Each mining model is associated with a custom viewer that displays content that is specific to that model.</span></span> <span data-ttu-id="4d5b9-127">È inoltre possibile visualizzare il contenuto del modello di data mining tramite il visualizzatore del contenuto.</span><span class="sxs-lookup"><span data-stu-id="4d5b9-127">You can also view mining model content by using the content viewer.</span></span>  
  
 <span data-ttu-id="4d5b9-128">Per ulteriori informazioni su come esplorare i modelli di data mining con i visualizzatori di data mining, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="4d5b9-128">See the following topics for more information about exploring mining models with the data mining viewers:</span></span>  
  
 [<span data-ttu-id="4d5b9-129">Visualizzatori modello di data mining</span><span class="sxs-lookup"><span data-stu-id="4d5b9-129">Data Mining Model Viewers</span></span>](data-mining-model-viewers.md)  
  
 [<span data-ttu-id="4d5b9-130">Attività e procedure relative al visualizzatore modello di data mining</span><span class="sxs-lookup"><span data-stu-id="4d5b9-130">Mining Model Viewer Tasks and How-tos</span></span>](mining-model-viewer-tasks-and-how-tos.md)  
  
## <a name="mining-accuracy-chart-tab"></a><span data-ttu-id="4d5b9-131">Scheda Grafico accuratezza modello di data mining</span><span class="sxs-lookup"><span data-stu-id="4d5b9-131">Mining Accuracy Chart Tab</span></span>  
 <span data-ttu-id="4d5b9-132">La scheda **Grafico accuratezza modello di data mining** consente di eseguire il test di accuratezza predittiva di un singolo modello di data mining o di confrontare la validità di più modelli di data mining contenuti in una struttura di data mining.</span><span class="sxs-lookup"><span data-stu-id="4d5b9-132">Use the **Mining Accuracy Chart** tab to test the predictive accuracy of a single mining model, or to compare the effectiveness of multiple mining models contained within a mining structure.</span></span> <span data-ttu-id="4d5b9-133">La scheda contiene strumenti per il filtraggio dei dati, la selezione dei modelli di data mining e la visualizzazione dei risultati in un grafico di accuratezza, in un grafico dei profitti o in una matrice di classificazione.</span><span class="sxs-lookup"><span data-stu-id="4d5b9-133">The tab contains tools for filtering the data, selecting mining models, and displaying the results in a lift chart, profit chart, or classification matrix.</span></span>  
  
 <span data-ttu-id="4d5b9-134">Per ulteriori informazioni sull'esecuzione di test e la convalida di modelli di data mining, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="4d5b9-134">See the following topics for more information about testing and validating mining models:</span></span>  
  
 [<span data-ttu-id="4d5b9-135">Test e convalida &#40;Data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="4d5b9-135">Testing and Validation &#40;Data Mining&#41;</span></span>](testing-and-validation-data-mining.md)  
  
 [<span data-ttu-id="4d5b9-136">Attività e procedure di test e convalida &#40;data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="4d5b9-136">Testing and Validation Tasks and How-tos &#40;Data Mining&#41;</span></span>](testing-and-validation-tasks-and-how-tos-data-mining.md)  
  
## <a name="mining-model-prediction-tab"></a><span data-ttu-id="4d5b9-137">Scheda Stima modello di data mining</span><span class="sxs-lookup"><span data-stu-id="4d5b9-137">Mining Model Prediction Tab</span></span>  
 <span data-ttu-id="4d5b9-138">La scheda **Stima modello di data mining** include il generatore delle query di stima, che consente di creare query di stima DMX (Data Mining Extensions).</span><span class="sxs-lookup"><span data-stu-id="4d5b9-138">The **Mining Model Prediction** tab includes Prediction Query Builder, which you can use to create a Data Mining Extensions (DMX) prediction query.</span></span> <span data-ttu-id="4d5b9-139">La scheda contiene strumenti per l'impostazione dei modelli di data mining e delle tabelle di input, il mapping tra le colonne del modello di data mining e le colonne della tabella di input, l'aggiunta di funzioni a una query e l'impostazione di criteri per ogni colonna.</span><span class="sxs-lookup"><span data-stu-id="4d5b9-139">The tab contains tools for specifying mining models and input tables, mapping the columns in the mining model to columns in the input table, adding functions to a query, and specifying criteria for each column.</span></span>  
  
 <span data-ttu-id="4d5b9-140">Dopo aver progettato una query, è possibile utilizzare viste diverse nella scheda per visualizzare i risultati della query e modificarla manualmente.</span><span class="sxs-lookup"><span data-stu-id="4d5b9-140">After you design a query, you can use different views in the tab to display the results of the query and to modify the query manually.</span></span> <span data-ttu-id="4d5b9-141">È inoltre possibile salvare i risultati della query in una tabella di un database.</span><span class="sxs-lookup"><span data-stu-id="4d5b9-141">You can also save the results of the query to a table in a database.</span></span>  
  
 <span data-ttu-id="4d5b9-142">Per ulteriori informazioni sulla creazione di query di data mining, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="4d5b9-142">See the following topics for more information about creating data mining queries:</span></span>  
  
 [<span data-ttu-id="4d5b9-143">Query di data mining</span><span class="sxs-lookup"><span data-stu-id="4d5b9-143">Data Mining Queries</span></span>](data-mining-queries.md)  
  
 [<span data-ttu-id="4d5b9-144">Attività e procedure relative alle query di data mining</span><span class="sxs-lookup"><span data-stu-id="4d5b9-144">Data Mining Query Tasks and How-tos</span></span>](data-mining-query-tasks-and-how-tos.md)  
  
## <a name="see-also"></a><span data-ttu-id="4d5b9-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4d5b9-145">See Also</span></span>  
 [<span data-ttu-id="4d5b9-146">Soluzioni di data mining</span><span class="sxs-lookup"><span data-stu-id="4d5b9-146">Data Mining Solutions</span></span>](data-mining-solutions.md)  
  
  
