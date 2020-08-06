---
title: 'Esercitazione: Aggiungere un grafico a torta al report (Generatore report) | Microsoft Docs'
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: eaadf7bf-c312-428a-b214-0a1fbf959c3f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 318370b185dcd75a8c3c54be49c47756bad5f3c9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720963"
---
# <a name="tutorial-add-a-pie-chart-to-your-report-report-builder"></a><span data-ttu-id="1e0e5-102">Esercitazione: Aggiungere un grafico a torta al report (Generatore report)</span><span class="sxs-lookup"><span data-stu-id="1e0e5-102">Tutorial: Add a Pie Chart to Your Report (Report Builder)</span></span>
  <span data-ttu-id="1e0e5-103">Nei grafici a torta e in quelli ad anello i dati vengono visualizzati come percentuali rispetto a un valore intero.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-103">Pie charts and doughnut charts display data as a proportion of the whole.</span></span> <span data-ttu-id="1e0e5-104">I grafici a torta vengono utilizzati principalmente per eseguire confronti tra gruppi.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-104">Pie charts are most commonly used to make comparisons between groups.</span></span> <span data-ttu-id="1e0e5-105">I grafici a torta e ad anello, insieme ai grafici a piramide e a imbuto, costituiscono un gruppo di grafici noti come grafici con forme.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-105">Pie and doughnut charts, along with pyramid and funnel charts, constitute a group of charts known as shape charts.</span></span> <span data-ttu-id="1e0e5-106">I grafici con forme non includono assi.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-106">Shape charts have no axes.</span></span> <span data-ttu-id="1e0e5-107">Quando un campo numerico viene inserito in un grafico con forme, viene calcolata la percentuale di ogni valore rispetto al totale.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-107">When a numeric field is dropped on a shape chart, the chart calculates the percentage of each value to the total.</span></span>  
  
 <span data-ttu-id="1e0e5-108">Se sono presenti troppi punti dati su un grafico a torta, le etichette dei punti dati potrebbero essere difficili da leggere.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-108">If there are too many data points on a pie chart, your data point labels might be too crowded to read.</span></span> <span data-ttu-id="1e0e5-109">In questo caso è preferibile utilizzare un grafico a linee.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-109">In that case, consider using a line chart.</span></span> <span data-ttu-id="1e0e5-110">Utilizzare grafici a torta solo dopo avere aggregato i dati in pochi punti dati.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-110">Consider using pie charts only after you have aggregated your data into a few data points.</span></span>  
  
 <span data-ttu-id="1e0e5-111">Nell'illustrazione seguente viene mostrato il grafico a torta che verrà creato.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-111">The following illustration shows the pie chart you will create.</span></span>  
  
 <span data-ttu-id="1e0e5-112">![rs_TutorialPieChartConcave](../../2014/tutorials/media/rs-tutorialpiechartconcave.gif "rs_TutorialPieChartConcave")</span><span class="sxs-lookup"><span data-stu-id="1e0e5-112">![rs_TutorialPieChartConcave](../../2014/tutorials/media/rs-tutorialpiechartconcave.gif "rs_TutorialPieChartConcave")</span></span>  
  
##  <a name="what-you-will-learn"></a><a name="BackToTop"></a><span data-ttu-id="1e0e5-113">Cosa si apprenderà</span><span class="sxs-lookup"><span data-stu-id="1e0e5-113">What You Will Learn</span></span>  
 <span data-ttu-id="1e0e5-114">In questa esercitazione verranno illustrate le procedure per:</span><span class="sxs-lookup"><span data-stu-id="1e0e5-114">In this tutorial, you will learn how to:</span></span>  
  
1.  [<span data-ttu-id="1e0e5-115">Creare un grafico a torta da Creazione guidata grafico</span><span class="sxs-lookup"><span data-stu-id="1e0e5-115">Create a Pie Chart from the Chart Wizard</span></span>](#Chart)  
  
2.  [<span data-ttu-id="1e0e5-116">Scegliere il tipo di grafico</span><span class="sxs-lookup"><span data-stu-id="1e0e5-116">Choose the Chart Type</span></span>](#ChartType)  
  
3.  [<span data-ttu-id="1e0e5-117">Visualizzare percentuali in ogni sezione</span><span class="sxs-lookup"><span data-stu-id="1e0e5-117">Display Percentages in Each Slice</span></span>](#Percentages)  
  
4.  [<span data-ttu-id="1e0e5-118">Combinare le piccole sezioni in una sezione</span><span class="sxs-lookup"><span data-stu-id="1e0e5-118">Combine Small Slices into One Slice</span></span>](#CombineSlices)  
  
5.  [<span data-ttu-id="1e0e5-119">Personalizzare l'effetto di disegno</span><span class="sxs-lookup"><span data-stu-id="1e0e5-119">Customize the Drawing Effect</span></span>](#DrawingEffect)  
  
6.  [<span data-ttu-id="1e0e5-120">Aggiungere un titolo al report</span><span class="sxs-lookup"><span data-stu-id="1e0e5-120">Add a Report Title</span></span>](#Title)  
  
7.  [<span data-ttu-id="1e0e5-121">Salva il report</span><span class="sxs-lookup"><span data-stu-id="1e0e5-121">Save the Report</span></span>](#Save)  
  
> [!NOTE]  
>  <span data-ttu-id="1e0e5-122">In questa esercitazione, i passaggi per la procedura guidata sono consolidati in due procedure.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-122">In this tutorial, the steps for the wizard are consolidated into two procedures.</span></span> <span data-ttu-id="1e0e5-123">Per istruzioni dettagliate su come selezionare un server di report, aggiungere un'origine dati e un set di dati, vedere la prima esercitazione di questa serie: [Esercitazione: Creazione di un report tabella semplice &#40;Generatore report&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="1e0e5-123">For step-by-step instructions about how to browse to a report server, add a data source, and add a dataset, see the first tutorial in this series: [Tutorial: Creating a Basic Table Report &#40;Report Builder&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span></span>  
  
 <span data-ttu-id="1e0e5-124">Il tempo stimato per il completare l'esercitazione è di 10 minuti.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-124">Estimated time to complete this tutorial: 10 minutes</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1e0e5-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1e0e5-125">Requirements</span></span>  
 <span data-ttu-id="1e0e5-126">Per altre informazioni sui requisiti, vedere [Prerequisiti per le esercitazioni &#40;Generatore report&#41;](../reporting-services/report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="1e0e5-126">For more information about requirements, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../reporting-services/report-builder-tutorials.md).</span></span>  
  
##  <a name="1-create-a-pie-chart-from-the-chart-wizard"></a><a name="Chart"></a><span data-ttu-id="1e0e5-127">1. creare un grafico a torta da Creazione guidata grafico</span><span class="sxs-lookup"><span data-stu-id="1e0e5-127">1. Create a Pie Chart from the Chart Wizard</span></span>  
 <span data-ttu-id="1e0e5-128">Dalla finestra di dialogo Riquadro attività iniziale utilizzare la Creazione guidata grafico per creare un set di dati incorporato, scegliere un'origine dati condivisa e creare un grafico a torta.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-128">From the Getting Started dialog box, use the Chart Wizard to create an embedded dataset, choose a shared data source, and create a pie chart.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1e0e5-129">Nella query di questa esercitazione sono contenuti i valori dei dati in modo che non sia necessaria un'origine dati esterna.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-129">In this tutorial, the query contains the data values, so that it does not need an external data source.</span></span> <span data-ttu-id="1e0e5-130">Tale condizione rende tuttavia la query piuttosto lunga.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-130">This makes the query quite long.</span></span> <span data-ttu-id="1e0e5-131">In una query di un ambiente aziendale non sarebbe incluso alcun dato.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-131">In a business environment, a query would not contain the data.</span></span> <span data-ttu-id="1e0e5-132">Questo esempio è solo a scopo illustrativo.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-132">This is for learning purposes only.</span></span>  
  
#### <a name="to-create-a-new-chart-report"></a><span data-ttu-id="1e0e5-133">Per creare un nuovo report grafico</span><span class="sxs-lookup"><span data-stu-id="1e0e5-133">To create a new chart report</span></span>  
  
1.  <span data-ttu-id="1e0e5-134">Fare clic sul menu **Start**, scegliere **Programmi**, **Generatore report per Microsoft SQL Server 2012**e quindi fare clic su **Generatore report**.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-134">Click **Start**, point to **Programs**, point to **Microsoft SQL Server 2012 Report Builder**, and then click **Report Builder**.</span></span>  
  
     <span data-ttu-id="1e0e5-135">Verrà visualizzata la finestra di dialogo Riquadro attività iniziale.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-135">The Getting Started dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1e0e5-136">Se la finestra di dialogo Introduzione non viene visualizzata, dal pulsante Generatore report fare clic su **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-136">If the Getting Started dialog box does not appear, from the Report Builder button, click **New**.</span></span>  
  
2.  <span data-ttu-id="1e0e5-137">Nel riquadro sinistro verificare che sia selezionata l'opzione **Nuovo report** .</span><span class="sxs-lookup"><span data-stu-id="1e0e5-137">In the left pane, verify that **New Report** is selected.</span></span>  
  
3.  <span data-ttu-id="1e0e5-138">Nel riquadro di destra fare clic su **Creazione guidata grafico**.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-138">In the right pane, click **Chart Wizard**.</span></span>  
  
4.  <span data-ttu-id="1e0e5-139">Nella pagina **Scegliere un set di dati** fare clic su **Crea un set di dati**e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-139">On the **Choose a dataset** page, click **Create a dataset**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="1e0e5-140">Nella pagina **Scegliere una connessione a un'origine dati** selezionare un'origine dati esistente o individuare il server di report, quindi selezionare un'origine dati e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-140">On the **Choose a connection to a data source** page, select an existing data source or browse to the report server and select a data source, and then click **Next**.</span></span> <span data-ttu-id="1e0e5-141">Potrebbe essere necessario immettere un nome utente e una password.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-141">You may need to enter a user name and password.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1e0e5-142">L'origine dati scelta non ha importanza purché si disponga delle autorizzazioni appropriate.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-142">The data source you choose is unimportant, as long as you have adequate permissions.</span></span> <span data-ttu-id="1e0e5-143">Non verranno recuperati dati dall'origine dati.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-143">You will not be getting data from the data source.</span></span> <span data-ttu-id="1e0e5-144">Per altre informazioni, vedere [Modalità alternative di acquisizione di una connessione dati &#40;Generatore report&#41;](../reporting-services/alternative-ways-to-get-a-data-connection-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="1e0e5-144">For more information, see [Alternative Ways to Get a Data Connection &#40;Report Builder&#41;](../reporting-services/alternative-ways-to-get-a-data-connection-report-builder.md).</span></span>  
  
6.  <span data-ttu-id="1e0e5-145">Nella pagina **Progetta query** fare clic su **modifica come testo**.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-145">On the **Design a Query** page, click **Edit as Text**.</span></span>  
  
7.  <span data-ttu-id="1e0e5-146">Incollare la query seguente nel relativo riquadro:</span><span class="sxs-lookup"><span data-stu-id="1e0e5-146">Paste the following query into the query pane:</span></span>  
  
    ```  
    SELECT 'Advanced Digital Camera' AS Product, CAST(254995.21 AS money) AS Sales  
    UNION SELECT 'Slim Digital Camera' AS Product, CAST(164499.04 AS money) AS Sales  
    UNION SELECT 'SLR Digital Camera' AS Product, CAST(782176.79 AS money) AS Sales  
    UNION SELECT 'Lens Adapter' AS Product, CAST(36333.08 AS money) AS Sales  
    UNION SELECT 'Macro Zoom Lens' AS Product, CAST(40199.3 AS money) AS Sales  
    UNION SELECT 'USB Cable' AS Product, CAST(53245.5 AS money) AS Sales  
    UNION SELECT 'Independent Filmmaker Camcorder' AS Product, CAST(452288.0 AS money) AS Sales  
    UNION SELECT 'Full Frame Digital Camera' AS Product, CAST(247250.85 AS money) AS Sales  
    ```  
  
8.  <span data-ttu-id="1e0e5-147">(Facoltativo) Fare clic sul pulsante Esegui (**!**) per visualizzare i dati su cui si baserà il grafico.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-147">(Optional) Click the Run button (**!**) to see the data your chart will be based on.</span></span>  
  
9. <span data-ttu-id="1e0e5-148">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-148">Click **Next**.</span></span>  
  
##  <a name="2-choose-the-chart-type"></a><a name="ChartType"></a><span data-ttu-id="1e0e5-149">2. scegliere il tipo di grafico</span><span class="sxs-lookup"><span data-stu-id="1e0e5-149">2. Choose the Chart Type</span></span>  
 <span data-ttu-id="1e0e5-150">È possibile scegliere tra diversi tipi di grafico predefiniti.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-150">You can choose from a variety of predefined chart types.</span></span>  
  
#### <a name="to-add-a-pie-chart"></a><span data-ttu-id="1e0e5-151">Per aggiungere un grafico a torta</span><span class="sxs-lookup"><span data-stu-id="1e0e5-151">To add a pie chart</span></span>  
  
1.  <span data-ttu-id="1e0e5-152">Nella pagina **scegliere un tipo di grafico** fare clic su **torta**, quindi su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-152">On the **Choose a chart type** page, click **Pie**, and then click **Next**.</span></span> <span data-ttu-id="1e0e5-153">Viene visualizzata la pagina **Disponi campi del grafico** .</span><span class="sxs-lookup"><span data-stu-id="1e0e5-153">The **Arrange chart fields** page opens.</span></span>  
  
     <span data-ttu-id="1e0e5-154">Nella pagina **Disponi campi del grafico** trascinare il campo Product nel riquadro **Categorie** .</span><span class="sxs-lookup"><span data-stu-id="1e0e5-154">On the **Arrange chart fields** page, drag the Product field to the **Categories** pane.</span></span> <span data-ttu-id="1e0e5-155">Le categorie consentono di definire il numero di sezioni nel grafico a torta.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-155">Categories define the number of slices in the pie chart.</span></span> <span data-ttu-id="1e0e5-156">In questo esempio, saranno presenti otto sezioni, una per ogni prodotto.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-156">In this example, there will be eight slices, one for each product.</span></span>  
  
2.  <span data-ttu-id="1e0e5-157">Trascinare il campo Sales nel riquadro **Valori** .</span><span class="sxs-lookup"><span data-stu-id="1e0e5-157">Drag the Sales field to the **Values** pane.</span></span> <span data-ttu-id="1e0e5-158">Sales rappresenta l'importo delle vendite per la sottocategoria.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-158">Sales represents the sales amount for the subcategory.</span></span> <span data-ttu-id="1e0e5-159">Nel riquadro **Valori** viene visualizzato `[Sum(Sales)]` perché nel grafico viene mostrata l'aggregazione per ogni prodotto.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-159">The **Values** pane displays `[Sum(Sales)]` because the chart displays the aggregate for each product.</span></span>  
  
3.  <span data-ttu-id="1e0e5-160">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-160">Click **Next**.</span></span>  
  
4.  <span data-ttu-id="1e0e5-161">Nel riquadro Stili della pagina **scegliere uno stile** selezionare uno stile.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-161">On the **Choose a style** page, in the Styles pane, select a style.</span></span>  
  
     <span data-ttu-id="1e0e5-162">Uno stile specifica lo stile del carattere, il set di colori e uno stile del bordo.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-162">A style specifies a font style, a set of colors, and a border style.</span></span> <span data-ttu-id="1e0e5-163">Quando si seleziona uno stile, nel riquadro di anteprima viene visualizzato un esempio del grafico con lo stile selezionato.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-163">When you select a style, the Preview pane displays a sample of the chart with that style.</span></span>  
  
5.  <span data-ttu-id="1e0e5-164">Fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-164">Click **Finish**.</span></span>  
  
     <span data-ttu-id="1e0e5-165">Il grafico verrà aggiunto all'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-165">The chart is added to the design surface.</span></span>  
  
6.  <span data-ttu-id="1e0e5-166">Fare clic sul grafico per visualizzarne gli handle.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-166">Click the chart to display the chart handles.</span></span> <span data-ttu-id="1e0e5-167">Trascinare l'angolo inferiore destro del grafico per ingrandirlo.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-167">Drag the bottom-right corner of the chart to increase the size of the chart.</span></span> <span data-ttu-id="1e0e5-168">Le dimensioni dell'area di progettazione del report vengono aumentate in base alle dimensioni del grafico.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-168">Note that the report design surface increases in size to accommodate the chart size.</span></span>  
  
7.  <span data-ttu-id="1e0e5-169">Fare clic su **Esegui** per visualizzare l'anteprima del report.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-169">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="1e0e5-170">Nel report viene visualizzato il grafico a torta con otto sezioni, una per ogni prodotto.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-170">The report displays the pie chart with eight slices, one for each product.</span></span> <span data-ttu-id="1e0e5-171">Le dimensioni di ogni sezione rappresentano le vendite per quel prodotto.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-171">The size of each slice represents the sales for that product.</span></span> <span data-ttu-id="1e0e5-172">Tre delle sezioni sono piuttosto sottili.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-172">Three of the slices are quite thin.</span></span>  
  
##  <a name="3-display-percentages-in-each-slice"></a><a name="Percentages"></a><span data-ttu-id="1e0e5-173">3. visualizzare le percentuali in ogni sezione</span><span class="sxs-lookup"><span data-stu-id="1e0e5-173">3. Display Percentages in Each Slice</span></span>  
 <span data-ttu-id="1e0e5-174">Su ogni sezione della torta, è possibile visualizzare una percentuale per questa sezione rispetto alla torta intera.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-174">On each slice of the pie, you can display a percentage for this slice compared to the whole pie.</span></span>  
  
#### <a name="to-display-percentages-in-each-slice-of-the-pie-chart"></a><span data-ttu-id="1e0e5-175">Per visualizzare le percentuali in ogni sezione del grafico a torta</span><span class="sxs-lookup"><span data-stu-id="1e0e5-175">To display percentages in each slice of the pie chart</span></span>  
  
1.  <span data-ttu-id="1e0e5-176">Passare alla visualizzazione di progettazione report.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-176">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="1e0e5-177">Fare clic con il pulsante destro del mouse sul grafico a torta e scegliere **Mostra etichette dati**.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-177">Right-click the pie chart and click **Show Data Labels**.</span></span> <span data-ttu-id="1e0e5-178">Le etichette dati vengono visualizzate nel grafico.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-178">The data labels appear on the chart.</span></span>  
  
3.  <span data-ttu-id="1e0e5-179">Fare clic con il pulsante destro del mouse su un'etichetta e scegliere **Proprietà etichetta serie**.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-179">Right-click a label, and then click **Series Label Properties**.</span></span>  
  
4.  <span data-ttu-id="1e0e5-180">In dati etichetta, nella casella di riepilogo a discesa, selezionare **#PERCENT**.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-180">In Label data, from the drop-down box, select **#PERCENT**.</span></span>  
  
     <span data-ttu-id="1e0e5-181">Per visualizzare i valori come percentuali, la proprietà UseValueAsLabel deve essere impostata su false.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-181">To display values as percentages, the UseValueAsLabel property must be false.</span></span> <span data-ttu-id="1e0e5-182">Se viene richiesto di impostare questo valore nella finestra di dialogo **Conferma azione** fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-182">If you are prompted to set this value in the **Confirm Action** dialog, click **Yes**.</span></span>  
  
5.  <span data-ttu-id="1e0e5-183">Opzionale Per specificare il numero di cifre decimali visualizzate nell'etichetta, digitare `#PERCENT{Pn}` dove *n* è il numero di posizioni decimali da visualizzare.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-183">(Optional) To specify how many decimal places the label shows, type `#PERCENT{Pn}` where *n* is the number of decimal places to display.</span></span> <span data-ttu-id="1e0e5-184">Ad esempio, per non visualizzare posizioni decimali, digitare `#PERCENT{P0}` .</span><span class="sxs-lookup"><span data-stu-id="1e0e5-184">For example, to display no decimal places, type `#PERCENT{P0}`.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1e0e5-185">L'impostazione di**Formato numeri** nella finestra di dialogo **Proprietà etichetta serie** non produrrà alcun effetto quando si formattano le percentuali.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-185">**Number Format** in the **Series Label Properties** dialog box has no effect when you format percentages.</span></span> <span data-ttu-id="1e0e5-186">Tale opzione consente solo di formattare le etichette come percentuali, senza tuttavia calcolare la percentuale del grafico a torta rappresentata da ciascuna sezione.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-186">This formats the labels as percentages, but does not calculate the percentage of the pie that each slice represents.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
7.  <span data-ttu-id="1e0e5-187">Fare clic su **Esegui** per visualizzare l'anteprima del report.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-187">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="1e0e5-188">Nel report viene visualizzata la percentuale rispetto all'intero per ogni sezione del grafico a torta.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-188">The report displays the percentage of the whole for each pie slice.</span></span>  
  
##  <a name="4-combine-small-slices-into-one-slice"></a><a name="CombineSlices"></a><span data-ttu-id="1e0e5-189">4. combinare le piccole sezioni in un'unica sezione</span><span class="sxs-lookup"><span data-stu-id="1e0e5-189">4. Combine Small Slices into One Slice</span></span>  
 <span data-ttu-id="1e0e5-190">Tre delle sezioni della torta sono piuttosto sottili.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-190">Three of the slices in the pie are quite small.</span></span> <span data-ttu-id="1e0e5-191">È possibile combinare più sezioni piccole in un'unica sezione più grande che le rappresenta tutte.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-191">You can combine multiple small slices into one larger slice that represents all of them.</span></span>  
  
#### <a name="to-combine-any-slices-on-the-pie-chart-smaller-than-5-percent-into-one-slice"></a><span data-ttu-id="1e0e5-192">Per combinare le sezioni del grafico a torta inferiori al 5% in un'unica sezione</span><span class="sxs-lookup"><span data-stu-id="1e0e5-192">To combine any slices on the pie chart smaller than 5 percent into one slice</span></span>  
  
1.  <span data-ttu-id="1e0e5-193">Passare alla visualizzazione di progettazione report.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-193">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="1e0e5-194">Nel gruppo Mostra **/Nascondi** della scheda **Visualizza** selezionare **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-194">On the **View** tab, in the **Show/Hide** group, select **Properties**.</span></span>  
  
3.  <span data-ttu-id="1e0e5-195">Nell'area di progettazione fare clic su una sezione del grafico a torta.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-195">On the design surface, click on any slice of the pie chart.</span></span> <span data-ttu-id="1e0e5-196">Le proprietà della serie verranno visualizzate nel riquadro Proprietà.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-196">The properties for the series are displayed in the Properties pane.</span></span>  
  
4.  <span data-ttu-id="1e0e5-197">Nella sezione **Generale** espandere il nodo **CustomAttributes** .</span><span class="sxs-lookup"><span data-stu-id="1e0e5-197">In the **General** section, expand the **CustomAttributes** node.</span></span>  
  
5.  <span data-ttu-id="1e0e5-198">Impostare la proprietà **CollectedStyle** su **SingleSlice**.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-198">Set the **CollectedStyle** property to **SingleSlice**.</span></span>  
  
6.  <span data-ttu-id="1e0e5-199">Verificare che la proprietà **CollectedThreshold** sia impostata su 5.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-199">Verify that the **CollectedThreshold** property is set to 5.</span></span>  
  
7.  <span data-ttu-id="1e0e5-200">Verificare che la proprietà **CollectedThresholdUsePercent** sia impostata su **True**.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-200">Verify that the **CollectedThresholdUsePercent** property is set to **True**.</span></span>  
  
8.  <span data-ttu-id="1e0e5-201">Nella scheda **Home** della barra multifunzione fare clic su **Esegui** per visualizzare l'anteprima del report.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-201">On the Ribbon, on the **Home** tab, click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="1e0e5-202">Nella legenda, la categoria "Other" ora esiste.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-202">In the legend, the category "Other" now exists.</span></span> <span data-ttu-id="1e0e5-203">La nuova sezione del grafico a torta combina tutte le sezioni inferiori al 5% in una sezione che costituisce il 6% della torta intera.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-203">The new pie slice combines all the slices that were under 5% into one slice that is 6% of the whole pie.</span></span>  
  
##  <a name="5-customize-the-drawing-effect"></a><a name="DrawingEffect"></a><span data-ttu-id="1e0e5-204">5. personalizzare l'effetto di disegno</span><span class="sxs-lookup"><span data-stu-id="1e0e5-204">5. Customize the Drawing Effect</span></span>  
 <span data-ttu-id="1e0e5-205">In Creazione guidata grafico, lo stile predefinito per un grafico a torta è Oceano che rappresenta un effetto concavo.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-205">In the Chart Wizard, the default style for a pie chart is Ocean, which features a Concave drawing effect.</span></span> <span data-ttu-id="1e0e5-206">Tale effetto può essere modificato dopo aver completato la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-206">You can change that after you run the wizard.</span></span>  
  
#### <a name="to-add-a-drawing-effect-to-the-pie-chart"></a><span data-ttu-id="1e0e5-207">Per aggiungere un effetto di disegno al grafico a torta</span><span class="sxs-lookup"><span data-stu-id="1e0e5-207">To add a drawing effect to the pie chart</span></span>  
  
1.  <span data-ttu-id="1e0e5-208">Passare alla visualizzazione di progettazione report.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-208">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="1e0e5-209">Se il riquadro proprietà non è già aperto, selezionare **Proprietà**nella scheda **Visualizza** .</span><span class="sxs-lookup"><span data-stu-id="1e0e5-209">If the Properties pane is not already opened, on the **View** tab, select **Properties**.</span></span>  
  
3.  <span data-ttu-id="1e0e5-210">Fare doppio clic sul grafico a torta.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-210">Double-click the pie chart itself.</span></span> <span data-ttu-id="1e0e5-211">Le proprietà della serie per il grafico a torta verranno visualizzate nel riquadro Proprietà.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-211">The series properties for the pie chart are shown in the Properties pane.</span></span>  
  
4.  <span data-ttu-id="1e0e5-212">Nel riquadro Proprietà espandere il nodo **CustomAttributes** .</span><span class="sxs-lookup"><span data-stu-id="1e0e5-212">In the Properties pane, expand the **CustomAttributes** node.</span></span>  
  
5.  <span data-ttu-id="1e0e5-213">Impostare **PieDrawingStyle** su **SoftEdge**.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-213">Set the **PieDrawingStyle** to **SoftEdge**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1e0e5-214">Gli effetti di disegno e gli effetti tridimensionali sono opzioni esclusive.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-214">Drawing effects and three-dimensional effects are exclusive options.</span></span> <span data-ttu-id="1e0e5-215">Se a un grafico sono applicati effetti tridimensionali, **PieDrawingStyle** non è disponibile nel riquadro proprietà.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-215">If a chart has three-dimensional effects applied, **PieDrawingStyle** is not available on the Properties pane.</span></span>  
  
6.  <span data-ttu-id="1e0e5-216">Fare clic su **Esegui** per visualizzare l'anteprima del report.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-216">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="1e0e5-217">Nell'illustrazione seguente viene mostrato il grafico a torta con l'effetto dei bordi sfumati.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-217">The following illustration shows the pie chart with the soft edge effect.</span></span>  
  
 <span data-ttu-id="1e0e5-218">![rs_TutorialPieChartSoftEdge](../../2014/tutorials/media/rs-tutorialpiechartsoftedge.gif "rs_TutorialPieChartSoftEdge")</span><span class="sxs-lookup"><span data-stu-id="1e0e5-218">![rs_TutorialPieChartSoftEdge](../../2014/tutorials/media/rs-tutorialpiechartsoftedge.gif "rs_TutorialPieChartSoftEdge")</span></span>  
  
##  <a name="6-add-a-report-title"></a><a name="Title"></a><span data-ttu-id="1e0e5-219">6. aggiungere un titolo al report</span><span class="sxs-lookup"><span data-stu-id="1e0e5-219">6. Add a Report Title</span></span>  
  
#### <a name="to-add-a-report-title"></a><span data-ttu-id="1e0e5-220">Per aggiungere il titolo di un report</span><span class="sxs-lookup"><span data-stu-id="1e0e5-220">To add a report title</span></span>  
  
1.  <span data-ttu-id="1e0e5-221">Nell'area di progettazione fare clic su **Fare clic per aggiungere il titolo**.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-221">On the design surface, click **Click to add title**.</span></span>  
  
2.  <span data-ttu-id="1e0e5-222">Digitare **Vendite di fotocamere e di cineprese**, premere INVIO e quindi digitare **Come percentuale delle vendite totali**. Verrà visualizzato quanto segue:</span><span class="sxs-lookup"><span data-stu-id="1e0e5-222">Type **Camera and Camcorder Sales**, press ENTER, and then type **As a Percentage of Total Sales**, so it looks like this:</span></span>  
  
     <span data-ttu-id="1e0e5-223">**Vendite di fotocamere e di cineprese**</span><span class="sxs-lookup"><span data-stu-id="1e0e5-223">**Camera and Camcorder Sales**</span></span>  
  
     <span data-ttu-id="1e0e5-224">**Come percentuale delle vendite totali**</span><span class="sxs-lookup"><span data-stu-id="1e0e5-224">**As a Percentage of Total Sales**</span></span>  
  
3.  <span data-ttu-id="1e0e5-225">Selezionare **vendite di fotocamere e**di cineprese e fare clic sul pulsante **grassetto** nella sezione **carattere** della scheda **Home** della barra multifunzione.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-225">Select **Camera and Camcorder Sales**, and click the **Bold** button from the **Font** section of the **Home** tab of the ribbon.</span></span>  
  
4.  <span data-ttu-id="1e0e5-226">Selezionare **come percentuale delle vendite totali**e nella sezione **carattere** della scheda **Home** impostare le dimensioni del carattere su **10**.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-226">Select **As a Percentage of Total Sales**, and in the **Font** section on the **Home** tab, set the font size to **10**.</span></span>  
  
5.  <span data-ttu-id="1e0e5-227">(Facoltativo) Per contenere le due righe del testo potrebbe essere necessario aumentare l'altezza della casella di testo Titolo.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-227">(Optional) You may need to make the Title text box taller to accommodate the two lines of text.</span></span>  
  
     <span data-ttu-id="1e0e5-228">Il titolo verrà visualizzato nella parte superiore del report.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-228">This title will appear at the top of the report.</span></span> <span data-ttu-id="1e0e5-229">Quando non è definita un'intestazione di pagina, gli elementi nella parte superiore del corpo del report equivalgono a un'intestazione di report.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-229">When there is no page header defined, items at the top of the report body are the equivalent of a report header.</span></span>  
  
6.  <span data-ttu-id="1e0e5-230">Fare clic su **Esegui** per visualizzare l'anteprima del report.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-230">Click **Run** to preview the report.</span></span>  
  
##  <a name="7-save-the-report"></a><a name="Save"></a><span data-ttu-id="1e0e5-231">7. salvare il report</span><span class="sxs-lookup"><span data-stu-id="1e0e5-231">7. Save the Report</span></span>  
  
#### <a name="to-save-the-report"></a><span data-ttu-id="1e0e5-232">Per salvare il report</span><span class="sxs-lookup"><span data-stu-id="1e0e5-232">To save the report</span></span>  
  
1.  <span data-ttu-id="1e0e5-233">Passare alla visualizzazione di progettazione report.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-233">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="1e0e5-234">Fare clic sul pulsante Generatore report , quindi su **Salva con nome**.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-234">From the Report Builder button, click **Save As**.</span></span>  
  
3.  <span data-ttu-id="1e0e5-235">In **Nome**digitare **Grafico a torta - Vendite**.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-235">In **Name**, type **Sales Pie Chart**.</span></span>  
  
4.  <span data-ttu-id="1e0e5-236">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-236">Click **Save**.</span></span>  
  
 <span data-ttu-id="1e0e5-237">Il report verrà salvato sul server di report.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-237">Your report is saved on the report server.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="1e0e5-238">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="1e0e5-238">Next Steps</span></span>  
 <span data-ttu-id="1e0e5-239">Questo passaggio conclude l'esercitazione relativa all'aggiunta di un grafico a torta al report.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-239">You have successfully completed the Adding a Pie Chart to Your Report tutorial.</span></span> <span data-ttu-id="1e0e5-240">Per altre informazioni sui grafici, vedere [Grafici &#40;Generatore report e SSRS&#41;](report-design/charts-report-builder-and-ssrs.md) e [Grafici sparkline e barre dei dati &#40;Generatore report e SSRS&#41;](report-design/sparklines-and-data-bars-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="1e0e5-240">To learn more about charts, see [Charts &#40;Report Builder and SSRS&#41;](report-design/charts-report-builder-and-ssrs.md) and [Sparklines and Data Bars &#40;Report Builder and SSRS&#41;](report-design/sparklines-and-data-bars-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e0e5-241">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1e0e5-241">See Also</span></span>  
 <span data-ttu-id="1e0e5-242">[Esercitazioni &#40;Generatore report&#41;](report-builder-tutorials.md) </span><span class="sxs-lookup"><span data-stu-id="1e0e5-242">[Tutorials &#40;Report Builder&#41;](report-builder-tutorials.md) </span></span>  
 [<span data-ttu-id="1e0e5-243">Generatore report in SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="1e0e5-243">Report Builder in SQL Server 2014</span></span>](report-builder/report-builder-in-sql-server-2016.md)  
  
  
