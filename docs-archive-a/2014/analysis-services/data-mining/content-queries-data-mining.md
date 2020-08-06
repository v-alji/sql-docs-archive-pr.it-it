---
title: Query sul contenuto (data mining) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: c4f4a5a8-a230-4222-bece-9d563501f65f
author: minewiskan
ms.author: owend
ms.openlocfilehash: 44b162c34f5f505462a713205d8434484473afa4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638174"
---
# <a name="content-queries-data-mining"></a><span data-ttu-id="4c87c-102">Query sul contenuto (Data mining)</span><span class="sxs-lookup"><span data-stu-id="4c87c-102">Content Queries (Data Mining)</span></span>
  <span data-ttu-id="4c87c-103">Una query sul contenuto consente di estrarre informazioni sulle statistiche interne e sulla struttura del modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="4c87c-103">A content query is a way of extracting information about the internal statistics and structure of the mining model.</span></span> <span data-ttu-id="4c87c-104">Talvolta una query sul contenuto può fornire dettagli che non sono immediatamente disponibili nel visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="4c87c-104">Sometimes a content query can provide details that are not readily available in the viewer.</span></span> <span data-ttu-id="4c87c-105">I risultati di una query sul contenuto possono essere utilizzati anche per estrarre a livello di codice informazioni per altri utilizzi.</span><span class="sxs-lookup"><span data-stu-id="4c87c-105">You can also use the results of a content query to extract information programmatically for other uses.</span></span>  
  
 <span data-ttu-id="4c87c-106">In questa sezione vengono fornite informazioni generali sui tipi di informazioni che è possibile recuperare tramite una query sul contenuto, nonché la sintassi DMX generale per le query sul contenuto.</span><span class="sxs-lookup"><span data-stu-id="4c87c-106">This section provides general information about the types of information that you can retrieve by using a content query, and the general DMX syntax for content queries.</span></span>  
  
 [<span data-ttu-id="4c87c-107">Query sul contenuto di base</span><span class="sxs-lookup"><span data-stu-id="4c87c-107">Basic Content Queries</span></span>](#bkmk_ContentQuery)  
  
-   [<span data-ttu-id="4c87c-108">Query sulla struttura e sui dati del case</span><span class="sxs-lookup"><span data-stu-id="4c87c-108">Queries on Structure and Case Data</span></span>](#bkmk_Structure)  
  
-   [<span data-ttu-id="4c87c-109">Query sugli schemi del modello</span><span class="sxs-lookup"><span data-stu-id="4c87c-109">Queries on Model Patterns</span></span>](#bkmk_Patterns)  
  
 [<span data-ttu-id="4c87c-110">esempi</span><span class="sxs-lookup"><span data-stu-id="4c87c-110">Examples</span></span>](#bkmk_Examples)  
  
-   [<span data-ttu-id="4c87c-111">Query sul contenuto su un modello di associazione</span><span class="sxs-lookup"><span data-stu-id="4c87c-111">Content Query on an Association Model</span></span>](#bkmk_Assoc)  
  
-   [<span data-ttu-id="4c87c-112">Query sul contenuto su un modello Decision Trees</span><span class="sxs-lookup"><span data-stu-id="4c87c-112">Content Query on a Decision Trees Model</span></span>](#bkmk_DecTree)  
  
 [<span data-ttu-id="4c87c-113">Utilizzo dei risultati delle query</span><span class="sxs-lookup"><span data-stu-id="4c87c-113">Working with the Query Results</span></span>](#bkmk_Results)  
  
##  <a name="basic-content-queries"></a><a name="bkmk_ContentQuery"></a><span data-ttu-id="4c87c-114">Query sul contenuto di base</span><span class="sxs-lookup"><span data-stu-id="4c87c-114">Basic Content Queries</span></span>  
 <span data-ttu-id="4c87c-115">È possibile creare query sul contenuto tramite il generatore delle query di stima, utilizzare i modelli di query sul contenuto DMX disponibili in SQL Server Management Studio o scrivere query direttamente in DMX.</span><span class="sxs-lookup"><span data-stu-id="4c87c-115">You can create content queries by using the Prediction Query Builder, use the DMX content query templates that are provided in SQL Server Management Studio, or write queries directly in DMX.</span></span> <span data-ttu-id="4c87c-116">A differenza delle query di stima, non è necessario unire in join i dati esterni, pertanto le query sul contenuto sono facili da scrivere.</span><span class="sxs-lookup"><span data-stu-id="4c87c-116">Unlike prediction queries you do not need to join external data, so content queries are easy to write.</span></span>  
  
 <span data-ttu-id="4c87c-117">In questa sezione viene fornita una panoramica dei tipi di query sul contenuto che è possibile creare.</span><span class="sxs-lookup"><span data-stu-id="4c87c-117">This section provides an overview of the types of content queries you can create.</span></span>  
  
-   <span data-ttu-id="4c87c-118">Le query sulla struttura di data mining o sui dati del case consentono di visualizzare i dati dettagliati utilizzati per il training.</span><span class="sxs-lookup"><span data-stu-id="4c87c-118">Queries on the mining structure or case data let you view the detailed data that was used for training.</span></span>  
  
-   <span data-ttu-id="4c87c-119">Le query sul modello possono restituire modelli, elenchi di attributi, formule e così via.</span><span class="sxs-lookup"><span data-stu-id="4c87c-119">Queries on the model can return patterns, lists of attributes, formulas, and so forth.</span></span>  
  
###  <a name="queries-on-structure-and-case-data"></a><a name="bkmk_Structure"></a> <span data-ttu-id="4c87c-120">Query sulla struttura e sui dati del case</span><span class="sxs-lookup"><span data-stu-id="4c87c-120">Queries on Structure and Case Data</span></span>  
 <span data-ttu-id="4c87c-121">DMX supporta le query sui dati memorizzati nella cache utilizzati per compilare strutture e modelli di data mining.</span><span class="sxs-lookup"><span data-stu-id="4c87c-121">DMX supports queries on the cached data that is used to build mining structures and models.</span></span> <span data-ttu-id="4c87c-122">Per impostazione predefinita, questa cache viene creata quando si definisce la struttura di data mining e viene popolata quando si elabora la struttura o il modello.</span><span class="sxs-lookup"><span data-stu-id="4c87c-122">By default, this cache is created when you define the mining structure, and is populated when you process the structure or model.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="4c87c-123">Questa cache non può essere cancellata o eliminata se è necessario separare i dati in set di training e di testing.</span><span class="sxs-lookup"><span data-stu-id="4c87c-123">This cache cannot be cleared or deleted if you need to separate data into training and testing sets.</span></span> <span data-ttu-id="4c87c-124">Se la cache viene cancellata, non è possibile eseguire una query sui dati del case.</span><span class="sxs-lookup"><span data-stu-id="4c87c-124">If the cache is cleared, you cannot query the case data.</span></span>  
  
 <span data-ttu-id="4c87c-125">Negli esempi seguenti vengono mostrati i modelli comuni utilizzati per la creazione di query sui dati del case o query sui dati nella struttura di data mining:</span><span class="sxs-lookup"><span data-stu-id="4c87c-125">The following examples show the common patterns for creating queries on the case data, or queries on the data in the mining structure:</span></span>  
  
 <span data-ttu-id="4c87c-126">**Ottenere tutti i case per un modello**</span><span class="sxs-lookup"><span data-stu-id="4c87c-126">**Get all the cases for a model**</span></span>  
 `SELECT FROM <model>.CASES`  
  
 <span data-ttu-id="4c87c-127">Utilizzare questa istruzione per recuperare colonne specifiche dai dati del case utilizzati per compilare un modello.</span><span class="sxs-lookup"><span data-stu-id="4c87c-127">Use this statement to retrieve specified columns from the case data used to build a model.</span></span> <span data-ttu-id="4c87c-128">È necessario disporre delle autorizzazioni drill-through sul modello per eseguire questa query.</span><span class="sxs-lookup"><span data-stu-id="4c87c-128">You must have drillthrough permissions on the model to run this query.</span></span>  
  
 <span data-ttu-id="4c87c-129">**Visualizzare tutti i dati inclusi nella struttura**</span><span class="sxs-lookup"><span data-stu-id="4c87c-129">**View all the data that is included in the structure**</span></span>  
 `SELECT FROM <structure>.CASES`  
  
 <span data-ttu-id="4c87c-130">Utilizzare questa istruzione per visualizzare tutti i dati presenti nella struttura, incluse le colonne non comprese in un determinato modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="4c87c-130">Use this statement to view all the data that is included in the structure, including columns that are not included in a particular mining model.</span></span> <span data-ttu-id="4c87c-131">Per recuperare i dati dalla struttura di data mining, è necessario disporre delle autorizzazioni drill-through sul modello e sulla struttura.</span><span class="sxs-lookup"><span data-stu-id="4c87c-131">You must have drillthrough permissions on the model, as well as on the structure, to retrieve data from the mining structure.</span></span>  
  
 <span data-ttu-id="4c87c-132">**Ottenere l'intervallo di valori**</span><span class="sxs-lookup"><span data-stu-id="4c87c-132">**Get range of values**</span></span>  
 `SELECT DISTINCT RangeMin(<column>), RangeMax(<column>) FROM <model>`  
  
 <span data-ttu-id="4c87c-133">Utilizzare questa istruzione per individuare i valori minimo e massimo e la media di una colonna continua o dei bucket di una colonna DISCRETIZED.</span><span class="sxs-lookup"><span data-stu-id="4c87c-133">Use this statement to find the minimum value, maximum value, and mean of a continuous column, or of the buckets of a DISCRETIZED column.</span></span>  
  
 <span data-ttu-id="4c87c-134">**Ottenere valori distinct**</span><span class="sxs-lookup"><span data-stu-id="4c87c-134">**Get distinct values**</span></span>  
 `SELECT DISTINCT <column>FROM <model>`  
  
 <span data-ttu-id="4c87c-135">Utilizzare questa istruzione per recuperare tutti i valori di una colonna DISCRETE.</span><span class="sxs-lookup"><span data-stu-id="4c87c-135">Use this statement to retrieve all the values of a DISCRETE column.</span></span>  <span data-ttu-id="4c87c-136">Non utilizzare questa istruzione per le colonne DISCRETIZED, ma utilizzare le funzioni `RangeMin` e `RangeMax`.</span><span class="sxs-lookup"><span data-stu-id="4c87c-136">Do not use this statement for DISCRETIZED columns; use the `RangeMin` and `RangeMax` functions instead.</span></span>  
  
 <span data-ttu-id="4c87c-137">**Individuare i case utilizzati per il training di un modello o di una struttura**</span><span class="sxs-lookup"><span data-stu-id="4c87c-137">**Find the cases that were used to train a model or structure**</span></span>  
 `SELECT  FROM <mining structure.CASES WHERE IsTrainingCase()`  
  
 <span data-ttu-id="4c87c-138">Utilizzare questa istruzione per ottenere il set di dati completo utilizzato per il training di un modello.</span><span class="sxs-lookup"><span data-stu-id="4c87c-138">Use this statement to get the complete set of data that was used in a training a model.</span></span>  
  
 <span data-ttu-id="4c87c-139">**Individuare i case utilizzati per il testing di un modello o di una struttura**</span><span class="sxs-lookup"><span data-stu-id="4c87c-139">**Find the cases that are used for testing a model or structure**</span></span>  
 `SELECT  FROM <mining structure.CASES WHERE IsTestingCase()`  
  
 <span data-ttu-id="4c87c-140">Utilizzare questa istruzione per ottenere i dati riservati per il testing dei modelli di data mining correlati a una struttura specifica.</span><span class="sxs-lookup"><span data-stu-id="4c87c-140">Use this statement to get the data that has been set aside for testing mining models related to a specific structure.</span></span>  
  
 <span data-ttu-id="4c87c-141">**Eseguire il drill-through da uno schema del modello specifico ai dati del case sottostanti**</span><span class="sxs-lookup"><span data-stu-id="4c87c-141">**Drillthrough from a specific model pattern to underlying case data**</span></span>  
 `SELECT FROM <model>.CASESWHERE IsTrainingCase() AND IsInNode(<node>)`  
  
 <span data-ttu-id="4c87c-142">Utilizzare questa istruzione per recuperare dati del case dettagliati da un modello sottoposto a training.</span><span class="sxs-lookup"><span data-stu-id="4c87c-142">Use this statement to retrieve detailed case data from a trained model.</span></span> <span data-ttu-id="4c87c-143">È necessario specificare un determinato nodo, ad esempio è necessario conoscere l'ID del nodo del cluster, il ramo specifico di un albero delle decision, e così via. Inoltre, è necessario disporre delle autorizzazioni drill-through sul modello per eseguire questa query.</span><span class="sxs-lookup"><span data-stu-id="4c87c-143">You must specify a specific node: for example, you must know the node ID of the cluster, the specific branch of the decision tree, etc. Moreover, you must have drillthrough permissions on the model to run this query.</span></span>  
  
###  <a name="queries-on-model-patterns-statistics-and-attributes"></a><a name="bkmk_Patterns"></a><span data-ttu-id="4c87c-144">Query su modelli di modello, statistiche e attributi</span><span class="sxs-lookup"><span data-stu-id="4c87c-144">Queries on Model Patterns, Statistics, and Attributes</span></span>  
 <span data-ttu-id="4c87c-145">Il contenuto di un modello di data mining è utile per molti scopi.</span><span class="sxs-lookup"><span data-stu-id="4c87c-145">The content of a data mining model is useful for many purposes.</span></span> <span data-ttu-id="4c87c-146">Con una query sul contenuto del modello, è possibile:</span><span class="sxs-lookup"><span data-stu-id="4c87c-146">With a model content query, you can:</span></span>  
  
-   <span data-ttu-id="4c87c-147">Estrarre formule o probabilità per effettuare i calcoli.</span><span class="sxs-lookup"><span data-stu-id="4c87c-147">Extract formulas or probabilities for making your own calculations.</span></span>  
  
-   <span data-ttu-id="4c87c-148">Per un modello di associazione, recuperare le regole utilizzate per generare una stima.</span><span class="sxs-lookup"><span data-stu-id="4c87c-148">For an association model, retrieve the rules that are used to generate a prediction.</span></span>  
  
-   <span data-ttu-id="4c87c-149">Recuperare le descrizioni di regole specifiche in modo da poter utilizzare le regole in un'applicazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="4c87c-149">Retrieve the descriptions of specific rules so that you can use the rules in a custom application.</span></span>  
  
-   <span data-ttu-id="4c87c-150">Visualizzare le medie mobili rilevate da un modello Time Series.</span><span class="sxs-lookup"><span data-stu-id="4c87c-150">View the moving averages detected by a time series model.</span></span>  
  
-   <span data-ttu-id="4c87c-151">Ottenere la formula di regressione per alcuni segmenti della linea di tendenza.</span><span class="sxs-lookup"><span data-stu-id="4c87c-151">Obtain the regression formula for some segment of the trend line.</span></span>  
  
-   <span data-ttu-id="4c87c-152">Recuperare informazioni utilizzabili sui clienti identificati come facenti parte di un cluster specifico.</span><span class="sxs-lookup"><span data-stu-id="4c87c-152">Retrieve actionable information about customers identified as being part of a specific cluster.</span></span>  
  
 <span data-ttu-id="4c87c-153">Negli esempi seguenti vengono mostrati alcuni dei modelli comuni per la creazione di query sul contenuto del modello:</span><span class="sxs-lookup"><span data-stu-id="4c87c-153">The following examples show some of the common patterns for creating queries on the model content:</span></span>  
  
 <span data-ttu-id="4c87c-154">**Ottenere schemi dal modello**</span><span class="sxs-lookup"><span data-stu-id="4c87c-154">**Get patterns from the model**</span></span>  
 `SELECT FROM <model>.CONTENT`  
  
 <span data-ttu-id="4c87c-155">Utilizzare questa istruzione per recuperare informazioni dettagliate su nodi specifici del modello.</span><span class="sxs-lookup"><span data-stu-id="4c87c-155">Use this statement to retrieve detailed information about specific nodes in the model.</span></span> <span data-ttu-id="4c87c-156">A seconda del tipo di algoritmo, nel nodo possono essere contenute regole e formule, statistiche sul supporto e sulla varianza e così via.</span><span class="sxs-lookup"><span data-stu-id="4c87c-156">Depending on the algorithm type, the node can contain rules and formulas, support and variance statistics, and so forth.</span></span>  
  
 <span data-ttu-id="4c87c-157">**Recuperare attributi utilizzati in un modello sottoposto a training**</span><span class="sxs-lookup"><span data-stu-id="4c87c-157">**Retrieve attributes used in a trained model**</span></span>  
 `CALL System.GetModelAttributes(<model>)`  
  
 <span data-ttu-id="4c87c-158">Utilizzare questa stored procedure per recuperare l'elenco di attributi utilizzati da un modello.</span><span class="sxs-lookup"><span data-stu-id="4c87c-158">Use this stored procedure to retrieve the list of attributes that were used by a model.</span></span> <span data-ttu-id="4c87c-159">Queste informazioni sono utili per determinare gli attributi eliminati, ad esempio, in seguito alla selezione delle caratteristiche.</span><span class="sxs-lookup"><span data-stu-id="4c87c-159">This information is useful for determining attributes that were eliminated as a result of feature selection, for example.</span></span>  
  
 <span data-ttu-id="4c87c-160">**Recuperare il contenuto archiviato in una dimensione di data mining**</span><span class="sxs-lookup"><span data-stu-id="4c87c-160">**Retrieve content stored in a data mining dimension**</span></span>  
 `SELECT FROM <model>.DIMENSIONCONTENT`  
  
 <span data-ttu-id="4c87c-161">Utilizzare questa istruzione per recuperare i dati da una dimensione di data mining.</span><span class="sxs-lookup"><span data-stu-id="4c87c-161">Use this statement to retrieve the data from a data mining dimension.</span></span>  
  
 <span data-ttu-id="4c87c-162">Questo tipo di query è destinato principalmente a uso interno.</span><span class="sxs-lookup"><span data-stu-id="4c87c-162">This query type is principally for internal use.</span></span> <span data-ttu-id="4c87c-163">Tuttavia, non tutti gli algoritmi supportano questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="4c87c-163">However, not all algorithms support this functionality.</span></span> <span data-ttu-id="4c87c-164">Il supporto è indicato da un flag nel set di righe dello schema MINING_SERVICES.</span><span class="sxs-lookup"><span data-stu-id="4c87c-164">Support is indicated by a flag in the MINING_SERVICES schema rowset.</span></span>  
  
 <span data-ttu-id="4c87c-165">Se si sviluppa un proprio algoritmo plug-in, è possibile utilizzare questa istruzione per verificare il contenuto del modello per il testing.</span><span class="sxs-lookup"><span data-stu-id="4c87c-165">If you develop your own plug-in algorithm, you might use this statement to verify the content of your model for testing.</span></span>  
  
 <span data-ttu-id="4c87c-166">**Ottenere la rappresentazione PMML di un modello**</span><span class="sxs-lookup"><span data-stu-id="4c87c-166">**Get the PMML representation of a model**</span></span>  
 `SELECT * FROM <model>.PMML`  
  
 <span data-ttu-id="4c87c-167">Consente di ottenere un documento XML che rappresenta il modello in formato PMML.</span><span class="sxs-lookup"><span data-stu-id="4c87c-167">Gets an XML document that represents the model in PMML format.</span></span> <span data-ttu-id="4c87c-168">Non sono supportati tutti i tipi di modello.</span><span class="sxs-lookup"><span data-stu-id="4c87c-168">Not all model types are supported.</span></span>  
  
##  <a name="examples"></a><a name="bkmk_Examples"></a> <span data-ttu-id="4c87c-169">Esempi</span><span class="sxs-lookup"><span data-stu-id="4c87c-169">Examples</span></span>  
 <span data-ttu-id="4c87c-170">Sebbene alcuni contenuti dei modelli siano standard nei diversi algoritmi, alcune parti del contenuto variano significativamente a seconda dell'algoritmo utilizzato per compilare il modello.</span><span class="sxs-lookup"><span data-stu-id="4c87c-170">Although some model content is standard across algorithms, some parts of the content vary greatly depending on the algorithm that you used to build the model.</span></span> <span data-ttu-id="4c87c-171">Pertanto, quando si crea una query sul contenuto, è necessario identificare le informazione del modello che sono utili per il modello specifico in uso.</span><span class="sxs-lookup"><span data-stu-id="4c87c-171">Therefore, when you create a content query, you must understand what information in the model is most useful to your specific model.</span></span>  
  
 <span data-ttu-id="4c87c-172">Alcuni esempi vengono forniti in questa sezione per illustrare come la scelta di algoritmo influisca sul tipo di informazioni archiviato nel modello.</span><span class="sxs-lookup"><span data-stu-id="4c87c-172">A few examples are provided in this section to illustrate how the choice of algorithm affects the kind of information that is stored in the model.</span></span> <span data-ttu-id="4c87c-173">Per altre informazioni sul contenuto del modello di data mining e sul contenuto specifico per ogni tipo di modello, vedere [Contenuto del modello di data mining &#40;Analysis Services - Data Mining&#41;](mining-model-content-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="4c87c-173">For more information about mining model content, and the content that is specific to each model type, see [Mining Model Content &#40;Analysis Services - Data Mining&#41;](mining-model-content-analysis-services-data-mining.md).</span></span>  
  
###  <a name="example-1-content-query-on-an-association-model"></a><a name="bkmk_Assoc"></a> <span data-ttu-id="4c87c-174">Esempio 1: Query sul contenuto su un modello di associazione</span><span class="sxs-lookup"><span data-stu-id="4c87c-174">Example 1: Content Query on an Association Model</span></span>  
 <span data-ttu-id="4c87c-175">Tramite l'istruzione, `SELECT FROM <model>.CONTENT`, vengono restituiti tipi diversi di informazioni, a seconda del tipo di modello su cui si esegue una query.</span><span class="sxs-lookup"><span data-stu-id="4c87c-175">The statement, `SELECT FROM <model>.CONTENT`, returns different kinds of information, depending on the type of model you are querying.</span></span> <span data-ttu-id="4c87c-176">Per un modello di associazione, un'informazione chiave è il *tipo di nodo*.</span><span class="sxs-lookup"><span data-stu-id="4c87c-176">For an association model, a key piece of information is the *node type*.</span></span> <span data-ttu-id="4c87c-177">I nodi sono come contenitori per le informazioni nel contenuto del modello.</span><span class="sxs-lookup"><span data-stu-id="4c87c-177">Nodes are like containers for information in the model content.</span></span> <span data-ttu-id="4c87c-178">In un modello di associazione, i nodi che rappresentano regole hanno un valore NODE_TYPE pari a 8, mentre i nodi che rappresentano i set di elementi hanno un valore NODE_TYPE pari a 7.</span><span class="sxs-lookup"><span data-stu-id="4c87c-178">In an association model, nodes that represent rules have a NODE_TYPE value of 8, whereas nodes that represent itemsets have a NODE_TYPE value of 7.</span></span>  
  
 <span data-ttu-id="4c87c-179">Pertanto, tramite la query seguente vengono restituiti i primi 10 set di elementi, classificati per supporto (ordinamento predefinito).</span><span class="sxs-lookup"><span data-stu-id="4c87c-179">Thus, the following query returns the top 10 itemsets, ranked by support (the default ordering).</span></span>  
  
```  
SELECT TOP 10 NODE_DESCRIPTION, NODE_PROBABILITY, SUPPORT  
FROM <model>.CONTENT WHERE NODE_TYPE = 7  
```  
  
 <span data-ttu-id="4c87c-180">La query seguente consente di compilare su queste informazioni.</span><span class="sxs-lookup"><span data-stu-id="4c87c-180">The following query builds on this information.</span></span> <span data-ttu-id="4c87c-181">La query restituisce tre colonne: l'ID del nodo, la regola completa e il prodotto sul lato destro del set di elementi, ovvero il prodotto stimato per essere associato ad altri prodotti come parte di un set di elementi.</span><span class="sxs-lookup"><span data-stu-id="4c87c-181">The query returns three columns: the ID of the node, the complete rule, and the product on the right-hand side of the itemset-that is, the product that is predicted to be associated with some other products as part of an itemset.</span></span>  
  
```  
SELECT FLATTENED NODE_UNIQUE_NAME, NODE_DESCRIPTION,  
     (SELECT RIGHT(ATTRIBUTE_NAME, (LEN(ATTRIBUTE_NAME)-LEN('Association model name')))   
FROM NODE_DISTRIBUTION  
WHERE LEN(ATTRIBUTE_NAME)>2  
)   
AS RightSideProduct  
FROM [<Association model name>].CONTENT  
WHERE NODE_TYPE = 8   
ORDER BY NODE_SUPPORT DESC  
```  
  
 <span data-ttu-id="4c87c-182">La parola chiave FLATTENED indica che il set di righe nidificato deve essere convertito in una tabella bidimensionale.</span><span class="sxs-lookup"><span data-stu-id="4c87c-182">The FLATTENED keyword indicates that the nested rowset should be converted into a flattened table.</span></span> <span data-ttu-id="4c87c-183">L'attributo che rappresenta il prodotto sul lato destro della regola è contenuto nella tabella NODE_DISTRIBUTION; pertanto, si recupera solo la riga che contiene un nome di attributo aggiungendo un requisito in base al quale la lunghezza deve essere maggiore di 2.</span><span class="sxs-lookup"><span data-stu-id="4c87c-183">The attribute that represents the product on the right-hand side of the rule is contained in the NODE_DISTRIBUTION table; therefore, we retrieve only the row that contains an attribute name, by adding a requirement that the length be greater than 2.</span></span>  
  
 <span data-ttu-id="4c87c-184">Per rimuovere il nome del modello dalla terza colonna viene utilizzata una semplice funzione stringa.</span><span class="sxs-lookup"><span data-stu-id="4c87c-184">A simple string function is used to remove the name of the model from the third column.</span></span> <span data-ttu-id="4c87c-185">Generalmente il nome del modello viene aggiunto come prefisso ai valori delle colonne nidificate.</span><span class="sxs-lookup"><span data-stu-id="4c87c-185">(Usually the model name is prefixed to the values of nested columns.)</span></span>  
  
 <span data-ttu-id="4c87c-186">La clausola WHERE consente di specificare che il valore di NODE_TYPE deve essere 8, per recuperare solo le regole.</span><span class="sxs-lookup"><span data-stu-id="4c87c-186">The WHERE clause specifies that the value of NODE_TYPE should be 8, to retrieve only rules.</span></span>  
  
 <span data-ttu-id="4c87c-187">Per altri esempi, vedere [Esempi di query sul modello di associazione](association-model-query-examples.md).</span><span class="sxs-lookup"><span data-stu-id="4c87c-187">For more examples, see [Association Model Query Examples](association-model-query-examples.md).</span></span>  
  
###  <a name="example-2-content-query-on-a-decision-trees-model"></a><a name="bkmk_DecTree"></a> <span data-ttu-id="4c87c-188">Esempio 2: Query sul contenuto su un modello di alberi delle decisioni</span><span class="sxs-lookup"><span data-stu-id="4c87c-188">Example 2: Content Query on a Decision Trees Model</span></span>  
 <span data-ttu-id="4c87c-189">Un modello di albero delle decisioni può essere utilizzato per la stima, nonché per la classificazione.</span><span class="sxs-lookup"><span data-stu-id="4c87c-189">A decision tree model can be used for prediction as well as for classification.</span></span>  <span data-ttu-id="4c87c-190">In questo esempio si presuppone l'utilizzo del modello per la stima di un risultato, ma si desidera scoprire anche quali fattori o regole possono essere utilizzate per classificare il risultato.</span><span class="sxs-lookup"><span data-stu-id="4c87c-190">This example assumes that you are using the model to predict an outcome, but you also want to find out which factors or rules can be used to classify the outcome.</span></span>  
  
 <span data-ttu-id="4c87c-191">In un modello di albero delle decisioni, i nodi sono utilizzati per rappresentare sia alberi sia nodi foglia.</span><span class="sxs-lookup"><span data-stu-id="4c87c-191">In a decision tree model, nodes are used to represent both trees and leaf nodes.</span></span> <span data-ttu-id="4c87c-192">Nella didascalia per ogni nodo è contenuta la descrizione del percorso fino al risultato.</span><span class="sxs-lookup"><span data-stu-id="4c87c-192">The caption for each node contains the description of the path to the outcome.</span></span> <span data-ttu-id="4c87c-193">Pertanto, per tracciare il percorso per qualsiasi particolare risultato, è necessario identificare il nodo in cui è contenuto e ottenere i dettagli per tale nodo.</span><span class="sxs-lookup"><span data-stu-id="4c87c-193">Therefore, to trace the path for any particular outcome, you need to identify the node that contains it, and get the details for that node.</span></span>  
  
 <span data-ttu-id="4c87c-194">Nella query di stima si aggiunge la funzione di stima [PredictNodeId &#40;DMX&#41;](/sql/dmx/predictnodeid-dmx) per ottenere l'ID del nodo correlato, come mostrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="4c87c-194">In your prediction query, you add the prediction function [PredictNodeId &#40;DMX&#41;](/sql/dmx/predictnodeid-dmx), to get the ID of the related node, as shown in the following example:</span></span>  
  
```  
SELECT  Predict([Bike Buyer]), PredictNodeID([Bike Buyer])   
FROM [<decision tree model name>]  
PREDICTION JOIN   
<input rowset>   
```  
  
 <span data-ttu-id="4c87c-195">Una volta ottenuto l'ID del nodo contenente il risultato, è possibile recuperare la regola o il percorso tramite cui viene spiegata la stima creando una query sul contenuto in cui sia incluso NODE_CAPTION, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="4c87c-195">Once you have the ID of the node that contains the outcome, you can retrieve the rule or path that explains the prediction by creating a content query that includes the NODE_CAPTION, as follows:</span></span>  
  
```  
SELECT NODE_CAPTION  
FROM [<decision tree model name>]   
WHERE NODE_UNIQUE_NAME= '<node id>'  
```  
  
 <span data-ttu-id="4c87c-196">Per altri esempi, vedere [Esempi di query sul modello di alberi delle decisioni](decision-trees-model-query-examples.md).</span><span class="sxs-lookup"><span data-stu-id="4c87c-196">For more examples, see [Decision Trees Model Query Examples](decision-trees-model-query-examples.md).</span></span>  
  
##  <a name="working-with-the-query-results"></a><a name="bkmk_Results"></a><span data-ttu-id="4c87c-197">Utilizzo dei risultati della query</span><span class="sxs-lookup"><span data-stu-id="4c87c-197">Working with the Query Results</span></span>  
 <span data-ttu-id="4c87c-198">Come dimostrato negli esempi, tramite le query sul contenuto vengono restituiti soprattutto set di righe tabulari, tuttavia possono essere incluse anche informazioni sulle colonne nidificate.</span><span class="sxs-lookup"><span data-stu-id="4c87c-198">As the examples demonstrate, content queries mostly return tabular rowsets, but can also include information from nested columns.</span></span> <span data-ttu-id="4c87c-199">È possibile rendere bidimensionale il set di righe restituito, tuttavia, in questo modo, l'utilizzo dei risultati può risultare più complesso.</span><span class="sxs-lookup"><span data-stu-id="4c87c-199">You can flatten the rowset that is returned, but this can make working with results more complex.</span></span> <span data-ttu-id="4c87c-200">Il contenuto del nodo NODE_DISTRIBUTION in particolare è nidificato, ma in esso sono contenute informazioni molto interessanti sul modello.</span><span class="sxs-lookup"><span data-stu-id="4c87c-200">The content of the NODE_DISTRIBUTION node in particular is nested, but contains much interesting information about the model.</span></span>  
  
 <span data-ttu-id="4c87c-201">Per ulteriori informazioni sull'utilizzo di set di righe gerarchici, vedere la specifica OLE DB su MSDN.</span><span class="sxs-lookup"><span data-stu-id="4c87c-201">For more information about how to work with hierarchical rowsets, see the OLEDB specification on MSDN.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c87c-202">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4c87c-202">See Also</span></span>  
 <span data-ttu-id="4c87c-203">[Informazioni sull'istruzione DMX SELECT](/sql/dmx/understanding-the-dmx-select-statement) </span><span class="sxs-lookup"><span data-stu-id="4c87c-203">[Understanding the DMX Select Statement](/sql/dmx/understanding-the-dmx-select-statement) </span></span>  
 [<span data-ttu-id="4c87c-204">Query di data mining</span><span class="sxs-lookup"><span data-stu-id="4c87c-204">Data Mining Queries</span></span>](data-mining-queries.md)  
  
  
