---
title: Creare una query DMX in SQL Server Management Studio | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- templates [Analysis Services], queries
- SQL Server Management Studio [Analysis Services], DMX queries
- predictions [Analysis Services], DMX prediction queries
- predictions [DMX]
- prediction queries [DMX]
- queries [DMX], prediction queries
- mining models [Analysis Services], DMX
ms.assetid: 568ce40a-1f53-47eb-8c79-14347cdfde83
author: minewiskan
ms.author: owend
ms.openlocfilehash: d20fc7a618f4977058203d8f35d235b543609dd9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630163"
---
# <a name="create-a-dmx-query-in-sql-server-management-studio"></a><span data-ttu-id="d2248-102">Creare una query DMX in SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d2248-102">Create a DMX Query in SQL Server Management Studio</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="d2248-103">offre un set di funzionalità che consentono di creare query di stima, query sul contenuto e query di definizione dei dati su modelli e strutture di data mining.</span><span class="sxs-lookup"><span data-stu-id="d2248-103">provides a set of features to help you create prediction queries, content queries, and data definition queries against mining models and mining structures.</span></span>  
  
-   <span data-ttu-id="d2248-104">Un generatore di query di stima grafico è disponibile sia in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] che in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]per semplificare il processo di scrittura delle query di stima e il mapping dei set di dati a un modello.</span><span class="sxs-lookup"><span data-stu-id="d2248-104">The graphical Prediction Query Builder is available in both [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] and [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], to simplify the process of writing prediction queries and mapping data sets to a model.</span></span>  
  
-   <span data-ttu-id="d2248-105">I modelli di query forniti in Esplora modelli avviano rapidamente la creazione di molti tipi di query DMX, tra cui molti tipi di query di stima.</span><span class="sxs-lookup"><span data-stu-id="d2248-105">The query templates provided in the Template Explorer jump-start the creation of many kinds of DMX queries, including many types of prediction queries.</span></span> <span data-ttu-id="d2248-106">Vengono forniti modelli per query contenuto, query che utilizzano set di dati nidificati, query che restituiscono case dalla struttura di data mining e anche query di definizione dei dati.</span><span class="sxs-lookup"><span data-stu-id="d2248-106">Templates are provided for content queries, queries used nested data sets, queries that return cases from the mining structure, and even data definition queries.</span></span>  
  
-   <span data-ttu-id="d2248-107">In Visualizzatore metadati nei riquadri delle query MDX e DMX è presente un elenco di modelli e strutture disponibili che è possibile trascinare nel generatore di query, nonché un elenco di funzioni DMX.</span><span class="sxs-lookup"><span data-stu-id="d2248-107">The Metadata Explorer in the MDX and DMX query panes provides a list of available models and structures that you can drag and drop into the query builder, as well as a list of DMX functions.</span></span> <span data-ttu-id="d2248-108">Questa funzionalità consente di ottenere con facilità i nomi degli oggetti corretti, senza doverli digitare.</span><span class="sxs-lookup"><span data-stu-id="d2248-108">This feature makes it easy to get object names right, without typing.</span></span>  
  
 <span data-ttu-id="d2248-109">In questo argomento viene illustrato come compilare una query DMX tramite Visualizzatore metadati e l'editor di query DMX.</span><span class="sxs-lookup"><span data-stu-id="d2248-109">This topic describes how to build a DMX query by using the Metadata Explorer and the DMX query editor.</span></span>  
  
##  <a name="dmx-query-templates"></a><a name="BKMK_Templates"></a><span data-ttu-id="d2248-110">Modelli di query DMX</span><span class="sxs-lookup"><span data-stu-id="d2248-110">DMX Query Templates</span></span>  
 <span data-ttu-id="d2248-111">I modelli per la creazione delle query DMX di base sono disponibili in Esplora modelli.</span><span class="sxs-lookup"><span data-stu-id="d2248-111">Templates for creating basic DMX queries are available in Template Explorer.</span></span> <span data-ttu-id="d2248-112">La cartella **DMX** contiene modelli di data mining, divisi nelle categorie seguenti:</span><span class="sxs-lookup"><span data-stu-id="d2248-112">The **DMX** folder contains data mining templates, which are divided into these categories:</span></span>  
  
-   <span data-ttu-id="d2248-113">**Contenuto del modello**</span><span class="sxs-lookup"><span data-stu-id="d2248-113">**Model Content**</span></span>  
  
-   <span data-ttu-id="d2248-114">**Gestione modelli**</span><span class="sxs-lookup"><span data-stu-id="d2248-114">**Model Management**</span></span>  
  
-   <span data-ttu-id="d2248-115">**Query di stima**</span><span class="sxs-lookup"><span data-stu-id="d2248-115">**Prediction Queries**</span></span>  
  
-   <span data-ttu-id="d2248-116">**Contenuto della struttura**</span><span class="sxs-lookup"><span data-stu-id="d2248-116">**Structure Content**</span></span>  
  
 <span data-ttu-id="d2248-117">È inoltre possibile creare modelli personalizzati, per query o comandi eseguiti frequentemente.</span><span class="sxs-lookup"><span data-stu-id="d2248-117">You can also create custom templates, for queries or commands that you run frequently.</span></span>  
  
## <a name="xmla-query-templates"></a><span data-ttu-id="d2248-118">Modelli di query XMLA</span><span class="sxs-lookup"><span data-stu-id="d2248-118">XMLA Query Templates</span></span>  
 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="d2248-119">include anche modelli per le query XMLA.</span><span class="sxs-lookup"><span data-stu-id="d2248-119">also provides templates for XMLA queries.</span></span>  
  
 <span data-ttu-id="d2248-120">I tipi di query che è possibile eseguire tramite XMLA e DMX sono parzialmente sovrapposti.</span><span class="sxs-lookup"><span data-stu-id="d2248-120">There is some overlap between the types of queries that you can perform by using XMLA and DMX.</span></span> <span data-ttu-id="d2248-121">Ad esempio, è possibile creare alcune query contenuto del modello tramite DMX o i set di righe dello schema di data mining, ma i set di righe dello schema talvolta contengono informazioni non esposte nelle query contenuto DMX.</span><span class="sxs-lookup"><span data-stu-id="d2248-121">For example, you can create some model content queries by using either DMX or the data mining schema rowsets, but the schema rowsets sometimes contain information that is not exposed in DMX content queries.</span></span>  
  
 <span data-ttu-id="d2248-122">Sono inoltre presenti alcune differenze fondamentali nella modalità di gestione delle operazioni in DMX e in XMLA.</span><span class="sxs-lookup"><span data-stu-id="d2248-122">There are also some key differences in the way that operations are handled in DMX and in XMLA.</span></span> <span data-ttu-id="d2248-123">Ad esempio, è possibile usare XMLA per eseguire operazioni amministrative, come il backup di un intero database di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], ma per eseguire il backup di un solo modello di data mining in DMX è disponibile un comando semplice, [EXPORT &#40;DMX&#41;](/sql/dmx/export-dmx), più indicato allo scopo.</span><span class="sxs-lookup"><span data-stu-id="d2248-123">For example, you can use XMLA to perform administrative operations such as backup of an entire [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database, but if you want to back up a single mining model, DMX provides a simple command, [EXPORT &#40;DMX&#41;](/sql/dmx/export-dmx), that is better suited to that purpose.</span></span>  
  
##  <a name="build-and-run-a-dmx-query"></a><a name="BKMK_Building_Queries"></a><span data-ttu-id="d2248-124">Compilare ed eseguire una query DMX</span><span class="sxs-lookup"><span data-stu-id="d2248-124">Build and Run a DMX Query</span></span>  
  
#### <a name="open-a-new-dmx-query-window"></a><span data-ttu-id="d2248-125">Aprire una nuova finestra Query DMX</span><span class="sxs-lookup"><span data-stu-id="d2248-125">Open a new DMX Query window</span></span>  
  
1.  <span data-ttu-id="d2248-126">Fare clic su **Nuova query** in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]e quindi selezionare **Nuova query DMX di Analysis Server**.</span><span class="sxs-lookup"><span data-stu-id="d2248-126">Click **New Query** in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], and then select **New Analysis Server DMX Query**.</span></span>  
  
2.  <span data-ttu-id="d2248-127">Quando viene visualizzata la finestra di dialogo **Connetti al server** , selezionare l'istanza di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] contenente i modelli di data mining da usare.</span><span class="sxs-lookup"><span data-stu-id="d2248-127">When the **Connect to Server** dialog box appears, select the instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] that contains the mining models you want to work with.</span></span>  
  
#### <a name="open-template-explorer"></a><span data-ttu-id="d2248-128">Aprire Esplora modelli</span><span class="sxs-lookup"><span data-stu-id="d2248-128">Open Template Explorer</span></span>  
  
1.  <span data-ttu-id="d2248-129">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]scegliere **Esplora modelli** dal menu **Visualizza**.</span><span class="sxs-lookup"><span data-stu-id="d2248-129">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], on the **View** menu, select **Template Explorer**.</span></span>  
  
2.  <span data-ttu-id="d2248-130">Fare clic su **Analysis Server** per ottenere una visualizzazione albero dei modelli applicabili a [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d2248-130">Click **Analysis Server** to see a tree view of the templates that apply to [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>  
  
#### <a name="apply-a-template-to-build-a-query"></a><span data-ttu-id="d2248-131">Applicare un modello per compilare una query</span><span class="sxs-lookup"><span data-stu-id="d2248-131">Apply a template to build a query</span></span>  
  
-   <span data-ttu-id="d2248-132">Fare clic con il pulsante destro del mouse sul tipo di query adatto e scegliere **Apri**.</span><span class="sxs-lookup"><span data-stu-id="d2248-132">Right-click the appropriate query type and select **Open**.</span></span>  
  
-   <span data-ttu-id="d2248-133">In alternativa, trascinare il modello nell'editor di query.</span><span class="sxs-lookup"><span data-stu-id="d2248-133">Or, drag the template into the query editor.</span></span>  
  
-   <span data-ttu-id="d2248-134">È anche possibile compilare i parametri per la query scegliendo l'opzione **Specifica valori per parametri**dal menu **Query** .</span><span class="sxs-lookup"><span data-stu-id="d2248-134">You can also fill in the parameters for the query by using the option, **Specify Values for Parameters**, from the **Query** menu.</span></span>  
  
 <span data-ttu-id="d2248-135">Per esempi relativi alla creazione di tipi specifici di query dai modelli, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="d2248-135">For examples of how to create specific types of queries from templates, see the following topics:</span></span>  
  
 [<span data-ttu-id="d2248-136">Creare una query di stima singleton da un modello</span><span class="sxs-lookup"><span data-stu-id="d2248-136">Create a Singleton Prediction Query from a Template</span></span>](create-a-singleton-prediction-query-from-a-template.md)  
  
 [<span data-ttu-id="d2248-137">Creare una query sul contenuto di un modello di data mining</span><span class="sxs-lookup"><span data-stu-id="d2248-137">Create a Content Query on a Mining Model</span></span>](create-a-content-query-on-a-mining-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="d2248-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d2248-138">See Also</span></span>  
 <span data-ttu-id="d2248-139">[Interfacce di query di data mining](data-mining-query-tools.md) </span><span class="sxs-lookup"><span data-stu-id="d2248-139">[Data Mining Query Interfaces](data-mining-query-tools.md) </span></span>  
 [<span data-ttu-id="d2248-140">Guida di riferimento a DMX &#40;Data Mining Extensions&#41;</span><span class="sxs-lookup"><span data-stu-id="d2248-140">Data Mining Extensions &#40;DMX&#41; Reference</span></span>](/sql/dmx/data-mining-extensions-dmx-reference)  
  
  
