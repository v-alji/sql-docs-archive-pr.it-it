---
title: Contenuto dei modelli di data mining per i modelli di clustering (Analysis Services-Data mining) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- nearest neighbor [Data Mining]
- clustering [Data Mining]
- mining model content, clustering models
- clustering algorithms [Analysis Services]
ms.assetid: aed1b7d3-8f20-4eeb-b156-0229f942cefd
author: minewiskan
ms.author: owend
ms.openlocfilehash: 400575d5c6ce8094b67500d15a86137302282fa7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627542"
---
# <a name="mining-model-content-for-clustering-models-analysis-services---data-mining"></a><span data-ttu-id="fa4b1-102">Contenuto dei modelli di data mining per i modelli di clustering (Analysis Services - Data mining)</span><span class="sxs-lookup"><span data-stu-id="fa4b1-102">Mining Model Content for Clustering Models (Analysis Services - Data Mining)</span></span>
  <span data-ttu-id="fa4b1-103">In questo argomento viene descritto il contenuto dei modelli di data mining specifico per i modelli che utilizzano l'algoritmo Microsoft Clustering.</span><span class="sxs-lookup"><span data-stu-id="fa4b1-103">This topic describes mining model content that is specific to models that use the Microsoft Clustering algorithm.</span></span> <span data-ttu-id="fa4b1-104">Per una spiegazione del modello di data mining applicabile a tutti i tipi di modello, vedere [Contenuto del modello di data mining &#40;Analysis Services - Data mining&#41;](mining-model-content-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="fa4b1-104">For a general explanation of mining model content for all model types, see [Mining Model Content &#40;Analysis Services - Data Mining&#41;](mining-model-content-analysis-services-data-mining.md).</span></span>  
  
## <a name="understanding-the-structure-of-a-clustering-model"></a><span data-ttu-id="fa4b1-105">Informazioni sulla struttura di un modello di clustering</span><span class="sxs-lookup"><span data-stu-id="fa4b1-105">Understanding the Structure of a Clustering Model</span></span>  
 <span data-ttu-id="fa4b1-106">Un modello di clustering ha una struttura semplice.</span><span class="sxs-lookup"><span data-stu-id="fa4b1-106">A clustering model has a simple structure.</span></span> <span data-ttu-id="fa4b1-107">Ogni modello include un singolo nodo padre che rappresenta il modello e i relativi metadati e ogni nodo padre è associato a un elenco semplice di cluster (NODE_TYPE = 5).</span><span class="sxs-lookup"><span data-stu-id="fa4b1-107">Each model has a single parent node that represents the model and its metadata, and each parent node has a flat list of clusters (NODE_TYPE = 5).</span></span> <span data-ttu-id="fa4b1-108">Questa organizzazione è illustrata nell'immagine seguente.</span><span class="sxs-lookup"><span data-stu-id="fa4b1-108">This organization is shown in the following image.</span></span>  
  
 <span data-ttu-id="fa4b1-109">![Struttura del contenuto del modello per il clustering](../media/modelcontentstructure-clust.gif "Struttura del contenuto del modello per il clustering")</span><span class="sxs-lookup"><span data-stu-id="fa4b1-109">![structure of model content for clustering](../media/modelcontentstructure-clust.gif "structure of model content for clustering")</span></span>  
  
 <span data-ttu-id="fa4b1-110">Ogni nodo figlio rappresenta un singolo cluster e contiene statistiche dettagliate sugli attributi dei relativi case,</span><span class="sxs-lookup"><span data-stu-id="fa4b1-110">Each child node represents a single cluster and contains detailed statistics about the attributes of the cases in that cluster.</span></span> <span data-ttu-id="fa4b1-111">tra cui un conteggio del numero di case nel cluster e la distribuzione di valori che distinguono un cluster dagli altri.</span><span class="sxs-lookup"><span data-stu-id="fa4b1-111">This includes a count of the number of cases in the cluster, and the distribution of values that distinguish the cluster from other clusters.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fa4b1-112">Non è necessario scorrere i nodi per ottenere un conteggio o una descrizione dei cluster; anche il nodo padre del modello contiene un conteggio e un elenco dei cluster.</span><span class="sxs-lookup"><span data-stu-id="fa4b1-112">You do not need to iterate through the nodes to get a count or description of the clusters; the model parent node also counts and lists the clusters.</span></span>  
  
 <span data-ttu-id="fa4b1-113">Il nodo padre contiene statistiche utili che descrivono la distribuzione effettiva di tutti i case di training.</span><span class="sxs-lookup"><span data-stu-id="fa4b1-113">The parent node contains useful statistics that describe the actual distribution of all the training cases.</span></span> <span data-ttu-id="fa4b1-114">Queste statistiche si trovano nella colonna della tabella nidificata, NODE_DISTRIBUTION.</span><span class="sxs-lookup"><span data-stu-id="fa4b1-114">These statistics are found in the nested table column, NODE_DISTRIBUTION.</span></span> <span data-ttu-id="fa4b1-115">Ad esempio, nella tabella seguente sono illustrate diverse righe della tabella NODE_DISTRIBUTION che descrivono la distribuzione di dati demografici dei clienti per il modello di clustering `TM_Clustering`creato nell' [Esercitazione di base sul data mining](../../tutorials/basic-data-mining-tutorial.md):</span><span class="sxs-lookup"><span data-stu-id="fa4b1-115">For example, the following table shows several rows from the NODE_DISTRIBUTION table that describe the distribution of customer demographics for the clustering model, `TM_Clustering`, that you create in the [Basic Data Mining Tutorial](../../tutorials/basic-data-mining-tutorial.md):</span></span>  
  
|<span data-ttu-id="fa4b1-116">ATTRIBUTE_NAME</span><span class="sxs-lookup"><span data-stu-id="fa4b1-116">ATTRIBUTE_NAME</span></span>|<span data-ttu-id="fa4b1-117">ATTRIBUTE_VALUE</span><span class="sxs-lookup"><span data-stu-id="fa4b1-117">ATRIBUTE_VALUE</span></span>|<span data-ttu-id="fa4b1-118">SUPPORT</span><span class="sxs-lookup"><span data-stu-id="fa4b1-118">SUPPORT</span></span>|<span data-ttu-id="fa4b1-119">PROBABILITY</span><span class="sxs-lookup"><span data-stu-id="fa4b1-119">PROBABILITY</span></span>|<span data-ttu-id="fa4b1-120">variance</span><span class="sxs-lookup"><span data-stu-id="fa4b1-120">VARIANCE</span></span>|<span data-ttu-id="fa4b1-121">VALUE_TYPE</span><span class="sxs-lookup"><span data-stu-id="fa4b1-121">VALUE_TYPE</span></span>|  
|---------------------|---------------------|-------------|-----------------|--------------|-----------------|  
|<span data-ttu-id="fa4b1-122">Età</span><span class="sxs-lookup"><span data-stu-id="fa4b1-122">Age</span></span>|<span data-ttu-id="fa4b1-123">Missing</span><span class="sxs-lookup"><span data-stu-id="fa4b1-123">Missing</span></span>|<span data-ttu-id="fa4b1-124">0</span><span class="sxs-lookup"><span data-stu-id="fa4b1-124">0</span></span>|<span data-ttu-id="fa4b1-125">0</span><span class="sxs-lookup"><span data-stu-id="fa4b1-125">0</span></span>|<span data-ttu-id="fa4b1-126">0</span><span class="sxs-lookup"><span data-stu-id="fa4b1-126">0</span></span>|<span data-ttu-id="fa4b1-127">1 (Mancante)</span><span class="sxs-lookup"><span data-stu-id="fa4b1-127">1 (Missing)</span></span>|  
|<span data-ttu-id="fa4b1-128">Età</span><span class="sxs-lookup"><span data-stu-id="fa4b1-128">Age</span></span>|<span data-ttu-id="fa4b1-129">44.9016152716593</span><span class="sxs-lookup"><span data-stu-id="fa4b1-129">44.9016152716593</span></span>|<span data-ttu-id="fa4b1-130">12939</span><span class="sxs-lookup"><span data-stu-id="fa4b1-130">12939</span></span>|<span data-ttu-id="fa4b1-131">1</span><span class="sxs-lookup"><span data-stu-id="fa4b1-131">1</span></span>|<span data-ttu-id="fa4b1-132">125.663453102554</span><span class="sxs-lookup"><span data-stu-id="fa4b1-132">125.663453102554</span></span>|<span data-ttu-id="fa4b1-133">3 (Continuo)</span><span class="sxs-lookup"><span data-stu-id="fa4b1-133">3 (Continuous)</span></span>|  
|<span data-ttu-id="fa4b1-134">Sesso</span><span class="sxs-lookup"><span data-stu-id="fa4b1-134">Gender</span></span>|<span data-ttu-id="fa4b1-135">Missing</span><span class="sxs-lookup"><span data-stu-id="fa4b1-135">Missing</span></span>|<span data-ttu-id="fa4b1-136">0</span><span class="sxs-lookup"><span data-stu-id="fa4b1-136">0</span></span>|<span data-ttu-id="fa4b1-137">0</span><span class="sxs-lookup"><span data-stu-id="fa4b1-137">0</span></span>|<span data-ttu-id="fa4b1-138">0</span><span class="sxs-lookup"><span data-stu-id="fa4b1-138">0</span></span>|<span data-ttu-id="fa4b1-139">1 (Mancante)</span><span class="sxs-lookup"><span data-stu-id="fa4b1-139">1 (Missing)</span></span>|  
|<span data-ttu-id="fa4b1-140">Sesso</span><span class="sxs-lookup"><span data-stu-id="fa4b1-140">Gender</span></span>|<span data-ttu-id="fa4b1-141">F</span><span class="sxs-lookup"><span data-stu-id="fa4b1-141">F</span></span>|<span data-ttu-id="fa4b1-142">6350</span><span class="sxs-lookup"><span data-stu-id="fa4b1-142">6350</span></span>|<span data-ttu-id="fa4b1-143">0.490764355823479</span><span class="sxs-lookup"><span data-stu-id="fa4b1-143">0.490764355823479</span></span>|<span data-ttu-id="fa4b1-144">0</span><span class="sxs-lookup"><span data-stu-id="fa4b1-144">0</span></span>|<span data-ttu-id="fa4b1-145">4 (discreto)</span><span class="sxs-lookup"><span data-stu-id="fa4b1-145">4 (Discrete)</span></span>|  
|<span data-ttu-id="fa4b1-146">Sesso</span><span class="sxs-lookup"><span data-stu-id="fa4b1-146">Gender</span></span>|<span data-ttu-id="fa4b1-147">M</span><span class="sxs-lookup"><span data-stu-id="fa4b1-147">M</span></span>|<span data-ttu-id="fa4b1-148">6589</span><span class="sxs-lookup"><span data-stu-id="fa4b1-148">6589</span></span>|<span data-ttu-id="fa4b1-149">0.509235644176521</span><span class="sxs-lookup"><span data-stu-id="fa4b1-149">0.509235644176521</span></span>|<span data-ttu-id="fa4b1-150">0</span><span class="sxs-lookup"><span data-stu-id="fa4b1-150">0</span></span>|<span data-ttu-id="fa4b1-151">4 (discreto)</span><span class="sxs-lookup"><span data-stu-id="fa4b1-151">4 (Discrete)</span></span>|  
  
 <span data-ttu-id="fa4b1-152">Da questi risultati emerge che sono stati utilizzati 12939 case per compilare il modello, che il rapporto tra maschi e femmine è approssimativamente 50-50 e che l'età media è 44 anni.</span><span class="sxs-lookup"><span data-stu-id="fa4b1-152">From these results, you can see that there were 12939 cases used to build the model, that the ratio of males to females was about 50-50, and that the mean age was 44.</span></span> <span data-ttu-id="fa4b1-153">Le statistiche descrittive variano a seconda che l'attributo riportato sia un tipo di dati numerico continuo, ad esempio l'età, o un tipo di valore discreto, ad esempio il sesso.</span><span class="sxs-lookup"><span data-stu-id="fa4b1-153">The descriptive statistics vary depending on whether the attribute being reported is a continuous numeric data type, such as age, or a discrete value type, such as gender.</span></span> <span data-ttu-id="fa4b1-154">Le misure statistiche *media* e *varianza* vengono calcolate per i tipi di dati continui, mentre *probabilità* e *supporto* vengono calcolate per i tipi di dati discreti.</span><span class="sxs-lookup"><span data-stu-id="fa4b1-154">The statistical measures *mean* and *variance* are computed for continuous data types, whereas *probability* and *support* are computed for discrete data types.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fa4b1-155">La varianza rappresenta la varianza totale per il cluster.</span><span class="sxs-lookup"><span data-stu-id="fa4b1-155">The variance represents the total variance for the cluster.</span></span> <span data-ttu-id="fa4b1-156">Se il valore relativo alla varianza è piccolo, significa che la maggior parte dei valori della colonna sono relativamente vicini alla media.</span><span class="sxs-lookup"><span data-stu-id="fa4b1-156">When the value for variance is small, it indicates that most values in the column were fairly close to the mean.</span></span> <span data-ttu-id="fa4b1-157">Per ottenere la deviazione standard, calcolare la radice quadrata della varianza.</span><span class="sxs-lookup"><span data-stu-id="fa4b1-157">To obtain the standard deviation, calculate the square root of the variance.</span></span>  
  
 <span data-ttu-id="fa4b1-158">Si noti che per ogni attributo è presente un tipo di valore `Missing` che indica il numero di case in cui i dati per tale attributo sono mancanti.</span><span class="sxs-lookup"><span data-stu-id="fa4b1-158">Note that for each of the attributes there is a `Missing` value type that tells you how many cases had no data for that attribute.</span></span> <span data-ttu-id="fa4b1-159">I dati mancanti possono essere significativi e influiscono sui calcoli in vari modi, a seconda del tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="fa4b1-159">Missing data can be significant and affects calculations in different ways, depending on the data type.</span></span> <span data-ttu-id="fa4b1-160">Per altre informazioni, vedere [Valori mancanti &#40;Analysis Services - Data mining&#41;](missing-values-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="fa4b1-160">For more information, see [Missing Values &#40;Analysis Services - Data Mining&#41;](missing-values-analysis-services-data-mining.md).</span></span>  
  
## <a name="model-content-for-a-clustering-model"></a><span data-ttu-id="fa4b1-161">Contenuto di un modello di clustering</span><span class="sxs-lookup"><span data-stu-id="fa4b1-161">Model Content for a Clustering Model</span></span>  
 <span data-ttu-id="fa4b1-162">In questa sezione vengono forniti dettagli ed esempi relativi solo alle colonne del contenuto dei modelli di data mining pertinenti per i modelli di clustering.</span><span class="sxs-lookup"><span data-stu-id="fa4b1-162">This section provides detail and examples only for those columns in the mining model content that are relevant for clustering models.</span></span>  
  
 <span data-ttu-id="fa4b1-163">Per informazioni sulle colonne generiche del set di righe dello schema, ad esempio MODEL_CATALOG e MODEL_NAME, vedere [Contenuto dei modelli di data mining &#40;Analysis Services - Data mining&#41;](mining-model-content-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="fa4b1-163">For information about the general-purpose columns in the schema rowset, such as MODEL_CATALOG and MODEL_NAME, see [Mining Model Content &#40;Analysis Services - Data Mining&#41;](mining-model-content-analysis-services-data-mining.md).</span></span>  
  
 <span data-ttu-id="fa4b1-164">MODEL_CATALOG</span><span class="sxs-lookup"><span data-stu-id="fa4b1-164">MODEL_CATALOG</span></span>  
 <span data-ttu-id="fa4b1-165">Nome del database in cui è archiviato il modello.</span><span class="sxs-lookup"><span data-stu-id="fa4b1-165">Name of the database where the model is stored.</span></span>  
  
 <span data-ttu-id="fa4b1-166">MODEL_NAME</span><span class="sxs-lookup"><span data-stu-id="fa4b1-166">MODEL_NAME</span></span>  
 <span data-ttu-id="fa4b1-167">Nome del modello.</span><span class="sxs-lookup"><span data-stu-id="fa4b1-167">Name of the model.</span></span>  
  
 <span data-ttu-id="fa4b1-168">ATTRIBUTE_NAME</span><span class="sxs-lookup"><span data-stu-id="fa4b1-168">ATTRIBUTE_NAME</span></span>  
 <span data-ttu-id="fa4b1-169">Sempre vuota nei modelli di clustering perché non è disponibile alcun attributo stimabile nel modello.</span><span class="sxs-lookup"><span data-stu-id="fa4b1-169">Always blank in clustering models because there is no predictable attribute in the mode.</span></span>  
  
 <span data-ttu-id="fa4b1-170">NODE_NAME</span><span class="sxs-lookup"><span data-stu-id="fa4b1-170">NODE_NAME</span></span>  
 <span data-ttu-id="fa4b1-171">Sempre uguale a NODE_UNIQUE_NAME.</span><span class="sxs-lookup"><span data-stu-id="fa4b1-171">Always same as NODE_UNIQUE_NAME.</span></span>  
  
 <span data-ttu-id="fa4b1-172">NODE_UNIQUE_NAME</span><span class="sxs-lookup"><span data-stu-id="fa4b1-172">NODE_UNIQUE_NAME</span></span>  
 <span data-ttu-id="fa4b1-173">Identificatore univoco del nodo all'interno del modello.</span><span class="sxs-lookup"><span data-stu-id="fa4b1-173">A unique identifier for the node within the model.</span></span> <span data-ttu-id="fa4b1-174">Questo valore non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="fa4b1-174">This value cannot be changed.</span></span>  
  
 <span data-ttu-id="fa4b1-175">NODE_TYPE</span><span class="sxs-lookup"><span data-stu-id="fa4b1-175">NODE_TYPE</span></span>  
 <span data-ttu-id="fa4b1-176">Un modello di clustering restituisce i tipi di nodo seguenti:</span><span class="sxs-lookup"><span data-stu-id="fa4b1-176">A clustering model outputs the following node types:</span></span>  
  
|<span data-ttu-id="fa4b1-177">ID e nome del nodo</span><span class="sxs-lookup"><span data-stu-id="fa4b1-177">Node ID and Name</span></span>|<span data-ttu-id="fa4b1-178">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fa4b1-178">Description</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="fa4b1-179">1 (Model)</span><span class="sxs-lookup"><span data-stu-id="fa4b1-179">1 (Model)</span></span>|<span data-ttu-id="fa4b1-180">Nodo radice per il modello.</span><span class="sxs-lookup"><span data-stu-id="fa4b1-180">Root node for model.</span></span>|  
|<span data-ttu-id="fa4b1-181">5 (Cluster)</span><span class="sxs-lookup"><span data-stu-id="fa4b1-181">5 (Cluster)</span></span>|<span data-ttu-id="fa4b1-182">Contiene un conteggio dei case nel cluster, le caratteristiche dei case nel cluster e statistiche che descrivono i valori nel cluster.</span><span class="sxs-lookup"><span data-stu-id="fa4b1-182">Contains a count of cases in the cluster, the characteristics of cases in the cluster, and statistics that describe the values in the cluster.</span></span>|  
  
 <span data-ttu-id="fa4b1-183">NODE_CAPTION</span><span class="sxs-lookup"><span data-stu-id="fa4b1-183">NODE_CAPTION</span></span>  
 <span data-ttu-id="fa4b1-184">Nome descrittivo a scopo di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="fa4b1-184">A friendly name for display purposes.</span></span> <span data-ttu-id="fa4b1-185">Quando si crea un modello, il valore di NODE_UNIQUE_NAME viene automaticamente utilizzato come didascalia.</span><span class="sxs-lookup"><span data-stu-id="fa4b1-185">When you create a model, the value of NODE_UNIQUE_NAME is automatically used as the caption.</span></span> <span data-ttu-id="fa4b1-186">Tuttavia, è possibile modificare il valore di NODE_CAPTION per aggiornare il nome visualizzato per il cluster, a livello di programmazione o tramite il visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="fa4b1-186">However, you can change the value for NODE_CAPTION to update the display name for the cluster, either programmatically or by using the viewer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fa4b1-187">Quando si rielabora il modello, tutte le modifiche dei nomi verranno sovrascritte dai nuovi valori.</span><span class="sxs-lookup"><span data-stu-id="fa4b1-187">When you reprocess the model, all name changes will be overwritten by the new values.</span></span> <span data-ttu-id="fa4b1-188">Non è possibile impostare come persistenti i nomi nel modello né effettuare il rilevamento delle modifiche nell'appartenenza al cluster tra versioni diverse di un modello.</span><span class="sxs-lookup"><span data-stu-id="fa4b1-188">You cannot persist names in the model, or track changes in cluster membership between different versions of a model.</span></span>  
  
 <span data-ttu-id="fa4b1-189">CHILDREN_CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="fa4b1-189">CHILDREN_CARDINALITY</span></span>  
 <span data-ttu-id="fa4b1-190">Stima del numero di nodi figlio del nodo.</span><span class="sxs-lookup"><span data-stu-id="fa4b1-190">An estimate of the number of children that the node has.</span></span>  
  
 <span data-ttu-id="fa4b1-191">**Nodo padre** Indica il numero di cluster nel modello.</span><span class="sxs-lookup"><span data-stu-id="fa4b1-191">**Parent node** Indicates the number of clusters in the model.</span></span>  
  
 <span data-ttu-id="fa4b1-192">**Nodi del cluster** Sempre 0.</span><span class="sxs-lookup"><span data-stu-id="fa4b1-192">**Cluster nodes** Always 0.</span></span>  
  
 <span data-ttu-id="fa4b1-193">PARENT_UNIQUE_NAME</span><span class="sxs-lookup"><span data-stu-id="fa4b1-193">PARENT_UNIQUE_NAME</span></span>  
 <span data-ttu-id="fa4b1-194">Nome univoco dell'elemento padre del nodo.</span><span class="sxs-lookup"><span data-stu-id="fa4b1-194">The unique name of the node's parent.</span></span>  
  
 <span data-ttu-id="fa4b1-195">**Nodo padre** Sempre NULL.</span><span class="sxs-lookup"><span data-stu-id="fa4b1-195">**Parent node** Always NULL</span></span>  
  
 <span data-ttu-id="fa4b1-196">**Nodi del cluster** Solitamente 000.</span><span class="sxs-lookup"><span data-stu-id="fa4b1-196">**Cluster nodes** Usually 000.</span></span>  
  
 <span data-ttu-id="fa4b1-197">NODE_DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="fa4b1-197">NODE_DESCRIPTION</span></span>  
 <span data-ttu-id="fa4b1-198">Descrizione del nodo.</span><span class="sxs-lookup"><span data-stu-id="fa4b1-198">A description of the node.</span></span>  
  
 <span data-ttu-id="fa4b1-199">**Nodo padre** Sempre **(All)**.</span><span class="sxs-lookup"><span data-stu-id="fa4b1-199">**Parent node** Always **(All)**.</span></span>  
  
 <span data-ttu-id="fa4b1-200">**Nodi del cluster** Elenco delimitato da virgole degli attributi principali che distinguono il cluster dagli altri.</span><span class="sxs-lookup"><span data-stu-id="fa4b1-200">**Cluster nodes** A comma-separated list of the primary attributes that distinguish the cluster from other clusters.</span></span>  
  
 <span data-ttu-id="fa4b1-201">NODE_RULE</span><span class="sxs-lookup"><span data-stu-id="fa4b1-201">NODE_RULE</span></span>  
 <span data-ttu-id="fa4b1-202">Opzione non utilizzata per i modelli di clustering.</span><span class="sxs-lookup"><span data-stu-id="fa4b1-202">Not used for clustering models.</span></span>  
  
 <span data-ttu-id="fa4b1-203">MARGINAL_RULE</span><span class="sxs-lookup"><span data-stu-id="fa4b1-203">MARGINAL_RULE</span></span>  
 <span data-ttu-id="fa4b1-204">Opzione non utilizzata per i modelli di clustering.</span><span class="sxs-lookup"><span data-stu-id="fa4b1-204">Not used for clustering models.</span></span>  
  
 <span data-ttu-id="fa4b1-205">NODE_PROBABILITY</span><span class="sxs-lookup"><span data-stu-id="fa4b1-205">NODE_PROBABILITY</span></span>  
 <span data-ttu-id="fa4b1-206">Probabilità associata a questo nodo.</span><span class="sxs-lookup"><span data-stu-id="fa4b1-206">The probability associated with this node.</span></span> <span data-ttu-id="fa4b1-207">**Nodo padre** Sempre 1.</span><span class="sxs-lookup"><span data-stu-id="fa4b1-207">**Parent node** Always 1.</span></span>  
  
 <span data-ttu-id="fa4b1-208">**Nodi del cluster** La probabilità rappresenta la probabilità composta degli attributi, con alcuni adattamenti a seconda dell'algoritmo usato per creare il modello di clustering.</span><span class="sxs-lookup"><span data-stu-id="fa4b1-208">**Cluster nodes** The probability represents the compound probability of the attributes, with some adjustments depending on the algorithm used to create the clustering model.</span></span>  
  
 <span data-ttu-id="fa4b1-209">MARGINAL_PROBABILITY</span><span class="sxs-lookup"><span data-stu-id="fa4b1-209">MARGINAL_PROBABILITY</span></span>  
 <span data-ttu-id="fa4b1-210">Probabilità di raggiungere il nodo dal nodo padre.</span><span class="sxs-lookup"><span data-stu-id="fa4b1-210">The probability of reaching the node from the parent node.</span></span> <span data-ttu-id="fa4b1-211">In un modello di clustering la probabilità marginale corrisponde sempre alla probabilità del nodo.</span><span class="sxs-lookup"><span data-stu-id="fa4b1-211">In a clustering model, the marginal probability is always the same as the node probability.</span></span>  
  
 <span data-ttu-id="fa4b1-212">NODE_DISTRIBUTION</span><span class="sxs-lookup"><span data-stu-id="fa4b1-212">NODE_DISTRIBUTION</span></span>  
 <span data-ttu-id="fa4b1-213">Tabella contenente l'istogramma delle probabilità del nodo.</span><span class="sxs-lookup"><span data-stu-id="fa4b1-213">A table that contains the probability histogram of the node.</span></span>  
  
 <span data-ttu-id="fa4b1-214">**Nodo padre** Vedere l'introduzione di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="fa4b1-214">**Parent node** See the Introduction to this topic.</span></span>  
  
 <span data-ttu-id="fa4b1-215">**Nodi del cluster** Rappresenta la distribuzione di attributi e valori per i case inclusi nel cluster.</span><span class="sxs-lookup"><span data-stu-id="fa4b1-215">**Cluster nodes** Represents the distribution of attributes and values for cases that are included in this cluster.</span></span>  
  
 <span data-ttu-id="fa4b1-216">NODE_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="fa4b1-216">NODE_SUPPORT</span></span>  
 <span data-ttu-id="fa4b1-217">Numero di case che supportano il nodo.</span><span class="sxs-lookup"><span data-stu-id="fa4b1-217">The number of cases that support this node.</span></span> <span data-ttu-id="fa4b1-218">**Nodo padre** Indica il numero di case di training per l'intero modello.</span><span class="sxs-lookup"><span data-stu-id="fa4b1-218">**Parent node** Indicates the number of training cases for the entire model.</span></span>  
  
 <span data-ttu-id="fa4b1-219">**Nodi del cluster** Indica la dimensione del cluster come numero di case.</span><span class="sxs-lookup"><span data-stu-id="fa4b1-219">**Cluster nodes** Indicates the size of the cluster as a number of cases.</span></span>  
  
 <span data-ttu-id="fa4b1-220">**Nota** Se il modello usa il clustering K-medie, ogni case può appartenere a un unico cluster.</span><span class="sxs-lookup"><span data-stu-id="fa4b1-220">**Note** If the model uses K-Means clustering, each case can belong to only one cluster.</span></span> <span data-ttu-id="fa4b1-221">Se invece il modello utilizza il clustering EM, ogni case può appartenere a cluster diversi e gli viene assegnata una distanza ponderata per ogni cluster cui appartiene.</span><span class="sxs-lookup"><span data-stu-id="fa4b1-221">However, if the model uses EM clustering, each case can belong to different cluster, and the case is assigned a weighted distance for each cluster to which it belongs.</span></span> <span data-ttu-id="fa4b1-222">Pertanto, per i modelli EM la somma del supporto per un singolo cluster è maggiore del supporto per il modello complessivo.</span><span class="sxs-lookup"><span data-stu-id="fa4b1-222">Therefore, for EM models the sum of support for an individual cluster is greater than support for the overall model.</span></span>  
  
 <span data-ttu-id="fa4b1-223">MSOLAP_MODEL_COLUMN</span><span class="sxs-lookup"><span data-stu-id="fa4b1-223">MSOLAP_MODEL_COLUMN</span></span>  
 <span data-ttu-id="fa4b1-224">Opzione non utilizzata per i modelli di clustering.</span><span class="sxs-lookup"><span data-stu-id="fa4b1-224">Not used for clustering models.</span></span>  
  
 <span data-ttu-id="fa4b1-225">MSOLAP_NODE_SCORE</span><span class="sxs-lookup"><span data-stu-id="fa4b1-225">MSOLAP_NODE_SCORE</span></span>  
 <span data-ttu-id="fa4b1-226">Visualizza un punteggio associato al nodo.</span><span class="sxs-lookup"><span data-stu-id="fa4b1-226">Displays a score associated with the node.</span></span>  
  
 <span data-ttu-id="fa4b1-227">**Nodo padre** Punteggio BIC (Bayesian Information Criterion) per il modello di clustering.</span><span class="sxs-lookup"><span data-stu-id="fa4b1-227">**Parent node** The Bayesian Information Criterion (BIC) score for the clustering model.</span></span>  
  
 <span data-ttu-id="fa4b1-228">**Nodi del cluster** Sempre 0.</span><span class="sxs-lookup"><span data-stu-id="fa4b1-228">**Cluster nodes** Always 0.</span></span>  
  
 <span data-ttu-id="fa4b1-229">MSOLAP_NODE_SHORT_CAPTION</span><span class="sxs-lookup"><span data-stu-id="fa4b1-229">MSOLAP_NODE_SHORT_CAPTION</span></span>  
 <span data-ttu-id="fa4b1-230">Etichetta utilizzata a scopo di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="fa4b1-230">A label used for display purposes.</span></span> <span data-ttu-id="fa4b1-231">Questa didascalia non può essere modificata.</span><span class="sxs-lookup"><span data-stu-id="fa4b1-231">You cannot change this caption.</span></span>  
  
 <span data-ttu-id="fa4b1-232">**Nodo padre** Tipo di modello: modello di cluster</span><span class="sxs-lookup"><span data-stu-id="fa4b1-232">**Parent node** The type of model: Cluster model</span></span>  
  
 <span data-ttu-id="fa4b1-233">**Nodi del cluster** Nome del cluster.</span><span class="sxs-lookup"><span data-stu-id="fa4b1-233">**Cluster nodes** The name of the cluster.</span></span> <span data-ttu-id="fa4b1-234">Esempio: Cluster 1.</span><span class="sxs-lookup"><span data-stu-id="fa4b1-234">Example: Cluster 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fa4b1-235">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="fa4b1-235">Remarks</span></span>  
 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="fa4b1-236">offre più metodi per la creazione di un modello di clustering.</span><span class="sxs-lookup"><span data-stu-id="fa4b1-236">provides multiple methods for creating a clustering model.</span></span> <span data-ttu-id="fa4b1-237">Se non si conosce il metodo impiegato per creare il modello in uso, è possibile recuperare a livello di programmazione i metadati del modello, utilizzando un client ADOMD o AMO oppure eseguendo una query sul set di righe dello schema di data mining.</span><span class="sxs-lookup"><span data-stu-id="fa4b1-237">If you do not know which method was used to create the model that you are working with, you can retrieve the model metadata programmatically, by using an ADOMD client or AMO, or by querying the data mining schema rowset.</span></span> <span data-ttu-id="fa4b1-238">Per altre informazioni, vedere [Eseguire query sui parametri usati per creare un modello di data mining](query-the-parameters-used-to-create-a-mining-model.md).</span><span class="sxs-lookup"><span data-stu-id="fa4b1-238">For more information, see [Query the Parameters Used to Create a Mining Model](query-the-parameters-used-to-create-a-mining-model.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fa4b1-239">La struttura e il contenuto del modello rimangono invariati, indipendentemente dal metodo di clustering o dai parametri utilizzati.</span><span class="sxs-lookup"><span data-stu-id="fa4b1-239">The structure and content of the model stay the same, regardless of which clustering method or parameters you use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa4b1-240">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fa4b1-240">See Also</span></span>  
 <span data-ttu-id="fa4b1-241">[Contenuto del modello di data mining &#40;Analysis Services-&#41;di data mining](mining-model-content-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="fa4b1-241">[Mining Model Content &#40;Analysis Services - Data Mining&#41;](mining-model-content-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="fa4b1-242">[Visualizzatori modello di data mining](data-mining-model-viewers.md) </span><span class="sxs-lookup"><span data-stu-id="fa4b1-242">[Data Mining Model Viewers](data-mining-model-viewers.md) </span></span>  
 <span data-ttu-id="fa4b1-243">[Algoritmo Microsoft Clustering](microsoft-clustering-algorithm.md) </span><span class="sxs-lookup"><span data-stu-id="fa4b1-243">[Microsoft Clustering Algorithm](microsoft-clustering-algorithm.md) </span></span>  
 [<span data-ttu-id="fa4b1-244">Query di data mining</span><span class="sxs-lookup"><span data-stu-id="fa4b1-244">Data Mining Queries</span></span>](data-mining-queries.md)  
  
  
