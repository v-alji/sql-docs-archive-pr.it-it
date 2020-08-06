---
title: Esempi di query sul modello di associazione | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- itemsets [Analysis Services]
- association algorithms [Analysis Services]
- rules [Data Mining]
- association rules
- content queries [DMX]
ms.assetid: 68b39f5c-c439-44ac-8046-6f2d36649059
author: minewiskan
ms.author: owend
ms.openlocfilehash: a19eb2302639c7f13d48a8778969bbeca4fee18d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636959"
---
# <a name="association-model-query-examples"></a><span data-ttu-id="b8d02-102">Esempi di query sul modello di associazione</span><span class="sxs-lookup"><span data-stu-id="b8d02-102">Association Model Query Examples</span></span>
  <span data-ttu-id="b8d02-103">Quando si crea una query su un modello di data mining, è possibile creare una query sul contenuto, tramite cui vengono forniti dettagli sulle regole e i set di elementi individuati durante l'analisi oppure una query di stima, in cui vengono utilizzate le associazioni individuate nei dati per eseguire stime.</span><span class="sxs-lookup"><span data-stu-id="b8d02-103">When you create a query against a data mining model, you can create either a content query, which provides details about the rules and itemsets discovered during analysis, or you can create a prediction query, which uses the associations discovered in the data to make predictions.</span></span> <span data-ttu-id="b8d02-104">Per un modello di associazione, le stime sono in genere basate su regole e possono essere utilizzate per fornire indicazioni, mentre le query sul contenuto solitamente esplorano la relazione tra set di elementi.</span><span class="sxs-lookup"><span data-stu-id="b8d02-104">For an association model, predictions typically are based on rules, and can be used to make recommendations, whereas queries on content typically explore the relationship among itemsets.</span></span> <span data-ttu-id="b8d02-105">È anche possibile recuperare metadati relativi al modello.</span><span class="sxs-lookup"><span data-stu-id="b8d02-105">You can also retrieve metadata about the model.</span></span>  
  
 <span data-ttu-id="b8d02-106">Questa sezione illustra come creare questi tipi di query per i modelli basati sull'algoritmo [!INCLUDE[msCoName](../../includes/msconame-md.md)] Association Rules.</span><span class="sxs-lookup"><span data-stu-id="b8d02-106">This section explains how to create these kinds of queries for models that are based on the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Association Rules algorithm.</span></span>  
  
 <span data-ttu-id="b8d02-107">**Query sul contenuto**</span><span class="sxs-lookup"><span data-stu-id="b8d02-107">**Content Queries**</span></span>  
  
 [<span data-ttu-id="b8d02-108">Recupero di dati dei metadati del modello tramite DMX</span><span class="sxs-lookup"><span data-stu-id="b8d02-108">Getting model metadata data by using DMX</span></span>](#bkmk_Query1)  
  
 [<span data-ttu-id="b8d02-109">Recupero di metadati dal set di righe dello schema</span><span class="sxs-lookup"><span data-stu-id="b8d02-109">Getting metadata from the schema rowset</span></span>](#bkmk_Query2)  
  
 [<span data-ttu-id="b8d02-110">Recupero dei parametri originali per il modello</span><span class="sxs-lookup"><span data-stu-id="b8d02-110">Retrieving the original parameters for the model</span></span>](#bkmk_Query3)  
  
 [<span data-ttu-id="b8d02-111">Recupero di un elenco di set di elementi e prodotti</span><span class="sxs-lookup"><span data-stu-id="b8d02-111">Retrieving a list of itemsets and products</span></span>](#bkmk_Query4)  
  
 [<span data-ttu-id="b8d02-112">Restituzione dei primi 10 set di elementi</span><span class="sxs-lookup"><span data-stu-id="b8d02-112">Returning the top 10 itemsets</span></span>](#bkmk_Query5)  
  
 <span data-ttu-id="b8d02-113">**Query di stima**</span><span class="sxs-lookup"><span data-stu-id="b8d02-113">**Prediction Queries**</span></span>  
  
 [<span data-ttu-id="b8d02-114">Stima degli elementi associati</span><span class="sxs-lookup"><span data-stu-id="b8d02-114">Predicting associated items</span></span>](#bkmk_Query6)  
  
 [<span data-ttu-id="b8d02-115">Determinazione della confidenza per i set di elementi correlati</span><span class="sxs-lookup"><span data-stu-id="b8d02-115">Determining confidence for related itemsets</span></span>](#bkmk_Query7)  
  
##  <a name="finding-information-about-the-model"></a><a name="bkmk_top2"></a> <span data-ttu-id="b8d02-116">Ricerca di informazioni sul modello</span><span class="sxs-lookup"><span data-stu-id="b8d02-116">Finding Information about the Model</span></span>  
 <span data-ttu-id="b8d02-117">In tutti i modelli di data mining viene esposto il contenuto appreso dall'algoritmo secondo uno schema standardizzato, definito set di righe dello schema del modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="b8d02-117">All mining models expose the content learned by the algorithm according to a standardized schema, which is named the mining model schema rowset.</span></span> <span data-ttu-id="b8d02-118">È possibile creare query sul set di righe dello schema del modello di data mining tramite istruzioni Data Mining Extensions (DMX) oppure utilizzando stored procedure [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b8d02-118">You can create queries against the mining model schema rowset either by using Data Mining Extensions (DMX) statements, or by using [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] stored procedures.</span></span> <span data-ttu-id="b8d02-119">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]è anche possibile eseguire query sui set di righe dello schema direttamente come tabelle di sistema, utilizzando una sintassi simile a SQL.</span><span class="sxs-lookup"><span data-stu-id="b8d02-119">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], you can also query the schema rowsets directly as system tables, by using a SQL-like syntax.</span></span>  
  
###  <a name="sample-query-1-getting-model-metadata-by-using-dmx"></a><a name="bkmk_Query1"></a><span data-ttu-id="b8d02-120">Esempio di query 1: recupero di metadati del modello tramite DMX</span><span class="sxs-lookup"><span data-stu-id="b8d02-120">Sample Query 1: Getting Model Metadata by Using DMX</span></span>  
 <span data-ttu-id="b8d02-121">Con la query seguente vengono restituiti i metadati relativi al modello di associazione `Association`, ad esempio il nome del modello, il database in cui è archiviato e il numero di nodi figlio del modello.</span><span class="sxs-lookup"><span data-stu-id="b8d02-121">The following query returns basic metadata about the association model, `Association`, such as the name of the model, the database where the model is stored, and the number of child nodes in the model.</span></span> <span data-ttu-id="b8d02-122">Questa query utilizza una query contenuto DMX per recuperare i metadati dal nodo padre del modello:</span><span class="sxs-lookup"><span data-stu-id="b8d02-122">This query uses a DMX content query to retrieve the metadata from the parent node of the model:</span></span>  
  
```  
SELECT MODEL_CATALOG, MODEL_NAME, NODE_CAPTION,   
NODE_SUPPORT, [CHILDREN_CARDINALITY], NODE_DESCRIPTION  
FROM Association.CONTENT  
WHERE NODE_TYPE = 1  
```  
  
> [!NOTE]  
>  <span data-ttu-id="b8d02-123">È necessario includere il nome della colonna CHILDREN_CARDINALITY tra parentesi quadre per distinguerlo dalla parola chiave riservata MDX con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="b8d02-123">You must enclose the name of the column, CHILDREN_CARDINALITY, in brackets to distinguish it from the MDX reserved keyword of the same name.</span></span>  
  
 <span data-ttu-id="b8d02-124">Risultati dell'esempio:</span><span class="sxs-lookup"><span data-stu-id="b8d02-124">Example results:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b8d02-125">MODEL_CATALOG</span><span class="sxs-lookup"><span data-stu-id="b8d02-125">MODEL_CATALOG</span></span>|<span data-ttu-id="b8d02-126">Association Test</span><span class="sxs-lookup"><span data-stu-id="b8d02-126">Association Test</span></span>|  
|<span data-ttu-id="b8d02-127">MODEL_NAME</span><span class="sxs-lookup"><span data-stu-id="b8d02-127">MODEL_NAME</span></span>|<span data-ttu-id="b8d02-128">Association Rules</span><span class="sxs-lookup"><span data-stu-id="b8d02-128">Association</span></span>|  
|<span data-ttu-id="b8d02-129">NODE_CAPTION</span><span class="sxs-lookup"><span data-stu-id="b8d02-129">NODE_CAPTION</span></span>|<span data-ttu-id="b8d02-130">Association Rules Model</span><span class="sxs-lookup"><span data-stu-id="b8d02-130">Association Rules Model</span></span>|  
|<span data-ttu-id="b8d02-131">NODE_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="b8d02-131">NODE_SUPPORT</span></span>|<span data-ttu-id="b8d02-132">14879</span><span class="sxs-lookup"><span data-stu-id="b8d02-132">14879</span></span>|  
|<span data-ttu-id="b8d02-133">CHILDREN_CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="b8d02-133">CHILDREN_CARDINALITY</span></span>|<span data-ttu-id="b8d02-134">942</span><span class="sxs-lookup"><span data-stu-id="b8d02-134">942</span></span>|  
|<span data-ttu-id="b8d02-135">NODE_DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b8d02-135">NODE_DESCRIPTION</span></span>|<span data-ttu-id="b8d02-136">Association Rules Model; ITEMSET_COUNT=679; RULE_COUNT=263; MIN_SUPPORT=14; MAX_SUPPORT=4334; MIN_ITEMSET_SIZE=0; MAX_ITEMSET_SIZE=3; MIN_PROBABILITY=0.400390625; MAX_PROBABILITY=1; MIN_LIFT=0.14309369632511; MAX_LIFT=1.95758227647523</span><span class="sxs-lookup"><span data-stu-id="b8d02-136">Association Rules Model; ITEMSET_COUNT=679; RULE_COUNT=263; MIN_SUPPORT=14; MAX_SUPPORT=4334; MIN_ITEMSET_SIZE=0; MAX_ITEMSET_SIZE=3; MIN_PROBABILITY=0.400390625; MAX_PROBABILITY=1; MIN_LIFT=0.14309369632511; MAX_LIFT=1.95758227647523</span></span>|  
  
 <span data-ttu-id="b8d02-137">Per una definizione del significato di queste colonne in un modello di associazione, vedere [Contenuto dei modelli di data mining per i modelli di associazione &#40;Analysis Services - Data mining&#41;](mining-model-content-for-association-models-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="b8d02-137">For a definition of what these columns mean in an association model, see [Mining Model Content for Association Models &#40;Analysis Services - Data Mining&#41;](mining-model-content-for-association-models-analysis-services-data-mining.md).</span></span>  
  
 [<span data-ttu-id="b8d02-138">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="b8d02-138">Return to Top</span></span>](#bkmk_top2)  
  
###  <a name="sample-query-2-getting-additional-metadata-from-the-schema-rowset"></a><a name="bkmk_Query2"></a> <span data-ttu-id="b8d02-139">Esempio di query 2: Recupero di metadati aggiuntivi dal set di righe dello schema</span><span class="sxs-lookup"><span data-stu-id="b8d02-139">Sample Query 2: Getting Additional Metadata from the Schema Rowset</span></span>  
 <span data-ttu-id="b8d02-140">Se si esegue una query sul set di righe dello schema di data mining, è possibile trovare le stesse informazioni restituite in una query contenuto DMX.</span><span class="sxs-lookup"><span data-stu-id="b8d02-140">By querying the data mining schema rowset, you can find the same information that is returned in a DMX content query.</span></span> <span data-ttu-id="b8d02-141">Tuttavia, il set di righe dello schema fornisce alcune colonne aggiuntive, ad esempio la data dell'ultima elaborazione del modello, la struttura di data mining e il nome della colonna utilizzata come attributo stimabile.</span><span class="sxs-lookup"><span data-stu-id="b8d02-141">However, the schema rowset provides some additional columns, such as the date the model was last processed, the mining structure, and the name of the column used as the predictable attribute.</span></span>  
  
```  
SELECT MODEL_CATALOG, MODEL_NAME, SERVICE_NAME, PREDICTION_ENTITY,   
MINING_STRUCTURE, LAST_PROCESSED  
FROM $system.DMSCHEMA_MINING_MODELS  
WHERE MODEL_NAME = 'Association'  
```  
  
 <span data-ttu-id="b8d02-142">Risultati dell'esempio:</span><span class="sxs-lookup"><span data-stu-id="b8d02-142">Example results:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b8d02-143">MODEL_CATALOG</span><span class="sxs-lookup"><span data-stu-id="b8d02-143">MODEL_CATALOG</span></span>|<span data-ttu-id="b8d02-144">Adventure Works DW Multidimensional 2012</span><span class="sxs-lookup"><span data-stu-id="b8d02-144">Adventure Works DW Multidimensional 2012</span></span>|  
|<span data-ttu-id="b8d02-145">MODEL_NAME</span><span class="sxs-lookup"><span data-stu-id="b8d02-145">MODEL_NAME</span></span>|<span data-ttu-id="b8d02-146">Association Rules</span><span class="sxs-lookup"><span data-stu-id="b8d02-146">Association</span></span>|  
|<span data-ttu-id="b8d02-147">SERVICE_NAME</span><span class="sxs-lookup"><span data-stu-id="b8d02-147">SERVICE_NAME</span></span>|<span data-ttu-id="b8d02-148">Association Rules Model</span><span class="sxs-lookup"><span data-stu-id="b8d02-148">Association Rules Model</span></span>|  
|<span data-ttu-id="b8d02-149">PREDICTION_ENTITY</span><span class="sxs-lookup"><span data-stu-id="b8d02-149">PREDICTION_ENTITY</span></span>|<span data-ttu-id="b8d02-150">v Assoc Seq Line Items</span><span class="sxs-lookup"><span data-stu-id="b8d02-150">v Assoc Seq Line Items</span></span>|  
|<span data-ttu-id="b8d02-151">MINING_STRUCTURE</span><span class="sxs-lookup"><span data-stu-id="b8d02-151">MINING_STRUCTURE</span></span>|<span data-ttu-id="b8d02-152">Association Rules</span><span class="sxs-lookup"><span data-stu-id="b8d02-152">Association</span></span>|  
|<span data-ttu-id="b8d02-153">LAST_PROCESSED</span><span class="sxs-lookup"><span data-stu-id="b8d02-153">LAST_PROCESSED</span></span>|<span data-ttu-id="b8d02-154">9/29/2007 10:21:24 PM</span><span class="sxs-lookup"><span data-stu-id="b8d02-154">9/29/2007 10:21:24 PM</span></span>|  
  
 [<span data-ttu-id="b8d02-155">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="b8d02-155">Return to Top</span></span>](#bkmk_top2)  
  
###  <a name="sample-query-3-retrieving-original-parameters-for-model"></a><a name="bkmk_Query3"></a> <span data-ttu-id="b8d02-156">Esempio di query 3: Recupero dei parametri originali per il modello</span><span class="sxs-lookup"><span data-stu-id="b8d02-156">Sample Query 3: Retrieving Original Parameters for Model</span></span>  
 <span data-ttu-id="b8d02-157">Con la query seguente viene restituita una singola colonna contenente i dettagli sulle impostazioni dei parametri utilizzate durante la creazione del modello.</span><span class="sxs-lookup"><span data-stu-id="b8d02-157">The following query returns a single column that contains details about the parameter settings that were used when the model was created.</span></span>  
  
```  
SELECT MINING_PARAMETERS   
from $system.DMSCHEMA_MINING_MODELS  
WHERE MODEL_NAME = 'Association'  
```  
  
 <span data-ttu-id="b8d02-158">Risultati dell'esempio:</span><span class="sxs-lookup"><span data-stu-id="b8d02-158">Example results:</span></span>  
  
 <span data-ttu-id="b8d02-159">MAXIMUM_ITEMSET_COUNT=200000,MAXIMUM_ITEMSET_SIZE=3,MAXIMUM_SUPPORT=1,MINIMUM_SUPPORT=9.40923449156529E-04,MINIMUM_IMPORTANCE=-999999999,MINIMUM_ITEMSET_SIZE=0,MINIMUM_PROBABILITY=0.4</span><span class="sxs-lookup"><span data-stu-id="b8d02-159">MAXIMUM_ITEMSET_COUNT=200000,MAXIMUM_ITEMSET_SIZE=3,MAXIMUM_SUPPORT=1,MINIMUM_SUPPORT=9.40923449156529E-04,MINIMUM_IMPORTANCE=-999999999,MINIMUM_ITEMSET_SIZE=0,MINIMUM_PROBABILITY=0.4</span></span>  
  
 [<span data-ttu-id="b8d02-160">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="b8d02-160">Return to Top</span></span>](#bkmk_top2)  
  
## <a name="finding-information-about-rules-and-itemsets"></a><span data-ttu-id="b8d02-161">Ricerca di informazioni su regole e set di elementi</span><span class="sxs-lookup"><span data-stu-id="b8d02-161">Finding Information about Rules and Itemsets</span></span>  
 <span data-ttu-id="b8d02-162">Un modello di associazione viene utilizzato in genere per individuare informazioni sui set di elementi frequenti e per estrarre dettagli su regole e set di elementi specifici.</span><span class="sxs-lookup"><span data-stu-id="b8d02-162">There are two common uses of an association model: to discover information about frequent itemsets, and to extract details about particular rules and itemsets.</span></span> <span data-ttu-id="b8d02-163">Ad esempio, è possibile che si desideri estrarre un elenco di regole classificate come particolarmente interessanti o creare un elenco dei set di elementi più comuni.</span><span class="sxs-lookup"><span data-stu-id="b8d02-163">For example, you might want to extract a list of rules that were scored as being especially interesting, or create a list of the most common itemsets.</span></span> <span data-ttu-id="b8d02-164">Tali informazioni vengono recuperate tramite una query sul contenuto DMX.</span><span class="sxs-lookup"><span data-stu-id="b8d02-164">You retrieve such information by using a DMX content query.</span></span> <span data-ttu-id="b8d02-165">È anche possibile esplorare queste informazioni usando il **Visualizzatore Microsoft Association Rules**.</span><span class="sxs-lookup"><span data-stu-id="b8d02-165">You can also browse this information by using the **Microsoft Association Viewer**.</span></span>  
  
###  <a name="sample-query-4-retrieving-list-of-itemsets-and-products"></a><a name="bkmk_Query4"></a> <span data-ttu-id="b8d02-166">Esempio di query 4: Recupero di un elenco di set di elementi e prodotti</span><span class="sxs-lookup"><span data-stu-id="b8d02-166">Sample Query 4: Retrieving List of Itemsets and Products</span></span>  
 <span data-ttu-id="b8d02-167">Con la query seguente vengono recuperati tutti i set di elementi, insieme a una tabella nidificata in cui sono elencati i prodotti inclusi in ognuno di essi.</span><span class="sxs-lookup"><span data-stu-id="b8d02-167">The following query retrieves all of the itemsets, together with a nested table that lists the products included in each itemset.</span></span> <span data-ttu-id="b8d02-168">La colonna NODE_NAME contiene l'ID univoco del set di elementi all'interno del modello, mentre NODE_CAPTION fornisce una descrizione di testo degli elementi.</span><span class="sxs-lookup"><span data-stu-id="b8d02-168">The NODE_NAME column contains the unique ID of the itemset within the model, whereas the NODE_CAPTION provides a text description of the items.</span></span> <span data-ttu-id="b8d02-169">In questo esempio la tabella nidificata è bidimensionale, in modo che il set di elementi che contiene due prodotti genera due righe nei risultati.</span><span class="sxs-lookup"><span data-stu-id="b8d02-169">In this example, the nested table is flattened, so that an itemset that contains two products generates two rows in the results.</span></span> <span data-ttu-id="b8d02-170">È possibile omettere la parola chiave FLATTENED se il client supporta dati gerarchici.</span><span class="sxs-lookup"><span data-stu-id="b8d02-170">You can omit the FLATTENED keyword if your client supports hierarchical data.</span></span>  
  
```  
SELECT FLATTENED NODE_NAME, NODE_CAPTION,  
NODE_PROBABILITY, NODE_SUPPORT,  
(SELECT ATTRIBUTE_NAME FROM NODE_DISTRIBUTION) as PurchasedProducts  
FROM Association.CONTENT  
WHERE NODE_TYPE = 7  
```  
  
 <span data-ttu-id="b8d02-171">Risultati dell'esempio:</span><span class="sxs-lookup"><span data-stu-id="b8d02-171">Example results:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b8d02-172">NODE_NAME</span><span class="sxs-lookup"><span data-stu-id="b8d02-172">NODE_NAME</span></span>|<span data-ttu-id="b8d02-173">37</span><span class="sxs-lookup"><span data-stu-id="b8d02-173">37</span></span>|  
|<span data-ttu-id="b8d02-174">NODE_CAPTION</span><span class="sxs-lookup"><span data-stu-id="b8d02-174">NODE_CAPTION</span></span>|<span data-ttu-id="b8d02-175">Sport-100 = Existing</span><span class="sxs-lookup"><span data-stu-id="b8d02-175">Sport-100 = Existing</span></span>|  
|<span data-ttu-id="b8d02-176">NODE_PROBABILITY</span><span class="sxs-lookup"><span data-stu-id="b8d02-176">NODE_PROBABILITY</span></span>|<span data-ttu-id="b8d02-177">0.291283016331743</span><span class="sxs-lookup"><span data-stu-id="b8d02-177">0.291283016331743</span></span>|  
|<span data-ttu-id="b8d02-178">NODE_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="b8d02-178">NODE_SUPPORT</span></span>|<span data-ttu-id="b8d02-179">4334</span><span class="sxs-lookup"><span data-stu-id="b8d02-179">4334</span></span>|  
|<span data-ttu-id="b8d02-180">PURCHASEDPRODUCTS.ATTRIBUTE_NAME</span><span class="sxs-lookup"><span data-stu-id="b8d02-180">PURCHASEDPRODUCTS.ATTRIBUTE_NAME</span></span>|<span data-ttu-id="b8d02-181">v Assoc Seq Line Items(Sport-100)</span><span class="sxs-lookup"><span data-stu-id="b8d02-181">v Assoc Seq Line Items(Sport-100)</span></span>|  
  
 [<span data-ttu-id="b8d02-182">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="b8d02-182">Return to Top</span></span>](#bkmk_top2)  
  
###  <a name="sample-query-5-returning-top-10-itemsets"></a><a name="bkmk_Query5"></a> <span data-ttu-id="b8d02-183">Esempio di query 5: Recupero dei primi 10 set di elementi</span><span class="sxs-lookup"><span data-stu-id="b8d02-183">Sample Query 5: Returning Top 10 Itemsets</span></span>  
 <span data-ttu-id="b8d02-184">In questo esempio viene illustrato come utilizzare alcune delle funzioni di raggruppamento e ordinamento disponibili per impostazione predefinita tramite DMX.</span><span class="sxs-lookup"><span data-stu-id="b8d02-184">This example demonstrates how to use some of the grouping and ordering functions that DMX provides by default.</span></span> <span data-ttu-id="b8d02-185">La query restituisce i primi 10 set di elementi ordinati per supporto per ogni nodo.</span><span class="sxs-lookup"><span data-stu-id="b8d02-185">The query returns the top 10 itemsets when ordered by the support for each node.</span></span> <span data-ttu-id="b8d02-186">Si noti che non è necessario raggruppare in modo esplicito i risultati, come avviene invece in Transact-SQL; tuttavia, è possibile utilizzare un'unica funzione di aggregazione in ogni query.</span><span class="sxs-lookup"><span data-stu-id="b8d02-186">Note that you do not need to explicitly group the results, as you would in Transact-SQL; however, you can use only one aggregate function in each query.</span></span>  
  
```  
SELECT TOP 10 (NODE_SUPPORT),NODE_NAME, NODE_CAPTION  
FROM Association.CONTENT  
WHERE NODE_TYPE = 7  
```  
  
 <span data-ttu-id="b8d02-187">Risultati dell'esempio:</span><span class="sxs-lookup"><span data-stu-id="b8d02-187">Example results:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b8d02-188">NODE_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="b8d02-188">NODE_SUPPORT</span></span>|<span data-ttu-id="b8d02-189">4334</span><span class="sxs-lookup"><span data-stu-id="b8d02-189">4334</span></span>|  
|<span data-ttu-id="b8d02-190">NODE_NAME</span><span class="sxs-lookup"><span data-stu-id="b8d02-190">NODE_NAME</span></span>|<span data-ttu-id="b8d02-191">37</span><span class="sxs-lookup"><span data-stu-id="b8d02-191">37</span></span>|  
|<span data-ttu-id="b8d02-192">NODE_CAPTION</span><span class="sxs-lookup"><span data-stu-id="b8d02-192">NODE_CAPTION</span></span>|<span data-ttu-id="b8d02-193">Sport-100 = Existing</span><span class="sxs-lookup"><span data-stu-id="b8d02-193">Sport-100 = Existing</span></span>|  
  
 [<span data-ttu-id="b8d02-194">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="b8d02-194">Return to Top</span></span>](#bkmk_top2)  
  
## <a name="making-predictions-using-the-model"></a><span data-ttu-id="b8d02-195">Esecuzione di stime tramite il modello</span><span class="sxs-lookup"><span data-stu-id="b8d02-195">Making Predictions using the Model</span></span>  
 <span data-ttu-id="b8d02-196">Un modello di regole di associazione viene spesso utilizzato per generare indicazioni basate sulle correlazioni individuate nei set di elementi.</span><span class="sxs-lookup"><span data-stu-id="b8d02-196">An association rules model is often used to generate recommendations, which are based on correlations discovered in the itemsets.</span></span> <span data-ttu-id="b8d02-197">Pertanto, quando si crea una query di stima basata su un modello di regole di associazione, si utilizzano in genere le regole nel modello per fare supposizioni basate sui nuovi dati.</span><span class="sxs-lookup"><span data-stu-id="b8d02-197">Therefore, when you create a prediction query based on an association rules model, you are typically using the rules in the model to make guesses based on new data.</span></span>  <span data-ttu-id="b8d02-198">[PredictAssociation &#40;DMX&#41;](/sql/dmx/predictassociation-dmx) è la funzione che restituisce indicazioni e dispone di diversi argomenti utilizzabili per personalizzare i risultati della query.</span><span class="sxs-lookup"><span data-stu-id="b8d02-198">[PredictAssociation &#40;DMX&#41;](/sql/dmx/predictassociation-dmx) is the function that returns recommendations, and has several arguments that you can use to customize the query results.</span></span>  
  
 <span data-ttu-id="b8d02-199">Le query su un modello di associazione possono anche risultare utili, ad esempio, per restituire la confidenza di varie regole e di vari set di elementi, in modo da confrontare l'efficacia di diverse strategie di cross-selling.</span><span class="sxs-lookup"><span data-stu-id="b8d02-199">Another example of where queries on an association model might be useful is to return the confidence for various rules and itemsets so that you can compare the effectiveness of different cross-sell strategies.</span></span> <span data-ttu-id="b8d02-200">Negli esempi seguenti viene illustrato come creare tali query.</span><span class="sxs-lookup"><span data-stu-id="b8d02-200">The following examples illustrate how to create such queries.</span></span>  
  
###  <a name="sample-query-6-predicting-associated-items"></a><a name="bkmk_Query6"></a> <span data-ttu-id="b8d02-201">Esempio di query 6: Stima degli elementi associati</span><span class="sxs-lookup"><span data-stu-id="b8d02-201">Sample Query 6: Predicting Associated Items</span></span>  
 <span data-ttu-id="b8d02-202">Questo esempio illustra il modello di associazione creato in [Esercitazione intermedia sul data mining &#40;Analysis Services - Data mining&#41;](../../tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="b8d02-202">This example uses the Association model created in the [Intermediate Data Mining Tutorial &#40;Analysis Services - Data Mining&#41;](../../tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md).</span></span> <span data-ttu-id="b8d02-203">Viene illustrato come creare una query di stima che indica quali prodotti consigliare a un cliente che ha acquistato un determinato prodotto.</span><span class="sxs-lookup"><span data-stu-id="b8d02-203">It demonstrates how to create a prediction query that tells you what products to recommend to a customer who has purchased a particular product.</span></span> <span data-ttu-id="b8d02-204">Questo tipo di query, in cui i valori vengono forniti al modello in un'istruzione `SELECT...UNION`, è denominata query singleton.</span><span class="sxs-lookup"><span data-stu-id="b8d02-204">This type of query, where you provide values to the model in a `SELECT...UNION` statement, is called a singleton query.</span></span> <span data-ttu-id="b8d02-205">Poiché la colonna del modello stimabile che corrisponde ai nuovi valori è una tabella nidificata, è necessario utilizzare una clausola `SELECT` per eseguire il mapping del nuovo valore alla colonna della tabella nidificata, `[Model]`, e un'altra clausola `SELECT` per eseguire il mapping della colonna della tabella nidificata alla colonna a livello di case, `[v Assoc Seq Line Items]`.</span><span class="sxs-lookup"><span data-stu-id="b8d02-205">Because the predictable model column that corresponds to the new values is a nested table, you must use one `SELECT` clause to map the new value to the nested table column, `[Model]`, and another `SELECT` clause to map the nested table column to the case-level column, `[v Assoc Seq Line Items]`.</span></span> <span data-ttu-id="b8d02-206">L'aggiunta della parola chiave INCLUDE-STATISTICS alla query consente di vedere la probabilità e il supporto per le indicazioni.</span><span class="sxs-lookup"><span data-stu-id="b8d02-206">Adding the keyword INCLUDE-STATISTICS to the query lets you see the probability and support for the recommendations.</span></span>  
  
```  
SELECT PredictAssociation([Association].[vAssocSeqLineItems],INCLUDE_STATISTICS, 3)  
FROM [Association]  
NATURAL PREDICTION JOIN   
(SELECT  
(SELECT 'Classic Vest' as [Model])  
AS [v Assoc Seq Line Items])  
AS t  
```  
  
 <span data-ttu-id="b8d02-207">Risultati dell'esempio:</span><span class="sxs-lookup"><span data-stu-id="b8d02-207">Example results:</span></span>  
  
|<span data-ttu-id="b8d02-208">Modello</span><span class="sxs-lookup"><span data-stu-id="b8d02-208">Model</span></span>|<span data-ttu-id="b8d02-209">$SUPPORT</span><span class="sxs-lookup"><span data-stu-id="b8d02-209">$SUPPORT</span></span>|<span data-ttu-id="b8d02-210">$PROBABILITY</span><span class="sxs-lookup"><span data-stu-id="b8d02-210">$PROBABILITY</span></span>|<span data-ttu-id="b8d02-211">$ADJUSTEDPROBABILITY</span><span class="sxs-lookup"><span data-stu-id="b8d02-211">$ADJUSTEDPROBABILITY</span></span>|  
|-----------|--------------|------------------|--------------------------|  
|<span data-ttu-id="b8d02-212">Sport-100</span><span class="sxs-lookup"><span data-stu-id="b8d02-212">Sport-100</span></span>|<span data-ttu-id="b8d02-213">4334</span><span class="sxs-lookup"><span data-stu-id="b8d02-213">4334</span></span>|<span data-ttu-id="b8d02-214">0.291283</span><span class="sxs-lookup"><span data-stu-id="b8d02-214">0.291283</span></span>|<span data-ttu-id="b8d02-215">0.252696</span><span class="sxs-lookup"><span data-stu-id="b8d02-215">0.252696</span></span>|  
|<span data-ttu-id="b8d02-216">Water Bottle</span><span class="sxs-lookup"><span data-stu-id="b8d02-216">Water Bottle</span></span>|<span data-ttu-id="b8d02-217">2866</span><span class="sxs-lookup"><span data-stu-id="b8d02-217">2866</span></span>|<span data-ttu-id="b8d02-218">0.19262</span><span class="sxs-lookup"><span data-stu-id="b8d02-218">0.19262</span></span>|<span data-ttu-id="b8d02-219">0.175205</span><span class="sxs-lookup"><span data-stu-id="b8d02-219">0.175205</span></span>|  
|<span data-ttu-id="b8d02-220">Patch kit</span><span class="sxs-lookup"><span data-stu-id="b8d02-220">Patch kit</span></span>|<span data-ttu-id="b8d02-221">2113</span><span class="sxs-lookup"><span data-stu-id="b8d02-221">2113</span></span>|<span data-ttu-id="b8d02-222">0.142012</span><span class="sxs-lookup"><span data-stu-id="b8d02-222">0.142012</span></span>|<span data-ttu-id="b8d02-223">0.132389</span><span class="sxs-lookup"><span data-stu-id="b8d02-223">0.132389</span></span>|  
  
 [<span data-ttu-id="b8d02-224">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="b8d02-224">Return to Top</span></span>](#bkmk_top2)  
  
###  <a name="sample-query-7-determining-confidence-for-related-itemsets"></a><a name="bkmk_Query7"></a> <span data-ttu-id="b8d02-225">Esempio di query 7: Determinazione della confidenza per i set di elementi correlati</span><span class="sxs-lookup"><span data-stu-id="b8d02-225">Sample Query 7: Determining Confidence for Related Itemsets</span></span>  
 <span data-ttu-id="b8d02-226">Mentre le regole sono utili per generare indicazioni, i set di elementi sono più interessanti per un'analisi più approfondita dei modelli nel set di dati.</span><span class="sxs-lookup"><span data-stu-id="b8d02-226">Whereas rules are useful for generating recommendations, itemsets are more interesting for deeper analysis of the patterns in the data set.</span></span> <span data-ttu-id="b8d02-227">Se ad esempio le indicazioni restituiti con la query dell'esempio precedente non sono soddisfacenti, è possibile esaminare altri set di elementi che contengono il Prodotto A per valutare in modo più efficace se il Prodotto A è un accessorio che i clienti tendono ad acquistare con tutti i tipi di prodotti o se è strettamente correlato all'acquisto di determinati prodotti.</span><span class="sxs-lookup"><span data-stu-id="b8d02-227">For example, if you were not satisfied with the recommendation that are returned by the previous sample query, you could examine other itemsets that contain Product A, to can get a better idea of whether Product A is an accessory that people tend to buy with all kinds of products, or whether A is strongly correlated with purchases of particular products.</span></span> <span data-ttu-id="b8d02-228">Il modo più semplice per esplorare queste relazioni consiste nel filtrare i set di elementi nel Visualizzatore [!INCLUDE[msCoName](../../includes/msconame-md.md)] Association. Tuttavia, è possibile recuperare le stesse informazioni con una query.</span><span class="sxs-lookup"><span data-stu-id="b8d02-228">The easiest way to explore these relationships is by filtering the itemsets in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Association Viewer; however, you can retrieve the same information with a query.</span></span>  
  
 <span data-ttu-id="b8d02-229">Con la query di esempio seguente vengono restituiti tutti i set di elementi che includono l'articolo Water Bottle, incluso il singolo articolo Water Bottle.</span><span class="sxs-lookup"><span data-stu-id="b8d02-229">The following sample query returns all itemsets that include the Water Bottle item, including the single item Water bottle.</span></span>  
  
```  
SELECT TOP 100 FROM   
(  
SELECT FLATTENED NODE_CAPTION, NODE_SUPPORT,   
(SELECT ATTRIBUTE_NAME from NODE_DISTRIBUTION  
WHERE ATTRIBUTE_NAME = 'v Assoc Seq Line Items(Water Bottle)') as D  
FROM Association.CONTENT  
WHERE NODE_TYPE = 7  
) AS Items  
WHERE [D.ATTRIBUTE_NAME] <> NULL  
ORDER BY NODE_SUPPORT DESC  
```  
  
 <span data-ttu-id="b8d02-230">Risultati dell'esempio:</span><span class="sxs-lookup"><span data-stu-id="b8d02-230">Example results:</span></span>  
  
|<span data-ttu-id="b8d02-231">NODE_CAPTION</span><span class="sxs-lookup"><span data-stu-id="b8d02-231">NODE_CAPTION</span></span>|<span data-ttu-id="b8d02-232">NODE_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="b8d02-232">NODE_SUPPORT</span></span>|<span data-ttu-id="b8d02-233">D.ATTRIBUTE_NAME</span><span class="sxs-lookup"><span data-stu-id="b8d02-233">D.ATTRIBUTE_NAME</span></span>|  
|-------------------|-------------------|-----------------------|  
|<span data-ttu-id="b8d02-234">Water Bottle = Existing</span><span class="sxs-lookup"><span data-stu-id="b8d02-234">Water Bottle = Existing</span></span>|<span data-ttu-id="b8d02-235">2866</span><span class="sxs-lookup"><span data-stu-id="b8d02-235">2866</span></span>|<span data-ttu-id="b8d02-236">v Assoc Seq Line Items(Water Bottle)</span><span class="sxs-lookup"><span data-stu-id="b8d02-236">v Assoc Seq Line Items(Water Bottle)</span></span>|  
|<span data-ttu-id="b8d02-237">Mountain Bottle Cage = Existing, Water Bottle = Existing</span><span class="sxs-lookup"><span data-stu-id="b8d02-237">Mountain Bottle Cage = Existing, Water Bottle = Existing</span></span>|<span data-ttu-id="b8d02-238">1136</span><span class="sxs-lookup"><span data-stu-id="b8d02-238">1136</span></span>|<span data-ttu-id="b8d02-239">v Assoc Seq Line Items(Water Bottle)</span><span class="sxs-lookup"><span data-stu-id="b8d02-239">v Assoc Seq Line Items(Water Bottle)</span></span>|  
|<span data-ttu-id="b8d02-240">Road Bottle Cage = Existing, Water Bottle = Existing</span><span class="sxs-lookup"><span data-stu-id="b8d02-240">Road Bottle Cage = Existing, Water Bottle = Existing</span></span>|<span data-ttu-id="b8d02-241">1068</span><span class="sxs-lookup"><span data-stu-id="b8d02-241">1068</span></span>|<span data-ttu-id="b8d02-242">v Assoc Seq Line Items(Water Bottle)</span><span class="sxs-lookup"><span data-stu-id="b8d02-242">v Assoc Seq Line Items(Water Bottle)</span></span>|  
|<span data-ttu-id="b8d02-243">Water Bottle = Existing, Sport-100 = Existing</span><span class="sxs-lookup"><span data-stu-id="b8d02-243">Water Bottle = Existing, Sport-100 = Existing</span></span>|<span data-ttu-id="b8d02-244">734</span><span class="sxs-lookup"><span data-stu-id="b8d02-244">734</span></span>|<span data-ttu-id="b8d02-245">v Assoc Seq Line Items(Water Bottle)</span><span class="sxs-lookup"><span data-stu-id="b8d02-245">v Assoc Seq Line Items(Water Bottle)</span></span>|  
  
 <span data-ttu-id="b8d02-246">Tramite questa query vengono restituite le righe della tabella nidificata che corrispondono ai criteri e tutte le righe della tabella esterna o del case.</span><span class="sxs-lookup"><span data-stu-id="b8d02-246">This query returns both the rows from the nested table that match the criteria, and all the rows from the outside or case table.</span></span> <span data-ttu-id="b8d02-247">Pertanto, è necessario aggiungere una condizione che consente di eliminare le righe della tabella del case contenenti valori Null per il nome dell'attributo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="b8d02-247">Therefore, you must add a condition that eliminates the case table rows that have a null value for the target attribute name.</span></span>  
  
 [<span data-ttu-id="b8d02-248">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="b8d02-248">Return to Top</span></span>](#bkmk_top2)  
  
## <a name="function-list"></a><span data-ttu-id="b8d02-249">Elenco di funzioni</span><span class="sxs-lookup"><span data-stu-id="b8d02-249">Function List</span></span>  
 <span data-ttu-id="b8d02-250">Tutti gli algoritmi [!INCLUDE[msCoName](../../includes/msconame-md.md)] supportano un set comune di funzioni.</span><span class="sxs-lookup"><span data-stu-id="b8d02-250">All [!INCLUDE[msCoName](../../includes/msconame-md.md)] algorithms support a common set of functions.</span></span> <span data-ttu-id="b8d02-251">L'algoritmo [!INCLUDE[msCoName](../../includes/msconame-md.md)] Association Rules supporta tuttavia le funzioni aggiuntive elencate nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="b8d02-251">However, the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Association algorithm supports the additional functions listed in the following table.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b8d02-252">Funzione di stima</span><span class="sxs-lookup"><span data-stu-id="b8d02-252">Prediction Function</span></span>|<span data-ttu-id="b8d02-253">Uso</span><span class="sxs-lookup"><span data-stu-id="b8d02-253">Usage</span></span>|  
|[<span data-ttu-id="b8d02-254">IsDescendant &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="b8d02-254">IsDescendant &#40;DMX&#41;</span></span>](/sql/dmx/isdescendant-dmx)|<span data-ttu-id="b8d02-255">Viene determinato se un nodo è figlio di un altro nodo nel grafico della rete neurale.</span><span class="sxs-lookup"><span data-stu-id="b8d02-255">Determines whether one node is a child of another node in the neural network graph.</span></span>|  
|[<span data-ttu-id="b8d02-256">IsInNode &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="b8d02-256">IsInNode &#40;DMX&#41;</span></span>](/sql/dmx/isinnode-dmx)|<span data-ttu-id="b8d02-257">Indica se il nodo specificato contiene o meno il case corrente.</span><span class="sxs-lookup"><span data-stu-id="b8d02-257">Indicates whether the specified node contains the current case.</span></span>|  
|[<span data-ttu-id="b8d02-258">PredictAdjustedProbability &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="b8d02-258">PredictAdjustedProbability &#40;DMX&#41;</span></span>](/sql/dmx/predictadjustedprobability-dmx)|<span data-ttu-id="b8d02-259">Viene restituita la probabilità ponderata.</span><span class="sxs-lookup"><span data-stu-id="b8d02-259">Returns the weighted probability.</span></span>|  
|[<span data-ttu-id="b8d02-260">PredictAssociation &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="b8d02-260">PredictAssociation &#40;DMX&#41;</span></span>](/sql/dmx/predictassociation-dmx)|<span data-ttu-id="b8d02-261">Viene stimata l'appartenenza a un set di dati associativo.</span><span class="sxs-lookup"><span data-stu-id="b8d02-261">Predicts membership in an associative dataset.</span></span>|  
|[<span data-ttu-id="b8d02-262">PredictHistogram &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="b8d02-262">PredictHistogram &#40;DMX&#41;</span></span>](/sql/dmx/predicthistogram-dmx)|<span data-ttu-id="b8d02-263">Viene restituita una tabella di valori correlati ai valori stimati correnti.</span><span class="sxs-lookup"><span data-stu-id="b8d02-263">Returns a table of values related to the current predicted value.</span></span>|  
|[<span data-ttu-id="b8d02-264">PredictNodeId &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="b8d02-264">PredictNodeId &#40;DMX&#41;</span></span>](/sql/dmx/predictnodeid-dmx)|<span data-ttu-id="b8d02-265">Viene restituito l'oggetto Node_ID per ogni case.</span><span class="sxs-lookup"><span data-stu-id="b8d02-265">Returns the Node_ID for each case.</span></span>|  
|[<span data-ttu-id="b8d02-266">PredictProbability &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="b8d02-266">PredictProbability &#40;DMX&#41;</span></span>](/sql/dmx/predictprobability-dmx)|<span data-ttu-id="b8d02-267">Viene restituita la probabilità per il valore stimato.</span><span class="sxs-lookup"><span data-stu-id="b8d02-267">Returns probability for the predicted value.</span></span>|  
|[<span data-ttu-id="b8d02-268">PredictSupport &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="b8d02-268">PredictSupport &#40;DMX&#41;</span></span>](/sql/dmx/predictsupport-dmx)|<span data-ttu-id="b8d02-269">Viene restituito il valore di supporto per uno stato specificato.</span><span class="sxs-lookup"><span data-stu-id="b8d02-269">Returns the support value for a specified state.</span></span>|  
|[<span data-ttu-id="b8d02-270">PredictVariance &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="b8d02-270">PredictVariance &#40;DMX&#41;</span></span>](/sql/dmx/predictvariance-dmx)|<span data-ttu-id="b8d02-271">Viene restituita la varianza per il valore stimato.</span><span class="sxs-lookup"><span data-stu-id="b8d02-271">Returns variance for the predicted value.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b8d02-272">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b8d02-272">See Also</span></span>  
 <span data-ttu-id="b8d02-273">[Algoritmo Microsoft Association](microsoft-association-algorithm.md) </span><span class="sxs-lookup"><span data-stu-id="b8d02-273">[Microsoft Association Algorithm](microsoft-association-algorithm.md) </span></span>  
 <span data-ttu-id="b8d02-274">[Riferimento tecnico per l'algoritmo Microsoft Association](microsoft-association-algorithm-technical-reference.md) </span><span class="sxs-lookup"><span data-stu-id="b8d02-274">[Microsoft Association Algorithm Technical Reference](microsoft-association-algorithm-technical-reference.md) </span></span>  
 [<span data-ttu-id="b8d02-275">Contenuto dei modelli di data mining per i modelli di associazione &#40;Analysis Services - Data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="b8d02-275">Mining Model Content for Association Models &#40;Analysis Services - Data Mining&#41;</span></span>](mining-model-content-for-association-models-analysis-services-data-mining.md)  
  
  
