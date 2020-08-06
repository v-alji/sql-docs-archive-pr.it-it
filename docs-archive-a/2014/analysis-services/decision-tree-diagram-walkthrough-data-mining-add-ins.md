---
title: Procedura dettagliata relativa al diagramma dell'albero delle decisioni (componenti aggiuntivi Data mining) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- shapes, data mining
- diagram, decision tree
- Visio shapes, decision tree
- decision tree [data mining]
ms.assetid: 9566f6a2-c750-4125-ba5e-42c7251a78c7
author: minewiskan
ms.author: owend
ms.openlocfilehash: bbe54db1ab3d00d074917db770a9a731f884f49a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627523"
---
# <a name="decision-tree-diagram-walkthrough--data-mining-add-ins"></a><span data-ttu-id="6b4eb-102">Procedura dettagliata relativa al diagramma dell'albero delle decisioni (componenti aggiuntivi Data mining)</span><span class="sxs-lookup"><span data-stu-id="6b4eb-102">Decision Tree Diagram Walkthrough  (Data Mining Add-ins)</span></span>
  <span data-ttu-id="6b4eb-103">Se è stato creato un modello di albero delle decisioni, è possibile creare un diagramma personalizzato in Visio tramite la forma Albero delle decisioni o la forma Rete di dipendenze.</span><span class="sxs-lookup"><span data-stu-id="6b4eb-103">If you have created a decision tree model, you can create a customized diagram in Visio by using either the Decision Tree shape or the Dependency Network shape.</span></span> <span data-ttu-id="6b4eb-104">In questo argomento vengono descritte le personalizzazioni che è possibile eseguire utilizzando la forma **albero delle decisioni** e i controlli seguenti:</span><span class="sxs-lookup"><span data-stu-id="6b4eb-104">This topic describes the customizations you can perform using the **Decision Tree** shape and these controls:</span></span>  
  
-   <span data-ttu-id="6b4eb-105">Controlli di rendering per il diagramma dell'albero delle decisioni</span><span class="sxs-lookup"><span data-stu-id="6b4eb-105">Rendering controls for the decision tree diagram</span></span>  
  
     <span data-ttu-id="6b4eb-106">Queste opzioni fanno parte della **procedura guidata albero delle decisioni** avviata quando si rilascia una forma nell'area di lavoro di Visio.</span><span class="sxs-lookup"><span data-stu-id="6b4eb-106">These options are part of the **Decision Tree Wizard** that is launched when you drop a shape into the Visio workspace.</span></span>  
  
-   <span data-ttu-id="6b4eb-107">Barra degli strumenti **Layout data mining**</span><span class="sxs-lookup"><span data-stu-id="6b4eb-107">**Data Mining Layout** toolbar</span></span>  
  
     <span data-ttu-id="6b4eb-108">Queste opzioni vengono aggiunte all'area di lavoro di Visio per consentire di interagire con la forma.</span><span class="sxs-lookup"><span data-stu-id="6b4eb-108">These options are added to the Visio workspace to help you interact with the shape.</span></span>  
  
## <a name="build-a-decision-tree-diagram"></a><span data-ttu-id="6b4eb-109">Compilazione di un diagramma dell'albero delle decisioni</span><span class="sxs-lookup"><span data-stu-id="6b4eb-109">Build a Decision Tree Diagram</span></span>  
 <span data-ttu-id="6b4eb-110">È possibile rilasciare la forma albero delle decisioni nella pagina Visio per avviare la **procedura guidata forma di Visio** per l'albero delle decisioni e impostare le opzioni del diagramma.</span><span class="sxs-lookup"><span data-stu-id="6b4eb-110">You drop the Decision Tree shape onto the Visio page to launch the **Decision Tree Visio Shape Wizard** and set diagram options.</span></span>  
  
#### <a name="use-the-decision-tree-wizard"></a><span data-ttu-id="6b4eb-111">Utilizzo della Procedura guidata Albero delle decisioni</span><span class="sxs-lookup"><span data-stu-id="6b4eb-111">Use the Decision Tree Wizard</span></span>  
  
1.  <span data-ttu-id="6b4eb-112">Se non vengono visualizzate le **forme di data mining di Microsoft** nell'elenco **forme** , fare clic su **altre forme**, selezionare **Apri stencil**e aprire il modello dal percorso di installazione predefinito.</span><span class="sxs-lookup"><span data-stu-id="6b4eb-112">If you do not see **Microsoft Data Mining Shapes** in the **Shapes** list, click **More Shapes**, select **Open Stencil**, and open the template from the default installation location.</span></span>  
  
     <span data-ttu-id="6b4eb-113">\<drive>: \Program Files (X85) \Microsoft SQL Server 2012 DM Add-ins</span><span class="sxs-lookup"><span data-stu-id="6b4eb-113">\<drive>:\Program files (x85)\Microsoft SQL Server 2012 DM Add-Ins</span></span>  
  
2.  <span data-ttu-id="6b4eb-114">Trascinare la forma **albero delle decisioni** nella pagina.</span><span class="sxs-lookup"><span data-stu-id="6b4eb-114">Drag the **Decision Tree** shape onto the page.</span></span>  
  
3.  <span data-ttu-id="6b4eb-115">Nella pagina iniziale della **procedura guidata forma di Visio**per l'albero delle decisioni fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="6b4eb-115">On the welcome page of the **Decision Tree Visio Shape Wizard**, click **Next**.</span></span>  
  
4.  <span data-ttu-id="6b4eb-116">Nella pagina **Selezione origine dati** della **creazione guidata cluster**scegliere una connessione a un [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server in cui è presente il modello che si desidera visualizzare.</span><span class="sxs-lookup"><span data-stu-id="6b4eb-116">On the **Select a Data Source** page of the **Cluster Wizard**, choose a connection to an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server that has the model you want to visualize.</span></span>  
  
5.  <span data-ttu-id="6b4eb-117">Selezionare un modello di data mining appropriato e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="6b4eb-117">Select an appropriate mining model, and click **Next**.</span></span>  
  
     <span data-ttu-id="6b4eb-118">Questo tipo di diagramma supporta i modelli creati mediante l'algoritmo Decision Trees o Linear Regression.</span><span class="sxs-lookup"><span data-stu-id="6b4eb-118">This diagram type supports models created using the Decision Trees or Linear Regression algorithm.</span></span>  
  
6.  <span data-ttu-id="6b4eb-119">Nella pagina **Seleziona albero delle decisioni** scegliere un singolo albero da visualizzare.</span><span class="sxs-lookup"><span data-stu-id="6b4eb-119">On the **Select Decision Tree** page, choose an individual tree to display.</span></span>  
  
     <span data-ttu-id="6b4eb-120">Un albero modella le interazioni che portano a un risultato specifico che è stato modellato; Pertanto, anche se il modello contiene più risultati, è possibile visualizzare solo un albero alla volta.</span><span class="sxs-lookup"><span data-stu-id="6b4eb-120">A tree models the interactions that lead to a particular outcome you've modeled; therefore, even if your model contains multiple outcomes, you can display only one tree at a time.</span></span>  
  
7.  <span data-ttu-id="6b4eb-121">Nella finestra di dialogo **Seleziona albero delle decisioni** è inoltre possibile impostare queste opzioni di rendering:</span><span class="sxs-lookup"><span data-stu-id="6b4eb-121">In the **Select Decision Tree** dialog box, you can also set these rendering options:</span></span>  
  
     <span data-ttu-id="6b4eb-122">**Profondità massima di rendering**</span><span class="sxs-lookup"><span data-stu-id="6b4eb-122">**Maximum Rendering Depth**</span></span>  
     <span data-ttu-id="6b4eb-123">Utilizzare questa opzione per controllare il numero di nodi visualizzati.</span><span class="sxs-lookup"><span data-stu-id="6b4eb-123">Use this option to control how many nodes are displayed.</span></span>  
  
     <span data-ttu-id="6b4eb-124">Un albero delle decisioni potrebbe avere una gerarchia molto profonda, creando un diagramma che non rientra nella pagina.</span><span class="sxs-lookup"><span data-stu-id="6b4eb-124">A decision tree might go very deep, creating a diagram that does not fit on the page.</span></span> <span data-ttu-id="6b4eb-125">Utilizzare questo controllo per concentrarsi sui nodi più a sinistra, che sono i più importanti.</span><span class="sxs-lookup"><span data-stu-id="6b4eb-125">Use this control to focus on the leftmost nodes, which are more important.</span></span>  
  
     <span data-ttu-id="6b4eb-126">L'impostazione predefinita è tre livelli di nodi.</span><span class="sxs-lookup"><span data-stu-id="6b4eb-126">The default is three levels of nodes.</span></span>  
  
     <span data-ttu-id="6b4eb-127">**Selezionare il colore e il testo da visualizzare per i valori**</span><span class="sxs-lookup"><span data-stu-id="6b4eb-127">**Select color and display text for values**</span></span>  
     <span data-ttu-id="6b4eb-128">Scegliere il colore che rappresenterà ognuno dei risultati.</span><span class="sxs-lookup"><span data-stu-id="6b4eb-128">Choose the color that will represent each one of the outcomes.</span></span> <span data-ttu-id="6b4eb-129">Se non si specificano i colori, questi vengono automaticamente generati utilizzando i colori del tema del video correnti.</span><span class="sxs-lookup"><span data-stu-id="6b4eb-129">If you do not specify colors, they are automatically generated using the current video theme colors.</span></span>  
  
8.  <span data-ttu-id="6b4eb-130">Fare clic su **Avanzate** per personalizzare le opzioni seguenti per ogni nodo del diagramma dell'albero delle decisioni.</span><span class="sxs-lookup"><span data-stu-id="6b4eb-130">Click **Advanced** to customize the following options for each of the nodes in the decision tree diagram.</span></span>  
  
     <span data-ttu-id="6b4eb-131">**Variabile ombreggiatura** e **stato**</span><span class="sxs-lookup"><span data-stu-id="6b4eb-131">**Shading Variable** and **State**</span></span>  
     <span data-ttu-id="6b4eb-132">Scegliere il risultato di destinazione che si desidera visualizzare nel diagramma dell'albero.</span><span class="sxs-lookup"><span data-stu-id="6b4eb-132">Choose the target outcome that you want to show in the tree diagram.</span></span>  
  
     <span data-ttu-id="6b4eb-133">**Mostra istogramma**</span><span class="sxs-lookup"><span data-stu-id="6b4eb-133">**Show Histogram**</span></span>  
     <span data-ttu-id="6b4eb-134">Consente di aggiungere un grafico a ogni nodo in cui vengono visualizzate le regole che definiscono tale nodo.</span><span class="sxs-lookup"><span data-stu-id="6b4eb-134">Adds a chart to each node that shows the rules that define that node.</span></span>  
  
     <span data-ttu-id="6b4eb-135">**Mostra etichetta**</span><span class="sxs-lookup"><span data-stu-id="6b4eb-135">**Show Label**</span></span>  
     <span data-ttu-id="6b4eb-136">Consente di aggiungere i nomi di colonna all'istogramma.</span><span class="sxs-lookup"><span data-stu-id="6b4eb-136">Adds column names to the histogram.</span></span>  
  
     <span data-ttu-id="6b4eb-137">**Mostra probabilità**</span><span class="sxs-lookup"><span data-stu-id="6b4eb-137">**Show Probability**</span></span>  
     <span data-ttu-id="6b4eb-138">Consente di visualizzare la probabilità di ogni valore.</span><span class="sxs-lookup"><span data-stu-id="6b4eb-138">Displays the probability of each value.</span></span>  
  
     <span data-ttu-id="6b4eb-139">**Mostra supporto**</span><span class="sxs-lookup"><span data-stu-id="6b4eb-139">**Show Support**</span></span>  
     <span data-ttu-id="6b4eb-140">Consente di visualizzare il supporto per ogni valore.</span><span class="sxs-lookup"><span data-stu-id="6b4eb-140">Displays the support for each value.</span></span>  
  
     <span data-ttu-id="6b4eb-141">**Mostra piè di pagina**</span><span class="sxs-lookup"><span data-stu-id="6b4eb-141">**Show Footer**</span></span>  
     <span data-ttu-id="6b4eb-142">Consente di aggiungere un piè di pagina in cui vengono sommati tutti i valori visualizzati.</span><span class="sxs-lookup"><span data-stu-id="6b4eb-142">Adds a footer that sums all displayed values.</span></span>  
  
     <span data-ttu-id="6b4eb-143">**Mostra intestazione**</span><span class="sxs-lookup"><span data-stu-id="6b4eb-143">**Show Header**</span></span>  
     <span data-ttu-id="6b4eb-144">Consente di aggiungere intestazioni di colonna.</span><span class="sxs-lookup"><span data-stu-id="6b4eb-144">Adds column headings.</span></span>  
  
     <span data-ttu-id="6b4eb-145">**Mostra stati con supporto zero**</span><span class="sxs-lookup"><span data-stu-id="6b4eb-145">**Show states with zero support**</span></span>  
     <span data-ttu-id="6b4eb-146">Consente di visualizzare i valori mancanti.</span><span class="sxs-lookup"><span data-stu-id="6b4eb-146">Lets you display missing values.</span></span>  
  
9. <span data-ttu-id="6b4eb-147">Fare clic su **fine** per creare il grafico.</span><span class="sxs-lookup"><span data-stu-id="6b4eb-147">Click **Finish** to create the graph.</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="6b4eb-148">In alcuni ambienti, i connettori nel grafico potrebbero non riuscire a eseguire il rendering in Office 2013.</span><span class="sxs-lookup"><span data-stu-id="6b4eb-148">In some environments, connectors in the chart might fail to render in Office 2013.</span></span>  
  
## <a name="explore-and-modify-the-finished-diagram"></a><span data-ttu-id="6b4eb-149">Esplorazione e modifica del diagramma completato</span><span class="sxs-lookup"><span data-stu-id="6b4eb-149">Explore and Modify the Finished Diagram</span></span>  
 <span data-ttu-id="6b4eb-150">Dopo aver completato la **procedura guidata forma di Visio**per l'albero delle decisioni, in Visio viene creato un diagramma ad albero nella pagina che visualizza graficamente le regole che portano al risultato stimato.</span><span class="sxs-lookup"><span data-stu-id="6b4eb-150">After you have completed the **Decision Tree Visio Shape Wizard**, Visio creates a tree diagram on the page that graphically displays the rules that lead to the predicted outcome.</span></span>  
  
 <span data-ttu-id="6b4eb-151">È possibile continuare a modificare la forma utilizzando i seguenti controlli per i diagrammi dell'albero delle decisioni:</span><span class="sxs-lookup"><span data-stu-id="6b4eb-151">You can continue to modify the shape by using the following controls for decision tree diagrams:</span></span>  
  
#### <a name="using-the-decision-tree-option-menus"></a><span data-ttu-id="6b4eb-152">Utilizzo dei menu delle opzioni dell'albero delle decisioni</span><span class="sxs-lookup"><span data-stu-id="6b4eb-152">Using the decision tree option menus</span></span>  
  
1.  <span data-ttu-id="6b4eb-153">Fare clic sulla barra multifunzione **componenti** aggiuntivi e quindi visualizzare una delle barre degli strumenti personalizzate utilizzate per l'utilizzo dei diagrammi data mining:</span><span class="sxs-lookup"><span data-stu-id="6b4eb-153">Click the **Add-Ins** ribbon, and then display one of the custom toolbars used for working with data mining diagrams:</span></span>  
  
     <span data-ttu-id="6b4eb-154">**Layout**</span><span class="sxs-lookup"><span data-stu-id="6b4eb-154">**Layout**</span></span>  
     <span data-ttu-id="6b4eb-155">Consente di ottimizzare la disposizione dell'albero da adattare nella pagina corrente.</span><span class="sxs-lookup"><span data-stu-id="6b4eb-155">Optimizes the arrangement of the tree to fit the current page.</span></span>  
  
     <span data-ttu-id="6b4eb-156">**Ridimensiona pagina**</span><span class="sxs-lookup"><span data-stu-id="6b4eb-156">**Resize Page**</span></span>  
     <span data-ttu-id="6b4eb-157">Questo controllo è destinato alle versioni HTML precedenti.</span><span class="sxs-lookup"><span data-stu-id="6b4eb-157">This control was intended for earlier HTML versions.</span></span> <span data-ttu-id="6b4eb-158">Utilizzare invece i controlli per il ridimensionamento della pagina di Visio.</span><span class="sxs-lookup"><span data-stu-id="6b4eb-158">Use the Visio page resizing controls instead,</span></span>  
  
     <span data-ttu-id="6b4eb-159">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="6b4eb-159">**Description**</span></span>  
     <span data-ttu-id="6b4eb-160">Quando è selezionato un nodo dell'albero, fare clic su questa opzione per visualizzare i dettagli sui case nel nodo.</span><span class="sxs-lookup"><span data-stu-id="6b4eb-160">When a node of the tree is selected, click this option to display details about the cases in the node.</span></span>  
  
2.  <span data-ttu-id="6b4eb-161">Utilizzare l'opzione **nuova pagina layout** nella barra multifunzione di **progettazione** di Visio per provare layout di struttura ad albero diversi.</span><span class="sxs-lookup"><span data-stu-id="6b4eb-161">Use the **Re-Layout Page** option in the Visio **Design** ribbon to experiment with different tree layouts.</span></span>  
  
3.  <span data-ttu-id="6b4eb-162">Utilizzare l'opzione **connettori** nella scheda **progettazione** per modificare i connettori utilizzati tra i nodi dell'albero.</span><span class="sxs-lookup"><span data-stu-id="6b4eb-162">Use the **Connectors** option on the **Design** tab to change the connectors used between nodes in the tree.</span></span>  
  
4.  <span data-ttu-id="6b4eb-163">Utilizzare il controllo **Pan e zoom** , nell'area **riquadro attività** della barra multifunzione **visualizzazione** Visio, per concentrarsi su una particolare area del diagramma.</span><span class="sxs-lookup"><span data-stu-id="6b4eb-163">Use the **Pan and Zoom** control, in the **Task Pane** area of the Visio **View** ribbon, to focus on a particular area of the diagram.</span></span>  
  
5.  <span data-ttu-id="6b4eb-164">Fare clic con il pulsante destro del mouse su qualsiasi nodo dell'albero e scegliere tra queste opzioni del menu di scelta rapida specifiche dei diagrammi dell'albero delle decisioni:</span><span class="sxs-lookup"><span data-stu-id="6b4eb-164">Right-click any node in the tree, and choose from these shortcut menu options specific to decision tree diagrams:</span></span>  
  
     <span data-ttu-id="6b4eb-165">**Ottimizza layout di pagina**</span><span class="sxs-lookup"><span data-stu-id="6b4eb-165">**Improve Page Layout**</span></span>  
     <span data-ttu-id="6b4eb-166">Consente di ripartire uniformemente i nodi nella pagina, nonché di modificare la visualizzazione della pagina in modo da includere tutti i nodi.</span><span class="sxs-lookup"><span data-stu-id="6b4eb-166">Distributes the nodes evenly on the page and adjusts the page view to see all nodes.</span></span>  
  
     <span data-ttu-id="6b4eb-167">**Sposta figli in una nuova pagina**</span><span class="sxs-lookup"><span data-stu-id="6b4eb-167">**Move Children to New Page**</span></span>  
     <span data-ttu-id="6b4eb-168">Consente di spostare in una nuova pagina i nodi figlio del nodo attualmente selezionato.</span><span class="sxs-lookup"><span data-stu-id="6b4eb-168">Moves the children of the currently selected node to a new page.</span></span>  
  
     <span data-ttu-id="6b4eb-169">**Comprimi nodi figlio**</span><span class="sxs-lookup"><span data-stu-id="6b4eb-169">**Collapse Child Nodes**</span></span>  
     <span data-ttu-id="6b4eb-170">Consente di nascondere i nodi figlio del nodo attualmente selezionato.</span><span class="sxs-lookup"><span data-stu-id="6b4eb-170">Hides the children of the currently selected node.</span></span>  
  
     <span data-ttu-id="6b4eb-171">**Espandi nodi figlio**</span><span class="sxs-lookup"><span data-stu-id="6b4eb-171">**Expand Child Nodes**</span></span>  
     <span data-ttu-id="6b4eb-172">Consente di visualizzare i nodi figlio del nodo attualmente selezionato.</span><span class="sxs-lookup"><span data-stu-id="6b4eb-172">Displays the children of the currently selected node.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b4eb-173">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6b4eb-173">See Also</span></span>  
 [<span data-ttu-id="6b4eb-174">Risoluzione dei problemi relativi ai diagrammi di data mining di Visio &#40;componenti aggiuntivi Data mining di SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="6b4eb-174">Troubleshooting Visio Data Mining Diagrams &#40;SQL Server Data Mining Add-ins&#41;</span></span>](troubleshooting-visio-data-mining-diagrams-sql-server-data-mining-add-ins.md)  
  
  
