---
title: Distribuzione di soluzioni di data mining | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining models [Analysis Services], deploying
- deploying [Analysis Services], production environments
- deploying [Analysis Services - data mining]
- solutions [Analysis Services], deploying
- models [Analysis Services], data mining
ms.assetid: d83effc7-437d-42e9-8ac3-b65f79e27043
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5764be2f7530add2fa4cb028b288be69598bb95c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636475"
---
# <a name="deployment-of-data-mining-solutions"></a><span data-ttu-id="e2ee8-102">Distribuzione di soluzioni di data mining</span><span class="sxs-lookup"><span data-stu-id="e2ee8-102">Deployment of Data Mining Solutions</span></span>
  <span data-ttu-id="e2ee8-103">L'ultimo passaggio del processo di data mining consiste nel distribuire i modelli in un ambiente di produzione.</span><span class="sxs-lookup"><span data-stu-id="e2ee8-103">The last step in the data mining process is to deploy the models to a production environment.</span></span> <span data-ttu-id="e2ee8-104">La distribuzione è importante perché rende disponibili i modelli agli utenti in modo da poter eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="e2ee8-104">Deployment is important because it makes the models available to users so that you can perform any of the following tasks:</span></span>  
  
-   <span data-ttu-id="e2ee8-105">Utilizzare i modelli per creare stime e prendere decisioni aziendali.</span><span class="sxs-lookup"><span data-stu-id="e2ee8-105">Use the models to create predictions and make business decisions.</span></span> <span data-ttu-id="e2ee8-106">Per informazioni sugli strumenti che è possibile utilizzare per creare query, vedere [interfacce di query di data mining](data-mining-query-tools.md).</span><span class="sxs-lookup"><span data-stu-id="e2ee8-106">For information about the tools you can use to create queries, see [Data Mining Query Interfaces](data-mining-query-tools.md).</span></span>  
  
-   <span data-ttu-id="e2ee8-107">Incorporare la funzionalità di data mining direttamente in un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e2ee8-107">Embed data mining functionality directly into an application.</span></span> <span data-ttu-id="e2ee8-108">È possibile includere la libreria AMO (Analysis Management Objects) o un assembly contenente un set di oggetti utilizzabili dall'applicazione per creare, modificare, elaborare ed eliminare strutture e modelli di data mining.</span><span class="sxs-lookup"><span data-stu-id="e2ee8-108">You can include Analysis Management Objects (AMO) or an assembly that contains a set of objects that your application can use to create, alter, process, and delete mining structures and mining models.</span></span>  
  
-   <span data-ttu-id="e2ee8-109">Creare report che consentano agli utenti di richiedere stime, visualizzare tendenze o confrontare modelli.</span><span class="sxs-lookup"><span data-stu-id="e2ee8-109">Create reports that let users request predictions, view trends, or compare models.</span></span>  
  
 <span data-ttu-id="e2ee8-110">In questa sezione vengono fornite informazioni dettagliate sulle opzioni di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="e2ee8-110">This section provides detailed information about deployment options.</span></span>  
  
 [<span data-ttu-id="e2ee8-111">Requisiti per la distribuzione delle soluzioni di data mining</span><span class="sxs-lookup"><span data-stu-id="e2ee8-111">Requirements for Deployment of Data Mining Solutions</span></span>](#bkmk_Reqs)  
  
 [<span data-ttu-id="e2ee8-112">Distribuzione di una soluzione relazionale</span><span class="sxs-lookup"><span data-stu-id="e2ee8-112">Deploying a Relational Solution</span></span>](#bkmk_RelationalSltn)  
  
 [<span data-ttu-id="e2ee8-113">Distribuzione di una soluzione multidimensionale</span><span class="sxs-lookup"><span data-stu-id="e2ee8-113">Deploying a Multidimensional Solution</span></span>](#bkmk_MDSltn)  
  
 [<span data-ttu-id="e2ee8-114">Risorse correlate</span><span class="sxs-lookup"><span data-stu-id="e2ee8-114">Related Resources</span></span>](#bkmk_Resources)  
  
## <a name="in-this-section"></a><span data-ttu-id="e2ee8-115">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="e2ee8-115">In This Section</span></span>  
 [<span data-ttu-id="e2ee8-116">Distribuire una soluzione di data mining in versioni precedenti di SQL Server</span><span class="sxs-lookup"><span data-stu-id="e2ee8-116">Deploy a Data Mining Solution to Previous Versions of SQL Server</span></span>](deploy-a-data-mining-solution-to-previous-versions-of-sql-server.md)  
  
 [<span data-ttu-id="e2ee8-117">Esportare e importare gli oggetti di data mining</span><span class="sxs-lookup"><span data-stu-id="e2ee8-117">Export and Import Data Mining Objects</span></span>](export-and-import-data-mining-objects.md)  
  
##  <a name="requirements-for-deployment-of-data-mining-solutions"></a><a name="bkmk_Reqs"></a><span data-ttu-id="e2ee8-118">Requisiti per la distribuzione di soluzioni di data mining</span><span class="sxs-lookup"><span data-stu-id="e2ee8-118">Requirements for Deployment of Data Mining Solutions</span></span>  
 <span data-ttu-id="e2ee8-119">L'istanza di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] a cui si distribuisce la soluzione deve essere in esecuzione in una modalità che supporta oggetti multidimensionali e oggetti di data mining; non è infatti possibile distribuire oggetti di data mining a un'istanza che ospita modelli tabulari o dati PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="e2ee8-119">The instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] to which you deploy the solution must be running in a mode that supports multidimensional objects and data mining objects; that is, you cannot deploy data mining objects to an instance that hosts tabular models or PowerPivot data.</span></span>  
  
 <span data-ttu-id="e2ee8-120">Pertanto, quando si crea una soluzione di data mining in Visual Studio, assicurarsi di usare il modello **Progetto multidimensionale e di data mining di Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="e2ee8-120">Therefore, when you create a data mining solution in Visual Studio, be sure to use the template, **Analysis Services Multidimensional and Data Mining Project**.</span></span>  
  
 <span data-ttu-id="e2ee8-121">Quando si distribuisce la soluzione, gli oggetti utilizzati per il data mining vengono creati nell'istanza di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] specificata, in un database con lo stesso nome del file della soluzione.</span><span class="sxs-lookup"><span data-stu-id="e2ee8-121">When you deploy the solution, the objects used for data mining are created in the specified [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance, in a database with the same name as the solution file.</span></span>  
  
###  <a name="deploying-a-relational-solution"></a><a name="bkmk_RelationalSltn"></a><span data-ttu-id="e2ee8-122">Distribuzione di una soluzione relazionale</span><span class="sxs-lookup"><span data-stu-id="e2ee8-122">Deploying a Relational Solution</span></span>  
 <span data-ttu-id="e2ee8-123">Quando si distribuisce una soluzione di data mining relazionale, gli oggetti di data mining obbligatori vengono creati all'interno di un nuovo database di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] e gli oggetti vengono elaborati per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="e2ee8-123">When you deploy a relational data mining solution, the required data mining objects are created within a new [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database, and the objects are processed by default.</span></span> <span data-ttu-id="e2ee8-124">Tramite la proprietà di configurazione **Opzione di elaborazione**è possibile modificare le opzioni di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="e2ee8-124">You can change processing options by using the configuration property, **Processing Option**.</span></span> <span data-ttu-id="e2ee8-125">Per altre informazioni, vedere [Configurare proprietà di progetti di Analysis Services &#40;SSDT&#41;](../multidimensional-models/configure-analysis-services-project-properties-ssdt.md).</span><span class="sxs-lookup"><span data-stu-id="e2ee8-125">For more information, see [Configure Analysis Services Project Properties &#40;SSDT&#41;](../multidimensional-models/configure-analysis-services-project-properties-ssdt.md).</span></span>  
  
 <span data-ttu-id="e2ee8-126">Per impostazione predefinita, solo le modifiche incrementali vengono distribuite ogni volta.</span><span class="sxs-lookup"><span data-stu-id="e2ee8-126">By default, only incremental changes are deployed each time.</span></span> <span data-ttu-id="e2ee8-127">In altre parole, è possibile modificare un modello di data mining e alla successiva distribuzione del progetto solo quel modello di data mining verrà aggiornato.</span><span class="sxs-lookup"><span data-stu-id="e2ee8-127">In other words, you can modify a mining model, and when you re-deploy the project, only that mining model would be updated.</span></span> <span data-ttu-id="e2ee8-128">Tuttavia, se più client modificano il database di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , è possibile che si verifichino degli errori.</span><span class="sxs-lookup"><span data-stu-id="e2ee8-128">However, if you have multiple clients editing the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database, this can lead to errors.</span></span> <span data-ttu-id="e2ee8-129">Per modificare la modalità di distribuzione predefinita in modo che l'intero database venga aggiornato alla distribuzione della soluzione, modificare la proprietà **Modalità distribuzione**</span><span class="sxs-lookup"><span data-stu-id="e2ee8-129">To change the default deployment mode so that the entire database is refreshed when you deploy the solution, change the **Deployment Mode** property</span></span>  
  
 <span data-ttu-id="e2ee8-130">In una soluzione di data mining relazionale, gli unici oggetti che devono essere distribuiti sono la definizione dell'origine dati, eventuali viste origine dati utilizzate, le strutture di data mining e tutti i modelli di data mining dipendenti.</span><span class="sxs-lookup"><span data-stu-id="e2ee8-130">In a relational data mining solution, the only objects that must be deployed are the data source definition, any data source views that were used, the mining structures, and all dependent mining models.</span></span>  
  
###  <a name="deploying-a-multidimensional-solution"></a><a name="bkmk_MDSltn"></a><span data-ttu-id="e2ee8-131">Distribuzione di una soluzione multidimensionale</span><span class="sxs-lookup"><span data-stu-id="e2ee8-131">Deploying a Multidimensional Solution</span></span>  
 <span data-ttu-id="e2ee8-132">Quando si distribuisce una soluzione di data mining multidimensionale, questa soluzione crea gli oggetti di data mining all'interno dello stesso database del cubo di origine.</span><span class="sxs-lookup"><span data-stu-id="e2ee8-132">When you deploy a multidimensional data mining solution, this solution creates your data mining objects within the same database as the source cube.</span></span>  
  
 <span data-ttu-id="e2ee8-133">Quando si elabora un modello o una struttura di data mining, è necessario elaborare anche il cubo di origine.</span><span class="sxs-lookup"><span data-stu-id="e2ee8-133">When you process the mining structure or mining model, you must process the source cube as well.</span></span> <span data-ttu-id="e2ee8-134">Per questo motivo, la distribuzione di una soluzione che utilizza modelli di data mining OLAP può prendere più tempo rispetto alle soluzioni di data mining relazionali.</span><span class="sxs-lookup"><span data-stu-id="e2ee8-134">For this reason, deploying a solution that uses OLAP mining models can take longer than relational data mining solutions.</span></span>  
  
 <span data-ttu-id="e2ee8-135">In genere, gli oggetti di data mining utilizzano anche le stesse origini dati e le stesse viste origine dati utilizzate per il cubo.</span><span class="sxs-lookup"><span data-stu-id="e2ee8-135">Typically data mining objects also use the same data sources and data source views that are used for the cube.</span></span> <span data-ttu-id="e2ee8-136">Tuttavia, è possibile aggiungere origini dati e viste origine dati destinate in modo specifico al data mining.</span><span class="sxs-lookup"><span data-stu-id="e2ee8-136">However, you can add data sources and data source views that are targeted specifically to data mining.</span></span> <span data-ttu-id="e2ee8-137">Ad esempio, un cubo in genere non contiene dati su clienti potenziali o dati esterni non utilizzati negli oggetti multidimensionali.</span><span class="sxs-lookup"><span data-stu-id="e2ee8-137">For example, typically a cube would not contain data about prospective clients, or external data not used in the multidimensional objects.</span></span>  
  
##  <a name="related-resources"></a><a name="bkmk_Resources"></a><span data-ttu-id="e2ee8-138">Risorse correlate</span><span class="sxs-lookup"><span data-stu-id="e2ee8-138">Related Resources</span></span>  
 [<span data-ttu-id="e2ee8-139">Spostamento di oggetti di data mining</span><span class="sxs-lookup"><span data-stu-id="e2ee8-139">Moving Data Mining Objects</span></span>](moving-data-mining-objects.md)  
  
 <span data-ttu-id="e2ee8-140">Se il modello è basato unicamente su dati relazionali, l'esportazione e l'importazione di oggetti tramite DMX è il modo più semplice per spostare i modelli.</span><span class="sxs-lookup"><span data-stu-id="e2ee8-140">If your model is based on relational data only, exporting and importing objects using DMX is the easiest way to move models.</span></span>  
  
 [<span data-ttu-id="e2ee8-141">Spostare un database di Analysis Services</span><span class="sxs-lookup"><span data-stu-id="e2ee8-141">Move an Analysis Services Database</span></span>](../multidimensional-models/move-an-analysis-services-database.md)  
  
 <span data-ttu-id="e2ee8-142">Quando i modelli utilizzano un cubo come origine dati, fare riferimento a questo argomento per ottenere ulteriori informazioni sullo spostamento dei modelli e dei dati del cubo di supporto.</span><span class="sxs-lookup"><span data-stu-id="e2ee8-142">When models use a cube as a data source, refer to this topic for more information about how to move models and their supporting cube data.</span></span>  
  
 [<span data-ttu-id="e2ee8-143">Distribuire progetti di Analysis Services &#40;SSDT&#41;</span><span class="sxs-lookup"><span data-stu-id="e2ee8-143">Deploy Analysis Services Projects &#40;SSDT&#41;</span></span>](../multidimensional-models/deploy-analysis-services-projects-ssdt.md)  
  
 <span data-ttu-id="e2ee8-144">Vengono fornite informazioni generali sulla distribuzione di progetti di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] e vengono descritte le proprietà che è possibile impostare come parte della configurazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="e2ee8-144">Provides general information about deployment of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] projects, and describes the properties that you can set as part of the project configuration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2ee8-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e2ee8-145">See Also</span></span>  
 <span data-ttu-id="e2ee8-146">[Elaborazione di oggetti del modello multidimensionale](../multidimensional-models/processing-a-multidimensional-model-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="e2ee8-146">[Multidimensional Model Object Processing](../multidimensional-models/processing-a-multidimensional-model-analysis-services.md) </span></span>  
 <span data-ttu-id="e2ee8-147">[Interfacce di query di data mining](data-mining-query-tools.md) </span><span class="sxs-lookup"><span data-stu-id="e2ee8-147">[Data Mining Query Interfaces](data-mining-query-tools.md) </span></span>  
 [<span data-ttu-id="e2ee8-148">Requisiti e considerazioni sull'elaborazione &#40;data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="e2ee8-148">Processing Requirements and Considerations &#40;Data Mining&#41;</span></span>](processing-requirements-and-considerations-data-mining.md)  
  
  
