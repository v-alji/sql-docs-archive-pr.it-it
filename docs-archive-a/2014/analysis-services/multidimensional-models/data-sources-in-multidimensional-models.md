---
title: Origini dati nei modelli multidimensionali | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- metadata [Analysis Services]
- Analysis Services objects, data sources
- storing data [Analysis Services], data sources
- data sources [Analysis Services], about data sources
- security [Analysis Services], data sources
- data sources [Analysis Services]
- storage [Analysis Services], data sources
ms.assetid: a16469d9-9d53-4e35-9982-fc06327a9d33
author: minewiskan
ms.author: owend
ms.openlocfilehash: 41386c1c7abb0324aa17df24b3c427ca8cbb5615
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636438"
---
# <a name="data-sources-in-multidimensional-models"></a><span data-ttu-id="f5d7c-102">Origini dati nei modelli multidimensionali</span><span class="sxs-lookup"><span data-stu-id="f5d7c-102">Data Sources in Multidimensional Models</span></span>
  <span data-ttu-id="f5d7c-103">Tutti i dati importati o caricati in un modello multidimensionale provengono da un'origine dati esterna.</span><span class="sxs-lookup"><span data-stu-id="f5d7c-103">All data that you import or load into a multidimensional model originates from an external data source.</span></span> <span data-ttu-id="f5d7c-104">In genere i dati di origine provengono da un data warehouse progettato per la creazione di report, ma potrebbero provenire da qualsiasi database relazionale a cui è stato effettuato l'accesso in modo diretto o indiretto tramite un intermediario, ad esempio un pacchetto [!INCLUDE[ssIS](../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f5d7c-104">Typically, source data is from a data warehouse designed for reporting purposes, but it could come from any relational database that is accessed directly or indirectly through an intermediary, such as an [!INCLUDE[ssIS](../../includes/ssis-md.md)] package.</span></span>  
  
 <span data-ttu-id="f5d7c-105">Un oggetto **origine dati** in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] consente di specificare una connessione diretta a un'origine dati esterna.</span><span class="sxs-lookup"><span data-stu-id="f5d7c-105">A **data source** object in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] specifies a direct connection to an external data source.</span></span> <span data-ttu-id="f5d7c-106">Oltre alla posizione fisica, un oggetto origine dati consente di specificare la stringa di connessione, il provider di dati, le credenziali e altre proprietà utilizzate per controllare il comportamento di connessione.</span><span class="sxs-lookup"><span data-stu-id="f5d7c-106">In addition to physical location, a data source object specifies the connection string, data provider, credentials, and other properties that control connection behavior.</span></span>  
  
 <span data-ttu-id="f5d7c-107">Le informazioni fornite dall'oggetto origine dati vengono utilizzate durante le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f5d7c-107">Information provided by the data source object is used during the following operations:</span></span>  
  
-   <span data-ttu-id="f5d7c-108">Ottenere informazioni sullo schema e altri metadati utilizzati per generare viste origine dati in un modello.</span><span class="sxs-lookup"><span data-stu-id="f5d7c-108">Get schema information and other metadata used to generate data source views into a model.</span></span>  
  
-   <span data-ttu-id="f5d7c-109">Eseguire una query e caricare i dati in un modello durante l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="f5d7c-109">Query or load data into a model during processing.</span></span>  
  
-   <span data-ttu-id="f5d7c-110">Eseguire query su modelli multidimensionali o di data mining in cui si utilizza la modalità di archiviazione ROLAP.</span><span class="sxs-lookup"><span data-stu-id="f5d7c-110">Run queries against multidimensional or data mining models that use ROLAP storage mode.</span></span>  
  
-   <span data-ttu-id="f5d7c-111">Leggere o scrivere in partizioni remote.</span><span class="sxs-lookup"><span data-stu-id="f5d7c-111">Read or write to remote partitions.</span></span>  
  
-   <span data-ttu-id="f5d7c-112">Connettersi a oggetti collegati ed eseguire la sincronizzazione da una destinazione a un'origine.</span><span class="sxs-lookup"><span data-stu-id="f5d7c-112">Connect to linked objects, as well as synchronize from target to source.</span></span>  
  
-   <span data-ttu-id="f5d7c-113">Eseguire operazioni di writeback per l'aggiornamento di dati della tabella dei fatti archiviati in un database relazionale.</span><span class="sxs-lookup"><span data-stu-id="f5d7c-113">Perform write back operations that update fact table data stored in a relational database.</span></span>  
  
 <span data-ttu-id="f5d7c-114">Quando si compila un modello multidimensionale a partire dal basso, si inizia creando l'oggetto origine dati che viene quindi usato per generare l'oggetto successivo, una **vista origine dati**.</span><span class="sxs-lookup"><span data-stu-id="f5d7c-114">When building a multidimensional model from the bottom up, you start by creating the data source object, and then use it to generate the next object, a **data source view**.</span></span> <span data-ttu-id="f5d7c-115">Una vista origine dati rappresenta il livello di astrazione dati nel modello.</span><span class="sxs-lookup"><span data-stu-id="f5d7c-115">A data source view is the data abstraction layer in the model.</span></span> <span data-ttu-id="f5d7c-116">Viene in genere creata dopo l'oggetto origine dati, utilizzando come base quello del database di origine.</span><span class="sxs-lookup"><span data-stu-id="f5d7c-116">It is typically created after the data source object, using the schema of the source database as the basis.</span></span> <span data-ttu-id="f5d7c-117">Tuttavia, si possono scegliere altri modi per compilare un modello, tra cui iniziare con cubi e dimensioni per poi generare lo schema che meglio supporta la progettazione.</span><span class="sxs-lookup"><span data-stu-id="f5d7c-117">However, you can choose other ways to build a model, including starting with cubes and dimensions, and generating the schema that best supports your design.</span></span>  
  
 <span data-ttu-id="f5d7c-118">Indipendentemente dalla modalità di compilazione, ogni modello richiede almeno un oggetto origine dati con cui è possibile specificare una connessione all'origine dati.</span><span class="sxs-lookup"><span data-stu-id="f5d7c-118">Regardless of how you build it, each model requires at least one data source object that specifies a connection to source data.</span></span> <span data-ttu-id="f5d7c-119">È possibile creare più oggetti origine dati in un solo modello per utilizzare dati provenienti da origini diverse o diverse proprietà di connessione per oggetti specifici.</span><span class="sxs-lookup"><span data-stu-id="f5d7c-119">You can create multiple data source objects in a single model to use data from different sources or vary connection properties for specific objects.</span></span>  
  
 <span data-ttu-id="f5d7c-120">Gli oggetti origine dati possono essere gestiti in modo indipendente da altri oggetti nel modello.</span><span class="sxs-lookup"><span data-stu-id="f5d7c-120">Data source objects can be managed independently of other objects in your model.</span></span> <span data-ttu-id="f5d7c-121">Dopo aver creato un'origine dati, è possibile modificarne le proprietà in seguito, quindi pre-elaborare il modello per assicurarsi che i dati vengano correttamente recuperati.</span><span class="sxs-lookup"><span data-stu-id="f5d7c-121">After you create a data source, you can change its properties later, and then preprocess the model to ensure the data is retrieved correctly.</span></span>  
  
## <a name="related-topics-and-tasks"></a><span data-ttu-id="f5d7c-122">Attività e argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="f5d7c-122">Related Topics and Tasks</span></span>  
  
|<span data-ttu-id="f5d7c-123">Argomento</span><span class="sxs-lookup"><span data-stu-id="f5d7c-123">Topic</span></span>|<span data-ttu-id="f5d7c-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f5d7c-124">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="f5d7c-125">Origini dati supportate &#40;SSAS multidimensionale&#41;</span><span class="sxs-lookup"><span data-stu-id="f5d7c-125">Data Sources Supported &#40;SSAS Multidimensional&#41;</span></span>](supported-data-sources-ssas-multidimensional.md)|<span data-ttu-id="f5d7c-126">Vengono descritti i tipi di origini dati che possono essere utilizzati in un modello multidimensionale.</span><span class="sxs-lookup"><span data-stu-id="f5d7c-126">Describes the types of data sources that can be used in a multidimensional model.</span></span>|  
|[<span data-ttu-id="f5d7c-127">Creare un'origine dati &#40;SSAS multidimensionale&#41;</span><span class="sxs-lookup"><span data-stu-id="f5d7c-127">Create a Data Source &#40;SSAS Multidimensional&#41;</span></span>](create-a-data-source-ssas-multidimensional.md)|<span data-ttu-id="f5d7c-128">Viene illustrato come aggiungere un oggetto origine dati a un modello multidimensionale.</span><span class="sxs-lookup"><span data-stu-id="f5d7c-128">Explains how to add a data source object to a multidimensional model.</span></span>|  
|[<span data-ttu-id="f5d7c-129">Eliminare un'origine dati in Esplora soluzioni &#40;SSAS multidimensionale&#41;</span><span class="sxs-lookup"><span data-stu-id="f5d7c-129">Delete a Data Source in Solution Explorer &#40;SSAS Multidimensional&#41;</span></span>](delete-a-data-source-in-solution-explorer-ssas-multidimensional.md)|<span data-ttu-id="f5d7c-130">Utilizzare questa procedura per eliminare un oggetto origine dati da un modello multidimensionale.</span><span class="sxs-lookup"><span data-stu-id="f5d7c-130">Use this procedure to delete a data source object from a multidimensional model.</span></span>|  
|[<span data-ttu-id="f5d7c-131">Impostare le proprietà dell'origine dati &#40;SSAS multidimensionale&#41;</span><span class="sxs-lookup"><span data-stu-id="f5d7c-131">Set Data Source Properties &#40;SSAS Multidimensional&#41;</span></span>](set-data-source-properties-ssas-multidimensional.md)|<span data-ttu-id="f5d7c-132">Viene descritta ogni proprietà e fornite informazioni su come impostarle.</span><span class="sxs-lookup"><span data-stu-id="f5d7c-132">Describes each property and explains how to set each one.</span></span>|  
|[<span data-ttu-id="f5d7c-133">Impostare opzioni di rappresentazione &#40;SSAS multidimensionale&#41;</span><span class="sxs-lookup"><span data-stu-id="f5d7c-133">Set Impersonation Options &#40;SSAS - Multidimensional&#41;</span></span>](set-impersonation-options-ssas-multidimensional.md)|<span data-ttu-id="f5d7c-134">Viene descritto come configurare le opzioni nella finestra di dialogo Impostazioni di rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="f5d7c-134">Explains how to configure options in the Impersonation Information dialog box.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f5d7c-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f5d7c-135">See Also</span></span>  
 <span data-ttu-id="f5d7c-136">[Oggetti di database &#40;Analysis Services-Dati multidimensionali&#41;](olap-logical/database-objects-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="f5d7c-136">[Database Objects &#40;Analysis Services - Multidimensional Data&#41;](olap-logical/database-objects-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="f5d7c-137">[Architettura logica &#40;Analysis Services-Dati multidimensionali&#41;](olap-logical/understanding-microsoft-olap-logical-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="f5d7c-137">[Logical Architecture &#40;Analysis Services - Multidimensional Data&#41;](olap-logical/understanding-microsoft-olap-logical-architecture.md) </span></span>  
 <span data-ttu-id="f5d7c-138">[Viste origine dati in modelli multidimensionali](data-source-views-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="f5d7c-138">[Data Source Views in Multidimensional Models](data-source-views-in-multidimensional-models.md) </span></span>  
 [<span data-ttu-id="f5d7c-139">Origini dati e associazioni &#40;SSAS multidimensionale&#41;</span><span class="sxs-lookup"><span data-stu-id="f5d7c-139">Data Sources and Bindings &#40;SSAS Multidimensional&#41;</span></span>](data-sources-and-bindings-ssas-multidimensional.md)  
  
  
