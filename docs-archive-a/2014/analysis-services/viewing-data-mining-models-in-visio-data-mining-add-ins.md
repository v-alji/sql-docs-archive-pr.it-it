---
title: Visualizzazione di modelli di data mining in Visio (componenti aggiuntivi Data mining) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- diagram, modifying
- templates [Visio]
- shapes, data mining
- diagram
ms.assetid: 5841adea-6650-4fae-8526-26af33edbede
author: minewiskan
ms.author: owend
ms.openlocfilehash: f3c1e63c058295b93e2562c64a6df90a30273a10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626901"
---
# <a name="viewing-data-mining-models-in-visio-data-mining-add-ins"></a><span data-ttu-id="f73a3-102">Visualizzazione di modelli di data mining in Visio (componenti aggiuntivi Data mining)</span><span class="sxs-lookup"><span data-stu-id="f73a3-102">Viewing Data Mining Models in Visio (Data Mining Add-ins)</span></span>
  <span data-ttu-id="f73a3-103">Le forme di Visio per il data mining consentono di connettersi a un server e creare un diagramma che rappresenta un modello di data mining esistente.</span><span class="sxs-lookup"><span data-stu-id="f73a3-103">The Visio shapes for data mining let you connect to a server and create a diagram representing an existing data mining model.</span></span> <span data-ttu-id="f73a3-104">I diagrammi possono quindi essere personalizzati utilizzando i controlli di Visio, ma è anche possibile eseguire il drill-down nei dati, esporre alcune delle statistiche sottostanti e utilizzare il modello sottostante.</span><span class="sxs-lookup"><span data-stu-id="f73a3-104">The diagrams can then be customized using Visio controls, but you can also drill down into data, expose some of the underlying statistics, and work with the underlying model.</span></span>  
  
## <a name="building-a-model-diagram"></a><span data-ttu-id="f73a3-105">Compilazione di un diagramma del modello</span><span class="sxs-lookup"><span data-stu-id="f73a3-105">Building a Model Diagram</span></span>  
 <span data-ttu-id="f73a3-106">Quando si apre il file contenente le forme di Visio per data mining, nel riquadro **forme** vengono visualizzate le forme seguenti.</span><span class="sxs-lookup"><span data-stu-id="f73a3-106">When you open the file containing the Visio shapes for data mining, the **Shapes** pane shows the following shapes.</span></span>  
  
 <span data-ttu-id="f73a3-107">Se all'apertura di Visio le forme di data mining non sono visibili, aprire il file modello dalla cartella di installazione.</span><span class="sxs-lookup"><span data-stu-id="f73a3-107">If you do not see the data mining shapes when you open Visio, open the template file from the installation folder.</span></span>  
  
 <span data-ttu-id="f73a3-108">![DM](media/dm-stencil.gif "DM")</span><span class="sxs-lookup"><span data-stu-id="f73a3-108">![DM](media/dm-stencil.gif "DM")</span></span>  
  
 <span data-ttu-id="f73a3-109">Per utilizzare una forma, trascinarla nella pagina.</span><span class="sxs-lookup"><span data-stu-id="f73a3-109">To use a shape, drag it to the page.</span></span> <span data-ttu-id="f73a3-110">Con ogni forma viene aperta una procedura guidata diversa, che consente di selezionare i dati di origine, di impostare opzioni per il tipo di diagramma specifico e di specificare l'ombreggiatura e altre opzioni di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="f73a3-110">Each of the shapes opens a different wizard, which helps you select source data, set options for the specific diagram type, and specify shading and other display options.</span></span>  
  
 <span data-ttu-id="f73a3-111">Nella tabella seguente sono elencati i tipi di modelli che è possibile utilizzare con ogni tipo di diagramma.</span><span class="sxs-lookup"><span data-stu-id="f73a3-111">The following table lists the types of models that you can use with each type of diagram.</span></span>  
  
|<span data-ttu-id="f73a3-112">Forma di Visio</span><span class="sxs-lookup"><span data-stu-id="f73a3-112">Visio shape</span></span>|<span data-ttu-id="f73a3-113">Modelli supportati</span><span class="sxs-lookup"><span data-stu-id="f73a3-113">Supported models</span></span>|  
|-----------------|----------------------|  
|<span data-ttu-id="f73a3-114">Albero delle decisioni</span><span class="sxs-lookup"><span data-stu-id="f73a3-114">Decision Tree</span></span>|<span data-ttu-id="f73a3-115">Utilizzare questa forma per modelli basati sugli algoritmi di regressione lineare o dell'albero delle decisioni.</span><span class="sxs-lookup"><span data-stu-id="f73a3-115">Use this shape for models based on the decision tree or linear regression algorithms.</span></span>|  
|<span data-ttu-id="f73a3-116">Rete di dipendenze</span><span class="sxs-lookup"><span data-stu-id="f73a3-116">Dependency Network</span></span>|<span data-ttu-id="f73a3-117">Utilizzare questa forma per modelli basati su uno dei seguenti algoritmi: Naïve Bayes, Decision Trees o Association Rules.</span><span class="sxs-lookup"><span data-stu-id="f73a3-117">Use this shape for models based on any of the following algorithms: Naive Bayes, Decision Trees, or Association Rules.</span></span>|  
|<span data-ttu-id="f73a3-118">Cluster</span><span class="sxs-lookup"><span data-stu-id="f73a3-118">Cluster</span></span>|<span data-ttu-id="f73a3-119">Utilizzare questa forma per modelli basati su algoritmi di clustering.</span><span class="sxs-lookup"><span data-stu-id="f73a3-119">Use this shape for models based on clustering algorithms.</span></span>|  
  
 <span data-ttu-id="f73a3-120">Le opzioni disponibili nella procedura guidata variano a seconda del tipo di dati del modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="f73a3-120">Depending on the type of data in your mining model, the wizard may offer different options.</span></span> <span data-ttu-id="f73a3-121">Ad esempio, le colonne contenenti numeri continui vengono visualizzate in modo diverso rispetto alle variabili di categoria.</span><span class="sxs-lookup"><span data-stu-id="f73a3-121">For example, columns that contain continuous numbers are visualized differently than categorical variables.</span></span>  
  
## <a name="working-with-completed-shapes"></a><span data-ttu-id="f73a3-122">Utilizzo delle forme completate</span><span class="sxs-lookup"><span data-stu-id="f73a3-122">Working with Completed Shapes</span></span>  
 <span data-ttu-id="f73a3-123">Dopo il completamento è possibile utilizzare il diagramma per esplorare il modello di data mining o migliorarlo per l'utilizzo nelle presentazioni.</span><span class="sxs-lookup"><span data-stu-id="f73a3-123">After the diagram is complete, you can use it to browse the data mining model or enhance the diagram for use in presentations.</span></span>  
  
### <a name="visio-menus"></a><span data-ttu-id="f73a3-124">Menu di Visio</span><span class="sxs-lookup"><span data-stu-id="f73a3-124">Visio Menus</span></span>  
 <span data-ttu-id="f73a3-125">In Visio vengono forniti diversi controlli di rendering, temi e menu di scelta rapida per migliorare un diagramma.</span><span class="sxs-lookup"><span data-stu-id="f73a3-125">Visio provides a variety of rendering controls, themes, and shortcut menus to help enhance a diagram.</span></span>  
  
-   <span data-ttu-id="f73a3-126">Utilizzare i temi di Visio per modificare i colori del diagramma.</span><span class="sxs-lookup"><span data-stu-id="f73a3-126">Use Visio themes to alter diagram colors.</span></span>  
  
-   <span data-ttu-id="f73a3-127">Modificare i connettori o il layout del diagramma.</span><span class="sxs-lookup"><span data-stu-id="f73a3-127">Change connectors or diagram layout.</span></span>  
  
### <a name="data-mining-menus"></a><span data-ttu-id="f73a3-128">Menu di data mining</span><span class="sxs-lookup"><span data-stu-id="f73a3-128">Data Mining Menus</span></span>  
 <span data-ttu-id="f73a3-129">Queste barre degli strumenti e voci di menu vengono fornite dai componenti aggiuntivi specifici di ogni tipo di modello o forma.</span><span class="sxs-lookup"><span data-stu-id="f73a3-129">These toolbars and menu items are provided by the add-ins that are specific to each shape or model type</span></span>  
  
-   <span data-ttu-id="f73a3-130">Ogni tipo di diagramma contiene un menu di scelta rapida per la forma che consente di accedere alle opzioni speciali.</span><span class="sxs-lookup"><span data-stu-id="f73a3-130">Each diagram type has a shortcut menu for the shape that lets you access special options.</span></span> <span data-ttu-id="f73a3-131">Benché molte delle opzioni di tale menu siano comuni a tutte le forme di Visio, alcune opzioni sono univoche nei modelli di data mining.</span><span class="sxs-lookup"><span data-stu-id="f73a3-131">Although many options in this menu are common to all Visio shapes, some options are unique to the data mining templates</span></span>  
  
     <span data-ttu-id="f73a3-132">In un diagramma dell'albero delle decisioni ad esempio è possibile fare clic su un nodo e quindi comprimere i nodi figlio per semplificare la consultazione del diagramma oppure spostare i nodi figlio in una pagina a parte.</span><span class="sxs-lookup"><span data-stu-id="f73a3-132">For example, in a decision tree diagram, you can click an individual node and then collapse the child nodes to make the diagram simpler, or move child nodes to a separate page.</span></span>  
  
-   <span data-ttu-id="f73a3-133">Poiché la forma è associata ai dati del modello, è inoltre possibile eseguire alcune attività di esplorazione utilizzando il diagramma:</span><span class="sxs-lookup"><span data-stu-id="f73a3-133">Because the shape is bound to the model data, you can also do some amount of exploration using the diagram:</span></span>  
  
     <span data-ttu-id="f73a3-134">Filtrare i nodi visualizzati oppure modificare il livello dell'albero o la profondità del grafico.</span><span class="sxs-lookup"><span data-stu-id="f73a3-134">Filter the nodes that are displayed, or change the level of the tree or depth of the graph.</span></span>  
  
     <span data-ttu-id="f73a3-135">Eseguire lo zoom avanti in sezioni specifiche, cercare i nodi che contengono un determinato attributo o filtrare un grafico delle dipendenze in base ai bordi (probabilità).</span><span class="sxs-lookup"><span data-stu-id="f73a3-135">Zoom in on specific sections, search for nodes that contain a certain attribute, or filter a dependency graph by its edges (probability).</span></span>  
  
## <a name="walkthroughs"></a><span data-ttu-id="f73a3-136">Procedure dettagliate</span><span class="sxs-lookup"><span data-stu-id="f73a3-136">Walkthroughs</span></span>  
 <span data-ttu-id="f73a3-137">Per esempi di come utilizzare e interpretare un diagramma completato, vedere i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="f73a3-137">For examples of how to work with and interpret a completed diagram, see these topics:</span></span>  
  
 [<span data-ttu-id="f73a3-138">Descrizione dettagliata del diagramma dei cluster</span><span class="sxs-lookup"><span data-stu-id="f73a3-138">Cluster Diagram Walkthrough</span></span>](cluster-diagram-walkthrough-data-mining-add-ins.md)  
  
 [<span data-ttu-id="f73a3-139">Descrizione dettagliata del diagramma della rete di dipendenze</span><span class="sxs-lookup"><span data-stu-id="f73a3-139">Dependency Net Diagram Walkthrough</span></span>](dependency-network-diagram-walkthrough-data-mining-add-ins.md)  
  
 [<span data-ttu-id="f73a3-140">Descrizione dettagliata del diagramma dell'albero delle decisioni</span><span class="sxs-lookup"><span data-stu-id="f73a3-140">Decision Tree Diagram Walkthrough</span></span>](decision-tree-diagram-walkthrough-data-mining-add-ins.md)  
  
## <a name="see-also"></a><span data-ttu-id="f73a3-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f73a3-141">See Also</span></span>  
 [<span data-ttu-id="f73a3-142">Esplorazione di modelli in Excel &#40;SQL Server componenti aggiuntivi Data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="f73a3-142">Browsing Models in Excel &#40;SQL Server Data Mining Add-ins&#41;</span></span>](browsing-models-in-excel-sql-server-data-mining-add-ins.md)  
  
  
