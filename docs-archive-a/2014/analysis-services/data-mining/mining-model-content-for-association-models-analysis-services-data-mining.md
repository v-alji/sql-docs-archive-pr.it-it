---
title: Contenuto dei modelli di data mining per i modelli di associazione (Analysis Services-Data mining) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- itemsets [Analysis Services]
- association algorithms [Analysis Services]
- mining model content, association models
- rules [Data Mining]
- associations [Analysis Services]
ms.assetid: d5849bcb-4b8f-4f71-9761-7dc5bb465224
author: minewiskan
ms.author: owend
ms.openlocfilehash: 8904ce155526aee595db19094fd2bad48770e83e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627540"
---
# <a name="mining-model-content-for-association-models-analysis-services---data-mining"></a><span data-ttu-id="08f00-102">Contenuto dei modelli di data mining per i modelli di associazione (Analysis Services - Data mining)</span><span class="sxs-lookup"><span data-stu-id="08f00-102">Mining Model Content for Association Models (Analysis Services - Data Mining)</span></span>
  <span data-ttu-id="08f00-103">Questo argomento descrive il contenuto dei modelli di data mining specifico dei modelli che usano l'algoritmo [!INCLUDE[msCoName](../../includes/msconame-md.md)] Association Rules.</span><span class="sxs-lookup"><span data-stu-id="08f00-103">This topic describes mining model content that is specific to models that use the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Association Rules algorithm.</span></span> <span data-ttu-id="08f00-104">Per una spiegazione della terminologia generale e statistica relativa al contenuto dei modelli di data mining applicabile a tutti i tipi di modello, vedere [Contenuto dei modelli di data mining &#40;Analysis Services - Data mining&#41;](mining-model-content-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="08f00-104">For an explanation of general and statistical terminology related to mining model content that applies to all model types, see [Mining Model Content &#40;Analysis Services - Data Mining&#41;](mining-model-content-analysis-services-data-mining.md).</span></span>  
  
## <a name="understanding-the-structure-of-an-association-model"></a><span data-ttu-id="08f00-105">Informazioni sulla struttura di un modello di associazione</span><span class="sxs-lookup"><span data-stu-id="08f00-105">Understanding the Structure of an Association Model</span></span>  
 <span data-ttu-id="08f00-106">Un modello di associazione ha una struttura semplice.</span><span class="sxs-lookup"><span data-stu-id="08f00-106">An association model has a simple structure.</span></span> <span data-ttu-id="08f00-107">Ogni modello include un singolo nodo padre che rappresenta il modello e i relativi metadati. Ciascun nodo padre è associato a un elenco semplice di set di elementi e regole.</span><span class="sxs-lookup"><span data-stu-id="08f00-107">Each model has a single parent node that represents the model and its metadata, and each parent node has a flat list of itemsets and rules.</span></span> <span data-ttu-id="08f00-108">I set di elementi e le regole non sono organizzati in alberi, ma sono ordinati come illustrato nel diagramma seguente, ossia con i set di elementi seguiti dalle regole.</span><span class="sxs-lookup"><span data-stu-id="08f00-108">The itemsets and rules are not organized in trees, they are ordered with itemsets first and rules next as shown in the following diagram.</span></span>  
  
 <span data-ttu-id="08f00-109">![Struttura del contenuto del modello per i modelli di associazione](../media/modelcontentstructure-assoc.gif "Struttura del contenuto del modello per i modelli di associazione")</span><span class="sxs-lookup"><span data-stu-id="08f00-109">![structure of model content for association models](../media/modelcontentstructure-assoc.gif "structure of model content for association models")</span></span>  
  
 <span data-ttu-id="08f00-110">Ogni set di elementi è contenuto nel proprio nodo (NODE_TYPE = 7).</span><span class="sxs-lookup"><span data-stu-id="08f00-110">Each itemset is contained in its own node (NODE_TYPE = 7).</span></span> <span data-ttu-id="08f00-111">Il *nodo* include la definizione del set di elementi, il numero di case che contengono il set di elementi e altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="08f00-111">The *node* includes the definition of the itemset, the number of cases that contain this itemset, and other information.</span></span>  
  
 <span data-ttu-id="08f00-112">Anche ogni regola è contenuta nel proprio nodo (NODE_TYPE = 8).</span><span class="sxs-lookup"><span data-stu-id="08f00-112">Each rule is also contained in its own node (NODE_TYPE = 8).</span></span> <span data-ttu-id="08f00-113">Una *regola* descrive un modello generale per la modalità di associazione degli elementi.</span><span class="sxs-lookup"><span data-stu-id="08f00-113">A *rule* describes a general pattern for how items are associated.</span></span> <span data-ttu-id="08f00-114">È simile a un'istruzione IF-THEN.</span><span class="sxs-lookup"><span data-stu-id="08f00-114">A rule is like an IF-THEN statement.</span></span> <span data-ttu-id="08f00-115">Il lato sinistro della regola indica una condizione o un set di condizioni esistente.</span><span class="sxs-lookup"><span data-stu-id="08f00-115">The left-hand side of the rule shows an existing condition or set of conditions.</span></span> <span data-ttu-id="08f00-116">Il lato destro indica l'elemento del set di dati solitamente associato alle condizioni riportate a sinistra.</span><span class="sxs-lookup"><span data-stu-id="08f00-116">The right-hand side of the rule shows the item in your data set that is usually associated with the conditions on the left side.</span></span>  
  
 <span data-ttu-id="08f00-117">**Nota** Se si vuole estrarre le regole o i set di elementi, è possibile usare una query che restituisca solo i tipi di nodo desiderati.</span><span class="sxs-lookup"><span data-stu-id="08f00-117">**Note** If you want to extract either the rules or the itemsets, you can use a query to return only the node types that you want.</span></span> <span data-ttu-id="08f00-118">Per altre informazioni, vedere [Esempi di query sul modello di associazione](association-model-query-examples.md).</span><span class="sxs-lookup"><span data-stu-id="08f00-118">For more information, see [Association Model Query Examples](association-model-query-examples.md).</span></span>  
  
## <a name="model-content-for-an-association-model"></a><span data-ttu-id="08f00-119">Contenuto di un modello di associazione</span><span class="sxs-lookup"><span data-stu-id="08f00-119">Model Content for an Association Model</span></span>  
 <span data-ttu-id="08f00-120">In questa sezione vengono forniti dettagli ed esempi relativi solo alle colonne del contenuto dei modelli di data mining pertinenti per i modelli di associazione.</span><span class="sxs-lookup"><span data-stu-id="08f00-120">This section provides detail and examples only for those columns in the mining model content that are relevant for association models.</span></span>  
  
 <span data-ttu-id="08f00-121">Per informazioni sulle colonne generiche del set di righe dello schema, ad esempio MODEL_CATALOG e MODEL_NAME, vedere [Contenuto dei modelli di data mining &#40;Analysis Services - Data mining&#41;](mining-model-content-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="08f00-121">For information about the general-purpose columns in the schema rowset, such as MODEL_CATALOG and MODEL_NAME, see [Mining Model Content &#40;Analysis Services - Data Mining&#41;](mining-model-content-analysis-services-data-mining.md).</span></span>  
  
 <span data-ttu-id="08f00-122">MODEL_CATALOG</span><span class="sxs-lookup"><span data-stu-id="08f00-122">MODEL_CATALOG</span></span>  
 <span data-ttu-id="08f00-123">Nome del database in cui è archiviato il modello.</span><span class="sxs-lookup"><span data-stu-id="08f00-123">Name of the database where the model is stored.</span></span>  
  
 <span data-ttu-id="08f00-124">MODEL_NAME</span><span class="sxs-lookup"><span data-stu-id="08f00-124">MODEL_NAME</span></span>  
 <span data-ttu-id="08f00-125">Nome del modello.</span><span class="sxs-lookup"><span data-stu-id="08f00-125">Name of the model.</span></span>  
  
 <span data-ttu-id="08f00-126">ATTRIBUTE_NAME</span><span class="sxs-lookup"><span data-stu-id="08f00-126">ATTRIBUTE_NAME</span></span>  
 <span data-ttu-id="08f00-127">Nomi degli attributi che corrispondono a questo nodo.</span><span class="sxs-lookup"><span data-stu-id="08f00-127">The names of the attributes that correspond to this node.</span></span>  
  
 <span data-ttu-id="08f00-128">NODE_NAME</span><span class="sxs-lookup"><span data-stu-id="08f00-128">NODE_NAME</span></span>  
 <span data-ttu-id="08f00-129">Il nome del nodo.</span><span class="sxs-lookup"><span data-stu-id="08f00-129">The name of the node.</span></span> <span data-ttu-id="08f00-130">Per un modello di associazione, questa colonna contiene lo stesso valore di NODE_UNIQUE_NAME.</span><span class="sxs-lookup"><span data-stu-id="08f00-130">For an association model, this column contains the same value as NODE_UNIQUE_NAME.</span></span>  
  
 <span data-ttu-id="08f00-131">NODE_UNIQUE_NAME</span><span class="sxs-lookup"><span data-stu-id="08f00-131">NODE_UNIQUE_NAME</span></span>  
 <span data-ttu-id="08f00-132">Nome univoco del nodo.</span><span class="sxs-lookup"><span data-stu-id="08f00-132">The unique name of the node.</span></span>  
  
 <span data-ttu-id="08f00-133">NODE_TYPE</span><span class="sxs-lookup"><span data-stu-id="08f00-133">NODE_TYPE</span></span>  
 <span data-ttu-id="08f00-134">Un modello di associazione restituisce solo i tipi di nodo seguenti:</span><span class="sxs-lookup"><span data-stu-id="08f00-134">A association model outputs only the following node types:</span></span>  
  
|<span data-ttu-id="08f00-135">ID tipo di nodo</span><span class="sxs-lookup"><span data-stu-id="08f00-135">Node Type ID</span></span>|<span data-ttu-id="08f00-136">Type</span><span class="sxs-lookup"><span data-stu-id="08f00-136">Type</span></span>|  
|------------------|----------|  
|<span data-ttu-id="08f00-137">1 (Model)</span><span class="sxs-lookup"><span data-stu-id="08f00-137">1 (Model)</span></span>|<span data-ttu-id="08f00-138">Radice o nodo padre.</span><span class="sxs-lookup"><span data-stu-id="08f00-138">Root or parent node.</span></span>|  
|<span data-ttu-id="08f00-139">7 (Itemset)</span><span class="sxs-lookup"><span data-stu-id="08f00-139">7 (Itemset)</span></span>|<span data-ttu-id="08f00-140">Set di elementi, ovvero raccolta di coppie attributo-valore.</span><span class="sxs-lookup"><span data-stu-id="08f00-140">An itemset, or collection of attribute-value pairs.</span></span> <span data-ttu-id="08f00-141">Esempi:</span><span class="sxs-lookup"><span data-stu-id="08f00-141">Examples:</span></span><br /><br /> `Product 1 = Existing, Product 2 = Existing`<br /><br /> <span data-ttu-id="08f00-142">oppure</span><span class="sxs-lookup"><span data-stu-id="08f00-142">or</span></span><br /><br /> <span data-ttu-id="08f00-143">`Gender = Male`.</span><span class="sxs-lookup"><span data-stu-id="08f00-143">`Gender = Male`.</span></span>|  
|<span data-ttu-id="08f00-144">8 (Rule)</span><span class="sxs-lookup"><span data-stu-id="08f00-144">8 (Rule)</span></span>|<span data-ttu-id="08f00-145">Regola che definisce la modalità di correlazione tra gli elementi.</span><span class="sxs-lookup"><span data-stu-id="08f00-145">A rule defining how items relate to each other.</span></span><br /><br /> <span data-ttu-id="08f00-146">Esempio:</span><span class="sxs-lookup"><span data-stu-id="08f00-146">Example:</span></span><br /><br /> <span data-ttu-id="08f00-147">`Product 1 = Existing, Product 2 = Existing -> Product 3 = Existing`.</span><span class="sxs-lookup"><span data-stu-id="08f00-147">`Product 1 = Existing, Product 2 = Existing -> Product 3 = Existing`.</span></span>|  
  
 <span data-ttu-id="08f00-148">NODE_CAPTION</span><span class="sxs-lookup"><span data-stu-id="08f00-148">NODE_CAPTION</span></span>  
 <span data-ttu-id="08f00-149">Etichetta o didascalia associata al nodo.</span><span class="sxs-lookup"><span data-stu-id="08f00-149">A label or a caption associated with the node.</span></span>  
  
 <span data-ttu-id="08f00-150">**Nodo di set di elementi** Elenco di elementi delimitati da virgole.</span><span class="sxs-lookup"><span data-stu-id="08f00-150">**Itemset node** A comma-separated list of items.</span></span>  
  
 <span data-ttu-id="08f00-151">**Nodo di regola** Contiene i lati sinistro e destro della regola.</span><span class="sxs-lookup"><span data-stu-id="08f00-151">**Rule node** Contains the left and right-hand sides of the rule.</span></span>  
  
 <span data-ttu-id="08f00-152">CHILDREN_CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="08f00-152">CHILDREN_CARDINALITY</span></span>  
 <span data-ttu-id="08f00-153">Indica il numero di figli del nodo corrente.</span><span class="sxs-lookup"><span data-stu-id="08f00-153">Indicates the number of children of the current node.</span></span>  
  
 <span data-ttu-id="08f00-154">**Nodo padre** Indica il numero totale di set di elementi e regole.</span><span class="sxs-lookup"><span data-stu-id="08f00-154">**Parent node** Indicates the total number of itemsets plus rules.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="08f00-155">Per ottenere una suddivisione del conteggio relativo a set di elementi e regole, vedere NODE_DESCRIPTION per il nodo radice del modello.</span><span class="sxs-lookup"><span data-stu-id="08f00-155">To get a breakdown of the count for itemsets and rules, see the NODE_DESCRIPTION for the root node of the model.</span></span>  
  
 <span data-ttu-id="08f00-156">**Nodo di set di elementi o di regola** Sempre 0.</span><span class="sxs-lookup"><span data-stu-id="08f00-156">**Itemset or rule node** Always 0.</span></span>  
  
 <span data-ttu-id="08f00-157">PARENT_UNIQUE_NAME</span><span class="sxs-lookup"><span data-stu-id="08f00-157">PARENT_UNIQUE_NAME</span></span>  
 <span data-ttu-id="08f00-158">Nome univoco dell'elemento padre del nodo.</span><span class="sxs-lookup"><span data-stu-id="08f00-158">The unique name of the node's parent.</span></span>  
  
 <span data-ttu-id="08f00-159">**Nodo padre** Sempre NULL.</span><span class="sxs-lookup"><span data-stu-id="08f00-159">**Parent node** Always NULL.</span></span>  
  
 <span data-ttu-id="08f00-160">**Nodo di set di elementi o di regola** Sempre 0.</span><span class="sxs-lookup"><span data-stu-id="08f00-160">**Itemset or rule node** Always 0.</span></span>  
  
 <span data-ttu-id="08f00-161">NODE_DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="08f00-161">NODE_DESCRIPTION</span></span>  
 <span data-ttu-id="08f00-162">Descrizione semplice del contenuto del nodo.</span><span class="sxs-lookup"><span data-stu-id="08f00-162">A user-friendly description of the contents of the node.</span></span>  
  
 <span data-ttu-id="08f00-163">**Nodo padre** Include un elenco delimitato da virgole delle informazioni seguenti sul modello:</span><span class="sxs-lookup"><span data-stu-id="08f00-163">**Parent node** Includes a comma-separated list of the following information about the model:</span></span>  
  
|<span data-ttu-id="08f00-164">Elemento</span><span class="sxs-lookup"><span data-stu-id="08f00-164">Item</span></span>|<span data-ttu-id="08f00-165">Descrizione</span><span class="sxs-lookup"><span data-stu-id="08f00-165">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="08f00-166">ITEMSET_COUNT</span><span class="sxs-lookup"><span data-stu-id="08f00-166">ITEMSET_COUNT</span></span>|<span data-ttu-id="08f00-167">Conteggio di tutti i set di elementi nel modello.</span><span class="sxs-lookup"><span data-stu-id="08f00-167">Count of all itemsets in model.</span></span>|  
|<span data-ttu-id="08f00-168">RULE_COUNT</span><span class="sxs-lookup"><span data-stu-id="08f00-168">RULE_COUNT</span></span>|<span data-ttu-id="08f00-169">Conteggio di tutte le regole nel modello.</span><span class="sxs-lookup"><span data-stu-id="08f00-169">Count of all rules in model.</span></span>|  
|<span data-ttu-id="08f00-170">MIN_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="08f00-170">MIN_SUPPORT</span></span>|<span data-ttu-id="08f00-171">Supporto minimo individuato per ogni singolo set di elementi.</span><span class="sxs-lookup"><span data-stu-id="08f00-171">The minimum support found for any single itemset.</span></span><br /><br /> <span data-ttu-id="08f00-172">**Nota** Questo valore potrebbe essere diverso da quello impostato per il parametro *MINIMUM_SUPPORT* .</span><span class="sxs-lookup"><span data-stu-id="08f00-172">**Note** This value might differ from the value that you set for the *MINIMUM _SUPPORT* parameter.</span></span>|  
|<span data-ttu-id="08f00-173">MAX_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="08f00-173">MAX_SUPPORT</span></span>|<span data-ttu-id="08f00-174">Supporto massimo individuato per ogni singolo set di elementi.</span><span class="sxs-lookup"><span data-stu-id="08f00-174">The maximum support found for any single itemset.</span></span><br /><br /> <span data-ttu-id="08f00-175">**Nota** Questo valore potrebbe essere diverso da quello impostato per il parametro *MAXIMUM_SUPPORT* .</span><span class="sxs-lookup"><span data-stu-id="08f00-175">**Note** This value might differ from the value that you set for the *MAXIMUM_SUPPORT* parameter.</span></span>|  
|<span data-ttu-id="08f00-176">MIN_ITEMSET_SIZE</span><span class="sxs-lookup"><span data-stu-id="08f00-176">MIN_ITEMSET_SIZE</span></span>|<span data-ttu-id="08f00-177">Dimensione del set di elementi più piccolo, rappresentata come conteggio di elementi.</span><span class="sxs-lookup"><span data-stu-id="08f00-177">The size of the smallest itemset, represented as a count of items.</span></span><br /><br /> <span data-ttu-id="08f00-178">Il valore 0 indica che lo stato `Missing` viene considerato come un elemento indipendente.</span><span class="sxs-lookup"><span data-stu-id="08f00-178">A value of 0 indicates that the `Missing` state was treated as an independent item.</span></span><br /><br /> <span data-ttu-id="08f00-179">**Nota** Il valore predefinito del parametro *MINIMUM_ITEMSET_SIZE* è 1.</span><span class="sxs-lookup"><span data-stu-id="08f00-179">**Note** The default value of the *MINIMUM_ITEMSET_SIZE* parameter is 1.</span></span>|  
|<span data-ttu-id="08f00-180">MAX_ITEMSET_SIZE</span><span class="sxs-lookup"><span data-stu-id="08f00-180">MAX_ITEMSET_SIZE</span></span>|<span data-ttu-id="08f00-181">Indica la dimensione del set di elementi più grande individuato.</span><span class="sxs-lookup"><span data-stu-id="08f00-181">Indicates the size of the largest itemset that was found.</span></span><br /><br /> <span data-ttu-id="08f00-182">**Nota** Questo valore è vincolato dal valore impostato per il parametro *MAX_ITEMSET_SIZE* durante la creazione del modello.</span><span class="sxs-lookup"><span data-stu-id="08f00-182">**Note** This value is constrained by the value that you set for the *MAX_ITEMSET_SIZE* parameter when you created the model.</span></span> <span data-ttu-id="08f00-183">Non può mai superare tale valore, ma può essere minore.</span><span class="sxs-lookup"><span data-stu-id="08f00-183">This value can never exceed that value; however, it can be less.</span></span> <span data-ttu-id="08f00-184">Il valore predefinito è 3.</span><span class="sxs-lookup"><span data-stu-id="08f00-184">The default value is 3.</span></span>|  
|<span data-ttu-id="08f00-185">MIN_PROBABILITY</span><span class="sxs-lookup"><span data-stu-id="08f00-185">MIN_PROBABILITY</span></span>|<span data-ttu-id="08f00-186">Probabilità minima individuata per ogni singolo set di elementi o regola nel modello.</span><span class="sxs-lookup"><span data-stu-id="08f00-186">The minimum probability detected for any single itemset or rule in the model.</span></span><br /><br /> <span data-ttu-id="08f00-187">Esempio: 0,400390625</span><span class="sxs-lookup"><span data-stu-id="08f00-187">Example: 0.400390625</span></span><br /><br /> <span data-ttu-id="08f00-188">**Nota** Per i set di elementi, questo valore è sempre maggiore del valore impostato per il parametro *MINIMUM_PROBABILITY* durante la creazione del modello.</span><span class="sxs-lookup"><span data-stu-id="08f00-188">**Note** For itemsets, this value is always greater than the value that you set for the *MINIMUM_PROBABILITY* parameter when you created the model.</span></span>|  
|<span data-ttu-id="08f00-189">MAX_PROBABILITY</span><span class="sxs-lookup"><span data-stu-id="08f00-189">MAX_PROBABILITY</span></span>|<span data-ttu-id="08f00-190">Probabilità massima individuata per ogni singolo set di elementi o regola nel modello.</span><span class="sxs-lookup"><span data-stu-id="08f00-190">The maximum probability detected for any single itemset or rule in the model.</span></span><br /><br /> <span data-ttu-id="08f00-191">Esempio: 1</span><span class="sxs-lookup"><span data-stu-id="08f00-191">Example: 1</span></span><br /><br /> <span data-ttu-id="08f00-192">**Nota** Non esistono parametri che vincolano la probabilità massima dei set di elementi.</span><span class="sxs-lookup"><span data-stu-id="08f00-192">**Note** There is no parameter to constrain maximum probability of itemsets.</span></span> <span data-ttu-id="08f00-193">Per eliminare gli elementi troppo frequenti, usare il parametro *MAXIMUM_SUPPORT* .</span><span class="sxs-lookup"><span data-stu-id="08f00-193">If you want to eliminate items that are too frequent, use the *MAXIMUM_SUPPORT* parameter instead.</span></span>|  
|<span data-ttu-id="08f00-194">MIN_LIFT</span><span class="sxs-lookup"><span data-stu-id="08f00-194">MIN_LIFT</span></span>|<span data-ttu-id="08f00-195">Livello minimo di accuratezza fornito dal modello per un set di elementi.</span><span class="sxs-lookup"><span data-stu-id="08f00-195">The minimum amount of lift that is provided by the model for any itemset.</span></span><br /><br /> <span data-ttu-id="08f00-196">Esempio: 0,4309369632511</span><span class="sxs-lookup"><span data-stu-id="08f00-196">Example: 0.14309369632511</span></span><br /><br /> <span data-ttu-id="08f00-197">Nota: conoscendo questo valore, è possibile determinare se l'accuratezza è significativa per ogni singolo set di elementi.</span><span class="sxs-lookup"><span data-stu-id="08f00-197">Note: Knowing the minimum lift can help you determine whether the lift for any one itemset is significant.</span></span>|  
|<span data-ttu-id="08f00-198">MAX_LIFT</span><span class="sxs-lookup"><span data-stu-id="08f00-198">MAX_LIFT</span></span>|<span data-ttu-id="08f00-199">Livello massimo di accuratezza fornito dal modello per ogni set di elementi.</span><span class="sxs-lookup"><span data-stu-id="08f00-199">The maximum amount of lift that is provided by the model for any itemset.</span></span><br /><br /> <span data-ttu-id="08f00-200">Esempio: 1,95758227647523 **Nota** Conoscendo questo valore, è possibile determinare se l'accuratezza è significativa per ogni singolo set di elementi.</span><span class="sxs-lookup"><span data-stu-id="08f00-200">Example: 1.95758227647523 **Note** Knowing the maximum lift can help you determine whether the lift for any one itemset is significant.</span></span>|  
  
 <span data-ttu-id="08f00-201">**Nodo di set di elementi** I nodi di set di elementi contengono un elenco di elementi, visualizzato come stringa di testo delimitato da virgole.</span><span class="sxs-lookup"><span data-stu-id="08f00-201">**Itemset node** Itemset nodes contain a list of the items, displayed as a comma-separated text string.</span></span>  
  
 <span data-ttu-id="08f00-202">Esempio:</span><span class="sxs-lookup"><span data-stu-id="08f00-202">Example:</span></span>  
  
 `Touring Tire = Existing, Water Bottle = Existing`  
  
 <span data-ttu-id="08f00-203">Significa che i pneumatici Touring e le bottiglie di acqua sono stati acquistati insieme.</span><span class="sxs-lookup"><span data-stu-id="08f00-203">This means touring tires and water bottles were purchased together.</span></span>  
  
 <span data-ttu-id="08f00-204">**Nodo di regola** I nodi di regola contengono i lati sinistro e destro della regola, separati da una freccia.</span><span class="sxs-lookup"><span data-stu-id="08f00-204">**Rule node** Rule nodes contains a left-hand and right-hand side of the rule, separated by an arrow.</span></span>  
  
 <span data-ttu-id="08f00-205">Esempio: `Touring Tire = Existing, Water Bottle = Existing -> Cycling cap = Existing`</span><span class="sxs-lookup"><span data-stu-id="08f00-205">Example: `Touring Tire = Existing, Water Bottle = Existing -> Cycling cap = Existing`</span></span>  
  
 <span data-ttu-id="08f00-206">Significa che chi ha acquistato un pneumatico Touring e una bottiglia d'acqua è probabile che abbia anche acquistato un berretto da ciclista.</span><span class="sxs-lookup"><span data-stu-id="08f00-206">This means that if someone bought a touring tire and a water bottle, they were also likely to buy a cycling cap.</span></span>  
  
 <span data-ttu-id="08f00-207">NODE_RULE</span><span class="sxs-lookup"><span data-stu-id="08f00-207">NODE_RULE</span></span>  
 <span data-ttu-id="08f00-208">Frammento XML che descrive la regola o il set di elementi incorporato nel nodo.</span><span class="sxs-lookup"><span data-stu-id="08f00-208">An XML fragment that describes the rule or itemset that is embedded in the node.</span></span>  
  
 <span data-ttu-id="08f00-209">**Nodo padre** Vuoto.</span><span class="sxs-lookup"><span data-stu-id="08f00-209">**Parent node** Blank.</span></span>  
  
 <span data-ttu-id="08f00-210">**Nodo di set di elementi** Vuoto.</span><span class="sxs-lookup"><span data-stu-id="08f00-210">**Itemset node** Blank.</span></span>  
  
 <span data-ttu-id="08f00-211">**Nodo di regola** Il frammento XML include informazioni utili aggiuntive sulla regola, come supporto, confidenza e numero di elementi, insieme all'ID del nodo che rappresenta il lato sinistro della regola.</span><span class="sxs-lookup"><span data-stu-id="08f00-211">**Rule node** The XML fragment includes additional useful information about the rule, such as support, confidence, and the number of items, and the ID of the node that represents the left-hand side of the rule.</span></span>  
  
 <span data-ttu-id="08f00-212">MARGINAL_RULE</span><span class="sxs-lookup"><span data-stu-id="08f00-212">MARGINAL_RULE</span></span>  
 <span data-ttu-id="08f00-213">Vuoto.</span><span class="sxs-lookup"><span data-stu-id="08f00-213">Blank.</span></span>  
  
 <span data-ttu-id="08f00-214">NODE_PROBABILITY</span><span class="sxs-lookup"><span data-stu-id="08f00-214">NODE_PROBABILITY</span></span>  
 <span data-ttu-id="08f00-215">Probabilità o punteggio di confidenza associato al set di elementi o alla regola.</span><span class="sxs-lookup"><span data-stu-id="08f00-215">A probability or confidence score associated with the itemset or rule.</span></span>  
  
 <span data-ttu-id="08f00-216">**Nodo padre** Sempre 0.</span><span class="sxs-lookup"><span data-stu-id="08f00-216">**Parent node** Always 0.</span></span>  
  
 <span data-ttu-id="08f00-217">**Nodo di set di elementi** Probabilità del set di elementi.</span><span class="sxs-lookup"><span data-stu-id="08f00-217">**Itemset node** Probability of the itemset.</span></span>  
  
 <span data-ttu-id="08f00-218">**Nodo di regola** Valore di confidenza per la regola.</span><span class="sxs-lookup"><span data-stu-id="08f00-218">**Rule node** Confidence value for the rule.</span></span>  
  
 <span data-ttu-id="08f00-219">MARGINAL_PROBABILITY</span><span class="sxs-lookup"><span data-stu-id="08f00-219">MARGINAL_PROBABILITY</span></span>  
 <span data-ttu-id="08f00-220">Uguale a NODE_PROBABILITY.</span><span class="sxs-lookup"><span data-stu-id="08f00-220">Same as NODE_PROBABILITY.</span></span>  
  
 <span data-ttu-id="08f00-221">NODE_DISTRIBUTION</span><span class="sxs-lookup"><span data-stu-id="08f00-221">NODE_DISTRIBUTION</span></span>  
 <span data-ttu-id="08f00-222">La tabella contiene informazioni molto diverse, a seconda che il nodo sia un set di elementi o una regola.</span><span class="sxs-lookup"><span data-stu-id="08f00-222">The table contains very different information, depending on whether the node is an itemset or a rule.</span></span>  
  
 <span data-ttu-id="08f00-223">**Nodo padre** Vuoto.</span><span class="sxs-lookup"><span data-stu-id="08f00-223">**Parent node** Blank.</span></span>  
  
 <span data-ttu-id="08f00-224">**Nodo di set di elementi** Elenca ogni elemento del set di elementi insieme a un valore di probabilità e di supporto.</span><span class="sxs-lookup"><span data-stu-id="08f00-224">**Itemset node** Lists each item in the itemset together with a probability and support value.</span></span> <span data-ttu-id="08f00-225">Se ad esempio il set di elementi contiene due prodotti, viene riportato il nome di ogni prodotto insieme al conteggio dei case che lo includono.</span><span class="sxs-lookup"><span data-stu-id="08f00-225">For example, if the itemset contains two products, the name of each product is listed, together with the count of cases that include each product.</span></span>  
  
 <span data-ttu-id="08f00-226">**Nodo di regola** Contiene due righe.</span><span class="sxs-lookup"><span data-stu-id="08f00-226">**Rule node** Contains two rows.</span></span> <span data-ttu-id="08f00-227">Nella prima riga è indicato l'attributo del lato destro della regola, ovvero l'elemento stimato, insieme a un punteggio di confidenza.</span><span class="sxs-lookup"><span data-stu-id="08f00-227">The first row shows the attribute from the right-hand side of the rule, which is the predicted item, together with a confidence score.</span></span>  
  
 <span data-ttu-id="08f00-228">La seconda riga è univoca per i modelli di associazione. Contiene un puntatore al set di elementi sul lato destro della regola.</span><span class="sxs-lookup"><span data-stu-id="08f00-228">The second row is unique to association models; it contains a pointer to the itemset on the right-hand side of the rule.</span></span> <span data-ttu-id="08f00-229">Il puntatore è rappresentato nella colonna ATTRIBUTE_VALUE come ID del set di elementi che contiene solo l'elemento di destra.</span><span class="sxs-lookup"><span data-stu-id="08f00-229">The pointer is represented in the ATTRIBUTE_VALUE column as the ID of the itemset that contains only the right-hand item.</span></span>  
  
 <span data-ttu-id="08f00-230">Ad esempio, se la regola è `If {A,B} Then {C}`, la tabella contiene il nome dell'elemento `{C}`e l'ID del nodo che contiene il set di elementi per l'elemento C.</span><span class="sxs-lookup"><span data-stu-id="08f00-230">For example, if the rule is `If {A,B} Then {C}`, the table contains the name of the item `{C}`, and the ID of the node that contains the itemset for item C.</span></span>  
  
 <span data-ttu-id="08f00-231">Questo puntatore è utile perché consente di determinare dal nodo di set di elementi la quantità complessiva di case che includono il prodotto del lato destro.</span><span class="sxs-lookup"><span data-stu-id="08f00-231">This pointer is useful because you can determine from the itemset node how many cases in all include the right-hand side product.</span></span> <span data-ttu-id="08f00-232">I casi soggetti alla regola `If {A,B} Then {C}` sono un subset dei case elencati nel set di elementi per `{C}`.</span><span class="sxs-lookup"><span data-stu-id="08f00-232">The cases that are subject to the rule `If {A,B} Then {C}` are a subset of the cases listed in the itemset for `{C}`.</span></span>  
  
 <span data-ttu-id="08f00-233">NODE_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="08f00-233">NODE_SUPPORT</span></span>  
 <span data-ttu-id="08f00-234">Numero di case che supportano il nodo.</span><span class="sxs-lookup"><span data-stu-id="08f00-234">The number of cases that support this node.</span></span>  
  
 <span data-ttu-id="08f00-235">**Nodo padre** Numero di case nel modello.</span><span class="sxs-lookup"><span data-stu-id="08f00-235">**Parent node** Number of cases in the model.</span></span>  
  
 <span data-ttu-id="08f00-236">**Nodo di set di elementi** Numero di case che contengono tutti gli elementi del set di elementi.</span><span class="sxs-lookup"><span data-stu-id="08f00-236">**Itemset node** Number of cases that contains all items in the itemset.</span></span>  
  
 <span data-ttu-id="08f00-237">**Nodo di regola** Numero di case che contengono tutti gli elementi inclusi nella regola.</span><span class="sxs-lookup"><span data-stu-id="08f00-237">**Rule node** The number of cases that contain all items included in the rule.</span></span>  
  
 <span data-ttu-id="08f00-238">MSOLAP_MODEL_COLUMN</span><span class="sxs-lookup"><span data-stu-id="08f00-238">MSOLAP_MODEL_COLUMN</span></span>  
 <span data-ttu-id="08f00-239">Contiene informazioni diverse a seconda che il nodo sia un set di elementi o una regola.</span><span class="sxs-lookup"><span data-stu-id="08f00-239">Contains different information depending on whether the node is an itemset or rule.</span></span>  
  
 <span data-ttu-id="08f00-240">**Nodo padre** Vuoto.</span><span class="sxs-lookup"><span data-stu-id="08f00-240">**Parent node** Blank.</span></span>  
  
 <span data-ttu-id="08f00-241">**Nodo di set di elementi** Vuoto.</span><span class="sxs-lookup"><span data-stu-id="08f00-241">**Itemset node** Blank.</span></span>  
  
 <span data-ttu-id="08f00-242">**Nodo di regola** ID del set di elementi che contiene gli elementi nel lato sinistro della regola.</span><span class="sxs-lookup"><span data-stu-id="08f00-242">**Rule node** The ID of the itemset that contains the items in the left-hand side of the rule.</span></span> <span data-ttu-id="08f00-243">Ad esempio, se la regola è `If {A,B} Then {C}`, questa colonna contiene l'ID del set di elementi che include solo `{A,B}`.</span><span class="sxs-lookup"><span data-stu-id="08f00-243">For example, if the rule is `If {A,B} Then {C}`, this column contains the ID of the itemset that contains only `{A,B}`.</span></span>  
  
 <span data-ttu-id="08f00-244">MSOLAP_NODE_SCORE</span><span class="sxs-lookup"><span data-stu-id="08f00-244">MSOLAP_NODE_SCORE</span></span>  
 <span data-ttu-id="08f00-245">**Nodo padre** Vuoto.</span><span class="sxs-lookup"><span data-stu-id="08f00-245">**Parent node** Blank.</span></span>  
  
 <span data-ttu-id="08f00-246">**Nodo di set di elementi** Punteggio di priorità per il set di elementi.</span><span class="sxs-lookup"><span data-stu-id="08f00-246">**Itemset node** Importance score for the itemset.</span></span>  
  
 <span data-ttu-id="08f00-247">**Nodo di regola** Punteggio di priorità per la regola.</span><span class="sxs-lookup"><span data-stu-id="08f00-247">**Rule node** Importance score for the rule.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="08f00-248">La priorità viene calcolata in modo diverso per i set di elementi e le regole.</span><span class="sxs-lookup"><span data-stu-id="08f00-248">Importance is calculated differently for itemsets and rules.</span></span> <span data-ttu-id="08f00-249">Per altre informazioni, vedere [Riferimento tecnico per l'algoritmo Microsoft Association Rules](microsoft-association-algorithm-technical-reference.md).</span><span class="sxs-lookup"><span data-stu-id="08f00-249">For more information, see [Microsoft Association Algorithm Technical Reference](microsoft-association-algorithm-technical-reference.md).</span></span>  
  
 <span data-ttu-id="08f00-250">MSOLAP_NODE_SHORT_CAPTION</span><span class="sxs-lookup"><span data-stu-id="08f00-250">MSOLAP_NODE_SHORT_CAPTION</span></span>  
 <span data-ttu-id="08f00-251">Vuoto.</span><span class="sxs-lookup"><span data-stu-id="08f00-251">Blank.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08f00-252">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="08f00-252">See Also</span></span>  
 <span data-ttu-id="08f00-253">[Contenuto del modello di data mining &#40;Analysis Services-&#41;di data mining](mining-model-content-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="08f00-253">[Mining Model Content &#40;Analysis Services - Data Mining&#41;](mining-model-content-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="08f00-254">[Algoritmo Microsoft Association](microsoft-association-algorithm.md) </span><span class="sxs-lookup"><span data-stu-id="08f00-254">[Microsoft Association Algorithm](microsoft-association-algorithm.md) </span></span>  
 [<span data-ttu-id="08f00-255">Esempi di query sul modello di associazione</span><span class="sxs-lookup"><span data-stu-id="08f00-255">Association Model Query Examples</span></span>](association-model-query-examples.md)  
  
  
