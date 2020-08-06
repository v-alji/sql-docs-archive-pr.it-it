---
title: Procedura dettagliata relativa al diagramma della rete di dipendenze (componenti aggiuntivi Data mining) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Visio shapes, dependency network
- shapes, data mining
- shapes, network
- dependencies
- diagram, dependency network
- data mining layout toolbar
- dependency network
ms.assetid: aac732a8-5262-4649-b7d7-3ccf6f9cfa8b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 07f97dac7ffb0211f0ff1e1b58c2e0792d026174
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636939"
---
# <a name="dependency-network-diagram-walkthrough-data-mining-add-ins"></a><span data-ttu-id="20c7c-102">Descrizione dettagliata del diagramma della rete di dipendenze (componenti aggiuntivi Data mining)</span><span class="sxs-lookup"><span data-stu-id="20c7c-102">Dependency Network Diagram Walkthrough (Data Mining Add-ins)</span></span>
  <span data-ttu-id="20c7c-103">In vari tipi differenti di modelli di data mining viene utilizzato un grafico della rete come modalità di esplorazione delle relazioni nei dati.</span><span class="sxs-lookup"><span data-stu-id="20c7c-103">Several different types of data mining models use a network graph as a way of exploring relationships in the data.</span></span> <span data-ttu-id="20c7c-104">È possibile importare questi modelli in Visio utilizzando la forma **rete di dipendenze** , quindi continuare a personalizzare e migliorare il layout.</span><span class="sxs-lookup"><span data-stu-id="20c7c-104">You can import these models into Visio using the **Dependency Network** shape and then continue to customize and enhance the layout.</span></span> <span data-ttu-id="20c7c-105">Nelle **forme di data mining per Visio** sono inclusi i seguenti controlli personalizzati per l'utilizzo di diagrammi di rete di dipendenze:</span><span class="sxs-lookup"><span data-stu-id="20c7c-105">The **Data Mining Shapes for Visio** include the following custom controls for working with dependency network diagrams:</span></span>  
  
-   <span data-ttu-id="20c7c-106">Controlli di rendering per il grafico della rete</span><span class="sxs-lookup"><span data-stu-id="20c7c-106">Rendering controls for the network graph</span></span>  
  
     <span data-ttu-id="20c7c-107">Queste opzioni fanno parte della procedura guidata che viene avviata quando si rilascia una forma nell'area di lavoro di Visio.</span><span class="sxs-lookup"><span data-stu-id="20c7c-107">These options are part of the wizard that is launched when you drop a shape into the Visio workspace.</span></span>  
  
-   <span data-ttu-id="20c7c-108">Barra degli strumenti **Layout data mining**</span><span class="sxs-lookup"><span data-stu-id="20c7c-108">**Data Mining Layout** toolbar</span></span>  
  
     <span data-ttu-id="20c7c-109">Queste opzioni vengono aggiunte all'area di lavoro di Visio per consentire di interagire con il grafico della rete di dipendenze.</span><span class="sxs-lookup"><span data-stu-id="20c7c-109">These options are added to the Visio workspace to help you interact with the dependency network graph.</span></span>  
  
## <a name="build-a-dependency-network-graph"></a><span data-ttu-id="20c7c-110">Compilazione di un grafico della rete di dipendenze</span><span class="sxs-lookup"><span data-stu-id="20c7c-110">Build a Dependency Network Graph</span></span>  
 <span data-ttu-id="20c7c-111">È possibile rilasciare una forma nella pagina Visio per avviare la **procedura guidata forma di Visio per la rete di dipendenze** e impostare le opzioni del diagramma.</span><span class="sxs-lookup"><span data-stu-id="20c7c-111">You drop a shape onto the Visio page to launch the **Dependency Net Visio Shape Wizard** and set diagram options.</span></span>  
  
#### <a name="use-the-dependency-net-visio-shape-wizard"></a><span data-ttu-id="20c7c-112">Utilizzo della Procedura guidata Forma di Visio per rete di dipendenze</span><span class="sxs-lookup"><span data-stu-id="20c7c-112">Use the Dependency Net Visio Shape Wizard</span></span>  
  
1.  <span data-ttu-id="20c7c-113">Se non vengono visualizzate le **forme di data mining di Microsoft** nell'elenco **forme** , fare clic su **altre forme**, selezionare **Apri stencil**e aprire il modello dal percorso di installazione predefinito.</span><span class="sxs-lookup"><span data-stu-id="20c7c-113">If you do not see **Microsoft Data Mining Shapes** in the **Shapes** list, click **More Shapes**, select **Open Stencil**, and open the template from the default installation location.</span></span>  
  
     <span data-ttu-id="20c7c-114">\<drive>: \Program Files (X85) \Microsoft SQL Server 2012 DM Add-ins</span><span class="sxs-lookup"><span data-stu-id="20c7c-114">\<drive>:\Program files (x85)\Microsoft SQL Server 2012 DM Add-Ins</span></span>  
  
2.  <span data-ttu-id="20c7c-115">Trascinare la forma **rete di dipendenze** nella pagina per avviare la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="20c7c-115">Drag the **Dependency Network** shape onto the page to start the wizard.</span></span> <span data-ttu-id="20c7c-116">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="20c7c-116">Click **Next**.</span></span>  
  
3.  <span data-ttu-id="20c7c-117">Nella pagina iniziale della **procedura guidata forma di Visio per rete di dipendenze**fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="20c7c-117">On the welcome page of the **Dependency Network Visio Shape Wizard**, click **Next**.</span></span>  
  
4.  <span data-ttu-id="20c7c-118">Nella pagina **Selezione origine dati** della **procedura guidata forma di Visio per rete di dipendenze**scegliere una connessione a un [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server che disponga del modello che si desidera visualizzare.</span><span class="sxs-lookup"><span data-stu-id="20c7c-118">On the **Select a Data Source** page of the **Dependency Network Visio Shape Wizard**, choose a connection to an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server that has the model you want to visualize.</span></span>  
  
5.  <span data-ttu-id="20c7c-119">Selezionare un modello di data mining appropriato e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="20c7c-119">Select an appropriate mining model, and click **Next**.</span></span>  
  
     <span data-ttu-id="20c7c-120">Per selezionare un modello appropriato, è possibile esaminare il nome, la descrizione, le colonne e il tipo di dati nel riquadro **Proprietà** .</span><span class="sxs-lookup"><span data-stu-id="20c7c-120">To select an appropriate model, you can review the name, description, columns, and type of data in the **Properties** pane.</span></span>  
  
     <span data-ttu-id="20c7c-121">Questa forma supporta modelli creati tramite questi algoritmi:</span><span class="sxs-lookup"><span data-stu-id="20c7c-121">This shape supports models created by using these algorithms:</span></span>  
  
    -   <span data-ttu-id="20c7c-122">Naive Bayes</span><span class="sxs-lookup"><span data-stu-id="20c7c-122">Naïve Bayes</span></span>  
  
    -   <span data-ttu-id="20c7c-123">Decision Trees</span><span class="sxs-lookup"><span data-stu-id="20c7c-123">Decision Trees</span></span>  
  
    -   <span data-ttu-id="20c7c-124">Regole di associazione</span><span class="sxs-lookup"><span data-stu-id="20c7c-124">Association Rules</span></span>  
  
6.  <span data-ttu-id="20c7c-125">Nella pagina selezionare i **nodi di cui eseguire il rendering**, personalizzare le dimensioni del grafico e, facoltativamente, applicare un filtro in modo da includere solo determinati nodi.</span><span class="sxs-lookup"><span data-stu-id="20c7c-125">On the page, **Select Nodes to Render**, customize the size of the graph, and optionally filter to only include certain nodes.</span></span>  
  
     <span data-ttu-id="20c7c-126">Con un set di dati di grandi dimensioni, un grafico delle dipendenze può diventare grande e contenere molti oggetti correlati, rappresentati come *nodi*.</span><span class="sxs-lookup"><span data-stu-id="20c7c-126">With a large dataset, a dependency graph can become huge, and contain many related objects, represented as *nodes*.</span></span> <span data-ttu-id="20c7c-127">Tramite questa finestra di dialogo, è possibile creare un grafico della rete personalizzato in cui sono inclusi solo i nodi di interesse.</span><span class="sxs-lookup"><span data-stu-id="20c7c-127">By using this dialog box, you can create a custom network graph that includes only the nodes of interest.</span></span>  
  
     <span data-ttu-id="20c7c-128">[segnaposto artistico]</span><span class="sxs-lookup"><span data-stu-id="20c7c-128">[art placeholder]</span></span>  
  
     <span data-ttu-id="20c7c-129">**Numero di nodi da recuperare**</span><span class="sxs-lookup"><span data-stu-id="20c7c-129">**Number of nodes to fetch**</span></span>  
     <span data-ttu-id="20c7c-130">Se nel modello sono contenuti meno nodi rispetto al numero specificato, questa impostazione non avrà effetto.</span><span class="sxs-lookup"><span data-stu-id="20c7c-130">If the model contains fewer than the specified number of nodes, this setting has no effect.</span></span> <span data-ttu-id="20c7c-131">Se nel modello sono contenuti più nodi rispetto al numero specificato, verranno visualizzati solo i nodi più attendibili.</span><span class="sxs-lookup"><span data-stu-id="20c7c-131">If the model contains more nodes than the specified number, only the strongest nodes are displayed.</span></span>  
  
     <span data-ttu-id="20c7c-132">**Contenuto del nome**</span><span class="sxs-lookup"><span data-stu-id="20c7c-132">**Name contains**</span></span>  
     <span data-ttu-id="20c7c-133">Lasciare vuota questa casella e fare clic sulla freccia verde per recuperare tutti i nodi del modello.</span><span class="sxs-lookup"><span data-stu-id="20c7c-133">Leave this box blank and click the green arrow to retrieve all nodes in the model.</span></span>  
  
     <span data-ttu-id="20c7c-134">In alternativa, digitare una stringa e fare clic sulla freccia verde per restituire solo i nodi contenenti la stringa specificata.</span><span class="sxs-lookup"><span data-stu-id="20c7c-134">Or, type a string and click the green arrow to return only those nodes that contain the specified string.</span></span>  
  
     <span data-ttu-id="20c7c-135">La maggior parte dei modelli che è possibile creare con i dati di esempio non è grande, pertanto per questo esempio, aumentare il numero di nodi a 10, quindi fare clic sulla freccia verde per eseguire una query e ottenere un elenco di tutti i nodi.</span><span class="sxs-lookup"><span data-stu-id="20c7c-135">Most of the models that you can create with the sample data are not big, so for this example, increase the number of nodes to 10, and then click the green arrow to run a query and get the list of all nodes.</span></span>  
  
7.  <span data-ttu-id="20c7c-136">Fare clic su **Avanzate** per impostare le opzioni di ombreggiatura e forma per il grafico.</span><span class="sxs-lookup"><span data-stu-id="20c7c-136">Click **Advanced** to set shading and shape options for the graph.</span></span>  
  
8.  <span data-ttu-id="20c7c-137">Fare clic su **Chiudi** per uscire dalla finestra di dialogo Opzioni **Avanzate** e quindi fare clic su **fine** per creare il grafico.</span><span class="sxs-lookup"><span data-stu-id="20c7c-137">Click **Close** to exit the **Advanced** options dialog box, and then click **Finish** to create the graph.</span></span>  
  
## <a name="explore-and-modify-the-finished-diagram"></a><span data-ttu-id="20c7c-138">Esplorazione e modifica del diagramma completato</span><span class="sxs-lookup"><span data-stu-id="20c7c-138">Explore and Modify the Finished Diagram</span></span>  
 <span data-ttu-id="20c7c-139">Dopo aver creato in Visio il grafico della rete di dipendenze, è possibile continuare a modificare e migliorare il grafico utilizzando le funzionalità di Visio.</span><span class="sxs-lookup"><span data-stu-id="20c7c-139">After Visio has created the network dependency graph, you can continue to modify and enhance the graph by using the features in Visio.</span></span>  
  
 <span data-ttu-id="20c7c-140">Nel grafico seguente viene mostrato il layout predefinito di un grafico della rete di dipendenze.</span><span class="sxs-lookup"><span data-stu-id="20c7c-140">The following graphic shows the default layout of a dependency network graph.</span></span>  
  
 <span data-ttu-id="20c7c-141">[segnaposto artistico]</span><span class="sxs-lookup"><span data-stu-id="20c7c-141">[art placeholder]</span></span>  
  
1.  <span data-ttu-id="20c7c-142">Utilizzare il controllo **Pan e zoom** , nell'area **riquadro attività** della barra multifunzione **visualizzazione** Visio, per concentrarsi su una sezione del grafico e spostarsi intorno al diagramma.</span><span class="sxs-lookup"><span data-stu-id="20c7c-142">Use the **Pan and Zoom** control, in the **Task Pane** area of the Visio **View** ribbon, to focus on a section of the graph and move around the diagram.</span></span>  
  
2.  <span data-ttu-id="20c7c-143">Provare a usare layout di grafico diversi forniti dall'opzione di **pagina nuovo layout** di Visio.</span><span class="sxs-lookup"><span data-stu-id="20c7c-143">Experiment with different graph layouts provided by the Visio **Re-Layout Page** option.</span></span>  
  
3.  <span data-ttu-id="20c7c-144">Fare clic sulla barra multifunzione **componenti** aggiuntivi e quindi visualizzare una delle barre degli strumenti personalizzate utilizzate per l'utilizzo dei diagrammi data mining:</span><span class="sxs-lookup"><span data-stu-id="20c7c-144">Click the **Add-Ins** ribbon, and then display one of the custom toolbars used for working with data mining diagrams:</span></span>  
  
     <span data-ttu-id="20c7c-145">**Layout**</span><span class="sxs-lookup"><span data-stu-id="20c7c-145">**Layout**</span></span>  
     <span data-ttu-id="20c7c-146">Consente di ottimizzare il layout dei nodi nella pagina, nonché di modificare la visualizzazione in modo da includere tutti i nodi.</span><span class="sxs-lookup"><span data-stu-id="20c7c-146">Optimizes the layout of nodes on the page, and changes the view so that all nodes are visible.</span></span>  
  
     <span data-ttu-id="20c7c-147">**Ridimensiona pagina**</span><span class="sxs-lookup"><span data-stu-id="20c7c-147">**Resize Page**</span></span>  
     <span data-ttu-id="20c7c-148">Consente di modificare le dimensioni della pagina in modo da visualizzare tutti i nodi.</span><span class="sxs-lookup"><span data-stu-id="20c7c-148">Changes the size of the page so that all nodes are visible.</span></span>  
  
     <span data-ttu-id="20c7c-149">**Livello attendibilità bordo**</span><span class="sxs-lookup"><span data-stu-id="20c7c-149">**Edge Strength**</span></span>  
     <span data-ttu-id="20c7c-150">Consente di attivare e disattivare la visualizzazione del livello di attendibilità bordo per l'intero grafico.</span><span class="sxs-lookup"><span data-stu-id="20c7c-150">Toggles display of edge strength for the entire graph.</span></span> <span data-ttu-id="20c7c-151">Un bordo è un collegamento tra nodi.</span><span class="sxs-lookup"><span data-stu-id="20c7c-151">An edge is a connection between nodes.</span></span> <span data-ttu-id="20c7c-152">È possibile utilizzare il controllo dispositivo di scorrimento per escludere tramite filtro i collegamenti non attendibili.</span><span class="sxs-lookup"><span data-stu-id="20c7c-152">You can use the slider control to filter out connections that are not strong.</span></span>  
  
     <span data-ttu-id="20c7c-153">**Dispositivo di scorrimento**</span><span class="sxs-lookup"><span data-stu-id="20c7c-153">**Slider**</span></span>  
     <span data-ttu-id="20c7c-154">Il **dispositivo di scorrimento** consente di controllare il livello di attendibilità delle relazioni visualizzate nel diagramma della rete di dipendenze.</span><span class="sxs-lookup"><span data-stu-id="20c7c-154">The **Slider** helps you control the strength of the relationships that are displayed in the dependency network diagram.</span></span>  
  
     <span data-ttu-id="20c7c-155">Ogni nodo del grafico rappresenta uno stato.</span><span class="sxs-lookup"><span data-stu-id="20c7c-155">Each node in the graph represents a state.</span></span> <span data-ttu-id="20c7c-156">Una freccia rappresenta una transizione tra due stati e la probabilità associata alla transizione.</span><span class="sxs-lookup"><span data-stu-id="20c7c-156">An arrow represents a transition between two states and the probability that is associated with the transition.</span></span> <span data-ttu-id="20c7c-157">Per ridurre il numero di nodi nel grafico, spostare il dispositivo di scorrimento verso l'alto.</span><span class="sxs-lookup"><span data-stu-id="20c7c-157">To reduce the number of nodes in the graph, move the slider bar up.</span></span>  
  
     <span data-ttu-id="20c7c-158">Per aumentare il numero di nodi del grafico, spostare il dispositivo di scorrimento verso il basso.</span><span class="sxs-lookup"><span data-stu-id="20c7c-158">To increase the number of nodes in the graph, move the slider bar down.</span></span>  
  
     <span data-ttu-id="20c7c-159">**Aggiungi elementi**</span><span class="sxs-lookup"><span data-stu-id="20c7c-159">**Add Items**</span></span>  
     <span data-ttu-id="20c7c-160">Apre la finestra di dialogo **Seleziona nodi per il rendering** , in modo che sia possibile selezionare nuovi nodi da aggiungere al grafico.</span><span class="sxs-lookup"><span data-stu-id="20c7c-160">Opens the **Select Nodes to Render** dialog box so that you can select new nodes to add to the graph.</span></span>  
  
4.  <span data-ttu-id="20c7c-161">È possibile rendere i grafici semplici o elaborati come desiderato e aggiungere annotazioni, rimanendo connessi al modello.</span><span class="sxs-lookup"><span data-stu-id="20c7c-161">You can make the graphs as simple or elaborate as you like, and add annotations, while staying connected to the model.</span></span>  
  
     <span data-ttu-id="20c7c-162">[segnaposto immagine]</span><span class="sxs-lookup"><span data-stu-id="20c7c-162">[ art placeholder]</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="20c7c-163">L'evidenziazione di nodi dipendenti e altre opzioni del menu di scelta rapida disponibili nelle versioni precedenti dei componenti aggiuntivi non funzionano in Office 2013.</span><span class="sxs-lookup"><span data-stu-id="20c7c-163">Highlighting of dependent nodes and other shortcut menu options that were available in previous versions of the Add-Ins do not work in Office 2013.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20c7c-164">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="20c7c-164">See Also</span></span>  
 [<span data-ttu-id="20c7c-165">Risoluzione dei problemi relativi ai diagrammi di data mining di Visio &#40;componenti aggiuntivi Data mining di SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="20c7c-165">Troubleshooting Visio Data Mining Diagrams &#40;SQL Server Data Mining Add-ins&#41;</span></span>](troubleshooting-visio-data-mining-diagrams-sql-server-data-mining-add-ins.md)  
  
  
