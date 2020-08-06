---
title: Programmazione di data mining | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- data mining [Analysis Services], developer's guide
ms.assetid: 9fd77b16-0b89-44ce-bcf1-7c04b62499da
author: minewiskan
ms.author: owend
ms.openlocfilehash: fd4bd48b5914d5fda89f94c0a959e670ffec3321
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712611"
---
# <a name="data-mining-programming"></a><span data-ttu-id="6058e-102">Programmazione di data mining</span><span class="sxs-lookup"><span data-stu-id="6058e-102">Data Mining Programming</span></span>
  <span data-ttu-id="6058e-103">Se gli strumenti e i visualizzatori predefiniti disponibili in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] non soddisfano i propri requisiti, è possibile estendere le funzionalità di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] mediante la codifica di estensioni personalizzate.</span><span class="sxs-lookup"><span data-stu-id="6058e-103">If you find that the built-in tools and viewers in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] do not meet your requirements, you can extend the power of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] by coding your own extensions.</span></span> <span data-ttu-id="6058e-104">Questo approccio rende disponibili due opzioni:</span><span class="sxs-lookup"><span data-stu-id="6058e-104">In this approach, you have two options:</span></span>  
  
-   <span data-ttu-id="6058e-105">**XMLA**</span><span class="sxs-lookup"><span data-stu-id="6058e-105">**XMLA**</span></span>  
  
     [!INCLUDE[msCoName](../../includes/msconame-md.md)]<span data-ttu-id="6058e-106">[!INCLUDE[ssASCurrent](../../includes/ssascurrent-md.md)]supporta XML for Analysis (XMLA) come protocollo per la comunicazione con le applicazioni client.</span><span class="sxs-lookup"><span data-stu-id="6058e-106">[!INCLUDE[ssASCurrent](../../includes/ssascurrent-md.md)] supports XML for Analysis (XMLA) as a protocol for communication with client applications.</span></span> <span data-ttu-id="6058e-107">[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] supporta comandi aggiuntivi che estendono la specifica XML for Analysis.</span><span class="sxs-lookup"><span data-stu-id="6058e-107">Additional commands are supported by [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] that extend the XML for Analysis specification.</span></span>  
  
     <span data-ttu-id="6058e-108">Poiché [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] utilizza XMLA per la definizione dei dati, la manipolazione dei dati e il supporto del controllo dei dati, è possibile creare strutture di data mining e modelli di data mining tramite gli strumenti visivi forniti da [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], quindi estendere gli oggetti di data mining creati tramite script DMX (Data Mining Extensions) e ASSL (Analysis Services Scripting Language).</span><span class="sxs-lookup"><span data-stu-id="6058e-108">Because [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] uses XMLA for data definition, data manipulation, and data control support, you can create mining structures and mining models by using the visual tools provided by [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], and then extend the data mining objects that you have created by using Data Mining Extensions (DMX) and Analysis Services Scripting Language (ASSL) scripts.</span></span>  
  
     <span data-ttu-id="6058e-109">È possibile creare e modificare completamente oggetti di data mining negli script XMLA ed eseguire query di stima sui modelli a livello di codice dalle applicazioni personalizzate.</span><span class="sxs-lookup"><span data-stu-id="6058e-109">You can create and modify data mining objects entirely in XMLA scripts, and run prediction queries against the models programmatically from your own applications.</span></span>  
  
-   <span data-ttu-id="6058e-110">**AMO (Analysis Management Objects)**</span><span class="sxs-lookup"><span data-stu-id="6058e-110">**Analysis Management Objects (AMO)**</span></span>  
  
     [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="6058e-111">include inoltre un framework completo che consente ai provider di data mining di terze parti di integrare gli oggetti di data mining in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6058e-111">also provides a complete framework that enables third-party data mining providers to integrate the data mining objects into [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>  
  
     <span data-ttu-id="6058e-112">È possibile creare le strutture e i modelli di data mining tramite AMO.</span><span class="sxs-lookup"><span data-stu-id="6058e-112">You can create mining structures and mining models by using AMO.</span></span> <span data-ttu-id="6058e-113">Vedere gli esempi seguenti in CodePlex:</span><span class="sxs-lookup"><span data-stu-id="6058e-113">See the following samples in CodePlex:</span></span>  
  
    -   <span data-ttu-id="6058e-114">Visualizzatore AMO</span><span class="sxs-lookup"><span data-stu-id="6058e-114">AMO Browser</span></span>  
  
         <span data-ttu-id="6058e-115">Si connette all'istanza di SSAS specificata e restituisce un elenco di tutti gli oggetti server e delle relative proprietà, inclusa la struttura di data mining e i modelli di data mining.</span><span class="sxs-lookup"><span data-stu-id="6058e-115">Connects to the SSAS instance you specify and lists all server objects and their properties, including mining structure and mining models.</span></span>  
  
    -   <span data-ttu-id="6058e-116">AMO Simple Sample</span><span class="sxs-lookup"><span data-stu-id="6058e-116">AMO Simple Sample</span></span>  
  
         <span data-ttu-id="6058e-117">AS Simple Sample illustra l'accesso a livello di codice alla maggior parte degli oggetti principali e dimostra la visualizzazione dei metadati e l'accesso ai valori negli oggetti.</span><span class="sxs-lookup"><span data-stu-id="6058e-117">The AS Simple Sample covers programmatic access to most major objects, and demonstrates metadata browsing, and access to the values in objects.</span></span>  
  
         <span data-ttu-id="6058e-118">L'esempio illustra inoltre come creare ed elaborare una struttura e un modello di data mining, nonché sfogliare un modello di data mining esistente.</span><span class="sxs-lookup"><span data-stu-id="6058e-118">The sample also demonstrates how to create and process a data mining structure and model, as well as browse an existing data mining model.</span></span>  
  
-   <span data-ttu-id="6058e-119">**DMX**</span><span class="sxs-lookup"><span data-stu-id="6058e-119">**DMX**</span></span>  
  
     <span data-ttu-id="6058e-120">È possibile utilizzare DMX per incapsulare istruzioni di comando, query di stima e query sui metadati e per restituire i risultati in un formato tabulare, presupponendo che sia stata creata una connessione a un server [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6058e-120">You can use DMX to encapsulate command statements, prediction queries, and metadata queries and return results in a tabular format, assuming you have created a connection to an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] server.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6058e-121">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="6058e-121">In This Section</span></span>  
 [<span data-ttu-id="6058e-122">OLE DB for Data Mining</span><span class="sxs-lookup"><span data-stu-id="6058e-122">OLE DB for Data Mining</span></span>](../../../2014/analysis-services/dev-guide/ole-db-for-data-mining.md)  
 <span data-ttu-id="6058e-123">Vengono descritte le aggiunte alla specifica per il supporto di data mining e dati multidimensionali, ovvero nuovi set di righe e colonne dello schema e linguaggio DMX (Data Mining Extensions) per la creazione e la gestione di strutture di data mining.</span><span class="sxs-lookup"><span data-stu-id="6058e-123">Describes additions to the specification to support data mining and multidimensional data: new schema rowsets and columns, Data Mining Extensions (DMX) language for creating and managing mining structures.</span></span>  
  
## <a name="related-reference"></a><span data-ttu-id="6058e-124">Riferimenti correlati</span><span class="sxs-lookup"><span data-stu-id="6058e-124">Related Reference</span></span>  
 [<span data-ttu-id="6058e-125">Sviluppo con ADOMD.NET</span><span class="sxs-lookup"><span data-stu-id="6058e-125">Developing with ADOMD.NET</span></span>](https://docs.microsoft.com/bi-reference/adomd/developing-with-adomd-net)  
 <span data-ttu-id="6058e-126">Viene fornita un'introduzione agli oggetti di programmazione client e server ADOMD.NET.</span><span class="sxs-lookup"><span data-stu-id="6058e-126">Introduces ADOMD.NET client and server programming objects.</span></span>  
  
 [<span data-ttu-id="6058e-127">Sviluppo con AMO &#40;Analysis Management Objects&#41;</span><span class="sxs-lookup"><span data-stu-id="6058e-127">Developing with Analysis Management Objects &#40;AMO&#41;</span></span>](https://docs.microsoft.com/bi-reference/amo/developing-with-analysis-management-objects-amo)  
 <span data-ttu-id="6058e-128">Viene fornita un'introduzione alla libreria di programmazione AMO.</span><span class="sxs-lookup"><span data-stu-id="6058e-128">Introduces the AMO programming library.</span></span>  
  
 [<span data-ttu-id="6058e-129">Sviluppo con Analysis Services Scripting Language &#40;ASSL&#41;</span><span class="sxs-lookup"><span data-stu-id="6058e-129">Developing with Analysis Services Scripting Language &#40;ASSL&#41;</span></span>](../multidimensional-models/scripting-language-assl/developing-with-analysis-services-scripting-language-assl.md)  
 <span data-ttu-id="6058e-130">Viene fornita un'introduzione a XML for Analysis (XMLA) e alle relative estensioni.</span><span class="sxs-lookup"><span data-stu-id="6058e-130">Introduces XML for Analysis (XMLA) and its extensions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6058e-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6058e-131">See Also</span></span>  
 <span data-ttu-id="6058e-132">[Guida per gli sviluppatori &#40;Analysis Services&#41;](../analysis-services-developer-documentation.md) </span><span class="sxs-lookup"><span data-stu-id="6058e-132">[Developer's Guide &#40;Analysis Services&#41;](../analysis-services-developer-documentation.md) </span></span>  
 [<span data-ttu-id="6058e-133">Guida di riferimento a DMX &#40;Data Mining Extensions&#41;</span><span class="sxs-lookup"><span data-stu-id="6058e-133">Data Mining Extensions &#40;DMX&#41; Reference</span></span>](/sql/dmx/data-mining-extensions-dmx-reference)  
  
  
