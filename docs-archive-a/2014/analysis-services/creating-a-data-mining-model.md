---
title: Creazione di un modello di data mining | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data mining models, creating
- forecasting [data mining]
- mining models, creating
- clustering [data mining]
- association [data mining]
- data modeling [data mining]
- estimation
- classification [data mining]
ms.assetid: 804b7db3-1f6a-4f73-a81d-bbe02520d7c6
author: minewiskan
ms.author: owend
ms.openlocfilehash: 1e27739d3733c0b48dc6cff3e83e01f9cb12bce7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629650"
---
# <a name="creating-a-data-mining-model"></a><span data-ttu-id="4dd71-102">Creazione di un modello di data mining</span><span class="sxs-lookup"><span data-stu-id="4dd71-102">Creating a Data Mining Model</span></span>
  <span data-ttu-id="4dd71-103">La modellazione dei dati è il passaggio di data mining in cui è possibile creare modelli e tendenze applicando *algoritmi* ai dati.</span><span class="sxs-lookup"><span data-stu-id="4dd71-103">Data modeling is the step of data mining where you build patterns and trends by applying *algorithms* to data.</span></span> <span data-ttu-id="4dd71-104">Successivamente è possibile utilizzare tali modelli per l'analisi o per eseguire stime.</span><span class="sxs-lookup"><span data-stu-id="4dd71-104">Later you can use those patterns for analysis, or to make predictions.</span></span>  
  
 <span data-ttu-id="4dd71-105">I componenti aggiuntivi Data mining per Office supportano il data mining tramite le procedure guidate che semplificano la creazione di modelli.</span><span class="sxs-lookup"><span data-stu-id="4dd71-105">The Data Mining Add-ins for Office support data mining through wizards that make it easy to create models.</span></span> <span data-ttu-id="4dd71-106">Le procedure guidate consentono di analizzare i dati, identificare le correlazioni, calcolare il significato statistico di tutte le variabili e selezionare automaticamente il modello migliore.</span><span class="sxs-lookup"><span data-stu-id="4dd71-106">The wizards analyze the data, identify correlations, compute statistical significance of all variables, and automatically select the best model.</span></span>  
  
 <span data-ttu-id="4dd71-107">Sebbene questa funzionalità sia molto potente quanto gli strumenti data mining forniti da [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] e [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] , la combinazione di procedure guidate e la nota interfaccia di Excel semplifica la creazione, la modifica e l'utilizzo di data mining.</span><span class="sxs-lookup"><span data-stu-id="4dd71-107">Although this functionality is every bit as powerful as the data mining tools provided by [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] and [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], the combination of wizards and the familiar Excel interface makes it easy to create, modify, and use data mining.</span></span>  
  
## <a name="advanced-data-mining"></a><span data-ttu-id="4dd71-108">Avanzate (Data mining)</span><span class="sxs-lookup"><span data-stu-id="4dd71-108">Advanced (Data Mining)</span></span>  
 <span data-ttu-id="4dd71-109">Le procedure guidate avanzate consentono di creare nuovi modelli di data mining, basati sui dati archiviati in Excel, utilizzando uno degli algoritmi di data mining in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4dd71-109">The Advanced wizards let you create new data mining models, based on data stored in Excel, by using one of the data mining algorithms in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>  
  
### <a name="create-mining-structure"></a><span data-ttu-id="4dd71-110">Crea struttura di data mining</span><span class="sxs-lookup"><span data-stu-id="4dd71-110">Create Mining Structure</span></span>  
 <span data-ttu-id="4dd71-111">La procedura guidata Crea struttura di data mining consente di compilare una nuova struttura di data mining da utilizzare come base per più modelli di data mining.</span><span class="sxs-lookup"><span data-stu-id="4dd71-111">The Create Mining Structure wizard helps you build a new data mining structure, which you can use as the basis for multiple mining models.</span></span> <span data-ttu-id="4dd71-112">La procedura guidata consente di riservare una parte dei dati da utilizzare come set di testing, in modo che sia possibile valutare tutti i modelli che utilizzano gli stessi dati in base a standard di test coerenti.</span><span class="sxs-lookup"><span data-stu-id="4dd71-112">The wizard gives you the option to set aside a portion of the data to use as a testing set, so that you can evaluate all models that use the same data according to a consistent testing standard.</span></span>  
  
 [<span data-ttu-id="4dd71-113">Creazione della struttura di data mining &#40;SQL Server i componenti aggiuntivi Data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="4dd71-113">Create Mining Structure &#40;SQL Server Data Mining Add-ins&#41;</span></span>](create-mining-structure-sql-server-data-mining-add-ins.md)  
  
### <a name="add-model-to-structure"></a><span data-ttu-id="4dd71-114">Aggiunta modello a struttura</span><span class="sxs-lookup"><span data-stu-id="4dd71-114">Add Model to Structure</span></span>  
 <span data-ttu-id="4dd71-115">La procedura guidata Aggiunta modello a struttura consente di scegliere una struttura di data mining esistente e di creare un nuovo modello di data mining per tale struttura.</span><span class="sxs-lookup"><span data-stu-id="4dd71-115">The Add Model to Structure wizard lets you choose an existing data mining structure and create a new data mining model for it.</span></span> <span data-ttu-id="4dd71-116">È possibile aggiungere più modelli di data mining a una struttura, modificando i parametri o scegliendo algoritmi di data mining diversi, nonché personalizzare l'output.</span><span class="sxs-lookup"><span data-stu-id="4dd71-116">You can add multiple mining models to a structure, changing the parameters or choosing different data mining algorithms, and customize the output.</span></span>  
  
 [<span data-ttu-id="4dd71-117">Aggiunta di un modello alla struttura &#40;componenti aggiuntivi Data mining per Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="4dd71-117">Add Model to Structure &#40;Data Mining Add-ins for Excel&#41;</span></span>](add-model-to-structure-data-mining-add-ins-for-excel.md)  
  
## <a name="analyze-key-influencers-analyze"></a><span data-ttu-id="4dd71-118">Analizza fattori di influenza chiave (Analisi)</span><span class="sxs-lookup"><span data-stu-id="4dd71-118">Analyze Key Influencers (Analyze)</span></span>  
 <span data-ttu-id="4dd71-119">Scegliere un valore della colonna o di output di interesse per consentire all'algoritmo di analizzare tutti i dati di input per identificare i fattori che influiscono maggiormente sulla destinazione.</span><span class="sxs-lookup"><span data-stu-id="4dd71-119">You choose a column or output value of interest, and then the algorithm analyzes all the input data to identify the factors that have the most influence on the target.</span></span> <span data-ttu-id="4dd71-120">Facoltativamente, è possibile creare un report che confronta due valori qualsiasi in modo da poter visualizzare i cambiamenti dei fattori di influenza.</span><span class="sxs-lookup"><span data-stu-id="4dd71-120">Optionally, you can create a report that compares any two values, so that you can see how the influencers change.</span></span>  
  
 <span data-ttu-id="4dd71-121">Lo strumento **Analizza fattori di influenza chiave** usa l'algoritmo Microsoft Naive Bayes.</span><span class="sxs-lookup"><span data-stu-id="4dd71-121">The **Analyze Key Influencers** tool uses the Microsoft Naïve Bayes algorithm.</span></span>  
  
 [<span data-ttu-id="4dd71-122">Analizzare i fattori di influenza chiave &#40;strumenti di analisi tabelle per Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="4dd71-122">Analyze Key Influencers &#40;Table Analysis Tools for Excel&#41;</span></span>](analyze-key-influencers-table-analysis-tools-for-excel.md)  
  
## <a name="associate-data-mining"></a><span data-ttu-id="4dd71-123">Associazione (Data mining)</span><span class="sxs-lookup"><span data-stu-id="4dd71-123">Associate (Data Mining)</span></span>  
 <span data-ttu-id="4dd71-124">La **procedura guidata associazione consente** di compilare un modello di associazione che rileva le associazioni tra gli elementi visualizzati in più transazioni, ad esempio in Market Basket Analysis.</span><span class="sxs-lookup"><span data-stu-id="4dd71-124">The **Associate** wizard builds an association model that detects associations between items that appear in multiple transactions: for example, in market basket analysis.</span></span>  
  
 [<span data-ttu-id="4dd71-125">Associazione guidata &#40;client di data mining per Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="4dd71-125">Associate Wizard &#40;Data Mining Client for Excel&#41;</span></span>](associate-wizard-data-mining-client-for-excel.md)  
  
## <a name="classify-data-mining"></a><span data-ttu-id="4dd71-126">Classificazione (Data mining)</span><span class="sxs-lookup"><span data-stu-id="4dd71-126">Classify (Data Mining)</span></span>  
 <span data-ttu-id="4dd71-127">La procedura guidata **classificazione** compila un modello di classificazione che analizza i fattori che hanno contribuito a un risultato di destinazione.</span><span class="sxs-lookup"><span data-stu-id="4dd71-127">The  **Classify** wizard builds a classification model that analyzes the factors that contributed to a target outcome.</span></span> <span data-ttu-id="4dd71-128">È possibile utilizzare più algoritmi con questa procedura guidata, tra cui Decision Trees, Naive Bayes e Neural Network.</span><span class="sxs-lookup"><span data-stu-id="4dd71-128">You can use multiple algorithms with this wizard, including Decision Trees, Naïve Bayes, and Neural Networks.</span></span>  
  
 [<span data-ttu-id="4dd71-129">Procedura guidata classificazione &#40;componenti aggiuntivi Data mining per Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="4dd71-129">Classify Wizard &#40;Data Mining Add-ins for Excel&#41;</span></span>](classify-wizard-data-mining-add-ins-for-excel.md)  
  
## <a name="cluster-data-mining"></a><span data-ttu-id="4dd71-130">Clustering (Data mining)</span><span class="sxs-lookup"><span data-stu-id="4dd71-130">Cluster (Data Mining)</span></span>  
 <span data-ttu-id="4dd71-131">La procedura guidata **cluster** consente di compilare un modello di clustering per rilevare gruppi di righe che condividono caratteristiche simili.</span><span class="sxs-lookup"><span data-stu-id="4dd71-131">The **Cluster** wizard builds a clustering model that detects groups of rows that share similar characteristics.</span></span> <span data-ttu-id="4dd71-132">Il clustering (talvolta denominato *segmentazione*) è una tecnica di apprendimento non supervisionata molto utile quando si tenta di comprendere i modelli e i raggruppamenti nei nuovi dati.</span><span class="sxs-lookup"><span data-stu-id="4dd71-132">Clustering (sometimes called *segmentation*) is an unsupervised learning technique that is very useful when trying to understand patterns and groupings in new data.</span></span>  
  
 <span data-ttu-id="4dd71-133">L'algoritmo Microsoft Clustering supporta diversi tipi di clustering K-medie ed Expectation Maximization (EM).</span><span class="sxs-lookup"><span data-stu-id="4dd71-133">The Microsoft Clustering algorithm supports several varieties of both K-means and Expectation maximization (EM) clustering</span></span>  
  
 <span data-ttu-id="4dd71-134">[Creazione guidata Cluster &#40;componenti aggiuntivi Data mining per&#41;Excel ](cluster-wizard-data-mining-add-ins-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="4dd71-134">[Cluster Wizard &#40;Data Mining Add-ins for Excel&#41;](cluster-wizard-data-mining-add-ins-for-excel.md).</span></span>  
  
## <a name="detect-categories-analyze"></a><span data-ttu-id="4dd71-135">Rileva categorie (Analisi)</span><span class="sxs-lookup"><span data-stu-id="4dd71-135">Detect Categories (Analyze)</span></span>  
 <span data-ttu-id="4dd71-136">Lo strumento **Rileva categorie** consente di aggiungere qualsiasi set di dati e di applicare il clustering per trovare i raggruppamenti di dati.</span><span class="sxs-lookup"><span data-stu-id="4dd71-136">The **Detect Categories** tool lets you add any data set and apply clustering to find groupings of data.</span></span> <span data-ttu-id="4dd71-137">È utile per trovare analogie e per creare gruppi da analizzare ulteriormente.</span><span class="sxs-lookup"><span data-stu-id="4dd71-137">It's useful for finding similarities and for creating groups to further analyze.</span></span>  
  
 <span data-ttu-id="4dd71-138">Lo strumento **Rileva categorie** utilizza l'algoritmo Microsoft Clustering.</span><span class="sxs-lookup"><span data-stu-id="4dd71-138">The **Detect Categories** tool uses the Microsoft Clustering algorithm.</span></span>  
  
 [<span data-ttu-id="4dd71-139">Rilevare le categorie &#40;strumenti di analisi tabelle per Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="4dd71-139">Detect Categories &#40;Table Analysis Tools for Excel&#41;</span></span>](detect-categories-table-analysis-tools-for-excel.md)  
  
## <a name="estimate-data-mining"></a><span data-ttu-id="4dd71-140">Stima (Data mining)</span><span class="sxs-lookup"><span data-stu-id="4dd71-140">Estimate (Data Mining)</span></span>  
 <span data-ttu-id="4dd71-141">La procedura guidata Stima consente di compilare un modello di stima per estrarre modelli di dati e utilizzare tali modelli per stimare valori continui numerici, di data o di ora.</span><span class="sxs-lookup"><span data-stu-id="4dd71-141">The Estimate wizard builds an estimation model that extracts data patterns and uses the patterns to predict continuous numeric, date, or time values.</span></span> <span data-ttu-id="4dd71-142">Per la creazione del modello viene utilizzato l'algoritmo [!INCLUDE[msCoName](../includes/msconame-md.md)] Decision Trees.</span><span class="sxs-lookup"><span data-stu-id="4dd71-142">It uses the [!INCLUDE[msCoName](../includes/msconame-md.md)] Decision Trees algorithm.</span></span>  
  
 [<span data-ttu-id="4dd71-143">Procedura guidata stima &#40;componenti aggiuntivi Data mining per Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="4dd71-143">Estimate Wizard &#40;Data Mining Add-ins for Excel&#41;</span></span>](estimate-wizard-data-mining-add-ins-for-excel.md)  
  
## <a name="fill-from-example-analyze"></a><span data-ttu-id="4dd71-144">Estendi da esempio (Analisi)</span><span class="sxs-lookup"><span data-stu-id="4dd71-144">Fill From Example (Analyze)</span></span>  
 <span data-ttu-id="4dd71-145">Lo strumento **Compila da esempio consente di** imputare i valori mancanti.</span><span class="sxs-lookup"><span data-stu-id="4dd71-145">The **Fill From Example** tool helps you impute missing values.</span></span> <span data-ttu-id="4dd71-146">Fornire alcuni esempi dei valori mancanti per consentire allo strumento di compilare i modelli in base a tutti i dati nella tabella e quindi di consigliare i nuovi valori in base ai modelli nei dati.</span><span class="sxs-lookup"><span data-stu-id="4dd71-146">You provide some examples of what the missing values should be, and the tool builds patterns based on all data in the table, and then recommends new values based on patterns in the data.</span></span>  
  
 <span data-ttu-id="4dd71-147">Lo strumento **Compila da esempio** usa l'algoritmo di regressione logistica Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4dd71-147">The **Fill From Example** tool uses the Microsoft Logistic Regression algorithm.</span></span>  
  
 [<span data-ttu-id="4dd71-148">Da esempio &#40;strumenti di analisi tabelle per Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="4dd71-148">Fill From Example &#40;Table Analysis Tools for Excel&#41;</span></span>](fill-from-example-table-analysis-tools-for-excel.md)  
  
## <a name="forecast-analyze"></a><span data-ttu-id="4dd71-149">Previsione (Analisi)</span><span class="sxs-lookup"><span data-stu-id="4dd71-149">Forecast (Analyze)</span></span>  
 <span data-ttu-id="4dd71-150">Lo strumento **previsione** prende i dati che cambiano nel tempo e stima i valori futuri.</span><span class="sxs-lookup"><span data-stu-id="4dd71-150">The **Forecast** tool takes data that changes over time, and predicts future values.</span></span>  
  
 <span data-ttu-id="4dd71-151">Lo strumento **previsione** utilizza l'algoritmo Microsoft Time Series.</span><span class="sxs-lookup"><span data-stu-id="4dd71-151">The **Forecast** tool uses the Microsoft Time Series algorithm.</span></span>  
  
 [<span data-ttu-id="4dd71-152">Strumenti di analisi tabelle di previsione &#40;per Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="4dd71-152">Forecast &#40;Table Analysis Tools for Excel&#41;</span></span>](forecast-table-analysis-tools-for-excel.md)  
  
## <a name="forecast-data-mining"></a><span data-ttu-id="4dd71-153">Previsione (Data mining)</span><span class="sxs-lookup"><span data-stu-id="4dd71-153">Forecast (Data Mining)</span></span>  
 <span data-ttu-id="4dd71-154">La procedura guidata **previsione** consente di compilare un modello di previsione per rilevare modelli in una serie di celle e quindi prevedere valori aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="4dd71-154">The **Forecast** wizard builds a forecasting model that detects patterns in a series of cells, and then forecasts additional values.</span></span>  
  
 [<span data-ttu-id="4dd71-155">Procedura guidata previsione &#40;componenti aggiuntivi Data mining per Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="4dd71-155">Forecast Wizard &#40;Data Mining Add-ins for Excel&#41;</span></span>](forecast-wizard-data-mining-add-ins-for-excel.md)  
  
## <a name="highlight-exceptions-analyze"></a><span data-ttu-id="4dd71-156">Evidenzia eccezioni (Analisi)</span><span class="sxs-lookup"><span data-stu-id="4dd71-156">Highlight Exceptions (Analyze)</span></span>  
 <span data-ttu-id="4dd71-157">Lo strumento **Evidenzia eccezioni** consente di analizzare i modelli in una tabella di dati e di trovare le righe e i valori che non rientrano nel modello.</span><span class="sxs-lookup"><span data-stu-id="4dd71-157">The **Highlight Exceptions** tool analyzes patterns in a table of data and finds rows and values that don't fit the pattern.</span></span> <span data-ttu-id="4dd71-158">È quindi possibile esaminarli e correggerli e infine rieseguire il modello o contrassegnare i valori per un'azione successiva.</span><span class="sxs-lookup"><span data-stu-id="4dd71-158">You can then review and correct them and rerun the model, or flag values for later action.</span></span>  
  
 <span data-ttu-id="4dd71-159">Lo strumento **Evidenzia eccezioni** utilizza l'algoritmo Microsoft Clustering.</span><span class="sxs-lookup"><span data-stu-id="4dd71-159">The **Highlight Exceptions** tool uses the Microsoft Clustering algorithm.</span></span>  
  
 [<span data-ttu-id="4dd71-160">Evidenziare le eccezioni &#40;strumenti di analisi tabelle per Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="4dd71-160">Highlight Exceptions &#40;Table Analysis Tools for Excel&#41;</span></span>](highlight-exceptions-table-analysis-tools-for-excel.md)  
  
## <a name="prediction-calculator-analyze"></a><span data-ttu-id="4dd71-161">Strumento Calcolo stime (Analisi)</span><span class="sxs-lookup"><span data-stu-id="4dd71-161">Prediction Calculator (Analyze)</span></span>  
 <span data-ttu-id="4dd71-162">Questo strumento consente di creare un modello che analizza i fattori che portano ai risultati desiderati e quindi di eseguire la stima di un risultato per un nuovo input, in base ai criteri derivati da questi modelli. Consente inoltre di generare un foglio di lavoro interattivo decisionale che consente di ottenere facilmente nuovi input.</span><span class="sxs-lookup"><span data-stu-id="4dd71-162">This tool creates a model that analyzes the factors leading to target outcomes, and then predicts a result for any new input, based on criteria derived from these patterns It also generates an interactive decision making worksheet that lets you easily score new inputs.</span></span> <span data-ttu-id="4dd71-163">È inoltre possibile creare una versione stampata del foglio di lavoro per l'assegnazione dei punteggi da utilizzare offline.</span><span class="sxs-lookup"><span data-stu-id="4dd71-163">You can also create a printed version of the scoring worksheet for offline use.</span></span>  
  
 <span data-ttu-id="4dd71-164">Lo strumento **Calcolo stime** usa l'algoritmo di regressione logistica Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4dd71-164">The **Prediction Calculator** tool uses the Microsoft Logistic Regression algorithm.</span></span>  
  
 [<span data-ttu-id="4dd71-165">Calcolo stime &#40;strumenti di analisi tabelle per Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="4dd71-165">Prediction Calculator &#40;Table Analysis Tools for Excel&#41;</span></span>](prediction-calculator-table-analysis-tools-for-excel.md)  
  
## <a name="scenario-goal-seek-analyze"></a><span data-ttu-id="4dd71-166">Scenario: Ricerca obiettivo (Analisi)</span><span class="sxs-lookup"><span data-stu-id="4dd71-166">Scenario: Goal Seek (Analyze)</span></span>  
 <span data-ttu-id="4dd71-167">Nello strumento **Ricerca obiettivo** specificare un valore di destinazione e lo strumento identifica i fattori sottostanti che devono essere modificati per soddisfare tale destinazione.</span><span class="sxs-lookup"><span data-stu-id="4dd71-167">In the **Goal Seek** tool, you specify a target value, and the tool identifies the underlying factors that must change to meet that target.</span></span> <span data-ttu-id="4dd71-168">Se, ad esempio, si desidera aumentare la soddisfazione chiamate del 20%, è possibile chiedere al modello di eseguire una stima dei fattori da modificare per raggiungere tale obiettivo.</span><span class="sxs-lookup"><span data-stu-id="4dd71-168">For example, if you know that you must increase call satisfaction by 20%, you can ask the model to predict the factors that should change to produce that goal.</span></span>  
  
 <span data-ttu-id="4dd71-169">Lo strumento **Ricerca obiettivo** usa l'algoritmo di regressione logistica Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4dd71-169">The **Goal Seek** tool uses the Microsoft Logistic Regression algorithm.</span></span>  
  
 <span data-ttu-id="4dd71-170">dettagli</span><span class="sxs-lookup"><span data-stu-id="4dd71-170">details</span></span>  
  
 [<span data-ttu-id="4dd71-171">Scenario di ricerca obiettivo &#40;strumenti di analisi tabelle per Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="4dd71-171">Goal Seek Scenario &#40;Table Analysis Tools for Excel&#41;</span></span>](goal-seek-scenario-table-analysis-tools-for-excel.md)  
  
## <a name="scenario-what-if-scenario-analyze"></a><span data-ttu-id="4dd71-172">Scenario: Analisi di simulazione (Analisi)</span><span class="sxs-lookup"><span data-stu-id="4dd71-172">Scenario: What-If Scenario (Analyze)</span></span>  
 <span data-ttu-id="4dd71-173">Lo strumento **di analisi di** simulazione integra lo strumento **Ricerca obiettivo** .</span><span class="sxs-lookup"><span data-stu-id="4dd71-173">The **What-If Analysis** tool complements the **Goal Seek** tool.</span></span> <span data-ttu-id="4dd71-174">Immettere nello strumento il valore che si desidera modificare per consentire al modello di stimare se tale modifica sarà sufficiente per il raggiungimento del risultato desiderato.</span><span class="sxs-lookup"><span data-stu-id="4dd71-174">With this tool, you entered the value you want to change, and the model predicts whether that change will be sufficient to achieve the desired outcome.</span></span> <span data-ttu-id="4dd71-175">È possibile ad esempio chiedere al modello di determinare se l'aggiunta di un operatore telefonico aumenterebbe la soddisfazione dei clienti di un punto.</span><span class="sxs-lookup"><span data-stu-id="4dd71-175">For example, you might ask the model to infer whether adding one extra call operator would increase customer satisfaction by one point.</span></span>  
  
 <span data-ttu-id="4dd71-176">Lo strumento **di** simulazione usa l'algoritmo di regressione logistica Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4dd71-176">The **What-If** tool uses the Microsoft Logistic Regression algorithm.</span></span>  
  
 [<span data-ttu-id="4dd71-177">Scenario di simulazione &#40;strumenti di analisi tabelle per Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="4dd71-177">What-If Scenario &#40;Table Analysis Tools for Excel&#41;</span></span>](what-if-scenario-table-analysis-tools-for-excel.md)  
  
## <a name="shopping-basket-analysis-analyze"></a><span data-ttu-id="4dd71-178">Market basket analysis (Analisi)</span><span class="sxs-lookup"><span data-stu-id="4dd71-178">Shopping Basket Analysis (Analyze)</span></span>  
 <span data-ttu-id="4dd71-179">Lo strumento Market **Basket Analysis** consente di creare gruppi di prodotti che vengono spesso acquistati insieme, per identificare i modelli che possono essere utilizzati per le vendite incrociate o le vendite.</span><span class="sxs-lookup"><span data-stu-id="4dd71-179">The **Shopping Basket Analysis** tool creates groups of products that are frequently purchased together, to identify patterns that can be used in cross-selling or up-selling.</span></span> <span data-ttu-id="4dd71-180">Consente inoltre di generare report in base al prezzo e al costo di prodotti correlati per agevolare le decisioni.</span><span class="sxs-lookup"><span data-stu-id="4dd71-180">It also generates reports based on the price and cost of related product bundles, to aid in decision-making.</span></span>  
  
 <span data-ttu-id="4dd71-181">È inoltre possibile utilizzare questo strumento per gli eventi che spesso si verificano insieme, per fattori che portano a una diagnosi o per qualsiasi altro set di risultati e cause potenziali.</span><span class="sxs-lookup"><span data-stu-id="4dd71-181">You can also use this tool for events that frequently occur together, factors leading to a diagnosis, or any other set of potential causes and outcomes.</span></span>  
  
 <span data-ttu-id="4dd71-182">Lo strumento Market **Basket Analysis** utilizza l'algoritmo Microsoft Association Rules.</span><span class="sxs-lookup"><span data-stu-id="4dd71-182">The **Shopping Basket Analysis** tool uses the Microsoft Association algorithm.</span></span>  
  
 [<span data-ttu-id="4dd71-183">Shopping Basket Analysis &#40;Table AnalysisTools per Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="4dd71-183">Shopping Basket Analysis &#40;Table AnalysisTools for Excel&#41;</span></span>](shopping-basket-analysis-table-analysistools-for-excel.md)  
  
## <a name="see-also"></a><span data-ttu-id="4dd71-184">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4dd71-184">See Also</span></span>  
 <span data-ttu-id="4dd71-185">[Esplorazione e pulizia dei dati](exploring-and-cleaning-data.md) </span><span class="sxs-lookup"><span data-stu-id="4dd71-185">[Exploring and Cleaning Data](exploring-and-cleaning-data.md) </span></span>  
 <span data-ttu-id="4dd71-186">[Convalida di modelli e utilizzo di modelli per la stima &#40;componenti aggiuntivi Data mining per Excel&#41;](validating-models-and-using-models-for-prediction-data-mining-add-ins-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="4dd71-186">[Validating Models and Using Models for Prediction &#40;Data Mining Add-ins for Excel&#41;](validating-models-and-using-models-for-prediction-data-mining-add-ins-for-excel.md) </span></span>  
 [<span data-ttu-id="4dd71-187">Distribuzione e scalabilità di modelli di data mining &#40;componenti aggiuntivi Data mining per Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="4dd71-187">Deploying and Scaling Mining Models &#40;Data Mining Add-ins for Excel&#41;</span></span>](deploying-and-scaling-mining-models-data-mining-add-ins-for-excel.md)  
  
  
