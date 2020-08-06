---
title: Procedura dettagliata relativa al diagramma dei cluster (componenti aggiuntivi Data mining) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Visio shapes, cluster
- diagram, cluster
- shapes, data mining
- shapes, cluster
- data mining layout toolbar
ms.assetid: 761bef6a-37d4-4b19-944e-f2aadc75a242
author: minewiskan
ms.author: owend
ms.openlocfilehash: 44ee8cce3cd2498d765c9b69e7f352b49cb0f115
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626394"
---
# <a name="cluster-diagram-walkthrough-data-mining-add-ins"></a><span data-ttu-id="e5892-102">Descrizione dettagliata del diagramma cluster (componenti aggiuntivi Data mining)</span><span class="sxs-lookup"><span data-stu-id="e5892-102">Cluster Diagram Walkthrough (Data Mining Add-ins)</span></span>
  <span data-ttu-id="e5892-103">Dopo aver creato un modello di clustering, è possibile importarlo in Visio utilizzando la forma **cluster** e quindi continuare a personalizzare e migliorare il layout.</span><span class="sxs-lookup"><span data-stu-id="e5892-103">After you have created a clustering model, you can import it into Visio using the **Cluster** shape and then continue to customize and enhance the layout.</span></span> <span data-ttu-id="e5892-104">Nelle **forme di data mining per Visio** sono inclusi i seguenti controlli personalizzati per l'utilizzo di diagrammi data mining:</span><span class="sxs-lookup"><span data-stu-id="e5892-104">The **Data Mining Shapes for Visio** include the following custom controls for working with data mining diagrams:</span></span>  
  
-   <span data-ttu-id="e5892-105">Controlli di rendering per il diagramma dei cluster</span><span class="sxs-lookup"><span data-stu-id="e5892-105">Rendering controls for the cluster diagram</span></span>  
  
     <span data-ttu-id="e5892-106">Queste opzioni fanno parte della **procedura guidata cluster** avviata quando si rilascia una forma nell'area di lavoro di Visio.</span><span class="sxs-lookup"><span data-stu-id="e5892-106">These options are part of the **Cluster Wizard** that is launched when you drop a shape into the Visio workspace.</span></span>  
  
-   <span data-ttu-id="e5892-107">Barra degli strumenti **Layout data mining**</span><span class="sxs-lookup"><span data-stu-id="e5892-107">**Data Mining Layout** toolbar</span></span>  
  
     <span data-ttu-id="e5892-108">Queste opzioni vengono aggiunte all'area di lavoro di Visio per consentire di interagire con la forma di data mining.</span><span class="sxs-lookup"><span data-stu-id="e5892-108">These options are added to the Visio workspace to help you interact with the data mining shape.</span></span> <span data-ttu-id="e5892-109">Le opzioni variano a seconda del tipo di modello di data mining utilizzato.</span><span class="sxs-lookup"><span data-stu-id="e5892-109">The options are different depending on which type of data mining model you are using.</span></span>  
  
## <a name="build-a-cluster-diagram"></a><span data-ttu-id="e5892-110">Creazione del diagramma di un cluster</span><span class="sxs-lookup"><span data-stu-id="e5892-110">Build a Cluster Diagram</span></span>  
 <span data-ttu-id="e5892-111">In questa procedura dettagliata viene illustrato come creare e personalizzare un diagramma di clustering in Visio.</span><span class="sxs-lookup"><span data-stu-id="e5892-111">This walkthrough demonstrates how to build and customize a clustering diagram in Visio.</span></span>  
  
 <span data-ttu-id="e5892-112">Per proseguire, è necessario avere un modello di clustering già disponibile.</span><span class="sxs-lookup"><span data-stu-id="e5892-112">To follow along, you should have a clustering model already available.</span></span> <span data-ttu-id="e5892-113">Se non si dispone di un modello, utilizzare la [procedura guidata Cluster &#40;componenti aggiuntivi Data mining per la procedura guidata&#41;di Excel](cluster-wizard-data-mining-add-ins-for-excel.md) e creare un modello utilizzando il set di dati di training nella cartella di lavoro di esempio, utilizzando tutte le impostazioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="e5892-113">If you do not have a model, use the [Cluster Wizard &#40;Data Mining Add-ins for Excel&#41;](cluster-wizard-data-mining-add-ins-for-excel.md) wizard and create a model using the Training data set in the sample workbook, using all the defaults.</span></span>  
  
#### <a name="use-the-cluster-visio-shape-wizard"></a><span data-ttu-id="e5892-114">Utilizzo della Procedura guidata Forma di Visio per cluster</span><span class="sxs-lookup"><span data-stu-id="e5892-114">Use the Cluster Visio Shape Wizard</span></span>  
  
1.  <span data-ttu-id="e5892-115">Se non vengono visualizzate le **forme di data mining di Microsoft** nell'elenco **forme** , fare clic su **altre forme**, selezionare **Apri stencil**e aprire il modello dal percorso di installazione predefinito.</span><span class="sxs-lookup"><span data-stu-id="e5892-115">If you do not see **Microsoft Data Mining Shapes** in the **Shapes** list, click **More Shapes**, select **Open Stencil**, and open the template from the default installation location.</span></span>  
  
     <span data-ttu-id="e5892-116">\<drive>: \Programmi\Microsoft SQL Server 2012 DM Add-ins</span><span class="sxs-lookup"><span data-stu-id="e5892-116">\<drive>:\Program files\Microsoft SQL Server 2012 DM Add-Ins</span></span>  
  
2.  <span data-ttu-id="e5892-117">Trascinare la forma **cluster** nella pagina.</span><span class="sxs-lookup"><span data-stu-id="e5892-117">Drag the **Cluster** shape onto the page.</span></span>  
  
3.  <span data-ttu-id="e5892-118">Nella pagina iniziale della **procedura guidata forma di Visio per cluster**fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="e5892-118">On the welcome page of the **Cluster Visio Shape Wizard**, click **Next**.</span></span>  
  
4.  <span data-ttu-id="e5892-119">Nella pagina **Selezione origine dati** della **creazione guidata cluster**scegliere una connessione a un [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server contenente i modelli di data mining che si desidera visualizzare.</span><span class="sxs-lookup"><span data-stu-id="e5892-119">On the **Select a Data Source** page of the **Cluster Wizard**, choose a connection to an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server that contains the data mining models you want to visualize.</span></span>  
  
5.  <span data-ttu-id="e5892-120">Selezionare un modello di data mining appropriato e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="e5892-120">Select an appropriate mining model, and click **Next**.</span></span>  
  
     <span data-ttu-id="e5892-121">Per assicurarsi di scegliere un modello di clustering, esaminare la descrizione nel riquadro **Proprietà** .</span><span class="sxs-lookup"><span data-stu-id="e5892-121">To make sure you choose a clustering model, review the description in the **Properties** pane.</span></span>  
  
6.  <span data-ttu-id="e5892-122">Se la connessione ha esito positivo, nella pagina **Opzioni per diagramma cluster**si decide il tipo di diagramma del cluster da includere nella presentazione di Visio:</span><span class="sxs-lookup"><span data-stu-id="e5892-122">If the connection is successful, on the page, **Options for cluster diagram**, you decide which type of cluster diagram to include in your Visio presentation:</span></span>  
  
     <span data-ttu-id="e5892-123">**Mostra solo forme del cluster**</span><span class="sxs-lookup"><span data-stu-id="e5892-123">**Show cluster shapes only**</span></span>  
     <span data-ttu-id="e5892-124">Questa opzione consente di creare un semplice diagramma dei cluster, dove ogni cluster è rappresentato da un rettangolo o un'altra forma scelta.</span><span class="sxs-lookup"><span data-stu-id="e5892-124">This option creates a simple cluster diagram, with each cluster represented by a rectangle or other shape you choose</span></span>  
  
     <span data-ttu-id="e5892-125">**Mostra cluster con grafico delle caratteristiche**</span><span class="sxs-lookup"><span data-stu-id="e5892-125">**Show clusters with characteristics chart**</span></span>  
     <span data-ttu-id="e5892-126">Questa opzione consente di creare lo stesso grafico precedente, ma all'interno delle forme sono presenti istogrammi in cui vengono descritte le caratteristiche del cluster.</span><span class="sxs-lookup"><span data-stu-id="e5892-126">This option creates the same chart as above, but inside the shapes are histograms that describe the characteristics of the cluster.</span></span>  
  
     <span data-ttu-id="e5892-127">![Esempio di grafico delle caratteristiche del cluster in Visio](media/dm13-visio-cluster-samplecharshape.gif "Esempio di grafico delle caratteristiche del cluster in Visio")</span><span class="sxs-lookup"><span data-stu-id="e5892-127">![Example of cluster characteristics chart in Visio](media/dm13-visio-cluster-samplecharshape.gif "Example of cluster characteristics chart in Visio")</span></span>  
  
     <span data-ttu-id="e5892-128">**Mostra cluster con grafico analisi discriminante**</span><span class="sxs-lookup"><span data-stu-id="e5892-128">**Show clusters with discrimination chart**</span></span>  
     <span data-ttu-id="e5892-129">Questa opzione consente di creare lo stesso grafico del diagramma dei cluster, ma anche di elencare le caratteristiche del cluster corrente che lo distinguono maggiormente dagli altri.</span><span class="sxs-lookup"><span data-stu-id="e5892-129">This option creates the same chart as the cluster diagram, but instead lists the characteristics of the current cluster that most strongly distinguish it from other clusters.</span></span>  
  
     <span data-ttu-id="e5892-130">È possibile passare a un altro tipo di grafico dopo che è stato creato il diagramma tramite la procedura guidata, facendo clic con il pulsante destro del mouse su un cluster e selezionando un nuovo tipo di grafico.</span><span class="sxs-lookup"><span data-stu-id="e5892-130">You can switch to another chart type after the wizard has built the diagram, by right-clicking a cluster and selecting a new chart type.</span></span> <span data-ttu-id="e5892-131">Per il momento, scegliere l'opzione **Mostra cluster con grafico delle caratteristiche**.</span><span class="sxs-lookup"><span data-stu-id="e5892-131">For now, choose the option, **Show clusters with characteristics chart**.</span></span>  
  
7.  <span data-ttu-id="e5892-132">Lasciare l'opzione, **numero di righe nel grafico**, come 5.</span><span class="sxs-lookup"><span data-stu-id="e5892-132">Leave the option, **Number of rows in the chart**, as 5.</span></span>  
  
     <span data-ttu-id="e5892-133">Questa opzione non consente di modificare il numero di cluster nel modello. limita semplicemente il numero di attributi che possono essere visualizzati come funzionalità di ogni cluster.</span><span class="sxs-lookup"><span data-stu-id="e5892-133">This option doesn't change the number of clusters in the model; it simply limits the number of attributes that can be displayed as features of each cluster.</span></span>  
  
     <span data-ttu-id="e5892-134">Tuttavia, l'opzione funge da filtro sui dati del grafico, pertanto non è possibile aumentare il numero di elementi in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="e5892-134">However, the option acts as a filter on the chart data, so you can't increase the number of items later.</span></span>  
  
8.  <span data-ttu-id="e5892-135">Fare clic su **Avanzate**.</span><span class="sxs-lookup"><span data-stu-id="e5892-135">Click **Advanced**.</span></span>  
  
     <span data-ttu-id="e5892-136">La finestra di dialogo **Opzioni cluster** consente di personalizzare l'aspetto visivo delle forme utilizzate nel diagramma.</span><span class="sxs-lookup"><span data-stu-id="e5892-136">The **Cluster Options** dialog box is where you customize the visual appearance of shapes used in the diagram.</span></span> <span data-ttu-id="e5892-137">È possibile modificare i colori utilizzati nel grafico e la forma utilizzata per i cluster.</span><span class="sxs-lookup"><span data-stu-id="e5892-137">You can change the colors used in the graph, and the shape used for clusters.</span></span>  
  
     <span data-ttu-id="e5892-138">Il controllo **Variabile ombreggiatura** non funziona in Office 2013.</span><span class="sxs-lookup"><span data-stu-id="e5892-138">The **Shading Variable** control does not work in Office 2013.</span></span>  
  
     <span data-ttu-id="e5892-139">![Fare clic su Avanzate per scegliere i colori delle forme](media/dm13-visio-clusteroptions-advanced.gif "Fare clic su Avanzate per scegliere i colori delle forme")</span><span class="sxs-lookup"><span data-stu-id="e5892-139">![click Advanced to choose shape colors](media/dm13-visio-clusteroptions-advanced.gif "click Advanced to choose shape colors")</span></span>  
  
     <span data-ttu-id="e5892-140">**Suggerimento:** Alcuni colori possono essere modificati in un secondo momento usando i temi di Visio e i controlli di modifica della forma.</span><span class="sxs-lookup"><span data-stu-id="e5892-140">**Tip:** Some colors can be altered later by using Visio themes and shape editing controls.</span></span> <span data-ttu-id="e5892-141">Tuttavia, i temi di Visio sostituiranno anche alcune di queste selezioni dei colori, pertanto è consigliabile iniziare con colori predefiniti e gradualmente applicare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="e5892-141">However, Visio themes will also override some of these color selections, so we recommend starting with the default colors and gradually applying changes.</span></span>  
  
9. <span data-ttu-id="e5892-142">Fare clic su **fine** per creare il grafico.</span><span class="sxs-lookup"><span data-stu-id="e5892-142">Click **Finish** to create the graph.</span></span>  
  
     <span data-ttu-id="e5892-143">La procedura guidata consente di recuperare le informazioni dal modello di data mining, eseguire il rendering delle forme e popolare ciascun cluster con attributi e valori.</span><span class="sxs-lookup"><span data-stu-id="e5892-143">The wizard retrieves information from the data mining model, renders the shapes, and populates each cluster with attributes and values.</span></span>  
  
     <span data-ttu-id="e5892-144">![Rete di dipendenze](media/dm13-visiodepnet-defaultgraph.gif "Rete di dipendenze")</span><span class="sxs-lookup"><span data-stu-id="e5892-144">![a dependency network](media/dm13-visiodepnet-defaultgraph.gif "a dependency network")</span></span>  
  
## <a name="explore-and-modify-the-finished-diagram"></a><span data-ttu-id="e5892-145">Esplorazione e modifica del diagramma completato</span><span class="sxs-lookup"><span data-stu-id="e5892-145">Explore and Modify the Finished Diagram</span></span>  
 <span data-ttu-id="e5892-146">Dopo che il diagramma è stato completato, è possibile continuare a personalizzare l'aspetto utilizzando i controlli di Visio, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="e5892-146">After the diagram is complete, you can continue to customize the appearance using the Visio controls, as shown in the following example.</span></span>  
  
 <span data-ttu-id="e5892-147">![Diagramma dei cluster personalizzato mediante Visio](media/dm13-visio-clustercomplete1.gif "Diagramma dei cluster personalizzato mediante Visio")</span><span class="sxs-lookup"><span data-stu-id="e5892-147">![cluster diagram customized using Visio](media/dm13-visio-clustercomplete1.gif "cluster diagram customized using Visio")</span></span>  
  
 <span data-ttu-id="e5892-148">Tutte le forme di base del cluster vengono generate dalla procedura guidata; utilizzare gli strumenti seguenti per aggiornare e personalizzare il diagramma:</span><span class="sxs-lookup"><span data-stu-id="e5892-148">All of the basic cluster shapes are generated by the wizard; use the following tools to update and personalize the diagram:</span></span>  
  
1.  <span data-ttu-id="e5892-149">Trascinare il dispositivo di scorrimento nel controllo delle **Opzioni del cluster** per filtrare le relazioni più vulnerabili e semplificare il diagramma.</span><span class="sxs-lookup"><span data-stu-id="e5892-149">Drag the slider in the **Cluster Options** control, to filter out weaker relationships and simplify the diagram.</span></span>  
  
2.  <span data-ttu-id="e5892-150">Usare l'opzione **rilayout della pagina** di Visio per provare i diversi layout del cluster.</span><span class="sxs-lookup"><span data-stu-id="e5892-150">Use the Visio **Re-Layout Page** option to experiment with different cluster layouts.</span></span>  
  
3.  <span data-ttu-id="e5892-151">Utilizzare l'opzione **connettori** nella scheda **progettazione** per modificare lo stile del connettore in modo da evitare che le linee attraversino i cluster.</span><span class="sxs-lookup"><span data-stu-id="e5892-151">Use the **Connectors** option on the **Design** tab to change the connector style to keep lines from crossing over clusters.</span></span>  
  
4.  <span data-ttu-id="e5892-152">Fare clic sulla barra multifunzione **componenti** aggiuntivi e quindi visualizzare una delle barre degli strumenti personalizzate utilizzate per l'utilizzo dei diagrammi data mining:</span><span class="sxs-lookup"><span data-stu-id="e5892-152">Click the **Add-Ins** ribbon, and then display one of the custom toolbars used for working with data mining diagrams:</span></span>  
  
     <span data-ttu-id="e5892-153">**Layout**</span><span class="sxs-lookup"><span data-stu-id="e5892-153">**Layout**</span></span>  
     <span data-ttu-id="e5892-154">Consente di ottimizzare la disposizione dei cluster da adattare nella pagina corrente.</span><span class="sxs-lookup"><span data-stu-id="e5892-154">Optimizes the arrangement of clusters to fit in the current page.</span></span>  
  
     <span data-ttu-id="e5892-155">**Ridimensiona pagina**</span><span class="sxs-lookup"><span data-stu-id="e5892-155">**Resize Page**</span></span>  
     <span data-ttu-id="e5892-156">Questo controllo è destinato alle versioni HTML precedenti.</span><span class="sxs-lookup"><span data-stu-id="e5892-156">This control was intended for earlier HTML versions.</span></span> <span data-ttu-id="e5892-157">Utilizzare invece i controlli per il ridimensionamento della pagina di Visio.</span><span class="sxs-lookup"><span data-stu-id="e5892-157">Use the Visio page resizing controls instead.</span></span>  
  
     <span data-ttu-id="e5892-158">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="e5892-158">**Description**</span></span>  
     <span data-ttu-id="e5892-159">Se viene selezionato un cluster, fare clic su questa opzione per visualizzare i dettagli sul cluster.</span><span class="sxs-lookup"><span data-stu-id="e5892-159">If a cluster is selected, click this option to display details about the cluster.</span></span>  
  
     <span data-ttu-id="e5892-160">![Fare clic su Descrizione per informazioni dettagliate sul cluster](media/dm13-visio-cluster-description-control.gif "Fare clic su Descrizione per informazioni dettagliate sul cluster")</span><span class="sxs-lookup"><span data-stu-id="e5892-160">![click Description to get details about the cluster](media/dm13-visio-cluster-description-control.gif "click Description to get details about the cluster")</span></span>  
  
     <span data-ttu-id="e5892-161">**Livello attendibilità bordo**</span><span class="sxs-lookup"><span data-stu-id="e5892-161">**Edge Strength**</span></span>  
     <span data-ttu-id="e5892-162">Consente di visualizzare i punteggi di confidenza sulle linee che connettono i cluster.</span><span class="sxs-lookup"><span data-stu-id="e5892-162">Displays confidence scores on the lines connecting clusters.</span></span>  
  
     <span data-ttu-id="e5892-163">Tuttavia, se si applica una qualsiasi formattazione speciale diversa da quella predefinita generata dalla procedura guidata, inclusi alcuni sfondi, questi numeri potrebbero non essere visibili.</span><span class="sxs-lookup"><span data-stu-id="e5892-163">However, if you apply any special formatting other than the default generated by the wizard, including some backgrounds, these numbers might not be visible.</span></span>  
  
     <span data-ttu-id="e5892-164">**Dispositivo di scorrimento**</span><span class="sxs-lookup"><span data-stu-id="e5892-164">**Slider**</span></span>  
     <span data-ttu-id="e5892-165">Consente di filtrare le linee tra i cluster.</span><span class="sxs-lookup"><span data-stu-id="e5892-165">Filters the lines between clusters.</span></span> <span data-ttu-id="e5892-166">Spostando il dispositivo di scorrimento verso l'alto vengono rimosse tutte le associazioni tranne quelle più importanti.</span><span class="sxs-lookup"><span data-stu-id="e5892-166">Moving the slider up removes all but the most important associations.</span></span>  
  
     <span data-ttu-id="e5892-167">**Ombreggiatura**</span><span class="sxs-lookup"><span data-stu-id="e5892-167">**Shading**</span></span>  
     <span data-ttu-id="e5892-168">Questo controllo non funziona in Office 2013.</span><span class="sxs-lookup"><span data-stu-id="e5892-168">This control does not work in Office 2013.</span></span>  
  
5.  <span data-ttu-id="e5892-169">Utilizzare il controllo **Pan e zoom** , nell'area **riquadro attività** della barra multifunzione **visualizzazione** Visio, per concentrarsi su un set di cluster e spostarsi intorno al diagramma.</span><span class="sxs-lookup"><span data-stu-id="e5892-169">Use the **Pan and Zoom** control, in the **Task Pane** area of the Visio **View** ribbon, to focus on a set of clusters and move around the diagram.</span></span>  
  
6.  <span data-ttu-id="e5892-170">Fare clic con il pulsante destro del mouse su un qualsiasi cluster per visualizzare le opzioni specifiche della forma del cluster:</span><span class="sxs-lookup"><span data-stu-id="e5892-170">Right-click any cluster to see options specific to the cluster shape:</span></span>  
  
    -   <span data-ttu-id="e5892-171">Modificare lo stile del grafico.</span><span class="sxs-lookup"><span data-stu-id="e5892-171">Change the chart style.</span></span>  
  
    -   <span data-ttu-id="e5892-172">Aggiungere un grafico delle caratteristiche del cluster.</span><span class="sxs-lookup"><span data-stu-id="e5892-172">Add a cluster characteristics chart.</span></span>  
  
    -   <span data-ttu-id="e5892-173">Aggiungere un grafico dell'analisi discriminante del cluster.</span><span class="sxs-lookup"><span data-stu-id="e5892-173">Add a cluster discrimination chart.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5892-174">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e5892-174">See Also</span></span>  
 [<span data-ttu-id="e5892-175">Risoluzione dei problemi relativi ai diagrammi di data mining di Visio &#40;componenti aggiuntivi Data mining di SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e5892-175">Troubleshooting Visio Data Mining Diagrams &#40;SQL Server Data Mining Add-ins&#41;</span></span>](troubleshooting-visio-data-mining-diagrams-sql-server-data-mining-add-ins.md)  
  
  
