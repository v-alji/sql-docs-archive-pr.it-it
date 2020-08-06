---
title: 'Esercitazione: Aggiungere un grafico a torta al report (Generatore report) | Microsoft Docs'
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 63480059-b7b9-44b5-9d7f-91780db708b6
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 0ef3b3f2872c2f8181296bb05337ca18975ac2f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722471"
---
# <a name="tutorial-add-a-column-chart-to-your-report-report-builder"></a><span data-ttu-id="2389a-102">Esercitazione: Aggiungere un istogramma al report (Generatore report)</span><span class="sxs-lookup"><span data-stu-id="2389a-102">Tutorial: Add a Column Chart to Your Report (Report Builder)</span></span>
  <span data-ttu-id="2389a-103">In un istogramma le serie vengono visualizzate come set di barre verticali raggruppate per categoria.</span><span class="sxs-lookup"><span data-stu-id="2389a-103">A column chart displays a series as a set of vertical bars that are grouped by category.</span></span> <span data-ttu-id="2389a-104">Un istogramma può essere utile per:</span><span class="sxs-lookup"><span data-stu-id="2389a-104">A column chart can be useful to:</span></span>  
  
-   <span data-ttu-id="2389a-105">Mostrare le modifiche apportate in un determinato periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="2389a-105">Show data changes over a period of time.</span></span>  
  
-   <span data-ttu-id="2389a-106">Confrontare il valore relativo di più serie.</span><span class="sxs-lookup"><span data-stu-id="2389a-106">Compare the relative value of multiple series.</span></span>  
  
-   <span data-ttu-id="2389a-107">Visualizzare una media mobile per indicare le tendenze.</span><span class="sxs-lookup"><span data-stu-id="2389a-107">Display a moving average to show trends.</span></span>  
  
 <span data-ttu-id="2389a-108">Nell'illustrazione seguente è mostrato l'istogramma che verrà creato con una media mobile.</span><span class="sxs-lookup"><span data-stu-id="2389a-108">The following illustration shows the column chart you will create, with a moving average.</span></span>  
  
 <span data-ttu-id="2389a-109">![rs_TutorialColChartFinished](../../2014/tutorials/media/rs-tutorialcolchartfinished.gif "rs_TutorialColChartFinished")</span><span class="sxs-lookup"><span data-stu-id="2389a-109">![rs_TutorialColChartFinished](../../2014/tutorials/media/rs-tutorialcolchartfinished.gif "rs_TutorialColChartFinished")</span></span>  
  
##  <a name="what-you-will-learn"></a><a name="BackToTop"></a><span data-ttu-id="2389a-110">Cosa si apprenderà</span><span class="sxs-lookup"><span data-stu-id="2389a-110">What You Will Learn</span></span>  
 <span data-ttu-id="2389a-111">In questa esercitazione verranno illustrate le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2389a-111">In this tutorial you will learn how to do the following:</span></span>  
  
1.  [<span data-ttu-id="2389a-112">Creare un grafico da Creazione guidata grafico</span><span class="sxs-lookup"><span data-stu-id="2389a-112">Create a Chart from the Chart Wizard</span></span>](#Chart)  
  
2.  [<span data-ttu-id="2389a-113">Scegliere il tipo di grafico</span><span class="sxs-lookup"><span data-stu-id="2389a-113">Choose the Chart Type</span></span>](#ChartType)  
  
3.  [<span data-ttu-id="2389a-114">Formattare l'asse orizzontale e assegnare un'etichetta</span><span class="sxs-lookup"><span data-stu-id="2389a-114">Format and Label the Horizontal Axis</span></span>](#Horizontal)  
  
4.  [<span data-ttu-id="2389a-115">Spostare la legenda</span><span class="sxs-lookup"><span data-stu-id="2389a-115">Move the Legend</span></span>](#Legend)  
  
5.  [<span data-ttu-id="2389a-116">Spostare il titolo del grafico</span><span class="sxs-lookup"><span data-stu-id="2389a-116">Title the Chart</span></span>](#ChartTitle)  
  
6.  [<span data-ttu-id="2389a-117">Formattare l'asse verticale e assegnare un'etichetta</span><span class="sxs-lookup"><span data-stu-id="2389a-117">Format and Label the Vertical Axis</span></span>](#Vertical)  
  
7.  [<span data-ttu-id="2389a-118">Aggiungere una media mobile</span><span class="sxs-lookup"><span data-stu-id="2389a-118">Add a Moving Average</span></span>](#Average)  
  
8.  [<span data-ttu-id="2389a-119">Aggiungere un titolo al report</span><span class="sxs-lookup"><span data-stu-id="2389a-119">Add a Report Title</span></span>](#Title)  
  
9. [<span data-ttu-id="2389a-120">Salva il report</span><span class="sxs-lookup"><span data-stu-id="2389a-120">Save the Report</span></span>](#Save)  
  
> [!NOTE]  
>  <span data-ttu-id="2389a-121">In questa esercitazione, i passaggi per la procedura guidata sono consolidati in un'unica procedura.</span><span class="sxs-lookup"><span data-stu-id="2389a-121">In this tutorial, the steps for the wizard are consolidated into one procedure.</span></span> <span data-ttu-id="2389a-122">Per istruzioni dettagliate su come selezionare un server di report, come scegliere un'origine dati e come creare un set di dati, vedere la prima esercitazione di questa serie: [Esercitazione: Creazione di un report tabella semplice &#40;Generatore report&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="2389a-122">For step-by-step instructions about how to browse to a report server, choose a data source, and create a dataset, see the first tutorial in this series: [Tutorial: Creating a Basic Table Report &#40;Report Builder&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span></span>  
  
 <span data-ttu-id="2389a-123">Tempo previsto per il completamento di questa esercitazione: 15 minuti.</span><span class="sxs-lookup"><span data-stu-id="2389a-123">Estimated time to complete this tutorial: 15 minutes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2389a-124">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2389a-124">Requirements</span></span>  
 <span data-ttu-id="2389a-125">Per informazioni sui requisiti, vedere [Prerequisiti per le esercitazioni &#40;Generatore report&#41;](../reporting-services/report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="2389a-125">For information about requirements, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../reporting-services/report-builder-tutorials.md).</span></span>  
  
##  <a name="1-create-a-chart-report-from-the-chart-wizard"></a><a name="Chart"></a><span data-ttu-id="2389a-126">1. creare un report grafico da Creazione guidata grafico</span><span class="sxs-lookup"><span data-stu-id="2389a-126">1. Create a Chart Report from the Chart Wizard</span></span>  
 <span data-ttu-id="2389a-127">Nella finestra di dialogo **Introduzione** utilizzare la creazione guidata grafico per creare un set di dati incorporato, scegliere un'origine dati condivisa e creare un istogramma.</span><span class="sxs-lookup"><span data-stu-id="2389a-127">From the **Getting Started** dialog box, use the Chart Wizard to create an embedded dataset, choose a shared data source, and create a column chart.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2389a-128">Nella query di questa esercitazione sono contenuti i valori dei dati in modo che non sia necessaria un'origine dati esterna.</span><span class="sxs-lookup"><span data-stu-id="2389a-128">In this tutorial, the query contains the data values, so that it does not need an external data source.</span></span> <span data-ttu-id="2389a-129">Tale condizione rende tuttavia la query piuttosto lunga.</span><span class="sxs-lookup"><span data-stu-id="2389a-129">This makes the query quite long.</span></span> <span data-ttu-id="2389a-130">In una query di un ambiente aziendale non sarebbe incluso alcun dato.</span><span class="sxs-lookup"><span data-stu-id="2389a-130">In a business environment, a query would not contain the data.</span></span> <span data-ttu-id="2389a-131">Questo esempio è solo a scopo illustrativo.</span><span class="sxs-lookup"><span data-stu-id="2389a-131">This is for learning purposes only.</span></span>  
  
#### <a name="to-create-a-new-chart-report"></a><span data-ttu-id="2389a-132">Per creare un nuovo report grafico</span><span class="sxs-lookup"><span data-stu-id="2389a-132">To create a new chart report</span></span>  
  
1.  <span data-ttu-id="2389a-133">Fare clic sul menu **Start**, scegliere **Programmi**, **Generatore report per Microsoft SQL Server 2012**e quindi fare clic su **Generatore report**.</span><span class="sxs-lookup"><span data-stu-id="2389a-133">Click **Start**, point to **Programs**, point to **Microsoft SQL Server 2012 Report Builder**, and then click **Report Builder**.</span></span>  
  
     <span data-ttu-id="2389a-134">Verrà visualizzata la finestra di dialogo **Introduzione** .</span><span class="sxs-lookup"><span data-stu-id="2389a-134">The **Getting Started** dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2389a-135">Se la finestra di dialogo **Introduzione** non viene visualizzata, dal pulsante **Generatore report** fare clic su **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="2389a-135">If the **Getting Started** dialog box does not appear, from the **Report Builder** button, click **New**.</span></span>  
  
2.  <span data-ttu-id="2389a-136">Nel riquadro sinistro verificare che sia selezionata l'opzione **Nuovo report** .</span><span class="sxs-lookup"><span data-stu-id="2389a-136">In the left pane, verify that **New Report** is selected.</span></span>  
  
3.  <span data-ttu-id="2389a-137">Nel riquadro di destra fare clic su **Creazione guidata grafico**.</span><span class="sxs-lookup"><span data-stu-id="2389a-137">In the right pane, click **Chart Wizard**.</span></span>  
  
4.  <span data-ttu-id="2389a-138">Nella **pagina scegliere un set di dati**fare clic su **Crea un set di dati**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="2389a-138">On the **Choose a dataset page**, click **Create a dataset**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="2389a-139">Nella pagina **Scegliere una connessione a un'origine dati** selezionare un'origine dati esistente o individuare il server di report, quindi selezionare un'origine dati e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="2389a-139">On the **Choose a connection to a data source** page, select an existing data source or browse to the report server and select a data source, and then click **Next**.</span></span> <span data-ttu-id="2389a-140">Potrebbe essere necessario immettere un nome utente e una password.</span><span class="sxs-lookup"><span data-stu-id="2389a-140">You may need to enter a user name and password.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2389a-141">L'origine dati scelta non ha importanza purché si disponga delle autorizzazioni appropriate.</span><span class="sxs-lookup"><span data-stu-id="2389a-141">The data source you choose is unimportant, as long as you have adequate permissions.</span></span> <span data-ttu-id="2389a-142">Non verranno recuperati dati dall'origine dati.</span><span class="sxs-lookup"><span data-stu-id="2389a-142">You will not be getting data from the data source.</span></span> <span data-ttu-id="2389a-143">Per altre informazioni, vedere [Modalità alternative di acquisizione di una connessione dati &#40;Generatore report&#41;](../reporting-services/alternative-ways-to-get-a-data-connection-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="2389a-143">For more information, see [Alternative Ways to Get a Data Connection &#40;Report Builder&#41;](../reporting-services/alternative-ways-to-get-a-data-connection-report-builder.md).</span></span>  
  
6.  <span data-ttu-id="2389a-144">Nella pagina **Progetta query** fare clic su **Modifica come testo**.</span><span class="sxs-lookup"><span data-stu-id="2389a-144">On the **Design a query** page, click **Edit as Text**.</span></span>  
  
7.  <span data-ttu-id="2389a-145">Incollare la query seguente nel relativo riquadro:</span><span class="sxs-lookup"><span data-stu-id="2389a-145">Paste the following query into the query pane:</span></span>  
  
    ```  
    SELECT CAST('2009-01-01' AS date) AS SalesDate, CAST(54995.21 AS money) AS Sales  
    UNION SELECT CAST('2009-01-05' AS date) AS SalesDate, CAST(64499.04 AS money) AS Sales  
    UNION SELECT CAST('2009-02-11' AS date) AS SalesDate, CAST(37821.79 AS money) AS Sales  
    UNION SELECT CAST('2009-03-18' AS date) AS SalesDate, CAST(53633.08 AS money) AS Sales  
    UNION SELECT CAST('2009-04-23' AS date) AS SalesDate, CAST(24019.3 AS money) AS Sales  
    UNION SELECT CAST('2009-05-01' AS date) AS SalesDate, CAST(93245.5 AS money) AS Sales  
    UNION SELECT CAST('2009-06-06' AS date) AS SalesDate, CAST(55288.0 AS money) AS Sales  
    UNION SELECT CAST('2009-06-16' AS date) AS SalesDate, CAST(68733.5 AS money) AS Sales  
    UNION SELECT CAST('2009-07-16' AS date) AS SalesDate, CAST(24750.85 AS money) AS Sales  
    UNION SELECT CAST('2009-08-23' AS date) AS SalesDate, CAST(43452.3 AS money) AS Sales  
    UNION SELECT CAST('2009-09-24' AS date) AS SalesDate, CAST(58656. AS money) AS Sales  
    UNION SELECT CAST('2009-10-15' AS date) AS SalesDate, CAST(44583. AS money) AS Sales  
    UNION SELECT CAST('2009-11-21' AS date) AS SalesDate, CAST(81568. AS money) AS Sales  
    UNION SELECT CAST('2009-12-15' AS date) AS SalesDate, CAST(45973. AS money) AS Sales  
    UNION SELECT CAST('2009-12-26' AS date) AS SalesDate, CAST(96357. AS money) AS Sales  
    UNION SELECT CAST('2009-12-31' AS date) AS SalesDate, CAST(81946. AS money) AS Sales  
    ```  
  
8.  <span data-ttu-id="2389a-146">(Facoltativo) Fare clic sul pulsante Esegui (**!**) per visualizzare i dati su cui si baserà il grafico.</span><span class="sxs-lookup"><span data-stu-id="2389a-146">(Optional) Click the Run button (**!**) to see the data your chart will be based on.</span></span>  
  
9. <span data-ttu-id="2389a-147">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="2389a-147">Click **Next**.</span></span>  
  
##  <a name="2-choose-the-chart-type"></a><a name="ChartType"></a><span data-ttu-id="2389a-148">2. scegliere il tipo di grafico</span><span class="sxs-lookup"><span data-stu-id="2389a-148">2. Choose the Chart Type</span></span>  
 <span data-ttu-id="2389a-149">È possibile scegliere tra diversi tipi di grafico predefiniti.</span><span class="sxs-lookup"><span data-stu-id="2389a-149">You can choose from a variety of predefined chart types.</span></span>  
  
#### <a name="to-add-a-column-chart"></a><span data-ttu-id="2389a-150">Per aggiungere un istogramma</span><span class="sxs-lookup"><span data-stu-id="2389a-150">To add a column chart</span></span>  
  
1.  <span data-ttu-id="2389a-151">L'istogramma è il tipo di grafico predefinito nella pagina **Scegliere un tipo di grafico** .</span><span class="sxs-lookup"><span data-stu-id="2389a-151">On the **Choose a chart type** page, the column chart is the default chart type.</span></span> <span data-ttu-id="2389a-152">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="2389a-152">Click **Next**.</span></span>  
  
2.  <span data-ttu-id="2389a-153">Nella pagina **Disponi campi del grafico** trascinare il campo SalesDate in **Categorie**.</span><span class="sxs-lookup"><span data-stu-id="2389a-153">On the **Arrange chart fields** page, drag the SalesDate field to **Categories**.</span></span> <span data-ttu-id="2389a-154">Le categorie vengono visualizzate sull'asse orizzontale.</span><span class="sxs-lookup"><span data-stu-id="2389a-154">Categories display on the horizontal axis.</span></span>  
  
3.  <span data-ttu-id="2389a-155">Trascinare il campo Sales in **Valori**.</span><span class="sxs-lookup"><span data-stu-id="2389a-155">Drag the Sales field to **Values**.</span></span> <span data-ttu-id="2389a-156">Nella casella **Valori** viene visualizzato Sum(Sales) perché per ogni data viene aggregata la somma dei totali di vendita.</span><span class="sxs-lookup"><span data-stu-id="2389a-156">The **Values** box displays Sum(Sales) because the sum of the sales total value is aggregated for each date.</span></span> <span data-ttu-id="2389a-157">I valori vengono visualizzati sull'asse verticale.</span><span class="sxs-lookup"><span data-stu-id="2389a-157">Values display on the vertical axis.</span></span>  
  
4.  <span data-ttu-id="2389a-158">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="2389a-158">Click **Next**.</span></span>  
  
5.  <span data-ttu-id="2389a-159">Nella casella stili della pagina **scegliere uno stile** selezionare uno stile.</span><span class="sxs-lookup"><span data-stu-id="2389a-159">On the **Choose a Style** page, in the Styles box, select a style.</span></span>  
  
     <span data-ttu-id="2389a-160">Uno stile specifica lo stile del carattere, il set di colori e uno stile del bordo.</span><span class="sxs-lookup"><span data-stu-id="2389a-160">A style specifies a font style, a set of colors, and a border style.</span></span> <span data-ttu-id="2389a-161">Quando si seleziona uno stile, nel riquadro di anteprima viene visualizzato un esempio del grafico con lo stile selezionato.</span><span class="sxs-lookup"><span data-stu-id="2389a-161">When you select a style, the Preview pane displays a sample of the chart with that style.</span></span>  
  
6.  <span data-ttu-id="2389a-162">Fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="2389a-162">Click **Finish**.</span></span>  
  
     <span data-ttu-id="2389a-163">Il grafico verrà aggiunto all'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="2389a-163">The chart is added to the design surface.</span></span>  
  
7.  <span data-ttu-id="2389a-164">Fare clic sul grafico per visualizzarne gli handle.</span><span class="sxs-lookup"><span data-stu-id="2389a-164">Click the chart to display the chart handles.</span></span> <span data-ttu-id="2389a-165">Trascinare l'angolo inferiore destro del grafico per ingrandirlo.</span><span class="sxs-lookup"><span data-stu-id="2389a-165">Drag the bottom-right corner of the chart to increase the size of the chart.</span></span> <span data-ttu-id="2389a-166">Le dimensioni dell'area di progettazione del report vengono aumentate in base alle dimensioni del grafico.</span><span class="sxs-lookup"><span data-stu-id="2389a-166">Note that the report design surface increases in size to accommodate the chart size.</span></span>  
  
8.  <span data-ttu-id="2389a-167">Fare clic su **Esegui** per visualizzare l'anteprima del report.</span><span class="sxs-lookup"><span data-stu-id="2389a-167">Click **Run** to preview the report.</span></span>  
  
##  <a name="3-format-and-label-the-horizontal-axis"></a><a name="Horizontal"></a><span data-ttu-id="2389a-168">3. formattare l'asse orizzontale e assegnare un'etichetta</span><span class="sxs-lookup"><span data-stu-id="2389a-168">3. Format and Label the Horizontal Axis</span></span>  
 <span data-ttu-id="2389a-169">Per impostazione predefinita, sull'asse orizzontale vengono visualizzati valori in un formato generale che viene ridimensionato automaticamente in base alle dimensioni del grafico.</span><span class="sxs-lookup"><span data-stu-id="2389a-169">By default, the horizontal axis displays values in a general format that is automatically scaled to fit the size of the chart.</span></span>  
  
#### <a name="to-format-a-date-on-the-horizontal-axis"></a><span data-ttu-id="2389a-170">Per formattare una data sull'asse orizzontale</span><span class="sxs-lookup"><span data-stu-id="2389a-170">To format a date on the horizontal axis</span></span>  
  
1.  <span data-ttu-id="2389a-171">Passare alla visualizzazione di progettazione report.</span><span class="sxs-lookup"><span data-stu-id="2389a-171">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="2389a-172">Fare clic con il pulsante destro del mouse sull'asse orizzontale, quindi scegliere **Proprietà asse orizzontale**.</span><span class="sxs-lookup"><span data-stu-id="2389a-172">Right-click the horizontal axis, and then click **Horizontal Axis Properties**.</span></span>  
  
3.  <span data-ttu-id="2389a-173">Fare clic su **numero**.</span><span class="sxs-lookup"><span data-stu-id="2389a-173">Click **Number**.</span></span>  
  
4.  <span data-ttu-id="2389a-174">In **categoria**selezionare **Data**.</span><span class="sxs-lookup"><span data-stu-id="2389a-174">In **Category**, select **Date**.</span></span>  
  
5.  <span data-ttu-id="2389a-175">Nella casella **Tipo** selezionare **31 gennaio 2000**.</span><span class="sxs-lookup"><span data-stu-id="2389a-175">In the **Type** box, select **31 Jan 2000**.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
7.  <span data-ttu-id="2389a-176">Nella scheda Home fare clic su **Esegui** per visualizzare l'anteprima del report.</span><span class="sxs-lookup"><span data-stu-id="2389a-176">On the Home tab, click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="2389a-177">La data viene visualizzata nel formato selezionato.</span><span class="sxs-lookup"><span data-stu-id="2389a-177">The date displays in the date format that you selected.</span></span> <span data-ttu-id="2389a-178">Osservare che sull'asse orizzontale del grafico non viene assegnata un'etichetta a ogni categoria.</span><span class="sxs-lookup"><span data-stu-id="2389a-178">Notice that the chart does not label every category on the horizontal axis.</span></span> <span data-ttu-id="2389a-179">Per impostazione predefinita, vengono incluse solo le etichette che possono essere posizionate accanto all'asse.</span><span class="sxs-lookup"><span data-stu-id="2389a-179">By default, only labels that fit next to the axis are included.</span></span>  
  
 <span data-ttu-id="2389a-180">È possibile personalizzare la visualizzazione delle etichette ruotandole e specificando l'intervallo.</span><span class="sxs-lookup"><span data-stu-id="2389a-180">You can customize the label display by rotating the labels and specifying the interval.</span></span>  
  
#### <a name="to-rotate-the-axis-labels-and-change-the-display-interval-along-the-horizontal-axis"></a><span data-ttu-id="2389a-181">Per ruotare le etichette dell'asse e modificare l'intervallo di visualizzazione lungo l'asse orizzontale</span><span class="sxs-lookup"><span data-stu-id="2389a-181">To rotate the axis labels and change the display interval along the horizontal axis</span></span>  
  
1.  <span data-ttu-id="2389a-182">Passare alla visualizzazione di progettazione report.</span><span class="sxs-lookup"><span data-stu-id="2389a-182">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="2389a-183">Fare clic con il pulsante destro del mouse sul titolo dell'asse orizzontale, quindi scegliere **Mostra titolo asse** per rimuovere il titolo.</span><span class="sxs-lookup"><span data-stu-id="2389a-183">Right-click the horizontal axis title, and then click **Show Axis Title** to remove the title.</span></span> <span data-ttu-id="2389a-184">Poiché sull'asse orizzontale vengono visualizzate le date, il titolo non è necessario.</span><span class="sxs-lookup"><span data-stu-id="2389a-184">Because the horizontal axis displays dates, the title is not needed.</span></span>  
  
3.  <span data-ttu-id="2389a-185">Fare clic con il pulsante destro del mouse sull'asse orizzontale, quindi scegliere **Proprietà asse orizzontale**.</span><span class="sxs-lookup"><span data-stu-id="2389a-185">Right-click the horizontal axis and then click **Horizontal Axis Properties**.</span></span>  
  
4.  <span data-ttu-id="2389a-186">Nella pagina **Opzioni asse** , in intervallo **asse**, digitare **3** per **intervallo**.</span><span class="sxs-lookup"><span data-stu-id="2389a-186">In the **Axis Options** page under **Axis range and interval**, type **3** for **Interval**.</span></span> <span data-ttu-id="2389a-187">Il grafico verrà visualizzato a intervalli di tre giorni.</span><span class="sxs-lookup"><span data-stu-id="2389a-187">The chart will display every third date.</span></span>  
  
5.  <span data-ttu-id="2389a-188">Fare clic su **etichette**.</span><span class="sxs-lookup"><span data-stu-id="2389a-188">Click **Labels**.</span></span>  
  
6.  <span data-ttu-id="2389a-189">In **modifica opzioni adattamento etichetta asse**selezionare **Disabilita adattamento automatico**.</span><span class="sxs-lookup"><span data-stu-id="2389a-189">In **Change axis label auto-fit options**, select **Disable auto-fit**.</span></span>  
  
7.  <span data-ttu-id="2389a-190">In **Angolo di rotazione etichetta**selezionare **-90**.</span><span class="sxs-lookup"><span data-stu-id="2389a-190">In **Label rotation angle**, select **-90**.</span></span>  
  
8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
     <span data-ttu-id="2389a-191">Il testo di esempio per l'asse orizzontale ruota di 90 gradi.</span><span class="sxs-lookup"><span data-stu-id="2389a-191">The sample text for the horizontal axis rotates by 90 degrees.</span></span>  
  
9. <span data-ttu-id="2389a-192">Fare clic su **Esegui** per visualizzare l'anteprima del report.</span><span class="sxs-lookup"><span data-stu-id="2389a-192">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="2389a-193">Sul grafico le etichette vengono ruotate e visualizzate ogni tre giorni.</span><span class="sxs-lookup"><span data-stu-id="2389a-193">On the chart, the labels are rotated and the label for every third date is shown.</span></span>  
  
##  <a name="4-move-the-legend"></a><a name="Legend"></a><span data-ttu-id="2389a-194">4. spostare la legenda</span><span class="sxs-lookup"><span data-stu-id="2389a-194">4. Move the Legend</span></span>  
 <span data-ttu-id="2389a-195">La legenda viene creata automaticamente dai dati di categoria e serie.</span><span class="sxs-lookup"><span data-stu-id="2389a-195">The legend is automatically created from category and series data.</span></span>  
  
#### <a name="to-move-the-legend-below-the-chart-area-of-a-column-chart"></a><span data-ttu-id="2389a-196">Per spostare la legenda al di sotto dell'area del grafico di un istogramma</span><span class="sxs-lookup"><span data-stu-id="2389a-196">To move the legend below the chart area of a column chart</span></span>  
  
1.  <span data-ttu-id="2389a-197">Passare alla visualizzazione di progettazione report.</span><span class="sxs-lookup"><span data-stu-id="2389a-197">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="2389a-198">Fare clic con il pulsante destro del mouse sulla legenda nel grafico, quindi scegliere **Proprietà legenda**.</span><span class="sxs-lookup"><span data-stu-id="2389a-198">Right-click the legend on the chart, and then click **Legend Properties**.</span></span>  
  
3.  <span data-ttu-id="2389a-199">Per **layout e posizione**selezionare una posizione diversa.</span><span class="sxs-lookup"><span data-stu-id="2389a-199">For **Layout and Position**, select a different position.</span></span> <span data-ttu-id="2389a-200">ad esempio la posizione centrale inferiore.</span><span class="sxs-lookup"><span data-stu-id="2389a-200">For example, set the position to the middle bottom option.</span></span>  
  
     <span data-ttu-id="2389a-201">Quando la legenda viene posizionata alla fine o all'inizio di un grafico, il relativo layout viene modificato da verticale in orizzontale.</span><span class="sxs-lookup"><span data-stu-id="2389a-201">When the legend is placed at the top or bottom of a chart, the layout of the legend changes from vertical to horizontal.</span></span> <span data-ttu-id="2389a-202">È possibile selezionare un altro layout nell'elenco a discesa **Layout** .</span><span class="sxs-lookup"><span data-stu-id="2389a-202">You can select a different layout from the **Layout** drop-down list.</span></span>  
  
4.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
5.  <span data-ttu-id="2389a-203">(Facoltativo) Poiché in questa esercitazione si fa riferimento a una sola categoria, la legenda non è necessaria.</span><span class="sxs-lookup"><span data-stu-id="2389a-203">(Optional) Because there is only one category in this tutorial, the legend is not needed.</span></span> <span data-ttu-id="2389a-204">Per rimuovere la legenda, fare clic con il pulsante destro del mouse sulla legenda, quindi scegliere **Elimina legenda**.</span><span class="sxs-lookup"><span data-stu-id="2389a-204">To remove the legend, right-click the legend and then click **Delete Legend**.</span></span>  
  
6.  <span data-ttu-id="2389a-205">Fare clic su **Esegui** per visualizzare l'anteprima del report.</span><span class="sxs-lookup"><span data-stu-id="2389a-205">Click **Run** to preview the report.</span></span>  
  
##  <a name="5-title-the-chart"></a><a name="ChartTitle"></a><span data-ttu-id="2389a-206">5. titolo del grafico</span><span class="sxs-lookup"><span data-stu-id="2389a-206">5. Title the Chart</span></span>  
  
#### <a name="to-change-the-chart-title-above-the-chart-area"></a><span data-ttu-id="2389a-207">Per modificare il titolo di un grafico al di sopra dell'area del grafico</span><span class="sxs-lookup"><span data-stu-id="2389a-207">To change the chart title above the chart area</span></span>  
  
1.  <span data-ttu-id="2389a-208">Passare alla visualizzazione di progettazione report.</span><span class="sxs-lookup"><span data-stu-id="2389a-208">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="2389a-209">Selezionare le parole **titolo grafico** nella parte superiore del grafico, quindi digitare il testo seguente: **Archivia totali ordini di vendita**.</span><span class="sxs-lookup"><span data-stu-id="2389a-209">Select the words **Chart Title** at the top of the chart, and then type the following text: **Store Sales Order Totals**.</span></span>  
  
3.  <span data-ttu-id="2389a-210">Fare clic su **Esegui** per visualizzare l'anteprima del report.</span><span class="sxs-lookup"><span data-stu-id="2389a-210">Click **Run** to preview the report.</span></span>  
  
##  <a name="6-format-and-label-the-vertical-axis"></a><a name="Vertical"></a><span data-ttu-id="2389a-211">6. formattare l'asse verticale e assegnare un'etichetta</span><span class="sxs-lookup"><span data-stu-id="2389a-211">6. Format and Label the Vertical Axis</span></span>  
 <span data-ttu-id="2389a-212">Per impostazione predefinita, sull'asse verticale vengono visualizzati valori in un formato generale che viene ridimensionato automaticamente in base alle dimensioni del grafico.</span><span class="sxs-lookup"><span data-stu-id="2389a-212">By default, the vertical axis displays values in a general format that is automatically scaled to fit the size of the chart.</span></span>  
  
#### <a name="to-format-as-currency-the-numbers-on-the-vertical-axis"></a><span data-ttu-id="2389a-213">Per formattare i numeri come valuta sull'asse verticale</span><span class="sxs-lookup"><span data-stu-id="2389a-213">To format as currency the numbers on the vertical axis</span></span>  
  
1.  <span data-ttu-id="2389a-214">Passare alla visualizzazione di progettazione report.</span><span class="sxs-lookup"><span data-stu-id="2389a-214">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="2389a-215">Fare doppio clic sulle etichette dell'asse verticale lateralmente al grafico per selezionarle.</span><span class="sxs-lookup"><span data-stu-id="2389a-215">Double-click the labels on the vertical axis along the side of the chart to select them.</span></span>  
  
3.  <span data-ttu-id="2389a-216">Sulla barra multifunzione, nel gruppo **numero** della scheda **Home** fare clic sul pulsante **valuta** .</span><span class="sxs-lookup"><span data-stu-id="2389a-216">On the ribbon, on the **Home** tab, in the **Number** group, click the **Currency** button.</span></span> <span data-ttu-id="2389a-217">Le etichette dell'asse cambiano per mostrare il formato della valuta.</span><span class="sxs-lookup"><span data-stu-id="2389a-217">The axis labels change to show the currency format.</span></span>  
  
4.  <span data-ttu-id="2389a-218">Sulla barra multifunzione, nel gruppo **numero** della scheda **Home** fare clic due volte sul pulsante **Diminuisci decimali** per visualizzare il numero arrotondato al dollaro più vicino.</span><span class="sxs-lookup"><span data-stu-id="2389a-218">On the ribbon, on the **Home** tab, in the **Number** group, click the **Decrease Decimal** button two times, to show the number rounded to the nearest dollar.</span></span>  
  
5.  <span data-ttu-id="2389a-219">Fare clic con il pulsante destro del mouse sull'asse verticale e scegliere **Proprietà asse verticale**.</span><span class="sxs-lookup"><span data-stu-id="2389a-219">Right-click the vertical axis and click **Vertical Axis Properties**.</span></span>  
  
6.  <span data-ttu-id="2389a-220">Fare clic su **numero**.</span><span class="sxs-lookup"><span data-stu-id="2389a-220">Click **Number**.</span></span> <span data-ttu-id="2389a-221">Si noti che la **valuta** è già selezionata nella casella **categoria** e le **posizioni decimali** sono già **0** (zero).</span><span class="sxs-lookup"><span data-stu-id="2389a-221">Note that **Currency** is already selected in the **Category** box, and **Decimal places** is already **0** (zero).</span></span>  
  
7.  <span data-ttu-id="2389a-222">Nella casella **Mostra valori in** fare clic su **migliaia**.</span><span class="sxs-lookup"><span data-stu-id="2389a-222">In the **Show Values in** box, click **Thousands**.</span></span>  
  
8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
9. <span data-ttu-id="2389a-223">Fare clic con il pulsante destro del mouse sul titolo dell'asse verticale lungo il lato del grafico e scegliere **Proprietà titolo asse**.</span><span class="sxs-lookup"><span data-stu-id="2389a-223">Right-click the vertical axis title along the side of the chart and click **Axis Title Properties**.</span></span>  
  
10. <span data-ttu-id="2389a-224">Sostituire il testo nel campo **testo titolo** con il testo seguente: **totale vendite (in migliaia)**.</span><span class="sxs-lookup"><span data-stu-id="2389a-224">Replace the text in the **Title text** field with the following text: **Sales Total (in Thousands)**.</span></span> <span data-ttu-id="2389a-225">È anche possibile specificare diverse opzioni relative alla formattazione del titolo.</span><span class="sxs-lookup"><span data-stu-id="2389a-225">You can also specify a variety of options related to how the title is formatted.</span></span>  
  
11. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
12. <span data-ttu-id="2389a-226">Fare clic su **Esegui** per visualizzare l'anteprima del report.</span><span class="sxs-lookup"><span data-stu-id="2389a-226">Click **Run** to preview the report.</span></span>  
  
##  <a name="7-add-a-moving-average"></a><a name="Average"></a><span data-ttu-id="2389a-227">7. aggiungere una media mobili</span><span class="sxs-lookup"><span data-stu-id="2389a-227">7. Add a Moving Average</span></span>  
  
#### <a name="to-add-a-moving-average"></a><span data-ttu-id="2389a-228">Per aggiungere una media mobile</span><span class="sxs-lookup"><span data-stu-id="2389a-228">To add a moving average</span></span>  
  
1.  <span data-ttu-id="2389a-229">Passare alla visualizzazione di progettazione report.</span><span class="sxs-lookup"><span data-stu-id="2389a-229">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="2389a-230">Fare doppio clic sul grafico per visualizzare il riquadro **Dati grafico** .</span><span class="sxs-lookup"><span data-stu-id="2389a-230">Double-click the chart to display the **Chart Data** pane.</span></span>  
  
3.  <span data-ttu-id="2389a-231">Fare clic con il pulsante destro del mouse sul campo **[Sum (Sales)]** che si trova nell'area **valori** , quindi scegliere **Aggiungi serie calcolata**.</span><span class="sxs-lookup"><span data-stu-id="2389a-231">Right-click the **[Sum(Sales)]** field that is in the **Values** area, and then click **Add Calculated Series**.</span></span>  
  
4.  <span data-ttu-id="2389a-232">In **Formula**verificare che sia selezionata l'opzione **Media mobile** .</span><span class="sxs-lookup"><span data-stu-id="2389a-232">In **Formula**, verify that **Moving average** is selected.</span></span>  
  
5.  <span data-ttu-id="2389a-233">In **Imposta parametri formula**, per l'opzione **Periodo**selezionare **4**.</span><span class="sxs-lookup"><span data-stu-id="2389a-233">In **Set Formula Parameters**, for **Period**, select **4**.</span></span>  
  
6.  <span data-ttu-id="2389a-234">Fare clic su **bordo**.</span><span class="sxs-lookup"><span data-stu-id="2389a-234">Click **Border**.</span></span>  
  
7.  <span data-ttu-id="2389a-235">In **lunghezza riga**selezionare **3PT**.</span><span class="sxs-lookup"><span data-stu-id="2389a-235">In **Line width**, select **3pt**.</span></span>  
  
8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
9. <span data-ttu-id="2389a-236">Fare clic su **Esegui** per visualizzare l'anteprima del report.</span><span class="sxs-lookup"><span data-stu-id="2389a-236">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="2389a-237">Nel grafico viene visualizzata una riga in cui è riportata la media mobile delle vendite totali per data, calcolata in base a un intervallo di quattro date.</span><span class="sxs-lookup"><span data-stu-id="2389a-237">The chart displays a line that shows the moving average for total sales by date, averaged over every four dates.</span></span>  
  
##  <a name="8-add-a-report-title"></a><a name="Title"></a><span data-ttu-id="2389a-238">8. aggiungere un titolo al report</span><span class="sxs-lookup"><span data-stu-id="2389a-238">8. Add a Report Title</span></span>  
  
#### <a name="to-add-a-report-title"></a><span data-ttu-id="2389a-239">Per aggiungere il titolo di un report</span><span class="sxs-lookup"><span data-stu-id="2389a-239">To add a report title</span></span>  
  
1.  <span data-ttu-id="2389a-240">Passare alla visualizzazione di progettazione report.</span><span class="sxs-lookup"><span data-stu-id="2389a-240">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="2389a-241">Nell'area di progettazione fare clic su **Fare clic per aggiungere il titolo**.</span><span class="sxs-lookup"><span data-stu-id="2389a-241">On the design surface, click **Click to add title**.</span></span>  
  
3.  <span data-ttu-id="2389a-242">Digitare **grafico vendite**, premere INVIO, quindi digitare **gennaio-dicembre 2009**, in modo che abbia un aspetto simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="2389a-242">Type **Sales Chart**, press ENTER, and then type **January to December 2009**, so it looks like this:</span></span>  
  
     <span data-ttu-id="2389a-243">**Grafico a barre - Vendite**</span><span class="sxs-lookup"><span data-stu-id="2389a-243">**Sales Chart**</span></span>  
  
     <span data-ttu-id="2389a-244">**Gennaio - dicembre 2009**</span><span class="sxs-lookup"><span data-stu-id="2389a-244">**January to December 2009**</span></span>  
  
4.  <span data-ttu-id="2389a-245">Selezionare **grafico vendite**, quindi fare clic sul pulsante **grassetto** nella sezione **carattere** della scheda **Home** della barra multifunzione.</span><span class="sxs-lookup"><span data-stu-id="2389a-245">Select **Sales Chart**, and click the **Bold** button in the **Font** section on the **Home** tab of the ribbon.</span></span>  
  
5.  <span data-ttu-id="2389a-246">Selezionare **gennaio-dicembre 2009**e nella sezione **carattere** della scheda **Home** impostare le dimensioni del carattere su **10**.</span><span class="sxs-lookup"><span data-stu-id="2389a-246">Select **January to December 2009**, and in the **Font** section on the **Home** tab, set the font size to **10**.</span></span>  
  
6.  <span data-ttu-id="2389a-247">Opzionale Potrebbe essere necessario fare in modo che la casella di testo del **titolo** sia più alta per contenere le due righe di testo spostando verso il basso le frecce a due punte quando si fa clic al centro del bordo inferiore.</span><span class="sxs-lookup"><span data-stu-id="2389a-247">(Optional) You may need to make the **Title** text box taller to accommodate the two lines of text by pulling down on the double-headed arrows when you click in the middle of the bottom edge.</span></span>  
  
     <span data-ttu-id="2389a-248">Il titolo verrà visualizzato nella parte superiore del report.</span><span class="sxs-lookup"><span data-stu-id="2389a-248">This title will appear at the top of the report.</span></span> <span data-ttu-id="2389a-249">Quando non è definita un'intestazione di pagina, gli elementi nella parte superiore del corpo del report equivalgono a un'intestazione di report.</span><span class="sxs-lookup"><span data-stu-id="2389a-249">When there is no page header defined, items at the top of the report body are the equivalent of a report header.</span></span>  
  
7.  <span data-ttu-id="2389a-250">Fare clic su **Esegui** per visualizzare l'anteprima del report.</span><span class="sxs-lookup"><span data-stu-id="2389a-250">Click **Run** to preview the report.</span></span>  
  
##  <a name="9-save-the-report"></a><a name="Save"></a><span data-ttu-id="2389a-251">9. salvare il report</span><span class="sxs-lookup"><span data-stu-id="2389a-251">9. Save the Report</span></span>  
  
#### <a name="to-save-the-report"></a><span data-ttu-id="2389a-252">Per salvare il report</span><span class="sxs-lookup"><span data-stu-id="2389a-252">To save the report</span></span>  
  
1.  <span data-ttu-id="2389a-253">Passare alla visualizzazione di progettazione report.</span><span class="sxs-lookup"><span data-stu-id="2389a-253">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="2389a-254">Fare clic sul pulsante Generatore report , quindi su **Salva con nome**.</span><span class="sxs-lookup"><span data-stu-id="2389a-254">From the Report Builder button, click **Save As**.</span></span>  
  
3.  <span data-ttu-id="2389a-255">In **Nome**digitare **Istogramma ordini vendita**.</span><span class="sxs-lookup"><span data-stu-id="2389a-255">In **Name**, type **Sales Order Column Chart**.</span></span>  
  
4.  <span data-ttu-id="2389a-256">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="2389a-256">Click **Save**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="2389a-257">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="2389a-257">Next Steps</span></span>  
 <span data-ttu-id="2389a-258">Questo passaggio conclude l'esercitazione relativa all'aggiunta di un istogramma al report.</span><span class="sxs-lookup"><span data-stu-id="2389a-258">You have successfully completed the Adding a Column Chart to Your Report tutorial.</span></span> <span data-ttu-id="2389a-259">Per altre informazioni sui grafici, vedere [Grafici &#40;Generatore report e SSRS&#41;](report-design/charts-report-builder-and-ssrs.md) e [Grafici sparkline e barre dei dati &#40;Generatore report e SSRS&#41;](report-design/sparklines-and-data-bars-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="2389a-259">To learn more about charts, see [Charts &#40;Report Builder and SSRS&#41;](report-design/charts-report-builder-and-ssrs.md) and [Sparklines and Data Bars &#40;Report Builder and SSRS&#41;](report-design/sparklines-and-data-bars-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2389a-260">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2389a-260">See Also</span></span>  
 <span data-ttu-id="2389a-261">[Esercitazioni &#40;Generatore report&#41;](report-builder-tutorials.md) </span><span class="sxs-lookup"><span data-stu-id="2389a-261">[Tutorials &#40;Report Builder&#41;](report-builder-tutorials.md) </span></span>  
 [<span data-ttu-id="2389a-262">Generatore report in SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="2389a-262">Report Builder in SQL Server 2014</span></span>](report-builder/report-builder-in-sql-server-2016.md)  
  
  
