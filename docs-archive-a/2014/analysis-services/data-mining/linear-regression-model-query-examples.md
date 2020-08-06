---
title: Esempi di query sul modello di regressione lineare | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- linear regression algorithms [Analysis Services]
- linear regression [Analysis Services]
- content queries [DMX]
ms.assetid: fd3cf312-57a1-44b6-b772-fce6fc1c26d7
author: minewiskan
ms.author: owend
ms.openlocfilehash: 02d4b7309d7b5ea3d6295089f0fb2e778b1c9b4b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637519"
---
# <a name="linear-regression-model-query-examples"></a><span data-ttu-id="1bf2e-102">Esempi di query sul modello di regressione lineare</span><span class="sxs-lookup"><span data-stu-id="1bf2e-102">Linear Regression Model Query Examples</span></span>
  <span data-ttu-id="1bf2e-103">Quando si crea una query su un modello di data mining, è possibile creare una query sul contenuto, che fornisce dettagli sui criteri individuati durante l'analisi, oppure una query di stima, che utilizza i criteri presenti nel modello di data mining per eseguire stime relative a nuovi dati.</span><span class="sxs-lookup"><span data-stu-id="1bf2e-103">When you create a query against a data mining model, you can create a content query, which provides details about the patterns discovered in analysis, or you can create a prediction query, which uses the patterns in the model to make predictions for new data.</span></span> <span data-ttu-id="1bf2e-104">Una query sul contenuto potrebbe ad esempio fornire dettagli aggiuntivi sulla formula di regressione, mentre una query di stima potrebbe indicare se un nuovo punto dati si adatta al modello.</span><span class="sxs-lookup"><span data-stu-id="1bf2e-104">For example, a content query might provide additional details about the regression formula, while a prediction query might tell you if a new data point fits the model.</span></span> <span data-ttu-id="1bf2e-105">Utilizzando una query è inoltre possibile recuperare metadati relativi al modello.</span><span class="sxs-lookup"><span data-stu-id="1bf2e-105">You can also retrieve metadata about the model by using a query.</span></span>  
  
 <span data-ttu-id="1bf2e-106">In questa sezione viene illustrato come creare query per i modelli basati sull'algoritmo Microsoft Linear Regression.</span><span class="sxs-lookup"><span data-stu-id="1bf2e-106">This section explains how to create queries for models that are based on the Microsoft Linear Regression algorithm.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1bf2e-107">Poiché la regressione lineare è basata su un case specifico dell'algoritmo Microsoft Decision Trees, sono presenti molte somiglianze e alcuni modelli di albero delle decisioni che utilizzano attributi stimabili continui possono contenere formule di regressione.</span><span class="sxs-lookup"><span data-stu-id="1bf2e-107">Because linear regression is based on a special case of the Microsoft Decision Trees algorithm, there are many similarities, and some decision tree models that use continuous predictable attributes can contain regression formulas.</span></span> <span data-ttu-id="1bf2e-108">Per altre informazioni, vedere [Guida di riferimento tecnico per l'algoritmo Microsoft Decision Trees](microsoft-decision-trees-algorithm-technical-reference.md).</span><span class="sxs-lookup"><span data-stu-id="1bf2e-108">For more information, see [Microsoft Decision Trees Algorithm Technical Reference](microsoft-decision-trees-algorithm-technical-reference.md).</span></span>  
  
 <span data-ttu-id="1bf2e-109">**Query sul contenuto**</span><span class="sxs-lookup"><span data-stu-id="1bf2e-109">**Content queries**</span></span>  
  
 [<span data-ttu-id="1bf2e-110">Utilizzo del set di righe dello schema di data mining per determinare i parametri utilizzati per un modello</span><span class="sxs-lookup"><span data-stu-id="1bf2e-110">Using the Data Mining Schema Rowset to determine parameters used for a model</span></span>](#bkmk_Query1)  
  
 [<span data-ttu-id="1bf2e-111">Utilizzo di DMX per restituire la formula di regressione per il modello</span><span class="sxs-lookup"><span data-stu-id="1bf2e-111">Using DMX to return the regression formula for the model</span></span>](#bkmk_Query2)  
  
 [<span data-ttu-id="1bf2e-112">Restituzione solo del coefficiente per il modello</span><span class="sxs-lookup"><span data-stu-id="1bf2e-112">Returning only the coefficient for the model</span></span>](#bkmk_Query3)  
  
 <span data-ttu-id="1bf2e-113">**Query di stima**</span><span class="sxs-lookup"><span data-stu-id="1bf2e-113">**Prediction queries**</span></span>  
  
 [<span data-ttu-id="1bf2e-114">Stima del reddito mediante una query singleton</span><span class="sxs-lookup"><span data-stu-id="1bf2e-114">Predicting income using a singleton query</span></span>](#bkmk_Query4)  
  
 [<span data-ttu-id="1bf2e-115">Utilizzo delle funzioni di stima con un modello di regressione</span><span class="sxs-lookup"><span data-stu-id="1bf2e-115">Using prediction functions with a regression model</span></span>](#bkmk_Query5)  
  
##  <a name="finding-information-about-the-linear-regression-model"></a><a name="bkmk_top"></a> <span data-ttu-id="1bf2e-116">Ricerca di informazioni sul modello di regressione lineare</span><span class="sxs-lookup"><span data-stu-id="1bf2e-116">Finding Information about the Linear Regression Model</span></span>  
 <span data-ttu-id="1bf2e-117">La struttura di un modello di regressione lineare è estremamente semplice: il modello di data mining rappresenta i dati come nodo singolo che definisce la formula di regressione.</span><span class="sxs-lookup"><span data-stu-id="1bf2e-117">The structure of a linear regression model is extremely simple: the mining model represents the data as a single node, which defines the regression formula.</span></span> <span data-ttu-id="1bf2e-118">Per altre informazioni, vedere [Contenuto dei modelli di data mining per i modelli di regressione logistica &#40;Analysis Services - Data mining&#41;](mining-model-content-for-logistic-regression-models.md).</span><span class="sxs-lookup"><span data-stu-id="1bf2e-118">For more information, see [Mining Model Content for Logistic Regression Models &#40;Analysis Services - Data Mining&#41;](mining-model-content-for-logistic-regression-models.md).</span></span>  
  
 [<span data-ttu-id="1bf2e-119">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="1bf2e-119">Return to Top</span></span>](#bkmk_top)  
  
###  <a name="sample-query-1-using-the-data-mining-schema-rowset-to-determine-parameters-used-for-a-model"></a><a name="bkmk_Query1"></a> <span data-ttu-id="1bf2e-120">Query di esempio 1: Utilizzo del set di righe dello schema di data mining per determinare i parametri utilizzati per un modello</span><span class="sxs-lookup"><span data-stu-id="1bf2e-120">Sample Query 1: Using the Data Mining Schema Rowset to Determine Parameters Used for a Model</span></span>  
 <span data-ttu-id="1bf2e-121">Eseguendo una query sul set di righe dello schema di data mining, è possibile trovare i metadati relativi al modello.</span><span class="sxs-lookup"><span data-stu-id="1bf2e-121">By querying the data mining schema rowset, you can find metadata about the model.</span></span> <span data-ttu-id="1bf2e-122">Tali dati potrebbero includere la data di creazione, la data dell'ultima elaborazione del modello, il nome della struttura di data mining sulla quale si basa il modello e il nome della colonna designata come attributo stimabile.</span><span class="sxs-lookup"><span data-stu-id="1bf2e-122">This might include when the model was created, when the model was last processed, the name of the mining structure that the model is based on, and the name of the column designated as the predictable attribute.</span></span> <span data-ttu-id="1bf2e-123">È inoltre possibile restituire i parametri utilizzati durante la creazione del modello.</span><span class="sxs-lookup"><span data-stu-id="1bf2e-123">You can also return the parameters that were used when the model was first created.</span></span>  
  
```  
SELECT MINING_PARAMETERS   
FROM $system.DMSCHEMA_MINING_MODELS  
WHERE MODEL_NAME = 'TM_PredictIncome'  
```  
  
 <span data-ttu-id="1bf2e-124">Risultati dell'esempio:</span><span class="sxs-lookup"><span data-stu-id="1bf2e-124">Sample results:</span></span>  
  
|<span data-ttu-id="1bf2e-125">MINING_PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1bf2e-125">MINING_PARAMETERS</span></span>|  
|------------------------|  
|<span data-ttu-id="1bf2e-126">COMPLEXITY_PENALTY=0.9,</span><span class="sxs-lookup"><span data-stu-id="1bf2e-126">COMPLEXITY_PENALTY=0.9,</span></span><br /><br /> <span data-ttu-id="1bf2e-127">MAXIMUM_INPUT_ATTRIBUTES=255,</span><span class="sxs-lookup"><span data-stu-id="1bf2e-127">MAXIMUM_INPUT_ATTRIBUTES=255,</span></span><br /><br /> <span data-ttu-id="1bf2e-128">MAXIMUM_OUTPUT_ATTRIBUTES=255,</span><span class="sxs-lookup"><span data-stu-id="1bf2e-128">MAXIMUM_OUTPUT_ATTRIBUTES=255,</span></span><br /><br /> <span data-ttu-id="1bf2e-129">MINIMUM_SUPPORT=10,</span><span class="sxs-lookup"><span data-stu-id="1bf2e-129">MINIMUM_SUPPORT=10,</span></span><br /><br /> <span data-ttu-id="1bf2e-130">SCORE_METHOD=4,</span><span class="sxs-lookup"><span data-stu-id="1bf2e-130">SCORE_METHOD=4,</span></span><br /><br /> <span data-ttu-id="1bf2e-131">SPLIT_METHOD=3,</span><span class="sxs-lookup"><span data-stu-id="1bf2e-131">SPLIT_METHOD=3,</span></span><br /><br /> <span data-ttu-id="1bf2e-132">FORCE_REGRESSOR=</span><span class="sxs-lookup"><span data-stu-id="1bf2e-132">FORCE_REGRESSOR=</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="1bf2e-133">L'impostazione del parametro, "`FORCE_REGRESSOR =` ", indica che il valore corrente per il parametro FORCE_REGRESSOR è Null.</span><span class="sxs-lookup"><span data-stu-id="1bf2e-133">The parameter setting, "`FORCE_REGRESSOR =` ", indicates that the current value for the FORCE_REGRESSOR parameter is null.</span></span>  
  
 [<span data-ttu-id="1bf2e-134">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="1bf2e-134">Return to Top</span></span>](#bkmk_top)  
  
###  <a name="sample-query-2-retrieving-the-regression-formula-for-the-model"></a><a name="bkmk_Query2"></a> <span data-ttu-id="1bf2e-135">Query di esempio 2: Recupero della formula di regressione per il modello</span><span class="sxs-lookup"><span data-stu-id="1bf2e-135">Sample Query 2: Retrieving the Regression Formula for the Model</span></span>  
 <span data-ttu-id="1bf2e-136">Nella query seguente viene restituito il contenuto del modello di data mining per un modello di regressione lineare compilato utilizzando la stessa origine dati Targeted Mailing utilizzata in [Basic Data Mining Tutorial](../../tutorials/basic-data-mining-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="1bf2e-136">The following query returns the mining model content for a linear regression model that was built by using the same Targeted Mailing data source that was used in the [Basic Data Mining Tutorial](../../tutorials/basic-data-mining-tutorial.md).</span></span> <span data-ttu-id="1bf2e-137">Questo modello esegue la stima del reddito del cliente in base all'età.</span><span class="sxs-lookup"><span data-stu-id="1bf2e-137">This model predicts customer income based on age.</span></span>  
  
 <span data-ttu-id="1bf2e-138">La query restituisce il contenuto del nodo che contiene la formula di regressione.</span><span class="sxs-lookup"><span data-stu-id="1bf2e-138">The query returns the contents of the node that contains the regression formula.</span></span> <span data-ttu-id="1bf2e-139">Ogni variabile e ogni coefficiente vengono archiviati in una riga separata della tabella NODE_DISTRIBUTION nidificata.</span><span class="sxs-lookup"><span data-stu-id="1bf2e-139">Each variable and coefficient is stored in a separate row of the nested NODE_DISTRIBUTION table.</span></span> <span data-ttu-id="1bf2e-140">Se si vuole visualizzare la formula di regressione completa, usare il [Visualizzatore Microsoft Decision Trees](browse-a-model-using-the-microsoft-tree-viewer.md), fare clic sul nodo **(Tutti)** e aprire **Legenda data mining**.</span><span class="sxs-lookup"><span data-stu-id="1bf2e-140">If you want to view the complete regression formula, use the [Microsoft Tree Viewer](browse-a-model-using-the-microsoft-tree-viewer.md), click the **(All)** node, and open the **Mining Legend**.</span></span>  
  
```  
SELECT FLATTENED NODE_DISTRIBUTION as t  
FROM LR_PredictIncome.CONTENT  
```  
  
> [!NOTE]  
>  <span data-ttu-id="1bf2e-141">Se si fa riferimento a colonne singole della tabella nidificata usando una query quale `SELECT <column name> from NODE_DISTRIBUTION`, alcune colonne, ad esempio **SUPPORT** o **PROBABILITY**, devono essere racchiuse tra parentesi per distinguerle dalle parole chiave riservate con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="1bf2e-141">If you reference individual columns of the nested table by using a query such as `SELECT <column name> from NODE_DISTRIBUTION`, some columns, such as **SUPPORT** or **PROBABILITY**, must be enclosed in brackets to distinguish them from reserved keywords of the same name.</span></span>  
  
 <span data-ttu-id="1bf2e-142">Risultati previsti:</span><span class="sxs-lookup"><span data-stu-id="1bf2e-142">Expected results:</span></span>  
  
|<span data-ttu-id="1bf2e-143">T.ATTRIBUTE_NAME</span><span class="sxs-lookup"><span data-stu-id="1bf2e-143">t.ATTRIBUTE_NAME</span></span>|<span data-ttu-id="1bf2e-144">t.ATTRIBUTE_VALUE</span><span class="sxs-lookup"><span data-stu-id="1bf2e-144">t.ATTRIBUTE_VALUE</span></span>|<span data-ttu-id="1bf2e-145">t.SUPPORT</span><span class="sxs-lookup"><span data-stu-id="1bf2e-145">t.SUPPORT</span></span>|<span data-ttu-id="1bf2e-146">t.PROBABILITY</span><span class="sxs-lookup"><span data-stu-id="1bf2e-146">t.PROBABILITY</span></span>|<span data-ttu-id="1bf2e-147">t.VARIANCE</span><span class="sxs-lookup"><span data-stu-id="1bf2e-147">t.VARIANCE</span></span>|<span data-ttu-id="1bf2e-148">t.VALUETYPE</span><span class="sxs-lookup"><span data-stu-id="1bf2e-148">t.VALUETYPE</span></span>|  
|-----------------------|------------------------|---------------|-------------------|----------------|-----------------|  
|<span data-ttu-id="1bf2e-149">Yearly Income</span><span class="sxs-lookup"><span data-stu-id="1bf2e-149">Yearly Income</span></span>|<span data-ttu-id="1bf2e-150">Missing</span><span class="sxs-lookup"><span data-stu-id="1bf2e-150">Missing</span></span>|<span data-ttu-id="1bf2e-151">0</span><span class="sxs-lookup"><span data-stu-id="1bf2e-151">0</span></span>|<span data-ttu-id="1bf2e-152">0,000457142857142857</span><span class="sxs-lookup"><span data-stu-id="1bf2e-152">0.000457142857142857</span></span>|<span data-ttu-id="1bf2e-153">0</span><span class="sxs-lookup"><span data-stu-id="1bf2e-153">0</span></span>|<span data-ttu-id="1bf2e-154">1</span><span class="sxs-lookup"><span data-stu-id="1bf2e-154">1</span></span>|  
|<span data-ttu-id="1bf2e-155">Yearly Income</span><span class="sxs-lookup"><span data-stu-id="1bf2e-155">Yearly Income</span></span>|<span data-ttu-id="1bf2e-156">57220,8876687257</span><span class="sxs-lookup"><span data-stu-id="1bf2e-156">57220.8876687257</span></span>|<span data-ttu-id="1bf2e-157">17484</span><span class="sxs-lookup"><span data-stu-id="1bf2e-157">17484</span></span>|<span data-ttu-id="1bf2e-158">0,999542857142857</span><span class="sxs-lookup"><span data-stu-id="1bf2e-158">0.999542857142857</span></span>|<span data-ttu-id="1bf2e-159">1041275619,52776</span><span class="sxs-lookup"><span data-stu-id="1bf2e-159">1041275619.52776</span></span>|<span data-ttu-id="1bf2e-160">3</span><span class="sxs-lookup"><span data-stu-id="1bf2e-160">3</span></span>|  
|<span data-ttu-id="1bf2e-161">Età</span><span class="sxs-lookup"><span data-stu-id="1bf2e-161">Age</span></span>|<span data-ttu-id="1bf2e-162">471.687717702463</span><span class="sxs-lookup"><span data-stu-id="1bf2e-162">471.687717702463</span></span>|<span data-ttu-id="1bf2e-163">0</span><span class="sxs-lookup"><span data-stu-id="1bf2e-163">0</span></span>|<span data-ttu-id="1bf2e-164">0</span><span class="sxs-lookup"><span data-stu-id="1bf2e-164">0</span></span>|<span data-ttu-id="1bf2e-165">126,969442359327</span><span class="sxs-lookup"><span data-stu-id="1bf2e-165">126.969442359327</span></span>|<span data-ttu-id="1bf2e-166">7</span><span class="sxs-lookup"><span data-stu-id="1bf2e-166">7</span></span>|  
|<span data-ttu-id="1bf2e-167">Età</span><span class="sxs-lookup"><span data-stu-id="1bf2e-167">Age</span></span>|<span data-ttu-id="1bf2e-168">234.680904692439</span><span class="sxs-lookup"><span data-stu-id="1bf2e-168">234.680904692439</span></span>|<span data-ttu-id="1bf2e-169">0</span><span class="sxs-lookup"><span data-stu-id="1bf2e-169">0</span></span>|<span data-ttu-id="1bf2e-170">0</span><span class="sxs-lookup"><span data-stu-id="1bf2e-170">0</span></span>|<span data-ttu-id="1bf2e-171">0</span><span class="sxs-lookup"><span data-stu-id="1bf2e-171">0</span></span>|<span data-ttu-id="1bf2e-172">8</span><span class="sxs-lookup"><span data-stu-id="1bf2e-172">8</span></span>|  
|<span data-ttu-id="1bf2e-173">Età</span><span class="sxs-lookup"><span data-stu-id="1bf2e-173">Age</span></span>|<span data-ttu-id="1bf2e-174">45,4269617936399</span><span class="sxs-lookup"><span data-stu-id="1bf2e-174">45.4269617936399</span></span>|<span data-ttu-id="1bf2e-175">0</span><span class="sxs-lookup"><span data-stu-id="1bf2e-175">0</span></span>|<span data-ttu-id="1bf2e-176">0</span><span class="sxs-lookup"><span data-stu-id="1bf2e-176">0</span></span>|<span data-ttu-id="1bf2e-177">126,969442359327</span><span class="sxs-lookup"><span data-stu-id="1bf2e-177">126.969442359327</span></span>|<span data-ttu-id="1bf2e-178">9</span><span class="sxs-lookup"><span data-stu-id="1bf2e-178">9</span></span>|  
||<span data-ttu-id="1bf2e-179">35793,5477381267</span><span class="sxs-lookup"><span data-stu-id="1bf2e-179">35793.5477381267</span></span>|<span data-ttu-id="1bf2e-180">0</span><span class="sxs-lookup"><span data-stu-id="1bf2e-180">0</span></span>|<span data-ttu-id="1bf2e-181">0</span><span class="sxs-lookup"><span data-stu-id="1bf2e-181">0</span></span>|<span data-ttu-id="1bf2e-182">1012968919,28372</span><span class="sxs-lookup"><span data-stu-id="1bf2e-182">1012968919.28372</span></span>|<span data-ttu-id="1bf2e-183">11</span><span class="sxs-lookup"><span data-stu-id="1bf2e-183">11</span></span>|  
  
 <span data-ttu-id="1bf2e-184">In **Legenda data mining**, invece, la formula di regressione appare come segue:</span><span class="sxs-lookup"><span data-stu-id="1bf2e-184">In comparison, in the **Mining Legend**, the regression formula appears as follows:</span></span>  
  
 <span data-ttu-id="1bf2e-185">Yearly Income = 57,220.919 + 471.688 \* (Age - 45.427)</span><span class="sxs-lookup"><span data-stu-id="1bf2e-185">Yearly Income = 57,220.919 + 471.688 \* (Age - 45.427)</span></span>  
  
 <span data-ttu-id="1bf2e-186">È possibile notare che alcuni numeri di **Legenda data mining**sono arrotondati. In **Legenda data mining** sono tuttavia contenuti sostanzialmente gli stessi valori della tabella NODE_DISTRIBUTION.</span><span class="sxs-lookup"><span data-stu-id="1bf2e-186">You can see that in the **Mining Legend**, some numbers are rounded; however, the NODE_DISTRIBUTION table and the **Mining Legend** essentially contain the same values.</span></span>  
  
 <span data-ttu-id="1bf2e-187">I valori della colonna VALUETYPE indicano il tipo di informazioni contenuto in ogni riga. Questa indicazione risulta utile se i risultati vengono elaborati a livello di programmazione.</span><span class="sxs-lookup"><span data-stu-id="1bf2e-187">The values in the VALUETYPE column tell you what kind of information is contained in each row, which is useful if you are processing the results programmatically.</span></span> <span data-ttu-id="1bf2e-188">Nella tabella seguente sono mostrati i tipi di valore che vengono restituiti per una formula di regressione lineare.</span><span class="sxs-lookup"><span data-stu-id="1bf2e-188">The following table shows the value types that are output for a linear regression formula.</span></span>  
  
|<span data-ttu-id="1bf2e-189">VALUETYPE</span><span class="sxs-lookup"><span data-stu-id="1bf2e-189">VALUETYPE</span></span>|  
|---------------|  
|<span data-ttu-id="1bf2e-190">1 (Mancante)</span><span class="sxs-lookup"><span data-stu-id="1bf2e-190">1 (Missing)</span></span>|  
|<span data-ttu-id="1bf2e-191">3 (Continuo)</span><span class="sxs-lookup"><span data-stu-id="1bf2e-191">3 (Continuous)</span></span>|  
|<span data-ttu-id="1bf2e-192">7 (Coefficiente)</span><span class="sxs-lookup"><span data-stu-id="1bf2e-192">7 (Coefficient)</span></span>|  
|<span data-ttu-id="1bf2e-193">8 (Miglioramento punteggio)</span><span class="sxs-lookup"><span data-stu-id="1bf2e-193">8 (Score Gain)</span></span>|  
|<span data-ttu-id="1bf2e-194">9 (Statistiche)</span><span class="sxs-lookup"><span data-stu-id="1bf2e-194">9 (Statistics)</span></span>|  
|<span data-ttu-id="1bf2e-195">7 (Coefficiente)</span><span class="sxs-lookup"><span data-stu-id="1bf2e-195">7 (Coefficient)</span></span>|  
|<span data-ttu-id="1bf2e-196">8 (Miglioramento punteggio)</span><span class="sxs-lookup"><span data-stu-id="1bf2e-196">8 (Score Gain)</span></span>|  
|<span data-ttu-id="1bf2e-197">9 (Statistiche)</span><span class="sxs-lookup"><span data-stu-id="1bf2e-197">9 (Statistics)</span></span>|  
|<span data-ttu-id="1bf2e-198">11 (Intercetta)</span><span class="sxs-lookup"><span data-stu-id="1bf2e-198">11 (Intercept)</span></span>|  
  
 <span data-ttu-id="1bf2e-199">Per altre informazioni sul significato di ciascun tipo di valore per i modelli di regressione, vedere [Contenuto dei modelli di data mining per i modelli di regressione lineare &#40;Analysis Services - Data mining&#41;](mining-model-content-for-linear-regression-models-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="1bf2e-199">For more information about the meaning of each value type for regression models, see [Mining Model Content for Linear Regression Models &#40;Analysis Services - Data Mining&#41;](mining-model-content-for-linear-regression-models-analysis-services-data-mining.md).</span></span>  
  
 [<span data-ttu-id="1bf2e-200">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="1bf2e-200">Return to Top</span></span>](#bkmk_top)  
  
###  <a name="sample-query-3-returning-only-the-coefficient-for-the-model"></a><a name="bkmk_Query3"></a> <span data-ttu-id="1bf2e-201">Query di esempio 3: Restituzione solo del coefficiente per il modello</span><span class="sxs-lookup"><span data-stu-id="1bf2e-201">Sample Query 3: Returning Only the Coefficient for the Model</span></span>  
 <span data-ttu-id="1bf2e-202">Utilizzando l'enumerazione VALUETYPE, è possibile restituire solo il coefficiente per l'equazione di regressione, come mostrato nella query seguente:</span><span class="sxs-lookup"><span data-stu-id="1bf2e-202">By using the VALUETYPE enumeration, you can return only the coefficient for the regression equation, as shown in the following query:</span></span>  
  
```  
SELECT FLATTENED MODEL_NAME,  
    (SELECT ATTRIBUTE_VALUE, VALUETYPE  
     FROM NODE_DISTRIBUTION  
     WHERE VALUETYPE = 11)   
AS t  
FROM LR_PredictIncome.CONTENT  
```  
  
 <span data-ttu-id="1bf2e-203">Questa query restituisce due righe, una dal contenuto del modello di data mining e la riga dalla tabella nidificata che contiene il coefficiente.</span><span class="sxs-lookup"><span data-stu-id="1bf2e-203">This query returns two rows, one from the mining model content, and the row from the nested table that contains the coefficient.</span></span> <span data-ttu-id="1bf2e-204">La colonna ATTRIBUTE_NAME non è inclusa, in quanto è sempre vuota per il coefficiente.</span><span class="sxs-lookup"><span data-stu-id="1bf2e-204">The ATTRIBUTE_NAME column is not included here because it is always blank for the coefficient.</span></span>  
  
|<span data-ttu-id="1bf2e-205">MODEL_NAME</span><span class="sxs-lookup"><span data-stu-id="1bf2e-205">MODEL_NAME</span></span>|<span data-ttu-id="1bf2e-206">t.ATTRIBUTE_VALUE</span><span class="sxs-lookup"><span data-stu-id="1bf2e-206">t.ATTRIBUTE_VALUE</span></span>|<span data-ttu-id="1bf2e-207">t.VALUETYPE</span><span class="sxs-lookup"><span data-stu-id="1bf2e-207">t.VALUETYPE</span></span>|  
|-----------------|------------------------|-----------------|  
|<span data-ttu-id="1bf2e-208">LR_PredictIncome</span><span class="sxs-lookup"><span data-stu-id="1bf2e-208">LR_PredictIncome</span></span>|||  
|<span data-ttu-id="1bf2e-209">LR_PredictIncome</span><span class="sxs-lookup"><span data-stu-id="1bf2e-209">LR_PredictIncome</span></span>|<span data-ttu-id="1bf2e-210">35793,5477381267</span><span class="sxs-lookup"><span data-stu-id="1bf2e-210">35793.5477381267</span></span>|<span data-ttu-id="1bf2e-211">11</span><span class="sxs-lookup"><span data-stu-id="1bf2e-211">11</span></span>|  
  
 [<span data-ttu-id="1bf2e-212">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="1bf2e-212">Return to Top</span></span>](#bkmk_top)  
  
## <a name="making-predictions-from-a-linear-regression-model"></a><span data-ttu-id="1bf2e-213">Esecuzione di stime da un modello di regressione lineare</span><span class="sxs-lookup"><span data-stu-id="1bf2e-213">Making Predictions from a Linear Regression Model</span></span>  
 <span data-ttu-id="1bf2e-214">È possibile compilare query di stima sui modelli di regressione lineare utilizzando la scheda Stima modello di data mining in Progettazione modelli di data mining.</span><span class="sxs-lookup"><span data-stu-id="1bf2e-214">You can build prediction queries on linear regression models by using the Mining Model Prediction tab in Data Mining Designer.</span></span> <span data-ttu-id="1bf2e-215">Il generatore della query di stima è disponibile sia in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , sia in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1bf2e-215">The prediction query builder is available in both [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1bf2e-216">È inoltre possibile creare query nei modelli di regressione usando i componenti aggiuntivi Data mining di [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] per Excel oppure i componenti aggiuntivi data mining di [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] per Excel.</span><span class="sxs-lookup"><span data-stu-id="1bf2e-216">You can also create queries on regression models by using the [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Data Mining Add-ins for Excel or the [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] Data Mining Add-ins for Excel.</span></span> <span data-ttu-id="1bf2e-217">Anche se i componenti aggiuntivi Data mining per Excel non creano modelli di regressione, è possibile esplorare ed eseguire una query su qualsiasi modello di data mining archiviato in un'istanza di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1bf2e-217">Even though the Data Mining Add-ins for Excel do not create regression models, you can browse and query any mining model that is stored on an instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="1bf2e-218">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="1bf2e-218">Return to Top</span></span>](#bkmk_top)  
  
###  <a name="sample-query-4-predicting-income-using-a-singleton-query"></a><a name="bkmk_Query4"></a> <span data-ttu-id="1bf2e-219">Esempio di query 4: Stima del reddito mediante una query singleton</span><span class="sxs-lookup"><span data-stu-id="1bf2e-219">Sample Query 4: Predicting Income using a Singleton Query</span></span>  
 <span data-ttu-id="1bf2e-220">Il modo più semplice per creare una query singleton su un modello di regressione consiste nell'usare la finestra di dialogo **Input query singleton** .</span><span class="sxs-lookup"><span data-stu-id="1bf2e-220">The easiest way to create a single query on a regression model is by using the **Singleton Query Input** dialog box.</span></span> <span data-ttu-id="1bf2e-221">È ad esempio possibile compilare la query DMX seguente selezionando il modello di regressione appropriato, scegliendo **query singleton**, quindi digitando `20` come valore per **Age**.</span><span class="sxs-lookup"><span data-stu-id="1bf2e-221">For example, you can build the following DMX query by selecting the appropriate regression model, choosing **Singleton Query**, and then typing `20` as the value for **Age**.</span></span>  
  
```  
SELECT [LR_PredictIncome].[Yearly Income]  
From   [LR_PredictIncome]  
NATURAL PREDICTION JOIN  
(SELECT 20 AS [Age]) AS t  
```  
  
 <span data-ttu-id="1bf2e-222">Risultati dell'esempio:</span><span class="sxs-lookup"><span data-stu-id="1bf2e-222">Sample results:</span></span>  
  
|<span data-ttu-id="1bf2e-223">Yearly Income</span><span class="sxs-lookup"><span data-stu-id="1bf2e-223">Yearly Income</span></span>|  
|-------------------|  
|<span data-ttu-id="1bf2e-224">45227,302092176</span><span class="sxs-lookup"><span data-stu-id="1bf2e-224">45227.302092176</span></span>|  
  
 [<span data-ttu-id="1bf2e-225">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="1bf2e-225">Return to Top</span></span>](#bkmk_top)  
  
###  <a name="sample-query-5-using-prediction-functions-with-a-regression-model"></a><a name="bkmk_Query5"></a> <span data-ttu-id="1bf2e-226">Esempio di query 5: Utilizzo delle funzioni di stima con un modello di regressione</span><span class="sxs-lookup"><span data-stu-id="1bf2e-226">Sample Query 5: Using Prediction Functions with a Regression Model</span></span>  
 <span data-ttu-id="1bf2e-227">È possibile utilizzare molte delle funzioni di stima standard con i modelli di regressione lineare.</span><span class="sxs-lookup"><span data-stu-id="1bf2e-227">You can use many of the standard prediction functions with linear regression models.</span></span> <span data-ttu-id="1bf2e-228">Nell'esempio seguente viene illustrato come aggiungere alcune statistiche descrittive ai risultati della query di stima.</span><span class="sxs-lookup"><span data-stu-id="1bf2e-228">The following example illustrates how to add some descriptive statistics to the prediction query results.</span></span> <span data-ttu-id="1bf2e-229">Da questi risultati è possibile notare che esiste una deviazione significativa dalla media per questo modello.</span><span class="sxs-lookup"><span data-stu-id="1bf2e-229">From these results, you can see that there is considerable deviation from the mean for this model.</span></span>  
  
```  
SELECT  
  ([LR_PredictIncome].[Yearly Income]) as [PredIncome],  
  (PredictStdev([LR_PredictIncome].[Yearly Income])) as [StDev1]  
From  
  [LR_PredictIncome]  
NATURAL PREDICTION JOIN  
(SELECT 20 AS [Age]) AS t  
```  
  
 <span data-ttu-id="1bf2e-230">Risultati dell'esempio:</span><span class="sxs-lookup"><span data-stu-id="1bf2e-230">Sample results:</span></span>  
  
|<span data-ttu-id="1bf2e-231">Yearly Income</span><span class="sxs-lookup"><span data-stu-id="1bf2e-231">Yearly Income</span></span>|<span data-ttu-id="1bf2e-232">StDev1</span><span class="sxs-lookup"><span data-stu-id="1bf2e-232">StDev1</span></span>|  
|-------------------|------------|  
|<span data-ttu-id="1bf2e-233">45227,302092176</span><span class="sxs-lookup"><span data-stu-id="1bf2e-233">45227.302092176</span></span>|<span data-ttu-id="1bf2e-234">31827,1726561396</span><span class="sxs-lookup"><span data-stu-id="1bf2e-234">31827.1726561396</span></span>|  
  
 [<span data-ttu-id="1bf2e-235">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="1bf2e-235">Return to Top</span></span>](#bkmk_top)  
  
## <a name="list-of-prediction-functions"></a><span data-ttu-id="1bf2e-236">Elenco delle funzioni di stima</span><span class="sxs-lookup"><span data-stu-id="1bf2e-236">List of Prediction Functions</span></span>  
 <span data-ttu-id="1bf2e-237">Tutti gli algoritmi [!INCLUDE[msCoName](../../includes/msconame-md.md)] supportano un set comune di funzioni.</span><span class="sxs-lookup"><span data-stu-id="1bf2e-237">All [!INCLUDE[msCoName](../../includes/msconame-md.md)] algorithms support a common set of functions.</span></span> <span data-ttu-id="1bf2e-238">L'algoritmo [!INCLUDE[msCoName](../../includes/msconame-md.md)] Linear Regression supporta tuttavia le funzioni aggiuntive elencate nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="1bf2e-238">However, the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Linear Regression algorithm supports the additional functions listed in the following table.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1bf2e-239">Funzione di stima</span><span class="sxs-lookup"><span data-stu-id="1bf2e-239">Prediction Function</span></span>|<span data-ttu-id="1bf2e-240">Uso</span><span class="sxs-lookup"><span data-stu-id="1bf2e-240">Usage</span></span>|  
|[<span data-ttu-id="1bf2e-241">IsDescendant &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="1bf2e-241">IsDescendant &#40;DMX&#41;</span></span>](/sql/dmx/isdescendant-dmx)|<span data-ttu-id="1bf2e-242">Viene determinato se un nodo è figlio di un altro nodo nel modello.</span><span class="sxs-lookup"><span data-stu-id="1bf2e-242">Determines whether one node is a child of another node in the model.</span></span>|  
|[<span data-ttu-id="1bf2e-243">IsInNode &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="1bf2e-243">IsInNode &#40;DMX&#41;</span></span>](/sql/dmx/isinnode-dmx)|<span data-ttu-id="1bf2e-244">Indica se il nodo specificato contiene o meno il case corrente.</span><span class="sxs-lookup"><span data-stu-id="1bf2e-244">Indicates whether the specified node contains the current case.</span></span>|  
|[<span data-ttu-id="1bf2e-245">PredictHistogram &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="1bf2e-245">PredictHistogram &#40;DMX&#41;</span></span>](/sql/dmx/predicthistogram-dmx)|<span data-ttu-id="1bf2e-246">Viene restituito un valore, o un set di valori, stimato per una colonna specificata.</span><span class="sxs-lookup"><span data-stu-id="1bf2e-246">Returns a predicted value, or set of values, for a specified column.</span></span>|  
|[<span data-ttu-id="1bf2e-247">PredictNodeId &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="1bf2e-247">PredictNodeId &#40;DMX&#41;</span></span>](/sql/dmx/predictnodeid-dmx)|<span data-ttu-id="1bf2e-248">Viene restituito l'oggetto Node_ID per ogni case.</span><span class="sxs-lookup"><span data-stu-id="1bf2e-248">Returns the Node_ID for each case.</span></span>|  
|[<span data-ttu-id="1bf2e-249">PredictStdev &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="1bf2e-249">PredictStdev &#40;DMX&#41;</span></span>](/sql/dmx/predictstdev-dmx)|<span data-ttu-id="1bf2e-250">Viene restituita la deviazione standard per il valore stimato.</span><span class="sxs-lookup"><span data-stu-id="1bf2e-250">Returns standard deviation for the predicted value.</span></span>|  
|[<span data-ttu-id="1bf2e-251">PredictSupport &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="1bf2e-251">PredictSupport &#40;DMX&#41;</span></span>](/sql/dmx/predictsupport-dmx)|<span data-ttu-id="1bf2e-252">Viene restituito il valore di supporto per uno stato specificato.</span><span class="sxs-lookup"><span data-stu-id="1bf2e-252">Returns the support value for a specified state.</span></span>|  
|[<span data-ttu-id="1bf2e-253">PredictVariance &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="1bf2e-253">PredictVariance &#40;DMX&#41;</span></span>](/sql/dmx/predictvariance-dmx)|<span data-ttu-id="1bf2e-254">Restituisce la varianza di una colonna specificata.</span><span class="sxs-lookup"><span data-stu-id="1bf2e-254">Returns the variance of a specified column.</span></span>|  
  
 <span data-ttu-id="1bf2e-255">Per un elenco delle funzioni comuni a tutti gli algoritmi [!INCLUDE[msCoName](../../includes/msconame-md.md)], vedere [Algoritmi di data mining &#40;Analysis Services - Data mining&#41;](data-mining-algorithms-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="1bf2e-255">For a list of the functions that are common to all [!INCLUDE[msCoName](../../includes/msconame-md.md)] algorithms, see [Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining-algorithms-analysis-services-data-mining.md).</span></span> <span data-ttu-id="1bf2e-256">Per altre informazioni su come usare queste funzioni, vedere [Guida di riferimento alle funzioni DMX &#40;Data Mining Extensions&#41;](/sql/dmx/data-mining-extensions-dmx-function-reference).</span><span class="sxs-lookup"><span data-stu-id="1bf2e-256">For more information about how to use these functions, see [Data Mining Extensions &#40;DMX&#41; Function Reference](/sql/dmx/data-mining-extensions-dmx-function-reference).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bf2e-257">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1bf2e-257">See Also</span></span>  
 <span data-ttu-id="1bf2e-258">[Algoritmo Microsoft Linear regressione](microsoft-linear-regression-algorithm.md) </span><span class="sxs-lookup"><span data-stu-id="1bf2e-258">[Microsoft Linear Regression Algorithm](microsoft-linear-regression-algorithm.md) </span></span>  
 <span data-ttu-id="1bf2e-259">[Query di data mining](data-mining-queries.md) </span><span class="sxs-lookup"><span data-stu-id="1bf2e-259">[Data Mining Queries](data-mining-queries.md) </span></span>  
 <span data-ttu-id="1bf2e-260">[Riferimento tecnico per l'algoritmo Microsoft Linear regressione](microsoft-linear-regression-algorithm-technical-reference.md) </span><span class="sxs-lookup"><span data-stu-id="1bf2e-260">[Microsoft Linear Regression Algorithm Technical Reference](microsoft-linear-regression-algorithm-technical-reference.md) </span></span>  
 [<span data-ttu-id="1bf2e-261">Contenuto dei modelli di data mining per i modelli di regressione lineare &#40;Analysis Services - Data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="1bf2e-261">Mining Model Content for Linear Regression Models &#40;Analysis Services - Data Mining&#41;</span></span>](mining-model-content-for-linear-regression-models-analysis-services-data-mining.md)  
  
  
