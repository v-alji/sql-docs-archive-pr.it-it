---
title: Attività e procedure relative alle query di data mining | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining models [Analysis Services], how-to topics
ms.assetid: 1bc2a775-6e62-4c66-a53c-201f2ea66295
author: minewiskan
ms.author: owend
ms.openlocfilehash: 454a3af33d0c18232bb36771235b328a17da6b86
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637522"
---
# <a name="data-mining-query-tasks-and-how-tos"></a><span data-ttu-id="7ee32-102">Attività e procedure relative alle query di data mining</span><span class="sxs-lookup"><span data-stu-id="7ee32-102">Data Mining Query Tasks and How-tos</span></span>
  <span data-ttu-id="7ee32-103">La possibilità di creare query è fondamentale se si utilizzeranno i modelli di data mining.</span><span class="sxs-lookup"><span data-stu-id="7ee32-103">The ability to create queries is critical if you are to make use of your data mining models.</span></span> <span data-ttu-id="7ee32-104">Questa sezione include collegamenti a esempi relativi alla creazione di query rispetto a un modello di data mining mediante gli strumenti disponibili in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] e [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7ee32-104">This section provides links to examples of how to create queries against a data mining model by using the tools provided in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="7ee32-105">Per altre informazioni sulle query di data mining o sui diversi tipi di query che è possibile creare, vedere [Query di data mining](data-mining-queries.md).</span><span class="sxs-lookup"><span data-stu-id="7ee32-105">If you need more information about what a data mining query is, or the different types of queries you can create, see [Data Mining Queries](data-mining-queries.md).</span></span>  
  
## <a name="creating-queries-with-prediction-query-builder"></a><span data-ttu-id="7ee32-106">Creazione di query con il generatore delle query di stima</span><span class="sxs-lookup"><span data-stu-id="7ee32-106">Creating Queries with Prediction Query Builder</span></span>  
 <span data-ttu-id="7ee32-107">Il generatore delle query di stima è disponibile sia in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] sia in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] come strumento grafico per la creazione di query rispetto ai modelli di data mining.</span><span class="sxs-lookup"><span data-stu-id="7ee32-107">The Prediction Query Builder is provided in both [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] and [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] as a way of graphically building queries against data mining models.</span></span> <span data-ttu-id="7ee32-108">Negli argomenti seguenti viene illustrato come selezionare un modello, specificare un'origine dati, personalizzare le stime e salvare l'output.</span><span class="sxs-lookup"><span data-stu-id="7ee32-108">The following topics explain how you can select a model, specify a data source, customize the predictions, and save output.</span></span>  
  
-   [<span data-ttu-id="7ee32-109">Creare una query di stima utilizzando Generatore query di stima</span><span class="sxs-lookup"><span data-stu-id="7ee32-109">Create a Prediction Query Using the Prediction Query Builder</span></span>](create-a-prediction-query-using-the-prediction-query-builder.md)  
  
-   [<span data-ttu-id="7ee32-110">Creare una query singleton in Progettazione modelli di data mining</span><span class="sxs-lookup"><span data-stu-id="7ee32-110">Create a Singleton Query in the Data Mining Designer</span></span>](create-a-singleton-query-in-the-data-mining-designer.md)  
  
-   [<span data-ttu-id="7ee32-111">Creare una query di stima utilizzando Generatore query di stima</span><span class="sxs-lookup"><span data-stu-id="7ee32-111">Create a Prediction Query Using the Prediction Query Builder</span></span>](create-a-prediction-query-using-the-prediction-query-builder.md)  
  
-   [<span data-ttu-id="7ee32-112">Visualizzare e salvare i risultati di una query di stima</span><span class="sxs-lookup"><span data-stu-id="7ee32-112">View and Save the Results of a Prediction Query</span></span>](view-and-save-the-results-of-a-prediction-query.md)  
  
-   [<span data-ttu-id="7ee32-113">Modificare manualmente un query di stima</span><span class="sxs-lookup"><span data-stu-id="7ee32-113">Manually Edit a Prediction Query</span></span>](manually-edit-a-prediction-query.md)  
  
-   [<span data-ttu-id="7ee32-114">Applicare le funzioni di stima a un modello</span><span class="sxs-lookup"><span data-stu-id="7ee32-114">Apply Prediction Functions to a Model</span></span>](apply-prediction-functions-to-a-model.md)  
  
-   [<span data-ttu-id="7ee32-115">Scegliere ed eseguire il mapping di dati di input per una query di stima</span><span class="sxs-lookup"><span data-stu-id="7ee32-115">Choose and Map Input Data for a Prediction Query</span></span>](choose-and-map-input-data-for-a-prediction-query.md)  
  
## <a name="using-other-data-mining-query-tools"></a><span data-ttu-id="7ee32-116">Utilizzo di altri strumenti di query di data mining</span><span class="sxs-lookup"><span data-stu-id="7ee32-116">Using Other Data Mining Query Tools</span></span>  
 <span data-ttu-id="7ee32-117">Oltre a usare il generatore delle query di stima, è possibile digitare una query direttamente in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] tramite DMX o XMLA.</span><span class="sxs-lookup"><span data-stu-id="7ee32-117">In addition to using the Prediction Query Builder, you can type a query directly into [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] by using DMX or by using XMLA.</span></span> <span data-ttu-id="7ee32-118">È inoltre possibile creare le query di stima a livello di codice e inviarle a un server [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7ee32-118">You can also build prediction queries programmatically and send them to an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] server.</span></span> <span data-ttu-id="7ee32-119">Negli argomenti seguenti vengono fornite informazioni sulla creazione e utilizzo delle query di stima all'esterno del generatore delle query di stima.</span><span class="sxs-lookup"><span data-stu-id="7ee32-119">The following topics provide more information about how to create and work with prediction queries outside of the Prediction Query Builder.</span></span>  
  
 [<span data-ttu-id="7ee32-120">Creare una query di stima singleton da un modello</span><span class="sxs-lookup"><span data-stu-id="7ee32-120">Create a Singleton Prediction Query from a Template</span></span>](create-a-singleton-prediction-query-from-a-template.md)  
 <span data-ttu-id="7ee32-121">Viene illustrato come usare gli strumenti disponibili in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] per creare ed eseguire una query di stima.</span><span class="sxs-lookup"><span data-stu-id="7ee32-121">Describes how to use the tools in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to build and run a prediction query.</span></span>  
  
 [<span data-ttu-id="7ee32-122">Creare una query di stima singleton da un modello</span><span class="sxs-lookup"><span data-stu-id="7ee32-122">Create a Singleton Prediction Query from a Template</span></span>](create-a-singleton-prediction-query-from-a-template.md)  
 <span data-ttu-id="7ee32-123">Viene illustrato come usare i modelli disponibili in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] per aggiungere parametri a una query di stima.</span><span class="sxs-lookup"><span data-stu-id="7ee32-123">Describes how to use the templates that are provided in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to add parameters to a prediction query.</span></span>  
  
 [<span data-ttu-id="7ee32-124">Modificare il valore di timeout per le query di data mining</span><span class="sxs-lookup"><span data-stu-id="7ee32-124">Change the Time-out Value for Data Mining Queries</span></span>](change-the-time-out-value-for-data-mining-queries.md)  
 <span data-ttu-id="7ee32-125">Viene illustrato come impostare proprietà nel server per controllare il comportamento correlato alle query di data mining.</span><span class="sxs-lookup"><span data-stu-id="7ee32-125">Describes how to set properties on the server that control behavior related to data mining queries.</span></span>  
  
 [<span data-ttu-id="7ee32-126">Creare una query sul contenuto di un modello di data mining</span><span class="sxs-lookup"><span data-stu-id="7ee32-126">Create a Content Query on a Mining Model</span></span>](create-a-content-query-on-a-mining-model.md)  
 <span data-ttu-id="7ee32-127">Viene illustrato come creare query che restituiscono informazioni dettagliate archiviate nel modello di data mining utilizzando i set di righe dello schema di data mining.</span><span class="sxs-lookup"><span data-stu-id="7ee32-127">Describes how to create queries that return detailed information that is stored in the mining model by using the data mining schema rowsets.</span></span>  
  
 [<span data-ttu-id="7ee32-128">Creare una query di data mining usando XMLA</span><span class="sxs-lookup"><span data-stu-id="7ee32-128">Create a Data Mining Query by Using XMLA</span></span>](create-a-data-mining-query-by-using-xmla.md)  
 <span data-ttu-id="7ee32-129">Viene illustrato come creare una query sul contenuto del modello di data mining utilizzando i modelli XMLA in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7ee32-129">Describes how to create a query against mining model content by using the XMLA templates in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ee32-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7ee32-130">See Also</span></span>  
 <span data-ttu-id="7ee32-131">[Riferimento al linguaggio di query ed espressioni &#40;Analysis Services&#41;](https://msdn.microsoft.com/library/gg492188(SQL.130).aspx) </span><span class="sxs-lookup"><span data-stu-id="7ee32-131">[Query and Expression Language Reference &#40;Analysis Services&#41;](https://msdn.microsoft.com/library/gg492188(SQL.130).aspx) </span></span>  
 [<span data-ttu-id="7ee32-132">Stored procedure di data mining &#40;Analysis Services - Data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="7ee32-132">Data Mining Stored Procedures &#40;Analysis Services - Data Mining&#41;</span></span>](/sql/analysis-services/data-mining/data-mining-stored-procedures-analysis-services-data-mining)  
  
  
