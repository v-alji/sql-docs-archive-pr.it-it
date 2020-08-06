---
title: 'Creazione ed esecuzione di query sui modelli di data mining con DMX: esercitazioni (Analysis Services-Data mining) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- content queries [DMX]
ms.assetid: 145b81a7-c0c3-4ca3-bb32-0b482423b9a0
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 22ed01105a32f460bcbeb2c067299fdf62af2eed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622967"
---
# <a name="creating-and-querying-data-mining-models-with-dmx-tutorials-analysis-services---data-mining"></a><span data-ttu-id="9d80b-102">Creazione ed esecuzione di query sui modelli di data mining con DMX: esercitazioni (Analysis Services - Data mining)</span><span class="sxs-lookup"><span data-stu-id="9d80b-102">Creating and Querying Data Mining Models with DMX: Tutorials (Analysis Services - Data Mining)</span></span>
  <span data-ttu-id="9d80b-103">Dopo aver creato una soluzione data mining utilizzando [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , è possibile creare query sui modelli data mining per stimare le tendenze, recuperare modelli nei dati e misurare l'accuratezza dei modelli di data mining.</span><span class="sxs-lookup"><span data-stu-id="9d80b-103">After you have created a data mining solution by using [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], you can create queries against the data mining models to predict trends, retrieve patterns in the data, and measure the accuracy of the mining models.</span></span>  
  
 <span data-ttu-id="9d80b-104">Le esercitazioni dettagliate nell'elenco seguente consentono di apprendere come compilare ed eseguire query data mining usando in [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] modo da ottenere il massimo dai dati.</span><span class="sxs-lookup"><span data-stu-id="9d80b-104">The step-by-step tutorials in the following list will help you learn how to build and run data mining queries by using [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] so that you can get the most from your data.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9d80b-105">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="9d80b-105">In This Section</span></span>  
  
-   [<span data-ttu-id="9d80b-106">Esercitazione su DMX per Bike Buyer</span><span class="sxs-lookup"><span data-stu-id="9d80b-106">Bike Buyer DMX Tutorial</span></span>](../../2014/tutorials/bike-buyer-dmx-tutorial.md)  
  
     <span data-ttu-id="9d80b-107">In questa esercitazione viene illustrata la creazione di una nuova struttura di data mining e di modelli di data mining tramite il linguaggio DMX (Data Mining Extensions) e viene mostrato come creare query di stima DMX.</span><span class="sxs-lookup"><span data-stu-id="9d80b-107">This tutorial walks you through the creation of a new mining structure and mining models by using the Data Mining Extensions (DMX) language, and explains how to create DMX prediction queries.</span></span>  
  
-   [<span data-ttu-id="9d80b-108">Esercitazione su DMX per Market Basket</span><span class="sxs-lookup"><span data-stu-id="9d80b-108">Market Basket DMX Tutorial</span></span>](../../2014/tutorials/market-basket-dmx-tutorial.md)  
  
     <span data-ttu-id="9d80b-109">In questa esercitazione viene utilizzato un scenario tipico di analisi di mercato caratterizzato da associazioni tra i prodotti che i clienti acquistano insieme.</span><span class="sxs-lookup"><span data-stu-id="9d80b-109">This tutorial uses a typical market basket scenario, where you find associations between the products that customers purchase together.</span></span> <span data-ttu-id="9d80b-110">Viene inoltre illustrato come utilizzare tabelle nidificate quando si crea una struttura di data mining.</span><span class="sxs-lookup"><span data-stu-id="9d80b-110">This tutorial also demonstrates how to use nested tables when you create a mining structure.</span></span> <span data-ttu-id="9d80b-111">Viene compilato ed eseguito il training di un modello basato su questa struttura, quindi vengono create stime utilizzando DMX.</span><span class="sxs-lookup"><span data-stu-id="9d80b-111">You build and train a model based on this structure, and then create predictions using DMX.</span></span>  
  
-   [<span data-ttu-id="9d80b-112">Esercitazione su DMX per le stime basate su serie temporali</span><span class="sxs-lookup"><span data-stu-id="9d80b-112">Time Series Prediction DMX Tutorial</span></span>](../../2014/tutorials/time-series-prediction-dmx-tutorial.md)  
  
     <span data-ttu-id="9d80b-113">Questa esercitazione consente di creare un modello di stima per illustrare l'utilizzo dell'istruzione CREATE MODEL (DMX).</span><span class="sxs-lookup"><span data-stu-id="9d80b-113">This tutorial creates a forecasting model to illustrate the use of the CREATE MODEL (DMX) statement.</span></span> <span data-ttu-id="9d80b-114">È quindi possibile aggiungere modelli correlati e personalizzare il comportamento di ognuno modificando i parametri dell'algoritmo Microsoft Time Series.</span><span class="sxs-lookup"><span data-stu-id="9d80b-114">You then add related models and customize the behavior of each by changing the parameters of the Microsoft Time Series algorithm.</span></span> <span data-ttu-id="9d80b-115">Infine, è possibile creare stime e aggiornarle con i nuovi dati.</span><span class="sxs-lookup"><span data-stu-id="9d80b-115">Finally you create predictions and update the predictions with new data.</span></span> <span data-ttu-id="9d80b-116">La capacità di aggiornare una serie temporale durante l'esecuzione di stime è stata aggiunta in [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9d80b-116">The ability to update a time series while making predictions was added in [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)].</span></span>  
  
## <a name="reference"></a><span data-ttu-id="9d80b-117">Informazioni di riferimento</span><span class="sxs-lookup"><span data-stu-id="9d80b-117">Reference</span></span>  
 [<span data-ttu-id="9d80b-118">Algoritmi di data mining &#40;Analysis Services - Data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="9d80b-118">Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;</span></span>](../../2014/analysis-services/data-mining/data-mining-algorithms-analysis-services-data-mining.md)  
  
 [<span data-ttu-id="9d80b-119">Guida di riferimento a DMX &#40;Data Mining Extensions&#41;</span><span class="sxs-lookup"><span data-stu-id="9d80b-119">Data Mining Extensions &#40;DMX&#41; Reference</span></span>](/sql/dmx/data-mining-extensions-dmx-reference)  
  
## <a name="related-sections"></a><span data-ttu-id="9d80b-120">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="9d80b-120">Related Sections</span></span>  
  
-   [<span data-ttu-id="9d80b-121">Esercitazione di base sul data mining</span><span class="sxs-lookup"><span data-stu-id="9d80b-121">Basic Data Mining Tutorial</span></span>](../../2014/tutorials/basic-data-mining-tutorial.md)  
  
     <span data-ttu-id="9d80b-122">In questa esercitazione vengono introdotti concetti di base, quali le modalità di creazione di un progetto e di compilazione di modelli e strutture di data mining.</span><span class="sxs-lookup"><span data-stu-id="9d80b-122">This tutorial introduces basic concepts, such as how to create a project and how to build mining structures and mining models.</span></span>  
  
-   [<span data-ttu-id="9d80b-123">Esercitazione intermedia sul data mining &#40;Analysis Services-&#41;di data mining</span><span class="sxs-lookup"><span data-stu-id="9d80b-123">Intermediate Data Mining Tutorial &#40;Analysis Services - Data Mining&#41;</span></span>](../../2014/tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md)  
  
     <span data-ttu-id="9d80b-124">Questa esercitazione contiene numerose lezioni indipendenti, ognuna delle quali presenta un tipo di modello diverso.</span><span class="sxs-lookup"><span data-stu-id="9d80b-124">This tutorial contains a number of independent lessons, each introducing you to a different model type.</span></span> <span data-ttu-id="9d80b-125">In ogni lezione viene illustrato il processo di creazione, esplorazione e personalizzazione di un modello, oltre al processo di creazione di query di stima.</span><span class="sxs-lookup"><span data-stu-id="9d80b-125">Each lesson walks you through the process of creating a model, exploring the model, and then customizing the model and creating prediction queries.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d80b-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9d80b-126">See Also</span></span>  
 <span data-ttu-id="9d80b-127">[Soluzioni di data mining](../../2014/analysis-services/data-mining/data-mining-solutions.md) </span><span class="sxs-lookup"><span data-stu-id="9d80b-127">[Data Mining Solutions](../../2014/analysis-services/data-mining/data-mining-solutions.md) </span></span>  
 <span data-ttu-id="9d80b-128">[Strumenti di data mining](../../2014/analysis-services/data-mining/data-mining-tools.md) </span><span class="sxs-lookup"><span data-stu-id="9d80b-128">[Data Mining Tools](../../2014/analysis-services/data-mining/data-mining-tools.md) </span></span>  
 [<span data-ttu-id="9d80b-129">Progetti di data mining</span><span class="sxs-lookup"><span data-stu-id="9d80b-129">Data Mining Projects</span></span>](../../2014/analysis-services/data-mining/data-mining-projects.md)  
  
  
