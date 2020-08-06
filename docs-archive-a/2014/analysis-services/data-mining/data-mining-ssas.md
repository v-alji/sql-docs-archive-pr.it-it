---
title: Data mining (SSAS) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data mining [Analysis Services], about data mining
ms.assetid: b1c912da-72f6-4d96-89c8-55a2c4f19e88
author: minewiskan
ms.author: owend
ms.openlocfilehash: 7044ee397d457f7924d0db99dbec6659f969f104
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635885"
---
# <a name="data-mining-ssas"></a><span data-ttu-id="e2e83-102">Data mining (SSAS)</span><span class="sxs-lookup"><span data-stu-id="e2e83-102">Data Mining (SSAS)</span></span>
  <span data-ttu-id="e2e83-103">In [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] è disponibile una piattaforma integrata per le soluzioni in cui è incorporato il data mining.</span><span class="sxs-lookup"><span data-stu-id="e2e83-103">[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] provides an integrated platform for solutions that incorporate data mining.</span></span> <span data-ttu-id="e2e83-104">Per creare soluzioni di Business Intelligence con analisi predittiva è possibile utilizzare i dati relazionali o del cubo.</span><span class="sxs-lookup"><span data-stu-id="e2e83-104">You can use either relational or cube data to create business intelligence solutions with predictive analytics.</span></span>  
  
## <a name="benefits-of-data-mining"></a><span data-ttu-id="e2e83-105">Vantaggi del data mining</span><span class="sxs-lookup"><span data-stu-id="e2e83-105">Benefits of Data Mining</span></span>  
 <span data-ttu-id="e2e83-106">Nel data mining vengono utilizzati principi statistici analizzati in modo approfondito per individuare modelli nei dati, consentendo di prendere decisioni intelligenti sui problemi complessi.</span><span class="sxs-lookup"><span data-stu-id="e2e83-106">Data mining uses well-researched statistical principles to discover patterns in your data, helping you make intelligent decisions about complex problems.</span></span> <span data-ttu-id="e2e83-107">Applicando gli algoritmi di data mining di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] ai dati, è possibile prevedere tendenze, identificare modelli, creare regole e indicazioni, analizzare la sequenza di eventi in set di dati complessi e acquisire nuovi approfondimenti.</span><span class="sxs-lookup"><span data-stu-id="e2e83-107">By applying the data mining algorithms in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] to your data, you can forecast trends, identify patterns, create rules and recommendations, analyze the sequence of events in complex data sets, and gain new insights.</span></span>  
  
 <span data-ttu-id="e2e83-108">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]il data mining è efficace, accessibile e integrato con gli strumenti preferiti dagli utenti per l'analisi e la creazione di report.</span><span class="sxs-lookup"><span data-stu-id="e2e83-108">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], data mining is powerful, accessible, and integrated with the tools that many people prefer to use for analysis and reporting.</span></span> <span data-ttu-id="e2e83-109">Per ottenere un'utile panoramica generale sul data mining che si desidera avviare, vedere i collegamenti di questa sezione.</span><span class="sxs-lookup"><span data-stu-id="e2e83-109">See the links in this section to get the broad background about data mining that you need to get started.</span></span>  
  
## <a name="key-data-mining-features"></a><span data-ttu-id="e2e83-110">Caratteristiche principali del data mining</span><span class="sxs-lookup"><span data-stu-id="e2e83-110">Key Data Mining Features</span></span>  
 <span data-ttu-id="e2e83-111">In SQL Server sono disponibili le caratteristiche seguenti per il supporto di soluzioni di data mining integrate:</span><span class="sxs-lookup"><span data-stu-id="e2e83-111">SQL Server provides the following features in support of integrated data mining solutions:</span></span>  
  
-   <span data-ttu-id="e2e83-112">Più origini dati: non è necessario creare un data warehouse o un cubo OLAP per eseguire il data mining.</span><span class="sxs-lookup"><span data-stu-id="e2e83-112">Multiple data sources: You do not have to create a data warehouse or an OLAP cube to do data mining.</span></span> <span data-ttu-id="e2e83-113">È possibile utilizzare dati tabulari forniti da provider esterni o disponibili in fogli di calcolo o addirittura file di testo.</span><span class="sxs-lookup"><span data-stu-id="e2e83-113">You can use tabular data from external providers, spreadsheets, and even text files.</span></span> <span data-ttu-id="e2e83-114">È anche possibile eseguire il processo di data mining di cubi OLAP creati in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e2e83-114">You can also easily mine OLAP cubes created in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="e2e83-115">Tuttavia, non è possibile usare i dati di un database in memoria.</span><span class="sxs-lookup"><span data-stu-id="e2e83-115">However, you cannot use data from an in-memory database.</span></span>  
  
-   <span data-ttu-id="e2e83-116">Pulizia dati integrata, gestione dati ed ETL: in Data Quality Services sono disponibili strumenti avanzati per il profiling e la pulizia dei dati.</span><span class="sxs-lookup"><span data-stu-id="e2e83-116">Integrated data cleansing, data management, and ETL: Data Quality Services provides advanced tools for profiling and cleansing data.</span></span> <span data-ttu-id="e2e83-117">Integration Services può essere utilizzato per compilare processi ETL per la pulizia dei dati, nonché per la compilazione, l'elaborazione, il training e l'aggiornamento di modelli.</span><span class="sxs-lookup"><span data-stu-id="e2e83-117">Integration Services can be used to build ETL processes for cleaning data, and also for building, processing, training, and updating models.</span></span>  
  
-   <span data-ttu-id="e2e83-118">Più algoritmi personalizzabili: oltre a fornire algoritmi quali quelli di clustering, reti neurali e alberi delle decisioni, la piattaforma supporta lo sviluppo di algoritmi plug-in personalizzati.</span><span class="sxs-lookup"><span data-stu-id="e2e83-118">Multiple customizable algorithms: In addition to providing algorithms such as clustering, neural networks, and decisions trees, the platform supports development of your own custom plug-in algorithms.</span></span>  
  
-   <span data-ttu-id="e2e83-119">Infrastruttura di test del modello: testare i modelli e i set di dati utilizzando importanti strumenti statistici come la convalida incrociata, le matrici di classificazione, i grafici di accuratezza e a dispersione.</span><span class="sxs-lookup"><span data-stu-id="e2e83-119">Model testing infrastructure: Test your models and data sets using important statistical tools as cross-validation, classification matrices, lift charts, and scatter plots.</span></span> <span data-ttu-id="e2e83-120">Creare e gestire facilmente i set di testing e di training.</span><span class="sxs-lookup"><span data-stu-id="e2e83-120">Easily create and manage testing and training sets.</span></span>  
  
-   <span data-ttu-id="e2e83-121">Esecuzione di query e drill-through: creare query di stima, recuperare schemi e statistiche del modello ed eseguire il drill-through nei dati del case.</span><span class="sxs-lookup"><span data-stu-id="e2e83-121">Querying and drillthrough: Create prediction queries, retrieve model patterns and statistics, and drill through to case data.</span></span>  
  
-   <span data-ttu-id="e2e83-122">Strumenti client: oltre agli strumenti di sviluppo e progettazione forniti da SQL Server, è possibile utilizzare i componenti aggiuntivi Data mining per Excel per creare ed esplorare i modelli, nonché per eseguirvi query.</span><span class="sxs-lookup"><span data-stu-id="e2e83-122">Client tools: In addition to the development and design studios provided by SQL Server, you can use the Data Mining Add-ins for Excel to create, query, and browse models.</span></span> <span data-ttu-id="e2e83-123">In alternativa creare client personalizzati, inclusi i servizi Web.</span><span class="sxs-lookup"><span data-stu-id="e2e83-123">Or, create custom clients, including Web services.</span></span>  
  
-   <span data-ttu-id="e2e83-124">Supporto del linguaggio di scripting e API gestita: tutti gli oggetti di data mining sono completamente programmabili.</span><span class="sxs-lookup"><span data-stu-id="e2e83-124">Scripting language support and managed API: All data mining objects are fully programmable.</span></span> <span data-ttu-id="e2e83-125">La generazione di script è possibile tramite MDX, XMLA o le estensioni PowerShell per [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e2e83-125">Scripting is possible through MDX, XMLA, or the PowerShell extensions for [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="e2e83-126">Utilizzare il linguaggio DMX (Data Mining Extensions) per eseguire query e generare script velocemente.</span><span class="sxs-lookup"><span data-stu-id="e2e83-126">Use the Data Mining Extensions (DMX) language for fast querying and scripting.</span></span>  
  
-   <span data-ttu-id="e2e83-127">Sicurezza e distribuzione: tramite [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]viene fornita la sicurezza basata su ruoli, incluse autorizzazioni separate relative al drill-through per i dati del modello e della struttura.</span><span class="sxs-lookup"><span data-stu-id="e2e83-127">Security and deployment: Provides role-based security through [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], including separate permissions for drillthrough to model and structure data.</span></span> <span data-ttu-id="e2e83-128">Distribuzione semplice di modelli agli altri server, in modo che gli utenti possano accedere agli schemi o effettuare stime</span><span class="sxs-lookup"><span data-stu-id="e2e83-128">Easy deployment of models to other servers, so that users can access the patterns or perform predictions</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e2e83-129">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="e2e83-129">In This Section</span></span>  
 <span data-ttu-id="e2e83-130">Negli argomenti di questa sezione sono illustrate le caratteristiche principali di Data mining di SQL Server e le attività correlate.</span><span class="sxs-lookup"><span data-stu-id="e2e83-130">The topics in this section introduce the principal features of SQL Server Data Mining and related tasks.</span></span>  
  
-   [<span data-ttu-id="e2e83-131">Concetti relativi al data mining</span><span class="sxs-lookup"><span data-stu-id="e2e83-131">Data Mining Concepts</span></span>](data-mining-concepts.md)  
  
-   [<span data-ttu-id="e2e83-132">Algoritmi di data mining &#40;Analysis Services - Data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="e2e83-132">Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;</span></span>](data-mining-algorithms-analysis-services-data-mining.md)  
  
-   [<span data-ttu-id="e2e83-133">Strutture di data mining &#40;Analysis Services - Data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="e2e83-133">Mining Structures &#40;Analysis Services - Data Mining&#41;</span></span>](mining-structures-analysis-services-data-mining.md)  
  
-   [<span data-ttu-id="e2e83-134">Modelli di data mining &#40;Analysis Services - Data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="e2e83-134">Mining Models &#40;Analysis Services - Data Mining&#41;</span></span>](mining-models-analysis-services-data-mining.md)  
  
-   [<span data-ttu-id="e2e83-135">Test e convalida &#40;Data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="e2e83-135">Testing and Validation &#40;Data Mining&#41;</span></span>](testing-and-validation-data-mining.md)  
  
-   [<span data-ttu-id="e2e83-136">Query di data mining</span><span class="sxs-lookup"><span data-stu-id="e2e83-136">Data Mining Queries</span></span>](data-mining-queries.md)  
  
-   [<span data-ttu-id="e2e83-137">Soluzioni di data mining</span><span class="sxs-lookup"><span data-stu-id="e2e83-137">Data Mining Solutions</span></span>](data-mining-solutions.md)  
  
-   [<span data-ttu-id="e2e83-138">Strumenti di data mining</span><span class="sxs-lookup"><span data-stu-id="e2e83-138">Data Mining Tools</span></span>](data-mining-tools.md)  
  
-   [<span data-ttu-id="e2e83-139">Architettura di data mining</span><span class="sxs-lookup"><span data-stu-id="e2e83-139">Data Mining Architecture</span></span>](data-mining-architecture.md)  
  
-   [<span data-ttu-id="e2e83-140">Panoramica della sicurezza &#40;data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="e2e83-140">Security Overview &#40;Data Mining&#41;</span></span>](security-overview-data-mining.md)  
  
  
