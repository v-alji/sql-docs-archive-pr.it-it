---
title: Esecuzione di query sui set di righe dello schema di data mining (Analysis Services-Data mining) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- schema rowsets [Analysis Services], data mining
- data mining [Analysis Services], queries
- mining model content
- data mining [Analysis Services], schema rowsets
- schema rowsets [Analysis Services], retrieving
- data mining [Analysis Services], troubleshooting
ms.assetid: 442d8c29-07c7-45de-9a15-d556059f68d7
author: minewiskan
ms.author: owend
ms.openlocfilehash: d60c802256454ee68d04392e685fa4acabf6c12e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635888"
---
# <a name="querying-the-data-mining-schema-rowsets-analysis-services---data-mining"></a><span data-ttu-id="f5dbb-102">Esecuzione di query sui set di righe dello schema di data mining (Analysis Services - Data mining)</span><span class="sxs-lookup"><span data-stu-id="f5dbb-102">Querying the Data Mining Schema Rowsets (Analysis Services - Data Mining)</span></span>
  <span data-ttu-id="f5dbb-103">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]molti dei set di righe esistenti dello schema di data mining OLE DB sono esposti come set di tabelle di sistema su cui è possibile eseguire query tramite istruzioni DMX (Data Mining Extensions).</span><span class="sxs-lookup"><span data-stu-id="f5dbb-103">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], many of the existing OLE DB data mining schema rowsets are exposed as a set of system tables that you can query by using Data Mining Extensions (DMX) statements.</span></span> <span data-ttu-id="f5dbb-104">Mediante la creazione di query sul set di righe dello schema di data mining, è possibile identificare i servizi disponibili, ottenere aggiornamenti sullo stato dei modelli e delle strutture e trovare dettagli sul contenuto del modello o sui parametri.</span><span class="sxs-lookup"><span data-stu-id="f5dbb-104">By creating queries against the data mining schema rowset, you can identify the services that are available, get updates on the status of your models and structures, and find out details about the model content or parameters.</span></span> <span data-ttu-id="f5dbb-105">Per una descrizione dei set di righe dello schema di data mining, vedere [Data Mining Schema Rowsets](../../relational-databases/native-client-ole-db-rowsets/rowsets.md).</span><span class="sxs-lookup"><span data-stu-id="f5dbb-105">For a description of the data mining schema rowsets, see [Data Mining Schema Rowsets](../../relational-databases/native-client-ole-db-rowsets/rowsets.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f5dbb-106">È anche possibile eseguire una query sul set di righe dello schema di data mining utilizzando l'analisi XMLA.</span><span class="sxs-lookup"><span data-stu-id="f5dbb-106">You can also query the data mining schema rowsets by using XMLA.</span></span> <span data-ttu-id="f5dbb-107">Per altre informazioni sull'esecuzione di questa operazione in SQL Server Management Studio, vedere [Creare una query di data mining utilizzando XMLA](create-a-data-mining-query-by-using-xmla.md).</span><span class="sxs-lookup"><span data-stu-id="f5dbb-107">For more information about how to do this in SQL Server Management Studio, see [Create a Data Mining Query by Using XMLA](create-a-data-mining-query-by-using-xmla.md).</span></span>  
  
## <a name="list-of-data-mining-schema-rowsets"></a><span data-ttu-id="f5dbb-108">Elenco di set di righe dello schema di data mining</span><span class="sxs-lookup"><span data-stu-id="f5dbb-108">List of Data Mining Schema Rowsets</span></span>  
 <span data-ttu-id="f5dbb-109">Nella tabella seguente sono elencati i set di righe dello schema di data mining che possono essere utili per l'esecuzione delle query e il monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="f5dbb-109">The following table lists the data mining schema rowsets that may be useful for querying and monitoring.</span></span>  
  
|<span data-ttu-id="f5dbb-110">Nome del set di righe</span><span class="sxs-lookup"><span data-stu-id="f5dbb-110">Rowset name</span></span>|<span data-ttu-id="f5dbb-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f5dbb-111">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="f5dbb-112">DMSCHEMA_MINING_MODELS</span><span class="sxs-lookup"><span data-stu-id="f5dbb-112">DMSCHEMA_MINING_MODELS</span></span>|<span data-ttu-id="f5dbb-113">Elenca tutti i modelli di data mining nel contesto corrente.</span><span class="sxs-lookup"><span data-stu-id="f5dbb-113">Lists all mining models in the current context.</span></span><br /><br /> <span data-ttu-id="f5dbb-114">Include informazioni quali la data di creazione, i parametri utilizzati per creare il modello e la dimensione del set di training.</span><span class="sxs-lookup"><span data-stu-id="f5dbb-114">Includes such information as the date created, parameters used to create the model, and the size of the training set.</span></span>|  
|<span data-ttu-id="f5dbb-115">DMSCHEMA_MINING_COLUMNS</span><span class="sxs-lookup"><span data-stu-id="f5dbb-115">DMSCHEMA_MINING_COLUMNS</span></span>|<span data-ttu-id="f5dbb-116">Elenca tutte le colonne utilizzate nei modelli di data mining nel contesto corrente.</span><span class="sxs-lookup"><span data-stu-id="f5dbb-116">Lists all columns used in mining models in the current context.</span></span><br /><br /> <span data-ttu-id="f5dbb-117">Le informazioni specificano il mapping a una colonna di origine della struttura di data mining, il tipo di dati, la precisione e le funzioni di stima che possono essere utilizzate con la colonna.</span><span class="sxs-lookup"><span data-stu-id="f5dbb-117">Information includes mapping to mining structure source column, data type, precision, and prediction functions that can be used with the column.</span></span>|  
|<span data-ttu-id="f5dbb-118">DMSCHEMA_MINING_STRUCTURES</span><span class="sxs-lookup"><span data-stu-id="f5dbb-118">DMSCHEMA_MINING_STRUCTURES</span></span>|<span data-ttu-id="f5dbb-119">Elenca tutte le strutture di data mining nel contesto corrente.</span><span class="sxs-lookup"><span data-stu-id="f5dbb-119">Lists all mining structure in the current context.</span></span><br /><br /> <span data-ttu-id="f5dbb-120">Le informazioni specificano se la struttura viene popolata, la data dell'ultima elaborazione della struttura e la definizione del set di dati di controllo per la struttura, se disponibile.</span><span class="sxs-lookup"><span data-stu-id="f5dbb-120">Information includes whether the structure is populated, the date the structure was last processed, and the definition of the holdout data set for the structure, if any.</span></span>|  
|<span data-ttu-id="f5dbb-121">DMSCHEMA_MINING_STRUCTURE_COLUMNS</span><span class="sxs-lookup"><span data-stu-id="f5dbb-121">DMSCHEMA_MINING_STRUCTURE_COLUMNS</span></span>|<span data-ttu-id="f5dbb-122">Elenca tutte le colonne utilizzate nelle strutture di data mining nel contesto corrente.</span><span class="sxs-lookup"><span data-stu-id="f5dbb-122">Lists all columns used in mining structures in the current context.</span></span><br /><br /> <span data-ttu-id="f5dbb-123">Le informazioni specificano il tipo di contenuto e il tipo di dati, l'eventuale supporto dei valori Null e la presenza o meno di dati di tabella nidificati nella colonna.</span><span class="sxs-lookup"><span data-stu-id="f5dbb-123">Information includes content type and data type, nullability, and whether the column contains nested table data.</span></span>|  
|<span data-ttu-id="f5dbb-124">DMSCHEMA_MINING_SERVICES</span><span class="sxs-lookup"><span data-stu-id="f5dbb-124">DMSCHEMA_MINING_SERVICES</span></span>|<span data-ttu-id="f5dbb-125">Elenca tutti i servizi di data mining, o algoritmi, disponibili sul server specificato.</span><span class="sxs-lookup"><span data-stu-id="f5dbb-125">Lists all mining services, or algorithms, that are available on the specified server.</span></span><br /><br /> <span data-ttu-id="f5dbb-126">Le informazioni specificano i flag di modellazione supportati, i tipi di input e i tipi di origine dati supportati.</span><span class="sxs-lookup"><span data-stu-id="f5dbb-126">Information includes supported modeling flags, input types, and supported data source types.</span></span>|  
|<span data-ttu-id="f5dbb-127">DMSCHEMA_MINING_SERVICE_PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f5dbb-127">DMSCHEMA_MINING_SERVICE_PARAMETERS</span></span>|<span data-ttu-id="f5dbb-128">Elenca tutti i parametri per i servizi di data mining disponibili nell'istanza corrente.</span><span class="sxs-lookup"><span data-stu-id="f5dbb-128">Lists all parameters for the mining services that are available on the current instance.</span></span><br /><br /> <span data-ttu-id="f5dbb-129">Le informazioni includono il tipo di dati per ogni parametro, i valori predefiniti e i limiti superiore e inferiore.</span><span class="sxs-lookup"><span data-stu-id="f5dbb-129">Information includes the data type for each parameter, the default values, and the upper and lower limits.</span></span>|  
|<span data-ttu-id="f5dbb-130">DMSCHEMA_MODEL_CONTENT</span><span class="sxs-lookup"><span data-stu-id="f5dbb-130">DMSCHEMA_MODEL_CONTENT</span></span>|<span data-ttu-id="f5dbb-131">Restituisce il contenuto del modello se il modello è stato elaborato.</span><span class="sxs-lookup"><span data-stu-id="f5dbb-131">Returns the content of the model if the model has been processed.</span></span><br /><br /> <span data-ttu-id="f5dbb-132">Per altre informazioni, vedere [Contenuto del modello di data mining &#40;Analysis Services - Data mining&#41;](mining-model-content-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="f5dbb-132">For more information, see [Mining Model Content &#40;Analysis Services - Data Mining&#41;](mining-model-content-analysis-services-data-mining.md).</span></span>|  
|<span data-ttu-id="f5dbb-133">DBSCHEMA_CATALOGS</span><span class="sxs-lookup"><span data-stu-id="f5dbb-133">DBSCHEMA_CATALOGS</span></span>|<span data-ttu-id="f5dbb-134">Elenca tutti i database (cataloghi) nell'istanza corrente di Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="f5dbb-134">Lists all databases (catalogs) in the current instance of Analysis Services.</span></span>|  
|<span data-ttu-id="f5dbb-135">MDSCHEMA_INPUT_DATASOURCES</span><span class="sxs-lookup"><span data-stu-id="f5dbb-135">MDSCHEMA_INPUT_DATASOURCES</span></span>|<span data-ttu-id="f5dbb-136">Elenca tutte le origini dati nell'istanza corrente di Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="f5dbb-136">Lists all data sources in the current instance of Analysis Services.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="f5dbb-137">L'elenco nella tabella non è completo in quanto contiene solo i set di righe che possono essere utili per la risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="f5dbb-137">The list in the table is not comprehensive; it shows only those rowsets that may be of most interest for troubleshooting.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="f5dbb-138">Esempi</span><span class="sxs-lookup"><span data-stu-id="f5dbb-138">Examples</span></span>  
 <span data-ttu-id="f5dbb-139">Nella sezione seguente sono riportati alcuni esempi di query sui set di righe dello schema di data mining.</span><span class="sxs-lookup"><span data-stu-id="f5dbb-139">The following section provides some examples of queries against the data mining schema rowsets.</span></span>  
  
### <a name="example-1-list-data-mining-services"></a><span data-ttu-id="f5dbb-140">Esempio 1: Elenco di servizi di data mining</span><span class="sxs-lookup"><span data-stu-id="f5dbb-140">Example 1: List Data Mining Services</span></span>  
 <span data-ttu-id="f5dbb-141">Nella query seguente viene restituito un elenco di servizi di data mining disponibili sul server corrente, che indica gli algoritmi abilitati.</span><span class="sxs-lookup"><span data-stu-id="f5dbb-141">The following query returns a list of the mining services that are available on the current server, meaning the algorithms that are enabled.</span></span> <span data-ttu-id="f5dbb-142">Le colonne specificate per ogni servizio di data mining includono i flag di modellazione e i tipi di contenuto che possono essere utilizzati con ogni algoritmo, il GUID di ogni servizio e gli eventuali limiti di stima che potrebbero essere stati specificati per ogni servizio.</span><span class="sxs-lookup"><span data-stu-id="f5dbb-142">The columns provided for each mining service include the modeling flags and content types that can be used by each algorithm, the GUID for each service, and any prediction limits that may have been added for each service.</span></span>  
  
```  
SELECT *  
FROM $system.DMSCHEMA_MINING_SERVICES  
```  
  
### <a name="example-2-list-mining-model-parameters"></a><span data-ttu-id="f5dbb-143">Esempio 2: Elenco di parametri del modello di data mining</span><span class="sxs-lookup"><span data-stu-id="f5dbb-143">Example 2: List Mining Model Parameters</span></span>  
 <span data-ttu-id="f5dbb-144">Nell'esempio seguente vengono restituiti i parametri utilizzati per creare uno specifico modello di data mining:</span><span class="sxs-lookup"><span data-stu-id="f5dbb-144">The following example returns the parameters that were used to create a specific mining model:</span></span>  
  
```  
SELECT MINING_PARAMETERS   
FROM $system.DMSCHEMA_MINING_MODELS  
WHERE MODEL_NAME = 'TM Clustering'  
```  
  
### <a name="example-3-list-all-rowsets"></a><span data-ttu-id="f5dbb-145">Esempio 3: Elenco di tutti i set di righe</span><span class="sxs-lookup"><span data-stu-id="f5dbb-145">Example 3: List All Rowsets</span></span>  
 <span data-ttu-id="f5dbb-146">Nell'esempio seguente viene restituito un elenco completo di set di righe disponibili nel server corrente:</span><span class="sxs-lookup"><span data-stu-id="f5dbb-146">The following example returns a comprehensive list of the rowsets that are available on the current server:</span></span>  
  
```  
SELECT *   
FROM $system.DBSCHEMA_TABLES  
```  
  
## <a name="see-also"></a><span data-ttu-id="f5dbb-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f5dbb-147">See Also</span></span>  
 [<span data-ttu-id="f5dbb-148">Concetti relativi alla risoluzione dei problemi (Analysis Services - Dati mining)</span><span class="sxs-lookup"><span data-stu-id="f5dbb-148">Troubleshooting Concepts (Analysis Services - Data Mining)</span></span>](https://msdn.microsoft.com/library/cc645881.aspx)  
  
  
